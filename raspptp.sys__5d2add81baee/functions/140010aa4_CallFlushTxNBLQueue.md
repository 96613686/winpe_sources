# CallFlushTxNBLQueue

- ea: `0x140010aa4`
- end: `0x140010c0d`
- name: `CallFlushTxNBLQueue`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140002e78`

## callees

- `0x140001a70`
- `0x140003e08`
- `0x140010aa4`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140010b1c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010b60`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010bf5`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010b1c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010b60`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010bf5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010b2f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010bd1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010b2f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010bd1`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x140010ba9`
- `NDIS!NdisMCoSendNetBufferListsComplete` at `0x140010ba9`

## pseudocode

```c
void __fastcall CallFlushTxNBLQueue(__int64 a1)
{
  char v2; // bp
  KIRQL v3; // al
  KIRQL v4; // al
  __int64 v5; // rdi

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids);
  }
  while ( 1 )
  {
    v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 136));
    *(_BYTE *)(a1 + 144) = v4;
    v5 = *(_QWORD *)(a1 + 120);
    if ( !v5 )
      break;
    *(_QWORD *)(a1 + 120) = *(_QWORD *)v5;
    *(_QWORD *)v5 = 0;
    if ( !*(_QWORD *)(a1 + 120) )
      *(_QWORD *)(a1 + 128) = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 136), *(_BYTE *)(a1 + 144));
    v2 = 0;
    v3 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 96));
    *(_BYTE *)(a1 + 104) = v3;
    *(_DWORD *)(a1 + 188) -= *(_DWORD *)(v5 + 96);
    if ( v5 == *(_QWORD *)(a1 + 480) )
    {
      v2 = 1;
      *(_BYTE *)(a1 + 464) = 0;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 96), v3);
    if ( v2 )
    {
LABEL_13:
      DereferenceRefCount(a1 + 32);
    }
    else if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 112), 0xFFFFFFFF) == 1 )
    {
      *(_DWORD *)(v5 + 140) = -1073741823;
      _InterlockedAdd(&dword_14000B408, *(_DWORD *)(v5 + 96));
      _InterlockedAdd((volatile signed __int32 *)(a1 + 688), *(_DWORD *)(v5 + 96));
      NdisMCoSendNetBufferListsComplete(*(NDIS_HANDLE *)(a1 + 224), (PNET_BUFFER_LIST)v5, 0);
      DereferenceRefCount(*(_QWORD *)(a1 + 56) + 192LL);
      goto LABEL_13;
    }
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 136), v4);
}

```

## disassembly

```asm
0x140010aa4  push    rbx
0x140010aa6  push    rbp
0x140010aa7  push    rsi
0x140010aa8  push    rdi
0x140010aa9  push    r14
0x140010aab  sub     rsp, 20h
0x140010aaf  mov     rbx, rcx
0x140010ab2  mov     rcx, cs:WPP_GLOBAL_Control
0x140010ab9  lea     rax, WPP_GLOBAL_Control
0x140010ac0  cmp     rcx, rax
0x140010ac3  jz      short loc_140010AE7
0x140010ac5  mov     eax, [rcx+2Ch]
0x140010ac8  test    al, 10h
0x140010aca  jz      short loc_140010AE7
0x140010acc  cmp     byte ptr [rcx+29h], 2
0x140010ad0  jb      short loc_140010AE7
0x140010ad2  mov     rcx, [rcx+18h]
0x140010ad6  lea     r8, WPP_73ef8c2e44df3fd8f2254796efa7405f_Traceguids
0x140010add  mov     edx, 11h
0x140010ae2  call    WPP_SF_
0x140010ae7  lea     rsi, [rbx+88h]
0x140010aee  jmp     loc_140010BCE
0x140010af3  mov     rax, [rdi]
0x140010af6  mov     [rbx+78h], rax
0x140010afa  mov     qword ptr [rdi], 0
0x140010b01  cmp     qword ptr [rbx+78h], 0
0x140010b06  jnz     short loc_140010B13
0x140010b08  mov     qword ptr [rbx+80h], 0
0x140010b13  mov     dl, [rbx+90h]; NewIrql
0x140010b19  mov     rcx, rsi; SpinLock
0x140010b1c  call    cs:__imp_KeReleaseSpinLock
0x140010b23  nop     dword ptr [rax+rax+00h]
0x140010b28  lea     rcx, [rbx+60h]; SpinLock
0x140010b2c  xor     bpl, bpl
0x140010b2f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010b36  nop     dword ptr [rax+rax+00h]
0x140010b3b  mov     [rbx+68h], al
0x140010b3e  mov     ecx, [rdi+60h]
0x140010b41  sub     [rbx+0BCh], ecx
0x140010b47  cmp     rdi, [rbx+1E0h]
0x140010b4e  jnz     short loc_140010B5A
0x140010b50  mov     bpl, 1
0x140010b53  mov     byte ptr [rbx+1D0h], 0
0x140010b5a  mov     dl, al; NewIrql
0x140010b5c  lea     rcx, [rbx+60h]; SpinLock
0x140010b60  call    cs:__imp_KeReleaseSpinLock
0x140010b67  nop     dword ptr [rax+rax+00h]
0x140010b6c  test    bpl, bpl
0x140010b6f  jnz     short loc_140010BC5
0x140010b71  or      eax, 0FFFFFFFFh
0x140010b74  lock xadd [rdi+70h], eax
0x140010b79  cmp     eax, 1
0x140010b7c  jnz     short loc_140010BCE
0x140010b7e  mov     dword ptr [rdi+8Ch], 0C0000001h
0x140010b88  mov     eax, [rdi+60h]
0x140010b8b  lock add cs:dword_14000B408, eax
0x140010b92  mov     eax, [rdi+60h]
0x140010b95  lock add [rbx+2B0h], eax
0x140010b9c  mov     rcx, [rbx+0E0h]; NdisVcHandle
0x140010ba3  xor     r8d, r8d; SendCompleteFlags
0x140010ba6  mov     rdx, rdi; NetBufferLists
0x140010ba9  call    cs:__imp_NdisMCoSendNetBufferListsComplete
0x140010bb0  nop     dword ptr [rax+rax+00h]
0x140010bb5  mov     rcx, [rbx+38h]
0x140010bb9  add     rcx, 0C0h
0x140010bc0  call    DereferenceRefCount
0x140010bc5  lea     rcx, [rbx+20h]
0x140010bc9  call    DereferenceRefCount
0x140010bce  mov     rcx, rsi; SpinLock
0x140010bd1  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010bd8  nop     dword ptr [rax+rax+00h]
0x140010bdd  mov     [rbx+90h], al
0x140010be3  mov     rdi, [rbx+78h]
0x140010be7  test    rdi, rdi
0x140010bea  jnz     loc_140010AF3
0x140010bf0  mov     dl, al; NewIrql
0x140010bf2  mov     rcx, rsi; SpinLock
0x140010bf5  call    cs:__imp_KeReleaseSpinLock
0x140010bfc  nop     dword ptr [rax+rax+00h]
0x140010c01  add     rsp, 20h
0x140010c05  pop     r14
0x140010c07  pop     rdi
0x140010c08  pop     rsi
0x140010c09  pop     rbp
0x140010c0a  pop     rbx
0x140010c0b  retn
```
