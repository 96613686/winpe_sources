# EnrollmentsNode::Add(IConfigManager2URI *,ConfigDataType,tagVARIANT,ICSPNode * *,ulong *)

- ea: `0x1800102b0`
- end: `0x18001043a`
- name: `?Add@EnrollmentsNode@@UEAAJPEAUIConfigManager2URI@@W4ConfigDataType@@UtagVARIANT@@PEAPEAUICSPNode@@PEAK@Z`
- size: `394`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180006974`
- `0x18000ff3c`
- `0x1800102b0`
- `0x18002306c`
- `0x180038010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EnrollmentsNode::Add(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, _DWORD *a6)
{
  int v8; // edi
  __int64 v9; // rdx
  int v11; // ebx
  __int64 v12; // rdx
  char *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rcx
  GenericBStrNode *v17; // rcx
  __int64 v18; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int16 *v19; // [rsp+28h] [rbp-20h] BYREF
  char v20; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v22; // [rsp+58h] [rbp+10h] BYREF

  v22 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a2 + 136LL))(a2, &v22);
  if ( v8 < 0 )
  {
    v9 = 40;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\enrollmentsnode.cpp",
      (const char *)(unsigned int)v8,
      v18);
    return (unsigned int)v8;
  }
  if ( v22 != 1 )
  {
    v11 = -2147024809;
    v12 = 41;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecoreuap\\admin\\prov\\provcsp\\enrollmentsnode.cpp",
      (const char *)(unsigned int)v11,
      v18);
    return (unsigned int)v11;
  }
  v19 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 **))(*(_QWORD *)a2 + 88LL))(a2, 0, &v19);
  if ( v8 < 0 )
  {
    v9 = 44;
    goto LABEL_3;
  }
  v13 = (char *)Microsoft::WRL::Details::Make<EnrollmentsUpnNode,>(&v18);
  v14 = 0;
  if ( &v20 != v13 )
  {
    v14 = *(_QWORD *)v13;
    *(_QWORD *)v13 = 0;
  }
  v15 = *(_QWORD *)(a1 + 24);
  *(_QWORD *)(a1 + 24) = v14;
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  v16 = v18;
  if ( v18 )
  {
    v18 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  v17 = *(GenericBStrNode **)(a1 + 24);
  if ( !v17 )
  {
    v11 = -2147024882;
    v12 = 48;
    goto LABEL_6;
  }
  v8 = GenericBStrNode::SetString(v17, v19);
  if ( v8 < 0 )
  {
    v9 = 49;
    goto LABEL_3;
  }
  if ( a5 )
  {
    v11 = (***(__int64 (__fastcall ****)(_QWORD, GUID *))(a1 + 24))(
            *(_QWORD *)(a1 + 24),
            &GUID_8a13633c_797d_46e9_b602_d982b8ec9847);
    if ( v11 < 0 )
    {
      v12 = 52;
      goto LABEL_6;
    }
  }
  *a6 |= 2u;
  return 0;
}

```

## disassembly

```asm
0x1800102b0  mov     [rsp+arg_0], rbx
0x1800102b5  mov     [rsp+arg_10], rsi
0x1800102ba  push    rdi
0x1800102bb  sub     rsp, 40h
0x1800102bf  mov     rsi, rdx
0x1800102c2  mov     rbx, rcx
0x1800102c5  mov     [rsp+48h+arg_8], 0
0x1800102cd  mov     rax, [rdx]
0x1800102d0  lea     rdx, [rsp+48h+arg_8]
0x1800102d5  mov     rcx, rsi
0x1800102d8  mov     rax, [rax+88h]
0x1800102df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102e4  mov     edi, eax
0x1800102e6  test    eax, eax
0x1800102e8  jns     short loc_18001030A
0x1800102ea  mov     edx, 28h ; '('; void *
0x1800102ef  mov     rcx, [rsp+48h]; this
0x1800102f4  mov     r9d, edi; char *
0x1800102f7  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\prov\\provcsp\\enrol"...
0x1800102fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010303  mov     eax, edi
0x180010305  jmp     loc_180010429
0x18001030a  cmp     [rsp+48h+arg_8], 1
0x18001030f  jz      short loc_180010336
0x180010311  mov     ebx, 80070057h
0x180010316  mov     edx, 29h ; ')'; void *
0x18001031b  mov     rcx, [rsp+48h]; this
0x180010320  mov     r9d, ebx; char *
0x180010323  lea     r8, aOnecoreuapAdmi_31; "onecoreuap\\admin\\prov\\provcsp\\enrol"...
0x18001032a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001032f  mov     eax, ebx
0x180010331  jmp     loc_180010429
0x180010336  mov     [rsp+48h+var_20], 0
0x18001033f  mov     rax, [rsi]
0x180010342  lea     r8, [rsp+48h+var_20]
0x180010347  xor     edx, edx
0x180010349  mov     rcx, rsi
0x18001034c  mov     rax, [rax+58h]
0x180010350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010355  mov     edi, eax
0x180010357  test    eax, eax
0x180010359  jns     short loc_180010362
0x18001035b  mov     edx, 2Ch ; ','
0x180010360  jmp     short loc_1800102EF
0x180010362  lea     rcx, [rsp+48h+var_28]
0x180010367  call    ??$Make@VEnrollmentsUpnNode@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VEnrollmentsUpnNode@@@12@XZ; Microsoft::WRL::Details::Make<EnrollmentsUpnNode,>(void)
0x18001036c  xor     ecx, ecx
0x18001036e  lea     rdx, [rsp+48h+var_18]
0x180010373  cmp     rdx, rax
0x180010376  jz      short loc_180010382
0x180010378  mov     rcx, [rax]
0x18001037b  mov     qword ptr [rax], 0
0x180010382  mov     rdx, [rbx+18h]
0x180010386  mov     [rbx+18h], rcx
0x18001038a  test    rdx, rdx
0x18001038d  jz      short loc_18001039F
0x18001038f  mov     rax, [rdx]
0x180010392  mov     rcx, rdx
0x180010395  mov     rax, [rax+10h]
0x180010399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001039e  nop
0x18001039f  mov     rcx, [rsp+48h+var_28]
0x1800103a4  test    rcx, rcx
0x1800103a7  jz      short loc_1800103BF
0x1800103a9  mov     [rsp+48h+var_28], 0
0x1800103b2  mov     rax, [rcx]
0x1800103b5  mov     rax, [rax+10h]
0x1800103b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103be  nop
0x1800103bf  mov     rcx, [rbx+18h]; this
0x1800103c3  test    rcx, rcx
0x1800103c6  jnz     short loc_1800103D5
0x1800103c8  mov     ebx, 8007000Eh
0x1800103cd  lea     edx, [rcx+30h]
0x1800103d0  jmp     loc_18001031B
0x1800103d5  mov     rdx, [rsp+48h+var_20]; unsigned __int16 *
0x1800103da  call    ?SetString@GenericBStrNode@@QEAAJPEBG@Z; GenericBStrNode::SetString(ushort const *)
0x1800103df  mov     edi, eax
0x1800103e1  test    eax, eax
0x1800103e3  jns     short loc_1800103EF
0x1800103e5  mov     edx, 31h ; '1'
0x1800103ea  jmp     loc_1800102EF
0x1800103ef  mov     r8, [rsp+48h+arg_20]
0x1800103f4  test    r8, r8
0x1800103f7  jz      short loc_18001041F
0x1800103f9  mov     rcx, [rbx+18h]
0x1800103fd  mov     rax, [rcx]
0x180010400  lea     rdx, _GUID_8a13633c_797d_46e9_b602_d982b8ec9847
0x180010407  mov     rax, [rax]
0x18001040a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001040f  mov     ebx, eax
0x180010411  test    eax, eax
0x180010413  jns     short loc_18001041F
0x180010415  mov     edx, 34h ; '4'
0x18001041a  jmp     loc_18001031B
0x18001041f  mov     rax, [rsp+48h+arg_28]
0x180010424  or      dword ptr [rax], 2
0x180010427  xor     eax, eax
0x180010429  mov     rbx, [rsp+48h+arg_0]
0x18001042e  mov     rsi, [rsp+48h+arg_10]
0x180010433  add     rsp, 40h
0x180010437  pop     rdi
0x180010438  retn
```
