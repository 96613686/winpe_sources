# IASRadiusGetPingUserName(void)

- ea: `0x180014840`
- end: `0x180014a19`
- name: `?IASRadiusGetPingUserName@@YAPEAGXZ`
- size: `473`
- prototype: `unsigned __int16 *(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x180014d54`

## callees

- `0x1800094e4`
- `0x180014840`
- `0x18001d31c`
- `0x18002df44`
- `0x18002e230`
- `0x18002e2f0`
- `0x180030010`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1800148ac`
- `ADVAPI32!RegQueryValueExW` at `0x1800149ee`
- `ADVAPI32!RegQueryValueExW` at `0x1800148ac`
- `ADVAPI32!RegQueryValueExW` at `0x1800149ee`
- `ADVAPI32!RegOpenKeyW` at `0x180014876`
- `ADVAPI32!RegOpenKeyW` at `0x180014876`
- `ADVAPI32!RegCloseKey` at `0x180014a0e`
- `ADVAPI32!RegCloseKey` at `0x180014a0e`
- `OLEAUT32!__imp_SysAllocString` at `0x180014a01`
- `OLEAUT32!__imp_SysAllocString` at `0x180014a01`

## string_xrefs

- `0x180014868`: `SYSTEM\CurrentControlSet\Services\IAS\Parameters`

## pseudocode

```c
BSTR IASRadiusGetPingUserName(void)
{
  BSTR v0; // rsi
  unsigned __int64 v1; // rdi
  OLECHAR *lpData; // rbx
  __int64 v3; // rcx
  unsigned __int64 v4; // rcx
  void *v5; // rsp
  void *v6; // rsp
  _DWORD *v7; // rax
  __int64 v9; // [rsp+0h] [rbp-30h] BYREF
  DWORD Type; // [rsp+30h] [rbp+0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp+4h] BYREF
  HKEY phkResult[2]; // [rsp+38h] [rbp+8h] BYREF

  phkResult[0] = 0;
  if ( RegOpenKeyW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\IAS\\Parameters", phkResult) )
    return 0;
  v0 = 0;
  cbData = 0;
  Type = 0;
  if ( !RegQueryValueExW(phkResult[0], L"Ping User-Name", 0, &Type, 0, &cbData) && Type == 1 )
  {
    v1 = cbData;
    lpData = 0;
    if ( !cbData
      || cbData > (unsigned __int64)g_ulMaxStackAllocSize
      || (unsigned __int64)cbData + g_ulAdditionalProbeSize + 8 < cbData
      || !(unsigned int)VerifyStackAvailable() )
    {
      goto LABEL_12;
    }
    v3 = v1 + 23;
    if ( v1 + 23 <= v1 + 8 )
      v3 = 0xFFFFFFFFFFFFFF0LL;
    v4 = v3 & 0xFFFFFFFFFFFFFFF0uLL;
    v5 = alloca(v4);
    v6 = alloca(v4);
    lpData = (OLECHAR *)&Type;
    if ( &v9 == (__int64 *)-48LL || (Type = 1801679955, (lpData = (OLECHAR *)phkResult) == 0) )
    {
LABEL_12:
      if ( v1 + 8 >= v1 )
      {
        v7 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
        if ( !v7 )
        {
LABEL_16:
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
          {
            WppDbgPrint("[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVEL! %!MOD! %!FUNC! %!FILE!@%!LINE!]Not enough memory to st"
                        "ore attribute information");
            WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_3c79d53b094e365fc1974d230e285c1c_Traceguids, "NPSRAD");
          }
          return 0;
        }
        *v7 = 1885431112;
        lpData = (OLECHAR *)(v7 + 2);
      }
      if ( !lpData )
        goto LABEL_16;
    }
    if ( !RegQueryValueExW(phkResult[0], L"Ping User-Name", 0, &Type, (LPBYTE)lpData, &cbData) && Type == 1 )
      v0 = SysAllocString(lpData);
  }
  RegCloseKey(phkResult[0]);
  return v0;
}

```

## disassembly

```asm
0x180014840  push    rbp
0x180014842  push    rbx
0x180014843  push    rsi
0x180014844  push    rdi
0x180014845  sub     rsp, 58h
0x180014849  lea     rbp, [rsp+30h]
0x18001484e  mov     rax, cs:__security_cookie
0x180014855  xor     rax, rbp
0x180014858  mov     [rbp+40h+var_28], rax
0x18001485c  lea     r8, [rbp+40h+phkResult]; phkResult
0x180014860  mov     [rbp+40h+phkResult], 0
0x180014868  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\IA"...
0x18001486f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180014876  call    cs:__imp_RegOpenKeyW
0x18001487c  test    eax, eax
0x18001487e  jnz     loc_1800149B7
0x180014884  mov     rcx, [rbp+40h+phkResult]; hKey
0x180014888  lea     rax, [rbp+40h+cbData]
0x18001488c  xor     esi, esi
0x18001488e  mov     [rsp+70h+lpcbData], rax; lpcbData
0x180014893  lea     r9, [rbp+40h+Type]; lpType
0x180014897  mov     [rsp+70h+lpData], rsi; lpData
0x18001489c  xor     r8d, r8d; lpReserved
0x18001489f  mov     [rbp+40h+cbData], esi
0x1800148a2  lea     rdx, ValueName; "Ping User-Name"
0x1800148a9  mov     [rbp+40h+Type], esi
0x1800148ac  call    cs:__imp_RegQueryValueExW
0x1800148b2  test    eax, eax
0x1800148b4  jnz     loc_180014A0A
0x1800148ba  cmp     [rbp+40h+Type], 1
0x1800148be  jnz     loc_180014A0A
0x1800148c4  mov     edi, [rbp+40h+cbData]
0x1800148c7  xor     ebx, ebx
0x1800148c9  test    rdi, rdi
0x1800148cc  jz      short loc_180014933
0x1800148ce  cmp     rdi, cs:g_ulMaxStackAllocSize
0x1800148d5  ja      short loc_180014933
0x1800148d7  mov     rcx, cs:g_ulAdditionalProbeSize
0x1800148de  add     rcx, 8
0x1800148e2  add     rcx, rdi
0x1800148e5  cmp     rcx, rdi
0x1800148e8  jb      short loc_180014933
0x1800148ea  call    VerifyStackAvailable
0x1800148ef  test    eax, eax
0x1800148f1  jz      short loc_180014933
0x1800148f3  lea     rax, [rdi+8]
0x1800148f7  lea     rcx, [rax+0Fh]
0x1800148fb  cmp     rcx, rax
0x1800148fe  ja      short loc_18001490A
0x180014900  mov     rcx, 0FFFFFFFFFFFFFF0h
0x18001490a  and     rcx, 0FFFFFFFFFFFFFFF0h
0x18001490e  mov     rax, rcx
0x180014911  call    _alloca_probe
0x180014916  sub     rsp, rcx
0x180014919  lea     rbx, [rsp+70h+Type]
0x18001491e  test    rbx, rbx
0x180014921  jz      short loc_180014933
0x180014923  mov     dword ptr [rbx], 6B637453h
0x180014929  add     rbx, 8
0x18001492d  jnz     loc_1800149CE
0x180014933  lea     rcx, [rdi+8]
0x180014937  cmp     rcx, rdi
0x18001493a  jb      short loc_18001495A
0x18001493c  mov     rax, cs:g_pfnAllocate
0x180014943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014948  mov     rbx, rax
0x18001494b  test    rax, rax
0x18001494e  jz      short loc_18001495F
0x180014950  mov     dword ptr [rax], 70616548h
0x180014956  add     rbx, 8
0x18001495a  test    rbx, rbx
0x18001495d  jnz     short loc_1800149CE
0x18001495f  mov     rax, cs:WPP_GLOBAL_Control
0x180014966  lea     rcx, WPP_GLOBAL_Control
0x18001496d  cmp     rax, rcx
0x180014970  jz      short loc_1800149B7
0x180014972  cmp     byte ptr [rax+19h], 2
0x180014976  jb      short loc_1800149B7
0x180014978  test    dword ptr [rax+1Ch], 100h
0x18001497f  jz      short loc_1800149B7
0x180014981  lea     rdx, aNpsrad; "NPSRAD"
0x180014988  lea     rcx, aCpuPidTidNowSL_0; "[%!CPU!]%!PID!.%!TID! %!NOW! [%s %!LEVE"...
0x18001498f  call    WppDbgPrint
0x180014994  mov     rcx, cs:WPP_GLOBAL_Control
0x18001499b  lea     r9, aNpsrad; "NPSRAD"
0x1800149a2  mov     edx, 0Ah
0x1800149a7  lea     r8, WPP_3c79d53b094e365fc1974d230e285c1c_Traceguids
0x1800149ae  mov     rcx, [rcx+10h]
0x1800149b2  call    WPP_SF_s
0x1800149b7  xor     eax, eax
0x1800149b9  mov     rcx, [rbp+40h+var_28]
0x1800149bd  xor     rcx, rbp; StackCookie
0x1800149c0  call    __security_check_cookie
0x1800149c5  lea     rsp, [rbp+28h]
0x1800149c9  pop     rdi
0x1800149ca  pop     rsi
0x1800149cb  pop     rbx
0x1800149cc  pop     rbp
0x1800149cd  retn
0x1800149ce  mov     rcx, [rbp+40h+phkResult]; hKey
0x1800149d2  lea     rax, [rbp+40h+cbData]
0x1800149d6  mov     [rsp+70h+lpcbData], rax; lpcbData
0x1800149db  lea     r9, [rbp+40h+Type]; lpType
0x1800149df  xor     r8d, r8d; lpReserved
0x1800149e2  mov     [rsp+70h+lpData], rbx; lpData
0x1800149e7  lea     rdx, ValueName; "Ping User-Name"
0x1800149ee  call    cs:__imp_RegQueryValueExW
0x1800149f4  test    eax, eax
0x1800149f6  jnz     short loc_180014A0A
0x1800149f8  cmp     [rbp+40h+Type], 1
0x1800149fc  jnz     short loc_180014A0A
0x1800149fe  mov     rcx, rbx; psz
0x180014a01  call    cs:__imp_SysAllocString
0x180014a07  mov     rsi, rax
0x180014a0a  mov     rcx, [rbp+40h+phkResult]; hKey
0x180014a0e  call    cs:__imp_RegCloseKey
0x180014a14  mov     rax, rsi
0x180014a17  jmp     short loc_1800149B9
```
