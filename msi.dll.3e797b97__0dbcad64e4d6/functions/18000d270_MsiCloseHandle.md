# MsiCloseHandle

- ea: `0x18000d270`
- end: `0x18000d6d2`
- name: `MsiCloseHandle`
- size: `1122`
- prototype: `UINT __stdcall(MSIHANDLE hAny)`
- caller_count: `19`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x18000b8bc`
- `0x18000bb80`
- `0x1800294e0`
- `0x18002ea94`
- `0x18004ebbc`
- `0x18005a9a8`
- `0x18005acec`
- `0x18008d67c`
- `0x1800a7b14`
- `0x1801197c8`
- `0x18011eec0`
- `0x180131928`
- `0x180158c04`
- `0x18015bf40`
- `0x180193250`
- `0x180194200`
- `0x1801943e0`
- `0x1801a51f0`
- `0x1801d1d1c`

## callees

- `0x18000c4bc`
- `0x18000ca3c`
- `0x18000d270`
- `0x18000d6d8`
- `0x180078100`
- `0x1801cb450`
- `0x180266010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000d2eb`
- `KERNEL32!LeaveCriticalSection` at `0x18000d37a`
- `KERNEL32!LeaveCriticalSection` at `0x18000d430`
- `KERNEL32!LeaveCriticalSection` at `0x18000d486`
- `KERNEL32!LeaveCriticalSection` at `0x18000d6ab`
- `KERNEL32!LeaveCriticalSection` at `0x18000d2eb`
- `KERNEL32!LeaveCriticalSection` at `0x18000d37a`
- `KERNEL32!LeaveCriticalSection` at `0x18000d430`
- `KERNEL32!LeaveCriticalSection` at `0x18000d486`
- `KERNEL32!LeaveCriticalSection` at `0x18000d6ab`
- `KERNEL32!GetCurrentThreadId` at `0x18000d2ba`
- `KERNEL32!GetCurrentThreadId` at `0x18000d2ba`
- `KERNEL32!OutputDebugStringW` at `0x18000d4eb`
- `KERNEL32!OutputDebugStringW` at `0x18000d4eb`
- `KERNEL32!EnterCriticalSection` at `0x18000d296`
- `KERNEL32!EnterCriticalSection` at `0x18000d306`
- `KERNEL32!EnterCriticalSection` at `0x18000d3bc`
- `KERNEL32!EnterCriticalSection` at `0x18000d296`
- `KERNEL32!EnterCriticalSection` at `0x18000d306`
- `KERNEL32!EnterCriticalSection` at `0x18000d3bc`
- `KERNEL32!TlsGetValue` at `0x18000d4fc`
- `KERNEL32!TlsGetValue` at `0x18000d4fc`

## string_xrefs

- `0x18000d4e4`: `Failed to release Service\n`
- `0x18000d698`: `Improper MSIHANDLE closing. Trying to close MSIHANDLE (%d) of type %d for thread %d by custom action thread.`
- `0x18000d57e`: `Closing MSIHANDLE (%d) of type %d for thread %d`
- `0x18000d5f1`: `Passing to service: MsiCloseHandle(%d)`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
UINT __stdcall MsiCloseHandle(MSIHANDLE hAny)
{
  DWORD CurrentThreadId; // esi
  __int64 v3; // rbx
  struct CMsiHandle **j; // r14
  struct CMsiHandle *v5; // rdi
  char v6; // si
  __int64 v7; // rbx
  unsigned int i; // ecx
  __int64 *Value; // rax
  __int64 v11; // [rsp+A8h] [rbp+10h]

  if ( !g_pCustomActionContext )
  {
    EnterCriticalSection(&g_csThreadImpersonationLock);
    HIDWORD(v11) = -1;
    if ( g_dwThreadImpersonationSlot == -1
      || (Value = (__int64 *)TlsGetValue(g_dwThreadImpersonationSlot)) == 0
      || (v3 = *Value, v11 = *Value, (CurrentThreadId = *Value) == 0) )
    {
      CurrentThreadId = GetCurrentThreadId();
      LODWORD(v11) = CurrentThreadId;
      if ( g_fThreadImpersonationArray && g_scServerContext != 2 )
      {
        for ( i = 0; i < dword_1803101F8; ++i )
        {
          if ( *((_DWORD *)g_rgThreadIdImpersonate + 3 * i) == CurrentThreadId )
          {
            v3 = *(_QWORD *)((char *)g_rgThreadIdImpersonate + 12 * i + 4);
            HIDWORD(v11) = HIDWORD(v3);
            CurrentThreadId = v3;
            goto LABEL_5;
          }
        }
      }
      v3 = v11;
    }
LABEL_5:
    LeaveCriticalSection(&g_csThreadImpersonationLock);
    if ( hAny )
    {
      EnterCriticalSection(&CMsiHandle::m_csLock);
      for ( j = &CMsiHandle::m_Head; ; j = (struct CMsiHandle **)((char *)v5 + 16) )
      {
        v5 = *j;
        if ( !*j )
        {
          LeaveCriticalSection(&CMsiHandle::m_csLock);
          return 6;
        }
        if ( *(_DWORD *)v5 == hAny )
          break;
      }
      if ( __PAIR64__(HIDWORD(v11), CurrentThreadId) != *((_QWORD *)v5 + 3)
        && (g_pActionThreadHead && (unsigned __int8)FIsCustomActionThread(v3) || *((_DWORD *)v5 + 1) == 790535) )
      {
        if ( g_dmDiagnosticMode )
          DebugString(
            9,
            0,
            0,
            L"Improper MSIHANDLE closing. Trying to close MSIHANDLE (%d) of type %d for thread %d by custom action thread.",
            (const unsigned __int16 *)*(unsigned int *)v5,
            (const unsigned __int16 *)*((int *)v5 + 1),
            (const unsigned __int16 *)*((unsigned int *)v5 + 6),
            L"(NULL)",
            L"(NULL)",
            L"(NULL)",
            0,
            0);
        LeaveCriticalSection(&CMsiHandle::m_csLock);
        return 1444;
      }
      v6 = 0;
      if ( g_dmDiagnosticMode && (g_dwLogMode & 0x2000) != 0 )
        DebugString(
          5,
          0,
          0,
          L"Closing MSIHANDLE (%d) of type %d for thread %d",
          (const unsigned __int16 *)*(unsigned int *)v5,
          (const unsigned __int16 *)*((int *)v5 + 1),
          (const unsigned __int16 *)*((unsigned int *)v5 + 6),
          L"(NULL)",
          L"(NULL)",
          L"(NULL)",
          0,
          0);
      *j = (struct CMsiHandle *)*((_QWORD *)v5 + 2);
      v7 = *((_QWORD *)v5 + 1);
      if ( !CMsiHandle::m_Head )
      {
        v6 = 1;
        if ( qword_180314138 )
          ((void (__fastcall *)(struct IUnknown *))qword_180314138->lpVtbl->Release)(qword_180314138);
        qword_180314138 = 0;
        CMsiHandle::m_piHandleServices = 0;
      }
      LoadServices();
      LeaveCriticalSection(&CMsiHandle::m_csLock);
      if ( piMalloc )
        (*(void (__fastcall **)(struct IMsiMalloc *, struct CMsiHandle *))(*(_QWORD *)piMalloc + 40LL))(piMalloc, v5);
      if ( v7 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
      EnterCriticalSection(&g_csSharedServicesLock);
      if ( !--g_cSharedServices )
      {
        if ( g_piSharedDllsRegKey )
        {
          (*(void (__fastcall **)(struct IMsiRegKey *))(*(_QWORD *)g_piSharedDllsRegKey + 16LL))(g_piSharedDllsRegKey);
          g_piSharedDllsRegKey = 0;
        }
        if ( g_piSharedDllsRegKey32 )
        {
          (*(void (__fastcall **)(struct IMsiRegKey *))(*(_QWORD *)g_piSharedDllsRegKey32 + 16LL))(g_piSharedDllsRegKey32);
          g_piSharedDllsRegKey32 = 0;
        }
        (*(void (__fastcall **)(struct IMsiServices *))(*(_QWORD *)g_piSharedServices + 160LL))(g_piSharedServices);
        while ( (*(int (__fastcall **)(struct IMsiServices *))(*(_QWORD *)g_piSharedServices + 16LL))(g_piSharedServices) > 0 )
          OutputDebugStringW(L"Failed to release Service\r\n");
        g_piSharedServices = 0;
      }
      LeaveCriticalSection(&g_csSharedServicesLock);
      if ( v6 )
        FreeServices();
    }
    return 0;
  }
  if ( g_dmDiagnosticMode )
    DebugString(
      9,
      0,
      0,
      L"Passing to service: MsiCloseHandle(%d)",
      (const unsigned __int16 *)hAny,
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  return CMsiCustomAction::CloseHandle(*(CMsiCustomAction **)&hAny, hAny);
}

```

## disassembly

```asm
0x18000d270  push    rbx
0x18000d272  push    rbp
0x18000d273  push    rsi
0x18000d274  push    rdi
0x18000d275  push    r14
0x18000d277  push    r15
0x18000d279  sub     rsp, 68h
0x18000d27d  xor     r15d, r15d
0x18000d280  mov     ebp, ecx
0x18000d282  cmp     cs:?g_pCustomActionContext@@3PEAVCMsiCustomAction@@EA, r15; CMsiCustomAction * g_pCustomActionContext
0x18000d289  jnz     loc_18000D5C2
0x18000d28f  lea     rcx, ?g_csThreadImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d296  call    cs:__imp_EnterCriticalSection
0x18000d29d  nop     dword ptr [rax+rax+00h]
0x18000d2a2  mov     ecx, cs:?g_dwThreadImpersonationSlot@@3KA; dwTlsIndex
0x18000d2a8  or      eax, 0FFFFFFFFh
0x18000d2ab  mov     dword ptr [rsp+98h+arg_8+4], eax
0x18000d2b2  cmp     ecx, eax
0x18000d2b4  jnz     loc_18000D4FC
0x18000d2ba  call    cs:__imp_GetCurrentThreadId
0x18000d2c1  nop     dword ptr [rax+rax+00h]
0x18000d2c6  cmp     cs:?g_fThreadImpersonationArray@@3_NA, r15b; bool g_fThreadImpersonationArray
0x18000d2cd  mov     esi, eax
0x18000d2cf  mov     dword ptr [rsp+98h+arg_8], eax
0x18000d2d6  jnz     loc_18000D499
0x18000d2dc  mov     rbx, [rsp+98h+arg_8]
0x18000d2e4  lea     rcx, ?g_csThreadImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d2eb  call    cs:__imp_LeaveCriticalSection
0x18000d2f2  nop     dword ptr [rax+rax+00h]
0x18000d2f7  test    ebp, ebp
0x18000d2f9  jz      loc_18000D441
0x18000d2ff  lea     rcx, ?m_csLock@CMsiHandle@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d306  call    cs:__imp_EnterCriticalSection
0x18000d30d  nop     dword ptr [rax+rax+00h]
0x18000d312  lea     r14, ?m_Head@CMsiHandle@@0PEAV1@EA; CMsiHandle * CMsiHandle::m_Head
0x18000d319  mov     rdi, [r14]
0x18000d31c  test    rdi, rdi
0x18000d31f  jz      loc_18000D47F
0x18000d325  cmp     [rdi], ebp
0x18000d327  jnz     loc_18000D5D7
0x18000d32d  cmp     esi, [rdi+18h]
0x18000d330  jnz     loc_18000D62C
0x18000d336  mov     eax, [rdi+1Ch]
0x18000d339  cmp     dword ptr [rsp+98h+arg_8+4], eax
0x18000d340  jnz     loc_18000D62C
0x18000d346  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x18000d34d  mov     sil, r15b
0x18000d350  jnz     loc_18000D560
0x18000d356  mov     rax, [rdi+10h]
0x18000d35a  mov     [r14], rax
0x18000d35d  cmp     cs:?m_Head@CMsiHandle@@0PEAV1@EA, r15; CMsiHandle * CMsiHandle::m_Head
0x18000d364  mov     rbx, [rdi+8]
0x18000d368  jz      loc_18000D452
0x18000d36e  call    ?LoadServices@@YAPEAVIMsiServices@@XZ; LoadServices(void)
0x18000d373  lea     rcx, ?m_csLock@CMsiHandle@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d37a  call    cs:__imp_LeaveCriticalSection
0x18000d381  nop     dword ptr [rax+rax+00h]
0x18000d386  mov     rcx, cs:?piMalloc@@3PEAVIMsiMalloc@@EA; IMsiMalloc * piMalloc
0x18000d38d  test    rcx, rcx
0x18000d390  jz      short loc_18000D3A1
0x18000d392  mov     rax, [rcx]
0x18000d395  mov     rdx, rdi
0x18000d398  mov     rax, [rax+28h]
0x18000d39c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3a1  test    rbx, rbx
0x18000d3a4  jz      short loc_18000D3B5
0x18000d3a6  mov     rax, [rbx]
0x18000d3a9  mov     rcx, rbx
0x18000d3ac  mov     rax, [rax+10h]
0x18000d3b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3b5  lea     rcx, ?g_csSharedServicesLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d3bc  call    cs:__imp_EnterCriticalSection
0x18000d3c3  nop     dword ptr [rax+rax+00h]
0x18000d3c8  sub     cs:?g_cSharedServices@@3HA, 1; int g_cSharedServices
0x18000d3cf  jnz     short loc_18000D429
0x18000d3d1  mov     rcx, cs:?g_piSharedDllsRegKey@@3PEAVIMsiRegKey@@EA; IMsiRegKey * g_piSharedDllsRegKey
0x18000d3d8  test    rcx, rcx
0x18000d3db  jnz     loc_18000D530
0x18000d3e1  mov     rcx, cs:?g_piSharedDllsRegKey32@@3PEAVIMsiRegKey@@EA; IMsiRegKey * g_piSharedDllsRegKey32
0x18000d3e8  test    rcx, rcx
0x18000d3eb  jnz     loc_18000D548
0x18000d3f1  mov     rcx, cs:?g_piSharedServices@@3PEAVIMsiServices@@EA; IMsiServices * g_piSharedServices
0x18000d3f8  mov     rax, [rcx]
0x18000d3fb  mov     rax, [rax+0A0h]
0x18000d402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d407  mov     rcx, cs:?g_piSharedServices@@3PEAVIMsiServices@@EA; IMsiServices * g_piSharedServices
0x18000d40e  mov     rax, [rcx]
0x18000d411  mov     rax, [rax+10h]
0x18000d415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d41a  test    eax, eax
0x18000d41c  jg      loc_18000D4E4
0x18000d422  mov     cs:?g_piSharedServices@@3PEAVIMsiServices@@EA, r15; IMsiServices * g_piSharedServices
0x18000d429  lea     rcx, ?g_csSharedServicesLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d430  call    cs:__imp_LeaveCriticalSection
0x18000d437  nop     dword ptr [rax+rax+00h]
0x18000d43c  test    sil, sil
0x18000d43f  jnz     short loc_18000D478
0x18000d441  mov     eax, r15d
0x18000d444  add     rsp, 68h
0x18000d448  pop     r15
0x18000d44a  pop     r14
0x18000d44c  pop     rdi
0x18000d44d  pop     rsi
0x18000d44e  pop     rbp
0x18000d44f  pop     rbx
0x18000d450  retn
0x18000d452  mov     rcx, cs:qword_180314138
0x18000d459  mov     sil, 1
0x18000d45c  test    rcx, rcx
0x18000d45f  jnz     loc_18000D6C1
0x18000d465  mov     cs:qword_180314138, r15
0x18000d46c  mov     cs:?m_piHandleServices@CMsiHandle@@0PEAVIMsiServices@@EA, r15; IMsiServices * CMsiHandle::m_piHandleServices
0x18000d473  jmp     loc_18000D36E
0x18000d478  call    ?FreeServices@@YAHXZ; FreeServices(void)
0x18000d47d  jmp     short loc_18000D441
0x18000d47f  lea     rcx, ?m_csLock@CMsiHandle@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d486  call    cs:__imp_LeaveCriticalSection
0x18000d48d  nop     dword ptr [rax+rax+00h]
0x18000d492  mov     eax, 6
0x18000d497  jmp     short loc_18000D444
0x18000d499  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x18000d4a0  jz      loc_18000D2DC
0x18000d4a6  mov     rdx, cs:?g_rgThreadIdImpersonate@@3V?$CAPITempBuffer@UThreadIdImpersonate@@$04@@A; CAPITempBuffer<ThreadIdImpersonate,5> g_rgThreadIdImpersonate
0x18000d4ad  mov     ecx, r15d
0x18000d4b0  cmp     ecx, cs:dword_1803101F8
0x18000d4b6  jnb     loc_18000D2DC
0x18000d4bc  mov     eax, ecx
0x18000d4be  lea     rbx, [rax+rax*2]
0x18000d4c2  cmp     [rdx+rbx*4], esi
0x18000d4c5  jnz     loc_18000D625
0x18000d4cb  mov     rbx, [rdx+rbx*4+4]
0x18000d4d0  mov     [rsp+98h+arg_8], rbx
0x18000d4d8  mov     esi, dword ptr [rsp+98h+arg_8]
0x18000d4df  jmp     loc_18000D2E4
0x18000d4e4  lea     rcx, aFailedToReleas; "Failed to release Service\r\n"
0x18000d4eb  call    cs:__imp_OutputDebugStringW
0x18000d4f2  nop     dword ptr [rax+rax+00h]
0x18000d4f7  jmp     loc_18000D407
0x18000d4fc  call    cs:__imp_TlsGetValue
0x18000d503  nop     dword ptr [rax+rax+00h]
0x18000d508  test    rax, rax
0x18000d50b  jz      loc_18000D2BA
0x18000d511  mov     rbx, [rax]
0x18000d514  mov     [rsp+98h+arg_8], rbx
0x18000d51c  mov     esi, dword ptr [rsp+98h+arg_8]
0x18000d523  test    esi, esi
0x18000d525  jz      loc_18000D2BA
0x18000d52b  jmp     loc_18000D2E4
0x18000d530  mov     rax, [rcx]
0x18000d533  mov     rax, [rax+10h]
0x18000d537  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d53c  mov     cs:?g_piSharedDllsRegKey@@3PEAVIMsiRegKey@@EA, r15; IMsiRegKey * g_piSharedDllsRegKey
0x18000d543  jmp     loc_18000D3E1
0x18000d548  mov     rax, [rcx]
0x18000d54b  mov     rax, [rax+10h]
0x18000d54f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d554  mov     cs:?g_piSharedDllsRegKey32@@3PEAVIMsiRegKey@@EA, r15; IMsiRegKey * g_piSharedDllsRegKey32
0x18000d55b  jmp     loc_18000D3F1
0x18000d560  test    cs:?g_dwLogMode@@3KA, 2000h; ulong g_dwLogMode
0x18000d56a  jz      loc_18000D356
0x18000d570  movsxd  rcx, dword ptr [rdi+4]
0x18000d574  lea     r10, aNull; "(NULL)"
0x18000d57b  mov     r8d, [rdi]
0x18000d57e  lea     r9, aClosingMsihand; "Closing MSIHANDLE (%d) of type %d for t"...
0x18000d585  mov     eax, [rdi+18h]
0x18000d588  xor     edx, edx; unsigned __int16
0x18000d58a  mov     [rsp+98h+var_40], r15; void *
0x18000d58f  mov     [rsp+98h+var_48], r15d; unsigned int
0x18000d594  mov     [rsp+98h+var_50], r10; unsigned __int16 *
0x18000d599  mov     [rsp+98h+var_58], r10; unsigned __int16 *
0x18000d59e  mov     [rsp+98h+var_60], r10; unsigned __int16 *
0x18000d5a3  mov     [rsp+98h+var_68], rax; unsigned __int16 *
0x18000d5a8  mov     [rsp+98h+var_70], rcx; unsigned __int16 *
0x18000d5ad  lea     ecx, [rdx+5]; int
0x18000d5b0  mov     [rsp+98h+var_78], r8; unsigned __int16 *
0x18000d5b5  xor     r8d, r8d; int
0x18000d5b8  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18000d5bd  jmp     loc_18000D356
0x18000d5c2  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x18000d5c9  jnz     short loc_18000D5E0
0x18000d5cb  mov     edx, ebp; unsigned int
0x18000d5cd  call    ?CloseHandle@CMsiCustomAction@@QEAAJK@Z; CMsiCustomAction::CloseHandle(ulong)
0x18000d5d2  jmp     loc_18000D444
0x18000d5d7  lea     r14, [rdi+10h]
0x18000d5db  jmp     loc_18000D319
0x18000d5e0  mov     [rsp+98h+var_40], r15; void *
0x18000d5e5  lea     r10, aNull; "(NULL)"
0x18000d5ec  mov     [rsp+98h+var_48], r15d; unsigned int
0x18000d5f1  lea     r9, aPassingToServi_11; "Passing to service: MsiCloseHandle(%d)"
0x18000d5f8  mov     [rsp+98h+var_50], r10; unsigned __int16 *
0x18000d5fd  xor     edx, edx; unsigned __int16
0x18000d5ff  mov     [rsp+98h+var_58], r10; unsigned __int16 *
0x18000d604  xor     r8d, r8d; int
0x18000d607  mov     [rsp+98h+var_60], r10; unsigned __int16 *
0x18000d60c  mov     [rsp+98h+var_68], r10; unsigned __int16 *
0x18000d611  mov     [rsp+98h+var_70], r10; unsigned __int16 *
0x18000d616  lea     ecx, [rdx+9]; int
0x18000d619  mov     [rsp+98h+var_78], rbp; unsigned __int16 *
0x18000d61e  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18000d623  jmp     short loc_18000D5CB
0x18000d625  inc     ecx
0x18000d627  jmp     loc_18000D4B0
0x18000d62c  cmp     cs:?g_pActionThreadHead@@3PEAVCActionThreadData@@EA, r15; CActionThreadData * g_pActionThreadHead
0x18000d633  jz      short loc_18000D641
0x18000d635  mov     rcx, rbx
0x18000d638  call    ?FIsCustomActionThread@@YA_NUUniqueThreadID@@@Z; FIsCustomActionThread(UniqueThreadID)
0x18000d63d  test    al, al
0x18000d63f  jnz     short loc_18000D64E
0x18000d641  cmp     dword ptr [rdi+4], 0C1007h
0x18000d648  jnz     loc_18000D346
0x18000d64e  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x18000d655  jz      short loc_18000D6A4
0x18000d657  movsxd  r8, dword ptr [rdi+4]
0x18000d65b  lea     r10, aNull; "(NULL)"
0x18000d662  mov     r9d, [rdi]
0x18000d665  xor     edx, edx; unsigned __int16
0x18000d667  mov     eax, [rdi+18h]
0x18000d66a  mov     [rsp+98h+var_40], r15; void *
0x18000d66f  mov     [rsp+98h+var_48], r15d; unsigned int
0x18000d674  mov     [rsp+98h+var_50], r10; unsigned __int16 *
0x18000d679  lea     ecx, [rdx+9]; int
0x18000d67c  mov     [rsp+98h+var_58], r10; unsigned __int16 *
0x18000d681  mov     [rsp+98h+var_60], r10; unsigned __int16 *
0x18000d686  mov     [rsp+98h+var_68], rax; unsigned __int16 *
0x18000d68b  mov     [rsp+98h+var_70], r8; unsigned __int16 *
0x18000d690  xor     r8d, r8d; int
0x18000d693  mov     [rsp+98h+var_78], r9; unsigned __int16 *
0x18000d698  lea     r9, aImproperMsihan; "Improper MSIHANDLE closing. Trying to c"...
0x18000d69f  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18000d6a4  lea     rcx, ?m_csLock@CMsiHandle@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d6ab  call    cs:__imp_LeaveCriticalSection
0x18000d6b2  nop     dword ptr [rax+rax+00h]
0x18000d6b7  mov     eax, 5A4h
0x18000d6bc  jmp     loc_18000D444
0x18000d6c1  mov     rax, [rcx]
0x18000d6c4  mov     rax, [rax+10h]
0x18000d6c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6cd  jmp     loc_18000D465
```
