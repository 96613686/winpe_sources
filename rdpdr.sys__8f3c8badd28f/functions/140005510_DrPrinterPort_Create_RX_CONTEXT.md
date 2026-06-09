# DrPrinterPort::Create(_RX_CONTEXT *)

- ea: `0x140005510`
- end: `0x140005656`
- name: `?Create@DrPrinterPort@@UEAAJPEAU_RX_CONTEXT@@@Z`
- size: `326`
- prototype: `__int64 __fastcall(DrPrinterPort *__hidden this, struct _RX_CONTEXT *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x14000324c`
- `0x140005510`
- `0x1400056e0`
- `0x14002b120`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000552a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400055ac`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000552a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400055ac`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005541`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000558c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400055f6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140005541`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000558c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400055f6`

## pseudocode

```c
__int64 __fastcall DrPrinterPort::Create(DrPrinterPort *this, struct _RX_CONTEXT *a2)
{
  KIRQL v4; // al
  int v6; // edx
  int v7; // edi
  int v8; // r8d
  KIRQL v9; // si
  __int64 v10; // rax
  int v11; // r9d

  v4 = KeAcquireSpinLockRaiseToDpc(&DrSpinLock);
  if ( *((_DWORD *)this + 22) )
  {
    KeReleaseSpinLock(&DrSpinLock, v4);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_6b2c43a11f0a329c1a4acc292f8a4ed9_Traceguids);
    return 3221225539LL;
  }
  else
  {
    *((_DWORD *)this + 22) = 1;
    KeReleaseSpinLock(&DrSpinLock, v4);
    v7 = DrDevice::Create(this, a2);
    if ( v7 >= 0 )
    {
      v10 = *((_QWORD *)this + 4);
      v11 = 0;
      if ( v10 )
        v11 = *(_DWORD *)(v10 + 1128);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        WPP_SF_dS(WPP_GLOBAL_Control->AttachedDevice, v6, v8, v11, *((_QWORD *)this + 10));
      *((_DWORD *)this + 23) = 0;
    }
    else
    {
      v9 = KeAcquireSpinLockRaiseToDpc(&DrSpinLock);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_6b2c43a11f0a329c1a4acc292f8a4ed9_Traceguids);
      *((_DWORD *)this + 22) = 0;
      KeReleaseSpinLock(&DrSpinLock, v9);
    }
    return (unsigned int)v7;
  }
}

```

## disassembly

```asm
0x140005510  push    rbx
0x140005512  push    rsi
0x140005513  push    rdi
0x140005514  push    r14
0x140005516  sub     rsp, 38h
0x14000551a  mov     rbx, rcx
0x14000551d  lea     r14, ?DrSpinLock@@3_KA; unsigned __int64 DrSpinLock
0x140005524  mov     rcx, r14; SpinLock
0x140005527  mov     rdi, rdx
0x14000552a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140005531  nop     dword ptr [rax+rax+00h]
0x140005536  cmp     dword ptr [rbx+58h], 0
0x14000553a  mov     rcx, r14; SpinLock
0x14000553d  mov     dl, al; NewIrql
0x14000553f  jz      short loc_140005585
0x140005541  call    cs:__imp_KeReleaseSpinLock
0x140005548  nop     dword ptr [rax+rax+00h]
0x14000554d  mov     rcx, cs:WPP_GLOBAL_Control
0x140005554  lea     rax, WPP_GLOBAL_Control
0x14000555b  cmp     rcx, rax
0x14000555e  jz      short loc_14000557B
0x140005560  cmp     byte ptr [rcx+29h], 5
0x140005564  jb      short loc_14000557B
0x140005566  mov     rcx, [rcx+18h]
0x14000556a  lea     r8, WPP_6b2c43a11f0a329c1a4acc292f8a4ed9_Traceguids
0x140005571  mov     edx, 1Eh
0x140005576  call    WPP_SF_
0x14000557b  mov     eax, 0C0000043h
0x140005580  jmp     loc_14000564B
0x140005585  mov     dword ptr [rbx+58h], 1
0x14000558c  call    cs:__imp_KeReleaseSpinLock
0x140005593  nop     dword ptr [rax+rax+00h]
0x140005598  mov     rdx, rdi; struct _RX_CONTEXT *
0x14000559b  mov     rcx, rbx; this
0x14000559e  call    ?Create@DrDevice@@UEAAJPEAU_RX_CONTEXT@@@Z; DrDevice::Create(_RX_CONTEXT *)
0x1400055a3  mov     edi, eax
0x1400055a5  test    eax, eax
0x1400055a7  jns     short loc_140005604
0x1400055a9  mov     rcx, r14; SpinLock
0x1400055ac  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400055b3  nop     dword ptr [rax+rax+00h]
0x1400055b8  mov     sil, al
0x1400055bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400055c2  lea     rax, WPP_GLOBAL_Control
0x1400055c9  cmp     rcx, rax
0x1400055cc  jz      short loc_1400055E9
0x1400055ce  cmp     byte ptr [rcx+29h], 4
0x1400055d2  jb      short loc_1400055E9
0x1400055d4  mov     rcx, [rcx+18h]
0x1400055d8  lea     r8, WPP_6b2c43a11f0a329c1a4acc292f8a4ed9_Traceguids
0x1400055df  mov     edx, 1Fh
0x1400055e4  call    WPP_SF_
0x1400055e9  mov     dl, sil; NewIrql
0x1400055ec  mov     dword ptr [rbx+58h], 0
0x1400055f3  mov     rcx, r14; SpinLock
0x1400055f6  call    cs:__imp_KeReleaseSpinLock
0x1400055fd  nop     dword ptr [rax+rax+00h]
0x140005602  jmp     short loc_140005649
0x140005604  mov     rax, [rbx+20h]
0x140005608  xor     r9d, r9d
0x14000560b  test    rax, rax
0x14000560e  jz      short loc_140005617
0x140005610  mov     r9d, [rax+468h]
0x140005617  mov     rcx, cs:WPP_GLOBAL_Control
0x14000561e  lea     rax, WPP_GLOBAL_Control
0x140005625  cmp     rcx, rax
0x140005628  jz      short loc_140005642
0x14000562a  cmp     byte ptr [rcx+29h], 2
0x14000562e  jb      short loc_140005642
0x140005630  mov     rax, [rbx+50h]
0x140005634  mov     rcx, [rcx+18h]
0x140005638  mov     [rsp+58h+var_38], rax
0x14000563d  call    WPP_SF_dS
0x140005642  mov     dword ptr [rbx+5Ch], 0
0x140005649  mov     eax, edi
0x14000564b  add     rsp, 38h
0x14000564f  pop     r14
0x140005651  pop     rdi
0x140005652  pop     rsi
0x140005653  pop     rbx
0x140005654  retn
```
