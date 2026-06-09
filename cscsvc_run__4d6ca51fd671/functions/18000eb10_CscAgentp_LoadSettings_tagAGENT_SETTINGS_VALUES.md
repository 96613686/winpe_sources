# CscAgentp_LoadSettings(tagAGENT_SETTINGS_VALUES *)

- ea: `0x18000eb10`
- end: `0x18000ed18`
- name: `?CscAgentp_LoadSettings@@YAJPEAUtagAGENT_SETTINGS_VALUES@@@Z`
- size: `520`
- prototype: `__int64 __fastcall(struct tagAGENT_SETTINGS_VALUES *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18003de40`
- `0x18003e670`
- `0x18005ddb0`

## callees

- `0x18000eb10`
- `0x18000f204`
- `0x18002e8f4`
- `0x180089010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000ec6c`
- `OLEAUT32!__imp_VariantInit` at `0x18000ec6c`
- `OLEAUT32!__imp_VariantClear` at `0x18000eceb`
- `OLEAUT32!__imp_VariantClear` at `0x18000eceb`

## string_xrefs

- `0x18000ebf1`: `AgentSyncDelayStartSec`
- `0x18000eb6a`: `AgentFillDelayStartMin`
- `0x18000eb2a`: `AgentFillEnabled`
- `0x18000eb7f`: `AgentReconnectEnabled`
- `0x18000eba5`: `AgentReconnectDelayStartMin`
- `0x18000ebb8`: `AgentDemandReconnectDelayStartSec`
- `0x18000eb55`: `AgentFillMaxMin`
- `0x18000eb3d`: `AgentFillPeriodMin`
- `0x18000ec04`: `AgentSyncNoPinNewFiles`
- `0x18000eb92`: `AgentReconnectPeriodMin`
- `0x18000ebcb`: `AgentSyncEnabled`
- `0x18000ebde`: `AgentSyncMaxMin`

## pseudocode

```c
__int64 __fastcall CscAgentp_LoadSettings(struct tagAGENT_SETTINGS_VALUES *a1)
{
  int v1; // ebx
  unsigned int v2; // r14d
  struct COfflineFilesSettingInternal *v3; // rdi
  VARIANTARG pvarg; // [rsp+20h] [rbp-E0h] BYREF
  LPCWSTR lpString2; // [rsp+40h] [rbp-C0h]
  unsigned int *v7[29]; // [rsp+48h] [rbp-B8h]
  int v8; // [rsp+150h] [rbp+50h] BYREF
  struct COfflineFilesSettingInternal *v9; // [rsp+158h] [rbp+58h] BYREF

  v7[0] = (unsigned int *)a1;
  lpString2 = L"AgentFillEnabled";
  v1 = 0;
  v2 = 0;
  v7[1] = (unsigned int *)L"AgentFillPeriodMin";
  v7[2] = (unsigned int *)((char *)a1 + 4);
  v7[3] = (unsigned int *)L"AgentFillMaxMin";
  v7[4] = (unsigned int *)((char *)a1 + 8);
  v7[5] = (unsigned int *)L"AgentFillDelayStartMin";
  v7[6] = (unsigned int *)((char *)a1 + 12);
  v7[7] = (unsigned int *)L"AgentReconnectEnabled";
  v7[8] = (unsigned int *)((char *)a1 + 32);
  v7[9] = (unsigned int *)L"AgentReconnectPeriodMin";
  v7[10] = (unsigned int *)((char *)a1 + 36);
  v7[11] = (unsigned int *)L"AgentReconnectDelayStartMin";
  v7[12] = (unsigned int *)((char *)a1 + 40);
  v7[13] = (unsigned int *)L"AgentDemandReconnectDelayStartSec";
  v7[14] = (unsigned int *)((char *)a1 + 44);
  v7[15] = (unsigned int *)L"AgentSyncEnabled";
  v7[16] = (unsigned int *)((char *)a1 + 16);
  v7[17] = (unsigned int *)L"AgentSyncMaxMin";
  v7[18] = (unsigned int *)((char *)a1 + 20);
  v7[19] = (unsigned int *)L"AgentSyncDelayStartSec";
  v7[20] = (unsigned int *)((char *)a1 + 28);
  v7[21] = (unsigned int *)L"AgentSyncNoPinNewFiles";
  v7[22] = (unsigned int *)((char *)a1 + 24);
  v7[23] = (unsigned int *)L"PrefetchCloseHandleEnabled";
  v7[24] = (unsigned int *)((char *)a1 + 48);
  v7[25] = (unsigned int *)L"PrefetchCloseHandlePeriodSec";
  v7[26] = (unsigned int *)((char *)a1 + 52);
  v7[27] = (unsigned int *)L"PrefetchCloseHandleDelayStartSec";
  v7[28] = (unsigned int *)((char *)a1 + 56);
  do
  {
    if ( v1 < 0 )
      break;
    memset(&pvarg, 0, sizeof(pvarg));
    VariantInit(&pvarg);
    v9 = 0;
    v1 = COfflineFilesSetting::CreateInstance((LPCWSTR)v7[2 * (int)v2 - 1], &v9);
    if ( v1 >= 0 )
    {
      v3 = v9;
      v8 = 0;
      v1 = (*(__int64 (__fastcall **)(struct COfflineFilesSettingInternal *, VARIANTARG *, int *))(*(_QWORD *)v9 + 56LL))(
             v9,
             &pvarg,
             &v8);
      if ( v3 )
        (**(void (__fastcall ***)(struct COfflineFilesSettingInternal *, __int64))v3)(v3, 1);
      if ( v1 >= 0 )
      {
        v1 = CscVarUtil_ConvertVariantToDWORD(&pvarg, v7[2 * (int)v2]);
        VariantClear(&pvarg);
      }
    }
    ++v2;
  }
  while ( v2 < 0xF );
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18000eb10  mov     [rsp-8+arg_10], rbx
0x18000eb15  mov     [rsp-8+arg_18], rsi
0x18000eb1a  push    rbp
0x18000eb1b  push    rdi
0x18000eb1c  push    r14
0x18000eb1e  lea     rbp, [rsp-30h]
0x18000eb23  sub     rsp, 130h
0x18000eb2a  lea     rax, aAgentfillenabl; "AgentFillEnabled"
0x18000eb31  mov     [rsp+140h+var_F8], rcx
0x18000eb36  mov     [rsp+140h+lpString2], rax
0x18000eb3b  xor     ebx, ebx
0x18000eb3d  lea     rax, aAgentfillperio; "AgentFillPeriodMin"
0x18000eb44  xor     r14d, r14d
0x18000eb47  mov     [rsp+140h+var_F0], rax
0x18000eb4c  lea     rax, [rcx+4]
0x18000eb50  mov     [rsp+140h+var_E8], rax
0x18000eb55  lea     rax, aAgentfillmaxmi; "AgentFillMaxMin"
0x18000eb5c  mov     [rsp+140h+var_E0], rax
0x18000eb61  lea     rax, [rcx+8]
0x18000eb65  mov     [rsp+140h+var_D8], rax
0x18000eb6a  lea     rax, aAgentfilldelay; "AgentFillDelayStartMin"
0x18000eb71  mov     [rsp+140h+var_D0], rax
0x18000eb76  lea     rax, [rcx+0Ch]
0x18000eb7a  mov     [rsp+140h+var_C8], rax
0x18000eb7f  lea     rax, aAgentreconnect_0; "AgentReconnectEnabled"
0x18000eb86  mov     [rbp+40h+var_C0], rax
0x18000eb8a  lea     rax, [rcx+20h]
0x18000eb8e  mov     [rbp+40h+var_B8], rax
0x18000eb92  lea     rax, aAgentreconnect_1; "AgentReconnectPeriodMin"
0x18000eb99  mov     [rbp+40h+var_B0], rax
0x18000eb9d  lea     rax, [rcx+24h]
0x18000eba1  mov     [rbp+40h+var_A8], rax
0x18000eba5  lea     rax, aAgentreconnect; "AgentReconnectDelayStartMin"
0x18000ebac  mov     [rbp+40h+var_A0], rax
0x18000ebb0  lea     rax, [rcx+28h]
0x18000ebb4  mov     [rbp+40h+var_98], rax
0x18000ebb8  lea     rax, aAgentdemandrec; "AgentDemandReconnectDelayStartSec"
0x18000ebbf  mov     [rbp+40h+var_90], rax
0x18000ebc3  lea     rax, [rcx+2Ch]
0x18000ebc7  mov     [rbp+40h+var_88], rax
0x18000ebcb  lea     rax, aAgentsyncenabl; "AgentSyncEnabled"
0x18000ebd2  mov     [rbp+40h+var_80], rax
0x18000ebd6  lea     rax, [rcx+10h]
0x18000ebda  mov     [rbp+40h+var_78], rax
0x18000ebde  lea     rax, aAgentsyncmaxmi; "AgentSyncMaxMin"
0x18000ebe5  mov     [rbp+40h+var_70], rax
0x18000ebe9  lea     rax, [rcx+14h]
0x18000ebed  mov     [rbp+40h+var_68], rax
0x18000ebf1  lea     rax, aAgentsyncdelay; "AgentSyncDelayStartSec"
0x18000ebf8  mov     [rbp+40h+var_60], rax
0x18000ebfc  lea     rax, [rcx+1Ch]
0x18000ec00  mov     [rbp+40h+var_58], rax
0x18000ec04  lea     rax, aAgentsyncnopin; "AgentSyncNoPinNewFiles"
0x18000ec0b  mov     [rbp+40h+var_50], rax
0x18000ec0f  lea     rax, [rcx+18h]
0x18000ec13  mov     [rbp+40h+var_48], rax
0x18000ec17  lea     rax, aPrefetchcloseh_4; "PrefetchCloseHandleEnabled"
0x18000ec1e  mov     [rbp+40h+var_40], rax
0x18000ec22  lea     rax, [rcx+30h]
0x18000ec26  mov     [rbp+40h+var_38], rax
0x18000ec2a  lea     rax, aPrefetchcloseh; "PrefetchCloseHandlePeriodSec"
0x18000ec31  mov     [rbp+40h+var_30], rax
0x18000ec35  lea     rax, [rcx+34h]
0x18000ec39  mov     [rbp+40h+var_28], rax
0x18000ec3d  lea     rax, aPrefetchcloseh_3; "PrefetchCloseHandleDelayStartSec"
0x18000ec44  mov     [rbp+40h+var_20], rax
0x18000ec48  lea     rax, [rcx+38h]
0x18000ec4c  mov     [rbp+40h+var_18], rax
0x18000ec50  test    ebx, ebx
0x18000ec52  js      loc_18000ECFE
0x18000ec58  xorps   xmm0, xmm0
0x18000ec5b  lea     rcx, [rsp+140h+pvarg]; pvarg
0x18000ec60  xor     eax, eax
0x18000ec62  movups  xmmword ptr [rsp+140h+pvarg], xmm0
0x18000ec67  mov     qword ptr [rsp+140h+pvarg+10h], rax
0x18000ec6c  call    cs:__imp_VariantInit
0x18000ec72  movsxd  rsi, r14d
0x18000ec75  lea     rdx, [rbp+40h+arg_8]; struct COfflineFilesSettingInternal **
0x18000ec79  add     rsi, rsi
0x18000ec7c  mov     [rbp+40h+arg_8], 0
0x18000ec84  mov     rcx, [rsp+rsi*8+140h+lpString2]; lpString2
0x18000ec89  call    ?CreateInstance@COfflineFilesSetting@@SAJPEBGPEAPEAVCOfflineFilesSettingInternal@@@Z; COfflineFilesSetting::CreateInstance(ushort const *,COfflineFilesSettingInternal * *)
0x18000ec8e  mov     ebx, eax
0x18000ec90  test    eax, eax
0x18000ec92  js      short loc_18000ECF1
0x18000ec94  mov     rdi, [rbp+40h+arg_8]
0x18000ec98  lea     r8, [rbp+40h+arg_0]
0x18000ec9c  mov     [rbp+40h+arg_0], 0
0x18000eca3  lea     rdx, [rsp+140h+pvarg]
0x18000eca8  mov     rcx, rdi
0x18000ecab  mov     rax, [rdi]
0x18000ecae  mov     rax, [rax+38h]
0x18000ecb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecb7  mov     ebx, eax
0x18000ecb9  test    rdi, rdi
0x18000ecbc  jz      short loc_18000ECD1
0x18000ecbe  mov     rax, [rdi]
0x18000ecc1  mov     edx, 1
0x18000ecc6  mov     rcx, rdi
0x18000ecc9  mov     rax, [rax]
0x18000eccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecd1  test    ebx, ebx
0x18000ecd3  js      short loc_18000ECF1
0x18000ecd5  mov     rdx, [rsp+rsi*8+140h+var_F8]; unsigned int *
0x18000ecda  lea     rcx, [rsp+140h+pvarg]; pvarSrc
0x18000ecdf  call    ?CscVarUtil_ConvertVariantToDWORD@@YAJAEBUtagVARIANT@@PEAK@Z; CscVarUtil_ConvertVariantToDWORD(tagVARIANT const &,ulong *)
0x18000ece4  lea     rcx, [rsp+140h+pvarg]; pvarg
0x18000ece9  mov     ebx, eax
0x18000eceb  call    cs:__imp_VariantClear
0x18000ecf1  inc     r14d
0x18000ecf4  cmp     r14d, 0Fh
0x18000ecf8  jb      loc_18000EC50
0x18000ecfe  lea     r11, [rsp+140h+var_10]
0x18000ed06  mov     eax, ebx
0x18000ed08  mov     rbx, [r11+30h]
0x18000ed0c  mov     rsi, [r11+38h]
0x18000ed10  mov     rsp, r11
0x18000ed13  pop     r14
0x18000ed15  pop     rdi
0x18000ed16  pop     rbp
0x18000ed17  retn
```
