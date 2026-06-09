# Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::GetCount(unsigned __int64 *)

- ea: `0x18000a160`
- end: `0x18000a1ff`
- name: `?GetCount@ExtensionRegistrationCollectionRegistry@Details@PlatformExtensions@Internal@Windows@@UEBAJPEA_K@Z`
- size: `159`
- prototype: `int __fastcall(Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry *this, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callees

- `0x18000a160`
- `0x18000cc58`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000a1cb`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18000a1cb`

## string_xrefs

- `0x18000a1dd`: `onecoreuap\internal\shell\inc\platformextensiontools.h`

## pseudocode

```c
int __fastcall Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry::GetCount(
        Windows::Internal::PlatformExtensions::Details::ExtensionRegistrationCollectionRegistry *this,
        unsigned __int64 *a2)
{
  HKEY v3; // rcx
  unsigned int v4; // eax
  unsigned int lpcSubKeys; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  DWORD v8; // [rsp+70h] [rbp+8h] BYREF

  *a2 = 0;
  v3 = (HKEY)*((_QWORD *)this + 1);
  if ( v3 )
  {
    v8 = 0;
    v4 = RegQueryInfoKeyW(v3, 0, 0, 0, &v8, 0, 0, 0, 0, 0, 0, 0);
    if ( v4 )
      return wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x137,
               (unsigned int)"onecoreuap\\internal\\shell\\inc\\platformextensiontools.h",
               (const char *)v4,
               lpcSubKeys);
    *a2 = v8;
  }
  return 0;
}

```

## disassembly

```asm
0x18000a160  mov     rax, rsp
0x18000a163  push    rbx
0x18000a164  sub     rsp, 60h
0x18000a168  mov     rbx, rdx
0x18000a16b  mov     qword ptr [rdx], 0
0x18000a172  mov     rcx, [rcx+8]; hKey
0x18000a176  test    rcx, rcx
0x18000a179  jz      short loc_18000A1F7
0x18000a17b  mov     dword ptr [rax+8], 0
0x18000a182  mov     qword ptr [rax-10h], 0
0x18000a18a  mov     qword ptr [rax-18h], 0
0x18000a192  mov     qword ptr [rax-20h], 0
0x18000a19a  mov     qword ptr [rax-28h], 0
0x18000a1a2  mov     qword ptr [rax-30h], 0
0x18000a1aa  mov     qword ptr [rax-38h], 0
0x18000a1b2  mov     qword ptr [rax-40h], 0
0x18000a1ba  lea     rax, [rax+8]
0x18000a1be  mov     qword ptr [rsp+68h+lpcSubKeys], rax; unsigned int
0x18000a1c3  xor     r9d, r9d; lpReserved
0x18000a1c6  xor     r8d, r8d; lpcchClass
0x18000a1c9  xor     edx, edx; lpClass
0x18000a1cb  call    cs:__imp_RegQueryInfoKeyW
0x18000a1d1  test    eax, eax
0x18000a1d3  jz      short loc_18000A1F0
0x18000a1d5  mov     rcx, [rsp+68h]; this
0x18000a1da  mov     r9d, eax; char *
0x18000a1dd  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\platf"...
0x18000a1e4  mov     edx, 137h; void *
0x18000a1e9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18000a1ee  jmp     short loc_18000A1F9
0x18000a1f0  mov     eax, [rsp+68h+arg_0]
0x18000a1f4  mov     [rbx], rax
0x18000a1f7  xor     eax, eax
0x18000a1f9  add     rsp, 60h
0x18000a1fd  pop     rbx
0x18000a1fe  retn
```
