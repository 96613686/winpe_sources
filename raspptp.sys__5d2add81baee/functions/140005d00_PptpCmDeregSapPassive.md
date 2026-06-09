# PptpCmDeregSapPassive

- ea: `0x140005d00`
- end: `0x140005dd0`
- name: `PptpCmDeregSapPassive`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140002320`
- `0x140002a30`
- `0x140003e08`
- `0x140005d00`
- `0x14001c7b4`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140005d55`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005d55`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005d13`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005d13`
- `NDIS!NdisCmDeregisterSapComplete` at `0x140005db8`
- `NDIS!NdisCmDeregisterSapComplete` at `0x140005db8`

## pseudocode

```c
void __fastcall PptpCmDeregSapPassive(__int64 a1)
{
  __int64 v1; // rbx
  KIRQL v2; // al
  __int64 v3; // rdi
  void *v4; // r14
  char v5; // si

  v1 = *(_QWORD *)(a1 + 24);
  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 8));
  v3 = *(_QWORD *)(v1 + 56);
  v4 = *(void **)(v1 + 136);
  *(_BYTE *)(v1 + 16) = v2;
  *(_QWORD *)(v1 + 136) = 0;
  if ( v3 )
  {
    v5 = 1;
    *(_QWORD *)(v1 + 56) = 0;
  }
  else
  {
    v5 = 0;
    v3 = 0;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 8), v2);
  if ( v5 )
    WskCloseSocketContextAndFreeSocket(v3);
  DereferenceAdapter(v1);
  DereferenceAf(v1);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids);
  }
  NdisCmDeregisterSapComplete(0, v4);
}

```

## disassembly

```asm
0x140005d00  push    rbx
0x140005d02  push    rbp
0x140005d03  push    rsi
0x140005d04  push    rdi
0x140005d05  push    r14
0x140005d07  sub     rsp, 20h
0x140005d0b  mov     rbx, [rcx+18h]
0x140005d0f  lea     rcx, [rbx+8]; SpinLock
0x140005d13  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005d1a  nop     dword ptr [rax+rax+00h]
0x140005d1f  mov     rdi, [rbx+38h]
0x140005d23  mov     r14, [rbx+88h]
0x140005d2a  mov     [rbx+10h], al
0x140005d2d  mov     qword ptr [rbx+88h], 0
0x140005d38  test    rdi, rdi
0x140005d3b  jz      short loc_140005D4A
0x140005d3d  mov     sil, 1
0x140005d40  mov     qword ptr [rbx+38h], 0
0x140005d48  jmp     short loc_140005D4F
0x140005d4a  xor     sil, sil
0x140005d4d  xor     edi, edi
0x140005d4f  mov     dl, al; NewIrql
0x140005d51  lea     rcx, [rbx+8]; SpinLock
0x140005d55  call    cs:__imp_KeReleaseSpinLock
0x140005d5c  nop     dword ptr [rax+rax+00h]
0x140005d61  test    sil, sil
0x140005d64  jz      short loc_140005D6E
0x140005d66  mov     rcx, rdi
0x140005d69  call    WskCloseSocketContextAndFreeSocket
0x140005d6e  mov     rcx, rbx
0x140005d71  call    DereferenceAdapter
0x140005d76  mov     rcx, rbx
0x140005d79  call    DereferenceAf
0x140005d7e  mov     rcx, cs:WPP_GLOBAL_Control
0x140005d85  lea     rax, WPP_GLOBAL_Control
0x140005d8c  cmp     rcx, rax
0x140005d8f  jz      short loc_140005DB3
0x140005d91  mov     eax, [rcx+2Ch]
0x140005d94  test    al, 4
0x140005d96  jz      short loc_140005DB3
0x140005d98  cmp     byte ptr [rcx+29h], 2
0x140005d9c  jb      short loc_140005DB3
0x140005d9e  mov     rcx, [rcx+18h]
0x140005da2  lea     r8, WPP_bb2356f62bb53f7d7b74420549d2b52f_Traceguids
0x140005da9  mov     edx, 23h ; '#'
0x140005dae  call    WPP_SF_
0x140005db3  mov     rdx, r14; NdisSapHandle
0x140005db6  xor     ecx, ecx; Status
0x140005db8  call    cs:__imp_NdisCmDeregisterSapComplete
0x140005dbf  nop     dword ptr [rax+rax+00h]
0x140005dc4  add     rsp, 20h
0x140005dc8  pop     r14
0x140005dca  pop     rdi
0x140005dcb  pop     rsi
0x140005dcc  pop     rbp
0x140005dcd  pop     rbx
0x140005dce  retn
```
