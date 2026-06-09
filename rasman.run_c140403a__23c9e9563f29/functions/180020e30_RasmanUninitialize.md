# RasmanUninitialize

- ea: `0x180020e30`
- end: `0x180020fab`
- name: `RasmanUninitialize`
- size: `379`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task`

## callees

- `0x18001491c`
- `0x180014ab0`
- `0x180020e30`
- `0x180020fd8`
- `0x180021000`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020edc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020edc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020f04`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020f04`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180020f22`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180020f22`
- `WS2_32!__imp_WSACleanup` at `0x180020f59`
- `WS2_32!__imp_WSACleanup` at `0x180020f59`

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
0x180020e30  push    rsi
0x180020e32  sub     rsp, 20h
0x180020e36  mov     rcx, cs:WPP_GLOBAL_Control
0x180020e3d  lea     rsi, WPP_GLOBAL_Control
0x180020e44  cmp     rcx, rsi
0x180020e47  jz      short loc_180020E71
0x180020e49  test    byte ptr [rcx+1Ch], 40h
0x180020e4d  jz      short loc_180020E71
0x180020e4f  cmp     byte ptr [rcx+19h], 6
0x180020e53  jb      short loc_180020E71
0x180020e55  mov     rcx, [rcx+10h]
0x180020e59  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180020e60  mov     edx, 30h ; '0'
0x180020e65  call    WPP_SF_
0x180020e6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180020e71  cmp     cs:g_fRasmanService, 0
0x180020e78  mov     [rsp+28h+Binding], 0
0x180020e81  jnz     loc_180020F13
0x180020e87  cmp     cs:g_fRasInitialized, 0
0x180020e8e  jnz     short loc_180020ECE
0x180020e90  cmp     rcx, rsi
0x180020e93  jz      loc_180020FA3
0x180020e99  test    byte ptr [rcx+1Ch], 40h
0x180020e9d  jz      loc_180020F7A
0x180020ea3  cmp     byte ptr [rcx+19h], 5
0x180020ea7  jb      loc_180020F7A
0x180020ead  mov     rcx, [rcx+10h]
0x180020eb1  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180020eb8  mov     edx, 31h ; '1'
0x180020ebd  call    WPP_SF_
0x180020ec2  mov     rcx, cs:WPP_GLOBAL_Control
0x180020ec9  jmp     loc_180020F7A
0x180020ece  xor     ecx, ecx
0x180020ed0  call    RasReferenceRasman
0x180020ed5  lea     rcx, g_RasCriticalSection; lpCriticalSection
0x180020edc  call    cs:__imp_EnterCriticalSection
0x180020ee2  mov     rax, cs:g_hBinding
0x180020ee9  mov     [rsp+28h+Binding], rax
0x180020eee  test    rax, rax
0x180020ef1  jz      short loc_180020EFD
0x180020ef3  lea     rcx, [rsp+28h+Binding]; Binding
0x180020ef8  call    RpcDisconnect
0x180020efd  lea     rcx, g_RasCriticalSection; lpCriticalSection
0x180020f04  call    cs:__imp_LeaveCriticalSection
0x180020f0a  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f11  jmp     short loc_180020F50
0x180020f13  mov     rax, cs:hInstRasmans
0x180020f1a  test    rax, rax
0x180020f1d  jz      short loc_180020F2F
0x180020f1f  mov     rcx, rax; hLibModule
0x180020f22  call    cs:__imp_FreeLibrary
0x180020f28  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f2f  mov     cs:hInstRasmans, 0
0x180020f3a  mov     cs:g_fnServiceRequest, 0
0x180020f45  mov     cs:g_fnRasmanServiceInitialized, 0
0x180020f50  cmp     cs:g_fWinsockInitialized, 0
0x180020f57  jz      short loc_180020F70
0x180020f59  call    cs:__imp_WSACleanup
0x180020f5f  mov     rcx, cs:WPP_GLOBAL_Control
0x180020f66  mov     cs:g_fWinsockInitialized, 0
0x180020f70  mov     cs:g_fRasInitialized, 0
0x180020f7a  cmp     rcx, rsi
0x180020f7d  jz      short loc_180020FA3
0x180020f7f  test    byte ptr [rcx+1Ch], 40h
0x180020f83  jz      short loc_180020FA3
0x180020f85  cmp     byte ptr [rcx+19h], 6
0x180020f89  jb      short loc_180020FA3
0x180020f8b  mov     rcx, [rcx+10h]
0x180020f8f  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180020f96  mov     edx, 32h ; '2'
0x180020f9b  xor     r9d, r9d
0x180020f9e  call    WPP_SF_d
0x180020fa3  xor     eax, eax
0x180020fa5  add     rsp, 20h
0x180020fa9  pop     rsi
0x180020faa  retn
```
