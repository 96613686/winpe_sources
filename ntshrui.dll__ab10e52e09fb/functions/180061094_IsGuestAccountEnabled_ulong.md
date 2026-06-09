# IsGuestAccountEnabled(ulong)

- ea: `0x180061094`
- end: `0x1800611c1`
- name: `?IsGuestAccountEnabled@@YAHK@Z`
- size: `301`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800620b4`

## callees

- `0x180008900`
- `0x1800222cc`
- `0x180061094`
- `0x180078010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006118a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006118a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800610c7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800610c7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061194`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180061194`
- `SspiCli!LogonUserExExW` at `0x180061177`
- `SspiCli!LogonUserExExW` at `0x180061177`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall IsGuestAccountEnabled()
{
  unsigned int v0; // edi
  int (__fastcall *v1)(LPVOID, __int64, __int64 *); // rbx
  HANDLE hObject[2]; // [rsp+60h] [rbp+17h] BYREF
  __int128 v4; // [rsp+70h] [rbp+27h] BYREF
  int v5; // [rsp+80h] [rbp+37h]
  LPVOID ppv; // [rsp+B8h] [rbp+6Fh] BYREF
  __int64 v7; // [rsp+C0h] [rbp+77h] BYREF
  LPVOID pv; // [rsp+C8h] [rbp+7Fh] BYREF

  v0 = 0;
  ppv = 0;
  if ( CoCreateInstance(&CLSID_LocalUserAccounts, 0, 1u, &GUID_3c708557_c99d_4fa3_9231_56518418b4e4, &ppv) >= 0 )
  {
    v7 = 0;
    v1 = *(int (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)ppv + 80LL);
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v7);
    if ( v1(ppv, 501, &v7) >= 0 )
    {
      pv = 0;
      v4 = PKEY_SAM_Name;
      v5 = 2;
      if ( (int)wil::PropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(&v7, &v4, &pv) >= 0 )
      {
        hObject[0] = 0;
        if ( (unsigned int)LogonUserExExW(pv, L".", &WindowName, 3, 0, 0, hObject, 0, 0, 0, 0) )
        {
          v0 = 1;
          CloseHandle(hObject[0]);
        }
        CoTaskMemFree(pv);
      }
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&v7);
  }
  return v0;
}

```

## disassembly

```asm
0x180061094  push    rbp
0x180061096  push    rbx
0x180061097  push    rdi
0x180061098  lea     rbp, [rsp-47h]
0x18006109d  sub     rsp, 90h
0x1800610a4  xor     edi, edi
0x1800610a6  mov     [rbp+57h+arg_8], rdi
0x1800610aa  lea     rax, [rbp+57h+arg_8]
0x1800610ae  mov     [rsp+0A0h+ppv], rax; ppv
0x1800610b3  lea     r9, _GUID_3c708557_c99d_4fa3_9231_56518418b4e4; riid
0x1800610ba  xor     edx, edx; pUnkOuter
0x1800610bc  lea     r8d, [rdi+1]; dwClsContext
0x1800610c0  lea     rcx, CLSID_LocalUserAccounts; rclsid
0x1800610c7  call    cs:__imp_CoCreateInstance
0x1800610cd  test    eax, eax
0x1800610cf  js      loc_1800611B4
0x1800610d5  mov     [rbp+57h+arg_10], rdi
0x1800610d9  mov     rax, [rbp+57h+arg_8]
0x1800610dd  mov     rcx, [rax]
0x1800610e0  mov     rbx, [rcx+50h]
0x1800610e4  lea     rcx, [rbp+57h+arg_10]
0x1800610e8  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800610ed  lea     r8, [rbp+57h+arg_10]
0x1800610f1  mov     edx, 1F5h
0x1800610f6  mov     rcx, [rbp+57h+arg_8]
0x1800610fa  mov     rax, rbx
0x1800610fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061102  test    eax, eax
0x180061104  js      loc_18006119A
0x18006110a  mov     [rbp+57h+pv], rdi
0x18006110e  movups  xmm0, cs:PKEY_SAM_Name
0x180061115  movaps  [rbp+57h+var_30], xmm0
0x180061119  mov     eax, cs:dword_18007E730
0x18006111f  mov     [rbp+57h+var_20], eax
0x180061122  lea     r8, [rbp+57h+pv]
0x180061126  lea     rdx, [rbp+57h+var_30]
0x18006112a  lea     rcx, [rbp+57h+arg_10]
0x18006112e  call    ??$GetString@U_tagpropertykey@@@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEBAJU_tagpropertykey@@PEAPEAG@Z; wil::PropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x180061133  test    eax, eax
0x180061135  js      short loc_18006119A
0x180061137  mov     [rbp+57h+hObject], rdi
0x18006113b  mov     [rsp+0A0h+var_50], rdi
0x180061140  mov     [rsp+0A0h+var_58], rdi
0x180061145  mov     [rsp+0A0h+var_60], rdi
0x18006114a  mov     [rsp+0A0h+var_68], rdi
0x18006114f  lea     rax, [rbp+57h+hObject]
0x180061153  mov     [rsp+0A0h+var_70], rax
0x180061158  mov     [rsp+0A0h+var_78], rdi
0x18006115d  mov     dword ptr [rsp+0A0h+ppv], edi
0x180061161  lea     r9d, [rdi+3]
0x180061165  lea     r8, WindowName
0x18006116c  lea     rdx, asc_180082018; "."
0x180061173  mov     rcx, [rbp+57h+pv]
0x180061177  call    cs:__imp_LogonUserExExW
0x18006117d  test    eax, eax
0x18006117f  jz      short loc_180061190
0x180061181  mov     edi, 1
0x180061186  mov     rcx, [rbp+57h+hObject]; hObject
0x18006118a  call    cs:__imp_CloseHandle
0x180061190  mov     rcx, [rbp+57h+pv]; pv
0x180061194  call    cs:__imp_CoTaskMemFree
0x18006119a  mov     rcx, [rbp+57h+arg_8]
0x18006119e  mov     rdx, [rcx]
0x1800611a1  mov     rax, [rdx+10h]
0x1800611a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800611aa  nop
0x1800611ab  lea     rcx, [rbp+57h+arg_10]
0x1800611af  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800611b4  mov     eax, edi
0x1800611b6  add     rsp, 90h
0x1800611bd  pop     rdi
0x1800611be  pop     rbx
0x1800611bf  pop     rbp
0x1800611c0  retn
```
