# RegistryConfig::GetNumericalValue(HKEY__ *,ushort const *,ulong *)

- ea: `0x1400089dc`
- end: `0x140008a23`
- name: `?GetNumericalValue@RegistryConfig@@AEAAJPEAUHKEY__@@PEBGPEAK@Z`
- size: `71`
- prototype: `int(RegistryConfig *__hidden this, HKEY, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x140008ce4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140008a0f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140008a0f`

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
0x1400089dc  mov     r11, rsp
0x1400089df  mov     [r11+8], rcx
0x1400089e3  sub     rsp, 48h
0x1400089e7  mov     rax, rdx
0x1400089ea  mov     [rsp+48h+arg_0], 4
0x1400089f2  lea     rcx, [r11+8]
0x1400089f6  xor     edx, edx; lpSubKey
0x1400089f8  mov     [r11-18h], rcx
0x1400089fc  mov     rcx, rax; hkey
0x1400089ff  mov     [r11-20h], r9
0x140008a03  mov     qword ptr [r11-28h], 0
0x140008a0b  lea     r9d, [rdx+10h]; dwFlags
0x140008a0f  call    cs:__imp_RegGetValueW
0x140008a15  neg     eax
0x140008a17  sbb     eax, eax
0x140008a19  and     eax, 490h
0x140008a1e  add     rsp, 48h
0x140008a22  retn
```
