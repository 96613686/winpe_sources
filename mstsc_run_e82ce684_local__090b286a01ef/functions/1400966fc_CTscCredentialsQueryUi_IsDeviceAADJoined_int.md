# CTscCredentialsQueryUi::IsDeviceAADJoined(int *)

- ea: `0x1400966fc`
- end: `0x140096936`
- name: `?IsDeviceAADJoined@CTscCredentialsQueryUi@@CAJPEAH@Z`
- size: `570`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1400970b0`

## callees

- `0x14000b7d8`
- `0x14000cf70`
- `0x14000cfb0`
- `0x14000d078`
- `0x1400966fc`
- `0x140114010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x14009677c`
- `KERNEL32!LoadLibraryW` at `0x14009677c`
- `KERNEL32!FreeLibrary` at `0x140096925`
- `KERNEL32!FreeLibrary` at `0x140096925`
- `KERNEL32!GetProcAddress` at `0x1400967fd`
- `KERNEL32!GetProcAddress` at `0x140096810`
- `KERNEL32!GetProcAddress` at `0x1400967fd`
- `KERNEL32!GetProcAddress` at `0x140096810`
- `KERNEL32!GetLastError` at `0x14009678a`
- `KERNEL32!GetLastError` at `0x14009678a`

## string_xrefs

- `0x140096775`: `netapi32.dll`

## pseudocode

```c
__int64 __fastcall CTscCredentialsQueryUi::IsDeviceAADJoined(int *a1)
{
  void (*v1)(void); // rbp
  HMODULE v3; // rdi
  unsigned int v4; // eax
  signed int LastError; // ebx
  HMODULE LibraryW; // rax
  unsigned int v7; // eax
  FARPROC ProcAddress; // rbx
  FARPROC v9; // rax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v11; // eax
  unsigned int v12; // eax
  _DWORD *v14; // [rsp+60h] [rbp+8h] BYREF

  v1 = 0;
  v14 = 0;
  if ( a1 )
  {
    LibraryW = LoadLibraryW(L"netapi32.dll");
    v3 = LibraryW;
    if ( LibraryW )
    {
      ProcAddress = GetProcAddress(LibraryW, "NetGetAadJoinInformation");
      v9 = GetProcAddress(v3, "NetFreeAadJoinInformation");
      v1 = (void (*)(void))v9;
      if ( ProcAddress && v9 )
      {
        LastError = ((__int64 (__fastcall *)(_QWORD, _DWORD **))ProcAddress)(0, &v14);
        if ( LastError >= 0 )
        {
          if ( !v14 || (v11 = 1, *v14 != 1) )
            v11 = 0;
          *a1 = v11;
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            62,
            (unsigned int)WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids,
            CurrentThreadActivityIdPrefix,
            (__int64)"NetGetAadJoinInformation failed",
            LastError);
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
        {
          v12 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids, v12);
        }
        LastError = -2147467263;
      }
    }
    else
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v7 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          60,
          WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids,
          v7,
          LastError);
      }
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError >= 0 )
        LastError = -2147467259;
    }
  }
  else
  {
    v3 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v4 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        59,
        (unsigned int)WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids,
        v4,
        (__int64)"pfAADJoined",
        -2147024809);
    }
    LastError = -2147024809;
  }
  if ( v14 && v1 )
    v1();
  if ( v3 )
    FreeLibrary(v3);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1400966fc  push    rbx
0x1400966fe  push    rbp
0x1400966ff  push    rsi
0x140096700  push    rdi
0x140096701  sub     rsp, 38h
0x140096705  xor     ebp, ebp
0x140096707  mov     rsi, rcx
0x14009670a  mov     [rsp+58h+arg_0], rbp
0x14009670f  test    rcx, rcx
0x140096712  jnz     short loc_140096775
0x140096714  xor     edi, edi
0x140096716  mov     rcx, cs:WPP_GLOBAL_Control
0x14009671d  lea     rax, WPP_GLOBAL_Control
0x140096724  cmp     rcx, rax
0x140096727  jz      short loc_14009676B
0x140096729  test    byte ptr [rcx+1Ch], 8
0x14009672d  jz      short loc_14009676B
0x14009672f  cmp     byte ptr [rcx+19h], 2
0x140096733  jb      short loc_14009676B
0x140096735  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14009673a  lea     rcx, aPfaadjoined; "pfAADJoined"
0x140096741  mov     [rsp+58h+var_30], 80070057h
0x140096749  mov     [rsp+58h+var_38], rcx
0x14009674e  lea     edx, [rsi+3Bh]
0x140096751  mov     rcx, cs:WPP_GLOBAL_Control
0x140096758  lea     r8, WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids
0x14009675f  mov     r9d, eax
0x140096762  mov     rcx, [rcx+10h]
0x140096766  call    WPP_SF_DsD
0x14009676b  mov     ebx, 80070057h
0x140096770  jmp     loc_140096906
0x140096775  lea     rcx, aNetapi32Dll_0; "netapi32.dll"
0x14009677c  call    cs:__imp_LoadLibraryW
0x140096782  mov     rdi, rax
0x140096785  test    rax, rax
0x140096788  jnz     short loc_1400967F3
0x14009678a  call    cs:__imp_GetLastError
0x140096790  mov     ebx, eax
0x140096792  mov     rcx, cs:WPP_GLOBAL_Control
0x140096799  lea     rax, WPP_GLOBAL_Control
0x1400967a0  cmp     rcx, rax
0x1400967a3  jz      short loc_1400967D7
0x1400967a5  test    byte ptr [rcx+1Ch], 8
0x1400967a9  jz      short loc_1400967D7
0x1400967ab  cmp     byte ptr [rcx+19h], 2
0x1400967af  jb      short loc_1400967D7
0x1400967b1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400967b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400967bd  lea     edx, [rdi+3Ch]
0x1400967c0  mov     r9d, eax
0x1400967c3  mov     dword ptr [rsp+58h+var_38], ebx
0x1400967c7  lea     r8, WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids
0x1400967ce  mov     rcx, [rcx+10h]
0x1400967d2  call    WPP_SF_Dd
0x1400967d7  test    ebx, ebx
0x1400967d9  jle     short loc_1400967E4
0x1400967db  movzx   ebx, bx
0x1400967de  or      ebx, 80070000h
0x1400967e4  test    ebx, ebx
0x1400967e6  mov     eax, 80004005h
0x1400967eb  cmovns  ebx, eax
0x1400967ee  jmp     loc_140096906
0x1400967f3  lea     rdx, aNetgetaadjoini; "NetGetAadJoinInformation"
0x1400967fa  mov     rcx, rdi; hModule
0x1400967fd  call    cs:__imp_GetProcAddress
0x140096803  lea     rdx, aNetfreeaadjoin; "NetFreeAadJoinInformation"
0x14009680a  mov     rcx, rdi; hModule
0x14009680d  mov     rbx, rax
0x140096810  call    cs:__imp_GetProcAddress
0x140096816  mov     rbp, rax
0x140096819  test    rbx, rbx
0x14009681c  jz      loc_1400968BA
0x140096822  test    rax, rax
0x140096825  jz      loc_1400968BA
0x14009682b  lea     rdx, [rsp+58h+arg_0]
0x140096830  xor     ecx, ecx
0x140096832  mov     rax, rbx
0x140096835  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009683a  mov     ebx, eax
0x14009683c  test    eax, eax
0x14009683e  jns     short loc_1400968A1
0x140096840  mov     rcx, cs:WPP_GLOBAL_Control
0x140096847  lea     rax, WPP_GLOBAL_Control
0x14009684e  cmp     rcx, rax
0x140096851  jz      loc_140096906
0x140096857  test    byte ptr [rcx+1Ch], 8
0x14009685b  jz      loc_140096906
0x140096861  cmp     byte ptr [rcx+19h], 2
0x140096865  jb      loc_140096906
0x14009686b  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140096870  lea     rcx, aNetgetaadjoini_0; "NetGetAadJoinInformation failed"
0x140096877  mov     [rsp+58h+var_30], ebx
0x14009687b  mov     [rsp+58h+var_38], rcx
0x140096880  lea     r8, WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids
0x140096887  mov     rcx, cs:WPP_GLOBAL_Control
0x14009688e  mov     edx, 3Eh ; '>'
0x140096893  mov     r9d, eax
0x140096896  mov     rcx, [rcx+10h]
0x14009689a  call    WPP_SF_DsD
0x14009689f  jmp     short loc_140096906
0x1400968a1  mov     rcx, [rsp+58h+arg_0]
0x1400968a6  test    rcx, rcx
0x1400968a9  jz      short loc_1400968B4
0x1400968ab  mov     eax, 1
0x1400968b0  cmp     [rcx], eax
0x1400968b2  jz      short loc_1400968B6
0x1400968b4  xor     eax, eax
0x1400968b6  mov     [rsi], eax
0x1400968b8  jmp     short loc_140096906
0x1400968ba  mov     rcx, cs:WPP_GLOBAL_Control
0x1400968c1  lea     rax, WPP_GLOBAL_Control
0x1400968c8  cmp     rcx, rax
0x1400968cb  jz      short loc_140096901
0x1400968cd  mov     eax, 1
0x1400968d2  test    [rcx+1Ch], al
0x1400968d5  jz      short loc_140096901
0x1400968d7  cmp     byte ptr [rcx+19h], 3
0x1400968db  jb      short loc_140096901
0x1400968dd  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400968e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400968e9  lea     r8, WPP_18bc4e26a4bc376c253e104f1e7a3196_Traceguids
0x1400968f0  mov     edx, 3Dh ; '='
0x1400968f5  mov     r9d, eax
0x1400968f8  mov     rcx, [rcx+10h]
0x1400968fc  call    WPP_SF_d
0x140096901  mov     ebx, 80004001h
0x140096906  mov     rcx, [rsp+58h+arg_0]
0x14009690b  test    rcx, rcx
0x14009690e  jz      short loc_14009691D
0x140096910  test    rbp, rbp
0x140096913  jz      short loc_14009691D
0x140096915  mov     rax, rbp
0x140096918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14009691d  test    rdi, rdi
0x140096920  jz      short loc_14009692B
0x140096922  mov     rcx, rdi; hLibModule
0x140096925  call    cs:__imp_FreeLibrary
0x14009692b  mov     eax, ebx
0x14009692d  add     rsp, 38h
0x140096931  pop     rdi
0x140096932  pop     rsi
0x140096933  pop     rbp
0x140096934  pop     rbx
0x140096935  retn
```
