# AdapterCacheUpdate::AddDXGIAdapterInfo(HKEY__ *,DXGI_ADAPTER_DESC1 const &)

- ea: `0x140007b30`
- end: `0x140007d84`
- name: `?AddDXGIAdapterInfo@AdapterCacheUpdate@@QEAAXPEAUHKEY__@@AEBUDXGI_ADAPTER_DESC1@@@Z`
- size: `596`
- prototype: `void __fastcall(const BYTE *this, HKEY, const BYTE *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x14000e174`

## callees

- `0x140007b30`
- `0x1400103d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140007b79`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140007bb2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140007be5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140007c18`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140007c47`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140007c76`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140007ca5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140007cd1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140007b79`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140007bb2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140007be5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140007c18`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140007c47`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140007c76`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140007ca5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x140007cd1`

## pseudocode

```c
void __fastcall AdapterCacheUpdate::AddDXGIAdapterInfo(const BYTE *this, HKEY a2, const BYTE *a3)
{
  __int64 v3; // rax
  unsigned int v7; // eax
  unsigned int v8; // r8d
  unsigned int v9; // eax
  unsigned int v10; // r8d
  unsigned int v11; // eax
  unsigned int v12; // r8d
  unsigned int v13; // eax
  unsigned int v14; // r8d
  unsigned int v15; // eax
  unsigned int v16; // r8d
  unsigned int v17; // eax
  unsigned int v18; // r8d
  unsigned int v19; // eax
  unsigned int v20; // r8d
  unsigned int v21; // eax
  unsigned int v22; // r8d
  unsigned int lpData; // [rsp+20h] [rbp-48h]
  unsigned int lpDataa; // [rsp+20h] [rbp-48h]
  unsigned int lpDatab; // [rsp+20h] [rbp-48h]
  unsigned int lpDatac; // [rsp+20h] [rbp-48h]
  unsigned int lpDatad; // [rsp+20h] [rbp-48h]
  unsigned int lpDatae; // [rsp+20h] [rbp-48h]
  unsigned int lpDataf; // [rsp+20h] [rbp-48h]
  unsigned int lpDatag; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v3 = -1;
  do
    ++v3;
  while ( *(_WORD *)&a3[2 * v3] );
  v7 = RegSetValueExW(a2, L"Description", 0, 1u, a3, 2 * v3 + 2);
  if ( v7 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x15D, v8, (const char *)v7, lpData);
  v9 = RegSetValueExW(a2, L"AdapterLuid", 0, 0xBu, a3 + 296, 8u);
  if ( v9 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x152, v10, (const char *)v9, lpDataa);
  v11 = RegSetValueExW(a2, L"VendorId", 0, 4u, a3 + 256, 4u);
  if ( v11 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x152, v12, (const char *)v11, lpDatab);
  v13 = RegSetValueExW(a2, L"DeviceId", 0, 4u, a3 + 260, 4u);
  if ( v13 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x152, v14, (const char *)v13, lpDatac);
  v15 = RegSetValueExW(a2, L"DedicatedVideoMemory", 0, 0xBu, a3 + 272, 8u);
  if ( v15 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x152, v16, (const char *)v15, lpDatad);
  v17 = RegSetValueExW(a2, L"DedicatedSystemMemory", 0, 0xBu, a3 + 280, 8u);
  if ( v17 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x152, v18, (const char *)v17, lpDatae);
  v19 = RegSetValueExW(a2, L"SharedSystemMemory", 0, 0xBu, a3 + 288, 8u);
  if ( v19 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x152, v20, (const char *)v19, lpDataf);
  v21 = RegSetValueExW(a2, L"LastSeen", 0, 0xBu, this + 32, 8u);
  if ( v21 )
    wil::details::in1diag3::_Throw_Win32(retaddr, (void *)0x152, v22, (const char *)v21, lpDatag);
}

```

## disassembly

```asm
0x140007b30  push    rbx
0x140007b32  push    rbp
0x140007b33  push    rsi
0x140007b34  push    rdi
0x140007b35  push    r14
0x140007b37  push    r15
0x140007b39  sub     rsp, 38h
0x140007b3d  or      rax, 0FFFFFFFFFFFFFFFFh
0x140007b41  mov     rbx, r8
0x140007b44  xor     ebp, ebp
0x140007b46  mov     rdi, rdx
0x140007b49  mov     rsi, rcx
0x140007b4c  inc     rax
0x140007b4f  cmp     [r8+rax*2], bp
0x140007b54  jnz     short loc_140007B4C
0x140007b56  lea     eax, ds:2[rax*2]
0x140007b5d  mov     r9d, 1; dwType
0x140007b63  mov     [rsp+68h+cbData], eax; cbData
0x140007b67  lea     rdx, ValueName; "Description"
0x140007b6e  xor     r8d, r8d; Reserved
0x140007b71  mov     [rsp+68h+lpData], rbx; unsigned int
0x140007b76  mov     rcx, rdi; hKey
0x140007b79  call    cs:__imp_RegSetValueExW
0x140007b7f  test    eax, eax
0x140007b81  jnz     loc_140007CEC
0x140007b87  mov     r14d, 8
0x140007b8d  lea     rax, [rbx+128h]
0x140007b94  mov     [rsp+68h+cbData], r14d; cbData
0x140007b99  lea     rdx, aAdapterluid; "AdapterLuid"
0x140007ba0  xor     r8d, r8d; Reserved
0x140007ba3  mov     [rsp+68h+lpData], rax; unsigned int
0x140007ba8  mov     rcx, rdi; hKey
0x140007bab  lea     r15d, [r14+3]
0x140007baf  mov     r9d, r15d; dwType
0x140007bb2  call    cs:__imp_RegSetValueExW
0x140007bb8  test    eax, eax
0x140007bba  jnz     loc_140007CFF
0x140007bc0  lea     rax, [rbx+100h]
0x140007bc7  mov     [rsp+68h+cbData], 4; cbData
0x140007bcf  lea     r9d, [r14-4]; dwType
0x140007bd3  mov     [rsp+68h+lpData], rax; unsigned int
0x140007bd8  xor     r8d, r8d; Reserved
0x140007bdb  lea     rdx, aVendorid; "VendorId"
0x140007be2  mov     rcx, rdi; hKey
0x140007be5  call    cs:__imp_RegSetValueExW
0x140007beb  test    eax, eax
0x140007bed  jnz     loc_140007D12
0x140007bf3  lea     rax, [rbx+104h]
0x140007bfa  mov     [rsp+68h+cbData], 4; cbData
0x140007c02  lea     r9d, [r14-4]; dwType
0x140007c06  mov     [rsp+68h+lpData], rax; unsigned int
0x140007c0b  xor     r8d, r8d; Reserved
0x140007c0e  lea     rdx, aDeviceid; "DeviceId"
0x140007c15  mov     rcx, rdi; hKey
0x140007c18  call    cs:__imp_RegSetValueExW
0x140007c1e  test    eax, eax
0x140007c20  jnz     loc_140007D25
0x140007c26  lea     rax, [rbx+110h]
0x140007c2d  mov     [rsp+68h+cbData], r14d; cbData
0x140007c32  mov     r9d, r15d; dwType
0x140007c35  mov     [rsp+68h+lpData], rax; unsigned int
0x140007c3a  xor     r8d, r8d; Reserved
0x140007c3d  lea     rdx, aDedicatedvideo; "DedicatedVideoMemory"
0x140007c44  mov     rcx, rdi; hKey
0x140007c47  call    cs:__imp_RegSetValueExW
0x140007c4d  test    eax, eax
0x140007c4f  jnz     loc_140007D38
0x140007c55  lea     rax, [rbx+118h]
0x140007c5c  mov     [rsp+68h+cbData], r14d; cbData
0x140007c61  mov     r9d, r15d; dwType
0x140007c64  mov     [rsp+68h+lpData], rax; unsigned int
0x140007c69  xor     r8d, r8d; Reserved
0x140007c6c  lea     rdx, aDedicatedsyste; "DedicatedSystemMemory"
0x140007c73  mov     rcx, rdi; hKey
0x140007c76  call    cs:__imp_RegSetValueExW
0x140007c7c  test    eax, eax
0x140007c7e  jnz     loc_140007D4B
0x140007c84  lea     rax, [rbx+120h]
0x140007c8b  mov     [rsp+68h+cbData], r14d; cbData
0x140007c90  mov     r9d, r15d; dwType
0x140007c93  mov     [rsp+68h+lpData], rax; unsigned int
0x140007c98  xor     r8d, r8d; Reserved
0x140007c9b  lea     rdx, aSharedsystemme; "SharedSystemMemory"
0x140007ca2  mov     rcx, rdi; hKey
0x140007ca5  call    cs:__imp_RegSetValueExW
0x140007cab  test    eax, eax
0x140007cad  jnz     loc_140007D5E
0x140007cb3  lea     rax, [rsi+20h]
0x140007cb7  mov     [rsp+68h+cbData], r14d; cbData
0x140007cbc  mov     r9d, r15d; dwType
0x140007cbf  mov     [rsp+68h+lpData], rax; unsigned int
0x140007cc4  xor     r8d, r8d; Reserved
0x140007cc7  lea     rdx, aLastseen; "LastSeen"
0x140007cce  mov     rcx, rdi; hKey
0x140007cd1  call    cs:__imp_RegSetValueExW
0x140007cd7  test    eax, eax
0x140007cd9  jnz     loc_140007D71
0x140007cdf  add     rsp, 38h
0x140007ce3  pop     r15
0x140007ce5  pop     r14
0x140007ce7  pop     rdi
0x140007ce8  pop     rsi
0x140007ce9  pop     rbp
0x140007cea  pop     rbx
0x140007ceb  retn
0x140007cec  mov     rcx, [rsp+68h]; this
0x140007cf1  mov     r9d, eax; char *
0x140007cf4  mov     edx, 15Dh; void *
0x140007cf9  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x140007cff  mov     rcx, [rsp+68h]; this
0x140007d04  mov     r9d, eax; char *
0x140007d07  mov     edx, 152h; void *
0x140007d0c  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x140007d12  mov     rcx, [rsp+68h]; this
0x140007d17  mov     r9d, eax; char *
0x140007d1a  mov     edx, 152h; void *
0x140007d1f  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x140007d25  mov     rcx, [rsp+68h]; this
0x140007d2a  mov     r9d, eax; char *
0x140007d2d  mov     edx, 152h; void *
0x140007d32  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x140007d38  mov     rcx, [rsp+68h]; this
0x140007d3d  mov     r9d, eax; char *
0x140007d40  mov     edx, 152h; void *
0x140007d45  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x140007d4b  mov     rcx, [rsp+68h]; this
0x140007d50  mov     r9d, eax; char *
0x140007d53  mov     edx, 152h; void *
0x140007d58  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x140007d5e  mov     rcx, [rsp+68h]; this
0x140007d63  mov     r9d, eax; char *
0x140007d66  mov     edx, 152h; void *
0x140007d6b  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
0x140007d71  mov     rcx, [rsp+68h]; this
0x140007d76  mov     r9d, eax; char *
0x140007d79  mov     edx, 152h; void *
0x140007d7e  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
