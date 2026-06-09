# IsatapCreateIsatapInterface

- ea: `0x1800598ac`
- end: `0x180059c16`
- name: `IsatapCreateIsatapInterface`
- size: `874`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180041160`

## callees

- `0x180004c54`
- `0x180008200`
- `0x18000d7b0`
- `0x180012dbc`
- `0x1800159c4`
- `0x18001f3f4`
- `0x18001f6c8`
- `0x180024240`
- `0x18002c824`
- `0x18003fb00`
- `0x18004702c`
- `0x18004ada8`
- `0x18004b630`
- `0x18004c1c8`
- `0x1800526c4`
- `0x180053418`
- `0x18005916c`
- `0x1800598ac`
- `0x18005b194`

## import_xrefs

- `IPHLPAPI!ConvertGuidToStringW` at `0x180059998`
- `IPHLPAPI!ConvertGuidToStringW` at `0x180059a82`
- `IPHLPAPI!ConvertGuidToStringW` at `0x180059998`
- `IPHLPAPI!ConvertGuidToStringW` at `0x180059a82`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x180059a60`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x180059a60`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005997e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18005997e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005994a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18005994a`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180059930`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180059930`

## string_xrefs

- `0x180059a28`: `System\CurrentControlSet\Services\IPHLPSVC\Parameters\Isatap`
- `0x180059bba`: `System\CurrentControlSet\Services\IPHLPSVC\Parameters\Isatap`
- `0x180059902`: `Entered: IsatapCreateIsatapInterface`
- `0x1800599b2`: `IsatapCreateIsatapInterface: For IPv4 Interface GUID %ls, DNS suffix %ls.`
- `0x1800599e6`: `IsatapCreateIsatapInterface: Generated ISATAP Interface name: %ls.`
- `0x180059aa1`: `IsatapCreateIsatapInterface: Installed ISATAP Interface %ls, GUID = %ls, LUID = %I64x`
- `0x180059acf`: `IsatapCreateIsatapInterface: StringCchCopyW failed %d`
- `0x180059be0`: `Leaving: IsatapCreateIsatapInterface`

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
0x1800598ac  push    rbp
0x1800598ae  push    rbx
0x1800598af  push    rsi
0x1800598b0  push    rdi
0x1800598b1  push    r13
0x1800598b3  push    r14
0x1800598b5  push    r15
0x1800598b7  lea     rbp, [rsp-7C0h]
0x1800598bf  sub     rsp, 8C0h
0x1800598c6  mov     rax, cs:__security_cookie
0x1800598cd  xor     rax, rsp
0x1800598d0  mov     [rbp+7F0h+var_40], rax
0x1800598d7  mov     r14, r8
0x1800598da  mov     qword ptr [rsp+8F0h+InterfaceLuid], 0
0x1800598e3  mov     r15, rdx
0x1800598e6  mov     rsi, rcx
0x1800598e9  xorps   xmm0, xmm0
0x1800598ec  lea     rcx, [rbp+7F0h+pszSrc]; void *
0x1800598f0  xor     edx, edx; Val
0x1800598f2  mov     r8d, 802h; Size
0x1800598f8  movups  xmmword ptr [rsp+8F0h+InterfaceGuid.Data1], xmm0
0x1800598fd  call    memset_0
0x180059902  lea     rdx, aEnteredIsatapc_0; "Entered: IsatapCreateIsatapInterface"
0x180059909  mov     ecx, 20000h
0x18005990e  call    EventWriteEnterEx
0x180059913  mov     ecx, 12F0h; dwBytes
0x180059918  call    MALLOC
0x18005991d  mov     rbx, rax
0x180059920  test    rax, rax
0x180059923  jz      loc_180059BE0
0x180059929  lea     rcx, [rax+1280h]; lpCriticalSection
0x180059930  call    cs:__imp_InitializeCriticalSection
0x180059937  nop     dword ptr [rax+rax+00h]
0x18005993c  xor     r9d, r9d; lpName
0x18005993f  xor     ecx, ecx; lpEventAttributes
0x180059941  lea     eax, [r9+1]
0x180059945  mov     r8d, eax; bInitialState
0x180059948  mov     edx, eax; bManualReset
0x18005994a  call    cs:__imp_CreateEventW
0x180059951  nop     dword ptr [rax+rax+00h]
0x180059956  lea     rdi, [rbx+0Ch]
0x18005995a  mov     [rbx+12B0h], rax
0x180059961  mov     rcx, rdi
0x180059964  mov     dword ptr [rdi], 2
0x18005996a  call    RoReferenceEx
0x18005996f  test    al, al
0x180059971  jz      loc_180059BCB
0x180059977  mov     rcx, [rbx+12B0h]; hEvent
0x18005997e  call    cs:__imp_SetEvent
0x180059985  nop     dword ptr [rax+rax+00h]
0x18005998a  mov     r8d, 27h ; '''
0x180059990  lea     rdx, [rsp+8F0h+var_8A0]
0x180059995  mov     rcx, rsi
0x180059998  call    cs:__imp_ConvertGuidToStringW
0x18005999f  nop     dword ptr [rax+rax+00h]
0x1800599a4  mov     r13d, 2000000h
0x1800599aa  lea     r8, [rsp+8F0h+var_8A0]
0x1800599af  mov     ecx, r13d
0x1800599b2  lea     rdx, aIsatapcreateis_0; "IsatapCreateIsatapInterface: For IPv4 I"...
0x1800599b9  mov     r9, r15
0x1800599bc  call    EventWrite0
0x1800599c1  lea     r9, [rbx+0A1Ch]
0x1800599c8  mov     r8, rsi
0x1800599cb  mov     rdx, r15; pszSrc
0x1800599ce  lea     rcx, [rbp+7F0h+pszSrc]; void *
0x1800599d2  call    IsatapGenerateInterfaceName
0x1800599d7  test    eax, eax
0x1800599d9  js      loc_180059BCB
0x1800599df  lea     r8, [rbp+7F0h+pszSrc]
0x1800599e3  mov     ecx, r13d
0x1800599e6  lea     rdx, aIsatapcreateis; "IsatapCreateIsatapInterface: Generated "...
0x1800599ed  call    EventWrite0
0x1800599f2  mov     r9d, [r14+10h]
0x1800599f6  lea     rax, [rsp+8F0h+InterfaceGuid]
0x1800599fb  mov     r15d, 0Dh
0x180059a01  mov     [rsp+8F0h+var_8D0], rax
0x180059a06  mov     ecx, r15d
0x180059a09  lea     r8, aMicrosoftIsata; "Microsoft ISATAP Adapter"
0x180059a10  lea     rdx, [rbp+7F0h+pszSrc]
0x180059a14  call    InstallTunnelInterface
0x180059a19  test    eax, eax
0x180059a1b  js      loc_180059BCB
0x180059a21  mov     r9, rsi
0x180059a24  lea     r8, [rbp+7F0h+pszSrc]
0x180059a28  lea     rdx, aSystemCurrentc_8; "System\\CurrentControlSet\\Services\\IP"...
0x180059a2f  lea     rcx, [rsp+8F0h+InterfaceGuid]
0x180059a34  call    StoreInterfaceGuidAndNameToRegistry
0x180059a39  test    eax, eax
0x180059a3b  jnz     loc_180059BCB
0x180059a41  lea     rdx, [rsp+8F0h+InterfaceGuid]
0x180059a46  mov     ecx, r15d
0x180059a49  call    StartTunnelInterface
0x180059a4e  test    eax, eax
0x180059a50  jnz     loc_180059BAC
0x180059a56  lea     rdx, [rsp+8F0h+InterfaceLuid]; InterfaceLuid
0x180059a5b  lea     rcx, [rsp+8F0h+InterfaceGuid]; InterfaceGuid
0x180059a60  call    cs:__imp_ConvertInterfaceGuidToLuid
0x180059a67  nop     dword ptr [rax+rax+00h]
0x180059a6c  test    eax, eax
0x180059a6e  jnz     loc_180059B9B
0x180059a74  lea     r8d, [r15+1Ah]
0x180059a78  lea     rdx, [rsp+8F0h+var_8A0]
0x180059a7d  lea     rcx, [rsp+8F0h+InterfaceGuid]
0x180059a82  call    cs:__imp_ConvertGuidToStringW
0x180059a89  nop     dword ptr [rax+rax+00h]
0x180059a8e  mov     rax, qword ptr [rsp+8F0h+InterfaceLuid]
0x180059a93  lea     r9, [rsp+8F0h+var_8A0]
0x180059a98  lea     r8, [rbp+7F0h+pszSrc]
0x180059a9c  mov     [rsp+8F0h+var_8D0], rax
0x180059aa1  lea     rdx, aIsatapcreateis_1; "IsatapCreateIsatapInterface: Installed "...
0x180059aa8  mov     ecx, r13d
0x180059aab  call    EventWrite0
0x180059ab0  lea     r11, [rbx+21Ah]
0x180059ab7  mov     edx, 401h; cchDest
0x180059abc  mov     rcx, r11; pszDest
0x180059abf  lea     r8, [rbp+7F0h+pszSrc]; pszSrc
0x180059ac3  call    StringCchCopyW
0x180059ac8  test    eax, eax
0x180059aca  jns     short loc_180059AE3
0x180059acc  mov     r8d, eax
0x180059acf  lea     rdx, aIsatapcreateis_2; "IsatapCreateIsatapInterface: StringCchC"...
0x180059ad6  mov     ecx, r13d
0x180059ad9  call    EventWrite0
0x180059ade  jmp     loc_180059B9B
0x180059ae3  lea     rcx, [rbx+10h]; pszDest
0x180059ae7  mov     r8, r11; pszSrc
0x180059aea  mov     edx, 105h; cchDest
0x180059aef  call    StringCchCopyW
0x180059af4  mov     edx, 80000000h
0x180059af9  lea     ecx, [rax+rdx]
0x180059afc  test    edx, ecx
0x180059afe  jnz     short loc_180059B07
0x180059b00  cmp     eax, 8007007Ah
0x180059b05  jnz     short loc_180059ACC
0x180059b07  cmp     dword ptr [rbx+0A74h], 0
0x180059b0e  movups  xmm0, xmmword ptr [rsp+8F0h+InterfaceGuid.Data1]
0x180059b13  movdqu  xmmword ptr [rbx+0A20h], xmm0
0x180059b1b  mov     rax, qword ptr [rsp+8F0h+InterfaceLuid]
0x180059b20  mov     [rbx+0A30h], rax
0x180059b27  mov     dword ptr [rbx+0A38h], 0FFFFFFFFh
0x180059b31  mov     byte ptr [rbx+0A64h], 1
0x180059b38  jnz     short loc_180059B41
0x180059b3a  mov     [rbx+0A50h], r14
0x180059b41  cmp     cs:dword_1800CA12C, 2
0x180059b48  setnz   al
0x180059b4b  mov     [rbx+127Ah], al
0x180059b51  cmp     cs:IpHlpSvcEtwEnabled, 0
0x180059b58  mov     rax, cs:qword_1800CA958
0x180059b5f  mov     [rbx], rax
0x180059b62  mov     dword ptr [rbx+8], 0
0x180059b69  mov     cs:qword_1800CA958, rbx
0x180059b70  jz      short loc_180059B8B
0x180059b72  test    byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits, 4
0x180059b79  jz      short loc_180059B8B
0x180059b7b  mov     r9, r11
0x180059b7e  mov     dword ptr [rsp+8F0h+var_8D0], 0
0x180059b86  call    McTemplateU0qzq_EventWriteTransfer
0x180059b8b  lea     rcx, dword_1800CA968
0x180059b92  call    RoReferenceEx
0x180059b97  test    al, al
0x180059b99  jnz     short loc_180059BE0
0x180059b9b  lea     rcx, [rsp+8F0h+InterfaceGuid]; struct _GUID *
0x180059ba0  call    StopTunnelInterface
0x180059ba5  mov     byte ptr [rbx+0A64h], 0
0x180059bac  lea     rcx, [rsp+8F0h+InterfaceGuid]
0x180059bb1  call    UninstallTunnelInterface
0x180059bb6  test    eax, eax
0x180059bb8  jz      short loc_180059BCB
0x180059bba  lea     rdx, aSystemCurrentc_8; "System\\CurrentControlSet\\Services\\IP"...
0x180059bc1  lea     rcx, [rsp+8F0h+InterfaceGuid]
0x180059bc6  call    DeleteInterfaceGuidFromRegistry
0x180059bcb  lock dec dword ptr [rdi]
0x180059bce  mov     rcx, rbx
0x180059bd1  call    CleanupIsatapInterface
0x180059bd6  mov     rcx, rbx
0x180059bd9  call    FREE
0x180059bde  xor     ebx, ebx
0x180059be0  lea     rdx, aLeavingIsatapc_0; "Leaving: IsatapCreateIsatapInterface"
0x180059be7  mov     ecx, 20000h
0x180059bec  call    EventWriteLeaveEx
0x180059bf1  mov     rax, rbx
0x180059bf4  mov     rcx, [rbp+7F0h+var_40]
0x180059bfb  xor     rcx, rsp; StackCookie
0x180059bfe  call    __security_check_cookie
0x180059c03  add     rsp, 8C0h
0x180059c0a  pop     r15
0x180059c0c  pop     r14
0x180059c0e  pop     r13
0x180059c10  pop     rdi
0x180059c11  pop     rsi
0x180059c12  pop     rbx
0x180059c13  pop     rbp
0x180059c14  retn
```
