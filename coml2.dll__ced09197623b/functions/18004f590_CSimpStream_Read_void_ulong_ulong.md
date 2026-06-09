# CSimpStream::Read(void *,ulong,ulong *)

- ea: `0x18004f590`
- end: `0x18004f625`
- name: `?Read@CSimpStream@@UEAAJPEAXKPEAK@Z`
- size: `149`
- prototype: `int(CSimpStream *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18004f630`

## callees

- `0x180023e70`
- `0x180026bc4`
- `0x18004f590`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f609`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f609`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18004f5fa`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18004f5fa`

## pseudocode

```c
__int64 __fastcall CSimpStream::Read(HANDLE *this, void *a2, unsigned int a3, unsigned int *a4)
{
  const void *v4; // r10
  _DWORD *v6; // r9
  DWORD v7; // r8d
  DWORD *v8; // r9
  void *v9; // r10
  DWORD *v11; // rbx
  BOOL File; // eax
  DWORD LastError; // eax
  int v14; // [rsp+58h] [rbp+20h] BYREF

  v14 = 0;
  v4 = a2;
  if ( a4 )
  {
    if ( !(unsigned int)IsValidReadPtrIn(a4, 4u) )
      return 2147680265LL;
    *v6 = 0;
  }
  if ( !(unsigned int)IsValidReadPtrIn(v4, a3) )
    return 2147680265LL;
  v11 = (DWORD *)&v14;
  if ( v8 )
    v11 = v8;
  File = ReadFile(this[5], v9, v7, v11, 0);
  *((_DWORD *)this + 6) += *v11;
  if ( File )
    return 0;
  LastError = GetLastError();
  return Win32ErrorToScode(LastError);
}

```

## disassembly

```asm
0x18004f590  mov     [rsp+arg_0], rbx
0x18004f595  push    rdi
0x18004f596  sub     rsp, 30h
0x18004f59a  mov     [rsp+38h+arg_18], 0
0x18004f5a2  mov     r10, rdx
0x18004f5a5  mov     rdi, rcx
0x18004f5a8  test    r9, r9
0x18004f5ab  jz      short loc_18004F5C5
0x18004f5ad  mov     edx, 4; unsigned __int64
0x18004f5b2  mov     rcx, r9; void *
0x18004f5b5  call    ?IsValidReadPtrIn@@YAHPEBX_K@Z; IsValidReadPtrIn(void const *,unsigned __int64)
0x18004f5ba  test    eax, eax
0x18004f5bc  jz      short loc_18004F5D4
0x18004f5be  mov     dword ptr [r9], 0
0x18004f5c5  mov     edx, r8d; unsigned __int64
0x18004f5c8  mov     rcx, r10; void *
0x18004f5cb  call    ?IsValidReadPtrIn@@YAHPEBX_K@Z; IsValidReadPtrIn(void const *,unsigned __int64)
0x18004f5d0  test    eax, eax
0x18004f5d2  jnz     short loc_18004F5DB
0x18004f5d4  mov     eax, 80030009h
0x18004f5d9  jmp     short loc_18004F61A
0x18004f5db  mov     rcx, [rdi+28h]; hFile
0x18004f5df  lea     rbx, [rsp+38h+arg_18]
0x18004f5e4  test    r9, r9
0x18004f5e7  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x18004f5f0  mov     rdx, r10; lpBuffer
0x18004f5f3  cmovnz  rbx, r9
0x18004f5f7  mov     r9, rbx; lpNumberOfBytesRead
0x18004f5fa  call    cs:__imp_ReadFile
0x18004f600  mov     ecx, [rbx]
0x18004f602  add     [rdi+18h], ecx
0x18004f605  test    eax, eax
0x18004f607  jnz     short loc_18004F618
0x18004f609  call    cs:__imp_GetLastError
0x18004f60f  mov     ecx, eax; unsigned int
0x18004f611  call    ?Win32ErrorToScode@@YAJK@Z; Win32ErrorToScode(ulong)
0x18004f616  jmp     short loc_18004F61A
0x18004f618  xor     eax, eax
0x18004f61a  mov     rbx, [rsp+38h+arg_0]
0x18004f61f  add     rsp, 30h
0x18004f623  pop     rdi
0x18004f624  retn
```
