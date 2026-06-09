# ConstructCacheEntryInfo

- ea: `0x180046c14`
- end: `0x180046e0e`
- name: `ConstructCacheEntryInfo`
- size: `506`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180048f70`

## callees

- `0x1800124a8`
- `0x1800464e8`
- `0x180046c14`
- `0x1800483c8`
- `0x180048408`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180046c2f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180046cc9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180046d84`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180046c2f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180046cc9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180046d84`

## string_xrefs

- `0x180046c70`: `onecoreuap\ds\security\efs\dll\efstfacache.cxx`
- `0x180046cad`: `onecoreuap\ds\security\efs\dll\efstfacache.cxx`
- `0x180046cdd`: `onecoreuap\ds\security\efs\dll\efstfacache.cxx`
- `0x180046d2a`: `onecoreuap\ds\security\efs\dll\efstfacache.cxx`
- `0x180046d68`: `onecoreuap\ds\security\efs\dll\efstfacache.cxx`
- `0x180046d98`: `onecoreuap\ds\security\efs\dll\efstfacache.cxx`
- `0x180046dfc`: `onecoreuap\ds\security\efs\dll\efstfacache.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_OWORD *__fastcall ConstructCacheEntryInfo(__int64 ***a1)
{
  _OWORD *v2; // rax
  const char *v3; // r9
  _OWORD *v4; // rbx
  unsigned int v5; // eax
  int v6; // eax
  HLOCAL v7; // rax
  const char *v8; // r9
  unsigned int v9; // r9d
  __int64 *v10; // rcx
  __int64 *i; // rax
  unsigned int v12; // eax
  int v13; // eax
  HLOCAL v14; // rax
  const char *v15; // r9
  __int64 v16; // r10
  __int64 **v17; // rcx
  __int64 *j; // rax
  int v20; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  SIZE_T uBytes; // [rsp+38h] [rbp+10h] BYREF
  _OWORD *v23; // [rsp+40h] [rbp+18h] BYREF

  v2 = LocalAlloc(0x40u, 0x30u);
  v4 = v2;
  v23 = v2;
  if ( !v2 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x245,
      (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efstfacache.cxx",
      v3);
  *v2 = 0;
  v2[1] = 0;
  v2[2] = 0;
  if ( (unsigned __int64)a1[1] > 0xFFFFFFFF )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x248,
      (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efstfacache.cxx",
      (const char *)0x8000000BLL,
      v20);
  v5 = *((_DWORD *)a1 + 2);
  *(_DWORD *)v4 = v5;
  uBytes = 0;
  v6 = ULongLongMult(v5, 0x10u, &uBytes);
  if ( v6 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x24B,
      (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efstfacache.cxx",
      (const char *)(unsigned int)v6,
      v20);
  v7 = LocalAlloc(0x40u, uBytes);
  *((_QWORD *)v4 + 1) = v7;
  if ( !v7 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x24D,
      (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efstfacache.cxx",
      v8);
  v9 = 0;
  v10 = (__int64 *)*a1;
  for ( i = **a1; i != v10; i = (__int64 *)*i )
    *(_OWORD *)(*((_QWORD *)v4 + 1) + 16LL * v9++) = *((_OWORD *)i + 1);
  if ( (unsigned __int64)a1[10] > 0xFFFFFFFF )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x254,
      (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efstfacache.cxx",
      (const char *)0x8000000BLL,
      v20);
  v12 = *((_DWORD *)a1 + 20);
  *((_DWORD *)v4 + 4) = v12;
  uBytes = 0;
  v13 = ULongLongMult(v12, 8u, &uBytes);
  if ( v13 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x257,
      (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efstfacache.cxx",
      (const char *)(unsigned int)v13,
      v20);
  v14 = LocalAlloc(0x40u, uBytes);
  *((_QWORD *)v4 + 3) = v14;
  if ( !v14 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x259,
      (unsigned int)"onecoreuap\\ds\\security\\efs\\dll\\efstfacache.cxx",
      v15);
  v16 = 0;
  v17 = a1[9];
  for ( j = *v17; j != (__int64 *)v17; j = (__int64 *)*j )
  {
    *(_QWORD *)(*((_QWORD *)v4 + 3) + 8 * v16) = j[2];
    v16 = (unsigned int)(v16 + 1);
  }
  *((_QWORD *)v4 + 5) = a1[8];
  v23 = 0;
  wil::details::unique_storage<wil::details::resource_policy<_EDP_TFA_CACHE_ENTRY_INFO *,void (*)(_EDP_TFA_CACHE_ENTRY_INFO *),&void DeleteEntryInfo(_EDP_TFA_CACHE_ENTRY_INFO *),wistd::integral_constant<unsigned __int64,0>,_EDP_TFA_CACHE_ENTRY_INFO *,_EDP_TFA_CACHE_ENTRY_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EDP_TFA_CACHE_ENTRY_INFO *,void (*)(_EDP_TFA_CACHE_ENTRY_INFO *),&void DeleteEntryInfo(_EDP_TFA_CACHE_ENTRY_INFO *),wistd::integral_constant<unsigned __int64,0>,_EDP_TFA_CACHE_ENTRY_INFO *,_EDP_TFA_CACHE_ENTRY_INFO *,0,std::nullptr_t>>(&v23);
  return v4;
}

```

## disassembly

```asm
0x180046c14  mov     [rsp+arg_0], rbx
0x180046c19  mov     [rsp+arg_18], rdi
0x180046c1e  push    r14; int
0x180046c20  sub     rsp, 20h
0x180046c24  mov     rdi, rcx
0x180046c27  mov     edx, 30h ; '0'; uBytes
0x180046c2c  lea     ecx, [rdx+10h]; uFlags
0x180046c2f  call    cs:__imp_LocalAlloc
0x180046c35  mov     rbx, rax
0x180046c38  mov     [rsp+28h+arg_10], rax
0x180046c3d  mov     rcx, [rsp+28h]; this
0x180046c42  test    rax, rax
0x180046c45  jz      loc_180046DFC
0x180046c4b  xorps   xmm0, xmm0
0x180046c4e  movups  xmmword ptr [rax], xmm0
0x180046c51  movups  xmmword ptr [rax+10h], xmm0
0x180046c55  movups  xmmword ptr [rax+20h], xmm0
0x180046c59  mov     rcx, [rsp+28h]; this
0x180046c5e  mov     r14d, 0FFFFFFFFh
0x180046c64  cmp     [rdi+8], r14
0x180046c68  jbe     short loc_180046C82
0x180046c6a  mov     r9d, 8000000Bh; char *
0x180046c70  lea     r8, aOnecoreuapDsSe_9; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x180046c77  mov     edx, 248h; void *
0x180046c7c  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180046c82  mov     eax, [rdi+8]
0x180046c85  mov     [rbx], eax
0x180046c87  mov     [rsp+28h+uBytes], 0
0x180046c90  mov     ecx, eax; unsigned __int64
0x180046c92  lea     r8, [rsp+28h+uBytes]; unsigned __int64 *
0x180046c97  mov     edx, 10h; unsigned __int64
0x180046c9c  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180046ca1  mov     rcx, [rsp+28h]; this
0x180046ca6  test    eax, eax
0x180046ca8  jns     short loc_180046CBF
0x180046caa  mov     r9d, eax; char *
0x180046cad  lea     r8, aOnecoreuapDsSe_9; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x180046cb4  mov     edx, 24Bh; void *
0x180046cb9  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180046cbf  mov     rdx, [rsp+28h+uBytes]; uBytes
0x180046cc4  mov     ecx, 40h ; '@'; uFlags
0x180046cc9  call    cs:__imp_LocalAlloc
0x180046ccf  mov     [rbx+8], rax
0x180046cd3  mov     rcx, [rsp+28h]; this
0x180046cd8  test    rax, rax
0x180046cdb  jnz     short loc_180046CEF
0x180046cdd  lea     r8, aOnecoreuapDsSe_9; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x180046ce4  mov     edx, 24Dh; void *
0x180046ce9  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180046cef  xor     r9d, r9d
0x180046cf2  mov     rcx, [rdi]
0x180046cf5  mov     rax, [rcx]
0x180046cf8  cmp     rax, rcx
0x180046cfb  jz      short loc_180046D19
0x180046cfd  movups  xmm0, xmmword ptr [rax+10h]
0x180046d01  mov     r8d, r9d
0x180046d04  add     r8, r8
0x180046d07  mov     rdx, [rbx+8]
0x180046d0b  movdqu  xmmword ptr [rdx+r8*8], xmm0
0x180046d11  inc     r9d
0x180046d14  mov     rax, [rax]
0x180046d17  jmp     short loc_180046CF8
0x180046d19  mov     rcx, [rsp+28h]; this
0x180046d1e  cmp     [rdi+50h], r14
0x180046d22  jbe     short loc_180046D3C
0x180046d24  mov     r9d, 8000000Bh; char *
0x180046d2a  lea     r8, aOnecoreuapDsSe_9; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x180046d31  mov     edx, 254h; void *
0x180046d36  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180046d3c  mov     eax, [rdi+50h]
0x180046d3f  mov     [rbx+10h], eax
0x180046d42  mov     [rsp+28h+uBytes], 0
0x180046d4b  mov     ecx, eax; unsigned __int64
0x180046d4d  lea     r8, [rsp+28h+uBytes]; unsigned __int64 *
0x180046d52  mov     edx, 8; unsigned __int64
0x180046d57  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x180046d5c  mov     rcx, [rsp+28h]; this
0x180046d61  test    eax, eax
0x180046d63  jns     short loc_180046D7A
0x180046d65  mov     r9d, eax; char *
0x180046d68  lea     r8, aOnecoreuapDsSe_9; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x180046d6f  mov     edx, 257h; void *
0x180046d74  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180046d7a  mov     rdx, [rsp+28h+uBytes]; uBytes
0x180046d7f  mov     ecx, 40h ; '@'; uFlags
0x180046d84  call    cs:__imp_LocalAlloc
0x180046d8a  mov     [rbx+18h], rax
0x180046d8e  mov     rcx, [rsp+28h]; this
0x180046d93  test    rax, rax
0x180046d96  jnz     short loc_180046DAA
0x180046d98  lea     r8, aOnecoreuapDsSe_9; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x180046d9f  mov     edx, 259h; void *
0x180046da4  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180046daa  xor     r10d, r10d
0x180046dad  mov     rcx, [rdi+48h]
0x180046db1  mov     rax, [rcx]
0x180046db4  cmp     rax, rcx
0x180046db7  jz      short loc_180046DCD
0x180046db9  mov     r8, [rbx+18h]
0x180046dbd  mov     rdx, [rax+10h]
0x180046dc1  mov     [r8+r10*8], rdx
0x180046dc5  inc     r10d
0x180046dc8  mov     rax, [rax]
0x180046dcb  jmp     short loc_180046DB4
0x180046dcd  mov     rax, [rdi+40h]
0x180046dd1  mov     [rbx+28h], rax
0x180046dd5  mov     [rsp+28h+arg_10], 0
0x180046dde  lea     rcx, [rsp+28h+arg_10]
0x180046de3  call    ??1?$unique_storage@U?$resource_policy@PEAU_EDP_TFA_CACHE_ENTRY_INFO@@P6AXPEAU1@@Z$1?DeleteEntryInfo@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_EDP_TFA_CACHE_ENTRY_INFO *,void (*)(_EDP_TFA_CACHE_ENTRY_INFO *),&DeleteEntryInfo(_EDP_TFA_CACHE_ENTRY_INFO *),wistd::integral_constant<unsigned __int64,0>,_EDP_TFA_CACHE_ENTRY_INFO *,_EDP_TFA_CACHE_ENTRY_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_EDP_TFA_CACHE_ENTRY_INFO *,void (*)(_EDP_TFA_CACHE_ENTRY_INFO *),&DeleteEntryInfo(_EDP_TFA_CACHE_ENTRY_INFO *),wistd::integral_constant<unsigned __int64,0>,_EDP_TFA_CACHE_ENTRY_INFO *,_EDP_TFA_CACHE_ENTRY_INFO *,0,std::nullptr_t>>(void)
0x180046de8  mov     rax, rbx
0x180046deb  mov     rbx, [rsp+28h+arg_0]
0x180046df0  mov     rdi, [rsp+28h+arg_18]
0x180046df5  add     rsp, 20h
0x180046df9  pop     r14
0x180046dfb  retn
0x180046dfc  lea     r8, aOnecoreuapDsSe_9; "onecoreuap\\ds\\security\\efs\\dll\\efs"...
0x180046e03  mov     edx, 245h; void *
0x180046e08  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
