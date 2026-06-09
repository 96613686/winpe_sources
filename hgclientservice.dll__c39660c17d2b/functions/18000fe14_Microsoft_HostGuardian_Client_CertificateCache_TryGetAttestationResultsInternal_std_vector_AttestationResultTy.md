# Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResultsInternal(std::vector<AttestationResultType,std::allocator<AttestationResultType>>,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,std::map<AttestationResultType,std::tuple<ShsAttestationFlag,std::vector<uchar,std::allocator<uchar>>,_FILETIME>,std::less<AttestationResultType>,std::allocator<std::pair<AttestationResultType const,std::tuple<ShsAttestationFlag,std::vector<uchar,std::allocator<uchar>>,_FILETIME>>>> &)

- ea: `0x18000fe14`
- end: `0x1800101be`
- name: `?TryGetAttestationResultsInternal@CertificateCache@Client@HostGuardian@Microsoft@@AEAA_NV?$vector@W4AttestationResultType@@V?$allocator@W4AttestationResultType@@@std@@@std@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@6@AEAV?$map@W4AttestationResultType@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@std@@U?$less@W4AttestationResultType@@@3@V?$allocator@U?$pair@$$CBW4AttestationResultType@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@std@@@std@@@3@@6@@Z`
- size: `938`
- prototype: `char __fastcall(__int64, char **, __int64, __int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x18000f814`

## callees

- `0x180001770`
- `0x180001794`
- `0x180004274`
- `0x18000b8b0`
- `0x18000bedc`
- `0x18000c45c`
- `0x18000c4c8`
- `0x18000c7f0`
- `0x18000e9fc`
- `0x18000eaa4`
- `0x18000ec58`
- `0x18000eef0`
- `0x18000fe14`
- `0x180010628`
- `0x180010858`
- `0x180010d20`

## import_xrefs

- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000ffe1`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18001015d`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18000ffe1`
- `msvcp_win!?_Xout_of_range@std@@YAXPEBD@Z` at `0x18001015d`

## pseudocode

```c
char __fastcall Microsoft::HostGuardian::Client::CertificateCache::TryGetAttestationResultsInternal(
        __int64 a1,
        char **a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v6; // rdi
  _QWORD *v7; // rax
  int v8; // r13d
  char *v9; // rsi
  __int64 *v10; // rdx
  __int64 *v11; // rax
  void *v12; // r14
  const wchar_t *v13; // rdx
  unsigned __int64 v14; // r15
  unsigned __int64 v15; // rdi
  char *v16; // rcx
  size_t v17; // r8
  int v18; // eax
  __int64 v20; // rdi
  const wchar_t *v21; // rdx
  unsigned __int64 v22; // r15
  unsigned __int64 v23; // r14
  char *v24; // rcx
  size_t v25; // r8
  int v26; // eax
  int v27; // eax
  _QWORD *v28; // r15
  __int64 *v29; // r13
  int v30; // r14d
  _QWORD *inserted; // rdi
  __int64 *v32; // rcx
  _DWORD *v33; // rax
  char v34; // [rsp+20h] [rbp-A9h]
  int v35; // [rsp+24h] [rbp-A5h]
  _QWORD *v36; // [rsp+28h] [rbp-A1h] BYREF
  __int64 v37; // [rsp+30h] [rbp-99h]
  void *v38[2]; // [rsp+38h] [rbp-91h] BYREF
  __int64 v39; // [rsp+48h] [rbp-81h]
  char *v40; // [rsp+50h] [rbp-79h]
  __int64 v41; // [rsp+58h] [rbp-71h]
  __int64 v42; // [rsp+60h] [rbp-69h]
  __int64 *v43; // [rsp+70h] [rbp-59h] BYREF
  int v44; // [rsp+78h] [rbp-51h]
  int v45; // [rsp+7Ch] [rbp-4Dh]
  _BYTE v46[12]; // [rsp+80h] [rbp-49h] BYREF
  int v47; // [rsp+8Ch] [rbp-3Dh]
  __int64 v48; // [rsp+90h] [rbp-39h]
  __int64 v49; // [rsp+98h] [rbp-31h]
  char *v50[3]; // [rsp+A0h] [rbp-29h] BYREF
  int v51; // [rsp+B8h] [rbp-11h]
  _QWORD **v52; // [rsp+C0h] [rbp-9h]
  __int64 v53; // [rsp+C8h] [rbp-1h]
  char **v54; // [rsp+D0h] [rbp+7h]
  __int64 v55; // [rsp+D8h] [rbp+Fh]

  v42 = a4;
  v6 = a1;
  v41 = a1;
  v54 = a2;
  v55 = a3;
  v37 = 0;
  v7 = operator new(0x50u);
  *v7 = v7;
  v7[1] = v7;
  v7[2] = v7;
  *((_WORD *)v7 + 12) = 257;
  v36 = v7;
  v8 = 0;
  v35 = 0;
  v34 = 0;
  v9 = *a2;
  v40 = a2[1];
  if ( v9 == v40 )
  {
LABEL_50:
    std::map<enum AttestationResultType,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>::operator=(
      v42,
      &v36);
    std::_Tree<std::_Tmap_traits<enum AttestationResultType,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>,std::less<enum AttestationResultType>,std::allocator<std::pair<enum AttestationResultType const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<enum AttestationResultType,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>,std::less<enum AttestationResultType>,std::allocator<std::pair<enum AttestationResultType const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,0>>((void **)&v36);
    std::vector<enum AttestationResultType>::~vector<enum AttestationResultType>(a2);
    std::wstring::~wstring((char **)a3);
    return 1;
  }
  else
  {
    while ( 1 )
    {
      v10 = *(__int64 **)(v6 + 8);
      v11 = (__int64 *)v10[1];
      v47 = 0;
      while ( !*((_BYTE *)v11 + 25) )
      {
        if ( *((_DWORD *)v11 + 8) >= *(_DWORD *)v9 )
        {
          v10 = v11;
          v11 = (__int64 *)*v11;
        }
        else
        {
          v11 = (__int64 *)v11[2];
        }
      }
      if ( *((_BYTE *)v10 + 25) || *(_DWORD *)v9 < *((_DWORD *)v10 + 8) )
      {
        std::_Xout_of_range("invalid map<K, T> key");
        __debugbreak();
      }
      std::map<std::wstring,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>::map<std::wstring,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>(
        v38,
        v10 + 5);
      std::_Tree<std::_Tmap_traits<std::wstring,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,0>>::_Find_lower_bound<std::wstring>(
        v38,
        v46,
        a3);
      v12 = (void *)v48;
      if ( *(_BYTE *)(v48 + 25) )
        break;
      v13 = (const wchar_t *)(v48 + 32);
      v14 = *(_QWORD *)(v48 + 48);
      if ( *(_QWORD *)(v48 + 56) > 7u )
        v13 = *(const wchar_t **)v13;
      v15 = *(_QWORD *)(a3 + 16);
      if ( *(_QWORD *)(a3 + 24) <= 7u )
        v16 = (char *)a3;
      else
        v16 = *(char **)a3;
      v17 = *(_QWORD *)(a3 + 16);
      if ( v14 < v15 )
        v17 = *(_QWORD *)(v48 + 48);
      v18 = wmemcmp((const wchar_t *)v16, v13, v17);
      if ( v18 )
      {
        if ( v18 < 0 )
          break;
      }
      else if ( v15 < v14 )
      {
        break;
      }
      if ( v12 == v38[0] )
        break;
      std::_Tree<std::_Tmap_traits<std::wstring,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,0>>::_Find_lower_bound<std::wstring>(
        v38,
        v46,
        a3);
      v20 = v48;
      if ( *(_BYTE *)(v48 + 25) )
        goto LABEL_32;
      v21 = (const wchar_t *)(v48 + 32);
      v22 = *(_QWORD *)(v48 + 48);
      if ( *(_QWORD *)(v48 + 56) > 7u )
        v21 = *(const wchar_t **)v21;
      v23 = *(_QWORD *)(a3 + 16);
      if ( *(_QWORD *)(a3 + 24) <= 7u )
        v24 = (char *)a3;
      else
        v24 = *(char **)a3;
      v25 = *(_QWORD *)(a3 + 16);
      if ( v22 < v23 )
        v25 = *(_QWORD *)(v48 + 48);
      v26 = wmemcmp((const wchar_t *)v24, v21, v25);
      if ( v26 )
      {
        if ( v26 < 0 )
          goto LABEL_32;
      }
      else if ( v23 < v22 )
      {
LABEL_32:
        std::_Xout_of_range("invalid map<K, T> key");
        __debugbreak();
      }
      v49 = *(_QWORD *)(v20 + 64);
      std::vector<unsigned char>::vector<unsigned char>(v50, v20 + 72);
      v27 = *(_DWORD *)(v20 + 96);
      v51 = v27;
      if ( v34 )
      {
        if ( v8 != v27 )
        {
          std::vector<unsigned char>::~vector<unsigned char>(v50);
          break;
        }
      }
      else
      {
        v35 = v27;
        v34 = 1;
      }
      v28 = v36;
      v29 = (__int64 *)v36[1];
      v30 = 0;
      v39 = 0;
      inserted = v36;
      v32 = v29;
      while ( !*((_BYTE *)v32 + 25) )
      {
        v29 = v32;
        if ( *((_DWORD *)v32 + 8) >= *(_DWORD *)v9 )
        {
          v30 = 1;
          inserted = v32;
          v32 = (__int64 *)*v32;
        }
        else
        {
          v30 = 0;
          v32 = (__int64 *)v32[2];
        }
      }
      if ( *((_BYTE *)inserted + 25) || *(_DWORD *)v9 < *((_DWORD *)inserted + 8) )
      {
        if ( v37 == 0x333333333333333LL )
          std::_Throw_tree_length_error();
        v52 = &v36;
        v53 = 0;
        v33 = operator new(0x50u);
        v33[8] = *(_DWORD *)v9;
        *((_QWORD *)v33 + 5) = 0;
        *((_QWORD *)v33 + 6) = 0;
        *((_QWORD *)v33 + 7) = 0;
        *((_QWORD *)v33 + 8) = 0;
        v33[18] = 0;
        *(_QWORD *)v33 = v28;
        *((_QWORD *)v33 + 1) = v28;
        *((_QWORD *)v33 + 2) = v28;
        *((_WORD *)v33 + 12) = 0;
        v53 = 0;
        v43 = v29;
        v44 = v30;
        v45 = v39;
        inserted = (_QWORD *)std::_Tree_val<std::_Tree_simple_types<std::pair<enum AttestationResultType const,std::wstring>>>::_Insert_node(
                               &v36,
                               &v43,
                               v33);
        v27 = v51;
      }
      *((_DWORD *)inserted + 18) = v27;
      std::vector<unsigned char>::operator=(inserted + 6, v50);
      inserted[5] = v49;
      std::vector<unsigned char>::~vector<unsigned char>(v50);
      std::_Tree<std::_Tmap_traits<std::wstring,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,0>>(v38);
      v9 += 4;
      if ( v9 == v40 )
        goto LABEL_50;
      v8 = v35;
      v6 = v41;
    }
    std::_Tree<std::_Tmap_traits<std::wstring,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,0>>(v38);
    std::_Tree<std::_Tmap_traits<enum AttestationResultType,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>,std::less<enum AttestationResultType>,std::allocator<std::pair<enum AttestationResultType const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<enum AttestationResultType,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>,std::less<enum AttestationResultType>,std::allocator<std::pair<enum AttestationResultType const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,0>>((void **)&v36);
    std::vector<enum AttestationResultType>::~vector<enum AttestationResultType>(a2);
    std::wstring::~wstring((char **)a3);
    return 0;
  }
}

```

## disassembly

```asm
0x18000fe14  mov     [rsp-8+arg_0], rbx
0x18000fe19  push    rbp
0x18000fe1a  push    rsi
0x18000fe1b  push    rdi
0x18000fe1c  push    r12
0x18000fe1e  push    r13
0x18000fe20  push    r14
0x18000fe22  push    r15
0x18000fe24  lea     rbp, [rsp-27h]
0x18000fe29  sub     rsp, 0F0h
0x18000fe30  mov     rax, cs:__security_cookie
0x18000fe37  xor     rax, rsp
0x18000fe3a  mov     [rbp+57h+var_40], rax
0x18000fe3e  mov     [rbp+57h+var_C0], r9
0x18000fe42  mov     rbx, r8
0x18000fe45  mov     r12, rdx
0x18000fe48  mov     rdi, rcx
0x18000fe4b  mov     [rbp+57h+var_C8], rcx
0x18000fe4f  mov     [rbp+57h+var_50], rdx
0x18000fe53  mov     [rbp+57h+var_48], rbx
0x18000fe57  xor     r15d, r15d
0x18000fe5a  mov     [rsp+120h+var_F8], r15
0x18000fe5f  mov     [rsp+120h+var_F0], r15
0x18000fe64  lea     ecx, [r15+50h]; Size
0x18000fe68  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000fe6d  mov     [rax], rax
0x18000fe70  mov     [rax+8], rax
0x18000fe74  mov     [rax+10h], rax
0x18000fe78  mov     word ptr [rax+18h], 101h
0x18000fe7e  mov     [rsp+120h+var_F8], rax
0x18000fe83  mov     r13d, r15d
0x18000fe86  mov     [rsp+120h+var_FC], r15d
0x18000fe8b  mov     [rsp+120h+var_100], r15b
0x18000fe90  mov     rsi, [r12]
0x18000fe94  mov     rax, [r12+8]
0x18000fe99  mov     [rbp+57h+var_D0], rax
0x18000fe9d  cmp     rsi, rax
0x18000fea0  jz      loc_180010164
0x18000fea6  mov     rdx, [rdi+8]
0x18000feaa  mov     rax, [rdx+8]
0x18000feae  xor     ecx, ecx
0x18000feb0  mov     [rbp+57h+var_94], ecx
0x18000feb3  cmp     [rax+19h], r15b
0x18000feb7  jnz     short loc_18000FED2
0x18000feb9  mov     ecx, [rsi]
0x18000febb  cmp     [rax+20h], ecx
0x18000febe  jge     short loc_18000FEC6
0x18000fec0  mov     rax, [rax+10h]
0x18000fec4  jmp     short loc_18000FECC
0x18000fec6  mov     rdx, rax
0x18000fec9  mov     rax, [rax]
0x18000fecc  cmp     [rax+19h], r15b
0x18000fed0  jz      short loc_18000FEBB
0x18000fed2  cmp     [rdx+19h], r15b
0x18000fed6  jnz     loc_180010156
0x18000fedc  mov     eax, [rdx+20h]
0x18000fedf  cmp     [rsi], eax
0x18000fee1  jl      loc_180010156
0x18000fee7  add     rdx, 28h ; '('
0x18000feeb  lea     rcx, [rsp+120h+var_E8]
0x18000fef0  call    ??0?$map@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@@std@@@2@@std@@QEAA@AEBV01@@Z; std::map<std::wstring,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>::map<std::wstring,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>(std::map<std::wstring,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>> const &)
0x18000fef5  nop
0x18000fef6  mov     r8, rbx
0x18000fef9  lea     rdx, [rbp+57h+var_A0]
0x18000fefd  lea     rcx, [rsp+120h+var_E8]
0x18000ff02  call    ??$_Find_lower_bound@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x18000ff07  mov     r14, [rbp+57h+var_90]
0x18000ff0b  cmp     [r14+19h], r15b
0x18000ff0f  jnz     short loc_18000FF4B
0x18000ff11  lea     rdx, [r14+20h]
0x18000ff15  mov     r15, [rdx+10h]
0x18000ff19  cmp     qword ptr [rdx+18h], 7
0x18000ff1e  jbe     short loc_18000FF23
0x18000ff20  mov     rdx, [rdx]; S2
0x18000ff23  mov     rdi, [rbx+10h]
0x18000ff27  cmp     qword ptr [rbx+18h], 7
0x18000ff2c  jbe     short loc_18000FF33
0x18000ff2e  mov     rcx, [rbx]
0x18000ff31  jmp     short loc_18000FF36
0x18000ff33  mov     rcx, rbx; S1
0x18000ff36  mov     r8, rdi
0x18000ff39  cmp     r15, rdi
0x18000ff3c  cmovb   r8, r15; N
0x18000ff40  call    wmemcmp
0x18000ff45  test    eax, eax
0x18000ff47  jz      short loc_18000FF79
0x18000ff49  jns     short loc_18000FF7E
0x18000ff4b  lea     rcx, [rsp+120h+var_E8]
0x18000ff50  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>>,0>>(void)
0x18000ff55  nop
0x18000ff56  lea     rcx, [rsp+120h+var_F8]
0x18000ff5b  call    ??1?$_Tree@V?$_Tmap_traits@W4AttestationResultType@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@std@@U?$less@W4AttestationResultType@@@3@V?$allocator@U?$pair@$$CBW4AttestationResultType@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<AttestationResultType,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>,std::less<AttestationResultType>,std::allocator<std::pair<AttestationResultType const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<AttestationResultType,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>,std::less<AttestationResultType>,std::allocator<std::pair<AttestationResultType const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>>,0>>(void)
0x18000ff60  nop
0x18000ff61  mov     rcx, r12
0x18000ff64  call    ??1?$vector@W4AttestationResultType@@V?$allocator@W4AttestationResultType@@@std@@@std@@QEAA@XZ; std::vector<AttestationResultType>::~vector<AttestationResultType>(void)
0x18000ff69  nop
0x18000ff6a  mov     rcx, rbx
0x18000ff6d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000ff72  xor     al, al
0x18000ff74  jmp     loc_180010191
0x18000ff79  cmp     rdi, r15
0x18000ff7c  jb      short loc_18000FF4B
0x18000ff7e  cmp     r14, [rsp+120h+var_E8]
0x18000ff83  jz      short loc_18000FF4B
0x18000ff85  mov     r8, rbx
0x18000ff88  lea     rdx, [rbp+57h+var_A0]
0x18000ff8c  lea     rcx, [rsp+120h+var_E8]
0x18000ff91  call    ??$_Find_lower_bound@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x18000ff96  mov     rdi, [rbp+57h+var_90]
0x18000ff9a  cmp     byte ptr [rdi+19h], 0
0x18000ff9e  jnz     short loc_18000FFDA
0x18000ffa0  lea     rdx, [rdi+20h]
0x18000ffa4  mov     r15, [rdx+10h]
0x18000ffa8  cmp     qword ptr [rdx+18h], 7
0x18000ffad  jbe     short loc_18000FFB2
0x18000ffaf  mov     rdx, [rdx]; S2
0x18000ffb2  mov     r14, [rbx+10h]
0x18000ffb6  cmp     qword ptr [rbx+18h], 7
0x18000ffbb  jbe     short loc_18000FFC2
0x18000ffbd  mov     rcx, [rbx]
0x18000ffc0  jmp     short loc_18000FFC5
0x18000ffc2  mov     rcx, rbx; S1
0x18000ffc5  mov     r8, r14
0x18000ffc8  cmp     r15, r14
0x18000ffcb  cmovb   r8, r15; N
0x18000ffcf  call    wmemcmp
0x18000ffd4  test    eax, eax
0x18000ffd6  jz      short loc_18000FFE8
0x18000ffd8  jns     short loc_18000FFED
0x18000ffda  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x18000ffe1  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x18000ffe7  int     3; Trap to Debugger
0x18000ffe8  cmp     r14, r15
0x18000ffeb  jb      short loc_18000FFDA
0x18000ffed  mov     rax, [rdi+40h]
0x18000fff1  mov     [rbp+57h+var_88], rax
0x18000fff5  lea     rdx, [rdi+48h]
0x18000fff9  lea     rcx, [rbp+57h+var_80]
0x18000fffd  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x180010002  mov     eax, [rdi+60h]
0x180010005  mov     [rbp+57h+var_68], eax
0x180010008  xor     r8d, r8d
0x18001000b  cmp     [rsp+120h+var_100], r8b
0x180010010  jnz     short loc_18001001D
0x180010012  mov     [rsp+120h+var_FC], eax
0x180010016  mov     [rsp+120h+var_100], 1
0x18001001b  jmp     short loc_180010026
0x18001001d  cmp     r13d, eax
0x180010020  jnz     loc_180010148
0x180010026  mov     r15, [rsp+120h+var_F8]
0x18001002b  mov     r13, [r15+8]
0x18001002f  mov     r14d, r8d
0x180010032  xor     ecx, ecx
0x180010034  mov     [rsp+120h+var_D8], rcx
0x180010039  mov     rdi, r15
0x18001003c  mov     rcx, r13
0x18001003f  cmp     [r13+19h], r8b
0x180010043  jnz     short loc_18001006A
0x180010045  mov     edx, [rsi]
0x180010047  mov     r13, rcx
0x18001004a  cmp     [rcx+20h], edx
0x18001004d  jge     short loc_180010058
0x18001004f  mov     r14d, r8d
0x180010052  mov     rcx, [rcx+10h]
0x180010056  jmp     short loc_180010064
0x180010058  mov     r14d, 1
0x18001005e  mov     rdi, rcx
0x180010061  mov     rcx, [rcx]
0x180010064  cmp     [rcx+19h], r8b
0x180010068  jz      short loc_180010047
0x18001006a  cmp     [rdi+19h], r8b
0x18001006e  jnz     short loc_18001007F
0x180010070  mov     ecx, [rdi+20h]
0x180010073  cmp     [rsi], ecx
0x180010075  jl      short loc_18001007F
0x180010077  xor     r15d, r15d
0x18001007a  jmp     loc_180010104
0x18001007f  mov     rax, 333333333333333h
0x180010089  cmp     [rsp+120h+var_F0], rax
0x18001008e  jz      loc_1800101B8
0x180010094  lea     rax, [rsp+120h+var_F8]
0x180010099  mov     [rbp+57h+var_60], rax
0x18001009d  mov     [rbp+57h+var_58], r8
0x1800100a1  mov     ecx, 50h ; 'P'; Size
0x1800100a6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800100ab  nop
0x1800100ac  mov     ecx, [rsi]
0x1800100ae  mov     [rax+20h], ecx
0x1800100b1  xor     ecx, ecx
0x1800100b3  mov     [rax+28h], rcx
0x1800100b7  mov     [rax+30h], rcx
0x1800100bb  mov     [rax+38h], rcx
0x1800100bf  mov     [rax+40h], rcx
0x1800100c3  mov     [rax+48h], ecx
0x1800100c6  mov     [rax], r15
0x1800100c9  mov     [rax+8], r15
0x1800100cd  mov     [rax+10h], r15
0x1800100d1  xor     r15d, r15d
0x1800100d4  mov     [rax+18h], r15w
0x1800100d9  mov     [rbp+57h+var_58], r15
0x1800100dd  mov     [rbp+57h+var_B0], r13
0x1800100e1  mov     [rbp+57h+var_A8], r14d
0x1800100e5  mov     rcx, [rsp+120h+var_D8]
0x1800100ea  mov     [rbp+57h+var_A4], ecx
0x1800100ed  mov     r8, rax
0x1800100f0  lea     rdx, [rbp+57h+var_B0]
0x1800100f4  lea     rcx, [rsp+120h+var_F8]
0x1800100f9  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4AttestationResultType@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBW4AttestationResultType@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBW4AttestationResultType@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<AttestationResultType const,std::wstring>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<AttestationResultType const,std::wstring>,void *> *>,std::_Tree_node<std::pair<AttestationResultType const,std::wstring>,void *> * const)
0x1800100fe  mov     rdi, rax
0x180010101  mov     eax, [rbp+57h+var_68]
0x180010104  mov     [rdi+48h], eax
0x180010107  lea     rcx, [rdi+30h]
0x18001010b  lea     rdx, [rbp+57h+var_80]
0x18001010f  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> const &)
0x180010114  mov     rcx, [rbp+57h+var_88]
0x180010118  mov     [rdi+28h], rcx
0x18001011c  lea     rcx, [rbp+57h+var_80]
0x180010120  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180010125  nop
0x180010126  lea     rcx, [rsp+120h+var_E8]
0x18001012b  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>>,0>>(void)
0x180010130  add     rsi, 4
0x180010134  cmp     rsi, [rbp+57h+var_D0]
0x180010138  jz      short loc_180010164
0x18001013a  mov     r13d, [rsp+120h+var_FC]
0x18001013f  mov     rdi, [rbp+57h+var_C8]
0x180010143  jmp     loc_18000FEA6
0x180010148  lea     rcx, [rbp+57h+var_80]
0x18001014c  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x180010151  jmp     loc_18000FF4B
0x180010156  lea     rcx, aInvalidMapKTKe; "invalid map<K, T> key"
0x18001015d  call    cs:__imp_?_Xout_of_range@std@@YAXPEBD@Z; std::_Xout_of_range(char const *)
0x180010163  int     3; Trap to Debugger
0x180010164  lea     rdx, [rsp+120h+var_F8]
0x180010169  mov     rcx, [rbp+57h+var_C0]
0x18001016d  call    ??4?$map@W4AttestationResultType@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@std@@U?$less@W4AttestationResultType@@@3@V?$allocator@U?$pair@$$CBW4AttestationResultType@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@std@@@std@@@3@@std@@QEAAAEAV01@AEBV01@@Z; std::map<AttestationResultType,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>::operator=(std::map<AttestationResultType,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>> const &)
0x180010172  nop
0x180010173  lea     rcx, [rsp+120h+var_F8]
0x180010178  call    ??1?$_Tree@V?$_Tmap_traits@W4AttestationResultType@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@std@@U?$less@W4AttestationResultType@@@3@V?$allocator@U?$pair@$$CBW4AttestationResultType@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@std@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<AttestationResultType,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>,std::less<AttestationResultType>,std::allocator<std::pair<AttestationResultType const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>>,0>>::~_Tree<std::_Tmap_traits<AttestationResultType,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>,std::less<AttestationResultType>,std::allocator<std::pair<AttestationResultType const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>>,0>>(void)
0x18001017d  nop
0x18001017e  mov     rcx, r12
0x180010181  call    ??1?$vector@W4AttestationResultType@@V?$allocator@W4AttestationResultType@@@std@@@std@@QEAA@XZ; std::vector<AttestationResultType>::~vector<AttestationResultType>(void)
0x180010186  nop
0x180010187  mov     rcx, rbx
0x18001018a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001018f  mov     al, 1
0x180010191  mov     rcx, [rbp+57h+var_40]
0x180010195  xor     rcx, rsp; StackCookie
0x180010198  call    __security_check_cookie
0x18001019d  mov     rbx, [rsp+120h+arg_0]
0x1800101a5  add     rsp, 0F0h
0x1800101ac  pop     r15
0x1800101ae  pop     r14
0x1800101b0  pop     r13
0x1800101b2  pop     r12
0x1800101b4  pop     rdi
0x1800101b5  pop     rsi
0x1800101b6  pop     rbp
0x1800101b7  retn
0x1800101b8  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
