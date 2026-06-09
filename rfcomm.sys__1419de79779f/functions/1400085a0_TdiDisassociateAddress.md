# TdiDisassociateAddress

- ea: `0x1400085a0`
- end: `0x140008774`
- name: `TdiDisassociateAddress`
- size: `468`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140006814`
- `0x140006a04`

## callees

- `0x140003330`
- `0x140004e58`
- `0x1400085a0`
- `0x140008ac0`
- `0x14000ab70`
- `0x14001ea34`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400085de`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008610`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400085de`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140008610`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400086ac`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400086bf`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400086ac`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400086bf`

## string_xrefs

- `0x1400086cb`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`

## pseudocode

```c
__int64 __fastcall TdiDisassociateAddress(__int64 a1, __int64 a2, __int64 a3, __int64 a4, _QWORD *a5)
{
  __int64 v8; // rax
  __int64 v9; // rbx
  int v10; // edi
  int v11; // edx
  _QWORD *v12; // rax
  __int64 v13; // rdx
  _QWORD *v14; // r8
  signed __int32 v16[8]; // [rsp+0h] [rbp-78h] BYREF
  __int64 v17; // [rsp+20h] [rbp-58h]

  v17 = 0;
  *a5 = 0;
  TdiDisconnectRequest(a1, 0, a3, 0);
  *(_BYTE *)(a3 + 56) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a3 + 48));
  v8 = TdiReferenceAddrLocked(a3, 0x20505249u);
  v9 = v8;
  if ( v8 )
  {
    *(_BYTE *)(v8 + 56) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v8 + 48));
    if ( *(_QWORD *)(a3 + 104) == v9 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_qq(
          WPP_GLOBAL_Control->DeviceExtension,
          v11,
          15,
          89,
          (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
          a3,
          v9);
      v12 = (_QWORD *)(a3 + 296);
      *(_QWORD *)(a3 + 104) = 0;
      v13 = *(_QWORD *)(a3 + 296);
      if ( *(_QWORD *)(v13 + 8) != a3 + 296 || (v14 = *(_QWORD **)(a3 + 304), (_QWORD *)*v14 != v12) )
        __fastfail(3u);
      *v14 = v13;
      v10 = 0;
      *(_QWORD *)(v13 + 8) = v14;
      *(_QWORD *)(a3 + 304) = a3 + 296;
      *v12 = v12;
    }
    else
    {
      v10 = -1073741504;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(v9 + 48), *(_BYTE *)(v9 + 56));
  }
  else
  {
    v10 = -1073741504;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a3 + 48), *(_BYTE *)(a3 + 56));
  if ( v10 >= 0 )
  {
    _InterlockedOr(v16, 0);
    if ( *(_BYTE *)(v9 + 136)
      && *(_DWORD *)(v9 + 216)
      && _InterlockedExchangeAdd((volatile signed __int32 *)(v9 + 224), 0xFFFFFFFF) == 1 )
    {
      v10 = RfcommSetPageScanForAddress(a1, v9, a2, 0);
    }
    RefObj_ReleaseEx(a3 + 24, 1380205633, 2596, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
    RefObj_ReleaseEx(v9 + 24, 1313754947, 2597, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
  }
  if ( v9 )
    RefObj_ReleaseEx(v9 + 24, 542134857, 2603, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\tdi.c");
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1400085a0  push    rbx
0x1400085a2  push    rbp
0x1400085a3  push    rsi
0x1400085a4  push    rdi
0x1400085a5  push    r12
0x1400085a7  push    r14
0x1400085a9  push    r15
0x1400085ab  sub     rsp, 40h
0x1400085af  mov     rax, [rsp+78h+arg_20]
0x1400085b7  mov     r12, rdx
0x1400085ba  xor     r9d, r9d
0x1400085bd  mov     [rsp+78h+var_58], 0
0x1400085c6  xor     edx, edx
0x1400085c8  mov     rsi, r8
0x1400085cb  mov     r15, rcx
0x1400085ce  mov     qword ptr [rax], 0
0x1400085d5  call    TdiDisconnectRequest
0x1400085da  lea     rcx, [rsi+30h]; SpinLock
0x1400085de  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400085e5  nop     dword ptr [rax+rax+00h]
0x1400085ea  mov     edx, 20505249h
0x1400085ef  mov     rcx, rsi
0x1400085f2  mov     [rsi+38h], al
0x1400085f5  call    TdiReferenceAddrLocked
0x1400085fa  mov     rbx, rax
0x1400085fd  test    rax, rax
0x140008600  jnz     short loc_14000860C
0x140008602  mov     edi, 0C0000140h
0x140008607  jmp     loc_1400086B8
0x14000860c  lea     rcx, [rax+30h]; SpinLock
0x140008610  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140008617  nop     dword ptr [rax+rax+00h]
0x14000861c  mov     [rbx+38h], al
0x14000861f  cmp     [rsi+68h], rbx
0x140008623  jz      short loc_14000862C
0x140008625  mov     edi, 0C0000140h
0x14000862a  jmp     short loc_1400086A5
0x14000862c  lea     rax, WPP_RECORDER_INITIALIZED
0x140008633  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000863a  jz      short loc_14000866C
0x14000863c  mov     rcx, cs:WPP_GLOBAL_Control
0x140008643  lea     rax, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x14000864a  mov     r9d, 59h ; 'Y'
0x140008650  mov     [rsp+78h+var_48], rbx
0x140008655  mov     [rsp+78h+var_50], rsi
0x14000865a  mov     [rsp+78h+var_58], rax
0x14000865f  mov     rcx, [rcx+40h]
0x140008663  lea     r8d, [r9-4Ah]
0x140008667  call    WPP_RECORDER_SF_qq
0x14000866c  lea     rax, [rsi+128h]
0x140008673  mov     qword ptr [rsi+68h], 0
0x14000867b  mov     rdx, [rax]
0x14000867e  cmp     [rdx+8], rax
0x140008682  jnz     loc_14000876D
0x140008688  mov     r8, [rax+8]
0x14000868c  cmp     [r8], rax
0x14000868f  jnz     loc_14000876D
0x140008695  mov     [r8], rdx
0x140008698  xor     edi, edi
0x14000869a  mov     [rdx+8], r8
0x14000869e  mov     [rax+8], rax
0x1400086a2  mov     [rax], rax
0x1400086a5  mov     dl, [rbx+38h]; NewIrql
0x1400086a8  lea     rcx, [rbx+30h]; SpinLock
0x1400086ac  call    cs:__imp_KeReleaseSpinLock
0x1400086b3  nop     dword ptr [rax+rax+00h]
0x1400086b8  mov     dl, [rsi+38h]; NewIrql
0x1400086bb  lea     rcx, [rsi+30h]; SpinLock
0x1400086bf  call    cs:__imp_KeReleaseSpinLock
0x1400086c6  nop     dword ptr [rax+rax+00h]
0x1400086cb  lea     rbp, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x1400086d2  test    edi, edi
0x1400086d4  js      short loc_14000873F
0x1400086d6  lock or [rsp+78h+var_78], 0
0x1400086db  cmp     byte ptr [rbx+88h], 0
0x1400086e2  jz      short loc_140008711
0x1400086e4  mov     eax, [rbx+0D8h]
0x1400086ea  test    eax, eax
0x1400086ec  jz      short loc_140008711
0x1400086ee  or      eax, 0FFFFFFFFh
0x1400086f1  lock xadd [rbx+0E0h], eax
0x1400086f9  cmp     eax, 1
0x1400086fc  jnz     short loc_140008711
0x1400086fe  xor     r9d, r9d
0x140008701  mov     r8, r12
0x140008704  mov     rdx, rbx
0x140008707  mov     rcx, r15
0x14000870a  call    RfcommSetPageScanForAddress
0x14000870f  mov     edi, eax
0x140008711  lea     rcx, [rsi+18h]
0x140008715  mov     r9, rbp
0x140008718  mov     edx, 52444441h
0x14000871d  mov     r8d, 0A24h
0x140008723  call    RefObj_ReleaseEx
0x140008728  lea     rcx, [rbx+18h]
0x14000872c  mov     r9, rbp
0x14000872f  mov     edx, 4E4E4F43h
0x140008734  mov     r8d, 0A25h
0x14000873a  call    RefObj_ReleaseEx
0x14000873f  test    rbx, rbx
0x140008742  jz      short loc_14000875B
0x140008744  lea     rcx, [rbx+18h]
0x140008748  mov     r9, rbp
0x14000874b  mov     edx, 20505249h
0x140008750  mov     r8d, 0A2Bh
0x140008756  call    RefObj_ReleaseEx
0x14000875b  mov     eax, edi
0x14000875d  add     rsp, 40h
0x140008761  pop     r15
0x140008763  pop     r14
0x140008765  pop     r12
0x140008767  pop     rdi
0x140008768  pop     rsi
0x140008769  pop     rbp
0x14000876a  pop     rbx
0x14000876b  retn
0x14000876d  mov     ecx, 3
0x140008772  int     29h; Win8: RtlFailFast(ecx)
```
