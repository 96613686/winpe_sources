# DSSRemoveExpiredTokens(void)

- ea: `0x18000d68c`
- end: `0x18000d7b1`
- name: `?DSSRemoveExpiredTokens@@YAJXZ`
- size: `293`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, service_task`

## callers

- `0x180007800`

## callees

- `0x180006f78`
- `0x18000bf80`
- `0x18000c558`
- `0x18000c758`
- `0x18000c95c`
- `0x18000d68c`
- `0x18000eacc`
- `0x18000f254`
- `0x18000f384`
- `0x18001213c`
- `0x18001686c`
- `0x180019720`
- `0x18001b340`

## string_xrefs

- `0x18000d6d2`: `Failed to remove expired tokens. hr=0x%x`
- `0x18000d6e3`: `DSSRemoveExpiredTokens`

## pseudocode

```c
__int64 DSSRemoveExpiredTokens(void)
{
  struct _FILETIME *v0; // rdx
  __int64 v1; // rcx
  __int64 v2; // r8
  __int64 v3; // r9
  int CurrentTimeAsFileTime; // ebx
  DSLogger *v5; // rax
  _DWORD *v7; // rdi
  unsigned int v8; // edi
  SharingTokenManager *v9; // rax
  int v10; // [rsp+20h] [rbp-198h]
  struct _FILETIME FileTime; // [rsp+30h] [rbp-188h] BYREF
  _BYTE v12[16]; // [rsp+38h] [rbp-180h] BYREF
  unsigned __int64 v13; // [rsp+48h] [rbp-170h]
  _BYTE v14[336]; // [rsp+50h] [rbp-168h] BYREF

  utl::list<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>::list<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&void tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>(v12);
  DataSharingServiceTelemetry::RemoveExpiredTokens::RemoveExpiredTokens((DataSharingServiceTelemetry::RemoveExpiredTokens *)v14);
  if ( dword_18002B2D0
    && (v7 = (_DWORD *)tlx::_LazyImpl<SharingTokenManager,tlx::lazy_construct<SharingTokenManager>,tlx::static_lazy<SharingTokenManager,0,tlx::lazy_construct<SharingTokenManager>>>::get(),
        FileTime = 0,
        *v7) )
  {
    CurrentTimeAsFileTime = DSUtils::GetCurrentTimeAsFileTime(&FileTime, v0);
    if ( CurrentTimeAsFileTime >= 0 )
      CurrentTimeAsFileTime = SharingTokenDatabase::GetExpiredTokens((SharingTokenDatabase *)(v7 + 2));
    if ( CurrentTimeAsFileTime >= 0 )
    {
      v8 = 0;
      if ( !v13 )
        goto LABEL_13;
      v8 = -1;
      if ( v13 <= 0xFFFFFFFF )
        v8 = v13;
      v9 = (SharingTokenManager *)tlx::_LazyImpl<SharingTokenManager,tlx::lazy_construct<SharingTokenManager>,tlx::static_lazy<SharingTokenManager,0,tlx::lazy_construct<SharingTokenManager>>>::get();
      CurrentTimeAsFileTime = SharingTokenManager::RemoveSharingTokens(v9);
      if ( CurrentTimeAsFileTime >= 0 )
      {
LABEL_13:
        DataSharingServiceTelemetry::RemoveExpiredTokens::Stop(
          (DataSharingServiceTelemetry::RemoveExpiredTokens *)v14,
          v8);
        goto LABEL_4;
      }
    }
  }
  else
  {
    CurrentTimeAsFileTime = -1055719422;
  }
  v5 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                     v1,
                     v0,
                     v2,
                     v3);
  v10 = CurrentTimeAsFileTime;
  DSLogger::LogError(v5, L"DSSRemoveExpiredTokens", 0x3DBu, L"Failed to remove expired tokens. hr=0x%x", v10);
LABEL_4:
  DataSharingServiceTelemetry::RemoveExpiredTokens::~RemoveExpiredTokens((DataSharingServiceTelemetry::RemoveExpiredTokens *)v14);
  utl::list<tlx::smart_ptr<SharingToken,&void tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingToken,&void tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>>>::clear(v12);
  return (unsigned int)CurrentTimeAsFileTime;
}

```

## disassembly

```asm
0x18000d68c  mov     [rsp+arg_0], rbx
0x18000d691  push    rdi
0x18000d692  sub     rsp, 1B0h
0x18000d699  mov     rax, cs:__security_cookie
0x18000d6a0  xor     rax, rsp
0x18000d6a3  mov     [rsp+1B8h+var_18], rax
0x18000d6ab  lea     rcx, [rsp+1B8h+var_180]
0x18000d6b0  call    ??0?$list@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@QEAA@XZ; utl::list<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>::list<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>>(void)
0x18000d6b5  lea     rcx, [rsp+1B8h+var_168]; this
0x18000d6ba  call    ??$?0$$V@RemoveExpiredTokens@DataSharingServiceTelemetry@@AEAA@U?$integral_constant@D$0A@@wistd@@@Z; DataSharingServiceTelemetry::RemoveExpiredTokens::RemoveExpiredTokens(wistd::integral_constant<char,0>)
0x18000d6bf  cmp     cs:dword_18002B2D0, 0
0x18000d6c6  jnz     short loc_18000D729
0x18000d6c8  mov     ebx, 0C1130002h
0x18000d6cd  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000d6d2  lea     r9, aFailedToRemove; "Failed to remove expired tokens. hr=0x%"...
0x18000d6d9  mov     [rsp+1B8h+var_198], ebx
0x18000d6dd  mov     r8d, 3DBh; unsigned int
0x18000d6e3  lea     rdx, aDssremoveexpir_1; "DSSRemoveExpiredTokens"
0x18000d6ea  mov     rcx, rax; this
0x18000d6ed  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18000d6f2  lea     rcx, [rsp+1B8h+var_168]; this
0x18000d6f7  call    ??1RemoveExpiredTokens@DataSharingServiceTelemetry@@QEAA@XZ; DataSharingServiceTelemetry::RemoveExpiredTokens::~RemoveExpiredTokens(void)
0x18000d6fc  lea     rcx, [rsp+1B8h+var_180]
0x18000d701  call    ?clear@?$list@V?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@QEAAXXZ; utl::list<tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>>>::clear(void)
0x18000d706  mov     eax, ebx
0x18000d708  mov     rcx, [rsp+1B8h+var_18]
0x18000d710  xor     rcx, rsp; StackCookie
0x18000d713  call    __security_check_cookie
0x18000d718  mov     rbx, [rsp+1B8h+arg_0]
0x18000d720  add     rsp, 1B0h
0x18000d727  pop     rdi
0x18000d728  retn
0x18000d729  call    ?get@?$_LazyImpl@VSharingTokenManager@@V?$lazy_construct@VSharingTokenManager@@@tlx@@V?$static_lazy@VSharingTokenManager@@$0A@V?$lazy_construct@VSharingTokenManager@@@tlx@@@3@@tlx@@QEAAAEAVSharingTokenManager@@XZ; tlx::_LazyImpl<SharingTokenManager,tlx::lazy_construct<SharingTokenManager>,tlx::static_lazy<SharingTokenManager,0,tlx::lazy_construct<SharingTokenManager>>>::get(void)
0x18000d72e  mov     rdi, rax
0x18000d731  mov     qword ptr [rsp+1B8h+FileTime.dwLowDateTime], 0
0x18000d73a  cmp     dword ptr [rax], 0
0x18000d73d  jz      short loc_18000D6C8
0x18000d73f  lea     rcx, [rsp+1B8h+FileTime]; lpFileTime
0x18000d744  call    ?GetCurrentTimeAsFileTime@DSUtils@@YAJPEAU_FILETIME@@@Z; DSUtils::GetCurrentTimeAsFileTime(_FILETIME *)
0x18000d749  mov     ebx, eax
0x18000d74b  test    eax, eax
0x18000d74d  js      short loc_18000D764
0x18000d74f  mov     rdx, qword ptr [rsp+1B8h+FileTime.dwLowDateTime]
0x18000d754  lea     rcx, [rdi+8]; this
0x18000d758  lea     r8, [rsp+1B8h+var_180]
0x18000d75d  call    ?GetExpiredTokens@SharingTokenDatabase@@QEAAJU_FILETIME@@AEAV?$list@V?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@@Z; SharingTokenDatabase::GetExpiredTokens(_FILETIME,utl::list<tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>>> &)
0x18000d762  mov     ebx, eax
0x18000d764  test    ebx, ebx
0x18000d766  js      loc_18000D6CD
0x18000d76c  mov     rax, [rsp+1B8h+var_170]
0x18000d771  xor     edi, edi
0x18000d773  test    rax, rax
0x18000d776  jz      short loc_18000D7A0
0x18000d778  mov     edi, 0FFFFFFFFh
0x18000d77d  cmp     rax, rdi
0x18000d780  ja      short loc_18000D784
0x18000d782  mov     edi, eax
0x18000d784  call    ?get@?$_LazyImpl@VSharingTokenManager@@V?$lazy_construct@VSharingTokenManager@@@tlx@@V?$static_lazy@VSharingTokenManager@@$0A@V?$lazy_construct@VSharingTokenManager@@@tlx@@@3@@tlx@@QEAAAEAVSharingTokenManager@@XZ; tlx::_LazyImpl<SharingTokenManager,tlx::lazy_construct<SharingTokenManager>,tlx::static_lazy<SharingTokenManager,0,tlx::lazy_construct<SharingTokenManager>>>::get(void)
0x18000d789  lea     rdx, [rsp+1B8h+var_180]
0x18000d78e  mov     rcx, rax; this
0x18000d791  call    ?RemoveSharingTokens@SharingTokenManager@@QEAAJAEAV?$list@V?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingToken@@$1??$_delete@VSharingToken@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@@Z; SharingTokenManager::RemoveSharingTokens(utl::list<tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingToken,&tlx::_delete<SharingToken>(SharingToken *),utl::allocator<int>>>> &)
0x18000d796  mov     ebx, eax
0x18000d798  test    eax, eax
0x18000d79a  js      loc_18000D6CD
0x18000d7a0  mov     edx, edi; unsigned int
0x18000d7a2  lea     rcx, [rsp+1B8h+var_168]; this
0x18000d7a7  call    ?Stop@RemoveExpiredTokens@DataSharingServiceTelemetry@@QEAAXI@Z; DataSharingServiceTelemetry::RemoveExpiredTokens::Stop(uint)
0x18000d7ac  jmp     loc_18000D6F2
```
