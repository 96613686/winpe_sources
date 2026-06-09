# NPCancelConnection

- ea: `0x180005c40`
- end: `0x180006049`
- name: `NPCancelConnection`
- size: `1033`
- prototype: `DWORD __stdcall(LPWSTR lpName, BOOL fForce)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x180002508`
- `0x180002538`
- `0x180005c40`
- `0x180008d00`
- `0x180009004`
- `0x1800091f4`
- `0x18000b0d8`
- `0x18000bda4`
- `0x18000e198`
- `0x180012e32`
- `0x180012e70`

## import_xrefs

- `msvcrt!towupper` at `0x180005da1`
- `msvcrt!towupper` at `0x180005da1`
- `ntdll!RtlAppendUnicodeToString` at `0x180005f2d`
- `ntdll!RtlAppendUnicodeToString` at `0x180005f4d`
- `ntdll!RtlAppendUnicodeToString` at `0x180005f67`
- `ntdll!RtlAppendUnicodeToString` at `0x180005f83`
- `ntdll!RtlAppendUnicodeToString` at `0x180005f2d`
- `ntdll!RtlAppendUnicodeToString` at `0x180005f4d`
- `ntdll!RtlAppendUnicodeToString` at `0x180005f67`
- `ntdll!RtlAppendUnicodeToString` at `0x180005f83`
- `KERNEL32!GetCurrentProcess` at `0x180005ea9`
- `KERNEL32!GetCurrentProcess` at `0x180005ea9`
- `KERNEL32!LocalFree` at `0x180005fd7`
- `KERNEL32!LocalFree` at `0x180005fd7`
- `ADVAPI32!RegDeleteKeyW` at `0x180005f9f`
- `ADVAPI32!RegDeleteKeyW` at `0x180005f9f`
- `ADVAPI32!ConvertSidToStringSidW` at `0x180005f01`
- `ADVAPI32!ConvertSidToStringSidW` at `0x180005f01`
- `WSOCK32!__imp_WSAStartup` at `0x180005cc9`
- `WSOCK32!__imp_WSAStartup` at `0x180005cc9`
- `WSOCK32!__imp_WSACleanup` at `0x180005d71`
- `WSOCK32!__imp_WSACleanup` at `0x18000600e`
- `WSOCK32!__imp_WSACleanup` at `0x180005d71`
- `WSOCK32!__imp_WSACleanup` at `0x18000600e`

## string_xrefs

- `0x180005f77`: `\Mount`

## pseudocode

```c
DWORD __stdcall NPCancelConnection(LPWSTR lpName, BOOL fForce)
{
  int v4; // r8d
  DWORD v5; // ebx
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  int IsClientRunning; // eax
  wint_t v11; // ax
  unsigned int v12; // esi
  LPWSTR v13; // rbx
  DWORD v14; // eax
  __int64 v15; // rcx
  WCHAR Source[4]; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR StringSid; // [rsp+48h] [rbp-B8h] BYREF
  struct WSAData WSAData; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE Sid[544]; // [rsp+1F0h] [rbp+F0h] BYREF
  WCHAR TargetPath[264]; // [rsp+410h] [rbp+310h] BYREF
  char v22; // [rsp+620h] [rbp+520h] BYREF
  __int16 v23; // [rsp+828h] [rbp+728h]

  memset_0(&WSAData, 0, sizeof(WSAData));
  *(_DWORD *)Source = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_Sd(*((_QWORD *)WPP_GLOBAL_Control + 2), 177, v4, (_DWORD)lpName, fForce);
  if ( WSAStartup(0x101u, &WSAData) )
  {
    v5 = 1222;
    goto LABEL_6;
  }
  IsClientRunning = NfsNpIsClientRunning(Source);
  if ( IsClientRunning < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        178,
        &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids,
        (unsigned int)IsClientRunning);
    v5 = 1222;
LABEL_16:
    WSACleanup();
    goto LABEL_6;
  }
  v11 = *lpName;
  if ( *lpName == 92 )
  {
    if ( lpName[1] == 92 )
    {
      v12 = 0;
      goto LABEL_24;
    }
    goto LABEL_21;
  }
  if ( v11 )
  {
LABEL_21:
    v13 = lpName;
    do
    {
      *v13++ = towupper(v11);
      v11 = *v13;
    }
    while ( *v13 );
  }
  v12 = 1;
LABEL_24:
  v5 = DeleteConnection(fForce, v12, lpName, TargetPath);
  if ( v5 )
  {
    if ( *(_DWORD *)Source )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 179, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v5);
      goto LABEL_16;
    }
    v5 = 0;
  }
  if ( *(_DWORD *)Source && (v14 = RemoveDeviceEntry(v12, lpName), (v5 = v14) != 0) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 180, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v14);
  }
  else if ( v12 )
  {
    *(_QWORD *)&Destination.Length = 34078720;
    Destination.Buffer = (PWSTR)&v22;
    memset_0(Sid, 0, sizeof(Sid));
    StringSid = 0;
    v23 = 0;
    RemoveDosDevice(lpName, TargetPath);
    GetCurrentProcess();
    if ( DaGetProcessSid(v15, Sid) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 181, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
    }
    else if ( ConvertSidToStringSidW(Sid, &StringSid) )
    {
      Source[0] = *lpName;
      Source[1] = 0;
      if ( RtlAppendUnicodeToString(&Destination, StringSid) >= 0
        && RtlAppendUnicodeToString(&Destination, L"\\Network\\") >= 0
        && RtlAppendUnicodeToString(&Destination, Source) >= 0
        && RtlAppendUnicodeToString(&Destination, L"\\Mount") >= 0
        && RegDeleteKeyW(HKEY_USERS, Destination.Buffer)
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 182, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids);
      }
      LocalFree(StringSid);
    }
  }
  else
  {
    while ( !(unsigned int)DeleteConnection(fForce, 0, lpName, TargetPath)
         && !(unsigned int)RemoveDeviceEntry(0, lpName) )
      ;
    v5 = 0;
  }
  WSACleanup();
  if ( v5 )
  {
LABEL_6:
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v7 = 184;
      v8 = v5;
LABEL_9:
      WPP_SF_d(v6[2], v7, &WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids, v8);
      return v5;
    }
    return v5;
  }
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v7 = 183;
    v8 = 0;
    goto LABEL_9;
  }
  return v5;
}

```

## disassembly

```asm
0x180005c40  mov     [rsp-8+arg_10], rbx
0x180005c45  push    rbp
0x180005c46  push    rsi
0x180005c47  push    rdi
0x180005c48  push    r12
0x180005c4a  push    r13
0x180005c4c  push    r14
0x180005c4e  push    r15
0x180005c50  lea     rbp, [rsp-740h]
0x180005c58  sub     rsp, 840h
0x180005c5f  mov     rax, cs:__security_cookie
0x180005c66  xor     rax, rsp
0x180005c69  mov     [rbp+770h+var_40], rax
0x180005c70  mov     r14d, edx
0x180005c73  mov     rdi, rcx
0x180005c76  xor     edx, edx; Val
0x180005c78  lea     rcx, [rsp+870h+WSAData]; void *
0x180005c7d  mov     r8d, 198h; Size
0x180005c83  call    memset_0
0x180005c88  xor     r15d, r15d
0x180005c8b  mov     dword ptr [rsp+870h+Source], r15d
0x180005c90  mov     rcx, cs:WPP_GLOBAL_Control
0x180005c97  lea     r12, WPP_GLOBAL_Control
0x180005c9e  cmp     rcx, r12
0x180005ca1  jz      short loc_180005CBF
0x180005ca3  test    byte ptr [rcx+1Ch], 1
0x180005ca7  jz      short loc_180005CBF
0x180005ca9  mov     rcx, [rcx+10h]
0x180005cad  mov     edx, 0B1h
0x180005cb2  mov     r9, rdi
0x180005cb5  mov     [rsp+870h+var_850], r14d
0x180005cba  call    WPP_SF_Sd
0x180005cbf  mov     ecx, 101h; wVersionRequested
0x180005cc4  lea     rdx, [rsp+870h+WSAData]; lpWSAData
0x180005cc9  call    cs:__imp_WSAStartup
0x180005cd0  nop     dword ptr [rax+rax+00h]
0x180005cd5  lea     r13, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x180005cdc  test    eax, eax
0x180005cde  jz      short loc_180005D38
0x180005ce0  mov     ebx, 4C6h
0x180005ce5  mov     rcx, cs:WPP_GLOBAL_Control
0x180005cec  cmp     rcx, r12
0x180005cef  jz      short loc_180005D0B
0x180005cf1  test    byte ptr [rcx+1Ch], 2
0x180005cf5  jz      short loc_180005D0B
0x180005cf7  mov     edx, 0B8h
0x180005cfc  mov     r9d, ebx
0x180005cff  mov     rcx, [rcx+10h]
0x180005d03  mov     r8, r13
0x180005d06  call    WPP_SF_d
0x180005d0b  mov     eax, ebx
0x180005d0d  mov     rcx, [rbp+770h+var_40]
0x180005d14  xor     rcx, rsp; StackCookie
0x180005d17  call    __security_check_cookie
0x180005d1c  mov     rbx, [rsp+870h+arg_10]
0x180005d24  add     rsp, 840h
0x180005d2b  pop     r15
0x180005d2d  pop     r14
0x180005d2f  pop     r13
0x180005d31  pop     r12
0x180005d33  pop     rdi
0x180005d34  pop     rsi
0x180005d35  pop     rbp
0x180005d36  retn
0x180005d38  lea     rcx, [rsp+870h+Source]
0x180005d3d  call    NfsNpIsClientRunning
0x180005d42  test    eax, eax
0x180005d44  jns     short loc_180005D82
0x180005d46  mov     rcx, cs:WPP_GLOBAL_Control
0x180005d4d  cmp     rcx, r12
0x180005d50  jz      short loc_180005D6C
0x180005d52  test    byte ptr [rcx+1Ch], 2
0x180005d56  jz      short loc_180005D6C
0x180005d58  mov     rcx, [rcx+10h]
0x180005d5c  mov     edx, 0B2h
0x180005d61  mov     r9d, eax
0x180005d64  mov     r8, r13
0x180005d67  call    WPP_SF_d
0x180005d6c  mov     ebx, 4C6h
0x180005d71  call    cs:__imp_WSACleanup
0x180005d78  nop     dword ptr [rax+rax+00h]
0x180005d7d  jmp     loc_180005CE5
0x180005d82  movzx   eax, word ptr [rdi]
0x180005d85  cmp     ax, 5Ch ; '\'
0x180005d89  jnz     short loc_180005D96
0x180005d8b  cmp     [rdi+2], ax
0x180005d8f  jnz     short loc_180005D9B
0x180005d91  mov     esi, r15d
0x180005d94  jmp     short loc_180005DC1
0x180005d96  test    ax, ax
0x180005d99  jz      short loc_180005DBC
0x180005d9b  mov     rbx, rdi
0x180005d9e  movzx   ecx, ax; C
0x180005da1  call    cs:__imp_towupper
0x180005da8  nop     dword ptr [rax+rax+00h]
0x180005dad  mov     [rbx], ax
0x180005db0  lea     rbx, [rbx+2]
0x180005db4  movzx   eax, word ptr [rbx]
0x180005db7  test    ax, ax
0x180005dba  jnz     short loc_180005D9E
0x180005dbc  mov     esi, 1
0x180005dc1  lea     r9, [rbp+770h+TargetPath]
0x180005dc8  mov     r8, rdi
0x180005dcb  mov     edx, esi
0x180005dcd  mov     ecx, r14d
0x180005dd0  call    DeleteConnection
0x180005dd5  mov     ebx, eax
0x180005dd7  mov     eax, dword ptr [rsp+870h+Source]
0x180005ddb  test    ebx, ebx
0x180005ddd  jz      short loc_180005E15
0x180005ddf  test    eax, eax
0x180005de1  jz      short loc_180005E12
0x180005de3  mov     rcx, cs:WPP_GLOBAL_Control
0x180005dea  cmp     rcx, r12
0x180005ded  jz      short loc_180005D71
0x180005def  test    byte ptr [rcx+1Ch], 2
0x180005df3  jz      loc_180005D71
0x180005df9  mov     rcx, [rcx+10h]
0x180005dfd  mov     edx, 0B3h
0x180005e02  mov     r9d, ebx
0x180005e05  mov     r8, r13
0x180005e08  call    WPP_SF_d
0x180005e0d  jmp     loc_180005D71
0x180005e12  mov     ebx, r15d
0x180005e15  test    eax, eax
0x180005e17  jz      short loc_180005E5C
0x180005e19  mov     rdx, rdi
0x180005e1c  mov     ecx, esi
0x180005e1e  call    RemoveDeviceEntry
0x180005e23  mov     ebx, eax
0x180005e25  test    eax, eax
0x180005e27  jz      short loc_180005E5C
0x180005e29  mov     rcx, cs:WPP_GLOBAL_Control
0x180005e30  cmp     rcx, r12
0x180005e33  jz      loc_18000600E
0x180005e39  test    byte ptr [rcx+1Ch], 2
0x180005e3d  jz      loc_18000600E
0x180005e43  mov     rcx, [rcx+10h]
0x180005e47  mov     edx, 0B4h
0x180005e4c  mov     r9d, eax
0x180005e4f  mov     r8, r13
0x180005e52  call    WPP_SF_d
0x180005e57  jmp     loc_18000600E
0x180005e5c  xor     edx, edx; Val
0x180005e5e  test    esi, esi
0x180005e60  jz      loc_180005FF5
0x180005e66  lea     rax, [rbp+770h+var_250]
0x180005e6d  mov     qword ptr [rsp+870h+Destination.Length], 2080000h
0x180005e76  mov     r8d, 220h; Size
0x180005e7c  mov     [rsp+870h+Destination.Buffer], rax
0x180005e81  lea     rcx, [rbp+770h+Sid]; void *
0x180005e88  call    memset_0
0x180005e8d  lea     rdx, [rbp+770h+TargetPath]; lpTargetPath
0x180005e94  mov     [rsp+870h+StringSid], r15
0x180005e99  mov     rcx, rdi; lpDeviceName
0x180005e9c  mov     [rbp+770h+var_48], r15w
0x180005ea4  call    RemoveDosDevice
0x180005ea9  call    cs:__imp_GetCurrentProcess
0x180005eb0  nop     dword ptr [rax+rax+00h]
0x180005eb5  lea     rdx, [rbp+770h+Sid]
0x180005ebc  call    DaGetProcessSid
0x180005ec1  test    eax, eax
0x180005ec3  jz      short loc_180005EF5
0x180005ec5  mov     rcx, cs:WPP_GLOBAL_Control
0x180005ecc  cmp     rcx, r12
0x180005ecf  jz      loc_18000600E
0x180005ed5  test    byte ptr [rcx+1Ch], 2
0x180005ed9  jz      loc_18000600E
0x180005edf  mov     rcx, [rcx+10h]
0x180005ee3  mov     edx, 0B5h
0x180005ee8  mov     r8, r13
0x180005eeb  call    WPP_SF_
0x180005ef0  jmp     loc_18000600E
0x180005ef5  lea     rdx, [rsp+870h+StringSid]; StringSid
0x180005efa  lea     rcx, [rbp+770h+Sid]; Sid
0x180005f01  call    cs:__imp_ConvertSidToStringSidW
0x180005f08  nop     dword ptr [rax+rax+00h]
0x180005f0d  test    eax, eax
0x180005f0f  jz      loc_18000600E
0x180005f15  movzx   eax, word ptr [rdi]
0x180005f18  lea     rcx, [rsp+870h+Destination]; Destination
0x180005f1d  mov     rdx, [rsp+870h+StringSid]; Source
0x180005f22  mov     [rsp+870h+Source], ax
0x180005f27  mov     [rsp+870h+Source+2], r15w
0x180005f2d  call    cs:__imp_RtlAppendUnicodeToString
0x180005f34  nop     dword ptr [rax+rax+00h]
0x180005f39  test    eax, eax
0x180005f3b  js      loc_180005FD2
0x180005f41  lea     rdx, aNetwork_0; "\\Network\\"
0x180005f48  lea     rcx, [rsp+870h+Destination]; Destination
0x180005f4d  call    cs:__imp_RtlAppendUnicodeToString
0x180005f54  nop     dword ptr [rax+rax+00h]
0x180005f59  test    eax, eax
0x180005f5b  js      short loc_180005FD2
0x180005f5d  lea     rdx, [rsp+870h+Source]; Source
0x180005f62  lea     rcx, [rsp+870h+Destination]; Destination
0x180005f67  call    cs:__imp_RtlAppendUnicodeToString
0x180005f6e  nop     dword ptr [rax+rax+00h]
0x180005f73  test    eax, eax
0x180005f75  js      short loc_180005FD2
0x180005f77  lea     rdx, aMount; "\\Mount"
0x180005f7e  lea     rcx, [rsp+870h+Destination]; Destination
0x180005f83  call    cs:__imp_RtlAppendUnicodeToString
0x180005f8a  nop     dword ptr [rax+rax+00h]
0x180005f8f  test    eax, eax
0x180005f91  js      short loc_180005FD2
0x180005f93  mov     rdx, [rsp+870h+Destination.Buffer]; lpSubKey
0x180005f98  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180005f9f  call    cs:__imp_RegDeleteKeyW
0x180005fa6  nop     dword ptr [rax+rax+00h]
0x180005fab  test    eax, eax
0x180005fad  jz      short loc_180005FD2
0x180005faf  mov     rcx, cs:WPP_GLOBAL_Control
0x180005fb6  cmp     rcx, r12
0x180005fb9  jz      short loc_180005FD2
0x180005fbb  test    byte ptr [rcx+1Ch], 2
0x180005fbf  jz      short loc_180005FD2
0x180005fc1  mov     rcx, [rcx+10h]
0x180005fc5  mov     edx, 0B6h
0x180005fca  mov     r8, r13
0x180005fcd  call    WPP_SF_
0x180005fd2  mov     rcx, [rsp+870h+StringSid]; hMem
0x180005fd7  call    cs:__imp_LocalFree
0x180005fde  nop     dword ptr [rax+rax+00h]
0x180005fe3  jmp     short loc_18000600E
0x180005fe5  mov     rdx, rdi
0x180005fe8  xor     ecx, ecx
0x180005fea  call    RemoveDeviceEntry
0x180005fef  test    eax, eax
0x180005ff1  jnz     short loc_18000600B
0x180005ff3  xor     edx, edx
0x180005ff5  lea     r9, [rbp+770h+TargetPath]
0x180005ffc  mov     r8, rdi
0x180005fff  mov     ecx, r14d
0x180006002  call    DeleteConnection
0x180006007  test    eax, eax
0x180006009  jz      short loc_180005FE5
0x18000600b  mov     ebx, r15d
0x18000600e  call    cs:__imp_WSACleanup
0x180006015  nop     dword ptr [rax+rax+00h]
0x18000601a  test    ebx, ebx
0x18000601c  jnz     loc_180005CE5
0x180006022  mov     rcx, cs:WPP_GLOBAL_Control
0x180006029  cmp     rcx, r12
0x18000602c  jz      loc_180005D0B
0x180006032  test    byte ptr [rcx+1Ch], 1
0x180006036  jz      loc_180005D0B
0x18000603c  mov     edx, 0B7h
0x180006041  xor     r9d, r9d
0x180006044  jmp     loc_180005CFF
```
