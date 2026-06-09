# UlpFastAuthenticate

- ea: `0x1c013b850`
- end: `0x1c013ba66`
- name: `UlpFastAuthenticate`
- size: `534`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1c001b640`
- `0x1c013b850`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x1c013b912`
- `ntoskrnl!RtlInitUnicodeString` at `0x1c013b912`
- `ntoskrnl!RtlMapSecurityErrorToNtStatus` at `0x1c013b9ea`
- `ntoskrnl!RtlMapSecurityErrorToNtStatus` at `0x1c013b9ea`
- `ntoskrnl!ZwClose` at `0x1c013b99c`
- `ntoskrnl!ZwClose` at `0x1c013b99c`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c013b933`
- `ntoskrnl!ExAllocatePoolWithTagPriority` at `0x1c013b933`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c013b9c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1c013b9c7`
- `ksecdd!FreeContextBuffer` at `0x1c013b9b1`
- `ksecdd!FreeContextBuffer` at `0x1c013b9dc`
- `ksecdd!FreeContextBuffer` at `0x1c013ba30`
- `ksecdd!FreeContextBuffer` at `0x1c013b9b1`
- `ksecdd!FreeContextBuffer` at `0x1c013b9dc`
- `ksecdd!FreeContextBuffer` at `0x1c013ba30`
- `ksecdd!ExportSecurityContext` at `0x1c013b979`
- `ksecdd!ExportSecurityContext` at `0x1c013b979`
- `ksecdd!QuerySecurityContextToken` at `0x1c013b8c4`
- `ksecdd!QuerySecurityContextToken` at `0x1c013b8c4`
- `ksecdd!QueryContextAttributesW` at `0x1c013b8eb`
- `ksecdd!QueryContextAttributesW` at `0x1c013b8eb`

## pseudocode

```c
__int64 __fastcall UlpFastAuthenticate(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 *v3; // rsi
  __int64 v4; // rbx
  void *v5; // r14
  __int64 v7; // rax
  __int64 v8; // rcx
  signed int v9; // edi
  PVOID PoolWithTagPriority; // rax
  struct _SecBuffer v11; // xmm0
  struct _SecBuffer pPackedContext; // [rsp+20h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-10h] BYREF
  PCWSTR *pBuffer; // [rsp+80h] [rbp+40h] BYREF
  void *Token; // [rsp+88h] [rbp+48h] BYREF

  v3 = (__int64 *)a3[1];
  v4 = *a3;
  *(_QWORD *)&pPackedContext.cbBuffer = 0;
  v5 = 0;
  DestinationString = 0;
  Token = 0;
  pBuffer = 0;
  pPackedContext.pvBuffer = 0;
  if ( v3[4] )
    return 259;
  v7 = *v3;
  v8 = *v3;
  if ( *v3 && *(_BYTE *)(v7 + 109) )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v7 - 12));
    v8 = *v3;
  }
  *(_QWORD *)(v4 + 8) = v8;
  v9 = QuerySecurityContextToken((PCtxtHandle)(v3 + 1), &Token);
  if ( v9 >= 0 )
  {
    v9 = QueryContextAttributesW((PCtxtHandle)(v3 + 1), 0xAu, &pBuffer);
    if ( v9 >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, pBuffer[2]);
      PoolWithTagPriority = ExAllocatePoolWithTagPriority(
                              PagedPool,
                              DestinationString.Length + 2LL,
                              0x54586C55u,
                              LowPoolPriority);
      v5 = PoolWithTagPriority;
      if ( PoolWithTagPriority )
      {
        memmove(PoolWithTagPriority, DestinationString.Buffer, DestinationString.Length + 2LL);
        if ( (*(_DWORD *)v4 & 8) == 0
          || (v9 = ExportSecurityContext((PCtxtHandle)(v3 + 1), 0, &pPackedContext, 0), v9 >= 0) )
        {
          *(_DWORD *)v4 |= 0x30u;
          *(_DWORD *)(v4 + 32) = *((_DWORD *)v3 + 6);
          *(_QWORD *)(v4 + 24) = Token;
          *(_QWORD *)(v4 + 72) = v5;
          *(_WORD *)(v4 + 80) = DestinationString.Length;
          FreeContextBuffer(pBuffer);
          v11 = pPackedContext;
          *(_QWORD *)(v4 + 16) = 0;
          *(struct _SecBuffer *)(v4 + 56) = v11;
          goto LABEL_27;
        }
        pPackedContext.pvBuffer = 0;
      }
      else
      {
        v9 = -2146893056;
      }
    }
    else
    {
      pBuffer = 0;
    }
    if ( Token )
      ZwClose(Token);
  }
  else
  {
    Token = 0;
  }
  if ( pBuffer )
    FreeContextBuffer(pBuffer);
  if ( v5 )
    ExFreePoolWithTag(v5, 0);
  if ( pPackedContext.pvBuffer )
    FreeContextBuffer(pPackedContext.pvBuffer);
  if ( RtlMapSecurityErrorToNtStatus(v9) == -1073741670 )
    return 3221225626LL;
  *(_DWORD *)(v4 + 16) = 2;
  *(_DWORD *)(v4 + 20) = v9;
LABEL_27:
  *(_DWORD *)v4 |= 1u;
  return 0;
}

```

## disassembly

```asm
0x1c013b850  mov     [rsp-28h+arg_0], rbx
0x1c013b855  mov     [rsp-28h+arg_8], rsi
0x1c013b85a  push    rbp
0x1c013b85b  push    rdi
0x1c013b85c  push    r12
0x1c013b85e  push    r14
0x1c013b860  push    r15
0x1c013b862  mov     rbp, rsp
0x1c013b865  sub     rsp, 40h
0x1c013b869  mov     rsi, [r8+8]
0x1c013b86d  xor     r12d, r12d
0x1c013b870  mov     rbx, [r8]
0x1c013b873  xorps   xmm0, xmm0
0x1c013b876  mov     qword ptr [rbp+pPackedContext.cbBuffer], r12
0x1c013b87a  mov     r14d, r12d
0x1c013b87d  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1c013b881  mov     [rbp+Token], r12
0x1c013b885  mov     [rbp+pBuffer], r12
0x1c013b889  mov     [rbp+pPackedContext.pvBuffer], r12
0x1c013b88d  cmp     [rsi+20h], r12
0x1c013b891  jz      short loc_1C013B89D
0x1c013b893  mov     eax, 103h
0x1c013b898  jmp     loc_1C013BA4E
0x1c013b89d  mov     rax, [rsi]
0x1c013b8a0  mov     rcx, rax
0x1c013b8a3  test    rax, rax
0x1c013b8a6  jz      short loc_1C013B8B5
0x1c013b8a8  cmp     [rax+6Dh], r12b
0x1c013b8ac  jz      short loc_1C013B8B5
0x1c013b8ae  lock inc dword ptr [rax-0Ch]
0x1c013b8b2  mov     rcx, [rsi]
0x1c013b8b5  mov     [rbx+8], rcx
0x1c013b8b9  lea     r15, [rsi+8]
0x1c013b8bd  mov     rcx, r15; phContext
0x1c013b8c0  lea     rdx, [rbp+Token]; Token
0x1c013b8c4  call    cs:__imp_QuerySecurityContextToken
0x1c013b8cb  nop     dword ptr [rax+rax+00h]
0x1c013b8d0  mov     edi, eax
0x1c013b8d2  test    eax, eax
0x1c013b8d4  jns     short loc_1C013B8DF
0x1c013b8d6  mov     [rbp+Token], r12
0x1c013b8da  jmp     loc_1C013B9A8
0x1c013b8df  lea     r8, [rbp+pBuffer]; pBuffer
0x1c013b8e3  mov     edx, 0Ah; ulAttribute
0x1c013b8e8  mov     rcx, r15; phContext
0x1c013b8eb  call    cs:__imp_QueryContextAttributesW
0x1c013b8f2  nop     dword ptr [rax+rax+00h]
0x1c013b8f7  mov     edi, eax
0x1c013b8f9  test    eax, eax
0x1c013b8fb  jns     short loc_1C013B906
0x1c013b8fd  mov     [rbp+pBuffer], r12
0x1c013b901  jmp     loc_1C013B993
0x1c013b906  mov     rdx, [rbp+pBuffer]
0x1c013b90a  lea     rcx, [rbp+DestinationString]; DestinationString
0x1c013b90e  mov     rdx, [rdx+10h]; SourceString
0x1c013b912  call    cs:__imp_RtlInitUnicodeString
0x1c013b919  nop     dword ptr [rax+rax+00h]
0x1c013b91e  movzx   edx, [rbp+DestinationString.Length]
0x1c013b922  xor     r9d, r9d; Priority
0x1c013b925  add     rdx, 2; NumberOfBytes
0x1c013b929  mov     r8d, 54586C55h; Tag
0x1c013b92f  lea     ecx, [r9+1]; PoolType
0x1c013b933  call    cs:__imp_ExAllocatePoolWithTagPriority
0x1c013b93a  nop     dword ptr [rax+rax+00h]
0x1c013b93f  mov     r14, rax
0x1c013b942  test    rax, rax
0x1c013b945  jnz     short loc_1C013B94E
0x1c013b947  mov     edi, 80090300h
0x1c013b94c  jmp     short loc_1C013B993
0x1c013b94e  movzx   r8d, [rbp+DestinationString.Length]
0x1c013b953  mov     rcx, r14; void *
0x1c013b956  mov     rdx, [rbp+DestinationString.Buffer]; Src
0x1c013b95a  add     r8, 2; Size
0x1c013b95e  call    memmove
0x1c013b963  mov     eax, [rbx]
0x1c013b965  test    al, 8
0x1c013b967  jz      loc_1C013BA0F
0x1c013b96d  xor     r9d, r9d; pToken
0x1c013b970  lea     r8, [rbp+pPackedContext]; pPackedContext
0x1c013b974  xor     edx, edx; fFlags
0x1c013b976  mov     rcx, r15; phContext
0x1c013b979  call    cs:__imp_ExportSecurityContext
0x1c013b980  nop     dword ptr [rax+rax+00h]
0x1c013b985  mov     edi, eax
0x1c013b987  test    eax, eax
0x1c013b989  jns     loc_1C013BA0F
0x1c013b98f  mov     [rbp+pPackedContext.pvBuffer], r12
0x1c013b993  mov     rcx, [rbp+Token]; Handle
0x1c013b997  test    rcx, rcx
0x1c013b99a  jz      short loc_1C013B9A8
0x1c013b99c  call    cs:__imp_ZwClose
0x1c013b9a3  nop     dword ptr [rax+rax+00h]
0x1c013b9a8  mov     rcx, [rbp+pBuffer]; pvContextBuffer
0x1c013b9ac  test    rcx, rcx
0x1c013b9af  jz      short loc_1C013B9BD
0x1c013b9b1  call    cs:__imp_FreeContextBuffer
0x1c013b9b8  nop     dword ptr [rax+rax+00h]
0x1c013b9bd  test    r14, r14
0x1c013b9c0  jz      short loc_1C013B9D3
0x1c013b9c2  xor     edx, edx; Tag
0x1c013b9c4  mov     rcx, r14; P
0x1c013b9c7  call    cs:__imp_ExFreePoolWithTag
0x1c013b9ce  nop     dword ptr [rax+rax+00h]
0x1c013b9d3  mov     rcx, [rbp+pPackedContext.pvBuffer]; pvContextBuffer
0x1c013b9d7  test    rcx, rcx
0x1c013b9da  jz      short loc_1C013B9E8
0x1c013b9dc  call    cs:__imp_FreeContextBuffer
0x1c013b9e3  nop     dword ptr [rax+rax+00h]
0x1c013b9e8  mov     ecx, edi; SecurityError
0x1c013b9ea  call    cs:__imp_RtlMapSecurityErrorToNtStatus
0x1c013b9f1  nop     dword ptr [rax+rax+00h]
0x1c013b9f6  mov     ecx, 0C000009Ah
0x1c013b9fb  cmp     eax, ecx
0x1c013b9fd  jnz     short loc_1C013BA03
0x1c013b9ff  mov     eax, ecx
0x1c013ba01  jmp     short loc_1C013BA4E
0x1c013ba03  mov     dword ptr [rbx+10h], 2
0x1c013ba0a  mov     [rbx+14h], edi
0x1c013ba0d  jmp     short loc_1C013BA49
0x1c013ba0f  or      dword ptr [rbx], 30h
0x1c013ba12  mov     eax, [rsi+18h]
0x1c013ba15  mov     [rbx+20h], eax
0x1c013ba18  mov     rax, [rbp+Token]
0x1c013ba1c  mov     [rbx+18h], rax
0x1c013ba20  mov     [rbx+48h], r14
0x1c013ba24  movzx   eax, [rbp+DestinationString.Length]
0x1c013ba28  mov     [rbx+50h], ax
0x1c013ba2c  mov     rcx, [rbp+pBuffer]; pvContextBuffer
0x1c013ba30  call    cs:__imp_FreeContextBuffer
0x1c013ba37  nop     dword ptr [rax+rax+00h]
0x1c013ba3c  movups  xmm0, xmmword ptr [rbp+pPackedContext.cbBuffer]
0x1c013ba40  mov     [rbx+10h], r12
0x1c013ba44  movdqu  xmmword ptr [rbx+38h], xmm0
0x1c013ba49  or      dword ptr [rbx], 1
0x1c013ba4c  xor     eax, eax
0x1c013ba4e  mov     rbx, [rsp+40h+arg_0]
0x1c013ba53  mov     rsi, [rsp+40h+arg_8]
0x1c013ba58  add     rsp, 40h
0x1c013ba5c  pop     r15
0x1c013ba5e  pop     r14
0x1c013ba60  pop     r12
0x1c013ba62  pop     rdi
0x1c013ba63  pop     rbp
0x1c013ba64  retn
```
