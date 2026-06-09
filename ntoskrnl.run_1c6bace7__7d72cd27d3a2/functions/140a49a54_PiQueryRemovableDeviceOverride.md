# PiQueryRemovableDeviceOverride

- ea: `0x140a49a54`
- end: `0x140a49d21`
- name: `PiQueryRemovableDeviceOverride`
- size: `717`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x140a48478`

## callees

- `0x1406dc8c0`
- `0x1406dd5c0`
- `0x1406dd6c0`
- `0x140768f58`
- `0x1408ee610`
- `0x14090def4`
- `0x140a49a54`
- `0x140a49d28`
- `0x140a4a3d8`
- `0x140a4b070`
- `0x140bb1410`
- `0x140bb19f0`

## string_xrefs

- `0x140a49ad4`: `ChildLocationPaths`
- `0x140a49c7d`: `ChildLocationPaths`
- `0x140a49b51`: `LocationPaths`

## pseudocode

```c
__int64 __fastcall PiQueryRemovableDeviceOverride(__int64 a1, void *a2, void *a3, bool *a4)
{
  char v8; // cl
  int DeviceOverrideEntry; // eax
  int DeviceLocationStrings; // ebx
  int v11; // eax
  __int64 v13; // rcx
  int v14; // edi
  void *v15; // rsi
  __int64 v16; // r15
  unsigned int v17; // eax
  __int64 Pool2; // rax
  int DeviceRegProp; // eax
  __int64 v20; // rcx
  char v21; // al
  int v22; // edi
  NTSTATUS v23; // eax
  unsigned int v24; // [rsp+40h] [rbp-69h] BYREF
  HANDLE KeyHandle; // [rsp+48h] [rbp-61h] BYREF
  UNICODE_STRING ValueName; // [rsp+50h] [rbp-59h] BYREF
  int v27; // [rsp+60h] [rbp-49h] BYREF
  __int128 v28; // [rsp+68h] [rbp-41h]
  HANDLE Handle[2]; // [rsp+78h] [rbp-31h]
  int v30; // [rsp+88h] [rbp-21h] BYREF
  ULONG ResultLength; // [rsp+8Ch] [rbp-1Dh] BYREF
  HANDLE v32; // [rsp+90h] [rbp-19h] BYREF
  PVOID P; // [rsp+98h] [rbp-11h] BYREF
  _DWORD v34[2]; // [rsp+A0h] [rbp-9h]
  _BYTE KeyValueInformation[4]; // [rsp+A8h] [rbp-1h] BYREF
  int v36; // [rsp+ACh] [rbp+3h]
  int v37; // [rsp+B0h] [rbp+7h]
  int v38; // [rsp+B4h] [rbp+Bh]

  ValueName = 0;
  v32 = 0;
  ResultLength = 0;
  KeyHandle = 0;
  P = 0;
  v30 = 0;
  v24 = 0;
  v27 = 0;
  if ( !PnpDeviceOverrideHashList )
    return (unsigned int)-1073741772;
  v8 = *(_BYTE *)(a1 + 680);
  v28 = 0;
  *(_OWORD *)Handle = 0;
  if ( (v8 & 1) == 0 )
  {
    LODWORD(v28) = 2490404;
    *((_QWORD *)&v28 + 1) = L"ChildLocationPaths";
    if ( a2 )
    {
      if ( (int)PipFindDeviceOverrideEntry(a2) >= 0 )
      {
LABEL_23:
        ZwClose(Handle[0]);
        *(_BYTE *)(a1 + 680) |= 4u;
LABEL_8:
        v8 = *(_BYTE *)(a1 + 680);
        goto LABEL_9;
      }
      v8 = *(_BYTE *)(a1 + 680);
    }
    if ( !a3 )
      goto LABEL_9;
    if ( (int)PipFindDeviceOverrideEntry(a3) < 0 )
      goto LABEL_8;
    goto LABEL_23;
  }
LABEL_9:
  if ( (v8 & 3) != 1 )
  {
    LODWORD(v28) = 1835034;
    *((_QWORD *)&v28 + 1) = L"LocationPaths";
    if ( a2 )
    {
      DeviceOverrideEntry = PipFindDeviceOverrideEntry(a2);
      v8 = *(_BYTE *)(a1 + 680);
      DeviceLocationStrings = DeviceOverrideEntry;
      if ( DeviceOverrideEntry >= 0 )
      {
LABEL_24:
        v8 |= 2u;
        goto LABEL_14;
      }
    }
    else
    {
      DeviceLocationStrings = -1073741772;
    }
    if ( !a3 )
      goto LABEL_14;
    v11 = PipFindDeviceOverrideEntry(a3);
    v8 = *(_BYTE *)(a1 + 680);
    DeviceLocationStrings = v11;
    if ( v11 < 0 )
      goto LABEL_14;
    goto LABEL_24;
  }
  DeviceLocationStrings = -1073741772;
LABEL_14:
  *(_BYTE *)(a1 + 680) = v8 | 1;
  if ( DeviceLocationStrings >= 0 )
  {
LABEL_15:
    KeyHandle = 0;
    if ( LODWORD(Handle[1]) != 1
      || (*(_DWORD *)&ValueName.Length = 262146,
          ValueName.Buffer = (wchar_t *)L"*",
          DeviceLocationStrings = IopOpenRegistryKeyEx(&KeyHandle, Handle[0], &ValueName, 131097),
          DeviceLocationStrings < 0) )
    {
      DeviceLocationStrings = PnpGetDeviceLocationStrings(a1, &P, &v30);
      if ( DeviceLocationStrings < 0
        || (DeviceLocationStrings = PnpOpenFirstMatchingSubKey((PCWSTR)P, (__int64)&KeyHandle),
            ExFreePoolWithTag(P, 0),
            DeviceLocationStrings < 0) )
      {
        if ( LODWORD(Handle[1]) > 1 )
        {
          *(_DWORD *)&ValueName.Length = 262146;
          ValueName.Buffer = (wchar_t *)L"*";
          DeviceLocationStrings = IopOpenRegistryKeyEx(&KeyHandle, Handle[0], &ValueName, 131097);
        }
      }
    }
    ZwClose(Handle[0]);
    if ( DeviceLocationStrings >= 0 )
    {
      *(_DWORD *)&ValueName.Length = 1310738;
      ValueName.Buffer = L"Removable";
      v22 = 0;
      v23 = ZwQueryValueKey(
              KeyHandle,
              &ValueName,
              KeyValuePartialInformation,
              KeyValueInformation,
              0x14u,
              &ResultLength);
      DeviceLocationStrings = v23;
      if ( v23 >= 0 )
      {
        if ( v36 == 4 && v37 == 4 )
          v22 = v38;
        else
          DeviceLocationStrings = -1073741823;
      }
      ZwClose(KeyHandle);
      *a4 = v22 != 0;
    }
    return (unsigned int)DeviceLocationStrings;
  }
  v13 = *(_QWORD *)(a1 + 16);
  if ( (*(_BYTE *)(v13 + 680) & 5) == 1 )
    return (unsigned int)DeviceLocationStrings;
  LODWORD(v28) = 2490404;
  *((_QWORD *)&v28 + 1) = L"ChildLocationPaths";
  DeviceLocationStrings = PnpDeviceObjectToDeviceInstance(*(_QWORD *)(v13 + 32), &v32, 131097);
  if ( DeviceLocationStrings < 0 )
    return (unsigned int)DeviceLocationStrings;
  v14 = 256;
  v34[0] = 2;
  v15 = 0;
  v24 = 256;
  v16 = 0;
  v34[1] = 3;
  v17 = 256;
  do
  {
    if ( !v15 )
    {
      Pool2 = ExAllocatePool2(256, v17, 0x6E697050u);
      v14 = v24;
      v15 = (void *)Pool2;
      if ( !Pool2 )
        goto LABEL_39;
    }
    DeviceRegProp = CmGetDeviceRegProp(
                      PiPnpRtlCtx,
                      *(_QWORD *)(*(_QWORD *)(a1 + 16) + 48LL),
                      (_DWORD)v32,
                      v34[v16],
                      (__int64)&v27,
                      (__int64)v15,
                      (__int64)&v24,
                      0);
    DeviceLocationStrings = DeviceRegProp;
    if ( DeviceRegProp == -1073741789 )
    {
      ExFreePoolWithTag(v15, 0);
      v15 = (void *)ExAllocatePool2(256, v24, 0x6E697050u);
      if ( v15 )
      {
        v17 = v24;
        v14 = v24;
        goto LABEL_44;
      }
      v14 = v24;
LABEL_39:
      DeviceLocationStrings = -1073741670;
      v24 = v14;
      v17 = v14;
      goto LABEL_44;
    }
    if ( DeviceRegProp >= 0 )
    {
      if ( v27 != 7 )
      {
        DeviceLocationStrings = -1073741823;
        v24 = v14;
        v17 = v14;
        goto LABEL_44;
      }
      DeviceLocationStrings = PipFindDeviceOverrideEntry(v15);
    }
    v17 = v14;
    v24 = v14;
    if ( DeviceLocationStrings >= 0 )
      break;
LABEL_44:
    v16 = (unsigned int)(v16 + 1);
  }
  while ( (unsigned int)v16 < 2 );
  if ( v15 )
    ExFreePoolWithTag(v15, 0);
  ZwClose(v32);
  v20 = *(_QWORD *)(a1 + 16);
  v21 = *(_BYTE *)(v20 + 680);
  if ( (v21 & 1) == 0 )
  {
    if ( DeviceLocationStrings >= 0 )
      *(_BYTE *)(v20 + 680) = v21 | 4;
    *(_BYTE *)(*(_QWORD *)(a1 + 16) + 680LL) |= 1u;
  }
  if ( DeviceLocationStrings >= 0 )
    goto LABEL_15;
  return (unsigned int)DeviceLocationStrings;
}

```

## disassembly

```asm
0x140a49a54  push    rbp
0x140a49a56  push    rbx
0x140a49a57  push    rsi
0x140a49a58  push    rdi
0x140a49a59  push    r12
0x140a49a5b  push    r14
0x140a49a5d  push    r15
0x140a49a5f  lea     rbp, [rsp-27h]
0x140a49a64  sub     rsp, 0D0h
0x140a49a6b  mov     rax, cs:__security_cookie
0x140a49a72  xor     rax, rsp
0x140a49a75  mov     [rbp+57h+var_40], rax
0x140a49a79  cmp     cs:PnpDeviceOverrideHashList, 0
0x140a49a81  xorps   xmm0, xmm0
0x140a49a84  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x140a49a88  mov     r12, r9
0x140a49a8b  mov     [rbp+57h+var_70], 0
0x140a49a93  mov     rdi, r8
0x140a49a96  mov     [rbp+57h+var_74], 0
0x140a49a9d  mov     rbx, rdx
0x140a49aa0  mov     [rbp+57h+KeyHandle], 0
0x140a49aa8  mov     r14, rcx
0x140a49aab  mov     [rbp+57h+P], 0
0x140a49ab3  mov     [rbp+57h+var_78], 0
0x140a49aba  mov     [rbp+57h+var_C0], 0
0x140a49ac1  mov     [rbp+57h+var_A0], 0
0x140a49ac8  jz      loc_140A49C20
0x140a49ace  mov     cl, [rcx+2A8h]
0x140a49ad4  lea     rax, aChildlocationp; "ChildLocationPaths"
0x140a49adb  mov     esi, 4
0x140a49ae0  movups  [rbp+57h+var_98], xmm0
0x140a49ae4  movups  xmmword ptr [rbp+57h+Handle], xmm0
0x140a49ae8  test    cl, 1
0x140a49aeb  jnz     short loc_140A49B38
0x140a49aed  mov     dword ptr [rbp+57h+var_98], 260024h
0x140a49af4  mov     qword ptr [rbp+57h+var_98+8], rax
0x140a49af8  test    rdx, rdx
0x140a49afb  jz      short loc_140A49B18
0x140a49afd  lea     r8, [rbp+57h+var_98]
0x140a49b01  mov     rcx, rdx; Src
0x140a49b04  call    PipFindDeviceOverrideEntry
0x140a49b09  test    eax, eax
0x140a49b0b  jns     loc_140A49C50
0x140a49b11  mov     cl, [r14+2A8h]
0x140a49b18  test    rdi, rdi
0x140a49b1b  jz      short loc_140A49B38
0x140a49b1d  lea     r8, [rbp+57h+var_98]
0x140a49b21  mov     rcx, rdi; Src
0x140a49b24  call    PipFindDeviceOverrideEntry
0x140a49b29  test    eax, eax
0x140a49b2b  jns     loc_140A49C50
0x140a49b31  mov     cl, [r14+2A8h]
0x140a49b38  mov     al, cl
0x140a49b3a  mov     r15d, 2
0x140a49b40  and     al, 3
0x140a49b42  cmp     al, 1
0x140a49b44  jz      loc_140A49C19
0x140a49b4a  mov     dword ptr [rbp+57h+var_98], 1C001Ah
0x140a49b51  lea     rax, aLocationpaths; "LocationPaths"
0x140a49b58  mov     qword ptr [rbp+57h+var_98+8], rax
0x140a49b5c  test    rbx, rbx
0x140a49b5f  jz      loc_140A49D09
0x140a49b65  lea     r8, [rbp+57h+var_98]
0x140a49b69  mov     rcx, rbx; Src
0x140a49b6c  call    PipFindDeviceOverrideEntry
0x140a49b71  mov     cl, [r14+2A8h]
0x140a49b78  mov     ebx, eax
0x140a49b7a  test    eax, eax
0x140a49b7c  jns     loc_140A49C65
0x140a49b82  test    rdi, rdi
0x140a49b85  jz      short loc_140A49BA4
0x140a49b87  lea     r8, [rbp+57h+var_98]
0x140a49b8b  mov     rcx, rdi; Src
0x140a49b8e  call    PipFindDeviceOverrideEntry
0x140a49b93  mov     cl, [r14+2A8h]
0x140a49b9a  mov     ebx, eax
0x140a49b9c  test    eax, eax
0x140a49b9e  jns     loc_140A49C65
0x140a49ba4  or      cl, 1
0x140a49ba7  mov     [r14+2A8h], cl
0x140a49bae  test    ebx, ebx
0x140a49bb0  js      loc_140A49C6D
0x140a49bb6  cmp     dword ptr [rbp+57h+Handle+8], 1
0x140a49bba  lea     rdi, asc_140B311A0; "*"
0x140a49bc1  mov     [rbp+57h+KeyHandle], 0
0x140a49bc9  jz      loc_140A49CC7
0x140a49bcf  lea     r8, [rbp+57h+var_78]
0x140a49bd3  mov     rcx, r14
0x140a49bd6  lea     rdx, [rbp+57h+P]
0x140a49bda  call    PnpGetDeviceLocationStrings
0x140a49bdf  mov     ebx, eax
0x140a49be1  test    eax, eax
0x140a49be3  js      loc_140B6EB19
0x140a49be9  mov     rdx, [rbp+57h+Handle]
0x140a49bed  lea     rax, [rbp+57h+KeyHandle]
0x140a49bf1  mov     rcx, [rbp+57h+P]; SourceString
0x140a49bf5  mov     qword ptr [rsp+100h+Length], rax; __int64
0x140a49bfa  call    PnpOpenFirstMatchingSubKey
0x140a49bff  mov     rcx, [rbp+57h+P]; P
0x140a49c03  xor     edx, edx; Tag
0x140a49c05  mov     ebx, eax
0x140a49c07  call    ExFreePoolWithTag
0x140a49c0c  test    ebx, ebx
0x140a49c0e  jns     loc_140A49CF3
0x140a49c14  jmp     loc_140B6EB19
0x140a49c19  mov     ebx, 0C0000034h
0x140a49c1e  jmp     short loc_140A49BA4
0x140a49c20  mov     ebx, 0C0000034h
0x140a49c25  jmp     short loc_140A49C2F
0x140a49c27  test    ebx, ebx
0x140a49c29  jns     loc_140A49D13
0x140a49c2f  mov     eax, ebx
0x140a49c31  mov     rcx, [rbp+57h+var_40]
0x140a49c35  xor     rcx, rsp; StackCookie
0x140a49c38  call    __security_check_cookie
0x140a49c3d  add     rsp, 0D0h
0x140a49c44  pop     r15
0x140a49c46  pop     r14
0x140a49c48  pop     r12
0x140a49c4a  pop     rdi
0x140a49c4b  pop     rsi
0x140a49c4c  pop     rbx
0x140a49c4d  pop     rbp
0x140a49c4e  retn
0x140a49c50  mov     rcx, [rbp+57h+Handle]; Handle
0x140a49c54  call    ZwClose
0x140a49c59  or      [r14+2A8h], sil
0x140a49c60  jmp     loc_140A49B31
0x140a49c65  or      cl, r15b
0x140a49c68  jmp     loc_140A49BA4
0x140a49c6d  mov     rcx, [r14+10h]
0x140a49c71  mov     al, [rcx+2A8h]
0x140a49c77  and     al, 5
0x140a49c79  cmp     al, 1
0x140a49c7b  jz      short loc_140A49C2F
0x140a49c7d  lea     rax, aChildlocationp; "ChildLocationPaths"
0x140a49c84  mov     dword ptr [rbp+57h+var_98], 260024h
0x140a49c8b  mov     qword ptr [rbp+57h+var_98+8], rax
0x140a49c8f  lea     rdx, [rbp+57h+var_70]
0x140a49c93  mov     rcx, [rcx+20h]
0x140a49c97  mov     r8d, 20019h
0x140a49c9d  call    PnpDeviceObjectToDeviceInstance
0x140a49ca2  mov     ebx, eax
0x140a49ca4  test    eax, eax
0x140a49ca6  js      short loc_140A49C2F
0x140a49ca8  mov     edi, 100h
0x140a49cad  mov     [rbp+57h+var_60], r15d
0x140a49cb1  xor     esi, esi
0x140a49cb3  mov     [rbp+57h+var_C0], edi
0x140a49cb6  xor     r15d, r15d
0x140a49cb9  mov     [rbp+57h+var_5C], 3
0x140a49cc0  mov     eax, edi
0x140a49cc2  jmp     loc_140B6E9F4
0x140a49cc7  mov     rdx, [rbp+57h+Handle]
0x140a49ccb  lea     r8, [rbp+57h+ValueName]
0x140a49ccf  mov     r9d, 20019h
0x140a49cd5  mov     dword ptr [rbp+57h+ValueName.Length], 40002h
0x140a49cdc  lea     rcx, [rbp+57h+KeyHandle]
0x140a49ce0  mov     [rbp+57h+ValueName.Buffer], rdi
0x140a49ce4  call    IopOpenRegistryKeyEx
0x140a49ce9  mov     ebx, eax
0x140a49ceb  test    eax, eax
0x140a49ced  js      loc_140A49BCF
0x140a49cf3  mov     rcx, [rbp+57h+Handle]; Handle
0x140a49cf7  call    ZwClose
0x140a49cfc  test    ebx, ebx
0x140a49cfe  js      loc_140A49C2F
0x140a49d04  jmp     loc_140B6EB4C
0x140a49d09  mov     ebx, 0C0000034h
0x140a49d0e  jmp     loc_140A49B82
0x140a49d13  mov     esi, 4
0x140a49d18  lea     r15d, [rsi-2]
0x140a49d1c  jmp     loc_140A49BB6
0x140b6e9f4  test    rsi, rsi
0x140b6e9f7  jnz     short loc_140B6EA16
0x140b6e9f9  mov     edx, eax
0x140b6e9fb  mov     ecx, 100h
0x140b6ea00  mov     r8d, 6E697050h
0x140b6ea06  call    ExAllocatePool2
0x140b6ea0b  mov     edi, [rbp+57h+var_C0]
0x140b6ea0e  mov     rsi, rax
0x140b6ea11  test    rax, rax
0x140b6ea14  jz      short loc_140B6EA8D
0x140b6ea16  mov     rdx, [r14+10h]
0x140b6ea1a  lea     rax, [rbp+57h+var_C0]
0x140b6ea1e  mov     r9d, [rbp+r15*4+57h+var_60]
0x140b6ea23  mov     r8, [rbp+57h+var_70]
0x140b6ea27  mov     rcx, cs:PiPnpRtlCtx
0x140b6ea2e  mov     rdx, [rdx+30h]
0x140b6ea32  mov     [rsp+100h+var_C8], 0
0x140b6ea3a  mov     [rsp+100h+var_D0], rax
0x140b6ea3f  lea     rax, [rbp+57h+var_A0]
0x140b6ea43  mov     [rsp+100h+ResultLength], rsi
0x140b6ea48  mov     qword ptr [rsp+100h+Length], rax
0x140b6ea4d  call    _CmGetDeviceRegProp
0x140b6ea52  mov     ebx, eax
0x140b6ea54  cmp     eax, 0C0000023h
0x140b6ea59  jnz     short loc_140B6EA99
0x140b6ea5b  xor     edx, edx; Tag
0x140b6ea5d  mov     rcx, rsi; P
0x140b6ea60  call    ExFreePoolWithTag
0x140b6ea65  mov     edx, [rbp+57h+var_C0]
0x140b6ea68  mov     ecx, 100h
0x140b6ea6d  mov     r8d, 6E697050h
0x140b6ea73  call    ExAllocatePool2
0x140b6ea78  mov     rsi, rax
0x140b6ea7b  test    rax, rax
0x140b6ea7e  jz      short loc_140B6EA8A
0x140b6ea80  mov     eax, [rbp+57h+var_C0]
0x140b6ea83  mov     edi, eax
0x140b6ea85  mov     [rbp+57h+var_C0], eax
0x140b6ea88  jmp     short loc_140B6EABA
0x140b6ea8a  mov     edi, [rbp+57h+var_C0]
0x140b6ea8d  mov     ebx, 0C000009Ah
0x140b6ea92  mov     [rbp+57h+var_C0], edi
0x140b6ea95  mov     eax, edi
0x140b6ea97  jmp     short loc_140B6EABA
0x140b6ea99  test    eax, eax
0x140b6ea9b  js      short loc_140B6EAB1
0x140b6ea9d  cmp     [rbp+57h+var_A0], 7
0x140b6eaa1  jnz     short loc_140B6EB0D
0x140b6eaa3  lea     r8, [rbp+57h+var_98]
0x140b6eaa7  mov     rcx, rsi; Src
0x140b6eaaa  call    PipFindDeviceOverrideEntry
0x140b6eaaf  mov     ebx, eax
0x140b6eab1  mov     eax, edi
0x140b6eab3  mov     [rbp+57h+var_C0], eax
0x140b6eab6  test    ebx, ebx
0x140b6eab8  jns     short loc_140B6EAC7
0x140b6eaba  inc     r15d
0x140b6eabd  cmp     r15d, 2
0x140b6eac1  jb      loc_140B6E9F4
0x140b6eac7  test    rsi, rsi
0x140b6eaca  jz      short loc_140B6EAD6
0x140b6eacc  xor     edx, edx; Tag
0x140b6eace  mov     rcx, rsi; P
0x140b6ead1  call    ExFreePoolWithTag
0x140b6ead6  mov     rcx, [rbp+57h+var_70]; Handle
0x140b6eada  call    ZwClose
0x140b6eadf  mov     rcx, [r14+10h]
0x140b6eae3  mov     al, [rcx+2A8h]
0x140b6eae9  test    al, 1
0x140b6eaeb  jnz     loc_140A49C27
0x140b6eaf1  test    ebx, ebx
0x140b6eaf3  js      short loc_140B6EAFD
0x140b6eaf5  or      al, 4
0x140b6eaf7  mov     [rcx+2A8h], al
0x140b6eafd  mov     rax, [r14+10h]
0x140b6eb01  or      byte ptr [rax+2A8h], 1
0x140b6eb08  jmp     loc_140A49C27
0x140b6eb0d  mov     ebx, 0C0000001h
0x140b6eb12  mov     [rbp+57h+var_C0], edi
0x140b6eb15  mov     eax, edi
0x140b6eb17  jmp     short loc_140B6EABA
0x140b6eb19  cmp     dword ptr [rbp+57h+Handle+8], 1
0x140b6eb1d  jbe     loc_140A49CF3
0x140b6eb23  mov     rdx, [rbp+57h+Handle]
0x140b6eb27  lea     r8, [rbp+57h+ValueName]
0x140b6eb2b  mov     r9d, 20019h
0x140b6eb31  mov     dword ptr [rbp+57h+ValueName.Length], 40002h
0x140b6eb38  lea     rcx, [rbp+57h+KeyHandle]
0x140b6eb3c  mov     [rbp+57h+ValueName.Buffer], rdi
0x140b6eb40  call    IopOpenRegistryKeyEx
0x140b6eb45  mov     ebx, eax
0x140b6eb47  jmp     loc_140A49CF3
0x140b6eb4c  lea     rax, aRemovable; "Removable"
0x140b6eb53  mov     dword ptr [rbp+57h+ValueName.Length], 140012h
0x140b6eb5a  mov     [rbp+57h+ValueName.Buffer], rax
0x140b6eb5e  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x140b6eb62  lea     rax, [rbp+57h+var_74]
0x140b6eb66  xor     edi, edi
0x140b6eb68  mov     [rsp+100h+ResultLength], rax; ResultLength
0x140b6eb6d  lea     rdx, [rbp+57h+ValueName]; ValueName
0x140b6eb71  mov     r8d, r15d; KeyValueInformationClass
0x140b6eb74  lea     ecx, [rdi+14h]
0x140b6eb77  mov     [rsp+100h+Length], ecx; Length
0x140b6eb7b  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140b6eb7f  call    ZwQueryValueKey
0x140b6eb84  mov     ebx, eax
0x140b6eb86  test    eax, eax
0x140b6eb88  js      short loc_140B6EB9E
0x140b6eb8a  cmp     [rbp+57h+var_54], esi
0x140b6eb8d  jnz     short loc_140B6EB99
0x140b6eb8f  cmp     [rbp+57h+var_50], esi
0x140b6eb92  jnz     short loc_140B6EB99
0x140b6eb94  mov     edi, [rbp+57h+var_4C]
0x140b6eb97  jmp     short loc_140B6EB9E
0x140b6eb99  mov     ebx, 0C0000001h
0x140b6eb9e  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140b6eba2  call    ZwClose
0x140b6eba7  test    edi, edi
0x140b6eba9  setnz   al
0x140b6ebac  mov     [r12], al
0x140b6ebb0  jmp     loc_140A49C2F
```
