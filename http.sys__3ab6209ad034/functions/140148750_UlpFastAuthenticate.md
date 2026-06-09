# UlpFastAuthenticate

- ea: `0x140148750`
- end: `0x140148992`
- name: `UlpFastAuthenticate`
- size: `578`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x14000a350`
- `0x1400af74c`
- `0x140148750`
- `0x140167940`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x14014883a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14014883a`
- `ntoskrnl!ZwClose` at `0x1401488cd`
- `ntoskrnl!ZwClose` at `0x1401488cd`
- `ntoskrnl!ExAllocatePool3` at `0x140148868`
- `ntoskrnl!ExAllocatePool3` at `0x140148868`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401488f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x1401488f8`
- `ksecdd!ExportSecurityContext` at `0x1401488ae`
- `ksecdd!ExportSecurityContext` at `0x1401488ae`
- `ksecdd!QueryContextAttributesW` at `0x140148813`
- `ksecdd!QueryContextAttributesW` at `0x140148813`
- `ksecdd!QuerySecurityContextToken` at `0x1401487ec`
- `ksecdd!QuerySecurityContextToken` at `0x1401487ec`
- `ksecdd!FreeContextBuffer` at `0x1401488e2`
- `ksecdd!FreeContextBuffer` at `0x14014890d`
- `ksecdd!FreeContextBuffer` at `0x14014895a`
- `ksecdd!FreeContextBuffer` at `0x1401488e2`
- `ksecdd!FreeContextBuffer` at `0x14014890d`
- `ksecdd!FreeContextBuffer` at `0x14014895a`

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
0x140148750  mov     [rsp-28h+arg_0], rbx
0x140148755  mov     [rsp-28h+arg_8], rsi
0x14014875a  push    rbp
0x14014875b  push    rdi
0x14014875c  push    r12
0x14014875e  push    r14
0x140148760  push    r15
0x140148762  mov     rbp, rsp
0x140148765  sub     rsp, 50h
0x140148769  mov     rsi, [r8+8]
0x14014876d  xor     r12d, r12d
0x140148770  xorps   xmm0, xmm0
0x140148773  mov     qword ptr [rbp+pPackedContext.cbBuffer], r12
0x140148777  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14014877b  mov     [rbp+Token], r12
0x14014877f  mov     [rbp+pBuffer], r12
0x140148783  mov     [rbp+pPackedContext.pvBuffer], r12
0x140148787  cmp     [rsi+20h], r12
0x14014878b  jz      short loc_140148797
0x14014878d  mov     eax, 103h
0x140148792  jmp     loc_140148978
0x140148797  mov     rax, [rsi]
0x14014879a  mov     rbx, [r8]
0x14014879d  test    rax, rax
0x1401487a0  jz      short loc_1401487D7
0x1401487a2  cmp     [rax+6Dh], r12b
0x1401487a6  jz      short loc_1401487D7
0x1401487a8  lea     rdx, [rax-0Ch]; BugCheckParameter2
0x1401487ac  mov     eax, 1
0x1401487b1  lock xadd [rdx], eax
0x1401487b5  inc     eax
0x1401487b7  cmp     cs:UxDebugCheckRefcount, r12b
0x1401487be  jz      short loc_1401487D7
0x1401487c0  cmp     eax, 0FFFFFFFFh
0x1401487c3  jg      short loc_1401487D7
0x1401487c5  mov     ecx, 3; BugCheckParameter1
0x1401487ca  movsxd  r9, eax; BugCheckParameter4
0x1401487cd  lea     r8d, [rcx+1Dh]; BugCheckParameter3
0x1401487d1  call    UlBugCheckEx
0x1401487d7  mov     rax, [rsi]
0x1401487da  lea     r15, [rsi+8]
0x1401487de  mov     rcx, r15; phContext
0x1401487e1  mov     [rbx+8], rax
0x1401487e5  lea     rdx, [rbp+Token]; Token
0x1401487e9  mov     r14, r12
0x1401487ec  call    cs:__imp_QuerySecurityContextToken
0x1401487f3  nop     dword ptr [rax+rax+00h]
0x1401487f8  mov     edi, eax
0x1401487fa  test    eax, eax
0x1401487fc  jns     short loc_140148807
0x1401487fe  mov     [rbp+Token], r12
0x140148802  jmp     loc_1401488D9
0x140148807  lea     r8, [rbp+pBuffer]; pBuffer
0x14014880b  mov     edx, 0Ah; ulAttribute
0x140148810  mov     rcx, r15; phContext
0x140148813  call    cs:__imp_QueryContextAttributesW
0x14014881a  nop     dword ptr [rax+rax+00h]
0x14014881f  mov     edi, eax
0x140148821  test    eax, eax
0x140148823  jns     short loc_14014882E
0x140148825  mov     [rbp+pBuffer], r12
0x140148829  jmp     loc_1401488C4
0x14014882e  mov     rdx, [rbp+pBuffer]
0x140148832  lea     rcx, [rbp+DestinationString]; DestinationString
0x140148836  mov     rdx, [rdx+10h]; SourceString
0x14014883a  call    cs:__imp_RtlInitUnicodeString
0x140148841  nop     dword ptr [rax+rax+00h]
0x140148846  movzx   edx, [rbp+DestinationString.Length]
0x14014884a  lea     r9, UxLowPriorityPool
0x140148851  add     rdx, 2
0x140148855  mov     [rsp+50h+var_30], 1
0x14014885d  mov     ecx, 102h
0x140148862  mov     r8d, 54586C55h
0x140148868  call    cs:__imp_ExAllocatePool3
0x14014886f  nop     dword ptr [rax+rax+00h]
0x140148874  mov     r14, rax
0x140148877  test    rax, rax
0x14014887a  jnz     short loc_140148883
0x14014887c  mov     edi, 80090300h
0x140148881  jmp     short loc_1401488C4
0x140148883  movzx   r8d, [rbp+DestinationString.Length]
0x140148888  mov     rcx, r14; void *
0x14014888b  mov     rdx, [rbp+DestinationString.Buffer]; Src
0x14014888f  add     r8, 2; Size
0x140148893  call    memmove
0x140148898  mov     eax, [rbx]
0x14014889a  test    al, 8
0x14014889c  jz      loc_140148939
0x1401488a2  xor     r9d, r9d; pToken
0x1401488a5  lea     r8, [rbp+pPackedContext]; pPackedContext
0x1401488a9  xor     edx, edx; fFlags
0x1401488ab  mov     rcx, r15; phContext
0x1401488ae  call    cs:__imp_ExportSecurityContext
0x1401488b5  nop     dword ptr [rax+rax+00h]
0x1401488ba  mov     edi, eax
0x1401488bc  test    eax, eax
0x1401488be  jns     short loc_140148939
0x1401488c0  mov     [rbp+pPackedContext.pvBuffer], r12
0x1401488c4  mov     rcx, [rbp+Token]; Handle
0x1401488c8  test    rcx, rcx
0x1401488cb  jz      short loc_1401488D9
0x1401488cd  call    cs:__imp_ZwClose
0x1401488d4  nop     dword ptr [rax+rax+00h]
0x1401488d9  mov     rcx, [rbp+pBuffer]; pvContextBuffer
0x1401488dd  test    rcx, rcx
0x1401488e0  jz      short loc_1401488EE
0x1401488e2  call    cs:__imp_FreeContextBuffer
0x1401488e9  nop     dword ptr [rax+rax+00h]
0x1401488ee  test    r14, r14
0x1401488f1  jz      short loc_140148904
0x1401488f3  xor     edx, edx; Tag
0x1401488f5  mov     rcx, r14; P
0x1401488f8  call    cs:__imp_ExFreePoolWithTag
0x1401488ff  nop     dword ptr [rax+rax+00h]
0x140148904  mov     rcx, [rbp+pPackedContext.pvBuffer]; pvContextBuffer
0x140148908  test    rcx, rcx
0x14014890b  jz      short loc_140148919
0x14014890d  call    cs:__imp_FreeContextBuffer
0x140148914  nop     dword ptr [rax+rax+00h]
0x140148919  mov     ecx, edi
0x14014891b  call    UxSslMapSecurityStatusToNtStatus
0x140148920  mov     ecx, 0C000009Ah
0x140148925  cmp     eax, ecx
0x140148927  jnz     short loc_14014892D
0x140148929  mov     eax, ecx
0x14014892b  jmp     short loc_140148978
0x14014892d  mov     dword ptr [rbx+10h], 2
0x140148934  mov     [rbx+14h], edi
0x140148937  jmp     short loc_140148973
0x140148939  or      dword ptr [rbx], 30h
0x14014893c  mov     eax, [rsi+18h]
0x14014893f  mov     [rbx+20h], eax
0x140148942  mov     rax, [rbp+Token]
0x140148946  mov     [rbx+18h], rax
0x14014894a  mov     [rbx+48h], r14
0x14014894e  movzx   eax, [rbp+DestinationString.Length]
0x140148952  mov     [rbx+50h], ax
0x140148956  mov     rcx, [rbp+pBuffer]; pvContextBuffer
0x14014895a  call    cs:__imp_FreeContextBuffer
0x140148961  nop     dword ptr [rax+rax+00h]
0x140148966  movups  xmm0, xmmword ptr [rbp+pPackedContext.cbBuffer]
0x14014896a  mov     [rbx+10h], r12
0x14014896e  movdqu  xmmword ptr [rbx+38h], xmm0
0x140148973  or      dword ptr [rbx], 1
0x140148976  xor     eax, eax
0x140148978  lea     r11, [rsp+50h+var_s0]
0x14014897d  mov     rbx, [r11+30h]
0x140148981  mov     rsi, [r11+38h]
0x140148985  mov     rsp, r11
0x140148988  pop     r15
0x14014898a  pop     r14
0x14014898c  pop     r12
0x14014898e  pop     rdi
0x14014898f  pop     rbp
0x140148990  retn
```
