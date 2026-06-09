# Microsoft::HostGuardian::Client::CertificateCache::AddCertificateInternal(std::vector<uchar,std::allocator<uchar>>,AttestationResultType,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>,ShsAttestationFlag,_FILETIME)

- ea: `0x18000f1ac`
- end: `0x18000f541`
- name: `?AddCertificateInternal@CertificateCache@Client@HostGuardian@Microsoft@@AEAAXV?$vector@EV?$allocator@E@std@@@std@@W4AttestationResultType@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@6@W4ShsAttestationFlag@@U_FILETIME@@@Z`
- size: `917`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *, char **, int, __int64, int, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18000efe0`

## callees

- `0x180001770`
- `0x180001794`
- `0x180003e30`
- `0x180004274`
- `0x18000977c`
- `0x18000b8b0`
- `0x18000c45c`
- `0x18000c740`
- `0x18000e9fc`
- `0x18000f1ac`
- `0x180010628`
- `0x180010858`
- `0x180010d20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f1f9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f1f9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f4f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f4f5`

## pseudocode

```c
__int64 __fastcall Microsoft::HostGuardian::Client::CertificateCache::AddCertificateInternal(
        RTL_SRWLOCK *a1,
        char **a2,
        int a3,
        __int64 a4,
        int a5,
        __int64 a6)
{
  RTL_SRWLOCK *v10; // rbx
  RTL_SRWLOCK *v11; // r15
  __int64 v12; // r13
  int v13; // esi
  __int64 inserted; // rcx
  __int64 v15; // rax
  _DWORD *v16; // rdi
  _QWORD *v17; // rax
  _QWORD *v18; // rax
  __int64 *v19; // r15
  __int64 v20; // rbx
  const wchar_t *v21; // rdx
  unsigned __int64 v22; // rsi
  unsigned __int64 v23; // rdi
  char *v24; // rcx
  size_t v25; // r8
  int v26; // eax
  __int64 v27; // rsi
  _QWORD *v28; // rdi
  RTL_SRWLOCK *v29; // r13
  RTL_SRWLOCK *v30; // rdi
  __int64 v31; // rsi
  __int64 v32; // r15
  int v33; // ebx
  __int64 v34; // rcx
  __int64 v35; // rax
  char *v36; // rax
  __int128 v38; // [rsp+20h] [rbp-89h] BYREF
  RTL_SRWLOCK *v39; // [rsp+30h] [rbp-79h]
  __int128 v40; // [rsp+40h] [rbp-69h] BYREF
  __int64 v41; // [rsp+50h] [rbp-59h]
  _QWORD *Ptr; // [rsp+60h] [rbp-49h]
  __int64 v43; // [rsp+68h] [rbp-41h]
  char **v44; // [rsp+70h] [rbp-39h]
  __int64 v45; // [rsp+78h] [rbp-31h]
  char *v46[3]; // [rsp+80h] [rbp-29h] BYREF
  int v47; // [rsp+98h] [rbp-11h]
  char **v48; // [rsp+A0h] [rbp-9h]
  RTL_SRWLOCK *v49; // [rsp+A8h] [rbp-1h]
  __int64 v50; // [rsp+B0h] [rbp+7h]

  v44 = a2;
  v39 = a1;
  v48 = a2;
  v50 = a4;
  v10 = a1 + 5;
  AcquireSRWLockExclusive(a1 + 5);
  v49 = v10;
  v45 = a6;
  std::vector<unsigned char>::vector<unsigned char>(v46, (__int64)a2);
  v47 = a5;
  v11 = a1 + 1;
  Ptr = a1[1].Ptr;
  v12 = Ptr[1];
  v13 = 0;
  v43 = 0;
  inserted = (__int64)Ptr;
  v15 = v12;
  while ( !*(_BYTE *)(v15 + 25) )
  {
    v12 = v15;
    if ( *(_DWORD *)(v15 + 32) >= a3 )
    {
      v13 = 1;
      inserted = v15;
      v15 = *(_QWORD *)v15;
    }
    else
    {
      v13 = 0;
      v15 = *(_QWORD *)(v15 + 16);
    }
  }
  if ( *(_BYTE *)(inserted + 25) || a3 < *(_DWORD *)(inserted + 32) )
  {
    if ( v11[1].Ptr == (PVOID)0x492492492492492LL )
      goto LABEL_37;
    *(_QWORD *)&v38 = v11;
    v16 = operator new(0x38u);
    *((_QWORD *)&v38 + 1) = v16;
    v16[8] = a3;
    *((_QWORD *)v16 + 5) = 0;
    *((_QWORD *)v16 + 6) = 0;
    v17 = operator new(0x68u);
    *v17 = v17;
    v17[1] = v17;
    v17[2] = v17;
    *((_WORD *)v17 + 12) = 257;
    *((_QWORD *)v16 + 5) = v17;
    v18 = Ptr;
    *(_QWORD *)v16 = Ptr;
    *((_QWORD *)v16 + 1) = v18;
    *((_QWORD *)v16 + 2) = v18;
    *((_WORD *)v16 + 12) = 0;
    *(_QWORD *)&v40 = v12;
    *((_QWORD *)&v40 + 1) = __PAIR64__(v43, v13);
    inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<enum AttestationResultType const,std::wstring>>>::_Insert_node(
                 v11,
                 &v40,
                 v16);
  }
  v19 = (__int64 *)(inserted + 40);
  std::_Tree<std::_Tmap_traits<std::wstring,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::tuple<enum ShsAttestationFlag,std::vector<unsigned char>,_FILETIME>>>,0>>::_Find_lower_bound<std::wstring>(
    inserted + 40,
    &v40,
    a4);
  v20 = v41;
  if ( !*(_BYTE *)(v41 + 25) )
  {
    v21 = (const wchar_t *)(v41 + 32);
    v22 = *(_QWORD *)(v41 + 48);
    if ( *(_QWORD *)(v41 + 56) > 7u )
      v21 = *(const wchar_t **)v21;
    v23 = *(_QWORD *)(a4 + 16);
    if ( *(_QWORD *)(a4 + 24) <= 7u )
      v24 = (char *)a4;
    else
      v24 = *(char **)a4;
    v25 = *(_QWORD *)(a4 + 16);
    if ( v22 < v23 )
      v25 = *(_QWORD *)(v41 + 48);
    v26 = wmemcmp((const wchar_t *)v24, v21, v25);
    if ( v26 )
    {
      if ( v26 >= 0 )
        goto LABEL_24;
    }
    else if ( v23 >= v22 )
    {
      goto LABEL_24;
    }
  }
  if ( v19[1] == 0x276276276276276LL )
LABEL_37:
    std::_Throw_tree_length_error();
  v27 = *v19;
  v28 = operator new(0x68u);
  std::wstring::wstring((__int64)(v28 + 4), a4);
  v28[8] = 0;
  v28[9] = 0;
  v28[10] = 0;
  v28[11] = 0;
  *((_DWORD *)v28 + 24) = 0;
  *v28 = v27;
  v28[1] = v27;
  v28[2] = v27;
  *((_WORD *)v28 + 12) = 0;
  v38 = v40;
  v20 = std::_Tree_val<std::_Tree_simple_types<std::pair<enum AttestationResultType const,std::wstring>>>::_Insert_node(
          v19,
          &v38,
          v28);
LABEL_24:
  *(_DWORD *)(v20 + 96) = v47;
  std::vector<unsigned char>::operator=(v20 + 72, v46);
  *(_QWORD *)(v20 + 64) = v45;
  std::vector<unsigned char>::~vector<unsigned char>(v46);
  v29 = v39;
  v30 = v39 + 3;
  v31 = (__int64)v39[3].Ptr;
  v32 = *(_QWORD *)(v31 + 8);
  v33 = 0;
  v39 = 0;
  v34 = v31;
  v35 = v32;
  while ( !*(_BYTE *)(v35 + 25) )
  {
    v32 = v35;
    if ( *(_DWORD *)(v35 + 32) >= a3 )
    {
      v33 = 1;
      v34 = v35;
      v35 = *(_QWORD *)v35;
    }
    else
    {
      v33 = 0;
      v35 = *(_QWORD *)(v35 + 16);
    }
  }
  if ( *(_BYTE *)(v34 + 25) || a3 < *(_DWORD *)(v34 + 32) )
  {
    if ( v30[1].Ptr == (PVOID)0x38E38E38E38E38ELL )
      std::_Throw_tree_length_error();
    v38 = (unsigned __int64)v30;
    v36 = (char *)operator new(0x48u);
    *((_DWORD *)v36 + 8) = a3;
    *(_OWORD *)(v36 + 40) = 0;
    *((_QWORD *)v36 + 7) = 0;
    *((_QWORD *)v36 + 8) = 7;
    *((_WORD *)v36 + 20) = 0;
    *(_QWORD *)v36 = v31;
    *((_QWORD *)v36 + 1) = v31;
    *((_QWORD *)v36 + 2) = v31;
    *((_WORD *)v36 + 12) = 0;
    *(_QWORD *)&v40 = v32;
    *((_QWORD *)&v40 + 1) = __PAIR64__((unsigned int)v39, v33);
    v34 = std::_Tree_val<std::_Tree_simple_types<std::pair<enum AttestationResultType const,std::wstring>>>::_Insert_node(
            v30,
            &v40,
            v36);
  }
  std::wstring::operator=(v34 + 40, a4);
  if ( v29 != (RTL_SRWLOCK *)-40LL )
    ReleaseSRWLockExclusive(v29 + 5);
  std::vector<unsigned char>::~vector<unsigned char>(v44);
  return std::wstring::~wstring((char **)a4);
}

```

## disassembly

```asm
0x18000f1ac  mov     [rsp-8+arg_10], rbx
0x18000f1b1  push    rbp
0x18000f1b2  push    rsi
0x18000f1b3  push    rdi
0x18000f1b4  push    r12
0x18000f1b6  push    r13
0x18000f1b8  push    r14
0x18000f1ba  push    r15
0x18000f1bc  lea     rbp, [rsp-17h]
0x18000f1c1  sub     rsp, 0C0h
0x18000f1c8  mov     rax, cs:__security_cookie
0x18000f1cf  xor     rax, rsp
0x18000f1d2  mov     [rbp+47h+var_38], rax
0x18000f1d6  mov     r14, r9
0x18000f1d9  mov     r12d, r8d
0x18000f1dc  mov     rdi, rdx
0x18000f1df  mov     [rbp+47h+var_80], rdx
0x18000f1e3  mov     rsi, rcx
0x18000f1e6  mov     [rbp+47h+var_C0], rcx
0x18000f1ea  mov     [rbp+47h+var_50], rdx
0x18000f1ee  mov     [rbp+47h+var_40], r9
0x18000f1f2  lea     rbx, [rcx+28h]
0x18000f1f6  mov     rcx, rbx; SRWLock
0x18000f1f9  call    cs:__imp_AcquireSRWLockExclusive
0x18000f1ff  mov     [rbp+47h+var_48], rbx
0x18000f203  mov     rax, [rbp+47h+arg_28]
0x18000f207  mov     [rbp+47h+var_78], rax
0x18000f20b  mov     rdx, rdi
0x18000f20e  lea     rcx, [rbp+47h+var_70]
0x18000f212  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x18000f217  mov     eax, [rbp+47h+arg_20]
0x18000f21a  mov     [rbp+47h+var_58], eax
0x18000f21d  lea     r15, [rsi+8]
0x18000f221  mov     rax, [r15]
0x18000f224  mov     [rbp+47h+var_90], rax
0x18000f228  mov     r13, [rax+8]
0x18000f22c  xor     edx, edx
0x18000f22e  mov     esi, edx
0x18000f230  xor     ecx, ecx
0x18000f232  mov     [rbp+47h+var_88], rcx
0x18000f236  mov     rcx, rax
0x18000f239  mov     rax, r13
0x18000f23c  cmp     [r13+19h], dl
0x18000f240  jnz     short loc_18000F263
0x18000f242  mov     r13, rax
0x18000f245  cmp     [rax+20h], r12d
0x18000f249  jge     short loc_18000F253
0x18000f24b  mov     esi, edx
0x18000f24d  mov     rax, [rax+10h]
0x18000f251  jmp     short loc_18000F25E
0x18000f253  mov     esi, 1
0x18000f258  mov     rcx, rax
0x18000f25b  mov     rax, [rax]
0x18000f25e  cmp     [rax+19h], dl
0x18000f261  jz      short loc_18000F242
0x18000f263  cmp     [rcx+19h], dl
0x18000f266  jnz     short loc_18000F272
0x18000f268  cmp     r12d, [rcx+20h]
0x18000f26c  jge     loc_18000F30A
0x18000f272  mov     rax, 492492492492492h
0x18000f27c  cmp     [r15+8], rax
0x18000f280  jz      loc_18000F53B
0x18000f286  mov     qword ptr [rsp+0F0h+var_D0], r15
0x18000f28b  mov     qword ptr [rsp+0F0h+var_D0+8], rdx
0x18000f290  mov     ecx, 38h ; '8'; Size
0x18000f295  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f29a  mov     rdi, rax
0x18000f29d  mov     qword ptr [rsp+0F0h+var_D0+8], rax
0x18000f2a2  mov     [rax+20h], r12d
0x18000f2a6  mov     qword ptr [rax+28h], 0
0x18000f2ae  mov     qword ptr [rax+30h], 0
0x18000f2b6  mov     ecx, 68h ; 'h'; Size
0x18000f2bb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f2c0  mov     [rax], rax
0x18000f2c3  mov     [rax+8], rax
0x18000f2c7  mov     [rax+10h], rax
0x18000f2cb  mov     word ptr [rax+18h], 101h
0x18000f2d1  mov     [rdi+28h], rax
0x18000f2d5  mov     rax, [rbp+47h+var_90]
0x18000f2d9  mov     [rdi], rax
0x18000f2dc  mov     [rdi+8], rax
0x18000f2e0  mov     [rdi+10h], rax
0x18000f2e4  mov     word ptr [rdi+18h], 0
0x18000f2ea  mov     qword ptr [rbp+47h+var_B0], r13
0x18000f2ee  mov     dword ptr [rbp+47h+var_B0+8], esi
0x18000f2f1  mov     rax, [rbp+47h+var_88]
0x18000f2f5  mov     dword ptr [rbp+47h+var_B0+0Ch], eax
0x18000f2f8  mov     r8, rdi
0x18000f2fb  lea     rdx, [rbp+47h+var_B0]
0x18000f2ff  mov     rcx, r15
0x18000f302  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4AttestationResultType@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBW4AttestationResultType@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBW4AttestationResultType@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<AttestationResultType const,std::wstring>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<AttestationResultType const,std::wstring>,void *> *>,std::_Tree_node<std::pair<AttestationResultType const,std::wstring>,void *> * const)
0x18000f307  mov     rcx, rax
0x18000f30a  lea     r15, [rcx+28h]
0x18000f30e  mov     r8, r14
0x18000f311  lea     rdx, [rbp+47h+var_B0]
0x18000f315  mov     rcx, r15
0x18000f318  call    ??$_Find_lower_bound@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$tuple@W4ShsAttestationFlag@@V?$vector@EV?$allocator@E@std@@@std@@U_FILETIME@@@2@@std@@PEAX@std@@@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::tuple<ShsAttestationFlag,std::vector<uchar>,_FILETIME>>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x18000f31d  mov     rbx, [rbp+47h+var_A0]
0x18000f321  xor     r13d, r13d
0x18000f324  cmp     [rbx+19h], r13b
0x18000f328  jnz     short loc_18000F373
0x18000f32a  lea     rdx, [rbx+20h]
0x18000f32e  mov     rsi, [rdx+10h]
0x18000f332  cmp     qword ptr [rdx+18h], 7
0x18000f337  jbe     short loc_18000F33C
0x18000f339  mov     rdx, [rdx]; S2
0x18000f33c  mov     rdi, [r14+10h]
0x18000f340  cmp     qword ptr [r14+18h], 7
0x18000f345  jbe     short loc_18000F34C
0x18000f347  mov     rcx, [r14]
0x18000f34a  jmp     short loc_18000F34F
0x18000f34c  mov     rcx, r14; S1
0x18000f34f  mov     r8, rdi
0x18000f352  cmp     rsi, rdi
0x18000f355  cmovb   r8, rsi; N
0x18000f359  call    wmemcmp
0x18000f35e  test    eax, eax
0x18000f360  jz      short loc_18000F36A
0x18000f362  jns     loc_18000F3F5
0x18000f368  jmp     short loc_18000F373
0x18000f36a  cmp     rdi, rsi
0x18000f36d  jnb     loc_18000F3F5
0x18000f373  mov     rax, 276276276276276h
0x18000f37d  cmp     [r15+8], rax
0x18000f381  jz      loc_18000F53B
0x18000f387  mov     rsi, [r15]
0x18000f38a  mov     qword ptr [rsp+0F0h+var_D0], r15
0x18000f38f  mov     qword ptr [rsp+0F0h+var_D0+8], r13
0x18000f394  mov     ecx, 68h ; 'h'; Size
0x18000f399  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f39e  mov     rdi, rax
0x18000f3a1  mov     qword ptr [rsp+0F0h+var_D0+8], rax
0x18000f3a6  mov     rdx, r14
0x18000f3a9  lea     rcx, [rax+20h]
0x18000f3ad  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18000f3b2  xor     eax, eax
0x18000f3b4  mov     [rdi+40h], rax
0x18000f3b8  mov     [rdi+48h], r13
0x18000f3bc  mov     [rdi+50h], r13
0x18000f3c0  mov     [rdi+58h], r13
0x18000f3c4  mov     [rdi+60h], r13d
0x18000f3c8  mov     [rdi], rsi
0x18000f3cb  mov     [rdi+8], rsi
0x18000f3cf  mov     [rdi+10h], rsi
0x18000f3d3  mov     [rdi+18h], r13w
0x18000f3d8  movups  xmm0, [rbp+47h+var_B0]
0x18000f3dc  movdqu  [rsp+0F0h+var_D0], xmm0
0x18000f3e2  mov     r8, rdi
0x18000f3e5  lea     rdx, [rsp+0F0h+var_D0]
0x18000f3ea  mov     rcx, r15
0x18000f3ed  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4AttestationResultType@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBW4AttestationResultType@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBW4AttestationResultType@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<AttestationResultType const,std::wstring>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<AttestationResultType const,std::wstring>,void *> *>,std::_Tree_node<std::pair<AttestationResultType const,std::wstring>,void *> * const)
0x18000f3f2  mov     rbx, rax
0x18000f3f5  mov     ecx, [rbp+47h+var_58]
0x18000f3f8  mov     [rbx+60h], ecx
0x18000f3fb  lea     rcx, [rbx+48h]
0x18000f3ff  lea     rdx, [rbp+47h+var_70]
0x18000f403  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x18000f408  mov     rcx, [rbp+47h+var_78]
0x18000f40c  mov     [rbx+40h], rcx
0x18000f410  lea     rcx, [rbp+47h+var_70]
0x18000f414  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000f419  mov     r13, [rbp+47h+var_C0]
0x18000f41d  lea     rdi, [r13+18h]
0x18000f421  mov     rsi, [rdi]
0x18000f424  mov     r15, [rsi+8]
0x18000f428  xor     edx, edx
0x18000f42a  mov     ebx, edx
0x18000f42c  xor     eax, eax
0x18000f42e  mov     [rbp+47h+var_C0], rax
0x18000f432  mov     rcx, rsi
0x18000f435  mov     rax, r15
0x18000f438  cmp     [r15+19h], dl
0x18000f43c  jnz     short loc_18000F45F
0x18000f43e  mov     r15, rax
0x18000f441  cmp     [rax+20h], r12d
0x18000f445  jge     short loc_18000F44F
0x18000f447  mov     ebx, edx
0x18000f449  mov     rax, [rax+10h]
0x18000f44d  jmp     short loc_18000F45A
0x18000f44f  mov     ebx, 1
0x18000f454  mov     rcx, rax
0x18000f457  mov     rax, [rax]
0x18000f45a  cmp     [rax+19h], dl
0x18000f45d  jz      short loc_18000F43E
0x18000f45f  cmp     [rcx+19h], dl
0x18000f462  jnz     short loc_18000F46A
0x18000f464  cmp     r12d, [rcx+20h]
0x18000f468  jge     short loc_18000F4DF
0x18000f46a  mov     rax, 38E38E38E38E38Eh
0x18000f474  cmp     [rdi+8], rax
0x18000f478  jz      loc_18000F535
0x18000f47e  mov     qword ptr [rsp+0F0h+var_D0], rdi
0x18000f483  mov     qword ptr [rsp+0F0h+var_D0+8], rdx
0x18000f488  mov     ecx, 48h ; 'H'; Size
0x18000f48d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f492  nop
0x18000f493  mov     [rax+20h], r12d
0x18000f497  xorps   xmm0, xmm0
0x18000f49a  movups  xmmword ptr [rax+28h], xmm0
0x18000f49e  xor     ecx, ecx
0x18000f4a0  mov     [rax+38h], rcx
0x18000f4a4  mov     qword ptr [rax+40h], 7
0x18000f4ac  mov     [rax+28h], cx
0x18000f4b0  mov     [rax], rsi
0x18000f4b3  mov     [rax+8], rsi
0x18000f4b7  mov     [rax+10h], rsi
0x18000f4bb  mov     [rax+18h], cx
0x18000f4bf  mov     qword ptr [rbp+47h+var_B0], r15
0x18000f4c3  mov     dword ptr [rbp+47h+var_B0+8], ebx
0x18000f4c6  mov     rcx, [rbp+47h+var_C0]
0x18000f4ca  mov     dword ptr [rbp+47h+var_B0+0Ch], ecx
0x18000f4cd  mov     r8, rax
0x18000f4d0  lea     rdx, [rbp+47h+var_B0]
0x18000f4d4  mov     rcx, rdi
0x18000f4d7  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4AttestationResultType@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBW4AttestationResultType@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBW4AttestationResultType@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<AttestationResultType const,std::wstring>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<AttestationResultType const,std::wstring>,void *> *>,std::_Tree_node<std::pair<AttestationResultType const,std::wstring>,void *> * const)
0x18000f4dc  mov     rcx, rax
0x18000f4df  add     rcx, 28h ; '('
0x18000f4e3  mov     rdx, r14
0x18000f4e6  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18000f4eb  nop
0x18000f4ec  lea     rcx, [r13+28h]; SRWLock
0x18000f4f0  test    rcx, rcx
0x18000f4f3  jz      short loc_18000F4FC
0x18000f4f5  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f4fb  nop
0x18000f4fc  mov     rcx, [rbp+47h+var_80]
0x18000f500  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18000f505  nop
0x18000f506  mov     rcx, r14
0x18000f509  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000f50e  mov     rcx, [rbp+47h+var_38]
0x18000f512  xor     rcx, rsp; StackCookie
0x18000f515  call    __security_check_cookie
0x18000f51a  mov     rbx, [rsp+0F0h+arg_10]
0x18000f522  add     rsp, 0C0h
0x18000f529  pop     r15
0x18000f52b  pop     r14
0x18000f52d  pop     r13
0x18000f52f  pop     r12
0x18000f531  pop     rdi
0x18000f532  pop     rsi
0x18000f533  pop     rbp
0x18000f534  retn
0x18000f535  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
0x18000f53b  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
