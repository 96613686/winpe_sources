# GetProcessNameFromPID(ulong,ushort * *)

- ea: `0x180027470`
- end: `0x1800275f5`
- name: `?GetProcessNameFromPID@@YAJKPEAPEAG@Z`
- size: `389`
- prototype: `__int64 __fastcall(DWORD dwProcessId, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180038e24`
- `0x18004bb10`

## callees

- `0x180005330`
- `0x1800084bc`
- `0x18001e690`
- `0x180027470`
- `0x18002df48`
- `0x180030ad0`
- `0x1800333a0`
- `0x18003bc70`
- `0x180056010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800274a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800274a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800275c7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800275c7`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800274f1`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800274f1`

## string_xrefs

- `0x1800274cc`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18002750d`: `onecore\ds\security\gina\profile\profsvc\util.cpp`
- `0x18002758a`: `onecore\ds\security\gina\profile\profsvc\util.cpp`

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
  HANDLE v15; // [rsp+38h] [rbp-41h] BYREF
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
              &v13,
              v16);
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
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v13);
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
0x180027470  mov     [rsp-8+arg_10], rbx
0x180027475  push    rbp
0x180027476  push    rsi
0x180027477  push    rdi
0x180027478  lea     rbp, [rsp-47h]
0x18002747d  sub     rsp, 0C0h
0x180027484  mov     rax, cs:__security_cookie
0x18002748b  xor     rax, rsp
0x18002748e  mov     [rbp+57h+var_18], rax
0x180027492  mov     qword ptr [rdx], 0
0x180027499  mov     rdi, rdx
0x18002749c  test    ecx, ecx
0x18002749e  jnz     short loc_1800274E7
0x1800274a0  call    cs:__imp_GetProcessHeap
0x1800274a7  nop     dword ptr [rax+rax+00h]
0x1800274ac  mov     r9, rdi
0x1800274af  lea     r8, aSystem; "SYSTEM"
0x1800274b6  mov     rcx, rax
0x1800274b9  call    ??$_AllocString@VCTHeapAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTHeapAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800274be  mov     ebx, eax
0x1800274c0  test    eax, eax
0x1800274c2  jns     loc_1800275D3
0x1800274c8  mov     rcx, [rbp+5Fh]; this
0x1800274cc  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800274d3  mov     r9d, eax; char *
0x1800274d6  mov     edx, 623h; void *
0x1800274db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800274e0  mov     eax, ebx
0x1800274e2  jmp     loc_1800275D5
0x1800274e7  mov     r8d, ecx; dwProcessId
0x1800274ea  xor     edx, edx; bInheritHandle
0x1800274ec  mov     ecx, 1000h; dwDesiredAccess
0x1800274f1  call    cs:__imp_OpenProcess
0x1800274f8  nop     dword ptr [rax+rax+00h]
0x1800274fd  mov     [rbp+57h+var_98], rax
0x180027501  mov     rbx, rax
0x180027504  test    rax, rax
0x180027507  jnz     short loc_180027525
0x180027509  mov     rcx, [rbp+5Fh]; this
0x18002750d  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180027514  mov     edx, 629h; void *
0x180027519  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002751e  mov     ebx, eax
0x180027520  jmp     loc_1800275A9
0x180027525  lea     rax, ??_7?$__func@V_lambda_b727b7dc3a79984c737ea01e3c3a200c_@@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_b727b7dc3a79984c737ea01e3c3a200c_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x18002752c  mov     [rbp+57h+var_A8], 0
0x180027534  mov     [rbp+57h+var_88], rax
0x180027538  lea     rdx, [rbp+57h+var_90]
0x18002753c  lea     rax, [rbp+57h+var_A0]
0x180027540  mov     [rbp+57h+var_B0], 0
0x180027547  mov     [rbp+57h+var_80], rax
0x18002754b  lea     rcx, [rbp+57h+var_A8]
0x18002754f  lea     rax, [rbp+57h+var_B0]
0x180027553  mov     [rbp+57h+var_A0], rbx
0x180027557  mov     [rbp+57h+var_78], rax
0x18002755b  lea     rax, [rbp+57h+var_88]
0x18002755f  mov     [rbp+57h+var_20], rax
0x180027563  call    ??$AdaptFixedSizeToAllocatedResult@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@AEBV?$function@$$A6AJPEAG_KPEA_K@Z@wistd@@@Z; wil::AdaptFixedSizeToAllocatedResult<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,wistd::function<long (ushort *,unsigned __int64,unsigned __int64 *)> const &)
0x180027568  mov     rdx, [rbp+57h+var_20]
0x18002756c  mov     esi, eax
0x18002756e  test    rdx, rdx
0x180027571  jz      short loc_180027582
0x180027573  mov     rcx, [rdx]
0x180027576  mov     rax, [rcx+18h]
0x18002757a  mov     rcx, rdx
0x18002757d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027582  test    esi, esi
0x180027584  jns     short loc_1800275B7
0x180027586  mov     rcx, [rbp+5Fh]; this
0x18002758a  lea     r8, aOnecoreDsSecur_14; "onecore\\ds\\security\\gina\\profile\\p"...
0x180027591  mov     r9d, esi; char *
0x180027594  mov     edx, 62Ch; void *
0x180027599  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002759e  lea     rcx, [rbp+57h+var_A8]
0x1800275a2  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?FreeProcessHeap@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800275a7  mov     ebx, esi
0x1800275a9  lea     rcx, [rbp+57h+var_98]
0x1800275ad  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800275b2  jmp     loc_1800274E0
0x1800275b7  mov     rax, [rbp+57h+var_A8]
0x1800275bb  mov     [rdi], rax
0x1800275be  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800275c2  jz      short loc_1800275D3
0x1800275c4  mov     rcx, rbx; hObject
0x1800275c7  call    cs:__imp_CloseHandle
0x1800275ce  nop     dword ptr [rax+rax+00h]
0x1800275d3  xor     eax, eax
0x1800275d5  mov     rcx, [rbp+57h+var_18]
0x1800275d9  xor     rcx, rsp; StackCookie
0x1800275dc  call    __security_check_cookie
0x1800275e1  mov     rbx, [rsp+0D0h+arg_10]
0x1800275e9  add     rsp, 0C0h
0x1800275f0  pop     rdi
0x1800275f1  pop     rsi
0x1800275f2  pop     rbp
0x1800275f3  retn
```
