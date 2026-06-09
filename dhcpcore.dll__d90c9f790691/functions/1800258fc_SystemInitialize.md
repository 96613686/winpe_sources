# SystemInitialize

- ea: `0x1800258fc`
- end: `0x1800259ec`
- name: `SystemInitialize`
- size: `240`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180025350`

## callees

- `0x1800258fc`
- `0x18004d1a0`
- `0x18004d9e8`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180025985`
- `ntdll!RtlNtStatusToDosError` at `0x180025985`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002591e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002591e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002590c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002590c`
- `DNSAPI!DnsDhcpRegisterInit` at `0x1800259aa`
- `DNSAPI!DnsDhcpRegisterInit` at `0x1800259aa`
- `SspiCli!LsaRegisterPolicyChangeNotification` at `0x180025959`
- `SspiCli!LsaRegisterPolicyChangeNotification` at `0x180025959`

## pseudocode

```c
__int64 SystemInitialize()
{
  HANDLE EventW; // rax
  ULONG LastError; // eax
  ULONG v2; // ebx
  __int64 v3; // rdx
  unsigned int v4; // eax
  NTSTATUS v5; // ebx
  unsigned int v6; // eax
  unsigned int v7; // ebx

  EventW = CreateEventW(0, 0, 0, 0);
  DhcpLsaDnsDomChangeNotifyHandle = EventW;
  if ( EventW )
  {
    v4 = LsaRegisterPolicyChangeNotification(PolicyNotifyDnsDomainInformation, EventW);
    v5 = v4;
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_d(1028, 80, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, v4);
    LastError = RtlNtStatusToDosError(v5);
    v2 = LastError;
    if ( LastError )
    {
      if ( (xmmword_1800616A0 & 2) == 0 )
        return v2;
      v3 = 81;
      goto LABEL_4;
    }
    if ( DhcpGlobalUseMHAsyncDns )
    {
      v6 = DnsDhcpRegisterInit();
      v7 = v6;
      if ( (xmmword_1800616A0 & 2) != 0 )
        WPP_SF_D(1025, 82, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, v6);
      if ( v7 )
        DhcpGlobalUseMHAsyncDns = 0;
      return 0;
    }
  }
  else
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( (xmmword_1800616A0 & 2) != 0 )
    {
      v3 = 79;
LABEL_4:
      WPP_SF_D(1025, v3, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids, LastError);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x1800258fc  push    rbx
0x1800258fe  sub     rsp, 20h
0x180025902  xor     r9d, r9d; lpName
0x180025905  xor     r8d, r8d; bInitialState
0x180025908  xor     edx, edx; bManualReset
0x18002590a  xor     ecx, ecx; lpEventAttributes
0x18002590c  call    cs:__imp_CreateEventW
0x180025912  mov     cs:DhcpLsaDnsDomChangeNotifyHandle, rax
0x180025919  test    rax, rax
0x18002591c  jnz     short loc_180025951
0x18002591e  call    cs:__imp_GetLastError
0x180025924  mov     ebx, eax
0x180025926  test    byte ptr cs:xmmword_1800616A0, 2
0x18002592d  jz      loc_1800259E4
0x180025933  mov     edx, 4Fh ; 'O'
0x180025938  mov     ecx, 401h
0x18002593d  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x180025944  mov     r9d, eax
0x180025947  call    WPP_SF_D
0x18002594c  jmp     loc_1800259E4
0x180025951  mov     rdx, rax; NotificationEventHandle
0x180025954  mov     ecx, 4; InformationClass
0x180025959  call    cs:__imp_LsaRegisterPolicyChangeNotification
0x18002595f  mov     ebx, eax
0x180025961  test    byte ptr cs:xmmword_1800616A0, 10h
0x180025968  jz      short loc_180025983
0x18002596a  mov     edx, 50h ; 'P'
0x18002596f  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x180025976  mov     ecx, 404h
0x18002597b  mov     r9d, eax
0x18002597e  call    WPP_SF_d
0x180025983  mov     ecx, ebx; Status
0x180025985  call    cs:__imp_RtlNtStatusToDosError
0x18002598b  mov     ebx, eax
0x18002598d  test    eax, eax
0x18002598f  jz      short loc_1800259A1
0x180025991  test    byte ptr cs:xmmword_1800616A0, 2
0x180025998  jz      short loc_1800259E4
0x18002599a  mov     edx, 51h ; 'Q'
0x18002599f  jmp     short loc_180025938
0x1800259a1  cmp     cs:DhcpGlobalUseMHAsyncDns, 0
0x1800259a8  jz      short loc_1800259E4
0x1800259aa  call    cs:__imp_DnsDhcpRegisterInit
0x1800259b0  mov     ebx, eax
0x1800259b2  test    byte ptr cs:xmmword_1800616A0, 2
0x1800259b9  jz      short loc_1800259D4
0x1800259bb  mov     edx, 52h ; 'R'
0x1800259c0  lea     r8, WPP_5243b35b49d53d31703b6efd85ecfd51_Traceguids
0x1800259c7  mov     ecx, 401h
0x1800259cc  mov     r9d, eax
0x1800259cf  call    WPP_SF_D
0x1800259d4  test    ebx, ebx
0x1800259d6  jz      short loc_1800259E2
0x1800259d8  mov     cs:DhcpGlobalUseMHAsyncDns, 0
0x1800259e2  xor     ebx, ebx
0x1800259e4  mov     eax, ebx
0x1800259e6  add     rsp, 20h
0x1800259ea  pop     rbx
0x1800259eb  retn
```
