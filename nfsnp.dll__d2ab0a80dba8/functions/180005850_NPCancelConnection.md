# NPCancelConnection

- ea: `0x180005850`
- end: `0x180005c08`
- name: `NPCancelConnection`
- size: `952`
- prototype: `DWORD __stdcall(LPWSTR lpName, BOOL fForce)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x1800023f0`
- `0x180002418`
- `0x180005850`
- `0x180008730`
- `0x1800089d4`
- `0x180008bac`
- `0x18000a92c`
- `0x18000b560`
- `0x18000d5d8`
- `0x180011b62`
- `0x180011ba0`

## import_xrefs

- `msvcrt!towupper` at `0x1800059a4`
- `msvcrt!towupper` at `0x1800059a4`
- `ntdll!RtlAppendUnicodeToString` at `0x180005b1a`
- `ntdll!RtlAppendUnicodeToString` at `0x180005b30`
- `ntdll!RtlAppendUnicodeToString` at `0x180005b44`
- `ntdll!RtlAppendUnicodeToString` at `0x180005b5a`
- `ntdll!RtlAppendUnicodeToString` at `0x180005b1a`
- `ntdll!RtlAppendUnicodeToString` at `0x180005b30`
- `ntdll!RtlAppendUnicodeToString` at `0x180005b44`
- `ntdll!RtlAppendUnicodeToString` at `0x180005b5a`
- `KERNEL32!GetCurrentProcess` at `0x180005aa2`
- `KERNEL32!GetCurrentProcess` at `0x180005aa2`
- `KERNEL32!LocalFree` at `0x180005ba2`
- `KERNEL32!LocalFree` at `0x180005ba2`
- `ADVAPI32!RegDeleteKeyW` at `0x180005b70`
- `ADVAPI32!RegDeleteKeyW` at `0x180005b70`
- `ADVAPI32!ConvertSidToStringSidW` at `0x180005af4`
- `ADVAPI32!ConvertSidToStringSidW` at `0x180005af4`
- `WSOCK32!__imp_WSAStartup` at `0x1800058d9`
- `WSOCK32!__imp_WSAStartup` at `0x1800058d9`
- `WSOCK32!__imp_WSACleanup` at `0x18000597a`
- `WSOCK32!__imp_WSACleanup` at `0x180005bd3`
- `WSOCK32!__imp_WSACleanup` at `0x18000597a`
- `WSOCK32!__imp_WSACleanup` at `0x180005bd3`

## string_xrefs

- `0x180005b4e`: `\Mount`

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
0x180005850  mov     [rsp-8+arg_10], rbx
0x180005855  push    rbp
0x180005856  push    rsi
0x180005857  push    rdi
0x180005858  push    r12
0x18000585a  push    r13
0x18000585c  push    r14
0x18000585e  push    r15
0x180005860  lea     rbp, [rsp-740h]
0x180005868  sub     rsp, 840h
0x18000586f  mov     rax, cs:__security_cookie
0x180005876  xor     rax, rsp
0x180005879  mov     [rbp+770h+var_40], rax
0x180005880  mov     r14d, edx
0x180005883  mov     rdi, rcx
0x180005886  xor     edx, edx; Val
0x180005888  lea     rcx, [rsp+870h+WSAData]; void *
0x18000588d  mov     r8d, 198h; Size
0x180005893  call    memset_0
0x180005898  xor     r15d, r15d
0x18000589b  mov     dword ptr [rsp+870h+Source], r15d
0x1800058a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800058a7  lea     r12, WPP_GLOBAL_Control
0x1800058ae  cmp     rcx, r12
0x1800058b1  jz      short loc_1800058CF
0x1800058b3  test    byte ptr [rcx+1Ch], 1
0x1800058b7  jz      short loc_1800058CF
0x1800058b9  mov     rcx, [rcx+10h]
0x1800058bd  mov     edx, 0B1h
0x1800058c2  mov     r9, rdi
0x1800058c5  mov     [rsp+870h+var_850], r14d
0x1800058ca  call    WPP_SF_Sd
0x1800058cf  mov     ecx, 101h; wVersionRequested
0x1800058d4  lea     rdx, [rsp+870h+WSAData]; lpWSAData
0x1800058d9  call    cs:__imp_WSAStartup
0x1800058df  lea     r13, WPP_f0988aefc7cb3a2e2e93de096c4af5c7_Traceguids
0x1800058e6  test    eax, eax
0x1800058e8  jz      short loc_180005941
0x1800058ea  mov     ebx, 4C6h
0x1800058ef  mov     rcx, cs:WPP_GLOBAL_Control
0x1800058f6  cmp     rcx, r12
0x1800058f9  jz      short loc_180005915
0x1800058fb  test    byte ptr [rcx+1Ch], 2
0x1800058ff  jz      short loc_180005915
0x180005901  mov     edx, 0B8h
0x180005906  mov     r9d, ebx
0x180005909  mov     rcx, [rcx+10h]
0x18000590d  mov     r8, r13
0x180005910  call    WPP_SF_d
0x180005915  mov     eax, ebx
0x180005917  mov     rcx, [rbp+770h+var_40]
0x18000591e  xor     rcx, rsp; StackCookie
0x180005921  call    __security_check_cookie
0x180005926  mov     rbx, [rsp+870h+arg_10]
0x18000592e  add     rsp, 840h
0x180005935  pop     r15
0x180005937  pop     r14
0x180005939  pop     r13
0x18000593b  pop     r12
0x18000593d  pop     rdi
0x18000593e  pop     rsi
0x18000593f  pop     rbp
0x180005940  retn
0x180005941  lea     rcx, [rsp+870h+Source]
0x180005946  call    NfsNpIsClientRunning
0x18000594b  test    eax, eax
0x18000594d  jns     short loc_180005985
0x18000594f  mov     rcx, cs:WPP_GLOBAL_Control
0x180005956  cmp     rcx, r12
0x180005959  jz      short loc_180005975
0x18000595b  test    byte ptr [rcx+1Ch], 2
0x18000595f  jz      short loc_180005975
0x180005961  mov     rcx, [rcx+10h]
0x180005965  mov     edx, 0B2h
0x18000596a  mov     r9d, eax
0x18000596d  mov     r8, r13
0x180005970  call    WPP_SF_d
0x180005975  mov     ebx, 4C6h
0x18000597a  call    cs:__imp_WSACleanup
0x180005980  jmp     loc_1800058EF
0x180005985  movzx   eax, word ptr [rdi]
0x180005988  cmp     ax, 5Ch ; '\'
0x18000598c  jnz     short loc_180005999
0x18000598e  cmp     [rdi+2], ax
0x180005992  jnz     short loc_18000599E
0x180005994  mov     esi, r15d
0x180005997  jmp     short loc_1800059BE
0x180005999  test    ax, ax
0x18000599c  jz      short loc_1800059B9
0x18000599e  mov     rbx, rdi
0x1800059a1  movzx   ecx, ax; C
0x1800059a4  call    cs:__imp_towupper
0x1800059aa  mov     [rbx], ax
0x1800059ad  lea     rbx, [rbx+2]
0x1800059b1  movzx   eax, word ptr [rbx]
0x1800059b4  test    ax, ax
0x1800059b7  jnz     short loc_1800059A1
0x1800059b9  mov     esi, 1
0x1800059be  lea     r9, [rbp+770h+TargetPath]
0x1800059c5  mov     r8, rdi
0x1800059c8  mov     edx, esi
0x1800059ca  mov     ecx, r14d
0x1800059cd  call    DeleteConnection
0x1800059d2  mov     ebx, eax
0x1800059d4  mov     eax, dword ptr [rsp+870h+Source]
0x1800059d8  test    ebx, ebx
0x1800059da  jz      short loc_180005A0E
0x1800059dc  test    eax, eax
0x1800059de  jz      short loc_180005A0B
0x1800059e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800059e7  cmp     rcx, r12
0x1800059ea  jz      short loc_18000597A
0x1800059ec  test    byte ptr [rcx+1Ch], 2
0x1800059f0  jz      short loc_18000597A
0x1800059f2  mov     rcx, [rcx+10h]
0x1800059f6  mov     edx, 0B3h
0x1800059fb  mov     r9d, ebx
0x1800059fe  mov     r8, r13
0x180005a01  call    WPP_SF_d
0x180005a06  jmp     loc_18000597A
0x180005a0b  mov     ebx, r15d
0x180005a0e  test    eax, eax
0x180005a10  jz      short loc_180005A55
0x180005a12  mov     rdx, rdi
0x180005a15  mov     ecx, esi
0x180005a17  call    RemoveDeviceEntry
0x180005a1c  mov     ebx, eax
0x180005a1e  test    eax, eax
0x180005a20  jz      short loc_180005A55
0x180005a22  mov     rcx, cs:WPP_GLOBAL_Control
0x180005a29  cmp     rcx, r12
0x180005a2c  jz      loc_180005BD3
0x180005a32  test    byte ptr [rcx+1Ch], 2
0x180005a36  jz      loc_180005BD3
0x180005a3c  mov     rcx, [rcx+10h]
0x180005a40  mov     edx, 0B4h
0x180005a45  mov     r9d, eax
0x180005a48  mov     r8, r13
0x180005a4b  call    WPP_SF_d
0x180005a50  jmp     loc_180005BD3
0x180005a55  xor     edx, edx; Val
0x180005a57  test    esi, esi
0x180005a59  jz      loc_180005BBA
0x180005a5f  lea     rax, [rbp+770h+var_250]
0x180005a66  mov     qword ptr [rsp+870h+Destination.Length], 2080000h
0x180005a6f  mov     r8d, 220h; Size
0x180005a75  mov     [rsp+870h+Destination.Buffer], rax
0x180005a7a  lea     rcx, [rbp+770h+Sid]; void *
0x180005a81  call    memset_0
0x180005a86  lea     rdx, [rbp+770h+TargetPath]; lpTargetPath
0x180005a8d  mov     [rsp+870h+StringSid], r15
0x180005a92  mov     rcx, rdi; lpDeviceName
0x180005a95  mov     [rbp+770h+var_48], r15w
0x180005a9d  call    RemoveDosDevice
0x180005aa2  call    cs:__imp_GetCurrentProcess
0x180005aa8  lea     rdx, [rbp+770h+Sid]
0x180005aaf  call    DaGetProcessSid
0x180005ab4  test    eax, eax
0x180005ab6  jz      short loc_180005AE8
0x180005ab8  mov     rcx, cs:WPP_GLOBAL_Control
0x180005abf  cmp     rcx, r12
0x180005ac2  jz      loc_180005BD3
0x180005ac8  test    byte ptr [rcx+1Ch], 2
0x180005acc  jz      loc_180005BD3
0x180005ad2  mov     rcx, [rcx+10h]
0x180005ad6  mov     edx, 0B5h
0x180005adb  mov     r8, r13
0x180005ade  call    WPP_SF_
0x180005ae3  jmp     loc_180005BD3
0x180005ae8  lea     rdx, [rsp+870h+StringSid]; StringSid
0x180005aed  lea     rcx, [rbp+770h+Sid]; Sid
0x180005af4  call    cs:__imp_ConvertSidToStringSidW
0x180005afa  test    eax, eax
0x180005afc  jz      loc_180005BD3
0x180005b02  movzx   eax, word ptr [rdi]
0x180005b05  lea     rcx, [rsp+870h+Destination]; Destination
0x180005b0a  mov     rdx, [rsp+870h+StringSid]; Source
0x180005b0f  mov     [rsp+870h+Source], ax
0x180005b14  mov     [rsp+870h+Source+2], r15w
0x180005b1a  call    cs:__imp_RtlAppendUnicodeToString
0x180005b20  test    eax, eax
0x180005b22  js      short loc_180005B9D
0x180005b24  lea     rdx, aNetwork_0; "\\Network\\"
0x180005b2b  lea     rcx, [rsp+870h+Destination]; Destination
0x180005b30  call    cs:__imp_RtlAppendUnicodeToString
0x180005b36  test    eax, eax
0x180005b38  js      short loc_180005B9D
0x180005b3a  lea     rdx, [rsp+870h+Source]; Source
0x180005b3f  lea     rcx, [rsp+870h+Destination]; Destination
0x180005b44  call    cs:__imp_RtlAppendUnicodeToString
0x180005b4a  test    eax, eax
0x180005b4c  js      short loc_180005B9D
0x180005b4e  lea     rdx, aMount; "\\Mount"
0x180005b55  lea     rcx, [rsp+870h+Destination]; Destination
0x180005b5a  call    cs:__imp_RtlAppendUnicodeToString
0x180005b60  test    eax, eax
0x180005b62  js      short loc_180005B9D
0x180005b64  mov     rdx, [rsp+870h+Destination.Buffer]; lpSubKey
0x180005b69  mov     rcx, 0FFFFFFFF80000003h; hKey
0x180005b70  call    cs:__imp_RegDeleteKeyW
0x180005b76  test    eax, eax
0x180005b78  jz      short loc_180005B9D
0x180005b7a  mov     rcx, cs:WPP_GLOBAL_Control
0x180005b81  cmp     rcx, r12
0x180005b84  jz      short loc_180005B9D
0x180005b86  test    byte ptr [rcx+1Ch], 2
0x180005b8a  jz      short loc_180005B9D
0x180005b8c  mov     rcx, [rcx+10h]
0x180005b90  mov     edx, 0B6h
0x180005b95  mov     r8, r13
0x180005b98  call    WPP_SF_
0x180005b9d  mov     rcx, [rsp+870h+StringSid]; hMem
0x180005ba2  call    cs:__imp_LocalFree
0x180005ba8  jmp     short loc_180005BD3
0x180005baa  mov     rdx, rdi
0x180005bad  xor     ecx, ecx
0x180005baf  call    RemoveDeviceEntry
0x180005bb4  test    eax, eax
0x180005bb6  jnz     short loc_180005BD0
0x180005bb8  xor     edx, edx
0x180005bba  lea     r9, [rbp+770h+TargetPath]
0x180005bc1  mov     r8, rdi
0x180005bc4  mov     ecx, r14d
0x180005bc7  call    DeleteConnection
0x180005bcc  test    eax, eax
0x180005bce  jz      short loc_180005BAA
0x180005bd0  mov     ebx, r15d
0x180005bd3  call    cs:__imp_WSACleanup
0x180005bd9  test    ebx, ebx
0x180005bdb  jnz     loc_1800058EF
0x180005be1  mov     rcx, cs:WPP_GLOBAL_Control
0x180005be8  cmp     rcx, r12
0x180005beb  jz      loc_180005915
0x180005bf1  test    byte ptr [rcx+1Ch], 1
0x180005bf5  jz      loc_180005915
0x180005bfb  mov     edx, 0B7h
0x180005c00  xor     r9d, r9d
0x180005c03  jmp     loc_180005909
```
