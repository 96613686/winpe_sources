# CmDeleteKey(RegEntry const &)

- ea: `0x180015068`
- end: `0x1800150af`
- name: `?CmDeleteKey@@YAXAEBVRegEntry@@@Z`
- size: `71`
- prototype: `void __fastcall(const struct RegEntry *)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180016b50`
- `0x180019b4c`
- `0x180019dc0`
- `0x180020ebc`
- `0x18002153a`

## callees

- `0x180015068`
- `0x180015748`

## import_xrefs

- `ADVAPI32!RegDeleteKeyW` at `0x180015086`
- `ADVAPI32!RegDeleteKeyW` at `0x180015086`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CmDeleteKey(const struct RegEntry *a1)
{
  HKEY v2; // rcx
  int v3; // eax

  v2 = (HKEY)qword_18002D0F0;
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
0x180015068  push    rbx
0x18001506a  sub     rsp, 20h
0x18001506e  mov     rbx, rcx
0x180015071  mov     rcx, cs:qword_18002D0F0
0x180015078  cmp     qword ptr [rbx+20h], 0
0x18001507d  mov     rdx, [rbx+8]; lpSubKey
0x180015081  cmovnz  rcx, [rbx+20h]; hKey
0x180015086  call    cs:__imp_RegDeleteKeyW
0x18001508c  test    eax, 0FFFFFFFDh
0x180015091  jz      short loc_1800150A9
0x180015093  test    eax, eax
0x180015095  jle     short loc_18001509F
0x180015097  movzx   eax, ax
0x18001509a  or      eax, 80070000h
0x18001509f  mov     edx, eax; int
0x1800150a1  mov     rcx, rbx; struct RegEntry *
0x1800150a4  call    ?ThrowMissingValue@@YAXAEBVRegEntry@@J@Z; ThrowMissingValue(RegEntry const &,long)
0x1800150a9  add     rsp, 20h
0x1800150ad  pop     rbx
0x1800150ae  retn
```
