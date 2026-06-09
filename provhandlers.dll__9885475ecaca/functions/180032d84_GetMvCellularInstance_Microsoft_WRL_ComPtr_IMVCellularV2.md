# GetMvCellularInstance(Microsoft::WRL::ComPtr<IMVCellularV2> &)

- ea: `0x180032d84`
- end: `0x180032f93`
- name: `?GetMvCellularInstance@@YAJAEAV?$ComPtr@UIMVCellularV2@@@WRL@Microsoft@@@Z`
- size: `527`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180027e90`
- `0x180030720`

## callees

- `0x1800076a4`
- `0x180032d84`
- `0x180032f9c`
- `0x18003755c`
- `0x18003b9a0`
- `0x18003f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180032e37`
- `msvcrt!??3@YAXPEAX@Z` at `0x180032f76`
- `msvcrt!??3@YAXPEAX@Z` at `0x180032e37`
- `msvcrt!??3@YAXPEAX@Z` at `0x180032f76`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032e7b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180032e7b`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180032e46`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180032e46`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetMvCellularInstance(unsigned __int16 *a1)
{
  int Configuration; // eax
  const unsigned __int16 *v3; // rcx
  HRESULT v4; // ebx
  OLECHAR *v6; // rdi
  __int64 v7; // rdx
  HRESULT v8; // eax
  LPVOID v9; // rcx
  int v10; // eax
  LPVOID v11; // rcx
  LPVOID v12; // rcx
  LPVOID v13; // rbx
  __int64 v14; // rdx
  int ppv; // [rsp+20h] [rbp-58h]
  int ppva; // [rsp+20h] [rbp-58h]
  LPVOID v17; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v18; // [rsp+38h] [rbp-40h] BYREF
  LPCOLESTR lpsz[2]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v20; // [rsp+50h] [rbp-28h]
  GUID pclsid; // [rsp+58h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]

  v18 = 0;
  Configuration = MvGetConfiguration(a1, 0, &v18);
  v4 = Configuration;
  if ( Configuration < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x11,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\utils.cpp",
      (const char *)(unsigned int)Configuration,
      ppv);
    return (unsigned int)v4;
  }
  pclsid = 0;
  *(_OWORD *)lpsz = 0;
  v20 = 0;
  if ( (unsigned __int64)v18 >> 1 )
    std::vector<unsigned short>::_Reallocate((__int64)lpsz, (unsigned __int64)v18 >> 1);
  v6 = (OLECHAR *)lpsz[0];
  v4 = MvGetConfiguration(v3, (unsigned __int8 *)lpsz[0], &v18);
  if ( v4 < 0 )
  {
    v7 = 23;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\utils.cpp",
      (const char *)(unsigned int)v4,
      ppv);
LABEL_9:
    if ( v6 )
      operator delete(v6);
    return (unsigned int)v4;
  }
  v4 = CLSIDFromString(v6, &pclsid);
  if ( v4 < 0 )
  {
    v7 = 26;
    goto LABEL_8;
  }
  v17 = 0;
  v8 = CoCreateInstance(&pclsid, 0, 1u, &GUID_f7882432_46e0_4985_8e85_56712af64b94, &v17);
  v4 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\utils.cpp",
      (const char *)(unsigned int)v8,
      ppva);
    v9 = v17;
    if ( v17 )
    {
      v17 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v9 + 16LL))(v9);
    }
    goto LABEL_9;
  }
  v10 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)v17 + 24LL))(v17);
  v4 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x20,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\uicc2\\utils.cpp",
      (const char *)(unsigned int)v10,
      ppva);
    v11 = v17;
    if ( v17 )
    {
      v17 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v11 + 16LL))(v11);
    }
    goto LABEL_9;
  }
  v12 = v17;
  if ( *(LPVOID *)a1 != v17 )
  {
    v13 = v17;
    if ( v17 )
    {
      (*(void (**)(void))(*(_QWORD *)v17 + 8LL))();
      v12 = v17;
    }
    v14 = *(_QWORD *)a1;
    *(_QWORD *)a1 = v13;
    if ( v14 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
      v12 = v17;
    }
  }
  if ( v12 )
  {
    v17 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v12 + 16LL))(v12);
  }
  if ( v6 )
    operator delete(v6);
  return 0;
}

```

## disassembly

```asm
0x180032d84  push    rbp
0x180032d86  push    rbx
0x180032d87  push    rsi
0x180032d88  push    rdi
0x180032d89  mov     rbp, rsp
0x180032d8c  sub     rsp, 78h
0x180032d90  mov     rax, cs:__security_cookie
0x180032d97  xor     rax, rsp
0x180032d9a  mov     [rbp+var_10], rax
0x180032d9e  mov     rsi, rcx
0x180032da1  mov     [rbp+var_40], 0
0x180032da8  lea     r8, [rbp+var_40]; unsigned int *
0x180032dac  xor     edx, edx; unsigned __int8 *
0x180032dae  call    ?MvGetConfiguration@@YAJPEBGPEAEPEAK@Z; MvGetConfiguration(ushort const *,uchar *,ulong *)
0x180032db3  mov     ebx, eax
0x180032db5  test    eax, eax
0x180032db7  jns     short loc_180032DD8
0x180032db9  mov     rcx, [rbp+20h]; this
0x180032dbd  mov     r9d, eax; char *
0x180032dc0  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180032dc7  mov     edx, 11h; void *
0x180032dcc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032dd1  mov     eax, ebx
0x180032dd3  jmp     loc_180032F7E
0x180032dd8  xorps   xmm0, xmm0
0x180032ddb  movups  xmmword ptr [rbp+pclsid.Data1], xmm0
0x180032ddf  xorps   xmm1, xmm1
0x180032de2  movdqu  xmmword ptr [rbp+lpsz], xmm1
0x180032de7  mov     [rbp+var_28], 0
0x180032def  mov     edx, [rbp+var_40]
0x180032df2  shr     rdx, 1
0x180032df5  jz      short loc_180032E00
0x180032df7  lea     rcx, [rbp+lpsz]
0x180032dfb  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x180032e00  lea     r8, [rbp+var_40]; unsigned int *
0x180032e04  mov     rdi, [rbp+lpsz]
0x180032e08  mov     rdx, rdi; unsigned __int8 *
0x180032e0b  call    ?MvGetConfiguration@@YAJPEBGPEAEPEAK@Z; MvGetConfiguration(ushort const *,uchar *,ulong *)
0x180032e10  mov     ebx, eax
0x180032e12  test    eax, eax
0x180032e14  jns     short loc_180032E3F
0x180032e16  mov     edx, 17h; void *
0x180032e1b  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180032e22  mov     r9d, ebx; char *
0x180032e25  mov     rcx, [rbp+20h]; this
0x180032e29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032e2e  nop
0x180032e2f  test    rdi, rdi
0x180032e32  jz      short loc_180032DD1
0x180032e34  mov     rcx, rdi
0x180032e37  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180032e3d  jmp     short loc_180032DD1
0x180032e3f  lea     rdx, [rbp+pclsid]; pclsid
0x180032e43  mov     rcx, rdi; lpsz
0x180032e46  call    cs:__imp_CLSIDFromString
0x180032e4c  mov     ebx, eax
0x180032e4e  test    eax, eax
0x180032e50  jns     short loc_180032E59
0x180032e52  mov     edx, 1Ah
0x180032e57  jmp     short loc_180032E1B
0x180032e59  mov     [rbp+var_48], 0
0x180032e61  lea     rax, [rbp+var_48]
0x180032e65  mov     qword ptr [rsp+78h+ppv], rax; int
0x180032e6a  lea     r9, _GUID_f7882432_46e0_4985_8e85_56712af64b94; riid
0x180032e71  xor     edx, edx; pUnkOuter
0x180032e73  lea     r8d, [rdx+1]; dwClsContext
0x180032e77  lea     rcx, [rbp+pclsid]; rclsid
0x180032e7b  call    cs:__imp_CoCreateInstance
0x180032e81  mov     ebx, eax
0x180032e83  test    eax, eax
0x180032e85  jns     short loc_180032EC3
0x180032e87  mov     rcx, [rbp+20h]; this
0x180032e8b  mov     r9d, eax; char *
0x180032e8e  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180032e95  mov     edx, 1Fh; void *
0x180032e9a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032e9f  nop
0x180032ea0  mov     rcx, [rbp+var_48]
0x180032ea4  test    rcx, rcx
0x180032ea7  jz      short loc_180032EBE
0x180032ea9  mov     [rbp+var_48], 0
0x180032eb1  mov     rax, [rcx]
0x180032eb4  mov     rax, [rax+10h]
0x180032eb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ebd  nop
0x180032ebe  jmp     loc_180032E2F
0x180032ec3  mov     rcx, [rbp+var_48]
0x180032ec7  mov     rax, [rcx]
0x180032eca  mov     rax, [rax+18h]
0x180032ece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032ed3  mov     ebx, eax
0x180032ed5  test    eax, eax
0x180032ed7  jns     short loc_180032F15
0x180032ed9  mov     rcx, [rbp+20h]; this
0x180032edd  mov     r9d, eax; char *
0x180032ee0  lea     r8, aOnecoreuapAdmi_0; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180032ee7  mov     edx, 20h ; ' '; void *
0x180032eec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032ef1  nop
0x180032ef2  mov     rcx, [rbp+var_48]
0x180032ef6  test    rcx, rcx
0x180032ef9  jz      short loc_180032F10
0x180032efb  mov     [rbp+var_48], 0
0x180032f03  mov     rax, [rcx]
0x180032f06  mov     rax, [rax+10h]
0x180032f0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f0f  nop
0x180032f10  jmp     loc_180032E2F
0x180032f15  mov     rcx, [rbp+var_48]
0x180032f19  cmp     [rsi], rcx
0x180032f1c  jz      short loc_180032F54
0x180032f1e  mov     rbx, rcx
0x180032f21  test    rcx, rcx
0x180032f24  jz      short loc_180032F36
0x180032f26  mov     rax, [rcx]
0x180032f29  mov     rax, [rax+8]
0x180032f2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f32  mov     rcx, [rbp+var_48]
0x180032f36  mov     rdx, [rsi]
0x180032f39  mov     [rsi], rbx
0x180032f3c  test    rdx, rdx
0x180032f3f  jz      short loc_180032F54
0x180032f41  mov     rax, [rdx]
0x180032f44  mov     rcx, rdx
0x180032f47  mov     rax, [rax+10h]
0x180032f4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f50  mov     rcx, [rbp+var_48]
0x180032f54  test    rcx, rcx
0x180032f57  jz      short loc_180032F6E
0x180032f59  mov     [rbp+var_48], 0
0x180032f61  mov     rax, [rcx]
0x180032f64  mov     rax, [rax+10h]
0x180032f68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f6d  nop
0x180032f6e  test    rdi, rdi
0x180032f71  jz      short loc_180032F7C
0x180032f73  mov     rcx, rdi
0x180032f76  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180032f7c  xor     eax, eax
0x180032f7e  mov     rcx, [rbp+var_10]
0x180032f82  xor     rcx, rsp; StackCookie
0x180032f85  call    __security_check_cookie
0x180032f8a  add     rsp, 78h
0x180032f8e  pop     rdi
0x180032f8f  pop     rsi
0x180032f90  pop     rbx
0x180032f91  pop     rbp
0x180032f92  retn
```
