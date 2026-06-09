# DfscRmGenerateDomainDcReferralFromDCName

- ea: `0x140001df8`
- end: `0x140001f45`
- name: `DfscRmGenerateDomainDcReferralFromDCName`
- size: `333`
- prototype: `__int64 __fastcall(PCUNICODE_STRING SourceString, const void **, __int64 *, char, char)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1400172ec`
- `0x14001abc0`
- `0x140022840`

## callees

- `0x140001df8`
- `0x140002134`
- `0x140006080`
- `0x14001d090`
- `0x14001ef20`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x140001ea1`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140001ea1`

## pseudocode

```c
__int64 __fastcall DfscRmGenerateDomainDcReferralFromDCName(
        PCUNICODE_STRING SourceString,
        const void **a2,
        __int64 *a3,
        char a4,
        char a5)
{
  unsigned int v6; // ebp
  size_t v8; // rcx
  __int64 Referral; // rax
  __int64 v12; // rdi
  int inited; // ebx
  __int128 *v14; // rbp
  void *v15; // rbx
  __int64 v16; // r8
  __int64 v17; // r9
  __int128 v18; // xmm0
  __int128 v20; // [rsp+20h] [rbp-48h] BYREF

  v6 = DWORD2(xmmword_14000C740);
  v8 = SourceString->Length + 276 + (unsigned int)*(unsigned __int16 *)a2;
  v20 = 0;
  Referral = DfscRmAllocateReferral(v8);
  v12 = Referral;
  if ( Referral )
  {
    *(_WORD *)(Referral + 12) |= 8u;
    *(_BYTE *)(Referral + 14) = a4;
    *(_WORD *)(Referral + 24) = 1;
    *(_WORD *)(Referral + 26) = 0;
    if ( v6 > 0x258 )
      v6 = 600;
    *(_BYTE *)(Referral + 15) = a5;
    *(_QWORD *)(Referral + 152) = Referral + 272;
    *(_DWORD *)(Referral + 40) = v6;
    v14 = (__int128 *)(Referral + 144);
    *(_WORD *)(Referral + 146) = SourceString->Length + 2;
    RtlCopyUnicodeString((PUNICODE_STRING)(Referral + 144), SourceString);
    v15 = (void *)(*(_QWORD *)(v12 + 152) + *(unsigned __int16 *)(v12 + 146));
    memmove(v15, a2[1], *(unsigned __int16 *)a2);
    *((_WORD *)v15 + ((unsigned __int64)*(unsigned __int16 *)a2 >> 1)) = 0;
    LOWORD(v20) = *(_WORD *)a2;
    WORD1(v20) = v20 + 2;
    *((_QWORD *)&v20 + 1) = v15;
    inited = DfscInitDfsPath(&v20, v12 + 176, v16, v17);
    if ( inited < 0 )
    {
      DfscRmDereferenceReferral((PVOID)v12);
    }
    else
    {
      *(_DWORD *)(v12 + 168) = -1;
      v18 = *v14;
      *(_DWORD *)(v12 + 8) = 0;
      *(_OWORD *)(v12 + 128) = v18;
      if ( a3 )
        *a3 = v12;
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
0x140001df8  push    rbx
0x140001dfa  push    rbp
0x140001dfb  push    rsi
0x140001dfc  push    rdi
0x140001dfd  push    r14
0x140001dff  push    r15
0x140001e01  sub     rsp, 38h
0x140001e05  movzx   r10d, word ptr [rcx]
0x140001e09  mov     rbx, rcx
0x140001e0c  movzx   ecx, word ptr [rdx]
0x140001e0f  add     r10d, 114h
0x140001e16  mov     ebp, dword ptr cs:xmmword_14000C740+8
0x140001e1c  mov     r14, rdx
0x140001e1f  xorps   xmm0, xmm0
0x140001e22  add     ecx, r10d; Size
0x140001e25  mov     edx, 72436644h
0x140001e2a  mov     r15b, r9b
0x140001e2d  mov     rsi, r8
0x140001e30  movups  [rsp+68h+var_48], xmm0
0x140001e35  call    DfscRmAllocateReferral
0x140001e3a  mov     rdi, rax
0x140001e3d  test    rax, rax
0x140001e40  jnz     short loc_140001E4C
0x140001e42  mov     ebx, 0C000009Ah
0x140001e47  jmp     loc_140001F35
0x140001e4c  or      word ptr [rax+0Ch], 8
0x140001e51  mov     rdx, rbx; SourceString
0x140001e54  mov     [rax+0Eh], r15b
0x140001e58  mov     word ptr [rax+18h], 1
0x140001e5e  xor     eax, eax
0x140001e60  mov     [rdi+1Ah], ax
0x140001e64  mov     eax, 258h
0x140001e69  cmp     ebp, eax
0x140001e6b  cmova   ebp, eax
0x140001e6e  mov     al, [rsp+68h+arg_20]
0x140001e75  mov     [rdi+0Fh], al
0x140001e78  lea     rax, [rdi+110h]
0x140001e7f  mov     [rdi+98h], rax
0x140001e86  mov     [rdi+28h], ebp
0x140001e89  lea     rbp, [rdi+90h]
0x140001e90  movzx   eax, word ptr [rbx]
0x140001e93  mov     rcx, rbp; DestinationString
0x140001e96  add     ax, 2
0x140001e9a  mov     [rdi+92h], ax
0x140001ea1  call    cs:__imp_RtlCopyUnicodeString
0x140001ea8  nop     dword ptr [rax+rax+00h]
0x140001ead  movzx   ebx, word ptr [rdi+92h]
0x140001eb4  add     rbx, [rdi+98h]
0x140001ebb  movzx   r8d, word ptr [r14]; Size
0x140001ebf  mov     rcx, rbx; void *
0x140001ec2  mov     rdx, [r14+8]; Src
0x140001ec6  call    memmove
0x140001ecb  movzx   ecx, word ptr [r14]
0x140001ecf  lea     rdx, [rdi+0B0h]
0x140001ed6  xor     eax, eax
0x140001ed8  shr     rcx, 1
0x140001edb  mov     [rbx+rcx*2], ax
0x140001edf  lea     rcx, [rsp+68h+var_48]
0x140001ee4  movzx   eax, word ptr [r14]
0x140001ee8  mov     word ptr [rsp+68h+var_48], ax
0x140001eed  add     ax, 2
0x140001ef1  mov     word ptr [rsp+68h+var_48+2], ax
0x140001ef6  mov     qword ptr [rsp+68h+var_48+8], rbx
0x140001efb  call    DfscInitDfsPath
0x140001f00  mov     ebx, eax
0x140001f02  test    eax, eax
0x140001f04  js      short loc_140001F2D
0x140001f06  mov     dword ptr [rdi+0A8h], 0FFFFFFFFh
0x140001f10  movups  xmm0, xmmword ptr [rbp+0]
0x140001f14  mov     dword ptr [rdi+8], 0
0x140001f1b  movdqu  xmmword ptr [rdi+80h], xmm0
0x140001f23  test    rsi, rsi
0x140001f26  jz      short loc_140001F35
0x140001f28  mov     [rsi], rdi
0x140001f2b  jmp     short loc_140001F35
0x140001f2d  mov     rcx, rdi; P
0x140001f30  call    DfscRmDereferenceReferral
0x140001f35  mov     eax, ebx
0x140001f37  add     rsp, 38h
0x140001f3b  pop     r15
0x140001f3d  pop     r14
0x140001f3f  pop     rdi
0x140001f40  pop     rsi
0x140001f41  pop     rbp
0x140001f42  pop     rbx
0x140001f43  retn
```
