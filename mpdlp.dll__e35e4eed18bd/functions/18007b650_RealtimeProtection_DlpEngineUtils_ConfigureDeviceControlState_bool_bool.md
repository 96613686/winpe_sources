# RealtimeProtection::DlpEngineUtils::ConfigureDeviceControlState(bool,bool)

- ea: `0x18007b650`
- end: `0x18007b9b2`
- name: `?ConfigureDeviceControlState@DlpEngineUtils@RealtimeProtection@@YAJ_N0@Z`
- size: `866`
- prototype: `__int64 __fastcall(RealtimeProtection::DlpEngineUtils *__hidden this, bool, bool)`
- caller_count: `4`
- callee_count: `14`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18007a790`
- `0x18019ad7c`
- `0x18019ff94`
- `0x1801a0eec`

## callees

- `0x180027a90`
- `0x18003ee0c`
- `0x180068cd0`
- `0x18007b650`
- `0x1800809d0`
- `0x180088d30`
- `0x1800890e0`
- `0x180089510`
- `0x1800a7df0`
- `0x1800ab660`
- `0x1800b809c`
- `0x18010cb40`
- `0x18010ce44`
- `0x18023a310`

## import_xrefs

- `MpClient!MpConfigSetValue` at `0x18007b854`
- `MpClient!MpConfigSetValue` at `0x18007b854`
- `MpClient!MpConfigClose` at `0x18007b7a7`
- `MpClient!MpConfigClose` at `0x18007b8f5`
- `MpClient!MpConfigClose` at `0x18007b7a7`
- `MpClient!MpConfigClose` at `0x18007b8f5`
- `MpClient!MpConfigDelValue` at `0x18007b97d`
- `MpClient!MpConfigDelValue` at `0x18007b97d`
- `MpClient!MpConfigOpen` at `0x18007b766`
- `MpClient!MpConfigOpen` at `0x18007b766`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RealtimeProtection::DlpEngineUtils::ConfigureDeviceControlState(
        RealtimeProtection::DlpEngineUtils *this,
        __int64 a2)
{
  char v2; // r12
  char v3; // r15
  __int64 v4; // rdx
  char BoolValue; // r14
  RealtimeProtection::DlpPlugin *v6; // rcx
  char v7; // si
  RealtimeProtection::CDlpFilterManager *FilterManager; // rax
  unsigned int v9; // edx
  int v10; // eax
  _BYTE *v11; // rdx
  int ValueDword; // edi
  __int64 v13; // r8
  __int64 v14; // r9
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  volatile signed __int32 *v18; // rbx
  RealtimeProtection::DlpPlugin *v19; // rcx
  struct RealtimeProtection::CPluginWorkItemQueue *PluginWorkItemQueue; // rax
  _BYTE v21[32]; // [rsp+0h] [rbp-78h] BYREF
  volatile signed __int32 *v22; // [rsp+30h] [rbp-48h] BYREF
  const std::exception *v23; // [rsp+38h] [rbp-40h] BYREF
  __int64 v24; // [rsp+40h] [rbp-38h] BYREF
  int v25; // [rsp+48h] [rbp-30h] BYREF
  int v26; // [rsp+4Ch] [rbp-2Ch] BYREF

  v2 = a2;
  v3 = (char)this;
  BoolValue = Dlp::FeatureControl::GetBoolValue(167, a2);
  if ( !BoolValue && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 223, &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids);
  v7 = Dlp::FeatureControl::GetBoolValue(160, v4);
  if ( !v7 )
  {
    v6 = (RealtimeProtection::DlpPlugin *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 224, &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids);
  }
  FilterManager = RealtimeProtection::DlpPlugin::GetFilterManager(v6);
  if ( FilterManager )
  {
    v9 = BoolValue && v7;
    v10 = RealtimeProtection::CDlpFilterManager::SetAllowDeviceControlUsage(FilterManager, v9);
    if ( v10 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        225,
        &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
        (unsigned int)v10);
  }
  v24 = 0;
  ValueDword = MpConfigOpen(L"Features", &v24);
  if ( ValueDword < 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v16 = 226;
LABEL_22:
      WPP_SF_d(v15[2], v16, &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids, (unsigned int)ValueDword);
      goto LABEL_23;
    }
    goto LABEL_23;
  }
  if ( BoolValue && v7 && !v3 )
  {
    LODWORD(v22) = 0;
    v25 = 0;
    ValueDword = MpConfigGetValueDword(v24, L"ForceDeviceControlEnabled", &v22, &v25);
    if ( ValueDword < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v16 = 228;
        goto LABEL_22;
      }
LABEL_23:
      if ( v24 )
        MpConfigClose(v24, v11, v13, v14);
      return (unsigned int)ValueDword;
    }
    if ( (_DWORD)v22 != 1 || v2 )
    {
      v26 = 1;
      ValueDword = MpConfigSetValue(v24, L"ForceDeviceControlEnabled", 1, 4, &v26);
      if ( ValueDword < 0 )
      {
        v15 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v16 = 229;
          goto LABEL_22;
        }
        goto LABEL_23;
      }
      try
      {
        v18 = (volatile signed __int32 *)operator new(0x50u);
        memset((void *)v18, 0, 0x50u);
        PluginWorkItemQueue = RealtimeProtection::DlpPlugin::GetPluginWorkItemQueue(v19);
        RealtimeProtection::CMpPluginWorkItemBase::CMpPluginWorkItemBase(v18, PluginWorkItemQueue, 36);
        *(_QWORD *)v18 = &RealtimeProtection::CDlpTriggerDeviceRefreshWorkItem::`vftable';
        *((_DWORD *)v18 + 18) = 10;
        *((_DWORD *)v18 + 19) = 5000;
        _InterlockedIncrement(v18 + 2);
        v22 = v18;
        RealtimeProtection::CMpPluginWorkItemBase::PrioritizedDispatchJob(v18, 5);
        CommonUtil::AutoRef<RealtimeProtection::CDlpHandleFilterReconnectWorkItem>::~AutoRef<RealtimeProtection::CDlpHandleFilterReconnectWorkItem>(&v22);
      }
      catch ( const std::exception *v23 )
      {
        CommonUtil::HrFromStdException(v23, (const struct std::exception *)v21);
      }
      catch ( ... )
      {
        v11 = v21;
        LODWORD(v22) = -2147467259;
        ValueDword = (int)v22;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            230,
            &WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids,
            (unsigned int)v22);
        goto LABEL_23;
      }
    }
  }
  else
  {
    ValueDword = MpConfigDelValue(v24, L"ForceDeviceControlEnabled", v13, v14);
    if ( ValueDword < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v16 = 227;
        goto LABEL_22;
      }
      goto LABEL_23;
    }
  }
  if ( v24 )
    MpConfigClose(v24, v11, v13, v14);
  return 0;
}

```

## disassembly

```asm
0x18007b650  mov     [rsp+arg_0], rbx
0x18007b655  mov     [rsp+arg_8], rsi
0x18007b65a  mov     [rsp+arg_10], rdi
0x18007b65f  push    r12
0x18007b661  push    r14
0x18007b663  push    r15
0x18007b665  sub     rsp, 60h
0x18007b669  mov     rax, cs:__security_cookie
0x18007b670  xor     rax, rsp
0x18007b673  mov     [rsp+78h+var_28], rax
0x18007b678  mov     r12b, dl
0x18007b67b  mov     r15b, cl
0x18007b67e  mov     ecx, 0A7h
0x18007b683  call    ?GetBoolValue@FeatureControl@Dlp@@YA_NW4FeatureControlEnum@@@Z; Dlp::FeatureControl::GetBoolValue(FeatureControlEnum)
0x18007b688  mov     r14b, al
0x18007b68b  test    al, al
0x18007b68d  jnz     short loc_18007B6BF
0x18007b68f  lea     rbx, WPP_GLOBAL_Control
0x18007b696  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b69d  cmp     rcx, rbx
0x18007b6a0  jz      short loc_18007B6C6
0x18007b6a2  test    byte ptr [rcx+1Ch], 2
0x18007b6a6  jz      short loc_18007B6C6
0x18007b6a8  mov     edx, 0DFh
0x18007b6ad  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18007b6b4  mov     rcx, [rcx+10h]
0x18007b6b8  call    WPP_SF_
0x18007b6bd  jmp     short loc_18007B6C6
0x18007b6bf  lea     rbx, WPP_GLOBAL_Control
0x18007b6c6  mov     ecx, 0A0h
0x18007b6cb  call    ?GetBoolValue@FeatureControl@Dlp@@YA_NW4FeatureControlEnum@@@Z; Dlp::FeatureControl::GetBoolValue(FeatureControlEnum)
0x18007b6d0  mov     sil, al
0x18007b6d3  test    al, al
0x18007b6d5  jnz     short loc_18007B6FE
0x18007b6d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b6de  cmp     rcx, rbx
0x18007b6e1  jz      short loc_18007B6FE
0x18007b6e3  test    byte ptr [rcx+1Ch], 2
0x18007b6e7  jz      short loc_18007B6FE
0x18007b6e9  mov     edx, 0E0h
0x18007b6ee  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18007b6f5  mov     rcx, [rcx+10h]
0x18007b6f9  call    WPP_SF_
0x18007b6fe  call    ?GetFilterManager@DlpPlugin@RealtimeProtection@@YAPEAVCDlpFilterManager@2@XZ; RealtimeProtection::DlpPlugin::GetFilterManager(void)
0x18007b703  test    rax, rax
0x18007b706  jz      short loc_18007B751
0x18007b708  test    r14b, r14b
0x18007b70b  jz      short loc_18007B719
0x18007b70d  test    sil, sil
0x18007b710  jz      short loc_18007B719
0x18007b712  mov     edx, 1
0x18007b717  jmp     short loc_18007B71B
0x18007b719  xor     edx, edx; unsigned int
0x18007b71b  mov     rcx, rax; this
0x18007b71e  call    ?SetAllowDeviceControlUsage@CDlpFilterManager@RealtimeProtection@@QEAAJK@Z; RealtimeProtection::CDlpFilterManager::SetAllowDeviceControlUsage(ulong)
0x18007b723  test    eax, eax
0x18007b725  jns     short loc_18007B751
0x18007b727  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b72e  cmp     rcx, rbx
0x18007b731  jz      short loc_18007B751
0x18007b733  test    byte ptr [rcx+1Ch], 2
0x18007b737  jz      short loc_18007B751
0x18007b739  mov     edx, 0E1h
0x18007b73e  mov     r9d, eax
0x18007b741  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18007b748  mov     rcx, [rcx+10h]
0x18007b74c  call    WPP_SF_d
0x18007b751  mov     [rsp+78h+var_38], 0
0x18007b75a  lea     rdx, [rsp+78h+var_38]
0x18007b75f  lea     rcx, aFeatures_0; "Features"
0x18007b766  call    cs:__imp_MpConfigOpen
0x18007b76c  mov     edi, eax
0x18007b76e  test    eax, eax
0x18007b770  jns     short loc_18007B7B4
0x18007b772  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b779  cmp     rcx, rbx
0x18007b77c  jz      short loc_18007B79D
0x18007b77e  test    byte ptr [rcx+1Ch], 1
0x18007b782  jz      short loc_18007B79D
0x18007b784  mov     edx, 0E2h
0x18007b789  mov     r9d, edi
0x18007b78c  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18007b793  mov     rcx, [rcx+10h]
0x18007b797  call    WPP_SF_d
0x18007b79c  nop
0x18007b79d  mov     rcx, [rsp+78h+var_38]
0x18007b7a2  test    rcx, rcx
0x18007b7a5  jz      short loc_18007B7AD
0x18007b7a7  call    cs:__imp_MpConfigClose
0x18007b7ad  mov     eax, edi
0x18007b7af  jmp     loc_18007B8FD
0x18007b7b4  test    r14b, r14b
0x18007b7b7  jz      loc_18007B971
0x18007b7bd  test    sil, sil
0x18007b7c0  jz      loc_18007B971
0x18007b7c6  test    r15b, r15b
0x18007b7c9  jnz     loc_18007B971
0x18007b7cf  mov     dword ptr [rsp+78h+var_48], 0
0x18007b7d7  mov     [rsp+78h+var_30], 0
0x18007b7df  lea     r9, [rsp+78h+var_30]
0x18007b7e4  lea     r8, [rsp+78h+var_48]
0x18007b7e9  lea     rdx, aForcedevicecon; "ForceDeviceControlEnabled"
0x18007b7f0  mov     rcx, [rsp+78h+var_38]
0x18007b7f5  call    MpConfigGetValueDword
0x18007b7fa  mov     edi, eax
0x18007b7fc  test    eax, eax
0x18007b7fe  jns     short loc_18007B81C
0x18007b800  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b807  cmp     rcx, rbx
0x18007b80a  jz      short loc_18007B79D
0x18007b80c  test    byte ptr [rcx+1Ch], 1
0x18007b810  jz      short loc_18007B79D
0x18007b812  mov     edx, 0E4h
0x18007b817  jmp     loc_18007B789
0x18007b81c  cmp     dword ptr [rsp+78h+var_48], 1
0x18007b821  jnz     short loc_18007B82C
0x18007b823  test    r12b, r12b
0x18007b826  jz      loc_18007B8EB
0x18007b82c  mov     [rsp+78h+var_2C], 1
0x18007b834  lea     rax, [rsp+78h+var_2C]
0x18007b839  mov     [rsp+78h+var_58], rax
0x18007b83e  mov     r9d, 4
0x18007b844  lea     r8d, [r9-3]
0x18007b848  lea     rdx, aForcedevicecon; "ForceDeviceControlEnabled"
0x18007b84f  mov     rcx, [rsp+78h+var_38]
0x18007b854  call    cs:__imp_MpConfigSetValue
0x18007b85a  mov     edi, eax
0x18007b85c  test    eax, eax
0x18007b85e  jns     short loc_18007B884
0x18007b860  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b867  cmp     rcx, rbx
0x18007b86a  jz      loc_18007B79D
0x18007b870  test    byte ptr [rcx+1Ch], 1
0x18007b874  jz      loc_18007B79D
0x18007b87a  mov     edx, 0E5h
0x18007b87f  jmp     loc_18007B789
0x18007b884  mov     edi, 50h ; 'P'
0x18007b889  mov     ecx, edi; Size
0x18007b88b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007b890  mov     rbx, rax
0x18007b893  mov     r8d, edi; Size
0x18007b896  xor     edx, edx; Val
0x18007b898  mov     rcx, rax; void *
0x18007b89b  call    memset
0x18007b8a0  call    ?GetPluginWorkItemQueue@DlpPlugin@RealtimeProtection@@YAPEAVCPluginWorkItemQueue@2@XZ; RealtimeProtection::DlpPlugin::GetPluginWorkItemQueue(void)
0x18007b8a5  lea     r8d, [rdi-2Ch]
0x18007b8a9  mov     rdx, rax
0x18007b8ac  mov     rcx, rbx
0x18007b8af  call    ??0CMpPluginWorkItemBase@RealtimeProtection@@QEAA@PEAVCPluginWorkItemQueue@1@W4WorkItemTypeIndex@1@@Z; RealtimeProtection::CMpPluginWorkItemBase::CMpPluginWorkItemBase(RealtimeProtection::CPluginWorkItemQueue *,RealtimeProtection::WorkItemTypeIndex)
0x18007b8b4  lea     rax, ??_7CDlpTriggerDeviceRefreshWorkItem@RealtimeProtection@@6B@; const RealtimeProtection::CDlpTriggerDeviceRefreshWorkItem::`vftable'
0x18007b8bb  mov     [rbx], rax
0x18007b8be  mov     dword ptr [rbx+48h], 0Ah
0x18007b8c5  mov     dword ptr [rbx+4Ch], 1388h
0x18007b8cc  lock inc dword ptr [rbx+8]
0x18007b8d0  mov     [rsp+78h+var_48], rbx
0x18007b8d5  lea     edx, [rdi-4Bh]
0x18007b8d8  mov     rcx, rbx
0x18007b8db  call    ?PrioritizedDispatchJob@CMpPluginWorkItemBase@RealtimeProtection@@UEAAXW4tagMP_THREAD_POOL_PRIORITY@@@Z; RealtimeProtection::CMpPluginWorkItemBase::PrioritizedDispatchJob(tagMP_THREAD_POOL_PRIORITY)
0x18007b8e0  lea     rcx, [rsp+78h+var_48]
0x18007b8e5  call    ??1?$AutoRef@VCDlpHandleFilterReconnectWorkItem@RealtimeProtection@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<RealtimeProtection::CDlpHandleFilterReconnectWorkItem>::~AutoRef<RealtimeProtection::CDlpHandleFilterReconnectWorkItem>(void)
0x18007b8ea  nop
0x18007b8eb  mov     rcx, [rsp+78h+var_38]
0x18007b8f0  test    rcx, rcx
0x18007b8f3  jz      short loc_18007B8FB
0x18007b8f5  call    cs:__imp_MpConfigClose
0x18007b8fb  xor     eax, eax
0x18007b8fd  mov     rcx, [rsp+78h+var_28]
0x18007b902  xor     rcx, rsp; StackCookie
0x18007b905  call    __security_check_cookie
0x18007b90a  lea     r11, [rsp+78h+var_18]
0x18007b90f  mov     rbx, [r11+20h]
0x18007b913  mov     rsi, [r11+28h]
0x18007b917  mov     rdi, [r11+30h]
0x18007b91b  mov     rsp, r11
0x18007b91e  pop     r15
0x18007b920  pop     r14
0x18007b922  pop     r12
0x18007b924  retn
0x18007b925  mov     edi, dword ptr [rsp+78h+var_48]
0x18007b929  test    edi, edi
0x18007b92b  jns     short loc_18007B8EB
0x18007b92d  jmp     short loc_18007B933
0x18007b92f  mov     edi, dword ptr [rsp+78h+var_48]
0x18007b933  lea     rbx, WPP_GLOBAL_Control
0x18007b93a  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b941  cmp     rcx, rbx
0x18007b944  jz      loc_18007B79D
0x18007b94a  test    byte ptr [rcx+1Ch], 1
0x18007b94e  jz      loc_18007B79D
0x18007b954  mov     edx, 0E6h
0x18007b959  mov     r9d, edi
0x18007b95c  lea     r8, WPP_3f83082974eb3d6f01ade477a19bf757_Traceguids
0x18007b963  mov     rcx, [rcx+10h]
0x18007b967  call    WPP_SF_d
0x18007b96c  jmp     loc_18007B79D
0x18007b971  lea     rdx, aForcedevicecon; "ForceDeviceControlEnabled"
0x18007b978  mov     rcx, [rsp+78h+var_38]
0x18007b97d  call    cs:__imp_MpConfigDelValue
0x18007b983  mov     edi, eax
0x18007b985  test    eax, eax
0x18007b987  jns     loc_18007B8EB
0x18007b98d  mov     rcx, cs:WPP_GLOBAL_Control
0x18007b994  cmp     rcx, rbx
0x18007b997  jz      loc_18007B79D
0x18007b99d  test    byte ptr [rcx+1Ch], 1
0x18007b9a1  jz      loc_18007B79D
0x18007b9a7  mov     edx, 0E3h
0x18007b9ac  jmp     loc_18007B789
```
