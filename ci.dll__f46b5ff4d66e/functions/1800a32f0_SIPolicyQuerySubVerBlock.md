# SIPolicyQuerySubVerBlock

- ea: `0x1800a32f0`
- end: `0x1800a3464`
- name: `SIPolicyQuerySubVerBlock`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a2c10`

## callees

- `0x1800a32f0`
- `0x1800a346c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1800a33e6`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a33e6`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800a3415`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800a3415`

## pseudocode

```c
__int64 __fastcall SIPolicyQuerySubVerBlock(unsigned __int16 *a1, WCHAR *a2, _QWORD *a3, _QWORD *a4)
{
  unsigned __int16 *v7; // rbx
  unsigned int v8; // r14d
  unsigned __int16 v9; // cx
  unsigned __int16 *v10; // rsi
  __int64 v11; // rax
  unsigned __int16 v12; // cx
  __int64 v13; // rax
  WCHAR *v15; // r15
  int v16; // ebp
  UNICODE_STRING String1; // [rsp+20h] [rbp-68h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-58h] BYREF

  v7 = a1;
  v8 = -1073741275;
  String1 = 0;
  DestinationString = 0;
  if ( !a1[2] )
  {
    v9 = *a1;
    if ( (unsigned __int16)(v9 - 8) <= 0x7FF8u && (v9 & 1) == 0 )
    {
LABEL_6:
      while ( *a2 == 92 )
        ++a2;
      v10 = (unsigned __int16 *)SIPolicyCheckVerBlock(v7, *v7);
      if ( v10 )
      {
        if ( *a2 )
        {
          v15 = a2;
          do
          {
            if ( *a2 == 92 )
              break;
            ++a2;
          }
          while ( *a2 );
          v16 = (_DWORD)v7 + *v7;
          while ( SIPolicyCheckVerBlock(v10, (unsigned int)(v16 - (_DWORD)v10)) )
          {
            RtlInitUnicodeString(&DestinationString, v10 + 3);
            String1.Buffer = v15;
            String1.Length = (_WORD)a2 - (_WORD)v15;
            String1.MaximumLength = (_WORD)a2 - (_WORD)v15;
            if ( !RtlCompareUnicodeString(&String1, &DestinationString, 1u) )
            {
              v7 = v10;
              goto LABEL_6;
            }
            v10 = (unsigned __int16 *)((char *)v10 + ((*v10 + 3LL) & 0xFFFFFFFFFFFFFFFCuLL));
          }
        }
        else
        {
          *a4 = v7[1];
          v11 = -1;
          do
            ++v11;
          while ( v7[v11 + 3] );
          v12 = v7[1];
          if ( v12 && (v7[2] || v12 >= 2u) )
            v13 = (2 * (_DWORD)v11 + 11) & 0xFFFFFFFC;
          else
            v13 = 2LL * (unsigned int)v11 + 6;
          v8 = 0;
          *a3 = (char *)v7 + v13;
        }
      }
    }
  }
  return v8;
}

```

## disassembly

```asm
0x1800a32f0  push    rbx
0x1800a32f2  push    rbp
0x1800a32f3  push    rsi
0x1800a32f4  push    rdi
0x1800a32f5  push    r12
0x1800a32f7  push    r13
0x1800a32f9  push    r14
0x1800a32fb  push    r15
0x1800a32fd  sub     rsp, 48h
0x1800a3301  xor     ebp, ebp
0x1800a3303  xorps   xmm0, xmm0
0x1800a3306  xorps   xmm1, xmm1
0x1800a3309  mov     r12, r9
0x1800a330c  mov     r13, r8
0x1800a330f  mov     rdi, rdx
0x1800a3312  mov     rbx, rcx
0x1800a3315  mov     r14d, 0C0000225h
0x1800a331b  movups  xmmword ptr [rsp+88h+String1.Length], xmm0
0x1800a3320  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm1
0x1800a3325  cmp     [rcx+4], bp
0x1800a3329  jnz     short loc_1800A33A0
0x1800a332b  movzx   ecx, word ptr [rcx]
0x1800a332e  mov     edx, 7FF8h
0x1800a3333  lea     eax, [rcx-8]
0x1800a3336  cmp     ax, dx
0x1800a3339  ja      short loc_1800A33A0
0x1800a333b  test    cl, 1
0x1800a333e  jnz     short loc_1800A33A0
0x1800a3340  mov     r15d, 2
0x1800a3346  jmp     short loc_1800A334B
0x1800a3348  add     rdi, r15
0x1800a334b  cmp     word ptr [rdi], 5Ch ; '\'
0x1800a334f  jz      short loc_1800A3348
0x1800a3351  movzx   edx, word ptr [rbx]
0x1800a3354  mov     rcx, rbx
0x1800a3357  call    SIPolicyCheckVerBlock
0x1800a335c  mov     rsi, rax
0x1800a335f  test    rax, rax
0x1800a3362  jz      short loc_1800A33A0
0x1800a3364  cmp     [rdi], bp
0x1800a3367  jnz     short loc_1800A33B5
0x1800a3369  movzx   eax, word ptr [rbx+2]
0x1800a336d  mov     [r12], rax
0x1800a3371  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a3375  inc     rax
0x1800a3378  cmp     [rbx+rax*2+6], bp
0x1800a337d  jnz     short loc_1800A3375
0x1800a337f  movzx   ecx, word ptr [rbx+2]
0x1800a3383  test    cx, cx
0x1800a3386  jnz     loc_1800A343F
0x1800a338c  mov     eax, eax
0x1800a338e  lea     rax, ds:6[rax*2]
0x1800a3396  add     rax, rbx
0x1800a3399  mov     r14d, ebp
0x1800a339c  mov     [r13+0], rax
0x1800a33a0  mov     eax, r14d
0x1800a33a3  add     rsp, 48h
0x1800a33a7  pop     r15
0x1800a33a9  pop     r14
0x1800a33ab  pop     r13
0x1800a33ad  pop     r12
0x1800a33af  pop     rdi
0x1800a33b0  pop     rsi
0x1800a33b1  pop     rbp
0x1800a33b2  pop     rbx
0x1800a33b3  retn
0x1800a33b5  mov     r15, rdi
0x1800a33b8  cmp     word ptr [rdi], 5Ch ; '\'
0x1800a33bc  jz      short loc_1800A33C7
0x1800a33be  add     rdi, 2
0x1800a33c2  cmp     [rdi], bp
0x1800a33c5  jnz     short loc_1800A33B8
0x1800a33c7  movzx   ebp, word ptr [rbx]
0x1800a33ca  add     ebp, ebx
0x1800a33cc  mov     edx, ebp
0x1800a33ce  mov     rcx, rsi
0x1800a33d1  sub     edx, esi
0x1800a33d3  call    SIPolicyCheckVerBlock
0x1800a33d8  test    rax, rax
0x1800a33db  jz      short loc_1800A33A0
0x1800a33dd  lea     rdx, [rsi+6]; SourceString
0x1800a33e1  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x1800a33e6  call    cs:__imp_RtlInitUnicodeString
0x1800a33ed  nop     dword ptr [rax+rax+00h]
0x1800a33f2  movzx   eax, di
0x1800a33f5  mov     [rsp+88h+String1.Buffer], r15
0x1800a33fa  sub     ax, r15w
0x1800a33fe  lea     rdx, [rsp+88h+DestinationString]; String2
0x1800a3403  mov     r8b, 1; CaseInSensitive
0x1800a3406  mov     [rsp+88h+String1.Length], ax
0x1800a340b  lea     rcx, [rsp+88h+String1]; String1
0x1800a3410  mov     [rsp+88h+String1.MaximumLength], ax
0x1800a3415  call    cs:__imp_RtlCompareUnicodeString
0x1800a341c  nop     dword ptr [rax+rax+00h]
0x1800a3421  test    eax, eax
0x1800a3423  jz      short loc_1800A3435
0x1800a3425  movzx   eax, word ptr [rsi]
0x1800a3428  add     rax, 3
0x1800a342c  and     rax, 0FFFFFFFFFFFFFFFCh
0x1800a3430  add     rsi, rax
0x1800a3433  jmp     short loc_1800A33CC
0x1800a3435  mov     rbx, rsi
0x1800a3438  xor     ebp, ebp
0x1800a343a  jmp     loc_1800A3340
0x1800a343f  cmp     [rbx+4], bp
0x1800a3443  jz      short loc_1800A3459
0x1800a3445  lea     eax, ds:0Bh[rax*2]
0x1800a344c  mov     ecx, 0FFFFFFFCh
0x1800a3451  and     rax, rcx
0x1800a3454  jmp     loc_1800A3396
0x1800a3459  cmp     cx, r15w
0x1800a345d  jnb     short loc_1800A3445
0x1800a345f  jmp     loc_1800A338C
```
