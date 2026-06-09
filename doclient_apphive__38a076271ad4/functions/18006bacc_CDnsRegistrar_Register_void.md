# CDnsRegistrar::_Register(void)

- ea: `0x18006bacc`
- end: `0x18006c17e`
- name: `?_Register@CDnsRegistrar@@AEAAXXZ`
- size: `1714`
- prototype: `void __fastcall(CDnsRegistrar *__hidden this)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006b874`
- `0x18006c280`

## callees

- `0x18000ef98`
- `0x18001dffc`
- `0x18001ec40`
- `0x18001ee94`
- `0x18001fd44`
- `0x18006bacc`
- `0x18006c418`
- `0x18006c49c`
- `0x18006c698`
- `0x1800a1f08`
- `0x1800a979c`
- `0x1800f82f0`
- `0x1800f8320`
- `0x180108ed0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c001`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c001`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006c014`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18006c014`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18006c0ed`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18006c0ed`
- `DNSAPI!DnsServiceFreeInstance` at `0x18006c00c`
- `DNSAPI!DnsServiceFreeInstance` at `0x18006c00c`
- `DNSAPI!DnsServiceRegister` at `0x18006c0a1`
- `DNSAPI!DnsServiceRegister` at `0x18006c0a1`
- `DNSAPI!DnsServiceConstructInstance` at `0x18006bfef`
- `DNSAPI!DnsServiceConstructInstance` at `0x18006bfef`

## string_xrefs

- `0x18006c0bf`: `DnsServiceRegister failed`
- `0x18006c0f5`: `DnsServiceConstructInstance failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall CDnsRegistrar::_Register(CDnsRegistrar *this)
{
  int v2; // r14d
  _QWORD *v3; // rax
  unsigned int v4; // r12d
  unsigned __int64 v5; // rbx
  unsigned __int64 v6; // rcx
  char *v7; // rax
  size_t v8; // rbx
  __int64 *v9; // rbx
  _QWORD *v10; // rdi
  _QWORD *v11; // rdx
  int v12; // r14d
  __int64 inserted; // r14
  __int64 v14; // rdi
  const wchar_t *v15; // rcx
  const wchar_t *v16; // rdx
  size_t v17; // r15
  size_t v18; // r12
  size_t v19; // r8
  int v20; // eax
  char v21; // cl
  __int64 *v22; // rax
  size_t v23; // rdi
  const wchar_t *v24; // rdx
  const wchar_t *v25; // rcx
  size_t v26; // r15
  size_t v27; // r8
  int v28; // eax
  _QWORD *v29; // rdi
  _OWORD *v30; // rax
  __int64 **v31; // rcx
  __int64 *i; // rax
  __int64 *j; // rcx
  __int64 *v34; // rax
  _QWORD *v35; // rdx
  _QWORD *v36; // rdx
  __int64 **v37; // rdx
  __int64 *k; // rcx
  __int64 *m; // rdx
  void *v40; // rdi
  __int64 v41; // r14
  __int16 v42; // r15
  _QWORD *v43; // rdx
  __int128 *v44; // rbx
  _QWORD *v45; // rdx
  wchar_t **v46; // rcx
  __int64 v47; // r14
  __int64 v48; // rdi
  DWORD LastError; // ebx
  int v50; // edi
  int v51; // eax
  unsigned int v52; // r9d
  const char *v53; // r9
  int v54; // [rsp+50h] [rbp-E8h]
  wchar_t *S2[2]; // [rsp+58h] [rbp-E0h] BYREF
  size_t N[3]; // [rsp+68h] [rbp-D0h]
  __int128 v57; // [rsp+80h] [rbp-B8h] BYREF
  unsigned __int64 v58; // [rsp+98h] [rbp-A0h]
  _QWORD **v59; // [rsp+A0h] [rbp-98h]
  __int64 v60; // [rsp+A8h] [rbp-90h]
  _BYTE v61[32]; // [rsp+B0h] [rbp-88h] BYREF
  _QWORD *v62; // [rsp+D0h] [rbp-68h] BYREF
  __int64 v63; // [rsp+D8h] [rbp-60h]
  void *v64[2]; // [rsp+E0h] [rbp-58h] BYREF
  __int64 v65; // [rsp+F0h] [rbp-48h]
  __int128 v66; // [rsp+F8h] [rbp-40h] BYREF
  __int64 v67; // [rsp+108h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+0h]

  v2 = 0;
  v62 = 0;
  v63 = 0;
  try
  {
    v3 = operator new(0x60u);
    *v3 = v3;
    v3[1] = v3;
    v3[2] = v3;
    *((_WORD *)v3 + 12) = 257;
    v62 = v3;
    v66 = 0;
    v67 = 0;
    *(_OWORD *)v64 = 0;
    v65 = 0;
    v4 = 0;
    if ( !*((_QWORD *)this + 12) )
      goto LABEL_74;
    std::vector<wchar_t const *>::_Resize_reallocate<std::_Value_init_tag>(&v66);
    v5 = *((_QWORD *)this + 12);
    v6 = ((char *)v64[1] - (char *)v64[0]) >> 3;
    if ( v5 >= v6 )
    {
      if ( v5 <= v6 )
        goto LABEL_10;
      if ( v5 > (signed __int64)(v65 - (unsigned __int64)v64[0]) >> 3 )
      {
        std::vector<wchar_t const *>::_Resize_reallocate<std::_Value_init_tag>(v64);
        goto LABEL_10;
      }
      v8 = 8 * (v5 - v6);
      memset(v64[1], 0, v8);
      v7 = (char *)v64[1] + v8;
    }
    else
    {
      v7 = (char *)v64[0] + 8 * v5;
    }
    v64[1] = v7;
LABEL_10:
    v9 = (__int64 *)**((_QWORD **)this + 11);
    while ( !*((_BYTE *)v9 + 25) )
    {
      v10 = v9 + 4;
      v11 = v9 + 8;
      if ( (unsigned __int64)v9[11] > 0xF )
        v11 = (_QWORD *)*v11;
      UTF8toWstr(v61, v11, v9[10]);
      v12 = v2 | 4;
      if ( (unsigned __int64)v9[7] > 0xF )
        v10 = (_QWORD *)*v10;
      UTF8toWstr(S2, v10, v9[6]);
      v54 = v12 | 8;
      inserted = (__int64)v62;
      v14 = v62[1];
      v57 = (unsigned __int64)v14;
      while ( !*(_BYTE *)(v14 + 25) )
      {
        *(_QWORD *)&v57 = v14;
        v15 = (const wchar_t *)(v14 + 32);
        v16 = (const wchar_t *)S2;
        if ( N[1] > 7 )
          v16 = S2[0];
        v17 = *(_QWORD *)(v14 + 48);
        if ( *(_QWORD *)(v14 + 56) > 7u )
          v15 = *(const wchar_t **)v15;
        v18 = N[0];
        v19 = *(_QWORD *)(v14 + 48);
        if ( N[0] < v17 )
          v19 = N[0];
        v20 = wmemcmp(v15, v16, v19);
        if ( v20 )
        {
          if ( v20 < 0 )
            goto LABEL_27;
        }
        else
        {
          if ( v17 < v18 )
          {
LABEL_27:
            DWORD2(v57) = 0;
            v21 = -1;
            goto LABEL_32;
          }
          if ( v17 <= v18 )
          {
            v21 = 0;
            goto LABEL_31;
          }
        }
        v21 = 1;
LABEL_31:
        DWORD2(v57) = 1;
        inserted = v14;
LABEL_32:
        v22 = (__int64 *)(v14 + 16);
        if ( v21 >= 0 )
          v22 = (__int64 *)v14;
        v14 = *v22;
      }
      if ( *(_BYTE *)(inserted + 25) )
        goto LABEL_47;
      v23 = *(_QWORD *)(inserted + 48);
      v24 = (const wchar_t *)(inserted + 32);
      if ( *(_QWORD *)(inserted + 56) > 7u )
        v24 = *(const wchar_t **)v24;
      v25 = (const wchar_t *)S2;
      if ( N[1] > 7 )
        v25 = S2[0];
      v26 = N[0];
      v27 = N[0];
      if ( v23 < N[0] )
        v27 = *(_QWORD *)(inserted + 48);
      v28 = wmemcmp(v25, v24, v27);
      if ( v28 )
      {
        if ( v28 < 0 )
        {
LABEL_47:
          if ( v63 == 0x2AAAAAAAAAAAAAALL )
            std::_Throw_tree_length_error();
          v29 = v62;
          v59 = &v62;
          v60 = 0;
          v30 = operator new(0x60u);
          v30[2] = *(_OWORD *)S2;
          v30[3] = *(_OWORD *)N;
          LOWORD(S2[0]) = 0;
          N[0] = 0;
          N[1] = 7;
          v30[4] = 0;
          *((_QWORD *)v30 + 10) = 0;
          *((_QWORD *)v30 + 11) = 7;
          *((_WORD *)v30 + 32) = 0;
          *(_QWORD *)v30 = v29;
          *((_QWORD *)v30 + 1) = v29;
          *((_QWORD *)v30 + 2) = v29;
          *((_WORD *)v30 + 12) = 0;
          v60 = 0;
          inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<CSwarmConn>>>>::_Insert_node(
                       &v62,
                       &v57,
                       v30);
        }
      }
      else if ( v26 < v23 )
      {
        goto LABEL_47;
      }
      std::wstring::operator=(inserted + 64, v61);
      std::wstring::~wstring(S2);
      std::wstring::~wstring(v61);
      v31 = (__int64 **)v9[2];
      if ( *((_BYTE *)v31 + 25) )
      {
        for ( i = (__int64 *)v9[1]; !*((_BYTE *)i + 25) && v9 == (__int64 *)i[2]; i = (__int64 *)i[1] )
          v9 = i;
        v9 = i;
      }
      else
      {
        v9 = (__int64 *)v9[2];
        for ( j = *v31; !*((_BYTE *)j + 25); j = (__int64 *)*j )
          v9 = j;
      }
      v2 = v54;
    }
    v34 = (__int64 *)*v62;
    v4 = 0;
    while ( !*((_BYTE *)v34 + 25) )
    {
      v35 = v34 + 4;
      if ( (unsigned __int64)v34[7] > 7 )
        v35 = (_QWORD *)*v35;
      *(_QWORD *)(v66 + 8LL * v4) = v35;
      v36 = v34 + 8;
      if ( (unsigned __int64)v34[11] > 7 )
        v36 = (_QWORD *)*v36;
      *((_QWORD *)v64[0] + v4++) = v36;
      v37 = (__int64 **)v34[2];
      if ( *((_BYTE *)v37 + 25) )
      {
        for ( k = (__int64 *)v34[1]; !*((_BYTE *)k + 25) && v34 == (__int64 *)k[2]; k = (__int64 *)k[1] )
          v34 = k;
        v34 = k;
      }
      else
      {
        v34 = (__int64 *)v34[2];
        for ( m = *v37; !*((_BYTE *)m + 25); m = (__int64 *)*m )
          v34 = m;
      }
    }
LABEL_74:
    v40 = v64[0];
    v41 = v66;
    v42 = *((_WORD *)this + 88);
    v43 = (_QWORD *)((char *)this + 56);
    if ( *((_QWORD *)this + 10) > 0xFu )
      v43 = (_QWORD *)*v43;
    UTF8toWstr(&v57, v43, *((_QWORD *)this + 9));
    v44 = &v57;
    if ( v58 > 7 )
      v44 = (__int128 *)v57;
    v45 = (_QWORD *)((char *)this + 24);
    if ( *((_QWORD *)this + 6) > 0xFu )
      v45 = (_QWORD *)*v45;
    UTF8toWstr(S2, v45, *((_QWORD *)this + 5));
    v46 = S2;
    if ( N[1] > 7 )
      v46 = (wchar_t **)S2[0];
    v47 = DnsServiceConstructInstance(v46, v44, 0, 0, v42, 0, 0, v4, v41, v40);
    v48 = *((_QWORD *)this + 13);
    if ( v48 )
    {
      LastError = GetLastError();
      DnsServiceFreeInstance(v48);
      SetLastError(LastError);
    }
    *((_QWORD *)this + 13) = v47;
    std::wstring::~wstring(S2);
    std::wstring::~wstring(&v57);
    if ( *((_QWORD *)this + 13) )
    {
      _InterlockedExchange((volatile __int32 *)this + 4, 0);
      *((_OWORD *)this + 7) = 0;
      *((_OWORD *)this + 8) = 0;
      *((_OWORD *)this + 9) = 0;
      *((_DWORD *)this + 28) = 1;
      *((_DWORD *)this + 29) = 0;
      *((_QWORD *)this + 15) = *((_QWORD *)this + 13);
      *((_QWORD *)this + 16) = CDnsRegistrar::s_OnComplete;
      *((_QWORD *)this + 17) = this;
      *((_DWORD *)this + 38) = *((unsigned __int8 *)this + 179);
      v50 = *((_DWORD *)this + 40);
      *((_DWORD *)this + 40) = 1;
      v51 = DnsServiceRegister((char *)this + 112, 0);
      if ( v51 != 9506 )
      {
        v52 = (unsigned __int16)v51 | 0x80070000;
        if ( v51 <= 0 )
          v52 = v51;
        LogResult(2u, "CDnsRegistrar::_Register", 0xD7u, v52, "DnsServiceRegister failed");
        *((_DWORD *)this + 40) = v50;
        *((_DWORD *)this + 4) = 1;
        WakeByAddressAll((char *)this + 16);
      }
    }
    else
    {
      LogResult(2u, "CDnsRegistrar::_Register", 0xE0u, -2147024882, "DnsServiceConstructInstance failed");
    }
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,std::shared_ptr<CConfigValue>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,std::shared_ptr<CConfigValue>>>>>>>(v64);
    std::_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,std::shared_ptr<CConfigValue>>>>>>>::~_Hash_vec<std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<unsigned int const,std::shared_ptr<CConfigValue>>>>>>>(&v66);
    std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>(&v62);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0xE3,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\core\\DnsRegistrar.cpp",
      v53);
  }
}

```

## disassembly

```asm
0x18006bacc  mov     r11, rsp
0x18006bacf  mov     [r11+10h], rbx
0x18006bad3  mov     [r11+18h], rsi
0x18006bad7  mov     [r11+20h], rdi
0x18006badb  push    r12
0x18006badd  push    r14
0x18006badf  push    r15
0x18006bae1  sub     rsp, 120h
0x18006bae8  mov     rax, cs:__security_cookie
0x18006baef  xor     rax, rsp
0x18006baf2  mov     [rsp+138h+var_28], rax
0x18006bafa  mov     rsi, rcx
0x18006bafd  xor     r15d, r15d
0x18006bb00  mov     r14d, r15d
0x18006bb03  mov     [rsp+138h+var_E8], r15d
0x18006bb08  xorps   xmm0, xmm0
0x18006bb0b  movups  xmmword ptr [r11-68h], xmm0
0x18006bb10  mov     [r11-68h], r15
0x18006bb14  mov     [r11-60h], r15
0x18006bb18  lea     ecx, [r15+60h]; Size
0x18006bb1c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006bb21  mov     [rax], rax
0x18006bb24  mov     [rax+8], rax
0x18006bb28  mov     [rax+10h], rax
0x18006bb2c  mov     word ptr [rax+18h], 101h
0x18006bb32  mov     [rsp+138h+var_68], rax
0x18006bb3a  xorps   xmm1, xmm1
0x18006bb3d  movdqu  [rsp+138h+var_40], xmm1
0x18006bb46  mov     [rsp+138h+var_30], r15
0x18006bb4e  movdqu  xmmword ptr [rsp+138h+var_58], xmm1
0x18006bb57  mov     [rsp+138h+var_48], r15
0x18006bb5f  mov     r12d, r15d
0x18006bb62  mov     [rsp+138h+var_E4], r15d
0x18006bb67  mov     rdx, [rsi+60h]
0x18006bb6b  test    rdx, rdx
0x18006bb6e  jz      loc_18006BF43
0x18006bb74  lea     rcx, [rsp+138h+var_40]
0x18006bb7c  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<wchar_t const *>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18006bb81  mov     rbx, [rsi+60h]
0x18006bb85  mov     rdi, [rsp+138h+var_58+8]
0x18006bb8d  mov     rcx, rdi
0x18006bb90  mov     rax, [rsp+138h+var_58]
0x18006bb98  sub     rcx, rax
0x18006bb9b  sar     rcx, 3
0x18006bb9f  cmp     rbx, rcx
0x18006bba2  jnb     short loc_18006BBAA
0x18006bba4  lea     rax, [rax+rbx*8]
0x18006bba8  jmp     short loc_18006BBEF
0x18006bbaa  jbe     short loc_18006BBF7
0x18006bbac  mov     rax, [rsp+138h+var_48]
0x18006bbb4  sub     rax, [rsp+138h+var_58]
0x18006bbbc  sar     rax, 3
0x18006bbc0  cmp     rbx, rax
0x18006bbc3  jbe     short loc_18006BBD7
0x18006bbc5  mov     rdx, rbx
0x18006bbc8  lea     rcx, [rsp+138h+var_58]
0x18006bbd0  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@PEB_WV?$allocator@PEB_W@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<wchar_t const *>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18006bbd5  jmp     short loc_18006BBF7
0x18006bbd7  sub     rbx, rcx
0x18006bbda  shl     rbx, 3
0x18006bbde  mov     r8, rbx; Size
0x18006bbe1  xor     edx, edx; Val
0x18006bbe3  mov     rcx, rdi; void *
0x18006bbe6  call    memset
0x18006bbeb  lea     rax, [rdi+rbx]
0x18006bbef  mov     [rsp+138h+var_58+8], rax
0x18006bbf7  mov     rbx, [rsi+58h]
0x18006bbfb  mov     rbx, [rbx]
0x18006bbfe  cmp     [rbx+19h], r15b
0x18006bc02  jnz     loc_18006BEA7
0x18006bc08  lea     rdi, [rbx+20h]
0x18006bc0c  lea     rdx, [rbx+40h]
0x18006bc10  cmp     qword ptr [rbx+58h], 0Fh
0x18006bc15  jbe     short loc_18006BC1A
0x18006bc17  mov     rdx, [rdx]
0x18006bc1a  mov     r8, [rbx+50h]
0x18006bc1e  lea     rcx, [rsp+138h+var_88]
0x18006bc26  call    ?UTF8toWstr@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBD_K@Z; UTF8toWstr(char const *,unsigned __int64)
0x18006bc2b  or      r14d, 4
0x18006bc2f  mov     r8, [rdi+10h]
0x18006bc33  cmp     qword ptr [rdi+18h], 0Fh
0x18006bc38  jbe     short loc_18006BC3D
0x18006bc3a  mov     rdi, [rdi]
0x18006bc3d  mov     rdx, rdi
0x18006bc40  lea     rcx, [rsp+138h+S2]
0x18006bc45  call    ?UTF8toWstr@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBD_K@Z; UTF8toWstr(char const *,unsigned __int64)
0x18006bc4a  or      r14d, 8
0x18006bc4e  mov     [rsp+138h+var_E8], r14d
0x18006bc53  mov     r14, [rsp+138h+var_68]
0x18006bc5b  mov     rdi, [r14+8]
0x18006bc5f  mov     qword ptr [rsp+138h+var_B8], rdi
0x18006bc67  mov     qword ptr [rsp+138h+var_B8+8], 0
0x18006bc73  jmp     loc_18006BD02
0x18006bc78  mov     qword ptr [rsp+138h+var_B8], rdi
0x18006bc80  lea     rcx, [rdi+20h]
0x18006bc84  lea     rdx, [rsp+138h+S2]
0x18006bc89  cmp     [rsp+138h+N+8], 7
0x18006bc8f  cmova   rdx, [rsp+138h+S2]; S2
0x18006bc95  mov     r15, [rdi+30h]
0x18006bc99  cmp     qword ptr [rcx+18h], 7
0x18006bc9e  jbe     short loc_18006BCA3
0x18006bca0  mov     rcx, [rcx]; S1
0x18006bca3  mov     r12, [rsp+138h+N]
0x18006bca8  mov     r8, r15
0x18006bcab  cmp     r12, r15
0x18006bcae  cmovb   r8, r12; N
0x18006bcb2  call    wmemcmp
0x18006bcb7  test    eax, eax
0x18006bcb9  jz      short loc_18006BCC4
0x18006bcbb  xor     r15d, r15d
0x18006bcbe  test    eax, eax
0x18006bcc0  jns     short loc_18006BCDD
0x18006bcc2  jmp     short loc_18006BCCC
0x18006bcc4  cmp     r15, r12
0x18006bcc7  jnb     short loc_18006BCD8
0x18006bcc9  xor     r15d, r15d
0x18006bccc  mov     dword ptr [rsp+138h+var_B8+8], r15d
0x18006bcd4  mov     cl, 0FFh
0x18006bcd6  jmp     short loc_18006BCF5
0x18006bcd8  jbe     short loc_18006BCE1
0x18006bcda  xor     r15d, r15d
0x18006bcdd  mov     cl, 1
0x18006bcdf  jmp     short loc_18006BCE7
0x18006bce1  xor     r15d, r15d
0x18006bce4  mov     cl, r15b
0x18006bce7  mov     dword ptr [rsp+138h+var_B8+8], 1
0x18006bcf2  mov     r14, rdi
0x18006bcf5  lea     rax, [rdi+10h]
0x18006bcf9  test    cl, cl
0x18006bcfb  cmovns  rax, rdi
0x18006bcff  mov     rdi, [rax]
0x18006bd02  cmp     [rdi+19h], r15b
0x18006bd06  jz      loc_18006BC78
0x18006bd0c  cmp     [r14+19h], r15b
0x18006bd10  jnz     short loc_18006BD6A
0x18006bd12  mov     rdi, [r14+30h]
0x18006bd16  lea     rdx, [r14+20h]
0x18006bd1a  cmp     qword ptr [r14+38h], 7
0x18006bd1f  jbe     short loc_18006BD24
0x18006bd21  mov     rdx, [rdx]; S2
0x18006bd24  lea     rcx, [rsp+138h+S2]
0x18006bd29  cmp     [rsp+138h+N+8], 7
0x18006bd2f  cmova   rcx, [rsp+138h+S2]; S1
0x18006bd35  mov     r15, [rsp+138h+N]
0x18006bd3a  mov     r8, r15
0x18006bd3d  cmp     rdi, r15
0x18006bd40  cmovb   r8, rdi; N
0x18006bd44  call    wmemcmp
0x18006bd49  test    eax, eax
0x18006bd4b  jz      short loc_18006BD5A
0x18006bd4d  xor     r15d, r15d
0x18006bd50  test    eax, eax
0x18006bd52  jns     loc_18006BE30
0x18006bd58  jmp     short loc_18006BD6A
0x18006bd5a  cmp     r15, rdi
0x18006bd5d  jb      short loc_18006BD67
0x18006bd5f  xor     r15d, r15d
0x18006bd62  jmp     loc_18006BE30
0x18006bd67  xor     r15d, r15d
0x18006bd6a  mov     rax, 2AAAAAAAAAAAAAAh
0x18006bd74  cmp     [rsp+138h+var_60], rax
0x18006bd7c  jz      loc_18006C177
0x18006bd82  mov     rdi, [rsp+138h+var_68]
0x18006bd8a  lea     rax, [rsp+138h+var_68]
0x18006bd92  mov     [rsp+138h+var_98], rax
0x18006bd9a  mov     [rsp+138h+var_90], r15
0x18006bda2  mov     ecx, 60h ; '`'; Size
0x18006bda7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006bdac  nop
0x18006bdad  movups  xmm0, xmmword ptr [rsp+138h+S2]
0x18006bdb2  movups  xmmword ptr [rax+20h], xmm0
0x18006bdb6  movups  xmm1, xmmword ptr [rsp+138h+N]
0x18006bdbb  movups  xmmword ptr [rax+30h], xmm1
0x18006bdbf  mov     word ptr [rsp+138h+S2], r15w
0x18006bdc5  mov     [rsp+138h+N], r15
0x18006bdca  mov     [rsp+138h+N+8], 7
0x18006bdd3  xorps   xmm0, xmm0
0x18006bdd6  movups  xmmword ptr [rax+40h], xmm0
0x18006bdda  mov     [rax+50h], r15
0x18006bdde  mov     qword ptr [rax+58h], 7
0x18006bde6  mov     [rax+40h], r15w
0x18006bdeb  mov     [rax], rdi
0x18006bdee  mov     [rax+8], rdi
0x18006bdf2  mov     [rax+10h], rdi
0x18006bdf6  mov     word ptr [rax+18h], 0
0x18006bdfc  mov     [rsp+138h+var_90], r15
0x18006be04  movups  xmm0, [rsp+138h+var_B8]
0x18006be0c  movdqu  [rsp+138h+var_B8], xmm0
0x18006be15  mov     r8, rax
0x18006be18  lea     rdx, [rsp+138h+var_B8]
0x18006be20  lea     rcx, [rsp+138h+var_68]
0x18006be28  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@VCSwarmConn@@@2@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@VCSwarmConn@@@2@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@VCSwarmConn@@@2@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<CSwarmConn>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::string const,std::shared_ptr<CSwarmConn>>,void *> *>,std::_Tree_node<std::pair<std::string const,std::shared_ptr<CSwarmConn>>,void *> * const)
0x18006be2d  mov     r14, rax
0x18006be30  lea     rcx, [r14+40h]
0x18006be34  lea     rdx, [rsp+138h+var_88]
0x18006be3c  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18006be41  nop
0x18006be42  lea     rcx, [rsp+138h+S2]
0x18006be47  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006be4c  nop
0x18006be4d  lea     rcx, [rsp+138h+var_88]
0x18006be55  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18006be5a  mov     rcx, [rbx+10h]
0x18006be5e  cmp     [rcx+19h], r15b
0x18006be62  jz      short loc_18006BE8A
0x18006be64  mov     rax, [rbx+8]
0x18006be68  jmp     short loc_18006BE77
0x18006be6a  cmp     rbx, [rax+10h]
0x18006be6e  jnz     short loc_18006BE7D
0x18006be70  mov     rbx, rax
0x18006be73  mov     rax, [rax+8]
0x18006be77  cmp     [rax+19h], r15b
0x18006be7b  jz      short loc_18006BE6A
0x18006be7d  mov     rbx, rax
0x18006be80  mov     r14d, [rsp+138h+var_E8]
0x18006be85  jmp     loc_18006BBFE
0x18006be8a  mov     rbx, rcx
0x18006be8d  mov     rcx, [rcx]
0x18006be90  cmp     [rcx+19h], r15b
0x18006be94  jnz     short loc_18006BE80
0x18006be96  mov     rbx, rcx
0x18006be99  mov     rax, [rcx]
0x18006be9c  mov     rcx, rax
0x18006be9f  cmp     [rax+19h], r15b
0x18006bea3  jz      short loc_18006BE96
0x18006bea5  jmp     short loc_18006BE80
0x18006bea7  mov     rax, [rsp+138h+var_68]
0x18006beaf  mov     rax, [rax]
0x18006beb2  mov     r12d, [rsp+138h+var_E4]
0x18006beb7  cmp     [rax+19h], r15b
0x18006bebb  jnz     loc_18006BF43
0x18006bec1  lea     rdx, [rax+20h]
0x18006bec5  cmp     qword ptr [rax+38h], 7
0x18006beca  jbe     short loc_18006BECF
0x18006becc  mov     rdx, [rdx]
0x18006becf  mov     r8d, r12d
0x18006bed2  mov     rcx, qword ptr [rsp+138h+var_40]
0x18006beda  mov     [rcx+r8*8], rdx
0x18006bede  lea     rdx, [rax+40h]
0x18006bee2  cmp     qword ptr [rax+58h], 7
0x18006bee7  jbe     short loc_18006BEEC
0x18006bee9  mov     rdx, [rdx]
0x18006beec  mov     rcx, [rsp+138h+var_58]
0x18006bef4  mov     [rcx+r8*8], rdx
0x18006bef8  inc     r12d
0x18006befb  mov     rdx, [rax+10h]
0x18006beff  cmp     [rdx+19h], r15b
0x18006bf03  jz      short loc_18006BF23
0x18006bf05  mov     rcx, [rax+8]
0x18006bf09  jmp     short loc_18006BF18
0x18006bf0b  cmp     rax, [rcx+10h]
0x18006bf0f  jnz     short loc_18006BF1E
0x18006bf11  mov     rax, rcx
0x18006bf14  mov     rcx, [rcx+8]
0x18006bf18  cmp     [rcx+19h], r15b
0x18006bf1c  jz      short loc_18006BF0B
0x18006bf1e  mov     rax, rcx
0x18006bf21  jmp     short loc_18006BEB7
0x18006bf23  mov     rax, rdx
0x18006bf26  mov     rdx, [rdx]
0x18006bf29  cmp     [rdx+19h], r15b
0x18006bf2d  jnz     short loc_18006BEB7
0x18006bf2f  mov     rax, rdx
0x18006bf32  mov     rcx, [rdx]
0x18006bf35  mov     rdx, rcx
0x18006bf38  cmp     [rcx+19h], r15b
0x18006bf3c  jz      short loc_18006BF2F
0x18006bf3e  jmp     loc_18006BEB7
0x18006bf43  mov     rdi, [rsp+138h+var_58]
0x18006bf4b  mov     r14, qword ptr [rsp+138h+var_40]
0x18006bf53  movzx   r15d, word ptr [rsi+0B0h]
0x18006bf5b  lea     rdx, [rsi+38h]
0x18006bf5f  mov     r8, [rdx+10h]
0x18006bf63  cmp     qword ptr [rdx+18h], 0Fh
0x18006bf68  jbe     short loc_18006BF6D
0x18006bf6a  mov     rdx, [rdx]
0x18006bf6d  lea     rcx, [rsp+138h+var_B8]
0x18006bf75  call    ?UTF8toWstr@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBD_K@Z; UTF8toWstr(char const *,unsigned __int64)
0x18006bf7a  nop
0x18006bf7b  lea     rbx, [rsp+138h+var_B8]
0x18006bf83  cmp     [rsp+138h+var_A0], 7
0x18006bf8c  cmova   rbx, qword ptr [rsp+138h+var_B8]
0x18006bf95  lea     rdx, [rsi+18h]
0x18006bf99  mov     r8, [rdx+10h]
0x18006bf9d  cmp     qword ptr [rdx+18h], 0Fh
0x18006bfa2  jbe     short loc_18006BFA7
0x18006bfa4  mov     rdx, [rdx]
0x18006bfa7  lea     rcx, [rsp+138h+S2]
0x18006bfac  call    ?UTF8toWstr@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEBD_K@Z; UTF8toWstr(char const *,unsigned __int64)
0x18006bfb1  lea     rcx, [rsp+138h+S2]
0x18006bfb6  cmp     [rsp+138h+N+8], 7
0x18006bfbc  cmova   rcx, [rsp+138h+S2]
0x18006bfc2  mov     [rsp+138h+var_F0], rdi
0x18006bfc7  mov     [rsp+138h+var_F8], r14
0x18006bfcc  mov     [rsp+138h+var_100], r12d
0x18006bfd1  xor     r12d, r12d
0x18006bfd4  mov     [rsp+138h+var_108], r12w
0x18006bfda  mov     [rsp+138h+var_110], r12w
0x18006bfe0  mov     word ptr [rsp+138h+var_118], r15w
0x18006bfe6  xor     r9d, r9d
  ... truncated ...
```
