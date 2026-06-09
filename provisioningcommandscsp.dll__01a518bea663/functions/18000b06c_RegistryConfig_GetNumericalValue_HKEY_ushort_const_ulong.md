# RegistryConfig::GetNumericalValue(HKEY__ *,ushort const *,ulong *)

- ea: `0x18000b06c`
- end: `0x18000b0b3`
- name: `?GetNumericalValue@RegistryConfig@@AEAAJPEAUHKEY__@@PEBGPEAK@Z`
- size: `71`
- prototype: `__int64 __fastcall(RegistryConfig *this, HKEY, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x18000b3f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b09f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000b09f`

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
0x18000b06c  mov     r11, rsp
0x18000b06f  mov     [r11+8], rcx
0x18000b073  sub     rsp, 48h
0x18000b077  mov     rax, rdx
0x18000b07a  mov     [rsp+48h+arg_0], 4
0x18000b082  lea     rcx, [r11+8]
0x18000b086  xor     edx, edx; lpSubKey
0x18000b088  mov     [r11-18h], rcx
0x18000b08c  mov     rcx, rax; hkey
0x18000b08f  mov     [r11-20h], r9
0x18000b093  mov     qword ptr [r11-28h], 0
0x18000b09b  lea     r9d, [rdx+10h]; dwFlags
0x18000b09f  call    cs:__imp_RegGetValueW
0x18000b0a5  neg     eax
0x18000b0a7  sbb     eax, eax
0x18000b0a9  and     eax, 490h
0x18000b0ae  add     rsp, 48h
0x18000b0b2  retn
```
