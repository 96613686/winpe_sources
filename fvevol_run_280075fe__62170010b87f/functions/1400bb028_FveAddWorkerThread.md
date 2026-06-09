# FveAddWorkerThread

- ea: `0x1400bb028`
- end: `0x1400bb395`
- name: `FveAddWorkerThread`
- size: `877`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400bb39c`

## callees

- `0x140008dc0`
- `0x140008e44`
- `0x140021d00`
- `0x14002c890`
- `0x1400bb028`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400bb108`
- `ntoskrnl!KeInitializeEvent` at `0x1400bb108`
- `ntoskrnl!PsCreateSystemThread` at `0x1400bb18b`
- `ntoskrnl!PsCreateSystemThread` at `0x1400bb18b`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400bb214`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400bb214`
- `ntoskrnl!KeReleaseMutex` at `0x1400bb30e`
- `ntoskrnl!KeReleaseMutex` at `0x1400bb30e`
- `ntoskrnl!KeSetPriorityThread` at `0x1400bb2bd`
- `ntoskrnl!KeSetPriorityThread` at `0x1400bb2bd`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400bb128`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400bb128`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bb330`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400bb330`
- `ntoskrnl!ZwClose` at `0x1400bb22e`
- `ntoskrnl!ZwClose` at `0x1400bb22e`
- `ntoskrnl!ExAllocatePool2` at `0x1400bb0b5`
- `ntoskrnl!ExAllocatePool2` at `0x1400bb0b5`

## pseudocode

```c
__int64 __fastcall FveAddWorkerThread(__int64 a1, int a2, __int64 a3, _QWORD *a4)
{
  char *Pool2; // rax
  char *StartContext; // rbx
  NTSTATUS v9; // edi
  NTSTATUS v10; // eax
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  void *v14; // rcx
  KPRIORITY PriorityFromThread; // eax
  PVOID Object; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-38h] BYREF
  void *ThreadHandle; // [rsp+C8h] [rbp+48h] BYREF

  ThreadHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_800090fb57ab3b3e6ac501450fc51a6b_Traceguids);
  }
  *a4 = 0;
  Pool2 = (char *)ExAllocatePool2(64, 64, 809850438);
  StartContext = Pool2;
  if ( Pool2 )
  {
    memset(Pool2, 0, 0x40u);
    *((_QWORD *)StartContext + 2) = a1;
    *((_DWORD *)StartContext + 8) = a2;
    *((_DWORD *)StartContext + 9) = 18;
    KeInitializeEvent((PRKEVENT)(StartContext + 40), NotificationEvent, 0);
    v9 = KeWaitForSingleObject((PVOID)(a1 + 296), Executive, 0, 0, 0);
    if ( v9 < 0 )
      goto LABEL_27;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 512;
    ObjectAttributes.ObjectName = 0;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v10 = PsCreateSystemThread(
            &ThreadHandle,
            0,
            &ObjectAttributes,
            0,
            0,
            (PKSTART_ROUTINE)FveWorkerForwardProgress,
            StartContext);
    v9 = v10;
    if ( v10 >= 0 )
    {
      v14 = ThreadHandle;
      *a4 = StartContext + 40;
      Object = 0;
      v9 = ObReferenceObjectByHandle(v14, 0x1FFFFFu, 0, 0, &Object, 0);
      *((_QWORD *)StartContext + 3) = Object;
      ZwClose(ThreadHandle);
      if ( v9 >= 0 )
      {
        if ( (int)FveGetPriorityFromThreadEx(KeGetCurrentThread(), 18) >= 18 )
          PriorityFromThread = FveGetPriorityFromThreadEx(KeGetCurrentThread(), 18);
        else
          PriorityFromThread = 18;
        KeSetPriorityThread(*((PKTHREAD *)StartContext + 3), PriorityFromThread);
        ++*(_DWORD *)(a1 + 232);
        StartContext = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_800090fb57ab3b3e6ac501450fc51a6b_Traceguids, 18);
        }
      }
      else
      {
        *((_QWORD *)StartContext + 3) = 0;
        StartContext = 0;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v12 = 12;
          v13 = (unsigned int)v9;
          goto LABEL_13;
        }
      }
    }
    else
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v12 = 11;
        v13 = (unsigned int)v10;
LABEL_13:
        WPP_SF_d(v11->AttachedDevice, v12, WPP_800090fb57ab3b3e6ac501450fc51a6b_Traceguids, v13);
      }
    }
    KeReleaseMutex((PRKMUTEX)(a1 + 296), 0);
    if ( !StartContext )
      goto LABEL_28;
LABEL_27:
    ExFreePoolWithTag(StartContext, 0x30455646u);
    *a4 = 0;
    goto LABEL_28;
  }
  v9 = -1073741670;
LABEL_28:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_800090fb57ab3b3e6ac501450fc51a6b_Traceguids, (unsigned int)v9);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400bb028  mov     [rsp-28h+arg_0], rbx
0x1400bb02d  mov     [rsp-28h+arg_8], rsi
0x1400bb032  push    rbp
0x1400bb033  push    rdi
0x1400bb034  push    r12
0x1400bb036  push    r14
0x1400bb038  push    r15
0x1400bb03a  mov     rbp, rsp
0x1400bb03d  sub     rsp, 80h
0x1400bb044  xorps   xmm0, xmm0
0x1400bb047  mov     [rbp+ThreadHandle], 0
0x1400bb04f  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1400bb053  mov     r14, r9
0x1400bb056  mov     edi, edx
0x1400bb058  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1400bb05c  mov     rsi, rcx
0x1400bb05f  xor     eax, eax
0x1400bb061  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1400bb065  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb06c  lea     rax, WPP_GLOBAL_Control
0x1400bb073  cmp     rcx, rax
0x1400bb076  jz      short loc_1400BB09C
0x1400bb078  test    dword ptr [rcx+2Ch], 200h
0x1400bb07f  jz      short loc_1400BB09C
0x1400bb081  cmp     byte ptr [rcx+29h], 5
0x1400bb085  jb      short loc_1400BB09C
0x1400bb087  mov     rcx, [rcx+18h]
0x1400bb08b  lea     r8, WPP_800090fb57ab3b3e6ac501450fc51a6b_Traceguids
0x1400bb092  mov     edx, 0Ah
0x1400bb097  call    WPP_SF_
0x1400bb09c  mov     r15d, 40h ; '@'
0x1400bb0a2  mov     qword ptr [r14], 0
0x1400bb0a9  mov     edx, r15d
0x1400bb0ac  mov     ecx, r15d
0x1400bb0af  mov     r8d, 30455646h
0x1400bb0b5  call    cs:__imp_ExAllocatePool2
0x1400bb0bc  nop     dword ptr [rax+rax+00h]
0x1400bb0c1  mov     rbx, rax
0x1400bb0c4  test    rax, rax
0x1400bb0c7  jnz     short loc_1400BB0DA
0x1400bb0c9  mov     edi, 0C000009Ah
0x1400bb0ce  lea     rsi, WPP_GLOBAL_Control
0x1400bb0d5  jmp     loc_1400BB343
0x1400bb0da  mov     r8, r15; Size
0x1400bb0dd  lea     r12, [rsi+128h]
0x1400bb0e4  xor     edx, edx; Val
0x1400bb0e6  mov     rcx, rbx; void *
0x1400bb0e9  call    memset
0x1400bb0ee  lea     r15, [rbx+28h]
0x1400bb0f2  mov     [rbx+10h], rsi
0x1400bb0f6  mov     rcx, r15; Event
0x1400bb0f9  mov     [rbx+20h], edi
0x1400bb0fc  xor     r8d, r8d; State
0x1400bb0ff  mov     dword ptr [rbx+24h], 12h
0x1400bb106  xor     edx, edx; Type
0x1400bb108  call    cs:__imp_KeInitializeEvent
0x1400bb10f  nop     dword ptr [rax+rax+00h]
0x1400bb114  xor     r9d, r9d; Alertable
0x1400bb117  mov     [rsp+80h+Timeout], 0; Timeout
0x1400bb120  xor     r8d, r8d; WaitMode
0x1400bb123  xor     edx, edx; WaitReason
0x1400bb125  mov     rcx, r12; Object
0x1400bb128  call    cs:__imp_KeWaitForSingleObject
0x1400bb12f  nop     dword ptr [rax+rax+00h]
0x1400bb134  mov     edi, eax
0x1400bb136  test    eax, eax
0x1400bb138  js      loc_1400BB321
0x1400bb13e  lea     rax, FveWorkerForwardProgress
0x1400bb145  mov     [rsp+80h+StartContext], rbx; StartContext
0x1400bb14a  xorps   xmm0, xmm0
0x1400bb14d  mov     [rsp+80h+StartRoutine], rax; StartRoutine
0x1400bb152  xor     r9d, r9d; ProcessHandle
0x1400bb155  mov     [rsp+80h+Timeout], 0; ClientId
0x1400bb15e  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400bb162  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400bb169  xor     edx, edx; DesiredAccess
0x1400bb16b  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1400bb173  lea     rcx, [rbp+ThreadHandle]; ThreadHandle
0x1400bb177  mov     [rbp+ObjectAttributes.Attributes], 200h
0x1400bb17e  mov     [rbp+ObjectAttributes.ObjectName], 0
0x1400bb186  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400bb18b  call    cs:__imp_PsCreateSystemThread
0x1400bb192  nop     dword ptr [rax+rax+00h]
0x1400bb197  mov     edi, eax
0x1400bb199  test    eax, eax
0x1400bb19b  jns     short loc_1400BB1E8
0x1400bb19d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb1a4  lea     rsi, WPP_GLOBAL_Control
0x1400bb1ab  cmp     rcx, rsi
0x1400bb1ae  jz      loc_1400BB309
0x1400bb1b4  test    dword ptr [rcx+2Ch], 200h
0x1400bb1bb  jz      loc_1400BB309
0x1400bb1c1  cmp     byte ptr [rcx+29h], 2
0x1400bb1c5  jb      loc_1400BB309
0x1400bb1cb  mov     edx, 0Bh
0x1400bb1d0  mov     r9d, eax
0x1400bb1d3  mov     rcx, [rcx+18h]
0x1400bb1d7  lea     r8, WPP_800090fb57ab3b3e6ac501450fc51a6b_Traceguids
0x1400bb1de  call    WPP_SF_d
0x1400bb1e3  jmp     loc_1400BB309
0x1400bb1e8  mov     rcx, [rbp+ThreadHandle]; Handle
0x1400bb1ec  lea     rax, [rbp+Object]
0x1400bb1f0  mov     [rsp+80h+StartRoutine], 0; HandleInformation
0x1400bb1f9  xor     r9d, r9d; AccessMode
0x1400bb1fc  xor     r8d, r8d; ObjectType
0x1400bb1ff  mov     [rsp+80h+Timeout], rax; Object
0x1400bb204  mov     edx, 1FFFFFh; DesiredAccess
0x1400bb209  mov     [r14], r15
0x1400bb20c  mov     [rbp+Object], 0
0x1400bb214  call    cs:__imp_ObReferenceObjectByHandle
0x1400bb21b  nop     dword ptr [rax+rax+00h]
0x1400bb220  mov     edi, eax
0x1400bb222  mov     rax, [rbp+Object]
0x1400bb226  mov     [rbx+18h], rax
0x1400bb22a  mov     rcx, [rbp+ThreadHandle]; Handle
0x1400bb22e  call    cs:__imp_ZwClose
0x1400bb235  nop     dword ptr [rax+rax+00h]
0x1400bb23a  test    edi, edi
0x1400bb23c  jns     short loc_1400BB281
0x1400bb23e  mov     qword ptr [rbx+18h], 0
0x1400bb246  xor     ebx, ebx
0x1400bb248  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb24f  lea     rsi, WPP_GLOBAL_Control
0x1400bb256  cmp     rcx, rsi
0x1400bb259  jz      loc_1400BB309
0x1400bb25f  test    dword ptr [rcx+2Ch], 200h
0x1400bb266  jz      loc_1400BB309
0x1400bb26c  cmp     byte ptr [rcx+29h], 2
0x1400bb270  jb      loc_1400BB309
0x1400bb276  lea     edx, [rbx+0Ch]
0x1400bb279  mov     r9d, edi
0x1400bb27c  jmp     loc_1400BB1D3
0x1400bb281  mov     rcx, gs:188h
0x1400bb28a  xor     r8d, r8d
0x1400bb28d  lea     r15d, [r8+12h]
0x1400bb291  mov     edx, r15d
0x1400bb294  call    FveGetPriorityFromThreadEx
0x1400bb299  cmp     eax, r15d
0x1400bb29c  jge     short loc_1400BB2A3
0x1400bb29e  mov     eax, r15d
0x1400bb2a1  jmp     short loc_1400BB2B7
0x1400bb2a3  mov     rcx, gs:188h
0x1400bb2ac  xor     r8d, r8d
0x1400bb2af  mov     edx, r15d
0x1400bb2b2  call    FveGetPriorityFromThreadEx
0x1400bb2b7  mov     rcx, [rbx+18h]; Thread
0x1400bb2bb  mov     edx, eax; Priority
0x1400bb2bd  call    cs:__imp_KeSetPriorityThread
0x1400bb2c4  nop     dword ptr [rax+rax+00h]
0x1400bb2c9  inc     dword ptr [rsi+0E8h]
0x1400bb2cf  xor     ebx, ebx
0x1400bb2d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb2d8  lea     rsi, WPP_GLOBAL_Control
0x1400bb2df  cmp     rcx, rsi
0x1400bb2e2  jz      short loc_1400BB309
0x1400bb2e4  test    dword ptr [rcx+2Ch], 200h
0x1400bb2eb  jz      short loc_1400BB309
0x1400bb2ed  cmp     byte ptr [rcx+29h], 5
0x1400bb2f1  jb      short loc_1400BB309
0x1400bb2f3  mov     rcx, [rcx+18h]
0x1400bb2f7  lea     edx, [rbx+0Dh]
0x1400bb2fa  mov     r9d, r15d
0x1400bb2fd  lea     r8, WPP_800090fb57ab3b3e6ac501450fc51a6b_Traceguids
0x1400bb304  call    WPP_SF_d
0x1400bb309  xor     edx, edx; Wait
0x1400bb30b  mov     rcx, r12; Mutex
0x1400bb30e  call    cs:__imp_KeReleaseMutex
0x1400bb315  nop     dword ptr [rax+rax+00h]
0x1400bb31a  test    rbx, rbx
0x1400bb31d  jz      short loc_1400BB343
0x1400bb31f  jmp     short loc_1400BB328
0x1400bb321  lea     rsi, WPP_GLOBAL_Control
0x1400bb328  mov     edx, 30455646h; Tag
0x1400bb32d  mov     rcx, rbx; P
0x1400bb330  call    cs:__imp_ExFreePoolWithTag
0x1400bb337  nop     dword ptr [rax+rax+00h]
0x1400bb33c  mov     qword ptr [r14], 0
0x1400bb343  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bb34a  cmp     rcx, rsi
0x1400bb34d  jz      short loc_1400BB376
0x1400bb34f  test    dword ptr [rcx+2Ch], 200h
0x1400bb356  jz      short loc_1400BB376
0x1400bb358  cmp     byte ptr [rcx+29h], 5
0x1400bb35c  jb      short loc_1400BB376
0x1400bb35e  mov     rcx, [rcx+18h]
0x1400bb362  lea     r8, WPP_800090fb57ab3b3e6ac501450fc51a6b_Traceguids
0x1400bb369  mov     edx, 0Eh
0x1400bb36e  mov     r9d, edi
0x1400bb371  call    WPP_SF_d
0x1400bb376  lea     r11, [rsp+80h+var_s0]
0x1400bb37e  mov     eax, edi
0x1400bb380  mov     rbx, [r11+30h]
0x1400bb384  mov     rsi, [r11+38h]
0x1400bb388  mov     rsp, r11
0x1400bb38b  pop     r15
0x1400bb38d  pop     r14
0x1400bb38f  pop     r12
0x1400bb391  pop     rdi
0x1400bb392  pop     rbp
0x1400bb393  retn
```
