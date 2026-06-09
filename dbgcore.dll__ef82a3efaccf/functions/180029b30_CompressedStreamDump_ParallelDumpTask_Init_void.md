# CompressedStreamDump::ParallelDumpTask::Init(void)

- ea: `0x180029b30`
- end: `0x180029d62`
- name: `?Init@ParallelDumpTask@CompressedStreamDump@@AEAAXXZ`
- size: `562`
- prototype: `void __fastcall(CompressedStreamDump::ParallelDumpTask *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180029408`

## callees

- `0x180002200`
- `0x18000f34c`
- `0x18001f14c`
- `0x1800278e8`
- `0x1800289b8`
- `0x1800295f0`
- `0x180029b30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180029ba5`
- `api-ms-win-core-synch-l1-1-0!CreateEventA` at `0x180029ba5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029bba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029cfa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029bba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029cfa`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029bd5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029bd5`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180029c0d`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180029c4d`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180029c71`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180029c9a`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180029c0d`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180029c4d`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180029c71`
- `api-ms-win-core-memory-l1-1-0!VirtualFree` at `0x180029c9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029bc5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029bc5`

## string_xrefs

- `0x180029d00`: `onecore\sdktools\debuggers\minidump\paralleldumptask.cpp`
- `0x180029d14`: `CompressedStreamDump::ParallelDumpTask::Init`
- `0x180029d2f`: `ParallelDumpTask initialize failed!`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CompressedStreamDump::ParallelDumpTask::Init(CompressedStreamDump::ParallelDumpTask *this)
{
  unsigned __int64 v1; // r8
  __int64 v3; // r11
  unsigned __int64 v4; // rdx
  _QWORD *v5; // r9
  __int64 v6; // rcx
  HANDLE EventA; // rax
  void *v8; // rsi
  HANDLE v9; // rdi
  DWORD LastError; // ebp
  unsigned int v11; // r8d
  const char *v12; // r9
  char *Memory; // rax
  void *v14; // rcx
  unsigned int v15; // ecx
  unsigned int v16; // eax
  char *v17; // rax
  void *v18; // rcx
  char *v19; // rax
  void *v20; // rcx
  char *v21; // rax
  void *v22; // rcx
  __int64 *v23; // rax
  unsigned __int64 v24; // r9
  __int64 i; // rdx
  unsigned __int64 v26; // rax
  DWORD v27; // eax
  _BYTE pExceptionObject[72]; // [rsp+30h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v1 = *((_QWORD *)this + 22);
  if ( v1 )
  {
    v3 = *((_QWORD *)this + 21);
    v4 = 0;
    v5 = (_QWORD *)*((_QWORD *)this + 20);
    do
    {
      v6 = v3 + v4;
      if ( 0xCCCCCCCCCCCCCCCDuLL * ((__int64)(v5[1] - *v5) >> 3) <= v3 + v4 )
        std::vector<MemoryBucket *>::_Xrange(v6, v4, v1, v5);
      ++v4;
      *((_QWORD *)this + 23) += *(unsigned int *)(*v5 + 40 * v6 + 32);
    }
    while ( v4 < v1 );
  }
  EventA = CreateEventA(0, 1, 1, 0);
  v8 = (void *)*((_QWORD *)this + 29);
  v9 = EventA;
  if ( v8 )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v8) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v11, v12);
    SetLastError(LastError);
  }
  *((_QWORD *)this + 29) = v9;
  if ( !v9 )
  {
    v27 = GetLastError();
    CompressedStreamDump::LogMessage(
      (CompressedStreamDump *)4,
      (int)"m_hBucketIOEvent is invalid. GetLastError: %u. Function: %s, File: %s, Line: %d.\n",
      (const char *)v27,
      "CompressedStreamDump::ParallelDumpTask::Init",
      "onecore\\sdktools\\debuggers\\minidump\\paralleldumptask.cpp",
      78);
    std::exception::exception((std::exception *)pExceptionObject, "ParallelDumpTask initialize failed!");
    throw (std::exception *)pExceptionObject;
  }
  Memory = CompressedStreamDump::ParallelDumpTask::AllocateMemory(this, *((unsigned int *)this + 6));
  v14 = (void *)*((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = Memory;
  if ( v14 )
    VirtualFree(v14, 0, 0x8000u);
  v15 = *((_DWORD *)this + 6);
  if ( v15 <= 0x7E000000 )
    v16 = v15 / 0xFF + v15 + 16;
  else
    v16 = 0;
  v17 = CompressedStreamDump::ParallelDumpTask::AllocateMemory(this, v16);
  v18 = (void *)*((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = v17;
  if ( v18 )
    VirtualFree(v18, 0, 0x8000u);
  v19 = CompressedStreamDump::ParallelDumpTask::AllocateMemory(this, *((int *)this + 16));
  v20 = (void *)*((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = v19;
  if ( v20 )
    VirtualFree(v20, 0, 0x8000u);
  v21 = CompressedStreamDump::ParallelDumpTask::AllocateMemory(
          this,
          (unsigned int)(*((_DWORD *)this + 16) + *(_DWORD *)(*(_QWORD *)this + 40LL)));
  v22 = (void *)*((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = v21;
  if ( v22 )
    VirtualFree(v22, 0, 0x8000u);
  v23 = (__int64 *)*((_QWORD *)this + 20);
  v24 = 0;
  for ( i = *v23; i != v23[1]; i += 40 )
    v24 += *(unsigned int *)(i + 8);
  v26 = v24 / (unsigned int)(20 * *(_DWORD *)(*(_QWORD *)this + 12LL));
  if ( v26 < 0x100000 )
    v26 = 0x100000;
  *((_QWORD *)this + 41) = v26;
}

```

## disassembly

```asm
0x180029b30  push    rbx
0x180029b32  push    rbp
0x180029b33  push    rsi
0x180029b34  push    rdi
0x180029b35  sub     rsp, 58h
0x180029b39  mov     r8, [rcx+0B0h]
0x180029b40  mov     rbx, rcx
0x180029b43  test    r8, r8
0x180029b46  jz      short loc_180029B99
0x180029b48  mov     r11, [rcx+0A8h]
0x180029b4f  xor     edx, edx
0x180029b51  mov     r9, [rcx+0A0h]
0x180029b58  mov     r10, [r9]
0x180029b5b  lea     rcx, [r11+rdx]
0x180029b5f  mov     rax, [r9+8]
0x180029b63  mov     rdi, 0CCCCCCCCCCCCCCCDh
0x180029b6d  sub     rax, r10
0x180029b70  sar     rax, 3
0x180029b74  imul    rax, rdi
0x180029b78  cmp     rax, rcx
0x180029b7b  jbe     loc_180029CF4
0x180029b81  lea     rax, [rcx+rcx*4]
0x180029b85  inc     rdx
0x180029b88  mov     ecx, [r10+rax*8+20h]
0x180029b8d  add     [rbx+0B8h], rcx
0x180029b94  cmp     rdx, r8
0x180029b97  jb      short loc_180029B58
0x180029b99  xor     r9d, r9d; lpName
0x180029b9c  xor     ecx, ecx; lpEventAttributes
0x180029b9e  lea     edx, [r9+1]; bManualReset
0x180029ba2  mov     r8d, edx; bInitialState
0x180029ba5  call    cs:__imp_CreateEventA
0x180029bab  mov     rsi, [rbx+0E8h]
0x180029bb2  mov     rdi, rax
0x180029bb5  test    rsi, rsi
0x180029bb8  jz      short loc_180029BDB
0x180029bba  call    cs:__imp_GetLastError
0x180029bc0  mov     rcx, rsi; hObject
0x180029bc3  mov     ebp, eax
0x180029bc5  call    cs:__imp_CloseHandle
0x180029bcb  test    eax, eax
0x180029bcd  jz      loc_180029D52
0x180029bd3  mov     ecx, ebp; dwErrCode
0x180029bd5  call    cs:__imp_SetLastError
0x180029bdb  mov     [rbx+0E8h], rdi
0x180029be2  test    rdi, rdi
0x180029be5  jz      loc_180029CFA
0x180029beb  mov     edx, [rbx+18h]; unsigned __int64
0x180029bee  mov     rcx, rbx; this
0x180029bf1  call    ?AllocateMemory@ParallelDumpTask@CompressedStreamDump@@AEAAPEAD_K@Z; CompressedStreamDump::ParallelDumpTask::AllocateMemory(unsigned __int64)
0x180029bf6  mov     rcx, [rbx+20h]; lpAddress
0x180029bfa  mov     edi, 8000h
0x180029bff  mov     [rbx+20h], rax
0x180029c03  test    rcx, rcx
0x180029c06  jz      short loc_180029C13
0x180029c08  mov     r8d, edi; dwFreeType
0x180029c0b  xor     edx, edx; dwSize
0x180029c0d  call    cs:__imp_VirtualFree
0x180029c13  mov     ecx, [rbx+18h]
0x180029c16  cmp     ecx, 7E000000h
0x180029c1c  jbe     short loc_180029C22
0x180029c1e  xor     eax, eax
0x180029c20  jmp     short loc_180029C31
0x180029c22  mov     eax, 80808081h
0x180029c27  mul     ecx
0x180029c29  lea     eax, [rcx+10h]
0x180029c2c  shr     edx, 7
0x180029c2f  add     eax, edx
0x180029c31  mov     edx, eax; unsigned __int64
0x180029c33  mov     rcx, rbx; this
0x180029c36  call    ?AllocateMemory@ParallelDumpTask@CompressedStreamDump@@AEAAPEAD_K@Z; CompressedStreamDump::ParallelDumpTask::AllocateMemory(unsigned __int64)
0x180029c3b  mov     rcx, [rbx+28h]; lpAddress
0x180029c3f  mov     [rbx+28h], rax
0x180029c43  test    rcx, rcx
0x180029c46  jz      short loc_180029C53
0x180029c48  mov     r8d, edi; dwFreeType
0x180029c4b  xor     edx, edx; dwSize
0x180029c4d  call    cs:__imp_VirtualFree
0x180029c53  movsxd  rdx, dword ptr [rbx+40h]; unsigned __int64
0x180029c57  mov     rcx, rbx; this
0x180029c5a  call    ?AllocateMemory@ParallelDumpTask@CompressedStreamDump@@AEAAPEAD_K@Z; CompressedStreamDump::ParallelDumpTask::AllocateMemory(unsigned __int64)
0x180029c5f  mov     rcx, [rbx+38h]; lpAddress
0x180029c63  mov     [rbx+38h], rax
0x180029c67  test    rcx, rcx
0x180029c6a  jz      short loc_180029C77
0x180029c6c  mov     r8d, edi; dwFreeType
0x180029c6f  xor     edx, edx; dwSize
0x180029c71  call    cs:__imp_VirtualFree
0x180029c77  mov     rax, [rbx]
0x180029c7a  mov     rcx, rbx; this
0x180029c7d  mov     edx, [rax+28h]
0x180029c80  add     edx, [rbx+40h]; unsigned __int64
0x180029c83  call    ?AllocateMemory@ParallelDumpTask@CompressedStreamDump@@AEAAPEAD_K@Z; CompressedStreamDump::ParallelDumpTask::AllocateMemory(unsigned __int64)
0x180029c88  mov     rcx, [rbx+30h]; lpAddress
0x180029c8c  mov     [rbx+30h], rax
0x180029c90  test    rcx, rcx
0x180029c93  jz      short loc_180029CA0
0x180029c95  mov     r8d, edi; dwFreeType
0x180029c98  xor     edx, edx; dwSize
0x180029c9a  call    cs:__imp_VirtualFree
0x180029ca0  mov     rax, [rbx+0A0h]
0x180029ca7  xor     r9d, r9d
0x180029caa  mov     r8, [rax+8]
0x180029cae  mov     rdx, [rax]
0x180029cb1  jmp     short loc_180029CBD
0x180029cb3  mov     ecx, [rdx+8]
0x180029cb6  add     r9, rcx
0x180029cb9  add     rdx, 28h ; '('
0x180029cbd  cmp     rdx, r8
0x180029cc0  jnz     short loc_180029CB3
0x180029cc2  mov     rcx, [rbx]
0x180029cc5  mov     rax, r9
0x180029cc8  mov     edx, [rcx+0Ch]
0x180029ccb  mov     ecx, 100000h
0x180029cd0  lea     r8d, [rdx+rdx*4]
0x180029cd4  xor     edx, edx
0x180029cd6  shl     r8d, 2
0x180029cda  div     r8
0x180029cdd  cmp     rax, rcx
0x180029ce0  cmovb   rax, rcx
0x180029ce4  mov     [rbx+148h], rax
0x180029ceb  add     rsp, 58h
0x180029cef  pop     rdi
0x180029cf0  pop     rsi
0x180029cf1  pop     rbp
0x180029cf2  pop     rbx
0x180029cf3  retn
0x180029cf4  call    ?_Xrange@?$vector@PEAUMemoryBucket@@V?$allocator@PEAUMemoryBucket@@@std@@@std@@CAXXZ; std::vector<MemoryBucket *>::_Xrange(void)
0x180029cfa  call    cs:__imp_GetLastError
0x180029d00  lea     rcx, aOnecoreSdktool; "onecore\\sdktools\\debuggers\\minidump"...
0x180029d07  mov     [rsp+78h+var_50], 4Eh ; 'N'
0x180029d0f  mov     [rsp+78h+var_58], rcx
0x180029d14  lea     r9, aCompressedstre; "CompressedStreamDump::ParallelDumpTask:"...
0x180029d1b  mov     ecx, 4; this
0x180029d20  lea     rdx, aMHbucketioeven; "m_hBucketIOEvent is invalid. GetLastErr"...
0x180029d27  mov     r8d, eax; char *
0x180029d2a  call    ?LogMessage@CompressedStreamDump@@YAXHPEBDZZ; CompressedStreamDump::LogMessage(int,char const *,...)
0x180029d2f  lea     rdx, aParalleldumpta; "ParallelDumpTask initialize failed!"
0x180029d36  lea     rcx, [rsp+78h+pExceptionObject]; this
0x180029d3b  call    ??0exception@std@@QEAA@QEBD@Z; std::exception::exception(char const * const)
0x180029d40  lea     rdx, _TI1?AVexception@std@@; pThrowInfo
0x180029d47  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x180029d4c  call    _CxxThrowException_0
0x180029d52  mov     rcx, [rsp+78h]; this
0x180029d57  mov     edx, 0A0Bh; void *
0x180029d5c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
