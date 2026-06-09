# FveAddWorkerThread

- ea: `0x1400be818`
- end: `0x1400beb85`
- name: `FveAddWorkerThread`
- size: `877`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1400beb8c`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x140023040`
- `0x14002d890`
- `0x1400be818`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x1400be8f8`
- `ntoskrnl!KeInitializeEvent` at `0x1400be8f8`
- `ntoskrnl!PsCreateSystemThread` at `0x1400be97b`
- `ntoskrnl!PsCreateSystemThread` at `0x1400be97b`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400bea04`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x1400bea04`
- `ntoskrnl!KeReleaseMutex` at `0x1400beafe`
- `ntoskrnl!KeReleaseMutex` at `0x1400beafe`
- `ntoskrnl!KeSetPriorityThread` at `0x1400beaad`
- `ntoskrnl!KeSetPriorityThread` at `0x1400beaad`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400be918`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400be918`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400beb20`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400beb20`
- `ntoskrnl!ZwClose` at `0x1400bea1e`
- `ntoskrnl!ZwClose` at `0x1400bea1e`
- `ntoskrnl!ExAllocatePool2` at `0x1400be8a5`
- `ntoskrnl!ExAllocatePool2` at `0x1400be8a5`

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
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_c7c1cf9ad7eb3c0cf12233945c35745b_Traceguids);
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
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_c7c1cf9ad7eb3c0cf12233945c35745b_Traceguids, 18);
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
        WPP_SF_d(v11->AttachedDevice, v12, WPP_c7c1cf9ad7eb3c0cf12233945c35745b_Traceguids, v13);
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
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_c7c1cf9ad7eb3c0cf12233945c35745b_Traceguids, (unsigned int)v9);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1400be818  mov     [rsp-28h+arg_0], rbx
0x1400be81d  mov     [rsp-28h+arg_8], rsi
0x1400be822  push    rbp
0x1400be823  push    rdi
0x1400be824  push    r12
0x1400be826  push    r14
0x1400be828  push    r15
0x1400be82a  mov     rbp, rsp
0x1400be82d  sub     rsp, 80h
0x1400be834  xorps   xmm0, xmm0
0x1400be837  mov     [rbp+ThreadHandle], 0
0x1400be83f  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1400be843  mov     r14, r9
0x1400be846  mov     edi, edx
0x1400be848  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1400be84c  mov     rsi, rcx
0x1400be84f  xor     eax, eax
0x1400be851  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1400be855  mov     rcx, cs:WPP_GLOBAL_Control
0x1400be85c  lea     rax, WPP_GLOBAL_Control
0x1400be863  cmp     rcx, rax
0x1400be866  jz      short loc_1400BE88C
0x1400be868  test    dword ptr [rcx+2Ch], 200h
0x1400be86f  jz      short loc_1400BE88C
0x1400be871  cmp     byte ptr [rcx+29h], 5
0x1400be875  jb      short loc_1400BE88C
0x1400be877  mov     rcx, [rcx+18h]
0x1400be87b  lea     r8, WPP_c7c1cf9ad7eb3c0cf12233945c35745b_Traceguids
0x1400be882  mov     edx, 0Ah
0x1400be887  call    WPP_SF_
0x1400be88c  mov     r15d, 40h ; '@'
0x1400be892  mov     qword ptr [r14], 0
0x1400be899  mov     edx, r15d
0x1400be89c  mov     ecx, r15d
0x1400be89f  mov     r8d, 30455646h
0x1400be8a5  call    cs:__imp_ExAllocatePool2
0x1400be8ac  nop     dword ptr [rax+rax+00h]
0x1400be8b1  mov     rbx, rax
0x1400be8b4  test    rax, rax
0x1400be8b7  jnz     short loc_1400BE8CA
0x1400be8b9  mov     edi, 0C000009Ah
0x1400be8be  lea     rsi, WPP_GLOBAL_Control
0x1400be8c5  jmp     loc_1400BEB33
0x1400be8ca  mov     r8, r15; Size
0x1400be8cd  lea     r12, [rsi+128h]
0x1400be8d4  xor     edx, edx; Val
0x1400be8d6  mov     rcx, rbx; void *
0x1400be8d9  call    memset
0x1400be8de  lea     r15, [rbx+28h]
0x1400be8e2  mov     [rbx+10h], rsi
0x1400be8e6  mov     rcx, r15; Event
0x1400be8e9  mov     [rbx+20h], edi
0x1400be8ec  xor     r8d, r8d; State
0x1400be8ef  mov     dword ptr [rbx+24h], 12h
0x1400be8f6  xor     edx, edx; Type
0x1400be8f8  call    cs:__imp_KeInitializeEvent
0x1400be8ff  nop     dword ptr [rax+rax+00h]
0x1400be904  xor     r9d, r9d; Alertable
0x1400be907  mov     [rsp+80h+Timeout], 0; Timeout
0x1400be910  xor     r8d, r8d; WaitMode
0x1400be913  xor     edx, edx; WaitReason
0x1400be915  mov     rcx, r12; Object
0x1400be918  call    cs:__imp_KeWaitForSingleObject
0x1400be91f  nop     dword ptr [rax+rax+00h]
0x1400be924  mov     edi, eax
0x1400be926  test    eax, eax
0x1400be928  js      loc_1400BEB11
0x1400be92e  lea     rax, FveWorkerForwardProgress
0x1400be935  mov     [rsp+80h+StartContext], rbx; StartContext
0x1400be93a  xorps   xmm0, xmm0
0x1400be93d  mov     [rsp+80h+StartRoutine], rax; StartRoutine
0x1400be942  xor     r9d, r9d; ProcessHandle
0x1400be945  mov     [rsp+80h+Timeout], 0; ClientId
0x1400be94e  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400be952  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1400be959  xor     edx, edx; DesiredAccess
0x1400be95b  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1400be963  lea     rcx, [rbp+ThreadHandle]; ThreadHandle
0x1400be967  mov     [rbp+ObjectAttributes.Attributes], 200h
0x1400be96e  mov     [rbp+ObjectAttributes.ObjectName], 0
0x1400be976  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1400be97b  call    cs:__imp_PsCreateSystemThread
0x1400be982  nop     dword ptr [rax+rax+00h]
0x1400be987  mov     edi, eax
0x1400be989  test    eax, eax
0x1400be98b  jns     short loc_1400BE9D8
0x1400be98d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400be994  lea     rsi, WPP_GLOBAL_Control
0x1400be99b  cmp     rcx, rsi
0x1400be99e  jz      loc_1400BEAF9
0x1400be9a4  test    dword ptr [rcx+2Ch], 200h
0x1400be9ab  jz      loc_1400BEAF9
0x1400be9b1  cmp     byte ptr [rcx+29h], 2
0x1400be9b5  jb      loc_1400BEAF9
0x1400be9bb  mov     edx, 0Bh
0x1400be9c0  mov     r9d, eax
0x1400be9c3  mov     rcx, [rcx+18h]
0x1400be9c7  lea     r8, WPP_c7c1cf9ad7eb3c0cf12233945c35745b_Traceguids
0x1400be9ce  call    WPP_SF_d
0x1400be9d3  jmp     loc_1400BEAF9
0x1400be9d8  mov     rcx, [rbp+ThreadHandle]; Handle
0x1400be9dc  lea     rax, [rbp+Object]
0x1400be9e0  mov     [rsp+80h+StartRoutine], 0; HandleInformation
0x1400be9e9  xor     r9d, r9d; AccessMode
0x1400be9ec  xor     r8d, r8d; ObjectType
0x1400be9ef  mov     [rsp+80h+Timeout], rax; Object
0x1400be9f4  mov     edx, 1FFFFFh; DesiredAccess
0x1400be9f9  mov     [r14], r15
0x1400be9fc  mov     [rbp+Object], 0
0x1400bea04  call    cs:__imp_ObReferenceObjectByHandle
0x1400bea0b  nop     dword ptr [rax+rax+00h]
0x1400bea10  mov     edi, eax
0x1400bea12  mov     rax, [rbp+Object]
0x1400bea16  mov     [rbx+18h], rax
0x1400bea1a  mov     rcx, [rbp+ThreadHandle]; Handle
0x1400bea1e  call    cs:__imp_ZwClose
0x1400bea25  nop     dword ptr [rax+rax+00h]
0x1400bea2a  test    edi, edi
0x1400bea2c  jns     short loc_1400BEA71
0x1400bea2e  mov     qword ptr [rbx+18h], 0
0x1400bea36  xor     ebx, ebx
0x1400bea38  mov     rcx, cs:WPP_GLOBAL_Control
0x1400bea3f  lea     rsi, WPP_GLOBAL_Control
0x1400bea46  cmp     rcx, rsi
0x1400bea49  jz      loc_1400BEAF9
0x1400bea4f  test    dword ptr [rcx+2Ch], 200h
0x1400bea56  jz      loc_1400BEAF9
0x1400bea5c  cmp     byte ptr [rcx+29h], 2
0x1400bea60  jb      loc_1400BEAF9
0x1400bea66  lea     edx, [rbx+0Ch]
0x1400bea69  mov     r9d, edi
0x1400bea6c  jmp     loc_1400BE9C3
0x1400bea71  mov     rcx, gs:188h
0x1400bea7a  xor     r8d, r8d
0x1400bea7d  lea     r15d, [r8+12h]
0x1400bea81  mov     edx, r15d
0x1400bea84  call    FveGetPriorityFromThreadEx
0x1400bea89  cmp     eax, r15d
0x1400bea8c  jge     short loc_1400BEA93
0x1400bea8e  mov     eax, r15d
0x1400bea91  jmp     short loc_1400BEAA7
0x1400bea93  mov     rcx, gs:188h
0x1400bea9c  xor     r8d, r8d
0x1400bea9f  mov     edx, r15d
0x1400beaa2  call    FveGetPriorityFromThreadEx
0x1400beaa7  mov     rcx, [rbx+18h]; Thread
0x1400beaab  mov     edx, eax; Priority
0x1400beaad  call    cs:__imp_KeSetPriorityThread
0x1400beab4  nop     dword ptr [rax+rax+00h]
0x1400beab9  inc     dword ptr [rsi+0E8h]
0x1400beabf  xor     ebx, ebx
0x1400beac1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400beac8  lea     rsi, WPP_GLOBAL_Control
0x1400beacf  cmp     rcx, rsi
0x1400bead2  jz      short loc_1400BEAF9
0x1400bead4  test    dword ptr [rcx+2Ch], 200h
0x1400beadb  jz      short loc_1400BEAF9
0x1400beadd  cmp     byte ptr [rcx+29h], 5
0x1400beae1  jb      short loc_1400BEAF9
0x1400beae3  mov     rcx, [rcx+18h]
0x1400beae7  lea     edx, [rbx+0Dh]
0x1400beaea  mov     r9d, r15d
0x1400beaed  lea     r8, WPP_c7c1cf9ad7eb3c0cf12233945c35745b_Traceguids
0x1400beaf4  call    WPP_SF_d
0x1400beaf9  xor     edx, edx; Wait
0x1400beafb  mov     rcx, r12; Mutex
0x1400beafe  call    cs:__imp_KeReleaseMutex
0x1400beb05  nop     dword ptr [rax+rax+00h]
0x1400beb0a  test    rbx, rbx
0x1400beb0d  jz      short loc_1400BEB33
0x1400beb0f  jmp     short loc_1400BEB18
0x1400beb11  lea     rsi, WPP_GLOBAL_Control
0x1400beb18  mov     edx, 30455646h; Tag
0x1400beb1d  mov     rcx, rbx; P
0x1400beb20  call    cs:__imp_ExFreePoolWithTag
0x1400beb27  nop     dword ptr [rax+rax+00h]
0x1400beb2c  mov     qword ptr [r14], 0
0x1400beb33  mov     rcx, cs:WPP_GLOBAL_Control
0x1400beb3a  cmp     rcx, rsi
0x1400beb3d  jz      short loc_1400BEB66
0x1400beb3f  test    dword ptr [rcx+2Ch], 200h
0x1400beb46  jz      short loc_1400BEB66
0x1400beb48  cmp     byte ptr [rcx+29h], 5
0x1400beb4c  jb      short loc_1400BEB66
0x1400beb4e  mov     rcx, [rcx+18h]
0x1400beb52  lea     r8, WPP_c7c1cf9ad7eb3c0cf12233945c35745b_Traceguids
0x1400beb59  mov     edx, 0Eh
0x1400beb5e  mov     r9d, edi
0x1400beb61  call    WPP_SF_d
0x1400beb66  lea     r11, [rsp+80h+var_s0]
0x1400beb6e  mov     eax, edi
0x1400beb70  mov     rbx, [r11+30h]
0x1400beb74  mov     rsi, [r11+38h]
0x1400beb78  mov     rsp, r11
0x1400beb7b  pop     r15
0x1400beb7d  pop     r14
0x1400beb7f  pop     r12
0x1400beb81  pop     rdi
0x1400beb82  pop     rbp
0x1400beb83  retn
```
