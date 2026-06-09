# GetErrorDescriptionSDK

- ea: `0x180016b60`
- end: `0x180016cab`
- name: `GetErrorDescriptionSDK`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180016128`

## callees

- `0x180002770`
- `0x180016b60`
- `0x18002f0e0`
- `0x180031010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180016bc0`
- `ole32!CoCreateInstance` at `0x180016bc0`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetErrorDescriptionSDK(unsigned int a1)
{
  __int64 v2; // rbx
  LPVOID ppv; // [rsp+40h] [rbp-9h] BYREF
  __int64 v5; // [rsp+48h] [rbp-1h] BYREF
  __int64 v6; // [rsp+50h] [rbp+7h] BYREF
  __int64 v7; // [rsp+58h] [rbp+Fh] BYREF
  _OWORD v8[3]; // [rsp+60h] [rbp+17h] BYREF

  memset(v8, 0, 44);
  ppv = 0;
  v7 = 0;
  v5 = 0;
  v6 = 0;
  if ( CoCreateInstance(&CLSID_EXTENDEDERRORINFO, 0, 1u, &IID_IErrorRecords, &ppv) < 0
    || (*(GUID *)((char *)v8 + 8) = CLSID_MSPersist,
        *(_QWORD *)&v8[0] = a1,
        memset((char *)&v8[1] + 8, 0, 20),
        (*(int (__fastcall **)(LPVOID, _OWORD *, __int64, _QWORD, _QWORD, _DWORD))(*(_QWORD *)ppv + 24LL))(
          ppv,
          v8,
          0x10000000,
          0,
          0,
          0) < 0)
    || (**(int (__fastcall ***)(LPVOID, GUID *, __int64 *))ppv)(ppv, &IID_IErrorInfo, &v5) < 0
    || (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v5 + 40LL))(v5, &v6) < 0 )
  {
    v2 = 0;
  }
  else
  {
    v2 = v6;
  }
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v5);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&v7);
  CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(&ppv);
  return v2;
}

```

## disassembly

```asm
0x180016b60  mov     [rsp-8+arg_8], rbx
0x180016b65  push    rbp
0x180016b66  lea     rbp, [rsp-57h]
0x180016b6b  sub     rsp, 0A0h
0x180016b72  mov     rax, cs:__security_cookie
0x180016b79  xor     rax, rsp
0x180016b7c  mov     [rbp+57h+var_10], rax
0x180016b80  mov     ebx, ecx
0x180016b82  xorps   xmm0, xmm0
0x180016b85  xor     eax, eax
0x180016b87  movups  [rbp+57h+var_40], xmm0
0x180016b8b  movups  [rbp+57h+var_30], xmm0
0x180016b8f  movups  [rbp+57h+var_30+0Ch], xmm0
0x180016b93  mov     [rbp+57h+var_60], rax
0x180016b97  mov     [rbp+57h+var_48], rax
0x180016b9b  mov     [rbp+57h+var_58], rax
0x180016b9f  mov     [rbp+57h+var_50], rax
0x180016ba3  lea     rax, [rbp+57h+var_60]
0x180016ba7  mov     [rsp+0A0h+ppv], rax; ppv
0x180016bac  lea     r9, IID_IErrorRecords; riid
0x180016bb3  xor     edx, edx; pUnkOuter
0x180016bb5  lea     r8d, [rdx+1]; dwClsContext
0x180016bb9  lea     rcx, CLSID_EXTENDEDERRORINFO; rclsid
0x180016bc0  call    cs:__imp_CoCreateInstance
0x180016bc7  nop     dword ptr [rax+rax+00h]
0x180016bcc  test    eax, eax
0x180016bce  js      loc_180016C6B
0x180016bd4  movups  xmm0, xmmword ptr cs:?CLSID_MSPersist@@3U_GUID@@B.Data1; _GUID const CLSID_MSPersist ...
0x180016bdb  movdqu  [rbp+57h+var_40+8], xmm0
0x180016be0  mov     [rbp+57h+var_18], 0
0x180016be7  mov     dword ptr [rbp+57h+var_40+4], 0
0x180016bee  mov     dword ptr [rbp+57h+var_40], ebx
0x180016bf1  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180016bf8  movdqu  [rbp+57h+var_30+8], xmm0
0x180016bfd  mov     rcx, [rbp+57h+var_60]
0x180016c01  mov     rax, [rcx]
0x180016c04  mov     [rsp+0A0h+var_78], 0
0x180016c0c  mov     [rsp+0A0h+ppv], 0
0x180016c15  xor     r9d, r9d
0x180016c18  mov     r8d, 10000000h
0x180016c1e  lea     rdx, [rbp+57h+var_40]
0x180016c22  mov     rax, [rax+18h]
0x180016c26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c2b  test    eax, eax
0x180016c2d  js      short loc_180016C6B
0x180016c2f  mov     rcx, [rbp+57h+var_60]
0x180016c33  mov     rax, [rcx]
0x180016c36  lea     r8, [rbp+57h+var_58]
0x180016c3a  lea     rdx, IID_IErrorInfo
0x180016c41  mov     rax, [rax]
0x180016c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c49  test    eax, eax
0x180016c4b  js      short loc_180016C6B
0x180016c4d  mov     rcx, [rbp+57h+var_58]
0x180016c51  mov     rax, [rcx]
0x180016c54  lea     rdx, [rbp+57h+var_50]
0x180016c58  mov     rax, [rax+28h]
0x180016c5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016c61  test    eax, eax
0x180016c63  js      short loc_180016C6B
0x180016c65  mov     rbx, [rbp+57h+var_50]
0x180016c69  jmp     short loc_180016C6D
0x180016c6b  xor     ebx, ebx
0x180016c6d  lea     rcx, [rbp+57h+var_58]
0x180016c71  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180016c76  nop
0x180016c77  lea     rcx, [rbp+57h+var_48]
0x180016c7b  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180016c80  nop
0x180016c81  lea     rcx, [rbp+57h+var_60]
0x180016c85  call    ??1?$CAutoRefc@UIWinInetHttpInfo@@@@QEAA@XZ; CAutoRefc<IWinInetHttpInfo>::~CAutoRefc<IWinInetHttpInfo>(void)
0x180016c8a  mov     rax, rbx
0x180016c8d  mov     rcx, [rbp+57h+var_10]
0x180016c91  xor     rcx, rsp; StackCookie
0x180016c94  call    __security_check_cookie
0x180016c99  mov     rbx, [rsp+0A0h+arg_8]
0x180016ca1  add     rsp, 0A0h
0x180016ca8  pop     rbp
0x180016ca9  retn
```
