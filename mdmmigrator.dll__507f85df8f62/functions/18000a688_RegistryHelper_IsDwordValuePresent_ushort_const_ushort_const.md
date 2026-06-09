# RegistryHelper::IsDwordValuePresent(ushort const *,ushort const *)

- ea: `0x18000a688`
- end: `0x18000a6eb`
- name: `?IsDwordValuePresent@RegistryHelper@@SA_NPEBG0@Z`
- size: `99`
- prototype: `bool __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, installer_update`

## callers

- `0x180007890`
- `0x180008940`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a6ce`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000a6ce`

## pseudocode

```c
bool __fastcall RegistryHelper::IsDwordValuePresent(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  LSTATUS ValueW; // eax
  int v3; // ecx
  DWORD v5; // [rsp+58h] [rbp+10h] BYREF
  int v6; // [rsp+5Ch] [rbp+14h]

  v6 = HIDWORD(a2);
  v5 = 0;
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, L"SYSTEM\\Setup", L"Upgrade", 0x10u, 0, 0, &v5);
  v3 = -2147024896;
  if ( ValueW <= 0 )
    v3 = ValueW;
  return v3 >= 0;
}

```

## disassembly

```asm
0x18000a688  mov     r11, rsp
0x18000a68b  mov     [r11+10h], rdx
0x18000a68f  sub     rsp, 48h
0x18000a693  lea     rax, [r11+10h]
0x18000a697  mov     [rsp+48h+arg_8], 0
0x18000a69f  mov     [r11-18h], rax
0x18000a6a3  lea     r8, Value; "Upgrade"
0x18000a6aa  mov     qword ptr [r11-20h], 0
0x18000a6b2  lea     rdx, SubKey; "SYSTEM\\Setup"
0x18000a6b9  mov     r9d, 10h; dwFlags
0x18000a6bf  mov     qword ptr [r11-28h], 0
0x18000a6c7  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000a6ce  call    cs:__imp_RegGetValueW
0x18000a6d4  test    eax, eax
0x18000a6d6  mov     ecx, 80070000h
0x18000a6db  cmovle  ecx, eax
0x18000a6de  shr     ecx, 1Fh
0x18000a6e1  xor     cl, 1
0x18000a6e4  mov     al, cl
0x18000a6e6  add     rsp, 48h
0x18000a6ea  retn
```
