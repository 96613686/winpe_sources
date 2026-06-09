# TrustedPlatformModule::IsReadyForAttestation(bool &,std::bitset<64> *)

- ea: `0x18013febc`
- end: `0x1801400e6`
- name: `?IsReadyForAttestation@TrustedPlatformModule@@QEAAJAEA_NPEAV?$bitset@$0EA@@std@@@Z`
- size: `554`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x18013fdcc`

## callees

- `0x180019080`
- `0x1800ed46c`
- `0x18013f2e4`
- `0x18013febc`
- `0x1801400ec`
- `0x180140280`
- `0x1801405fc`
- `0x180140674`
- `0x1801419e4`
- `0x180142560`
- `0x1801447c4`
- `0x1801448a4`
- `0x180144954`

## import_xrefs

- `tbs!Tbsi_Get_TCG_Log_Ex` at `0x18013ff67`
- `tbs!Tbsi_Get_TCG_Log_Ex` at `0x18013ff67`

## string_xrefs

- `0x18013ff0e`: `onecore\base\ngscb\tpmhli\lib\isready.cpp`
- `0x18013ff46`: `onecore\base\ngscb\tpmhli\lib\isready.cpp`
- `0x18013ff91`: `onecore\base\ngscb\tpmhli\lib\isready.cpp`
- `0x18013fff3`: `onecore\base\ngscb\tpmhli\lib\isready.cpp`
- `0x18014003d`: `onecore\base\ngscb\tpmhli\lib\isready.cpp`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall TrustedPlatformModule::IsReadyForAttestation(TrustedPlatformModule *this, char *a2, _QWORD *a3)
{
  char v6; // bl
  int Version; // eax
  unsigned int v8; // edi
  int IsReadyForStorage; // eax
  unsigned int v11; // edi
  unsigned int TCG_Log; // edi
  __int64 v13; // r8
  __int64 v14; // rdx
  TrustedPlatformModule *v15; // rcx
  int IsEkCertificatePresent; // eax
  __int64 v17; // r8
  unsigned int v18; // edi
  int v19; // eax
  __int64 v20; // r8
  unsigned int v21; // edi
  __int64 v22; // r8
  __int64 v23; // rax
  bool v24[4]; // [rsp+20h] [rbp-48h] BYREF
  int v25; // [rsp+24h] [rbp-44h] BYREF
  _BYTE v26[8]; // [rsp+28h] [rbp-40h] BYREF
  __int64 v27; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v27 = 0;
  v25 = 0;
  v24[0] = 0;
  v6 = 1;
  v24[1] = 1;
  Version = TrustedPlatformModule::GetVersion(this, 0, 0);
  v8 = Version;
  if ( Version >= 0 )
  {
    IsReadyForStorage = TrustedPlatformModule::IsReadyForStorage(this, v26, &v27);
    v11 = IsReadyForStorage;
    if ( IsReadyForStorage >= 0 )
    {
      TCG_Log = Tbsi_Get_TCG_Log_Ex(0, 0, &v25);
      if ( (int)(TCG_Log + 0x80000000) < 0 || TCG_Log == -2144845807 )
      {
        if ( !v25 )
        {
          LOBYTE(v13) = 1;
          std::bitset<64>::set(&v27, 0, v13);
        }
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EkCertPresentRegStandard>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EkCertPresentRegStandard>::GetImpl'::`2'::impl) )
          IsEkCertificatePresent = TrustedPlatformModule::CheckUpdateEkCertPresent(v15, v14, v24);
        else
          IsEkCertificatePresent = TrustedPlatformModule::IsEkCertificatePresent(v15, v24);
        v18 = IsEkCertificatePresent;
        if ( IsEkCertificatePresent >= 0 )
        {
          if ( !v24[0] )
          {
            LOBYTE(v17) = 1;
            std::bitset<64>::set(&v27, 1, v17);
          }
          v19 = TrustedPlatformModule::LostAuths(this, &v24[1]);
          v21 = v19;
          if ( v19 >= 0 )
          {
            if ( v24[1] )
            {
              LOBYTE(v20) = 1;
              std::bitset<64>::set(&v27, 2, v20);
            }
            if ( TrustedPlatformModule::HasRsaKeygenVulnerability(this)
              || TrustedPlatformModule::HasActivateCredentialVulnerability(this)
              || TrustedPlatformModule::HasIntelManagementVulnerability(this) )
            {
              LOBYTE(v22) = 1;
              std::bitset<64>::set(&v27, 4, v22);
            }
            v23 = 0;
            while ( !*(&v27 + v23) )
            {
              if ( ++v23 )
                goto LABEL_30;
            }
            v6 = 0;
LABEL_30:
            *a2 = v6;
            if ( a3 )
              *a3 = v27;
            return 0;
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xBA,
              (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\isready.cpp",
              (const char *)(unsigned int)v19,
              *(int *)v24);
            return v21;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xAE,
            (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\isready.cpp",
            (const char *)(unsigned int)IsEkCertificatePresent,
            *(int *)v24);
          return v18;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9C,
          (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\isready.cpp",
          (const char *)TCG_Log,
          *(int *)v24);
        return TCG_Log;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x8F,
        (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\isready.cpp",
        (const char *)(unsigned int)IsReadyForStorage,
        *(int *)v24);
      return v11;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8C,
      (unsigned int)"onecore\\base\\ngscb\\tpmhli\\lib\\isready.cpp",
      (const char *)(unsigned int)Version,
      *(int *)v24);
    return v8;
  }
}

```

## disassembly

```asm
0x18013febc  push    rbx
0x18013febe  push    rsi
0x18013febf  push    rdi
0x18013fec0  push    r14
0x18013fec2  push    r15
0x18013fec4  sub     rsp, 40h
0x18013fec8  mov     rax, cs:__security_cookie
0x18013fecf  xor     rax, rsp
0x18013fed2  mov     [rsp+68h+var_30], rax
0x18013fed7  mov     r14, r8
0x18013feda  mov     r15, rdx
0x18013fedd  mov     rsi, rcx
0x18013fee0  xor     eax, eax
0x18013fee2  mov     [rsp+68h+var_38], rax
0x18013fee7  mov     [rsp+68h+var_44], eax
0x18013feeb  mov     [rsp+68h+var_48], al; int
0x18013feef  lea     ebx, [rax+1]
0x18013fef2  mov     [rsp+68h+var_48+1], bl
0x18013fef6  xor     r8d, r8d
0x18013fef9  xor     edx, edx
0x18013fefb  call    ?GetVersion@TrustedPlatformModule@@QEAAJPEAW4TpmVersion@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; TrustedPlatformModule::GetVersion(TpmVersion *,std::wstring *)
0x18013ff00  mov     edi, eax
0x18013ff02  test    eax, eax
0x18013ff04  jns     short loc_18013FF26
0x18013ff06  mov     rcx, [rsp+68h]; this
0x18013ff0b  mov     r9d, eax; char *
0x18013ff0e  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\tpmhli\\lib\\isre"...
0x18013ff15  mov     edx, 8Ch; void *
0x18013ff1a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013ff1f  mov     eax, edi
0x18013ff21  jmp     loc_1801400CC
0x18013ff26  lea     r8, [rsp+68h+var_38]
0x18013ff2b  lea     rdx, [rsp+68h+var_40]
0x18013ff30  mov     rcx, rsi
0x18013ff33  call    ?IsReadyForStorage@TrustedPlatformModule@@QEAAJAEA_NPEAV?$bitset@$0EA@@std@@@Z; TrustedPlatformModule::IsReadyForStorage(bool &,std::bitset<64> *)
0x18013ff38  mov     edi, eax
0x18013ff3a  test    eax, eax
0x18013ff3c  jns     short loc_18013FF5E
0x18013ff3e  mov     rcx, [rsp+68h]; this
0x18013ff43  mov     r9d, eax; char *
0x18013ff46  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\tpmhli\\lib\\isre"...
0x18013ff4d  mov     edx, 8Fh; void *
0x18013ff52  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013ff57  mov     eax, edi
0x18013ff59  jmp     loc_1801400CC
0x18013ff5e  lea     r8, [rsp+68h+var_44]
0x18013ff63  xor     edx, edx
0x18013ff65  xor     ecx, ecx
0x18013ff67  call    cs:__imp_Tbsi_Get_TCG_Log_Ex
0x18013ff6e  nop     dword ptr [rax+rax+00h]
0x18013ff73  mov     edi, eax
0x18013ff75  mov     eax, 80000000h
0x18013ff7a  lea     ecx, [rdi+rax]
0x18013ff7d  test    eax, ecx
0x18013ff7f  jnz     short loc_18013FFA9
0x18013ff81  cmp     edi, 80284011h
0x18013ff87  jz      short loc_18013FFA9
0x18013ff89  mov     rcx, [rsp+68h]; this
0x18013ff8e  mov     r9d, edi; char *
0x18013ff91  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\tpmhli\\lib\\isre"...
0x18013ff98  mov     edx, 9Ch; void *
0x18013ff9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013ffa2  mov     eax, edi
0x18013ffa4  jmp     loc_1801400CC
0x18013ffa9  cmp     [rsp+68h+var_44], 0
0x18013ffae  jnz     short loc_18013FFBF
0x18013ffb0  mov     r8b, bl
0x18013ffb3  xor     edx, edx
0x18013ffb5  lea     rcx, [rsp+68h+var_38]
0x18013ffba  call    ?set@?$bitset@$0EA@@std@@QEAAAEAV12@_K_N@Z; std::bitset<64>::set(unsigned __int64,bool)
0x18013ffbf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EkCertPresentRegStandard@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EkCertPresentRegStandard@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EkCertPresentRegStandard> `wil::Feature<__WilFeatureTraits_Feature_EkCertPresentRegStandard>::GetImpl(void)'::`2'::impl
0x18013ffc6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EkCertPresentRegStandard@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EkCertPresentRegStandard>::__private_IsEnabled(void)
0x18013ffcb  test    al, al
0x18013ffcd  jz      short loc_18013FFDB
0x18013ffcf  lea     r8, [rsp+68h+var_48]
0x18013ffd4  call    ?CheckUpdateEkCertPresent@TrustedPlatformModule@@QEAAJW4TpmAlgID@@AEA_N@Z; TrustedPlatformModule::CheckUpdateEkCertPresent(TpmAlgID,bool &)
0x18013ffd9  jmp     short loc_18013FFE5
0x18013ffdb  lea     rdx, [rsp+68h+var_48]; bool *
0x18013ffe0  call    ?IsEkCertificatePresent@TrustedPlatformModule@@QEAAJAEA_N@Z; TrustedPlatformModule::IsEkCertificatePresent(bool &)
0x18013ffe5  mov     edi, eax
0x18013ffe7  test    eax, eax
0x18013ffe9  jns     short loc_18014000B
0x18013ffeb  mov     rcx, [rsp+68h]; this
0x18013fff0  mov     r9d, eax; char *
0x18013fff3  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\tpmhli\\lib\\isre"...
0x18013fffa  mov     edx, 0AEh; void *
0x18013ffff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180140004  mov     eax, edi
0x180140006  jmp     loc_1801400CC
0x18014000b  cmp     [rsp+68h+var_48], 0
0x180140010  jnz     short loc_180140022
0x180140012  mov     r8b, bl
0x180140015  mov     rdx, rbx
0x180140018  lea     rcx, [rsp+68h+var_38]
0x18014001d  call    ?set@?$bitset@$0EA@@std@@QEAAAEAV12@_K_N@Z; std::bitset<64>::set(unsigned __int64,bool)
0x180140022  lea     rdx, [rsp+68h+var_48+1]; bool *
0x180140027  mov     rcx, rsi; this
0x18014002a  call    ?LostAuths@TrustedPlatformModule@@AEAAJAEA_N@Z; TrustedPlatformModule::LostAuths(bool &)
0x18014002f  mov     edi, eax
0x180140031  test    eax, eax
0x180140033  jns     short loc_180140052
0x180140035  mov     rcx, [rsp+68h]; this
0x18014003a  mov     r9d, eax; char *
0x18014003d  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\tpmhli\\lib\\isre"...
0x180140044  mov     edx, 0BAh; void *
0x180140049  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014004e  mov     eax, edi
0x180140050  jmp     short loc_1801400CC
0x180140052  cmp     [rsp+68h+var_48+1], 0
0x180140057  jz      short loc_18014006B
0x180140059  mov     r8b, bl
0x18014005c  mov     edx, 2
0x180140061  lea     rcx, [rsp+68h+var_38]
0x180140066  call    ?set@?$bitset@$0EA@@std@@QEAAAEAV12@_K_N@Z; std::bitset<64>::set(unsigned __int64,bool)
0x18014006b  mov     rcx, rsi; this
0x18014006e  call    ?HasRsaKeygenVulnerability@TrustedPlatformModule@@QEAA_NXZ; TrustedPlatformModule::HasRsaKeygenVulnerability(void)
0x180140073  test    al, al
0x180140075  jnz     short loc_18014008F
0x180140077  mov     rcx, rsi; this
0x18014007a  call    ?HasActivateCredentialVulnerability@TrustedPlatformModule@@QEAA_NXZ; TrustedPlatformModule::HasActivateCredentialVulnerability(void)
0x18014007f  test    al, al
0x180140081  jnz     short loc_18014008F
0x180140083  mov     rcx, rsi; this
0x180140086  call    ?HasIntelManagementVulnerability@TrustedPlatformModule@@QEAA_NXZ; TrustedPlatformModule::HasIntelManagementVulnerability(void)
0x18014008b  test    al, al
0x18014008d  jz      short loc_1801400A1
0x18014008f  mov     r8b, bl
0x180140092  mov     edx, 4
0x180140097  lea     rcx, [rsp+68h+var_38]
0x18014009c  call    ?set@?$bitset@$0EA@@std@@QEAAAEAV12@_K_N@Z; std::bitset<64>::set(unsigned __int64,bool)
0x1801400a1  xor     eax, eax
0x1801400a3  cmp     [rsp+rax*8+68h+var_38], 0
0x1801400a9  jnz     short loc_1801400B2
0x1801400ab  add     rax, rbx
0x1801400ae  jz      short loc_1801400A3
0x1801400b0  jmp     short loc_1801400B4
0x1801400b2  xor     bl, bl
0x1801400b4  mov     [r15], bl
0x1801400b7  test    r14, r14
0x1801400ba  jz      short loc_1801400C4
0x1801400bc  mov     rax, [rsp+68h+var_38]
0x1801400c1  mov     [r14], rax
0x1801400c4  xor     eax, eax
0x1801400c6  jmp     short loc_1801400CC
0x1801400c8  mov     eax, [rsp+68h+var_44]
0x1801400cc  mov     rcx, [rsp+68h+var_30]
0x1801400d1  xor     rcx, rsp; StackCookie
0x1801400d4  call    __security_check_cookie
0x1801400d9  add     rsp, 40h
0x1801400dd  pop     r15
0x1801400df  pop     r14
0x1801400e1  pop     rdi
0x1801400e2  pop     rsi
0x1801400e3  pop     rbx
0x1801400e4  retn
```
