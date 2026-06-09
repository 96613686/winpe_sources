# VctIndDataReady

- ea: `0x140008840`
- end: `0x140008b68`
- name: `VctIndDataReady`
- size: `808`
- prototype: `__int64 __fastcall(__int64, signed __int64, __int64, int)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x1400043a0`
- `0x1400054b0`
- `0x140008840`
- `0x140008b70`
- `0x14000bd10`
- `0x14000dfa8`
- `0x14000ebd8`
- `0x140012014`
- `0x1400126a4`
- `0x14001276c`
- `0x140015344`
- `0x140015890`
- `0x140016640`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140008955`
- `ntoskrnl!KeReleaseSpinLock` at `0x140008955`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400088f9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400088f9`
- `ntoskrnl!DbgPrint` at `0x1400089fa`
- `ntoskrnl!DbgPrint` at `0x1400089fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400088db`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008b40`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400088db`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008b40`
- `mrxsmb!MRxSmbLegacyPerfCtrs` at `0x140008a80`

## string_xrefs

- `0x1400089f3`: `SS mismatch on data ready ind, tear down connection\n`

## pseudocode

```c
__int64 __fastcall VctIndDataReady(__int64 a1, signed __int64 a2, __int64 a3, int a4)
{
  int v4; // r14d
  __int64 v5; // rbp
  unsigned __int64 v7; // r15
  __int64 v9; // rbx
  __int64 v10; // rdi
  __int64 v11; // rdx
  __int64 v12; // rax
  __int64 v13; // rdx
  char v14; // al
  __int64 v15; // rax
  int v17; // [rsp+20h] [rbp-78h]
  unsigned int v18; // [rsp+50h] [rbp-48h] BYREF
  __int64 v19; // [rsp+58h] [rbp-40h] BYREF
  __int128 *v20; // [rsp+60h] [rbp-38h] BYREF
  __int64 v21; // [rsp+A0h] [rbp+8h] BYREF
  unsigned int v22; // [rsp+A8h] [rbp+10h] BYREF

  v21 = a1;
  v4 = a4;
  v5 = *(_QWORD *)(a1 + 384);
  v7 = (unsigned int)a3;
  if ( *(_DWORD *)(a2 + 4) )
  {
    v9 = *(_QWORD *)(a2 + 16);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_qqqDD(WPP_GLOBAL_Control->AttachedDevice, a2, a3, a1, *(_QWORD *)(a2 + 8), v9, a3, a4);
    *(_OWORD *)a2 = 0;
    *(_OWORD *)(a2 + 12) = 0;
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 480), a2, 0) )
    {
      VctTeardownReceiveContext(a2);
      ExFreePoolWithTag((PVOID)a2, 0);
    }
    if ( !v9 )
      return 0;
    v10 = 0;
    s_SmbCeDbSpinLockSavedIrql = KeAcquireSpinLockRaiseToDpc(&s_SmbCeDbSpinLock);
    v11 = *(_QWORD *)(v5 + 368);
    v12 = 0;
    if ( v11 != v5 + 368 )
      v12 = v11 - 32;
    while ( v12 )
    {
      if ( *(_DWORD *)(v12 + 48) == 1 && *(_QWORD *)(v12 + 72) == v9 )
      {
        v10 = *(_QWORD *)(v12 + 56);
        *(_QWORD *)(v12 + 72) = 0;
        break;
      }
      v15 = *(_QWORD *)(v12 + 32);
      if ( v15 == v5 + 368 )
        v12 = 0;
      else
        v12 = v15 - 32;
    }
    KeReleaseSpinLock(&s_SmbCeDbSpinLock, s_SmbCeDbSpinLockSavedIrql);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_96809d50ffaa30ffc961a4216fa88776_Traceguids, v10);
    if ( !v10 )
      return 0;
    if ( !v4 )
    {
      if ( (*(_BYTE *)(v5 + 672) & 8) == 0
        || (!*(_BYTE *)(v10 + 255)
          ? (v14 = SmbCheckSecuritySignatureWithMdl(v10, v5 + 400, (unsigned int)v7, v9))
          : (v14 = SmbCheckSecuritySignaturePartial(v10, v13, (unsigned int)v7, v9)),
            v14) )
      {
        _InterlockedAdd64(
          (volatile signed __int64 *)(MRxSmbLegacyPerfCtrs + ((unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 8)),
          v7);
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(v10 + 152) + 16LL))(v10, v9);
        goto LABEL_32;
      }
      DbgPrint("SS mismatch on data ready ind, tear down connection\n");
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_96809d50ffaa30ffc961a4216fa88776_Traceguids);
      }
      v4 = -1073741629;
      SmbCeTransportDisconnectIndicated(*(PVOID *)(v10 + 80));
    }
    *(_DWORD *)(v10 + 48) = v4;
    *(_DWORD *)(v10 + 40) = v4;
LABEL_32:
    SmbCeDecrementPendingOperationsAndFinalize((PVOID)v10);
    return 0;
  }
  v18 = 0;
  v19 = 0;
  v22 = 0;
  if ( a4 >= 0 )
    VctIndReceive(a1, 1024, a3, a3, v17, &v18, *(_QWORD *)(a2 + 40), &v19, &v20, &v22);
  else
    SmbCeErrorInd((PVOID)v5);
  *(_OWORD *)a2 = 0;
  *(_OWORD *)(a2 + 12) = 0;
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 480), a2, 0) )
  {
    VctTeardownReceiveContext(a2);
    ExFreePoolWithTag((PVOID)a2, 0);
  }
  SmbCepDereferenceServerTransport(&v21);
  return 0;
}

```

## disassembly

```asm
0x140008840  mov     r11, rsp
0x140008843  mov     [r11+8], rcx
0x140008847  push    rbp
0x140008848  push    rsi
0x140008849  push    rdi
0x14000884a  push    r14
0x14000884c  push    r15
0x14000884e  sub     rsp, 70h
0x140008852  cmp     dword ptr [rdx+4], 0
0x140008856  mov     r14d, r9d
0x140008859  mov     rbp, [rcx+180h]
0x140008860  mov     rdi, rdx
0x140008863  mov     r15d, r8d
0x140008866  mov     rsi, rcx
0x140008869  jz      loc_140008AAA
0x14000886f  mov     [r11+18h], rbx
0x140008873  mov     rbx, [rdx+10h]
0x140008877  mov     [r11+20h], r12
0x14000887b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140008882  lea     r12, WPP_GLOBAL_Control
0x140008889  cmp     rcx, r12
0x14000888c  jz      short loc_1400088B7
0x14000888e  test    dword ptr [rcx+2Ch], 400h
0x140008895  jz      short loc_1400088B7
0x140008897  mov     rax, [rdx+8]
0x14000889b  mov     rcx, [rcx+18h]
0x14000889f  mov     [r11-60h], r9d
0x1400088a3  mov     r9, rsi
0x1400088a6  mov     [r11-68h], r15d
0x1400088aa  mov     [r11-70h], rbx
0x1400088ae  mov     [r11-78h], rax
0x1400088b2  call    WPP_SF_qqqDD
0x1400088b7  xorps   xmm0, xmm0
0x1400088ba  xor     eax, eax
0x1400088bc  movups  xmmword ptr [rdi], xmm0
0x1400088bf  movups  xmmword ptr [rdi+0Ch], xmm0
0x1400088c3  lock cmpxchg [rsi+1E0h], rdi
0x1400088cc  jz      short loc_1400088E7
0x1400088ce  mov     rcx, rdi
0x1400088d1  call    VctTeardownReceiveContext
0x1400088d6  xor     edx, edx; Tag
0x1400088d8  mov     rcx, rdi; P
0x1400088db  call    cs:__imp_ExFreePoolWithTag
0x1400088e2  nop     dword ptr [rax+rax+00h]
0x1400088e7  test    rbx, rbx
0x1400088ea  jz      loc_140008A54
0x1400088f0  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x1400088f7  xor     edi, edi
0x1400088f9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140008900  nop     dword ptr [rax+rax+00h]
0x140008905  lea     r8, [rbp+170h]
0x14000890c  mov     cs:s_SmbCeDbSpinLockSavedIrql, al
0x140008912  mov     rdx, [r8]
0x140008915  xor     eax, eax
0x140008917  cmp     rdx, r8
0x14000891a  lea     rcx, [rdx-20h]
0x14000891e  cmovnz  rax, rcx
0x140008922  test    rax, rax
0x140008925  jz      short loc_140008947
0x140008927  cmp     dword ptr [rax+30h], 1
0x14000892b  jnz     loc_1400089C6
0x140008931  cmp     [rax+48h], rbx
0x140008935  jnz     loc_1400089C6
0x14000893b  mov     rdi, [rax+38h]
0x14000893f  mov     qword ptr [rax+48h], 0
0x140008947  movzx   edx, cs:s_SmbCeDbSpinLockSavedIrql; NewIrql
0x14000894e  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x140008955  call    cs:__imp_KeReleaseSpinLock
0x14000895c  nop     dword ptr [rax+rax+00h]
0x140008961  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140008968  cmp     rcx, r12
0x14000896b  jz      short loc_14000898E
0x14000896d  test    dword ptr [rcx+2Ch], 400h
0x140008974  jz      short loc_14000898E
0x140008976  mov     rcx, [rcx+18h]
0x14000897a  lea     r8, WPP_96809d50ffaa30ffc961a4216fa88776_Traceguids
0x140008981  mov     edx, 12h
0x140008986  mov     r9, rdi
0x140008989  call    WPP_SF_q
0x14000898e  test    rdi, rdi
0x140008991  jz      loc_140008A54
0x140008997  test    r14d, r14d
0x14000899a  jnz     loc_140008A3F
0x1400089a0  test    byte ptr [rbp+2A0h], 8
0x1400089a7  jz      loc_140008A73
0x1400089ad  mov     r9, rbx
0x1400089b0  mov     r8d, r15d
0x1400089b3  mov     rcx, rdi
0x1400089b6  cmp     [rdi+0FFh], r14b
0x1400089bd  jz      short loc_1400089DF
0x1400089bf  call    SmbCheckSecuritySignaturePartial
0x1400089c4  jmp     short loc_1400089EB
0x1400089c6  mov     rax, [rax+20h]
0x1400089ca  cmp     rax, r8
0x1400089cd  jnz     short loc_1400089D6
0x1400089cf  xor     eax, eax
0x1400089d1  jmp     loc_140008922
0x1400089d6  add     rax, 0FFFFFFFFFFFFFFE0h
0x1400089da  jmp     loc_140008922
0x1400089df  lea     rdx, [rbp+190h]
0x1400089e6  call    SmbCheckSecuritySignatureWithMdl
0x1400089eb  test    al, al
0x1400089ed  jnz     loc_140008A73
0x1400089f3  lea     rcx, aSsMismatchOnDa; "SS mismatch on data ready ind, tear dow"...
0x1400089fa  call    cs:__imp_DbgPrint
0x140008a01  nop     dword ptr [rax+rax+00h]
0x140008a06  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140008a0d  cmp     rcx, r12
0x140008a10  jz      short loc_140008A30
0x140008a12  test    dword ptr [rcx+2Ch], 200h
0x140008a19  jz      short loc_140008A30
0x140008a1b  mov     rcx, [rcx+18h]
0x140008a1f  lea     r8, WPP_96809d50ffaa30ffc961a4216fa88776_Traceguids
0x140008a26  mov     edx, 13h
0x140008a2b  call    WPP_SF_
0x140008a30  mov     rcx, [rdi+50h]; pContext
0x140008a34  mov     r14d, 0C00000C3h
0x140008a3a  call    SmbCeTransportDisconnectIndicated
0x140008a3f  mov     [rdi+30h], r14d
0x140008a43  mov     [rdi+28h], r14d
0x140008a47  mov     edx, 4
0x140008a4c  mov     rcx, rdi; pContext
0x140008a4f  call    SmbCeDecrementPendingOperationsAndFinalize
0x140008a54  mov     rbx, [rsp+98h+arg_10]
0x140008a5c  xor     eax, eax
0x140008a5e  mov     r12, [rsp+98h+arg_18]
0x140008a66  add     rsp, 70h
0x140008a6a  pop     r15
0x140008a6c  pop     r14
0x140008a6e  pop     rdi
0x140008a6f  pop     rsi
0x140008a70  pop     rbp
0x140008a71  retn
0x140008a73  mov     eax, gs:1A4h
0x140008a7b  mov     r8, r15
0x140008a7e  mov     ecx, eax
0x140008a80  mov     rax, cs:__imp_MRxSmbLegacyPerfCtrs
0x140008a87  shl     rcx, 8
0x140008a8b  add     rcx, [rax]
0x140008a8e  lock add [rcx], r8
0x140008a92  mov     rax, [rdi+98h]
0x140008a99  mov     rdx, rbx
0x140008a9c  mov     rcx, rdi
0x140008a9f  mov     rax, [rax+10h]
0x140008aa3  call    _guard_dispatch_icall
0x140008aa8  jmp     short loc_140008A47
0x140008aaa  mov     [rsp+98h+var_48], 0
0x140008ab2  mov     [rsp+98h+var_40], 0
0x140008abb  mov     [rsp+98h+arg_8], 0
0x140008ac6  test    r14d, r14d
0x140008ac9  jns     short loc_140008AD8
0x140008acb  mov     edx, r14d
0x140008ace  mov     rcx, rbp; pContext
0x140008ad1  call    SmbCeErrorInd
0x140008ad6  jmp     short loc_140008B1C
0x140008ad8  lea     rax, [rsp+98h+arg_8]
0x140008ae0  mov     r9d, r15d
0x140008ae3  mov     [rsp+98h+var_50], rax
0x140008ae8  mov     r8d, r15d
0x140008aeb  lea     rax, [rsp+98h+var_38]
0x140008af0  mov     [rsp+98h+var_58], rax
0x140008af5  lea     rax, [rsp+98h+var_40]
0x140008afa  mov     [rsp+98h+var_60], rax
0x140008aff  mov     rax, [rdx+28h]
0x140008b03  mov     edx, 400h
0x140008b08  mov     [rsp+98h+var_68], rax
0x140008b0d  lea     rax, [rsp+98h+var_48]
0x140008b12  mov     [rsp+98h+var_70], rax
0x140008b17  call    VctIndReceive
0x140008b1c  xorps   xmm0, xmm0
0x140008b1f  xor     eax, eax
0x140008b21  movups  xmmword ptr [rdi], xmm0
0x140008b24  movups  xmmword ptr [rdi+0Ch], xmm0
0x140008b28  lock cmpxchg [rsi+1E0h], rdi
0x140008b31  jz      short loc_140008B4C
0x140008b33  mov     rcx, rdi
0x140008b36  call    VctTeardownReceiveContext
0x140008b3b  xor     edx, edx; Tag
0x140008b3d  mov     rcx, rdi; P
0x140008b40  call    cs:__imp_ExFreePoolWithTag
0x140008b47  nop     dword ptr [rax+rax+00h]
0x140008b4c  lea     rcx, [rsp+98h+arg_0]
0x140008b54  call    SmbCepDereferenceServerTransport
0x140008b59  xor     eax, eax
0x140008b5b  add     rsp, 70h
0x140008b5f  pop     r15
0x140008b61  pop     r14
0x140008b63  pop     rdi
0x140008b64  pop     rsi
0x140008b65  pop     rbp
0x140008b66  retn
```
