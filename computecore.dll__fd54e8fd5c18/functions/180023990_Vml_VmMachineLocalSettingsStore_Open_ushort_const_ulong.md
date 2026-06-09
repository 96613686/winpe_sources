# Vml::VmMachineLocalSettingsStore::Open(ushort const *,ulong)

- ea: `0x180023990`
- end: `0x180023abd`
- name: `?Open@VmMachineLocalSettingsStore@Vml@@UEAA_NPEBGK@Z`
- size: `301`
- prototype: `bool(Vml::VmMachineLocalSettingsStore *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800067c0`
- `0x1800136d0`
- `0x180023990`
- `0x180027380`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800239f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023a0c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023a69`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800239f6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023a0c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023a69`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800239d9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023a4d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800239d9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180023a4d`

## string_xrefs

- `0x180023a91`: `onecore\vm\common\vml\VmRegistry.h`
- `0x180023aab`: `onecore\vm\common\vml\VmRegistry.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall Vml::VmMachineLocalSettingsStore::Open(
        Vml::VmMachineLocalSettingsStore *this,
        unsigned __int16 *a2,
        REGSAM a3)
{
  unsigned int v6; // eax
  HKEY v8; // rcx
  __int64 *v9; // rdx
  __int64 v10; // r8
  unsigned int v11; // eax
  bool v12; // bl
  unsigned int phkResult; // [rsp+20h] [rbp-48h]
  unsigned int phkResulta; // [rsp+20h] [rbp-48h]
  HKEY hKey; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  hKey = 0;
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Virtualization",
         0,
         a3,
         &hKey);
  if ( v6 )
  {
    if ( v6 != 2 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1F9,
        (unsigned int)"onecore\\vm\\common\\vml\\VmRegistry.h",
        (const char *)v6,
        phkResult);
    if ( hKey )
      RegCloseKey(hKey);
    return 0;
  }
  else
  {
    v8 = (HKEY)*((_QWORD *)this + 1);
    if ( v8 )
    {
      RegCloseKey(v8);
      *((_QWORD *)this + 1) = 0;
    }
    v9 = &qword_1800AD7F8;
    if ( a2 )
      v9 = (__int64 *)a2;
    v10 = -1;
    do
      ++v10;
    while ( *((_WORD *)v9 + v10) );
    std::wstring::_Assign<unsigned short>((char *)this + 16, v9);
    v11 = RegOpenKeyExW(hKey, a2, 0, a3, (PHKEY)this + 1);
    if ( (v11 & 0xFFFFFFFD) != 0 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1F9,
        (unsigned int)"onecore\\vm\\common\\vml\\VmRegistry.h",
        (const char *)v11,
        phkResulta);
    v12 = v11 == 0;
    if ( hKey )
      RegCloseKey(hKey);
    return v12;
  }
}

```

## disassembly

```asm
0x180023990  push    rbx
0x180023992  push    rbp
0x180023993  push    rsi
0x180023994  push    rdi
0x180023995  push    r14
0x180023997  sub     rsp, 40h
0x18002399b  mov     rax, cs:__security_cookie
0x1800239a2  xor     rax, rsp
0x1800239a5  mov     [rsp+68h+var_30], rax
0x1800239aa  mov     ebp, r8d
0x1800239ad  mov     rdi, rdx
0x1800239b0  mov     rsi, rcx
0x1800239b3  xor     r14d, r14d
0x1800239b6  mov     [rsp+68h+hKey], r14
0x1800239bb  lea     rax, [rsp+68h+hKey]
0x1800239c0  mov     qword ptr [rsp+68h+phkResult], rax; unsigned int
0x1800239c5  mov     r9d, r8d; samDesired
0x1800239c8  xor     r8d, r8d; ulOptions
0x1800239cb  lea     rdx, ?g_SettingsRegistryPath@Vml@@3QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x1800239d2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800239d9  call    cs:__imp_RegOpenKeyExW
0x1800239df  test    eax, eax
0x1800239e1  jz      short loc_180023A00
0x1800239e3  cmp     eax, 2
0x1800239e6  jnz     loc_180023AA3
0x1800239ec  mov     rcx, [rsp+68h+hKey]; hKey
0x1800239f1  test    rcx, rcx
0x1800239f4  jz      short loc_1800239FC
0x1800239f6  call    cs:__imp_RegCloseKey
0x1800239fc  xor     al, al
0x1800239fe  jmp     short loc_180023A71
0x180023a00  lea     rbx, [rsi+8]
0x180023a04  mov     rcx, [rbx]; hKey
0x180023a07  test    rcx, rcx
0x180023a0a  jz      short loc_180023A15
0x180023a0c  call    cs:__imp_RegCloseKey
0x180023a12  mov     [rbx], r14
0x180023a15  lea     rdx, qword_1800AD7F8
0x180023a1c  test    rdi, rdi
0x180023a1f  cmovnz  rdx, rdi
0x180023a23  or      r8, 0FFFFFFFFFFFFFFFFh
0x180023a27  inc     r8
0x180023a2a  cmp     [rdx+r8*2], r14w
0x180023a2f  jnz     short loc_180023A27
0x180023a31  lea     rcx, [rsi+10h]
0x180023a35  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180023a3a  mov     qword ptr [rsp+68h+phkResult], rbx; unsigned int
0x180023a3f  mov     r9d, ebp; samDesired
0x180023a42  xor     r8d, r8d; ulOptions
0x180023a45  mov     rdx, rdi; lpSubKey
0x180023a48  mov     rcx, [rsp+68h+hKey]; hKey
0x180023a4d  call    cs:__imp_RegOpenKeyExW
0x180023a53  test    eax, 0FFFFFFFDh
0x180023a58  jnz     short loc_180023A89
0x180023a5a  test    eax, eax
0x180023a5c  setz    bl
0x180023a5f  mov     rcx, [rsp+68h+hKey]; hKey
0x180023a64  test    rcx, rcx
0x180023a67  jz      short loc_180023A6F
0x180023a69  call    cs:__imp_RegCloseKey
0x180023a6f  mov     al, bl
0x180023a71  mov     rcx, [rsp+68h+var_30]
0x180023a76  xor     rcx, rsp; StackCookie
0x180023a79  call    __security_check_cookie
0x180023a7e  add     rsp, 40h
0x180023a82  pop     r14
0x180023a84  pop     rdi
0x180023a85  pop     rsi
0x180023a86  pop     rbp
0x180023a87  pop     rbx
0x180023a88  retn
0x180023a89  mov     rcx, [rsp+68h]; this
0x180023a8e  mov     r9d, eax; char *
0x180023a91  lea     r8, aOnecoreVmCommo_35; "onecore\\vm\\common\\vml\\VmRegistry.h"
0x180023a98  mov     edx, 1F9h; void *
0x180023a9d  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180023aa3  mov     rcx, [rsp+68h]; this
0x180023aa8  mov     r9d, eax; char *
0x180023aab  lea     r8, aOnecoreVmCommo_35; "onecore\\vm\\common\\vml\\VmRegistry.h"
0x180023ab2  mov     edx, 1F9h; void *
0x180023ab7  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
