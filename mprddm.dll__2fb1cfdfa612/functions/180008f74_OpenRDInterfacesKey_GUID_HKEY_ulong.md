# OpenRDInterfacesKey(_GUID *,HKEY__ * *,ulong &)

- ea: `0x180008f74`
- end: `0x18000926a`
- name: `?OpenRDInterfacesKey@@YAKPEAU_GUID@@PEAPEAUHKEY__@@AEAK@Z`
- size: `758`
- prototype: `unsigned int(struct _GUID *, HKEY *, unsigned int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180009270`

## callees

- `0x180007b7c`
- `0x180008f74`
- `0x180071cec`
- `0x180073664`
- `0x18008c5f2`
- `0x18008c630`

## import_xrefs

- `ADVAPI32!RegQueryInfoKeyW` at `0x18000919e`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000919e`
- `ADVAPI32!RegOpenKeyExW` at `0x180009010`
- `ADVAPI32!RegOpenKeyExW` at `0x180009094`
- `ADVAPI32!RegOpenKeyExW` at `0x180009107`
- `ADVAPI32!RegOpenKeyExW` at `0x180009010`
- `ADVAPI32!RegOpenKeyExW` at `0x180009094`
- `ADVAPI32!RegOpenKeyExW` at `0x180009107`
- `ADVAPI32!RegCloseKey` at `0x18000922c`
- `ADVAPI32!RegCloseKey` at `0x18000923c`
- `ADVAPI32!RegCloseKey` at `0x18000922c`
- `ADVAPI32!RegCloseKey` at `0x18000923c`

## string_xrefs

- `0x180009002`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\RoutingDomains`
- `0x180009031`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\RoutingDomains`
- `0x180009038`: `OpenRDInterfacesKey: Failed to open (%s) key, status = %d`
- `0x1800090b9`: `OpenRDInterfacesKey: Failed to open RDID (%s) key, status = %d`
- `0x180009128`: `OpenRDInterfacesKey: Failed to open <RDID>/Interfaces key, status = %d`
- `0x1800091bf`: `OpenRDInterfacesKey: GetKeyMax failed with error = %d`

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
    if ( (byte_1800C8404 & 8) != 0 )
    {
      LOWORD(v25) = 0;
      FormatRRASErrorString(
        &v25,
        L"OpenRDInterfacesKey: Failed to open (%s) key, status = %d",
        L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\RoutingDomains",
        v6);
      if ( (byte_1800C8404 & 8) != 0 )
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
      if ( (byte_1800C8404 & 8) != 0 )
      {
        LOWORD(v25) = 0;
        FormatRRASErrorString(&v25, L"OpenRDInterfacesKey: Failed to open RDID (%s) key, status = %d", SubKey, v11);
        if ( (byte_1800C8404 & 8) != 0 )
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
        if ( (byte_1800C8404 & 8) != 0 )
        {
          LOWORD(v25) = 0;
          FormatRRASErrorString(&v25, L"OpenRDInterfacesKey: Failed to open <RDID>/Interfaces key, status = %d", v12);
          if ( (byte_1800C8404 & 8) != 0 )
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
          if ( (byte_1800C8404 & 8) != 0 )
          {
            LOWORD(v25) = 0;
            FormatRRASErrorString(&v25, L"OpenRDInterfacesKey: GetKeyMax failed with error = %d", v13);
            if ( (byte_1800C8404 & 8) != 0 )
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
0x180008f74  mov     [rsp-8+arg_18], rbx
0x180008f79  push    rbp
0x180008f7a  push    rsi
0x180008f7b  push    rdi
0x180008f7c  push    r14
0x180008f7e  push    r15
0x180008f80  lea     rbp, [rsp-800h]
0x180008f88  sub     rsp, 900h
0x180008f8f  mov     rax, cs:__security_cookie
0x180008f96  xor     rax, rsp
0x180008f99  mov     [rbp+820h+var_30], rax
0x180008fa0  mov     rsi, r8
0x180008fa3  mov     rdi, rdx
0x180008fa6  mov     r14, rcx
0x180008fa9  xor     r15d, r15d
0x180008fac  xor     edx, edx; Val
0x180008fae  mov     [rbp+820h+var_830], r15d
0x180008fb2  mov     r8d, 7FCh; Size
0x180008fb8  lea     rcx, [rbp+820h+var_82C]; void *
0x180008fbc  call    memset_0
0x180008fc1  xor     edx, edx; Val
0x180008fc3  mov     [rsp+920h+hKey], r15
0x180008fc8  lea     r8d, [r15+50h]; Size
0x180008fcc  mov     [rsp+920h+var_8A8], r15
0x180008fd1  lea     rcx, [rbp+820h+SubKey]; void *
0x180008fd5  mov     [rsp+920h+cbMaxValueNameLen], r15d
0x180008fda  mov     [rsp+920h+cValues], r15d
0x180008fdf  mov     [rsp+920h+cbMaxValueLen], r15d
0x180008fe4  call    memset_0
0x180008fe9  lea     rax, [rsp+920h+hKey]
0x180008fee  mov     [rdi], r15
0x180008ff1  mov     r9d, 0F003Fh; samDesired
0x180008ff7  mov     [rsp+920h+phkResult], rax; phkResult
0x180008ffc  xor     r8d, r8d; ulOptions
0x180008fff  mov     [rsi], r15d
0x180009002  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x180009009  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180009010  call    cs:__imp_RegOpenKeyExW
0x180009016  mov     ebx, eax
0x180009018  test    eax, eax
0x18000901a  jz      short loc_18000906C
0x18000901c  test    cs:byte_1800C8404, 8
0x180009023  jz      loc_180009222
0x180009029  mov     r9d, eax
0x18000902c  mov     word ptr [rbp+820h+var_830], r15w
0x180009031  lea     r8, SubKey; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x180009038  lea     rdx, aOpenrdinterfac; "OpenRDInterfacesKey: Failed to open (%s"...
0x18000903f  lea     rcx, [rbp+820h+var_830]
0x180009043  call    FormatRRASErrorString
0x180009048  test    cs:byte_1800C8404, 8
0x18000904f  jz      loc_180009222
0x180009055  lea     rcx, [rbp+820h+var_830]
0x180009059  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000905d  inc     rax
0x180009060  cmp     [rcx+rax*2], r15w
0x180009065  jnz     short loc_18000905D
0x180009067  jmp     loc_1800091EA
0x18000906c  lea     r8, [rbp+820h+SubKey]
0x180009070  mov     rcx, r14
0x180009073  call    MprConvertGuidToString
0x180009078  mov     rcx, [rsp+920h+hKey]; hKey
0x18000907d  lea     rax, [rsp+920h+var_8A8]
0x180009082  mov     r9d, 0F003Fh; samDesired
0x180009088  mov     [rsp+920h+phkResult], rax; phkResult
0x18000908d  xor     r8d, r8d; ulOptions
0x180009090  lea     rdx, [rbp+820h+SubKey]; lpSubKey
0x180009094  call    cs:__imp_RegOpenKeyExW
0x18000909a  mov     ebx, eax
0x18000909c  test    eax, eax
0x18000909e  jz      short loc_1800090ED
0x1800090a0  test    cs:byte_1800C8404, 8
0x1800090a7  jz      loc_180009222
0x1800090ad  mov     r9d, eax
0x1800090b0  mov     word ptr [rbp+820h+var_830], r15w
0x1800090b5  lea     r8, [rbp+820h+SubKey]
0x1800090b9  lea     rdx, aOpenrdinterfac_2; "OpenRDInterfacesKey: Failed to open RDI"...
0x1800090c0  lea     rcx, [rbp+820h+var_830]
0x1800090c4  call    FormatRRASErrorString
0x1800090c9  test    cs:byte_1800C8404, 8
0x1800090d0  jz      loc_180009222
0x1800090d6  lea     rcx, [rbp+820h+var_830]
0x1800090da  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800090de  inc     rax
0x1800090e1  cmp     [rcx+rax*2], r15w
0x1800090e6  jnz     short loc_1800090DE
0x1800090e8  jmp     loc_1800091EA
0x1800090ed  mov     rcx, [rsp+920h+var_8A8]; hKey
0x1800090f2  lea     rdx, aInterfaces; "Interfaces"
0x1800090f9  mov     r9d, 0F003Fh; samDesired
0x1800090ff  mov     [rsp+920h+phkResult], rdi; phkResult
0x180009104  xor     r8d, r8d; ulOptions
0x180009107  call    cs:__imp_RegOpenKeyExW
0x18000910d  mov     ebx, eax
0x18000910f  test    eax, eax
0x180009111  jz      short loc_18000915C
0x180009113  test    cs:byte_1800C8404, 8
0x18000911a  jz      loc_180009222
0x180009120  mov     r8d, eax
0x180009123  mov     word ptr [rbp+820h+var_830], r15w
0x180009128  lea     rdx, aOpenrdinterfac_1; "OpenRDInterfacesKey: Failed to open <RD"...
0x18000912f  lea     rcx, [rbp+820h+var_830]
0x180009133  call    FormatRRASErrorString
0x180009138  test    cs:byte_1800C8404, 8
0x18000913f  jz      loc_180009222
0x180009145  lea     rcx, [rbp+820h+var_830]
0x180009149  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000914d  inc     rax
0x180009150  cmp     [rcx+rax*2], r15w
0x180009155  jnz     short loc_18000914D
0x180009157  jmp     loc_1800091EA
0x18000915c  mov     rcx, [rdi]; hKey
0x18000915f  lea     rax, [rsp+920h+cbMaxValueLen]
0x180009164  mov     [rsp+920h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180009169  xor     r9d, r9d; lpReserved
0x18000916c  mov     [rsp+920h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180009171  xor     r8d, r8d; lpcchClass
0x180009174  mov     [rsp+920h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180009179  xor     edx, edx; lpClass
0x18000917b  lea     rax, [rsp+920h+cbMaxValueNameLen]
0x180009180  mov     [rsp+920h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180009185  lea     rax, [rsp+920h+cValues]
0x18000918a  mov     [rsp+920h+lpcValues], rax; lpcValues
0x18000918f  mov     [rsp+920h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x180009194  mov     [rsp+920h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x180009199  mov     [rsp+920h+phkResult], rsi; lpcSubKeys
0x18000919e  call    cs:__imp_RegQueryInfoKeyW
0x1800091a4  inc     [rsp+920h+cbMaxValueNameLen]
0x1800091a8  mov     ebx, eax
0x1800091aa  test    eax, eax
0x1800091ac  jz      short loc_180009222
0x1800091ae  test    cs:byte_1800C8404, 8
0x1800091b5  jz      short loc_180009222
0x1800091b7  mov     r8d, eax
0x1800091ba  mov     word ptr [rbp+820h+var_830], r15w
0x1800091bf  lea     rdx, aOpenrdinterfac_0; "OpenRDInterfacesKey: GetKeyMax failed w"...
0x1800091c6  lea     rcx, [rbp+820h+var_830]
0x1800091ca  call    FormatRRASErrorString
0x1800091cf  test    cs:byte_1800C8404, 8
0x1800091d6  jz      short loc_180009222
0x1800091d8  lea     rcx, [rbp+820h+var_830]
0x1800091dc  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800091e0  inc     rax
0x1800091e3  cmp     [rcx+rax*2], r15w
0x1800091e8  jnz     short loc_1800091E0
0x1800091ea  lea     eax, ds:2[rax*2]
0x1800091f1  mov     [rbp+820h+var_884], r15d
0x1800091f5  lea     rcx, [rbp+820h+var_830]
0x1800091f9  mov     [rbp+820h+var_888], eax
0x1800091fc  lea     rax, [rbp+820h+var_8A0]
0x180009200  mov     [rbp+820h+var_890], rcx
0x180009204  mov     r9d, 2
0x18000920a  mov     [rsp+920h+phkResult], rax
0x18000920f  lea     rdx, RasDdmTraceError
0x180009216  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18000921d  call    McGenEventWrite_EventWriteTransfer
0x180009222  mov     rcx, [rsp+920h+hKey]; hKey
0x180009227  test    rcx, rcx
0x18000922a  jz      short loc_180009232
0x18000922c  call    cs:__imp_RegCloseKey
0x180009232  mov     rcx, [rsp+920h+var_8A8]; hKey
0x180009237  test    rcx, rcx
0x18000923a  jz      short loc_180009242
0x18000923c  call    cs:__imp_RegCloseKey
0x180009242  mov     eax, ebx
0x180009244  mov     rcx, [rbp+820h+var_30]
0x18000924b  xor     rcx, rsp; StackCookie
0x18000924e  call    __security_check_cookie
0x180009253  mov     rbx, [rsp+920h+arg_18]
0x18000925b  add     rsp, 900h
0x180009262  pop     r15
0x180009264  pop     r14
0x180009266  pop     rdi
0x180009267  pop     rsi
0x180009268  pop     rbp
0x180009269  retn
```
