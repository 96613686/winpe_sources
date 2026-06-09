# GetHidclassCollection

- ea: `0x18000c250`
- end: `0x18000c2b1`
- name: `GetHidclassCollection`
- size: `97`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: ``

## callers

- `0x18000621c`
- `0x180006ac8`
- `0x180009b70`
- `0x18000a88c`
- `0x18000ac70`
- `0x18000adc0`
- `0x18000b140`
- `0x18000deb0`
- `0x180018880`
- `0x18003ff7c`
- `0x1800405e4`
- `0x180041d94`
- `0x180042f24`

## callees

- `0x18000c250`
- `0x180021ac0`

## import_xrefs

- `ntoskrnl!MmBadPointer` at `0x18000c267`

## pseudocode

```c
char *__fastcall GetHidclassCollection(__int64 a1, __int64 a2)
{
  char *v2; // r8
  char *v3; // rbx
  unsigned int v5; // r9d
  unsigned int i; // eax
  char *v7; // rcx

  v2 = *(char **)(a1 + 152);
  v3 = 0;
  if ( v2 && v2 != MmBadPointer )
  {
    v5 = *(_DWORD *)(a1 + 168);
    for ( i = 0; i < v5; ++i )
    {
      v7 = &v2[424 * i];
      if ( *(_DWORD *)v7 == (_DWORD)a2 )
      {
        v3 = &v2[424 * i];
        if ( !v7 )
          break;
        return v3;
      }
    }
  }
  TraceLoggingGetClassCollectionFailed(a1, a2);
  return v3;
}

```

## disassembly

```asm
0x18000c250  push    rbx
0x18000c252  sub     rsp, 20h
0x18000c256  mov     r8, [rcx+98h]
0x18000c25d  xor     ebx, ebx
0x18000c25f  mov     r11, rcx
0x18000c262  test    r8, r8
0x18000c265  jz      short loc_18000C2A7
0x18000c267  mov     rax, cs:MmBadPointer
0x18000c26e  cmp     r8, [rax]
0x18000c271  jz      short loc_18000C2A7
0x18000c273  mov     r9d, [rcx+0A8h]
0x18000c27a  xor     eax, eax
0x18000c27c  cmp     eax, r9d
0x18000c27f  jnb     short loc_18000C2A7
0x18000c281  mov     ecx, eax
0x18000c283  imul    rcx, 1A8h
0x18000c28a  add     rcx, r8
0x18000c28d  cmp     [rcx], edx
0x18000c28f  jnz     short loc_18000C2A3
0x18000c291  mov     rbx, rcx
0x18000c294  test    rcx, rcx
0x18000c297  jz      short loc_18000C2A7
0x18000c299  mov     rax, rbx
0x18000c29c  add     rsp, 20h
0x18000c2a0  pop     rbx
0x18000c2a1  retn
0x18000c2a3  inc     eax
0x18000c2a5  jmp     short loc_18000C27C
0x18000c2a7  mov     rcx, r11
0x18000c2aa  call    TraceLoggingGetClassCollectionFailed
0x18000c2af  jmp     short loc_18000C299
```
