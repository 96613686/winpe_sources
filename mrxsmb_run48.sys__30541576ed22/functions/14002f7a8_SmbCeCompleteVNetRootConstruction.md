# SmbCeCompleteVNetRootConstruction

- ea: `0x14002f7a8`
- end: `0x14002fba2`
- name: `SmbCeCompleteVNetRootConstruction`
- size: `1018`
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

- `rdbss!RxUpdateNetRootCachingMode` at `0x14002f93f`
- `rdbss!RxUpdateNetRootCachingMode` at `0x14002f93f`
- `rdbss!RxPostToWorkerThread` at `0x14002fb1c`
- `rdbss!RxPostToWorkerThread` at `0x14002fb1c`

## pseudocode

```c
NTSTATUS __fastcall SmbCeCompleteVNetRootConstruction(_QWORD *BugCheckParameter2, PVOID pContext, int a3)
{
  int v4; // ebp
  int v5; // edx
  _QWORD *v6; // rsi
  char v7; // r12
  __int64 v8; // r13
  __int64 v9; // rdi
  __int64 v10; // r15
  PDEVICE_OBJECT *v11; // r9
  __int64 v12; // r8
  __int64 v13; // rbx
  __int64 v14; // r10
  int v16; // eax
  __int64 v17; // rcx
  int v18; // [rsp+A0h] [rbp+8h]
  __int64 v19; // [rsp+A8h] [rbp+10h]
  struct _RDBSS_DEVICE_OBJECT *pMRxDeviceObject; // [rsp+B8h] [rbp+20h]

  v4 = a3;
  v5 = 856;
  v6 = BugCheckParameter2;
  v18 = 856;
  v7 = 0;
  v8 = *((_QWORD *)pContext + 4);
  v9 = BugCheckParameter2[53];
  pMRxDeviceObject = (struct _RDBSS_DEVICE_OBJECT *)BugCheckParameter2[3];
  if ( a3 == -1067646964 )
  {
    LOBYTE(a3) = *(_BYTE *)(BugCheckParameter2[52] + 480LL);
    *(_BYTE *)(v8 + 236) = a3;
  }
  v10 = *((_QWORD *)pContext + 33);
  v11 = &WPP_GLOBAL_Control;
  if ( v4 < 0 )
    goto LABEL_43;
  v12 = *(unsigned __int8 *)(v9 + 188);
  v13 = *(_QWORD *)(v10 + 32);
  if ( *(_BYTE *)(v9 + 188) )
  {
    if ( *(_BYTE *)(v9 + 188) == 1 )
    {
      *(_BYTE *)(v13 + 77) = 1;
      *(_DWORD *)(v13 + 80) = 17;
    }
    else if ( *(_BYTE *)(v9 + 188) == 3 )
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
        WPP_SF_qD(WPP_GLOBAL_Control->AttachedDevice, 23, &WPP_c2a8e7a4add33c98a1c08e02d1cd8763_Traceguids, v13, v12);
      }
      v4 = -1073741621;
      v18 = 950;
    }
  }
  else
  {
    *(_BYTE *)(v13 + 77) = 0;
    *(_DWORD *)(v13 + 80) = 7;
    v19 = *(_QWORD *)(v8 + 80);
    if ( *(_DWORD *)(MRxSmbGetInstanceConfigurationBlock(v19) + 40) )
      *(_DWORD *)(v13 + 108) = *(_DWORD *)(MRxSmbGetInstanceConfigurationBlock(v19) + 40);
    *(_DWORD *)(v13 + 112) = *(_DWORD *)(v13 + 108);
  }
  if ( (*(_DWORD *)(v9 + 176) & 2) != 0 )
    *(_DWORD *)(v13 + 56) |= 2u;
  if ( (*(_DWORD *)(v9 + 176) & 0x40) != 0 )
    *(_DWORD *)(v13 + 56) |= 0x40u;
  if ( (*(_DWORD *)(v9 + 176) & 0x80u) != 0 )
    *(_DWORD *)(v13 + 56) |= 0x80u;
  if ( (*(_DWORD *)(v9 + 176) & 0x100) != 0 )
    *(_DWORD *)(v13 + 56) |= 0x100u;
  if ( (*(_DWORD *)(v9 + 176) & 0x200) != 0 )
    *(_DWORD *)(v13 + 56) |= 0x200u;
  if ( (*(_DWORD *)(v9 + 184) & 0x800000) != 0 )
    *(_DWORD *)(v13 + 56) |= 0x400u;
  RxUpdateNetRootCachingMode(v13, *(unsigned int *)(v9 + 180), v12, v11);
  if ( v4 < 0 )
  {
LABEL_42:
    v5 = v18;
LABEL_43:
    if ( (Microsoft_Windows_SMBClientEnableBits & 1) != 0 )
      McTemplateK0qqq_EtwWriteTransfer(
        (_DWORD)BugCheckParameter2,
        (unsigned int)&CreateVNetRootError,
        *((_QWORD *)pContext + 4) + 412,
        v4,
        v5);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qZL(WPP_GLOBAL_Control->AttachedDevice, v5, a3, v10, v6[53] + 96LL, v4);
    }
    *(_QWORD *)(v10 + 40) = 0;
    v6[60] = 0;
    SmbCeDecrementActiveVNetRootsOnVNetRootContext(v6, v10);
    SmbCeDereferenceVNetRootContext((ULONG_PTR)v6);
    goto LABEL_50;
  }
  if ( (*(_DWORD *)(v9 + 176) & 0x200) != 0 || (*(_DWORD *)(v9 + 180) & 0x100000) != 0 )
  {
    if ( (byte_1400712C3 & 8) != 0 )
    {
      v14 = *(_QWORD *)(v9 + 88);
      McTemplateK0hzr0hzr2ttt_EtwWriteTransfer(
        *(_WORD *)(v9 + 96) >> 1,
        (*(_DWORD *)(v9 + 180) >> 20) & 1,
        (*(unsigned __int8 *)(v14 + 737) >> 4) & 1,
        *(_WORD *)(v14 + 80) >> 1,
        *(_QWORD *)(v14 + 88),
        *(_WORD *)(v9 + 96) >> 1,
        *(_QWORD *)(v9 + 104),
        (*(_DWORD *)(v9 + 176) & 0x200) != 0,
        (*(_DWORD *)(v9 + 180) & 0x100000) != 0,
        (*(_BYTE *)(v14 + 737) & 0x10) != 0);
    }
    if ( (*(_BYTE *)(*(_QWORD *)(v9 + 88) + 737LL) & 0x10) == 0 )
    {
      LODWORD(BugCheckParameter2) = (_DWORD)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 24, &WPP_c2a8e7a4add33c98a1c08e02d1cd8763_Traceguids, v9 + 96);
      }
      *(_BYTE *)(v8 + 750) |= 0x10u;
      if ( (*(_DWORD *)(v9 + 176) & 0x200) != 0 )
        *(_BYTE *)(v8 + 750) |= 0x20u;
      v7 = 1;
      v4 = -1069481983;
      *(_BYTE *)(*(_QWORD *)(v9 + 88) + 737LL) |= 0x40u;
      goto LABEL_42;
    }
  }
  if ( *((_DWORD *)pContext + 71) == -1073741620 && (*(_DWORD *)(v9 + 176) & 0x200) != 0 && !*(_BYTE *)(v9 + 189) )
    SmbCeSuspendServerConnections(*(_QWORD *)(v9 + 88), 0, 5);
  v16 = `RxIsGlobalMappingLuid'::`2'::globalMappingLuid;
  *(_QWORD *)(v10 + 40) = v6;
  v17 = v6[52];
  v6[60] = v10;
  if ( *(_DWORD *)(v17 + 96) == v16 && *(_DWORD *)(v17 + 100) == dword_14007025C )
    *(_DWORD *)(v10 + 56) |= 0x100u;
LABEL_50:
  *((_DWORD *)pContext + 70) = v4;
  *((_DWORD *)pContext + 71) = v7 != 0 ? v4 : 0;
  return RxPostToWorkerThread(
           pMRxDeviceObject,
           CriticalWorkQueue,
           (PRX_WORK_QUEUE_ITEM)pContext + 5,
           *((PRX_WORKERTHREAD_ROUTINE *)pContext + 34),
           pContext);
}

```

## disassembly

```asm
0x14002f7a8  push    rbx
0x14002f7aa  push    rbp
0x14002f7ab  push    rsi
0x14002f7ac  push    rdi
0x14002f7ad  push    r12
0x14002f7af  push    r13
0x14002f7b1  push    r14
0x14002f7b3  push    r15
0x14002f7b5  sub     rsp, 58h
0x14002f7b9  mov     r14, rdx
0x14002f7bc  mov     ebp, r8d
0x14002f7bf  mov     edx, 358h
0x14002f7c4  mov     rsi, rcx
0x14002f7c7  mov     [rsp+98h+arg_0], edx
0x14002f7ce  xor     r12b, r12b
0x14002f7d1  mov     r13, [r14+20h]
0x14002f7d5  mov     rax, [rcx+18h]
0x14002f7d9  mov     rdi, [rcx+1A8h]
0x14002f7e0  mov     [rsp+98h+pMRxDeviceObject], rax
0x14002f7e8  cmp     r8d, 0C05D000Ch
0x14002f7ef  jnz     short loc_14002F806
0x14002f7f1  mov     rax, [rcx+1A0h]
0x14002f7f8  mov     r8b, [rax+1E0h]
0x14002f7ff  mov     [r13+0ECh], r8b
0x14002f806  mov     r15, [r14+108h]
0x14002f80d  lea     r9, WPP_GLOBAL_Control
0x14002f814  test    ebp, ebp
0x14002f816  js      loc_14002FA57
0x14002f81c  movzx   r8d, byte ptr [rdi+0BCh]
0x14002f824  mov     rbx, [r15+20h]
0x14002f828  mov     ecx, r8d
0x14002f82b  test    r8d, r8d
0x14002f82e  jz      short loc_14002F89C
0x14002f830  sub     ecx, 1
0x14002f833  jz      short loc_14002F88F
0x14002f835  cmp     ecx, 2
0x14002f838  jz      short loc_14002F882
0x14002f83a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002f841  cmp     rcx, r9
0x14002f844  jz      short loc_14002F870
0x14002f846  mov     eax, [rcx+2Ch]
0x14002f849  test    al, 1
0x14002f84b  jz      short loc_14002F870
0x14002f84d  cmp     byte ptr [rcx+29h], 1
0x14002f851  jb      short loc_14002F870
0x14002f853  mov     rcx, [rcx+18h]
0x14002f857  mov     edx, 17h
0x14002f85c  mov     dword ptr [rsp+98h+pContext], r8d
0x14002f861  mov     r9, rbx
0x14002f864  lea     r8, WPP_c2a8e7a4add33c98a1c08e02d1cd8763_Traceguids
0x14002f86b  call    WPP_SF_qD
0x14002f870  mov     ebp, 0C00000CBh
0x14002f875  mov     [rsp+98h+arg_0], 3B6h
0x14002f880  jmp     short loc_14002F8DA
0x14002f882  mov     byte ptr [rbx+4Dh], 3
0x14002f886  mov     dword ptr [rbx+50h], 18h
0x14002f88d  jmp     short loc_14002F8DA
0x14002f88f  mov     byte ptr [rbx+4Dh], 1
0x14002f893  mov     dword ptr [rbx+50h], 11h
0x14002f89a  jmp     short loc_14002F8DA
0x14002f89c  mov     [rbx+4Dh], r12b
0x14002f8a0  mov     dword ptr [rbx+50h], 7
0x14002f8a7  mov     rax, [r13+50h]
0x14002f8ab  mov     rcx, rax
0x14002f8ae  mov     [rsp+98h+arg_8], rax
0x14002f8b6  call    MRxSmbGetInstanceConfigurationBlock
0x14002f8bb  cmp     dword ptr [rax+28h], 0
0x14002f8bf  jz      short loc_14002F8D4
0x14002f8c1  mov     rcx, [rsp+98h+arg_8]
0x14002f8c9  call    MRxSmbGetInstanceConfigurationBlock
0x14002f8ce  mov     ecx, [rax+28h]
0x14002f8d1  mov     [rbx+6Ch], ecx
0x14002f8d4  mov     eax, [rbx+6Ch]
0x14002f8d7  mov     [rbx+70h], eax
0x14002f8da  mov     eax, [rdi+0B0h]
0x14002f8e0  test    al, 2
0x14002f8e2  jz      short loc_14002F8E8
0x14002f8e4  or      dword ptr [rbx+38h], 2
0x14002f8e8  mov     eax, [rdi+0B0h]
0x14002f8ee  test    al, 40h
0x14002f8f0  jz      short loc_14002F8F6
0x14002f8f2  or      dword ptr [rbx+38h], 40h
0x14002f8f6  mov     eax, [rdi+0B0h]
0x14002f8fc  test    al, al
0x14002f8fe  jns     short loc_14002F905
0x14002f900  bts     dword ptr [rbx+38h], 7
0x14002f905  mov     ecx, 100h
0x14002f90a  test    [rdi+0B0h], ecx
0x14002f910  jz      short loc_14002F915
0x14002f912  or      [rbx+38h], ecx
0x14002f915  mov     ecx, 200h
0x14002f91a  test    [rdi+0B0h], ecx
0x14002f920  jz      short loc_14002F925
0x14002f922  or      [rbx+38h], ecx
0x14002f925  test    dword ptr [rdi+0B8h], 800000h
0x14002f92f  jz      short loc_14002F936
0x14002f931  bts     dword ptr [rbx+38h], 0Ah
0x14002f936  mov     edx, [rdi+0B4h]
0x14002f93c  mov     rcx, rbx
0x14002f93f  call    cs:__imp_RxUpdateNetRootCachingMode
0x14002f946  nop     dword ptr [rax+rax+00h]
0x14002f94b  test    ebp, ebp
0x14002f94d  js      loc_14002FA50
0x14002f953  mov     ecx, [rdi+0B0h]
0x14002f959  mov     ebx, 200h
0x14002f95e  and     ecx, ebx
0x14002f960  jnz     short loc_14002F972
0x14002f962  test    dword ptr [rdi+0B4h], 100000h
0x14002f96c  jz      loc_14002FB3A
0x14002f972  test    cs:byte_1400712C3, 8
0x14002f979  jz      short loc_14002F9DB
0x14002f97b  mov     r10, [rdi+58h]
0x14002f97f  xor     eax, eax
0x14002f981  mov     edx, [rdi+0B4h]
0x14002f987  shr     edx, 14h
0x14002f98a  and     edx, 1
0x14002f98d  movzx   r8d, byte ptr [r10+2E1h]
0x14002f995  movzx   r9d, word ptr [r10+50h]
0x14002f99a  shr     r8d, 4
0x14002f99e  and     r8d, 1
0x14002f9a2  mov     [rsp+98h+var_50], r8d
0x14002f9a7  test    ecx, ecx
0x14002f9a9  movzx   ecx, word ptr [rdi+60h]
0x14002f9ad  setnz   al
0x14002f9b0  mov     [rsp+98h+var_58], edx
0x14002f9b4  mov     [rsp+98h+var_60], eax
0x14002f9b8  mov     rax, [rdi+68h]
0x14002f9bc  mov     [rsp+98h+var_68], rax
0x14002f9c1  mov     rax, [r10+58h]
0x14002f9c5  shr     cx, 1
0x14002f9c8  mov     word ptr [rsp+98h+var_70], cx
0x14002f9cd  shr     r9w, 1
0x14002f9d1  mov     [rsp+98h+pContext], rax
0x14002f9d6  call    McTemplateK0hzr0hzr2ttt_EtwWriteTransfer
0x14002f9db  mov     rax, [rdi+58h]
0x14002f9df  test    byte ptr [rax+2E1h], 10h
0x14002f9e6  jnz     loc_14002FB3A
0x14002f9ec  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002f9f3  lea     rax, WPP_GLOBAL_Control
0x14002f9fa  cmp     rcx, rax
0x14002f9fd  jz      short loc_14002FA25
0x14002f9ff  mov     eax, [rcx+2Ch]
0x14002fa02  test    al, 40h
0x14002fa04  jz      short loc_14002FA25
0x14002fa06  cmp     byte ptr [rcx+29h], 2
0x14002fa0a  jb      short loc_14002FA25
0x14002fa0c  mov     rcx, [rcx+18h]
0x14002fa10  lea     r9, [rdi+60h]
0x14002fa14  mov     edx, 18h
0x14002fa19  lea     r8, WPP_c2a8e7a4add33c98a1c08e02d1cd8763_Traceguids
0x14002fa20  call    WPP_SF_Z
0x14002fa25  or      byte ptr [r13+2EEh], 10h
0x14002fa2d  test    [rdi+0B0h], ebx
0x14002fa33  jz      short loc_14002FA3D
0x14002fa35  or      byte ptr [r13+2EEh], 20h
0x14002fa3d  mov     rax, [rdi+58h]
0x14002fa41  mov     r12b, 1
0x14002fa44  mov     ebp, 0C0410001h
0x14002fa49  or      byte ptr [rax+2E1h], 40h
0x14002fa50  mov     edx, [rsp+98h+arg_0]
0x14002fa57  test    cs:Microsoft_Windows_SMBClientEnableBits, 1
0x14002fa5e  jz      short loc_14002FA84
0x14002fa60  mov     r8, [r14+20h]
0x14002fa64  or      edx, 30300000h
0x14002fa6a  mov     dword ptr [rsp+98h+pContext], edx
0x14002fa6e  add     r8, 19Ch
0x14002fa75  lea     rdx, CreateVNetRootError
0x14002fa7c  mov     r9d, ebp
0x14002fa7f  call    McTemplateK0qqq_EtwWriteTransfer
0x14002fa84  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002fa8b  lea     rax, WPP_GLOBAL_Control
0x14002fa92  cmp     rcx, rax
0x14002fa95  jz      short loc_14002FAC4
0x14002fa97  mov     eax, [rcx+2Ch]
0x14002fa9a  test    al, 1
0x14002fa9c  jz      short loc_14002FAC4
0x14002fa9e  cmp     byte ptr [rcx+29h], 1
0x14002faa2  jb      short loc_14002FAC4
0x14002faa4  mov     rax, [rsi+1A8h]
0x14002faab  mov     r9, r15
0x14002faae  mov     rcx, [rcx+18h]
0x14002fab2  add     rax, 60h ; '`'
0x14002fab6  mov     [rsp+98h+var_70], ebp
0x14002faba  mov     [rsp+98h+pContext], rax
0x14002fabf  call    WPP_SF_qZL
0x14002fac4  mov     qword ptr [r15+28h], 0
0x14002facc  mov     rdx, r15
0x14002facf  mov     rcx, rsi
0x14002fad2  mov     qword ptr [rsi+1E0h], 0
0x14002fadd  call    SmbCeDecrementActiveVNetRootsOnVNetRootContext
0x14002fae2  mov     rcx, rsi; BugCheckParameter2
0x14002fae5  call    SmbCeDereferenceVNetRootContext
0x14002faea  neg     r12b
0x14002faed  mov     [r14+118h], ebp
0x14002faf4  sbb     eax, eax
0x14002faf6  and     eax, ebp
0x14002faf8  mov     [r14+11Ch], eax
0x14002faff  mov     r9, [r14+110h]; Routine
0x14002fb06  lea     r8, [r14+0C8h]; pWorkQueueItem
0x14002fb0d  mov     rcx, [rsp+98h+pMRxDeviceObject]; pMRxDeviceObject
0x14002fb15  xor     edx, edx; WorkQueueType
0x14002fb17  mov     [rsp+98h+pContext], r14; pContext
0x14002fb1c  call    cs:__imp_RxPostToWorkerThread
0x14002fb23  nop     dword ptr [rax+rax+00h]
0x14002fb28  add     rsp, 58h
0x14002fb2c  pop     r15
0x14002fb2e  pop     r14
0x14002fb30  pop     r13
0x14002fb32  pop     r12
0x14002fb34  pop     rdi
0x14002fb35  pop     rsi
0x14002fb36  pop     rbp
0x14002fb37  pop     rbx
0x14002fb38  retn
0x14002fb3a  cmp     dword ptr [r14+11Ch], 0C00000CCh
0x14002fb45  jnz     short loc_14002FB67
0x14002fb47  test    [rdi+0B0h], ebx
0x14002fb4d  jz      short loc_14002FB67
0x14002fb4f  cmp     byte ptr [rdi+0BDh], 0
0x14002fb56  jnz     short loc_14002FB67
0x14002fb58  mov     rcx, [rdi+58h]
0x14002fb5c  xor     edx, edx
0x14002fb5e  lea     r8d, [rdx+5]
0x14002fb62  call    SmbCeSuspendServerConnections
0x14002fb67  mov     eax, cs:?globalMappingLuid@?1??RxIsGlobalMappingLuid@@9@9; `RxIsGlobalMappingLuid'::`2'::globalMappingLuid
0x14002fb6d  mov     [r15+28h], rsi
0x14002fb71  mov     rcx, [rsi+1A0h]
0x14002fb78  mov     [rsi+1E0h], r15
0x14002fb7f  cmp     [rcx+60h], eax
0x14002fb82  jnz     loc_14002FAEA
0x14002fb88  mov     eax, cs:dword_14007025C
0x14002fb8e  cmp     [rcx+64h], eax
0x14002fb91  jnz     loc_14002FAEA
0x14002fb97  bts     dword ptr [r15+38h], 8
0x14002fb9d  jmp     loc_14002FAEA
```
