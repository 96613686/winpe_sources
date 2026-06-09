# RxLowIoCompletionTail

- ea: `0x140002300`
- end: `0x140002577`
- name: `RxLowIoCompletionTail`
- size: `631`
- prototype: `NTSTATUS __stdcall(PRX_CONTEXT RxContext)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140002170`
- `0x140067ad0`

## callees

- `0x140002300`
- `0x1400027b0`
- `0x140016e20`
- `0x14002442c`
- `0x140025d00`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1400024d9`
- `ntoskrnl!ObfDereferenceObject` at `0x1400024d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400024f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002537`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400024f8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140002537`
- `ntoskrnl!KeGetCurrentIrql` at `0x140002335`
- `ntoskrnl!KeGetCurrentIrql` at `0x140002335`

## pseudocode

```c
NTSTATUS __stdcall RxLowIoCompletionTail(PRX_CONTEXT RxContext)
{
  __int64 v1; // rdx
  __int64 v2; // r8
  int v3; // esi
  __int64 v5; // rdx
  struct _LIST_ENTRY *Blink; // rcx
  struct _LIST_ENTRY *Flink; // rax
  __int64 v8; // rdx
  unsigned int v9; // edi
  struct _LIST_ENTRY *v11; // rcx
  struct _LIST_ENTRY *v12; // rax
  int v13; // eax
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx

  v3 = *((unsigned __int16 *)&RxContext->9 + 60);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_Lq(WPP_GLOBAL_Control->AttachedDevice, v1, v2, *((unsigned __int16 *)&RxContext->9 + 60), RxContext);
  }
  if ( KeGetCurrentIrql() >= 2u && (*((_BYTE *)&RxContext->9 + 122) & 8) == 0 )
  {
    v9 = -1073741802;
    goto LABEL_7;
  }
  Blink = RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.WaitListHead.Blink;
  if ( Blink )
  {
    Flink = Blink[42].Flink;
    if ( Flink )
    {
      LOBYTE(v5) = 9;
      ((void (__fastcall *)(PRX_CONTEXT, __int64))Flink)(RxContext, v5);
    }
  }
  v9 = (*((__int64 (__fastcall **)(PRX_CONTEXT))&RxContext->9 + 16))(RxContext);
  switch ( v9 )
  {
    case 0xC0000016:
    case 0xC0410003:
      goto LABEL_7;
    case 0xC0410001:
      if ( !RxContext->Create.NtCreateParameters.AllocationSize.LowPart )
        goto LABEL_7;
      break;
    case 0xC01C0006:
    case 0x103u:
LABEL_7:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 18, &WPP_ab807026a5683cdcaf6085912ea536d5_Traceguids, v9);
      }
      return v9;
  }
  if ( (unsigned int)(v3 - 6) < 2 )
  {
    v13 = *((_DWORD *)&RxContext->9 + 35);
    if ( (v13 == 1344068 || v13 == 1344075) && (v15 = (void *)*((_QWORD *)&RxContext->9 + 18)) != 0 )
    {
      ExFreePoolWithTag(v15, 0x77427852u);
    }
    else if ( (v13 == 1327692 || v13 == 1327699) && (v16 = (void *)*((_QWORD *)&RxContext->9 + 18)) != 0 )
    {
      ExFreePoolWithTag(v16, 0x72427852u);
    }
    else
    {
      v14 = (void *)*((_QWORD *)&RxContext->9 + 18);
      if ( !v14 )
        goto LABEL_14;
      ObfDereferenceObject(v14);
    }
    *((_QWORD *)&RxContext->9 + 18) = 0;
  }
LABEL_14:
  if ( (*((_BYTE *)&RxContext->9 + 122) & 1) == 0 )
  {
    v11 = RxContext->NonPagedFcb->AdvancedFcbHeaderMutex.Event.Header.WaitListHead.Blink;
    if ( v11 )
    {
      v12 = v11[42].Flink;
      if ( v12 )
      {
        LOBYTE(v8) = 10;
        ((void (__fastcall *)(PRX_CONTEXT, __int64))v12)(RxContext, v8);
      }
    }
    RxCompleteRequestEx(RxContext, RxContext->CurrentIrp, v9);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 19, &WPP_ab807026a5683cdcaf6085912ea536d5_Traceguids, v9);
  }
  return v9;
}

```

## disassembly

```asm
0x140002300  mov     [rsp+arg_8], rbx
0x140002305  mov     [rsp+arg_10], rbp
0x14000230a  push    rsi
0x14000230b  sub     rsp, 30h
0x14000230f  movzx   esi, word ptr [rcx+208h]
0x140002316  mov     rbx, rcx
0x140002319  mov     rcx, cs:WPP_GLOBAL_Control
0x140002320  lea     rbp, WPP_GLOBAL_Control
0x140002327  cmp     rcx, rbp
0x14000232a  jnz     loc_140002465
0x140002330  mov     [rsp+38h+arg_0], rdi
0x140002335  call    cs:__imp_KeGetCurrentIrql
0x14000233c  nop     dword ptr [rax+rax+00h]
0x140002341  cmp     al, 2
0x140002343  jnb     loc_140002490
0x140002349  mov     rax, [rbx+50h]
0x14000234d  mov     rcx, [rax+160h]
0x140002354  test    rcx, rcx
0x140002357  jz      short loc_14000236F
0x140002359  mov     rax, [rcx+2A0h]
0x140002360  test    rax, rax
0x140002363  jz      short loc_14000236F
0x140002365  mov     dl, 9
0x140002367  mov     rcx, rbx
0x14000236a  call    _guard_dispatch_icall
0x14000236f  mov     rax, [rbx+210h]
0x140002376  mov     rcx, rbx
0x140002379  call    _guard_dispatch_icall
0x14000237e  mov     edi, eax
0x140002380  cmp     eax, 0C0000016h
0x140002385  jnz     short loc_1400023AF
0x140002387  mov     rcx, cs:WPP_GLOBAL_Control
0x14000238e  cmp     rcx, rbp
0x140002391  jnz     loc_140002545
0x140002397  mov     rbx, [rsp+38h+arg_8]
0x14000239c  mov     eax, edi
0x14000239e  mov     rdi, [rsp+38h+arg_0]
0x1400023a3  mov     rbp, [rsp+38h+arg_10]
0x1400023a8  add     rsp, 30h
0x1400023ac  pop     rsi
0x1400023ad  retn
0x1400023af  cmp     edi, 0C0410003h
0x1400023b5  jz      short loc_140002387
0x1400023b7  cmp     edi, 0C0410001h
0x1400023bd  jz      loc_140002514
0x1400023c3  cmp     edi, 0C01C0006h
0x1400023c9  jz      short loc_140002387
0x1400023cb  cmp     edi, 103h
0x1400023d1  jz      short loc_140002387
0x1400023d3  sub     esi, 6
0x1400023d6  jz      loc_1400024A7
0x1400023dc  cmp     esi, 1
0x1400023df  jz      loc_1400024A7
0x1400023e5  test    byte ptr [rbx+20Ah], 1
0x1400023ec  jnz     short loc_140002423
0x1400023ee  mov     rax, [rbx+50h]
0x1400023f2  mov     rcx, [rax+160h]
0x1400023f9  test    rcx, rcx
0x1400023fc  jz      short loc_140002414
0x1400023fe  mov     rax, [rcx+2A0h]
0x140002405  test    rax, rax
0x140002408  jz      short loc_140002414
0x14000240a  mov     dl, 0Ah
0x14000240c  mov     rcx, rbx
0x14000240f  call    _guard_dispatch_icall
0x140002414  mov     rdx, [rbx+28h]; Irp
0x140002418  mov     r8d, edi
0x14000241b  mov     rcx, rbx; RxContext
0x14000241e  call    RxCompleteRequestEx
0x140002423  mov     rcx, cs:WPP_GLOBAL_Control
0x14000242a  cmp     rcx, rbp
0x14000242d  jz      loc_140002397
0x140002433  mov     eax, [rcx+2Ch]
0x140002436  test    al, 4
0x140002438  jz      loc_140002397
0x14000243e  cmp     byte ptr [rcx+29h], 4
0x140002442  jb      loc_140002397
0x140002448  mov     rcx, [rcx+18h]
0x14000244c  lea     r8, WPP_ab807026a5683cdcaf6085912ea536d5_Traceguids
0x140002453  mov     edx, 13h
0x140002458  mov     r9d, edi
0x14000245b  call    WPP_SF_d
0x140002460  jmp     loc_140002397
0x140002465  mov     eax, [rcx+2Ch]
0x140002468  test    al, 4
0x14000246a  jz      loc_140002330
0x140002470  cmp     byte ptr [rcx+29h], 4
0x140002474  jb      loc_140002330
0x14000247a  mov     rcx, [rcx+18h]
0x14000247e  mov     r9d, esi
0x140002481  mov     [rsp+38h+var_18], rbx
0x140002486  call    WPP_SF_Lq
0x14000248b  jmp     loc_140002330
0x140002490  test    byte ptr [rbx+20Ah], 8
0x140002497  jnz     loc_140002349
0x14000249d  mov     edi, 0C0000016h
0x1400024a2  jmp     loc_140002387
0x1400024a7  mov     eax, [rbx+21Ch]
0x1400024ad  cmp     eax, 148244h
0x1400024b2  jz      short loc_1400024E7
0x1400024b4  cmp     eax, 14824Bh
0x1400024b9  jz      short loc_1400024E7
0x1400024bb  cmp     eax, 14424Ch
0x1400024c0  jz      short loc_140002526
0x1400024c2  cmp     eax, 144253h
0x1400024c7  jz      short loc_140002526
0x1400024c9  mov     rcx, [rbx+220h]; Object
0x1400024d0  test    rcx, rcx
0x1400024d3  jz      loc_1400023E5
0x1400024d9  call    cs:__imp_ObfDereferenceObject
0x1400024e0  nop     dword ptr [rax+rax+00h]
0x1400024e5  jmp     short loc_140002504
0x1400024e7  mov     rcx, [rbx+220h]; P
0x1400024ee  test    rcx, rcx
0x1400024f1  jz      short loc_1400024BB
0x1400024f3  mov     edx, 77427852h; Tag
0x1400024f8  call    cs:__imp_ExFreePoolWithTag
0x1400024ff  nop     dword ptr [rax+rax+00h]
0x140002504  mov     qword ptr [rbx+220h], 0
0x14000250f  jmp     loc_1400023E5
0x140002514  cmp     dword ptr [rbx+198h], 0
0x14000251b  jz      loc_140002387
0x140002521  jmp     loc_1400023D3
0x140002526  mov     rcx, [rbx+220h]; P
0x14000252d  test    rcx, rcx
0x140002530  jz      short loc_1400024C9
0x140002532  mov     edx, 72427852h; Tag
0x140002537  call    cs:__imp_ExFreePoolWithTag
0x14000253e  nop     dword ptr [rax+rax+00h]
0x140002543  jmp     short loc_140002504
0x140002545  mov     eax, [rcx+2Ch]
0x140002548  test    al, 4
0x14000254a  jz      loc_140002397
0x140002550  cmp     byte ptr [rcx+29h], 4
0x140002554  jb      loc_140002397
0x14000255a  mov     rcx, [rcx+18h]
0x14000255e  lea     r8, WPP_ab807026a5683cdcaf6085912ea536d5_Traceguids
0x140002565  mov     edx, 12h
0x14000256a  mov     r9d, edi
0x14000256d  call    WPP_SF_d
0x140002572  jmp     loc_140002397
```
