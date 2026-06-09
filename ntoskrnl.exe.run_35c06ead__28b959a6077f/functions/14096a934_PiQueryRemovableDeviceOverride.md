# PiQueryRemovableDeviceOverride

- ea: `0x14096a934`
- end: `0x14096ac01`
- name: `PiQueryRemovableDeviceOverride`
- size: `717`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x140969358`

## callees

- `0x1406d9d70`
- `0x1406daa70`
- `0x1406dab70`
- `0x140764ae8`
- `0x1408b9700`
- `0x1408d9114`
- `0x14096a934`
- `0x14096ac08`
- `0x14096b1e4`
- `0x14096c1c0`
- `0x140bae410`
- `0x140bae8e0`

## string_xrefs

- `0x14096a9b4`: `ChildLocationPaths`
- `0x14096ab5d`: `ChildLocationPaths`
- `0x14096aa31`: `LocationPaths`

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
      Pool2 = ExAllocatePool2(256, v17, 1852403792);
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
      v15 = (void *)ExAllocatePool2(256, v24, 1852403792);
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
0x14096a934  push    rbp
0x14096a936  push    rbx
0x14096a937  push    rsi
0x14096a938  push    rdi
0x14096a939  push    r12
0x14096a93b  push    r14
0x14096a93d  push    r15
0x14096a93f  lea     rbp, [rsp-27h]
0x14096a944  sub     rsp, 0D0h
0x14096a94b  mov     rax, cs:__security_cookie
0x14096a952  xor     rax, rsp
0x14096a955  mov     [rbp+57h+var_40], rax
0x14096a959  cmp     cs:PnpDeviceOverrideHashList, 0
0x14096a961  xorps   xmm0, xmm0
0x14096a964  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x14096a968  mov     r12, r9
0x14096a96b  mov     [rbp+57h+var_70], 0
0x14096a973  mov     rdi, r8
0x14096a976  mov     [rbp+57h+var_74], 0
0x14096a97d  mov     rbx, rdx
0x14096a980  mov     [rbp+57h+KeyHandle], 0
0x14096a988  mov     r14, rcx
0x14096a98b  mov     [rbp+57h+P], 0
0x14096a993  mov     [rbp+57h+var_78], 0
0x14096a99a  mov     [rbp+57h+var_C0], 0
0x14096a9a1  mov     [rbp+57h+var_A0], 0
0x14096a9a8  jz      loc_14096AB00
0x14096a9ae  mov     cl, [rcx+2A8h]
0x14096a9b4  lea     rax, aChildlocationp; "ChildLocationPaths"
0x14096a9bb  mov     esi, 4
0x14096a9c0  movups  [rbp+57h+var_98], xmm0
0x14096a9c4  movups  xmmword ptr [rbp+57h+Handle], xmm0
0x14096a9c8  test    cl, 1
0x14096a9cb  jnz     short loc_14096AA18
0x14096a9cd  mov     dword ptr [rbp+57h+var_98], 260024h
0x14096a9d4  mov     qword ptr [rbp+57h+var_98+8], rax
0x14096a9d8  test    rdx, rdx
0x14096a9db  jz      short loc_14096A9F8
0x14096a9dd  lea     r8, [rbp+57h+var_98]
0x14096a9e1  mov     rcx, rdx; Src
0x14096a9e4  call    PipFindDeviceOverrideEntry
0x14096a9e9  test    eax, eax
0x14096a9eb  jns     loc_14096AB30
0x14096a9f1  mov     cl, [r14+2A8h]
0x14096a9f8  test    rdi, rdi
0x14096a9fb  jz      short loc_14096AA18
0x14096a9fd  lea     r8, [rbp+57h+var_98]
0x14096aa01  mov     rcx, rdi; Src
0x14096aa04  call    PipFindDeviceOverrideEntry
0x14096aa09  test    eax, eax
0x14096aa0b  jns     loc_14096AB30
0x14096aa11  mov     cl, [r14+2A8h]
0x14096aa18  mov     al, cl
0x14096aa1a  mov     r15d, 2
0x14096aa20  and     al, 3
0x14096aa22  cmp     al, 1
0x14096aa24  jz      loc_14096AAF9
0x14096aa2a  mov     dword ptr [rbp+57h+var_98], 1C001Ah
0x14096aa31  lea     rax, aLocationpaths; "LocationPaths"
0x14096aa38  mov     qword ptr [rbp+57h+var_98+8], rax
0x14096aa3c  test    rbx, rbx
0x14096aa3f  jz      loc_14096ABE9
0x14096aa45  lea     r8, [rbp+57h+var_98]
0x14096aa49  mov     rcx, rbx; Src
0x14096aa4c  call    PipFindDeviceOverrideEntry
0x14096aa51  mov     cl, [r14+2A8h]
0x14096aa58  mov     ebx, eax
0x14096aa5a  test    eax, eax
0x14096aa5c  jns     loc_14096AB45
0x14096aa62  test    rdi, rdi
0x14096aa65  jz      short loc_14096AA84
0x14096aa67  lea     r8, [rbp+57h+var_98]
0x14096aa6b  mov     rcx, rdi; Src
0x14096aa6e  call    PipFindDeviceOverrideEntry
0x14096aa73  mov     cl, [r14+2A8h]
0x14096aa7a  mov     ebx, eax
0x14096aa7c  test    eax, eax
0x14096aa7e  jns     loc_14096AB45
0x14096aa84  or      cl, 1
0x14096aa87  mov     [r14+2A8h], cl
0x14096aa8e  test    ebx, ebx
0x14096aa90  js      loc_14096AB4D
0x14096aa96  cmp     dword ptr [rbp+57h+Handle+8], 1
0x14096aa9a  lea     rdi, asc_140B2FCD0; "*"
0x14096aaa1  mov     [rbp+57h+KeyHandle], 0
0x14096aaa9  jz      loc_14096ABA7
0x14096aaaf  lea     r8, [rbp+57h+var_78]
0x14096aab3  mov     rcx, r14
0x14096aab6  lea     rdx, [rbp+57h+P]
0x14096aaba  call    PnpGetDeviceLocationStrings
0x14096aabf  mov     ebx, eax
0x14096aac1  test    eax, eax
0x14096aac3  js      loc_140B5F489
0x14096aac9  mov     rdx, [rbp+57h+Handle]
0x14096aacd  lea     rax, [rbp+57h+KeyHandle]
0x14096aad1  mov     rcx, [rbp+57h+P]; SourceString
0x14096aad5  mov     qword ptr [rsp+100h+Length], rax; __int64
0x14096aada  call    PnpOpenFirstMatchingSubKey
0x14096aadf  mov     rcx, [rbp+57h+P]; P
0x14096aae3  xor     edx, edx; Tag
0x14096aae5  mov     ebx, eax
0x14096aae7  call    ExFreePoolWithTag
0x14096aaec  test    ebx, ebx
0x14096aaee  jns     loc_14096ABD3
0x14096aaf4  jmp     loc_140B5F489
0x14096aaf9  mov     ebx, 0C0000034h
0x14096aafe  jmp     short loc_14096AA84
0x14096ab00  mov     ebx, 0C0000034h
0x14096ab05  jmp     short loc_14096AB0F
0x14096ab07  test    ebx, ebx
0x14096ab09  jns     loc_14096ABF3
0x14096ab0f  mov     eax, ebx
0x14096ab11  mov     rcx, [rbp+57h+var_40]
0x14096ab15  xor     rcx, rsp; StackCookie
0x14096ab18  call    __security_check_cookie
0x14096ab1d  add     rsp, 0D0h
0x14096ab24  pop     r15
0x14096ab26  pop     r14
0x14096ab28  pop     r12
0x14096ab2a  pop     rdi
0x14096ab2b  pop     rsi
0x14096ab2c  pop     rbx
0x14096ab2d  pop     rbp
0x14096ab2e  retn
0x14096ab30  mov     rcx, [rbp+57h+Handle]; Handle
0x14096ab34  call    ZwClose
0x14096ab39  or      [r14+2A8h], sil
0x14096ab40  jmp     loc_14096AA11
0x14096ab45  or      cl, r15b
0x14096ab48  jmp     loc_14096AA84
0x14096ab4d  mov     rcx, [r14+10h]
0x14096ab51  mov     al, [rcx+2A8h]
0x14096ab57  and     al, 5
0x14096ab59  cmp     al, 1
0x14096ab5b  jz      short loc_14096AB0F
0x14096ab5d  lea     rax, aChildlocationp; "ChildLocationPaths"
0x14096ab64  mov     dword ptr [rbp+57h+var_98], 260024h
0x14096ab6b  mov     qword ptr [rbp+57h+var_98+8], rax
0x14096ab6f  lea     rdx, [rbp+57h+var_70]
0x14096ab73  mov     rcx, [rcx+20h]
0x14096ab77  mov     r8d, 20019h
0x14096ab7d  call    PnpDeviceObjectToDeviceInstance
0x14096ab82  mov     ebx, eax
0x14096ab84  test    eax, eax
0x14096ab86  js      short loc_14096AB0F
0x14096ab88  mov     edi, 100h
0x14096ab8d  mov     [rbp+57h+var_60], r15d
0x14096ab91  xor     esi, esi
0x14096ab93  mov     [rbp+57h+var_C0], edi
0x14096ab96  xor     r15d, r15d
0x14096ab99  mov     [rbp+57h+var_5C], 3
0x14096aba0  mov     eax, edi
0x14096aba2  jmp     loc_140B5F364
0x14096aba7  mov     rdx, [rbp+57h+Handle]
0x14096abab  lea     r8, [rbp+57h+ValueName]
0x14096abaf  mov     r9d, 20019h
0x14096abb5  mov     dword ptr [rbp+57h+ValueName.Length], 40002h
0x14096abbc  lea     rcx, [rbp+57h+KeyHandle]
0x14096abc0  mov     [rbp+57h+ValueName.Buffer], rdi
0x14096abc4  call    IopOpenRegistryKeyEx
0x14096abc9  mov     ebx, eax
0x14096abcb  test    eax, eax
0x14096abcd  js      loc_14096AAAF
0x14096abd3  mov     rcx, [rbp+57h+Handle]; Handle
0x14096abd7  call    ZwClose
0x14096abdc  test    ebx, ebx
0x14096abde  js      loc_14096AB0F
0x14096abe4  jmp     loc_140B5F4BC
0x14096abe9  mov     ebx, 0C0000034h
0x14096abee  jmp     loc_14096AA62
0x14096abf3  mov     esi, 4
0x14096abf8  lea     r15d, [rsi-2]
0x14096abfc  jmp     loc_14096AA96
0x140b5f364  test    rsi, rsi
0x140b5f367  jnz     short loc_140B5F386
0x140b5f369  mov     edx, eax
0x140b5f36b  mov     ecx, 100h
0x140b5f370  mov     r8d, 6E697050h
0x140b5f376  call    ExAllocatePool2
0x140b5f37b  mov     edi, [rbp+57h+var_C0]
0x140b5f37e  mov     rsi, rax
0x140b5f381  test    rax, rax
0x140b5f384  jz      short loc_140B5F3FD
0x140b5f386  mov     rdx, [r14+10h]
0x140b5f38a  lea     rax, [rbp+57h+var_C0]
0x140b5f38e  mov     r9d, [rbp+r15*4+57h+var_60]
0x140b5f393  mov     r8, [rbp+57h+var_70]
0x140b5f397  mov     rcx, cs:PiPnpRtlCtx
0x140b5f39e  mov     rdx, [rdx+30h]
0x140b5f3a2  mov     [rsp+100h+var_C8], 0
0x140b5f3aa  mov     [rsp+100h+var_D0], rax
0x140b5f3af  lea     rax, [rbp+57h+var_A0]
0x140b5f3b3  mov     [rsp+100h+ResultLength], rsi
0x140b5f3b8  mov     qword ptr [rsp+100h+Length], rax
0x140b5f3bd  call    _CmGetDeviceRegProp
0x140b5f3c2  mov     ebx, eax
0x140b5f3c4  cmp     eax, 0C0000023h
0x140b5f3c9  jnz     short loc_140B5F409
0x140b5f3cb  xor     edx, edx; Tag
0x140b5f3cd  mov     rcx, rsi; P
0x140b5f3d0  call    ExFreePoolWithTag
0x140b5f3d5  mov     edx, [rbp+57h+var_C0]
0x140b5f3d8  mov     ecx, 100h
0x140b5f3dd  mov     r8d, 6E697050h
0x140b5f3e3  call    ExAllocatePool2
0x140b5f3e8  mov     rsi, rax
0x140b5f3eb  test    rax, rax
0x140b5f3ee  jz      short loc_140B5F3FA
0x140b5f3f0  mov     eax, [rbp+57h+var_C0]
0x140b5f3f3  mov     edi, eax
0x140b5f3f5  mov     [rbp+57h+var_C0], eax
0x140b5f3f8  jmp     short loc_140B5F42A
0x140b5f3fa  mov     edi, [rbp+57h+var_C0]
0x140b5f3fd  mov     ebx, 0C000009Ah
0x140b5f402  mov     [rbp+57h+var_C0], edi
0x140b5f405  mov     eax, edi
0x140b5f407  jmp     short loc_140B5F42A
0x140b5f409  test    eax, eax
0x140b5f40b  js      short loc_140B5F421
0x140b5f40d  cmp     [rbp+57h+var_A0], 7
0x140b5f411  jnz     short loc_140B5F47D
0x140b5f413  lea     r8, [rbp+57h+var_98]
0x140b5f417  mov     rcx, rsi; Src
0x140b5f41a  call    PipFindDeviceOverrideEntry
0x140b5f41f  mov     ebx, eax
0x140b5f421  mov     eax, edi
0x140b5f423  mov     [rbp+57h+var_C0], eax
0x140b5f426  test    ebx, ebx
0x140b5f428  jns     short loc_140B5F437
0x140b5f42a  inc     r15d
0x140b5f42d  cmp     r15d, 2
0x140b5f431  jb      loc_140B5F364
0x140b5f437  test    rsi, rsi
0x140b5f43a  jz      short loc_140B5F446
0x140b5f43c  xor     edx, edx; Tag
0x140b5f43e  mov     rcx, rsi; P
0x140b5f441  call    ExFreePoolWithTag
0x140b5f446  mov     rcx, [rbp+57h+var_70]; Handle
0x140b5f44a  call    ZwClose
0x140b5f44f  mov     rcx, [r14+10h]
0x140b5f453  mov     al, [rcx+2A8h]
0x140b5f459  test    al, 1
0x140b5f45b  jnz     loc_14096AB07
0x140b5f461  test    ebx, ebx
0x140b5f463  js      short loc_140B5F46D
0x140b5f465  or      al, 4
0x140b5f467  mov     [rcx+2A8h], al
0x140b5f46d  mov     rax, [r14+10h]
0x140b5f471  or      byte ptr [rax+2A8h], 1
0x140b5f478  jmp     loc_14096AB07
0x140b5f47d  mov     ebx, 0C0000001h
0x140b5f482  mov     [rbp+57h+var_C0], edi
0x140b5f485  mov     eax, edi
0x140b5f487  jmp     short loc_140B5F42A
0x140b5f489  cmp     dword ptr [rbp+57h+Handle+8], 1
0x140b5f48d  jbe     loc_14096ABD3
0x140b5f493  mov     rdx, [rbp+57h+Handle]
0x140b5f497  lea     r8, [rbp+57h+ValueName]
0x140b5f49b  mov     r9d, 20019h
0x140b5f4a1  mov     dword ptr [rbp+57h+ValueName.Length], 40002h
0x140b5f4a8  lea     rcx, [rbp+57h+KeyHandle]
0x140b5f4ac  mov     [rbp+57h+ValueName.Buffer], rdi
0x140b5f4b0  call    IopOpenRegistryKeyEx
0x140b5f4b5  mov     ebx, eax
0x140b5f4b7  jmp     loc_14096ABD3
0x140b5f4bc  lea     rax, aRemovable; "Removable"
0x140b5f4c3  mov     dword ptr [rbp+57h+ValueName.Length], 140012h
0x140b5f4ca  mov     [rbp+57h+ValueName.Buffer], rax
0x140b5f4ce  lea     r9, [rbp+57h+KeyValueInformation]; KeyValueInformation
0x140b5f4d2  lea     rax, [rbp+57h+var_74]
0x140b5f4d6  xor     edi, edi
0x140b5f4d8  mov     [rsp+100h+ResultLength], rax; ResultLength
0x140b5f4dd  lea     rdx, [rbp+57h+ValueName]; ValueName
0x140b5f4e1  mov     r8d, r15d; KeyValueInformationClass
0x140b5f4e4  lea     ecx, [rdi+14h]
0x140b5f4e7  mov     [rsp+100h+Length], ecx; Length
0x140b5f4eb  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140b5f4ef  call    ZwQueryValueKey
0x140b5f4f4  mov     ebx, eax
0x140b5f4f6  test    eax, eax
0x140b5f4f8  js      short loc_140B5F50E
0x140b5f4fa  cmp     [rbp+57h+var_54], esi
0x140b5f4fd  jnz     short loc_140B5F509
0x140b5f4ff  cmp     [rbp+57h+var_50], esi
0x140b5f502  jnz     short loc_140B5F509
0x140b5f504  mov     edi, [rbp+57h+var_4C]
0x140b5f507  jmp     short loc_140B5F50E
0x140b5f509  mov     ebx, 0C0000001h
0x140b5f50e  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x140b5f512  call    ZwClose
0x140b5f517  test    edi, edi
0x140b5f519  setnz   al
0x140b5f51c  mov     [r12], al
0x140b5f520  jmp     loc_14096AB0F
```
