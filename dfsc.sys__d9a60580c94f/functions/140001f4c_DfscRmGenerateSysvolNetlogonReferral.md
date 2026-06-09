# DfscRmGenerateSysvolNetlogonReferral

- ea: `0x140001f4c`
- end: `0x14000212d`
- name: `DfscRmGenerateSysvolNetlogonReferral`
- size: `481`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140002cd0`
- `0x140003020`
- `0x140016070`

## callees

- `0x140001f4c`
- `0x140002134`
- `0x140006380`
- `0x14001d090`
- `0x14001ef20`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000206d`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140002097`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14000206d`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140002097`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140002016`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140002016`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140002080`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400020aa`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140002080`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400020aa`

## pseudocode

```c
__int64 __fastcall DfscRmGenerateSysvolNetlogonReferral(
        const UNICODE_STRING *a1,
        const UNICODE_STRING *a2,
        char a3,
        _QWORD *a4)
{
  const UNICODE_STRING *v7; // r15
  const UNICODE_STRING *v8; // r13
  unsigned int v9; // r14d
  _WORD *Referral; // rdi
  int inited; // ebx
  __int16 v12; // cx
  struct _UNICODE_STRING v13; // xmm0
  _UNICODE_STRING Destination; // [rsp+20h] [rbp-59h] BYREF
  struct _UNICODE_STRING v16[10]; // [rsp+30h] [rbp-49h] BYREF

  Destination = 0;
  memset(v16, 0, 0x60u);
  v7 = a1 + 3;
  v8 = a1 + 1;
  v9 = DWORD2(xmmword_14000C740);
  Referral = DfscRmAllocateReferral(a1[1].Length + 284 + a1[3].Length + (unsigned int)a2->Length, 0x72436644u);
  if ( Referral )
  {
    Referral[6] |= 8u;
    *((_BYTE *)Referral + 14) = a3;
    *((_DWORD *)Referral + 6) = 1;
    if ( v9 > 0x384 )
      v9 = 900;
    *((_QWORD *)Referral + 19) = Referral + 136;
    *((_DWORD *)Referral + 10) = v9;
    Referral[73] = v7->Length + 2;
    RtlCopyUnicodeString((PUNICODE_STRING)Referral + 9, v7);
    inited = DfscInitDfsPath(Referral + 72, v16);
    if ( inited < 0 )
      goto LABEL_9;
    v12 = a2->Length + 10;
    Destination.Buffer = (PWSTR)(*((_QWORD *)Referral + 19) + (unsigned __int16)Referral[73]);
    Destination.MaximumLength = v8->Length + v12;
    Destination.Length = 0;
    RtlAppendUnicodeToString(&Destination, L"\\");
    RtlAppendUnicodeStringToString(&Destination, a2);
    RtlAppendUnicodeToString(&Destination, L"\\");
    RtlAppendUnicodeStringToString(&Destination, v8);
    Destination.Buffer[((unsigned __int64)Destination.MaximumLength >> 1) - 1] = 0;
    inited = DfscInitDfsPath(&Destination.Length, (struct _UNICODE_STRING *)Referral + 11);
    if ( inited < 0 )
    {
LABEL_9:
      DfscRmDereferenceReferral((volatile signed __int32 *)Referral);
    }
    else
    {
      *((_DWORD *)Referral + 42) = -1;
      v13 = v16[0];
      Referral[6] &= ~2u;
      *((struct _UNICODE_STRING *)Referral + 8) = v13;
      *((_DWORD *)Referral + 2) = 1;
      if ( a4 )
        *a4 = Referral;
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
0x140001f4c  mov     [rsp-8+arg_10], r8b
0x140001f51  push    rbp
0x140001f52  push    rbx
0x140001f53  push    rsi
0x140001f54  push    rdi
0x140001f55  push    r12
0x140001f57  push    r13
0x140001f59  push    r14
0x140001f5b  push    r15
0x140001f5d  lea     rbp, [rsp-1Fh]
0x140001f62  sub     rsp, 98h
0x140001f69  mov     r12, rdx
0x140001f6c  mov     rbx, rcx
0x140001f6f  xor     edx, edx; Val
0x140001f71  lea     rcx, [rbp+57h+var_A0]; void *
0x140001f75  xorps   xmm0, xmm0
0x140001f78  mov     rsi, r9
0x140001f7b  movups  xmmword ptr [rbp+57h+Destination.Length], xmm0
0x140001f7f  lea     r8d, [rdx+60h]; Size
0x140001f83  call    memset
0x140001f88  movzx   ecx, word ptr [r12]
0x140001f8d  lea     r15, [rbx+30h]
0x140001f91  movzx   eax, word ptr [r15]
0x140001f95  lea     r13, [rbx+10h]
0x140001f99  mov     r14d, dword ptr cs:xmmword_14000C740+8
0x140001fa0  add     ecx, eax
0x140001fa2  movzx   eax, word ptr [r13+0]
0x140001fa7  mov     edx, 72436644h
0x140001fac  add     eax, 11Ch
0x140001fb1  add     ecx, eax; Size
0x140001fb3  call    DfscRmAllocateReferral
0x140001fb8  mov     rdi, rax
0x140001fbb  test    rax, rax
0x140001fbe  jnz     short loc_140001FCA
0x140001fc0  mov     ebx, 0C000009Ah
0x140001fc5  jmp     loc_140002116
0x140001fca  mov     al, [rbp+57h+arg_10]
0x140001fcd  lea     rbx, [rdi+90h]
0x140001fd4  or      word ptr [rdi+0Ch], 8
0x140001fd9  mov     rdx, r15; SourceString
0x140001fdc  mov     [rdi+0Eh], al
0x140001fdf  mov     rcx, rbx; DestinationString
0x140001fe2  mov     eax, 384h
0x140001fe7  mov     dword ptr [rdi+18h], 1
0x140001fee  cmp     r14d, eax
0x140001ff1  cmova   r14d, eax
0x140001ff5  lea     rax, [rdi+110h]
0x140001ffc  mov     [rdi+98h], rax
0x140002003  mov     [rdi+28h], r14d
0x140002007  movzx   eax, word ptr [r15]
0x14000200b  add     ax, 2
0x14000200f  mov     [rdi+92h], ax
0x140002016  call    cs:__imp_RtlCopyUnicodeString
0x14000201d  nop     dword ptr [rax+rax+00h]
0x140002022  lea     rdx, [rbp+57h+var_A0]
0x140002026  mov     rcx, rbx
0x140002029  call    DfscInitDfsPath
0x14000202e  mov     ebx, eax
0x140002030  test    eax, eax
0x140002032  js      loc_14000210E
0x140002038  movzx   eax, word ptr [rdi+92h]
0x14000203f  lea     rdx, Source; "\\"
0x140002046  add     rax, [rdi+98h]
0x14000204d  movzx   ecx, word ptr [r12]
0x140002052  add     cx, 0Ah
0x140002056  mov     [rbp+57h+Destination.Buffer], rax
0x14000205a  add     cx, [r13+0]
0x14000205f  xor     eax, eax
0x140002061  mov     [rbp+57h+Destination.MaximumLength], cx
0x140002065  lea     rcx, [rbp+57h+Destination]; Destination
0x140002069  mov     [rbp+57h+Destination.Length], ax
0x14000206d  call    cs:__imp_RtlAppendUnicodeToString
0x140002074  nop     dword ptr [rax+rax+00h]
0x140002079  mov     rdx, r12; Source
0x14000207c  lea     rcx, [rbp+57h+Destination]; Destination
0x140002080  call    cs:__imp_RtlAppendUnicodeStringToString
0x140002087  nop     dword ptr [rax+rax+00h]
0x14000208c  lea     rdx, Source; "\\"
0x140002093  lea     rcx, [rbp+57h+Destination]; Destination
0x140002097  call    cs:__imp_RtlAppendUnicodeToString
0x14000209e  nop     dword ptr [rax+rax+00h]
0x1400020a3  mov     rdx, r13; Source
0x1400020a6  lea     rcx, [rbp+57h+Destination]; Destination
0x1400020aa  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400020b1  nop     dword ptr [rax+rax+00h]
0x1400020b6  movzx   edx, [rbp+57h+Destination.MaximumLength]
0x1400020ba  xor     ecx, ecx
0x1400020bc  mov     rax, [rbp+57h+Destination.Buffer]
0x1400020c0  shr     rdx, 1
0x1400020c3  mov     [rax+rdx*2-2], cx
0x1400020c8  lea     rdx, [rdi+0B0h]
0x1400020cf  lea     rcx, [rbp+57h+Destination]
0x1400020d3  call    DfscInitDfsPath
0x1400020d8  mov     ebx, eax
0x1400020da  test    eax, eax
0x1400020dc  js      short loc_14000210E
0x1400020de  mov     dword ptr [rdi+0A8h], 0FFFFFFFFh
0x1400020e8  mov     eax, 0FFFDh
0x1400020ed  movaps  xmm0, [rbp+57h+var_A0]
0x1400020f1  and     [rdi+0Ch], ax
0x1400020f5  movdqu  xmmword ptr [rdi+80h], xmm0
0x1400020fd  mov     dword ptr [rdi+8], 1
0x140002104  test    rsi, rsi
0x140002107  jz      short loc_140002116
0x140002109  mov     [rsi], rdi
0x14000210c  jmp     short loc_140002116
0x14000210e  mov     rcx, rdi; P
0x140002111  call    DfscRmDereferenceReferral
0x140002116  mov     eax, ebx
0x140002118  add     rsp, 98h
0x14000211f  pop     r15
0x140002121  pop     r14
0x140002123  pop     r13
0x140002125  pop     r12
0x140002127  pop     rdi
0x140002128  pop     rsi
0x140002129  pop     rbx
0x14000212a  pop     rbp
0x14000212b  retn
```
