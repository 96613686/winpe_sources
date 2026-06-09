# MupFsdIrpPassThrough

- ea: `0x14001b860`
- end: `0x14001ba8a`
- name: `MupFsdIrpPassThrough`
- size: `554`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter4, ULONG_PTR BugCheckParameter2)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140001070`
- `0x140001c10`
- `0x1400029b0`
- `0x140002eb8`
- `0x14001b860`
- `0x14001ba90`
- `0x14001bb30`
- `0x14001bb60`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14001ba32`
- `ntoskrnl!KeBugCheckEx` at `0x14001ba32`
- `ntoskrnl!IofCallDriver` at `0x14001b9bb`
- `ntoskrnl!IofCallDriver` at `0x14001b9bb`
- `ntoskrnl!IofCompleteRequest` at `0x14001b975`
- `ntoskrnl!IofCompleteRequest` at `0x14001b975`
- `ntoskrnl!IoGetAttachedDevice` at `0x14001b9a9`
- `ntoskrnl!IoGetAttachedDevice` at `0x14001b9a9`

## pseudocode

```c
__int64 __fastcall MupFsdIrpPassThrough(ULONG_PTR BugCheckParameter4, IRP *BugCheckParameter2, __int64 a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  ULONG_PTR FileObject; // rsi
  ULONG_PTR FileContext; // rbp
  __int64 SiloFromFileObject; // rax
  unsigned int ContainerContextFromSilo; // ebx
  __int64 v11; // rbp
  struct _DEVICE_OBJECT *AttachedDevice; // rax
  NTSTATUS v13; // eax
  __int64 v14; // [rsp+78h] [rbp+10h] BYREF
  PVOID P; // [rsp+80h] [rbp+18h] BYREF

  CurrentStackLocation = BugCheckParameter2->Tail.Overlay.CurrentStackLocation;
  P = 0;
  FileObject = (ULONG_PTR)CurrentStackLocation->FileObject;
  v14 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
  {
    WPP_SF_qqDD(
      WPP_GLOBAL_Control->AttachedDevice,
      CurrentStackLocation->MajorFunction,
      a3,
      FileObject,
      BugCheckParameter2,
      CurrentStackLocation->MajorFunction,
      CurrentStackLocation->MinorFunction);
  }
  if ( !FileObject )
    goto LABEL_15;
  FileContext = MupFindFileContext(FileObject);
  if ( !FileContext )
  {
    if ( *(FSRTL_ADVANCED_FCB_HEADER **)(FileObject + 24) != &g_MupAdvancedFcbHeader )
      KeBugCheckEx(0x103u, 1u, (ULONG_PTR)BugCheckParameter2, FileObject, BugCheckParameter4);
LABEL_15:
    ContainerContextFromSilo = -1073741808;
    goto LABEL_16;
  }
  if ( CurrentStackLocation->MajorFunction != 3 && CurrentStackLocation->MajorFunction != 4
    || MupiCachingAndGenericSurrogateCount )
  {
    SiloFromFileObject = MupGetSiloFromFileObject(BugCheckParameter2->Tail.Overlay.CurrentStackLocation->FileObject);
    ContainerContextFromSilo = MupGetContainerContextFromSilo(SiloFromFileObject, &v14);
    if ( !ContainerContextFromSilo )
    {
      ContainerContextFromSilo = MupCreateIrpContext(FileContext, v14, (ULONG_PTR)BugCheckParameter2, 0, (__int64 **)&P);
      if ( !ContainerContextFromSilo )
      {
        ContainerContextFromSilo = MupStateMachine(P);
        goto LABEL_11;
      }
    }
LABEL_16:
    BugCheckParameter2->IoStatus.Status = ContainerContextFromSilo;
    IofCompleteRequest(BugCheckParameter2, 2);
    goto LABEL_11;
  }
  v11 = *(_QWORD *)(FileContext + 168);
  ++BugCheckParameter2->CurrentLocation;
  ++BugCheckParameter2->Tail.Overlay.CurrentStackLocation;
  AttachedDevice = IoGetAttachedDevice(*(PDEVICE_OBJECT *)(v11 + 168));
  v13 = IofCallDriver(AttachedDevice, BugCheckParameter2);
  ContainerContextFromSilo = v13;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
  {
    WPP_SF_qqD(
      WPP_GLOBAL_Control->AttachedDevice,
      38,
      WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids,
      BugCheckParameter2,
      v11,
      v13);
  }
LABEL_11:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
  {
    WPP_SF_qqD(
      WPP_GLOBAL_Control->AttachedDevice,
      15,
      WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids,
      FileObject,
      BugCheckParameter2,
      ContainerContextFromSilo);
  }
  return ContainerContextFromSilo;
}

```

## disassembly

```asm
0x14001b860  push    rbx
0x14001b862  push    rsi
0x14001b863  push    rdi
0x14001b864  push    r14
0x14001b866  push    r15
0x14001b868  sub     rsp, 40h
0x14001b86c  mov     rbx, [rdx+0B8h]
0x14001b873  xor     eax, eax
0x14001b875  mov     rdi, rdx
0x14001b878  mov     [rsp+68h+P], rax
0x14001b880  mov     r14, rcx
0x14001b883  mov     rsi, [rbx+30h]
0x14001b887  mov     [rsp+68h+arg_8], rax
0x14001b88c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b893  lea     r15, WPP_GLOBAL_Control
0x14001b89a  cmp     rcx, r15
0x14001b89d  jz      short loc_14001B8AC
0x14001b89f  test    dword ptr [rcx+2Ch], 4000000h
0x14001b8a6  jnz     loc_14001BA3F
0x14001b8ac  mov     [rsp+68h+arg_0], rbp
0x14001b8b1  test    rsi, rsi
0x14001b8b4  jz      loc_14001B968
0x14001b8ba  mov     rcx, rsi
0x14001b8bd  call    MupFindFileContext
0x14001b8c2  mov     rbp, rax
0x14001b8c5  test    rax, rax
0x14001b8c8  jz      loc_14001BA0C
0x14001b8ce  movzx   eax, byte ptr [rbx]
0x14001b8d1  sub     eax, 3
0x14001b8d4  jz      loc_14001B983
0x14001b8da  cmp     eax, 1
0x14001b8dd  jz      loc_14001B983
0x14001b8e3  mov     rcx, [rdi+0B8h]
0x14001b8ea  mov     rcx, [rcx+30h]
0x14001b8ee  call    MupGetSiloFromFileObject
0x14001b8f3  mov     rcx, rax
0x14001b8f6  lea     rdx, [rsp+68h+arg_8]
0x14001b8fb  call    MupGetContainerContextFromSilo
0x14001b900  mov     ebx, eax
0x14001b902  test    eax, eax
0x14001b904  jnz     short loc_14001B96D
0x14001b906  mov     rdx, [rsp+68h+arg_8]
0x14001b90b  lea     rax, [rsp+68h+P]
0x14001b913  xor     r9d, r9d
0x14001b916  mov     [rsp+68h+BugCheckParameter4], rax; __int64
0x14001b91b  mov     r8, rdi
0x14001b91e  mov     rcx, rbp; BugCheckParameter4
0x14001b921  call    MupCreateIrpContext
0x14001b926  mov     ebx, eax
0x14001b928  test    eax, eax
0x14001b92a  jnz     short loc_14001B96D
0x14001b92c  mov     rcx, [rsp+68h+P]; P
0x14001b934  call    MupStateMachine
0x14001b939  mov     ebx, eax
0x14001b93b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b942  cmp     rcx, r15
0x14001b945  jz      short loc_14001B954
0x14001b947  test    dword ptr [rcx+2Ch], 4000000h
0x14001b94e  jnz     loc_14001BA64
0x14001b954  mov     rbp, [rsp+68h+arg_0]
0x14001b959  mov     eax, ebx
0x14001b95b  add     rsp, 40h
0x14001b95f  pop     r15
0x14001b961  pop     r14
0x14001b963  pop     rdi
0x14001b964  pop     rsi
0x14001b965  pop     rbx
0x14001b966  retn
0x14001b968  mov     ebx, 0C0000010h
0x14001b96d  mov     dl, 2; PriorityBoost
0x14001b96f  mov     [rdi+30h], ebx
0x14001b972  mov     rcx, rdi; Irp
0x14001b975  call    cs:__imp_IofCompleteRequest
0x14001b97c  nop     dword ptr [rax+rax+00h]
0x14001b981  jmp     short loc_14001B93B
0x14001b983  cmp     cs:MupiCachingAndGenericSurrogateCount, 0
0x14001b98a  ja      loc_14001B8E3
0x14001b990  mov     rbp, [rbp+0A8h]
0x14001b997  inc     byte ptr [rdi+43h]
0x14001b99a  add     qword ptr [rdi+0B8h], 48h ; 'H'
0x14001b9a2  mov     rcx, [rbp+0A8h]; DeviceObject
0x14001b9a9  call    cs:__imp_IoGetAttachedDevice
0x14001b9b0  nop     dword ptr [rax+rax+00h]
0x14001b9b5  mov     rcx, rax; DeviceObject
0x14001b9b8  mov     rdx, rdi; Irp
0x14001b9bb  call    cs:__imp_IofCallDriver
0x14001b9c2  nop     dword ptr [rax+rax+00h]
0x14001b9c7  mov     ebx, eax
0x14001b9c9  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b9d0  cmp     rcx, r15
0x14001b9d3  jz      loc_14001B93B
0x14001b9d9  test    dword ptr [rcx+2Ch], 4000000h
0x14001b9e0  jz      loc_14001B93B
0x14001b9e6  mov     rcx, [rcx+18h]
0x14001b9ea  lea     r8, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids
0x14001b9f1  mov     [rsp+68h+var_40], eax
0x14001b9f5  mov     edx, 26h ; '&'
0x14001b9fa  mov     r9, rdi
0x14001b9fd  mov     [rsp+68h+BugCheckParameter4], rbp
0x14001ba02  call    WPP_SF_qqD
0x14001ba07  jmp     loc_14001B93B
0x14001ba0c  lea     rax, g_MupAdvancedFcbHeader
0x14001ba13  cmp     [rsi+18h], rax
0x14001ba17  jz      loc_14001B968
0x14001ba1d  mov     r9, rsi; BugCheckParameter3
0x14001ba20  mov     [rsp+68h+BugCheckParameter4], r14; BugCheckParameter4
0x14001ba25  mov     r8, rdi; BugCheckParameter2
0x14001ba28  mov     edx, 1; BugCheckParameter1
0x14001ba2d  mov     ecx, 103h; BugCheckCode
0x14001ba32  call    cs:__imp_KeBugCheckEx
0x14001ba3f  movzx   eax, byte ptr [rbx+1]
0x14001ba43  mov     r9, rsi
0x14001ba46  movzx   edx, byte ptr [rbx]
0x14001ba49  mov     rcx, [rcx+18h]
0x14001ba4d  mov     [rsp+68h+var_38], eax
0x14001ba51  mov     [rsp+68h+var_40], edx
0x14001ba55  mov     [rsp+68h+BugCheckParameter4], rdi
0x14001ba5a  call    WPP_SF_qqDD
0x14001ba5f  jmp     loc_14001B8AC
0x14001ba64  mov     rcx, [rcx+18h]
0x14001ba68  lea     r8, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids
0x14001ba6f  mov     edx, 0Fh
0x14001ba74  mov     [rsp+68h+var_40], ebx
0x14001ba78  mov     r9, rsi
0x14001ba7b  mov     [rsp+68h+BugCheckParameter4], rdi
0x14001ba80  call    WPP_SF_qqD
0x14001ba85  jmp     loc_14001B954
```
