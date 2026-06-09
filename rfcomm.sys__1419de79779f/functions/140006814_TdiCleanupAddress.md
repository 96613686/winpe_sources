# TdiCleanupAddress

- ea: `0x140006814`
- end: `0x1400069fd`
- name: `TdiCleanupAddress`
- size: `489`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140006750`

## callees

- `0x140003bf4`
- `0x140004a68`
- `0x140006814`
- `0x1400085a0`
- `0x1400133b0`
- `0x14001e74c`
- `0x14001ea34`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000688b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000696a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000688b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000696a`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000690e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400069a6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000690e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400069a6`

## string_xrefs

- `0x1400068f6`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`
- `0x140006976`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`

## pseudocode

```c
__int64 __fastcall TdiCleanupAddress(int a1, __int64 a2)
{
  _QWORD *v4; // rax
  __int64 v5; // rcx
  _QWORD *v6; // rsi
  int v7; // edx
  int v8; // edx
  __int128 v10; // [rsp+30h] [rbp-10h] BYREF
  char v11; // [rsp+78h] [rbp+38h] BYREF

  v10 = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      15,
      92,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
      a2,
      v10);
  *((_QWORD *)&v10 + 1) = &v10;
  *(_QWORD *)&v10 = &v10;
  *(_BYTE *)(a2 + 56) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 48));
  ListDrainLocked(&v10, a2 + 120);
  while ( 1 )
  {
    v4 = (_QWORD *)v10;
    if ( (__int128 *)v10 == &v10 )
      break;
    if ( *(__int128 **)(v10 + 8) != &v10 || (v5 = *(_QWORD *)v10, *(_QWORD *)(*(_QWORD *)v10 + 8LL) != (_QWORD)v10) )
      __fastfail(3u);
    *(_QWORD *)&v10 = *(_QWORD *)v10;
    *(_QWORD *)(v5 + 8) = &v10;
    v6 = v4 - 37;
    v4[1] = v4;
    *v4 = v4;
    RefObj_AddRefEx(v4 - 34, 1313164355, 2732, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
    KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 48), *(_BYTE *)(a2 + 56));
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_q(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        15,
        93,
        (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
        v6);
    TdiDisassociateAddress(a1, 0, (_DWORD)v6, 0, (__int64)&v11);
    *(_BYTE *)(a2 + 56) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 48));
    RefObj_ReleaseEx(v6 + 3, 1313164355, 2747, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 48), *(_BYTE *)(a2 + 56));
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v8,
      15,
      94,
      (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids);
  return 0;
}

```

## disassembly

```asm
0x140006814  mov     rax, rsp
0x140006817  mov     [rax+8], rbx
0x14000681b  mov     [rax+18h], rsi
0x14000681f  push    rbp
0x140006820  push    rdi
0x140006821  push    r13
0x140006823  push    r14
0x140006825  push    r15
0x140006827  mov     rbp, rsp
0x14000682a  sub     rsp, 40h
0x14000682e  xorps   xmm0, xmm0
0x140006831  mov     rbx, rdx
0x140006834  movups  [rbp+var_10], xmm0
0x140006838  mov     r15, rcx
0x14000683b  lea     rsi, WPP_RECORDER_INITIALIZED
0x140006842  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140006849  lea     r13, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x140006850  jz      short loc_140006874
0x140006852  mov     rcx, cs:WPP_GLOBAL_Control
0x140006859  mov     r9d, 5Ch ; '\'
0x14000685f  mov     [rax-40h], rdx
0x140006863  mov     [rax-48h], r13
0x140006867  mov     rcx, [rcx+40h]
0x14000686b  lea     r8d, [r9-4Dh]
0x14000686f  call    WPP_RECORDER_SF_q
0x140006874  lea     rax, [rbp+var_10]
0x140006878  mov     qword ptr [rbp+var_10+8], rax
0x14000687c  lea     rdi, [rbx+30h]
0x140006880  lea     rax, [rbp+var_10]
0x140006884  mov     rcx, rdi; SpinLock
0x140006887  mov     qword ptr [rbp+var_10], rax
0x14000688b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006892  nop     dword ptr [rax+rax+00h]
0x140006897  lea     rdx, [rbx+78h]
0x14000689b  mov     [rbx+38h], al
0x14000689e  lea     rcx, [rbp+var_10]
0x1400068a2  call    ListDrainLocked
0x1400068a7  mov     rax, qword ptr [rbp+var_10]
0x1400068ab  lea     rcx, [rbp+var_10]
0x1400068af  cmp     rax, rcx
0x1400068b2  jz      loc_1400069A0
0x1400068b8  lea     rcx, [rbp+var_10]
0x1400068bc  cmp     [rax+8], rcx
0x1400068c0  jnz     loc_140006999
0x1400068c6  mov     rcx, [rax]
0x1400068c9  cmp     [rcx+8], rax
0x1400068cd  jnz     loc_140006999
0x1400068d3  mov     qword ptr [rbp+var_10], rcx
0x1400068d7  lea     rdx, [rbp+var_10]
0x1400068db  mov     [rcx+8], rdx
0x1400068df  lea     rsi, [rax-128h]
0x1400068e6  mov     edx, 4E454C43h
0x1400068eb  mov     [rax+8], rax
0x1400068ef  lea     rcx, [rsi+18h]
0x1400068f3  mov     [rax], rax
0x1400068f6  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1400068fd  mov     r8d, 0AACh
0x140006903  call    RefObj_AddRefEx
0x140006908  mov     dl, [rbx+38h]; NewIrql
0x14000690b  mov     rcx, rdi; SpinLock
0x14000690e  call    cs:__imp_KeReleaseSpinLock
0x140006915  nop     dword ptr [rax+rax+00h]
0x14000691a  lea     rax, WPP_RECORDER_INITIALIZED
0x140006921  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140006928  jz      short loc_14000694E
0x14000692a  mov     rcx, cs:WPP_GLOBAL_Control
0x140006931  mov     r9d, 5Dh ; ']'
0x140006937  mov     [rsp+40h+var_18], rsi
0x14000693c  mov     [rsp+40h+var_20], r13
0x140006941  mov     rcx, [rcx+40h]
0x140006945  lea     r8d, [r9-4Eh]
0x140006949  call    WPP_RECORDER_SF_q
0x14000694e  lea     rax, [rbp+arg_8]
0x140006952  xor     r9d, r9d
0x140006955  mov     r8, rsi
0x140006958  mov     [rsp+40h+var_20], rax
0x14000695d  xor     edx, edx
0x14000695f  mov     rcx, r15
0x140006962  call    TdiDisassociateAddress
0x140006967  mov     rcx, rdi; SpinLock
0x14000696a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006971  nop     dword ptr [rax+rax+00h]
0x140006976  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x14000697d  mov     edx, 4E454C43h
0x140006982  lea     rcx, [rsi+18h]
0x140006986  mov     [rbx+38h], al
0x140006989  mov     r8d, 0ABBh
0x14000698f  call    RefObj_ReleaseEx
0x140006994  jmp     loc_1400068A7
0x140006999  mov     ecx, 3
0x14000699e  int     29h; Win8: RtlFailFast(ecx)
0x1400069a0  mov     dl, [rbx+38h]; NewIrql
0x1400069a3  mov     rcx, rdi; SpinLock
0x1400069a6  call    cs:__imp_KeReleaseSpinLock
0x1400069ad  nop     dword ptr [rax+rax+00h]
0x1400069b2  lea     rax, WPP_RECORDER_INITIALIZED
0x1400069b9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400069c0  jz      short loc_1400069E1
0x1400069c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400069c9  mov     r9d, 5Eh ; '^'
0x1400069cf  mov     [rsp+40h+var_20], r13
0x1400069d4  mov     rcx, [rcx+40h]
0x1400069d8  lea     r8d, [r9-4Fh]
0x1400069dc  call    WPP_RECORDER_SF_
0x1400069e1  lea     r11, [rsp+40h+var_s0]
0x1400069e6  xor     eax, eax
0x1400069e8  mov     rbx, [r11+30h]
0x1400069ec  mov     rsi, [r11+40h]
0x1400069f0  mov     rsp, r11
0x1400069f3  pop     r15
0x1400069f5  pop     r14
0x1400069f7  pop     r13
0x1400069f9  pop     rdi
0x1400069fa  pop     rbp
0x1400069fb  retn
```
