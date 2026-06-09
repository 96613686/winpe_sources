# UlpFastAuthenticate

- ea: `0x140148660`
- end: `0x1401488a2`
- name: `UlpFastAuthenticate`
- size: `578`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14000a350`
- `0x1400af82c`
- `0x140148660`
- `0x140167840`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14014874a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14014874a`
- `ntoskrnl!ZwClose` at `0x1401487dd`
- `ntoskrnl!ZwClose` at `0x1401487dd`
- `ntoskrnl!ExAllocatePool3` at `0x140148778`
- `ntoskrnl!ExAllocatePool3` at `0x140148778`
- `ntoskrnl!ExFreePoolWithTag` at `0x140148808`
- `ntoskrnl!ExFreePoolWithTag` at `0x140148808`
- `ksecdd!ExportSecurityContext` at `0x1401487be`
- `ksecdd!ExportSecurityContext` at `0x1401487be`
- `ksecdd!QueryContextAttributesW` at `0x140148723`
- `ksecdd!QueryContextAttributesW` at `0x140148723`
- `ksecdd!QuerySecurityContextToken` at `0x1401486fc`
- `ksecdd!QuerySecurityContextToken` at `0x1401486fc`
- `ksecdd!FreeContextBuffer` at `0x1401487f2`
- `ksecdd!FreeContextBuffer` at `0x14014881d`
- `ksecdd!FreeContextBuffer` at `0x14014886a`
- `ksecdd!FreeContextBuffer` at `0x1401487f2`
- `ksecdd!FreeContextBuffer` at `0x14014881d`
- `ksecdd!FreeContextBuffer` at `0x14014886a`

## pseudocode

```c
__int64 __fastcall UlpFastAuthenticate(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 *v3; // rsi
  __int64 v5; // rax
  __int64 v6; // rbx
  ULONG_PTR v7; // rdx
  int v8; // eax
  void *v9; // r14
  SECURITY_STATUS v10; // edi
  void *Pool3; // rax
  struct _SecBuffer v12; // xmm0
  struct _SecBuffer pPackedContext; // [rsp+30h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-10h] BYREF
  PCWSTR *pBuffer; // [rsp+90h] [rbp+40h] BYREF
  void *Token; // [rsp+98h] [rbp+48h] BYREF

  v3 = (__int64 *)a3[1];
  *(_QWORD *)&pPackedContext.cbBuffer = 0;
  DestinationString = 0;
  Token = 0;
  pBuffer = 0;
  pPackedContext.pvBuffer = 0;
  if ( v3[4] )
    return 259;
  v5 = *v3;
  v6 = *a3;
  if ( *v3 )
  {
    if ( *(_BYTE *)(v5 + 109) )
    {
      v7 = v5 - 12;
      v8 = _InterlockedIncrement((volatile signed __int32 *)(v5 - 12));
      if ( UxDebugCheckRefcount )
      {
        if ( v8 <= -1 )
          UlBugCheckEx(3u, v7, 0x20u, v8);
      }
    }
  }
  *(_QWORD *)(v6 + 8) = *v3;
  v9 = 0;
  v10 = QuerySecurityContextToken((PCtxtHandle)(v3 + 1), &Token);
  if ( v10 >= 0 )
  {
    v10 = QueryContextAttributesW((PCtxtHandle)(v3 + 1), 0xAu, &pBuffer);
    if ( v10 >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, pBuffer[2]);
      Pool3 = (void *)ExAllocatePool3(258, DestinationString.Length + 2LL, 1415081045, UxLowPriorityPool, 1);
      v9 = Pool3;
      if ( Pool3 )
      {
        memmove(Pool3, DestinationString.Buffer, DestinationString.Length + 2LL);
        if ( (*(_DWORD *)v6 & 8) == 0
          || (v10 = ExportSecurityContext((PCtxtHandle)(v3 + 1), 0, &pPackedContext, 0), v10 >= 0) )
        {
          *(_DWORD *)v6 |= 0x30u;
          *(_DWORD *)(v6 + 32) = *((_DWORD *)v3 + 6);
          *(_QWORD *)(v6 + 24) = Token;
          *(_QWORD *)(v6 + 72) = v9;
          *(_WORD *)(v6 + 80) = DestinationString.Length;
          FreeContextBuffer(pBuffer);
          v12 = pPackedContext;
          *(_QWORD *)(v6 + 16) = 0;
          *(struct _SecBuffer *)(v6 + 56) = v12;
          goto LABEL_29;
        }
        pPackedContext.pvBuffer = 0;
      }
      else
      {
        v10 = -2146893056;
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
  if ( v9 )
    ExFreePoolWithTag(v9, 0);
  if ( pPackedContext.pvBuffer )
    FreeContextBuffer(pPackedContext.pvBuffer);
  if ( (unsigned int)UxSslMapSecurityStatusToNtStatus((unsigned int)v10) == -1073741670 )
    return 3221225626LL;
  *(_DWORD *)(v6 + 16) = 2;
  *(_DWORD *)(v6 + 20) = v10;
LABEL_29:
  *(_DWORD *)v6 |= 1u;
  return 0;
}

```

## disassembly

```asm
0x140148660  mov     [rsp-28h+arg_0], rbx
0x140148665  mov     [rsp-28h+arg_8], rsi
0x14014866a  push    rbp
0x14014866b  push    rdi
0x14014866c  push    r12
0x14014866e  push    r14
0x140148670  push    r15
0x140148672  mov     rbp, rsp
0x140148675  sub     rsp, 50h
0x140148679  mov     rsi, [r8+8]
0x14014867d  xor     r12d, r12d
0x140148680  xorps   xmm0, xmm0
0x140148683  mov     qword ptr [rbp+pPackedContext.cbBuffer], r12
0x140148687  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14014868b  mov     [rbp+Token], r12
0x14014868f  mov     [rbp+pBuffer], r12
0x140148693  mov     [rbp+pPackedContext.pvBuffer], r12
0x140148697  cmp     [rsi+20h], r12
0x14014869b  jz      short loc_1401486A7
0x14014869d  mov     eax, 103h
0x1401486a2  jmp     loc_140148888
0x1401486a7  mov     rax, [rsi]
0x1401486aa  mov     rbx, [r8]
0x1401486ad  test    rax, rax
0x1401486b0  jz      short loc_1401486E7
0x1401486b2  cmp     [rax+6Dh], r12b
0x1401486b6  jz      short loc_1401486E7
0x1401486b8  lea     rdx, [rax-0Ch]; BugCheckParameter2
0x1401486bc  mov     eax, 1
0x1401486c1  lock xadd [rdx], eax
0x1401486c5  inc     eax
0x1401486c7  cmp     cs:UxDebugCheckRefcount, r12b
0x1401486ce  jz      short loc_1401486E7
0x1401486d0  cmp     eax, 0FFFFFFFFh
0x1401486d3  jg      short loc_1401486E7
0x1401486d5  mov     ecx, 3; BugCheckParameter1
0x1401486da  movsxd  r9, eax; BugCheckParameter4
0x1401486dd  lea     r8d, [rcx+1Dh]; BugCheckParameter3
0x1401486e1  call    UlBugCheckEx
0x1401486e7  mov     rax, [rsi]
0x1401486ea  lea     r15, [rsi+8]
0x1401486ee  mov     rcx, r15; phContext
0x1401486f1  mov     [rbx+8], rax
0x1401486f5  lea     rdx, [rbp+Token]; Token
0x1401486f9  mov     r14, r12
0x1401486fc  call    cs:__imp_QuerySecurityContextToken
0x140148703  nop     dword ptr [rax+rax+00h]
0x140148708  mov     edi, eax
0x14014870a  test    eax, eax
0x14014870c  jns     short loc_140148717
0x14014870e  mov     [rbp+Token], r12
0x140148712  jmp     loc_1401487E9
0x140148717  lea     r8, [rbp+pBuffer]; pBuffer
0x14014871b  mov     edx, 0Ah; ulAttribute
0x140148720  mov     rcx, r15; phContext
0x140148723  call    cs:__imp_QueryContextAttributesW
0x14014872a  nop     dword ptr [rax+rax+00h]
0x14014872f  mov     edi, eax
0x140148731  test    eax, eax
0x140148733  jns     short loc_14014873E
0x140148735  mov     [rbp+pBuffer], r12
0x140148739  jmp     loc_1401487D4
0x14014873e  mov     rdx, [rbp+pBuffer]
0x140148742  lea     rcx, [rbp+DestinationString]; DestinationString
0x140148746  mov     rdx, [rdx+10h]; SourceString
0x14014874a  call    cs:__imp_RtlInitUnicodeString
0x140148751  nop     dword ptr [rax+rax+00h]
0x140148756  movzx   edx, [rbp+DestinationString.Length]
0x14014875a  lea     r9, UxLowPriorityPool
0x140148761  add     rdx, 2
0x140148765  mov     [rsp+50h+var_30], 1
0x14014876d  mov     ecx, 102h
0x140148772  mov     r8d, 54586C55h
0x140148778  call    cs:__imp_ExAllocatePool3
0x14014877f  nop     dword ptr [rax+rax+00h]
0x140148784  mov     r14, rax
0x140148787  test    rax, rax
0x14014878a  jnz     short loc_140148793
0x14014878c  mov     edi, 80090300h
0x140148791  jmp     short loc_1401487D4
0x140148793  movzx   r8d, [rbp+DestinationString.Length]
0x140148798  mov     rcx, r14; void *
0x14014879b  mov     rdx, [rbp+DestinationString.Buffer]; Src
0x14014879f  add     r8, 2; Size
0x1401487a3  call    memmove
0x1401487a8  mov     eax, [rbx]
0x1401487aa  test    al, 8
0x1401487ac  jz      loc_140148849
0x1401487b2  xor     r9d, r9d; pToken
0x1401487b5  lea     r8, [rbp+pPackedContext]; pPackedContext
0x1401487b9  xor     edx, edx; fFlags
0x1401487bb  mov     rcx, r15; phContext
0x1401487be  call    cs:__imp_ExportSecurityContext
0x1401487c5  nop     dword ptr [rax+rax+00h]
0x1401487ca  mov     edi, eax
0x1401487cc  test    eax, eax
0x1401487ce  jns     short loc_140148849
0x1401487d0  mov     [rbp+pPackedContext.pvBuffer], r12
0x1401487d4  mov     rcx, [rbp+Token]; Handle
0x1401487d8  test    rcx, rcx
0x1401487db  jz      short loc_1401487E9
0x1401487dd  call    cs:__imp_ZwClose
0x1401487e4  nop     dword ptr [rax+rax+00h]
0x1401487e9  mov     rcx, [rbp+pBuffer]; pvContextBuffer
0x1401487ed  test    rcx, rcx
0x1401487f0  jz      short loc_1401487FE
0x1401487f2  call    cs:__imp_FreeContextBuffer
0x1401487f9  nop     dword ptr [rax+rax+00h]
0x1401487fe  test    r14, r14
0x140148801  jz      short loc_140148814
0x140148803  xor     edx, edx; Tag
0x140148805  mov     rcx, r14; P
0x140148808  call    cs:__imp_ExFreePoolWithTag
0x14014880f  nop     dword ptr [rax+rax+00h]
0x140148814  mov     rcx, [rbp+pPackedContext.pvBuffer]; pvContextBuffer
0x140148818  test    rcx, rcx
0x14014881b  jz      short loc_140148829
0x14014881d  call    cs:__imp_FreeContextBuffer
0x140148824  nop     dword ptr [rax+rax+00h]
0x140148829  mov     ecx, edi
0x14014882b  call    UxSslMapSecurityStatusToNtStatus
0x140148830  mov     ecx, 0C000009Ah
0x140148835  cmp     eax, ecx
0x140148837  jnz     short loc_14014883D
0x140148839  mov     eax, ecx
0x14014883b  jmp     short loc_140148888
0x14014883d  mov     dword ptr [rbx+10h], 2
0x140148844  mov     [rbx+14h], edi
0x140148847  jmp     short loc_140148883
0x140148849  or      dword ptr [rbx], 30h
0x14014884c  mov     eax, [rsi+18h]
0x14014884f  mov     [rbx+20h], eax
0x140148852  mov     rax, [rbp+Token]
0x140148856  mov     [rbx+18h], rax
0x14014885a  mov     [rbx+48h], r14
0x14014885e  movzx   eax, [rbp+DestinationString.Length]
0x140148862  mov     [rbx+50h], ax
0x140148866  mov     rcx, [rbp+pBuffer]; pvContextBuffer
0x14014886a  call    cs:__imp_FreeContextBuffer
0x140148871  nop     dword ptr [rax+rax+00h]
0x140148876  movups  xmm0, xmmword ptr [rbp+pPackedContext.cbBuffer]
0x14014887a  mov     [rbx+10h], r12
0x14014887e  movdqu  xmmword ptr [rbx+38h], xmm0
0x140148883  or      dword ptr [rbx], 1
0x140148886  xor     eax, eax
0x140148888  lea     r11, [rsp+50h+var_s0]
0x14014888d  mov     rbx, [r11+30h]
0x140148891  mov     rsi, [r11+38h]
0x140148895  mov     rsp, r11
0x140148898  pop     r15
0x14014889a  pop     r14
0x14014889c  pop     r12
0x14014889e  pop     rdi
0x14014889f  pop     rbp
0x1401488a0  retn
```
