# PmConstructDeviceLocation(_DEVICE_EXTENSION *,_IRP *)

- ea: `0x14002366c`
- end: `0x140023926`
- name: `?PmConstructDeviceLocation@@YAJPEAU_DEVICE_EXTENSION@@PEAU_IRP@@@Z`
- size: `698`
- prototype: `__int64 __fastcall(struct _DEVICE_EXTENSION *, struct _IRP *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1400261fc`

## callees

- `0x140010f20`
- `0x140011440`
- `0x14001f99c`
- `0x14001fa44`
- `0x14002366c`
- `0x140023cb4`
- `0x1400243b0`
- `0x140024844`

## import_xrefs

- `ntoskrnl!IoSynchronousCallDriver` at `0x140023733`
- `ntoskrnl!IoSynchronousCallDriver` at `0x140023733`
- `ntoskrnl!IoGetDevicePropertyData` at `0x140023789`
- `ntoskrnl!IoGetDevicePropertyData` at `0x1400237d1`
- `ntoskrnl!IoGetDevicePropertyData` at `0x140023789`
- `ntoskrnl!IoGetDevicePropertyData` at `0x1400237d1`

## pseudocode

```c
__int64 __fastcall PmConstructDeviceLocation(struct _DEVICE_EXTENSION *a1, struct _IRP *a2)
{
  __int64 v4; // rax
  struct _DEVICE_OBJECT *v5; // rsi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  unsigned int DevicePropertyString; // ebx
  int v8; // ecx
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  int v14; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int v20; // ecx
  int v21; // ecx
  int v22; // ecx
  unsigned int v23; // [rsp+40h] [rbp-29h] BYREF
  int Data; // [rsp+44h] [rbp-25h] BYREF
  ULONG Type; // [rsp+48h] [rbp-21h] BYREF
  ULONG RequiredSize; // [rsp+4Ch] [rbp-1Dh] BYREF
  __int64 v27; // [rsp+50h] [rbp-19h] BYREF
  _DWORD v28[16]; // [rsp+60h] [rbp-9h] BYREF

  RequiredSize = 0;
  memset(v28, 0, sizeof(v28));
  v4 = *((_QWORD *)a1 + 3);
  if ( v4 )
    v4 = *(_QWORD *)(*(_QWORD *)(v4 + 312) + 40LL);
  v5 = 0;
  v23 = 0;
  Data = 0;
  v27 = 0;
  Type = 0;
  if ( v4 )
    v5 = *(struct _DEVICE_OBJECT **)(*(_QWORD *)(v4 + 16) + 32LL);
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  v28[0] = 65600;
  v28[3] = -1;
  v28[2] = -1;
  memset(&CurrentStackLocation[-1], 0, sizeof(struct _IO_STACK_LOCATION));
  *(_WORD *)&CurrentStackLocation[-1].MajorFunction = 2331;
  CurrentStackLocation[-1].Parameters.WMI.ProviderId = (ULONG_PTR)v28;
  a2->IoStatus.Status = -1073741637;
  a2->IoStatus.Information = 0;
  if ( (int)IoSynchronousCallDriver(*((_QWORD *)a1 + 2), a2) >= 0 )
    *((_DWORD *)a1 + 103) = v28[3];
  if ( v5 )
  {
    if ( IoGetDevicePropertyData(v5, &DEVPKEY_Device_BusNumber, 0, 0, 4u, &Data, &RequiredSize, &Type) >= 0 )
      *((_DWORD *)a1 + 108) = Data;
    if ( IoGetDevicePropertyData(v5, &DEVPKEY_Device_Address, 0, 0, 4u, &v23, &RequiredSize, &Type) >= 0 )
    {
      *((_DWORD *)a1 + 109) = HIWORD(v23);
      *((_DWORD *)a1 + 110) = (unsigned __int16)v23;
    }
  }
  DevicePropertyString = PmSendDeviceControl(*((PDEVICE_OBJECT *)a1 + 2), 0x41018u, 0, 0, &v27, 8u, 0);
  if ( (DevicePropertyString & 0x80000000) != 0 )
  {
    DevicePropertyString = 0;
  }
  else
  {
    *((_DWORD *)a1 + 104) = BYTE4(v27);
    *((_DWORD *)a1 + 105) = BYTE5(v27);
    *((_DWORD *)a1 + 106) = BYTE6(v27);
    *((_DWORD *)a1 + 107) = HIBYTE(v27);
  }
  v8 = *(_DWORD *)(*((_QWORD *)a1 + 29) + 28LL);
  if ( v8 > 9 )
  {
    v16 = v8 - 10;
    if ( !v16 )
      return (unsigned int)PmConstructDeviceLocationDefault(a1);
    v17 = v16 - 1;
    if ( !v17 )
      return (unsigned int)PmConstructDeviceLocationDefault(a1);
    v18 = v17 - 1;
    if ( !v18 )
      return (unsigned int)PmConstructDeviceLocationDefault(a1);
    v19 = v18 - 1;
    if ( !v19 )
      return (unsigned int)PmConstructDeviceLocationDefault(a1);
    v20 = v19 - 2;
    if ( !v20 )
    {
      PmConstructDeviceLocationVhd(a1);
      return DevicePropertyString;
    }
    v21 = v20 - 2;
    if ( !v21 )
    {
      if ( !v5 )
        return (unsigned int)PmConstructDeviceLocationDefault(a1);
      DevicePropertyString = PmGetDevicePropertyString(
                               v5,
                               &DEVPKEY_PciDevice_Label_String,
                               (struct _UNICODE_STRING *)a1 + 28);
      if ( (DevicePropertyString & 0x80000000) != 0 )
        return (unsigned int)PmConstructDeviceLocationDefault(a1);
      return DevicePropertyString;
    }
    v22 = v21 - 2;
    if ( !v22 )
      return (unsigned int)PmConstructDeviceLocationDefault(a1);
    if ( v22 != 1 )
      return DevicePropertyString;
LABEL_34:
    PmConstructDeviceLocationNetworkStorage(a1);
    return DevicePropertyString;
  }
  if ( v8 == 9 )
    goto LABEL_34;
  v9 = v8 - 1;
  if ( !v9 )
    return (unsigned int)PmConstructDeviceLocationDefault(a1);
  v10 = v9 - 1;
  if ( !v10 )
    return (unsigned int)PmConstructDeviceLocationDefault(a1);
  v11 = v10 - 1;
  if ( !v11 )
    return (unsigned int)PmConstructDeviceLocationDefault(a1);
  v12 = v11 - 1;
  if ( !v12 )
    return (unsigned int)PmConstructDeviceLocationDefault(a1);
  v13 = v12 - 1;
  if ( !v13 )
    return (unsigned int)PmConstructDeviceLocationDefault(a1);
  v14 = v13 - 1;
  if ( !v14 || (unsigned int)(v14 - 1) <= 1 )
    return (unsigned int)PmConstructDeviceLocationDefault(a1);
  return DevicePropertyString;
}

```

## disassembly

```asm
0x14002366c  mov     [rsp-8+arg_10], rbx
0x140023671  mov     [rsp-8+arg_18], rsi
0x140023676  push    rbp
0x140023677  push    rdi
0x140023678  push    r14
0x14002367a  lea     rbp, [rsp-47h]
0x14002367f  sub     rsp, 0B0h
0x140023686  mov     rax, cs:__security_cookie
0x14002368d  xor     rax, rsp
0x140023690  mov     [rbp+57h+var_20], rax
0x140023694  mov     r14, rdx
0x140023697  mov     [rbp+57h+var_74], 0
0x14002369e  xor     edx, edx; Val
0x1400236a0  mov     rdi, rcx
0x1400236a3  lea     rcx, [rbp+57h+var_60]; void *
0x1400236a7  lea     r8d, [rdx+40h]; Size
0x1400236ab  call    memset
0x1400236b0  mov     rax, [rdi+18h]
0x1400236b4  test    rax, rax
0x1400236b7  jz      short loc_1400236C4
0x1400236b9  mov     rax, [rax+138h]
0x1400236c0  mov     rax, [rax+28h]
0x1400236c4  xor     esi, esi
0x1400236c6  mov     [rbp+57h+var_80], 0
0x1400236cd  mov     [rbp+57h+var_7C], 0
0x1400236d4  mov     [rbp+57h+var_70], rsi
0x1400236d8  mov     [rbp+57h+var_78], esi
0x1400236db  test    rax, rax
0x1400236de  jz      short loc_1400236E8
0x1400236e0  mov     rax, [rax+10h]
0x1400236e4  mov     rsi, [rax+20h]
0x1400236e8  mov     rbx, [r14+0B8h]
0x1400236ef  or      eax, 0FFFFFFFFh
0x1400236f2  xor     edx, edx; Val
0x1400236f4  mov     [rbp+57h+var_60], 10040h
0x1400236fb  mov     [rbp+57h+var_54], eax
0x1400236fe  mov     [rbp+57h+var_58], eax
0x140023701  lea     rcx, [rbx-48h]; void *
0x140023705  lea     r8d, [rdx+48h]; Size
0x140023709  call    memset
0x14002370e  mov     word ptr [rbx-48h], 91Bh
0x140023714  lea     rax, [rbp+57h+var_60]
0x140023718  mov     [rbx-40h], rax
0x14002371c  mov     rdx, r14
0x14002371f  mov     dword ptr [r14+30h], 0C00000BBh
0x140023727  mov     qword ptr [r14+38h], 0
0x14002372f  mov     rcx, [rdi+10h]
0x140023733  call    cs:__imp_IoSynchronousCallDriver
0x14002373a  nop     dword ptr [rax+rax+00h]
0x14002373f  test    eax, eax
0x140023741  js      short loc_14002374C
0x140023743  mov     eax, [rbp+57h+var_54]
0x140023746  mov     [rdi+19Ch], eax
0x14002374c  test    rsi, rsi
0x14002374f  jz      loc_1400237F7
0x140023755  lea     rax, [rbp+57h+var_78]
0x140023759  mov     ebx, 4
0x14002375e  mov     [rsp+0C0h+Type], rax; Type
0x140023763  lea     rdx, DEVPKEY_Device_BusNumber; PropertyKey
0x14002376a  lea     rax, [rbp+57h+var_74]
0x14002376e  xor     r9d, r9d; Flags
0x140023771  mov     [rsp+0C0h+RequiredSize], rax; RequiredSize
0x140023776  xor     r8d, r8d; Lcid
0x140023779  lea     rax, [rbp+57h+var_7C]
0x14002377d  mov     rcx, rsi; Pdo
0x140023780  mov     [rsp+0C0h+Data], rax; Data
0x140023785  mov     [rsp+0C0h+Size], ebx; Size
0x140023789  call    cs:__imp_IoGetDevicePropertyData
0x140023790  nop     dword ptr [rax+rax+00h]
0x140023795  test    eax, eax
0x140023797  js      short loc_1400237A2
0x140023799  mov     eax, [rbp+57h+var_7C]
0x14002379c  mov     [rdi+1B0h], eax
0x1400237a2  lea     rax, [rbp+57h+var_78]
0x1400237a6  xor     r9d, r9d; Flags
0x1400237a9  mov     [rsp+0C0h+Type], rax; Type
0x1400237ae  lea     rdx, DEVPKEY_Device_Address; PropertyKey
0x1400237b5  lea     rax, [rbp+57h+var_74]
0x1400237b9  xor     r8d, r8d; Lcid
0x1400237bc  mov     [rsp+0C0h+RequiredSize], rax; RequiredSize
0x1400237c1  mov     rcx, rsi; Pdo
0x1400237c4  lea     rax, [rbp+57h+var_80]
0x1400237c8  mov     [rsp+0C0h+Data], rax; Data
0x1400237cd  mov     [rsp+0C0h+Size], ebx; Size
0x1400237d1  call    cs:__imp_IoGetDevicePropertyData
0x1400237d8  nop     dword ptr [rax+rax+00h]
0x1400237dd  test    eax, eax
0x1400237df  js      short loc_1400237F7
0x1400237e1  mov     eax, [rbp+57h+var_80]
0x1400237e4  shr     eax, 10h
0x1400237e7  mov     [rdi+1B4h], eax
0x1400237ed  movzx   eax, word ptr [rbp+57h+var_80]
0x1400237f1  mov     [rdi+1B8h], eax
0x1400237f7  mov     rcx, [rdi+10h]; DeviceObject
0x1400237fb  lea     rax, [rbp+57h+var_70]
0x1400237ff  mov     byte ptr [rsp+0C0h+RequiredSize], 0; BOOLEAN
0x140023804  xor     r9d, r9d; InputBufferLength
0x140023807  mov     dword ptr [rsp+0C0h+Data], 8; ULONG
0x14002380f  xor     r8d, r8d; InputBuffer
0x140023812  mov     edx, 41018h; IoControlCode
0x140023817  mov     qword ptr [rsp+0C0h+Size], rax; PVOID
0x14002381c  call    ?PmSendDeviceControl@@YAJPEAU_DEVICE_OBJECT@@KPEAXK1KE@Z; PmSendDeviceControl(_DEVICE_OBJECT *,ulong,void *,ulong,void *,ulong,uchar)
0x140023821  mov     ebx, eax
0x140023823  test    eax, eax
0x140023825  js      short loc_140023851
0x140023827  movzx   ecx, byte ptr [rbp+57h+var_70+4]
0x14002382b  mov     [rdi+1A0h], ecx
0x140023831  movzx   ecx, byte ptr [rbp+57h+var_70+5]
0x140023835  mov     [rdi+1A4h], ecx
0x14002383b  movzx   ecx, byte ptr [rbp+57h+var_70+6]
0x14002383f  mov     [rdi+1A8h], ecx
0x140023845  movzx   ecx, byte ptr [rbp+57h+var_70+7]
0x140023849  mov     [rdi+1ACh], ecx
0x14002384f  jmp     short loc_140023853
0x140023851  xor     ebx, ebx
0x140023853  mov     rax, [rdi+0E8h]
0x14002385a  mov     ecx, [rax+1Ch]
0x14002385d  cmp     ecx, 9
0x140023860  jg      short loc_1400238C1
0x140023862  jz      loc_1400238E9
0x140023868  sub     ecx, 1
0x14002386b  jz      short loc_140023890
0x14002386d  sub     ecx, 1
0x140023870  jz      short loc_140023890
0x140023872  sub     ecx, 1
0x140023875  jz      short loc_140023890
0x140023877  sub     ecx, 1
0x14002387a  jz      short loc_140023890
0x14002387c  sub     ecx, 1
0x14002387f  jz      short loc_140023890
0x140023881  sub     ecx, 1
0x140023884  jz      short loc_140023890
0x140023886  sub     ecx, 1
0x140023889  jz      short loc_140023890
0x14002388b  cmp     ecx, 1
0x14002388e  jnz     short loc_14002389A
0x140023890  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x140023893  call    ?PmConstructDeviceLocationDefault@@YAJPEAU_DEVICE_EXTENSION@@@Z; PmConstructDeviceLocationDefault(_DEVICE_EXTENSION *)
0x140023898  mov     ebx, eax
0x14002389a  mov     eax, ebx
0x14002389c  mov     rcx, [rbp+57h+var_20]
0x1400238a0  xor     rcx, rsp; StackCookie
0x1400238a3  call    __security_check_cookie
0x1400238a8  lea     r11, [rsp+0C0h+var_10]
0x1400238b0  mov     rbx, [r11+30h]
0x1400238b4  mov     rsi, [r11+38h]
0x1400238b8  mov     rsp, r11
0x1400238bb  pop     r14
0x1400238bd  pop     rdi
0x1400238be  pop     rbp
0x1400238bf  retn
0x1400238c1  sub     ecx, 0Ah
0x1400238c4  jz      short loc_140023890
0x1400238c6  sub     ecx, 1
0x1400238c9  jz      short loc_140023890
0x1400238cb  sub     ecx, 1
0x1400238ce  jz      short loc_140023890
0x1400238d0  sub     ecx, 1
0x1400238d3  jz      short loc_140023890
0x1400238d5  sub     ecx, 2
0x1400238d8  jz      short loc_140023919
0x1400238da  sub     ecx, 2
0x1400238dd  jz      short loc_1400238F3
0x1400238df  sub     ecx, 2
0x1400238e2  jz      short loc_140023890
0x1400238e4  cmp     ecx, 1
0x1400238e7  jnz     short loc_14002389A
0x1400238e9  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x1400238ec  call    ?PmConstructDeviceLocationNetworkStorage@@YAJPEAU_DEVICE_EXTENSION@@@Z; PmConstructDeviceLocationNetworkStorage(_DEVICE_EXTENSION *)
0x1400238f1  jmp     short loc_14002389A
0x1400238f3  test    rsi, rsi
0x1400238f6  jz      short loc_140023890
0x1400238f8  lea     r8, [rdi+1C0h]; struct _UNICODE_STRING *
0x1400238ff  mov     rcx, rsi; struct _DEVICE_OBJECT *
0x140023902  lea     rdx, DEVPKEY_PciDevice_Label_String; struct _DEVPROPKEY *
0x140023909  call    ?PmGetDevicePropertyString@@YAJPEAU_DEVICE_OBJECT@@PEBU_DEVPROPKEY@@PEAU_UNICODE_STRING@@@Z; PmGetDevicePropertyString(_DEVICE_OBJECT *,_DEVPROPKEY const *,_UNICODE_STRING *)
0x14002390e  mov     ebx, eax
0x140023910  test    eax, eax
0x140023912  jns     short loc_14002389A
0x140023914  jmp     loc_140023890
0x140023919  mov     rcx, rdi; struct _DEVICE_EXTENSION *
0x14002391c  call    ?PmConstructDeviceLocationVhd@@YAJPEAU_DEVICE_EXTENSION@@@Z; PmConstructDeviceLocationVhd(_DEVICE_EXTENSION *)
0x140023921  jmp     loc_14002389A
```
