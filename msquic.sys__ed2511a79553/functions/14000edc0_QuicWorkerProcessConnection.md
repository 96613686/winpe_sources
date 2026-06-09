# QuicWorkerProcessConnection

- ea: `0x14000edc0`
- end: `0x14000f127`
- name: `QuicWorkerProcessConnection`
- size: `871`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update`

## callers

- `0x14002e380`

## callees

- `0x140003b0c`
- `0x14000edc0`
- `0x14000f400`
- `0x140010820`
- `0x140014d80`
- `0x14001dcd0`
- `0x1400200d8`
- `0x140022528`
- `0x140022644`
- `0x1400291a4`
- `0x1400337e4`
- `0x14003c8e0`
- `0x14003e884`
- `0x14003ec10`
- `0x14003fd84`

## import_xrefs

- `ntoskrnl!_snprintf_s` at `0x14000ef15`
- `ntoskrnl!_snprintf_s` at `0x14000ef15`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ef73`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000ef73`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f06f`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000f06f`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14000f083`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x14000f083`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14000ee2e`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x14000ee2e`

## pseudocode

```c
void __fastcall QuicWorkerProcessConnection(__int64 a1, __int64 a2, __int64 a3, unsigned int *a4)
{
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rbp
  __int64 v11; // rcx
  unsigned int v12; // eax
  __int64 v13; // rcx
  unsigned int v14; // r9d
  __int64 v15; // r9
  char v16; // al
  unsigned __int16 *v17; // rax
  int v18; // ecx
  int v19; // edx
  __int64 v20; // rcx
  char v21; // r14
  KIRQL v22; // al
  __int64 v23; // rcx
  unsigned __int8 v24; // r12
  char v25; // r15
  char v26; // r14
  bool v27; // zf
  __int64 v28; // rax
  _QWORD *v29; // rdx
  __int64 v30; // rcx
  _QWORD *v31; // rax
  _QWORD *v32; // rax
  _BYTE v33[8]; // [rsp+30h] [rbp-108h] BYREF
  __int64 v34; // [rsp+38h] [rbp-100h] BYREF
  unsigned __int16 v35; // [rsp+40h] [rbp-F8h]
  __int16 v36; // [rsp+42h] [rbp-F6h]
  __int128 v37; // [rsp+44h] [rbp-F4h]
  __int128 v38; // [rsp+54h] [rbp-E4h]
  __int64 v39; // [rsp+64h] [rbp-D4h]
  char DstBuf[128]; // [rsp+70h] [rbp-C8h] BYREF

  if ( byte_14005C489 < 0 )
    McTemplateU0pq_EtwWriteTransfer(a1, QuicConnScheduleState, a2, 2);
  v8 = *(_QWORD *)(a2 + 88);
  if ( v8 && (v9 = *(_QWORD *)(v8 + 64)) != 0 )
    v10 = PsAttachSiloToCurrentThread(v9);
  else
    v10 = -1;
  v11 = *(unsigned int *)(a2 + 3672);
  if ( (_DWORD)v11 )
  {
    v12 = CxPlatTimeDiff32(v11, *a4);
    v14 = 0;
    if ( v12 < 0x7FFFFFFF )
      v14 = v12;
    v15 = (7 * *(_DWORD *)(a1 + 84) + v14) >> 3;
    *(_DWORD *)(a1 + 84) = v15;
    if ( (byte_14005C489 & 1) != 0 )
      McTemplateU0pq_EtwWriteTransfer(v13, QuicWorkerQueueDelayUpdated, a1, v15);
  }
  ++*(_QWORD *)(a2 + 3680);
  v16 = *(_BYTE *)(a2 + 250);
  *(_QWORD *)(a2 + 256) = a3;
  if ( (v16 & 0x40) != 0 )
  {
    *(_BYTE *)(a2 + 250) = v16 & 0xBF;
    QuicTimerWheelUpdateConnection(a1 + 88, a2);
    v17 = *(unsigned __int16 **)(a1 + 48);
    v34 = 9;
    v37 = 0;
    v39 = 0;
    v38 = 0;
    v18 = v17[1];
    v35 = v17[1];
    v19 = *v17;
    v36 = *v17;
    if ( (byte_14005C48C & 1) != 0 )
    {
      _snprintf_s(
        DstBuf,
        0x80u,
        0xFFFFFFFFFFFFFFFFuLL,
        "Indicating QUIC_CONNECTION_EVENT_IDEAL_PROCESSOR_CHANGED (Proc=%hu,Indx=%hu)",
        v18,
        v19);
      McTemplateU0ps_EtwWriteTransfer(v20, QuicConnLogVerbose, a2, DstBuf);
    }
    QuicConnIndicateEvent(a2, &v34);
  }
  v33[0] = 0;
  v21 = (*(_BYTE *)(a2 + 250) >> 6) | QuicConnDrainOperations(a2, v33);
  *(_QWORD *)(a2 + 256) = 0;
  v22 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 160));
  v24 = v33[0];
  *(_BYTE *)(a1 + 168) = v22;
  v25 = 1;
  v26 = *(_BYTE *)(a2 + 277) & 0xFE | (2 * (v21 & 1));
  v27 = (*(_BYTE *)(a2 + 250) & 0x40) == 0;
  *(_BYTE *)(a2 + 277) = v26;
  if ( v27 )
  {
    if ( (v26 & 2) != 0 )
    {
      v28 = QuicTimePlat();
      *(_DWORD *)(a2 + 3672) = QuicTimePlatToUs64(v28);
      v29 = (_QWORD *)(a2 + 32);
      if ( v24 )
      {
        v30 = **(_QWORD **)(a1 + 192);
        v31 = *(_QWORD **)(v30 + 8);
        *v29 = v30;
        *(_QWORD *)(a2 + 40) = v31;
        *v31 = v29;
        *(_QWORD *)(v30 + 8) = v29;
        *(_QWORD *)(a1 + 192) = v29;
        *(_BYTE *)(a2 + 277) |= 4u;
      }
      else
      {
        v30 = a1 + 176;
        v32 = *(_QWORD **)(a1 + 184);
        *v29 = a1 + 176;
        *(_QWORD *)(a2 + 40) = v32;
        *v32 = v29;
        *(_QWORD *)(a1 + 184) = v29;
      }
      if ( byte_14005C489 < 0 )
        McTemplateU0pq_EtwWriteTransfer(v30, QuicConnScheduleState, a2, 1);
      v25 = 0;
    }
    else if ( byte_14005C489 < 0 )
    {
      McTemplateU0pq_EtwWriteTransfer(v23, QuicConnScheduleState, a2, 0);
    }
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 160), *(_BYTE *)(a1 + 168));
  if ( v10 != -1 )
    PsDetachSiloFromCurrentThread(v10);
  if ( v25 )
  {
    if ( (*(_BYTE *)(a2 + 250) & 0x40) != 0 )
    {
      QuicTimerWheelRemoveConnection(a1 + 88, a2);
      if ( !*(_QWORD *)(a2 + 80) )
      {
        CxPlatLogAssert("C:\\__w\\1\\s\\msquic\\src\\core\\worker.c", 627, "Connection->Registration != ((void *)0)");
        __int2c();
      }
      QuicRegistrationQueueNewConnection(*(_QWORD *)(a2 + 80), a2);
      QuicWorkerMoveConnection(*(_QWORD *)(a2 + 64), a2, v24);
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a2 + 240), 0xFFFFFFFF) == 1 )
      QuicConnFree(a2);
  }
}

```

## disassembly

```asm
0x14000edc0  mov     [rsp+arg_10], rbx
0x14000edc5  push    rbp
0x14000edc6  push    rsi
0x14000edc7  push    rdi
0x14000edc8  push    r12
0x14000edca  push    r13
0x14000edcc  push    r14
0x14000edce  push    r15
0x14000edd0  sub     rsp, 100h
0x14000edd7  mov     rax, cs:__security_cookie
0x14000edde  xor     rax, rsp
0x14000ede1  mov     [rsp+138h+var_48], rax
0x14000ede9  movzx   eax, cs:byte_14005C489
0x14000edf0  mov     r15, r9
0x14000edf3  mov     r14, r8
0x14000edf6  mov     rbx, rdx
0x14000edf9  mov     rdi, rcx
0x14000edfc  test    al, al
0x14000edfe  jns     short loc_14000EE15
0x14000ee00  mov     r8, rdx
0x14000ee03  mov     r9d, 2
0x14000ee09  lea     rdx, QuicConnScheduleState
0x14000ee10  call    McTemplateU0pq_EtwWriteTransfer
0x14000ee15  mov     rax, [rbx+58h]
0x14000ee19  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x14000ee20  test    rax, rax
0x14000ee23  jz      short loc_14000EE3F
0x14000ee25  mov     rcx, [rax+40h]
0x14000ee29  test    rcx, rcx
0x14000ee2c  jz      short loc_14000EE3F
0x14000ee2e  call    cs:__imp_PsAttachSiloToCurrentThread
0x14000ee35  nop     dword ptr [rax+rax+00h]
0x14000ee3a  mov     rbp, rax
0x14000ee3d  jmp     short loc_14000EE42
0x14000ee3f  mov     rbp, rsi
0x14000ee42  mov     ecx, [rbx+0E58h]
0x14000ee48  xor     r12d, r12d
0x14000ee4b  test    ecx, ecx
0x14000ee4d  jz      short loc_14000EE8A
0x14000ee4f  mov     edx, [r15]
0x14000ee52  call    CxPlatTimeDiff32
0x14000ee57  cmp     eax, 7FFFFFFFh
0x14000ee5c  mov     r9d, r12d
0x14000ee5f  cmovb   r9d, eax
0x14000ee63  imul    eax, [rdi+54h], 7
0x14000ee67  add     r9d, eax
0x14000ee6a  shr     r9d, 3
0x14000ee6e  mov     [rdi+54h], r9d
0x14000ee72  test    cs:byte_14005C489, 1
0x14000ee79  jz      short loc_14000EE8A
0x14000ee7b  mov     r8, rdi
0x14000ee7e  lea     rdx, QuicWorkerQueueDelayUpdated
0x14000ee85  call    McTemplateU0pq_EtwWriteTransfer
0x14000ee8a  inc     qword ptr [rbx+0E60h]
0x14000ee91  movzx   eax, byte ptr [rbx+0FAh]
0x14000ee98  mov     [rbx+100h], r14
0x14000ee9f  test    al, 40h
0x14000eea1  jz      loc_14000EF42
0x14000eea7  and     al, 0BFh
0x14000eea9  lea     rcx, [rdi+58h]
0x14000eead  mov     rdx, rbx
0x14000eeb0  mov     [rbx+0FAh], al
0x14000eeb6  call    QuicTimerWheelUpdateConnection
0x14000eebb  test    cs:byte_14005C48C, 1
0x14000eec2  xorps   xmm0, xmm0
0x14000eec5  mov     rax, [rdi+30h]
0x14000eec9  xorps   xmm1, xmm1
0x14000eecc  mov     [rsp+138h+var_100], 9
0x14000eed5  movdqu  [rsp+138h+var_F4], xmm0
0x14000eedb  mov     [rsp+138h+var_D4], r12
0x14000eee0  movdqu  [rsp+138h+var_E4], xmm1
0x14000eee6  movzx   ecx, word ptr [rax+2]
0x14000eeea  mov     [rsp+138h+var_F8], cx
0x14000eeef  movzx   edx, word ptr [rax]
0x14000eef2  mov     [rsp+138h+var_F6], dx
0x14000eef7  jz      short loc_14000EF35
0x14000eef9  mov     [rsp+138h+var_110], edx
0x14000eefd  lea     r9, aIndicatingQuic_8; "Indicating QUIC_CONNECTION_EVENT_IDEAL_"...
0x14000ef04  mov     [rsp+138h+var_118], ecx
0x14000ef08  mov     r8, rsi; MaxCount
0x14000ef0b  lea     rcx, [rsp+138h+DstBuf]; DstBuf
0x14000ef10  mov     edx, 80h; SizeInBytes
0x14000ef15  call    cs:__imp__snprintf_s
0x14000ef1c  nop     dword ptr [rax+rax+00h]
0x14000ef21  lea     r9, [rsp+138h+DstBuf]
0x14000ef26  mov     r8, rbx
0x14000ef29  lea     rdx, QuicConnLogVerbose
0x14000ef30  call    McTemplateU0ps_EtwWriteTransfer
0x14000ef35  lea     rdx, [rsp+138h+var_100]
0x14000ef3a  mov     rcx, rbx
0x14000ef3d  call    QuicConnIndicateEvent
0x14000ef42  lea     rdx, [rsp+138h+var_108]
0x14000ef47  mov     [rsp+138h+var_108], r12b
0x14000ef4c  mov     rcx, rbx
0x14000ef4f  call    QuicConnDrainOperations
0x14000ef54  movzx   ecx, byte ptr [rbx+0FAh]
0x14000ef5b  movzx   r14d, al
0x14000ef5f  shr     cl, 6
0x14000ef62  or      r14b, cl
0x14000ef65  mov     [rbx+100h], r12
0x14000ef6c  lea     rcx, [rdi+0A0h]; SpinLock
0x14000ef73  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000ef7a  nop     dword ptr [rax+rax+00h]
0x14000ef7f  movzx   r12d, [rsp+138h+var_108]
0x14000ef85  and     r14b, 1
0x14000ef89  add     r14b, r14b
0x14000ef8c  mov     [rdi+0A8h], al
0x14000ef92  or      r14b, [rbx+115h]
0x14000ef99  mov     r15b, 1
0x14000ef9c  and     r14b, 0FEh
0x14000efa0  test    byte ptr [rbx+0FAh], 40h
0x14000efa7  mov     [rbx+115h], r14b
0x14000efae  jnz     loc_14000F061
0x14000efb4  test    r14b, 2
0x14000efb8  jz      loc_14000F044
0x14000efbe  call    QuicTimePlat
0x14000efc3  mov     rcx, rax
0x14000efc6  call    QuicTimePlatToUs64
0x14000efcb  mov     [rbx+0E58h], eax
0x14000efd1  lea     rdx, [rbx+20h]
0x14000efd5  test    r12b, r12b
0x14000efd8  jz      short loc_14000F006
0x14000efda  mov     rax, [rdi+0C0h]
0x14000efe1  mov     rcx, [rax]
0x14000efe4  mov     rax, [rcx+8]
0x14000efe8  mov     [rdx], rcx
0x14000efeb  mov     [rdx+8], rax
0x14000efef  mov     [rax], rdx
0x14000eff2  mov     [rcx+8], rdx
0x14000eff6  mov     [rdi+0C0h], rdx
0x14000effd  or      byte ptr [rbx+115h], 4
0x14000f004  jmp     short loc_14000F01F
0x14000f006  lea     rcx, [rdi+0B0h]
0x14000f00d  mov     rax, [rcx+8]
0x14000f011  mov     [rdx], rcx
0x14000f014  mov     [rdx+8], rax
0x14000f018  mov     [rax], rdx
0x14000f01b  mov     [rcx+8], rdx
0x14000f01f  movzx   eax, cs:byte_14005C489
0x14000f026  test    al, al
0x14000f028  jns     short loc_14000F03F
0x14000f02a  mov     r9d, 1
0x14000f030  lea     rdx, QuicConnScheduleState
0x14000f037  mov     r8, rbx
0x14000f03a  call    McTemplateU0pq_EtwWriteTransfer
0x14000f03f  xor     r15b, r15b
0x14000f042  jmp     short loc_14000F061
0x14000f044  movzx   eax, cs:byte_14005C489
0x14000f04b  test    al, al
0x14000f04d  jns     short loc_14000F061
0x14000f04f  xor     r9d, r9d
0x14000f052  lea     rdx, QuicConnScheduleState
0x14000f059  mov     r8, rbx
0x14000f05c  call    McTemplateU0pq_EtwWriteTransfer
0x14000f061  movzx   edx, byte ptr [rdi+0A8h]; NewIrql
0x14000f068  lea     rcx, [rdi+0A0h]; SpinLock
0x14000f06f  call    cs:__imp_KeReleaseSpinLock
0x14000f076  nop     dword ptr [rax+rax+00h]
0x14000f07b  cmp     rbp, rsi
0x14000f07e  jz      short loc_14000F08F
0x14000f080  mov     rcx, rbp
0x14000f083  call    cs:__imp_PsDetachSiloFromCurrentThread
0x14000f08a  nop     dword ptr [rax+rax+00h]
0x14000f08f  test    r15b, r15b
0x14000f092  jz      short loc_14000F0FB
0x14000f094  test    byte ptr [rbx+0FAh], 40h
0x14000f09b  jz      short loc_14000F0E6
0x14000f09d  lea     rcx, [rdi+58h]
0x14000f0a1  mov     rdx, rbx
0x14000f0a4  call    QuicTimerWheelRemoveConnection
0x14000f0a9  cmp     qword ptr [rbx+50h], 0
0x14000f0ae  jnz     short loc_14000F0CA
0x14000f0b0  lea     r8, aConnectionRegi; "Connection->Registration != ((void *)0)"
0x14000f0b7  mov     edx, 273h
0x14000f0bc  lea     rcx, aCW1SMsquicSrcC_20; "C:\\__w\\1\\s\\msquic\\src\\core\\worke"...
0x14000f0c3  call    CxPlatLogAssert
0x14000f0c8  int     2Ch; Windows NT - assertion failure
0x14000f0ca  mov     rcx, [rbx+50h]
0x14000f0ce  mov     rdx, rbx
0x14000f0d1  call    QuicRegistrationQueueNewConnection
0x14000f0d6  mov     rcx, [rbx+40h]
0x14000f0da  movzx   r8d, r12b
0x14000f0de  mov     rdx, rbx
0x14000f0e1  call    QuicWorkerMoveConnection
0x14000f0e6  lock xadd [rbx+0F0h], esi
0x14000f0ee  cmp     esi, 1
0x14000f0f1  jnz     short loc_14000F0FB
0x14000f0f3  mov     rcx, rbx
0x14000f0f6  call    QuicConnFree
0x14000f0fb  mov     rcx, [rsp+138h+var_48]
0x14000f103  xor     rcx, rsp; StackCookie
0x14000f106  call    __security_check_cookie
0x14000f10b  mov     rbx, [rsp+138h+arg_10]
0x14000f113  add     rsp, 100h
0x14000f11a  pop     r15
0x14000f11c  pop     r14
0x14000f11e  pop     r13
0x14000f120  pop     r12
0x14000f122  pop     rdi
0x14000f123  pop     rsi
0x14000f124  pop     rbp
0x14000f125  retn
```
