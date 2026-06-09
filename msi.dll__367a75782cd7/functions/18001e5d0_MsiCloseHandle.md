# MsiCloseHandle

- ea: `0x18001e5d0`
- end: `0x18001e9ef`
- name: `MsiCloseHandle`
- size: `1055`
- prototype: `UINT __stdcall(MSIHANDLE hAny)`
- caller_count: `19`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, service_task, installer_update`

## callers

- `0x1800437b8`
- `0x1800598c0`
- `0x18005a210`
- `0x18005a51c`
- `0x1800659c0`
- `0x18009d810`
- `0x18009f870`
- `0x1800b3a04`
- `0x180111040`
- `0x18011105c`
- `0x180117e10`
- `0x18012c5c4`
- `0x1801532b4`
- `0x1801564c0`
- `0x18018cb60`
- `0x18018da20`
- `0x18018dbf0`
- `0x18019e210`
- `0x1801c94a0`

## callees

- `0x18001de18`
- `0x18001e5d0`
- `0x18001e9f8`
- `0x180025a18`
- `0x180058af0`
- `0x1801c2d84`
- `0x18025c010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001e63f`
- `KERNEL32!LeaveCriticalSection` at `0x18001e6c2`
- `KERNEL32!LeaveCriticalSection` at `0x18001e76c`
- `KERNEL32!LeaveCriticalSection` at `0x18001e7bb`
- `KERNEL32!LeaveCriticalSection` at `0x18001e9ce`
- `KERNEL32!LeaveCriticalSection` at `0x18001e63f`
- `KERNEL32!LeaveCriticalSection` at `0x18001e6c2`
- `KERNEL32!LeaveCriticalSection` at `0x18001e76c`
- `KERNEL32!LeaveCriticalSection` at `0x18001e7bb`
- `KERNEL32!LeaveCriticalSection` at `0x18001e9ce`
- `KERNEL32!GetCurrentThreadId` at `0x18001e614`
- `KERNEL32!GetCurrentThreadId` at `0x18001e614`
- `KERNEL32!OutputDebugStringW` at `0x18001e81a`
- `KERNEL32!OutputDebugStringW` at `0x18001e81a`
- `KERNEL32!EnterCriticalSection` at `0x18001e5f6`
- `KERNEL32!EnterCriticalSection` at `0x18001e654`
- `KERNEL32!EnterCriticalSection` at `0x18001e6fe`
- `KERNEL32!EnterCriticalSection` at `0x18001e5f6`
- `KERNEL32!EnterCriticalSection` at `0x18001e654`
- `KERNEL32!EnterCriticalSection` at `0x18001e6fe`
- `KERNEL32!TlsGetValue` at `0x18001e825`
- `KERNEL32!TlsGetValue` at `0x18001e825`

## string_xrefs

- `0x18001e813`: `Failed to release Service\n`
- `0x18001e9bb`: `Improper MSIHANDLE closing. Trying to close MSIHANDLE (%d) of type %d for thread %d by custom action thread.`
- `0x18001e8a1`: `Closing MSIHANDLE (%d) of type %d for thread %d`
- `0x18001e914`: `Passing to service: MsiCloseHandle(%d)`

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
        for ( i = 0; i < dword_1803061F8; ++i )
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
        if ( qword_18030A188 )
          ((void (__fastcall *)(struct IUnknown *))qword_18030A188->lpVtbl->Release)(qword_18030A188);
        qword_18030A188 = 0;
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
0x18001e5d0  push    rbx
0x18001e5d2  push    rbp
0x18001e5d3  push    rsi
0x18001e5d4  push    rdi
0x18001e5d5  push    r14
0x18001e5d7  push    r15
0x18001e5d9  sub     rsp, 68h
0x18001e5dd  xor     r15d, r15d
0x18001e5e0  mov     ebp, ecx
0x18001e5e2  cmp     cs:?g_pCustomActionContext@@3PEAVCMsiCustomAction@@EA, r15; CMsiCustomAction * g_pCustomActionContext
0x18001e5e9  jnz     loc_18001E8E5
0x18001e5ef  lea     rcx, ?g_csThreadImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001e5f6  call    cs:__imp_EnterCriticalSection
0x18001e5fc  mov     ecx, cs:?g_dwThreadImpersonationSlot@@3KA; dwTlsIndex
0x18001e602  or      eax, 0FFFFFFFFh
0x18001e605  mov     dword ptr [rsp+98h+arg_8+4], eax
0x18001e60c  cmp     ecx, eax
0x18001e60e  jnz     loc_18001E825
0x18001e614  call    cs:__imp_GetCurrentThreadId
0x18001e61a  cmp     cs:?g_fThreadImpersonationArray@@3_NA, r15b; bool g_fThreadImpersonationArray
0x18001e621  mov     esi, eax
0x18001e623  mov     dword ptr [rsp+98h+arg_8], eax
0x18001e62a  jnz     loc_18001E7C8
0x18001e630  mov     rbx, [rsp+98h+arg_8]
0x18001e638  lea     rcx, ?g_csThreadImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001e63f  call    cs:__imp_LeaveCriticalSection
0x18001e645  test    ebp, ebp
0x18001e647  jz      loc_18001E777
0x18001e64d  lea     rcx, ?m_csLock@CMsiHandle@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001e654  call    cs:__imp_EnterCriticalSection
0x18001e65a  lea     r14, ?m_Head@CMsiHandle@@0PEAV1@EA; CMsiHandle * CMsiHandle::m_Head
0x18001e661  mov     rdi, [r14]
0x18001e664  test    rdi, rdi
0x18001e667  jz      loc_18001E7B4
0x18001e66d  cmp     [rdi], ebp
0x18001e66f  jnz     loc_18001E8FA
0x18001e675  cmp     esi, [rdi+18h]
0x18001e678  jnz     loc_18001E94F
0x18001e67e  mov     eax, [rdi+1Ch]
0x18001e681  cmp     dword ptr [rsp+98h+arg_8+4], eax
0x18001e688  jnz     loc_18001E94F
0x18001e68e  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x18001e695  mov     sil, r15b
0x18001e698  jnz     loc_18001E883
0x18001e69e  mov     rax, [rdi+10h]
0x18001e6a2  mov     [r14], rax
0x18001e6a5  cmp     cs:?m_Head@CMsiHandle@@0PEAV1@EA, r15; CMsiHandle * CMsiHandle::m_Head
0x18001e6ac  mov     rbx, [rdi+8]
0x18001e6b0  jz      loc_18001E787
0x18001e6b6  call    ?LoadServices@@YAPEAVIMsiServices@@XZ; LoadServices(void)
0x18001e6bb  lea     rcx, ?m_csLock@CMsiHandle@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001e6c2  call    cs:__imp_LeaveCriticalSection
0x18001e6c8  mov     rcx, cs:?piMalloc@@3PEAVIMsiMalloc@@EA; IMsiMalloc * piMalloc
0x18001e6cf  test    rcx, rcx
0x18001e6d2  jz      short loc_18001E6E3
0x18001e6d4  mov     rax, [rcx]
0x18001e6d7  mov     rdx, rdi
0x18001e6da  mov     rax, [rax+28h]
0x18001e6de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6e3  test    rbx, rbx
0x18001e6e6  jz      short loc_18001E6F7
0x18001e6e8  mov     rax, [rbx]
0x18001e6eb  mov     rcx, rbx
0x18001e6ee  mov     rax, [rax+10h]
0x18001e6f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6f7  lea     rcx, ?g_csSharedServicesLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001e6fe  call    cs:__imp_EnterCriticalSection
0x18001e704  sub     cs:?g_cSharedServices@@3HA, 1; int g_cSharedServices
0x18001e70b  jnz     short loc_18001E765
0x18001e70d  mov     rcx, cs:?g_piSharedDllsRegKey@@3PEAVIMsiRegKey@@EA; IMsiRegKey * g_piSharedDllsRegKey
0x18001e714  test    rcx, rcx
0x18001e717  jnz     loc_18001E853
0x18001e71d  mov     rcx, cs:?g_piSharedDllsRegKey32@@3PEAVIMsiRegKey@@EA; IMsiRegKey * g_piSharedDllsRegKey32
0x18001e724  test    rcx, rcx
0x18001e727  jnz     loc_18001E86B
0x18001e72d  mov     rcx, cs:?g_piSharedServices@@3PEAVIMsiServices@@EA; IMsiServices * g_piSharedServices
0x18001e734  mov     rax, [rcx]
0x18001e737  mov     rax, [rax+0A0h]
0x18001e73e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e743  mov     rcx, cs:?g_piSharedServices@@3PEAVIMsiServices@@EA; IMsiServices * g_piSharedServices
0x18001e74a  mov     rax, [rcx]
0x18001e74d  mov     rax, [rax+10h]
0x18001e751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e756  test    eax, eax
0x18001e758  jg      loc_18001E813
0x18001e75e  mov     cs:?g_piSharedServices@@3PEAVIMsiServices@@EA, r15; IMsiServices * g_piSharedServices
0x18001e765  lea     rcx, ?g_csSharedServicesLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001e76c  call    cs:__imp_LeaveCriticalSection
0x18001e772  test    sil, sil
0x18001e775  jnz     short loc_18001E7AD
0x18001e777  mov     eax, r15d
0x18001e77a  add     rsp, 68h
0x18001e77e  pop     r15
0x18001e780  pop     r14
0x18001e782  pop     rdi
0x18001e783  pop     rsi
0x18001e784  pop     rbp
0x18001e785  pop     rbx
0x18001e786  retn
0x18001e787  mov     rcx, cs:qword_18030A188
0x18001e78e  mov     sil, 1
0x18001e791  test    rcx, rcx
0x18001e794  jnz     loc_18001E9DE
0x18001e79a  mov     cs:qword_18030A188, r15
0x18001e7a1  mov     cs:?m_piHandleServices@CMsiHandle@@0PEAVIMsiServices@@EA, r15; IMsiServices * CMsiHandle::m_piHandleServices
0x18001e7a8  jmp     loc_18001E6B6
0x18001e7ad  call    ?FreeServices@@YAHXZ; FreeServices(void)
0x18001e7b2  jmp     short loc_18001E777
0x18001e7b4  lea     rcx, ?m_csLock@CMsiHandle@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001e7bb  call    cs:__imp_LeaveCriticalSection
0x18001e7c1  mov     eax, 6
0x18001e7c6  jmp     short loc_18001E77A
0x18001e7c8  cmp     cs:?g_scServerContext@@3W4scEnum@@A, 2; scEnum g_scServerContext
0x18001e7cf  jz      loc_18001E630
0x18001e7d5  mov     rdx, cs:?g_rgThreadIdImpersonate@@3V?$CAPITempBuffer@UThreadIdImpersonate@@$04@@A; CAPITempBuffer<ThreadIdImpersonate,5> g_rgThreadIdImpersonate
0x18001e7dc  mov     ecx, r15d
0x18001e7df  cmp     ecx, cs:dword_1803061F8
0x18001e7e5  jnb     loc_18001E630
0x18001e7eb  mov     eax, ecx
0x18001e7ed  lea     rbx, [rax+rax*2]
0x18001e7f1  cmp     [rdx+rbx*4], esi
0x18001e7f4  jnz     loc_18001E948
0x18001e7fa  mov     rbx, [rdx+rbx*4+4]
0x18001e7ff  mov     [rsp+98h+arg_8], rbx
0x18001e807  mov     esi, dword ptr [rsp+98h+arg_8]
0x18001e80e  jmp     loc_18001E638
0x18001e813  lea     rcx, aFailedToReleas; "Failed to release Service\r\n"
0x18001e81a  call    cs:__imp_OutputDebugStringW
0x18001e820  jmp     loc_18001E743
0x18001e825  call    cs:__imp_TlsGetValue
0x18001e82b  test    rax, rax
0x18001e82e  jz      loc_18001E614
0x18001e834  mov     rbx, [rax]
0x18001e837  mov     [rsp+98h+arg_8], rbx
0x18001e83f  mov     esi, dword ptr [rsp+98h+arg_8]
0x18001e846  test    esi, esi
0x18001e848  jz      loc_18001E614
0x18001e84e  jmp     loc_18001E638
0x18001e853  mov     rax, [rcx]
0x18001e856  mov     rax, [rax+10h]
0x18001e85a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e85f  mov     cs:?g_piSharedDllsRegKey@@3PEAVIMsiRegKey@@EA, r15; IMsiRegKey * g_piSharedDllsRegKey
0x18001e866  jmp     loc_18001E71D
0x18001e86b  mov     rax, [rcx]
0x18001e86e  mov     rax, [rax+10h]
0x18001e872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e877  mov     cs:?g_piSharedDllsRegKey32@@3PEAVIMsiRegKey@@EA, r15; IMsiRegKey * g_piSharedDllsRegKey32
0x18001e87e  jmp     loc_18001E72D
0x18001e883  test    cs:?g_dwLogMode@@3KA, 2000h; ulong g_dwLogMode
0x18001e88d  jz      loc_18001E69E
0x18001e893  movsxd  rcx, dword ptr [rdi+4]
0x18001e897  lea     r10, aNull; "(NULL)"
0x18001e89e  mov     r8d, [rdi]
0x18001e8a1  lea     r9, aClosingMsihand; "Closing MSIHANDLE (%d) of type %d for t"...
0x18001e8a8  mov     eax, [rdi+18h]
0x18001e8ab  xor     edx, edx; unsigned __int16
0x18001e8ad  mov     [rsp+98h+var_40], r15; void *
0x18001e8b2  mov     [rsp+98h+var_48], r15d; unsigned int
0x18001e8b7  mov     [rsp+98h+var_50], r10; unsigned __int16 *
0x18001e8bc  mov     [rsp+98h+var_58], r10; unsigned __int16 *
0x18001e8c1  mov     [rsp+98h+var_60], r10; unsigned __int16 *
0x18001e8c6  mov     [rsp+98h+var_68], rax; unsigned __int16 *
0x18001e8cb  mov     [rsp+98h+var_70], rcx; unsigned __int16 *
0x18001e8d0  lea     ecx, [rdx+5]; int
0x18001e8d3  mov     [rsp+98h+var_78], r8; unsigned __int16 *
0x18001e8d8  xor     r8d, r8d; int
0x18001e8db  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18001e8e0  jmp     loc_18001E69E
0x18001e8e5  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x18001e8ec  jnz     short loc_18001E903
0x18001e8ee  mov     edx, ebp; unsigned int
0x18001e8f0  call    ?CloseHandle@CMsiCustomAction@@QEAAJK@Z; CMsiCustomAction::CloseHandle(ulong)
0x18001e8f5  jmp     loc_18001E77A
0x18001e8fa  lea     r14, [rdi+10h]
0x18001e8fe  jmp     loc_18001E661
0x18001e903  mov     [rsp+98h+var_40], r15; void *
0x18001e908  lea     r10, aNull; "(NULL)"
0x18001e90f  mov     [rsp+98h+var_48], r15d; unsigned int
0x18001e914  lea     r9, aPassingToServi_11; "Passing to service: MsiCloseHandle(%d)"
0x18001e91b  mov     [rsp+98h+var_50], r10; unsigned __int16 *
0x18001e920  xor     edx, edx; unsigned __int16
0x18001e922  mov     [rsp+98h+var_58], r10; unsigned __int16 *
0x18001e927  xor     r8d, r8d; int
0x18001e92a  mov     [rsp+98h+var_60], r10; unsigned __int16 *
0x18001e92f  mov     [rsp+98h+var_68], r10; unsigned __int16 *
0x18001e934  mov     [rsp+98h+var_70], r10; unsigned __int16 *
0x18001e939  lea     ecx, [rdx+9]; int
0x18001e93c  mov     [rsp+98h+var_78], rbp; unsigned __int16 *
0x18001e941  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18001e946  jmp     short loc_18001E8EE
0x18001e948  inc     ecx
0x18001e94a  jmp     loc_18001E7DF
0x18001e94f  cmp     cs:?g_pActionThreadHead@@3PEAVCActionThreadData@@EA, r15; CActionThreadData * g_pActionThreadHead
0x18001e956  jz      short loc_18001E964
0x18001e958  mov     rcx, rbx
0x18001e95b  call    ?FIsCustomActionThread@@YA_NUUniqueThreadID@@@Z; FIsCustomActionThread(UniqueThreadID)
0x18001e960  test    al, al
0x18001e962  jnz     short loc_18001E971
0x18001e964  cmp     dword ptr [rdi+4], 0C1007h
0x18001e96b  jnz     loc_18001E68E
0x18001e971  cmp     cs:?g_dmDiagnosticMode@@3HA, r15d; int g_dmDiagnosticMode
0x18001e978  jz      short loc_18001E9C7
0x18001e97a  movsxd  r8, dword ptr [rdi+4]
0x18001e97e  lea     r10, aNull; "(NULL)"
0x18001e985  mov     r9d, [rdi]
0x18001e988  xor     edx, edx; unsigned __int16
0x18001e98a  mov     eax, [rdi+18h]
0x18001e98d  mov     [rsp+98h+var_40], r15; void *
0x18001e992  mov     [rsp+98h+var_48], r15d; unsigned int
0x18001e997  mov     [rsp+98h+var_50], r10; unsigned __int16 *
0x18001e99c  lea     ecx, [rdx+9]; int
0x18001e99f  mov     [rsp+98h+var_58], r10; unsigned __int16 *
0x18001e9a4  mov     [rsp+98h+var_60], r10; unsigned __int16 *
0x18001e9a9  mov     [rsp+98h+var_68], rax; unsigned __int16 *
0x18001e9ae  mov     [rsp+98h+var_70], r8; unsigned __int16 *
0x18001e9b3  xor     r8d, r8d; int
0x18001e9b6  mov     [rsp+98h+var_78], r9; unsigned __int16 *
0x18001e9bb  lea     r9, aImproperMsihan; "Improper MSIHANDLE closing. Trying to c"...
0x18001e9c2  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x18001e9c7  lea     rcx, ?m_csLock@CMsiHandle@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18001e9ce  call    cs:__imp_LeaveCriticalSection
0x18001e9d4  mov     eax, 5A4h
0x18001e9d9  jmp     loc_18001E77A
0x18001e9de  mov     rax, [rcx]
0x18001e9e1  mov     rax, [rax+10h]
0x18001e9e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9ea  jmp     loc_18001E79A
```
