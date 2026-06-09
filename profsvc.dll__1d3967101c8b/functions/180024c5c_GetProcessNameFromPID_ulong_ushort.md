# GetProcessNameFromPID(ulong,ushort * *)

- ea: `0x180024c5c`
- end: `0x180024dce`
- name: `?GetProcessNameFromPID@@YAJKPEAPEAG@Z`
- size: `370`
- prototype: `__int64 __fastcall(DWORD dwProcessId, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800379c0`
- `0x180049634`

## callees

- `0x180007978`
- `0x180008360`
- `0x18000a9b8`
- `0x180024c5c`
- `0x18002d2d8`
- `0x18002db38`
- `0x180032668`
- `0x18003a730`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024c8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180024c8c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024da7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024da7`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180024cd7`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180024cd7`

## string_xrefs

- `0x180024cb2`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180024ced`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x180024d6a`: `onecore\ds\security\gina\profile\profsvc\util.cpp`

## pseudocode

```c
__int64 __fastcall GetProcessNameFromPID(DWORD dwProcessId, unsigned __int16 **a2)
{
  HANDLE ProcessHeap; // rax
  __int64 v4; // rdx
  int v5; // eax
  unsigned int LastError; // ebx
  HANDLE v8; // rax
  const char *v9; // r9
  void *v10; // rbx
  int v11; // esi
  int v12; // [rsp+20h] [rbp-59h] BYREF
  unsigned __int16 *v13; // [rsp+28h] [rbp-51h] BYREF
  HANDLE v14; // [rsp+30h] [rbp-49h] BYREF
  void *v15; // [rsp+38h] [rbp-41h] BYREF
  _BYTE v16[8]; // [rsp+40h] [rbp-39h] BYREF
  _QWORD v17[13]; // [rsp+48h] [rbp-31h] BYREF
  _QWORD *v18; // [rsp+B0h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  *a2 = 0;
  if ( dwProcessId )
  {
    v8 = OpenProcess(0x1000u, 0, dwProcessId);
    v15 = v8;
    v10 = v8;
    if ( v8 )
    {
      v13 = 0;
      v17[0] = &wistd::__function::__func<_lambda_b727b7dc3a79984c737ea01e3c3a200c_,long (unsigned short *,unsigned __int64,unsigned __int64 *)>::`vftable';
      v12 = 0;
      v17[1] = &v14;
      v14 = v8;
      v17[2] = &v12;
      v18 = v17;
      v11 = wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
              (__int64)&v13,
              (__int64)v16);
      if ( v18 )
        (*(void (__fastcall **)(_QWORD *))(*v18 + 24LL))(v18);
      if ( v11 >= 0 )
      {
        *a2 = v13;
        if ( v10 != (void *)-1LL )
          CloseHandle(v10);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x62C,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
        (const char *)(unsigned int)v11,
        v12);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>((void **)&v13);
      LastError = v11;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x629,
                    (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
                    v9);
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v15);
    return LastError;
  }
  ProcessHeap = GetProcessHeap();
  v5 = _AllocString<CTHeapAllocPolicy>(ProcessHeap, v4, L"SYSTEM", a2);
  LastError = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x623,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profsvc\\util.cpp",
      (const char *)(unsigned int)v5,
      v12);
    return LastError;
  }
  return 0;
}

```

## disassembly

```asm
0x180024c5c  mov     [rsp-8+arg_10], rbx
0x180024c61  push    rbp
0x180024c62  push    rsi
0x180024c63  push    rdi
0x180024c64  lea     rbp, [rsp-47h]
0x180024c69  sub     rsp, 0C0h
0x180024c70  mov     rax, cs:__security_cookie
0x180024c77  xor     rax, rsp
0x180024c7a  mov     [rbp+57h+var_18], rax
0x180024c7e  mov     qword ptr [rdx], 0
0x180024c85  mov     rdi, rdx
0x180024c88  test    ecx, ecx
0x180024c8a  jnz     short loc_180024CCD
0x180024c8c  call    cs:__imp_GetProcessHeap
0x180024c92  mov     r9, rdi
0x180024c95  lea     r8, aSystem; "SYSTEM"
0x180024c9c  mov     rcx, rax
0x180024c9f  call    ??$_AllocString@VCTHeapAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTHeapAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x180024ca4  mov     ebx, eax
0x180024ca6  test    eax, eax
0x180024ca8  jns     loc_180024DAD
0x180024cae  mov     rcx, [rbp+5Fh]; this
0x180024cb2  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180024cb9  mov     r9d, eax; char *
0x180024cbc  mov     edx, 623h; void *
0x180024cc1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024cc6  mov     eax, ebx
0x180024cc8  jmp     loc_180024DAF
0x180024ccd  mov     r8d, ecx; dwProcessId
0x180024cd0  xor     edx, edx; bInheritHandle
0x180024cd2  mov     ecx, 1000h; dwDesiredAccess
0x180024cd7  call    cs:__imp_OpenProcess
0x180024cdd  mov     [rbp+57h+var_98], rax
0x180024ce1  mov     rbx, rax
0x180024ce4  test    rax, rax
0x180024ce7  jnz     short loc_180024D05
0x180024ce9  mov     rcx, [rbp+5Fh]; this
0x180024ced  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180024cf4  mov     edx, 629h; void *
0x180024cf9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180024cfe  mov     ebx, eax
0x180024d00  jmp     loc_180024D89
0x180024d05  lea     rax, ??_7?$__func@V_lambda_b727b7dc3a79984c737ea01e3c3a200c_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_b727b7dc3a79984c737ea01e3c3a200c_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x180024d0c  mov     [rbp+57h+var_A8], 0
0x180024d14  mov     [rbp+57h+var_88], rax
0x180024d18  lea     rdx, [rbp+57h+var_90]
0x180024d1c  lea     rax, [rbp+57h+var_A0]
0x180024d20  mov     [rbp+57h+var_B0], 0
0x180024d27  mov     [rbp+57h+var_80], rax
0x180024d2b  lea     rcx, [rbp+57h+var_A8]
0x180024d2f  lea     rax, [rbp+57h+var_B0]
0x180024d33  mov     [rbp+57h+var_A0], rbx
0x180024d37  mov     [rbp+57h+var_78], rax
0x180024d3b  lea     rax, [rbp+57h+var_88]
0x180024d3f  mov     [rbp+57h+var_20], rax
0x180024d43  call    ??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)
0x180024d48  mov     rdx, [rbp+57h+var_20]
0x180024d4c  mov     esi, eax
0x180024d4e  test    rdx, rdx
0x180024d51  jz      short loc_180024D62
0x180024d53  mov     rcx, [rdx]
0x180024d56  mov     rax, [rcx+18h]
0x180024d5a  mov     rcx, rdx
0x180024d5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d62  test    esi, esi
0x180024d64  jns     short loc_180024D97
0x180024d66  mov     rcx, [rbp+5Fh]; this
0x180024d6a  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180024d71  mov     r9d, esi; char *
0x180024d74  mov     edx, 62Ch; void *
0x180024d79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024d7e  lea     rcx, [rbp+57h+var_A8]
0x180024d82  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180024d87  mov     ebx, esi
0x180024d89  lea     rcx, [rbp+57h+var_98]
0x180024d8d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180024d92  jmp     loc_180024CC6
0x180024d97  mov     rax, [rbp+57h+var_A8]
0x180024d9b  mov     [rdi], rax
0x180024d9e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180024da2  jz      short loc_180024DAD
0x180024da4  mov     rcx, rbx; hObject
0x180024da7  call    cs:__imp_CloseHandle
0x180024dad  xor     eax, eax
0x180024daf  mov     rcx, [rbp+57h+var_18]
0x180024db3  xor     rcx, rsp; StackCookie
0x180024db6  call    __security_check_cookie
0x180024dbb  mov     rbx, [rsp+0D0h+arg_10]
0x180024dc3  add     rsp, 0C0h
0x180024dca  pop     rdi
0x180024dcb  pop     rsi
0x180024dcc  pop     rbp
0x180024dcd  retn
```
