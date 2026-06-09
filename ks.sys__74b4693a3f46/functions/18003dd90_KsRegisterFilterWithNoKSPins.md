# KsRegisterFilterWithNoKSPins

- ea: `0x18003dd90`
- end: `0x18003e0a9`
- name: `KsRegisterFilterWithNoKSPins`
- size: `793`
- prototype: `NTSTATUS __stdcall(PDEVICE_OBJECT DeviceObject, const GUID *InterfaceClassGUID, ULONG PinCount, BOOL *PinDirection, KSPIN_MEDIUM *MediumList, GUID *CategoryList)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, registry_config`

## callers

- `0x1800716f0`

## callees

- `0x180019fc0`
- `0x1800340d0`
- `0x18003dd90`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x18003dfb8`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003dff5`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003dfb8`
- `ntoskrnl!RtlInitUnicodeString` at `0x18003dff5`
- `ntoskrnl!ZwClose` at `0x18003e030`
- `ntoskrnl!ZwClose` at `0x18003e030`
- `ntoskrnl!ZwSetValueKey` at `0x18003e01e`
- `ntoskrnl!ZwSetValueKey` at `0x18003e01e`
- `ntoskrnl!IoOpenDeviceInterfaceRegistryKey` at `0x18003dfd1`
- `ntoskrnl!IoOpenDeviceInterfaceRegistryKey` at `0x18003dfd1`
- `ntoskrnl!IoGetDeviceInterfaces` at `0x18003df8b`
- `ntoskrnl!IoGetDeviceInterfaces` at `0x18003df8b`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003e06a`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003e07b`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003e06a`
- `ntoskrnl!ExFreePoolWithTag` at `0x18003e07b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18003de0c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x18003de0c`

## pseudocode

```c
NTSTATUS __stdcall KsRegisterFilterWithNoKSPins(
        PDEVICE_OBJECT DeviceObject,
        const GUID *InterfaceClassGUID,
        ULONG PinCount,
        BOOL *PinDirection,
        KSPIN_MEDIUM *MediumList,
        GUID *CategoryList)
{
  __int64 v6; // rdi
  SIZE_T v9; // rsi
  _DWORD *PoolWithTag; // rax
  _DWORD *v11; // rbx
  void *Data; // r15
  int v13; // r10d
  _DWORD *v14; // rbx
  _DWORD *v15; // r8
  GUID *v16; // rsi
  unsigned int v17; // r11d
  __int64 v18; // r9
  bool v19; // cf
  __int64 v20; // rax
  __int64 v22; // r9
  __int64 v23; // rax
  GUID Set; // xmm0
  int DeviceInterfaces; // ebx
  __int64 i; // rsi
  void *DeviceInterfaceRegKey; // [rsp+30h] [rbp-30h] BYREF
  PZZWSTR SymbolicLinkList; // [rsp+38h] [rbp-28h] BYREF
  UNICODE_STRING DestinationString; // [rsp+40h] [rbp-20h] BYREF
  UNICODE_STRING ValueName; // [rsp+50h] [rbp-10h] BYREF

  v6 = PinCount;
  SymbolicLinkList = 0;
  if ( !PinCount || !InterfaceClassGUID || !PinDirection || !MediumList )
    return -1073741808;
  v9 = 16 * (CategoryList != 0 ? PinCount + 1 : 1) + 52 * PinCount;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)1025, v9, 0x6466534Bu);
  v11 = PoolWithTag;
  if ( ExPoolZeroingNativelySupported )
  {
    if ( PoolWithTag )
      goto LABEL_8;
    return -1073741670;
  }
  if ( !PoolWithTag )
    return -1073741670;
  memset(PoolWithTag, 0, (unsigned int)v9);
LABEL_8:
  Data = v11;
  *v11 = 2;
  v13 = (int)v11;
  v11[1] = 0x200000;
  v11[2] = v6;
  v11[3] = 0;
  v14 = v11 + 4;
  v15 = &v14[7 * v6];
  v16 = (GUID *)&v15[6 * v6];
  if ( (_DWORD)v6 )
  {
    v17 = 0;
    if ( CategoryList )
    {
      v18 = 0;
      do
      {
        *v14 = 862548016;
        *(_BYTE *)v14 = v17 + 48;
        v14 += 7;
        v19 = PinDirection[v18];
        *(_QWORD *)(v14 - 5) = 1;
        *(v14 - 3) = 1;
        *(v14 - 1) = (_DWORD)v15 - v13;
        *(v14 - 6) = v19 ? 8 : 0;
        ++v17;
        *(KSPIN_MEDIUM *)v15 = MediumList[v18];
        *(v14 - 2) = (_DWORD)v16 - v13;
        v15 += 6;
        v20 = v18++;
        *v16++ = CategoryList[v20];
      }
      while ( v17 < (unsigned int)v6 );
    }
    else
    {
      v22 = 0;
      do
      {
        *v14 = 862548016;
        *(_BYTE *)v14 = v22 + 48;
        v14 += 7;
        v19 = PinDirection[v22];
        *(_QWORD *)(v14 - 5) = 1;
        *(v14 - 3) = 1;
        *(v14 - 1) = (_DWORD)v15 - v13;
        *(v14 - 6) = v19 ? 8 : 0;
        v23 = v22;
        Set = MediumList[v22].Set;
        v22 = (unsigned int)(v22 + 1);
        *(GUID *)v15 = Set;
        *((_QWORD *)v15 + 2) = *(&MediumList[v23].Alignment + 2);
        v15 += 6;
        *(v14 - 2) = 0;
      }
      while ( (unsigned int)v22 < (unsigned int)v6 );
    }
  }
  DeviceInterfaces = IoGetDeviceInterfaces(InterfaceClassGUID, DeviceObject, 1u, &SymbolicLinkList);
  if ( DeviceInterfaces >= 0 )
  {
    DeviceInterfaceRegKey = 0;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, SymbolicLinkList);
    DeviceInterfaces = IoOpenDeviceInterfaceRegistryKey(&DestinationString, 0x1F0000u, &DeviceInterfaceRegKey);
    if ( DeviceInterfaces >= 0 )
    {
      ValueName = 0;
      RtlInitUnicodeString(&ValueName, L"FilterData");
      DeviceInterfaces = ZwSetValueKey(
                           DeviceInterfaceRegKey,
                           &ValueName,
                           0,
                           3u,
                           Data,
                           16 * (CategoryList != 0 ? v6 + 1 : 1) + 52 * v6);
      ZwClose(DeviceInterfaceRegKey);
    }
    for ( i = 0; (unsigned int)i < (unsigned int)v6; i = (unsigned int)(i + 1) )
      KsCacheMedium(&DestinationString, &MediumList[i], PinDirection[i]);
    ExFreePoolWithTag(SymbolicLinkList, 0);
  }
  ExFreePoolWithTag(Data, 0);
  return DeviceInterfaces;
}

```

## disassembly

```asm
0x18003dd90  mov     [rsp-38h+arg_8], rbx
0x18003dd95  mov     [rsp-38h+PhysicalDeviceObject], rcx
0x18003dd9a  push    rbp
0x18003dd9b  push    rsi
0x18003dd9c  push    rdi
0x18003dd9d  push    r12
0x18003dd9f  push    r13
0x18003dda1  push    r14
0x18003dda3  push    r15
0x18003dda5  mov     rbp, rsp
0x18003dda8  sub     rsp, 60h
0x18003ddac  mov     edi, r8d
0x18003ddaf  mov     r12, r9
0x18003ddb2  mov     [rbp+SymbolicLinkList], 0
0x18003ddba  mov     r13, rdx
0x18003ddbd  test    r8d, r8d
0x18003ddc0  jz      loc_18003E08B
0x18003ddc6  test    rdx, rdx
0x18003ddc9  jz      loc_18003E08B
0x18003ddcf  test    r9, r9
0x18003ddd2  jz      loc_18003E08B
0x18003ddd8  mov     r14, [rbp+MediumList]
0x18003dddc  test    r14, r14
0x18003dddf  jz      loc_18003E08B
0x18003dde5  mov     rax, [rbp+CategoryList]
0x18003dde9  mov     r8d, 6466534Bh; Tag
0x18003ddef  neg     rax
0x18003ddf2  sbb     ecx, ecx
0x18003ddf4  imul    eax, edi, 34h ; '4'
0x18003ddf7  and     ecx, edi
0x18003ddf9  inc     ecx
0x18003ddfb  shl     ecx, 4
0x18003ddfe  add     eax, ecx
0x18003de00  mov     ecx, 401h; PoolType
0x18003de05  mov     edx, eax; NumberOfBytes
0x18003de07  mov     [rbp+arg_10], eax
0x18003de0a  mov     esi, eax
0x18003de0c  call    cs:__imp_ExAllocatePoolWithTag
0x18003de13  nop     dword ptr [rax+rax+00h]
0x18003de18  cmp     cs:ExPoolZeroingNativelySupported, 0
0x18003de1f  mov     rbx, rax
0x18003de22  jnz     loc_18003DF04
0x18003de28  test    rax, rax
0x18003de2b  jz      loc_18003DF0D
0x18003de31  mov     r8d, esi; Size
0x18003de34  xor     edx, edx; Val
0x18003de36  mov     rcx, rax; void *
0x18003de39  call    memset
0x18003de3e  imul    r8, rdi, 1Ch
0x18003de42  mov     r15, rbx
0x18003de45  mov     dword ptr [rbx], 2
0x18003de4b  mov     r10, rbx
0x18003de4e  mov     dword ptr [rbx+4], 200000h
0x18003de55  mov     [rbx+8], edi
0x18003de58  lea     rax, [rdi+rdi*2]
0x18003de5c  mov     dword ptr [rbx+0Ch], 0
0x18003de63  add     rbx, 10h
0x18003de67  add     r8, rbx
0x18003de6a  lea     rsi, [r8+rax*8]
0x18003de6e  test    edi, edi
0x18003de70  jz      loc_18003DF7A
0x18003de76  mov     rdx, [rbp+CategoryList]
0x18003de7a  xor     r11d, r11d
0x18003de7d  test    rdx, rdx
0x18003de80  jz      loc_18003DF17
0x18003de86  xor     r9d, r9d
0x18003de89  mov     dword ptr [rbx], 33697030h
0x18003de8f  lea     eax, [r11+30h]
0x18003de93  mov     [rbx], al
0x18003de95  lea     rbx, [rbx+1Ch]
0x18003de99  mov     eax, [r12+r9*4]
0x18003de9d  neg     eax
0x18003de9f  mov     qword ptr [rbx-14h], 1
0x18003dea7  mov     dword ptr [rbx-0Ch], 1
0x18003deae  mov     eax, r8d
0x18003deb1  sbb     ecx, ecx
0x18003deb3  sub     eax, r10d
0x18003deb6  mov     [rbx-4], eax
0x18003deb9  and     ecx, 8
0x18003debc  mov     [rbx-18h], ecx
0x18003debf  lea     rax, [r9+r9*2]
0x18003dec3  movups  xmm0, xmmword ptr [r14+rax*8]
0x18003dec8  inc     r11d
0x18003decb  movups  xmmword ptr [r8], xmm0
0x18003decf  movsd   xmm1, qword ptr [r14+rax*8+10h]
0x18003ded6  mov     eax, esi
0x18003ded8  sub     eax, r10d
0x18003dedb  movsd   qword ptr [r8+10h], xmm1
0x18003dee1  mov     [rbx-8], eax
0x18003dee4  add     r8, 18h
0x18003dee8  mov     rax, r9
0x18003deeb  inc     r9
0x18003deee  add     rax, rax
0x18003def1  movups  xmm0, xmmword ptr [rdx+rax*8]
0x18003def5  movdqu  xmmword ptr [rsi], xmm0
0x18003def9  add     rsi, 10h
0x18003defd  cmp     r11d, edi
0x18003df00  jb      short loc_18003DE89
0x18003df02  jmp     short loc_18003DF7A
0x18003df04  test    rbx, rbx
0x18003df07  jnz     loc_18003DE3E
0x18003df0d  mov     eax, 0C000009Ah
0x18003df12  jmp     loc_18003E090
0x18003df17  xor     r9d, r9d
0x18003df1a  mov     dword ptr [rbx], 33697030h
0x18003df20  lea     eax, [r9+30h]
0x18003df24  mov     [rbx], al
0x18003df26  lea     rbx, [rbx+1Ch]
0x18003df2a  mov     eax, [r12+r9*4]
0x18003df2e  neg     eax
0x18003df30  mov     qword ptr [rbx-14h], 1
0x18003df38  mov     dword ptr [rbx-0Ch], 1
0x18003df3f  mov     eax, r8d
0x18003df42  sbb     ecx, ecx
0x18003df44  sub     eax, r10d
0x18003df47  mov     [rbx-4], eax
0x18003df4a  and     ecx, 8
0x18003df4d  mov     [rbx-18h], ecx
0x18003df50  lea     rax, [r9+r9*2]
0x18003df54  movups  xmm0, xmmword ptr [r14+rax*8]
0x18003df59  inc     r9d
0x18003df5c  movups  xmmword ptr [r8], xmm0
0x18003df60  movsd   xmm1, qword ptr [r14+rax*8+10h]
0x18003df67  movsd   qword ptr [r8+10h], xmm1
0x18003df6d  add     r8, 18h
0x18003df71  mov     [rbx-8], r11d
0x18003df75  cmp     r9d, edi
0x18003df78  jb      short loc_18003DF1A
0x18003df7a  mov     rdx, [rbp+PhysicalDeviceObject]; PhysicalDeviceObject
0x18003df7e  lea     r9, [rbp+SymbolicLinkList]; SymbolicLinkList
0x18003df82  mov     r8d, 1; Flags
0x18003df88  mov     rcx, r13; InterfaceClassGuid
0x18003df8b  call    cs:__imp_IoGetDeviceInterfaces
0x18003df92  nop     dword ptr [rax+rax+00h]
0x18003df97  mov     ebx, eax
0x18003df99  test    eax, eax
0x18003df9b  js      loc_18003E076
0x18003dfa1  mov     rdx, [rbp+SymbolicLinkList]; SourceString
0x18003dfa5  lea     rcx, [rbp+DestinationString]; DestinationString
0x18003dfa9  xorps   xmm0, xmm0
0x18003dfac  mov     [rbp+DeviceInterfaceRegKey], 0
0x18003dfb4  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18003dfb8  call    cs:__imp_RtlInitUnicodeString
0x18003dfbf  nop     dword ptr [rax+rax+00h]
0x18003dfc4  lea     r8, [rbp+DeviceInterfaceRegKey]; DeviceInterfaceRegKey
0x18003dfc8  mov     edx, 1F0000h; DesiredAccess
0x18003dfcd  lea     rcx, [rbp+DestinationString]; SymbolicLinkName
0x18003dfd1  call    cs:__imp_IoOpenDeviceInterfaceRegistryKey
0x18003dfd8  nop     dword ptr [rax+rax+00h]
0x18003dfdd  mov     ebx, eax
0x18003dfdf  test    eax, eax
0x18003dfe1  js      short loc_18003E03C
0x18003dfe3  xorps   xmm0, xmm0
0x18003dfe6  lea     rdx, aFilterdata; "FilterData"
0x18003dfed  lea     rcx, [rbp+ValueName]; DestinationString
0x18003dff1  movups  xmmword ptr [rbp+ValueName.Length], xmm0
0x18003dff5  call    cs:__imp_RtlInitUnicodeString
0x18003dffc  nop     dword ptr [rax+rax+00h]
0x18003e001  mov     eax, [rbp+arg_10]
0x18003e004  lea     rdx, [rbp+ValueName]; ValueName
0x18003e008  mov     rcx, [rbp+DeviceInterfaceRegKey]; KeyHandle
0x18003e00c  mov     r9d, 3; Type
0x18003e012  mov     [rsp+60h+DataSize], eax; DataSize
0x18003e016  xor     r8d, r8d; TitleIndex
0x18003e019  mov     [rsp+60h+Data], r15; Data
0x18003e01e  call    cs:__imp_ZwSetValueKey
0x18003e025  nop     dword ptr [rax+rax+00h]
0x18003e02a  mov     rcx, [rbp+DeviceInterfaceRegKey]; Handle
0x18003e02e  mov     ebx, eax
0x18003e030  call    cs:__imp_ZwClose
0x18003e037  nop     dword ptr [rax+rax+00h]
0x18003e03c  xor     esi, esi
0x18003e03e  test    edi, edi
0x18003e040  jz      short loc_18003E064
0x18003e042  xor     r8d, r8d
0x18003e045  lea     rax, [rsi+rsi*2]
0x18003e049  cmp     [r12+rsi*4], r8d
0x18003e04d  lea     rdx, [r14+rax*8]; Medium
0x18003e051  lea     rcx, [rbp+DestinationString]; SymbolicLink
0x18003e055  setnz   r8b; PinDirection
0x18003e059  call    KsCacheMedium
0x18003e05e  inc     esi
0x18003e060  cmp     esi, edi
0x18003e062  jb      short loc_18003E042
0x18003e064  mov     rcx, [rbp+SymbolicLinkList]; P
0x18003e068  xor     edx, edx; Tag
0x18003e06a  call    cs:__imp_ExFreePoolWithTag
0x18003e071  nop     dword ptr [rax+rax+00h]
0x18003e076  xor     edx, edx; Tag
0x18003e078  mov     rcx, r15; P
0x18003e07b  call    cs:__imp_ExFreePoolWithTag
0x18003e082  nop     dword ptr [rax+rax+00h]
0x18003e087  mov     eax, ebx
0x18003e089  jmp     short loc_18003E090
0x18003e08b  mov     eax, 0C0000010h
0x18003e090  mov     rbx, [rsp+60h+arg_8]
0x18003e098  add     rsp, 60h
0x18003e09c  pop     r15
0x18003e09e  pop     r14
0x18003e0a0  pop     r13
0x18003e0a2  pop     r12
0x18003e0a4  pop     rdi
0x18003e0a5  pop     rsi
0x18003e0a6  pop     rbp
0x18003e0a7  retn
```
