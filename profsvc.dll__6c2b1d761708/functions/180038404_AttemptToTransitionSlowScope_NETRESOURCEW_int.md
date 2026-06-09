# AttemptToTransitionSlowScope(_NETRESOURCEW *,int *)

- ea: `0x180038404`
- end: `0x1800385ab`
- name: `?AttemptToTransitionSlowScope@@YAJPEAU_NETRESOURCEW@@PEAH@Z`
- size: `423`
- prototype: `__int64 __fastcall(struct _NETRESOURCEW *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180038118`

## callees

- `0x1800039f0`
- `0x180005330`
- `0x180027960`
- `0x180030ad0`
- `0x180038404`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x1800384e1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x1800384e1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x180038500`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x180038500`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180038480`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180038480`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
          (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
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
        (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
        (const char *)(unsigned int)v6,
        ppva);
    }
LABEL_17:
    wil::com_ptr_t<IProfileNotify,wil::err_exception_policy>::~com_ptr_t<IProfileNotify,wil::err_exception_policy>(&v17);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPath);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x559,
      (unsigned int)`DaclContainsPackageAndLpacCapabilitySid_'::`2'::AppPackageAuthority.SubAuthority,
      (const char *)(unsigned int)v3,
      ppv);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180038404  push    rbp
0x180038406  push    rbx
0x180038407  push    rsi
0x180038408  push    rdi
0x180038409  push    r14
0x18003840b  mov     rbp, rsp
0x18003840e  sub     rsp, 30h
0x180038412  mov     rsi, rdx
0x180038415  mov     dword ptr [rdx], 0
0x18003841b  mov     [rbp+pszPath], 0
0x180038423  lea     rdx, [rbp+pszPath]; unsigned __int16 **
0x180038427  mov     rcx, [rcx+18h]; unsigned __int16 *
0x18003842b  call    ?HeapDupStr@@YAJPEBGPEAPEAG@Z; HeapDupStr(ushort const *,ushort * *)
0x180038430  mov     ebx, eax
0x180038432  test    eax, eax
0x180038434  jns     short loc_180038453
0x180038436  mov     rcx, [rbp+28h]; this
0x18003843a  mov     r9d, eax; char *
0x18003843d  lea     r8, ?AppPackageAuthority@?1??DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z@4U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; unsigned int
0x180038444  mov     edx, 559h; void *
0x180038449  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003844e  jmp     loc_18003859D
0x180038453  mov     rdi, [rbp+pszPath]
0x180038457  mov     [rbp+pszPath], rdi
0x18003845b  mov     [rbp+arg_8], 0
0x180038463  lea     rax, [rbp+arg_8]
0x180038467  mov     qword ptr [rsp+30h+ppv], rax; int
0x18003846c  lea     r9, _GUID_855d6203_7914_48b9_8d40_4c56f5acffc5; riid
0x180038473  xor     edx, edx; pUnkOuter
0x180038475  lea     r8d, [rdx+17h]; dwClsContext
0x180038479  lea     rcx, _GUID_48c6be7c_3871_43cc_b46f_1449a1bb2ff3; rclsid
0x180038480  call    cs:__imp_CoCreateInstance
0x180038487  nop     dword ptr [rax+rax+00h]
0x18003848c  mov     ebx, eax
0x18003848e  test    eax, eax
0x180038490  jns     short loc_1800384AF
0x180038492  mov     rcx, [rbp+28h]; this
0x180038496  mov     r9d, eax; char *
0x180038499  lea     r8, ?AppPackageAuthority@?1??DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z@4U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; unsigned int
0x1800384a0  mov     edx, 55Dh; void *
0x1800384a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800384aa  jmp     loc_18003858A
0x1800384af  mov     [rbp+arg_0], 0
0x1800384b7  mov     rcx, [rbp+arg_8]
0x1800384bb  mov     rax, [rcx]
0x1800384be  mov     [rbp+arg_0], 0
0x1800384c6  mov     rax, [rax+50h]
0x1800384ca  lea     r9, [rbp+arg_0]
0x1800384ce  mov     r8d, 20h ; ' '
0x1800384d4  mov     rdx, rdi
0x1800384d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800384dc  mov     ebx, eax
0x1800384de  mov     rcx, rdi; pszPath
0x1800384e1  call    cs:__imp_PathRemoveFileSpecW
0x1800384e8  nop     dword ptr [rax+rax+00h]
0x1800384ed  cmp     ebx, 80070002h
0x1800384f3  jz      short loc_1800384FD
0x1800384f5  cmp     ebx, 80070005h
0x1800384fb  jnz     short loc_180038551
0x1800384fd  mov     rcx, rdi; pszPath
0x180038500  call    cs:__imp_PathIsUNCServerW
0x180038507  nop     dword ptr [rax+rax+00h]
0x18003850c  test    eax, eax
0x18003850e  jnz     short loc_180038541
0x180038510  mov     rbx, [rbp+arg_8]
0x180038514  mov     rax, [rbx]
0x180038517  mov     r14, [rax+50h]
0x18003851b  mov     rcx, [rbp+arg_0]
0x18003851f  mov     [rbp+arg_0], 0
0x180038527  test    rcx, rcx
0x18003852a  jz      short loc_180038539
0x18003852c  mov     rdx, [rcx]
0x18003852f  mov     rax, [rdx+10h]
0x180038533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038538  nop
0x180038539  mov     rcx, rbx
0x18003853c  mov     rax, r14
0x18003853f  jmp     short loc_1800384CA
0x180038541  cmp     ebx, 80070002h
0x180038547  jz      short loc_18003857F
0x180038549  cmp     ebx, 80070005h
0x18003854f  jz      short loc_18003857F
0x180038551  test    ebx, ebx
0x180038553  jns     short loc_180038579
0x180038555  mov     rcx, [rbp+28h]; this
0x180038559  mov     r9d, ebx; char *
0x18003855c  lea     r8, ?AppPackageAuthority@?1??DaclContainsPackageAndLpacCapabilitySid_@@YAHPEAX@Z@4U_SID_IDENTIFIER_AUTHORITY@@B.SubAuthority; unsigned int
0x180038563  mov     edx, 571h; void *
0x180038568  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003856d  nop
0x18003856e  lea     rcx, [rbp+arg_0]
0x180038572  call    ??1?$com_ptr_t@UIProfileNotify@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IProfileNotify,wil::err_exception_policy>::~com_ptr_t<IProfileNotify,wil::err_exception_policy>(void)
0x180038577  jmp     short loc_18003858A
0x180038579  mov     dword ptr [rsi], 1
0x18003857f  lea     rcx, [rbp+arg_0]
0x180038583  call    ??1?$com_ptr_t@UIProfileNotify@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IProfileNotify,wil::err_exception_policy>::~com_ptr_t<IProfileNotify,wil::err_exception_policy>(void)
0x180038588  xor     ebx, ebx
0x18003858a  lea     rcx, [rbp+arg_8]
0x18003858e  call    ??1?$com_ptr_t@UIProfileNotify@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IProfileNotify,wil::err_exception_policy>::~com_ptr_t<IProfileNotify,wil::err_exception_policy>(void)
0x180038593  nop
0x180038594  lea     rcx, [rbp+pszPath]
0x180038598  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003859d  mov     eax, ebx
0x18003859f  add     rsp, 30h
0x1800385a3  pop     r14
0x1800385a5  pop     rdi
0x1800385a6  pop     rsi
0x1800385a7  pop     rbx
0x1800385a8  pop     rbp
0x1800385a9  retn
```
