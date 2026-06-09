# FwPlumber::Shutdown(void)

- ea: `0x1800e0340`
- end: `0x1800e05ad`
- name: `?Shutdown@FwPlumber@@YAXXZ`
- size: `621`
- prototype: `void __fastcall(FwPlumber *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800e05d8`

## callees

- `0x1800093b0`
- `0x180017110`
- `0x18001d2b4`
- `0x18004c284`
- `0x1800d3138`
- `0x1800e0170`
- `0x1800e0340`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800e0515`
- `ntdll!EtwEventWrite` at `0x1800e0541`
- `ntdll!EtwEventWrite` at `0x1800e0515`
- `ntdll!EtwEventWrite` at `0x1800e0541`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800e038f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800e03a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800e03c1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800e038f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800e03a8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800e03c1`
- `fwpuclnt!FwpmEngineClose0` at `0x1800e0522`
- `fwpuclnt!FwpmEngineClose0` at `0x1800e0522`
- `fwpuclnt!FwpmProviderContextDeleteById0` at `0x1800e03e1`
- `fwpuclnt!FwpmProviderContextDeleteById0` at `0x1800e03fa`
- `fwpuclnt!FwpmProviderContextDeleteById0` at `0x1800e0413`
- `fwpuclnt!FwpmProviderContextDeleteById0` at `0x1800e042c`
- `fwpuclnt!FwpmProviderContextDeleteById0` at `0x1800e0445`
- `fwpuclnt!FwpmProviderContextDeleteById0` at `0x1800e045e`
- `fwpuclnt!FwpmProviderContextDeleteById0` at `0x1800e0477`
- `fwpuclnt!FwpmProviderContextDeleteById0` at `0x1800e0490`
- `fwpuclnt!FwpmProviderContextDeleteById0` at `0x1800e04a9`
- `fwpuclnt!FwpmProviderContextDeleteById0` at `0x1800e03e1`
- `fwpuclnt!FwpmProviderContextDeleteById0` at `0x1800e03fa`
- `fwpuclnt!FwpmProviderContextDeleteById0` at `0x1800e0413`
- `fwpuclnt!FwpmProviderContextDeleteById0` at `0x1800e042c`
- `fwpuclnt!FwpmProviderContextDeleteById0` at `0x1800e0445`
- `fwpuclnt!FwpmProviderContextDeleteById0` at `0x1800e045e`
- `fwpuclnt!FwpmProviderContextDeleteById0` at `0x1800e0477`
- `fwpuclnt!FwpmProviderContextDeleteById0` at `0x1800e0490`
- `fwpuclnt!FwpmProviderContextDeleteById0` at `0x1800e04a9`

## pseudocode

```c
void __fastcall FwPlumber::Shutdown(FwPlumber *this, __int64 a2, __int64 a3, __int64 a4)
{
  PSID v4; // rcx
  UINT64 v5; // rdx
  unsigned int v6; // edx

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 116, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids);
  if ( engineHandle )
  {
    if ( FwPlumber::m_pAllAppContainersSd )
    {
      LocalFree(FwPlumber::m_pAllAppContainersSd);
      FwPlumber::m_pAllAppContainersSd = 0;
    }
    if ( FwPlumber::m_pIntranetAppCLoopbackSd )
    {
      LocalFree(FwPlumber::m_pIntranetAppCLoopbackSd);
      FwPlumber::m_pIntranetAppCLoopbackSd = 0;
    }
    v4 = FwPlumber::m_pNullSID;
    if ( FwPlumber::m_pNullSID )
    {
      LocalFree(FwPlumber::m_pNullSID);
      FwPlumber::m_pNullSID = 0;
    }
    if ( FwPlumber::LOMProviderCtxtID )
      FwpmProviderContextDeleteById0(engineHandle, FwPlumber::LOMProviderCtxtID);
    if ( FwPlumber::LSMProviderCtxtID )
      FwpmProviderContextDeleteById0(engineHandle, FwPlumber::LSMProviderCtxtID);
    if ( FwPlumber::PolicySilentModeProviderCtxtID )
      FwpmProviderContextDeleteById0(engineHandle, FwPlumber::PolicySilentModeProviderCtxtID);
    if ( FwPlumber::QuarantineProviderCtxtID )
      FwpmProviderContextDeleteById0(engineHandle, FwPlumber::QuarantineProviderCtxtID);
    if ( FwPlumber::BootProviderCtxtID )
      FwpmProviderContextDeleteById0(engineHandle, FwPlumber::BootProviderCtxtID);
    if ( FwPlumber::WshProviderCtxtID )
      FwpmProviderContextDeleteById0(engineHandle, FwPlumber::WshProviderCtxtID);
    if ( FwPlumber::QueryUserProviderCtxtID )
      FwpmProviderContextDeleteById0(engineHandle, FwPlumber::QueryUserProviderCtxtID);
    if ( FwPlumber::AppCLoopbackProviderCtxtID )
      FwpmProviderContextDeleteById0(engineHandle, FwPlumber::AppCLoopbackProviderCtxtID);
    v5 = FwPlumber::StealthProviderCtxtID;
    if ( FwPlumber::StealthProviderCtxtID )
      FwpmProviderContextDeleteById0(engineHandle, FwPlumber::StealthProviderCtxtID);
    if ( dword_180131DA0 )
    {
      if ( gvMipsInitialized != 1 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v4, v5, a3, a4);
      if ( !gvBfeEngineHandle )
        MicrosoftTelemetryAssertTriggeredNoArgs(v4, v5, a3, a4);
      IpsecShutdownInternal();
      IpsReturnError("IpsecApiShutdown", 0x10Au, 0, 1, 0);
      dword_180131DA0 = 0;
    }
    if ( g_Provider )
      EtwEventWrite(g_Provider, MPS_SVC_BFE_EngineClose_Enter, 0, 0);
    FwpmEngineClose0(engineHandle);
    if ( g_Provider )
      EtwEventWrite(g_Provider, MPS_SVC_BFE_EngineClose_Exit, 0, 0);
    engineHandle = 0;
    if ( qword_180131E38 )
    {
      FwPlumber::FILTER_HANDLE::`scalar deleting destructor'(qword_180131E38, v6);
      qword_180131E38 = 0;
    }
    if ( qword_180131DF0 )
    {
      FwPlumber::FILTER_HANDLE::`scalar deleting destructor'(qword_180131DF0, v6);
      qword_180131DF0 = 0;
      dword_180131D9C = 0;
    }
  }
  FwPlumberFreeTrackObjError((struct _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *)&g_FwFilterError);
  FwPlumberFreeTrackObjError((struct _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *)&g_FwCalloutError);
  FwPlumberFreeTrackObjError((struct _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *)&g_FwProvCtxError);
}

```

## disassembly

```asm
0x1800e0340  push    rbx
0x1800e0342  sub     rsp, 30h
0x1800e0346  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e034d  lea     rax, WPP_GLOBAL_Control
0x1800e0354  cmp     rcx, rax
0x1800e0357  jz      short loc_1800E0374
0x1800e0359  test    byte ptr [rcx+1Ch], 8
0x1800e035d  jz      short loc_1800E0374
0x1800e035f  mov     rcx, [rcx+10h]
0x1800e0363  lea     r8, WPP_489b48d90f353cde71bd342750f78ef2_Traceguids
0x1800e036a  mov     edx, 74h ; 't'
0x1800e036f  call    WPP_SF_
0x1800e0374  xor     ebx, ebx
0x1800e0376  cmp     cs:engineHandle, rbx
0x1800e037d  jz      loc_1800E0584
0x1800e0383  mov     rcx, cs:?m_pAllAppContainersSd@FwPlumber@@3PEAXEA; hMem
0x1800e038a  test    rcx, rcx
0x1800e038d  jz      short loc_1800E039C
0x1800e038f  call    cs:__imp_LocalFree
0x1800e0395  mov     cs:?m_pAllAppContainersSd@FwPlumber@@3PEAXEA, rbx; void * FwPlumber::m_pAllAppContainersSd
0x1800e039c  mov     rcx, cs:?m_pIntranetAppCLoopbackSd@FwPlumber@@3PEAXEA; hMem
0x1800e03a3  test    rcx, rcx
0x1800e03a6  jz      short loc_1800E03B5
0x1800e03a8  call    cs:__imp_LocalFree
0x1800e03ae  mov     cs:?m_pIntranetAppCLoopbackSd@FwPlumber@@3PEAXEA, rbx; void * FwPlumber::m_pIntranetAppCLoopbackSd
0x1800e03b5  mov     rcx, cs:?m_pNullSID@FwPlumber@@3PEAXEA; hMem
0x1800e03bc  test    rcx, rcx
0x1800e03bf  jz      short loc_1800E03CE
0x1800e03c1  call    cs:__imp_LocalFree
0x1800e03c7  mov     cs:?m_pNullSID@FwPlumber@@3PEAXEA, rbx; void * FwPlumber::m_pNullSID
0x1800e03ce  mov     rdx, cs:?LOMProviderCtxtID@FwPlumber@@3_KA; id
0x1800e03d5  test    rdx, rdx
0x1800e03d8  jz      short loc_1800E03E7
0x1800e03da  mov     rcx, cs:engineHandle; engineHandle
0x1800e03e1  call    cs:__imp_FwpmProviderContextDeleteById0
0x1800e03e7  mov     rdx, cs:?LSMProviderCtxtID@FwPlumber@@3_KA; id
0x1800e03ee  test    rdx, rdx
0x1800e03f1  jz      short loc_1800E0400
0x1800e03f3  mov     rcx, cs:engineHandle; engineHandle
0x1800e03fa  call    cs:__imp_FwpmProviderContextDeleteById0
0x1800e0400  mov     rdx, cs:?PolicySilentModeProviderCtxtID@FwPlumber@@3_KA; id
0x1800e0407  test    rdx, rdx
0x1800e040a  jz      short loc_1800E0419
0x1800e040c  mov     rcx, cs:engineHandle; engineHandle
0x1800e0413  call    cs:__imp_FwpmProviderContextDeleteById0
0x1800e0419  mov     rdx, cs:?QuarantineProviderCtxtID@FwPlumber@@3_KA; id
0x1800e0420  test    rdx, rdx
0x1800e0423  jz      short loc_1800E0432
0x1800e0425  mov     rcx, cs:engineHandle; engineHandle
0x1800e042c  call    cs:__imp_FwpmProviderContextDeleteById0
0x1800e0432  mov     rdx, cs:?BootProviderCtxtID@FwPlumber@@3_KA; id
0x1800e0439  test    rdx, rdx
0x1800e043c  jz      short loc_1800E044B
0x1800e043e  mov     rcx, cs:engineHandle; engineHandle
0x1800e0445  call    cs:__imp_FwpmProviderContextDeleteById0
0x1800e044b  mov     rdx, cs:?WshProviderCtxtID@FwPlumber@@3_KA; id
0x1800e0452  test    rdx, rdx
0x1800e0455  jz      short loc_1800E0464
0x1800e0457  mov     rcx, cs:engineHandle; engineHandle
0x1800e045e  call    cs:__imp_FwpmProviderContextDeleteById0
0x1800e0464  mov     rdx, cs:?QueryUserProviderCtxtID@FwPlumber@@3_KA; id
0x1800e046b  test    rdx, rdx
0x1800e046e  jz      short loc_1800E047D
0x1800e0470  mov     rcx, cs:engineHandle; engineHandle
0x1800e0477  call    cs:__imp_FwpmProviderContextDeleteById0
0x1800e047d  mov     rdx, cs:?AppCLoopbackProviderCtxtID@FwPlumber@@3_KA; id
0x1800e0484  test    rdx, rdx
0x1800e0487  jz      short loc_1800E0496
0x1800e0489  mov     rcx, cs:engineHandle; engineHandle
0x1800e0490  call    cs:__imp_FwpmProviderContextDeleteById0
0x1800e0496  mov     rdx, cs:?StealthProviderCtxtID@FwPlumber@@3_KA; id
0x1800e049d  test    rdx, rdx
0x1800e04a0  jz      short loc_1800E04AF
0x1800e04a2  mov     rcx, cs:engineHandle; engineHandle
0x1800e04a9  call    cs:__imp_FwpmProviderContextDeleteById0
0x1800e04af  cmp     cs:dword_180131DA0, ebx
0x1800e04b5  jz      short loc_1800E04FC
0x1800e04b7  cmp     cs:?gvMipsInitialized@@3HA, 1; int gvMipsInitialized
0x1800e04be  jz      short loc_1800E04C5
0x1800e04c0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800e04c5  cmp     cs:?gvBfeEngineHandle@@3PEAXEA, rbx; void * gvBfeEngineHandle
0x1800e04cc  jnz     short loc_1800E04D3
0x1800e04ce  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800e04d3  call    ?IpsecShutdownInternal@@YAKXZ; IpsecShutdownInternal(void)
0x1800e04d8  mov     r9d, 1; int
0x1800e04de  mov     [rsp+38h+var_18], ebx; int
0x1800e04e2  xor     r8d, r8d; unsigned int
0x1800e04e5  lea     rcx, aIpsecapishutdo; "IpsecApiShutdown"
0x1800e04ec  mov     edx, 10Ah; unsigned int
0x1800e04f1  call    ?IpsReturnError@@YAKPEBDKKHH@Z; IpsReturnError(char const *,ulong,ulong,int,int)
0x1800e04f6  mov     cs:dword_180131DA0, ebx
0x1800e04fc  mov     rcx, cs:g_Provider
0x1800e0503  test    rcx, rcx
0x1800e0506  jz      short loc_1800E051B
0x1800e0508  xor     r9d, r9d
0x1800e050b  lea     rdx, MPS_SVC_BFE_EngineClose_Enter
0x1800e0512  xor     r8d, r8d
0x1800e0515  call    cs:__imp_EtwEventWrite
0x1800e051b  mov     rcx, cs:engineHandle; engineHandle
0x1800e0522  call    cs:__imp_FwpmEngineClose0
0x1800e0528  mov     rcx, cs:g_Provider
0x1800e052f  test    rcx, rcx
0x1800e0532  jz      short loc_1800E0547
0x1800e0534  xor     r9d, r9d
0x1800e0537  lea     rdx, MPS_SVC_BFE_EngineClose_Exit
0x1800e053e  xor     r8d, r8d
0x1800e0541  call    cs:__imp_EtwEventWrite
0x1800e0547  mov     rcx, cs:qword_180131E38; this
0x1800e054e  mov     cs:engineHandle, rbx
0x1800e0555  test    rcx, rcx
0x1800e0558  jz      short loc_1800E0566
0x1800e055a  call    ??_GFILTER_HANDLE@FwPlumber@@QEAAPEAXI@Z; FwPlumber::FILTER_HANDLE::`scalar deleting destructor'(uint)
0x1800e055f  mov     cs:qword_180131E38, rbx
0x1800e0566  mov     rcx, cs:qword_180131DF0; this
0x1800e056d  test    rcx, rcx
0x1800e0570  jz      short loc_1800E0584
0x1800e0572  call    ??_GFILTER_HANDLE@FwPlumber@@QEAAPEAXI@Z; FwPlumber::FILTER_HANDLE::`scalar deleting destructor'(uint)
0x1800e0577  mov     cs:qword_180131DF0, rbx
0x1800e057e  mov     cs:dword_180131D9C, ebx
0x1800e0584  lea     rcx, ?g_FwFilterError@@3U_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST@@A; struct _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *
0x1800e058b  call    ?FwPlumberFreeTrackObjError@@YAXPEAU_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST@@@Z; FwPlumberFreeTrackObjError(_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *)
0x1800e0590  lea     rcx, ?g_FwCalloutError@@3U_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST@@A; struct _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *
0x1800e0597  call    ?FwPlumberFreeTrackObjError@@YAXPEAU_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST@@@Z; FwPlumberFreeTrackObjError(_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *)
0x1800e059c  lea     rcx, ?g_FwProvCtxError@@3U_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST@@A; struct _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *
0x1800e05a3  add     rsp, 30h
0x1800e05a7  pop     rbx
0x1800e05a8  jmp     ?FwPlumberFreeTrackObjError@@YAXPEAU_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST@@@Z; FwPlumberFreeTrackObjError(_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *)
```
