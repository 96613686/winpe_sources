# CRepository::LockRepository(void)

- ea: `0x18003b450`
- end: `0x18003b622`
- name: `?LockRepository@CRepository@@UEAAJXZ`
- size: `466`
- prototype: `__int64 __fastcall(CRepository *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800012b8`
- `0x1800013a0`
- `0x18001ad80`
- `0x18001d258`
- `0x180038e10`
- `0x18003b450`
- `0x18003e598`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x18003b4a8`
- `wbemcomn!GetMemLogObject` at `0x18003b580`
- `wbemcomn!GetMemLogObject` at `0x18003b5bc`
- `wbemcomn!GetMemLogObject` at `0x18003b4a8`
- `wbemcomn!GetMemLogObject` at `0x18003b580`
- `wbemcomn!GetMemLogObject` at `0x18003b5bc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003b4b8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003b590`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003b5cc`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003b4b8`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003b590`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x18003b5cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b530`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b530`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x18003b553`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCaptureStackBackTrace` at `0x18003b553`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CRepository::LockRepository(CRepository *this)
{
  unsigned int v1; // ebx
  CMemoryLog *v2; // rax
  CLock *v3; // rcx
  CMemoryLog *v4; // rax
  CVarObjHeap *v5; // rcx
  __int64 v6; // rdx
  CMemoryLog *MemLogObject; // rax
  char v9[8]; // [rsp+20h] [rbp-28h] BYREF
  __int128 *v10; // [rsp+28h] [rbp-20h]
  __int64 (__fastcall *v11)(CLock *__hidden); // [rsp+30h] [rbp-18h]
  ULONG BackTraceHash; // [rsp+58h] [rbp+10h] BYREF

  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids);
  }
  v1 = 0;
  if ( !(unsigned int)CLock::WriteLock((HANDLE *)&g_readWriteLock) )
  {
    v9[0] = 0;
    v10 = &g_readWriteLock;
    v11 = CLock::WriteUnlock;
    if ( g_bShuttingDown )
    {
      v1 = -2147217357;
LABEL_25:
      ObjScopeGuardImpl0<CLock,int (CLock::*)(void)>::~ObjScopeGuardImpl0<CLock,int (CLock::*)(void)>(v9);
      return v1;
    }
    _InterlockedIncrement(&g_NumTimes);
    LODWORD(g_Backup) = GetCurrentThreadId();
    BackTraceHash = 0;
    RtlCaptureStackBackTrace(0, 0xBu, &BackTrace, &BackTraceHash);
    dword_180058950 = 0;
    if ( !dword_180058AFC || CPageSource::Checkpoint((CPageSource *)qword_180058B00) )
    {
      MemLogObject = GetMemLogObject();
      v1 = -2147217407;
      CMemoryLog::Write(MemLogObject, -2147217407);
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_25;
      }
      v6 = 82;
    }
    else
    {
      if ( !(unsigned int)CLock::DowngradeLock(v3) )
      {
        v9[0] = 1;
        goto LABEL_25;
      }
      v4 = GetMemLogObject();
      v1 = -2147217407;
      CMemoryLog::Write(v4, -2147217407);
      v5 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CVarObjHeap *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_25;
      }
      v6 = 83;
    }
    WPP_SF_d(*((_QWORD *)v5 + 2), v6, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids, 2147749889LL);
    goto LABEL_25;
  }
  v2 = GetMemLogObject();
  v1 = -2147217407;
  CMemoryLog::Write(v2, -2147217407);
  if ( WPP_GLOBAL_Control != (CVarObjHeap *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 81, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids, 2147749889LL);
  }
  return v1;
}

```

## disassembly

```asm
0x18003b450  mov     [rsp+arg_0], rbx
0x18003b455  mov     [rsp+arg_10], rbp
0x18003b45a  push    rdi
0x18003b45b  sub     rsp, 40h
0x18003b45f  lea     rdi, WPP_GLOBAL_Control
0x18003b466  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b46d  cmp     rcx, rdi
0x18003b470  jz      short loc_18003B493
0x18003b472  test    byte ptr [rcx+1Ch], 1
0x18003b476  jz      short loc_18003B493
0x18003b478  cmp     byte ptr [rcx+19h], 5
0x18003b47c  jb      short loc_18003B493
0x18003b47e  mov     edx, 50h ; 'P'
0x18003b483  lea     r8, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids
0x18003b48a  mov     rcx, [rcx+10h]
0x18003b48e  call    WPP_SF_
0x18003b493  lea     rbp, ?g_readWriteLock@@3VCLock@@A; CLock g_readWriteLock
0x18003b49a  mov     rcx, rbp; this
0x18003b49d  call    ?WriteLock@CLock@@QEAAHK@Z; CLock::WriteLock(ulong)
0x18003b4a2  xor     ebx, ebx
0x18003b4a4  test    eax, eax
0x18003b4a6  jz      short loc_18003B502
0x18003b4a8  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003b4ae  mov     ebx, 80041001h
0x18003b4b3  mov     edx, ebx
0x18003b4b5  mov     rcx, rax
0x18003b4b8  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003b4be  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b4c5  cmp     rcx, rdi
0x18003b4c8  jz      loc_18003B610
0x18003b4ce  test    byte ptr [rcx+1Ch], 1
0x18003b4d2  jz      loc_18003B610
0x18003b4d8  cmp     byte ptr [rcx+19h], 2
0x18003b4dc  jb      loc_18003B610
0x18003b4e2  mov     edx, 51h ; 'Q'
0x18003b4e7  mov     r9d, 80041001h
0x18003b4ed  lea     r8, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids
0x18003b4f4  mov     rcx, [rcx+10h]
0x18003b4f8  call    WPP_SF_d
0x18003b4fd  jmp     loc_18003B610
0x18003b502  mov     [rsp+48h+var_28], bl
0x18003b506  mov     [rsp+48h+var_20], rbp
0x18003b50b  lea     rax, ?WriteUnlock@CLock@@QEAAHXZ; CLock::WriteUnlock(void)
0x18003b512  mov     [rsp+48h+var_18], rax
0x18003b517  cmp     cs:?g_bShuttingDown@@3_NA, bl; bool g_bShuttingDown
0x18003b51d  jz      short loc_18003B529
0x18003b51f  mov     ebx, 80041033h
0x18003b524  jmp     loc_18003B606
0x18003b529  lock inc cs:?g_NumTimes@@3JA; long g_NumTimes
0x18003b530  call    cs:__imp_GetCurrentThreadId
0x18003b536  mov     cs:?g_Backup@@3PAUBackUpTraces@@A, eax; BackUpTraces near * g_Backup
0x18003b53c  mov     [rsp+48h+BackTraceHash], ebx
0x18003b540  lea     r9, [rsp+48h+BackTraceHash]; BackTraceHash
0x18003b545  lea     r8, BackTrace; BackTrace
0x18003b54c  mov     edx, 0Bh; FramesToCapture
0x18003b551  xor     ecx, ecx; FramesToSkip
0x18003b553  call    cs:__imp_RtlCaptureStackBackTrace
0x18003b559  mov     cs:dword_180058950, ebx
0x18003b55f  cmp     cs:dword_180058AFC, ebx
0x18003b565  jz      short loc_18003B5BC
0x18003b567  lea     rcx, qword_180058B00; this
0x18003b56e  call    ?Checkpoint@CPageSource@@QEAAK_N@Z; CPageSource::Checkpoint(bool)
0x18003b573  test    eax, eax
0x18003b575  jnz     short loc_18003B5BC
0x18003b577  call    ?DowngradeLock@CLock@@QEAAHXZ; CLock::DowngradeLock(void)
0x18003b57c  test    eax, eax
0x18003b57e  jz      short loc_18003B5B5
0x18003b580  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003b586  mov     ebx, 80041001h
0x18003b58b  mov     edx, ebx
0x18003b58d  mov     rcx, rax
0x18003b590  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003b596  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b59d  cmp     rcx, rdi
0x18003b5a0  jz      short loc_18003B606
0x18003b5a2  test    byte ptr [rcx+1Ch], 1
0x18003b5a6  jz      short loc_18003B606
0x18003b5a8  cmp     byte ptr [rcx+19h], 2
0x18003b5ac  jb      short loc_18003B606
0x18003b5ae  mov     edx, 53h ; 'S'
0x18003b5b3  jmp     short loc_18003B5EF
0x18003b5b5  mov     [rsp+48h+var_28], 1
0x18003b5ba  jmp     short loc_18003B606
0x18003b5bc  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x18003b5c2  mov     ebx, 80041001h
0x18003b5c7  mov     edx, ebx
0x18003b5c9  mov     rcx, rax
0x18003b5cc  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x18003b5d2  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b5d9  cmp     rcx, rdi
0x18003b5dc  jz      short loc_18003B606
0x18003b5de  test    byte ptr [rcx+1Ch], 1
0x18003b5e2  jz      short loc_18003B606
0x18003b5e4  cmp     byte ptr [rcx+19h], 2
0x18003b5e8  jb      short loc_18003B606
0x18003b5ea  mov     edx, 52h ; 'R'
0x18003b5ef  mov     r9d, 80041001h
0x18003b5f5  lea     r8, WPP_53e1474670223052d7bc731b72ed24d6_Traceguids
0x18003b5fc  mov     rcx, [rcx+10h]
0x18003b600  call    WPP_SF_d
0x18003b605  nop
0x18003b606  lea     rcx, [rsp+48h+var_28]
0x18003b60b  call    ??1?$ObjScopeGuardImpl0@VCLock@@P81@EAAHXZ@@QEAA@XZ; ObjScopeGuardImpl0<CLock,int (CLock::*)(void)>::~ObjScopeGuardImpl0<CLock,int (CLock::*)(void)>(void)
0x18003b610  mov     eax, ebx
0x18003b612  mov     rbx, [rsp+48h+arg_0]
0x18003b617  mov     rbp, [rsp+48h+arg_10]
0x18003b61c  add     rsp, 40h
0x18003b620  pop     rdi
0x18003b621  retn
```
