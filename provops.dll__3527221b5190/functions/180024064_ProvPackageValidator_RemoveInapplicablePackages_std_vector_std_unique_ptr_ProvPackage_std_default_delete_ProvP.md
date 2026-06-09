# ProvPackageValidator::RemoveInapplicablePackages(std::vector<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>,std::allocator<std::unique_ptr<ProvPackage,std::default_delete<ProvPackage>>>> *,ulong,int)

- ea: `0x180024064`
- end: `0x180024318`
- name: `?RemoveInapplicablePackages@ProvPackageValidator@@QEAAXPEAV?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@KH@Z`
- size: `692`
- prototype: `const struct ProvPackage **__fastcall(ProvPackageValidator *this, const struct ProvPackage ***, unsigned int, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f8d0`

## callees

- `0x18000164c`
- `0x180001718`
- `0x180004d68`
- `0x18001b388`
- `0x180023d4c`
- `0x180024064`
- `0x1800243e4`
- `0x180024440`
- `0x180033ed0`
- `0x180037010`

## import_xrefs

- `policymanager!PolicyManager_GetPolicyInt` at `0x1800240f6`
- `policymanager!PolicyManager_GetPolicyInt` at `0x1800240f6`

## string_xrefs

- `0x18002408b`: `Security`

## pseudocode

```c
const struct ProvPackage **__fastcall ProvPackageValidator::RemoveInapplicablePackages(
        ProvPackageValidator *this,
        const struct ProvPackage ***a2,
        unsigned int a3,
        int a4)
{
  ProvPackageValidator *v6; // r12
  int v7; // r15d
  int PolicyInt; // eax
  const struct ProvPackage **v9; // r14
  const struct ProvPackage **v10; // rbx
  const struct ProvPackage **result; // rax
  const struct ProvPackage **v12; // rdi
  const struct ProvPackage **v13; // r15
  const struct ProvPackage *v14; // r12
  const struct ProvPackage *v15; // rcx
  __int64 v16; // r9
  unsigned int v17; // eax
  __int64 v18; // r9
  unsigned int v19; // eax
  unsigned int v20; // eax
  int v22; // [rsp+24h] [rbp-65h] BYREF
  ProvPackageValidator *v23; // [rsp+28h] [rbp-61h] BYREF
  __int128 v24; // [rsp+40h] [rbp-49h] BYREF
  wchar_t v25; // [rsp+50h] [rbp-39h]
  _OWORD v26[3]; // [rsp+58h] [rbp-31h] BYREF
  __int64 v27; // [rsp+88h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v6 = this;
  v24 = *(_OWORD *)L"Security";
  v23 = this;
  v7 = a4;
  v26[1] = *(_OWORD *)L"ProvisioningPackage";
  v26[0] = *(_OWORD *)L"AllowAddProvisioningPackage";
  v25 = aSecurity[8];
  v22 = 0;
  v27 = *(_QWORD *)L"age";
  v26[2] = *(_OWORD *)L"ningPackage";
  PolicyInt = PolicyManager_GetPolicyInt(&v24, v26, &v22);
  if ( PolicyInt < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x101,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpackagevalidator.cpp",
      (const char *)(unsigned int)PolicyInt,
      a4);
  if ( !v22 )
  {
    if ( *(_DWORD *)g_hProvTraceProvider > 5u && (unsigned __int8)tlgKeywordOn(g_hProvTraceProvider, 0) )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        v18,
        &unk_180041100,
        0);
    std::vector<std::unique_ptr<ProvPackage>>::clear(a2);
    v19 = wil::verify_hresult<long>(2147942405LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpackagevalidator.cpp",
      (const char *)v19,
      a4);
  }
  v9 = a2[1];
  v10 = *a2;
  if ( (char *)v9 - (char *)*a2 == 8 )
  {
    result = (const struct ProvPackage **)ProvPackageValidator::CheckPackageValid(v6, *v10, a3, v7);
    if ( (_DWORD)result == -2147467260 || (_DWORD)result == -2147024713 )
    {
      v20 = wil::verify_hresult<long>((unsigned int)result);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x28,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpackagevalidator.cpp",
        (const char *)v20,
        a4);
    }
    if ( (int)result < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2B,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpackagevalidator.cpp",
        (const char *)(unsigned int)result,
        a4);
  }
  else
  {
    if ( v10 != v9 )
    {
      while ( 1 )
      {
        v12 = v10 + 1;
        if ( (int)ProvPackageValidator::CheckPackageValid(v6, *v10, a3, v7) < 0 )
          break;
        ++v10;
        if ( v12 == v9 )
          goto LABEL_22;
      }
      while ( v12 != v9 )
      {
        if ( (int)ProvPackageValidator::CheckPackageValid(v6, *v12, a3, v7) >= 0 )
        {
          v13 = v10++;
          if ( v13 != v12 )
          {
            v14 = *v12;
            *v12 = 0;
            v15 = *v13;
            if ( v14 != *v13 )
            {
              if ( v15 )
                (*(void (__fastcall **)(const struct ProvPackage *, __int64))(*(_QWORD *)v15 + 64LL))(v15, 1);
              *v13 = v14;
            }
            v6 = v23;
          }
          v7 = a4;
        }
        ++v12;
      }
    }
LABEL_22:
    std::vector<std::unique_ptr<ProvPackage>>::erase(a2, &v23, v10, a2[1]);
    result = a2[1];
    if ( *a2 == result )
    {
      if ( *(_DWORD *)g_hProvTraceProvider > 2u && (unsigned __int8)tlgKeywordOn(g_hProvTraceProvider, 0) )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          v16,
          &byte_1800410DF,
          0);
      v17 = wil::verify_hresult<long>(2147942659LL);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x3D,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\provpackagevalidator.cpp",
        (const char *)v17,
        a4);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180024064  push    rbp
0x180024066  push    rbx
0x180024067  push    rsi
0x180024068  push    rdi
0x180024069  push    r12
0x18002406b  push    r13
0x18002406d  push    r14
0x18002406f  push    r15
0x180024071  lea     rbp, [rsp-1Fh]
0x180024076  sub     rsp, 0A8h
0x18002407d  mov     rax, cs:__security_cookie
0x180024084  xor     rax, rsp
0x180024087  mov     [rbp+57h+var_50], rax
0x18002408b  movups  xmm0, xmmword ptr cs:aSecurity; "Security"
0x180024092  movzx   eax, word ptr cs:aSecurity+10h; ""
0x180024099  mov     r13d, r8d
0x18002409c  movups  xmm1, xmmword ptr cs:aAllowaddprovis+10h; "ProvisioningPackage"
0x1800240a3  mov     rsi, rdx
0x1800240a6  mov     r12, rcx
0x1800240a9  movups  [rbp+57h+var_A0], xmm0
0x1800240ad  mov     [rbp+57h+var_B8], rcx
0x1800240b1  lea     r8, [rbp+57h+var_BC]
0x1800240b5  movups  xmm0, xmmword ptr cs:aAllowaddprovis; "AllowAddProvisioningPackage"
0x1800240bc  lea     rdx, [rbp+57h+var_88]
0x1800240c0  mov     r15d, r9d
0x1800240c3  movups  [rbp+57h+var_78], xmm1
0x1800240c7  lea     rcx, [rbp+57h+var_A0]
0x1800240cb  mov     [rbp+57h+var_C0], r9d
0x1800240cf  movsd   xmm1, qword ptr cs:aAllowaddprovis+30h; "age"
0x1800240d7  movups  [rbp+57h+var_88], xmm0
0x1800240db  mov     [rbp+57h+var_90], ax
0x1800240df  movups  xmm0, xmmword ptr cs:aAllowaddprovis+20h; "ningPackage"
0x1800240e6  mov     [rbp+57h+var_BC], 0
0x1800240ed  movsd   [rbp+57h+var_58], xmm1
0x1800240f2  movups  [rbp+57h+var_68], xmm0
0x1800240f6  call    cs:__imp_PolicyManager_GetPolicyInt
0x1800240fc  test    eax, eax
0x1800240fe  js      loc_180024285
0x180024104  cmp     [rbp+57h+var_BC], 0
0x180024108  jz      loc_18002429E
0x18002410e  mov     r14, [rsi+8]
0x180024112  mov     rbx, [rsi]
0x180024115  mov     rax, r14
0x180024118  sub     rax, rbx
0x18002411b  cmp     rax, 8
0x18002411f  jnz     short loc_180024155
0x180024121  mov     rdx, [rbx]; struct ProvPackage *
0x180024124  mov     r9d, r15d; int
0x180024127  mov     r8d, r13d; unsigned int
0x18002412a  mov     rcx, r12; this
0x18002412d  call    ?CheckPackageValid@ProvPackageValidator@@QEAAJAEBVProvPackage@@KH@Z; ProvPackageValidator::CheckPackageValid(ProvPackage const &,ulong,int)
0x180024132  cmp     eax, 80004004h
0x180024137  jz      loc_1800242F8
0x18002413d  cmp     eax, 800700B7h
0x180024142  jz      loc_1800242F8
0x180024148  test    eax, eax
0x18002414a  js      loc_18002426C
0x180024150  jmp     loc_1800241FA
0x180024155  cmp     rbx, r14
0x180024158  jz      loc_1800241DE
0x18002415e  mov     rdx, [rbx]; struct ProvPackage *
0x180024161  lea     rdi, [rbx+8]
0x180024165  mov     r9d, r15d; int
0x180024168  mov     r8d, r13d; unsigned int
0x18002416b  mov     rcx, r12; this
0x18002416e  call    ?CheckPackageValid@ProvPackageValidator@@QEAAJAEBVProvPackage@@KH@Z; ProvPackageValidator::CheckPackageValid(ProvPackage const &,ulong,int)
0x180024173  test    eax, eax
0x180024175  js      short loc_1800241D9
0x180024177  mov     rbx, rdi
0x18002417a  cmp     rdi, r14
0x18002417d  jnz     short loc_18002415E
0x18002417f  jmp     short loc_1800241DE
0x180024181  mov     rdx, [rdi]; struct ProvPackage *
0x180024184  mov     r9d, r15d; int
0x180024187  mov     r8d, r13d; unsigned int
0x18002418a  mov     rcx, r12; this
0x18002418d  call    ?CheckPackageValid@ProvPackageValidator@@QEAAJAEBVProvPackage@@KH@Z; ProvPackageValidator::CheckPackageValid(ProvPackage const &,ulong,int)
0x180024192  test    eax, eax
0x180024194  js      short loc_1800241D5
0x180024196  mov     r15, rbx
0x180024199  add     rbx, 8
0x18002419d  cmp     r15, rdi
0x1800241a0  jz      short loc_1800241D1
0x1800241a2  mov     r12, [rdi]
0x1800241a5  mov     qword ptr [rdi], 0
0x1800241ac  mov     rcx, [r15]
0x1800241af  cmp     r12, rcx
0x1800241b2  jz      short loc_1800241CD
0x1800241b4  test    rcx, rcx
0x1800241b7  jz      short loc_1800241CA
0x1800241b9  mov     rax, [rcx]
0x1800241bc  mov     edx, 1
0x1800241c1  mov     rax, [rax+40h]
0x1800241c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800241ca  mov     [r15], r12
0x1800241cd  mov     r12, [rbp+57h+var_B8]
0x1800241d1  mov     r15d, [rbp+57h+var_C0]
0x1800241d5  add     rdi, 8
0x1800241d9  cmp     rdi, r14
0x1800241dc  jnz     short loc_180024181
0x1800241de  mov     r9, [rsi+8]
0x1800241e2  lea     rdx, [rbp+57h+var_B8]
0x1800241e6  mov     r8, rbx
0x1800241e9  mov     rcx, rsi
0x1800241ec  call    ?erase@?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@std@@@std@@@2@0@Z; std::vector<std::unique_ptr<ProvPackage>>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::unique_ptr<ProvPackage>>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::unique_ptr<ProvPackage>>>>)
0x1800241f1  mov     rax, [rsi+8]
0x1800241f5  cmp     [rsi], rax
0x1800241f8  jz      short loc_18002421A
0x1800241fa  mov     rcx, [rbp+57h+var_50]
0x1800241fe  xor     rcx, rsp; StackCookie
0x180024201  call    __security_check_cookie
0x180024206  add     rsp, 0A8h
0x18002420d  pop     r15
0x18002420f  pop     r14
0x180024211  pop     r13
0x180024213  pop     r12
0x180024215  pop     rdi
0x180024216  pop     rsi
0x180024217  pop     rbx
0x180024218  pop     rbp
0x180024219  retn
0x18002421a  mov     r9, cs:g_hProvTraceProvider
0x180024221  mov     eax, [r9]
0x180024224  cmp     eax, 2
0x180024227  jbe     short loc_180024249
0x180024229  xor     edx, edx
0x18002422b  mov     rcx, r9
0x18002422e  call    _tlgKeywordOn
0x180024233  test    al, al
0x180024235  jz      short loc_180024249
0x180024237  xor     r8d, r8d
0x18002423a  lea     rdx, byte_1800410DF
0x180024241  mov     rcx, r9
0x180024244  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180024249  mov     ecx, 80070103h
0x18002424e  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x180024253  mov     rcx, [rbp+5Fh]; this
0x180024257  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x18002425e  mov     r9d, eax; char *
0x180024261  mov     edx, 3Dh ; '='; void *
0x180024266  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002426c  mov     rcx, [rbp+5Fh]; this
0x180024270  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x180024277  mov     r9d, eax; char *
0x18002427a  mov     edx, 2Bh ; '+'; void *
0x18002427f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180024285  mov     rcx, [rbp+5Fh]; this
0x180024289  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x180024290  mov     r9d, eax; char *
0x180024293  mov     edx, 101h; void *
0x180024298  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002429e  mov     r9, cs:g_hProvTraceProvider
0x1800242a5  mov     eax, [r9]
0x1800242a8  cmp     eax, 5
0x1800242ab  jbe     short loc_1800242CD
0x1800242ad  xor     edx, edx
0x1800242af  mov     rcx, r9
0x1800242b2  call    _tlgKeywordOn
0x1800242b7  test    al, al
0x1800242b9  jz      short loc_1800242CD
0x1800242bb  xor     r8d, r8d
0x1800242be  lea     rdx, unk_180041100
0x1800242c5  mov     rcx, r9
0x1800242c8  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800242cd  mov     rcx, rsi
0x1800242d0  call    ?clear@?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@QEAAXXZ; std::vector<std::unique_ptr<ProvPackage>>::clear(void)
0x1800242d5  mov     ecx, 80070005h
0x1800242da  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800242df  mov     rcx, [rbp+5Fh]; this
0x1800242e3  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x1800242ea  mov     r9d, eax; char *
0x1800242ed  mov     edx, 1Eh; void *
0x1800242f2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800242f8  mov     ecx, eax
0x1800242fa  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800242ff  mov     rcx, [rbp+5Fh]; this
0x180024303  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\prov\\lib\\provpacka"...
0x18002430a  mov     r9d, eax; char *
0x18002430d  mov     edx, 28h ; '('; void *
0x180024312  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
