# CFhService::SetServiceStartType(int)

- ea: `0x180002f30`
- end: `0x18000317c`
- name: `?SetServiceStartType@CFhService@@QEAAJH@Z`
- size: `588`
- prototype: `__int64 __fastcall(CFhService *__hidden this, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x180001950`
- `0x1800079e0`
- `0x18000e8b0`

## callees

- `0x180002f30`
- `0x18000ca14`
- `0x18000d910`
- `0x18000d970`

## import_xrefs

- `ADVAPI32!CloseServiceHandle` at `0x180003152`
- `ADVAPI32!CloseServiceHandle` at `0x18000315b`
- `ADVAPI32!CloseServiceHandle` at `0x180003152`
- `ADVAPI32!CloseServiceHandle` at `0x18000315b`
- `ADVAPI32!ChangeServiceConfig2W` at `0x1800030fe`
- `ADVAPI32!ChangeServiceConfig2W` at `0x1800030fe`
- `ADVAPI32!ChangeServiceConfigW` at `0x1800030a7`
- `ADVAPI32!ChangeServiceConfigW` at `0x1800030a7`
- `ADVAPI32!OpenServiceW` at `0x180003008`
- `ADVAPI32!OpenServiceW` at `0x180003008`
- `ADVAPI32!OpenSCManagerW` at `0x180002f90`
- `ADVAPI32!OpenSCManagerW` at `0x180002f90`
- `KERNEL32!GetLastError` at `0x180002f9e`
- `KERNEL32!GetLastError` at `0x180003016`
- `KERNEL32!GetLastError` at `0x1800030b1`
- `KERNEL32!GetLastError` at `0x180003108`
- `KERNEL32!GetLastError` at `0x180002f9e`
- `KERNEL32!GetLastError` at `0x180003016`
- `KERNEL32!GetLastError` at `0x1800030b1`
- `KERNEL32!GetLastError` at `0x180003108`

## string_xrefs

- `0x180002f87`: `ServicesActive`

## pseudocode

```c
__int64 __fastcall CFhService::SetServiceStartType(CFhService *this, int a2)
{
  const wchar_t *v3; // r9
  SC_HANDLE v4; // rax
  SC_HANDLE v5; // rbx
  signed int v6; // eax
  unsigned int v7; // ebx
  SC_HANDLE v9; // rax
  SC_HANDLE v10; // rbp
  signed int LastError; // eax
  unsigned int v12; // esi
  signed int v13; // eax
  _QWORD *v14; // rcx
  int v15; // edx
  signed int v16; // eax
  CFhService *Info; // [rsp+80h] [rbp+8h] BYREF

  Info = this;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v3 = L"Demand";
    if ( !a2 )
      v3 = L"Auto Delayed";
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids, v3);
  }
  v4 = OpenSCManagerW(0, L"ServicesActive", 1u);
  v5 = v4;
  if ( v4 )
  {
    v9 = OpenServiceW(v4, L"fhsvc", 2u);
    v10 = v9;
    if ( !v9 )
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          31,
          (unsigned int)&WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids,
          (unsigned int)L"fhsvc",
          v12);
      goto LABEL_34;
    }
    v12 = 0;
    if ( ChangeServiceConfigW(v9, 0xFFFFFFFF, (a2 != 0) + 2, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
    {
      if ( a2 )
        goto LABEL_33;
      LODWORD(Info) = 1;
      if ( ChangeServiceConfig2W(v10, 3u, &Info) )
        goto LABEL_33;
      v16 = GetLastError();
      v12 = v16;
      if ( v16 > 0 )
        v12 = (unsigned __int16)v16 | 0x80070000;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_33;
      v15 = 33;
    }
    else
    {
      v13 = GetLastError();
      v12 = v13;
      if ( v13 > 0 )
        v12 = (unsigned __int16)v13 | 0x80070000;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_33;
      v15 = 32;
    }
    WPP_SF_Sd(v14[2], v15, (unsigned int)&WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids, (unsigned int)L"fhsvc", v12);
LABEL_33:
    CloseServiceHandle(v10);
LABEL_34:
    CloseServiceHandle(v5);
    return v12;
  }
  v6 = GetLastError();
  v7 = v6;
  if ( v6 > 0 )
    v7 = (unsigned __int16)v6 | 0x80070000;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids, v7);
  return v7;
}

```

## disassembly

```asm
0x180002f30  mov     [rsp+Info], rcx
0x180002f35  push    rbx
0x180002f36  push    rdi
0x180002f37  push    r14
0x180002f39  sub     rsp, 60h
0x180002f3d  mov     edi, edx
0x180002f3f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f46  lea     r14, WPP_GLOBAL_Control
0x180002f4d  cmp     rcx, r14
0x180002f50  jz      short loc_180002F81
0x180002f52  test    byte ptr [rcx+1Ch], 8
0x180002f56  jz      short loc_180002F81
0x180002f58  mov     rcx, [rcx+10h]
0x180002f5c  lea     rax, aAutoDelayed; "Auto Delayed"
0x180002f63  test    edx, edx
0x180002f65  lea     r9, aDemand; "Demand"
0x180002f6c  mov     edx, 1Dh
0x180002f71  lea     r8, WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids
0x180002f78  cmovz   r9, rax
0x180002f7c  call    WPP_SF_S
0x180002f81  mov     r8d, 1; dwDesiredAccess
0x180002f87  lea     rdx, DatabaseName; "ServicesActive"
0x180002f8e  xor     ecx, ecx; lpMachineName
0x180002f90  call    cs:__imp_OpenSCManagerW
0x180002f96  mov     rbx, rax
0x180002f99  test    rax, rax
0x180002f9c  jnz     short loc_180002FE8
0x180002f9e  call    cs:__imp_GetLastError
0x180002fa4  mov     ebx, eax
0x180002fa6  test    eax, eax
0x180002fa8  jle     short loc_180002FB3
0x180002faa  movzx   ebx, ax
0x180002fad  or      ebx, 80070000h
0x180002fb3  mov     rcx, cs:WPP_GLOBAL_Control
0x180002fba  cmp     rcx, r14
0x180002fbd  jz      short loc_180002FDD
0x180002fbf  test    byte ptr [rcx+1Ch], 1
0x180002fc3  jz      short loc_180002FDD
0x180002fc5  mov     rcx, [rcx+10h]
0x180002fc9  lea     r8, WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids
0x180002fd0  mov     edx, 1Eh
0x180002fd5  mov     r9d, ebx
0x180002fd8  call    WPP_SF_d
0x180002fdd  mov     eax, ebx
0x180002fdf  add     rsp, 60h
0x180002fe3  pop     r14
0x180002fe5  pop     rdi
0x180002fe6  pop     rbx
0x180002fe7  retn
0x180002fe8  mov     [rsp+78h+arg_8], rbp
0x180002ff0  lea     rdx, ServiceName; "fhsvc"
0x180002ff7  mov     r8d, 2; dwDesiredAccess
0x180002ffd  mov     [rsp+78h+arg_10], rsi
0x180003005  mov     rcx, rbx; hSCManager
0x180003008  call    cs:__imp_OpenServiceW
0x18000300e  mov     rbp, rax
0x180003011  test    rax, rax
0x180003014  jnz     short loc_18000306A
0x180003016  call    cs:__imp_GetLastError
0x18000301c  mov     esi, eax
0x18000301e  test    eax, eax
0x180003020  jle     short loc_18000302B
0x180003022  movzx   esi, ax
0x180003025  or      esi, 80070000h
0x18000302b  mov     rcx, cs:WPP_GLOBAL_Control
0x180003032  cmp     rcx, r14
0x180003035  jz      loc_180003158
0x18000303b  test    byte ptr [rcx+1Ch], 1
0x18000303f  jz      loc_180003158
0x180003045  mov     rcx, [rcx+10h]
0x180003049  lea     r9, ServiceName; "fhsvc"
0x180003050  mov     edx, 1Fh
0x180003055  mov     dword ptr [rsp+78h+lpBinaryPathName], esi
0x180003059  lea     r8, WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids
0x180003060  call    WPP_SF_Sd
0x180003065  jmp     loc_180003158
0x18000306a  xor     esi, esi
0x18000306c  mov     edx, 0FFFFFFFFh; dwServiceType
0x180003071  mov     [rsp+78h+lpDisplayName], rsi; lpDisplayName
0x180003076  mov     r8d, esi
0x180003079  mov     [rsp+78h+lpPassword], rsi; lpPassword
0x18000307e  test    edi, edi
0x180003080  mov     [rsp+78h+lpServiceStartName], rsi; lpServiceStartName
0x180003085  mov     r9d, edx; dwErrorControl
0x180003088  mov     [rsp+78h+lpDependencies], rsi; lpDependencies
0x18000308d  setnz   r8b
0x180003091  mov     [rsp+78h+lpdwTagId], rsi; lpdwTagId
0x180003096  add     r8d, 2; dwStartType
0x18000309a  mov     [rsp+78h+lpLoadOrderGroup], rsi; lpLoadOrderGroup
0x18000309f  mov     rcx, rbp; hService
0x1800030a2  mov     [rsp+78h+lpBinaryPathName], rsi; lpBinaryPathName
0x1800030a7  call    cs:__imp_ChangeServiceConfigW
0x1800030ad  test    eax, eax
0x1800030af  jnz     short loc_1800030DF
0x1800030b1  call    cs:__imp_GetLastError
0x1800030b7  mov     esi, eax
0x1800030b9  test    eax, eax
0x1800030bb  jle     short loc_1800030C6
0x1800030bd  movzx   esi, ax
0x1800030c0  or      esi, 80070000h
0x1800030c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800030cd  cmp     rcx, r14
0x1800030d0  jz      short loc_18000314F
0x1800030d2  test    byte ptr [rcx+1Ch], 1
0x1800030d6  jz      short loc_18000314F
0x1800030d8  mov     edx, 20h ; ' '
0x1800030dd  jmp     short loc_180003134
0x1800030df  test    edi, edi
0x1800030e1  jnz     short loc_18000314F
0x1800030e3  lea     r8, [rsp+78h+Info]; lpInfo
0x1800030eb  mov     dword ptr [rsp+78h+Info], 1
0x1800030f6  mov     edx, 3; dwInfoLevel
0x1800030fb  mov     rcx, rbp; hService
0x1800030fe  call    cs:__imp_ChangeServiceConfig2W
0x180003104  test    eax, eax
0x180003106  jnz     short loc_18000314F
0x180003108  call    cs:__imp_GetLastError
0x18000310e  mov     esi, eax
0x180003110  test    eax, eax
0x180003112  jle     short loc_18000311D
0x180003114  movzx   esi, ax
0x180003117  or      esi, 80070000h
0x18000311d  mov     rcx, cs:WPP_GLOBAL_Control
0x180003124  cmp     rcx, r14
0x180003127  jz      short loc_18000314F
0x180003129  test    byte ptr [rcx+1Ch], 1
0x18000312d  jz      short loc_18000314F
0x18000312f  mov     edx, 21h ; '!'
0x180003134  mov     rcx, [rcx+10h]
0x180003138  lea     r9, ServiceName; "fhsvc"
0x18000313f  lea     r8, WPP_305fb7554e703b1695bfea0e3f3a03b2_Traceguids
0x180003146  mov     dword ptr [rsp+78h+lpBinaryPathName], esi
0x18000314a  call    WPP_SF_Sd
0x18000314f  mov     rcx, rbp; hSCObject
0x180003152  call    cs:__imp_CloseServiceHandle
0x180003158  mov     rcx, rbx; hSCObject
0x18000315b  call    cs:__imp_CloseServiceHandle
0x180003161  mov     rbp, [rsp+78h+arg_8]
0x180003169  mov     eax, esi
0x18000316b  mov     rsi, [rsp+78h+arg_10]
0x180003173  add     rsp, 60h
0x180003177  pop     r14
0x180003179  pop     rdi
0x18000317a  pop     rbx
0x18000317b  retn
```
