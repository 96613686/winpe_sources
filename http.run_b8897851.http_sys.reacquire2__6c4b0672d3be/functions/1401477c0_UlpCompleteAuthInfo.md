# UlpCompleteAuthInfo

- ea: `0x1401477c0`
- end: `0x140147a87`
- name: `UlpCompleteAuthInfo`
- size: `711`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140148060`
- `0x140148450`
- `0x140149ce0`

## callees

- `0x14014756c`
- `0x1401477c0`
- `0x140149bb0`
- `0x140167840`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140147880`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401478f5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14014790c`
- `ntoskrnl!RtlInitUnicodeString` at `0x140147880`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401478f5`
- `ntoskrnl!RtlInitUnicodeString` at `0x14014790c`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140147923`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140147944`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140147923`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140147944`
- `ntoskrnl!ZwClose` at `0x1401479be`
- `ntoskrnl!ZwClose` at `0x1401479be`
- `ntoskrnl!ExAllocatePool3` at `0x1401478ae`
- `ntoskrnl!ExAllocatePool3` at `0x1401478ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401479e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401479e9`
- `ksecdd!ExportSecurityContext` at `0x140147972`
- `ksecdd!ExportSecurityContext` at `0x140147972`
- `ksecdd!QueryContextAttributesW` at `0x140147859`
- `ksecdd!QueryContextAttributesW` at `0x140147859`
- `ksecdd!QuerySecurityContextToken` at `0x140147813`
- `ksecdd!QuerySecurityContextToken` at `0x140147813`
- `ksecdd!FreeContextBuffer` at `0x1401479d3`
- `ksecdd!FreeContextBuffer` at `0x1401479fe`
- `ksecdd!FreeContextBuffer` at `0x140147a57`
- `ksecdd!FreeContextBuffer` at `0x1401479d3`
- `ksecdd!FreeContextBuffer` at `0x1401479fe`
- `ksecdd!FreeContextBuffer` at `0x140147a57`

## pseudocode

```c
__int64 __fastcall UlpCompleteAuthInfo(__int64 a1, __int64 a2, __int64 a3)
{
  struct _SecHandle *v3; // r12
  void *v7; // r14
  SECURITY_STATUS v8; // esi
  void *Pool3; // rax
  void *v10; // rcx
  __int64 result; // rax
  __int64 v12; // rax
  PCWSTR *v13; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _SecBuffer pPackedContext; // [rsp+40h] [rbp-30h] BYREF
  UNICODE_STRING String1; // [rsp+50h] [rbp-20h] BYREF
  UNICODE_STRING v17; // [rsp+60h] [rbp-10h] BYREF
  void *Token; // [rsp+B8h] [rbp+48h] BYREF
  PCWSTR *pBuffer; // [rsp+C8h] [rbp+58h] BYREF

  v3 = (struct _SecHandle *)(a2 + 8);
  *(_QWORD *)&pPackedContext.cbBuffer = 0;
  Token = 0;
  pBuffer = 0;
  pPackedContext.pvBuffer = 0;
  v7 = 0;
  String1 = 0;
  v17 = 0;
  DestinationString = 0;
  v8 = QuerySecurityContextToken((PCtxtHandle)(a2 + 8), &Token);
  if ( v8 < 0 )
  {
    Token = 0;
LABEL_20:
    *(_DWORD *)a3 |= 1u;
    v10 = Token;
    *(_DWORD *)(a3 + 16) = 2;
    *(_DWORD *)(a3 + 20) = v8;
    if ( v10 )
      ZwClose(v10);
    if ( pBuffer )
      FreeContextBuffer(pBuffer);
    if ( v7 )
      ExFreePoolWithTag(v7, 0);
    if ( pPackedContext.pvBuffer )
      FreeContextBuffer(pPackedContext.pvBuffer);
    return (unsigned int)v8;
  }
  if ( *(_BYTE *)(a1 + 1052) )
  {
    v8 = UlpReplaceSystemAccessToken(a1, &Token);
    if ( v8 < 0 )
      goto LABEL_20;
  }
  v8 = QueryContextAttributesW(v3, 0xAu, &pBuffer);
  if ( v8 < 0 )
  {
    pBuffer = 0;
    goto LABEL_20;
  }
  RtlInitUnicodeString(&DestinationString, pBuffer[2]);
  Pool3 = (void *)ExAllocatePool3(258, DestinationString.Length + 2LL, 1415081045, UxLowPriorityPool, 1);
  v7 = Pool3;
  if ( !Pool3 )
  {
    v8 = -2146893056;
    goto LABEL_20;
  }
  memmove(Pool3, DestinationString.Buffer, DestinationString.Length + 2LL);
  if ( *(_BYTE *)(*(_QWORD *)a2 + 107LL) )
  {
    RtlInitUnicodeString(&String1, *(PCWSTR *)(a1 + 536));
    RtlInitUnicodeString(&v17, *(PCWSTR *)(a1 + 792));
    if ( RtlEqualUnicodeString(&String1, &DestinationString, 1u) )
    {
      *(_BYTE *)(a2 + 29) = 1;
    }
    else if ( RtlEqualUnicodeString(&v17, &DestinationString, 1u) )
    {
      *(_BYTE *)(a2 + 30) = 1;
    }
  }
  if ( (*(_DWORD *)a3 & 8) != 0 && **(_DWORD **)a2 != 2 )
  {
    v8 = ExportSecurityContext(v3, 0, &pPackedContext, 0);
    if ( v8 < 0 )
    {
      pPackedContext.pvBuffer = 0;
      goto LABEL_20;
    }
  }
  if ( (*(_DWORD *)(a3 + 136) & 1) != 0 )
  {
    v8 = UlpCheckAuthenticationSpn(a1, a2, a3);
    if ( v8 )
      goto LABEL_20;
  }
  v12 = *(_QWORD *)(a2 + 56);
  if ( v12 )
  {
    *(_QWORD *)(a3 + 88) = v12;
    *(_DWORD *)(a3 + 96) = *(_DWORD *)(a2 + 64);
    *(_DWORD *)(a3 + 100) = *(_DWORD *)(a2 + 68);
    *(_QWORD *)(a2 + 56) = 0;
    *(_QWORD *)(a2 + 64) = 0;
  }
  *(_DWORD *)a3 |= 1u;
  v13 = pBuffer;
  *(_DWORD *)(a3 + 16) = 0;
  *(_DWORD *)(a3 + 20) = v8;
  *(_DWORD *)(a3 + 32) = *(_DWORD *)(a2 + 24);
  *(_QWORD *)(a3 + 24) = Token;
  *(_WORD *)(a3 + 80) = DestinationString.Length;
  *(_QWORD *)(a3 + 72) = v7;
  FreeContextBuffer(v13);
  result = 0;
  *(struct _SecBuffer *)(a3 + 56) = pPackedContext;
  return result;
}

```

## disassembly

```asm
0x1401477c0  mov     [rsp-38h+arg_0], rbx
0x1401477c5  push    rbp
0x1401477c6  push    rsi
0x1401477c7  push    rdi
0x1401477c8  push    r12
0x1401477ca  push    r13
0x1401477cc  push    r14
0x1401477ce  push    r15
0x1401477d0  mov     rbp, rsp
0x1401477d3  sub     rsp, 70h
0x1401477d7  xor     r13d, r13d
0x1401477da  lea     r12, [rdx+8]
0x1401477de  xorps   xmm0, xmm0
0x1401477e1  mov     qword ptr [rbp+pPackedContext.cbBuffer], r13
0x1401477e5  mov     rdi, rdx
0x1401477e8  mov     [rbp+Token], r13
0x1401477ec  mov     r15, rcx
0x1401477ef  mov     [rbp+pBuffer], r13
0x1401477f3  xorps   xmm1, xmm1
0x1401477f6  mov     [rbp+pPackedContext.pvBuffer], r13
0x1401477fa  mov     rcx, r12; phContext
0x1401477fd  lea     rdx, [rbp+Token]; Token
0x140147801  mov     rbx, r8
0x140147804  mov     r14d, r13d
0x140147807  movups  xmmword ptr [rbp+String1.Length], xmm0
0x14014780b  movups  xmmword ptr [rbp+var_10.Length], xmm1
0x14014780f  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140147813  call    cs:__imp_QuerySecurityContextToken
0x14014781a  nop     dword ptr [rax+rax+00h]
0x14014781f  mov     esi, eax
0x140147821  test    eax, eax
0x140147823  jns     short loc_14014782E
0x140147825  mov     [rbp+Token], r13
0x140147829  jmp     loc_1401479A8
0x14014782e  cmp     [r15+41Ch], r13b
0x140147835  jz      short loc_14014784D
0x140147837  lea     rdx, [rbp+Token]
0x14014783b  mov     rcx, r15
0x14014783e  call    UlpReplaceSystemAccessToken
0x140147843  mov     esi, eax
0x140147845  test    eax, eax
0x140147847  js      loc_1401479A8
0x14014784d  lea     r8, [rbp+pBuffer]; pBuffer
0x140147851  mov     edx, 0Ah; ulAttribute
0x140147856  mov     rcx, r12; phContext
0x140147859  call    cs:__imp_QueryContextAttributesW
0x140147860  nop     dword ptr [rax+rax+00h]
0x140147865  mov     esi, eax
0x140147867  test    eax, eax
0x140147869  jns     short loc_140147874
0x14014786b  mov     [rbp+pBuffer], r13
0x14014786f  jmp     loc_1401479A8
0x140147874  mov     rdx, [rbp+pBuffer]
0x140147878  lea     rcx, [rbp+DestinationString]; DestinationString
0x14014787c  mov     rdx, [rdx+10h]; SourceString
0x140147880  call    cs:__imp_RtlInitUnicodeString
0x140147887  nop     dword ptr [rax+rax+00h]
0x14014788c  movzx   edx, [rbp+DestinationString.Length]
0x140147890  lea     r9, UxLowPriorityPool
0x140147897  add     rdx, 2
0x14014789b  mov     [rsp+70h+var_50], 1
0x1401478a3  mov     ecx, 102h
0x1401478a8  mov     r8d, 54586C55h
0x1401478ae  call    cs:__imp_ExAllocatePool3
0x1401478b5  nop     dword ptr [rax+rax+00h]
0x1401478ba  mov     r14, rax
0x1401478bd  test    rax, rax
0x1401478c0  jnz     short loc_1401478CC
0x1401478c2  mov     esi, 80090300h
0x1401478c7  jmp     loc_1401479A8
0x1401478cc  movzx   r8d, [rbp+DestinationString.Length]
0x1401478d1  mov     rcx, r14; void *
0x1401478d4  mov     rdx, [rbp+DestinationString.Buffer]; Src
0x1401478d8  add     r8, 2; Size
0x1401478dc  call    memmove
0x1401478e1  mov     rax, [rdi]
0x1401478e4  cmp     [rax+6Bh], r13b
0x1401478e8  jz      short loc_140147958
0x1401478ea  mov     rdx, [r15+218h]; SourceString
0x1401478f1  lea     rcx, [rbp+String1]; DestinationString
0x1401478f5  call    cs:__imp_RtlInitUnicodeString
0x1401478fc  nop     dword ptr [rax+rax+00h]
0x140147901  mov     rdx, [r15+318h]; SourceString
0x140147908  lea     rcx, [rbp+var_10]; DestinationString
0x14014790c  call    cs:__imp_RtlInitUnicodeString
0x140147913  nop     dword ptr [rax+rax+00h]
0x140147918  mov     r8b, 1; CaseInSensitive
0x14014791b  lea     rdx, [rbp+DestinationString]; String2
0x14014791f  lea     rcx, [rbp+String1]; String1
0x140147923  call    cs:__imp_RtlEqualUnicodeString
0x14014792a  nop     dword ptr [rax+rax+00h]
0x14014792f  test    al, al
0x140147931  jz      short loc_140147939
0x140147933  mov     byte ptr [rdi+1Dh], 1
0x140147937  jmp     short loc_140147958
0x140147939  mov     r8b, 1; CaseInSensitive
0x14014793c  lea     rdx, [rbp+DestinationString]; String2
0x140147940  lea     rcx, [rbp+var_10]; String1
0x140147944  call    cs:__imp_RtlEqualUnicodeString
0x14014794b  nop     dword ptr [rax+rax+00h]
0x140147950  test    al, al
0x140147952  jz      short loc_140147958
0x140147954  mov     byte ptr [rdi+1Eh], 1
0x140147958  mov     eax, [rbx]
0x14014795a  test    al, 8
0x14014795c  jz      short loc_14014798A
0x14014795e  mov     rax, [rdi]
0x140147961  cmp     dword ptr [rax], 2
0x140147964  jz      short loc_14014798A
0x140147966  xor     r9d, r9d; pToken
0x140147969  lea     r8, [rbp+pPackedContext]; pPackedContext
0x14014796d  xor     edx, edx; fFlags
0x14014796f  mov     rcx, r12; phContext
0x140147972  call    cs:__imp_ExportSecurityContext
0x140147979  nop     dword ptr [rax+rax+00h]
0x14014797e  mov     esi, eax
0x140147980  test    eax, eax
0x140147982  jns     short loc_14014798A
0x140147984  mov     [rbp+pPackedContext.pvBuffer], r13
0x140147988  jmp     short loc_1401479A8
0x14014798a  mov     eax, [rbx+88h]
0x140147990  test    al, 1
0x140147992  jz      short loc_140147A0E
0x140147994  mov     r8, rbx
0x140147997  mov     rdx, rdi
0x14014799a  mov     rcx, r15
0x14014799d  call    UlpCheckAuthenticationSpn
0x1401479a2  mov     esi, eax
0x1401479a4  test    eax, eax
0x1401479a6  jz      short loc_140147A0E
0x1401479a8  or      dword ptr [rbx], 1
0x1401479ab  mov     rcx, [rbp+Token]; Handle
0x1401479af  mov     dword ptr [rbx+10h], 2
0x1401479b6  mov     [rbx+14h], esi
0x1401479b9  test    rcx, rcx
0x1401479bc  jz      short loc_1401479CA
0x1401479be  call    cs:__imp_ZwClose
0x1401479c5  nop     dword ptr [rax+rax+00h]
0x1401479ca  mov     rcx, [rbp+pBuffer]; pvContextBuffer
0x1401479ce  test    rcx, rcx
0x1401479d1  jz      short loc_1401479DF
0x1401479d3  call    cs:__imp_FreeContextBuffer
0x1401479da  nop     dword ptr [rax+rax+00h]
0x1401479df  test    r14, r14
0x1401479e2  jz      short loc_1401479F5
0x1401479e4  xor     edx, edx; Tag
0x1401479e6  mov     rcx, r14; P
0x1401479e9  call    cs:__imp_ExFreePoolWithTag
0x1401479f0  nop     dword ptr [rax+rax+00h]
0x1401479f5  mov     rcx, [rbp+pPackedContext.pvBuffer]; pvContextBuffer
0x1401479f9  test    rcx, rcx
0x1401479fc  jz      short loc_140147A0A
0x1401479fe  call    cs:__imp_FreeContextBuffer
0x140147a05  nop     dword ptr [rax+rax+00h]
0x140147a0a  mov     eax, esi
0x140147a0c  jmp     short loc_140147A6E
0x140147a0e  mov     rax, [rdi+38h]
0x140147a12  test    rax, rax
0x140147a15  jz      short loc_140147A2F
0x140147a17  mov     [rbx+58h], rax
0x140147a1b  mov     eax, [rdi+40h]
0x140147a1e  mov     [rbx+60h], eax
0x140147a21  mov     eax, [rdi+44h]
0x140147a24  mov     [rbx+64h], eax
0x140147a27  mov     [rdi+38h], r13
0x140147a2b  mov     [rdi+40h], r13
0x140147a2f  or      dword ptr [rbx], 1
0x140147a32  mov     rcx, [rbp+pBuffer]; pvContextBuffer
0x140147a36  mov     [rbx+10h], r13d
0x140147a3a  mov     [rbx+14h], esi
0x140147a3d  mov     eax, [rdi+18h]
0x140147a40  mov     [rbx+20h], eax
0x140147a43  mov     rax, [rbp+Token]
0x140147a47  mov     [rbx+18h], rax
0x140147a4b  movzx   eax, [rbp+DestinationString.Length]
0x140147a4f  mov     [rbx+50h], ax
0x140147a53  mov     [rbx+48h], r14
0x140147a57  call    cs:__imp_FreeContextBuffer
0x140147a5e  nop     dword ptr [rax+rax+00h]
0x140147a63  movups  xmm0, xmmword ptr [rbp+pPackedContext.cbBuffer]
0x140147a67  xor     eax, eax
0x140147a69  movdqu  xmmword ptr [rbx+38h], xmm0
0x140147a6e  mov     rbx, [rsp+70h+arg_0]
0x140147a76  add     rsp, 70h
0x140147a7a  pop     r15
0x140147a7c  pop     r14
0x140147a7e  pop     r13
0x140147a80  pop     r12
0x140147a82  pop     rdi
0x140147a83  pop     rsi
0x140147a84  pop     rbp
0x140147a85  retn
```
