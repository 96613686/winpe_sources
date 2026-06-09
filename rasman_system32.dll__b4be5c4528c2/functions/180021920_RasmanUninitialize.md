# RasmanUninitialize

- ea: `0x180021920`
- end: `0x180021ab4`
- name: `RasmanUninitialize`
- size: `404`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task`

## callees

- `0x18001528c`
- `0x1800153e0`
- `0x180021920`
- `0x180021ae4`
- `0x180021b14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800219cc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800219cc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800219fa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800219fa`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180021a1e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180021a1e`
- `WS2_32!__imp_WSACleanup` at `0x180021a5b`
- `WS2_32!__imp_WSACleanup` at `0x180021a5b`

## pseudocode

```c
__int64 RasmanUninitialize()
{
  PVOID *v0; // rcx
  RPC_BINDING_HANDLE Binding; // [rsp+30h] [rbp+8h] BYREF

  v0 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
    v0 = (PVOID *)WPP_GLOBAL_Control;
  }
  Binding = 0;
  if ( g_fRasmanService )
  {
    if ( hInstRasmans )
    {
      FreeLibrary(hInstRasmans);
      v0 = (PVOID *)WPP_GLOBAL_Control;
    }
    hInstRasmans = 0;
    g_fnServiceRequest = 0;
    g_fnRasmanServiceInitialized = 0;
    goto LABEL_17;
  }
  if ( g_fRasInitialized )
  {
    RasReferenceRasman(0);
    EnterCriticalSection(&g_RasCriticalSection);
    Binding = (RPC_BINDING_HANDLE)g_hBinding;
    if ( g_hBinding )
      RpcDisconnect(&Binding);
    LeaveCriticalSection(&g_RasCriticalSection);
    v0 = (PVOID *)WPP_GLOBAL_Control;
LABEL_17:
    if ( g_fWinsockInitialized )
    {
      WSACleanup();
      v0 = (PVOID *)WPP_GLOBAL_Control;
      g_fWinsockInitialized = 0;
    }
    g_fRasInitialized = 0;
    goto LABEL_20;
  }
  if ( v0 == &WPP_GLOBAL_Control )
    return 0;
  if ( (*((_BYTE *)v0 + 28) & 0x40) != 0 && *((_BYTE *)v0 + 25) >= 5u )
  {
    WPP_SF_(v0[2], 49, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
    v0 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_20:
  if ( v0 != &WPP_GLOBAL_Control && (*((_BYTE *)v0 + 28) & 0x40) != 0 && *((_BYTE *)v0 + 25) >= 6u )
    WPP_SF_d(v0[2], 50, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, 0);
  return 0;
}

```

## disassembly

```asm
0x180021920  push    rsi
0x180021922  sub     rsp, 20h
0x180021926  mov     rcx, cs:WPP_GLOBAL_Control
0x18002192d  lea     rsi, WPP_GLOBAL_Control
0x180021934  cmp     rcx, rsi
0x180021937  jz      short loc_180021961
0x180021939  test    byte ptr [rcx+1Ch], 40h
0x18002193d  jz      short loc_180021961
0x18002193f  cmp     byte ptr [rcx+19h], 6
0x180021943  jb      short loc_180021961
0x180021945  mov     rcx, [rcx+10h]
0x180021949  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180021950  mov     edx, 30h ; '0'
0x180021955  call    WPP_SF_
0x18002195a  mov     rcx, cs:WPP_GLOBAL_Control
0x180021961  cmp     cs:g_fRasmanService, 0
0x180021968  mov     [rsp+28h+Binding], 0
0x180021971  jnz     loc_180021A0F
0x180021977  cmp     cs:g_fRasInitialized, 0
0x18002197e  jnz     short loc_1800219BE
0x180021980  cmp     rcx, rsi
0x180021983  jz      loc_180021AAB
0x180021989  test    byte ptr [rcx+1Ch], 40h
0x18002198d  jz      loc_180021A82
0x180021993  cmp     byte ptr [rcx+19h], 5
0x180021997  jb      loc_180021A82
0x18002199d  mov     rcx, [rcx+10h]
0x1800219a1  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800219a8  mov     edx, 31h ; '1'
0x1800219ad  call    WPP_SF_
0x1800219b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800219b9  jmp     loc_180021A82
0x1800219be  xor     ecx, ecx
0x1800219c0  call    RasReferenceRasman
0x1800219c5  lea     rcx, g_RasCriticalSection; lpCriticalSection
0x1800219cc  call    cs:__imp_EnterCriticalSection
0x1800219d3  nop     dword ptr [rax+rax+00h]
0x1800219d8  mov     rax, cs:g_hBinding
0x1800219df  mov     [rsp+28h+Binding], rax
0x1800219e4  test    rax, rax
0x1800219e7  jz      short loc_1800219F3
0x1800219e9  lea     rcx, [rsp+28h+Binding]; Binding
0x1800219ee  call    RpcDisconnect
0x1800219f3  lea     rcx, g_RasCriticalSection; lpCriticalSection
0x1800219fa  call    cs:__imp_LeaveCriticalSection
0x180021a01  nop     dword ptr [rax+rax+00h]
0x180021a06  mov     rcx, cs:WPP_GLOBAL_Control
0x180021a0d  jmp     short loc_180021A52
0x180021a0f  mov     rax, cs:hInstRasmans
0x180021a16  test    rax, rax
0x180021a19  jz      short loc_180021A31
0x180021a1b  mov     rcx, rax; hLibModule
0x180021a1e  call    cs:__imp_FreeLibrary
0x180021a25  nop     dword ptr [rax+rax+00h]
0x180021a2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180021a31  mov     cs:hInstRasmans, 0
0x180021a3c  mov     cs:g_fnServiceRequest, 0
0x180021a47  mov     cs:g_fnRasmanServiceInitialized, 0
0x180021a52  cmp     cs:g_fWinsockInitialized, 0
0x180021a59  jz      short loc_180021A78
0x180021a5b  call    cs:__imp_WSACleanup
0x180021a62  nop     dword ptr [rax+rax+00h]
0x180021a67  mov     rcx, cs:WPP_GLOBAL_Control
0x180021a6e  mov     cs:g_fWinsockInitialized, 0
0x180021a78  mov     cs:g_fRasInitialized, 0
0x180021a82  cmp     rcx, rsi
0x180021a85  jz      short loc_180021AAB
0x180021a87  test    byte ptr [rcx+1Ch], 40h
0x180021a8b  jz      short loc_180021AAB
0x180021a8d  cmp     byte ptr [rcx+19h], 6
0x180021a91  jb      short loc_180021AAB
0x180021a93  mov     rcx, [rcx+10h]
0x180021a97  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180021a9e  mov     edx, 32h ; '2'
0x180021aa3  xor     r9d, r9d
0x180021aa6  call    WPP_SF_d
0x180021aab  xor     eax, eax
0x180021aad  add     rsp, 20h
0x180021ab1  pop     rsi
0x180021ab2  retn
```
