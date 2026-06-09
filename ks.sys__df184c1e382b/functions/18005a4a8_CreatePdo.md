# CreatePdo

- ea: `0x18005a4a8`
- end: `0x18005a6ce`
- name: `CreatePdo`
- size: `550`
- prototype: `__int64 __fastcall(__int64, LARGE_INTEGER *, PDEVICE_OBJECT *)`
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180035be0`
- `0x1800599f8`
- `0x180059df0`

## callees

- `0x18000ae68`
- `0x18000c630`
- `0x180019bd0`
- `0x18005a4a8`
- `0x18005a6d4`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18005a52c`
- `ntoskrnl!RtlInitUnicodeString` at `0x18005a52c`
- `ntoskrnl!PsGetHostSilo` at `0x18005a538`
- `ntoskrnl!PsGetHostSilo` at `0x18005a538`
- `ntoskrnl!IoDeleteDevice` at `0x18005a690`
- `ntoskrnl!IoDeleteDevice` at `0x18005a690`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x18005a547`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x18005a547`
- `ntoskrnl!IoCreateDevice` at `0x18005a57c`
- `ntoskrnl!IoCreateDevice` at `0x18005a57c`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x18005a58d`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x18005a58d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18005a5b1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18005a5b1`
- `HAL!KeQueryPerformanceCounter` at `0x18005a600`
- `HAL!KeQueryPerformanceCounter` at `0x18005a600`

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
  __int64 Exclusive; // [rsp+28h] [rbp-A1h]
  PDEVICE_OBJECT DeviceObject; // [rsp+40h] [rbp-89h] BYREF
  UNICODE_STRING DestinationString; // [rsp+48h] [rbp-81h] BYREF
  wchar_t pszDest[64]; // [rsp+60h] [rbp-69h] BYREF

  v3 = *(_QWORD *)(a1 + 112);
  DeviceObject = 0;
  DestinationString = 0;
  v6 = *(struct _DRIVER_OBJECT **)(v3 + 8);
  a2[7].LowPart = 1;
  if ( StringCbPrintfW(pszDest, 0x80u, L"\\Device\\KSENUM#%08x", (unsigned int)_InterlockedIncrement(&dword_180028320)) < 0 )
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
      LODWORD(Exclusive) = v13;
      LOBYTE(v12) = 5;
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v12,
        1,
        86,
        (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
        Exclusive);
    }
  }
  *a3 = DeviceObject;
  return v13;
}

```

## disassembly

```asm
0x18005a4a8  push    rbp
0x18005a4aa  push    rbx
0x18005a4ab  push    rsi
0x18005a4ac  push    rdi
0x18005a4ad  push    r12
0x18005a4af  push    r14
0x18005a4b1  push    r15
0x18005a4b3  lea     rbp, [rsp-27h]
0x18005a4b8  sub     rsp, 0F0h
0x18005a4bf  mov     rax, cs:__security_cookie
0x18005a4c6  xor     rax, rsp
0x18005a4c9  mov     [rbp+57h+var_40], rax
0x18005a4cd  mov     rax, [rcx+70h]
0x18005a4d1  xor     r12d, r12d
0x18005a4d4  xorps   xmm0, xmm0
0x18005a4d7  mov     [rsp+120h+var_E0], r12
0x18005a4dc  movups  xmmword ptr [rsp+120h+DestinationString.Length], xmm0
0x18005a4e1  mov     r14, r8
0x18005a4e4  mov     rsi, rdx
0x18005a4e7  mov     rdi, [rax+8]
0x18005a4eb  lea     r9d, [r12+1]
0x18005a4f0  mov     dword ptr [rdx+38h], 1
0x18005a4f7  mov     r15, rcx
0x18005a4fa  lock xadd cs:dword_180028320, r9d
0x18005a503  inc     r9d
0x18005a506  lea     r8, aDeviceKsenum08; "\\Device\\KSENUM#%08x"
0x18005a50d  mov     edx, 80h; cbDest
0x18005a512  lea     rcx, [rbp+57h+pszDest]; pszDest
0x18005a516  call    StringCbPrintfW
0x18005a51b  test    eax, eax
0x18005a51d  js      loc_18005A69C
0x18005a523  lea     rdx, [rbp+57h+pszDest]; SourceString
0x18005a527  lea     rcx, [rsp+120h+DestinationString]; DestinationString
0x18005a52c  call    cs:__imp_RtlInitUnicodeString
0x18005a533  nop     dword ptr [rax+rax+00h]
0x18005a538  call    cs:__imp_PsGetHostSilo
0x18005a53f  nop     dword ptr [rax+rax+00h]
0x18005a544  mov     rcx, rax
0x18005a547  call    cs:__imp_PsAttachSiloToCurrentThread
0x18005a54e  nop     dword ptr [rax+rax+00h]
0x18005a553  lea     r9d, [r12+22h]; DeviceType
0x18005a558  mov     rcx, rdi; DriverObject
0x18005a55b  mov     rbx, rax
0x18005a55e  lea     r8, [rsp+120h+DestinationString]; DeviceName
0x18005a563  lea     rax, [rsp+120h+var_E0]
0x18005a568  mov     [rsp+120h+DeviceObject], rax; DeviceObject
0x18005a56d  lea     edx, [r12+8]; DeviceExtensionSize
0x18005a572  mov     [rsp+120h+Exclusive], r12b; Exclusive
0x18005a577  mov     [rsp+120h+DeviceCharacteristics], r12d; DeviceCharacteristics
0x18005a57c  call    cs:__imp_IoCreateDevice
0x18005a583  nop     dword ptr [rax+rax+00h]
0x18005a588  mov     rcx, rbx
0x18005a58b  mov     edi, eax
0x18005a58d  call    cs:__imp_PsDetachSiloFromCurrentThread
0x18005a594  nop     dword ptr [rax+rax+00h]
0x18005a599  test    edi, edi
0x18005a59b  js      loc_18005A6A3
0x18005a5a1  lea     edx, [r12+38h]; NumberOfBytes
0x18005a5a6  mov     ecx, 200h; PoolType
0x18005a5ab  mov     r8d, 64705753h; Tag
0x18005a5b1  call    cs:__imp_ExAllocatePoolWithTag
0x18005a5b8  nop     dword ptr [rax+rax+00h]
0x18005a5bd  mov     rdx, rax
0x18005a5c0  test    rax, rax
0x18005a5c3  jz      loc_18005A68B
0x18005a5c9  mov     rax, [rsp+120h+var_E0]
0x18005a5ce  xorps   xmm0, xmm0
0x18005a5d1  mov     rcx, [rax+40h]
0x18005a5d5  xor     eax, eax
0x18005a5d7  mov     [rcx], rdx
0x18005a5da  xor     ecx, ecx; PerformanceFrequency
0x18005a5dc  movups  xmmword ptr [rdx], xmm0
0x18005a5df  movups  xmmword ptr [rdx+10h], xmm0
0x18005a5e3  movups  xmmword ptr [rdx+20h], xmm0
0x18005a5e7  mov     [rdx+30h], rax
0x18005a5eb  mov     rax, [rsp+120h+var_E0]
0x18005a5f0  mov     [rdx+18h], rax
0x18005a5f4  mov     [rdx+20h], rsi
0x18005a5f8  mov     [rdx+28h], r15
0x18005a5fc  mov     [rsi+50h], r12d
0x18005a600  call    cs:__imp_KeQueryPerformanceCounter
0x18005a607  nop     dword ptr [rax+rax+00h]
0x18005a60c  mov     [rsi+70h], rax
0x18005a610  mov     rdx, 0FFFFFFFFF70F2E80h
0x18005a617  mov     rcx, r15
0x18005a61a  imul    rax, [r15+2E8h], 1Eh
0x18005a622  mov     [rsi+80h], rax
0x18005a629  mov     rax, [rsp+120h+var_E0]
0x18005a62e  bts     dword ptr [rax+30h], 0Dh
0x18005a633  mov     rax, [rsp+120h+var_E0]
0x18005a638  btr     dword ptr [rax+30h], 7
0x18005a63d  call    QueueSweeperTimer
0x18005a642  mov     ebx, eax
0x18005a644  lea     rax, WPP_RECORDER_INITIALIZED
0x18005a64b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005a652  jz      short loc_18005A662
0x18005a654  mov     rcx, cs:WPP_GLOBAL_Control
0x18005a65b  cmp     [rcx+48h], r12w
0x18005a660  jnz     short loc_18005A6A7
0x18005a662  mov     rax, [rsp+120h+var_E0]
0x18005a667  mov     [r14], rax
0x18005a66a  mov     eax, ebx
0x18005a66c  mov     rcx, [rbp+57h+var_40]
0x18005a670  xor     rcx, rsp; StackCookie
0x18005a673  call    __security_check_cookie
0x18005a678  add     rsp, 0F0h
0x18005a67f  pop     r15
0x18005a681  pop     r14
0x18005a683  pop     r12
0x18005a685  pop     rdi
0x18005a686  pop     rsi
0x18005a687  pop     rbx
0x18005a688  pop     rbp
0x18005a689  retn
0x18005a68b  mov     rcx, [rsp+120h+var_E0]; DeviceObject
0x18005a690  call    cs:__imp_IoDeleteDevice
0x18005a697  nop     dword ptr [rax+rax+00h]
0x18005a69c  mov     eax, 0C000009Ah
0x18005a6a1  jmp     short loc_18005A66C
0x18005a6a3  mov     eax, edi
0x18005a6a5  jmp     short loc_18005A66C
0x18005a6a7  mov     rcx, [rcx+40h]
0x18005a6ab  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x18005a6b2  mov     r9d, 56h ; 'V'
0x18005a6b8  mov     dword ptr [rsp+120h+Exclusive], ebx
0x18005a6bc  mov     dl, 5
0x18005a6be  mov     qword ptr [rsp+120h+DeviceCharacteristics], rax
0x18005a6c3  lea     r8d, [r9-55h]
0x18005a6c7  call    WPP_RECORDER_SF_D
0x18005a6cc  jmp     short loc_18005A662
```
