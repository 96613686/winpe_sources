# SmbCeMemoryRegisterCompleteInd

- ea: `0x14000d080`
- end: `0x14000d2f3`
- name: `SmbCeMemoryRegisterCompleteInd`
- size: `627`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140006660`
- `0x140009360`
- `0x1400093a0`
- `0x140009fc0`
- `0x14000c030`
- `0x14000c6a0`
- `0x14000c880`
- `0x14000d080`
- `0x14000df60`
- `0x14000fbe0`
- `0x14001b2a0`
- `0x140028960`
- `0x140038068`
- `0x1400383d0`
- `0x140059ea0`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x14000d19f`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000d19f`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000d0aa`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000d0aa`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d18b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000d18b`
- `rdbss!RxCeUntrackTransportOpEx` at `0x14000d0f1`
- `rdbss!RxCeUntrackTransportOpEx` at `0x14000d0f1`
- `rdbss!RxDispatchToWorkerThread` at `0x14000d1c6`
- `rdbss!RxDispatchToWorkerThread` at `0x14000d1c6`

## pseudocode

```c
void __fastcall SmbCeMemoryRegisterCompleteInd(int a1, __int64 a2)
{
  unsigned __int64 v2; // rdi
  NTSTATUS v3; // esi
  __int64 v5; // rbp
  char v6; // r12
  __int64 v7; // rax
  _BYTE *v8; // r15
  int v9; // ecx
  int v10; // eax
  unsigned int v11; // [rsp+60h] [rbp+8h] BYREF
  __int64 v12; // [rsp+68h] [rbp+10h]

  v2 = *(_QWORD *)(a2 + 56);
  v3 = a1;
  if ( a1 < 0 )
    v3 = -1073741300;
  v5 = *(_QWORD *)(v2 + 56);
  v11 = 0;
  if ( (PIRP)v2 == IoGetTopLevelIrp() )
  {
    v6 = 1;
  }
  else
  {
    v6 = 0;
    if ( v5 )
      SmbCeAcquireCompoundingKeyLock(v5);
    else
      SmbCeAcquireExchangeLock(v2);
  }
  *(_DWORD *)(a2 + 4) &= ~0x800u;
  *(_BYTE *)(a2 + 84) = 0;
  RxCeUntrackTransportOpEx(a2 + 344, (unsigned int)v3);
  _InterlockedIncrement((volatile signed __int32 *)(v2 + 36));
  if ( v3 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qqD(WPP_GLOBAL_Control->AttachedDevice, 27, &WPP_1ffd7df1a0ca364e8ae776b5c429ef78_Traceguids, a2, v2, v3);
    }
    v8 = (_BYTE *)(a2 + 87);
    goto LABEL_42;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 28, &WPP_1ffd7df1a0ca364e8ae776b5c429ef78_Traceguids, a2);
  }
  v7 = *(_QWORD *)(a2 + 56);
  v8 = (_BYTE *)(a2 + 87);
  *(_BYTE *)(a2 + 87) = 1;
  if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v7 + 96) + 392LL) + 320LL) == 2 )
  {
    (*(void (__fastcall **)(_QWORD, _QWORD, unsigned int *))(SmbdFastDispatch + 48))(*(_QWORD *)(a2 + 760), 0, &v11);
  }
  else if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v7 + 96) + 392LL) + 320LL) == 3 )
  {
    if ( *(_QWORD *)(a2 + 760) == -1 )
      v9 = 8
         * ((*(unsigned int *)(*(_QWORD *)(a2 + 768) + 40LL)
           + 4095LL
           + (unsigned __int64)(*(_DWORD *)(*(_QWORD *)(a2 + 768) + 44LL) & 0xFFF)) >> 12)
         + 8;
    else
      v9 = 16;
    v11 = v9;
  }
  if ( *(unsigned __int16 *)(a2 + 784) < v11 )
  {
    v3 = -1073741507;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 29, &WPP_1ffd7df1a0ca364e8ae776b5c429ef78_Traceguids, a2, v2);
    }
    goto LABEL_42;
  }
  if ( !v6 )
  {
    if ( v5 )
    {
      SmbCeReleaseCompoundingKeyLock(v5);
    }
    else
    {
      KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 24), *(_BYTE *)(v2 + 32));
      SmbCeDereferenceExchange(v2);
    }
  }
  if ( !KeGetCurrentIrql() )
  {
    SmbCsepResubmitBufferContextHelper((PVOID)a2);
    return;
  }
  v3 = RxDispatchToWorkerThread(
         *(PRDBSS_DEVICE_OBJECT *)(*(_QWORD *)(v2 + 72) + 24LL),
         NormalWorkQueue,
         SmbCsepResubmitBufferContextHelper,
         (PVOID)a2);
  if ( v3 < 0 )
  {
    if ( !v6 )
    {
      if ( v5 )
        SmbCeAcquireCompoundingKeyLock(v5);
      else
        SmbCeAcquireExchangeLock(v2);
    }
LABEL_42:
    v10 = SmbCseInvalidateMemoryRegistrationAsync(a2);
    if ( v10 != -1073741816 && v10 != 259 )
      *v8 = 0;
    v12 = (unsigned int)v3;
    SmbCseUpdateBufferContextStatus(a2, (unsigned int)v3);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v2 + 36), 0xFFFFFFFF) == 1
      && (unsigned __int8)SmbCepCheckExchangeForDeferredAbortOrIfFinalizable(v2) )
    {
      SmbCepCompleteExchangeLite(v2);
    }
    if ( !v6 )
    {
      if ( v5 )
        SmbCeReleaseCompoundingKeyLock(v5);
      else
        SmbCeReleaseExchangeLock((PVOID)v2);
    }
  }
}

```

## disassembly

```asm
0x14000d080  push    rbx
0x14000d082  push    rbp
0x14000d083  push    rsi
0x14000d084  push    rdi
0x14000d085  push    r12
0x14000d087  sub     rsp, 30h
0x14000d08b  mov     rdi, [rdx+38h]
0x14000d08f  test    ecx, ecx
0x14000d091  mov     esi, ecx
0x14000d093  mov     eax, 0C000020Ch
0x14000d098  mov     rbx, rdx
0x14000d09b  cmovs   esi, eax
0x14000d09e  mov     rbp, [rdi+38h]
0x14000d0a2  mov     [rsp+58h+arg_0], 0
0x14000d0aa  call    cs:__imp_IoGetTopLevelIrp
0x14000d0b1  nop     dword ptr [rax+rax+00h]
0x14000d0b6  cmp     rdi, rax
0x14000d0b9  jz      loc_14000D1FC
0x14000d0bf  xor     r12b, r12b
0x14000d0c2  test    rbp, rbp
0x14000d0c5  jz      loc_14005CAA2
0x14000d0cb  mov     rcx, rbp
0x14000d0ce  call    SmbCeAcquireCompoundingKeyLock
0x14000d0d3  and     dword ptr [rbx+4], 0FFFFF7FFh
0x14000d0da  lea     rcx, [rbx+158h]
0x14000d0e1  mov     [rsp+58h+arg_10], r14
0x14000d0e6  mov     edx, esi
0x14000d0e8  mov     [rsp+58h+arg_18], r15
0x14000d0ed  mov     byte ptr [rbx+54h], 0
0x14000d0f1  call    cs:__imp_RxCeUntrackTransportOpEx
0x14000d0f8  nop     dword ptr [rax+rax+00h]
0x14000d0fd  lock inc dword ptr [rdi+24h]
0x14000d101  test    esi, esi
0x14000d103  js      loc_14005CAB0
0x14000d109  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d110  lea     r14, WPP_GLOBAL_Control
0x14000d117  cmp     rcx, r14
0x14000d11a  jnz     loc_14000D204
0x14000d120  mov     rax, [rbx+38h]
0x14000d124  lea     r15, [rbx+57h]
0x14000d128  mov     byte ptr [r15], 1
0x14000d12c  mov     rcx, [rax+60h]
0x14000d130  mov     rdx, [rcx+188h]
0x14000d137  mov     ecx, [rdx+140h]
0x14000d13d  sub     ecx, 2
0x14000d140  jnz     loc_14000D236
0x14000d146  mov     rax, cs:SmbdFastDispatch
0x14000d14d  lea     r8, [rsp+58h+arg_0]
0x14000d152  mov     rcx, [rbx+2F8h]
0x14000d159  xor     edx, edx
0x14000d15b  mov     rax, [rax+30h]
0x14000d15f  call    _guard_dispatch_icall
0x14000d164  movzx   eax, word ptr [rbx+310h]
0x14000d16b  cmp     eax, [rsp+58h+arg_0]
0x14000d16f  jb      loc_14000D279
0x14000d175  test    r12b, r12b
0x14000d178  jnz     short loc_14000D19F
0x14000d17a  test    rbp, rbp
0x14000d17d  jnz     loc_14000D2C6
0x14000d183  movzx   edx, byte ptr [rdi+20h]; NewIrql
0x14000d187  lea     rcx, [rdi+18h]; SpinLock
0x14000d18b  call    cs:__imp_KeReleaseSpinLock
0x14000d192  nop     dword ptr [rax+rax+00h]
0x14000d197  mov     rcx, rdi; pContext
0x14000d19a  call    SmbCeDereferenceExchange
0x14000d19f  call    cs:__imp_KeGetCurrentIrql
0x14000d1a6  nop     dword ptr [rax+rax+00h]
0x14000d1ab  test    al, al
0x14000d1ad  jz      short loc_14000D1F2
0x14000d1af  mov     rcx, [rdi+48h]
0x14000d1b3  lea     r8, SmbCsepResubmitBufferContextHelper; Routine
0x14000d1ba  mov     r9, rbx; pContext
0x14000d1bd  mov     edx, 3; WorkQueueType
0x14000d1c2  mov     rcx, [rcx+18h]; pMRxDeviceObject
0x14000d1c6  call    cs:__imp_RxDispatchToWorkerThread
0x14000d1cd  nop     dword ptr [rax+rax+00h]
0x14000d1d2  mov     esi, eax
0x14000d1d4  test    eax, eax
0x14000d1d6  js      loc_14000D2D3
0x14000d1dc  mov     r15, [rsp+58h+arg_18]
0x14000d1e1  mov     r14, [rsp+58h+arg_10]
0x14000d1e6  add     rsp, 30h
0x14000d1ea  pop     r12
0x14000d1ec  pop     rdi
0x14000d1ed  pop     rsi
0x14000d1ee  pop     rbp
0x14000d1ef  pop     rbx
0x14000d1f0  retn
0x14000d1f2  mov     rcx, rbx; Context
0x14000d1f5  call    SmbCsepResubmitBufferContextHelper
0x14000d1fa  jmp     short loc_14000D1DC
0x14000d1fc  mov     r12b, 1
0x14000d1ff  jmp     loc_14000D0D3
0x14000d204  mov     eax, [rcx+2Ch]
0x14000d207  test    al, 10h
0x14000d209  jz      loc_14000D120
0x14000d20f  cmp     byte ptr [rcx+29h], 4
0x14000d213  jb      loc_14000D120
0x14000d219  mov     rcx, [rcx+18h]
0x14000d21d  lea     r8, WPP_1ffd7df1a0ca364e8ae776b5c429ef78_Traceguids
0x14000d224  mov     edx, 1Ch
0x14000d229  mov     r9, rbx
0x14000d22c  call    WPP_SF_q
0x14000d231  jmp     loc_14000D120
0x14000d236  cmp     ecx, 1
0x14000d239  jnz     loc_14000D164
0x14000d23f  cmp     qword ptr [rbx+2F8h], 0FFFFFFFFFFFFFFFFh
0x14000d247  jnz     loc_14005CAF7
0x14000d24d  mov     rax, [rbx+300h]
0x14000d254  mov     ecx, [rax+2Ch]
0x14000d257  mov     eax, [rax+28h]
0x14000d25a  and     ecx, 0FFFh
0x14000d260  add     rax, 0FFFh
0x14000d266  add     rcx, rax
0x14000d269  shr     rcx, 0Ch
0x14000d26d  lea     ecx, ds:8[rcx*8]
0x14000d274  jmp     loc_14005CAFC
0x14000d279  mov     esi, 0C000013Dh
0x14000d27e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d285  cmp     rcx, r14
0x14000d288  jz      loc_14005CB0D
0x14000d28e  mov     eax, [rcx+2Ch]
0x14000d291  test    al, 1
0x14000d293  jz      loc_14005CB0D
0x14000d299  cmp     byte ptr [rcx+29h], 1
0x14000d29d  jb      loc_14005CB0D
0x14000d2a3  mov     rcx, [rcx+18h]
0x14000d2a7  lea     r8, WPP_1ffd7df1a0ca364e8ae776b5c429ef78_Traceguids
0x14000d2ae  mov     edx, 1Dh
0x14000d2b3  mov     [rsp+58h+var_38], rdi
0x14000d2b8  mov     r9, rbx
0x14000d2bb  call    WPP_SF_qq
0x14000d2c0  nop
0x14000d2c1  jmp     loc_14005CB0D
0x14000d2c6  mov     rcx, rbp
0x14000d2c9  call    SmbCeReleaseCompoundingKeyLock
0x14000d2ce  jmp     loc_14000D19F
0x14000d2d3  test    r12b, r12b
0x14000d2d6  jnz     loc_14005CB0D
0x14000d2dc  test    rbp, rbp
0x14000d2df  jz      loc_14005CB05
0x14000d2e5  mov     rcx, rbp
0x14000d2e8  call    SmbCeAcquireCompoundingKeyLock
0x14000d2ed  nop
0x14000d2ee  jmp     loc_14005CB0D
0x14005caa2  mov     rcx, rdi
0x14005caa5  call    SmbCeAcquireExchangeLock
0x14005caaa  nop
0x14005caab  jmp     loc_14000D0D3
0x14005cab0  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cab7  lea     r14, WPP_GLOBAL_Control
0x14005cabe  cmp     rcx, r14
0x14005cac1  jz      short loc_14005CAF1
0x14005cac3  mov     eax, [rcx+2Ch]
0x14005cac6  test    al, 1
0x14005cac8  jz      short loc_14005CAF1
0x14005caca  cmp     byte ptr [rcx+29h], 1
0x14005cace  jb      short loc_14005CAF1
0x14005cad0  mov     rcx, [rcx+18h]
0x14005cad4  lea     r8, WPP_1ffd7df1a0ca364e8ae776b5c429ef78_Traceguids
0x14005cadb  mov     edx, 1Bh
0x14005cae0  mov     [rsp+58h+var_30], esi
0x14005cae4  mov     r9, rbx
0x14005cae7  mov     [rsp+58h+var_38], rdi
0x14005caec  call    WPP_SF_qqD
0x14005caf1  lea     r15, [rbx+57h]
0x14005caf5  jmp     short loc_14005CB0D
0x14005caf7  mov     ecx, 10h
0x14005cafc  mov     [rsp+58h+arg_0], ecx
0x14005cb00  jmp     loc_14000D164
0x14005cb05  mov     rcx, rdi
0x14005cb08  call    SmbCeAcquireExchangeLock
0x14005cb0d  mov     rcx, rbx
0x14005cb10  call    SmbCseInvalidateMemoryRegistrationAsync
0x14005cb15  cmp     eax, 0C0000008h
0x14005cb1a  jz      short loc_14005CB27
0x14005cb1c  cmp     eax, 103h
0x14005cb21  jz      short loc_14005CB27
0x14005cb23  mov     byte ptr [r15], 0
0x14005cb27  mov     dword ptr [rsp+58h+arg_8], esi
0x14005cb2b  mov     rcx, rbx
0x14005cb2e  mov     dword ptr [rsp+58h+arg_8+4], 0
0x14005cb36  mov     rdx, [rsp+58h+arg_8]
0x14005cb3b  call    SmbCseUpdateBufferContextStatus
0x14005cb40  mov     eax, 0FFFFFFFFh
0x14005cb45  lock xadd [rdi+24h], eax
0x14005cb4a  cmp     eax, 1
0x14005cb4d  jnz     short loc_14005CB63
0x14005cb4f  mov     rcx, rdi
0x14005cb52  call    SmbCepCheckExchangeForDeferredAbortOrIfFinalizable
0x14005cb57  test    al, al
0x14005cb59  jz      short loc_14005CB63
0x14005cb5b  mov     rcx, rdi
0x14005cb5e  call    SmbCepCompleteExchangeLite
0x14005cb63  test    r12b, r12b
0x14005cb66  jnz     loc_14000D1DC
0x14005cb6c  test    rbp, rbp
0x14005cb6f  jz      short loc_14005CB7F
0x14005cb71  mov     rcx, rbp
0x14005cb74  call    SmbCeReleaseCompoundingKeyLock
0x14005cb79  nop
0x14005cb7a  jmp     loc_14000D1DC
0x14005cb7f  mov     rcx, rdi
0x14005cb82  call    SmbCeReleaseExchangeLock
0x14005cb87  nop
0x14005cb88  jmp     loc_14000D1DC
```
