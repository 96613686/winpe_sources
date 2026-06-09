# Vml::VmMachineLocalSettingsStore::Open(ushort const *,ulong)

- ea: `0x18001e590`
- end: `0x18001e6df`
- name: `?Open@VmMachineLocalSettingsStore@Vml@@UEAA_NPEBGK@Z`
- size: `335`
- prototype: `bool(Vml::VmMachineLocalSettingsStore *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002690`
- `0x180006c00`
- `0x180012818`
- `0x18001e590`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e5fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e61b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e684`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e5fc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e61b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e684`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e5d9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e662`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e5d9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001e662`

## string_xrefs

- `0x18001e6b3`: `onecore\vm\common\vml\VmRegistry.h`
- `0x18001e6cd`: `onecore\vm\common\vml\VmRegistry.h`

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
  unsigned __int64 v10; // r8
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
    v9 = &qword_18004C4D0;
    if ( a2 )
      v9 = (__int64 *)a2;
    v10 = -1;
    do
      ++v10;
    while ( *((_WORD *)v9 + v10) );
    std::wstring::_Assign<unsigned short>((void **)this + 2, v9, v10);
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
0x18001e590  push    rbx
0x18001e592  push    rbp
0x18001e593  push    rsi
0x18001e594  push    rdi
0x18001e595  push    r14
0x18001e597  sub     rsp, 40h
0x18001e59b  mov     rax, cs:__security_cookie
0x18001e5a2  xor     rax, rsp
0x18001e5a5  mov     [rsp+68h+var_30], rax
0x18001e5aa  mov     ebp, r8d
0x18001e5ad  mov     rdi, rdx
0x18001e5b0  mov     rsi, rcx
0x18001e5b3  xor     r14d, r14d
0x18001e5b6  mov     [rsp+68h+hKey], r14
0x18001e5bb  lea     rax, [rsp+68h+hKey]
0x18001e5c0  mov     qword ptr [rsp+68h+phkResult], rax; unsigned int
0x18001e5c5  mov     r9d, r8d; samDesired
0x18001e5c8  xor     r8d, r8d; ulOptions
0x18001e5cb  lea     rdx, ?g_SettingsRegistryPath@Vml@@3QBGB; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18001e5d2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e5d9  call    cs:__imp_RegOpenKeyExW
0x18001e5e0  nop     dword ptr [rax+rax+00h]
0x18001e5e5  test    eax, eax
0x18001e5e7  jz      short loc_18001E60F
0x18001e5e9  cmp     eax, 2
0x18001e5ec  jnz     loc_18001E6C5
0x18001e5f2  mov     rcx, [rsp+68h+hKey]; hKey
0x18001e5f7  test    rcx, rcx
0x18001e5fa  jz      short loc_18001E608
0x18001e5fc  call    cs:__imp_RegCloseKey
0x18001e603  nop     dword ptr [rax+rax+00h]
0x18001e608  xor     al, al
0x18001e60a  jmp     loc_18001E692
0x18001e60f  lea     rbx, [rsi+8]
0x18001e613  mov     rcx, [rbx]; hKey
0x18001e616  test    rcx, rcx
0x18001e619  jz      short loc_18001E62A
0x18001e61b  call    cs:__imp_RegCloseKey
0x18001e622  nop     dword ptr [rax+rax+00h]
0x18001e627  mov     [rbx], r14
0x18001e62a  lea     rdx, qword_18004C4D0
0x18001e631  test    rdi, rdi
0x18001e634  cmovnz  rdx, rdi
0x18001e638  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001e63c  inc     r8
0x18001e63f  cmp     [rdx+r8*2], r14w
0x18001e644  jnz     short loc_18001E63C
0x18001e646  lea     rcx, [rsi+10h]
0x18001e64a  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18001e64f  mov     qword ptr [rsp+68h+phkResult], rbx; unsigned int
0x18001e654  mov     r9d, ebp; samDesired
0x18001e657  xor     r8d, r8d; ulOptions
0x18001e65a  mov     rdx, rdi; lpSubKey
0x18001e65d  mov     rcx, [rsp+68h+hKey]; hKey
0x18001e662  call    cs:__imp_RegOpenKeyExW
0x18001e669  nop     dword ptr [rax+rax+00h]
0x18001e66e  test    eax, 0FFFFFFFDh
0x18001e673  jnz     short loc_18001E6AB
0x18001e675  test    eax, eax
0x18001e677  setz    bl
0x18001e67a  mov     rcx, [rsp+68h+hKey]; hKey
0x18001e67f  test    rcx, rcx
0x18001e682  jz      short loc_18001E690
0x18001e684  call    cs:__imp_RegCloseKey
0x18001e68b  nop     dword ptr [rax+rax+00h]
0x18001e690  mov     al, bl
0x18001e692  mov     rcx, [rsp+68h+var_30]
0x18001e697  xor     rcx, rsp; StackCookie
0x18001e69a  call    __security_check_cookie
0x18001e69f  add     rsp, 40h
0x18001e6a3  pop     r14
0x18001e6a5  pop     rdi
0x18001e6a6  pop     rsi
0x18001e6a7  pop     rbp
0x18001e6a8  pop     rbx
0x18001e6a9  retn
0x18001e6ab  mov     rcx, [rsp+68h]; this
0x18001e6b0  mov     r9d, eax; char *
0x18001e6b3  lea     r8, aOnecoreVmCommo_8; "onecore\\vm\\common\\vml\\VmRegistry.h"
0x18001e6ba  mov     edx, 1F9h; void *
0x18001e6bf  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18001e6c5  mov     rcx, [rsp+68h]; this
0x18001e6ca  mov     r9d, eax; char *
0x18001e6cd  lea     r8, aOnecoreVmCommo_8; "onecore\\vm\\common\\vml\\VmRegistry.h"
0x18001e6d4  mov     edx, 1F9h; void *
0x18001e6d9  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
