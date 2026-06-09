# PxTapiCompleteDropIrps

- ea: `0x140011d30`
- end: `0x140011e7a`
- name: `PxTapiCompleteDropIrps`
- size: `330`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000f250`
- `0x14000fcb0`
- `0x140011c00`

## callees

- `0x140001b54`
- `0x140001bc8`
- `0x140001c0c`
- `0x140011d30`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011e27`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140011e27`
- `ntoskrnl!IofCompleteRequest` at `0x140011e18`
- `ntoskrnl!IofCompleteRequest` at `0x140011e18`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011db8`
- `ntoskrnl!KeReleaseSpinLock` at `0x140011db8`

## pseudocode

```c
void __fastcall PxTapiCompleteDropIrps(__int64 a1)
{
  _QWORD *v2; // rbx
  _QWORD *v3; // rdi
  __int64 v4; // rax
  __int64 v5; // rbp
  __int64 v6; // rax

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 129, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids, a1);
  v2 = (_QWORD *)(a1 + 96);
  while ( 1 )
  {
    v3 = (_QWORD *)*v2;
    if ( (_QWORD *)*v2 == v2 )
      break;
    if ( (_QWORD *)v3[1] != v2 || (v4 = *v3, *(_QWORD **)(*v3 + 8LL) != v3) )
      __fastfail(3u);
    *v2 = v4;
    *(_QWORD *)(v4 + 8) = v2;
    if ( (_QWORD *)*v2 == v2 )
      *(_DWORD *)(a1 + 32) &= ~0x10u;
    KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 512), *(_BYTE *)(a1 + 520));
    v5 = v3[2];
    _InterlockedExchange64((volatile __int64 *)(v5 + 104), 0);
    v6 = (unsigned int)(*((_DWORD *)v3 + 10) - 1);
    *(_DWORD *)(v5 + 48) = 0;
    *(_QWORD *)(v5 + 56) = v6 + 56;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        130,
        WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids,
        v5,
        *((_DWORD *)v3 + 8));
    IofCompleteRequest((PIRP)v5, 0);
    *(_BYTE *)(a1 + 520) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 512));
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 131, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids);
}

```

## disassembly

```asm
0x140011d30  push    rbx
0x140011d32  push    rbp
0x140011d33  push    rsi
0x140011d34  push    rdi
0x140011d35  push    r13
0x140011d37  push    r14
0x140011d39  sub     rsp, 38h
0x140011d3d  mov     rsi, rcx
0x140011d40  mov     rcx, cs:WPP_GLOBAL_Control
0x140011d47  lea     r13, WPP_GLOBAL_Control
0x140011d4e  cmp     rcx, r13
0x140011d51  jz      short loc_140011D71
0x140011d53  cmp     byte ptr [rcx+29h], 5
0x140011d57  jb      short loc_140011D71
0x140011d59  mov     rcx, [rcx+18h]
0x140011d5d  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x140011d64  mov     edx, 81h
0x140011d69  mov     r9, rsi
0x140011d6c  call    WPP_SF_q
0x140011d71  lea     rbx, [rsi+60h]
0x140011d75  mov     rdi, [rbx]
0x140011d78  cmp     rdi, rbx
0x140011d7b  jz      loc_140011E45
0x140011d81  cmp     [rdi+8], rbx
0x140011d85  jnz     loc_140011E3E
0x140011d8b  mov     rax, [rdi]
0x140011d8e  cmp     [rax+8], rdi
0x140011d92  jnz     loc_140011E3E
0x140011d98  mov     [rbx], rax
0x140011d9b  mov     [rax+8], rbx
0x140011d9f  cmp     [rbx], rbx
0x140011da2  jnz     short loc_140011DA8
0x140011da4  and     dword ptr [rsi+20h], 0FFFFFFEFh
0x140011da8  mov     dl, [rsi+208h]; NewIrql
0x140011dae  lea     r14, [rsi+200h]
0x140011db5  mov     rcx, r14; SpinLock
0x140011db8  call    cs:__imp_KeReleaseSpinLock
0x140011dbf  nop     dword ptr [rax+rax+00h]
0x140011dc4  mov     rbp, [rdi+10h]
0x140011dc8  xor     eax, eax
0x140011dca  xchg    rax, [rbp+68h]
0x140011dce  mov     eax, [rdi+28h]
0x140011dd1  dec     eax
0x140011dd3  mov     dword ptr [rbp+30h], 0
0x140011dda  add     rax, 38h ; '8'
0x140011dde  mov     [rbp+38h], rax
0x140011de2  mov     rcx, cs:WPP_GLOBAL_Control
0x140011de9  cmp     rcx, r13
0x140011dec  jz      short loc_140011E13
0x140011dee  cmp     byte ptr [rcx+29h], 5
0x140011df2  jb      short loc_140011E13
0x140011df4  mov     eax, [rdi+20h]
0x140011df7  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x140011dfe  mov     rcx, [rcx+18h]
0x140011e02  mov     edx, 82h
0x140011e07  mov     r9, rbp
0x140011e0a  mov     [rsp+68h+var_48], eax
0x140011e0e  call    WPP_SF_qD
0x140011e13  xor     edx, edx; PriorityBoost
0x140011e15  mov     rcx, rbp; Irp
0x140011e18  call    cs:__imp_IofCompleteRequest
0x140011e1f  nop     dword ptr [rax+rax+00h]
0x140011e24  mov     rcx, r14; SpinLock
0x140011e27  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140011e2e  nop     dword ptr [rax+rax+00h]
0x140011e33  mov     [rsi+208h], al
0x140011e39  jmp     loc_140011D75
0x140011e3e  mov     ecx, 3
0x140011e43  int     29h; Win8: RtlFailFast(ecx)
0x140011e45  mov     rcx, cs:WPP_GLOBAL_Control
0x140011e4c  cmp     rcx, r13
0x140011e4f  jz      short loc_140011E6C
0x140011e51  cmp     byte ptr [rcx+29h], 5
0x140011e55  jb      short loc_140011E6C
0x140011e57  mov     rcx, [rcx+18h]
0x140011e5b  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x140011e62  mov     edx, 83h
0x140011e67  call    WPP_SF_
0x140011e6c  add     rsp, 38h
0x140011e70  pop     r14
0x140011e72  pop     r13
0x140011e74  pop     rdi
0x140011e75  pop     rsi
0x140011e76  pop     rbp
0x140011e77  pop     rbx
0x140011e78  retn
```
