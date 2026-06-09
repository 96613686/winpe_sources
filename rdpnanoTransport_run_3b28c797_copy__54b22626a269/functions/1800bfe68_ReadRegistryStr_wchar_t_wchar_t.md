# ReadRegistryStr(wchar_t *,wchar_t *)

- ea: `0x1800bfe68`
- end: `0x1800bffff`
- name: `?ReadRegistryStr@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@PEA_W0@Z`
- size: `407`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config`

## callers

- `0x18002ee30`

## callees

- `0x1800448dc`
- `0x1800bfe68`
- `0x18032f050`
- `0x18032f0b0`
- `0x18032f140`
- `0x18032f58c`
- `0x180345268`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800bffde`
- `ADVAPI32!RegCloseKey` at `0x1800bffde`
- `ADVAPI32!RegOpenKeyExW` at `0x1800bfef1`
- `ADVAPI32!RegOpenKeyExW` at `0x1800bfef1`
- `ADVAPI32!RegQueryValueExW` at `0x1800bff1f`
- `ADVAPI32!RegQueryValueExW` at `0x1800bff7d`
- `ADVAPI32!RegQueryValueExW` at `0x1800bff1f`
- `ADVAPI32!RegQueryValueExW` at `0x1800bff7d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ReadRegistryStr(__int64 a1, const WCHAR *a2, const WCHAR *a3)
{
  wchar_t *v5; // rsi
  char *v6; // rdi
  const struct std::nothrow_t *v7; // rdx
  const struct std::nothrow_t *v8; // rdx
  DWORD cbData[2]; // [rsp+40h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-28h] BYREF
  DWORD Type; // [rsp+50h] [rbp-20h] BYREF
  size_t PtNumOfCharConverted; // [rsp+58h] [rbp-18h] BYREF

  hKey = 0;
  Type = 1;
  *(_QWORD *)cbData = 0;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 15;
  *(_BYTE *)a1 = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0x20019u, &hKey) && !RegQueryValueExW(hKey, a2, 0, &Type, 0, cbData) )
  {
    v5 = (wchar_t *)operator new[](saturated_mul(*(_QWORD *)cbData + 1LL, 2u));
    v6 = (char *)operator new[](*(_QWORD *)cbData + 1LL);
    if ( !RegQueryValueExW(hKey, a2, 0, &Type, (LPBYTE)v5, cbData) )
    {
      PtNumOfCharConverted = 0;
      wcstombs_s(&PtNumOfCharConverted, v6, *(_QWORD *)cbData + 1LL, v5, 2LL * *(_QWORD *)cbData + 2);
      v6[*(_QWORD *)cbData] = 0;
      std::string::assign(a1, v6);
    }
    operator delete(v6, v7);
    operator delete(v5, v8);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return a1;
}

```

## disassembly

```asm
0x1800bfe68  push    rbp
0x1800bfe6a  push    rbx
0x1800bfe6b  push    rsi
0x1800bfe6c  push    rdi
0x1800bfe6d  push    r14
0x1800bfe6f  mov     rbp, rsp
0x1800bfe72  mov     eax, 70h
0x1800bfe77  call    _alloca_probe
0x1800bfe7c  sub     rsp, rax
0x1800bfe7f  mov     rax, cs:__security_cookie
0x1800bfe86  xor     rax, rsp
0x1800bfe89  mov     [rbp+var_10], rax
0x1800bfe8d  mov     rax, r8
0x1800bfe90  mov     r14, rdx
0x1800bfe93  mov     rbx, rcx
0x1800bfe96  mov     [rbp+var_38], rcx
0x1800bfe9a  mov     [rbp+var_40], 0
0x1800bfea1  mov     [rbp+hKey], 0
0x1800bfea9  mov     ecx, 1
0x1800bfeae  mov     [rbp+Type], ecx
0x1800bfeb1  mov     qword ptr [rbp+cbData], 0
0x1800bfeb9  xorps   xmm0, xmm0
0x1800bfebc  movups  xmmword ptr [rbx], xmm0
0x1800bfebf  mov     qword ptr [rbx+10h], 0
0x1800bfec7  mov     qword ptr [rbx+18h], 0Fh
0x1800bfecf  mov     byte ptr [rbx], 0
0x1800bfed2  mov     [rbp+var_40], ecx
0x1800bfed5  lea     rcx, [rbp+hKey]
0x1800bfed9  mov     [rsp+70h+phkResult], rcx; phkResult
0x1800bfede  mov     r9d, 20019h; samDesired
0x1800bfee4  xor     r8d, r8d; ulOptions
0x1800bfee7  mov     rdx, rax; lpSubKey
0x1800bfeea  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800bfef1  call    cs:__imp_RegOpenKeyExW
0x1800bfef7  test    eax, eax
0x1800bfef9  jnz     loc_1800BFFD5
0x1800bfeff  lea     rax, [rbp+cbData]
0x1800bff03  mov     [rsp+70h+lpcbData], rax; lpcbData
0x1800bff08  mov     [rsp+70h+phkResult], 0; lpData
0x1800bff11  lea     r9, [rbp+Type]; lpType
0x1800bff15  xor     r8d, r8d; lpReserved
0x1800bff18  mov     rdx, r14; lpValueName
0x1800bff1b  mov     rcx, [rbp+hKey]; hKey
0x1800bff1f  call    cs:__imp_RegQueryValueExW
0x1800bff25  test    eax, eax
0x1800bff27  jnz     loc_1800BFFD5
0x1800bff2d  mov     rcx, qword ptr [rbp+cbData]
0x1800bff31  inc     rcx
0x1800bff34  mov     eax, 2
0x1800bff39  mul     rcx
0x1800bff3c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800bff43  cmovb   rax, rcx
0x1800bff47  mov     rcx, rax; unsigned __int64
0x1800bff4a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800bff4f  mov     rsi, rax
0x1800bff52  mov     rcx, qword ptr [rbp+cbData]
0x1800bff56  inc     rcx; unsigned __int64
0x1800bff59  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800bff5e  mov     rdi, rax
0x1800bff61  lea     rax, [rbp+cbData]
0x1800bff65  mov     [rsp+70h+lpcbData], rax; lpcbData
0x1800bff6a  mov     [rsp+70h+phkResult], rsi; lpData
0x1800bff6f  lea     r9, [rbp+Type]; lpType
0x1800bff73  xor     r8d, r8d; lpReserved
0x1800bff76  mov     rdx, r14; lpValueName
0x1800bff79  mov     rcx, [rbp+hKey]; hKey
0x1800bff7d  call    cs:__imp_RegQueryValueExW
0x1800bff83  test    eax, eax
0x1800bff85  jnz     short loc_1800BFFC5
0x1800bff87  mov     [rbp+PtNumOfCharConverted], 0
0x1800bff8f  mov     r8, qword ptr [rbp+cbData]
0x1800bff93  lea     rax, ds:2[r8*2]
0x1800bff9b  inc     r8; DstSizeInBytes
0x1800bff9e  mov     [rsp+70h+phkResult], rax; MaxCountInBytes
0x1800bffa3  mov     r9, rsi; Src
0x1800bffa6  mov     rdx, rdi; Dst
0x1800bffa9  lea     rcx, [rbp+PtNumOfCharConverted]; PtNumOfCharConverted
0x1800bffad  call    wcstombs_s
0x1800bffb2  mov     rax, qword ptr [rbp+cbData]
0x1800bffb6  mov     byte ptr [rdi+rax], 0
0x1800bffba  mov     rdx, rdi
0x1800bffbd  mov     rcx, rbx
0x1800bffc0  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD@Z; std::string::assign(char const * const)
0x1800bffc5  mov     rcx, rdi; void *
0x1800bffc8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800bffcd  mov     rcx, rsi; void *
0x1800bffd0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800bffd5  mov     rcx, [rbp+hKey]; hKey
0x1800bffd9  test    rcx, rcx
0x1800bffdc  jz      short loc_1800BFFE4
0x1800bffde  call    cs:__imp_RegCloseKey
0x1800bffe4  mov     rax, rbx
0x1800bffe7  mov     rcx, [rbp+var_10]
0x1800bffeb  xor     rcx, rsp; StackCookie
0x1800bffee  call    __security_check_cookie
0x1800bfff3  add     rsp, 70h
0x1800bfff7  pop     r14
0x1800bfff9  pop     rdi
0x1800bfffa  pop     rsi
0x1800bfffb  pop     rbx
0x1800bfffc  pop     rbp
0x1800bfffd  retn
```
