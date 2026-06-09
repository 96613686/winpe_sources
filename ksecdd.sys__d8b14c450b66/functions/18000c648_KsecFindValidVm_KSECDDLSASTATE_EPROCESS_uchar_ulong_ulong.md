# KsecFindValidVm(_KSECDDLSASTATE *,_EPROCESS *,uchar *,ulong,ulong)

- ea: `0x18000c648`
- end: `0x18000c6ca`
- name: `?KsecFindValidVm@@YAKPEAU_KSECDDLSASTATE@@PEAU_EPROCESS@@PEAEKK@Z`
- size: `130`
- prototype: `unsigned int __fastcall(struct _KSECDDLSASTATE *, struct _EPROCESS *, unsigned __int8 *, unsigned int, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180004e7c`
- `0x180005b58`
- `0x18000c7a0`

## callees

- `0x18000c648`

## pseudocode

```c
__int64 __fastcall KsecFindValidVm(
        struct _KSECDDLSASTATE *a1,
        struct _EPROCESS *a2,
        unsigned __int8 *a3,
        int a4,
        unsigned int a5)
{
  unsigned __int8 *v6; // rdi
  __int64 result; // rax
  unsigned int v9; // r10d
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // rcx

  v6 = &a3[a4];
  if ( v6 < a3 )
    return 0xFFFFFFFFLL;
  result = a5;
  v9 = *((_DWORD *)a1 + 144);
  if ( a5 < v9 )
  {
    v10 = *((_QWORD *)a1 + 73);
    if ( a2 == *(struct _EPROCESS **)(v10 + 40LL * a5 + 8)
      && (unsigned __int64)a3 >= *(_QWORD *)(v10 + 40LL * a5 + 16)
      && (unsigned __int64)v6 <= *(_QWORD *)(v10 + 40LL * a5 + 24) )
    {
      return result;
    }
  }
  if ( !v9 )
    return 0xFFFFFFFFLL;
  v11 = *((_QWORD *)a1 + 73);
  v12 = 0;
  while ( a2 != *(struct _EPROCESS **)(v11 + 40 * v12 + 8)
       || (unsigned __int64)a3 < *(_QWORD *)(v11 + 40 * v12 + 16)
       || (unsigned __int64)v6 > *(_QWORD *)(v11 + 40 * v12 + 24) )
  {
    v12 = (unsigned int)(v12 + 1);
    if ( (unsigned int)v12 >= v9 )
      return 0xFFFFFFFFLL;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18000c648  push    rbx
0x18000c64a  push    rsi
0x18000c64b  push    rdi
0x18000c64c  mov     edi, r9d
0x18000c64f  mov     rbx, r8
0x18000c652  add     rdi, r8
0x18000c655  mov     rsi, rdx
0x18000c658  mov     r11, rcx
0x18000c65b  cmp     rdi, r8
0x18000c65e  jb      short loc_18000C6BE
0x18000c660  mov     eax, [rsp+18h+arg_20]
0x18000c664  mov     r10d, [rcx+240h]
0x18000c66b  cmp     eax, r10d
0x18000c66e  jnb     short loc_18000C690
0x18000c670  mov     rdx, [rcx+248h]
0x18000c677  lea     r8, [rax+rax*4]
0x18000c67b  cmp     rsi, [rdx+r8*8+8]
0x18000c680  jnz     short loc_18000C690
0x18000c682  cmp     rbx, [rdx+r8*8+10h]
0x18000c687  jb      short loc_18000C690
0x18000c689  cmp     rdi, [rdx+r8*8+18h]
0x18000c68e  jbe     short loc_18000C6C1
0x18000c690  test    r10d, r10d
0x18000c693  jz      short loc_18000C6BE
0x18000c695  mov     r8, [r11+248h]
0x18000c69c  xor     ecx, ecx
0x18000c69e  lea     rdx, [rcx+rcx*4]
0x18000c6a2  cmp     rsi, [r8+rdx*8+8]
0x18000c6a7  jnz     short loc_18000C6B7
0x18000c6a9  cmp     rbx, [r8+rdx*8+10h]
0x18000c6ae  jb      short loc_18000C6B7
0x18000c6b0  cmp     rdi, [r8+rdx*8+18h]
0x18000c6b5  jbe     short loc_18000C6C6
0x18000c6b7  inc     ecx
0x18000c6b9  cmp     ecx, r10d
0x18000c6bc  jb      short loc_18000C69E
0x18000c6be  or      eax, 0FFFFFFFFh
0x18000c6c1  pop     rdi
0x18000c6c2  pop     rsi
0x18000c6c3  pop     rbx
0x18000c6c4  retn
0x18000c6c6  mov     eax, ecx
0x18000c6c8  jmp     short loc_18000C6C1
```
