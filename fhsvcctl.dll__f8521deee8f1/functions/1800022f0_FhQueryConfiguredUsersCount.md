# FhQueryConfiguredUsersCount

- ea: `0x1800022f0`
- end: `0x180002530`
- name: `FhQueryConfiguredUsersCount`
- size: `576`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task`

## callees

- `0x1800022f0`
- `0x180002538`
- `0x180002578`
- `0x1800025cc`
- `0x180002628`
- `0x180004f20`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180002509`
- `ADVAPI32!RegCloseKey` at `0x180002509`
- `ADVAPI32!RegEnumValueW` at `0x180002438`
- `ADVAPI32!RegEnumValueW` at `0x1800024ec`
- `ADVAPI32!RegEnumValueW` at `0x180002438`
- `ADVAPI32!RegEnumValueW` at `0x1800024ec`
- `ADVAPI32!RegOpenKeyExW` at `0x18000238f`
- `ADVAPI32!RegOpenKeyExW` at `0x18000238f`

## string_xrefs

- `0x18000234b`: `ConfiguredUsers`
- `0x180002385`: `System\CurrentControlSet\Services\fhsvc\Parameters\Configs`

## pseudocode

```c
__int64 __fastcall FhQueryConfiguredUsersCount(_DWORD *a1)
{
  LSTATUS v3; // eax
  unsigned int v4; // ebx
  DWORD v5; // r15d
  __int64 v6; // rdx
  int i; // esi
  __int64 v8; // r8
  _QWORD *v9; // rcx
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  BYTE Data[4]; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchValueName; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR ValueName[264]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = 0;
  if ( a1 )
  {
    *a1 = 0;
    v3 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"System\\CurrentControlSet\\Services\\fhsvc\\Parameters\\Configs",
           0,
           9u,
           &hKey);
    v4 = v3;
    if ( v3 == 2 )
    {
      v4 = 0;
    }
    else if ( v3 )
    {
      if ( v3 > 0 )
        v4 = (unsigned __int16)v3 | 0x80070000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_f8f99a6abf3431f29ed4a99639276213_Traceguids, v4);
    }
    else
    {
      v4 = 0;
      cbData = 4;
      *(_DWORD *)Data = 0;
      v5 = 0;
      cchValueName = 261;
      for ( i = RegEnumValueW(hKey, 0, ValueName, &cchValueName, 0, 0, Data, &cbData);
            i != 259;
            i = RegEnumValueW(hKey, v5, ValueName, &cchValueName, 0, 0, Data, &cbData) )
      {
        if ( i )
        {
          v9 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
            {
              WPP_SF_ss(*((_QWORD *)WPP_GLOBAL_Control + 2));
              v9 = WPP_GLOBAL_Control;
            }
            if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 )
            {
              if ( i > 0 )
                i = (unsigned __int16)i | 0x80070000;
              WPP_SF_dd(v9[2], v6, v8, v5, i);
            }
          }
        }
        else
        {
          ++*a1;
        }
        *(_DWORD *)Data = 0;
        ++v5;
        cbData = 4;
        cchValueName = 261;
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
    return v4;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_s(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        10,
        &WPP_f8f99a6abf3431f29ed4a99639276213_Traceguids,
        "ConfiguredUsers");
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x1800022f0  push    rbp
0x1800022f2  push    rbx
0x1800022f3  push    rsi
0x1800022f4  push    rdi
0x1800022f5  push    r14
0x1800022f7  push    r15
0x1800022f9  lea     rbp, [rsp-188h]
0x180002301  sub     rsp, 288h
0x180002308  mov     rax, cs:__security_cookie
0x18000230f  xor     rax, rsp
0x180002312  mov     [rbp+1B0h+var_40], rax
0x180002319  mov     [rsp+2B0h+hKey], 0
0x180002322  mov     r14, rcx
0x180002325  test    rcx, rcx
0x180002328  jnz     short loc_180002368
0x18000232a  mov     rcx, cs:WPP_GLOBAL_Control
0x180002331  lea     rdi, WPP_GLOBAL_Control
0x180002338  cmp     rcx, rdi
0x18000233b  jz      short loc_18000235E
0x18000233d  test    byte ptr [rcx+1Ch], 1
0x180002341  jz      short loc_18000235E
0x180002343  mov     rcx, [rcx+10h]
0x180002347  lea     edx, [r14+0Ah]
0x18000234b  lea     r9, aConfigureduser; "ConfiguredUsers"
0x180002352  lea     r8, WPP_f8f99a6abf3431f29ed4a99639276213_Traceguids
0x180002359  call    WPP_SF_s
0x18000235e  mov     eax, 80070057h
0x180002363  jmp     loc_180002511
0x180002368  mov     dword ptr [rcx], 0
0x18000236e  lea     rax, [rsp+2B0h+hKey]
0x180002373  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000237a  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18000237f  mov     r9d, 9; samDesired
0x180002385  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\fh"...
0x18000238c  xor     r8d, r8d; ulOptions
0x18000238f  call    cs:__imp_RegOpenKeyExW
0x180002395  mov     ebx, eax
0x180002397  cmp     eax, 2
0x18000239a  jnz     short loc_1800023A3
0x18000239c  xor     ebx, ebx
0x18000239e  jmp     loc_1800024FF
0x1800023a3  test    eax, eax
0x1800023a5  jz      short loc_1800023F0
0x1800023a7  jle     short loc_1800023B2
0x1800023a9  movzx   ebx, ax
0x1800023ac  or      ebx, 80070000h
0x1800023b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800023b9  lea     rdi, WPP_GLOBAL_Control
0x1800023c0  cmp     rcx, rdi
0x1800023c3  jz      loc_1800024FF
0x1800023c9  test    byte ptr [rcx+1Ch], 1
0x1800023cd  jz      loc_1800024FF
0x1800023d3  mov     rcx, [rcx+10h]
0x1800023d7  lea     r8, WPP_f8f99a6abf3431f29ed4a99639276213_Traceguids
0x1800023de  mov     edx, 0Bh
0x1800023e3  mov     r9d, ebx
0x1800023e6  call    WPP_SF_d
0x1800023eb  jmp     loc_1800024FF
0x1800023f0  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800023f5  lea     rax, [rsp+2B0h+cbData]
0x1800023fa  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x1800023ff  lea     r9, [rsp+2B0h+cchValueName]; lpcchValueName
0x180002404  xor     ebx, ebx
0x180002406  mov     [rsp+2B0h+cbData], 4
0x18000240e  lea     rax, [rsp+2B0h+Data]
0x180002413  mov     dword ptr [rsp+2B0h+Data], ebx
0x180002417  mov     [rsp+2B0h+lpData], rax; lpData
0x18000241c  lea     r8, [rsp+2B0h+ValueName]; lpValueName
0x180002421  mov     [rsp+2B0h+lpType], rbx; lpType
0x180002426  xor     edx, edx; dwIndex
0x180002428  mov     [rsp+2B0h+phkResult], rbx; lpReserved
0x18000242d  xor     r15d, r15d
0x180002430  mov     [rsp+2B0h+cchValueName], 105h
0x180002438  call    cs:__imp_RegEnumValueW
0x18000243e  mov     esi, eax
0x180002440  cmp     eax, 103h
0x180002445  jz      loc_1800024FF
0x18000244b  lea     rdi, WPP_GLOBAL_Control
0x180002452  test    esi, esi
0x180002454  jz      short loc_1800024A2
0x180002456  mov     rcx, cs:WPP_GLOBAL_Control
0x18000245d  cmp     rcx, rdi
0x180002460  jz      short loc_1800024A5
0x180002462  test    byte ptr [rcx+1Ch], 4
0x180002466  jz      short loc_180002478
0x180002468  mov     rcx, [rcx+10h]
0x18000246c  call    WPP_SF_ss
0x180002471  mov     rcx, cs:WPP_GLOBAL_Control
0x180002478  cmp     rcx, rdi
0x18000247b  jz      short loc_1800024A5
0x18000247d  test    byte ptr [rcx+1Ch], 1
0x180002481  jz      short loc_1800024A5
0x180002483  test    esi, esi
0x180002485  jle     short loc_180002490
0x180002487  movzx   esi, si
0x18000248a  or      esi, 80070000h
0x180002490  mov     rcx, [rcx+10h]
0x180002494  mov     r9d, r15d
0x180002497  mov     dword ptr [rsp+2B0h+phkResult], esi
0x18000249b  call    WPP_SF_dd
0x1800024a0  jmp     short loc_1800024A5
0x1800024a2  inc     dword ptr [r14]
0x1800024a5  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1800024aa  lea     rax, [rsp+2B0h+cbData]
0x1800024af  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x1800024b4  lea     r9, [rsp+2B0h+cchValueName]; lpcchValueName
0x1800024b9  lea     rax, [rsp+2B0h+Data]
0x1800024be  mov     dword ptr [rsp+2B0h+Data], ebx
0x1800024c2  mov     [rsp+2B0h+lpData], rax; lpData
0x1800024c7  lea     r8, [rsp+2B0h+ValueName]; lpValueName
0x1800024cc  inc     r15d
0x1800024cf  mov     [rsp+2B0h+lpType], rbx; lpType
0x1800024d4  mov     edx, r15d; dwIndex
0x1800024d7  mov     [rsp+2B0h+phkResult], rbx; lpReserved
0x1800024dc  mov     [rsp+2B0h+cbData], 4
0x1800024e4  mov     [rsp+2B0h+cchValueName], 105h
0x1800024ec  call    cs:__imp_RegEnumValueW
0x1800024f2  mov     esi, eax
0x1800024f4  cmp     eax, 103h
0x1800024f9  jnz     loc_180002452
0x1800024ff  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180002504  test    rcx, rcx
0x180002507  jz      short loc_18000250F
0x180002509  call    cs:__imp_RegCloseKey
0x18000250f  mov     eax, ebx
0x180002511  mov     rcx, [rbp+1B0h+var_40]
0x180002518  xor     rcx, rsp; StackCookie
0x18000251b  call    __security_check_cookie
0x180002520  add     rsp, 288h
0x180002527  pop     r15
0x180002529  pop     r14
0x18000252b  pop     rdi
0x18000252c  pop     rsi
0x18000252d  pop     rbx
0x18000252e  pop     rbp
0x18000252f  retn
```
