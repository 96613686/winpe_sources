# NatDeleteAnyAssociatedInterface

- ea: `0x14000c8b0`
- end: `0x14000c9af`
- name: `NatDeleteAnyAssociatedInterface`
- size: `255`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140002260`

## callees

- `0x14000218c`
- `0x14000c8b0`
- `0x14000c9b8`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000c947`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14000c947`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c968`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000c968`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000c92a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14000c92a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c8fb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000c8fb`

## pseudocode

```c
void __fastcall NatDeleteAnyAssociatedInterface(__int64 a1)
{
  KIRQL v2; // al
  PVOID *v3; // rcx
  KIRQL v4; // si
  unsigned int v5; // ebx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids);
  }
  v2 = KeAcquireSpinLockRaiseToDpc(&InterfaceLock);
  v3 = (PVOID *)InterfaceList;
  v4 = v2;
  while ( v3 != &InterfaceList )
  {
    if ( v3[5] == (PVOID)a1 )
    {
      v5 = *((_DWORD *)v3 + 8);
      KeReleaseSpinLockFromDpcLevel(&InterfaceLock);
      NatDeleteInterface(v5, a1);
      KeAcquireSpinLockAtDpcLevel(&InterfaceLock);
      v3 = &InterfaceList;
    }
    v3 = (PVOID *)*v3;
  }
  KeReleaseSpinLock(&InterfaceLock, v4);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 6u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids);
  }
}

```

## disassembly

```asm
0x14000c8b0  push    rbx
0x14000c8b2  push    rsi
0x14000c8b3  push    rdi
0x14000c8b4  push    r14
0x14000c8b6  push    r15
0x14000c8b8  sub     rsp, 20h
0x14000c8bc  mov     rdi, rcx
0x14000c8bf  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c8c6  lea     r15, WPP_GLOBAL_Control
0x14000c8cd  cmp     rcx, r15
0x14000c8d0  jz      short loc_14000C8F4
0x14000c8d2  mov     eax, [rcx+2Ch]
0x14000c8d5  test    al, 1
0x14000c8d7  jz      short loc_14000C8F4
0x14000c8d9  cmp     byte ptr [rcx+29h], 6
0x14000c8dd  jb      short loc_14000C8F4
0x14000c8df  mov     rcx, [rcx+18h]
0x14000c8e3  lea     r8, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids
0x14000c8ea  mov     edx, 2Fh ; '/'
0x14000c8ef  call    WPP_SF_
0x14000c8f4  lea     rcx, InterfaceLock; SpinLock
0x14000c8fb  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000c902  nop     dword ptr [rax+rax+00h]
0x14000c907  mov     rcx, cs:InterfaceList
0x14000c90e  lea     r14, InterfaceList
0x14000c915  mov     sil, al
0x14000c918  jmp     short loc_14000C959
0x14000c91a  cmp     [rcx+28h], rdi
0x14000c91e  jnz     short loc_14000C956
0x14000c920  mov     ebx, [rcx+20h]
0x14000c923  lea     rcx, InterfaceLock; SpinLock
0x14000c92a  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14000c931  nop     dword ptr [rax+rax+00h]
0x14000c936  mov     rdx, rdi
0x14000c939  mov     ecx, ebx
0x14000c93b  call    NatDeleteInterface
0x14000c940  lea     rcx, InterfaceLock; SpinLock
0x14000c947  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14000c94e  nop     dword ptr [rax+rax+00h]
0x14000c953  mov     rcx, r14
0x14000c956  mov     rcx, [rcx]
0x14000c959  cmp     rcx, r14
0x14000c95c  jnz     short loc_14000C91A
0x14000c95e  mov     dl, sil; NewIrql
0x14000c961  lea     rcx, InterfaceLock; SpinLock
0x14000c968  call    cs:__imp_KeReleaseSpinLock
0x14000c96f  nop     dword ptr [rax+rax+00h]
0x14000c974  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c97b  cmp     rcx, r15
0x14000c97e  jz      short loc_14000C9A2
0x14000c980  mov     eax, [rcx+2Ch]
0x14000c983  test    al, 1
0x14000c985  jz      short loc_14000C9A2
0x14000c987  cmp     byte ptr [rcx+29h], 6
0x14000c98b  jb      short loc_14000C9A2
0x14000c98d  mov     rcx, [rcx+18h]
0x14000c991  lea     r8, WPP_10e38ed1fb59383d510acb91f3960fad_Traceguids
0x14000c998  mov     edx, 30h ; '0'
0x14000c99d  call    WPP_SF_
0x14000c9a2  add     rsp, 20h
0x14000c9a6  pop     r15
0x14000c9a8  pop     r14
0x14000c9aa  pop     rdi
0x14000c9ab  pop     rsi
0x14000c9ac  pop     rbx
0x14000c9ad  retn
```
