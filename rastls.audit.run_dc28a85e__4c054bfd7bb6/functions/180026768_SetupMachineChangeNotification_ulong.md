# SetupMachineChangeNotification(ulong)

- ea: `0x180026768`
- end: `0x180026955`
- name: `?SetupMachineChangeNotification@@YAKK@Z`
- size: `493`
- prototype: `unsigned int __fastcall(PVOID Context)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x1800239a0`

## callees

- `0x180005010`
- `0x180007d00`
- `0x180026768`
- `0x18005db88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800267b7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800267b7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002693d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002693d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800267d9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800267d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800267f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002684d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800268b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026900`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800267f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002684d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800268b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026900`
- `CRYPT32!CertControlStore` at `0x1800268f0`
- `CRYPT32!CertControlStore` at `0x1800268f0`
- `CRYPT32!CertOpenStore` at `0x180026893`
- `CRYPT32!CertOpenStore` at `0x180026893`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18002683d`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x18002683d`

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
0x180026768  push    rbx
0x18002676a  push    rbp
0x18002676b  push    rsi
0x18002676c  push    rdi
0x18002676d  sub     rsp, 38h
0x180026771  mov     edi, ecx
0x180026773  mov     rcx, cs:WPP_GLOBAL_Control
0x18002677a  lea     rsi, WPP_GLOBAL_Control
0x180026781  lea     rbp, WPP_88923bd842923c348eb3d02ba21152e8_Traceguids
0x180026788  cmp     rcx, rsi
0x18002678b  jz      short loc_18002679E
0x18002678d  mov     rcx, [rcx+10h]
0x180026791  mov     edx, 0Ah
0x180026796  mov     r8, rbp
0x180026799  call    WPP_SF_
0x18002679e  cmp     cs:?g_fChangeNotificationSetup@@3HA, 0; int g_fChangeNotificationSetup
0x1800267a5  jz      short loc_1800267AE
0x1800267a7  xor     eax, eax
0x1800267a9  jmp     loc_18002694B
0x1800267ae  lea     rcx, ?g_csProtectCachedCredentials@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800267b5  xor     ebx, ebx
0x1800267b7  call    cs:__imp_EnterCriticalSection
0x1800267be  nop     dword ptr [rax+rax+00h]
0x1800267c3  cmp     cs:?g_fChangeNotificationSetup@@3HA, ebx; int g_fChangeNotificationSetup
0x1800267c9  jnz     loc_180026936
0x1800267cf  xor     r9d, r9d; lpName
0x1800267d2  xor     r8d, r8d; bInitialState
0x1800267d5  xor     edx, edx; bManualReset
0x1800267d7  xor     ecx, ecx; lpEventAttributes
0x1800267d9  call    cs:__imp_CreateEventW
0x1800267e0  nop     dword ptr [rax+rax+00h]
0x1800267e5  mov     cs:?g_hStoreChangeNotificationEvt@@3PEAXEA, rax; void * g_hStoreChangeNotificationEvt
0x1800267ec  test    rax, rax
0x1800267ef  jnz     short loc_180026819
0x1800267f1  call    cs:__imp_GetLastError
0x1800267f8  nop     dword ptr [rax+rax+00h]
0x1800267fd  mov     ebx, eax
0x1800267ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180026806  cmp     rcx, rsi
0x180026809  jz      loc_180026936
0x18002680f  mov     edx, 0Bh
0x180026814  jmp     loc_18002691F
0x180026819  mov     r9, rdi; Context
0x18002681c  mov     [rsp+58h+dwFlags], 10h; dwFlags
0x180026824  lea     r8, ?MachineStoreChangeNotification@@YAXPEAXE@Z; Callback
0x18002682b  mov     [rsp+58h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x180026833  mov     rdx, rax; hObject
0x180026836  lea     rcx, ?g_hWaitonStoreChangeEvt@@3PEAXEA; phNewWaitObject
0x18002683d  call    cs:__imp_RegisterWaitForSingleObject
0x180026844  nop     dword ptr [rax+rax+00h]
0x180026849  test    eax, eax
0x18002684b  jnz     short loc_180026875
0x18002684d  call    cs:__imp_GetLastError
0x180026854  nop     dword ptr [rax+rax+00h]
0x180026859  mov     ebx, eax
0x18002685b  mov     rcx, cs:WPP_GLOBAL_Control
0x180026862  cmp     rcx, rsi
0x180026865  jz      loc_180026936
0x18002686b  mov     edx, 0Ch
0x180026870  jmp     loc_18002691F
0x180026875  xor     r8d, r8d; hCryptProv
0x180026878  lea     rax, aMy; "MY"
0x18002687f  mov     r9d, 28000h; dwFlags
0x180026885  mov     qword ptr [rsp+58h+dwMilliseconds], rax; pvPara
0x18002688a  lea     edi, [r8+1]
0x18002688e  mov     edx, edi; dwEncodingType
0x180026890  lea     ecx, [rdi+8]; lpszStoreProvider
0x180026893  call    cs:__imp_CertOpenStore
0x18002689a  nop     dword ptr [rax+rax+00h]
0x18002689f  mov     cs:?g_hLocalMachineStore@@3PEAXEA, rax; void * g_hLocalMachineStore
0x1800268a6  test    rax, rax
0x1800268a9  jnz     short loc_1800268E0
0x1800268ab  mov     ebx, 80420010h
0x1800268b0  cmp     cs:WPP_GLOBAL_Control, rsi
0x1800268b7  jz      short loc_180026936
0x1800268b9  call    cs:__imp_GetLastError
0x1800268c0  nop     dword ptr [rax+rax+00h]
0x1800268c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800268cc  lea     edx, [rdi+0Ch]
0x1800268cf  mov     r9d, eax
0x1800268d2  mov     r8, rbp
0x1800268d5  mov     rcx, [rcx+10h]
0x1800268d9  call    WPP_SF_Dd
0x1800268de  jmp     short loc_180026936
0x1800268e0  xor     edx, edx; dwFlags
0x1800268e2  lea     r9, ?g_hStoreChangeNotificationEvt@@3PEAXEA; pvCtrlPara
0x1800268e9  mov     rcx, rax; hCertStore
0x1800268ec  lea     r8d, [rdx+2]; dwCtrlType
0x1800268f0  call    cs:__imp_CertControlStore
0x1800268f7  nop     dword ptr [rax+rax+00h]
0x1800268fc  test    eax, eax
0x1800268fe  jnz     short loc_180026930
0x180026900  call    cs:__imp_GetLastError
0x180026907  nop     dword ptr [rax+rax+00h]
0x18002690c  mov     ebx, eax
0x18002690e  mov     rcx, cs:WPP_GLOBAL_Control
0x180026915  cmp     rcx, rsi
0x180026918  jz      short loc_180026936
0x18002691a  mov     edx, 0Eh
0x18002691f  mov     rcx, [rcx+10h]
0x180026923  mov     r9d, eax
0x180026926  mov     r8, rbp
0x180026929  call    WPP_SF_d
0x18002692e  jmp     short loc_180026936
0x180026930  mov     cs:?g_fChangeNotificationSetup@@3HA, edi; int g_fChangeNotificationSetup
0x180026936  lea     rcx, ?g_csProtectCachedCredentials@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18002693d  call    cs:__imp_LeaveCriticalSection
0x180026944  nop     dword ptr [rax+rax+00h]
0x180026949  mov     eax, ebx
0x18002694b  add     rsp, 38h
0x18002694f  pop     rdi
0x180026950  pop     rsi
0x180026951  pop     rbp
0x180026952  pop     rbx
0x180026953  retn
```
