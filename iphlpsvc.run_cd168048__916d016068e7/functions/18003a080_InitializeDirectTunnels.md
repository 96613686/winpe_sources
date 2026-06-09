# InitializeDirectTunnels

- ea: `0x18003a080`
- end: `0x18003a48b`
- name: `InitializeDirectTunnels`
- size: `1035`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180004c54`
- `0x180004f50`
- `0x180009000`
- `0x18000ce90`
- `0x18000d7b0`
- `0x180012dbc`
- `0x1800190e0`
- `0x18001e9bc`
- `0x18003a080`
- `0x18004b630`
- `0x18004c1c8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003a1be`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003a1be`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a3cc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003a3cc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003a171`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003a171`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18003a230`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x18003a230`
- `IPHLPAPI!ConvertStringToGuidW` at `0x18003a1fc`
- `IPHLPAPI!ConvertStringToGuidW` at `0x18003a1fc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18003a3e2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18003a3e2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003a41f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18003a41f`
- `NSI!NsiGetAllParameters` at `0x18003a288`
- `NSI!NsiGetAllParameters` at `0x18003a2f2`
- `NSI!NsiGetAllParameters` at `0x18003a288`
- `NSI!NsiGetAllParameters` at `0x18003a2f2`

## string_xrefs

- `0x18003a114`: `onecoreuap\net\netio\iphlpsvc\service\direct.c`
- `0x18003a3f2`: `onecoreuap\net\netio\iphlpsvc\service\direct.c`
- `0x18003a163`: `System\CurrentControlSet\Services\IPHLPSVC\Direct`
- `0x18003a184`: `Direct Tunnel failed to open regkey for tunnels: 0x%x`
- `0x18003a431`: `onecoreuap\net\netio\iphlpsvc\service\direct.c`
- `0x18003a3a4`: `Direct Tunnel failed to read tunnel GUID subkey: 0x%x`

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
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  LPWSTR lpClass; // [rsp+28h] [rbp-D8h]
  LPDWORD lpcchClass; // [rsp+30h] [rbp-D0h]
  __int64 v16; // [rsp+40h] [rbp-C0h]
  __int64 v17; // [rsp+50h] [rbp-B0h]
  DWORD cchName; // [rsp+60h] [rbp-A0h] BYREF
  NET_LUID InterfaceLuid; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  int InBuffer; // [rsp+80h] [rbp-80h] BYREF
  GUID InterfaceGuid; // [rsp+84h] [rbp-7Ch] BYREF
  int v23; // [rsp+94h] [rbp-6Ch]
  _BYTE v24[32]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v25[40]; // [rsp+B8h] [rbp-48h] BYREF
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
            LODWORD(v17) = 0;
            LODWORD(v16) = 0;
            LODWORD(lpcchClass) = 32;
            LODWORD(phkResult) = 8;
            AllParameters = NsiGetAllParameters(0, &NPI_MS_FL6T_MODULEID, 4, &InterfaceLuid);
            if ( AllParameters )
            {
              EventWriteError0(
                0x800000,
                L"Direct Tunnel failed to get tunnel remote DL address 0x%x, interface %ws",
                AllParameters,
                Name,
                phkResult,
                v25,
                lpcchClass,
                0,
                v16,
                0,
                v17);
            }
            else
            {
              LODWORD(v17) = 0;
              LODWORD(v16) = 0;
              LODWORD(lpcchClass) = 32;
              LODWORD(phkResult) = 8;
              v8 = NsiGetAllParameters(0, &NPI_MS_FL6T_MODULEID, 2, &InterfaceLuid);
              if ( v8 )
              {
                EventWriteError0(
                  0x800000,
                  L"Direct Tunnel failed to get tunnel local DL address 0x%x, interface: %ws",
                  v8,
                  Name,
                  phkResult,
                  v24,
                  lpcchClass,
                  0,
                  v16,
                  0,
                  v17);
              }
              else
              {
                v9 = MALLOC(0x20u);
                if ( v9 )
                {
                  InBuffer = 2;
                  v23 = 4;
                  started = StartTunnelInterfaceEx((char *)&InBuffer);
                  if ( started )
                  {
                    EventWriteError0(
                      0x800000,
                      L"Direct Tunnel failed to start tunnel 0x%x, interface %ws",
                      started,
                      Name,
                      phkResult,
                      v24,
                      lpcchClass,
                      0,
                      v16,
                      0,
                      v17);
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
0x18003a080  push    rbp
0x18003a082  push    rbx
0x18003a083  push    rsi
0x18003a084  push    rdi
0x18003a085  push    r13
0x18003a087  push    r14
0x18003a089  push    r15
0x18003a08b  lea     rbp, [rsp-40h]
0x18003a090  sub     rsp, 140h
0x18003a097  mov     rax, cs:__security_cookie
0x18003a09e  xor     rax, rsp
0x18003a0a1  mov     [rbp+70h+var_40], rax
0x18003a0a5  xor     edx, edx; Val
0x18003a0a7  lea     rcx, [rbp+70h+Name]; void *
0x18003a0ab  lea     r8d, [rdx+4Eh]; Size
0x18003a0af  call    memset_0
0x18003a0b4  xor     esi, esi
0x18003a0b6  mov     [rsp+170h+cchName], 27h ; '''
0x18003a0be  xor     edx, edx; Val
0x18003a0c0  mov     [rsp+170h+hKey], rsi
0x18003a0c5  lea     rcx, [rbp+70h+InBuffer]; void *
0x18003a0c9  mov     qword ptr [rsp+170h+InterfaceLuid], rsi
0x18003a0ce  lea     r8d, [rsi+58h]; Size
0x18003a0d2  call    memset_0
0x18003a0d7  cmp     cs:IpHlpSvcEtwEnabled, sil
0x18003a0de  jz      short loc_18003A103
0x18003a0e0  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, sil
0x18003a0e7  jge     short loc_18003A103
0x18003a0e9  lea     r8, aEnteredInitial_0; "Entered: InitializeDirectTunnels"
0x18003a0f0  lea     rdx, EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE
0x18003a0f7  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18003a0fe  call    McTemplateU0z_EventWriteTransfer
0x18003a103  mov     r9, cs:g_DirectTunnelLock
0x18003a10a  lea     r13, aInitializedire; "InitializeDirectTunnels"
0x18003a111  mov     rdx, r13
0x18003a114  lea     rcx, aOnecoreuapNetN_30; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18003a11b  mov     r8d, 2Eh ; '.'
0x18003a121  call    GetAndTraceLock
0x18003a126  mov     r14d, 800000h
0x18003a12c  test    eax, eax
0x18003a12e  jz      loc_18003A3D8
0x18003a134  or      cs:dword_1800CBAA0, 1
0x18003a13b  lea     r15, qword_1800CBAA8
0x18003a142  lea     rax, [rsp+170h+hKey]
0x18003a147  mov     cs:qword_1800CBAB0, r15
0x18003a14e  mov     r9d, 20019h; samDesired
0x18003a154  mov     cs:qword_1800CBAA8, r15
0x18003a15b  xor     r8d, r8d; ulOptions
0x18003a15e  mov     [rsp+170h+phkResult], rax; phkResult
0x18003a163  lea     rdx, aSystemCurrentc_16; "System\\CurrentControlSet\\Services\\IP"...
0x18003a16a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003a171  call    cs:__imp_RegOpenKeyExW
0x18003a178  nop     dword ptr [rax+rax+00h]
0x18003a17d  test    eax, eax
0x18003a17f  jz      short loc_18003A198
0x18003a181  mov     r8d, eax
0x18003a184  lea     rdx, aDirectTunnelFa_8; "Direct Tunnel failed to open regkey for"...
0x18003a18b  mov     ecx, r14d
0x18003a18e  call    EventWriteError0
0x18003a193  jmp     loc_18003A3D8
0x18003a198  mov     edi, esi
0x18003a19a  mov     rcx, [rsp+170h+hKey]; hKey
0x18003a19f  lea     r9, [rsp+170h+cchName]; lpcchName
0x18003a1a4  mov     [rsp+170h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x18003a1a9  lea     r8, [rbp+70h+Name]; lpName
0x18003a1ad  mov     [rsp+170h+lpcchClass], rsi; lpcchClass
0x18003a1b2  mov     edx, edi; dwIndex
0x18003a1b4  mov     [rsp+170h+lpClass], rsi; lpClass
0x18003a1b9  mov     [rsp+170h+phkResult], rsi; lpReserved
0x18003a1be  call    cs:__imp_RegEnumKeyExW
0x18003a1c5  nop     dword ptr [rax+rax+00h]
0x18003a1ca  cmp     eax, 103h
0x18003a1cf  jz      loc_18003A3B5
0x18003a1d5  test    eax, eax
0x18003a1d7  jnz     loc_18003A3A1
0x18003a1dd  xor     edx, edx; Val
0x18003a1df  lea     r8d, [rax+58h]; Size
0x18003a1e3  lea     rcx, [rbp+70h+InBuffer]; void *
0x18003a1e7  call    memset_0
0x18003a1ec  lea     rdx, [rbp+70h+InterfaceGuid]
0x18003a1f0  mov     [rsp+170h+cchName], 27h ; '''
0x18003a1f8  lea     rcx, [rbp+70h+Name]
0x18003a1fc  call    cs:__imp_ConvertStringToGuidW
0x18003a203  nop     dword ptr [rax+rax+00h]
0x18003a208  test    eax, eax
0x18003a20a  jz      short loc_18003A227
0x18003a20c  lea     rdx, aDirectTunnelFa_5; "Direct Tunnel failed to convert \"%ws\""...
0x18003a213  lea     r8, [rbp+70h+Name]
0x18003a217  mov     r9d, eax
0x18003a21a  mov     ecx, r14d
0x18003a21d  call    EventWriteError0
0x18003a222  jmp     loc_18003A393
0x18003a227  lea     rdx, [rsp+170h+InterfaceLuid]; InterfaceLuid
0x18003a22c  lea     rcx, [rbp+70h+InterfaceGuid]; InterfaceGuid
0x18003a230  call    cs:__imp_ConvertInterfaceGuidToLuid
0x18003a237  nop     dword ptr [rax+rax+00h]
0x18003a23c  test    eax, eax
0x18003a23e  jz      short loc_18003A249
0x18003a240  lea     rdx, aDirectTunnelFa_13; "Direct Tunnel failed to get tunnel LUID"...
0x18003a247  jmp     short loc_18003A213
0x18003a249  mov     [rsp+170h+var_120], esi
0x18003a24d  lea     rax, [rbp+70h+var_B8]
0x18003a251  mov     [rsp+170h+var_128], rsi
0x18003a256  lea     r9, [rsp+170h+InterfaceLuid]
0x18003a25b  mov     dword ptr [rsp+170h+var_130], esi
0x18003a25f  lea     rdx, NPI_MS_FL6T_MODULEID
0x18003a266  mov     [rsp+170h+lpftLastWriteTime], rsi
0x18003a26b  mov     r8d, 4
0x18003a271  mov     dword ptr [rsp+170h+lpcchClass], 20h ; ' '
0x18003a279  xor     ecx, ecx
0x18003a27b  mov     [rsp+170h+lpClass], rax
0x18003a280  mov     dword ptr [rsp+170h+phkResult], 8
0x18003a288  call    cs:__imp_NsiGetAllParameters
0x18003a28f  nop     dword ptr [rax+rax+00h]
0x18003a294  test    eax, eax
0x18003a296  jz      short loc_18003A2B3
0x18003a298  lea     rdx, aDirectTunnelFa_9; "Direct Tunnel failed to get tunnel remo"...
0x18003a29f  mov     r8d, eax
0x18003a2a2  lea     r9, [rbp+70h+Name]
0x18003a2a6  mov     ecx, r14d
0x18003a2a9  call    EventWriteError0
0x18003a2ae  jmp     loc_18003A393
0x18003a2b3  mov     [rsp+170h+var_120], esi
0x18003a2b7  lea     rax, [rbp+70h+var_D8]
0x18003a2bb  mov     [rsp+170h+var_128], rsi
0x18003a2c0  lea     r9, [rsp+170h+InterfaceLuid]
0x18003a2c5  mov     dword ptr [rsp+170h+var_130], esi
0x18003a2c9  lea     rdx, NPI_MS_FL6T_MODULEID
0x18003a2d0  mov     [rsp+170h+lpftLastWriteTime], rsi
0x18003a2d5  mov     r8d, 2
0x18003a2db  mov     dword ptr [rsp+170h+lpcchClass], 20h ; ' '
0x18003a2e3  xor     ecx, ecx
0x18003a2e5  mov     [rsp+170h+lpClass], rax
0x18003a2ea  mov     dword ptr [rsp+170h+phkResult], 8
0x18003a2f2  call    cs:__imp_NsiGetAllParameters
0x18003a2f9  nop     dword ptr [rax+rax+00h]
0x18003a2fe  test    eax, eax
0x18003a300  jz      short loc_18003A30B
0x18003a302  lea     rdx, aDirectTunnelFa_12; "Direct Tunnel failed to get tunnel loca"...
0x18003a309  jmp     short loc_18003A29F
0x18003a30b  mov     ecx, 20h ; ' '; dwBytes
0x18003a310  call    MALLOC
0x18003a315  mov     rbx, rax
0x18003a318  test    rax, rax
0x18003a31b  jnz     short loc_18003A332
0x18003a31d  lea     r8, [rbp+70h+Name]
0x18003a321  mov     ecx, r14d
0x18003a324  lea     rdx, aDirectTunnelFa_3; "Direct Tunnel failed to allocate memory"...
0x18003a32b  call    EventWriteError0
0x18003a330  jmp     short loc_18003A393
0x18003a332  lea     rcx, [rbp+70h+InBuffer]; lpInBuffer
0x18003a336  mov     [rbp+70h+InBuffer], 2
0x18003a33d  mov     [rbp+70h+var_DC], 4
0x18003a344  call    StartTunnelInterfaceEx
0x18003a349  test    eax, eax
0x18003a34b  jz      short loc_18003A36D
0x18003a34d  lea     r9, [rbp+70h+Name]
0x18003a351  mov     r8d, eax
0x18003a354  lea     rdx, aDirectTunnelFa_6; "Direct Tunnel failed to start tunnel 0x"...
0x18003a35b  mov     ecx, r14d
0x18003a35e  call    EventWriteError0
0x18003a363  mov     rcx, rbx
0x18003a366  call    FREE
0x18003a36b  jmp     short loc_18003A393
0x18003a36d  movups  xmm0, xmmword ptr [rbp+70h+InterfaceGuid.Data1]
0x18003a371  movdqu  xmmword ptr [rbx+10h], xmm0
0x18003a376  mov     rax, cs:qword_1800CBAB0
0x18003a37d  cmp     [rax], r15
0x18003a380  jnz     short loc_18003A39A
0x18003a382  mov     [rbx], r15
0x18003a385  mov     [rbx+8], rax
0x18003a389  mov     [rax], rbx
0x18003a38c  mov     cs:qword_1800CBAB0, rbx
0x18003a393  inc     edi
0x18003a395  jmp     loc_18003A19A
0x18003a39a  mov     ecx, 3
0x18003a39f  int     29h; Win8: RtlFailFast(ecx)
0x18003a3a1  mov     r8d, eax
0x18003a3a4  lea     rdx, aDirectTunnelFa_0; "Direct Tunnel failed to read tunnel GUI"...
0x18003a3ab  mov     ecx, r14d
0x18003a3ae  call    EventWriteError0
0x18003a3b3  jmp     short loc_18003A3C7
0x18003a3b5  mov     r8d, edi
0x18003a3b8  lea     rdx, aDirectTunnelSu; "Direct Tunnel successfully finished sta"...
0x18003a3bf  mov     ecx, r14d
0x18003a3c2  call    EventWrite0
0x18003a3c7  mov     rcx, [rsp+170h+hKey]; hKey
0x18003a3cc  call    cs:__imp_RegCloseKey
0x18003a3d3  nop     dword ptr [rax+rax+00h]
0x18003a3d8  mov     rbx, cs:g_DirectTunnelLock
0x18003a3df  mov     rcx, rbx; hMutex
0x18003a3e2  call    cs:__imp_ReleaseMutex
0x18003a3e9  nop     dword ptr [rax+rax+00h]
0x18003a3ee  mov     dword ptr [rsp+170h+lpcchClass], eax
0x18003a3f2  lea     r9, aOnecoreuapNetN_30; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18003a3f9  mov     dword ptr [rsp+170h+lpClass], 0C8h
0x18003a401  mov     r8, rbx
0x18003a404  lea     rdx, aLockPReleasedA; "Lock (%p) released at %S : %S : %u. Ret"...
0x18003a40b  mov     [rsp+170h+phkResult], r13
0x18003a410  mov     ecx, r14d
0x18003a413  call    EventWrite0
0x18003a418  mov     rcx, cs:g_DirectTunnelStartCompleteEvent; hEvent
0x18003a41f  call    cs:__imp_SetEvent
0x18003a426  nop     dword ptr [rax+rax+00h]
0x18003a42b  mov     r8d, 0CAh
0x18003a431  lea     rdx, aOnecoreuapNetN_6; "onecoreuap\\net\\netio\\iphlpsvc\\servi"...
0x18003a438  mov     rcx, r13
0x18003a43b  call    DereferenceServiceEx
0x18003a440  cmp     cs:IpHlpSvcEtwEnabled, sil
0x18003a447  jz      short loc_18003A46C
0x18003a449  cmp     byte ptr cs:Microsoft_Windows_Iphlpsvc_TraceEnableBits+2, sil
0x18003a450  jge     short loc_18003A46C
0x18003a452  lea     r8, aLeavingInitial_0; "Leaving: InitializeDirectTunnels"
0x18003a459  lea     rdx, EVENT_IPHLPSVC_ETW_FUNCTION_ENTRY_EXIT_MESSAGE
0x18003a460  lea     rcx, MS_IPHLPSVC_ETW_PROVIDER_ID_Context
0x18003a467  call    McTemplateU0z_EventWriteTransfer
0x18003a46c  mov     rcx, [rbp+70h+var_40]
0x18003a470  xor     rcx, rsp; StackCookie
0x18003a473  call    __security_check_cookie
0x18003a478  add     rsp, 140h
0x18003a47f  pop     r15
0x18003a481  pop     r14
0x18003a483  pop     r13
0x18003a485  pop     rdi
0x18003a486  pop     rsi
0x18003a487  pop     rbx
0x18003a488  pop     rbp
0x18003a489  retn
```
