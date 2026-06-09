# RxPrefixClaim

- ea: `0x140065830`
- end: `0x140065c94`
- name: `RxPrefixClaim`
- size: `1124`
- prototype: `NTSTATUS __stdcall(PRX_CONTEXT RxContext)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140063990`

## callees

- `0x140003f50`
- `0x14000ce60`
- `0x14000e950`
- `0x140014e40`
- `0x140016e20`
- `0x140016e70`
- `0x1400232e0`
- `0x140025d80`
- `0x140026080`
- `0x140053f50`
- `0x1400548f0`
- `0x140065830`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140065913`
- `ntoskrnl!ExAllocatePool2` at `0x140065a5a`
- `ntoskrnl!ExAllocatePool2` at `0x140065913`
- `ntoskrnl!ExAllocatePool2` at `0x140065a5a`
- `ntoskrnl!IoGetRequestorProcess` at `0x140065851`
- `ntoskrnl!IoGetRequestorProcess` at `0x140065851`
- `ntoskrnl!PsGetEffectiveServerSilo` at `0x1400659ae`
- `ntoskrnl!PsGetEffectiveServerSilo` at `0x1400659ae`
- `ntoskrnl!PsIsHostSilo` at `0x1400659c0`
- `ntoskrnl!PsIsHostSilo` at `0x1400659c0`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x140065c15`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x140065c15`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065bc7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065be8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065bc7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140065be8`

## pseudocode

```c
NTSTATUS __stdcall RxPrefixClaim(PRX_CONTEXT RxContext)
{
  PIRP CurrentIrp; // rsi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rdi
  NTSTATUS Ecp; // edi
  _DWORD *UserBuffer; // rbp
  PNAMED_PIPE_CREATE_PARAMETERS Parameters; // r15
  void *Pool2; // rax
  PVOID *p_pInputBuffer; // r14
  char v9; // di
  PNON_PAGED_FCB NonPagedFcb; // rax
  UNICODE_STRING *v11; // rdi
  char v12; // al
  unsigned int v13; // ecx
  _WORD *v14; // rax
  bool v15; // cl
  char v16; // al
  void *v17; // rcx
  PSZ FileName; // rcx
  __int64 v20[2]; // [rsp+40h] [rbp-58h] BYREF
  UNICODE_STRING v21; // [rsp+50h] [rbp-48h] BYREF
  UNICODE_STRING CanonicalName; // [rsp+60h] [rbp-38h] BYREF
  char v23; // [rsp+A0h] [rbp+8h] BYREF

  CurrentIrp = RxContext->CurrentIrp;
  IoGetRequestorProcess(CurrentIrp);
  CurrentStackLocation = CurrentIrp->Tail.Overlay.CurrentStackLocation;
  v23 = 4;
  v21 = 0;
  CanonicalName = 0;
  *(_OWORD *)v20 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids, RxContext);
  }
  LODWORD(RxContext->RdbssDbgExtension) |= 2u;
  LODWORD(v20[0]) = 0;
  v20[1] = 0;
  if ( CurrentIrp->RequestorMode == 1 )
  {
    Ecp = -1073741808;
    goto LABEL_45;
  }
  UserBuffer = CurrentIrp->UserBuffer;
  if ( LOBYTE(RxContext->RealDevice) != 14 )
  {
    p_pInputBuffer = &RxContext->LowIoContext.ParamsFor.FsCtl.pInputBuffer;
    goto LABEL_23;
  }
  Parameters = CurrentStackLocation->Parameters.CreatePipe.Parameters;
  LOBYTE(RxContext->RealDevice) = 0;
  Pool2 = (void *)ExAllocatePool2(66, LOWORD(Parameters->DefaultTimeout.LowPart), 860715090);
  p_pInputBuffer = &RxContext->LowIoContext.ParamsFor.FsCtl.pInputBuffer;
  RxContext->LowIoContext.ParamsFor.ReadWrite.ByteOffset = (RXVBO)Pool2;
  if ( !Pool2 )
  {
    Ecp = -1073741670;
    goto LABEL_36;
  }
  memmove(Pool2, *(const void **)&Parameters->TimeoutSpecified, LOWORD(Parameters->DefaultTimeout.LowPart));
  v9 = BYTE6(RxContext->TrackerHistory[4].FileName);
  LOWORD(RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory.NotificationBufferLength) = Parameters->DefaultTimeout.LowPart;
  RxContext->Create.NetNamePrefixEntry = *(PRX_PREFIX_ENTRY *)&Parameters[1].InboundQuota;
  memset((char *)&RxContext->9 + 112, 0, 0xEEu);
  memset((char *)&RxContext->TrackerHistory[4].FileName + 7, 0, 0x69u);
  NonPagedFcb = RxContext->NonPagedFcb;
  BYTE6(RxContext->TrackerHistory[4].FileName) = v9 & 0x10;
  if ( (NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.LockNV & 0x2000) != 0 )
  {
    v11 = (UNICODE_STRING *)((__int64 (__fastcall *)(_QWORD))PsGetEffectiveServerSilo)((LARGE_INTEGER)Parameters[1].DefaultTimeout.QuadPart);
    if ( !(unsigned __int8)PsIsHostSilo(v11) )
    {
      RxContext->TrackerHistory[8].FileName = (PSZ)RxGetSiloFromServerSilo(v11);
      RxContext->LoudCompletionString = v11;
    }
  }
  BYTE5(RxContext->TrackerHistory[4].FileName) |= 0x28u;
  *((_QWORD *)&RxContext->9 + 18) = *(_QWORD *)&Parameters->NamedPipeType;
  v12 = BYTE6(RxContext->TrackerHistory[4].FileName) & 0xFB;
  v13 = (*(_DWORD *)(*(_QWORD *)&Parameters->NamedPipeType + 20LL) & 0xFFFFFFu) >> 8;
  *((_DWORD *)&RxContext->9 + 35) = *(_DWORD *)(*(_QWORD *)&Parameters->NamedPipeType + 20LL) & 0xFFFBFF;
  BYTE6(RxContext->TrackerHistory[4].FileName) = v12 | v13 & 4;
  RxContext->TrackerHistory[2].FileName = *(PSZ *)&Parameters->InboundQuota;
  RxContext->TrackerHistory[3].AcquireRelease = Parameters->CompletionMode;
  if ( !*(_QWORD *)&Parameters[1].CompletionMode )
  {
LABEL_20:
    RxInitializeSMBTreeConnectEcp(RxContext, RxContext->Create.NetNamePrefixEntry);
    Ecp = RxFindOrInitializeNetworkCreateEcp((__int64)RxContext);
    if ( Ecp < 0 )
    {
LABEL_33:
      if ( Ecp == 259 )
        goto LABEL_45;
      if ( Ecp >= 0 )
        *UserBuffer = LOWORD(RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory.NotificationBufferLength)
                    - LOWORD(v20[0]);
      goto LABEL_36;
    }
LABEL_23:
    v21 = *(UNICODE_STRING *)&RxContext->LowIoContext.ParamsFor.NotifyChangeDirectory.NotificationBufferLength;
    *(UNICODE_STRING *)v20 = v21;
    Ecp = RxFirstCanonicalize((__int64)RxContext, (char *)CurrentIrp, &v21, &CanonicalName, &v23);
    if ( Ecp >= 0 )
    {
      v15 = (BYTE6(RxContext->TrackerHistory[4].FileName) & 4) != 0
         && (RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.LockNV & 0x20) != 0;
      v16 = (*((_DWORD *)&RxContext->9 + 35) & 0x80u) != 0 && v15;
      Ecp = RxFindOrConstructVirtualNetRootWithRetry(RxContext, CurrentIrp, &CanonicalName, v16, 0, (__int64)v20);
    }
    goto LABEL_33;
  }
  v14 = (_WORD *)ExAllocatePool2(64, LOWORD(Parameters[1].NamedPipeType) + 4LL, 860715090);
  *(_QWORD *)&RxContext->TrackerHistory[1].Flags = v14;
  if ( v14 )
  {
    *v14 = Parameters[1].NamedPipeType;
    memmove(
      (void *)(*(_QWORD *)&RxContext->TrackerHistory[1].Flags + 2LL),
      *(const void **)&Parameters[1].CompletionMode,
      LOWORD(Parameters[1].NamedPipeType));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids, &Parameters[1]);
    }
    goto LABEL_20;
  }
  Ecp = -1073741670;
LABEL_36:
  if ( !LOBYTE(RxContext->RealDevice) )
  {
    if ( *p_pInputBuffer )
    {
      ExFreePoolWithTag(*p_pInputBuffer, 0);
      *p_pInputBuffer = 0;
    }
    v17 = *(void **)&RxContext->TrackerHistory[1].Flags;
    if ( v17 )
    {
      ExFreePoolWithTag(v17, 0);
      *(_QWORD *)&RxContext->TrackerHistory[1].Flags = 0;
    }
    if ( !RxContext->Create.NetNamePrefixEntry )
    {
      FileName = RxContext->TrackerHistory[1].FileName;
      if ( FileName )
        FsRtlFreeExtraCreateParameter(FileName);
    }
    RxpFinalizeCreateContext(RxContext);
    LOBYTE(RxContext->RealDevice) = 14;
  }
LABEL_45:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids, (unsigned int)Ecp);
  }
  return Ecp;
}

```

## disassembly

```asm
0x140065830  mov     rax, rsp
0x140065833  push    rdi
0x140065834  sub     rsp, 90h
0x14006583b  mov     [rax+10h], rbx
0x14006583f  mov     rbx, rcx
0x140065842  mov     [rax-10h], rsi
0x140065846  mov     rsi, [rcx+28h]
0x14006584a  mov     rcx, rsi; Irp
0x14006584d  mov     [rax-18h], r13
0x140065851  call    cs:__imp_IoGetRequestorProcess
0x140065858  nop     dword ptr [rax+rax+00h]
0x14006585d  mov     rdi, [rsi+0B8h]
0x140065864  xorps   xmm0, xmm0
0x140065867  xorps   xmm1, xmm1
0x14006586a  mov     [rsp+98h+arg_0], 4
0x140065872  movups  [rsp+98h+var_48], xmm0
0x140065877  movups  xmmword ptr [rsp+98h+CanonicalName.Length], xmm1
0x14006587c  movups  xmmword ptr [rsp+98h+var_58], xmm0
0x140065881  mov     rcx, cs:WPP_GLOBAL_Control
0x140065888  lea     r13, WPP_GLOBAL_Control
0x14006588f  cmp     rcx, r13
0x140065892  jz      short loc_1400658B9
0x140065894  mov     eax, [rcx+2Ch]
0x140065897  test    al, 8
0x140065899  jz      short loc_1400658B9
0x14006589b  cmp     byte ptr [rcx+29h], 2
0x14006589f  jb      short loc_1400658B9
0x1400658a1  mov     rcx, [rcx+18h]
0x1400658a5  lea     r8, WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids
0x1400658ac  mov     edx, 30h ; '0'
0x1400658b1  mov     r9, rbx
0x1400658b4  call    WPP_SF_q
0x1400658b9  or      dword ptr [rbx+78h], 2
0x1400658bd  xor     eax, eax
0x1400658bf  mov     dword ptr [rsp+98h+var_58], eax
0x1400658c3  mov     [rsp+98h+var_58+8], 0
0x1400658cc  cmp     byte ptr [rsi+40h], 1
0x1400658d0  jnz     short loc_1400658DC
0x1400658d2  mov     edi, 0C0000010h
0x1400658d7  jmp     loc_140065C3F
0x1400658dc  cmp     byte ptr [rbx+20h], 0Eh
0x1400658e0  mov     [rsp+98h+arg_10], rbp
0x1400658e8  mov     rbp, [rsi+70h]
0x1400658ec  mov     [rsp+98h+var_20], r14
0x1400658f1  mov     [rsp+98h+var_28], r15
0x1400658f6  jnz     loc_140065AF5
0x1400658fc  mov     r15, [rdi+20h]
0x140065900  mov     ecx, 42h ; 'B'
0x140065905  mov     [rbx+20h], al
0x140065908  mov     r8d, 334D7852h
0x14006590e  movzx   edx, word ptr [r15+18h]
0x140065913  call    cs:__imp_ExAllocatePool2
0x14006591a  nop     dword ptr [rax+rax+00h]
0x14006591f  lea     r14, [rbx+1C8h]
0x140065926  mov     [r14], rax
0x140065929  test    rax, rax
0x14006592c  jnz     short loc_140065938
0x14006592e  mov     edi, 0C000009Ah
0x140065933  jmp     loc_140065BB7
0x140065938  movzx   r8d, word ptr [r15+18h]; Size
0x14006593d  mov     rcx, rax; void *
0x140065940  mov     rdx, [r15+20h]; Src
0x140065944  call    memmove
0x140065949  movzx   eax, word ptr [r15+18h]
0x14006594e  lea     rcx, [rbx+200h]; void *
0x140065955  movzx   edi, byte ptr [rbx+2EEh]
0x14006595c  xor     edx, edx; Val
0x14006595e  mov     [rbx+1C0h], ax
0x140065965  mov     r8d, 0EEh; Size
0x14006596b  mov     rax, [r15+38h]
0x14006596f  mov     [rbx+1E0h], rax
0x140065976  call    memset
0x14006597b  lea     rcx, [rbx+2EFh]; void *
0x140065982  xor     edx, edx; Val
0x140065984  mov     r8d, 69h ; 'i'; Size
0x14006598a  call    memset
0x14006598f  mov     rax, [rbx+50h]
0x140065993  and     dil, 10h
0x140065997  mov     [rbx+2EEh], dil
0x14006599e  test    dword ptr [rax+150h], 2000h
0x1400659a8  jz      short loc_1400659E6
0x1400659aa  mov     rcx, [r15+40h]
0x1400659ae  call    cs:__imp_PsGetEffectiveServerSilo
0x1400659b5  nop     dword ptr [rax+rax+00h]
0x1400659ba  mov     rcx, rax
0x1400659bd  mov     rdi, rax
0x1400659c0  call    cs:__imp_PsIsHostSilo
0x1400659c7  nop     dword ptr [rax+rax+00h]
0x1400659cc  test    al, al
0x1400659ce  jnz     short loc_1400659E6
0x1400659d0  mov     rcx, rdi
0x1400659d3  call    RxGetSiloFromServerSilo
0x1400659d8  mov     [rbx+348h], rax
0x1400659df  mov     [rbx+270h], rdi
0x1400659e6  or      byte ptr [rbx+2EDh], 28h
0x1400659ed  mov     rax, [r15]
0x1400659f0  mov     [rbx+220h], rax
0x1400659f7  mov     rax, [r15]
0x1400659fa  mov     edx, [rax+14h]
0x1400659fd  movzx   eax, byte ptr [rbx+2EEh]
0x140065a04  and     edx, 0FFFFFFh
0x140065a0a  and     al, 0FBh
0x140065a0c  mov     ecx, edx
0x140065a0e  shr     ecx, 8
0x140065a11  btr     edx, 0Ah
0x140065a15  mov     [rbx+21Ch], edx
0x140065a1b  and     cl, 4
0x140065a1e  or      cl, al
0x140065a20  mov     [rbx+2EEh], cl
0x140065a26  mov     rax, [r15+10h]
0x140065a2a  mov     [rbx+2B8h], rax
0x140065a31  mov     eax, [r15+8]
0x140065a35  mov     [rbx+2C8h], eax
0x140065a3b  cmp     qword ptr [r15+30h], 0
0x140065a40  jz      loc_140065AD2
0x140065a46  movzx   edx, word ptr [r15+28h]
0x140065a4b  mov     ecx, 40h ; '@'
0x140065a50  add     rdx, 4
0x140065a54  mov     r8d, 334D7852h
0x140065a5a  call    cs:__imp_ExAllocatePool2
0x140065a61  nop     dword ptr [rax+rax+00h]
0x140065a66  mov     [rbx+2A8h], rax
0x140065a6d  mov     rcx, rax
0x140065a70  test    rax, rax
0x140065a73  jnz     short loc_140065A7F
0x140065a75  mov     edi, 0C000009Ah
0x140065a7a  jmp     loc_140065BB7
0x140065a7f  movzx   eax, word ptr [r15+28h]
0x140065a84  mov     [rcx], ax
0x140065a87  mov     rcx, [rbx+2A8h]
0x140065a8e  movzx   r8d, word ptr [r15+28h]; Size
0x140065a93  add     rcx, 2; void *
0x140065a97  mov     rdx, [r15+30h]; Src
0x140065a9b  call    memmove
0x140065aa0  mov     rcx, cs:WPP_GLOBAL_Control
0x140065aa7  cmp     rcx, r13
0x140065aaa  jz      short loc_140065AD2
0x140065aac  mov     eax, [rcx+2Ch]
0x140065aaf  test    al, 8
0x140065ab1  jz      short loc_140065AD2
0x140065ab3  cmp     byte ptr [rcx+29h], 4
0x140065ab7  jb      short loc_140065AD2
0x140065ab9  mov     rcx, [rcx+18h]
0x140065abd  lea     r9, [r15+28h]
0x140065ac1  mov     edx, 31h ; '1'
0x140065ac6  lea     r8, WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids
0x140065acd  call    WPP_SF_Z
0x140065ad2  mov     rdx, [rbx+1E0h]
0x140065ad9  mov     rcx, rbx
0x140065adc  call    RxInitializeSMBTreeConnectEcp
0x140065ae1  mov     rcx, rbx
0x140065ae4  call    RxFindOrInitializeNetworkCreateEcp
0x140065ae9  mov     edi, eax
0x140065aeb  test    eax, eax
0x140065aed  js      loc_140065B96
0x140065af3  jmp     short loc_140065AFC
0x140065af5  lea     r14, [rbx+1C8h]
0x140065afc  movups  xmm0, xmmword ptr [rbx+1C0h]
0x140065b03  lea     rax, [rsp+98h+arg_0]
0x140065b0b  mov     rdx, rsi
0x140065b0e  lea     r9, [rsp+98h+CanonicalName]
0x140065b13  mov     qword ptr [rsp+98h+var_78], rax
0x140065b18  lea     r8, [rsp+98h+var_48]
0x140065b1d  movaps  [rsp+98h+var_48], xmm0
0x140065b22  mov     rcx, rbx
0x140065b25  movdqa  xmmword ptr [rsp+98h+var_58], xmm0
0x140065b2b  call    RxFirstCanonicalize
0x140065b30  mov     edi, eax
0x140065b32  test    eax, eax
0x140065b34  js      short loc_140065B96
0x140065b36  test    byte ptr [rbx+2EEh], 4
0x140065b3d  jz      short loc_140065B52
0x140065b3f  mov     rax, [rbx+50h]
0x140065b43  mov     ecx, [rax+150h]
0x140065b49  test    cl, 20h
0x140065b4c  jz      short loc_140065B52
0x140065b4e  mov     cl, 1
0x140065b50  jmp     short loc_140065B54
0x140065b52  xor     cl, cl
0x140065b54  mov     eax, [rbx+21Ch]
0x140065b5a  test    al, al
0x140065b5c  jns     short loc_140065B66
0x140065b5e  test    cl, cl
0x140065b60  jz      short loc_140065B66
0x140065b62  mov     al, 1
0x140065b64  jmp     short loc_140065B68
0x140065b66  xor     al, al
0x140065b68  movzx   r9d, [rsp+98h+arg_0]
0x140065b71  lea     rcx, [rsp+98h+var_58]
0x140065b76  mov     [rsp+98h+var_68], rcx; __int64
0x140065b7b  lea     r8, [rsp+98h+CanonicalName]; CanonicalName
0x140065b80  mov     [rsp+98h+var_70], 0; char
0x140065b85  mov     rcx, rbx; RxContext
0x140065b88  mov     rdx, rsi; Irp
0x140065b8b  mov     [rsp+98h+var_78], al; char
0x140065b8f  call    RxFindOrConstructVirtualNetRootWithRetry
0x140065b94  mov     edi, eax
0x140065b96  cmp     edi, 103h
0x140065b9c  jz      loc_140065C2D
0x140065ba2  test    edi, edi
0x140065ba4  js      short loc_140065BB7
0x140065ba6  movzx   ecx, word ptr [rbx+1C0h]
0x140065bad  movzx   eax, word ptr [rsp+98h+var_58]
0x140065bb2  sub     ecx, eax
0x140065bb4  mov     [rbp+0], ecx
0x140065bb7  cmp     byte ptr [rbx+20h], 0
0x140065bbb  jnz     short loc_140065C2D
0x140065bbd  mov     rcx, [r14]; P
0x140065bc0  test    rcx, rcx
0x140065bc3  jz      short loc_140065BDA
0x140065bc5  xor     edx, edx; Tag
0x140065bc7  call    cs:__imp_ExFreePoolWithTag
0x140065bce  nop     dword ptr [rax+rax+00h]
0x140065bd3  mov     qword ptr [r14], 0
0x140065bda  mov     rcx, [rbx+2A8h]; P
0x140065be1  test    rcx, rcx
0x140065be4  jz      short loc_140065BFF
0x140065be6  xor     edx, edx; Tag
0x140065be8  call    cs:__imp_ExFreePoolWithTag
0x140065bef  nop     dword ptr [rax+rax+00h]
0x140065bf4  mov     qword ptr [rbx+2A8h], 0
0x140065bff  cmp     qword ptr [rbx+1E0h], 0
0x140065c07  jnz     short loc_140065C21
0x140065c09  mov     rcx, [rbx+2A0h]; EcpContext
0x140065c10  test    rcx, rcx
0x140065c13  jz      short loc_140065C21
0x140065c15  call    cs:__imp_FsRtlFreeExtraCreateParameter
0x140065c1c  nop     dword ptr [rax+rax+00h]
0x140065c21  mov     rcx, rbx
0x140065c24  call    RxpFinalizeCreateContext
0x140065c29  mov     byte ptr [rbx+20h], 0Eh
0x140065c2d  mov     r14, [rsp+98h+var_20]
0x140065c32  mov     rbp, [rsp+98h+arg_10]
0x140065c3a  mov     r15, [rsp+98h+var_28]
0x140065c3f  mov     rcx, cs:WPP_GLOBAL_Control
0x140065c46  mov     rsi, [rsp+98h+var_10]
0x140065c4e  cmp     rcx, r13
0x140065c51  mov     r13, [rsp+98h+var_18]
0x140065c59  mov     rbx, [rsp+98h+arg_8]
0x140065c61  jz      short loc_140065C88
0x140065c63  mov     eax, [rcx+2Ch]
0x140065c66  test    al, 8
0x140065c68  jz      short loc_140065C88
0x140065c6a  cmp     byte ptr [rcx+29h], 2
0x140065c6e  jb      short loc_140065C88
0x140065c70  mov     rcx, [rcx+18h]
0x140065c74  lea     r8, WPP_fbbfb4a06e683304bfd4095949c06444_Traceguids
0x140065c7b  mov     edx, 32h ; '2'
0x140065c80  mov     r9d, edi
0x140065c83  call    WPP_SF_d
0x140065c88  mov     eax, edi
0x140065c8a  add     rsp, 90h
0x140065c91  pop     rdi
0x140065c92  retn
```
