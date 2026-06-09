# DSSRemoveSharingToken(ushort const *)

- ea: `0x18000d7b8`
- end: `0x18000d857`
- name: `?DSSRemoveSharingToken@@YAJPEBG@Z`
- size: `159`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180007870`

## callees

- `0x180006f78`
- `0x18000bf80`
- `0x18000d7b8`
- `0x18000da68`
- `0x18000f120`
- `0x18000f384`
- `0x1800120ac`

## string_xrefs

- `0x18000d816`: `Failed to remove token: %s. hr=0x%x`
- `0x18000d82c`: `DSSRemoveSharingToken`

## pseudocode

```c
__int64 __fastcall DSSRemoveSharingToken(unsigned __int16 *a1, __int64 a2, __int64 a3, __int64 a4)
{
  int AuthorizedSharingToken; // ebx
  SharingTokenManager *v6; // rax
  __int64 v7; // r9
  DSLogger *v8; // rax
  utl::_RefCountBase *v10[2]; // [rsp+30h] [rbp-18h] BYREF

  *(_OWORD *)v10 = 0;
  if ( !dword_18002B2D0 )
  {
    AuthorizedSharingToken = -1055719422;
LABEL_5:
    v8 = (DSLogger *)tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(
                       a1,
                       a2,
                       a3,
                       a4);
    DSLogger::LogError(
      v8,
      L"DSSRemoveSharingToken",
      0x2BCu,
      L"Failed to remove token: %s. hr=0x%x",
      a1,
      AuthorizedSharingToken);
    goto LABEL_6;
  }
  AuthorizedSharingToken = GetAuthorizedSharingToken(a1, 1, (FILETIME **)v10);
  if ( AuthorizedSharingToken < 0 )
    goto LABEL_5;
  v6 = (SharingTokenManager *)tlx::_LazyImpl<SharingTokenManager,tlx::lazy_construct<SharingTokenManager>,tlx::static_lazy<SharingTokenManager,0,tlx::lazy_construct<SharingTokenManager>>>::get();
  AuthorizedSharingToken = SharingTokenManager::RemoveSharingToken(v6, v10[0], 1, v7);
  if ( AuthorizedSharingToken < 0 )
    goto LABEL_5;
LABEL_6:
  if ( v10[1] )
    utl::_RefCountBase::_DecStrong(v10[1]);
  return (unsigned int)AuthorizedSharingToken;
}

```

## disassembly

```asm
0x18000d7b8  mov     [rsp+arg_0], rbx
0x18000d7bd  push    rdi
0x18000d7be  sub     rsp, 40h
0x18000d7c2  cmp     cs:dword_18002B2D0, 0
0x18000d7c9  xorps   xmm0, xmm0
0x18000d7cc  movdqu  xmmword ptr [rsp+48h+var_18], xmm0
0x18000d7d2  mov     rdi, rcx
0x18000d7d5  jnz     short loc_18000D7DE
0x18000d7d7  mov     ebx, 0C1130002h
0x18000d7dc  jmp     short loc_18000D811
0x18000d7de  lea     r8, [rsp+48h+var_18]
0x18000d7e3  mov     edx, 1
0x18000d7e8  call    GetAuthorizedSharingToken
0x18000d7ed  mov     ebx, eax
0x18000d7ef  test    eax, eax
0x18000d7f1  js      short loc_18000D811
0x18000d7f3  call    ?get@?$_LazyImpl@VSharingTokenManager@@V?$lazy_construct@VSharingTokenManager@@@tlx@@V?$static_lazy@VSharingTokenManager@@$0A@V?$lazy_construct@VSharingTokenManager@@@tlx@@@3@@tlx@@QEAAAEAVSharingTokenManager@@XZ; tlx::_LazyImpl<SharingTokenManager,tlx::lazy_construct<SharingTokenManager>,tlx::static_lazy<SharingTokenManager,0,tlx::lazy_construct<SharingTokenManager>>>::get(void)
0x18000d7f8  mov     rdx, [rsp+48h+var_18]; struct SharingToken *
0x18000d7fd  mov     r8d, 1; int
0x18000d803  mov     rcx, rax; this
0x18000d806  call    ?RemoveSharingToken@SharingTokenManager@@QEAAJPEAVSharingToken@@H@Z; SharingTokenManager::RemoveSharingToken(SharingToken *,int)
0x18000d80b  mov     ebx, eax
0x18000d80d  test    eax, eax
0x18000d80f  jns     short loc_18000D83B
0x18000d811  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x18000d816  lea     r9, aFailedToRemove_0; "Failed to remove token: %s. hr=0x%x"
0x18000d81d  mov     [rsp+48h+var_20], ebx
0x18000d821  mov     r8d, 2BCh; unsigned int
0x18000d827  mov     [rsp+48h+var_28], rdi
0x18000d82c  lea     rdx, aDssremoveshari_0; "DSSRemoveSharingToken"
0x18000d833  mov     rcx, rax; this
0x18000d836  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x18000d83b  mov     rcx, [rsp+48h+var_18+8]; this
0x18000d840  test    rcx, rcx
0x18000d843  jz      short loc_18000D84A
0x18000d845  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18000d84a  mov     eax, ebx
0x18000d84c  mov     rbx, [rsp+48h+arg_0]
0x18000d851  add     rsp, 40h
0x18000d855  pop     rdi
0x18000d856  retn
```
