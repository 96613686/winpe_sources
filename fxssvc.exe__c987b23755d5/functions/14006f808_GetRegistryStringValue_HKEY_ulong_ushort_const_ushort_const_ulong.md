# GetRegistryStringValue(HKEY__ *,ulong,ushort const *,ushort const *,ulong *)

- ea: `0x14006f808`
- end: `0x14006fa7f`
- name: `?GetRegistryStringValue@@YAPEAGPEAUHKEY__@@KPEBG1PEAK@Z`
- size: `631`
- prototype: `unsigned __int16 *__fastcall(HKEY hKey, DWORD dwType, LPCWSTR lpValueName, const unsigned __int16 *, DWORD cbData)`
- caller_count: `12`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x14000d680`
- `0x140050adc`
- `0x140074688`
- `0x14007a880`
- `0x14007aab0`
- `0x14007ad30`
- `0x14007aec0`
- `0x14007b000`
- `0x14007c450`
- `0x14007d030`
- `0x14007d36c`
- `0x14007d650`

## callees

- `0x14001598c`
- `0x140065d14`
- `0x140065dbc`
- `0x14006f808`
- `0x140071ec8`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x14006f96c`
- `ADVAPI32!RegSetValueExW` at `0x14006f96c`
- `ADVAPI32!RegQueryValueExW` at `0x14006f84f`
- `ADVAPI32!RegQueryValueExW` at `0x14006f8fa`
- `ADVAPI32!RegQueryValueExW` at `0x14006f84f`
- `ADVAPI32!RegQueryValueExW` at `0x14006f8fa`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x14006f9a9`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x14006f9d6`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x14006f9a9`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x14006f9d6`
- `KERNEL32!GetLastError` at `0x14006f9fd`
- `KERNEL32!GetLastError` at `0x14006f9fd`

## string_xrefs

- `0x14006f947`: `StringCbCopy failed, hr: 0x%x`
- `0x14006f98d`: `Can't create DefaultValue since it's NULL`
- `0x14006f979`: `RegSetValueEx() failed[%s], ec=%d`
- `0x14006fa58`: `StringCbCopy failed, hr = 0x%x`

## pseudocode

```c
BYTE *__fastcall GetRegistryStringValue(
        HKEY hKey,
        DWORD dwType,
        LPCWSTR lpValueName,
        const unsigned __int16 *a4,
        DWORD cbData)
{
  unsigned int v8; // eax
  __int64 v9; // r15
  BYTE *lpData; // rbx
  __int64 v11; // rcx
  DWORD v12; // ecx
  DWORD v13; // esi
  SIZE_T v14; // r13
  int v15; // eax
  unsigned int v16; // eax
  DWORD v17; // eax
  signed int v18; // r14d
  WCHAR *v19; // rax
  WCHAR *v20; // rsi
  signed int v21; // eax
  DWORD LastError; // eax
  unsigned __int16 *v24; // rax
  int v25; // eax
  DWORD Type; // [rsp+30h] [rbp-18h] BYREF
  DWORD v27; // [rsp+34h] [rbp-14h]

  cbData = 0;
  Type = 0;
  v8 = RegQueryValueExW(hKey, lpValueName, 0, &Type, 0, &cbData);
  v9 = -1;
  if ( v8 )
  {
    lpData = 0;
    if ( v8 != 2 )
      goto LABEL_8;
    if ( !a4 )
    {
      fax_dprintf(L"RegQueryValueEx() failed, ec=%d - and no default value was specified", 2);
      goto LABEL_32;
    }
    v11 = -1;
    do
      ++v11;
    while ( a4[v11] );
    v12 = 2 * v11 + 2;
    cbData = v12;
LABEL_11:
    if ( !v12 )
    {
      v12 = 32;
      cbData = 32;
    }
    v27 = v12 + (v12 & 1);
    v13 = v27 + 2;
    v14 = v27 + 2;
    lpData = (BYTE *)pMemAlloc(v14);
    if ( !lpData )
      goto LABEL_32;
    v8 = RegQueryValueExW(hKey, lpValueName, 0, &Type, lpData, &cbData);
    lpData[v13 - 1] = 0;
    lpData[v27] = 0;
    if ( (cbData & 1) != 0 )
      lpData[v13 - 3] = 0;
    if ( !v8 )
    {
LABEL_24:
      if ( dwType != 2 )
        return lpData;
      v17 = ExpandEnvironmentStringsW((LPCWSTR)lpData, 0, 0);
      v18 = v17;
      if ( v17 )
      {
        cbData = 2 * v17 + 2;
        v19 = (WCHAR *)pMemAlloc(cbData);
        v20 = v19;
        if ( v19 )
        {
          v21 = ExpandEnvironmentStringsW((LPCWSTR)lpData, v19, v18);
          if ( v21 && v21 <= v18 )
          {
            pMemFree(lpData);
            return (BYTE *)v20;
          }
          pMemFree(v20);
          LastError = GetLastError();
          fax_dprintf(L"ExpandEnvironmentStrings() failed, ec=%d", LastError);
        }
      }
LABEL_32:
      pMemFree(lpData);
      if ( !a4 )
        return 0;
      do
        ++v9;
      while ( a4[v9] );
      cbData = 2 * v9 + 2;
      v24 = (unsigned __int16 *)pMemAlloc(cbData);
      lpData = (BYTE *)v24;
      if ( !v24 )
        return 0;
      v25 = StringCbCopyW(v24, cbData, a4);
      if ( v25 < 0 )
      {
        fax_dprintf(L"StringCbCopy failed, hr = 0x%x", (unsigned int)v25);
        pMemFree(lpData);
        return 0;
      }
      return lpData;
    }
    if ( v8 == 2 )
    {
      if ( !a4 )
      {
        fax_dprintf(L"Can't create DefaultValue since it's NULL");
        goto LABEL_32;
      }
      v15 = StringCbCopyW((unsigned __int16 *)lpData, v14, a4);
      if ( v15 < 0 )
      {
        fax_dprintf(L"StringCbCopy failed, hr: 0x%x", (unsigned int)v15);
        goto LABEL_32;
      }
      v16 = RegSetValueExW(hKey, lpValueName, 0, dwType, lpData, cbData);
      if ( v16 )
      {
        fax_dprintf(L"RegSetValueEx() failed[%s], ec=%d", lpValueName, v16);
        goto LABEL_32;
      }
      goto LABEL_24;
    }
LABEL_8:
    fax_dprintf(L"RegQueryValueEx() failed, ec=%d", v8);
    goto LABEL_32;
  }
  if ( Type == dwType )
  {
    v12 = cbData;
    goto LABEL_11;
  }
  return 0;
}

```

## disassembly

```asm
0x14006f808  mov     [rsp-40h+hKey], rcx
0x14006f80d  push    rbp
0x14006f80e  push    rbx
0x14006f80f  push    rsi
0x14006f810  push    rdi
0x14006f811  push    r12
0x14006f813  push    r13
0x14006f815  push    r14
0x14006f817  push    r15
0x14006f819  mov     rbp, rsp
0x14006f81c  sub     rsp, 48h
0x14006f820  mov     rax, rcx
0x14006f823  mov     r12, r8
0x14006f826  xor     esi, esi
0x14006f828  lea     rcx, [rbp+cbData]
0x14006f82c  mov     [rsp+48h+lpcbData], rcx; lpcbData
0x14006f831  mov     rdi, r9
0x14006f834  mov     r14d, edx
0x14006f837  mov     [rbp+cbData], esi
0x14006f83a  mov     rcx, rax; hKey
0x14006f83d  mov     [rbp+Type], esi
0x14006f840  lea     r9, [rbp+Type]; lpType
0x14006f844  mov     [rsp+48h+lpData], rsi; lpData
0x14006f849  xor     r8d, r8d; lpReserved
0x14006f84c  mov     rdx, r12; lpValueName
0x14006f84f  call    cs:__imp_RegQueryValueExW
0x14006f855  or      r15, 0FFFFFFFFFFFFFFFFh
0x14006f859  test    eax, eax
0x14006f85b  jz      short loc_14006F8A2
0x14006f85d  mov     ebx, esi
0x14006f85f  cmp     eax, 2
0x14006f862  jnz     short loc_14006F897
0x14006f864  test    rdi, rdi
0x14006f867  jz      short loc_14006F881
0x14006f869  mov     rcx, r15
0x14006f86c  inc     rcx
0x14006f86f  cmp     [rdi+rcx*2], si
0x14006f873  jnz     short loc_14006F86C
0x14006f875  lea     ecx, ds:2[rcx*2]
0x14006f87c  mov     [rbp+cbData], ecx
0x14006f87f  jmp     short loc_14006F8AF
0x14006f881  mov     edx, 2
0x14006f886  lea     rcx, aRegqueryvaluee; "RegQueryValueEx() failed, ec=%d - and n"...
0x14006f88d  call    fax_dprintf
0x14006f892  jmp     loc_14006FA13
0x14006f897  mov     edx, eax
0x14006f899  lea     rcx, aRegqueryvaluee_1; "RegQueryValueEx() failed, ec=%d"
0x14006f8a0  jmp     short loc_14006F88D
0x14006f8a2  cmp     [rbp+Type], r14d
0x14006f8a6  jnz     loc_14006FA6C
0x14006f8ac  mov     ecx, [rbp+cbData]
0x14006f8af  test    ecx, ecx
0x14006f8b1  jnz     short loc_14006F8BB
0x14006f8b3  mov     ecx, 20h ; ' '
0x14006f8b8  mov     [rbp+cbData], ecx
0x14006f8bb  mov     eax, ecx
0x14006f8bd  and     eax, 1
0x14006f8c0  add     eax, ecx
0x14006f8c2  mov     [rbp+var_14], eax
0x14006f8c5  lea     esi, [rax+2]
0x14006f8c8  mov     ecx, esi; dwBytes
0x14006f8ca  mov     r13d, esi
0x14006f8cd  call    pMemAlloc
0x14006f8d2  mov     rbx, rax
0x14006f8d5  test    rax, rax
0x14006f8d8  jz      loc_14006FA11
0x14006f8de  mov     rcx, [rbp+hKey]; hKey
0x14006f8e2  lea     rax, [rbp+cbData]
0x14006f8e6  mov     [rsp+48h+lpcbData], rax; lpcbData
0x14006f8eb  lea     r9, [rbp+Type]; lpType
0x14006f8ef  xor     r8d, r8d; lpReserved
0x14006f8f2  mov     [rsp+48h+lpData], rbx; lpData
0x14006f8f7  mov     rdx, r12; lpValueName
0x14006f8fa  call    cs:__imp_RegQueryValueExW
0x14006f900  lea     ecx, [rsi-1]
0x14006f903  mov     byte ptr [rcx+rbx], 0
0x14006f907  mov     ecx, [rbp+var_14]
0x14006f90a  mov     byte ptr [rcx+rbx], 0
0x14006f90e  test    byte ptr [rbp+cbData], 1
0x14006f912  jz      short loc_14006F91F
0x14006f914  lea     ecx, [rsi-3]
0x14006f917  xor     esi, esi
0x14006f919  mov     [rcx+rbx], sil
0x14006f91d  jmp     short loc_14006F921
0x14006f91f  xor     esi, esi
0x14006f921  test    eax, eax
0x14006f923  jz      short loc_14006F99B
0x14006f925  cmp     eax, 2
0x14006f928  jnz     loc_14006F897
0x14006f92e  test    rdi, rdi
0x14006f931  jz      short loc_14006F98D
0x14006f933  mov     r8, rdi; unsigned __int16 *
0x14006f936  mov     rdx, r13; unsigned __int64
0x14006f939  mov     rcx, rbx; unsigned __int16 *
0x14006f93c  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x14006f941  test    eax, eax
0x14006f943  jns     short loc_14006F953
0x14006f945  mov     edx, eax
0x14006f947  lea     rcx, aStringcbcopyFa_0; "StringCbCopy failed, hr: 0x%x"
0x14006f94e  jmp     loc_14006F88D
0x14006f953  mov     eax, [rbp+cbData]
0x14006f956  mov     r9d, r14d; dwType
0x14006f959  mov     rcx, [rbp+hKey]; hKey
0x14006f95d  xor     r8d, r8d; Reserved
0x14006f960  mov     dword ptr [rsp+48h+lpcbData], eax; cbData
0x14006f964  mov     rdx, r12; lpValueName
0x14006f967  mov     [rsp+48h+lpData], rbx; lpData
0x14006f96c  call    cs:__imp_RegSetValueExW
0x14006f972  test    eax, eax
0x14006f974  jz      short loc_14006F99B
0x14006f976  mov     r8d, eax
0x14006f979  lea     rcx, aRegsetvalueexF; "RegSetValueEx() failed[%s], ec=%d"
0x14006f980  mov     rdx, r12
0x14006f983  call    fax_dprintf
0x14006f988  jmp     loc_14006FA13
0x14006f98d  lea     rcx, aCanTCreateDefa; "Can't create DefaultValue since it's NU"...
0x14006f994  call    fax_dprintf
0x14006f999  jmp     short loc_14006FA13
0x14006f99b  cmp     r14d, 2
0x14006f99f  jnz     short loc_14006F9F0
0x14006f9a1  xor     r8d, r8d; nSize
0x14006f9a4  xor     edx, edx; lpDst
0x14006f9a6  mov     rcx, rbx; lpSrc
0x14006f9a9  call    cs:__imp_ExpandEnvironmentStringsW
0x14006f9af  mov     r14d, eax
0x14006f9b2  test    eax, eax
0x14006f9b4  jz      short loc_14006FA13
0x14006f9b6  lea     ecx, ds:2[rax*2]; dwBytes
0x14006f9bd  mov     [rbp+cbData], ecx
0x14006f9c0  call    pMemAlloc
0x14006f9c5  mov     rsi, rax
0x14006f9c8  test    rax, rax
0x14006f9cb  jz      short loc_14006FA11
0x14006f9cd  mov     r8d, r14d; nSize
0x14006f9d0  mov     rdx, rax; lpDst
0x14006f9d3  mov     rcx, rbx; lpSrc
0x14006f9d6  call    cs:__imp_ExpandEnvironmentStringsW
0x14006f9dc  test    eax, eax
0x14006f9de  jz      short loc_14006F9F5
0x14006f9e0  cmp     eax, r14d
0x14006f9e3  jg      short loc_14006F9F5
0x14006f9e5  mov     rcx, rbx; lpMem
0x14006f9e8  call    pMemFree
0x14006f9ed  mov     rbx, rsi
0x14006f9f0  mov     rax, rbx
0x14006f9f3  jmp     short loc_14006FA6E
0x14006f9f5  mov     rcx, rsi; lpMem
0x14006f9f8  call    pMemFree
0x14006f9fd  call    cs:__imp_GetLastError
0x14006fa03  mov     edx, eax
0x14006fa05  lea     rcx, aExpandenvironm; "ExpandEnvironmentStrings() failed, ec=%"...
0x14006fa0c  call    fax_dprintf
0x14006fa11  xor     esi, esi
0x14006fa13  mov     rcx, rbx; lpMem
0x14006fa16  call    pMemFree
0x14006fa1b  test    rdi, rdi
0x14006fa1e  jz      short loc_14006FA6C
0x14006fa20  inc     r15
0x14006fa23  cmp     [rdi+r15*2], si
0x14006fa28  jnz     short loc_14006FA20
0x14006fa2a  lea     eax, ds:2[r15*2]
0x14006fa32  mov     ecx, eax; dwBytes
0x14006fa34  mov     [rbp+cbData], eax
0x14006fa37  call    pMemAlloc
0x14006fa3c  mov     rbx, rax
0x14006fa3f  test    rax, rax
0x14006fa42  jz      short loc_14006FA6C
0x14006fa44  mov     edx, [rbp+cbData]; unsigned __int64
0x14006fa47  mov     r8, rdi; unsigned __int16 *
0x14006fa4a  mov     rcx, rax; unsigned __int16 *
0x14006fa4d  call    ?StringCbCopyW@@YAJPEAG_KPEBG@Z; StringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x14006fa52  test    eax, eax
0x14006fa54  jns     short loc_14006F9F0
0x14006fa56  mov     edx, eax
0x14006fa58  lea     rcx, aStringcbcopyFa; "StringCbCopy failed, hr = 0x%x"
0x14006fa5f  call    fax_dprintf
0x14006fa64  mov     rcx, rbx; lpMem
0x14006fa67  call    pMemFree
0x14006fa6c  xor     eax, eax
0x14006fa6e  add     rsp, 48h
0x14006fa72  pop     r15
0x14006fa74  pop     r14
0x14006fa76  pop     r13
0x14006fa78  pop     r12
0x14006fa7a  pop     rdi
0x14006fa7b  pop     rsi
0x14006fa7c  pop     rbx
0x14006fa7d  pop     rbp
0x14006fa7e  retn
```
