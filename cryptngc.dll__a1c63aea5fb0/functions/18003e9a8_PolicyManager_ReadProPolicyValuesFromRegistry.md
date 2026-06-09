# PolicyManager::ReadProPolicyValuesFromRegistry

- ea: `0x18003e9a8`
- end: `0x18003ee12`
- name: `PolicyManager::ReadProPolicyValuesFromRegistry`
- size: `1130`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023e1c`
- `0x180024014`

## callees

- `0x1800158e0`
- `0x180016538`
- `0x180024390`
- `0x18002541c`
- `0x18003e9a8`
- `0x180043f48`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ea11`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ea11`

## string_xrefs

- `0x18003eb2f`: `PINComplexity`
- `0x18003ec20`: `PINComplexity`
- `0x18003ec55`: `PINComplexity`
- `0x18003ec94`: `PINComplexity`
- `0x18003ea77`: `RequireSecurityDevice`
- `0x18003eaf3`: `AllowAllUserAccessToSmartCardNode`

## pseudocode

```c
__int64 __fastcall PolicyManager::ReadProPolicyValuesFromRegistry(int a1, _OWORD *a2)
{
  LSTATUS v3; // eax
  int PolicyValue; // eax
  int v5; // ecx
  int v6; // edi
  unsigned int v7; // r13d
  unsigned int v8; // r12d
  int v9; // r15d
  int v10; // r14d
  int v11; // esi
  int v12; // edi
  int v13; // ebx
  int v14; // eax
  int v15; // ebx
  char *v16; // rdx
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int128 v19; // xmm1
  unsigned int v21; // [rsp+50h] [rbp-79h] BYREF
  void **v22; // [rsp+58h] [rbp-71h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-69h] BYREF
  unsigned int v24; // [rsp+68h] [rbp-61h]
  unsigned int v25; // [rsp+6Ch] [rbp-5Dh]
  __int128 v26; // [rsp+70h] [rbp-59h] BYREF
  _BYTE v27[44]; // [rsp+80h] [rbp-49h]
  _BYTE v28[4]; // [rsp+B0h] [rbp-19h] BYREF
  int v29; // [rsp+B4h] [rbp-15h]
  int v30; // [rsp+B8h] [rbp-11h]
  __int128 v31; // [rsp+BCh] [rbp-Dh]
  int v32; // [rsp+CCh] [rbp+3h]
  __int64 v33; // [rsp+D0h] [rbp+7h]
  int v34; // [rsp+D8h] [rbp+Fh]
  int v37; // [rsp+140h] [rbp+77h] BYREF
  unsigned int v38; // [rsp+148h] [rbp+7Fh] BYREF

  phkResult = 0;
  v37 = -1;
  v22 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::Close(&v22);
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WinBio\\Credential Provider",
         0,
         0x20019u,
         &phkResult);
  if ( (v3 & 0xFFFFFFFD) != 0 && (unsigned int)dword_18006E000 > 3 )
  {
    v38 = v3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18006E000,
      (unsigned int)byte_180062269,
      0,
      0,
      (__int64)&v38);
  }
  PolicyValue = PolicyManager::ReadPolicyValue((unsigned int)&v22, 0, (unsigned int)L"Enabled", 0, 1, (__int64)&v37);
  v5 = 1;
  if ( PolicyValue >= 0 )
    v5 = v37;
  v6 = 0;
  v25 = v5;
  v37 = -1;
  if ( (int)PolicyManager::ReadPolicyValue(a1, 0, (unsigned int)L"RequireSecurityDevice", 0, 1, (__int64)&v37) >= 0 )
    v6 = v37;
  v24 = v6;
  v37 = -1;
  if ( (int)PolicyManager::ReadPolicyValue(a1, 0, (unsigned int)L"DisableSmartCardNode", 0, 1, (__int64)&v37) >= 0
    && v37 == 1 )
  {
    v7 = 0;
  }
  else
  {
    v7 = 1;
    if ( (int)PolicyManager::ReadPolicyValue(
                a1,
                0,
                (unsigned int)L"AllowAllUserAccessToSmartCardNode",
                0,
                1,
                (__int64)&v37) >= 0
      && v37 == 1 )
    {
      v7 = 2;
    }
  }
  v21 = 6;
  PolicyManager::ReadPolicyValue(
    a1,
    (unsigned int)L"PINComplexity",
    (unsigned int)L"MinimumPINLength",
    4,
    127,
    (__int64)&v21);
  v38 = 127;
  PolicyManager::ReadPolicyValue(
    a1,
    (unsigned int)L"PINComplexity",
    (unsigned int)L"MaximumPINLength",
    4,
    127,
    (__int64)&v38);
  v37 = -1;
  v8 = 0;
  if ( (int)PolicyManager::ReadPolicyValue(
              a1,
              (unsigned int)L"PINComplexity",
              (unsigned int)L"UppercaseLetters",
              0,
              2,
              (__int64)&v37) >= 0 )
    v8 = v37;
  v37 = -1;
  v9 = 0;
  if ( (int)PolicyManager::ReadPolicyValue(
              a1,
              (unsigned int)L"PINComplexity",
              (unsigned int)L"LowercaseLetters",
              0,
              2,
              (__int64)&v37) >= 0 )
    v9 = v37;
  v10 = 0;
  v37 = -1;
  if ( (int)PolicyManager::ReadPolicyValue(
              a1,
              (unsigned int)L"PINComplexity",
              (unsigned int)L"Digits",
              0,
              2,
              (__int64)&v37) >= 0 )
    v10 = v37;
  v37 = -1;
  v11 = 0;
  if ( (int)PolicyManager::ReadPolicyValue(
              a1,
              (unsigned int)L"PINComplexity",
              (unsigned int)L"SpecialCharacters",
              0,
              2,
              (__int64)&v37) >= 0 )
    v11 = v37;
  v37 = -1;
  v12 = 0;
  if ( (int)PolicyManager::ReadPolicyValue(
              a1,
              (unsigned int)L"PINComplexity",
              (unsigned int)L"History",
              0,
              50,
              (__int64)&v37) >= 0 )
    v12 = v37;
  v37 = -1;
  v13 = 0;
  v14 = PolicyManager::ReadPolicyValue(
          a1,
          (unsigned int)L"PINComplexity",
          (unsigned int)L"Expiration",
          0,
          730,
          (__int64)&v37);
  v28[0] = 0;
  if ( v14 >= 0 )
    v13 = v37;
  v34 = 0;
  v29 = 8;
  v30 = 127;
  v31 = 0;
  v32 = 2;
  v33 = 1;
  v15 = NgcPolicy::NgcPinPolicy::Initialize(v28, v21, v38, v8, v9, v10, v11, 0, v12, v13);
  if ( v15 >= 0 )
  {
    DWORD1(v26) = 1;
    *((_QWORD *)&v26 + 1) = 1;
    *(_QWORD *)&v27[32] = 1;
    LOBYTE(v26) = 0;
    v27[0] = 0;
    *(_QWORD *)&v27[4] = 0x7F00000008LL;
    *(_OWORD *)&v27[12] = 0;
    *(_DWORD *)&v27[28] = 2;
    *(_DWORD *)&v27[40] = 0;
    v15 = NgcPolicy::NgcPolicy::Initialize(&v26, v25, v7, v24, v28);
    if ( v15 >= 0 )
    {
      v17 = *(_OWORD *)v27;
      *a2 = v26;
      v18 = *(_OWORD *)&v27[16];
      a2[1] = v17;
      v19 = *(_OWORD *)&v27[28];
      a2[2] = v18;
      *(_OWORD *)((char *)a2 + 44) = v19;
      goto LABEL_34;
    }
    if ( (unsigned int)dword_18006E000 > 2 )
    {
      v16 = &byte_180062207;
      goto LABEL_29;
    }
  }
  else if ( (unsigned int)dword_18006E000 > 2 )
  {
    v16 = (char *)&unk_180062238;
LABEL_29:
    v37 = v15;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_18006E000,
      (_DWORD)v16,
      0,
      0,
      (__int64)&v37);
  }
LABEL_34:
  v22 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::Close(&v22);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18003e9a8  mov     [rsp-8+arg_8], rdx
0x18003e9ad  mov     [rsp-8+arg_0], rcx
0x18003e9b2  push    rbp
0x18003e9b3  push    rbx
0x18003e9b4  push    rsi
0x18003e9b5  push    rdi
0x18003e9b6  push    r12
0x18003e9b8  push    r13
0x18003e9ba  push    r14
0x18003e9bc  push    r15
0x18003e9be  lea     rbp, [rsp-1Fh]
0x18003e9c3  sub     rsp, 0E8h
0x18003e9ca  mov     rbx, rcx
0x18003e9cd  mov     [rbp+57h+var_C0], 0
0x18003e9d5  lea     rax, ??_7?$HandleT@URegKeyHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable'
0x18003e9dc  or      r15d, 0FFFFFFFFh
0x18003e9e0  lea     rcx, [rbp+57h+var_C8]
0x18003e9e4  mov     [rbp+57h+arg_10], r15d
0x18003e9e8  mov     [rbp+57h+var_C8], rax
0x18003e9ec  call    ?Close@?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::Close(void)
0x18003e9f1  lea     rax, [rbp+57h+var_C0]
0x18003e9f5  mov     r9d, 20019h; samDesired
0x18003e9fb  xor     r8d, r8d; ulOptions
0x18003e9fe  mov     [rsp+120h+phkResult], rax; phkResult
0x18003ea03  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18003ea0a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003ea11  call    cs:__imp_RegOpenKeyExW
0x18003ea17  test    eax, 0FFFFFFFDh
0x18003ea1c  jz      short loc_18003EA4E
0x18003ea1e  mov     ecx, cs:dword_18006E000
0x18003ea24  cmp     ecx, 3
0x18003ea27  jbe     short loc_18003EA4E
0x18003ea29  mov     [rbp+57h+arg_18], eax
0x18003ea2c  lea     rdx, byte_180062269
0x18003ea33  lea     rax, [rbp+57h+arg_18]
0x18003ea37  xor     r9d, r9d
0x18003ea3a  xor     r8d, r8d
0x18003ea3d  mov     [rsp+120h+phkResult], rax
0x18003ea42  lea     rcx, dword_18006E000
0x18003ea49  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003ea4e  lea     rax, [rbp+57h+arg_10]
0x18003ea52  mov     esi, 1
0x18003ea57  mov     [rsp+120h+var_F8], rax
0x18003ea5c  lea     r8, aEnabled; "Enabled"
0x18003ea63  xor     r9d, r9d
0x18003ea66  mov     dword ptr [rsp+120h+phkResult], esi
0x18003ea6a  xor     edx, edx
0x18003ea6c  lea     rcx, [rbp+57h+var_C8]
0x18003ea70  call    PolicyManager__ReadPolicyValue
0x18003ea75  test    eax, eax
0x18003ea77  lea     r8, aRequiresecurit; "RequireSecurityDevice"
0x18003ea7e  mov     ecx, esi
0x18003ea80  lea     rax, [rbp+57h+arg_10]
0x18003ea84  cmovns  ecx, [rbp+57h+arg_10]
0x18003ea88  xor     edi, edi
0x18003ea8a  mov     [rbp+57h+var_B4], ecx
0x18003ea8d  xor     r9d, r9d
0x18003ea90  mov     [rsp+120h+var_F8], rax
0x18003ea95  mov     rcx, rbx
0x18003ea98  xor     edx, edx
0x18003ea9a  mov     [rbp+57h+arg_10], r15d
0x18003ea9e  mov     dword ptr [rsp+120h+phkResult], esi
0x18003eaa2  call    PolicyManager__ReadPolicyValue
0x18003eaa7  test    eax, eax
0x18003eaa9  lea     r8, aDisablesmartca; "DisableSmartCardNode"
0x18003eab0  lea     rax, [rbp+57h+arg_10]
0x18003eab4  mov     rcx, rbx
0x18003eab7  cmovns  edi, [rbp+57h+arg_10]
0x18003eabb  xor     r9d, r9d
0x18003eabe  mov     [rsp+120h+var_F8], rax
0x18003eac3  xor     edx, edx
0x18003eac5  mov     [rbp+57h+var_B8], edi
0x18003eac8  mov     [rbp+57h+arg_10], r15d
0x18003eacc  mov     dword ptr [rsp+120h+phkResult], esi
0x18003ead0  call    PolicyManager__ReadPolicyValue
0x18003ead5  lea     r14d, [rsi+1]
0x18003ead9  test    eax, eax
0x18003eadb  js      short loc_18003EAE7
0x18003eadd  cmp     [rbp+57h+arg_10], esi
0x18003eae0  jnz     short loc_18003EAE7
0x18003eae2  xor     r13d, r13d
0x18003eae5  jmp     short loc_18003EB16
0x18003eae7  lea     rax, [rbp+57h+arg_10]
0x18003eaeb  xor     r9d, r9d
0x18003eaee  mov     [rsp+120h+var_F8], rax
0x18003eaf3  lea     r8, aAllowalluserac; "AllowAllUserAccessToSmartCardNode"
0x18003eafa  xor     edx, edx
0x18003eafc  mov     dword ptr [rsp+120h+phkResult], esi
0x18003eb00  mov     rcx, rbx
0x18003eb03  mov     r13d, esi
0x18003eb06  call    PolicyManager__ReadPolicyValue
0x18003eb0b  test    eax, eax
0x18003eb0d  js      short loc_18003EB16
0x18003eb0f  cmp     [rbp+57h+arg_10], esi
0x18003eb12  cmovz   r13d, r14d
0x18003eb16  mov     r12d, 7Fh
0x18003eb1c  mov     [rbp+57h+var_D0], 6
0x18003eb23  lea     rax, [rbp+57h+var_D0]
0x18003eb27  mov     rcx, rbx
0x18003eb2a  mov     [rsp+120h+var_F8], rax
0x18003eb2f  lea     rsi, aPincomplexity; "PINComplexity"
0x18003eb36  lea     r8, aMinimumpinleng_0; "MinimumPINLength"
0x18003eb3d  mov     dword ptr [rsp+120h+phkResult], r12d
0x18003eb42  lea     edi, [r12-7Bh]
0x18003eb47  mov     rdx, rsi
0x18003eb4a  mov     r9d, edi
0x18003eb4d  call    PolicyManager__ReadPolicyValue
0x18003eb52  lea     rax, [rbp+57h+arg_18]
0x18003eb56  mov     [rbp+57h+arg_18], r12d
0x18003eb5a  mov     [rsp+120h+var_F8], rax
0x18003eb5f  lea     r8, aMaximumpinleng; "MaximumPINLength"
0x18003eb66  mov     r9d, edi
0x18003eb69  mov     dword ptr [rsp+120h+phkResult], r12d
0x18003eb6e  mov     rdx, rsi
0x18003eb71  mov     rcx, rbx
0x18003eb74  call    PolicyManager__ReadPolicyValue
0x18003eb79  lea     rax, [rbp+57h+arg_10]
0x18003eb7d  mov     [rbp+57h+arg_10], r15d
0x18003eb81  mov     [rsp+120h+var_F8], rax
0x18003eb86  lea     r8, aUppercaselette; "UppercaseLetters"
0x18003eb8d  xor     r9d, r9d
0x18003eb90  mov     dword ptr [rsp+120h+phkResult], r14d
0x18003eb95  mov     rdx, rsi
0x18003eb98  mov     rcx, rbx
0x18003eb9b  xor     r12d, r12d
0x18003eb9e  call    PolicyManager__ReadPolicyValue
0x18003eba3  test    eax, eax
0x18003eba5  lea     r8, aLowercaselette; "LowercaseLetters"
0x18003ebac  lea     rax, [rbp+57h+arg_10]
0x18003ebb0  mov     rdx, rsi
0x18003ebb3  cmovns  r12d, [rbp+57h+arg_10]
0x18003ebb8  mov     rcx, rbx
0x18003ebbb  mov     [rbp+57h+arg_10], r15d
0x18003ebbf  xor     r9d, r9d
0x18003ebc2  mov     [rsp+120h+var_F8], rax
0x18003ebc7  xor     r15d, r15d
0x18003ebca  mov     dword ptr [rsp+120h+phkResult], r14d
0x18003ebcf  call    PolicyManager__ReadPolicyValue
0x18003ebd4  test    eax, eax
0x18003ebd6  lea     r8, aDigits; "Digits"
0x18003ebdd  lea     rax, [rbp+57h+arg_10]
0x18003ebe1  mov     rdx, rsi
0x18003ebe4  cmovns  r15d, [rbp+57h+arg_10]
0x18003ebe9  mov     rcx, rbx
0x18003ebec  mov     [rsp+120h+var_F8], rax
0x18003ebf1  xor     r14d, r14d
0x18003ebf4  xor     r9d, r9d
0x18003ebf7  mov     [rbp+57h+arg_10], 0FFFFFFFFh
0x18003ebfe  lea     edi, [r14+2]
0x18003ec02  mov     dword ptr [rsp+120h+phkResult], edi
0x18003ec06  call    PolicyManager__ReadPolicyValue
0x18003ec0b  test    eax, eax
0x18003ec0d  lea     r8, aSpecialcharact; "SpecialCharacters"
0x18003ec14  lea     rax, [rbp+57h+arg_10]
0x18003ec18  mov     rcx, rbx
0x18003ec1b  cmovns  r14d, [rbp+57h+arg_10]
0x18003ec20  lea     rdx, aPincomplexity; "PINComplexity"
0x18003ec27  mov     [rsp+120h+var_F8], rax
0x18003ec2c  xor     r9d, r9d
0x18003ec2f  mov     [rbp+57h+arg_10], 0FFFFFFFFh
0x18003ec36  xor     esi, esi
0x18003ec38  mov     dword ptr [rsp+120h+phkResult], edi
0x18003ec3c  call    PolicyManager__ReadPolicyValue
0x18003ec41  test    eax, eax
0x18003ec43  lea     r8, aHistory; "History"
0x18003ec4a  lea     rax, [rbp+57h+arg_10]
0x18003ec4e  mov     rcx, rbx
0x18003ec51  cmovns  esi, [rbp+57h+arg_10]
0x18003ec55  lea     rdx, aPincomplexity; "PINComplexity"
0x18003ec5c  mov     [rsp+120h+var_F8], rax
0x18003ec61  xor     r9d, r9d
0x18003ec64  mov     [rbp+57h+arg_10], 0FFFFFFFFh
0x18003ec6b  xor     edi, edi
0x18003ec6d  mov     dword ptr [rsp+120h+phkResult], 32h ; '2'
0x18003ec75  call    PolicyManager__ReadPolicyValue
0x18003ec7a  test    eax, eax
0x18003ec7c  cmovns  edi, [rbp+57h+arg_10]
0x18003ec80  lea     rax, [rbp+57h+arg_10]
0x18003ec84  mov     rcx, [rbp+57h+arg_0]
0x18003ec88  lea     r8, aExpiration; "Expiration"
0x18003ec8f  mov     [rsp+120h+var_F8], rax
0x18003ec94  lea     rdx, aPincomplexity; "PINComplexity"
0x18003ec9b  xor     r9d, r9d
0x18003ec9e  mov     dword ptr [rsp+120h+phkResult], 2DAh
0x18003eca6  mov     [rbp+57h+arg_10], 0FFFFFFFFh
0x18003ecad  xor     ebx, ebx
0x18003ecaf  call    PolicyManager__ReadPolicyValue
0x18003ecb4  mov     r8d, [rbp+57h+arg_18]
0x18003ecb8  xor     ecx, ecx
0x18003ecba  mov     edx, [rbp+57h+var_D0]
0x18003ecbd  test    eax, eax
0x18003ecbf  mov     [rbp+57h+var_70], cl
0x18003ecc2  xorps   xmm0, xmm0
0x18003ecc5  cmovns  ebx, [rbp+57h+arg_10]
0x18003ecc9  mov     r9d, r12d
0x18003eccc  mov     [rsp+120h+var_D8], ebx
0x18003ecd0  mov     [rsp+120h+var_E0], edi
0x18003ecd4  xor     edi, edi
0x18003ecd6  mov     [rsp+120h+var_E8], edi
0x18003ecda  mov     [rsp+120h+var_F0], esi
0x18003ecde  mov     [rbp+57h+var_48], ecx
0x18003ece1  lea     rcx, [rbp+57h+var_70]
0x18003ece5  mov     dword ptr [rsp+120h+var_F8], r14d
0x18003ecea  mov     dword ptr [rsp+120h+phkResult], r15d
0x18003ecef  mov     [rbp+57h+var_6C], 8
0x18003ecf6  mov     [rbp+57h+var_68], 7Fh
0x18003ecfd  movups  [rbp+57h+var_64], xmm0
0x18003ed01  mov     [rbp+57h+var_54], 2
0x18003ed08  mov     [rbp+57h+var_50], 1
0x18003ed10  call    ?Initialize@NgcPinPolicy@NgcPolicy@@QEAAJKKW4_PIN_CHARACTER_POLICY_OPTION@@000HKK@Z; NgcPolicy::NgcPinPolicy::Initialize(ulong,ulong,_PIN_CHARACTER_POLICY_OPTION,_PIN_CHARACTER_POLICY_OPTION,_PIN_CHARACTER_POLICY_OPTION,_PIN_CHARACTER_POLICY_OPTION,int,ulong,ulong)
0x18003ed15  mov     ebx, eax
0x18003ed17  test    eax, eax
0x18003ed19  jns     short loc_18003ED54
0x18003ed1b  mov     edx, cs:dword_18006E000
0x18003ed21  cmp     edx, 2
0x18003ed24  jbe     loc_18003EDE8
0x18003ed2a  lea     rdx, unk_180062238
0x18003ed31  xor     r9d, r9d
0x18003ed34  lea     rax, [rbp+57h+arg_10]
0x18003ed38  xor     r8d, r8d
0x18003ed3b  mov     [rsp+120h+phkResult], rax
0x18003ed40  lea     rcx, dword_18006E000
0x18003ed47  mov     [rbp+57h+arg_10], ebx
0x18003ed4a  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003ed4f  jmp     loc_18003EDE8
0x18003ed54  mov     r9d, [rbp+57h+var_B8]
0x18003ed58  lea     rcx, [rbp+57h+var_B0]
0x18003ed5c  mov     edx, [rbp+57h+var_B4]
0x18003ed5f  mov     eax, 1
0x18003ed64  mov     dword ptr [rbp+57h+var_B0+4], eax
0x18003ed67  xorps   xmm0, xmm0
0x18003ed6a  mov     qword ptr [rbp+57h+var_B0+8], rax
0x18003ed6e  mov     r8d, r13d
0x18003ed71  mov     qword ptr [rbp+57h+var_84+4], rax
0x18003ed75  lea     rax, [rbp+57h+var_70]
0x18003ed79  mov     [rsp+120h+phkResult], rax
0x18003ed7e  mov     byte ptr [rbp+57h+var_B0], dil
0x18003ed82  mov     byte ptr [rbp+57h+var_A0], dil
0x18003ed86  mov     dword ptr [rbp+57h+var_A0+4], 8
0x18003ed8d  mov     dword ptr [rbp+57h+var_A0+8], 7Fh
0x18003ed94  movdqu  [rbp+57h+var_A0+0Ch], xmm0
0x18003ed99  mov     dword ptr [rbp+57h+var_84], 2
0x18003eda0  mov     dword ptr [rbp+57h+var_84+0Ch], edi
0x18003eda3  call    ?Initialize@NgcPolicy@1@QEAAJW4_NGC_BIOMETRICS_POLICY@@W4_NGC_SMART_CARD_POLICY@@W4_NGC_HARDWARE_POLICY@@AEBVNgcPinPolicy@1@@Z; NgcPolicy::NgcPolicy::Initialize(_NGC_BIOMETRICS_POLICY,_NGC_SMART_CARD_POLICY,_NGC_HARDWARE_POLICY,NgcPolicy::NgcPinPolicy const &)
0x18003eda8  mov     ebx, eax
0x18003edaa  test    eax, eax
0x18003edac  jns     short loc_18003EDC5
0x18003edae  mov     ecx, cs:dword_18006E000
0x18003edb4  cmp     ecx, 2
0x18003edb7  jbe     short loc_18003EDE8
0x18003edb9  lea     rdx, byte_180062207
0x18003edc0  jmp     loc_18003ED31
0x18003edc5  mov     rax, [rbp+57h+arg_8]
0x18003edc9  movups  xmm0, [rbp+57h+var_B0]
0x18003edcd  movups  xmm1, [rbp+57h+var_A0]
0x18003edd1  movups  xmmword ptr [rax], xmm0
0x18003edd4  movups  xmm0, xmmword ptr [rbp-39h]
0x18003edd8  movups  xmmword ptr [rax+10h], xmm1
0x18003eddc  movups  xmm1, [rbp+57h+var_84]
0x18003ede0  movups  xmmword ptr [rax+20h], xmm0
0x18003ede4  movups  xmmword ptr [rax+2Ch], xmm1
0x18003ede8  lea     rax, ??_7?$HandleT@URegKeyHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable'
0x18003edef  lea     rcx, [rbp+57h+var_C8]
0x18003edf3  mov     [rbp+57h+var_C8], rax
0x18003edf7  call    ?Close@?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::Close(void)
0x18003edfc  mov     eax, ebx
0x18003edfe  add     rsp, 0E8h
0x18003ee05  pop     r15
0x18003ee07  pop     r14
0x18003ee09  pop     r13
0x18003ee0b  pop     r12
0x18003ee0d  pop     rdi
0x18003ee0e  pop     rsi
0x18003ee0f  pop     rbx
0x18003ee10  pop     rbp
0x18003ee11  retn
```
