# ndisCloseHandler(_DEVICE_OBJECT *,_NDIS_MINIPORT_BLOCK *,_IRP *,bool)

- ea: `0x1400825c8`
- end: `0x14008288d`
- name: `?ndisCloseHandler@@YAJPEAU_DEVICE_OBJECT@@PEAU_NDIS_MINIPORT_BLOCK@@PEAU_IRP@@_N@Z`
- size: `709`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _NDIS_MINIPORT_BLOCK *, struct _IRP *, bool)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140058880`
- `0x1400650a0`

## callees

- `0x14001a3a0`
- `0x14001c050`
- `0x14001cf50`
- `0x1400733f0`
- `0x1400825c8`
- `0x140082894`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140082715`
- `ntoskrnl!KeWaitForSingleObject` at `0x140082715`
- `ntoskrnl!IofCompleteRequest` at `0x140082780`
- `ntoskrnl!IofCompleteRequest` at `0x140082837`
- `ntoskrnl!IofCompleteRequest` at `0x140082780`
- `ntoskrnl!IofCompleteRequest` at `0x140082837`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082762`
- `ntoskrnl!ExFreePoolWithTag` at `0x140082762`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400826c5`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400826c5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400826aa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400826aa`

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
0x1400825c8  push    rbx
0x1400825ca  push    rbp
0x1400825cb  push    rsi
0x1400825cc  push    rdi
0x1400825cd  push    r12
0x1400825cf  push    r13
0x1400825d1  push    r14
0x1400825d3  push    r15
0x1400825d5  sub     rsp, 48h
0x1400825d9  mov     dil, r9b
0x1400825dc  mov     r14, r8
0x1400825df  mov     rbp, rdx
0x1400825e2  mov     rbx, rcx
0x1400825e5  call    Feature_NDPQualityWinter26__private_IsEnabledDeviceUsageNoInline
0x1400825ea  test    eax, eax
0x1400825ec  jz      loc_1400827A4
0x1400825f2  test    dil, dil
0x1400825f5  jnz     short loc_140082654
0x1400825f7  cmp     byte ptr [rbp+0], 11h
0x1400825fb  jz      short loc_140082654
0x1400825fd  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140082604  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14008260b  jz      short loc_140082641
0x14008260d  mov     r9d, 18h; int
0x140082613  mov     rcx, cs:WPP_GLOBAL_Control
0x14008261a  lea     r15, WPP_5c1c115ae3d7308ea4dc20929af9c88a_Traceguids
0x140082621  mov     qword ptr [rsp+88h+var_58], r14; char
0x140082626  mov     r8d, 0Bh; int
0x14008262c  mov     qword ptr [rsp+88h+var_60], rbp; char
0x140082631  mov     dl, 4; int
0x140082633  mov     [rsp+88h+Timeout], r15; struct _GUID *
0x140082638  mov     rcx, [rcx+40h]; int
0x14008263c  call    WPP_RECORDER_SF_qq
0x140082641  mov     r8, r14; struct _IRP *
0x140082644  mov     rdx, rbp; struct _NDIS_OBJECT_HEADER *
0x140082647  mov     rcx, rbx; struct _DEVICE_OBJECT *
0x14008264a  call    ?ndisDummyHandler@@YAJPEAU_DEVICE_OBJECT@@PEAU_NDIS_OBJECT_HEADER@@PEAU_IRP@@@Z; ndisDummyHandler(_DEVICE_OBJECT *,_NDIS_OBJECT_HEADER *,_IRP *)
0x14008264f  jmp     loc_14008287B
0x140082654  mov     r12, [r14+0B8h]
0x14008265b  mov     rax, [r12+30h]
0x140082660  mov     r13, [rax+18h]
0x140082664  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14008266b  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140082672  lea     r15, WPP_5c1c115ae3d7308ea4dc20929af9c88a_Traceguids
0x140082679  jz      short loc_1400826A6
0x14008267b  mov     rcx, cs:WPP_GLOBAL_Control
0x140082682  mov     r9d, 19h; int
0x140082688  mov     qword ptr [rsp+88h+var_58], r14; char
0x14008268d  mov     dl, 4; int
0x14008268f  mov     qword ptr [rsp+88h+var_60], rbp; char
0x140082694  mov     [rsp+88h+Timeout], r15; struct _GUID *
0x140082699  mov     rcx, [rcx+40h]; int
0x14008269d  lea     r8d, [r9-0Eh]; int
0x1400826a1  call    WPP_RECORDER_SF_qq
0x1400826a6  lea     rcx, [r13+20h]; SpinLock
0x1400826aa  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400826b1  nop     dword ptr [rax+rax+00h]
0x1400826b6  mov     bl, [r13+28h]
0x1400826ba  lea     rcx, [r13+20h]; SpinLock
0x1400826be  mov     dl, al; NewIrql
0x1400826c0  mov     byte ptr [r13+29h], 1
0x1400826c5  call    cs:__imp_KeReleaseSpinLock
0x1400826cc  nop     dword ptr [rax+rax+00h]
0x1400826d1  xor     edi, edi
0x1400826d3  test    bl, bl
0x1400826d5  jz      short loc_140082723
0x1400826d7  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x1400826de  jz      short loc_140082704
0x1400826e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400826e7  lea     r9d, [rdi+1Ah]; int
0x1400826eb  mov     qword ptr [rsp+88h+var_60], r13; char
0x1400826f0  lea     r8d, [rdi+0Dh]; int
0x1400826f4  mov     dl, 4; int
0x1400826f6  mov     [rsp+88h+Timeout], r15; struct _GUID *
0x1400826fb  mov     rcx, [rcx+40h]; int
0x1400826ff  call    WPP_RECORDER_SF_q
0x140082704  lea     rcx, [r13+30h]; Object
0x140082708  mov     [rsp+88h+Timeout], rdi; Timeout
0x14008270d  xor     r9d, r9d; Alertable
0x140082710  xor     r8d, r8d; WaitMode
0x140082713  xor     edx, edx; WaitReason
0x140082715  call    cs:__imp_KeWaitForSingleObject
0x14008271c  nop     dword ptr [rax+rax+00h]
0x140082721  jmp     short loc_14008275D
0x140082723  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x14008272a  jz      short loc_140082752
0x14008272c  mov     rcx, cs:WPP_GLOBAL_Control
0x140082733  mov     r9d, 1Bh; int
0x140082739  mov     qword ptr [rsp+88h+var_60], r13; char
0x14008273e  mov     dl, 4; int
0x140082740  mov     [rsp+88h+Timeout], r15; struct _GUID *
0x140082745  mov     rcx, [rcx+40h]; int
0x140082749  lea     r8d, [r9-0Eh]; int
0x14008274d  call    WPP_RECORDER_SF_q
0x140082752  mov     rdx, r13; P
0x140082755  mov     rcx, rbp; struct _NDIS_MINIPORT_BLOCK *
0x140082758  call    ?ndisCleanupUserOpenContext@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_USER_OPEN_CONTEXT@@@Z; ndisCleanupUserOpenContext(_NDIS_MINIPORT_BLOCK *,_NDIS_USER_OPEN_CONTEXT *)
0x14008275d  xor     edx, edx; Tag
0x14008275f  mov     rcx, r13; P
0x140082762  call    cs:__imp_ExFreePoolWithTag
0x140082769  nop     dword ptr [rax+rax+00h]
0x14008276e  mov     rax, [r12+30h]
0x140082773  mov     dl, 2; PriorityBoost
0x140082775  mov     rcx, r14; Irp
0x140082778  mov     [rax+18h], rdi
0x14008277c  mov     [r14+30h], edi
0x140082780  call    cs:__imp_IofCompleteRequest
0x140082787  nop     dword ptr [rax+rax+00h]
0x14008278c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x140082793  jz      loc_140082879
0x140082799  mov     r9d, 1Ch
0x14008279f  jmp     loc_140082852
0x1400827a4  cmp     byte ptr [rbp+0], 11h
0x1400827a8  jz      short loc_1400827C9
0x1400827aa  lea     rsi, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400827b1  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400827b8  jz      loc_140082641
0x1400827be  mov     r9d, 1Dh
0x1400827c4  jmp     loc_140082613
0x1400827c9  mov     rbx, [r14+0B8h]; __annotation("TMF:",
0x1400827d0  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400827d7  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400827de  lea     r15, WPP_5c1c115ae3d7308ea4dc20929af9c88a_Traceguids
0x1400827e5  jz      short loc_140082812
0x1400827e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400827ee  mov     r9d, 1Eh; int
0x1400827f4  mov     qword ptr [rsp+88h+var_58], r14; char
0x1400827f9  mov     dl, 4; int
0x1400827fb  mov     qword ptr [rsp+88h+var_60], rbp; char
0x140082800  mov     [rsp+88h+Timeout], r15; struct _GUID *
0x140082805  mov     rcx, [rcx+40h]; int
0x140082809  lea     r8d, [r9-13h]; int
0x14008280d  call    WPP_RECORDER_SF_qq
0x140082812  mov     rax, [rbx+30h]
0x140082816  mov     rcx, rbp; struct _NDIS_MINIPORT_BLOCK *
0x140082819  mov     rdx, [rax+18h]; P
0x14008281d  mov     qword ptr [rax+18h], 0
0x140082825  call    ?ndisCleanupUserOpenContext@@YAXPEAU_NDIS_MINIPORT_BLOCK@@PEAU_NDIS_USER_OPEN_CONTEXT@@@Z; ndisCleanupUserOpenContext(_NDIS_MINIPORT_BLOCK *,_NDIS_USER_OPEN_CONTEXT *)
0x14008282a  mov     dl, 2; PriorityBoost
0x14008282c  mov     dword ptr [r14+30h], 0
0x140082834  mov     rcx, r14; Irp
0x140082837  call    cs:__imp_IofCompleteRequest
0x14008283e  nop     dword ptr [rax+rax+00h]
0x140082843  cmp     cs:WPP_RECORDER_INITIALIZED, rsi; __annotation("TMF:",
0x14008284a  jz      short loc_140082879
0x14008284c  mov     r9d, 1Fh; int
0x140082852  mov     rcx, cs:WPP_GLOBAL_Control
0x140082859  mov     r8d, 0Bh; int
0x14008285f  mov     qword ptr [rsp+88h+var_58], r14; char
0x140082864  mov     dl, 4; int
0x140082866  mov     qword ptr [rsp+88h+var_60], rbp; char
0x14008286b  mov     [rsp+88h+Timeout], r15; struct _GUID *
0x140082870  mov     rcx, [rcx+40h]; int
0x140082874  call    WPP_RECORDER_SF_qq
0x140082879  xor     eax, eax
0x14008287b  add     rsp, 48h
0x14008287f  pop     r15
0x140082881  pop     r14
0x140082883  pop     r13
0x140082885  pop     r12
0x140082887  pop     rdi
0x140082888  pop     rsi
0x140082889  pop     rbp
0x14008288a  pop     rbx
0x14008288b  retn
```
