# SetupMachineChangeNotification(ulong)

- ea: `0x1800246f4`
- end: `0x1800248a4`
- name: `?SetupMachineChangeNotification@@YAKK@Z`
- size: `432`
- prototype: `unsigned int __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180023b60`

## callees

- `0x180004bd0`
- `0x1800075b0`
- `0x1800246f4`
- `0x18005a7ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024743`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180024743`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024893`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180024893`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002475f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002475f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024771`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800247c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024821`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002485c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024771`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800247c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024821`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002485c`
- `CRYPT32!CertControlStore` at `0x180024852`
- `CRYPT32!CertControlStore` at `0x180024852`
- `CRYPT32!CertOpenStore` at `0x180024801`
- `CRYPT32!CertOpenStore` at `0x180024801`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x1800247b7`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x1800247b7`

## pseudocode

```c
__int64 __fastcall SetupMachineChangeNotification(PVOID Context)
{
  unsigned __int64 v1; // rdi
  unsigned int v3; // ebx
  HANDLE EventW; // rax
  DWORD v5; // eax
  struct _EAPTLS_CONTROL_BLOCK *v6; // rcx
  __int64 v7; // rdx
  HCERTSTORE v8; // rax
  DWORD LastError; // eax

  v1 = (unsigned int)Context;
  if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_88923bd842923c348eb3d02ba21152e8_Traceguids);
  if ( g_fChangeNotificationSetup )
    return 0;
  v3 = 0;
  EnterCriticalSection(&g_csProtectCachedCredentials);
  if ( !g_fChangeNotificationSetup )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    g_hStoreChangeNotificationEvt = EventW;
    if ( EventW )
    {
      if ( RegisterWaitForSingleObject(
             &g_hWaitonStoreChangeEvt,
             EventW,
             MachineStoreChangeNotification,
             (PVOID)v1,
             0xFFFFFFFF,
             0x10u) )
      {
        v8 = CertOpenStore((LPCSTR)9, 1u, 0, 0x28000u, "MY");
        g_hLocalMachineStore = v8;
        if ( !v8 )
        {
          v3 = -2143158256;
          if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
          {
            LastError = GetLastError();
            WPP_SF_Dd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              13,
              &WPP_88923bd842923c348eb3d02ba21152e8_Traceguids,
              LastError);
          }
          goto LABEL_20;
        }
        if ( CertControlStore(v8, 0, 2u, &g_hStoreChangeNotificationEvt) )
        {
          g_fChangeNotificationSetup = 1;
          goto LABEL_20;
        }
        v5 = GetLastError();
        v3 = v5;
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
          v7 = 14;
          goto LABEL_18;
        }
      }
      else
      {
        v5 = GetLastError();
        v3 = v5;
        v6 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
        {
          v7 = 12;
          goto LABEL_18;
        }
      }
    }
    else
    {
      v5 = GetLastError();
      v3 = v5;
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _EAPTLS_CONTROL_BLOCK *)&WPP_GLOBAL_Control )
      {
        v7 = 11;
LABEL_18:
        WPP_SF_d(*((_QWORD *)v6 + 2), v7, &WPP_88923bd842923c348eb3d02ba21152e8_Traceguids, v5);
      }
    }
  }
LABEL_20:
  LeaveCriticalSection(&g_csProtectCachedCredentials);
  return v3;
}

```

## disassembly

```asm
0x1800246f4  push    rbx
0x1800246f6  push    rbp
0x1800246f7  push    rsi
0x1800246f8  push    rdi
0x1800246f9  sub     rsp, 38h
0x1800246fd  mov     edi, ecx
0x1800246ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180024706  lea     rsi, WPP_GLOBAL_Control
0x18002470d  lea     rbp, WPP_88923bd842923c348eb3d02ba21152e8_Traceguids
0x180024714  cmp     rcx, rsi
0x180024717  jz      short loc_18002472A
0x180024719  mov     rcx, [rcx+10h]
0x18002471d  mov     edx, 0Ah
0x180024722  mov     r8, rbp
0x180024725  call    WPP_SF_
0x18002472a  cmp     cs:?g_fChangeNotificationSetup@@3HA, 0; int g_fChangeNotificationSetup
0x180024731  jz      short loc_18002473A
0x180024733  xor     eax, eax
0x180024735  jmp     loc_18002489B
0x18002473a  lea     rcx, ?g_csProtectCachedCredentials@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180024741  xor     ebx, ebx
0x180024743  call    cs:__imp_EnterCriticalSection
0x180024749  cmp     cs:?g_fChangeNotificationSetup@@3HA, ebx; int g_fChangeNotificationSetup
0x18002474f  jnz     loc_18002488C
0x180024755  xor     r9d, r9d; lpName
0x180024758  xor     r8d, r8d; bInitialState
0x18002475b  xor     edx, edx; bManualReset
0x18002475d  xor     ecx, ecx; lpEventAttributes
0x18002475f  call    cs:__imp_CreateEventW
0x180024765  mov     cs:?g_hStoreChangeNotificationEvt@@3PEAXEA, rax; void * g_hStoreChangeNotificationEvt
0x18002476c  test    rax, rax
0x18002476f  jnz     short loc_180024793
0x180024771  call    cs:__imp_GetLastError
0x180024777  mov     ebx, eax
0x180024779  mov     rcx, cs:WPP_GLOBAL_Control
0x180024780  cmp     rcx, rsi
0x180024783  jz      loc_18002488C
0x180024789  mov     edx, 0Bh
0x18002478e  jmp     loc_180024875
0x180024793  mov     r9, rdi; Context
0x180024796  mov     [rsp+58h+dwFlags], 10h; dwFlags
0x18002479e  lea     r8, ?MachineStoreChangeNotification@@YAXPEAXE@Z; Callback
0x1800247a5  mov     [rsp+58h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x1800247ad  mov     rdx, rax; hObject
0x1800247b0  lea     rcx, ?g_hWaitonStoreChangeEvt@@3PEAXEA; phNewWaitObject
0x1800247b7  call    cs:__imp_RegisterWaitForSingleObject
0x1800247bd  test    eax, eax
0x1800247bf  jnz     short loc_1800247E3
0x1800247c1  call    cs:__imp_GetLastError
0x1800247c7  mov     ebx, eax
0x1800247c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800247d0  cmp     rcx, rsi
0x1800247d3  jz      loc_18002488C
0x1800247d9  mov     edx, 0Ch
0x1800247de  jmp     loc_180024875
0x1800247e3  xor     r8d, r8d; hCryptProv
0x1800247e6  lea     rax, aMy; "MY"
0x1800247ed  mov     r9d, 28000h; dwFlags
0x1800247f3  mov     qword ptr [rsp+58h+dwMilliseconds], rax; pvPara
0x1800247f8  lea     edi, [r8+1]
0x1800247fc  mov     edx, edi; dwEncodingType
0x1800247fe  lea     ecx, [rdi+8]; lpszStoreProvider
0x180024801  call    cs:__imp_CertOpenStore
0x180024807  mov     cs:?g_hLocalMachineStore@@3PEAXEA, rax; void * g_hLocalMachineStore
0x18002480e  test    rax, rax
0x180024811  jnz     short loc_180024842
0x180024813  mov     ebx, 80420010h
0x180024818  cmp     cs:WPP_GLOBAL_Control, rsi
0x18002481f  jz      short loc_18002488C
0x180024821  call    cs:__imp_GetLastError
0x180024827  mov     rcx, cs:WPP_GLOBAL_Control
0x18002482e  lea     edx, [rdi+0Ch]
0x180024831  mov     r9d, eax
0x180024834  mov     r8, rbp
0x180024837  mov     rcx, [rcx+10h]
0x18002483b  call    WPP_SF_Dd
0x180024840  jmp     short loc_18002488C
0x180024842  xor     edx, edx; dwFlags
0x180024844  lea     r9, ?g_hStoreChangeNotificationEvt@@3PEAXEA; pvCtrlPara
0x18002484b  mov     rcx, rax; hCertStore
0x18002484e  lea     r8d, [rdx+2]; dwCtrlType
0x180024852  call    cs:__imp_CertControlStore
0x180024858  test    eax, eax
0x18002485a  jnz     short loc_180024886
0x18002485c  call    cs:__imp_GetLastError
0x180024862  mov     ebx, eax
0x180024864  mov     rcx, cs:WPP_GLOBAL_Control
0x18002486b  cmp     rcx, rsi
0x18002486e  jz      short loc_18002488C
0x180024870  mov     edx, 0Eh
0x180024875  mov     rcx, [rcx+10h]
0x180024879  mov     r9d, eax
0x18002487c  mov     r8, rbp
0x18002487f  call    WPP_SF_d
0x180024884  jmp     short loc_18002488C
0x180024886  mov     cs:?g_fChangeNotificationSetup@@3HA, edi; int g_fChangeNotificationSetup
0x18002488c  lea     rcx, ?g_csProtectCachedCredentials@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180024893  call    cs:__imp_LeaveCriticalSection
0x180024899  mov     eax, ebx
0x18002489b  add     rsp, 38h
0x18002489f  pop     rdi
0x1800248a0  pop     rsi
0x1800248a1  pop     rbp
0x1800248a2  pop     rbx
0x1800248a3  retn
```
