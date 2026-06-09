# SecCacheQueryFileEa

- ea: `0x1400300d4`
- end: `0x1400302a4`
- name: `SecCacheQueryFileEa`
- size: `464`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1400303b8`

## callees

- `0x140009b80`
- `0x140011650`
- `0x140011700`
- `0x1400119c0`
- `0x1400300d4`
- `0x1400302a4`

## import_xrefs

- `ntoskrnl!RtlInitString` at `0x1400301ae`
- `ntoskrnl!RtlInitString` at `0x1400301ae`
- `ntoskrnl!RtlEqualString` at `0x1400301c5`
- `ntoskrnl!RtlEqualString` at `0x1400301c5`

## pseudocode

```c
__int64 __fastcall SecCacheQueryFileEa(int a1, int a2, int a3, int a4, __int64 a5, unsigned __int64 a6)
{
  unsigned __int64 v6; // rbx
  unsigned int v7; // esi
  int v8; // eax
  unsigned int v9; // ecx
  __int64 v10; // rax
  __int64 v11; // r12
  unsigned int *v12; // rdi
  unsigned int v13; // r13d
  unsigned int v14; // r14d
  unsigned __int16 v15; // ax
  unsigned int v16; // edx
  unsigned int v17; // eax
  __int64 v18; // rbx
  __int64 v19; // rax
  unsigned __int8 v21; // [rsp+50h] [rbp-29h]
  unsigned int v22; // [rsp+54h] [rbp-25h] BYREF
  unsigned int v23; // [rsp+58h] [rbp-21h]
  int FileEaInternal; // [rsp+5Ch] [rbp-1Dh]
  unsigned int *v25; // [rsp+60h] [rbp-19h] BYREF
  PVOID P; // [rsp+68h] [rbp-11h] BYREF
  struct _STRING DestinationString; // [rsp+70h] [rbp-9h] BYREF

  v6 = a6;
  v22 = 0;
  DestinationString = 0;
  v25 = 0;
  P = 0;
  FileEaInternal = SecCacheQueryFileEaInternal(a1, a2, a3, a4, a5, a6, (__int64)&P, (__int64)&v25, (__int64)&v22);
  v7 = FileEaInternal;
  if ( FileEaInternal >= 0 )
  {
    _mm_lfence();
    v9 = 0;
    v23 = 0;
    if ( a6 )
    {
      v10 = 0;
      do
      {
        v11 = 3 * v10;
        v12 = v25;
        v13 = 0;
        *(_DWORD *)(a5 + 24 * v10 + 20) = -1073741275;
        if ( v22 )
        {
          do
          {
            v14 = *v12;
            if ( !*v12 )
              v14 = v22 - v13;
            v21 = *((_BYTE *)v12 + 5);
            RtlInitString(&DestinationString, (PCSZ)v12 + 8);
            if ( RtlEqualString(&DestinationString, *(const STRING **)(a5 + 8 * v11), 1u) )
            {
              v15 = *((_WORD *)v12 + 3);
              v16 = *(unsigned __int16 *)(a5 + 8 * v11 + 16);
              if ( v15 <= (unsigned __int16)v16 )
              {
                if ( v15 )
                  *(_DWORD *)(a5 + 8 * v11 + 20) = 0;
              }
              else
              {
                *(_DWORD *)(a5 + 8 * v11 + 20) = -2147483643;
              }
              v17 = v16;
              if ( (unsigned __int16)v16 >= *((_WORD *)v12 + 3) )
                v17 = *((unsigned __int16 *)v12 + 3);
              v18 = v17;
              memmove(*(void **)(a5 + 8 * v11 + 8), (char *)v12 + v21 + 9, v17);
              memset(
                (void *)(v18 + *(_QWORD *)(a5 + 8 * v11 + 8)),
                0,
                *(unsigned __int16 *)(a5 + 8 * v11 + 16) - (unsigned int)v18);
            }
            v19 = *v12;
            v13 += v14;
            if ( !(_DWORD)v19 )
              break;
            v12 = (unsigned int *)((char *)v12 + v19);
          }
          while ( v22 > v13 );
          v9 = v23;
          v6 = a6;
        }
        v10 = ++v9;
        v23 = v9;
      }
      while ( v9 < v6 );
      v7 = FileEaInternal;
    }
  }
  else
  {
    v8 = 0;
    if ( FileEaInternal != -1073741275 )
      v8 = FileEaInternal;
    v7 = v8;
  }
  if ( P )
    SecFreePool(P, 0x516D6553u);
  return v7;
}

```

## disassembly

```asm
0x1400300d4  mov     [rsp-8+arg_10], rbx
0x1400300d9  push    rbp
0x1400300da  push    rsi
0x1400300db  push    rdi
0x1400300dc  push    r12
0x1400300de  push    r13
0x1400300e0  push    r14
0x1400300e2  push    r15
0x1400300e4  lea     rbp, [rsp-17h]
0x1400300e9  sub     rsp, 90h
0x1400300f0  mov     rax, cs:__security_cookie
0x1400300f7  xor     rax, rsp
0x1400300fa  mov     [rbp+47h+var_40], rax
0x1400300fe  mov     rbx, [rbp+47h+arg_28]
0x140030102  lea     rax, [rbp+47h+var_6C]
0x140030106  mov     r15, [rbp+47h+arg_20]
0x14003010a  xor     edi, edi
0x14003010c  mov     [rsp+0C0h+var_80], rax
0x140030111  xorps   xmm0, xmm0
0x140030114  lea     rax, [rbp+47h+var_60]
0x140030118  mov     [rbp+47h+var_6C], edi
0x14003011b  mov     [rsp+0C0h+var_88], rax
0x140030120  lea     rax, [rbp+47h+P]
0x140030124  mov     [rsp+0C0h+var_90], rax
0x140030129  mov     [rsp+0C0h+var_98], rbx
0x14003012e  mov     [rsp+0C0h+var_A0], r15
0x140030133  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm0
0x140030137  mov     [rbp+47h+var_60], rdi
0x14003013b  mov     [rbp+47h+P], rdi
0x14003013f  call    SecCacheQueryFileEaInternal
0x140030144  mov     [rbp+47h+var_64], eax
0x140030147  mov     esi, eax
0x140030149  test    eax, eax
0x14003014b  jns     short loc_14003015F
0x14003014d  cmp     esi, 0C0000225h
0x140030153  mov     eax, edi
0x140030155  cmovnz  eax, esi
0x140030158  mov     esi, eax
0x14003015a  jmp     loc_140030267
0x14003015f  lfence
0x140030162  mov     ecx, edi
0x140030164  mov     [rbp+47h+var_68], ecx
0x140030167  test    rbx, rbx
0x14003016a  jz      loc_140030267
0x140030170  xor     esi, esi
0x140030172  mov     eax, esi
0x140030174  lea     r12, [rax+rax*2]
0x140030178  mov     rdi, [rbp+47h+var_60]
0x14003017c  mov     r13d, esi
0x14003017f  mov     dword ptr [r15+r12*8+14h], 0C0000225h
0x140030188  cmp     [rbp+47h+var_6C], esi
0x14003018b  jbe     loc_140030254
0x140030191  mov     r14d, [rdi]
0x140030194  test    r14d, r14d
0x140030197  jnz     short loc_1400301A0
0x140030199  mov     r14d, [rbp+47h+var_6C]
0x14003019d  sub     r14d, r13d
0x1400301a0  mov     al, [rdi+5]
0x1400301a3  lea     rdx, [rdi+8]; SourceString
0x1400301a7  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x1400301ab  mov     [rbp+47h+var_70], al
0x1400301ae  call    cs:__imp_RtlInitString
0x1400301b5  nop     dword ptr [rax+rax+00h]
0x1400301ba  mov     rdx, [r15+r12*8]; String2
0x1400301be  lea     rcx, [rbp+47h+DestinationString]; String1
0x1400301c2  mov     r8b, 1; CaseInSensitive
0x1400301c5  call    cs:__imp_RtlEqualString
0x1400301cc  nop     dword ptr [rax+rax+00h]
0x1400301d1  test    al, al
0x1400301d3  jz      short loc_140030237
0x1400301d5  movzx   eax, word ptr [rdi+6]
0x1400301d9  movzx   edx, word ptr [r15+r12*8+10h]
0x1400301df  cmp     ax, dx
0x1400301e2  jbe     short loc_1400301EF
0x1400301e4  mov     dword ptr [r15+r12*8+14h], 80000005h
0x1400301ed  jmp     short loc_1400301F9
0x1400301ef  test    ax, ax
0x1400301f2  jz      short loc_1400301F9
0x1400301f4  mov     [r15+r12*8+14h], esi
0x1400301f9  movzx   ecx, word ptr [rdi+6]
0x1400301fd  mov     eax, edx
0x1400301ff  cmp     dx, cx
0x140030202  movzx   edx, [rbp+47h+var_70]
0x140030206  cmovnb  eax, ecx
0x140030209  mov     rcx, [r15+r12*8+8]; void *
0x14003020e  add     rdx, 9
0x140030212  mov     r8d, eax; Size
0x140030215  add     rdx, rdi; Src
0x140030218  mov     ebx, eax
0x14003021a  call    memmove
0x14003021f  movzx   r8d, word ptr [r15+r12*8+10h]
0x140030225  xor     edx, edx; Val
0x140030227  mov     rcx, [r15+r12*8+8]
0x14003022c  sub     r8d, ebx; Size
0x14003022f  add     rcx, rbx; void *
0x140030232  call    memset
0x140030237  mov     eax, [rdi]
0x140030239  add     r13d, r14d
0x14003023c  test    eax, eax
0x14003023e  jz      short loc_14003024D
0x140030240  add     rdi, rax
0x140030243  cmp     [rbp+47h+var_6C], r13d
0x140030247  ja      loc_140030191
0x14003024d  mov     ecx, [rbp+47h+var_68]
0x140030250  mov     rbx, [rbp+47h+arg_28]
0x140030254  inc     ecx
0x140030256  mov     eax, ecx
0x140030258  mov     [rbp+47h+var_68], ecx
0x14003025b  cmp     rax, rbx
0x14003025e  jb      loc_140030174
0x140030264  mov     esi, [rbp+47h+var_64]
0x140030267  mov     rcx, [rbp+47h+P]; P
0x14003026b  test    rcx, rcx
0x14003026e  jz      short loc_14003027A
0x140030270  mov     edx, 516D6553h; Tag
0x140030275  call    SecFreePool
0x14003027a  mov     eax, esi
0x14003027c  mov     rcx, [rbp+47h+var_40]
0x140030280  xor     rcx, rsp; StackCookie
0x140030283  call    __security_check_cookie
0x140030288  mov     rbx, [rsp+0C0h+arg_10]
0x140030290  add     rsp, 90h
0x140030297  pop     r15
0x140030299  pop     r14
0x14003029b  pop     r13
0x14003029d  pop     r12
0x14003029f  pop     rdi
0x1400302a0  pop     rsi
0x1400302a1  pop     rbp
0x1400302a2  retn
```
