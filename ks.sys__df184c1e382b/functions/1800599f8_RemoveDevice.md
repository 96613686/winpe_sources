# RemoveDevice

- ea: `0x1800599f8`
- end: `0x180059de2`
- name: `RemoveDevice`
- size: `1002`
- prototype: `__int64 __fastcall(PDEVICE_OBJECT DeviceObject)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005a890`

## callees

- `0x18000b7bc`
- `0x18000dddc`
- `0x18005997c`
- `0x1800599f8`
- `0x18005a260`
- `0x18005a4a8`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x180059a50`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x180059a50`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180059a3d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x180059a3d`
- `ntoskrnl!IoDeleteDevice` at `0x180059b2c`
- `ntoskrnl!IoDeleteDevice` at `0x180059d49`
- `ntoskrnl!IoDeleteDevice` at `0x180059b2c`
- `ntoskrnl!IoDeleteDevice` at `0x180059d49`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x180059bce`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x180059d95`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x180059bce`
- `ntoskrnl!IoInvalidateDeviceRelations` at `0x180059d95`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x180059b3b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x180059bb0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x180059cbd`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x180059d77`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x180059b3b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x180059bb0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x180059cbd`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x180059d77`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180059b47`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180059bbc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180059cc9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180059d83`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180059b47`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180059bbc`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180059cc9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x180059d83`
- `ntoskrnl!IofCompleteRequest` at `0x180059b03`
- `ntoskrnl!IofCompleteRequest` at `0x180059b03`
- `ntoskrnl!ExFreePoolWithTag` at `0x180059a79`
- `ntoskrnl!ExFreePoolWithTag` at `0x180059b16`
- `ntoskrnl!ExFreePoolWithTag` at `0x180059d5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x180059a79`
- `ntoskrnl!ExFreePoolWithTag` at `0x180059b16`
- `ntoskrnl!ExFreePoolWithTag` at `0x180059d5a`

## pseudocode

```c
__int64 __fastcall RemoveDevice(PDEVICE_OBJECT DeviceObject)
{
  __int64 *v2; // rdx
  PVOID DeviceExtension; // rax
  void *v4; // r12
  __int64 v5; // rbx
  __int64 v6; // r14
  __int64 v7; // rdx
  int v8; // eax
  void *v9; // rcx
  int v10; // eax
  _QWORD *v11; // rdi
  _QWORD *v12; // rsi
  _QWORD *v13; // rax
  __int64 v14; // rcx
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
  v5 = *(_QWORD *)(*(_QWORD *)DeviceExtension + 32LL);
  v6 = *(_QWORD *)(*(_QWORD *)DeviceExtension + 40LL);
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v6 + 24));
  v8 = *(_DWORD *)(v5 + 56);
  if ( v8 < 4 && v8 )
    CompletePendingIo(v5, v7, -1073741772);
  v9 = *(void **)(v5 + 88);
  if ( v9 )
  {
    ExFreePoolWithTag(v9, 0);
    *(_QWORD *)(v5 + 88) = 0;
  }
  v10 = *(_DWORD *)(v5 + 80);
  *(_DWORD *)(v5 + 56) = 0;
  if ( !v10 )
  {
    *(_DWORD *)(v5 + 80) = 1;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED && LOWORD(WPP_GLOBAL_Control->DeviceType) )
    {
      LOBYTE(v7) = 5;
      WPP_RECORDER_SF_q(
        WPP_GLOBAL_Control->DeviceExtension,
        v7,
        1,
        48,
        (__int64)WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids,
        *(_QWORD *)(v5 + 48));
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
        *(_QWORD *)(v5 + 48));
    }
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v6 + 24));
    KeLeaveCriticalRegion();
    return 0;
  }
  v11 = (_QWORD *)(v5 + 32);
  v12 = (_QWORD *)(v5 + 48);
  if ( (_QWORD *)*v11 == v11 )
    goto LABEL_8;
  if ( (int)CreatePdo(v6, v5, v5 + 48) < 0 )
  {
    *(_DWORD *)(v5 + 80) = 2;
LABEL_8:
    *v12 = 0;
    while ( 1 )
    {
      v13 = (_QWORD *)*v11;
      if ( (_QWORD *)*v11 == v11 )
        break;
      if ( (_QWORD *)v13[1] != v11 || (v14 = *v13, *(_QWORD **)(*v13 + 8LL) != v13) )
        __fastfail(3u);
      *v11 = v14;
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
      *v12);
  }
  *(_QWORD *)DeviceObject->DeviceExtension = 0;
  IoDeleteDevice(DeviceObject);
  ExFreePoolWithTag(v4, 0);
  *(_QWORD *)(v5 + 128) = *(_QWORD *)(v5 + 120);
  *(_DWORD *)(v5 + 80) = 0;
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
0x1800599f8  push    rbx
0x1800599fa  push    rbp
0x1800599fb  push    rsi
0x1800599fc  push    rdi
0x1800599fd  push    r12
0x1800599ff  push    r13
0x180059a01  push    r14
0x180059a03  push    r15
0x180059a05  sub     rsp, 38h
0x180059a09  mov     r13, rcx
0x180059a0c  xor     edi, edi
0x180059a0e  lea     rax, WPP_RECORDER_INITIALIZED
0x180059a15  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x180059a1c  lea     rdx, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180059a23  lea     esi, [rdi+1]
0x180059a26  jnz     loc_180059BEE
0x180059a2c  mov     rax, [r13+40h]
0x180059a30  mov     r12, [rax]
0x180059a33  mov     rbx, [r12+20h]
0x180059a38  mov     r14, [r12+28h]
0x180059a3d  call    cs:__imp_KeEnterCriticalRegion
0x180059a44  nop     dword ptr [rax+rax+00h]
0x180059a49  lea     rbp, [r14+18h]
0x180059a4d  mov     rcx, rbp; FastMutex
0x180059a50  call    cs:__imp_ExAcquireFastMutexUnsafe
0x180059a57  nop     dword ptr [rax+rax+00h]
0x180059a5c  mov     eax, [rbx+38h]
0x180059a5f  mov     r15d, 0C0000034h
0x180059a65  cmp     eax, 4
0x180059a68  jl      loc_180059C1D
0x180059a6e  mov     rcx, [rbx+58h]; P
0x180059a72  test    rcx, rcx
0x180059a75  jz      short loc_180059A89
0x180059a77  xor     edx, edx; Tag
0x180059a79  call    cs:__imp_ExFreePoolWithTag
0x180059a80  nop     dword ptr [rax+rax+00h]
0x180059a85  mov     [rbx+58h], rdi
0x180059a89  mov     eax, [rbx+50h]
0x180059a8c  mov     [rbx+38h], edi
0x180059a8f  test    eax, eax
0x180059a91  jz      loc_180059B96
0x180059a97  cmp     eax, esi
0x180059a99  jz      loc_180059C74
0x180059a9f  lea     rdi, [rbx+20h]
0x180059aa3  lea     rsi, [rbx+30h]
0x180059aa7  cmp     [rdi], rdi
0x180059aaa  jnz     loc_180059CDA
0x180059ab0  xor     r14d, r14d
0x180059ab3  mov     [rsi], r14
0x180059ab6  mov     rax, [rdi]
0x180059ab9  cmp     rax, rdi
0x180059abc  jz      short loc_180059B11
0x180059abe  cmp     [rax+8], rdi
0x180059ac2  jnz     loc_180059DDB
0x180059ac8  mov     rcx, [rax]
0x180059acb  cmp     [rcx+8], rax
0x180059acf  jnz     loc_180059DDB
0x180059ad5  mov     [rdi], rcx
0x180059ad8  lea     rsi, [rax-0A8h]
0x180059adf  mov     [rcx+8], rdi
0x180059ae3  cmp     r15d, 104h
0x180059aea  jnz     short loc_180059AFA
0x180059aec  mov     rdx, rbx
0x180059aef  mov     rcx, rsi
0x180059af2  call    IssueReparseForIrp
0x180059af7  mov     r15d, eax
0x180059afa  xor     edx, edx; PriorityBoost
0x180059afc  mov     [rsi+30h], r15d
0x180059b00  mov     rcx, rsi; Irp
0x180059b03  call    cs:__imp_IofCompleteRequest
0x180059b0a  nop     dword ptr [rax+rax+00h]
0x180059b0f  jmp     short loc_180059AB6
0x180059b11  xor     edx, edx; Tag
0x180059b13  mov     rcx, r12; P
0x180059b16  call    cs:__imp_ExFreePoolWithTag
0x180059b1d  nop     dword ptr [rax+rax+00h]
0x180059b22  mov     rax, [r13+40h]
0x180059b26  mov     rcx, r13; DeviceObject
0x180059b29  mov     [rax], r14
0x180059b2c  call    cs:__imp_IoDeleteDevice
0x180059b33  nop     dword ptr [rax+rax+00h]
0x180059b38  mov     rcx, rbp; FastMutex
0x180059b3b  call    cs:__imp_ExReleaseFastMutexUnsafe
0x180059b42  nop     dword ptr [rax+rax+00h]
0x180059b47  call    cs:__imp_KeLeaveCriticalRegion
0x180059b4e  nop     dword ptr [rax+rax+00h]
0x180059b53  lea     r15, WPP_RECORDER_INITIALIZED
0x180059b5a  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180059b61  jz      short loc_180059BDA
0x180059b63  mov     rcx, cs:WPP_GLOBAL_Control
0x180059b6a  cmp     [rcx+48h], r14w
0x180059b6f  jz      short loc_180059BDA
0x180059b71  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180059b78  mov     r9d, 34h ; '4'
0x180059b7e  mov     [rsp+78h+var_58], rax
0x180059b83  mov     rcx, [rcx+40h]
0x180059b87  mov     r8d, 1
0x180059b8d  mov     dl, 5
0x180059b8f  call    WPP_RECORDER_SF_
0x180059b94  jmp     short loc_180059BDA
0x180059b96  mov     [rbx+50h], esi
0x180059b99  lea     r15, WPP_RECORDER_INITIALIZED
0x180059ba0  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180059ba7  jnz     loc_180059C35
0x180059bad  mov     rcx, rbp; FastMutex
0x180059bb0  call    cs:__imp_ExReleaseFastMutexUnsafe
0x180059bb7  nop     dword ptr [rax+rax+00h]
0x180059bbc  call    cs:__imp_KeLeaveCriticalRegion
0x180059bc3  nop     dword ptr [rax+rax+00h]
0x180059bc8  mov     rcx, [r14+60h]; DeviceObject
0x180059bcc  xor     edx, edx; Type
0x180059bce  call    cs:__imp_IoInvalidateDeviceRelations
0x180059bd5  nop     dword ptr [rax+rax+00h]
0x180059bda  xor     eax, eax
0x180059bdc  add     rsp, 38h
0x180059be0  pop     r15
0x180059be2  pop     r14
0x180059be4  pop     r13
0x180059be6  pop     r12
0x180059be8  pop     rdi
0x180059be9  pop     rsi
0x180059bea  pop     rbp
0x180059beb  pop     rbx
0x180059bec  retn
0x180059bee  mov     rcx, cs:WPP_GLOBAL_Control
0x180059bf5  cmp     [rcx+48h], di
0x180059bf9  jz      loc_180059A2C
0x180059bff  mov     rcx, [rcx+40h]
0x180059c03  mov     r9d, 2Fh ; '/'
0x180059c09  mov     [rsp+78h+var_58], rdx
0x180059c0e  mov     r8d, esi
0x180059c11  mov     dl, 5
0x180059c13  call    WPP_RECORDER_SF_
0x180059c18  jmp     loc_180059A2C
0x180059c1d  test    eax, eax
0x180059c1f  jz      loc_180059A6E
0x180059c25  mov     r8d, r15d
0x180059c28  mov     rcx, rbx
0x180059c2b  call    CompletePendingIo
0x180059c30  jmp     loc_180059A6E
0x180059c35  mov     rcx, cs:WPP_GLOBAL_Control
0x180059c3c  cmp     [rcx+48h], di
0x180059c40  jz      loc_180059BAD
0x180059c46  mov     rax, [rbx+30h]
0x180059c4a  mov     r9d, 30h ; '0'
0x180059c50  mov     rcx, [rcx+40h]
0x180059c54  mov     r8d, esi
0x180059c57  mov     [rsp+78h+var_50], rax
0x180059c5c  mov     dl, 5
0x180059c5e  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180059c65  mov     [rsp+78h+var_58], rax
0x180059c6a  call    WPP_RECORDER_SF_q
0x180059c6f  jmp     loc_180059BAD
0x180059c74  lea     r15, WPP_RECORDER_INITIALIZED
0x180059c7b  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180059c82  jz      short loc_180059CBA
0x180059c84  mov     rcx, cs:WPP_GLOBAL_Control
0x180059c8b  cmp     [rcx+48h], di
0x180059c8f  jz      short loc_180059CBA
0x180059c91  mov     rax, [rbx+30h]
0x180059c95  mov     r9d, 31h ; '1'
0x180059c9b  mov     rcx, [rcx+40h]
0x180059c9f  mov     r8d, esi
0x180059ca2  mov     [rsp+78h+var_50], rax
0x180059ca7  mov     dl, 5
0x180059ca9  lea     rax, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180059cb0  mov     [rsp+78h+var_58], rax
0x180059cb5  call    WPP_RECORDER_SF_q
0x180059cba  mov     rcx, rbp; FastMutex
0x180059cbd  call    cs:__imp_ExReleaseFastMutexUnsafe
0x180059cc4  nop     dword ptr [rax+rax+00h]
0x180059cc9  call    cs:__imp_KeLeaveCriticalRegion
0x180059cd0  nop     dword ptr [rax+rax+00h]
0x180059cd5  jmp     loc_180059BDA
0x180059cda  mov     r8, rsi
0x180059cdd  mov     rdx, rbx
0x180059ce0  mov     rcx, r14
0x180059ce3  call    CreatePdo
0x180059ce8  test    eax, eax
0x180059cea  js      loc_180059DCF
0x180059cf0  lea     r15, WPP_RECORDER_INITIALIZED
0x180059cf7  xor     edi, edi
0x180059cf9  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180059d00  jz      short loc_180059D38
0x180059d02  mov     rcx, cs:WPP_GLOBAL_Control
0x180059d09  cmp     [rcx+48h], di
0x180059d0d  jz      short loc_180059D38
0x180059d0f  mov     rax, [rsi]
0x180059d12  lea     r9d, [rdi+32h]
0x180059d16  mov     rcx, [rcx+40h]
0x180059d1a  lea     rsi, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180059d21  mov     [rsp+78h+var_50], rax
0x180059d26  lea     r8d, [rdi+1]
0x180059d2a  mov     dl, 5
0x180059d2c  mov     [rsp+78h+var_58], rsi
0x180059d31  call    WPP_RECORDER_SF_q
0x180059d36  jmp     short loc_180059D3F
0x180059d38  lea     rsi, WPP_36c6b157cc5b353e3e13f4b169c77c35_Traceguids
0x180059d3f  mov     rax, [r13+40h]
0x180059d43  mov     rcx, r13; DeviceObject
0x180059d46  mov     [rax], rdi
0x180059d49  call    cs:__imp_IoDeleteDevice
0x180059d50  nop     dword ptr [rax+rax+00h]
0x180059d55  xor     edx, edx; Tag
0x180059d57  mov     rcx, r12; P
0x180059d5a  call    cs:__imp_ExFreePoolWithTag
0x180059d61  nop     dword ptr [rax+rax+00h]
0x180059d66  mov     rax, [rbx+78h]
0x180059d6a  mov     rcx, rbp; FastMutex
0x180059d6d  mov     [rbx+80h], rax
0x180059d74  mov     [rbx+50h], edi
0x180059d77  call    cs:__imp_ExReleaseFastMutexUnsafe
0x180059d7e  nop     dword ptr [rax+rax+00h]
0x180059d83  call    cs:__imp_KeLeaveCriticalRegion
0x180059d8a  nop     dword ptr [rax+rax+00h]
0x180059d8f  mov     rcx, [r14+60h]; DeviceObject
0x180059d93  xor     edx, edx; Type
0x180059d95  call    cs:__imp_IoInvalidateDeviceRelations
0x180059d9c  nop     dword ptr [rax+rax+00h]
0x180059da1  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180059da8  jz      loc_180059BDA
0x180059dae  mov     rcx, cs:WPP_GLOBAL_Control
0x180059db5  cmp     [rcx+48h], di
0x180059db9  jz      loc_180059BDA
0x180059dbf  mov     r9d, 33h ; '3'
0x180059dc5  mov     [rsp+78h+var_58], rsi
0x180059dca  jmp     loc_180059B83
0x180059dcf  mov     dword ptr [rbx+50h], 2
0x180059dd6  jmp     loc_180059AB0
0x180059ddb  mov     ecx, 3
0x180059de0  int     29h; Win8: RtlFailFast(ecx)
```
