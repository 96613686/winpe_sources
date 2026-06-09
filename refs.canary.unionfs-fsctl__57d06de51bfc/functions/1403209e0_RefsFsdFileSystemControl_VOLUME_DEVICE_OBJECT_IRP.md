# RefsFsdFileSystemControl(_VOLUME_DEVICE_OBJECT *,_IRP *)

- ea: `0x1403209e0`
- end: `0x140320d71`
- name: `?RefsFsdFileSystemControl@@YAJPEAU_VOLUME_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `913`
- prototype: `int(struct _VOLUME_DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x140039b60`
- `0x14003a520`
- `0x14003ec10`
- `0x14003fbe0`
- `0x14007dd30`
- `0x14008dbd0`
- `0x1400a648c`
- `0x1400b2b60`
- `0x1400ca788`
- `0x1401e9ce0`
- `0x1403209e0`
- `0x140320e78`
- `0x140321a64`
- `0x1403326dc`
- `0x1403389e4`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140320c34`
- `ntoskrnl!ObfDereferenceObject` at `0x140320c34`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140320adf`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140320adf`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140320a58`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140320a58`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x140320a74`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x140320a74`
- `ntoskrnl!IoClearActivityIdThread` at `0x140320d63`
- `ntoskrnl!IoClearActivityIdThread` at `0x140320d63`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140320d01`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140320d01`
- `ntoskrnl!KeSetEvent` at `0x140320c23`
- `ntoskrnl!KeSetEvent` at `0x140320c23`
- `ntoskrnl!IoIsOperationSynchronous` at `0x140320a48`
- `ntoskrnl!IoIsOperationSynchronous` at `0x140320a48`
- `ntoskrnl!FsRtlNotifyVolumeEventEx` at `0x140320c06`
- `ntoskrnl!FsRtlNotifyVolumeEventEx` at `0x140320c06`

## pseudocode

```c
__int64 __fastcall RefsFsdFileSystemControl(struct _VOLUME_DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _TOP_LEVEL_CONTEXT *v3; // r14
  int v4; // edx
  struct _IRP_CONTEXT *v5; // rbx
  __int64 v6; // r8
  const char *v7; // r9
  UCHAR MinorFunction; // al
  unsigned int v9; // esi
  BOOLEAN IsOperationSynchronous; // [rsp+20h] [rbp-F8h]
  struct _IRP_CONTEXT *v12; // [rsp+28h] [rbp-F0h] BYREF
  int v13; // [rsp+30h] [rbp-E8h]
  PFILE_OBJECT FileObject; // [rsp+38h] [rbp-E0h]
  struct _VCB *v15; // [rsp+40h] [rbp-D8h]
  struct _TOP_LEVEL_CONTEXT *v16; // [rsp+48h] [rbp-D0h]
  __int64 v17; // [rsp+50h] [rbp-C8h] BYREF
  union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *p_CurrentStackLocation; // [rsp+58h] [rbp-C0h]
  struct _IRP *v19; // [rsp+60h] [rbp-B8h]
  __int128 v20; // [rsp+68h] [rbp-B0h] BYREF
  __int64 v21; // [rsp+78h] [rbp-A0h]
  __int128 v22; // [rsp+80h] [rbp-98h] BYREF

  v19 = a2;
  v20 = 0;
  v21 = 0;
  v12 = 0;
  v22 = 0;
  v17 = 0;
  p_CurrentStackLocation = (union _IRP::$::$::$665C8370128C04AB892B069E6FB086E8::$8B5CD6CDFBAAB114E6B0B83ED2C2A4E9 *)&a2->Tail.Overlay.CurrentStackLocation;
  if ( a2->Tail.Overlay.CurrentStackLocation->FileObject )
    IsOperationSynchronous = IoIsOperationSynchronous(a2);
  else
    IsOperationSynchronous = 1;
  KeEnterCriticalRegion();
  v13 = IoPropagateActivityIdToThread(a2, &v22, &v17);
  v3 = RefsInitializeTopLevelIrp((struct _TOP_LEVEL_CONTEXT *)&v20, 0, 0);
  v16 = v3;
  RefsInitializeIrpContext(a2, IsOperationSynchronous, 1, &v12);
  if ( *((_QWORD *)v3 + 2) )
  {
    v5 = v12;
  }
  else
  {
    *((_DWORD *)v3 + 1) = 1397140410;
    v5 = v12;
    *((_QWORD *)v3 + 2) = v12;
    *((_QWORD *)v5 + 1) |= 0x100000uLL;
    IoSetTopLevelIrp((PIRP)v3);
  }
  *((_QWORD *)v5 + 13) = *((_QWORD *)v3 + 2);
  RefsPreRequestProcessingExtend(v5, v4);
  MinorFunction = p_CurrentStackLocation->CurrentStackLocation->MinorFunction;
  if ( MinorFunction == 1 )
  {
    v9 = RefsPostRequest(v5, (struct _SECURITY_SUBJECT_CONTEXT *)a2, 1, 0);
  }
  else if ( MinorFunction == 2 )
  {
    v9 = RefsVerifyVolumeRequest(v5, a2);
  }
  else
  {
    v15 = 0;
    FileObject = 0;
    if ( MinorFunction == 4 || !MinorFunction )
    {
      v9 = RefsUserFsRequest((_VCB **)v5, a2, v6, v7);
    }
    else
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v9 = -1073741808;
      }
      else
      {
        v9 = -1073741808;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids, 3221225488LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741808, 0, "FsCtrl.c", 0x581u);
      RefsCompleteFileSystemControlRequest(v5, a2, -1073741808);
    }
  }
  if ( v13 >= 0 )
    IoClearActivityIdThread(v17);
  KeLeaveCriticalRegion();
  return v9;
}

```

## disassembly

```asm
0x1403209e0  push    rbx
0x1403209e2  push    rsi
0x1403209e3  push    rdi
0x1403209e4  push    r14
0x1403209e6  sub     rsp, 0F8h
0x1403209ed  mov     rax, cs:__security_cookie
0x1403209f4  xor     rax, rsp
0x1403209f7  mov     [rsp+118h+var_38], rax
0x1403209ff  mov     rdi, rdx
0x140320a02  mov     [rsp+118h+var_B8], rdx
0x140320a07  xorps   xmm0, xmm0
0x140320a0a  xor     eax, eax
0x140320a0c  movups  [rsp+118h+var_B0], xmm0
0x140320a11  mov     [rsp+118h+var_A0], rax
0x140320a16  xor     ebx, ebx
0x140320a18  mov     [rsp+118h+var_F0], rbx
0x140320a1d  xor     esi, esi
0x140320a1f  movups  [rsp+118h+var_98], xmm0
0x140320a27  mov     [rsp+118h+var_C8], rax
0x140320a2c  lea     rax, [rdx+0B8h]
0x140320a33  mov     [rsp+118h+var_C0], rax
0x140320a38  mov     rax, [rax]
0x140320a3b  cmp     [rax+30h], rbx
0x140320a3f  jz      loc_140320D2D
0x140320a45  mov     rcx, rdx; Irp
0x140320a48  call    cs:__imp_IoIsOperationSynchronous
0x140320a4f  nop     dword ptr [rax+rax+00h]
0x140320a54  mov     [rsp+118h+var_F8], al
0x140320a58  call    cs:__imp_KeEnterCriticalRegion
0x140320a5f  nop     dword ptr [rax+rax+00h]
0x140320a64  lea     r8, [rsp+118h+var_C8]
0x140320a69  lea     rdx, [rsp+118h+var_98]
0x140320a71  mov     rcx, rdi
0x140320a74  call    cs:__imp_IoPropagateActivityIdToThread
0x140320a7b  nop     dword ptr [rax+rax+00h]
0x140320a80  mov     [rsp+118h+var_E8], eax
0x140320a84  xor     r8d, r8d; unsigned __int8
0x140320a87  xor     edx, edx; unsigned __int8
0x140320a89  lea     rcx, [rsp+118h+var_B0]; struct _TOP_LEVEL_CONTEXT *
0x140320a8e  call    ?RefsInitializeTopLevelIrp@@YAPEAU_TOP_LEVEL_CONTEXT@@PEAU1@EE@Z; RefsInitializeTopLevelIrp(_TOP_LEVEL_CONTEXT *,uchar,uchar)
0x140320a93  mov     r14, rax
0x140320a96  mov     [rsp+118h+var_D0], rax
0x140320a9b  test    rbx, rbx
0x140320a9e  jnz     loc_140320C45
0x140320aa4  lea     r9, [rsp+118h+var_F0]; struct _IRP_CONTEXT **
0x140320aa9  mov     r8b, 1; unsigned __int8
0x140320aac  movzx   edx, [rsp+118h+var_F8]; unsigned __int8
0x140320ab1  mov     rcx, rdi; Irp
0x140320ab4  call    ?RefsInitializeIrpContext@@YAJPEAU_IRP@@EEPEAPEAU_IRP_CONTEXT@@@Z; RefsInitializeIrpContext(_IRP *,uchar,uchar,_IRP_CONTEXT * *)
0x140320ab9  cmp     [r14+10h], rbx
0x140320abd  jnz     loc_140320B6E
0x140320ac3  mov     dword ptr [r14+4], 5346ABBAh
0x140320acb  mov     rbx, [rsp+118h+var_F0]
0x140320ad0  mov     [r14+10h], rbx
0x140320ad4  or      qword ptr [rbx+8], 100000h
0x140320adc  mov     rcx, r14; Irp
0x140320adf  call    cs:__imp_IoSetTopLevelIrp
0x140320ae6  nop     dword ptr [rax+rax+00h]
0x140320aeb  mov     rax, [r14+10h]
0x140320aef  mov     [rbx+68h], rax
0x140320af3  mov     rcx, rbx; struct _IRP_CONTEXT *
0x140320af6  call    ?RefsPreRequestProcessingExtend@@YAXPEAU_IRP_CONTEXT@@J@Z; RefsPreRequestProcessingExtend(_IRP_CONTEXT *,long)
0x140320afb  mov     rax, [rsp+118h+var_C0]
0x140320b00  mov     rcx, [rax]
0x140320b03  movzx   eax, byte ptr [rcx+1]
0x140320b07  cmp     al, 1
0x140320b09  jnz     short loc_140320B28
0x140320b0b  xor     r9d, r9d; unsigned __int8
0x140320b0e  movzx   r8d, al; unsigned __int8
0x140320b12  mov     rdx, rdi; struct _IRP *
0x140320b15  mov     rcx, rbx; struct _IRP_CONTEXT *
0x140320b18  call    ?RefsPostRequest@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@EE@Z; RefsPostRequest(_IRP_CONTEXT *,_IRP *,uchar,uchar)
0x140320b1d  mov     esi, eax
0x140320b1f  mov     [rsp+118h+var_F4], eax
0x140320b23  jmp     loc_140320CD8
0x140320b28  cmp     al, 2
0x140320b2a  jz      short loc_140320B58
0x140320b2c  mov     [rsp+118h+var_D8], 0
0x140320b35  mov     [rsp+118h+FileObject], 0
0x140320b3e  cmp     al, 4
0x140320b40  jnz     short loc_140320B78
0x140320b42  mov     rdx, rdi; Irp
0x140320b45  mov     rcx, rbx; struct _IRP_CONTEXT *
0x140320b48  call    ?RefsUserFsRequest@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@@Z; RefsUserFsRequest(_IRP_CONTEXT *,_IRP *)
0x140320b4d  mov     esi, eax
0x140320b4f  mov     [rsp+118h+var_F4], esi
0x140320b53  jmp     loc_140320CD8
0x140320b58  mov     rdx, rdi; Irp
0x140320b5b  mov     rcx, rbx; struct _IRP_CONTEXT *
0x140320b5e  call    ?RefsVerifyVolumeRequest@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@@Z; RefsVerifyVolumeRequest(_IRP_CONTEXT *,_IRP *)
0x140320b63  mov     esi, eax
0x140320b65  mov     [rsp+118h+var_F4], eax
0x140320b69  jmp     loc_140320CD8
0x140320b6e  mov     rbx, [rsp+118h+var_F0]
0x140320b73  jmp     loc_140320AEB
0x140320b78  test    al, al
0x140320b7a  jz      short loc_140320B42
0x140320b7c  cmp     eax, 1
0x140320b7f  jnz     loc_140320C5E
0x140320b85  lea     r9, [rsp+118h+FileObject]; struct _FILE_OBJECT **
0x140320b8a  lea     r8, [rsp+118h+var_D8]; struct _VCB **
0x140320b8f  mov     rdx, rdi; Irp
0x140320b92  mov     rcx, rbx; struct _IRP_CONTEXT *
0x140320b95  call    ?RefsMountVolume@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@PEAPEAU_VCB@@PEAPEAU_FILE_OBJECT@@@Z; RefsMountVolume(_IRP_CONTEXT *,_IRP *,_VCB * *,_FILE_OBJECT * *)
0x140320b9a  mov     esi, eax
0x140320b9c  mov     rcx, [rsp+118h+FileObject]; FileObject
0x140320ba1  test    rcx, rcx
0x140320ba4  jz      short loc_140320B4F
0x140320ba6  mov     dword ptr [rsp+118h+Event.Version], 480001h
0x140320bb1  mov     [rsp+118h+Event.FileObject], 0
0x140320bbd  mov     [rsp+118h+Event.NameBufferOffset], 0FFFFFFFFh
0x140320bc8  mov     qword ptr [rsp+118h+Event.CustomDataBuffer], 1
0x140320bd4  mov     [rsp+118h+var_5C], 8
0x140320bdf  mov     [rsp+118h+var_58], 10h
0x140320bea  mov     rax, qword ptr cs:aRefs_0; "ReFS"
0x140320bf1  mov     [rsp+118h+var_54], rax
0x140320bf9  lea     r8, [rsp+118h+Event]; Event
0x140320c01  mov     edx, 6; EventCode
0x140320c06  call    cs:__imp_FsRtlNotifyVolumeEventEx
0x140320c0d  nop     dword ptr [rax+rax+00h]
0x140320c12  mov     rcx, [rsp+118h+var_D8]
0x140320c17  add     rcx, 17F0h; Event
0x140320c1e  xor     r8d, r8d; Wait
0x140320c21  xor     edx, edx; Increment
0x140320c23  call    cs:__imp_KeSetEvent
0x140320c2a  nop     dword ptr [rax+rax+00h]
0x140320c2f  mov     rcx, [rsp+118h+FileObject]; Object
0x140320c34  call    cs:__imp_ObfDereferenceObject
0x140320c3b  nop     dword ptr [rax+rax+00h]
0x140320c40  jmp     loc_140320B4F
0x140320c45  cmp     esi, 0C0000188h
0x140320c4b  jnz     loc_140320AF3
0x140320c51  mov     rcx, rbx; struct _IRP_CONTEXT *
0x140320c54  call    ?RefsCheckpointForLogFileFull@@YAXPEAU_IRP_CONTEXT@@@Z; RefsCheckpointForLogFileFull(_IRP_CONTEXT *)
0x140320c59  jmp     loc_140320AF3
0x140320c5e  lea     rax, WPP_GLOBAL_Control
0x140320c65  mov     rcx, cs:WPP_GLOBAL_Control
0x140320c6c  cmp     rcx, rax
0x140320c6f  jz      short loc_140320C9F
0x140320c71  test    dword ptr [rcx+2Ch], 100h
0x140320c78  jz      short loc_140320C9F
0x140320c7a  cmp     byte ptr [rcx+29h], 4
0x140320c7e  jb      short loc_140320C9F
0x140320c80  mov     edx, 0Ch
0x140320c85  mov     esi, 0C0000010h
0x140320c8a  mov     r9d, esi
0x140320c8d  lea     r8, WPP_9a30568c93c333a296ab3c507849cc83_Traceguids
0x140320c94  mov     rcx, [rcx+18h]
0x140320c98  call    WPP_SF_d
0x140320c9d  jmp     short loc_140320CA4
0x140320c9f  mov     esi, 0C0000010h
0x140320ca4  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140320cab  test    al, al
0x140320cad  jz      short loc_140320CC5
0x140320caf  mov     r9d, 581h; unsigned int
0x140320cb5  lea     r8, aFsctrlC; "FsCtrl.c"
0x140320cbc  xor     edx, edx; struct _IRP_CONTEXT *
0x140320cbe  mov     ecx, esi; Status
0x140320cc0  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x140320cc5  mov     r8d, esi; int
0x140320cc8  mov     rdx, rdi; struct _IRP *
0x140320ccb  mov     rcx, rbx; struct _IRP_CONTEXT *
0x140320cce  call    ?RefsCompleteFileSystemControlRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteFileSystemControlRequest(_IRP_CONTEXT *,_IRP *,long)
0x140320cd3  jmp     loc_140320B4F
0x140320cd8  jmp     short loc_140320CFA
0x140320cda  mov     r8d, eax; int
0x140320cdd  mov     rdi, [rsp+118h+var_B8]
0x140320ce2  mov     rdx, rdi; struct _IRP *
0x140320ce5  mov     rbx, [rsp+118h+var_F0]
0x140320cea  mov     rcx, rbx; struct _IRP_CONTEXT *
0x140320ced  call    ?RefsProcessException@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsProcessException(_IRP_CONTEXT *,_IRP *,long)
0x140320cf2  mov     esi, eax
0x140320cf4  mov     [rsp+118h+var_F4], eax
0x140320cf8  jmp     short loc_140320D37
0x140320cfa  cmp     [rsp+118h+var_E8], 0
0x140320cff  jge     short loc_140320D5E
0x140320d01  call    cs:__imp_KeLeaveCriticalRegion
0x140320d08  nop     dword ptr [rax+rax+00h]
0x140320d0d  mov     eax, esi
0x140320d0f  mov     rcx, [rsp+118h+var_38]
0x140320d17  xor     rcx, rsp; StackCookie
0x140320d1a  call    __security_check_cookie
0x140320d1f  add     rsp, 0F8h
0x140320d26  pop     r14
0x140320d28  pop     rdi
0x140320d29  pop     rsi
0x140320d2a  pop     rbx
0x140320d2b  retn
0x140320d2d  mov     [rsp+118h+var_F8], 1
0x140320d32  jmp     loc_140320A58
0x140320d37  cmp     eax, 0C00000D8h
0x140320d3c  jz      loc_14034A466
0x140320d42  cmp     eax, 0C00001A8h
0x140320d47  jz      loc_14034A466
0x140320d4d  cmp     eax, 0C0000188h
0x140320d52  jnz     short loc_140320CFA
0x140320d54  mov     r14, [rsp+118h+var_D0]
0x140320d59  jmp     loc_140320A9B
0x140320d5e  mov     rcx, [rsp+118h+var_C8]
0x140320d63  call    cs:__imp_IoClearActivityIdThread
0x140320d6a  nop     dword ptr [rax+rax+00h]
0x140320d6f  jmp     short loc_140320D01
0x140340ad0  push    rbp
0x140340ad2  sub     rsp, 20h
0x140340ad6  mov     rbp, rdx
0x140340ad9  mov     rdx, rcx; struct _EXCEPTION_POINTERS *
0x140340adc  mov     rcx, [rbp+28h]; struct _IRP_CONTEXT *
0x140340ae0  call    ?RefsExceptionFilter@@YAJPEAU_IRP_CONTEXT@@PEAU_EXCEPTION_POINTERS@@@Z; RefsExceptionFilter(_IRP_CONTEXT *,_EXCEPTION_POINTERS *)
0x140340ae5  nop
0x140340ae6  add     rsp, 20h
0x140340aea  pop     rbp
0x140340aeb  retn
0x14034a466  mov     r14, [rsp+118h+var_D0]
0x14034a46b  jmp     loc_140320A9B
```
