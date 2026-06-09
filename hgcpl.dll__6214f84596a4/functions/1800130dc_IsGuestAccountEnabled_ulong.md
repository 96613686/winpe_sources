# IsGuestAccountEnabled(ulong)

- ea: `0x1800130dc`
- end: `0x180013208`
- name: `?IsGuestAccountEnabled@@YAHK@Z`
- size: `300`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180015af8`

## callees

- `0x180005904`
- `0x180012a7c`
- `0x1800130dc`
- `0x18001a010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800131d2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800131d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800131dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800131dc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001310f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001310f`
- `SspiCli!LogonUserExExW` at `0x1800131bf`
- `SspiCli!LogonUserExExW` at `0x1800131bf`

## pseudocode

```c
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
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v7);
    if ( v1(ppv, 501, &v7) >= 0 )
    {
      pv = 0;
      v4 = PKEY_SAM_Name;
      v5 = 2;
      if ( (int)wil::PropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(&v7, &v4, &pv) >= 0 )
      {
        hObject[0] = 0;
        if ( (unsigned int)LogonUserExExW(pv, L".", &qword_18001E1A0, 3, 0, 0, hObject, 0, 0, 0, 0) )
        {
          v0 = 1;
          CloseHandle(hObject[0]);
        }
        CoTaskMemFree(pv);
      }
    }
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v7);
  }
  return v0;
}

```

## disassembly

```asm
0x1800130dc  push    rbp
0x1800130de  push    rbx
0x1800130df  push    rdi
0x1800130e0  lea     rbp, [rsp-47h]
0x1800130e5  sub     rsp, 90h
0x1800130ec  xor     edi, edi
0x1800130ee  lea     rax, [rbp+57h+arg_8]
0x1800130f2  lea     r9, _GUID_3c708557_c99d_4fa3_9231_56518418b4e4; riid
0x1800130f9  mov     [rbp+57h+arg_8], rdi
0x1800130fd  xor     edx, edx; pUnkOuter
0x1800130ff  mov     [rsp+0A0h+ppv], rax; ppv
0x180013104  lea     rcx, CLSID_LocalUserAccounts; rclsid
0x18001310b  lea     r8d, [rdi+1]; dwClsContext
0x18001310f  call    cs:__imp_CoCreateInstance
0x180013115  test    eax, eax
0x180013117  js      loc_1800131FB
0x18001311d  mov     rax, [rbp+57h+arg_8]
0x180013121  mov     [rbp+57h+arg_10], rdi
0x180013125  mov     rcx, [rax]
0x180013128  mov     rbx, [rcx+50h]
0x18001312c  lea     rcx, [rbp+57h+arg_10]
0x180013130  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180013135  mov     rcx, [rbp+57h+arg_8]
0x180013139  lea     r8, [rbp+57h+arg_10]
0x18001313d  mov     edx, 1F5h
0x180013142  mov     rax, rbx
0x180013145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001314a  test    eax, eax
0x18001314c  js      loc_1800131E2
0x180013152  movups  xmm0, cs:PKEY_SAM_Name
0x180013159  mov     eax, cs:dword_18001D698
0x18001315f  lea     r8, [rbp+57h+pv]
0x180013163  lea     rdx, [rbp+57h+var_30]
0x180013167  mov     [rbp+57h+pv], rdi
0x18001316b  lea     rcx, [rbp+57h+arg_10]
0x18001316f  movaps  [rbp+57h+var_30], xmm0
0x180013173  mov     [rbp+57h+var_20], eax
0x180013176  call    ??$GetString@U_tagpropertykey@@@?$PropertyStoreHelperBase@UIPropertyStore@@@wil@@QEBAJU_tagpropertykey@@PEAPEAG@Z; wil::PropertyStoreHelperBase<IPropertyStore>::GetString<_tagpropertykey>(_tagpropertykey,ushort * *)
0x18001317b  test    eax, eax
0x18001317d  js      short loc_1800131E2
0x18001317f  mov     rcx, [rbp+57h+pv]
0x180013183  lea     rax, [rbp+57h+hObject]
0x180013187  mov     [rsp+0A0h+var_50], rdi
0x18001318c  lea     r9d, [rdi+3]
0x180013190  mov     [rsp+0A0h+var_58], rdi
0x180013195  lea     r8, qword_18001E1A0
0x18001319c  mov     [rsp+0A0h+var_60], rdi
0x1800131a1  lea     rdx, asc_18001E800; "."
0x1800131a8  mov     [rsp+0A0h+var_68], rdi
0x1800131ad  mov     [rsp+0A0h+var_70], rax
0x1800131b2  mov     [rsp+0A0h+var_78], rdi
0x1800131b7  mov     dword ptr [rsp+0A0h+ppv], edi
0x1800131bb  mov     [rbp+57h+hObject], rdi
0x1800131bf  call    cs:__imp_LogonUserExExW
0x1800131c5  test    eax, eax
0x1800131c7  jz      short loc_1800131D8
0x1800131c9  mov     rcx, [rbp+57h+hObject]; hObject
0x1800131cd  mov     edi, 1
0x1800131d2  call    cs:__imp_CloseHandle
0x1800131d8  mov     rcx, [rbp+57h+pv]; pv
0x1800131dc  call    cs:__imp_CoTaskMemFree
0x1800131e2  mov     rcx, [rbp+57h+arg_8]
0x1800131e6  mov     rdx, [rcx]
0x1800131e9  mov     rax, [rdx+10h]
0x1800131ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131f2  lea     rcx, [rbp+57h+arg_10]
0x1800131f6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800131fb  mov     eax, edi
0x1800131fd  add     rsp, 90h
0x180013204  pop     rdi
0x180013205  pop     rbx
0x180013206  pop     rbp
0x180013207  retn
```
