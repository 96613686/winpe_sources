# DfscConnOpenIpcConnectionCallin

- ea: `0x140026660`
- end: `0x140026ab3`
- name: `DfscConnOpenIpcConnectionCallin`
- size: `1107`
- prototype: `__int64 __fastcall(__int64, struct _UNICODE_STRING *, const void **, unsigned int, __int64, char, unsigned int *, PHANDLE FileHandle)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140026610`

## callees

- `0x14000219c`
- `0x1400027f8`
- `0x140006080`
- `0x140011a18`
- `0x1400131d0`
- `0x140026660`

## import_xrefs

- `ntoskrnl!IoGetSiloParameters` at `0x1400266f3`
- `ntoskrnl!IoGetSiloParameters` at `0x1400266f3`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x1400268b5`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x1400268b5`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x140026918`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x140026996`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x140026918`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x140026996`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x140026955`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x1400269ef`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x140026955`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x1400269ef`
- `ntoskrnl!IoCreateFileEx` at `0x1400267b9`
- `ntoskrnl!IoCreateFileEx` at `0x1400267b9`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x140026aa2`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x140026aa2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026a91`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026a91`

## pseudocode

```c
__int64 __fastcall DfscConnOpenIpcConnectionCallin(
        __int64 a1,
        struct _UNICODE_STRING *a2,
        const void **a3,
        unsigned int a4,
        __int64 a5,
        char a6,
        unsigned int *a7,
        PHANDLE FileHandle)
{
  int v10; // r13d
  __int64 SiloParameters; // rax
  __int64 v12; // rbx
  void *EaBuffer; // rcx
  ULONG CreateOptions; // edi
  unsigned int *v15; // r14
  NTSTATUS Status; // esi
  __int64 v17; // rax
  __int64 v18; // rdx
  wchar_t *v20; // rcx
  const char *v21; // rax
  ULONG EaLength; // eax
  int v23; // eax
  char *v24; // rax
  int Eas; // eax
  __int128 v26; // [rsp+90h] [rbp-78h] BYREF
  _IO_DRIVER_CREATE_CONTEXT DriverContext; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v28; // [rsp+C0h] [rbp-48h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C8h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D8h] [rbp-30h] BYREF
  PVOID v31; // [rsp+148h] [rbp+40h] BYREF
  PVOID EcpContext; // [rsp+150h] [rbp+48h] BYREF
  ULONG v33; // [rsp+160h] [rbp+58h]

  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  EcpContext = 0;
  v31 = 0;
  v10 = (int)a2;
  v33 = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = a2;
  v28 = 1;
  memset(&DriverContext, 0, sizeof(DriverContext));
  DriverContext.Size = 40;
  IoStatusBlock = 0;
  v26 = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( a1 )
  {
    SiloParameters = IoGetSiloParameters(*(_QWORD *)(*(_QWORD *)(a1 + 184) + 48LL));
    if ( SiloParameters )
      v28 = *(_QWORD *)(SiloParameters + 8);
    else
      v28 = 0;
  }
  v12 = a5;
  if ( !a4 || (Status = FsRtlAllocateExtraCreateParameterList(0, &DriverContext.ExtraCreateParameter)) == 0 )
  {
    if ( a3 )
    {
      v23 = *(unsigned __int16 *)a3;
      if ( (_WORD)v23 )
      {
        if ( (a4 & 1) != 0 )
        {
          Status = FsRtlAllocateExtraCreateParameter(
                     &GUID_ECP_DOMAIN_SERVICE_NAME_CONTEXT,
                     v23 + 2,
                     0,
                     0,
                     0x4A436644u,
                     &EcpContext);
          if ( Status )
            goto LABEL_15;
          *(_WORD *)EcpContext = *(_WORD *)a3;
          memmove((char *)EcpContext + 2, a3[1], *(unsigned __int16 *)a3);
          if ( FsRtlInsertExtraCreateParameter(DriverContext.ExtraCreateParameter, EcpContext) )
            goto LABEL_35;
        }
      }
    }
    if ( a4 )
    {
      Status = FsRtlAllocateExtraCreateParameter(&GUID_ECP_NETWORK_OPEN_CONTEXT, 0x1Cu, 0, 0, 0x4A436644u, &v31);
      if ( Status )
        goto LABEL_15;
      v24 = (char *)v31;
      *(_OWORD *)v31 = 0;
      *(_OWORD *)(v24 + 12) = 0;
      *(_WORD *)v31 = 28;
      *((_WORD *)v31 + 1) = 0;
      *((_DWORD *)v31 + 2) = DfscGetNetworkOpenEcpIntegrityLevelFromHardeningCapabilities(a4);
      *((_DWORD *)v31 + 3) = 8 * (a4 & 1);
      if ( FsRtlInsertExtraCreateParameter(DriverContext.ExtraCreateParameter, v31) )
      {
LABEL_35:
        Status = -1073741595;
        goto LABEL_15;
      }
    }
    EaBuffer = (void *)(v12 + 80);
    CreateOptions = 1184;
    if ( !a6 )
      CreateOptions = 160;
    if ( v12 )
    {
      EaLength = *(_DWORD *)(v12 + 72);
    }
    else
    {
      EaBuffer = 0;
      EaLength = 0;
    }
    v15 = a7;
    if ( a7 )
    {
      if ( a7[1] )
      {
        Eas = DfscCreateEas(0, v12, (char *)a7 + *a7);
        Status = Eas;
        if ( Eas < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
          {
            WPP_SF_D(
              WPP_GLOBAL_Control->AttachedDevice,
              10,
              WPP_d29483b364bf358e773d59db54935b3a_Traceguids,
              (unsigned int)Eas);
          }
          goto LABEL_15;
        }
        EaLength = v33;
        EaBuffer = 0;
      }
      CreateOptions |= v15[2];
    }
    Status = IoCreateFileEx(
               FileHandle,
               0x100000u,
               &ObjectAttributes,
               &IoStatusBlock,
               0,
               0x80u,
               7u,
               3u,
               CreateOptions,
               EaBuffer,
               EaLength,
               CreateFileTypeNone,
               0,
               0,
               &DriverContext);
    if ( Status >= 0 )
      Status = IoStatusBlock.Status;
  }
LABEL_15:
  if ( DriverContext.ExtraCreateParameter )
    FsRtlFreeExtraCreateParameterList(DriverContext.ExtraCreateParameter);
  v17 = v12 + 80;
  if ( !v12 )
    v17 = 0;
  if ( v17 )
  {
    v18 = *(unsigned __int8 *)(v17 + 5) + 9LL;
    WORD1(v26) = *(_WORD *)(v17 + 6);
    LOWORD(v26) = WORD1(v26);
    *((_QWORD *)&v26 + 1) = v17 + v18;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 )
  {
    v20 = (wchar_t *)&v26;
    if ( v17 )
    {
      v21 = (const char *)(v17 + 8);
    }
    else
    {
      v20 = DfscDefaultLogString;
      v21 = "<Def>";
    }
    WPP_SF_ZqsZZD(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)WPP_GLOBAL_Control,
      (unsigned int)DfscDefaultLogString,
      v10,
      v12,
      (__int64)v21,
      (__int64)v20,
      (__int64)a3,
      Status);
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140026660  mov     rax, rsp
0x140026663  push    rbp
0x140026664  push    rbx
0x140026665  push    r12
0x140026667  push    r13
0x140026669  lea     rbp, [rax-38h]
0x14002666d  sub     rsp, 118h
0x140026674  mov     [rax-28h], rdi
0x140026678  xorps   xmm1, xmm1
0x14002667b  mov     [rax-30h], r14
0x14002667f  xorps   xmm0, xmm0
0x140026682  xor     r14d, r14d
0x140026685  mov     [rax-38h], r15
0x140026689  mov     qword ptr [rbp+30h+ObjectAttributes.Length], 30h ; '0'
0x140026691  mov     eax, 28h ; '('
0x140026696  mov     qword ptr [rbp+30h+ObjectAttributes.Attributes], 240h
0x14002669e  mov     edi, r9d
0x1400266a1  mov     [rbp+30h+EcpContext], r14
0x1400266a5  mov     r12, r8
0x1400266a8  mov     [rbp+30h+arg_0], r14
0x1400266ac  mov     r13, rdx
0x1400266af  mov     [rbp+30h+var_B0], r14
0x1400266b3  mov     r15d, r14d
0x1400266b6  mov     [rbp+30h+arg_18], r14d
0x1400266ba  mov     [rbp+30h+ObjectAttributes.RootDirectory], r14
0x1400266be  mov     [rbp+30h+ObjectAttributes.ObjectName], rdx
0x1400266c2  mov     [rbp+30h+var_78], 1
0x1400266ca  movups  xmmword ptr [rbp+30h+DriverContext.Size], xmm1
0x1400266ce  mov     [rbp+30h+DriverContext.Size], ax
0x1400266d2  movups  xmmword ptr [rbp+30h+IoStatusBlock], xmm0
0x1400266d6  movups  [rbp+30h+var_A8], xmm1
0x1400266da  movdqu  xmmword ptr [rbp-10h], xmm0
0x1400266df  movups  xmmword ptr [rbp+30h+DriverContext.DeviceObjectHint], xmm1
0x1400266e3  test    rcx, rcx
0x1400266e6  jz      short loc_14002670C
0x1400266e8  mov     rcx, [rcx+0B8h]
0x1400266ef  mov     rcx, [rcx+30h]
0x1400266f3  call    cs:__imp_IoGetSiloParameters
0x1400266fa  nop     dword ptr [rax+rax+00h]
0x1400266ff  test    rax, rax
0x140026702  jnz     loc_14002685B
0x140026708  mov     [rbp+30h+var_78], r14
0x14002670c  mov     rbx, [rbp+30h+arg_20]
0x140026710  mov     [rsp+130h+arg_10], rsi
0x140026718  test    edi, edi
0x14002671a  jnz     loc_1400268AF
0x140026720  test    r12, r12
0x140026723  jnz     loc_1400268DF
0x140026729  test    edi, edi
0x14002672b  jnz     loc_140026973
0x140026731  cmp     [rbp+30h+arg_28], r14b
0x140026735  lea     rcx, [rbx+50h]
0x140026739  mov     edi, 4A0h
0x14002673e  mov     eax, 0A0h
0x140026743  cmovz   edi, eax
0x140026746  test    rbx, rbx
0x140026749  cmovz   rcx, r14
0x14002674d  jz      loc_1400268D7
0x140026753  mov     eax, [rbx+48h]
0x140026756  mov     r14, [rbp+30h+arg_30]
0x14002675a  test    r14, r14
0x14002675d  jnz     loc_140026A08
0x140026763  xor     r14d, r14d
0x140026766  lea     rdx, [rbp+30h+DriverContext]
0x14002676a  mov     [rsp+70h], rdx; DriverContext
0x14002676f  lea     r9, [rbp+30h+IoStatusBlock]; IoStatusBlock
0x140026773  mov     [rsp+130h+Options], r14d; Options
0x140026778  lea     r8, [rbp+30h+ObjectAttributes]; ObjectAttributes
0x14002677c  mov     [rsp+130h+InternalParameters], r14; InternalParameters
0x140026781  mov     edx, 100000h; DesiredAccess
0x140026786  mov     [rsp+130h+CreateFileType], r14d; CreateFileType
0x14002678b  mov     [rsp+130h+EaLength], eax; EaLength
0x14002678f  mov     [rsp+130h+EaBuffer], rcx; EaBuffer
0x140026794  mov     rcx, [rbp+30h+FileHandle]; FileHandle
0x140026798  mov     [rsp+130h+CreateOptions], edi; CreateOptions
0x14002679c  mov     [rsp+130h+Disposition], 3; Disposition
0x1400267a4  mov     [rsp+130h+ShareAccess], 7; ShareAccess
0x1400267ac  mov     [rsp+130h+FileAttributes], 80h; FileAttributes
0x1400267b4  mov     [rsp+130h+AllocationSize], r14; AllocationSize
0x1400267b9  call    cs:__imp_IoCreateFileEx
0x1400267c0  nop     dword ptr [rax+rax+00h]
0x1400267c5  test    eax, eax
0x1400267c7  lea     rdi, WPP_GLOBAL_Control
0x1400267ce  mov     esi, eax
0x1400267d0  cmovns  esi, dword ptr [rbp+30h+IoStatusBlock]
0x1400267d4  test    r15, r15
0x1400267d7  jnz     loc_140026A8C
0x1400267dd  mov     rcx, [rbp+30h+DriverContext.ExtraCreateParameter]; EcpList
0x1400267e1  mov     r15, [rsp+130h+var_30]
0x1400267e9  test    rcx, rcx
0x1400267ec  jnz     loc_140026AA2
0x1400267f2  test    rbx, rbx
0x1400267f5  lea     rax, [rbx+50h]
0x1400267f9  cmovz   rax, r14
0x1400267fd  mov     r14, [rsp+130h+var_28]
0x140026805  test    rax, rax
0x140026808  jz      short loc_140026825
0x14002680a  movzx   ecx, word ptr [rax+6]
0x14002680e  movzx   edx, byte ptr [rax+5]
0x140026812  add     rdx, 9
0x140026816  mov     word ptr [rbp+30h+var_A8+2], cx
0x14002681a  add     rdx, rax
0x14002681d  mov     word ptr [rbp+30h+var_A8], cx
0x140026821  mov     qword ptr [rbp+30h+var_A8+8], rdx
0x140026825  mov     rdx, cs:WPP_GLOBAL_Control
0x14002682c  cmp     rdx, rdi
0x14002682f  mov     rdi, [rsp+110h]
0x140026837  jz      short loc_140026842
0x140026839  test    dword ptr [rdx+2Ch], 400000h
0x140026840  jnz     short loc_140026868
0x140026842  mov     eax, esi
0x140026844  mov     rsi, [rsp+130h+arg_10]
0x14002684c  add     rsp, 118h
0x140026853  pop     r13
0x140026855  pop     r12
0x140026857  pop     rbx
0x140026858  pop     rbp
0x140026859  retn
0x14002685b  mov     rax, [rax+8]
0x14002685f  mov     [rbp+30h+var_78], rax
0x140026863  jmp     loc_14002670C
0x140026868  test    rax, rax
0x14002686b  lea     r8, DfscDefaultLogString; "\n\n"
0x140026872  lea     rcx, [rbp+30h+var_A8]
0x140026876  cmovz   rcx, r8
0x14002687a  jz      short loc_1400268A6
0x14002687c  add     rax, 8
0x140026880  mov     [rsp+130h+CreateOptions], esi
0x140026884  mov     r9, r13
0x140026887  mov     qword ptr [rsp+130h+Disposition], r12
0x14002688c  mov     qword ptr [rsp+130h+ShareAccess], rcx
0x140026891  mov     rcx, [rdx+18h]
0x140026895  mov     qword ptr [rsp+130h+FileAttributes], rax
0x14002689a  mov     [rsp+130h+AllocationSize], rbx
0x14002689f  call    WPP_SF_ZqsZZD
0x1400268a4  jmp     short loc_140026842
0x1400268a6  lea     rax, aDef_0; "<Def>"
0x1400268ad  jmp     short loc_140026880
0x1400268af  lea     rdx, [rbp+30h+DriverContext.ExtraCreateParameter]; EcpList
0x1400268b3  xor     ecx, ecx; Flags
0x1400268b5  call    cs:__imp_FsRtlAllocateExtraCreateParameterList
0x1400268bc  nop     dword ptr [rax+rax+00h]
0x1400268c1  mov     esi, eax
0x1400268c3  test    eax, eax
0x1400268c5  jz      loc_140026720
0x1400268cb  lea     rdi, WPP_GLOBAL_Control
0x1400268d2  jmp     loc_1400267DD
0x1400268d7  mov     eax, r14d
0x1400268da  jmp     loc_140026756
0x1400268df  movzx   eax, word ptr [r12]
0x1400268e4  test    ax, ax
0x1400268e7  jz      loc_140026729
0x1400268ed  test    dil, 1
0x1400268f1  jz      loc_140026729
0x1400268f7  lea     edx, [rax+2]; SizeOfContext
0x1400268fa  xor     r9d, r9d; CleanupCallback
0x1400268fd  lea     rax, [rbp+30h+EcpContext]
0x140026901  xor     r8d, r8d; Flags
0x140026904  mov     qword ptr [rsp+130h+FileAttributes], rax; EcpContext
0x140026909  lea     rcx, GUID_ECP_DOMAIN_SERVICE_NAME_CONTEXT; EcpType
0x140026910  mov     dword ptr [rsp+130h+AllocationSize], 4A436644h; PoolTag
0x140026918  call    cs:__imp_FsRtlAllocateExtraCreateParameter
0x14002691f  nop     dword ptr [rax+rax+00h]
0x140026924  mov     esi, eax
0x140026926  test    eax, eax
0x140026928  jnz     short loc_1400268CB
0x14002692a  movzx   ecx, word ptr [r12]
0x14002692f  mov     rax, [rbp+30h+EcpContext]
0x140026933  mov     [rax], cx
0x140026936  mov     rcx, [rbp+30h+EcpContext]
0x14002693a  movzx   r8d, word ptr [r12]; Size
0x14002693f  add     rcx, 2; void *
0x140026943  mov     rdx, [r12+8]; Src
0x140026948  call    memmove
0x14002694d  mov     rdx, [rbp+30h+EcpContext]; EcpContext
0x140026951  mov     rcx, [rbp+30h+DriverContext.ExtraCreateParameter]; EcpList
0x140026955  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x14002695c  nop     dword ptr [rax+rax+00h]
0x140026961  test    eax, eax
0x140026963  jz      loc_140026729
0x140026969  mov     esi, 0C00000E5h
0x14002696e  jmp     loc_1400268CB
0x140026973  lea     rax, [rbp+30h+arg_0]
0x140026977  xor     r9d, r9d; CleanupCallback
0x14002697a  mov     qword ptr [rsp+130h+FileAttributes], rax; EcpContext
0x14002697f  lea     rcx, GUID_ECP_NETWORK_OPEN_CONTEXT; EcpType
0x140026986  xor     r8d, r8d; Flags
0x140026989  mov     dword ptr [rsp+130h+AllocationSize], 4A436644h; PoolTag
0x140026991  mov     edx, 1Ch; SizeOfContext
0x140026996  call    cs:__imp_FsRtlAllocateExtraCreateParameter
0x14002699d  nop     dword ptr [rax+rax+00h]
0x1400269a2  mov     esi, eax
0x1400269a4  test    eax, eax
0x1400269a6  jnz     loc_1400268CB
0x1400269ac  mov     rax, [rbp+30h+arg_0]
0x1400269b0  xorps   xmm0, xmm0
0x1400269b3  mov     ecx, edi
0x1400269b5  movups  xmmword ptr [rax], xmm0
0x1400269b8  movups  xmmword ptr [rax+0Ch], xmm0
0x1400269bc  mov     rax, [rbp+30h+arg_0]
0x1400269c0  mov     word ptr [rax], 1Ch
0x1400269c5  mov     rax, [rbp+30h+arg_0]
0x1400269c9  mov     [rax+2], r14w
0x1400269ce  call    DfscGetNetworkOpenEcpIntegrityLevelFromHardeningCapabilities
0x1400269d3  mov     rcx, [rbp+30h+arg_0]
0x1400269d7  and     edi, 1
0x1400269da  shl     edi, 3
0x1400269dd  mov     [rcx+8], eax
0x1400269e0  mov     rax, [rbp+30h+arg_0]
0x1400269e4  mov     [rax+0Ch], edi
0x1400269e7  mov     rdx, [rbp+30h+arg_0]; EcpContext
0x1400269eb  mov     rcx, [rbp+30h+DriverContext.ExtraCreateParameter]; EcpList
0x1400269ef  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x1400269f6  nop     dword ptr [rax+rax+00h]
0x1400269fb  test    eax, eax
0x1400269fd  jz      loc_140026731
0x140026a03  jmp     loc_140026969
0x140026a08  mov     r9d, [r14+4]
0x140026a0c  test    r9d, r9d
0x140026a0f  jz      short loc_140026A83
0x140026a11  mov     r8d, [r14]
0x140026a14  lea     rax, [rbp+30h+arg_18]
0x140026a18  mov     qword ptr [rsp+130h+FileAttributes], rax
0x140026a1d  add     r8, r14
0x140026a20  lea     rax, [rbp+30h+var_B0]
0x140026a24  mov     rdx, rbx
0x140026a27  xor     ecx, ecx
0x140026a29  mov     [rsp+130h+AllocationSize], rax
0x140026a2e  call    DfscCreateEas
0x140026a33  mov     esi, eax
0x140026a35  test    eax, eax
0x140026a37  jns     short loc_140026A79
0x140026a39  mov     rcx, cs:WPP_GLOBAL_Control
0x140026a40  lea     rdi, WPP_GLOBAL_Control
0x140026a47  cmp     rcx, rdi
0x140026a4a  jz      short loc_140026A6D
0x140026a4c  test    dword ptr [rcx+2Ch], 400000h
0x140026a53  jz      short loc_140026A6D
0x140026a55  mov     rcx, [rcx+18h]
0x140026a59  lea     r8, WPP_d29483b364bf358e773d59db54935b3a_Traceguids
0x140026a60  mov     edx, 0Ah
0x140026a65  mov     r9d, eax
0x140026a68  call    WPP_SF_D
0x140026a6d  mov     r15, [rbp+30h+var_B0]
0x140026a71  xor     r14d, r14d
0x140026a74  jmp     loc_1400267D4
0x140026a79  mov     r15, [rbp+30h+var_B0]
0x140026a7d  mov     eax, [rbp+30h+arg_18]
0x140026a80  mov     rcx, r15
0x140026a83  or      edi, [r14+8]
0x140026a87  jmp     loc_140026763
0x140026a8c  xor     edx, edx; Tag
0x140026a8e  mov     rcx, r15; P
0x140026a91  call    cs:__imp_ExFreePoolWithTag
0x140026a98  nop     dword ptr [rax+rax+00h]
0x140026a9d  jmp     loc_1400267DD
0x140026aa2  call    cs:__imp_FsRtlFreeExtraCreateParameterList
0x140026aa9  nop     dword ptr [rax+rax+00h]
0x140026aae  jmp     loc_1400267F2
```
