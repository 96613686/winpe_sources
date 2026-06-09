# PmTableGuidCompareRoutine(_RTL_AVL_TABLE *,void *,void *)

- ea: `0x140025760`
- end: `0x140025793`
- name: `?PmTableGuidCompareRoutine@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z`
- size: `51`
- prototype: `RTL_AVL_COMPARE_ROUTINE`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140011020`
- `0x140025760`

## pseudocode

```c
__int64 __fastcall PmTableGuidCompareRoutine(struct _RTL_AVL_TABLE *Table, char *FirstStruct, char *SecondStruct)
{
  int v3; // ecx

  v3 = memcmp(FirstStruct + 24, SecondStruct + 24, 0x10u);
  if ( v3 >= 0 )
    return (unsigned int)(v3 <= 0) + 1;
  else
    return 0;
}

```

## disassembly

```asm
0x140025760  sub     rsp, 28h
0x140025764  mov     rcx, rdx
0x140025767  lea     rdx, [r8+18h]; Buf2
0x14002576b  add     rcx, 18h; Buf1
0x14002576f  mov     r8d, 10h; Size
0x140025775  call    memcmp
0x14002577a  mov     ecx, eax
0x14002577c  test    eax, eax
0x14002577e  jns     short loc_140025784
0x140025780  xor     eax, eax
0x140025782  jmp     short loc_14002578D
0x140025784  xor     eax, eax
0x140025786  test    ecx, ecx
0x140025788  setle   al
0x14002578b  inc     eax
0x14002578d  add     rsp, 28h
0x140025791  retn
```
