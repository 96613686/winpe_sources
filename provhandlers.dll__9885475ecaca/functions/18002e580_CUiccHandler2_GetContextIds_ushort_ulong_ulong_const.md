# CUiccHandler2::GetContextIds(ushort * * *,ulong *,ulong const *)

- ea: `0x18002e580`
- end: `0x18002e8e0`
- name: `?GetContextIds@CUiccHandler2@@UEAAJPEAPEAPEAGPEAKPEBK@Z`
- size: `864`
- prototype: `__int64 __fastcall(CUiccHandler2 *__hidden this, unsigned __int16 ***, unsigned int *, const unsigned int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180004894`
- `0x1800076a4`
- `0x18000e1f8`
- `0x18000e308`
- `0x180010084`
- `0x180012d04`
- `0x180012d80`
- `0x180012da0`
- `0x180012e18`
- `0x18002e580`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e82f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e877`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e890`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e82f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e877`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002e890`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18002e79e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x18002e79e`

## string_xrefs

- `0x18002e8a4`: `onecoreuap\admin\prov\multivariant\common\inc\MvTypes.h`
- `0x18002e8bc`: `onecoreuap\admin\prov\multivariant\common\inc\MvTypes.h`
- `0x18002e8ce`: `onecoreuap\admin\prov\multivariant\common\inc\MvTypes.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CUiccHandler2::GetContextIds(
        CUiccHandler2 *this,
        unsigned __int16 ***a2,
        unsigned int *a3,
        const unsigned int *a4)
{
  unsigned __int16 ***v6; // r13
  unsigned __int64 v8; // r15
  __int64 v9; // rdx
  _QWORD *v11; // rbx
  _QWORD *v12; // rbx
  __int64 v13; // rax
  void ***v14; // rdi
  unsigned __int64 v15; // rcx
  unsigned int v16; // esi
  __int64 v17; // rsi
  void **v18; // r13
  _QWORD *v19; // r15
  __int64 v20; // rdi
  char *v21; // rsi
  void **v22; // rdi
  char *v23; // rsi
  unsigned __int64 v24; // rbx
  SIZE_T v25; // rax
  __int64 v26; // r9
  unsigned __int16 **v27; // rax
  const char *v28; // r9
  unsigned __int16 **v29; // rdi
  char *v30; // rcx
  int v31; // eax
  __int64 v32; // r15
  int v33; // [rsp+20h] [rbp-38h]
  void *v34[2]; // [rsp+30h] [rbp-28h] BYREF
  _QWORD *v35; // [rsp+40h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]

  v6 = a2;
  v8 = 0;
  if ( !a2 )
  {
    v9 = 467;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
      (const char *)0x80004003LL,
      v33);
    return 2147500035LL;
  }
  if ( !a3 )
  {
    v9 = 468;
    goto LABEL_3;
  }
  *a2 = 0;
  *a3 = 0;
  *(_OWORD *)v34 = 0;
  v35 = 0;
  std::vector<std::wstring>::_Reserve(v34);
  v11 = v34[1];
  *((_QWORD *)v34[1] + 3) = 7;
  v11[2] = 0;
  *(_WORD *)v11 = 0;
  std::wstring::assign(v11, (char *)L"UICC", 4u);
  v12 = v11 + 4;
  v34[1] = v12;
  v13 = *((_QWORD *)this + 6);
  v14 = *(void ****)v13;
  if ( a4 )
  {
    v15 = *a4;
    if ( v15 >= 0xAAAAAAAAAAAAAAABuLL * ((__int64)(*(_QWORD *)(v13 + 8) - (_QWORD)v14) >> 4) )
    {
      v16 = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1DC,
        (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
        (const char *)0x80070057LL,
        v33);
      goto LABEL_35;
    }
    v17 = 6 * v15;
    v18 = v14[6 * v15];
    v19 = v35;
    if ( v12 == v35 )
    {
      std::vector<std::wstring>::_Reserve(v34);
      v19 = v35;
      v12 = v34[1];
    }
    v12[3] = 7;
    v12[2] = 0;
    *(_WORD *)v12 = 0;
    std::wstring::assign((void **)v12, v18, 0, 0xFFFFFFFFFFFFFFFFuLL);
    v12 += 4;
    v34[1] = v12;
    v20 = 96LL * LODWORD(v14[v17 + 5]);
    v21 = (char *)v18[7];
    if ( v12 == v19 )
    {
      std::vector<std::wstring>::_Reserve(v34);
      v12 = v34[1];
    }
    v12[3] = 7;
    v8 = 0;
    v12[2] = 0;
    *(_WORD *)v12 = 0;
    std::wstring::assign((void **)v12, (void **)&v21[v20 + 32], 0, 0xFFFFFFFFFFFFFFFFuLL);
    v6 = a2;
  }
  else
  {
    if ( *(void ****)(v13 + 8) == v14 )
      std::vector<UiccKeySet>::_Xran();
    v22 = *v14;
    if ( v12 == v35 )
    {
      std::vector<std::wstring>::_Reserve(v34);
      v12 = v34[1];
    }
    v12[3] = 7;
    v12[2] = 0;
    *(_WORD *)v12 = 0;
    std::wstring::assign((void **)v12, v22, 0, 0xFFFFFFFFFFFFFFFFuLL);
  }
  v34[1] = v12 + 4;
  v23 = (char *)v34[0];
  v24 = ((char *)(v12 + 4) - (char *)v34[0]) >> 5;
  v25 = 8 * v24;
  if ( is_mul_ok(v24, 8u) )
  {
    v26 = 0;
  }
  else
  {
    v25 = -1;
    v26 = 2147942934LL;
  }
  if ( (int)v26 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3B,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\MvTypes.h",
      (const char *)v26,
      v33);
  v27 = (unsigned __int16 **)CoTaskMemRealloc(0, v25);
  v29 = v27;
  if ( v24 && !v27 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x3F,
      (int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\MvTypes.h",
      v28);
  if ( v24 > 0xFFFFFFFF )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x41,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\inc\\MvTypes.h",
      v24 > 0xFFFFFFFF ? (const char *)0x80070216LL : 0,
      v33);
  if ( !v24 )
  {
LABEL_31:
    *v6 = v29;
    *a3 = v24;
    CoTaskMemFree(0);
    std::vector<std::wstring>::_Tidy((__int64)v34);
    return 0;
  }
  while ( 1 )
  {
    v30 = &v23[32 * v8];
    if ( *((_QWORD *)v30 + 3) >= 8u )
      v30 = *(char **)v30;
    v31 = CoAllocString((const unsigned __int16 *)v30, &v29[v8]);
    v16 = v31;
    if ( v31 < 0 )
      break;
    ++v8;
    v23 = (char *)v34[0];
    if ( v8 >= v24 )
      goto LABEL_31;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1EA,
    (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
    (const char *)(unsigned int)v31,
    (int)v29);
  v32 = 0;
  do
  {
    CoTaskMemFree(v29[v32]);
    v29[v32] = 0;
    v32 = (unsigned int)(v32 + 1);
  }
  while ( (unsigned int)v32 < (unsigned int)v24 );
  CoTaskMemFree(v29);
LABEL_35:
  std::vector<std::wstring>::_Tidy((__int64)v34);
  return v16;
}

```

## disassembly

```asm
0x18002e580  mov     [rsp-40h+arg_8], rdx
0x18002e585  push    rbp
0x18002e586  push    rbx
0x18002e587  push    rsi
0x18002e588  push    rdi
0x18002e589  push    r12
0x18002e58b  push    r13
0x18002e58d  push    r14
0x18002e58f  push    r15
0x18002e591  mov     rbp, rsp
0x18002e594  sub     rsp, 58h
0x18002e598  mov     rsi, r9
0x18002e59b  mov     r12, r8
0x18002e59e  mov     r13, rdx
0x18002e5a1  mov     rdi, rcx
0x18002e5a4  xor     r15d, r15d
0x18002e5a7  test    rdx, rdx
0x18002e5aa  jnz     short loc_18002E5D0
0x18002e5ac  mov     edx, 1D3h; void *
0x18002e5b1  mov     ebx, 80004003h
0x18002e5b6  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002e5bd  mov     r9d, ebx; char *
0x18002e5c0  mov     rcx, [rbp+40h]; this
0x18002e5c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e5c9  mov     eax, ebx
0x18002e5cb  jmp     loc_18002E841
0x18002e5d0  test    r12, r12
0x18002e5d3  jnz     short loc_18002E5DC
0x18002e5d5  mov     edx, 1D4h
0x18002e5da  jmp     short loc_18002E5B1
0x18002e5dc  mov     [rdx], r15
0x18002e5df  mov     [r8], r15d
0x18002e5e2  xorps   xmm0, xmm0
0x18002e5e5  movdqu  xmmword ptr [rbp+var_28], xmm0
0x18002e5ea  mov     [rbp+var_18], r15
0x18002e5ee  lea     rcx, [rbp+var_28]
0x18002e5f2  call    ?_Reserve@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::wstring>::_Reserve(unsigned __int64)
0x18002e5f7  mov     rbx, [rbp+var_28+8]
0x18002e5fb  mov     r14d, 7
0x18002e601  mov     [rbx+18h], r14
0x18002e605  mov     [rbx+10h], r15
0x18002e609  mov     [rbx], r15w
0x18002e60d  lea     r8d, [r14-3]
0x18002e611  lea     rdx, ?c_uicc@@3QBGB; "UICC"
0x18002e618  mov     rcx, rbx; void *
0x18002e61b  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18002e620  add     rbx, 20h ; ' '
0x18002e624  mov     [rbp+var_28+8], rbx
0x18002e628  mov     rax, [rdi+30h]
0x18002e62c  mov     rdi, [rax]
0x18002e62f  test    rsi, rsi
0x18002e632  jz      loc_18002E71D
0x18002e638  mov     ecx, [rsi]
0x18002e63a  mov     rax, [rax+8]
0x18002e63e  sub     rax, rdi
0x18002e641  sar     rax, 4
0x18002e645  mov     rdx, 0AAAAAAAAAAAAAAABh
0x18002e64f  imul    rax, rdx
0x18002e653  cmp     rcx, rax
0x18002e656  jb      short loc_18002E67A
0x18002e658  mov     rcx, [rbp+40h]; this
0x18002e65c  mov     esi, 80070057h
0x18002e661  mov     r9d, esi; char *
0x18002e664  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002e66b  mov     edx, 1DCh; void *
0x18002e670  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e675  jmp     loc_18002E897
0x18002e67a  lea     rsi, [rcx+rcx*2]
0x18002e67e  add     rsi, rsi
0x18002e681  mov     r13, [rdi+rsi*8]
0x18002e685  mov     r15, [rbp+var_18]
0x18002e689  cmp     rbx, r15
0x18002e68c  jnz     short loc_18002E69F
0x18002e68e  lea     rcx, [rbp+var_28]
0x18002e692  call    ?_Reserve@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::wstring>::_Reserve(unsigned __int64)
0x18002e697  mov     r15, [rbp+var_18]
0x18002e69b  mov     rbx, [rbp+var_28+8]
0x18002e69f  mov     [rbx+18h], r14
0x18002e6a3  mov     qword ptr [rbx+10h], 0
0x18002e6ab  xor     eax, eax
0x18002e6ad  mov     [rbx], ax
0x18002e6b0  or      r14, 0FFFFFFFFFFFFFFFFh
0x18002e6b4  mov     r9, r14
0x18002e6b7  xor     r8d, r8d
0x18002e6ba  mov     rdx, r13
0x18002e6bd  mov     rcx, rbx; void *
0x18002e6c0  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18002e6c5  add     rbx, 20h ; ' '
0x18002e6c9  mov     [rbp+var_28+8], rbx
0x18002e6cd  mov     eax, [rdi+rsi*8+28h]
0x18002e6d1  lea     rdi, [rax+rax*2]
0x18002e6d5  shl     rdi, 5
0x18002e6d9  mov     rsi, [r13+38h]
0x18002e6dd  cmp     rbx, r15
0x18002e6e0  jnz     short loc_18002E6EF
0x18002e6e2  lea     rcx, [rbp+var_28]
0x18002e6e6  call    ?_Reserve@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::wstring>::_Reserve(unsigned __int64)
0x18002e6eb  mov     rbx, [rbp+var_28+8]
0x18002e6ef  mov     qword ptr [rbx+18h], 7
0x18002e6f7  xor     r15d, r15d
0x18002e6fa  mov     [rbx+10h], r15
0x18002e6fe  mov     [rbx], r15w
0x18002e702  lea     rdx, [rsi+20h]
0x18002e706  add     rdx, rdi
0x18002e709  mov     r9, r14
0x18002e70c  xor     r8d, r8d
0x18002e70f  mov     rcx, rbx; void *
0x18002e712  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18002e717  mov     r13, [rbp+arg_8]
0x18002e71b  jmp     short loc_18002E75E
0x18002e71d  cmp     [rax+8], rdi
0x18002e721  jz      loc_18002E8B6
0x18002e727  mov     rdi, [rdi]
0x18002e72a  cmp     rbx, [rbp+var_18]
0x18002e72e  jnz     short loc_18002E73D
0x18002e730  lea     rcx, [rbp+var_28]
0x18002e734  call    ?_Reserve@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::wstring>::_Reserve(unsigned __int64)
0x18002e739  mov     rbx, [rbp+var_28+8]
0x18002e73d  mov     [rbx+18h], r14
0x18002e741  mov     [rbx+10h], r15
0x18002e745  mov     [rbx], r15w
0x18002e749  or      r14, 0FFFFFFFFFFFFFFFFh
0x18002e74d  mov     r9, r14
0x18002e750  xor     r8d, r8d
0x18002e753  mov     rdx, rdi
0x18002e756  mov     rcx, rbx; void *
0x18002e759  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18002e75e  add     rbx, 20h ; ' '
0x18002e762  mov     [rbp+var_28+8], rbx
0x18002e766  mov     rsi, [rbp+var_28]
0x18002e76a  sub     rbx, rsi
0x18002e76d  sar     rbx, 5
0x18002e771  mov     eax, 8
0x18002e776  mul     rbx
0x18002e779  test    rdx, rdx
0x18002e77c  jnz     short loc_18002E783
0x18002e77e  mov     r9d, r15d
0x18002e781  jmp     short loc_18002E78C
0x18002e783  mov     rax, r14
0x18002e786  mov     r9d, 80070216h; char *
0x18002e78c  mov     rcx, [rbp+40h]; this
0x18002e790  test    r9d, r9d
0x18002e793  js      loc_18002E8BC
0x18002e799  mov     rdx, rax; cb
0x18002e79c  xor     ecx, ecx; pv
0x18002e79e  call    cs:__imp_CoTaskMemRealloc
0x18002e7a4  mov     rdi, rax
0x18002e7a7  test    rbx, rbx
0x18002e7aa  jz      short loc_18002E7B9
0x18002e7ac  mov     rcx, [rbp+40h]; this
0x18002e7b0  test    rax, rax
0x18002e7b3  jz      loc_18002E8CE
0x18002e7b9  mov     eax, 0FFFFFFFFh
0x18002e7be  cmp     rbx, rax
0x18002e7c1  mov     r14d, ebx
0x18002e7c4  jbe     short loc_18002E7C9
0x18002e7c6  mov     r14d, eax
0x18002e7c9  cmp     rax, rbx
0x18002e7cc  sbb     r9d, r9d
0x18002e7cf  and     r9d, 80070216h; char *
0x18002e7d6  mov     rcx, [rbp+40h]; this
0x18002e7da  cmp     rbx, rax
0x18002e7dd  ja      loc_18002E8A4
0x18002e7e3  mov     [rbp+var_38], rdi
0x18002e7e7  mov     [rbp+var_30], r14d
0x18002e7eb  mov     eax, [rbp+var_2C]
0x18002e7ee  mov     [rbp+var_2C], eax
0x18002e7f1  test    rbx, rbx
0x18002e7f4  jz      short loc_18002E825
0x18002e7f6  lea     rdx, [rdi+r15*8]; unsigned __int16 **
0x18002e7fa  mov     rcx, r15
0x18002e7fd  shl     rcx, 5
0x18002e801  add     rcx, rsi
0x18002e804  cmp     qword ptr [rcx+18h], 8
0x18002e809  jb      short loc_18002E80E
0x18002e80b  mov     rcx, [rcx]; unsigned __int16 *
0x18002e80e  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x18002e813  mov     esi, eax
0x18002e815  test    eax, eax
0x18002e817  js      short loc_18002E852
0x18002e819  inc     r15
0x18002e81c  cmp     r15, rbx
0x18002e81f  mov     rsi, [rbp+var_28]
0x18002e823  jb      short loc_18002E7F6
0x18002e825  mov     [r13+0], rdi
0x18002e829  mov     [r12], r14d
0x18002e82d  xor     ecx, ecx; pv
0x18002e82f  call    cs:__imp_CoTaskMemFree
0x18002e835  nop
0x18002e836  lea     rcx, [rbp+var_28]
0x18002e83a  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18002e83f  xor     eax, eax
0x18002e841  add     rsp, 58h
0x18002e845  pop     r15
0x18002e847  pop     r14
0x18002e849  pop     r13
0x18002e84b  pop     r12
0x18002e84d  pop     rdi
0x18002e84e  pop     rsi
0x18002e84f  pop     rbx
0x18002e850  pop     rbp
0x18002e851  retn
0x18002e852  mov     rcx, [rbp+40h]; this
0x18002e856  mov     r9d, eax; char *
0x18002e859  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002e860  mov     edx, 1EAh; void *
0x18002e865  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e86a  nop
0x18002e86b  xor     r15d, r15d
0x18002e86e  test    r14d, r14d
0x18002e871  jz      short loc_18002E88D
0x18002e873  mov     rcx, [rdi+r15*8]; pv
0x18002e877  call    cs:__imp_CoTaskMemFree
0x18002e87d  mov     qword ptr [rdi+r15*8], 0
0x18002e885  inc     r15d
0x18002e888  cmp     r15d, r14d
0x18002e88b  jb      short loc_18002E873
0x18002e88d  mov     rcx, rdi; pv
0x18002e890  call    cs:__imp_CoTaskMemFree
0x18002e896  nop
0x18002e897  lea     rcx, [rbp+var_28]
0x18002e89b  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18002e8a0  mov     eax, esi
0x18002e8a2  jmp     short loc_18002E841
0x18002e8a4  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002e8ab  mov     edx, 41h ; 'A'; void *
0x18002e8b0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002e8b6  call    ?_Xran@?$vector@UUiccKeySet@@V?$allocator@UUiccKeySet@@@std@@@std@@IEBAXXZ; std::vector<UiccKeySet>::_Xran(void)
0x18002e8bc  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002e8c3  mov     edx, 3Bh ; ';'; void *
0x18002e8c8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002e8ce  lea     r8, aOnecoreuapAdmi_7; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002e8d5  mov     edx, 3Fh ; '?'; void *
0x18002e8da  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
