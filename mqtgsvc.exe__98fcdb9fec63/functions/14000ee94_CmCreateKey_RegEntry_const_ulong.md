# CmCreateKey(RegEntry const &,ulong)

- ea: `0x14000ee94`
- end: `0x14000ef2b`
- name: `?CmCreateKey@@YAPEAUHKEY__@@AEBVRegEntry@@K@Z`
- size: `151`
- prototype: `HKEY __fastcall(const struct RegEntry *, REGSAM samDesired)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x14000f59c`
- `0x140011d38`

## callees

- `0x14000ee94`
- `0x14000f61c`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x14000eefe`
- `ADVAPI32!RegCreateKeyExW` at `0x14000eefe`

## pseudocode

```c
HKEY __fastcall CmCreateKey(const struct RegEntry *a1, REGSAM samDesired)
{
  const WCHAR *v2; // rax
  HKEY v4; // rcx
  bool v5; // zf
  int v6; // eax
  DWORD v8; // [rsp+60h] [rbp+8h] BYREF
  HKEY v9; // [rsp+70h] [rbp+18h] BYREF

  v2 = &ServiceName;
  if ( *((_QWORD *)a1 + 1) )
    v2 = (const WCHAR *)*((_QWORD *)a1 + 1);
  v4 = (HKEY)qword_14002AF40;
  v5 = *((_QWORD *)a1 + 4) == 0;
  v9 = 0;
  if ( !v5 )
    v4 = (HKEY)*((_QWORD *)a1 + 4);
  v8 = 0;
  v6 = RegCreateKeyExW(v4, v2, 0, 0, 0, samDesired, 0, &v9, &v8);
  if ( !v6 )
    return v9;
  if ( v6 > 0 )
    v6 = (unsigned __int16)v6 | 0x80070000;
  ThrowMissingValue(a1, v6);
  return 0;
}

```

## disassembly

```asm
0x14000ee94  mov     r11, rsp
0x14000ee97  push    rbx
0x14000ee98  sub     rsp, 50h
0x14000ee9c  cmp     qword ptr [rcx+8], 0
0x14000eea1  lea     r8, [r11+8]
0x14000eea5  mov     [r11-18h], r8
0x14000eea9  lea     rax, ServiceName
0x14000eeb0  cmovnz  rax, [rcx+8]
0x14000eeb5  lea     r8, [r11+18h]
0x14000eeb9  mov     [r11-20h], r8
0x14000eebd  mov     rbx, rcx
0x14000eec0  mov     rcx, cs:qword_14002AF40
0x14000eec7  mov     qword ptr [r11-28h], 0
0x14000eecf  mov     [rsp+58h+samDesired], edx; samDesired
0x14000eed3  mov     rdx, rax; lpSubKey
0x14000eed6  cmp     qword ptr [rbx+20h], 0
0x14000eedb  mov     qword ptr [r11+18h], 0
0x14000eee3  cmovnz  rcx, [rbx+20h]; hKey
0x14000eee8  xor     r9d, r9d; lpClass
0x14000eeeb  xor     r8d, r8d; Reserved
0x14000eeee  mov     [rsp+58h+arg_0], 0
0x14000eef6  mov     [rsp+58h+dwOptions], 0; dwOptions
0x14000eefe  call    cs:__imp_RegCreateKeyExW
0x14000ef04  test    eax, eax
0x14000ef06  jz      short loc_14000EF20
0x14000ef08  jle     short loc_14000EF12
0x14000ef0a  movzx   eax, ax
0x14000ef0d  or      eax, 80070000h
0x14000ef12  mov     edx, eax; int
0x14000ef14  mov     rcx, rbx; struct RegEntry *
0x14000ef17  call    ?ThrowMissingValue@@YAXAEBVRegEntry@@J@Z; ThrowMissingValue(RegEntry const &,long)
0x14000ef1c  xor     eax, eax
0x14000ef1e  jmp     short loc_14000EF25
0x14000ef20  mov     rax, [rsp+58h+arg_10]
0x14000ef25  add     rsp, 50h
0x14000ef29  pop     rbx
0x14000ef2a  retn
```
