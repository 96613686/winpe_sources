# CreateWmiPath(ushort const *,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> &,IConfigManager2URI * *)

- ea: `0x18000eae0`
- end: `0x18000ee10`
- name: `?CreateWmiPath@@YAJPEBGAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@2@PEAPEAUIConfigManager2URI@@@Z`
- size: `816`
- prototype: `__int64 __fastcall(_WORD *, __int64 *, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010864`

## callees

- `0x1800022e0`
- `0x180007720`
- `0x180007b38`
- `0x180007bec`
- `0x180007f40`
- `0x18000820c`
- `0x18000977c`
- `0x180009850`
- `0x18000dca4`
- `0x18000eae0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000eb51`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000eb51`

## pseudocode

```c
__int64 __fastcall CreateWmiPath(_WORD *a1, __int64 *a2, _QWORD *a3, __int64 a4)
{
  HRESULT v8; // ebx
  LPVOID v9; // rcx
  LPVOID v10; // rcx
  LPVOID v11; // rcx
  unsigned __int64 v12; // r8
  __int64 v13; // rbx
  __int64 v14; // rdi
  unsigned __int64 v15; // rsi
  const wchar_t *v16; // rdx
  unsigned __int64 v17; // r14
  const wchar_t *v18; // rcx
  size_t v19; // r8
  int v20; // eax
  LPVOID v21; // rcx
  __int128 *p_Src; // rdx
  LPVOID v23; // rcx
  LPVOID v24; // rcx
  void (*v25)(void); // rax
  LPVOID v26; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-49h] BYREF
  __int64 v29; // [rsp+38h] [rbp-41h] BYREF
  __int64 v30; // [rsp+48h] [rbp-31h]
  __int128 Src; // [rsp+50h] [rbp-29h] BYREF
  __m128i si128; // [rsp+60h] [rbp-19h]
  wchar_t *S1[2]; // [rsp+70h] [rbp-9h] BYREF
  __int128 v34; // [rsp+80h] [rbp+7h]

  Src = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Src) = 0;
  ppv = 0;
  v8 = CoCreateInstance(
         &GUID_c196b2be_ba06_4049_8518_322e1e04282b,
         0,
         1u,
         &GUID_4b965405_f21f_4702_95dd_4e81c3d1bb30,
         &ppv);
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(LPVOID, const wchar_t *))(*(_QWORD *)ppv + 40LL))(ppv, L"./cimv2");
    if ( v8 >= 0 )
    {
      v8 = (*(__int64 (__fastcall **)(LPVOID, _WORD *, _QWORD))(*(_QWORD *)ppv + 176LL))(ppv, a1, 0);
      if ( v8 >= 0 )
      {
        *(_OWORD *)S1 = 0;
        v34 = 0;
        v12 = -1;
        do
          ++v12;
        while ( a1[v12] );
        std::wstring::_Construct<1,unsigned short const *>(S1, a1, v12);
        std::wstring::operator=((char **)&Src, (__int64)S1);
        std::wstring::~wstring((char **)S1);
        std::wstring::append(&Src, L".");
        v13 = *a2;
        while ( v13 != a2[1] )
        {
          std::wstring::wstring((__int64)S1, v13);
          std::wstring::operator+=(&Src);
          std::wstring::append(&Src, L"=");
          std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_lower_bound<std::wstring>(
            (__int64)a3,
            &v29,
            (__int64)S1);
          v14 = v30;
          if ( *(_BYTE *)(v30 + 25) )
            goto LABEL_32;
          v15 = *(_QWORD *)(v30 + 48);
          v16 = (const wchar_t *)(v30 + 32);
          if ( *(_QWORD *)(v30 + 56) > 7u )
            v16 = *(const wchar_t **)v16;
          v17 = v34;
          v18 = (const wchar_t *)S1;
          if ( *((_QWORD *)&v34 + 1) > 7u )
            v18 = S1[0];
          v19 = v34;
          if ( v15 < (unsigned __int64)v34 )
            v19 = *(_QWORD *)(v30 + 48);
          v20 = wmemcmp(v18, v16, v19);
          if ( v20 )
          {
            if ( v20 < 0 )
              goto LABEL_32;
          }
          else if ( v17 < v15 )
          {
            goto LABEL_32;
          }
          if ( v14 == *a3 )
          {
LABEL_32:
            std::wstring::~wstring((char **)S1);
            v21 = ppv;
            if ( ppv )
            {
              ppv = 0;
              (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v21 + 16LL))(v21);
            }
            v8 = -2147024809;
            goto LABEL_47;
          }
          std::wstring::operator+=(&Src);
          v13 += 32;
          if ( a2[1] != v13 )
            std::wstring::append(&Src, L",");
          std::wstring::~wstring((char **)S1);
        }
        p_Src = &Src;
        if ( si128.m128i_i64[1] > 7uLL )
          p_Src = (__int128 *)Src;
        v8 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, _QWORD))(*(_QWORD *)ppv + 176LL))(ppv, p_Src, 0);
        if ( v8 >= 0 )
        {
          v8 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 224LL))(ppv, a4);
          if ( v8 >= 0 )
          {
            v26 = ppv;
            if ( !ppv )
              goto LABEL_47;
            ppv = 0;
            v25 = *(void (**)(void))(*(_QWORD *)v26 + 16LL);
          }
          else
          {
            v24 = ppv;
            if ( !ppv )
              goto LABEL_47;
            ppv = 0;
            v25 = *(void (**)(void))(*(_QWORD *)v24 + 16LL);
          }
          v25();
        }
        else
        {
          v23 = ppv;
          if ( ppv )
          {
            ppv = 0;
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v23 + 16LL))(v23);
          }
        }
      }
      else
      {
        v11 = ppv;
        if ( ppv )
        {
          ppv = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v11 + 16LL))(v11);
        }
      }
    }
    else
    {
      v10 = ppv;
      if ( ppv )
      {
        ppv = 0;
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v10 + 16LL))(v10);
      }
    }
  }
  else
  {
    v9 = ppv;
    if ( ppv )
    {
      ppv = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 16LL))(v9);
    }
  }
LABEL_47:
  std::wstring::~wstring((char **)&Src);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000eae0  mov     [rsp-8+arg_8], rbx
0x18000eae5  push    rbp
0x18000eae6  push    rsi
0x18000eae7  push    rdi
0x18000eae8  push    r12
0x18000eaea  push    r13
0x18000eaec  push    r14
0x18000eaee  push    r15
0x18000eaf0  lea     rbp, [rsp-27h]
0x18000eaf5  sub     rsp, 0A0h
0x18000eafc  mov     rax, cs:__security_cookie
0x18000eb03  xor     rax, rsp
0x18000eb06  mov     [rbp+57h+var_40], rax
0x18000eb0a  mov     r13, r9
0x18000eb0d  mov     r12, r8
0x18000eb10  mov     r15, rdx
0x18000eb13  mov     rdi, rcx
0x18000eb16  xorps   xmm0, xmm0
0x18000eb19  movups  [rbp+57h+Src], xmm0
0x18000eb1d  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18000eb25  movdqu  [rbp+57h+var_70], xmm1
0x18000eb2a  xor     esi, esi
0x18000eb2c  mov     word ptr [rbp+57h+Src], si
0x18000eb30  mov     [rbp+57h+var_A0], rsi
0x18000eb34  lea     rax, [rbp+57h+var_A0]
0x18000eb38  mov     [rsp+0D0h+ppv], rax; ppv
0x18000eb3d  lea     r9, _GUID_4b965405_f21f_4702_95dd_4e81c3d1bb30; riid
0x18000eb44  xor     edx, edx; pUnkOuter
0x18000eb46  lea     r8d, [rsi+1]; dwClsContext
0x18000eb4a  lea     rcx, _GUID_c196b2be_ba06_4049_8518_322e1e04282b; rclsid
0x18000eb51  call    cs:__imp_CoCreateInstance
0x18000eb57  mov     ebx, eax
0x18000eb59  test    eax, eax
0x18000eb5b  jns     short loc_18000EB7C
0x18000eb5d  mov     rcx, [rbp+57h+var_A0]
0x18000eb61  test    rcx, rcx
0x18000eb64  jz      short loc_18000EB77
0x18000eb66  mov     [rbp+57h+var_A0], rsi
0x18000eb6a  mov     rdx, [rcx]
0x18000eb6d  mov     rax, [rdx+10h]
0x18000eb71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb76  nop
0x18000eb77  jmp     loc_18000EDDE
0x18000eb7c  mov     rcx, [rbp+57h+var_A0]
0x18000eb80  mov     rax, [rcx]
0x18000eb83  lea     rdx, aCimv2; "./cimv2"
0x18000eb8a  mov     rax, [rax+28h]
0x18000eb8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb93  mov     ebx, eax
0x18000eb95  test    eax, eax
0x18000eb97  jns     short loc_18000EBB8
0x18000eb99  mov     rcx, [rbp+57h+var_A0]
0x18000eb9d  test    rcx, rcx
0x18000eba0  jz      short loc_18000EBB3
0x18000eba2  mov     [rbp+57h+var_A0], rsi
0x18000eba6  mov     rdx, [rcx]
0x18000eba9  mov     rax, [rdx+10h]
0x18000ebad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebb2  nop
0x18000ebb3  jmp     loc_18000EDDE
0x18000ebb8  mov     rcx, [rbp+57h+var_A0]
0x18000ebbc  mov     rax, [rcx]
0x18000ebbf  xor     r8d, r8d
0x18000ebc2  mov     rdx, rdi
0x18000ebc5  mov     rax, [rax+0B0h]
0x18000ebcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebd1  mov     ebx, eax
0x18000ebd3  test    eax, eax
0x18000ebd5  jns     short loc_18000EBF6
0x18000ebd7  mov     rcx, [rbp+57h+var_A0]
0x18000ebdb  test    rcx, rcx
0x18000ebde  jz      short loc_18000EBF1
0x18000ebe0  mov     [rbp+57h+var_A0], rsi
0x18000ebe4  mov     rdx, [rcx]
0x18000ebe7  mov     rax, [rdx+10h]
0x18000ebeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebf0  nop
0x18000ebf1  jmp     loc_18000EDDE
0x18000ebf6  xorps   xmm0, xmm0
0x18000ebf9  movups  xmmword ptr [rbp+57h+S1], xmm0
0x18000ebfd  xorps   xmm1, xmm1
0x18000ec00  movdqu  [rbp+57h+var_50], xmm1
0x18000ec05  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000ec09  inc     r8
0x18000ec0c  cmp     [rdi+r8*2], si
0x18000ec11  jnz     short loc_18000EC09
0x18000ec13  mov     rdx, rdi
0x18000ec16  lea     rcx, [rbp+57h+S1]
0x18000ec1a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18000ec1f  lea     rdx, [rbp+57h+S1]
0x18000ec23  lea     rcx, [rbp+57h+Src]
0x18000ec27  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18000ec2c  lea     rcx, [rbp+57h+S1]; void *
0x18000ec30  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ec35  lea     rdx, asc_180023428; "."
0x18000ec3c  lea     rcx, [rbp+57h+Src]; Src
0x18000ec40  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18000ec45  mov     rbx, [r15]
0x18000ec48  cmp     rbx, [r15+8]
0x18000ec4c  jz      loc_18000ED4C
0x18000ec52  mov     rdx, rbx
0x18000ec55  lea     rcx, [rbp+57h+S1]
0x18000ec59  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000ec5e  nop
0x18000ec5f  lea     rdx, [rbp+57h+S1]
0x18000ec63  lea     rcx, [rbp+57h+Src]; Src
0x18000ec67  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator+=(std::wstring const &)
0x18000ec6c  lea     rdx, asc_180023424; "="
0x18000ec73  lea     rcx, [rbp+57h+Src]; Src
0x18000ec77  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18000ec7c  lea     r8, [rbp+57h+S1]
0x18000ec80  lea     rdx, [rbp+57h+var_98]
0x18000ec84  mov     rcx, r12
0x18000ec87  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x18000ec8c  mov     rdi, [rbp+57h+var_88]
0x18000ec90  cmp     [rdi+19h], sil
0x18000ec94  jnz     loc_18000ED1E
0x18000ec9a  mov     rsi, [rdi+30h]
0x18000ec9e  lea     rdx, [rdi+20h]
0x18000eca2  cmp     qword ptr [rdi+38h], 7
0x18000eca7  jbe     short loc_18000ECAC
0x18000eca9  mov     rdx, [rdx]; S2
0x18000ecac  mov     r14, qword ptr [rbp+57h+var_50]
0x18000ecb0  lea     rcx, [rbp+57h+S1]
0x18000ecb4  cmp     qword ptr [rbp+57h+var_50+8], 7
0x18000ecb9  cmova   rcx, [rbp+57h+S1]; S1
0x18000ecbe  mov     r8, r14
0x18000ecc1  cmp     rsi, r14
0x18000ecc4  cmovb   r8, rsi; N
0x18000ecc8  call    wmemcmp
0x18000eccd  test    eax, eax
0x18000eccf  jz      short loc_18000ECD9
0x18000ecd1  xor     esi, esi
0x18000ecd3  test    eax, eax
0x18000ecd5  js      short loc_18000ED1E
0x18000ecd7  jmp     short loc_18000ECE0
0x18000ecd9  cmp     r14, rsi
0x18000ecdc  jb      short loc_18000ED1C
0x18000ecde  xor     esi, esi
0x18000ece0  cmp     rdi, [r12]
0x18000ece4  jz      short loc_18000ED1E
0x18000ece6  lea     rdx, [rdi+40h]
0x18000ecea  lea     rcx, [rbp+57h+Src]; Src
0x18000ecee  call    ??Y?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator+=(std::wstring const &)
0x18000ecf3  add     rbx, 20h ; ' '
0x18000ecf7  cmp     [r15+8], rbx
0x18000ecfb  jz      short loc_18000ED0E
0x18000ecfd  lea     rdx, asc_180023460; ","
0x18000ed04  lea     rcx, [rbp+57h+Src]; Src
0x18000ed08  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18000ed0d  nop
0x18000ed0e  lea     rcx, [rbp+57h+S1]; void *
0x18000ed12  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ed17  jmp     loc_18000EC48
0x18000ed1c  xor     esi, esi
0x18000ed1e  lea     rcx, [rbp+57h+S1]; void *
0x18000ed22  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ed27  nop
0x18000ed28  mov     rcx, [rbp+57h+var_A0]
0x18000ed2c  test    rcx, rcx
0x18000ed2f  jz      short loc_18000ED42
0x18000ed31  mov     [rbp+57h+var_A0], rsi
0x18000ed35  mov     rax, [rcx]
0x18000ed38  mov     rax, [rax+10h]
0x18000ed3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed41  nop
0x18000ed42  mov     ebx, 80070057h
0x18000ed47  jmp     loc_18000EDDE
0x18000ed4c  mov     rcx, [rbp+57h+var_A0]
0x18000ed50  mov     rax, [rcx]
0x18000ed53  lea     rdx, [rbp+57h+Src]
0x18000ed57  cmp     qword ptr [rbp+57h+var_70+8], 7
0x18000ed5c  cmova   rdx, qword ptr [rbp+57h+Src]
0x18000ed61  xor     r8d, r8d
0x18000ed64  mov     rax, [rax+0B0h]
0x18000ed6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed70  mov     ebx, eax
0x18000ed72  test    eax, eax
0x18000ed74  jns     short loc_18000ED92
0x18000ed76  mov     rcx, [rbp+57h+var_A0]
0x18000ed7a  test    rcx, rcx
0x18000ed7d  jz      short loc_18000ED90
0x18000ed7f  mov     [rbp+57h+var_A0], rsi
0x18000ed83  mov     rdx, [rcx]
0x18000ed86  mov     rax, [rdx+10h]
0x18000ed8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed8f  nop
0x18000ed90  jmp     short loc_18000EDDE
0x18000ed92  mov     rcx, [rbp+57h+var_A0]
0x18000ed96  mov     rax, [rcx]
0x18000ed99  mov     rdx, r13
0x18000ed9c  mov     rax, [rax+0E0h]
0x18000eda3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eda8  mov     ebx, eax
0x18000edaa  test    eax, eax
0x18000edac  jns     short loc_18000EDC4
0x18000edae  mov     rcx, [rbp+57h+var_A0]
0x18000edb2  test    rcx, rcx
0x18000edb5  jz      short loc_18000EDDE
0x18000edb7  mov     [rbp+57h+var_A0], rsi
0x18000edbb  mov     rdx, [rcx]
0x18000edbe  mov     rax, [rdx+10h]
0x18000edc2  jmp     short loc_18000EDD8
0x18000edc4  mov     rcx, [rbp+57h+var_A0]
0x18000edc8  test    rcx, rcx
0x18000edcb  jz      short loc_18000EDDE
0x18000edcd  mov     [rbp+57h+var_A0], rsi
0x18000edd1  mov     rax, [rcx]
0x18000edd4  mov     rax, [rax+10h]
0x18000edd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eddd  nop
0x18000edde  lea     rcx, [rbp+57h+Src]; void *
0x18000ede2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ede7  mov     eax, ebx
0x18000ede9  mov     rcx, [rbp+57h+var_40]
0x18000eded  xor     rcx, rsp; StackCookie
0x18000edf0  call    __security_check_cookie
0x18000edf5  mov     rbx, [rsp+0D0h+arg_8]
0x18000edfd  add     rsp, 0A0h
0x18000ee04  pop     r15
0x18000ee06  pop     r14
0x18000ee08  pop     r13
0x18000ee0a  pop     r12
0x18000ee0c  pop     rdi
0x18000ee0d  pop     rsi
0x18000ee0e  pop     rbp
0x18000ee0f  retn
```
