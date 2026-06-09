# JitvLifetimeManager::AllowServicing(ushort const * *,ulong,ushort const * *,ulong,int,int,ushort * * *,ulong *,SERVICING_TERMINATION_INFO * *,ulong *)

- ea: `0x18007f040`
- end: `0x18007f33e`
- name: `?AllowServicing@JitvLifetimeManager@@UEAAJPEAPEBGK0KHHPEAPEAPEAGPEAKPEAPEAUSERVICING_TERMINATION_INFO@@2@Z`
- size: `766`
- prototype: `__int64 __fastcall(JitvLifetimeManager *__hidden this, const unsigned __int16 **, unsigned int, const unsigned __int16 **, unsigned int, int, int, unsigned __int16 ***, unsigned int *, struct SERVICING_TERMINATION_INFO **, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x1800059a8`
- `0x180011e9c`
- `0x1800125f4`
- `0x180035e2c`
- `0x1800360e0`
- `0x18007f040`
- `0x18007f720`
- `0x18007fb58`
- `0x18007ff60`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007f0ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007f22a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007f0ea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18007f22a`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18007f150`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18007f28a`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18007f150`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18007f28a`

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
  __int64 v15; // rcx
  const char *v16; // r9
  __int64 result; // rax
  signed __int64 v18; // rax
  unsigned __int16 **v19; // rax
  const char *v20; // r9
  int v21; // esi
  LPCWSTR v22; // rax
  LPCWSTR v23; // rdi
  LPCWSTR v24; // rcx
  LPCWSTR v25; // rdx
  const WCHAR *v26; // rcx
  HRESULT v27; // eax
  const unsigned __int16 **v28; // rdi
  _DWORD *v29; // rax
  DesktopAppXProvider *v30; // rcx
  __int64 i; // rdi
  __int64 j; // rdi
  struct SERVICING_TERMINATION_INFO *v33; // rcx
  const char *v34; // r9
  struct SERVICING_TERMINATION_INFO **v35; // rsi
  __int64 v36; // rdi
  __int64 v37; // rsi
  HRESULT v38; // eax
  LPCWSTR psz[2]; // [rsp+20h] [rbp-58h] BYREF
  __int64 v40; // [rsp+30h] [rbp-48h]
  unsigned __int16 ***v41; // [rsp+38h] [rbp-40h]
  unsigned int *v42; // [rsp+40h] [rbp-38h]
  char v43; // [rsp+48h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  unsigned __int16 ***v46; // [rsp+B8h] [rbp+40h]

  *a8 = 0;
  *a9 = 0;
  *a10 = 0;
  *a11 = 0;
  *(_OWORD *)psz = 0;
  v40 = 0;
  try
  {
    JitvLifetimeManager::GetActiveJitvApps((__int64)this, (__int64)a2, a3, (__int64)psz);
    JitvLifetimeManager::GetActiveJitvApps(v15, (__int64)a4, a5, (__int64)psz);
    if ( psz[0] == psz[1] )
    {
LABEL_3:
      std::vector<WriteVirtualization::RegistryExclusion>::_Tidy(psz);
      return 0;
    }
    v18 = ((char *)psz[1] - (char *)psz[0]) >> 5;
    *a9 = v18;
    v19 = (unsigned __int16 **)CoTaskMemAlloc(8LL * (unsigned int)v18);
    *a8 = v19;
    if ( !v19 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0xB0,
        (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\jitvlifetimemanager.cpp",
        v20);
    memset_0(v19, 0, 8LL * *a9);
    v21 = 0;
    v22 = psz[0];
    v23 = psz[0];
    v24 = psz[1];
    v25 = psz[1];
    v46 = (unsigned __int16 ***)psz[1];
    while ( v23 != v25 )
    {
      if ( *((_QWORD *)v23 + 3) <= 7u )
        v26 = v23;
      else
        v26 = *(const WCHAR **)v23;
      v27 = SHStrDupW(v26, &(*a8)[v21]);
      if ( v27 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB5,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\jitvlifetimemanager.cpp",
          (const char *)(unsigned int)v27,
          (int)psz[0]);
      ++v21;
      v23 += 16;
      v24 = psz[1];
      v22 = psz[0];
      v25 = (LPCWSTR)v46;
    }
    if ( a6 || v22 == v24 )
    {
      v41 = a8;
      v42 = a9;
      v43 = 1;
      for ( i = 0; (unsigned int)i < a3; i = (unsigned int)(i + 1) )
        JitvLifetimeManager::ShutdownPackage((JitvLifetimeManager *)((char *)this - 136), a2[i]);
      for ( j = 0; (unsigned int)j < a5; j = (unsigned int)(j + 1) )
        JitvLifetimeManager::ShutdownPackage((JitvLifetimeManager *)((char *)this - 136), a4[j]);
      v33 = (struct SERVICING_TERMINATION_INFO *)CoTaskMemAlloc(24LL * *a9);
      v35 = a10;
      *a10 = v33;
      if ( !v33 )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0xD1,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\jitvlifetimemanager.cpp",
          v34);
      memset_0(v33, 0, 24LL * *a9);
      *a11 = *a9;
      v36 = 0;
      while ( (unsigned int)v36 < *a9 )
      {
        v37 = (__int64)*v35 + 24 * v36;
        v38 = SHStrDupW((*a8)[v36], (LPWSTR *)v37);
        if ( v38 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xD7,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\libjitv\\jitvlifetimemanager.cpp",
            (const char *)(unsigned int)v38,
            (int)psz[0]);
        *(_DWORD *)(v37 + 8) = 1;
        *(_QWORD *)(v37 + 16) = 0;
        v36 = (unsigned int)(v36 + 1);
        v35 = a10;
      }
      goto LABEL_3;
    }
    v28 = (const unsigned __int16 **)*a8;
    v29 = (_DWORD *)*((_QWORD *)DesktopAppXProvider::Instance() + 1);
    if ( v29 && *v29 )
    {
      DesktopAppXProvider::Instance();
      DesktopAppXProvider::JitvAllowServicingError_(v30, v28, *a9);
    }
    std::vector<WriteVirtualization::RegistryExclusion>::_Tidy(psz);
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
0x18007f040  mov     r11, rsp
0x18007f043  mov     [r11+10h], rbx
0x18007f047  mov     [r11+18h], rsi
0x18007f04b  mov     [r11+8], rcx
0x18007f04f  push    rdi
0x18007f050  push    r12
0x18007f052  push    r13
0x18007f054  push    r14
0x18007f056  push    r15
0x18007f058  sub     rsp, 50h
0x18007f05c  mov     r13, r9
0x18007f05f  mov     r15d, r8d
0x18007f062  mov     r12, rdx
0x18007f065  xor     edi, edi
0x18007f067  mov     r14, [rsp+78h+arg_38]
0x18007f06f  mov     [r14], rdi
0x18007f072  mov     rbx, [rsp+78h+arg_40]
0x18007f07a  mov     [rbx], edi
0x18007f07c  mov     rax, [rsp+78h+arg_48]
0x18007f084  mov     [rax], rdi
0x18007f087  mov     rax, [rsp+78h+arg_50]
0x18007f08f  mov     [rax], edi
0x18007f091  xorps   xmm0, xmm0
0x18007f094  movdqu  xmmword ptr [rsp+78h+psz], xmm0; int
0x18007f09a  mov     [r11-48h], rdi
0x18007f09e  lea     r9, [r11-58h]
0x18007f0a2  call    ?GetActiveJitvApps@JitvLifetimeManager@@AEAAXPEAPEBGKAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; JitvLifetimeManager::GetActiveJitvApps(ushort const * *,ulong,std::vector<std::wstring> &)
0x18007f0a7  lea     r9, [rsp+78h+psz]
0x18007f0ac  mov     r8d, [rsp+78h+arg_20]
0x18007f0b4  mov     rdx, r13
0x18007f0b7  call    ?GetActiveJitvApps@JitvLifetimeManager@@AEAAXPEAPEBGKAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; JitvLifetimeManager::GetActiveJitvApps(ushort const * *,ulong,std::vector<std::wstring> &)
0x18007f0bc  mov     rax, [rsp+78h+psz+8]
0x18007f0c1  cmp     [rsp+78h+psz], rax
0x18007f0c6  jnz     short loc_18007F0D9
0x18007f0c8  lea     rcx, [rsp+78h+psz]
0x18007f0cd  call    ?_Tidy@?$vector@URegistryExclusion@WriteVirtualization@@V?$allocator@URegistryExclusion@WriteVirtualization@@@std@@@std@@AEAAXXZ; std::vector<WriteVirtualization::RegistryExclusion>::_Tidy(void)
0x18007f0d2  xor     eax, eax
0x18007f0d4  jmp     loc_18007F2D3
0x18007f0d9  sub     rax, [rsp+78h+psz]
0x18007f0de  sar     rax, 5
0x18007f0e2  mov     ecx, eax
0x18007f0e4  mov     [rbx], ecx
0x18007f0e6  shl     rcx, 3; cb
0x18007f0ea  call    cs:__imp_CoTaskMemAlloc
0x18007f0f1  nop     dword ptr [rax+rax+00h]
0x18007f0f6  mov     [r14], rax
0x18007f0f9  mov     rcx, [rsp+78h]; this
0x18007f0fe  test    rax, rax
0x18007f101  jz      loc_18007F2EE
0x18007f107  mov     r8d, [rbx]
0x18007f10a  shl     r8, 3; Size
0x18007f10e  xor     edx, edx; Val
0x18007f110  mov     rcx, rax; void *
0x18007f113  call    memset_0
0x18007f118  mov     esi, edi
0x18007f11a  mov     rax, [rsp+78h+psz]
0x18007f11f  mov     rdi, rax
0x18007f122  mov     rcx, [rsp+78h+psz+8]
0x18007f127  mov     rdx, rcx
0x18007f12a  mov     [rsp+78h+arg_38], rcx
0x18007f132  cmp     rdi, rdx
0x18007f135  jz      short loc_18007F183
0x18007f137  movsxd  rcx, esi
0x18007f13a  mov     rax, [r14]
0x18007f13d  lea     rdx, [rax+rcx*8]; ppwsz
0x18007f141  cmp     qword ptr [rdi+18h], 7
0x18007f146  jbe     short loc_18007F14D
0x18007f148  mov     rcx, [rdi]
0x18007f14b  jmp     short loc_18007F150
0x18007f14d  mov     rcx, rdi; psz
0x18007f150  call    cs:__imp_SHStrDupW
0x18007f157  nop     dword ptr [rax+rax+00h]
0x18007f15c  mov     rcx, [rsp+78h]; this
0x18007f161  test    eax, eax
0x18007f163  js      loc_18007F2FF
0x18007f169  inc     esi
0x18007f16b  add     rdi, 20h ; ' '
0x18007f16f  mov     rcx, [rsp+78h+psz+8]
0x18007f174  mov     rax, [rsp+78h+psz]
0x18007f179  mov     rdx, [rsp+78h+arg_38]
0x18007f181  jmp     short loc_18007F132
0x18007f183  cmp     [rsp+78h+arg_28], 0
0x18007f18b  jnz     short loc_18007F1CE
0x18007f18d  cmp     rax, rcx
0x18007f190  jz      short loc_18007F1CE
0x18007f192  mov     rdi, [r14]
0x18007f195  call    ?Instance@DesktopAppXProvider@@KAPEAV1@XZ; DesktopAppXProvider::Instance(void)
0x18007f19a  mov     rax, [rax+8]
0x18007f19e  test    rax, rax
0x18007f1a1  jz      short loc_18007F1BA
0x18007f1a3  mov     eax, [rax]
0x18007f1a5  test    eax, eax
0x18007f1a7  jz      short loc_18007F1BA
0x18007f1a9  call    ?Instance@DesktopAppXProvider@@KAPEAV1@XZ; DesktopAppXProvider::Instance(void)
0x18007f1ae  mov     r8d, [rbx]; int
0x18007f1b1  mov     rdx, rdi; unsigned __int16 **
0x18007f1b4  call    ?JitvAllowServicingError_@DesktopAppXProvider@@QEAAXPEAPEBGH@Z; DesktopAppXProvider::JitvAllowServicingError_(ushort const * *,int)
0x18007f1b9  nop
0x18007f1ba  lea     rcx, [rsp+78h+psz]
0x18007f1bf  call    ?_Tidy@?$vector@URegistryExclusion@WriteVirtualization@@V?$allocator@URegistryExclusion@WriteVirtualization@@@std@@@std@@AEAAXXZ; std::vector<WriteVirtualization::RegistryExclusion>::_Tidy(void)
0x18007f1c4  mov     eax, 80004004h
0x18007f1c9  jmp     loc_18007F2D3
0x18007f1ce  mov     [rsp+78h+var_40], r14
0x18007f1d3  mov     [rsp+78h+var_38], rbx
0x18007f1d8  mov     [rsp+78h+var_30], 1
0x18007f1dd  xor     edi, edi
0x18007f1df  mov     rsi, [rsp+78h+arg_0]
0x18007f1e7  cmp     edi, r15d
0x18007f1ea  jnb     short loc_18007F200
0x18007f1ec  mov     rdx, [r12+rdi*8]; unsigned __int16 *
0x18007f1f0  lea     rcx, [rsi-88h]; this
0x18007f1f7  call    ?ShutdownPackage@JitvLifetimeManager@@AEAAXPEBG@Z; JitvLifetimeManager::ShutdownPackage(ushort const *)
0x18007f1fc  inc     edi
0x18007f1fe  jmp     short loc_18007F1DF
0x18007f200  xor     edi, edi
0x18007f202  cmp     edi, [rsp+78h+arg_20]
0x18007f209  jnb     short loc_18007F220
0x18007f20b  mov     rdx, [r13+rdi*8+0]; unsigned __int16 *
0x18007f210  lea     rcx, [rsi-88h]; this
0x18007f217  call    ?ShutdownPackage@JitvLifetimeManager@@AEAAXPEBG@Z; JitvLifetimeManager::ShutdownPackage(ushort const *)
0x18007f21c  inc     edi
0x18007f21e  jmp     short loc_18007F202
0x18007f220  mov     eax, [rbx]
0x18007f222  lea     rcx, [rax+rax*2]
0x18007f226  shl     rcx, 3; cb
0x18007f22a  call    cs:__imp_CoTaskMemAlloc
0x18007f231  nop     dword ptr [rax+rax+00h]
0x18007f236  mov     rcx, rax; void *
0x18007f239  mov     rsi, [rsp+78h+arg_48]
0x18007f241  mov     [rsi], rax
0x18007f244  mov     rax, [rsp+78h]
0x18007f249  test    rcx, rcx
0x18007f24c  jz      loc_18007F314
0x18007f252  mov     eax, [rbx]
0x18007f254  lea     r8, [rax+rax*2]
0x18007f258  shl     r8, 3; Size
0x18007f25c  xor     edx, edx; Val
0x18007f25e  call    memset_0
0x18007f263  mov     eax, [rbx]
0x18007f265  mov     rcx, [rsp+78h+arg_50]
0x18007f26d  mov     [rcx], eax
0x18007f26f  xor     edi, edi
0x18007f271  cmp     edi, [rbx]
0x18007f273  jnb     short loc_18007F2BE
0x18007f275  lea     rdx, [rdi+rdi*2]
0x18007f279  mov     rax, [rsi]
0x18007f27c  lea     rsi, [rax+rdx*8]
0x18007f280  mov     rcx, [r14]
0x18007f283  mov     rdx, rsi; ppwsz
0x18007f286  mov     rcx, [rcx+rdi*8]; psz
0x18007f28a  call    cs:__imp_SHStrDupW
0x18007f291  nop     dword ptr [rax+rax+00h]
0x18007f296  mov     rcx, [rsp+78h]; this
0x18007f29b  test    eax, eax
0x18007f29d  js      loc_18007F328
0x18007f2a3  mov     dword ptr [rsi+8], 1
0x18007f2aa  mov     qword ptr [rsi+10h], 0
0x18007f2b2  inc     edi
0x18007f2b4  mov     rsi, [rsp+78h+arg_48]
0x18007f2bc  jmp     short loc_18007F271
0x18007f2be  lea     rcx, [rsp+78h+psz]
0x18007f2c3  call    ?_Tidy@?$vector@URegistryExclusion@WriteVirtualization@@V?$allocator@URegistryExclusion@WriteVirtualization@@@std@@@std@@AEAAXXZ; std::vector<WriteVirtualization::RegistryExclusion>::_Tidy(void)
0x18007f2c8  xor     eax, eax
0x18007f2ca  jmp     short loc_18007F2D3
0x18007f2cc  mov     eax, dword ptr [rsp+78h+arg_48]
0x18007f2d3  lea     r11, [rsp+78h+var_28]
0x18007f2d8  mov     rbx, [r11+38h]
0x18007f2dc  mov     rsi, [r11+40h]
0x18007f2e0  mov     rsp, r11
0x18007f2e3  pop     r15
0x18007f2e5  pop     r14
0x18007f2e7  pop     r13
0x18007f2e9  pop     r12
0x18007f2eb  pop     rdi
0x18007f2ec  retn
0x18007f2ee  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x18007f2f5  mov     edx, 0B0h; void *
0x18007f2fa  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18007f2ff  mov     r9d, eax; char *
0x18007f302  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x18007f309  mov     edx, 0B5h; void *
0x18007f30e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007f314  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x18007f31b  mov     edx, 0D1h; void *
0x18007f320  mov     rcx, rax; this
0x18007f323  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18007f328  mov     r9d, eax; char *
0x18007f32b  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\execmodel\\des"...
0x18007f332  mov     edx, 0D7h; void *
0x18007f337  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
