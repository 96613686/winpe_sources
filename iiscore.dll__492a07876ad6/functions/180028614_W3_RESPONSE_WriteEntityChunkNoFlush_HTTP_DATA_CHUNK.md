# W3_RESPONSE::WriteEntityChunkNoFlush(_HTTP_DATA_CHUNK *)

- ea: `0x180028614`
- end: `0x180028885`
- name: `?WriteEntityChunkNoFlush@W3_RESPONSE@@QEAAJPEAU_HTTP_DATA_CHUNK@@@Z`
- size: `625`
- prototype: `signed int __fastcall(W3_RESPONSE *this, struct _HTTP_DATA_CHUNK *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180026228`
- `0x180028974`

## callees

- `0x180015fd0`
- `0x180028614`
- `0x180037722`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800286b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800286c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800286b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800286c7`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800286f8`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800286f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028795`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028795`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028708`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028708`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800287c3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800287c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028868`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180028868`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002875e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180028810`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18002875e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180028810`
- `iisutil!?Resize@BUFFER@@QEAA_NKK@Z` at `0x18002874b`
- `iisutil!?Resize@BUFFER@@QEAA_NKK@Z` at `0x1800287fd`
- `iisutil!?Resize@BUFFER@@QEAA_NKK@Z` at `0x18002874b`
- `iisutil!?Resize@BUFFER@@QEAA_NKK@Z` at `0x1800287fd`

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
0x180028614  push    rbp
0x180028616  push    rbx
0x180028617  push    rsi
0x180028618  push    rdi
0x180028619  push    r14
0x18002861b  mov     rbp, rsp
0x18002861e  sub     rsp, 60h
0x180028622  mov     r8d, [rdx]
0x180028625  xorps   xmm0, xmm0
0x180028628  mov     rsi, rdx
0x18002862b  mov     r14, rcx
0x18002862e  movups  xmmword ptr [rbp+lpMem], xmm0
0x180028632  mov     dword ptr [rbp+lpMem], r8d
0x180028636  movups  xmmword ptr [rbp+TargetHandle], xmm0
0x18002863a  test    r8d, r8d
0x18002863d  jz      loc_1800287A6
0x180028643  sub     r8d, 1
0x180028647  jz      short loc_180028698
0x180028649  cmp     r8d, 1
0x18002864d  jnz     loc_180028849
0x180028653  movzx   edx, word ptr [rdx+8]
0x180028657  mov     rcx, [rcx+30h]
0x18002865b  mov     word ptr [rbp+lpMem+8], dx
0x18002865f  add     edx, 2
0x180028662  mov     rax, [rcx]
0x180028665  mov     rax, [rax+90h]
0x18002866c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028671  mov     [rbp+TargetHandle], rax
0x180028675  test    rax, rax
0x180028678  jz      loc_180028874
0x18002867e  movzx   r8d, word ptr [rbp+lpMem+8]
0x180028683  mov     rcx, rax; void *
0x180028686  mov     rdx, [rsi+10h]; Src
0x18002868a  add     r8d, 2; Size
0x18002868e  call    memcpy_0
0x180028693  jmp     loc_180028849
0x180028698  cmp     qword ptr [rdx+10h], 0
0x18002869d  jz      loc_1800287AD
0x1800286a3  cmp     qword ptr [rdx+18h], 0FFFFFFFFFFFFFFFFh
0x1800286a8  jnz     short loc_1800286B4
0x1800286aa  mov     eax, 80070006h
0x1800286af  jmp     loc_180028879
0x1800286b4  call    cs:__imp_GetCurrentProcess
0x1800286bb  nop     dword ptr [rax+rax+00h]
0x1800286c0  mov     rdi, [rsi+18h]
0x1800286c4  mov     rbx, rax
0x1800286c7  call    cs:__imp_GetCurrentProcess
0x1800286ce  nop     dword ptr [rax+rax+00h]
0x1800286d3  mov     [rsp+60h+dwOptions], 2; dwOptions
0x1800286db  lea     r9, [rbp+TargetHandle+8]; lpTargetHandle
0x1800286df  mov     rcx, rax; hSourceProcessHandle
0x1800286e2  mov     [rsp+60h+bInheritHandle], 0; bInheritHandle
0x1800286ea  mov     r8, rbx; hTargetProcessHandle
0x1800286ed  mov     [rsp+60h+dwDesiredAccess], 0; dwDesiredAccess
0x1800286f5  mov     rdx, rdi; hSourceHandle
0x1800286f8  call    cs:__imp_DuplicateHandle
0x1800286ff  nop     dword ptr [rax+rax+00h]
0x180028704  test    eax, eax
0x180028706  jnz     short loc_180028729
0x180028708  call    cs:__imp_GetLastError
0x18002870f  nop     dword ptr [rax+rax+00h]
0x180028714  test    eax, eax
0x180028716  jle     loc_180028879
0x18002871c  movzx   eax, ax
0x18002871f  or      eax, 80070000h
0x180028724  jmp     loc_180028879
0x180028729  mov     edx, [r14+604h]
0x180028730  lea     rbx, [r14+5D0h]
0x180028737  mov     rdi, [rbp+TargetHandle+8]
0x18002873b  mov     r8d, 80h
0x180028741  mov     rcx, rbx
0x180028744  lea     edx, ds:8[rdx*8]
0x18002874b  call    cs:__imp_?Resize@BUFFER@@QEAA_NKK@Z; BUFFER::Resize(ulong,ulong)
0x180028752  nop     dword ptr [rax+rax+00h]
0x180028757  test    al, al
0x180028759  jz      short loc_180028791
0x18002875b  mov     rcx, rbx
0x18002875e  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180028765  nop     dword ptr [rax+rax+00h]
0x18002876a  mov     ecx, [r14+604h]
0x180028771  mov     [rax+rcx*8], rdi
0x180028775  inc     dword ptr [r14+604h]
0x18002877c  mov     rax, [rsi+8]
0x180028780  mov     [rbp+lpMem+8], rax
0x180028784  mov     rax, [rsi+10h]
0x180028788  mov     [rbp+TargetHandle], rax
0x18002878c  jmp     loc_180028849
0x180028791  mov     rcx, [rbp+TargetHandle+8]; hObject
0x180028795  call    cs:__imp_CloseHandle
0x18002879c  nop     dword ptr [rax+rax+00h]
0x1800287a1  jmp     loc_180028874
0x1800287a6  mov     eax, [rdx+10h]
0x1800287a9  test    eax, eax
0x1800287ab  jnz     short loc_1800287B4
0x1800287ad  xor     eax, eax
0x1800287af  jmp     loc_180028879
0x1800287b4  mov     rcx, cs:?sm_hResponseBufferHeap@W3_RESPONSE@@0PEAXEA; hHeap
0x1800287bb  mov     r8, rax; dwBytes
0x1800287be  xor     edx, edx; dwFlags
0x1800287c0  mov     dword ptr [rbp+TargetHandle], eax
0x1800287c3  call    cs:__imp_HeapAlloc
0x1800287ca  nop     dword ptr [rax+rax+00h]
0x1800287cf  mov     [rbp+lpMem+8], rax
0x1800287d3  mov     rbx, rax
0x1800287d6  test    rax, rax
0x1800287d9  jz      loc_180028874
0x1800287df  mov     edx, [r14+600h]
0x1800287e6  lea     rdi, [r14+5A0h]
0x1800287ed  mov     r8d, 80h
0x1800287f3  mov     rcx, rdi
0x1800287f6  lea     edx, ds:8[rdx*8]
0x1800287fd  call    cs:__imp_?Resize@BUFFER@@QEAA_NKK@Z; BUFFER::Resize(ulong,ulong)
0x180028804  nop     dword ptr [rax+rax+00h]
0x180028809  test    al, al
0x18002880b  jz      short loc_18002885B
0x18002880d  mov     rcx, rdi
0x180028810  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180028817  nop     dword ptr [rax+rax+00h]
0x18002881c  mov     ecx, [r14+600h]
0x180028823  mov     [rax+rcx*8], rbx
0x180028827  inc     dword ptr [r14+600h]
0x18002882e  mov     rdx, [rsi+8]; Src
0x180028832  mov     r8d, dword ptr [rbp+TargetHandle]; Size
0x180028836  mov     rcx, [rbp+lpMem+8]; void *
0x18002883a  call    memcpy_0
0x18002883f  mov     eax, dword ptr [rbp+TargetHandle]
0x180028842  add     [r14+608h], eax
0x180028849  or      r8d, 0FFFFFFFFh; int
0x18002884d  lea     rdx, [rbp+lpMem]; struct _HTTP_DATA_CHUNK *
0x180028851  mov     rcx, r14; this
0x180028854  call    ?WriteEntityChunkByReference@W3_RESPONSE@@QEAAJPEAU_HTTP_DATA_CHUNK@@J@Z; W3_RESPONSE::WriteEntityChunkByReference(_HTTP_DATA_CHUNK *,long)
0x180028859  jmp     short loc_180028879
0x18002885b  mov     r8, [rbp+lpMem+8]; lpMem
0x18002885f  xor     edx, edx; dwFlags
0x180028861  mov     rcx, cs:?sm_hResponseBufferHeap@W3_RESPONSE@@0PEAXEA; hHeap
0x180028868  call    cs:__imp_HeapFree
0x18002886f  nop     dword ptr [rax+rax+00h]
0x180028874  mov     eax, 80070008h
0x180028879  add     rsp, 60h
0x18002887d  pop     r14
0x18002887f  pop     rdi
0x180028880  pop     rsi
0x180028881  pop     rbx
0x180028882  pop     rbp
0x180028883  retn
```
