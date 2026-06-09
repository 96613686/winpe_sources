# SmbCeDataReadyInd

- ea: `0x14000b524`
- end: `0x14000b6e6`
- name: `SmbCeDataReadyInd`
- size: `450`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1400043a0`

## callees

- `0x1400054b0`
- `0x14000b524`
- `0x14000dfa8`
- `0x14000ebd8`
- `0x140012014`
- `0x1400126a4`
- `0x14001276c`
- `0x140016640`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000b5a3`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000b5a3`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b546`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000b546`
- `ntoskrnl!DbgPrint` at `0x14000b645`
- `ntoskrnl!DbgPrint` at `0x14000b645`
- `mrxsmb!MRxSmbLegacyPerfCtrs` at `0x14000b6b9`

## string_xrefs

- `0x14000b63e`: `SS mismatch on data ready ind, tear down connection\n`

## pseudocode

```c
__int64 __fastcall SmbCeDataReadyInd(__int64 a1, __int64 *a2, unsigned int a3, int a4)
{
  unsigned __int64 v5; // rbp
  __int64 v8; // rbx
  KIRQL v9; // al
  __int64 v10; // r8
  __int64 v11; // r10
  bool v12; // zf
  __int64 i; // rax
  __int64 v14; // rdx
  char v15; // al
  __int64 v16; // rcx

  v5 = a3;
  v8 = 0;
  v9 = KeAcquireSpinLockRaiseToDpc(&s_SmbCeDbSpinLock);
  v10 = 0;
  s_SmbCeDbSpinLockSavedIrql = v9;
  v11 = *(_QWORD *)(a1 + 368);
  v12 = v11 == a1 + 368;
  for ( i = v11 - 32; ; i = v16 - 32 )
  {
    if ( !v12 )
      v10 = i;
    if ( !v10 )
      break;
    if ( *(_DWORD *)(v10 + 48) == 1 && *(__int64 **)(v10 + 72) == a2 )
    {
      v8 = *(_QWORD *)(v10 + 56);
      *(_QWORD *)(v10 + 72) = 0;
      break;
    }
    v16 = *(_QWORD *)(v10 + 32);
    v10 = 0;
    v12 = v16 == a1 + 368;
  }
  KeReleaseSpinLock(&s_SmbCeDbSpinLock, s_SmbCeDbSpinLockSavedIrql);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_96809d50ffaa30ffc961a4216fa88776_Traceguids, v8);
  if ( v8 )
  {
    if ( !a4 )
    {
      if ( (*(_BYTE *)(a1 + 672) & 8) == 0
        || (!*(_BYTE *)(v8 + 255)
          ? (v15 = SmbCheckSecuritySignatureWithMdl(v8, a1 + 400, v5, (__int64)a2))
          : (v15 = SmbCheckSecuritySignaturePartial(v8, v14, v5, a2)),
            v15) )
      {
        _InterlockedAdd64(
          (volatile signed __int64 *)(MRxSmbLegacyPerfCtrs + ((unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 8)),
          v5);
        (*(void (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)(v8 + 152) + 16LL))(v8, a2, (unsigned int)v5);
        goto LABEL_24;
      }
      DbgPrint("SS mismatch on data ready ind, tear down connection\n");
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_96809d50ffaa30ffc961a4216fa88776_Traceguids);
      }
      a4 = -1073741629;
      SmbCeTransportDisconnectIndicated(*(PVOID *)(v8 + 80));
    }
    *(_DWORD *)(v8 + 48) = a4;
    *(_DWORD *)(v8 + 40) = a4;
LABEL_24:
    SmbCeDecrementPendingOperationsAndFinalize((PVOID)v8);
  }
  return 0;
}

```

## disassembly

```asm
0x14000b524  push    rbx
0x14000b526  push    rbp
0x14000b527  push    rsi
0x14000b528  push    rdi
0x14000b529  push    r14
0x14000b52b  push    r15
0x14000b52d  sub     rsp, 28h
0x14000b531  mov     r14, rcx
0x14000b534  mov     ebp, r8d
0x14000b537  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x14000b53e  mov     edi, r9d
0x14000b541  mov     rsi, rdx
0x14000b544  xor     ebx, ebx
0x14000b546  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000b54d  nop     dword ptr [rax+rax+00h]
0x14000b552  lea     rdx, [r14+170h]
0x14000b559  xor     r8d, r8d
0x14000b55c  mov     cs:s_SmbCeDbSpinLockSavedIrql, al
0x14000b562  mov     r10, [rdx]
0x14000b565  cmp     r10, rdx
0x14000b568  lea     rax, [r10-20h]
0x14000b56c  cmovnz  r8, rax
0x14000b570  test    r8, r8
0x14000b573  jz      short loc_14000B596
0x14000b575  cmp     dword ptr [r8+30h], 1
0x14000b57a  jnz     loc_14000B61B
0x14000b580  cmp     [r8+48h], rsi
0x14000b584  jnz     loc_14000B61B
0x14000b58a  mov     rbx, [r8+38h]
0x14000b58e  mov     qword ptr [r8+48h], 0
0x14000b596  mov     dl, cs:s_SmbCeDbSpinLockSavedIrql; NewIrql
0x14000b59c  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x14000b5a3  call    cs:__imp_KeReleaseSpinLock
0x14000b5aa  nop     dword ptr [rax+rax+00h]
0x14000b5af  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000b5b6  lea     r15, WPP_GLOBAL_Control
0x14000b5bd  cmp     rcx, r15
0x14000b5c0  jz      short loc_14000B5E3
0x14000b5c2  test    dword ptr [rcx+2Ch], 400h
0x14000b5c9  jz      short loc_14000B5E3
0x14000b5cb  mov     rcx, [rcx+18h]
0x14000b5cf  lea     r8, WPP_96809d50ffaa30ffc961a4216fa88776_Traceguids
0x14000b5d6  mov     edx, 12h
0x14000b5db  mov     r9, rbx
0x14000b5de  call    WPP_SF_q
0x14000b5e3  test    rbx, rbx
0x14000b5e6  jz      loc_14000B69C
0x14000b5ec  test    edi, edi
0x14000b5ee  jnz     loc_14000B689
0x14000b5f4  test    byte ptr [r14+2A0h], 8
0x14000b5fc  jz      loc_14000B6AC
0x14000b602  mov     r9, rsi
0x14000b605  mov     r8d, ebp
0x14000b608  mov     rcx, rbx
0x14000b60b  cmp     [rbx+0FFh], dil
0x14000b612  jz      short loc_14000B62E
0x14000b614  call    SmbCheckSecuritySignaturePartial
0x14000b619  jmp     short loc_14000B63A
0x14000b61b  mov     rcx, [r8+20h]
0x14000b61f  xor     r8d, r8d
0x14000b622  cmp     rcx, rdx
0x14000b625  lea     rax, [rcx-20h]
0x14000b629  jmp     loc_14000B56C
0x14000b62e  lea     rdx, [r14+190h]
0x14000b635  call    SmbCheckSecuritySignatureWithMdl
0x14000b63a  test    al, al
0x14000b63c  jnz     short loc_14000B6AC
0x14000b63e  lea     rcx, aSsMismatchOnDa; "SS mismatch on data ready ind, tear dow"...
0x14000b645  call    cs:__imp_DbgPrint
0x14000b64c  nop     dword ptr [rax+rax+00h]
0x14000b651  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14000b658  cmp     rcx, r15
0x14000b65b  jz      short loc_14000B67B
0x14000b65d  test    dword ptr [rcx+2Ch], 200h
0x14000b664  jz      short loc_14000B67B
0x14000b666  mov     rcx, [rcx+18h]
0x14000b66a  lea     r8, WPP_96809d50ffaa30ffc961a4216fa88776_Traceguids
0x14000b671  mov     edx, 13h
0x14000b676  call    WPP_SF_
0x14000b67b  mov     rcx, [rbx+50h]; pContext
0x14000b67f  mov     edi, 0C00000C3h
0x14000b684  call    SmbCeTransportDisconnectIndicated
0x14000b689  mov     [rbx+30h], edi
0x14000b68c  mov     [rbx+28h], edi
0x14000b68f  mov     edx, 4
0x14000b694  mov     rcx, rbx; pContext
0x14000b697  call    SmbCeDecrementPendingOperationsAndFinalize
0x14000b69c  xor     eax, eax
0x14000b69e  add     rsp, 28h
0x14000b6a2  pop     r15
0x14000b6a4  pop     r14
0x14000b6a6  pop     rdi
0x14000b6a7  pop     rsi
0x14000b6a8  pop     rbp
0x14000b6a9  pop     rbx
0x14000b6aa  retn
0x14000b6ac  mov     eax, gs:1A4h
0x14000b6b4  mov     rdx, rbp
0x14000b6b7  mov     ecx, eax
0x14000b6b9  mov     rax, cs:__imp_MRxSmbLegacyPerfCtrs
0x14000b6c0  shl     rcx, 8
0x14000b6c4  add     rcx, [rax]
0x14000b6c7  lock add [rcx], rdx
0x14000b6cb  mov     rax, [rbx+98h]
0x14000b6d2  mov     r8d, ebp
0x14000b6d5  mov     rdx, rsi
0x14000b6d8  mov     rcx, rbx
0x14000b6db  mov     rax, [rax+10h]
0x14000b6df  call    _guard_dispatch_icall
0x14000b6e4  jmp     short loc_14000B68F
```
