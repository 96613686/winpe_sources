# NotifyDownloadViaToast

- ea: `0x18000711c`
- end: `0x180007396`
- name: `NotifyDownloadViaToast`
- size: `634`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180006000`

## callees

- `0x18000711c`
- `0x180008618`
- `0x180008b1c`
- `0x180008d14`
- `0x18000933c`
- `0x1800a49c4`
- `0x1800a4e18`
- `0x1800f82f0`
- `0x180108e50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800072ad`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800072ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007208`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000736a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180007208`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000736a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800071df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800071df`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000716a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18000716a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007217`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007253`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007217`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007253`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000719f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18000719f`

## string_xrefs

- `0x180007170`: `C:\__w\1\s\src\DeliveryOptimization\dll\dosvc.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall NotifyDownloadViaToast(unsigned __int8 a1, void *a2)
{
  unsigned int v2; // esi
  HKEY v3; // rbx
  const char *v4; // r9
  int LastError; // edi
  const char *v6; // r9
  unsigned int v7; // eax
  HRESULT Instance; // eax
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v11; // eax
  __int64 v12; // rcx
  int ReturnLength; // [rsp+20h] [rbp-59h]
  unsigned int ReturnLengtha; // [rsp+20h] [rbp-59h]
  int ReturnLengthb; // [rsp+20h] [rbp-59h]
  DWORD v17[2]; // [rsp+38h] [rbp-41h] BYREF
  unsigned int v18; // [rsp+40h] [rbp-39h] BYREF
  LPWSTR StringSid; // [rsp+48h] [rbp-31h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-29h] BYREF
  PSID TokenInformation[10]; // [rsp+60h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v2 = a1;
  v3 = 0;
  v17[0] = 0;
  if ( GetTokenInformation(a2, TokenUser, TokenInformation, 0x44u, v17) )
  {
    StringSid = 0;
    if ( ConvertSidToStringSidW(TokenInformation[0], &StringSid) )
    {
      phkResult = 0;
      v7 = RegOpenKeyExW(HKEY_USERS, StringSid, 0, 0x2001Fu, &phkResult);
      if ( !v7 )
      {
        v3 = phkResult;
        phkResult = 0;
        if ( StringSid )
          LocalFree(StringSid);
        goto LABEL_14;
      }
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x2C9,
                    (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\dosvc.cpp",
                    (const char *)v7,
                    ReturnLengtha);
      if ( phkResult )
        RegCloseKey(phkResult);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x2C6,
                    (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\dosvc.cpp",
                    v6);
    }
    if ( StringSid )
      LocalFree(StringSid);
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x2C3,
                  (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\dosvc.cpp",
                  v4);
  }
  if ( LastError < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D2,
      (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\dosvc.cpp",
      (const char *)(unsigned int)LastError,
      ReturnLength);
    goto LABEL_28;
  }
LABEL_14:
  v18 = 0;
  if ( (int)RegQueryDwordValue(v3, "SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\DeliveryOptimization", "Toast", &v18) >= 0
    && v18 )
  {
LABEL_27:
    LastError = 0;
    goto LABEL_28;
  }
  *(_QWORD *)v17 = 0;
  Instance = CoCreateInstance(
               &GUID_338b40f9_9d68_4b53_a793_6b9aa0c5f63b,
               0,
               4u,
               &GUID_8863f93e_77ea_4c67_a86f_7638e3a568a6,
               (LPVOID *)v17);
  LastError = Instance;
  if ( Instance < 0 )
  {
    v9 = 731;
    goto LABEL_20;
  }
  Instance = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)v17 + 24LL))(*(_QWORD *)v17, v2);
  LastError = Instance;
  if ( Instance >= 0 )
  {
    v11 = RegSetDwordValue(v3, "SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\DeliveryOptimization", "Toast", 1u);
    if ( v11 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2DD,
        (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\dosvc.cpp",
        (const char *)(unsigned int)v11,
        ReturnLengthb);
    v12 = *(_QWORD *)v17;
    if ( *(_QWORD *)v17 )
    {
      *(_QWORD *)v17 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    goto LABEL_27;
  }
  v9 = 732;
LABEL_20:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"C:\\__w\\1\\s\\src\\DeliveryOptimization\\dll\\dosvc.cpp",
    (const char *)(unsigned int)Instance,
    ReturnLengthb);
  v10 = *(_QWORD *)v17;
  if ( *(_QWORD *)v17 )
  {
    *(_QWORD *)v17 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
LABEL_28:
  if ( v3 )
    RegCloseKey(v3);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18000711c  mov     [rsp-8+arg_10], rbx
0x180007121  mov     [rsp-8+arg_18], rsi
0x180007126  push    rbp
0x180007127  push    rdi
0x180007128  push    r15
0x18000712a  lea     rbp, [rsp-47h]
0x18000712f  sub     rsp, 0C0h
0x180007136  mov     rax, cs:__security_cookie
0x18000713d  xor     rax, rsp
0x180007140  mov     [rbp+57h+var_20], rax
0x180007144  mov     rax, rdx
0x180007147  movzx   esi, cl
0x18000714a  xor     ebx, ebx
0x18000714c  mov     [rbp+57h+var_A0], rbx
0x180007150  mov     [rbp+57h+var_98], ebx
0x180007153  lea     rcx, [rbp+57h+var_98]
0x180007157  mov     qword ptr [rsp+0D0h+ReturnLength], rcx; ReturnLength
0x18000715c  lea     r9d, [rbx+44h]; TokenInformationLength
0x180007160  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180007164  lea     edx, [rbx+1]; TokenInformationClass
0x180007167  mov     rcx, rax; TokenHandle
0x18000716a  call    cs:__imp_GetTokenInformation
0x180007170  lea     r15, aCW1SSrcDeliver_56; "C:\\__w\\1\\s\\src\\DeliveryOptimizatio"...
0x180007177  test    eax, eax
0x180007179  jnz     short loc_180007193
0x18000717b  mov     rcx, [rbp+5Fh]; this
0x18000717f  mov     r8, r15; unsigned int
0x180007182  mov     edx, 2C3h; void *
0x180007187  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000718c  mov     edi, eax
0x18000718e  jmp     loc_18000721D
0x180007193  mov     [rbp+57h+StringSid], rbx
0x180007197  lea     rdx, [rbp+57h+StringSid]; StringSid
0x18000719b  mov     rcx, [rbp+57h+TokenInformation]; Sid
0x18000719f  call    cs:__imp_ConvertSidToStringSidW
0x1800071a5  test    eax, eax
0x1800071a7  jnz     short loc_1800071BE
0x1800071a9  mov     rcx, [rbp+5Fh]; this
0x1800071ad  mov     r8, r15; unsigned int
0x1800071b0  mov     edx, 2C6h; void *
0x1800071b5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800071ba  mov     edi, eax
0x1800071bc  jmp     short loc_18000720E
0x1800071be  mov     [rbp+57h+phkResult], rbx
0x1800071c2  lea     rax, [rbp+57h+phkResult]
0x1800071c6  mov     qword ptr [rsp+0D0h+ReturnLength], rax; int
0x1800071cb  mov     r9d, 2001Fh; samDesired
0x1800071d1  xor     r8d, r8d; ulOptions
0x1800071d4  mov     rdx, [rbp+57h+StringSid]; lpSubKey
0x1800071d8  mov     rcx, 0FFFFFFFF80000003h; hKey
0x1800071df  call    cs:__imp_RegOpenKeyExW
0x1800071e5  test    eax, eax
0x1800071e7  jz      short loc_18000723A
0x1800071e9  mov     rcx, [rbp+5Fh]; this
0x1800071ed  mov     r9d, eax; char *
0x1800071f0  mov     r8, r15; unsigned int
0x1800071f3  mov     edx, 2C9h; void *
0x1800071f8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800071fd  mov     edi, eax
0x1800071ff  mov     rcx, [rbp+57h+phkResult]; hKey
0x180007203  test    rcx, rcx
0x180007206  jz      short loc_18000720E
0x180007208  call    cs:__imp_RegCloseKey
0x18000720e  mov     rcx, [rbp+57h+StringSid]; hMem
0x180007212  test    rcx, rcx
0x180007215  jz      short loc_18000721D
0x180007217  call    cs:__imp_LocalFree
0x18000721d  test    edi, edi
0x18000721f  jns     short loc_180007259
0x180007221  mov     rcx, [rbp+5Fh]; this
0x180007225  mov     r9d, edi; char *
0x180007228  mov     r8, r15; unsigned int
0x18000722b  mov     edx, 2D2h; void *
0x180007230  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007235  jmp     loc_180007362
0x18000723a  mov     rbx, [rbp+57h+phkResult]
0x18000723e  mov     [rbp+57h+phkResult], 0
0x180007246  mov     [rbp+57h+var_A0], rbx
0x18000724a  mov     rcx, [rbp+57h+StringSid]; hMem
0x18000724e  test    rcx, rcx
0x180007251  jz      short loc_180007259
0x180007253  call    cs:__imp_LocalFree
0x180007259  mov     [rbp+57h+var_90], 0
0x180007260  lea     r9, [rbp+57h+var_90]; unsigned int *
0x180007264  lea     r8, aToast; "Toast"
0x18000726b  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180007272  mov     rcx, rbx; HKEY
0x180007275  call    ?RegQueryDwordValue@@YAJPEAUHKEY__@@PEBD1PEAI@Z; RegQueryDwordValue(HKEY__ *,char const *,char const *,uint *)
0x18000727a  test    eax, eax
0x18000727c  js      short loc_180007288
0x18000727e  cmp     [rbp+57h+var_90], 0
0x180007282  jnz     loc_180007360
0x180007288  mov     qword ptr [rbp+57h+var_98], 0
0x180007290  lea     rax, [rbp+57h+var_98]
0x180007294  mov     qword ptr [rsp+0D0h+ReturnLength], rax; int
0x180007299  lea     r9, _GUID_8863f93e_77ea_4c67_a86f_7638e3a568a6; riid
0x1800072a0  xor     edx, edx; pUnkOuter
0x1800072a2  lea     r8d, [rdx+4]; dwClsContext
0x1800072a6  lea     rcx, _GUID_338b40f9_9d68_4b53_a793_6b9aa0c5f63b; rclsid
0x1800072ad  call    cs:__imp_CoCreateInstance
0x1800072b3  mov     edi, eax
0x1800072b5  test    eax, eax
0x1800072b7  jns     short loc_1800072C0
0x1800072b9  mov     edx, 2DBh
0x1800072be  jmp     short loc_1800072DD
0x1800072c0  mov     edx, esi
0x1800072c2  mov     rcx, qword ptr [rbp+57h+var_98]
0x1800072c6  mov     rax, [rcx]
0x1800072c9  mov     rax, [rax+18h]
0x1800072cd  call    _guard_dispatch_icall
0x1800072d2  mov     edi, eax
0x1800072d4  test    eax, eax
0x1800072d6  jns     short loc_18000730D
0x1800072d8  mov     edx, 2DCh; void *
0x1800072dd  mov     r9d, eax; char *
0x1800072e0  mov     r8, r15; unsigned int
0x1800072e3  mov     rcx, [rbp+5Fh]; this
0x1800072e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800072ec  nop
0x1800072ed  mov     rcx, qword ptr [rbp+57h+var_98]
0x1800072f1  test    rcx, rcx
0x1800072f4  jz      short loc_18000730B
0x1800072f6  mov     qword ptr [rbp+57h+var_98], 0
0x1800072fe  mov     rax, [rcx]
0x180007301  mov     rax, [rax+10h]
0x180007305  call    _guard_dispatch_icall
0x18000730a  nop
0x18000730b  jmp     short loc_180007362
0x18000730d  mov     r9d, 1; unsigned int
0x180007313  lea     r8, aToast; "Toast"
0x18000731a  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180007321  mov     rcx, rbx; HKEY
0x180007324  call    ?RegSetDwordValue@@YAJPEAUHKEY__@@PEBD1I@Z; RegSetDwordValue(HKEY__ *,char const *,char const *,uint)
0x180007329  mov     rcx, [rbp+5Fh]; this
0x18000732d  test    eax, eax
0x18000732f  jns     short loc_180007342
0x180007331  mov     r9d, eax; char *
0x180007334  mov     r8, r15; unsigned int
0x180007337  mov     edx, 2DDh; void *
0x18000733c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180007341  nop
0x180007342  mov     rcx, qword ptr [rbp+57h+var_98]
0x180007346  test    rcx, rcx
0x180007349  jz      short loc_180007360
0x18000734b  mov     qword ptr [rbp+57h+var_98], 0
0x180007353  mov     rax, [rcx]
0x180007356  mov     rax, [rax+10h]
0x18000735a  call    _guard_dispatch_icall
0x18000735f  nop
0x180007360  xor     edi, edi
0x180007362  test    rbx, rbx
0x180007365  jz      short loc_180007370
0x180007367  mov     rcx, rbx; hKey
0x18000736a  call    cs:__imp_RegCloseKey
0x180007370  mov     eax, edi
0x180007372  mov     rcx, [rbp+57h+var_20]
0x180007376  xor     rcx, rsp; StackCookie
0x180007379  call    __security_check_cookie
0x18000737e  lea     r11, [rsp+0D0h+var_10]
0x180007386  mov     rbx, [r11+30h]
0x18000738a  mov     rsi, [r11+38h]
0x18000738e  mov     rsp, r11
0x180007391  pop     r15
0x180007393  pop     rdi
0x180007394  pop     rbp
0x180007395  retn
```
