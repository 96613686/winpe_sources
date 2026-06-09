# FwPlumber::CommitPolicy(void)

- ea: `0x18001eb68`
- end: `0x18001efb1`
- name: `?CommitPolicy@FwPlumber@@YAXXZ`
- size: `1097`
- prototype: `void __fastcall(FwPlumber *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001eb40`

## callees

- `0x18000a710`
- `0x1800192e0`
- `0x18001e130`
- `0x18001e4e0`
- `0x18001eb68`
- `0x18001efb8`
- `0x18001f084`
- `0x18001f340`
- `0x18001f5d0`
- `0x18001f624`
- `0x18001f64c`
- `0x1800204cc`
- `0x1800221c0`
- `0x180055674`
- `0x1800599c0`
- `0x1800697b0`
- `0x18006ecd4`
- `0x180076d96`
- `0x1800e5c90`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x18001ec66`
- `ntdll!EtwEventWrite` at `0x18001eca0`
- `ntdll!EtwEventWrite` at `0x18001ed37`
- `ntdll!EtwEventWrite` at `0x18001ec66`
- `ntdll!EtwEventWrite` at `0x18001eca0`
- `ntdll!EtwEventWrite` at `0x18001ed37`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001ec37`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001ec37`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ee6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ee8e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ee6b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001ee8e`
- `fwbase!FwFree` at `0x18001eec6`
- `fwbase!FwFree` at `0x18001ef42`
- `fwbase!FwFree` at `0x18001eec6`
- `fwbase!FwFree` at `0x18001ef42`
- `fwpuclnt!FwpmTransactionCommit0` at `0x18001ec79`
- `fwpuclnt!FwpmTransactionCommit0` at `0x18001ec79`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  struct Filter *v11; // rbx
  struct FILTER_HANDLE *v12; // rdx
  struct FILTER_HANDLE *v13; // rdx
  FwPlumber::FILTER_HANDLE *v14; // rax
  FwPlumber::FILTER_HANDLE *v15; // rax
  struct FILTER_HANDLE *v16; // rdx
  unsigned int v17; // edx
  unsigned int i; // ecx
  FwPlumber *pExceptionObject; // [rsp+50h] [rbp+8h] BYREF
  struct Filter *v20; // [rsp+58h] [rbp+10h] BYREF

  v1 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
  {
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 120, WPP_2afde9bce9f33b7e8b7f061cee2eaad7_Traceguids);
    v1 = WPP_GLOBAL_Control;
  }
  if ( !byte_180138020 )
  {
    if ( (_UNKNOWN *)v1 != &WPP_GLOBAL_Control && (*(_BYTE *)(v1 + 28) & 1) != 0 )
      WPP_SF_d(*(_QWORD *)(v1 + 16), 12, WPP_2afde9bce9f33b7e8b7f061cee2eaad7_Traceguids, 2147942487LL);
    LODWORD(pExceptionObject) = -2147024809;
    throw (FwPlumber::Exception *)&pExceptionObject;
  }
  pExceptionObject = 0;
  FwPlumber::CSmartFilterHandle::CSmartFilterHandle((FwPlumber::CSmartFilterHandle *)&pExceptionObject);
  if ( dword_180137F58 && (BYTE4(xmmword_180137FE0) & 1) != 0 )
  {
    v20 = 0;
    FwPlumber::CSmartFilterHandle::CSmartFilterHandle((FwPlumber::CSmartFilterHandle *)&v20);
    v11 = v20;
    if ( (BYTE4(xmmword_180137FE0) & 4) != 0 )
    {
      FwPlumber::AddDeepInspectionFilters((FwPlumber *)v20, v10);
      FwPlumber::AddFtpFilters((FwPlumber *)v11, v16);
    }
    if ( (_DWORD)xmmword_180137FE0 )
      FwPlumber::AddLoggingFilters((FwPlumber *)v11, v10);
    FwPlumber::AddStateManagementFilters((FwPlumber *)v11, v10);
    FwPlumber::AddNonPersistentStealthFilters((FwPlumber *)v11, v12);
    FwPlumber::AddMAFPCrossingFilters(v11, v13);
    if ( !(unsigned int)FwPlumber::FILTER_HANDLE::IsEmpty((FwPlumber::FILTER_HANDLE *)v11) )
    {
      v14 = (FwPlumber::FILTER_HANDLE *)v11;
      v11 = 0;
      qword_180137FD0 = v14;
    }
    if ( v11 )
      FwPlumber::FILTER_HANDLE::`scalar deleting destructor'((FwPlumber::FILTER_HANDLE *)v11, (unsigned int)v2);
  }
  if ( qword_180137F40 )
    FwPlumber::DeleteFiltersByHandle(qword_180137F40, v2);
  if ( dword_180137F2C == 1 && !qword_180137F80 && (_DWORD)xmmword_180137F88 == 1 )
  {
    v3 = pExceptionObject;
    FwPlumber::AddAppContainerLoopbackFilters(pExceptionObject, v2);
    if ( !(unsigned int)FwPlumber::FILTER_HANDLE::IsEmpty(v3) )
    {
      v15 = v3;
      v3 = 0;
      pExceptionObject = 0;
      qword_180137F80 = v15;
    }
  }
  else
  {
    v3 = pExceptionObject;
  }
  v4 = qword_180138040;
  if ( qword_180138040 )
    FwPlumber::DeleteFiltersByHandle(qword_180138040, v2);
  if ( dword_180137F58 )
    FwPlumber::ApplyPersistentPolicy(v4);
  if ( dword_180137F2C == 1 )
    FwPlumber::ApplyPersistentAppContainerPolicy(v4);
  v5 = qword_180137F30;
  v6 = qword_180137FA8;
  v7 = GetTickCount64() - qword_180137F48;
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_SVC_BFE_TransactionCommit_Enter, 0, 0);
  v8 = FwpmTransactionCommit0(engineHandle);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_SVC_BFE_TransactionCommit_Exit, 0, 0);
  if ( v8 )
  {
    v17 = g_FwCommitDynamic;
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
    FwPlumber::ThrowWin32((FwPlumber *)v8, v17);
  }
  FwTelemetryEventWriteTransactionStatistics((unsigned int)v7, v5, v6);
  byte_180138020 = 0;
  if ( qword_180138040 )
    FwPlumber::FILTER_HANDLE::`scalar deleting destructor'(qword_180138040, v9);
  qword_180138040 = 0;
  if ( qword_180137F40 )
    FwPlumber::FILTER_HANDLE::`scalar deleting destructor'(qword_180137F40, v9);
  qword_180137F40 = 0;
  if ( dword_180137F58 )
  {
    if ( (_QWORD)xmmword_180138000 )
    {
      FwFree(xmmword_180138000);
      *(_QWORD *)&xmmword_180138000 = 0;
    }
    if ( (_QWORD)xmmword_180138010 )
    {
      FwFree(xmmword_180138010);
      *(_QWORD *)&xmmword_180138010 = 0;
    }
  }
  if ( dword_180137F2C )
  {
    if ( *((_QWORD *)&xmmword_180137F88 + 1) )
    {
      LocalFree(*((HLOCAL *)&xmmword_180137F88 + 1));
      *((_QWORD *)&xmmword_180137F88 + 1) = 0;
    }
    if ( hMem )
    {
      LocalFree(hMem);
      hMem = 0;
    }
  }
  dword_180137F58 = 0;
  dword_180137F2C = 0;
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_SVC_Plumber_Policy_Commit, 0, 0);
  if ( v3 )
    FwPlumber::FILTER_HANDLE::`scalar deleting destructor'(v3, v9);
}

```

## disassembly

```asm
0x18001eb68  mov     [rsp+arg_10], rbx
0x18001eb6d  push    rbp
0x18001eb6e  push    rsi
0x18001eb6f  push    rdi
0x18001eb70  push    r14
0x18001eb72  push    r15
0x18001eb74  sub     rsp, 20h
0x18001eb78  lea     rbx, WPP_GLOBAL_Control
0x18001eb7f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eb86  cmp     rcx, rbx
0x18001eb89  jnz     loc_18001ED63
0x18001eb8f  xor     r15d, r15d
0x18001eb92  cmp     cs:byte_180138020, r15b
0x18001eb99  jnz     short loc_18001EBBF
0x18001eb9b  mov     edi, 80070057h
0x18001eba0  cmp     rcx, rbx
0x18001eba3  jnz     loc_18001EF1B
0x18001eba9  mov     dword ptr [rsp+48h+pExceptionObject], edi
0x18001ebad  lea     rdx, _TI1?AUException@FwPlumber@@; pThrowInfo
0x18001ebb4  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18001ebb9  call    _CxxThrowException_0
0x18001ebbf  mov     [rsp+48h+pExceptionObject], r15
0x18001ebc4  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18001ebc9  call    ??0CSmartFilterHandle@FwPlumber@@QEAA@XZ; FwPlumber::CSmartFilterHandle::CSmartFilterHandle(void)
0x18001ebce  nop
0x18001ebcf  cmp     cs:dword_180137F58, r15d
0x18001ebd6  jnz     loc_18001ED8E
0x18001ebdc  mov     rcx, cs:qword_180137F40; this
0x18001ebe3  test    rcx, rcx
0x18001ebe6  jz      short loc_18001EBED
0x18001ebe8  call    ?DeleteFiltersByHandle@FwPlumber@@YAXPEAUFILTER_HANDLE@1@@Z; FwPlumber::DeleteFiltersByHandle(FwPlumber::FILTER_HANDLE *)
0x18001ebed  cmp     cs:dword_180137F2C, 1
0x18001ebf4  jz      loc_18001EE11
0x18001ebfa  mov     rbx, [rsp+48h+pExceptionObject]
0x18001ebff  mov     rcx, cs:qword_180138040; this
0x18001ec06  test    rcx, rcx
0x18001ec09  jnz     loc_18001EF5A
0x18001ec0f  cmp     cs:dword_180137F58, r15d
0x18001ec16  jnz     loc_18001EEFD
0x18001ec1c  cmp     cs:dword_180137F2C, 1
0x18001ec23  jz      loc_18001EF11
0x18001ec29  mov     rbp, cs:qword_180137F30
0x18001ec30  mov     r14, cs:qword_180137FA8
0x18001ec37  call    cs:__imp_GetTickCount64
0x18001ec3e  nop     dword ptr [rax+rax+00h]
0x18001ec43  mov     rsi, rax
0x18001ec46  sub     rsi, cs:qword_180137F48
0x18001ec4d  mov     rcx, cs:g_Provider
0x18001ec54  test    rcx, rcx
0x18001ec57  jz      short loc_18001EC72
0x18001ec59  xor     r9d, r9d
0x18001ec5c  xor     r8d, r8d
0x18001ec5f  lea     rdx, MPS_SVC_BFE_TransactionCommit_Enter
0x18001ec66  call    cs:__imp_EtwEventWrite
0x18001ec6d  nop     dword ptr [rax+rax+00h]
0x18001ec72  mov     rcx, cs:engineHandle; engineHandle
0x18001ec79  call    cs:__imp_FwpmTransactionCommit0
0x18001ec80  nop     dword ptr [rax+rax+00h]
0x18001ec85  mov     edi, eax
0x18001ec87  mov     rcx, cs:g_Provider
0x18001ec8e  test    rcx, rcx
0x18001ec91  jz      short loc_18001ECAC
0x18001ec93  xor     r9d, r9d
0x18001ec96  xor     r8d, r8d
0x18001ec99  lea     rdx, MPS_SVC_BFE_TransactionCommit_Exit
0x18001eca0  call    cs:__imp_EtwEventWrite
0x18001eca7  nop     dword ptr [rax+rax+00h]
0x18001ecac  test    edi, edi
0x18001ecae  jnz     loc_18001EF71
0x18001ecb4  mov     ecx, esi
0x18001ecb6  mov     r8, r14
0x18001ecb9  mov     rdx, rbp
0x18001ecbc  call    FwTelemetryEventWriteTransactionStatistics
0x18001ecc1  mov     cs:byte_180138020, r15b
0x18001ecc8  mov     rcx, cs:qword_180138040; this
0x18001eccf  test    rcx, rcx
0x18001ecd2  jnz     loc_18001EF07
0x18001ecd8  mov     cs:qword_180138040, r15
0x18001ecdf  mov     rcx, cs:qword_180137F40; this
0x18001ece6  test    rcx, rcx
0x18001ece9  jnz     loc_18001EEDE
0x18001ecef  mov     cs:qword_180137F40, r15
0x18001ecf6  cmp     cs:dword_180137F58, r15d
0x18001ecfd  jnz     loc_18001EEA6
0x18001ed03  cmp     cs:dword_180137F2C, r15d
0x18001ed0a  jnz     loc_18001EE5F
0x18001ed10  mov     cs:dword_180137F58, r15d
0x18001ed17  mov     cs:dword_180137F2C, r15d
0x18001ed1e  mov     rcx, cs:g_Provider
0x18001ed25  test    rcx, rcx
0x18001ed28  jz      short loc_18001ED44
0x18001ed2a  xor     r9d, r9d
0x18001ed2d  xor     r8d, r8d
0x18001ed30  lea     rdx, MPS_SVC_Plumber_Policy_Commit
0x18001ed37  call    cs:__imp_EtwEventWrite
0x18001ed3e  nop     dword ptr [rax+rax+00h]
0x18001ed43  nop
0x18001ed44  test    rbx, rbx
0x18001ed47  jz      short loc_18001ED51
0x18001ed49  mov     rcx, rbx; this
0x18001ed4c  call    ??_GFILTER_HANDLE@FwPlumber@@QEAAPEAXI@Z; FwPlumber::FILTER_HANDLE::`scalar deleting destructor'(uint)
0x18001ed51  mov     rbx, [rsp+48h+arg_10]
0x18001ed56  add     rsp, 20h
0x18001ed5a  pop     r15
0x18001ed5c  pop     r14
0x18001ed5e  pop     rdi
0x18001ed5f  pop     rsi
0x18001ed60  pop     rbp
0x18001ed61  retn
0x18001ed63  test    byte ptr [rcx+1Ch], 8
0x18001ed67  jz      loc_18001EB8F
0x18001ed6d  mov     edx, 78h ; 'x'
0x18001ed72  lea     r8, WPP_2afde9bce9f33b7e8b7f061cee2eaad7_Traceguids
0x18001ed79  mov     rcx, [rcx+10h]
0x18001ed7d  call    WPP_SF_
0x18001ed82  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ed89  jmp     loc_18001EB8F
0x18001ed8e  test    byte ptr cs:xmmword_180137FE0+4, 1
0x18001ed95  jz      loc_18001EBDC
0x18001ed9b  mov     [rsp+48h+arg_8], r15
0x18001eda0  lea     rcx, [rsp+48h+arg_8]; this
0x18001eda5  call    ??0CSmartFilterHandle@FwPlumber@@QEAA@XZ; FwPlumber::CSmartFilterHandle::CSmartFilterHandle(void)
0x18001edaa  nop
0x18001edab  mov     rbx, [rsp+48h+arg_8]
0x18001edb0  test    byte ptr cs:xmmword_180137FE0+4, 4
0x18001edb7  jnz     loc_18001EEE8
0x18001edbd  cmp     dword ptr cs:xmmword_180137FE0, r15d
0x18001edc4  jnz     loc_18001EF64
0x18001edca  mov     rcx, rbx; this
0x18001edcd  call    ?AddStateManagementFilters@FwPlumber@@YAXAEAUFILTER_HANDLE@1@@Z; FwPlumber::AddStateManagementFilters(FwPlumber::FILTER_HANDLE &)
0x18001edd2  mov     rcx, rbx; this
0x18001edd5  call    ?AddNonPersistentStealthFilters@FwPlumber@@YAXAEAUFILTER_HANDLE@1@@Z; FwPlumber::AddNonPersistentStealthFilters(FwPlumber::FILTER_HANDLE &)
0x18001edda  mov     rcx, rbx; this
0x18001eddd  call    ?AddMAFPCrossingFilters@FwPlumber@@YAXAEAUFILTER_HANDLE@1@@Z; FwPlumber::AddMAFPCrossingFilters(FwPlumber::FILTER_HANDLE &)
0x18001ede2  mov     rcx, rbx; this
0x18001ede5  call    ?IsEmpty@FILTER_HANDLE@FwPlumber@@QEAAHXZ; FwPlumber::FILTER_HANDLE::IsEmpty(void)
0x18001edea  test    eax, eax
0x18001edec  jnz     short loc_18001EDFB
0x18001edee  mov     rax, rbx
0x18001edf1  mov     rbx, r15
0x18001edf4  mov     cs:qword_180137FD0, rax
0x18001edfb  test    rbx, rbx
0x18001edfe  jz      loc_18001EBDC
0x18001ee04  mov     rcx, rbx; this
0x18001ee07  call    ??_GFILTER_HANDLE@FwPlumber@@QEAAPEAXI@Z; FwPlumber::FILTER_HANDLE::`scalar deleting destructor'(uint)
0x18001ee0c  jmp     loc_18001EBDC
0x18001ee11  cmp     cs:qword_180137F80, r15
0x18001ee18  jnz     loc_18001EBFA
0x18001ee1e  cmp     dword ptr cs:xmmword_180137F88, 1
0x18001ee25  jnz     loc_18001EBFA
0x18001ee2b  mov     rbx, [rsp+48h+pExceptionObject]
0x18001ee30  mov     rcx, rbx; this
0x18001ee33  call    ?AddAppContainerLoopbackFilters@FwPlumber@@YAXAEAUFILTER_HANDLE@1@@Z; FwPlumber::AddAppContainerLoopbackFilters(FwPlumber::FILTER_HANDLE &)
0x18001ee38  mov     rcx, rbx; this
0x18001ee3b  call    ?IsEmpty@FILTER_HANDLE@FwPlumber@@QEAAHXZ; FwPlumber::FILTER_HANDLE::IsEmpty(void)
0x18001ee40  test    eax, eax
0x18001ee42  jnz     loc_18001EBFF
0x18001ee48  mov     rax, rbx
0x18001ee4b  mov     rbx, r15
0x18001ee4e  mov     [rsp+48h+pExceptionObject], rbx
0x18001ee53  mov     cs:qword_180137F80, rax
0x18001ee5a  jmp     loc_18001EBFF
0x18001ee5f  mov     rcx, qword ptr cs:xmmword_180137F88+8; hMem
0x18001ee66  test    rcx, rcx
0x18001ee69  jz      short loc_18001EE7E
0x18001ee6b  call    cs:__imp_LocalFree
0x18001ee72  nop     dword ptr [rax+rax+00h]
0x18001ee77  mov     qword ptr cs:xmmword_180137F88+8, r15
0x18001ee7e  mov     rcx, qword ptr cs:hMem; hMem
0x18001ee85  test    rcx, rcx
0x18001ee88  jz      loc_18001ED10
0x18001ee8e  call    cs:__imp_LocalFree
0x18001ee95  nop     dword ptr [rax+rax+00h]
0x18001ee9a  mov     qword ptr cs:hMem, r15
0x18001eea1  jmp     loc_18001ED10
0x18001eea6  mov     rcx, qword ptr cs:xmmword_180138000
0x18001eead  test    rcx, rcx
0x18001eeb0  jnz     loc_18001EF42
0x18001eeb6  mov     rcx, qword ptr cs:xmmword_180138010
0x18001eebd  test    rcx, rcx
0x18001eec0  jz      loc_18001ED03
0x18001eec6  call    cs:__imp_FwFree
0x18001eecd  nop     dword ptr [rax+rax+00h]
0x18001eed2  mov     qword ptr cs:xmmword_180138010, r15
0x18001eed9  jmp     loc_18001ED03
0x18001eede  call    ??_GFILTER_HANDLE@FwPlumber@@QEAAPEAXI@Z; FwPlumber::FILTER_HANDLE::`scalar deleting destructor'(uint)
0x18001eee3  jmp     loc_18001ECEF
0x18001eee8  mov     rcx, rbx; this
0x18001eeeb  call    ?AddDeepInspectionFilters@FwPlumber@@YAXAEAUFILTER_HANDLE@1@@Z; FwPlumber::AddDeepInspectionFilters(FwPlumber::FILTER_HANDLE &)
0x18001eef0  mov     rcx, rbx; this
0x18001eef3  call    ?AddFtpFilters@FwPlumber@@YAXAEAUFILTER_HANDLE@1@@Z; FwPlumber::AddFtpFilters(FwPlumber::FILTER_HANDLE &)
0x18001eef8  jmp     loc_18001EDBD
0x18001eefd  call    ?ApplyPersistentPolicy@FwPlumber@@YAXXZ; FwPlumber::ApplyPersistentPolicy(void)
0x18001ef02  jmp     loc_18001EC1C
0x18001ef07  call    ??_GFILTER_HANDLE@FwPlumber@@QEAAPEAXI@Z; FwPlumber::FILTER_HANDLE::`scalar deleting destructor'(uint)
0x18001ef0c  jmp     loc_18001ECD8
0x18001ef11  call    ?ApplyPersistentAppContainerPolicy@FwPlumber@@YAXXZ; FwPlumber::ApplyPersistentAppContainerPolicy(void)
0x18001ef16  jmp     loc_18001EC29
0x18001ef1b  test    byte ptr [rcx+1Ch], 1
0x18001ef1f  jz      loc_18001EBA9
0x18001ef25  mov     edx, 0Ch
0x18001ef2a  mov     r9d, edi
0x18001ef2d  lea     r8, WPP_2afde9bce9f33b7e8b7f061cee2eaad7_Traceguids
0x18001ef34  mov     rcx, [rcx+10h]
0x18001ef38  call    WPP_SF_d
0x18001ef3d  jmp     loc_18001EBA9
0x18001ef42  call    cs:__imp_FwFree
0x18001ef49  nop     dword ptr [rax+rax+00h]
0x18001ef4e  mov     qword ptr cs:xmmword_180138000, r15
0x18001ef55  jmp     loc_18001EEB6
0x18001ef5a  call    ?DeleteFiltersByHandle@FwPlumber@@YAXPEAUFILTER_HANDLE@1@@Z; FwPlumber::DeleteFiltersByHandle(FwPlumber::FILTER_HANDLE *)
0x18001ef5f  jmp     loc_18001EC0F
0x18001ef64  mov     rcx, rbx; this
0x18001ef67  call    ?AddLoggingFilters@FwPlumber@@YAXAEAUFILTER_HANDLE@1@@Z; FwPlumber::AddLoggingFilters(FwPlumber::FILTER_HANDLE &)
0x18001ef6c  jmp     loc_18001EDCA
0x18001ef71  mov     edx, cs:?g_FwCommitDynamic@@3U_FW_PLUMBER_ERROR_TRACKING@@A; unsigned int
0x18001ef77  cmp     edx, 32h ; '2'
0x18001ef7a  jnb     short loc_18001EFA9
0x18001ef7c  mov     ecx, r15d
0x18001ef7f  lea     r8, ?g_FwCommitDynamic@@3U_FW_PLUMBER_ERROR_TRACKING@@A; _FW_PLUMBER_ERROR_TRACKING g_FwCommitDynamic
0x18001ef86  cmp     ecx, edx
0x18001ef88  jnb     short loc_18001EF97
0x18001ef8a  mov     eax, ecx
0x18001ef8c  cmp     edi, [r8+rax*4+4]
0x18001ef91  jz      short loc_18001EFA9
0x18001ef93  inc     ecx
0x18001ef95  jmp     short loc_18001EF86
0x18001ef97  cmp     ecx, 32h ; '2'
0x18001ef9a  jnb     short loc_18001EFA9
0x18001ef9c  mov     eax, ecx
0x18001ef9e  mov     [r8+rax*4+4], edi
0x18001efa3  inc     cs:?g_FwCommitDynamic@@3U_FW_PLUMBER_ERROR_TRACKING@@A; _FW_PLUMBER_ERROR_TRACKING g_FwCommitDynamic
0x18001efa9  mov     ecx, edi; this
0x18001efab  call    ?ThrowWin32@FwPlumber@@YAXK@Z; FwPlumber::ThrowWin32(ulong)
```
