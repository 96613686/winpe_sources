# DiskIoctlPredictFailure

- ea: `0x140012210`
- end: `0x1400125bb`
- name: `DiskIoctlPredictFailure`
- size: `939`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1400014a0`

## callees

- `0x140003dd8`
- `0x140003ecc`
- `0x140004078`
- `0x14000431c`
- `0x140005bf0`
- `0x140012210`
- `0x1400125d0`
- `0x1400126c0`

## import_xrefs

- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x1400123ef`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x1400123ef`
- `ntoskrnl!KeWaitForSingleObject` at `0x140012551`
- `ntoskrnl!KeWaitForSingleObject` at `0x140012551`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x140012381`
- `ntoskrnl!IoGetAttachedDeviceReference` at `0x140012381`
- `ntoskrnl!KeInitializeEvent` at `0x140012372`
- `ntoskrnl!KeInitializeEvent` at `0x140012372`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012445`
- `ntoskrnl!ExFreePoolWithTag` at `0x140012445`
- `ntoskrnl!IofCallDriver` at `0x14001241a`
- `ntoskrnl!IofCallDriver` at `0x14001241a`
- `ntoskrnl!ExAllocatePool2` at `0x1400123a3`
- `ntoskrnl!ExAllocatePool2` at `0x1400123a3`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400124da`
- `ntoskrnl!IoGetActivityIdIrp` at `0x1400124da`
- `ntoskrnl!IoSetActivityIdIrp` at `0x1400124f5`
- `ntoskrnl!IoSetActivityIdIrp` at `0x1400124f5`
- `ntoskrnl!ObfDereferenceObject` at `0x140012454`
- `ntoskrnl!ObfDereferenceObject` at `0x1400125aa`
- `ntoskrnl!ObfDereferenceObject` at `0x140012454`
- `ntoskrnl!ObfDereferenceObject` at `0x1400125aa`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001226b`
- `ntoskrnl!KeGetCurrentIrql` at `0x14001226b`

## pseudocode

```c
__int64 __fastcall DiskIoctlPredictFailure(PDEVICE_OBJECT DeviceObject, _QWORD *a2)
{
  PVOID DeviceExtension; // rbp
  __int64 v3; // rbx
  __int64 v5; // rsi
  _DWORD *v7; // r14
  unsigned int Status; // ebx
  PDEVICE_OBJECT AttachedDeviceReference; // rax
  ULONG v11; // ebx
  struct _DEVICE_OBJECT *v12; // r15
  void *Pool2; // rax
  void *v14; // r12
  IRP *v15; // r13
  int v16; // edx
  int v17; // ecx
  int v18; // edx
  int v19; // ecx
  int v20; // [rsp+28h] [rbp-C0h]
  union _LARGE_INTEGER StartingOffset; // [rsp+60h] [rbp-88h] BYREF
  __int64 v22; // [rsp+68h] [rbp-80h] BYREF
  struct _KEVENT Event; // [rsp+70h] [rbp-78h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp-60h] BYREF
  __int128 v25; // [rsp+98h] [rbp-50h] BYREF

  DeviceExtension = DeviceObject->DeviceExtension;
  v3 = a2[23];
  v22 = 0;
  v5 = *((_QWORD *)DeviceExtension + 12);
  memset(&Event, 0, sizeof(Event));
  IoStatusBlock = 0;
  v25 = 0;
  if ( KeGetCurrentIrql() >= 2u )
    return 3221225800LL;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 69, WPP_0d021951613e35be7880fae860fb7f50_Traceguids, DeviceObject, a2);
  }
  if ( *(_DWORD *)(v3 + 8) >= 0x204u )
  {
    v7 = (_DWORD *)a2[3];
    if ( *(_DWORD *)(v5 + 16) == 3 )
    {
      *v7 = 0;
      KeInitializeEvent(&Event, SynchronizationEvent, 0);
      AttachedDeviceReference = IoGetAttachedDeviceReference(DeviceObject);
      v11 = *((_DWORD *)DeviceExtension + 143);
      v12 = AttachedDeviceReference;
      Pool2 = (void *)ExAllocatePool2(64, v11, 1631871827);
      v14 = Pool2;
      if ( !Pool2 )
      {
        Status = -1073741670;
        ObfDereferenceObject(v12);
        return Status;
      }
      StartingOffset.QuadPart = 0;
      v15 = IoBuildSynchronousFsdRequest(3u, v12, Pool2, v11, &StartingOffset, &Event, &IoStatusBlock);
      if ( v15 )
      {
        if ( DiskETWEnabled )
        {
          if ( (int)IoGetActivityIdIrp(a2, &v25) >= 0 )
            IoSetActivityIdIrp(v15, &v25);
          if ( ((__int64)WPP_MAIN_CB.DeviceExtension & 4) != 0 )
            McTemplateK0qpuxi_EtwWriteTransfer(
              v19,
              v18,
              (unsigned int)&v25,
              *((_DWORD *)DeviceExtension + 147),
              (char)v15,
              v20,
              v11,
              StartingOffset.QuadPart);
        }
        Status = IofCallDriver(v12, v15);
        if ( Status == 259 )
        {
          KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
          Status = IoStatusBlock.Status;
        }
        if ( DiskETWEnabled && (BYTE1(WPP_MAIN_CB.DeviceExtension) & 1) != 0 )
          McTemplateK0qpduuuuu_EtwWriteTransfer(
            v17,
            v16,
            (unsigned int)&v25,
            *((_DWORD *)DeviceExtension + 147),
            (char)v15,
            Status);
      }
      else
      {
        Status = -1073741670;
      }
      ExFreePoolWithTag(v14, 0);
      ObfDereferenceObject(v12);
      if ( Status == -1073741670 )
        return Status;
    }
    if ( (unsigned int)(*(_DWORD *)(v5 + 16) - 2) > 1 )
    {
      return (unsigned int)-1073741808;
    }
    else
    {
      Status = DiskReadFailurePredictStatus(DeviceExtension, &v22);
      if ( (Status & 0x80000000) == 0 )
      {
        Status = DiskReadFailurePredictData((int)DeviceExtension);
        *v7 = BYTE4(v22) != 0;
        a2[7] = 516;
      }
    }
    return Status;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 70, WPP_0d021951613e35be7880fae860fb7f50_Traceguids);
  }
  return 3221225507LL;
}

```

## disassembly

```asm
0x140012210  mov     r11, rsp
0x140012213  push    rbx
0x140012214  push    rbp
0x140012215  push    rsi
0x140012216  push    rdi
0x140012217  push    r13
0x140012219  push    r15
0x14001221b  sub     rsp, 0B8h
0x140012222  mov     rax, cs:__security_cookie
0x140012229  xor     rax, rsp
0x14001222c  mov     [rsp+0E8h+var_40], rax
0x140012234  mov     rbp, [rcx+40h]
0x140012238  xorps   xmm0, xmm0
0x14001223b  mov     rbx, [rdx+0B8h]
0x140012242  xorps   xmm1, xmm1
0x140012245  xor     eax, eax
0x140012247  xor     r13d, r13d
0x14001224a  mov     rdi, rdx
0x14001224d  mov     [r11-80h], r13
0x140012251  mov     rsi, [rbp+60h]
0x140012255  mov     r15, rcx
0x140012258  movups  xmmword ptr [rsp+0E8h+Event.Header], xmm1
0x14001225d  mov     [r11-68h], rax
0x140012261  movups  xmmword ptr [r11-60h], xmm0
0x140012266  movups  xmmword ptr [r11-50h], xmm0
0x14001226b  call    cs:__imp_KeGetCurrentIrql
0x140012272  nop     dword ptr [rax+rax+00h]
0x140012277  cmp     al, 2
0x140012279  jnb     loc_140012344
0x14001227f  mov     rcx, cs:WPP_GLOBAL_Control
0x140012286  mov     [rsp+0E8h+var_38], r14
0x14001228e  lea     r14, WPP_GLOBAL_Control
0x140012295  cmp     rcx, r14
0x140012298  jz      short loc_1400122A5
0x14001229a  mov     eax, [rcx+2Ch]
0x14001229d  test    al, 10h
0x14001229f  jnz     loc_140012474
0x1400122a5  cmp     dword ptr [rbx+8], 204h
0x1400122ac  jb      loc_14001234B
0x1400122b2  cmp     dword ptr [rsi+10h], 3
0x1400122b6  mov     r14, [rdi+18h]
0x1400122ba  mov     [rsp+0E8h+arg_10], r12
0x1400122c2  jz      loc_140012362
0x1400122c8  mov     eax, [rsi+10h]
0x1400122cb  sub     eax, 2
0x1400122ce  cmp     eax, 1
0x1400122d1  ja      short loc_14001233D
0x1400122d3  lea     rdx, [rsp+0E8h+var_80]
0x1400122d8  mov     rcx, rbp
0x1400122db  call    DiskReadFailurePredictStatus
0x1400122e0  mov     ebx, eax
0x1400122e2  test    eax, eax
0x1400122e4  js      short loc_14001230A
0x1400122e6  mov     rdx, [rdi+18h]
0x1400122ea  mov     rcx, rbp; int
0x1400122ed  call    DiskReadFailurePredictData
0x1400122f2  cmp     [rsp+0E8h+var_7C], 0
0x1400122f7  mov     ebx, eax
0x1400122f9  mov     eax, r13d
0x1400122fc  setnz   al
0x1400122ff  mov     [r14], eax
0x140012302  mov     qword ptr [rdi+38h], 204h
0x14001230a  mov     r12, [rsp+0E8h+arg_10]
0x140012312  mov     eax, ebx
0x140012314  mov     r14, [rsp+0E8h+var_38]
0x14001231c  mov     rcx, [rsp+0E8h+var_40]
0x140012324  xor     rcx, rsp; StackCookie
0x140012327  call    __security_check_cookie
0x14001232c  add     rsp, 0B8h
0x140012333  pop     r15
0x140012335  pop     r13
0x140012337  pop     rdi
0x140012338  pop     rsi
0x140012339  pop     rbp
0x14001233a  pop     rbx
0x14001233b  retn
0x14001233d  mov     ebx, 0C0000010h
0x140012342  jmp     short loc_14001230A
0x140012344  mov     eax, 0C0000148h
0x140012349  jmp     short loc_14001231C
0x14001234b  mov     rcx, cs:WPP_GLOBAL_Control
0x140012352  cmp     rcx, r14
0x140012355  jnz     loc_1400124A0
0x14001235b  mov     eax, 0C0000023h
0x140012360  jmp     short loc_140012314
0x140012362  xor     r8d, r8d; State
0x140012365  mov     [r14], r13d
0x140012368  mov     edx, 1; Type
0x14001236d  lea     rcx, [rsp+0E8h+Event]; Event
0x140012372  call    cs:__imp_KeInitializeEvent
0x140012379  nop     dword ptr [rax+rax+00h]
0x14001237e  mov     rcx, r15; DeviceObject
0x140012381  call    cs:__imp_IoGetAttachedDeviceReference
0x140012388  nop     dword ptr [rax+rax+00h]
0x14001238d  mov     ebx, [rbp+23Ch]
0x140012393  mov     r8d, 61446353h
0x140012399  mov     edx, ebx
0x14001239b  mov     ecx, 40h ; '@'
0x1400123a0  mov     r15, rax
0x1400123a3  call    cs:__imp_ExAllocatePool2
0x1400123aa  nop     dword ptr [rax+rax+00h]
0x1400123af  mov     r12, rax
0x1400123b2  test    rax, rax
0x1400123b5  jz      loc_1400125A2
0x1400123bb  lea     rax, [rsp+0E8h+var_60]
0x1400123c3  mov     qword ptr [rsp+0E8h+var_88], r13
0x1400123c8  mov     [rsp+0E8h+IoStatusBlock], rax; IoStatusBlock
0x1400123cd  mov     r9d, ebx; Length
0x1400123d0  lea     rax, [rsp+0E8h+Event]
0x1400123d5  mov     r8, r12; Buffer
0x1400123d8  mov     [rsp+0E8h+var_C0], rax; Event
0x1400123dd  mov     rdx, r15; DeviceObject
0x1400123e0  lea     rax, [rsp+0E8h+var_88]
0x1400123e5  mov     ecx, 3; MajorFunction
0x1400123ea  mov     [rsp+0E8h+StartingOffset], rax; StartingOffset
0x1400123ef  call    cs:__imp_IoBuildSynchronousFsdRequest
0x1400123f6  nop     dword ptr [rax+rax+00h]
0x1400123fb  mov     r13, rax
0x1400123fe  test    rax, rax
0x140012401  jz      loc_140012598
0x140012407  cmp     cs:DiskETWEnabled, 0
0x14001240e  jnz     loc_1400124CF
0x140012414  mov     rdx, r13; Irp
0x140012417  mov     rcx, r15; DeviceObject
0x14001241a  call    cs:__imp_IofCallDriver
0x140012421  nop     dword ptr [rax+rax+00h]
0x140012426  mov     ebx, eax
0x140012428  cmp     eax, 103h
0x14001242d  jz      loc_14001253B
0x140012433  cmp     cs:DiskETWEnabled, 0
0x14001243a  jnz     loc_140012569
0x140012440  xor     edx, edx; Tag
0x140012442  mov     rcx, r12; P
0x140012445  call    cs:__imp_ExFreePoolWithTag
0x14001244c  nop     dword ptr [rax+rax+00h]
0x140012451  mov     rcx, r15; Object
0x140012454  call    cs:__imp_ObfDereferenceObject
0x14001245b  nop     dword ptr [rax+rax+00h]
0x140012460  cmp     ebx, 0C000009Ah
0x140012466  jz      loc_14001230A
0x14001246c  xor     r13d, r13d
0x14001246f  jmp     loc_1400122C8
0x140012474  cmp     byte ptr [rcx+29h], 4
0x140012478  jb      loc_1400122A5
0x14001247e  mov     rcx, [rcx+18h]
0x140012482  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x140012489  mov     edx, 45h ; 'E'
0x14001248e  mov     [rsp+0E8h+StartingOffset], rdi
0x140012493  mov     r9, r15
0x140012496  call    WPP_SF_qq
0x14001249b  jmp     loc_1400122A5
0x1400124a0  mov     eax, [rcx+2Ch]
0x1400124a3  test    al, 10h
0x1400124a5  jz      loc_14001235B
0x1400124ab  cmp     byte ptr [rcx+29h], 2
0x1400124af  jb      loc_14001235B
0x1400124b5  mov     rcx, [rcx+18h]
0x1400124b9  lea     r8, WPP_0d021951613e35be7880fae860fb7f50_Traceguids
0x1400124c0  mov     edx, 46h ; 'F'
0x1400124c5  call    WPP_SF_
0x1400124ca  jmp     loc_14001235B
0x1400124cf  lea     rdx, [rsp+0E8h+var_50]
0x1400124d7  mov     rcx, rdi
0x1400124da  call    cs:__imp_IoGetActivityIdIrp
0x1400124e1  nop     dword ptr [rax+rax+00h]
0x1400124e6  test    eax, eax
0x1400124e8  js      short loc_140012501
0x1400124ea  lea     rdx, [rsp+0E8h+var_50]
0x1400124f2  mov     rcx, r13
0x1400124f5  call    cs:__imp_IoSetActivityIdIrp
0x1400124fc  nop     dword ptr [rax+rax+00h]
0x140012501  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension, 4
0x140012508  jz      loc_140012414
0x14001250e  mov     rax, qword ptr [rsp+0E8h+var_88]
0x140012513  lea     r8, [rsp+0E8h+var_50]
0x14001251b  mov     r9d, [rbp+24Ch]
0x140012522  mov     [rsp+0E8h+var_B0], rax
0x140012527  mov     [rsp+0E8h+IoStatusBlock], rbx
0x14001252c  mov     [rsp+0E8h+StartingOffset], r13
0x140012531  call    McTemplateK0qpuxi_EtwWriteTransfer
0x140012536  jmp     loc_140012414
0x14001253b  xor     r9d, r9d; Alertable
0x14001253e  mov     [rsp+0E8h+StartingOffset], 0; Timeout
0x140012547  xor     r8d, r8d; WaitMode
0x14001254a  lea     rcx, [rsp+0E8h+Event]; Object
0x14001254f  xor     edx, edx; WaitReason
0x140012551  call    cs:__imp_KeWaitForSingleObject
0x140012558  nop     dword ptr [rax+rax+00h]
0x14001255d  mov     ebx, dword ptr [rsp+0E8h+var_60]
0x140012564  jmp     loc_140012433
0x140012569  test    byte ptr cs:WPP_MAIN_CB.DeviceExtension+1, 1
0x140012570  jz      loc_140012440
0x140012576  mov     r9d, [rbp+24Ch]
0x14001257d  lea     r8, [rsp+0E8h+var_50]
0x140012585  mov     dword ptr [rsp+0E8h+var_C0], ebx
0x140012589  mov     [rsp+0E8h+StartingOffset], r13
0x14001258e  call    McTemplateK0qpduuuuu_EtwWriteTransfer
0x140012593  jmp     loc_140012440
0x140012598  mov     ebx, 0C000009Ah
0x14001259d  jmp     loc_140012440
0x1400125a2  mov     rcx, r15; Object
0x1400125a5  mov     ebx, 0C000009Ah
0x1400125aa  call    cs:__imp_ObfDereferenceObject
0x1400125b1  nop     dword ptr [rax+rax+00h]
0x1400125b6  jmp     loc_14001230A
```
