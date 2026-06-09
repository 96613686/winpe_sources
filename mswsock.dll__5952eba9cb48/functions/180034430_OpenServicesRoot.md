# OpenServicesRoot

- ea: `0x180034430`
- end: `0x180034689`
- name: `OpenServicesRoot`
- size: `601`
- prototype: `__int64 __fastcall(PHKEY phkResult)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x1800328c0`

## callees

- `0x1800222f0`
- `0x1800327a8`
- `0x180034430`
- `0x180038118`
- `0x18003847c`
- `0x18003ae8c`
- `0x180053010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800344e5`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1800344e5`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180034521`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18003454c`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180034577`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800345a2`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800345cb`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180034521`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x18003454c`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180034577`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800345a2`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800345cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800345ec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800345ec`

## string_xrefs

- `0x180034483`: `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services`
- `0x1800344d4`: `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services`
- `0x18003449b`: `Could not translate path`
- `0x180034654`: `Unknown registry root`
- `0x1800345fe`: `Could not open key`

## pseudocode

```c
__int64 __fastcall OpenServicesRoot(PHKEY phkResult, __int64 a2)
{
  __int64 (__fastcall *v2)(__int64, const wchar_t *, __int64, wchar_t *, _DWORD *); // rax
  unsigned int v4; // eax
  unsigned int v5; // ebx
  unsigned __int64 v6; // rbx
  wchar_t *v7; // rax
  unsigned int v8; // eax
  const wchar_t *v9; // rdx
  __int64 v10; // rcx
  _DWORD v12[4]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t Str[520]; // [rsp+40h] [rbp-C0h] BYREF

  v2 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, wchar_t *, _DWORD *))(a2 + 8);
  if ( v2 )
  {
    v12[0] = 0;
    v4 = v2(1, L"HKEY_LOCAL_MACHINE\\System\\CurrentControlSet\\Services", 520, Str, v12);
    v5 = v4;
    if ( v4 )
    {
      LogError(v4, L"Could not translate path");
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_d(1025, 16, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids, v5);
      return v5;
    }
  }
  else
  {
    _o_wcscpy_s(Str, 520, L"HKEY_LOCAL_MACHINE\\System\\CurrentControlSet\\Services");
  }
  if ( (xmmword_180063D60 & 2) != 0 )
    WPP_SF_S(1025, 17, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids, Str);
  if ( wcsstr(Str, L"HKEY_LOCAL_MACHINE") == Str )
  {
    v6 = -2147483646;
  }
  else if ( wcsstr(Str, L"HKEY_CURRENT_USER") == Str )
  {
    v6 = -2147483647;
  }
  else if ( wcsstr(Str, L"HKEY_CLASSES_ROOT") == Str )
  {
    v6 = 0xFFFFFFFF80000000uLL;
  }
  else
  {
    if ( wcsstr(Str, L"HKEY_USERS") != Str )
    {
      if ( (xmmword_180063D60 & 2) != 0 )
        WPP_SF_q(1025, 18, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids, 0);
      v5 = 3;
      v9 = L"Unknown registry root";
      v10 = 3;
      goto LABEL_23;
    }
    v6 = -2147483645;
  }
  v7 = wcsstr(Str, L"\\");
  v8 = RegOpenKeyExW((HKEY)v6, v7 + 1, 0, 0x20019u, phkResult);
  v5 = v8;
  if ( v8 )
  {
    v9 = L"Could not open key";
    v10 = v8;
LABEL_23:
    LogError(v10, v9);
    return v5;
  }
  if ( (xmmword_180063D60 & 2) != 0 )
    WPP_SF_q(1025, 19, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids, *phkResult);
  return v5;
}

```

## disassembly

```asm
0x180034430  mov     [rsp-8+arg_10], rbx
0x180034435  mov     [rsp-8+arg_18], rsi
0x18003443a  push    rbp
0x18003443b  lea     rbp, [rsp-360h]
0x180034443  sub     rsp, 460h
0x18003444a  mov     rax, cs:__security_cookie
0x180034451  xor     rax, rsp
0x180034454  mov     [rbp+360h+var_10], rax
0x18003445b  mov     rax, [rdx+8]
0x18003445f  mov     rsi, rcx
0x180034462  test    rax, rax
0x180034465  jz      short loc_1800344D4
0x180034467  lea     rcx, [rsp+460h+var_430]
0x18003446c  mov     [rsp+460h+var_430], 0
0x180034474  mov     [rsp+460h+phkResult], rcx
0x180034479  lea     r9, [rsp+460h+Str]
0x18003447e  mov     ecx, 1
0x180034483  lea     rdx, aHkeyLocalMachi_0; "HKEY_LOCAL_MACHINE\\System\\CurrentCont"...
0x18003448a  mov     r8d, 208h
0x180034490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034495  mov     ebx, eax
0x180034497  test    eax, eax
0x180034499  jz      short loc_1800344F1
0x18003449b  lea     rdx, aCouldNotTransl; "Could not translate path"
0x1800344a2  mov     ecx, eax
0x1800344a4  call    LogError
0x1800344a9  test    byte ptr cs:xmmword_180063D60, 2
0x1800344b0  jz      loc_180034662
0x1800344b6  mov     edx, 10h
0x1800344bb  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x1800344c2  mov     ecx, 401h
0x1800344c7  mov     r9d, ebx
0x1800344ca  call    WPP_SF_d
0x1800344cf  jmp     loc_180034662
0x1800344d4  lea     r8, aHkeyLocalMachi_0; "HKEY_LOCAL_MACHINE\\System\\CurrentCont"...
0x1800344db  mov     edx, 208h
0x1800344e0  lea     rcx, [rsp+460h+Str]
0x1800344e5  call    cs:__imp__o_wcscpy_s
0x1800344ec  nop     dword ptr [rax+rax+00h]
0x1800344f1  test    byte ptr cs:xmmword_180063D60, 2
0x1800344f8  jz      short loc_180034515
0x1800344fa  mov     edx, 11h
0x1800344ff  lea     r9, [rsp+460h+Str]
0x180034504  mov     ecx, 401h
0x180034509  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x180034510  call    WPP_SF_S
0x180034515  lea     rdx, aHkeyLocalMachi; "HKEY_LOCAL_MACHINE"
0x18003451c  lea     rcx, [rsp+460h+Str]; Str
0x180034521  call    cs:__imp_wcsstr
0x180034528  nop     dword ptr [rax+rax+00h]
0x18003452d  lea     rcx, [rsp+460h+Str]
0x180034532  cmp     rax, rcx
0x180034535  jnz     short loc_180034540
0x180034537  mov     rbx, 0FFFFFFFF80000002h
0x18003453e  jmp     short loc_1800345BF
0x180034540  lea     rdx, aHkeyCurrentUse; "HKEY_CURRENT_USER"
0x180034547  lea     rcx, [rsp+460h+Str]; Str
0x18003454c  call    cs:__imp_wcsstr
0x180034553  nop     dword ptr [rax+rax+00h]
0x180034558  lea     rcx, [rsp+460h+Str]
0x18003455d  cmp     rax, rcx
0x180034560  jnz     short loc_18003456B
0x180034562  mov     rbx, 0FFFFFFFF80000001h
0x180034569  jmp     short loc_1800345BF
0x18003456b  lea     rdx, aHkeyClassesRoo; "HKEY_CLASSES_ROOT"
0x180034572  lea     rcx, [rsp+460h+Str]; Str
0x180034577  call    cs:__imp_wcsstr
0x18003457e  nop     dword ptr [rax+rax+00h]
0x180034583  lea     rcx, [rsp+460h+Str]
0x180034588  cmp     rax, rcx
0x18003458b  jnz     short loc_180034596
0x18003458d  mov     rbx, 0FFFFFFFF80000000h
0x180034594  jmp     short loc_1800345BF
0x180034596  lea     rdx, aHkeyUsers; "HKEY_USERS"
0x18003459d  lea     rcx, [rsp+460h+Str]; Str
0x1800345a2  call    cs:__imp_wcsstr
0x1800345a9  nop     dword ptr [rax+rax+00h]
0x1800345ae  lea     rcx, [rsp+460h+Str]
0x1800345b3  cmp     rax, rcx
0x1800345b6  jnz     short loc_18003462D
0x1800345b8  mov     rbx, 0FFFFFFFF80000003h
0x1800345bf  lea     rdx, asc_180055EA0; "\\"
0x1800345c6  lea     rcx, [rsp+460h+Str]; Str
0x1800345cb  call    cs:__imp_wcsstr
0x1800345d2  nop     dword ptr [rax+rax+00h]
0x1800345d7  mov     r9d, 20019h; samDesired
0x1800345dd  mov     [rsp+460h+phkResult], rsi; phkResult
0x1800345e2  xor     r8d, r8d; ulOptions
0x1800345e5  mov     rcx, rbx; hKey
0x1800345e8  lea     rdx, [rax+2]; lpSubKey
0x1800345ec  call    cs:__imp_RegOpenKeyExW
0x1800345f3  nop     dword ptr [rax+rax+00h]
0x1800345f8  mov     ebx, eax
0x1800345fa  test    eax, eax
0x1800345fc  jz      short loc_180034609
0x1800345fe  lea     rdx, aCouldNotOpenKe; "Could not open key"
0x180034605  mov     ecx, eax
0x180034607  jmp     short loc_18003465D
0x180034609  test    byte ptr cs:xmmword_180063D60, 2
0x180034610  jz      short loc_180034662
0x180034612  mov     r9, [rsi]
0x180034615  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x18003461c  mov     edx, 13h
0x180034621  mov     ecx, 401h
0x180034626  call    WPP_SF_q
0x18003462b  jmp     short loc_180034662
0x18003462d  test    byte ptr cs:xmmword_180063D60, 2
0x180034634  jz      short loc_18003464F
0x180034636  mov     edx, 12h
0x18003463b  lea     r8, WPP_4593deb55ead3582b257adde53a3fabd_Traceguids
0x180034642  mov     ecx, 401h
0x180034647  xor     r9d, r9d
0x18003464a  call    WPP_SF_q
0x18003464f  mov     ebx, 3
0x180034654  lea     rdx, aUnknownRegistr; "Unknown registry root"
0x18003465b  mov     ecx, ebx
0x18003465d  call    LogError
0x180034662  mov     eax, ebx
0x180034664  mov     rcx, [rbp+360h+var_10]
0x18003466b  xor     rcx, rsp; StackCookie
0x18003466e  call    __security_check_cookie
0x180034673  lea     r11, [rsp+460h+var_s0]
0x18003467b  mov     rbx, [r11+20h]
0x18003467f  mov     rsi, [r11+28h]
0x180034683  mov     rsp, r11
0x180034686  pop     rbp
0x180034687  retn
```
