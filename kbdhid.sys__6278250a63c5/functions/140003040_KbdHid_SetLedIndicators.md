# KbdHid_SetLedIndicators

- ea: `0x140003040`
- end: `0x140003468`
- name: `KbdHid_SetLedIndicators`
- size: `1064`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x140003470`

## callees

- `0x140003040`
- `0x140005d88`
- `0x140007130`

## import_xrefs

- `ntoskrnl!IoSetCompletionRoutineEx` at `0x140003347`
- `ntoskrnl!IoSetCompletionRoutineEx` at `0x140003347`
- `ntoskrnl!IoFreeMdl` at `0x140003439`
- `ntoskrnl!IoFreeMdl` at `0x140003439`
- `ntoskrnl!IofCallDriver` at `0x140003371`
- `ntoskrnl!IofCallDriver` at `0x140003371`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003414`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003425`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003414`
- `ntoskrnl!ExFreePoolWithTag` at `0x140003425`
- `ntoskrnl!IofCompleteRequest` at `0x1400030ac`
- `ntoskrnl!IofCompleteRequest` at `0x140003160`
- `ntoskrnl!IofCompleteRequest` at `0x1400033fb`
- `ntoskrnl!IofCompleteRequest` at `0x1400030ac`
- `ntoskrnl!IofCompleteRequest` at `0x140003160`
- `ntoskrnl!IofCompleteRequest` at `0x1400033fb`
- `ntoskrnl!ExAllocatePool2` at `0x14000313f`
- `ntoskrnl!ExAllocatePool2` at `0x140003180`
- `ntoskrnl!ExAllocatePool2` at `0x14000313f`
- `ntoskrnl!ExAllocatePool2` at `0x140003180`
- `ntoskrnl!IoAllocateMdl` at `0x1400031b9`
- `ntoskrnl!IoAllocateMdl` at `0x1400031b9`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400031e0`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400031e0`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140003455`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140003455`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140003092`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140003092`
- `HIDPARSE!HidP_SetUsages` at `0x1400033c7`
- `HIDPARSE!HidP_SetUsages` at `0x1400033c7`
- `HIDPARSE!HidP_UnsetUsages` at `0x1400032a0`
- `HIDPARSE!HidP_UnsetUsages` at `0x1400032a0`

## pseudocode

```c
NTSTATUS __fastcall KbdHid_SetLedIndicators(__int64 a1, __int64 a2, IRP *a3)
{
  __int64 v3; // rbx
  NTSTATUS v7; // eax
  int v8; // edx
  NTSTATUS v9; // ebp
  int v11; // ebx
  __int64 Pool2; // r15
  void *v13; // rax
  struct _MDL *v14; // rbp
  NTSTATUS v15; // r12d
  struct _MDL *Mdl; // rax
  __int16 v17; // cx
  ULONG v18; // edx
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  NTSTATUS v22; // eax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  struct _IO_STACK_LOCATION *v24; // rax
  struct _IO_STACK_LOCATION *v25; // rax
  ULONG UsageLength; // [rsp+40h] [rbp-58h] BYREF
  USHORT UsageList[4]; // [rsp+48h] [rbp-50h] BYREF

  v3 = *(_QWORD *)(a1 + 112);
  UsageLength = 0;
  v7 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(a1 + 152), a3, File, 1u, 0x20u);
  v9 = v7;
  if ( v7 < 0 )
  {
    a3->IoStatus.Status = v7;
    IofCompleteRequest(a3, 0);
    return v9;
  }
  if ( !*(_BYTE *)(a1 + 88) )
  {
    v11 = -1073741436;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v8) = 2;
      WPP_RECORDER_SF_qqd(
        WPP_GLOBAL_Control->DeviceExtension,
        v8,
        3,
        25,
        (__int64)WPP_a3eb93ac5d7d3982e3cdea956b1ca812_Traceguids,
        *(_QWORD *)a1,
        (char)a3,
        132);
    }
    goto LABEL_10;
  }
  if ( !*(_WORD *)(v3 + 14) )
  {
    v11 = 0;
    a3->IoStatus.Status = 0;
LABEL_11:
    IofCompleteRequest(a3, 0);
LABEL_37:
    IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(a1 + 152), a3, 0x20u);
    return v11;
  }
  Pool2 = ExAllocatePool2(64, 16, 1214538315);
  if ( !Pool2 )
  {
    v11 = -1073741670;
LABEL_10:
    a3->IoStatus.Status = v11;
    goto LABEL_11;
  }
  v13 = (void *)ExAllocatePool2(64, *(unsigned __int16 *)(v3 + 14), 1214538315);
  *(_QWORD *)Pool2 = v13;
  if ( !v13 )
  {
    v14 = 0;
    v15 = -1073741670;
    a3->IoStatus.Status = -1073741670;
LABEL_33:
    IofCompleteRequest(a3, 0);
    v11 = v15;
    if ( *(_QWORD *)Pool2 )
      ExFreePoolWithTag(*(PVOID *)Pool2, 0);
    ExFreePoolWithTag((PVOID)Pool2, 0);
    if ( v14 )
      IoFreeMdl(v14);
    goto LABEL_37;
  }
  Mdl = IoAllocateMdl(v13, *(unsigned __int16 *)(v3 + 14), 0, 0, 0);
  v14 = Mdl;
  if ( !Mdl )
  {
    v15 = -1073741670;
    a3->IoStatus.Status = -1073741670;
    goto LABEL_33;
  }
  MmBuildMdlForNonPagedPool(Mdl);
  v17 = *(_WORD *)(a2 + 2);
  v18 = UsageLength;
  if ( (v17 & 4) != 0 )
  {
    UsageList[UsageLength] = 2;
    UsageLength = ++v18;
  }
  if ( (v17 & 2) != 0 )
  {
    v19 = v18++;
    UsageLength = v18;
    UsageList[v19] = 1;
  }
  if ( (v17 & 1) != 0 )
  {
    v20 = v18++;
    UsageLength = v18;
    UsageList[v20] = 3;
  }
  if ( (v17 & 8) != 0 )
  {
    v21 = v18++;
    UsageLength = v18;
    UsageList[v21] = 5;
  }
  if ( v18 )
  {
    v15 = HidP_SetUsages(
            HidP_Output,
            8u,
            0,
            UsageList,
            &UsageLength,
            *(PHIDP_PREPARSED_DATA *)v3,
            *(PCHAR *)Pool2,
            *(unsigned __int16 *)(v3 + 14));
    if ( (int)(v15 + 0x80000000) < 0 || v15 == -1072627697 )
      goto LABEL_27;
LABEL_32:
    a3->IoStatus.Status = v15;
    goto LABEL_33;
  }
  UsageList[0] = 3;
  UsageLength = 1;
  v22 = HidP_UnsetUsages(
          HidP_Output,
          8u,
          0,
          UsageList,
          &UsageLength,
          *(PHIDP_PREPARSED_DATA *)v3,
          *(PCHAR *)Pool2,
          *(unsigned __int16 *)(v3 + 14));
  v15 = v22;
  if ( (int)(v22 + 0x80000000) >= 0 && v22 != -1072627697 )
    goto LABEL_32;
LABEL_27:
  CurrentStackLocation = a3->Tail.Overlay.CurrentStackLocation;
  *(_QWORD *)(Pool2 + 8) = a3->MdlAddress;
  v24 = a3->Tail.Overlay.CurrentStackLocation;
  a3->MdlAddress = v14;
  *(_OWORD *)&v24[-1].MajorFunction = *(_OWORD *)&v24->MajorFunction;
  *(_OWORD *)&v24[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v24->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&v24[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v24->Parameters.SetQuota + 6);
  v24[-1].FileObject = v24->FileObject;
  v24[-1].Control = 0;
  CurrentStackLocation[-1].MajorFunction = 14;
  CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 721507;
  CurrentStackLocation[-1].Parameters.Create.Options = *(unsigned __int16 *)(v3 + 14);
  CurrentStackLocation[-1].Parameters.Read.Length = 0;
  CurrentStackLocation[-1].Parameters.CreatePipe.Parameters = *(PNAMED_PIPE_CREATE_PARAMETERS *)Pool2;
  if ( IoSetCompletionRoutineEx(*(PDEVICE_OBJECT *)a1, a3, KbdHid_SetLedIndicatorsComplete, (PVOID)Pool2, 1u, 1u, 1u) < 0 )
  {
    v25 = a3->Tail.Overlay.CurrentStackLocation;
    v25[-1].CompletionRoutine = KbdHid_SetLedIndicatorsComplete;
    v25[-1].Context = (PVOID)Pool2;
    v25[-1].Control = -32;
  }
  return IofCallDriver(*(PDEVICE_OBJECT *)(a1 + 8), a3);
}

```

## disassembly

```asm
0x140003040  push    rbx
0x140003042  push    rbp
0x140003043  push    rsi
0x140003044  push    rdi
0x140003045  push    r12
0x140003047  push    r13
0x140003049  push    r14
0x14000304b  sub     rsp, 60h
0x14000304f  mov     rax, cs:__security_cookie
0x140003056  xor     rax, rsp
0x140003059  mov     [rsp+98h+var_48], rax
0x14000305e  mov     rbx, [rcx+70h]
0x140003062  mov     rdi, r8
0x140003065  mov     r13, rdx
0x140003068  mov     [rsp+98h+RemlockSize], 20h ; ' '; RemlockSize
0x140003070  mov     r14, rcx
0x140003073  lea     r8, File; File
0x14000307a  xor     r12d, r12d
0x14000307d  mov     rdx, rdi; Tag
0x140003080  mov     r9d, 1; Line
0x140003086  mov     [rsp+98h+UsageLength], r12d
0x14000308b  add     rcx, 98h; RemoveLock
0x140003092  call    cs:__imp_IoAcquireRemoveLockEx
0x140003099  nop     dword ptr [rax+rax+00h]
0x14000309e  mov     ebp, eax
0x1400030a0  test    eax, eax
0x1400030a2  jns     short loc_1400030BF
0x1400030a4  xor     edx, edx; PriorityBoost
0x1400030a6  mov     [rdi+30h], eax
0x1400030a9  mov     rcx, rdi; Irp
0x1400030ac  call    cs:__imp_IofCompleteRequest
0x1400030b3  nop     dword ptr [rax+rax+00h]
0x1400030b8  mov     eax, ebp
0x1400030ba  jmp     loc_140003385
0x1400030bf  mov     [rsp+98h+arg_8], r15
0x1400030c7  cmp     [r14+58h], r12b
0x1400030cb  jnz     short loc_14000311F
0x1400030cd  mov     ebx, 0C0000184h
0x1400030d2  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400030d9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400030e0  jz      short loc_140003158
0x1400030e2  mov     rax, [r14]
0x1400030e5  mov     r9d, 19h
0x1400030eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400030f2  mov     r8d, 3
0x1400030f8  mov     [rsp+98h+ReportLength], ebx
0x1400030fc  mov     dl, 2
0x1400030fe  mov     [rsp+98h+Report], rdi
0x140003103  mov     [rsp+98h+PreparsedData], rax
0x140003108  lea     rax, WPP_a3eb93ac5d7d3982e3cdea956b1ca812_Traceguids
0x14000310f  mov     rcx, [rcx+40h]
0x140003113  mov     qword ptr [rsp+98h+RemlockSize], rax
0x140003118  call    WPP_RECORDER_SF_qqd
0x14000311d  jmp     short loc_140003158
0x14000311f  cmp     r12w, [rbx+0Eh]
0x140003124  jnz     short loc_14000312F
0x140003126  mov     ebx, r12d
0x140003129  mov     [rdi+30h], r12d
0x14000312d  jmp     short loc_14000315B
0x14000312f  mov     edx, 10h
0x140003134  mov     ecx, 40h ; '@'
0x140003139  mov     r8d, 4864624Bh
0x14000313f  call    cs:__imp_ExAllocatePool2
0x140003146  nop     dword ptr [rax+rax+00h]
0x14000314b  mov     r15, rax
0x14000314e  test    rax, rax
0x140003151  jnz     short loc_140003171
0x140003153  mov     ebx, 0C000009Ah
0x140003158  mov     [rdi+30h], ebx
0x14000315b  xor     edx, edx; PriorityBoost
0x14000315d  mov     rcx, rdi; Irp
0x140003160  call    cs:__imp_IofCompleteRequest
0x140003167  nop     dword ptr [rax+rax+00h]
0x14000316c  jmp     loc_140003445
0x140003171  movzx   edx, word ptr [rbx+0Eh]
0x140003175  mov     ecx, 40h ; '@'
0x14000317a  mov     r8d, 4864624Bh
0x140003180  call    cs:__imp_ExAllocatePool2
0x140003187  nop     dword ptr [rax+rax+00h]
0x14000318c  mov     [r15], rax
0x14000318f  test    rax, rax
0x140003192  jnz     short loc_1400031A7
0x140003194  mov     ebx, 0C000009Ah
0x140003199  mov     rbp, r12
0x14000319c  mov     r12d, ebx
0x14000319f  mov     [rdi+30h], ebx
0x1400031a2  jmp     loc_1400033F6
0x1400031a7  movzx   edx, word ptr [rbx+0Eh]; Length
0x1400031ab  xor     r9d, r9d; ChargeQuota
0x1400031ae  xor     r8d, r8d; SecondaryBuffer
0x1400031b1  mov     qword ptr [rsp+98h+RemlockSize], r12; Irp
0x1400031b6  mov     rcx, rax; VirtualAddress
0x1400031b9  call    cs:__imp_IoAllocateMdl
0x1400031c0  nop     dword ptr [rax+rax+00h]
0x1400031c5  mov     rbp, rax
0x1400031c8  test    rax, rax
0x1400031cb  jnz     short loc_1400031DD
0x1400031cd  mov     ebx, 0C000009Ah
0x1400031d2  mov     r12d, ebx
0x1400031d5  mov     [rdi+30h], ebx
0x1400031d8  jmp     loc_1400033F6
0x1400031dd  mov     rcx, rbp; MemoryDescriptorList
0x1400031e0  call    cs:__imp_MmBuildMdlForNonPagedPool
0x1400031e7  nop     dword ptr [rax+rax+00h]
0x1400031ec  movzx   ecx, word ptr [r13+2]
0x1400031f1  test    cl, 4
0x1400031f4  jz      short loc_14000320E
0x1400031f6  mov     edx, [rsp+98h+UsageLength]
0x1400031fa  mov     r8d, 2
0x140003200  mov     [rsp+rdx*2+98h+UsageList], r8w
0x140003206  inc     edx
0x140003208  mov     [rsp+98h+UsageLength], edx
0x14000320c  jmp     short loc_140003212
0x14000320e  mov     edx, [rsp+98h+UsageLength]
0x140003212  mov     r10d, 1
0x140003218  test    cl, 2
0x14000321b  jz      short loc_14000322B
0x14000321d  mov     eax, edx
0x14000321f  inc     edx
0x140003221  mov     [rsp+98h+UsageLength], edx
0x140003225  mov     [rsp+rax*2+98h+UsageList], r10w
0x14000322b  mov     r8d, 3
0x140003231  test    cl, 1
0x140003234  jz      short loc_140003244
0x140003236  mov     eax, edx
0x140003238  inc     edx
0x14000323a  mov     [rsp+98h+UsageLength], edx
0x14000323e  mov     [rsp+rax*2+98h+UsageList], r8w
0x140003244  test    cl, 8
0x140003247  jz      short loc_14000325B
0x140003249  mov     eax, edx
0x14000324b  mov     ecx, 5
0x140003250  inc     edx
0x140003252  mov     [rsp+98h+UsageLength], edx
0x140003256  mov     [rsp+rax*2+98h+UsageList], cx
0x14000325b  test    edx, edx
0x14000325d  lea     r9, [rsp+98h+UsageList]; UsageList
0x140003262  mov     edx, 8; UsagePage
0x140003267  mov     ecx, r10d; ReportType
0x14000326a  jnz     loc_1400033A2
0x140003270  mov     [rsp+98h+UsageList], r8w
0x140003276  xor     r8d, r8d; LinkCollection
0x140003279  mov     [rsp+98h+UsageLength], r10d
0x14000327e  movzx   eax, word ptr [rbx+0Eh]
0x140003282  mov     [rsp+98h+ReportLength], eax; ReportLength
0x140003286  mov     rax, [r15]
0x140003289  mov     [rsp+98h+Report], rax; Report
0x14000328e  mov     rax, [rbx]
0x140003291  mov     [rsp+98h+PreparsedData], rax; PreparsedData
0x140003296  lea     rax, [rsp+98h+UsageLength]
0x14000329b  mov     qword ptr [rsp+98h+RemlockSize], rax; UsageLength
0x1400032a0  call    cs:__imp_HidP_UnsetUsages
0x1400032a7  nop     dword ptr [rax+rax+00h]
0x1400032ac  mov     edx, 80000000h
0x1400032b1  mov     r12d, eax
0x1400032b4  lea     ecx, [rax+rdx]
0x1400032b7  test    edx, ecx
0x1400032b9  jnz     short loc_1400032C6
0x1400032bb  cmp     eax, 0C011000Fh
0x1400032c0  jnz     loc_1400033F2
0x1400032c6  mov     rax, [rdi+8]
0x1400032ca  mov     r9, r15; Context
0x1400032cd  mov     rcx, [rdi+0B8h]
0x1400032d4  mov     rdx, rdi; Irp
0x1400032d7  mov     [r15+8], rax
0x1400032db  mov     rax, [rdi+0B8h]
0x1400032e2  mov     [rdi+8], rbp
0x1400032e6  mov     byte ptr [rsp+98h+Report], 1; InvokeOnCancel
0x1400032eb  mov     byte ptr [rsp+98h+PreparsedData], 1; InvokeOnError
0x1400032f0  movups  xmm0, xmmword ptr [rax]
0x1400032f3  mov     byte ptr [rsp+98h+RemlockSize], 1; InvokeOnSuccess
0x1400032f8  movups  xmmword ptr [rax-48h], xmm0
0x1400032fc  movups  xmm1, xmmword ptr [rax+10h]
0x140003300  movups  xmmword ptr [rax-38h], xmm1
0x140003304  movups  xmm0, xmmword ptr [rax+20h]
0x140003308  movups  xmmword ptr [rax-28h], xmm0
0x14000330c  movsd   xmm1, qword ptr [rax+30h]
0x140003311  movsd   qword ptr [rax-18h], xmm1
0x140003316  mov     byte ptr [rax-45h], 0
0x14000331a  mov     byte ptr [rcx-48h], 0Eh
0x14000331e  mov     dword ptr [rcx-30h], 0B0263h
0x140003325  movzx   eax, word ptr [rbx+0Eh]
0x140003329  lea     rbx, KbdHid_SetLedIndicatorsComplete
0x140003330  mov     [rcx-38h], eax
0x140003333  mov     r8, rbx; CompletionRoutine
0x140003336  mov     dword ptr [rcx-40h], 0
0x14000333d  mov     rax, [r15]
0x140003340  mov     [rcx-28h], rax
0x140003344  mov     rcx, [r14]; DeviceObject
0x140003347  call    cs:__imp_IoSetCompletionRoutineEx
0x14000334e  nop     dword ptr [rax+rax+00h]
0x140003353  test    eax, eax
0x140003355  jns     short loc_14000336A
0x140003357  mov     rax, [rdi+0B8h]
0x14000335e  mov     [rax-10h], rbx
0x140003362  mov     [rax-8], r15
0x140003366  mov     byte ptr [rax-45h], 0E0h
0x14000336a  mov     rcx, [r14+8]; DeviceObject
0x14000336e  mov     rdx, rdi; Irp
0x140003371  call    cs:__imp_IofCallDriver
0x140003378  nop     dword ptr [rax+rax+00h]
0x14000337d  mov     r15, [rsp+98h+arg_8]
0x140003385  mov     rcx, [rsp+98h+var_48]
0x14000338a  xor     rcx, rsp; StackCookie
0x14000338d  call    __security_check_cookie
0x140003392  add     rsp, 60h
0x140003396  pop     r14
0x140003398  pop     r13
0x14000339a  pop     r12
0x14000339c  pop     rdi
0x14000339d  pop     rsi
0x14000339e  pop     rbp
0x14000339f  pop     rbx
0x1400033a0  retn
0x1400033a2  movzx   eax, word ptr [rbx+0Eh]
0x1400033a6  xor     r8d, r8d; LinkCollection
0x1400033a9  mov     [rsp+98h+ReportLength], eax; ReportLength
0x1400033ad  mov     rax, [r15]
0x1400033b0  mov     [rsp+98h+Report], rax; Report
0x1400033b5  mov     rax, [rbx]
0x1400033b8  mov     [rsp+98h+PreparsedData], rax; PreparsedData
0x1400033bd  lea     rax, [rsp+98h+UsageLength]
0x1400033c2  mov     qword ptr [rsp+98h+RemlockSize], rax; UsageLength
0x1400033c7  call    cs:__imp_HidP_SetUsages
0x1400033ce  nop     dword ptr [rax+rax+00h]
0x1400033d3  mov     edx, 80000000h
0x1400033d8  mov     r12d, eax
0x1400033db  add     eax, edx
0x1400033dd  test    edx, eax
0x1400033df  jnz     loc_1400032C6
0x1400033e5  cmp     r12d, 0C011000Fh
0x1400033ec  jz      loc_1400032C6
0x1400033f2  mov     [rdi+30h], r12d
0x1400033f6  xor     edx, edx; PriorityBoost
0x1400033f8  mov     rcx, rdi; Irp
0x1400033fb  call    cs:__imp_IofCompleteRequest
0x140003402  nop     dword ptr [rax+rax+00h]
0x140003407  mov     rcx, [r15]; P
0x14000340a  mov     ebx, r12d
0x14000340d  test    rcx, rcx
0x140003410  jz      short loc_140003420
0x140003412  xor     edx, edx; Tag
0x140003414  call    cs:__imp_ExFreePoolWithTag
0x14000341b  nop     dword ptr [rax+rax+00h]
0x140003420  xor     edx, edx; Tag
0x140003422  mov     rcx, r15; P
0x140003425  call    cs:__imp_ExFreePoolWithTag
0x14000342c  nop     dword ptr [rax+rax+00h]
0x140003431  test    rbp, rbp
0x140003434  jz      short loc_140003445
0x140003436  mov     rcx, rbp; Mdl
0x140003439  call    cs:__imp_IoFreeMdl
0x140003440  nop     dword ptr [rax+rax+00h]
0x140003445  mov     r8d, 20h ; ' '; RemlockSize
0x14000344b  lea     rcx, [r14+98h]; RemoveLock
0x140003452  mov     rdx, rdi; Tag
0x140003455  call    cs:__imp_IoReleaseRemoveLockEx
0x14000345c  nop     dword ptr [rax+rax+00h]
0x140003461  mov     eax, ebx
0x140003463  jmp     loc_14000337D
```
