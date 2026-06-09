# HidpGetFilterDriverTypes

- ea: `0x18000a430`
- end: `0x18000a805`
- name: `HidpGetFilterDriverTypes`
- size: `981`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000a88c`

## callees

- `0x180009778`
- `0x18000a430`
- `0x180013860`
- `0x180027ba0`
- `0x180027c80`
- `0x180028000`

## import_xrefs

- `ntoskrnl!MmGetSystemRoutineAddress` at `0x18000a75a`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x18000a75a`
- `ntoskrnl!IoGetDeviceProperty` at `0x18000a5f0`
- `ntoskrnl!IoGetDeviceProperty` at `0x18000a5f0`
- `ntoskrnl!IoGetDevicePropertyData` at `0x18000a54c`
- `ntoskrnl!IoGetDevicePropertyData` at `0x18000a5ad`
- `ntoskrnl!IoGetDevicePropertyData` at `0x18000a54c`
- `ntoskrnl!IoGetDevicePropertyData` at `0x18000a5ad`
- `ntoskrnl!RtlQueryRegistryValues` at `0x18000a782`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000a7b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000a7ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000a7b7`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000a7ce`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000a74a`
- `ntoskrnl!RtlInitUnicodeString` at `0x18000a74a`

## string_xrefs

- `0x18000a466`: `\Registry\Machine\System\CurrentControlSet\Control\Class\%ws`
- `0x18000a70c`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
__int64 __fastcall HidpGetFilterDriverTypes(__int64 a1, _DWORD *a2)
{
  struct _DEVICE_OBJECT *v4; // rcx
  __int64 v5; // r14
  NTSTATUS DevicePropertyData; // eax
  unsigned int DeviceProperty; // edi
  NTSTATUS v8; // eax
  int v9; // edx
  __int64 v10; // r8
  __int64 v11; // rax
  PVOID SystemRoutineAddress; // rax
  ULONG Type; // [rsp+60h] [rbp-A0h] BYREF
  ULONG RequiredSize; // [rsp+64h] [rbp-9Ch] BYREF
  int v16; // [rsp+68h] [rbp-98h] BYREF
  ULONG ResultLength; // [rsp+6Ch] [rbp-94h] BYREF
  PVOID P[2]; // [rsp+70h] [rbp-90h] BYREF
  PVOID v19[2]; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v21[28]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t pszFormat[64]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE PropertyBuffer[76]; // [rsp+200h] [rbp+100h] BYREF
  __int16 v24; // [rsp+24Ch] [rbp+14Ch]
  wchar_t pszDest[120]; // [rsp+250h] [rbp+150h] BYREF

  wcscpy(pszFormat, L"\\Registry\\Machine\\System\\CurrentControlSet\\Controlass\\%ws");
  RequiredSize = 0;
  ResultLength = 0;
  memset(v21, 0, sizeof(v21));
  v4 = *(struct _DEVICE_OBJECT **)(a1 + 48);
  v5 = *(_QWORD *)(a1 + 64);
  v16 = 0;
  *(_OWORD *)P = 0;
  Type = 8210;
  *(_OWORD *)v19 = 0;
  DevicePropertyData = IoGetDevicePropertyData(v4, &DEVPKEY_Device_UpperFilters, 0, 0, 0, 0, &RequiredSize, &Type);
  DeviceProperty = DevicePropertyData;
  if ( DevicePropertyData == -1073741789 )
  {
    *a2 |= 2u;
  }
  else if ( DevicePropertyData != -1073741772 )
  {
    return DeviceProperty;
  }
  v8 = IoGetDevicePropertyData(
         *(PDEVICE_OBJECT *)(a1 + 48),
         &DEVPKEY_Device_LowerFilters,
         0,
         0,
         0,
         0,
         &RequiredSize,
         &Type);
  DeviceProperty = v8;
  if ( v8 == -1073741789 )
  {
    *a2 |= 4u;
  }
  else if ( v8 != -1073741772 )
  {
    return DeviceProperty;
  }
  DeviceProperty = IoGetDeviceProperty(
                     *(PDEVICE_OBJECT *)(a1 + 48),
                     DevicePropertyClassGuid,
                     0x4Eu,
                     PropertyBuffer,
                     &ResultLength);
  if ( (DeviceProperty & 0x80000000) == 0 )
  {
    v24 = 0;
    RtlStringCbPrintfW(pszDest, 0xF0u, pszFormat, PropertyBuffer);
    memset(v21, 0, sizeof(v21));
    LODWORD(v21[6]) = 4;
    LODWORD(v21[1]) = 304;
    LODWORD(v21[4]) = 117440519;
    v21[2] = L"UpperFilters";
    LODWORD(v21[8]) = 304;
    v21[3] = P;
    LODWORD(v21[11]) = 117440519;
    v21[5] = &v16;
    LODWORD(v21[13]) = 4;
    v21[9] = L"LowerFilters";
    v21[10] = v19;
    v21[12] = &v16;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
    SystemRoutineAddress = MmGetSystemRoutineAddress(&DestinationString);
    if ( !SystemRoutineAddress )
      SystemRoutineAddress = RtlQueryRegistryValues;
    if ( ((int (__fastcall *)(__int64, wchar_t *, _QWORD *, _QWORD, _QWORD))SystemRoutineAddress)(
           0x80000000LL,
           pszDest,
           v21,
           0,
           0) >= 0 )
    {
      if ( LOWORD(P[0]) > 2u )
        *a2 |= 8u;
      if ( LOWORD(v19[0]) > 2u )
        *a2 |= 0x10u;
    }
    if ( P[1] )
      ExFreePoolWithTag(P[1], 0);
    if ( v19[1] )
      ExFreePoolWithTag(v19[1], 0);
    return 0;
  }
  else
  {
    LOBYTE(v9) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    if ( (_BYTE)v9 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v10 = *(_QWORD *)(a1 + 64);
      v11 = *(_QWORD *)(v10 + 32);
      LOBYTE(v10) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_qdqL(
        WPP_GLOBAL_Control->AttachedDevice,
        v9,
        v10,
        *(_QWORD *)(v5 + 704),
        2,
        2,
        14,
        (__int64)WPP_b44b9c582a6d3a011072db7b2d15a10e_Traceguids,
        v11,
        *(_DWORD *)(a1 + 8),
        *(_QWORD *)(a1 + 48),
        DeviceProperty);
    }
  }
  return DeviceProperty;
}

```

## disassembly

```asm
0x18000a430  mov     [rsp-8+arg_10], rbx
0x18000a435  push    rbp
0x18000a436  push    rsi
0x18000a437  push    rdi
0x18000a438  push    r12
0x18000a43a  push    r14
0x18000a43c  lea     rbp, [rsp-250h]
0x18000a444  sub     rsp, 350h
0x18000a44b  mov     rax, cs:__security_cookie
0x18000a452  xor     rax, rsp
0x18000a455  mov     [rbp+270h+var_30], rax
0x18000a45c  movaps  xmm1, xmmword ptr cs:aRegistryMachin+10h; "y\\Machine\\System\\CurrentControlSet\\"...
0x18000a463  mov     rbx, rdx
0x18000a466  movaps  xmm0, xmmword ptr cs:aRegistryMachin; "\\Registry\\Machine\\System\\CurrentCon"...
0x18000a46d  mov     rsi, rcx
0x18000a470  movaps  [rbp+270h+var_1E0], xmm1
0x18000a477  lea     rcx, [rbp+270h+var_2D0]; void *
0x18000a47b  movaps  xmm1, xmmword ptr cs:aRegistryMachin+30h; "\\CurrentControlSet\\Control\\Class\\%w"...
0x18000a482  xor     edx, edx; Val
0x18000a484  movaps  xmmword ptr [rbp+270h+pszFormat], xmm0
0x18000a48b  mov     r8d, 0E0h; Size
0x18000a491  movaps  xmm0, xmmword ptr cs:aRegistryMachin+20h; "e\\System\\CurrentControlSet\\Control\\"...
0x18000a498  movaps  [rbp+270h+var_1C0], xmm1
0x18000a49f  movaps  xmm1, xmmword ptr cs:aRegistryMachin+50h; "et\\Control\\Class\\%ws"
0x18000a4a6  movaps  [rbp+270h+var_1D0], xmm0
0x18000a4ad  movaps  xmm0, xmmword ptr cs:aRegistryMachin+40h; "ControlSet\\Control\\Class\\%ws"
0x18000a4b4  movaps  [rbp+270h+var_1A0], xmm1
0x18000a4bb  movups  xmm1, xmmword ptr cs:aRegistryMachin+6Ah; "ass\\%ws"
0x18000a4c2  mov     [rsp+370h+var_30C], 0
0x18000a4ca  movaps  [rbp+270h+var_1B0], xmm0
0x18000a4d1  movaps  xmm0, xmmword ptr cs:aRegistryMachin+60h; "ol\\Class\\%ws"
0x18000a4d8  movaps  [rbp+270h+var_190], xmm0
0x18000a4df  movups  [rbp+270h+var_190+0Ah], xmm1
0x18000a4e6  mov     [rsp+370h+ResultLength], 0
0x18000a4ee  call    memset
0x18000a4f3  mov     rcx, [rsi+30h]; Pdo
0x18000a4f7  lea     rax, [rsp+370h+var_310]
0x18000a4fc  mov     r14, [rsi+40h]
0x18000a500  lea     rdx, DEVPKEY_Device_UpperFilters; PropertyKey
0x18000a507  mov     [rsp+370h+Type], rax; Type
0x18000a50c  xorps   xmm0, xmm0
0x18000a50f  lea     rax, [rsp+370h+var_30C]
0x18000a514  mov     [rsp+370h+var_308], 0
0x18000a51c  mov     [rsp+370h+RequiredSize], rax; RequiredSize
0x18000a521  xorps   xmm1, xmm1
0x18000a524  mov     [rsp+370h+Data], 0; Data
0x18000a52d  xor     r9d, r9d; Flags
0x18000a530  xor     r8d, r8d; Lcid
0x18000a533  mov     [rsp+370h+Size], 0; Size
0x18000a53b  movups  xmmword ptr [rsp+370h+P], xmm0
0x18000a540  mov     [rsp+370h+var_310], 2012h
0x18000a548  movups  xmmword ptr [rbp+270h+var_2F0], xmm1
0x18000a54c  call    cs:__imp_IoGetDevicePropertyData
0x18000a553  nop     dword ptr [rax+rax+00h]
0x18000a558  mov     edi, eax
0x18000a55a  mov     r12d, 2
0x18000a560  cmp     eax, 0C0000023h
0x18000a565  jnz     short loc_18000A56C
0x18000a567  or      [rbx], r12d
0x18000a56a  jmp     short loc_18000A577
0x18000a56c  cmp     eax, 0C0000034h
0x18000a571  jnz     loc_18000A7DC
0x18000a577  mov     rcx, [rsi+30h]; Pdo
0x18000a57b  lea     rax, [rsp+370h+var_310]
0x18000a580  mov     [rsp+370h+Type], rax; Type
0x18000a585  lea     rdx, DEVPKEY_Device_LowerFilters; PropertyKey
0x18000a58c  lea     rax, [rsp+370h+var_30C]
0x18000a591  xor     r9d, r9d; Flags
0x18000a594  mov     [rsp+370h+RequiredSize], rax; RequiredSize
0x18000a599  xor     r8d, r8d; Lcid
0x18000a59c  mov     [rsp+370h+Data], 0; Data
0x18000a5a5  mov     [rsp+370h+Size], 0; Size
0x18000a5ad  call    cs:__imp_IoGetDevicePropertyData
0x18000a5b4  nop     dword ptr [rax+rax+00h]
0x18000a5b9  mov     edi, eax
0x18000a5bb  cmp     eax, 0C0000023h
0x18000a5c0  jnz     short loc_18000A5C7
0x18000a5c2  or      dword ptr [rbx], 4
0x18000a5c5  jmp     short loc_18000A5D2
0x18000a5c7  cmp     eax, 0C0000034h
0x18000a5cc  jnz     loc_18000A7DC
0x18000a5d2  mov     rcx, [rsi+30h]; DeviceObject
0x18000a5d6  lea     rax, [rsp+370h+ResultLength]
0x18000a5db  mov     edx, 6; DeviceProperty
0x18000a5e0  mov     qword ptr [rsp+370h+Size], rax; ResultLength
0x18000a5e5  lea     r9, [rbp+270h+PropertyBuffer]; PropertyBuffer
0x18000a5ec  lea     r8d, [rdx+48h]; BufferLength
0x18000a5f0  call    cs:__imp_IoGetDeviceProperty
0x18000a5f7  nop     dword ptr [rax+rax+00h]
0x18000a5fc  mov     edi, eax
0x18000a5fe  test    eax, eax
0x18000a600  jns     loc_18000A6A2
0x18000a606  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a60d  lea     rax, WPP_GLOBAL_Control
0x18000a614  cmp     rcx, rax
0x18000a617  jz      short loc_18000A62B
0x18000a619  mov     eax, [rcx+2Ch]
0x18000a61c  test    r12b, al
0x18000a61f  jz      short loc_18000A62B
0x18000a621  cmp     [rcx+29h], r12b
0x18000a625  jb      short loc_18000A62B
0x18000a627  mov     dl, 1
0x18000a629  jmp     short loc_18000A62D
0x18000a62b  xor     dl, dl
0x18000a62d  lea     rax, WPP_RECORDER_INITIALIZED
0x18000a634  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18000a63b  setnz   r10b
0x18000a63f  test    dl, dl
0x18000a641  jnz     short loc_18000A64C
0x18000a643  test    r10b, r10b
0x18000a646  jz      loc_18000A7DC
0x18000a64c  mov     rax, [rsi+30h]
0x18000a650  mov     r8, [rsi+40h]
0x18000a654  mov     r9, [r14+2C0h]
0x18000a65b  mov     rcx, [rcx+18h]
0x18000a65f  mov     [rsp+370h+var_318], edi
0x18000a663  mov     [rsp+370h+var_320], rax
0x18000a668  mov     eax, [rsi+8]
0x18000a66b  mov     [rsp+370h+var_328], eax
0x18000a66f  mov     rax, [r8+20h]
0x18000a673  mov     r8b, r10b
0x18000a676  mov     [rsp+370h+var_330], rax
0x18000a67b  lea     rax, WPP_b44b9c582a6d3a011072db7b2d15a10e_Traceguids
0x18000a682  mov     [rsp+370h+Type], rax
0x18000a687  mov     word ptr [rsp+370h+RequiredSize], 0Eh
0x18000a68e  mov     dword ptr [rsp+370h+Data], r12d
0x18000a693  mov     byte ptr [rsp+370h+Size], r12b
0x18000a698  call    WPP_RECORDER_AND_TRACE_SF_qdqL
0x18000a69d  jmp     loc_18000A7DC
0x18000a6a2  xor     eax, eax
0x18000a6a4  lea     r9, [rbp+270h+PropertyBuffer]
0x18000a6ab  lea     r8, [rbp+270h+pszFormat]; pszFormat
0x18000a6b2  mov     [rbp+270h+var_124], ax
0x18000a6b9  mov     edx, 0F0h; cbDest
0x18000a6be  lea     rcx, [rbp+270h+pszDest]; pszDest
0x18000a6c5  call    RtlStringCbPrintfW
0x18000a6ca  xor     edx, edx; Val
0x18000a6cc  lea     rcx, [rbp+270h+var_2D0]; void *
0x18000a6d0  mov     r8d, 0E0h; Size
0x18000a6d6  call    memset
0x18000a6db  mov     edx, 130h
0x18000a6e0  mov     [rbp+270h+var_2A0], 4
0x18000a6e7  mov     ecx, 7000007h
0x18000a6ec  mov     [rbp+270h+var_2C8], edx
0x18000a6ef  lea     rax, aUpperfilters; "UpperFilters"
0x18000a6f6  mov     [rbp+270h+var_2B0], ecx
0x18000a6f9  mov     [rbp+270h+var_2C0], rax
0x18000a6fd  xorps   xmm0, xmm0
0x18000a700  lea     rax, [rsp+370h+P]
0x18000a705  mov     [rbp+270h+var_290], edx
0x18000a708  mov     [rbp+270h+var_2B8], rax
0x18000a70c  lea     rdx, SourceString; "RtlQueryRegistryValuesEx"
0x18000a713  lea     rax, [rsp+370h+var_308]
0x18000a718  mov     [rbp+270h+var_278], ecx
0x18000a71b  mov     [rbp+270h+var_2A8], rax
0x18000a71f  lea     rcx, [rbp+270h+DestinationString]; DestinationString
0x18000a723  lea     rax, aLowerfilters; "LowerFilters"
0x18000a72a  mov     [rbp+270h+var_268], 4
0x18000a731  mov     [rbp+270h+var_288], rax
0x18000a735  lea     rax, [rbp+270h+var_2F0]
0x18000a739  mov     [rbp+270h+var_280], rax
0x18000a73d  lea     rax, [rsp+370h+var_308]
0x18000a742  mov     [rbp+270h+var_270], rax
0x18000a746  movups  xmmword ptr [rbp+270h+DestinationString.Length], xmm0
0x18000a74a  call    cs:__imp_RtlInitUnicodeString
0x18000a751  nop     dword ptr [rax+rax+00h]
0x18000a756  lea     rcx, [rbp+270h+DestinationString]; SystemRoutineName
0x18000a75a  call    cs:__imp_MmGetSystemRoutineAddress
0x18000a761  nop     dword ptr [rax+rax+00h]
0x18000a766  lea     r8, [rbp+270h+var_2D0]
0x18000a76a  mov     qword ptr [rsp+370h+Size], 0
0x18000a773  test    rax, rax
0x18000a776  lea     rdx, [rbp+270h+pszDest]
0x18000a77d  mov     ecx, 80000000h
0x18000a782  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x18000a78a  xor     r9d, r9d
0x18000a78d  call    _guard_dispatch_icall
0x18000a792  test    eax, eax
0x18000a794  js      short loc_18000A7AB
0x18000a796  cmp     word ptr [rsp+370h+P], r12w
0x18000a79c  jbe     short loc_18000A7A1
0x18000a79e  or      dword ptr [rbx], 8
0x18000a7a1  cmp     word ptr [rbp+270h+var_2F0], r12w
0x18000a7a6  jbe     short loc_18000A7AB
0x18000a7a8  or      dword ptr [rbx], 10h
0x18000a7ab  mov     rcx, [rsp+370h+P+8]; P
0x18000a7b0  test    rcx, rcx
0x18000a7b3  jz      short loc_18000A7C3
0x18000a7b5  xor     edx, edx; Tag
0x18000a7b7  call    cs:__imp_ExFreePoolWithTag
0x18000a7be  nop     dword ptr [rax+rax+00h]
0x18000a7c3  mov     rcx, [rbp+270h+var_2F0+8]; P
0x18000a7c7  test    rcx, rcx
0x18000a7ca  jz      short loc_18000A7DA
0x18000a7cc  xor     edx, edx; Tag
0x18000a7ce  call    cs:__imp_ExFreePoolWithTag
0x18000a7d5  nop     dword ptr [rax+rax+00h]
0x18000a7da  xor     edi, edi
0x18000a7dc  mov     eax, edi
0x18000a7de  mov     rcx, [rbp+270h+var_30]
0x18000a7e5  xor     rcx, rsp; StackCookie
0x18000a7e8  call    __security_check_cookie
0x18000a7ed  mov     rbx, [rsp+370h+arg_10]
0x18000a7f5  add     rsp, 350h
0x18000a7fc  pop     r14
0x18000a7fe  pop     r12
0x18000a800  pop     rdi
0x18000a801  pop     rsi
0x18000a802  pop     rbp
0x18000a803  retn
```
