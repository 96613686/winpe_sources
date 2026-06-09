# ClassDeviceProcessOffloadWrite

- ea: `0x140056664`
- end: `0x1400569db`
- name: `ClassDeviceProcessOffloadWrite`
- size: `887`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x140019de0`

## callees

- `0x140001008`
- `0x14001fc38`
- `0x14002001c`
- `0x140022668`
- `0x140023e3c`
- `0x14002689c`
- `0x140026f28`
- `0x140027870`
- `0x14003e430`
- `0x140056664`
- `0x14005a300`
- `0x14005c054`
- `0x14005c3d8`

## import_xrefs

- `ntoskrnl!KeGetCurrentIrql` at `0x1400566f8`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400566f8`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140056895`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140056895`

## pseudocode

```c
__int64 __fastcall ClassDeviceProcessOffloadWrite(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  _IO_STACK_LOCATION *CurrentStackLocation; // r14
  int v5; // ebx
  _IRP *MasterIrp; // rcx
  int v7; // r9d
  unsigned int Flags; // r8d
  unsigned int Length; // r8d
  __int64 v10; // rbx
  unsigned int IrpCount; // edx
  __int64 *v12; // r14
  _DWORD *DeviceExtension; // r15
  unsigned int v14; // ecx
  unsigned int v15; // edx
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v19; // [rsp+40h] [rbp-49h] BYREF
  __int64 v20; // [rsp+48h] [rbp-41h] BYREF
  __int128 v21; // [rsp+50h] [rbp-39h] BYREF
  __int64 v22[10]; // [rsp+60h] [rbp-29h] BYREF

  v21 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qq(
      WPP_GLOBAL_Control->AttachedDevice,
      227,
      WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
      DeviceObject,
      Irp);
  }
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v21 = *(_OWORD *)&Irp->Type;
  v5 = ClasspValidateOffloadSupported(DeviceObject, Irp);
  if ( v5 < 0 )
    goto LABEL_40;
  if ( KeGetCurrentIrql() >= 2u )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 228, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, DeviceObject);
    }
    v5 = -1073741496;
    goto LABEL_40;
  }
  if ( Irp->RequestorMode )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 229, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids, DeviceObject);
    }
    v5 = -1073741790;
    goto LABEL_40;
  }
  v5 = ClasspValidateOffloadInputParameters(DeviceObject, Irp);
  if ( v5 < 0 )
  {
LABEL_40:
    ClasspCompleteOffloadRequest(DeviceObject, Irp);
    goto LABEL_41;
  }
  MasterIrp = Irp->AssociatedIrp.MasterIrp;
  v7 = 528;
  Flags = MasterIrp->Flags;
  if ( Flags < 0x210 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qDD(
        WPP_GLOBAL_Control->AttachedDevice,
        230,
        WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
        DeviceObject,
        Flags,
        528);
    }
    v5 = -1073741811;
    goto LABEL_40;
  }
  Length = CurrentStackLocation->Parameters.Read.Length;
  if ( Length < 0x10 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        231,
        WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
        DeviceObject,
        Length);
    }
    v5 = -1073741789;
    goto LABEL_40;
  }
  v10 = 0;
  IrpCount = MasterIrp->AssociatedIrp.IrpCount;
  v12 = (__int64 *)((char *)&MasterIrp->Type + *(&MasterIrp->Flags + 1));
  DeviceExtension = DeviceObject->DeviceExtension;
  v14 = 0;
  v15 = IrpCount >> 4;
  if ( v15 )
  {
    do
    {
      v16 = v14++;
      v10 += v12[2 * v16 + 1];
    }
    while ( v14 < v15 );
  }
  if ( ClassPnPETWEnabled
    && (int)IoGetActivityIdIrp(Irp, &v21) >= 0
    && ((__int64)WPP_MAIN_CB.Queue.Wcb.CurrentIrp & 0x10) != 0 )
  {
    McTemplateK0qptix_EtwWriteTransfer(
      v14,
      (unsigned int)EventCopyOffloadWriteRequest,
      (unsigned int)&v21,
      DeviceExtension[147],
      (char)Irp,
      1,
      *v12,
      v10);
  }
  if ( (unsigned int)dword_14004D060 > 5 )
  {
    v17 = *((_QWORD *)DeviceExtension + 146);
    v22[5] = 16;
    v22[4] = v17 + 4;
    v19 = *v12;
    v22[6] = (__int64)&v19;
    v22[8] = (__int64)&v20;
    v22[7] = 8;
    v20 = v10;
    v22[9] = 8;
    tlgWriteTransfer_EtwWriteTransfer(v14, (int)&byte_140048665, Length, v7, 5u, (__int64)v22);
  }
  v5 = ClasspServiceWriteUsingTokenTransferRequest(DeviceObject, Irp);
  if ( v5 != 259 )
    goto LABEL_40;
LABEL_41:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_qqD(
      WPP_GLOBAL_Control->AttachedDevice,
      232,
      WPP_9ee7907f5c473329e20561a6f3486187_Traceguids,
      DeviceObject,
      Irp,
      v5);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140056664  mov     [rsp-8+arg_10], rbx
0x140056669  push    rbp
0x14005666a  push    rsi
0x14005666b  push    rdi
0x14005666c  push    r14
0x14005666e  push    r15
0x140056670  lea     rbp, [rsp-37h]
0x140056675  sub     rsp, 0C0h
0x14005667c  mov     rax, cs:__security_cookie
0x140056683  xor     rax, rsp
0x140056686  mov     [rbp+57h+var_30], rax
0x14005668a  xorps   xmm0, xmm0
0x14005668d  mov     rdi, rdx
0x140056690  movups  [rbp+57h+var_90], xmm0
0x140056694  mov     rsi, rcx
0x140056697  mov     rcx, cs:WPP_GLOBAL_Control
0x14005669e  lea     rax, WPP_GLOBAL_Control
0x1400566a5  cmp     rcx, rax
0x1400566a8  jz      short loc_1400566D4
0x1400566aa  mov     eax, [rcx+2Ch]
0x1400566ad  test    al, 10h
0x1400566af  jz      short loc_1400566D4
0x1400566b1  cmp     byte ptr [rcx+29h], 5
0x1400566b5  jb      short loc_1400566D4
0x1400566b7  mov     rcx, [rcx+18h]
0x1400566bb  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x1400566c2  mov     edx, 0E3h
0x1400566c7  mov     qword ptr [rsp+0E0h+var_C0], rdi
0x1400566cc  mov     r9, rsi
0x1400566cf  call    WPP_SF_qq
0x1400566d4  movups  xmm0, xmmword ptr [rdi]
0x1400566d7  mov     r14, [rdi+0B8h]
0x1400566de  mov     rdx, rdi
0x1400566e1  mov     rcx, rsi
0x1400566e4  movdqu  [rbp+57h+var_90], xmm0
0x1400566e9  call    ClasspValidateOffloadSupported
0x1400566ee  mov     ebx, eax
0x1400566f0  test    eax, eax
0x1400566f2  js      loc_140056966
0x1400566f8  call    cs:__imp_KeGetCurrentIrql
0x1400566ff  nop     dword ptr [rax+rax+00h]
0x140056704  mov     r15b, 2
0x140056707  cmp     al, r15b
0x14005670a  jb      short loc_14005674E
0x14005670c  mov     rcx, cs:WPP_GLOBAL_Control
0x140056713  lea     r14, WPP_GLOBAL_Control
0x14005671a  cmp     rcx, r14
0x14005671d  jz      short loc_140056744
0x14005671f  mov     eax, [rcx+2Ch]
0x140056722  test    al, 10h
0x140056724  jz      short loc_140056744
0x140056726  cmp     [rcx+29h], r15b
0x14005672a  jb      short loc_140056744
0x14005672c  mov     rcx, [rcx+18h]
0x140056730  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x140056737  mov     edx, 0E4h
0x14005673c  mov     r9, rsi
0x14005673f  call    WPP_SF_q
0x140056744  mov     ebx, 0C0000148h
0x140056749  jmp     loc_14005696D
0x14005674e  cmp     byte ptr [rdi+40h], 0
0x140056752  jz      short loc_140056796
0x140056754  mov     rcx, cs:WPP_GLOBAL_Control
0x14005675b  lea     r14, WPP_GLOBAL_Control
0x140056762  cmp     rcx, r14
0x140056765  jz      short loc_14005678C
0x140056767  mov     eax, [rcx+2Ch]
0x14005676a  test    al, 10h
0x14005676c  jz      short loc_14005678C
0x14005676e  cmp     [rcx+29h], r15b
0x140056772  jb      short loc_14005678C
0x140056774  mov     rcx, [rcx+18h]
0x140056778  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x14005677f  mov     edx, 0E5h
0x140056784  mov     r9, rsi
0x140056787  call    WPP_SF_q
0x14005678c  mov     ebx, 0C0000022h
0x140056791  jmp     loc_14005696D
0x140056796  mov     rdx, rdi
0x140056799  mov     rcx, rsi
0x14005679c  call    ClasspValidateOffloadInputParameters
0x1400567a1  mov     ebx, eax
0x1400567a3  test    eax, eax
0x1400567a5  js      loc_140056966
0x1400567ab  mov     rcx, [rdi+18h]
0x1400567af  mov     r9d, 210h
0x1400567b5  mov     r8d, [rcx+10h]
0x1400567b9  cmp     r8d, r9d
0x1400567bc  jnb     short loc_14005680A
0x1400567be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400567c5  lea     r14, WPP_GLOBAL_Control
0x1400567cc  cmp     rcx, r14
0x1400567cf  jz      short loc_140056800
0x1400567d1  mov     eax, [rcx+2Ch]
0x1400567d4  test    al, 10h
0x1400567d6  jz      short loc_140056800
0x1400567d8  cmp     [rcx+29h], r15b
0x1400567dc  jb      short loc_140056800
0x1400567de  mov     rcx, [rcx+18h]
0x1400567e2  mov     edx, 0E6h
0x1400567e7  mov     dword ptr [rsp+0E0h+var_B8], r9d
0x1400567ec  mov     r9, rsi
0x1400567ef  mov     [rsp+0E0h+var_C0], r8d
0x1400567f4  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x1400567fb  call    WPP_SF_qDD
0x140056800  mov     ebx, 0C000000Dh
0x140056805  jmp     loc_14005696D
0x14005680a  mov     r8d, [r14+8]
0x14005680e  cmp     r8d, 10h
0x140056812  jnb     short loc_14005685B
0x140056814  mov     rcx, cs:WPP_GLOBAL_Control
0x14005681b  lea     r14, WPP_GLOBAL_Control
0x140056822  cmp     rcx, r14
0x140056825  jz      short loc_140056851
0x140056827  mov     eax, [rcx+2Ch]
0x14005682a  test    al, 10h
0x14005682c  jz      short loc_140056851
0x14005682e  cmp     [rcx+29h], r15b
0x140056832  jb      short loc_140056851
0x140056834  mov     rcx, [rcx+18h]
0x140056838  mov     edx, 0E7h
0x14005683d  mov     [rsp+0E0h+var_C0], r8d
0x140056842  mov     r9, rsi
0x140056845  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x14005684c  call    WPP_SF_qD
0x140056851  mov     ebx, 0C0000023h
0x140056856  jmp     loc_14005696D
0x14005685b  mov     r14d, [rcx+14h]
0x14005685f  xor     ebx, ebx
0x140056861  mov     edx, [rcx+18h]
0x140056864  add     r14, rcx
0x140056867  mov     r15, [rsi+40h]
0x14005686b  xor     ecx, ecx
0x14005686d  shr     edx, 4
0x140056870  test    edx, edx
0x140056872  jz      short loc_140056885
0x140056874  mov     eax, ecx
0x140056876  inc     ecx
0x140056878  shl     rax, 4
0x14005687c  add     rbx, [rax+r14+8]
0x140056881  cmp     ecx, edx
0x140056883  jb      short loc_140056874
0x140056885  cmp     cs:ClassPnPETWEnabled, 0
0x14005688c  jz      short loc_1400568DF
0x14005688e  lea     rdx, [rbp+57h+var_90]
0x140056892  mov     rcx, rdi
0x140056895  call    cs:__imp_IoGetActivityIdIrp
0x14005689c  nop     dword ptr [rax+rax+00h]
0x1400568a1  test    eax, eax
0x1400568a3  js      short loc_1400568DF
0x1400568a5  test    byte ptr cs:WPP_MAIN_CB.Queue+38h, 10h
0x1400568ac  jz      short loc_1400568DF
0x1400568ae  mov     rax, [r14]
0x1400568b1  lea     r8, [rbp+57h+var_90]
0x1400568b5  mov     r9d, [r15+24Ch]
0x1400568bc  lea     rdx, EventCopyOffloadWriteRequest
0x1400568c3  mov     [rsp+0E0h+var_A8], rbx
0x1400568c8  mov     [rsp+0E0h+var_B0], rax
0x1400568cd  mov     dword ptr [rsp+0E0h+var_B8], 1
0x1400568d5  mov     qword ptr [rsp+0E0h+var_C0], rdi
0x1400568da  call    McTemplateK0qptix_EtwWriteTransfer
0x1400568df  mov     eax, cs:dword_14004D060
0x1400568e5  cmp     eax, 5
0x1400568e8  jbe     short loc_140056949
0x1400568ea  mov     rax, [r15+490h]
0x1400568f1  lea     rdx, byte_140048665; int
0x1400568f8  add     rax, 4
0x1400568fc  mov     [rbp+57h+var_58], 10h
0x140056904  mov     [rbp+57h+var_60], rax
0x140056908  mov     rax, [r14]
0x14005690b  mov     [rbp+57h+var_A0], rax
0x14005690f  lea     rax, [rbp+57h+var_A0]
0x140056913  mov     [rbp+57h+var_50], rax
0x140056917  lea     rax, [rbp+57h+var_98]
0x14005691b  mov     [rbp+57h+var_40], rax
0x14005691f  lea     rax, [rbp+57h+var_80]
0x140056923  mov     [rsp+0E0h+var_B8], rax; __int64
0x140056928  mov     [rsp+0E0h+var_C0], 5; ULONG
0x140056930  mov     [rbp+57h+var_48], 8
0x140056938  mov     [rbp+57h+var_98], rbx
0x14005693c  mov     [rbp+57h+var_38], 8
0x140056944  call    _tlgWriteTransfer_EtwWriteTransfer
0x140056949  mov     rdx, rdi
0x14005694c  mov     rcx, rsi
0x14005694f  call    ClasspServiceWriteUsingTokenTransferRequest
0x140056954  lea     r14, WPP_GLOBAL_Control
0x14005695b  mov     ebx, eax
0x14005695d  cmp     eax, 103h
0x140056962  jz      short loc_14005697B
0x140056964  jmp     short loc_14005696D
0x140056966  lea     r14, WPP_GLOBAL_Control
0x14005696d  mov     r8d, ebx
0x140056970  mov     rdx, rdi; Irp
0x140056973  mov     rcx, rsi; DeviceObject
0x140056976  call    ClasspCompleteOffloadRequest
0x14005697b  mov     rcx, cs:WPP_GLOBAL_Control
0x140056982  cmp     rcx, r14
0x140056985  jz      short loc_1400569B5
0x140056987  mov     eax, [rcx+2Ch]
0x14005698a  test    al, 10h
0x14005698c  jz      short loc_1400569B5
0x14005698e  cmp     byte ptr [rcx+29h], 5
0x140056992  jb      short loc_1400569B5
0x140056994  mov     rcx, [rcx+18h]
0x140056998  lea     r8, WPP_9ee7907f5c473329e20561a6f3486187_Traceguids
0x14005699f  mov     edx, 0E8h
0x1400569a4  mov     dword ptr [rsp+0E0h+var_B8], ebx
0x1400569a8  mov     r9, rsi
0x1400569ab  mov     qword ptr [rsp+0E0h+var_C0], rdi
0x1400569b0  call    WPP_SF_qqD
0x1400569b5  mov     eax, ebx
0x1400569b7  mov     rcx, [rbp+57h+var_30]
0x1400569bb  xor     rcx, rsp; StackCookie
0x1400569be  call    __security_check_cookie
0x1400569c3  mov     rbx, [rsp+0E0h+arg_10]
0x1400569cb  add     rsp, 0C0h
0x1400569d2  pop     r15
0x1400569d4  pop     r14
0x1400569d6  pop     rdi
0x1400569d7  pop     rsi
0x1400569d8  pop     rbp
0x1400569d9  retn
```
