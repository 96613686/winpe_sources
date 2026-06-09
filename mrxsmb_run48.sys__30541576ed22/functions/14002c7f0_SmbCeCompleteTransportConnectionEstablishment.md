# SmbCeCompleteTransportConnectionEstablishment

- ea: `0x14002c7f0`
- end: `0x14002cbed`
- name: `SmbCeCompleteTransportConnectionEstablishment`
- size: `1021`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000a260`
- `0x140013470`
- `0x1400135e0`
- `0x140013650`
- `0x1400181f0`
- `0x14002c7f0`
- `0x140030bb0`
- `0x140037bb8`
- `0x14003faa8`
- `0x140042394`
- `0x140059ea0`

## import_xrefs

- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14002c908`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14002c99d`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14002c908`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14002c99d`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14002c8e6`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14002c8e6`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002c98c`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002ca96`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002cadc`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002c98c`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002ca96`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002cadc`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14002c887`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14002c887`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002c89a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14002c89a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002cbc8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002cbc8`

## pseudocode

```c
void __fastcall SmbCeCompleteTransportConnectionEstablishment(PVOID P, __int64 a2, __int64 a3)
{
  __int64 v3; // r12
  int v5; // ebp
  unsigned __int64 v6; // rsi
  __int64 v7; // rdi
  __int64 v8; // r13
  __int64 v9; // r14
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rax
  __int64 v13; // rax
  KIRQL v14; // dl
  __int64 v15; // rax
  int v16; // ecx
  int v17; // r8d
  char v18; // al
  int v19; // ebp
  KIRQL v20; // dl
  KIRQL v21; // dl
  __int64 v22; // rax
  int v23; // eax
  __int64 v24; // r14
  _QWORD *v25; // rcx
  void (**v26)(void); // rcx
  unsigned int v27; // [rsp+30h] [rbp-48h]
  PVOID pContext; // [rsp+80h] [rbp+8h] BYREF
  __int64 v29; // [rsp+88h] [rbp+10h]

  v3 = *((_QWORD *)P + 3);
  v5 = *((_DWORD *)P + 2);
  v6 = v3 & 0xFFFFFFFFFFFFFFFEuLL;
  v29 = *((_QWORD *)P + 2);
  v7 = *(_QWORD *)((v3 & 0xFFFFFFFFFFFFFFFEuLL) + 432);
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_qLd(WPP_GLOBAL_Control->AttachedDevice, a2, a3, *(_QWORD *)(v6 + 432), v5, *((_DWORD *)P + 3));
    }
    *(_QWORD *)(v6 + 384) = 0;
    goto LABEL_41;
  }
  v8 = *(_QWORD *)(v7 + 24);
  v9 = _InterlockedExchange64((volatile __int64 *)P + 4, 0);
  LOBYTE(pContext) = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v8 + 1920));
  *(_DWORD *)(v8 + 2352) = (unsigned int)PsGetCurrentThreadId();
  if ( *(_DWORD *)(v9 + 320) == 2 )
  {
    v12 = *(_QWORD *)(v9 + 32);
    if ( *(_DWORD *)(v12 + 56) != 1 || !*(_BYTE *)(v12 + 69) || !(_BYTE)word_14007D202 || *(_DWORD *)(v7 + 784) )
      goto LABEL_14;
    ExAcquirePushLockSharedEx(&MRxSmbRdmaRundownSrwLock, 0, v10, v11);
    if ( MRxSmbRdmaRundownState )
    {
      ExReleasePushLockSharedEx(&MRxSmbRdmaRundownSrwLock, 0);
LABEL_14:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qZ(
          WPP_GLOBAL_Control->AttachedDevice,
          12,
          (unsigned int)&WPP_135b509c546f39c2b4adcf37810e0da5_Traceguids,
          v7,
          v7 + 80);
      }
      v13 = 0x19BC000020CLL;
LABEL_19:
      *((_QWORD *)P + 1) = v13;
      *(_QWORD *)(v6 + 384) = 0;
      VctDereferenceEndpoint((PVOID)v9);
      v14 = (unsigned __int8)pContext;
      *(_DWORD *)(v8 + 2352) = -1;
      ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v8 + 1920), v14);
      goto LABEL_40;
    }
    ExReleasePushLockSharedEx(&MRxSmbRdmaRundownSrwLock, 0);
  }
  v15 = SmbCseInitializeSlidingWindowLite();
  *(_QWORD *)(v9 + 512) = v15;
  if ( !v15 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qZ(
        WPP_GLOBAL_Control->AttachedDevice,
        13,
        (unsigned int)&WPP_135b509c546f39c2b4adcf37810e0da5_Traceguids,
        v7,
        v7 + 80);
    }
    v13 = 3221225626LL;
    goto LABEL_19;
  }
  if ( (Microsoft_Windows_SMBClientEnableBits & 8) != 0 )
    McTemplateK0hzr0p_EtwWriteTransfer(
      v16,
      (unsigned int)&SmbInitializeMidWindow,
      v17,
      *(_WORD *)(v7 + 80) >> 1,
      *(_QWORD *)(v7 + 88),
      v15);
  if ( *(_WORD *)(v9 + 334) > 1u || *(_WORD *)(v9 + 332) > 1u )
  {
    v18 = *(_BYTE *)(v7 + 737);
    if ( (v18 & 0xC) == 0 )
      *(_BYTE *)(v7 + 737) = v18 & 0xF3 | 4;
  }
  v19 = SmbCeBindObjectToEndpointLite(*(_QWORD *)(v6 + 384), v9, v6);
  VctDereferenceEndpoint((PVOID)v9);
  if ( v19 >= 0 )
  {
    SmbCeReferenceBindingObject(v6);
    v21 = (unsigned __int8)pContext;
    *(_DWORD *)(v8 + 2352) = -1;
    ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v8 + 1920), v21);
    *(_QWORD *)P = SmbCeCompleteNegotiatedConnectionEstablishment;
    v22 = *(_QWORD *)(v7 + 56);
    if ( v22 )
    {
      v23 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, __int64, PVOID))(v22 + 800))(v7, v6, v3 & 1, P);
    }
    else
    {
      v24 = *((_QWORD *)P + 5);
      v27 = *(unsigned __int16 *)(v7 + 80) + 1778;
      pContext = 0;
      v5 = SmbCeInitializeExchange((char **)&pContext, 0, v6, (_DWORD *)v7, 0, 0, v27, &InitialNegotiateDispatch);
      if ( v5 )
        goto LABEL_40;
      v25 = pContext;
      _InterlockedOr((volatile signed __int32 *)pContext + 17, 0x2010u);
      v25[128] = P;
      v25[129] = v24;
      *((_DWORD *)v25 + 260) = 256;
      *((_DWORD *)v25 + 261) = 16;
      v23 = SmbCeInitiateExchange(v25);
    }
    v5 = v23;
LABEL_40:
    if ( v5 == 259 )
      return;
    goto LABEL_41;
  }
  v20 = (unsigned __int8)pContext;
  *(_DWORD *)(v8 + 2352) = -1;
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v8 + 1920), v20);
  *((_QWORD *)P + 1) = (unsigned int)v19 | 0x19500000000LL;
LABEL_41:
  v26 = (void (**)(void))v29;
  *(_QWORD *)(v29 + 8) = *((_QWORD *)P + 1);
  (*v26)();
  ExFreePoolWithTag(P, 0x6D536243u);
}

```

## disassembly

```asm
0x14002c7f0  mov     [rsp+arg_10], rbx
0x14002c7f5  push    rbp
0x14002c7f6  push    rsi
0x14002c7f7  push    rdi
0x14002c7f8  push    r12
0x14002c7fa  push    r13
0x14002c7fc  push    r14
0x14002c7fe  push    r15
0x14002c800  sub     rsp, 40h
0x14002c804  mov     r12, [rcx+18h]
0x14002c808  mov     rbx, rcx
0x14002c80b  mov     ebp, [rcx+8]
0x14002c80e  mov     rsi, r12
0x14002c811  mov     rax, [rcx+10h]
0x14002c815  and     rsi, 0FFFFFFFFFFFFFFFEh
0x14002c819  mov     [rsp+78h+arg_8], rax
0x14002c821  mov     rdi, [rsi+1B0h]
0x14002c828  test    ebp, ebp
0x14002c82a  jns     short loc_14002C872
0x14002c82c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002c833  lea     rax, WPP_GLOBAL_Control
0x14002c83a  cmp     rcx, rax
0x14002c83d  jz      short loc_14002C863
0x14002c83f  mov     eax, [rcx+2Ch]
0x14002c842  test    al, 1
0x14002c844  jz      short loc_14002C863
0x14002c846  cmp     byte ptr [rcx+29h], 1
0x14002c84a  jb      short loc_14002C863
0x14002c84c  mov     eax, [rbx+0Ch]
0x14002c84f  mov     r9, rdi
0x14002c852  mov     rcx, [rcx+18h]
0x14002c856  mov     dword ptr [rsp+78h+var_50], eax
0x14002c85a  mov     dword ptr [rsp+78h+var_58], ebp
0x14002c85e  call    WPP_SF_qLd
0x14002c863  xor     r15d, r15d
0x14002c866  mov     [rsi+180h], r15
0x14002c86d  jmp     loc_14002CBA8
0x14002c872  mov     r13, [rdi+18h]
0x14002c876  xor     r15d, r15d
0x14002c879  mov     r14d, r15d
0x14002c87c  xchg    r14, [rcx+20h]
0x14002c880  lea     rcx, [r13+780h]; SpinLock
0x14002c887  call    cs:__imp_ExAcquireSpinLockExclusive
0x14002c88e  nop     dword ptr [rax+rax+00h]
0x14002c893  mov     byte ptr [rsp+78h+pContext], al
0x14002c89a  call    cs:__imp_PsGetCurrentThreadId
0x14002c8a1  nop     dword ptr [rax+rax+00h]
0x14002c8a6  mov     [r13+930h], eax
0x14002c8ad  cmp     dword ptr [r14+140h], 2
0x14002c8b5  jnz     loc_14002C9A9
0x14002c8bb  mov     rax, [r14+20h]
0x14002c8bf  cmp     dword ptr [rax+38h], 1
0x14002c8c3  jnz     short loc_14002C914
0x14002c8c5  cmp     [rax+45h], r15b
0x14002c8c9  jz      short loc_14002C914
0x14002c8cb  cmp     byte ptr cs:word_14007D202, r15b
0x14002c8d2  jz      short loc_14002C914
0x14002c8d4  cmp     [rdi+310h], r15d
0x14002c8db  jnz     short loc_14002C914
0x14002c8dd  xor     edx, edx
0x14002c8df  lea     rcx, MRxSmbRdmaRundownSrwLock
0x14002c8e6  call    cs:__imp_ExAcquirePushLockSharedEx
0x14002c8ed  nop     dword ptr [rax+rax+00h]
0x14002c8f2  xor     edx, edx
0x14002c8f4  lea     rcx, MRxSmbRdmaRundownSrwLock
0x14002c8fb  cmp     cs:MRxSmbRdmaRundownState, r15d
0x14002c902  jz      loc_14002C99D
0x14002c908  call    cs:__imp_ExReleasePushLockSharedEx
0x14002c90f  nop     dword ptr [rax+rax+00h]
0x14002c914  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002c91b  lea     rax, WPP_GLOBAL_Control
0x14002c922  cmp     rcx, rax
0x14002c925  jz      short loc_14002C955
0x14002c927  mov     eax, [rcx+2Ch]
0x14002c92a  test    al, 1
0x14002c92c  jz      short loc_14002C955
0x14002c92e  cmp     byte ptr [rcx+29h], 1
0x14002c932  jb      short loc_14002C955
0x14002c934  mov     rcx, [rcx+18h]
0x14002c938  lea     rax, [rdi+50h]
0x14002c93c  mov     edx, 0Ch
0x14002c941  mov     [rsp+78h+var_58], rax
0x14002c946  mov     r9, rdi
0x14002c949  lea     r8, WPP_135b509c546f39c2b4adcf37810e0da5_Traceguids
0x14002c950  call    WPP_SF_qZ
0x14002c955  mov     rax, 19BC000020Ch
0x14002c95f  mov     [rbx+8], rax
0x14002c963  mov     rcx, r14; pContext
0x14002c966  mov     [rsi+180h], r15
0x14002c96d  call    VctDereferenceEndpoint
0x14002c972  movzx   edx, byte ptr [rsp+78h+pContext]; OldIrql
0x14002c97a  lea     rcx, [r13+780h]; SpinLock
0x14002c981  mov     dword ptr [r13+930h], 0FFFFFFFFh
0x14002c98c  call    cs:__imp_ExReleaseSpinLockExclusive
0x14002c993  nop     dword ptr [rax+rax+00h]
0x14002c998  jmp     loc_14002CBA0
0x14002c99d  call    cs:__imp_ExReleasePushLockSharedEx
0x14002c9a4  nop     dword ptr [rax+rax+00h]
0x14002c9a9  call    SmbCseInitializeSlidingWindowLite
0x14002c9ae  mov     [r14+200h], rax
0x14002c9b5  test    rax, rax
0x14002c9b8  jnz     short loc_14002CA05
0x14002c9ba  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002c9c1  lea     rax, WPP_GLOBAL_Control
0x14002c9c8  cmp     rcx, rax
0x14002c9cb  jz      short loc_14002C9FB
0x14002c9cd  mov     eax, [rcx+2Ch]
0x14002c9d0  test    al, 1
0x14002c9d2  jz      short loc_14002C9FB
0x14002c9d4  cmp     byte ptr [rcx+29h], 1
0x14002c9d8  jb      short loc_14002C9FB
0x14002c9da  mov     rcx, [rcx+18h]
0x14002c9de  lea     rax, [rdi+50h]
0x14002c9e2  mov     edx, 0Dh
0x14002c9e7  mov     [rsp+78h+var_58], rax
0x14002c9ec  mov     r9, rdi
0x14002c9ef  lea     r8, WPP_135b509c546f39c2b4adcf37810e0da5_Traceguids
0x14002c9f6  call    WPP_SF_qZ
0x14002c9fb  mov     eax, 0C000009Ah
0x14002ca00  jmp     loc_14002C95F
0x14002ca05  test    cs:Microsoft_Windows_SMBClientEnableBits, 8
0x14002ca0c  jz      short loc_14002CA31
0x14002ca0e  movzx   r9d, word ptr [rdi+50h]
0x14002ca13  lea     rdx, SmbInitializeMidWindow
0x14002ca1a  mov     [rsp+78h+var_50], rax
0x14002ca1f  mov     rax, [rdi+58h]
0x14002ca23  shr     r9w, 1
0x14002ca27  mov     [rsp+78h+var_58], rax
0x14002ca2c  call    McTemplateK0hzr0p_EtwWriteTransfer
0x14002ca31  cmp     word ptr [r14+14Eh], 1
0x14002ca3a  ja      short loc_14002CA47
0x14002ca3c  cmp     word ptr [r14+14Ch], 1
0x14002ca45  jbe     short loc_14002CA5C
0x14002ca47  movzx   eax, byte ptr [rdi+2E1h]
0x14002ca4e  test    al, 0Ch
0x14002ca50  jnz     short loc_14002CA5C
0x14002ca52  and     al, 0F7h
0x14002ca54  or      al, 4
0x14002ca56  mov     [rdi+2E1h], al
0x14002ca5c  mov     rcx, [rsi+180h]
0x14002ca63  mov     r8, rsi
0x14002ca66  mov     rdx, r14
0x14002ca69  call    SmbCeBindObjectToEndpointLite
0x14002ca6e  mov     rcx, r14; pContext
0x14002ca71  mov     ebp, eax
0x14002ca73  call    VctDereferenceEndpoint
0x14002ca78  test    ebp, ebp
0x14002ca7a  jns     short loc_14002CABA
0x14002ca7c  movzx   edx, byte ptr [rsp+78h+pContext]; OldIrql
0x14002ca84  lea     rcx, [r13+780h]; SpinLock
0x14002ca8b  mov     dword ptr [r13+930h], 0FFFFFFFFh
0x14002ca96  call    cs:__imp_ExReleaseSpinLockExclusive
0x14002ca9d  nop     dword ptr [rax+rax+00h]
0x14002caa2  mov     eax, ebp
0x14002caa4  mov     rcx, 19500000000h
0x14002caae  or      rax, rcx
0x14002cab1  mov     [rbx+8], rax
0x14002cab5  jmp     loc_14002CBA8
0x14002caba  mov     rcx, rsi
0x14002cabd  call    SmbCeReferenceBindingObject
0x14002cac2  movzx   edx, byte ptr [rsp+78h+pContext]; OldIrql
0x14002caca  lea     rcx, [r13+780h]; SpinLock
0x14002cad1  mov     dword ptr [r13+930h], 0FFFFFFFFh
0x14002cadc  call    cs:__imp_ExReleaseSpinLockExclusive
0x14002cae3  nop     dword ptr [rax+rax+00h]
0x14002cae8  lea     rax, SmbCeCompleteNegotiatedConnectionEstablishment
0x14002caef  mov     [rbx], rax
0x14002caf2  mov     rax, [rdi+38h]
0x14002caf6  test    rax, rax
0x14002caf9  jz      short loc_14002CB1D
0x14002cafb  mov     rax, [rax+320h]
0x14002cb02  and     r12b, 1
0x14002cb06  movzx   r8d, r12b
0x14002cb0a  mov     r9, rbx
0x14002cb0d  mov     rdx, rsi
0x14002cb10  mov     rcx, rdi
0x14002cb13  call    _guard_dispatch_icall
0x14002cb18  jmp     loc_14002CB9E
0x14002cb1d  movzx   eax, word ptr [rdi+50h]
0x14002cb21  lea     rcx, InitialNegotiateDispatch
0x14002cb28  mov     r14, [rbx+28h]
0x14002cb2c  add     eax, 6F2h
0x14002cb31  mov     [rsp+78h+var_40], rcx
0x14002cb36  mov     r9, rdi
0x14002cb39  mov     [rsp+78h+var_48], eax
0x14002cb3d  lea     rcx, [rsp+78h+pContext]
0x14002cb45  mov     [rsp+78h+var_50], r15
0x14002cb4a  mov     r8, rsi
0x14002cb4d  xor     edx, edx
0x14002cb4f  mov     [rsp+78h+var_58], r15
0x14002cb54  mov     [rsp+78h+pContext], r15
0x14002cb5c  call    SmbCeInitializeExchange
0x14002cb61  mov     ebp, eax
0x14002cb63  test    eax, eax
0x14002cb65  jnz     short loc_14002CBA0
0x14002cb67  mov     rcx, [rsp+78h+pContext]; pContext
0x14002cb6f  lock or dword ptr [rcx+44h], 2010h
0x14002cb77  mov     [rcx+400h], rbx
0x14002cb7e  mov     [rcx+408h], r14
0x14002cb85  mov     dword ptr [rcx+410h], 100h
0x14002cb8f  mov     dword ptr [rcx+414h], 10h
0x14002cb99  call    SmbCeInitiateExchange
0x14002cb9e  mov     ebp, eax
0x14002cba0  cmp     ebp, 103h
0x14002cba6  jz      short loc_14002CBD4
0x14002cba8  mov     rcx, [rsp+78h+arg_8]
0x14002cbb0  mov     rax, [rbx+8]
0x14002cbb4  mov     [rcx+8], rax
0x14002cbb8  mov     rax, [rcx]
0x14002cbbb  call    _guard_dispatch_icall
0x14002cbc0  mov     edx, 6D536243h; Tag
0x14002cbc5  mov     rcx, rbx; P
0x14002cbc8  call    cs:__imp_ExFreePoolWithTag
0x14002cbcf  nop     dword ptr [rax+rax+00h]
0x14002cbd4  mov     rbx, [rsp+78h+arg_10]
0x14002cbdc  add     rsp, 40h
0x14002cbe0  pop     r15
0x14002cbe2  pop     r14
0x14002cbe4  pop     r13
0x14002cbe6  pop     r12
0x14002cbe8  pop     rdi
0x14002cbe9  pop     rsi
0x14002cbea  pop     rbp
0x14002cbeb  retn
```
