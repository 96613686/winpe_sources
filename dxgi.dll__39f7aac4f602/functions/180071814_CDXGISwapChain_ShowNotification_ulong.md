# CDXGISwapChain::ShowNotification(ulong)

- ea: `0x180071814`
- end: `0x1800719c4`
- name: `?ShowNotification@CDXGISwapChain@@AEAAXK@Z`
- size: `432`
- prototype: `void __fastcall(CDXGISwapChain *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800088f0`

## callees

- `0x18000c6b0`
- `0x1800306f4`
- `0x180071814`
- `0x180075fa0`
- `0x18008c4d8`
- `0x1800908ac`
- `0x180090c4c`

## import_xrefs

- `ntdll!EtwEventUnregister` at `0x180071977`
- `ntdll!EtwEventUnregister` at `0x180071977`
- `ntdll!EtwEventRegister` at `0x18007191f`
- `ntdll!EtwEventRegister` at `0x18007191f`
- `ntdll!EtwEventWrite` at `0x180071952`
- `ntdll!EtwEventWrite` at `0x180071952`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800718d8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800718d8`

## string_xrefs

- `0x180071965`: `Failed to write notification ETW event`

## pseudocode

```c
void __fastcall CDXGISwapChain::ShowNotification(CDXGISwapChain *this, unsigned int a2)
{
  CModule *v4; // rcx
  __int64 v5; // r8
  bool v6; // r9
  const char *v7; // r8
  unsigned int v8; // edx
  char v9; // al
  signed int v10; // eax
  bool v11; // sf
  int v12; // eax
  CModule *v13; // rcx
  bool v14; // r9
  bool v15; // sf
  bool v16; // dl
  bool v17; // sf
  __int64 v18; // [rsp+20h] [rbp-40h] BYREF
  _QWORD v19[2]; // [rsp+28h] [rbp-38h] BYREF
  _DWORD v20[4]; // [rsp+38h] [rbp-28h] BYREF
  _QWORD v21[2]; // [rsp+48h] [rbp-18h] BYREF

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl'::`2'::impl) )
  {
    CModule::ShowNotification(v4, a2, v5, v6);
    return;
  }
  if ( a2 - 12 > 4 )
  {
    v7 = "Unsupported notification type";
LABEL_5:
    v8 = -2147024809;
LABEL_34:
    CModule::RecordJournalImpl(v4, v8, v7, v6);
    return;
  }
  v4 = (CDXGISwapChain *)((char *)this + 3944);
  if ( (*((_DWORD *)this + 980) & 1) != 0 && *(_DWORD *)v4 == 1 )
  {
    v9 = 1;
LABEL_9:
    LOBYTE(v4) = 0;
    goto LABEL_10;
  }
  v9 = 0;
  if ( (*((_DWORD *)this + 980) & 1) == 0 || *(_DWORD *)v4 != 2 )
    goto LABEL_9;
  LOBYTE(v4) = 1;
LABEL_10:
  if ( a2 == 12 && !v9 || a2 == 13 && v9 || a2 == 14 && !(_BYTE)v4 )
  {
    v7 = "Notification blocked due to inconsistent state";
    goto LABEL_5;
  }
  if ( CModule::GetBufferUpgradeNotificationShown(v4) )
    return;
  v20[0] = 0;
  v20[2] = 0;
  v20[1] = a2;
  v21[1] = 16;
  v20[3] = GetCurrentProcessId();
  v18 = 0;
  v21[0] = v20;
  v19[0] = 268435459;
  v19[1] = 0x8000000000020000uLL;
  v10 = EtwEventRegister(WdDiagEtwControlGuid, 0, 0, &v18);
  v11 = v10 < 0;
  if ( v10 > 0 )
  {
    v10 = (unsigned __int16)v10 | 0x80070000;
    v11 = v10 < 0;
  }
  if ( v11 )
  {
    v7 = "Failed to register WdDiag ETW provider";
LABEL_33:
    v8 = v10;
    goto LABEL_34;
  }
  v12 = EtwEventWrite(v18, v19, 1, v21);
  v15 = v12 < 0;
  if ( v12 > 0 )
  {
    v12 = (unsigned __int16)v12 | 0x80070000;
    v15 = v12 < 0;
  }
  if ( v15 )
    CModule::RecordJournalImpl(v13, v12, "Failed to write notification ETW event", v14);
  v10 = EtwEventUnregister(v18);
  v17 = v10 < 0;
  if ( v10 > 0 )
  {
    v10 = (unsigned __int16)v10 | 0x80070000;
    v17 = v10 < 0;
  }
  if ( v17 )
  {
    v7 = "Failed to unregister WdDiag ETW provider";
    goto LABEL_33;
  }
  CModule::SetBufferUpgradeNotificationShown((CModule *)g_Module, v16);
}

```

## disassembly

```asm
0x180071814  mov     [rsp-8+arg_0], rbx
0x180071819  mov     [rsp-8+arg_10], rdi
0x18007181e  push    rbp
0x18007181f  mov     rbp, rsp
0x180071822  sub     rsp, 60h
0x180071826  mov     rax, cs:__security_cookie
0x18007182d  xor     rax, rsp
0x180071830  mov     [rbp+var_8], rax
0x180071834  mov     ebx, edx
0x180071836  mov     rdi, rcx
0x180071839  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutoSR_v2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_v2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2> `wil::Feature<__WilFeatureTraits_Feature_AutoSR_v2>::GetImpl(void)'::`2'::impl
0x180071840  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutoSR_v2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutoSR_v2>::__private_IsEnabled(void)
0x180071845  test    al, al
0x180071847  jz      short loc_180071855
0x180071849  mov     edx, ebx; unsigned int
0x18007184b  call    ?ShowNotification@CModule@@QEAAXK@Z; CModule::ShowNotification(ulong)
0x180071850  jmp     loc_1800719A6
0x180071855  lea     eax, [rbx-0Ch]
0x180071858  cmp     eax, 4
0x18007185b  jbe     short loc_18007186E
0x18007185d  lea     r8, aUnsupportedNot; "Unsupported notification type"
0x180071864  mov     edx, 80070057h
0x180071869  jmp     loc_180071993
0x18007186e  mov     edx, [rdi+0F50h]
0x180071874  lea     rcx, [rdi+0F68h]
0x18007187b  and     edx, 1
0x18007187e  jz      short loc_1800718AD
0x180071880  cmp     dword ptr [rcx], 1
0x180071883  jnz     short loc_1800718AD
0x180071885  mov     al, 1
0x180071887  xor     cl, cl; this
0x180071889  cmp     ebx, 0Ch
0x18007188c  jnz     short loc_180071892
0x18007188e  test    al, al
0x180071890  jz      short loc_1800718A4
0x180071892  cmp     ebx, 0Dh
0x180071895  jnz     short loc_18007189B
0x180071897  test    al, al
0x180071899  jnz     short loc_1800718A4
0x18007189b  cmp     ebx, 0Eh
0x18007189e  jnz     short loc_1800718BC
0x1800718a0  test    cl, cl
0x1800718a2  jnz     short loc_1800718BC
0x1800718a4  lea     r8, aNotificationBl_0; "Notification blocked due to inconsisten"...
0x1800718ab  jmp     short loc_180071864
0x1800718ad  xor     al, al
0x1800718af  test    edx, edx
0x1800718b1  jz      short loc_180071887
0x1800718b3  cmp     dword ptr [rcx], 2
0x1800718b6  jnz     short loc_180071887
0x1800718b8  mov     cl, 1
0x1800718ba  jmp     short loc_180071889
0x1800718bc  call    ?GetBufferUpgradeNotificationShown@CModule@@QEBA_NXZ; CModule::GetBufferUpgradeNotificationShown(void)
0x1800718c1  test    al, al
0x1800718c3  jnz     loc_1800719A6
0x1800718c9  xor     eax, eax
0x1800718cb  mov     [rbp+var_28], 0
0x1800718d2  mov     [rbp+var_20], eax
0x1800718d5  mov     [rbp+var_24], ebx
0x1800718d8  call    cs:__imp_GetCurrentProcessId
0x1800718de  lea     r9, [rbp+var_40]
0x1800718e2  mov     [rbp+var_10], 10h
0x1800718ea  mov     [rbp+var_1C], eax
0x1800718ed  lea     rcx, WdDiagEtwControlGuid
0x1800718f4  lea     rax, [rbp+var_28]
0x1800718f8  mov     [rbp+var_40], 0
0x180071900  mov     [rbp+var_18], rax
0x180071904  xor     r8d, r8d
0x180071907  mov     rax, 8000000000020000h
0x180071911  mov     [rbp+var_38], 10000003h
0x180071919  xor     edx, edx
0x18007191b  mov     [rbp+var_30], rax
0x18007191f  call    cs:__imp_EtwEventRegister
0x180071925  mov     ebx, 80070000h
0x18007192a  test    eax, eax
0x18007192c  jle     short loc_180071935
0x18007192e  movzx   eax, ax
0x180071931  or      eax, ebx
0x180071933  test    eax, eax
0x180071935  jns     short loc_180071940
0x180071937  lea     r8, aFailedToRegist; "Failed to register WdDiag ETW provider"
0x18007193e  jmp     short loc_180071991
0x180071940  mov     rcx, [rbp+var_40]
0x180071944  lea     r9, [rbp+var_18]
0x180071948  mov     r8d, 1
0x18007194e  lea     rdx, [rbp+var_38]
0x180071952  call    cs:__imp_EtwEventWrite
0x180071958  test    eax, eax
0x18007195a  jle     short loc_180071963
0x18007195c  movzx   eax, ax
0x18007195f  or      eax, ebx
0x180071961  test    eax, eax
0x180071963  jns     short loc_180071973
0x180071965  lea     r8, aFailedToWriteN; "Failed to write notification ETW event"
0x18007196c  mov     edx, eax; unsigned int
0x18007196e  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x180071973  mov     rcx, [rbp+var_40]
0x180071977  call    cs:__imp_EtwEventUnregister
0x18007197d  test    eax, eax
0x18007197f  jle     short loc_180071988
0x180071981  movzx   eax, ax
0x180071984  or      eax, ebx
0x180071986  test    eax, eax
0x180071988  jns     short loc_18007199A
0x18007198a  lea     r8, aFailedToUnregi; "Failed to unregister WdDiag ETW provide"...
0x180071991  mov     edx, eax; unsigned int
0x180071993  call    ?RecordJournalImpl@CModule@@QEAAXIPEBD_N@Z; CModule::RecordJournalImpl(uint,char const *,bool)
0x180071998  jmp     short loc_1800719A6
0x18007199a  lea     rcx, ?g_Module@@3VCModule@@A; this
0x1800719a1  call    ?SetBufferUpgradeNotificationShown@CModule@@QEAAX_N@Z; CModule::SetBufferUpgradeNotificationShown(bool)
0x1800719a6  mov     rcx, [rbp+var_8]
0x1800719aa  xor     rcx, rsp; StackCookie
0x1800719ad  call    __security_check_cookie
0x1800719b2  lea     r11, [rsp+60h+var_s0]
0x1800719b7  mov     rbx, [r11+10h]
0x1800719bb  mov     rdi, [r11+20h]
0x1800719bf  mov     rsp, r11
0x1800719c2  pop     rbp
0x1800719c3  retn
```
