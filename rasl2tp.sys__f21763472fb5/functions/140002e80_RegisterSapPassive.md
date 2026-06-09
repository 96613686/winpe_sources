# RegisterSapPassive

- ea: `0x140002e80`
- end: `0x140003048`
- name: `RegisterSapPassive`
- size: `456`
- prototype: `__int64 __fastcall(NDIS_HANDLE CallMgrSapContext, NDIS_HANDLE NdisIoWorkItemHandle)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140001850`
- `0x140001870`
- `0x140002e80`
- `0x140003050`
- `0x140003080`
- `0x140018f2c`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140003014`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003014`
- `ntoskrnl!MmLockPagableDataSection` at `0x140002ed6`
- `ntoskrnl!MmLockPagableDataSection` at `0x140002ed6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002f8f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002f8f`
- `NDIS!NdisCmRegisterSapComplete` at `0x140003030`
- `NDIS!NdisCmRegisterSapComplete` at `0x140003030`
- `NDIS!NdisFreeIoWorkItem` at `0x140002eec`
- `NDIS!NdisFreeIoWorkItem` at `0x140002eec`

## pseudocode

```c
void __fastcall RegisterSapPassive(char *CallMgrSapContext, NDIS_HANDLE NdisIoWorkItemHandle)
{
  unsigned int v4; // eax
  __int64 Timer_high; // rdx
  NDIS_STATUS v6; // edi
  int v7; // esi
  KIRQL v8; // al
  void *v9; // rbp

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids);
  }
  if ( !g_fPagesLocked )
  {
    MmLockPagableDataSection(CreateTunnelCb);
    g_fPagesLocked = 1;
  }
  NdisFreeIoWorkItem(NdisIoWorkItemHandle);
  v4 = TransportOpen(CallMgrSapContext + 240, 0);
  v6 = v4;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (Timer_high & 4) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids, v4);
    }
  }
  LOBYTE(Timer_high) = 1;
  v7 = TransportOpen(CallMgrSapContext + 240, Timer_high);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids, (unsigned int)v6);
  }
  if ( v6 >= 0 || v7 >= 0 )
    v6 = 0;
  v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)CallMgrSapContext + 48);
  v9 = (void *)*((_QWORD *)CallMgrSapContext + 42);
  CallMgrSapContext[392] = v8;
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        15,
        WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids,
        (unsigned int)v6);
    }
    *((_QWORD *)CallMgrSapContext + 42) = 0;
  }
  else
  {
    SetFlags(CallMgrSapContext + 8, 16);
    *((_DWORD *)CallMgrSapContext + 95) = 1;
    _InterlockedIncrement((volatile signed __int32 *)CallMgrSapContext + 1);
    _InterlockedIncrement((volatile signed __int32 *)CallMgrSapContext + 94);
  }
  KeReleaseSpinLock((PKSPIN_LOCK)CallMgrSapContext + 48, CallMgrSapContext[392]);
  DereferenceAdapter(CallMgrSapContext);
  NdisCmRegisterSapComplete(v6, v9, CallMgrSapContext);
}

```

## disassembly

```asm
0x140002e80  push    rbx
0x140002e82  push    rbp
0x140002e83  push    rsi
0x140002e84  push    rdi
0x140002e85  push    r12
0x140002e87  sub     rsp, 20h
0x140002e8b  mov     rdi, rdx
0x140002e8e  mov     rbx, rcx
0x140002e91  mov     rcx, cs:WPP_GLOBAL_Control
0x140002e98  lea     r12, WPP_GLOBAL_Control
0x140002e9f  cmp     rcx, r12
0x140002ea2  jz      short loc_140002EC6
0x140002ea4  mov     eax, [rcx+2Ch]
0x140002ea7  test    al, 4
0x140002ea9  jz      short loc_140002EC6
0x140002eab  cmp     byte ptr [rcx+29h], 1
0x140002eaf  jb      short loc_140002EC6
0x140002eb1  mov     rcx, [rcx+18h]
0x140002eb5  lea     r8, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids
0x140002ebc  mov     edx, 0Ch
0x140002ec1  call    WPP_SF_
0x140002ec6  cmp     cs:g_fPagesLocked, 0
0x140002ecd  jnz     short loc_140002EE9
0x140002ecf  lea     rcx, CreateTunnelCb; AddressWithinSection
0x140002ed6  call    cs:__imp_MmLockPagableDataSection
0x140002edd  nop     dword ptr [rax+rax+00h]
0x140002ee2  mov     cs:g_fPagesLocked, 1
0x140002ee9  mov     rcx, rdi; NdisIoWorkItemHandle
0x140002eec  call    cs:__imp_NdisFreeIoWorkItem
0x140002ef3  nop     dword ptr [rax+rax+00h]
0x140002ef8  lea     rsi, [rbx+0F0h]
0x140002eff  xor     edx, edx
0x140002f01  mov     rcx, rsi
0x140002f04  call    TransportOpen
0x140002f09  mov     edi, eax
0x140002f0b  mov     rcx, cs:WPP_GLOBAL_Control
0x140002f12  cmp     rcx, r12
0x140002f15  jz      short loc_140002F3D
0x140002f17  mov     edx, [rcx+2Ch]
0x140002f1a  test    dl, 4
0x140002f1d  jz      short loc_140002F3D
0x140002f1f  cmp     byte ptr [rcx+29h], 1
0x140002f23  jb      short loc_140002F3D
0x140002f25  mov     rcx, [rcx+18h]
0x140002f29  lea     r8, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids
0x140002f30  mov     edx, 0Dh
0x140002f35  mov     r9d, eax
0x140002f38  call    WPP_SF_d
0x140002f3d  mov     dl, 1
0x140002f3f  mov     rcx, rsi
0x140002f42  call    TransportOpen
0x140002f47  mov     esi, eax
0x140002f49  mov     rcx, cs:WPP_GLOBAL_Control
0x140002f50  cmp     rcx, r12
0x140002f53  jz      short loc_140002F7B
0x140002f55  mov     edx, [rcx+2Ch]
0x140002f58  test    dl, 4
0x140002f5b  jz      short loc_140002F7B
0x140002f5d  cmp     byte ptr [rcx+29h], 1
0x140002f61  jb      short loc_140002F7B
0x140002f63  mov     rcx, [rcx+18h]
0x140002f67  lea     r8, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids
0x140002f6e  mov     edx, 0Eh
0x140002f73  mov     r9d, edi
0x140002f76  call    WPP_SF_d
0x140002f7b  test    edi, edi
0x140002f7d  jns     short loc_140002F83
0x140002f7f  test    esi, esi
0x140002f81  js      short loc_140002F85
0x140002f83  xor     edi, edi
0x140002f85  lea     rsi, [rbx+180h]
0x140002f8c  mov     rcx, rsi; SpinLock
0x140002f8f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002f96  nop     dword ptr [rax+rax+00h]
0x140002f9b  mov     rbp, [rbx+150h]
0x140002fa2  mov     [rbx+188h], al
0x140002fa8  test    edi, edi
0x140002faa  jnz     short loc_140002FCF
0x140002fac  lea     rcx, [rbx+8]
0x140002fb0  lea     edx, [rdi+10h]
0x140002fb3  call    SetFlags
0x140002fb8  mov     dword ptr [rbx+17Ch], 1
0x140002fc2  lock inc dword ptr [rbx+4]
0x140002fc6  lock inc dword ptr [rbx+178h]
0x140002fcd  jmp     short loc_14000300B
0x140002fcf  mov     rcx, cs:WPP_GLOBAL_Control
0x140002fd6  cmp     rcx, r12
0x140002fd9  jz      short loc_140003000
0x140002fdb  mov     eax, [rcx+2Ch]
0x140002fde  test    al, 4
0x140002fe0  jz      short loc_140003000
0x140002fe2  cmp     byte ptr [rcx+29h], 1
0x140002fe6  jb      short loc_140003000
0x140002fe8  mov     rcx, [rcx+18h]
0x140002fec  lea     r8, WPP_1bbc90e225963caa466f1adf6e6a9e48_Traceguids
0x140002ff3  mov     edx, 0Fh
0x140002ff8  mov     r9d, edi
0x140002ffb  call    WPP_SF_d
0x140003000  mov     qword ptr [rbx+150h], 0
0x14000300b  mov     dl, [rbx+188h]; NewIrql
0x140003011  mov     rcx, rsi; SpinLock
0x140003014  call    cs:__imp_KeReleaseSpinLock
0x14000301b  nop     dword ptr [rax+rax+00h]
0x140003020  mov     rcx, rbx
0x140003023  call    DereferenceAdapter
0x140003028  mov     r8, rbx; CallMgrSapContext
0x14000302b  mov     rdx, rbp; NdisSapHandle
0x14000302e  mov     ecx, edi; Status
0x140003030  call    cs:__imp_NdisCmRegisterSapComplete
0x140003037  nop     dword ptr [rax+rax+00h]
0x14000303c  add     rsp, 20h
0x140003040  pop     r12
0x140003042  pop     rdi
0x140003043  pop     rsi
0x140003044  pop     rbp
0x140003045  pop     rbx
0x140003046  retn
```
