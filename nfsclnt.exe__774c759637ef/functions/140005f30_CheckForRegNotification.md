# CheckForRegNotification

- ea: `0x140005f30`
- end: `0x140006425`
- name: `CheckForRegNotification`
- size: `1269`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140002bd8`
- `0x140002c00`
- `0x140005f30`
- `0x1400065b0`
- `0x1400100f0`
- `0x140018350`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140005fc5`
- `ADVAPI32!RegOpenKeyExW` at `0x14000600c`
- `ADVAPI32!RegOpenKeyExW` at `0x140005fc5`
- `ADVAPI32!RegOpenKeyExW` at `0x14000600c`
- `ADVAPI32!RegCloseKey` at `0x140006147`
- `ADVAPI32!RegCloseKey` at `0x140006160`
- `ADVAPI32!RegCloseKey` at `0x1400063be`
- `ADVAPI32!RegCloseKey` at `0x1400063cd`
- `ADVAPI32!RegCloseKey` at `0x140006147`
- `ADVAPI32!RegCloseKey` at `0x140006160`
- `ADVAPI32!RegCloseKey` at `0x1400063be`
- `ADVAPI32!RegCloseKey` at `0x1400063cd`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x1400060c8`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x140006100`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x140006279`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x14000634a`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x1400060c8`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x140006100`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x140006279`
- `ADVAPI32!RegNotifyChangeKeyValue` at `0x14000634a`
- `KERNEL32!GetLastError` at `0x14000639c`
- `KERNEL32!GetLastError` at `0x14000639c`
- `KERNEL32!CreateEventW` at `0x140006044`
- `KERNEL32!CreateEventW` at `0x140006081`
- `KERNEL32!CreateEventW` at `0x140006044`
- `KERNEL32!CreateEventW` at `0x140006081`
- `KERNEL32!WaitForMultipleObjects` at `0x1400061d9`
- `KERNEL32!WaitForMultipleObjects` at `0x1400061d9`
- `KERNEL32!CloseHandle` at `0x140006175`
- `KERNEL32!CloseHandle` at `0x14000618a`
- `KERNEL32!CloseHandle` at `0x1400063d6`
- `KERNEL32!CloseHandle` at `0x1400063df`
- `KERNEL32!CloseHandle` at `0x140006175`
- `KERNEL32!CloseHandle` at `0x14000618a`
- `KERNEL32!CloseHandle` at `0x1400063d6`
- `KERNEL32!CloseHandle` at `0x1400063df`
- `KERNEL32!ResetEvent` at `0x14000625e`
- `KERNEL32!ResetEvent` at `0x14000632f`
- `KERNEL32!ResetEvent` at `0x14000625e`
- `KERNEL32!ResetEvent` at `0x14000632f`

## string_xrefs

- `0x140006002`: `SOFTWARE\Microsoft\ServicesForNFS`

## pseudocode

```c
__int64 __fastcall CheckForRegNotification(PVOID Parameter)
{
  HANDLE EventW; // rsi
  HANDLE v2; // rdi
  unsigned int v3; // eax
  _BYTE *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // r9
  __int64 v7; // rdx
  char v8; // bl
  DWORD v9; // eax
  unsigned int v10; // eax
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // rbx
  DWORD LastError; // eax
  HKEY hKey; // [rsp+30h] [rbp-30h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-28h] BYREF
  HANDLE Handles[2]; // [rsp+40h] [rbp-20h] BYREF
  HANDLE v19; // [rsp+50h] [rbp-10h]

  EventW = 0;
  hKey = 0;
  v2 = 0;
  phkResult = 0;
  v19 = 0;
  *(_OWORD *)Handles = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids);
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Default\\RegNotify",
         0,
         0x20019u,
         &hKey);
  if ( v3 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v5 = 53;
LABEL_29:
      v6 = v3;
      goto LABEL_30;
    }
    goto LABEL_31;
  }
  v3 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\ServicesForNFS", 0, 0x20019u, &phkResult);
  if ( v3 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v5 = 54;
      goto LABEL_29;
    }
LABEL_31:
    if ( hKey )
    {
      RegCloseKey(hKey);
      v4 = WPP_GLOBAL_Control;
    }
    if ( phkResult )
    {
      RegCloseKey(phkResult);
      v4 = WPP_GLOBAL_Control;
    }
    if ( EventW )
    {
      CloseHandle(EventW);
      v4 = WPP_GLOBAL_Control;
    }
    if ( v2 )
    {
      CloseHandle(v2);
      v4 = WPP_GLOBAL_Control;
    }
    if ( v4 != (_BYTE *)&WPP_GLOBAL_Control && (v4[28] & 8) != 0 )
    {
      v7 = 68;
      goto LABEL_86;
    }
    return 0;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  if ( !EventW )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_31;
    v5 = 55;
    goto LABEL_16;
  }
  v2 = CreateEventW(0, 0, 0, 0);
  if ( !v2 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_31;
    v5 = 56;
LABEL_16:
    v6 = 0;
LABEL_30:
    WPP_SF_d(*((_QWORD *)v4 + 2), v5, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids, v6);
    v4 = WPP_GLOBAL_Control;
    goto LABEL_31;
  }
  v3 = RegNotifyChangeKeyValue(hKey, 1, 5u, EventW, 1);
  if ( v3 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v5 = 57;
      goto LABEL_29;
    }
    goto LABEL_31;
  }
  v3 = RegNotifyChangeKeyValue(phkResult, 1, 5u, v2, 1);
  if ( v3 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v5 = 58;
      goto LABEL_29;
    }
    goto LABEL_31;
  }
  v8 = 1;
  Handles[0] = g_hShutdownEvent;
  Handles[1] = EventW;
  v19 = v2;
  while ( 1 )
  {
    v9 = WaitForMultipleObjects(3u, Handles, 0, 0xFFFFFFFF);
    if ( v9 == -1 )
      break;
    if ( !v9 )
      goto LABEL_79;
    if ( v9 == 1 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids);
      if ( !(unsigned int)SendIoctlToDriver(0x14C848u)
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids);
      }
      if ( !(unsigned int)SendIoctlToDriver(0x14C844u)
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 62, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids);
      }
      ResetEvent(EventW);
      v10 = RegNotifyChangeKeyValue(hKey, 1, 5u, EventW, 1);
      if ( !v10 )
        goto LABEL_74;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_73;
      v12 = 63;
      goto LABEL_72;
    }
    if ( v9 != 2 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 66, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids, v9);
      goto LABEL_74;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids);
    NfsLdapRfc2307ChangeNotification();
    ResetEvent(v2);
    v10 = RegNotifyChangeKeyValue(phkResult, 1, 5u, v2, 1);
    if ( !v10 )
      goto LABEL_74;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v12 = 65;
LABEL_72:
      WPP_SF_d(v11[2], v12, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids, v10);
    }
LABEL_73:
    v8 = 0;
LABEL_74:
    if ( !v8 )
      goto LABEL_79;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    v13 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    LastError = GetLastError();
    WPP_SF_d(v13, 59, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids, LastError);
  }
LABEL_79:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  CloseHandle(EventW);
  CloseHandle(v2);
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    v7 = 67;
LABEL_86:
    WPP_SF_(*((_QWORD *)v4 + 2), v7, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x140005f30  push    rbp
0x140005f32  push    rbx
0x140005f33  push    rsi
0x140005f34  push    rdi
0x140005f35  push    r12
0x140005f37  push    r14
0x140005f39  push    r15
0x140005f3b  mov     rbp, rsp
0x140005f3e  sub     rsp, 60h
0x140005f42  mov     rax, cs:__security_cookie
0x140005f49  xor     rax, rsp
0x140005f4c  mov     [rbp+var_8], rax
0x140005f50  xor     esi, esi
0x140005f52  mov     [rbp+hKey], 0
0x140005f5a  xor     edi, edi
0x140005f5c  mov     [rbp+var_28], 0
0x140005f64  xor     eax, eax
0x140005f66  xorps   xmm0, xmm0
0x140005f69  mov     [rbp+var_10], rax
0x140005f6d  movups  xmmword ptr [rbp+Handles], xmm0
0x140005f71  mov     rcx, cs:WPP_GLOBAL_Control
0x140005f78  lea     r14, WPP_GLOBAL_Control
0x140005f7f  lea     r15, WPP_6982ecdaab8237b4b8a840ed8e59f977_Traceguids
0x140005f86  cmp     rcx, r14
0x140005f89  jz      short loc_140005FA0
0x140005f8b  test    byte ptr [rcx+1Ch], 8
0x140005f8f  jz      short loc_140005FA0
0x140005f91  mov     rcx, [rcx+10h]
0x140005f95  lea     edx, [rsi+34h]
0x140005f98  mov     r8, r15
0x140005f9b  call    WPP_SF_
0x140005fa0  lea     rax, [rbp+hKey]
0x140005fa4  mov     ebx, 20019h
0x140005fa9  mov     r12, 0FFFFFFFF80000002h
0x140005fb0  mov     [rsp+60h+phkResult], rax; phkResult
0x140005fb5  mov     r9d, ebx; samDesired
0x140005fb8  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x140005fbf  mov     rcx, r12; hKey
0x140005fc2  xor     r8d, r8d; ulOptions
0x140005fc5  call    cs:__imp_RegOpenKeyExW
0x140005fcb  test    eax, eax
0x140005fcd  jz      short loc_140005FF3
0x140005fcf  mov     rcx, cs:WPP_GLOBAL_Control
0x140005fd6  cmp     rcx, r14
0x140005fd9  jz      loc_14000613B
0x140005fdf  test    byte ptr [rcx+1Ch], 2
0x140005fe3  jz      loc_14000613B
0x140005fe9  mov     edx, 35h ; '5'
0x140005fee  jmp     loc_140006125
0x140005ff3  lea     rax, [rbp+var_28]
0x140005ff7  mov     r9d, ebx; samDesired
0x140005ffa  xor     r8d, r8d; ulOptions
0x140005ffd  mov     [rsp+60h+phkResult], rax; phkResult
0x140006002  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\ServicesForNFS"
0x140006009  mov     rcx, r12; hKey
0x14000600c  call    cs:__imp_RegOpenKeyExW
0x140006012  test    eax, eax
0x140006014  jz      short loc_14000603A
0x140006016  mov     rcx, cs:WPP_GLOBAL_Control
0x14000601d  cmp     rcx, r14
0x140006020  jz      loc_14000613B
0x140006026  test    byte ptr [rcx+1Ch], 2
0x14000602a  jz      loc_14000613B
0x140006030  mov     edx, 36h ; '6'
0x140006035  jmp     loc_140006125
0x14000603a  xor     r9d, r9d; lpName
0x14000603d  xor     r8d, r8d; bInitialState
0x140006040  xor     edx, edx; bManualReset
0x140006042  xor     ecx, ecx; lpEventAttributes
0x140006044  call    cs:__imp_CreateEventW
0x14000604a  mov     rsi, rax
0x14000604d  test    rax, rax
0x140006050  jnz     short loc_140006077
0x140006052  mov     rcx, cs:WPP_GLOBAL_Control
0x140006059  cmp     rcx, r14
0x14000605c  jz      loc_14000613B
0x140006062  test    byte ptr [rcx+1Ch], 2
0x140006066  jz      loc_14000613B
0x14000606c  lea     edx, [rax+37h]
0x14000606f  xor     r9d, r9d
0x140006072  jmp     loc_140006128
0x140006077  xor     r9d, r9d; lpName
0x14000607a  xor     r8d, r8d; bInitialState
0x14000607d  xor     edx, edx; bManualReset
0x14000607f  xor     ecx, ecx; lpEventAttributes
0x140006081  call    cs:__imp_CreateEventW
0x140006087  mov     rdi, rax
0x14000608a  test    rax, rax
0x14000608d  jnz     short loc_1400060AE
0x14000608f  mov     rcx, cs:WPP_GLOBAL_Control
0x140006096  cmp     rcx, r14
0x140006099  jz      loc_14000613B
0x14000609f  test    byte ptr [rcx+1Ch], 2
0x1400060a3  jz      loc_14000613B
0x1400060a9  lea     edx, [rax+38h]
0x1400060ac  jmp     short loc_14000606F
0x1400060ae  mov     rcx, [rbp+hKey]; hKey
0x1400060b2  mov     r12d, 1
0x1400060b8  mov     r9, rsi; hEvent
0x1400060bb  mov     dword ptr [rsp+60h+phkResult], r12d; fAsynchronous
0x1400060c0  mov     edx, r12d; bWatchSubtree
0x1400060c3  lea     r8d, [r12+4]; dwNotifyFilter
0x1400060c8  call    cs:__imp_RegNotifyChangeKeyValue
0x1400060ce  test    eax, eax
0x1400060d0  jz      short loc_1400060EB
0x1400060d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400060d9  cmp     rcx, r14
0x1400060dc  jz      short loc_14000613B
0x1400060de  test    byte ptr [rcx+1Ch], 2
0x1400060e2  jz      short loc_14000613B
0x1400060e4  lea     edx, [r12+38h]
0x1400060e9  jmp     short loc_140006125
0x1400060eb  mov     rcx, [rbp+var_28]; hKey
0x1400060ef  mov     r9, rdi; hEvent
0x1400060f2  mov     r8d, 5; dwNotifyFilter
0x1400060f8  mov     dword ptr [rsp+60h+phkResult], r12d; fAsynchronous
0x1400060fd  mov     edx, r12d; bWatchSubtree
0x140006100  call    cs:__imp_RegNotifyChangeKeyValue
0x140006106  test    eax, eax
0x140006108  jz      loc_1400061B4
0x14000610e  mov     rcx, cs:WPP_GLOBAL_Control
0x140006115  cmp     rcx, r14
0x140006118  jz      short loc_14000613B
0x14000611a  test    byte ptr [rcx+1Ch], 2
0x14000611e  jz      short loc_14000613B
0x140006120  mov     edx, 3Ah ; ':'
0x140006125  mov     r9d, eax
0x140006128  mov     rcx, [rcx+10h]
0x14000612c  mov     r8, r15
0x14000612f  call    WPP_SF_d
0x140006134  mov     rcx, cs:WPP_GLOBAL_Control
0x14000613b  mov     rax, [rbp+hKey]
0x14000613f  test    rax, rax
0x140006142  jz      short loc_140006154
0x140006144  mov     rcx, rax; hKey
0x140006147  call    cs:__imp_RegCloseKey
0x14000614d  mov     rcx, cs:WPP_GLOBAL_Control
0x140006154  mov     rax, [rbp+var_28]
0x140006158  test    rax, rax
0x14000615b  jz      short loc_14000616D
0x14000615d  mov     rcx, rax; hKey
0x140006160  call    cs:__imp_RegCloseKey
0x140006166  mov     rcx, cs:WPP_GLOBAL_Control
0x14000616d  test    rsi, rsi
0x140006170  jz      short loc_140006182
0x140006172  mov     rcx, rsi; hObject
0x140006175  call    cs:__imp_CloseHandle
0x14000617b  mov     rcx, cs:WPP_GLOBAL_Control
0x140006182  test    rdi, rdi
0x140006185  jz      short loc_140006197
0x140006187  mov     rcx, rdi; hObject
0x14000618a  call    cs:__imp_CloseHandle
0x140006190  mov     rcx, cs:WPP_GLOBAL_Control
0x140006197  cmp     rcx, r14
0x14000619a  jz      loc_140006408
0x1400061a0  test    byte ptr [rcx+1Ch], 8
0x1400061a4  jz      loc_140006408
0x1400061aa  mov     edx, 44h ; 'D'
0x1400061af  jmp     loc_1400063FC
0x1400061b4  mov     rax, cs:g_hShutdownEvent
0x1400061bb  mov     bl, r12b
0x1400061be  mov     [rbp+Handles], rax
0x1400061c2  mov     [rbp+Handles+8], rsi
0x1400061c6  mov     [rbp+var_10], rdi
0x1400061ca  xor     r8d, r8d; bWaitAll
0x1400061cd  lea     rdx, [rbp+Handles]; lpHandles
0x1400061d1  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1400061d5  lea     ecx, [r8+3]; nCount
0x1400061d9  call    cs:__imp_WaitForMultipleObjects
0x1400061df  cmp     eax, 0FFFFFFFFh
0x1400061e2  jz      loc_140006386
0x1400061e8  mov     ecx, eax
0x1400061ea  test    eax, eax
0x1400061ec  jz      loc_1400063B5
0x1400061f2  sub     ecx, r12d
0x1400061f5  jz      loc_1400062AB
0x1400061fb  cmp     ecx, r12d
0x1400061fe  jz      short loc_140006233
0x140006200  mov     rcx, cs:WPP_GLOBAL_Control
0x140006207  cmp     rcx, r14
0x14000620a  jz      loc_14000637C
0x140006210  test    byte ptr [rcx+1Ch], 2
0x140006214  jz      loc_14000637C
0x14000621a  mov     rcx, [rcx+10h]
0x14000621e  mov     edx, 42h ; 'B'
0x140006223  mov     r9d, eax
0x140006226  mov     r8, r15
0x140006229  call    WPP_SF_d
0x14000622e  jmp     loc_14000637C
0x140006233  mov     rcx, cs:WPP_GLOBAL_Control
0x14000623a  cmp     rcx, r14
0x14000623d  jz      short loc_140006256
0x14000623f  test    byte ptr [rcx+1Ch], 8
0x140006243  jz      short loc_140006256
0x140006245  mov     rcx, [rcx+10h]
0x140006249  mov     edx, 40h ; '@'
0x14000624e  mov     r8, r15
0x140006251  call    WPP_SF_
0x140006256  call    NfsLdapRfc2307ChangeNotification
0x14000625b  mov     rcx, rdi; hEvent
0x14000625e  call    cs:__imp_ResetEvent
0x140006264  mov     rcx, [rbp+var_28]; hKey
0x140006268  mov     r9, rdi; hEvent
0x14000626b  mov     r8d, 5; dwNotifyFilter
0x140006271  mov     dword ptr [rsp+60h+phkResult], r12d; fAsynchronous
0x140006276  mov     edx, r12d; bWatchSubtree
0x140006279  call    cs:__imp_RegNotifyChangeKeyValue
0x14000627f  test    eax, eax
0x140006281  jz      loc_14000637C
0x140006287  mov     rcx, cs:WPP_GLOBAL_Control
0x14000628e  cmp     rcx, r14
0x140006291  jz      loc_14000637A
0x140006297  test    byte ptr [rcx+1Ch], 2
0x14000629b  jz      loc_14000637A
0x1400062a1  mov     edx, 41h ; 'A'
0x1400062a6  jmp     loc_14000636B
0x1400062ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1400062b2  cmp     rcx, r14
0x1400062b5  jz      short loc_1400062CE
0x1400062b7  test    byte ptr [rcx+1Ch], 8
0x1400062bb  jz      short loc_1400062CE
0x1400062bd  mov     rcx, [rcx+10h]
0x1400062c1  mov     edx, 3Ch ; '<'
0x1400062c6  mov     r8, r15
0x1400062c9  call    WPP_SF_
0x1400062ce  mov     ecx, 14C848h; dwIoControlCode
0x1400062d3  call    SendIoctlToDriver
0x1400062d8  test    eax, eax
0x1400062da  jnz     short loc_1400062FD
0x1400062dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400062e3  cmp     rcx, r14
0x1400062e6  jz      short loc_1400062FD
0x1400062e8  test    byte ptr [rcx+1Ch], 2
0x1400062ec  jz      short loc_1400062FD
0x1400062ee  mov     rcx, [rcx+10h]
0x1400062f2  lea     edx, [rax+3Dh]
0x1400062f5  mov     r8, r15
0x1400062f8  call    WPP_SF_
0x1400062fd  mov     ecx, 14C844h; dwIoControlCode
0x140006302  call    SendIoctlToDriver
0x140006307  test    eax, eax
0x140006309  jnz     short loc_14000632C
0x14000630b  mov     rcx, cs:WPP_GLOBAL_Control
0x140006312  cmp     rcx, r14
0x140006315  jz      short loc_14000632C
0x140006317  test    byte ptr [rcx+1Ch], 2
0x14000631b  jz      short loc_14000632C
0x14000631d  mov     rcx, [rcx+10h]
0x140006321  lea     edx, [rax+3Eh]
0x140006324  mov     r8, r15
0x140006327  call    WPP_SF_
0x14000632c  mov     rcx, rsi; hEvent
0x14000632f  call    cs:__imp_ResetEvent
0x140006335  mov     rcx, [rbp+hKey]; hKey
0x140006339  mov     r9, rsi; hEvent
0x14000633c  mov     r8d, 5; dwNotifyFilter
0x140006342  mov     dword ptr [rsp+60h+phkResult], r12d; fAsynchronous
0x140006347  mov     edx, r12d; bWatchSubtree
0x14000634a  call    cs:__imp_RegNotifyChangeKeyValue
0x140006350  test    eax, eax
0x140006352  jz      short loc_14000637C
0x140006354  mov     rcx, cs:WPP_GLOBAL_Control
0x14000635b  cmp     rcx, r14
0x14000635e  jz      short loc_14000637A
0x140006360  test    byte ptr [rcx+1Ch], 2
0x140006364  jz      short loc_14000637A
0x140006366  mov     edx, 3Fh ; '?'
0x14000636b  mov     rcx, [rcx+10h]
0x14000636f  mov     r9d, eax
0x140006372  mov     r8, r15
0x140006375  call    WPP_SF_d
0x14000637a  xor     bl, bl
0x14000637c  test    bl, bl
0x14000637e  jnz     loc_1400061CA
0x140006384  jmp     short loc_1400063B5
0x140006386  mov     rbx, cs:WPP_GLOBAL_Control
0x14000638d  cmp     rbx, r14
0x140006390  jz      short loc_1400063B5
0x140006392  test    byte ptr [rbx+1Ch], 2
0x140006396  jz      short loc_1400063B5
0x140006398  mov     rbx, [rbx+10h]
0x14000639c  call    cs:__imp_GetLastError
0x1400063a2  mov     edx, 3Bh ; ';'
0x1400063a7  mov     r8, r15
0x1400063aa  mov     r9d, eax
0x1400063ad  mov     rcx, rbx
0x1400063b0  call    WPP_SF_d
0x1400063b5  mov     rcx, [rbp+hKey]; hKey
0x1400063b9  test    rcx, rcx
0x1400063bc  jz      short loc_1400063C4
0x1400063be  call    cs:__imp_RegCloseKey
0x1400063c4  mov     rcx, [rbp+var_28]; hKey
0x1400063c8  test    rcx, rcx
0x1400063cb  jz      short loc_1400063D3
0x1400063cd  call    cs:__imp_RegCloseKey
0x1400063d3  mov     rcx, rsi; hObject
0x1400063d6  call    cs:__imp_CloseHandle
0x1400063dc  mov     rcx, rdi; hObject
0x1400063df  call    cs:__imp_CloseHandle
0x1400063e5  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
