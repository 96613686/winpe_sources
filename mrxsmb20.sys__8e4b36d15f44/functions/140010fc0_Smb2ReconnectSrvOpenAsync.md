# Smb2ReconnectSrvOpenAsync

- ea: `0x140010fc0`
- end: `0x140011440`
- name: `Smb2ReconnectSrvOpenAsync`
- size: `1152`
- prototype: `__int64 __fastcall(struct _MRX_SRV_OPEN_ *, __int64, char)`
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400108f0`
- `0x140010950`

## callees

- `0x140010fc0`
- `0x140028730`
- `0x14002a230`
- `0x14002a590`

## import_xrefs

- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x140011177`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x140011177`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x1400111cc`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x1400111cc`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x14001113a`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x14001113a`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x1400113fb`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x1400113fb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140011051`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400113e7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140011051`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400113e7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140011038`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400113ce`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140011038`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x1400113ce`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x1400111e6`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x1400111e6`
- `rdbss!RxCreateRxContext` at `0x140010ffa`
- `rdbss!RxCreateRxContext` at `0x140010ffa`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x14001140d`
- `rdbss!RxDereferenceAndDeleteRxContext_Real` at `0x14001140d`
- `mrxsmb!SmbCeAssociateExchangeWithCompoundingKeyEx` at `0x14001136f`
- `mrxsmb!SmbCeAssociateExchangeWithCompoundingKeyEx` at `0x14001136f`
- `mrxsmb!SmbCeInitiateExchange` at `0x1400113a8`
- `mrxsmb!SmbCeInitiateExchange` at `0x1400113a8`
- `mrxsmb!SmbCeInitializeExchange` at `0x14001133a`
- `mrxsmb!SmbCeInitializeExchange` at `0x14001133a`

## pseudocode

```c
__int64 __fastcall Smb2ReconnectSrvOpenAsync(struct _MRX_SRV_OPEN_ *a1, __int64 a2, char a3)
{
  __int64 v4; // rbp
  struct _RDBSS_DEVICE_OBJECT *v6; // rdx
  PRX_CONTEXT RxContext; // rbx
  int v9; // r8d
  PECP_LIST *v10; // rsi
  NTSTATUS ParameterList; // edi
  int v12; // edx
  PMRX_SRV_OPEN pRelevantSrvOpen; // rdi
  PMRX_FCB pFcb; // r14
  __int64 v15; // r15
  int v16; // edx
  PMRX_SHADOW_CALLDOWN DispatchRoutine; // rsi
  PDEVICE_OBJECT v18; // rcx
  volatile signed __int64 *v19; // rax
  PDEVICE_OBJECT v20; // rcx
  __int64 v21; // [rsp+80h] [rbp+8h] BYREF
  __int64 v22; // [rsp+88h] [rbp+10h]
  PVOID EcpContext; // [rsp+98h] [rbp+20h] BYREF

  v22 = a2;
  v4 = *(_QWORD *)&a1->Flags;
  v6 = (struct _RDBSS_DEVICE_OBJECT *)*((_QWORD *)a1->ShadowContext->DispatchRoutine + 3);
  EcpContext = 0;
  RxContext = RxCreateRxContext(0, v6, 0x80000002);
  if ( !RxContext )
    return 3221225626LL;
  ExAcquirePushLockExclusiveEx(v4 + 16, 0);
  *(_QWORD *)(v4 + 304) = RxContext;
  ExReleasePushLockExclusiveEx(v4 + 16, 0);
  LOWORD(RxContext->RealDevice) = 0;
  RxContext->pFcb = (PMRX_FCB)a1->Context2;
  RxContext->pRelevantSrvOpen = a1;
  RxContext->pFobx = 0;
  RxContext->CurrentIrp = 0;
  RxContext->CurrentIrpSp = 0;
  *(_QWORD *)&RxContext->TrackerHistory[0].Flags = a1->ShadowContext;
  RxContext->TrackerHistory[0].FileName = (PSZ)a1->ShadowContext->FastIoWrite;
  *(_QWORD *)&RxContext->TrackerHistory[0].AcquireRelease = *((_QWORD *)a1->ShadowContext->FastIoWrite + 4);
  WORD1(RxContext->TrackerHistory[4].FileName) = *(_WORD *)(v4 + 168);
  *((_OWORD *)&RxContext->9 + 7) = *(_OWORD *)(v4 + 72);
  *((_OWORD *)&RxContext->9 + 8) = *(_OWORD *)(v4 + 88);
  *((_OWORD *)&RxContext->9 + 9) = *(_OWORD *)(v4 + 104);
  *((_OWORD *)&RxContext->9 + 10) = *(_OWORD *)(v4 + 120);
  *((_OWORD *)&RxContext->9 + 11) = *(_OWORD *)(v4 + 136);
  RxContext->Create.Password.Buffer = *(PWSTR *)(v4 + 152);
  *(_QWORD *)&RxContext->TrackerHistory[7].AcquireRelease = *(_QWORD *)(v4 + 160);
  if ( (*(_DWORD *)(v4 + 8) & 4) == 0 && (*(_BYTE *)(v4 + 170) || *(_BYTE *)(v4 + 171)) )
  {
    v10 = (PECP_LIST *)&RxContext->TrackerHistory[2];
    ParameterList = FsRtlAllocateExtraCreateParameterList(0, (PECP_LIST *)&RxContext->TrackerHistory[2]);
    if ( ParameterList < 0 )
      goto LABEL_28;
    ParameterList = FsRtlAllocateExtraCreateParameter(
                      &GUID_ECP_ENABLE_REDIRECTIONGUARD,
                      4u,
                      0,
                      0,
                      0x6D537843u,
                      &EcpContext);
    if ( ParameterList < 0 )
      goto LABEL_28;
    v12 = *(_DWORD *)EcpContext ^ ((unsigned __int8)*(_DWORD *)EcpContext ^ *(_BYTE *)(v4 + 170)) & 1;
    *(_DWORD *)EcpContext = v12;
    *(_DWORD *)EcpContext = v12 ^ ((unsigned __int8)v12 ^ (unsigned __int8)(2 * *(_BYTE *)(v4 + 171))) & 2;
    ParameterList = FsRtlInsertExtraCreateParameter(*v10, EcpContext);
    if ( ParameterList < 0 )
    {
      FsRtlFreeExtraCreateParameter(EcpContext);
LABEL_29:
      ExAcquirePushLockExclusiveEx(v4 + 16, 0);
      *(_QWORD *)(v4 + 304) = 0;
      ExReleasePushLockExclusiveEx(v4 + 16, 0);
      if ( *v10 )
      {
        FsRtlFreeExtraCreateParameterList(*v10);
        *v10 = 0;
      }
      RxDereferenceAndDeleteRxContext_Real(RxContext);
      return (unsigned int)ParameterList;
    }
  }
  pRelevantSrvOpen = RxContext->pRelevantSrvOpen;
  pFcb = RxContext->pFcb;
  v15 = *(_QWORD *)&pRelevantSrvOpen->Flags;
  v16 = (_DWORD)pFcb + 360;
  DispatchRoutine = pRelevantSrvOpen->ShadowContext->DispatchRoutine;
  v21 = 0;
  if ( (*(_DWORD *)(v15 + 8) & 4) != 0 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qiZ(
        WPP_GLOBAL_Control->AttachedDevice,
        v16,
        v9,
        (_DWORD)pRelevantSrvOpen,
        *(_QWORD *)(v15 + 28),
        (__int64)&pFcb[2].Header.Resource);
    }
    if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x100) != 0 )
      McTemplateK0pp_EtwWriteTransfer(v18, SmbReconnect, &RxContext->LowIoContext.Flags + 1, pFcb, pRelevantSrvOpen);
    v19 = (volatile signed __int64 *)((char *)DispatchRoutine + 512);
  }
  else
  {
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qDDZ(
        WPP_GLOBAL_Control->AttachedDevice,
        v16,
        v9,
        (_DWORD)pRelevantSrvOpen,
        *((_DWORD *)&RxContext->9 + 28),
        RxContext->Create.PipeReadMode,
        (__int64)&pFcb[2].Header.Resource);
    }
    if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x100) != 0 )
      McTemplateK0pp_EtwWriteTransfer(v20, SmbUndeferOpen, &RxContext->LowIoContext.Flags + 1, pFcb, pRelevantSrvOpen);
    v19 = (volatile signed __int64 *)((char *)DispatchRoutine + 504);
  }
  _InterlockedIncrement64(v19);
  v21 = 0;
  ParameterList = SmbCeInitializeExchange(&v21, RxContext, 0, 0, 0, DispatchRoutine, 2424, &ReconnectOpenDispatch);
  if ( !ParameterList )
  {
    _InterlockedOr((volatile signed __int32 *)(v21 + 68), 0x2080u);
    SmbCeAssociateExchangeWithCompoundingKeyEx(v21, v22, 0);
    *(_BYTE *)(v21 + 2416) = a3;
    *(_BYTE *)(v21 + 1016) = *(_BYTE *)(v15 + 328);
    ParameterList = SmbCeInitiateExchange(v21);
  }
  v10 = (PECP_LIST *)&RxContext->TrackerHistory[2];
LABEL_28:
  if ( ParameterList != 259 )
    goto LABEL_29;
  return (unsigned int)ParameterList;
}

```

## disassembly

```asm
0x140010fc0  mov     [rsp+arg_8], rdx
0x140010fc5  push    rbx
0x140010fc6  push    rbp
0x140010fc7  push    rdi
0x140010fc8  push    r13
0x140010fca  push    r15
0x140010fcc  sub     rsp, 50h
0x140010fd0  mov     rax, [rcx+28h]
0x140010fd4  movzx   r13d, r8b
0x140010fd8  mov     rbp, [rcx+30h]
0x140010fdc  mov     rdi, rcx
0x140010fdf  xor     r15d, r15d
0x140010fe2  xor     ecx, ecx; Irp
0x140010fe4  mov     r8d, 80000002h; InitialContextFlags
0x140010fea  mov     r9, [rax+28h]
0x140010fee  mov     rdx, [r9+18h]; RxDeviceObject
0x140010ff2  mov     [rsp+78h+arg_18], r15
0x140010ffa  call    cs:__imp_RxCreateRxContext
0x140011001  nop     dword ptr [rax+rax+00h]
0x140011006  mov     rbx, rax
0x140011009  test    rax, rax
0x14001100c  jnz     short loc_140011020
0x14001100e  mov     eax, 0C000009Ah
0x140011013  add     rsp, 50h
0x140011017  pop     r15
0x140011019  pop     r13
0x14001101b  pop     rdi
0x14001101c  pop     rbp
0x14001101d  pop     rbx
0x14001101e  retn
0x140011020  mov     [rsp+78h+arg_10], rsi
0x140011028  lea     rcx, [rbp+10h]
0x14001102c  mov     [rsp+78h+var_30], r12
0x140011031  xor     edx, edx
0x140011033  mov     [rsp+78h+var_38], r14
0x140011038  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14001103f  nop     dword ptr [rax+rax+00h]
0x140011044  xor     edx, edx
0x140011046  mov     [rbp+130h], rbx
0x14001104d  lea     rcx, [rbp+10h]
0x140011051  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140011058  nop     dword ptr [rax+rax+00h]
0x14001105d  mov     [rbx+20h], r15w
0x140011062  mov     rax, [rdi+20h]
0x140011066  mov     [rbx+38h], rax
0x14001106a  mov     [rbx+48h], rdi
0x14001106e  mov     [rbx+40h], r15
0x140011072  mov     [rbx+28h], r15
0x140011076  mov     [rbx+30h], r15
0x14001107a  mov     rax, [rdi+28h]
0x14001107e  mov     [rbx+290h], rax
0x140011085  mov     rax, [rdi+28h]
0x140011089  mov     rcx, [rax+20h]
0x14001108d  mov     [rbx+288h], rcx
0x140011094  mov     rax, [rdi+28h]
0x140011098  mov     rcx, [rax+20h]
0x14001109c  mov     rax, [rcx+20h]
0x1400110a0  mov     [rbx+280h], rax
0x1400110a7  movzx   eax, word ptr [rbp+0A8h]
0x1400110ae  mov     [rbx+2EAh], ax
0x1400110b5  movups  xmm0, xmmword ptr [rbp+48h]
0x1400110b9  movups  xmmword ptr [rbx+200h], xmm0
0x1400110c0  movups  xmm1, xmmword ptr [rbp+58h]
0x1400110c4  movups  xmmword ptr [rbx+210h], xmm1
0x1400110cb  movups  xmm0, xmmword ptr [rbp+68h]
0x1400110cf  movups  xmmword ptr [rbx+220h], xmm0
0x1400110d6  movups  xmm1, xmmword ptr [rbp+78h]
0x1400110da  movups  xmmword ptr [rbx+230h], xmm1
0x1400110e1  movups  xmm0, xmmword ptr [rbp+88h]
0x1400110e8  movups  xmmword ptr [rbx+240h], xmm0
0x1400110ef  movsd   xmm1, qword ptr [rbp+98h]
0x1400110f7  movsd   qword ptr [rbx+250h], xmm1
0x1400110ff  mov     rax, [rbp+0A0h]
0x140011106  mov     [rbx+328h], rax
0x14001110d  mov     eax, [rbp+8]
0x140011110  test    al, 4
0x140011112  jnz     loc_1400111F7
0x140011118  cmp     [rbp+0AAh], r15b
0x14001111f  jnz     short loc_14001112E
0x140011121  cmp     [rbp+0ABh], r15b
0x140011128  jz      loc_1400111F7
0x14001112e  lea     rsi, [rbx+2B0h]
0x140011135  xor     ecx, ecx; Flags
0x140011137  mov     rdx, rsi; EcpList
0x14001113a  call    cs:__imp_FsRtlAllocateExtraCreateParameterList
0x140011141  nop     dword ptr [rax+rax+00h]
0x140011146  mov     edi, eax
0x140011148  test    eax, eax
0x14001114a  js      loc_1400113C0
0x140011150  lea     rax, [rsp+78h+arg_18]
0x140011158  xor     r9d, r9d; CleanupCallback
0x14001115b  mov     [rsp+78h+EcpContext], rax; EcpContext
0x140011160  lea     rcx, GUID_ECP_ENABLE_REDIRECTIONGUARD; EcpType
0x140011167  xor     r8d, r8d; Flags
0x14001116a  mov     [rsp+78h+PoolTag], 6D537843h; PoolTag
0x140011172  mov     edx, 4; SizeOfContext
0x140011177  call    cs:__imp_FsRtlAllocateExtraCreateParameter
0x14001117e  nop     dword ptr [rax+rax+00h]
0x140011183  mov     edi, eax
0x140011185  test    eax, eax
0x140011187  js      loc_1400113C0
0x14001118d  mov     rcx, [rsp+78h+arg_18]
0x140011195  movzx   edx, byte ptr [rbp+0AAh]
0x14001119c  mov     eax, [rcx]
0x14001119e  xor     edx, eax
0x1400111a0  and     edx, 1
0x1400111a3  xor     edx, eax
0x1400111a5  mov     [rcx], edx
0x1400111a7  movzx   ecx, byte ptr [rbp+0ABh]
0x1400111ae  mov     rax, [rsp+78h+arg_18]
0x1400111b6  add     ecx, ecx
0x1400111b8  xor     ecx, edx
0x1400111ba  and     ecx, 2
0x1400111bd  xor     ecx, edx
0x1400111bf  mov     [rax], ecx
0x1400111c1  mov     rdx, [rsp+78h+arg_18]; EcpContext
0x1400111c9  mov     rcx, [rsi]; EcpList
0x1400111cc  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x1400111d3  nop     dword ptr [rax+rax+00h]
0x1400111d8  mov     edi, eax
0x1400111da  test    eax, eax
0x1400111dc  jns     short loc_1400111F7
0x1400111de  mov     rcx, [rsp+78h+arg_18]; EcpContext
0x1400111e6  call    cs:__imp_FsRtlFreeExtraCreateParameter
0x1400111ed  nop     dword ptr [rax+rax+00h]
0x1400111f2  jmp     loc_1400113C8
0x1400111f7  mov     rdi, [rbx+48h]
0x1400111fb  mov     r14, [rbx+38h]
0x1400111ff  mov     rax, [rdi+28h]
0x140011203  mov     r15, [rdi+30h]
0x140011207  lea     rdx, [r14+168h]
0x14001120e  mov     rsi, [rax+28h]
0x140011212  mov     [rsp+78h+arg_0], 0
0x14001121e  mov     eax, [r15+8]
0x140011222  test    al, 4
0x140011224  jz      short loc_14001128D
0x140011226  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14001122d  lea     rax, WPP_GLOBAL_Control
0x140011234  cmp     rcx, rax
0x140011237  jz      short loc_140011260
0x140011239  mov     eax, [rcx+2Ch]
0x14001123c  test    al, 20h
0x14001123e  jz      short loc_140011260
0x140011240  cmp     byte ptr [rcx+29h], 2
0x140011244  jb      short loc_140011260
0x140011246  mov     rax, [r15+1Ch]
0x14001124a  mov     r9, rdi
0x14001124d  mov     rcx, [rcx+18h]
0x140011251  mov     [rsp+78h+EcpContext], rdx
0x140011256  mov     qword ptr [rsp+78h+PoolTag], rax
0x14001125b  call    WPP_SF_qiZ
0x140011260  test    byte ptr cs:WPP_MAIN_CB.Queue+11h, 1
0x140011267  jz      short loc_140011284
0x140011269  lea     r8, [rbx+19Ch]
0x140011270  mov     qword ptr [rsp+78h+PoolTag], rdi
0x140011275  mov     r9, r14
0x140011278  lea     rdx, SmbReconnect
0x14001127f  call    McTemplateK0pp_EtwWriteTransfer
0x140011284  lea     rax, [rsi+200h]
0x14001128b  jmp     short loc_1400112FD
0x14001128d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140011294  lea     rax, WPP_GLOBAL_Control
0x14001129b  cmp     rcx, rax
0x14001129e  jz      short loc_1400112D2
0x1400112a0  mov     eax, [rcx+2Ch]
0x1400112a3  test    al, 20h
0x1400112a5  jz      short loc_1400112D2
0x1400112a7  cmp     byte ptr [rcx+29h], 2
0x1400112ab  jb      short loc_1400112D2
0x1400112ad  mov     eax, [rbx+214h]
0x1400112b3  mov     r9, rdi
0x1400112b6  mov     rcx, [rcx+18h]
0x1400112ba  mov     [rsp+78h+var_48], rdx
0x1400112bf  mov     dword ptr [rsp+78h+EcpContext], eax
0x1400112c3  mov     eax, [rbx+200h]
0x1400112c9  mov     [rsp+78h+PoolTag], eax
0x1400112cd  call    WPP_SF_qDDZ
0x1400112d2  test    byte ptr cs:WPP_MAIN_CB.Queue+11h, 1
0x1400112d9  jz      short loc_1400112F6
0x1400112db  lea     r8, [rbx+19Ch]
0x1400112e2  mov     qword ptr [rsp+78h+PoolTag], rdi
0x1400112e7  mov     r9, r14
0x1400112ea  lea     rdx, SmbUndeferOpen
0x1400112f1  call    McTemplateK0pp_EtwWriteTransfer
0x1400112f6  lea     rax, [rsi+1F8h]
0x1400112fd  lock inc qword ptr [rax]
0x140011301  xor     ecx, ecx
0x140011303  lea     rax, ReconnectOpenDispatch
0x14001130a  mov     [rsp+78h+var_40], rax
0x14001130f  xor     r9d, r9d
0x140011312  mov     dword ptr [rsp+78h+var_48], 978h
0x14001131a  xor     r8d, r8d
0x14001131d  mov     [rsp+78h+arg_0], rcx
0x140011325  mov     rdx, rbx
0x140011328  mov     [rsp+78h+EcpContext], rsi
0x14001132d  mov     qword ptr [rsp+78h+PoolTag], rcx
0x140011332  lea     rcx, [rsp+78h+arg_0]
0x14001133a  call    cs:__imp_SmbCeInitializeExchange
0x140011341  nop     dword ptr [rax+rax+00h]
0x140011346  mov     edi, eax
0x140011348  test    eax, eax
0x14001134a  jnz     short loc_1400113B6
0x14001134c  mov     rax, [rsp+78h+arg_0]
0x140011354  lock or dword ptr [rax+44h], 2080h
0x14001135c  mov     rdx, [rsp+78h+arg_8]
0x140011364  xor     r8d, r8d
0x140011367  mov     rcx, [rsp+78h+arg_0]
0x14001136f  call    cs:__imp_SmbCeAssociateExchangeWithCompoundingKeyEx
0x140011376  nop     dword ptr [rax+rax+00h]
0x14001137b  mov     rax, [rsp+78h+arg_0]
0x140011383  mov     [rax+970h], r13b
0x14001138a  movzx   ecx, byte ptr [r15+148h]
0x140011392  mov     rax, [rsp+78h+arg_0]
0x14001139a  mov     [rax+3F8h], cl
0x1400113a0  mov     rcx, [rsp+78h+arg_0]
0x1400113a8  call    cs:__imp_SmbCeInitiateExchange
0x1400113af  nop     dword ptr [rax+rax+00h]
0x1400113b4  mov     edi, eax
0x1400113b6  lea     rsi, [rbx+2B0h]
0x1400113bd  xor     r15d, r15d
0x1400113c0  cmp     edi, 103h
0x1400113c6  jz      short loc_140011419
0x1400113c8  xor     edx, edx
0x1400113ca  lea     rcx, [rbp+10h]
0x1400113ce  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400113d5  nop     dword ptr [rax+rax+00h]
0x1400113da  xor     edx, edx
0x1400113dc  mov     [rbp+130h], r15
0x1400113e3  lea     rcx, [rbp+10h]
0x1400113e7  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400113ee  nop     dword ptr [rax+rax+00h]
0x1400113f3  mov     rcx, [rsi]; EcpList
0x1400113f6  test    rcx, rcx
0x1400113f9  jz      short loc_14001140A
0x1400113fb  call    cs:__imp_FsRtlFreeExtraCreateParameterList
0x140011402  nop     dword ptr [rax+rax+00h]
0x140011407  mov     [rsi], r15
0x14001140a  mov     rcx, rbx; RxContext
0x14001140d  call    cs:__imp_RxDereferenceAndDeleteRxContext_Real
0x140011414  nop     dword ptr [rax+rax+00h]
0x140011419  mov     r12, [rsp+78h+var_30]
0x14001141e  mov     eax, edi
0x140011420  mov     rsi, [rsp+78h+arg_10]
0x140011428  mov     r14, [rsp+78h+var_38]
0x14001142d  add     rsp, 50h
0x140011431  pop     r15
0x140011433  pop     r13
0x140011435  pop     rdi
0x140011436  pop     rbp
0x140011437  pop     rbx
0x140011438  retn
```
