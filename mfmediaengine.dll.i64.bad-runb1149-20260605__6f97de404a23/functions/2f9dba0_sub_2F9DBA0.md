# sub_2F9DBA0

- ea: `0x2f9dba0`
- end: `0x2f9dba6`
- name: `sub_2F9DBA0`
- size: `6`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall sub_2F9DBA0(__int64 a1, __int64 a2, __int64 a3, _BYTE *a4)
{
  __int64 result; // rax

  *a4 += result;
  return result;
}

```

## disassembly

```asm
0x2f9dba0  add     [rcx], al
0x2f9dba2  cmp     byte ptr [rcx], 0F7h
0x2f9dba5  retn
```
