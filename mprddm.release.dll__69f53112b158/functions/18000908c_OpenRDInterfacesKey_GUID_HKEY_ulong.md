# OpenRDInterfacesKey(_GUID *,HKEY__ * *,ulong &)

- ea: `0x18000908c`
- end: `0x1800093a7`
- name: `?OpenRDInterfacesKey@@YAKPEAU_GUID@@PEAPEAUHKEY__@@AEAK@Z`
- size: `795`
- prototype: `unsigned int(struct _GUID *, HKEY *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800093b0`

## callees

- `0x180007c0c`
- `0x18000908c`
- `0x1800755b8`
- `0x1800771b8`
- `0x180092a92`
- `0x180092ad0`

## import_xrefs

- `ADVAPI32!RegQueryInfoKeyW` at `0x1800092c8`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800092c8`
- `ADVAPI32!RegOpenKeyExW` at `0x180009128`
- `ADVAPI32!RegOpenKeyExW` at `0x1800091b2`
- `ADVAPI32!RegOpenKeyExW` at `0x18000922b`
- `ADVAPI32!RegOpenKeyExW` at `0x180009128`
- `ADVAPI32!RegOpenKeyExW` at `0x1800091b2`
- `ADVAPI32!RegOpenKeyExW` at `0x18000922b`
- `ADVAPI32!RegCloseKey` at `0x18000935c`
- `ADVAPI32!RegCloseKey` at `0x180009372`
- `ADVAPI32!RegCloseKey` at `0x18000935c`
- `ADVAPI32!RegCloseKey` at `0x180009372`

## string_xrefs

- `0x18000911a`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\RoutingDomains`
- `0x18000914f`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\RoutingDomains`
- `0x180009156`: `OpenRDInterfacesKey: Failed to open (%s) key, status = %d`
- `0x1800091dd`: `OpenRDInterfacesKey: Failed to open RDID (%s) key, status = %d`
- `0x180009252`: `OpenRDInterfacesKey: Failed to open <RDID>/Interfaces key, status = %d`
- `0x1800092ef`: `OpenRDInterfacesKey: GetKeyMax failed with error = %d`

## pseudocode

```c
__int64 __fastcall OpenRDInterfacesKey(struct _GUID *a1, HKEY *a2, unsigned int *a3)
{
  unsigned int v6; // eax
  __int64 v7; // rdx
  unsigned int v8; // ebx
  __int64 v9; // r8
  __int64 v10; // rax
  unsigned int v11; // eax
  unsigned int v12; // eax
  unsigned int v13; // eax
  DWORD cbMaxValueNameLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbMaxValueLen; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cValues; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v20[16]; // [rsp+80h] [rbp-80h] BYREF
  int *v21; // [rsp+90h] [rbp-70h]
  int v22; // [rsp+98h] [rbp-68h]
  int v23; // [rsp+9Ch] [rbp-64h]
  WCHAR SubKey[40]; // [rsp+A0h] [rbp-60h] BYREF
  int v25; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v26[2044]; // [rsp+F4h] [rbp-Ch] BYREF

  v25 = 0;
  memset_0(v26, 0, sizeof(v26));
  hKey = 0;
  phkResult = 0;
  cbMaxValueNameLen = 0;
  cValues = 0;
  cbMaxValueLen = 0;
  memset_0(SubKey, 0, sizeof(SubKey));
  *a2 = 0;
  *a3 = 0;
  v6 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\RoutingDomains",
         0,
         0xF003Fu,
         &hKey);
  v8 = v6;
  if ( v6 )
  {
    if ( (byte_1800CF404 & 8) != 0 )
    {
      LOWORD(v25) = 0;
      FormatRRASErrorString(
        &v25,
        L"OpenRDInterfacesKey: Failed to open (%s) key, status = %d",
        L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\RoutingDomains",
        v6);
      if ( (byte_1800CF404 & 8) != 0 )
      {
        v10 = -1;
        do
          ++v10;
        while ( *(_WORD *)&v26[2 * v10 - 4] );
LABEL_24:
        v23 = 0;
        v22 = 2 * v10 + 2;
        v21 = &v25;
        McGenEventWrite_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasDdmTraceError, v9, 2, v20);
      }
    }
  }
  else
  {
    MprConvertGuidToString(a1, v7, SubKey);
    v11 = RegOpenKeyExW(hKey, SubKey, 0, 0xF003Fu, &phkResult);
    v8 = v11;
    if ( v11 )
    {
      if ( (byte_1800CF404 & 8) != 0 )
      {
        LOWORD(v25) = 0;
        FormatRRASErrorString(&v25, L"OpenRDInterfacesKey: Failed to open RDID (%s) key, status = %d", SubKey, v11);
        if ( (byte_1800CF404 & 8) != 0 )
        {
          v10 = -1;
          do
            ++v10;
          while ( *(_WORD *)&v26[2 * v10 - 4] );
          goto LABEL_24;
        }
      }
    }
    else
    {
      v12 = RegOpenKeyExW(phkResult, L"Interfaces", 0, 0xF003Fu, a2);
      v8 = v12;
      if ( v12 )
      {
        if ( (byte_1800CF404 & 8) != 0 )
        {
          LOWORD(v25) = 0;
          FormatRRASErrorString(&v25, L"OpenRDInterfacesKey: Failed to open <RDID>/Interfaces key, status = %d", v12);
          if ( (byte_1800CF404 & 8) != 0 )
          {
            v10 = -1;
            do
              ++v10;
            while ( *(_WORD *)&v26[2 * v10 - 4] );
            goto LABEL_24;
          }
        }
      }
      else
      {
        v13 = RegQueryInfoKeyW(*a2, 0, 0, 0, a3, 0, 0, &cValues, &cbMaxValueNameLen, &cbMaxValueLen, 0, 0);
        ++cbMaxValueNameLen;
        v8 = v13;
        if ( v13 )
        {
          if ( (byte_1800CF404 & 8) != 0 )
          {
            LOWORD(v25) = 0;
            FormatRRASErrorString(&v25, L"OpenRDInterfacesKey: GetKeyMax failed with error = %d", v13);
            if ( (byte_1800CF404 & 8) != 0 )
            {
              v10 = -1;
              do
                ++v10;
              while ( *(_WORD *)&v26[2 * v10 - 4] );
              goto LABEL_24;
            }
          }
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  return v8;
}

```

## disassembly

```asm
0x18000908c  mov     [rsp-8+arg_18], rbx
0x180009091  push    rbp
0x180009092  push    rsi
0x180009093  push    rdi
0x180009094  push    r14
0x180009096  push    r15
0x180009098  lea     rbp, [rsp-800h]
0x1800090a0  sub     rsp, 900h
0x1800090a7  mov     rax, cs:__security_cookie
0x1800090ae  xor     rax, rsp
0x1800090b1  mov     [rbp+820h+var_30], rax
0x1800090b8  mov     rsi, r8
0x1800090bb  mov     rdi, rdx
0x1800090be  mov     r14, rcx
0x1800090c1  xor     r15d, r15d
0x1800090c4  xor     edx, edx; Val
0x1800090c6  mov     [rbp+820h+var_830], r15d
0x1800090ca  mov     r8d, 7FCh; Size
0x1800090d0  lea     rcx, [rbp+820h+var_82C]; void *
0x1800090d4  call    memset_0
0x1800090d9  xor     edx, edx; Val
0x1800090db  mov     [rsp+920h+hKey], r15
0x1800090e0  lea     r8d, [r15+50h]; Size
0x1800090e4  mov     [rsp+920h+var_8A8], r15
0x1800090e9  lea     rcx, [rbp+820h+SubKey]; void *
0x1800090ed  mov     [rsp+920h+cbMaxValueNameLen], r15d
0x1800090f2  mov     [rsp+920h+cValues], r15d
0x1800090f7  mov     [rsp+920h+cbMaxValueLen], r15d
0x1800090fc  call    memset_0
0x180009101  lea     rax, [rsp+920h+hKey]
0x180009106  mov     [rdi], r15
0x180009109  mov     r9d, 0F003Fh; samDesired
0x18000910f  mov     [rsp+920h+phkResult], rax; phkResult
0x180009114  xor     r8d, r8d; ulOptions
0x180009117  mov     [rsi], r15d
0x18000911a  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x180009121  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180009128  call    cs:__imp_RegOpenKeyExW
0x18000912f  nop     dword ptr [rax+rax+00h]
0x180009134  mov     ebx, eax
0x180009136  test    eax, eax
0x180009138  jz      short loc_18000918A
0x18000913a  test    cs:byte_1800CF404, 8
0x180009141  jz      loc_180009352
0x180009147  mov     r9d, eax
0x18000914a  mov     word ptr [rbp+820h+var_830], r15w
0x18000914f  lea     r8, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x180009156  lea     rdx, aOpenrdinterfac; "OpenRDInterfacesKey: Failed to open (%s"...
0x18000915d  lea     rcx, [rbp+820h+var_830]
0x180009161  call    FormatRRASErrorString
0x180009166  test    cs:byte_1800CF404, 8
0x18000916d  jz      loc_180009352
0x180009173  lea     rcx, [rbp+820h+var_830]
0x180009177  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000917b  inc     rax
0x18000917e  cmp     [rcx+rax*2], r15w
0x180009183  jnz     short loc_18000917B
0x180009185  jmp     loc_18000931A
0x18000918a  lea     r8, [rbp+820h+SubKey]
0x18000918e  mov     rcx, r14
0x180009191  call    MprConvertGuidToString
0x180009196  mov     rcx, [rsp+920h+hKey]; hKey
0x18000919b  lea     rax, [rsp+920h+var_8A8]
0x1800091a0  mov     r9d, 0F003Fh; samDesired
0x1800091a6  mov     [rsp+920h+phkResult], rax; phkResult
0x1800091ab  xor     r8d, r8d; ulOptions
0x1800091ae  lea     rdx, [rbp+820h+SubKey]; lpSubKey
0x1800091b2  call    cs:__imp_RegOpenKeyExW
0x1800091b9  nop     dword ptr [rax+rax+00h]
0x1800091be  mov     ebx, eax
0x1800091c0  test    eax, eax
0x1800091c2  jz      short loc_180009211
0x1800091c4  test    cs:byte_1800CF404, 8
0x1800091cb  jz      loc_180009352
0x1800091d1  mov     r9d, eax
0x1800091d4  mov     word ptr [rbp+820h+var_830], r15w
0x1800091d9  lea     r8, [rbp+820h+SubKey]
0x1800091dd  lea     rdx, aOpenrdinterfac_2; "OpenRDInterfacesKey: Failed to open RDI"...
0x1800091e4  lea     rcx, [rbp+820h+var_830]
0x1800091e8  call    FormatRRASErrorString
0x1800091ed  test    cs:byte_1800CF404, 8
0x1800091f4  jz      loc_180009352
0x1800091fa  lea     rcx, [rbp+820h+var_830]
0x1800091fe  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009202  inc     rax
0x180009205  cmp     [rcx+rax*2], r15w
0x18000920a  jnz     short loc_180009202
0x18000920c  jmp     loc_18000931A
0x180009211  mov     rcx, [rsp+920h+var_8A8]; hKey
0x180009216  lea     rdx, aInterfaces; "Interfaces"
0x18000921d  mov     r9d, 0F003Fh; samDesired
0x180009223  mov     [rsp+920h+phkResult], rdi; phkResult
0x180009228  xor     r8d, r8d; ulOptions
0x18000922b  call    cs:__imp_RegOpenKeyExW
0x180009232  nop     dword ptr [rax+rax+00h]
0x180009237  mov     ebx, eax
0x180009239  test    eax, eax
0x18000923b  jz      short loc_180009286
0x18000923d  test    cs:byte_1800CF404, 8
0x180009244  jz      loc_180009352
0x18000924a  mov     r8d, eax
0x18000924d  mov     word ptr [rbp+820h+var_830], r15w
0x180009252  lea     rdx, aOpenrdinterfac_1; "OpenRDInterfacesKey: Failed to open <RD"...
0x180009259  lea     rcx, [rbp+820h+var_830]
0x18000925d  call    FormatRRASErrorString
0x180009262  test    cs:byte_1800CF404, 8
0x180009269  jz      loc_180009352
0x18000926f  lea     rcx, [rbp+820h+var_830]
0x180009273  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009277  inc     rax
0x18000927a  cmp     [rcx+rax*2], r15w
0x18000927f  jnz     short loc_180009277
0x180009281  jmp     loc_18000931A
0x180009286  mov     rcx, [rdi]; hKey
0x180009289  lea     rax, [rsp+920h+cbMaxValueLen]
0x18000928e  mov     [rsp+920h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180009293  xor     r9d, r9d; lpReserved
0x180009296  mov     [rsp+920h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18000929b  xor     r8d, r8d; lpcchClass
0x18000929e  mov     [rsp+920h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1800092a3  xor     edx, edx; lpClass
0x1800092a5  lea     rax, [rsp+920h+cbMaxValueNameLen]
0x1800092aa  mov     [rsp+920h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800092af  lea     rax, [rsp+920h+cValues]
0x1800092b4  mov     [rsp+920h+lpcValues], rax; lpcValues
0x1800092b9  mov     [rsp+920h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800092be  mov     [rsp+920h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800092c3  mov     [rsp+920h+phkResult], rsi; lpcSubKeys
0x1800092c8  call    cs:__imp_RegQueryInfoKeyW
0x1800092cf  nop     dword ptr [rax+rax+00h]
0x1800092d4  inc     [rsp+920h+cbMaxValueNameLen]
0x1800092d8  mov     ebx, eax
0x1800092da  test    eax, eax
0x1800092dc  jz      short loc_180009352
0x1800092de  test    cs:byte_1800CF404, 8
0x1800092e5  jz      short loc_180009352
0x1800092e7  mov     r8d, eax
0x1800092ea  mov     word ptr [rbp+820h+var_830], r15w
0x1800092ef  lea     rdx, aOpenrdinterfac_0; "OpenRDInterfacesKey: GetKeyMax failed w"...
0x1800092f6  lea     rcx, [rbp+820h+var_830]
0x1800092fa  call    FormatRRASErrorString
0x1800092ff  test    cs:byte_1800CF404, 8
0x180009306  jz      short loc_180009352
0x180009308  lea     rcx, [rbp+820h+var_830]
0x18000930c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180009310  inc     rax
0x180009313  cmp     [rcx+rax*2], r15w
0x180009318  jnz     short loc_180009310
0x18000931a  lea     eax, ds:2[rax*2]
0x180009321  mov     [rbp+820h+var_884], r15d
0x180009325  lea     rcx, [rbp+820h+var_830]
0x180009329  mov     [rbp+820h+var_888], eax
0x18000932c  lea     rax, [rbp+820h+var_8A0]
0x180009330  mov     [rbp+820h+var_890], rcx
0x180009334  mov     r9d, 2
0x18000933a  mov     [rsp+920h+phkResult], rax
0x18000933f  lea     rdx, RasDdmTraceError
0x180009346  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000934d  call    McGenEventWrite_EventWriteTransfer
0x180009352  mov     rcx, [rsp+920h+hKey]; hKey
0x180009357  test    rcx, rcx
0x18000935a  jz      short loc_180009368
0x18000935c  call    cs:__imp_RegCloseKey
0x180009363  nop     dword ptr [rax+rax+00h]
0x180009368  mov     rcx, [rsp+920h+var_8A8]; hKey
0x18000936d  test    rcx, rcx
0x180009370  jz      short loc_18000937E
0x180009372  call    cs:__imp_RegCloseKey
0x180009379  nop     dword ptr [rax+rax+00h]
0x18000937e  mov     eax, ebx
0x180009380  mov     rcx, [rbp+820h+var_30]
0x180009387  xor     rcx, rsp; StackCookie
0x18000938a  call    __security_check_cookie
0x18000938f  mov     rbx, [rsp+920h+arg_18]
0x180009397  add     rsp, 900h
0x18000939e  pop     r15
0x1800093a0  pop     r14
0x1800093a2  pop     rdi
0x1800093a3  pop     rsi
0x1800093a4  pop     rbp
0x1800093a5  retn
```
