# AttemptToTransitionSlowScope(_NETRESOURCEW *,int *)

- ea: `0x1800371c0`
- end: `0x180037354`
- name: `?AttemptToTransitionSlowScope@@YAJPEAU_NETRESOURCEW@@PEAH@Z`
- size: `404`
- prototype: `__int64 __fastcall(struct _NETRESOURCEW *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180036eec`

## callees

- `0x180003920`
- `0x180007978`
- `0x180025274`
- `0x18002d2d8`
- `0x1800371c0`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x180037297`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x180037297`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x1800372b0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x1800372b0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003723c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003723c`

## string_xrefs

- `0x1800371f9`: `onecore\ds\security\gina\profile\profsvc\winlogon.cpp`
- `0x18003724f`: `onecore\ds\security\gina\profile\profsvc\winlogon.cpp`
- `0x180037306`: `onecore\ds\security\gina\profile\profsvc\winlogon.cpp`

## pseudocode

```c
__int64 __fastcall AttemptToTransitionSlowScope(struct _NETRESOURCEW *a1, int *a2)
{
  int v3; // eax
  int v4; // ebx
  WCHAR *v5; // rdi
  HRESULT v6; // eax
  __int64 v7; // rax
  int i; // eax
  LPVOID v9; // rbx
  __int64 (__fastcall *v10)(LPVOID, WCHAR *, __int64, __int64 *); // r14
  __int64 v11; // rcx
  int ppv; // [rsp+20h] [rbp-10h]
  int ppva; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  __int64 v16; // [rsp+60h] [rbp+30h] BYREF
  LPVOID v17; // [rsp+68h] [rbp+38h] BYREF
  LPWSTR pszPath; // [rsp+70h] [rbp+40h] BYREF

  *a2 = 0;
  pszPath = 0;
  v3 = HeapDupStr(a1->lpRemoteName, &pszPath);
  v4 = v3;
  if ( v3 >= 0 )
  {
    v5 = pszPath;
    v17 = 0;
    v6 = CoCreateInstance(
           &GUID_48c6be7c_3871_43cc_b46f_1449a1bb2ff3,
           0,
           0x17u,
           &GUID_855d6203_7914_48b9_8d40_4c56f5acffc5,
           &v17);
    v4 = v6;
    if ( v6 >= 0 )
    {
      v16 = 0;
      v7 = *(_QWORD *)v17;
      v16 = 0;
      for ( i = (*(__int64 (__fastcall **)(LPVOID, WCHAR *, __int64, __int64 *))(v7 + 80))(v17, v5, 32, &v16);
            ;
            i = v10(v9, v5, 32, &v16) )
      {
        v4 = i;
        PathRemoveFileSpecW(v5);
        if ( v4 != -2147024894 && v4 != -2147024891 )
          break;
        if ( PathIsUNCServerW(v5) )
          goto LABEL_16;
        v9 = v17;
        v10 = *(__int64 (__fastcall **)(LPVOID, WCHAR *, __int64, __int64 *))(*(_QWORD *)v17 + 80LL);
        v11 = v16;
        v16 = 0;
        if ( v11 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      }
      if ( v4 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x571,
          (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
          (const char *)(unsigned int)v4,
          ppva);
        wil::com_ptr_t<IProfileNotify,wil::err_exception_policy>::~com_ptr_t<IProfileNotify,wil::err_exception_policy>(&v16);
        goto LABEL_17;
      }
      *a2 = 1;
LABEL_16:
      wil::com_ptr_t<IProfileNotify,wil::err_exception_policy>::~com_ptr_t<IProfileNotify,wil::err_exception_policy>(&v16);
      v4 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x55D,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
        (const char *)(unsigned int)v6,
        ppva);
    }
LABEL_17:
    wil::com_ptr_t<IProfileNotify,wil::err_exception_policy>::~com_ptr_t<IProfileNotify,wil::err_exception_policy>((__int64 *)&v17);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&pszPath);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x559,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\winlogon.cpp",
      (const char *)(unsigned int)v3,
      ppv);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800371c0  push    rbp
0x1800371c2  push    rbx
0x1800371c3  push    rsi
0x1800371c4  push    rdi
0x1800371c5  push    r14
0x1800371c7  mov     rbp, rsp
0x1800371ca  sub     rsp, 30h
0x1800371ce  mov     rsi, rdx
0x1800371d1  mov     dword ptr [rdx], 0
0x1800371d7  mov     [rbp+pszPath], 0
0x1800371df  lea     rdx, [rbp+pszPath]; unsigned __int16 **
0x1800371e3  mov     rcx, [rcx+18h]; unsigned __int16 *
0x1800371e7  call    ?HeapDupStr@@YAJPEBGPEAPEAG@Z; HeapDupStr(ushort const *,ushort * *)
0x1800371ec  mov     ebx, eax
0x1800371ee  test    eax, eax
0x1800371f0  jns     short loc_18003720F
0x1800371f2  mov     rcx, [rbp+28h]; this
0x1800371f6  mov     r9d, eax; char *
0x1800371f9  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\gina\\profile\\p"...
0x180037200  mov     edx, 559h; void *
0x180037205  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003720a  jmp     loc_180037347
0x18003720f  mov     rdi, [rbp+pszPath]
0x180037213  mov     [rbp+pszPath], rdi
0x180037217  mov     [rbp+arg_8], 0
0x18003721f  lea     rax, [rbp+arg_8]
0x180037223  mov     qword ptr [rsp+30h+ppv], rax; int
0x180037228  lea     r9, _GUID_855d6203_7914_48b9_8d40_4c56f5acffc5; riid
0x18003722f  xor     edx, edx; pUnkOuter
0x180037231  lea     r8d, [rdx+17h]; dwClsContext
0x180037235  lea     rcx, _GUID_48c6be7c_3871_43cc_b46f_1449a1bb2ff3; rclsid
0x18003723c  call    cs:__imp_CoCreateInstance
0x180037242  mov     ebx, eax
0x180037244  test    eax, eax
0x180037246  jns     short loc_180037265
0x180037248  mov     rcx, [rbp+28h]; this
0x18003724c  mov     r9d, eax; char *
0x18003724f  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\gina\\profile\\p"...
0x180037256  mov     edx, 55Dh; void *
0x18003725b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037260  jmp     loc_180037334
0x180037265  mov     [rbp+arg_0], 0
0x18003726d  mov     rcx, [rbp+arg_8]
0x180037271  mov     rax, [rcx]
0x180037274  mov     [rbp+arg_0], 0
0x18003727c  mov     rax, [rax+50h]
0x180037280  lea     r9, [rbp+arg_0]
0x180037284  mov     r8d, 20h ; ' '
0x18003728a  mov     rdx, rdi
0x18003728d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037292  mov     ebx, eax
0x180037294  mov     rcx, rdi; pszPath
0x180037297  call    cs:__imp_PathRemoveFileSpecW
0x18003729d  cmp     ebx, 80070002h
0x1800372a3  jz      short loc_1800372AD
0x1800372a5  cmp     ebx, 80070005h
0x1800372ab  jnz     short loc_1800372FB
0x1800372ad  mov     rcx, rdi; pszPath
0x1800372b0  call    cs:__imp_PathIsUNCServerW
0x1800372b6  test    eax, eax
0x1800372b8  jnz     short loc_1800372EB
0x1800372ba  mov     rbx, [rbp+arg_8]
0x1800372be  mov     rax, [rbx]
0x1800372c1  mov     r14, [rax+50h]
0x1800372c5  mov     rcx, [rbp+arg_0]
0x1800372c9  mov     [rbp+arg_0], 0
0x1800372d1  test    rcx, rcx
0x1800372d4  jz      short loc_1800372E3
0x1800372d6  mov     rdx, [rcx]
0x1800372d9  mov     rax, [rdx+10h]
0x1800372dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800372e2  nop
0x1800372e3  mov     rcx, rbx
0x1800372e6  mov     rax, r14
0x1800372e9  jmp     short loc_180037280
0x1800372eb  cmp     ebx, 80070002h
0x1800372f1  jz      short loc_180037329
0x1800372f3  cmp     ebx, 80070005h
0x1800372f9  jz      short loc_180037329
0x1800372fb  test    ebx, ebx
0x1800372fd  jns     short loc_180037323
0x1800372ff  mov     rcx, [rbp+28h]; this
0x180037303  mov     r9d, ebx; char *
0x180037306  lea     r8, aOnecoreDsSecur_12; "onecore\\ds\\security\\gina\\profile\\p"...
0x18003730d  mov     edx, 571h; void *
0x180037312  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037317  nop
0x180037318  lea     rcx, [rbp+arg_0]
0x18003731c  call    ??1?$com_ptr_t@UIProfileNotify@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IProfileNotify,wil::err_exception_policy>::~com_ptr_t<IProfileNotify,wil::err_exception_policy>(void)
0x180037321  jmp     short loc_180037334
0x180037323  mov     dword ptr [rsi], 1
0x180037329  lea     rcx, [rbp+arg_0]
0x18003732d  call    ??1?$com_ptr_t@UIProfileNotify@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IProfileNotify,wil::err_exception_policy>::~com_ptr_t<IProfileNotify,wil::err_exception_policy>(void)
0x180037332  xor     ebx, ebx
0x180037334  lea     rcx, [rbp+arg_8]
0x180037338  call    ??1?$com_ptr_t@UIProfileNotify@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IProfileNotify,wil::err_exception_policy>::~com_ptr_t<IProfileNotify,wil::err_exception_policy>(void)
0x18003733d  nop
0x18003733e  lea     rcx, [rbp+pszPath]
0x180037342  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180037347  mov     eax, ebx
0x180037349  add     rsp, 30h
0x18003734d  pop     r14
0x18003734f  pop     rdi
0x180037350  pop     rsi
0x180037351  pop     rbx
0x180037352  pop     rbp
0x180037353  retn
```
