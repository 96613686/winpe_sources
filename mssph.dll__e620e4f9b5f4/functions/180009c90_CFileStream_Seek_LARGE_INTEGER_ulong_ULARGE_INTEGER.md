# CFileStream::Seek(_LARGE_INTEGER,ulong,_ULARGE_INTEGER *)

- ea: `0x180009c90`
- end: `0x180009d35`
- name: `?Seek@CFileStream@@UEAAJT_LARGE_INTEGER@@KPEAT_ULARGE_INTEGER@@@Z`
- size: `165`
- prototype: `__int64 __fastcall(CFileStream *__hidden this, union _LARGE_INTEGER, unsigned int, union _ULARGE_INTEGER *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180009c90`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009cde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009cde`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180009cc1`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180009cc1`

## pseudocode

```c
__int64 __fastcall CFileStream::Seek(CFileStream *this, union _LARGE_INTEGER a2, int a3, union _ULARGE_INTEGER *a4)
{
  DWORD v5; // r9d
  void *v6; // rcx
  signed int v7; // ebx
  DWORD v8; // edi
  signed int LastError; // eax
  int v11; // r8d
  LONG DistanceToMoveHigh; // [rsp+40h] [rbp+18h] BYREF

  if ( a3 )
  {
    v11 = a3 - 1;
    if ( v11 )
    {
      if ( v11 != 1 )
        return 2147942487LL;
      v5 = 2;
    }
    else
    {
      v5 = 1;
    }
  }
  else
  {
    v5 = 0;
  }
  v6 = (void *)*((_QWORD *)this + 3);
  v7 = 0;
  DistanceToMoveHigh = a2.HighPart;
  v8 = SetFilePointer(v6, a2.LowPart, &DistanceToMoveHigh, v5);
  if ( v8 != -1 )
    goto LABEL_4;
  LastError = GetLastError();
  v7 = LastError;
  if ( LastError > 0 )
    v7 = (unsigned __int16)LastError | 0x80070000;
  if ( v7 >= 0 )
  {
LABEL_4:
    if ( a4 )
    {
      a4->HighPart = DistanceToMoveHigh;
      a4->LowPart = v8;
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180009c90  push    rsi
0x180009c92  sub     rsp, 20h
0x180009c96  mov     rsi, r9
0x180009c99  test    r8d, r8d
0x180009c9c  jnz     short loc_180009D00
0x180009c9e  xor     r9d, r9d; dwMoveMethod
0x180009ca1  mov     rcx, [rcx+18h]; hFile
0x180009ca5  lea     r8, [rsp+28h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x180009caa  mov     rax, rdx
0x180009cad  mov     [rsp+28h+arg_0], rbx
0x180009cb2  shr     rax, 20h
0x180009cb6  xor     ebx, ebx
0x180009cb8  mov     [rsp+28h+DistanceToMoveHigh], eax
0x180009cbc  mov     [rsp+28h+arg_8], rdi
0x180009cc1  call    cs:__imp_SetFilePointer
0x180009cc7  mov     edi, eax
0x180009cc9  cmp     eax, 0FFFFFFFFh
0x180009ccc  jz      short loc_180009CDE
0x180009cce  test    rsi, rsi
0x180009cd1  jz      short loc_180009CEE
0x180009cd3  mov     ecx, [rsp+28h+DistanceToMoveHigh]
0x180009cd7  mov     [rsi+4], ecx
0x180009cda  mov     [rsi], edi
0x180009cdc  jmp     short loc_180009CEE
0x180009cde  call    cs:__imp_GetLastError
0x180009ce4  mov     ebx, eax
0x180009ce6  test    eax, eax
0x180009ce8  jg      short loc_180009D2A
0x180009cea  test    ebx, ebx
0x180009cec  jns     short loc_180009CCE
0x180009cee  mov     rdi, [rsp+28h+arg_8]
0x180009cf3  mov     eax, ebx
0x180009cf5  mov     rbx, [rsp+28h+arg_0]
0x180009cfa  add     rsp, 20h
0x180009cfe  pop     rsi
0x180009cff  retn
0x180009d00  sub     r8d, 1
0x180009d04  jz      short loc_180009D1F
0x180009d06  cmp     r8d, 1
0x180009d0a  jz      short loc_180009D17
0x180009d0c  mov     eax, 80070057h
0x180009d11  add     rsp, 20h
0x180009d15  pop     rsi
0x180009d16  retn
0x180009d17  mov     r9d, 2
0x180009d1d  jmp     short loc_180009CA1
0x180009d1f  mov     r9d, 1
0x180009d25  jmp     loc_180009CA1
0x180009d2a  movzx   ebx, ax
0x180009d2d  or      ebx, 80070000h
0x180009d33  jmp     short loc_180009CEA
```
