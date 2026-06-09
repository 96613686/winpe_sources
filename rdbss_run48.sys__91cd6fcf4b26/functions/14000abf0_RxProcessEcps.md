# RxProcessEcps

- ea: `0x14000abf0`
- end: `0x14000b0be`
- name: `RxProcessEcps`
- size: `1230`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000a830`

## callees

- `0x14000abf0`
- `0x140014ec0`
- `0x140015230`
- `0x140016e70`

## import_xrefs

- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14000ac58`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14000accf`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14000add8`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14000ae0e`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14000ae41`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14000ae6f`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14000ac58`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14000accf`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14000add8`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14000ae0e`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14000ae41`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14000ae6f`
- `ntoskrnl!FsRtlGetEcpListFromIrp` at `0x14000ac13`
- `ntoskrnl!FsRtlGetEcpListFromIrp` at `0x14000aca8`
- `ntoskrnl!FsRtlGetEcpListFromIrp` at `0x14000ac13`
- `ntoskrnl!FsRtlGetEcpListFromIrp` at `0x14000aca8`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x14000ae9f`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x14000ae9f`
- `ntoskrnl!FsRtlSetEcpListIntoIrp` at `0x14000aebc`
- `ntoskrnl!FsRtlSetEcpListIntoIrp` at `0x14000aebc`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x14000aee2`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x14000aee2`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x14000ad1b`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x14000ad1b`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x14000ad86`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x14000ad86`

## pseudocode

```c
__int64 __fastcall RxProcessEcps(__int64 a1)
{
  IRP *v2; // rcx
  struct _ECP_LIST *v3; // rcx
  __int64 v4; // rsi
  int v5; // r14d
  struct _ECP_LIST *v6; // rax
  NTSTATUS Parameter; // edi
  char *v8; // rax
  PVOID v9; // rax
  NTSTATUS ExtraCreateParameter; // eax
  PVOID v12; // r8
  PVOID v13; // r8
  PVOID EcpContext; // [rsp+70h] [rbp+38h] BYREF
  PVOID v15; // [rsp+78h] [rbp+40h] BYREF
  PECP_LIST v16; // [rsp+80h] [rbp+48h] BYREF
  PECP_LIST EcpList; // [rsp+88h] [rbp+50h] BYREF

  v2 = *(IRP **)(a1 + 40);
  EcpList = 0;
  FsRtlGetEcpListFromIrp(v2, &EcpList);
  v3 = EcpList;
  *(_QWORD *)(a1 + 688) = EcpList;
  if ( v3 )
  {
    if ( !*(_QWORD *)(a1 + 568) )
    {
      EcpContext = 0;
      ExtraCreateParameter = FsRtlFindExtraCreateParameter(v3, &DFSC_DFS_SHARE_CHECK_ECP_GUID, &EcpContext, 0);
      v3 = EcpList;
      if ( ExtraCreateParameter >= 0 )
        *(_BYTE *)(a1 + 749) |= 0x40u;
    }
    if ( v3 )
    {
      EcpContext = 0;
      if ( FsRtlFindExtraCreateParameter(v3, &GUID_ECP_DOMAIN_SERVICE_NAME_CONTEXT, &EcpContext, 0) >= 0 )
      {
        v13 = EcpContext;
        *(_QWORD *)(a1 + 680) = EcpContext;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 17, &WPP_a28743743bb83892c11d9270eb466b78_Traceguids, a1, v13);
        }
      }
      v3 = EcpList;
      if ( EcpList )
      {
        EcpContext = 0;
        if ( FsRtlFindExtraCreateParameter(EcpList, &GUID_ECP_OPEN_AS_BLOCK_DEVICE, &EcpContext, 0) >= 0
          && (*((_DWORD *)EcpContext + 7) & 1) != 0 )
        {
          *(_BYTE *)(a1 + 750) |= 0x50u;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 18, &WPP_a28743743bb83892c11d9270eb466b78_Traceguids, a1);
          }
        }
        v3 = EcpList;
        if ( EcpList )
        {
          if ( FsRtlFindExtraCreateParameter(EcpList, &GUID_ECP_RDBSS_FORCE_PER_SHARE_CONNECTION, 0, 0) >= 0 )
          {
            *(_BYTE *)(a1 + 750) |= 0x50u;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 19, &WPP_a28743743bb83892c11d9270eb466b78_Traceguids, a1);
            }
          }
          v3 = EcpList;
        }
      }
    }
  }
  EcpContext = 0;
  *(_QWORD *)(a1 + 848) = 0;
  if ( v3 )
  {
    if ( FsRtlFindExtraCreateParameter(v3, &GUID_ECP_SMB_TREE_CONNECT_CONTEXT, &EcpContext, 0) >= 0 )
    {
      v12 = EcpContext;
      *(_QWORD *)(a1 + 848) = EcpContext;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 10, &WPP_a28743743bb83892c11d9270eb466b78_Traceguids, a1, v12);
      }
    }
  }
  v4 = *(_QWORD *)(a1 + 40);
  v5 = 0;
  v16 = 0;
  v15 = 0;
  LODWORD(EcpContext) = 0;
  if ( **(_BYTE **)(v4 + 184) )
  {
    if ( (*(_BYTE *)(a1 + 749) & 0x20) == 0 )
      goto LABEL_11;
  }
  else if ( (*(_BYTE *)(a1 + 749) & 0x20) == 0 )
  {
    FsRtlGetEcpListFromIrp((PIRP)v4, &v16);
    v6 = v16;
    goto LABEL_7;
  }
  v6 = *(struct _ECP_LIST **)(a1 + 480);
  v16 = v6;
LABEL_7:
  if ( v6 )
  {
    Parameter = FsRtlFindExtraCreateParameter(v6, &GUID_ECP_NETWORK_OPEN_CONTEXT, &v15, (ULONG *)&EcpContext);
    if ( !Parameter )
    {
      if ( (unsigned int)EcpContext < 0x1C
        || (v9 = v15, *(_WORD *)v15 != 28)
        || *((_WORD *)v15 + 1)
        || *((int *)v15 + 1) > 2
        || *((int *)v15 + 2) > 4 )
      {
        v9 = 0;
        Parameter = -1073741811;
        v15 = 0;
        v5 = 128;
      }
LABEL_15:
      *(_QWORD *)(a1 + 672) = v9;
      if ( Parameter >= 0 )
        return (unsigned int)Parameter;
      goto LABEL_32;
    }
    v6 = v16;
  }
  v15 = 0;
  if ( !v6 && (*(_BYTE *)(a1 + 749) & 0x20) == 0 )
  {
    Parameter = FsRtlAllocateExtraCreateParameterList(0, &v16);
    if ( Parameter < 0 )
    {
      v5 = 150;
      *(_QWORD *)(a1 + 672) = v15;
      goto LABEL_32;
    }
    Parameter = FsRtlSetEcpListIntoIrp((PIRP)v4, v16);
    if ( Parameter < 0 )
    {
      FsRtlFreeExtraCreateParameterList(v16);
      v5 = 160;
      *(_QWORD *)(a1 + 672) = v15;
      v16 = 0;
      goto LABEL_32;
    }
    *(_QWORD *)(a1 + 688) = v16;
  }
LABEL_11:
  Parameter = FsRtlAllocateExtraCreateParameter(&GUID_ECP_NETWORK_OPEN_CONTEXT, 0x1Cu, 0, 0, 0x63457852u, &v15);
  v8 = (char *)v15;
  if ( Parameter >= 0 )
  {
    *(_OWORD *)v15 = 0;
    *(_OWORD *)(v8 + 12) = 0;
    *(_WORD *)v15 = 28;
    *((_WORD *)v15 + 1) = 0;
    *((_DWORD *)v15 + 1) = dbgInitialNetworkOpenLocation;
    *((_DWORD *)v15 + 2) = dbgInitialNetworkOpenIntegrity;
    *((_DWORD *)v15 + 4) = 0;
    *((_DWORD *)v15 + 5) = 0;
    if ( v16 )
      Parameter = FsRtlInsertExtraCreateParameter(v16, v15);
    v9 = v15;
    goto LABEL_15;
  }
  v5 = 183;
  *(_QWORD *)(a1 + 672) = v15;
LABEL_32:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_qDD(
      WPP_GLOBAL_Control->AttachedDevice,
      11,
      &WPP_a28743743bb83892c11d9270eb466b78_Traceguids,
      a1,
      Parameter,
      v5);
  }
  return (unsigned int)Parameter;
}

```

## disassembly

```asm
0x14000abf0  push    rbp
0x14000abf2  push    rbx
0x14000abf3  push    rsi
0x14000abf4  push    r12
0x14000abf6  push    r14
0x14000abf8  push    r15
0x14000abfa  mov     rbp, rsp
0x14000abfd  sub     rsp, 38h
0x14000ac01  mov     rbx, rcx
0x14000ac04  lea     rdx, [rbp+EcpList]; EcpList
0x14000ac08  mov     rcx, [rcx+28h]; Irp
0x14000ac0c  xor     r15d, r15d
0x14000ac0f  mov     [rbp+EcpList], r15
0x14000ac13  call    cs:__imp_FsRtlGetEcpListFromIrp
0x14000ac1a  nop     dword ptr [rax+rax+00h]
0x14000ac1f  mov     rcx, [rbp+EcpList]; EcpList
0x14000ac23  lea     r12, WPP_GLOBAL_Control
0x14000ac2a  mov     [rbx+2B0h], rcx
0x14000ac31  test    rcx, rcx
0x14000ac34  jnz     loc_14000ADBD
0x14000ac3a  mov     [rbp+EcpContext], r15
0x14000ac3e  mov     [rbx+350h], r15
0x14000ac45  test    rcx, rcx
0x14000ac48  jz      short loc_14000AC6C
0x14000ac4a  xor     r9d, r9d; EcpContextSize
0x14000ac4d  lea     r8, [rbp+EcpContext]; EcpContext
0x14000ac51  lea     rdx, GUID_ECP_SMB_TREE_CONNECT_CONTEXT; EcpType
0x14000ac58  call    cs:__imp_FsRtlFindExtraCreateParameter
0x14000ac5f  nop     dword ptr [rax+rax+00h]
0x14000ac64  test    eax, eax
0x14000ac66  jns     loc_14000AF6B
0x14000ac6c  mov     rsi, [rbx+28h]
0x14000ac70  mov     r14d, r15d
0x14000ac73  mov     [rbp+arg_10], r15
0x14000ac77  mov     [rbp+arg_8], r15
0x14000ac7b  mov     dword ptr [rbp+EcpContext], r15d
0x14000ac7f  mov     rax, [rsi+0B8h]
0x14000ac86  mov     [rsp+38h+var_8], rdi
0x14000ac8b  cmp     [rax], r14b
0x14000ac8e  jnz     loc_14000AF4E
0x14000ac94  test    byte ptr [rbx+2EDh], 20h
0x14000ac9b  jnz     loc_14000AF5B
0x14000aca1  lea     rdx, [rbp+arg_10]; EcpList
0x14000aca5  mov     rcx, rsi; Irp
0x14000aca8  call    cs:__imp_FsRtlGetEcpListFromIrp
0x14000acaf  nop     dword ptr [rax+rax+00h]
0x14000acb4  mov     rax, [rbp+arg_10]
0x14000acb8  test    rax, rax
0x14000acbb  jz      short loc_14000ACE9
0x14000acbd  lea     r9, [rbp+EcpContext]; EcpContextSize
0x14000acc1  mov     rcx, rax; EcpList
0x14000acc4  lea     r8, [rbp+arg_8]; EcpContext
0x14000acc8  lea     rdx, GUID_ECP_NETWORK_OPEN_CONTEXT; EcpType
0x14000accf  call    cs:__imp_FsRtlFindExtraCreateParameter
0x14000acd6  nop     dword ptr [rax+rax+00h]
0x14000acdb  mov     edi, eax
0x14000acdd  test    eax, eax
0x14000acdf  jz      loc_14000AFBD
0x14000ace5  mov     rax, [rbp+arg_10]
0x14000ace9  mov     [rbp+arg_8], r15
0x14000aced  test    rax, rax
0x14000acf0  jz      loc_14000AE8C
0x14000acf6  lea     rax, [rbp+arg_8]
0x14000acfa  mov     esi, 1Ch
0x14000acff  mov     [rsp+38h+var_10], rax; EcpContext
0x14000ad04  lea     rcx, GUID_ECP_NETWORK_OPEN_CONTEXT; EcpType
0x14000ad0b  mov     edx, esi; SizeOfContext
0x14000ad0d  mov     [rsp+38h+PoolTag], 63457852h; PoolTag
0x14000ad15  xor     r9d, r9d; CleanupCallback
0x14000ad18  xor     r8d, r8d; Flags
0x14000ad1b  call    cs:__imp_FsRtlAllocateExtraCreateParameter
0x14000ad22  nop     dword ptr [rax+rax+00h]
0x14000ad27  mov     edi, eax
0x14000ad29  test    eax, eax
0x14000ad2b  mov     rax, [rbp+arg_8]
0x14000ad2f  js      loc_14000B0AC
0x14000ad35  xorps   xmm0, xmm0
0x14000ad38  movups  xmmword ptr [rax], xmm0
0x14000ad3b  movups  xmmword ptr [rax+0Ch], xmm0
0x14000ad3f  mov     rax, [rbp+arg_8]
0x14000ad43  mov     [rax], si
0x14000ad46  mov     rax, [rbp+arg_8]
0x14000ad4a  mov     [rax+2], r15w
0x14000ad4f  mov     eax, cs:dbgInitialNetworkOpenLocation
0x14000ad55  mov     rcx, [rbp+arg_8]
0x14000ad59  mov     [rcx+4], eax
0x14000ad5c  mov     eax, cs:dbgInitialNetworkOpenIntegrity
0x14000ad62  mov     rcx, [rbp+arg_8]
0x14000ad66  mov     [rcx+8], eax
0x14000ad69  mov     rax, [rbp+arg_8]
0x14000ad6d  mov     [rax+10h], r15d
0x14000ad71  mov     rax, [rbp+arg_8]
0x14000ad75  mov     [rax+14h], r15d
0x14000ad79  mov     rcx, [rbp+arg_10]; EcpList
0x14000ad7d  test    rcx, rcx
0x14000ad80  jz      short loc_14000AD94
0x14000ad82  mov     rdx, [rbp+arg_8]; EcpContext
0x14000ad86  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x14000ad8d  nop     dword ptr [rax+rax+00h]
0x14000ad92  mov     edi, eax
0x14000ad94  mov     rax, [rbp+arg_8]
0x14000ad98  mov     [rbx+2A0h], rax
0x14000ad9f  test    edi, edi
0x14000ada1  js      loc_14000AF03
0x14000ada7  mov     eax, edi
0x14000ada9  mov     rdi, [rsp+38h+var_8]
0x14000adae  add     rsp, 38h
0x14000adb2  pop     r15
0x14000adb4  pop     r14
0x14000adb6  pop     r12
0x14000adb8  pop     rsi
0x14000adb9  pop     rbx
0x14000adba  pop     rbp
0x14000adbb  retn
0x14000adbd  cmp     [rbx+238h], r15
0x14000adc4  jnz     short loc_14000ADF3
0x14000adc6  xor     r9d, r9d; EcpContextSize
0x14000adc9  mov     [rbp+EcpContext], r15
0x14000adcd  lea     r8, [rbp+EcpContext]; EcpContext
0x14000add1  lea     rdx, DFSC_DFS_SHARE_CHECK_ECP_GUID; EcpType
0x14000add8  call    cs:__imp_FsRtlFindExtraCreateParameter
0x14000addf  nop     dword ptr [rax+rax+00h]
0x14000ade4  mov     rcx, [rbp+EcpList]; EcpList
0x14000ade8  test    eax, eax
0x14000adea  js      short loc_14000ADF3
0x14000adec  or      byte ptr [rbx+2EDh], 40h
0x14000adf3  test    rcx, rcx
0x14000adf6  jz      loc_14000AC3A
0x14000adfc  xor     r9d, r9d; EcpContextSize
0x14000adff  mov     [rbp+EcpContext], r15
0x14000ae03  lea     r8, [rbp+EcpContext]; EcpContext
0x14000ae07  lea     rdx, GUID_ECP_DOMAIN_SERVICE_NAME_CONTEXT; EcpType
0x14000ae0e  call    cs:__imp_FsRtlFindExtraCreateParameter
0x14000ae15  nop     dword ptr [rax+rax+00h]
0x14000ae1a  test    eax, eax
0x14000ae1c  jns     loc_14000AFFB
0x14000ae22  mov     rcx, [rbp+EcpList]; EcpList
0x14000ae26  test    rcx, rcx
0x14000ae29  jz      loc_14000AC3A
0x14000ae2f  xor     r9d, r9d; EcpContextSize
0x14000ae32  mov     [rbp+EcpContext], r15
0x14000ae36  lea     r8, [rbp+EcpContext]; EcpContext
0x14000ae3a  lea     rdx, GUID_ECP_OPEN_AS_BLOCK_DEVICE; EcpType
0x14000ae41  call    cs:__imp_FsRtlFindExtraCreateParameter
0x14000ae48  nop     dword ptr [rax+rax+00h]
0x14000ae4d  test    eax, eax
0x14000ae4f  jns     loc_140027462
0x14000ae55  mov     rcx, [rbp+EcpList]; EcpList
0x14000ae59  test    rcx, rcx
0x14000ae5c  jz      loc_14000AC3A
0x14000ae62  xor     r9d, r9d; EcpContextSize
0x14000ae65  lea     rdx, GUID_ECP_RDBSS_FORCE_PER_SHARE_CONNECTION; EcpType
0x14000ae6c  xor     r8d, r8d; EcpContext
0x14000ae6f  call    cs:__imp_FsRtlFindExtraCreateParameter
0x14000ae76  nop     dword ptr [rax+rax+00h]
0x14000ae7b  test    eax, eax
0x14000ae7d  jns     loc_14000B04D
0x14000ae83  mov     rcx, [rbp+EcpList]
0x14000ae87  jmp     loc_14000AC3A
0x14000ae8c  test    byte ptr [rbx+2EDh], 20h
0x14000ae93  jnz     loc_14000ACF6
0x14000ae99  lea     rdx, [rbp+arg_10]; EcpList
0x14000ae9d  xor     ecx, ecx; Flags
0x14000ae9f  call    cs:__imp_FsRtlAllocateExtraCreateParameterList
0x14000aea6  nop     dword ptr [rax+rax+00h]
0x14000aeab  mov     edi, eax
0x14000aead  test    eax, eax
0x14000aeaf  js      loc_14000B096
0x14000aeb5  mov     rdx, [rbp+arg_10]; EcpList
0x14000aeb9  mov     rcx, rsi; Irp
0x14000aebc  call    cs:__imp_FsRtlSetEcpListIntoIrp
0x14000aec3  nop     dword ptr [rax+rax+00h]
0x14000aec8  mov     edi, eax
0x14000aeca  test    eax, eax
0x14000aecc  js      short loc_14000AEDE
0x14000aece  mov     rax, [rbp+arg_10]
0x14000aed2  mov     [rbx+2B0h], rax
0x14000aed9  jmp     loc_14000ACF6
0x14000aede  mov     rcx, [rbp+arg_10]; EcpList
0x14000aee2  call    cs:__imp_FsRtlFreeExtraCreateParameterList
0x14000aee9  nop     dword ptr [rax+rax+00h]
0x14000aeee  mov     rax, [rbp+arg_8]
0x14000aef2  mov     r14d, 0A0h
0x14000aef8  mov     [rbx+2A0h], rax
0x14000aeff  mov     [rbp+arg_10], r15
0x14000af03  mov     rcx, cs:WPP_GLOBAL_Control
0x14000af0a  cmp     rcx, r12
0x14000af0d  jz      loc_14000ADA7
0x14000af13  mov     eax, [rcx+2Ch]
0x14000af16  test    al, 1
0x14000af18  jz      loc_14000ADA7
0x14000af1e  cmp     byte ptr [rcx+29h], 1
0x14000af22  jb      loc_14000ADA7
0x14000af28  mov     rcx, [rcx+18h]
0x14000af2c  lea     r8, WPP_a28743743bb83892c11d9270eb466b78_Traceguids
0x14000af33  mov     edx, 0Bh
0x14000af38  mov     dword ptr [rsp+38h+var_10], r14d
0x14000af3d  mov     r9, rbx
0x14000af40  mov     [rsp+38h+PoolTag], edi
0x14000af44  call    WPP_SF_qDD
0x14000af49  jmp     loc_14000ADA7
0x14000af4e  test    byte ptr [rbx+2EDh], 20h
0x14000af55  jz      loc_14000ACF6
0x14000af5b  mov     rax, [rbx+1E0h]
0x14000af62  mov     [rbp+arg_10], rax
0x14000af66  jmp     loc_14000ACB8
0x14000af6b  mov     r8, [rbp+EcpContext]
0x14000af6f  mov     [rbx+350h], r8
0x14000af76  mov     rcx, cs:WPP_GLOBAL_Control
0x14000af7d  cmp     rcx, r12
0x14000af80  jz      loc_14000AC6C
0x14000af86  mov     eax, [rcx+2Ch]
0x14000af89  test    al, 8
0x14000af8b  jz      loc_14000AC6C
0x14000af91  cmp     byte ptr [rcx+29h], 4
0x14000af95  jb      loc_14000AC6C
0x14000af9b  mov     rcx, [rcx+18h]
0x14000af9f  mov     edx, 0Ah
0x14000afa4  mov     qword ptr [rsp+38h+PoolTag], r8
0x14000afa9  mov     r9, rbx
0x14000afac  lea     r8, WPP_a28743743bb83892c11d9270eb466b78_Traceguids
0x14000afb3  call    WPP_SF_qq
0x14000afb8  jmp     loc_14000AC6C
0x14000afbd  cmp     dword ptr [rbp+EcpContext], 1Ch
0x14000afc1  jb      short loc_14000AFE4
0x14000afc3  mov     rax, [rbp+arg_8]
0x14000afc7  cmp     word ptr [rax], 1Ch
0x14000afcb  jnz     short loc_14000AFE4
0x14000afcd  cmp     [rax+2], r14w
0x14000afd2  jnz     short loc_14000AFE4
0x14000afd4  cmp     dword ptr [rax+4], 2
0x14000afd8  jg      short loc_14000AFE4
0x14000afda  cmp     dword ptr [rax+8], 4
0x14000afde  jle     loc_14000AD98
0x14000afe4  mov     rax, r15
0x14000afe7  mov     edi, 0C000000Dh
0x14000afec  mov     [rbp+arg_8], rax
0x14000aff0  mov     r14d, 80h
0x14000aff6  jmp     loc_14000AD98
0x14000affb  mov     r8, [rbp+EcpContext]
0x14000afff  mov     [rbx+2A8h], r8
0x14000b006  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b00d  cmp     rcx, r12
0x14000b010  jz      loc_14000AE22
0x14000b016  mov     eax, [rcx+2Ch]
0x14000b019  test    al, 8
0x14000b01b  jz      loc_14000AE22
0x14000b021  cmp     byte ptr [rcx+29h], 4
0x14000b025  jb      loc_14000AE22
0x14000b02b  mov     rcx, [rcx+18h]
0x14000b02f  mov     edx, 11h
0x14000b034  mov     qword ptr [rsp+38h+PoolTag], r8
0x14000b039  mov     r9, rbx
0x14000b03c  lea     r8, WPP_a28743743bb83892c11d9270eb466b78_Traceguids
0x14000b043  call    WPP_SF_qq
0x14000b048  jmp     loc_14000AE22
0x14000b04d  or      byte ptr [rbx+2EEh], 50h
0x14000b054  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b05b  cmp     rcx, r12
0x14000b05e  jz      loc_14000AE83
0x14000b064  mov     eax, [rcx+2Ch]
0x14000b067  test    al, 8
0x14000b069  jz      loc_14000AE83
0x14000b06f  cmp     byte ptr [rcx+29h], 4
0x14000b073  jb      loc_14000AE83
0x14000b079  mov     rcx, [rcx+18h]
0x14000b07d  lea     r8, WPP_a28743743bb83892c11d9270eb466b78_Traceguids
0x14000b084  mov     edx, 13h
0x14000b089  mov     r9, rbx
0x14000b08c  call    WPP_SF_q
0x14000b091  jmp     loc_14000AE83
0x14000b096  mov     rax, [rbp+arg_8]
0x14000b09a  mov     r14d, 96h
0x14000b0a0  mov     [rbx+2A0h], rax
0x14000b0a7  jmp     loc_14000AF03
0x14000b0ac  mov     r14d, 0B7h
0x14000b0b2  mov     [rbx+2A0h], rax
0x14000b0b9  jmp     loc_14000AF03
0x140027462  mov     rax, [rbp+EcpContext]
0x140027466  mov     ecx, [rax+1Ch]
0x140027469  test    cl, 1
0x14002746c  jz      loc_14000AE55
0x140027472  or      byte ptr [rbx+2EEh], 50h
0x140027479  mov     rcx, cs:WPP_GLOBAL_Control
0x140027480  cmp     rcx, r12
0x140027483  jz      loc_14000AE55
0x140027489  mov     eax, [rcx+2Ch]
0x14002748c  test    al, 8
0x14002748e  jz      loc_14000AE55
0x140027494  cmp     byte ptr [rcx+29h], 4
0x140027498  jb      loc_14000AE55
0x14002749e  mov     rcx, [rcx+18h]
0x1400274a2  lea     r8, WPP_a28743743bb83892c11d9270eb466b78_Traceguids
0x1400274a9  mov     edx, 12h
0x1400274ae  mov     r9, rbx
0x1400274b1  call    WPP_SF_q
0x1400274b6  nop
0x1400274b7  jmp     loc_14000AE55
```
