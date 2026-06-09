# TrustedPlatformModule::IsReadyForAttestation(bool &,std::bitset<64> *)

- ea: `0x18013dab0`
- end: `0x18013dcd4`
- name: `?IsReadyForAttestation@TrustedPlatformModule@@QEAAJAEA_NPEAV?$bitset@$0EA@@std@@@Z`
- size: `548`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update`

## callers

- `0x18013d9c0`

## callees

- `0x180019000`
- `0x1800ece5c`
- `0x18013cf74`
- `0x18013dab0`
- `0x18013dcdc`
- `0x18013de70`
- `0x18013e1e4`
- `0x18013e25c`
- `0x18013f4c4`
- `0x18013fff8`
- `0x1801420f4`
- `0x1801421d0`
- `0x180142280`

## import_xrefs

- `tbs!Tbsi_Get_TCG_Log_Ex` at `0x18013db5b`
- `tbs!Tbsi_Get_TCG_Log_Ex` at `0x18013db5b`

## string_xrefs

- `0x18013db02`: `onecore\base\ngscb\tpmhli\lib\isready.cpp`
- `0x18013db3a`: `onecore\base\ngscb\tpmhli\lib\isready.cpp`
- `0x18013db7f`: `onecore\base\ngscb\tpmhli\lib\isready.cpp`
- `0x18013dbe1`: `onecore\base\ngscb\tpmhli\lib\isready.cpp`
- `0x18013dc2b`: `onecore\base\ngscb\tpmhli\lib\isready.cpp`

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
0x18013dab0  push    rbx
0x18013dab2  push    rsi
0x18013dab3  push    rdi
0x18013dab4  push    r14
0x18013dab6  push    r15
0x18013dab8  sub     rsp, 40h
0x18013dabc  mov     rax, cs:__security_cookie
0x18013dac3  xor     rax, rsp
0x18013dac6  mov     [rsp+68h+var_30], rax
0x18013dacb  mov     r14, r8
0x18013dace  mov     r15, rdx
0x18013dad1  mov     rsi, rcx
0x18013dad4  xor     eax, eax
0x18013dad6  mov     [rsp+68h+var_38], rax
0x18013dadb  mov     [rsp+68h+var_44], eax
0x18013dadf  mov     [rsp+68h+var_48], al; int
0x18013dae3  lea     ebx, [rax+1]
0x18013dae6  mov     [rsp+68h+var_48+1], bl
0x18013daea  xor     r8d, r8d
0x18013daed  xor     edx, edx
0x18013daef  call    ?GetVersion@TrustedPlatformModule@@QEAAJPEAW4TpmVersion@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; TrustedPlatformModule::GetVersion(TpmVersion *,std::wstring *)
0x18013daf4  mov     edi, eax
0x18013daf6  test    eax, eax
0x18013daf8  jns     short loc_18013DB1A
0x18013dafa  mov     rcx, [rsp+68h]; this
0x18013daff  mov     r9d, eax; char *
0x18013db02  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\tpmhli\\lib\\isre"...
0x18013db09  mov     edx, 8Ch; void *
0x18013db0e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013db13  mov     eax, edi
0x18013db15  jmp     loc_18013DCBA
0x18013db1a  lea     r8, [rsp+68h+var_38]
0x18013db1f  lea     rdx, [rsp+68h+var_40]
0x18013db24  mov     rcx, rsi
0x18013db27  call    ?IsReadyForStorage@TrustedPlatformModule@@QEAAJAEA_NPEAV?$bitset@$0EA@@std@@@Z; TrustedPlatformModule::IsReadyForStorage(bool &,std::bitset<64> *)
0x18013db2c  mov     edi, eax
0x18013db2e  test    eax, eax
0x18013db30  jns     short loc_18013DB52
0x18013db32  mov     rcx, [rsp+68h]; this
0x18013db37  mov     r9d, eax; char *
0x18013db3a  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\tpmhli\\lib\\isre"...
0x18013db41  mov     edx, 8Fh; void *
0x18013db46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013db4b  mov     eax, edi
0x18013db4d  jmp     loc_18013DCBA
0x18013db52  lea     r8, [rsp+68h+var_44]
0x18013db57  xor     edx, edx
0x18013db59  xor     ecx, ecx
0x18013db5b  call    cs:__imp_Tbsi_Get_TCG_Log_Ex
0x18013db61  mov     edi, eax
0x18013db63  mov     eax, 80000000h
0x18013db68  lea     ecx, [rdi+rax]
0x18013db6b  test    eax, ecx
0x18013db6d  jnz     short loc_18013DB97
0x18013db6f  cmp     edi, 80284011h
0x18013db75  jz      short loc_18013DB97
0x18013db77  mov     rcx, [rsp+68h]; this
0x18013db7c  mov     r9d, edi; char *
0x18013db7f  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\tpmhli\\lib\\isre"...
0x18013db86  mov     edx, 9Ch; void *
0x18013db8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013db90  mov     eax, edi
0x18013db92  jmp     loc_18013DCBA
0x18013db97  cmp     [rsp+68h+var_44], 0
0x18013db9c  jnz     short loc_18013DBAD
0x18013db9e  mov     r8b, bl
0x18013dba1  xor     edx, edx
0x18013dba3  lea     rcx, [rsp+68h+var_38]
0x18013dba8  call    ?set@?$bitset@$0EA@@std@@QEAAAEAV12@_K_N@Z; std::bitset<64>::set(unsigned __int64,bool)
0x18013dbad  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EkCertPresentRegStandard@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EkCertPresentRegStandard@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EkCertPresentRegStandard> `wil::Feature<__WilFeatureTraits_Feature_EkCertPresentRegStandard>::GetImpl(void)'::`2'::impl
0x18013dbb4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EkCertPresentRegStandard@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EkCertPresentRegStandard>::__private_IsEnabled(void)
0x18013dbb9  test    al, al
0x18013dbbb  jz      short loc_18013DBC9
0x18013dbbd  lea     r8, [rsp+68h+var_48]
0x18013dbc2  call    ?CheckUpdateEkCertPresent@TrustedPlatformModule@@QEAAJW4TpmAlgID@@AEA_N@Z; TrustedPlatformModule::CheckUpdateEkCertPresent(TpmAlgID,bool &)
0x18013dbc7  jmp     short loc_18013DBD3
0x18013dbc9  lea     rdx, [rsp+68h+var_48]; bool *
0x18013dbce  call    ?IsEkCertificatePresent@TrustedPlatformModule@@QEAAJAEA_N@Z; TrustedPlatformModule::IsEkCertificatePresent(bool &)
0x18013dbd3  mov     edi, eax
0x18013dbd5  test    eax, eax
0x18013dbd7  jns     short loc_18013DBF9
0x18013dbd9  mov     rcx, [rsp+68h]; this
0x18013dbde  mov     r9d, eax; char *
0x18013dbe1  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\tpmhli\\lib\\isre"...
0x18013dbe8  mov     edx, 0AEh; void *
0x18013dbed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013dbf2  mov     eax, edi
0x18013dbf4  jmp     loc_18013DCBA
0x18013dbf9  cmp     [rsp+68h+var_48], 0
0x18013dbfe  jnz     short loc_18013DC10
0x18013dc00  mov     r8b, bl
0x18013dc03  mov     rdx, rbx
0x18013dc06  lea     rcx, [rsp+68h+var_38]
0x18013dc0b  call    ?set@?$bitset@$0EA@@std@@QEAAAEAV12@_K_N@Z; std::bitset<64>::set(unsigned __int64,bool)
0x18013dc10  lea     rdx, [rsp+68h+var_48+1]; bool *
0x18013dc15  mov     rcx, rsi; this
0x18013dc18  call    ?LostAuths@TrustedPlatformModule@@AEAAJAEA_N@Z; TrustedPlatformModule::LostAuths(bool &)
0x18013dc1d  mov     edi, eax
0x18013dc1f  test    eax, eax
0x18013dc21  jns     short loc_18013DC40
0x18013dc23  mov     rcx, [rsp+68h]; this
0x18013dc28  mov     r9d, eax; char *
0x18013dc2b  lea     r8, aOnecoreBaseNgs_8; "onecore\\base\\ngscb\\tpmhli\\lib\\isre"...
0x18013dc32  mov     edx, 0BAh; void *
0x18013dc37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013dc3c  mov     eax, edi
0x18013dc3e  jmp     short loc_18013DCBA
0x18013dc40  cmp     [rsp+68h+var_48+1], 0
0x18013dc45  jz      short loc_18013DC59
0x18013dc47  mov     r8b, bl
0x18013dc4a  mov     edx, 2
0x18013dc4f  lea     rcx, [rsp+68h+var_38]
0x18013dc54  call    ?set@?$bitset@$0EA@@std@@QEAAAEAV12@_K_N@Z; std::bitset<64>::set(unsigned __int64,bool)
0x18013dc59  mov     rcx, rsi; this
0x18013dc5c  call    ?HasRsaKeygenVulnerability@TrustedPlatformModule@@QEAA_NXZ; TrustedPlatformModule::HasRsaKeygenVulnerability(void)
0x18013dc61  test    al, al
0x18013dc63  jnz     short loc_18013DC7D
0x18013dc65  mov     rcx, rsi; this
0x18013dc68  call    ?HasActivateCredentialVulnerability@TrustedPlatformModule@@QEAA_NXZ; TrustedPlatformModule::HasActivateCredentialVulnerability(void)
0x18013dc6d  test    al, al
0x18013dc6f  jnz     short loc_18013DC7D
0x18013dc71  mov     rcx, rsi; this
0x18013dc74  call    ?HasIntelManagementVulnerability@TrustedPlatformModule@@QEAA_NXZ; TrustedPlatformModule::HasIntelManagementVulnerability(void)
0x18013dc79  test    al, al
0x18013dc7b  jz      short loc_18013DC8F
0x18013dc7d  mov     r8b, bl
0x18013dc80  mov     edx, 4
0x18013dc85  lea     rcx, [rsp+68h+var_38]
0x18013dc8a  call    ?set@?$bitset@$0EA@@std@@QEAAAEAV12@_K_N@Z; std::bitset<64>::set(unsigned __int64,bool)
0x18013dc8f  xor     eax, eax
0x18013dc91  cmp     [rsp+rax*8+68h+var_38], 0
0x18013dc97  jnz     short loc_18013DCA0
0x18013dc99  add     rax, rbx
0x18013dc9c  jz      short loc_18013DC91
0x18013dc9e  jmp     short loc_18013DCA2
0x18013dca0  xor     bl, bl
0x18013dca2  mov     [r15], bl
0x18013dca5  test    r14, r14
0x18013dca8  jz      short loc_18013DCB2
0x18013dcaa  mov     rax, [rsp+68h+var_38]
0x18013dcaf  mov     [r14], rax
0x18013dcb2  xor     eax, eax
0x18013dcb4  jmp     short loc_18013DCBA
0x18013dcb6  mov     eax, [rsp+68h+var_44]
0x18013dcba  mov     rcx, [rsp+68h+var_30]
0x18013dcbf  xor     rcx, rsp; StackCookie
0x18013dcc2  call    __security_check_cookie
0x18013dcc7  add     rsp, 40h
0x18013dccb  pop     r15
0x18013dccd  pop     r14
0x18013dccf  pop     rdi
0x18013dcd0  pop     rsi
0x18013dcd1  pop     rbx
0x18013dcd2  retn
```
