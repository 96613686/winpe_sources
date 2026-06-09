# DllUnregisterServer

- ea: `0x180017a60`
- end: `0x180017ca6`
- name: `DllUnregisterServer`
- size: `582`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800172e0`
- `0x180017358`
- `0x180017a60`
- `0x18004700f`
- `0x180047050`

## import_xrefs

- `ADVAPI32!RegDeleteKeyW` at `0x180017b2c`
- `ADVAPI32!RegDeleteKeyW` at `0x180017b6c`
- `ADVAPI32!RegDeleteKeyW` at `0x180017bdc`
- `ADVAPI32!RegDeleteKeyW` at `0x180017bea`
- `ADVAPI32!RegDeleteKeyW` at `0x180017c5a`
- `ADVAPI32!RegDeleteKeyW` at `0x180017c68`
- `ADVAPI32!RegDeleteKeyW` at `0x180017b2c`
- `ADVAPI32!RegDeleteKeyW` at `0x180017b6c`
- `ADVAPI32!RegDeleteKeyW` at `0x180017bdc`
- `ADVAPI32!RegDeleteKeyW` at `0x180017bea`
- `ADVAPI32!RegDeleteKeyW` at `0x180017c5a`
- `ADVAPI32!RegDeleteKeyW` at `0x180017c68`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180017af0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180017b3e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180017b7e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180017bae`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180017bfc`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180017c2c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180017af0`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180017b3e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180017b7e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180017bae`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180017bfc`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180017c2c`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180017aa9`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180017acf`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180017aa9`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180017acf`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017b05`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017b17`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017b4c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017b5e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017b8c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017b9e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017bbc`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017bce`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017c0a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017c1c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017c3a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017c4c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017b05`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017b17`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017b4c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017b5e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017b8c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017b9e`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017bbc`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017bce`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017c0a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017c1c`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017c3a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180017c4c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180017c78`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180017c83`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180017c78`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180017c83`

## string_xrefs

- `0x180017c40`: `ProxyStubClsid32`
- `0x180017b32`: `CLSID`
- `0x180017b72`: `CLSID`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  HRESULT GlobalGUIDStrings; // ebx
  _BYTE v2[32]; // [rsp+20h] [rbp-E0h] BYREF
  LPCWSTR lpSubKey; // [rsp+40h] [rbp-C0h]
  _BYTE v4[32]; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR v5; // [rsp+78h] [rbp-88h]
  unsigned __int16 v6[256]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v7[256]; // [rsp+290h] [rbp+190h] BYREF

  memset_0(v6, 0, sizeof(v6));
  STRU::STRU((STRU *)v2, v6, 0x100u);
  memset_0(v7, 0, sizeof(v7));
  STRU::STRU((STRU *)v4, v7, 0x100u);
  GlobalGUIDStrings = AllocateGlobalGUIDStrings();
  if ( GlobalGUIDStrings >= 0 )
  {
    STRU::Copy((STRU *)v2, L"AppID");
    STRU::Append((STRU *)v2, L"\\");
    STRU::Append((STRU *)v2, (const unsigned __int16 *)lpData);
    RegDeleteKeyW(HKEY_CLASSES_ROOT, lpSubKey);
    STRU::Copy((STRU *)v2, L"CLSID");
    STRU::Append((STRU *)v2, L"\\");
    STRU::Append((STRU *)v2, (const unsigned __int16 *)lpData);
    RegDeleteKeyW(HKEY_CLASSES_ROOT, lpSubKey);
    STRU::Copy((STRU *)v2, L"CLSID");
    STRU::Append((STRU *)v2, L"\\");
    STRU::Append((STRU *)v2, (const unsigned __int16 *)qword_1800614E8);
    STRU::Copy((STRU *)v4, lpSubKey);
    STRU::Append((STRU *)v4, L"\\");
    STRU::Append((STRU *)v4, L"InprocServer32");
    RegDeleteKeyW(HKEY_CLASSES_ROOT, v5);
    RegDeleteKeyW(HKEY_CLASSES_ROOT, lpSubKey);
    STRU::Copy((STRU *)v2, L"Interface");
    STRU::Append((STRU *)v2, L"\\");
    STRU::Append((STRU *)v2, (const unsigned __int16 *)qword_1800614E8);
    STRU::Copy((STRU *)v4, lpSubKey);
    STRU::Append((STRU *)v4, L"\\");
    STRU::Append((STRU *)v4, L"ProxyStubClsid32");
    RegDeleteKeyW(HKEY_CLASSES_ROOT, v5);
    RegDeleteKeyW(HKEY_CLASSES_ROOT, lpSubKey);
    FreeGlobalGUIDStrings();
  }
  STRU::~STRU(v4);
  STRU::~STRU(v2);
  return GlobalGUIDStrings;
}

```

## disassembly

```asm
0x180017a60  push    rbp
0x180017a62  push    rbx
0x180017a63  push    rsi
0x180017a64  push    rdi
0x180017a65  lea     rbp, [rsp-3A8h]
0x180017a6d  sub     rsp, 4A8h
0x180017a74  mov     rax, cs:__security_cookie
0x180017a7b  xor     rax, rsp
0x180017a7e  mov     [rbp+3C0h+var_30], rax
0x180017a85  mov     edi, 200h
0x180017a8a  lea     rcx, [rbp+3C0h+var_430]; void *
0x180017a8e  mov     r8d, edi; Size
0x180017a91  xor     edx, edx; Val
0x180017a93  call    memset_0
0x180017a98  mov     ebx, 100h
0x180017a9d  lea     rdx, [rbp+3C0h+var_430]
0x180017aa1  mov     r8d, ebx
0x180017aa4  lea     rcx, [rsp+4C0h+var_4A0]
0x180017aa9  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180017aaf  mov     r8d, edi; Size
0x180017ab2  lea     rcx, [rbp+3C0h+var_230]; void *
0x180017ab9  xor     edx, edx; Val
0x180017abb  call    memset_0
0x180017ac0  mov     r8d, ebx
0x180017ac3  lea     rdx, [rbp+3C0h+var_230]
0x180017aca  lea     rcx, [rsp+4C0h+var_468]
0x180017acf  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180017ad5  call    AllocateGlobalGUIDStrings
0x180017ada  mov     ebx, eax
0x180017adc  test    eax, eax
0x180017ade  js      loc_180017C73
0x180017ae4  lea     rdx, aAppid_0; "AppID"
0x180017aeb  lea     rcx, [rsp+4C0h+var_4A0]
0x180017af0  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180017af6  lea     rdi, asc_18004BD10; "\\"
0x180017afd  mov     rdx, rdi
0x180017b00  lea     rcx, [rsp+4C0h+var_4A0]
0x180017b05  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180017b0b  mov     rdx, cs:lpData
0x180017b12  lea     rcx, [rsp+4C0h+var_4A0]
0x180017b17  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180017b1d  mov     rdx, [rsp+4C0h+lpSubKey]; lpSubKey
0x180017b22  mov     rsi, 0FFFFFFFF80000000h
0x180017b29  mov     rcx, rsi; hKey
0x180017b2c  call    cs:__imp_RegDeleteKeyW
0x180017b32  lea     rdx, aClsid_0; "CLSID"
0x180017b39  lea     rcx, [rsp+4C0h+var_4A0]
0x180017b3e  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180017b44  mov     rdx, rdi
0x180017b47  lea     rcx, [rsp+4C0h+var_4A0]
0x180017b4c  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180017b52  mov     rdx, cs:lpData
0x180017b59  lea     rcx, [rsp+4C0h+var_4A0]
0x180017b5e  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180017b64  mov     rdx, [rsp+4C0h+lpSubKey]; lpSubKey
0x180017b69  mov     rcx, rsi; hKey
0x180017b6c  call    cs:__imp_RegDeleteKeyW
0x180017b72  lea     rdx, aClsid_0; "CLSID"
0x180017b79  lea     rcx, [rsp+4C0h+var_4A0]
0x180017b7e  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180017b84  mov     rdx, rdi
0x180017b87  lea     rcx, [rsp+4C0h+var_4A0]
0x180017b8c  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180017b92  mov     rdx, cs:qword_1800614E8
0x180017b99  lea     rcx, [rsp+4C0h+var_4A0]
0x180017b9e  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180017ba4  mov     rdx, [rsp+4C0h+lpSubKey]
0x180017ba9  lea     rcx, [rsp+4C0h+var_468]
0x180017bae  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180017bb4  mov     rdx, rdi
0x180017bb7  lea     rcx, [rsp+4C0h+var_468]
0x180017bbc  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180017bc2  lea     rdx, aInprocserver32; "InprocServer32"
0x180017bc9  lea     rcx, [rsp+4C0h+var_468]
0x180017bce  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180017bd4  mov     rdx, [rsp+4C0h+var_448]; lpSubKey
0x180017bd9  mov     rcx, rsi; hKey
0x180017bdc  call    cs:__imp_RegDeleteKeyW
0x180017be2  mov     rdx, [rsp+4C0h+lpSubKey]; lpSubKey
0x180017be7  mov     rcx, rsi; hKey
0x180017bea  call    cs:__imp_RegDeleteKeyW
0x180017bf0  lea     rdx, aInterface; "Interface"
0x180017bf7  lea     rcx, [rsp+4C0h+var_4A0]
0x180017bfc  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180017c02  mov     rdx, rdi
0x180017c05  lea     rcx, [rsp+4C0h+var_4A0]
0x180017c0a  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180017c10  mov     rdx, cs:qword_1800614E8
0x180017c17  lea     rcx, [rsp+4C0h+var_4A0]
0x180017c1c  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180017c22  mov     rdx, [rsp+4C0h+lpSubKey]
0x180017c27  lea     rcx, [rsp+4C0h+var_468]
0x180017c2c  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180017c32  mov     rdx, rdi
0x180017c35  lea     rcx, [rsp+4C0h+var_468]
0x180017c3a  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180017c40  lea     rdx, aProxystubclsid; "ProxyStubClsid32"
0x180017c47  lea     rcx, [rsp+4C0h+var_468]
0x180017c4c  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180017c52  mov     rdx, [rsp+4C0h+var_448]; lpSubKey
0x180017c57  mov     rcx, rsi; hKey
0x180017c5a  call    cs:__imp_RegDeleteKeyW
0x180017c60  mov     rdx, [rsp+4C0h+lpSubKey]; lpSubKey
0x180017c65  mov     rcx, rsi; hKey
0x180017c68  call    cs:__imp_RegDeleteKeyW
0x180017c6e  call    FreeGlobalGUIDStrings
0x180017c73  lea     rcx, [rsp+4C0h+var_468]
0x180017c78  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180017c7e  lea     rcx, [rsp+4C0h+var_4A0]
0x180017c83  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180017c89  mov     eax, ebx
0x180017c8b  mov     rcx, [rbp+3C0h+var_30]
0x180017c92  xor     rcx, rsp; StackCookie
0x180017c95  call    __security_check_cookie
0x180017c9a  add     rsp, 4A8h
0x180017ca1  pop     rdi
0x180017ca2  pop     rsi
0x180017ca3  pop     rbx
0x180017ca4  pop     rbp
0x180017ca5  retn
```
