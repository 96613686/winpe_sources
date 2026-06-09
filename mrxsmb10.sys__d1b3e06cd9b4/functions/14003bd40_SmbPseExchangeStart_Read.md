# SmbPseExchangeStart_Read

- ea: `0x14003bd40`
- end: `0x14003c227`
- name: `SmbPseExchangeStart_Read`
- size: `1255`
- prototype: `__int64 __fastcall(PVOID pContext, PRX_CONTEXT RxContext)`
- caller_count: `0`
- callee_count: `13`
- tags: `broker_com_uri`

## callees

- `0x14000b120`
- `0x14000dfa8`
- `0x14000dfd8`
- `0x14000f0d0`
- `0x14003b980`
- `0x14003bd40`
- `0x140042fd4`
- `0x140045d50`
- `0x140046120`
- `0x140046a50`
- `0x14004ee60`
- `0x14004f820`
- `0x140053c10`

## import_xrefs

- `ntoskrnl!MmUnmapLockedPages` at `0x14003c020`
- `ntoskrnl!MmUnmapLockedPages` at `0x14003c1d4`
- `ntoskrnl!MmUnmapLockedPages` at `0x14003c020`
- `ntoskrnl!MmUnmapLockedPages` at `0x14003c1d4`
- `ntoskrnl!IoFreeMdl` at `0x14003c1e2`
- `ntoskrnl!IoFreeMdl` at `0x14003c1e2`
- `rdbss!RxLowIoGetBufferAddress` at `0x14003be12`
- `rdbss!RxLowIoGetBufferAddress` at `0x14003be12`
- `rdbss!RxLowIoCompletion` at `0x14003c20c`
- `rdbss!RxLowIoCompletion` at `0x14003c20c`
- `mrxsmb!MRxSmbLegacyPerfCtrs` at `0x14003befd`

## pseudocode

```c
__int64 __fastcall SmbPseExchangeStart_Read(char *pContext, PRX_CONTEXT RxContext, __int64 a3, __int64 a4)
{
  __int64 v4; // r12
  char *v5; // r15
  PMRX_FCB pFcb; // r14
  PMRX_FOBX pFobx; // r13
  __int64 v10; // rdx
  __int64 ExchangeSession; // rdi
  int v12; // ebp
  int v13; // eax
  unsigned int Request; // edi
  int v15; // ecx
  unsigned int v16; // eax
  int v17; // eax
  unsigned int v18; // ecx
  __int64 v19; // rax
  __int64 v21; // rcx
  unsigned int v22; // [rsp+70h] [rbp+8h]
  __int64 v23; // [rsp+78h] [rbp+10h]

  v4 = *((_QWORD *)pContext + 10);
  v5 = pContext + 888;
  pFcb = RxContext->pFcb;
  pFobx = RxContext->pFobx;
  ExchangeSession = SmbCeGetExchangeSession(pContext, RxContext, a3, a4);
  v12 = *(_DWORD *)(v10 + 120) & 0x1000;
  v23 = ExchangeSession;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_f246e64eea833cb58dbbe2117b998014_Traceguids);
  v22 = ++*((_DWORD *)pContext + 93);
  *((_WORD *)pContext + 192) |= 4u;
  while ( 1 )
  {
    while ( pContext[387] )
    {
      if ( pContext[387] == 1 )
        goto LABEL_15;
      if ( pContext[387] == 2 )
        goto LABEL_22;
    }
    pContext[387] = 1;
    if ( v12 )
      *((_QWORD *)pContext + 53) = SmbPseExchangeStart_Read;
    MRxSmbSetInitialSMB(v5);
    *((_QWORD *)pContext + 59) = RxLowIoGetBufferAddress(RxContext);
    *((_QWORD *)pContext + 63) = RxContext->Create.TransportName.Buffer;
    *((_DWORD *)pContext + 122) = *((_DWORD *)&RxContext->9 + 42);
    if ( *(_BYTE *)(*(_QWORD *)&pFcb->UncleanCount + 77LL) == 1 && pFobx[1].pSrvOpen->NodeReferenceCount )
      pContext[386] |= 0x80u;
    *((_DWORD *)pContext + 125) = 0;
    *((_WORD *)pContext + 258) = 0;
    *((_QWORD *)pContext + 65) = 0;
LABEL_15:
    v13 = MRxSmbReadSendOptions;
    pContext[386] &= ~1u;
    *((_DWORD *)pContext + 98) = v13;
    pContext[387] = 2;
    Request = MRxSmbBuildReadRequest(pContext);
    if ( Request )
      break;
    if ( (RxContext->Create.PipeCompletionMode & 1) != 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    {
      WPP_SF_qqL(
        WPP_GLOBAL_Control->AttachedDevice,
        Request + 15,
        WPP_f246e64eea833cb58dbbe2117b998014_Traceguids,
        RxContext,
        pContext + 504,
        *((_DWORD *)pContext + 124));
    }
    _InterlockedIncrement((volatile signed __int32 *)(((unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 8)
                                                    + MRxSmbLegacyPerfCtrs
                                                    + 112));
    Request = SmbPseOrdinaryExchange(pContext);
    if ( Request == 259 )
      goto LABEL_57;
    ExchangeSession = v23;
LABEL_22:
    v15 = *((_DWORD *)pContext + 10);
    pContext[387] = 1;
    *((_DWORD *)pContext + 12) = v15;
    if ( v15 == -1069481983 )
    {
      SmbCeUninitializeExchangeTransport(pContext);
      SmbCeReconnect(*((PVOID *)pContext + 11));
      Request = v16;
      if ( v16 )
        goto LABEL_64;
      *((_DWORD *)pContext + 128) = 0;
      *((_DWORD *)pContext + 10) = 0;
      Request = SmbCeInitializeExchangeTransport(pContext);
      if ( Request )
        goto LABEL_64;
    }
    else if ( v15
           && ((*(_DWORD *)(ExchangeSession + 8) & 8) != 0 || *(_BYTE *)(v4 + 640))
           && (v15 == -1073741643
            || v15 == -1073741636
            || v15 == -1073741634
            || v15 == -1073741309
            || v15 == -1073741300
            || v15 == -1073741252) )
    {
      v17 = SmbCeRemoteBootReconnect(pContext, RxContext);
      *((_DWORD *)pContext + 12) = -1069481983;
      if ( v17 )
      {
        Request = -1069481983;
        *((_DWORD *)pContext + 10) = -1069481983;
LABEL_56:
        RxContext->InformationToReturn = 0;
        goto LABEL_57;
      }
      *((_DWORD *)pContext + 10) = 0;
      SmbCeInitializeExchangeTransport(pContext);
      *((_DWORD *)pContext + 128) = 0;
    }
    v18 = *((_DWORD *)pContext + 128);
    if ( v18 )
    {
      if ( pContext[517] )
      {
        if ( (pContext[538] & 0x20) != 0 )
        {
          MmUnmapLockedPages(*((PVOID *)pContext + 69), (PMDL)pContext + 11);
          v18 = *((_DWORD *)pContext + 128);
        }
        pContext[517] = 0;
      }
    }
    else if ( !*((_DWORD *)pContext + 12) )
    {
      if ( *(_BYTE *)(*(_QWORD *)&pFcb->UncleanCount + 77LL) == 1 )
        *((_DWORD *)pContext + 12) = -1073741607;
      else
        *((_DWORD *)pContext + 12) = -1073741807;
    }
    *((_DWORD *)pContext + 122) -= v18;
    if ( *((_DWORD *)pContext + 12) == -1073741807 && RxContext->InformationToReturn )
    {
      *((_DWORD *)pContext + 12) = 0;
      *((_DWORD *)pContext + 122) = 0;
    }
    RxContext->InformationToReturn += v18;
    Request = *((_DWORD *)pContext + 12);
    if ( Request != -1069481983
      && ((Request & 0xC0000000) == 0xC0000000
       || !*((_DWORD *)pContext + 122)
       || *(_BYTE *)(*(_QWORD *)&pFcb->UncleanCount + 77LL) && Request != -2147483643) )
    {
      goto LABEL_64;
    }
    v19 = *((unsigned int *)pContext + 128);
    *((_QWORD *)pContext + 63) += v19;
    *((_DWORD *)pContext + 125) += v19;
    *((_DWORD *)pContext + 128) = 0;
    MRxSmbSetInitialSMB(v5);
    ExchangeSession = v23;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_f246e64eea833cb58dbbe2117b998014_Traceguids);
LABEL_64:
  if ( Request != 259 )
  {
    if ( Request == -1069481983 )
      goto LABEL_56;
    if ( v22 > 1 )
    {
      v21 = *((_QWORD *)pContext + 47);
      if ( v21 )
      {
        if ( _bittest16((const signed __int16 *)pContext + 192, 9u) )
        {
          if ( (*(_BYTE *)(v21 + 10) & 0x20) != 0 )
            MmUnmapLockedPages(*(PVOID *)(v21 + 24), *((PMDL *)pContext + 47));
        }
        else
        {
          IoFreeMdl((PMDL)v21);
          *((_WORD *)pContext + 192) &= ~0x10u;
          *((_QWORD *)pContext + 47) = 0;
        }
      }
      RxContext->StoredStatus = Request;
      RxLowIoCompletion(RxContext);
      SmbPseFinalizeOrdinaryExchange((unsigned __int8 *)pContext);
      Request = 259;
    }
  }
LABEL_57:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_f246e64eea833cb58dbbe2117b998014_Traceguids, Request);
  return Request;
}

```

## disassembly

```asm
0x14003bd40  mov     [rsp+arg_10], rbx
0x14003bd45  push    rbp
0x14003bd46  push    rsi
0x14003bd47  push    rdi
0x14003bd48  push    r12
0x14003bd4a  push    r13
0x14003bd4c  push    r14
0x14003bd4e  push    r15
0x14003bd50  sub     rsp, 30h
0x14003bd54  mov     r12, [rcx+50h]
0x14003bd58  lea     r15, [rcx+378h]
0x14003bd5f  mov     r14, [rdx+38h]
0x14003bd63  mov     rsi, rdx
0x14003bd66  mov     r13, [rdx+40h]
0x14003bd6a  mov     rbx, rcx
0x14003bd6d  call    SmbCeGetExchangeSession
0x14003bd72  mov     ebp, [rdx+78h]
0x14003bd75  mov     rdi, rax
0x14003bd78  and     ebp, 1000h
0x14003bd7e  mov     [rsp+68h+arg_8], rax
0x14003bd83  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003bd8a  lea     rax, WPP_GLOBAL_Control
0x14003bd91  cmp     rcx, rax
0x14003bd94  jz      short loc_14003BDB4
0x14003bd96  test    dword ptr [rcx+2Ch], 400h
0x14003bd9d  jz      short loc_14003BDB4
0x14003bd9f  mov     rcx, [rcx+18h]
0x14003bda3  lea     r8, WPP_f246e64eea833cb58dbbe2117b998014_Traceguids
0x14003bdaa  mov     edx, 0Dh
0x14003bdaf  call    WPP_SF_
0x14003bdb4  inc     dword ptr [rbx+174h]
0x14003bdba  mov     eax, [rbx+174h]
0x14003bdc0  mov     [rsp+68h+arg_0], eax
0x14003bdc4  mov     eax, 4
0x14003bdc9  or      [rbx+180h], ax
0x14003bdd0  movzx   ecx, byte ptr [rbx+183h]
0x14003bdd7  test    ecx, ecx
0x14003bdd9  jz      short loc_14003BDEE
0x14003bddb  sub     ecx, 1
0x14003bdde  jz      loc_14003BE75
0x14003bde4  cmp     ecx, 1
0x14003bde7  jnz     short loc_14003BDD0
0x14003bde9  jmp     loc_14003BF33
0x14003bdee  mov     byte ptr [rbx+183h], 1
0x14003bdf5  test    ebp, ebp
0x14003bdf7  jz      short loc_14003BE07
0x14003bdf9  lea     rax, SmbPseExchangeStart_Read
0x14003be00  mov     [rbx+1A8h], rax
0x14003be07  mov     rcx, r15
0x14003be0a  call    MRxSmbSetInitialSMB
0x14003be0f  mov     rcx, rsi; RxContext
0x14003be12  call    cs:__imp_RxLowIoGetBufferAddress
0x14003be19  nop     dword ptr [rax+rax+00h]
0x14003be1e  mov     [rbx+1D8h], rax
0x14003be25  xor     ecx, ecx
0x14003be27  mov     rax, [rsi+230h]
0x14003be2e  mov     [rbx+1F8h], rax
0x14003be35  mov     eax, [rsi+238h]
0x14003be3b  mov     [rbx+1E8h], eax
0x14003be41  mov     rax, [r14+78h]
0x14003be45  cmp     byte ptr [rax+4Dh], 1
0x14003be49  jnz     short loc_14003BE5B
0x14003be4b  mov     rax, [r13+50h]
0x14003be4f  cmp     [rax+4], ecx
0x14003be52  jz      short loc_14003BE5B
0x14003be54  or      byte ptr [rbx+182h], 80h
0x14003be5b  mov     [rbx+1F4h], ecx
0x14003be61  mov     word ptr [rbx+204h], 0
0x14003be6a  mov     qword ptr [rbx+208h], 0
0x14003be75  mov     eax, cs:MRxSmbReadSendOptions
0x14003be7b  mov     rcx, rbx
0x14003be7e  and     byte ptr [rbx+182h], 0FEh
0x14003be85  mov     [rbx+188h], eax
0x14003be8b  mov     byte ptr [rbx+183h], 2
0x14003be92  call    MRxSmbBuildReadRequest
0x14003be97  mov     edi, eax
0x14003be99  test    eax, eax
0x14003be9b  jnz     loc_14003C15B
0x14003bea1  mov     eax, [rsi+218h]
0x14003bea7  test    al, 1
0x14003bea9  jz      short loc_14003BEF3
0x14003beab  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003beb2  lea     rax, WPP_GLOBAL_Control
0x14003beb9  cmp     rcx, rax
0x14003bebc  jz      short loc_14003BEF3
0x14003bebe  test    dword ptr [rcx+2Ch], 200h
0x14003bec5  jz      short loc_14003BEF3
0x14003bec7  mov     eax, [rbx+1F0h]
0x14003becd  lea     r8, [rbx+1F8h]
0x14003bed4  mov     rcx, [rcx+18h]
0x14003bed8  lea     edx, [rdi+0Fh]
0x14003bedb  mov     [rsp+68h+var_40], eax
0x14003bedf  mov     r9, rsi
0x14003bee2  mov     [rsp+68h+var_48], r8
0x14003bee7  lea     r8, WPP_f246e64eea833cb58dbbe2117b998014_Traceguids
0x14003beee  call    WPP_SF_qqL
0x14003bef3  mov     eax, gs:1A4h
0x14003befb  mov     edx, eax
0x14003befd  mov     rax, cs:__imp_MRxSmbLegacyPerfCtrs
0x14003bf04  shl     rdx, 8
0x14003bf08  mov     rcx, [rax]
0x14003bf0b  lock inc dword ptr [rdx+rcx+70h]
0x14003bf10  mov     r8d, 4
0x14003bf16  mov     rdx, rsi
0x14003bf19  mov     rcx, rbx; pContext
0x14003bf1c  call    SmbPseOrdinaryExchange
0x14003bf21  mov     edi, eax
0x14003bf23  cmp     eax, 103h
0x14003bf28  jz      loc_14003C10C
0x14003bf2e  mov     rdi, [rsp+68h+arg_8]
0x14003bf33  mov     ecx, [rbx+28h]
0x14003bf36  mov     byte ptr [rbx+183h], 1
0x14003bf3d  mov     [rbx+30h], ecx
0x14003bf40  cmp     ecx, 0C0410001h
0x14003bf46  jnz     short loc_14003BF80
0x14003bf48  mov     rcx, rbx
0x14003bf4b  call    SmbCeUninitializeExchangeTransport
0x14003bf50  mov     rcx, [rbx+58h]; Context
0x14003bf54  call    SmbCeReconnect
0x14003bf59  mov     edi, eax
0x14003bf5b  test    eax, eax
0x14003bf5d  jnz     loc_14003C18C
0x14003bf63  mov     [rbx+200h], eax
0x14003bf69  mov     rcx, rbx
0x14003bf6c  mov     [rbx+28h], eax
0x14003bf6f  call    SmbCeInitializeExchangeTransport
0x14003bf74  mov     edi, eax
0x14003bf76  test    eax, eax
0x14003bf78  jnz     loc_14003C18C
0x14003bf7e  jmp     short loc_14003BFF6
0x14003bf80  test    ecx, ecx
0x14003bf82  jz      short loc_14003BFF6
0x14003bf84  mov     eax, [rdi+8]
0x14003bf87  test    al, 8
0x14003bf89  jnz     short loc_14003BF96
0x14003bf8b  cmp     byte ptr [r12+280h], 0
0x14003bf94  jz      short loc_14003BFF6
0x14003bf96  cmp     ecx, 0C00000B5h
0x14003bf9c  jz      short loc_14003BFC6
0x14003bf9e  cmp     ecx, 0C00000BCh
0x14003bfa4  jz      short loc_14003BFC6
0x14003bfa6  cmp     ecx, 0C00000BEh
0x14003bfac  jz      short loc_14003BFC6
0x14003bfae  cmp     ecx, 0C0000203h
0x14003bfb4  jz      short loc_14003BFC6
0x14003bfb6  cmp     ecx, 0C000020Ch
0x14003bfbc  jz      short loc_14003BFC6
0x14003bfbe  cmp     ecx, 0C000023Ch
0x14003bfc4  jnz     short loc_14003BFF6
0x14003bfc6  mov     rdx, rsi
0x14003bfc9  mov     rcx, rbx
0x14003bfcc  call    SmbCeRemoteBootReconnect
0x14003bfd1  mov     ecx, 0C0410001h
0x14003bfd6  mov     [rbx+30h], ecx
0x14003bfd9  test    eax, eax
0x14003bfdb  jnz     loc_14003C0FC
0x14003bfe1  mov     rcx, rbx
0x14003bfe4  mov     [rbx+28h], eax
0x14003bfe7  call    SmbCeInitializeExchangeTransport
0x14003bfec  mov     dword ptr [rbx+200h], 0
0x14003bff6  mov     ecx, [rbx+200h]
0x14003bffc  test    ecx, ecx
0x14003bffe  jz      short loc_14003C03B
0x14003c000  cmp     byte ptr [rbx+205h], 0
0x14003c007  jz      short loc_14003C05B
0x14003c009  test    byte ptr [rbx+21Ah], 20h
0x14003c010  jz      short loc_14003C032
0x14003c012  lea     rcx, [rbx+210h]
0x14003c019  mov     rdx, rcx; MemoryDescriptorList
0x14003c01c  mov     rcx, [rcx+18h]; BaseAddress
0x14003c020  call    cs:__imp_MmUnmapLockedPages
0x14003c027  nop     dword ptr [rax+rax+00h]
0x14003c02c  mov     ecx, [rbx+200h]
0x14003c032  mov     byte ptr [rbx+205h], 0
0x14003c039  jmp     short loc_14003C05B
0x14003c03b  cmp     dword ptr [rbx+30h], 0
0x14003c03f  jnz     short loc_14003C05B
0x14003c041  mov     rax, [r14+78h]
0x14003c045  cmp     byte ptr [rax+4Dh], 1
0x14003c049  jnz     short loc_14003C054
0x14003c04b  mov     dword ptr [rbx+30h], 0C00000D9h
0x14003c052  jmp     short loc_14003C05B
0x14003c054  mov     dword ptr [rbx+30h], 0C0000011h
0x14003c05b  sub     [rbx+1E8h], ecx
0x14003c061  cmp     dword ptr [rbx+30h], 0C0000011h
0x14003c068  jnz     short loc_14003C085
0x14003c06a  cmp     qword ptr [rsi+0B8h], 0
0x14003c072  jbe     short loc_14003C085
0x14003c074  mov     dword ptr [rbx+30h], 0
0x14003c07b  mov     dword ptr [rbx+1E8h], 0
0x14003c085  mov     eax, ecx
0x14003c087  add     [rsi+0B8h], rax
0x14003c08e  mov     edi, [rbx+30h]
0x14003c091  cmp     edi, 0C0410001h
0x14003c097  jz      short loc_14003C0CD
0x14003c099  mov     ecx, 0C0000000h
0x14003c09e  mov     eax, edi
0x14003c0a0  and     eax, ecx
0x14003c0a2  cmp     eax, ecx
0x14003c0a4  jz      loc_14003C18C
0x14003c0aa  cmp     dword ptr [rbx+1E8h], 0
0x14003c0b1  jz      loc_14003C18C
0x14003c0b7  mov     rax, [r14+78h]
0x14003c0bb  cmp     byte ptr [rax+4Dh], 0
0x14003c0bf  jz      short loc_14003C0CD
0x14003c0c1  cmp     edi, 80000005h
0x14003c0c7  jnz     loc_14003C18C
0x14003c0cd  mov     eax, [rbx+200h]
0x14003c0d3  mov     rcx, r15
0x14003c0d6  add     [rbx+1F8h], rax
0x14003c0dd  add     [rbx+1F4h], eax
0x14003c0e3  mov     dword ptr [rbx+200h], 0
0x14003c0ed  call    MRxSmbSetInitialSMB
0x14003c0f2  mov     rdi, [rsp+68h+arg_8]
0x14003c0f7  jmp     loc_14003BDD0
0x14003c0fc  mov     edi, ecx
0x14003c0fe  mov     [rbx+28h], ecx
0x14003c101  mov     qword ptr [rsi+0B8h], 0
0x14003c10c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003c113  lea     rax, WPP_GLOBAL_Control
0x14003c11a  cmp     rcx, rax
0x14003c11d  jz      short loc_14003C140
0x14003c11f  test    dword ptr [rcx+2Ch], 400h
0x14003c126  jz      short loc_14003C140
0x14003c128  mov     rcx, [rcx+18h]
0x14003c12c  lea     r8, WPP_f246e64eea833cb58dbbe2117b998014_Traceguids
0x14003c133  mov     edx, 10h
0x14003c138  mov     r9d, edi
0x14003c13b  call    WPP_SF_d
0x14003c140  mov     rbx, [rsp+68h+arg_10]
0x14003c148  mov     eax, edi
0x14003c14a  add     rsp, 30h
0x14003c14e  pop     r15
0x14003c150  pop     r14
0x14003c152  pop     r13
0x14003c154  pop     r12
0x14003c156  pop     rdi
0x14003c157  pop     rsi
0x14003c158  pop     rbp
0x14003c159  retn
0x14003c15b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003c162  lea     rax, WPP_GLOBAL_Control
0x14003c169  cmp     rcx, rax
0x14003c16c  jz      short loc_14003C18C
0x14003c16e  test    dword ptr [rcx+2Ch], 400h
0x14003c175  jz      short loc_14003C18C
0x14003c177  mov     rcx, [rcx+18h]
0x14003c17b  lea     r8, WPP_f246e64eea833cb58dbbe2117b998014_Traceguids
0x14003c182  mov     edx, 0Eh
0x14003c187  call    WPP_SF_
0x14003c18c  mov     ebp, 103h
0x14003c191  cmp     edi, ebp
0x14003c193  jz      loc_14003C10C
0x14003c199  cmp     edi, 0C0410001h
0x14003c19f  jz      loc_14003C101
0x14003c1a5  cmp     [rsp+68h+arg_0], 1
0x14003c1aa  jbe     loc_14003C10C
0x14003c1b0  mov     rcx, [rbx+178h]; Mdl
0x14003c1b7  test    rcx, rcx
0x14003c1ba  jz      short loc_14003C203
0x14003c1bc  bt      word ptr [rbx+180h], 9
0x14003c1c5  jnb     short loc_14003C1E2
0x14003c1c7  test    byte ptr [rcx+0Ah], 20h
0x14003c1cb  jz      short loc_14003C203
0x14003c1cd  mov     rdx, rcx; MemoryDescriptorList
0x14003c1d0  mov     rcx, [rcx+18h]; BaseAddress
0x14003c1d4  call    cs:__imp_MmUnmapLockedPages
0x14003c1db  nop     dword ptr [rax+rax+00h]
0x14003c1e0  jmp     short loc_14003C203
0x14003c1e2  call    cs:__imp_IoFreeMdl
0x14003c1e9  nop     dword ptr [rax+rax+00h]
0x14003c1ee  xor     ecx, ecx
0x14003c1f0  mov     eax, 0FFEFh
0x14003c1f5  and     [rbx+180h], ax
0x14003c1fc  mov     [rbx+178h], rcx
0x14003c203  mov     rcx, rsi; RxContext
0x14003c206  mov     [rsi+0B0h], edi
0x14003c20c  call    cs:__imp_RxLowIoCompletion
0x14003c213  nop     dword ptr [rax+rax+00h]
0x14003c218  mov     rcx, rbx; pContext
0x14003c21b  call    SmbPseFinalizeOrdinaryExchange
0x14003c220  mov     edi, ebp
0x14003c222  jmp     loc_14003C10C
```
