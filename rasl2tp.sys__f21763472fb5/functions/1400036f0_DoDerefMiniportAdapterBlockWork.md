# DoDerefMiniportAdapterBlockWork

- ea: `0x1400036f0`
- end: `0x1400037b9`
- name: `DoDerefMiniportAdapterBlockWork`
- size: `201`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140003050`
- `0x1400036f0`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140003759`
- `ntoskrnl!KeReleaseSpinLock` at `0x140003759`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000373d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000373d`
- `NDIS!NdisMPauseComplete` at `0x14000376c`
- `NDIS!NdisMPauseComplete` at `0x14000376c`

## pseudocode

```c
void __fastcall DoDerefMiniportAdapterBlockWork(__int64 a1)
{
  KIRQL v2; // al

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_8ac02f22297f31ed9b47b3d0f49ff24b_Traceguids);
  }
  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 24));
  *(_DWORD *)(a1 + 16) = 0;
  *(_BYTE *)(a1 + 32) = v2;
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 24), v2);
  NdisMPauseComplete(*(NDIS_HANDLE *)(a1 + 160));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_8ac02f22297f31ed9b47b3d0f49ff24b_Traceguids);
  }
}

```

## disassembly

```asm
0x1400036f0  mov     [rsp+arg_0], rbx
0x1400036f5  mov     [rsp+arg_8], rbp
0x1400036fa  push    rdi
0x1400036fb  sub     rsp, 20h
0x1400036ff  mov     rdi, rcx
0x140003702  mov     rcx, cs:WPP_GLOBAL_Control
0x140003709  lea     rbp, WPP_GLOBAL_Control
0x140003710  cmp     rcx, rbp
0x140003713  jz      short loc_140003739
0x140003715  test    dword ptr [rcx+2Ch], 200h
0x14000371c  jz      short loc_140003739
0x14000371e  cmp     byte ptr [rcx+29h], 4
0x140003722  jb      short loc_140003739
0x140003724  mov     rcx, [rcx+18h]
0x140003728  lea     r8, WPP_8ac02f22297f31ed9b47b3d0f49ff24b_Traceguids
0x14000372f  mov     edx, 0Ah
0x140003734  call    WPP_SF_
0x140003739  lea     rcx, [rdi+18h]; SpinLock
0x14000373d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140003744  nop     dword ptr [rax+rax+00h]
0x140003749  lea     rcx, [rdi+18h]; SpinLock
0x14000374d  mov     dword ptr [rdi+10h], 0
0x140003754  mov     dl, al; NewIrql
0x140003756  mov     [rdi+20h], al
0x140003759  call    cs:__imp_KeReleaseSpinLock
0x140003760  nop     dword ptr [rax+rax+00h]
0x140003765  mov     rcx, [rdi+0A0h]; MiniportAdapterHandle
0x14000376c  call    cs:__imp_NdisMPauseComplete
0x140003773  nop     dword ptr [rax+rax+00h]
0x140003778  mov     rcx, cs:WPP_GLOBAL_Control
0x14000377f  cmp     rcx, rbp
0x140003782  jz      short loc_1400037A8
0x140003784  test    dword ptr [rcx+2Ch], 200h
0x14000378b  jz      short loc_1400037A8
0x14000378d  cmp     byte ptr [rcx+29h], 4
0x140003791  jb      short loc_1400037A8
0x140003793  mov     rcx, [rcx+18h]
0x140003797  lea     r8, WPP_8ac02f22297f31ed9b47b3d0f49ff24b_Traceguids
0x14000379e  mov     edx, 0Bh
0x1400037a3  call    WPP_SF_
0x1400037a8  mov     rbx, [rsp+28h+arg_0]
0x1400037ad  mov     rbp, [rsp+28h+arg_8]
0x1400037b2  add     rsp, 20h
0x1400037b6  pop     rdi
0x1400037b7  retn
```
