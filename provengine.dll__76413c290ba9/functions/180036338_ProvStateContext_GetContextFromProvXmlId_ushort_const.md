# ProvStateContext::GetContextFromProvXmlId(ushort const *)

- ea: `0x180036338`
- end: `0x180036464`
- name: `?GetContextFromProvXmlId@ProvStateContext@@QEAAAEAUPackageContext@@PEBG@Z`
- size: `300`
- prototype: `struct PackageContext *__fastcall(ProvStateContext *this, char *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x18001240c`
- `0x180018698`
- `0x180018f74`

## callees

- `0x18000b030`
- `0x180022844`
- `0x180036338`
- `0x180043750`

## import_xrefs

- `msvcp110_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18003645d`
- `msvcp110_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18003645d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180036427`
- `msvcrt!??3@YAXPEAX@Z` at `0x180036427`

## pseudocode

```c
struct PackageContext *__fastcall ProvStateContext::GetContextFromProvXmlId(ProvStateContext *this, char *a2)
{
  _QWORD *v2; // rdi
  int v3; // ebx
  unsigned __int64 v4; // r8
  _WORD *v5; // rdx
  unsigned __int64 v6; // r10
  unsigned __int64 v7; // rcx
  void **v8; // r8
  __int64 v9; // rbx
  _QWORD *v11; // [rsp+20h] [rbp-38h] BYREF
  void *v12[2]; // [rsp+28h] [rbp-30h] BYREF
  unsigned __int64 v13; // [rsp+38h] [rbp-20h]
  unsigned __int64 v14; // [rsp+40h] [rbp-18h]

  v2 = (_QWORD *)((char *)this + 48);
  v14 = 7;
  v13 = 0;
  LOWORD(v12[0]) = 0;
  v3 = -1;
  if ( *(_WORD *)a2 )
  {
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)&a2[2 * v4] );
  }
  else
  {
    v4 = 0;
  }
  std::wstring::assign(v12, a2, v4);
  std::_Tree<std::_Tmap_traits<std::wstring,PackageContext *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PackageContext *>>,0>>::lower_bound(
    v2,
    &v11,
    v12);
  if ( v11 == (_QWORD *)*v2 )
    goto LABEL_23;
  if ( v11[7] < 8u )
    v5 = v11 + 4;
  else
    v5 = (_WORD *)v11[4];
  v6 = v11[6];
  v7 = v13;
  if ( v13 >= v6 )
    v7 = v11[6];
  v8 = v12;
  if ( v14 >= 8 )
    v8 = (void **)v12[0];
  if ( v7 )
  {
    while ( *(_WORD *)v8 == *v5 )
    {
      v8 = (void **)((char *)v8 + 2);
      ++v5;
      if ( !--v7 )
        goto LABEL_16;
    }
    v3 = *(_WORD *)v8 < *v5 ? -1 : 1;
  }
  else
  {
LABEL_16:
    if ( v13 >= v6 )
      v3 = v13 != v6;
  }
  if ( v3 < 0 )
  {
LABEL_23:
    std::_Xout_of_range("invalid map<K, T> key");
    JUMPOUT(0x180036463LL);
  }
  v9 = v11[8];
  if ( v14 >= 8 )
    operator delete(v12[0]);
  return (struct PackageContext *)v9;
}

```

## disassembly

```asm
0x180036338  mov     r11, rsp
0x18003633b  mov     [r11+18h], rbx
0x18003633f  mov     [r11+20h], rsi
0x180036343  push    rdi
0x180036344  sub     rsp, 50h
0x180036348  mov     rax, cs:__security_cookie
0x18003634f  xor     rax, rsp
0x180036352  mov     [rsp+58h+var_10], rax
0x180036357  lea     rdi, [rcx+30h]
0x18003635b  mov     qword ptr [r11-18h], 7
0x180036363  xor     esi, esi
0x180036365  mov     [r11-20h], rsi
0x180036369  mov     word ptr [rsp+58h+var_30], si
0x18003636e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180036372  cmp     [rdx], si
0x180036375  jnz     short loc_18003637C
0x180036377  mov     r8d, esi
0x18003637a  jmp     short loc_180036389
0x18003637c  mov     r8, rbx
0x18003637f  inc     r8
0x180036382  cmp     [rdx+r8*2], si
0x180036387  jnz     short loc_18003637F
0x180036389  lea     rcx, [rsp+58h+var_30]; void *
0x18003638e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180036393  nop
0x180036394  lea     r8, [rsp+58h+var_30]
0x180036399  lea     rdx, [rsp+58h+var_38]
0x18003639e  mov     rcx, rdi
0x1800363a1  call    ?lower_bound@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUPackageContext@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUPackageContext@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUPackageContext@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,PackageContext *,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PackageContext *>>,0>>::lower_bound(std::wstring const &)
0x1800363a6  mov     rax, [rsp+58h+var_38]
0x1800363ab  cmp     rax, [rdi]
0x1800363ae  jz      loc_180036456
0x1800363b4  cmp     qword ptr [rax+38h], 8
0x1800363b9  jb      short loc_1800363C1
0x1800363bb  mov     rdx, [rax+20h]
0x1800363bf  jmp     short loc_1800363C5
0x1800363c1  lea     rdx, [rax+20h]
0x1800363c5  mov     r10, [rax+30h]
0x1800363c9  mov     r9, [rsp+58h+var_20]
0x1800363ce  mov     rcx, r9
0x1800363d1  cmp     r9, r10
0x1800363d4  cmovnb  rcx, r10
0x1800363d8  lea     r8, [rsp+58h+var_30]
0x1800363dd  cmp     [rsp+58h+var_18], 8
0x1800363e3  cmovnb  r8, [rsp+58h+var_30]
0x1800363e9  test    rcx, rcx
0x1800363ec  jz      short loc_180036406
0x1800363ee  movzx   r11d, word ptr [r8]
0x1800363f2  cmp     r11w, [rdx]
0x1800363f6  jnz     short loc_18003644D
0x1800363f8  add     r8, 2
0x1800363fc  add     rdx, 2
0x180036400  sub     rcx, 1
0x180036404  jnz     short loc_1800363EE
0x180036406  cmp     r9, r10
0x180036409  jb      short loc_180036412
0x18003640b  mov     edx, esi
0x18003640d  setnz   dl
0x180036410  mov     ebx, edx
0x180036412  test    ebx, ebx
0x180036414  js      short loc_180036456
0x180036416  mov     rbx, [rax+40h]
0x18003641a  cmp     [rsp+58h+var_18], 8
0x180036420  jb      short loc_18003642D
0x180036422  mov     rcx, [rsp+58h+var_30]
0x180036427  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003642d  mov     rax, rbx
0x180036430  mov     rcx, [rsp+58h+var_10]
0x180036435  xor     rcx, rsp; StackCookie
0x180036438  call    __security_check_cookie
0x18003643d  mov     rbx, [rsp+58h+arg_10]
0x180036442  mov     rsi, [rsp+58h+arg_18]
0x180036447  add     rsp, 50h
0x18003644b  pop     rdi
0x18003644c  retn
0x18003644d  sbb     ebx, ebx
0x18003644f  and     ebx, 0FFFFFFFEh
0x180036452  inc     ebx
0x180036454  jmp     short loc_180036412
0x180036456  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x18003645d  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
```
