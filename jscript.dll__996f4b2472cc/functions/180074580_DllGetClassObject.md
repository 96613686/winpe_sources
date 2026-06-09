# DllGetClassObject

- ea: `0x180074580`
- end: `0x1800747fb`
- name: `DllGetClassObject`
- size: `635`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180049f44`
- `0x180053860`
- `0x1800684a0`
- `0x180068518`
- `0x180074264`
- `0x1800743cc`
- `0x180074580`
- `0x1800966e0`
- `0x180098010`

## import_xrefs

- `ole32!CoGetClassObject` at `0x1800746e8`
- `ole32!CoGetClassObject` at `0x1800746e8`

## pseudocode

```c
HRESULT __stdcall DllGetClassObject(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  const IID *v4; // rbp
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r10
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 v11; // rax
  bool v12; // zf
  IID v13; // xmm0
  HRESULT v14; // ebx
  struct CClassFactory *AuthorClassFactory; // rax
  struct CClassFactory *v16; // rdi
  _QWORD *v18; // rax
  int v19; // [rsp+30h] [rbp-38h] BYREF
  IID rclsida; // [rsp+38h] [rbp-30h] BYREF

  v19 = 0;
  v4 = riid;
  LOBYTE(riid) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScriptingEngines_GroupPolicyJScriptReplacement>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_ScriptingEngines_GroupPolicyJScriptReplacement>::GetImpl'::`2'::impl,
    riid);
  if ( *(_OWORD *)rclsid == *(_OWORD *)&CLSID_JScript
    || (v6 = *(_QWORD *)&CLSID_JScriptAuthor.Data1,
        v7 = *(_QWORD *)CLSID_JScriptAuthor.Data4,
        *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_JScriptAuthor.Data1)
    && *(_QWORD *)rclsid->Data4 == *(_QWORD *)CLSID_JScriptAuthor.Data4
    || (v8 = *(_QWORD *)&CLSID_JScriptEncode.Data1,
        v9 = *(_QWORD *)CLSID_JScriptEncode.Data4,
        *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_JScriptEncode.Data1)
    && *(_QWORD *)rclsid->Data4 == *(_QWORD *)CLSID_JScriptEncode.Data4
    || (v10 = *(_QWORD *)&CLSID_JScriptCompact.Data1,
        v11 = *(_QWORD *)CLSID_JScriptCompact.Data4,
        *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_JScriptCompact.Data1)
    && *(_QWORD *)rclsid->Data4 == *(_QWORD *)CLSID_JScriptCompact.Data4 )
  {
    IsJScript9LegacyEnabled(&v19);
    if ( v19 )
    {
      v12 = *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_JScript.Data1;
      rclsida = GUID_NULL;
      if ( v12 && *(_QWORD *)rclsid->Data4 == *(_QWORD *)CLSID_JScript.Data4 )
      {
        v13 = (IID)xmmword_1800A7710;
      }
      else if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_JScriptAuthor.Data1
             && *(_QWORD *)rclsid->Data4 == *(_QWORD *)CLSID_JScriptAuthor.Data4 )
      {
        v13 = (IID)xmmword_1800A7730;
      }
      else if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_JScriptEncode.Data1
             && *(_QWORD *)rclsid->Data4 == *(_QWORD *)CLSID_JScriptEncode.Data4 )
      {
        v13 = (IID)xmmword_1800A7740;
      }
      else
      {
        if ( *(_QWORD *)&rclsid->Data1 != *(_QWORD *)&CLSID_JScriptCompact.Data1
          || *(_QWORD *)rclsid->Data4 != *(_QWORD *)CLSID_JScriptCompact.Data4 )
        {
          return CoGetClassObject(&rclsida, 7u, 0, v4, ppv);
        }
        v13 = (IID)xmmword_1800A7720;
      }
      rclsida = v13;
      return CoGetClassObject(&rclsida, 7u, 0, v4, ppv);
    }
    v7 = *(_QWORD *)CLSID_JScriptAuthor.Data4;
    v6 = *(_QWORD *)&CLSID_JScriptAuthor.Data1;
    v9 = *(_QWORD *)CLSID_JScriptEncode.Data4;
    v8 = *(_QWORD *)&CLSID_JScriptEncode.Data1;
    v11 = *(_QWORD *)CLSID_JScriptCompact.Data4;
    v10 = *(_QWORD *)&CLSID_JScriptCompact.Data1;
  }
  if ( ppv )
  {
    if ( *(_QWORD *)&rclsid->Data1 == v6 && *(_QWORD *)rclsid->Data4 == v7 )
    {
      AuthorClassFactory = CreateAuthorClassFactory();
    }
    else if ( *(_QWORD *)&rclsid->Data1 == v8 && *(_QWORD *)rclsid->Data4 == v9 )
    {
      AuthorClassFactory = CreateEncodeClassFactory();
    }
    else if ( *(_QWORD *)&rclsid->Data1 == v10 && *(_QWORD *)rclsid->Data4 == v11 )
    {
      AuthorClassFactory = CreateCompactClassFactory();
    }
    else
    {
      AuthorClassFactory = CreateClassFactory();
    }
    v16 = AuthorClassFactory;
    if ( !AuthorClassFactory )
    {
      *ppv = 0;
      return -2147024882;
    }
    v18 = (_QWORD *)(*(__int64 (__fastcall **)(struct CClassFactory *))(*(_QWORD *)AuthorClassFactory + 40LL))(AuthorClassFactory);
    if ( *(_QWORD *)&rclsid->Data1 == *v18 && *(_QWORD *)rclsid->Data4 == v18[1] )
    {
      v14 = (**(__int64 (__fastcall ***)(struct CClassFactory *, const IID *, LPVOID *))v16)(v16, v4, ppv);
      (*(void (__fastcall **)(struct CClassFactory *))(*(_QWORD *)v16 + 16LL))(v16);
      return v14;
    }
    *ppv = 0;
    (*(void (__fastcall **)(struct CClassFactory *))(*(_QWORD *)v16 + 16LL))(v16);
  }
  return -2147024809;
}

```

## disassembly

```asm
0x180074580  mov     [rsp+arg_0], rbx
0x180074585  push    rbp
0x180074586  push    rsi
0x180074587  push    rdi
0x180074588  sub     rsp, 50h
0x18007458c  mov     rax, cs:__security_cookie
0x180074593  xor     rax, rsp
0x180074596  mov     [rsp+68h+var_20], rax
0x18007459b  mov     rsi, r8
0x18007459e  mov     [rsp+68h+var_38], 0
0x1800745a6  mov     rbp, rdx
0x1800745a9  mov     rbx, rcx
0x1800745ac  mov     dl, 1
0x1800745ae  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ScriptingEngines_GroupPolicyJScriptReplacement@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ScriptingEngines_GroupPolicyJScriptReplacement@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScriptingEngines_GroupPolicyJScriptReplacement> `wil::Feature<__WilFeatureTraits_Feature_ScriptingEngines_GroupPolicyJScriptReplacement>::GetImpl(void)'::`2'::impl
0x1800745b5  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ScriptingEngines_GroupPolicyJScriptReplacement@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScriptingEngines_GroupPolicyJScriptReplacement>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800745ba  mov     rax, [rbx]
0x1800745bd  cmp     rax, qword ptr cs:CLSID_JScript.Data1
0x1800745c4  jnz     short loc_1800745D3
0x1800745c6  mov     rax, [rbx+8]
0x1800745ca  cmp     rax, qword ptr cs:CLSID_JScript.Data4
0x1800745d1  jz      short loc_180074626
0x1800745d3  mov     rdx, qword ptr cs:CLSID_JScriptAuthor.Data1
0x1800745da  mov     rcx, qword ptr cs:CLSID_JScriptAuthor.Data4
0x1800745e1  cmp     [rbx], rdx
0x1800745e4  jnz     short loc_1800745EC
0x1800745e6  cmp     [rbx+8], rcx
0x1800745ea  jz      short loc_180074626
0x1800745ec  mov     r10, qword ptr cs:CLSID_JScriptEncode.Data1
0x1800745f3  mov     r8, qword ptr cs:CLSID_JScriptEncode.Data4
0x1800745fa  cmp     [rbx], r10
0x1800745fd  jnz     short loc_180074605
0x1800745ff  cmp     [rbx+8], r8
0x180074603  jz      short loc_180074626
0x180074605  mov     r9, qword ptr cs:CLSID_JScriptCompact.Data1
0x18007460c  mov     rax, qword ptr cs:CLSID_JScriptCompact.Data4
0x180074613  cmp     [rbx], r9
0x180074616  jnz     loc_180074725
0x18007461c  cmp     [rbx+8], rax
0x180074620  jnz     loc_180074725
0x180074626  lea     rcx, [rsp+68h+var_38]; int *
0x18007462b  call    ?IsJScript9LegacyEnabled@@YAXPEAH@Z; IsJScript9LegacyEnabled(int *)
0x180074630  cmp     [rsp+68h+var_38], 0
0x180074635  jz      loc_1800746FB
0x18007463b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180074642  mov     rax, [rbx]
0x180074645  cmp     rax, qword ptr cs:CLSID_JScript.Data1
0x18007464c  movdqu  xmmword ptr [rsp+68h+rclsid.Data1], xmm0
0x180074652  jnz     short loc_18007466A
0x180074654  mov     rax, [rbx+8]
0x180074658  cmp     rax, qword ptr cs:CLSID_JScript.Data4
0x18007465f  jnz     short loc_18007466A
0x180074661  movups  xmm0, cs:xmmword_1800A7710
0x180074668  jmp     short loc_1800746CE
0x18007466a  mov     rax, [rbx]
0x18007466d  cmp     rax, qword ptr cs:CLSID_JScriptAuthor.Data1
0x180074674  jnz     short loc_18007468C
0x180074676  mov     rax, [rbx+8]
0x18007467a  cmp     rax, qword ptr cs:CLSID_JScriptAuthor.Data4
0x180074681  jnz     short loc_18007468C
0x180074683  movups  xmm0, cs:xmmword_1800A7730
0x18007468a  jmp     short loc_1800746CE
0x18007468c  mov     rax, [rbx]
0x18007468f  cmp     rax, qword ptr cs:CLSID_JScriptEncode.Data1
0x180074696  jnz     short loc_1800746AE
0x180074698  mov     rax, [rbx+8]
0x18007469c  cmp     rax, qword ptr cs:CLSID_JScriptEncode.Data4
0x1800746a3  jnz     short loc_1800746AE
0x1800746a5  movups  xmm0, cs:xmmword_1800A7740
0x1800746ac  jmp     short loc_1800746CE
0x1800746ae  mov     rax, [rbx]
0x1800746b1  cmp     rax, qword ptr cs:CLSID_JScriptCompact.Data1
0x1800746b8  jnz     short loc_1800746D4
0x1800746ba  mov     rax, [rbx+8]
0x1800746be  cmp     rax, qword ptr cs:CLSID_JScriptCompact.Data4
0x1800746c5  jnz     short loc_1800746D4
0x1800746c7  movups  xmm0, cs:xmmword_1800A7720
0x1800746ce  movdqu  xmmword ptr [rsp+68h+rclsid.Data1], xmm0
0x1800746d4  xor     r8d, r8d; pvReserved
0x1800746d7  mov     [rsp+68h+ppv], rsi; ppv
0x1800746dc  mov     r9, rbp; riid
0x1800746df  lea     rcx, [rsp+68h+rclsid]; rclsid
0x1800746e4  lea     edx, [r8+7]; dwClsContext
0x1800746e8  call    cs:__imp_CoGetClassObject
0x1800746ef  nop     dword ptr [rax+rax+00h]
0x1800746f4  mov     ebx, eax
0x1800746f6  jmp     loc_1800747C1
0x1800746fb  mov     rcx, qword ptr cs:CLSID_JScriptAuthor.Data4
0x180074702  mov     rdx, qword ptr cs:CLSID_JScriptAuthor.Data1
0x180074709  mov     r8, qword ptr cs:CLSID_JScriptEncode.Data4
0x180074710  mov     r10, qword ptr cs:CLSID_JScriptEncode.Data1
0x180074717  mov     rax, qword ptr cs:CLSID_JScriptCompact.Data4
0x18007471e  mov     r9, qword ptr cs:CLSID_JScriptCompact.Data1
0x180074725  test    rsi, rsi
0x180074728  jz      loc_1800747DB
0x18007472e  cmp     [rbx], rdx
0x180074731  jnz     short loc_180074740
0x180074733  cmp     [rbx+8], rcx
0x180074737  jnz     short loc_180074740
0x180074739  call    ?CreateAuthorClassFactory@@YAPEAVCClassFactory@@XZ; CreateAuthorClassFactory(void)
0x18007473e  jmp     short loc_180074769
0x180074740  cmp     [rbx], r10
0x180074743  jnz     short loc_180074752
0x180074745  cmp     [rbx+8], r8
0x180074749  jnz     short loc_180074752
0x18007474b  call    ?CreateEncodeClassFactory@@YAPEAVCClassFactory@@XZ; CreateEncodeClassFactory(void)
0x180074750  jmp     short loc_180074769
0x180074752  cmp     [rbx], r9
0x180074755  jnz     short loc_180074764
0x180074757  cmp     [rbx+8], rax
0x18007475b  jnz     short loc_180074764
0x18007475d  call    ?CreateCompactClassFactory@@YAPEAVCClassFactory@@XZ; CreateCompactClassFactory(void)
0x180074762  jmp     short loc_180074769
0x180074764  call    ?CreateClassFactory@@YAPEAVCClassFactory@@XZ; CreateClassFactory(void)
0x180074769  mov     rdi, rax
0x18007476c  test    rax, rax
0x18007476f  jnz     short loc_18007477B
0x180074771  mov     [rsi], rax
0x180074774  mov     eax, 8007000Eh
0x180074779  jmp     short loc_1800747E0
0x18007477b  mov     rax, [rdi]
0x18007477e  mov     rcx, rdi
0x180074781  mov     rax, [rax+28h]
0x180074785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007478a  mov     rcx, [rbx]
0x18007478d  cmp     rcx, [rax]
0x180074790  jnz     short loc_1800747C5
0x180074792  mov     rcx, [rbx+8]
0x180074796  cmp     rcx, [rax+8]
0x18007479a  jnz     short loc_1800747C5
0x18007479c  mov     rax, [rdi]
0x18007479f  mov     r8, rsi
0x1800747a2  mov     rdx, rbp
0x1800747a5  mov     rcx, rdi
0x1800747a8  mov     rax, [rax]
0x1800747ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800747b0  mov     ebx, eax
0x1800747b2  mov     rcx, rdi
0x1800747b5  mov     rax, [rdi]
0x1800747b8  mov     rax, [rax+10h]
0x1800747bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800747c1  mov     eax, ebx
0x1800747c3  jmp     short loc_1800747E0
0x1800747c5  mov     qword ptr [rsi], 0
0x1800747cc  mov     rcx, rdi
0x1800747cf  mov     rax, [rdi]
0x1800747d2  mov     rax, [rax+10h]
0x1800747d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800747db  mov     eax, 80070057h
0x1800747e0  mov     rcx, [rsp+68h+var_20]
0x1800747e5  xor     rcx, rsp; StackCookie
0x1800747e8  call    __security_check_cookie
0x1800747ed  mov     rbx, [rsp+68h+arg_0]
0x1800747f2  add     rsp, 50h
0x1800747f6  pop     rdi
0x1800747f7  pop     rsi
0x1800747f8  pop     rbp
0x1800747f9  retn
```
