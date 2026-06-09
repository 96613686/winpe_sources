# CentennialLifetimeManager::AllowServicing(ushort const * *,ulong,ushort const * *,ulong,int,int,ushort * * *,ulong *,SERVICING_TERMINATION_INFO * *,ulong *)

- ea: `0x1800455b0`
- end: `0x180045a1d`
- name: `?AllowServicing@CentennialLifetimeManager@@UEAAJPEAPEBGK0KHHPEAPEAPEAGPEAKPEAPEAUSERVICING_TERMINATION_INFO@@2@Z`
- size: `1133`
- prototype: `__int64 __fastcall(CentennialLifetimeManager *__hidden this, const unsigned __int16 **, unsigned int, const unsigned __int16 **, unsigned int, int, int, unsigned __int16 ***, unsigned int *, struct SERVICING_TERMINATION_INFO **, unsigned int *)`
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180004f70`
- `0x1800059a8`
- `0x1800164f8`
- `0x180016b98`
- `0x1800190e0`
- `0x18001f808`
- `0x180035e2c`
- `0x180038de8`
- `0x180038e70`
- `0x180038f88`
- `0x1800417a8`
- `0x180044484`
- `0x180044c90`
- `0x1800455b0`
- `0x180048f64`
- `0x180049374`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180045708`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800458b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180045708`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800458b6`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18004576e`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180045956`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x18004576e`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x180045956`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x18004592c`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x18004592c`

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
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  const char *v28; // r9
  __int64 result; // rax
  __int64 v30; // rbx
  struct SERVICING_TERMINATION_INFO *v31; // rcx
  const char *v32; // r9
  struct SERVICING_TERMINATION_INFO **v33; // r14
  unsigned __int64 i; // rbx
  __int64 v35; // rdi
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  int packageRelativeApplicationId; // [rsp+20h] [rbp-248h]
  unsigned int v40; // [rsp+30h] [rbp-238h] BYREF
  UINT32 packageFamilyNameLength[2]; // [rsp+38h] [rbp-230h] BYREF
  unsigned __int16 **v42; // [rsp+40h] [rbp-228h] BYREF
  UINT32 packageRelativeApplicationIdLength[2]; // [rsp+48h] [rbp-220h] BYREF
  unsigned __int16 ***v44; // [rsp+50h] [rbp-218h] BYREF
  struct SERVICING_TERMINATION_INFO **v45; // [rsp+58h] [rbp-210h]
  _QWORD v46[2]; // [rsp+60h] [rbp-208h] BYREF
  _QWORD v47[3]; // [rsp+70h] [rbp-1F8h] BYREF
  char v48; // [rsp+88h] [rbp-1E0h]
  char v49[8]; // [rsp+90h] [rbp-1D8h] BYREF
  _QWORD *v50; // [rsp+98h] [rbp-1D0h] BYREF
  __int64 v51; // [rsp+A0h] [rbp-1C8h]
  char v52[40]; // [rsp+A8h] [rbp-1C0h] BYREF
  _QWORD v53[42]; // [rsp+D0h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+0h]

  *(_QWORD *)packageRelativeApplicationIdLength = a4;
  v11 = a3;
  *(_QWORD *)packageFamilyNameLength = a2;
  v44 = a8;
  v45 = a10;
  v13 = a3 + a5;
  wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v53,
    "AllowServicing");
  v53[0] = &DesktopAppXProvider::AllowServicing::`vftable';
  try
  {
    DesktopAppXProvider::AllowServicing::StartActivity((DesktopAppXProvider::AllowServicing *)v53, v13, a6);
    v14 = 0;
    *a11 = 0;
    *a10 = 0;
    *a9 = 0;
    if ( v44 )
      *v44 = 0;
    v47[0] = &v42;
    v47[1] = &v40;
    v47[2] = &v44;
    v48 = 1;
    v42 = 0;
    v40 = 0;
    std::unordered_set<std::wstring>::unordered_set<std::wstring>(v49);
    v15 = (CentennialLifetimeManager *)((char *)this - 152);
    v46[0] = (char *)this - 152;
    v46[1] = v49;
    v16 = a5;
    lambda_1d46f3311b4a979ff36b016456cb2094_::operator()(v46, a5, *(_QWORD *)packageRelativeApplicationIdLength);
    lambda_1d46f3311b4a979ff36b016456cb2094_::operator()(v46, v11, *(_QWORD *)packageFamilyNameLength);
    if ( v51 )
    {
      v40 = v51;
      v17 = (unsigned __int16 **)CoTaskMemAlloc(8LL * (unsigned int)v51);
      v42 = v17;
      if ( !v17 )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0x1B1,
          (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\centenniallifetimemanager.cpp",
          v18);
      memset_0(v17, 0, 8LL * v40);
      v19 = 0;
      v20 = v50;
      v21 = (_QWORD *)*v50;
      while ( v21 != v20 && v19 < v40 )
      {
        v22 = (const WCHAR *)(v21 + 2);
        if ( v21[5] > 7u )
          v22 = *(const WCHAR **)v22;
        v23 = SHStrDupW(v22, &v42[v19]);
        if ( v23 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1B9,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\centenniallifetimemanager.cpp",
            (const char *)(unsigned int)v23,
            packageRelativeApplicationId);
        v21 = (_QWORD *)*v21;
        ++v19;
        v20 = v50;
      }
      v14 = 0;
      v16 = a5;
    }
    std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(v52);
    std::list<std::wstring>::~list<std::wstring>(&v50);
    v24 = v40;
    *a9 = v40;
    if ( v44 )
    {
      *v44 = v42;
      v48 = 0;
      v24 = v40;
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
        v24 = v40;
      }
      v30 = 0;
      while ( (unsigned int)v30 < v16 )
      {
        CentennialLifetimeManager::ShutdownPackage(
          v15,
          *(const unsigned __int16 **)(*(_QWORD *)packageRelativeApplicationIdLength + 8 * v30),
          0,
          a7 != 0);
        v30 = (unsigned int)(v30 + 1);
        v24 = v40;
      }
      if ( (_DWORD)v24 )
      {
        v31 = (struct SERVICING_TERMINATION_INFO *)CoTaskMemAlloc(24 * v24);
        v33 = v45;
        *v45 = v31;
        if ( !v31 )
          wil::details::in1diag3::_Throw_NullAlloc(
            retaddr,
            (void *)0xE5,
            (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\centenniallifetimemanager.cpp",
            v32);
        memset_0(v31, 0, 24LL * v40);
        for ( i = 0; i < v40; ++i )
        {
          packageFamilyNameLength[0] = 0;
          packageRelativeApplicationIdLength[0] = 0;
          if ( ParseApplicationUserModelId(v42[i], packageFamilyNameLength, 0, packageRelativeApplicationIdLength, 0) == 122 )
          {
            v35 = (__int64)*v33 + 24 * *a11;
            if ( SHStrDupW(v42[i], (LPWSTR *)v35) >= 0 )
            {
              *(_DWORD *)(v35 + 8) = 1;
              *(_QWORD *)(v35 + 16) = 0;
              ++*a11;
            }
          }
        }
      }
      wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v53, 0);
      wil::details::ScopeExitFn__lambda_acfd60c8a63b5138d0ae6bffd2ceb1de___::_ScopeExitFn__lambda_acfd60c8a63b5138d0ae6bffd2ceb1de___(v47);
      v53[0] = &DesktopAppXProvider::AllowServicing::`vftable';
      wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v53, v36, v37, v38);
      wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v53);
      result = 0;
    }
    else
    {
      wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v53, 0);
      wil::details::ScopeExitFn__lambda_acfd60c8a63b5138d0ae6bffd2ceb1de___::_ScopeExitFn__lambda_acfd60c8a63b5138d0ae6bffd2ceb1de___(v47);
      v53[0] = &DesktopAppXProvider::AllowServicing::`vftable';
      wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v53, v25, v26, v27);
      wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v53);
      result = 2147500036LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xFF,
                           (unsigned int)"onecore\\base\\appmodel\\execmodel\\desktopappx\\lib\\centenniallifetimemanager.cpp",
                           v28);
  }
  return result;
}

```

## disassembly

```asm
0x1800455b0  push    rbx
0x1800455b2  push    rsi
0x1800455b3  push    rdi
0x1800455b4  push    r13
0x1800455b6  push    r14
0x1800455b8  push    r15
0x1800455ba  sub     rsp, 238h
0x1800455c1  mov     rax, cs:__security_cookie
0x1800455c8  xor     rax, rsp
0x1800455cb  mov     [rsp+268h+var_48], rax
0x1800455d3  mov     qword ptr [rsp+268h+packageRelativeApplicationIdLength], r9
0x1800455d8  mov     r14d, r8d
0x1800455db  mov     qword ptr [rsp+268h+packageFamilyNameLength], rdx
0x1800455e0  mov     rdi, rcx
0x1800455e3  mov     rax, [rsp+268h+arg_38]
0x1800455eb  mov     [rsp+268h+var_218], rax
0x1800455f0  mov     r15, [rsp+268h+arg_40]
0x1800455f8  mov     r13, [rsp+268h+arg_48]
0x180045600  mov     [rsp+268h+var_210], r13
0x180045605  mov     rsi, [rsp+268h+arg_50]
0x18004560d  mov     ebx, [rsp+268h+arg_20]
0x180045614  add     ebx, r14d
0x180045617  lea     rdx, aAllowservicing; "AllowServicing"
0x18004561e  lea     rcx, [rsp+268h+var_198]
0x180045626  call    ??0?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18004562b  lea     rax, ??_7AllowServicing@DesktopAppXProvider@@6B@; const DesktopAppXProvider::AllowServicing::`vftable'
0x180045632  mov     [rsp+268h+var_198], rax
0x18004563a  mov     r8d, [rsp+268h+arg_28]; int
0x180045642  mov     edx, ebx; int
0x180045644  lea     rcx, [rsp+268h+var_198]; this
0x18004564c  call    ?StartActivity@AllowServicing@DesktopAppXProvider@@QEAAXHH@Z; DesktopAppXProvider::AllowServicing::StartActivity(int,int)
0x180045651  nop
0x180045652  xor     ebx, ebx
0x180045654  mov     [rsi], ebx
0x180045656  mov     [r13+0], rbx
0x18004565a  mov     [r15], ebx
0x18004565d  mov     rax, [rsp+268h+var_218]
0x180045662  test    rax, rax
0x180045665  jz      short loc_18004566A
0x180045667  mov     [rax], rbx
0x18004566a  lea     rax, [rsp+268h+var_228]
0x18004566f  mov     [rsp+268h+var_1F8], rax
0x180045674  lea     rax, [rsp+268h+var_238]
0x180045679  mov     [rsp+268h+var_1F0], rax
0x18004567e  lea     rax, [rsp+268h+var_218]
0x180045683  mov     [rsp+268h+var_1E8], rax
0x18004568b  mov     [rsp+268h+var_1E0], 1
0x180045693  mov     [rsp+268h+var_228], rbx
0x180045698  mov     [rsp+268h+var_238], ebx
0x18004569c  lea     rcx, [rsp+268h+var_1D8]
0x1800456a4  call    ??0?$unordered_set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::unordered_set<std::wstring>::unordered_set<std::wstring>(void)
0x1800456a9  nop
0x1800456aa  lea     r13, [rdi-98h]
0x1800456b1  mov     [rsp+268h+var_208], r13
0x1800456b6  lea     rax, [rsp+268h+var_1D8]
0x1800456be  mov     [rsp+268h+var_200], rax
0x1800456c3  mov     edi, [rsp+268h+arg_20]
0x1800456ca  mov     edx, edi
0x1800456cc  mov     r8, qword ptr [rsp+268h+packageRelativeApplicationIdLength]
0x1800456d1  lea     rcx, [rsp+268h+var_208]
0x1800456d6  call    _lambda_1d46f3311b4a979ff36b016456cb2094___operator__
0x1800456db  mov     rdx, r14
0x1800456de  mov     r8, qword ptr [rsp+268h+packageFamilyNameLength]
0x1800456e3  lea     rcx, [rsp+268h+var_208]
0x1800456e8  call    _lambda_1d46f3311b4a979ff36b016456cb2094___operator__
0x1800456ed  mov     rax, [rsp+268h+var_1C8]
0x1800456f5  test    rax, rax
0x1800456f8  jz      loc_1800457B2
0x1800456fe  mov     ecx, eax
0x180045700  mov     [rsp+268h+var_238], ecx
0x180045704  shl     rcx, 3; cb
0x180045708  call    cs:__imp_CoTaskMemAlloc
0x18004570f  nop     dword ptr [rax+rax+00h]
0x180045714  mov     [rsp+268h+var_228], rax
0x180045719  mov     rcx, [rsp+268h]; this
0x180045721  test    rax, rax
0x180045724  jz      loc_1800459F5
0x18004572a  mov     r8d, [rsp+268h+var_238]
0x18004572f  shl     r8, 3; Size
0x180045733  xor     edx, edx; Val
0x180045735  mov     rcx, rax; void *
0x180045738  call    memset_0
0x18004573d  mov     edi, ebx
0x18004573f  mov     rax, [rsp+268h+var_1D0]
0x180045747  mov     rbx, [rax]
0x18004574a  cmp     rbx, rax
0x18004574d  jz      short loc_1800457A9
0x18004574f  cmp     edi, [rsp+268h+var_238]
0x180045753  jnb     short loc_1800457A9
0x180045755  mov     ecx, edi
0x180045757  mov     rax, [rsp+268h+var_228]
0x18004575c  lea     rdx, [rax+rcx*8]; ppwsz
0x180045760  lea     rcx, [rbx+10h]
0x180045764  cmp     qword ptr [rbx+28h], 7
0x180045769  jbe     short loc_18004576E
0x18004576b  mov     rcx, [rcx]; psz
0x18004576e  call    cs:__imp_SHStrDupW
0x180045775  nop     dword ptr [rax+rax+00h]
0x18004577a  test    eax, eax
0x18004577c  jns     short loc_18004579A
0x18004577e  mov     rcx, [rsp+268h]; this
0x180045786  mov     r9d, eax; char *
0x180045789  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\execmodel\\des"...
0x180045790  mov     edx, 1B9h; void *
0x180045795  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004579a  mov     rbx, [rbx]
0x18004579d  inc     edi
0x18004579f  mov     rax, [rsp+268h+var_1D0]
0x1800457a7  jmp     short loc_18004574A
0x1800457a9  xor     ebx, ebx
0x1800457ab  mov     edi, [rsp+268h+arg_20]
0x1800457b2  lea     rcx, [rsp+268h+var_1C0]
0x1800457ba  call    ??1?$_Hash_vec@V?$allocator@V?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@U_Iterator_base0@2@@std@@@std@@@std@@QEAA@XZ; std::_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>::~_Hash_vec<std::allocator<std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<std::wstring>>,std::_Iterator_base0>>>(void)
0x1800457bf  lea     rcx, [rsp+268h+var_1D0]
0x1800457c7  call    ??1?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::list<std::wstring>::~list<std::wstring>(void)
0x1800457cc  mov     eax, [rsp+268h+var_238]
0x1800457d0  mov     [r15], eax
0x1800457d3  mov     rcx, [rsp+268h+var_218]
0x1800457d8  test    rcx, rcx
0x1800457db  jz      short loc_1800457F0
0x1800457dd  mov     rax, [rsp+268h+var_228]
0x1800457e2  mov     [rcx], rax
0x1800457e5  mov     [rsp+268h+var_1E0], bl
0x1800457ec  mov     eax, [rsp+268h+var_238]
0x1800457f0  cmp     [rsp+268h+arg_28], ebx
0x1800457f7  jnz     short loc_18004584B
0x1800457f9  test    eax, eax
0x1800457fb  jz      short loc_18004584B
0x1800457fd  xor     edx, edx
0x1800457ff  lea     rcx, [rsp+268h+var_198]
0x180045807  call    ?Stop@?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x18004580c  nop
0x18004580d  lea     rcx, [rsp+268h+var_1F8]
0x180045812  call    wil__details__ScopeExitFn__lambda_acfd60c8a63b5138d0ae6bffd2ceb1de______ScopeExitFn__lambda_acfd60c8a63b5138d0ae6bffd2ceb1de___
0x180045817  nop
0x180045818  lea     rax, ??_7AllowServicing@DesktopAppXProvider@@6B@; const DesktopAppXProvider::AllowServicing::`vftable'
0x18004581f  mov     [rsp+268h+var_198], rax
0x180045827  lea     rcx, [rsp+268h+var_198]
0x18004582f  call    ?Destroy@?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180045834  lea     rcx, [rsp+268h+var_198]
0x18004583c  call    ??1?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180045841  mov     eax, 80004004h
0x180045846  jmp     loc_1800459D3
0x18004584b  mov     r15d, [rsp+268h+arg_30]
0x180045853  cmp     ebx, r14d
0x180045856  jnb     short loc_18004587D
0x180045858  test    r15d, r15d
0x18004585b  setnz   r9b; bool
0x18004585f  mov     edx, ebx
0x180045861  xor     r8d, r8d; bool
0x180045864  mov     rax, qword ptr [rsp+268h+packageFamilyNameLength]
0x180045869  mov     rdx, [rax+rdx*8]; unsigned __int16 *
0x18004586d  mov     rcx, r13; this
0x180045870  call    ?ShutdownPackage@CentennialLifetimeManager@@AEAAXPEBG_N1@Z; CentennialLifetimeManager::ShutdownPackage(ushort const *,bool,bool)
0x180045875  inc     ebx
0x180045877  mov     eax, [rsp+268h+var_238]
0x18004587b  jmp     short loc_180045853
0x18004587d  xor     ebx, ebx
0x18004587f  cmp     ebx, edi
0x180045881  jnb     short loc_1800458A6
0x180045883  test    r15d, r15d
0x180045886  setnz   r9b; bool
0x18004588a  xor     r8d, r8d; bool
0x18004588d  mov     rax, qword ptr [rsp+268h+packageRelativeApplicationIdLength]
0x180045892  mov     rdx, [rax+rbx*8]; unsigned __int16 *
0x180045896  mov     rcx, r13; this
0x180045899  call    ?ShutdownPackage@CentennialLifetimeManager@@AEAAXPEBG_N1@Z; CentennialLifetimeManager::ShutdownPackage(ushort const *,bool,bool)
0x18004589e  inc     ebx
0x1800458a0  mov     eax, [rsp+268h+var_238]
0x1800458a4  jmp     short loc_18004587F
0x1800458a6  test    eax, eax
0x1800458a8  jz      loc_180045987
0x1800458ae  lea     rcx, [rax+rax*2]
0x1800458b2  shl     rcx, 3; cb
0x1800458b6  call    cs:__imp_CoTaskMemAlloc
0x1800458bd  nop     dword ptr [rax+rax+00h]
0x1800458c2  mov     rcx, rax; void *
0x1800458c5  mov     r14, [rsp+268h+var_210]
0x1800458ca  mov     [r14], rax
0x1800458cd  mov     rax, [rsp+268h]
0x1800458d5  test    rcx, rcx
0x1800458d8  jz      loc_180045A07
0x1800458de  mov     eax, [rsp+268h+var_238]
0x1800458e2  lea     r8, [rax+rax*2]
0x1800458e6  shl     r8, 3; Size
0x1800458ea  xor     edx, edx; Val
0x1800458ec  call    memset_0
0x1800458f1  xor     ebx, ebx
0x1800458f3  cmp     [rsp+268h+var_238], ebx
0x1800458f7  jbe     loc_180045987
0x1800458fd  mov     [rsp+268h+packageFamilyNameLength], 0
0x180045905  mov     [rsp+268h+packageRelativeApplicationIdLength], 0
0x18004590d  mov     qword ptr [rsp+268h+packageRelativeApplicationId], 0; packageRelativeApplicationId
0x180045916  lea     r9, [rsp+268h+packageRelativeApplicationIdLength]; packageRelativeApplicationIdLength
0x18004591b  xor     r8d, r8d; packageFamilyName
0x18004591e  lea     rdx, [rsp+268h+packageFamilyNameLength]; packageFamilyNameLength
0x180045923  mov     rcx, [rsp+268h+var_228]
0x180045928  mov     rcx, [rcx+rbx*8]; applicationUserModelId
0x18004592c  call    cs:__imp_ParseApplicationUserModelId
0x180045933  nop     dword ptr [rax+rax+00h]
0x180045938  cmp     eax, 7Ah ; 'z'
0x18004593b  jnz     short loc_180045977
0x18004593d  mov     eax, [rsi]
0x18004593f  lea     rcx, [rax+rax*2]
0x180045943  mov     rax, [r14]
0x180045946  lea     rdi, [rax+rcx*8]
0x18004594a  mov     rdx, rdi; ppwsz
0x18004594d  mov     rcx, [rsp+268h+var_228]
0x180045952  mov     rcx, [rcx+rbx*8]; psz
0x180045956  call    cs:__imp_SHStrDupW
0x18004595d  nop     dword ptr [rax+rax+00h]
0x180045962  test    eax, eax
0x180045964  js      short loc_180045977
0x180045966  mov     dword ptr [rdi+8], 1
0x18004596d  mov     qword ptr [rdi+10h], 0
0x180045975  inc     dword ptr [rsi]
0x180045977  inc     rbx
0x18004597a  mov     eax, [rsp+268h+var_238]
0x18004597e  cmp     rbx, rax
0x180045981  jb      loc_1800458FD
0x180045987  xor     edx, edx
0x180045989  lea     rcx, [rsp+268h+var_198]
0x180045991  call    ?Stop@?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180045996  nop
0x180045997  lea     rcx, [rsp+268h+var_1F8]
0x18004599c  call    wil__details__ScopeExitFn__lambda_acfd60c8a63b5138d0ae6bffd2ceb1de______ScopeExitFn__lambda_acfd60c8a63b5138d0ae6bffd2ceb1de___
0x1800459a1  nop
0x1800459a2  lea     rax, ??_7AllowServicing@DesktopAppXProvider@@6B@; const DesktopAppXProvider::AllowServicing::`vftable'
0x1800459a9  mov     [rsp+268h+var_198], rax
0x1800459b1  lea     rcx, [rsp+268h+var_198]
0x1800459b9  call    ?Destroy@?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800459be  lea     rcx, [rsp+268h+var_198]
0x1800459c6  call    ??1?$ActivityBase@VDesktopAppXProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<DesktopAppXProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800459cb  xor     eax, eax
0x1800459cd  jmp     short loc_1800459D3
0x1800459cf  mov     eax, [rsp+268h+packageFamilyNameLength]
0x1800459d3  mov     rcx, [rsp+268h+var_48]
0x1800459db  xor     rcx, rsp; StackCookie
0x1800459de  call    __security_check_cookie
0x1800459e3  add     rsp, 238h
0x1800459ea  pop     r15
0x1800459ec  pop     r14
0x1800459ee  pop     r13
0x1800459f0  pop     rdi
0x1800459f1  pop     rsi
0x1800459f2  pop     rbx
0x1800459f3  retn
0x1800459f5  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\execmodel\\des"...
0x1800459fc  mov     edx, 1B1h; void *
0x180045a01  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180045a07  lea     r8, aOnecoreBaseApp_1; "onecore\\base\\appmodel\\execmodel\\des"...
0x180045a0e  mov     edx, 0E5h; void *
0x180045a13  mov     rcx, rax; this
0x180045a16  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
