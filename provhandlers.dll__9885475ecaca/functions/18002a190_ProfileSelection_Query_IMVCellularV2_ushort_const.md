# ProfileSelection::Query(IMVCellularV2 *,ushort const *)

- ea: `0x18002a190`
- end: `0x18002a347`
- name: `?Query@ProfileSelection@@SA?AV?$unique_ptr@VProfileSelection@@U?$default_delete@VProfileSelection@@@std@@@std@@PEAUIMVCellularV2@@PEBG@Z`
- size: `439`
- prototype: `ProfileSelection **__fastcall(ProfileSelection **, __int64 *, __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180027220`
- `0x1800308d0`

## callees

- `0x180002034`
- `0x180012d80`
- `0x180026240`
- `0x18002a190`
- `0x18002b1a0`
- `0x18003b9a0`
- `0x18003f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002a2e8`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002a2f2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002a2e8`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002a2f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a295`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a308`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a295`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a308`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
ProfileSelection **__fastcall ProfileSelection::Query(ProfileSelection **a1, __int64 *a2, __int16 *a3)
{
  __int64 v6; // rax
  __int64 v7; // rdx
  _WORD *v8; // r8
  __int16 v9; // cx
  _WORD *v10; // rcx
  __int64 v11; // rax
  bool v12; // bl
  void *v13; // rcx
  ProfileSelection *v14; // rax
  ProfileSelection *v15; // rdi
  void **v16; // rbx
  void *v17; // rcx
  int v19; // [rsp+20h] [rbp-49h]
  unsigned int v20; // [rsp+30h] [rbp-39h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-31h] BYREF
  int v22; // [rsp+40h] [rbp-29h]
  LPVOID *p_pv; // [rsp+48h] [rbp-21h]
  void *v24; // [rsp+50h] [rbp-19h] BYREF
  char v25; // [rsp+58h] [rbp-11h]
  ProfileSelection **v26; // [rsp+60h] [rbp-9h]
  ProfileSelection *v27; // [rsp+68h] [rbp-1h]
  _OWORD v28[3]; // [rsp+70h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v26 = a1;
  *a1 = 0;
  v22 = 1;
  memset(v28, 0, sizeof(v28));
  v6 = 2147483646;
  v7 = 21;
  v8 = v28;
  do
  {
    if ( !v6 )
      break;
    v9 = *a3;
    if ( !*a3 )
      break;
    ++a3;
    *v8++ = v9;
    --v6;
    --v7;
  }
  while ( v7 );
  v10 = v8 - 1;
  if ( v7 )
    v10 = v8;
  *v10 = 0;
  if ( !v7 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x6A,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\profileselection.cpp",
      (const char *)0x8007007ALL,
      v19);
  v20 = 0;
  pv = 0;
  v11 = *a2;
  p_pv = &pv;
  v24 = 0;
  v25 = 1;
  v12 = (*(int (__fastcall **)(__int64 *, _OWORD *, unsigned int *, void **))(v11 + 56))(a2, v28, &v20, &v24) >= 0;
  if ( v25 )
  {
    v13 = *p_pv;
    *p_pv = v24;
    if ( v13 )
      CoTaskMemFree(v13);
  }
  if ( v12 && v20 )
  {
    v14 = (ProfileSelection *)operator new(0x18u);
    v27 = v14;
    v15 = v14 ? ProfileSelection::ProfileSelection(v14, (const unsigned __int8 *)pv, v20) : 0LL;
    v16 = (void **)*a1;
    if ( v15 != *a1 )
    {
      if ( v16 )
      {
        std::_Tree<std::_Tmap_traits<unsigned short const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<unsigned short const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::clear(*a1);
        operator delete(*v16);
        operator delete(v16);
      }
      *a1 = v15;
    }
  }
  v17 = pv;
  pv = 0;
  if ( v17 )
    CoTaskMemFree(v17);
  return a1;
}

```

## disassembly

```asm
0x18002a190  mov     [rsp-8+arg_10], rbx
0x18002a195  mov     [rsp-8+arg_18], rsi
0x18002a19a  push    rbp
0x18002a19b  push    rdi
0x18002a19c  push    r14
0x18002a19e  lea     rbp, [rsp-47h]
0x18002a1a3  sub     rsp, 0B0h
0x18002a1aa  mov     rax, cs:__security_cookie
0x18002a1b1  xor     rax, rsp
0x18002a1b4  mov     [rbp+57h+var_20], rax
0x18002a1b8  mov     r9, r8
0x18002a1bb  mov     r10, rdx
0x18002a1be  mov     rsi, rcx
0x18002a1c1  mov     [rbp+57h+var_60], rcx
0x18002a1c5  xor     r14d, r14d
0x18002a1c8  mov     [rbp+57h+var_80], r14d
0x18002a1cc  mov     [rcx], r14
0x18002a1cf  mov     [rbp+57h+var_80], 1
0x18002a1d6  xorps   xmm0, xmm0
0x18002a1d9  movups  [rbp+57h+var_50], xmm0
0x18002a1dd  movups  [rbp+57h+var_40], xmm0
0x18002a1e1  movups  [rbp+57h+var_30], xmm0
0x18002a1e5  mov     eax, 7FFFFFFEh
0x18002a1ea  lea     edx, [r14+15h]
0x18002a1ee  lea     r8, [rbp+57h+var_50]
0x18002a1f2  test    rax, rax
0x18002a1f5  jz      short loc_18002A215
0x18002a1f7  movzx   ecx, word ptr [r9]
0x18002a1fb  test    cx, cx
0x18002a1fe  jz      short loc_18002A215
0x18002a200  add     r9, 2
0x18002a204  mov     [r8], cx
0x18002a208  add     r8, 2
0x18002a20c  dec     rax
0x18002a20f  sub     rdx, 1
0x18002a213  jnz     short loc_18002A1F2
0x18002a215  mov     rax, rdx
0x18002a218  neg     rax
0x18002a21b  sbb     r9d, r9d
0x18002a21e  not     r9d
0x18002a221  and     r9d, 8007007Ah; char *
0x18002a228  lea     rcx, [r8-2]
0x18002a22c  test    rdx, rdx
0x18002a22f  cmovnz  rcx, r8
0x18002a233  mov     [rcx], r14w
0x18002a237  mov     rcx, [rbp+5Fh]; this
0x18002a23b  jz      loc_18002A335
0x18002a241  mov     [rbp+57h+var_90], r14d
0x18002a245  mov     [rbp+57h+pv], r14
0x18002a249  mov     rax, [r10]
0x18002a24c  lea     rcx, [rbp+57h+pv]
0x18002a250  mov     [rbp+57h+var_78], rcx
0x18002a254  mov     [rbp+57h+var_70], r14
0x18002a258  mov     [rbp+57h+var_68], 1
0x18002a25c  lea     r9, [rbp+57h+var_70]
0x18002a260  lea     r8, [rbp+57h+var_90]
0x18002a264  lea     rdx, [rbp+57h+var_50]
0x18002a268  mov     rcx, r10
0x18002a26b  mov     rax, [rax+38h]
0x18002a26f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a274  mov     ebx, eax
0x18002a276  shr     ebx, 1Fh
0x18002a279  xor     bl, 1
0x18002a27c  cmp     [rbp+57h+var_68], r14b
0x18002a280  jz      short loc_18002A29B
0x18002a282  mov     rdx, [rbp+57h+var_78]
0x18002a286  mov     rcx, [rdx]; pv
0x18002a289  mov     rax, [rbp+57h+var_70]
0x18002a28d  mov     [rdx], rax
0x18002a290  test    rcx, rcx
0x18002a293  jz      short loc_18002A29B
0x18002a295  call    cs:__imp_CoTaskMemFree
0x18002a29b  test    bl, bl
0x18002a29d  jz      short loc_18002A2FB
0x18002a29f  cmp     [rbp+57h+var_90], r14d
0x18002a2a3  jbe     short loc_18002A2FB
0x18002a2a5  mov     ecx, 18h; Size
0x18002a2aa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002a2af  mov     [rbp+57h+var_58], rax
0x18002a2b3  test    rax, rax
0x18002a2b6  jz      short loc_18002A2CD
0x18002a2b8  mov     r8d, [rbp+57h+var_90]; unsigned int
0x18002a2bc  mov     rdx, [rbp+57h+pv]; unsigned __int8 *
0x18002a2c0  mov     rcx, rax; this
0x18002a2c3  call    ??0ProfileSelection@@QEAA@PEBEK@Z; ProfileSelection::ProfileSelection(uchar const *,ulong)
0x18002a2c8  mov     rdi, rax
0x18002a2cb  jmp     short loc_18002A2D0
0x18002a2cd  mov     rdi, r14
0x18002a2d0  mov     rbx, [rsi]
0x18002a2d3  cmp     rdi, rbx
0x18002a2d6  jz      short loc_18002A2FB
0x18002a2d8  test    rbx, rbx
0x18002a2db  jz      short loc_18002A2F8
0x18002a2dd  mov     rcx, rbx
0x18002a2e0  call    ?clear@?$_Tree@V?$_Tmap_traits@PEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@Ukeyname_less@@V?$allocator@U?$pair@QEBGV?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@$0A@@std@@@std@@QEAAXXZ; std::_Tree<std::_Tmap_traits<ushort const *,Microsoft::WRL::ComPtr<IMVKey>,keyname_less,std::allocator<std::pair<ushort const * const,Microsoft::WRL::ComPtr<IMVKey>>>,0>>::clear(void)
0x18002a2e5  mov     rcx, [rbx]
0x18002a2e8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002a2ee  nop
0x18002a2ef  mov     rcx, rbx
0x18002a2f2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18002a2f8  mov     [rsi], rdi
0x18002a2fb  mov     rcx, [rbp+57h+pv]; pv
0x18002a2ff  mov     [rbp+57h+pv], r14
0x18002a303  test    rcx, rcx
0x18002a306  jz      short loc_18002A30E
0x18002a308  call    cs:__imp_CoTaskMemFree
0x18002a30e  mov     rax, rsi
0x18002a311  mov     rcx, [rbp+57h+var_20]
0x18002a315  xor     rcx, rsp; StackCookie
0x18002a318  call    __security_check_cookie
0x18002a31d  lea     r11, [rsp+0C0h+var_10]
0x18002a325  mov     rbx, [r11+30h]
0x18002a329  mov     rsi, [r11+38h]
0x18002a32d  mov     rsp, r11
0x18002a330  pop     r14
0x18002a332  pop     rdi
0x18002a333  pop     rbp
0x18002a334  retn
0x18002a335  lea     r8, aOnecoreuapAdmi_14; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18002a33c  mov     edx, 6Ah ; 'j'; void *
0x18002a341  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
