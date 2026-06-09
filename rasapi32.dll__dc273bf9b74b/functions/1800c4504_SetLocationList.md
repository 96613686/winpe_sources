# SetLocationList

- ea: `0x1800c4504`
- end: `0x1800c473d`
- name: `SetLocationList`
- size: `569`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800c4744`

## callees

- `0x18008d8d8`
- `0x1800c4504`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800c45ab`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800c45ab`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c46b0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c46e5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c46b0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800c46e5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800c4574`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800c4677`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800c4574`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800c4677`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800c45c3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1800c45c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c46f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c4711`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c46f1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800c4711`
- `rtutils!TracePrintfExA` at `0x1800c463b`
- `rtutils!TracePrintfExA` at `0x1800c463b`

## pseudocode

```c
LSTATUS __fastcall SetLocationList(HKEY a1, __int64 *a2)
{
  LSTATUS result; // eax
  LSTATUS v4; // eax
  LSTATUS v5; // ebx
  __int64 v6; // rdi
  _DWORD *v7; // rsi
  HRESULT v8; // eax
  LPDWORD lpcchClass; // [rsp+38h] [rbp-19h]
  BYTE Data[8]; // [rsp+58h] [rbp+7h] BYREF
  DWORD cchName; // [rsp+60h] [rbp+Fh] BYREF
  DWORD dwDisposition; // [rsp+64h] [rbp+13h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+17h] BYREF
  HKEY phkResult; // [rsp+70h] [rbp+1Fh] BYREF
  WCHAR Name[12]; // [rsp+78h] [rbp+27h] BYREF

  cchName = 0;
  dwDisposition = 0;
  hKey = 0;
  phkResult = 0;
  result = RegCreateKeyExW(a1, L"Location", 0, (LPWSTR)&::Data, 0, 0x2000Eu, 0, &hKey, &dwDisposition);
  if ( !result )
  {
    do
    {
      cchName = 12;
      v4 = RegEnumKeyExW(hKey, 0, Name, &cchName, 0, 0, 0, 0);
      if ( v4 )
        break;
      v4 = RegDeleteKeyExW(hKey, Name, 0, 0);
    }
    while ( !v4 );
    v5 = 0;
    if ( v4 != 259 )
      v5 = v4;
    if ( !v5 )
    {
      v6 = *a2;
      if ( v6 )
      {
        do
        {
          v7 = *(_DWORD **)(v6 + 16);
          LODWORD(lpcchClass) = *v7;
          v8 = StringCchPrintfExW(Name, 0xCu, 0, 0, 0x100u, L"%d", lpcchClass);
          if ( v8 < 0 && g_dwTraceId != -1 )
            TracePrintfExA(g_dwTraceId, 0xCu, "LToT: StringCchPrintfEx failed. hr= 0x%x", v8);
          v5 = RegCreateKeyExW(hKey, Name, 0, (LPWSTR)&::Data, 0, 0x20006u, 0, &phkResult, &dwDisposition);
          if ( v5 )
            break;
          *(_DWORD *)Data = v7[1];
          v5 = RegSetValueExW(phkResult, L"Prefix", 0, 4u, Data, 4u);
          if ( !v5 )
          {
            *(_DWORD *)Data = v7[2];
            v5 = RegSetValueExW(phkResult, L"Suffix", 0, 4u, Data, 4u);
          }
          RegCloseKey(phkResult);
          if ( v5 )
            break;
          v6 = *(_QWORD *)(v6 + 8);
        }
        while ( v6 );
      }
      else
      {
        v5 = 0;
      }
    }
    RegCloseKey(hKey);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x1800c4504  mov     r11, rsp
0x1800c4507  mov     [r11+18h], rbx
0x1800c450b  mov     [r11+20h], rsi
0x1800c450f  push    rbp
0x1800c4510  push    rdi
0x1800c4511  push    r14
0x1800c4513  lea     rbp, [r11-5Fh]
0x1800c4517  sub     rsp, 90h
0x1800c451e  mov     rax, cs:__security_cookie
0x1800c4525  xor     rax, rsp
0x1800c4528  mov     [rbp+57h+var_18], rax
0x1800c452c  xor     r14d, r14d
0x1800c452f  lea     rax, [rbp+57h+dwDisposition]
0x1800c4533  mov     [r11-68h], rax
0x1800c4537  lea     r9, Data; lpClass
0x1800c453e  lea     rax, [rbp+57h+hKey]
0x1800c4542  mov     [rbp+57h+cchName], r14d
0x1800c4546  mov     [r11-70h], rax
0x1800c454a  mov     rdi, rdx
0x1800c454d  mov     [r11-78h], r14
0x1800c4551  lea     rdx, aLocation; "Location"
0x1800c4558  mov     [rsp+0A0h+samDesired], 2000Eh; samDesired
0x1800c4560  xor     r8d, r8d; Reserved
0x1800c4563  mov     [rsp+0A0h+dwOptions], r14d; dwOptions
0x1800c4568  mov     [rbp+57h+dwDisposition], r14d
0x1800c456c  mov     [rbp+57h+hKey], r14
0x1800c4570  mov     [rbp+57h+phkResult], r14
0x1800c4574  call    cs:__imp_RegCreateKeyExW
0x1800c457a  test    eax, eax
0x1800c457c  jnz     loc_1800C4719
0x1800c4582  mov     rcx, [rbp+57h+hKey]; hKey
0x1800c4586  lea     r9, [rbp+57h+cchName]; lpcchName
0x1800c458a  mov     [rsp+0A0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x1800c458f  lea     r8, [rbp+57h+Name]; lpName
0x1800c4593  mov     [rsp+0A0h+lpcchClass], r14; lpcchClass
0x1800c4598  xor     edx, edx; dwIndex
0x1800c459a  mov     qword ptr [rsp+0A0h+samDesired], r14; lpClass
0x1800c459f  mov     qword ptr [rsp+0A0h+dwOptions], r14; lpReserved
0x1800c45a4  mov     [rbp+57h+cchName], 0Ch
0x1800c45ab  call    cs:__imp_RegEnumKeyExW
0x1800c45b1  test    eax, eax
0x1800c45b3  jnz     short loc_1800C45CD
0x1800c45b5  mov     rcx, [rbp+57h+hKey]; hKey
0x1800c45b9  lea     rdx, [rbp+57h+Name]; lpSubKey
0x1800c45bd  xor     r9d, r9d; Reserved
0x1800c45c0  xor     r8d, r8d; samDesired
0x1800c45c3  call    cs:__imp_RegDeleteKeyExW
0x1800c45c9  test    eax, eax
0x1800c45cb  jz      short loc_1800C4582
0x1800c45cd  cmp     eax, 103h
0x1800c45d2  mov     ebx, r14d
0x1800c45d5  cmovnz  ebx, eax
0x1800c45d8  test    ebx, ebx
0x1800c45da  jnz     loc_1800C470D
0x1800c45e0  mov     rdi, [rdi]
0x1800c45e3  test    rdi, rdi
0x1800c45e6  jz      loc_1800C470A
0x1800c45ec  mov     rsi, [rdi+10h]
0x1800c45f0  lea     rcx, [rbp+57h+Name]; pszDest
0x1800c45f4  xor     r9d, r9d; pcchRemaining
0x1800c45f7  xor     r8d, r8d; ppszDestEnd
0x1800c45fa  mov     eax, [rsi]
0x1800c45fc  mov     dword ptr [rsp+0A0h+lpcchClass], eax
0x1800c4600  lea     edx, [r9+0Ch]; cchDest
0x1800c4604  lea     rax, aD; "%d"
0x1800c460b  mov     qword ptr [rsp+0A0h+samDesired], rax; pszFormat
0x1800c4610  mov     [rsp+0A0h+dwOptions], 100h; dwFlags
0x1800c4618  call    StringCchPrintfExW
0x1800c461d  test    eax, eax
0x1800c461f  jns     short loc_1800C4641
0x1800c4621  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800c4627  cmp     ecx, 0FFFFFFFFh
0x1800c462a  jz      short loc_1800C4641
0x1800c462c  mov     r9d, eax
0x1800c462f  lea     r8, aLtotStringcchp; "LToT: StringCchPrintfEx failed. hr= 0x%"...
0x1800c4636  mov     edx, 0Ch; dwFlags
0x1800c463b  call    cs:__imp_TracePrintfExA
0x1800c4641  mov     rcx, [rbp+57h+hKey]; hKey
0x1800c4645  lea     rax, [rbp+57h+dwDisposition]
0x1800c4649  mov     [rsp+0A0h+lpdwDisposition], rax; lpdwDisposition
0x1800c464e  lea     r9, Data; lpClass
0x1800c4655  lea     rax, [rbp+57h+phkResult]
0x1800c4659  xor     r8d, r8d; Reserved
0x1800c465c  mov     [rsp+0A0h+lpftLastWriteTime], rax; phkResult
0x1800c4661  lea     rdx, [rbp+57h+Name]; lpSubKey
0x1800c4665  mov     [rsp+0A0h+lpcchClass], r14; lpSecurityAttributes
0x1800c466a  mov     [rsp+0A0h+samDesired], 20006h; samDesired
0x1800c4672  mov     [rsp+0A0h+dwOptions], r14d; dwOptions
0x1800c4677  call    cs:__imp_RegCreateKeyExW
0x1800c467d  mov     ebx, eax
0x1800c467f  test    eax, eax
0x1800c4681  jnz     loc_1800C470D
0x1800c4687  mov     eax, [rsi+4]
0x1800c468a  lea     r9d, [rbx+4]; dwType
0x1800c468e  mov     rcx, [rbp+57h+phkResult]; hKey
0x1800c4692  lea     rdx, aPrefix; "Prefix"
0x1800c4699  mov     dword ptr [rbp+57h+Data], eax
0x1800c469c  xor     r8d, r8d; Reserved
0x1800c469f  lea     rax, [rbp+57h+Data]
0x1800c46a3  mov     [rsp+0A0h+samDesired], 4; cbData
0x1800c46ab  mov     qword ptr [rsp+0A0h+dwOptions], rax; lpData
0x1800c46b0  call    cs:__imp_RegSetValueExW
0x1800c46b6  mov     ebx, eax
0x1800c46b8  test    eax, eax
0x1800c46ba  jnz     short loc_1800C46ED
0x1800c46bc  mov     eax, [rsi+8]
0x1800c46bf  lea     r9d, [rbx+4]; dwType
0x1800c46c3  mov     rcx, [rbp+57h+phkResult]; hKey
0x1800c46c7  lea     rdx, aSuffix; "Suffix"
0x1800c46ce  mov     dword ptr [rbp+57h+Data], eax
0x1800c46d1  xor     r8d, r8d; Reserved
0x1800c46d4  lea     rax, [rbp+57h+Data]
0x1800c46d8  mov     [rsp+0A0h+samDesired], 4; cbData
0x1800c46e0  mov     qword ptr [rsp+0A0h+dwOptions], rax; lpData
0x1800c46e5  call    cs:__imp_RegSetValueExW
0x1800c46eb  mov     ebx, eax
0x1800c46ed  mov     rcx, [rbp+57h+phkResult]; hKey
0x1800c46f1  call    cs:__imp_RegCloseKey
0x1800c46f7  test    ebx, ebx
0x1800c46f9  jnz     short loc_1800C470D
0x1800c46fb  mov     rdi, [rdi+8]
0x1800c46ff  test    rdi, rdi
0x1800c4702  jnz     loc_1800C45EC
0x1800c4708  jmp     short loc_1800C470D
0x1800c470a  mov     ebx, r14d
0x1800c470d  mov     rcx, [rbp+57h+hKey]; hKey
0x1800c4711  call    cs:__imp_RegCloseKey
0x1800c4717  mov     eax, ebx
0x1800c4719  mov     rcx, [rbp+57h+var_18]
0x1800c471d  xor     rcx, rsp; StackCookie
0x1800c4720  call    __security_check_cookie
0x1800c4725  lea     r11, [rsp+0A0h+var_10]
0x1800c472d  mov     rbx, [r11+30h]
0x1800c4731  mov     rsi, [r11+38h]
0x1800c4735  mov     rsp, r11
0x1800c4738  pop     r14
0x1800c473a  pop     rdi
0x1800c473b  pop     rbp
0x1800c473c  retn
```
