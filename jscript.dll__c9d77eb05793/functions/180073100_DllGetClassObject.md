# DllGetClassObject

- ea: `0x180073100`
- end: `0x180073374`
- name: `DllGetClassObject`
- size: `628`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800491f8`
- `0x180052a9c`
- `0x1800671e0`
- `0x180067254`
- `0x180072e14`
- `0x180072f50`
- `0x180073100`
- `0x1800942d0`
- `0x180096010`

## import_xrefs

- `ole32!CoGetClassObject` at `0x180073268`
- `ole32!CoGetClassObject` at `0x180073268`

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
        v13 = (IID)xmmword_1800A5720;
      }
      else if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_JScriptAuthor.Data1
             && *(_QWORD *)rclsid->Data4 == *(_QWORD *)CLSID_JScriptAuthor.Data4 )
      {
        v13 = (IID)xmmword_1800A5740;
      }
      else if ( *(_QWORD *)&rclsid->Data1 == *(_QWORD *)&CLSID_JScriptEncode.Data1
             && *(_QWORD *)rclsid->Data4 == *(_QWORD *)CLSID_JScriptEncode.Data4 )
      {
        v13 = (IID)xmmword_1800A5750;
      }
      else
      {
        if ( *(_QWORD *)&rclsid->Data1 != *(_QWORD *)&CLSID_JScriptCompact.Data1
          || *(_QWORD *)rclsid->Data4 != *(_QWORD *)CLSID_JScriptCompact.Data4 )
        {
          return CoGetClassObject(&rclsida, 7u, 0, v4, ppv);
        }
        v13 = (IID)xmmword_1800A5730;
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
0x180073100  mov     [rsp+arg_0], rbx
0x180073105  push    rbp
0x180073106  push    rsi
0x180073107  push    rdi
0x180073108  sub     rsp, 50h
0x18007310c  mov     rax, cs:__security_cookie
0x180073113  xor     rax, rsp
0x180073116  mov     [rsp+68h+var_20], rax
0x18007311b  mov     rsi, r8
0x18007311e  mov     [rsp+68h+var_38], 0
0x180073126  mov     rbp, rdx
0x180073129  mov     rbx, rcx
0x18007312c  mov     dl, 1
0x18007312e  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ScriptingEngines_GroupPolicyJScriptReplacement@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ScriptingEngines_GroupPolicyJScriptReplacement@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScriptingEngines_GroupPolicyJScriptReplacement> `wil::Feature<__WilFeatureTraits_Feature_ScriptingEngines_GroupPolicyJScriptReplacement>::GetImpl(void)'::`2'::impl
0x180073135  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_ScriptingEngines_GroupPolicyJScriptReplacement@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ScriptingEngines_GroupPolicyJScriptReplacement>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18007313a  mov     rax, [rbx]
0x18007313d  cmp     rax, qword ptr cs:CLSID_JScript.Data1
0x180073144  jnz     short loc_180073153
0x180073146  mov     rax, [rbx+8]
0x18007314a  cmp     rax, qword ptr cs:CLSID_JScript.Data4
0x180073151  jz      short loc_1800731A6
0x180073153  mov     rdx, qword ptr cs:CLSID_JScriptAuthor.Data1
0x18007315a  mov     rcx, qword ptr cs:CLSID_JScriptAuthor.Data4
0x180073161  cmp     [rbx], rdx
0x180073164  jnz     short loc_18007316C
0x180073166  cmp     [rbx+8], rcx
0x18007316a  jz      short loc_1800731A6
0x18007316c  mov     r10, qword ptr cs:CLSID_JScriptEncode.Data1
0x180073173  mov     r8, qword ptr cs:CLSID_JScriptEncode.Data4
0x18007317a  cmp     [rbx], r10
0x18007317d  jnz     short loc_180073185
0x18007317f  cmp     [rbx+8], r8
0x180073183  jz      short loc_1800731A6
0x180073185  mov     r9, qword ptr cs:CLSID_JScriptCompact.Data1
0x18007318c  mov     rax, qword ptr cs:CLSID_JScriptCompact.Data4
0x180073193  cmp     [rbx], r9
0x180073196  jnz     loc_18007329F
0x18007319c  cmp     [rbx+8], rax
0x1800731a0  jnz     loc_18007329F
0x1800731a6  lea     rcx, [rsp+68h+var_38]; int *
0x1800731ab  call    ?IsJScript9LegacyEnabled@@YAXPEAH@Z; IsJScript9LegacyEnabled(int *)
0x1800731b0  cmp     [rsp+68h+var_38], 0
0x1800731b5  jz      loc_180073275
0x1800731bb  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800731c2  mov     rax, [rbx]
0x1800731c5  cmp     rax, qword ptr cs:CLSID_JScript.Data1
0x1800731cc  movdqu  xmmword ptr [rsp+68h+rclsid.Data1], xmm0
0x1800731d2  jnz     short loc_1800731EA
0x1800731d4  mov     rax, [rbx+8]
0x1800731d8  cmp     rax, qword ptr cs:CLSID_JScript.Data4
0x1800731df  jnz     short loc_1800731EA
0x1800731e1  movups  xmm0, cs:xmmword_1800A5720
0x1800731e8  jmp     short loc_18007324E
0x1800731ea  mov     rax, [rbx]
0x1800731ed  cmp     rax, qword ptr cs:CLSID_JScriptAuthor.Data1
0x1800731f4  jnz     short loc_18007320C
0x1800731f6  mov     rax, [rbx+8]
0x1800731fa  cmp     rax, qword ptr cs:CLSID_JScriptAuthor.Data4
0x180073201  jnz     short loc_18007320C
0x180073203  movups  xmm0, cs:xmmword_1800A5740
0x18007320a  jmp     short loc_18007324E
0x18007320c  mov     rax, [rbx]
0x18007320f  cmp     rax, qword ptr cs:CLSID_JScriptEncode.Data1
0x180073216  jnz     short loc_18007322E
0x180073218  mov     rax, [rbx+8]
0x18007321c  cmp     rax, qword ptr cs:CLSID_JScriptEncode.Data4
0x180073223  jnz     short loc_18007322E
0x180073225  movups  xmm0, cs:xmmword_1800A5750
0x18007322c  jmp     short loc_18007324E
0x18007322e  mov     rax, [rbx]
0x180073231  cmp     rax, qword ptr cs:CLSID_JScriptCompact.Data1
0x180073238  jnz     short loc_180073254
0x18007323a  mov     rax, [rbx+8]
0x18007323e  cmp     rax, qword ptr cs:CLSID_JScriptCompact.Data4
0x180073245  jnz     short loc_180073254
0x180073247  movups  xmm0, cs:xmmword_1800A5730
0x18007324e  movdqu  xmmword ptr [rsp+68h+rclsid.Data1], xmm0
0x180073254  xor     r8d, r8d; pvReserved
0x180073257  mov     [rsp+68h+ppv], rsi; ppv
0x18007325c  mov     r9, rbp; riid
0x18007325f  lea     rcx, [rsp+68h+rclsid]; rclsid
0x180073264  lea     edx, [r8+7]; dwClsContext
0x180073268  call    cs:__imp_CoGetClassObject
0x18007326e  mov     ebx, eax
0x180073270  jmp     loc_18007333B
0x180073275  mov     rcx, qword ptr cs:CLSID_JScriptAuthor.Data4
0x18007327c  mov     rdx, qword ptr cs:CLSID_JScriptAuthor.Data1
0x180073283  mov     r8, qword ptr cs:CLSID_JScriptEncode.Data4
0x18007328a  mov     r10, qword ptr cs:CLSID_JScriptEncode.Data1
0x180073291  mov     rax, qword ptr cs:CLSID_JScriptCompact.Data4
0x180073298  mov     r9, qword ptr cs:CLSID_JScriptCompact.Data1
0x18007329f  test    rsi, rsi
0x1800732a2  jz      loc_180073355
0x1800732a8  cmp     [rbx], rdx
0x1800732ab  jnz     short loc_1800732BA
0x1800732ad  cmp     [rbx+8], rcx
0x1800732b1  jnz     short loc_1800732BA
0x1800732b3  call    ?CreateAuthorClassFactory@@YAPEAVCClassFactory@@XZ; CreateAuthorClassFactory(void)
0x1800732b8  jmp     short loc_1800732E3
0x1800732ba  cmp     [rbx], r10
0x1800732bd  jnz     short loc_1800732CC
0x1800732bf  cmp     [rbx+8], r8
0x1800732c3  jnz     short loc_1800732CC
0x1800732c5  call    ?CreateEncodeClassFactory@@YAPEAVCClassFactory@@XZ; CreateEncodeClassFactory(void)
0x1800732ca  jmp     short loc_1800732E3
0x1800732cc  cmp     [rbx], r9
0x1800732cf  jnz     short loc_1800732DE
0x1800732d1  cmp     [rbx+8], rax
0x1800732d5  jnz     short loc_1800732DE
0x1800732d7  call    ?CreateCompactClassFactory@@YAPEAVCClassFactory@@XZ; CreateCompactClassFactory(void)
0x1800732dc  jmp     short loc_1800732E3
0x1800732de  call    ?CreateClassFactory@@YAPEAVCClassFactory@@XZ; CreateClassFactory(void)
0x1800732e3  mov     rdi, rax
0x1800732e6  test    rax, rax
0x1800732e9  jnz     short loc_1800732F5
0x1800732eb  mov     [rsi], rax
0x1800732ee  mov     eax, 8007000Eh
0x1800732f3  jmp     short loc_18007335A
0x1800732f5  mov     rax, [rdi]
0x1800732f8  mov     rcx, rdi
0x1800732fb  mov     rax, [rax+28h]
0x1800732ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073304  mov     rcx, [rbx]
0x180073307  cmp     rcx, [rax]
0x18007330a  jnz     short loc_18007333F
0x18007330c  mov     rcx, [rbx+8]
0x180073310  cmp     rcx, [rax+8]
0x180073314  jnz     short loc_18007333F
0x180073316  mov     rax, [rdi]
0x180073319  mov     r8, rsi
0x18007331c  mov     rdx, rbp
0x18007331f  mov     rcx, rdi
0x180073322  mov     rax, [rax]
0x180073325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007332a  mov     ebx, eax
0x18007332c  mov     rcx, rdi
0x18007332f  mov     rax, [rdi]
0x180073332  mov     rax, [rax+10h]
0x180073336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007333b  mov     eax, ebx
0x18007333d  jmp     short loc_18007335A
0x18007333f  mov     qword ptr [rsi], 0
0x180073346  mov     rcx, rdi
0x180073349  mov     rax, [rdi]
0x18007334c  mov     rax, [rax+10h]
0x180073350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073355  mov     eax, 80070057h
0x18007335a  mov     rcx, [rsp+68h+var_20]
0x18007335f  xor     rcx, rsp; StackCookie
0x180073362  call    __security_check_cookie
0x180073367  mov     rbx, [rsp+68h+arg_0]
0x18007336c  add     rsp, 50h
0x180073370  pop     rdi
0x180073371  pop     rsi
0x180073372  pop     rbp
0x180073373  retn
```
