# PppoeCmCreateVc

- ea: `0x140005c90`
- end: `0x140005f82`
- name: `PppoeCmCreateVc`
- size: `754`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x14000110c`
- `0x14000113c`
- `0x1400023c0`
- `0x140002958`
- `0x140002a60`
- `0x1400053c4`
- `0x140005c90`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140005d2b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005d63`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005e9f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005ebd`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005d2b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005d63`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005e9f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005ebd`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005d09`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005e52`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005d09`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140005e52`
- `NDIS!NdisAllocateMemoryWithTag` at `0x140005d7e`
- `NDIS!NdisAllocateMemoryWithTag` at `0x140005d7e`

## pseudocode

```c
__int64 __fastcall PppoeCmCreateVc(__int64 a1, __int64 a2, PVOID *a3)
{
  KIRQL v6; // al
  KSPIN_LOCK *v7; // rcx
  bool v8; // zf
  unsigned int v10; // ebx
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  _DWORD *v13; // rax
  _DWORD *v14; // rax
  KIRQL v15; // al
  PVOID v16; // r8
  __int64 v17; // rcx
  __int64 v18; // rax
  _DWORD *v19; // rax
  __int64 v20; // rdx
  PVOID VirtualAddress; // [rsp+70h] [rbp+48h] BYREF

  VirtualAddress = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xFu)
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_419ea9763cf3388c37536f51169668cc_Traceguids);
  }
  if ( a1 && *(_DWORD *)a1 == 1631940432 )
  {
    v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
    v7 = (KSPIN_LOCK *)(a1 + 8);
    v8 = *(_DWORD *)(a1 + 684) == *(_DWORD *)(a1 + 680);
    *(_BYTE *)(a1 + 16) = v6;
    if ( v8 )
    {
      KeReleaseSpinLock(v7, v6);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
      {
        if ( BYTE1(WPP_GLOBAL_Control->Timer) )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_419ea9763cf3388c37536f51169668cc_Traceguids);
      }
      return 3221225626LL;
    }
    KeReleaseSpinLock(v7, v6);
    if ( NdisAllocateMemoryWithTag(&VirtualAddress, 0x358u, 0x68456F50u) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xFu)
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_419ea9763cf3388c37536f51169668cc_Traceguids, 3221225626LL);
      }
      return 3221225626LL;
    }
    v10 = TpCallInitialize(VirtualAddress);
    if ( v10 )
    {
      v10 = -1073741823;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        v12 = 21;
LABEL_29:
        WPP_SF_d(v11->AttachedDevice, v12, WPP_419ea9763cf3388c37536f51169668cc_Traceguids, 3221225473LL);
      }
    }
    else
    {
      v13 = VirtualAddress;
      *((_QWORD *)VirtualAddress + 4) = FinalDerefCall;
      v13[6] = 0;
      v14 = VirtualAddress;
      *((_QWORD *)VirtualAddress + 6) = FinalDerefVcCall;
      v14[10] = 0;
      *((_QWORD *)VirtualAddress + 21) = a2;
      *((_QWORD *)VirtualAddress + 12) = a1;
      v15 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 8));
      v16 = VirtualAddress;
      v17 = *(_QWORD *)(a1 + 96);
      *(_BYTE *)(a1 + 16) = v15;
      v18 = InsertToHandleTable(v17, 0xFFFF, v16);
      if ( v18 )
      {
        ++*(_DWORD *)(a1 + 684);
        *((_QWORD *)VirtualAddress + 14) = v18;
        v19 = VirtualAddress;
        *a3 = VirtualAddress;
        v19[22] |= 1u;
        _InterlockedIncrement((volatile signed __int32 *)VirtualAddress + 6);
        KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), *(_BYTE *)(a1 + 16));
        LOBYTE(v20) = 1;
        ReferenceAdapter(a1, v20);
LABEL_32:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_419ea9763cf3388c37536f51169668cc_Traceguids, v10);
        }
        return v10;
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 8), *(_BYTE *)(a1 + 16));
      v10 = -1073741823;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        v12 = 22;
        goto LABEL_29;
      }
    }
    if ( VirtualAddress )
      TpCallCleanup(VirtualAddress);
    goto LABEL_32;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 0xFu)
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_419ea9763cf3388c37536f51169668cc_Traceguids);
  }
  return 3221225473LL;
}

```

## disassembly

```asm
0x140005c90  push    rbp
0x140005c92  push    rbx
0x140005c93  push    rsi
0x140005c94  push    rdi
0x140005c95  push    r12
0x140005c97  push    r13
0x140005c99  push    r14
0x140005c9b  push    r15
0x140005c9d  mov     rbp, rsp
0x140005ca0  sub     rsp, 28h
0x140005ca4  mov     r14, r8
0x140005ca7  mov     [rbp+VirtualAddress], 0
0x140005caf  mov     r15, rdx
0x140005cb2  mov     rdi, rcx
0x140005cb5  mov     rcx, cs:WPP_GLOBAL_Control
0x140005cbc  lea     r12, WPP_GLOBAL_Control
0x140005cc3  lea     r13, WPP_419ea9763cf3388c37536f51169668cc_Traceguids
0x140005cca  cmp     rcx, r12
0x140005ccd  jz      short loc_140005CED
0x140005ccf  bt      dword ptr [rcx+2Ch], 0Fh
0x140005cd4  jnb     short loc_140005CED
0x140005cd6  cmp     byte ptr [rcx+29h], 2
0x140005cda  jb      short loc_140005CED
0x140005cdc  mov     rcx, [rcx+18h]
0x140005ce0  mov     edx, 11h
0x140005ce5  mov     r8, r13
0x140005ce8  call    WPP_SF_
0x140005ced  test    rdi, rdi
0x140005cf0  jz      loc_140005F41
0x140005cf6  cmp     dword ptr [rdi], 61456F50h
0x140005cfc  jnz     loc_140005F41
0x140005d02  lea     rsi, [rdi+8]
0x140005d06  mov     rcx, rsi; SpinLock
0x140005d09  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005d10  nop     dword ptr [rax+rax+00h]
0x140005d15  mov     edx, [rdi+2A8h]
0x140005d1b  mov     rcx, rsi; SpinLock
0x140005d1e  cmp     [rdi+2ACh], edx
0x140005d24  mov     dl, al; NewIrql
0x140005d26  mov     [rdi+10h], al
0x140005d29  jnz     short loc_140005D63
0x140005d2b  call    cs:__imp_KeReleaseSpinLock
0x140005d32  nop     dword ptr [rax+rax+00h]
0x140005d37  mov     rcx, cs:WPP_GLOBAL_Control
0x140005d3e  cmp     rcx, r12
0x140005d41  jz      short loc_140005DBE
0x140005d43  mov     eax, [rcx+2Ch]
0x140005d46  test    al, 2
0x140005d48  jz      short loc_140005DBE
0x140005d4a  cmp     byte ptr [rcx+29h], 1
0x140005d4e  jb      short loc_140005DBE
0x140005d50  mov     rcx, [rcx+18h]
0x140005d54  mov     edx, 13h
0x140005d59  mov     r8, r13
0x140005d5c  call    WPP_SF_
0x140005d61  jmp     short loc_140005DBE
0x140005d63  call    cs:__imp_KeReleaseSpinLock
0x140005d6a  nop     dword ptr [rax+rax+00h]
0x140005d6f  mov     edx, 358h; Length
0x140005d74  lea     rcx, [rbp+VirtualAddress]; VirtualAddress
0x140005d78  mov     r8d, 68456F50h; Tag
0x140005d7e  call    cs:__imp_NdisAllocateMemoryWithTag
0x140005d85  nop     dword ptr [rax+rax+00h]
0x140005d8a  test    eax, eax
0x140005d8c  jz      short loc_140005DC8
0x140005d8e  mov     rcx, cs:WPP_GLOBAL_Control
0x140005d95  cmp     rcx, r12
0x140005d98  jz      short loc_140005DBE
0x140005d9a  bt      dword ptr [rcx+2Ch], 0Fh
0x140005d9f  jnb     short loc_140005DBE
0x140005da1  cmp     byte ptr [rcx+29h], 1
0x140005da5  jb      short loc_140005DBE
0x140005da7  mov     rcx, [rcx+18h]
0x140005dab  mov     edx, 14h
0x140005db0  mov     r9d, 0C000009Ah
0x140005db6  mov     r8, r13
0x140005db9  call    WPP_SF_d
0x140005dbe  mov     eax, 0C000009Ah
0x140005dc3  jmp     loc_140005F70
0x140005dc8  mov     rcx, [rbp+VirtualAddress]; void *
0x140005dcc  xor     r9d, r9d
0x140005dcf  call    TpCallInitialize
0x140005dd4  mov     ebx, eax
0x140005dd6  test    eax, eax
0x140005dd8  jz      short loc_140005E10
0x140005dda  mov     ebx, 0C0000001h
0x140005ddf  mov     rcx, cs:WPP_GLOBAL_Control
0x140005de6  cmp     rcx, r12
0x140005de9  jz      loc_140005F00
0x140005def  test    dword ptr [rcx+2Ch], 8000h
0x140005df6  jz      loc_140005F00
0x140005dfc  cmp     byte ptr [rcx+29h], 1
0x140005e00  jb      loc_140005F00
0x140005e06  mov     edx, 15h
0x140005e0b  jmp     loc_140005EEE
0x140005e10  mov     rax, [rbp+VirtualAddress]
0x140005e14  lea     rcx, FinalDerefCall
0x140005e1b  mov     [rax+20h], rcx
0x140005e1f  lea     rcx, FinalDerefVcCall
0x140005e26  mov     dword ptr [rax+18h], 0
0x140005e2d  mov     rax, [rbp+VirtualAddress]
0x140005e31  mov     [rax+30h], rcx
0x140005e35  mov     rcx, rsi; SpinLock
0x140005e38  mov     dword ptr [rax+28h], 0
0x140005e3f  mov     rax, [rbp+VirtualAddress]
0x140005e43  mov     [rax+0A8h], r15
0x140005e4a  mov     rax, [rbp+VirtualAddress]
0x140005e4e  mov     [rax+60h], rdi
0x140005e52  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005e59  nop     dword ptr [rax+rax+00h]
0x140005e5e  mov     r8, [rbp+VirtualAddress]
0x140005e62  mov     edx, 0FFFFh
0x140005e67  mov     rcx, [rdi+60h]
0x140005e6b  mov     [rdi+10h], al
0x140005e6e  call    InsertToHandleTable
0x140005e73  test    rax, rax
0x140005e76  jz      short loc_140005EB7
0x140005e78  inc     dword ptr [rdi+2ACh]
0x140005e7e  mov     rcx, [rbp+VirtualAddress]
0x140005e82  mov     [rcx+70h], rax
0x140005e86  mov     rax, [rbp+VirtualAddress]
0x140005e8a  mov     [r14], rax
0x140005e8d  or      dword ptr [rax+58h], 1
0x140005e91  mov     rax, [rbp+VirtualAddress]
0x140005e95  lock inc dword ptr [rax+18h]
0x140005e99  mov     dl, [rdi+10h]; NewIrql
0x140005e9c  mov     rcx, rsi; SpinLock
0x140005e9f  call    cs:__imp_KeReleaseSpinLock
0x140005ea6  nop     dword ptr [rax+rax+00h]
0x140005eab  mov     dl, 1
0x140005ead  mov     rcx, rdi
0x140005eb0  call    ReferenceAdapter
0x140005eb5  jmp     short loc_140005F0E
0x140005eb7  mov     dl, [rdi+10h]; NewIrql
0x140005eba  mov     rcx, rsi; SpinLock
0x140005ebd  call    cs:__imp_KeReleaseSpinLock
0x140005ec4  nop     dword ptr [rax+rax+00h]
0x140005ec9  mov     ebx, 0C0000001h
0x140005ece  mov     rcx, cs:WPP_GLOBAL_Control
0x140005ed5  cmp     rcx, r12
0x140005ed8  jz      short loc_140005F00
0x140005eda  test    dword ptr [rcx+2Ch], 8000h
0x140005ee1  jz      short loc_140005F00
0x140005ee3  cmp     byte ptr [rcx+29h], 1
0x140005ee7  jb      short loc_140005F00
0x140005ee9  mov     edx, 16h
0x140005eee  mov     rcx, [rcx+18h]
0x140005ef2  mov     r9d, 0C0000001h
0x140005ef8  mov     r8, r13
0x140005efb  call    WPP_SF_d
0x140005f00  mov     rcx, [rbp+VirtualAddress]; VirtualAddress
0x140005f04  test    rcx, rcx
0x140005f07  jz      short loc_140005F0E
0x140005f09  call    TpCallCleanup
0x140005f0e  mov     rcx, cs:WPP_GLOBAL_Control
0x140005f15  cmp     rcx, r12
0x140005f18  jz      short loc_140005F3D
0x140005f1a  test    dword ptr [rcx+2Ch], 8000h
0x140005f21  jz      short loc_140005F3D
0x140005f23  cmp     byte ptr [rcx+29h], 2
0x140005f27  jb      short loc_140005F3D
0x140005f29  mov     rcx, [rcx+18h]
0x140005f2d  mov     edx, 17h
0x140005f32  mov     r9d, ebx
0x140005f35  mov     r8, r13
0x140005f38  call    WPP_SF_d
0x140005f3d  mov     eax, ebx
0x140005f3f  jmp     short loc_140005F70
0x140005f41  mov     rcx, cs:WPP_GLOBAL_Control
0x140005f48  cmp     rcx, r12
0x140005f4b  jz      short loc_140005F6B
0x140005f4d  bt      dword ptr [rcx+2Ch], 0Fh
0x140005f52  jnb     short loc_140005F6B
0x140005f54  cmp     byte ptr [rcx+29h], 1
0x140005f58  jb      short loc_140005F6B
0x140005f5a  mov     rcx, [rcx+18h]
0x140005f5e  mov     edx, 12h
0x140005f63  mov     r8, r13
0x140005f66  call    WPP_SF_
0x140005f6b  mov     eax, 0C0000001h
0x140005f70  add     rsp, 28h
0x140005f74  pop     r15
0x140005f76  pop     r14
0x140005f78  pop     r13
0x140005f7a  pop     r12
0x140005f7c  pop     rdi
0x140005f7d  pop     rsi
0x140005f7e  pop     rbx
0x140005f7f  pop     rbp
0x140005f80  retn
```
