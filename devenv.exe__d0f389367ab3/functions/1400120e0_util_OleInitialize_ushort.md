# util_OleInitialize(ushort *)

- ea: `0x1400120e0`
- end: `0x140012313`
- name: `?util_OleInitialize@@YAJPEAG@Z`
- size: `563`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14000ccfc`

## callees

- `0x140001020`
- `0x1400120e0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140012223`
- `ADVAPI32!RegCloseKey` at `0x140012223`
- `ADVAPI32!RegOpenKeyExW` at `0x140012176`
- `ADVAPI32!RegOpenKeyExW` at `0x140012176`
- `ADVAPI32!RegQueryValueExW` at `0x1400121b4`
- `ADVAPI32!RegQueryValueExW` at `0x1400121fe`
- `ADVAPI32!RegQueryValueExW` at `0x1400121b4`
- `ADVAPI32!RegQueryValueExW` at `0x1400121fe`
- `KERNEL32!Sleep` at `0x140012138`
- `KERNEL32!Sleep` at `0x140012138`
- `ole32!CoInitializeSecurity` at `0x140012297`
- `ole32!CoInitializeSecurity` at `0x140012297`
- `ole32!OleInitialize` at `0x140012127`
- `ole32!OleInitialize` at `0x140012127`
- `ole32!IIDFromString` at `0x140012218`
- `ole32!IIDFromString` at `0x140012218`
- `ole32!CoCreateInstance` at `0x1400122bd`
- `ole32!CoCreateInstance` at `0x1400122bd`

## string_xrefs

- `0x1400121ad`: `EnableSecurity`
- `0x1400121f7`: `SecurityAppID`

## pseudocode

```c
__int64 __fastcall util_OleInitialize(LPCWSTR lpSubKey)
{
  BOOL v2; // esi
  int v3; // edi
  HRESULT v4; // ebx
  HRESULT v5; // eax
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD Type; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cbData; // [rsp+5Ch] [rbp-A4h] BYREF
  BYTE Data[4]; // [rsp+60h] [rbp-A0h] BYREF
  DWORD dwImpLevel; // [rsp+64h] [rbp-9Ch] BYREF
  IID iid; // [rsp+68h] [rbp-98h] BYREF
  OLECHAR v13[264]; // [rsp+80h] [rbp-80h] BYREF

  v2 = 1;
  v3 = 0;
  iid = GUID_NULL;
  while ( 1 )
  {
    v4 = OleInitialize(0);
    if ( v4 >= 0 )
      break;
    Sleep(0x1388u);
    if ( ++v3 >= 15 )
    {
      _mm_lfence();
      return (unsigned int)v4;
    }
  }
  _mm_lfence();
  if ( !lpSubKey || RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey) )
    goto LABEL_15;
  cbData = 4;
  if ( !RegQueryValueExW(hKey, L"EnableSecurity", 0, &Type, Data, &cbData) && Type == 4 )
    v2 = *(_DWORD *)Data == 0;
  dwImpLevel = 520;
  if ( !RegQueryValueExW(hKey, L"SecurityAppID", 0, &Type, (LPBYTE)v13, &dwImpLevel) && Type == 1 )
    IIDFromString(v13, &iid);
  RegCloseKey(hKey);
  if ( v2 )
  {
LABEL_15:
    if ( *(_QWORD *)&iid.Data1 == *(_QWORD *)&GUID_NULL.Data1 && *(_QWORD *)iid.Data4 == *(_QWORD *)GUID_NULL.Data4 )
      v5 = CoInitializeSecurity(0, -1, 0, 0, 0, 2u, 0, 0, 0);
    else
      v5 = CoInitializeSecurity(&iid, -1, 0, 0, 0, 0, 0, 8u, 0);
    v4 = v5;
    if ( CoCreateInstance(&CLSID_GlobalOptions, 0, 1u, &GUID_0000015b_0000_0000_c000_000000000046, (LPVOID *)&hKey) >= 0
      && hKey )
    {
      (*(void (__fastcall **)(HKEY, __int64, __int64))(*(_QWORD *)hKey + 24LL))(hKey, 1, 2);
      (*(void (__fastcall **)(HKEY))(*(_QWORD *)hKey + 16LL))(hKey);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1400120e0  mov     [rsp-8+arg_8], rbx
0x1400120e5  mov     [rsp-8+arg_10], rsi
0x1400120ea  push    rbp
0x1400120eb  push    rdi
0x1400120ec  push    r14
0x1400120ee  lea     rbp, [rsp-1A0h]
0x1400120f6  sub     rsp, 2A0h
0x1400120fd  mov     rax, cs:__security_cookie
0x140012104  xor     rax, rsp
0x140012107  mov     [rbp+1B0h+var_20], rax
0x14001210e  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x140012115  mov     r14, rcx
0x140012118  mov     esi, 1
0x14001211d  xor     edi, edi
0x14001211f  movdqu  xmmword ptr [rsp+2B0h+iid.Data1], xmm0
0x140012125  xor     ecx, ecx; pvReserved
0x140012127  call    cs:__imp_OleInitialize
0x14001212d  mov     ebx, eax
0x14001212f  test    eax, eax
0x140012131  jns     short loc_14001214D
0x140012133  mov     ecx, 1388h; dwMilliseconds
0x140012138  call    cs:__imp_Sleep
0x14001213e  inc     edi
0x140012140  cmp     edi, 0Fh
0x140012143  jl      short loc_140012125
0x140012145  lfence
0x140012148  jmp     loc_1400122EA
0x14001214d  lfence
0x140012150  test    r14, r14
0x140012153  jz      loc_140012231
0x140012159  lea     rax, [rsp+2B0h+hKey]
0x14001215e  mov     r9d, 20019h; samDesired
0x140012164  xor     r8d, r8d; ulOptions
0x140012167  mov     [rsp+2B0h+phkResult], rax; phkResult
0x14001216c  mov     rdx, r14; lpSubKey
0x14001216f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140012176  call    cs:__imp_RegOpenKeyExW
0x14001217c  test    eax, eax
0x14001217e  jnz     loc_140012231
0x140012184  mov     rcx, [rsp+2B0h+hKey]; hKey
0x140012189  lea     rax, [rsp+2B0h+cbData]
0x14001218e  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x140012193  lea     r9, [rsp+2B0h+Type]; lpType
0x140012198  lea     rax, [rsp+2B0h+Data]
0x14001219d  mov     [rsp+2B0h+cbData], 4
0x1400121a5  xor     r8d, r8d; lpReserved
0x1400121a8  mov     [rsp+2B0h+phkResult], rax; lpData
0x1400121ad  lea     rdx, aEnablesecurity; "EnableSecurity"
0x1400121b4  call    cs:__imp_RegQueryValueExW
0x1400121ba  test    eax, eax
0x1400121bc  jnz     short loc_1400121CF
0x1400121be  cmp     [rsp+2B0h+Type], 4
0x1400121c3  jnz     short loc_1400121CF
0x1400121c5  xor     esi, esi
0x1400121c7  cmp     dword ptr [rsp+2B0h+Data], esi
0x1400121cb  setz    sil
0x1400121cf  mov     rcx, [rsp+2B0h+hKey]; hKey
0x1400121d4  lea     rax, [rsp+2B0h+dwImpLevel]
0x1400121d9  mov     [rsp+2B0h+lpcbData], rax; dwImpLevel
0x1400121de  lea     r9, [rsp+2B0h+Type]; lpType
0x1400121e3  lea     rax, [rbp+1B0h+var_230]
0x1400121e7  mov     [rsp+2B0h+dwImpLevel], 208h
0x1400121ef  xor     r8d, r8d; lpReserved
0x1400121f2  mov     [rsp+2B0h+phkResult], rax; dwAuthnLevel
0x1400121f7  lea     rdx, aSecurityappid; "SecurityAppID"
0x1400121fe  call    cs:__imp_RegQueryValueExW
0x140012204  test    eax, eax
0x140012206  jnz     short loc_14001221E
0x140012208  cmp     [rsp+2B0h+Type], 1
0x14001220d  jnz     short loc_14001221E
0x14001220f  lea     rdx, [rsp+2B0h+iid]; lpiid
0x140012214  lea     rcx, [rbp+1B0h+var_230]; lpsz
0x140012218  call    cs:__imp_IIDFromString
0x14001221e  mov     rcx, [rsp+2B0h+hKey]; hKey
0x140012223  call    cs:__imp_RegCloseKey
0x140012229  test    esi, esi
0x14001222b  jz      loc_1400122EA
0x140012231  mov     rax, qword ptr [rsp+2B0h+iid.Data1]
0x140012236  mov     edi, 2
0x14001223b  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x140012242  jnz     short loc_14001226B
0x140012244  mov     rax, qword ptr [rsp+2B0h+iid.Data4]
0x140012249  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x140012250  jnz     short loc_14001226B
0x140012252  and     [rsp+2B0h+var_270], 0
0x140012258  and     [rsp+2B0h+dwCapabilities], 0
0x14001225d  and     [rsp+2B0h+var_280], 0
0x140012263  xor     ecx, ecx
0x140012265  mov     dword ptr [rsp+2B0h+lpcbData], edi
0x140012269  jmp     short loc_140012289
0x14001226b  and     [rsp+2B0h+var_270], 0
0x140012271  lea     rcx, [rsp+2B0h+iid]; pSecDesc
0x140012276  mov     [rsp+2B0h+dwCapabilities], 8; dwCapabilities
0x14001227e  and     [rsp+2B0h+var_280], 0
0x140012284  and     dword ptr [rsp+2B0h+lpcbData], 0
0x140012289  and     dword ptr [rsp+2B0h+phkResult], 0
0x14001228e  xor     r9d, r9d; pReserved1
0x140012291  xor     r8d, r8d; asAuthSvc
0x140012294  or      edx, 0FFFFFFFFh; cAuthSvc
0x140012297  call    cs:__imp_CoInitializeSecurity
0x14001229d  xor     edx, edx; pUnkOuter
0x14001229f  lea     r9, _GUID_0000015b_0000_0000_c000_000000000046; riid
0x1400122a6  mov     ebx, eax
0x1400122a8  lea     rcx, CLSID_GlobalOptions; rclsid
0x1400122af  lea     rax, [rsp+2B0h+hKey]
0x1400122b4  mov     [rsp+2B0h+phkResult], rax; ppv
0x1400122b9  lea     r8d, [rdx+1]; dwClsContext
0x1400122bd  call    cs:__imp_CoCreateInstance
0x1400122c3  test    eax, eax
0x1400122c5  js      short loc_1400122EA
0x1400122c7  mov     rcx, [rsp+2B0h+hKey]
0x1400122cc  test    rcx, rcx
0x1400122cf  jz      short loc_1400122EA
0x1400122d1  mov     rax, [rcx]
0x1400122d4  mov     r8, rdi
0x1400122d7  mov     edx, 1
0x1400122dc  call    qword ptr [rax+18h]
0x1400122df  mov     rcx, [rsp+2B0h+hKey]
0x1400122e4  mov     rax, [rcx]
0x1400122e7  call    qword ptr [rax+10h]
0x1400122ea  mov     eax, ebx
0x1400122ec  mov     rcx, [rbp+1B0h+var_20]
0x1400122f3  xor     rcx, rsp; StackCookie
0x1400122f6  call    __security_check_cookie
0x1400122fb  lea     r11, [rsp+2B0h+var_10]
0x140012303  mov     rbx, [r11+28h]
0x140012307  mov     rsi, [r11+30h]
0x14001230b  mov     rsp, r11
0x14001230e  pop     r14
0x140012310  pop     rdi
0x140012311  pop     rbp
0x140012312  retn
```
