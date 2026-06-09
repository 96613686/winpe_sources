# Microsoft::Basix::WinUtils::ReadRegistryString(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x1802e429c`
- end: `0x1802e43fb`
- name: `?ReadRegistryString@WinUtils@Basix@Microsoft@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV45@0@Z`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800fa23c`

## callees

- `0x1800448dc`
- `0x1802e429c`
- `0x18032f050`
- `0x18032f0b0`
- `0x18032f140`
- `0x18032f58c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1802e43d5`
- `ADVAPI32!RegCloseKey` at `0x1802e43d5`
- `ADVAPI32!RegOpenKeyExA` at `0x1802e4330`
- `ADVAPI32!RegOpenKeyExA` at `0x1802e4330`
- `ADVAPI32!RegQueryValueExA` at `0x1802e4368`
- `ADVAPI32!RegQueryValueExA` at `0x1802e43a7`
- `ADVAPI32!RegQueryValueExA` at `0x1802e4368`
- `ADVAPI32!RegQueryValueExA` at `0x1802e43a7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Basix::WinUtils::ReadRegistryString(__int64 a1, const CHAR *a2, __int64 a3)
{
  const CHAR *v3; // rax
  const CHAR *v6; // rdx
  BYTE *v7; // rdi
  const struct std::nothrow_t *v8; // rdx
  DWORD cbData[2]; // [rsp+40h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-18h] BYREF
  DWORD Type; // [rsp+50h] [rbp-10h] BYREF

  v3 = (const CHAR *)a3;
  hKey = 0;
  Type = 1;
  *(_QWORD *)cbData = 0;
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 15;
  *(_BYTE *)a1 = 0;
  if ( *(_QWORD *)(a3 + 24) > 0xFu )
    v3 = *(const CHAR **)a3;
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, v3, 0, 0x20019u, &hKey) )
  {
    v6 = a2;
    if ( *((_QWORD *)a2 + 3) > 0xFu )
      v6 = *(const CHAR **)a2;
    if ( !RegQueryValueExA(hKey, v6, 0, &Type, 0, cbData) )
    {
      v7 = (BYTE *)operator new[](*(_QWORD *)cbData + 1LL);
      if ( *((_QWORD *)a2 + 3) > 0xFu )
        a2 = *(const CHAR **)a2;
      if ( !RegQueryValueExA(hKey, a2, 0, &Type, v7, cbData) )
      {
        v7[*(_QWORD *)cbData] = 0;
        std::string::assign(a1, v7);
      }
      operator delete(v7, v8);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return a1;
}

```

## disassembly

```asm
0x1802e429c  mov     [rsp-18h+arg_18], rbx
0x1802e42a1  push    rbp
0x1802e42a2  push    rsi
0x1802e42a3  push    rdi
0x1802e42a4  mov     rbp, rsp
0x1802e42a7  mov     eax, 60h
0x1802e42ac  call    _alloca_probe
0x1802e42b1  sub     rsp, rax
0x1802e42b4  mov     rax, cs:__security_cookie
0x1802e42bb  xor     rax, rsp
0x1802e42be  mov     [rbp+var_8], rax
0x1802e42c2  mov     rax, r8
0x1802e42c5  mov     rbx, rdx
0x1802e42c8  mov     rsi, rcx
0x1802e42cb  mov     [rbp+var_28], rcx
0x1802e42cf  mov     [rbp+var_30], 0
0x1802e42d6  mov     [rbp+hKey], 0
0x1802e42de  mov     ecx, 1
0x1802e42e3  mov     [rbp+Type], ecx
0x1802e42e6  mov     qword ptr [rbp+cbData], 0
0x1802e42ee  xorps   xmm0, xmm0
0x1802e42f1  movups  xmmword ptr [rsi], xmm0
0x1802e42f4  mov     qword ptr [rsi+10h], 0
0x1802e42fc  mov     qword ptr [rsi+18h], 0Fh
0x1802e4304  mov     byte ptr [rsi], 0
0x1802e4307  mov     [rbp+var_30], ecx
0x1802e430a  cmp     qword ptr [r8+18h], 0Fh
0x1802e430f  jbe     short loc_1802E4314
0x1802e4311  mov     rax, [r8]
0x1802e4314  lea     rcx, [rbp+hKey]
0x1802e4318  mov     [rsp+60h+phkResult], rcx; phkResult
0x1802e431d  mov     r9d, 20019h; samDesired
0x1802e4323  xor     r8d, r8d; ulOptions
0x1802e4326  mov     rdx, rax; lpSubKey
0x1802e4329  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1802e4330  call    cs:__imp_RegOpenKeyExA
0x1802e4336  test    eax, eax
0x1802e4338  jnz     loc_1802E43CC
0x1802e433e  mov     rdx, rbx
0x1802e4341  cmp     qword ptr [rbx+18h], 0Fh
0x1802e4346  jbe     short loc_1802E434B
0x1802e4348  mov     rdx, [rbx]; lpValueName
0x1802e434b  lea     rax, [rbp+cbData]
0x1802e434f  mov     [rsp+60h+lpcbData], rax; lpcbData
0x1802e4354  mov     [rsp+60h+phkResult], 0; lpData
0x1802e435d  lea     r9, [rbp+Type]; lpType
0x1802e4361  xor     r8d, r8d; lpReserved
0x1802e4364  mov     rcx, [rbp+hKey]; hKey
0x1802e4368  call    cs:__imp_RegQueryValueExA
0x1802e436e  test    eax, eax
0x1802e4370  jnz     short loc_1802E43CC
0x1802e4372  mov     rcx, qword ptr [rbp+cbData]
0x1802e4376  inc     rcx; unsigned __int64
0x1802e4379  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1802e437e  mov     rdi, rax
0x1802e4381  cmp     qword ptr [rbx+18h], 0Fh
0x1802e4386  jbe     short loc_1802E438B
0x1802e4388  mov     rbx, [rbx]
0x1802e438b  lea     rax, [rbp+cbData]
0x1802e438f  mov     [rsp+60h+lpcbData], rax; lpcbData
0x1802e4394  mov     [rsp+60h+phkResult], rdi; lpData
0x1802e4399  lea     r9, [rbp+Type]; lpType
0x1802e439d  xor     r8d, r8d; lpReserved
0x1802e43a0  mov     rdx, rbx; lpValueName
0x1802e43a3  mov     rcx, [rbp+hKey]; hKey
0x1802e43a7  call    cs:__imp_RegQueryValueExA
0x1802e43ad  test    eax, eax
0x1802e43af  jnz     short loc_1802E43C4
0x1802e43b1  mov     rax, qword ptr [rbp+cbData]
0x1802e43b5  mov     byte ptr [rdi+rax], 0
0x1802e43b9  mov     rdx, rdi
0x1802e43bc  mov     rcx, rsi
0x1802e43bf  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD@Z; std::string::assign(char const * const)
0x1802e43c4  mov     rcx, rdi; void *
0x1802e43c7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1802e43cc  mov     rcx, [rbp+hKey]; hKey
0x1802e43d0  test    rcx, rcx
0x1802e43d3  jz      short loc_1802E43DB
0x1802e43d5  call    cs:__imp_RegCloseKey
0x1802e43db  mov     rax, rsi
0x1802e43de  mov     rcx, [rbp+var_8]
0x1802e43e2  xor     rcx, rsp; StackCookie
0x1802e43e5  call    __security_check_cookie
0x1802e43ea  mov     rbx, [rsp+60h+arg_18]
0x1802e43f2  add     rsp, 60h
0x1802e43f6  pop     rdi
0x1802e43f7  pop     rsi
0x1802e43f8  pop     rbp
0x1802e43f9  retn
```
