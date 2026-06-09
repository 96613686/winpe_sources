# DrDevice::OnDeviceControlCompletion(tagRDPDR_IOCOMPLETION_PACKET *,ulong,int *,SmartPtr<DrExchange>)

- ea: `0x140023500`
- end: `0x140023ce1`
- name: `?OnDeviceControlCompletion@DrDevice@@UEAAJPEAUtagRDPDR_IOCOMPLETION_PACKET@@KPEAHV?$SmartPtr@VDrExchange@@@@@Z`
- size: `2017`
- prototype: `__int64 __fastcall(__int64, unsigned int *, unsigned int, _DWORD *, RefCount *ContextPointer)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x140001660`
- `0x1400016a0`
- `0x14000324c`
- `0x14000327c`
- `0x1400032c0`
- `0x140006560`
- `0x1400065c0`
- `0x1400117e0`
- `0x140023500`
- `0x140023cf0`
- `0x140024020`
- `0x140024180`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x1400235cc`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400237f5`
- `ntoskrnl!ExAcquireFastMutex` at `0x140023837`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002392c`
- `ntoskrnl!ExAcquireFastMutex` at `0x140023970`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400235cc`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400237f5`
- `ntoskrnl!ExAcquireFastMutex` at `0x140023837`
- `ntoskrnl!ExAcquireFastMutex` at `0x14002392c`
- `ntoskrnl!ExAcquireFastMutex` at `0x140023970`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400235fd`
- `ntoskrnl!ExReleaseFastMutex` at `0x140023813`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002386a`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002394c`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002399f`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400235fd`
- `ntoskrnl!ExReleaseFastMutex` at `0x140023813`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002386a`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002394c`
- `ntoskrnl!ExReleaseFastMutex` at `0x14002399f`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140023b56`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140023b56`
- `rdbss!RxMapAndDissociateMidFromContext` at `0x1400239dc`
- `rdbss!RxMapAndDissociateMidFromContext` at `0x140023a12`
- `rdbss!RxMapAndDissociateMidFromContext` at `0x1400239dc`
- `rdbss!RxMapAndDissociateMidFromContext` at `0x140023a12`

## pseudocode

```c
__int64 __fastcall DrDevice::OnDeviceControlCompletion(
        __int64 a1,
        unsigned int *a2,
        unsigned int a3,
        _DWORD *a4,
        RefCount *ContextPointer)
{
  _DWORD *v5; // r12
  __int64 v8; // r10
  RefCount **v9; // r15
  __int64 v10; // rbx
  __int64 v11; // r14
  int v12; // eax
  unsigned int v13; // ebx
  unsigned int v14; // r12d
  __int64 v15; // rax
  __int64 v16; // rax
  struct _RX_CONTEXT *v17; // rsi
  __int64 v18; // rbx
  const void *v20; // r9
  __int64 v21; // rcx
  char *v22; // rdx
  __int64 v23; // rsi
  __int64 v24; // rbx
  struct _RX_MID_ATLAS *v25; // rcx
  __int64 v26; // rsi
  __int64 v27; // rbx
  struct _RX_MID_ATLAS *v28; // rcx
  __int64 v30; // [rsp+78h] [rbp+10h]

  v5 = a4;
  v8 = a1;
  v9 = (RefCount **)ContextPointer;
  v10 = *(_QWORD *)(*(_QWORD *)ContextPointer + 32LL);
  v30 = v10;
  v11 = *(_QWORD *)(v10 + 48);
  if ( a3 < 0x14 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 87, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids);
      v8 = a1;
    }
    if ( v11 )
      DrDevice::CompleteBusyExchange(v8, v9, 3221225862LL, 0);
    else
      DrDevice::DiscardBusyExchange(v8, v9);
    goto LABEL_71;
  }
  if ( (a2[3] & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 95, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids);
      v8 = a1;
    }
    if ( v11 )
    {
      DrDevice::CompleteBusyExchange(v8, v9, a2[3], 0);
    }
    else
    {
      ExAcquireFastMutex(&DrMutex);
      v26 = *((_QWORD *)*v9 + 4);
      *((_QWORD *)*v9 + 4) = 0;
      ExReleaseFastMutex(&DrMutex);
      v27 = *(_QWORD *)(a1 + 32);
      ContextPointer = 0;
      ExAcquireFastMutex(&DrMutex);
      v28 = *(struct _RX_MID_ATLAS **)(v27 + 720);
      if ( v28 )
      {
        RxMapAndDissociateMidFromContext(v28, *((_WORD *)*v9 + 24), (PVOID *)&ContextPointer);
        if ( ContextPointer )
          RefCount::Release(ContextPointer);
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_e59448592ec538b831cf1e49bf008190_Traceguids);
      }
      ExReleaseFastMutex(&DrMutex);
      if ( v26 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v26 + 16LL))(v26, 1);
    }
    *v5 = 1;
    goto LABEL_16;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 88, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids);
    v8 = a1;
  }
  v12 = *(_DWORD *)(v10 + 40);
  v13 = a2[4] - v12;
  v14 = a3 - 20;
  if ( a3 - 20 > v13 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_dd(
        WPP_GLOBAL_Control->AttachedDevice,
        89,
        WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids,
        v14,
        a2[4] - v12);
      v8 = a1;
    }
    if ( v11 )
      DrDevice::CompleteBusyExchange(v8, v9, 3221225862LL, 0);
    else
      DrDevice::DiscardBusyExchange(v8, v9);
    v5 = a4;
LABEL_71:
    *v5 = 0;
    SmartPtr<DrFile>::~SmartPtr<DrFile>(v9);
    return 3221225862LL;
  }
  if ( !v11 )
    goto LABEL_9;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 90, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids);
    v8 = a1;
  }
  if ( v13 <= *(_DWORD *)(v11 + 572) )
  {
    v15 = a2[4];
    *(_QWORD *)(v11 + 184) = v15;
    if ( v15 && a3 != 20 )
    {
      v20 = a2 + 5;
      v21 = *(_QWORD *)(v11 + 40);
      v22 = 0;
      if ( (*(_DWORD *)(v11 + 540) & 3) != 0 )
      {
        if ( (*(_DWORD *)(v11 + 540) & 3) == 1 || (*(_DWORD *)(v11 + 540) & 3) == 2 )
        {
          if ( !v21 )
            goto LABEL_22;
          v21 = *(_QWORD *)(v21 + 8);
        }
        else
        {
          if ( (*(_DWORD *)(v11 + 540) & 3) != 3 )
            goto LABEL_22;
          v21 = *(_QWORD *)(v30 + 64);
          if ( !v21 )
            goto LABEL_22;
        }
        if ( (*(_BYTE *)(v21 + 10) & 5) == 0 )
        {
          v22 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v21, 0, MmCached, 0, 0, 0x40000010u);
          v20 = a2 + 5;
          goto LABEL_22;
        }
      }
      else if ( !v21 )
      {
LABEL_22:
        if ( !v22 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 92, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids);
            v20 = a2 + 5;
          }
          v22 = *(char **)(v11 + 560);
        }
        memmove(&v22[*(unsigned int *)(v30 + 40)], v20, v14);
        v16 = v30;
        *(_DWORD *)(v30 + 40) += v14;
        v8 = a1;
        goto LABEL_10;
      }
      v22 = *(char **)(v21 + 24);
      goto LABEL_22;
    }
LABEL_9:
    v16 = v30;
LABEL_10:
    if ( v14 == v13 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          94,
          WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids,
          *(unsigned int *)(v16 + 40));
        v8 = a1;
      }
      if ( v11 )
      {
        DrDevice::CompleteBusyExchange(v8, v9, a2[3], a2[4]);
        *a4 = 1;
      }
      else
      {
        ExAcquireFastMutex(&DrMutex);
        v23 = *((_QWORD *)*v9 + 4);
        *((_QWORD *)*v9 + 4) = 0;
        ExReleaseFastMutex(&DrMutex);
        v24 = *(_QWORD *)(a1 + 32);
        ContextPointer = 0;
        ExAcquireFastMutex(&DrMutex);
        v25 = *(struct _RX_MID_ATLAS **)(v24 + 720);
        if ( v25 )
        {
          RxMapAndDissociateMidFromContext(v25, *((_WORD *)*v9 + 24), (PVOID *)&ContextPointer);
          if ( ContextPointer )
            RefCount::Release(ContextPointer);
        }
        else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_e59448592ec538b831cf1e49bf008190_Traceguids);
        }
        ExReleaseFastMutex(&DrMutex);
        if ( v23 )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v23 + 16LL))(v23, 1);
        *a4 = 1;
      }
    }
    else
    {
      v17 = 0;
      ExAcquireFastMutex(&DrMutex);
      v18 = *((_QWORD *)*v9 + 4);
      *(_DWORD *)(v18 + 24) = 0;
      if ( *(_DWORD *)(v18 + 28) && *(_QWORD *)(v18 + 48) )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 65, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids);
        v17 = *(struct _RX_CONTEXT **)(v18 + 48);
        *(_QWORD *)(v18 + 48) = 0;
        v17->MRxContext[2] = 0;
      }
      if ( *(_DWORD *)(v18 + 32) )
        *((_QWORD *)*v9 + 4) = 0;
      ExReleaseFastMutex(&DrMutex);
      if ( v17 )
      {
        DrDevice::CompleteRxContext(v17, -1073741536, 0);
        if ( *(_DWORD *)(v18 + 32) )
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v18 + 16LL))(v18, 1);
      }
      DrSession::ReadMore(*(DrSession **)(*(_QWORD *)(a1 + 32) + 736LL), 0x14u, 0);
      *a4 = 0;
    }
LABEL_16:
    if ( *v9 )
      RefCount::Release(*v9);
    return 0;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 91, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids);
    v8 = a1;
  }
  DrDevice::CompleteBusyExchange(v8, v9, 3221225862LL, 0);
  *a4 = 0;
  if ( *v9 )
    RefCount::Release(*v9);
  return 3221225862LL;
}

```

## disassembly

```asm
0x140023500  mov     [rsp+arg_18], r9
0x140023505  mov     [rsp+arg_0], rcx
0x14002350a  push    rbx
0x14002350b  push    rsi
0x14002350c  push    rdi
0x14002350d  push    r12
0x14002350f  push    r13
0x140023511  push    r14
0x140023513  push    r15
0x140023515  sub     rsp, 30h
0x140023519  mov     r12, r9
0x14002351c  mov     edi, r8d
0x14002351f  mov     rsi, rdx
0x140023522  mov     r10, rcx
0x140023525  mov     r15, [rsp+68h+ContextPointer]
0x14002352d  mov     rax, [r15]
0x140023530  mov     rbx, [rax+20h]
0x140023534  mov     [rsp+68h+arg_8], rbx
0x140023539  mov     r14, [rbx+30h]
0x14002353d  cmp     r8d, 14h
0x140023541  jb      loc_140023A39
0x140023547  cmp     dword ptr [rdx+0Ch], 0
0x14002354b  jl      loc_140023892
0x140023551  lea     r13, WPP_GLOBAL_Control
0x140023558  mov     rcx, cs:WPP_GLOBAL_Control
0x14002355f  cmp     rcx, r13
0x140023562  jnz     loc_1400237AC
0x140023568  mov     eax, [rbx+28h]
0x14002356b  mov     ebx, [rsi+10h]
0x14002356e  sub     ebx, eax
0x140023570  lea     r12d, [rdi-14h]
0x140023574  cmp     r12d, ebx
0x140023577  ja      loc_140023A8E
0x14002357d  test    r14, r14
0x140023580  jz      short loc_1400235B2
0x140023582  mov     rcx, cs:WPP_GLOBAL_Control
0x140023589  cmp     rcx, r13
0x14002358c  jnz     loc_140023727
0x140023592  cmp     ebx, [r14+23Ch]
0x140023599  ja      loc_140023750
0x14002359f  mov     eax, [rsi+10h]
0x1400235a2  mov     [r14+0B8h], rax
0x1400235a9  test    rax, rax
0x1400235ac  jnz     loc_140023659
0x1400235b2  xor     edi, edi
0x1400235b4  mov     rax, [rsp+68h+arg_8]
0x1400235b9  cmp     r12d, ebx
0x1400235bc  jz      loc_1400237D5
0x1400235c2  mov     rsi, rdi
0x1400235c5  lea     rcx, ?DrMutex@@3U_FAST_MUTEX@@A; FastMutex
0x1400235cc  call    cs:__imp_ExAcquireFastMutex
0x1400235d3  nop     dword ptr [rax+rax+00h]
0x1400235d8  mov     rbx, [r15]
0x1400235db  mov     rbx, [rbx+20h]
0x1400235df  mov     [rbx+18h], edi
0x1400235e2  cmp     dword ptr [rbx+1Ch], 0
0x1400235e6  jnz     loc_140023C0F
0x1400235ec  cmp     dword ptr [rbx+20h], 0
0x1400235f0  jnz     loc_140023C55
0x1400235f6  lea     rcx, ?DrMutex@@3U_FAST_MUTEX@@A; FastMutex
0x1400235fd  call    cs:__imp_ExReleaseFastMutex
0x140023604  nop     dword ptr [rax+rax+00h]
0x140023609  test    rsi, rsi
0x14002360c  jnz     loc_140023C61
0x140023612  mov     rbx, [rsp+68h+arg_0]
0x140023617  mov     rcx, [rbx+20h]
0x14002361b  xor     r8d, r8d; unsigned int
0x14002361e  mov     edx, 14h; unsigned int
0x140023623  mov     rcx, [rcx+2E0h]; this
0x14002362a  call    ?ReadMore@DrSession@@QEAAHKK@Z; DrSession::ReadMore(ulong,ulong)
0x14002362f  mov     rax, [rsp+68h+arg_18]
0x140023637  mov     [rax], edi
0x140023639  mov     rcx, [r15]; this
0x14002363c  test    rcx, rcx
0x14002363f  jz      short loc_140023646
0x140023641  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x140023646  xor     eax, eax
0x140023648  add     rsp, 30h
0x14002364c  pop     r15
0x14002364e  pop     r14
0x140023650  pop     r13
0x140023652  pop     r12
0x140023654  pop     rdi
0x140023655  pop     rsi
0x140023656  pop     rbx
0x140023657  retn
0x140023659  test    r12d, r12d
0x14002365c  jz      loc_1400235B2
0x140023662  lea     r9, [rsi+14h]
0x140023666  mov     eax, [r14+21Ch]
0x14002366d  and     eax, 3
0x140023670  mov     rcx, [r14+28h]
0x140023674  mov     edi, 0
0x140023679  mov     edx, edi; AccessMode
0x14002367b  jnz     loc_1400238CD
0x140023681  test    rcx, rcx
0x140023684  jnz     loc_1400237A3
0x14002368a  test    rdx, rdx
0x14002368d  jz      loc_140023B6E
0x140023693  mov     r8d, r12d; Size
0x140023696  mov     rax, [rsp+68h+arg_8]
0x14002369b  mov     ecx, [rax+28h]
0x14002369e  add     rcx, rdx; void *
0x1400236a1  mov     rdx, r9; Src
0x1400236a4  call    memmove
0x1400236a9  mov     rax, [rsp+68h+arg_8]
0x1400236ae  add     [rax+28h], r12d
0x1400236b2  mov     r10, [rsp+68h+arg_0]
0x1400236b7  jmp     loc_1400235B9
0x1400236bc  lea     rax, WPP_GLOBAL_Control
0x1400236c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400236ca  cmp     rcx, rax
0x1400236cd  jz      short loc_1400236EA
0x1400236cf  cmp     byte ptr [rcx+29h], 2
0x1400236d3  jb      short loc_1400236EA
0x1400236d5  mov     edx, 5Dh ; ']'
0x1400236da  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x1400236e1  mov     rcx, [rcx+18h]
0x1400236e5  call    WPP_SF_
0x1400236ea  xor     r9d, r9d
0x1400236ed  mov     r8d, 0C000000Dh
0x1400236f3  mov     rdx, [rsp+68h+ContextPointer]
0x1400236fb  mov     rcx, [rsp+68h+arg_0]
0x140023700  call    ?CompleteBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@JK@Z; DrDevice::CompleteBusyExchange(SmartPtr<DrExchange> &,long,ulong)
0x140023705  mov     rax, [rsp+68h+arg_18]
0x14002370d  mov     dword ptr [rax], 1
0x140023713  mov     rcx, [rsp+68h+ContextPointer]
0x14002371b  call    ??1?$SmartPtr@VDrFile@@@@QEAA@XZ; SmartPtr<DrFile>::~SmartPtr<DrFile>(void)
0x140023720  xor     eax, eax
0x140023722  jmp     loc_140023648
0x140023727  cmp     byte ptr [rcx+29h], 5
0x14002372b  jb      loc_140023592
0x140023731  mov     edx, 5Ah ; 'Z'
0x140023736  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x14002373d  mov     rcx, [rcx+18h]
0x140023741  call    WPP_SF_
0x140023746  mov     r10, [rsp+68h+arg_0]
0x14002374b  jmp     loc_140023592
0x140023750  mov     rcx, cs:WPP_GLOBAL_Control
0x140023757  cmp     rcx, r13
0x14002375a  jnz     loc_140023B01
0x140023760  xor     r9d, r9d
0x140023763  mov     r8d, 0C0000186h
0x140023769  mov     rdx, r15
0x14002376c  mov     rcx, r10
0x14002376f  call    ?CompleteBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@JK@Z; DrDevice::CompleteBusyExchange(SmartPtr<DrExchange> &,long,ulong)
0x140023774  xor     edi, edi
0x140023776  mov     rax, [rsp+68h+arg_18]
0x14002377e  mov     [rax], edi
0x140023780  mov     rcx, [r15]; this
0x140023783  test    rcx, rcx
0x140023786  jz      short loc_14002378D
0x140023788  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x14002378d  mov     eax, 0C0000186h
0x140023792  add     rsp, 30h
0x140023796  pop     r15
0x140023798  pop     r14
0x14002379a  pop     r13
0x14002379c  pop     r12
0x14002379e  pop     rdi
0x14002379f  pop     rsi
0x1400237a0  pop     rbx
0x1400237a1  retn
0x1400237a3  mov     rdx, [rcx+18h]
0x1400237a7  jmp     loc_14002368A
0x1400237ac  cmp     byte ptr [rcx+29h], 5
0x1400237b0  jb      loc_140023568
0x1400237b6  mov     edx, 58h ; 'X'
0x1400237bb  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
0x1400237c2  mov     rcx, [rcx+18h]
0x1400237c6  call    WPP_SF_
0x1400237cb  mov     r10, [rsp+68h+arg_0]
0x1400237d0  jmp     loc_140023568
0x1400237d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400237dc  cmp     rcx, r13
0x1400237df  jnz     loc_140023BA5
0x1400237e5  test    r14, r14
0x1400237e8  jnz     loc_1400238FF
0x1400237ee  lea     rcx, ?DrMutex@@3U_FAST_MUTEX@@A; FastMutex
0x1400237f5  call    cs:__imp_ExAcquireFastMutex
0x1400237fc  nop     dword ptr [rax+rax+00h]
0x140023801  mov     rax, [r15]
0x140023804  mov     rsi, [rax+20h]
0x140023808  mov     [rax+20h], rdi
0x14002380c  lea     rcx, ?DrMutex@@3U_FAST_MUTEX@@A; FastMutex
0x140023813  call    cs:__imp_ExReleaseFastMutex
0x14002381a  nop     dword ptr [rax+rax+00h]
0x14002381f  mov     rbx, [rsp+68h+arg_0]
0x140023824  mov     rbx, [rbx+20h]
0x140023828  mov     [rsp+68h+ContextPointer], rdi
0x140023830  lea     rcx, ?DrMutex@@3U_FAST_MUTEX@@A; FastMutex
0x140023837  call    cs:__imp_ExAcquireFastMutex
0x14002383e  nop     dword ptr [rax+rax+00h]
0x140023843  mov     rcx, [rbx+2D0h]; MidAtlas
0x14002384a  test    rcx, rcx
0x14002384d  jnz     loc_1400239CD
0x140023853  mov     rcx, cs:WPP_GLOBAL_Control
0x14002385a  cmp     rcx, r13
0x14002385d  jnz     loc_140023BD2
0x140023863  lea     rcx, ?DrMutex@@3U_FAST_MUTEX@@A; FastMutex
0x14002386a  call    cs:__imp_ExReleaseFastMutex
0x140023871  nop     dword ptr [rax+rax+00h]
0x140023876  test    rsi, rsi
0x140023879  jnz     loc_140023BF6
0x14002387f  mov     rax, [rsp+68h+arg_18]
0x140023887  mov     dword ptr [rax], 1
0x14002388d  jmp     loc_140023639
0x140023892  lea     r13, WPP_GLOBAL_Control
0x140023899  mov     rcx, cs:WPP_GLOBAL_Control
0x1400238a0  cmp     rcx, r13
0x1400238a3  jnz     loc_140023C94
0x1400238a9  test    r14, r14
0x1400238ac  jz      short loc_140023925
0x1400238ae  xor     r9d, r9d
0x1400238b1  mov     r8d, [rsi+0Ch]
0x1400238b5  mov     rdx, r15
0x1400238b8  mov     rcx, r10
0x1400238bb  call    ?CompleteBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@JK@Z; DrDevice::CompleteBusyExchange(SmartPtr<DrExchange> &,long,ulong)
0x1400238c0  mov     dword ptr [r12], 1
0x1400238c8  jmp     loc_140023639
0x1400238cd  sub     eax, 1
0x1400238d0  jz      loc_140023B2A
0x1400238d6  sub     eax, 1
0x1400238d9  jz      loc_140023B2A
0x1400238df  cmp     eax, 1
0x1400238e2  jnz     loc_14002368A
0x1400238e8  mov     rax, [rsp+68h+arg_8]
0x1400238ed  mov     rcx, [rax+40h]
0x1400238f1  test    rcx, rcx
0x1400238f4  jz      loc_14002368A
0x1400238fa  jmp     loc_140023B37
0x1400238ff  mov     r9d, [rsi+10h]
0x140023903  mov     r8d, [rsi+0Ch]
0x140023907  mov     rdx, r15
0x14002390a  mov     rcx, r10
0x14002390d  call    ?CompleteBusyExchange@DrDevice@@IEAAXAEAV?$SmartPtr@VDrExchange@@@@JK@Z; DrDevice::CompleteBusyExchange(SmartPtr<DrExchange> &,long,ulong)
0x140023912  mov     rax, [rsp+68h+arg_18]
0x14002391a  mov     dword ptr [rax], 1
0x140023920  jmp     loc_140023639
0x140023925  lea     rcx, ?DrMutex@@3U_FAST_MUTEX@@A; FastMutex
0x14002392c  call    cs:__imp_ExAcquireFastMutex
0x140023933  nop     dword ptr [rax+rax+00h]
0x140023938  mov     rax, [r15]
0x14002393b  mov     rsi, [rax+20h]
0x14002393f  xor     edi, edi
0x140023941  mov     [rax+20h], rdi
0x140023945  lea     rcx, ?DrMutex@@3U_FAST_MUTEX@@A; FastMutex
0x14002394c  call    cs:__imp_ExReleaseFastMutex
0x140023953  nop     dword ptr [rax+rax+00h]
0x140023958  mov     rbx, [rsp+68h+arg_0]
0x14002395d  mov     rbx, [rbx+20h]
0x140023961  mov     [rsp+68h+ContextPointer], rdi
0x140023969  lea     rcx, ?DrMutex@@3U_FAST_MUTEX@@A; FastMutex
0x140023970  call    cs:__imp_ExAcquireFastMutex
0x140023977  nop     dword ptr [rax+rax+00h]
0x14002397c  mov     rcx, [rbx+2D0h]; MidAtlas
0x140023983  test    rcx, rcx
0x140023986  jnz     short loc_140023A03
0x140023988  mov     rcx, cs:WPP_GLOBAL_Control
0x14002398f  cmp     rcx, r13
0x140023992  jnz     loc_140023CBD
0x140023998  lea     rcx, ?DrMutex@@3U_FAST_MUTEX@@A; FastMutex
0x14002399f  call    cs:__imp_ExReleaseFastMutex
0x1400239a6  nop     dword ptr [rax+rax+00h]
0x1400239ab  test    rsi, rsi
0x1400239ae  jz      loc_1400238C0
0x1400239b4  mov     rax, [rsi]
0x1400239b7  mov     rax, [rax+10h]
0x1400239bb  mov     edx, 1
0x1400239c0  mov     rcx, rsi
0x1400239c3  call    _guard_dispatch_icall
0x1400239c8  jmp     loc_1400238C0
0x1400239cd  mov     rdx, [r15]
0x1400239d0  lea     r8, [rsp+68h+ContextPointer]; ContextPointer
0x1400239d8  movzx   edx, word ptr [rdx+30h]; Mid
0x1400239dc  call    cs:__imp_RxMapAndDissociateMidFromContext
0x1400239e3  nop     dword ptr [rax+rax+00h]
0x1400239e8  mov     rcx, [rsp+68h+ContextPointer]; this
0x1400239f0  test    rcx, rcx
0x1400239f3  jz      loc_140023863
0x1400239f9  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x1400239fe  jmp     loc_140023863
0x140023a03  mov     rdx, [r15]
0x140023a06  lea     r8, [rsp+68h+ContextPointer]; ContextPointer
0x140023a0e  movzx   edx, word ptr [rdx+30h]; Mid
0x140023a12  call    cs:__imp_RxMapAndDissociateMidFromContext
0x140023a19  nop     dword ptr [rax+rax+00h]
0x140023a1e  mov     rcx, [rsp+68h+ContextPointer]; this
0x140023a26  test    rcx, rcx
0x140023a29  jz      loc_140023998
0x140023a2f  call    ?Release@RefCount@@QEAAXXZ; RefCount::Release(void)
0x140023a34  jmp     loc_140023998
0x140023a39  lea     r13, WPP_GLOBAL_Control
0x140023a40  mov     rcx, cs:WPP_GLOBAL_Control
0x140023a47  cmp     rcx, r13
0x140023a4a  jz      short loc_140023A6C
0x140023a4c  cmp     byte ptr [rcx+29h], 2
0x140023a50  jb      short loc_140023A6C
0x140023a52  mov     edx, 57h ; 'W'
0x140023a57  lea     r8, WPP_85c2389aa0203b96a2708d64b3a7b42b_Traceguids
  ... truncated ...
```
