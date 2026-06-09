# CmDeleteKey(RegEntry const &)

- ea: `0x14000ef34`
- end: `0x14000ef7b`
- name: `?CmDeleteKey@@YAXAEBVRegEntry@@@Z`
- size: `71`
- prototype: `void __fastcall(const struct RegEntry *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140011d38`

## callees

- `0x14000ef34`
- `0x14000f61c`

## import_xrefs

- `ADVAPI32!RegDeleteKeyW` at `0x14000ef52`
- `ADVAPI32!RegDeleteKeyW` at `0x14000ef52`

## pseudocode

```c
void __fastcall CmDeleteKey(const struct RegEntry *a1)
{
  HKEY v2; // rcx
  int v3; // eax

  v2 = (HKEY)qword_14002AF40;
  if ( *((_QWORD *)a1 + 4) )
    v2 = (HKEY)*((_QWORD *)a1 + 4);
  v3 = RegDeleteKeyW(v2, *((LPCWSTR *)a1 + 1));
  if ( (v3 & 0xFFFFFFFD) != 0 )
  {
    if ( v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
    ThrowMissingValue(a1, v3);
  }
}

```

## disassembly

```asm
0x14000ef34  push    rbx
0x14000ef36  sub     rsp, 20h
0x14000ef3a  mov     rbx, rcx
0x14000ef3d  mov     rcx, cs:qword_14002AF40
0x14000ef44  cmp     qword ptr [rbx+20h], 0
0x14000ef49  mov     rdx, [rbx+8]; lpSubKey
0x14000ef4d  cmovnz  rcx, [rbx+20h]; hKey
0x14000ef52  call    cs:__imp_RegDeleteKeyW
0x14000ef58  test    eax, 0FFFFFFFDh
0x14000ef5d  jz      short loc_14000EF75
0x14000ef5f  test    eax, eax
0x14000ef61  jle     short loc_14000EF6B
0x14000ef63  movzx   eax, ax
0x14000ef66  or      eax, 80070000h
0x14000ef6b  mov     edx, eax; int
0x14000ef6d  mov     rcx, rbx; struct RegEntry *
0x14000ef70  call    ?ThrowMissingValue@@YAXAEBVRegEntry@@J@Z; ThrowMissingValue(RegEntry const &,long)
0x14000ef75  add     rsp, 20h
0x14000ef79  pop     rbx
0x14000ef7a  retn
```
