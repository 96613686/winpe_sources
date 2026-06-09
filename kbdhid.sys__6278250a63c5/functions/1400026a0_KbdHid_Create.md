# KbdHid_Create

- ea: `0x1400026a0`
- end: `0x140002d72`
- name: `KbdHid_Create`
- size: `1746`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001a00`
- `0x1400026a0`
- `0x140002d80`
- `0x140002eb0`
- `0x1400042d0`
- `0x1400052a0`
- `0x140005580`
- `0x140005a0c`
- `0x140005d88`
- `0x140006e30`
- `0x140007130`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14000280a`
- `ntoskrnl!IofCallDriver` at `0x14000280a`
- `ntoskrnl!IofCompleteRequest` at `0x14000288f`
- `ntoskrnl!IofCompleteRequest` at `0x14000291e`
- `ntoskrnl!IofCompleteRequest` at `0x14000288f`
- `ntoskrnl!IofCompleteRequest` at `0x14000291e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000282b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000282b`
- `ntoskrnl!KeSetEvent` at `0x140002d31`
- `ntoskrnl!KeSetEvent` at `0x140002d31`
- `ntoskrnl!KeInitializeEvent` at `0x1400027d8`
- `ntoskrnl!KeInitializeEvent` at `0x1400027d8`
- `ntoskrnl!KeResetEvent` at `0x140002ac5`
- `ntoskrnl!KeResetEvent` at `0x140002ac5`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400029a4`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400029a4`
- `ntoskrnl!ExReleaseFastMutex` at `0x140002863`
- `ntoskrnl!ExReleaseFastMutex` at `0x140002b2c`
- `ntoskrnl!ExReleaseFastMutex` at `0x140002cd4`
- `ntoskrnl!ExReleaseFastMutex` at `0x140002cfb`
- `ntoskrnl!ExReleaseFastMutex` at `0x140002863`
- `ntoskrnl!ExReleaseFastMutex` at `0x140002b2c`
- `ntoskrnl!ExReleaseFastMutex` at `0x140002cd4`
- `ntoskrnl!ExReleaseFastMutex` at `0x140002cfb`
- `ntoskrnl!ExAcquireFastMutex` at `0x140002786`
- `ntoskrnl!ExAcquireFastMutex` at `0x140002786`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400028ab`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x1400028ab`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000275d`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140002af8`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x14000275d`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140002af8`

## pseudocode

```c
__int64 __fastcall KbdHid_Create(__int64 a1, IRP *a2, int a3, int a4)
{
  int v6; // edx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  __int64 v8; // rbp
  int v9; // r14d
  USHORT ShareAccess; // ax
  PFILE_OBJECT FileObject; // rax
  NTSTATUS v12; // eax
  int v13; // edx
  NTSTATUS Status; // r14d
  int v15; // edx
  struct _IO_STACK_LOCATION *v16; // rax
  struct _IO_STACK_LOCATION *v17; // rax
  int v18; // r8d
  int v19; // r9d
  PFILE_OBJECT v20; // rdi
  int v21; // edx
  PDEVICE_OBJECT v23; // rcx
  int v24; // r9d
  int v25; // edx
  int v26; // r8d
  int v27; // r9d
  char v28; // al
  int v29; // eax
  int v30; // edx
  int v31; // r9d
  int RemlockSize; // [rsp+20h] [rbp-C8h]
  int RemlockSizea; // [rsp+20h] [rbp-C8h]
  char v34; // [rsp+60h] [rbp-88h]
  char v35; // [rsp+64h] [rbp-84h]
  UNICODE_STRING String2; // [rsp+68h] [rbp-80h] BYREF
  _KEVENT Event; // [rsp+78h] [rbp-70h] BYREF
  PFAST_MUTEX FastMutex; // [rsp+90h] [rbp-58h] BYREF
  wchar_t v39; // [rsp+98h] [rbp-50h]

  memset(&Event, 0, sizeof(Event));
  v6 = 10;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v6) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      1,
      10,
      (__int64)WPP_98d22518711f34f074bb80910c9ade48_Traceguids);
  }
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v8 = *(_QWORD *)(a1 + 64);
  v9 = *(_DWORD *)(CurrentStackLocation->Parameters.WMI.ProviderId + 16);
  ShareAccess = CurrentStackLocation->Parameters.Create.ShareAccess;
  v34 = ShareAccess;
  v35 = v9;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qqqDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      a3,
      a4,
      RemlockSize,
      a1,
      (char)a2,
      (char)CurrentStackLocation->FileObject,
      v9,
      ShareAccess);
  FileObject = CurrentStackLocation->FileObject;
  if ( FileObject && FileObject->FileName.Length )
  {
    v39 = aKbd[4];
    String2.Buffer = (PWSTR)&FastMutex;
    FastMutex = *(PFAST_MUTEX *)L"\\KBD";
    *(_QWORD *)&String2.Length = 655368;
    if ( !RtlEqualUnicodeString(&FileObject->FileName, &String2, 1u) )
    {
      Status = -1073741790;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        goto LABEL_15;
      v27 = 12;
      goto LABEL_23;
    }
    if ( (v9 & 1) != 0 )
    {
      Status = -1073741757;
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v27 = 13;
LABEL_23:
        WPP_RECORDER_SF_qqqd(
          WPP_GLOBAL_Control->DeviceExtension,
          v25,
          v26,
          v27,
          RemlockSize,
          a1,
          (char)a2,
          (char)CurrentStackLocation->FileObject,
          Status);
      }
LABEL_15:
      a2->IoStatus.Status = Status;
      a2->IoStatus.Information = 0;
      IofCompleteRequest(a2, 0);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v23 = WPP_GLOBAL_Control;
        if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
        {
          v24 = 21;
LABEL_52:
          LOBYTE(v21) = 5;
          WPP_RECORDER_SF_(v23->DeviceExtension, v21, 1, v24, (__int64)WPP_98d22518711f34f074bb80910c9ade48_Traceguids);
          return (unsigned int)Status;
        }
      }
      return (unsigned int)Status;
    }
  }
  v12 = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v8 + 152), a2, File, 1u, 0x20u);
  Status = v12;
  if ( v12 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v13) = 3;
      WPP_RECORDER_SF_qqd(
        WPP_GLOBAL_Control->DeviceExtension,
        v13,
        1,
        14,
        (__int64)WPP_98d22518711f34f074bb80910c9ade48_Traceguids,
        a1,
        (char)a2,
        v12);
    }
    goto LABEL_15;
  }
  FastMutex = (PFAST_MUTEX)(v8 + 184);
  ExAcquireFastMutex((PFAST_MUTEX)(v8 + 184));
  if ( !*(_QWORD *)(v8 + 144) )
  {
    Status = -1073741823;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
LABEL_45:
      ExReleaseFastMutex(FastMutex);
      goto LABEL_11;
    }
    v31 = 15;
LABEL_44:
    LOBYTE(v15) = 2;
    WPP_RECORDER_SF_qqd(
      WPP_GLOBAL_Control->DeviceExtension,
      v15,
      1,
      v31,
      (__int64)WPP_98d22518711f34f074bb80910c9ade48_Traceguids,
      a1,
      (char)a2,
      Status);
    goto LABEL_45;
  }
  v16 = a2->Tail.Overlay.CurrentStackLocation;
  *(_OWORD *)&v16[-1].MajorFunction = *(_OWORD *)&v16->MajorFunction;
  *(_OWORD *)&v16[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v16->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&v16[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v16->Parameters.SetQuota + 6);
  v16[-1].FileObject = v16->FileObject;
  v16[-1].Control = 0;
  KeInitializeEvent(&Event, NotificationEvent, 0);
  v17 = a2->Tail.Overlay.CurrentStackLocation;
  v17[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&KbdHid_CreateComplete;
  v17[-1].Context = &Event;
  v17[-1].Control = -32;
  Status = IofCallDriver(*(PDEVICE_OBJECT *)(v8 + 8), a2);
  KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
  if ( Status < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
LABEL_9:
      v20 = 0;
      goto LABEL_10;
    }
    v31 = 18;
    goto LABEL_44;
  }
  Status = a2->IoStatus.Status;
  v28 = _InterlockedIncrement((volatile signed __int32 *)(v8 + 28));
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qqdl(
      WPP_GLOBAL_Control->DeviceExtension,
      (unsigned int)&WPP_RECORDER_INITIALIZED,
      v18,
      v19,
      RemlockSizea,
      a1,
      (char)a2,
      Status,
      v28);
  if ( *(_QWORD *)(v8 + 128) || (*(_DWORD *)(CurrentStackLocation->Parameters.WMI.ProviderId + 16) & 1) == 0 )
    goto LABEL_9;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_qqqDDl(
      WPP_GLOBAL_Control->DeviceExtension,
      (unsigned int)&WPP_RECORDER_INITIALIZED,
      v18,
      v19,
      RemlockSizea,
      a1,
      (char)a2,
      (char)CurrentStackLocation->FileObject,
      v35,
      v34,
      *(_DWORD *)(v8 + 28));
  v20 = CurrentStackLocation->FileObject;
  *(_QWORD *)(v8 + 128) = v20;
  KeResetEvent((PRKEVENT)(v8 + 40));
  _InterlockedExchange((volatile __int32 *)(v8 + 32), 2);
  IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v8 + 152), *(PVOID *)(v8 + 104), File, 1u, 0x20u);
  *(_DWORD *)(*(_QWORD *)(v8 + 104) + 48LL) = 0;
  v29 = KbdHid_StartRead((PVOID)v8);
  Status = v29;
  if ( v29 != 259 )
  {
    if ( v29 < 0 )
    {
      *(_QWORD *)(v8 + 128) = 0;
      ExReleaseFastMutex((PFAST_MUTEX)(v8 + 184));
      goto LABEL_11;
    }
LABEL_10:
    ExReleaseFastMutex((PFAST_MUTEX)(v8 + 184));
    if ( Status < 0 )
      goto LABEL_11;
    goto LABEL_34;
  }
  Status = 0;
  ExReleaseFastMutex((PFAST_MUTEX)(v8 + 184));
LABEL_34:
  if ( v20 && !_InterlockedCompareExchange((volatile signed __int32 *)(v8 + 316), 1, 0) )
  {
    Status = KbdHid_QueryExtendedAttributes(v8);
    if ( Status < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v30) = 3;
        WPP_RECORDER_SF_qd(
          WPP_GLOBAL_Control->DeviceExtension,
          v30,
          1,
          19,
          (__int64)WPP_98d22518711f34f074bb80910c9ade48_Traceguids,
          a1,
          Status);
      }
      Status = 0;
    }
    _InterlockedExchange((volatile __int32 *)(v8 + 316), 2);
    KeSetEvent((PRKEVENT)(v8 + 320), 0, 0);
  }
LABEL_11:
  a2->IoStatus.Status = Status;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v8 + 152), a2, 0x20u);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v23 = WPP_GLOBAL_Control;
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      v24 = 20;
      goto LABEL_52;
    }
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x1400026a0  mov     [rsp+arg_10], rbx
0x1400026a5  push    rbp
0x1400026a6  push    rsi
0x1400026a7  push    rdi
0x1400026a8  push    r12
0x1400026aa  push    r13
0x1400026ac  push    r14
0x1400026ae  push    r15
0x1400026b0  sub     rsp, 0B0h
0x1400026b7  mov     rax, cs:__security_cookie
0x1400026be  xor     rax, rsp
0x1400026c1  mov     [rsp+0E8h+var_48], rax
0x1400026c9  xorps   xmm0, xmm0
0x1400026cc  xor     eax, eax
0x1400026ce  movups  xmmword ptr [rsp+0E8h+Event.Header], xmm0
0x1400026d3  mov     [rsp+0E8h+Event.Header.WaitListHead.Blink], rax
0x1400026db  mov     rbx, rdx
0x1400026de  mov     r13, rcx
0x1400026e1  lea     r12, WPP_RECORDER_INITIALIZED
0x1400026e8  mov     edx, 0Ah
0x1400026ed  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x1400026f4  lea     rax, WPP_98d22518711f34f074bb80910c9ade48_Traceguids
0x1400026fb  mov     r15d, 1
0x140002701  jnz     loc_140002A07
0x140002707  mov     rsi, [rbx+0B8h]
0x14000270e  mov     rbp, [r13+40h]
0x140002712  mov     rax, [rsi+8]
0x140002716  mov     r14d, [rax+10h]
0x14000271a  movzx   eax, word ptr [rsi+1Ah]
0x14000271e  mov     [rsp+0E8h+var_88], eax
0x140002722  mov     [rsp+0E8h+var_84], r14d
0x140002727  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x14000272e  jnz     loc_140002BCF
0x140002734  mov     rax, [rsi+30h]
0x140002738  test    rax, rax
0x14000273b  jnz     loc_140002956
0x140002741  mov     r9d, r15d; Line
0x140002744  mov     [rsp+0E8h+RemlockSize], 20h ; ' '; RemlockSize
0x14000274c  lea     r8, File; File
0x140002753  mov     rdx, rbx; Tag
0x140002756  lea     rcx, [rbp+98h]; RemoveLock
0x14000275d  call    cs:__imp_IoAcquireRemoveLockEx
0x140002764  nop     dword ptr [rax+rax+00h]
0x140002769  mov     r14d, eax
0x14000276c  test    eax, eax
0x14000276e  js      loc_1400028FA
0x140002774  lea     rax, [rbp+0B8h]
0x14000277b  mov     rcx, rax; FastMutex
0x14000277e  mov     [rsp+0E8h+FastMutex], rax
0x140002786  call    cs:__imp_ExAcquireFastMutex
0x14000278d  nop     dword ptr [rax+rax+00h]
0x140002792  xor     r12d, r12d
0x140002795  cmp     [rbp+90h], r12
0x14000279c  jz      loc_140002C69
0x1400027a2  mov     rax, [rbx+0B8h]
0x1400027a9  lea     rcx, [rsp+0E8h+Event]; Event
0x1400027ae  xor     r8d, r8d; State
0x1400027b1  xor     edx, edx; Type
0x1400027b3  movups  xmm0, xmmword ptr [rax]
0x1400027b6  movups  xmmword ptr [rax-48h], xmm0
0x1400027ba  movups  xmm1, xmmword ptr [rax+10h]
0x1400027be  movups  xmmword ptr [rax-38h], xmm1
0x1400027c2  movups  xmm0, xmmword ptr [rax+20h]
0x1400027c6  movups  xmmword ptr [rax-28h], xmm0
0x1400027ca  movsd   xmm1, qword ptr [rax+30h]
0x1400027cf  movsd   qword ptr [rax-18h], xmm1
0x1400027d4  mov     [rax-45h], r12b
0x1400027d8  call    cs:__imp_KeInitializeEvent
0x1400027df  nop     dword ptr [rax+rax+00h]
0x1400027e4  mov     rax, [rbx+0B8h]
0x1400027eb  lea     rcx, KbdHid_CreateComplete
0x1400027f2  mov     rdx, rbx; Irp
0x1400027f5  mov     [rax-10h], rcx
0x1400027f9  lea     rcx, [rsp+0E8h+Event]
0x1400027fe  mov     [rax-8], rcx
0x140002802  mov     byte ptr [rax-45h], 0E0h
0x140002806  mov     rcx, [rbp+8]; DeviceObject
0x14000280a  call    cs:__imp_IofCallDriver
0x140002811  nop     dword ptr [rax+rax+00h]
0x140002816  xor     r9d, r9d; Alertable
0x140002819  mov     qword ptr [rsp+0E8h+RemlockSize], r12; Timeout
0x14000281e  xor     r8d, r8d; WaitMode
0x140002821  lea     rcx, [rsp+0E8h+Event]; Object
0x140002826  xor     edx, edx; WaitReason
0x140002828  mov     r14d, eax
0x14000282b  call    cs:__imp_KeWaitForSingleObject
0x140002832  nop     dword ptr [rax+rax+00h]
0x140002837  test    r14d, r14d
0x14000283a  jns     loc_140002A34
0x140002840  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140002847  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14000284e  jnz     loc_140002C8A
0x140002854  mov     rdi, r12
0x140002857  mov     esi, 2
0x14000285c  lea     rcx, [rbp+0B8h]; FastMutex
0x140002863  call    cs:__imp_ExReleaseFastMutex
0x14000286a  nop     dword ptr [rax+rax+00h]
0x14000286f  test    r14d, r14d
0x140002872  jns     loc_140002B38
0x140002878  mov     edi, r15d
0x14000287b  lea     r13, WPP_98d22518711f34f074bb80910c9ade48_Traceguids
0x140002882  xor     edx, edx; PriorityBoost
0x140002884  mov     [rbx+30h], r14d
0x140002888  mov     rcx, rbx; Irp
0x14000288b  mov     [rbx+38h], r12
0x14000288f  call    cs:__imp_IofCompleteRequest
0x140002896  nop     dword ptr [rax+rax+00h]
0x14000289b  mov     r8d, 20h ; ' '; RemlockSize
0x1400028a1  lea     rcx, [rbp+98h]; RemoveLock
0x1400028a8  mov     rdx, rbx; Tag
0x1400028ab  call    cs:__imp_IoReleaseRemoveLockEx
0x1400028b2  nop     dword ptr [rax+rax+00h]
0x1400028b7  lea     rax, WPP_RECORDER_INITIALIZED
0x1400028be  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400028c5  jnz     loc_140002D42
0x1400028cb  mov     eax, r14d
0x1400028ce  mov     rcx, [rsp+0E8h+var_48]
0x1400028d6  xor     rcx, rsp; StackCookie
0x1400028d9  call    __security_check_cookie
0x1400028de  mov     rbx, [rsp+0E8h+arg_10]
0x1400028e6  add     rsp, 0B0h
0x1400028ed  pop     r15
0x1400028ef  pop     r14
0x1400028f1  pop     r13
0x1400028f3  pop     r12
0x1400028f5  pop     rdi
0x1400028f6  pop     rsi
0x1400028f7  pop     rbp
0x1400028f8  retn
0x1400028fa  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140002901  jnz     loc_140002C2F
0x140002907  lea     r13, WPP_98d22518711f34f074bb80910c9ade48_Traceguids
0x14000290e  xor     r12d, r12d
0x140002911  mov     [rbx+30h], r14d
0x140002915  xor     edx, edx; PriorityBoost
0x140002917  mov     [rbx+38h], r12
0x14000291b  mov     rcx, rbx; Irp
0x14000291e  call    cs:__imp_IofCompleteRequest
0x140002925  nop     dword ptr [rax+rax+00h]
0x14000292a  lea     rax, WPP_RECORDER_INITIALIZED
0x140002931  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140002938  jz      short loc_1400028CB
0x14000293a  mov     rcx, cs:WPP_GLOBAL_Control
0x140002941  cmp     [rcx+48h], r12w
0x140002946  jz      short loc_1400028CB
0x140002948  mov     r9d, 15h
0x14000294e  mov     r8d, r15d
0x140002951  jmp     loc_140002D5D
0x140002956  cmp     word ptr [rax+58h], 0
0x14000295b  lea     rcx, [rax+58h]; String1
0x14000295f  jz      loc_140002741
0x140002965  movzx   eax, word ptr cs:aKbd+8; ""
0x14000296c  lea     rdx, [rsp+0E8h+String2]; String2
0x140002971  movsd   xmm0, qword ptr cs:aKbd; "\\KBD"
0x140002979  movzx   r8d, r15b; CaseInSensitive
0x14000297d  mov     [rsp+0E8h+var_50], ax
0x140002985  lea     rax, [rsp+0E8h+FastMutex]
0x14000298d  mov     [rsp+0E8h+String2.Buffer], rax
0x140002992  movsd   [rsp+0E8h+FastMutex], xmm0
0x14000299b  mov     qword ptr [rsp+0E8h+String2.Length], 0A0008h
0x1400029a4  call    cs:__imp_RtlEqualUnicodeString
0x1400029ab  nop     dword ptr [rax+rax+00h]
0x1400029b0  test    al, al
0x1400029b2  jz      loc_140002BB1
0x1400029b8  test    r15b, r14b
0x1400029bb  jz      loc_140002741
0x1400029c1  mov     r14d, 0C0000043h
0x1400029c7  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x1400029ce  jz      loc_140002907
0x1400029d4  mov     r9d, 0Dh
0x1400029da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400029e1  mov     rax, [rsi+30h]
0x1400029e5  mov     [rsp+0E8h+var_A8], r14d
0x1400029ea  mov     [rsp+0E8h+var_B0], rax
0x1400029ef  mov     rcx, [rcx+40h]
0x1400029f3  mov     [rsp+0E8h+var_B8], rbx
0x1400029f8  mov     [rsp+0E8h+var_C0], r13
0x1400029fd  call    WPP_RECORDER_SF_qqqd
0x140002a02  jmp     loc_140002907
0x140002a07  mov     rcx, cs:WPP_GLOBAL_Control
0x140002a0e  cmp     word ptr [rcx+48h], 0
0x140002a13  jz      loc_140002707
0x140002a19  mov     rcx, [rcx+40h]
0x140002a1d  mov     r9d, edx
0x140002a20  mov     dl, 5
0x140002a22  mov     qword ptr [rsp+0E8h+RemlockSize], rax
0x140002a27  mov     r8d, r15d
0x140002a2a  call    WPP_RECORDER_SF_
0x140002a2f  jmp     loc_140002707
0x140002a34  mov     r14d, [rbx+30h]
0x140002a38  mov     eax, r15d
0x140002a3b  lock xadd [rbp+1Ch], eax
0x140002a40  inc     eax
0x140002a42  lea     rdx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140002a49  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x140002a50  jnz     loc_140002C00
0x140002a56  cmp     [rbp+80h], r12
0x140002a5d  jnz     loc_140002854
0x140002a63  mov     rax, [rsi+8]
0x140002a67  mov     ecx, [rax+10h]
0x140002a6a  test    r15b, cl
0x140002a6d  jz      loc_140002854
0x140002a73  cmp     cs:WPP_RECORDER_INITIALIZED, rdx; __annotation("TMF:",
0x140002a7a  jz      short loc_140002AB6
0x140002a7c  mov     eax, [rbp+1Ch]
0x140002a7f  mov     rcx, cs:WPP_GLOBAL_Control
0x140002a86  mov     [rsp+0E8h+var_98], eax
0x140002a8a  mov     eax, [rsp+0E8h+var_88]
0x140002a8e  mov     [rsp+0E8h+var_A0], eax
0x140002a92  mov     eax, [rsp+0E8h+var_84]
0x140002a96  mov     rcx, [rcx+40h]
0x140002a9a  mov     [rsp+0E8h+var_A8], eax
0x140002a9e  mov     rax, [rsi+30h]
0x140002aa2  mov     [rsp+0E8h+var_B0], rax
0x140002aa7  mov     [rsp+0E8h+var_B8], rbx
0x140002aac  mov     [rsp+0E8h+var_C0], r13
0x140002ab1  call    WPP_RECORDER_SF_qqqDDl
0x140002ab6  mov     rdi, [rsi+30h]
0x140002aba  lea     rcx, [rbp+28h]; Event
0x140002abe  mov     [rbp+80h], rdi
0x140002ac5  call    cs:__imp_KeResetEvent
0x140002acc  nop     dword ptr [rax+rax+00h]
0x140002ad1  mov     esi, 2
0x140002ad6  mov     [rsp+0E8h+RemlockSize], 20h ; ' '; RemlockSize
0x140002ade  mov     eax, esi
0x140002ae0  lea     r8, File; File
0x140002ae7  xchg    eax, [rbp+20h]
0x140002aea  mov     rdx, [rbp+68h]; Tag
0x140002aee  lea     rcx, [rbp+98h]; RemoveLock
0x140002af5  mov     r9d, r15d; Line
0x140002af8  call    cs:__imp_IoAcquireRemoveLockEx
0x140002aff  nop     dword ptr [rax+rax+00h]
0x140002b04  mov     rax, [rbp+68h]
0x140002b08  mov     rcx, rbp; Context
0x140002b0b  mov     [rax+30h], r12d
0x140002b0f  call    KbdHid_StartRead
0x140002b14  mov     r14d, eax
0x140002b17  cmp     eax, 103h
0x140002b1c  jnz     loc_140002CE5
0x140002b22  lea     rcx, [rbp+0B8h]; FastMutex
0x140002b29  mov     r14d, r12d
0x140002b2c  call    cs:__imp_ExReleaseFastMutex
0x140002b33  nop     dword ptr [rax+rax+00h]
0x140002b38  test    rdi, rdi
0x140002b3b  mov     edi, r15d
0x140002b3e  jz      loc_14000287B
0x140002b44  xor     eax, eax
0x140002b46  lock cmpxchg [rbp+13Ch], edi
0x140002b4e  jnz     loc_14000287B
0x140002b54  mov     rcx, rbp
0x140002b57  call    KbdHid_QueryExtendedAttributes
0x140002b5c  mov     r14d, eax
0x140002b5f  test    eax, eax
0x140002b61  jns     loc_140002D18
0x140002b67  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140002b6e  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140002b75  jz      loc_140002D0C
0x140002b7b  mov     rcx, cs:WPP_GLOBAL_Control
0x140002b82  mov     r9d, 13h
0x140002b88  mov     dword ptr [rsp+0E8h+var_B8], r14d
0x140002b8d  mov     r8d, r15d
0x140002b90  mov     [rsp+0E8h+var_C0], r13
0x140002b95  mov     dl, 3
0x140002b97  lea     r13, WPP_98d22518711f34f074bb80910c9ade48_Traceguids
0x140002b9e  mov     rcx, [rcx+40h]
0x140002ba2  mov     qword ptr [rsp+0E8h+RemlockSize], r13
0x140002ba7  call    WPP_RECORDER_SF_qd
0x140002bac  jmp     loc_140002D13
0x140002bb1  mov     r14d, 0C0000022h
0x140002bb7  cmp     cs:WPP_RECORDER_INITIALIZED, r12; __annotation("TMF:",
0x140002bbe  jz      loc_140002907
0x140002bc4  mov     r9d, 0Ch
0x140002bca  jmp     loc_1400029DA
0x140002bcf  mov     rcx, cs:WPP_GLOBAL_Control
0x140002bd6  mov     [rsp+0E8h+var_A0], eax
0x140002bda  mov     rax, [rsi+30h]
0x140002bde  mov     [rsp+0E8h+var_A8], r14d
0x140002be3  mov     rcx, [rcx+40h]
0x140002be7  mov     [rsp+0E8h+var_B0], rax
0x140002bec  mov     [rsp+0E8h+var_B8], rbx
0x140002bf1  mov     [rsp+0E8h+var_C0], r13
0x140002bf6  call    WPP_RECORDER_SF_qqqDD
0x140002bfb  jmp     loc_140002734
0x140002c00  mov     rcx, cs:WPP_GLOBAL_Control
0x140002c07  mov     [rsp+0E8h+var_A8], eax
0x140002c0b  mov     dword ptr [rsp+0E8h+var_B0], r14d
0x140002c10  mov     [rsp+0E8h+var_B8], rbx
0x140002c15  mov     rcx, [rcx+40h]
0x140002c19  mov     [rsp+0E8h+var_C0], r13
0x140002c1e  call    WPP_RECORDER_SF_qqdl
0x140002c23  lea     rdx, WPP_RECORDER_INITIALIZED
0x140002c2a  jmp     loc_140002A56
0x140002c2f  mov     rcx, cs:WPP_GLOBAL_Control
0x140002c36  mov     r9d, 0Eh
0x140002c3c  mov     dword ptr [rsp+0E8h+var_B0], eax
0x140002c40  mov     r8d, r15d
0x140002c43  mov     [rsp+0E8h+var_B8], rbx
0x140002c48  mov     dl, 3
0x140002c4a  mov     [rsp+0E8h+var_C0], r13
0x140002c4f  lea     r13, WPP_98d22518711f34f074bb80910c9ade48_Traceguids
  ... truncated ...
```
