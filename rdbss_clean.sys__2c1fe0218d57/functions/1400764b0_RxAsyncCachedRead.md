# RxAsyncCachedRead

- ea: `0x1400764b0`
- end: `0x14007674d`
- name: `RxAsyncCachedRead`
- size: `669`
- prototype: `__int64 __usercall@<rax>(PRX_CONTEXT RxContext@<rcx>, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x140066390`

## callees

- `0x140007f60`
- `0x1400104f0`
- `0x140010570`
- `0x140016e70`
- `0x140017370`
- `0x14001bea8`
- `0x1400764b0`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007656b`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007656b`
- `ntoskrnl!MmUnlockPages` at `0x14007661d`
- `ntoskrnl!MmUnlockPages` at `0x1400766d6`
- `ntoskrnl!MmUnlockPages` at `0x14007661d`
- `ntoskrnl!MmUnlockPages` at `0x1400766d6`
- `ntoskrnl!IoFreeMdl` at `0x14007662d`
- `ntoskrnl!IoFreeMdl` at `0x1400766e6`
- `ntoskrnl!IoFreeMdl` at `0x14007662d`
- `ntoskrnl!IoFreeMdl` at `0x1400766e6`
- `ntoskrnl!CcAsyncCopyRead` at `0x1400765ca`
- `ntoskrnl!CcAsyncCopyRead` at `0x1400765ca`

## pseudocode

```c
__int64 RxAsyncCachedRead(PRX_CONTEXT RxContext, _QWORD *a2, __int64 a3, ...)
{
  char *v6; // rsi
  __int64 v7; // rdx
  __int64 Mdl2; // rax
  __int64 v9; // rcx
  const CHAR *v10; // r14
  ULONG v11; // r9d
  __int64 v13; // rcx
  __int64 v15; // [rsp+98h] [rbp+20h] BYREF
  va_list va; // [rsp+98h] [rbp+20h]
  __int64 v17; // [rsp+A0h] [rbp+28h]
  va_list va1; // [rsp+A8h] [rbp+30h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v15 = va_arg(va1, _QWORD);
  v17 = va_arg(va1, _QWORD);
  v6 = (char *)&RxContext->9 + 136;
  v7 = a2[23];
  *(_OWORD *)((char *)&RxContext->9 + 136) = 0;
  *(_OWORD *)((char *)&RxContext->9 + 152) = 0;
  Mdl2 = a2[1];
  if ( !Mdl2 )
  {
    Mdl2 = RxAllocateMdl2(a2[14], *(_DWORD *)(v7 + 8), 0, 0, 0);
    if ( !Mdl2 )
      return 3221225626LL;
  }
  *((_QWORD *)v6 + 2) = Mdl2;
  *(_BYTE *)(a2[23] + 3LL) |= 1u;
  *(_QWORD *)v6 = RxAsyncCachedReadCompletion;
  *((_QWORD *)v6 + 1) = RxContext;
  *((_QWORD *)&RxContext->9 + 21) = (__int64)RxContext->RxDeviceObject | 3;
  RxSetFcbMainOwnerPointer(RxContext->pFcb);
  v9 = a2[1];
  if ( v9 )
  {
    if ( (*(_BYTE *)(v9 + 10) & 5) != 0 )
      v10 = *(const CHAR **)(v9 + 24);
    else
      v10 = (const CHAR *)MmMapLockedPagesSpecifyCache((PMDL)v9, 0, MmCached, 0, 0, 0x40000010u);
  }
  else
  {
    v10 = (const CHAR *)a2[14];
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 16, &WPP_ab807026a5683cdcaf6085912ea536d5_Traceguids, v10);
  }
  if ( (unsigned __int8)CcAsyncCopyRead(a3, (__int64 *)va, (unsigned int)v17, 0) )
  {
    return 259;
  }
  else
  {
    v13 = *((_QWORD *)v6 + 2);
    if ( v13 != a2[1] )
    {
      if ( (*(_BYTE *)(v13 + 10) & 2) != 0 )
        MmUnlockPages((PMDL)v13);
      IoFreeMdl(*((PMDL *)v6 + 2));
      *((_QWORD *)v6 + 2) = 0;
    }
    _RxReleaseFcbForThread(
      RxContext,
      RxContext->pFcb,
      *((_QWORD *)&RxContext->9 + 21),
      v11,
      v10,
      (_DWORD)RxContext + 176);
    return (unsigned int)-1069481981;
  }
}

```

## disassembly

```asm
0x1400764b0  mov     [rsp+arg_10], rbx
0x1400764b5  mov     [rsp+arg_18], r9
0x1400764ba  mov     [rsp+arg_8], rdx
0x1400764bf  mov     [rsp+RxContext], rcx
0x1400764c4  push    rsi
0x1400764c5  push    rdi
0x1400764c6  push    r12
0x1400764c8  push    r14
0x1400764ca  push    r15
0x1400764cc  sub     rsp, 50h
0x1400764d0  mov     r15, r8
0x1400764d3  mov     rbx, rdx
0x1400764d6  mov     rdi, rcx
0x1400764d9  lea     rsi, [rcx+218h]
0x1400764e0  mov     rdx, [rdx+0B8h]
0x1400764e7  xorps   xmm0, xmm0
0x1400764ea  movups  xmmword ptr [rsi], xmm0
0x1400764ed  movups  xmmword ptr [rsi+10h], xmm0
0x1400764f1  mov     rax, [rbx+8]
0x1400764f5  xor     r12d, r12d
0x1400764f8  test    rax, rax
0x1400764fb  jz      loc_140076726
0x140076501  mov     [rsp+78h+var_30], rsi
0x140076506  mov     [rsi+10h], rax
0x14007650a  mov     rax, [rbx+0B8h]
0x140076511  or      byte ptr [rax+3], 1
0x140076515  lea     rax, RxAsyncCachedReadCompletion
0x14007651c  mov     [rsi], rax
0x14007651f  mov     [rsi+8], rdi
0x140076523  mov     rdx, [rdi+58h]
0x140076527  or      rdx, 3
0x14007652b  mov     [rdi+238h], rdx
0x140076532  mov     rcx, [rdi+38h]
0x140076536  call    RxSetFcbMainOwnerPointer
0x14007653b  nop
0x14007653c  mov     rcx, [rbx+8]; MemoryDescriptorList
0x140076540  test    rcx, rcx
0x140076543  jz      loc_1400765E7
0x140076549  test    byte ptr [rcx+0Ah], 5
0x14007654d  jnz     loc_1400765E1
0x140076553  mov     [rsp+78h+Priority], 40000010h; Priority
0x14007655b  mov     [rsp+78h+BugCheckOnFailure], r12d; BugCheckOnFailure
0x140076560  xor     r9d, r9d; RequestedAddress
0x140076563  xor     edx, edx; AccessMode
0x140076565  mov     r8d, 1; CacheType
0x14007656b  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140076572  nop     dword ptr [rax+rax+00h]
0x140076577  mov     r14, rax
0x14007657a  lea     rax, WPP_GLOBAL_Control
0x140076581  mov     rcx, cs:WPP_GLOBAL_Control
0x140076588  cmp     rcx, rax
0x14007658b  jz      short loc_140076595
0x14007658d  mov     edx, [rcx+2Ch]
0x140076590  test    dl, 2
0x140076593  jnz     short loc_1400765ED
0x140076595  lea     rcx, [rdi+0B0h]
0x14007659c  mov     [rsp+78h+var_40], rsi
0x1400765a1  mov     rax, [rdi+58h]
0x1400765a5  mov     [rsp+78h+var_48], rax
0x1400765aa  mov     qword ptr [rsp+78h+Priority], rcx; SerialNumber
0x1400765af  mov     qword ptr [rsp+78h+BugCheckOnFailure], r14; FileName
0x1400765b4  xor     r9d, r9d
0x1400765b7  mov     r8d, dword ptr [rsp+78h+arg_20]
0x1400765bf  lea     rdx, [rsp+78h+arg_18]
0x1400765c7  mov     rcx, r15
0x1400765ca  call    cs:__imp_CcAsyncCopyRead
0x1400765d1  nop     dword ptr [rax+rax+00h]
0x1400765d6  test    al, al
0x1400765d8  jz      short loc_14007660D
0x1400765da  mov     ebx, 103h
0x1400765df  jmp     short loc_140076655
0x1400765e1  mov     r14, [rcx+18h]
0x1400765e5  jmp     short loc_14007657A
0x1400765e7  mov     r14, [rbx+70h]
0x1400765eb  jmp     short loc_14007657A
0x1400765ed  cmp     byte ptr [rcx+29h], 4
0x1400765f1  jb      short loc_140076595
0x1400765f3  mov     edx, 10h
0x1400765f8  mov     r9, r14
0x1400765fb  lea     r8, WPP_ab807026a5683cdcaf6085912ea536d5_Traceguids
0x140076602  mov     rcx, [rcx+18h]
0x140076606  call    WPP_SF_q
0x14007660b  jmp     short loc_140076595
0x14007660d  mov     rcx, [rsi+10h]; MemoryDescriptorList
0x140076611  cmp     rcx, [rbx+8]
0x140076615  jz      short loc_14007663D
0x140076617  test    byte ptr [rcx+0Ah], 2
0x14007661b  jz      short loc_140076629
0x14007661d  call    cs:__imp_MmUnlockPages
0x140076624  nop     dword ptr [rax+rax+00h]
0x140076629  mov     rcx, [rsi+10h]; Mdl
0x14007662d  call    cs:__imp_IoFreeMdl
0x140076634  nop     dword ptr [rax+rax+00h]
0x140076639  mov     [rsi+10h], r12
0x14007663d  mov     r8, [rdi+238h]; ResourceThreadId
0x140076644  mov     rdx, [rdi+38h]; MrxFcb
0x140076648  mov     rcx, rdi; RxContext
0x14007664b  call    __RxReleaseFcbForThread
0x140076650  mov     ebx, 0C0410003h
0x140076655  mov     [rsp+78h+var_38], ebx
0x140076659  jmp     loc_14007670E
0x14007665e  mov     ebx, eax
0x140076660  mov     [rsp+78h+var_38], eax
0x140076664  lea     rax, WPP_GLOBAL_Control
0x14007666b  mov     rcx, cs:WPP_GLOBAL_Control
0x140076672  cmp     rcx, rax
0x140076675  jz      short loc_1400766AA
0x140076677  mov     eax, [rcx+2Ch]
0x14007667a  test    al, 10h
0x14007667c  jz      short loc_1400766AA
0x14007667e  cmp     byte ptr [rcx+29h], 4
0x140076682  jb      short loc_1400766AA
0x140076684  mov     edx, 10h
0x140076689  mov     [rsp+78h+BugCheckOnFailure], ebx
0x14007668d  mov     rsi, [rsp+78h+RxContext]
0x140076695  mov     r9, rsi
0x140076698  lea     r8, WPP_eba0f78664123ae955be5a8e7a20cae6_Traceguids
0x14007669f  mov     rcx, [rcx+18h]
0x1400766a3  call    WPP_SF_qD
0x1400766a8  jmp     short loc_1400766B2
0x1400766aa  mov     rsi, [rsp+78h+RxContext]
0x1400766b2  mov     rax, [rsp+78h+arg_8]
0x1400766ba  mov     rcx, [rax+8]
0x1400766be  mov     rdi, [rsp+78h+var_30]
0x1400766c3  cmp     [rdi+10h], rcx
0x1400766c7  jz      short loc_1400766FA
0x1400766c9  mov     rax, [rdi+10h]
0x1400766cd  test    byte ptr [rax+0Ah], 2
0x1400766d1  jz      short loc_1400766E2
0x1400766d3  mov     rcx, rax; MemoryDescriptorList
0x1400766d6  call    cs:__imp_MmUnlockPages
0x1400766dd  nop     dword ptr [rax+rax+00h]
0x1400766e2  mov     rcx, [rdi+10h]; Mdl
0x1400766e6  call    cs:__imp_IoFreeMdl
0x1400766ed  nop     dword ptr [rax+rax+00h]
0x1400766f2  mov     qword ptr [rdi+10h], 0
0x1400766fa  mov     r8, [rsi+238h]; ResourceThreadId
0x140076701  mov     rdx, [rsi+38h]; MrxFcb
0x140076705  mov     rcx, rsi; RxContext
0x140076708  call    __RxReleaseFcbForThread
0x14007670d  nop
0x14007670e  mov     eax, ebx
0x140076710  mov     rbx, [rsp+78h+arg_10]
0x140076718  add     rsp, 50h
0x14007671c  pop     r15
0x14007671e  pop     r14
0x140076720  pop     r12
0x140076722  pop     rdi
0x140076723  pop     rsi
0x140076724  retn
0x140076726  mov     qword ptr [rsp+78h+BugCheckOnFailure], r12; PIRP
0x14007672b  xor     r9d, r9d; int
0x14007672e  xor     r8d, r8d; int
0x140076731  mov     edx, [rdx+8]; int
0x140076734  mov     rcx, [rbx+70h]; int
0x140076738  call    RxAllocateMdl2
0x14007673d  test    rax, rax
0x140076740  jnz     loc_140076501
0x140076746  mov     eax, 0C000009Ah
0x14007674b  jmp     short loc_140076710
0x14007b8e0  push    rbp
0x14007b8e2  sub     rsp, 40h
0x14007b8e6  mov     rbp, rdx
0x14007b8e9  mov     rdx, rcx; ExceptionPointer
0x14007b8ec  mov     rcx, [rbp+80h]; RxContext
0x14007b8f3  call    RxExceptionFilter
0x14007b8f8  nop
0x14007b8f9  add     rsp, 40h
0x14007b8fd  pop     rbp
0x14007b8fe  retn
```
