# RxSetReparsePointInformation

- ea: `0x14001aa54`
- end: `0x14001abb1`
- name: `RxSetReparsePointInformation`
- size: `349`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext, PIRP Irp, PFCB Fcb)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, loader_planting`

## callers

- `0x140045410`

## callees

- `0x140009b80`
- `0x14000f880`
- `0x140012030`
- `0x14001aa54`
- `0x14001b178`
- `0x1400465c8`
- `0x140057660`
- `0x140072a80`

## import_xrefs

- `ntoskrnl!FsRtlValidateReparsePointBuffer` at `0x14001aa8e`
- `ntoskrnl!FsRtlValidateReparsePointBuffer` at `0x14001aa8e`

## pseudocode

```c
__int64 __fastcall RxSetReparsePointInformation(PRX_CONTEXT RxContext, PIRP Irp, PFCB Fcb)
{
  struct _IRP *MasterIrp; // rbp
  NTSTATUS v7; // edi
  PMRX_FOBX pFobx; // r15
  NTSTATUS v9; // eax
  struct _FOBX *v10; // r9
  ULONG v11; // r8d
  const CHAR *v12; // r9
  const CHAR *SerialNumber; // [rsp+20h] [rbp-48h]
  ULONG SerialNumbera; // [rsp+20h] [rbp-48h]
  ULONG v16; // [rsp+28h] [rbp-40h]

  MasterIrp = Irp->AssociatedIrp.MasterIrp;
  if ( MasterIrp )
  {
    pFobx = RxContext->pFobx;
    v7 = FsRtlValidateReparsePointBuffer(
           Irp->Tail.Overlay.CurrentStackLocation->Parameters.Create.Options,
           (PREPARSE_DATA_BUFFER)Irp->AssociatedIrp.MasterIrp);
    if ( v7 >= 0 )
    {
      if ( *(_DWORD *)&MasterIrp->Type != -1610612724 || (*(_DWORD *)&pFobx[1].NodeTypeCode & 0x400) != 0 )
      {
        v9 = _RxAcquireFcb(Fcb, RxContext, 1u, 0, SerialNumber, v16);
        v7 = v9;
        if ( v9 >= 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_qqZ(
              WPP_GLOBAL_Control->AttachedDevice,
              38,
              (unsigned int)WPP_0631a9abaf7433de250bb1791161ea05_Traceguids,
              (_DWORD)Fcb,
              (char)pFobx->Context2,
              *((_QWORD *)pFobx->Context2 + 10));
          }
          *((_DWORD *)&Fcb->1 + 40) &= 0xFFBFF7FF;
          RxPurgeConflictingSrvOpens(Fcb, 0, 0);
          if ( Fcb->Header.NodeTypeCode == -5086 )
            RxDisableLocalBuffering(Fcb);
          LODWORD(RxContext->RdbssDbgExtension) = (__int64)RxContext->RdbssDbgExtension & 0xFFFFEFFD | 2;
          v7 = RxLowIoFsCtlShell(RxContext, Irp, Fcb, v10);
          if ( v7 >= 0 )
          {
            RxSetFcbNameTargetType(Fcb, 2);
            *(_DWORD *)&Fcb->FcbTableEntry.Path.Length |= 0x400u;
          }
          _RxReleaseFcb(RxContext, (PMRX_FCB)&Fcb->Header, v11, v12, SerialNumbera);
        }
        else if ( v9 == -1073741739 )
        {
          BYTE3(RxContext->RealDevice) = 1;
        }
      }
      else
      {
        return (unsigned int)-1073741790;
      }
    }
  }
  else
  {
    return (unsigned int)-1073741306;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14001aa54  push    rbx
0x14001aa56  push    rbp
0x14001aa57  push    rsi
0x14001aa58  push    rdi
0x14001aa59  push    r14
0x14001aa5b  push    r15
0x14001aa5d  sub     rsp, 38h
0x14001aa61  mov     rbp, [rdx+18h]
0x14001aa65  mov     rbx, r8
0x14001aa68  mov     r14, rdx
0x14001aa6b  mov     rsi, rcx
0x14001aa6e  test    rbp, rbp
0x14001aa71  jnz     short loc_14001AA7D
0x14001aa73  mov     edi, 0C0000206h
0x14001aa78  jmp     loc_14001ABA1
0x14001aa7d  mov     r15, [rcx+40h]
0x14001aa81  mov     rcx, [rdx+0B8h]
0x14001aa88  mov     rdx, rbp; ReparseBuffer
0x14001aa8b  mov     ecx, [rcx+10h]; BufferLength
0x14001aa8e  call    cs:__imp_FsRtlValidateReparsePointBuffer
0x14001aa95  nop     dword ptr [rax+rax+00h]
0x14001aa9a  mov     edi, eax
0x14001aa9c  test    eax, eax
0x14001aa9e  js      loc_14001ABA1
0x14001aaa4  cmp     dword ptr [rbp+0], 0A000000Ch
0x14001aaab  jnz     short loc_14001AAC1
0x14001aaad  test    dword ptr [r15+48h], 400h
0x14001aab5  jnz     short loc_14001AAC1
0x14001aab7  mov     edi, 0C0000022h
0x14001aabc  jmp     loc_14001ABA1
0x14001aac1  xor     r9d, r9d; LineNumber
0x14001aac4  mov     rdx, rsi; RxContext
0x14001aac7  mov     rcx, rbx; Fcb
0x14001aaca  lea     r8d, [r9+1]; Mode
0x14001aace  call    __RxAcquireFcb
0x14001aad3  mov     edi, eax
0x14001aad5  test    eax, eax
0x14001aad7  jns     short loc_14001AAED
0x14001aad9  cmp     eax, 0C0000055h
0x14001aade  jnz     loc_14001ABA1
0x14001aae4  mov     byte ptr [rsi+23h], 1
0x14001aae8  jmp     loc_14001ABA1
0x14001aaed  mov     rcx, cs:WPP_GLOBAL_Control
0x14001aaf4  lea     rax, WPP_GLOBAL_Control
0x14001aafb  mov     ebp, 2
0x14001ab00  cmp     rcx, rax
0x14001ab03  jz      short loc_14001AB3B
0x14001ab05  mov     eax, [rcx+2Ch]
0x14001ab08  test    bpl, al
0x14001ab0b  jz      short loc_14001AB3B
0x14001ab0d  cmp     [rcx+29h], bpl
0x14001ab11  jb      short loc_14001AB3B
0x14001ab13  mov     r8, [r15+20h]
0x14001ab17  lea     edx, [rbp+24h]
0x14001ab1a  mov     rcx, [rcx+18h]
0x14001ab1e  mov     r9, rbx
0x14001ab21  mov     rax, [r8+50h]
0x14001ab25  mov     qword ptr [rsp+68h+var_40], rax
0x14001ab2a  mov     qword ptr [rsp+68h+SerialNumber], r8; SerialNumber
0x14001ab2f  lea     r8, WPP_0631a9abaf7433de250bb1791161ea05_Traceguids
0x14001ab36  call    WPP_SF_qqZ
0x14001ab3b  and     dword ptr [rbx+0A0h], 0FFBFF7FFh
0x14001ab45  xor     r8d, r8d
0x14001ab48  xor     edx, edx
0x14001ab4a  mov     rcx, rbx
0x14001ab4d  call    RxPurgeConflictingSrvOpens
0x14001ab52  mov     eax, 0EC22h
0x14001ab57  cmp     [rbx], ax
0x14001ab5a  jnz     short loc_14001AB64
0x14001ab5c  mov     rcx, rbx; Fcb
0x14001ab5f  call    RxDisableLocalBuffering
0x14001ab64  mov     eax, [rsi+78h]
0x14001ab67  mov     r8, rbx; Fcb
0x14001ab6a  btr     eax, 0Ch
0x14001ab6e  mov     rdx, r14; Irp
0x14001ab71  or      eax, ebp
0x14001ab73  mov     rcx, rsi; RxContext
0x14001ab76  mov     [rsi+78h], eax
0x14001ab79  call    RxLowIoFsCtlShell
0x14001ab7e  mov     edi, eax
0x14001ab80  test    eax, eax
0x14001ab82  js      short loc_14001AB96
0x14001ab84  mov     edx, ebp
0x14001ab86  mov     rcx, rbx
0x14001ab89  call    RxSetFcbNameTargetType
0x14001ab8e  bts     dword ptr [rbx+0E8h], 0Ah
0x14001ab96  mov     rdx, rbx; MrxFcb
0x14001ab99  mov     rcx, rsi; RxContext
0x14001ab9c  call    __RxReleaseFcb
0x14001aba1  mov     eax, edi
0x14001aba3  add     rsp, 38h
0x14001aba7  pop     r15
0x14001aba9  pop     r14
0x14001abab  pop     rdi
0x14001abac  pop     rsi
0x14001abad  pop     rbp
0x14001abae  pop     rbx
0x14001abaf  retn
```
