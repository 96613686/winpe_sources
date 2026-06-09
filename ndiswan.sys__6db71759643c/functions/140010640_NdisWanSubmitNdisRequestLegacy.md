# NdisWanSubmitNdisRequestLegacy

- ea: `0x140010640`
- end: `0x1400107d4`
- name: `NdisWanSubmitNdisRequestLegacy`
- size: `404`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x14000f2d0`
- `0x140010b40`
- `0x1400288a0`
- `0x14002b270`
- `0x140035f70`

## callees

- `0x14000a2c0`
- `0x14000a648`
- `0x140010640`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x140010756`
- `ntoskrnl!KeClearEvent` at `0x140010756`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001073d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001073d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400106cb`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400106eb`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400106cb`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400106eb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400106ac`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400106ac`
- `NDIS!NdisRequest` at `0x140010707`
- `NDIS!NdisRequest` at `0x140010707`
- `NDIS!NdisSetEvent` at `0x1400107b0`
- `NDIS!NdisSetEvent` at `0x1400107b0`

## pseudocode

```c
__int64 __fastcall NdisWanSubmitNdisRequestLegacy(__int64 a1, __int64 a2)
{
  int v2; // ebp
  KIRQL v5; // al
  int v6; // edx
  KSPIN_LOCK *v7; // rcx
  int v9; // ebx
  unsigned int v10; // [rsp+58h] [rbp+10h] BYREF

  v2 = *(_DWORD *)(a2 + 20);
  v10 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_q(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0xCu,
      (__int64)WPP_20bf124fffdd3be673ce951aa7b13aa4_Traceguids,
      a2);
  }
  if ( v2 != 1 )
  {
    v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 504));
    v6 = *(_DWORD *)(a1 + 20);
    v7 = (KSPIN_LOCK *)(a1 + 504);
    *(_BYTE *)(a1 + 512) = v5;
    if ( (v6 & 2) != 0 )
    {
      KeReleaseSpinLock(v7, v5);
      return 3221225473LL;
    }
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 16));
    KeReleaseSpinLock(v7, *(_BYTE *)(a1 + 512));
  }
  v9 = *(_DWORD *)(a2 + 16);
  NdisRequest(&v10, *(_QWORD *)(a1 + 56), a2 + 48);
  if ( v9 == 1 && v10 == 259 )
  {
    KeWaitForSingleObject((PVOID)(a2 + 240), Executive, 0, 1u, 0);
    v10 = *(_DWORD *)(a2 + 232);
    KeClearEvent((PRKEVENT)(a2 + 240));
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x80000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0xDu,
      (__int64)WPP_20bf124fffdd3be673ce951aa7b13aa4_Traceguids,
      v10);
  }
  if ( v2 != 1 && _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 16), 0xFFFFFFFF) == 1 )
    NdisSetEvent((PNDIS_EVENT)(a1 + 552));
  return v10;
}

```

## disassembly

```asm
0x140010640  mov     [rsp+arg_0], rbx
0x140010645  mov     [rsp+arg_10], rbp
0x14001064a  push    rsi
0x14001064b  push    rdi
0x14001064c  push    r15
0x14001064e  sub     rsp, 30h
0x140010652  mov     ebp, [rdx+14h]
0x140010655  mov     rsi, rdx
0x140010658  mov     rdi, rcx
0x14001065b  mov     [rsp+48h+arg_8], 0
0x140010663  mov     rcx, cs:WPP_GLOBAL_Control
0x14001066a  lea     r15, WPP_GLOBAL_Control
0x140010671  cmp     rcx, r15
0x140010674  jz      short loc_14001069D
0x140010676  test    dword ptr [rcx+2Ch], 80000h
0x14001067d  jz      short loc_14001069D
0x14001067f  cmp     byte ptr [rcx+29h], 5
0x140010683  jb      short loc_14001069D
0x140010685  mov     rcx, [rcx+18h]
0x140010689  lea     r8, WPP_20bf124fffdd3be673ce951aa7b13aa4_Traceguids
0x140010690  mov     edx, 0Ch
0x140010695  mov     r9, rsi
0x140010698  call    WPP_SF_q
0x14001069d  cmp     ebp, 1
0x1400106a0  jz      short loc_1400106F7
0x1400106a2  lea     rbx, [rdi+1F8h]
0x1400106a9  mov     rcx, rbx; SpinLock
0x1400106ac  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400106b3  nop     dword ptr [rax+rax+00h]
0x1400106b8  mov     edx, [rdi+14h]
0x1400106bb  mov     rcx, rbx; SpinLock
0x1400106be  mov     [rdi+200h], al
0x1400106c4  test    dl, 2
0x1400106c7  jz      short loc_1400106E1
0x1400106c9  mov     dl, al; NewIrql
0x1400106cb  call    cs:__imp_KeReleaseSpinLock
0x1400106d2  nop     dword ptr [rax+rax+00h]
0x1400106d7  mov     eax, 0C0000001h
0x1400106dc  jmp     loc_1400107C0
0x1400106e1  lock inc dword ptr [rdi+10h]
0x1400106e5  mov     dl, [rdi+200h]; NewIrql
0x1400106eb  call    cs:__imp_KeReleaseSpinLock
0x1400106f2  nop     dword ptr [rax+rax+00h]
0x1400106f7  mov     rdx, [rdi+38h]
0x1400106fb  lea     r8, [rsi+30h]
0x1400106ff  mov     ebx, [rsi+10h]
0x140010702  lea     rcx, [rsp+48h+arg_8]
0x140010707  call    cs:__imp_NdisRequest
0x14001070e  nop     dword ptr [rax+rax+00h]
0x140010713  cmp     ebx, 1
0x140010716  jnz     short loc_140010762
0x140010718  cmp     [rsp+48h+arg_8], 103h
0x140010720  jnz     short loc_140010762
0x140010722  lea     rbx, [rsi+0F0h]
0x140010729  mov     [rsp+48h+Timeout], 0; Timeout
0x140010732  mov     rcx, rbx; Object
0x140010735  mov     r9b, 1; Alertable
0x140010738  xor     r8d, r8d; WaitMode
0x14001073b  xor     edx, edx; WaitReason
0x14001073d  call    cs:__imp_KeWaitForSingleObject
0x140010744  nop     dword ptr [rax+rax+00h]
0x140010749  mov     eax, [rsi+0E8h]
0x14001074f  mov     rcx, rbx; Event
0x140010752  mov     [rsp+48h+arg_8], eax
0x140010756  call    cs:__imp_KeClearEvent
0x14001075d  nop     dword ptr [rax+rax+00h]
0x140010762  mov     rcx, cs:WPP_GLOBAL_Control
0x140010769  cmp     rcx, r15
0x14001076c  jz      short loc_140010797
0x14001076e  test    dword ptr [rcx+2Ch], 80000h
0x140010775  jz      short loc_140010797
0x140010777  cmp     byte ptr [rcx+29h], 5
0x14001077b  jb      short loc_140010797
0x14001077d  mov     r9d, [rsp+48h+arg_8]
0x140010782  lea     r8, WPP_20bf124fffdd3be673ce951aa7b13aa4_Traceguids
0x140010789  mov     rcx, [rcx+18h]
0x14001078d  mov     edx, 0Dh
0x140010792  call    WPP_SF_d
0x140010797  cmp     ebp, 1
0x14001079a  jz      short loc_1400107BC
0x14001079c  or      eax, 0FFFFFFFFh
0x14001079f  lock xadd [rdi+10h], eax
0x1400107a4  cmp     eax, 1
0x1400107a7  jnz     short loc_1400107BC
0x1400107a9  lea     rcx, [rdi+228h]; Event
0x1400107b0  call    cs:__imp_NdisSetEvent
0x1400107b7  nop     dword ptr [rax+rax+00h]
0x1400107bc  mov     eax, [rsp+48h+arg_8]
0x1400107c0  mov     rbx, [rsp+48h+arg_0]
0x1400107c5  mov     rbp, [rsp+48h+arg_10]
0x1400107ca  add     rsp, 30h
0x1400107ce  pop     r15
0x1400107d0  pop     rdi
0x1400107d1  pop     rsi
0x1400107d2  retn
```
