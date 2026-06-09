# MsiRegOpen64bitKey(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)

- ea: `0x14000669c`
- end: `0x1400066d2`
- name: `?MsiRegOpen64bitKey@@YAKPEAUHKEY__@@PEBGKKPEAPEAU1@@Z`
- size: `54`
- prototype: `unsigned int __fastcall(HKEY, const unsigned __int16 *, unsigned int, unsigned int, HKEY *)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x1400011e4`
- `0x140007110`

## callees

- `0x140003cbc`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1400066cb`

## pseudocode

```c
LSTATUS __fastcall MsiRegOpen64bitKey(HKEY a1, const unsigned __int16 *a2, __int64 a3, __int64 a4, HKEY *a5)
{
  LPCWSTR v5; // r10
  unsigned int v7[6]; // [rsp+30h] [rbp-18h] BYREF

  v7[0] = 131097;
  AdjustREGSAM(v7);
  return RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, v7[0], a5);
}

```

## disassembly

```asm
0x14000669c  sub     rsp, 48h
0x1400066a0  lea     rcx, [rsp+48h+var_18]; unsigned int *
0x1400066a5  mov     [rsp+48h+var_18], 20019h
0x1400066ad  mov     r10, rdx
0x1400066b0  call    ?AdjustREGSAM@@YAXAEAK@Z; AdjustREGSAM(ulong &)
0x1400066b5  xor     r8d, r8d
0x1400066b8  mov     r9d, [rsp+48h+var_18]
0x1400066bd  mov     rdx, r10
0x1400066c0  mov     rcx, 0FFFFFFFF80000002h
0x1400066c7  add     rsp, 48h
0x1400066cb  jmp     cs:__imp_RegOpenKeyExW
```
