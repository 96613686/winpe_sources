# CFileStream::Seek(_LARGE_INTEGER,ulong,_ULARGE_INTEGER *)

- ea: `0x180037580`
- end: `0x180037619`
- name: `?Seek@CFileStream@@UEAAJT_LARGE_INTEGER@@KPEAT_ULARGE_INTEGER@@@Z`
- size: `153`
- prototype: `__int64 __fastcall(CFileStream *__hidden this, union _LARGE_INTEGER, unsigned int, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180037580`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800375e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800375e0`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800375d3`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800375d3`

## pseudocode

```c
__int64 __fastcall CFileStream::Seek(CFileStream *this, union _LARGE_INTEGER a2, int a3, union _ULARGE_INTEGER *a4)
{
  int v5; // r8d
  DWORD v7; // r9d
  void *v8; // rcx
  signed int v9; // ebx
  DWORD v10; // esi
  signed int LastError; // eax
  LONG DistanceToMoveHigh; // [rsp+40h] [rbp+18h] BYREF

  if ( a3 )
  {
    v5 = a3 - 1;
    if ( v5 )
    {
      if ( v5 != 1 )
        return 2147942487LL;
      v7 = 2;
    }
    else
    {
      v7 = 1;
    }
  }
  else
  {
    v7 = 0;
  }
  v8 = (void *)*((_QWORD *)this + 3);
  v9 = 0;
  DistanceToMoveHigh = a2.HighPart;
  v10 = SetFilePointer(v8, a2.LowPart, &DistanceToMoveHigh, v7);
  if ( v10 != -1 )
    goto LABEL_12;
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
  if ( v9 >= 0 )
  {
LABEL_12:
    if ( a4 )
    {
      a4->HighPart = DistanceToMoveHigh;
      a4->LowPart = v10;
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180037580  mov     [rsp+arg_0], rbx
0x180037585  mov     [rsp+arg_8], rsi
0x18003758a  push    rdi
0x18003758b  sub     rsp, 20h
0x18003758f  mov     rdi, r9
0x180037592  test    r8d, r8d
0x180037595  jz      short loc_1800375BA
0x180037597  sub     r8d, 1
0x18003759b  jz      short loc_1800375B2
0x18003759d  cmp     r8d, 1
0x1800375a1  jz      short loc_1800375AA
0x1800375a3  mov     eax, 80070057h
0x1800375a8  jmp     short loc_180037609
0x1800375aa  mov     r9d, 2
0x1800375b0  jmp     short loc_1800375BD
0x1800375b2  mov     r9d, 1
0x1800375b8  jmp     short loc_1800375BD
0x1800375ba  xor     r9d, r9d; dwMoveMethod
0x1800375bd  mov     rcx, [rcx+18h]; hFile
0x1800375c1  lea     r8, [rsp+28h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x1800375c6  mov     rax, rdx
0x1800375c9  xor     ebx, ebx
0x1800375cb  shr     rax, 20h
0x1800375cf  mov     [rsp+28h+DistanceToMoveHigh], eax
0x1800375d3  call    cs:__imp_SetFilePointer
0x1800375d9  mov     esi, eax
0x1800375db  cmp     eax, 0FFFFFFFFh
0x1800375de  jnz     short loc_1800375F9
0x1800375e0  call    cs:__imp_GetLastError
0x1800375e6  mov     ebx, eax
0x1800375e8  test    eax, eax
0x1800375ea  jle     short loc_1800375F5
0x1800375ec  movzx   ebx, ax
0x1800375ef  or      ebx, 80070000h
0x1800375f5  test    ebx, ebx
0x1800375f7  js      short loc_180037607
0x1800375f9  test    rdi, rdi
0x1800375fc  jz      short loc_180037607
0x1800375fe  mov     ecx, [rsp+28h+DistanceToMoveHigh]
0x180037602  mov     [rdi+4], ecx
0x180037605  mov     [rdi], esi
0x180037607  mov     eax, ebx
0x180037609  mov     rbx, [rsp+28h+arg_0]
0x18003760e  mov     rsi, [rsp+28h+arg_8]
0x180037613  add     rsp, 20h
0x180037617  pop     rdi
0x180037618  retn
```
