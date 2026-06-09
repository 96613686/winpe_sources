# DesktopAppXVFS::MakeExclusionsArray(WriteVirtualization::NormalizedExclusionPathList<WriteVirtualization::NormalizedFileSystemPath> const &)

- ea: `0x18003365c`
- end: `0x1800338b0`
- name: `?MakeExclusionsArray@DesktopAppXVFS@@YA?AV?$unique_any_array_ptr@PEBGU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEBGP6AXPEBG@Z$1?CoTaskMemFreeConstString@DesktopAppXVFS@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEBGPEBG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@AEBV?$NormalizedExclusionPathList@VNormalizedFileSystemPath@WriteVirtualization@@@WriteVirtualization@@@Z`
- size: `596`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x18002f408`

## callees

- `0x18002109c`
- `0x18002b6a8`
- `0x18002cd38`
- `0x18003365c`
- `0x180035e2c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003374b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003374b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003372c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003372c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003373d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033767`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033803`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003373d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033767`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180033803`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800336c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800336c0`

## string_xrefs

- `0x18003387a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18003388c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18003389e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DesktopAppXVFS::MakeExclusionsArray(__int64 a1, _QWORD *a2, __int64 a3, const char *a4)
{
  _QWORD **v4; // rdi
  unsigned __int64 v6; // r12
  __int64 v7; // rbx
  void **v8; // rax
  const char *v9; // r9
  void **v10; // r14
  void **i; // rcx
  void **v12; // r15
  void **v13; // r13
  void *v14; // rbx
  DWORD LastError; // edi
  unsigned __int64 v16; // rax
  unsigned int v17; // r14d
  __int64 v18; // r15
  _QWORD *v19; // rdi
  _QWORD *v20; // rbx
  _QWORD *v21; // rdx
  const char *v22; // r9
  int v23; // r14d
  LPVOID v24; // rax
  __int64 **v25; // rcx
  __int64 j; // rax
  __int64 *k; // rcx
  void **v29; // [rsp+28h] [rbp-18h] BYREF
  unsigned __int64 v30; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  LPVOID pv; // [rsp+88h] [rbp+48h] BYREF
  void **v33; // [rsp+90h] [rbp+50h]

  pv = a2;
  v4 = (_QWORD **)a2;
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  v6 = a2[1];
  if ( v6 )
  {
    if ( v6 > 0x1FFFFFFFFFFFFFFFLL )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x1802,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        a4);
    v7 = v6;
    v8 = (void **)CoTaskMemAlloc(8 * v6);
    v10 = v8;
    v33 = v8;
    if ( v8 )
    {
      for ( i = &v8[v7]; v8 != i; ++v8 )
        *v8 = 0;
    }
    if ( !v10 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x1854,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v9);
    v29 = v10;
    v30 = v6;
    if ( (void ***)a1 != &v29 )
    {
      v12 = *(void ***)a1;
      if ( *(_QWORD *)a1 )
      {
        v13 = &v12[*(_QWORD *)(a1 + 8)];
        if ( v12 != v13 )
        {
          do
          {
            v14 = *v12;
            LastError = GetLastError();
            CoTaskMemFree(v14);
            SetLastError(LastError);
            ++v12;
          }
          while ( v12 != v13 );
          v4 = (_QWORD **)pv;
        }
        CoTaskMemFree(*(LPVOID *)a1);
        *(_QWORD *)a1 = 0;
        *(_QWORD *)(a1 + 8) = 0;
        v12 = 0;
      }
      v16 = *(_QWORD *)(a1 + 8);
      *(_QWORD *)a1 = v10;
      *(_QWORD *)(a1 + 8) = v6;
      v29 = v12;
      v30 = v16;
    }
    wil::unique_any_array_ptr<unsigned short const *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short const *,void (*)(unsigned short const *),&void DesktopAppXVFS::CoTaskMemFreeConstString(unsigned short const *),wistd::integral_constant<unsigned __int64,0>,unsigned short const *,unsigned short const *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<unsigned short const *,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short const *,void (*)(unsigned short const *),&void DesktopAppXVFS::CoTaskMemFreeConstString(unsigned short const *),wistd::integral_constant<unsigned __int64,0>,unsigned short const *,unsigned short const *,0,std::nullptr_t>>>>,unsigned __int64>(&v29);
    v17 = 1;
    v18 = 0;
    v19 = *v4;
    v20 = (_QWORD *)*v19;
    while ( v20 != v19 )
    {
      v21 = v20 + 4;
      if ( v20[7] > 7u )
        v21 = (_QWORD *)*v21;
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &pv,
        v21,
        -1);
      v23 = v17 | 4;
      v24 = pv;
      if ( !pv )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0xFF8,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v22);
      pv = 0;
      *(_QWORD *)(*(_QWORD *)a1 + 8 * v18++) = v24;
      v17 = v23 & 0xFFFFFFFB;
      if ( pv )
        CoTaskMemFree(pv);
      v25 = (__int64 **)v20[2];
      if ( *((_BYTE *)v25 + 25) )
      {
        for ( j = v20[1]; !*(_BYTE *)(j + 25) && v20 == *(_QWORD **)(j + 16); j = *(_QWORD *)(j + 8) )
          v20 = (_QWORD *)j;
        v20 = (_QWORD *)j;
      }
      else
      {
        v20 = (_QWORD *)v20[2];
        for ( k = *v25; !*((_BYTE *)k + 25); k = (__int64 *)*k )
          v20 = k;
      }
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18003365c  mov     [rsp-38h+arg_18], rbx
0x180033661  mov     [rsp-38h+pv], rdx
0x180033666  mov     [rsp-38h+arg_0], rcx
0x18003366b  push    rbp
0x18003366c  push    rsi
0x18003366d  push    rdi
0x18003366e  push    r12
0x180033670  push    r13
0x180033672  push    r14
0x180033674  push    r15
0x180033676  mov     rbp, rsp
0x180033679  sub     rsp, 40h
0x18003367d  mov     rdi, rdx
0x180033680  mov     rsi, rcx
0x180033683  xor     r13d, r13d
0x180033686  mov     [rbp+var_20], r13d
0x18003368a  mov     [rcx], r13
0x18003368d  mov     [rcx+8], r13
0x180033691  mov     r12, [rdx+8]
0x180033695  test    r12, r12
0x180033698  jz      loc_18003385E
0x18003369e  mov     rcx, [rbp+38h]; this
0x1800336a2  mov     rax, 1FFFFFFFFFFFFFFFh
0x1800336ac  cmp     r12, rax
0x1800336af  ja      loc_18003388C
0x1800336b5  lea     rbx, ds:0[r12*8]
0x1800336bd  mov     rcx, rbx; cb
0x1800336c0  call    cs:__imp_CoTaskMemAlloc
0x1800336c7  nop     dword ptr [rax+rax+00h]
0x1800336cc  mov     r14, rax
0x1800336cf  mov     [rbp+arg_10], rax
0x1800336d3  test    rax, rax
0x1800336d6  jz      short loc_1800336EF
0x1800336d8  lea     rcx, [rbx+rax]
0x1800336dc  cmp     rax, rcx
0x1800336df  jz      short loc_1800336EF
0x1800336e1  xor     edx, edx
0x1800336e3  mov     [rax], rdx
0x1800336e6  add     rax, 8
0x1800336ea  cmp     rax, rcx
0x1800336ed  jnz     short loc_1800336E1
0x1800336ef  mov     [rbp+var_20], 3
0x1800336f6  mov     rcx, [rbp+38h]; this
0x1800336fa  test    r14, r14
0x1800336fd  jz      loc_18003387A
0x180033703  mov     [rbp+var_18], r14
0x180033707  mov     [rbp+var_10], r12
0x18003370b  lea     rax, [rbp+var_18]
0x18003370f  cmp     rsi, rax
0x180033712  jz      short loc_180033793
0x180033714  mov     r15, [rsi]
0x180033717  test    r15, r15
0x18003371a  jz      short loc_180033780
0x18003371c  mov     rax, [rsi+8]
0x180033720  lea     r13, [r15+rax*8]
0x180033724  cmp     r15, r13
0x180033727  jz      short loc_180033764
0x180033729  mov     rbx, [r15]
0x18003372c  call    cs:__imp_GetLastError
0x180033733  nop     dword ptr [rax+rax+00h]
0x180033738  mov     edi, eax
0x18003373a  mov     rcx, rbx; pv
0x18003373d  call    cs:__imp_CoTaskMemFree
0x180033744  nop     dword ptr [rax+rax+00h]
0x180033749  mov     ecx, edi; dwErrCode
0x18003374b  call    cs:__imp_SetLastError
0x180033752  nop     dword ptr [rax+rax+00h]
0x180033757  add     r15, 8
0x18003375b  cmp     r15, r13
0x18003375e  jnz     short loc_180033729
0x180033760  mov     rdi, [rbp+pv]
0x180033764  mov     rcx, [rsi]; pv
0x180033767  call    cs:__imp_CoTaskMemFree
0x18003376e  nop     dword ptr [rax+rax+00h]
0x180033773  xor     r13d, r13d
0x180033776  mov     [rsi], r13
0x180033779  mov     [rsi+8], r13
0x18003377d  mov     r15d, r13d
0x180033780  mov     rax, [rsi+8]
0x180033784  mov     [rsi], r14
0x180033787  mov     [rsi+8], r12
0x18003378b  mov     [rbp+var_18], r15
0x18003378f  mov     [rbp+var_10], rax
0x180033793  lea     rcx, [rbp+var_18]
0x180033797  call    ??1?$unique_any_array_ptr@PEBGU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@U?$unique_any_array_deleter@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEBGP6AXPEBG@Z$1?CoTaskMemFreeConstString@DesktopAppXVFS@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEBGPEBG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@2@_K@wil@@QEAA@XZ; wil::unique_any_array_ptr<ushort const *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort const *,void (*)(ushort const *),&DesktopAppXVFS::CoTaskMemFreeConstString(ushort const *),wistd::integral_constant<unsigned __int64,0>,ushort const *,ushort const *,0,std::nullptr_t>>>>,unsigned __int64>::~unique_any_array_ptr<ushort const *,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::details::unique_any_array_deleter<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort const *,void (*)(ushort const *),&DesktopAppXVFS::CoTaskMemFreeConstString(ushort const *),wistd::integral_constant<unsigned __int64,0>,ushort const *,ushort const *,0,std::nullptr_t>>>>,unsigned __int64>(void)
0x18003379c  mov     r14d, 1
0x1800337a2  mov     r15, r13
0x1800337a5  mov     rdi, [rdi]
0x1800337a8  mov     rbx, [rdi]
0x1800337ab  cmp     rbx, rdi
0x1800337ae  jz      loc_18003385E
0x1800337b4  lea     rdx, [rbx+20h]
0x1800337b8  cmp     qword ptr [rbx+38h], 7
0x1800337bd  jbe     short loc_1800337C2
0x1800337bf  mov     rdx, [rdx]
0x1800337c2  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800337c6  lea     rcx, [rbp+pv]
0x1800337ca  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800337cf  or      r14d, 4
0x1800337d3  mov     [rbp+var_20], r14d
0x1800337d7  mov     rcx, [rbp+38h]; this
0x1800337db  mov     rax, [rbp+pv]
0x1800337df  test    rax, rax
0x1800337e2  jz      loc_18003389E
0x1800337e8  mov     [rbp+pv], r13
0x1800337ec  mov     rcx, [rsi]
0x1800337ef  mov     [rcx+r15*8], rax
0x1800337f3  inc     r15
0x1800337f6  and     r14d, 0FFFFFFFBh
0x1800337fa  mov     rcx, [rbp+pv]; pv
0x1800337fe  test    rcx, rcx
0x180033801  jz      short loc_18003380F
0x180033803  call    cs:__imp_CoTaskMemFree
0x18003380a  nop     dword ptr [rax+rax+00h]
0x18003380f  mov     rcx, [rbx+10h]
0x180033813  cmp     [rcx+19h], r13b
0x180033817  jz      short loc_18003383A
0x180033819  mov     rax, [rbx+8]
0x18003381d  jmp     short loc_18003382C
0x18003381f  cmp     rbx, [rax+10h]
0x180033823  jnz     short loc_180033832
0x180033825  mov     rbx, rax
0x180033828  mov     rax, [rax+8]
0x18003382c  cmp     [rax+19h], r13b
0x180033830  jz      short loc_18003381F
0x180033832  mov     rbx, rax
0x180033835  jmp     loc_1800337AB
0x18003383a  mov     rbx, rcx
0x18003383d  mov     rcx, [rcx]
0x180033840  cmp     [rcx+19h], r13b
0x180033844  jnz     loc_1800337AB
0x18003384a  mov     rbx, rcx
0x18003384d  mov     rax, [rcx]
0x180033850  mov     rcx, rax
0x180033853  cmp     [rax+19h], r13b
0x180033857  jz      short loc_18003384A
0x180033859  jmp     loc_1800337AB
0x18003385e  mov     rax, rsi
0x180033861  mov     rbx, [rsp+40h+arg_18]
0x180033869  add     rsp, 40h
0x18003386d  pop     r15
0x18003386f  pop     r14
0x180033871  pop     r13
0x180033873  pop     r12
0x180033875  pop     rdi
0x180033876  pop     rsi
0x180033877  pop     rbp
0x180033878  retn
0x18003387a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180033881  mov     edx, 1854h; void *
0x180033886  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18003388c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180033893  mov     edx, 1802h; void *
0x180033898  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18003389e  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800338a5  mov     edx, 0FF8h; void *
0x1800338aa  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
