# RasInitializeNoWait

- ea: `0x1800016f0`
- end: `0x180001c2b`
- name: `RasInitializeNoWait`
- size: `1339`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task`

## callers

- `0x18000b230`

## callees

- `0x1800016f0`
- `0x180001c40`
- `0x180021ae4`
- `0x180021b14`
- `0x18002739e`
- `0x1800273d0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800018c1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x1800018c1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800019b3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180001a9b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800019b3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180001a9b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001990`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001a78`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001990`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180001a78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800018dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800019c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001ab0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800018dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800019c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001ab0`
- `WS2_32!__imp_WSAGetLastError` at `0x1800017a8`
- `WS2_32!__imp_WSAGetLastError` at `0x1800017a8`
- `WS2_32!__imp_WSAStartup` at `0x180001790`
- `WS2_32!__imp_WSAStartup` at `0x180001790`

## string_xrefs

- `0x1800018b4`: `rasmans.dll`
- `0x180001986`: `ServiceRequestInProcess`
- `0x180001a71`: `ServiceInitialized`

## pseudocode

```c
__int64 RasInitializeNoWait()
{
  PVOID *v0; // rcx
  unsigned int Error; // eax
  unsigned int v2; // ebx
  PVOID *v3; // rcx
  __int64 v5; // rdx
  HMODULE Library; // rax
  DWORD v7; // eax
  PVOID *v8; // rcx
  __int64 v9; // rdx
  DWORD LastError; // eax
  DWORD v11; // eax
  WSAData WSAData; // [rsp+20h] [rbp-1B8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
  }
  g_fRasmanService = IsRasmanProcess();
  if ( !g_fRasmanService )
  {
    v0 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 63, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
      v0 = (PVOID *)WPP_GLOBAL_Control;
    }
    hInstRasmans = 0;
    g_fnServiceRequest = 0;
    g_fnRasmanServiceInitialized = 0;
    if ( !g_fWinsockInitialized )
    {
      memset_0(&WSAData, 0, sizeof(WSAData));
      if ( WSAStartup(2u, &WSAData) )
      {
        Error = WSAGetLastError();
        v2 = Error;
        if ( Error )
        {
          v3 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
            return v2;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
LABEL_10:
            if ( v3 != &WPP_GLOBAL_Control && (*((_BYTE *)v3 + 28) & 0x40) != 0 && *((_BYTE *)v3 + 25) >= 6u )
              WPP_SF_d(v3[2], 65, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v2);
            return v2;
          }
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, Error);
        }
        v3 = (PVOID *)WPP_GLOBAL_Control;
        goto LABEL_10;
      }
      v0 = (PVOID *)WPP_GLOBAL_Control;
      g_fWinsockInitialized = 1;
    }
    if ( v0 == &WPP_GLOBAL_Control || (*((_BYTE *)v0 + 28) & 0x40) == 0 || *((_BYTE *)v0 + 25) < 6u )
      return 0;
    v5 = 66;
    goto LABEL_21;
  }
  v0 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids);
    v0 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( hInstRasmans )
  {
LABEL_14:
    if ( v0 == &WPP_GLOBAL_Control || (*((_BYTE *)v0 + 28) & 0x40) == 0 || *((_BYTE *)v0 + 25) < 6u )
      return 0;
    v5 = 62;
LABEL_21:
    WPP_SF_d(v0[2], v5, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, 0);
    return 0;
  }
  Library = LoadLibraryExA("rasmans.dll", 0, 0x800u);
  hInstRasmans = Library;
  if ( Library )
  {
    g_fnServiceRequest = (__int64)GetProcAddress(Library, "ServiceRequestInProcess");
    if ( !g_fnServiceRequest )
    {
      FreeLibrary(hInstRasmans);
      hInstRasmans = 0;
      LastError = GetLastError();
      if ( LastError )
      {
        v8 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
          return 711;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          goto LABEL_49;
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, LastError);
      }
      v8 = (PVOID *)WPP_GLOBAL_Control;
LABEL_49:
      if ( v8 == &WPP_GLOBAL_Control )
        return 711;
      if ( (*((_BYTE *)v8 + 28) & 0x40) != 0 && *((_BYTE *)v8 + 25) >= 2u )
      {
        WPP_SF_d(v8[2], 57, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, 711);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v8 == &WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 0x40) == 0 || *((_BYTE *)v8 + 25) < 6u )
        return 711;
      v9 = 58;
      goto LABEL_72;
    }
    g_fnRasmanServiceInitialized = GetProcAddress(hInstRasmans, "ServiceInitialized");
    if ( g_fnRasmanServiceInitialized )
    {
      v0 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_14;
    }
    FreeLibrary(hInstRasmans);
    hInstRasmans = 0;
    v11 = GetLastError();
    if ( v11 )
    {
      v8 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
        return 711;
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        goto LABEL_64;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v11);
    }
    v8 = (PVOID *)WPP_GLOBAL_Control;
LABEL_64:
    if ( v8 == &WPP_GLOBAL_Control )
      return 711;
    if ( (*((_BYTE *)v8 + 28) & 0x40) != 0 && *((_BYTE *)v8 + 25) >= 2u )
    {
      WPP_SF_d(v8[2], 60, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, 711);
      v8 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v8 == &WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 0x40) == 0 || *((_BYTE *)v8 + 25) < 6u )
      return 711;
    v9 = 61;
LABEL_72:
    WPP_SF_d(v8[2], v9, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, 711);
    return 711;
  }
  v7 = GetLastError();
  if ( !v7 )
    goto LABEL_33;
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) == 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
LABEL_34:
      if ( v8 == &WPP_GLOBAL_Control )
        return 711;
      if ( (*((_BYTE *)v8 + 28) & 0x40) != 0 && *((_BYTE *)v8 + 25) >= 2u )
      {
        WPP_SF_d(v8[2], 54, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, 711);
        v8 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v8 == &WPP_GLOBAL_Control || (*((_BYTE *)v8 + 28) & 0x40) == 0 || *((_BYTE *)v8 + 25) < 6u )
        return 711;
      v9 = 55;
      goto LABEL_72;
    }
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, &WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids, v7);
LABEL_33:
    v8 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_34;
  }
  return 711;
}

```

## disassembly

```asm
0x1800016f0  push    rdi
0x1800016f2  sub     rsp, 1D0h
0x1800016f9  mov     rax, cs:__security_cookie
0x180001700  xor     rax, rsp
0x180001703  mov     [rsp+1D8h+var_18], rax
0x18000170b  mov     rcx, cs:WPP_GLOBAL_Control
0x180001712  lea     rdi, WPP_GLOBAL_Control
0x180001719  cmp     rcx, rdi
0x18000171c  jz      short loc_180001728
0x18000171e  test    byte ptr [rcx+1Ch], 40h
0x180001722  jnz     loc_180001859
0x180001728  call    IsRasmanProcess
0x18000172d  mov     cs:g_fRasmanService, eax
0x180001733  test    eax, eax
0x180001735  jnz     loc_1800017DA
0x18000173b  mov     rcx, cs:WPP_GLOBAL_Control
0x180001742  cmp     rcx, rdi
0x180001745  jz      short loc_180001751
0x180001747  test    byte ptr [rcx+1Ch], 40h
0x18000174b  jnz     loc_180001B8E
0x180001751  xor     eax, eax
0x180001753  cmp     cs:g_fWinsockInitialized, eax
0x180001759  mov     cs:hInstRasmans, rax
0x180001760  mov     cs:g_fnServiceRequest, rax
0x180001767  mov     cs:g_fnRasmanServiceInitialized, rax
0x18000176e  jnz     loc_18000182E
0x180001774  xor     edx, edx; Val
0x180001776  lea     rcx, [rsp+1D8h+WSAData]; void *
0x18000177b  mov     r8d, 198h; Size
0x180001781  call    memset_0
0x180001786  mov     ecx, 2; wVersionRequested
0x18000178b  lea     rdx, [rsp+1D8h+WSAData]; lpWSAData
0x180001790  call    cs:__imp_WSAStartup
0x180001797  nop     dword ptr [rax+rax+00h]
0x18000179c  test    eax, eax
0x18000179e  jz      short loc_18000181D
0x1800017a0  mov     [rsp+1D8h+arg_0], rbx
0x1800017a8  call    cs:__imp_WSAGetLastError
0x1800017af  nop     dword ptr [rax+rax+00h]
0x1800017b4  mov     ebx, eax
0x1800017b6  test    eax, eax
0x1800017b8  jnz     loc_180001BB9
0x1800017be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800017c5  cmp     rcx, rdi
0x1800017c8  jnz     loc_180001BFA
0x1800017ce  mov     eax, ebx
0x1800017d0  mov     rbx, [rsp+1D8h+arg_0]
0x1800017d8  jmp     short loc_180001803
0x1800017da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800017e1  cmp     rcx, rdi
0x1800017e4  jnz     loc_18000187D
0x1800017ea  cmp     cs:hInstRasmans, 0
0x1800017f2  jz      loc_1800018B2
0x1800017f8  cmp     rcx, rdi
0x1800017fb  jnz     loc_180001B70
0x180001801  xor     eax, eax
0x180001803  mov     rcx, [rsp+1D8h+var_18]
0x18000180b  xor     rcx, rsp; StackCookie
0x18000180e  call    __security_check_cookie
0x180001813  add     rsp, 1D0h
0x18000181a  pop     rdi
0x18000181b  retn
0x18000181d  mov     rcx, cs:WPP_GLOBAL_Control
0x180001824  mov     cs:g_fWinsockInitialized, 1
0x18000182e  cmp     rcx, rdi
0x180001831  jz      short loc_180001801
0x180001833  test    byte ptr [rcx+1Ch], 40h
0x180001837  jz      short loc_180001801
0x180001839  cmp     byte ptr [rcx+19h], 6
0x18000183d  jb      short loc_180001801
0x18000183f  mov     edx, 42h ; 'B'
0x180001844  mov     rcx, [rcx+10h]
0x180001848  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18000184f  xor     r9d, r9d
0x180001852  call    WPP_SF_d
0x180001857  jmp     short loc_180001801
0x180001859  cmp     byte ptr [rcx+19h], 6
0x18000185d  jb      loc_180001728
0x180001863  mov     rcx, [rcx+10h]
0x180001867  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18000186e  mov     edx, 33h ; '3'
0x180001873  call    WPP_SF_
0x180001878  jmp     loc_180001728
0x18000187d  test    byte ptr [rcx+1Ch], 40h
0x180001881  jz      loc_1800017EA
0x180001887  cmp     byte ptr [rcx+19h], 5
0x18000188b  jb      loc_1800017EA
0x180001891  mov     rcx, [rcx+10h]
0x180001895  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x18000189c  mov     edx, 34h ; '4'
0x1800018a1  call    WPP_SF_
0x1800018a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800018ad  jmp     loc_1800017EA
0x1800018b2  xor     edx, edx; hFile
0x1800018b4  lea     rcx, LibFileName; "rasmans.dll"
0x1800018bb  mov     r8d, 800h; dwFlags
0x1800018c1  call    cs:__imp_LoadLibraryExA
0x1800018c8  nop     dword ptr [rax+rax+00h]
0x1800018cd  mov     cs:hInstRasmans, rax
0x1800018d4  test    rax, rax
0x1800018d7  jnz     loc_180001986
0x1800018dd  call    cs:__imp_GetLastError
0x1800018e4  nop     dword ptr [rax+rax+00h]
0x1800018e9  test    eax, eax
0x1800018eb  jz      short loc_180001921
0x1800018ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800018f4  cmp     rcx, rdi
0x1800018f7  jz      loc_180001B5A
0x1800018fd  test    byte ptr [rcx+1Ch], 40h
0x180001901  jz      short loc_180001928
0x180001903  cmp     byte ptr [rcx+19h], 2
0x180001907  jb      short loc_180001928
0x180001909  mov     rcx, [rcx+10h]
0x18000190d  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180001914  mov     edx, 35h ; '5'
0x180001919  mov     r9d, eax
0x18000191c  call    WPP_SF_d
0x180001921  mov     rcx, cs:WPP_GLOBAL_Control
0x180001928  cmp     rcx, rdi
0x18000192b  jz      loc_180001B5A
0x180001931  test    byte ptr [rcx+1Ch], 40h
0x180001935  jz      short loc_18000195F
0x180001937  cmp     byte ptr [rcx+19h], 2
0x18000193b  jb      short loc_18000195F
0x18000193d  mov     rcx, [rcx+10h]
0x180001941  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180001948  mov     edx, 36h ; '6'
0x18000194d  mov     r9d, 2C7h
0x180001953  call    WPP_SF_d
0x180001958  mov     rcx, cs:WPP_GLOBAL_Control
0x18000195f  cmp     rcx, rdi
0x180001962  jz      loc_180001B5A
0x180001968  test    byte ptr [rcx+1Ch], 40h
0x18000196c  jz      loc_180001B5A
0x180001972  cmp     byte ptr [rcx+19h], 6
0x180001976  jb      loc_180001B5A
0x18000197c  mov     edx, 37h ; '7'
0x180001981  jmp     loc_180001B44
0x180001986  lea     rdx, ProcName; "ServiceRequestInProcess"
0x18000198d  mov     rcx, rax; hModule
0x180001990  call    cs:__imp_GetProcAddress
0x180001997  nop     dword ptr [rax+rax+00h]
0x18000199c  mov     rcx, cs:hInstRasmans; hModule
0x1800019a3  mov     cs:g_fnServiceRequest, rax
0x1800019aa  test    rax, rax
0x1800019ad  jnz     loc_180001A71
0x1800019b3  call    cs:__imp_FreeLibrary
0x1800019ba  nop     dword ptr [rax+rax+00h]
0x1800019bf  xor     eax, eax
0x1800019c1  mov     cs:hInstRasmans, rax
0x1800019c8  call    cs:__imp_GetLastError
0x1800019cf  nop     dword ptr [rax+rax+00h]
0x1800019d4  test    eax, eax
0x1800019d6  jz      short loc_180001A0C
0x1800019d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800019df  cmp     rcx, rdi
0x1800019e2  jz      loc_180001B5A
0x1800019e8  test    byte ptr [rcx+1Ch], 40h
0x1800019ec  jz      short loc_180001A13
0x1800019ee  cmp     byte ptr [rcx+19h], 2
0x1800019f2  jb      short loc_180001A13
0x1800019f4  mov     rcx, [rcx+10h]
0x1800019f8  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x1800019ff  mov     edx, 38h ; '8'
0x180001a04  mov     r9d, eax
0x180001a07  call    WPP_SF_d
0x180001a0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180001a13  cmp     rcx, rdi
0x180001a16  jz      loc_180001B5A
0x180001a1c  test    byte ptr [rcx+1Ch], 40h
0x180001a20  jz      short loc_180001A4A
0x180001a22  cmp     byte ptr [rcx+19h], 2
0x180001a26  jb      short loc_180001A4A
0x180001a28  mov     rcx, [rcx+10h]
0x180001a2c  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180001a33  mov     edx, 39h ; '9'
0x180001a38  mov     r9d, 2C7h
0x180001a3e  call    WPP_SF_d
0x180001a43  mov     rcx, cs:WPP_GLOBAL_Control
0x180001a4a  cmp     rcx, rdi
0x180001a4d  jz      loc_180001B5A
0x180001a53  test    byte ptr [rcx+1Ch], 40h
0x180001a57  jz      loc_180001B5A
0x180001a5d  cmp     byte ptr [rcx+19h], 6
0x180001a61  jb      loc_180001B5A
0x180001a67  mov     edx, 3Ah ; ':'
0x180001a6c  jmp     loc_180001B44
0x180001a71  lea     rdx, aServiceinitial; "ServiceInitialized"
0x180001a78  call    cs:__imp_GetProcAddress
0x180001a7f  nop     dword ptr [rax+rax+00h]
0x180001a84  mov     cs:g_fnRasmanServiceInitialized, rax
0x180001a8b  test    rax, rax
0x180001a8e  jnz     loc_180001B64
0x180001a94  mov     rcx, cs:hInstRasmans; hLibModule
0x180001a9b  call    cs:__imp_FreeLibrary
0x180001aa2  nop     dword ptr [rax+rax+00h]
0x180001aa7  xor     eax, eax
0x180001aa9  mov     cs:hInstRasmans, rax
0x180001ab0  call    cs:__imp_GetLastError
0x180001ab7  nop     dword ptr [rax+rax+00h]
0x180001abc  test    eax, eax
0x180001abe  jz      short loc_180001AF4
0x180001ac0  mov     rcx, cs:WPP_GLOBAL_Control
0x180001ac7  cmp     rcx, rdi
0x180001aca  jz      loc_180001B5A
0x180001ad0  test    byte ptr [rcx+1Ch], 40h
0x180001ad4  jz      short loc_180001AFB
0x180001ad6  cmp     byte ptr [rcx+19h], 2
0x180001ada  jb      short loc_180001AFB
0x180001adc  mov     rcx, [rcx+10h]
0x180001ae0  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180001ae7  mov     edx, 3Bh ; ';'
0x180001aec  mov     r9d, eax
0x180001aef  call    WPP_SF_d
0x180001af4  mov     rcx, cs:WPP_GLOBAL_Control
0x180001afb  cmp     rcx, rdi
0x180001afe  jz      short loc_180001B5A
0x180001b00  test    byte ptr [rcx+1Ch], 40h
0x180001b04  jz      short loc_180001B2E
0x180001b06  cmp     byte ptr [rcx+19h], 2
0x180001b0a  jb      short loc_180001B2E
0x180001b0c  mov     rcx, [rcx+10h]
0x180001b10  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180001b17  mov     edx, 3Ch ; '<'
0x180001b1c  mov     r9d, 2C7h
0x180001b22  call    WPP_SF_d
0x180001b27  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b2e  cmp     rcx, rdi
0x180001b31  jz      short loc_180001B5A
0x180001b33  test    byte ptr [rcx+1Ch], 40h
0x180001b37  jz      short loc_180001B5A
0x180001b39  cmp     byte ptr [rcx+19h], 6
0x180001b3d  jb      short loc_180001B5A
0x180001b3f  mov     edx, 3Dh ; '='
0x180001b44  mov     rcx, [rcx+10h]
0x180001b48  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180001b4f  mov     r9d, 2C7h
0x180001b55  call    WPP_SF_d
0x180001b5a  mov     eax, 2C7h
0x180001b5f  jmp     loc_180001803
0x180001b64  mov     rcx, cs:WPP_GLOBAL_Control
0x180001b6b  jmp     loc_1800017F8
0x180001b70  test    byte ptr [rcx+1Ch], 40h
0x180001b74  jz      loc_180001801
0x180001b7a  cmp     byte ptr [rcx+19h], 6
0x180001b7e  jb      loc_180001801
0x180001b84  mov     edx, 3Eh ; '>'
0x180001b89  jmp     loc_180001844
0x180001b8e  cmp     byte ptr [rcx+19h], 5
0x180001b92  jb      loc_180001751
0x180001b98  mov     rcx, [rcx+10h]
0x180001b9c  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180001ba3  mov     edx, 3Fh ; '?'
0x180001ba8  call    WPP_SF_
0x180001bad  mov     rcx, cs:WPP_GLOBAL_Control
0x180001bb4  jmp     loc_180001751
0x180001bb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180001bc0  cmp     rcx, rdi
0x180001bc3  jz      loc_1800017CE
0x180001bc9  test    byte ptr [rcx+1Ch], 40h
0x180001bcd  jz      loc_1800017C5
0x180001bd3  cmp     byte ptr [rcx+19h], 2
0x180001bd7  jb      loc_1800017C5
0x180001bdd  mov     rcx, [rcx+10h]
0x180001be1  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180001be8  mov     edx, 40h ; '@'
0x180001bed  mov     r9d, ebx
0x180001bf0  call    WPP_SF_d
0x180001bf5  jmp     loc_1800017BE
0x180001bfa  test    byte ptr [rcx+1Ch], 40h
0x180001bfe  jz      loc_1800017CE
0x180001c04  cmp     byte ptr [rcx+19h], 6
0x180001c08  jb      loc_1800017CE
0x180001c0e  mov     rcx, [rcx+10h]
0x180001c12  lea     r8, WPP_540dc6cfd5e1370610f4c4bf743174e2_Traceguids
0x180001c19  mov     edx, 41h ; 'A'
0x180001c1e  mov     r9d, ebx
0x180001c21  call    WPP_SF_d
0x180001c26  jmp     loc_1800017CE
```
