# NatCleanupInterface

- ea: `0x14000bc50`
- end: `0x14000bd79`
- name: `NatCleanupInterface`
- size: `297`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `19`
- callee_count: `3`
- tags: ``

## callers

- `0x140007ca0`
- `0x14000bed0`
- `0x14000c9b8`
- `0x14000cf88`
- `0x14000d318`
- `0x14001e1f0`
- `0x14001e4e4`
- `0x14001e874`
- `0x140020970`
- `0x140021150`
- `0x140021cf0`
- `0x140023160`
- `0x140023940`
- `0x1400244e0`
- `0x14002597c`
- `0x14002633c`
- `0x14002665c`
- `0x1400273f8`
- `0x1400275d0`

## callees

- `0x14000218c`
- `0x14000bc50`
- `0x14000d50c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000bcff`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bd16`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bd27`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bcff`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bd16`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bd27`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000bce8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000bce8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000bc9e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000bc9e`

## pseudocode

```c
void __fastcall NatCleanupInterface(_DWORD *P)
{
  KIRQL v2; // bl
  __int64 v3; // r8
  void *v4; // rcx
  void *v5; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_((__int64)WPP_GLOBAL_Control->AttachedDevice, 0xAu, (__int64)WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids);
  }
  v2 = KeAcquireSpinLockRaiseToDpc(&InterfaceLock);
  v3 = 3LL * (P[8] & 0xF);
  LODWORD(InterfaceCache[v3]) = 0;
  InterfaceCache[v3 + 1] = 0;
  InterfaceCache[v3 + 2] = 0;
  NatResetInterface(P);
  KeReleaseSpinLock(&InterfaceLock, v2);
  v4 = (void *)*((_QWORD *)P + 15);
  if ( v4 )
    ExFreePoolWithTag(v4, 0);
  v5 = (void *)*((_QWORD *)P + 6);
  if ( v5 )
    ExFreePoolWithTag(v5, 0);
  ExFreePoolWithTag(P, 0);
  _InterlockedDecrement(&InterfaceCount);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_((__int64)WPP_GLOBAL_Control->AttachedDevice, 0xBu, (__int64)WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids);
  }
}

```

## disassembly

```asm
0x14000bc50  mov     [rsp+arg_0], rbx
0x14000bc55  mov     [rsp+arg_8], rsi
0x14000bc5a  push    rdi
0x14000bc5b  sub     rsp, 20h
0x14000bc5f  mov     rdi, rcx
0x14000bc62  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bc69  lea     rsi, WPP_GLOBAL_Control
0x14000bc70  cmp     rcx, rsi
0x14000bc73  jz      short loc_14000BC97
0x14000bc75  mov     eax, [rcx+2Ch]
0x14000bc78  test    al, 1
0x14000bc7a  jz      short loc_14000BC97
0x14000bc7c  cmp     byte ptr [rcx+29h], 6
0x14000bc80  jb      short loc_14000BC97
0x14000bc82  mov     rcx, [rcx+18h]
0x14000bc86  lea     r8, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids
0x14000bc8d  mov     edx, 0Ah
0x14000bc92  call    WPP_SF_
0x14000bc97  lea     rcx, InterfaceLock; SpinLock
0x14000bc9e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000bca5  nop     dword ptr [rax+rax+00h]
0x14000bcaa  mov     edx, [rdi+20h]
0x14000bcad  mov     rcx, rdi
0x14000bcb0  mov     r9, cs:off_14002F058
0x14000bcb7  and     edx, 0Fh
0x14000bcba  mov     bl, al
0x14000bcbc  lea     r8, [rdx+rdx*2]
0x14000bcc0  mov     dword ptr [r9+r8*8], 0
0x14000bcc8  mov     qword ptr [r9+r8*8+8], 0
0x14000bcd1  mov     qword ptr [r9+r8*8+10h], 0
0x14000bcda  call    NatResetInterface
0x14000bcdf  mov     dl, bl; NewIrql
0x14000bce1  lea     rcx, InterfaceLock; SpinLock
0x14000bce8  call    cs:__imp_KeReleaseSpinLock
0x14000bcef  nop     dword ptr [rax+rax+00h]
0x14000bcf4  mov     rcx, [rdi+78h]; P
0x14000bcf8  test    rcx, rcx
0x14000bcfb  jz      short loc_14000BD0B
0x14000bcfd  xor     edx, edx; Tag
0x14000bcff  call    cs:__imp_ExFreePoolWithTag
0x14000bd06  nop     dword ptr [rax+rax+00h]
0x14000bd0b  mov     rcx, [rdi+30h]; P
0x14000bd0f  test    rcx, rcx
0x14000bd12  jz      short loc_14000BD22
0x14000bd14  xor     edx, edx; Tag
0x14000bd16  call    cs:__imp_ExFreePoolWithTag
0x14000bd1d  nop     dword ptr [rax+rax+00h]
0x14000bd22  xor     edx, edx; Tag
0x14000bd24  mov     rcx, rdi; P
0x14000bd27  call    cs:__imp_ExFreePoolWithTag
0x14000bd2e  nop     dword ptr [rax+rax+00h]
0x14000bd33  lock dec cs:InterfaceCount
0x14000bd3a  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bd41  cmp     rcx, rsi
0x14000bd44  jz      short loc_14000BD68
0x14000bd46  mov     eax, [rcx+2Ch]
0x14000bd49  test    al, 1
0x14000bd4b  jz      short loc_14000BD68
0x14000bd4d  cmp     byte ptr [rcx+29h], 6
0x14000bd51  jb      short loc_14000BD68
0x14000bd53  mov     rcx, [rcx+18h]
0x14000bd57  lea     r8, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids
0x14000bd5e  mov     edx, 0Bh
0x14000bd63  call    WPP_SF_
0x14000bd68  mov     rbx, [rsp+28h+arg_0]
0x14000bd6d  mov     rsi, [rsp+28h+arg_8]
0x14000bd72  add     rsp, 20h
0x14000bd76  pop     rdi
0x14000bd77  retn
```
