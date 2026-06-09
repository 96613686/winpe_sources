# _anonymous_namespace_::AddWnfTrigger

- ea: `0x1800f2dc8`
- end: `0x1800f2fdf`
- name: `_anonymous_namespace_::AddWnfTrigger`
- size: `535`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800f3340`
- `0x1800f3900`

## callees

- `0x18000caf4`
- `0x180023874`
- `0x1800c1264`
- `0x1800c18f0`
- `0x1800ca7a8`
- `0x1800f2dc8`
- `0x180107010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800f2f6a`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800f2f92`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800f2f6a`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800f2f92`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1800f2f57`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1800f2f7f`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1800f2f57`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1800f2f7f`

## string_xrefs

- `0x1800f2e0f`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1800f2e5c`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1800f2e8e`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1800f2efa`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1800f2f3d`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`
- `0x1800f2fcd`: `onecoreuap\admin\enterprisemgmt\dynamo\lib\taskcreator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall anonymous_namespace_::AddWnfTrigger(__int64 a1, __int64 a2)
{
  __int64 (__fastcall *v4)(__int64, __int64 *); // rbx
  int v5; // eax
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, __int64, __int64 *); // rbx
  int v8; // eax
  int v9; // eax
  unsigned int i; // ebx
  int v11; // eax
  SAFEARRAY *v12; // rbx
  int v13; // eax
  SAFEARRAY *v14; // rdi
  int v15; // eax
  SAFEARRAY *v17; // [rsp+20h] [rbp-10h] BYREF
  SAFEARRAY *psa; // [rsp+28h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  __int64 v20; // [rsp+50h] [rbp+20h] BYREF
  __int64 v21; // [rsp+60h] [rbp+30h] BYREF
  __int64 v22; // [rsp+68h] [rbp+38h] BYREF

  v22 = 0;
  v4 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a1 + 72LL);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v22);
  v5 = v4(a1, &v22);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x14,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v5,
      (int)v17);
  v21 = 0;
  v6 = v22;
  v7 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v22 + 80LL);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v21);
  v8 = v7(v6, 12, &v21);
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x17,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v8,
      (int)v17);
  v20 = 0;
  v9 = Microsoft::WRL::ComPtr<ITrigger>::As<IWnfStateChangeTrigger>(&v21, &v20);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1A,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v9,
      (int)v17);
  ATL::CComSafeArray<unsigned char,17>::CComSafeArray<unsigned char,17>(&v17, 8);
  for ( i = 0; i < 8; ++i )
  {
    v11 = ATL::CComSafeArray<unsigned char,17>::SetAt(&v17, i, a2 + (int)i);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1F,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
        (const char *)(unsigned int)v11,
        (int)v17);
  }
  v12 = v17;
  v13 = (*(__int64 (__fastcall **)(__int64, SAFEARRAY *))(*(_QWORD *)v20 + 184LL))(v20, v17);
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x22,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v13,
      (int)v17);
  ATL::CComSafeArray<unsigned char,17>::CComSafeArray<unsigned char,17>(&psa, 0);
  v14 = psa;
  v15 = (*(__int64 (__fastcall **)(__int64, SAFEARRAY *))(*(_QWORD *)v20 + 200LL))(v20, psa);
  if ( v15 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\dynamo\\lib\\taskcreator.cpp",
      (const char *)(unsigned int)v15,
      (int)v17);
  if ( v14 && SafeArrayUnlock(v14) >= 0 )
    SafeArrayDestroy(v14);
  if ( v12 && SafeArrayUnlock(v12) >= 0 )
    SafeArrayDestroy(v12);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v20);
  Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v21);
  return Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(&v22);
}

```

## disassembly

```asm
0x1800f2dc8  mov     [rsp-18h+arg_8], rbx
0x1800f2dcd  push    rbp
0x1800f2dce  push    rsi
0x1800f2dcf  push    rdi
0x1800f2dd0  mov     rbp, rsp
0x1800f2dd3  sub     rsp, 30h
0x1800f2dd7  mov     rsi, rdx
0x1800f2dda  mov     rdi, rcx
0x1800f2ddd  mov     [rbp+arg_18], 0
0x1800f2de5  mov     rax, [rcx]
0x1800f2de8  mov     rbx, [rax+48h]
0x1800f2dec  lea     rcx, [rbp+arg_18]
0x1800f2df0  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f2df5  lea     rdx, [rbp+arg_18]
0x1800f2df9  mov     rcx, rdi
0x1800f2dfc  mov     rax, rbx
0x1800f2dff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2e04  mov     rcx, [rbp+18h]; this
0x1800f2e08  test    eax, eax
0x1800f2e0a  jns     short loc_1800F2E21
0x1800f2e0c  mov     r9d, eax; char *
0x1800f2e0f  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f2e16  mov     edx, 14h; void *
0x1800f2e1b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f2e21  mov     [rbp+arg_10], 0
0x1800f2e29  mov     rdi, [rbp+arg_18]
0x1800f2e2d  mov     rax, [rdi]
0x1800f2e30  mov     rbx, [rax+50h]
0x1800f2e34  lea     rcx, [rbp+arg_10]
0x1800f2e38  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f2e3d  lea     r8, [rbp+arg_10]
0x1800f2e41  mov     edx, 0Ch
0x1800f2e46  mov     rcx, rdi
0x1800f2e49  mov     rax, rbx
0x1800f2e4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2e51  mov     rcx, [rbp+18h]; this
0x1800f2e55  test    eax, eax
0x1800f2e57  jns     short loc_1800F2E6E
0x1800f2e59  mov     r9d, eax; char *
0x1800f2e5c  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f2e63  mov     edx, 17h; void *
0x1800f2e68  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f2e6e  mov     [rbp+arg_0], 0
0x1800f2e76  lea     rdx, [rbp+arg_0]
0x1800f2e7a  lea     rcx, [rbp+arg_10]
0x1800f2e7e  call    ??$As@UIWnfStateChangeTrigger@@@?$ComPtr@UITrigger@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWnfStateChangeTrigger@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<ITrigger>::As<IWnfStateChangeTrigger>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IWnfStateChangeTrigger>>)
0x1800f2e83  mov     rcx, [rbp+18h]; this
0x1800f2e87  test    eax, eax
0x1800f2e89  jns     short loc_1800F2EA0
0x1800f2e8b  mov     r9d, eax; char *
0x1800f2e8e  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f2e95  mov     edx, 1Ah; void *
0x1800f2e9a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f2ea0  mov     edx, 8
0x1800f2ea5  lea     rcx, [rbp+var_10]
0x1800f2ea9  call    ??0?$CComSafeArray@E$0BB@@ATL@@QEAA@KJ@Z; ATL::CComSafeArray<uchar,17>::CComSafeArray<uchar,17>(ulong,long)
0x1800f2eae  nop
0x1800f2eaf  xor     ebx, ebx
0x1800f2eb1  movsxd  r8, ebx
0x1800f2eb4  add     r8, rsi
0x1800f2eb7  mov     edx, ebx
0x1800f2eb9  lea     rcx, [rbp+var_10]
0x1800f2ebd  call    ?SetAt@?$CComSafeArray@E$0BB@@ATL@@QEAAJJAEBEH@Z; ATL::CComSafeArray<uchar,17>::SetAt(long,uchar const &,int)
0x1800f2ec2  mov     rcx, [rbp+18h]; this
0x1800f2ec6  test    eax, eax
0x1800f2ec8  js      loc_1800F2FCA
0x1800f2ece  inc     ebx
0x1800f2ed0  cmp     ebx, 8
0x1800f2ed3  jb      short loc_1800F2EB1
0x1800f2ed5  mov     rcx, [rbp+arg_0]
0x1800f2ed9  mov     rax, [rcx]
0x1800f2edc  mov     rbx, [rbp+var_10]
0x1800f2ee0  mov     rdx, rbx
0x1800f2ee3  mov     rax, [rax+0B8h]
0x1800f2eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2eef  mov     rcx, [rbp+18h]; this
0x1800f2ef3  test    eax, eax
0x1800f2ef5  jns     short loc_1800F2F0C
0x1800f2ef7  mov     r9d, eax; char *
0x1800f2efa  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f2f01  mov     edx, 22h ; '"'; void *
0x1800f2f06  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f2f0c  xor     edx, edx
0x1800f2f0e  lea     rcx, [rbp+psa]
0x1800f2f12  call    ??0?$CComSafeArray@E$0BB@@ATL@@QEAA@KJ@Z; ATL::CComSafeArray<uchar,17>::CComSafeArray<uchar,17>(ulong,long)
0x1800f2f17  nop
0x1800f2f18  mov     rcx, [rbp+arg_0]
0x1800f2f1c  mov     rax, [rcx]
0x1800f2f1f  mov     rdi, [rbp+psa]
0x1800f2f23  mov     rdx, rdi
0x1800f2f26  mov     rax, [rax+0C8h]
0x1800f2f2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f2f32  mov     rcx, [rbp+18h]; this
0x1800f2f36  test    eax, eax
0x1800f2f38  jns     short loc_1800F2F4F
0x1800f2f3a  mov     r9d, eax; char *
0x1800f2f3d  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f2f44  mov     edx, 24h ; '$'; void *
0x1800f2f49  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800f2f4f  test    rdi, rdi
0x1800f2f52  jz      short loc_1800F2F77
0x1800f2f54  mov     rcx, rdi; psa
0x1800f2f57  call    cs:__imp_SafeArrayUnlock
0x1800f2f5e  nop     dword ptr [rax+rax+00h]
0x1800f2f63  test    eax, eax
0x1800f2f65  js      short loc_1800F2F77
0x1800f2f67  mov     rcx, rdi; psa
0x1800f2f6a  call    cs:__imp_SafeArrayDestroy
0x1800f2f71  nop     dword ptr [rax+rax+00h]
0x1800f2f76  nop
0x1800f2f77  test    rbx, rbx
0x1800f2f7a  jz      short loc_1800F2F9F
0x1800f2f7c  mov     rcx, rbx; psa
0x1800f2f7f  call    cs:__imp_SafeArrayUnlock
0x1800f2f86  nop     dword ptr [rax+rax+00h]
0x1800f2f8b  test    eax, eax
0x1800f2f8d  js      short loc_1800F2F9F
0x1800f2f8f  mov     rcx, rbx; psa
0x1800f2f92  call    cs:__imp_SafeArrayDestroy
0x1800f2f99  nop     dword ptr [rax+rax+00h]
0x1800f2f9e  nop
0x1800f2f9f  lea     rcx, [rbp+arg_0]
0x1800f2fa3  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f2fa8  nop
0x1800f2fa9  lea     rcx, [rbp+arg_10]
0x1800f2fad  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f2fb2  nop
0x1800f2fb3  lea     rcx, [rbp+arg_18]
0x1800f2fb7  call    ?InternalRelease@?$ComPtr@UIExecAction@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IExecAction>::InternalRelease(void)
0x1800f2fbc  mov     rbx, [rsp+30h+arg_8]
0x1800f2fc1  add     rsp, 30h
0x1800f2fc5  pop     rdi
0x1800f2fc6  pop     rsi
0x1800f2fc7  pop     rbp
0x1800f2fc8  retn
0x1800f2fca  mov     r9d, eax; char *
0x1800f2fcd  lea     r8, aOnecoreuapAdmi_34; "onecoreuap\\admin\\enterprisemgmt\\dyna"...
0x1800f2fd4  mov     edx, 1Fh; void *
0x1800f2fd9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
