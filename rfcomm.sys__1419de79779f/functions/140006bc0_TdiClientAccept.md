# TdiClientAccept

- ea: `0x140006bc0`
- end: `0x140006f60`
- name: `TdiClientAccept`
- size: `928`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140006f68`
- `0x14000a380`

## callees

- `0x140002e20`
- `0x140003bf4`
- `0x140003cb4`
- `0x140006bc0`
- `0x140007488`
- `0x14000c1cc`
- `0x14000ca20`
- `0x140018d08`
- `0x14001bfa8`
- `0x14001e74c`
- `0x14001fc30`
- `0x14001fc70`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006cf8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006dca`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006ecc`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006cf8`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006dca`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140006ecc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006da7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006e5b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006efb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006f0e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006da7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006e5b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006efb`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006f0e`

## string_xrefs

- `0x140006d2e`: `onecore\drivers\wdm\bluetooth\drivers\tdi\rfcomm\tdi.c`

## pseudocode

```c
_UNKNOWN **__fastcall TdiClientAccept(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  __int64 (__fastcall *v5)(_QWORD, __int64, _QWORD *, _QWORD); // r10
  __int64 v6; // rax
  unsigned int v7; // ecx
  int v8; // eax
  int v9; // edx
  int v10; // r14d
  _QWORD v13[5]; // [rsp+88h] [rbp-11h] BYREF

  v4 = *(_QWORD *)(a1 + 56);
  v5 = *(__int64 (__fastcall **)(_QWORD, __int64, _QWORD *, _QWORD))(a2 + 144);
  if ( v5 )
  {
    *(_OWORD *)v13 = 0x20001C00000001uLL;
    memset(&v13[2], 0, 23);
    v6 = *(_QWORD *)(v4 + 264);
    v7 = *(unsigned __int8 *)(a1 + 184);
    v13[1] = v6;
    LODWORD(v13[4]) = (v7 >> 1) & 0x1F;
    v8 = v5(*(_QWORD *)(a2 + 152), 39, v13, 0);
    v10 = v8;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v9,
        2,
        66,
        (__int64)WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids,
        v8);
  }
  else
  {
    v10 = -1073741258;
  }
  return ChannelCompleteAccept(a1, 0, 0, v10);
}

```

## disassembly

```asm
0x140006bc0  mov     [rsp-8+arg_10], rbx
0x140006bc5  push    rbp
0x140006bc6  push    rsi
0x140006bc7  push    rdi
0x140006bc8  push    r12
0x140006bca  push    r13
0x140006bcc  push    r14
0x140006bce  push    r15
0x140006bd0  lea     rbp, [rsp-27h]
0x140006bd5  sub     rsp, 0C0h
0x140006bdc  mov     rax, cs:__security_cookie
0x140006be3  xor     rax, rsp
0x140006be6  mov     [rbp+57h+var_40], rax
0x140006bea  xor     ebx, ebx
0x140006bec  mov     [rbp+57h+var_70], rcx
0x140006bf0  mov     r12, rdx
0x140006bf3  mov     esi, ebx
0x140006bf5  mov     rdx, rcx
0x140006bf8  mov     rcx, [rcx+38h]
0x140006bfc  mov     r10, [r12+90h]
0x140006c04  mov     rax, [rcx+48h]
0x140006c08  mov     [rbp+57h+var_78], rax
0x140006c0c  mov     rax, [rax+60h]
0x140006c10  mov     r13, [rax+10h]
0x140006c14  mov     [rbp+57h+var_98], rbx
0x140006c18  mov     [rbp+57h+var_A0], rbx
0x140006c1c  test    r10, r10
0x140006c1f  jz      loc_140006F1F
0x140006c25  xor     eax, eax
0x140006c27  lea     r8, [rbp+57h+var_68]
0x140006c2b  xorps   xmm0, xmm0
0x140006c2e  xor     r9d, r9d
0x140006c31  movups  [rbp+57h+var_68], xmm0
0x140006c35  mov     dword ptr [rbp+57h+var_68], 1
0x140006c3c  movups  [rbp+57h+var_58], xmm0
0x140006c40  mov     qword ptr [rbp+57h+var_58+0Fh], rax
0x140006c44  mov     dword ptr [rbp+57h+var_68+4], 20001Ch
0x140006c4b  mov     rax, [rcx+108h]
0x140006c52  movzx   ecx, byte ptr [rdx+0B8h]
0x140006c59  lea     edx, [rbx+27h]
0x140006c5c  mov     qword ptr [rbp+57h+var_68+8], rax
0x140006c60  lea     rax, [rbp+57h+var_A0]
0x140006c64  mov     [rsp+0F0h+var_B0], rax
0x140006c69  lea     rax, [rbp+57h+var_98]
0x140006c6d  mov     [rsp+0F0h+var_B8], rax
0x140006c72  mov     rax, r10
0x140006c75  shr     ecx, 1
0x140006c77  and     ecx, 1Fh
0x140006c7a  mov     [rsp+0F0h+var_C0], rbx
0x140006c7f  mov     [rbp+57h+var_48], ecx
0x140006c82  mov     rcx, [r12+98h]
0x140006c8a  mov     dword ptr [rsp+0F0h+var_C8], ebx
0x140006c8e  mov     [rsp+0F0h+var_D0], rbx
0x140006c93  call    _guard_dispatch_icall
0x140006c98  mov     r14d, eax
0x140006c9b  cmp     [rbp+57h+var_A0], rbx
0x140006c9f  jnz     short loc_140006CE2
0x140006ca1  lea     rdi, WPP_RECORDER_INITIALIZED
0x140006ca8  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140006caf  jz      loc_140006F25
0x140006cb5  mov     rcx, cs:WPP_GLOBAL_Control
0x140006cbc  lea     r15, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x140006cc3  mov     dword ptr [rsp+0F0h+var_C8], eax
0x140006cc7  lea     r9d, [rbx+42h]
0x140006ccb  lea     r8d, [rbx+2]
0x140006ccf  mov     [rsp+0F0h+var_D0], r15
0x140006cd4  mov     rcx, [rcx+40h]
0x140006cd8  call    WPP_RECORDER_SF_d
0x140006cdd  jmp     loc_140006F25
0x140006ce2  cmp     eax, 0C0000016h
0x140006ce7  jz      short loc_140006CF4
0x140006ce9  mov     r14d, 0C0000001h
0x140006cef  jmp     loc_140006F25
0x140006cf4  lea     rcx, [r13+30h]; SpinLock
0x140006cf8  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006cff  nop     dword ptr [rax+rax+00h]
0x140006d04  mov     [r13+38h], al
0x140006d08  lea     rax, [r13+60h]
0x140006d0c  mov     rcx, [rax]
0x140006d0f  cmp     rcx, rax
0x140006d12  jz      short loc_140006D49
0x140006d14  mov     rdx, [rbp+57h+var_98]
0x140006d18  cmp     [rcx+148h], rdx
0x140006d1f  jz      short loc_140006D2B
0x140006d21  mov     rcx, [rcx]
0x140006d24  cmp     rcx, rax
0x140006d27  jnz     short loc_140006D18
0x140006d29  jmp     short loc_140006D49
0x140006d2b  mov     rsi, rcx
0x140006d2e  lea     r9, aOnecoreDrivers_5; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140006d35  add     rcx, 18h
0x140006d39  mov     edx, 444E4946h
0x140006d3e  mov     r8d, 6E3h
0x140006d44  call    RefObj_AddRefEx
0x140006d49  lea     rdi, WPP_RECORDER_INITIALIZED
0x140006d50  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140006d57  lea     r15, WPP_73cece3c56ca3b922bd18ab25e85809f_Traceguids
0x140006d5e  jz      short loc_140006D9F
0x140006d60  mov     rax, cs:WPP_GLOBAL_Control
0x140006d67  mov     ecx, 0C0000016h
0x140006d6c  mov     rbx, [rax+40h]
0x140006d70  call    NtStatusTxt
0x140006d75  mov     [rsp+0F0h+var_B8], rax
0x140006d7a  mov     r9d, 43h ; 'C'
0x140006d80  mov     rax, [rbp+57h+var_A0]
0x140006d84  mov     rcx, rbx
0x140006d87  mov     [rsp+0F0h+var_C0], rax
0x140006d8c  mov     [rsp+0F0h+var_C8], rsi
0x140006d91  lea     r8d, [r9-41h]
0x140006d95  mov     [rsp+0F0h+var_D0], r15
0x140006d9a  call    WPP_RECORDER_SF_qqs
0x140006d9f  mov     dl, [r13+38h]; NewIrql
0x140006da3  lea     rcx, [r13+30h]; SpinLock
0x140006da7  call    cs:__imp_KeReleaseSpinLock
0x140006dae  nop     dword ptr [rax+rax+00h]
0x140006db3  test    rsi, rsi
0x140006db6  jnz     short loc_140006DC3
0x140006db8  mov     r14d, 0C0000140h
0x140006dbe  jmp     loc_140006F25
0x140006dc3  lea     rbx, [rsi+30h]
0x140006dc7  mov     rcx, rbx; SpinLock
0x140006dca  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006dd1  nop     dword ptr [rax+rax+00h]
0x140006dd6  cmp     dword ptr [rsi+50h], 0
0x140006dda  mov     [rsi+38h], al
0x140006ddd  jnz     loc_140006F09
0x140006de3  cmp     [rsi+68h], r12
0x140006de7  jnz     loc_140006F09
0x140006ded  mov     edx, 2
0x140006df2  mov     rcx, rsi
0x140006df5  call    TdiConnStateLocked
0x140006dfa  mov     word ptr [rsi+60h], 101h
0x140006e00  xor     r14d, r14d
0x140006e03  mov     rax, qword ptr [rbp+57h+var_68+8]
0x140006e07  mov     [rsi+74h], rax
0x140006e0b  movups  xmm0, [rbp+57h+var_58]
0x140006e0f  mov     rcx, qword ptr [rbp+57h+var_68+8]
0x140006e13  movdqu  xmmword ptr [rsi+7Ch], xmm0
0x140006e18  mov     eax, [rbp+57h+var_48]
0x140006e1b  mov     [rsi+8Ch], eax
0x140006e21  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140006e28  jz      short loc_140006E55
0x140006e2a  mov     dword ptr [rsp+0F0h+var_B0], eax
0x140006e2e  mov     eax, [rsi+74h]
0x140006e31  shr     rcx, 20h
0x140006e35  movzx   edx, cx
0x140006e38  mov     rcx, cs:WPP_GLOBAL_Control
0x140006e3f  mov     dword ptr [rsp+0F0h+var_B8], eax
0x140006e43  mov     dword ptr [rsp+0F0h+var_C0], edx
0x140006e47  mov     [rsp+0F0h+var_C8], rsi
0x140006e4c  mov     rcx, [rcx+40h]
0x140006e50  call    WPP_RECORDER_SF_qDDd
0x140006e55  mov     dl, [rsi+38h]; NewIrql
0x140006e58  mov     rcx, rbx; SpinLock
0x140006e5b  call    cs:__imp_KeReleaseSpinLock
0x140006e62  nop     dword ptr [rax+rax+00h]
0x140006e67  cmp     [rsi+33Ch], r14b
0x140006e6e  jz      loc_140006F25
0x140006e74  cmp     cs:WPP_RECORDER_INITIALIZED, rdi
0x140006e7b  jz      short loc_140006E9C
0x140006e7d  mov     rcx, cs:WPP_GLOBAL_Control
0x140006e84  mov     r9d, 45h ; 'E'
0x140006e8a  mov     [rsp+0F0h+var_D0], r15
0x140006e8f  mov     rcx, [rcx+40h]
0x140006e93  lea     r8d, [r9-32h]
0x140006e97  call    WPP_RECORDER_SF_
0x140006e9c  mov     eax, [rsi+338h]
0x140006ea2  mov     r15, [rbp+57h+var_78]
0x140006ea6  mov     [rbp+57h+var_8C], eax
0x140006ea9  mov     rax, [rsi+74h]
0x140006ead  mov     [rbp+57h+var_88], rax
0x140006eb1  mov     rax, [rsi+68h]
0x140006eb5  lea     rdi, [r15+170h]
0x140006ebc  mov     [rbp+57h+var_90], 1
0x140006ec3  mov     cl, [rax+70h]
0x140006ec6  mov     [rbp+57h+var_80], cl
0x140006ec9  mov     rcx, rdi; SpinLock
0x140006ecc  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140006ed3  nop     dword ptr [rax+rax+00h]
0x140006ed8  lea     rdx, [r15+180h]
0x140006edf  mov     bl, al
0x140006ee1  lea     r8, [rbp+57h+var_90]
0x140006ee5  call    RfcommFindFirewallEntry
0x140006eea  test    rax, rax
0x140006eed  mov     rcx, rdi; SpinLock
0x140006ef0  setnz   dl
0x140006ef3  mov     [rsi+33Dh], dl
0x140006ef9  mov     dl, bl; NewIrql
0x140006efb  call    cs:__imp_KeReleaseSpinLock
0x140006f02  nop     dword ptr [rax+rax+00h]
0x140006f07  jmp     short loc_140006F25
0x140006f09  mov     dl, al; NewIrql
0x140006f0b  mov     rcx, rbx; SpinLock
0x140006f0e  call    cs:__imp_KeReleaseSpinLock
0x140006f15  nop     dword ptr [rax+rax+00h]
0x140006f1a  jmp     loc_140006DB8
0x140006f1f  mov     r14d, 0C0000236h
0x140006f25  mov     r8, [rbp+57h+var_A0]
0x140006f29  mov     r9d, r14d
0x140006f2c  mov     rcx, [rbp+57h+var_70]
0x140006f30  mov     rdx, rsi
0x140006f33  call    ChannelCompleteAccept
0x140006f38  mov     rcx, [rbp+57h+var_40]
0x140006f3c  xor     rcx, rsp; StackCookie
0x140006f3f  call    __security_check_cookie
0x140006f44  mov     rbx, [rsp+0F0h+arg_10]
0x140006f4c  add     rsp, 0C0h
0x140006f53  pop     r15
0x140006f55  pop     r14
0x140006f57  pop     r13
0x140006f59  pop     r12
0x140006f5b  pop     rdi
0x140006f5c  pop     rsi
0x140006f5d  pop     rbp
0x140006f5e  retn
```
