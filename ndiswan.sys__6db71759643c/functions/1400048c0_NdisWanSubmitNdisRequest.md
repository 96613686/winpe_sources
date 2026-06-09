# NdisWanSubmitNdisRequest

- ea: `0x1400048c0`
- end: `0x140004aaf`
- name: `NdisWanSubmitNdisRequest`
- size: `495`
- prototype: ``
- caller_count: `9`
- callee_count: `3`
- tags: ``

## callers

- `0x140003c30`
- `0x1400040a0`
- `0x140008c80`
- `0x14000ec48`
- `0x140011780`
- `0x1400288a0`
- `0x14002aa40`
- `0x14002b270`
- `0x140035f70`

## callees

- `0x1400048c0`
- `0x14000a2c0`
- `0x14000a648`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x140004969`
- `ntoskrnl!KeClearEvent` at `0x140004969`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000494f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000494f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004a12`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004a5a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004a12`
- `ntoskrnl!KeReleaseSpinLock` at `0x140004a5a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400049e6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400049e6`
- `NDIS!NdisCoOidRequest` at `0x1400049ce`
- `NDIS!NdisCoOidRequest` at `0x1400049ce`
- `NDIS!NdisOidRequest` at `0x14000491b`
- `NDIS!NdisOidRequest` at `0x14000491b`
- `NDIS!NdisSetEvent` at `0x140004a9e`
- `NDIS!NdisSetEvent` at `0x140004a9e`

## pseudocode

```c
__int64 __fastcall NdisWanSubmitNdisRequest(__int64 a1, __int64 a2)
{
  int v2; // ebp
  void *v5; // r8
  int v6; // edi
  void *v7; // rcx
  NDIS_STATUS v8; // eax
  unsigned int v9; // r14d
  KIRQL v11; // al
  int v12; // edx
  KSPIN_LOCK *v13; // rcx

  v2 = *(_DWORD *)(a2 + 20);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0xAu,
      (__int64)WPP_20bf124fffdd3be673ce951aa7b13aa4_Traceguids,
      a2);
  }
  if ( v2 != 1 )
  {
    v11 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 504));
    v12 = *(_DWORD *)(a1 + 20);
    v13 = (KSPIN_LOCK *)(a1 + 504);
    *(_BYTE *)(a1 + 512) = v11;
    if ( (v12 & 2) != 0 )
    {
      KeReleaseSpinLock(v13, v11);
      return 3221225473LL;
    }
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 16));
    KeReleaseSpinLock(v13, *(_BYTE *)(a1 + 512));
  }
  v5 = *(void **)(a2 + 40);
  v6 = *(_DWORD *)(a2 + 16);
  v7 = *(void **)(a1 + 56);
  if ( v5 )
    v8 = NdisCoOidRequest(v7, *(NDIS_HANDLE *)(a2 + 32), v5, 0, (PNDIS_OID_REQUEST)(a2 + 48));
  else
    v8 = NdisOidRequest(v7, (PNDIS_OID_REQUEST)(a2 + 48));
  v9 = v8;
  if ( v6 == 1 && v8 == 259 )
  {
    KeWaitForSingleObject((PVOID)(a2 + 304), Executive, 0, 1u, 0);
    v9 = *(_DWORD *)(a2 + 296);
    KeClearEvent((PRKEVENT)(a2 + 304));
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0xBu,
      (__int64)WPP_20bf124fffdd3be673ce951aa7b13aa4_Traceguids,
      v9);
  }
  if ( v2 != 1 && _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), 0xFFFFFFFF) == 1 )
    NdisSetEvent((PNDIS_EVENT)(a1 + 552));
  return v9;
}

```

## disassembly

```asm
0x1400048c0  mov     [rsp+arg_10], rbx
0x1400048c5  push    rbp
0x1400048c6  push    rsi
0x1400048c7  push    r15
0x1400048c9  sub     rsp, 30h
0x1400048cd  mov     ebp, [rdx+14h]
0x1400048d0  mov     rsi, rdx
0x1400048d3  mov     rbx, rcx
0x1400048d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400048dd  lea     r15, WPP_GLOBAL_Control
0x1400048e4  cmp     rcx, r15
0x1400048e7  jnz     loc_140004A23
0x1400048ed  mov     [rsp+48h+arg_0], rdi
0x1400048f2  cmp     ebp, 1
0x1400048f5  jnz     loc_1400049DF
0x1400048fb  mov     r8, [rsi+28h]; NdisVcHandle
0x1400048ff  lea     rax, [rsi+30h]
0x140004903  mov     edi, [rsi+10h]
0x140004906  mov     rcx, [rbx+38h]; NdisBindingHandle
0x14000490a  mov     [rsp+48h+arg_8], r14
0x14000490f  test    r8, r8
0x140004912  jnz     loc_1400049C2
0x140004918  mov     rdx, rax; OidRequest
0x14000491b  call    cs:__imp_NdisOidRequest
0x140004922  nop     dword ptr [rax+rax+00h]
0x140004927  mov     r14d, eax
0x14000492a  cmp     edi, 1
0x14000492d  jnz     short loc_140004975
0x14000492f  cmp     eax, 103h
0x140004934  jnz     short loc_140004975
0x140004936  movzx   r9d, dil; Alertable
0x14000493a  mov     [rsp+48h+Timeout], 0; Timeout
0x140004943  xor     r8d, r8d; WaitMode
0x140004946  lea     rcx, [rsi+130h]; Object
0x14000494d  xor     edx, edx; WaitReason
0x14000494f  call    cs:__imp_KeWaitForSingleObject
0x140004956  nop     dword ptr [rax+rax+00h]
0x14000495b  mov     r14d, [rsi+128h]
0x140004962  lea     rcx, [rsi+130h]; Event
0x140004969  call    cs:__imp_KeClearEvent
0x140004970  nop     dword ptr [rax+rax+00h]
0x140004975  mov     rcx, cs:WPP_GLOBAL_Control
0x14000497c  cmp     rcx, r15
0x14000497f  jz      short loc_14000498E
0x140004981  test    dword ptr [rcx+2Ch], 80000h
0x140004988  jnz     loc_140004A70
0x14000498e  cmp     ebp, 1
0x140004991  jz      short loc_1400049A6
0x140004993  mov     eax, 0FFFFFFFFh
0x140004998  lock xadd [rbx+10h], eax
0x14000499d  cmp     eax, 1
0x1400049a0  jz      loc_140004A97
0x1400049a6  mov     eax, r14d
0x1400049a9  mov     r14, [rsp+48h+arg_8]
0x1400049ae  mov     rdi, [rsp+48h+arg_0]
0x1400049b3  mov     rbx, [rsp+48h+arg_10]
0x1400049b8  add     rsp, 30h
0x1400049bc  pop     r15
0x1400049be  pop     rsi
0x1400049bf  pop     rbp
0x1400049c0  retn
0x1400049c2  mov     rdx, [rsi+20h]; NdisAfHandle
0x1400049c6  xor     r9d, r9d; NdisPartyHandle
0x1400049c9  mov     [rsp+48h+Timeout], rax; OidRequest
0x1400049ce  call    cs:__imp_NdisCoOidRequest
0x1400049d5  nop     dword ptr [rax+rax+00h]
0x1400049da  jmp     loc_140004927
0x1400049df  lea     rcx, [rbx+1F8h]; SpinLock
0x1400049e6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400049ed  nop     dword ptr [rax+rax+00h]
0x1400049f2  mov     edx, [rbx+14h]
0x1400049f5  lea     rcx, [rbx+1F8h]; SpinLock
0x1400049fc  mov     [rbx+200h], al
0x140004a02  test    dl, 2
0x140004a05  jnz     short loc_140004A57
0x140004a07  lock inc dword ptr [rbx+10h]
0x140004a0b  movzx   edx, byte ptr [rbx+200h]; NewIrql
0x140004a12  call    cs:__imp_KeReleaseSpinLock
0x140004a19  nop     dword ptr [rax+rax+00h]
0x140004a1e  jmp     loc_1400048FB
0x140004a23  test    dword ptr [rcx+2Ch], 80000h
0x140004a2a  jz      loc_1400048ED
0x140004a30  cmp     byte ptr [rcx+29h], 5
0x140004a34  jb      loc_1400048ED
0x140004a3a  mov     rcx, [rcx+18h]
0x140004a3e  lea     r8, WPP_20bf124fffdd3be673ce951aa7b13aa4_Traceguids
0x140004a45  mov     edx, 0Ah
0x140004a4a  mov     r9, rsi
0x140004a4d  call    WPP_SF_q
0x140004a52  jmp     loc_1400048ED
0x140004a57  movzx   edx, al; NewIrql
0x140004a5a  call    cs:__imp_KeReleaseSpinLock
0x140004a61  nop     dword ptr [rax+rax+00h]
0x140004a66  mov     eax, 0C0000001h
0x140004a6b  jmp     loc_1400049AE
0x140004a70  cmp     byte ptr [rcx+29h], 5
0x140004a74  jb      loc_14000498E
0x140004a7a  mov     rcx, [rcx+18h]
0x140004a7e  lea     r8, WPP_20bf124fffdd3be673ce951aa7b13aa4_Traceguids
0x140004a85  mov     edx, 0Bh
0x140004a8a  mov     r9d, r14d
0x140004a8d  call    WPP_SF_d
0x140004a92  jmp     loc_14000498E
0x140004a97  lea     rcx, [rbx+228h]; Event
0x140004a9e  call    cs:__imp_NdisSetEvent
0x140004aa5  nop     dword ptr [rax+rax+00h]
0x140004aaa  jmp     loc_1400049A6
```
