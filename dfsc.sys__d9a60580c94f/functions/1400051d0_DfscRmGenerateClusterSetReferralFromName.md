# DfscRmGenerateClusterSetReferralFromName

- ea: `0x1400051d0`
- end: `0x14000530a`
- name: `DfscRmGenerateClusterSetReferralFromName`
- size: `314`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, const void **, struct _UNICODE_STRING **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400169f8`

## callees

- `0x140002134`
- `0x1400051d0`
- `0x140006080`
- `0x14001d090`
- `0x14001ef20`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14000526a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000526a`

## pseudocode

```c
__int64 __fastcall DfscRmGenerateClusterSetReferralFromName(
        PCUNICODE_STRING SourceString,
        const void **a2,
        struct _UNICODE_STRING **a3)
{
  size_t v5; // rcx
  _WORD *Referral; // rax
  struct _UNICODE_STRING *v8; // rsi
  int inited; // ebx
  struct _UNICODE_STRING *v10; // r15
  char *v11; // rbx
  unsigned int v12; // edi
  struct _UNICODE_STRING v13; // xmm0
  __int128 v15; // [rsp+20h] [rbp-48h] BYREF

  v5 = SourceString->Length + 276 + (unsigned int)*(unsigned __int16 *)a2;
  v15 = 0;
  Referral = DfscRmAllocateReferral(v5, 0x72436644u);
  v8 = (struct _UNICODE_STRING *)Referral;
  if ( Referral )
  {
    *((_BYTE *)Referral + 14) = 0;
    v10 = (struct _UNICODE_STRING *)(Referral + 72);
    *(_WORD *)((char *)Referral + 15) = 256;
    Referral[6] &= ~8u;
    *((_DWORD *)Referral + 6) = 1;
    *((_QWORD *)Referral + 19) = Referral + 136;
    *((_DWORD *)Referral + 10) = -1;
    Referral[73] = SourceString->Length + 2;
    RtlCopyUnicodeString((PUNICODE_STRING)Referral + 9, SourceString);
    v11 = (char *)v8[9].Buffer + v8[9].MaximumLength;
    v12 = *(unsigned __int16 *)a2;
    memmove(v11, a2[1], *(unsigned __int16 *)a2);
    *(_WORD *)&v11[2 * ((unsigned __int64)v12 >> 1)] = 0;
    LOWORD(v15) = v12;
    WORD1(v15) = v12 + 2;
    *((_QWORD *)&v15 + 1) = v11;
    inited = DfscInitDfsPath((unsigned __int16 *)&v15, v8 + 11);
    if ( inited < 0 )
    {
      DfscRmDereferenceReferral((volatile signed __int32 *)v8);
    }
    else
    {
      LODWORD(v8[10].Buffer) = 0;
      v13 = *v10;
      LODWORD(v8->Buffer) = 1;
      v8[8] = v13;
      if ( a3 )
        *a3 = v8;
    }
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x1400051d0  push    rbx
0x1400051d2  push    rbp
0x1400051d3  push    rsi
0x1400051d4  push    rdi
0x1400051d5  push    r13
0x1400051d7  push    r14
0x1400051d9  push    r15
0x1400051db  sub     rsp, 30h
0x1400051df  movzx   r9d, word ptr [rcx]
0x1400051e3  mov     rbx, rcx
0x1400051e6  movzx   ecx, word ptr [rdx]
0x1400051e9  add     r9d, 114h
0x1400051f0  mov     rbp, rdx
0x1400051f3  xorps   xmm0, xmm0
0x1400051f6  add     ecx, r9d; Size
0x1400051f9  mov     edx, 72436644h
0x1400051fe  mov     r14, r8
0x140005201  movups  [rsp+68h+var_48], xmm0
0x140005206  call    DfscRmAllocateReferral
0x14000520b  mov     rsi, rax
0x14000520e  test    rax, rax
0x140005211  jnz     short loc_14000521D
0x140005213  mov     ebx, 0C000009Ah
0x140005218  jmp     loc_1400052F8
0x14000521d  mov     byte ptr [rax+0Eh], 0
0x140005221  lea     r15, [rsi+90h]
0x140005228  mov     eax, 0FFF7h
0x14000522d  mov     word ptr [rsi+0Fh], 100h
0x140005233  and     [rsi+0Ch], ax
0x140005237  mov     r13d, 1
0x14000523d  lea     rax, [rsi+110h]
0x140005244  mov     [rsi+18h], r13d
0x140005248  mov     [rsi+98h], rax
0x14000524f  mov     rdx, rbx; SourceString
0x140005252  mov     dword ptr [rsi+28h], 0FFFFFFFFh
0x140005259  mov     rcx, r15; DestinationString
0x14000525c  movzx   eax, word ptr [rbx]
0x14000525f  add     ax, 2
0x140005263  mov     [rsi+92h], ax
0x14000526a  call    cs:__imp_RtlCopyUnicodeString
0x140005271  nop     dword ptr [rax+rax+00h]
0x140005276  movzx   ebx, word ptr [rsi+92h]
0x14000527d  add     rbx, [rsi+98h]
0x140005284  movzx   edi, word ptr [rbp+0]
0x140005288  mov     rcx, rbx; void *
0x14000528b  mov     rdx, [rbp+8]; Src
0x14000528f  mov     r8d, edi; Size
0x140005292  call    memmove
0x140005297  mov     ecx, edi
0x140005299  lea     rdx, [rsi+0B0h]
0x1400052a0  shr     rcx, 1
0x1400052a3  xor     eax, eax
0x1400052a5  mov     [rbx+rcx*2], ax
0x1400052a9  lea     rcx, [rsp+68h+var_48]
0x1400052ae  mov     word ptr [rsp+68h+var_48], di
0x1400052b3  add     di, 2
0x1400052b7  mov     word ptr [rsp+68h+var_48+2], di
0x1400052bc  mov     qword ptr [rsp+68h+var_48+8], rbx
0x1400052c1  call    DfscInitDfsPath
0x1400052c6  mov     ebx, eax
0x1400052c8  test    eax, eax
0x1400052ca  js      short loc_1400052F0
0x1400052cc  mov     dword ptr [rsi+0A8h], 0
0x1400052d6  movups  xmm0, xmmword ptr [r15]
0x1400052da  mov     [rsi+8], r13d
0x1400052de  movdqu  xmmword ptr [rsi+80h], xmm0
0x1400052e6  test    r14, r14
0x1400052e9  jz      short loc_1400052F8
0x1400052eb  mov     [r14], rsi
0x1400052ee  jmp     short loc_1400052F8
0x1400052f0  mov     rcx, rsi; P
0x1400052f3  call    DfscRmDereferenceReferral
0x1400052f8  mov     eax, ebx
0x1400052fa  add     rsp, 30h
0x1400052fe  pop     r15
0x140005300  pop     r14
0x140005302  pop     r13
0x140005304  pop     rdi
0x140005305  pop     rsi
0x140005306  pop     rbp
0x140005307  pop     rbx
0x140005308  retn
```
