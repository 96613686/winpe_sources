# RegistryValuePresent(HKEY__ *,ushort const *)

- ea: `0x18001059c`
- end: `0x1800105ec`
- name: `?RegistryValuePresent@@YA_NPEAUHKEY__@@PEBG@Z`
- size: `80`
- prototype: `char __fastcall(HKEY, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000afe4`

## callees

- `0x18000c43c`
- `0x18001059c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800105b8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800105b8`

## string_xrefs

- `0x1800105d7`: `onecoreuap\ds\ext\common\lib\registryhelpers\registryhelpers.cpp`

## pseudocode

```c
char __fastcall RegistryValuePresent(HKEY a1, const unsigned __int16 *a2)
{
  unsigned int Value; // eax
  unsigned int lpData; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  Value = RegQueryValueExW(a1, a2, 0, 0, 0, 0);
  if ( !Value )
    return 1;
  if ( Value != 2 )
    wil::details::in1diag3::_Throw_Win32(
      retaddr,
      (void *)0xAC,
      (int)"onecoreuap\\ds\\ext\\common\\lib\\registryhelpers\\registryhelpers.cpp",
      (const char *)Value,
      lpData);
  return 0;
}

```

## disassembly

```asm
0x18001059c  sub     rsp, 38h
0x1800105a0  mov     [rsp+38h+lpcbData], 0; lpcbData
0x1800105a9  xor     r9d, r9d; lpType
0x1800105ac  xor     r8d, r8d; lpReserved
0x1800105af  mov     [rsp+38h+lpData], 0; unsigned int
0x1800105b8  call    cs:__imp_RegQueryValueExW
0x1800105be  test    eax, eax
0x1800105c0  jnz     short loc_1800105C9
0x1800105c2  mov     al, 1
0x1800105c4  add     rsp, 38h
0x1800105c8  retn
0x1800105c9  cmp     eax, 2
0x1800105cc  jnz     short loc_1800105D2
0x1800105ce  xor     al, al
0x1800105d0  jmp     short loc_1800105C4
0x1800105d2  mov     rcx, [rsp+38h]; this
0x1800105d7  lea     r8, aOnecoreuapDsEx_2; "onecoreuap\\ds\\ext\\common\\lib\\regis"...
0x1800105de  mov     r9d, eax; char *
0x1800105e1  mov     edx, 0ACh; void *
0x1800105e6  call    ?_Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Throw_Win32(void *,uint,char const *,ulong)
```
