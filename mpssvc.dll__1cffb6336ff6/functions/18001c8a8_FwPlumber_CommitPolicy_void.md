# FwPlumber::CommitPolicy(void)

- ea: `0x18001c8a8`
- end: `0x18001ccba`
- name: `?CommitPolicy@FwPlumber@@YAXXZ`
- size: `1042`
- prototype: `void __fastcall(FwPlumber *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001c884`

## callees

- `0x18000af3c`
- `0x180017110`
- `0x18001be88`
- `0x18001c228`
- `0x18001c8a8`
- `0x18001ccc0`
- `0x18001cd88`
- `0x18001d040`
- `0x18001d2b4`
- `0x18001d304`
- `0x18001d32c`
- `0x18001e198`
- `0x18001fe6c`
- `0x180051344`
- `0x18005463c`
- `0x180065f90`
- `0x180068dec`
- `0x1800738d6`
- `0x1800df8fc`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18001c9a0`
- `ntdll!EtwEventWrite` at `0x18001c9ce`
- `ntdll!EtwEventWrite` at `0x18001ca5f`
- `ntdll!EtwEventWrite` at `0x18001c9a0`
- `ntdll!EtwEventWrite` at `0x18001c9ce`
- `ntdll!EtwEventWrite` at `0x18001ca5f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001c977`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001c977`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cb8c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cba9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cb8c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001cba9`
- `fwbase!FwFree` at `0x18001cbdb`
- `fwbase!FwFree` at `0x18001cc51`
- `fwbase!FwFree` at `0x18001cbdb`
- `fwbase!FwFree` at `0x18001cc51`
- `fwpuclnt!FwpmTransactionCommit0` at `0x18001c9ad`
- `fwpuclnt!FwpmTransactionCommit0` at `0x18001c9ad`

## pseudocode

```c
void __fastcall FwPlumber::CommitPolicy(FwPlumber *this)
{
  __int64 v1; // rcx
  struct FILTER_HANDLE *v2; // rdx
  FwPlumber::FILTER_HANDLE *v3; // rbx
  FwPlumber *v4; // rcx
  __int64 v5; // rbp
  __int64 v6; // r14
  ULONGLONG v7; // rsi
  DWORD v8; // edi
  unsigned int v9; // edx
  struct FILTER_HANDLE *v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  struct Filter *v13; // rbx
  struct FILTER_HANDLE *v14; // rdx
  struct FILTER_HANDLE *v15; // rdx
  FwPlumber::FILTER_HANDLE *v16; // rax
  FwPlumber::FILTER_HANDLE *v17; // rax
  struct FILTER_HANDLE *v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  unsigned int v21; // edx
  unsigned int i; // ecx
  FwPlumber *pExceptionObject; // [rsp+50h] [rbp+8h] BYREF
  struct Filter *v24; // [rsp+58h] [rbp+10h] BYREF

  v1 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 120, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids);
    v1 = WPP_GLOBAL_Control;
  }
  if ( !byte_180131E88 )
  {
    if ( (_UNKNOWN *)v1 != &WPP_GLOBAL_Control && (*(_BYTE *)(v1 + 28) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(v1 + 16), 12, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids, 2147942487LL);
    LODWORD(pExceptionObject) = -2147024809;
    throw (FwPlumber::Exception *)&pExceptionObject;
  }
  pExceptionObject = 0;
  FwPlumber::CSmartFilterHandle::CSmartFilterHandle((FwPlumber::CSmartFilterHandle *)&pExceptionObject);
  if ( dword_180131DC8 && (BYTE4(xmmword_180131E40) & 1) != 0 )
  {
    v24 = 0;
    FwPlumber::CSmartFilterHandle::CSmartFilterHandle((FwPlumber::CSmartFilterHandle *)&v24);
    v13 = v24;
    if ( (BYTE4(xmmword_180131E40) & 4) != 0 )
    {
      FwPlumber::AddDeepInspectionFilters((FwPlumber *)v24, v10, v11, v12);
      FwPlumber::AddFtpFilters((FwPlumber *)v13, v18, v19, v20);
    }
    if ( (_DWORD)xmmword_180131E40 )
      FwPlumber::AddLoggingFilters((FwPlumber *)v13, v10, v11, v12);
    FwPlumber::AddStateManagementFilters((FwPlumber *)v13, v10, v11, v12);
    FwPlumber::AddNonPersistentStealthFilters((FwPlumber *)v13, v14);
    FwPlumber::AddMAFPCrossingFilters(v13, v15);
    if ( !(unsigned int)FwPlumber::FILTER_HANDLE::IsEmpty((FwPlumber::FILTER_HANDLE *)v13) )
    {
      v16 = (FwPlumber::FILTER_HANDLE *)v13;
      v13 = 0;
      qword_180131E38 = v16;
    }
    if ( v13 )
      FwPlumber::FILTER_HANDLE::`scalar deleting destructor'((FwPlumber::FILTER_HANDLE *)v13, (unsigned int)v2);
  }
  if ( qword_180131DB0 )
    FwPlumber::DeleteFiltersByHandle(qword_180131DB0, v2);
  if ( dword_180131D9C == 1 && !qword_180131DF0 && (_DWORD)xmmword_180131DF8 == 1 )
  {
    v3 = pExceptionObject;
    FwPlumber::AddAppContainerLoopbackFilters(pExceptionObject, v2);
    if ( !(unsigned int)FwPlumber::FILTER_HANDLE::IsEmpty(v3) )
    {
      v17 = v3;
      v3 = 0;
      pExceptionObject = 0;
      qword_180131DF0 = v17;
    }
  }
  else
  {
    v3 = pExceptionObject;
  }
  v4 = qword_180131EA8;
  if ( qword_180131EA8 )
    FwPlumber::DeleteFiltersByHandle(qword_180131EA8, v2);
  if ( dword_180131DC8 )
    FwPlumber::ApplyPersistentPolicy(v4);
  if ( dword_180131D9C == 1 )
    FwPlumber::ApplyPersistentAppContainerPolicy(v4);
  v5 = qword_180131DA8;
  v6 = qword_180131E28;
  v7 = GetTickCount64() - qword_180131DB8;
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_SVC_BFE_TransactionCommit_Enter, 0, 0);
  v8 = FwpmTransactionCommit0(engineHandle);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_SVC_BFE_TransactionCommit_Exit, 0, 0);
  if ( v8 )
  {
    v21 = g_FwCommitDynamic;
    if ( g_FwCommitDynamic < 0x32 )
    {
      for ( i = 0; i < g_FwCommitDynamic; ++i )
      {
        if ( v8 == *(&g_FwCommitDynamic + i + 1) )
          goto LABEL_64;
      }
      if ( i < 0x32 )
      {
        *(&g_FwCommitDynamic + i + 1) = v8;
        ++g_FwCommitDynamic;
      }
    }
LABEL_64:
    FwPlumber::ThrowWin32((FwPlumber *)v8, v21);
  }
  FwTelemetryEventWriteTransactionStatistics((unsigned int)v7, v5, v6);
  byte_180131E88 = 0;
  if ( qword_180131EA8 )
    FwPlumber::FILTER_HANDLE::`scalar deleting destructor'(qword_180131EA8, v9);
  qword_180131EA8 = 0;
  if ( qword_180131DB0 )
    FwPlumber::FILTER_HANDLE::`scalar deleting destructor'(qword_180131DB0, v9);
  qword_180131DB0 = 0;
  if ( dword_180131DC8 )
  {
    if ( (_QWORD)xmmword_180131E60 )
    {
      FwFree(xmmword_180131E60);
      *(_QWORD *)&xmmword_180131E60 = 0;
    }
    if ( (_QWORD)xmmword_180131E70 )
    {
      FwFree(xmmword_180131E70);
      *(_QWORD *)&xmmword_180131E70 = 0;
    }
  }
  if ( dword_180131D9C )
  {
    if ( *((_QWORD *)&xmmword_180131DF8 + 1) )
    {
      LocalFree(*((HLOCAL *)&xmmword_180131DF8 + 1));
      *((_QWORD *)&xmmword_180131DF8 + 1) = 0;
    }
    if ( hMem )
    {
      LocalFree(hMem);
      hMem = 0;
    }
  }
  dword_180131DC8 = 0;
  dword_180131D9C = 0;
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_SVC_Plumber_Policy_Commit, 0, 0);
  if ( v3 )
    FwPlumber::FILTER_HANDLE::`scalar deleting destructor'(v3, v9);
}

```

## disassembly

```asm
0x18001c8a8  mov     [rsp+arg_10], rbx
0x18001c8ad  push    rbp
0x18001c8ae  push    rsi
0x18001c8af  push    rdi
0x18001c8b0  push    r14
0x18001c8b2  push    r15
0x18001c8b4  sub     rsp, 20h
0x18001c8b8  lea     rbx, WPP_GLOBAL_Control
0x18001c8bf  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c8c6  cmp     rcx, rbx
0x18001c8c9  jnz     loc_18001CA84
0x18001c8cf  xor     r15d, r15d
0x18001c8d2  cmp     cs:byte_180131E88, r15b
0x18001c8d9  jnz     short loc_18001C8FF
0x18001c8db  mov     edi, 80070057h
0x18001c8e0  cmp     rcx, rbx
0x18001c8e3  jnz     loc_18001CC2A
0x18001c8e9  mov     dword ptr [rsp+48h+pExceptionObject], edi
0x18001c8ed  lea     rdx, _TI1?AUException@FwPlumber@@; pThrowInfo
0x18001c8f4  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18001c8f9  call    _CxxThrowException_0
0x18001c8ff  mov     [rsp+48h+pExceptionObject], r15
0x18001c904  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18001c909  call    ??0CSmartFilterHandle@FwPlumber@@QEAA@XZ; FwPlumber::CSmartFilterHandle::CSmartFilterHandle(void)
0x18001c90e  nop
0x18001c90f  cmp     cs:dword_180131DC8, r15d
0x18001c916  jnz     loc_18001CAAF
0x18001c91c  mov     rcx, cs:qword_180131DB0; this
0x18001c923  test    rcx, rcx
0x18001c926  jz      short loc_18001C92D
0x18001c928  call    ?DeleteFiltersByHandle@FwPlumber@@YAXPEAUFILTER_HANDLE@1@@Z; FwPlumber::DeleteFiltersByHandle(FwPlumber::FILTER_HANDLE *)
0x18001c92d  cmp     cs:dword_180131D9C, 1
0x18001c934  jz      loc_18001CB32
0x18001c93a  mov     rbx, [rsp+48h+pExceptionObject]
0x18001c93f  mov     rcx, cs:qword_180131EA8; this
0x18001c946  test    rcx, rcx
0x18001c949  jnz     loc_18001CC63
0x18001c94f  cmp     cs:dword_180131DC8, r15d
0x18001c956  jnz     loc_18001CC0C
0x18001c95c  cmp     cs:dword_180131D9C, 1
0x18001c963  jz      loc_18001CC20
0x18001c969  mov     rbp, cs:qword_180131DA8
0x18001c970  mov     r14, cs:qword_180131E28
0x18001c977  call    cs:__imp_GetTickCount64
0x18001c97d  mov     rsi, rax
0x18001c980  sub     rsi, cs:qword_180131DB8
0x18001c987  mov     rcx, cs:g_Provider
0x18001c98e  test    rcx, rcx
0x18001c991  jz      short loc_18001C9A6
0x18001c993  xor     r9d, r9d
0x18001c996  xor     r8d, r8d
0x18001c999  lea     rdx, MPS_SVC_BFE_TransactionCommit_Enter
0x18001c9a0  call    cs:__imp_EtwEventWrite
0x18001c9a6  mov     rcx, cs:engineHandle; engineHandle
0x18001c9ad  call    cs:__imp_FwpmTransactionCommit0
0x18001c9b3  mov     edi, eax
0x18001c9b5  mov     rcx, cs:g_Provider
0x18001c9bc  test    rcx, rcx
0x18001c9bf  jz      short loc_18001C9D4
0x18001c9c1  xor     r9d, r9d
0x18001c9c4  xor     r8d, r8d
0x18001c9c7  lea     rdx, MPS_SVC_BFE_TransactionCommit_Exit
0x18001c9ce  call    cs:__imp_EtwEventWrite
0x18001c9d4  test    edi, edi
0x18001c9d6  jnz     loc_18001CC7A
0x18001c9dc  mov     ecx, esi
0x18001c9de  mov     r8, r14
0x18001c9e1  mov     rdx, rbp
0x18001c9e4  call    FwTelemetryEventWriteTransactionStatistics
0x18001c9e9  mov     cs:byte_180131E88, r15b
0x18001c9f0  mov     rcx, cs:qword_180131EA8; this
0x18001c9f7  test    rcx, rcx
0x18001c9fa  jnz     loc_18001CC16
0x18001ca00  mov     cs:qword_180131EA8, r15
0x18001ca07  mov     rcx, cs:qword_180131DB0; this
0x18001ca0e  test    rcx, rcx
0x18001ca11  jnz     loc_18001CBED
0x18001ca17  mov     cs:qword_180131DB0, r15
0x18001ca1e  cmp     cs:dword_180131DC8, r15d
0x18001ca25  jnz     loc_18001CBBB
0x18001ca2b  cmp     cs:dword_180131D9C, r15d
0x18001ca32  jnz     loc_18001CB80
0x18001ca38  mov     cs:dword_180131DC8, r15d
0x18001ca3f  mov     cs:dword_180131D9C, r15d
0x18001ca46  mov     rcx, cs:g_Provider
0x18001ca4d  test    rcx, rcx
0x18001ca50  jz      short loc_18001CA66
0x18001ca52  xor     r9d, r9d
0x18001ca55  xor     r8d, r8d
0x18001ca58  lea     rdx, MPS_SVC_Plumber_Policy_Commit
0x18001ca5f  call    cs:__imp_EtwEventWrite
0x18001ca65  nop
0x18001ca66  test    rbx, rbx
0x18001ca69  jz      short loc_18001CA73
0x18001ca6b  mov     rcx, rbx; this
0x18001ca6e  call    ??_GFILTER_HANDLE@FwPlumber@@QEAAPEAXI@Z; FwPlumber::FILTER_HANDLE::`scalar deleting destructor'(uint)
0x18001ca73  mov     rbx, [rsp+48h+arg_10]
0x18001ca78  add     rsp, 20h
0x18001ca7c  pop     r15
0x18001ca7e  pop     r14
0x18001ca80  pop     rdi
0x18001ca81  pop     rsi
0x18001ca82  pop     rbp
0x18001ca83  retn
0x18001ca84  test    byte ptr [rcx+1Ch], 8
0x18001ca88  jz      loc_18001C8CF
0x18001ca8e  mov     edx, 78h ; 'x'
0x18001ca93  lea     r8, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids
0x18001ca9a  mov     rcx, [rcx+10h]
0x18001ca9e  call    WPP_SF_
0x18001caa3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001caaa  jmp     loc_18001C8CF
0x18001caaf  test    byte ptr cs:xmmword_180131E40+4, 1
0x18001cab6  jz      loc_18001C91C
0x18001cabc  mov     [rsp+48h+arg_8], r15
0x18001cac1  lea     rcx, [rsp+48h+arg_8]; this
0x18001cac6  call    ??0CSmartFilterHandle@FwPlumber@@QEAA@XZ; FwPlumber::CSmartFilterHandle::CSmartFilterHandle(void)
0x18001cacb  nop
0x18001cacc  mov     rbx, [rsp+48h+arg_8]
0x18001cad1  test    byte ptr cs:xmmword_180131E40+4, 4
0x18001cad8  jnz     loc_18001CBF7
0x18001cade  cmp     dword ptr cs:xmmword_180131E40, r15d
0x18001cae5  jnz     loc_18001CC6D
0x18001caeb  mov     rcx, rbx; this
0x18001caee  call    ?AddStateManagementFilters@FwPlumber@@YAXAEAUFILTER_HANDLE@1@@Z; FwPlumber::AddStateManagementFilters(FwPlumber::FILTER_HANDLE &)
0x18001caf3  mov     rcx, rbx; this
0x18001caf6  call    ?AddNonPersistentStealthFilters@FwPlumber@@YAXAEAUFILTER_HANDLE@1@@Z; FwPlumber::AddNonPersistentStealthFilters(FwPlumber::FILTER_HANDLE &)
0x18001cafb  mov     rcx, rbx; this
0x18001cafe  call    ?AddMAFPCrossingFilters@FwPlumber@@YAXAEAUFILTER_HANDLE@1@@Z; FwPlumber::AddMAFPCrossingFilters(FwPlumber::FILTER_HANDLE &)
0x18001cb03  mov     rcx, rbx; this
0x18001cb06  call    ?IsEmpty@FILTER_HANDLE@FwPlumber@@QEAAHXZ; FwPlumber::FILTER_HANDLE::IsEmpty(void)
0x18001cb0b  test    eax, eax
0x18001cb0d  jnz     short loc_18001CB1C
0x18001cb0f  mov     rax, rbx
0x18001cb12  mov     rbx, r15
0x18001cb15  mov     cs:qword_180131E38, rax
0x18001cb1c  test    rbx, rbx
0x18001cb1f  jz      loc_18001C91C
0x18001cb25  mov     rcx, rbx; this
0x18001cb28  call    ??_GFILTER_HANDLE@FwPlumber@@QEAAPEAXI@Z; FwPlumber::FILTER_HANDLE::`scalar deleting destructor'(uint)
0x18001cb2d  jmp     loc_18001C91C
0x18001cb32  cmp     cs:qword_180131DF0, r15
0x18001cb39  jnz     loc_18001C93A
0x18001cb3f  cmp     dword ptr cs:xmmword_180131DF8, 1
0x18001cb46  jnz     loc_18001C93A
0x18001cb4c  mov     rbx, [rsp+48h+pExceptionObject]
0x18001cb51  mov     rcx, rbx; this
0x18001cb54  call    ?AddAppContainerLoopbackFilters@FwPlumber@@YAXAEAUFILTER_HANDLE@1@@Z; FwPlumber::AddAppContainerLoopbackFilters(FwPlumber::FILTER_HANDLE &)
0x18001cb59  mov     rcx, rbx; this
0x18001cb5c  call    ?IsEmpty@FILTER_HANDLE@FwPlumber@@QEAAHXZ; FwPlumber::FILTER_HANDLE::IsEmpty(void)
0x18001cb61  test    eax, eax
0x18001cb63  jnz     loc_18001C93F
0x18001cb69  mov     rax, rbx
0x18001cb6c  mov     rbx, r15
0x18001cb6f  mov     [rsp+48h+pExceptionObject], rbx
0x18001cb74  mov     cs:qword_180131DF0, rax
0x18001cb7b  jmp     loc_18001C93F
0x18001cb80  mov     rcx, qword ptr cs:xmmword_180131DF8+8; hMem
0x18001cb87  test    rcx, rcx
0x18001cb8a  jz      short loc_18001CB99
0x18001cb8c  call    cs:__imp_LocalFree
0x18001cb92  mov     qword ptr cs:xmmword_180131DF8+8, r15
0x18001cb99  mov     rcx, qword ptr cs:hMem; hMem
0x18001cba0  test    rcx, rcx
0x18001cba3  jz      loc_18001CA38
0x18001cba9  call    cs:__imp_LocalFree
0x18001cbaf  mov     qword ptr cs:hMem, r15
0x18001cbb6  jmp     loc_18001CA38
0x18001cbbb  mov     rcx, qword ptr cs:xmmword_180131E60
0x18001cbc2  test    rcx, rcx
0x18001cbc5  jnz     loc_18001CC51
0x18001cbcb  mov     rcx, qword ptr cs:xmmword_180131E70
0x18001cbd2  test    rcx, rcx
0x18001cbd5  jz      loc_18001CA2B
0x18001cbdb  call    cs:__imp_FwFree
0x18001cbe1  mov     qword ptr cs:xmmword_180131E70, r15
0x18001cbe8  jmp     loc_18001CA2B
0x18001cbed  call    ??_GFILTER_HANDLE@FwPlumber@@QEAAPEAXI@Z; FwPlumber::FILTER_HANDLE::`scalar deleting destructor'(uint)
0x18001cbf2  jmp     loc_18001CA17
0x18001cbf7  mov     rcx, rbx; this
0x18001cbfa  call    ?AddDeepInspectionFilters@FwPlumber@@YAXAEAUFILTER_HANDLE@1@@Z; FwPlumber::AddDeepInspectionFilters(FwPlumber::FILTER_HANDLE &)
0x18001cbff  mov     rcx, rbx; this
0x18001cc02  call    ?AddFtpFilters@FwPlumber@@YAXAEAUFILTER_HANDLE@1@@Z; FwPlumber::AddFtpFilters(FwPlumber::FILTER_HANDLE &)
0x18001cc07  jmp     loc_18001CADE
0x18001cc0c  call    ?ApplyPersistentPolicy@FwPlumber@@YAXXZ; FwPlumber::ApplyPersistentPolicy(void)
0x18001cc11  jmp     loc_18001C95C
0x18001cc16  call    ??_GFILTER_HANDLE@FwPlumber@@QEAAPEAXI@Z; FwPlumber::FILTER_HANDLE::`scalar deleting destructor'(uint)
0x18001cc1b  jmp     loc_18001CA00
0x18001cc20  call    ?ApplyPersistentAppContainerPolicy@FwPlumber@@YAXXZ; FwPlumber::ApplyPersistentAppContainerPolicy(void)
0x18001cc25  jmp     loc_18001C969
0x18001cc2a  test    byte ptr [rcx+1Ch], 1
0x18001cc2e  jz      loc_18001C8E9
0x18001cc34  mov     edx, 0Ch
0x18001cc39  mov     r9d, edi
0x18001cc3c  lea     r8, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids
0x18001cc43  mov     rcx, [rcx+10h]
0x18001cc47  call    WPP_SF_d
0x18001cc4c  jmp     loc_18001C8E9
0x18001cc51  call    cs:__imp_FwFree
0x18001cc57  mov     qword ptr cs:xmmword_180131E60, r15
0x18001cc5e  jmp     loc_18001CBCB
0x18001cc63  call    ?DeleteFiltersByHandle@FwPlumber@@YAXPEAUFILTER_HANDLE@1@@Z; FwPlumber::DeleteFiltersByHandle(FwPlumber::FILTER_HANDLE *)
0x18001cc68  jmp     loc_18001C94F
0x18001cc6d  mov     rcx, rbx; this
0x18001cc70  call    ?AddLoggingFilters@FwPlumber@@YAXAEAUFILTER_HANDLE@1@@Z; FwPlumber::AddLoggingFilters(FwPlumber::FILTER_HANDLE &)
0x18001cc75  jmp     loc_18001CAEB
0x18001cc7a  mov     edx, cs:?g_FwCommitDynamic@@3U_FW_PLUMBER_ERROR_TRACKING@@A; unsigned int
0x18001cc80  cmp     edx, 32h ; '2'
0x18001cc83  jnb     short loc_18001CCB2
0x18001cc85  mov     ecx, r15d
0x18001cc88  lea     r8, ?g_FwCommitDynamic@@3U_FW_PLUMBER_ERROR_TRACKING@@A; _FW_PLUMBER_ERROR_TRACKING g_FwCommitDynamic
0x18001cc8f  cmp     ecx, edx
0x18001cc91  jnb     short loc_18001CCA0
0x18001cc93  mov     eax, ecx
0x18001cc95  cmp     edi, [r8+rax*4+4]
0x18001cc9a  jz      short loc_18001CCB2
0x18001cc9c  inc     ecx
0x18001cc9e  jmp     short loc_18001CC8F
0x18001cca0  cmp     ecx, 32h ; '2'
0x18001cca3  jnb     short loc_18001CCB2
0x18001cca5  mov     eax, ecx
0x18001cca7  mov     [r8+rax*4+4], edi
0x18001ccac  inc     cs:?g_FwCommitDynamic@@3U_FW_PLUMBER_ERROR_TRACKING@@A; _FW_PLUMBER_ERROR_TRACKING g_FwCommitDynamic
0x18001ccb2  mov     ecx, edi; this
0x18001ccb4  call    ?ThrowWin32@FwPlumber@@YAXK@Z; FwPlumber::ThrowWin32(ulong)
```
