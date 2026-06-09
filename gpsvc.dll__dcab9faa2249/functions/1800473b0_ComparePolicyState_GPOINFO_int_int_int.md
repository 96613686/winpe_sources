# ComparePolicyState(_GPOINFO *,int *,int *,int *)

- ea: `0x1800473b0`
- end: `0x1800479fe`
- name: `?ComparePolicyState@@YAKPEAU_GPOINFO@@PEAH11@Z`
- size: `1614`
- prototype: `__int64 __fastcall(struct _GPOINFO *, int *, int *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005ce5c`

## callees

- `0x180003770`
- `0x1800473b0`
- `0x180047a10`
- `0x180048010`
- `0x180075ec0`
- `0x18007d320`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180047571`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800475d1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180047571`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800475d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180047698`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004773d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004774f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180047698`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004773d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004774f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047410`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047410`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800474f7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800474f7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004767a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004767a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047984`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180047984`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800474cd`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800474cd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180047718`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800478ee`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004793d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180047718`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800478ee`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18004793d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180047474`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180047474`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047546`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800475b0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047619`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047878`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047546`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800475b0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047619`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180047878`

## string_xrefs

- `0x18004760d`: `SlowLink`
- `0x1800477b9`: `GPLink-List`
- `0x180047822`: `Loopback-GPLink-List`
- `0x1800477fe`: `ComparePolicyState: Links have changed`
- `0x18004796e`: `ComparePolicyState: Links have changed`
- `0x1800479b2`: `ComparePolicyState: Failed Registry operation with %d`
- `0x1800479e7`: `ComparePolicyState: Failed Registry operation with %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ComparePolicyState(struct _GPOINFO *a1, int *a2, int *a3, int *a4)
{
  unsigned int v8; // r12d
  int v9; // edi
  int v10; // r12d
  DWORD LastError; // ebx
  const wchar_t *v12; // r9
  int v13; // eax
  LSTATUS v14; // eax
  unsigned int v15; // edi
  DWORD v16; // ecx
  BYTE *v17; // rsi
  const WCHAR *v18; // r13
  const WCHAR *v19; // rdx
  int v20; // r12d
  unsigned int v21; // eax
  unsigned int v23; // ebx
  DWORD cbData; // [rsp+60h] [rbp-A0h] BYREF
  DWORD Type; // [rsp+64h] [rbp-9Ch] BYREF
  BYTE v26[4]; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  BYTE Data[4]; // [rsp+78h] [rbp-88h] BYREF
  DWORD cbMaxValueLen; // [rsp+7Ch] [rbp-84h] BYREF
  BYTE v30[4]; // [rsp+80h] [rbp-80h] BYREF
  DWORD v31; // [rsp+84h] [rbp-7Ch]
  int *v32; // [rsp+88h] [rbp-78h]
  WCHAR SubKey[264]; // [rsp+90h] [rbp-70h] BYREF

  v32 = a2;
  v8 = *(_DWORD *)a1;
  *(_DWORD *)v30 = *(_DWORD *)a1 & 1;
  v9 = *(_DWORD *)v30;
  hKey = 0;
  *(_DWORD *)Data = 0;
  v10 = (v8 >> 18) & 1;
  *(_DWORD *)v26 = 0;
  LastError = GetLastError();
  v31 = LastError;
  *a3 = 0;
  *a2 = 0;
  *a4 = 0;
  v12 = L"Machine";
  if ( !v9 )
    v12 = (const wchar_t *)*((_QWORD *)a1 + 9);
  v13 = StringCchPrintfW(SubKey, 0x105u, L"Software\\Microsoft\\Windows\\CurrentVersion\\Group Policy\\State\\%ws", v12);
  if ( v13 < 0 )
  {
    v23 = (unsigned __int16)v13;
    SetLastError((unsigned __int16)v13);
    return v23;
  }
  v14 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0xF003Fu, &hKey);
  v15 = v14;
  if ( v14 )
  {
    *a3 = 1;
    *a4 = 1;
    if ( v14 == 2 )
    {
      SetLastError(LastError);
      return 0;
    }
    goto LABEL_22;
  }
  cbMaxValueLen = 0;
  Type = 0;
  cbData = 0;
  v15 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, 0, 0, &cbMaxValueLen, 0, 0);
  if ( v15 )
    goto LABEL_27;
  v16 = cbMaxValueLen + 2;
  if ( cbMaxValueLen + 2 < cbMaxValueLen )
  {
    cbMaxValueLen = -1;
    v15 = 534;
    goto LABEL_27;
  }
  cbMaxValueLen += 2;
  v17 = (BYTE *)LocalAlloc(0x40u, v16);
  if ( !v17 )
  {
LABEL_27:
    *a3 = 1;
    goto LABEL_22;
  }
  if ( (*(_DWORD *)a1 & 0x10000) == 0 )
  {
    Type = 0;
    *(_DWORD *)Data = 0;
    cbData = 4;
    v15 = RegQueryValueExW(hKey, L"ForceForegroundLogging", 0, &Type, Data, &cbData);
    if ( v15 || *(_DWORD *)Data )
    {
      *a3 = 1;
      goto LABEL_21;
    }
  }
  cbData = cbMaxValueLen;
  Type = 0;
  v15 = RegQueryValueExW(hKey, L"Site-Name", 0, &Type, v17, &cbData);
  if ( !v15 )
  {
    v18 = &DomainName;
    v19 = &DomainName;
    if ( *((_QWORD *)a1 + 28) )
      v19 = (const WCHAR *)*((_QWORD *)a1 + 28);
    if ( (unsigned int)_o__wcsicmp(v17, v19) )
    {
      *a3 = 1;
      goto LABEL_21;
    }
    cbData = cbMaxValueLen;
    Type = 0;
    v15 = RegQueryValueExW(hKey, L"Distinguished-Name", 0, &Type, v17, &cbData);
    if ( !v15 )
    {
      if ( *((_QWORD *)a1 + 3) )
        v18 = (const WCHAR *)*((_QWORD *)a1 + 3);
      if ( (unsigned int)_o__wcsicmp(v17, v18) )
      {
        *a3 = 1;
        if ( (*(_DWORD *)a1 & 0x10000) != 0 )
        {
          *(_DWORD *)v26 = 1;
          v15 = RegSetValueExW(hKey, L"ForceForegroundLogging", 0, 4u, v26, 4u);
        }
        goto LABEL_21;
      }
      Type = 0;
      *(_DWORD *)Data = 0;
      cbData = 4;
      if ( RegQueryValueExW(hKey, L"SlowLink", 0, &Type, Data, &cbData) || *(_DWORD *)Data != v10 )
        *v32 = 1;
      v20 = *(_DWORD *)v30;
      v21 = RegCompareGPOs(hKey, *((struct _GPCONTAINER **)a1 + 20), *(int *)v30, L"GPO-List", a3, (int *)v26);
      v15 = v21;
      if ( (*(_DWORD *)a1 & 0x10000) != 0 && *(_DWORD *)v26 )
      {
        *(_DWORD *)v30 = 1;
        v15 = RegSetValueExW(hKey, L"ForceForegroundLogging", 0, 4u, v30, 4u);
        if ( v15 )
          goto LABEL_21;
      }
      else if ( v21 )
      {
        goto LABEL_21;
      }
      if ( !*a3 )
      {
        if ( !v20
          && (v15 = RegCompareGPOs(hKey, *((struct _GPCONTAINER **)a1 + 22), 0, L"Loopback-GPO-List", a3, (int *)v26),
              (*(_DWORD *)a1 & 0x10000) != 0)
          && *(_DWORD *)v26 )
        {
          *(_DWORD *)v26 = 1;
          v15 = RegSetValueExW(hKey, L"ForceForegroundLogging", 0, 4u, v26, 4u);
          if ( v15 )
            goto LABEL_21;
        }
        else if ( v15 )
        {
          goto LABEL_21;
        }
        if ( !*a3 )
        {
          v15 = RegCompareGPLs(hKey, *((struct _SCOPEOFMGMT **)a1 + 19), L"GPLink-List", a3);
          if ( !v15 )
          {
            if ( *a3 )
            {
LABEL_40:
              if ( *(_DWORD *)&g_dwDebugLevel )
              {
                if ( g_lpDebugMsg )
                {
                  g_lpDebugMsg(4u, L"ComparePolicyState: Links have changed");
                }
                else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
                {
                  RedirectDebugMsg(4u, L"ComparePolicyState: Links have changed");
                }
              }
              goto LABEL_21;
            }
            if ( !v20 )
              v15 = RegCompareGPLs(hKey, *((struct _SCOPEOFMGMT **)a1 + 21), L"Loopback-GPLink-List", a3);
          }
          if ( *a3 )
            goto LABEL_40;
        }
      }
    }
  }
LABEL_21:
  LocalFree(v17);
LABEL_22:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v15 )
  {
    *a3 = 1;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"ComparePolicyState: Failed Registry operation with %d", v15);
      }
      else if ( g_lpDebugMsgContextInstance )
      {
        if ( g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"ComparePolicyState: Failed Registry operation with %d", v15);
      }
    }
  }
  SetLastError(LastError);
  return v15;
}

```

## disassembly

```asm
0x1800473b0  push    rbp
0x1800473b2  push    rbx
0x1800473b3  push    rsi
0x1800473b4  push    rdi
0x1800473b5  push    r12
0x1800473b7  push    r13
0x1800473b9  push    r14
0x1800473bb  push    r15
0x1800473bd  lea     rbp, [rsp-1B8h]
0x1800473c5  sub     rsp, 2B8h
0x1800473cc  mov     rax, cs:__security_cookie
0x1800473d3  xor     rax, rsp
0x1800473d6  mov     [rbp+1F0h+var_50], rax
0x1800473dd  mov     rsi, r9
0x1800473e0  mov     r14, r8
0x1800473e3  mov     r13, rdx
0x1800473e6  mov     [rbp+1F0h+var_268], rdx
0x1800473ea  mov     r15, rcx
0x1800473ed  mov     r12d, [rcx]
0x1800473f0  mov     edi, r12d
0x1800473f3  and     edi, 1
0x1800473f6  mov     dword ptr [rbp+1F0h+var_270], edi
0x1800473f9  xor     eax, eax
0x1800473fb  mov     [rsp+2F0h+hKey], rax
0x180047400  mov     dword ptr [rsp+2F0h+Data], eax
0x180047404  shr     r12d, 12h
0x180047408  and     r12d, 1
0x18004740c  mov     dword ptr [rsp+2F0h+var_288], eax
0x180047410  call    cs:__imp_GetLastError
0x180047416  mov     ebx, eax
0x180047418  mov     [rbp+1F0h+var_26C], eax
0x18004741b  xor     eax, eax
0x18004741d  mov     [r14], eax
0x180047420  mov     [r13+0], eax
0x180047424  xor     r13d, r13d
0x180047427  mov     [rsi], r13d
0x18004742a  test    edi, edi
0x18004742c  lea     r9, aMachine; "Machine"
0x180047433  jnz     short loc_180047439
0x180047435  mov     r9, [r15+48h]
0x180047439  lea     r8, aSoftwareMicros_13; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180047440  mov     edx, 105h; unsigned __int64
0x180047445  lea     rcx, [rbp+1F0h+SubKey]; unsigned __int16 *
0x180047449  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004744e  test    eax, eax
0x180047450  js      loc_18004774A
0x180047456  lea     rax, [rsp+2F0h+hKey]
0x18004745b  mov     [rsp+2F0h+phkResult], rax; phkResult
0x180047460  mov     r9d, 0F003Fh; samDesired
0x180047466  xor     r8d, r8d; ulOptions
0x180047469  lea     rdx, [rbp+1F0h+SubKey]; lpSubKey
0x18004746d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180047474  call    cs:__imp_RegOpenKeyExW
0x18004747a  mov     edi, eax
0x18004747c  test    eax, eax
0x18004747e  jnz     loc_180047725
0x180047484  mov     [rsp+2F0h+cbMaxValueLen], r13d
0x180047489  mov     [rsp+2F0h+Type], r13d
0x18004748e  mov     [rsp+2F0h+cbData], r13d
0x180047493  mov     [rsp+2F0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x180047498  mov     [rsp+2F0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18004749d  lea     rax, [rsp+2F0h+cbMaxValueLen]
0x1800474a2  mov     [rsp+2F0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1800474a7  mov     [rsp+2F0h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x1800474ac  mov     [rsp+2F0h+lpcValues], r13; lpcValues
0x1800474b1  mov     [rsp+2F0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x1800474b6  mov     [rsp+2F0h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x1800474bb  mov     [rsp+2F0h+phkResult], r13; lpcSubKeys
0x1800474c0  xor     r9d, r9d; lpReserved
0x1800474c3  xor     r8d, r8d; lpcchClass
0x1800474c6  xor     edx, edx; lpClass
0x1800474c8  mov     rcx, [rsp+2F0h+hKey]; hKey
0x1800474cd  call    cs:__imp_RegQueryInfoKeyW
0x1800474d3  mov     edi, eax
0x1800474d5  test    eax, eax
0x1800474d7  jnz     loc_1800476D0
0x1800474dd  mov     eax, [rsp+2F0h+cbMaxValueLen]
0x1800474e1  lea     ecx, [rax+2]
0x1800474e4  cmp     ecx, eax
0x1800474e6  jb      loc_1800476C3
0x1800474ec  mov     [rsp+2F0h+cbMaxValueLen], ecx
0x1800474f0  mov     edx, ecx; uBytes
0x1800474f2  mov     ecx, 40h ; '@'; uFlags
0x1800474f7  call    cs:__imp_LocalAlloc
0x1800474fd  mov     rsi, rax
0x180047500  test    rax, rax
0x180047503  jz      loc_1800476D0
0x180047509  test    dword ptr [r15], 10000h
0x180047510  jz      loc_18004783E
0x180047516  mov     eax, [rsp+2F0h+cbMaxValueLen]
0x18004751a  mov     [rsp+2F0h+cbData], eax
0x18004751e  mov     [rsp+2F0h+Type], r13d
0x180047523  lea     rax, [rsp+2F0h+cbData]
0x180047528  mov     [rsp+2F0h+lpcbMaxSubKeyLen], rax; lpcbData
0x18004752d  mov     [rsp+2F0h+phkResult], rsi; lpData
0x180047532  lea     r9, [rsp+2F0h+Type]; lpType
0x180047537  xor     r8d, r8d; lpReserved
0x18004753a  lea     rdx, aSiteName; "Site-Name"
0x180047541  mov     rcx, [rsp+2F0h+hKey]; hKey
0x180047546  call    cs:__imp_RegQueryValueExW
0x18004754c  mov     edi, eax
0x18004754e  test    eax, eax
0x180047550  jnz     loc_180047677
0x180047556  mov     rax, [r15+0E0h]
0x18004755d  lea     r13, DomainName
0x180047564  mov     rdx, r13
0x180047567  test    rax, rax
0x18004756a  cmovnz  rdx, rax
0x18004756e  mov     rcx, rsi
0x180047571  call    cs:__imp__o__wcsicmp
0x180047577  test    eax, eax
0x180047579  jnz     loc_18004789B
0x18004757f  mov     eax, [rsp+2F0h+cbMaxValueLen]
0x180047583  mov     [rsp+2F0h+cbData], eax
0x180047587  xor     eax, eax
0x180047589  mov     [rsp+2F0h+Type], eax
0x18004758d  lea     rax, [rsp+2F0h+cbData]
0x180047592  mov     [rsp+2F0h+lpcbMaxSubKeyLen], rax; lpcbData
0x180047597  mov     [rsp+2F0h+phkResult], rsi; lpData
0x18004759c  lea     r9, [rsp+2F0h+Type]; lpType
0x1800475a1  xor     r8d, r8d; lpReserved
0x1800475a4  lea     rdx, aDistinguishedN; "Distinguished-Name"
0x1800475ab  mov     rcx, [rsp+2F0h+hKey]; hKey
0x1800475b0  call    cs:__imp_RegQueryValueExW
0x1800475b6  mov     edi, eax
0x1800475b8  test    eax, eax
0x1800475ba  jnz     loc_180047677
0x1800475c0  mov     rax, [r15+18h]
0x1800475c4  test    rax, rax
0x1800475c7  cmovnz  r13, rax
0x1800475cb  mov     rdx, r13
0x1800475ce  mov     rcx, rsi
0x1800475d1  call    cs:__imp__o__wcsicmp
0x1800475d7  test    eax, eax
0x1800475d9  jnz     loc_1800476D9
0x1800475df  xor     eax, eax
0x1800475e1  mov     [rsp+2F0h+Type], eax
0x1800475e5  mov     dword ptr [rsp+2F0h+Data], eax
0x1800475e9  mov     [rsp+2F0h+cbData], 4
0x1800475f1  lea     rax, [rsp+2F0h+cbData]
0x1800475f6  mov     [rsp+2F0h+lpcbMaxSubKeyLen], rax; lpcbData
0x1800475fb  lea     rax, [rsp+2F0h+Data]
0x180047600  mov     [rsp+2F0h+phkResult], rax; lpData
0x180047605  lea     r9, [rsp+2F0h+Type]; lpType
0x18004760a  xor     r8d, r8d; lpReserved
0x18004760d  lea     rdx, aSlowlink_0; "SlowLink"
0x180047614  mov     rcx, [rsp+2F0h+hKey]; hKey
0x180047619  call    cs:__imp_RegQueryValueExW
0x18004761f  test    eax, eax
0x180047621  jnz     loc_1800478A7
0x180047627  cmp     dword ptr [rsp+2F0h+Data], r12d
0x18004762c  jnz     loc_1800478A7
0x180047632  lea     rax, [rsp+2F0h+var_288]
0x180047637  mov     [rsp+2F0h+lpcbMaxSubKeyLen], rax; int *
0x18004763c  mov     [rsp+2F0h+phkResult], r14; int *
0x180047641  lea     r9, aGpoList; "GPO-List"
0x180047648  mov     r12d, dword ptr [rbp+1F0h+var_270]
0x18004764c  mov     r8d, r12d; int
0x18004764f  mov     rdx, [r15+0A0h]; struct _GPCONTAINER *
0x180047656  mov     rcx, [rsp+2F0h+hKey]; HKEY
0x18004765b  call    ?RegCompareGPOs@@YAKPEAUHKEY__@@PEAU_GPCONTAINER@@HPEBGPEAH3@Z; RegCompareGPOs(HKEY__ *,_GPCONTAINER *,int,ushort const *,int *,int *)
0x180047660  mov     edi, eax
0x180047662  test    dword ptr [r15], 10000h
0x180047669  jnz     loc_1800478B6
0x18004766f  test    eax, eax
0x180047671  jz      loc_18004775C
0x180047677  mov     rcx, rsi; hMem
0x18004767a  call    cs:__imp_LocalFree
0x180047680  mov     rcx, [rsp+2F0h+hKey]; hKey
0x180047685  test    rcx, rcx
0x180047688  jnz     loc_180047984
0x18004768e  test    edi, edi
0x180047690  jnz     loc_18004798F
0x180047696  mov     ecx, ebx; dwErrCode
0x180047698  call    cs:__imp_SetLastError
0x18004769e  mov     eax, edi
0x1800476a0  mov     rcx, [rbp+1F0h+var_50]
0x1800476a7  xor     rcx, rsp; StackCookie
0x1800476aa  call    __security_check_cookie
0x1800476af  add     rsp, 2B8h
0x1800476b6  pop     r15
0x1800476b8  pop     r14
0x1800476ba  pop     r13
0x1800476bc  pop     r12
0x1800476be  pop     rdi
0x1800476bf  pop     rsi
0x1800476c0  pop     rbx
0x1800476c1  pop     rbp
0x1800476c2  retn
0x1800476c3  mov     [rsp+2F0h+cbMaxValueLen], 0FFFFFFFFh
0x1800476cb  mov     edi, 216h
0x1800476d0  mov     dword ptr [r14], 1
0x1800476d7  jmp     short loc_180047680
0x1800476d9  mov     dword ptr [r14], 1
0x1800476e0  test    dword ptr [r15], 10000h
0x1800476e7  jz      short loc_180047677
0x1800476e9  mov     dword ptr [rsp+2F0h+var_288], 1
0x1800476f1  mov     dword ptr [rsp+2F0h+lpcbMaxSubKeyLen], 4; cbData
0x1800476f9  lea     rax, [rsp+2F0h+var_288]
0x1800476fe  mov     [rsp+2F0h+phkResult], rax; lpData
0x180047703  mov     r9d, 4; dwType
0x180047709  xor     r8d, r8d; Reserved
0x18004770c  lea     rdx, aForceforegroun; "ForceForegroundLogging"
0x180047713  mov     rcx, [rsp+2F0h+hKey]; hKey
0x180047718  call    cs:__imp_RegSetValueExW
0x18004771e  mov     edi, eax
0x180047720  jmp     loc_180047677
0x180047725  mov     dword ptr [r14], 1
0x18004772c  mov     dword ptr [rsi], 1
0x180047732  cmp     eax, 2
0x180047735  jnz     loc_180047680
0x18004773b  mov     ecx, ebx; dwErrCode
0x18004773d  call    cs:__imp_SetLastError
0x180047743  xor     eax, eax
0x180047745  jmp     loc_1800476A0
0x18004774a  movzx   ebx, ax
0x18004774d  mov     ecx, ebx; dwErrCode
0x18004774f  call    cs:__imp_SetLastError
0x180047755  mov     eax, ebx
0x180047757  jmp     loc_1800476A0
0x18004775c  cmp     dword ptr [r14], 0
0x180047760  jnz     loc_180047677
0x180047766  test    r12d, r12d
0x180047769  jnz     short loc_1800477A4
0x18004776b  lea     rax, [rsp+2F0h+var_288]
0x180047770  mov     [rsp+2F0h+lpcbMaxSubKeyLen], rax; int *
0x180047775  mov     [rsp+2F0h+phkResult], r14; int *
0x18004777a  lea     r9, aLoopbackGpoLis; "Loopback-GPO-List"
0x180047781  xor     r8d, r8d; int
0x180047784  mov     rdx, [r15+0B0h]; struct _GPCONTAINER *
0x18004778b  mov     rcx, [rsp+2F0h+hKey]; HKEY
0x180047790  call    ?RegCompareGPOs@@YAKPEAUHKEY__@@PEAU_GPCONTAINER@@HPEBGPEAH3@Z; RegCompareGPOs(HKEY__ *,_GPCONTAINER *,int,ushort const *,int *,int *)
0x180047795  mov     edi, eax
0x180047797  test    dword ptr [r15], 10000h
0x18004779e  jnz     loc_180047903
0x1800477a4  test    edi, edi
0x1800477a6  jnz     loc_180047677
0x1800477ac  cmp     dword ptr [r14], 0
0x1800477b0  jnz     loc_180047677
0x1800477b6  mov     r9, r14; int *
0x1800477b9  lea     r8, aGplinkList; "GPLink-List"
0x1800477c0  mov     rdx, [r15+98h]; struct _SCOPEOFMGMT *
0x1800477c7  mov     rcx, [rsp+2F0h+hKey]; HKEY
0x1800477cc  call    ?RegCompareGPLs@@YAKPEAUHKEY__@@PEAU_SCOPEOFMGMT@@PEBGPEAH@Z; RegCompareGPLs(HKEY__ *,_SCOPEOFMGMT *,ushort const *,int *)
0x1800477d1  mov     edi, eax
0x1800477d3  test    eax, eax
0x1800477d5  jz      short loc_180047814
0x1800477d7  cmp     dword ptr [r14], 0
0x1800477db  jz      loc_180047677
0x1800477e1  cmp     cs:?g_dwDebugLevel@@3KA, 0; ulong g_dwDebugLevel
0x1800477e8  jz      loc_180047677
0x1800477ee  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800477f5  test    rax, rax
0x1800477f8  jz      loc_180047952
0x1800477fe  lea     rdx, aComparepolicys; "ComparePolicyState: Links have changed"
0x180047805  mov     ecx, 4
0x18004780a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004780f  jmp     loc_180047677
0x180047814  cmp     dword ptr [r14], 0
0x180047818  jnz     short loc_1800477E1
0x18004781a  test    r12d, r12d
0x18004781d  jnz     short loc_1800477D7
0x18004781f  mov     r9, r14; int *
0x180047822  lea     r8, aLoopbackGplink; "Loopback-GPLink-List"
0x180047829  mov     rdx, [r15+0A8h]; struct _SCOPEOFMGMT *
0x180047830  mov     rcx, [rsp+2F0h+hKey]; HKEY
0x180047835  call    ?RegCompareGPLs@@YAKPEAUHKEY__@@PEAU_SCOPEOFMGMT@@PEBGPEAH@Z; RegCompareGPLs(HKEY__ *,_SCOPEOFMGMT *,ushort const *,int *)
0x18004783a  mov     edi, eax
0x18004783c  jmp     short loc_1800477D7
0x18004783e  mov     [rsp+2F0h+Type], r13d
0x180047843  mov     dword ptr [rsp+2F0h+Data], r13d
0x180047848  mov     [rsp+2F0h+cbData], 4
0x180047850  lea     rax, [rsp+2F0h+cbData]
0x180047855  mov     [rsp+2F0h+lpcbMaxSubKeyLen], rax; lpcbData
0x18004785a  lea     rax, [rsp+2F0h+Data]
0x18004785f  mov     [rsp+2F0h+phkResult], rax; lpData
0x180047864  lea     r9, [rsp+2F0h+Type]; lpType
0x180047869  xor     r8d, r8d; lpReserved
0x18004786c  lea     rdx, aForceforegroun; "ForceForegroundLogging"
0x180047873  mov     rcx, [rsp+2F0h+hKey]; hKey
0x180047878  call    cs:__imp_RegQueryValueExW
0x18004787e  mov     edi, eax
0x180047880  test    eax, eax
0x180047882  jnz     short loc_18004788F
0x180047884  cmp     dword ptr [rsp+2F0h+Data], r13d
0x180047889  jz      loc_180047516
0x18004788f  mov     dword ptr [r14], 1
0x180047896  jmp     loc_180047677
0x18004789b  mov     dword ptr [r14], 1
0x1800478a2  jmp     loc_180047677
0x1800478a7  mov     rax, [rbp+1F0h+var_268]
0x1800478ab  mov     dword ptr [rax], 1
0x1800478b1  jmp     loc_180047632
0x1800478b6  cmp     dword ptr [rsp+2F0h+var_288], 0
0x1800478bb  jz      loc_18004766F
0x1800478c1  mov     dword ptr [rbp+1F0h+var_270], 1
0x1800478c8  mov     dword ptr [rsp+2F0h+lpcbMaxSubKeyLen], 4; cbData
0x1800478d0  lea     rax, [rbp+1F0h+var_270]
0x1800478d4  mov     [rsp+2F0h+phkResult], rax; lpData
0x1800478d9  mov     r9d, 4; dwType
  ... truncated ...
```
