# SIPolicyQuerySubVerBlock

- ea: `0x1800a4920`
- end: `0x1800a4a94`
- name: `SIPolicyQuerySubVerBlock`
- size: `372`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a4240`

## callees

- `0x1800a4920`
- `0x1800a4a9c`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1800a4a16`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a4a16`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800a4a45`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800a4a45`

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
0x1800a4920  push    rbx
0x1800a4922  push    rbp
0x1800a4923  push    rsi
0x1800a4924  push    rdi
0x1800a4925  push    r12
0x1800a4927  push    r13
0x1800a4929  push    r14
0x1800a492b  push    r15
0x1800a492d  sub     rsp, 48h
0x1800a4931  xor     ebp, ebp
0x1800a4933  xorps   xmm0, xmm0
0x1800a4936  xorps   xmm1, xmm1
0x1800a4939  mov     r12, r9
0x1800a493c  mov     r13, r8
0x1800a493f  mov     rdi, rdx
0x1800a4942  mov     rbx, rcx
0x1800a4945  mov     r14d, 0C0000225h
0x1800a494b  movups  xmmword ptr [rsp+88h+String1.Length], xmm0
0x1800a4950  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm1
0x1800a4955  cmp     [rcx+4], bp
0x1800a4959  jnz     short loc_1800A49D0
0x1800a495b  movzx   ecx, word ptr [rcx]
0x1800a495e  mov     edx, 7FF8h
0x1800a4963  lea     eax, [rcx-8]
0x1800a4966  cmp     ax, dx
0x1800a4969  ja      short loc_1800A49D0
0x1800a496b  test    cl, 1
0x1800a496e  jnz     short loc_1800A49D0
0x1800a4970  mov     r15d, 2
0x1800a4976  jmp     short loc_1800A497B
0x1800a4978  add     rdi, r15
0x1800a497b  cmp     word ptr [rdi], 5Ch ; '\'
0x1800a497f  jz      short loc_1800A4978
0x1800a4981  movzx   edx, word ptr [rbx]
0x1800a4984  mov     rcx, rbx
0x1800a4987  call    SIPolicyCheckVerBlock
0x1800a498c  mov     rsi, rax
0x1800a498f  test    rax, rax
0x1800a4992  jz      short loc_1800A49D0
0x1800a4994  cmp     [rdi], bp
0x1800a4997  jnz     short loc_1800A49E5
0x1800a4999  movzx   eax, word ptr [rbx+2]
0x1800a499d  mov     [r12], rax
0x1800a49a1  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a49a5  inc     rax
0x1800a49a8  cmp     [rbx+rax*2+6], bp
0x1800a49ad  jnz     short loc_1800A49A5
0x1800a49af  movzx   ecx, word ptr [rbx+2]
0x1800a49b3  test    cx, cx
0x1800a49b6  jnz     loc_1800A4A6F
0x1800a49bc  mov     eax, eax
0x1800a49be  lea     rax, ds:6[rax*2]
0x1800a49c6  add     rax, rbx
0x1800a49c9  mov     r14d, ebp
0x1800a49cc  mov     [r13+0], rax
0x1800a49d0  mov     eax, r14d
0x1800a49d3  add     rsp, 48h
0x1800a49d7  pop     r15
0x1800a49d9  pop     r14
0x1800a49db  pop     r13
0x1800a49dd  pop     r12
0x1800a49df  pop     rdi
0x1800a49e0  pop     rsi
0x1800a49e1  pop     rbp
0x1800a49e2  pop     rbx
0x1800a49e3  retn
0x1800a49e5  mov     r15, rdi
0x1800a49e8  cmp     word ptr [rdi], 5Ch ; '\'
0x1800a49ec  jz      short loc_1800A49F7
0x1800a49ee  add     rdi, 2
0x1800a49f2  cmp     [rdi], bp
0x1800a49f5  jnz     short loc_1800A49E8
0x1800a49f7  movzx   ebp, word ptr [rbx]
0x1800a49fa  add     ebp, ebx
0x1800a49fc  mov     edx, ebp
0x1800a49fe  mov     rcx, rsi
0x1800a4a01  sub     edx, esi
0x1800a4a03  call    SIPolicyCheckVerBlock
0x1800a4a08  test    rax, rax
0x1800a4a0b  jz      short loc_1800A49D0
0x1800a4a0d  lea     rdx, [rsi+6]; SourceString
0x1800a4a11  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x1800a4a16  call    cs:__imp_RtlInitUnicodeString
0x1800a4a1d  nop     dword ptr [rax+rax+00h]
0x1800a4a22  movzx   eax, di
0x1800a4a25  mov     [rsp+88h+String1.Buffer], r15
0x1800a4a2a  sub     ax, r15w
0x1800a4a2e  lea     rdx, [rsp+88h+DestinationString]; String2
0x1800a4a33  mov     r8b, 1; CaseInSensitive
0x1800a4a36  mov     [rsp+88h+String1.Length], ax
0x1800a4a3b  lea     rcx, [rsp+88h+String1]; String1
0x1800a4a40  mov     [rsp+88h+String1.MaximumLength], ax
0x1800a4a45  call    cs:__imp_RtlCompareUnicodeString
0x1800a4a4c  nop     dword ptr [rax+rax+00h]
0x1800a4a51  test    eax, eax
0x1800a4a53  jz      short loc_1800A4A65
0x1800a4a55  movzx   eax, word ptr [rsi]
0x1800a4a58  add     rax, 3
0x1800a4a5c  and     rax, 0FFFFFFFFFFFFFFFCh
0x1800a4a60  add     rsi, rax
0x1800a4a63  jmp     short loc_1800A49FC
0x1800a4a65  mov     rbx, rsi
0x1800a4a68  xor     ebp, ebp
0x1800a4a6a  jmp     loc_1800A4970
0x1800a4a6f  cmp     [rbx+4], bp
0x1800a4a73  jz      short loc_1800A4A89
0x1800a4a75  lea     eax, ds:0Bh[rax*2]
0x1800a4a7c  mov     ecx, 0FFFFFFFCh
0x1800a4a81  and     rax, rcx
0x1800a4a84  jmp     loc_1800A49C6
0x1800a4a89  cmp     cx, r15w
0x1800a4a8d  jnb     short loc_1800A4A75
0x1800a4a8f  jmp     loc_1800A49BC
```
