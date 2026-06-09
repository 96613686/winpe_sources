# W3_RESPONSE::WriteEntityChunkByReference(_HTTP_DATA_CHUNK *,long)

- ea: `0x180015fd0`
- end: `0x1800161de`
- name: `?WriteEntityChunkByReference@W3_RESPONSE@@QEAAJPEAU_HTTP_DATA_CHUNK@@J@Z`
- size: `526`
- prototype: `signed int __fastcall(W3_RESPONSE *this, struct _HTTP_DATA_CHUNK *, int)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180004710`
- `0x180005030`
- `0x180024b80`
- `0x180028614`
- `0x180028974`

## callees

- `0x180015fd0`
- `0x18003772e`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016137`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016137`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800160eb`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800160eb`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180016075`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001611b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180016185`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180016075`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001611b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180016185`
- `iisutil!?Resize@BUFFER@@QEAA_NKK@Z` at `0x180016041`
- `iisutil!?Resize@BUFFER@@QEAA_NKK@Z` at `0x180016041`

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
0x180015fd0  push    rbx
0x180015fd2  push    rbp
0x180015fd3  push    r15
0x180015fd5  sub     rsp, 20h
0x180015fd9  movsxd  r15, r8d
0x180015fdc  mov     rbx, rdx
0x180015fdf  mov     rbp, rcx
0x180015fe2  test    rdx, rdx
0x180015fe5  jz      loc_180016158
0x180015feb  movzx   ecx, word ptr [rcx+250h]
0x180015ff2  lea     eax, [rcx+1]
0x180015ff5  cmp     ax, cx
0x180015ff8  jb      loc_180016162
0x180015ffe  cmp     dword ptr [rdx], 1
0x180016001  mov     [rsp+38h+arg_0], rsi
0x180016006  mov     [rsp+38h+arg_10], rdi
0x18001600b  mov     [rsp+38h+arg_18], r14
0x180016010  jz      loc_1800160C6
0x180016016  mov     rdi, [rbp+258h]
0x18001601d  xor     esi, esi
0x18001601f  test    rdi, rdi
0x180016022  jnz     loc_180016114
0x180016028  movzx   edx, word ptr [rbp+250h]
0x18001602f  lea     rcx, [rbp+3E8h]
0x180016036  inc     edx
0x180016038  mov     r8d, 200h
0x18001603e  shl     edx, 5
0x180016041  call    cs:__imp_?Resize@BUFFER@@QEAA_NKK@Z; BUFFER::Resize(ulong,ulong)
0x180016048  nop     dword ptr [rax+rax+00h]
0x18001604d  test    al, al
0x18001604f  jz      loc_18001610D
0x180016055  test    esi, esi
0x180016057  jnz     loc_18001616C
0x18001605d  movzx   esi, word ptr [rbp+250h]
0x180016064  lea     rcx, [rbp+3E8h]
0x18001606b  lea     eax, [rsi+1]
0x18001606e  mov     [rbp+250h], ax
0x180016075  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001607c  nop     dword ptr [rax+rax+00h]
0x180016081  mov     [rbp+258h], rax
0x180016088  mov     rdi, rax
0x18001608b  cmp     r15d, 0FFFFFFFFh
0x18001608f  jnz     loc_1800161A4
0x180016095  movups  xmm0, xmmword ptr [rbx]
0x180016098  mov     ecx, esi
0x18001609a  shl     rcx, 5
0x18001609e  movups  xmmword ptr [rcx+rax], xmm0
0x1800160a2  movups  xmm1, xmmword ptr [rbx+10h]
0x1800160a6  movups  xmmword ptr [rcx+rax+10h], xmm1
0x1800160ab  xor     eax, eax
0x1800160ad  mov     rdi, [rsp+38h+arg_10]
0x1800160b2  mov     rsi, [rsp+38h+arg_0]
0x1800160b7  mov     r14, [rsp+38h+arg_18]
0x1800160bc  add     rsp, 20h
0x1800160c0  pop     r15
0x1800160c2  pop     rbp
0x1800160c3  pop     rbx
0x1800160c4  retn
0x1800160c6  mov     rax, [rdx+10h]
0x1800160ca  test    rax, rax
0x1800160cd  jz      short loc_1800160AB
0x1800160cf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800160d3  jnz     loc_180016016
0x1800160d9  mov     rcx, [rbx+18h]; hFile
0x1800160dd  lea     rdx, [rsp+38h+FileSize]; lpFileSize
0x1800160e2  mov     qword ptr [rsp+38h+FileSize], 0
0x1800160eb  call    cs:__imp_GetFileSizeEx
0x1800160f2  nop     dword ptr [rax+rax+00h]
0x1800160f7  test    eax, eax
0x1800160f9  jz      short loc_180016137
0x1800160fb  mov     rax, qword ptr [rsp+38h+FileSize]
0x180016100  sub     rax, [rbx+8]
0x180016104  mov     [rbx+10h], rax
0x180016108  jmp     loc_180016016
0x18001610d  mov     eax, 80070008h
0x180016112  jmp     short loc_1800160AD
0x180016114  lea     rcx, [rbp+3E8h]
0x18001611b  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180016122  nop     dword ptr [rax+rax+00h]
0x180016127  cmp     rax, rdi
0x18001612a  mov     ecx, 1
0x18001612f  cmovnz  esi, ecx
0x180016132  jmp     loc_180016028
0x180016137  call    cs:__imp_GetLastError
0x18001613e  nop     dword ptr [rax+rax+00h]
0x180016143  test    eax, eax
0x180016145  jle     loc_1800160AD
0x18001614b  movzx   eax, ax
0x18001614e  or      eax, 80070000h
0x180016153  jmp     loc_1800160AD
0x180016158  mov     eax, 80070057h
0x18001615d  jmp     loc_1800160BC
0x180016162  mov     eax, 80070216h
0x180016167  jmp     loc_1800160BC
0x18001616c  movzx   esi, word ptr [rbp+250h]
0x180016173  lea     rcx, [rbp+3E8h]
0x18001617a  mov     rdi, [rbp+258h]
0x180016181  shl     rsi, 5
0x180016185  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001618c  nop     dword ptr [rax+rax+00h]
0x180016191  mov     r8, rsi; Size
0x180016194  mov     rdx, rdi; Src
0x180016197  mov     rcx, rax; void *
0x18001619a  call    memmove_0
0x18001619f  jmp     loc_18001605D
0x1800161a4  mov     eax, esi
0x1800161a6  mov     rsi, r15
0x1800161a9  shl     rsi, 5
0x1800161ad  cmp     eax, r15d
0x1800161b0  jbe     short loc_1800161C9
0x1800161b2  sub     eax, r15d
0x1800161b5  lea     rdx, [rdi+rsi]; Src
0x1800161b9  mov     r8d, eax
0x1800161bc  lea     rcx, [rdx+20h]; void *
0x1800161c0  shl     r8, 5; Size
0x1800161c4  call    memmove_0
0x1800161c9  movups  xmm0, xmmword ptr [rbx]
0x1800161cc  movups  xmmword ptr [rdi+rsi], xmm0
0x1800161d0  movups  xmm1, xmmword ptr [rbx+10h]
0x1800161d4  movups  xmmword ptr [rdi+rsi+10h], xmm1
0x1800161d9  jmp     loc_1800160AB
```
