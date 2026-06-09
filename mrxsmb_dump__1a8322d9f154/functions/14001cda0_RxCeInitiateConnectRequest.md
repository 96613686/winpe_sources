# RxCeInitiateConnectRequest

- ea: `0x14001cda0`
- end: `0x14001cf66`
- name: `RxCeInitiateConnectRequest`
- size: `454`
- prototype: `NTSTATUS __stdcall(PRX_CALLOUT_PARAMETERS_BLOCK ParameterBlock)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x14001cda0`
- `0x14001cf70`
- `0x14001d570`
- `0x14003e14c`
- `0x140053a6c`
- `0x140055440`
- `0x1400573b4`
- `0x14008b648`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001cdba`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001cdba`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14001cf46`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14001cf46`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14001cefd`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14001cefd`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001cdd4`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001cdd4`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14001ce43`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14001ce43`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14001ce00`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14001ce00`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ce0f`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14001ce0f`
- `rdbss!RxDereferenceSiloAndReleaseRundown` at `0x14001cf55`
- `rdbss!RxDereferenceSiloAndReleaseRundown` at `0x14001cf55`
- `rdbss!RxReferenceSiloAndAcquireRundown` at `0x14001cee5`
- `rdbss!RxReferenceSiloAndAcquireRundown` at `0x14001cee5`

## pseudocode

```c
NTSTATUS __stdcall RxCeInitiateConnectRequest(PRX_CALLOUT_PARAMETERS_BLOCK ParameterBlock)
{
  __int64 v1; // rsi
  KIRQL v3; // al
  char v4; // bl
  __int64 v5; // r14
  __int64 v6; // r12
  __int64 v7; // r15
  __int64 v8; // rbx
  KIRQL v9; // di
  __int32 v10; // ebx
  __int64 v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rcx
  int v16; // ecx
  NTSTATUS v17; // eax
  NTSTATUS v18; // ebx
  __int64 v20; // rax
  int v21; // ecx
  int v22; // ecx

  v1 = *((_QWORD *)ParameterBlock + 1);
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 8));
  v4 = *(_BYTE *)(v1 + 188);
  KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 8), v3);
  if ( v4 )
    goto LABEL_13;
  v5 = *((_QWORD *)ParameterBlock + 27);
  v6 = 0;
  v7 = 0;
  v8 = *(_QWORD *)(v5 + 24);
  v9 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v8 + 1920));
  *(_DWORD *)(v8 + 2352) = (unsigned int)PsGetCurrentThreadId();
  v10 = _InterlockedExchange((volatile __int32 *)(v5 + 12), 3);
  v11 = *(_QWORD *)(v5 + 24);
  *(_DWORD *)(v11 + 2352) = -1;
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v11 + 1920), v9);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_2f623439b0cb30f148aad6ad1abf961a_Traceguids, v5, v10);
  }
  v15 = *(_QWORD *)(v1 + 200);
  if ( v15 )
  {
    v20 = RxReferenceSiloAndAcquireRundown(v15, v12, v13, v14);
    v7 = v20;
    if ( v20 )
    {
      v6 = PsAttachSiloToCurrentThread(*(_QWORD *)(v20 + 40));
      goto LABEL_5;
    }
LABEL_13:
    v18 = -1073741536;
LABEL_11:
    RxCeCompleteConnectRequest(ParameterBlock);
    return v18;
  }
LABEL_5:
  v16 = *(_DWORD *)(v5 + 320);
  if ( v16 == 1 )
  {
    v17 = SmbWskInitiateAsynchronousConnect(ParameterBlock);
LABEL_7:
    v18 = v17;
    goto LABEL_8;
  }
  v18 = 0;
  if ( !v16 )
  {
    v17 = RxTdiInitiateAsynchronousConnect(ParameterBlock);
    goto LABEL_7;
  }
  v21 = v16 - 2;
  if ( !v21 )
  {
    v17 = RxSmbdInitiateAsynchronousConnect((__int64)ParameterBlock, v12, v13);
    goto LABEL_7;
  }
  v22 = v21 - 1;
  if ( !v22 )
  {
    v17 = RxVmbusInitiateAsynchronousConnect(ParameterBlock);
    goto LABEL_7;
  }
  if ( v22 == 1 )
  {
    v17 = SmbQuicInitiateAsynchronousConnect(ParameterBlock);
    goto LABEL_7;
  }
LABEL_8:
  if ( v7 )
  {
    PsDetachSiloFromCurrentThread(v6);
    RxDereferenceSiloAndReleaseRundown(v7);
  }
  if ( v18 != 259 )
    goto LABEL_11;
  return v18;
}

```

## disassembly

```asm
0x14001cda0  push    rbx
0x14001cda2  push    rbp
0x14001cda3  push    rsi
0x14001cda4  push    rdi
0x14001cda5  push    r12
0x14001cda7  push    r14
0x14001cda9  push    r15
0x14001cdab  sub     rsp, 30h
0x14001cdaf  mov     rsi, [rcx+8]
0x14001cdb3  mov     rbp, rcx
0x14001cdb6  lea     rcx, [rsi+8]; SpinLock
0x14001cdba  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001cdc1  nop     dword ptr [rax+rax+00h]
0x14001cdc6  movzx   ebx, byte ptr [rsi+0BCh]
0x14001cdcd  lea     rcx, [rsi+8]; SpinLock
0x14001cdd1  movzx   edx, al; NewIrql
0x14001cdd4  call    cs:__imp_KeReleaseSpinLock
0x14001cddb  nop     dword ptr [rax+rax+00h]
0x14001cde0  test    bl, bl
0x14001cde2  jnz     loc_14001CEBA
0x14001cde8  mov     r14, [rbp+0D8h]
0x14001cdef  xor     r12d, r12d
0x14001cdf2  xor     r15d, r15d
0x14001cdf5  mov     rbx, [r14+18h]
0x14001cdf9  lea     rcx, [rbx+780h]; SpinLock
0x14001ce00  call    cs:__imp_ExAcquireSpinLockExclusive
0x14001ce07  nop     dword ptr [rax+rax+00h]
0x14001ce0c  movzx   edi, al
0x14001ce0f  call    cs:__imp_PsGetCurrentThreadId
0x14001ce16  nop     dword ptr [rax+rax+00h]
0x14001ce1b  mov     [rbx+930h], eax
0x14001ce21  movzx   edx, dil; OldIrql
0x14001ce25  mov     ebx, 3
0x14001ce2a  xchg    ebx, [r14+0Ch]
0x14001ce2e  mov     rcx, [r14+18h]
0x14001ce32  mov     dword ptr [rcx+930h], 0FFFFFFFFh
0x14001ce3c  add     rcx, 780h; SpinLock
0x14001ce43  call    cs:__imp_ExReleaseSpinLockExclusive
0x14001ce4a  nop     dword ptr [rax+rax+00h]
0x14001ce4f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ce56  lea     rax, WPP_GLOBAL_Control
0x14001ce5d  cmp     rcx, rax
0x14001ce60  jz      short loc_14001CE69
0x14001ce62  mov     eax, [rcx+2Ch]
0x14001ce65  test    al, 4
0x14001ce67  jnz     short loc_14001CEC1
0x14001ce69  mov     rcx, [rsi+0C8h]
0x14001ce70  test    rcx, rcx
0x14001ce73  jnz     short loc_14001CEE5
0x14001ce75  mov     ecx, [r14+140h]
0x14001ce7c  cmp     ecx, 1
0x14001ce7f  jnz     loc_14001CF11
0x14001ce85  mov     rcx, rbp
0x14001ce88  call    SmbWskInitiateAsynchronousConnect
0x14001ce8d  mov     ebx, eax
0x14001ce8f  test    r15, r15
0x14001ce92  jnz     loc_14001CF43
0x14001ce98  cmp     ebx, 103h
0x14001ce9e  jz      short loc_14001CEA8
0x14001cea0  mov     rcx, rbp
0x14001cea3  call    RxCeCompleteConnectRequest
0x14001cea8  mov     eax, ebx
0x14001ceaa  add     rsp, 30h
0x14001ceae  pop     r15
0x14001ceb0  pop     r14
0x14001ceb2  pop     r12
0x14001ceb4  pop     rdi
0x14001ceb5  pop     rsi
0x14001ceb6  pop     rbp
0x14001ceb7  pop     rbx
0x14001ceb8  retn
0x14001ceba  mov     ebx, 0C0000120h
0x14001cebf  jmp     short loc_14001CEA0
0x14001cec1  cmp     byte ptr [rcx+29h], 4
0x14001cec5  jb      short loc_14001CE69
0x14001cec7  mov     rcx, [rcx+18h]
0x14001cecb  lea     r8, WPP_2f623439b0cb30f148aad6ad1abf961a_Traceguids
0x14001ced2  mov     edx, 13h
0x14001ced7  mov     [rsp+68h+var_48], ebx
0x14001cedb  mov     r9, r14
0x14001cede  call    WPP_SF_qD
0x14001cee3  jmp     short loc_14001CE69
0x14001cee5  call    cs:__imp_RxReferenceSiloAndAcquireRundown
0x14001ceec  nop     dword ptr [rax+rax+00h]
0x14001cef1  mov     r15, rax
0x14001cef4  test    rax, rax
0x14001cef7  jz      short loc_14001CEBA
0x14001cef9  mov     rcx, [rax+28h]
0x14001cefd  call    cs:__imp_PsAttachSiloToCurrentThread
0x14001cf04  nop     dword ptr [rax+rax+00h]
0x14001cf09  mov     r12, rax
0x14001cf0c  jmp     loc_14001CE75
0x14001cf11  xor     ebx, ebx
0x14001cf13  test    ecx, ecx
0x14001cf15  jz      loc_14005E56E
0x14001cf1b  sub     ecx, 2
0x14001cf1e  jz      loc_14005E560
0x14001cf24  sub     ecx, 1
0x14001cf27  jz      loc_14005E552
0x14001cf2d  cmp     ecx, 1
0x14001cf30  jnz     loc_14001CE8F
0x14001cf36  mov     rcx, rbp
0x14001cf39  call    SmbQuicInitiateAsynchronousConnect
0x14001cf3e  jmp     loc_14001CE8D
0x14001cf43  mov     rcx, r12
0x14001cf46  call    cs:__imp_PsDetachSiloFromCurrentThread
0x14001cf4d  nop     dword ptr [rax+rax+00h]
0x14001cf52  mov     rcx, r15
0x14001cf55  call    cs:__imp_RxDereferenceSiloAndReleaseRundown
0x14001cf5c  nop     dword ptr [rax+rax+00h]
0x14001cf61  jmp     loc_14001CE98
0x14005e552  mov     rcx, rbp; pContext
0x14005e555  call    RxVmbusInitiateAsynchronousConnect
0x14005e55a  nop
0x14005e55b  jmp     loc_14001CE8D
0x14005e560  mov     rcx, rbp
0x14005e563  call    RxSmbdInitiateAsynchronousConnect
0x14005e568  nop
0x14005e569  jmp     loc_14001CE8D
0x14005e56e  mov     rcx, rbp
0x14005e571  call    RxTdiInitiateAsynchronousConnect
0x14005e576  nop
0x14005e577  jmp     loc_14001CE8D
```
