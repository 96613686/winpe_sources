# rasWriteFile

- ea: `0x1800905ac`
- end: `0x180090708`
- name: `rasWriteFile`
- size: `348`
- prototype: `BOOL __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18007b698`

## callees

- `0x18000bb90`
- `0x1800905ac`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800905e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009064c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800906d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800905e3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009064c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800906d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009062f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800906c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009062f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800906c9`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18009063f`
- `api-ms-win-core-file-l1-1-0!GetFileType` at `0x18009063f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180090621`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180090621`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800906b5`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800906b5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180090696`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x180090696`

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
  const char *v8; // r9
  DWORD v9; // eax
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-C48h] BYREF
  char pszDest[3088]; // [rsp+50h] [rbp-C38h] BYREF

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
        while ( 1 )
        {
          v8 = (const char *)v7[2];
          NumberOfBytesWritten = 0;
          if ( StringCchPrintfA(pszDest, 0xC04u, "%s%s", v8, "\r\n") )
            break;
          v9 = lstrlenA(pszDest);
          if ( !WriteFile(v6, pszDest, v9, &NumberOfBytesWritten, 0) )
          {
            GetLastError();
            break;
          }
          v7 = (_QWORD *)*v7;
          if ( v7 == *(_QWORD **)a1 )
            goto LABEL_16;
        }
        v4 = 0;
      }
LABEL_16:
      CloseHandle(v6);
      result = v4;
      goto LABEL_17;
    }
    CloseHandle(v6);
  }
  result = 0;
LABEL_17:
  *(_QWORD *)(a1 + 24) = -1;
  return result;
}

```

## disassembly

```asm
0x1800905ac  mov     [rsp+arg_8], rbx
0x1800905b1  mov     [rsp+arg_10], rbp
0x1800905b6  push    rsi
0x1800905b7  push    rdi
0x1800905b8  push    r14
0x1800905ba  sub     rsp, 0C70h
0x1800905c1  mov     rax, cs:__security_cookie
0x1800905c8  xor     rax, rsp
0x1800905cb  mov     [rsp+0C88h+var_28], rax
0x1800905d3  mov     rbx, rcx
0x1800905d6  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800905da  mov     rcx, [rcx+18h]; hObject
0x1800905de  cmp     rcx, r14
0x1800905e1  jz      short loc_1800905F5
0x1800905e3  call    cs:__imp_CloseHandle
0x1800905e9  test    eax, eax
0x1800905eb  jz      loc_1800906E0
0x1800905f1  mov     [rbx+18h], r14
0x1800905f5  xor     r9d, r9d; lpSecurityAttributes
0x1800905f8  mov     [rsp+0C88h+hTemplateFile], 0; hTemplateFile
0x180090601  lea     rcx, [rbx+34h]; lpFileName
0x180090605  mov     [rsp+0C88h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18009060d  mov     edx, 0C0000000h; dwDesiredAccess
0x180090612  mov     [rsp+0C88h+dwCreationDisposition], 2; dwCreationDisposition
0x18009061a  lea     ebp, [r9+1]
0x18009061e  mov     r8d, ebp; dwShareMode
0x180090621  call    cs:__imp_CreateFileW
0x180090627  mov     rsi, rax
0x18009062a  cmp     rax, r14
0x18009062d  jnz     short loc_18009063C
0x18009062f  call    cs:__imp_GetLastError
0x180090635  xor     eax, eax
0x180090637  jmp     loc_1800906DC
0x18009063c  mov     rcx, rsi; hFile
0x18009063f  call    cs:__imp_GetFileType
0x180090645  cmp     eax, ebp
0x180090647  jz      short loc_180090654
0x180090649  mov     rcx, rsi; hObject
0x18009064c  call    cs:__imp_CloseHandle
0x180090652  jmp     short loc_180090635
0x180090654  mov     rax, [rbx]
0x180090657  mov     rdi, [rax]
0x18009065a  cmp     rdi, rax
0x18009065d  jz      short loc_1800906D1
0x18009065f  mov     r9, [rdi+10h]
0x180090663  lea     rax, asc_1800F3A44; "\r\n"
0x18009066a  lea     r8, aSS_4; "%s%s"
0x180090671  mov     qword ptr [rsp+0C88h+dwCreationDisposition], rax
0x180090676  mov     edx, 0C04h; cchDest
0x18009067b  mov     [rsp+0C88h+NumberOfBytesWritten], 0
0x180090683  lea     rcx, [rsp+0C88h+pszDest]; pszDest
0x180090688  call    StringCchPrintfA
0x18009068d  test    eax, eax
0x18009068f  jnz     short loc_1800906CF
0x180090691  lea     rcx, [rsp+0C88h+pszDest]; lpString
0x180090696  call    cs:__imp_lstrlenA
0x18009069c  lea     r9, [rsp+0C88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800906a1  mov     qword ptr [rsp+0C88h+dwCreationDisposition], 0; lpOverlapped
0x1800906aa  mov     r8d, eax; nNumberOfBytesToWrite
0x1800906ad  lea     rdx, [rsp+0C88h+pszDest]; lpBuffer
0x1800906b2  mov     rcx, rsi; hFile
0x1800906b5  call    cs:__imp_WriteFile
0x1800906bb  test    eax, eax
0x1800906bd  jz      short loc_1800906C9
0x1800906bf  mov     rdi, [rdi]
0x1800906c2  cmp     rdi, [rbx]
0x1800906c5  jnz     short loc_18009065F
0x1800906c7  jmp     short loc_1800906D1
0x1800906c9  call    cs:__imp_GetLastError
0x1800906cf  xor     ebp, ebp
0x1800906d1  mov     rcx, rsi; hObject
0x1800906d4  call    cs:__imp_CloseHandle
0x1800906da  mov     eax, ebp
0x1800906dc  mov     [rbx+18h], r14
0x1800906e0  mov     rcx, [rsp+0C88h+var_28]
0x1800906e8  xor     rcx, rsp; StackCookie
0x1800906eb  call    __security_check_cookie
0x1800906f0  lea     r11, [rsp+0C88h+var_18]
0x1800906f8  mov     rbx, [r11+28h]
0x1800906fc  mov     rbp, [r11+30h]
0x180090700  mov     rsp, r11
0x180090703  pop     r14
0x180090705  pop     rdi
0x180090706  pop     rsi
0x180090707  retn
```
