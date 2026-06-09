# BthServStart(void)

- ea: `0x18000e8f0`
- end: `0x18000eba5`
- name: `?BthServStart@@YAXXZ`
- size: `693`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18000ce48`

## callees

- `0x18000d218`
- `0x18000e8f0`
- `0x180012004`
- `0x1800120b8`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000e97a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000e97a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e9d4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e9d4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000e9a6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000ea12`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000e9a6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000ea12`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e995`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e995`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ea01`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e9b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ea20`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000e9b4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ea20`

## string_xrefs

- `0x18000e96d`: `Microsoft.Bluetooth.Service.dll`

## pseudocode

```c
void BthServStart(void)
{
  char v0; // di
  bool v1; // dl
  HMODULE Library; // rax
  HMODULE v3; // rbp
  HMODULE v4; // rsi
  DWORD LastError; // ebx
  FARPROC ProcAddress; // rax
  HMODULE v7; // rsi
  DWORD v8; // ebx
  _BYTE *v9; // rcx
  bool v10; // dl
  int v11; // edx
  int v12; // r8d
  bool v13; // dl

  v0 = 1;
  v1 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( v1 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v1,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  Library = LoadLibraryExW(L"Microsoft.Bluetooth.Service.dll", 0, 0x800u);
  v3 = hLibModule;
  v4 = Library;
  if ( hLibModule )
  {
    LastError = GetLastError();
    FreeLibrary(v3);
    SetLastError(LastError);
  }
  hLibModule = v4;
  if ( v4 )
  {
    ProcAddress = GetProcAddress(v4, (LPCSTR)0x64);
    qword_180047108 = (__int64)ProcAddress;
    if ( ProcAddress )
    {
      ((void (__fastcall *)(_QWORD))ProcAddress)(0);
    }
    else
    {
      v7 = hLibModule;
      if ( hLibModule )
      {
        v8 = GetLastError();
        FreeLibrary(v7);
        SetLastError(v8);
      }
      hLibModule = 0;
    }
  }
  BthServLoadBackgroundBrokerModule();
  v9 = WPP_GLOBAL_Control;
  v10 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( v10 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v10,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
    v9 = WPP_GLOBAL_Control;
  }
  if ( qword_180046FC0 )
  {
    if ( !(unsigned int)qword_180046FC0(&GUID_BLUETOOTH_EVENT_BROKER_ID, &dword_180046FD0, 7) )
    {
LABEL_32:
      v9 = WPP_GLOBAL_Control;
      goto LABEL_33;
    }
    v9 = WPP_GLOBAL_Control;
    LOBYTE(v11) = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u;
    if ( (_BYTE)v11 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v12) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, v12, *((_QWORD *)WPP_GLOBAL_Control + 5));
      goto LABEL_32;
    }
  }
LABEL_33:
  v13 = v9 != (_BYTE *)&WPP_GLOBAL_Control && v9[25] >= 5u;
  if ( v13 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)v9 + 2),
      v13,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)v9 + 5));
    v9 = WPP_GLOBAL_Control;
  }
  if ( v9 == (_BYTE *)&WPP_GLOBAL_Control || v9[25] < 5u )
    v0 = 0;
  if ( v0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)v9 + 2),
      v0,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)v9 + 5));
}

```

## disassembly

```asm
0x18000e8f0  mov     rax, rsp
0x18000e8f3  mov     [rax+8], rbx
0x18000e8f7  mov     [rax+10h], rbp
0x18000e8fb  mov     [rax+18h], rsi
0x18000e8ff  mov     [rax+20h], rdi
0x18000e903  push    r12
0x18000e905  push    r13
0x18000e907  push    r14
0x18000e909  sub     rsp, 50h
0x18000e90d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000e914  lea     r14, WPP_GLOBAL_Control
0x18000e91b  mov     dil, 1
0x18000e91e  cmp     rcx, r14
0x18000e921  jz      short loc_18000E92E
0x18000e923  cmp     byte ptr [rcx+19h], 5
0x18000e927  jb      short loc_18000E92E
0x18000e929  mov     dl, dil
0x18000e92c  jmp     short loc_18000E930
0x18000e92e  xor     dl, dl
0x18000e930  lea     r12, WPP_RECORDER_INITIALIZED
0x18000e937  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18000e93e  lea     r13, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x18000e945  setnz   r8b
0x18000e949  test    dl, dl
0x18000e94b  jnz     short loc_18000E952
0x18000e94d  test    r8b, r8b
0x18000e950  jz      short loc_18000E96B
0x18000e952  mov     r9, [rcx+28h]
0x18000e956  mov     rcx, [rcx+10h]
0x18000e95a  mov     [rsp+68h+var_30], r13
0x18000e95f  mov     [rsp+68h+var_38], 31h ; '1'
0x18000e966  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000e96b  xor     edx, edx; hFile
0x18000e96d  lea     rcx, aMicrosoftBluet; "Microsoft.Bluetooth.Service.dll"
0x18000e974  mov     r8d, 800h; dwFlags
0x18000e97a  call    cs:__imp_LoadLibraryExW
0x18000e981  nop     dword ptr [rax+rax+00h]
0x18000e986  mov     rbp, cs:hLibModule
0x18000e98d  mov     rsi, rax
0x18000e990  test    rbp, rbp
0x18000e993  jz      short loc_18000E9C0
0x18000e995  call    cs:__imp_GetLastError
0x18000e99c  nop     dword ptr [rax+rax+00h]
0x18000e9a1  mov     rcx, rbp; hLibModule
0x18000e9a4  mov     ebx, eax
0x18000e9a6  call    cs:__imp_FreeLibrary
0x18000e9ad  nop     dword ptr [rax+rax+00h]
0x18000e9b2  mov     ecx, ebx; dwErrCode
0x18000e9b4  call    cs:__imp_SetLastError
0x18000e9bb  nop     dword ptr [rax+rax+00h]
0x18000e9c0  mov     cs:hLibModule, rsi
0x18000e9c7  test    rsi, rsi
0x18000e9ca  jz      short loc_18000EA34
0x18000e9cc  mov     edx, 64h ; 'd'; lpProcName
0x18000e9d1  mov     rcx, rsi; hModule
0x18000e9d4  call    cs:__imp_GetProcAddress
0x18000e9db  nop     dword ptr [rax+rax+00h]
0x18000e9e0  mov     cs:qword_180047108, rax
0x18000e9e7  test    rax, rax
0x18000e9ea  jz      short loc_18000E9F5
0x18000e9ec  xor     ecx, ecx
0x18000e9ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9f3  jmp     short loc_18000EA34
0x18000e9f5  mov     rsi, cs:hLibModule
0x18000e9fc  test    rsi, rsi
0x18000e9ff  jz      short loc_18000EA2C
0x18000ea01  call    cs:__imp_GetLastError
0x18000ea08  nop     dword ptr [rax+rax+00h]
0x18000ea0d  mov     rcx, rsi; hLibModule
0x18000ea10  mov     ebx, eax
0x18000ea12  call    cs:__imp_FreeLibrary
0x18000ea19  nop     dword ptr [rax+rax+00h]
0x18000ea1e  mov     ecx, ebx; dwErrCode
0x18000ea20  call    cs:__imp_SetLastError
0x18000ea27  nop     dword ptr [rax+rax+00h]
0x18000ea2c  and     cs:hLibModule, 0
0x18000ea34  call    ?BthServLoadBackgroundBrokerModule@@YAXXZ; BthServLoadBackgroundBrokerModule(void)
0x18000ea39  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea40  cmp     rcx, r14
0x18000ea43  jz      short loc_18000EA50
0x18000ea45  cmp     byte ptr [rcx+19h], 5
0x18000ea49  jb      short loc_18000EA50
0x18000ea4b  mov     dl, dil
0x18000ea4e  jmp     short loc_18000EA52
0x18000ea50  xor     dl, dl
0x18000ea52  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18000ea59  setnz   r8b
0x18000ea5d  test    dl, dl
0x18000ea5f  jnz     short loc_18000EA66
0x18000ea61  test    r8b, r8b
0x18000ea64  jz      short loc_18000EA86
0x18000ea66  mov     r9, [rcx+28h]
0x18000ea6a  mov     rcx, [rcx+10h]
0x18000ea6e  mov     [rsp+68h+var_30], r13
0x18000ea73  mov     [rsp+68h+var_38], 40h ; '@'
0x18000ea7a  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000ea7f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ea86  mov     rax, cs:qword_180046FC0
0x18000ea8d  test    rax, rax
0x18000ea90  jz      short loc_18000EB00
0x18000ea92  mov     r8d, 7
0x18000ea98  lea     rdx, dword_180046FD0
0x18000ea9f  lea     rcx, GUID_BLUETOOTH_EVENT_BROKER_ID
0x18000eaa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eaab  test    eax, eax
0x18000eaad  jz      short loc_18000EAF9
0x18000eaaf  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eab6  cmp     rcx, r14
0x18000eab9  jz      short loc_18000EAC6
0x18000eabb  cmp     byte ptr [rcx+19h], 3
0x18000eabf  jb      short loc_18000EAC6
0x18000eac1  mov     dl, dil
0x18000eac4  jmp     short loc_18000EAC8
0x18000eac6  xor     dl, dl
0x18000eac8  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18000eacf  setnz   r8b
0x18000ead3  test    dl, dl
0x18000ead5  jnz     short loc_18000EADC
0x18000ead7  test    r8b, r8b
0x18000eada  jz      short loc_18000EB00
0x18000eadc  mov     r9, [rcx+28h]
0x18000eae0  mov     rcx, [rcx+10h]
0x18000eae4  mov     [rsp+68h+var_20], eax
0x18000eae8  mov     [rsp+68h+var_30], r13
0x18000eaed  mov     [rsp+68h+var_38], 41h ; 'A'
0x18000eaf4  call    WPP_RECORDER_AND_TRACE_SF_sD
0x18000eaf9  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb00  cmp     rcx, r14
0x18000eb03  jz      short loc_18000EB10
0x18000eb05  cmp     byte ptr [rcx+19h], 5
0x18000eb09  jb      short loc_18000EB10
0x18000eb0b  mov     dl, dil
0x18000eb0e  jmp     short loc_18000EB12
0x18000eb10  xor     dl, dl
0x18000eb12  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18000eb19  setnz   r8b
0x18000eb1d  test    dl, dl
0x18000eb1f  jnz     short loc_18000EB26
0x18000eb21  test    r8b, r8b
0x18000eb24  jz      short loc_18000EB46
0x18000eb26  mov     r9, [rcx+28h]
0x18000eb2a  mov     rcx, [rcx+10h]
0x18000eb2e  mov     [rsp+68h+var_30], r13
0x18000eb33  mov     [rsp+68h+var_38], 42h ; 'B'
0x18000eb3a  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000eb3f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000eb46  cmp     rcx, r14
0x18000eb49  jz      short loc_18000EB51
0x18000eb4b  cmp     byte ptr [rcx+19h], 5
0x18000eb4f  jnb     short loc_18000EB54
0x18000eb51  xor     dil, dil
0x18000eb54  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x18000eb5b  setnz   r8b
0x18000eb5f  test    dil, dil
0x18000eb62  jnz     short loc_18000EB69
0x18000eb64  test    r8b, r8b
0x18000eb67  jz      short loc_18000EB85
0x18000eb69  mov     r9, [rcx+28h]
0x18000eb6d  mov     dl, dil
0x18000eb70  mov     rcx, [rcx+10h]
0x18000eb74  mov     [rsp+68h+var_30], r13
0x18000eb79  mov     [rsp+68h+var_38], 32h ; '2'
0x18000eb80  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000eb85  lea     r11, [rsp+68h+var_18]
0x18000eb8a  mov     rbx, [r11+20h]
0x18000eb8e  mov     rbp, [r11+28h]
0x18000eb92  mov     rsi, [r11+30h]
0x18000eb96  mov     rdi, [r11+38h]
0x18000eb9a  mov     rsp, r11
0x18000eb9d  pop     r14
0x18000eb9f  pop     r13
0x18000eba1  pop     r12
0x18000eba3  retn
```
