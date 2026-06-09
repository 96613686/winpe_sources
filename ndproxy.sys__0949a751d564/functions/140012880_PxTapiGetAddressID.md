# PxTapiGetAddressID

- ea: `0x140012880`
- end: `0x140012988`
- name: `PxTapiGetAddressID`
- size: `264`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x140001b54`
- `0x140006c1c`
- `0x140007308`
- `0x1400112d8`
- `0x140012880`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001290b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001290b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012933`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012949`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012933`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012949`

## pseudocode

```c
__int64 __fastcall PxTapiGetAddressID(__int64 a1)
{
  __int64 v2; // r8
  _BYTE *v4; // rbx
  KSPIN_LOCK *v5; // rsi
  bool v6; // zf
  KIRQL v7; // dl
  PVOID P; // [rsp+50h] [rbp+8h] BYREF

  P = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 61, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids);
  if ( IsTapiLineValid(*(_DWORD *)(a1 + 56), (struct _SINGLE_LIST_ENTRY **)&P) )
  {
    v4 = P;
    v5 = (KSPIN_LOCK *)((char *)P + 120);
    v4[128] = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)P + 15);
    *(_DWORD *)(a1 + 64) = 0;
    v6 = (*((_DWORD *)v4 + 4))-- == 1;
    v7 = v4[128];
    if ( v6 )
    {
      KeReleaseSpinLock(v5, v7);
      FreeTapiLine(v4);
    }
    else
    {
      KeReleaseSpinLock(v5, v7);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 63, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_P(WPP_GLOBAL_Control->AttachedDevice, 62, v2, *(_QWORD *)(a1 + 56));
    return 4098;
  }
}

```

## disassembly

```asm
0x140012880  push    rbx
0x140012882  push    rbp
0x140012883  push    rsi
0x140012884  push    rdi
0x140012885  sub     rsp, 28h
0x140012889  mov     rdi, rcx
0x14001288c  mov     [rsp+48h+P], 0
0x140012895  mov     rcx, cs:WPP_GLOBAL_Control
0x14001289c  lea     rbp, WPP_GLOBAL_Control
0x1400128a3  cmp     rcx, rbp
0x1400128a6  jz      short loc_1400128C3
0x1400128a8  cmp     byte ptr [rcx+29h], 4
0x1400128ac  jb      short loc_1400128C3
0x1400128ae  mov     rcx, [rcx+18h]
0x1400128b2  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x1400128b9  mov     edx, 3Dh ; '='
0x1400128be  call    WPP_SF_
0x1400128c3  mov     ecx, [rdi+38h]
0x1400128c6  lea     rdx, [rsp+48h+P]
0x1400128cb  call    IsTapiLineValid
0x1400128d0  test    al, al
0x1400128d2  jnz     short loc_1400128FF
0x1400128d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400128db  cmp     rcx, rbp
0x1400128de  jz      short loc_1400128F8
0x1400128e0  cmp     byte ptr [rcx+29h], 3
0x1400128e4  jb      short loc_1400128F8
0x1400128e6  mov     r9, [rdi+38h]
0x1400128ea  mov     edx, 3Eh ; '>'
0x1400128ef  mov     rcx, [rcx+18h]
0x1400128f3  call    WPP_SF_P
0x1400128f8  mov     eax, 1002h
0x1400128fd  jmp     short loc_14001297E
0x1400128ff  mov     rbx, [rsp+48h+P]
0x140012904  lea     rsi, [rbx+78h]
0x140012908  mov     rcx, rsi; SpinLock
0x14001290b  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140012912  nop     dword ptr [rax+rax+00h]
0x140012917  mov     [rbx+80h], al
0x14001291d  mov     rcx, rsi; SpinLock
0x140012920  mov     dword ptr [rdi+40h], 0
0x140012927  add     dword ptr [rbx+10h], 0FFFFFFFFh
0x14001292b  mov     dl, [rbx+80h]; NewIrql
0x140012931  jnz     short loc_140012949
0x140012933  call    cs:__imp_KeReleaseSpinLock
0x14001293a  nop     dword ptr [rax+rax+00h]
0x14001293f  mov     rcx, rbx; P
0x140012942  call    FreeTapiLine
0x140012947  jmp     short loc_140012955
0x140012949  call    cs:__imp_KeReleaseSpinLock
0x140012950  nop     dword ptr [rax+rax+00h]
0x140012955  mov     rcx, cs:WPP_GLOBAL_Control
0x14001295c  cmp     rcx, rbp
0x14001295f  jz      short loc_14001297C
0x140012961  cmp     byte ptr [rcx+29h], 4
0x140012965  jb      short loc_14001297C
0x140012967  mov     rcx, [rcx+18h]
0x14001296b  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x140012972  mov     edx, 3Fh ; '?'
0x140012977  call    WPP_SF_
0x14001297c  xor     eax, eax
0x14001297e  add     rsp, 28h
0x140012982  pop     rdi
0x140012983  pop     rsi
0x140012984  pop     rbp
0x140012985  pop     rbx
0x140012986  retn
```
