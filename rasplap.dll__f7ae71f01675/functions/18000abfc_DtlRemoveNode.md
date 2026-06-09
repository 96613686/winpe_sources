# DtlRemoveNode

- ea: `0x18000abfc`
- end: `0x18000ac37`
- name: `DtlRemoveNode`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000aba4`

## callees

- `0x18000abfc`

## pseudocode

```c
_QWORD *__fastcall DtlRemoveNode(__int64 a1, _QWORD *a2)
{
  __int64 v2; // rax
  _QWORD *v3; // r8
  __int64 v4; // rax

  if ( a1 && a2 )
  {
    v2 = a2[1];
    if ( *a2 )
      *(_QWORD *)(*a2 + 8LL) = v2;
    else
      *(_QWORD *)a1 = v2;
    v3 = (_QWORD *)a2[1];
    v4 = *a2;
    if ( v3 )
      *v3 = v4;
    else
      *(_QWORD *)(a1 + 8) = v4;
    --*(_DWORD *)(a1 + 16);
  }
  return a2;
}

```

## disassembly

```asm
0x18000abfc  test    rcx, rcx
0x18000abff  jz      short loc_18000AC33
0x18000ac01  test    rdx, rdx
0x18000ac04  jz      short loc_18000AC33
0x18000ac06  mov     r8, [rdx]
0x18000ac09  mov     rax, [rdx+8]
0x18000ac0d  test    r8, r8
0x18000ac10  jz      short loc_18000AC18
0x18000ac12  mov     [r8+8], rax
0x18000ac16  jmp     short loc_18000AC1B
0x18000ac18  mov     [rcx], rax
0x18000ac1b  mov     r8, [rdx+8]
0x18000ac1f  mov     rax, [rdx]
0x18000ac22  test    r8, r8
0x18000ac25  jz      short loc_18000AC2C
0x18000ac27  mov     [r8], rax
0x18000ac2a  jmp     short loc_18000AC30
0x18000ac2c  mov     [rcx+8], rax
0x18000ac30  dec     dword ptr [rcx+10h]
0x18000ac33  mov     rax, rdx
0x18000ac36  retn
```
