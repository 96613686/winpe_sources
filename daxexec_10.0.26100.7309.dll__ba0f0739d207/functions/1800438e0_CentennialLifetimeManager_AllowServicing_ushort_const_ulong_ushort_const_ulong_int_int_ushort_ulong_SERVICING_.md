# CentennialLifetimeManager::AllowServicing(ushort const * *,ulong,ushort const * *,ulong,int,int,ushort * * *,ulong *,SERVICING_TERMINATION_INFO * *,ulong *)

- ea: `0x1800438e0`
- end: `0x180043d39`
- name: `?AllowServicing@CentennialLifetimeManager@@UEAAJPEAPEBGK0KHHPEAPEAPEAGPEAKPEAPEAUSERVICING_TERMINATION_INFO@@2@Z`
- size: `1113`
- prototype: `__int64 __fastcall(CentennialLifetimeManager *__hidden this, const unsigned __int16 **, unsigned int, const unsigned __int16 **, unsigned int, int, int, unsigned __int16 ***, unsigned int *, struct SERVICING_TERMINATION_INFO **, unsigned int *)`
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1800053a0`
- `0x180006158`
- `0x1800148e8`
- `0x180014f4c`
- `0x18001748c`
- `0x18001ec94`
- `0x1800341b4`
- `0x180037468`
- `0x1800374e0`
- `0x180037600`
- `0x18003fa14`
- `0x1800428b4`
- `0x180042fb4`
- `0x1800438e0`
- `0x180047298`
- `0x1800476c8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180043a38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180043be6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180043a38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180043be6`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180043a9e`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180043c79`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180043a9e`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180043c79`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x180043c4f`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x180043c4f`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CentennialLifetimeManager::AllowServicing(
        CentennialLifetimeManager *this,
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
  __int64 v11; // r14
  int v13; // ebx
  unsigned int v14; // ebx
  CentennialLifetimeManager *v15; // r13
  unsigned int v16; // edi
  unsigned __int16 **v17; // rax
  const char *v18; // r9
  unsigned int v19; // edi
  _QWORD *v20; // rax
  _QWORD *v21; // rbx
  const WCHAR *v22; // rcx
  HRESULT v23; // eax
  __int64 v24; // rax
  const char *v25; // r9
  __int64 result; // rax
  __int64 v27; // rbx
  struct SERVICING_TERMINATION_INFO *v28; // rcx
  const char *v29; // r9
  struct SERVICING_TERMINATION_INFO **v30; // r14
  unsigned __int64 i; // rbx
  __int64 v32; // rdi
  int v33; // [rsp+20h] [rbp-248h]
  unsigned int v34; // [rsp+30h] [rbp-238h] BYREF
  UINT32 packageFamilyNameLength[2]; // [rsp+38h] [rbp-230h] BYREF
  unsigned __int16 **v36; // [rsp+40h] [rbp-228h] BYREF
  UINT32 packageRelativeApplicationIdLength[2]; // [rsp+48h] [rbp-220h] BYREF
  unsigned __int16 ***v38; // [rsp+50h] [rbp-218h] BYREF
  struct SERVICING_TERMINATION_INFO **v39; // [rsp+58h] [rbp-210h]
  _QWORD v40[2]; // [rsp+60h] [rbp-208h] BYREF
  _QWORD v41[3]; // [rsp+70h] [rbp-1F8h] BYREF
  char v42; // [rsp+88h] [rbp-1E0h]
  char v43[8]; // [rsp+90h] [rbp-1D8h] BYREF
  _QWORD *v44; // [rsp+98h] [rbp-1D0h] BYREF
  __int64 v45; // [rsp+A0h] [rbp-1C8h]
  char v46[40]; // [rsp+A8h] [rbp-1C0h] BYREF
  _QWORD v47[42]; // [rsp+D0h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  *(_QWORD *)packageRelativeApplicationIdLength = a4;
  v11 = a3;
  *(_QWORD *)packageFamilyNameLength = a2;
  v38 = a8;
  v39 = a10;
  v13 = a3 + a5;
  wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v47,
    "AllowServicing");
  v47[0] = &DesktopAppXProvider::AllowServicing::`vftable';
  try
  {
    DesktopAppXProvider::AllowServicing::StartActivity((DesktopAppXProvider::AllowServicing *)v47, v13, a6);
    v14 = 0;
    *a11 = 0;
    *a10 = 0;
    *a9 = 0;
    if ( v38 )
      *v38 = 0;
    v41[0] = &v36;
    v41[1] = &v34;
    v41[2] = &v38;
    v42 = 1;
    v15 = (CentennialLifetimeManager *)((char *)this - 152);
    v36 = 0;
    v34 = 0;
    std::unordered_set<std::wstring>::unordered_set<std::wstring>(v43);
    v40[0] = (char *)this - 152;
    v40[1] = v43;
    v16 = a5;
    lambda_1d46f3311b4a979ff36b016456cb2094_::operator()(v40, a5, *(_QWORD *)packageRelativeApplicationIdLength);
    lambda_1d46f3311b4a979ff36b016456cb2094_::operator()(v40, v11, *(_QWORD *)packageFamilyNameLength);
    if ( v45 )
    {
      v34 = v45;
      v17 = (unsigned __int16 **)CoTaskMemAlloc(8LL * (unsigned int)v45);
      v36 = v17;
      if ( !v17 )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0x1B1,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\centenniallifetimemanager.cpp",
          v18);
      memset_0(v17, 0, 8LL * v34);
      v19 = 0;
      v20 = v44;
      v21 = (_QWORD *)*v44;
      while ( v21 != v20 && v19 < v34 )
      {
        v22 = (const WCHAR *)(v21 + 2);
        if ( v21[5] > 7u )
          v22 = *(const WCHAR **)v22;
        v23 = SHStrDupW(v22, &v36[v19]);
        if ( v23 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1B9,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\centenniallifetimemanager.cpp",
            (const char *)(unsigned int)v23,
            v33);
        v21 = (_QWORD *)*v21;
        ++v19;
        v20 = v44;
      }
      v14 = 0;
      v16 = a5;
    }
    std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(v46);
    std::list<std::wstring>::~list<std::wstring>(&v44);
    v24 = v34;
    *a9 = v34;
    if ( v38 )
    {
      *v38 = v36;
      v42 = 0;
      v24 = v34;
    }
    if ( a6 || !(_DWORD)v24 )
    {
      while ( v14 < (unsigned int)v11 )
      {
        CentennialLifetimeManager::ShutdownPackage(
          v15,
          *(const unsigned __int16 **)(*(_QWORD *)packageFamilyNameLength + 8LL * v14++),
          0,
          a7 != 0);
        v24 = v34;
      }
      v27 = 0;
      while ( (unsigned int)v27 < v16 )
      {
        CentennialLifetimeManager::ShutdownPackage(
          v15,
          *(const unsigned __int16 **)(*(_QWORD *)packageRelativeApplicationIdLength + 8 * v27),
          0,
          a7 != 0);
        v27 = (unsigned int)(v27 + 1);
        v24 = v34;
      }
      if ( (_DWORD)v24 )
      {
        v28 = (struct SERVICING_TERMINATION_INFO *)CoTaskMemAlloc(24 * v24);
        v30 = v39;
        *v39 = v28;
        if ( !v28 )
          wil::details::in1diag3::_Throw_NullAlloc(
            retaddr,
            (void *)0xE5,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\centenniallifetimemanager.cpp",
            v29);
        memset_0(v28, 0, 24LL * v34);
        for ( i = 0; i < v34; ++i )
        {
          packageFamilyNameLength[0] = 0;
          packageRelativeApplicationIdLength[0] = 0;
          if ( ParseApplicationUserModelId(v36[i], packageFamilyNameLength, 0, packageRelativeApplicationIdLength, 0) == 122 )
          {
            v32 = (__int64)*v30 + 24 * *a11;
            if ( SHStrDupW(v36[i], (LPWSTR *)v32) >= 0 )
            {
              *(_DWORD *)(v32 + 8) = 1;
              *(_QWORD *)(v32 + 16) = 0;
              ++*a11;
            }
          }
        }
      }
      wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v47, 0);
      wil::details::ScopeExitFn__lambda_acfd60c8a63b5138d0ae6bffd2ceb1de___::_ScopeExitFn__lambda_acfd60c8a63b5138d0ae6bffd2ceb1de___(v41);
      v47[0] = &DesktopAppXProvider::AllowServicing::`vftable';
      wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v47);
      wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v47);
      result = 0;
    }
    else
    {
      wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v47, 0);
      wil::details::ScopeExitFn__lambda_acfd60c8a63b5138d0ae6bffd2ceb1de___::_ScopeExitFn__lambda_acfd60c8a63b5138d0ae6bffd2ceb1de___(v41);
      v47[0] = &DesktopAppXProvider::AllowServicing::`vftable';
      wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v47);
      wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v47);
      result = 2147500036LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xFF,
                           (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\centenniallifetimemanager.cpp",
                           v25);
  }
  return result;
}

```

## disassembly

```asm
0x1800438e0  push    rbx
0x1800438e2  push    rsi
0x1800438e3  push    rdi
0x1800438e4  push    r13
0x1800438e6  push    r14
0x1800438e8  push    r15
0x1800438ea  sub     rsp, 238h
0x1800438f1  mov     rax, cs:__security_cookie
0x1800438f8  xor     rax, rsp
0x1800438fb  mov     [rsp+268h+var_48], rax
0x180043903  mov     qword ptr [rsp+268h+packageRelativeApplicationIdLength], r9
0x180043908  mov     r14d, r8d
0x18004390b  mov     qword ptr [rsp+268h+packageFamilyNameLength], rdx
0x180043910  mov     rdi, rcx
0x180043913  mov     rax, [rsp+268h+arg_38]
0x18004391b  mov     [rsp+268h+var_218], rax
0x180043920  mov     r15, [rsp+268h+arg_40]
0x180043928  mov     r13, [rsp+268h+arg_48]
0x180043930  mov     [rsp+268h+var_210], r13
0x180043935  mov     rsi, [rsp+268h+arg_50]
0x18004393d  mov     ebx, [rsp+268h+arg_20]
0x180043944  add     ebx, r14d
0x180043947  lea     rdx, aAllowservicing; "AllowServicing"
0x18004394e  lea     rcx, [rsp+268h+var_198]
0x180043956  call    ??0?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18004395b  lea     rax, ??_7AllowServicing@DesktopAppXProvider@@6B@; const DesktopAppXProvider::AllowServicing::`vftable'
0x180043962  mov     [rsp+268h+var_198], rax
0x18004396a  mov     r8d, [rsp+268h+arg_28]; int
0x180043972  mov     edx, ebx; int
0x180043974  lea     rcx, [rsp+268h+var_198]; this
0x18004397c  call    ?StartActivity@AllowServicing@DesktopAppXProvider@@QEAAXHH@Z; DesktopAppXProvider::AllowServicing::StartActivity(int,int)
0x180043981  nop
0x180043982  xor     ebx, ebx
0x180043984  mov     [rsi], ebx
0x180043986  mov     [r13+0], rbx
0x18004398a  mov     [r15], ebx
0x18004398d  mov     rax, [rsp+268h+var_218]
0x180043992  test    rax, rax
0x180043995  jz      short loc_18004399A
0x180043997  mov     [rax], rbx
0x18004399a  lea     rax, [rsp+268h+var_228]
0x18004399f  mov     [rsp+268h+var_1F8], rax
0x1800439a4  lea     rax, [rsp+268h+var_238]
0x1800439a9  mov     [rsp+268h+var_1F0], rax
0x1800439ae  lea     rax, [rsp+268h+var_218]
0x1800439b3  mov     [rsp+268h+var_1E8], rax
0x1800439bb  mov     [rsp+268h+var_1E0], 1
0x1800439c3  lea     r13, [rdi-98h]
0x1800439ca  mov     [rsp+268h+var_228], rbx
0x1800439cf  mov     [rsp+268h+var_238], ebx
0x1800439d3  lea     rcx, [rsp+268h+var_1D8]
0x1800439db  call    ??0?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::unordered_set<std::wstring>::unordered_set<std::wstring>(void)
0x1800439e0  nop
0x1800439e1  mov     [rsp+268h+var_208], r13
0x1800439e6  lea     rax, [rsp+268h+var_1D8]
0x1800439ee  mov     [rsp+268h+var_200], rax
0x1800439f3  mov     edi, [rsp+268h+arg_20]
0x1800439fa  mov     edx, edi
0x1800439fc  mov     r8, qword ptr [rsp+268h+packageRelativeApplicationIdLength]
0x180043a01  lea     rcx, [rsp+268h+var_208]
0x180043a06  call    _lambda_1d46f3311b4a979ff36b016456cb2094___operator__
0x180043a0b  mov     rdx, r14
0x180043a0e  mov     r8, qword ptr [rsp+268h+packageFamilyNameLength]
0x180043a13  lea     rcx, [rsp+268h+var_208]
0x180043a18  call    _lambda_1d46f3311b4a979ff36b016456cb2094___operator__
0x180043a1d  mov     rax, [rsp+268h+var_1C8]
0x180043a25  test    rax, rax
0x180043a28  jz      loc_180043AE2
0x180043a2e  mov     [rsp+268h+var_238], eax
0x180043a32  mov     ecx, eax
0x180043a34  shl     rcx, 3; cb
0x180043a38  call    cs:__imp_CoTaskMemAlloc
0x180043a3f  nop     dword ptr [rax+rax+00h]
0x180043a44  mov     [rsp+268h+var_228], rax
0x180043a49  mov     rcx, [rsp+268h]; this
0x180043a51  test    rax, rax
0x180043a54  jz      loc_180043D11
0x180043a5a  mov     r8d, [rsp+268h+var_238]
0x180043a5f  shl     r8, 3; Size
0x180043a63  xor     edx, edx; Val
0x180043a65  mov     rcx, rax; void *
0x180043a68  call    memset_0
0x180043a6d  mov     edi, ebx
0x180043a6f  mov     rax, [rsp+268h+var_1D0]
0x180043a77  mov     rbx, [rax]
0x180043a7a  cmp     rbx, rax
0x180043a7d  jz      short loc_180043AD9
0x180043a7f  cmp     edi, [rsp+268h+var_238]
0x180043a83  jnb     short loc_180043AD9
0x180043a85  mov     ecx, edi
0x180043a87  mov     rax, [rsp+268h+var_228]
0x180043a8c  lea     rdx, [rax+rcx*8]; ppwsz
0x180043a90  lea     rcx, [rbx+10h]
0x180043a94  cmp     qword ptr [rcx+18h], 7
0x180043a99  jbe     short loc_180043A9E
0x180043a9b  mov     rcx, [rcx]; psz
0x180043a9e  call    cs:__imp_SHStrDupW
0x180043aa5  nop     dword ptr [rax+rax+00h]
0x180043aaa  test    eax, eax
0x180043aac  jns     short loc_180043ACA
0x180043aae  mov     rcx, [rsp+268h]; this
0x180043ab6  mov     r9d, eax; char *
0x180043ab9  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\execmodel\\des"...
0x180043ac0  mov     edx, 1B9h; void *
0x180043ac5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180043aca  mov     rbx, [rbx]
0x180043acd  inc     edi
0x180043acf  mov     rax, [rsp+268h+var_1D0]
0x180043ad7  jmp     short loc_180043A7A
0x180043ad9  xor     ebx, ebx
0x180043adb  mov     edi, [rsp+268h+arg_20]
0x180043ae2  lea     rcx, [rsp+268h+var_1C0]
0x180043aea  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(void)
0x180043aef  lea     rcx, [rsp+268h+var_1D0]
0x180043af7  call    ??1?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::~list<std::wstring>(void)
0x180043afc  mov     eax, [rsp+268h+var_238]
0x180043b00  mov     [r15], eax
0x180043b03  mov     rcx, [rsp+268h+var_218]
0x180043b08  test    rcx, rcx
0x180043b0b  jz      short loc_180043B20
0x180043b0d  mov     rax, [rsp+268h+var_228]
0x180043b12  mov     [rcx], rax
0x180043b15  mov     [rsp+268h+var_1E0], bl
0x180043b1c  mov     eax, [rsp+268h+var_238]
0x180043b20  cmp     [rsp+268h+arg_28], ebx
0x180043b27  jnz     short loc_180043B7B
0x180043b29  test    eax, eax
0x180043b2b  jz      short loc_180043B7B
0x180043b2d  xor     edx, edx
0x180043b2f  lea     rcx, [rsp+268h+var_198]
0x180043b37  call    ?Stop@?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180043b3c  nop
0x180043b3d  lea     rcx, [rsp+268h+var_1F8]
0x180043b42  call    wil__details__ScopeExitFn__lambda_acfd60c8a63b5138d0ae6bffd2ceb1de______ScopeExitFn__lambda_acfd60c8a63b5138d0ae6bffd2ceb1de___
0x180043b47  nop
0x180043b48  lea     rax, ??_7AllowServicing@DesktopAppXProvider@@6B@; const DesktopAppXProvider::AllowServicing::`vftable'
0x180043b4f  mov     [rsp+268h+var_198], rax
0x180043b57  lea     rcx, [rsp+268h+var_198]
0x180043b5f  call    ?Destroy@?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180043b64  lea     rcx, [rsp+268h+var_198]
0x180043b6c  call    ??1?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180043b71  mov     eax, 80004004h
0x180043b76  jmp     loc_180043CEF
0x180043b7b  mov     r15d, [rsp+268h+arg_30]
0x180043b83  cmp     ebx, r14d
0x180043b86  jnb     short loc_180043BAD
0x180043b88  test    r15d, r15d
0x180043b8b  setnz   r9b; bool
0x180043b8f  mov     edx, ebx
0x180043b91  xor     r8d, r8d; bool
0x180043b94  mov     rax, qword ptr [rsp+268h+packageFamilyNameLength]
0x180043b99  mov     rdx, [rax+rdx*8]; unsigned __int16 *
0x180043b9d  mov     rcx, r13; this
0x180043ba0  call    ?ShutdownPackage@CentennialLifetimeManager@@AEAAXPEBG_N1@Z; CentennialLifetimeManager::ShutdownPackage(ushort const *,bool,bool)
0x180043ba5  inc     ebx
0x180043ba7  mov     eax, [rsp+268h+var_238]
0x180043bab  jmp     short loc_180043B83
0x180043bad  xor     ebx, ebx
0x180043baf  cmp     ebx, edi
0x180043bb1  jnb     short loc_180043BD6
0x180043bb3  test    r15d, r15d
0x180043bb6  setnz   r9b; bool
0x180043bba  xor     r8d, r8d; bool
0x180043bbd  mov     rax, qword ptr [rsp+268h+packageRelativeApplicationIdLength]
0x180043bc2  mov     rdx, [rax+rbx*8]; unsigned __int16 *
0x180043bc6  mov     rcx, r13; this
0x180043bc9  call    ?ShutdownPackage@CentennialLifetimeManager@@AEAAXPEBG_N1@Z; CentennialLifetimeManager::ShutdownPackage(ushort const *,bool,bool)
0x180043bce  inc     ebx
0x180043bd0  mov     eax, [rsp+268h+var_238]
0x180043bd4  jmp     short loc_180043BAF
0x180043bd6  test    eax, eax
0x180043bd8  jz      loc_180043CA3
0x180043bde  lea     rcx, [rax+rax*2]
0x180043be2  shl     rcx, 3; cb
0x180043be6  call    cs:__imp_CoTaskMemAlloc
0x180043bed  nop     dword ptr [rax+rax+00h]
0x180043bf2  mov     rcx, rax; void *
0x180043bf5  mov     r14, [rsp+268h+var_210]
0x180043bfa  mov     [r14], rax
0x180043bfd  mov     rax, [rsp+268h]
0x180043c05  test    rcx, rcx
0x180043c08  jz      loc_180043D23
0x180043c0e  mov     eax, [rsp+268h+var_238]
0x180043c12  lea     r8, [rax+rax*2]
0x180043c16  shl     r8, 3; Size
0x180043c1a  xor     edx, edx; Val
0x180043c1c  call    memset_0
0x180043c21  xor     ebx, ebx
0x180043c23  cmp     [rsp+268h+var_238], ebx
0x180043c27  jbe     short loc_180043CA3
0x180043c29  mov     rax, [rsp+268h+var_228]
0x180043c2e  and     [rsp+268h+packageFamilyNameLength], 0
0x180043c33  and     [rsp+268h+packageRelativeApplicationIdLength], 0
0x180043c38  and     qword ptr [rsp+268h+var_248], 0
0x180043c3e  lea     r9, [rsp+268h+packageRelativeApplicationIdLength]; packageRelativeApplicationIdLength
0x180043c43  xor     r8d, r8d; packageFamilyName
0x180043c46  lea     rdx, [rsp+268h+packageFamilyNameLength]; packageFamilyNameLength
0x180043c4b  mov     rcx, [rax+rbx*8]; applicationUserModelId
0x180043c4f  call    cs:__imp_ParseApplicationUserModelId
0x180043c56  nop     dword ptr [rax+rax+00h]
0x180043c5b  cmp     eax, 7Ah ; 'z'
0x180043c5e  jnz     short loc_180043C97
0x180043c60  mov     eax, [rsi]
0x180043c62  lea     rcx, [rax+rax*2]
0x180043c66  mov     rax, [r14]
0x180043c69  lea     rdi, [rax+rcx*8]
0x180043c6d  mov     rdx, rdi; ppwsz
0x180043c70  mov     rcx, [rsp+268h+var_228]
0x180043c75  mov     rcx, [rcx+rbx*8]; psz
0x180043c79  call    cs:__imp_SHStrDupW
0x180043c80  nop     dword ptr [rax+rax+00h]
0x180043c85  test    eax, eax
0x180043c87  js      short loc_180043C97
0x180043c89  mov     dword ptr [rdi+8], 1
0x180043c90  and     qword ptr [rdi+10h], 0
0x180043c95  inc     dword ptr [rsi]
0x180043c97  inc     rbx
0x180043c9a  mov     eax, [rsp+268h+var_238]
0x180043c9e  cmp     rbx, rax
0x180043ca1  jb      short loc_180043C29
0x180043ca3  xor     edx, edx
0x180043ca5  lea     rcx, [rsp+268h+var_198]
0x180043cad  call    ?Stop@?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180043cb2  nop
0x180043cb3  lea     rcx, [rsp+268h+var_1F8]
0x180043cb8  call    wil__details__ScopeExitFn__lambda_acfd60c8a63b5138d0ae6bffd2ceb1de______ScopeExitFn__lambda_acfd60c8a63b5138d0ae6bffd2ceb1de___
0x180043cbd  nop
0x180043cbe  lea     rax, ??_7AllowServicing@DesktopAppXProvider@@6B@; const DesktopAppXProvider::AllowServicing::`vftable'
0x180043cc5  mov     [rsp+268h+var_198], rax
0x180043ccd  lea     rcx, [rsp+268h+var_198]
0x180043cd5  call    ?Destroy@?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180043cda  lea     rcx, [rsp+268h+var_198]
0x180043ce2  call    ??1?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180043ce7  xor     eax, eax
0x180043ce9  jmp     short loc_180043CEF
0x180043ceb  mov     eax, [rsp+268h+packageFamilyNameLength]
0x180043cef  mov     rcx, [rsp+268h+var_48]
0x180043cf7  xor     rcx, rsp; StackCookie
0x180043cfa  call    __security_check_cookie
0x180043cff  add     rsp, 238h
0x180043d06  pop     r15
0x180043d08  pop     r14
0x180043d0a  pop     r13
0x180043d0c  pop     rdi
0x180043d0d  pop     rsi
0x180043d0e  pop     rbx
0x180043d0f  retn
0x180043d11  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\execmodel\\des"...
0x180043d18  mov     edx, 1B1h; void *
0x180043d1d  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180043d23  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\execmodel\\des"...
0x180043d2a  mov     edx, 0E5h; void *
0x180043d2f  mov     rcx, rax; this
0x180043d32  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
