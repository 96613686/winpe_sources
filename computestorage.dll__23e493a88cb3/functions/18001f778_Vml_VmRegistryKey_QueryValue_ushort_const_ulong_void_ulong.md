# Vml::VmRegistryKey::QueryValue(ushort const *,ulong,void *,ulong &)

- ea: `0x18001f778`
- end: `0x18001f867`
- name: `?QueryValue@VmRegistryKey@Vml@@QEBAHPEBGKPEAXAEAK@Z`
- size: `239`
- prototype: `int(Vml::VmRegistryKey *__hidden this, const unsigned __int16 *, unsigned int, void *, unsigned int *)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f190`
- `0x18001f200`
- `0x18001f2a0`
- `0x18001f470`
- `0x18001f50c`

## callees

- `0x180002690`
- `0x180012818`
- `0x180015a40`
- `0x180015b20`
- `0x18001f778`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001f7b9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001f7b9`

## string_xrefs

- `0x18001f80f`: `onecore\vm\common\vml\VmRegistry.h`
- `0x18001f84f`: `onecore\vm\common\vml\VmRegistry.h`
- `0x18001f839`: `Registry type mismatch - expected = %u, actual = %u`

## pseudocode

```c
__int64 __fastcall Vml::VmRegistryKey::QueryValue(
        HKEY *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        BYTE *a4,
        unsigned int *lpcbData)
{
  HKEY v6; // rcx
  unsigned int v8; // ebx
  unsigned int v9; // eax
  __int64 v10; // rdx
  unsigned int lpData; // [rsp+20h] [rbp-48h]
  DWORD Type; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v6 = *this;
  v8 = 0;
  Type = 0;
  v9 = RegQueryValueExW(v6, a2, 0, &Type, a4, lpcbData);
  if ( v9 == 2 )
  {
    *lpcbData = 0;
  }
  else if ( v9 != 234 )
  {
    if ( v9 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x487,
        (unsigned int)"onecore\\vm\\common\\vml\\VmRegistry.h",
        (const char *)v9,
        lpData);
    if ( Type != a3 && (a3 != 2 || Type != 1) )
    {
      if ( (unsigned int)VmlIsDebugTraceEnabled(16388, v10) )
        VmlDebugTrace(16388, L"Registry type mismatch - expected = %u, actual = %u", a3, Type);
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x48F,
        (unsigned int)"onecore\\vm\\common\\vml\\VmRegistry.h",
        (const char *)0x65D,
        lpData);
    }
    LOBYTE(v8) = a4 != 0;
  }
  return v8;
}

```

## disassembly

```asm
0x18001f778  push    rbx
0x18001f77a  push    rbp
0x18001f77b  push    rsi
0x18001f77c  push    rdi
0x18001f77d  sub     rsp, 48h
0x18001f781  mov     rax, cs:__security_cookie
0x18001f788  xor     rax, rsp
0x18001f78b  mov     [rsp+68h+var_30], rax
0x18001f790  mov     rsi, [rsp+68h+arg_20]
0x18001f798  mov     rbp, r9
0x18001f79b  mov     rcx, [rcx]; hKey
0x18001f79e  mov     edi, r8d
0x18001f7a1  mov     [rsp+68h+lpcbData], rsi; lpcbData
0x18001f7a6  xor     ebx, ebx
0x18001f7a8  mov     [rsp+68h+lpData], r9; unsigned int
0x18001f7ad  xor     r8d, r8d; lpReserved
0x18001f7b0  lea     r9, [rsp+68h+Type]; lpType
0x18001f7b5  mov     [rsp+68h+Type], ebx
0x18001f7b9  call    cs:__imp_RegQueryValueExW
0x18001f7c0  nop     dword ptr [rax+rax+00h]
0x18001f7c5  cmp     eax, 2
0x18001f7c8  jz      short loc_18001F7EF
0x18001f7ca  cmp     eax, 0EAh
0x18001f7cf  jz      short loc_18001F7F1
0x18001f7d1  test    eax, eax
0x18001f7d3  jnz     short loc_18001F80A
0x18001f7d5  cmp     [rsp+68h+Type], edi
0x18001f7d9  jz      short loc_18001F7E7
0x18001f7db  cmp     edi, 2
0x18001f7de  jnz     short loc_18001F824
0x18001f7e0  cmp     [rsp+68h+Type], 1
0x18001f7e5  jnz     short loc_18001F824
0x18001f7e7  test    rbp, rbp
0x18001f7ea  setnz   bl
0x18001f7ed  jmp     short loc_18001F7F1
0x18001f7ef  mov     [rsi], ebx
0x18001f7f1  mov     eax, ebx
0x18001f7f3  mov     rcx, [rsp+68h+var_30]
0x18001f7f8  xor     rcx, rsp; StackCookie
0x18001f7fb  call    __security_check_cookie
0x18001f800  add     rsp, 48h
0x18001f804  pop     rdi
0x18001f805  pop     rsi
0x18001f806  pop     rbp
0x18001f807  pop     rbx
0x18001f808  retn
0x18001f80a  mov     rcx, [rsp+68h]; this
0x18001f80f  lea     r8, aOnecoreVmCommo_8; "onecore\\vm\\common\\vml\\VmRegistry.h"
0x18001f816  mov     r9d, eax; char *
0x18001f819  mov     edx, 487h; void *
0x18001f81e  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18001f824  mov     ebx, 4004h
0x18001f829  mov     ecx, ebx
0x18001f82b  call    VmlIsDebugTraceEnabled
0x18001f830  test    eax, eax
0x18001f832  jz      short loc_18001F84A
0x18001f834  mov     r9d, [rsp+68h+Type]
0x18001f839  lea     rdx, aRegistryTypeMi; "Registry type mismatch - expected = %u,"...
0x18001f840  mov     r8d, edi
0x18001f843  mov     ecx, ebx
0x18001f845  call    VmlDebugTrace
0x18001f84a  mov     rcx, [rsp+68h]; this
0x18001f84f  lea     r8, aOnecoreVmCommo_8; "onecore\\vm\\common\\vml\\VmRegistry.h"
0x18001f856  mov     r9d, 65Dh; char *
0x18001f85c  mov     edx, 48Fh; void *
0x18001f861  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
