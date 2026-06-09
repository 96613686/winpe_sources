# MupFsdIrpPassThrough

- ea: `0x14001b8b0`
- end: `0x14001bada`
- name: `MupFsdIrpPassThrough`
- size: `554`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter4, IRP *BugCheckParameter2, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140001070`
- `0x140001c10`
- `0x1400029b0`
- `0x140002eb8`
- `0x14001b8b0`
- `0x14001bae0`
- `0x14001bb80`
- `0x14001bbb0`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x14001ba82`
- `ntoskrnl!KeBugCheckEx` at `0x14001ba82`
- `ntoskrnl!IofCallDriver` at `0x14001ba0b`
- `ntoskrnl!IofCallDriver` at `0x14001ba0b`
- `ntoskrnl!IofCompleteRequest` at `0x14001b9c5`
- `ntoskrnl!IofCompleteRequest` at `0x14001b9c5`
- `ntoskrnl!IoGetAttachedDevice` at `0x14001b9f9`
- `ntoskrnl!IoGetAttachedDevice` at `0x14001b9f9`

## pseudocode

```c
__int64 __fastcall MupFsdIrpPassThrough(ULONG_PTR BugCheckParameter4, IRP *BugCheckParameter2, __int64 a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  ULONG_PTR FileObject; // rsi
  ULONG_PTR FileContext; // rbp
  __int64 SiloFromFileObject; // rax
  unsigned int ContainerContextFromSilo; // ebx
  unsigned __int64 v10; // rdx
  __int64 v12; // rbp
  struct _DEVICE_OBJECT *AttachedDevice; // rax
  NTSTATUS v14; // eax
  __int64 v15; // [rsp+78h] [rbp+10h] BYREF
  PVOID P; // [rsp+80h] [rbp+18h] BYREF

  CurrentStackLocation = BugCheckParameter2->Tail.Overlay.CurrentStackLocation;
  P = 0;
  FileObject = (ULONG_PTR)CurrentStackLocation->FileObject;
  v15 = 0;
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
    ContainerContextFromSilo = MupGetContainerContextFromSilo(SiloFromFileObject, &v15);
    if ( !ContainerContextFromSilo )
    {
      ContainerContextFromSilo = MupCreateIrpContext(FileContext, (__int64)&P);
      if ( !ContainerContextFromSilo )
      {
        ContainerContextFromSilo = MupStateMachine((unsigned __int64)P, v10);
        goto LABEL_11;
      }
    }
LABEL_16:
    BugCheckParameter2->IoStatus.Status = ContainerContextFromSilo;
    IofCompleteRequest(BugCheckParameter2, 2);
    goto LABEL_11;
  }
  v12 = *(_QWORD *)(FileContext + 168);
  ++BugCheckParameter2->CurrentLocation;
  ++BugCheckParameter2->Tail.Overlay.CurrentStackLocation;
  AttachedDevice = IoGetAttachedDevice(*(PDEVICE_OBJECT *)(v12 + 168));
  v14 = IofCallDriver(AttachedDevice, BugCheckParameter2);
  ContainerContextFromSilo = v14;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x4000000) != 0 )
  {
    WPP_SF_qqD(
      WPP_GLOBAL_Control->AttachedDevice,
      38,
      WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids,
      BugCheckParameter2,
      v12,
      v14);
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
0x14001b8b0  push    rbx
0x14001b8b2  push    rsi
0x14001b8b3  push    rdi
0x14001b8b4  push    r14
0x14001b8b6  push    r15
0x14001b8b8  sub     rsp, 40h
0x14001b8bc  mov     rbx, [rdx+0B8h]
0x14001b8c3  xor     eax, eax
0x14001b8c5  mov     rdi, rdx
0x14001b8c8  mov     [rsp+68h+P], rax
0x14001b8d0  mov     r14, rcx
0x14001b8d3  mov     rsi, [rbx+30h]
0x14001b8d7  mov     [rsp+68h+arg_8], rax
0x14001b8dc  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b8e3  lea     r15, WPP_GLOBAL_Control
0x14001b8ea  cmp     rcx, r15
0x14001b8ed  jz      short loc_14001B8FC
0x14001b8ef  test    dword ptr [rcx+2Ch], 4000000h
0x14001b8f6  jnz     loc_14001BA8F
0x14001b8fc  mov     [rsp+68h+arg_0], rbp
0x14001b901  test    rsi, rsi
0x14001b904  jz      loc_14001B9B8
0x14001b90a  mov     rcx, rsi
0x14001b90d  call    MupFindFileContext
0x14001b912  mov     rbp, rax
0x14001b915  test    rax, rax
0x14001b918  jz      loc_14001BA5C
0x14001b91e  movzx   eax, byte ptr [rbx]
0x14001b921  sub     eax, 3
0x14001b924  jz      loc_14001B9D3
0x14001b92a  cmp     eax, 1
0x14001b92d  jz      loc_14001B9D3
0x14001b933  mov     rcx, [rdi+0B8h]
0x14001b93a  mov     rcx, [rcx+30h]
0x14001b93e  call    MupGetSiloFromFileObject
0x14001b943  mov     rcx, rax
0x14001b946  lea     rdx, [rsp+68h+arg_8]
0x14001b94b  call    MupGetContainerContextFromSilo
0x14001b950  mov     ebx, eax
0x14001b952  test    eax, eax
0x14001b954  jnz     short loc_14001B9BD
0x14001b956  mov     rdx, [rsp+68h+arg_8]
0x14001b95b  lea     rax, [rsp+68h+P]
0x14001b963  xor     r9d, r9d
0x14001b966  mov     [rsp+68h+BugCheckParameter4], rax; __int64
0x14001b96b  mov     r8, rdi
0x14001b96e  mov     rcx, rbp; BugCheckParameter4
0x14001b971  call    MupCreateIrpContext
0x14001b976  mov     ebx, eax
0x14001b978  test    eax, eax
0x14001b97a  jnz     short loc_14001B9BD
0x14001b97c  mov     rcx, [rsp+68h+P]; P
0x14001b984  call    MupStateMachine
0x14001b989  mov     ebx, eax
0x14001b98b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001b992  cmp     rcx, r15
0x14001b995  jz      short loc_14001B9A4
0x14001b997  test    dword ptr [rcx+2Ch], 4000000h
0x14001b99e  jnz     loc_14001BAB4
0x14001b9a4  mov     rbp, [rsp+68h+arg_0]
0x14001b9a9  mov     eax, ebx
0x14001b9ab  add     rsp, 40h
0x14001b9af  pop     r15
0x14001b9b1  pop     r14
0x14001b9b3  pop     rdi
0x14001b9b4  pop     rsi
0x14001b9b5  pop     rbx
0x14001b9b6  retn
0x14001b9b8  mov     ebx, 0C0000010h
0x14001b9bd  mov     dl, 2; PriorityBoost
0x14001b9bf  mov     [rdi+30h], ebx
0x14001b9c2  mov     rcx, rdi; Irp
0x14001b9c5  call    cs:__imp_IofCompleteRequest
0x14001b9cc  nop     dword ptr [rax+rax+00h]
0x14001b9d1  jmp     short loc_14001B98B
0x14001b9d3  cmp     cs:MupiCachingAndGenericSurrogateCount, 0
0x14001b9da  ja      loc_14001B933
0x14001b9e0  mov     rbp, [rbp+0A8h]
0x14001b9e7  inc     byte ptr [rdi+43h]
0x14001b9ea  add     qword ptr [rdi+0B8h], 48h ; 'H'
0x14001b9f2  mov     rcx, [rbp+0A8h]; DeviceObject
0x14001b9f9  call    cs:__imp_IoGetAttachedDevice
0x14001ba00  nop     dword ptr [rax+rax+00h]
0x14001ba05  mov     rcx, rax; DeviceObject
0x14001ba08  mov     rdx, rdi; Irp
0x14001ba0b  call    cs:__imp_IofCallDriver
0x14001ba12  nop     dword ptr [rax+rax+00h]
0x14001ba17  mov     ebx, eax
0x14001ba19  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ba20  cmp     rcx, r15
0x14001ba23  jz      loc_14001B98B
0x14001ba29  test    dword ptr [rcx+2Ch], 4000000h
0x14001ba30  jz      loc_14001B98B
0x14001ba36  mov     rcx, [rcx+18h]
0x14001ba3a  lea     r8, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids
0x14001ba41  mov     [rsp+68h+var_40], eax
0x14001ba45  mov     edx, 26h ; '&'
0x14001ba4a  mov     r9, rdi
0x14001ba4d  mov     [rsp+68h+BugCheckParameter4], rbp
0x14001ba52  call    WPP_SF_qqD
0x14001ba57  jmp     loc_14001B98B
0x14001ba5c  lea     rax, g_MupAdvancedFcbHeader
0x14001ba63  cmp     [rsi+18h], rax
0x14001ba67  jz      loc_14001B9B8
0x14001ba6d  mov     r9, rsi; BugCheckParameter3
0x14001ba70  mov     [rsp+68h+BugCheckParameter4], r14; BugCheckParameter4
0x14001ba75  mov     r8, rdi; BugCheckParameter2
0x14001ba78  mov     edx, 1; BugCheckParameter1
0x14001ba7d  mov     ecx, 103h; BugCheckCode
0x14001ba82  call    cs:__imp_KeBugCheckEx
0x14001ba8f  movzx   eax, byte ptr [rbx+1]
0x14001ba93  mov     r9, rsi
0x14001ba96  movzx   edx, byte ptr [rbx]
0x14001ba99  mov     rcx, [rcx+18h]
0x14001ba9d  mov     [rsp+68h+var_38], eax
0x14001baa1  mov     [rsp+68h+var_40], edx
0x14001baa5  mov     [rsp+68h+BugCheckParameter4], rdi
0x14001baaa  call    WPP_SF_qqDD
0x14001baaf  jmp     loc_14001B8FC
0x14001bab4  mov     rcx, [rcx+18h]
0x14001bab8  lea     r8, WPP_c5473a374ddf3a0e52f92742cfcc1391_Traceguids
0x14001babf  mov     edx, 0Fh
0x14001bac4  mov     [rsp+68h+var_40], ebx
0x14001bac8  mov     r9, rsi
0x14001bacb  mov     [rsp+68h+BugCheckParameter4], rdi
0x14001bad0  call    WPP_SF_qqD
0x14001bad5  jmp     loc_14001B9A4
```
