# InitializeDirectTunnels

- ea: `0x18003a090`
- end: `0x18003a49b`
- name: `InitializeDirectTunnels`
- size: `1035`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004c64`
- `0x180004f60`
- `0x180009010`
- `0x18000cea0`
- `0x18000d7c0`
- `0x180012dcc`
- `0x1800190f0`
- `0x18001e9cc`
- `0x18003a090`
- `0x18004b5f0`
- `0x18004c188`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003a1ce`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003a1ce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a3dc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a3dc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003a181`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003a181`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18003a240`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18003a240`
- `IPHLPAPI!ConvertStringToGuidW` at `0x18003a20c`
- `IPHLPAPI!ConvertStringToGuidW` at `0x18003a20c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18003a3f2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18003a3f2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003a42f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003a42f`
- `NSI!NsiGetAllParameters` at `0x18003a298`
- `NSI!NsiGetAllParameters` at `0x18003a302`
- `NSI!NsiGetAllParameters` at `0x18003a298`
- `NSI!NsiGetAllParameters` at `0x18003a302`

## string_xrefs

- `0x18003a124`: `onecoreuap\net\netio\iphlpsvc\service\direct.c`
- `0x18003a402`: `onecoreuap\net\netio\iphlpsvc\service\direct.c`
- `0x18003a173`: `System\CurrentControlSet\Services\IPHLPSVC\Direct`
- `0x18003a194`: `Direct Tunnel failed to open regkey for tunnels: 0x%x`
- `0x18003a441`: `onecoreuap\net\netio\iphlpsvc\service\direct.c`
- `0x18003a3b4`: `Direct Tunnel failed to read tunnel GUID subkey: 0x%x`

## pseudocode

```c
void __fastcall InitializeDirectTunnels(PTP_CALLBACK_INSTANCE Instance, PVOID Context)
{
  unsigned int v2; // eax
  DWORD i; // edi
  unsigned int v4; // eax
  unsigned int v5; // eax
  unsigned int v6; // eax
  unsigned int AllParameters; // eax
  unsigned int v8; // eax
  __int64 v9; // rbx
  unsigned int started; // eax
  __int64 *v11; // rax
  HANDLE v12; // rbx
  LPWSTR lpClass; // [rsp+28h] [rbp-D8h]
  LPDWORD lpcchClass; // [rsp+30h] [rbp-D0h]
  DWORD cchName; // [rsp+60h] [rbp-A0h] BYREF
  NET_LUID InterfaceLuid; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  int InBuffer; // [rsp+80h] [rbp-80h] BYREF
  GUID InterfaceGuid; // [rsp+84h] [rbp-7Ch] BYREF
  int v20; // [rsp+94h] [rbp-6Ch]
  _BYTE v21[32]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v22[40]; // [rsp+B8h] [rbp-48h] BYREF
  WCHAR Name[40]; // [rsp+E0h] [rbp-20h] BYREF

  memset_0(Name, 0, 0x4Eu);
  cchName = 39;
  hKey = 0;
  InterfaceLuid.Value = 0;
  memset_0(&InBuffer, 0, 0x58u);
  if ( IpHlpSvcEtwEnabled && (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800000) != 0 )
    McTemplateU0z_EventWriteTransfer(
      MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
      EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE,
      L"Entered: InitializeDirectTunnels");
  if ( (unsigned int)GetAndTraceLock(
                       "onecoreuap\\net\\netio\\iphlpsvc\\service\\direct.c",
                       "InitializeDirectTunnels",
                       46,
                       g_DirectTunnelLock) )
  {
    dword_1800CBAA0 |= 1u;
    qword_1800CBAB0 = (__int64)&qword_1800CBAA8;
    qword_1800CBAA8 = (__int64)&qword_1800CBAA8;
    v2 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\IPHLPSVC\\Direct", 0, 0x20019u, &hKey);
    if ( v2 )
    {
      EventWriteError0(0x800000, L"Direct Tunnel failed to open regkey for tunnels: 0x%x", v2);
    }
    else
    {
      for ( i = 0; ; ++i )
      {
        v4 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
        if ( v4 == 259 )
          break;
        if ( v4 )
        {
          EventWriteError0(0x800000, L"Direct Tunnel failed to read tunnel GUID subkey: 0x%x", v4);
          goto LABEL_30;
        }
        memset_0(&InBuffer, 0, 0x58u);
        cchName = 39;
        v5 = ConvertStringToGuidW(Name, &InterfaceGuid);
        if ( v5 )
        {
          EventWriteError0(0x800000, L"Direct Tunnel failed to convert \"%ws\" to GUID 0x%x", Name, v5);
        }
        else
        {
          v6 = ConvertInterfaceGuidToLuid(&InterfaceGuid, &InterfaceLuid);
          if ( v6 )
          {
            EventWriteError0(0x800000, L"Direct Tunnel failed to get tunnel LUID for GUID %ws: 0x%x", Name, v6);
          }
          else
          {
            AllParameters = NsiGetAllParameters(0, &NPI_MS_FL6T_MODULEID, 4, &InterfaceLuid, 8, v22, 32, 0, 0, 0, 0);
            if ( AllParameters )
            {
              EventWriteError0(
                0x800000,
                L"Direct Tunnel failed to get tunnel remote DL address 0x%x, interface %ws",
                AllParameters,
                Name);
            }
            else
            {
              v8 = NsiGetAllParameters(0, &NPI_MS_FL6T_MODULEID, 2, &InterfaceLuid, 8, v21, 32, 0, 0, 0, 0);
              if ( v8 )
              {
                EventWriteError0(
                  0x800000,
                  L"Direct Tunnel failed to get tunnel local DL address 0x%x, interface: %ws",
                  v8,
                  Name);
              }
              else
              {
                v9 = MALLOC(0x20u);
                if ( v9 )
                {
                  InBuffer = 2;
                  v20 = 4;
                  started = StartTunnelInterfaceEx((char *)&InBuffer);
                  if ( started )
                  {
                    EventWriteError0(
                      0x800000,
                      L"Direct Tunnel failed to start tunnel 0x%x, interface %ws",
                      started,
                      Name);
                    FREE(v9);
                  }
                  else
                  {
                    *(GUID *)(v9 + 16) = InterfaceGuid;
                    v11 = (__int64 *)qword_1800CBAB0;
                    if ( *(__int64 **)qword_1800CBAB0 != &qword_1800CBAA8 )
                      __fastfail(3u);
                    *(_QWORD *)v9 = &qword_1800CBAA8;
                    *(_QWORD *)(v9 + 8) = v11;
                    *v11 = v9;
                    qword_1800CBAB0 = v9;
                  }
                }
                else
                {
                  EventWriteError0(
                    0x800000,
                    L"Direct Tunnel failed to allocate memory for tunnel state. Interface: %ws",
                    Name);
                }
              }
            }
          }
        }
      }
      EventWrite0(0x800000, L"Direct Tunnel successfully finished starting %d persisted tunnels!", i);
LABEL_30:
      RegCloseKey(hKey);
    }
  }
  v12 = g_DirectTunnelLock;
  LODWORD(lpcchClass) = ReleaseMutex(g_DirectTunnelLock);
  LODWORD(lpClass) = 200;
  EventWrite0(
    0x800000,
    L"Lock (%p) released at %S : %S : %u. Return %d",
    v12,
    "onecoreuap\\net\\netio\\iphlpsvc\\service\\direct.c",
    "InitializeDirectTunnels",
    lpClass,
    lpcchClass);
  SetEvent(g_DirectTunnelStartCompleteEvent);
  DereferenceServiceEx("InitializeDirectTunnels", L"onecoreuap\\net\\netio\\iphlpsvc\\service\\direct.c", 202);
  if ( IpHlpSvcEtwEnabled )
  {
    if ( (Microsoft_Windows_Iphlpsvc_TraceEnableBits & 0x800000) != 0 )
      McTemplateU0z_EventWriteTransfer(
        MS_IPHLPSVC_ETW_PROVIDER_ID_Context,
        EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE,
        L"Leaving: InitializeDirectTunnels");
  }
}

```

## disassembly

```asm
0x18003a090  push    rbp
0x18003a092  push    rbx
0x18003a093  push    rsi
0x18003a094  push    rdi
0x18003a095  push    r13
0x18003a097  push    r14
0x18003a099  push    r15
0x18003a09b  lea     rbp, [rsp-40h]
0x18003a0a0  sub     rsp, 140h
0x18003a0a7  mov     rax, cs:__security_cookie
0x18003a0ae  xor     rax, rsp
0x18003a0b1  mov     [rbp+70h+var_40], rax
0x18003a0b5  xor     edx, edx; Val
0x18003a0b7  lea     rcx, [rbp+70h+Name]; void *
0x18003a0bb  lea     r8d, [rdx+4Eh]; Size
0x18003a0bf  call    memset_0
0x18003a0c4  xor     esi, esi
0x18003a0c6  mov     [rsp+170h+cchName], 27h ; '''
0x18003a0ce  xor     edx, edx; Val
0x18003a0d0  mov     [rsp+170h+hKey], rsi
0x18003a0d5  lea     rcx, [rbp+70h+InBuffer]; void *
0x18003a0d9  mov     qword ptr [rsp+170h+InterfaceLuid], rsi
0x18003a0de  lea     r8d, [rsi+58h]; Size
0x18003a0e2  call    memset_0
0x18003a0e7  cmp     cs:IpHlpSvcEtwEnabled, sil
0x18003a0ee  jz      short loc_18003A113
0x18003a0f0  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, sil
0x18003a0f7  jge     short loc_18003A113
0x18003a0f9  lea     r8, aEnteredInitial_0; "Entered: InitializeDirectTunnels"
0x18003a100  lea     rdx, EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE
0x18003a107  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18003a10e  call    McTemplateU0z_EventWriteTransfer
0x18003a113  mov     r9, cs:g_DirectTunnelLock
0x18003a11a  lea     r13, aInitializedire; "InitializeDirectTunnels"
0x18003a121  mov     rdx, r13
0x18003a124  lea     rcx, aOnecoreuapNetN_30; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18003a12b  mov     r8d, 2Eh ; '.'
0x18003a131  call    GetAndTraceLock
0x18003a136  mov     r14d, 800000h
0x18003a13c  test    eax, eax
0x18003a13e  jz      loc_18003A3E8
0x18003a144  or      cs:dword_1800CBAA0, 1
0x18003a14b  lea     r15, qword_1800CBAA8
0x18003a152  lea     rax, [rsp+170h+hKey]
0x18003a157  mov     cs:qword_1800CBAB0, r15
0x18003a15e  mov     r9d, 20019h; samDesired
0x18003a164  mov     cs:qword_1800CBAA8, r15
0x18003a16b  xor     r8d, r8d; ulOptions
0x18003a16e  mov     [rsp+170h+phkResult], rax; phkResult
0x18003a173  lea     rdx, aSystemCurrentc_16; "System\\CurrentControlSet\\Services\\IP"...
0x18003a17a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003a181  call    cs:__imp_RegOpenKeyExW
0x18003a188  nop     dword ptr [rax+rax+00h]
0x18003a18d  test    eax, eax
0x18003a18f  jz      short loc_18003A1A8
0x18003a191  mov     r8d, eax
0x18003a194  lea     rdx, aDirectTunnelFa_8; "Direct Tunnel failed to open regkey for"...
0x18003a19b  mov     ecx, r14d
0x18003a19e  call    EventWriteError0
0x18003a1a3  jmp     loc_18003A3E8
0x18003a1a8  mov     edi, esi
0x18003a1aa  mov     rcx, [rsp+170h+hKey]; hKey
0x18003a1af  lea     r9, [rsp+170h+cchName]; lpcchName
0x18003a1b4  mov     [rsp+170h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x18003a1b9  lea     r8, [rbp+70h+Name]; lpName
0x18003a1bd  mov     [rsp+170h+lpcchClass], rsi; lpcchClass
0x18003a1c2  mov     edx, edi; dwIndex
0x18003a1c4  mov     [rsp+170h+lpClass], rsi; lpClass
0x18003a1c9  mov     [rsp+170h+phkResult], rsi; lpReserved
0x18003a1ce  call    cs:__imp_RegEnumKeyExW
0x18003a1d5  nop     dword ptr [rax+rax+00h]
0x18003a1da  cmp     eax, 103h
0x18003a1df  jz      loc_18003A3C5
0x18003a1e5  test    eax, eax
0x18003a1e7  jnz     loc_18003A3B1
0x18003a1ed  xor     edx, edx; Val
0x18003a1ef  lea     r8d, [rax+58h]; Size
0x18003a1f3  lea     rcx, [rbp+70h+InBuffer]; void *
0x18003a1f7  call    memset_0
0x18003a1fc  lea     rdx, [rbp+70h+InterfaceGuid]
0x18003a200  mov     [rsp+170h+cchName], 27h ; '''
0x18003a208  lea     rcx, [rbp+70h+Name]
0x18003a20c  call    cs:__imp_ConvertStringToGuidW
0x18003a213  nop     dword ptr [rax+rax+00h]
0x18003a218  test    eax, eax
0x18003a21a  jz      short loc_18003A237
0x18003a21c  lea     rdx, aDirectTunnelFa_5; "Direct Tunnel failed to convert \"%ws\""...
0x18003a223  lea     r8, [rbp+70h+Name]
0x18003a227  mov     r9d, eax
0x18003a22a  mov     ecx, r14d
0x18003a22d  call    EventWriteError0
0x18003a232  jmp     loc_18003A3A3
0x18003a237  lea     rdx, [rsp+170h+InterfaceLuid]; InterfaceLuid
0x18003a23c  lea     rcx, [rbp+70h+InterfaceGuid]; InterfaceGuid
0x18003a240  call    cs:__imp_ConvertInterfaceGuidToLuid
0x18003a247  nop     dword ptr [rax+rax+00h]
0x18003a24c  test    eax, eax
0x18003a24e  jz      short loc_18003A259
0x18003a250  lea     rdx, aDirectTunnelFa_13; "Direct Tunnel failed to get tunnel LUID"...
0x18003a257  jmp     short loc_18003A223
0x18003a259  mov     [rsp+170h+var_120], esi
0x18003a25d  lea     rax, [rbp+70h+var_B8]
0x18003a261  mov     [rsp+170h+var_128], rsi
0x18003a266  lea     r9, [rsp+170h+InterfaceLuid]
0x18003a26b  mov     [rsp+170h+var_130], esi
0x18003a26f  lea     rdx, NPI_MS_FL6T_MODULEID
0x18003a276  mov     [rsp+170h+lpftLastWriteTime], rsi
0x18003a27b  mov     r8d, 4
0x18003a281  mov     dword ptr [rsp+170h+lpcchClass], 20h ; ' '
0x18003a289  xor     ecx, ecx
0x18003a28b  mov     [rsp+170h+lpClass], rax
0x18003a290  mov     dword ptr [rsp+170h+phkResult], 8
0x18003a298  call    cs:__imp_NsiGetAllParameters
0x18003a29f  nop     dword ptr [rax+rax+00h]
0x18003a2a4  test    eax, eax
0x18003a2a6  jz      short loc_18003A2C3
0x18003a2a8  lea     rdx, aDirectTunnelFa_9; "Direct Tunnel failed to get tunnel remo"...
0x18003a2af  mov     r8d, eax
0x18003a2b2  lea     r9, [rbp+70h+Name]
0x18003a2b6  mov     ecx, r14d
0x18003a2b9  call    EventWriteError0
0x18003a2be  jmp     loc_18003A3A3
0x18003a2c3  mov     [rsp+170h+var_120], esi
0x18003a2c7  lea     rax, [rbp+70h+var_D8]
0x18003a2cb  mov     [rsp+170h+var_128], rsi
0x18003a2d0  lea     r9, [rsp+170h+InterfaceLuid]
0x18003a2d5  mov     [rsp+170h+var_130], esi
0x18003a2d9  lea     rdx, NPI_MS_FL6T_MODULEID
0x18003a2e0  mov     [rsp+170h+lpftLastWriteTime], rsi
0x18003a2e5  mov     r8d, 2
0x18003a2eb  mov     dword ptr [rsp+170h+lpcchClass], 20h ; ' '
0x18003a2f3  xor     ecx, ecx
0x18003a2f5  mov     [rsp+170h+lpClass], rax
0x18003a2fa  mov     dword ptr [rsp+170h+phkResult], 8
0x18003a302  call    cs:__imp_NsiGetAllParameters
0x18003a309  nop     dword ptr [rax+rax+00h]
0x18003a30e  test    eax, eax
0x18003a310  jz      short loc_18003A31B
0x18003a312  lea     rdx, aDirectTunnelFa_12; "Direct Tunnel failed to get tunnel loca"...
0x18003a319  jmp     short loc_18003A2AF
0x18003a31b  mov     ecx, 20h ; ' '; dwBytes
0x18003a320  call    MALLOC
0x18003a325  mov     rbx, rax
0x18003a328  test    rax, rax
0x18003a32b  jnz     short loc_18003A342
0x18003a32d  lea     r8, [rbp+70h+Name]
0x18003a331  mov     ecx, r14d
0x18003a334  lea     rdx, aDirectTunnelFa_3; "Direct Tunnel failed to allocate memory"...
0x18003a33b  call    EventWriteError0
0x18003a340  jmp     short loc_18003A3A3
0x18003a342  lea     rcx, [rbp+70h+InBuffer]; lpInBuffer
0x18003a346  mov     [rbp+70h+InBuffer], 2
0x18003a34d  mov     [rbp+70h+var_DC], 4
0x18003a354  call    StartTunnelInterfaceEx
0x18003a359  test    eax, eax
0x18003a35b  jz      short loc_18003A37D
0x18003a35d  lea     r9, [rbp+70h+Name]
0x18003a361  mov     r8d, eax
0x18003a364  lea     rdx, aDirectTunnelFa_6; "Direct Tunnel failed to start tunnel 0x"...
0x18003a36b  mov     ecx, r14d
0x18003a36e  call    EventWriteError0
0x18003a373  mov     rcx, rbx
0x18003a376  call    FREE
0x18003a37b  jmp     short loc_18003A3A3
0x18003a37d  movups  xmm0, xmmword ptr [rbp+70h+InterfaceGuid.Data1]
0x18003a381  movdqu  xmmword ptr [rbx+10h], xmm0
0x18003a386  mov     rax, cs:qword_1800CBAB0
0x18003a38d  cmp     [rax], r15
0x18003a390  jnz     short loc_18003A3AA
0x18003a392  mov     [rbx], r15
0x18003a395  mov     [rbx+8], rax
0x18003a399  mov     [rax], rbx
0x18003a39c  mov     cs:qword_1800CBAB0, rbx
0x18003a3a3  inc     edi
0x18003a3a5  jmp     loc_18003A1AA
0x18003a3aa  mov     ecx, 3
0x18003a3af  int     29h; Win8: RtlFailFast(ecx)
0x18003a3b1  mov     r8d, eax
0x18003a3b4  lea     rdx, aDirectTunnelFa_0; "Direct Tunnel failed to read tunnel GUI"...
0x18003a3bb  mov     ecx, r14d
0x18003a3be  call    EventWriteError0
0x18003a3c3  jmp     short loc_18003A3D7
0x18003a3c5  mov     r8d, edi
0x18003a3c8  lea     rdx, aDirectTunnelSu; "Direct Tunnel successfully finished sta"...
0x18003a3cf  mov     ecx, r14d
0x18003a3d2  call    EventWrite0
0x18003a3d7  mov     rcx, [rsp+170h+hKey]; hKey
0x18003a3dc  call    cs:__imp_RegCloseKey
0x18003a3e3  nop     dword ptr [rax+rax+00h]
0x18003a3e8  mov     rbx, cs:g_DirectTunnelLock
0x18003a3ef  mov     rcx, rbx; hMutex
0x18003a3f2  call    cs:__imp_ReleaseMutex
0x18003a3f9  nop     dword ptr [rax+rax+00h]
0x18003a3fe  mov     dword ptr [rsp+170h+lpcchClass], eax
0x18003a402  lea     r9, aOnecoreuapNetN_30; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18003a409  mov     dword ptr [rsp+170h+lpClass], 0C8h
0x18003a411  mov     r8, rbx
0x18003a414  lea     rdx, aLockPReleasedA; "Lock (%p) released at %S : %S : %u. Ret"...
0x18003a41b  mov     [rsp+170h+phkResult], r13
0x18003a420  mov     ecx, r14d
0x18003a423  call    EventWrite0
0x18003a428  mov     rcx, cs:g_DirectTunnelStartCompleteEvent; hEvent
0x18003a42f  call    cs:__imp_SetEvent
0x18003a436  nop     dword ptr [rax+rax+00h]
0x18003a43b  mov     r8d, 0CAh
0x18003a441  lea     rdx, aOnecoreuapNetN_6; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18003a448  mov     rcx, r13
0x18003a44b  call    DereferenceServiceEx
0x18003a450  cmp     cs:IpHlpSvcEtwEnabled, sil
0x18003a457  jz      short loc_18003A47C
0x18003a459  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, sil
0x18003a460  jge     short loc_18003A47C
0x18003a462  lea     r8, aLeavingInitial_0; "Leaving: InitializeDirectTunnels"
0x18003a469  lea     rdx, EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE
0x18003a470  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18003a477  call    McTemplateU0z_EventWriteTransfer
0x18003a47c  mov     rcx, [rbp+70h+var_40]
0x18003a480  xor     rcx, rsp; StackCookie
0x18003a483  call    __security_check_cookie
0x18003a488  add     rsp, 140h
0x18003a48f  pop     r15
0x18003a491  pop     r14
0x18003a493  pop     r13
0x18003a495  pop     rdi
0x18003a496  pop     rsi
0x18003a497  pop     rbx
0x18003a498  pop     rbp
0x18003a499  retn
```
