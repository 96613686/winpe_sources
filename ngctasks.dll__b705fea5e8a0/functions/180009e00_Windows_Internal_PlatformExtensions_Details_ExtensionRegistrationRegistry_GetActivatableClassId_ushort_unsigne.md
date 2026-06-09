# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::GetActivatableClassId(ushort *,unsigned __int64)

- ea: `0x180009e00`
- end: `0x180009e62`
- name: `?GetActivatableClassId@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@UEBAJPEAG_K@Z`
- size: `98`
- prototype: `int __fastcall(HKEY *this, unsigned __int16 *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x180009e00`
- `0x18000cc58`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180009e36`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180009e36`

## string_xrefs

- `0x180009e48`: `onecoreuap\internal\shell\inc\platformextensiontools.h`
- `0x180009e29`: `ActivatableClassID`

## pseudocode

```c
int __fastcall Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::GetActivatableClassId(
        HKEY *this,
        unsigned __int16 *a2,
        int a3)
{
  unsigned int ValueW; // eax
  unsigned int v5; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v7; // [rsp+50h] [rbp+8h] BYREF

  v7 = 2 * a3;
  ValueW = RegGetValueW(this[1], 0, L"ActivatableClassID", 2u, 0, a2, (LPDWORD)&v7);
  if ( ValueW )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x107,
             (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
             (const char *)ValueW,
             v5);
  else
    return 0;
}

```

## disassembly

```asm
0x180009e00  mov     r11, rsp
0x180009e03  sub     rsp, 48h
0x180009e07  lea     eax, [r8+r8]
0x180009e0b  mov     [rsp+48h+arg_0], eax
0x180009e0f  lea     rax, [r11+8]
0x180009e13  mov     [r11-18h], rax
0x180009e17  mov     [r11-20h], rdx
0x180009e1b  mov     qword ptr [r11-28h], 0
0x180009e23  mov     r9d, 2; dwFlags
0x180009e29  lea     r8, Value; "ActivatableClassID"
0x180009e30  xor     edx, edx; lpSubKey
0x180009e32  mov     rcx, [rcx+8]; hkey
0x180009e36  call    cs:__imp_RegGetValueW
0x180009e3c  test    eax, eax
0x180009e3e  jz      short loc_180009E5B
0x180009e40  mov     rcx, [rsp+48h]; this
0x180009e45  mov     r9d, eax; char *
0x180009e48  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x180009e4f  mov     edx, 107h; void *
0x180009e54  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180009e59  jmp     short loc_180009E5D
0x180009e5b  xor     eax, eax
0x180009e5d  add     rsp, 48h
0x180009e61  retn
```
