# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::GetExtensionClass(ushort *,unsigned __int64)

- ea: `0x18000a260`
- end: `0x18000a2a6`
- name: `?GetExtensionClass@ExtensionRegistrationRegistry@Details@PlatformExtensions@Internal@Windows@@UEBAJPEAG_K@Z`
- size: `70`
- prototype: `__int64 __fastcall(Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry *this, unsigned __int16 *, unsigned __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x18000a260`
- `0x18000cc34`
- `0x18000df08`

## string_xrefs

- `0x18000a286`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

## pseudocode

```c
__int64 __fastcall Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry::GetExtensionClass(
        Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationRegistry *this,
        unsigned __int16 *a2,
        unsigned __int64 a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = StringCchCopyW(a2, a3, (const unsigned __int16 *)this + 12);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x100,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
    (const char *)(unsigned int)v3,
    v6);
  return v4;
}

```

## disassembly

```asm
0x18000a260  push    rbx; int
0x18000a262  sub     rsp, 20h
0x18000a266  mov     rax, r8
0x18000a269  mov     r9, rdx
0x18000a26c  lea     r8, [rcx+18h]; unsigned __int16 *
0x18000a270  mov     rdx, rax; unsigned __int64
0x18000a273  mov     rcx, r9; unsigned __int16 *
0x18000a276  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a27b  mov     ebx, eax
0x18000a27d  test    eax, eax
0x18000a27f  jns     short loc_18000A29E
0x18000a281  mov     rcx, [rsp+28h]; this
0x18000a286  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18000a28d  mov     r9d, eax; char *
0x18000a290  mov     edx, 100h; void *
0x18000a295  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a29a  mov     eax, ebx
0x18000a29c  jmp     short loc_18000A2A0
0x18000a29e  xor     eax, eax
0x18000a2a0  add     rsp, 20h
0x18000a2a4  pop     rbx
0x18000a2a5  retn
```
