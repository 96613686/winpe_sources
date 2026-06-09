# KsDispatchIrp

- ea: `0x1800481d0`
- end: `0x18004859a`
- name: `KsDispatchIrp`
- size: `970`
- prototype: `NTSTATUS __stdcall(PDEVICE_OBJECT DeviceObject, PIRP Irp)`
- caller_count: `4`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180006210`
- `0x18000c1dc`
- `0x180047cd8`
- `0x18005c69c`

## callees

- `0x1800073d0`
- `0x18000b7bc`
- `0x18000c380`
- `0x180019c60`
- `0x180047030`
- `0x1800481d0`
- `0x1800485a0`
- `0x180048c60`
- `0x180049460`
- `0x180049580`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x180048386`
- `ntoskrnl!IofCompleteRequest` at `0x1800483c4`
- `ntoskrnl!IofCompleteRequest` at `0x180048386`
- `ntoskrnl!IofCompleteRequest` at `0x1800483c4`

## pseudocode

```c
NTSTATUS __stdcall KsDispatchIrp(PDEVICE_OBJECT DeviceObject, PIRP Irp)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  PFILE_OBJECT FileObject; // r8
  __int64 *FsContext; // rdx
  __int64 v7; // rdx
  int MajorFunction; // ecx
  __int64 v10; // rbp
  __int64 v11; // rsi
  int v12; // edx
  NTSTATUS v13; // edi

  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  FileObject = CurrentStackLocation->FileObject;
  if ( FileObject && (FsContext = (__int64 *)FileObject->FsContext) != 0 )
    v7 = *FsContext;
  else
    v7 = 0;
  MajorFunction = CurrentStackLocation->MajorFunction;
  if ( MajorFunction != 14 )
  {
    if ( MajorFunction == 2 )
      return (*(__int64 (__fastcall **)(PDEVICE_OBJECT, PIRP))(*(_QWORD *)v7 + 32LL))(DeviceObject, Irp);
    switch ( CurrentStackLocation->MajorFunction )
    {
      case 0u:
        if ( !*(_QWORD *)(*(_QWORD *)DeviceObject->DeviceExtension + 360LL) )
          return DispatchCreate((__int64)DeviceObject, Irp);
        if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          LOBYTE(v7) = 5;
          WPP_RECORDER_SF_(
            WPP_GLOBAL_Control->DeviceExtension,
            v7,
            1,
            157,
            (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
        }
        v10 = *(_QWORD *)(*(_QWORD *)DeviceObject->DeviceExtension + 360LL);
        v11 = v10 - 200;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(v10 - 200) + 40LL))(v10 - 200, v7);
        if ( *(_BYTE *)(v10 - 200 + 788) )
        {
          v13 = -1073741436;
        }
        else
        {
          if ( !*(_BYTE *)(v11 + 784) )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
              && LOWORD(WPP_GLOBAL_Control->DeviceType) )
            {
              LOBYTE(v12) = 5;
              WPP_RECORDER_SF_(
                WPP_GLOBAL_Control->DeviceExtension,
                v12,
                1,
                158,
                (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
            }
            Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
            KsAddIrpToCancelableQueue((PLIST_ENTRY)(v11 + 536), (PKSPIN_LOCK)(v11 + 552), Irp, KsListEntryTail, 0);
            v13 = 259;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 48LL))(v10 - 200);
            return v13;
          }
          if ( *(_BYTE *)(v10 + 48) )
          {
            if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
              {
                LOBYTE(v12) = 5;
                WPP_RECORDER_SF_(
                  WPP_GLOBAL_Control->DeviceExtension,
                  v12,
                  1,
                  160,
                  (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
              }
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 48LL))(v10 - 200);
            return DispatchCreate((__int64)DeviceObject, Irp);
          }
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
            && LOWORD(WPP_GLOBAL_Control->DeviceType) )
          {
            LOBYTE(v12) = 5;
            WPP_RECORDER_SF_(
              WPP_GLOBAL_Control->DeviceExtension,
              v12,
              1,
              159,
              (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
          }
          v13 = -1073741661;
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 48LL))(v10 - 200);
        Irp->IoStatus.Status = v13;
        IofCompleteRequest(Irp, 0);
        return v13;
      case 3u:
        return (*(__int64 (__fastcall **)(PDEVICE_OBJECT, PIRP))(*(_QWORD *)v7 + 8LL))(DeviceObject, Irp);
      case 4u:
        return (*(__int64 (__fastcall **)(PDEVICE_OBJECT, PIRP))(*(_QWORD *)v7 + 16LL))(DeviceObject, Irp);
      case 9u:
        return (*(__int64 (__fastcall **)(PDEVICE_OBJECT, PIRP))(*(_QWORD *)v7 + 24LL))(DeviceObject, Irp);
      case 0x14u:
        return (*(__int64 (__fastcall **)(PDEVICE_OBJECT, PIRP))(*(_QWORD *)v7 + 40LL))(DeviceObject, Irp);
      case 0x15u:
        return (*(__int64 (__fastcall **)(PDEVICE_OBJECT, PIRP))(*(_QWORD *)v7 + 48LL))(DeviceObject, Irp);
      case 0x16u:
        if ( *(_QWORD *)(*(_QWORD *)DeviceObject->DeviceExtension + 360LL) )
          return CKsDevice::DispatchPower(DeviceObject, Irp);
        else
          return KsDefaultDispatchPower(DeviceObject, Irp);
      case 0x17u:
        return KsDefaultForwardIrp(DeviceObject, Irp);
      case 0x1Bu:
        if ( *(_QWORD *)(*(_QWORD *)DeviceObject->DeviceExtension + 360LL) )
          return CKsDevice::DispatchPnp(DeviceObject, Irp);
        else
          return KsDefaultDispatchPnp(DeviceObject, Irp);
      default:
        Irp->IoStatus.Status = -1073741808;
        IofCompleteRequest(Irp, 0);
        return -1073741808;
    }
  }
  if ( v7 )
    return (**(__int64 (__fastcall ***)(PDEVICE_OBJECT, PIRP))v7)(DeviceObject, Irp);
  else
    return KsDefaultForwardIrp(DeviceObject, Irp);
}

```

## disassembly

```asm
0x1800481d0  push    rbx
0x1800481d2  push    rdi
0x1800481d3  sub     rsp, 38h
0x1800481d7  mov     rax, [rdx+0B8h]
0x1800481de  mov     rbx, rdx
0x1800481e1  mov     rdi, rcx
0x1800481e4  mov     r8, [rax+30h]
0x1800481e8  test    r8, r8
0x1800481eb  jz      short loc_180048223
0x1800481ed  mov     rdx, [r8+18h]
0x1800481f1  test    rdx, rdx
0x1800481f4  jz      short loc_180048223
0x1800481f6  mov     rdx, [rdx]
0x1800481f9  movzx   ecx, byte ptr [rax]
0x1800481fc  cmp     ecx, 0Eh
0x1800481ff  jnz     short loc_180048227
0x180048201  test    rdx, rdx
0x180048204  jz      loc_18004843A; jumptable 000000018004826A case 23
0x18004820a  mov     rax, [rdx]
0x18004820d  mov     rcx, rdi
0x180048210  mov     rdx, rbx
0x180048213  mov     rax, [rax]
0x180048216  call    _guard_dispatch_icall
0x18004821b  add     rsp, 38h
0x18004821f  pop     rdi
0x180048220  pop     rbx
0x180048221  retn
0x180048223  xor     edx, edx
0x180048225  jmp     short loc_1800481F9
0x180048227  cmp     ecx, 2
0x18004822a  jnz     short loc_180048246
0x18004822c  mov     rax, [rdx]
0x18004822f  mov     rcx, rdi
0x180048232  mov     rdx, rbx
0x180048235  mov     rax, [rax+20h]
0x180048239  call    _guard_dispatch_icall
0x18004823e  add     rsp, 38h
0x180048242  pop     rdi
0x180048243  pop     rbx
0x180048244  retn
0x180048246  cmp     ecx, 1Bh; switch 28 cases
0x180048249  ja      def_18004826A; jumptable 000000018004826A default case, cases 1,2,5-8,10-19,24-26
0x18004824f  lea     r8, cs:180000000h
0x180048256  movzx   eax, ds:(byte_180023458 - 180000000h)[r8+rcx]
0x18004825f  mov     ecx, ds:(jpt_18004826A - 180000000h)[r8+rax*4]
0x180048267  add     rcx, r8
0x18004826a  jmp     rcx; switch jump
0x180048270  mov     rax, [rdi+40h]; jumptable 000000018004826A case 0
0x180048274  mov     rcx, [rax]
0x180048277  cmp     qword ptr [rcx+168h], 0
0x18004827f  jnz     short loc_180048294
0x180048281  mov     rdx, rbx
0x180048284  mov     rcx, rdi
0x180048287  call    DispatchCreate
0x18004828c  add     rsp, 38h
0x180048290  pop     rdi
0x180048291  pop     rbx
0x180048292  retn
0x180048294  mov     [rsp+48h+arg_0], rbp
0x180048299  mov     [rsp+48h+arg_8], rsi
0x18004829e  mov     [rsp+48h+arg_10], r14
0x1800482a3  mov     [rsp+48h+var_18], r15
0x1800482a8  lea     r14, WPP_RECORDER_INITIALIZED
0x1800482af  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1800482b6  lea     r15, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x1800482bd  jz      short loc_1800482D1
0x1800482bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800482c6  cmp     word ptr [rcx+48h], 0
0x1800482cb  jnz     loc_180048475
0x1800482d1  mov     rax, [rdi+40h]
0x1800482d5  mov     rcx, [rax]
0x1800482d8  mov     rbp, [rcx+168h]
0x1800482df  lea     rsi, [rbp-0C8h]
0x1800482e6  mov     rax, [rsi]
0x1800482e9  mov     rcx, rsi
0x1800482ec  mov     rax, [rax+28h]
0x1800482f0  call    _guard_dispatch_icall
0x1800482f5  cmp     byte ptr [rsi+314h], 0
0x1800482fc  jnz     short loc_18004836A
0x1800482fe  cmp     byte ptr [rsi+310h], 0
0x180048305  jz      loc_1800483EA
0x18004830b  cmp     byte ptr [rbp+30h], 0
0x18004830f  jz      loc_1800484C9
0x180048315  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18004831c  jz      short loc_180048330
0x18004831e  mov     rcx, cs:WPP_GLOBAL_Control
0x180048325  cmp     word ptr [rcx+48h], 0
0x18004832a  jnz     loc_180048506
0x180048330  mov     rax, [rsi]
0x180048333  mov     rcx, rsi
0x180048336  mov     rax, [rax+30h]
0x18004833a  call    _guard_dispatch_icall
0x18004833f  mov     rdx, rbx
0x180048342  mov     rcx, rdi
0x180048345  call    DispatchCreate
0x18004834a  mov     edi, eax
0x18004834c  mov     r15, [rsp+48h+var_18]
0x180048351  mov     eax, edi
0x180048353  mov     r14, [rsp+48h+arg_10]
0x180048358  mov     rsi, [rsp+48h+arg_8]
0x18004835d  mov     rbp, [rsp+48h+arg_0]
0x180048362  add     rsp, 38h
0x180048366  pop     rdi
0x180048367  pop     rbx
0x180048368  retn
0x18004836a  mov     edi, 0C0000184h
0x18004836f  mov     rax, [rsi]
0x180048372  mov     rcx, rsi
0x180048375  mov     rax, [rax+30h]
0x180048379  call    _guard_dispatch_icall
0x18004837e  xor     edx, edx; PriorityBoost
0x180048380  mov     [rbx+30h], edi
0x180048383  mov     rcx, rbx; Irp
0x180048386  call    cs:__imp_IofCompleteRequest
0x18004838d  nop     dword ptr [rax+rax+00h]
0x180048392  jmp     short loc_18004834C
0x180048394  mov     rax, [rdi+40h]; jumptable 000000018004826A case 27
0x180048398  mov     rdx, rbx; struct _IRP *
0x18004839b  mov     rcx, [rax]
0x18004839e  cmp     qword ptr [rcx+168h], 0
0x1800483a6  mov     rcx, rdi; Object
0x1800483a9  jz      short loc_1800483DD
0x1800483ab  call    ?DispatchPnp@CKsDevice@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; CKsDevice::DispatchPnp(_DEVICE_OBJECT *,_IRP *)
0x1800483b0  add     rsp, 38h
0x1800483b4  pop     rdi
0x1800483b5  pop     rbx
0x1800483b6  retn
0x1800483b8  xor     edx, edx; jumptable 000000018004826A default case, cases 1,2,5-8,10-19,24-26
0x1800483ba  mov     dword ptr [rbx+30h], 0C0000010h
0x1800483c1  mov     rcx, rbx; Irp
0x1800483c4  call    cs:__imp_IofCompleteRequest
0x1800483cb  nop     dword ptr [rax+rax+00h]
0x1800483d0  mov     eax, 0C0000010h
0x1800483d5  add     rsp, 38h
0x1800483d9  pop     rdi
0x1800483da  pop     rbx
0x1800483db  retn
0x1800483dd  call    KsDefaultDispatchPnp
0x1800483e2  add     rsp, 38h
0x1800483e6  pop     rdi
0x1800483e7  pop     rbx
0x1800483e8  retn
0x1800483ea  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1800483f1  jnz     loc_180048496
0x1800483f7  mov     rax, [rbx+0B8h]
0x1800483fe  lea     rcx, [rsi+218h]; QueueHead
0x180048405  lea     rdx, [rcx+10h]; SpinLock
0x180048409  mov     [rsp+48h+DriverCancel], 0; DriverCancel
0x180048412  xor     r9d, r9d; ListLocation
0x180048415  mov     r8, rbx; Irp
0x180048418  or      byte ptr [rax+3], 1
0x18004841c  call    KsAddIrpToCancelableQueue
0x180048421  mov     rax, [rsi]
0x180048424  mov     rcx, rsi
0x180048427  mov     edi, 103h
0x18004842c  mov     rax, [rax+30h]
0x180048430  call    _guard_dispatch_icall
0x180048435  jmp     loc_18004834C
0x18004843a  mov     rdx, rbx; jumptable 000000018004826A case 23
0x18004843d  mov     rcx, rdi; DeviceObject
0x180048440  call    KsDefaultForwardIrp
0x180048445  jmp     loc_18004821B
0x18004844a  mov     rax, [rdi+40h]; jumptable 000000018004826A case 22
0x18004844e  mov     rdx, rbx; Irp
0x180048451  mov     rcx, [rax]
0x180048454  cmp     qword ptr [rcx+168h], 0
0x18004845c  mov     rcx, rdi; struct _DEVICE_OBJECT *
0x18004845f  jz      short loc_18004846B
0x180048461  call    ?DispatchPower@CKsDevice@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; CKsDevice::DispatchPower(_DEVICE_OBJECT *,_IRP *)
0x180048466  jmp     loc_18004821B
0x18004846b  call    KsDefaultDispatchPower
0x180048470  jmp     loc_18004821B
0x180048475  mov     rcx, [rcx+40h]
0x180048479  mov     r9d, 9Dh
0x18004847f  mov     r8d, 1
0x180048485  mov     [rsp+48h+DriverCancel], r15
0x18004848a  mov     dl, 5
0x18004848c  call    WPP_RECORDER_SF_
0x180048491  jmp     loc_1800482D1
0x180048496  mov     rcx, cs:WPP_GLOBAL_Control
0x18004849d  cmp     word ptr [rcx+48h], 0
0x1800484a2  jz      loc_1800483F7
0x1800484a8  mov     rcx, [rcx+40h]
0x1800484ac  mov     r9d, 9Eh
0x1800484b2  mov     r8d, 1
0x1800484b8  mov     [rsp+48h+DriverCancel], r15
0x1800484bd  mov     dl, 5
0x1800484bf  call    WPP_RECORDER_SF_
0x1800484c4  jmp     loc_1800483F7
0x1800484c9  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1800484d0  jz      short loc_1800484FC
0x1800484d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800484d9  cmp     word ptr [rcx+48h], 0
0x1800484de  jz      short loc_1800484FC
0x1800484e0  mov     rcx, [rcx+40h]
0x1800484e4  mov     r9d, 9Fh
0x1800484ea  mov     r8d, 1
0x1800484f0  mov     [rsp+48h+DriverCancel], r15
0x1800484f5  mov     dl, 5
0x1800484f7  call    WPP_RECORDER_SF_
0x1800484fc  mov     edi, 0C00000A3h
0x180048501  jmp     loc_18004836F
0x180048506  mov     rcx, [rcx+40h]
0x18004850a  mov     r9d, 0A0h
0x180048510  mov     r8d, 1
0x180048516  mov     [rsp+48h+DriverCancel], r15
0x18004851b  mov     dl, 5
0x18004851d  call    WPP_RECORDER_SF_
0x180048522  jmp     loc_180048330
0x180048527  mov     rax, [rdx]; jumptable 000000018004826A case 3
0x18004852a  mov     rcx, rdi
0x18004852d  mov     rdx, rbx
0x180048530  mov     rax, [rax+8]
0x180048534  call    _guard_dispatch_icall
0x180048539  jmp     loc_18004821B
0x18004853e  mov     rax, [rdx]; jumptable 000000018004826A case 4
0x180048541  mov     rcx, rdi
0x180048544  mov     rdx, rbx
0x180048547  mov     rax, [rax+10h]
0x18004854b  call    _guard_dispatch_icall
0x180048550  jmp     loc_18004821B
0x180048555  mov     rax, [rdx]; jumptable 000000018004826A case 9
0x180048558  mov     rcx, rdi
0x18004855b  mov     rdx, rbx
0x18004855e  mov     rax, [rax+18h]
0x180048562  call    _guard_dispatch_icall
0x180048567  jmp     loc_18004821B
0x18004856c  mov     rax, [rdx]; jumptable 000000018004826A case 20
0x18004856f  mov     rcx, rdi
0x180048572  mov     rdx, rbx
0x180048575  mov     rax, [rax+28h]
0x180048579  call    _guard_dispatch_icall
0x18004857e  jmp     loc_18004821B
0x180048583  mov     rax, [rdx]; jumptable 000000018004826A case 21
0x180048586  mov     rcx, rdi
0x180048589  mov     rdx, rbx
0x18004858c  mov     rax, [rax+30h]
0x180048590  call    _guard_dispatch_icall
0x180048595  jmp     loc_18004821B
```
