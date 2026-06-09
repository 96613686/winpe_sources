# PxTapiCompleteAllIrps

- ea: `0x140011c00`
- end: `0x140011d27`
- name: `PxTapiCompleteAllIrps`
- size: `295`
- prototype: `char __fastcall(__int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140003940`
- `0x140004760`
- `0x140011ab0`

## callees

- `0x140001b54`
- `0x140001bc8`
- `0x140001c0c`
- `0x140011c00`
- `0x140011d30`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011ce2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011ce2`
- `ntoskrnl!IofCompleteRequest` at `0x140011cd3`
- `ntoskrnl!IofCompleteRequest` at `0x140011cd3`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011c73`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011c73`

## pseudocode

```c
char __fastcall PxTapiCompleteAllIrps(__int64 a1)
{
  int v2; // eax
  __int64 v3; // rdi
  KIRQL v4; // dl
  __int64 v5; // rsi
  __int64 v6; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 132, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids, a1);
  v2 = *(_DWORD *)(a1 + 32);
  if ( (v2 & 0x10) != 0 )
    LOBYTE(v2) = PxTapiCompleteDropIrps(a1);
  v3 = *(_QWORD *)(a1 + 112);
  if ( v3 )
  {
    v4 = *(_BYTE *)(a1 + 520);
    *(_QWORD *)(a1 + 112) = 0;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 512), v4);
    v5 = *(_QWORD *)(v3 + 16);
    _InterlockedExchange64((volatile __int64 *)(v5 + 104), 0);
    v6 = (unsigned int)(*(_DWORD *)(v3 + 40) - 1);
    *(_DWORD *)(v5 + 48) = 0;
    *(_QWORD *)(v5 + 56) = v6 + 56;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        133,
        WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids,
        v5,
        *(_DWORD *)(v3 + 32));
    IofCompleteRequest((PIRP)v5, 0);
    LOBYTE(v2) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 512));
    *(_BYTE *)(a1 + 520) = v2;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    LOBYTE(v2) = WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 134, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids);
  return v2;
}

```

## disassembly

```asm
0x140011c00  push    rbx
0x140011c02  push    rbp
0x140011c03  push    rsi
0x140011c04  push    rdi
0x140011c05  push    r12
0x140011c07  sub     rsp, 30h
0x140011c0b  mov     rbx, rcx
0x140011c0e  mov     rcx, cs:WPP_GLOBAL_Control
0x140011c15  lea     r12, WPP_GLOBAL_Control
0x140011c1c  cmp     rcx, r12
0x140011c1f  jz      short loc_140011C3F
0x140011c21  cmp     byte ptr [rcx+29h], 5
0x140011c25  jb      short loc_140011C3F
0x140011c27  mov     rcx, [rcx+18h]
0x140011c2b  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x140011c32  mov     edx, 84h
0x140011c37  mov     r9, rbx
0x140011c3a  call    WPP_SF_q
0x140011c3f  mov     eax, [rbx+20h]
0x140011c42  test    al, 10h
0x140011c44  jz      short loc_140011C4E
0x140011c46  mov     rcx, rbx
0x140011c49  call    PxTapiCompleteDropIrps
0x140011c4e  mov     rdi, [rbx+70h]
0x140011c52  test    rdi, rdi
0x140011c55  jz      loc_140011CF4
0x140011c5b  mov     dl, [rbx+208h]; NewIrql
0x140011c61  lea     rbp, [rbx+200h]
0x140011c68  mov     rcx, rbp; SpinLock
0x140011c6b  mov     qword ptr [rbx+70h], 0
0x140011c73  call    cs:__imp_KeReleaseSpinLock
0x140011c7a  nop     dword ptr [rax+rax+00h]
0x140011c7f  mov     rsi, [rdi+10h]
0x140011c83  xor     eax, eax
0x140011c85  xchg    rax, [rsi+68h]
0x140011c89  mov     eax, [rdi+28h]
0x140011c8c  dec     eax
0x140011c8e  mov     dword ptr [rsi+30h], 0
0x140011c95  add     rax, 38h ; '8'
0x140011c99  mov     [rsi+38h], rax
0x140011c9d  mov     rcx, cs:WPP_GLOBAL_Control
0x140011ca4  cmp     rcx, r12
0x140011ca7  jz      short loc_140011CCE
0x140011ca9  cmp     byte ptr [rcx+29h], 5
0x140011cad  jb      short loc_140011CCE
0x140011caf  mov     eax, [rdi+20h]
0x140011cb2  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x140011cb9  mov     rcx, [rcx+18h]
0x140011cbd  mov     edx, 85h
0x140011cc2  mov     r9, rsi
0x140011cc5  mov     [rsp+58h+var_38], eax
0x140011cc9  call    WPP_SF_qD
0x140011cce  xor     edx, edx; PriorityBoost
0x140011cd0  mov     rcx, rsi; Irp
0x140011cd3  call    cs:__imp_IofCompleteRequest
0x140011cda  nop     dword ptr [rax+rax+00h]
0x140011cdf  mov     rcx, rbp; SpinLock
0x140011ce2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140011ce9  nop     dword ptr [rax+rax+00h]
0x140011cee  mov     [rbx+208h], al
0x140011cf4  mov     rcx, cs:WPP_GLOBAL_Control
0x140011cfb  cmp     rcx, r12
0x140011cfe  jz      short loc_140011D1B
0x140011d00  cmp     byte ptr [rcx+29h], 5
0x140011d04  jb      short loc_140011D1B
0x140011d06  mov     rcx, [rcx+18h]
0x140011d0a  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x140011d11  mov     edx, 86h
0x140011d16  call    WPP_SF_
0x140011d1b  add     rsp, 30h
0x140011d1f  pop     r12
0x140011d21  pop     rdi
0x140011d22  pop     rsi
0x140011d23  pop     rbp
0x140011d24  pop     rbx
0x140011d25  retn
```
