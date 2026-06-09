# CKsDevice::CreateChildPdo(ushort *,ulong)

- ea: `0x18003abec`
- end: `0x18003adbc`
- name: `?CreateChildPdo@CKsDevice@@QEAAJPEAGK@Z`
- size: `464`
- prototype: `int(CKsDevice *__hidden this, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18005ce9c`

## callees

- `0x18000b7bc`
- `0x18000d1e0`
- `0x180013538`
- `0x180019fc0`
- `0x18003abec`

## import_xrefs

- `ntoskrnl!IoCreateDevice` at `0x18003ac3d`
- `ntoskrnl!IoCreateDevice` at `0x18003ac3d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18003ad41`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18003ad41`

## pseudocode

```c
__int64 __fastcall CKsDevice::CreateChildPdo(CKsDevice *this, unsigned __int16 *a2, int a3)
{
  int v6; // edx
  NTSTATUS v7; // ebx
  _DEVICE_OBJECT *FunctionalDeviceObject; // rax
  _QWORD *DeviceExtension; // r14
  size_t v10; // rdi
  unsigned __int16 *PoolWithTag; // rax
  unsigned __int16 *v12; // rsi
  PDEVICE_OBJECT v14; // [rsp+60h] [rbp+8h] BYREF
  size_t pcchLength; // [rsp+78h] [rbp+20h] BYREF

  v14 = 0;
  v7 = IoCreateDevice(this->m_Ext.Public.FunctionalDeviceObject->DriverObject, 0x30u, 0, 0x22u, 0x180u, 0, &v14);
  if ( v7 >= 0 )
  {
    FunctionalDeviceObject = this->m_Ext.Public.FunctionalDeviceObject;
    pcchLength = 0;
    v14->StackSize = FunctionalDeviceObject->StackSize + 1;
    DeviceExtension = v14->DeviceExtension;
    *(_DWORD *)DeviceExtension = 1146114891;
    DeviceExtension[3] = v14;
    *((_DWORD *)DeviceExtension + 1) = 0;
    *((_BYTE *)DeviceExtension + 44) = 0;
    DeviceExtension[1] = this->m_Ext.Public.FunctionalDeviceObject;
    DeviceExtension[2] = this->m_pNextChildPdo;
    *((_DWORD *)DeviceExtension + 10) = a3;
    this->m_pNextChildPdo = v14;
    DeviceExtension[4] = 0;
    if ( a2 )
    {
      v7 = RtlStringLengthWorkerW(a2, 0x7FFFFFFFu, &pcchLength);
      if ( v7 >= 0 )
      {
        v10 = 2 * pcchLength + 2;
        if ( v10 < 2 * pcchLength )
        {
          v7 = -1073741675;
        }
        else
        {
          PoolWithTag = (unsigned __int16 *)ExAllocatePoolWithTag((POOL_TYPE)1025, 2 * pcchLength + 2, 0x6E63534Bu);
          v12 = PoolWithTag;
          if ( PoolWithTag )
          {
            if ( !ExPoolZeroingNativelySupported )
              memset(PoolWithTag, 0, v10);
            RtlStringCbCopyW(v12, v10, a2);
            DeviceExtension[4] = v12;
          }
          else
          {
            v7 = -1073741670;
          }
        }
      }
    }
    else
    {
      v7 = -1073741811;
    }
    v14->Flags |= 0x2000u;
    v14->Flags &= ~0x80u;
  }
  else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v6) = 2;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v6,
      1,
      10,
      (__int64)WPP_50288c75019938eedd86f8b19427641e_Traceguids);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18003abec  mov     r11, rsp
0x18003abef  mov     [r11+10h], rbx
0x18003abf3  mov     [r11+18h], rbp
0x18003abf7  push    rsi
0x18003abf8  push    rdi
0x18003abf9  push    r14
0x18003abfb  sub     rsp, 40h
0x18003abff  mov     rdi, rcx
0x18003ac02  mov     qword ptr [r11+8], 0
0x18003ac0a  mov     rcx, [rcx+0E0h]
0x18003ac11  lea     rax, [r11+8]
0x18003ac15  mov     [r11-28h], rax
0x18003ac19  mov     r9d, 22h ; '"'; DeviceType
0x18003ac1f  mov     esi, r8d
0x18003ac22  mov     [rsp+58h+Exclusive], 0; Exclusive
0x18003ac27  mov     rbp, rdx
0x18003ac2a  mov     [rsp+58h+DeviceCharacteristics], 180h; DeviceCharacteristics
0x18003ac32  mov     rcx, [rcx+8]; DriverObject
0x18003ac36  xor     r8d, r8d; DeviceName
0x18003ac39  lea     edx, [r9+0Eh]; DeviceExtensionSize
0x18003ac3d  call    cs:__imp_IoCreateDevice
0x18003ac44  nop     dword ptr [rax+rax+00h]
0x18003ac49  mov     ebx, eax
0x18003ac4b  test    eax, eax
0x18003ac4d  jns     short loc_18003AC90
0x18003ac4f  lea     rax, WPP_RECORDER_INITIALIZED
0x18003ac56  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003ac5d  jz      loc_18003ADA6
0x18003ac63  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ac6a  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18003ac71  mov     r9d, 0Ah
0x18003ac77  mov     qword ptr [rsp+58h+DeviceCharacteristics], rax
0x18003ac7c  mov     dl, 2
0x18003ac7e  mov     rcx, [rcx+40h]
0x18003ac82  lea     r8d, [r9-9]
0x18003ac86  call    WPP_RECORDER_SF_
0x18003ac8b  jmp     loc_18003ADA6
0x18003ac90  mov     rax, [rdi+0E0h]
0x18003ac97  mov     [rsp+58h+pcchLength], 0
0x18003aca0  mov     cl, [rax+4Ch]
0x18003aca3  mov     rax, [rsp+58h+arg_0]
0x18003aca8  inc     cl
0x18003acaa  mov     [rax+4Ch], cl
0x18003acad  mov     rax, [rsp+58h+arg_0]
0x18003acb2  mov     r14, [rax+40h]
0x18003acb6  mov     dword ptr [r14], 4450534Bh
0x18003acbd  mov     rax, [rsp+58h+arg_0]
0x18003acc2  mov     [r14+18h], rax
0x18003acc6  mov     dword ptr [r14+4], 0
0x18003acce  mov     byte ptr [r14+2Ch], 0
0x18003acd3  mov     rax, [rdi+0E0h]
0x18003acda  mov     [r14+8], rax
0x18003acde  mov     rax, [rdi+460h]
0x18003ace5  mov     [r14+10h], rax
0x18003ace9  mov     [r14+28h], esi
0x18003aced  mov     rax, [rsp+58h+arg_0]
0x18003acf2  mov     [rdi+460h], rax
0x18003acf9  mov     qword ptr [r14+20h], 0
0x18003ad01  test    rbp, rbp
0x18003ad04  jz      loc_18003AD8D
0x18003ad0a  lea     r8, [rsp+58h+pcchLength]; pcchLength
0x18003ad0f  mov     edx, 7FFFFFFFh; cchMax
0x18003ad14  mov     rcx, rbp; psz
0x18003ad17  call    RtlStringLengthWorkerW
0x18003ad1c  mov     ebx, eax
0x18003ad1e  test    eax, eax
0x18003ad20  js      short loc_18003AD92
0x18003ad22  mov     rax, [rsp+58h+pcchLength]
0x18003ad27  add     rax, rax
0x18003ad2a  lea     rdi, [rax+2]
0x18003ad2e  cmp     rdi, rax
0x18003ad31  jb      short loc_18003AD86
0x18003ad33  mov     r8d, 6E63534Bh; Tag
0x18003ad39  mov     rdx, rdi; NumberOfBytes
0x18003ad3c  mov     ecx, 401h; PoolType
0x18003ad41  call    cs:__imp_ExAllocatePoolWithTag
0x18003ad48  nop     dword ptr [rax+rax+00h]
0x18003ad4d  mov     rsi, rax
0x18003ad50  test    rax, rax
0x18003ad53  jz      short loc_18003AD7F
0x18003ad55  cmp     cs:ExPoolZeroingNativelySupported, 0
0x18003ad5c  jnz     short loc_18003AD6B
0x18003ad5e  mov     r8, rdi; Size
0x18003ad61  xor     edx, edx; Val
0x18003ad63  mov     rcx, rax; void *
0x18003ad66  call    memset
0x18003ad6b  mov     r8, rbp; unsigned __int16 *
0x18003ad6e  mov     rdx, rdi; unsigned __int64
0x18003ad71  mov     rcx, rsi; unsigned __int16 *
0x18003ad74  call    ?RtlStringCbCopyW@@YAJPEAG_KPEBG@Z; RtlStringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18003ad79  mov     [r14+20h], rsi
0x18003ad7d  jmp     short loc_18003AD92
0x18003ad7f  mov     ebx, 0C000009Ah
0x18003ad84  jmp     short loc_18003AD92
0x18003ad86  mov     ebx, 0C0000095h
0x18003ad8b  jmp     short loc_18003AD92
0x18003ad8d  mov     ebx, 0C000000Dh
0x18003ad92  mov     rcx, [rsp+58h+arg_0]
0x18003ad97  bts     dword ptr [rcx+30h], 0Dh
0x18003ad9c  mov     rcx, [rsp+58h+arg_0]
0x18003ada1  btr     dword ptr [rcx+30h], 7
0x18003ada6  mov     rbp, [rsp+58h+arg_10]
0x18003adab  mov     eax, ebx
0x18003adad  mov     rbx, [rsp+58h+arg_8]
0x18003adb2  add     rsp, 40h
0x18003adb6  pop     r14
0x18003adb8  pop     rdi
0x18003adb9  pop     rsi
0x18003adba  retn
```
