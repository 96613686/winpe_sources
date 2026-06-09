# RxFinalizeNetFcb

- ea: `0x140059910`
- end: `0x140059cfb`
- name: `RxFinalizeNetFcb`
- size: `1003`
- prototype: `BOOLEAN __stdcall(PFCB ThisFcb, BOOLEAN RecursiveFinalize, BOOLEAN ForceFinalize, LONG ReferenceCount)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x14000f180`
- `0x140014d10`
- `0x140016e70`
- `0x140025d00`
- `0x140058f00`
- `0x140059660`
- `0x140059910`
- `0x140059d10`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x140059b4a`
- `ntoskrnl!ExDeleteResourceLite` at `0x140059b5a`
- `ntoskrnl!ExDeleteResourceLite` at `0x140059b4a`
- `ntoskrnl!ExDeleteResourceLite` at `0x140059b5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140059c8e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140059c8e`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400599cb`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400599cb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400599f3`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400599f3`
- `ntoskrnl!FsRtlUninitializeFileLock` at `0x140059bd7`
- `ntoskrnl!FsRtlUninitializeFileLock` at `0x140059bd7`
- `ntoskrnl!FsRtlUninitializeOplock` at `0x140059b6a`
- `ntoskrnl!FsRtlUninitializeOplock` at `0x140059b6a`
- `ntoskrnl!RtlRbRemoveNode` at `0x140059aa4`
- `ntoskrnl!RtlRbRemoveNode` at `0x140059aa4`
- `ntoskrnl!KeBugCheckEx` at `0x140059bc3`
- `ntoskrnl!KeBugCheckEx` at `0x140059bc3`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
BOOLEAN __stdcall RxFinalizeNetFcb(PFCB ThisFcb, BOOLEAN RecursiveFinalize, BOOLEAN ForceFinalize, LONG ReferenceCount)
{
  PMINIRDR_DISPATCH *p_MRxDispatch; // rsi
  __int64 v6; // rdi
  _QWORD *i; // rdx
  __int64 v8; // r9
  __int64 Deleters; // r8
  unsigned __int64 v10; // r8
  int j; // ebp
  __int64 *v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  BOOLEAN result; // al
  unsigned __int64 MRxFastIoDispatch; // r8
  _QWORD *v18; // r9
  PMINIRDR_DISPATCH *v19; // rax
  PMINIRDR_DISPATCH **v20; // rcx

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qZ(
      WPP_GLOBAL_Control->AttachedDevice,
      62,
      (unsigned int)WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids,
      (_DWORD)ThisFcb,
      (__int64)&ThisFcb->InternalFobx);
  }
  if ( LODWORD(ThisFcb->ScavengerFinalizationList.Flink)
    || LODWORD(ThisFcb->NonPaged)
    || *((_DWORD *)&ThisFcb->1 + 38) > 1u
    || *((_DWORD *)&ThisFcb->1 + 38) == 1 && (*((_DWORD *)&ThisFcb->1 + 39) & 0x10000000) != 0 )
  {
    KeBugCheckEx(
      0x27u,
      0xFCB0151D,
      (ULONG_PTR)ThisFcb,
      SLODWORD(ThisFcb->ScavengerFinalizationList.Flink),
      *((unsigned int *)&ThisFcb->1 + 38));
  }
  if ( !LOBYTE(ThisFcb->ShareAccessPerSrvOpens.Readers) )
  {
    if ( ThisFcb->Header.NodeTypeCode == -5086 )
      FsRtlUninitializeFileLock((PFILE_LOCK)&ThisFcb->FileLock.LockRequestsInProgress);
    if ( (*((_DWORD *)&ThisFcb->1 + 39) & 0x10000000) == 0 )
    {
      p_MRxDispatch = &ThisFcb->MRxDispatch;
      v6 = *((_QWORD *)&ThisFcb->1 + 15);
      ExAcquirePushLockExclusiveEx(v6 + 320, 0);
      for ( i = *(_QWORD **)(v6 + 328); i != (_QWORD *)(v6 + 328); i = (_QWORD *)*i )
      {
        if ( (PMINIRDR_DISPATCH *)i[5] == p_MRxDispatch )
        {
          MRxFastIoDispatch = (unsigned __int64)ThisFcb->MRxFastIoDispatch;
          if ( MRxFastIoDispatch )
          {
            v18 = *(_QWORD **)MRxFastIoDispatch;
            if ( *(_QWORD *)MRxFastIoDispatch )
            {
              do
              {
                MRxFastIoDispatch = (unsigned __int64)v18;
                v18 = (_QWORD *)*v18;
              }
              while ( v18 );
            }
          }
          else
          {
            v19 = &ThisFcb->MRxDispatch;
            for ( MRxFastIoDispatch = (unsigned __int64)ThisFcb->InternalSrvOpen & 0xFFFFFFFFFFFFFFFCuLL;
                  MRxFastIoDispatch;
                  MRxFastIoDispatch = *(_QWORD *)(MRxFastIoDispatch + 16) & 0xFFFFFFFFFFFFFFFCuLL )
            {
              if ( *(PMINIRDR_DISPATCH **)MRxFastIoDispatch == v19 )
                break;
              v19 = (PMINIRDR_DISPATCH *)MRxFastIoDispatch;
            }
          }
          i[5] = MRxFastIoDispatch;
        }
      }
      ExReleasePushLockExclusiveEx(v6 + 320, 0);
      v8 = *(_QWORD *)(v6 + 464);
      if ( v8 )
      {
        Deleters = ThisFcb->ShareAccess.Deleters;
        v10 = ((((unsigned __int64)(((unsigned __int16)Deleters
                                   ^ (unsigned __int16)((unsigned __int64)(unsigned int)Deleters >> 6))
                                  & 0x3F00) >> 6)
              ^ ThisFcb->ShareAccess.Deleters
              & 0xFC) >> 2)
            ^ ((unsigned __int8)((Deleters ^ ((unsigned __int64)(unsigned int)Deleters >> 6)) >> 20)
             ^ Deleters
             & 3)
            & 0x3F;
        if ( (PMINIRDR_DISPATCH *)(*(_QWORD *)(v8 + 8 * v10) & 0xFFFFFFFFFFFFFFFEuLL) == p_MRxDispatch )
          *(_QWORD *)(v8 + 8 * v10) = 0;
        for ( j = 0; j < 64; ++j )
        {
          if ( !LOWORD(ThisFcb->ShareAccess.Writers) )
            break;
          v12 = (__int64 *)(*(_QWORD *)(v6 + 464) + 8LL * (unsigned int)j);
          v13 = *v12;
          if ( *v12 )
          {
            if ( (v13 & 1) != 0 )
            {
              v20 = (PMINIRDR_DISPATCH **)(v13 & 0xFFFFFFFFFFFFFFFEuLL);
              if ( *v20 == p_MRxDispatch )
              {
                *v12 = 0;
                ExFreePoolWithTag(v20, 0);
                --LOWORD(ThisFcb->ShareAccess.Writers);
              }
            }
          }
        }
      }
      RtlRbRemoveNode(v6 + 448, &ThisFcb->MRxDispatch);
      *(_OWORD *)p_MRxDispatch = 0;
      ThisFcb->InternalSrvOpen = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qZ(
          WPP_GLOBAL_Control->AttachedDevice,
          14,
          (unsigned int)WPP_518c92af35303f374eeedacc3593600d_Traceguids,
          (_DWORD)ThisFcb,
          (__int64)&ThisFcb->InternalFobx);
      }
      --*(_DWORD *)(v6 + 312);
      _InterlockedIncrement((volatile signed __int32 *)(v6 + 300));
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 63, WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids, ThisFcb);
    }
    LOBYTE(ThisFcb->ShareAccessPerSrvOpens.Readers) = 1;
  }
  RxCloseFcbForTurboIo(ThisFcb, RecursiveFinalize, ForceFinalize, *(_QWORD *)&ReferenceCount);
  RxDeregisterFcbWithBufferingManager(ThisFcb);
  v14 = *(_QWORD *)&ThisFcb->ShareAccessPerSrvOpens.SharedWrite;
  WORD1(ThisFcb->PrivateAlreadyPrefixedName.Buffer) = 0;
  if ( v14 )
    (*(void (__fastcall **)(_QWORD, PFCB))(v14 + 128))(0, ThisFcb);
  ExDeleteResourceLite(ThisFcb->Header.Resource);
  ExDeleteResourceLite(ThisFcb->Header.PagingIoResource);
  FsRtlUninitializeOplock((POPLOCK)&ThisFcb->pNetRoot);
  v15 = *((_QWORD *)&ThisFcb->1 + 15);
  if ( v15 )
  {
    _InterlockedDecrement((volatile signed __int32 *)(v15 + 60));
    RxDereference(*((PVOID *)&ThisFcb->1 + 15), LHS_LockNotHeld);
    *((_QWORD *)&ThisFcb->1 + 15) = 0;
  }
  RxFreeFcbObject(ThisFcb);
  return result;
}

```

## disassembly

```asm
0x140059910  push    rbx
0x140059912  push    r14
0x140059914  sub     rsp, 38h
0x140059918  mov     rbx, rcx
0x14005991b  mov     rcx, cs:WPP_GLOBAL_Control
0x140059922  lea     r14, WPP_GLOBAL_Control
0x140059929  cmp     rcx, r14
0x14005992c  jz      short loc_14005993B
0x14005992e  test    dword ptr [rcx+2Ch], 100h
0x140059935  jnz     loc_140059C40
0x14005993b  movsxd  rcx, dword ptr [rbx+0C0h]
0x140059942  test    ecx, ecx
0x140059944  jnz     loc_140059BA8
0x14005994a  cmp     [rbx+0B8h], ecx
0x140059950  jnz     loc_140059BA8
0x140059956  cmp     dword ptr [rbx+98h], 1
0x14005995d  ja      loc_140059BA8
0x140059963  jnz     short loc_140059975
0x140059965  test    dword ptr [rbx+9Ch], 10000000h
0x14005996f  jnz     loc_140059BA8
0x140059975  mov     [rsp+48h+var_18], r15
0x14005997a  xor     r15d, r15d
0x14005997d  cmp     [rbx+178h], r15b
0x140059984  jnz     loc_140059B11
0x14005998a  mov     eax, 0EC22h
0x14005998f  cmp     [rbx], ax
0x140059992  jz      loc_140059BD0
0x140059998  test    dword ptr [rbx+9Ch], 10000000h
0x1400599a2  jnz     loc_140059AF1
0x1400599a8  mov     [rsp+48h+arg_0], rbp
0x1400599ad  xor     edx, edx
0x1400599af  mov     [rsp+48h+arg_8], rsi
0x1400599b4  lea     rsi, [rbx+138h]
0x1400599bb  mov     [rsp+48h+arg_10], rdi
0x1400599c0  mov     rdi, [rbx+78h]
0x1400599c4  lea     rcx, [rdi+140h]
0x1400599cb  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400599d2  nop     dword ptr [rax+rax+00h]
0x1400599d7  lea     rcx, [rdi+148h]
0x1400599de  mov     rdx, [rcx]
0x1400599e1  cmp     rdx, rcx
0x1400599e4  jnz     loc_140059BF8
0x1400599ea  xor     edx, edx
0x1400599ec  lea     rcx, [rdi+140h]
0x1400599f3  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400599fa  nop     dword ptr [rax+rax+00h]
0x1400599ff  mov     r9, [rdi+1D0h]
0x140059a06  test    r9, r9
0x140059a09  jz      loc_140059A9A
0x140059a0f  mov     r8d, [rsi+2Ch]
0x140059a13  mov     ecx, r8d
0x140059a16  mov     [rsp+48h+arg_18], r12
0x140059a1b  mov     edx, r8d
0x140059a1e  and     ecx, 0FCh
0x140059a24  shr     rdx, 6
0x140059a28  mov     rax, rdx
0x140059a2b  xor     rdx, r8
0x140059a2e  xor     rax, r8
0x140059a31  shr     rdx, 14h
0x140059a35  and     eax, 3F00h
0x140059a3a  and     r8d, 3
0x140059a3e  shr     rax, 6
0x140059a42  xor     r8, rdx
0x140059a45  xor     rcx, rax
0x140059a48  and     r8d, 3Fh
0x140059a4c  shr     rcx, 2
0x140059a50  xor     r8, rcx
0x140059a53  mov     rax, [r9+r8*8]
0x140059a57  and     rax, 0FFFFFFFFFFFFFFFEh
0x140059a5b  cmp     rax, rsi
0x140059a5e  jnz     short loc_140059A64
0x140059a60  mov     [r9+r8*8], r15
0x140059a64  mov     ebp, r15d
0x140059a67  mov     r12d, 0FFFFh
0x140059a6d  cmp     [rsi+28h], r15w
0x140059a72  jbe     short loc_140059A95
0x140059a74  mov     rax, [rdi+1D0h]
0x140059a7b  mov     ecx, ebp
0x140059a7d  lea     rdx, [rax+rcx*8]
0x140059a81  mov     rcx, [rax+rcx*8]
0x140059a85  test    rcx, rcx
0x140059a88  jnz     loc_140059C73
0x140059a8e  inc     ebp
0x140059a90  cmp     ebp, 40h ; '@'
0x140059a93  jl      short loc_140059A6D
0x140059a95  mov     r12, [rsp+48h+arg_18]
0x140059a9a  lea     rcx, [rdi+1C0h]
0x140059aa1  mov     rdx, rsi
0x140059aa4  call    cs:__imp_RtlRbRemoveNode
0x140059aab  nop     dword ptr [rax+rax+00h]
0x140059ab0  xorps   xmm0, xmm0
0x140059ab3  xor     eax, eax
0x140059ab5  movups  xmmword ptr [rsi], xmm0
0x140059ab8  mov     [rsi+10h], rax
0x140059abc  mov     rcx, cs:WPP_GLOBAL_Control
0x140059ac3  mov     rbp, [rsp+48h+arg_0]
0x140059ac8  cmp     rcx, r14
0x140059acb  jz      short loc_140059ADA
0x140059acd  test    dword ptr [rcx+2Ch], 100h
0x140059ad4  jnz     loc_140059CA4
0x140059ada  dec     dword ptr [rdi+138h]
0x140059ae0  lock inc dword ptr [rdi+12Ch]
0x140059ae7  mov     rdi, [rsp+48h+arg_10]
0x140059aec  mov     rsi, [rsp+48h+arg_8]
0x140059af1  mov     rcx, cs:WPP_GLOBAL_Control
0x140059af8  cmp     rcx, r14
0x140059afb  jz      short loc_140059B0A
0x140059afd  test    dword ptr [rcx+2Ch], 100h
0x140059b04  jnz     loc_140059CD4
0x140059b0a  mov     byte ptr [rbx+178h], 1
0x140059b11  mov     rcx, rbx
0x140059b14  call    RxCloseFcbForTurboIo
0x140059b19  mov     rcx, rbx; Instance
0x140059b1c  call    RxDeregisterFcbWithBufferingManager
0x140059b21  mov     rax, [rbx+188h]
0x140059b28  mov     [rbx+11Ah], r15w
0x140059b30  test    rax, rax
0x140059b33  jz      short loc_140059B46
0x140059b35  mov     rax, [rax+80h]
0x140059b3c  mov     rdx, rbx
0x140059b3f  xor     ecx, ecx
0x140059b41  call    _guard_dispatch_icall
0x140059b46  mov     rcx, [rbx+8]; Resource
0x140059b4a  call    cs:__imp_ExDeleteResourceLite
0x140059b51  nop     dword ptr [rax+rax+00h]
0x140059b56  mov     rcx, [rbx+10h]; Resource
0x140059b5a  call    cs:__imp_ExDeleteResourceLite
0x140059b61  nop     dword ptr [rax+rax+00h]
0x140059b66  lea     rcx, [rbx+58h]; Oplock
0x140059b6a  call    cs:__imp_FsRtlUninitializeOplock
0x140059b71  nop     dword ptr [rax+rax+00h]
0x140059b76  mov     rax, [rbx+78h]
0x140059b7a  test    rax, rax
0x140059b7d  jz      short loc_140059B92
0x140059b7f  lock dec dword ptr [rax+3Ch]
0x140059b83  xor     edx, edx; LockHoldingState
0x140059b85  mov     rcx, [rbx+78h]; Instance
0x140059b89  call    RxDereference
0x140059b8e  mov     [rbx+78h], r15
0x140059b92  mov     rcx, rbx; Object
0x140059b95  call    RxFreeFcbObject
0x140059b9a  mov     r15, [rsp+48h+var_18]
0x140059b9f  add     rsp, 38h
0x140059ba3  pop     r14
0x140059ba5  pop     rbx
0x140059ba6  retn
0x140059ba8  mov     eax, [rbx+98h]
0x140059bae  mov     r9, rcx; BugCheckParameter3
0x140059bb1  mov     ecx, 27h ; '''; BugCheckCode
0x140059bb6  mov     [rsp+48h+BugCheckParameter4], rax; BugCheckParameter4
0x140059bbb  mov     r8, rbx; BugCheckParameter2
0x140059bbe  mov     edx, 0FCB0151Dh; BugCheckParameter1
0x140059bc3  call    cs:__imp_KeBugCheckEx
0x140059bd0  lea     rcx, [rbx+218h]; FileLock
0x140059bd7  call    cs:__imp_FsRtlUninitializeFileLock
0x140059bde  nop     dword ptr [rax+rax+00h]
0x140059be3  jmp     loc_140059998
0x140059be8  mov     [rdx+28h], r8
0x140059bec  mov     rdx, [rdx]
0x140059bef  cmp     rdx, rcx
0x140059bf2  jz      loc_1400599EA
0x140059bf8  cmp     [rdx+28h], rsi
0x140059bfc  jnz     short loc_140059BEC
0x140059bfe  mov     r8, [rsi+8]
0x140059c02  test    r8, r8
0x140059c05  jz      short loc_140059C1F
0x140059c07  mov     r9, [r8]
0x140059c0a  test    r9, r9
0x140059c0d  jz      short loc_140059BE8
0x140059c0f  mov     rax, [r9]
0x140059c12  mov     r8, r9
0x140059c15  mov     r9, rax
0x140059c18  test    rax, rax
0x140059c1b  jnz     short loc_140059C0F
0x140059c1d  jmp     short loc_140059BE8
0x140059c1f  mov     r8, [rsi+10h]
0x140059c23  mov     rax, rsi
0x140059c26  and     r8, 0FFFFFFFFFFFFFFFCh
0x140059c2a  jz      short loc_140059BE8
0x140059c2c  cmp     [r8], rax
0x140059c2f  jz      short loc_140059BE8
0x140059c31  mov     rax, r8
0x140059c34  mov     r8, [r8+10h]
0x140059c38  and     r8, 0FFFFFFFFFFFFFFFCh
0x140059c3c  jnz     short loc_140059C2C
0x140059c3e  jmp     short loc_140059BE8
0x140059c40  cmp     byte ptr [rcx+29h], 2
0x140059c44  jb      loc_14005993B
0x140059c4a  mov     rcx, [rcx+18h]
0x140059c4e  lea     rax, [rbx+150h]
0x140059c55  mov     edx, 3Eh ; '>'
0x140059c5a  mov     [rsp+48h+BugCheckParameter4], rax
0x140059c5f  mov     r9, rbx
0x140059c62  lea     r8, WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids
0x140059c69  call    WPP_SF_qZ
0x140059c6e  jmp     loc_14005993B
0x140059c73  test    cl, 1
0x140059c76  jz      loc_140059A8E
0x140059c7c  and     rcx, 0FFFFFFFFFFFFFFFEh; P
0x140059c80  cmp     [rcx], rsi
0x140059c83  jnz     loc_140059A8E
0x140059c89  mov     [rdx], r15
0x140059c8c  xor     edx, edx; Tag
0x140059c8e  call    cs:__imp_ExFreePoolWithTag
0x140059c95  nop     dword ptr [rax+rax+00h]
0x140059c9a  add     [rsi+28h], r12w
0x140059c9f  jmp     loc_140059A8E
0x140059ca4  cmp     byte ptr [rcx+29h], 4
0x140059ca8  jb      loc_140059ADA
0x140059cae  mov     rcx, [rcx+18h]
0x140059cb2  lea     rax, [rsi+18h]
0x140059cb6  mov     edx, 0Eh
0x140059cbb  mov     [rsp+48h+BugCheckParameter4], rax
0x140059cc0  mov     r9, rbx
0x140059cc3  lea     r8, WPP_518c92af35303f374eeedacc3593600d_Traceguids
0x140059cca  call    WPP_SF_qZ
0x140059ccf  jmp     loc_140059ADA
0x140059cd4  cmp     byte ptr [rcx+29h], 4
0x140059cd8  jb      loc_140059B0A
0x140059cde  mov     rcx, [rcx+18h]
0x140059ce2  lea     r8, WPP_e7aebc7caeed3866654dc8faf8a6aa71_Traceguids
0x140059ce9  mov     edx, 3Fh ; '?'
0x140059cee  mov     r9, rbx
0x140059cf1  call    WPP_SF_q
0x140059cf6  jmp     loc_140059B0A
```
