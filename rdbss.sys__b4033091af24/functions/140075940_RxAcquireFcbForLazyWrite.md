# RxAcquireFcbForLazyWrite

- ea: `0x140075940`
- end: `0x140075afe`
- name: `RxAcquireFcbForLazyWrite`
- size: `446`
- prototype: `BOOLEAN __stdcall(PVOID Null, BOOLEAN Wait)`
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x140003410`
- `0x1400037e0`
- `0x140008f60`
- `0x140009ea0`
- `0x14000e770`
- `0x1400108f0`
- `0x140010d70`
- `0x140016e20`
- `0x140016e70`
- `0x140075940`

## import_xrefs

- `ntoskrnl!IoSetTopLevelIrp` at `0x140075a2e`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140075a2e`

## pseudocode

```c
BOOLEAN __stdcall RxAcquireFcbForLazyWrite(PVOID Null, BOOLEAN Wait)
{
  char v4; // r14
  enum _RX_BLOCK_CONDITION *RxContext; // rbx
  BOOLEAN v6; // di
  unsigned __int8 v7; // zf
  __int64 v9; // [rsp+50h] [rbp+8h] BYREF

  v4 = 0;
  RxContext = 0;
  LOBYTE(v9) = 1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids, Null);
  }
  if ( *((_QWORD *)Null + 16) )
  {
    v6 = 0;
    v7 = Wait == 0;
    if ( Wait )
    {
      RxContext = (enum _RX_BLOCK_CONDITION *)RxCreateRxContext(
                                                0,
                                                *(PRDBSS_DEVICE_OBJECT *)(*(_QWORD *)(*((_QWORD *)Null + 15) + 32LL)
                                                                        + 48LL),
                                                2u);
      if ( !RxContext )
        goto LABEL_8;
      v7 = Wait == 0;
    }
    if ( (unsigned __int8)RxWaitForStableLViewOnFcbAndAcquireRundown(RxContext, (PMRX_FCB)Null, v7, 0, &v9) )
    {
      if ( !(_BYTE)v9 )
        v4 = 1;
    }
    else if ( !(_BYTE)v9 )
    {
      goto LABEL_6;
    }
  }
  v6 = RxAcquirePagingIoResourceShared(0, Null, Wait);
  if ( v6 )
  {
    IoSetTopLevelIrp((PIRP)2);
    if ( !RxContext )
      goto LABEL_8;
    if ( v4 )
      RxRemoveLViewFromRxContextNoRelease(RxContext);
    goto LABEL_7;
  }
  if ( v4 )
  {
    if ( !RxContext )
    {
      RxReleaseRundownDerefView(Null);
      goto LABEL_8;
    }
    RxReleaseLViewRundown(RxContext);
    goto LABEL_7;
  }
LABEL_6:
  if ( RxContext )
LABEL_7:
    RxDereferenceAndDeleteRxContext_Real((PRX_CONTEXT)RxContext);
LABEL_8:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x140075940  sub     rsp, 48h
0x140075944  mov     [rsp+48h+arg_8], rbx
0x140075949  mov     [rsp+48h+arg_10], rbp
0x14007594e  movzx   ebp, dl
0x140075951  mov     [rsp+48h+arg_18], rsi
0x140075956  mov     rsi, rcx
0x140075959  mov     [rsp+48h+var_10], r14
0x14007595e  xor     r14b, r14b
0x140075961  xor     ebx, ebx
0x140075963  mov     [rsp+48h+var_18], r15
0x140075968  mov     byte ptr [rsp+48h+arg_0], 1
0x14007596d  mov     rcx, cs:WPP_GLOBAL_Control
0x140075974  lea     r15, WPP_GLOBAL_Control
0x14007597b  cmp     rcx, r15
0x14007597e  jnz     loc_140075AAB
0x140075984  mov     [rsp+48h+var_8], rdi
0x140075989  cmp     [rsi+80h], rbx
0x140075990  jz      short loc_140075A10
0x140075992  xor     dil, dil
0x140075995  test    bpl, bpl
0x140075998  jnz     loc_140075A7E
0x14007599e  setz    r8b
0x1400759a2  lea     rax, [rsp+48h+arg_0]
0x1400759a7  xor     r9d, r9d
0x1400759aa  mov     [rsp+48h+var_28], rax; __int64
0x1400759af  mov     rdx, rsi; MrxFcb
0x1400759b2  mov     rcx, rbx; Condition
0x1400759b5  call    RxWaitForStableLViewOnFcbAndAcquireRundown
0x1400759ba  test    al, al
0x1400759bc  jnz     short loc_140075A06
0x1400759be  cmp     byte ptr [rsp+48h+arg_0], dil
0x1400759c3  jnz     short loc_140075A10
0x1400759c5  test    rbx, rbx
0x1400759c8  jz      short loc_1400759D2
0x1400759ca  mov     rcx, rbx; RxContext
0x1400759cd  call    RxDereferenceAndDeleteRxContext_Real
0x1400759d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400759d9  mov     r14, [rsp+48h+var_10]
0x1400759de  cmp     rcx, r15
0x1400759e1  mov     r15, [rsp+48h+var_18]
0x1400759e6  mov     rsi, [rsp+48h+arg_18]
0x1400759eb  mov     rbp, [rsp+48h+arg_10]
0x1400759f0  mov     rbx, [rsp+48h+arg_8]
0x1400759f5  jnz     short loc_140075A51
0x1400759f7  movzx   eax, dil
0x1400759fb  mov     rdi, [rsp+48h+var_8]
0x140075a00  add     rsp, 48h
0x140075a04  retn
0x140075a06  cmp     byte ptr [rsp+48h+arg_0], dil
0x140075a0b  jnz     short loc_140075A10
0x140075a0d  mov     r14b, 1
0x140075a10  movzx   r8d, bpl
0x140075a14  mov     rdx, rsi
0x140075a17  xor     ecx, ecx
0x140075a19  call    RxAcquirePagingIoResourceShared
0x140075a1e  movzx   edi, al
0x140075a21  test    al, al
0x140075a23  jz      loc_140075ADF
0x140075a29  mov     ecx, 2; Irp
0x140075a2e  call    cs:__imp_IoSetTopLevelIrp
0x140075a35  nop     dword ptr [rax+rax+00h]
0x140075a3a  test    rbx, rbx
0x140075a3d  jz      short loc_1400759D2
0x140075a3f  test    r14b, r14b
0x140075a42  jz      short loc_1400759CA
0x140075a44  mov     rcx, rbx
0x140075a47  call    RxRemoveLViewFromRxContextNoRelease
0x140075a4c  jmp     loc_1400759CA
0x140075a51  test    dword ptr [rcx+2Ch], 100h
0x140075a58  jz      short loc_1400759F7
0x140075a5a  cmp     byte ptr [rcx+29h], 2
0x140075a5e  jb      short loc_1400759F7
0x140075a60  mov     rcx, [rcx+18h]
0x140075a64  lea     r8, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids
0x140075a6b  movzx   r9d, dil
0x140075a6f  mov     edx, 17h
0x140075a74  call    WPP_SF_d
0x140075a79  jmp     loc_1400759F7
0x140075a7e  mov     rax, [rsi+78h]
0x140075a82  mov     r8d, 2; InitialContextFlags
0x140075a88  xor     ecx, ecx; Irp
0x140075a8a  mov     rdx, [rax+20h]
0x140075a8e  mov     rdx, [rdx+30h]; RxDeviceObject
0x140075a92  call    RxCreateRxContext
0x140075a97  mov     rbx, rax
0x140075a9a  test    rax, rax
0x140075a9d  jz      loc_1400759D2
0x140075aa3  test    bpl, bpl
0x140075aa6  jmp     loc_14007599E
0x140075aab  test    dword ptr [rcx+2Ch], 100h
0x140075ab2  jz      loc_140075984
0x140075ab8  cmp     byte ptr [rcx+29h], 2
0x140075abc  jb      loc_140075984
0x140075ac2  mov     rcx, [rcx+18h]
0x140075ac6  lea     r8, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids
0x140075acd  mov     edx, 16h
0x140075ad2  mov     r9, rsi
0x140075ad5  call    WPP_SF_q
0x140075ada  jmp     loc_140075984
0x140075adf  test    r14b, r14b
0x140075ae2  jz      loc_1400759C5
0x140075ae8  test    rbx, rbx
0x140075aeb  jz      loc_14007F9FC
0x140075af1  mov     rcx, rbx
0x140075af4  call    RxReleaseLViewRundown
0x140075af9  jmp     loc_1400759CA
0x14007f9fc  mov     rcx, rsi
0x14007f9ff  call    RxReleaseRundownDerefView
0x14007fa04  nop
0x14007fa05  jmp     loc_1400759D2
```
