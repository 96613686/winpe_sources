# TdiDataInd

- ea: `0x140008334`
- end: `0x140008453`
- name: `TdiDataInd`
- size: `287`
- prototype: `char __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140012c60`

## callees

- `0x140004e58`
- `0x140008334`
- `0x1400097f4`
- `0x14000c838`
- `0x14001e74c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000834d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000834d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000842b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000842b`

## string_xrefs

- `0x1400083ea`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`

## pseudocode

```c
char __fastcall TdiDataInd(__int64 a1, _QWORD *a2)
{
  KIRQL v4; // al
  int v5; // edx
  int v6; // r8d
  bool v7; // zf
  char v8; // di
  _QWORD *v9; // rcx

  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 48));
  v7 = *(_BYTE *)(a1 + 96) == 0;
  *(_BYTE *)(a1 + 56) = v4;
  if ( v7 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qdq(WPP_GLOBAL_Control->DeviceExtension, v5, v6, 76);
    v8 = 1;
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qq(
        WPP_GLOBAL_Control->DeviceExtension,
        v5,
        15,
        77,
        (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
        (char)a2,
        a1);
    RefObj_AddRefEx(a1 + 24, 1447249234, 2016, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
    v9 = *(_QWORD **)(a1 + 800);
    if ( *v9 != a1 + 792 )
      __fastfail(3u);
    *a2 = a1 + 792;
    a2[1] = v9;
    *v9 = a2;
    *(_QWORD *)(a1 + 800) = a2;
    v8 = 0;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 48), *(_BYTE *)(a1 + 56));
  TdiIndicateReceive(a1);
  return v8;
}

```

## disassembly

```asm
0x140008334  mov     [rsp+arg_0], rbx
0x140008339  mov     [rsp+arg_8], rsi
0x14000833e  push    rdi
0x14000833f  sub     rsp, 40h
0x140008343  mov     rbx, rcx
0x140008346  mov     rdi, rdx
0x140008349  add     rcx, 30h ; '0'; SpinLock
0x14000834d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140008354  nop     dword ptr [rax+rax+00h]
0x140008359  cmp     byte ptr [rbx+60h], 0
0x14000835d  mov     [rbx+38h], al
0x140008360  jnz     short loc_1400083A1
0x140008362  lea     rax, WPP_RECORDER_INITIALIZED
0x140008369  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140008370  jz      short loc_140008399
0x140008372  mov     rcx, cs:WPP_GLOBAL_Control
0x140008379  mov     r9d, 4Ch ; 'L'
0x14000837f  mov     eax, [rbx+50h]
0x140008382  mov     [rsp+48h+var_10], rdi
0x140008387  mov     dword ptr [rsp+48h+var_18], eax
0x14000838b  mov     rcx, [rcx+40h]
0x14000838f  mov     [rsp+48h+var_20], rbx
0x140008394  call    WPP_RECORDER_SF_qdq
0x140008399  mov     dil, 1
0x14000839c  jmp     loc_140008424
0x1400083a1  lea     rax, WPP_RECORDER_INITIALIZED
0x1400083a8  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400083af  jz      short loc_1400083E1
0x1400083b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400083b8  lea     rax, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x1400083bf  mov     r9d, 4Dh ; 'M'
0x1400083c5  mov     [rsp+48h+var_18], rbx
0x1400083ca  mov     [rsp+48h+var_20], rdi
0x1400083cf  mov     [rsp+48h+var_28], rax
0x1400083d4  mov     rcx, [rcx+40h]
0x1400083d8  lea     r8d, [r9-3Eh]
0x1400083dc  call    WPP_RECORDER_SF_qq
0x1400083e1  lea     rcx, [rbx+18h]
0x1400083e5  mov     edx, 56434552h
0x1400083ea  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1400083f1  mov     r8d, 7E0h
0x1400083f7  call    RefObj_AddRefEx
0x1400083fc  lea     rax, [rbx+318h]
0x140008403  mov     rcx, [rax+8]
0x140008407  cmp     [rcx], rax
0x14000840a  jz      short loc_140008413
0x14000840c  mov     ecx, 3
0x140008411  int     29h; Win8: RtlFailFast(ecx)
0x140008413  mov     [rdi], rax
0x140008416  mov     [rdi+8], rcx
0x14000841a  mov     [rcx], rdi
0x14000841d  mov     [rax+8], rdi
0x140008421  xor     dil, dil
0x140008424  mov     dl, [rbx+38h]; NewIrql
0x140008427  lea     rcx, [rbx+30h]; SpinLock
0x14000842b  call    cs:__imp_KeReleaseSpinLock
0x140008432  nop     dword ptr [rax+rax+00h]
0x140008437  mov     rcx, rbx
0x14000843a  call    TdiIndicateReceive
0x14000843f  mov     rbx, [rsp+48h+arg_0]
0x140008444  mov     al, dil
0x140008447  mov     rsi, [rsp+48h+arg_8]
0x14000844c  add     rsp, 40h
0x140008450  pop     rdi
0x140008451  retn
```
