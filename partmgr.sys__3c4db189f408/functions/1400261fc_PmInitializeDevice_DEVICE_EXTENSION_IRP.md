# PmInitializeDevice(_DEVICE_EXTENSION *,_IRP *)

- ea: `0x1400261fc`
- end: `0x1400265b0`
- name: `?PmInitializeDevice@@YAJPEAU_DEVICE_EXTENSION@@PEAU_IRP@@@Z`
- size: `948`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callers

- `0x140007674`

## callees

- `0x140006300`
- `0x140009ba8`
- `0x140010f20`
- `0x14001ff34`
- `0x140023394`
- `0x14002366c`
- `0x14002392c`
- `0x140023aa0`
- `0x140023cb4`
- `0x1400243b0`
- `0x1400261fc`

## import_xrefs

- `ntoskrnl!IoGetDevicePropertyData` at `0x1400262b4`
- `ntoskrnl!IoGetDevicePropertyData` at `0x1400262b4`
- `ntoskrnl!FsRtlGetVirtualDiskNestingLevel` at `0x140026546`
- `ntoskrnl!FsRtlGetVirtualDiskNestingLevel` at `0x140026546`

## pseudocode

```c
__int64 __fastcall PmInitializeDevice(struct _DEVICE_EXTENSION *a1, struct _IRP *a2)
{
  __int64 v4; // rdx
  __int64 v5; // rax
  NTSTATUS DevicePropertyData; // ebx
  int v7; // eax
  struct _DEVICE_OBJECT *v8; // rcx
  __int128 v9; // xmm0
  int v10; // eax
  struct _STORAGE_DEVICE_DESCRIPTOR **v11; // rsi
  struct _STORAGE_HW_FIRMWARE_INFO *v12; // rcx
  ULONG Type; // [rsp+40h] [rbp-19h] BYREF
  ULONG RequiredSize; // [rsp+44h] [rbp-15h] BYREF
  __int64 v16; // [rsp+48h] [rbp-11h] BYREF
  int v17; // [rsp+50h] [rbp-9h]
  _BYTE v18[40]; // [rsp+58h] [rbp-1h] BYREF

  RequiredSize = 0;
  v16 = 0;
  v17 = 0;
  v4 = *((_QWORD *)a1 + 1);
  Type = 0;
  v5 = *((_QWORD *)a1 + 2);
  memset(v18, 0, sizeof(v18));
  *(_DWORD *)(v4 + 52) |= *(_DWORD *)(v5 + 52) & 0x40001;
  if ( (*(_DWORD *)(*((_QWORD *)a1 + 2) + 52LL) & 1) != 0 )
    *((_DWORD *)a1 + 129) |= 0x1000u;
  DevicePropertyData = IoGetDevicePropertyData(
                         *((PDEVICE_OBJECT *)a1 + 3),
                         &DEVPKEY_Device_ClassGuid,
                         0,
                         0,
                         0x10u,
                         (char *)a1 + 32,
                         &RequiredSize,
                         &Type);
  if ( DevicePropertyData >= 0 )
  {
    v7 = PmSendDeviceControl(*((PDEVICE_OBJECT *)a1 + 2), 0x2D1084u, 0, 0, v18, 0x28u, 0);
    v8 = (struct _DEVICE_OBJECT *)*((_QWORD *)a1 + 2);
    if ( v7 < 0 )
    {
      DevicePropertyData = PmSendDeviceControl(v8, 0x2D1080u, 0, 0, &v16, 0xCu, 0);
      if ( DevicePropertyData < 0 )
        return (unsigned int)DevicePropertyData;
      *((_DWORD *)a1 + 42) = HIDWORD(v16);
    }
    else
    {
      v9 = *(_OWORD *)&v18[20];
      *((_DWORD *)a1 + 42) = *(_DWORD *)&v18[16];
      v10 = *(_DWORD *)&v18[8];
      *(_OWORD *)((char *)a1 + 184) = v9;
      *((_DWORD *)a1 + 43) = v10;
      *((_DWORD *)a1 + 45) = 40;
      *((_DWORD *)a1 + 44) = 40;
      PmSendDeviceControl(v8, 0x2D280Cu, (char *)a1 + 176, 0x28u, (char *)a1 + 176, 0x28u, 0);
    }
    DevicePropertyData = PmGetRegistryId(a1, (struct _GUID *)((char *)a1 + 216));
    if ( DevicePropertyData >= 0 )
    {
      v11 = (struct _STORAGE_DEVICE_DESCRIPTOR **)((char *)a1 + 232);
      DevicePropertyData = PmQueryStorageProperty(a1, StorageDeviceProperty, 0x28u, (void **)a1 + 29);
      if ( DevicePropertyData >= 0 )
      {
        DevicePropertyData = ScExtractDeviceStrings(
                               *v11,
                               (struct _UNICODE_STRING *)((char *)a1 + 344),
                               (struct _UNICODE_STRING *)((char *)a1 + 360),
                               (struct _UNICODE_STRING *)((char *)a1 + 376),
                               (struct _UNICODE_STRING *)((char *)a1 + 392));
        if ( DevicePropertyData >= 0 )
        {
          PmGetFirmwareInfo(a1, (*v11)->BusType, (struct _STORAGE_HW_FIRMWARE_INFO **)a1 + 30);
          v12 = (struct _STORAGE_HW_FIRMWARE_INFO *)*((_QWORD *)a1 + 30);
          if ( !v12
            || (DevicePropertyData = ScExtractFirmwareRevision(v12, (struct _UNICODE_STRING *)((char *)a1 + 376)),
                DevicePropertyData >= 0) )
          {
            PmQueryStorageProperty(a1, StorageDeviceIdProperty, 0x10u, (void **)a1 + 31);
            if ( (*(_DWORD *)(*((_QWORD *)a1 + 1) + 52LL) & 0x40001) == 0 )
              PmQueryStorageProperty(a1, StorageDeviceWriteCacheProperty, 0x1Cu, (void **)a1 + 32);
            PmQueryStorageProperty(a1, StorageAccessAlignmentProperty, 0x1Cu, (void **)a1 + 33);
            PmQueryStorageProperty(a1, StorageDeviceSeekPenaltyProperty, 0xCu, (void **)a1 + 34);
            PmQueryStorageProperty(a1, StorageDeviceTrimProperty, 0xCu, (void **)a1 + 35);
            PmQueryStorageProperty(a1, StorageDeviceLBProvisioningProperty, 0x28u, (void **)a1 + 36);
            PmQueryStorageProperty(a1, StorageDeviceResiliencyProperty, 0x20u, (void **)a1 + 37);
            PmQueryStorageProperty(a1, StorageDeviceZonedDeviceProperty, 0x30u, (void **)a1 + 38);
            PmGetHybridInfo(a1, (struct _SRB_IO_CONTROL_HYBRID **)a1 + 39);
            PmQueryStorageProperty(a1, StorageAdapterProperty, 0x20u, (void **)a1 + 40);
            PmQueryStorageProperty(a1, StorageAdapterSerialNumberProperty, 0x108u, (void **)a1 + 41);
            PmQueryStorageProperty(a1, StorageMiniportProperty, 0x18u, (void **)a1 + 42);
            if ( FsRtlGetVirtualDiskNestingLevel(*((PDEVICE_OBJECT *)a1 + 2), (PULONG)a1 + 12, 0) < 0 )
              *((_DWORD *)a1 + 12) = 0;
            DevicePropertyData = PmConstructDeviceLocation(a1, a2);
            if ( DevicePropertyData >= 0 )
              PmGetDevicePropertyString(
                *((struct _DEVICE_OBJECT **)a1 + 3),
                &DEVPKEY_Device_Parent,
                (struct _UNICODE_STRING *)a1 + 29);
          }
        }
      }
    }
  }
  return (unsigned int)DevicePropertyData;
}

```

## disassembly

```asm
0x1400261fc  mov     [rsp-8+arg_10], rbx
0x140026201  mov     [rsp-8+arg_18], rsi
0x140026206  push    rbp
0x140026207  push    rdi
0x140026208  push    r13
0x14002620a  push    r14
0x14002620c  push    r15
0x14002620e  lea     rbp, [rsp-37h]
0x140026213  sub     rsp, 90h
0x14002621a  mov     rax, cs:__security_cookie
0x140026221  xor     rax, rsp
0x140026224  mov     [rbp+57h+var_30], rax
0x140026228  xor     eax, eax
0x14002622a  mov     [rbp+57h+var_6C], 0
0x140026231  mov     [rbp+57h+var_68], rax
0x140026235  mov     rdi, rcx
0x140026238  mov     [rbp+57h+var_60], eax
0x14002623b  xorps   xmm0, xmm0
0x14002623e  mov     [rbp+57h+var_38], rax
0x140026242  mov     r15, rdx
0x140026245  mov     rdx, [rcx+8]
0x140026249  mov     [rbp+57h+var_70], eax
0x14002624c  mov     rax, [rcx+10h]
0x140026250  movups  [rbp+57h+var_58], xmm0
0x140026254  movups  [rbp+57h+var_48], xmm0
0x140026258  mov     ecx, [rax+34h]
0x14002625b  and     ecx, 40001h
0x140026261  or      [rdx+34h], ecx
0x140026264  mov     rax, [rdi+10h]
0x140026268  mov     ecx, [rax+34h]
0x14002626b  test    cl, 1
0x14002626e  jz      short loc_140026280
0x140026270  mov     eax, [rdi+204h]
0x140026276  bts     eax, 0Ch
0x14002627a  mov     [rdi+204h], eax
0x140026280  lea     rcx, [rbp+57h+var_70]
0x140026284  xor     r9d, r9d; Flags
0x140026287  mov     [rsp+0B0h+Type], rcx; Type
0x14002628c  lea     rax, [rdi+20h]
0x140026290  lea     rcx, [rbp+57h+var_6C]
0x140026294  xor     r8d, r8d; Lcid
0x140026297  mov     [rsp+0B0h+RequiredSize], rcx; RequiredSize
0x14002629c  lea     rdx, DEVPKEY_Device_ClassGuid; PropertyKey
0x1400262a3  mov     rcx, [rdi+18h]; Pdo
0x1400262a7  mov     [rsp+0B0h+Data], rax; Data
0x1400262ac  mov     [rsp+0B0h+Size], 10h; Size
0x1400262b4  call    cs:__imp_IoGetDevicePropertyData
0x1400262bb  nop     dword ptr [rax+rax+00h]
0x1400262c0  mov     ebx, eax
0x1400262c2  test    eax, eax
0x1400262c4  js      loc_140026585
0x1400262ca  mov     rcx, [rdi+10h]; DeviceObject
0x1400262ce  lea     rax, [rbp+57h+var_58]
0x1400262d2  mov     byte ptr [rsp+0B0h+RequiredSize], 0; BOOLEAN
0x1400262d7  mov     r13d, 28h ; '('
0x1400262dd  mov     dword ptr [rsp+0B0h+Data], r13d; ULONG
0x1400262e2  xor     r9d, r9d; InputBufferLength
0x1400262e5  xor     r8d, r8d; InputBuffer
0x1400262e8  mov     qword ptr [rsp+0B0h+Size], rax; PVOID
0x1400262ed  mov     edx, 2D1084h; IoControlCode
0x1400262f2  call    ?PmSendDeviceControl@@YAJPEAU_DEVICE_OBJECT@@KPEAXK1KE@Z; PmSendDeviceControl(_DEVICE_OBJECT *,ulong,void *,ulong,void *,ulong,uchar)
0x1400262f7  mov     rcx, [rdi+10h]; DeviceObject
0x1400262fb  mov     byte ptr [rsp+0B0h+RequiredSize], 0; BOOLEAN
0x140026300  test    eax, eax
0x140026302  js      short loc_140026349
0x140026304  mov     eax, dword ptr [rbp+57h+var_48]
0x140026307  lea     r8, [rdi+0B0h]; InputBuffer
0x14002630e  movups  xmm0, [rbp+57h+var_48+4]
0x140026312  mov     [rdi+0A8h], eax
0x140026318  mov     r9d, r13d; InputBufferLength
0x14002631b  mov     eax, dword ptr [rbp+57h+var_58+8]
0x14002631e  mov     edx, 2D280Ch; IoControlCode
0x140026323  mov     dword ptr [rsp+0B0h+Data], r13d; ULONG
0x140026328  movdqu  xmmword ptr [rdi+0B8h], xmm0
0x140026330  mov     [rdi+0ACh], eax
0x140026336  mov     [r8+4], r13d
0x14002633a  mov     [r8], r13d
0x14002633d  mov     qword ptr [rsp+0B0h+Size], r8; PVOID
0x140026342  call    ?PmSendDeviceControl@@YAJPEAU_DEVICE_OBJECT@@KPEAXK1KE@Z; PmSendDeviceControl(_DEVICE_OBJECT *,ulong,void *,ulong,void *,ulong,uchar)
0x140026347  jmp     short loc_14002637D
0x140026349  lea     rax, [rbp+57h+var_68]
0x14002634d  mov     dword ptr [rsp+0B0h+Data], 0Ch; ULONG
0x140026355  xor     r9d, r9d; InputBufferLength
0x140026358  mov     qword ptr [rsp+0B0h+Size], rax; PVOID
0x14002635d  xor     r8d, r8d; InputBuffer
0x140026360  mov     edx, 2D1080h; IoControlCode
0x140026365  call    ?PmSendDeviceControl@@YAJPEAU_DEVICE_OBJECT@@KPEAXK1KE@Z; PmSendDeviceControl(_DEVICE_OBJECT *,ulong,void *,ulong,void *,ulong,uchar)
0x14002636a  mov     ebx, eax
0x14002636c  test    eax, eax
0x14002636e  js      loc_140026585
0x140026374  mov     eax, dword ptr [rbp+57h+var_68+4]
0x140026377  mov     [rdi+0A8h], eax
0x14002637d  lea     rdx, [rdi+0D8h]; struct _GUID *
0x140026384  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x140026387  call    ?PmGetRegistryId@@YAJPEAU_DEVICE_EXTENSION@@PEAU_GUID@@@Z; PmGetRegistryId(_DEVICE_EXTENSION *,_GUID *)
0x14002638c  mov     ebx, eax
0x14002638e  test    eax, eax
0x140026390  js      loc_140026585
0x140026396  lea     rsi, [rdi+0E8h]
0x14002639d  mov     r8d, r13d; unsigned int
0x1400263a0  mov     r9, rsi; void **
0x1400263a3  xor     edx, edx; enum _STORAGE_PROPERTY_ID
0x1400263a5  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x1400263a8  call    ?PmQueryStorageProperty@@YAJPEAU_DEVICE_EXTENSION@@W4_STORAGE_PROPERTY_ID@@KPEAPEAX@Z; PmQueryStorageProperty(_DEVICE_EXTENSION *,_STORAGE_PROPERTY_ID,ulong,void * *)
0x1400263ad  mov     ebx, eax
0x1400263af  test    eax, eax
0x1400263b1  js      loc_140026585
0x1400263b7  mov     rcx, [rsi]; struct _STORAGE_DEVICE_DESCRIPTOR *
0x1400263ba  lea     rax, [rdi+188h]
0x1400263c1  lea     r14, [rdi+178h]
0x1400263c8  mov     qword ptr [rsp+0B0h+Size], rax; struct _UNICODE_STRING *
0x1400263cd  mov     r9, r14; struct _UNICODE_STRING *
0x1400263d0  lea     r8, [rdi+168h]; struct _UNICODE_STRING *
0x1400263d7  lea     rdx, [rdi+158h]; struct _UNICODE_STRING *
0x1400263de  call    ?ScExtractDeviceStrings@@YAJPEAU_STORAGE_DEVICE_DESCRIPTOR@@PEAU_UNICODE_STRING@@111@Z; ScExtractDeviceStrings(_STORAGE_DEVICE_DESCRIPTOR *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *)
0x1400263e3  mov     ebx, eax
0x1400263e5  test    eax, eax
0x1400263e7  js      loc_140026585
0x1400263ed  mov     rdx, [rsi]
0x1400263f0  lea     rbx, [rdi+0F0h]
0x1400263f7  mov     r8, rbx; struct _STORAGE_HW_FIRMWARE_INFO **
0x1400263fa  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x1400263fd  mov     edx, [rdx+1Ch]; enum _STORAGE_BUS_TYPE
0x140026400  call    ?PmGetFirmwareInfo@@YAJPEAU_DEVICE_EXTENSION@@W4_STORAGE_BUS_TYPE@@PEAPEAU_STORAGE_HW_FIRMWARE_INFO@@@Z; PmGetFirmwareInfo(_DEVICE_EXTENSION *,_STORAGE_BUS_TYPE,_STORAGE_HW_FIRMWARE_INFO * *)
0x140026405  mov     rcx, [rbx]; struct _STORAGE_HW_FIRMWARE_INFO *
0x140026408  test    rcx, rcx
0x14002640b  jz      short loc_14002641F
0x14002640d  mov     rdx, r14; struct _UNICODE_STRING *
0x140026410  call    ?ScExtractFirmwareRevision@@YAJPEAU_STORAGE_HW_FIRMWARE_INFO@@PEAU_UNICODE_STRING@@@Z; ScExtractFirmwareRevision(_STORAGE_HW_FIRMWARE_INFO *,_UNICODE_STRING *)
0x140026415  mov     ebx, eax
0x140026417  test    eax, eax
0x140026419  js      loc_140026585
0x14002641f  mov     edx, 2; enum _STORAGE_PROPERTY_ID
0x140026424  lea     r9, [rdi+0F8h]; void **
0x14002642b  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x14002642e  lea     r8d, [rdx+0Eh]; unsigned int
0x140026432  call    ?PmQueryStorageProperty@@YAJPEAU_DEVICE_EXTENSION@@W4_STORAGE_PROPERTY_ID@@KPEAPEAX@Z; PmQueryStorageProperty(_DEVICE_EXTENSION *,_STORAGE_PROPERTY_ID,ulong,void * *)
0x140026437  mov     rax, [rdi+8]
0x14002643b  mov     ebx, 1Ch
0x140026440  test    dword ptr [rax+34h], 40001h
0x140026447  jnz     short loc_14002645E
0x140026449  lea     r9, [rdi+100h]; void **
0x140026450  mov     r8d, ebx; unsigned int
0x140026453  lea     edx, [rbx-18h]; enum _STORAGE_PROPERTY_ID
0x140026456  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x140026459  call    ?PmQueryStorageProperty@@YAJPEAU_DEVICE_EXTENSION@@W4_STORAGE_PROPERTY_ID@@KPEAPEAX@Z; PmQueryStorageProperty(_DEVICE_EXTENSION *,_STORAGE_PROPERTY_ID,ulong,void * *)
0x14002645e  lea     r9, [rdi+108h]; void **
0x140026465  mov     r8d, ebx; unsigned int
0x140026468  mov     edx, 6; enum _STORAGE_PROPERTY_ID
0x14002646d  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x140026470  call    ?PmQueryStorageProperty@@YAJPEAU_DEVICE_EXTENSION@@W4_STORAGE_PROPERTY_ID@@KPEAPEAX@Z; PmQueryStorageProperty(_DEVICE_EXTENSION *,_STORAGE_PROPERTY_ID,ulong,void * *)
0x140026475  mov     ebx, 0Ch
0x14002647a  lea     r9, [rdi+110h]; void **
0x140026481  mov     r8d, ebx; unsigned int
0x140026484  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x140026487  lea     edx, [rbx-5]; enum _STORAGE_PROPERTY_ID
0x14002648a  call    ?PmQueryStorageProperty@@YAJPEAU_DEVICE_EXTENSION@@W4_STORAGE_PROPERTY_ID@@KPEAPEAX@Z; PmQueryStorageProperty(_DEVICE_EXTENSION *,_STORAGE_PROPERTY_ID,ulong,void * *)
0x14002648f  lea     r9, [rdi+118h]; void **
0x140026496  mov     r8d, ebx; unsigned int
0x140026499  lea     edx, [rbx-4]; enum _STORAGE_PROPERTY_ID
0x14002649c  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x14002649f  call    ?PmQueryStorageProperty@@YAJPEAU_DEVICE_EXTENSION@@W4_STORAGE_PROPERTY_ID@@KPEAPEAX@Z; PmQueryStorageProperty(_DEVICE_EXTENSION *,_STORAGE_PROPERTY_ID,ulong,void * *)
0x1400264a4  lea     r9, [rdi+120h]; void **
0x1400264ab  mov     r8d, r13d; unsigned int
0x1400264ae  lea     edx, [rbx-1]; enum _STORAGE_PROPERTY_ID
0x1400264b1  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x1400264b4  call    ?PmQueryStorageProperty@@YAJPEAU_DEVICE_EXTENSION@@W4_STORAGE_PROPERTY_ID@@KPEAPEAX@Z; PmQueryStorageProperty(_DEVICE_EXTENSION *,_STORAGE_PROPERTY_ID,ulong,void * *)
0x1400264b9  mov     ebx, 20h ; ' '
0x1400264be  lea     r9, [rdi+128h]; void **
0x1400264c5  mov     r8d, ebx; unsigned int
0x1400264c8  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x1400264cb  lea     edx, [rbx-12h]; enum _STORAGE_PROPERTY_ID
0x1400264ce  call    ?PmQueryStorageProperty@@YAJPEAU_DEVICE_EXTENSION@@W4_STORAGE_PROPERTY_ID@@KPEAPEAX@Z; PmQueryStorageProperty(_DEVICE_EXTENSION *,_STORAGE_PROPERTY_ID,ulong,void * *)
0x1400264d3  lea     r9, [rdi+130h]; void **
0x1400264da  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x1400264dd  lea     edx, [rbx+1Ch]; enum _STORAGE_PROPERTY_ID
0x1400264e0  lea     r8d, [rbx+10h]; unsigned int
0x1400264e4  call    ?PmQueryStorageProperty@@YAJPEAU_DEVICE_EXTENSION@@W4_STORAGE_PROPERTY_ID@@KPEAPEAX@Z; PmQueryStorageProperty(_DEVICE_EXTENSION *,_STORAGE_PROPERTY_ID,ulong,void * *)
0x1400264e9  lea     rdx, [rdi+138h]; struct _SRB_IO_CONTROL_HYBRID **
0x1400264f0  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x1400264f3  call    ?PmGetHybridInfo@@YAJPEAU_DEVICE_EXTENSION@@PEAPEAU_SRB_IO_CONTROL_HYBRID@@@Z; PmGetHybridInfo(_DEVICE_EXTENSION *,_SRB_IO_CONTROL_HYBRID * *)
0x1400264f8  lea     r9, [rdi+140h]; void **
0x1400264ff  mov     r8d, ebx; unsigned int
0x140026502  lea     edx, [rbx-1Fh]; enum _STORAGE_PROPERTY_ID
0x140026505  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x140026508  call    ?PmQueryStorageProperty@@YAJPEAU_DEVICE_EXTENSION@@W4_STORAGE_PROPERTY_ID@@KPEAPEAX@Z; PmQueryStorageProperty(_DEVICE_EXTENSION *,_STORAGE_PROPERTY_ID,ulong,void * *)
0x14002650d  lea     r9, [rdi+148h]; void **
0x140026514  mov     r8d, 108h; unsigned int
0x14002651a  lea     edx, [rbx+19h]; enum _STORAGE_PROPERTY_ID
0x14002651d  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x140026520  call    ?PmQueryStorageProperty@@YAJPEAU_DEVICE_EXTENSION@@W4_STORAGE_PROPERTY_ID@@KPEAPEAX@Z; PmQueryStorageProperty(_DEVICE_EXTENSION *,_STORAGE_PROPERTY_ID,ulong,void * *)
0x140026525  lea     r9, [rdi+150h]; void **
0x14002652c  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x14002652f  lea     edx, [rbx-1Bh]; enum _STORAGE_PROPERTY_ID
0x140026532  lea     r8d, [rbx-8]; unsigned int
0x140026536  call    ?PmQueryStorageProperty@@YAJPEAU_DEVICE_EXTENSION@@W4_STORAGE_PROPERTY_ID@@KPEAPEAX@Z; PmQueryStorageProperty(_DEVICE_EXTENSION *,_STORAGE_PROPERTY_ID,ulong,void * *)
0x14002653b  mov     rcx, [rdi+10h]; DeviceObject
0x14002653f  lea     rdx, [rdi+30h]; NestingLevel
0x140026543  xor     r8d, r8d; NestingFlags
0x140026546  call    cs:__imp_FsRtlGetVirtualDiskNestingLevel
0x14002654d  nop     dword ptr [rax+rax+00h]
0x140026552  test    eax, eax
0x140026554  jns     short loc_14002655D
0x140026556  mov     dword ptr [rdi+30h], 0
0x14002655d  mov     rdx, r15; struct _IRP *
0x140026560  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x140026563  call    ?PmConstructDeviceLocation@@YAJPEAU_DEVICE_EXTENSION@@PEAU_IRP@@@Z; PmConstructDeviceLocation(_DEVICE_EXTENSION *,_IRP *)
0x140026568  mov     ebx, eax
0x14002656a  test    eax, eax
0x14002656c  js      short loc_140026585
0x14002656e  mov     rcx, [rdi+18h]; struct _DEVICE_OBJECT *
0x140026572  lea     r8, [rdi+1D0h]; struct _UNICODE_STRING *
0x140026579  lea     rdx, DEVPKEY_Device_Parent; struct _DEVPROPKEY *
0x140026580  call    ?PmGetDevicePropertyString@@YAJPEAU_DEVICE_OBJECT@@PEBU_DEVPROPKEY@@PEAU_UNICODE_STRING@@@Z; PmGetDevicePropertyString(_DEVICE_OBJECT *,_DEVPROPKEY const *,_UNICODE_STRING *)
0x140026585  mov     eax, ebx
0x140026587  mov     rcx, [rbp+57h+var_30]
0x14002658b  xor     rcx, rsp; StackCookie
0x14002658e  call    __security_check_cookie
0x140026593  lea     r11, [rsp+0B0h+var_20]
0x14002659b  mov     rbx, [r11+40h]
0x14002659f  mov     rsi, [r11+48h]
0x1400265a3  mov     rsp, r11
0x1400265a6  pop     r15
0x1400265a8  pop     r14
0x1400265aa  pop     r13
0x1400265ac  pop     rdi
0x1400265ad  pop     rbp
0x1400265ae  retn
```
