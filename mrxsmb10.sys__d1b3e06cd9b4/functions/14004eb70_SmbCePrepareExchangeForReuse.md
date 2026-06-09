# SmbCePrepareExchangeForReuse

- ea: `0x14004eb70`
- end: `0x14004ee55`
- name: `SmbCePrepareExchangeForReuse`
- size: `741`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400099a0`
- `0x14000bfc0`
- `0x140029be0`

## callees

- `0x140001e40`
- `0x140002470`
- `0x140003e20`
- `0x140004030`
- `0x1400054b0`
- `0x140005b20`
- `0x140009340`
- `0x140009e40`
- `0x14000dc44`
- `0x14000dfa8`
- `0x140016640`
- `0x140042d00`
- `0x14004eb70`
- `0x14004ee60`
- `0x140053db0`

## string_xrefs

- `0x14004ed23`: `SmbCeUpdateSessionEntryAndVNetRootContext`
- `0x14004ed8c`: `SmbCeUpdateSessionEntryAndVNetRootContext`
- `0x14004eda8`: `SmbCeUpdateSessionEntryAndVNetRootContext`

## pseudocode

```c
__int64 __fastcall SmbCePrepareExchangeForReuse(__int64 a1)
{
  int v2; // eax
  char *v3; // rbp
  char *v4; // rdi
  __int64 v5; // rsi
  __int64 v6; // r14
  __int64 v8; // rbx
  signed __int32 v9; // eax
  int v10; // ecx
  signed __int32 v11; // eax
  __int64 v12; // rax
  int v13; // eax
  char v14; // [rsp+50h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids);
  v2 = *(_DWORD *)(a1 + 72);
  if ( (v2 & 0x8000) == 0 )
  {
    v3 = *(char **)(a1 + 80);
    v4 = *(char **)(a1 + 88);
    if ( v3 )
    {
      if ( (v2 & 1) != 0 )
        SmbCeDissociateMidFromExchange(v3, a1);
      SmbCePurgeBuffersAssociatedWithExchange(v3, a1);
      SmbCeUninitializeExchangeTransport(a1);
      v2 = *(_DWORD *)(a1 + 72);
    }
    v5 = *(_QWORD *)(a1 + 88);
    if ( v5 )
      v6 = *(_QWORD *)(v5 + 96);
    else
      v6 = 0;
    if ( (v2 & 0x100) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids);
      }
      MRxSmbTrackRefCount(v6, "SmbCeUpdateSessionEntryAndVNetRootContext", 2787);
      _InterlockedIncrement((volatile signed __int32 *)(v6 + 8));
      SmbCeCompleteSessionEntryInitialization(v6, *(_DWORD *)(a1 + 248), *(_BYTE *)(a1 + 254));
      *(_DWORD *)(a1 + 72) &= ~0x100u;
      v2 = *(_DWORD *)(a1 + 72);
    }
    if ( (v2 & 0x200) != 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 52, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids);
      }
      MRxSmbTrackRefCount(v5, "SmbCeUpdateSessionEntryAndVNetRootContext", 2803);
      SmbReferenceRecord(v5 + 136, "SmbCeUpdateSessionEntryAndVNetRootContext", 2803);
      _InterlockedIncrement((volatile signed __int32 *)(v5 + 8));
      SmbCeCompleteVNetRootContextInitialization((PVOID)v5);
      *(_DWORD *)(a1 + 72) &= ~0x200u;
    }
    if ( v4 )
    {
      MRxSmbTrackDerefCount(v4, "SmbCePrepareExchangeForReuse", 2866);
      SmbReferenceRecord(v4 + 136, "SmbCePrepareExchangeForReuse", 2866);
      SmbCepDereferenceVNetRootContext(v4);
    }
    else if ( v3 )
    {
      MRxSmbTrackDerefCount(v3, "SmbCePrepareExchangeForReuse", 2869);
      SmbReferenceRecord(v3 + 792, "SmbCePrepareExchangeForReuse", 2869);
      SmbCepDereferenceServerEntry(v3);
    }
  }
  if ( *(int *)(a1 + 72) < 0 )
  {
    v8 = *(_QWORD *)(a1 + 160);
    v9 = _InterlockedExchangeAdd((volatile signed __int32 *)(v8 + 168), 0xFFFFFFFF);
    v10 = *(_DWORD *)(v8 + 72);
    v11 = v9 - 1;
    if ( (v10 & 0x40000000) != 0 && !v11 )
    {
      v14 = 0;
      v12 = *(_QWORD *)(v8 + 152);
      *(_DWORD *)(v8 + 72) = v10 & 0xBFFFFFFF;
      v13 = (*(__int64 (__fastcall **)(__int64, char *))(v12 + 40))(v8, &v14);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 54, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids, v8, v13);
      }
    }
    SmbCeDecrementPendingOperationsAndFinalize((PVOID)v8);
  }
  return 0;
}

```

## disassembly

```asm
0x14004eb70  push    rbx
0x14004eb72  push    r15
0x14004eb74  sub     rsp, 38h
0x14004eb78  mov     rbx, rcx
0x14004eb7b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004eb82  lea     r15, WPP_GLOBAL_Control
0x14004eb89  cmp     rcx, r15
0x14004eb8c  jnz     loc_14004ECBC
0x14004eb92  mov     eax, [rbx+48h]
0x14004eb95  bt      eax, 0Fh
0x14004eb99  jb      loc_14004EC3C
0x14004eb9f  mov     [rsp+48h+arg_8], rbp
0x14004eba4  mov     rbp, [rbx+50h]
0x14004eba8  mov     [rsp+48h+arg_10], rsi
0x14004ebad  mov     [rsp+48h+arg_18], rdi
0x14004ebb2  mov     rdi, [rbx+58h]
0x14004ebb6  test    rbp, rbp
0x14004ebb9  jnz     loc_14004EC51
0x14004ebbf  mov     rsi, [rbx+58h]
0x14004ebc3  mov     [rsp+48h+var_18], r14
0x14004ebc8  test    rsi, rsi
0x14004ebcb  jz      loc_14004EC74
0x14004ebd1  mov     r14, [rsi+60h]
0x14004ebd5  bt      eax, 8
0x14004ebd9  jb      loc_14004ECF3
0x14004ebdf  mov     r14, [rsp+48h+var_18]
0x14004ebe4  bt      eax, 9
0x14004ebe8  jb      loc_14004ED5C
0x14004ebee  mov     rsi, [rsp+48h+arg_10]
0x14004ebf3  test    rdi, rdi
0x14004ebf6  jz      loc_14004EC7C
0x14004ebfc  mov     r8d, 0B32h
0x14004ec02  lea     rdx, aSmbceprepareex; "SmbCePrepareExchangeForReuse"
0x14004ec09  mov     rcx, rdi
0x14004ec0c  call    MRxSmbTrackDerefCount
0x14004ec11  lea     rcx, [rdi+88h]
0x14004ec18  mov     r8d, 0B32h
0x14004ec1e  lea     rdx, aSmbceprepareex; "SmbCePrepareExchangeForReuse"
0x14004ec25  call    SmbReferenceRecord
0x14004ec2a  mov     rcx, rdi; P
0x14004ec2d  call    SmbCepDereferenceVNetRootContext
0x14004ec32  mov     rbp, [rsp+48h+arg_8]
0x14004ec37  mov     rdi, [rsp+48h+arg_18]
0x14004ec3c  cmp     dword ptr [rbx+48h], 0
0x14004ec40  jl      loc_14004EDCC
0x14004ec46  xor     eax, eax
0x14004ec48  add     rsp, 38h
0x14004ec4c  pop     r15
0x14004ec4e  pop     rbx
0x14004ec4f  retn
0x14004ec51  test    al, 1
0x14004ec53  jnz     loc_14004ECE3
0x14004ec59  mov     rdx, rbx
0x14004ec5c  mov     rcx, rbp
0x14004ec5f  call    SmbCePurgeBuffersAssociatedWithExchange
0x14004ec64  mov     rcx, rbx
0x14004ec67  call    SmbCeUninitializeExchangeTransport
0x14004ec6c  mov     eax, [rbx+48h]
0x14004ec6f  jmp     loc_14004EBBF
0x14004ec74  xor     r14d, r14d
0x14004ec77  jmp     loc_14004EBD5
0x14004ec7c  test    rbp, rbp
0x14004ec7f  jz      short loc_14004EC32
0x14004ec81  mov     r8d, 0B35h
0x14004ec87  lea     rdx, aSmbceprepareex; "SmbCePrepareExchangeForReuse"
0x14004ec8e  mov     rcx, rbp
0x14004ec91  call    MRxSmbTrackDerefCount
0x14004ec96  lea     rcx, [rbp+318h]
0x14004ec9d  mov     r8d, 0B35h
0x14004eca3  lea     rdx, aSmbceprepareex; "SmbCePrepareExchangeForReuse"
0x14004ecaa  call    SmbReferenceRecord
0x14004ecaf  mov     rcx, rbp; pContext
0x14004ecb2  call    SmbCepDereferenceServerEntry
0x14004ecb7  jmp     loc_14004EC32
0x14004ecbc  test    dword ptr [rcx+2Ch], 400h
0x14004ecc3  jz      loc_14004EB92
0x14004ecc9  mov     rcx, [rcx+18h]
0x14004eccd  lea     r8, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids
0x14004ecd4  mov     edx, 35h ; '5'
0x14004ecd9  call    WPP_SF_
0x14004ecde  jmp     loc_14004EB92
0x14004ece3  mov     rdx, rbx
0x14004ece6  mov     rcx, rbp
0x14004ece9  call    SmbCeDissociateMidFromExchange
0x14004ecee  jmp     loc_14004EC59
0x14004ecf3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004ecfa  cmp     rcx, r15
0x14004ecfd  jz      short loc_14004ED1D
0x14004ecff  test    dword ptr [rcx+2Ch], 400h
0x14004ed06  jz      short loc_14004ED1D
0x14004ed08  mov     rcx, [rcx+18h]
0x14004ed0c  lea     r8, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids
0x14004ed13  mov     edx, 33h ; '3'
0x14004ed18  call    WPP_SF_
0x14004ed1d  mov     r8d, 0AE3h
0x14004ed23  lea     rdx, aSmbceupdateses; "SmbCeUpdateSessionEntryAndVNetRootConte"...
0x14004ed2a  mov     rcx, r14
0x14004ed2d  call    MRxSmbTrackRefCount
0x14004ed32  lock inc dword ptr [r14+8]
0x14004ed37  movzx   r8d, byte ptr [rbx+0FEh]
0x14004ed3f  mov     rcx, r14
0x14004ed42  mov     edx, [rbx+0F8h]
0x14004ed48  call    SmbCeCompleteSessionEntryInitialization
0x14004ed4d  and     dword ptr [rbx+48h], 0FFFFFEFFh
0x14004ed54  mov     eax, [rbx+48h]
0x14004ed57  jmp     loc_14004EBDF
0x14004ed5c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004ed63  cmp     rcx, r15
0x14004ed66  jz      short loc_14004ED86
0x14004ed68  test    dword ptr [rcx+2Ch], 400h
0x14004ed6f  jz      short loc_14004ED86
0x14004ed71  mov     rcx, [rcx+18h]
0x14004ed75  lea     r8, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids
0x14004ed7c  mov     edx, 34h ; '4'
0x14004ed81  call    WPP_SF_
0x14004ed86  mov     r8d, 0AF3h
0x14004ed8c  lea     rdx, aSmbceupdateses; "SmbCeUpdateSessionEntryAndVNetRootConte"...
0x14004ed93  mov     rcx, rsi
0x14004ed96  call    MRxSmbTrackRefCount
0x14004ed9b  lea     rcx, [rsi+88h]
0x14004eda2  mov     r8d, 0AF3h
0x14004eda8  lea     rdx, aSmbceupdateses; "SmbCeUpdateSessionEntryAndVNetRootConte"...
0x14004edaf  call    SmbReferenceRecord
0x14004edb4  lock inc dword ptr [rsi+8]
0x14004edb8  mov     rcx, rsi; P
0x14004edbb  call    SmbCeCompleteVNetRootContextInitialization
0x14004edc0  and     dword ptr [rbx+48h], 0FFFFFDFFh
0x14004edc7  jmp     loc_14004EBEE
0x14004edcc  mov     rbx, [rbx+0A0h]
0x14004edd3  mov     eax, 0FFFFFFFFh
0x14004edd8  lock xadd [rbx+0A8h], eax
0x14004ede0  mov     ecx, [rbx+48h]
0x14004ede3  dec     eax
0x14004ede5  bt      ecx, 1Eh
0x14004ede9  jnb     short loc_14004EE43
0x14004edeb  test    eax, eax
0x14004eded  jnz     short loc_14004EE43
0x14004edef  mov     [rsp+48h+arg_0], al
0x14004edf3  lea     rdx, [rsp+48h+arg_0]
0x14004edf8  mov     rax, [rbx+98h]
0x14004edff  btr     ecx, 1Eh
0x14004ee03  mov     [rbx+48h], ecx
0x14004ee06  mov     rcx, rbx
0x14004ee09  mov     rax, [rax+28h]
0x14004ee0d  call    _guard_dispatch_icall
0x14004ee12  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004ee19  cmp     rcx, r15
0x14004ee1c  jz      short loc_14004EE43
0x14004ee1e  test    dword ptr [rcx+2Ch], 400h
0x14004ee25  jz      short loc_14004EE43
0x14004ee27  mov     rcx, [rcx+18h]
0x14004ee2b  lea     r8, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids
0x14004ee32  mov     edx, 36h ; '6'
0x14004ee37  mov     [rsp+48h+var_28], eax
0x14004ee3b  mov     r9, rbx
0x14004ee3e  call    WPP_SF_qD
0x14004ee43  mov     edx, 1
0x14004ee48  mov     rcx, rbx; pContext
0x14004ee4b  call    SmbCeDecrementPendingOperationsAndFinalize
0x14004ee50  jmp     loc_14004EC46
```
