# CUiccHandler2::GetContextPath(ushort * *,ulong const *)

- ea: `0x18002e8f0`
- end: `0x18002ead2`
- name: `?GetContextPath@CUiccHandler2@@UEAAJPEAPEAGPEBK@Z`
- size: `482`
- prototype: `__int64 __fastcall(CUiccHandler2 *this, unsigned __int16 **, const unsigned int *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callees

- `0x1800076a4`
- `0x18000dfb0`
- `0x18000e308`
- `0x180010084`
- `0x180012e18`
- `0x180012e30`
- `0x18002e8f0`
- `0x18003b9a0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002eaad`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002eaad`

## pseudocode

```c
__int64 __fastcall CUiccHandler2::GetContextPath(CUiccHandler2 *this, unsigned __int16 **a2, const unsigned int *a3)
{
  unsigned int v6; // ebx
  unsigned __int16 **v7; // rcx
  __int64 v8; // rdx
  unsigned __int16 **v9; // rax
  char **v10; // rax
  char *v11; // rbx
  unsigned __int64 v12; // rcx
  __int64 v13; // rsi
  _QWORD *v14; // r14
  unsigned __int16 **v15; // rcx
  __int64 v16; // rdx
  unsigned __int16 **v17; // rax
  _QWORD *v18; // rdx
  const unsigned __int16 *v19; // rcx
  unsigned __int16 *v21[2]; // [rsp+20h] [rbp-30h] BYREF
  __int64 v22; // [rsp+30h] [rbp-20h]
  unsigned __int64 v23; // [rsp+38h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+28h]

  if ( !a2 )
  {
    v6 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B8,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
      (const char *)0x80004003LL,
      (int)v21[0]);
    return v6;
  }
  *a2 = 0;
  v23 = 7;
  v22 = 0;
  LOWORD(v21[0]) = 0;
  std::wstring::assign(v21, (char *)L"UICC", 4u);
  v7 = v21;
  if ( v23 >= 8 )
    v7 = (unsigned __int16 **)v21[0];
  v8 = (__int64)v7 + 2 * v22;
  v9 = v21;
  if ( v23 >= 8 )
    v9 = (unsigned __int16 **)v21[0];
  if ( v8 )
    v8 = (v8 - (__int64)v9) >> 1;
  std::wstring::insert(v21, v8, 1);
  v10 = (char **)*((_QWORD *)this + 6);
  v11 = *v10;
  if ( !a3 )
  {
    if ( v10[1] == v11 )
      std::vector<UiccKeySet>::_Xran();
    v18 = *(_QWORD **)v11;
    goto LABEL_21;
  }
  v12 = *a3;
  if ( v12 < 0xAAAAAAAAAAAAAAABuLL * ((v10[1] - v11) >> 4) )
  {
    v13 = 6 * v12;
    v14 = *(_QWORD **)&v11[48 * v12];
    std::wstring::append(v21, v14, 0, 0xFFFFFFFFFFFFFFFFuLL);
    v15 = v21;
    if ( v23 >= 8 )
      v15 = (unsigned __int16 **)v21[0];
    v16 = (__int64)v15 + 2 * v22;
    v17 = v21;
    if ( v23 >= 8 )
      v17 = (unsigned __int16 **)v21[0];
    if ( v16 )
      v16 = (v16 - (__int64)v17) >> 1;
    std::wstring::insert(v21, v16, 1);
    v18 = (_QWORD *)(96LL * *(unsigned int *)&v11[8 * v13 + 40] + v14[7] + 32LL);
LABEL_21:
    std::wstring::append(v21, v18, 0, 0xFFFFFFFFFFFFFFFFuLL);
    v19 = (const unsigned __int16 *)v21;
    if ( v23 >= 8 )
      v19 = v21[0];
    v6 = CoAllocString(v19, a2);
    goto LABEL_24;
  }
  v6 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1C0,
    (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\uicchandler2.cpp",
    (const char *)0x80070057LL,
    (int)v21[0]);
LABEL_24:
  if ( v23 >= 8 )
    operator delete(v21[0]);
  return v6;
}

```

## disassembly

```asm
0x18002e8f0  push    rbp
0x18002e8f2  push    rbx
0x18002e8f3  push    rsi
0x18002e8f4  push    rdi
0x18002e8f5  push    r14
0x18002e8f7  mov     rbp, rsp
0x18002e8fa  sub     rsp, 50h
0x18002e8fe  mov     rax, cs:__security_cookie
0x18002e905  xor     rax, rsp
0x18002e908  mov     [rbp+var_10], rax
0x18002e90c  mov     rsi, r8
0x18002e90f  mov     rdi, rdx
0x18002e912  mov     rbx, rcx
0x18002e915  test    rdx, rdx
0x18002e918  jnz     short loc_18002E93C
0x18002e91a  mov     rcx, [rbp+28h]; this
0x18002e91e  mov     ebx, 80004003h
0x18002e923  mov     r9d, ebx; char *
0x18002e926  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002e92d  mov     edx, 1B8h; void *
0x18002e932  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e937  jmp     loc_18002EAB3
0x18002e93c  mov     qword ptr [rdx], 0
0x18002e943  mov     [rbp+var_18], 7
0x18002e94b  mov     [rbp+var_20], 0
0x18002e953  xor     eax, eax
0x18002e955  mov     word ptr [rbp+var_30], ax
0x18002e959  lea     r8d, [rax+4]
0x18002e95d  lea     rdx, ?c_uicc@@3QBGB; "UICC"
0x18002e964  lea     rcx, [rbp+var_30]; void *
0x18002e968  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18002e96d  nop
0x18002e96e  lea     rcx, [rbp+var_30]
0x18002e972  cmp     [rbp+var_18], 8
0x18002e977  cmovnb  rcx, [rbp+var_30]
0x18002e97c  mov     rax, [rbp+var_20]
0x18002e980  lea     rdx, [rcx+rax*2]
0x18002e984  lea     rax, [rbp+var_30]
0x18002e988  cmovnb  rax, [rbp+var_30]
0x18002e98d  test    rdx, rdx
0x18002e990  jz      short loc_18002E998
0x18002e992  sub     rdx, rax
0x18002e995  sar     rdx, 1
0x18002e998  mov     r9d, 5Ch ; '\'
0x18002e99e  lea     r8d, [r9-5Bh]
0x18002e9a2  lea     rcx, [rbp+var_30]
0x18002e9a6  call    ?insert@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0G@Z; std::wstring::insert(unsigned __int64,unsigned __int64,ushort)
0x18002e9ab  mov     rax, [rbx+30h]
0x18002e9af  mov     rbx, [rax]
0x18002e9b2  test    rsi, rsi
0x18002e9b5  jz      loc_18002EA71
0x18002e9bb  mov     ecx, [rsi]
0x18002e9bd  mov     rax, [rax+8]
0x18002e9c1  sub     rax, rbx
0x18002e9c4  sar     rax, 4
0x18002e9c8  mov     rdx, 0AAAAAAAAAAAAAAABh
0x18002e9d2  imul    rax, rdx
0x18002e9d6  cmp     rcx, rax
0x18002e9d9  jb      short loc_18002E9FD
0x18002e9db  mov     rcx, [rbp+28h]; this
0x18002e9df  mov     ebx, 80070057h
0x18002e9e4  mov     r9d, ebx; char *
0x18002e9e7  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002e9ee  mov     edx, 1C0h; void *
0x18002e9f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e9f8  jmp     loc_18002EAA2
0x18002e9fd  lea     rsi, [rcx+rcx*2]
0x18002ea01  add     rsi, rsi
0x18002ea04  mov     r14, [rbx+rsi*8]
0x18002ea08  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002ea0c  xor     r8d, r8d
0x18002ea0f  mov     rdx, r14
0x18002ea12  lea     rcx, [rbp+var_30]
0x18002ea16  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x18002ea1b  lea     rcx, [rbp+var_30]
0x18002ea1f  cmp     [rbp+var_18], 8
0x18002ea24  cmovnb  rcx, [rbp+var_30]
0x18002ea29  mov     rax, [rbp+var_20]
0x18002ea2d  lea     rdx, [rcx+rax*2]
0x18002ea31  lea     rax, [rbp+var_30]
0x18002ea35  cmovnb  rax, [rbp+var_30]
0x18002ea3a  test    rdx, rdx
0x18002ea3d  jz      short loc_18002EA45
0x18002ea3f  sub     rdx, rax
0x18002ea42  sar     rdx, 1
0x18002ea45  mov     r9d, 5Ch ; '\'
0x18002ea4b  lea     r8d, [r9-5Bh]
0x18002ea4f  lea     rcx, [rbp+var_30]
0x18002ea53  call    ?insert@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_K0G@Z; std::wstring::insert(unsigned __int64,unsigned __int64,ushort)
0x18002ea58  mov     eax, [rbx+rsi*8+28h]
0x18002ea5c  lea     rcx, [rax+rax*2]
0x18002ea60  shl     rcx, 5
0x18002ea64  mov     rdx, [r14+38h]
0x18002ea68  add     rdx, 20h ; ' '
0x18002ea6c  add     rdx, rcx
0x18002ea6f  jmp     short loc_18002EA7A
0x18002ea71  cmp     [rax+8], rbx
0x18002ea75  jz      short loc_18002EACC
0x18002ea77  mov     rdx, [rbx]
0x18002ea7a  or      r9, 0FFFFFFFFFFFFFFFFh
0x18002ea7e  xor     r8d, r8d
0x18002ea81  lea     rcx, [rbp+var_30]
0x18002ea85  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x18002ea8a  lea     rcx, [rbp+var_30]
0x18002ea8e  cmp     [rbp+var_18], 8
0x18002ea93  cmovnb  rcx, [rbp+var_30]; unsigned __int16 *
0x18002ea98  mov     rdx, rdi; unsigned __int16 **
0x18002ea9b  call    ?CoAllocString@@YAJPEBGPEAPEAG@Z; CoAllocString(ushort const *,ushort * *)
0x18002eaa0  mov     ebx, eax
0x18002eaa2  cmp     [rbp+var_18], 8
0x18002eaa7  jb      short loc_18002EAB3
0x18002eaa9  mov     rcx, [rbp+var_30]
0x18002eaad  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002eab3  mov     eax, ebx
0x18002eab5  mov     rcx, [rbp+var_10]
0x18002eab9  xor     rcx, rsp; StackCookie
0x18002eabc  call    __security_check_cookie
0x18002eac1  add     rsp, 50h
0x18002eac5  pop     r14
0x18002eac7  pop     rdi
0x18002eac8  pop     rsi
0x18002eac9  pop     rbx
0x18002eaca  pop     rbp
0x18002eacb  retn
0x18002eacc  call    ?_Xran@?$vector@UUiccKeySet@@V?$allocator@UUiccKeySet@@@std@@@std@@IEBAXXZ; std::vector<UiccKeySet>::_Xran(void)
```
