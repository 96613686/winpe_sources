# W3_RESPONSE::WriteEntityChunkByReference(_HTTP_DATA_CHUNK *,long)

- ea: `0x180014db0`
- end: `0x180014f99`
- name: `?WriteEntityChunkByReference@W3_RESPONSE@@QEAAJPEAU_HTTP_DATA_CHUNK@@J@Z`
- size: `489`
- prototype: `__int64 __fastcall(W3_RESPONSE *__hidden this, struct _HTTP_DATA_CHUNK *, int)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180004340`
- `0x180004c00`
- `0x180022e70`
- `0x1800265b8`
- `0x1800268d0`

## callees

- `0x180014db0`
- `0x18003438e`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014efe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014efe`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180014ebe`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180014ebe`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180014e4f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180014ee8`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180014f46`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180014e4f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180014ee8`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180014f46`
- `iisutil!?Resize@BUFFER@@QEAA_NKK@Z` at `0x180014e21`
- `iisutil!?Resize@BUFFER@@QEAA_NKK@Z` at `0x180014e21`

## pseudocode

```c
signed int __fastcall W3_RESPONSE::WriteEntityChunkByReference(W3_RESPONSE *this, struct _HTTP_DATA_CHUNK *a2, int a3)
{
  __int64 v3; // r15
  void *v6; // rdi
  BOOL v7; // esi
  unsigned int v8; // esi
  char *v9; // rax
  char *v10; // rdi
  __int64 v11; // rcx
  signed int result; // eax
  ULARGE_INTEGER Length; // rax
  HANDLE FileHandle; // rcx
  const void *v15; // rdi
  size_t v16; // rsi
  void *Ptr; // rax
  unsigned int v18; // eax
  __int64 v19; // rsi
  union _LARGE_INTEGER FileSize; // [rsp+48h] [rbp+10h] BYREF

  v3 = a3;
  if ( !a2 )
    return -2147024809;
  if ( (unsigned __int16)(*((_WORD *)this + 296) + 1) < *((_WORD *)this + 296) )
    return -2147024362;
  if ( a2->DataChunkType != HttpDataChunkFromFileHandle )
    goto LABEL_4;
  Length = a2->FromFileHandle.ByteRange.Length;
  if ( !Length.QuadPart )
    return 0;
  if ( Length.QuadPart != -1 )
  {
LABEL_4:
    v6 = (void *)*((_QWORD *)this + 75);
    v7 = 0;
    if ( v6 )
      v7 = BUFFER::QueryPtr((W3_RESPONSE *)((char *)this + 1000)) != v6;
    if ( !BUFFER::Resize((W3_RESPONSE *)((char *)this + 1000), 32 * (*((unsigned __int16 *)this + 296) + 1), 0x200u) )
      return -2147024888;
    if ( v7 )
    {
      v15 = (const void *)*((_QWORD *)this + 75);
      v16 = 32LL * *((unsigned __int16 *)this + 296);
      Ptr = BUFFER::QueryPtr((W3_RESPONSE *)((char *)this + 1000));
      memmove_0(Ptr, v15, v16);
    }
    v8 = *((unsigned __int16 *)this + 296);
    *((_WORD *)this + 296) = v8 + 1;
    v9 = (char *)BUFFER::QueryPtr((W3_RESPONSE *)((char *)this + 1000));
    *((_QWORD *)this + 75) = v9;
    v10 = v9;
    if ( (_DWORD)v3 == -1 )
    {
      v11 = 32LL * v8;
      *(_OWORD *)&v9[v11] = *(_OWORD *)&a2->DataChunkType;
      *(_OWORD *)&v9[v11 + 16] = *(_OWORD *)&a2->FromFragmentCacheEx.ByteRange.Length.LowPart;
    }
    else
    {
      v18 = v8;
      v19 = 32 * v3;
      if ( v18 > (unsigned int)v3 )
        memmove_0(&v10[v19 + 32], &v10[v19], 32LL * (v18 - (unsigned int)v3));
      *(_OWORD *)&v10[32 * v3] = *(_OWORD *)&a2->DataChunkType;
      *(_OWORD *)&v10[v19 + 16] = *(_OWORD *)&a2->FromFragmentCacheEx.ByteRange.Length.LowPart;
    }
    return 0;
  }
  FileHandle = a2->FromFileHandle.FileHandle;
  FileSize.QuadPart = 0;
  if ( GetFileSizeEx(FileHandle, &FileSize) )
  {
    a2->FromFileHandle.ByteRange.Length.QuadPart = FileSize.QuadPart
                                                 - a2->FromFileHandle.ByteRange.StartingOffset.QuadPart;
    goto LABEL_4;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180014db0  push    rbx
0x180014db2  push    rbp
0x180014db3  push    r15
0x180014db5  sub     rsp, 20h
0x180014db9  movsxd  r15, r8d
0x180014dbc  mov     rbx, rdx
0x180014dbf  mov     rbp, rcx
0x180014dc2  test    rdx, rdx
0x180014dc5  jz      loc_180014F19
0x180014dcb  movzx   ecx, word ptr [rcx+250h]
0x180014dd2  lea     eax, [rcx+1]
0x180014dd5  cmp     ax, cx
0x180014dd8  jb      loc_180014F23
0x180014dde  cmp     dword ptr [rdx], 1
0x180014de1  mov     [rsp+38h+arg_0], rsi
0x180014de6  mov     [rsp+38h+arg_10], rdi
0x180014deb  mov     [rsp+38h+arg_18], r14
0x180014df0  jz      loc_180014E99
0x180014df6  mov     rdi, [rbp+258h]
0x180014dfd  xor     esi, esi
0x180014dff  test    rdi, rdi
0x180014e02  jnz     loc_180014EE1
0x180014e08  movzx   edx, word ptr [rbp+250h]
0x180014e0f  lea     rcx, [rbp+3E8h]
0x180014e16  inc     edx
0x180014e18  mov     r8d, 200h
0x180014e1e  shl     edx, 5
0x180014e21  call    cs:__imp_?Resize@BUFFER@@QEAA_NKK@Z; BUFFER::Resize(ulong,ulong)
0x180014e27  test    al, al
0x180014e29  jz      loc_180014EDA
0x180014e2f  test    esi, esi
0x180014e31  jnz     loc_180014F2D
0x180014e37  movzx   esi, word ptr [rbp+250h]
0x180014e3e  lea     rcx, [rbp+3E8h]
0x180014e45  lea     eax, [rsi+1]
0x180014e48  mov     [rbp+250h], ax
0x180014e4f  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180014e55  mov     [rbp+258h], rax
0x180014e5c  mov     rdi, rax
0x180014e5f  cmp     r15d, 0FFFFFFFFh
0x180014e63  jnz     loc_180014F5F
0x180014e69  movups  xmm0, xmmword ptr [rbx]
0x180014e6c  mov     ecx, esi
0x180014e6e  shl     rcx, 5
0x180014e72  movups  xmmword ptr [rcx+rax], xmm0
0x180014e76  movups  xmm1, xmmword ptr [rbx+10h]
0x180014e7a  movups  xmmword ptr [rcx+rax+10h], xmm1
0x180014e7f  xor     eax, eax
0x180014e81  mov     rdi, [rsp+38h+arg_10]
0x180014e86  mov     rsi, [rsp+38h+arg_0]
0x180014e8b  mov     r14, [rsp+38h+arg_18]
0x180014e90  add     rsp, 20h
0x180014e94  pop     r15
0x180014e96  pop     rbp
0x180014e97  pop     rbx
0x180014e98  retn
0x180014e99  mov     rax, [rdx+10h]
0x180014e9d  test    rax, rax
0x180014ea0  jz      short loc_180014E7F
0x180014ea2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180014ea6  jnz     loc_180014DF6
0x180014eac  mov     rcx, [rbx+18h]; hFile
0x180014eb0  lea     rdx, [rsp+38h+FileSize]; lpFileSize
0x180014eb5  mov     qword ptr [rsp+38h+FileSize], 0
0x180014ebe  call    cs:__imp_GetFileSizeEx
0x180014ec4  test    eax, eax
0x180014ec6  jz      short loc_180014EFE
0x180014ec8  mov     rax, qword ptr [rsp+38h+FileSize]
0x180014ecd  sub     rax, [rbx+8]
0x180014ed1  mov     [rbx+10h], rax
0x180014ed5  jmp     loc_180014DF6
0x180014eda  mov     eax, 80070008h
0x180014edf  jmp     short loc_180014E81
0x180014ee1  lea     rcx, [rbp+3E8h]
0x180014ee8  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180014eee  cmp     rax, rdi
0x180014ef1  mov     ecx, 1
0x180014ef6  cmovnz  esi, ecx
0x180014ef9  jmp     loc_180014E08
0x180014efe  call    cs:__imp_GetLastError
0x180014f04  test    eax, eax
0x180014f06  jle     loc_180014E81
0x180014f0c  movzx   eax, ax
0x180014f0f  or      eax, 80070000h
0x180014f14  jmp     loc_180014E81
0x180014f19  mov     eax, 80070057h
0x180014f1e  jmp     loc_180014E90
0x180014f23  mov     eax, 80070216h
0x180014f28  jmp     loc_180014E90
0x180014f2d  movzx   esi, word ptr [rbp+250h]
0x180014f34  lea     rcx, [rbp+3E8h]
0x180014f3b  mov     rdi, [rbp+258h]
0x180014f42  shl     rsi, 5
0x180014f46  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180014f4c  mov     r8, rsi; Size
0x180014f4f  mov     rdx, rdi; Src
0x180014f52  mov     rcx, rax; void *
0x180014f55  call    memmove_0
0x180014f5a  jmp     loc_180014E37
0x180014f5f  mov     eax, esi
0x180014f61  mov     rsi, r15
0x180014f64  shl     rsi, 5
0x180014f68  cmp     eax, r15d
0x180014f6b  jbe     short loc_180014F84
0x180014f6d  sub     eax, r15d
0x180014f70  lea     rdx, [rdi+rsi]; Src
0x180014f74  mov     r8d, eax
0x180014f77  lea     rcx, [rdx+20h]; void *
0x180014f7b  shl     r8, 5; Size
0x180014f7f  call    memmove_0
0x180014f84  movups  xmm0, xmmword ptr [rbx]
0x180014f87  movups  xmmword ptr [rdi+rsi], xmm0
0x180014f8b  movups  xmm1, xmmword ptr [rbx+10h]
0x180014f8f  movups  xmmword ptr [rdi+rsi+10h], xmm1
0x180014f94  jmp     loc_180014E7F
```
