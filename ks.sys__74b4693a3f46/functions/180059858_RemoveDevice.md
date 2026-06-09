# RemoveDevice

- ea: `0x180059858`
- end: `0x180059c42`
- name: `RemoveDevice`
- size: `1002`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005a6f0`

## callees

- `0x18000b7bc`
- `0x18000dddc`
- `0x1800597dc`
- `0x180059858`
- `0x18005a0c0`
- `0x18005a308`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1800598b0`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1800598b0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18005989d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18005989d`
- `ntoskrnl!IoDeleteDevice` at `0x18005998c`
- `ntoskrnl!IoDeleteDevice` at `0x180059ba9`
- `ntoskrnl!IoDeleteDevice` at `0x18005998c`
- `ntoskrnl!IoDeleteDevice` at `0x180059ba9`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x180059a2e`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x180059bf5`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x180059a2e`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x180059bf5`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x18005999b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x180059a10`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x180059b1d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x180059bd7`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x18005999b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x180059a10`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x180059b1d`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x180059bd7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800599a7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180059a1c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180059b29`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180059be3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1800599a7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180059a1c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180059b29`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180059be3`
- `ntoskrnl!IofCompleteRequest` at `0x180059963`
- `ntoskrnl!IofCompleteRequest` at `0x180059963`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800598d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x180059976`
- `ntoskrnl!ExFreePoolWithTag` at `0x180059bba`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800598d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x180059976`
- `ntoskrnl!ExFreePoolWithTag` at `0x180059bba`

## pseudocode

```c
__int64 __fastcall RemoveDevice(PDEVICE_OBJECT DeviceObject)
{
  __int64 *v2; // rdx
  PVOID DeviceExtension; // rax
  void *v4; // r12
  LARGE_INTEGER *v5; // rbx
  __int64 v6; // r14
  __int64 v7; // rdx
  int LowPart; // eax
  void *QuadPart; // rcx
  ULONG v10; // eax
  LARGE_INTEGER *v11; // rdi
  LARGE_INTEGER *v12; // rsi
  LONGLONG *v13; // rax
  LONGLONG v14; // rcx
  int v15; // edx
  PDEVICE_OBJECT v16; // rcx
  int v17; // r9d
  int v19; // edx

  v2 = WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v2,
      1,
      47,
      (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids);
  }
  DeviceExtension = DeviceObject->DeviceExtension;
  v4 = *(void **)DeviceExtension;
  v5 = *(LARGE_INTEGER **)(*(_QWORD *)DeviceExtension + 32LL);
  v6 = *(_QWORD *)(*(_QWORD *)DeviceExtension + 40LL);
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v6 + 24));
  LowPart = v5[7].LowPart;
  if ( LowPart < 4 && LowPart )
    CompletePendingIo(v5, v7, 3221225524LL);
  QuadPart = (void *)v5[11].QuadPart;
  if ( QuadPart )
  {
    ExFreePoolWithTag(QuadPart, 0);
    v5[11].QuadPart = 0;
  }
  v10 = v5[10].LowPart;
  v5[7].LowPart = 0;
  if ( !v10 )
  {
    v5[10].LowPart = 1;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v7) = 5;
      WPP_RECORDER_SF_q(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        1,
        48,
        (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
        v5[6].QuadPart);
    }
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v6 + 24));
    KeLeaveCriticalRegion();
    IoInvalidateDeviceRelations(*(PDEVICE_OBJECT *)(v6 + 96), BusRelations);
    return 0;
  }
  if ( v10 == 1 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v7) = 5;
      WPP_RECORDER_SF_q(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        1,
        49,
        (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
        v5[6].QuadPart);
    }
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v6 + 24));
    KeLeaveCriticalRegion();
    return 0;
  }
  v11 = v5 + 4;
  v12 = v5 + 6;
  if ( (LARGE_INTEGER *)v11->QuadPart == v11 )
    goto LABEL_8;
  if ( (int)CreatePdo(v6, v5, (PDEVICE_OBJECT *)&v5[6]) < 0 )
  {
    v5[10].LowPart = 2;
LABEL_8:
    v12->QuadPart = 0;
    while ( 1 )
    {
      v13 = (LONGLONG *)v11->QuadPart;
      if ( (LARGE_INTEGER *)v11->QuadPart == v11 )
        break;
      if ( (LARGE_INTEGER *)v13[1] != v11 || (v14 = *v13, *(LONGLONG **)(*v13 + 8) != v13) )
        __fastfail(3u);
      v11->QuadPart = v14;
      *(_QWORD *)(v14 + 8) = v11;
      *((_DWORD *)v13 - 30) = -1073741772;
      IofCompleteRequest((PIRP)(v13 - 21), 0);
    }
    ExFreePoolWithTag(v4, 0);
    *(_QWORD *)DeviceObject->DeviceExtension = 0;
    IoDeleteDevice(DeviceObject);
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v6 + 24));
    KeLeaveCriticalRegion();
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v16 = WPP_GLOBAL_Control;
      if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
      {
        v17 = 52;
LABEL_16:
        LOBYTE(v15) = 5;
        WPP_RECORDER_SF_(v16->DeviceExtension, v15, 1, v17, (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids);
        return 0;
      }
    }
    return 0;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
  {
    LOBYTE(v19) = 5;
    WPP_RECORDER_SF_q(
      WPP_GLOBAL_Control->DeviceExtension,
      v19,
      1,
      50,
      (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
      v12->QuadPart);
  }
  *(_QWORD *)DeviceObject->DeviceExtension = 0;
  IoDeleteDevice(DeviceObject);
  ExFreePoolWithTag(v4, 0);
  v5[16] = v5[15];
  v5[10].LowPart = 0;
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v6 + 24));
  KeLeaveCriticalRegion();
  IoInvalidateDeviceRelations(*(PDEVICE_OBJECT *)(v6 + 96), BusRelations);
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v16 = WPP_GLOBAL_Control;
    if ( LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      v17 = 51;
      goto LABEL_16;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180059858  push    rbx
0x18005985a  push    rbp
0x18005985b  push    rsi
0x18005985c  push    rdi
0x18005985d  push    r12
0x18005985f  push    r13
0x180059861  push    r14
0x180059863  push    r15
0x180059865  sub     rsp, 38h
0x180059869  mov     r13, rcx
0x18005986c  xor     edi, edi
0x18005986e  lea     rax, WPP_RECORDER_INITIALIZED
0x180059875  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18005987c  lea     rdx, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180059883  lea     esi, [rdi+1]
0x180059886  jnz     loc_180059A4E
0x18005988c  mov     rax, [r13+40h]
0x180059890  mov     r12, [rax]
0x180059893  mov     rbx, [r12+20h]
0x180059898  mov     r14, [r12+28h]
0x18005989d  call    cs:__imp_KeEnterCriticalRegion
0x1800598a4  nop     dword ptr [rax+rax+00h]
0x1800598a9  lea     rbp, [r14+18h]
0x1800598ad  mov     rcx, rbp; FastMutex
0x1800598b0  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1800598b7  nop     dword ptr [rax+rax+00h]
0x1800598bc  mov     eax, [rbx+38h]
0x1800598bf  mov     r15d, 0C0000034h
0x1800598c5  cmp     eax, 4
0x1800598c8  jl      loc_180059A7D
0x1800598ce  mov     rcx, [rbx+58h]; P
0x1800598d2  test    rcx, rcx
0x1800598d5  jz      short loc_1800598E9
0x1800598d7  xor     edx, edx; Tag
0x1800598d9  call    cs:__imp_ExFreePoolWithTag
0x1800598e0  nop     dword ptr [rax+rax+00h]
0x1800598e5  mov     [rbx+58h], rdi
0x1800598e9  mov     eax, [rbx+50h]
0x1800598ec  mov     [rbx+38h], edi
0x1800598ef  test    eax, eax
0x1800598f1  jz      loc_1800599F6
0x1800598f7  cmp     eax, esi
0x1800598f9  jz      loc_180059AD4
0x1800598ff  lea     rdi, [rbx+20h]
0x180059903  lea     rsi, [rbx+30h]
0x180059907  cmp     [rdi], rdi
0x18005990a  jnz     loc_180059B3A
0x180059910  xor     r14d, r14d
0x180059913  mov     [rsi], r14
0x180059916  mov     rax, [rdi]
0x180059919  cmp     rax, rdi
0x18005991c  jz      short loc_180059971
0x18005991e  cmp     [rax+8], rdi
0x180059922  jnz     loc_180059C3B
0x180059928  mov     rcx, [rax]
0x18005992b  cmp     [rcx+8], rax
0x18005992f  jnz     loc_180059C3B
0x180059935  mov     [rdi], rcx
0x180059938  lea     rsi, [rax-0A8h]
0x18005993f  mov     [rcx+8], rdi
0x180059943  cmp     r15d, 104h
0x18005994a  jnz     short loc_18005995A
0x18005994c  mov     rdx, rbx
0x18005994f  mov     rcx, rsi
0x180059952  call    IssueReparseForIrp
0x180059957  mov     r15d, eax
0x18005995a  xor     edx, edx; PriorityBoost
0x18005995c  mov     [rsi+30h], r15d
0x180059960  mov     rcx, rsi; Irp
0x180059963  call    cs:__imp_IofCompleteRequest
0x18005996a  nop     dword ptr [rax+rax+00h]
0x18005996f  jmp     short loc_180059916
0x180059971  xor     edx, edx; Tag
0x180059973  mov     rcx, r12; P
0x180059976  call    cs:__imp_ExFreePoolWithTag
0x18005997d  nop     dword ptr [rax+rax+00h]
0x180059982  mov     rax, [r13+40h]
0x180059986  mov     rcx, r13; DeviceObject
0x180059989  mov     [rax], r14
0x18005998c  call    cs:__imp_IoDeleteDevice
0x180059993  nop     dword ptr [rax+rax+00h]
0x180059998  mov     rcx, rbp; FastMutex
0x18005999b  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1800599a2  nop     dword ptr [rax+rax+00h]
0x1800599a7  call    cs:__imp_KeLeaveCriticalRegion
0x1800599ae  nop     dword ptr [rax+rax+00h]
0x1800599b3  lea     r15, WPP_RECORDER_INITIALIZED
0x1800599ba  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1800599c1  jz      short loc_180059A3A
0x1800599c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800599ca  cmp     [rcx+48h], r14w
0x1800599cf  jz      short loc_180059A3A
0x1800599d1  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x1800599d8  mov     r9d, 34h ; '4'
0x1800599de  mov     [rsp+78h+var_58], rax
0x1800599e3  mov     rcx, [rcx+40h]
0x1800599e7  mov     r8d, 1
0x1800599ed  mov     dl, 5
0x1800599ef  call    WPP_RECORDER_SF_
0x1800599f4  jmp     short loc_180059A3A
0x1800599f6  mov     [rbx+50h], esi
0x1800599f9  lea     r15, WPP_RECORDER_INITIALIZED
0x180059a00  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180059a07  jnz     loc_180059A95
0x180059a0d  mov     rcx, rbp; FastMutex
0x180059a10  call    cs:__imp_ExReleaseFastMutexUnsafe
0x180059a17  nop     dword ptr [rax+rax+00h]
0x180059a1c  call    cs:__imp_KeLeaveCriticalRegion
0x180059a23  nop     dword ptr [rax+rax+00h]
0x180059a28  mov     rcx, [r14+60h]; DeviceObject
0x180059a2c  xor     edx, edx; Type
0x180059a2e  call    cs:__imp_IoInvalidateDeviceRelations
0x180059a35  nop     dword ptr [rax+rax+00h]
0x180059a3a  xor     eax, eax
0x180059a3c  add     rsp, 38h
0x180059a40  pop     r15
0x180059a42  pop     r14
0x180059a44  pop     r13
0x180059a46  pop     r12
0x180059a48  pop     rdi
0x180059a49  pop     rsi
0x180059a4a  pop     rbp
0x180059a4b  pop     rbx
0x180059a4c  retn
0x180059a4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180059a55  cmp     [rcx+48h], di
0x180059a59  jz      loc_18005988C
0x180059a5f  mov     rcx, [rcx+40h]
0x180059a63  mov     r9d, 2Fh ; '/'
0x180059a69  mov     [rsp+78h+var_58], rdx
0x180059a6e  mov     r8d, esi
0x180059a71  mov     dl, 5
0x180059a73  call    WPP_RECORDER_SF_
0x180059a78  jmp     loc_18005988C
0x180059a7d  test    eax, eax
0x180059a7f  jz      loc_1800598CE
0x180059a85  mov     r8d, r15d
0x180059a88  mov     rcx, rbx
0x180059a8b  call    CompletePendingIo
0x180059a90  jmp     loc_1800598CE
0x180059a95  mov     rcx, cs:WPP_GLOBAL_Control
0x180059a9c  cmp     [rcx+48h], di
0x180059aa0  jz      loc_180059A0D
0x180059aa6  mov     rax, [rbx+30h]
0x180059aaa  mov     r9d, 30h ; '0'
0x180059ab0  mov     rcx, [rcx+40h]
0x180059ab4  mov     r8d, esi
0x180059ab7  mov     [rsp+78h+var_50], rax
0x180059abc  mov     dl, 5
0x180059abe  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180059ac5  mov     [rsp+78h+var_58], rax
0x180059aca  call    WPP_RECORDER_SF_q
0x180059acf  jmp     loc_180059A0D
0x180059ad4  lea     r15, WPP_RECORDER_INITIALIZED
0x180059adb  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180059ae2  jz      short loc_180059B1A
0x180059ae4  mov     rcx, cs:WPP_GLOBAL_Control
0x180059aeb  cmp     [rcx+48h], di
0x180059aef  jz      short loc_180059B1A
0x180059af1  mov     rax, [rbx+30h]
0x180059af5  mov     r9d, 31h ; '1'
0x180059afb  mov     rcx, [rcx+40h]
0x180059aff  mov     r8d, esi
0x180059b02  mov     [rsp+78h+var_50], rax
0x180059b07  mov     dl, 5
0x180059b09  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180059b10  mov     [rsp+78h+var_58], rax
0x180059b15  call    WPP_RECORDER_SF_q
0x180059b1a  mov     rcx, rbp; FastMutex
0x180059b1d  call    cs:__imp_ExReleaseFastMutexUnsafe
0x180059b24  nop     dword ptr [rax+rax+00h]
0x180059b29  call    cs:__imp_KeLeaveCriticalRegion
0x180059b30  nop     dword ptr [rax+rax+00h]
0x180059b35  jmp     loc_180059A3A
0x180059b3a  mov     r8, rsi
0x180059b3d  mov     rdx, rbx
0x180059b40  mov     rcx, r14
0x180059b43  call    CreatePdo
0x180059b48  test    eax, eax
0x180059b4a  js      loc_180059C2F
0x180059b50  lea     r15, WPP_RECORDER_INITIALIZED
0x180059b57  xor     edi, edi
0x180059b59  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180059b60  jz      short loc_180059B98
0x180059b62  mov     rcx, cs:WPP_GLOBAL_Control
0x180059b69  cmp     [rcx+48h], di
0x180059b6d  jz      short loc_180059B98
0x180059b6f  mov     rax, [rsi]
0x180059b72  lea     r9d, [rdi+32h]
0x180059b76  mov     rcx, [rcx+40h]
0x180059b7a  lea     rsi, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180059b81  mov     [rsp+78h+var_50], rax
0x180059b86  lea     r8d, [rdi+1]
0x180059b8a  mov     dl, 5
0x180059b8c  mov     [rsp+78h+var_58], rsi
0x180059b91  call    WPP_RECORDER_SF_q
0x180059b96  jmp     short loc_180059B9F
0x180059b98  lea     rsi, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180059b9f  mov     rax, [r13+40h]
0x180059ba3  mov     rcx, r13; DeviceObject
0x180059ba6  mov     [rax], rdi
0x180059ba9  call    cs:__imp_IoDeleteDevice
0x180059bb0  nop     dword ptr [rax+rax+00h]
0x180059bb5  xor     edx, edx; Tag
0x180059bb7  mov     rcx, r12; P
0x180059bba  call    cs:__imp_ExFreePoolWithTag
0x180059bc1  nop     dword ptr [rax+rax+00h]
0x180059bc6  mov     rax, [rbx+78h]
0x180059bca  mov     rcx, rbp; FastMutex
0x180059bcd  mov     [rbx+80h], rax
0x180059bd4  mov     [rbx+50h], edi
0x180059bd7  call    cs:__imp_ExReleaseFastMutexUnsafe
0x180059bde  nop     dword ptr [rax+rax+00h]
0x180059be3  call    cs:__imp_KeLeaveCriticalRegion
0x180059bea  nop     dword ptr [rax+rax+00h]
0x180059bef  mov     rcx, [r14+60h]; DeviceObject
0x180059bf3  xor     edx, edx; Type
0x180059bf5  call    cs:__imp_IoInvalidateDeviceRelations
0x180059bfc  nop     dword ptr [rax+rax+00h]
0x180059c01  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180059c08  jz      loc_180059A3A
0x180059c0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180059c15  cmp     [rcx+48h], di
0x180059c19  jz      loc_180059A3A
0x180059c1f  mov     r9d, 33h ; '3'
0x180059c25  mov     [rsp+78h+var_58], rsi
0x180059c2a  jmp     loc_1800599E3
0x180059c2f  mov     dword ptr [rbx+50h], 2
0x180059c36  jmp     loc_180059910
0x180059c3b  mov     ecx, 3
0x180059c40  int     29h; Win8: RtlFailFast(ecx)
```
