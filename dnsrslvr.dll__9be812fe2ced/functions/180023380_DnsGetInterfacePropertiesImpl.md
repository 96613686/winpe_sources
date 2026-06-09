# DnsGetInterfacePropertiesImpl

- ea: `0x180023380`
- end: `0x180023751`
- name: `DnsGetInterfacePropertiesImpl`
- size: `977`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, HKEY@<rdx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023080`

## callees

- `0x180023380`
- `0x180023760`
- `0x180023a50`
- `0x180023aac`
- `0x180040cd4`
- `0x180046ec0`
- `0x180079518`
- `0x18007e670`
- `0x180086700`
- `0x180086b1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023717`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180023717`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023570`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800236fe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023570`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800236fe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023585`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180023585`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800234ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800234ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023546`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023741`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023546`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023741`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002344d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800236f3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002344d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800236f3`

## pseudocode

```c
__int64 __fastcall DnsGetInterfacePropertiesImpl(
        HKEY hKey,
        HKEY a2,
        __int64 a3,
        void *a4,
        unsigned int *a5,
        _QWORD *a6)
{
  WCHAR *StringCopy_W_New; // rdi
  int v8; // r15d
  const WCHAR *v11; // rbp
  const WCHAR *v12; // rdx
  __int64 v13; // rax
  SIZE_T v15; // rsi
  HANDLE ProcessHeap; // rax
  WCHAR *v17; // rax
  unsigned int PropertiesForServers; // esi
  unsigned int v19; // ebx
  unsigned int v20; // eax
  HANDLE v21; // rax
  HKEY hKeya; // [rsp+50h] [rbp-58h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-50h] BYREF
  unsigned int v25; // [rsp+60h] [rbp-48h]

  StringCopy_W_New = 0;
  hKeya = 0;
  phkResult = 0;
  v8 = a3;
  v25 = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_qqlSqq((_DWORD)hKey, (_DWORD)a2, a3, (_DWORD)hKey, (__int64)a2, a3, (__int64)a4, (__int64)a5, (__int64)a6);
  if ( a6 )
    *a6 = 0;
  if ( a5 )
    *a5 = 0;
  if ( !a4 || !a5 || !a6 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs(hKey, a2, a3, a4);
    PropertiesForServers = 87;
    goto LABEL_35;
  }
  v11 = L"Dot6";
  if ( !v8 )
    v11 = L"Dot";
  v12 = L"Doh6";
  if ( !v8 )
    v12 = L"Doh";
  if ( hKey )
    RegOpenKeyExW(hKey, v12, 0, 0x20019u, &hKeya);
  if ( a2 )
    RegOpenKeyExW(a2, v11, 0, 0x20019u, &phkResult);
  if ( hKeya || phkResult )
  {
    if ( g_fVelocityDnsKernelApi )
    {
      StringCopy_W_New = (WCHAR *)Dns_CreateStringCopy_W_New(a4);
      if ( !StringCopy_W_New )
      {
        PropertiesForServers = 14;
        goto LABEL_35;
      }
    }
    else
    {
      v13 = -1;
      while ( *((_WORD *)a4 + ++v13) != 0 )
        ;
      v15 = (unsigned int)(2 * v13 + 2);
      ProcessHeap = g_hProcessHeap;
      if ( !g_hProcessHeap )
      {
        ProcessHeap = GetProcessHeap();
        g_hProcessHeap = ProcessHeap;
      }
      v17 = (WCHAR *)HeapAlloc(ProcessHeap, 8u, v15);
      StringCopy_W_New = v17;
      if ( !v17 )
      {
        PropertiesForServers = 14;
        SetLastError(0xEu);
        StringCopy_W_New = 0;
        goto LABEL_35;
      }
      memcpy_0(v17, a4, v15);
    }
    PropertiesForServers = 0;
    v19 = 0;
    while ( v19 < 3 )
    {
      ++v19;
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_d(1035, 310, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v19);
      v20 = DnsCountServerProperties(hKeya, phkResult, StringCopy_W_New);
      PropertiesForServers = v20;
      if ( v20 )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          WPP_SF_d(1035, 311, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v20);
        goto LABEL_35;
      }
      if ( !v25 )
      {
        if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
          WPP_SF_(1035, 312, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids);
        goto LABEL_35;
      }
      PropertiesForServers = DnsReadPropertiesForServers(hKeya, phkResult, (__int64)StringCopy_W_New, v25, a5, a6);
      if ( !PropertiesForServers )
        goto LABEL_35;
    }
    goto LABEL_35;
  }
  PropertiesForServers = 0;
  if ( (BYTE1(xmmword_1800AB5A0) & 8) == 0 )
    return PropertiesForServers;
  WPP_SF_(1035, 309, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids);
LABEL_35:
  if ( hKeya )
  {
    RegCloseKey(hKeya);
    hKeya = 0;
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( StringCopy_W_New )
  {
    v21 = g_hProcessHeap;
    if ( !g_hProcessHeap )
    {
      v21 = GetProcessHeap();
      g_hProcessHeap = v21;
    }
    HeapFree(v21, 0, StringCopy_W_New);
  }
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 313, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, PropertiesForServers);
  return PropertiesForServers;
}

```

## disassembly

```asm
0x180023380  mov     [rsp+arg_10], rbx
0x180023385  push    rbp
0x180023386  push    rsi
0x180023387  push    rdi
0x180023388  push    r12
0x18002338a  push    r13
0x18002338c  push    r14
0x18002338e  push    r15
0x180023390  sub     rsp, 70h
0x180023394  mov     rax, cs:__security_cookie
0x18002339b  xor     rax, rsp
0x18002339e  mov     [rsp+0A8h+var_40], rax
0x1800233a3  mov     r12, [rsp+0A8h+arg_20]
0x1800233ab  xor     ebp, ebp
0x1800233ad  mov     r13, [rsp+0A8h+arg_28]
0x1800233b5  mov     edi, ebp
0x1800233b7  mov     [rsp+0A8h+hKey], rbp
0x1800233bc  mov     rbx, r9
0x1800233bf  mov     [rsp+0A8h+var_50], rbp
0x1800233c4  mov     r15d, r8d
0x1800233c7  mov     [rsp+0A8h+var_48], ebp
0x1800233cb  mov     r14, rdx
0x1800233ce  mov     rsi, rcx
0x1800233d1  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800233d8  jnz     loc_180023696
0x1800233de  test    r13, r13
0x1800233e1  jz      short loc_1800233E7
0x1800233e3  mov     [r13+0], rbp
0x1800233e7  test    r12, r12
0x1800233ea  jz      short loc_1800233F0
0x1800233ec  mov     [r12], ebp
0x1800233f0  test    rbx, rbx
0x1800233f3  jz      loc_180023634
0x1800233f9  test    r12, r12
0x1800233fc  jz      loc_1800236BC
0x180023402  test    r13, r13
0x180023405  jz      loc_1800236CB
0x18002340b  test    r15d, r15d
0x18002340e  lea     rax, aDot; "Dot"
0x180023415  lea     rbp, aDot6; "Dot6"
0x18002341c  cmovz   rbp, rax
0x180023420  lea     rdx, aDoh6; "Doh6"
0x180023427  lea     rax, aDoh; "Doh"
0x18002342e  cmovz   rdx, rax; lpSubKey
0x180023432  test    rsi, rsi
0x180023435  jz      short loc_180023453
0x180023437  lea     rax, [rsp+0A8h+hKey]
0x18002343c  mov     r9d, 20019h; samDesired
0x180023442  xor     r8d, r8d; ulOptions
0x180023445  mov     [rsp+0A8h+phkResult], rax; phkResult
0x18002344a  mov     rcx, rsi; hKey
0x18002344d  call    cs:__imp_RegOpenKeyExW
0x180023453  test    r14, r14
0x180023456  jnz     loc_1800236DA
0x18002345c  cmp     [rsp+0A8h+hKey], rdi
0x180023461  jz      loc_1800235BB
0x180023467  cmp     cs:g_fVelocityDnsKernelApi, edi
0x18002346d  jnz     short loc_1800234CF
0x18002346f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180023476  nop     word ptr [rax+rax+00000000h]
0x180023480  cmp     [rbx+rax*2+2], di
0x180023485  lea     rax, [rax+1]
0x180023489  jnz     short loc_180023480
0x18002348b  lea     esi, ds:2[rax*2]
0x180023492  mov     rax, cs:g_hProcessHeap
0x180023499  test    rax, rax
0x18002349c  jz      loc_1800236FE
0x1800234a2  mov     r8, rsi; dwBytes
0x1800234a5  mov     edx, 8; dwFlags
0x1800234aa  mov     rcx, rax; hHeap
0x1800234ad  call    cs:__imp_HeapAlloc
0x1800234b3  mov     rdi, rax
0x1800234b6  test    rax, rax
0x1800234b9  jz      loc_180023710
0x1800234bf  mov     r8, rsi; Size
0x1800234c2  mov     rdx, rbx; Src
0x1800234c5  mov     rcx, rax; void *
0x1800234c8  call    memcpy_0
0x1800234cd  jmp     short loc_1800234E3
0x1800234cf  mov     rcx, rbx; Src
0x1800234d2  call    Dns_CreateStringCopy_W_New
0x1800234d7  mov     rdi, rax
0x1800234da  test    rax, rax
0x1800234dd  jz      loc_18002366E
0x1800234e3  xor     esi, esi
0x1800234e5  mov     rbp, rdi
0x1800234e8  xor     ebx, ebx
0x1800234ea  cmp     ebx, 3
0x1800234ed  jnb     short loc_18002353A
0x1800234ef  inc     ebx
0x1800234f1  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800234f8  jnz     loc_180023678
0x1800234fe  mov     rdx, [rsp+0A8h+var_50]; HKEY
0x180023503  lea     r9, [rsp+0A8h+var_48]
0x180023508  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18002350d  mov     r8, rbp; lpSubKey
0x180023510  call    DnsCountServerProperties
0x180023515  mov     esi, eax
0x180023517  test    eax, eax
0x180023519  jnz     loc_180023643
0x18002351f  mov     r9d, [rsp+0A8h+var_48]
0x180023524  test    r9d, r9d
0x180023527  jnz     loc_180023609
0x18002352d  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180023534  jnz     loc_180023726
0x18002353a  xor     ebp, ebp
0x18002353c  mov     rcx, [rsp+0A8h+hKey]; hKey
0x180023541  test    rcx, rcx
0x180023544  jz      short loc_180023551
0x180023546  call    cs:__imp_RegCloseKey
0x18002354c  mov     [rsp+0A8h+hKey], rbp
0x180023551  mov     rcx, [rsp+0A8h+var_50]; hKey
0x180023556  test    rcx, rcx
0x180023559  jnz     loc_180023741
0x18002355f  test    rdi, rdi
0x180023562  jz      short loc_18002358B
0x180023564  mov     rax, cs:g_hProcessHeap
0x18002356b  test    rax, rax
0x18002356e  jnz     short loc_18002357D
0x180023570  call    cs:__imp_GetProcessHeap
0x180023576  mov     cs:g_hProcessHeap, rax
0x18002357d  mov     r8, rdi; lpMem
0x180023580  xor     edx, edx; dwFlags
0x180023582  mov     rcx, rax; hHeap
0x180023585  call    cs:__imp_HeapFree
0x18002358b  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180023592  jnz     short loc_1800235EE
0x180023594  mov     eax, esi
0x180023596  mov     rcx, [rsp+0A8h+var_40]
0x18002359b  xor     rcx, rsp; StackCookie
0x18002359e  call    __security_check_cookie
0x1800235a3  mov     rbx, [rsp+0A8h+arg_10]
0x1800235ab  add     rsp, 70h
0x1800235af  pop     r15
0x1800235b1  pop     r14
0x1800235b3  pop     r13
0x1800235b5  pop     r12
0x1800235b7  pop     rdi
0x1800235b8  pop     rsi
0x1800235b9  pop     rbp
0x1800235ba  retn
0x1800235bb  cmp     [rsp+0A8h+var_50], rdi
0x1800235c0  jnz     loc_180023467
0x1800235c6  xor     ebp, ebp
0x1800235c8  mov     esi, ebp
0x1800235ca  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800235d1  jz      short loc_180023594
0x1800235d3  mov     edx, 135h
0x1800235d8  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x1800235df  mov     ecx, 40Bh
0x1800235e4  call    WPP_SF_
0x1800235e9  jmp     loc_18002353C
0x1800235ee  mov     edx, 139h
0x1800235f3  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x1800235fa  mov     ecx, 40Bh
0x1800235ff  mov     r9d, esi
0x180023602  call    WPP_SF_d
0x180023607  jmp     short loc_180023594
0x180023609  mov     rdx, [rsp+0A8h+var_50]; HKEY
0x18002360e  mov     r8, rbp; lpSubKey
0x180023611  mov     rcx, [rsp+0A8h+hKey]; hKey
0x180023616  mov     [rsp+0A8h+var_80], r13; __int64
0x18002361b  mov     [rsp+0A8h+phkResult], r12; __int64
0x180023620  call    DnsReadPropertiesForServers
0x180023625  mov     esi, eax
0x180023627  test    eax, eax
0x180023629  jnz     loc_1800234EA
0x18002362f  jmp     loc_18002353A
0x180023634  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180023639  mov     esi, 57h ; 'W'
0x18002363e  jmp     loc_18002353C
0x180023643  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x18002364a  jz      loc_18002353A
0x180023650  mov     edx, 137h
0x180023655  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x18002365c  mov     ecx, 40Bh
0x180023661  mov     r9d, eax
0x180023664  call    WPP_SF_d
0x180023669  jmp     loc_18002353A
0x18002366e  mov     esi, 0Eh
0x180023673  jmp     loc_18002353A
0x180023678  mov     edx, 136h
0x18002367d  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x180023684  mov     ecx, 40Bh
0x180023689  mov     r9d, ebx
0x18002368c  call    WPP_SF_d
0x180023691  jmp     loc_1800234FE
0x180023696  mov     [rsp+0A8h+var_68], r13
0x18002369b  mov     r9, rsi
0x18002369e  mov     [rsp+0A8h+var_70], r12
0x1800236a3  mov     [rsp+0A8h+var_78], rbx
0x1800236a8  mov     dword ptr [rsp+0A8h+var_80], r15d
0x1800236ad  mov     [rsp+0A8h+phkResult], r14
0x1800236b2  call    WPP_SF_qqlSqq
0x1800236b7  jmp     loc_1800233DE
0x1800236bc  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800236c1  mov     esi, 57h ; 'W'
0x1800236c6  jmp     loc_18002353C
0x1800236cb  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800236d0  mov     esi, 57h ; 'W'
0x1800236d5  jmp     loc_18002353C
0x1800236da  lea     rax, [rsp+0A8h+var_50]
0x1800236df  mov     r9d, 20019h; samDesired
0x1800236e5  xor     r8d, r8d; ulOptions
0x1800236e8  mov     [rsp+0A8h+phkResult], rax; phkResult
0x1800236ed  mov     rdx, rbp; lpSubKey
0x1800236f0  mov     rcx, r14; hKey
0x1800236f3  call    cs:__imp_RegOpenKeyExW
0x1800236f9  jmp     loc_18002345C
0x1800236fe  call    cs:__imp_GetProcessHeap
0x180023704  mov     cs:g_hProcessHeap, rax
0x18002370b  jmp     loc_1800234A2
0x180023710  mov     esi, 0Eh
0x180023715  mov     ecx, esi; dwErrCode
0x180023717  call    cs:__imp_SetLastError
0x18002371d  xor     ebp, ebp
0x18002371f  mov     edi, ebp
0x180023721  jmp     loc_18002353C
0x180023726  mov     edx, 138h
0x18002372b  lea     r8, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x180023732  mov     ecx, 40Bh
0x180023737  call    WPP_SF_
0x18002373c  jmp     loc_18002353A
0x180023741  call    cs:__imp_RegCloseKey
0x180023747  mov     [rsp+0A8h+var_50], rbp
0x18002374c  jmp     loc_18002355F
```
