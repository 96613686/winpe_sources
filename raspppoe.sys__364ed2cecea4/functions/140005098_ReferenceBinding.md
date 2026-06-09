# ReferenceBinding

- ea: `0x140005098`
- end: `0x14000515c`
- name: `ReferenceBinding`
- size: `196`
- prototype: ``
- caller_count: `11`
- callee_count: `3`
- tags: ``

## callers

- `0x1400035b8`
- `0x140004100`
- `0x1400112e8`
- `0x140011560`
- `0x14001169c`
- `0x140014d2c`
- `0x140014e68`
- `0x1400150cc`
- `0x1400152f4`
- `0x140016534`
- `0x140017a00`

## callees

- `0x14000110c`
- `0x14000113c`
- `0x140005098`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140005113`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005113`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400050ed`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400050ed`

## pseudocode

```c
void __fastcall ReferenceBinding(__int64 a1, char a2)
{
  int v4; // ebp

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x13u,
      (__int64)WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids);
  }
  if ( a2 )
    *(_BYTE *)(a1 + 392) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 384));
  v4 = ++*(_DWORD *)(a1 + 20);
  if ( a2 )
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 384), *(_BYTE *)(a1 + 392));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x14u,
      (__int64)WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids,
      v4);
  }
}

```

## disassembly

```asm
0x140005098  push    rbx
0x14000509a  push    rbp
0x14000509b  push    rsi
0x14000509c  push    rdi
0x14000509d  push    r15
0x14000509f  sub     rsp, 20h
0x1400050a3  mov     sil, dl
0x1400050a6  mov     rbx, rcx
0x1400050a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400050b0  lea     r15, WPP_GLOBAL_Control
0x1400050b7  cmp     rcx, r15
0x1400050ba  jz      short loc_1400050DE
0x1400050bc  mov     eax, [rcx+2Ch]
0x1400050bf  test    al, 4
0x1400050c1  jz      short loc_1400050DE
0x1400050c3  cmp     byte ptr [rcx+29h], 4
0x1400050c7  jb      short loc_1400050DE
0x1400050c9  mov     rcx, [rcx+18h]
0x1400050cd  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x1400050d4  mov     edx, 13h
0x1400050d9  call    WPP_SF_
0x1400050de  lea     rdi, [rbx+180h]
0x1400050e5  test    sil, sil
0x1400050e8  jz      short loc_1400050FF
0x1400050ea  mov     rcx, rdi; SpinLock
0x1400050ed  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400050f4  nop     dword ptr [rax+rax+00h]
0x1400050f9  mov     [rbx+188h], al
0x1400050ff  inc     dword ptr [rbx+14h]
0x140005102  mov     ebp, [rbx+14h]
0x140005105  test    sil, sil
0x140005108  jz      short loc_14000511F
0x14000510a  mov     dl, [rbx+188h]; NewIrql
0x140005110  mov     rcx, rdi; SpinLock
0x140005113  call    cs:__imp_KeReleaseSpinLock
0x14000511a  nop     dword ptr [rax+rax+00h]
0x14000511f  mov     rcx, cs:WPP_GLOBAL_Control
0x140005126  cmp     rcx, r15
0x140005129  jz      short loc_140005150
0x14000512b  mov     eax, [rcx+2Ch]
0x14000512e  test    al, 4
0x140005130  jz      short loc_140005150
0x140005132  cmp     byte ptr [rcx+29h], 4
0x140005136  jb      short loc_140005150
0x140005138  mov     rcx, [rcx+18h]
0x14000513c  lea     r8, WPP_ba8e1113a5d83cdd6e70590fe70766f4_Traceguids
0x140005143  mov     edx, 14h
0x140005148  mov     r9d, ebp
0x14000514b  call    WPP_SF_d
0x140005150  add     rsp, 20h
0x140005154  pop     r15
0x140005156  pop     rdi
0x140005157  pop     rsi
0x140005158  pop     rbp
0x140005159  pop     rbx
0x14000515a  retn
```
