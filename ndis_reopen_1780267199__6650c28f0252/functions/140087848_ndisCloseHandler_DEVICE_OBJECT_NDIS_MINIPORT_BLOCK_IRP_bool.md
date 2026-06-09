# ndisCloseHandler(_DEVICE_OBJECT *,_NDIS_MINIPORT_BLOCK *,_IRP *,bool)

- ea: `0x140087848`
- end: `0x140087b0d`
- name: `?ndisCloseHandler@@YAJPEAU_DEVICE_OBJECT@@PEAU_NDIS_MINIPORT_BLOCK@@PEAU_IRP@@_N@Z`
- size: `709`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _NDIS_MINIPORT_BLOCK *, struct _IRP *, bool)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14005d3f0`
- `0x14006a7e0`

## callees

- `0x14000e440`
- `0x1400100f0`
- `0x1400110b0`
- `0x140078ad0`
- `0x140087848`
- `0x140087b14`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140087995`
- `ntoskrnl!KeWaitForSingleObject` at `0x140087995`
- `ntoskrnl!IofCompleteRequest` at `0x140087a00`
- `ntoskrnl!IofCompleteRequest` at `0x140087ab7`
- `ntoskrnl!IofCompleteRequest` at `0x140087a00`
- `ntoskrnl!IofCompleteRequest` at `0x140087ab7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400879e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400879e2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140087945`
- `ntoskrnl!KeReleaseSpinLock` at `0x140087945`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14008792a`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14008792a`

## pseudocode

```c
__int64 __fastcall ndisCloseHandler(
        struct _DEVICE_OBJECT *a1,
        struct _NDIS_MINIPORT_BLOCK *a2,
        struct _IRP *a3,
        char a4)
{
  int v8; // edx
  int v9; // r9d
  _IO_STACK_LOCATION *CurrentStackLocation; // r12
  KSPIN_LOCK *FsContext; // r13
  KIRQL v13; // al
  char v14; // bl
  int v15; // edx
  int v16; // edx
  int v17; // r9d
  _IO_STACK_LOCATION *v18; // rbx
  _FILE_OBJECT *FileObject; // rax
  void *v20; // rdx

  if ( (unsigned int)Feature_NDPQualityWinter26__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( !a4 && a2->Header.Type != 17 )
    {
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return ndisDummyHandler(a1, &a2->Header, a3);
      v9 = 24;
LABEL_6:
      LOBYTE(v8) = 4;
      WPP_RECORDER_SF_qq(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v8,
        11,
        v9,
        (struct _GUID *)&WPP_5c1c115ae3d7308ea4dc20929af9c88a_Traceguids,
        (char)a2,
        (char)a3);
      return ndisDummyHandler(a1, &a2->Header, a3);
    }
    CurrentStackLocation = a3->Tail.Overlay.CurrentStackLocation;
    FsContext = (KSPIN_LOCK *)CurrentStackLocation->FileObject->FsContext;
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 4;
      WPP_RECORDER_SF_qq(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v8,
        11,
        25,
        (struct _GUID *)&WPP_5c1c115ae3d7308ea4dc20929af9c88a_Traceguids,
        (char)a2,
        (char)a3);
    }
    v13 = KeAcquireSpinLockRaiseToDpc(FsContext + 4);
    v14 = *((_BYTE *)FsContext + 40);
    *((_BYTE *)FsContext + 41) = 1;
    KeReleaseSpinLock(FsContext + 4, v13);
    if ( v14 )
    {
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v15) = 4;
        WPP_RECORDER_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          v15,
          13,
          26,
          (struct _GUID *)&WPP_5c1c115ae3d7308ea4dc20929af9c88a_Traceguids,
          (char)FsContext);
      }
      KeWaitForSingleObject(FsContext + 6, Executive, 0, 0, 0);
    }
    else
    {
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v15) = 4;
        WPP_RECORDER_SF_q(
          *((_QWORD *)WPP_GLOBAL_Control + 8),
          v15,
          13,
          27,
          (struct _GUID *)&WPP_5c1c115ae3d7308ea4dc20929af9c88a_Traceguids,
          (char)FsContext);
      }
      ndisCleanupUserOpenContext(a2, FsContext);
    }
    ExFreePoolWithTag(FsContext, 0);
    CurrentStackLocation->FileObject->FsContext = 0;
    a3->IoStatus.Status = 0;
    IofCompleteRequest(a3, 2);
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v17 = 28;
LABEL_26:
      LOBYTE(v16) = 4;
      WPP_RECORDER_SF_qq(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v16,
        11,
        v17,
        (struct _GUID *)&WPP_5c1c115ae3d7308ea4dc20929af9c88a_Traceguids,
        (char)a2,
        (char)a3);
    }
  }
  else
  {
    if ( a2->Header.Type != 17 )
    {
      if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED == &WPP_RECORDER_INITIALIZED )
        return ndisDummyHandler(a1, &a2->Header, a3);
      v9 = 29;
      goto LABEL_6;
    }
    v18 = a3->Tail.Overlay.CurrentStackLocation;
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 4;
      WPP_RECORDER_SF_qq(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v8,
        11,
        30,
        (struct _GUID *)&WPP_5c1c115ae3d7308ea4dc20929af9c88a_Traceguids,
        (char)a2,
        (char)a3);
    }
    FileObject = v18->FileObject;
    v20 = FileObject->FsContext;
    FileObject->FsContext = 0;
    ndisCleanupUserOpenContext(a2, v20);
    a3->IoStatus.Status = 0;
    IofCompleteRequest(a3, 2);
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v17 = 31;
      goto LABEL_26;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140087848  push    rbx
0x14008784a  push    rbp
0x14008784b  push    rsi
0x14008784c  push    rdi
0x14008784d  push    r12
0x14008784f  push    r13
0x140087851  push    r14
0x140087853  push    r15
0x140087855  sub     rsp, 48h
0x140087859  mov     dil, r9b
0x14008785c  mov     r14, r8
0x14008785f  mov     rbp, rdx
0x140087862  mov     rbx, rcx
0x140087865  call    Feature_NDPQualityWinter26__private_IsEnabledDeviceUsageNoInline
0x14008786a  test    eax, eax
0x14008786c  jz      loc_140087A24
0x140087872  test    dil, dil
0x140087875  jnz     short loc_1400878D4
0x140087877  cmp     byte ptr [rbp+0], 11h
0x14008787b  jz      short loc_1400878D4
0x14008787d  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140087884  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14008788b  jz      short loc_1400878C1
0x14008788d  mov     r9d, 18h; int
0x140087893  mov     rcx, cs:WPP_GLOBAL_Control
0x14008789a  lea     r15, WPP_5c1c115ae3d7308ea4dc20929af9c88a_Traceguids
0x1400878a1  mov     qword ptr [rsp+88h+var_58], r14; char
0x1400878a6  mov     r8d, 0Bh; int
0x1400878ac  mov     qword ptr [rsp+88h+var_60], rbp; char
0x1400878b1  mov     dl, 4; int
0x1400878b3  mov     [rsp+88h+Timeout], r15; struct _GUID *
0x1400878b8  mov     rcx, [rcx+40h]; int
0x1400878bc  call    WPP_RECORDER_SF_qq
0x1400878c1  mov     r8, r14; struct _IRP *
0x1400878c4  mov     rdx, rbp; struct _NDIS_OBJECT_HEADER *
0x1400878c7  mov     rcx, rbx; struct _DEVICE_OBJECT *
0x1400878ca  call    ?ndisDummyHandler@@YAJPEAU_DEVICE_OBJECT@@PEAU_NDIS_OBJECT_HEADER@@PEAU_IRP@@@Z; ndisDummyHandler(_DEVICE_OBJECT *,_NDIS_OBJECT_HEADER *,_IRP *)
0x1400878cf  jmp     loc_140087AFB
0x1400878d4  mov     r12, [r14+0B8h]
0x1400878db  mov     rax, [r12+30h]
0x1400878e0  mov     r13, [rax+18h]
0x1400878e4  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400878eb  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400878f2  lea     r15, WPP_5c1c115ae3d7308ea4dc20929af9c88a_Traceguids
0x1400878f9  jz      short loc_140087926
0x1400878fb  mov     rcx, cs:WPP_GLOBAL_Control
0x140087902  mov     r9d, 19h; int
0x140087908  mov     qword ptr [rsp+88h+var_58], r14; char
0x14008790d  mov     dl, 4; int
0x14008790f  mov     qword ptr [rsp+88h+var_60], rbp; char
0x140087914  mov     [rsp+88h+Timeout], r15; struct _GUID *
0x140087919  mov     rcx, [rcx+40h]; int
0x14008791d  lea     r8d, [r9-0Eh]; int
0x140087921  call    WPP_RECORDER_SF_qq
0x140087926  lea     rcx, [r13+20h]; SpinLock
0x14008792a  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140087931  nop     dword ptr [rax+rax+00h]
0x140087936  mov     bl, [r13+28h]
0x14008793a  lea     rcx, [r13+20h]; SpinLock
0x14008793e  mov     dl, al; NewIrql
0x140087940  mov     byte ptr [r13+29h], 1
0x140087945  call    cs:__imp_KeReleaseSpinLock
0x14008794c  nop     dword ptr [rax+rax+00h]
0x140087951  xor     edi, edi
0x140087953  test    bl, bl
0x140087955  jz      short loc_1400879A3
0x140087957  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x14008795e  jz      short loc_140087984
0x140087960  mov     rcx, cs:WPP_GLOBAL_Control
0x140087967  lea     r9d, [rdi+1Ah]; int
0x14008796b  mov     qword ptr [rsp+88h+var_60], r13; char
0x140087970  lea     r8d, [rdi+0Dh]; int
0x140087974  mov     dl, 4; int
0x140087976  mov     [rsp+88h+Timeout], r15; struct _GUID *
0x14008797b  mov     rcx, [rcx+40h]; int
0x14008797f  call    WPP_RECORDER_SF_q
0x140087984  lea     rcx, [r13+30h]; Object
0x140087988  mov     [rsp+88h+Timeout], rdi; Timeout
0x14008798d  xor     r9d, r9d; Alertable
0x140087990  xor     r8d, r8d; WaitMode
0x140087993  xor     edx, edx; WaitReason
0x140087995  call    cs:__imp_KeWaitForSingleObject
0x14008799c  nop     dword ptr [rax+rax+00h]
0x1400879a1  jmp     short loc_1400879DD
0x1400879a3  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x1400879aa  jz      short loc_1400879D2
0x1400879ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1400879b3  mov     r9d, 1Bh; int
0x1400879b9  mov     qword ptr [rsp+88h+var_60], r13; char
0x1400879be  mov     dl, 4; int
0x1400879c0  mov     [rsp+88h+Timeout], r15; struct _GUID *
0x1400879c5  mov     rcx, [rcx+40h]; int
0x1400879c9  lea     r8d, [r9-0Eh]; int
0x1400879cd  call    WPP_RECORDER_SF_q
0x1400879d2  mov     rdx, r13; P
0x1400879d5  mov     rcx, rbp; struct _NDIS_MINIPORT_BLOCK *
0x1400879d8  call    ?ndisCleanupUserOpenContext@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_USER_OPEN_CONTEXT@@@Z; ndisCleanupUserOpenContext(_NDIS_MINIPORT_BLOCK *,_NDIS_USER_OPEN_CONTEXT *)
0x1400879dd  xor     edx, edx; Tag
0x1400879df  mov     rcx, r13; P
0x1400879e2  call    cs:__imp_ExFreePoolWithTag
0x1400879e9  nop     dword ptr [rax+rax+00h]
0x1400879ee  mov     rax, [r12+30h]
0x1400879f3  mov     dl, 2; PriorityBoost
0x1400879f5  mov     rcx, r14; Irp
0x1400879f8  mov     [rax+18h], rdi
0x1400879fc  mov     [r14+30h], edi
0x140087a00  call    cs:__imp_IofCompleteRequest
0x140087a07  nop     dword ptr [rax+rax+00h]
0x140087a0c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140087a13  jz      loc_140087AF9
0x140087a19  mov     r9d, 1Ch
0x140087a1f  jmp     loc_140087AD2
0x140087a24  cmp     byte ptr [rbp+0], 11h
0x140087a28  jz      short loc_140087A49
0x140087a2a  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140087a31  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140087a38  jz      loc_1400878C1
0x140087a3e  mov     r9d, 1Dh
0x140087a44  jmp     loc_140087893
0x140087a49  mov     rbx, [r14+0B8h]; __annotation("TMF:",
0x140087a50  lea     rsi, WPP_RECORDER_INITIALIZED
0x140087a57  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140087a5e  lea     r15, WPP_5c1c115ae3d7308ea4dc20929af9c88a_Traceguids
0x140087a65  jz      short loc_140087A92
0x140087a67  mov     rcx, cs:WPP_GLOBAL_Control
0x140087a6e  mov     r9d, 1Eh; int
0x140087a74  mov     qword ptr [rsp+88h+var_58], r14; char
0x140087a79  mov     dl, 4; int
0x140087a7b  mov     qword ptr [rsp+88h+var_60], rbp; char
0x140087a80  mov     [rsp+88h+Timeout], r15; struct _GUID *
0x140087a85  mov     rcx, [rcx+40h]; int
0x140087a89  lea     r8d, [r9-13h]; int
0x140087a8d  call    WPP_RECORDER_SF_qq
0x140087a92  mov     rax, [rbx+30h]
0x140087a96  mov     rcx, rbp; struct _NDIS_MINIPORT_BLOCK *
0x140087a99  mov     rdx, [rax+18h]; P
0x140087a9d  mov     qword ptr [rax+18h], 0
0x140087aa5  call    ?ndisCleanupUserOpenContext@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_USER_OPEN_CONTEXT@@@Z; ndisCleanupUserOpenContext(_NDIS_MINIPORT_BLOCK *,_NDIS_USER_OPEN_CONTEXT *)
0x140087aaa  mov     dl, 2; PriorityBoost
0x140087aac  mov     dword ptr [r14+30h], 0
0x140087ab4  mov     rcx, r14; Irp
0x140087ab7  call    cs:__imp_IofCompleteRequest
0x140087abe  nop     dword ptr [rax+rax+00h]
0x140087ac3  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140087aca  jz      short loc_140087AF9
0x140087acc  mov     r9d, 1Fh; int
0x140087ad2  mov     rcx, cs:WPP_GLOBAL_Control
0x140087ad9  mov     r8d, 0Bh; int
0x140087adf  mov     qword ptr [rsp+88h+var_58], r14; char
0x140087ae4  mov     dl, 4; int
0x140087ae6  mov     qword ptr [rsp+88h+var_60], rbp; char
0x140087aeb  mov     [rsp+88h+Timeout], r15; struct _GUID *
0x140087af0  mov     rcx, [rcx+40h]; int
0x140087af4  call    WPP_RECORDER_SF_qq
0x140087af9  xor     eax, eax
0x140087afb  add     rsp, 48h
0x140087aff  pop     r15
0x140087b01  pop     r14
0x140087b03  pop     r13
0x140087b05  pop     r12
0x140087b07  pop     rdi
0x140087b08  pop     rsi
0x140087b09  pop     rbp
0x140087b0a  pop     rbx
0x140087b0b  retn
```
