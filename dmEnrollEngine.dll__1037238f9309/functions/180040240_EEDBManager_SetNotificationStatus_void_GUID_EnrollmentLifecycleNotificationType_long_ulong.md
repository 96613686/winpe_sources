# EEDBManager::SetNotificationStatus(void *,_GUID,EnrollmentLifecycleNotificationType,long,ulong)

- ea: `0x180040240`
- end: `0x1800404a2`
- name: `?SetNotificationStatus@EEDBManager@@QEAAJPEAXU_GUID@@W4EnrollmentLifecycleNotificationType@@JK@Z`
- size: `610`
- prototype: `int __high(void *, struct _GUID, enum EnrollmentLifecycleNotificationType, int, unsigned int)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001a9dc`
- `0x180037810`

## callees

- `0x180005cf0`
- `0x1800067a0`
- `0x1800071c0`
- `0x18002e1a0`
- `0x18002ec8c`
- `0x180040240`
- `0x1800404a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004046d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18004046d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800402e4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040328`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040361`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040430`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040457`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800402e4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040328`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040361`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040430`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180040457`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004047d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004047d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180040378`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180040378`

## pseudocode

```c
__int64 __fastcall EEDBManager::SetNotificationStatus(__int64 a1, void *a2, struct _SYSTEMTIME *a3, int a4, int a5)
{
  signed int v7; // edi
  LSTATUS v8; // eax
  bool v9; // cc
  BYTE *lpData; // [rsp+20h] [rbp-E0h]
  __int64 cbData; // [rsp+28h] [rbp-D8h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[8]; // [rsp+58h] [rbp-A8h] BYREF
  BYTE v15[8]; // [rsp+60h] [rbp-A0h] BYREF
  DWORD v16[2]; // [rsp+68h] [rbp-98h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 v18[264]; // [rsp+80h] [rbp-80h] BYREF

  *(_DWORD *)Data = a4;
  *(_DWORD *)v15 = 0;
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  SystemTime = *a3;
  v7 = EEDBManager::OpenEnrollmentKey((struct _GUID *)&SystemTime, 0x2001Fu, L"Status", &hKey);
  if ( v7 < 0 )
    goto LABEL_15;
  v8 = RegSetValueExW(hKey, L"LifecycleNotificationStatus", 0, 4u, Data, 4u);
  v9 = v8 <= 0;
  if ( v8 )
    goto LABEL_3;
  v8 = RegSetValueExW(hKey, L"LifecycleNotificationHResult", 0, 4u, (const BYTE *)&a5, 4u);
  v9 = v8 <= 0;
  if ( v8 )
    goto LABEL_3;
  if ( a5 < 0 )
  {
    v8 = RegSetValueExW(hKey, L"LifecycleNotificationLastFailure", 0, 4u, (const BYTE *)&a5, 4u);
    v9 = v8 <= 0;
    if ( v8 )
      goto LABEL_3;
    SystemTime = 0;
    GetSystemTime(&SystemTime);
    memset_0(v18, 0, 0x208u);
    LODWORD(cbData) = SystemTime.wDay;
    LODWORD(lpData) = SystemTime.wMonth;
    if ( (int)StringCchPrintfW(
                v18,
                0x104u,
                L"%d-%02d-%02d %02d:%02d:%02d.%03d",
                SystemTime.wYear,
                lpData,
                cbData,
                SystemTime.wHour,
                SystemTime.wMinute,
                SystemTime.wSecond,
                SystemTime.wMilliseconds) >= 0 )
    {
      *(_QWORD *)v16 = 0;
      if ( (int)StringCbLengthW(v18, 0x208u, (unsigned __int64 *)v16) >= 0 )
        RegSetValueExW(hKey, L"Time", 0, 1u, (const BYTE *)v18, v16[0]);
    }
  }
  v8 = RegSetValueExW(hKey, L"LifecycleNotificationProgress", 0, 4u, v15, 4u);
  v9 = v8 <= 0;
  if ( v8 )
  {
LABEL_3:
    if ( v9 )
      v7 = v8;
    else
      v7 = (unsigned __int16)v8 | 0x80070000;
    goto LABEL_15;
  }
  if ( a2 )
    SetEvent(a2);
LABEL_15:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180040240  push    rbp
0x180040242  push    rbx
0x180040243  push    rsi
0x180040244  push    rdi
0x180040245  push    r15
0x180040247  lea     rbp, [rsp-1A0h]
0x18004024f  sub     rsp, 2A0h
0x180040256  mov     rax, cs:__security_cookie
0x18004025d  xor     rax, rsp
0x180040260  mov     [rbp+1C0h+var_30], rax
0x180040267  mov     rsi, rdx
0x18004026a  mov     dword ptr [rsp+2C0h+Data], r9d
0x18004026f  xor     edx, edx
0x180040271  mov     dword ptr [rsp+2C0h+var_260], 0
0x180040279  lea     rcx, [rsp+2C0h+hKey]
0x18004027e  mov     [rsp+2C0h+hKey], 0
0x180040287  mov     rbx, r8
0x18004028a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18004028f  movaps  xmm0, xmmword ptr [rbx]
0x180040292  lea     r9, [rsp+2C0h+hKey]; HKEY *
0x180040297  lea     r8, aStatus; "Status"
0x18004029e  movdqa  xmmword ptr [rsp+2C0h+SystemTime.wYear], xmm0
0x1800402a4  mov     edx, 2001Fh; unsigned int
0x1800402a9  lea     rcx, [rsp+2C0h+SystemTime]; struct _GUID
0x1800402ae  call    ?OpenEnrollmentKey@EEDBManager@@CAJU_GUID@@KPEBGPEAPEAUHKEY__@@@Z; EEDBManager::OpenEnrollmentKey(_GUID,ulong,ushort const *,HKEY__ * *)
0x1800402b3  mov     edi, eax
0x1800402b5  test    eax, eax
0x1800402b7  js      loc_180040473
0x1800402bd  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1800402c2  lea     rax, [rsp+2C0h+Data]
0x1800402c7  mov     r15d, 4
0x1800402cd  lea     rdx, aLifecyclenotif_2; "LifecycleNotificationStatus"
0x1800402d4  mov     dword ptr [rsp+2C0h+cbData], r15d; cbData
0x1800402d9  mov     r9d, r15d; dwType
0x1800402dc  xor     r8d, r8d; Reserved
0x1800402df  mov     [rsp+2C0h+lpData], rax; lpData
0x1800402e4  call    cs:__imp_RegSetValueExW
0x1800402ea  test    eax, eax
0x1800402ec  jz      short loc_180040305
0x1800402ee  jg      short loc_1800402F7
0x1800402f0  mov     edi, eax
0x1800402f2  jmp     loc_180040473
0x1800402f7  movzx   edi, ax
0x1800402fa  or      edi, 80070000h
0x180040300  jmp     loc_180040473
0x180040305  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18004030a  lea     rax, [rbp+1C0h+arg_20]
0x180040311  mov     dword ptr [rsp+2C0h+cbData], r15d; cbData
0x180040316  lea     rdx, aLifecyclenotif_0; "LifecycleNotificationHResult"
0x18004031d  mov     r9d, r15d; dwType
0x180040320  mov     [rsp+2C0h+lpData], rax; lpData
0x180040325  xor     r8d, r8d; Reserved
0x180040328  call    cs:__imp_RegSetValueExW
0x18004032e  test    eax, eax
0x180040330  jnz     short loc_1800402EE
0x180040332  cmp     [rbp+1C0h+arg_20], eax
0x180040338  jge     loc_180040436
0x18004033e  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180040343  lea     rax, [rbp+1C0h+arg_20]
0x18004034a  mov     dword ptr [rsp+2C0h+cbData], r15d; cbData
0x18004034f  lea     rdx, aLifecyclenotif; "LifecycleNotificationLastFailure"
0x180040356  mov     r9d, r15d; dwType
0x180040359  mov     [rsp+2C0h+lpData], rax; lpData
0x18004035e  xor     r8d, r8d; Reserved
0x180040361  call    cs:__imp_RegSetValueExW
0x180040367  test    eax, eax
0x180040369  jnz     short loc_1800402EE
0x18004036b  xorps   xmm0, xmm0
0x18004036e  lea     rcx, [rsp+2C0h+SystemTime]; lpSystemTime
0x180040373  movups  xmmword ptr [rsp+2C0h+SystemTime.wYear], xmm0
0x180040378  call    cs:__imp_GetSystemTime
0x18004037e  xor     edx, edx; Val
0x180040380  lea     rcx, [rbp+1C0h+var_240]; void *
0x180040384  mov     r8d, 208h; Size
0x18004038a  call    memset_0
0x18004038f  movzx   ecx, [rsp+2C0h+SystemTime.wSecond]
0x180040394  mov     edx, 104h; unsigned __int64
0x180040399  movzx   r8d, [rsp+2C0h+SystemTime.wMinute]
0x18004039f  movzx   eax, [rsp+2C0h+SystemTime.wMilliseconds]
0x1800403a4  movzx   r10d, [rsp+2C0h+SystemTime.wHour]
0x1800403aa  movzx   r11d, [rsp+2C0h+SystemTime.wDay]
0x1800403b0  movzx   ebx, [rsp+2C0h+SystemTime.wMonth]
0x1800403b5  movzx   r9d, [rsp+2C0h+SystemTime.wYear]
0x1800403bb  mov     [rsp+2C0h+var_278], eax
0x1800403bf  mov     [rsp+2C0h+var_280], ecx
0x1800403c3  lea     rcx, [rbp+1C0h+var_240]; unsigned __int16 *
0x1800403c7  mov     [rsp+2C0h+var_288], r8d
0x1800403cc  lea     r8, aD02d02d02d02d0; "%d-%02d-%02d %02d:%02d:%02d.%03d"
0x1800403d3  mov     [rsp+2C0h+var_290], r10d
0x1800403d8  mov     dword ptr [rsp+2C0h+cbData], r11d
0x1800403dd  mov     dword ptr [rsp+2C0h+lpData], ebx
0x1800403e1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800403e6  test    eax, eax
0x1800403e8  js      short loc_180040436
0x1800403ea  lea     r8, [rsp+2C0h+var_258]; unsigned __int64 *
0x1800403ef  mov     qword ptr [rsp+2C0h+var_258], 0
0x1800403f8  mov     edx, 208h; unsigned __int64
0x1800403fd  lea     rcx, [rbp+1C0h+var_240]; unsigned __int16 *
0x180040401  call    ?StringCbLengthW@@YAJPEBG_KPEA_K@Z; StringCbLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180040406  test    eax, eax
0x180040408  js      short loc_180040436
0x18004040a  mov     eax, [rsp+2C0h+var_258]
0x18004040e  lea     rdx, aTime; "Time"
0x180040415  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18004041a  mov     r9d, 1; dwType
0x180040420  mov     dword ptr [rsp+2C0h+cbData], eax; cbData
0x180040424  xor     r8d, r8d; Reserved
0x180040427  lea     rax, [rbp+1C0h+var_240]
0x18004042b  mov     [rsp+2C0h+lpData], rax; lpData
0x180040430  call    cs:__imp_RegSetValueExW
0x180040436  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18004043b  lea     rax, [rsp+2C0h+var_260]
0x180040440  mov     dword ptr [rsp+2C0h+cbData], r15d; cbData
0x180040445  lea     rdx, aLifecyclenotif_1; "LifecycleNotificationProgress"
0x18004044c  mov     r9d, r15d; dwType
0x18004044f  mov     [rsp+2C0h+lpData], rax; lpData
0x180040454  xor     r8d, r8d; Reserved
0x180040457  call    cs:__imp_RegSetValueExW
0x18004045d  test    eax, eax
0x18004045f  jnz     loc_1800402EE
0x180040465  test    rsi, rsi
0x180040468  jz      short loc_180040473
0x18004046a  mov     rcx, rsi; hEvent
0x18004046d  call    cs:__imp_SetEvent
0x180040473  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180040478  test    rcx, rcx
0x18004047b  jz      short loc_180040483
0x18004047d  call    cs:__imp_RegCloseKey
0x180040483  mov     eax, edi
0x180040485  mov     rcx, [rbp+1C0h+var_30]
0x18004048c  xor     rcx, rsp; StackCookie
0x18004048f  call    __security_check_cookie
0x180040494  add     rsp, 2A0h
0x18004049b  pop     r15
0x18004049d  pop     rdi
0x18004049e  pop     rsi
0x18004049f  pop     rbx
0x1800404a0  pop     rbp
0x1800404a1  retn
```
