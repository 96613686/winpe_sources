# FwRulesEnum::GetVariant(ulong,tagVARIANT *,FwEnumBase::GET_VARIANT_RESULT *)

- ea: `0x180004c60`
- end: `0x1800050ef`
- name: `?GetVariant@FwRulesEnum@@EEAAJKPEAUtagVARIANT@@PEAW4GET_VARIANT_RESULT@FwEnumBase@@@Z`
- size: `1167`
- prototype: `__int64 __fastcall(FwRulesEnum *__hidden this, unsigned int, struct tagVARIANT *, enum FwEnumBase::GET_VARIANT_RESULT *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180004c60`
- `0x1800052b0`
- `0x18003336c`
- `0x180062010`

## import_xrefs

- `fwbase!FwReportReturnError` at `0x180004df6`
- `fwbase!FwReportReturnError` at `0x180004e24`
- `fwbase!FwReportReturnError` at `0x180004f86`
- `fwbase!FwReportReturnError` at `0x180004faf`
- `fwbase!FwReportReturnError` at `0x180004fce`
- `fwbase!FwReportReturnError` at `0x1800050c9`
- `fwbase!FwReportReturnError` at `0x1800050de`
- `fwbase!FwReportReturnError` at `0x180004df6`
- `fwbase!FwReportReturnError` at `0x180004e24`
- `fwbase!FwReportReturnError` at `0x180004f86`
- `fwbase!FwReportReturnError` at `0x180004faf`
- `fwbase!FwReportReturnError` at `0x180004fce`
- `fwbase!FwReportReturnError` at `0x1800050c9`
- `fwbase!FwReportReturnError` at `0x1800050de`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180004f96`
- `FWPolicyIOMgr!FwFreeWFRule` at `0x180004f96`
- `FWPolicyIOMgr!FwCopyRule` at `0x180004dcb`
- `FWPolicyIOMgr!FwCopyRule` at `0x180004dcb`

## string_xrefs

- `0x180004def`: `FwRule::CreateInstance`
- `0x180004e1d`: `FwRule::CreateInstance`
- `0x180004fc7`: `FwRule::CreateInstance`

## pseudocode

```c
__int64 __fastcall FwRulesEnum::GetVariant(
        FwRulesEnum *this,
        int a2,
        struct tagVARIANT *a3,
        enum FwEnumBase::GET_VARIANT_RESULT *a4)
{
  FwPolicy2 *v8; // r10
  unsigned int v9; // esi
  int v10; // r12d
  __int64 v11; // rbp
  _WORD *v12; // rax
  __int16 v13; // ax
  unsigned int i; // r9d
  int v15; // ecx
  __int64 *v16; // r12
  int v17; // esi
  __int64 v18; // rcx
  LONGLONG v19; // rbp
  int v20; // eax
  unsigned int v21; // ebx
  LONGLONG v22; // rdi
  int v23; // eax
  __int64 v25; // rcx
  _WORD *v26; // rdx
  __int64 v27; // rdx
  _WORD *v28; // rcx
  _WORD *v29; // rax
  int v30; // eax
  _WORD *v31; // rcx
  LONGLONG v32; // [rsp+50h] [rbp+8h] BYREF

  v8 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_098d31ae94223bbae5defc232583cd37_Traceguids);
    v8 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    *((_QWORD *)this + 14) = *((_QWORD *)this + 12);
    *((_QWORD *)this + 15) = 0;
    v8 = WPP_GLOBAL_Control;
  }
  v9 = *((_DWORD *)this + 30);
  if ( v9 >= *((_DWORD *)this + 26) )
  {
LABEL_41:
    *(_DWORD *)a4 = 2;
    return 0;
  }
  while ( 1 )
  {
    v10 = *((_DWORD *)this + 18);
    v11 = *((_QWORD *)this + 14);
    if ( v8 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 8) != 0 )
    {
      WPP_SF_(*((_QWORD *)v8 + 2), 95, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids);
      v8 = WPP_GLOBAL_Control;
    }
    v12 = *(_WORD **)(v11 + 24);
    if ( v12 )
    {
      if ( *v12 && (unsigned int)(*(_DWORD *)(v11 + 288) - 2) <= 1 )
        break;
    }
LABEL_40:
    ++v9;
    v25 = **((_QWORD **)this + 14);
    ++*((_DWORD *)this + 30);
    *((_QWORD *)this + 14) = v25;
    if ( v9 >= *((_DWORD *)this + 26) )
      goto LABEL_41;
    v8 = WPP_GLOBAL_Control;
  }
  v13 = *(_WORD *)(v11 + 48);
  if ( v13 == 1 || v13 == 58 )
    goto LABEL_19;
  if ( v11 == -56 )
  {
    if ( v8 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 1) == 0 )
      goto LABEL_40;
    v27 = 10;
LABEL_47:
    WPP_SF_(*((_QWORD *)v8 + 2), v27, WPP_a5b3657941d83b93491a297b9144c2a3_Traceguids);
    goto LABEL_40;
  }
  if ( (*(_WORD *)(v11 + 56) & 0xFC20) != 0 )
  {
    if ( v8 == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 1) == 0 )
      goto LABEL_40;
    v27 = 11;
    goto LABEL_47;
  }
  for ( i = 0; i < *(_DWORD *)(v11 + 64); ++i )
  {
    v26 = (_WORD *)(*(_QWORD *)(v11 + 72) + 4LL * i);
    if ( *v26 > v26[1] )
    {
      if ( v8 != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 1) != 0 )
      {
        v27 = 12;
        goto LABEL_47;
      }
      goto LABEL_40;
    }
  }
LABEL_19:
  if ( (v10 & 1) != 0 )
  {
    v28 = *(_WORD **)(v11 + 376);
    if ( v28 || *(_QWORD *)(v11 + 384) )
    {
      if ( (v10 & 4) == 0 )
        goto LABEL_40;
      if ( !v28 )
        goto LABEL_40;
      if ( !*v28 )
        goto LABEL_40;
      v31 = *(_WORD **)(v11 + 384);
      if ( !v31 || !*v31 )
        goto LABEL_40;
    }
    v29 = *(_WORD **)(v11 + 280);
    if ( v29 )
    {
      if ( (v10 & 2) == 0 || !*v29 )
        goto LABEL_40;
    }
  }
  v15 = *((_DWORD *)this + 31);
  *((_DWORD *)this + 31) = v15 + 1;
  if ( a2 != v15 )
    goto LABEL_40;
  v16 = (__int64 *)*((_QWORD *)this + 14);
  v17 = *((_DWORD *)this + 18);
  v18 = *v16;
  ++*((_DWORD *)this + 30);
  *((_QWORD *)this + 14) = v18;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 85, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids);
  v32 = 0;
  v19 = 0;
  v20 = ATL::CComObject<FwRule>::CreateInstance(&v32);
  v21 = v20;
  if ( v20 < 0 )
  {
    FwReportReturnError("FwRule::CreateInstance", (unsigned int)v20);
    v22 = v32;
    goto LABEL_32;
  }
  v22 = v32;
  (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v32 + 8LL))(v32);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 90, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids);
  *(_DWORD *)(v22 + 64) = v17;
  v23 = FwCopyRule(v16, v22 + 80);
  v21 = v23;
  if ( v23 >= 0 )
  {
    *(_DWORD *)(v22 + 88) = 1;
    goto LABEL_30;
  }
  FwReportReturnError("FwRule::Initialize", (unsigned int)v23);
  FwFreeWFRule(*(_QWORD *)(v22 + 80));
  *(_QWORD *)(v22 + 80) = 0;
  v30 = FwReportReturnError("FwRule::Initialize", v21);
  v21 = v30;
  if ( v30 >= 0 )
  {
LABEL_30:
    v19 = v22;
    goto LABEL_35;
  }
  FwReportReturnError("FwRule::CreateInstance", (unsigned int)v30);
LABEL_32:
  if ( v22 )
    (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v22 + 16LL))(v22);
  v21 = FwReportReturnError("FwRule::CreateInstance", v21);
  if ( v21 == -2147024883 )
    goto LABEL_54;
LABEL_35:
  if ( v21 == -2147024894 )
  {
LABEL_54:
    *(_DWORD *)a4 = 1;
    return 0;
  }
  if ( (v21 & 0x80000000) == 0 )
  {
    a3->vt = 9;
    a3->llVal = v19;
    *(_DWORD *)a4 = 0;
    return v21;
  }
  FwReportReturnError("FwRulesEnum::GetVariant", v21);
  return FwReportReturnError("FwRulesEnum::GetVariant", v21);
}

```

## disassembly

```asm
0x180004c60  mov     [rsp+arg_18], rbx
0x180004c65  push    rsi
0x180004c66  push    rdi
0x180004c67  push    r13
0x180004c69  push    r14
0x180004c6b  push    r15
0x180004c6d  sub     rsp, 20h
0x180004c71  mov     r14, r9
0x180004c74  mov     r15, r8
0x180004c77  mov     edi, edx
0x180004c79  mov     rbx, rcx
0x180004c7c  mov     r10, cs:WPP_GLOBAL_Control
0x180004c83  lea     r11, WPP_GLOBAL_Control
0x180004c8a  cmp     r10, r11
0x180004c8d  jz      short loc_180004C9A
0x180004c8f  test    byte ptr [r10+1Ch], 8
0x180004c94  jnz     loc_180004FDF
0x180004c9a  xor     r13d, r13d
0x180004c9d  test    edi, edi
0x180004c9f  jz      loc_180004E7D
0x180004ca5  mov     esi, [rbx+78h]
0x180004ca8  mov     [rsp+48h+arg_8], rbp
0x180004cad  mov     [rsp+48h+arg_10], r12
0x180004cb2  cmp     esi, [rbx+68h]
0x180004cb5  jnb     loc_180004EB7
0x180004cbb  mov     r12d, [rbx+48h]
0x180004cbf  mov     rbp, [rbx+70h]
0x180004cc3  cmp     r10, r11
0x180004cc6  jz      short loc_180004CD3
0x180004cc8  test    byte ptr [r10+1Ch], 8
0x180004ccd  jnz     loc_180005007
0x180004cd3  mov     rax, [rbp+18h]
0x180004cd7  test    rax, rax
0x180004cda  jz      loc_180004E9E
0x180004ce0  cmp     [rax], r13w
0x180004ce4  jz      loc_180004E9E
0x180004cea  mov     eax, [rbp+120h]
0x180004cf0  sub     eax, 2
0x180004cf3  cmp     eax, 1
0x180004cf6  ja      loc_180004E9E
0x180004cfc  movzx   eax, word ptr [rbp+30h]
0x180004d00  cmp     ax, 1
0x180004d04  jz      short loc_180004D35
0x180004d06  cmp     ax, 3Ah ; ':'
0x180004d0a  jz      short loc_180004D35
0x180004d0c  lea     r8, [rbp+38h]
0x180004d10  test    r8, r8
0x180004d13  jz      loc_180004F5F
0x180004d19  movzx   eax, word ptr [r8]
0x180004d1d  test    eax, 0FFFFFC20h
0x180004d22  jnz     loc_180004E95
0x180004d28  mov     r9d, r13d
0x180004d2b  cmp     r9d, [r8+8]
0x180004d2f  jb      loc_180004EC3
0x180004d35  test    r12b, 1
0x180004d39  jnz     loc_180004F0A
0x180004d3f  mov     ecx, [rbx+7Ch]
0x180004d42  lea     eax, [rcx+1]
0x180004d45  mov     [rbx+7Ch], eax
0x180004d48  cmp     edi, ecx
0x180004d4a  jnz     loc_180004E9E
0x180004d50  mov     r12, [rbx+70h]
0x180004d54  mov     esi, [rbx+48h]
0x180004d57  mov     rcx, [r12]
0x180004d5b  inc     dword ptr [rbx+78h]
0x180004d5e  mov     [rbx+70h], rcx
0x180004d62  mov     rcx, cs:WPP_GLOBAL_Control
0x180004d69  cmp     rcx, r11
0x180004d6c  jz      short loc_180004D78
0x180004d6e  test    byte ptr [rcx+1Ch], 8
0x180004d72  jnz     loc_18000508C
0x180004d78  lea     rcx, [rsp+48h+arg_0]
0x180004d7d  mov     [rsp+48h+arg_0], r13
0x180004d82  mov     rbp, r13
0x180004d85  call    ?CreateInstance@?$CComObject@VFwRule@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<FwRule>::CreateInstance(ATL::CComObject<FwRule> * *)
0x180004d8a  mov     ebx, eax
0x180004d8c  test    eax, eax
0x180004d8e  js      short loc_180004DED
0x180004d90  mov     rdi, [rsp+48h+arg_0]
0x180004d95  mov     rcx, rdi
0x180004d98  mov     rax, [rdi]
0x180004d9b  mov     rax, [rax+8]
0x180004d9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004da4  mov     rcx, cs:WPP_GLOBAL_Control
0x180004dab  lea     rax, WPP_GLOBAL_Control
0x180004db2  cmp     rcx, rax
0x180004db5  jz      short loc_180004DC1
0x180004db7  test    byte ptr [rcx+1Ch], 8
0x180004dbb  jnz     loc_1800050A6
0x180004dc1  lea     rdx, [rdi+50h]
0x180004dc5  mov     [rdi+40h], esi
0x180004dc8  mov     rcx, r12
0x180004dcb  call    cs:__imp_FwCopyRule
0x180004dd2  nop     dword ptr [rax+rax+00h]
0x180004dd7  mov     ebx, eax
0x180004dd9  test    eax, eax
0x180004ddb  js      loc_180004F7D
0x180004de1  mov     dword ptr [rdi+58h], 1
0x180004de8  mov     rbp, rdi
0x180004deb  jmp     short loc_180004E3D
0x180004ded  mov     edx, eax
0x180004def  lea     rcx, aFwruleCreatein; "FwRule::CreateInstance"
0x180004df6  call    cs:__imp_FwReportReturnError
0x180004dfd  nop     dword ptr [rax+rax+00h]
0x180004e02  mov     rdi, [rsp+48h+arg_0]
0x180004e07  test    rdi, rdi
0x180004e0a  jz      short loc_180004E1B
0x180004e0c  mov     rax, [rdi]
0x180004e0f  mov     rcx, rdi
0x180004e12  mov     rax, [rax+10h]
0x180004e16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e1b  mov     edx, ebx
0x180004e1d  lea     rcx, aFwruleCreatein; "FwRule::CreateInstance"
0x180004e24  call    cs:__imp_FwReportReturnError
0x180004e2b  nop     dword ptr [rax+rax+00h]
0x180004e30  mov     ebx, eax
0x180004e32  cmp     eax, 8007000Dh
0x180004e37  jz      loc_180004F50
0x180004e3d  cmp     ebx, 80070002h
0x180004e43  jz      loc_180004F50
0x180004e49  test    ebx, ebx
0x180004e4b  js      loc_1800050C0
0x180004e51  mov     word ptr [r15], 9
0x180004e57  mov     [r15+8], rbp
0x180004e5b  mov     [r14], r13d
0x180004e5e  mov     eax, ebx
0x180004e60  mov     r12, [rsp+48h+arg_10]
0x180004e65  mov     rbp, [rsp+48h+arg_8]
0x180004e6a  mov     rbx, [rsp+48h+arg_18]
0x180004e6f  add     rsp, 20h
0x180004e73  pop     r15
0x180004e75  pop     r14
0x180004e77  pop     r13
0x180004e79  pop     rdi
0x180004e7a  pop     rsi
0x180004e7b  retn
0x180004e7d  mov     rax, [rbx+60h]
0x180004e81  mov     [rbx+70h], rax
0x180004e85  mov     [rbx+78h], r13
0x180004e89  mov     r10, cs:WPP_GLOBAL_Control
0x180004e90  jmp     loc_180004CA5
0x180004e95  cmp     r10, r11
0x180004e98  jnz     loc_18000502F
0x180004e9e  mov     rax, [rbx+70h]
0x180004ea2  inc     esi
0x180004ea4  mov     rcx, [rax]
0x180004ea7  inc     dword ptr [rbx+78h]
0x180004eaa  mov     [rbx+70h], rcx
0x180004eae  cmp     esi, [rbx+68h]
0x180004eb1  jb      loc_180005080
0x180004eb7  mov     dword ptr [r14], 2
0x180004ebe  mov     ebx, r13d
0x180004ec1  jmp     short loc_180004E5E
0x180004ec3  mov     rax, [r8+10h]
0x180004ec7  mov     ecx, r9d
0x180004eca  lea     rdx, [rax+rcx*4]
0x180004ece  movzx   eax, word ptr [rax+rcx*4+2]
0x180004ed3  cmp     [rdx], ax
0x180004ed6  ja      short loc_180004EE0
0x180004ed8  inc     r9d
0x180004edb  jmp     loc_180004D2B
0x180004ee0  cmp     r10, r11
0x180004ee3  jz      short loc_180004E9E
0x180004ee5  test    byte ptr [r10+1Ch], 1
0x180004eea  jz      short loc_180004E9E
0x180004eec  mov     edx, 0Ch
0x180004ef1  mov     rcx, [r10+10h]
0x180004ef5  lea     r8, WPP_a5b3657941d83b93491a297b9144c2a3_Traceguids
0x180004efc  call    WPP_SF_
0x180004f01  lea     r11, WPP_GLOBAL_Control
0x180004f08  jmp     short loc_180004E9E
0x180004f0a  mov     rcx, [rbp+178h]
0x180004f11  test    rcx, rcx
0x180004f14  jnz     loc_180005044
0x180004f1a  cmp     [rbp+180h], r13
0x180004f21  jnz     loc_180005044
0x180004f27  mov     rax, [rbp+118h]
0x180004f2e  test    rax, rax
0x180004f31  jz      loc_180004D3F
0x180004f37  test    r12b, 2
0x180004f3b  jz      loc_180004E9E
0x180004f41  cmp     [rax], r13w
0x180004f45  jnz     loc_180004D3F
0x180004f4b  jmp     loc_180004E9E
0x180004f50  mov     dword ptr [r14], 1
0x180004f57  mov     ebx, r13d
0x180004f5a  jmp     loc_180004E5E
0x180004f5f  cmp     r10, r11
0x180004f62  jz      loc_180004E9E
0x180004f68  test    byte ptr [r10+1Ch], 1
0x180004f6d  jz      loc_180004E9E
0x180004f73  mov     edx, 0Ah
0x180004f78  jmp     loc_180004EF1
0x180004f7d  mov     edx, ebx
0x180004f7f  lea     rcx, aFwruleInitiali; "FwRule::Initialize"
0x180004f86  call    cs:__imp_FwReportReturnError
0x180004f8d  nop     dword ptr [rax+rax+00h]
0x180004f92  mov     rcx, [rdi+50h]
0x180004f96  call    cs:__imp_FwFreeWFRule
0x180004f9d  nop     dword ptr [rax+rax+00h]
0x180004fa2  mov     edx, ebx
0x180004fa4  mov     [rdi+50h], r13
0x180004fa8  lea     rcx, aFwruleInitiali; "FwRule::Initialize"
0x180004faf  call    cs:__imp_FwReportReturnError
0x180004fb6  nop     dword ptr [rax+rax+00h]
0x180004fbb  mov     ebx, eax
0x180004fbd  test    eax, eax
0x180004fbf  jns     loc_180004DE8
0x180004fc5  mov     edx, eax
0x180004fc7  lea     rcx, aFwruleCreatein; "FwRule::CreateInstance"
0x180004fce  call    cs:__imp_FwReportReturnError
0x180004fd5  nop     dword ptr [rax+rax+00h]
0x180004fda  jmp     loc_180004E07
0x180004fdf  mov     rcx, [r10+10h]
0x180004fe3  lea     r8, WPP_098d31ae94223bbae5defc232583cd37_Traceguids
0x180004fea  mov     edx, 0Dh
0x180004fef  call    WPP_SF_
0x180004ff4  mov     r10, cs:WPP_GLOBAL_Control
0x180004ffb  lea     r11, WPP_GLOBAL_Control
0x180005002  jmp     loc_180004C9A
0x180005007  mov     rcx, [r10+10h]
0x18000500b  lea     r8, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids
0x180005012  mov     edx, 5Fh ; '_'
0x180005017  call    WPP_SF_
0x18000501c  mov     r10, cs:WPP_GLOBAL_Control
0x180005023  lea     r11, WPP_GLOBAL_Control
0x18000502a  jmp     loc_180004CD3
0x18000502f  test    byte ptr [r10+1Ch], 1
0x180005034  jz      loc_180004E9E
0x18000503a  mov     edx, 0Bh
0x18000503f  jmp     loc_180004EF1
0x180005044  test    r12b, 4
0x180005048  jz      loc_180004E9E
0x18000504e  test    rcx, rcx
0x180005051  jz      loc_180004E9E
0x180005057  cmp     [rcx], r13w
0x18000505b  jz      loc_180004E9E
0x180005061  mov     rcx, [rbp+180h]
0x180005068  test    rcx, rcx
0x18000506b  jz      loc_180004E9E
0x180005071  cmp     [rcx], r13w
0x180005075  jz      loc_180004E9E
0x18000507b  jmp     loc_180004F27
0x180005080  mov     r10, cs:WPP_GLOBAL_Control
0x180005087  jmp     loc_180004CBB
0x18000508c  mov     rcx, [rcx+10h]
0x180005090  lea     r8, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids
0x180005097  mov     edx, 55h ; 'U'
0x18000509c  call    WPP_SF_
0x1800050a1  jmp     loc_180004D78
0x1800050a6  mov     rcx, [rcx+10h]
0x1800050aa  lea     r8, WPP_92d7822da2e63f0d2b29182cb9b878d1_Traceguids
0x1800050b1  mov     edx, 5Ah ; 'Z'
0x1800050b6  call    WPP_SF_
0x1800050bb  jmp     loc_180004DC1
0x1800050c0  mov     edx, ebx
0x1800050c2  lea     rcx, aFwrulesenumGet; "FwRulesEnum::GetVariant"
0x1800050c9  call    cs:__imp_FwReportReturnError
0x1800050d0  nop     dword ptr [rax+rax+00h]
0x1800050d5  mov     edx, ebx
0x1800050d7  lea     rcx, aFwrulesenumGet; "FwRulesEnum::GetVariant"
0x1800050de  call    cs:__imp_FwReportReturnError
0x1800050e5  nop     dword ptr [rax+rax+00h]
0x1800050ea  jmp     loc_180004E60
```
