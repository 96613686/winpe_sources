# CMVEngine::CacheProvisioningResults(_MVProvisionData const &)

- ea: `0x180012eb4`
- end: `0x180013279`
- name: `?CacheProvisioningResults@CMVEngine@@QEAAJAEBU_MVProvisionData@@@Z`
- size: `965`
- prototype: `__int64 __fastcall(CMVEngine *this, const struct _MVProvisionData *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops`

## callers

- `0x180018698`

## callees

- `0x1800021b4`
- `0x18000af20`
- `0x18000b030`
- `0x18000f5f4`
- `0x180010ad8`
- `0x180010c3c`
- `0x180012eb4`
- `0x180021e40`
- `0x180021f40`
- `0x180022088`
- `0x18003c030`
- `0x18003eb94`
- `0x18003ec58`
- `0x18003fc9c`
- `0x180043750`
- `0x180047010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180012f78`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001301d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180013037`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800130ae`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800130de`
- `msvcrt!??3@YAXPEAX@Z` at `0x180013101`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001311b`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800131c0`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001322a`
- `msvcrt!??3@YAXPEAX@Z` at `0x180012f78`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001301d`
- `msvcrt!??3@YAXPEAX@Z` at `0x180013037`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800130ae`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800130de`
- `msvcrt!??3@YAXPEAX@Z` at `0x180013101`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001311b`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800131c0`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001322a`

## pseudocode

```c
__int64 __fastcall CMVEngine::CacheProvisioningResults(CMVEngine *this, const struct _MVProvisionData *a2)
{
  char *v4; // rdx
  unsigned __int64 v5; // r8
  void **v6; // rax
  HKEY *v7; // r12
  const struct ICategoryIndex *Instance; // r15
  const struct ICategoryIndex **v9; // rax
  __int64 v10; // rcx
  const struct ICategoryIndex **v11; // rbx
  __int64 v12; // r8
  __int64 v14; // rdi
  __int64 v15; // rsi
  const unsigned __int16 *v16; // r9
  const unsigned __int16 *v17; // r8
  unsigned int v18; // r12d
  char *CategoryByID; // rax
  HKEY *v20; // [rsp+20h] [rbp-F8h]
  _QWORD v21[4]; // [rsp+28h] [rbp-F0h] BYREF
  const void *Src[2]; // [rsp+48h] [rbp-D0h] BYREF
  __int64 v23; // [rsp+58h] [rbp-C0h]
  unsigned __int64 v24; // [rsp+60h] [rbp-B8h]
  unsigned __int16 *v25[2]; // [rsp+68h] [rbp-B0h] BYREF
  __int64 v26; // [rsp+78h] [rbp-A0h]
  unsigned __int64 v27; // [rsp+80h] [rbp-98h]
  void *v28[2]; // [rsp+88h] [rbp-90h] BYREF
  __int64 v29; // [rsp+98h] [rbp-80h]
  unsigned __int64 v30; // [rsp+A0h] [rbp-78h]
  void *v31[2]; // [rsp+A8h] [rbp-70h] BYREF
  __int64 v32; // [rsp+B8h] [rbp-60h]
  unsigned __int64 v33; // [rsp+C0h] [rbp-58h]
  void *v34[3]; // [rsp+C8h] [rbp-50h] BYREF
  unsigned __int64 v35; // [rsp+E0h] [rbp-38h]

  v4 = (char *)*((_QWORD *)a2 + 6);
  v30 = 7;
  v29 = 0;
  LOWORD(v28[0]) = 0;
  if ( *(_WORD *)v4 )
  {
    v5 = -1;
    do
      ++v5;
    while ( *(_WORD *)&v4[2 * v5] );
  }
  else
  {
    v5 = 0;
  }
  std::wstring::assign(v28, v4, v5);
  v6 = (void **)std::map<std::wstring,std::unique_ptr<ProvResults>>::at((_QWORD *)this + 40, v28);
  v35 = 7;
  v34[2] = 0;
  LOWORD(v34[0]) = 0;
  std::wstring::assign(v34, v6, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( v30 >= 8 )
    operator delete(v28[0]);
  v30 = 7;
  v29 = 0;
  LOWORD(v28[0]) = 0;
  v7 = (HKEY *)*std::map<std::wstring,std::unique_ptr<ProvResults>>::at((_QWORD *)this + 38, v34);
  v20 = v7;
  Instance = CategoryIndex::GetInstance();
  v9 = (const struct ICategoryIndex **)operator new(8u);
  v11 = v9;
  v21[3] = v9;
  *v9 = Instance;
  v24 = 7;
  v23 = 0;
  LOWORD(Src[0]) = 0;
  v27 = 7;
  v26 = 0;
  LOWORD(v25[0]) = 0;
  v12 = *((_QWORD *)a2 + 2);
  if ( v12 )
  {
    CategoryResolver::GetPaths(v10, v21, v12);
    v14 = v21[0];
    v15 = v21[1];
    while ( v14 != v15 )
    {
      std::vector<std::wstring>::vector<std::wstring>(v28, v14);
      v18 = (**(__int64 (__fastcall ***)(const struct ICategoryIndex *, void **))Instance)(Instance, v28);
      if ( v23 )
        std::wstring::append(Src, (char *)L"/");
      CategoryByID = (char *)CategoryIndex::GetCategoryByID(v18);
      std::wstring::append(Src, CategoryByID);
      (*(void (__fastcall **)(const struct ICategoryIndex *, void **, void **))(*(_QWORD *)Instance + 32LL))(
        Instance,
        v31,
        v28);
      if ( v32 )
      {
        if ( v26 )
          std::wstring::append((const void **)v25, (char *)L"/");
        std::wstring::append(v25, v31, 0, 0xFFFFFFFFFFFFFFFFuLL);
        if ( v33 >= 8 )
          operator delete(v31[0]);
      }
      else
      {
        if ( v33 >= 8 )
          operator delete(v31[0]);
        v33 = 7;
        v32 = 0;
        LOWORD(v31[0]) = 0;
      }
      std::vector<std::wstring>::_Tidy((__int64)v28);
      v14 += 24;
      v7 = v20;
    }
    v16 = (const unsigned __int16 *)v25;
    if ( v27 >= 8 )
      v16 = v25[0];
    v17 = (const unsigned __int16 *)Src;
    if ( v24 >= 8 )
      v17 = (const unsigned __int16 *)Src[0];
    ProvResults::AddResult(v7, a2, v17, v16);
    std::vector<std::vector<std::wstring>>::~vector<std::vector<std::wstring>>(v21);
    if ( v27 >= 8 )
      operator delete(v25[0]);
    v27 = 7;
    v26 = 0;
    LOWORD(v25[0]) = 0;
    if ( v24 >= 8 )
      operator delete((void *)Src[0]);
    v24 = 7;
    v23 = 0;
    LOWORD(Src[0]) = 0;
    if ( v11 )
      operator delete(v11);
    if ( v35 >= 8 )
      operator delete(v34[0]);
    return 0;
  }
  else
  {
    v27 = 7;
    v26 = 0;
    LOWORD(v25[0]) = 0;
    v24 = 7;
    v23 = 0;
    LOWORD(Src[0]) = 0;
    operator delete(v9);
    if ( v35 >= 8 )
      operator delete(v34[0]);
    return 0;
  }
}

```

## disassembly

```asm
0x180012eb4  mov     r11, rsp
0x180012eb7  mov     [r11+18h], rbx
0x180012ebb  push    rsi
0x180012ebc  push    rdi
0x180012ebd  push    r12
0x180012ebf  push    r13
0x180012ec1  push    r15
0x180012ec3  sub     rsp, 0F0h
0x180012eca  mov     rax, cs:__security_cookie
0x180012ed1  xor     rax, rsp
0x180012ed4  mov     [rsp+118h+var_30], rax
0x180012edc  mov     r13, rdx
0x180012edf  mov     rbx, rcx
0x180012ee2  xor     edi, edi
0x180012ee4  mov     rdx, [rdx+30h]; Src
0x180012ee8  lea     esi, [rdi+7]
0x180012eeb  mov     [r11-78h], rsi
0x180012eef  mov     [r11-80h], rdi
0x180012ef3  mov     word ptr [rsp+118h+var_90], di
0x180012efb  cmp     [rdx], di
0x180012efe  jnz     short loc_180012F05
0x180012f00  mov     r8d, edi
0x180012f03  jmp     short loc_180012F13
0x180012f05  or      r8, 0FFFFFFFFFFFFFFFFh
0x180012f09  inc     r8
0x180012f0c  cmp     [rdx+r8*2], di
0x180012f11  jnz     short loc_180012F09
0x180012f13  lea     rcx, [rsp+118h+var_90]; void *
0x180012f1b  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180012f20  nop
0x180012f21  lea     rcx, [rbx+140h]
0x180012f28  lea     rdx, [rsp+118h+var_90]
0x180012f30  call    ?at@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@@2@@std@@QEAAAEAV?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::map<std::wstring,std::unique_ptr<ProvResults>>::at(std::wstring const &)
0x180012f35  mov     [rsp+118h+var_38], rsi
0x180012f3d  mov     [rsp+118h+var_40], rdi
0x180012f45  mov     word ptr [rsp+118h+var_50], di
0x180012f4d  or      r9, 0FFFFFFFFFFFFFFFFh
0x180012f51  xor     r8d, r8d
0x180012f54  mov     rdx, rax
0x180012f57  lea     rcx, [rsp+118h+var_50]; void *
0x180012f5f  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180012f64  nop
0x180012f65  cmp     [rsp+118h+var_78], 8
0x180012f6e  jb      short loc_180012F7E
0x180012f70  mov     rcx, [rsp+118h+var_90]
0x180012f78  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180012f7e  mov     [rsp+118h+var_78], rsi
0x180012f86  mov     [rsp+118h+var_80], rdi
0x180012f8e  mov     word ptr [rsp+118h+var_90], di
0x180012f96  lea     rcx, [rbx+130h]
0x180012f9d  lea     rdx, [rsp+118h+var_50]
0x180012fa5  call    ?at@?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@@std@@@2@@std@@QEAAAEAV?$unique_ptr@VProvResults@@U?$default_delete@VProvResults@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::map<std::wstring,std::unique_ptr<ProvResults>>::at(std::wstring const &)
0x180012faa  mov     r12, [rax]
0x180012fad  mov     [rsp+118h+var_F8], r12
0x180012fb2  call    ?GetInstance@CategoryIndex@@SAPEBUICategoryIndex@@XZ; CategoryIndex::GetInstance(void)
0x180012fb7  mov     r15, rax
0x180012fba  mov     ecx, 8; Size
0x180012fbf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012fc4  mov     rbx, rax
0x180012fc7  mov     [rsp+118h+var_D8], rax
0x180012fcc  mov     [rax], r15
0x180012fcf  mov     [rsp+118h+var_B8], rsi
0x180012fd4  mov     [rsp+118h+var_C0], rdi
0x180012fd9  mov     word ptr [rsp+118h+Src], di
0x180012fde  mov     [rsp+118h+var_98], rsi
0x180012fe6  mov     [rsp+118h+var_A0], rdi
0x180012feb  mov     word ptr [rsp+118h+var_B0], di
0x180012ff0  mov     r8, [r13+10h]
0x180012ff4  test    r8, r8
0x180012ff7  jnz     short loc_180013044
0x180012ff9  mov     [rsp+118h+var_98], rsi
0x180013001  mov     [rsp+118h+var_A0], rdi
0x180013006  mov     word ptr [rsp+118h+var_B0], di
0x18001300b  mov     [rsp+118h+var_B8], rsi
0x180013010  mov     [rsp+118h+var_C0], rdi
0x180013015  mov     word ptr [rsp+118h+Src], di
0x18001301a  mov     rcx, rax
0x18001301d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180013023  nop
0x180013024  cmp     [rsp+118h+var_38], 8
0x18001302d  jb      short loc_18001303D
0x18001302f  mov     rcx, [rsp+118h+var_50]
0x180013037  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001303d  xor     eax, eax
0x18001303f  jmp     loc_180013250
0x180013044  lea     rdx, [rsp+118h+var_F0]
0x180013049  call    ?GetPaths@CategoryResolver@@QEAA?AV?$vector@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$allocator@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@std@@PEAG@Z; CategoryResolver::GetPaths(ushort *)
0x18001304e  nop
0x18001304f  mov     rdi, [rsp+118h+var_F0]
0x180013054  mov     rsi, [rsp+118h+var_E8]
0x180013059  cmp     rdi, rsi
0x18001305c  jnz     loc_180013128
0x180013062  lea     r9, [rsp+118h+var_B0]
0x180013067  cmp     [rsp+118h+var_98], 8
0x180013070  cmovnb  r9, [rsp+118h+var_B0]; unsigned __int16 *
0x180013076  lea     r8, [rsp+118h+Src]
0x18001307b  cmp     [rsp+118h+var_B8], 8
0x180013081  cmovnb  r8, [rsp+118h+Src]; unsigned __int16 *
0x180013087  mov     rdx, r13; struct _MVProvisionData *
0x18001308a  mov     rcx, r12; this
0x18001308d  call    ?AddResult@ProvResults@@QEBAXAEBU_MVProvisionData@@PEBG1@Z; ProvResults::AddResult(_MVProvisionData const &,ushort const *,ushort const *)
0x180013092  nop
0x180013093  lea     rcx, [rsp+118h+var_F0]
0x180013098  call    ??1?$vector@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@V?$allocator@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::vector<std::wstring>>::~vector<std::vector<std::wstring>>(void)
0x18001309d  nop
0x18001309e  cmp     [rsp+118h+var_98], 8
0x1800130a7  jb      short loc_1800130B4
0x1800130a9  mov     rcx, [rsp+118h+var_B0]
0x1800130ae  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800130b4  mov     edi, 7
0x1800130b9  mov     [rsp+118h+var_98], rdi
0x1800130c1  mov     [rsp+118h+var_A0], 0
0x1800130ca  xor     eax, eax
0x1800130cc  mov     word ptr [rsp+118h+var_B0], ax
0x1800130d1  cmp     [rsp+118h+var_B8], 8
0x1800130d7  jb      short loc_1800130E4
0x1800130d9  mov     rcx, [rsp+118h+Src]
0x1800130de  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800130e4  mov     [rsp+118h+var_B8], rdi
0x1800130e9  mov     [rsp+118h+var_C0], 0
0x1800130f2  xor     eax, eax
0x1800130f4  mov     word ptr [rsp+118h+Src], ax
0x1800130f9  test    rbx, rbx
0x1800130fc  jz      short loc_180013108
0x1800130fe  mov     rcx, rbx
0x180013101  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180013107  nop
0x180013108  cmp     [rsp+118h+var_38], 8
0x180013111  jb      short loc_180013121
0x180013113  mov     rcx, [rsp+118h+var_50]
0x18001311b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180013121  xor     eax, eax
0x180013123  jmp     loc_180013250
0x180013128  mov     rdx, rdi
0x18001312b  lea     rcx, [rsp+118h+var_90]
0x180013133  call    ??0?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::wstring>::vector<std::wstring>(std::vector<std::wstring> const &)
0x180013138  nop
0x180013139  mov     rax, [r15]
0x18001313c  lea     rdx, [rsp+118h+var_90]
0x180013144  mov     rcx, r15
0x180013147  mov     rax, [rax]
0x18001314a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001314f  mov     r12d, eax
0x180013152  cmp     [rsp+118h+var_C0], 0
0x180013158  jz      short loc_18001316B
0x18001315a  lea     rdx, asc_180049F24; "/"
0x180013161  lea     rcx, [rsp+118h+Src]; Src
0x180013166  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18001316b  mov     ecx, r12d; unsigned int
0x18001316e  call    ?GetCategoryByID@CategoryIndex@@SAPEBGI@Z; CategoryIndex::GetCategoryByID(uint)
0x180013173  mov     rdx, rax; void *
0x180013176  lea     rcx, [rsp+118h+Src]; Src
0x18001317b  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x180013180  mov     rax, [r15]
0x180013183  lea     r8, [rsp+118h+var_90]
0x18001318b  lea     rdx, [rsp+118h+var_70]
0x180013193  mov     rcx, r15
0x180013196  mov     rax, [rax+20h]
0x18001319a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001319f  nop
0x1800131a0  xor     r12d, r12d
0x1800131a3  cmp     [rsp+118h+var_60], r12
0x1800131ab  jnz     short loc_1800131E5
0x1800131ad  cmp     [rsp+118h+var_58], 8
0x1800131b6  jb      short loc_1800131C6
0x1800131b8  mov     rcx, [rsp+118h+var_70]
0x1800131c0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800131c6  mov     [rsp+118h+var_58], 7
0x1800131d2  mov     [rsp+118h+var_60], r12
0x1800131da  mov     word ptr [rsp+118h+var_70], r12w
0x1800131e3  jmp     short loc_180013231
0x1800131e5  cmp     [rsp+118h+var_A0], r12
0x1800131ea  jz      short loc_1800131FD
0x1800131ec  lea     rdx, asc_180049F24; "/"
0x1800131f3  lea     rcx, [rsp+118h+var_B0]; Src
0x1800131f8  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x1800131fd  or      r9, 0FFFFFFFFFFFFFFFFh
0x180013201  xor     r8d, r8d
0x180013204  lea     rdx, [rsp+118h+var_70]
0x18001320c  lea     rcx, [rsp+118h+var_B0]
0x180013211  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x180013216  nop
0x180013217  cmp     [rsp+118h+var_58], 8
0x180013220  jb      short loc_180013231
0x180013222  mov     rcx, [rsp+118h+var_70]
0x18001322a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180013230  nop
0x180013231  lea     rcx, [rsp+118h+var_90]
0x180013239  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18001323e  add     rdi, 18h
0x180013242  mov     r12, [rsp+118h+var_F8]
0x180013247  jmp     loc_180013059
0x18001324c  mov     eax, dword ptr [rsp+118h+var_F8]
0x180013250  mov     rcx, [rsp+118h+var_30]
0x180013258  xor     rcx, rsp; StackCookie
0x18001325b  call    __security_check_cookie
0x180013260  mov     rbx, [rsp+118h+arg_10]
0x180013268  add     rsp, 0F0h
0x18001326f  pop     r15
0x180013271  pop     r13
0x180013273  pop     r12
0x180013275  pop     rdi
0x180013276  pop     rsi
0x180013277  retn
```
