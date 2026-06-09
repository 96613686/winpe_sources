# ProvPackageValidator::SigningRequired(void)

- ea: `0x180024320`
- end: `0x1800243dd`
- name: `?SigningRequired@ProvPackageValidator@@QEAA_NXZ`
- size: `189`
- prototype: `bool __fastcall(ProvPackageValidator *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023d4c`

## callees

- `0x18001b388`
- `0x180024320`
- `0x180033ed0`

## import_xrefs

- `policymanager!PolicyManager_GetPolicyInt` at `0x18002439e`
- `policymanager!PolicyManager_GetPolicyInt` at `0x18002439e`

## string_xrefs

- `0x18002433c`: `Security`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall ProvPackageValidator::SigningRequired(ProvPackageValidator *this)
{
  int PolicyInt; // eax
  int v3; // [rsp+20h] [rbp-29h] BYREF
  __int128 v4; // [rsp+28h] [rbp-21h] BYREF
  wchar_t v5; // [rsp+38h] [rbp-11h]
  _OWORD v6[4]; // [rsp+40h] [rbp-9h] BYREF
  __int64 v7; // [rsp+80h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  v4 = *(_OWORD *)L"Security";
  v5 = aSecurity[8];
  v6[0] = *(_OWORD *)L"RequireProvisioningPackageSignature";
  v6[2] = *(_OWORD *)L"ingPackageSignature";
  v6[1] = *(_OWORD *)L"rovisioningPackageSignature";
  v7 = *(_QWORD *)L"ure";
  v6[3] = *(_OWORD *)L"geSignature";
  v3 = 1;
  PolicyInt = PolicyManager_GetPolicyInt(&v4, v6, &v3);
  if ( PolicyInt < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x10A,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpackagevalidator.cpp",
      (const char *)(unsigned int)PolicyInt,
      v3);
  return v3 != 0;
}

```

## disassembly

```asm
0x180024320  push    rbp
0x180024322  lea     rbp, [rsp-57h]
0x180024327  sub     rsp, 0A0h
0x18002432e  mov     rax, cs:__security_cookie
0x180024335  xor     rax, rsp
0x180024338  mov     [rbp+57h+var_10], rax
0x18002433c  movups  xmm0, xmmword ptr cs:aSecurity; "Security"
0x180024343  lea     r8, [rbp+57h+var_80]
0x180024347  movzx   eax, word ptr cs:aSecurity+10h; ""
0x18002434e  movaps  xmm1, xmmword ptr cs:aRequireprovisi+10h; "rovisioningPackageSignature"
0x180024355  lea     rdx, [rbp+57h+var_60]
0x180024359  movups  [rbp+57h+var_78], xmm0
0x18002435d  lea     rcx, [rbp+57h+var_78]
0x180024361  mov     [rbp+57h+var_68], ax
0x180024365  movaps  xmm0, xmmword ptr cs:aRequireprovisi; "RequireProvisioningPackageSignature"
0x18002436c  movaps  [rbp+57h+var_60], xmm0
0x180024370  movaps  xmm0, xmmword ptr cs:aRequireprovisi+20h; "ingPackageSignature"
0x180024377  movaps  [rbp+57h+var_40], xmm0
0x18002437b  movsd   xmm0, qword ptr cs:aRequireprovisi+40h; "ure"
0x180024383  movaps  [rbp+57h+var_50], xmm1
0x180024387  movaps  xmm1, xmmword ptr cs:aRequireprovisi+30h; "geSignature"
0x18002438e  movsd   [rbp+57h+var_20], xmm0
0x180024393  movaps  [rbp+57h+var_30], xmm1
0x180024397  mov     [rbp+57h+var_80], 1
0x18002439e  call    cs:__imp_PolicyManager_GetPolicyInt
0x1800243a4  test    eax, eax
0x1800243a6  js      short loc_1800243C4
0x1800243a8  cmp     [rbp+57h+var_80], 0
0x1800243ac  setnz   al
0x1800243af  mov     rcx, [rbp+57h+var_10]
0x1800243b3  xor     rcx, rsp; StackCookie
0x1800243b6  call    __security_check_cookie
0x1800243bb  add     rsp, 0A0h
0x1800243c2  pop     rbp
0x1800243c3  retn
0x1800243c4  mov     rcx, [rbp+5Fh]; this
0x1800243c8  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x1800243cf  mov     r9d, eax; char *
0x1800243d2  mov     edx, 10Ah; void *
0x1800243d7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
