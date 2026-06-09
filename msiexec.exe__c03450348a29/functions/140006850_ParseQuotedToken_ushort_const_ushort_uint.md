# ParseQuotedToken(ushort const * &,ushort * &,uint)

- ea: `0x140006850`
- end: `0x1400069f0`
- name: `?ParseQuotedToken@@YA_NAEAPEBGAEAPEAGI@Z`
- size: `416`
- prototype: `bool __fastcall(const unsigned __int16 **, unsigned __int16 **, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140006a90`

## callees

- `0x140006850`
- `0x1400097f2`

## pseudocode

```c
char __fastcall ParseQuotedToken(const unsigned __int16 **a1, unsigned __int16 **a2, unsigned int a3)
{
  const unsigned __int16 *v5; // rdx
  const unsigned __int16 *i; // rsi
  __int64 v8; // rbp
  char *v9; // rdi
  _WORD *v10; // rax
  __int64 v11; // rbp
  char *v12; // rdi
  _WORD *v13; // rax
  const unsigned __int16 *v14; // rcx
  __int64 v15; // rcx
  char *v16; // rbx
  size_t v17; // rdi

  v5 = *a1;
  if ( **a1 )
    v5 = *a1 + 1;
  *a1 = v5;
  for ( i = v5; *i != 34 && *i; *a1 = i )
  {
    if ( *i == 92 )
    {
      if ( i[1] == 96 )
      {
        v8 = i - v5;
        if ( v8 >= a3 || v8 < 0 )
          return 0;
        if ( (_DWORD)v8 )
        {
          v9 = (char *)*a2;
          memcpy_0(*a2, v5, 2LL * (unsigned int)v8);
          *a2 = (unsigned __int16 *)&v9[2 * (unsigned int)v8];
        }
        v10 = *a2;
        v5 = i + 2;
        *v10 = 96;
        *a2 = v10 + 1;
        a3 += -1 - v8;
        ++i;
      }
    }
    else
    {
      if ( *i != 96 )
      {
        v14 = i;
LABEL_23:
        i = v14 + 1;
        continue;
      }
      v11 = i - v5;
      if ( v11 >= a3 || v11 < 0 )
        return 0;
      if ( (_DWORD)v11 )
      {
        v12 = (char *)*a2;
        memcpy_0(*a2, v5, 2LL * (unsigned int)v11);
        *a2 = (unsigned __int16 *)&v12[2 * (unsigned int)v11];
      }
      v13 = *a2;
      v5 = i + 1;
      *v13 = 34;
      *a2 = v13 + 1;
      a3 += -1 - v11;
    }
    v14 = i;
    if ( *i )
      goto LABEL_23;
  }
  v15 = i - v5;
  if ( v15 >= a3 || v15 < 0 )
    return 0;
  if ( (_DWORD)v15 )
  {
    v16 = (char *)*a2;
    v17 = 2LL * (unsigned int)v15;
    memcpy_0(*a2, v5, v17);
    *a2 = (unsigned __int16 *)&v16[v17];
  }
  **a2 = 0;
  if ( *i == 34 )
    *a1 = i + 1;
  return 1;
}

```

## disassembly

```asm
0x140006850  push    rbx
0x140006852  push    rbp
0x140006853  push    rsi
0x140006854  push    rdi
0x140006855  push    r12
0x140006857  push    r13
0x140006859  push    r14
0x14000685b  push    r15
0x14000685d  sub     rsp, 28h
0x140006861  mov     r14, rdx
0x140006864  mov     r15d, r8d
0x140006867  mov     rdx, [rcx]
0x14000686a  xor     r8d, r8d
0x14000686d  mov     r13, rcx
0x140006870  cmp     r8w, [rdx]
0x140006874  lea     rax, [rdx+2]
0x140006878  lea     r12d, [r8+22h]
0x14000687c  cmovnz  rdx, rax; Src
0x140006880  mov     [rcx], rdx
0x140006883  mov     rsi, rdx
0x140006886  mov     eax, 60h ; '`'
0x14000688b  cmp     [rsi], r12w
0x14000688f  jz      loc_14000698C
0x140006895  cmp     [rsi], r8w
0x140006899  jz      loc_14000698C
0x14000689f  cmp     word ptr [rsi], 5Ch ; '\'
0x1400068a3  jnz     short loc_140006912
0x1400068a5  cmp     [rsi+2], ax
0x1400068a9  jnz     short loc_14000690A
0x1400068ab  mov     rbp, rsi
0x1400068ae  mov     eax, r15d
0x1400068b1  sub     rbp, rdx
0x1400068b4  sar     rbp, 1
0x1400068b7  cmp     rbp, rax
0x1400068ba  jge     loc_1400069DD
0x1400068c0  test    rbp, rbp
0x1400068c3  js      loc_1400069DD
0x1400068c9  test    ebp, ebp
0x1400068cb  jz      short loc_1400068EB
0x1400068cd  mov     rdi, [r14]
0x1400068d0  mov     eax, ebp
0x1400068d2  mov     rcx, rdi; void *
0x1400068d5  lea     rbx, [rax+rax]
0x1400068d9  mov     r8, rbx; Size
0x1400068dc  call    memcpy_0
0x1400068e1  lea     rax, [rbx+rdi]
0x1400068e5  xor     r8d, r8d
0x1400068e8  mov     [r14], rax
0x1400068eb  mov     rax, [r14]
0x1400068ee  lea     rdx, [rsi+4]
0x1400068f2  mov     word ptr [rax], 60h ; '`'
0x1400068f7  add     rax, 2
0x1400068fb  mov     [r14], rax
0x1400068fe  or      eax, 0FFFFFFFFh
0x140006901  sub     eax, ebp
0x140006903  add     r15d, eax
0x140006906  add     rsi, 2
0x14000690a  mov     r12d, 22h ; '"'
0x140006910  jmp     short loc_140006971
0x140006912  cmp     [rsi], ax
0x140006915  jnz     short loc_14000697C
0x140006917  mov     rbp, rsi
0x14000691a  mov     eax, r15d
0x14000691d  sub     rbp, rdx
0x140006920  sar     rbp, 1
0x140006923  cmp     rbp, rax
0x140006926  jge     loc_1400069DD
0x14000692c  test    rbp, rbp
0x14000692f  js      loc_1400069DD
0x140006935  test    ebp, ebp
0x140006937  jz      short loc_140006957
0x140006939  mov     rdi, [r14]
0x14000693c  mov     eax, ebp
0x14000693e  mov     rcx, rdi; void *
0x140006941  lea     rbx, [rax+rax]
0x140006945  mov     r8, rbx; Size
0x140006948  call    memcpy_0
0x14000694d  lea     rax, [rbx+rdi]
0x140006951  xor     r8d, r8d
0x140006954  mov     [r14], rax
0x140006957  mov     rax, [r14]
0x14000695a  lea     rdx, [rsi+2]
0x14000695e  mov     [rax], r12w
0x140006962  add     rax, 2
0x140006966  mov     [r14], rax
0x140006969  or      eax, 0FFFFFFFFh
0x14000696c  sub     eax, ebp
0x14000696e  add     r15d, eax
0x140006971  mov     rcx, rsi
0x140006974  cmp     r8w, [rsi]
0x140006978  jnz     short loc_14000697F
0x14000697a  jmp     short loc_140006983
0x14000697c  mov     rcx, rsi
0x14000697f  lea     rsi, [rcx+2]
0x140006983  mov     [r13+0], rsi
0x140006987  jmp     loc_140006886
0x14000698c  mov     rcx, rsi
0x14000698f  mov     eax, r15d
0x140006992  sub     rcx, rdx
0x140006995  sar     rcx, 1
0x140006998  cmp     rcx, rax
0x14000699b  jge     short loc_1400069DD
0x14000699d  test    rcx, rcx
0x1400069a0  js      short loc_1400069DD
0x1400069a2  test    ecx, ecx
0x1400069a4  jz      short loc_1400069C4
0x1400069a6  mov     rbx, [r14]
0x1400069a9  mov     eax, ecx
0x1400069ab  mov     rcx, rbx; void *
0x1400069ae  lea     rdi, [rax+rax]
0x1400069b2  mov     r8, rdi; Size
0x1400069b5  call    memcpy_0
0x1400069ba  lea     rax, [rdi+rbx]
0x1400069be  xor     r8d, r8d
0x1400069c1  mov     [r14], rax
0x1400069c4  mov     rcx, [r14]
0x1400069c7  mov     [rcx], r8w
0x1400069cb  cmp     [rsi], r12w
0x1400069cf  jnz     short loc_1400069D9
0x1400069d1  lea     rax, [rsi+2]
0x1400069d5  mov     [r13+0], rax
0x1400069d9  mov     al, 1
0x1400069db  jmp     short loc_1400069DF
0x1400069dd  xor     al, al
0x1400069df  add     rsp, 28h
0x1400069e3  pop     r15
0x1400069e5  pop     r14
0x1400069e7  pop     r13
0x1400069e9  pop     r12
0x1400069eb  pop     rdi
0x1400069ec  pop     rsi
0x1400069ed  pop     rbp
0x1400069ee  pop     rbx
0x1400069ef  retn
```
