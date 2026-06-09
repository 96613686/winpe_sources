# RxAcquireFcbForReadAhead

- ea: `0x140075b10`
- end: `0x140075cd6`
- name: `RxAcquireFcbForReadAhead`
- size: `454`
- prototype: `BOOLEAN __stdcall(PVOID Null, BOOLEAN Wait)`
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x140003410`
- `0x1400037e0`
- `0x140008f60`
- `0x140009ea0`
- `0x14000e770`
- `0x140010d70`
- `0x140016e20`
- `0x140016e70`
- `0x140075b10`

## import_xrefs

- `ntoskrnl!IoSetTopLevelIrp` at `0x140075be5`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140075be5`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140075bc9`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140075bc9`

## pseudocode

```c
BOOLEAN __stdcall RxAcquireFcbForReadAhead(PVOID Null, BOOLEAN Wait)
{
  char v2; // bp
  enum _RX_BLOCK_CONDITION *RxContext; // rbx
  BOOLEAN v6; // di
  unsigned __int8 v7; // zf
  __int64 v9; // [rsp+50h] [rbp+8h] BYREF

  v2 = 0;
  RxContext = 0;
  LOBYTE(v9) = 1;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids, Null);
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
        goto LABEL_15;
      v7 = Wait == 0;
    }
    if ( (unsigned __int8)RxWaitForStableLViewOnFcbAndAcquireRundown(RxContext, (PMRX_FCB)Null, v7, 0, &v9) )
    {
      if ( !(_BYTE)v9 )
        v2 = 1;
    }
    else if ( !(_BYTE)v9 )
    {
      goto LABEL_13;
    }
  }
  v6 = ExAcquireResourceSharedLite(*((PERESOURCE *)Null + 1), Wait);
  if ( v6 )
  {
    IoSetTopLevelIrp((PIRP)2);
    if ( RxContext )
    {
      if ( v2 )
        RxRemoveLViewFromRxContextNoRelease(RxContext);
      goto LABEL_14;
    }
    goto LABEL_15;
  }
  if ( v2 )
  {
    if ( !RxContext )
    {
      RxReleaseRundownDerefView(Null);
      goto LABEL_15;
    }
    RxReleaseLViewRundown(RxContext);
    goto LABEL_14;
  }
LABEL_13:
  if ( RxContext )
LABEL_14:
    RxDereferenceAndDeleteRxContext_Real((PRX_CONTEXT)RxContext);
LABEL_15:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x140075b10  sub     rsp, 48h
0x140075b14  mov     [rsp+48h+arg_8], rbx
0x140075b19  mov     [rsp+48h+arg_10], rbp
0x140075b1e  xor     bpl, bpl
0x140075b21  mov     [rsp+48h+arg_18], rsi
0x140075b26  xor     ebx, ebx
0x140075b28  mov     [rsp+48h+var_10], r14
0x140075b2d  mov     rsi, rcx
0x140075b30  mov     [rsp+48h+var_18], r15
0x140075b35  movzx   r14d, dl
0x140075b39  mov     byte ptr [rsp+48h+arg_0], 1
0x140075b3e  mov     rcx, cs:WPP_GLOBAL_Control
0x140075b45  lea     r15, WPP_GLOBAL_Control
0x140075b4c  cmp     rcx, r15
0x140075b4f  jnz     loc_140075C4F
0x140075b55  mov     [rsp+48h+var_8], rdi
0x140075b5a  cmp     [rsi+80h], rbx
0x140075b61  jz      short loc_140075BC1
0x140075b63  xor     dil, dil
0x140075b66  test    r14b, r14b
0x140075b69  jz      short loc_140075B93
0x140075b6b  mov     rax, [rsi+78h]
0x140075b6f  mov     r8d, 2; InitialContextFlags
0x140075b75  xor     ecx, ecx; Irp
0x140075b77  mov     rdx, [rax+20h]
0x140075b7b  mov     rdx, [rdx+30h]; RxDeviceObject
0x140075b7f  call    RxCreateRxContext
0x140075b84  mov     rbx, rax
0x140075b87  test    rax, rax
0x140075b8a  jz      loc_140075C12
0x140075b90  test    r14b, r14b
0x140075b93  setz    r8b
0x140075b97  lea     rax, [rsp+48h+arg_0]
0x140075b9c  xor     r9d, r9d
0x140075b9f  mov     [rsp+48h+var_28], rax; __int64
0x140075ba4  mov     rdx, rsi; MrxFcb
0x140075ba7  mov     rcx, rbx; Condition
0x140075baa  call    RxWaitForStableLViewOnFcbAndAcquireRundown
0x140075baf  test    al, al
0x140075bb1  jz      loc_140075C83
0x140075bb7  cmp     byte ptr [rsp+48h+arg_0], dil
0x140075bbc  jnz     short loc_140075BC1
0x140075bbe  mov     bpl, 1
0x140075bc1  mov     rcx, [rsi+8]; Resource
0x140075bc5  movzx   edx, r14b; Wait
0x140075bc9  call    cs:__imp_ExAcquireResourceSharedLite
0x140075bd0  nop     dword ptr [rax+rax+00h]
0x140075bd5  movzx   edi, al
0x140075bd8  test    al, al
0x140075bda  jz      loc_140075C93
0x140075be0  mov     ecx, 2; Irp
0x140075be5  call    cs:__imp_IoSetTopLevelIrp
0x140075bec  nop     dword ptr [rax+rax+00h]
0x140075bf1  test    rbx, rbx
0x140075bf4  jz      short loc_140075C12
0x140075bf6  test    bpl, bpl
0x140075bf9  jz      short loc_140075C0A
0x140075bfb  mov     rcx, rbx
0x140075bfe  call    RxRemoveLViewFromRxContextNoRelease
0x140075c03  jmp     short loc_140075C0A
0x140075c05  test    rbx, rbx
0x140075c08  jz      short loc_140075C12
0x140075c0a  mov     rcx, rbx; RxContext
0x140075c0d  call    RxDereferenceAndDeleteRxContext_Real
0x140075c12  mov     rcx, cs:WPP_GLOBAL_Control
0x140075c19  mov     r14, [rsp+48h+var_10]
0x140075c1e  cmp     rcx, r15
0x140075c21  mov     r15, [rsp+48h+var_18]
0x140075c26  mov     rsi, [rsp+48h+arg_18]
0x140075c2b  mov     rbp, [rsp+48h+arg_10]
0x140075c30  mov     rbx, [rsp+48h+arg_8]
0x140075c35  jz      short loc_140075C40
0x140075c37  test    dword ptr [rcx+2Ch], 100h
0x140075c3e  jnz     short loc_140075CB2
0x140075c40  movzx   eax, dil
0x140075c44  mov     rdi, [rsp+48h+var_8]
0x140075c49  add     rsp, 48h
0x140075c4d  retn
0x140075c4f  test    dword ptr [rcx+2Ch], 100h
0x140075c56  jz      loc_140075B55
0x140075c5c  cmp     byte ptr [rcx+29h], 2
0x140075c60  jb      loc_140075B55
0x140075c66  mov     rcx, [rcx+18h]
0x140075c6a  lea     r8, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids
0x140075c71  mov     edx, 19h
0x140075c76  mov     r9, rsi
0x140075c79  call    WPP_SF_q
0x140075c7e  jmp     loc_140075B55
0x140075c83  cmp     byte ptr [rsp+48h+arg_0], dil
0x140075c88  jz      loc_140075C05
0x140075c8e  jmp     loc_140075BC1
0x140075c93  test    bpl, bpl
0x140075c96  jz      loc_140075C05
0x140075c9c  test    rbx, rbx
0x140075c9f  jz      loc_14007FA0A
0x140075ca5  mov     rcx, rbx
0x140075ca8  call    RxReleaseLViewRundown
0x140075cad  jmp     loc_140075C0A
0x140075cb2  cmp     byte ptr [rcx+29h], 2
0x140075cb6  jb      short loc_140075C40
0x140075cb8  mov     rcx, [rcx+18h]
0x140075cbc  lea     r8, WPP_16f2bee2656c381c8186d78b34bda825_Traceguids
0x140075cc3  movzx   r9d, dil
0x140075cc7  mov     edx, 1Ah
0x140075ccc  call    WPP_SF_d
0x140075cd1  jmp     loc_140075C40
0x14007fa0a  mov     rcx, rsi
0x14007fa0d  call    RxReleaseRundownDerefView
0x14007fa12  nop
0x14007fa13  jmp     loc_140075C12
```
