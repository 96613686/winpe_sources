# FwPlumber::Shutdown(void)

- ea: `0x1800e7198`
- end: `0x1800e745f`
- name: `?Shutdown@FwPlumber@@YAXXZ`
- size: `711`
- prototype: `void __fastcall(FwPlumber *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800e74cc`

## callees

- `0x1800089bc`
- `0x1800192e0`
- `0x18001f5d0`
- `0x18004f4ac`
- `0x1800d9b08`
- `0x1800e6770`
- `0x1800e7198`

## import_xrefs

- `ntdll!EtwEventWrite` at `0x1800e73b5`
- `ntdll!EtwEventWrite` at `0x1800e73ed`
- `ntdll!EtwEventWrite` at `0x1800e73b5`
- `ntdll!EtwEventWrite` at `0x1800e73ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800e71e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800e7206`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800e7225`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800e71e7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800e7206`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800e7225`
- `fwpuclnt!FwpmEngineClose0` at `0x1800e73c8`
- `fwpuclnt!FwpmEngineClose0` at `0x1800e73c8`
- `fwpuclnt!FwpmProviderContextDeleteById0` at `0x1800e724b`
- `fwpuclnt!FwpmProviderContextDeleteById0` at `0x1800e726a`
- `fwpuclnt!FwpmProviderContextDeleteById0` at `0x1800e7289`
- `fwpuclnt!FwpmProviderContextDeleteById0` at `0x1800e72a8`
- `fwpuclnt!FwpmProviderContextDeleteById0` at `0x1800e72c7`
- `fwpuclnt!FwpmProviderContextDeleteById0` at `0x1800e72e6`
- `fwpuclnt!FwpmProviderContextDeleteById0` at `0x1800e7305`
- `fwpuclnt!FwpmProviderContextDeleteById0` at `0x1800e7324`
- `fwpuclnt!FwpmProviderContextDeleteById0` at `0x1800e7343`
- `fwpuclnt!FwpmProviderContextDeleteById0` at `0x1800e724b`
- `fwpuclnt!FwpmProviderContextDeleteById0` at `0x1800e726a`
- `fwpuclnt!FwpmProviderContextDeleteById0` at `0x1800e7289`
- `fwpuclnt!FwpmProviderContextDeleteById0` at `0x1800e72a8`
- `fwpuclnt!FwpmProviderContextDeleteById0` at `0x1800e72c7`
- `fwpuclnt!FwpmProviderContextDeleteById0` at `0x1800e72e6`
- `fwpuclnt!FwpmProviderContextDeleteById0` at `0x1800e7305`
- `fwpuclnt!FwpmProviderContextDeleteById0` at `0x1800e7324`
- `fwpuclnt!FwpmProviderContextDeleteById0` at `0x1800e7343`

## pseudocode

```c
void __fastcall FwPlumber::Shutdown(FwPlumber *this)
{
  unsigned int v1; // edx

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 8) != 0 )
    WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 116, WPP_2afde9bce9f33b7e8b7f061cee2eaad7_Traceguids);
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
    if ( FwPlumber::StealthProviderCtxtID )
      FwpmProviderContextDeleteById0(engineHandle, FwPlumber::StealthProviderCtxtID);
    if ( dword_180137F38 )
    {
      if ( gvMipsInitialized != 1 )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      if ( !gvBfeEngineHandle )
        MicrosoftTelemetryAssertTriggeredNoArgs();
      IpsecShutdownInternal();
      IpsReturnError("IpsecApiShutdown", 0xE0u, 0, 1, 0);
      dword_180137F38 = 0;
    }
    if ( g_Provider )
      EtwEventWrite(g_Provider, MPS_SVC_BFE_EngineClose_Enter, 0, 0);
    FwpmEngineClose0(engineHandle);
    if ( g_Provider )
      EtwEventWrite(g_Provider, MPS_SVC_BFE_EngineClose_Exit, 0, 0);
    engineHandle = 0;
    if ( qword_180137FD0 )
    {
      FwPlumber::FILTER_HANDLE::`scalar deleting destructor'(qword_180137FD0, v1);
      qword_180137FD0 = 0;
    }
    if ( qword_180137F80 )
    {
      FwPlumber::FILTER_HANDLE::`scalar deleting destructor'(qword_180137F80, v1);
      qword_180137F80 = 0;
      dword_180137F2C = 0;
    }
  }
  FwPlumberFreeTrackObjError((struct _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *)&g_FwFilterError);
  FwPlumberFreeTrackObjError((struct _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *)&g_FwCalloutError);
  FwPlumberFreeTrackObjError((struct _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *)&g_FwProvCtxError);
}

```

## disassembly

```asm
0x1800e7198  push    rbx
0x1800e719a  sub     rsp, 30h
0x1800e719e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e71a5  lea     rax, WPP_GLOBAL_Control
0x1800e71ac  cmp     rcx, rax
0x1800e71af  jz      short loc_1800E71CC
0x1800e71b1  test    byte ptr [rcx+1Ch], 8
0x1800e71b5  jz      short loc_1800E71CC
0x1800e71b7  mov     rcx, [rcx+10h]
0x1800e71bb  lea     r8, WPP_2afde9bce9f33b7e8b7f061cee2eaad7_Traceguids
0x1800e71c2  mov     edx, 74h ; 't'
0x1800e71c7  call    WPP_SF_
0x1800e71cc  xor     ebx, ebx
0x1800e71ce  cmp     cs:engineHandle, rbx
0x1800e71d5  jz      loc_1800E7436
0x1800e71db  mov     rcx, cs:?m_pAllAppContainersSd@FwPlumber@@3PEAXEA; hMem
0x1800e71e2  test    rcx, rcx
0x1800e71e5  jz      short loc_1800E71FA
0x1800e71e7  call    cs:__imp_LocalFree
0x1800e71ee  nop     dword ptr [rax+rax+00h]
0x1800e71f3  mov     cs:?m_pAllAppContainersSd@FwPlumber@@3PEAXEA, rbx; void * FwPlumber::m_pAllAppContainersSd
0x1800e71fa  mov     rcx, cs:?m_pIntranetAppCLoopbackSd@FwPlumber@@3PEAXEA; hMem
0x1800e7201  test    rcx, rcx
0x1800e7204  jz      short loc_1800E7219
0x1800e7206  call    cs:__imp_LocalFree
0x1800e720d  nop     dword ptr [rax+rax+00h]
0x1800e7212  mov     cs:?m_pIntranetAppCLoopbackSd@FwPlumber@@3PEAXEA, rbx; void * FwPlumber::m_pIntranetAppCLoopbackSd
0x1800e7219  mov     rcx, cs:?m_pNullSID@FwPlumber@@3PEAXEA; hMem
0x1800e7220  test    rcx, rcx
0x1800e7223  jz      short loc_1800E7238
0x1800e7225  call    cs:__imp_LocalFree
0x1800e722c  nop     dword ptr [rax+rax+00h]
0x1800e7231  mov     cs:?m_pNullSID@FwPlumber@@3PEAXEA, rbx; void * FwPlumber::m_pNullSID
0x1800e7238  mov     rdx, cs:?LOMProviderCtxtID@FwPlumber@@3_KA; id
0x1800e723f  test    rdx, rdx
0x1800e7242  jz      short loc_1800E7257
0x1800e7244  mov     rcx, cs:engineHandle; engineHandle
0x1800e724b  call    cs:__imp_FwpmProviderContextDeleteById0
0x1800e7252  nop     dword ptr [rax+rax+00h]
0x1800e7257  mov     rdx, cs:?LSMProviderCtxtID@FwPlumber@@3_KA; id
0x1800e725e  test    rdx, rdx
0x1800e7261  jz      short loc_1800E7276
0x1800e7263  mov     rcx, cs:engineHandle; engineHandle
0x1800e726a  call    cs:__imp_FwpmProviderContextDeleteById0
0x1800e7271  nop     dword ptr [rax+rax+00h]
0x1800e7276  mov     rdx, cs:?PolicySilentModeProviderCtxtID@FwPlumber@@3_KA; id
0x1800e727d  test    rdx, rdx
0x1800e7280  jz      short loc_1800E7295
0x1800e7282  mov     rcx, cs:engineHandle; engineHandle
0x1800e7289  call    cs:__imp_FwpmProviderContextDeleteById0
0x1800e7290  nop     dword ptr [rax+rax+00h]
0x1800e7295  mov     rdx, cs:?QuarantineProviderCtxtID@FwPlumber@@3_KA; id
0x1800e729c  test    rdx, rdx
0x1800e729f  jz      short loc_1800E72B4
0x1800e72a1  mov     rcx, cs:engineHandle; engineHandle
0x1800e72a8  call    cs:__imp_FwpmProviderContextDeleteById0
0x1800e72af  nop     dword ptr [rax+rax+00h]
0x1800e72b4  mov     rdx, cs:?BootProviderCtxtID@FwPlumber@@3_KA; id
0x1800e72bb  test    rdx, rdx
0x1800e72be  jz      short loc_1800E72D3
0x1800e72c0  mov     rcx, cs:engineHandle; engineHandle
0x1800e72c7  call    cs:__imp_FwpmProviderContextDeleteById0
0x1800e72ce  nop     dword ptr [rax+rax+00h]
0x1800e72d3  mov     rdx, cs:?WshProviderCtxtID@FwPlumber@@3_KA; id
0x1800e72da  test    rdx, rdx
0x1800e72dd  jz      short loc_1800E72F2
0x1800e72df  mov     rcx, cs:engineHandle; engineHandle
0x1800e72e6  call    cs:__imp_FwpmProviderContextDeleteById0
0x1800e72ed  nop     dword ptr [rax+rax+00h]
0x1800e72f2  mov     rdx, cs:?QueryUserProviderCtxtID@FwPlumber@@3_KA; id
0x1800e72f9  test    rdx, rdx
0x1800e72fc  jz      short loc_1800E7311
0x1800e72fe  mov     rcx, cs:engineHandle; engineHandle
0x1800e7305  call    cs:__imp_FwpmProviderContextDeleteById0
0x1800e730c  nop     dword ptr [rax+rax+00h]
0x1800e7311  mov     rdx, cs:?AppCLoopbackProviderCtxtID@FwPlumber@@3_KA; id
0x1800e7318  test    rdx, rdx
0x1800e731b  jz      short loc_1800E7330
0x1800e731d  mov     rcx, cs:engineHandle; engineHandle
0x1800e7324  call    cs:__imp_FwpmProviderContextDeleteById0
0x1800e732b  nop     dword ptr [rax+rax+00h]
0x1800e7330  mov     rdx, cs:?StealthProviderCtxtID@FwPlumber@@3_KA; id
0x1800e7337  test    rdx, rdx
0x1800e733a  jz      short loc_1800E734F
0x1800e733c  mov     rcx, cs:engineHandle; engineHandle
0x1800e7343  call    cs:__imp_FwpmProviderContextDeleteById0
0x1800e734a  nop     dword ptr [rax+rax+00h]
0x1800e734f  cmp     cs:dword_180137F38, ebx
0x1800e7355  jz      short loc_1800E739C
0x1800e7357  cmp     cs:?gvMipsInitialized@@3HA, 1; int gvMipsInitialized
0x1800e735e  jz      short loc_1800E7365
0x1800e7360  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "gvMipsInitialized == TRUE")
0x1800e7365  cmp     cs:?gvBfeEngineHandle@@3PEAXEA, rbx; void * gvBfeEngineHandle
0x1800e736c  jnz     short loc_1800E7373
0x1800e736e  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "gvBfeEngineHandle != NULL")
0x1800e7373  call    ?IpsecShutdownInternal@@YAKXZ; IpsecShutdownInternal(void)
0x1800e7378  mov     r9d, 1; int
0x1800e737e  mov     [rsp+38h+var_18], ebx; int
0x1800e7382  xor     r8d, r8d; unsigned int
0x1800e7385  lea     rcx, aIpsecapishutdo; "IpsecApiShutdown"
0x1800e738c  mov     edx, 0E0h; unsigned int
0x1800e7391  call    ?IpsReturnError@@YAKPEBDKKHH@Z; IpsReturnError(char const *,ulong,ulong,int,int)
0x1800e7396  mov     cs:dword_180137F38, ebx
0x1800e739c  mov     rcx, cs:g_Provider
0x1800e73a3  test    rcx, rcx
0x1800e73a6  jz      short loc_1800E73C1
0x1800e73a8  xor     r9d, r9d
0x1800e73ab  lea     rdx, MPS_SVC_BFE_EngineClose_Enter
0x1800e73b2  xor     r8d, r8d
0x1800e73b5  call    cs:__imp_EtwEventWrite
0x1800e73bc  nop     dword ptr [rax+rax+00h]
0x1800e73c1  mov     rcx, cs:engineHandle; engineHandle
0x1800e73c8  call    cs:__imp_FwpmEngineClose0
0x1800e73cf  nop     dword ptr [rax+rax+00h]
0x1800e73d4  mov     rcx, cs:g_Provider
0x1800e73db  test    rcx, rcx
0x1800e73de  jz      short loc_1800E73F9
0x1800e73e0  xor     r9d, r9d
0x1800e73e3  lea     rdx, MPS_SVC_BFE_EngineClose_Exit
0x1800e73ea  xor     r8d, r8d
0x1800e73ed  call    cs:__imp_EtwEventWrite
0x1800e73f4  nop     dword ptr [rax+rax+00h]
0x1800e73f9  mov     rcx, cs:qword_180137FD0; this
0x1800e7400  mov     cs:engineHandle, rbx
0x1800e7407  test    rcx, rcx
0x1800e740a  jz      short loc_1800E7418
0x1800e740c  call    ??_GFILTER_HANDLE@FwPlumber@@QEAAPEAXI@Z; FwPlumber::FILTER_HANDLE::`scalar deleting destructor'(uint)
0x1800e7411  mov     cs:qword_180137FD0, rbx
0x1800e7418  mov     rcx, cs:qword_180137F80; this
0x1800e741f  test    rcx, rcx
0x1800e7422  jz      short loc_1800E7436
0x1800e7424  call    ??_GFILTER_HANDLE@FwPlumber@@QEAAPEAXI@Z; FwPlumber::FILTER_HANDLE::`scalar deleting destructor'(uint)
0x1800e7429  mov     cs:qword_180137F80, rbx
0x1800e7430  mov     cs:dword_180137F2C, ebx
0x1800e7436  lea     rcx, ?g_FwFilterError@@3U_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST@@A; struct _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *
0x1800e743d  call    ?FwPlumberFreeTrackObjError@@YAXPEAU_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST@@@Z; FwPlumberFreeTrackObjError(_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *)
0x1800e7442  lea     rcx, ?g_FwCalloutError@@3U_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST@@A; struct _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *
0x1800e7449  call    ?FwPlumberFreeTrackObjError@@YAXPEAU_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST@@@Z; FwPlumberFreeTrackObjError(_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *)
0x1800e744e  lea     rcx, ?g_FwProvCtxError@@3U_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST@@A; struct _FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *
0x1800e7455  add     rsp, 30h
0x1800e7459  pop     rbx
0x1800e745a  jmp     ?FwPlumberFreeTrackObjError@@YAXPEAU_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST@@@Z; FwPlumberFreeTrackObjError(_FW_PLUMBER_OBJ_ERROR_TRACKING_LIST *)
```
