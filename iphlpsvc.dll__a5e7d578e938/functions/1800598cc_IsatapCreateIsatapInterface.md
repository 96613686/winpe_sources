# IsatapCreateIsatapInterface

- ea: `0x1800598cc`
- end: `0x180059c36`
- name: `IsatapCreateIsatapInterface`
- size: `874`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180041120`

## callees

- `0x180004c64`
- `0x180008210`
- `0x18000d7c0`
- `0x180012dcc`
- `0x1800159d4`
- `0x18001f404`
- `0x18001f6d8`
- `0x180024250`
- `0x18002c834`
- `0x18003fac0`
- `0x180046fec`
- `0x18004ad68`
- `0x18004b5f0`
- `0x18004c188`
- `0x180052684`
- `0x1800533d8`
- `0x18005918c`
- `0x1800598cc`
- `0x18005b1b4`

## import_xrefs

- `IPHLPAPI!ConvertGuidToStringW` at `0x1800599b8`
- `IPHLPAPI!ConvertGuidToStringW` at `0x180059aa2`
- `IPHLPAPI!ConvertGuidToStringW` at `0x1800599b8`
- `IPHLPAPI!ConvertGuidToStringW` at `0x180059aa2`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x180059a80`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x180059a80`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005999e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005999e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005996a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005996a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180059950`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180059950`

## string_xrefs

- `0x180059a48`: `System\CurrentControlSet\Services\IPHLPSVC\Parameters\Isatap`
- `0x180059bda`: `System\CurrentControlSet\Services\IPHLPSVC\Parameters\Isatap`
- `0x180059922`: `Entered: IsatapCreateIsatapInterface`
- `0x1800599d2`: `IsatapCreateIsatapInterface: For IPv4 Interface GUID %ls, DNS suffix %ls.`
- `0x180059a06`: `IsatapCreateIsatapInterface: Generated ISATAP Interface name: %ls.`
- `0x180059ac1`: `IsatapCreateIsatapInterface: Installed ISATAP Interface %ls, GUID = %ls, LUID = %I64x`
- `0x180059aef`: `IsatapCreateIsatapInterface: StringCchCopyW failed %d`
- `0x180059c00`: `Leaving: IsatapCreateIsatapInterface`

## pseudocode

```c
__int64 __fastcall IsatapCreateIsatapInterface(__int64 a1, const wchar_t *a2, __int64 a3)
{
  __int64 v6; // rax
  __int64 v7; // rbx
  HRESULT v8; // eax
  const wchar_t *v9; // r11
  int v10; // r8d
  int v11; // r11d
  bool v12; // zf
  NET_LUID InterfaceLuid; // [rsp+30h] [rbp-D0h] BYREF
  GUID InterfaceGuid; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v16[80]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t pszSrc[1032]; // [rsp+A0h] [rbp-60h] BYREF

  InterfaceLuid.Value = 0;
  InterfaceGuid = 0;
  memset_0(pszSrc, 0, 0x802u);
  EventWriteEnterEx(0x20000, L"Entered: IsatapCreateIsatapInterface");
  v6 = MALLOC(0x12F0u);
  v7 = v6;
  if ( !v6 )
    goto LABEL_22;
  InitializeCriticalSection((LPCRITICAL_SECTION)(v6 + 4736));
  *(_QWORD *)(v7 + 4784) = CreateEventW(0, 1, 1, 0);
  *(_DWORD *)(v7 + 12) = 2;
  if ( !(unsigned __int8)RoReferenceEx(v7 + 12)
    || (SetEvent(*(HANDLE *)(v7 + 4784)),
        ConvertGuidToStringW(a1, v16, 39),
        EventWrite0(0x2000000, L"IsatapCreateIsatapInterface: For IPv4 Interface GUID %ls, DNS suffix %ls.", v16, a2),
        (int)IsatapGenerateInterfaceName(pszSrc, a2) < 0)
    || (EventWrite0(0x2000000, L"IsatapCreateIsatapInterface: Generated ISATAP Interface name: %ls.", pszSrc),
        (int)InstallTunnelInterface(
               13,
               (__int64)pszSrc,
               (__int64)L"Microsoft ISATAP Adapter",
               *(_DWORD *)(a3 + 16),
               (__int64)&InterfaceGuid) < 0)
    || (unsigned int)StoreInterfaceGuidAndNameToRegistry(
                       (__int64)&InterfaceGuid,
                       (__int64)L"System\\CurrentControlSet\\Services\\IPHLPSVC\\Parameters\\Isatap",
                       (const BYTE *)pszSrc,
                       a1) )
  {
LABEL_21:
    _InterlockedDecrement((volatile signed __int32 *)(v7 + 12));
    CleanupIsatapInterface(v7);
    FREE(v7);
    v7 = 0;
    goto LABEL_22;
  }
  if ( (unsigned int)StartTunnelInterface(13, &InterfaceGuid) )
  {
LABEL_19:
    if ( (unsigned int)UninstallTunnelInterface((__int128 *)&InterfaceGuid) )
      DeleteInterfaceGuidFromRegistry(
        &InterfaceGuid,
        L"System\\CurrentControlSet\\Services\\IPHLPSVC\\Parameters\\Isatap");
    goto LABEL_21;
  }
  if ( ConvertInterfaceGuidToLuid(&InterfaceGuid, &InterfaceLuid) )
  {
LABEL_18:
    StopTunnelInterface(&InterfaceGuid);
    *(_BYTE *)(v7 + 2660) = 0;
    goto LABEL_19;
  }
  ConvertGuidToStringW(&InterfaceGuid, v16, 39);
  EventWrite0(
    0x2000000,
    L"IsatapCreateIsatapInterface: Installed ISATAP Interface %ls, GUID = %ls, LUID = %I64x",
    pszSrc,
    v16,
    InterfaceLuid.Value);
  v8 = StringCchCopyW((STRSAFE_LPWSTR)(v7 + 538), 0x401u, pszSrc);
  if ( v8 < 0
    || (v8 = StringCchCopyW((STRSAFE_LPWSTR)(v7 + 16), 0x105u, v9), (int)(v8 + 0x80000000) >= 0) && v8 != -2147024774 )
  {
    EventWrite0(0x2000000, L"IsatapCreateIsatapInterface: StringCchCopyW failed %d", (unsigned int)v8);
    goto LABEL_18;
  }
  v12 = *(_DWORD *)(v7 + 2676) == 0;
  *(GUID *)(v7 + 2592) = InterfaceGuid;
  *(NET_LUID *)(v7 + 2608) = InterfaceLuid;
  *(_DWORD *)(v7 + 2616) = -1;
  *(_BYTE *)(v7 + 2660) = 1;
  if ( v12 )
    *(_QWORD *)(v7 + 2640) = a3;
  *(_BYTE *)(v7 + 4730) = dword_1800CA12C != 2;
  v12 = IpHlpSvcEtwEnabled == 0;
  *(_QWORD *)v7 = qword_1800CA958;
  *(_DWORD *)(v7 + 8) = 0;
  qword_1800CA958 = v7;
  if ( !v12 && (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 4) != 0 )
    McTemplateU0qzq_EventWriteTransfer(v8 + 0x80000000, 0x80000000, v10, v11, 0);
  if ( !(unsigned __int8)RoReferenceEx(&dword_1800CA968) )
    goto LABEL_18;
LABEL_22:
  EventWriteLeaveEx(0x20000, L"Leaving: IsatapCreateIsatapInterface");
  return v7;
}

```

## disassembly

```asm
0x1800598cc  push    rbp
0x1800598ce  push    rbx
0x1800598cf  push    rsi
0x1800598d0  push    rdi
0x1800598d1  push    r13
0x1800598d3  push    r14
0x1800598d5  push    r15
0x1800598d7  lea     rbp, [rsp-7C0h]
0x1800598df  sub     rsp, 8C0h
0x1800598e6  mov     rax, cs:__security_cookie
0x1800598ed  xor     rax, rsp
0x1800598f0  mov     [rbp+7F0h+var_40], rax
0x1800598f7  mov     r14, r8
0x1800598fa  mov     qword ptr [rsp+8F0h+InterfaceLuid], 0
0x180059903  mov     r15, rdx
0x180059906  mov     rsi, rcx
0x180059909  xorps   xmm0, xmm0
0x18005990c  lea     rcx, [rbp+7F0h+pszSrc]; void *
0x180059910  xor     edx, edx; Val
0x180059912  mov     r8d, 802h; Size
0x180059918  movups  xmmword ptr [rsp+8F0h+InterfaceGuid.Data1], xmm0
0x18005991d  call    memset_0
0x180059922  lea     rdx, aEnteredIsatapc_0; "Entered: IsatapCreateIsatapInterface"
0x180059929  mov     ecx, 20000h
0x18005992e  call    EventWriteEnterEx
0x180059933  mov     ecx, 12F0h; dwBytes
0x180059938  call    MALLOC
0x18005993d  mov     rbx, rax
0x180059940  test    rax, rax
0x180059943  jz      loc_180059C00
0x180059949  lea     rcx, [rax+1280h]; lpCriticalSection
0x180059950  call    cs:__imp_InitializeCriticalSection
0x180059957  nop     dword ptr [rax+rax+00h]
0x18005995c  xor     r9d, r9d; lpName
0x18005995f  xor     ecx, ecx; lpEventAttributes
0x180059961  lea     eax, [r9+1]
0x180059965  mov     r8d, eax; bInitialState
0x180059968  mov     edx, eax; bManualReset
0x18005996a  call    cs:__imp_CreateEventW
0x180059971  nop     dword ptr [rax+rax+00h]
0x180059976  lea     rdi, [rbx+0Ch]
0x18005997a  mov     [rbx+12B0h], rax
0x180059981  mov     rcx, rdi
0x180059984  mov     dword ptr [rdi], 2
0x18005998a  call    RoReferenceEx
0x18005998f  test    al, al
0x180059991  jz      loc_180059BEB
0x180059997  mov     rcx, [rbx+12B0h]; hEvent
0x18005999e  call    cs:__imp_SetEvent
0x1800599a5  nop     dword ptr [rax+rax+00h]
0x1800599aa  mov     r8d, 27h ; '''
0x1800599b0  lea     rdx, [rsp+8F0h+var_8A0]
0x1800599b5  mov     rcx, rsi
0x1800599b8  call    cs:__imp_ConvertGuidToStringW
0x1800599bf  nop     dword ptr [rax+rax+00h]
0x1800599c4  mov     r13d, 2000000h
0x1800599ca  lea     r8, [rsp+8F0h+var_8A0]
0x1800599cf  mov     ecx, r13d
0x1800599d2  lea     rdx, aIsatapcreateis_0; "IsatapCreateIsatapInterface: For IPv4 I"...
0x1800599d9  mov     r9, r15
0x1800599dc  call    EventWrite0
0x1800599e1  lea     r9, [rbx+0A1Ch]
0x1800599e8  mov     r8, rsi
0x1800599eb  mov     rdx, r15; pszSrc
0x1800599ee  lea     rcx, [rbp+7F0h+pszSrc]; void *
0x1800599f2  call    IsatapGenerateInterfaceName
0x1800599f7  test    eax, eax
0x1800599f9  js      loc_180059BEB
0x1800599ff  lea     r8, [rbp+7F0h+pszSrc]
0x180059a03  mov     ecx, r13d
0x180059a06  lea     rdx, aIsatapcreateis; "IsatapCreateIsatapInterface: Generated "...
0x180059a0d  call    EventWrite0
0x180059a12  mov     r9d, [r14+10h]
0x180059a16  lea     rax, [rsp+8F0h+InterfaceGuid]
0x180059a1b  mov     r15d, 0Dh
0x180059a21  mov     [rsp+8F0h+var_8D0], rax
0x180059a26  mov     ecx, r15d
0x180059a29  lea     r8, aMicrosoftIsata; "Microsoft ISATAP Adapter"
0x180059a30  lea     rdx, [rbp+7F0h+pszSrc]
0x180059a34  call    InstallTunnelInterface
0x180059a39  test    eax, eax
0x180059a3b  js      loc_180059BEB
0x180059a41  mov     r9, rsi
0x180059a44  lea     r8, [rbp+7F0h+pszSrc]
0x180059a48  lea     rdx, aSystemCurrentc_8; "System\\CurrentControlSet\\Services\\IP"...
0x180059a4f  lea     rcx, [rsp+8F0h+InterfaceGuid]
0x180059a54  call    StoreInterfaceGuidAndNameToRegistry
0x180059a59  test    eax, eax
0x180059a5b  jnz     loc_180059BEB
0x180059a61  lea     rdx, [rsp+8F0h+InterfaceGuid]
0x180059a66  mov     ecx, r15d
0x180059a69  call    StartTunnelInterface
0x180059a6e  test    eax, eax
0x180059a70  jnz     loc_180059BCC
0x180059a76  lea     rdx, [rsp+8F0h+InterfaceLuid]; InterfaceLuid
0x180059a7b  lea     rcx, [rsp+8F0h+InterfaceGuid]; InterfaceGuid
0x180059a80  call    cs:__imp_ConvertInterfaceGuidToLuid
0x180059a87  nop     dword ptr [rax+rax+00h]
0x180059a8c  test    eax, eax
0x180059a8e  jnz     loc_180059BBB
0x180059a94  lea     r8d, [r15+1Ah]
0x180059a98  lea     rdx, [rsp+8F0h+var_8A0]
0x180059a9d  lea     rcx, [rsp+8F0h+InterfaceGuid]
0x180059aa2  call    cs:__imp_ConvertGuidToStringW
0x180059aa9  nop     dword ptr [rax+rax+00h]
0x180059aae  mov     rax, qword ptr [rsp+8F0h+InterfaceLuid]
0x180059ab3  lea     r9, [rsp+8F0h+var_8A0]
0x180059ab8  lea     r8, [rbp+7F0h+pszSrc]
0x180059abc  mov     [rsp+8F0h+var_8D0], rax
0x180059ac1  lea     rdx, aIsatapcreateis_1; "IsatapCreateIsatapInterface: Installed "...
0x180059ac8  mov     ecx, r13d
0x180059acb  call    EventWrite0
0x180059ad0  lea     r11, [rbx+21Ah]
0x180059ad7  mov     edx, 401h; cchDest
0x180059adc  mov     rcx, r11; pszDest
0x180059adf  lea     r8, [rbp+7F0h+pszSrc]; pszSrc
0x180059ae3  call    StringCchCopyW
0x180059ae8  test    eax, eax
0x180059aea  jns     short loc_180059B03
0x180059aec  mov     r8d, eax
0x180059aef  lea     rdx, aIsatapcreateis_2; "IsatapCreateIsatapInterface: StringCchC"...
0x180059af6  mov     ecx, r13d
0x180059af9  call    EventWrite0
0x180059afe  jmp     loc_180059BBB
0x180059b03  lea     rcx, [rbx+10h]; pszDest
0x180059b07  mov     r8, r11; pszSrc
0x180059b0a  mov     edx, 105h; cchDest
0x180059b0f  call    StringCchCopyW
0x180059b14  mov     edx, 80000000h
0x180059b19  lea     ecx, [rax+rdx]
0x180059b1c  test    edx, ecx
0x180059b1e  jnz     short loc_180059B27
0x180059b20  cmp     eax, 8007007Ah
0x180059b25  jnz     short loc_180059AEC
0x180059b27  cmp     dword ptr [rbx+0A74h], 0
0x180059b2e  movups  xmm0, xmmword ptr [rsp+8F0h+InterfaceGuid.Data1]
0x180059b33  movdqu  xmmword ptr [rbx+0A20h], xmm0
0x180059b3b  mov     rax, qword ptr [rsp+8F0h+InterfaceLuid]
0x180059b40  mov     [rbx+0A30h], rax
0x180059b47  mov     dword ptr [rbx+0A38h], 0FFFFFFFFh
0x180059b51  mov     byte ptr [rbx+0A64h], 1
0x180059b58  jnz     short loc_180059B61
0x180059b5a  mov     [rbx+0A50h], r14
0x180059b61  cmp     cs:dword_1800CA12C, 2
0x180059b68  setnz   al
0x180059b6b  mov     [rbx+127Ah], al
0x180059b71  cmp     cs:IpHlpSvcEtwEnabled, 0
0x180059b78  mov     rax, cs:qword_1800CA958
0x180059b7f  mov     [rbx], rax
0x180059b82  mov     dword ptr [rbx+8], 0
0x180059b89  mov     cs:qword_1800CA958, rbx
0x180059b90  jz      short loc_180059BAB
0x180059b92  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 4
0x180059b99  jz      short loc_180059BAB
0x180059b9b  mov     r9, r11
0x180059b9e  mov     dword ptr [rsp+8F0h+var_8D0], 0
0x180059ba6  call    McTemplateU0qzq_EventWriteTransfer
0x180059bab  lea     rcx, dword_1800CA968
0x180059bb2  call    RoReferenceEx
0x180059bb7  test    al, al
0x180059bb9  jnz     short loc_180059C00
0x180059bbb  lea     rcx, [rsp+8F0h+InterfaceGuid]; struct _GUID *
0x180059bc0  call    StopTunnelInterface
0x180059bc5  mov     byte ptr [rbx+0A64h], 0
0x180059bcc  lea     rcx, [rsp+8F0h+InterfaceGuid]
0x180059bd1  call    UninstallTunnelInterface
0x180059bd6  test    eax, eax
0x180059bd8  jz      short loc_180059BEB
0x180059bda  lea     rdx, aSystemCurrentc_8; "System\\CurrentControlSet\\Services\\IP"...
0x180059be1  lea     rcx, [rsp+8F0h+InterfaceGuid]
0x180059be6  call    DeleteInterfaceGuidFromRegistry
0x180059beb  lock dec dword ptr [rdi]
0x180059bee  mov     rcx, rbx
0x180059bf1  call    CleanupIsatapInterface
0x180059bf6  mov     rcx, rbx
0x180059bf9  call    FREE
0x180059bfe  xor     ebx, ebx
0x180059c00  lea     rdx, aLeavingIsatapc_0; "Leaving: IsatapCreateIsatapInterface"
0x180059c07  mov     ecx, 20000h
0x180059c0c  call    EventWriteLeaveEx
0x180059c11  mov     rax, rbx
0x180059c14  mov     rcx, [rbp+7F0h+var_40]
0x180059c1b  xor     rcx, rsp; StackCookie
0x180059c1e  call    __security_check_cookie
0x180059c23  add     rsp, 8C0h
0x180059c2a  pop     r15
0x180059c2c  pop     r14
0x180059c2e  pop     r13
0x180059c30  pop     rdi
0x180059c31  pop     rsi
0x180059c32  pop     rbx
0x180059c33  pop     rbp
0x180059c34  retn
```
