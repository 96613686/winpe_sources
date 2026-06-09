# SmbCeCancelExchange

- ea: `0x140012940`
- end: `0x140012d41`
- name: `SmbCeCancelExchange`
- size: `1025`
- prototype: `NTSTATUS __stdcall(PRX_CONTEXT RxContext)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1400054b0`
- `0x140005d10`
- `0x14000ebd8`
- `0x14001243c`
- `0x140012940`
- `0x140016560`
- `0x14003f020`
- `0x14003f41c`
- `0x1400478f0`

## import_xrefs

- `ntoskrnl!IoGetRequestorProcessId` at `0x140012c10`
- `ntoskrnl!IoGetRequestorProcessId` at `0x140012c10`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012aae`
- `ntoskrnl!KeReleaseSpinLock` at `0x140012aae`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400129f2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400129f2`
- `ntoskrnl!IoFreeMdl` at `0x140012ccf`
- `ntoskrnl!IoFreeMdl` at `0x140012ccf`
- `ntoskrnl!MmProbeAndLockPages` at `0x140012c79`
- `ntoskrnl!MmProbeAndLockPages` at `0x140012c79`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140012bda`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140012bda`
- `ntoskrnl!ExReleaseResourceLite` at `0x140012bce`
- `ntoskrnl!ExReleaseResourceLite` at `0x140012bce`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140012b67`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140012b67`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140012b52`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140012b52`
- `rdbss!RxUnlockHeaderPages` at `0x140012cc0`
- `rdbss!RxUnlockHeaderPages` at `0x140012cc0`
- `rdbss!RxAllocateMdl2` at `0x140012c54`
- `rdbss!RxAllocateMdl2` at `0x140012c54`

## pseudocode

```c
__int64 __fastcall SmbCeCancelExchange(PRX_CONTEXT RxContext)
{
  PSZ FileName; // rax
  __int64 v3; // r12
  _QWORD *v4; // rax
  _QWORD *v5; // rdi
  volatile signed __int32 *v6; // rcx
  _QWORD *v7; // rdx
  unsigned int v8; // r15d
  __int64 *v9; // rdi
  __int64 *v10; // r13
  __int64 **v11; // rax
  __int64 *v12; // rbx
  int v13; // edi
  ULONG RequestorProcessId; // kr00_4
  struct _MDL *Mdl2; // rax
  struct _MDL *v16; // rdi
  __int64 v17; // rdx
  char v19[8]; // [rsp+30h] [rbp-A8h] BYREF
  __int128 v20; // [rsp+38h] [rbp-A0h] BYREF
  struct _MDL *v21; // [rsp+48h] [rbp-90h] BYREF
  int v22; // [rsp+50h] [rbp-88h] BYREF
  __int64 v23; // [rsp+58h] [rbp-80h]
  PRX_CONTEXT v24; // [rsp+60h] [rbp-78h]
  __int64 *v25; // [rsp+68h] [rbp-70h]
  __int64 *v26; // [rsp+70h] [rbp-68h]
  _BYTE v27[12]; // [rsp+78h] [rbp-60h] BYREF
  __int16 v28; // [rsp+84h] [rbp-54h]
  __int16 v29; // [rsp+92h] [rbp-46h]
  __int16 v30; // [rsp+96h] [rbp-42h]
  char v31; // [rsp+98h] [rbp-40h]
  __int16 v32; // [rsp+99h] [rbp-3Fh]

  v24 = RxContext;
  v20 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 57, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids, RxContext);
  if ( LOBYTE(RxContext->RealDevice) )
    FileName = *(PSZ *)&RxContext->pFcb->UncleanCount;
  else
    FileName = RxContext->TrackerHistory[0].FileName;
  v23 = *(_QWORD *)(*((_QWORD *)FileName + 5) + 56LL);
  v3 = v23;
  *((_QWORD *)&v20 + 1) = &v20;
  *(_QWORD *)&v20 = &v20;
  s_SmbCeDbSpinLockSavedIrql = KeAcquireSpinLockRaiseToDpc(&s_SmbCeDbSpinLock);
  v4 = *(_QWORD **)(v3 + 232);
  if ( v4 != (_QWORD *)(v3 + 232) )
  {
    do
    {
      v5 = (_QWORD *)*v4;
      v6 = (volatile signed __int32 *)(v4 - 16);
      if ( (PRX_CONTEXT)*(v4 - 13) == RxContext && (v6[18] & 8) == 0 )
      {
        if ( *((int *)v6 + 28) <= 0 )
        {
          _InterlockedCompareExchange(v6 + 17, -858993460, -1431655766);
        }
        else
        {
          v7 = (_QWORD *)*((_QWORD *)&v20 + 1);
          if ( **((__int128 ***)&v20 + 1) != &v20 )
LABEL_33:
            __fastfail(3u);
          *((_QWORD *)v6 + 32) = &v20;
          *((_QWORD *)v6 + 33) = v7;
          *v7 = v6 + 64;
          *((_QWORD *)&v20 + 1) = v6 + 64;
          _InterlockedIncrement(v6 + 29);
          if ( (*(_DWORD *)(v3 + 420) & 0x40000) == 0 && (v6[18] & 1) != 0 )
            SmbCepDiscardMidAssociatedWithExchange();
        }
      }
      v4 = v5;
    }
    while ( v5 != (_QWORD *)(v3 + 232) );
  }
  v8 = 0;
  KeReleaseSpinLock(&s_SmbCeDbSpinLock, s_SmbCeDbSpinLockSavedIrql);
  v9 = (__int64 *)v20;
  while ( v9 != (__int64 *)&v20 )
  {
    v10 = (__int64 *)*v9;
    v25 = v10;
    if ( (__int64 *)v10[1] != v9 )
      goto LABEL_33;
    v11 = (__int64 **)v9[1];
    if ( *v11 != v9 )
      goto LABEL_33;
    v12 = v9 - 32;
    v26 = v9 - 32;
    *v11 = v10;
    v10[1] = (__int64)v11;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 58, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids, v9 - 32);
    if ( (*(_DWORD *)(v3 + 420) & 0x40000) != 0 )
    {
      v21 = 0;
      v22 = 36;
      KeEnterCriticalRegion();
      ExAcquireResourceExclusiveLite(&s_SmbCeDbResource, 1u);
      v13 = *((_DWORD *)v12 + 18);
      if ( (v13 & 0x1000) == 0 )
      {
        SmbCeSetExpiryTime(v12);
        v13 = *((_DWORD *)v12 + 18) | 0x1000;
      }
      *((_DWORD *)v12 + 18) = v13 & 0xFFFFFCFF;
      v8 = SmbCeBuildSmbHeader((_DWORD)v12, (unsigned int)v27, 36, (unsigned int)&v22, (__int64)v19, (__int64)&v21);
      *((_DWORD *)v12 + 18) = v13;
      ExReleaseResourceLite(&s_SmbCeDbResource);
      KeLeaveCriticalRegion();
      if ( !v8 )
      {
        LOBYTE(v21->Next) = -92;
        v30 = *((_WORD *)v12 + 32);
        if ( (v12[9] & 0x4000) != 0 )
        {
          RequestorProcessId = IoGetRequestorProcessId(RxContext->CurrentIrp);
          v28 = HIWORD(RequestorProcessId);
          v29 = RequestorProcessId;
        }
        v31 = 0;
        v32 = 0;
        Mdl2 = (struct _MDL *)RxAllocateMdl2(v27, 36, 0, 0, 0);
        v16 = Mdl2;
        v21 = Mdl2;
        if ( Mdl2 )
        {
          MmProbeAndLockPages(Mdl2, 0, IoModifyAccess);
          v8 = SmbCeSendToServer(v3, v17, v16, 36);
          RxUnlockHeaderPages(v16);
          IoFreeMdl(v16);
        }
      }
    }
    else
    {
      SmbCeFinalizeExchangeOnDisconnect(v9 - 32);
    }
    v9 = v10;
    _InterlockedCompareExchange((volatile signed __int32 *)v12 + 17, -858993460, -1431655766);
    SmbCeDecrementPendingOperationsAndFinalize(v12);
  }
  return v8;
}

```

## disassembly

```asm
0x140012940  mov     [rsp+arg_8], rbx
0x140012945  mov     [rsp+arg_10], rsi
0x14001294a  push    rdi
0x14001294b  push    r12
0x14001294d  push    r13
0x14001294f  push    r14
0x140012951  push    r15
0x140012953  sub     rsp, 0B0h
0x14001295a  mov     rax, cs:__security_cookie
0x140012961  xor     rax, rsp
0x140012964  mov     [rsp+0D8h+var_38], rax
0x14001296c  mov     rsi, rcx
0x14001296f  mov     [rsp+0D8h+var_78], rcx
0x140012974  xorps   xmm0, xmm0
0x140012977  movups  [rsp+0D8h+var_A0], xmm0
0x14001297c  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x140012983  mov     rcx, cs:WPP_GLOBAL_Control
0x14001298a  cmp     rcx, rax
0x14001298d  jz      short loc_1400129B0
0x14001298f  test    dword ptr [rcx+2Ch], 200h
0x140012996  jz      short loc_1400129B0
0x140012998  mov     edx, 39h ; '9'
0x14001299d  mov     r9, rsi
0x1400129a0  lea     r8, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids
0x1400129a7  mov     rcx, [rcx+18h]
0x1400129ab  call    WPP_SF_q
0x1400129b0  xor     r14d, r14d
0x1400129b3  cmp     [rsi+20h], r14b
0x1400129b7  jnz     short loc_1400129C2
0x1400129b9  mov     rax, [rsi+288h]
0x1400129c0  jmp     short loc_1400129CA
0x1400129c2  mov     rax, [rsi+38h]
0x1400129c6  mov     rax, [rax+78h]
0x1400129ca  mov     rax, [rax+28h]
0x1400129ce  mov     r12, [rax+38h]
0x1400129d2  mov     [rsp+0D8h+var_80], r12
0x1400129d7  lea     rax, [rsp+0D8h+var_A0]
0x1400129dc  mov     qword ptr [rsp+0D8h+var_A0+8], rax
0x1400129e1  lea     rax, [rsp+0D8h+var_A0]
0x1400129e6  mov     qword ptr [rsp+0D8h+var_A0], rax
0x1400129eb  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x1400129f2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400129f9  nop     dword ptr [rax+rax+00h]
0x1400129fe  mov     cs:s_SmbCeDbSpinLockSavedIrql, al
0x140012a04  lea     rbx, [r12+0E8h]
0x140012a0c  mov     rax, [rbx]
0x140012a0f  cmp     rax, rbx
0x140012a12  jz      loc_140012A9E
0x140012a18  mov     r13d, 0CCCCCCCCh
0x140012a1e  mov     rdi, [rax]
0x140012a21  lea     rcx, [rax-80h]
0x140012a25  cmp     [rcx+18h], rsi
0x140012a29  jnz     short loc_140012A96
0x140012a2b  mov     eax, [rcx+48h]
0x140012a2e  test    al, 8
0x140012a30  jnz     short loc_140012A96
0x140012a32  cmp     [rcx+70h], r14d
0x140012a36  jle     short loc_140012A8B
0x140012a38  mov     rdx, qword ptr [rsp+0D8h+var_A0+8]
0x140012a3d  lea     rax, [rsp+0D8h+var_A0]
0x140012a42  cmp     [rdx], rax
0x140012a45  jnz     loc_140012D09
0x140012a4b  lea     rax, [rcx+100h]
0x140012a52  lea     r8, [rsp+0D8h+var_A0]
0x140012a57  mov     [rax], r8
0x140012a5a  mov     [rax+8], rdx
0x140012a5e  mov     [rdx], rax
0x140012a61  mov     qword ptr [rsp+0D8h+var_A0+8], rax
0x140012a66  lock inc dword ptr [rcx+74h]
0x140012a6a  test    dword ptr [r12+1A4h], 40000h
0x140012a76  setz    dl
0x140012a79  test    byte ptr [rcx+48h], 1
0x140012a7d  setnz   al
0x140012a80  test    al, dl
0x140012a82  jz      short loc_140012A96
0x140012a84  call    SmbCepDiscardMidAssociatedWithExchange
0x140012a89  jmp     short loc_140012A96
0x140012a8b  mov     eax, 0AAAAAAAAh
0x140012a90  lock cmpxchg [rcx+44h], r13d
0x140012a96  mov     rax, rdi
0x140012a99  cmp     rdi, rbx
0x140012a9c  jnz     short loc_140012A1E
0x140012a9e  mov     r15d, r14d
0x140012aa1  mov     dl, cs:s_SmbCeDbSpinLockSavedIrql; NewIrql
0x140012aa7  lea     rcx, s_SmbCeDbSpinLock; SpinLock
0x140012aae  call    cs:__imp_KeReleaseSpinLock
0x140012ab5  nop     dword ptr [rax+rax+00h]
0x140012aba  mov     rdi, qword ptr [rsp+0D8h+var_A0]
0x140012abf  lea     rax, [rsp+0D8h+var_A0]
0x140012ac4  cmp     rdi, rax
0x140012ac7  jz      loc_140012D10
0x140012acd  mov     r13, [rdi]
0x140012ad0  mov     [rsp+0D8h+var_70], r13
0x140012ad5  cmp     [r13+8], rdi
0x140012ad9  jnz     loc_140012D09
0x140012adf  mov     rax, [rdi+8]
0x140012ae3  cmp     [rax], rdi
0x140012ae6  jnz     loc_140012D09
0x140012aec  lea     rbx, [rdi-100h]
0x140012af3  mov     [rsp+0D8h+var_68], rbx
0x140012af8  mov     [rax], r13
0x140012afb  mov     [r13+8], rax
0x140012aff  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140012b06  lea     rax, WPP_GLOBAL_Control
0x140012b0d  cmp     rcx, rax
0x140012b10  jz      short loc_140012B33
0x140012b12  test    dword ptr [rcx+2Ch], 200h
0x140012b19  jz      short loc_140012B33
0x140012b1b  mov     edx, 3Ah ; ':'
0x140012b20  mov     r9, rbx
0x140012b23  lea     r8, WPP_65e251ebcb3a3c140a4f07b17494cbc8_Traceguids
0x140012b2a  mov     rcx, [rcx+18h]
0x140012b2e  call    WPP_SF_q
0x140012b33  test    dword ptr [r12+1A4h], 40000h
0x140012b3f  jz      loc_140012CDD
0x140012b45  mov     [rsp+0D8h+var_90], r14
0x140012b4a  mov     [rsp+0D8h+var_88], 24h ; '$'
0x140012b52  call    cs:__imp_KeEnterCriticalRegion
0x140012b59  nop     dword ptr [rax+rax+00h]
0x140012b5e  mov     dl, 1; Wait
0x140012b60  lea     rcx, s_SmbCeDbResource; Resource
0x140012b67  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140012b6e  nop     dword ptr [rax+rax+00h]
0x140012b73  mov     edi, [rbx+48h]
0x140012b76  bt      edi, 0Ch
0x140012b7a  jb      short loc_140012B8B
0x140012b7c  mov     rcx, rbx
0x140012b7f  call    SmbCeSetExpiryTime
0x140012b84  mov     edi, [rbx+48h]
0x140012b87  bts     edi, 0Ch
0x140012b8b  mov     eax, edi
0x140012b8d  and     eax, 0FFFFFCFFh
0x140012b92  mov     [rbx+48h], eax
0x140012b95  lea     rax, [rsp+0D8h+var_90]
0x140012b9a  mov     [rsp+0D8h+var_B0], rax
0x140012b9f  lea     rax, [rsp+0D8h+var_A8]
0x140012ba4  mov     [rsp+0D8h+var_B8], rax
0x140012ba9  lea     r9, [rsp+0D8h+var_88]
0x140012bae  mov     r8d, 24h ; '$'
0x140012bb4  lea     rdx, [rsp+0D8h+var_60]
0x140012bb9  mov     rcx, rbx
0x140012bbc  call    SmbCeBuildSmbHeader
0x140012bc1  mov     r15d, eax
0x140012bc4  mov     [rbx+48h], edi
0x140012bc7  lea     rcx, s_SmbCeDbResource; Resource
0x140012bce  call    cs:__imp_ExReleaseResourceLite
0x140012bd5  nop     dword ptr [rax+rax+00h]
0x140012bda  call    cs:__imp_KeLeaveCriticalRegion
0x140012be1  nop     dword ptr [rax+rax+00h]
0x140012be6  test    r15d, r15d
0x140012be9  jnz     loc_140012CE5
0x140012bef  mov     rcx, [rsp+0D8h+var_90]
0x140012bf4  mov     byte ptr [rcx], 0A4h
0x140012bf7  movzx   ecx, word ptr [rbx+40h]
0x140012bfb  mov     [rsp+0D8h+var_42], cx
0x140012c03  test    dword ptr [rbx+48h], 4000h
0x140012c0a  jz      short loc_140012C2F
0x140012c0c  mov     rcx, [rsi+28h]; Irp
0x140012c10  call    cs:__imp_IoGetRequestorProcessId
0x140012c17  nop     dword ptr [rax+rax+00h]
0x140012c1c  mov     [rsp+0D8h+var_46], ax
0x140012c24  shr     eax, 10h
0x140012c27  mov     [rsp+0D8h+var_54], ax
0x140012c2f  mov     [rsp+0D8h+var_40], r14b
0x140012c37  mov     [rsp+0D8h+var_3F], r14w
0x140012c40  mov     [rsp+0D8h+var_B8], r14
0x140012c45  xor     r9d, r9d
0x140012c48  xor     r8d, r8d
0x140012c4b  lea     edx, [r9+24h]
0x140012c4f  lea     rcx, [rsp+0D8h+var_60]
0x140012c54  call    cs:__imp_RxAllocateMdl2
0x140012c5b  nop     dword ptr [rax+rax+00h]
0x140012c60  mov     rdi, rax
0x140012c63  mov     [rsp+0D8h+var_90], rax
0x140012c68  test    rax, rax
0x140012c6b  jz      short loc_140012CE5
0x140012c6d  mov     r15d, r14d
0x140012c70  xor     edx, edx; AccessMode
0x140012c72  lea     r8d, [rdx+2]; Operation
0x140012c76  mov     rcx, rax; MemoryDescriptorList
0x140012c79  call    cs:__imp_MmProbeAndLockPages
0x140012c80  nop     dword ptr [rax+rax+00h]
0x140012c85  jmp     short loc_140012CA6
0x140012c87  mov     r15d, eax
0x140012c8a  xor     r14d, r14d
0x140012c8d  mov     r12, [rsp+0D8h+var_80]
0x140012c92  mov     rdi, [rsp+0D8h+var_90]
0x140012c97  mov     rsi, [rsp+0D8h+var_78]
0x140012c9c  mov     r13, [rsp+0D8h+var_70]
0x140012ca1  mov     rbx, [rsp+0D8h+var_68]
0x140012ca6  test    r15d, r15d
0x140012ca9  jnz     short loc_140012CCC
0x140012cab  lea     r9d, [r15+24h]
0x140012caf  mov     r8, rdi
0x140012cb2  mov     rcx, r12
0x140012cb5  call    SmbCeSendToServer
0x140012cba  mov     r15d, eax
0x140012cbd  mov     rcx, rdi
0x140012cc0  call    cs:__imp_RxUnlockHeaderPages
0x140012cc7  nop     dword ptr [rax+rax+00h]
0x140012ccc  mov     rcx, rdi; Mdl
0x140012ccf  call    cs:__imp_IoFreeMdl
0x140012cd6  nop     dword ptr [rax+rax+00h]
0x140012cdb  jmp     short loc_140012CE5
0x140012cdd  mov     rcx, rbx
0x140012ce0  call    SmbCeFinalizeExchangeOnDisconnect
0x140012ce5  mov     rdi, r13
0x140012ce8  mov     eax, 0AAAAAAAAh
0x140012ced  mov     ecx, 0CCCCCCCCh
0x140012cf2  lock cmpxchg [rbx+44h], ecx
0x140012cf7  mov     edx, 1
0x140012cfc  mov     rcx, rbx; pContext
0x140012cff  call    SmbCeDecrementPendingOperationsAndFinalize
0x140012d04  jmp     loc_140012ABF
0x140012d09  mov     ecx, 3
0x140012d0e  int     29h; Win8: RtlFailFast(ecx)
0x140012d10  mov     eax, r15d
0x140012d13  mov     rcx, [rsp+0D8h+var_38]
0x140012d1b  xor     rcx, rsp; StackCookie
0x140012d1e  call    __security_check_cookie
0x140012d23  lea     r11, [rsp+0D8h+var_28]
0x140012d2b  mov     rbx, [r11+38h]
0x140012d2f  mov     rsi, [r11+40h]
0x140012d33  mov     rsp, r11
0x140012d36  pop     r15
0x140012d38  pop     r14
0x140012d3a  pop     r13
0x140012d3c  pop     r12
0x140012d3e  pop     rdi
0x140012d3f  retn
```
