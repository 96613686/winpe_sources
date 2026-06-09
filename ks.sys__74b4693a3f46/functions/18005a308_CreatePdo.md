# CreatePdo

- ea: `0x18005a308`
- end: `0x18005a52e`
- name: `CreatePdo`
- size: `550`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180035ad0`
- `0x180059858`
- `0x180059c50`

## callees

- `0x18000ae68`
- `0x18000c630`
- `0x180019b80`
- `0x18005a308`
- `0x18005a534`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18005a38c`
- `ntoskrnl!RtlInitUnicodeString` at `0x18005a38c`
- `ntoskrnl!PsGetHostSilo` at `0x18005a398`
- `ntoskrnl!PsGetHostSilo` at `0x18005a398`
- `ntoskrnl!IoDeleteDevice` at `0x18005a4f0`
- `ntoskrnl!IoDeleteDevice` at `0x18005a4f0`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x18005a3a7`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x18005a3a7`
- `ntoskrnl!IoCreateDevice` at `0x18005a3dc`
- `ntoskrnl!IoCreateDevice` at `0x18005a3dc`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x18005a3ed`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x18005a3ed`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18005a411`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18005a411`
- `HAL!KeQueryPerformanceCounter` at `0x18005a460`
- `HAL!KeQueryPerformanceCounter` at `0x18005a460`

## pseudocode

```c
__int64 __fastcall CreatePdo(__int64 a1, LARGE_INTEGER *a2, PDEVICE_OBJECT *a3)
{
  __int64 v3; // rax
  struct _DRIVER_OBJECT *v6; // rdi
  __int64 HostSilo; // rax
  __int64 v9; // rbx
  NTSTATUS v10; // edi
  _OWORD *PoolWithTag; // rax
  int v12; // edx
  unsigned int v13; // ebx
  PDEVICE_OBJECT DeviceObject; // [rsp+40h] [rbp-89h] BYREF
  UNICODE_STRING DestinationString; // [rsp+48h] [rbp-81h] BYREF
  wchar_t pszDest[64]; // [rsp+60h] [rbp-69h] BYREF

  v3 = *(_QWORD *)(a1 + 112);
  DeviceObject = 0;
  DestinationString = 0;
  v6 = *(struct _DRIVER_OBJECT **)(v3 + 8);
  a2[7].LowPart = 1;
  if ( StringCbPrintfW(pszDest, 0x80u, L"\\Device\\KSENUM#%08x", (unsigned int)_InterlockedIncrement(&dword_1800282A0)) < 0 )
    return 3221225626LL;
  RtlInitUnicodeString(&DestinationString, pszDest);
  HostSilo = PsGetHostSilo();
  v9 = PsAttachSiloToCurrentThread(HostSilo);
  v10 = IoCreateDevice(v6, 8u, &DestinationString, 0x22u, 0, 0, &DeviceObject);
  PsDetachSiloFromCurrentThread(v9);
  if ( v10 < 0 )
    return (unsigned int)v10;
  PoolWithTag = ExAllocatePoolWithTag(NonPagedPoolNx, 0x38u, 0x64705753u);
  if ( !PoolWithTag )
  {
    IoDeleteDevice(DeviceObject);
    return 3221225626LL;
  }
  *(_QWORD *)DeviceObject->DeviceExtension = PoolWithTag;
  *PoolWithTag = 0;
  PoolWithTag[1] = 0;
  PoolWithTag[2] = 0;
  *((_QWORD *)PoolWithTag + 6) = 0;
  *((_QWORD *)PoolWithTag + 3) = DeviceObject;
  *((_QWORD *)PoolWithTag + 4) = a2;
  *((_QWORD *)PoolWithTag + 5) = a1;
  a2[10].LowPart = 0;
  a2[14] = KeQueryPerformanceCounter(0);
  a2[16].QuadPart = 30LL * *(_QWORD *)(a1 + 744);
  DeviceObject->Flags |= 0x2000u;
  DeviceObject->Flags &= ~0x80u;
  v13 = QueueSweeperTimer(a1, -150000000);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v12) = 5;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v12,
        1,
        86,
        (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
        v13);
    }
  }
  *a3 = DeviceObject;
  return v13;
}

```

## disassembly

```asm
0x18005a308  push    rbp
0x18005a30a  push    rbx
0x18005a30b  push    rsi
0x18005a30c  push    rdi
0x18005a30d  push    r12
0x18005a30f  push    r14
0x18005a311  push    r15
0x18005a313  lea     rbp, [rsp-27h]
0x18005a318  sub     rsp, 0F0h
0x18005a31f  mov     rax, cs:__security_cookie
0x18005a326  xor     rax, rsp
0x18005a329  mov     [rbp+57h+var_40], rax
0x18005a32d  mov     rax, [rcx+70h]
0x18005a331  xor     r12d, r12d
0x18005a334  xorps   xmm0, xmm0
0x18005a337  mov     [rsp+120h+var_E0], r12
0x18005a33c  movups  xmmword ptr [rsp+120h+DestinationString.Length], xmm0
0x18005a341  mov     r14, r8
0x18005a344  mov     rsi, rdx
0x18005a347  mov     rdi, [rax+8]
0x18005a34b  lea     r9d, [r12+1]
0x18005a350  mov     dword ptr [rdx+38h], 1
0x18005a357  mov     r15, rcx
0x18005a35a  lock xadd cs:dword_1800282A0, r9d
0x18005a363  inc     r9d
0x18005a366  lea     r8, aDeviceKsenum08; "\\Device\\KSENUM#%08x"
0x18005a36d  mov     edx, 80h; cbDest
0x18005a372  lea     rcx, [rbp+57h+pszDest]; pszDest
0x18005a376  call    StringCbPrintfW
0x18005a37b  test    eax, eax
0x18005a37d  js      loc_18005A4FC
0x18005a383  lea     rdx, [rbp+57h+pszDest]; SourceString
0x18005a387  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x18005a38c  call    cs:__imp_RtlInitUnicodeString
0x18005a393  nop     dword ptr [rax+rax+00h]
0x18005a398  call    cs:__imp_PsGetHostSilo
0x18005a39f  nop     dword ptr [rax+rax+00h]
0x18005a3a4  mov     rcx, rax
0x18005a3a7  call    cs:__imp_PsAttachSiloToCurrentThread
0x18005a3ae  nop     dword ptr [rax+rax+00h]
0x18005a3b3  lea     r9d, [r12+22h]; DeviceType
0x18005a3b8  mov     rcx, rdi; DriverObject
0x18005a3bb  mov     rbx, rax
0x18005a3be  lea     r8, [rsp+120h+DestinationString]; DeviceName
0x18005a3c3  lea     rax, [rsp+120h+var_E0]
0x18005a3c8  mov     [rsp+120h+DeviceObject], rax; DeviceObject
0x18005a3cd  lea     edx, [r12+8]; DeviceExtensionSize
0x18005a3d2  mov     [rsp+120h+Exclusive], r12b; Exclusive
0x18005a3d7  mov     [rsp+120h+DeviceCharacteristics], r12d; DeviceCharacteristics
0x18005a3dc  call    cs:__imp_IoCreateDevice
0x18005a3e3  nop     dword ptr [rax+rax+00h]
0x18005a3e8  mov     rcx, rbx
0x18005a3eb  mov     edi, eax
0x18005a3ed  call    cs:__imp_PsDetachSiloFromCurrentThread
0x18005a3f4  nop     dword ptr [rax+rax+00h]
0x18005a3f9  test    edi, edi
0x18005a3fb  js      loc_18005A503
0x18005a401  lea     edx, [r12+38h]; NumberOfBytes
0x18005a406  mov     ecx, 200h; PoolType
0x18005a40b  mov     r8d, 64705753h; Tag
0x18005a411  call    cs:__imp_ExAllocatePoolWithTag
0x18005a418  nop     dword ptr [rax+rax+00h]
0x18005a41d  mov     rdx, rax
0x18005a420  test    rax, rax
0x18005a423  jz      loc_18005A4EB
0x18005a429  mov     rax, [rsp+120h+var_E0]
0x18005a42e  xorps   xmm0, xmm0
0x18005a431  mov     rcx, [rax+40h]
0x18005a435  xor     eax, eax
0x18005a437  mov     [rcx], rdx
0x18005a43a  xor     ecx, ecx; PerformanceFrequency
0x18005a43c  movups  xmmword ptr [rdx], xmm0
0x18005a43f  movups  xmmword ptr [rdx+10h], xmm0
0x18005a443  movups  xmmword ptr [rdx+20h], xmm0
0x18005a447  mov     [rdx+30h], rax
0x18005a44b  mov     rax, [rsp+120h+var_E0]
0x18005a450  mov     [rdx+18h], rax
0x18005a454  mov     [rdx+20h], rsi
0x18005a458  mov     [rdx+28h], r15
0x18005a45c  mov     [rsi+50h], r12d
0x18005a460  call    cs:__imp_KeQueryPerformanceCounter
0x18005a467  nop     dword ptr [rax+rax+00h]
0x18005a46c  mov     [rsi+70h], rax
0x18005a470  mov     rdx, 0FFFFFFFFF70F2E80h
0x18005a477  mov     rcx, r15
0x18005a47a  imul    rax, [r15+2E8h], 1Eh
0x18005a482  mov     [rsi+80h], rax
0x18005a489  mov     rax, [rsp+120h+var_E0]
0x18005a48e  bts     dword ptr [rax+30h], 0Dh
0x18005a493  mov     rax, [rsp+120h+var_E0]
0x18005a498  btr     dword ptr [rax+30h], 7
0x18005a49d  call    QueueSweeperTimer
0x18005a4a2  mov     ebx, eax
0x18005a4a4  lea     rax, WPP_RECORDER_INITIALIZED
0x18005a4ab  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005a4b2  jz      short loc_18005A4C2
0x18005a4b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a4bb  cmp     [rcx+48h], r12w
0x18005a4c0  jnz     short loc_18005A507
0x18005a4c2  mov     rax, [rsp+120h+var_E0]
0x18005a4c7  mov     [r14], rax
0x18005a4ca  mov     eax, ebx
0x18005a4cc  mov     rcx, [rbp+57h+var_40]
0x18005a4d0  xor     rcx, rsp; StackCookie
0x18005a4d3  call    __security_check_cookie
0x18005a4d8  add     rsp, 0F0h
0x18005a4df  pop     r15
0x18005a4e1  pop     r14
0x18005a4e3  pop     r12
0x18005a4e5  pop     rdi
0x18005a4e6  pop     rsi
0x18005a4e7  pop     rbx
0x18005a4e8  pop     rbp
0x18005a4e9  retn
0x18005a4eb  mov     rcx, [rsp+120h+var_E0]; DeviceObject
0x18005a4f0  call    cs:__imp_IoDeleteDevice
0x18005a4f7  nop     dword ptr [rax+rax+00h]
0x18005a4fc  mov     eax, 0C000009Ah
0x18005a501  jmp     short loc_18005A4CC
0x18005a503  mov     eax, edi
0x18005a505  jmp     short loc_18005A4CC
0x18005a507  mov     rcx, [rcx+40h]
0x18005a50b  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x18005a512  mov     r9d, 56h ; 'V'
0x18005a518  mov     dword ptr [rsp+120h+Exclusive], ebx
0x18005a51c  mov     dl, 5
0x18005a51e  mov     qword ptr [rsp+120h+DeviceCharacteristics], rax
0x18005a523  lea     r8d, [r9-55h]
0x18005a527  call    WPP_RECORDER_SF_D
0x18005a52c  jmp     short loc_18005A4C2
```
