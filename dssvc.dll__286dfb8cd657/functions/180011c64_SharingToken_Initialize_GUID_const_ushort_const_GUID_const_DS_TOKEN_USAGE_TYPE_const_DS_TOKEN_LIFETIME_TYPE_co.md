# SharingToken::Initialize(_GUID const &,ushort const *,_GUID const &,_DS_TOKEN_USAGE_TYPE const &,_DS_TOKEN_LIFETIME_TYPE const &,ShareAccessControl const &)

- ea: `0x180011c64`
- end: `0x180011d06`
- name: `?Initialize@SharingToken@@QEAAJAEBU_GUID@@PEBG0AEBW4_DS_TOKEN_USAGE_TYPE@@AEBW4_DS_TOKEN_LIFETIME_TYPE@@AEBVShareAccessControl@@@Z`
- size: `162`
- prototype: `__int64 __usercall@<rax>(SharingToken *__hidden this@<rcx>, const struct _GUID *@<rdx>, const unsigned __int16 *@<r8>, const struct _GUID *@<r9>, const enum _DS_TOKEN_USAGE_TYPE *, const enum _DS_TOKEN_LIFETIME_TYPE *, const struct ShareAccessControl *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180013bf0`

## callees

- `0x180006e2c`
- `0x180006f78`
- `0x18000bf80`
- `0x18000fbd8`
- `0x180011c64`
- `0x180011fc0`

## string_xrefs

- `0x180011cd9`: `SharingToken::Initialize failed. HR=0x%x`
- `0x180011cea`: `SharingToken::Initialize`

## pseudocode

```c
__int64 __fastcall SharingToken::Initialize(
        SharingToken *this,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        const struct _GUID *a4,
        const enum _DS_TOKEN_USAGE_TYPE *a5,
        const enum _DS_TOKEN_LIFETIME_TYPE *a6,
        const struct ShareAccessControl *a7)
{
  __int64 v9; // rcx
  int v10; // ebx
  int *v11; // rax
  int v13; // [rsp+20h] [rbp-18h]

  *(struct _GUID *)((char *)this + 12) = *a2;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           (__int64)this + 32,
                           (__int64)a3) )
  {
    v10 = -2147024882;
LABEL_5:
    v11 = tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(v9);
    v13 = v10;
    DSLogger::LogError(
      (DSLogger *)v11,
      L"SharingToken::Initialize",
      151,
      L"SharingToken::Initialize failed. HR=0x%x",
      v13);
    return (unsigned int)v10;
  }
  *((struct _GUID *)this + 4) = *a4;
  *((_DWORD *)this + 20) = *(_DWORD *)a5;
  v10 = SharingToken::SetTokenLifeTime(this, a6);
  if ( v10 < 0 )
    goto LABEL_5;
  v10 = ShareAccessControl::Initialize((char *)this + 120, a7, (char *)a7 + 4, (char *)a7 + 8);
  if ( v10 < 0 )
    goto LABEL_5;
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180011c64  mov     [rsp+arg_0], rbx
0x180011c69  push    rdi
0x180011c6a  sub     rsp, 30h
0x180011c6e  movups  xmm0, xmmword ptr [rdx]
0x180011c71  mov     rdi, rcx
0x180011c74  mov     rdx, r8
0x180011c77  mov     rbx, r9
0x180011c7a  movdqu  xmmword ptr [rcx+0Ch], xmm0
0x180011c7f  add     rcx, 20h ; ' '
0x180011c83  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *)
0x180011c88  test    al, al
0x180011c8a  jnz     short loc_180011C93
0x180011c8c  mov     ebx, 8007000Eh
0x180011c91  jmp     short loc_180011CD4
0x180011c93  movups  xmm0, xmmword ptr [rbx]
0x180011c96  mov     rax, [rsp+38h+arg_20]
0x180011c9b  mov     rdx, [rsp+38h+arg_28]; enum _DS_TOKEN_LIFETIME_TYPE *
0x180011ca0  movdqu  xmmword ptr [rdi+40h], xmm0
0x180011ca5  mov     ecx, [rax]
0x180011ca7  mov     [rdi+50h], ecx
0x180011caa  mov     rcx, rdi; this
0x180011cad  call    ?SetTokenLifeTime@SharingToken@@AEAAJAEBW4_DS_TOKEN_LIFETIME_TYPE@@@Z; SharingToken::SetTokenLifeTime(_DS_TOKEN_LIFETIME_TYPE const &)
0x180011cb2  mov     ebx, eax
0x180011cb4  test    eax, eax
0x180011cb6  js      short loc_180011CD4
0x180011cb8  mov     rdx, [rsp+38h+arg_30]
0x180011cbd  lea     rcx, [rdi+78h]
0x180011cc1  lea     r9, [rdx+8]
0x180011cc5  lea     r8, [rdx+4]
0x180011cc9  call    ?Initialize@ShareAccessControl@@QEAAJAEBW4_DS_SHARE_PERMISSION@@AEBW4_DS_SHARE_MODE@@AEBV?$list@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@V?$allocator@V?$smart_ptr@VSharingTarget@@$1??$_delete@VSharingTarget@@@tlx@@YAXPEAV1@@ZV?$allocator@H@utl@@@tlx@@@utl@@@utl@@@Z; ShareAccessControl::Initialize(_DS_SHARE_PERMISSION const &,_DS_SHARE_MODE const &,utl::list<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>,utl::allocator<tlx::smart_ptr<SharingTarget,&tlx::_delete<SharingTarget>(SharingTarget *),utl::allocator<int>>>> const &)
0x180011cce  mov     ebx, eax
0x180011cd0  test    eax, eax
0x180011cd2  jns     short loc_180011CF9
0x180011cd4  call    ?get@?$_LazyImpl@VDSLogger@@V?$lazy_construct@VDSLogger@@@tlx@@V?$static_lazy@VDSLogger@@$0A@V?$lazy_construct@VDSLogger@@@tlx@@@3@@tlx@@QEAAAEAVDSLogger@@XZ; tlx::_LazyImpl<DSLogger,tlx::lazy_construct<DSLogger>,tlx::static_lazy<DSLogger,0,tlx::lazy_construct<DSLogger>>>::get(void)
0x180011cd9  lea     r9, aSharingtokenIn_0; "SharingToken::Initialize failed. HR=0x%"...
0x180011ce0  mov     [rsp+38h+var_18], ebx
0x180011ce4  mov     r8d, 97h; unsigned int
0x180011cea  lea     rdx, aSharingtokenIn; "SharingToken::Initialize"
0x180011cf1  mov     rcx, rax; this
0x180011cf4  call    ?LogError@DSLogger@@QEAAXPEBGK0ZZ; DSLogger::LogError(ushort const *,ulong,ushort const *,...)
0x180011cf9  mov     eax, ebx
0x180011cfb  mov     rbx, [rsp+38h+arg_0]
0x180011d00  add     rsp, 30h
0x180011d04  pop     rdi
0x180011d05  retn
```
