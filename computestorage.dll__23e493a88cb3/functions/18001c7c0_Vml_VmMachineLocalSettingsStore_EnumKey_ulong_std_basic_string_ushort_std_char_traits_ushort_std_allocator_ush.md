# Vml::VmMachineLocalSettingsStore::EnumKey(ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18001c7c0`
- end: `0x18001c904`
- name: `?EnumKey@VmMachineLocalSettingsStore@Vml@@UEBA_NKAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `324`
- prototype: `char __fastcall(__int64, DWORD, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180002690`
- `0x180012818`
- `0x180013cb4`
- `0x18001c7c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001c883`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18001c883`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001c81f`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001c81f`

## string_xrefs

- `0x18001c8d2`: `onecore\vm\common\vml\VmRegistry.h`
- `0x18001c8ef`: `onecore\vm\common\vml\VmRegistry.h`

## pseudocode

```c
char __fastcall Vml::VmMachineLocalSettingsStore::EnumKey(__int64 a1, DWORD a2, _QWORD *a3)
{
  HKEY v6; // rcx
  unsigned int v7; // eax
  char v8; // di
  bool v9; // cc
  WCHAR *v10; // r8
  unsigned int v11; // eax
  unsigned int lpcSubKeys; // [rsp+20h] [rbp-88h]
  unsigned int lpcSubKeysa; // [rsp+20h] [rbp-88h]
  DWORD cchName; // [rsp+60h] [rbp-48h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+68h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v6 = *(HKEY *)(a1 + 8);
  cchName = 0;
  v7 = RegQueryInfoKeyW(v6, 0, 0, 0, 0, &cchName, 0, 0, 0, 0, 0, 0);
  if ( v7 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x3FB,
      (unsigned int)"onecore\\vm\\common\\vml\\VmRegistry.h",
      (const char *)v7,
      lpcSubKeys);
  v8 = 1;
  ++cchName;
  std::wstring::resize(a3);
  v9 = a3[3] <= 7u;
  ftLastWriteTime = 0;
  if ( v9 )
    v10 = (WCHAR *)a3;
  else
    v10 = (WCHAR *)*a3;
  v11 = RegEnumKeyExW(*(HKEY *)(a1 + 8), a2, v10, &cchName, 0, 0, 0, &ftLastWriteTime);
  if ( v11 == 259 )
    return 0;
  if ( v11 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x408,
      (unsigned int)"onecore\\vm\\common\\vml\\VmRegistry.h",
      (const char *)v11,
      lpcSubKeysa);
  std::wstring::resize(a3);
  return v8;
}

```

## disassembly

```asm
0x18001c7c0  mov     r11, rsp
0x18001c7c3  push    rbx
0x18001c7c4  push    rbp
0x18001c7c5  push    rsi
0x18001c7c6  push    rdi
0x18001c7c7  push    r14
0x18001c7c9  sub     rsp, 80h
0x18001c7d0  mov     rax, cs:__security_cookie
0x18001c7d7  xor     rax, rsp
0x18001c7da  mov     [rsp+0A8h+var_38], rax
0x18001c7df  xor     r14d, r14d
0x18001c7e2  lea     rax, [r11-48h]
0x18001c7e6  mov     [r11-50h], r14
0x18001c7ea  mov     rbx, r8
0x18001c7ed  mov     [r11-58h], r14
0x18001c7f1  mov     ebp, edx
0x18001c7f3  mov     [r11-60h], r14
0x18001c7f7  mov     rsi, rcx
0x18001c7fa  mov     rcx, [rcx+8]; hKey
0x18001c7fe  xor     r9d, r9d; lpReserved
0x18001c801  mov     [r11-68h], r14
0x18001c805  xor     r8d, r8d; lpcchClass
0x18001c808  mov     [r11-70h], r14
0x18001c80c  xor     edx, edx; lpClass
0x18001c80e  mov     [r11-78h], r14
0x18001c812  mov     [r11-80h], rax
0x18001c816  mov     [rsp+0A8h+lpcSubKeys], r14; unsigned int
0x18001c81b  mov     [r11-48h], r14d
0x18001c81f  call    cs:__imp_RegQueryInfoKeyW
0x18001c826  nop     dword ptr [rax+rax+00h]
0x18001c82b  test    eax, eax
0x18001c82d  jnz     loc_18001C8E7
0x18001c833  mov     eax, [rsp+0A8h+cchName]
0x18001c837  lea     edi, [r14+1]
0x18001c83b  mov     edx, eax
0x18001c83d  mov     rcx, rbx; Src
0x18001c840  add     eax, edi
0x18001c842  mov     [rsp+0A8h+cchName], eax
0x18001c846  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18001c84b  cmp     qword ptr [rbx+18h], 7
0x18001c850  mov     qword ptr [rsp+0A8h+ftLastWriteTime.dwLowDateTime], r14
0x18001c855  jbe     short loc_18001C85C
0x18001c857  mov     r8, [rbx]
0x18001c85a  jmp     short loc_18001C85F
0x18001c85c  mov     r8, rbx; lpName
0x18001c85f  mov     rcx, [rsi+8]; hKey
0x18001c863  lea     rax, [rsp+0A8h+ftLastWriteTime]
0x18001c868  mov     [rsp+0A8h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18001c86d  lea     r9, [rsp+0A8h+cchName]; lpcchName
0x18001c872  mov     [rsp+0A8h+lpcchClass], r14; lpcchClass
0x18001c877  mov     edx, ebp; dwIndex
0x18001c879  mov     [rsp+0A8h+lpClass], r14; lpClass
0x18001c87e  mov     [rsp+0A8h+lpcSubKeys], r14; unsigned int
0x18001c883  call    cs:__imp_RegEnumKeyExW
0x18001c88a  nop     dword ptr [rax+rax+00h]
0x18001c88f  cmp     eax, 103h
0x18001c894  jnz     short loc_18001C89B
0x18001c896  mov     dil, r14b
0x18001c899  jmp     short loc_18001C8AB
0x18001c89b  test    eax, eax
0x18001c89d  jnz     short loc_18001C8CA
0x18001c89f  mov     edx, [rsp+0A8h+cchName]
0x18001c8a3  mov     rcx, rbx; Src
0x18001c8a6  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18001c8ab  mov     al, dil
0x18001c8ae  mov     rcx, [rsp+0A8h+var_38]
0x18001c8b3  xor     rcx, rsp; StackCookie
0x18001c8b6  call    __security_check_cookie
0x18001c8bb  add     rsp, 80h
0x18001c8c2  pop     r14
0x18001c8c4  pop     rdi
0x18001c8c5  pop     rsi
0x18001c8c6  pop     rbp
0x18001c8c7  pop     rbx
0x18001c8c8  retn
0x18001c8ca  mov     rcx, [rsp+0A8h]; this
0x18001c8d2  lea     r8, aOnecoreVmCommo_8; "onecore\\vm\\common\\vml\\VmRegistry.h"
0x18001c8d9  mov     r9d, eax; char *
0x18001c8dc  mov     edx, 408h; void *
0x18001c8e1  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18001c8e7  mov     rcx, [rsp+0A8h]; this
0x18001c8ef  lea     r8, aOnecoreVmCommo_8; "onecore\\vm\\common\\vml\\VmRegistry.h"
0x18001c8f6  mov     r9d, eax; char *
0x18001c8f9  mov     edx, 3FBh; void *
0x18001c8fe  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
