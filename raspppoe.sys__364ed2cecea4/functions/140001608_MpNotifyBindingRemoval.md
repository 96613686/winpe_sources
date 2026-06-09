# MpNotifyBindingRemoval

- ea: `0x140001608`
- end: `0x14000191c`
- name: `MpNotifyBindingRemoval`
- size: `788`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: ``

## callers

- `0x140004460`
- `0x140004620`
- `0x140004e10`

## callees

- `0x140001608`
- `0x1400024dc`
- `0x140002794`
- `0x1400028cc`
- `0x140002e0c`
- `0x140006b80`
- `0x140015e28`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140001721`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001734`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001756`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001847`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000185e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400018c2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001721`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001734`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001756`
- `ntoskrnl!KeReleaseSpinLock` at `0x140001847`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000185e`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400018c2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400016cc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400016f9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400017cc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000181e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001892`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400016cc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400016f9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400017cc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000181e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140001892`

## pseudocode

```c
void __fastcall MpNotifyBindingRemoval(__int64 a1)
{
  PDEVICE_OBJECT v2; // rcx
  __int64 v3; // rdx
  __int64 v4; // rbx
  KSPIN_LOCK *v5; // rsi
  KIRQL v6; // al
  __int64 v7; // rdx
  KIRQL v8; // al
  unsigned int v9; // r14d
  unsigned int v10; // r12d
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rbp
  char v14; // r13
  volatile signed __int32 *v15; // rsi
  __int64 v16; // [rsp+78h] [rbp+10h]

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 108, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids, a1);
  }
  if ( gl_fLockAllocated )
  {
    v4 = 0;
    NewIrql = KeAcquireSpinLockRaiseToDpc(&gl_lockAdapter);
    if ( gl_pAdapter && *(_DWORD *)(gl_pAdapter + 64) )
    {
      v5 = (KSPIN_LOCK *)(gl_pAdapter + 8);
      v4 = gl_pAdapter;
      v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(gl_pAdapter + 8));
      v7 = *(unsigned int *)(v4 + 84);
      LOBYTE(v7) = v7 & 3;
      *(_BYTE *)(v4 + 16) = v6;
      if ( (_BYTE)v7 == 1 )
      {
        ReferenceTapiProv(v4, v7);
        KeReleaseSpinLock(v5, *(_BYTE *)(v4 + 16));
      }
      else
      {
        KeReleaseSpinLock(v5, v6);
        v4 = 0;
      }
    }
    KeReleaseSpinLock(&gl_lockAdapter, NewIrql);
    if ( v4 )
    {
      v8 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 8));
      v9 = 0;
      v10 = *(_DWORD *)(v4 + 676) * *(_DWORD *)(v4 + 680);
      *(_BYTE *)(v4 + 16) = v8;
      v11 = *(_QWORD *)(v4 + 96);
      v16 = v11;
      if ( v10 )
      {
        do
        {
          v12 = RetrieveFromHandleTableByIndex(v11, (unsigned __int16)v9);
          v13 = v12;
          if ( v12 )
          {
            v14 = 0;
            v15 = (volatile signed __int32 *)(v12 + 24);
            *(_BYTE *)(v12 + 64) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v12 + 56));
            if ( *(_QWORD *)(v13 + 728) == a1 )
            {
              _InterlockedIncrement(v15);
              v14 = 1;
            }
            KeReleaseSpinLock((PKSPIN_LOCK)(v13 + 56), *(_BYTE *)(v13 + 64));
            if ( v14 )
            {
              KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 8), *(_BYTE *)(v4 + 16));
              TpCmCallCleanup(v13, 0x100u);
              if ( _InterlockedExchangeAdd(v15, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(__int64))(v13 + 32))(v13 + 24);
              *(_BYTE *)(v4 + 16) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v4 + 8));
            }
          }
          v11 = v16;
          ++v9;
        }
        while ( v9 < v10 );
      }
      KeReleaseSpinLock((PKSPIN_LOCK)(v4 + 8), *(_BYTE *)(v4 + 16));
      DereferenceTapiProv(v4);
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        v3 = 113;
        goto LABEL_41;
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 111, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids, a1);
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      {
        v3 = 112;
        goto LABEL_41;
      }
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 109, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids, a1);
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
    {
      v3 = 110;
LABEL_41:
      WPP_SF_q(v2->AttachedDevice, v3, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids, a1);
    }
  }
}

```

## disassembly

```asm
0x140001608  push    rbx
0x14000160a  push    rbp
0x14000160b  push    rsi
0x14000160c  push    rdi
0x14000160d  push    r12
0x14000160f  push    r13
0x140001611  push    r14
0x140001613  push    r15
0x140001615  sub     rsp, 28h
0x140001619  mov     rdi, rcx
0x14000161c  mov     rcx, cs:WPP_GLOBAL_Control
0x140001623  lea     rsi, WPP_GLOBAL_Control
0x14000162a  lea     rbp, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids
0x140001631  mov     r13b, 3
0x140001634  cmp     rcx, rsi
0x140001637  jz      short loc_14000165A
0x140001639  mov     eax, [rcx+2Ch]
0x14000163c  test    al, 1
0x14000163e  jz      short loc_14000165A
0x140001640  cmp     [rcx+29h], r13b
0x140001644  jb      short loc_14000165A
0x140001646  mov     rcx, [rcx+18h]
0x14000164a  mov     edx, 6Ch ; 'l'
0x14000164f  mov     r9, rdi
0x140001652  mov     r8, rbp
0x140001655  call    WPP_SF_q
0x14000165a  cmp     cs:gl_fLockAllocated, 0
0x140001661  jnz     short loc_1400016C3
0x140001663  mov     rcx, cs:WPP_GLOBAL_Control
0x14000166a  cmp     rcx, rsi
0x14000166d  jz      loc_14000190A
0x140001673  mov     eax, [rcx+2Ch]
0x140001676  test    al, 1
0x140001678  jz      short loc_140001694
0x14000167a  cmp     byte ptr [rcx+29h], 1
0x14000167e  jb      short loc_140001694
0x140001680  mov     rcx, [rcx+18h]
0x140001684  mov     edx, 6Dh ; 'm'
0x140001689  mov     r9, rdi
0x14000168c  mov     r8, rbp
0x14000168f  call    WPP_SF_q
0x140001694  mov     rcx, cs:WPP_GLOBAL_Control
0x14000169b  cmp     rcx, rsi
0x14000169e  jz      loc_14000190A
0x1400016a4  mov     eax, [rcx+2Ch]
0x1400016a7  test    al, 1
0x1400016a9  jz      loc_14000190A
0x1400016af  cmp     [rcx+29h], r13b
0x1400016b3  jb      loc_14000190A
0x1400016b9  mov     edx, 6Eh ; 'n'
0x1400016be  jmp     loc_1400018FB
0x1400016c3  lea     rcx, gl_lockAdapter; SpinLock
0x1400016ca  xor     ebx, ebx
0x1400016cc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400016d3  nop     dword ptr [rax+rax+00h]
0x1400016d8  mov     cs:NewIrql, al
0x1400016de  mov     rax, cs:gl_pAdapter
0x1400016e5  test    rax, rax
0x1400016e8  jz      short loc_140001749
0x1400016ea  cmp     [rax+40h], ebx
0x1400016ed  jz      short loc_140001749
0x1400016ef  lea     rsi, [rax+8]
0x1400016f3  mov     rbx, rax
0x1400016f6  mov     rcx, rsi; SpinLock
0x1400016f9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001700  nop     dword ptr [rax+rax+00h]
0x140001705  mov     edx, [rbx+54h]
0x140001708  and     dl, r13b
0x14000170b  mov     [rbx+10h], al
0x14000170e  cmp     dl, 1
0x140001711  jnz     short loc_14000172F
0x140001713  mov     rcx, rbx
0x140001716  call    ReferenceTapiProv
0x14000171b  mov     dl, [rbx+10h]; NewIrql
0x14000171e  mov     rcx, rsi; SpinLock
0x140001721  call    cs:__imp_KeReleaseSpinLock
0x140001728  nop     dword ptr [rax+rax+00h]
0x14000172d  jmp     short loc_140001742
0x14000172f  mov     dl, al; NewIrql
0x140001731  mov     rcx, rsi; SpinLock
0x140001734  call    cs:__imp_KeReleaseSpinLock
0x14000173b  nop     dword ptr [rax+rax+00h]
0x140001740  xor     ebx, ebx
0x140001742  lea     rsi, WPP_GLOBAL_Control
0x140001749  mov     dl, cs:NewIrql; NewIrql
0x14000174f  lea     rcx, gl_lockAdapter; SpinLock
0x140001756  call    cs:__imp_KeReleaseSpinLock
0x14000175d  nop     dword ptr [rax+rax+00h]
0x140001762  test    rbx, rbx
0x140001765  jnz     short loc_1400017C5
0x140001767  mov     rcx, cs:WPP_GLOBAL_Control
0x14000176e  cmp     rcx, rsi
0x140001771  jz      loc_14000190A
0x140001777  mov     eax, [rcx+2Ch]
0x14000177a  test    al, 1
0x14000177c  jz      short loc_140001796
0x14000177e  cmp     byte ptr [rcx+29h], 1
0x140001782  jb      short loc_140001796
0x140001784  mov     rcx, [rcx+18h]
0x140001788  lea     edx, [rbx+6Fh]
0x14000178b  mov     r9, rdi
0x14000178e  mov     r8, rbp
0x140001791  call    WPP_SF_q
0x140001796  mov     rcx, cs:WPP_GLOBAL_Control
0x14000179d  cmp     rcx, rsi
0x1400017a0  jz      loc_14000190A
0x1400017a6  mov     eax, [rcx+2Ch]
0x1400017a9  test    al, 1
0x1400017ab  jz      loc_14000190A
0x1400017b1  cmp     [rcx+29h], r13b
0x1400017b5  jb      loc_14000190A
0x1400017bb  mov     edx, 70h ; 'p'
0x1400017c0  jmp     loc_1400018FB
0x1400017c5  lea     r15, [rbx+8]
0x1400017c9  mov     rcx, r15; SpinLock
0x1400017cc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400017d3  nop     dword ptr [rax+rax+00h]
0x1400017d8  mov     r12d, [rbx+2A8h]
0x1400017df  xor     r14d, r14d
0x1400017e2  imul    r12d, [rbx+2A4h]
0x1400017ea  mov     [rbx+10h], al
0x1400017ed  mov     rax, [rbx+60h]
0x1400017f1  mov     [rsp+68h+arg_8], rax
0x1400017f6  test    r12d, r12d
0x1400017f9  jz      loc_1400018BC
0x1400017ff  movzx   edx, r14w
0x140001803  mov     rcx, rax
0x140001806  call    RetrieveFromHandleTableByIndex
0x14000180b  mov     rbp, rax
0x14000180e  test    rax, rax
0x140001811  jz      loc_1400018A1
0x140001817  lea     rcx, [rax+38h]; SpinLock
0x14000181b  xor     r13b, r13b
0x14000181e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001825  nop     dword ptr [rax+rax+00h]
0x14000182a  lea     rsi, [rbp+18h]
0x14000182e  mov     [rbp+40h], al
0x140001831  cmp     [rbp+2D8h], rdi
0x140001838  jnz     short loc_140001840
0x14000183a  lock inc dword ptr [rsi]
0x14000183d  mov     r13b, 1
0x140001840  mov     dl, [rbp+40h]; NewIrql
0x140001843  lea     rcx, [rbp+38h]; SpinLock
0x140001847  call    cs:__imp_KeReleaseSpinLock
0x14000184e  nop     dword ptr [rax+rax+00h]
0x140001853  test    r13b, r13b
0x140001856  jz      short loc_1400018A1
0x140001858  mov     dl, [rbx+10h]; NewIrql
0x14000185b  mov     rcx, r15; SpinLock
0x14000185e  call    cs:__imp_KeReleaseSpinLock
0x140001865  nop     dword ptr [rax+rax+00h]
0x14000186a  mov     edx, 100h
0x14000186f  mov     rcx, rbp
0x140001872  call    TpCmCallCleanup
0x140001877  or      eax, 0FFFFFFFFh
0x14000187a  lock xadd [rsi], eax
0x14000187e  cmp     eax, 1
0x140001881  jnz     short loc_14000188F
0x140001883  mov     rax, [rsi+8]
0x140001887  mov     rcx, rsi
0x14000188a  call    _guard_dispatch_icall
0x14000188f  mov     rcx, r15; SpinLock
0x140001892  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140001899  nop     dword ptr [rax+rax+00h]
0x14000189e  mov     [rbx+10h], al
0x1400018a1  mov     rax, [rsp+68h+arg_8]
0x1400018a6  inc     r14d
0x1400018a9  cmp     r14d, r12d
0x1400018ac  jb      loc_1400017FF
0x1400018b2  lea     rbp, WPP_1e2386c18f813770d1ae045e18655ca9_Traceguids
0x1400018b9  mov     r13b, 3
0x1400018bc  mov     dl, [rbx+10h]; NewIrql
0x1400018bf  mov     rcx, r15; SpinLock
0x1400018c2  call    cs:__imp_KeReleaseSpinLock
0x1400018c9  nop     dword ptr [rax+rax+00h]
0x1400018ce  mov     rcx, rbx
0x1400018d1  call    DereferenceTapiProv
0x1400018d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400018dd  lea     rax, WPP_GLOBAL_Control
0x1400018e4  cmp     rcx, rax
0x1400018e7  jz      short loc_14000190A
0x1400018e9  mov     eax, [rcx+2Ch]
0x1400018ec  test    al, 1
0x1400018ee  jz      short loc_14000190A
0x1400018f0  cmp     [rcx+29h], r13b
0x1400018f4  jb      short loc_14000190A
0x1400018f6  mov     edx, 71h ; 'q'
0x1400018fb  mov     rcx, [rcx+18h]
0x1400018ff  mov     r9, rdi
0x140001902  mov     r8, rbp
0x140001905  call    WPP_SF_q
0x14000190a  add     rsp, 28h
0x14000190e  pop     r15
0x140001910  pop     r14
0x140001912  pop     r13
0x140001914  pop     r12
0x140001916  pop     rdi
0x140001917  pop     rsi
0x140001918  pop     rbp
0x140001919  pop     rbx
0x14000191a  retn
```
