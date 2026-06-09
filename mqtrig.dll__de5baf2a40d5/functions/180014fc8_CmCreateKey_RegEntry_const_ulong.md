# CmCreateKey(RegEntry const &,ulong)

- ea: `0x180014fc8`
- end: `0x18001505f`
- name: `?CmCreateKey@@YAPEAUHKEY__@@AEBVRegEntry@@K@Z`
- size: `151`
- prototype: `HKEY __fastcall(const struct RegEntry *, REGSAM samDesired)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800156d4`
- `0x180016944`
- `0x1800199a0`
- `0x180019dc0`

## callees

- `0x180014fc8`
- `0x180015748`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x180015032`
- `ADVAPI32!RegCreateKeyExW` at `0x180015032`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HKEY __fastcall CmCreateKey(const struct RegEntry *a1, REGSAM samDesired)
{
  const WCHAR *v2; // rax
  HKEY v4; // rcx
  bool v5; // zf
  int v6; // eax
  DWORD v8; // [rsp+60h] [rbp+8h] BYREF
  HKEY v9; // [rsp+70h] [rbp+18h] BYREF

  v2 = &psz;
  if ( *((_QWORD *)a1 + 1) )
    v2 = (const WCHAR *)*((_QWORD *)a1 + 1);
  v4 = (HKEY)qword_18002D0F0;
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
0x180014fc8  mov     r11, rsp
0x180014fcb  push    rbx
0x180014fcc  sub     rsp, 50h
0x180014fd0  cmp     qword ptr [rcx+8], 0
0x180014fd5  lea     r8, [r11+8]
0x180014fd9  mov     [r11-18h], r8
0x180014fdd  lea     rax, psz
0x180014fe4  cmovnz  rax, [rcx+8]
0x180014fe9  lea     r8, [r11+18h]
0x180014fed  mov     [r11-20h], r8
0x180014ff1  mov     rbx, rcx
0x180014ff4  mov     rcx, cs:qword_18002D0F0
0x180014ffb  mov     qword ptr [r11-28h], 0
0x180015003  mov     [rsp+58h+samDesired], edx; samDesired
0x180015007  mov     rdx, rax; lpSubKey
0x18001500a  cmp     qword ptr [rbx+20h], 0
0x18001500f  mov     qword ptr [r11+18h], 0
0x180015017  cmovnz  rcx, [rbx+20h]; hKey
0x18001501c  xor     r9d, r9d; lpClass
0x18001501f  xor     r8d, r8d; Reserved
0x180015022  mov     [rsp+58h+arg_0], 0
0x18001502a  mov     [rsp+58h+dwOptions], 0; dwOptions
0x180015032  call    cs:__imp_RegCreateKeyExW
0x180015038  test    eax, eax
0x18001503a  jz      short loc_180015054
0x18001503c  jle     short loc_180015046
0x18001503e  movzx   eax, ax
0x180015041  or      eax, 80070000h
0x180015046  mov     edx, eax; int
0x180015048  mov     rcx, rbx; struct RegEntry *
0x18001504b  call    ?ThrowMissingValue@@YAXAEBVRegEntry@@J@Z; ThrowMissingValue(RegEntry const &,long)
0x180015050  xor     eax, eax
0x180015052  jmp     short loc_180015059
0x180015054  mov     rax, [rsp+58h+arg_10]
0x180015059  add     rsp, 50h
0x18001505d  pop     rbx
0x18001505e  retn
```
