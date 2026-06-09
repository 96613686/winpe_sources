# RxCommonLockControl

- ea: `0x140047970`
- end: `0x140047cb2`
- name: `RxCommonLockControl`
- size: `834`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext)`
- caller_count: `0`
- callee_count: `14`
- tags: `broker_com_uri`

## callees

- `0x1400037e0`
- `0x140007ca0`
- `0x140009b80`
- `0x14000f130`
- `0x140012030`
- `0x140016d40`
- `0x140016e20`
- `0x140016fc0`
- `0x140017310`
- `0x14001bea8`
- `0x140025d00`
- `0x140047970`
- `0x140048874`
- `0x140057660`

## import_xrefs

- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x140047b29`
- `ntoskrnl!ExConvertExclusiveToSharedLite` at `0x140047b29`
- `ntoskrnl!FsRtlProcessFileLock` at `0x140047bee`
- `ntoskrnl!FsRtlProcessFileLock` at `0x140047bee`

## string_xrefs

- `0x14007baf0`: `RxCommonLockControl`

## pseudocode

```c
__int64 __fastcall RxCommonLockControl(PRX_CONTEXT RxContext, IRP *a2)
{
  __int16 v3; // si
  __int64 v4; // r9
  PFCB v5; // rbx
  unsigned int v6; // esi
  int v7; // r14d
  NTSTATUS v8; // eax
  ULONG v9; // r8d
  const CHAR *v10; // r9
  NTSTATUS v11; // eax
  ULONG v12; // r8d
  __int64 (__fastcall *v13)(PFCB, LARGE_INTEGER *, ULONG_PTR, _QWORD); // rax
  const CHAR *v15; // [rsp+20h] [rbp-78h]
  ULONG v16; // [rsp+20h] [rbp-78h]
  PCSTR v17; // [rsp+20h] [rbp-78h]
  ULONG v18; // [rsp+28h] [rbp-70h]
  ULONG v19; // [rsp+28h] [rbp-70h]
  char v20; // [rsp+40h] [rbp-58h]
  struct _IO_STACK_LOCATION *CurrentStackLocation; // [rsp+50h] [rbp-48h]
  PFCB Fcb; // [rsp+B0h] [rbp+18h] BYREF
  PVOID *p_EaBuffer; // [rsp+B8h] [rbp+20h] BYREF

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  Fcb = 0;
  p_EaBuffer = 0;
  v3 = RxDecodeFileObject2(CurrentStackLocation->FileObject, &Fcb, &p_EaBuffer);
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
  {
    v5 = Fcb;
  }
  else
  {
    v5 = Fcb;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_qqqL(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        WPP_0973a78508ef3a1691b241bd7e52eaac_Traceguids,
        RxContext,
        p_EaBuffer,
        Fcb,
        *(unsigned __int8 *)(v4 + 1));
  }
  if ( v3 != -5086 )
  {
    v6 = -1073741811;
    v7 = 88;
    goto LABEL_37;
  }
  v8 = _RxAcquireFcb(v5, RxContext, 2u, 0, v15, v18);
  v6 = v8;
  if ( v8 == -1073741739 )
  {
    v6 = RxFsdPostRequest(RxContext);
    v7 = 102;
    goto LABEL_37;
  }
  if ( v8 )
  {
    v7 = 107;
    goto LABEL_37;
  }
  if ( (*((_DWORD *)&v5->1 + 41) & 4) == 0 || LOBYTE(v5->PagingIoResourceFile) )
  {
    if ( _bittest((const signed __int32 *)&v5->1 + 39, 0x16u) )
    {
      LOBYTE(v5->PagingIoResourceFile) = 1;
    }
    else
    {
      _RxReleaseFcb(RxContext, (PMRX_FCB)&v5->Header, v9, v10, v16);
      v11 = _RxAcquireFcb(v5, RxContext, 1u, 0, v17, v19);
      v6 = v11;
      if ( v11 == -1073741739 )
      {
        v6 = RxFsdPostRequest(RxContext);
        v7 = 140;
        goto LABEL_37;
      }
      if ( v11 )
      {
        v7 = 145;
        goto LABEL_37;
      }
      if ( (*((_DWORD *)&v5->1 + 41) & 4) == 0 || LOBYTE(v5->PagingIoResourceFile) )
      {
        if ( !_bittest((const signed __int32 *)&v5->1 + 39, 0x16u) )
          RxDisableLocalBuffering(v5);
        LOBYTE(v5->PagingIoResourceFile) = 1;
      }
      ExConvertExclusiveToSharedLite(v5->Header.Resource);
    }
  }
  v7 = 0;
  v20 = 0;
  p_EaBuffer = &RxContext->Create.EaBuffer;
  *((_DWORD *)&RxContext->9 + 28) |= 0x20u;
  v12 = (unsigned int)CurrentStackLocation;
  if ( CurrentStackLocation->MinorFunction == 1 )
  {
    if ( *(_QWORD *)&v5->NumberOfLinks )
    {
      v13 = *(__int64 (__fastcall **)(PFCB, LARGE_INTEGER *, ULONG_PTR, _QWORD))(*(_QWORD *)&v5->ShareAccessPerSrvOpens.SharedWrite
                                                                               + 152LL);
      if ( v13 )
        v6 = v13(
               v5,
               &CurrentStackLocation->Parameters.Read.ByteOffset,
               CurrentStackLocation->Parameters.WMI.ProviderId,
               CurrentStackLocation->Flags);
    }
    if ( v6 )
    {
      v7 = 203;
      goto LABEL_35;
    }
  }
  else if ( (unsigned int)CurrentStackLocation->MinorFunction - 3 <= 1 )
  {
    *((_WORD *)&RxContext->9 + 61) |= 2u;
  }
  RxContext->LastExecutionThread = KeGetCurrentThread();
  _InterlockedIncrement((volatile signed __int32 *)&RxContext->ReferenceCount);
  v20 = 1;
  v6 = FsRtlProcessFileLock((PFILE_LOCK)&v5->FileLock.LockRequestsInProgress, a2, RxContext);
LABEL_35:
  RxContext->LastExecutionThread = 0;
  _RxReleaseFcb(RxContext, (PMRX_FCB)&v5->Header, v12, v10, v16);
  *((_DWORD *)&RxContext->9 + 28) &= ~0x20u;
  if ( v20 )
    RxDereferenceAndDeleteRxContext_Real(RxContext);
LABEL_37:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_0973a78508ef3a1691b241bd7e52eaac_Traceguids, v6, v7);
  }
  return v6;
}

```

## disassembly

```asm
0x140047970  mov     rax, rsp
0x140047973  mov     [rax+10h], rdx
0x140047977  mov     [rax+8], rcx
0x14004797b  push    rbx
0x14004797c  push    rsi
0x14004797d  push    rdi
0x14004797e  push    r12
0x140047980  push    r13
0x140047982  push    r14
0x140047984  sub     rsp, 68h
0x140047988  mov     rdi, rcx
0x14004798b  mov     r9, [rdx+0B8h]
0x140047992  mov     [rsp+98h+var_48], r9
0x140047997  mov     qword ptr [rax+18h], 0
0x14004799f  mov     qword ptr [rax+20h], 0
0x1400479a7  lea     r8, [rax+20h]
0x1400479ab  lea     rdx, [rax+18h]
0x1400479af  mov     rcx, [r9+30h]
0x1400479b3  call    RxDecodeFileObject2
0x1400479b8  movzx   esi, ax
0x1400479bb  lea     rax, WPP_GLOBAL_Control
0x1400479c2  mov     r10, cs:WPP_GLOBAL_Control
0x1400479c9  mov     r12d, 2
0x1400479cf  cmp     r10, rax
0x1400479d2  jz      short loc_140047A20
0x1400479d4  mov     ecx, [r10+2Ch]
0x1400479d8  test    cl, 4
0x1400479db  jz      short loc_140047A20
0x1400479dd  mov     rbx, [rsp+98h+Fcb]
0x1400479e5  cmp     [r10+29h], r12b
0x1400479e9  jb      short loc_140047A28
0x1400479eb  movzx   eax, byte ptr [r9+1]
0x1400479f0  lea     edx, [r12+8]
0x1400479f5  mov     [rsp+98h+var_68], eax
0x1400479f9  mov     [rsp+98h+var_70], rbx
0x1400479fe  mov     rax, [rsp+98h+arg_18]
0x140047a06  mov     [rsp+98h+var_78], rax
0x140047a0b  mov     r9, rdi
0x140047a0e  lea     r8, WPP_0973a78508ef3a1691b241bd7e52eaac_Traceguids
0x140047a15  mov     rcx, [r10+18h]
0x140047a19  call    WPP_SF_qqqL
0x140047a1e  jmp     short loc_140047A28
0x140047a20  mov     rbx, [rsp+98h+Fcb]
0x140047a28  mov     eax, 0EC22h
0x140047a2d  cmp     si, ax
0x140047a30  jz      short loc_140047A42
0x140047a32  mov     esi, 0C000000Dh
0x140047a37  mov     r14d, 58h ; 'X'
0x140047a3d  jmp     loc_140047C63
0x140047a42  xor     r9d, r9d; LineNumber
0x140047a45  mov     r8d, r12d; Mode
0x140047a48  mov     rdx, rdi; RxContext
0x140047a4b  mov     rcx, rbx; Fcb
0x140047a4e  call    __RxAcquireFcb
0x140047a53  mov     esi, eax
0x140047a55  mov     [rsp+98h+var_54], eax
0x140047a59  mov     r13d, 0C0000055h
0x140047a5f  cmp     eax, r13d
0x140047a62  jnz     short loc_140047A79
0x140047a64  mov     rcx, rdi; RxContext
0x140047a67  call    RxFsdPostRequest
0x140047a6c  mov     esi, eax
0x140047a6e  mov     r14d, 66h ; 'f'
0x140047a74  jmp     loc_140047C63
0x140047a79  test    eax, eax
0x140047a7b  jz      short loc_140047A88
0x140047a7d  mov     r14d, 6Bh ; 'k'
0x140047a83  jmp     loc_140047C63
0x140047a88  mov     eax, [rbx+0A4h]
0x140047a8e  test    al, 4
0x140047a90  jz      short loc_140047A9F
0x140047a92  cmp     byte ptr [rbx+280h], 0
0x140047a99  jz      loc_140047B3E
0x140047a9f  bt      dword ptr [rbx+9Ch], 16h
0x140047aa7  jb      loc_140047B37
0x140047aad  mov     rdx, rbx; MrxFcb
0x140047ab0  mov     rcx, rdi; RxContext
0x140047ab3  call    __RxReleaseFcb
0x140047ab8  xor     r9d, r9d; LineNumber
0x140047abb  lea     r8d, [r9+1]; Mode
0x140047abf  mov     rdx, rdi; RxContext
0x140047ac2  mov     rcx, rbx; Fcb
0x140047ac5  call    __RxAcquireFcb
0x140047aca  mov     esi, eax
0x140047acc  mov     [rsp+98h+var_54], eax
0x140047ad0  cmp     eax, r13d
0x140047ad3  jnz     short loc_140047AEA
0x140047ad5  mov     rcx, rdi; RxContext
0x140047ad8  call    RxFsdPostRequest
0x140047add  mov     esi, eax
0x140047adf  mov     r14d, 8Ch
0x140047ae5  jmp     loc_140047C63
0x140047aea  test    eax, eax
0x140047aec  jz      short loc_140047AF9
0x140047aee  mov     r14d, 91h
0x140047af4  jmp     loc_140047C63
0x140047af9  mov     eax, [rbx+0A4h]
0x140047aff  test    al, 4
0x140047b01  jz      short loc_140047B0C
0x140047b03  cmp     byte ptr [rbx+280h], 0
0x140047b0a  jz      short loc_140047B25
0x140047b0c  bt      dword ptr [rbx+9Ch], 16h
0x140047b14  jb      short loc_140047B1E
0x140047b16  mov     rcx, rbx; Fcb
0x140047b19  call    RxDisableLocalBuffering
0x140047b1e  mov     byte ptr [rbx+280h], 1
0x140047b25  mov     rcx, [rbx+8]; Resource
0x140047b29  call    cs:__imp_ExConvertExclusiveToSharedLite
0x140047b30  nop     dword ptr [rax+rax+00h]
0x140047b35  jmp     short loc_140047B3E
0x140047b37  mov     byte ptr [rbx+280h], 1
0x140047b3e  xor     r14d, r14d
0x140047b41  mov     [rsp+98h+var_58], r14b
0x140047b46  lea     r13, [rdi+200h]
0x140047b4d  mov     [rsp+98h+arg_18], r13
0x140047b55  or      dword ptr [r13+0], 20h
0x140047b5a  mov     r8, [rsp+98h+var_48]
0x140047b5f  movzx   ecx, byte ptr [r8+1]
0x140047b64  sub     ecx, 1
0x140047b67  jz      short loc_140047B7D
0x140047b69  sub     ecx, r12d
0x140047b6c  jz      short loc_140047B73
0x140047b6e  cmp     ecx, 1
0x140047b71  jnz     short loc_140047BC6
0x140047b73  or      [rdi+20Ah], r12w
0x140047b7b  jmp     short loc_140047BC6
0x140047b7d  cmp     qword ptr [rbx+190h], 0
0x140047b85  jz      short loc_140047BB5
0x140047b87  mov     rax, [rbx+188h]
0x140047b8e  mov     rax, [rax+98h]
0x140047b95  test    rax, rax
0x140047b98  jz      short loc_140047BB5
0x140047b9a  movzx   r9d, byte ptr [r8+2]
0x140047b9f  lea     rdx, [r8+18h]
0x140047ba3  mov     r8, [r8+8]
0x140047ba7  mov     rcx, rbx
0x140047baa  call    _guard_dispatch_icall
0x140047baf  mov     esi, eax
0x140047bb1  mov     [rsp+98h+var_54], eax
0x140047bb5  test    esi, esi
0x140047bb7  jz      short loc_140047BC6
0x140047bb9  mov     r14d, 0CBh
0x140047bbf  mov     [rsp+98h+var_50], r14d
0x140047bc4  jmp     short loc_140047C3C
0x140047bc6  mov     rax, gs:188h
0x140047bcf  mov     [rdi+68h], rax
0x140047bd3  lock inc dword ptr [rdi+4]
0x140047bd7  mov     [rsp+98h+var_58], 1
0x140047bdc  lea     rcx, [rbx+218h]; FileLock
0x140047be3  mov     r8, rdi; Context
0x140047be6  mov     rdx, [rsp+98h+Irp]; Irp
0x140047bee  call    cs:__imp_FsRtlProcessFileLock
0x140047bf5  nop     dword ptr [rax+rax+00h]
0x140047bfa  mov     esi, eax
0x140047bfc  mov     [rsp+98h+var_54], eax
0x140047c00  jmp     short loc_140047C3C
0x140047c02  mov     edx, eax; ExceptionCode
0x140047c04  mov     rdi, [rsp+98h+RxContext]
0x140047c0c  mov     rcx, rdi; RxContext
0x140047c0f  call    RxProcessException
0x140047c14  mov     esi, 103h
0x140047c19  mov     [rsp+98h+var_54], esi
0x140047c1d  lea     r14d, [rsi-1]
0x140047c21  mov     [rsp+98h+var_50], r14d
0x140047c26  mov     r12d, 2
0x140047c2c  mov     rbx, [rsp+98h+Fcb]
0x140047c34  mov     r13, [rsp+98h+arg_18]
0x140047c3c  mov     qword ptr [rdi+68h], 0
0x140047c44  mov     rdx, rbx; MrxFcb
0x140047c47  mov     rcx, rdi; RxContext
0x140047c4a  call    __RxReleaseFcb
0x140047c4f  and     dword ptr [r13+0], 0FFFFFFDFh
0x140047c54  cmp     [rsp+98h+var_58], 0
0x140047c59  jz      short loc_140047C63
0x140047c5b  mov     rcx, rdi; RxContext
0x140047c5e  call    RxDereferenceAndDeleteRxContext_Real
0x140047c63  mov     rcx, cs:WPP_GLOBAL_Control
0x140047c6a  lea     rax, WPP_GLOBAL_Control
0x140047c71  cmp     rcx, rax
0x140047c74  jz      short loc_140047CA1
0x140047c76  mov     eax, [rcx+2Ch]
0x140047c79  test    r12b, al
0x140047c7c  jz      short loc_140047CA1
0x140047c7e  cmp     [rcx+29h], r12b
0x140047c82  jb      short loc_140047CA1
0x140047c84  mov     edx, 0Ch
0x140047c89  mov     dword ptr [rsp+98h+var_78], r14d
0x140047c8e  mov     r9d, esi
0x140047c91  lea     r8, WPP_0973a78508ef3a1691b241bd7e52eaac_Traceguids
0x140047c98  mov     rcx, [rcx+18h]
0x140047c9c  call    WPP_SF_Dd
0x140047ca1  mov     eax, esi
0x140047ca3  add     rsp, 68h
0x140047ca7  pop     r14
0x140047ca9  pop     r13
0x140047cab  pop     r12
0x140047cad  pop     rdi
0x140047cae  pop     rsi
0x140047caf  pop     rbx
0x140047cb0  retn
0x14007bab9  push    rbp
0x14007babb  sub     rsp, 40h
0x14007babf  mov     rbp, rdx
0x14007bac2  mov     rdx, rcx; ExceptionPointer
0x14007bac5  mov     rcx, [rbp+0A0h]; RxContext
0x14007bacc  call    RxExceptionFilter
0x14007bad1  nop
0x14007bad2  add     rsp, 40h
0x14007bad6  pop     rbp
0x14007bad7  retn
0x14007bad9  push    rbx
0x14007badb  push    rbp
0x14007badc  push    rdi
0x14007badd  sub     rsp, 40h
0x14007bae1  mov     rbp, rdx
0x14007bae4  movzx   edi, cl
0x14007bae7  test    cl, cl
0x14007bae9  jz      short loc_14007BAFD
0x14007baeb  mov     edx, 10Ch
0x14007baf0  lea     rcx, aRxcommonlockco; "RxCommonLockControl"
0x14007baf7  call    RxLogAbnormalTermination
0x14007bafc  nop
0x14007bafd  mov     rdx, [rbp+0B0h]; MrxFcb
0x14007bb04  mov     rbx, [rbp+0A0h]
0x14007bb0b  mov     rcx, rbx; RxContext
0x14007bb0e  call    __RxReleaseFcb
0x14007bb13  and     dword ptr [rbx+200h], 0FFFFFFDFh
0x14007bb1a  cmp     byte ptr [rbp+40h], 0
0x14007bb1e  jz      short loc_14007BB29
0x14007bb20  mov     rcx, rbx; RxContext
0x14007bb23  call    RxDereferenceAndDeleteRxContext_Real
0x14007bb28  nop
0x14007bb29  mov     eax, edi
0x14007bb2b  test    dil, dil
0x14007bb2e  jz      short loc_14007BB6A
0x14007bb30  lea     rax, WPP_GLOBAL_Control
0x14007bb37  mov     rcx, cs:WPP_GLOBAL_Control
0x14007bb3e  cmp     rcx, rax
0x14007bb41  jz      short loc_14007BB6A
0x14007bb43  mov     eax, [rcx+2Ch]
0x14007bb46  test    al, 2
0x14007bb48  jz      short loc_14007BB6A
0x14007bb4a  cmp     byte ptr [rcx+29h], 4
0x14007bb4e  jb      short loc_14007BB6A
0x14007bb50  mov     edx, 0Bh
0x14007bb55  mov     r9d, [rbp+44h]
0x14007bb59  lea     r8, WPP_0973a78508ef3a1691b241bd7e52eaac_Traceguids
0x14007bb60  mov     rcx, [rcx+18h]
0x14007bb64  call    WPP_SF_d
0x14007bb69  nop
0x14007bb6a  add     rsp, 40h
0x14007bb6e  pop     rdi
0x14007bb6f  pop     rbp
0x14007bb70  pop     rbx
0x14007bb71  retn
```
