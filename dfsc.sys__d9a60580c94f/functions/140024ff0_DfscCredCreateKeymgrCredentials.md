# DfscCredCreateKeymgrCredentials

- ea: `0x140024ff0`
- end: `0x1400252a5`
- name: `DfscCredCreateKeymgrCredentials`
- size: `693`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x140012158`
- `0x140029160`

## callees

- `0x140006080`
- `0x140006380`
- `0x140022620`
- `0x140024ff0`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1400251cb`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400251cb`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140025027`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x14002503a`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x140025027`
- `ntoskrnl!RtlInitUnicodeStringEx` at `0x14002503a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400251ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002520e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400251ed`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002520e`
- `ntoskrnl!ExAllocatePool2` at `0x14002509d`
- `ntoskrnl!ExAllocatePool2` at `0x140025119`
- `ntoskrnl!ExAllocatePool2` at `0x14002509d`
- `ntoskrnl!ExAllocatePool2` at `0x140025119`

## pseudocode

```c
__int64 __fastcall DfscCredCreateKeymgrCredentials(unsigned __int16 *a1, __int64 a2, _QWORD *a3)
{
  size_t v6; // rdi
  unsigned __int16 v7; // bx
  unsigned __int64 v8; // r12
  WCHAR *Pool2; // rax
  WCHAR *v10; // rsi
  unsigned int v11; // esi
  unsigned int v12; // ebx
  char *v13; // rax
  char *v14; // rdi
  struct _UNICODE_STRING v15; // xmm0
  unsigned int Length; // eax
  _WORD *v18; // rdx
  _WORD *v19; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-78h] BYREF
  struct _UNICODE_STRING v21; // [rsp+30h] [rbp-68h]
  struct _UNICODE_STRING v22; // [rsp+40h] [rbp-58h] BYREF

  *a3 = 0;
  DestinationString = 0;
  v22 = 0;
  RtlInitUnicodeStringEx(&DestinationString, 0);
  RtlInitUnicodeStringEx(&v22, 0);
  v6 = *a1;
  v21 = 0;
  if ( (_WORD)v6 )
  {
    v7 = v6;
    v21.MaximumLength = v6;
    v21.Length = v6;
    v8 = (unsigned __int64)(unsigned int)v6 >> 1;
    if ( *(_WORD *)(*((_QWORD *)a1 + 1) + v8 * 2 - 2) )
    {
      v7 = v6 + 2;
      v21.MaximumLength = v6 + 2;
      if ( (unsigned __int16)(v6 + 2) < (unsigned __int16)v6 )
      {
        v11 = -1073741670;
        goto LABEL_17;
      }
    }
    Pool2 = (WCHAR *)ExAllocatePool2(258, v7, 2017683012);
    v21.Buffer = Pool2;
    v10 = Pool2;
    if ( !Pool2 )
    {
      v11 = -1073741670;
      goto LABEL_17;
    }
    memmove(Pool2, *((const void **)a1 + 1), v6);
    if ( (unsigned __int16)v6 < v7 )
      v10[v8] = 0;
    DestinationString = v21;
  }
  else
  {
    RtlInitUnicodeString(&DestinationString, 0);
  }
  v11 = 0;
  if ( !a2
    || (v18 = (_WORD *)(a2 + 56), a2 == -56)
    || !*v18
    || (v19 = *(_WORD **)(a2 + 64)) == 0
    || !*v19
    || (v11 = DfscCreateNameFromUnicodeString(&v22, v18, 2017683012)) == 0 )
  {
    v12 = (DestinationString.Length + 23) & 0xFFFFFFFC;
    if ( v12 > 0xFFFF )
    {
      v11 = -1073741811;
    }
    else
    {
      v13 = (char *)ExAllocatePool2(66, v12 + 88, 2017683012);
      v14 = v13;
      if ( v13 )
      {
        memset(v13, 0, v12 + 88);
        *(_WORD *)v14 = -32508;
        *((_WORD *)v14 + 1) = v12 + 88;
        *((_DWORD *)v14 + 1) = 1;
        v15 = DestinationString;
        *((_QWORD *)v14 + 3) = 0;
        *(struct _UNICODE_STRING *)(v14 + 8) = v15;
        qmemcpy(v14 + 88, "Principal", 9);
        v14[85] = 11;
        Length = DestinationString.Length;
        *((_WORD *)v14 + 43) = DestinationString.Length;
        memmove(v14 + 100, DestinationString.Buffer, Length);
        *((_DWORD *)v14 + 20) = 0;
        *((_DWORD *)v14 + 18) = v12;
        if ( a2 )
        {
          *((_DWORD *)v14 + 10) = *(_DWORD *)(a2 + 40);
          *((_DWORD *)v14 + 11) = *(_DWORD *)(a2 + 44);
          *((_DWORD *)v14 + 13) = *(_DWORD *)(a2 + 52);
          *((_DWORD *)v14 + 12) = *(_DWORD *)(a2 + 48);
        }
        *(struct _UNICODE_STRING *)(v14 + 56) = v22;
        *a3 = v14;
        return v11;
      }
      v11 = -1073741670;
    }
  }
LABEL_17:
  if ( DestinationString.Buffer )
  {
    ExFreePoolWithTag(DestinationString.Buffer, 0);
    DestinationString.Buffer = 0;
  }
  if ( v22.Buffer )
    ExFreePoolWithTag(v22.Buffer, 0);
  return v11;
}

```

## disassembly

```asm
0x140024ff0  push    rbx
0x140024ff2  push    rbp
0x140024ff3  push    rsi
0x140024ff4  push    rdi
0x140024ff5  push    r12
0x140024ff7  push    r13
0x140024ff9  push    r14
0x140024ffb  push    r15
0x140024ffd  sub     rsp, 58h
0x140025001  mov     r13, rdx
0x140025004  mov     r14, rcx
0x140025007  xorps   xmm0, xmm0
0x14002500a  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x14002500f  xorps   xmm1, xmm1
0x140025012  xor     r12d, r12d
0x140025015  xor     edx, edx; SourceString
0x140025017  mov     [r8], r12
0x14002501a  movups  xmmword ptr [rsp+98h+DestinationString.Length], xmm0
0x14002501f  mov     r15, r8
0x140025022  movups  xmmword ptr [rsp+98h+var_58.Length], xmm1
0x140025027  call    cs:__imp_RtlInitUnicodeStringEx
0x14002502e  nop     dword ptr [rax+rax+00h]
0x140025033  xor     edx, edx; SourceString
0x140025035  lea     rcx, [rsp+98h+var_58]; DestinationString
0x14002503a  call    cs:__imp_RtlInitUnicodeStringEx
0x140025041  nop     dword ptr [rax+rax+00h]
0x140025046  movzx   edi, word ptr [r14]
0x14002504a  xorps   xmm0, xmm0
0x14002504d  movups  [rsp+98h+var_68], xmm0
0x140025052  test    di, di
0x140025055  jz      loc_1400251C4
0x14002505b  movzx   ebx, di
0x14002505e  mov     eax, edi
0x140025060  shr     rax, 1
0x140025063  mov     word ptr [rsp+98h+var_68+2], bx
0x140025068  mov     word ptr [rsp+98h+var_68], bx
0x14002506d  lea     r12, [rax+rax]
0x140025071  mov     rax, [r14+8]
0x140025075  cmp     word ptr [rax+r12-2], 0
0x14002507c  jz      short loc_14002508F
0x14002507e  lea     ebx, [rdi+2]
0x140025081  mov     word ptr [rsp+98h+var_68+2], bx
0x140025086  cmp     bx, di
0x140025089  jb      loc_14002521C
0x14002508f  movzx   edx, bx
0x140025092  mov     ecx, 102h
0x140025097  mov     r8d, 78436644h
0x14002509d  call    cs:__imp_ExAllocatePool2
0x1400250a4  nop     dword ptr [rax+rax+00h]
0x1400250a9  mov     qword ptr [rsp+98h+var_68+8], rax
0x1400250ae  mov     rsi, rax
0x1400250b1  test    rax, rax
0x1400250b4  jz      loc_1400251DC
0x1400250ba  mov     rdx, [r14+8]; Src
0x1400250be  mov     r8, rdi; Size
0x1400250c1  mov     rcx, rax; void *
0x1400250c4  call    memmove
0x1400250c9  cmp     di, bx
0x1400250cc  jnb     short loc_1400250D5
0x1400250ce  xor     eax, eax
0x1400250d0  mov     [r12+rsi], ax
0x1400250d5  movaps  xmm0, [rsp+98h+var_68]
0x1400250da  xor     r12d, r12d
0x1400250dd  movdqa  xmmword ptr [rsp+98h+DestinationString.Length], xmm0
0x1400250e3  mov     esi, r12d
0x1400250e6  test    r13, r13
0x1400250e9  jnz     loc_140025223
0x1400250ef  movzx   ebx, [rsp+98h+DestinationString.Length]
0x1400250f4  add     ebx, 17h
0x1400250f7  and     ebx, 0FFFFFFFCh
0x1400250fa  cmp     ebx, 0FFFFh
0x140025100  ja      loc_140025270
0x140025106  lea     ebp, [rbx+58h]
0x140025109  mov     r8d, 78436644h
0x14002510f  mov     edx, ebp
0x140025111  mov     ecx, 42h ; 'B'
0x140025116  mov     r14d, ebp
0x140025119  call    cs:__imp_ExAllocatePool2
0x140025120  nop     dword ptr [rax+rax+00h]
0x140025125  mov     rdi, rax
0x140025128  test    rax, rax
0x14002512b  jz      loc_14002527A
0x140025131  mov     r8d, r14d; Size
0x140025134  xor     edx, edx; Val
0x140025136  mov     rcx, rax; void *
0x140025139  call    memset
0x14002513e  mov     word ptr [rdi], 8104h
0x140025143  lea     rcx, [rdi+64h]; void *
0x140025147  mov     [rdi+2], bp
0x14002514b  mov     dword ptr [rdi+4], 1
0x140025152  movups  xmm0, xmmword ptr [rsp+98h+DestinationString.Length]
0x140025157  mov     [rdi+18h], r12
0x14002515b  movups  xmmword ptr [rdi+8], xmm0
0x14002515f  movsd   xmm0, qword ptr cs:Str2; "Principal"
0x140025167  movsd   qword ptr [rdi+58h], xmm0
0x14002516c  movzx   eax, byte ptr cs:Str2+8; "l"
0x140025173  mov     [rdi+60h], al
0x140025176  mov     byte ptr [rdi+55h], 0Bh
0x14002517a  movzx   eax, [rsp+98h+DestinationString.Length]
0x14002517f  mov     [rdi+56h], ax
0x140025183  mov     r8d, eax; Size
0x140025186  mov     rdx, [rsp+98h+DestinationString.Buffer]; Src
0x14002518b  call    memmove
0x140025190  mov     [rdi+50h], r12d
0x140025194  mov     [rdi+48h], ebx
0x140025197  test    r13, r13
0x14002519a  jnz     loc_140025284
0x1400251a0  movups  xmm0, xmmword ptr [rsp+98h+var_58.Length]
0x1400251a5  movups  xmmword ptr [rdi+38h], xmm0
0x1400251a9  mov     [r15], rdi
0x1400251ac  test    esi, esi
0x1400251ae  jnz     short loc_1400251E1
0x1400251b0  mov     eax, esi
0x1400251b2  add     rsp, 58h
0x1400251b6  pop     r15
0x1400251b8  pop     r14
0x1400251ba  pop     r13
0x1400251bc  pop     r12
0x1400251be  pop     rdi
0x1400251bf  pop     rsi
0x1400251c0  pop     rbp
0x1400251c1  pop     rbx
0x1400251c2  retn
0x1400251c4  xor     edx, edx; SourceString
0x1400251c6  lea     rcx, [rsp+98h+DestinationString]; DestinationString
0x1400251cb  call    cs:__imp_RtlInitUnicodeString
0x1400251d2  nop     dword ptr [rax+rax+00h]
0x1400251d7  jmp     loc_1400250E3
0x1400251dc  mov     esi, 0C000009Ah
0x1400251e1  mov     rcx, [rsp+98h+DestinationString.Buffer]; P
0x1400251e6  test    rcx, rcx
0x1400251e9  jz      short loc_140025202
0x1400251eb  xor     edx, edx; Tag
0x1400251ed  call    cs:__imp_ExFreePoolWithTag
0x1400251f4  nop     dword ptr [rax+rax+00h]
0x1400251f9  mov     [rsp+98h+DestinationString.Buffer], 0
0x140025202  mov     rcx, [rsp+98h+var_58.Buffer]; P
0x140025207  test    rcx, rcx
0x14002520a  jz      short loc_1400251B0
0x14002520c  xor     edx, edx; Tag
0x14002520e  call    cs:__imp_ExFreePoolWithTag
0x140025215  nop     dword ptr [rax+rax+00h]
0x14002521a  jmp     short loc_1400251B0
0x14002521c  mov     esi, 0C000009Ah
0x140025221  jmp     short loc_1400251E1
0x140025223  lea     rdx, [r13+38h]
0x140025227  test    rdx, rdx
0x14002522a  jz      loc_1400250EF
0x140025230  cmp     word ptr [rdx], 0
0x140025234  jz      loc_1400250EF
0x14002523a  mov     rax, [r13+40h]
0x14002523e  test    rax, rax
0x140025241  jz      loc_1400250EF
0x140025247  cmp     word ptr [rax], 0
0x14002524b  jz      loc_1400250EF
0x140025251  mov     r8d, 78436644h
0x140025257  lea     rcx, [rsp+98h+var_58]
0x14002525c  call    DfscCreateNameFromUnicodeString
0x140025261  mov     esi, eax
0x140025263  test    eax, eax
0x140025265  jnz     loc_1400251E1
0x14002526b  jmp     loc_1400250EF
0x140025270  mov     esi, 0C000000Dh
0x140025275  jmp     loc_1400251E1
0x14002527a  mov     esi, 0C000009Ah
0x14002527f  jmp     loc_1400251E1
0x140025284  mov     eax, [r13+28h]
0x140025288  mov     [rdi+28h], eax
0x14002528b  mov     eax, [r13+2Ch]
0x14002528f  mov     [rdi+2Ch], eax
0x140025292  mov     eax, [r13+34h]
0x140025296  mov     [rdi+34h], eax
0x140025299  mov     eax, [r13+30h]
0x14002529d  mov     [rdi+30h], eax
0x1400252a0  jmp     loc_1400251A0
```
