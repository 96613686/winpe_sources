# MouHid_Create

- ea: `0x140003fd0`
- end: `0x140004489`
- name: `MouHid_Create`
- size: `1209`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001464`
- `0x140002d28`
- `0x14000383c`
- `0x140003fd0`
- `0x1400047a0`
- `0x1400048c0`
- `0x140004a0c`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400043f0`
- `ntoskrnl!KeSetEvent` at `0x1400043f0`
- `ntoskrnl!KeInitializeEvent` at `0x1400041ba`
- `ntoskrnl!KeInitializeEvent` at `0x1400041ba`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000420c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000420c`
- `ntoskrnl!KeResetEvent` at `0x1400042b3`
- `ntoskrnl!KeResetEvent` at `0x140004358`
- `ntoskrnl!KeResetEvent` at `0x1400042b3`
- `ntoskrnl!KeResetEvent` at `0x140004358`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000431e`
- `ntoskrnl!ExReleaseFastMutex` at `0x14000431e`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000411b`
- `ntoskrnl!ExAcquireFastMutex` at `0x14000411b`
- `ntoskrnl!IofCompleteRequest` at `0x1400040cc`
- `ntoskrnl!IofCompleteRequest` at `0x140004410`
- `ntoskrnl!IofCompleteRequest` at `0x1400040cc`
- `ntoskrnl!IofCompleteRequest` at `0x140004410`
- `ntoskrnl!IofCallDriver` at `0x1400041ec`
- `ntoskrnl!IofCallDriver` at `0x1400041ec`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140004428`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x140004428`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400040a7`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400042e0`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400040a7`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x1400042e0`

## pseudocode

```c
__int64 __fastcall MouHid_Create(__int64 a1, IRP *a2, int a3, int a4)
{
  _UNKNOWN **v6; // rdx
  PFILE_OBJECT FileObject; // r15
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbp
  NTSTATUS Status; // esi
  __int64 v10; // rbx
  int v11; // edx
  PDEVICE_OBJECT v12; // rcx
  int v13; // r9d
  int v14; // edx
  struct _IO_STACK_LOCATION *v15; // rax
  struct _IO_STACK_LOCATION *v16; // rax
  int v17; // r9d
  int v18; // edx
  USHORT ShareAccess; // ax
  char v20; // cl
  int v21; // eax
  int v22; // edx
  int RemlockSize; // [rsp+20h] [rbp-A8h]
  int RemlockSizea; // [rsp+20h] [rbp-A8h]
  char v26; // [rsp+38h] [rbp-90h]
  struct _KEVENT Event; // [rsp+60h] [rbp-68h] BYREF

  memset(&Event, 0, sizeof(Event));
  v6 = &WPP_RECORDER_INITIALIZED;
  FileObject = 0;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v6) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v6,
      1,
      14,
      (__int64)WPP_bce545a1de1235e2be96703916423b99_Traceguids);
  }
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  if ( CurrentStackLocation->FileObject->FileName.Length )
  {
    Status = -1073741790;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_qqqd(
        WPP_GLOBAL_Control->DeviceExtension,
        (unsigned int)&WPP_RECORDER_INITIALIZED,
        a3,
        a4,
        RemlockSize,
        a1,
        (char)a2,
        (char)CurrentStackLocation->FileObject);
LABEL_8:
    a2->IoStatus.Status = Status;
    a2->IoStatus.Information = 0;
    IofCompleteRequest(a2, 0);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v12 = WPP_GLOBAL_Control;
      if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        v13 = 20;
LABEL_34:
        LOBYTE(v11) = 5;
        WPP_RECORDER_SF_(v12->DeviceExtension, v11, 1, v13, (__int64)WPP_bce545a1de1235e2be96703916423b99_Traceguids);
        return (unsigned int)Status;
      }
    }
    return (unsigned int)Status;
  }
  v10 = *(_QWORD *)(a1 + 64);
  Status = IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v10 + 240), a2, File, 1u, 0x20u);
  if ( Status < 0 )
    goto LABEL_8;
  ExAcquireFastMutex((PFAST_MUTEX)(v10 + 272));
  if ( *(_QWORD *)(v10 + 232) )
  {
    v15 = a2->Tail.Overlay.CurrentStackLocation;
    *(_OWORD *)&v15[-1].MajorFunction = *(_OWORD *)&v15->MajorFunction;
    *(_OWORD *)&v15[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v15->Parameters.NotifyDirectoryEx.CompletionFilter;
    *(_OWORD *)(&v15[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v15->Parameters.SetQuota + 6);
    v15[-1].FileObject = v15->FileObject;
    v15[-1].Control = 0;
    KeInitializeEvent(&Event, NotificationEvent, 0);
    v16 = a2->Tail.Overlay.CurrentStackLocation;
    v16[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&MouHid_CreateComplete;
    v16[-1].Context = &Event;
    v16[-1].Control = -32;
    Status = IofCallDriver(*(PDEVICE_OBJECT *)(v10 + 8), a2);
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    if ( Status >= 0 )
    {
      Status = a2->IoStatus.Status;
      if ( Status >= 0 && !*(_QWORD *)(v10 + 128) )
      {
        v18 = *(_DWORD *)(CurrentStackLocation->Parameters.WMI.ProviderId + 16);
        if ( (v18 & 1) != 0 )
        {
          ShareAccess = CurrentStackLocation->Parameters.Create.ShareAccess;
          v20 = _InterlockedIncrement((volatile signed __int32 *)(v10 + 24));
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_qqqDDl(
              WPP_GLOBAL_Control->DeviceExtension,
              v18,
              (unsigned int)&WPP_RECORDER_INITIALIZED,
              v17,
              RemlockSizea,
              a1,
              (char)a2,
              (char)CurrentStackLocation->FileObject,
              v18,
              ShareAccess,
              v20);
          FileObject = CurrentStackLocation->FileObject;
          *(_QWORD *)(v10 + 128) = FileObject;
          _InterlockedExchange((volatile __int32 *)(v10 + 136), 1);
          KeResetEvent((PRKEVENT)(v10 + 144));
          _InterlockedExchange((volatile __int32 *)(v10 + 28), 2);
          IoAcquireRemoveLockEx((PIO_REMOVE_LOCK)(v10 + 240), *(PVOID *)(v10 + 112), File, 1u, 0x20u);
          *(_DWORD *)(*(_QWORD *)(v10 + 112) + 48LL) = 0;
          v21 = MouHid_StartRead(v10);
          Status = v21;
          if ( v21 == 259 )
          {
            Status = 0;
          }
          else if ( v21 < 0 )
          {
            *(_QWORD *)(v10 + 128) = 0;
          }
        }
      }
    }
  }
  else
  {
    Status = -1073741823;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v14) = 2;
      WPP_RECORDER_SF_qqd(
        WPP_GLOBAL_Control->DeviceExtension,
        v14,
        1,
        16,
        (__int64)WPP_bce545a1de1235e2be96703916423b99_Traceguids,
        a1,
        (char)a2,
        1);
    }
  }
  ExReleaseFastMutex((PFAST_MUTEX)(v10 + 272));
  if ( Status >= 0 && FileObject && !_InterlockedCompareExchange((volatile signed __int32 *)(v10 + 56), 0, 0) )
  {
    KeResetEvent((PRKEVENT)(v10 + 192));
    if ( _InterlockedCompareExchange((volatile signed __int32 *)(v10 + 136), 2, 1) == 1 )
    {
      v22 = MouHid_SetResolutionMultipliers(v10);
      _InterlockedExchange((volatile __int32 *)(v10 + 56), (v22 != -1073741637) + 1);
      _InterlockedCompareExchange((volatile signed __int32 *)(v10 + 136), 1, 2);
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v26 = v22;
        LOBYTE(v22) = 4;
        WPP_RECORDER_SF_qqd(
          WPP_GLOBAL_Control->DeviceExtension,
          v22,
          1,
          18,
          (__int64)WPP_bce545a1de1235e2be96703916423b99_Traceguids,
          a1,
          (char)a2,
          v26);
      }
    }
    KeSetEvent((PRKEVENT)(v10 + 192), 0, 0);
  }
  a2->IoStatus.Status = Status;
  a2->IoStatus.Information = 0;
  IofCompleteRequest(a2, 0);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(v10 + 240), a2, 0x20u);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v12 = WPP_GLOBAL_Control;
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      v13 = 19;
      goto LABEL_34;
    }
  }
  return (unsigned int)Status;
}

```

## disassembly

```asm
0x140003fd0  push    rbx
0x140003fd2  push    rbp
0x140003fd3  push    rsi
0x140003fd4  push    rdi
0x140003fd5  push    r12
0x140003fd7  push    r13
0x140003fd9  push    r14
0x140003fdb  push    r15
0x140003fdd  sub     rsp, 88h
0x140003fe4  xorps   xmm0, xmm0
0x140003fe7  xor     eax, eax
0x140003fe9  movups  xmmword ptr [rsp+0C8h+Event.Header], xmm0
0x140003fee  mov     [rsp+0C8h+Event.Header.WaitListHead.Blink], rax
0x140003ff3  mov     rdi, rdx
0x140003ff6  mov     r14, rcx
0x140003ff9  lea     rdx, WPP_RECORDER_INITIALIZED
0x140004000  xor     r15d, r15d
0x140004003  cmp     cs:WPP_RECORDER_INITIALIZED, rdx
0x14000400a  lea     rbx, WPP_bce545a1de1235e2be96703916423b99_Traceguids
0x140004011  lea     r12d, [rax+1]
0x140004015  jz      short loc_140004043
0x140004017  mov     rcx, cs:WPP_GLOBAL_Control
0x14000401e  cmp     [rcx+48h], r15w
0x140004023  jz      short loc_140004043
0x140004025  mov     rcx, [rcx+40h]
0x140004029  lea     r9d, [rax+0Eh]
0x14000402d  mov     r8d, r12d
0x140004030  mov     qword ptr [rsp+0C8h+RemlockSize], rbx
0x140004035  mov     dl, 5
0x140004037  call    WPP_RECORDER_SF_
0x14000403c  lea     rdx, WPP_RECORDER_INITIALIZED
0x140004043  mov     rbp, [rdi+0B8h]
0x14000404a  mov     rcx, [rbp+30h]
0x14000404e  cmp     r15w, [rcx+58h]
0x140004053  jz      short loc_140004084
0x140004055  mov     esi, 0C0000022h
0x14000405a  cmp     cs:WPP_RECORDER_INITIALIZED, rdx; __annotation("TMF:",
0x140004061  jz      short loc_1400040C0
0x140004063  mov     [rsp+0C8h+var_90], rcx
0x140004068  mov     rcx, cs:WPP_GLOBAL_Control
0x14000406f  mov     [rsp+0C8h+var_98], rdi
0x140004074  mov     [rsp+0C8h+var_A0], r14
0x140004079  mov     rcx, [rcx+40h]
0x14000407d  call    WPP_RECORDER_SF_qqqd
0x140004082  jmp     short loc_1400040C0
0x140004084  mov     rbx, [r14+40h]
0x140004088  lea     r8, File; File
0x14000408f  mov     r9d, r12d; Line
0x140004092  mov     [rsp+0C8h+RemlockSize], 20h ; ' '; RemlockSize
0x14000409a  mov     rdx, rdi; Tag
0x14000409d  lea     r13, [rbx+0F0h]
0x1400040a4  mov     rcx, r13; RemoveLock
0x1400040a7  call    cs:__imp_IoAcquireRemoveLockEx
0x1400040ae  nop     dword ptr [rax+rax+00h]
0x1400040b3  mov     esi, eax
0x1400040b5  test    eax, eax
0x1400040b7  jns     short loc_140004111
0x1400040b9  lea     rbx, WPP_bce545a1de1235e2be96703916423b99_Traceguids
0x1400040c0  xor     edx, edx; PriorityBoost
0x1400040c2  mov     [rdi+30h], esi
0x1400040c5  mov     rcx, rdi; Irp
0x1400040c8  mov     [rdi+38h], r15
0x1400040cc  call    cs:__imp_IofCompleteRequest
0x1400040d3  nop     dword ptr [rax+rax+00h]
0x1400040d8  lea     r8, WPP_RECORDER_INITIALIZED
0x1400040df  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x1400040e6  jz      loc_140004472
0x1400040ec  mov     rcx, cs:WPP_GLOBAL_Control
0x1400040f3  cmp     [rcx+48h], r15w
0x1400040f8  jz      loc_140004472
0x1400040fe  mov     r9d, 14h
0x140004104  mov     qword ptr [rsp+0C8h+RemlockSize], rbx
0x140004109  mov     r8d, r12d
0x14000410c  jmp     loc_140004467
0x140004111  lea     r12, [rbx+110h]
0x140004118  mov     rcx, r12; FastMutex
0x14000411b  call    cs:__imp_ExAcquireFastMutex
0x140004122  nop     dword ptr [rax+rax+00h]
0x140004127  cmp     [rbx+0E8h], r15
0x14000412e  jnz     short loc_140004184
0x140004130  mov     esi, 0C0000001h
0x140004135  lea     r8, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14000413c  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x140004143  jz      loc_14000431B
0x140004149  mov     rcx, cs:WPP_GLOBAL_Control
0x140004150  lea     rax, WPP_bce545a1de1235e2be96703916423b99_Traceguids
0x140004157  mov     dword ptr [rsp+0C8h+var_90], esi
0x14000415b  mov     r9d, 10h
0x140004161  mov     [rsp+0C8h+var_98], rdi
0x140004166  mov     dl, 2
0x140004168  mov     [rsp+0C8h+var_A0], r14
0x14000416d  mov     rcx, [rcx+40h]
0x140004171  lea     r8d, [r9-0Fh]
0x140004175  mov     qword ptr [rsp+0C8h+RemlockSize], rax
0x14000417a  call    WPP_RECORDER_SF_qqd
0x14000417f  jmp     loc_14000431B
0x140004184  mov     rax, [rdi+0B8h]
0x14000418b  lea     rcx, [rsp+0C8h+Event]; Event
0x140004190  xor     r8d, r8d; State
0x140004193  xor     edx, edx; Type
0x140004195  movups  xmm0, xmmword ptr [rax]
0x140004198  movups  xmmword ptr [rax-48h], xmm0
0x14000419c  movups  xmm1, xmmword ptr [rax+10h]
0x1400041a0  movups  xmmword ptr [rax-38h], xmm1
0x1400041a4  movups  xmm0, xmmword ptr [rax+20h]
0x1400041a8  movups  xmmword ptr [rax-28h], xmm0
0x1400041ac  movsd   xmm1, qword ptr [rax+30h]
0x1400041b1  movsd   qword ptr [rax-18h], xmm1
0x1400041b6  mov     [rax-45h], r15b
0x1400041ba  call    cs:__imp_KeInitializeEvent
0x1400041c1  nop     dword ptr [rax+rax+00h]
0x1400041c6  mov     rax, [rdi+0B8h]
0x1400041cd  lea     rcx, MouHid_CreateComplete
0x1400041d4  mov     rdx, rdi; Irp
0x1400041d7  mov     [rax-10h], rcx
0x1400041db  lea     rcx, [rsp+0C8h+Event]
0x1400041e0  mov     [rax-8], rcx
0x1400041e4  mov     byte ptr [rax-45h], 0E0h
0x1400041e8  mov     rcx, [rbx+8]; DeviceObject
0x1400041ec  call    cs:__imp_IofCallDriver
0x1400041f3  nop     dword ptr [rax+rax+00h]
0x1400041f8  xor     r9d, r9d; Alertable
0x1400041fb  mov     qword ptr [rsp+0C8h+RemlockSize], r15; Timeout
0x140004200  xor     r8d, r8d; WaitMode
0x140004203  lea     rcx, [rsp+0C8h+Event]; Object
0x140004208  xor     edx, edx; WaitReason
0x14000420a  mov     esi, eax
0x14000420c  call    cs:__imp_KeWaitForSingleObject
0x140004213  nop     dword ptr [rax+rax+00h]
0x140004218  test    esi, esi
0x14000421a  js      loc_14000431B
0x140004220  mov     esi, [rdi+30h]
0x140004223  test    esi, esi
0x140004225  js      loc_14000431B
0x14000422b  cmp     [rbx+80h], r15
0x140004232  jnz     loc_14000431B
0x140004238  mov     rax, [rbp+8]
0x14000423c  mov     edx, [rax+10h]
0x14000423f  test    dl, 1
0x140004242  jz      loc_14000431B
0x140004248  movzx   eax, word ptr [rbp+1Ah]
0x14000424c  mov     esi, 1
0x140004251  mov     ecx, esi
0x140004253  lock xadd [rbx+18h], ecx
0x140004258  add     ecx, esi
0x14000425a  lea     r8, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140004261  cmp     cs:WPP_RECORDER_INITIALIZED, r8
0x140004268  jz      short loc_140004299
0x14000426a  mov     [rsp+0C8h+var_78], ecx
0x14000426e  mov     rcx, cs:WPP_GLOBAL_Control
0x140004275  mov     [rsp+0C8h+var_80], eax
0x140004279  mov     rax, [rbp+30h]
0x14000427d  mov     [rsp+0C8h+var_88], edx
0x140004281  mov     rcx, [rcx+40h]
0x140004285  mov     [rsp+0C8h+var_90], rax
0x14000428a  mov     [rsp+0C8h+var_98], rdi
0x14000428f  mov     [rsp+0C8h+var_A0], r14
0x140004294  call    WPP_RECORDER_SF_qqqDDl
0x140004299  mov     r15, [rbp+30h]
0x14000429d  lea     rcx, [rbx+90h]; Event
0x1400042a4  mov     eax, esi
0x1400042a6  mov     [rbx+80h], r15
0x1400042ad  xchg    eax, [rbx+88h]
0x1400042b3  call    cs:__imp_KeResetEvent
0x1400042ba  nop     dword ptr [rax+rax+00h]
0x1400042bf  mov     eax, 2
0x1400042c4  mov     [rsp+0C8h+RemlockSize], 20h ; ' '; RemlockSize
0x1400042cc  xchg    eax, [rbx+1Ch]
0x1400042cf  mov     rdx, [rbx+70h]; Tag
0x1400042d3  lea     r8, File; File
0x1400042da  mov     r9d, esi; Line
0x1400042dd  mov     rcx, r13; RemoveLock
0x1400042e0  call    cs:__imp_IoAcquireRemoveLockEx
0x1400042e7  nop     dword ptr [rax+rax+00h]
0x1400042ec  mov     rax, [rbx+70h]
0x1400042f0  mov     rcx, rbx
0x1400042f3  mov     dword ptr [rax+30h], 0
0x1400042fa  call    MouHid_StartRead
0x1400042ff  mov     esi, eax
0x140004301  cmp     eax, 103h
0x140004306  jnz     short loc_14000430C
0x140004308  xor     esi, esi
0x14000430a  jmp     short loc_14000431B
0x14000430c  test    eax, eax
0x14000430e  jns     short loc_14000431B
0x140004310  mov     qword ptr [rbx+80h], 0
0x14000431b  mov     rcx, r12; FastMutex
0x14000431e  call    cs:__imp_ExReleaseFastMutex
0x140004325  nop     dword ptr [rax+rax+00h]
0x14000432a  xor     r12d, r12d
0x14000432d  test    esi, esi
0x14000432f  js      loc_1400043FE
0x140004335  test    r15, r15
0x140004338  jz      loc_1400043FE
0x14000433e  mov     ecx, r12d
0x140004341  xor     eax, eax
0x140004343  lock cmpxchg [rbx+38h], ecx
0x140004348  jnz     loc_1400043FE
0x14000434e  lea     rbp, [rbx+0C0h]
0x140004355  mov     rcx, rbp; Event
0x140004358  call    cs:__imp_KeResetEvent
0x14000435f  nop     dword ptr [rax+rax+00h]
0x140004364  lea     r15d, [r12+1]
0x140004369  mov     eax, r15d
0x14000436c  lea     ecx, [r12+2]
0x140004371  lock cmpxchg [rbx+88h], ecx
0x140004379  jnz     short loc_1400043E8
0x14000437b  mov     rcx, rbx
0x14000437e  call    MouHid_SetResolutionMultipliers
0x140004383  cmp     eax, 0C00000BBh
0x140004388  mov     ecx, r12d
0x14000438b  mov     edx, eax
0x14000438d  lea     eax, [r12+2]
0x140004392  setnz   cl
0x140004395  add     ecx, r15d
0x140004398  xchg    ecx, [rbx+38h]
0x14000439b  lock cmpxchg [rbx+88h], r15d
0x1400043a4  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400043ab  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400043b2  jz      short loc_1400043E8
0x1400043b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400043bb  lea     rax, WPP_bce545a1de1235e2be96703916423b99_Traceguids
0x1400043c2  mov     dword ptr [rsp+0C8h+var_90], edx
0x1400043c6  lea     r9d, [r12+12h]
0x1400043cb  mov     [rsp+0C8h+var_98], rdi
0x1400043d0  mov     r8d, r15d
0x1400043d3  mov     [rsp+0C8h+var_A0], r14
0x1400043d8  mov     dl, 4
0x1400043da  mov     rcx, [rcx+40h]
0x1400043de  mov     qword ptr [rsp+0C8h+RemlockSize], rax
0x1400043e3  call    WPP_RECORDER_SF_qqd
0x1400043e8  xor     r8d, r8d; Wait
0x1400043eb  xor     edx, edx; Increment
0x1400043ed  mov     rcx, rbp; Event
0x1400043f0  call    cs:__imp_KeSetEvent
0x1400043f7  nop     dword ptr [rax+rax+00h]
0x1400043fc  jmp     short loc_140004404
0x1400043fe  mov     r15d, 1
0x140004404  xor     edx, edx; PriorityBoost
0x140004406  mov     [rdi+30h], esi
0x140004409  mov     rcx, rdi; Irp
0x14000440c  mov     [rdi+38h], r12
0x140004410  call    cs:__imp_IofCompleteRequest
0x140004417  nop     dword ptr [rax+rax+00h]
0x14000441c  mov     r8d, 20h ; ' '; RemlockSize
0x140004422  mov     rdx, rdi; Tag
0x140004425  mov     rcx, r13; RemoveLock
0x140004428  call    cs:__imp_IoReleaseRemoveLockEx
0x14000442f  nop     dword ptr [rax+rax+00h]
0x140004434  lea     rax, WPP_RECORDER_INITIALIZED
0x14000443b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140004442  jz      short loc_140004472
0x140004444  mov     rcx, cs:WPP_GLOBAL_Control
0x14000444b  cmp     [rcx+48h], r12w
0x140004450  jz      short loc_140004472
0x140004452  lea     rax, WPP_bce545a1de1235e2be96703916423b99_Traceguids
0x140004459  mov     r9d, 13h
0x14000445f  mov     qword ptr [rsp+0C8h+RemlockSize], rax
0x140004464  mov     r8d, r15d
0x140004467  mov     rcx, [rcx+40h]
0x14000446b  mov     dl, 5
0x14000446d  call    WPP_RECORDER_SF_
0x140004472  mov     eax, esi
0x140004474  add     rsp, 88h
0x14000447b  pop     r15
0x14000447d  pop     r14
0x14000447f  pop     r13
0x140004481  pop     r12
0x140004483  pop     rdi
0x140004484  pop     rsi
0x140004485  pop     rbp
0x140004486  pop     rbx
0x140004487  retn
```
