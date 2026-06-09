# DSSDelegateSharingToken(ushort const *,_DS_SHARE_SCOPE const *)

- ea: `0x18000ceb4`
- end: `0x18000cfc4`
- name: `?DSSDelegateSharingToken@@YAJPEBGPEBU_DS_SHARE_SCOPE@@@Z`
- size: `272`
- prototype: `__int64 __fastcall(unsigned __int16 *, const struct _DS_SHARE_SCOPE *)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180007440`

## callees

- `0x180006f78`
- `0x18000bf80`
- `0x18000c758`
- `0x18000ceb4`
- `0x18000da68`
- `0x18000e364`
- `0x18000f068`
- `0x18000f120`
- `0x18000f218`
- `0x18000f384`
- `0x18000fbfc`
- `0x180012310`

## string_xrefs

- `0x18000cf74`: `Failed to delegate token: %s. hr=0x%x`
- `0x18000cf8a`: `DSSDelegateSharingToken`

## pseudocode

```c
__int64 __fastcall DSSDelegateSharingToken(unsigned __int16 *a1, const struct _DS_SHARE_SCOPE *a2)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  int AuthorizedSharingToken; // ebx
  struct SharingToken *v9; // rdi
  SharingTokenManager *v10; // rax
  DSLogger *v11; // rax
  __int128 v13; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v14[40]; // [rsp+40h] [rbp-28h] BYREF
  int v15; // [rsp+80h] [rbp+18h] BYREF

  v13 = 0;
  utl::list<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>::list<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>(v14);
  if ( !dword_18002B2D0 )
  {
    AuthorizedSharingToken = -1055719422;
LABEL_8:
    v11 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                        v5,
                        v4,
                        v6,
                        v7);
    DSLogger::LogError(
      v11,
      L"DSSDelegateSharingToken",
      0x2A4u,
      L"Failed to delegate token: %s. hr=0x%x",
      a1,
      AuthorizedSharingToken);
    goto LABEL_9;
  }
  AuthorizedSharingToken = GetAuthorizedSharingToken(a1);
  if ( AuthorizedSharingToken < 0 )
    goto LABEL_8;
  v15 = 1;
  AuthorizedSharingToken = ValidateUsage(&v13, &v15);
  if ( AuthorizedSharingToken < 0 )
    goto LABEL_8;
  AuthorizedSharingToken = ResolveTargets(v5, (int *)a2, (__int64)v14);
  if ( AuthorizedSharingToken < 0 )
    goto LABEL_8;
  v9 = (struct SharingToken *)v13;
  AuthorizedSharingToken = ShareAccessControl::InitializeScope(v13 + 120, v14);
  if ( AuthorizedSharingToken < 0 )
    goto LABEL_8;
  *((_DWORD *)v9 + 20) = 0;
  v10 = (SharingTokenManager *)tlx::_LazyImpl<SharingTokenManager,tlx::lazy_construct<SharingTokenManager>,tlx::static_lazy<SharingTokenManager,0,tlx::lazy_construct<SharingTokenManager>>>::get();
  AuthorizedSharingToken = SharingTokenManager::UpdateSharingToken(v10, v9);
  if ( AuthorizedSharingToken < 0 )
    goto LABEL_8;
LABEL_9:
  utl::list<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>::clear(v14);
  if ( *((_QWORD *)&v13 + 1) )
    utl::_RefCountBase::_DecStrong(*((utl::_RefCountBase **)&v13 + 1));
  return (unsigned int)AuthorizedSharingToken;
}

```

## disassembly

```asm
0x18000ceb4  mov     rax, rsp
0x18000ceb7  mov     [rax+8], rbx
0x18000cebb  mov     [rax+10h], rsi
0x18000cebf  push    rdi
0x18000cec0  sub     rsp, 60h
0x18000cec4  mov     rsi, rcx
0x18000cec7  xorps   xmm0, xmm0
0x18000ceca  lea     rcx, [rax-28h]
0x18000cece  mov     rdi, rdx
0x18000ced1  movdqu  xmmword ptr [rax-38h], xmm0
0x18000ced6  call    ??0?$list@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@QEAA@XZ; utl::list<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>::list<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>(void)
0x18000cedb  cmp     cs:dword_18002B2D0, 0
0x18000cee2  jnz     short loc_18000CEEE
0x18000cee4  mov     ebx, 0C1130002h
0x18000cee9  jmp     loc_18000CF6F
0x18000ceee  lea     r8, [rsp+68h+var_38]
0x18000cef3  xor     edx, edx
0x18000cef5  mov     rcx, rsi; unsigned __int16 *
0x18000cef8  call    GetAuthorizedSharingToken
0x18000cefd  mov     ebx, eax
0x18000ceff  test    eax, eax
0x18000cf01  js      short loc_18000CF6F
0x18000cf03  lea     rdx, [rsp+68h+arg_10]
0x18000cf0b  mov     [rsp+68h+arg_10], 1
0x18000cf16  lea     rcx, [rsp+68h+var_38]
0x18000cf1b  call    ValidateUsage
0x18000cf20  mov     ebx, eax
0x18000cf22  test    eax, eax
0x18000cf24  js      short loc_18000CF6F
0x18000cf26  lea     r8, [rsp+68h+var_28]
0x18000cf2b  mov     rdx, rdi
0x18000cf2e  call    ResolveTargets
0x18000cf33  mov     ebx, eax
0x18000cf35  test    eax, eax
0x18000cf37  js      short loc_18000CF6F
0x18000cf39  mov     rdi, [rsp+68h+var_38]
0x18000cf3e  lea     rdx, [rsp+68h+var_28]
0x18000cf43  lea     rcx, [rdi+78h]
0x18000cf47  call    ?InitializeScope@ShareAccessControl@@QEAAJAEBV?$list@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@@Z; ShareAccessControl::InitializeScope(utl::list<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>> const &)
0x18000cf4c  mov     ebx, eax
0x18000cf4e  test    eax, eax
0x18000cf50  js      short loc_18000CF6F
0x18000cf52  mov     dword ptr [rdi+50h], 0
0x18000cf59  call    ?get@?$_LazyImpl@VSharingTokenManager@@V?$lazy_construct@VSharingTokenManager@@@tlx@@V?$static_lazy@VSharingTokenManager@@$0A@V?$lazy_construct@VSharingTokenManager@@@tlx@@@3@@tlx@@QEAAAEAVSharingTokenManager@@XZ; tlx::_LazyImpl<SharingTokenManager,tlx::lazy_construct<SharingTokenManager>,tlx::static_lazy<SharingTokenManager,0,tlx::lazy_construct<SharingTokenManager>>>::get(void)
0x18000cf5e  mov     rdx, rdi; struct SharingToken *
0x18000cf61  mov     rcx, rax; this
0x18000cf64  call    ?UpdateSharingToken@SharingTokenManager@@QEAAJPEAVSharingToken@@@Z; SharingTokenManager::UpdateSharingToken(SharingToken *)
0x18000cf69  mov     ebx, eax
0x18000cf6b  test    eax, eax
0x18000cf6d  jns     short loc_18000CF99
0x18000cf6f  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000cf74  lea     r9, aFailedToDelega; "Failed to delegate token: %s. hr=0x%x"
0x18000cf7b  mov     [rsp+68h+var_40], ebx
0x18000cf7f  mov     r8d, 2A4h; unsigned int
0x18000cf85  mov     [rsp+68h+var_48], rsi
0x18000cf8a  lea     rdx, aDssdelegatesha_0; "DSSDelegateSharingToken"
0x18000cf91  mov     rcx, rax; this
0x18000cf94  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18000cf99  lea     rcx, [rsp+68h+var_28]
0x18000cf9e  call    ?clear@?$list@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@QEAAXXZ; utl::list<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>::clear(void)
0x18000cfa3  mov     rcx, [rsp+68h+var_30]; this
0x18000cfa8  test    rcx, rcx
0x18000cfab  jz      short loc_18000CFB2
0x18000cfad  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18000cfb2  mov     rsi, [rsp+68h+arg_8]
0x18000cfb7  mov     eax, ebx
0x18000cfb9  mov     rbx, [rsp+68h+arg_0]
0x18000cfbe  add     rsp, 60h
0x18000cfc2  pop     rdi
0x18000cfc3  retn
```
