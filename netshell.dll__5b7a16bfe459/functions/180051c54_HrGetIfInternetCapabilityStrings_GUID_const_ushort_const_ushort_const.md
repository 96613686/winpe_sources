# HrGetIfInternetCapabilityStrings(_GUID const &,ushort const * *,ushort const * *)

- ea: `0x180051c54`
- end: `0x180051de7`
- name: `?HrGetIfInternetCapabilityStrings@@YAJAEBU_GUID@@PEAPEBG1@Z`
- size: `403`
- prototype: `__int64 __fastcall(const struct _GUID *, const unsigned __int16 **, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005b1cc`

## callees

- `0x18001644c`
- `0x180017674`
- `0x180022294`
- `0x180051c54`
- `0x180065010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180051cf9`
- `ole32!CoCreateInstance` at `0x180051cf9`
- `ole32!CoUninitialize` at `0x180051d2d`
- `ole32!CoUninitialize` at `0x180051dd0`
- `ole32!CoUninitialize` at `0x180051d2d`
- `ole32!CoUninitialize` at `0x180051dd0`
- `ole32!CoInitializeEx` at `0x180051c8c`
- `ole32!CoInitializeEx` at `0x180051c8c`

## string_xrefs

- `0x180051cb0`: `net\config\shell\statmon\smutil.cpp`
- `0x180051d0a`: `net\config\shell\statmon\smutil.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall HrGetIfInternetCapabilityStrings(
        const struct _GUID *a1,
        const unsigned __int16 **a2,
        const unsigned __int16 **a3)
{
  HRESULT v6; // edi
  bool v8; // si
  __int64 v9; // rdx
  char v10; // al
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  int ppv; // [rsp+20h] [rbp-20h]
  int ppva; // [rsp+20h] [rbp-20h]
  __int128 v15; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  int v17; // [rsp+90h] [rbp+50h] BYREF
  LPVOID v18; // [rsp+98h] [rbp+58h] BYREF

  *a2 = SzLoadIds(0x5A88u);
  *a3 = SzLoadIds(0x5A88u);
  v6 = CoInitializeEx(0, 0);
  if ( (int)(v6 + 0x80000000) >= 0 && v6 != -2147417850 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B6,
      (unsigned int)"net\\config\\shell\\statmon\\smutil.cpp",
      (const char *)(unsigned int)v6,
      ppv);
    return (unsigned int)v6;
  }
  v8 = v6 != -2147417850;
  v18 = 0;
  v6 = CoCreateInstance(
         &GUID_a47979d2_c419_11d9_a5b4_001185ad2b89,
         0,
         4u,
         &GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b,
         &v18);
  if ( v6 < 0 )
  {
    v9 = 452;
    goto LABEL_7;
  }
  v17 = 0;
  v15 = (__int128)*a1;
  v6 = (*(__int64 (__fastcall **)(LPVOID, __int128 *, int *))(*(_QWORD *)v18 + 208LL))(v18, &v15, &v17);
  if ( v6 < 0 )
  {
    v9 = 460;
LABEL_7:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"net\\config\\shell\\statmon\\smutil.cpp",
      (const char *)(unsigned int)v6,
      ppva);
    ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>((__int64 *)&v18);
    if ( v8 )
      CoUninitialize();
    return (unsigned int)v6;
  }
  v10 = v17;
  if ( (v17 & 8) != 0 )
  {
    v11 = 23175;
  }
  else if ( (v17 & 4) != 0 )
  {
    v11 = 23174;
  }
  else
  {
    if ( (v17 & 1) == 0 )
      goto LABEL_18;
    v11 = 23173;
  }
  *a2 = SzLoadIds(v11);
  v10 = v17;
LABEL_18:
  if ( (v10 & 0x20) != 0 )
  {
    v12 = 23175;
LABEL_24:
    *a3 = SzLoadIds(v12);
    goto LABEL_25;
  }
  if ( (v10 & 0x10) != 0 )
  {
    v12 = 23174;
    goto LABEL_24;
  }
  if ( (v10 & 1) != 0 )
  {
    v12 = 23173;
    goto LABEL_24;
  }
LABEL_25:
  ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>((__int64 *)&v18);
  if ( v8 )
    CoUninitialize();
  return 0;
}

```

## disassembly

```asm
0x180051c54  push    rbp
0x180051c56  push    rbx
0x180051c57  push    rsi
0x180051c58  push    rdi
0x180051c59  push    r12
0x180051c5b  push    r14
0x180051c5d  push    r15
0x180051c5f  mov     rbp, rsp
0x180051c62  sub     rsp, 40h
0x180051c66  mov     r14, r8
0x180051c69  mov     r15, rdx
0x180051c6c  mov     r12, rcx
0x180051c6f  mov     ebx, 5A88h
0x180051c74  mov     ecx, ebx; unsigned int
0x180051c76  call    ?SzLoadIds@@YAPEBGI@Z; SzLoadIds(uint)
0x180051c7b  mov     [r15], rax
0x180051c7e  mov     ecx, ebx; unsigned int
0x180051c80  call    ?SzLoadIds@@YAPEBGI@Z; SzLoadIds(uint)
0x180051c85  mov     [r14], rax
0x180051c88  xor     edx, edx; dwCoInit
0x180051c8a  xor     ecx, ecx; pvReserved
0x180051c8c  call    cs:__imp_CoInitializeEx
0x180051c92  mov     edi, eax
0x180051c94  mov     eax, 80000000h
0x180051c99  lea     ecx, [rdi+rax]
0x180051c9c  mov     edx, 80010106h
0x180051ca1  test    eax, ecx
0x180051ca3  jnz     short loc_180051CC8
0x180051ca5  cmp     edi, edx
0x180051ca7  jz      short loc_180051CC8
0x180051ca9  mov     rcx, [rbp+38h]; this
0x180051cad  mov     r9d, edi; char *
0x180051cb0  lea     r8, aNetConfigShell; "net\\config\\shell\\statmon\\smutil.cpp"
0x180051cb7  mov     edx, 1B6h; void *
0x180051cbc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051cc1  mov     eax, edi
0x180051cc3  jmp     loc_180051DD8
0x180051cc8  mov     bl, 1
0x180051cca  movzx   esi, bl
0x180051ccd  xor     eax, eax
0x180051ccf  cmp     edi, edx
0x180051cd1  cmovz   esi, eax
0x180051cd4  mov     [rbp+arg_8], sil
0x180051cd8  mov     [rbp+arg_18], rax
0x180051cdc  lea     rax, [rbp+arg_18]
0x180051ce0  mov     qword ptr [rsp+40h+ppv], rax; int
0x180051ce5  lea     r9, _GUID_d0074ffd_570f_4a9b_8d69_199fdba5723b; riid
0x180051cec  xor     edx, edx; pUnkOuter
0x180051cee  lea     r8d, [rdx+4]; dwClsContext
0x180051cf2  lea     rcx, _GUID_a47979d2_c419_11d9_a5b4_001185ad2b89; rclsid
0x180051cf9  call    cs:__imp_CoCreateInstance
0x180051cff  mov     edi, eax
0x180051d01  test    eax, eax
0x180051d03  jns     short loc_180051D35
0x180051d05  mov     edx, 1C4h; void *
0x180051d0a  lea     r8, aNetConfigShell; "net\\config\\shell\\statmon\\smutil.cpp"
0x180051d11  mov     r9d, edi; char *
0x180051d14  mov     rcx, [rbp+38h]; this
0x180051d18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051d1d  nop
0x180051d1e  lea     rcx, [rbp+arg_18]
0x180051d22  call    ??1?$CComPtrBase@UIUPnPService@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(void)
0x180051d27  nop
0x180051d28  test    sil, sil
0x180051d2b  jz      short loc_180051CC1
0x180051d2d  call    cs:__imp_CoUninitialize
0x180051d33  jmp     short loc_180051CC1
0x180051d35  mov     [rbp+arg_10], 0
0x180051d3c  mov     rcx, [rbp+arg_18]
0x180051d40  movups  xmm0, xmmword ptr [r12]
0x180051d45  movdqu  [rbp+var_10], xmm0
0x180051d4a  mov     rax, [rcx]
0x180051d4d  lea     r8, [rbp+arg_10]
0x180051d51  lea     rdx, [rbp+var_10]
0x180051d55  mov     rax, [rax+0D0h]
0x180051d5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051d61  mov     edi, eax
0x180051d63  test    eax, eax
0x180051d65  jns     short loc_180051D6E
0x180051d67  mov     edx, 1CCh
0x180051d6c  jmp     short loc_180051D0A
0x180051d6e  mov     eax, [rbp+arg_10]
0x180051d71  mov     edi, 5A87h
0x180051d76  lea     r12d, [rdi-1]
0x180051d7a  test    al, 8
0x180051d7c  jz      short loc_180051D82
0x180051d7e  mov     ecx, edi
0x180051d80  jmp     short loc_180051D94
0x180051d82  test    al, 4
0x180051d84  jz      short loc_180051D8B
0x180051d86  mov     ecx, r12d
0x180051d89  jmp     short loc_180051D94
0x180051d8b  test    bl, al
0x180051d8d  jz      short loc_180051D9F
0x180051d8f  mov     ecx, 5A85h; unsigned int
0x180051d94  call    ?SzLoadIds@@YAPEBGI@Z; SzLoadIds(uint)
0x180051d99  mov     [r15], rax
0x180051d9c  mov     eax, [rbp+arg_10]
0x180051d9f  test    al, 20h
0x180051da1  jz      short loc_180051DA7
0x180051da3  mov     ecx, edi
0x180051da5  jmp     short loc_180051DB9
0x180051da7  test    al, 10h
0x180051da9  jz      short loc_180051DB0
0x180051dab  mov     ecx, r12d
0x180051dae  jmp     short loc_180051DB9
0x180051db0  test    bl, al
0x180051db2  jz      short loc_180051DC1
0x180051db4  mov     ecx, 5A85h; unsigned int
0x180051db9  call    ?SzLoadIds@@YAPEBGI@Z; SzLoadIds(uint)
0x180051dbe  mov     [r14], rax
0x180051dc1  lea     rcx, [rbp+arg_18]
0x180051dc5  call    ??1?$CComPtrBase@UIUPnPService@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUPnPService>::~CComPtrBase<IUPnPService>(void)
0x180051dca  nop
0x180051dcb  test    sil, sil
0x180051dce  jz      short loc_180051DD6
0x180051dd0  call    cs:__imp_CoUninitialize
0x180051dd6  xor     eax, eax
0x180051dd8  add     rsp, 40h
0x180051ddc  pop     r15
0x180051dde  pop     r14
0x180051de0  pop     r12
0x180051de2  pop     rdi
0x180051de3  pop     rsi
0x180051de4  pop     rbx
0x180051de5  pop     rbp
0x180051de6  retn
```
