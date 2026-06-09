# RfcommDispatchFdoClose

- ea: `0x14000280c`
- end: `0x140002ac1`
- name: `RfcommDispatchFdoClose`
- size: `693`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000256c`

## callees

- `0x140001958`
- `0x14000280c`
- `0x140004a68`
- `0x140004b4c`
- `0x14000aba8`
- `0x140019cd0`
- `0x14001ea34`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002845`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002980`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002845`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140002980`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000291d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400029b8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000291d`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400029b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002a95`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002a95`

## string_xrefs

- `0x140002a2a`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\io.c`
- `0x140002a7e`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\io.c`

## pseudocode

```c
__int64 __fastcall RfcommDispatchFdoClose(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  __int64 v3; // r15
  KIRQL v4; // r12
  PVOID *v5; // rdx
  PVOID **v6; // rbx
  PVOID **v7; // rax
  PVOID *v8; // rax
  _QWORD *v9; // rdi
  __int64 v10; // rax
  __int64 v11; // rbx
  __int64 v12; // rbx
  int v13; // edx
  __int64 v14; // rax
  int v15; // edx
  __int64 v16; // r14
  PVOID P; // [rsp+40h] [rbp-18h] BYREF
  PVOID *p_P; // [rsp+48h] [rbp-10h]

  v2 = *(_QWORD *)(a1 + 64);
  v3 = *(_QWORD *)(a2 + 184);
  p_P = &P;
  P = &P;
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v2 + 368));
  v5 = *(PVOID **)(v2 + 384);
  if ( v5 != (PVOID *)(v2 + 384) )
  {
    do
    {
      v6 = (PVOID **)*v5;
      if ( v5[2] == *(PVOID *)(v3 + 48) )
      {
        if ( v6[1] != v5
          || (v7 = (PVOID **)v5[1], *v7 != v5)
          || (*v7 = (PVOID *)v6, v6[1] = (PVOID *)v7, --*(_DWORD *)(v2 + 376), v8 = p_P, *p_P != &P) )
        {
LABEL_22:
          __fastfail(3u);
        }
        v5[1] = p_P;
        *v5 = &P;
        *v8 = v5;
        p_P = v5;
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          WPP_RECORDER_SF_qD(
            WPP_GLOBAL_Control->DeviceExtension,
            (_DWORD)v5,
            19,
            46,
            (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
            (char)v5,
            *(_DWORD *)(v2 + 376));
      }
      v5 = (PVOID *)v6;
    }
    while ( v6 != (PVOID **)(v2 + 384) );
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(v2 + 368), v4);
  while ( 1 )
  {
    v9 = P;
    if ( P == &P )
      return 0;
    if ( *((PVOID **)P + 1) != &P )
      goto LABEL_22;
    v10 = *(_QWORD *)P;
    if ( *(PVOID *)(*(_QWORD *)P + 8LL) != P )
      goto LABEL_22;
    P = *(PVOID *)P;
    *(_QWORD *)(v10 + 8) = &P;
    v9[1] = v9;
    *v9 = v9;
    v11 = *(_QWORD *)(*(_QWORD *)(v2 + 96) + 16LL);
    *(_BYTE *)(v11 + 56) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v11 + 48));
    v12 = RfcommApplyActionOnConnObjLocked(*(_QWORD *)(*(_QWORD *)(v2 + 96) + 16LL), v9 + 3, 2);
    KeReleaseSpinLock(
      (PKSPIN_LOCK)(*(_QWORD *)(*(_QWORD *)(v2 + 96) + 16LL) + 48LL),
      *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(v2 + 96) + 16LL) + 56LL));
    if ( v12 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_q(
          WPP_GLOBAL_Control->DeviceExtension,
          v13,
          19,
          47,
          (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
          v12);
      v14 = TdiReferenceChannelLocked(v12, 1313754947);
      v16 = v14;
      if ( v14 )
      {
        ChannelDisconnectRequest(v14, 2);
        RefObj_ReleaseEx(v16 + 24, 1313754947, 961, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\io.c");
      }
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_qD(
          WPP_GLOBAL_Control->DeviceExtension,
          v15,
          19,
          48,
          (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
          v12,
          *(_DWORD *)(v12 + 24) - 1);
      RefObj_ReleaseEx(v12 + 24, 541672532, 965, "onecore\\drivers\\wdm\\bluetooth\\drivers\\tdi\\rfcomm\\io.c");
    }
    ExFreePoolWithTag(v9, 0);
  }
}

```

## disassembly

```asm
0x14000280c  push    rbp
0x14000280e  push    rbx
0x14000280f  push    rsi
0x140002810  push    rdi
0x140002811  push    r12
0x140002813  push    r13
0x140002815  push    r14
0x140002817  push    r15
0x140002819  mov     rbp, rsp
0x14000281c  sub     rsp, 58h
0x140002820  mov     rsi, [rcx+40h]
0x140002824  lea     rax, [rbp+P]
0x140002828  mov     r15, [rdx+0B8h]
0x14000282f  mov     [rbp+var_10], rax
0x140002833  lea     rax, [rbp+P]
0x140002837  mov     [rbp+P], rax
0x14000283b  lea     r14, [rsi+170h]
0x140002842  mov     rcx, r14; SpinLock
0x140002845  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000284c  nop     dword ptr [rax+rax+00h]
0x140002851  lea     rdi, [rsi+180h]
0x140002858  mov     r12b, al
0x14000285b  mov     rdx, [rdi]
0x14000285e  lea     r13, WPP_RECORDER_INITIALIZED
0x140002865  lea     r8, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x14000286c  cmp     rdx, rdi
0x14000286f  jz      loc_140002917
0x140002875  mov     rcx, [r15+30h]
0x140002879  mov     rbx, [rdx]
0x14000287c  cmp     [rdx+10h], rcx
0x140002880  jnz     loc_14000290B
0x140002886  cmp     [rbx+8], rdx
0x14000288a  jnz     loc_140002AA6
0x140002890  mov     rax, [rdx+8]
0x140002894  cmp     [rax], rdx
0x140002897  jnz     loc_140002AA6
0x14000289d  mov     [rax], rbx
0x1400028a0  lea     rcx, [rbp+P]
0x1400028a4  mov     [rbx+8], rax
0x1400028a8  dec     dword ptr [rsi+178h]
0x1400028ae  mov     rax, [rbp+var_10]
0x1400028b2  cmp     [rax], rcx
0x1400028b5  jnz     loc_140002AA6
0x1400028bb  mov     [rdx+8], rax
0x1400028bf  lea     rcx, [rbp+P]
0x1400028c3  mov     [rdx], rcx
0x1400028c6  mov     [rax], rdx
0x1400028c9  mov     [rbp+var_10], rdx
0x1400028cd  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400028d4  jz      short loc_14000290B
0x1400028d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400028dd  mov     r9d, 2Eh ; '.'
0x1400028e3  mov     eax, [rsi+178h]
0x1400028e9  mov     [rsp+58h+var_28], eax
0x1400028ed  mov     [rsp+58h+var_30], rdx
0x1400028f2  mov     rcx, [rcx+40h]
0x1400028f6  mov     [rsp+58h+var_38], r8
0x1400028fb  lea     r8d, [r9-1Bh]
0x1400028ff  call    WPP_RECORDER_SF_qD
0x140002904  lea     r8, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x14000290b  mov     rdx, rbx
0x14000290e  cmp     rbx, rdi
0x140002911  jnz     loc_140002875
0x140002917  mov     dl, r12b; NewIrql
0x14000291a  mov     rcx, r14; SpinLock
0x14000291d  call    cs:__imp_KeReleaseSpinLock
0x140002924  nop     dword ptr [rax+rax+00h]
0x140002929  mov     r15d, 4E4E4F43h
0x14000292f  mov     r12d, 13h
0x140002935  mov     rdi, [rbp+P]
0x140002939  lea     rax, [rbp+P]
0x14000293d  cmp     rdi, rax
0x140002940  jz      loc_140002AAD
0x140002946  lea     rax, [rbp+P]
0x14000294a  cmp     [rdi+8], rax
0x14000294e  jnz     loc_140002AA6
0x140002954  mov     rax, [rdi]
0x140002957  cmp     [rax+8], rdi
0x14000295b  jnz     loc_140002AA6
0x140002961  mov     [rbp+P], rax
0x140002965  lea     rcx, [rbp+P]
0x140002969  mov     [rax+8], rcx
0x14000296d  mov     [rdi+8], rdi
0x140002971  mov     [rdi], rdi
0x140002974  mov     rax, [rsi+60h]
0x140002978  mov     rbx, [rax+10h]
0x14000297c  lea     rcx, [rbx+30h]; SpinLock
0x140002980  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140002987  nop     dword ptr [rax+rax+00h]
0x14000298c  mov     [rbx+38h], al
0x14000298f  lea     rdx, [rdi+18h]
0x140002993  mov     rcx, [rsi+60h]
0x140002997  mov     r8d, 2
0x14000299d  mov     rcx, [rcx+10h]
0x1400029a1  call    RfcommApplyActionOnConnObjLocked
0x1400029a6  mov     rcx, [rsi+60h]
0x1400029aa  mov     rbx, rax
0x1400029ad  mov     rdx, [rcx+10h]
0x1400029b1  lea     rcx, [rdx+30h]; SpinLock
0x1400029b5  mov     dl, [rdx+38h]; NewIrql
0x1400029b8  call    cs:__imp_KeReleaseSpinLock
0x1400029bf  nop     dword ptr [rax+rax+00h]
0x1400029c4  test    rbx, rbx
0x1400029c7  jz      loc_140002A90
0x1400029cd  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x1400029d4  jz      short loc_140002A00
0x1400029d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400029dd  lea     rax, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x1400029e4  mov     r9d, 2Fh ; '/'
0x1400029ea  mov     [rsp+58h+var_30], rbx
0x1400029ef  mov     r8d, r12d
0x1400029f2  mov     [rsp+58h+var_38], rax
0x1400029f7  mov     rcx, [rcx+40h]
0x1400029fb  call    WPP_RECORDER_SF_q
0x140002a00  mov     edx, r15d
0x140002a03  mov     rcx, rbx
0x140002a06  call    TdiReferenceChannelLocked
0x140002a0b  mov     r14, rax
0x140002a0e  test    rax, rax
0x140002a11  jz      short loc_140002A39
0x140002a13  mov     edx, 2
0x140002a18  mov     rcx, rax
0x140002a1b  call    ChannelDisconnectRequest
0x140002a20  lea     rcx, [r14+18h]
0x140002a24  mov     r8d, 3C1h
0x140002a2a  lea     r9, File; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140002a31  mov     rdx, r15
0x140002a34  call    RefObj_ReleaseEx
0x140002a39  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x140002a40  jz      short loc_140002A75
0x140002a42  mov     eax, [rbx+18h]
0x140002a45  mov     r9d, 30h ; '0'
0x140002a4b  mov     rcx, cs:WPP_GLOBAL_Control
0x140002a52  dec     eax
0x140002a54  mov     [rsp+58h+var_28], eax
0x140002a58  mov     r8d, r12d
0x140002a5b  lea     rax, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x140002a62  mov     [rsp+58h+var_30], rbx
0x140002a67  mov     [rsp+58h+var_38], rax
0x140002a6c  mov     rcx, [rcx+40h]
0x140002a70  call    WPP_RECORDER_SF_qD
0x140002a75  lea     rcx, [rbx+18h]
0x140002a79  mov     edx, 20494454h
0x140002a7e  lea     r9, File; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140002a85  mov     r8d, 3C5h
0x140002a8b  call    RefObj_ReleaseEx
0x140002a90  xor     edx, edx; Tag
0x140002a92  mov     rcx, rdi; P
0x140002a95  call    cs:__imp_ExFreePoolWithTag
0x140002a9c  nop     dword ptr [rax+rax+00h]
0x140002aa1  jmp     loc_140002935
0x140002aa6  mov     ecx, 3
0x140002aab  int     29h; Win8: RtlFailFast(ecx)
0x140002aad  xor     eax, eax
0x140002aaf  add     rsp, 58h
0x140002ab3  pop     r15
0x140002ab5  pop     r14
0x140002ab7  pop     r13
0x140002ab9  pop     r12
0x140002abb  pop     rdi
0x140002abc  pop     rsi
0x140002abd  pop     rbx
0x140002abe  pop     rbp
0x140002abf  retn
```
