# rasWriteFile

- ea: `0x180095000`
- end: `0x1800950ef`
- name: `rasWriteFile`
- size: `239`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18007f488`

## callees

- `0x180094f40`
- `0x180095000`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009501b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180095099`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800950d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009501b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180095099`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800950d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095073`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180095073`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009505f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18009505f`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180095086`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x180095086`

## pseudocode

```c
BOOL __fastcall rasWriteFile(__int64 a1)
{
  void *v2; // rcx
  BOOL result; // eax
  int v4; // ebp
  HANDLE FileW; // rax
  void *v6; // rsi
  _QWORD *v7; // rdi

  v2 = *(void **)(a1 + 24);
  if ( v2 != (void *)-1LL )
  {
    result = CloseHandle(v2);
    if ( !result )
      return result;
    *(_QWORD *)(a1 + 24) = -1;
  }
  v4 = 1;
  FileW = CreateFileW((LPCWSTR)(a1 + 52), 0xC0000000, 1u, 0, 2u, 0x80u, 0);
  v6 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    GetLastError();
  }
  else
  {
    if ( GetFileType(FileW) == 1 )
    {
      v7 = **(_QWORD ***)a1;
      if ( v7 != *(_QWORD **)a1 )
      {
        while ( (unsigned int)rasPutFileLine(v6) )
        {
          v7 = (_QWORD *)*v7;
          if ( v7 == *(_QWORD **)a1 )
            goto LABEL_14;
        }
        v4 = 0;
      }
LABEL_14:
      CloseHandle(v6);
      result = v4;
      goto LABEL_15;
    }
    CloseHandle(v6);
  }
  result = 0;
LABEL_15:
  *(_QWORD *)(a1 + 24) = -1;
  return result;
}

```

## disassembly

```asm
0x180095000  push    rbx
0x180095002  push    rbp
0x180095003  push    rsi
0x180095004  push    rdi
0x180095005  push    r14
0x180095007  sub     rsp, 40h
0x18009500b  mov     rbx, rcx
0x18009500e  or      r14, 0FFFFFFFFFFFFFFFFh
0x180095012  mov     rcx, [rcx+18h]; hObject
0x180095016  cmp     rcx, r14
0x180095019  jz      short loc_180095033
0x18009501b  call    cs:__imp_CloseHandle
0x180095022  nop     dword ptr [rax+rax+00h]
0x180095027  test    eax, eax
0x180095029  jz      loc_1800950E3
0x18009502f  mov     [rbx+18h], r14
0x180095033  xor     r9d, r9d; lpSecurityAttributes
0x180095036  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x18009503f  lea     rcx, [rbx+34h]; lpFileName
0x180095043  mov     [rsp+68h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18009504b  mov     edx, 0C0000000h; dwDesiredAccess
0x180095050  mov     [rsp+68h+dwCreationDisposition], 2; dwCreationDisposition
0x180095058  lea     ebp, [r9+1]
0x18009505c  mov     r8d, ebp; dwShareMode
0x18009505f  call    cs:__imp_CreateFileW
0x180095066  nop     dword ptr [rax+rax+00h]
0x18009506b  mov     rsi, rax
0x18009506e  cmp     rax, r14
0x180095071  jnz     short loc_180095083
0x180095073  call    cs:__imp_GetLastError
0x18009507a  nop     dword ptr [rax+rax+00h]
0x18009507f  xor     eax, eax
0x180095081  jmp     short loc_1800950DF
0x180095083  mov     rcx, rsi; hFile
0x180095086  call    cs:__imp_GetFileType
0x18009508d  nop     dword ptr [rax+rax+00h]
0x180095092  cmp     eax, ebp
0x180095094  jz      short loc_1800950A7
0x180095096  mov     rcx, rsi; hObject
0x180095099  call    cs:__imp_CloseHandle
0x1800950a0  nop     dword ptr [rax+rax+00h]
0x1800950a5  jmp     short loc_18009507F
0x1800950a7  mov     rax, [rbx]
0x1800950aa  mov     rdi, [rax]
0x1800950ad  cmp     rdi, rax
0x1800950b0  jz      short loc_1800950CE
0x1800950b2  mov     rdx, [rdi+10h]
0x1800950b6  mov     rcx, rsi; hFile
0x1800950b9  call    rasPutFileLine
0x1800950be  test    eax, eax
0x1800950c0  jz      short loc_1800950CC
0x1800950c2  mov     rdi, [rdi]
0x1800950c5  cmp     rdi, [rbx]
0x1800950c8  jnz     short loc_1800950B2
0x1800950ca  jmp     short loc_1800950CE
0x1800950cc  xor     ebp, ebp
0x1800950ce  mov     rcx, rsi; hObject
0x1800950d1  call    cs:__imp_CloseHandle
0x1800950d8  nop     dword ptr [rax+rax+00h]
0x1800950dd  mov     eax, ebp
0x1800950df  mov     [rbx+18h], r14
0x1800950e3  add     rsp, 40h
0x1800950e7  pop     r14
0x1800950e9  pop     rdi
0x1800950ea  pop     rsi
0x1800950eb  pop     rbp
0x1800950ec  pop     rbx
0x1800950ed  retn
```
