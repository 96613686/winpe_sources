# InitSendAcls(void)

- ea: `0x180025550`
- end: `0x18002568f`
- name: `?InitSendAcls@@YAXXZ`
- size: `319`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800207c4`

## callees

- `0x18000c39c`
- `0x1800176f4`
- `0x180025550`

## string_xrefs

- `0x180025560`: `security`
- `0x180025658`: `msmq_MulticastInstalled`

## pseudocode

```c
void InitSendAcls(void)
{
  int v0; // [rsp+20h] [rbp-38h] BYREF
  const wchar_t *v1; // [rsp+28h] [rbp-30h]
  const wchar_t *v2; // [rsp+30h] [rbp-28h]
  int v3; // [rsp+38h] [rbp-20h]
  __int64 v4; // [rsp+40h] [rbp-18h]

  v0 = 0;
  v1 = L"security";
  v2 = L"PermitAnonEveryoneSend";
  v3 = 0;
  v4 = 0;
  try
  {
    CmQueryValue((const struct RegEntry *)&v0, &dword_1800431D0);
    if ( dword_1800431D0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 10, &WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids);
    }
    else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 11, &WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids);
    }
    v0 = 0;
    v1 = L"SOFTWARE\\Microsoft\\MSMQ\\Setup";
    v2 = L"msmq_HTTPSupport";
    v3 = 0;
    v4 = -2147483646;
    CmQueryValue((const struct RegEntry *)&v0, &dword_1800431CC);
    v0 = 0;
    v1 = L"SOFTWARE\\Microsoft\\MSMQ\\Setup";
    v2 = L"msmq_MulticastInstalled";
    v3 = 0;
    v4 = -2147483646;
    CmQueryValue((const struct RegEntry *)&v0, &dword_1800431C8);
  }
  catch ( registry_access_error )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 268) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 32), 12, &WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids);
  }
}

```

## disassembly

```asm
0x180025550  mov     r11, rsp
0x180025553  push    rdi
0x180025554  sub     rsp, 50h
0x180025558  mov     [rsp+58h+var_38], 0
0x180025560  lea     rax, aSecurity; "security"
0x180025567  mov     [r11-30h], rax
0x18002556b  lea     rax, aPermitanonever; "PermitAnonEveryoneSend"
0x180025572  mov     [r11-28h], rax
0x180025576  mov     [rsp+58h+var_20], 0
0x18002557e  mov     qword ptr [r11-18h], 0
0x180025586  lea     rdx, dword_1800431D0; int *
0x18002558d  lea     rcx, [r11-38h]; struct RegEntry *
0x180025591  call    ?CmQueryValue@@YAXAEBVRegEntry@@PEAH@Z; CmQueryValue(RegEntry const &,int *)
0x180025596  cmp     cs:dword_1800431D0, 0
0x18002559d  jz      short loc_1800255D5
0x18002559f  lea     rax, WPP_GLOBAL_Control
0x1800255a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800255ad  cmp     rcx, rax
0x1800255b0  jz      short loc_180025609
0x1800255b2  test    byte ptr [rcx+10Ch], 4
0x1800255b9  jz      short loc_180025609
0x1800255bb  mov     edx, 0Ah
0x1800255c0  lea     r8, WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids
0x1800255c7  mov     rcx, [rcx+100h]
0x1800255ce  call    WPP_SF_
0x1800255d3  jmp     short loc_180025609
0x1800255d5  lea     rax, WPP_GLOBAL_Control
0x1800255dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800255e3  cmp     rcx, rax
0x1800255e6  jz      short loc_180025609
0x1800255e8  test    byte ptr [rcx+10Ch], 4
0x1800255ef  jz      short loc_180025609
0x1800255f1  mov     edx, 0Bh
0x1800255f6  lea     r8, WPP_abcc90b310a6358b658ae825a318a2f1_Traceguids
0x1800255fd  mov     rcx, [rcx+100h]
0x180025604  call    WPP_SF_
0x180025609  mov     [rsp+58h+var_38], 0
0x180025611  lea     rdi, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\MSMQ\\Setup"
0x180025618  mov     [rsp+58h+var_30], rdi
0x18002561d  lea     rax, aMsmqHttpsuppor; "msmq_HTTPSupport"
0x180025624  mov     [rsp+58h+var_28], rax
0x180025629  mov     [rsp+58h+var_20], 0
0x180025631  mov     [rsp+58h+var_18], 0FFFFFFFF80000002h
0x18002563a  lea     rdx, dword_1800431CC; int *
0x180025641  lea     rcx, [rsp+58h+var_38]; struct RegEntry *
0x180025646  call    ?CmQueryValue@@YAXAEBVRegEntry@@PEAH@Z; CmQueryValue(RegEntry const &,int *)
0x18002564b  mov     [rsp+58h+var_38], 0
0x180025653  mov     [rsp+58h+var_30], rdi
0x180025658  lea     rax, aMsmqMulticasti; "msmq_MulticastInstalled"
0x18002565f  mov     [rsp+58h+var_28], rax
0x180025664  mov     [rsp+58h+var_20], 0
0x18002566c  mov     [rsp+58h+var_18], 0FFFFFFFF80000002h
0x180025675  lea     rdx, dword_1800431C8; int *
0x18002567c  lea     rcx, [rsp+58h+var_38]; struct RegEntry *
0x180025681  call    ?CmQueryValue@@YAXAEBVRegEntry@@PEAH@Z; CmQueryValue(RegEntry const &,int *)
0x180025686  nop
0x180025687  jmp     short $+2
0x180025689  add     rsp, 50h
0x18002568d  pop     rdi
0x18002568e  retn
```
