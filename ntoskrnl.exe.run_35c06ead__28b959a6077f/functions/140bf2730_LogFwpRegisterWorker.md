# LogFwpRegisterWorker

- ea: `0x140bf2730`
- end: `0x140bf2e62`
- name: `LogFwpRegisterWorker`
- size: `1842`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1403f2d50`
- `0x1406daa70`
- `0x1406daad0`
- `0x1406dac30`
- `0x1406db490`
- `0x140bf2730`

## string_xrefs

- `0x140bf2abc`: `ResidentSize`
- `0x140bf2e06`: `CompressBitmaps`
- `0x140bf274e`: `\REGISTRY\MACHINE\SYSTEM\CurrentControlSet\Control`

## pseudocode

```c
int LogFwpRegisterWorker()
{
  int result; // eax
  NTSTATUS v1; // eax
  HANDLE v2; // rcx
  unsigned int PriorityFloorSummary; // ebx
  HANDLE KeyHandle; // [rsp+40h] [rbp+7h] BYREF
  UNICODE_STRING DestinationString; // [rsp+48h] [rbp+Fh] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp+1Fh] BYREF
  int Data; // [rsp+A8h] [rbp+6Fh] BYREF
  ULONG Disposition; // [rsp+B0h] [rbp+77h] BYREF
  HANDLE v9; // [rsp+B8h] [rbp+7Fh] BYREF

  Disposition = 0;
  Data = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  v9 = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\REGISTRY\\MACHINE\\SYSTEM\\CurrentControlSet\\Control");
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.Length = 48;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes);
  if ( result >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"BGFX");
    ObjectAttributes.RootDirectory = KeyHandle;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v1 = ZwCreateKey(&v9, 0x20019u, &ObjectAttributes, 0, 0, 1u, &Disposition);
    v2 = KeyHandle;
    if ( v1 >= 0 )
    {
      PriorityFloorSummary = WheapPfaLock.PriorityFloorSummary;
      ZwClose(KeyHandle);
      RtlInitUnicodeString(&DestinationString, L"Resume");
      Data = (PriorityFloorSummary & 0x100000) != 0;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"Width");
      Data = WheapPfaLock.ForegroundLossTime;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"Height");
      Data = *(&WheapPfaLock.ForegroundLossTime + 1);
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"BPP");
      Data = HIDWORD(WheapPfaLock.MutantListHead.Blink);
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"LogoSize");
      Data = *(_DWORD *)&gLoadedDiffHivesLock.WaitBlockFill11[168];
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"ProgressFrames");
      Data = WheapPfaLock.AbCompletedIoQoSBoostCount;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"ProgressMemory");
      Data = *(_DWORD *)&gLoadedDiffHivesLock.WaitBlockFill11[112];
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"ProgressProlog");
      Data = 1000000 * WheapPfaLock.ReadOperationCount / qword_140E139C0;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"ProgressLow");
      Data = 1000000 * qword_140E139B8 / qword_140E139C0;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"ProgressHigh");
      Data = 1000000 * (__int64)WheapPfaLock.MutantListHead.Flink / qword_140E139C0;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      if ( gLoadedDiffHivesLock.WaitBlock[2].Object )
      {
        RtlInitUnicodeString(&DestinationString, L"ResidentSize");
        Data = *(_DWORD *)gLoadedDiffHivesLock.WaitBlock[2].Object;
        ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      }
      RtlInitUnicodeString(&DestinationString, L"ProgressTotal");
      Data = 1000000LL * *(_QWORD *)&WheapPfaLock.PriorityFloorCounts[8] / qword_140E139C0;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"ProgressManual");
      Data = 1000000LL * *(_QWORD *)&WheapPfaLock.PriorityFloorCounts[16] / qword_140E139C0;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"FadeProlog");
      Data = (signed __int64)(1000000 * WheapPfaLock.InGlobalForegroundList) / qword_140E139C0;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"FadeOverlap");
      Data = WheapPfaLock.OtherOperationCount;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"FadeIo");
      Data = WheapPfaLock.AbCompletedIoBoostCount;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"FadeCpu");
      Data = (int)WheapPfaLock.MutantListHead.Blink;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"FadeFrames");
      Data = (int)WheapPfaLock.SchedulerSharedSystemSlot;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"FadeMemory");
      Data = *(_DWORD *)&gLoadedDiffHivesLock.WaitBlockFill11[108];
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"FadeLow");
      Data = 1000000 * qword_140E139C8 / qword_140E139C0;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"FadeHigh");
      Data = 1000000LL * *(_QWORD *)&WheapPfaLock.AbWaitEntryCount / qword_140E139C0;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"FadeTotal");
      Data = 1000000LL * *(_QWORD *)&WheapPfaLock.PriorityFloorCounts[24] / qword_140E139C0;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"AnimationTotal");
      Data = 1000000LL * *(_QWORD *)WheapPfaLock.PriorityFloorCounts / qword_140E139C0;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      RtlInitUnicodeString(&DestinationString, L"CompressBitmaps");
      Data = 1000000 * qword_140E4B2A8 / qword_140E139C0;
      ZwSetValueKey(v9, &DestinationString, 0, 4u, &Data, 4u);
      v2 = v9;
    }
    return ZwClose(v2);
  }
  return result;
}

```

## disassembly

```asm
0x140bf2730  mov     [rsp-8+arg_0], rbx
0x140bf2735  push    rbp
0x140bf2736  lea     rbp, [rsp-57h]
0x140bf273b  sub     rsp, 90h
0x140bf2742  xorps   xmm0, xmm0
0x140bf2745  mov     [rbp+57h+arg_10], 0
0x140bf274c  xor     eax, eax
0x140bf274e  lea     rdx, aRegistryMachin_198; "\\REGISTRY\\MACHINE\\SYSTEM\\CurrentCon"...
0x140bf2755  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140bf2759  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf275d  mov     [rbp+57h+Data], eax
0x140bf2760  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140bf2764  mov     [rbp+57h+KeyHandle], rax
0x140bf2768  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140bf276c  mov     [rbp+57h+arg_18], rax
0x140bf2770  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140bf2774  call    RtlInitUnicodeString
0x140bf2779  lea     rax, [rbp+57h+DestinationString]
0x140bf277d  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140bf2785  xorps   xmm0, xmm0
0x140bf2788  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140bf278c  mov     ebx, 30h ; '0'
0x140bf2791  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140bf2798  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140bf279c  mov     [rbp+57h+ObjectAttributes.Length], ebx
0x140bf279f  mov     edx, 20019h; DesiredAccess
0x140bf27a4  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140bf27a8  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140bf27ad  call    ZwOpenKey
0x140bf27b2  test    eax, eax
0x140bf27b4  js      short loc_140BF2824
0x140bf27b6  lea     rdx, aBgfx; "BGFX"
0x140bf27bd  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf27c1  call    RtlInitUnicodeString
0x140bf27c6  mov     rax, [rbp+57h+KeyHandle]
0x140bf27ca  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140bf27ce  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x140bf27d2  lea     rcx, [rbp+57h+arg_18]; KeyHandle
0x140bf27d6  lea     rax, [rbp+57h+DestinationString]
0x140bf27da  mov     [rbp+57h+ObjectAttributes.Length], ebx
0x140bf27dd  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140bf27e1  xorps   xmm0, xmm0
0x140bf27e4  lea     rax, [rbp+57h+arg_10]
0x140bf27e8  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140bf27ef  mov     [rsp+90h+Disposition], rax; Disposition
0x140bf27f4  xor     r9d, r9d; TitleIndex
0x140bf27f7  mov     [rsp+90h+CreateOptions], 1; CreateOptions
0x140bf27ff  mov     edx, 20019h; DesiredAccess
0x140bf2804  mov     [rsp+90h+Class], 0; Class
0x140bf280d  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140bf2812  call    ZwCreateKey
0x140bf2817  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140bf281b  test    eax, eax
0x140bf281d  jns     short loc_140BF2836
0x140bf281f  call    ZwClose
0x140bf2824  mov     rbx, [rsp+90h+arg_0]
0x140bf282c  add     rsp, 90h
0x140bf2833  pop     rbp
0x140bf2834  retn
0x140bf2836  mov     ebx, cs:WheapPfaLock.PriorityFloorSummary
0x140bf283c  call    ZwClose
0x140bf2841  lea     rdx, aResume; "Resume"
0x140bf2848  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf284c  call    RtlInitUnicodeString
0x140bf2851  mov     [rbp+57h+Data], 0
0x140bf2858  bt      ebx, 14h
0x140bf285c  jb      loc_140BF2E56
0x140bf2862  mov     rcx, [rbp+57h+arg_18]; KeyHandle
0x140bf2866  lea     rax, [rbp+57h+Data]
0x140bf286a  mov     ebx, 4
0x140bf286f  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140bf2873  mov     [rsp+90h+CreateOptions], ebx; DataSize
0x140bf2877  mov     r9d, ebx; Type
0x140bf287a  xor     r8d, r8d; TitleIndex
0x140bf287d  mov     [rsp+90h+Class], rax; Data
0x140bf2882  call    ZwSetValueKey
0x140bf2887  lea     rdx, aWidth; "Width"
0x140bf288e  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf2892  call    RtlInitUnicodeString
0x140bf2897  mov     eax, cs:WheapPfaLock.ForegroundLossTime
0x140bf289d  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140bf28a1  mov     rcx, [rbp+57h+arg_18]; KeyHandle
0x140bf28a5  mov     r9d, ebx; Type
0x140bf28a8  mov     [rbp+57h+Data], eax
0x140bf28ab  xor     r8d, r8d; TitleIndex
0x140bf28ae  lea     rax, [rbp+57h+Data]
0x140bf28b2  mov     [rsp+90h+CreateOptions], ebx; DataSize
0x140bf28b6  mov     [rsp+90h+Class], rax; Data
0x140bf28bb  call    ZwSetValueKey
0x140bf28c0  lea     rdx, aHeight; "Height"
0x140bf28c7  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf28cb  call    RtlInitUnicodeString
0x140bf28d0  mov     eax, dword ptr cs:WheapPfaLock+36Ch
0x140bf28d6  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140bf28da  mov     rcx, [rbp+57h+arg_18]; KeyHandle
0x140bf28de  mov     r9d, ebx; Type
0x140bf28e1  mov     [rbp+57h+Data], eax
0x140bf28e4  xor     r8d, r8d; TitleIndex
0x140bf28e7  lea     rax, [rbp+57h+Data]
0x140bf28eb  mov     [rsp+90h+CreateOptions], ebx; DataSize
0x140bf28ef  mov     [rsp+90h+Class], rax; Data
0x140bf28f4  call    ZwSetValueKey
0x140bf28f9  lea     rdx, aBpp; "BPP"
0x140bf2900  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf2904  call    RtlInitUnicodeString
0x140bf2909  mov     eax, dword ptr cs:WheapPfaLock.MutantListHead.Blink+4
0x140bf290f  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140bf2913  mov     rcx, [rbp+57h+arg_18]; KeyHandle
0x140bf2917  mov     r9d, ebx; Type
0x140bf291a  mov     [rbp+57h+Data], eax
0x140bf291d  xor     r8d, r8d; TitleIndex
0x140bf2920  lea     rax, [rbp+57h+Data]
0x140bf2924  mov     [rsp+90h+CreateOptions], ebx; DataSize
0x140bf2928  mov     [rsp+90h+Class], rax; Data
0x140bf292d  call    ZwSetValueKey
0x140bf2932  lea     rdx, aLogosize; "LogoSize"
0x140bf2939  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf293d  call    RtlInitUnicodeString
0x140bf2942  mov     eax, dword ptr cs:gLoadedDiffHivesLock.___u33+0A8h
0x140bf2948  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140bf294c  mov     rcx, [rbp+57h+arg_18]; KeyHandle
0x140bf2950  mov     r9d, ebx; Type
0x140bf2953  mov     [rbp+57h+Data], eax
0x140bf2956  xor     r8d, r8d; TitleIndex
0x140bf2959  lea     rax, [rbp+57h+Data]
0x140bf295d  mov     [rsp+90h+CreateOptions], ebx; DataSize
0x140bf2961  mov     [rsp+90h+Class], rax; Data
0x140bf2966  call    ZwSetValueKey
0x140bf296b  lea     rdx, aProgressframes; "ProgressFrames"
0x140bf2972  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf2976  call    RtlInitUnicodeString
0x140bf297b  mov     eax, cs:WheapPfaLock.AbCompletedIoQoSBoostCount
0x140bf2981  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140bf2985  mov     rcx, [rbp+57h+arg_18]; KeyHandle
0x140bf2989  mov     r9d, ebx; Type
0x140bf298c  mov     [rbp+57h+Data], eax
0x140bf298f  xor     r8d, r8d; TitleIndex
0x140bf2992  lea     rax, [rbp+57h+Data]
0x140bf2996  mov     [rsp+90h+CreateOptions], ebx; DataSize
0x140bf299a  mov     [rsp+90h+Class], rax; Data
0x140bf299f  call    ZwSetValueKey
0x140bf29a4  lea     rdx, aProgressmemory; "ProgressMemory"
0x140bf29ab  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf29af  call    RtlInitUnicodeString
0x140bf29b4  mov     eax, dword ptr cs:gLoadedDiffHivesLock.___u33+70h
0x140bf29ba  mov     [rbp+57h+Data], eax
0x140bf29bd  lea     rax, [rbp+57h+Data]
0x140bf29c1  mov     [rsp+90h+CreateOptions], ebx; DataSize
0x140bf29c5  mov     rcx, [rbp+57h+arg_18]; KeyHandle
0x140bf29c9  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140bf29cd  mov     r9d, ebx; Type
0x140bf29d0  mov     [rsp+90h+Class], rax; Data
0x140bf29d5  xor     r8d, r8d; TitleIndex
0x140bf29d8  call    ZwSetValueKey
0x140bf29dd  lea     rdx, aProgressprolog_0; "ProgressProlog"
0x140bf29e4  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf29e8  call    RtlInitUnicodeString
0x140bf29ed  imul    rax, cs:WheapPfaLock.ReadOperationCount, 0F4240h
0x140bf29f8  mov     rcx, [rbp+57h+arg_18]; KeyHandle
0x140bf29fc  mov     r9d, ebx; Type
0x140bf29ff  cqo
0x140bf2a01  mov     [rsp+90h+CreateOptions], ebx; DataSize
0x140bf2a05  idiv    cs:qword_140E139C0
0x140bf2a0c  xor     r8d, r8d; TitleIndex
0x140bf2a0f  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140bf2a13  mov     [rbp+57h+Data], eax
0x140bf2a16  lea     rax, [rbp+57h+Data]
0x140bf2a1a  mov     [rsp+90h+Class], rax; Data
0x140bf2a1f  call    ZwSetValueKey
0x140bf2a24  lea     rdx, aProgresslow; "ProgressLow"
0x140bf2a2b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf2a2f  call    RtlInitUnicodeString
0x140bf2a34  imul    rax, cs:qword_140E139B8, 0F4240h
0x140bf2a3f  mov     rcx, [rbp+57h+arg_18]; KeyHandle
0x140bf2a43  mov     r9d, ebx; Type
0x140bf2a46  cqo
0x140bf2a48  mov     [rsp+90h+CreateOptions], ebx; DataSize
0x140bf2a4c  idiv    cs:qword_140E139C0
0x140bf2a53  xor     r8d, r8d; TitleIndex
0x140bf2a56  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140bf2a5a  mov     [rbp+57h+Data], eax
0x140bf2a5d  lea     rax, [rbp+57h+Data]
0x140bf2a61  mov     [rsp+90h+Class], rax; Data
0x140bf2a66  call    ZwSetValueKey
0x140bf2a6b  lea     rdx, aProgresshigh; "ProgressHigh"
0x140bf2a72  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf2a76  call    RtlInitUnicodeString
0x140bf2a7b  imul    rax, cs:WheapPfaLock.MutantListHead.Flink, 0F4240h
0x140bf2a86  mov     rcx, [rbp+57h+arg_18]; KeyHandle
0x140bf2a8a  mov     r9d, ebx; Type
0x140bf2a8d  cqo
0x140bf2a8f  mov     [rsp+90h+CreateOptions], ebx; DataSize
0x140bf2a93  idiv    cs:qword_140E139C0
0x140bf2a9a  xor     r8d, r8d; TitleIndex
0x140bf2a9d  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140bf2aa1  mov     [rbp+57h+Data], eax
0x140bf2aa4  lea     rax, [rbp+57h+Data]
0x140bf2aa8  mov     [rsp+90h+Class], rax; Data
0x140bf2aad  call    ZwSetValueKey
0x140bf2ab2  cmp     qword ptr cs:gLoadedDiffHivesLock.___u33+80h, 0
0x140bf2aba  jz      short loc_140BF2AF8
0x140bf2abc  lea     rdx, aResidentsize; "ResidentSize"
0x140bf2ac3  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf2ac7  call    RtlInitUnicodeString
0x140bf2acc  mov     rax, qword ptr cs:gLoadedDiffHivesLock.___u33+80h
0x140bf2ad3  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140bf2ad7  mov     [rsp+90h+CreateOptions], ebx; DataSize
0x140bf2adb  mov     r9d, ebx; Type
0x140bf2ade  xor     r8d, r8d; TitleIndex
0x140bf2ae1  mov     ecx, [rax]
0x140bf2ae3  lea     rax, [rbp+57h+Data]
0x140bf2ae7  mov     [rbp+57h+Data], ecx
0x140bf2aea  mov     rcx, [rbp+57h+arg_18]; KeyHandle
0x140bf2aee  mov     [rsp+90h+Class], rax; Data
0x140bf2af3  call    ZwSetValueKey
0x140bf2af8  lea     rdx, aProgresstotal; "ProgressTotal"
0x140bf2aff  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf2b03  call    RtlInitUnicodeString
0x140bf2b08  imul    rax, qword ptr cs:WheapPfaLock.PriorityFloorCounts+8, 0F4240h
0x140bf2b13  mov     rcx, [rbp+57h+arg_18]; KeyHandle
0x140bf2b17  mov     r9d, ebx; Type
0x140bf2b1a  cqo
0x140bf2b1c  mov     [rsp+90h+CreateOptions], ebx; DataSize
0x140bf2b20  idiv    cs:qword_140E139C0
0x140bf2b27  xor     r8d, r8d; TitleIndex
0x140bf2b2a  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140bf2b2e  mov     [rbp+57h+Data], eax
0x140bf2b31  lea     rax, [rbp+57h+Data]
0x140bf2b35  mov     [rsp+90h+Class], rax; Data
0x140bf2b3a  call    ZwSetValueKey
0x140bf2b3f  lea     rdx, aProgressmanual_0; "ProgressManual"
0x140bf2b46  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf2b4a  call    RtlInitUnicodeString
0x140bf2b4f  imul    rax, qword ptr cs:WheapPfaLock.PriorityFloorCounts+10h, 0F4240h
0x140bf2b5a  mov     rcx, [rbp+57h+arg_18]; KeyHandle
0x140bf2b5e  mov     r9d, ebx; Type
0x140bf2b61  cqo
0x140bf2b63  mov     [rsp+90h+CreateOptions], ebx; DataSize
0x140bf2b67  idiv    cs:qword_140E139C0
0x140bf2b6e  xor     r8d, r8d; TitleIndex
0x140bf2b71  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140bf2b75  mov     [rbp+57h+Data], eax
0x140bf2b78  lea     rax, [rbp+57h+Data]
0x140bf2b7c  mov     [rsp+90h+Class], rax; Data
0x140bf2b81  call    ZwSetValueKey
0x140bf2b86  lea     rdx, aFadeprolog; "FadeProlog"
0x140bf2b8d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf2b91  call    RtlInitUnicodeString
0x140bf2b96  imul    rax, qword ptr cs:WheapPfaLock.___u77+8, 0F4240h
0x140bf2ba1  mov     rcx, [rbp+57h+arg_18]; KeyHandle
0x140bf2ba5  mov     r9d, ebx; Type
0x140bf2ba8  cqo
0x140bf2baa  mov     [rsp+90h+CreateOptions], ebx; DataSize
0x140bf2bae  idiv    cs:qword_140E139C0
0x140bf2bb5  xor     r8d, r8d; TitleIndex
0x140bf2bb8  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140bf2bbc  mov     [rbp+57h+Data], eax
0x140bf2bbf  lea     rax, [rbp+57h+Data]
0x140bf2bc3  mov     [rsp+90h+Class], rax; Data
0x140bf2bc8  call    ZwSetValueKey
0x140bf2bcd  lea     rdx, aFadeoverlap; "FadeOverlap"
0x140bf2bd4  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf2bd8  call    RtlInitUnicodeString
0x140bf2bdd  mov     eax, dword ptr cs:WheapPfaLock.OtherOperationCount
0x140bf2be3  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140bf2be7  mov     rcx, [rbp+57h+arg_18]; KeyHandle
0x140bf2beb  mov     r9d, ebx; Type
0x140bf2bee  mov     [rbp+57h+Data], eax
0x140bf2bf1  xor     r8d, r8d; TitleIndex
0x140bf2bf4  lea     rax, [rbp+57h+Data]
0x140bf2bf8  mov     [rsp+90h+CreateOptions], ebx; DataSize
0x140bf2bfc  mov     [rsp+90h+Class], rax; Data
0x140bf2c01  call    ZwSetValueKey
0x140bf2c06  lea     rdx, aFadeio; "FadeIo"
0x140bf2c0d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf2c11  call    RtlInitUnicodeString
0x140bf2c16  mov     eax, cs:WheapPfaLock.AbCompletedIoBoostCount
0x140bf2c1c  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140bf2c20  mov     rcx, [rbp+57h+arg_18]; KeyHandle
0x140bf2c24  mov     r9d, ebx; Type
0x140bf2c27  mov     [rbp+57h+Data], eax
0x140bf2c2a  xor     r8d, r8d; TitleIndex
0x140bf2c2d  lea     rax, [rbp+57h+Data]
0x140bf2c31  mov     [rsp+90h+CreateOptions], ebx; DataSize
0x140bf2c35  mov     [rsp+90h+Class], rax; Data
0x140bf2c3a  call    ZwSetValueKey
0x140bf2c3f  lea     rdx, aFadecpu; "FadeCpu"
0x140bf2c46  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140bf2c4a  call    RtlInitUnicodeString
0x140bf2c4f  mov     eax, dword ptr cs:WheapPfaLock.MutantListHead.Blink
0x140bf2c55  mov     r9d, ebx; Type
0x140bf2c58  mov     [rbp+57h+Data], eax
0x140bf2c5b  xor     r8d, r8d; TitleIndex
0x140bf2c5e  lea     rax, [rbp+57h+Data]
0x140bf2c62  mov     [rsp+90h+CreateOptions], ebx; DataSize
0x140bf2c66  mov     [rsp+90h+Class], rax; Data
0x140bf2c6b  mov     rcx, [rbp+57h+arg_18]; KeyHandle
0x140bf2c6f  lea     rdx, [rbp+57h+DestinationString]; ValueName
0x140bf2c73  call    ZwSetValueKey
0x140bf2c78  lea     rdx, aFadeframes; "FadeFrames"
  ... truncated ...
```
