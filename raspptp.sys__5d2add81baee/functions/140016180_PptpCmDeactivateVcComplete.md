# PptpCmDeactivateVcComplete

- ea: `0x140016180`
- end: `0x1400162c3`
- name: `PptpCmDeactivateVcComplete`
- size: `323`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140003bc0`

## callees

- `0x140001a70`
- `0x140002e78`
- `0x140003e38`
- `0x140016180`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140016213`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016296`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016213`
- `ntoskrnl!KeReleaseSpinLock` at `0x140016296`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400161d1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001626f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400161d1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001626f`
- `NDIS!NdisCmCloseCallComplete` at `0x140016260`
- `NDIS!NdisCmCloseCallComplete` at `0x140016260`

## pseudocode

```c
__int64 __fastcall PptpCmDeactivateVcComplete(unsigned int a1, __int64 a2)
{
  KIRQL v3; // dl
  unsigned int v4; // eax
  int v5; // ecx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 101, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids, a1);
  }
  v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 96));
  *(_BYTE *)(a2 + 104) = v3;
  v4 = *(_DWORD *)(a2 + 424);
  if ( (v4 & 0x8000) != 0 )
  {
    v5 = *(_DWORD *)(a2 + 428);
    if ( (v5 & 0x200) == 0 )
    {
      *(_DWORD *)(a2 + 428) = v5 | 0x200;
      KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 96), v3);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          102,
          WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids,
          *(unsigned int *)(a2 + 200));
      }
      NdisCmCloseCallComplete(0, *(NDIS_HANDLE *)(a2 + 224), 0);
      v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 96));
      *(_BYTE *)(a2 + 104) = v3;
      v4 = *(_DWORD *)(a2 + 424) & 0xFFFF7FFF;
    }
  }
  *(_DWORD *)(a2 + 424) = v4 & 0xFFFFFFFB;
  KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 96), v3);
  CallCleanup(a2);
  return DereferenceRefCount(a2);
}

```

## disassembly

```asm
0x140016180  mov     [rsp+arg_0], rbx
0x140016185  mov     [rsp+arg_8], rsi
0x14001618a  push    rdi
0x14001618b  sub     rsp, 20h
0x14001618f  mov     rbx, rdx
0x140016192  mov     r9d, ecx
0x140016195  mov     rcx, cs:WPP_GLOBAL_Control
0x14001619c  lea     rsi, WPP_GLOBAL_Control
0x1400161a3  cmp     rcx, rsi
0x1400161a6  jz      short loc_1400161CA
0x1400161a8  mov     eax, [rcx+2Ch]
0x1400161ab  test    al, 4
0x1400161ad  jz      short loc_1400161CA
0x1400161af  cmp     byte ptr [rcx+29h], 2
0x1400161b3  jb      short loc_1400161CA
0x1400161b5  mov     rcx, [rcx+18h]
0x1400161b9  lea     r8, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids
0x1400161c0  mov     edx, 65h ; 'e'
0x1400161c5  call    WPP_SF_d
0x1400161ca  lea     rdi, [rbx+60h]
0x1400161ce  mov     rcx, rdi; SpinLock
0x1400161d1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400161d8  nop     dword ptr [rax+rax+00h]
0x1400161dd  mov     dl, al; NewIrql
0x1400161df  mov     [rbx+68h], al
0x1400161e2  mov     eax, [rbx+1A8h]
0x1400161e8  bt      eax, 0Fh
0x1400161ec  jnb     loc_14001628A
0x1400161f2  mov     ecx, [rbx+1ACh]
0x1400161f8  mov     r8d, 200h
0x1400161fe  test    r8d, ecx
0x140016201  jnz     loc_14001628A
0x140016207  or      ecx, r8d
0x14001620a  mov     [rbx+1ACh], ecx
0x140016210  mov     rcx, rdi; SpinLock
0x140016213  call    cs:__imp_KeReleaseSpinLock
0x14001621a  nop     dword ptr [rax+rax+00h]
0x14001621f  mov     rcx, cs:WPP_GLOBAL_Control
0x140016226  cmp     rcx, rsi
0x140016229  jz      short loc_140016254
0x14001622b  mov     eax, [rcx+2Ch]
0x14001622e  test    al, 10h
0x140016230  jz      short loc_140016254
0x140016232  cmp     byte ptr [rcx+29h], 2
0x140016236  jb      short loc_140016254
0x140016238  mov     r9d, [rbx+0C8h]
0x14001623f  lea     r8, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids
0x140016246  mov     rcx, [rcx+18h]
0x14001624a  mov     edx, 66h ; 'f'
0x14001624f  call    WPP_SF_d
0x140016254  mov     rdx, [rbx+0E0h]; NdisVcHandle
0x14001625b  xor     r8d, r8d; NdisPartyHandle
0x14001625e  xor     ecx, ecx; Status
0x140016260  call    cs:__imp_NdisCmCloseCallComplete
0x140016267  nop     dword ptr [rax+rax+00h]
0x14001626c  mov     rcx, rdi; SpinLock
0x14001626f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140016276  nop     dword ptr [rax+rax+00h]
0x14001627b  mov     dl, al; NewIrql
0x14001627d  mov     [rbx+68h], al
0x140016280  mov     eax, [rbx+1A8h]
0x140016286  btr     eax, 0Fh
0x14001628a  and     eax, 0FFFFFFFBh
0x14001628d  mov     rcx, rdi; SpinLock
0x140016290  mov     [rbx+1A8h], eax
0x140016296  call    cs:__imp_KeReleaseSpinLock
0x14001629d  nop     dword ptr [rax+rax+00h]
0x1400162a2  mov     rcx, rbx
0x1400162a5  call    CallCleanup
0x1400162aa  mov     rcx, rbx
0x1400162ad  call    DereferenceRefCount
0x1400162b2  mov     rbx, [rsp+28h+arg_0]
0x1400162b7  mov     rsi, [rsp+28h+arg_8]
0x1400162bc  add     rsp, 20h
0x1400162c0  pop     rdi
0x1400162c1  retn
```
