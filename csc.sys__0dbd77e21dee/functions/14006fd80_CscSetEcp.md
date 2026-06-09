# CscSetEcp

- ea: `0x14006fd80`
- end: `0x14006ff5a`
- name: `CscSetEcp`
- size: `474`
- prototype: `__int64 __fastcall(PIRP Irp, LPCGUID EcpType)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14006f2ec`
- `0x14006f360`

## callees

- `0x14001a5b4`
- `0x14006fd80`

## import_xrefs

- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x14006fe19`
- `ntoskrnl!FsRtlFreeExtraCreateParameterList` at `0x14006fe19`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x14006fe7a`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x14006fecd`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x14006fe7a`
- `ntoskrnl!FsRtlInsertExtraCreateParameter` at `0x14006fecd`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x14006fe4d`
- `ntoskrnl!FsRtlAllocateExtraCreateParameter` at `0x14006fe4d`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x14006fde0`
- `ntoskrnl!FsRtlAllocateExtraCreateParameterList` at `0x14006fde0`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x14006feb9`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x14006fef4`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x14006feb9`
- `ntoskrnl!FsRtlFreeExtraCreateParameter` at `0x14006fef4`
- `ntoskrnl!IoSetIrpExtraCreateParameter` at `0x14006fe03`
- `ntoskrnl!IoSetIrpExtraCreateParameter` at `0x14006fe03`
- `ntoskrnl!FsRtlRemoveExtraCreateParameter` at `0x14006fea5`
- `ntoskrnl!FsRtlRemoveExtraCreateParameter` at `0x14006fea5`
- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x14006fdb7`
- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x14006fdb7`

## pseudocode

```c
__int64 __fastcall CscSetEcp(PIRP Irp, LPCGUID EcpType, _BYTE *a3)
{
  NTSTATUS IrpExtraCreateParameter; // ebx
  PVOID v7; // rcx
  PVOID EcpContext; // [rsp+40h] [rbp-10h] BYREF
  PVOID v10; // [rsp+48h] [rbp-8h] BYREF
  struct _ECP_LIST *ExtraCreateParameter; // [rsp+88h] [rbp+38h] BYREF

  ExtraCreateParameter = 0;
  EcpContext = 0;
  IrpExtraCreateParameter = IoGetIrpExtraCreateParameter(Irp, &ExtraCreateParameter);
  if ( IrpExtraCreateParameter >= 0 )
  {
    if ( !ExtraCreateParameter )
    {
      IrpExtraCreateParameter = FsRtlAllocateExtraCreateParameterList(0, &ExtraCreateParameter);
      if ( IrpExtraCreateParameter < 0 )
        goto LABEL_12;
      IrpExtraCreateParameter = IoSetIrpExtraCreateParameter(Irp, ExtraCreateParameter);
      if ( IrpExtraCreateParameter < 0 )
      {
        FsRtlFreeExtraCreateParameterList(ExtraCreateParameter);
        goto LABEL_12;
      }
    }
    IrpExtraCreateParameter = FsRtlAllocateExtraCreateParameter(EcpType, 1u, 0, 0, 0x63457343u, &EcpContext);
    if ( IrpExtraCreateParameter >= 0 )
    {
      *(_BYTE *)EcpContext = *a3;
      IrpExtraCreateParameter = FsRtlInsertExtraCreateParameter(ExtraCreateParameter, EcpContext);
      if ( IrpExtraCreateParameter == -1073741811 )
      {
        v10 = 0;
        if ( FsRtlRemoveExtraCreateParameter(ExtraCreateParameter, EcpType, &v10, 0) < 0 )
        {
LABEL_11:
          IrpExtraCreateParameter = -1073741595;
          goto LABEL_12;
        }
        FsRtlFreeExtraCreateParameter(v10);
        IrpExtraCreateParameter = FsRtlInsertExtraCreateParameter(ExtraCreateParameter, EcpContext);
      }
      if ( IrpExtraCreateParameter >= 0 )
      {
LABEL_14:
        v7 = EcpContext;
        goto LABEL_15;
      }
      goto LABEL_11;
    }
  }
LABEL_12:
  v7 = EcpContext;
  if ( EcpContext )
  {
    FsRtlFreeExtraCreateParameter(EcpContext);
    goto LABEL_14;
  }
LABEL_15:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_qqDD(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_f74abd63425539499d784964bfbadaaa_Traceguids, Irp, v7);
  return (unsigned int)IrpExtraCreateParameter;
}

```

## disassembly

```asm
0x14006fd80  mov     [rsp-18h+arg_0], rbx
0x14006fd85  mov     [rsp-18h+arg_8], rsi
0x14006fd8a  mov     [rsp-18h+ExtraCreateParameter], r9
0x14006fd8f  push    rbp
0x14006fd90  push    rdi
0x14006fd91  push    r14
0x14006fd93  mov     rbp, rsp
0x14006fd96  sub     rsp, 50h
0x14006fd9a  mov     rdi, rdx
0x14006fd9d  mov     [rbp+ExtraCreateParameter], 0
0x14006fda5  lea     rdx, [rbp+ExtraCreateParameter]; ExtraCreateParameter
0x14006fda9  mov     [rbp+var_10], 0
0x14006fdb1  mov     r14, r8
0x14006fdb4  mov     rsi, rcx
0x14006fdb7  call    cs:__imp_IoGetIrpExtraCreateParameter
0x14006fdbe  nop     dword ptr [rax+rax+00h]
0x14006fdc3  mov     ebx, eax
0x14006fdc5  test    eax, eax
0x14006fdc7  jns     short loc_14006FDD3
0x14006fdc9  mov     edi, 81h
0x14006fdce  jmp     loc_14006FEEB
0x14006fdd3  cmp     [rbp+ExtraCreateParameter], 0
0x14006fdd8  jnz     short loc_14006FE2F
0x14006fdda  lea     rdx, [rbp+ExtraCreateParameter]; EcpList
0x14006fdde  xor     ecx, ecx; Flags
0x14006fde0  call    cs:__imp_FsRtlAllocateExtraCreateParameterList
0x14006fde7  nop     dword ptr [rax+rax+00h]
0x14006fdec  mov     ebx, eax
0x14006fdee  test    eax, eax
0x14006fdf0  jns     short loc_14006FDFC
0x14006fdf2  mov     edi, 95h
0x14006fdf7  jmp     loc_14006FEEB
0x14006fdfc  mov     rdx, [rbp+ExtraCreateParameter]; ExtraCreateParameter
0x14006fe00  mov     rcx, rsi; Irp
0x14006fe03  call    cs:__imp_IoSetIrpExtraCreateParameter
0x14006fe0a  nop     dword ptr [rax+rax+00h]
0x14006fe0f  mov     ebx, eax
0x14006fe11  test    eax, eax
0x14006fe13  jns     short loc_14006FE2F
0x14006fe15  mov     rcx, [rbp+ExtraCreateParameter]; EcpList
0x14006fe19  call    cs:__imp_FsRtlFreeExtraCreateParameterList
0x14006fe20  nop     dword ptr [rax+rax+00h]
0x14006fe25  mov     edi, 0BFh
0x14006fe2a  jmp     loc_14006FEEB
0x14006fe2f  xor     r9d, r9d; CleanupCallback
0x14006fe32  lea     rax, [rbp+var_10]
0x14006fe36  mov     [rsp+50h+EcpContext], rax; EcpContext
0x14006fe3b  xor     r8d, r8d; Flags
0x14006fe3e  mov     rcx, rdi; EcpType
0x14006fe41  mov     [rsp+50h+PoolTag], 63457343h; PoolTag
0x14006fe49  lea     edx, [r9+1]; SizeOfContext
0x14006fe4d  call    cs:__imp_FsRtlAllocateExtraCreateParameter
0x14006fe54  nop     dword ptr [rax+rax+00h]
0x14006fe59  mov     ebx, eax
0x14006fe5b  test    eax, eax
0x14006fe5d  jns     short loc_14006FE69
0x14006fe5f  mov     edi, 0D1h
0x14006fe64  jmp     loc_14006FEEB
0x14006fe69  mov     cl, [r14]
0x14006fe6c  mov     rax, [rbp+var_10]
0x14006fe70  mov     [rax], cl
0x14006fe72  mov     rdx, [rbp+var_10]; EcpContext
0x14006fe76  mov     rcx, [rbp+ExtraCreateParameter]; EcpList
0x14006fe7a  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x14006fe81  nop     dword ptr [rax+rax+00h]
0x14006fe86  mov     ebx, eax
0x14006fe88  cmp     eax, 0C000000Dh
0x14006fe8d  jnz     short loc_14006FEDB
0x14006fe8f  mov     rcx, [rbp+ExtraCreateParameter]; EcpList
0x14006fe93  lea     r8, [rbp+var_8]; EcpContext
0x14006fe97  xor     r9d, r9d; EcpContextSize
0x14006fe9a  mov     [rbp+var_8], 0
0x14006fea2  mov     rdx, rdi; EcpType
0x14006fea5  call    cs:__imp_FsRtlRemoveExtraCreateParameter
0x14006feac  nop     dword ptr [rax+rax+00h]
0x14006feb1  test    eax, eax
0x14006feb3  js      short loc_14006FEE1
0x14006feb5  mov     rcx, [rbp+var_8]; EcpContext
0x14006feb9  call    cs:__imp_FsRtlFreeExtraCreateParameter
0x14006fec0  nop     dword ptr [rax+rax+00h]
0x14006fec5  mov     rdx, [rbp+var_10]; EcpContext
0x14006fec9  mov     rcx, [rbp+ExtraCreateParameter]; EcpList
0x14006fecd  call    cs:__imp_FsRtlInsertExtraCreateParameter
0x14006fed4  nop     dword ptr [rax+rax+00h]
0x14006fed9  mov     ebx, eax
0x14006fedb  xor     edi, edi
0x14006fedd  test    ebx, ebx
0x14006fedf  jns     short loc_14006FF00
0x14006fee1  mov     ebx, 0C00000E5h
0x14006fee6  mov     edi, 106h
0x14006feeb  mov     rcx, [rbp+var_10]; EcpContext
0x14006feef  test    rcx, rcx
0x14006fef2  jz      short loc_14006FF04
0x14006fef4  call    cs:__imp_FsRtlFreeExtraCreateParameter
0x14006fefb  nop     dword ptr [rax+rax+00h]
0x14006ff00  mov     rcx, [rbp+var_10]
0x14006ff04  mov     r10, cs:WPP_GLOBAL_Control
0x14006ff0b  lea     rax, WPP_GLOBAL_Control
0x14006ff12  cmp     r10, rax
0x14006ff15  jz      short loc_14006FF44
0x14006ff17  mov     eax, [r10+2Ch]
0x14006ff1b  test    al, 40h
0x14006ff1d  jz      short loc_14006FF44
0x14006ff1f  mov     [rsp+50h+var_20], edi
0x14006ff23  lea     r8, WPP_f74abd63425539499d784964bfbadaaa_Traceguids
0x14006ff2a  mov     dword ptr [rsp+50h+EcpContext], ebx
0x14006ff2e  mov     edx, 0Ah
0x14006ff33  mov     qword ptr [rsp+50h+PoolTag], rcx
0x14006ff38  mov     r9, rsi
0x14006ff3b  mov     rcx, [r10+18h]
0x14006ff3f  call    WPP_SF_qqDD
0x14006ff44  mov     rsi, [rsp+50h+arg_8]
0x14006ff49  mov     eax, ebx
0x14006ff4b  mov     rbx, [rsp+50h+arg_0]
0x14006ff50  add     rsp, 50h
0x14006ff54  pop     r14
0x14006ff56  pop     rdi
0x14006ff57  pop     rbp
0x14006ff58  retn
```
