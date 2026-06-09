# EnrollmentsUpnNode::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)

- ea: `0x180014870`
- end: `0x180014dcf`
- name: `?Add@EnrollmentsUpnNode@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z`
- size: `1375`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180006974`
- `0x180013844`
- `0x180014870`
- `0x180022e48`
- `0x180026248`
- `0x180038010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18001495a`
- `msvcrt!_wcsicmp` at `0x1800149ce`
- `msvcrt!_wcsicmp` at `0x180014a42`
- `msvcrt!_wcsicmp` at `0x180014ab6`
- `msvcrt!_wcsicmp` at `0x180014b2a`
- `msvcrt!_wcsicmp` at `0x180014b9e`
- `msvcrt!_wcsicmp` at `0x180014c12`
- `msvcrt!_wcsicmp` at `0x180014c86`
- `msvcrt!_wcsicmp` at `0x180014cfa`
- `msvcrt!_wcsicmp` at `0x18001495a`
- `msvcrt!_wcsicmp` at `0x1800149ce`
- `msvcrt!_wcsicmp` at `0x180014a42`
- `msvcrt!_wcsicmp` at `0x180014ab6`
- `msvcrt!_wcsicmp` at `0x180014b2a`
- `msvcrt!_wcsicmp` at `0x180014b9e`
- `msvcrt!_wcsicmp` at `0x180014c12`
- `msvcrt!_wcsicmp` at `0x180014c86`
- `msvcrt!_wcsicmp` at `0x180014cfa`

## string_xrefs

- `0x180014a37`: `PolicyServiceFullURL`
- `0x1800149c3`: `DiscoveryServiceFullUrl`
- `0x180014aab`: `EnrollmentServiceFullURL`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EnrollmentsUpnNode::Add(
        _QWORD *a1,
        __int64 a2,
        unsigned int a3,
        __int128 *a4,
        __int64 a5,
        _DWORD *a6)
{
  int v10; // eax
  unsigned int v11; // edi
  __int64 v13; // rdx
  int v14; // ebx
  _DWORD *v15; // rdi
  int v16; // eax
  unsigned int v17; // r14d
  __int64 *v18; // rbx
  __int64 v19; // rcx
  __int64 *v20; // rbx
  __int64 v21; // rcx
  __int64 *v22; // rbx
  __int64 v23; // rcx
  __int64 *v24; // rbx
  __int64 v25; // rcx
  __int64 *v26; // rbx
  __int64 v27; // rcx
  __int64 *v28; // rbx
  __int64 v29; // rcx
  __int64 *v30; // rbx
  __int64 v31; // rcx
  __int64 *v32; // rbx
  __int64 v33; // rcx
  char *v34; // rax
  __int64 v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // rcx
  __int64 (__fastcall ***v38)(_QWORD, GUID *); // rcx
  int v39; // [rsp+20h] [rbp-50h]
  wchar_t *String1; // [rsp+30h] [rbp-40h] BYREF
  __int64 v41; // [rsp+38h] [rbp-38h] BYREF
  _QWORD *v42; // [rsp+40h] [rbp-30h] BYREF
  char v43; // [rsp+48h] [rbp-28h] BYREF
  __int128 v44; // [rsp+50h] [rbp-20h] BYREF
  __int64 v45; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]
  int v47; // [rsp+A8h] [rbp+38h] BYREF

  v47 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a2 + 136LL))(a2, &v47);
  v11 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x38,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\enrollmentsupnnode.cpp",
      (const char *)(unsigned int)v10,
      v39);
    return v11;
  }
  if ( v47 != 1 )
  {
    v13 = 57;
LABEL_5:
    v14 = -2147024809;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\enrollmentsupnnode.cpp",
      (const char *)(unsigned int)v14,
      v39);
    return (unsigned int)v14;
  }
  v15 = a6;
  if ( !a6 )
  {
    v13 = 58;
    goto LABEL_5;
  }
  String1 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, wchar_t **))(*(_QWORD *)a2 + 88LL))(a2, 0, &String1);
  v17 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3D,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\enrollmentsupnnode.cpp",
      (const char *)(unsigned int)v16,
      v39);
    return v17;
  }
  if ( !_wcsicmp(String1, L"Secret") )
  {
    v18 = a1 + 7;
    v19 = *v18;
    if ( *v18 )
    {
      *v18 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    v44 = *a4;
    v45 = *((_QWORD *)a4 + 2);
    v39 = (int)v18;
    v14 = GenericBStrNode::AddStringNode(a3, &v44, a5, v15);
    if ( v14 < 0 )
    {
      v13 = 66;
      goto LABEL_6;
    }
    return 0;
  }
  if ( !_wcsicmp(String1, L"DiscoveryServiceFullUrl") )
  {
    v20 = a1 + 8;
    v21 = *v20;
    if ( *v20 )
    {
      *v20 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    }
    v44 = *a4;
    v45 = *((_QWORD *)a4 + 2);
    v39 = (int)v20;
    v14 = GenericBStrNode::AddStringNode(a3, &v44, a5, v15);
    if ( v14 < 0 )
    {
      v13 = 71;
      goto LABEL_6;
    }
    return 0;
  }
  if ( !_wcsicmp(String1, L"PolicyServiceFullURL") )
  {
    v22 = a1 + 9;
    v23 = *v22;
    if ( *v22 )
    {
      *v22 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    v44 = *a4;
    v45 = *((_QWORD *)a4 + 2);
    v39 = (int)v22;
    v14 = GenericBStrNode::AddStringNode(a3, &v44, a5, v15);
    if ( v14 < 0 )
    {
      v13 = 76;
      goto LABEL_6;
    }
    return 0;
  }
  if ( !_wcsicmp(String1, L"EnrollmentServiceFullURL") )
  {
    v24 = a1 + 10;
    v25 = *v24;
    if ( *v24 )
    {
      *v24 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    }
    v44 = *a4;
    v45 = *((_QWORD *)a4 + 2);
    v39 = (int)v24;
    v14 = GenericBStrNode::AddStringNode(a3, &v44, a5, v15);
    if ( v14 < 0 )
    {
      v13 = 81;
      goto LABEL_6;
    }
    return 0;
  }
  if ( !_wcsicmp(String1, L"EnrollmentType") )
  {
    v26 = a1 + 12;
    v27 = *v26;
    if ( *v26 )
    {
      *v26 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
    }
    v44 = *a4;
    v45 = *((_QWORD *)a4 + 2);
    v39 = (int)v26;
    v14 = GenericBStrNode::AddStringNode(a3, &v44, a5, v15);
    if ( v14 < 0 )
    {
      v13 = 86;
      goto LABEL_6;
    }
    return 0;
  }
  if ( !_wcsicmp(String1, L"AuthPolicy") )
  {
    v28 = a1 + 11;
    v29 = *v28;
    if ( *v28 )
    {
      *v28 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    v44 = *a4;
    v45 = *((_QWORD *)a4 + 2);
    v39 = (int)v28;
    v14 = GenericIntNode::AddNode(a3, &v44, a5, v15);
    if ( v14 < 0 )
    {
      v13 = 91;
      goto LABEL_6;
    }
    return 0;
  }
  if ( !_wcsicmp(String1, L"DomainUsername") )
  {
    v30 = a1 + 13;
    v31 = *v30;
    if ( *v30 )
    {
      *v30 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    }
    v44 = *a4;
    v45 = *((_QWORD *)a4 + 2);
    v39 = (int)v30;
    v14 = GenericBStrNode::AddStringNode(a3, &v44, a5, v15);
    if ( v14 < 0 )
    {
      v13 = 96;
      goto LABEL_6;
    }
    return 0;
  }
  if ( !_wcsicmp(String1, L"EnrollmentID") )
  {
    v32 = a1 + 14;
    v33 = *v32;
    if ( *v32 )
    {
      *v32 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    }
    v44 = *a4;
    v45 = *((_QWORD *)a4 + 2);
    v39 = (int)v32;
    v14 = GenericBStrNode::AddStringNode(a3, &v44, a5, v15);
    if ( v14 < 0 )
    {
      v13 = 101;
      goto LABEL_6;
    }
    return 0;
  }
  if ( !_wcsicmp(String1, L"EnrollDevice") )
  {
    v42 = a1;
    v34 = (char *)Microsoft::WRL::Details::Make<EnrollmentsEnrollNode,EnrollmentsUpnNode *>(&v41, &v42);
    v35 = 0;
    if ( &v43 != v34 )
    {
      v35 = *(_QWORD *)v34;
      *(_QWORD *)v34 = 0;
    }
    v36 = a1[15];
    a1[15] = v35;
    if ( v36 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
    v37 = v41;
    if ( v41 )
    {
      v41 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
    }
    v38 = (__int64 (__fastcall ***)(_QWORD, GUID *))a1[15];
    if ( !v38 )
    {
      v14 = -2147024882;
      v13 = 107;
      goto LABEL_6;
    }
    if ( a5 )
    {
      v14 = (**v38)(v38, &GUID_8a13633c_797d_46e9_b602_d982b8ec9847);
      if ( v14 < 0 )
      {
        v13 = 110;
        goto LABEL_6;
      }
    }
    *v15 |= 2u;
    return 0;
  }
  return 2248146946LL;
}

```

## disassembly

```asm
0x180014870  mov     [rsp-28h+arg_0], rbx
0x180014875  mov     [rsp-28h+arg_10], rsi
0x18001487a  push    rbp
0x18001487b  push    rdi
0x18001487c  push    r12
0x18001487e  push    r14
0x180014880  push    r15
0x180014882  mov     rbp, rsp
0x180014885  sub     rsp, 70h
0x180014889  mov     rsi, r9
0x18001488c  mov     r15d, r8d
0x18001488f  mov     r14, rdx
0x180014892  mov     rbx, rcx
0x180014895  xor     r12d, r12d
0x180014898  mov     [rbp+arg_8], r12d
0x18001489c  mov     rax, [rdx]
0x18001489f  lea     rdx, [rbp+arg_8]
0x1800148a3  mov     rcx, r14
0x1800148a6  mov     rax, [rax+88h]
0x1800148ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800148b2  mov     edi, eax
0x1800148b4  test    eax, eax
0x1800148b6  jns     short loc_1800148D7
0x1800148b8  mov     rcx, [rbp+28h]; this
0x1800148bc  mov     r9d, eax; char *
0x1800148bf  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\prov\\provcsp\\enrol"...
0x1800148c6  lea     edx, [r12+38h]; void *
0x1800148cb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800148d0  mov     eax, edi
0x1800148d2  jmp     loc_180014DB5
0x1800148d7  cmp     [rbp+arg_8], 1
0x1800148db  jz      short loc_180014901
0x1800148dd  mov     edx, 39h ; '9'; void *
0x1800148e2  mov     ebx, 80070057h
0x1800148e7  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\prov\\provcsp\\enrol"...
0x1800148ee  mov     r9d, ebx; char *
0x1800148f1  mov     rcx, [rbp+28h]; this
0x1800148f5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800148fa  mov     eax, ebx
0x1800148fc  jmp     loc_180014DB5
0x180014901  mov     rdi, [rbp+arg_28]
0x180014905  test    rdi, rdi
0x180014908  jnz     short loc_18001490F
0x18001490a  lea     edx, [rdi+3Ah]
0x18001490d  jmp     short loc_1800148E2
0x18001490f  mov     [rbp+String1], r12
0x180014913  mov     rax, [r14]
0x180014916  lea     r8, [rbp+String1]
0x18001491a  xor     edx, edx
0x18001491c  mov     rcx, r14
0x18001491f  mov     rax, [rax+58h]
0x180014923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014928  mov     r14d, eax
0x18001492b  test    eax, eax
0x18001492d  jns     short loc_18001494F
0x18001492f  mov     rcx, [rbp+28h]; this
0x180014933  mov     r9d, eax; char *
0x180014936  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\prov\\provcsp\\enrol"...
0x18001493d  mov     edx, 3Dh ; '='; void *
0x180014942  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014947  mov     eax, r14d
0x18001494a  jmp     loc_180014DB5
0x18001494f  lea     rdx, ?gc_wszEnrollmentsSecretNode@@3QBGB; "Secret"
0x180014956  mov     rcx, [rbp+String1]; String1
0x18001495a  call    cs:__imp__wcsicmp
0x180014961  nop     dword ptr [rax+rax+00h]
0x180014966  test    eax, eax
0x180014968  jnz     short loc_1800149C3
0x18001496a  add     rbx, 38h ; '8'
0x18001496e  mov     rcx, [rbx]
0x180014971  test    rcx, rcx
0x180014974  jz      short loc_180014986
0x180014976  mov     [rbx], r12
0x180014979  mov     rax, [rcx]
0x18001497c  mov     rax, [rax+10h]
0x180014980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014985  nop
0x180014986  movups  xmm0, xmmword ptr [rsi]
0x180014989  movaps  [rbp+var_20], xmm0
0x18001498d  movsd   xmm1, qword ptr [rsi+10h]
0x180014992  movsd   [rbp+var_10], xmm1
0x180014997  mov     qword ptr [rsp+70h+var_50], rbx
0x18001499c  mov     r9, rdi
0x18001499f  mov     r8, [rbp+arg_20]
0x1800149a3  lea     rdx, [rbp+var_20]
0x1800149a7  mov     ecx, r15d
0x1800149aa  call    ?AddStringNode@GenericBStrNode@@SAJW4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAKPEAPEAV1@@Z; GenericBStrNode::AddStringNode(ConfigDataType,tagVARIANT,ICSPNode * *,ulong *,GenericBStrNode * *)
0x1800149af  mov     ebx, eax
0x1800149b1  test    eax, eax
0x1800149b3  jns     loc_180014DAC
0x1800149b9  mov     edx, 42h ; 'B'
0x1800149be  jmp     loc_1800148E7
0x1800149c3  lea     rdx, ?gc_wszEnrollmentsDiscoveryServiceNode@@3QBGB; "DiscoveryServiceFullUrl"
0x1800149ca  mov     rcx, [rbp+String1]; String1
0x1800149ce  call    cs:__imp__wcsicmp
0x1800149d5  nop     dword ptr [rax+rax+00h]
0x1800149da  test    eax, eax
0x1800149dc  jnz     short loc_180014A37
0x1800149de  add     rbx, 40h ; '@'
0x1800149e2  mov     rcx, [rbx]
0x1800149e5  test    rcx, rcx
0x1800149e8  jz      short loc_1800149FA
0x1800149ea  mov     [rbx], r12
0x1800149ed  mov     rax, [rcx]
0x1800149f0  mov     rax, [rax+10h]
0x1800149f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800149f9  nop
0x1800149fa  movups  xmm0, xmmword ptr [rsi]
0x1800149fd  movaps  [rbp+var_20], xmm0
0x180014a01  movsd   xmm1, qword ptr [rsi+10h]
0x180014a06  movsd   [rbp+var_10], xmm1
0x180014a0b  mov     qword ptr [rsp+70h+var_50], rbx
0x180014a10  mov     r9, rdi
0x180014a13  mov     r8, [rbp+arg_20]
0x180014a17  lea     rdx, [rbp+var_20]
0x180014a1b  mov     ecx, r15d
0x180014a1e  call    ?AddStringNode@GenericBStrNode@@SAJW4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAKPEAPEAV1@@Z; GenericBStrNode::AddStringNode(ConfigDataType,tagVARIANT,ICSPNode * *,ulong *,GenericBStrNode * *)
0x180014a23  mov     ebx, eax
0x180014a25  test    eax, eax
0x180014a27  jns     loc_180014DAC
0x180014a2d  mov     edx, 47h ; 'G'
0x180014a32  jmp     loc_1800148E7
0x180014a37  lea     rdx, ?gc_wszEnrollmentsPolicyServiceNode@@3QBGB; "PolicyServiceFullURL"
0x180014a3e  mov     rcx, [rbp+String1]; String1
0x180014a42  call    cs:__imp__wcsicmp
0x180014a49  nop     dword ptr [rax+rax+00h]
0x180014a4e  test    eax, eax
0x180014a50  jnz     short loc_180014AAB
0x180014a52  add     rbx, 48h ; 'H'
0x180014a56  mov     rcx, [rbx]
0x180014a59  test    rcx, rcx
0x180014a5c  jz      short loc_180014A6E
0x180014a5e  mov     [rbx], r12
0x180014a61  mov     rax, [rcx]
0x180014a64  mov     rax, [rax+10h]
0x180014a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a6d  nop
0x180014a6e  movups  xmm0, xmmword ptr [rsi]
0x180014a71  movaps  [rbp+var_20], xmm0
0x180014a75  movsd   xmm1, qword ptr [rsi+10h]
0x180014a7a  movsd   [rbp+var_10], xmm1
0x180014a7f  mov     qword ptr [rsp+70h+var_50], rbx
0x180014a84  mov     r9, rdi
0x180014a87  mov     r8, [rbp+arg_20]
0x180014a8b  lea     rdx, [rbp+var_20]
0x180014a8f  mov     ecx, r15d
0x180014a92  call    ?AddStringNode@GenericBStrNode@@SAJW4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAKPEAPEAV1@@Z; GenericBStrNode::AddStringNode(ConfigDataType,tagVARIANT,ICSPNode * *,ulong *,GenericBStrNode * *)
0x180014a97  mov     ebx, eax
0x180014a99  test    eax, eax
0x180014a9b  jns     loc_180014DAC
0x180014aa1  mov     edx, 4Ch ; 'L'
0x180014aa6  jmp     loc_1800148E7
0x180014aab  lea     rdx, ?gc_wszEnrollmentsEnrollmentServiceNode@@3QBGB; "EnrollmentServiceFullURL"
0x180014ab2  mov     rcx, [rbp+String1]; String1
0x180014ab6  call    cs:__imp__wcsicmp
0x180014abd  nop     dword ptr [rax+rax+00h]
0x180014ac2  test    eax, eax
0x180014ac4  jnz     short loc_180014B1F
0x180014ac6  add     rbx, 50h ; 'P'
0x180014aca  mov     rcx, [rbx]
0x180014acd  test    rcx, rcx
0x180014ad0  jz      short loc_180014AE2
0x180014ad2  mov     [rbx], r12
0x180014ad5  mov     rax, [rcx]
0x180014ad8  mov     rax, [rax+10h]
0x180014adc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ae1  nop
0x180014ae2  movups  xmm0, xmmword ptr [rsi]
0x180014ae5  movaps  [rbp+var_20], xmm0
0x180014ae9  movsd   xmm1, qword ptr [rsi+10h]
0x180014aee  movsd   [rbp+var_10], xmm1
0x180014af3  mov     qword ptr [rsp+70h+var_50], rbx
0x180014af8  mov     r9, rdi
0x180014afb  mov     r8, [rbp+arg_20]
0x180014aff  lea     rdx, [rbp+var_20]
0x180014b03  mov     ecx, r15d
0x180014b06  call    ?AddStringNode@GenericBStrNode@@SAJW4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAKPEAPEAV1@@Z; GenericBStrNode::AddStringNode(ConfigDataType,tagVARIANT,ICSPNode * *,ulong *,GenericBStrNode * *)
0x180014b0b  mov     ebx, eax
0x180014b0d  test    eax, eax
0x180014b0f  jns     loc_180014DAC
0x180014b15  mov     edx, 51h ; 'Q'
0x180014b1a  jmp     loc_1800148E7
0x180014b1f  lea     rdx, ?gc_wszEnrollmentsEnrollmentTypeNode@@3QBGB; "EnrollmentType"
0x180014b26  mov     rcx, [rbp+String1]; String1
0x180014b2a  call    cs:__imp__wcsicmp
0x180014b31  nop     dword ptr [rax+rax+00h]
0x180014b36  test    eax, eax
0x180014b38  jnz     short loc_180014B93
0x180014b3a  add     rbx, 60h ; '`'
0x180014b3e  mov     rcx, [rbx]
0x180014b41  test    rcx, rcx
0x180014b44  jz      short loc_180014B56
0x180014b46  mov     [rbx], r12
0x180014b49  mov     rax, [rcx]
0x180014b4c  mov     rax, [rax+10h]
0x180014b50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b55  nop
0x180014b56  movups  xmm0, xmmword ptr [rsi]
0x180014b59  movaps  [rbp+var_20], xmm0
0x180014b5d  movsd   xmm1, qword ptr [rsi+10h]
0x180014b62  movsd   [rbp+var_10], xmm1
0x180014b67  mov     qword ptr [rsp+70h+var_50], rbx
0x180014b6c  mov     r9, rdi
0x180014b6f  mov     r8, [rbp+arg_20]
0x180014b73  lea     rdx, [rbp+var_20]
0x180014b77  mov     ecx, r15d
0x180014b7a  call    ?AddStringNode@GenericBStrNode@@SAJW4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAKPEAPEAV1@@Z; GenericBStrNode::AddStringNode(ConfigDataType,tagVARIANT,ICSPNode * *,ulong *,GenericBStrNode * *)
0x180014b7f  mov     ebx, eax
0x180014b81  test    eax, eax
0x180014b83  jns     loc_180014DAC
0x180014b89  mov     edx, 56h ; 'V'
0x180014b8e  jmp     loc_1800148E7
0x180014b93  lea     rdx, ?gc_wszEnrollmentsAuthPolicyNode@@3QBGB; "AuthPolicy"
0x180014b9a  mov     rcx, [rbp+String1]; String1
0x180014b9e  call    cs:__imp__wcsicmp
0x180014ba5  nop     dword ptr [rax+rax+00h]
0x180014baa  test    eax, eax
0x180014bac  jnz     short loc_180014C07
0x180014bae  add     rbx, 58h ; 'X'
0x180014bb2  mov     rcx, [rbx]
0x180014bb5  test    rcx, rcx
0x180014bb8  jz      short loc_180014BCA
0x180014bba  mov     [rbx], r12
0x180014bbd  mov     rax, [rcx]
0x180014bc0  mov     rax, [rax+10h]
0x180014bc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014bc9  nop
0x180014bca  movups  xmm0, xmmword ptr [rsi]
0x180014bcd  movaps  [rbp+var_20], xmm0
0x180014bd1  movsd   xmm1, qword ptr [rsi+10h]
0x180014bd6  movsd   [rbp+var_10], xmm1
0x180014bdb  mov     qword ptr [rsp+70h+var_50], rbx
0x180014be0  mov     r9, rdi
0x180014be3  mov     r8, [rbp+arg_20]
0x180014be7  lea     rdx, [rbp+var_20]
0x180014beb  mov     ecx, r15d
0x180014bee  call    ?AddNode@GenericIntNode@@SAJW4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAKPEAPEAV1@@Z; GenericIntNode::AddNode(ConfigDataType,tagVARIANT,ICSPNode * *,ulong *,GenericIntNode * *)
0x180014bf3  mov     ebx, eax
0x180014bf5  test    eax, eax
0x180014bf7  jns     loc_180014DAC
0x180014bfd  mov     edx, 5Bh ; '['
0x180014c02  jmp     loc_1800148E7
0x180014c07  lea     rdx, ?gc_wszEnrollmentsDomainUsernameNode@@3QBGB; "DomainUsername"
0x180014c0e  mov     rcx, [rbp+String1]; String1
0x180014c12  call    cs:__imp__wcsicmp
0x180014c19  nop     dword ptr [rax+rax+00h]
0x180014c1e  test    eax, eax
0x180014c20  jnz     short loc_180014C7B
0x180014c22  add     rbx, 68h ; 'h'
0x180014c26  mov     rcx, [rbx]
0x180014c29  test    rcx, rcx
0x180014c2c  jz      short loc_180014C3E
0x180014c2e  mov     [rbx], r12
0x180014c31  mov     rax, [rcx]
0x180014c34  mov     rax, [rax+10h]
0x180014c38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014c3d  nop
0x180014c3e  movups  xmm0, xmmword ptr [rsi]
0x180014c41  movaps  [rbp+var_20], xmm0
0x180014c45  movsd   xmm1, qword ptr [rsi+10h]
0x180014c4a  movsd   [rbp+var_10], xmm1
0x180014c4f  mov     qword ptr [rsp+70h+var_50], rbx
0x180014c54  mov     r9, rdi
0x180014c57  mov     r8, [rbp+arg_20]
0x180014c5b  lea     rdx, [rbp+var_20]
0x180014c5f  mov     ecx, r15d
0x180014c62  call    ?AddStringNode@GenericBStrNode@@SAJW4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAKPEAPEAV1@@Z; GenericBStrNode::AddStringNode(ConfigDataType,tagVARIANT,ICSPNode * *,ulong *,GenericBStrNode * *)
0x180014c67  mov     ebx, eax
0x180014c69  test    eax, eax
0x180014c6b  jns     loc_180014DAC
0x180014c71  mov     edx, 60h ; '`'
0x180014c76  jmp     loc_1800148E7
0x180014c7b  lea     rdx, ?gc_wszEnrollmentsEnrollmentIDNode@@3QBGB; "EnrollmentID"
0x180014c82  mov     rcx, [rbp+String1]; String1
0x180014c86  call    cs:__imp__wcsicmp
0x180014c8d  nop     dword ptr [rax+rax+00h]
0x180014c92  test    eax, eax
0x180014c94  jnz     short loc_180014CEF
0x180014c96  add     rbx, 70h ; 'p'
0x180014c9a  mov     rcx, [rbx]
0x180014c9d  test    rcx, rcx
0x180014ca0  jz      short loc_180014CB2
0x180014ca2  mov     [rbx], r12
0x180014ca5  mov     rax, [rcx]
0x180014ca8  mov     rax, [rax+10h]
0x180014cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014cb1  nop
0x180014cb2  movups  xmm0, xmmword ptr [rsi]
0x180014cb5  movaps  [rbp+var_20], xmm0
0x180014cb9  movsd   xmm1, qword ptr [rsi+10h]
0x180014cbe  movsd   [rbp+var_10], xmm1
0x180014cc3  mov     qword ptr [rsp+70h+var_50], rbx
0x180014cc8  mov     r9, rdi
0x180014ccb  mov     r8, [rbp+arg_20]
0x180014ccf  lea     rdx, [rbp+var_20]
0x180014cd3  mov     ecx, r15d
0x180014cd6  call    ?AddStringNode@GenericBStrNode@@SAJW4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAKPEAPEAV1@@Z; GenericBStrNode::AddStringNode(ConfigDataType,tagVARIANT,ICSPNode * *,ulong *,GenericBStrNode * *)
0x180014cdb  mov     ebx, eax
0x180014cdd  test    eax, eax
0x180014cdf  jns     loc_180014DAC
  ... truncated ...
```
