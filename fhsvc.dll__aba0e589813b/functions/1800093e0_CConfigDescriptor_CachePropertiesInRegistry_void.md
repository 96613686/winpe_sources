# CConfigDescriptor::CachePropertiesInRegistry(void)

- ea: `0x1800093e0`
- end: `0x180009656`
- name: `?CachePropertiesInRegistry@CConfigDescriptor@@QEAAXXZ`
- size: `630`
- prototype: `void __fastcall(CConfigDescriptor *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003f00`
- `0x180009fd0`

## callees

- `0x1800093e0`
- `0x18000ca14`
- `0x18000d970`
- `0x18000daf0`
- `0x180010288`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18000952c`
- `ADVAPI32!RegSetValueExW` at `0x18000952c`
- `ADVAPI32!RegCreateKeyExW` at `0x180009492`
- `ADVAPI32!RegCreateKeyExW` at `0x180009492`
- `ADVAPI32!SetThreadToken` at `0x180009401`
- `ADVAPI32!SetThreadToken` at `0x180009580`
- `ADVAPI32!SetThreadToken` at `0x180009401`
- `ADVAPI32!SetThreadToken` at `0x180009580`
- `ADVAPI32!RegCloseKey` at `0x1800095f8`
- `ADVAPI32!RegCloseKey` at `0x1800095f8`
- `KERNEL32!GetLastError` at `0x180009412`
- `KERNEL32!GetLastError` at `0x18000958e`
- `KERNEL32!GetLastError` at `0x1800095b6`
- `KERNEL32!GetLastError` at `0x180009412`
- `KERNEL32!GetLastError` at `0x18000958e`
- `KERNEL32!GetLastError` at `0x1800095b6`

## string_xrefs

- `0x18000962e`: `SUCCEEDED(hr) || (hr == HRESULT_FROM_WIN32(ERROR_ACCESS_DENIED))`

## pseudocode

```c
void __fastcall CConfigDescriptor::CachePropertiesInRegistry(CConfigDescriptor *this)
{
  void *v1; // rdx
  signed int LastError; // eax
  signed int v4; // ebx
  LSTATUS v5; // eax
  LSTATUS v6; // eax
  signed int v7; // eax
  PVOID *v8; // r10
  signed int v9; // eax
  HKEY hKey; // [rsp+70h] [rbp+8h] BYREF
  unsigned __int64 Data; // [rsp+78h] [rbp+10h] BYREF

  v1 = (void *)*((_QWORD *)this + 1);
  hKey = 0;
  Data = 0;
  if ( SetThreadToken(0, v1) )
  {
    v5 = RegCreateKeyExW(
           HKEY_CURRENT_USER,
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\FileHistory",
           0,
           0,
           0,
           0x2001Fu,
           0,
           &hKey,
           0);
    v4 = v5;
    if ( v5 )
    {
      if ( v5 > 0 )
        v4 = (unsigned __int16)v5 | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          (int)&WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
          (int)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\FileHistory",
          v4);
    }
    else
    {
      Data = *((unsigned int *)this + 37) + ((unsigned __int64)*((unsigned int *)this + 38) << 32);
      v4 = 0;
      v6 = RegSetValueExW(hKey, L"ProtectedUpToTime", 0, 0xBu, (const BYTE *)&Data, 8u);
      if ( v6 )
      {
        v4 = v6 > 0 ? (unsigned __int16)v6 | 0x80070000 : v6;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_SSd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            29,
            (unsigned int)&WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
            (unsigned int)L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\FileHistory",
            (__int64)L"ProtectedUpToTime",
            v4);
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        27,
        &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
        (unsigned int)v4);
  }
  if ( SetThreadToken(0, 0) )
    goto LABEL_29;
  if ( v4 >= 0 )
  {
    v7 = GetLastError();
    v4 = v7;
    if ( v7 > 0 )
      v4 = (unsigned __int16)v7 | 0x80070000;
  }
  v8 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v9 = GetLastError();
    if ( v9 > 0 )
      v9 = (unsigned __int16)v9 | 0x80070000;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      30,
      &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
      (unsigned int)v9);
LABEL_29:
    v8 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    v8 = (PVOID *)WPP_GLOBAL_Control;
    hKey = 0;
  }
  if ( (int)(v4 + 0x80000000) >= 0 && v4 != -2147024891 && v8 != &WPP_GLOBAL_Control && (*((_BYTE *)v8 + 28) & 4) != 0 )
    WPP_SF_s(
      v8[2],
      31,
      &WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids,
      "SUCCEEDED(hr) || (hr == HRESULT_FROM_WIN32(ERROR_ACCESS_DENIED))");
}

```

## disassembly

```asm
0x1800093e0  mov     [rsp+arg_10], rbx
0x1800093e5  push    rbp
0x1800093e6  push    rsi
0x1800093e7  push    rdi
0x1800093e8  sub     rsp, 50h
0x1800093ec  mov     rdx, [rcx+8]; Token
0x1800093f0  mov     rdi, rcx
0x1800093f3  xor     esi, esi
0x1800093f5  xor     ecx, ecx; Thread
0x1800093f7  mov     [rsp+68h+hKey], rsi
0x1800093fc  mov     [rsp+68h+Data], rsi
0x180009401  call    cs:__imp_SetThreadToken
0x180009407  lea     rbp, WPP_GLOBAL_Control
0x18000940e  test    eax, eax
0x180009410  jnz     short loc_18000945E
0x180009412  call    cs:__imp_GetLastError
0x180009418  mov     ebx, eax
0x18000941a  test    eax, eax
0x18000941c  jle     short loc_180009427
0x18000941e  movzx   ebx, ax
0x180009421  or      ebx, 80070000h
0x180009427  mov     rcx, cs:WPP_GLOBAL_Control
0x18000942e  cmp     rcx, rbp
0x180009431  jz      loc_18000957C
0x180009437  test    byte ptr [rcx+1Ch], 1
0x18000943b  jz      loc_18000957C
0x180009441  mov     rcx, [rcx+10h]
0x180009445  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x18000944c  mov     edx, 1Bh
0x180009451  mov     r9d, ebx
0x180009454  call    WPP_SF_d
0x180009459  jmp     loc_18000957C
0x18000945e  mov     [rsp+68h+lpdwDisposition], rsi; lpdwDisposition
0x180009463  lea     rax, [rsp+68h+hKey]
0x180009468  mov     [rsp+68h+phkResult], rax; phkResult
0x18000946d  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180009474  mov     [rsp+68h+lpSecurityAttributes], rsi; lpSecurityAttributes
0x180009479  xor     r9d, r9d; lpClass
0x18000947c  mov     [rsp+68h+samDesired], 2001Fh; samDesired
0x180009484  xor     r8d, r8d; Reserved
0x180009487  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000948e  mov     [rsp+68h+dwOptions], esi; dwOptions
0x180009492  call    cs:__imp_RegCreateKeyExW
0x180009498  mov     ebx, eax
0x18000949a  test    eax, eax
0x18000949c  jz      short loc_1800094E8
0x18000949e  jle     short loc_1800094A9
0x1800094a0  movzx   ebx, ax
0x1800094a3  or      ebx, 80070000h
0x1800094a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800094b0  cmp     rcx, rbp
0x1800094b3  jz      loc_18000957C
0x1800094b9  test    byte ptr [rcx+1Ch], 1
0x1800094bd  jz      loc_18000957C
0x1800094c3  mov     rcx, [rcx+10h]
0x1800094c7  lea     r9, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800094ce  mov     edx, 1Ch
0x1800094d3  mov     [rsp+68h+dwOptions], ebx
0x1800094d7  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x1800094de  call    WPP_SF_Sd
0x1800094e3  jmp     loc_18000957C
0x1800094e8  mov     eax, [rdi+94h]
0x1800094ee  mov     r9d, 0Bh; dwType
0x1800094f4  mov     ecx, [rdi+98h]
0x1800094fa  xor     r8d, r8d; Reserved
0x1800094fd  shl     rcx, 20h
0x180009501  lea     rdi, ValueName; "ProtectedUpToTime"
0x180009508  add     rcx, rax
0x18000950b  mov     [rsp+68h+samDesired], 8; cbData
0x180009513  mov     [rsp+68h+Data], rcx
0x180009518  lea     rax, [rsp+68h+Data]
0x18000951d  mov     rcx, [rsp+68h+hKey]; hKey
0x180009522  mov     rdx, rdi; lpValueName
0x180009525  mov     ebx, esi
0x180009527  mov     qword ptr [rsp+68h+dwOptions], rax; lpData
0x18000952c  call    cs:__imp_RegSetValueExW
0x180009532  test    eax, eax
0x180009534  jz      short loc_18000957C
0x180009536  jg      short loc_18000953C
0x180009538  mov     ebx, eax
0x18000953a  jmp     short loc_180009545
0x18000953c  movzx   ebx, ax
0x18000953f  or      ebx, 80070000h
0x180009545  mov     rcx, cs:WPP_GLOBAL_Control
0x18000954c  cmp     rcx, rbp
0x18000954f  jz      short loc_18000957C
0x180009551  test    byte ptr [rcx+1Ch], 1
0x180009555  jz      short loc_18000957C
0x180009557  mov     rcx, [rcx+10h]
0x18000955b  lea     r9, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180009562  mov     edx, 1Dh
0x180009567  mov     [rsp+68h+samDesired], ebx
0x18000956b  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180009572  mov     qword ptr [rsp+68h+dwOptions], rdi
0x180009577  call    WPP_SF_SSd
0x18000957c  xor     edx, edx; Token
0x18000957e  xor     ecx, ecx; Thread
0x180009580  call    cs:__imp_SetThreadToken
0x180009586  test    eax, eax
0x180009588  jnz     short loc_1800095E7
0x18000958a  test    ebx, ebx
0x18000958c  js      short loc_1800095A3
0x18000958e  call    cs:__imp_GetLastError
0x180009594  mov     ebx, eax
0x180009596  test    eax, eax
0x180009598  jle     short loc_1800095A3
0x18000959a  movzx   ebx, ax
0x18000959d  or      ebx, 80070000h
0x1800095a3  mov     r10, cs:WPP_GLOBAL_Control
0x1800095aa  cmp     r10, rbp
0x1800095ad  jz      short loc_1800095EE
0x1800095af  test    byte ptr [r10+1Ch], 1
0x1800095b4  jz      short loc_1800095EE
0x1800095b6  call    cs:__imp_GetLastError
0x1800095bc  test    eax, eax
0x1800095be  jle     short loc_1800095C8
0x1800095c0  movzx   eax, ax
0x1800095c3  or      eax, 80070000h
0x1800095c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800095cf  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x1800095d6  mov     edx, 1Eh
0x1800095db  mov     r9d, eax
0x1800095de  mov     rcx, [rcx+10h]
0x1800095e2  call    WPP_SF_d
0x1800095e7  mov     r10, cs:WPP_GLOBAL_Control
0x1800095ee  mov     rcx, [rsp+68h+hKey]; hKey
0x1800095f3  test    rcx, rcx
0x1800095f6  jz      short loc_18000960A
0x1800095f8  call    cs:__imp_RegCloseKey
0x1800095fe  mov     r10, cs:WPP_GLOBAL_Control
0x180009605  mov     [rsp+68h+hKey], rsi
0x18000960a  mov     ecx, 80000000h
0x18000960f  lea     eax, [rbx+rcx]
0x180009612  test    ecx, eax
0x180009614  jnz     short loc_180009646
0x180009616  cmp     ebx, 80070005h
0x18000961c  jz      short loc_180009646
0x18000961e  cmp     r10, rbp
0x180009621  jz      short loc_180009646
0x180009623  test    byte ptr [r10+1Ch], 4
0x180009628  jz      short loc_180009646
0x18000962a  mov     rcx, [r10+10h]
0x18000962e  lea     r9, aSucceededHrHrH; "SUCCEEDED(hr) || (hr == HRESULT_FROM_WI"...
0x180009635  mov     edx, 1Fh
0x18000963a  lea     r8, WPP_a36920fbec7731c49b02dea361b0ee02_Traceguids
0x180009641  call    WPP_SF_s
0x180009646  mov     rbx, [rsp+68h+arg_10]
0x18000964e  add     rsp, 50h
0x180009652  pop     rdi
0x180009653  pop     rsi
0x180009654  pop     rbp
0x180009655  retn
```
