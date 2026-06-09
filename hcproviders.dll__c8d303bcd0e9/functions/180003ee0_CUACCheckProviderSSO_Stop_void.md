# CUACCheckProviderSSO::Stop(void)

- ea: `0x180003ee0`
- end: `0x180003fa2`
- name: `?Stop@CUACCheckProviderSSO@@UEAAJXZ`
- size: `194`
- prototype: `__int64 __fastcall(CUACCheckProviderSSO *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180003ee0`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003f14`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180003f14`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003f68`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180003f68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f4f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f4f`

## pseudocode

```c
HRESULT __fastcall CUACCheckProviderSSO::Stop(CUACCheckProviderSSO *this)
{
  HRESULT result; // eax
  int v3; // edi
  void *v4; // rcx
  HKEY v5; // rcx
  LPVOID ppv; // [rsp+48h] [rbp+10h] BYREF

  ppv = 0;
  result = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 1u, &GUID_00000146_0000_0000_c000_000000000046, &ppv);
  if ( result >= 0 )
  {
    v3 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)ppv + 32LL))(ppv, CUACCheckProviderSSO::s_dwCookie);
    if ( v3 >= 0 )
    {
      v4 = (void *)*((_QWORD *)this + 2);
      if ( v4 )
      {
        CloseHandle(v4);
        *((_QWORD *)this + 2) = 0;
      }
      v5 = (HKEY)*((_QWORD *)this + 3);
      if ( v5 )
      {
        RegCloseKey(v5);
        *((_QWORD *)this + 3) = 0;
      }
    }
    CUACCheckProviderSSO::s_dwCookie = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x180003ee0  mov     [rsp+arg_10], rbx
0x180003ee5  push    rsi
0x180003ee6  sub     rsp, 30h
0x180003eea  mov     rbx, rcx
0x180003eed  lea     rax, [rsp+38h+arg_8]
0x180003ef2  xor     esi, esi
0x180003ef4  mov     [rsp+38h+ppv], rax; ppv
0x180003ef9  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180003f00  mov     [rsp+38h+arg_8], rsi
0x180003f05  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180003f0c  xor     edx, edx; pUnkOuter
0x180003f0e  mov     r8d, 1; dwClsContext
0x180003f14  call    cs:__imp_CoCreateInstance
0x180003f1b  nop     dword ptr [rax+rax+00h]
0x180003f20  test    eax, eax
0x180003f22  js      short loc_180003F96
0x180003f24  mov     rcx, [rsp+38h+arg_8]
0x180003f29  mov     edx, cs:?s_dwCookie@CUACCheckProviderSSO@@0KA; ulong CUACCheckProviderSSO::s_dwCookie
0x180003f2f  mov     [rsp+38h+arg_0], rdi
0x180003f34  mov     rax, [rcx]
0x180003f37  mov     rax, [rax+20h]
0x180003f3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f40  mov     edi, eax
0x180003f42  test    eax, eax
0x180003f44  js      short loc_180003F78
0x180003f46  mov     rcx, [rbx+10h]; hObject
0x180003f4a  test    rcx, rcx
0x180003f4d  jz      short loc_180003F5F
0x180003f4f  call    cs:__imp_CloseHandle
0x180003f56  nop     dword ptr [rax+rax+00h]
0x180003f5b  mov     [rbx+10h], rsi
0x180003f5f  mov     rcx, [rbx+18h]; hKey
0x180003f63  test    rcx, rcx
0x180003f66  jz      short loc_180003F78
0x180003f68  call    cs:__imp_RegCloseKey
0x180003f6f  nop     dword ptr [rax+rax+00h]
0x180003f74  mov     [rbx+18h], rsi
0x180003f78  mov     rcx, [rsp+38h+arg_8]
0x180003f7d  mov     cs:?s_dwCookie@CUACCheckProviderSSO@@0KA, esi; ulong CUACCheckProviderSSO::s_dwCookie
0x180003f83  mov     rax, [rcx]
0x180003f86  mov     rax, [rax+10h]
0x180003f8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f8f  mov     eax, edi
0x180003f91  mov     rdi, [rsp+38h+arg_0]
0x180003f96  mov     rbx, [rsp+38h+arg_10]
0x180003f9b  add     rsp, 30h
0x180003f9f  pop     rsi
0x180003fa0  retn
```
