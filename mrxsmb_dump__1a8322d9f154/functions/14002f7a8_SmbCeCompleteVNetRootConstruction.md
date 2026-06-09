# SmbCeCompleteVNetRootConstruction

- ea: `0x14002f7a8`
- end: `0x14002fb9d`
- name: `SmbCeCompleteVNetRootConstruction`
- size: `1013`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter2, PVOID pContext)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14002eeb0`
- `0x1400473f0`

## callees

- `0x1400097e0`
- `0x140010f94`
- `0x1400189c0`
- `0x14001b280`
- `0x14002f7a8`
- `0x14003e14c`
- `0x14003fb30`
- `0x1400448ec`
- `0x14004710c`
- `0x140048134`

## import_xrefs

- `rdbss!RxUpdateNetRootCachingMode` at `0x14002f937`
- `rdbss!RxUpdateNetRootCachingMode` at `0x14002f937`
- `rdbss!RxPostToWorkerThread` at `0x14002fb10`
- `rdbss!RxPostToWorkerThread` at `0x14002fb10`

## pseudocode

```c
NTSTATUS __fastcall SmbCeCompleteVNetRootConstruction(
        ULONG_PTR BugCheckParameter2,
        struct _RX_WORK_QUEUE_ITEM_ *pContext,
        int a3)
{
  __int64 v3; // rdi
  char v5; // r12
  int v6; // edx
  int v7; // ebp
  ULONG_PTR v8; // rsi
  PRDBSS_DEVICE_OBJECT pDeviceObject; // r13
  _QWORD *Parameter; // r15
  PDEVICE_OBJECT *v11; // r9
  __int64 v12; // r8
  __int64 v13; // rbx
  __int64 v14; // r10
  void (__stdcall *v15)(PVOID); // r9
  int v17; // eax
  __int64 v18; // rcx
  int v19; // [rsp+90h] [rbp+8h]
  struct _LIST_ENTRY *Flink; // [rsp+98h] [rbp+10h]

  v3 = *(_QWORD *)(BugCheckParameter2 + 424);
  v5 = 0;
  v6 = 855;
  v19 = 855;
  v7 = a3;
  v8 = BugCheckParameter2;
  pDeviceObject = pContext->pDeviceObject;
  if ( a3 == -1067646964 )
    BYTE4(pDeviceObject->Dpc.DeferredContext) = *(_BYTE *)(*(_QWORD *)(BugCheckParameter2 + 416) + 480LL);
  Parameter = pContext[6].Parameter;
  v11 = &WPP_GLOBAL_Control;
  if ( a3 < 0 )
    goto LABEL_43;
  v12 = *(unsigned __int8 *)(v3 + 188);
  v13 = Parameter[4];
  if ( *(_BYTE *)(v3 + 188) )
  {
    if ( *(_BYTE *)(v3 + 188) == 1 )
    {
      *(_BYTE *)(v13 + 77) = 1;
      *(_DWORD *)(v13 + 80) = 17;
    }
    else if ( *(_BYTE *)(v3 + 188) == 3 )
    {
      *(_BYTE *)(v13 + 77) = 3;
      *(_DWORD *)(v13 + 80) = 24;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_57bae5703ea63848601f64ee373b1e39_Traceguids, v13, v12);
      }
      v7 = -1073741621;
      v19 = 942;
    }
  }
  else
  {
    *(_BYTE *)(v13 + 77) = 0;
    *(_DWORD *)(v13 + 80) = 7;
    Flink = pDeviceObject->DeviceObject.Queue.ListEntry.Flink;
    if ( *(_DWORD *)(MRxSmbGetInstanceConfigurationBlock(Flink) + 40) )
      *(_DWORD *)(v13 + 108) = *(_DWORD *)(MRxSmbGetInstanceConfigurationBlock(Flink) + 40);
    *(_DWORD *)(v13 + 112) = *(_DWORD *)(v13 + 108);
  }
  if ( (*(_DWORD *)(v3 + 176) & 2) != 0 )
    *(_DWORD *)(v13 + 56) |= 2u;
  if ( (*(_DWORD *)(v3 + 176) & 0x40) != 0 )
    *(_DWORD *)(v13 + 56) |= 0x40u;
  if ( (*(_DWORD *)(v3 + 176) & 0x80u) != 0 )
    *(_DWORD *)(v13 + 56) |= 0x80u;
  if ( (*(_DWORD *)(v3 + 176) & 0x100) != 0 )
    *(_DWORD *)(v13 + 56) |= 0x100u;
  if ( (*(_DWORD *)(v3 + 176) & 0x200) != 0 )
    *(_DWORD *)(v13 + 56) |= 0x200u;
  if ( (*(_DWORD *)(v3 + 184) & 0x800000) != 0 )
    *(_DWORD *)(v13 + 56) |= 0x400u;
  RxUpdateNetRootCachingMode(v13, *(unsigned int *)(v3 + 180), v12, v11);
  if ( v7 < 0 )
  {
LABEL_42:
    v6 = v19;
LABEL_43:
    if ( (Microsoft_Windows_SMBClientEnableBits & 1) != 0 )
      McTemplateK0qqq_EtwWriteTransfer(
        BugCheckParameter2,
        (unsigned int)CreateVNetRootError,
        (struct _LIST_ENTRY **)((char *)&pContext->pDeviceObject->MiniRdrListLinks.Flink + 4),
        v7,
        v6);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qZL(WPP_GLOBAL_Control->AttachedDevice, v6, a3, (_DWORD)Parameter, *(_QWORD *)(v8 + 424) + 96LL, v7);
    }
    Parameter[5] = 0;
    *(_QWORD *)(v8 + 480) = 0;
    SmbCeDecrementActiveVNetRootsOnVNetRootContext(v8, Parameter);
    SmbCeDereferenceVNetRootContext(v8);
    goto LABEL_50;
  }
  if ( (*(_DWORD *)(v3 + 176) & 0x200) != 0 || (*(_DWORD *)(v3 + 180) & 0x100000) != 0 )
  {
    if ( (byte_1400712A3 & 8) != 0 )
    {
      v14 = *(_QWORD *)(v3 + 88);
      McTemplateK0hzr0hzr2ttt_EtwWriteTransfer(
        *(_WORD *)(v3 + 96) >> 1,
        (*(_DWORD *)(v3 + 180) >> 20) & 1,
        (*(unsigned __int8 *)(v14 + 737) >> 4) & 1,
        *(_WORD *)(v14 + 80) >> 1,
        *(_QWORD *)(v14 + 88),
        *(_WORD *)(v3 + 96) >> 1,
        *(_QWORD *)(v3 + 104),
        (*(_DWORD *)(v3 + 176) & 0x200) != 0,
        (*(_DWORD *)(v3 + 180) & 0x100000) != 0,
        (*(_BYTE *)(v14 + 737) & 0x10) != 0);
    }
    if ( (*(_BYTE *)(*(_QWORD *)(v3 + 88) + 737LL) & 0x10) == 0 )
    {
      LODWORD(BugCheckParameter2) = (_DWORD)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_57bae5703ea63848601f64ee373b1e39_Traceguids, v3 + 96);
      }
      BYTE6(pDeviceObject->RxNetNameTableInDeviceObject.TableLock.ExclusiveWaiters) |= 0x10u;
      if ( (*(_DWORD *)(v3 + 176) & 0x200) != 0 )
        BYTE6(pDeviceObject->RxNetNameTableInDeviceObject.TableLock.ExclusiveWaiters) |= 0x20u;
      v5 = 1;
      v7 = -1069481983;
      *(_BYTE *)(*(_QWORD *)(v3 + 88) + 737LL) |= 0x40u;
      goto LABEL_42;
    }
  }
  if ( HIDWORD(pContext[7].List.Flink) == -1073741620 && (*(_DWORD *)(v3 + 176) & 0x200) != 0 && !*(_BYTE *)(v3 + 189) )
    SmbCeSuspendServerConnections(*(_QWORD *)(v3 + 88), 0, 5);
  v17 = `RxIsGlobalMappingLuid'::`2'::globalMappingLuid;
  Parameter[5] = v8;
  v18 = *(_QWORD *)(v8 + 416);
  *(_QWORD *)(v8 + 480) = Parameter;
  if ( *(_DWORD *)(v18 + 96) == v17 && *(_DWORD *)(v18 + 100) == dword_14007025C )
    *((_DWORD *)Parameter + 14) |= 0x100u;
LABEL_50:
  v15 = (void (__stdcall *)(PVOID))pContext[6].pDeviceObject;
  LODWORD(pContext[7].List.Flink) = v7;
  HIDWORD(pContext[7].List.Flink) = v5 != 0 ? v7 : 0;
  return RxPostToWorkerThread(*(PRDBSS_DEVICE_OBJECT *)(v8 + 24), CriticalWorkQueue, pContext + 5, v15, pContext);
}

```

## disassembly

```asm
0x14002f7a8  mov     [rsp+arg_18], rbx
0x14002f7ad  push    rbp
0x14002f7ae  push    rsi
0x14002f7af  push    rdi
0x14002f7b0  push    r12
0x14002f7b2  push    r13
0x14002f7b4  push    r14
0x14002f7b6  push    r15
0x14002f7b8  sub     rsp, 50h
0x14002f7bc  mov     rdi, [rcx+1A8h]
0x14002f7c3  mov     r14, rdx
0x14002f7c6  xor     r12b, r12b
0x14002f7c9  mov     edx, 357h
0x14002f7ce  mov     [rsp+88h+arg_0], edx
0x14002f7d5  mov     ebp, r8d
0x14002f7d8  mov     rsi, rcx
0x14002f7db  mov     r13, [r14+20h]
0x14002f7df  cmp     r8d, 0C05D000Ch
0x14002f7e6  jnz     short loc_14002F7FD
0x14002f7e8  mov     rax, [rcx+1A0h]
0x14002f7ef  mov     r9b, [rax+1E0h]
0x14002f7f6  mov     [r13+0ECh], r9b
0x14002f7fd  mov     r15, [r14+108h]
0x14002f804  lea     r9, WPP_GLOBAL_Control
0x14002f80b  test    r8d, r8d
0x14002f80e  js      loc_14002FA4F
0x14002f814  movzx   r8d, byte ptr [rdi+0BCh]
0x14002f81c  mov     rbx, [r15+20h]
0x14002f820  mov     ecx, r8d
0x14002f823  test    r8d, r8d
0x14002f826  jz      short loc_14002F894
0x14002f828  sub     ecx, 1
0x14002f82b  jz      short loc_14002F887
0x14002f82d  cmp     ecx, 2
0x14002f830  jz      short loc_14002F87A
0x14002f832  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002f839  cmp     rcx, r9
0x14002f83c  jz      short loc_14002F868
0x14002f83e  mov     eax, [rcx+2Ch]
0x14002f841  test    al, 1
0x14002f843  jz      short loc_14002F868
0x14002f845  cmp     byte ptr [rcx+29h], 1
0x14002f849  jb      short loc_14002F868
0x14002f84b  mov     rcx, [rcx+18h]
0x14002f84f  mov     edx, 17h
0x14002f854  mov     dword ptr [rsp+88h+pContext], r8d
0x14002f859  mov     r9, rbx
0x14002f85c  lea     r8, WPP_57bae5703ea63848601f64ee373b1e39_Traceguids
0x14002f863  call    WPP_SF_qD
0x14002f868  mov     ebp, 0C00000CBh
0x14002f86d  mov     [rsp+88h+arg_0], 3AEh
0x14002f878  jmp     short loc_14002F8D2
0x14002f87a  mov     byte ptr [rbx+4Dh], 3
0x14002f87e  mov     dword ptr [rbx+50h], 18h
0x14002f885  jmp     short loc_14002F8D2
0x14002f887  mov     byte ptr [rbx+4Dh], 1
0x14002f88b  mov     dword ptr [rbx+50h], 11h
0x14002f892  jmp     short loc_14002F8D2
0x14002f894  mov     [rbx+4Dh], r12b
0x14002f898  mov     dword ptr [rbx+50h], 7
0x14002f89f  mov     rax, [r13+50h]
0x14002f8a3  mov     rcx, rax
0x14002f8a6  mov     [rsp+88h+arg_8], rax
0x14002f8ae  call    MRxSmbGetInstanceConfigurationBlock
0x14002f8b3  cmp     dword ptr [rax+28h], 0
0x14002f8b7  jz      short loc_14002F8CC
0x14002f8b9  mov     rcx, [rsp+88h+arg_8]
0x14002f8c1  call    MRxSmbGetInstanceConfigurationBlock
0x14002f8c6  mov     ecx, [rax+28h]
0x14002f8c9  mov     [rbx+6Ch], ecx
0x14002f8cc  mov     eax, [rbx+6Ch]
0x14002f8cf  mov     [rbx+70h], eax
0x14002f8d2  mov     eax, [rdi+0B0h]
0x14002f8d8  test    al, 2
0x14002f8da  jz      short loc_14002F8E0
0x14002f8dc  or      dword ptr [rbx+38h], 2
0x14002f8e0  mov     eax, [rdi+0B0h]
0x14002f8e6  test    al, 40h
0x14002f8e8  jz      short loc_14002F8EE
0x14002f8ea  or      dword ptr [rbx+38h], 40h
0x14002f8ee  mov     eax, [rdi+0B0h]
0x14002f8f4  test    al, al
0x14002f8f6  jns     short loc_14002F8FD
0x14002f8f8  bts     dword ptr [rbx+38h], 7
0x14002f8fd  mov     ecx, 100h
0x14002f902  test    [rdi+0B0h], ecx
0x14002f908  jz      short loc_14002F90D
0x14002f90a  or      [rbx+38h], ecx
0x14002f90d  mov     ecx, 200h
0x14002f912  test    [rdi+0B0h], ecx
0x14002f918  jz      short loc_14002F91D
0x14002f91a  or      [rbx+38h], ecx
0x14002f91d  test    dword ptr [rdi+0B8h], 800000h
0x14002f927  jz      short loc_14002F92E
0x14002f929  bts     dword ptr [rbx+38h], 0Ah
0x14002f92e  mov     edx, [rdi+0B4h]
0x14002f934  mov     rcx, rbx
0x14002f937  call    cs:__imp_RxUpdateNetRootCachingMode
0x14002f93e  nop     dword ptr [rax+rax+00h]
0x14002f943  test    ebp, ebp
0x14002f945  js      loc_14002FA48
0x14002f94b  mov     ecx, [rdi+0B0h]
0x14002f951  mov     ebx, 200h
0x14002f956  and     ecx, ebx
0x14002f958  jnz     short loc_14002F96A
0x14002f95a  test    dword ptr [rdi+0B4h], 100000h
0x14002f964  jz      loc_14002FB35
0x14002f96a  test    cs:byte_1400712A3, 8
0x14002f971  jz      short loc_14002F9D3
0x14002f973  mov     r10, [rdi+58h]
0x14002f977  xor     eax, eax
0x14002f979  mov     edx, [rdi+0B4h]
0x14002f97f  shr     edx, 14h
0x14002f982  and     edx, 1
0x14002f985  movzx   r8d, byte ptr [r10+2E1h]
0x14002f98d  movzx   r9d, word ptr [r10+50h]
0x14002f992  shr     r8d, 4
0x14002f996  and     r8d, 1
0x14002f99a  mov     [rsp+88h+var_40], r8d
0x14002f99f  test    ecx, ecx
0x14002f9a1  movzx   ecx, word ptr [rdi+60h]
0x14002f9a5  setnz   al
0x14002f9a8  mov     [rsp+88h+var_48], edx
0x14002f9ac  mov     [rsp+88h+var_50], eax
0x14002f9b0  mov     rax, [rdi+68h]
0x14002f9b4  mov     [rsp+88h+var_58], rax
0x14002f9b9  mov     rax, [r10+58h]
0x14002f9bd  shr     cx, 1
0x14002f9c0  mov     word ptr [rsp+88h+var_60], cx
0x14002f9c5  shr     r9w, 1
0x14002f9c9  mov     [rsp+88h+pContext], rax
0x14002f9ce  call    McTemplateK0hzr0hzr2ttt_EtwWriteTransfer
0x14002f9d3  mov     rax, [rdi+58h]
0x14002f9d7  test    byte ptr [rax+2E1h], 10h
0x14002f9de  jnz     loc_14002FB35
0x14002f9e4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002f9eb  lea     rax, WPP_GLOBAL_Control
0x14002f9f2  cmp     rcx, rax
0x14002f9f5  jz      short loc_14002FA1D
0x14002f9f7  mov     eax, [rcx+2Ch]
0x14002f9fa  test    al, 40h
0x14002f9fc  jz      short loc_14002FA1D
0x14002f9fe  cmp     byte ptr [rcx+29h], 2
0x14002fa02  jb      short loc_14002FA1D
0x14002fa04  mov     rcx, [rcx+18h]
0x14002fa08  lea     r9, [rdi+60h]
0x14002fa0c  mov     edx, 18h
0x14002fa11  lea     r8, WPP_57bae5703ea63848601f64ee373b1e39_Traceguids
0x14002fa18  call    WPP_SF_Z
0x14002fa1d  or      byte ptr [r13+2EEh], 10h
0x14002fa25  test    [rdi+0B0h], ebx
0x14002fa2b  jz      short loc_14002FA35
0x14002fa2d  or      byte ptr [r13+2EEh], 20h
0x14002fa35  mov     rax, [rdi+58h]
0x14002fa39  mov     r12b, 1
0x14002fa3c  mov     ebp, 0C0410001h
0x14002fa41  or      byte ptr [rax+2E1h], 40h
0x14002fa48  mov     edx, [rsp+88h+arg_0]
0x14002fa4f  test    cs:Microsoft_Windows_SMBClientEnableBits, 1
0x14002fa56  jz      short loc_14002FA7C
0x14002fa58  mov     r8, [r14+20h]
0x14002fa5c  or      edx, 30300000h
0x14002fa62  mov     dword ptr [rsp+88h+pContext], edx
0x14002fa66  add     r8, 19Ch
0x14002fa6d  lea     rdx, CreateVNetRootError
0x14002fa74  mov     r9d, ebp
0x14002fa77  call    McTemplateK0qqq_EtwWriteTransfer
0x14002fa7c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002fa83  lea     rax, WPP_GLOBAL_Control
0x14002fa8a  cmp     rcx, rax
0x14002fa8d  jz      short loc_14002FABC
0x14002fa8f  mov     eax, [rcx+2Ch]
0x14002fa92  test    al, 1
0x14002fa94  jz      short loc_14002FABC
0x14002fa96  cmp     byte ptr [rcx+29h], 1
0x14002fa9a  jb      short loc_14002FABC
0x14002fa9c  mov     rax, [rsi+1A8h]
0x14002faa3  mov     r9, r15
0x14002faa6  mov     rcx, [rcx+18h]
0x14002faaa  add     rax, 60h ; '`'
0x14002faae  mov     [rsp+88h+var_60], ebp
0x14002fab2  mov     [rsp+88h+pContext], rax
0x14002fab7  call    WPP_SF_qZL
0x14002fabc  mov     qword ptr [r15+28h], 0
0x14002fac4  mov     rdx, r15
0x14002fac7  mov     rcx, rsi
0x14002faca  mov     qword ptr [rsi+1E0h], 0
0x14002fad5  call    SmbCeDecrementActiveVNetRootsOnVNetRootContext
0x14002fada  mov     rcx, rsi; BugCheckParameter2
0x14002fadd  call    SmbCeDereferenceVNetRootContext
0x14002fae2  mov     r9, [r14+110h]; Routine
0x14002fae9  lea     r8, [r14+0C8h]; pWorkQueueItem
0x14002faf0  neg     r12b
0x14002faf3  mov     [r14+118h], ebp
0x14002fafa  mov     [rsp+88h+pContext], r14; pContext
0x14002faff  sbb     eax, eax
0x14002fb01  xor     edx, edx; WorkQueueType
0x14002fb03  and     eax, ebp
0x14002fb05  mov     [r14+11Ch], eax
0x14002fb0c  mov     rcx, [rsi+18h]; pMRxDeviceObject
0x14002fb10  call    cs:__imp_RxPostToWorkerThread
0x14002fb17  nop     dword ptr [rax+rax+00h]
0x14002fb1c  mov     rbx, [rsp+88h+arg_18]
0x14002fb24  add     rsp, 50h
0x14002fb28  pop     r15
0x14002fb2a  pop     r14
0x14002fb2c  pop     r13
0x14002fb2e  pop     r12
0x14002fb30  pop     rdi
0x14002fb31  pop     rsi
0x14002fb32  pop     rbp
0x14002fb33  retn
0x14002fb35  cmp     dword ptr [r14+11Ch], 0C00000CCh
0x14002fb40  jnz     short loc_14002FB62
0x14002fb42  test    [rdi+0B0h], ebx
0x14002fb48  jz      short loc_14002FB62
0x14002fb4a  cmp     byte ptr [rdi+0BDh], 0
0x14002fb51  jnz     short loc_14002FB62
0x14002fb53  mov     rcx, [rdi+58h]
0x14002fb57  xor     edx, edx
0x14002fb59  lea     r8d, [rdx+5]
0x14002fb5d  call    SmbCeSuspendServerConnections
0x14002fb62  mov     eax, cs:?globalMappingLuid@?1??RxIsGlobalMappingLuid@@9@9; `RxIsGlobalMappingLuid'::`2'::globalMappingLuid
0x14002fb68  mov     [r15+28h], rsi
0x14002fb6c  mov     rcx, [rsi+1A0h]
0x14002fb73  mov     [rsi+1E0h], r15
0x14002fb7a  cmp     [rcx+60h], eax
0x14002fb7d  jnz     loc_14002FAE2
0x14002fb83  mov     eax, cs:dword_14007025C
0x14002fb89  cmp     [rcx+64h], eax
0x14002fb8c  jnz     loc_14002FAE2
0x14002fb92  bts     dword ptr [r15+38h], 8
0x14002fb98  jmp     loc_14002FAE2
```
