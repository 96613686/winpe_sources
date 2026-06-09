# PiiFilterpAddItemSorted(_PII_FILTER *,ushort const *,ushort const *)

- ea: `0x18000ad40`
- end: `0x18000adf2`
- name: `?PiiFilterpAddItemSorted@@YAJPEAU_PII_FILTER@@PEBG1@Z`
- size: `178`
- prototype: `__int64 __fastcall(struct _PII_FILTER *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180003560`
- `0x18000adf8`

## callees

- `0x180007010`
- `0x18000aa1c`
- `0x18000ad40`

## pseudocode

```c
__int64 __fastcall PiiFilterpAddItemSorted(
        struct _PII_FILTER *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  unsigned __int64 v3; // r11
  const unsigned __int16 *v5; // rbx
  struct _PII_FILTER *v6; // r10
  unsigned __int64 v7; // rcx
  unsigned int i; // r9d
  __int64 *v9; // rax
  unsigned __int64 v10; // rcx
  __int64 v11; // rcx
  unsigned __int64 v12; // rax
  unsigned __int64 v14; // [rsp+40h] [rbp+8h] BYREF

  v3 = -1;
  v5 = a2;
  v6 = this;
  do
    ++v3;
  while ( a2[v3] );
  v7 = *((_QWORD *)this + 2);
  for ( i = 0; i < v7; ++i )
  {
    a2 = (const unsigned __int16 *)i;
    v9 = 0;
    if ( i < v7 )
    {
      v10 = *((_QWORD *)v6 + 1);
      v14 = 0;
      if ( (int)ULongLongMult(v10, i, &v14) < 0
        || (v9 = (__int64 *)(*((_QWORD *)v6 + 5) + v14), (unsigned __int64)v9 < *((_QWORD *)v6 + 5)) )
      {
        v9 = 0;
      }
    }
    v11 = *v9;
    v12 = -1;
    do
      ++v12;
    while ( *(_WORD *)(v11 + 2 * v12) );
    if ( v3 > v12 )
      break;
    v7 = *((_QWORD *)v6 + 2);
  }
  return RtlNameValueArray::Insert(v6, a2, v5, a3, i);
}

```

## disassembly

```asm
0x18000ad40  mov     [rsp+arg_8], rbx
0x18000ad45  mov     [rsp+arg_10], rsi
0x18000ad4a  push    rdi
0x18000ad4b  sub     rsp, 30h
0x18000ad4f  or      r11, 0FFFFFFFFFFFFFFFFh
0x18000ad53  mov     rdi, r8
0x18000ad56  xor     esi, esi
0x18000ad58  mov     rbx, rdx
0x18000ad5b  mov     r10, rcx
0x18000ad5e  inc     r11
0x18000ad61  cmp     [rdx+r11*2], si
0x18000ad66  jnz     short loc_18000AD5E
0x18000ad68  mov     rcx, [rcx+10h]
0x18000ad6c  mov     r9d, esi
0x18000ad6f  test    rcx, rcx
0x18000ad72  jz      short loc_18000ADCC
0x18000ad74  mov     edx, r9d; unsigned __int64
0x18000ad77  mov     rax, rsi
0x18000ad7a  cmp     rdx, rcx
0x18000ad7d  jnb     short loc_18000ADA8
0x18000ad7f  mov     rcx, [r10+8]; unsigned __int64
0x18000ad83  lea     r8, [rsp+38h+arg_0]; unsigned __int64 *
0x18000ad88  mov     [rsp+38h+arg_0], rsi
0x18000ad8d  call    ?ULongLongMult@@YAJ_K0PEA_K@Z; ULongLongMult(unsigned __int64,unsigned __int64,unsigned __int64 *)
0x18000ad92  test    eax, eax
0x18000ad94  js      short loc_18000ADA5
0x18000ad96  mov     rax, [rsp+38h+arg_0]
0x18000ad9b  add     rax, [r10+28h]
0x18000ad9f  cmp     rax, [r10+28h]
0x18000ada3  jnb     short loc_18000ADA8
0x18000ada5  mov     rax, rsi
0x18000ada8  mov     rcx, [rax]
0x18000adab  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000adaf  inc     rax
0x18000adb2  cmp     [rcx+rax*2], si
0x18000adb6  jnz     short loc_18000ADAF
0x18000adb8  cmp     r11, rax
0x18000adbb  ja      short loc_18000ADCC
0x18000adbd  mov     rcx, [r10+10h]
0x18000adc1  inc     r9d
0x18000adc4  mov     eax, r9d
0x18000adc7  cmp     rax, rcx
0x18000adca  jb      short loc_18000AD74
0x18000adcc  mov     eax, r9d
0x18000adcf  mov     r8, rbx; unsigned __int16 *
0x18000add2  mov     r9, rdi; unsigned __int16 *
0x18000add5  mov     [rsp+38h+var_18], rax; unsigned __int64
0x18000adda  mov     rcx, r10; this
0x18000addd  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x18000ade2  mov     rbx, [rsp+38h+arg_8]
0x18000ade7  mov     rsi, [rsp+38h+arg_10]
0x18000adec  add     rsp, 30h
0x18000adf0  pop     rdi
0x18000adf1  retn
```
