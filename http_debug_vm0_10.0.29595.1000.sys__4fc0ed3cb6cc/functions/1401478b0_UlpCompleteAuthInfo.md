# UlpCompleteAuthInfo

- ea: `0x1401478b0`
- end: `0x140147b77`
- name: `UlpCompleteAuthInfo`
- size: `711`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140148150`
- `0x140148540`
- `0x140149df0`

## callees

- `0x14014765c`
- `0x1401478b0`
- `0x140149cc0`
- `0x140167940`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140147970`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401479e5`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401479fc`
- `ntoskrnl!RtlInitUnicodeString` at `0x140147970`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401479e5`
- `ntoskrnl!RtlInitUnicodeString` at `0x1401479fc`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140147a13`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140147a34`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140147a13`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140147a34`
- `ntoskrnl!ZwClose` at `0x140147aae`
- `ntoskrnl!ZwClose` at `0x140147aae`
- `ntoskrnl!ExAllocatePool3` at `0x14014799e`
- `ntoskrnl!ExAllocatePool3` at `0x14014799e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140147ad9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140147ad9`
- `ksecdd!ExportSecurityContext` at `0x140147a62`
- `ksecdd!ExportSecurityContext` at `0x140147a62`
- `ksecdd!QueryContextAttributesW` at `0x140147949`
- `ksecdd!QueryContextAttributesW` at `0x140147949`
- `ksecdd!QuerySecurityContextToken` at `0x140147903`
- `ksecdd!QuerySecurityContextToken` at `0x140147903`
- `ksecdd!FreeContextBuffer` at `0x140147ac3`
- `ksecdd!FreeContextBuffer` at `0x140147aee`
- `ksecdd!FreeContextBuffer` at `0x140147b47`
- `ksecdd!FreeContextBuffer` at `0x140147ac3`
- `ksecdd!FreeContextBuffer` at `0x140147aee`
- `ksecdd!FreeContextBuffer` at `0x140147b47`

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
0x1401478b0  mov     [rsp-38h+arg_0], rbx
0x1401478b5  push    rbp
0x1401478b6  push    rsi
0x1401478b7  push    rdi
0x1401478b8  push    r12
0x1401478ba  push    r13
0x1401478bc  push    r14
0x1401478be  push    r15
0x1401478c0  mov     rbp, rsp
0x1401478c3  sub     rsp, 70h
0x1401478c7  xor     r13d, r13d
0x1401478ca  lea     r12, [rdx+8]
0x1401478ce  xorps   xmm0, xmm0
0x1401478d1  mov     qword ptr [rbp+pPackedContext.cbBuffer], r13
0x1401478d5  mov     rdi, rdx
0x1401478d8  mov     [rbp+Token], r13
0x1401478dc  mov     r15, rcx
0x1401478df  mov     [rbp+pBuffer], r13
0x1401478e3  xorps   xmm1, xmm1
0x1401478e6  mov     [rbp+pPackedContext.pvBuffer], r13
0x1401478ea  mov     rcx, r12; phContext
0x1401478ed  lea     rdx, [rbp+Token]; Token
0x1401478f1  mov     rbx, r8
0x1401478f4  mov     r14d, r13d
0x1401478f7  movups  xmmword ptr [rbp+String1.Length], xmm0
0x1401478fb  movups  xmmword ptr [rbp+var_10.Length], xmm1
0x1401478ff  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140147903  call    cs:__imp_QuerySecurityContextToken
0x14014790a  nop     dword ptr [rax+rax+00h]
0x14014790f  mov     esi, eax
0x140147911  test    eax, eax
0x140147913  jns     short loc_14014791E
0x140147915  mov     [rbp+Token], r13
0x140147919  jmp     loc_140147A98
0x14014791e  cmp     [r15+41Ch], r13b
0x140147925  jz      short loc_14014793D
0x140147927  lea     rdx, [rbp+Token]
0x14014792b  mov     rcx, r15
0x14014792e  call    UlpReplaceSystemAccessToken
0x140147933  mov     esi, eax
0x140147935  test    eax, eax
0x140147937  js      loc_140147A98
0x14014793d  lea     r8, [rbp+pBuffer]; pBuffer
0x140147941  mov     edx, 0Ah; ulAttribute
0x140147946  mov     rcx, r12; phContext
0x140147949  call    cs:__imp_QueryContextAttributesW
0x140147950  nop     dword ptr [rax+rax+00h]
0x140147955  mov     esi, eax
0x140147957  test    eax, eax
0x140147959  jns     short loc_140147964
0x14014795b  mov     [rbp+pBuffer], r13
0x14014795f  jmp     loc_140147A98
0x140147964  mov     rdx, [rbp+pBuffer]
0x140147968  lea     rcx, [rbp+DestinationString]; DestinationString
0x14014796c  mov     rdx, [rdx+10h]; SourceString
0x140147970  call    cs:__imp_RtlInitUnicodeString
0x140147977  nop     dword ptr [rax+rax+00h]
0x14014797c  movzx   edx, [rbp+DestinationString.Length]
0x140147980  lea     r9, UxLowPriorityPool
0x140147987  add     rdx, 2
0x14014798b  mov     [rsp+70h+var_50], 1
0x140147993  mov     ecx, 102h
0x140147998  mov     r8d, 54586C55h
0x14014799e  call    cs:__imp_ExAllocatePool3
0x1401479a5  nop     dword ptr [rax+rax+00h]
0x1401479aa  mov     r14, rax
0x1401479ad  test    rax, rax
0x1401479b0  jnz     short loc_1401479BC
0x1401479b2  mov     esi, 80090300h
0x1401479b7  jmp     loc_140147A98
0x1401479bc  movzx   r8d, [rbp+DestinationString.Length]
0x1401479c1  mov     rcx, r14; void *
0x1401479c4  mov     rdx, [rbp+DestinationString.Buffer]; Src
0x1401479c8  add     r8, 2; Size
0x1401479cc  call    memmove
0x1401479d1  mov     rax, [rdi]
0x1401479d4  cmp     [rax+6Bh], r13b
0x1401479d8  jz      short loc_140147A48
0x1401479da  mov     rdx, [r15+218h]; SourceString
0x1401479e1  lea     rcx, [rbp+String1]; DestinationString
0x1401479e5  call    cs:__imp_RtlInitUnicodeString
0x1401479ec  nop     dword ptr [rax+rax+00h]
0x1401479f1  mov     rdx, [r15+318h]; SourceString
0x1401479f8  lea     rcx, [rbp+var_10]; DestinationString
0x1401479fc  call    cs:__imp_RtlInitUnicodeString
0x140147a03  nop     dword ptr [rax+rax+00h]
0x140147a08  mov     r8b, 1; CaseInSensitive
0x140147a0b  lea     rdx, [rbp+DestinationString]; String2
0x140147a0f  lea     rcx, [rbp+String1]; String1
0x140147a13  call    cs:__imp_RtlEqualUnicodeString
0x140147a1a  nop     dword ptr [rax+rax+00h]
0x140147a1f  test    al, al
0x140147a21  jz      short loc_140147A29
0x140147a23  mov     byte ptr [rdi+1Dh], 1
0x140147a27  jmp     short loc_140147A48
0x140147a29  mov     r8b, 1; CaseInSensitive
0x140147a2c  lea     rdx, [rbp+DestinationString]; String2
0x140147a30  lea     rcx, [rbp+var_10]; String1
0x140147a34  call    cs:__imp_RtlEqualUnicodeString
0x140147a3b  nop     dword ptr [rax+rax+00h]
0x140147a40  test    al, al
0x140147a42  jz      short loc_140147A48
0x140147a44  mov     byte ptr [rdi+1Eh], 1
0x140147a48  mov     eax, [rbx]
0x140147a4a  test    al, 8
0x140147a4c  jz      short loc_140147A7A
0x140147a4e  mov     rax, [rdi]
0x140147a51  cmp     dword ptr [rax], 2
0x140147a54  jz      short loc_140147A7A
0x140147a56  xor     r9d, r9d; pToken
0x140147a59  lea     r8, [rbp+pPackedContext]; pPackedContext
0x140147a5d  xor     edx, edx; fFlags
0x140147a5f  mov     rcx, r12; phContext
0x140147a62  call    cs:__imp_ExportSecurityContext
0x140147a69  nop     dword ptr [rax+rax+00h]
0x140147a6e  mov     esi, eax
0x140147a70  test    eax, eax
0x140147a72  jns     short loc_140147A7A
0x140147a74  mov     [rbp+pPackedContext.pvBuffer], r13
0x140147a78  jmp     short loc_140147A98
0x140147a7a  mov     eax, [rbx+88h]
0x140147a80  test    al, 1
0x140147a82  jz      short loc_140147AFE
0x140147a84  mov     r8, rbx
0x140147a87  mov     rdx, rdi
0x140147a8a  mov     rcx, r15
0x140147a8d  call    UlpCheckAuthenticationSpn
0x140147a92  mov     esi, eax
0x140147a94  test    eax, eax
0x140147a96  jz      short loc_140147AFE
0x140147a98  or      dword ptr [rbx], 1
0x140147a9b  mov     rcx, [rbp+Token]; Handle
0x140147a9f  mov     dword ptr [rbx+10h], 2
0x140147aa6  mov     [rbx+14h], esi
0x140147aa9  test    rcx, rcx
0x140147aac  jz      short loc_140147ABA
0x140147aae  call    cs:__imp_ZwClose
0x140147ab5  nop     dword ptr [rax+rax+00h]
0x140147aba  mov     rcx, [rbp+pBuffer]; pvContextBuffer
0x140147abe  test    rcx, rcx
0x140147ac1  jz      short loc_140147ACF
0x140147ac3  call    cs:__imp_FreeContextBuffer
0x140147aca  nop     dword ptr [rax+rax+00h]
0x140147acf  test    r14, r14
0x140147ad2  jz      short loc_140147AE5
0x140147ad4  xor     edx, edx; Tag
0x140147ad6  mov     rcx, r14; P
0x140147ad9  call    cs:__imp_ExFreePoolWithTag
0x140147ae0  nop     dword ptr [rax+rax+00h]
0x140147ae5  mov     rcx, [rbp+pPackedContext.pvBuffer]; pvContextBuffer
0x140147ae9  test    rcx, rcx
0x140147aec  jz      short loc_140147AFA
0x140147aee  call    cs:__imp_FreeContextBuffer
0x140147af5  nop     dword ptr [rax+rax+00h]
0x140147afa  mov     eax, esi
0x140147afc  jmp     short loc_140147B5E
0x140147afe  mov     rax, [rdi+38h]
0x140147b02  test    rax, rax
0x140147b05  jz      short loc_140147B1F
0x140147b07  mov     [rbx+58h], rax
0x140147b0b  mov     eax, [rdi+40h]
0x140147b0e  mov     [rbx+60h], eax
0x140147b11  mov     eax, [rdi+44h]
0x140147b14  mov     [rbx+64h], eax
0x140147b17  mov     [rdi+38h], r13
0x140147b1b  mov     [rdi+40h], r13
0x140147b1f  or      dword ptr [rbx], 1
0x140147b22  mov     rcx, [rbp+pBuffer]; pvContextBuffer
0x140147b26  mov     [rbx+10h], r13d
0x140147b2a  mov     [rbx+14h], esi
0x140147b2d  mov     eax, [rdi+18h]
0x140147b30  mov     [rbx+20h], eax
0x140147b33  mov     rax, [rbp+Token]
0x140147b37  mov     [rbx+18h], rax
0x140147b3b  movzx   eax, [rbp+DestinationString.Length]
0x140147b3f  mov     [rbx+50h], ax
0x140147b43  mov     [rbx+48h], r14
0x140147b47  call    cs:__imp_FreeContextBuffer
0x140147b4e  nop     dword ptr [rax+rax+00h]
0x140147b53  movups  xmm0, xmmword ptr [rbp+pPackedContext.cbBuffer]
0x140147b57  xor     eax, eax
0x140147b59  movdqu  xmmword ptr [rbx+38h], xmm0
0x140147b5e  mov     rbx, [rsp+70h+arg_0]
0x140147b66  add     rsp, 70h
0x140147b6a  pop     r15
0x140147b6c  pop     r14
0x140147b6e  pop     r13
0x140147b70  pop     r12
0x140147b72  pop     rdi
0x140147b73  pop     rsi
0x140147b74  pop     rbp
0x140147b75  retn
```
