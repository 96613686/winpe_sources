# CKsDevice::CreateChildPdo(ushort *,ulong)

- ea: `0x18003abdc`
- end: `0x18003adac`
- name: `?CreateChildPdo@CKsDevice@@QEAAJPEAGK@Z`
- size: `464`
- prototype: `__int64 __fastcall(CKsDevice *this, unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18005d03c`

## callees

- `0x18000b7bc`
- `0x18000d1e0`
- `0x180013538`
- `0x18001a000`
- `0x18003abdc`

## import_xrefs

- `ntoskrnl!IoCreateDevice` at `0x18003ac2d`
- `ntoskrnl!IoCreateDevice` at `0x18003ac2d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18003ad31`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18003ad31`

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
0x18003abdc  mov     r11, rsp
0x18003abdf  mov     [r11+10h], rbx
0x18003abe3  mov     [r11+18h], rbp
0x18003abe7  push    rsi
0x18003abe8  push    rdi
0x18003abe9  push    r14
0x18003abeb  sub     rsp, 40h
0x18003abef  mov     rdi, rcx
0x18003abf2  mov     qword ptr [r11+8], 0
0x18003abfa  mov     rcx, [rcx+0E0h]
0x18003ac01  lea     rax, [r11+8]
0x18003ac05  mov     [r11-28h], rax
0x18003ac09  mov     r9d, 22h ; '"'; DeviceType
0x18003ac0f  mov     esi, r8d
0x18003ac12  mov     [rsp+58h+Exclusive], 0; Exclusive
0x18003ac17  mov     rbp, rdx
0x18003ac1a  mov     [rsp+58h+DeviceCharacteristics], 180h; DeviceCharacteristics
0x18003ac22  mov     rcx, [rcx+8]; DriverObject
0x18003ac26  xor     r8d, r8d; DeviceName
0x18003ac29  lea     edx, [r9+0Eh]; DeviceExtensionSize
0x18003ac2d  call    cs:__imp_IoCreateDevice
0x18003ac34  nop     dword ptr [rax+rax+00h]
0x18003ac39  mov     ebx, eax
0x18003ac3b  test    eax, eax
0x18003ac3d  jns     short loc_18003AC80
0x18003ac3f  lea     rax, WPP_RECORDER_INITIALIZED
0x18003ac46  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18003ac4d  jz      loc_18003AD96
0x18003ac53  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ac5a  lea     rax, WPP_50288c75019938eedd86f8b19427641e_Traceguids
0x18003ac61  mov     r9d, 0Ah
0x18003ac67  mov     qword ptr [rsp+58h+DeviceCharacteristics], rax
0x18003ac6c  mov     dl, 2
0x18003ac6e  mov     rcx, [rcx+40h]
0x18003ac72  lea     r8d, [r9-9]
0x18003ac76  call    WPP_RECORDER_SF_
0x18003ac7b  jmp     loc_18003AD96
0x18003ac80  mov     rax, [rdi+0E0h]
0x18003ac87  mov     [rsp+58h+pcchLength], 0
0x18003ac90  mov     cl, [rax+4Ch]
0x18003ac93  mov     rax, [rsp+58h+arg_0]
0x18003ac98  inc     cl
0x18003ac9a  mov     [rax+4Ch], cl
0x18003ac9d  mov     rax, [rsp+58h+arg_0]
0x18003aca2  mov     r14, [rax+40h]
0x18003aca6  mov     dword ptr [r14], 4450534Bh
0x18003acad  mov     rax, [rsp+58h+arg_0]
0x18003acb2  mov     [r14+18h], rax
0x18003acb6  mov     dword ptr [r14+4], 0
0x18003acbe  mov     byte ptr [r14+2Ch], 0
0x18003acc3  mov     rax, [rdi+0E0h]
0x18003acca  mov     [r14+8], rax
0x18003acce  mov     rax, [rdi+460h]
0x18003acd5  mov     [r14+10h], rax
0x18003acd9  mov     [r14+28h], esi
0x18003acdd  mov     rax, [rsp+58h+arg_0]
0x18003ace2  mov     [rdi+460h], rax
0x18003ace9  mov     qword ptr [r14+20h], 0
0x18003acf1  test    rbp, rbp
0x18003acf4  jz      loc_18003AD7D
0x18003acfa  lea     r8, [rsp+58h+pcchLength]; pcchLength
0x18003acff  mov     edx, 7FFFFFFFh; cchMax
0x18003ad04  mov     rcx, rbp; psz
0x18003ad07  call    RtlStringLengthWorkerW
0x18003ad0c  mov     ebx, eax
0x18003ad0e  test    eax, eax
0x18003ad10  js      short loc_18003AD82
0x18003ad12  mov     rax, [rsp+58h+pcchLength]
0x18003ad17  add     rax, rax
0x18003ad1a  lea     rdi, [rax+2]
0x18003ad1e  cmp     rdi, rax
0x18003ad21  jb      short loc_18003AD76
0x18003ad23  mov     r8d, 6E63534Bh; Tag
0x18003ad29  mov     rdx, rdi; NumberOfBytes
0x18003ad2c  mov     ecx, 401h; PoolType
0x18003ad31  call    cs:__imp_ExAllocatePoolWithTag
0x18003ad38  nop     dword ptr [rax+rax+00h]
0x18003ad3d  mov     rsi, rax
0x18003ad40  test    rax, rax
0x18003ad43  jz      short loc_18003AD6F
0x18003ad45  cmp     cs:ExPoolZeroingNativelySupported, 0
0x18003ad4c  jnz     short loc_18003AD5B
0x18003ad4e  mov     r8, rdi; Size
0x18003ad51  xor     edx, edx; Val
0x18003ad53  mov     rcx, rax; void *
0x18003ad56  call    memset
0x18003ad5b  mov     r8, rbp; unsigned __int16 *
0x18003ad5e  mov     rdx, rdi; unsigned __int64
0x18003ad61  mov     rcx, rsi; unsigned __int16 *
0x18003ad64  call    ?RtlStringCbCopyW@@YAJPEAG_KPEBG@Z; RtlStringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x18003ad69  mov     [r14+20h], rsi
0x18003ad6d  jmp     short loc_18003AD82
0x18003ad6f  mov     ebx, 0C000009Ah
0x18003ad74  jmp     short loc_18003AD82
0x18003ad76  mov     ebx, 0C0000095h
0x18003ad7b  jmp     short loc_18003AD82
0x18003ad7d  mov     ebx, 0C000000Dh
0x18003ad82  mov     rcx, [rsp+58h+arg_0]
0x18003ad87  bts     dword ptr [rcx+30h], 0Dh
0x18003ad8c  mov     rcx, [rsp+58h+arg_0]
0x18003ad91  btr     dword ptr [rcx+30h], 7
0x18003ad96  mov     rbp, [rsp+58h+arg_10]
0x18003ad9b  mov     eax, ebx
0x18003ad9d  mov     rbx, [rsp+58h+arg_8]
0x18003ada2  add     rsp, 40h
0x18003ada6  pop     r14
0x18003ada8  pop     rdi
0x18003ada9  pop     rsi
0x18003adaa  retn
```
