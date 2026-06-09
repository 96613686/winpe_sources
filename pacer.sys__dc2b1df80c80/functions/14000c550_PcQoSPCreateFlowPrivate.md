# PcQoSPCreateFlowPrivate

- ea: `0x14000c550`
- end: `0x14000c5b6`
- name: `PcQoSPCreateFlowPrivate`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `reparse_path`

## callees

- `0x14000adf8`
- `0x14000c550`
- `0x14000c75c`

## pseudocode

```c
__int64 __fastcall PcQoSPCreateFlowPrivate(void **a1)
{
  ULONG v1; // edx
  unsigned int Flow; // eax

  v1 = *((_DWORD *)*a1 + 16) + 80;
  if ( *((_DWORD *)*a1 + 16) >= 0xFFFFFFB0 )
  {
    Flow = -1073741675;
  }
  else if ( (unsigned __int64)a1[1] >= v1 )
  {
    Flow = PcpCreateFlow(a1[3], 0, 0, 0, v1, 2, *a1, 0, (__int64)a1[2]);
  }
  else
  {
    Flow = -1073741789;
  }
  return PcpNormalizeNtStatus(Flow);
}

```

## disassembly

```asm
0x14000c550  sub     rsp, 58h
0x14000c554  mov     r8, [rcx]
0x14000c557  mov     edx, [r8+40h]
0x14000c55b  add     edx, 50h ; 'P'
0x14000c55e  cmp     edx, 50h ; 'P'
0x14000c561  jb      short loc_14000C5A4
0x14000c563  mov     eax, edx
0x14000c565  cmp     [rcx+8], rax
0x14000c569  jnb     short loc_14000C572
0x14000c56b  mov     eax, 0C0000023h
0x14000c570  jmp     short loc_14000C5A9
0x14000c572  mov     rax, [rcx+10h]
0x14000c576  xor     r9d, r9d
0x14000c579  mov     rcx, [rcx+18h]
0x14000c57d  mov     [rsp+58h+var_18], rax
0x14000c582  mov     [rsp+58h+var_20], 0
0x14000c587  mov     [rsp+58h+var_28], r8
0x14000c58c  xor     r8d, r8d
0x14000c58f  mov     [rsp+58h+var_30], 2
0x14000c597  mov     [rsp+58h+var_38], edx
0x14000c59b  xor     edx, edx
0x14000c59d  call    PcpCreateFlow
0x14000c5a2  jmp     short loc_14000C5A9
0x14000c5a4  mov     eax, 0C0000095h
0x14000c5a9  mov     ecx, eax
0x14000c5ab  call    PcpNormalizeNtStatus
0x14000c5b0  add     rsp, 58h
0x14000c5b4  retn
```
