# PxTapiGetCallAddressID

- ea: `0x140012a00`
- end: `0x140012b13`
- name: `PxTapiGetCallAddressID`
- size: `275`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x140001b54`
- `0x140001bc8`
- `0x140007308`
- `0x1400113a0`
- `0x140012a00`
- `0x1400156d8`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012a9c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140012a9c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012ad4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012ad4`

## pseudocode

```c
__int64 __fastcall PxTapiGetCallAddressID(__int64 a1)
{
  __int64 v2; // r8
  _DWORD *v4; // rbx
  PVOID Entry; // [rsp+50h] [rbp+8h] BYREF

  Entry = 0;
  if ( IsVcValid(*(_QWORD *)(a1 + 56), &Entry) )
  {
    v4 = Entry;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 67, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids, Entry);
    *((_BYTE *)v4 + 520) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)v4 + 64);
    *(_DWORD *)(a1 + 64) = *(_DWORD *)(*((_QWORD *)v4 + 33) + 32LL);
    if ( v4[7]-- == 1 )
      DoDerefVcWork(v4);
    else
      KeReleaseSpinLock((PKSPIN_LOCK)v4 + 64, *((_BYTE *)v4 + 520));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 68, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
      WPP_SF_P(WPP_GLOBAL_Control->AttachedDevice, 66, v2, *(_QWORD *)(a1 + 56));
    return 3221299213LL;
  }
}

```

## disassembly

```asm
0x140012a00  push    rbx
0x140012a02  push    rbp
0x140012a03  push    rsi
0x140012a04  push    rdi
0x140012a05  sub     rsp, 28h
0x140012a09  mov     rsi, rcx
0x140012a0c  mov     [rsp+48h+Entry], 0
0x140012a15  mov     rcx, [rcx+38h]
0x140012a19  lea     rdx, [rsp+48h+Entry]
0x140012a1e  call    IsVcValid
0x140012a23  test    al, al
0x140012a25  jnz     short loc_140012A5C
0x140012a27  mov     rcx, cs:WPP_GLOBAL_Control
0x140012a2e  lea     rdi, WPP_GLOBAL_Control
0x140012a35  cmp     rcx, rdi
0x140012a38  jz      short loc_140012A52
0x140012a3a  cmp     byte ptr [rcx+29h], 3
0x140012a3e  jb      short loc_140012A52
0x140012a40  mov     r9, [rsi+38h]
0x140012a44  mov     edx, 42h ; 'B'
0x140012a49  mov     rcx, [rcx+18h]
0x140012a4d  call    WPP_SF_P
0x140012a52  mov     eax, 0C001200Dh
0x140012a57  jmp     loc_140012B09
0x140012a5c  mov     rcx, cs:WPP_GLOBAL_Control
0x140012a63  lea     rdi, WPP_GLOBAL_Control
0x140012a6a  mov     rbx, [rsp+48h+Entry]
0x140012a6f  cmp     rcx, rdi
0x140012a72  jz      short loc_140012A92
0x140012a74  cmp     byte ptr [rcx+29h], 4
0x140012a78  jb      short loc_140012A92
0x140012a7a  mov     rcx, [rcx+18h]
0x140012a7e  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x140012a85  mov     edx, 43h ; 'C'
0x140012a8a  mov     r9, rbx
0x140012a8d  call    WPP_SF_q
0x140012a92  lea     rbp, [rbx+200h]
0x140012a99  mov     rcx, rbp; SpinLock
0x140012a9c  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140012aa3  nop     dword ptr [rax+rax+00h]
0x140012aa8  mov     [rbx+208h], al
0x140012aae  mov     rax, [rbx+108h]
0x140012ab5  mov     edx, [rax+20h]
0x140012ab8  mov     [rsi+40h], edx
0x140012abb  add     dword ptr [rbx+1Ch], 0FFFFFFFFh
0x140012abf  jnz     short loc_140012ACB
0x140012ac1  mov     rcx, rbx; Entry
0x140012ac4  call    DoDerefVcWork
0x140012ac9  jmp     short loc_140012AE0
0x140012acb  mov     dl, [rbx+208h]; NewIrql
0x140012ad1  mov     rcx, rbp; SpinLock
0x140012ad4  call    cs:__imp_KeReleaseSpinLock
0x140012adb  nop     dword ptr [rax+rax+00h]
0x140012ae0  mov     rcx, cs:WPP_GLOBAL_Control
0x140012ae7  cmp     rcx, rdi
0x140012aea  jz      short loc_140012B07
0x140012aec  cmp     byte ptr [rcx+29h], 4
0x140012af0  jb      short loc_140012B07
0x140012af2  mov     rcx, [rcx+18h]
0x140012af6  lea     r8, WPP_a6f614c6986b3fb356aa18da61a57bd2_Traceguids
0x140012afd  mov     edx, 44h ; 'D'
0x140012b02  call    WPP_SF_
0x140012b07  xor     eax, eax
0x140012b09  add     rsp, 28h
0x140012b0d  pop     rdi
0x140012b0e  pop     rsi
0x140012b0f  pop     rbp
0x140012b10  pop     rbx
0x140012b11  retn
```
