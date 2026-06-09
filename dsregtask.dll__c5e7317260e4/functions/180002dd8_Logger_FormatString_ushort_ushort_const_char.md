# Logger::FormatString(ushort * &,ushort const *,char *)

- ea: `0x180002dd8`
- end: `0x180002f20`
- name: `?FormatString@Logger@@CAJAEAPEAGPEBGPEAD@Z`
- size: `328`
- prototype: `__int64 __fastcall(unsigned __int16 **, const unsigned __int16 *, va_list)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180002f28`

## callees

- `0x180001da4`
- `0x180002dd8`
- `0x180003574`
- `0x1800035a0`

## pseudocode

```c
__int64 __fastcall Logger::FormatString(unsigned __int16 **a1, const unsigned __int16 *a2, va_list a3)
{
  unsigned int v6; // edx
  const unsigned __int16 *v7; // rax
  __int64 v8; // r8
  unsigned __int64 v9; // rbx
  unsigned __int16 *v10; // rax
  unsigned __int16 *v11; // rdi
  unsigned __int64 v12; // rsi
  int v13; // eax
  unsigned __int64 v14; // kr00_8

  if ( !a2 )
    return (unsigned int)-2147024809;
  v7 = a2;
  v8 = 0x7FFFFFFF;
  do
  {
    if ( !*v7 )
      break;
    ++v7;
    --v8;
  }
  while ( v8 );
  v6 = v8 == 0 ? 0x80070057 : 0;
  if ( v8 )
  {
    v9 = ((0x7FFFFFFF - v8) & -(__int64)(v8 != 0)) + 50;
    while ( 1 )
    {
      v10 = (unsigned __int16 *)SafeAlloc(2 * v9);
      *a1 = v10;
      v11 = v10;
      if ( !v10 )
        return (unsigned int)-2147024882;
      if ( v9 > 0x7FFFFFFF )
      {
        *v10 = 0;
        return (unsigned int)-2147024809;
      }
      if ( v9 )
      {
        v12 = v9 - 1;
        v13 = vsnwprintf(v10, v9 - 1, a2, a3);
        if ( v13 < 0 || v13 > v12 )
        {
          v6 = -2147024774;
LABEL_17:
          v11[v12] = 0;
          goto LABEL_18;
        }
        v6 = 0;
        if ( v13 == v12 )
          goto LABEL_17;
      }
      else
      {
        v6 = *a2 != 0 ? 0x8007007A : 0;
      }
LABEL_18:
      if ( v6 != -2147024774 )
        return v6;
      SafeFree(*a1);
      *a1 = 0;
      if ( v9 < 0x3FFFFFFF )
      {
        v14 = v9;
        v9 *= 2LL;
        if ( !is_mul_ok(v14, 2u) )
          return (unsigned int)-2147024362;
      }
      else
      {
        if ( v9 == 0x7FFFFFFF )
          return (unsigned int)-2147024882;
        v9 = 0x7FFFFFFF;
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x180002dd8  push    rbx
0x180002dda  push    rbp
0x180002ddb  push    rsi
0x180002ddc  push    rdi
0x180002ddd  push    r12
0x180002ddf  push    r13
0x180002de1  push    r14
0x180002de3  push    r15
0x180002de5  sub     rsp, 28h
0x180002de9  xor     r12d, r12d
0x180002dec  mov     rbp, r8
0x180002def  mov     r14, rdx
0x180002df2  mov     r15, rcx
0x180002df5  test    rdx, rdx
0x180002df8  jnz     short loc_180002E04
0x180002dfa  mov     edx, 80070057h
0x180002dff  jmp     loc_180002F0D
0x180002e04  mov     r13d, 7FFFFFFFh
0x180002e0a  mov     rax, r14
0x180002e0d  mov     r8d, r13d
0x180002e10  cmp     [rax], r12w
0x180002e14  jz      short loc_180002E20
0x180002e16  add     rax, 2
0x180002e1a  sub     r8, 1
0x180002e1e  jnz     short loc_180002E10
0x180002e20  mov     rax, r8
0x180002e23  mov     rcx, r13
0x180002e26  neg     rax
0x180002e29  mov     rax, r8
0x180002e2c  sbb     edx, edx
0x180002e2e  sub     rcx, r8
0x180002e31  not     edx
0x180002e33  and     edx, 80070057h
0x180002e39  neg     rax
0x180002e3c  sbb     rbx, rbx
0x180002e3f  and     rbx, rcx
0x180002e42  test    r8, r8
0x180002e45  jz      loc_180002F0D
0x180002e4b  add     rbx, 32h ; '2'
0x180002e4f  lea     rcx, [rbx+rbx]; unsigned __int64
0x180002e53  call    ?SafeAlloc@@YAPEAX_K@Z; SafeAlloc(unsigned __int64)
0x180002e58  mov     [r15], rax
0x180002e5b  mov     rdi, rax
0x180002e5e  test    rax, rax
0x180002e61  jz      loc_180002F08
0x180002e67  cmp     rbx, r13
0x180002e6a  ja      loc_180002EFF
0x180002e70  test    rbx, rbx
0x180002e73  jnz     short loc_180002E86
0x180002e75  movzx   eax, word ptr [r14]
0x180002e79  neg     ax
0x180002e7c  sbb     edx, edx
0x180002e7e  and     edx, 8007007Ah
0x180002e84  jmp     short loc_180002EB7
0x180002e86  lea     rsi, [rbx-1]
0x180002e8a  mov     r9, rbp; Args
0x180002e8d  mov     rdx, rsi; BufferCount
0x180002e90  mov     r8, r14; Format
0x180002e93  mov     rcx, rdi; Buffer
0x180002e96  call    _vsnwprintf
0x180002e9b  test    eax, eax
0x180002e9d  js      short loc_180002EAD
0x180002e9f  cdqe
0x180002ea1  cmp     rax, rsi
0x180002ea4  ja      short loc_180002EAD
0x180002ea6  mov     edx, r12d
0x180002ea9  jnz     short loc_180002EB7
0x180002eab  jmp     short loc_180002EB2
0x180002ead  mov     edx, 8007007Ah
0x180002eb2  mov     [rdi+rsi*2], r12w
0x180002eb7  test    edx, edx
0x180002eb9  jns     short loc_180002F0D
0x180002ebb  cmp     edx, 8007007Ah
0x180002ec1  jnz     short loc_180002F0D
0x180002ec3  mov     rcx, [r15]; void *
0x180002ec6  call    ?SafeFree@@YAHPEAX@Z; SafeFree(void *)
0x180002ecb  mov     [r15], r12
0x180002ece  cmp     rbx, 3FFFFFFFh
0x180002ed5  jb      short loc_180002EE4
0x180002ed7  cmp     rbx, r13
0x180002eda  jz      short loc_180002F08
0x180002edc  mov     rbx, r13
0x180002edf  jmp     loc_180002E4F
0x180002ee4  mov     eax, 2
0x180002ee9  mul     rbx
0x180002eec  mov     rbx, rax
0x180002eef  test    rdx, rdx
0x180002ef2  jz      loc_180002E4F
0x180002ef8  mov     edx, 80070216h
0x180002efd  jmp     short loc_180002F0D
0x180002eff  mov     [rax], r12w
0x180002f03  jmp     loc_180002DFA
0x180002f08  mov     edx, 8007000Eh
0x180002f0d  mov     eax, edx
0x180002f0f  add     rsp, 28h
0x180002f13  pop     r15
0x180002f15  pop     r14
0x180002f17  pop     r13
0x180002f19  pop     r12
0x180002f1b  pop     rdi
0x180002f1c  pop     rsi
0x180002f1d  pop     rbp
0x180002f1e  pop     rbx
0x180002f1f  retn
```
