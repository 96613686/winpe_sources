# VmbusTlFulfillReceiveRequest

- ea: `0x1400034f4`
- end: `0x1400036c8`
- name: `VmbusTlFulfillReceiveRequest`
- size: `468`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000309c`

## callees

- `0x1400034f4`
- `0x140003a20`
- `0x140003c70`
- `0x14000975c`
- `0x140009c38`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003564`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140003564`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003636`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003636`
- `ntoskrnl!IofCompleteRequest` at `0x140003689`
- `ntoskrnl!IofCompleteRequest` at `0x140003689`

## string_xrefs

- `0x1400035f2`: `Endpoint read received bytes.`

## pseudocode

```c
__int64 __fastcall VmbusTlFulfillReceiveRequest(__int64 a1, __int64 a2)
{
  bool v2; // zf
  unsigned int v5; // ebx
  _QWORD *v6; // r14
  __int64 v7; // r8
  bool v8; // r13
  _QWORD *v9; // rdi
  unsigned __int64 v10; // rax
  __int64 v11; // r12
  __int64 v12; // r8
  __int64 v13; // rax
  __int64 v14; // rcx
  _QWORD v16[2]; // [rsp+30h] [rbp-10h] BYREF
  KIRQL NewIrql; // [rsp+80h] [rbp+40h]

  v2 = *(_QWORD *)(a2 + 24) == 0;
  v16[1] = v16;
  v16[0] = v16;
  if ( v2 )
  {
    v5 = -1073741300;
    if ( (unsigned int)dword_140013058 > 2 )
      HvsocketTraceEndpointError("VmbusTlFulfillReceiveRequest", 419, 3221225996LL, a1);
  }
  else
  {
    v5 = -1073741807;
  }
  v6 = (_QWORD *)(a1 + 832);
  NewIrql = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 848));
  v8 = *(_QWORD *)a2 == 0;
  while ( 1 )
  {
    v9 = (_QWORD *)*v6;
    if ( (_QWORD *)*v6 == v6 )
      break;
    if ( v5 == -1073741300 )
    {
      LOBYTE(v7) = v8;
      v9[9] = 0;
      VmbusTlpDeferReceiveCompletionList(v9 - 13, v16, v7);
    }
    else
    {
      v10 = *(_QWORD *)(a2 + 24);
      if ( v10 >= v9[9] )
        LODWORD(v10) = v9[9];
      v11 = (unsigned int)v10;
      VmbusTlReadWriteChainedMdl(*(_QWORD *)(a2 + 8), *(_DWORD *)(a2 + 16), v9[7], *((_DWORD *)v9 + 16), v10, 3);
      *(_QWORD *)(a2 + 64) += v11;
      *(_QWORD *)(a2 + 24) -= v11;
      *(_DWORD *)(a2 + 16) += v11;
      *((_DWORD *)v9 + 16) += v11;
      v9[9] -= v11;
      v9[10] += v11;
      if ( (unsigned int)dword_140013058 > 4 )
        HvsocketTraceEndpointUlongMessage("Endpoint read received bytes.", a1, (unsigned int)v11);
      LOBYTE(v12) = v8;
      VmbusTlpDeferReceiveCompletionList(v9 - 13, v16, v12);
      if ( !*(_QWORD *)(a2 + 24) )
        break;
    }
  }
  if ( (_QWORD *)*v6 != v6 && v5 != -1073741300 )
    v5 = 0;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 848), NewIrql);
  while ( 1 )
  {
    v13 = v16[0];
    v14 = *(_QWORD *)v16[0];
    if ( *(_QWORD **)(v16[0] + 8LL) != v16 || *(_QWORD *)(v14 + 8) != v16[0] )
      __fastfail(3u);
    v16[0] = *(_QWORD *)v16[0];
    *(_QWORD *)(v14 + 8) = v16;
    if ( (_QWORD *)v13 == v16 )
      break;
    *(_QWORD *)(v13 + 8) = v13;
    *(_QWORD *)v13 = v13;
    IofCompleteRequest(*(PIRP *)(v13 + 120), 0);
  }
  return v5;
}

```

## disassembly

```asm
0x1400034f4  mov     [rsp-38h+arg_10], rbx
0x1400034f9  push    rbp
0x1400034fa  push    rsi
0x1400034fb  push    rdi
0x1400034fc  push    r12
0x1400034fe  push    r13
0x140003500  push    r14
0x140003502  push    r15
0x140003504  mov     rbp, rsp
0x140003507  sub     rsp, 40h
0x14000350b  cmp     qword ptr [rdx+18h], 0
0x140003510  lea     rax, [rbp+var_10]
0x140003514  mov     [rbp+var_8], rax
0x140003518  mov     rsi, rdx
0x14000351b  lea     rax, [rbp+var_10]
0x14000351f  mov     r15, rcx
0x140003522  mov     [rbp+var_10], rax
0x140003526  jnz     short loc_140003551
0x140003528  mov     eax, cs:dword_140013058
0x14000352e  mov     ebx, 0C000020Ch
0x140003533  cmp     eax, 2
0x140003536  jbe     short loc_140003556
0x140003538  mov     r9, rcx
0x14000353b  mov     edx, 1A3h
0x140003540  lea     rcx, aVmbustlfulfill; "VmbusTlFulfillReceiveRequest"
0x140003547  mov     r8d, ebx
0x14000354a  call    HvsocketTraceEndpointError
0x14000354f  jmp     short loc_140003556
0x140003551  mov     ebx, 0C0000011h
0x140003556  lea     r13, [r15+350h]
0x14000355d  mov     rcx, r13; SpinLock
0x140003560  mov     [rbp+SpinLock], r13
0x140003564  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000356b  nop     dword ptr [rax+rax+00h]
0x140003570  cmp     qword ptr [rsi], 0
0x140003574  lea     r14, [r15+340h]
0x14000357b  mov     [rbp+NewIrql], al
0x14000357e  setz    r13b
0x140003582  mov     rdi, [r14]
0x140003585  cmp     rdi, r14
0x140003588  jz      loc_14000361C
0x14000358e  cmp     ebx, 0C000020Ch
0x140003594  jz      loc_140003644
0x14000359a  mov     rcx, [rdi+48h]
0x14000359e  mov     rax, [rsi+18h]
0x1400035a2  mov     r9d, [rdi+40h]
0x1400035a6  cmp     rax, rcx
0x1400035a9  mov     r8, [rdi+38h]
0x1400035ad  mov     edx, [rsi+10h]
0x1400035b0  cmovnb  eax, ecx
0x1400035b3  mov     rcx, [rsi+8]
0x1400035b7  mov     r12d, eax
0x1400035ba  mov     [rsp+40h+var_18], 3
0x1400035c2  mov     [rsp+40h+var_20], r12d
0x1400035c7  call    VmbusTlReadWriteChainedMdl
0x1400035cc  add     [rsi+40h], r12
0x1400035d0  sub     [rsi+18h], r12
0x1400035d4  add     [rsi+10h], r12d
0x1400035d8  add     [rdi+40h], r12d
0x1400035dc  sub     [rdi+48h], r12
0x1400035e0  add     [rdi+50h], r12
0x1400035e4  mov     eax, cs:dword_140013058
0x1400035ea  cmp     eax, 4
0x1400035ed  jbe     short loc_140003601
0x1400035ef  mov     r8d, r12d
0x1400035f2  lea     rcx, aEndpointReadRe; "Endpoint read received bytes."
0x1400035f9  mov     rdx, r15
0x1400035fc  call    HvsocketTraceEndpointUlongMessage
0x140003601  mov     r8b, r13b
0x140003604  lea     rdx, [rbp+var_10]
0x140003608  lea     rcx, [rdi-68h]
0x14000360c  call    VmbusTlpDeferReceiveCompletionList
0x140003611  cmp     qword ptr [rsi+18h], 0
0x140003616  jnz     loc_140003582
0x14000361c  mov     r13, [rbp+SpinLock]
0x140003620  cmp     [r14], r14
0x140003623  jz      short loc_140003630
0x140003625  xor     eax, eax
0x140003627  cmp     ebx, 0C000020Ch
0x14000362d  cmovnz  ebx, eax
0x140003630  mov     dl, [rbp+NewIrql]; NewIrql
0x140003633  mov     rcx, r13; SpinLock
0x140003636  call    cs:__imp_KeReleaseSpinLock
0x14000363d  nop     dword ptr [rax+rax+00h]
0x140003642  jmp     short loc_140003695
0x140003644  mov     r8b, r13b
0x140003647  mov     qword ptr [rdi+48h], 0
0x14000364f  lea     rdx, [rbp+var_10]
0x140003653  lea     rcx, [rdi-68h]
0x140003657  call    VmbusTlpDeferReceiveCompletionList
0x14000365c  jmp     loc_140003582
0x140003661  cmp     [rcx+8], rax
0x140003665  jnz     short loc_1400036A6
0x140003667  mov     [rbp+var_10], rcx
0x14000366b  lea     rdx, [rbp+var_10]
0x14000366f  mov     [rcx+8], rdx
0x140003673  lea     rcx, [rbp+var_10]
0x140003677  cmp     rax, rcx
0x14000367a  jz      short loc_1400036AD
0x14000367c  mov     [rax+8], rax
0x140003680  xor     edx, edx; PriorityBoost
0x140003682  mov     [rax], rax
0x140003685  mov     rcx, [rax+78h]; Irp
0x140003689  call    cs:__imp_IofCompleteRequest
0x140003690  nop     dword ptr [rax+rax+00h]
0x140003695  mov     rax, [rbp+var_10]
0x140003699  lea     rdx, [rbp+var_10]
0x14000369d  mov     rcx, [rax]
0x1400036a0  cmp     [rax+8], rdx
0x1400036a4  jz      short loc_140003661
0x1400036a6  mov     ecx, 3
0x1400036ab  int     29h; Win8: RtlFailFast(ecx)
0x1400036ad  mov     eax, ebx
0x1400036af  mov     rbx, [rsp+40h+arg_10]
0x1400036b7  add     rsp, 40h
0x1400036bb  pop     r15
0x1400036bd  pop     r14
0x1400036bf  pop     r13
0x1400036c1  pop     r12
0x1400036c3  pop     rdi
0x1400036c4  pop     rsi
0x1400036c5  pop     rbp
0x1400036c6  retn
```
