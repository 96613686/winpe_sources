# W3_RESPONSE::WriteEntityChunkNoFlush(_HTTP_DATA_CHUNK *)

- ea: `0x1800265b8`
- end: `0x1800267e6`
- name: `?WriteEntityChunkNoFlush@W3_RESPONSE@@QEAAJPEAU_HTTP_DATA_CHUNK@@@Z`
- size: `558`
- prototype: `__int64 __fastcall(W3_RESPONSE *__hidden this, struct _HTTP_DATA_CHUNK *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180024388`
- `0x1800268d0`

## callees

- `0x180014db0`
- `0x1800265b8`
- `0x180034382`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180026658`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180026665`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180026658`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180026665`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180026690`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180026690`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026715`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026715`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002669a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002669a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002673d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002673d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800267d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800267d0`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800266e4`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002677e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800266e4`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002677e`
- `iisutil!?Resize@BUFFER@@QEAA_NKK@Z` at `0x1800266d7`
- `iisutil!?Resize@BUFFER@@QEAA_NKK@Z` at `0x180026771`
- `iisutil!?Resize@BUFFER@@QEAA_NKK@Z` at `0x1800266d7`
- `iisutil!?Resize@BUFFER@@QEAA_NKK@Z` at `0x180026771`

## pseudocode

```c
signed int __fastcall W3_RESPONSE::WriteEntityChunkNoFlush(W3_RESPONSE *this, struct _HTTP_DATA_CHUNK *a2)
{
  HTTP_DATA_CHUNK_TYPE DataChunkType; // r8d
  __int32 v5; // r8d
  int FragmentNameLength; // edx
  __int64 v7; // rcx
  void *v8; // rax
  signed int result; // eax
  HANDLE CurrentProcess; // rax
  HANDLE FileHandle; // rdi
  void *v12; // rbx
  HANDLE v13; // rax
  HANDLE v14; // rdi
  struct _HTTP_DATA_CHUNK lpMem; // [rsp+40h] [rbp-20h] BYREF

  DataChunkType = a2->DataChunkType;
  memset(&lpMem, 0, sizeof(lpMem));
  lpMem.DataChunkType = DataChunkType;
  if ( DataChunkType == HttpDataChunkFromMemory )
  {
    if ( a2->FromMemory.BufferLength )
    {
      lpMem.FromMemory.BufferLength = a2->FromMemory.BufferLength;
      lpMem.FromFileHandle.ByteRange.StartingOffset.QuadPart = (ULONGLONG)HeapAlloc(
                                                                            W3_RESPONSE::sm_hResponseBufferHeap,
                                                                            0,
                                                                            lpMem.FromMemory.BufferLength);
      if ( lpMem.FromFileHandle.ByteRange.StartingOffset.QuadPart )
      {
        if ( BUFFER::Resize((W3_RESPONSE *)((char *)this + 1440), 8 * *((_DWORD *)this + 384) + 8, 0x80u) )
        {
          *((_QWORD *)BUFFER::QueryPtr((W3_RESPONSE *)((char *)this + 1440)) + *((unsigned int *)this + 384)) = lpMem.FromMemory.pBuffer;
          ++*((_DWORD *)this + 384);
          memcpy_0(lpMem.FromMemory.pBuffer, a2->FromMemory.pBuffer, lpMem.FromMemory.BufferLength);
          *((_DWORD *)this + 386) += lpMem.FromMemory.BufferLength;
          return W3_RESPONSE::WriteEntityChunkByReference(this, &lpMem, -1);
        }
        HeapFree(W3_RESPONSE::sm_hResponseBufferHeap, 0, lpMem.FromMemory.pBuffer);
      }
      return -2147024888;
    }
    return 0;
  }
  v5 = DataChunkType - 1;
  if ( v5 )
  {
    if ( v5 != 1 )
      return W3_RESPONSE::WriteEntityChunkByReference(this, &lpMem, -1);
    FragmentNameLength = a2->FromFragmentCache.FragmentNameLength;
    v7 = *((_QWORD *)this + 6);
    lpMem.FromFragmentCache.FragmentNameLength = FragmentNameLength;
    v8 = (void *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v7 + 144LL))(
                   v7,
                   (unsigned int)(FragmentNameLength + 2));
    lpMem.FromFileHandle.ByteRange.Length.QuadPart = (ULONGLONG)v8;
    if ( v8 )
    {
      memcpy_0(v8, a2->FromFragmentCache.pFragmentName, (unsigned int)lpMem.FromFragmentCache.FragmentNameLength + 2);
      return W3_RESPONSE::WriteEntityChunkByReference(this, &lpMem, -1);
    }
    return -2147024888;
  }
  if ( !a2->FromFileHandle.ByteRange.Length.QuadPart )
    return 0;
  if ( a2->FromFileHandle.FileHandle == (HANDLE)-1LL )
    return -2147024890;
  CurrentProcess = GetCurrentProcess();
  FileHandle = a2->FromFileHandle.FileHandle;
  v12 = CurrentProcess;
  v13 = GetCurrentProcess();
  if ( DuplicateHandle(v13, FileHandle, v12, &lpMem.FromFileHandle.FileHandle, 0, 0, 2u) )
  {
    v14 = lpMem.FromFileHandle.FileHandle;
    if ( BUFFER::Resize((W3_RESPONSE *)((char *)this + 1488), 8 * *((_DWORD *)this + 385) + 8, 0x80u) )
    {
      *((_QWORD *)BUFFER::QueryPtr((W3_RESPONSE *)((char *)this + 1488)) + *((unsigned int *)this + 385)) = v14;
      ++*((_DWORD *)this + 385);
      lpMem.FromMemory = a2->FromMemory;
      return W3_RESPONSE::WriteEntityChunkByReference(this, &lpMem, -1);
    }
    CloseHandle(lpMem.FromFileHandle.FileHandle);
    return -2147024888;
  }
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800265b8  push    rbp
0x1800265ba  push    rbx
0x1800265bb  push    rsi
0x1800265bc  push    rdi
0x1800265bd  push    r14
0x1800265bf  mov     rbp, rsp
0x1800265c2  sub     rsp, 60h
0x1800265c6  mov     r8d, [rdx]
0x1800265c9  xorps   xmm0, xmm0
0x1800265cc  mov     rsi, rdx
0x1800265cf  mov     r14, rcx
0x1800265d2  movups  xmmword ptr [rbp+lpMem], xmm0
0x1800265d6  mov     dword ptr [rbp+lpMem], r8d
0x1800265da  movups  xmmword ptr [rbp+TargetHandle], xmm0
0x1800265de  test    r8d, r8d
0x1800265e1  jz      loc_180026720
0x1800265e7  sub     r8d, 1
0x1800265eb  jz      short loc_18002663C
0x1800265ed  cmp     r8d, 1
0x1800265f1  jnz     loc_1800267B1
0x1800265f7  movzx   edx, word ptr [rdx+8]
0x1800265fb  mov     rcx, [rcx+30h]
0x1800265ff  mov     word ptr [rbp+lpMem+8], dx
0x180026603  add     edx, 2
0x180026606  mov     rax, [rcx]
0x180026609  mov     rax, [rax+90h]
0x180026610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026615  mov     [rbp+TargetHandle], rax
0x180026619  test    rax, rax
0x18002661c  jz      loc_1800267D6
0x180026622  movzx   r8d, word ptr [rbp+lpMem+8]
0x180026627  mov     rcx, rax; void *
0x18002662a  mov     rdx, [rsi+10h]; Src
0x18002662e  add     r8d, 2; Size
0x180026632  call    memcpy_0
0x180026637  jmp     loc_1800267B1
0x18002663c  cmp     qword ptr [rdx+10h], 0
0x180026641  jz      loc_180026727
0x180026647  cmp     qword ptr [rdx+18h], 0FFFFFFFFFFFFFFFFh
0x18002664c  jnz     short loc_180026658
0x18002664e  mov     eax, 80070006h
0x180026653  jmp     loc_1800267DB
0x180026658  call    cs:__imp_GetCurrentProcess
0x18002665e  mov     rdi, [rsi+18h]
0x180026662  mov     rbx, rax
0x180026665  call    cs:__imp_GetCurrentProcess
0x18002666b  mov     [rsp+60h+dwOptions], 2; dwOptions
0x180026673  lea     r9, [rbp+TargetHandle+8]; lpTargetHandle
0x180026677  mov     rcx, rax; hSourceProcessHandle
0x18002667a  mov     [rsp+60h+bInheritHandle], 0; bInheritHandle
0x180026682  mov     r8, rbx; hTargetProcessHandle
0x180026685  mov     [rsp+60h+dwDesiredAccess], 0; dwDesiredAccess
0x18002668d  mov     rdx, rdi; hSourceHandle
0x180026690  call    cs:__imp_DuplicateHandle
0x180026696  test    eax, eax
0x180026698  jnz     short loc_1800266B5
0x18002669a  call    cs:__imp_GetLastError
0x1800266a0  test    eax, eax
0x1800266a2  jle     loc_1800267DB
0x1800266a8  movzx   eax, ax
0x1800266ab  or      eax, 80070000h
0x1800266b0  jmp     loc_1800267DB
0x1800266b5  mov     edx, [r14+604h]
0x1800266bc  lea     rbx, [r14+5D0h]
0x1800266c3  mov     rdi, [rbp+TargetHandle+8]
0x1800266c7  mov     r8d, 80h
0x1800266cd  mov     rcx, rbx
0x1800266d0  lea     edx, ds:8[rdx*8]
0x1800266d7  call    cs:__imp_?Resize@BUFFER@@QEAA_NKK@Z; BUFFER::Resize(ulong,ulong)
0x1800266dd  test    al, al
0x1800266df  jz      short loc_180026711
0x1800266e1  mov     rcx, rbx
0x1800266e4  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800266ea  mov     ecx, [r14+604h]
0x1800266f1  mov     [rax+rcx*8], rdi
0x1800266f5  inc     dword ptr [r14+604h]
0x1800266fc  mov     rax, [rsi+8]
0x180026700  mov     [rbp+lpMem+8], rax
0x180026704  mov     rax, [rsi+10h]
0x180026708  mov     [rbp+TargetHandle], rax
0x18002670c  jmp     loc_1800267B1
0x180026711  mov     rcx, [rbp+TargetHandle+8]; hObject
0x180026715  call    cs:__imp_CloseHandle
0x18002671b  jmp     loc_1800267D6
0x180026720  mov     eax, [rdx+10h]
0x180026723  test    eax, eax
0x180026725  jnz     short loc_18002672E
0x180026727  xor     eax, eax
0x180026729  jmp     loc_1800267DB
0x18002672e  mov     rcx, cs:?sm_hResponseBufferHeap@W3_RESPONSE@@0PEAXEA; hHeap
0x180026735  mov     r8, rax; dwBytes
0x180026738  xor     edx, edx; dwFlags
0x18002673a  mov     dword ptr [rbp+TargetHandle], eax
0x18002673d  call    cs:__imp_HeapAlloc
0x180026743  mov     [rbp+lpMem+8], rax
0x180026747  mov     rbx, rax
0x18002674a  test    rax, rax
0x18002674d  jz      loc_1800267D6
0x180026753  mov     edx, [r14+600h]
0x18002675a  lea     rdi, [r14+5A0h]
0x180026761  mov     r8d, 80h
0x180026767  mov     rcx, rdi
0x18002676a  lea     edx, ds:8[rdx*8]
0x180026771  call    cs:__imp_?Resize@BUFFER@@QEAA_NKK@Z; BUFFER::Resize(ulong,ulong)
0x180026777  test    al, al
0x180026779  jz      short loc_1800267C3
0x18002677b  mov     rcx, rdi
0x18002677e  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180026784  mov     ecx, [r14+600h]
0x18002678b  mov     [rax+rcx*8], rbx
0x18002678f  inc     dword ptr [r14+600h]
0x180026796  mov     rdx, [rsi+8]; Src
0x18002679a  mov     r8d, dword ptr [rbp+TargetHandle]; Size
0x18002679e  mov     rcx, [rbp+lpMem+8]; void *
0x1800267a2  call    memcpy_0
0x1800267a7  mov     eax, dword ptr [rbp+TargetHandle]
0x1800267aa  add     [r14+608h], eax
0x1800267b1  or      r8d, 0FFFFFFFFh; int
0x1800267b5  lea     rdx, [rbp+lpMem]; struct _HTTP_DATA_CHUNK *
0x1800267b9  mov     rcx, r14; this
0x1800267bc  call    ?WriteEntityChunkByReference@W3_RESPONSE@@QEAAJPEAU_HTTP_DATA_CHUNK@@J@Z; W3_RESPONSE::WriteEntityChunkByReference(_HTTP_DATA_CHUNK *,long)
0x1800267c1  jmp     short loc_1800267DB
0x1800267c3  mov     r8, [rbp+lpMem+8]; lpMem
0x1800267c7  xor     edx, edx; dwFlags
0x1800267c9  mov     rcx, cs:?sm_hResponseBufferHeap@W3_RESPONSE@@0PEAXEA; hHeap
0x1800267d0  call    cs:__imp_HeapFree
0x1800267d6  mov     eax, 80070008h
0x1800267db  add     rsp, 60h
0x1800267df  pop     r14
0x1800267e1  pop     rdi
0x1800267e2  pop     rsi
0x1800267e3  pop     rbx
0x1800267e4  pop     rbp
0x1800267e5  retn
```
