# GetTypeByNameW

- ea: `0x18002ccd0`
- end: `0x18002cf85`
- name: `GetTypeByNameW`
- size: `693`
- prototype: `INT __stdcall(LPWSTR lpServiceName, LPGUID lpServiceType)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x18002c910`
- `0x18002cc30`

## callees

- `0x1800222f0`
- `0x180022330`
- `0x18002c73c`
- `0x18002ccd0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18002ce71`
- `ntdll!RtlFreeHeap` at `0x18002ced5`
- `ntdll!RtlFreeHeap` at `0x18002ce71`
- `ntdll!RtlFreeHeap` at `0x18002ced5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cf52`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002cf52`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002cd75`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002cdcd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002cd75`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002cdcd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002cdba`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002cdba`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002cd36`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002cd62`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002cd36`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002cd62`
- `WS2_32!__imp_htons` at `0x18002ce81`
- `WS2_32!__imp_htons` at `0x18002ceea`
- `WS2_32!__imp_htons` at `0x18002ce81`
- `WS2_32!__imp_htons` at `0x18002ceea`
- `WS2_32!__imp_getservbyname` at `0x18002ce51`
- `WS2_32!__imp_getservbyname` at `0x18002ceba`
- `WS2_32!__imp_getservbyname` at `0x18002ce51`
- `WS2_32!__imp_getservbyname` at `0x18002ceba`
- `RPCRT4!UuidFromStringW` at `0x18002ce12`
- `RPCRT4!UuidFromStringW` at `0x18002ce12`

## string_xrefs

- `0x18002cd28`: `SYSTEM\CurrentControlSet\Control\ServiceProvider\ServiceTypes`

## pseudocode

```c
INT __stdcall GetTypeByNameW(LPWSTR lpServiceName, LPGUID lpServiceType)
{
  LSTATUS v4; // ebx
  LSTATUS v5; // ebx
  DWORD v6; // ecx
  __int64 v7; // rax
  unsigned __int64 v8; // rcx
  RPC_STATUS v9; // eax
  const char *AnsiName; // rax
  char *v11; // rbx
  struct servent *v12; // rsi
  unsigned int v13; // eax
  struct servent *v15; // rsi
  unsigned int i; // ecx
  LPWSTR v17; // rax
  int v18; // r8d
  int v19; // edx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  BYTE Data[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 StringUuid[103]; // [rsp+52h] [rbp-AEh] BYREF

  hKey = 0;
  phkResult = 0;
  cbData = 0;
  Type = 0;
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Control\\ServiceProvider\\ServiceTypes",
         0,
         0x20019u,
         &hKey)
    || (v4 = RegOpenKeyExW(hKey, lpServiceName, 0, 0x20019u, &phkResult), RegCloseKey(hKey), v4) )
  {
    AnsiName = (const char *)GetAnsiName(lpServiceName);
    v11 = (char *)AnsiName;
    if ( AnsiName )
    {
      v12 = getservbyname(AnsiName, "tcp");
      if ( v12 )
      {
        RtlFreeHeap(SockPrivateHeap, 0, v11);
        v13 = htons(v12->s_port) | 0x90000;
LABEL_14:
        lpServiceType->Data1 = v13;
        *(_DWORD *)&lpServiceType->Data2 = 0;
        *(_DWORD *)lpServiceType->Data4 = 192;
        *(_DWORD *)&lpServiceType->Data4[4] = 1174405120;
        return 0;
      }
      v15 = getservbyname(v11, "udp");
      RtlFreeHeap(SockPrivateHeap, 0, v11);
      if ( v15 )
      {
        v13 = htons(v15->s_port) | 0xA0000;
        goto LABEL_14;
      }
    }
    for ( i = 0; i < 0x15; ++i )
    {
      v17 = lpServiceName;
      do
      {
        v18 = *(LPWSTR)((char *)v17 + (char *)(&KnownGuids)[3 * (int)i] - (char *)lpServiceName);
        v19 = *v17 - v18;
        if ( v19 )
          break;
        ++v17;
      }
      while ( v18 );
      if ( !v19 )
      {
        *lpServiceType = *(LPGUID)(&KnownGuids + 3 * (int)i + 1);
        return 0;
      }
    }
    v6 = 1060;
    goto LABEL_27;
  }
  cbData = 200;
  v5 = RegQueryValueExW(phkResult, L"GUID", 0, &Type, Data, &cbData);
  RegCloseKey(phkResult);
  if ( !v5 )
  {
    v7 = -1;
    do
      ++v7;
    while ( *(_WORD *)&Data[2 * v7] );
    v8 = 2 * v7 - 2;
    if ( v8 >= 0xC8 )
      _report_rangecheckfailure();
    *(_WORD *)&Data[v8] = 0;
    v9 = UuidFromStringW(StringUuid, lpServiceType);
    if ( v9 )
    {
      v6 = v9;
      goto LABEL_27;
    }
    return 0;
  }
  v6 = v5;
LABEL_27:
  SetLastError(v6);
  return -1;
}

```

## disassembly

```asm
0x18002ccd0  mov     [rsp-8+arg_10], rbx
0x18002ccd5  push    rbp
0x18002ccd6  push    rsi
0x18002ccd7  push    rdi
0x18002ccd8  push    r14
0x18002ccda  push    r15
0x18002ccdc  lea     rbp, [rsp-30h]
0x18002cce1  sub     rsp, 130h
0x18002cce8  mov     rax, cs:__security_cookie
0x18002ccef  xor     rax, rsp
0x18002ccf2  mov     [rbp+50h+var_30], rax
0x18002ccf6  xor     r15d, r15d
0x18002ccf9  lea     rax, [rsp+150h+hKey]
0x18002ccfe  mov     rdi, rdx
0x18002cd01  mov     [rsp+150h+hKey], r15
0x18002cd06  mov     r14, rcx
0x18002cd09  mov     [rsp+150h+var_110], r15
0x18002cd0e  mov     ebx, 20019h
0x18002cd13  mov     [rsp+150h+cbData], r15d
0x18002cd18  mov     r9d, ebx; samDesired
0x18002cd1b  mov     [rsp+150h+Type], r15d
0x18002cd20  xor     r8d, r8d; ulOptions
0x18002cd23  mov     [rsp+150h+phkResult], rax; phkResult
0x18002cd28  lea     rdx, aSystemCurrentc_1; "SYSTEM\\CurrentControlSet\\Control\\Ser"...
0x18002cd2f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002cd36  call    cs:__imp_RegOpenKeyExW
0x18002cd3d  nop     dword ptr [rax+rax+00h]
0x18002cd42  test    eax, eax
0x18002cd44  jnz     loc_18002CE33
0x18002cd4a  mov     rcx, [rsp+150h+hKey]; hKey
0x18002cd4f  lea     rax, [rsp+150h+var_110]
0x18002cd54  mov     r9d, ebx; samDesired
0x18002cd57  mov     [rsp+150h+phkResult], rax; phkResult
0x18002cd5c  xor     r8d, r8d; ulOptions
0x18002cd5f  mov     rdx, r14; lpSubKey
0x18002cd62  call    cs:__imp_RegOpenKeyExW
0x18002cd69  nop     dword ptr [rax+rax+00h]
0x18002cd6e  mov     rcx, [rsp+150h+hKey]; hKey
0x18002cd73  mov     ebx, eax
0x18002cd75  call    cs:__imp_RegCloseKey
0x18002cd7c  nop     dword ptr [rax+rax+00h]
0x18002cd81  test    ebx, ebx
0x18002cd83  jnz     loc_18002CE33
0x18002cd89  mov     rcx, [rsp+150h+var_110]; hKey
0x18002cd8e  lea     rax, [rsp+150h+cbData]
0x18002cd93  mov     [rsp+150h+lpcbData], rax; lpcbData
0x18002cd98  lea     r9, [rsp+150h+Type]; lpType
0x18002cd9d  lea     rax, [rsp+150h+Data]
0x18002cda2  mov     esi, 0C8h
0x18002cda7  xor     r8d, r8d; lpReserved
0x18002cdaa  mov     [rsp+150h+phkResult], rax; lpData
0x18002cdaf  lea     rdx, aGuid; "GUID"
0x18002cdb6  mov     [rsp+150h+cbData], esi
0x18002cdba  call    cs:__imp_RegQueryValueExW
0x18002cdc1  nop     dword ptr [rax+rax+00h]
0x18002cdc6  mov     rcx, [rsp+150h+var_110]; hKey
0x18002cdcb  mov     ebx, eax
0x18002cdcd  call    cs:__imp_RegCloseKey
0x18002cdd4  nop     dword ptr [rax+rax+00h]
0x18002cdd9  test    ebx, ebx
0x18002cddb  jz      short loc_18002CDE4
0x18002cddd  mov     ecx, ebx
0x18002cddf  jmp     loc_18002CF52
0x18002cde4  lea     rcx, [rsp+150h+Data]
0x18002cde9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002cded  inc     rax
0x18002cdf0  cmp     [rcx+rax*2], r15w
0x18002cdf5  jnz     short loc_18002CDED
0x18002cdf7  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x18002cdff  cmp     rcx, rsi
0x18002ce02  jnb     short loc_18002CE2D
0x18002ce04  mov     word ptr [rsp+rcx+150h+Data], r15w
0x18002ce0a  mov     rdx, rdi; Uuid
0x18002ce0d  lea     rcx, [rsp+150h+StringUuid]; StringUuid
0x18002ce12  call    cs:__imp_UuidFromStringW
0x18002ce19  nop     dword ptr [rax+rax+00h]
0x18002ce1e  test    eax, eax
0x18002ce20  jz      loc_18002CEA9
0x18002ce26  mov     ecx, eax
0x18002ce28  jmp     loc_18002CF52
0x18002ce2d  call    __report_rangecheckfailure
0x18002ce33  mov     rcx, r14; SourceString
0x18002ce36  call    GetAnsiName
0x18002ce3b  mov     rbx, rax
0x18002ce3e  test    rax, rax
0x18002ce41  jz      loc_18002CF00
0x18002ce47  lea     rdx, aTcp; "tcp"
0x18002ce4e  mov     rcx, rax; name
0x18002ce51  call    cs:__imp_getservbyname
0x18002ce58  nop     dword ptr [rax+rax+00h]
0x18002ce5d  mov     rsi, rax
0x18002ce60  test    rax, rax
0x18002ce63  jz      short loc_18002CEB0
0x18002ce65  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18002ce6c  mov     r8, rbx; P
0x18002ce6f  xor     edx, edx; Flags
0x18002ce71  call    cs:__imp_RtlFreeHeap
0x18002ce78  nop     dword ptr [rax+rax+00h]
0x18002ce7d  movzx   ecx, word ptr [rsi+18h]; hostshort
0x18002ce81  call    cs:__imp_htons
0x18002ce88  nop     dword ptr [rax+rax+00h]
0x18002ce8d  movzx   eax, ax
0x18002ce90  or      eax, 90000h
0x18002ce95  mov     [rdi], eax
0x18002ce97  mov     [rdi+4], r15d
0x18002ce9b  mov     dword ptr [rdi+8], 0C0h
0x18002cea2  mov     dword ptr [rdi+0Ch], 46000000h
0x18002cea9  xor     eax, eax
0x18002ceab  jmp     loc_18002CF61
0x18002ceb0  lea     rdx, proto; "udp"
0x18002ceb7  mov     rcx, rbx; name
0x18002ceba  call    cs:__imp_getservbyname
0x18002cec1  nop     dword ptr [rax+rax+00h]
0x18002cec6  mov     rcx, cs:SockPrivateHeap; HeapHandle
0x18002cecd  mov     r8, rbx; P
0x18002ced0  xor     edx, edx; Flags
0x18002ced2  mov     rsi, rax
0x18002ced5  call    cs:__imp_RtlFreeHeap
0x18002cedc  nop     dword ptr [rax+rax+00h]
0x18002cee1  test    rsi, rsi
0x18002cee4  jz      short loc_18002CF00
0x18002cee6  movzx   ecx, word ptr [rsi+18h]; hostshort
0x18002ceea  call    cs:__imp_htons
0x18002cef1  nop     dword ptr [rax+rax+00h]
0x18002cef6  movzx   eax, ax
0x18002cef9  or      eax, 0A0000h
0x18002cefe  jmp     short loc_18002CE95
0x18002cf00  mov     ecx, r15d
0x18002cf03  lea     r11, KnownGuids
0x18002cf0a  cmp     ecx, 15h
0x18002cf0d  jnb     short loc_18002CF4D
0x18002cf0f  movsxd  rax, ecx
0x18002cf12  lea     r10, [rax+rax*2]
0x18002cf16  mov     rax, r14
0x18002cf19  mov     r9, [r11+r10*8]
0x18002cf1d  sub     r9, r14
0x18002cf20  movzx   edx, word ptr [rax]
0x18002cf23  movzx   r8d, word ptr [rax+r9]
0x18002cf28  sub     edx, r8d
0x18002cf2b  jnz     short loc_18002CF36
0x18002cf2d  add     rax, 2
0x18002cf31  test    r8d, r8d
0x18002cf34  jnz     short loc_18002CF20
0x18002cf36  test    edx, edx
0x18002cf38  jz      short loc_18002CF3E
0x18002cf3a  inc     ecx
0x18002cf3c  jmp     short loc_18002CF0A
0x18002cf3e  movups  xmm0, xmmword ptr [r11+r10*8+8]
0x18002cf44  movdqu  xmmword ptr [rdi], xmm0
0x18002cf48  jmp     loc_18002CEA9
0x18002cf4d  mov     ecx, 424h; dwErrCode
0x18002cf52  call    cs:__imp_SetLastError
0x18002cf59  nop     dword ptr [rax+rax+00h]
0x18002cf5e  or      eax, 0FFFFFFFFh
0x18002cf61  mov     rcx, [rbp+50h+var_30]
0x18002cf65  xor     rcx, rsp; StackCookie
0x18002cf68  call    __security_check_cookie
0x18002cf6d  mov     rbx, [rsp+150h+arg_10]
0x18002cf75  add     rsp, 130h
0x18002cf7c  pop     r15
0x18002cf7e  pop     r14
0x18002cf80  pop     rdi
0x18002cf81  pop     rsi
0x18002cf82  pop     rbp
0x18002cf83  retn
```
