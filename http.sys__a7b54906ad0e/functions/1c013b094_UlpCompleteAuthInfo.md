# UlpCompleteAuthInfo

- ea: `0x1c013b094`
- end: `0x1c013b32f`
- name: `UlpCompleteAuthInfo`
- size: `667`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1c004c790`
- `0x1c004cb80`
- `0x1c013cbf0`

## callees

- `0x1c001b640`
- `0x1c013ae30`
- `0x1c013b094`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1c013b135`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c013b19d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c013b1b4`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c013b135`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c013b19d`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c013b1b4`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1c013b1cb`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1c013b1ec`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1c013b1cb`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1c013b1ec`
- `ntoskrnl!ZwClose` at `0x1c013b266`
- `ntoskrnl!ZwClose` at `0x1c013b266`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c013b156`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c013b156`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c013b291`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c013b291`
- `ksecdd!FreeContextBuffer` at `0x1c013b27b`
- `ksecdd!FreeContextBuffer` at `0x1c013b2a6`
- `ksecdd!FreeContextBuffer` at `0x1c013b2ff`
- `ksecdd!FreeContextBuffer` at `0x1c013b27b`
- `ksecdd!FreeContextBuffer` at `0x1c013b2a6`
- `ksecdd!FreeContextBuffer` at `0x1c013b2ff`
- `ksecdd!ExportSecurityContext` at `0x1c013b21a`
- `ksecdd!ExportSecurityContext` at `0x1c013b21a`
- `ksecdd!QuerySecurityContextToken` at `0x1c013b0e7`
- `ksecdd!QuerySecurityContextToken` at `0x1c013b0e7`
- `ksecdd!QueryContextAttributesW` at `0x1c013b10e`
- `ksecdd!QueryContextAttributesW` at `0x1c013b10e`

## pseudocode

```c
__int64 __fastcall UlpCompleteAuthInfo(__int64 a1, __int64 a2, __int64 a3)
{
  struct _SecHandle *v3; // r15
  void *v7; // r14
  SECURITY_STATUS v8; // esi
  PVOID PoolWithTagPriority; // rax
  void *v10; // rcx
  __int64 result; // rax
  __int64 v12; // rax
  PCWSTR *v13; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _SecBuffer pPackedContext; // [rsp+30h] [rbp-30h] BYREF
  UNICODE_STRING String1; // [rsp+40h] [rbp-20h] BYREF
  UNICODE_STRING v17; // [rsp+50h] [rbp-10h] BYREF
  PCWSTR *pBuffer; // [rsp+A8h] [rbp+48h] BYREF
  void *Token; // [rsp+B8h] [rbp+58h] BYREF

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
LABEL_18:
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
  v8 = QueryContextAttributesW(v3, 0xAu, &pBuffer);
  if ( v8 < 0 )
  {
    pBuffer = 0;
    goto LABEL_18;
  }
  RtlInitUnicodeString(&DestinationString, pBuffer[2]);
  PoolWithTagPriority = ExAllocatePoolWithTagPriority(
                          PagedPool,
                          DestinationString.Length + 2LL,
                          0x54586C55u,
                          LowPoolPriority);
  v7 = PoolWithTagPriority;
  if ( !PoolWithTagPriority )
  {
    v8 = -2146893056;
    goto LABEL_18;
  }
  memmove(PoolWithTagPriority, DestinationString.Buffer, DestinationString.Length + 2LL);
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
      goto LABEL_18;
    }
  }
  if ( (*(_DWORD *)(a3 + 136) & 1) != 0 )
  {
    v8 = UlpCheckAuthenticationSpn(a1, a2, a3);
    if ( v8 )
      goto LABEL_18;
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
0x1c013b094  mov     [rsp-38h+arg_0], rbx
0x1c013b099  push    rbp
0x1c013b09a  push    rsi
0x1c013b09b  push    rdi
0x1c013b09c  push    r12
0x1c013b09e  push    r13
0x1c013b0a0  push    r14
0x1c013b0a2  push    r15
0x1c013b0a4  mov     rbp, rsp
0x1c013b0a7  sub     rsp, 60h
0x1c013b0ab  xor     r12d, r12d
0x1c013b0ae  lea     r15, [rdx+8]
0x1c013b0b2  xorps   xmm0, xmm0
0x1c013b0b5  mov     qword ptr [rbp+pPackedContext.cbBuffer], r12
0x1c013b0b9  mov     rdi, rdx
0x1c013b0bc  mov     [rbp+Token], r12
0x1c013b0c0  mov     r13, rcx
0x1c013b0c3  mov     [rbp+pBuffer], r12
0x1c013b0c7  xorps   xmm1, xmm1
0x1c013b0ca  mov     [rbp+pPackedContext.pvBuffer], r12
0x1c013b0ce  mov     rcx, r15; phContext
0x1c013b0d1  lea     rdx, [rbp+Token]; Token
0x1c013b0d5  mov     rbx, r8
0x1c013b0d8  mov     r14d, r12d
0x1c013b0db  movups  xmmword ptr [rbp+String1.Length], xmm0
0x1c013b0df  movups  xmmword ptr [rbp+var_10.Length], xmm1
0x1c013b0e3  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1c013b0e7  call    cs:__imp_QuerySecurityContextToken
0x1c013b0ee  nop     dword ptr [rax+rax+00h]
0x1c013b0f3  mov     esi, eax
0x1c013b0f5  test    eax, eax
0x1c013b0f7  jns     short loc_1C013B102
0x1c013b0f9  mov     [rbp+Token], r12
0x1c013b0fd  jmp     loc_1C013B250
0x1c013b102  lea     r8, [rbp+pBuffer]; pBuffer
0x1c013b106  mov     edx, 0Ah; ulAttribute
0x1c013b10b  mov     rcx, r15; phContext
0x1c013b10e  call    cs:__imp_QueryContextAttributesW
0x1c013b115  nop     dword ptr [rax+rax+00h]
0x1c013b11a  mov     esi, eax
0x1c013b11c  test    eax, eax
0x1c013b11e  jns     short loc_1C013B129
0x1c013b120  mov     [rbp+pBuffer], r12
0x1c013b124  jmp     loc_1C013B250
0x1c013b129  mov     rdx, [rbp+pBuffer]
0x1c013b12d  lea     rcx, [rbp+DestinationString]; DestinationString
0x1c013b131  mov     rdx, [rdx+10h]; SourceString
0x1c013b135  call    cs:__imp_RtlInitUnicodeString
0x1c013b13c  nop     dword ptr [rax+rax+00h]
0x1c013b141  movzx   edx, [rbp+DestinationString.Length]
0x1c013b145  xor     r9d, r9d; Priority
0x1c013b148  add     rdx, 2; NumberOfBytes
0x1c013b14c  mov     r8d, 54586C55h; Tag
0x1c013b152  lea     ecx, [r9+1]; PoolType
0x1c013b156  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c013b15d  nop     dword ptr [rax+rax+00h]
0x1c013b162  mov     r14, rax
0x1c013b165  test    rax, rax
0x1c013b168  jnz     short loc_1C013B174
0x1c013b16a  mov     esi, 80090300h
0x1c013b16f  jmp     loc_1C013B250
0x1c013b174  movzx   r8d, [rbp+DestinationString.Length]
0x1c013b179  mov     rcx, r14; void *
0x1c013b17c  mov     rdx, [rbp+DestinationString.Buffer]; Src
0x1c013b180  add     r8, 2; Size
0x1c013b184  call    memmove
0x1c013b189  mov     rax, [rdi]
0x1c013b18c  cmp     [rax+6Bh], r12b
0x1c013b190  jz      short loc_1C013B200
0x1c013b192  mov     rdx, [r13+218h]; SourceString
0x1c013b199  lea     rcx, [rbp+String1]; DestinationString
0x1c013b19d  call    cs:__imp_RtlInitUnicodeString
0x1c013b1a4  nop     dword ptr [rax+rax+00h]
0x1c013b1a9  mov     rdx, [r13+318h]; SourceString
0x1c013b1b0  lea     rcx, [rbp+var_10]; DestinationString
0x1c013b1b4  call    cs:__imp_RtlInitUnicodeString
0x1c013b1bb  nop     dword ptr [rax+rax+00h]
0x1c013b1c0  mov     r8b, 1; CaseInSensitive
0x1c013b1c3  lea     rdx, [rbp+DestinationString]; String2
0x1c013b1c7  lea     rcx, [rbp+String1]; String1
0x1c013b1cb  call    cs:__imp_RtlEqualUnicodeString
0x1c013b1d2  nop     dword ptr [rax+rax+00h]
0x1c013b1d7  test    al, al
0x1c013b1d9  jz      short loc_1C013B1E1
0x1c013b1db  mov     byte ptr [rdi+1Dh], 1
0x1c013b1df  jmp     short loc_1C013B200
0x1c013b1e1  mov     r8b, 1; CaseInSensitive
0x1c013b1e4  lea     rdx, [rbp+DestinationString]; String2
0x1c013b1e8  lea     rcx, [rbp+var_10]; String1
0x1c013b1ec  call    cs:__imp_RtlEqualUnicodeString
0x1c013b1f3  nop     dword ptr [rax+rax+00h]
0x1c013b1f8  test    al, al
0x1c013b1fa  jz      short loc_1C013B200
0x1c013b1fc  mov     byte ptr [rdi+1Eh], 1
0x1c013b200  mov     eax, [rbx]
0x1c013b202  test    al, 8
0x1c013b204  jz      short loc_1C013B232
0x1c013b206  mov     rax, [rdi]
0x1c013b209  cmp     dword ptr [rax], 2
0x1c013b20c  jz      short loc_1C013B232
0x1c013b20e  xor     r9d, r9d; pToken
0x1c013b211  lea     r8, [rbp+pPackedContext]; pPackedContext
0x1c013b215  xor     edx, edx; fFlags
0x1c013b217  mov     rcx, r15; phContext
0x1c013b21a  call    cs:__imp_ExportSecurityContext
0x1c013b221  nop     dword ptr [rax+rax+00h]
0x1c013b226  mov     esi, eax
0x1c013b228  test    eax, eax
0x1c013b22a  jns     short loc_1C013B232
0x1c013b22c  mov     [rbp+pPackedContext.pvBuffer], r12
0x1c013b230  jmp     short loc_1C013B250
0x1c013b232  mov     eax, [rbx+88h]
0x1c013b238  test    al, 1
0x1c013b23a  jz      short loc_1C013B2B6
0x1c013b23c  mov     r8, rbx
0x1c013b23f  mov     rdx, rdi
0x1c013b242  mov     rcx, r13
0x1c013b245  call    UlpCheckAuthenticationSpn
0x1c013b24a  mov     esi, eax
0x1c013b24c  test    eax, eax
0x1c013b24e  jz      short loc_1C013B2B6
0x1c013b250  or      dword ptr [rbx], 1
0x1c013b253  mov     rcx, [rbp+Token]; Handle
0x1c013b257  mov     dword ptr [rbx+10h], 2
0x1c013b25e  mov     [rbx+14h], esi
0x1c013b261  test    rcx, rcx
0x1c013b264  jz      short loc_1C013B272
0x1c013b266  call    cs:__imp_ZwClose
0x1c013b26d  nop     dword ptr [rax+rax+00h]
0x1c013b272  mov     rcx, [rbp+pBuffer]; pvContextBuffer
0x1c013b276  test    rcx, rcx
0x1c013b279  jz      short loc_1C013B287
0x1c013b27b  call    cs:__imp_FreeContextBuffer
0x1c013b282  nop     dword ptr [rax+rax+00h]
0x1c013b287  test    r14, r14
0x1c013b28a  jz      short loc_1C013B29D
0x1c013b28c  xor     edx, edx; Tag
0x1c013b28e  mov     rcx, r14; P
0x1c013b291  call    cs:__imp_ExFreePoolWithTag
0x1c013b298  nop     dword ptr [rax+rax+00h]
0x1c013b29d  mov     rcx, [rbp+pPackedContext.pvBuffer]; pvContextBuffer
0x1c013b2a1  test    rcx, rcx
0x1c013b2a4  jz      short loc_1C013B2B2
0x1c013b2a6  call    cs:__imp_FreeContextBuffer
0x1c013b2ad  nop     dword ptr [rax+rax+00h]
0x1c013b2b2  mov     eax, esi
0x1c013b2b4  jmp     short loc_1C013B316
0x1c013b2b6  mov     rax, [rdi+38h]
0x1c013b2ba  test    rax, rax
0x1c013b2bd  jz      short loc_1C013B2D7
0x1c013b2bf  mov     [rbx+58h], rax
0x1c013b2c3  mov     eax, [rdi+40h]
0x1c013b2c6  mov     [rbx+60h], eax
0x1c013b2c9  mov     eax, [rdi+44h]
0x1c013b2cc  mov     [rbx+64h], eax
0x1c013b2cf  mov     [rdi+38h], r12
0x1c013b2d3  mov     [rdi+40h], r12
0x1c013b2d7  or      dword ptr [rbx], 1
0x1c013b2da  mov     rcx, [rbp+pBuffer]; pvContextBuffer
0x1c013b2de  mov     [rbx+10h], r12d
0x1c013b2e2  mov     [rbx+14h], esi
0x1c013b2e5  mov     eax, [rdi+18h]
0x1c013b2e8  mov     [rbx+20h], eax
0x1c013b2eb  mov     rax, [rbp+Token]
0x1c013b2ef  mov     [rbx+18h], rax
0x1c013b2f3  movzx   eax, [rbp+DestinationString.Length]
0x1c013b2f7  mov     [rbx+50h], ax
0x1c013b2fb  mov     [rbx+48h], r14
0x1c013b2ff  call    cs:__imp_FreeContextBuffer
0x1c013b306  nop     dword ptr [rax+rax+00h]
0x1c013b30b  movups  xmm0, xmmword ptr [rbp+pPackedContext.cbBuffer]
0x1c013b30f  xor     eax, eax
0x1c013b311  movdqu  xmmword ptr [rbx+38h], xmm0
0x1c013b316  mov     rbx, [rsp+60h+arg_0]
0x1c013b31e  add     rsp, 60h
0x1c013b322  pop     r15
0x1c013b324  pop     r14
0x1c013b326  pop     r13
0x1c013b328  pop     r12
0x1c013b32a  pop     rdi
0x1c013b32b  pop     rsi
0x1c013b32c  pop     rbp
0x1c013b32d  retn
```
