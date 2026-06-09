# JitvLifetimeManager::AllowServicing(ushort const * *,ulong,ushort const * *,ulong,int,int,ushort * * *,ulong *,SERVICING_TERMINATION_INFO * *,ulong *)

- ea: `0x18007d540`
- end: `0x18007d82e`
- name: `?AllowServicing@JitvLifetimeManager@@UEAAJPEAPEBGK0KHHPEAPEAPEAGPEAKPEAPEAUSERVICING_TERMINATION_INFO@@2@Z`
- size: `750`
- prototype: `__int64 __fastcall(JitvLifetimeManager *__hidden this, const unsigned __int16 **, unsigned int, const unsigned __int16 **, unsigned int, int, int, unsigned __int16 ***, unsigned int *, struct SERVICING_TERMINATION_INFO **, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180006158`
- `0x18001031c`
- `0x180010a84`
- `0x1800341b4`
- `0x180034460`
- `0x18007d540`
- `0x18007dbfc`
- `0x18007e034`
- `0x18007e430`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007d5ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007d722`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007d5ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007d722`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18007d642`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18007d789`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18007d642`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18007d789`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall JitvLifetimeManager::AllowServicing(
        JitvLifetimeManager *this,
        const unsigned __int16 **a2,
        unsigned int a3,
        const unsigned __int16 **a4,
        unsigned int a5,
        int a6,
        int a7,
        unsigned __int16 ***a8,
        unsigned int *a9,
        struct SERVICING_TERMINATION_INFO **a10,
        unsigned int *a11)
{
  int v13; // r13d
  __int64 v14; // rcx
  __int128 v15; // kr10_16
  const char *v16; // r9
  __int64 result; // rax
  __int64 v18; // rcx
  unsigned __int16 **v19; // rax
  const char *v20; // r9
  __int64 i; // rdi
  LPWSTR *v22; // rdx
  const WCHAR *v23; // rcx
  HRESULT v24; // eax
  const unsigned __int16 **v25; // rdi
  _DWORD *v26; // rcx
  DesktopAppXProvider *v27; // rcx
  unsigned int j; // edi
  unsigned int k; // edi
  struct SERVICING_TERMINATION_INFO *v30; // rcx
  const char *v31; // r9
  struct SERVICING_TERMINATION_INFO **v32; // rsi
  unsigned int m; // edi
  __int64 v34; // rsi
  HRESULT v35; // eax
  __int128 v36; // [rsp+20h] [rbp-68h] BYREF
  __int64 v37; // [rsp+30h] [rbp-58h]
  unsigned __int16 ***v38; // [rsp+38h] [rbp-50h]
  unsigned int *v39; // [rsp+40h] [rbp-48h]
  char v40; // [rsp+48h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v13 = 0;
  *a8 = 0;
  *a9 = 0;
  *a10 = 0;
  *a11 = 0;
  v36 = 0;
  v37 = 0;
  try
  {
    JitvLifetimeManager::GetActiveJitvApps((__int64)a11, (__int64)a2, a3, (__int64)&v36);
    JitvLifetimeManager::GetActiveJitvApps(v14, (__int64)a4, a5, (__int64)&v36);
    v15 = v36;
    if ( (_QWORD)v36 == *((_QWORD *)&v36 + 1) )
    {
LABEL_3:
      std::vector<WriteVirtualization::RegistryExclusion>::_Tidy(&v36);
      return 0;
    }
    v18 = (unsigned int)((__int64)(*((_QWORD *)&v36 + 1) - v36) >> 5);
    *a9 = v18;
    v19 = (unsigned __int16 **)CoTaskMemAlloc(8 * v18);
    *a8 = v19;
    if ( !v19 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0xB0,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\jitvlifetimemanager.cpp",
        v20);
    memset_0(v19, 0, 8LL * *a9);
    for ( i = v15; i != *((_QWORD *)&v15 + 1); i += 32 )
    {
      v22 = &(*a8)[v13++];
      v23 = (const WCHAR *)i;
      if ( *(_QWORD *)(i + 24) > 7u )
        v23 = *(const WCHAR **)i;
      v24 = SHStrDupW(v23, v22);
      if ( v24 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB5,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\jitvlifetimemanager.cpp",
          (const char *)(unsigned int)v24,
          v36);
    }
    if ( a6 || (_QWORD)v15 == *((_QWORD *)&v15 + 1) )
    {
      v38 = a8;
      v39 = a9;
      v40 = 1;
      for ( j = 0; j < a3; ++j )
        JitvLifetimeManager::ShutdownPackage((JitvLifetimeManager *)((char *)this - 136), a2[j]);
      for ( k = 0; k < a5; ++k )
        JitvLifetimeManager::ShutdownPackage((JitvLifetimeManager *)((char *)this - 136), a4[k]);
      v30 = (struct SERVICING_TERMINATION_INFO *)CoTaskMemAlloc(24LL * *a9);
      v32 = a10;
      *a10 = v30;
      if ( !v30 )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0xD1,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\jitvlifetimemanager.cpp",
          v31);
      memset_0(v30, 0, 24LL * *a9);
      *a11 = *a9;
      for ( m = 0; m < *a9; ++m )
      {
        v34 = (__int64)*v32 + 24 * m;
        v35 = SHStrDupW((*a8)[m], (LPWSTR *)v34);
        if ( v35 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xD7,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\jitvlifetimemanager.cpp",
            (const char *)(unsigned int)v35,
            v36);
        *(_DWORD *)(v34 + 8) = 1;
        *(_QWORD *)(v34 + 16) = 0;
        v32 = a10;
      }
      goto LABEL_3;
    }
    v25 = (const unsigned __int16 **)*a8;
    v26 = (_DWORD *)*((_QWORD *)DesktopAppXProvider::Instance() + 1);
    if ( v26 && *v26 )
    {
      DesktopAppXProvider::Instance();
      DesktopAppXProvider::JitvAllowServicingError_(v27, v25, *a9);
    }
    std::vector<WriteVirtualization::RegistryExclusion>::_Tidy(&v36);
    result = 2147500036LL;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xE4,
                           (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\jitvlifetimemanager.cpp",
                           v16);
  }
  return result;
}

```

## disassembly

```asm
0x18007d540  mov     rax, rsp
0x18007d543  mov     [rax+20h], r9
0x18007d547  mov     [rax+10h], rdx
0x18007d54b  mov     [rax+8], rcx
0x18007d54f  push    rbx
0x18007d550  push    rsi
0x18007d551  push    rdi
0x18007d552  push    r12
0x18007d554  push    r13
0x18007d556  push    r14
0x18007d558  push    r15
0x18007d55a  sub     rsp, 50h
0x18007d55e  mov     rdi, r9
0x18007d561  mov     r12d, r8d
0x18007d564  mov     r14, [rsp+88h+arg_38]
0x18007d56c  mov     rbx, [rsp+88h+arg_40]
0x18007d574  xor     r13d, r13d
0x18007d577  mov     [r14], r13
0x18007d57a  mov     [rbx], r13d
0x18007d57d  mov     rcx, [rsp+88h+arg_48]
0x18007d585  mov     [rcx], r13
0x18007d588  mov     rcx, [rsp+88h+arg_50]
0x18007d590  mov     [rcx], r13d
0x18007d593  xorps   xmm0, xmm0
0x18007d596  movdqu  xmmword ptr [rax-68h], xmm0
0x18007d59b  mov     [rax-58h], r13
0x18007d59f  lea     r9, [rax-68h]
0x18007d5a3  call    ?GetActiveJitvApps@JitvLifetimeManager@@AEAAXPEAPEBGKAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; JitvLifetimeManager::GetActiveJitvApps(ushort const * *,ulong,std::vector<std::wstring> &)
0x18007d5a8  lea     r9, [rsp+88h+var_68]
0x18007d5ad  mov     r8d, [rsp+88h+arg_20]
0x18007d5b5  mov     rdx, rdi
0x18007d5b8  call    ?GetActiveJitvApps@JitvLifetimeManager@@AEAAXPEAPEBGKAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; JitvLifetimeManager::GetActiveJitvApps(ushort const * *,ulong,std::vector<std::wstring> &)
0x18007d5bd  mov     r15, [rsp+88h+var_68]
0x18007d5c2  mov     rsi, [rsp+88h+var_60]
0x18007d5c7  cmp     r15, rsi
0x18007d5ca  jnz     short loc_18007D5DD
0x18007d5cc  lea     rcx, [rsp+88h+var_68]
0x18007d5d1  call    ?_Tidy@?$vector@URegistryExclusion@WriteVirtualization@@V?$allocator@URegistryExclusion@WriteVirtualization@@@std@@@std@@AEAAXXZ; std::vector<WriteVirtualization::RegistryExclusion>::_Tidy(void)
0x18007d5d6  xor     eax, eax
0x18007d5d8  jmp     loc_18007D7CD
0x18007d5dd  mov     rcx, rsi
0x18007d5e0  sub     rcx, r15
0x18007d5e3  sar     rcx, 5
0x18007d5e7  mov     ecx, ecx
0x18007d5e9  mov     [rbx], ecx
0x18007d5eb  shl     rcx, 3; cb
0x18007d5ef  call    cs:__imp_CoTaskMemAlloc
0x18007d5f6  nop     dword ptr [rax+rax+00h]
0x18007d5fb  mov     [r14], rax
0x18007d5fe  mov     rcx, [rsp+88h]; this
0x18007d606  test    rax, rax
0x18007d609  jz      loc_18007D7DE
0x18007d60f  mov     r8d, [rbx]
0x18007d612  shl     r8, 3; Size
0x18007d616  xor     edx, edx; Val
0x18007d618  mov     rcx, rax; void *
0x18007d61b  call    memset_0
0x18007d620  mov     rdi, r15
0x18007d623  cmp     rdi, rsi
0x18007d626  jz      short loc_18007D664
0x18007d628  movsxd  rcx, r13d
0x18007d62b  mov     rax, [r14]
0x18007d62e  lea     rdx, [rax+rcx*8]; ppwsz
0x18007d632  inc     r13d
0x18007d635  mov     rcx, rdi
0x18007d638  cmp     qword ptr [rdi+18h], 7
0x18007d63d  jbe     short loc_18007D642
0x18007d63f  mov     rcx, [rdi]; psz
0x18007d642  call    cs:__imp_SHStrDupW
0x18007d649  nop     dword ptr [rax+rax+00h]
0x18007d64e  mov     rcx, [rsp+88h]; this
0x18007d656  test    eax, eax
0x18007d658  js      loc_18007D7EF
0x18007d65e  add     rdi, 20h ; ' '
0x18007d662  jmp     short loc_18007D623
0x18007d664  xor     r13d, r13d
0x18007d667  cmp     [rsp+88h+arg_28], r13d
0x18007d66f  jnz     short loc_18007D6B1
0x18007d671  cmp     r15, rsi
0x18007d674  jz      short loc_18007D6B1
0x18007d676  mov     rdi, [r14]
0x18007d679  call    ?Instance@DesktopAppXProvider@@KAPEAV1@XZ; DesktopAppXProvider::Instance(void)
0x18007d67e  mov     rcx, [rax+8]
0x18007d682  test    rcx, rcx
0x18007d685  jz      short loc_18007D69D
0x18007d687  cmp     [rcx], r13d
0x18007d68a  jbe     short loc_18007D69D
0x18007d68c  call    ?Instance@DesktopAppXProvider@@KAPEAV1@XZ; DesktopAppXProvider::Instance(void)
0x18007d691  mov     r8d, [rbx]; int
0x18007d694  mov     rdx, rdi; unsigned __int16 **
0x18007d697  call    ?JitvAllowServicingError_@DesktopAppXProvider@@QEAAXPEAPEBGH@Z; DesktopAppXProvider::JitvAllowServicingError_(ushort const * *,int)
0x18007d69c  nop
0x18007d69d  lea     rcx, [rsp+88h+var_68]
0x18007d6a2  call    ?_Tidy@?$vector@URegistryExclusion@WriteVirtualization@@V?$allocator@URegistryExclusion@WriteVirtualization@@@std@@@std@@AEAAXXZ; std::vector<WriteVirtualization::RegistryExclusion>::_Tidy(void)
0x18007d6a7  mov     eax, 80004004h
0x18007d6ac  jmp     loc_18007D7CD
0x18007d6b1  mov     [rsp+88h+var_50], r14
0x18007d6b6  mov     [rsp+88h+var_48], rbx
0x18007d6bb  mov     [rsp+88h+var_40], 1
0x18007d6c0  mov     edi, r13d
0x18007d6c3  mov     rsi, [rsp+88h+arg_0]
0x18007d6cb  mov     r15, [rsp+88h+arg_8]
0x18007d6d3  cmp     edi, r12d
0x18007d6d6  jnb     short loc_18007D6EE
0x18007d6d8  mov     edx, edi
0x18007d6da  mov     rdx, [r15+rdx*8]; unsigned __int16 *
0x18007d6de  lea     rcx, [rsi-88h]; this
0x18007d6e5  call    ?ShutdownPackage@JitvLifetimeManager@@AEAAXPEBG@Z; JitvLifetimeManager::ShutdownPackage(ushort const *)
0x18007d6ea  inc     edi
0x18007d6ec  jmp     short loc_18007D6D3
0x18007d6ee  mov     edi, r13d
0x18007d6f1  mov     r15, [rsp+88h+arg_18]
0x18007d6f9  cmp     edi, [rsp+88h+arg_20]
0x18007d700  jnb     short loc_18007D718
0x18007d702  mov     edx, edi
0x18007d704  mov     rdx, [r15+rdx*8]; unsigned __int16 *
0x18007d708  lea     rcx, [rsi-88h]; this
0x18007d70f  call    ?ShutdownPackage@JitvLifetimeManager@@AEAAXPEBG@Z; JitvLifetimeManager::ShutdownPackage(ushort const *)
0x18007d714  inc     edi
0x18007d716  jmp     short loc_18007D6F9
0x18007d718  mov     eax, [rbx]
0x18007d71a  lea     rcx, [rax+rax*2]
0x18007d71e  shl     rcx, 3; cb
0x18007d722  call    cs:__imp_CoTaskMemAlloc
0x18007d729  nop     dword ptr [rax+rax+00h]
0x18007d72e  mov     rcx, rax; void *
0x18007d731  mov     rsi, [rsp+88h+arg_48]
0x18007d739  mov     [rsi], rax
0x18007d73c  mov     rax, [rsp+88h]
0x18007d744  test    rcx, rcx
0x18007d747  jz      loc_18007D804
0x18007d74d  mov     eax, [rbx]
0x18007d74f  lea     r8, [rax+rax*2]
0x18007d753  shl     r8, 3; Size
0x18007d757  xor     edx, edx; Val
0x18007d759  call    memset_0
0x18007d75e  mov     eax, [rbx]
0x18007d760  mov     rcx, [rsp+88h+arg_50]
0x18007d768  mov     [rcx], eax
0x18007d76a  mov     edi, r13d
0x18007d76d  cmp     edi, [rbx]
0x18007d76f  jnb     short loc_18007D7B8
0x18007d771  mov     r8d, edi
0x18007d774  lea     rdx, [r8+r8*2]
0x18007d778  mov     rax, [rsi]
0x18007d77b  lea     rsi, [rax+rdx*8]
0x18007d77f  mov     rcx, [r14]
0x18007d782  mov     rdx, rsi; ppwsz
0x18007d785  mov     rcx, [rcx+r8*8]; psz
0x18007d789  call    cs:__imp_SHStrDupW
0x18007d790  nop     dword ptr [rax+rax+00h]
0x18007d795  mov     rcx, [rsp+88h]; this
0x18007d79d  test    eax, eax
0x18007d79f  js      short loc_18007D818
0x18007d7a1  mov     dword ptr [rsi+8], 1
0x18007d7a8  mov     [rsi+10h], r13
0x18007d7ac  inc     edi
0x18007d7ae  mov     rsi, [rsp+88h+arg_48]
0x18007d7b6  jmp     short loc_18007D76D
0x18007d7b8  lea     rcx, [rsp+88h+var_68]
0x18007d7bd  call    ?_Tidy@?$vector@URegistryExclusion@WriteVirtualization@@V?$allocator@URegistryExclusion@WriteVirtualization@@@std@@@std@@AEAAXXZ; std::vector<WriteVirtualization::RegistryExclusion>::_Tidy(void)
0x18007d7c2  xor     eax, eax
0x18007d7c4  jmp     short loc_18007D7CD
0x18007d7c6  mov     eax, dword ptr [rsp+88h+arg_48]
0x18007d7cd  add     rsp, 50h
0x18007d7d1  pop     r15
0x18007d7d3  pop     r14
0x18007d7d5  pop     r13
0x18007d7d7  pop     r12
0x18007d7d9  pop     rdi
0x18007d7da  pop     rsi
0x18007d7db  pop     rbx
0x18007d7dc  retn
0x18007d7de  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x18007d7e5  mov     edx, 0B0h; void *
0x18007d7ea  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18007d7ef  mov     r9d, eax; char *
0x18007d7f2  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x18007d7f9  mov     edx, 0B5h; void *
0x18007d7fe  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007d804  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x18007d80b  mov     edx, 0D1h; void *
0x18007d810  mov     rcx, rax; this
0x18007d813  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18007d818  mov     r9d, eax; char *
0x18007d81b  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x18007d822  mov     edx, 0D7h; void *
0x18007d827  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
