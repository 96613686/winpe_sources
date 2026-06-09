# RegistryConfig::GetNumericalValue(HKEY__ *,ushort const *,ulong *)

- ea: `0x18000b6a4`
- end: `0x18000b6f2`
- name: `?GetNumericalValue@RegistryConfig@@AEAAJPEAUHKEY__@@PEBGPEAK@Z`
- size: `78`
- prototype: `int(RegistryConfig *__hidden this, HKEY, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18000ba60`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b6d7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b6d7`

## pseudocode

```c
__int64 __fastcall RegistryConfig::GetNumericalValue(
        RegistryConfig *this,
        HKEY a2,
        const unsigned __int16 *a3,
        unsigned int *a4)
{
  DWORD v5; // [rsp+50h] [rbp+8h] BYREF
  int v6; // [rsp+54h] [rbp+Ch]

  v6 = HIDWORD(this);
  v5 = 4;
  return RegGetValueW(a2, 0, a3, 0x10u, 0, a4, &v5) != 0 ? 0x490 : 0;
}

```

## disassembly

```asm
0x18000b6a4  mov     r11, rsp
0x18000b6a7  mov     [r11+8], rcx
0x18000b6ab  sub     rsp, 48h
0x18000b6af  mov     rax, rdx
0x18000b6b2  mov     [rsp+48h+arg_0], 4
0x18000b6ba  lea     rcx, [r11+8]
0x18000b6be  xor     edx, edx; lpSubKey
0x18000b6c0  mov     [r11-18h], rcx
0x18000b6c4  mov     rcx, rax; hkey
0x18000b6c7  mov     [r11-20h], r9
0x18000b6cb  mov     qword ptr [r11-28h], 0
0x18000b6d3  lea     r9d, [rdx+10h]; dwFlags
0x18000b6d7  call    cs:__imp_RegGetValueW
0x18000b6de  nop     dword ptr [rax+rax+00h]
0x18000b6e3  neg     eax
0x18000b6e5  sbb     eax, eax
0x18000b6e7  and     eax, 490h
0x18000b6ec  add     rsp, 48h
0x18000b6f0  retn
```
