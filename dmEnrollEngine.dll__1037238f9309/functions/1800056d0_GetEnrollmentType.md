# GetEnrollmentType

- ea: `0x1800056d0`
- end: `0x180005b06`
- name: `GetEnrollmentType`
- size: `1078`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800056d0`
- `0x1800067a0`
- `0x18002e1a0`
- `0x180078040`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180005a9f`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180005a9f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800058b7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800059fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800058b7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800059fd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180005965`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180005965`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000597f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005a67`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005a8a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005af6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000597f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005a67`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005a8a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005af6`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000573e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18000573e`

## pseudocode

```c
__int64 __fastcall GetEnrollmentType(GUID *a1, _DWORD *a2)
{
  GUID v2; // xmm0
  __int64 v4; // rbx
  __int64 v5; // rcx
  OLECHAR *p_sz; // rax
  signed int v7; // r15d
  __int64 v8; // rdx
  __int64 v9; // rdi
  wchar_t *v10; // rdx
  __int64 v11; // rcx
  wchar_t *v12; // r9
  __int64 v13; // r8
  wchar_t *v14; // rcx
  int v15; // r14d
  wchar_t *v16; // rax
  _WORD *v17; // rcx
  HKEY v18; // rsi
  __int64 v19; // rbx
  LSTATUS v20; // eax
  WCHAR *v21; // rcx
  __int16 *v22; // rdx
  __int16 *v23; // rcx
  LSTATUS ValueW; // eax
  unsigned int v25; // ebx
  LSTATUS v27; // eax
  HKEY hkey; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+48h] [rbp-B8h] BYREF
  GUID rguid; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t String1[38]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v32[4]; // [rsp+ACh] [rbp-54h] BYREF
  OLECHAR sz; // [rsp+B0h] [rbp-50h] BYREF
  char v34; // [rsp+B2h] [rbp-4Eh] BYREF
  WCHAR SubKey[264]; // [rsp+100h] [rbp+0h] BYREF
  __int16 v36; // [rsp+310h] [rbp+210h] BYREF

  v2 = *a1;
  *a2 = 63;
  pcbData = 4;
  v4 = 39;
  rguid = v2;
  hkey = 0;
  v36 = 0;
  String1[0] = 0;
  sz = 0;
  if ( StringFromGUID2(&rguid, &sz, 39) != 39 )
  {
    v7 = -2147418113;
    goto LABEL_50;
  }
  v5 = 39;
  p_sz = &sz;
  do
  {
    if ( !*p_sz )
      break;
    ++p_sz;
    --v5;
  }
  while ( v5 );
  v7 = -2147024809;
  LODWORD(v8) = -2147024809;
  if ( !v5 )
    goto LABEL_40;
  if ( (unsigned __int64)(37 - v5) > 0x24 )
    goto LABEL_41;
  v9 = 2147483646;
  v10 = (wchar_t *)&v34;
  v11 = 2147483646;
  v12 = String1;
  v13 = 39;
  do
  {
    if ( !v11 )
      break;
    if ( !*v10 )
      break;
    *v12++ = *v10++;
    --v11;
    --v13;
  }
  while ( v13 );
  v14 = v12 - 1;
  v15 = -2147024774;
  if ( v13 )
    v14 = v12;
  v8 = 2147942522LL;
  if ( v13 )
    v8 = 0;
  *v14 = 0;
  if ( !v13 )
  {
LABEL_40:
    v7 = v8;
    goto LABEL_35;
  }
  v16 = String1;
  do
  {
    if ( !*v16 )
      break;
    ++v16;
    --v4;
  }
  while ( v4 );
  if ( !v4 )
    goto LABEL_35;
  if ( (unsigned __int64)(37 - v4) > 0x24 )
  {
LABEL_41:
    v7 = -2147418113;
    goto LABEL_35;
  }
  v17 = &v32[-2 * v4];
  v18 = (HKEY)((word_1800AFC84 != 0x2000) - 0x7FFFFFFFLL);
  *v17 = 0;
  hkey = 0;
  if ( v18 == HKEY_LOCAL_MACHINE && (unsigned __int8)RtlIsStateSeparationEnabled(v17, v8) )
  {
    v19 = 260;
    v7 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", L"OSData\\Software\\Microsoft\\Enrollments", String1);
    if ( v7 < 0 )
      goto LABEL_35;
    v27 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20119u, &hkey);
    v7 = v27;
    if ( v27 > 0 )
      v7 = (unsigned __int16)v27 | 0x80070000;
    if ( v7 < 0 && (!wcsncmp_0(String1, L"Status", 6u) || !wcsncmp_0(String1, L"Context", 7u))
      || (unsigned int)(v7 + 2147024894) > 1 )
    {
      goto LABEL_26;
    }
  }
  else
  {
    v19 = 260;
  }
  v7 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", L"Software\\Microsoft\\Enrollments", String1);
  if ( v7 < 0 )
    goto LABEL_35;
  v20 = RegOpenKeyExW(v18, SubKey, 0, 0x20119u, &hkey);
  v7 = v20;
  if ( v20 > 0 )
    v7 = (unsigned __int16)v20 | 0x80070000;
LABEL_26:
  v21 = SubKey;
  v22 = &v36;
  do
  {
    if ( !v9 )
      break;
    if ( !*v21 )
      break;
    *v22++ = *v21++;
    --v9;
    --v19;
  }
  while ( v19 );
  v23 = v22 - 1;
  if ( v19 )
  {
    v23 = v22;
    v15 = 0;
  }
  *v23 = 0;
  if ( v7 >= 0 )
  {
    if ( v19 )
    {
      v7 = 0;
      goto LABEL_35;
    }
    v7 = v15;
  }
  if ( hkey )
  {
    RegCloseKey(hkey);
    hkey = 0;
  }
LABEL_35:
  if ( v7 >= 0 )
  {
    ValueW = RegGetValueW(hkey, 0, L"EnrollmentType", 0x10u, 0, a2, &pcbData);
    v25 = ValueW;
    if ( ValueW )
    {
      if ( ValueW > 0 )
        v25 = (unsigned __int16)ValueW | 0x80070000;
      if ( hkey )
        RegCloseKey(hkey);
      return v25;
    }
    else
    {
      if ( hkey )
        RegCloseKey(hkey);
      return 0;
    }
  }
LABEL_50:
  if ( hkey )
    RegCloseKey(hkey);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800056d0  push    rbp
0x1800056d2  push    rbx
0x1800056d3  push    r12
0x1800056d5  push    r13
0x1800056d7  push    r15
0x1800056d9  lea     rbp, [rsp-440h]
0x1800056e1  sub     rsp, 540h
0x1800056e8  mov     rax, cs:__security_cookie
0x1800056ef  xor     rax, rsp
0x1800056f2  mov     [rbp+460h+var_40], rax
0x1800056f9  movups  xmm0, xmmword ptr [rcx]
0x1800056fc  xor     r13d, r13d
0x1800056ff  mov     dword ptr [rdx], 3Fh ; '?'
0x180005705  mov     r12, rdx
0x180005708  mov     [rsp+560h+var_518], 4
0x180005710  mov     ebx, 27h ; '''
0x180005715  movaps  xmmword ptr [rsp+560h+rguid.Data1], xmm0
0x18000571a  mov     r8d, ebx; cchMax
0x18000571d  mov     [rsp+560h+hkey], r13
0x180005722  lea     rdx, [rbp+460h+sz]; lpsz
0x180005726  mov     [rbp+460h+var_250], r13w
0x18000572e  lea     rcx, [rsp+560h+rguid]; rguid
0x180005733  mov     [rsp+560h+String1], r13w
0x180005739  mov     [rbp+460h+sz], r13w
0x18000573e  call    cs:__imp_StringFromGUID2
0x180005744  cmp     eax, ebx
0x180005746  jnz     loc_180005A97
0x18000574c  mov     ecx, ebx
0x18000574e  lea     rax, [rbp+460h+sz]
0x180005752  cmp     [rax], r13w
0x180005756  jz      short loc_180005762
0x180005758  add     rax, 2
0x18000575c  sub     rcx, 1
0x180005760  jnz     short loc_180005752
0x180005762  mov     r15d, 80070057h
0x180005768  mov     [rsp+560h+var_28], rdi
0x180005770  test    rcx, rcx
0x180005773  mov     [rsp+560h+var_30], r14
0x18000577b  mov     edx, r15d
0x18000577e  cmovnz  edx, r13d
0x180005782  jz      loc_1800059A7
0x180005788  mov     r10d, 25h ; '%'
0x18000578e  mov     eax, r10d
0x180005791  sub     rax, rcx
0x180005794  cmp     rax, 24h ; '$'
0x180005798  ja      loc_1800059AF
0x18000579e  mov     edi, 7FFFFFFEh
0x1800057a3  lea     rdx, [rbp+460h+var_4AE]
0x1800057a7  mov     ecx, edi
0x1800057a9  lea     r9, [rsp+560h+String1]
0x1800057ae  mov     r8, rbx
0x1800057b1  test    rcx, rcx
0x1800057b4  jz      short loc_1800057D3
0x1800057b6  movzx   eax, word ptr [rdx]
0x1800057b9  test    ax, ax
0x1800057bc  jz      short loc_1800057D3
0x1800057be  mov     [r9], ax
0x1800057c2  add     rdx, 2
0x1800057c6  add     r9, 2
0x1800057ca  dec     rcx
0x1800057cd  sub     r8, 1
0x1800057d1  jnz     short loc_1800057B1
0x1800057d3  test    r8, r8
0x1800057d6  lea     rcx, [r9-2]
0x1800057da  mov     r14d, 8007007Ah
0x1800057e0  cmovnz  rcx, r9
0x1800057e4  mov     edx, r14d
0x1800057e7  cmovnz  edx, r13d
0x1800057eb  mov     [rcx], r13w
0x1800057ef  jz      loc_1800059A7
0x1800057f5  lea     rax, [rsp+560h+String1]
0x1800057fa  nop     word ptr [rax+rax+00h]
0x180005800  cmp     [rax], r13w
0x180005804  jz      short loc_180005810
0x180005806  add     rax, 2
0x18000580a  sub     rbx, 1
0x18000580e  jnz     short loc_180005800
0x180005810  test    rbx, rbx
0x180005813  cmovnz  r15d, r13d
0x180005817  jz      loc_180005924
0x18000581d  sub     r10, rbx
0x180005820  cmp     r10, 24h ; '$'
0x180005824  ja      loc_1800059AF
0x18000582a  mov     [rsp+560h+arg_10], rsi
0x180005832  lea     rax, [rbx+rbx]
0x180005836  mov     rsi, r13
0x180005839  lea     rcx, [rbp+460h+var_4B4]
0x18000583d  sub     rcx, rax
0x180005840  mov     eax, 2000h
0x180005845  cmp     cs:word_1800AFC84, ax
0x18000584c  setnz   sil
0x180005850  add     rsi, 0FFFFFFFF80000001h
0x180005857  mov     [rcx], r13w
0x18000585b  mov     [rsp+560h+hkey], r13
0x180005860  cmp     rsi, 0FFFFFFFF80000002h
0x180005867  jz      loc_180005A9F
0x18000586d  mov     ebx, 104h
0x180005872  lea     rax, [rsp+560h+String1]
0x180005877  mov     rdx, rbx; unsigned __int64
0x18000587a  lea     r9, SubKey; "Software\\Microsoft\\Enrollments"
0x180005881  mov     [rsp+560h+phkResult], rax
0x180005886  lea     r8, aSS_0; "%s\\%s"
0x18000588d  lea     rcx, [rbp+460h+SubKey]; unsigned __int16 *
0x180005891  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005896  mov     r15d, eax
0x180005899  test    eax, eax
0x18000589b  js      short loc_18000591C
0x18000589d  lea     rax, [rsp+560h+hkey]
0x1800058a2  mov     r9d, 20119h; samDesired
0x1800058a8  xor     r8d, r8d; ulOptions
0x1800058ab  mov     [rsp+560h+phkResult], rax; phkResult
0x1800058b0  lea     rdx, [rbp+460h+SubKey]; lpSubKey
0x1800058b4  mov     rcx, rsi; hKey
0x1800058b7  call    cs:__imp_RegOpenKeyExW
0x1800058bd  mov     r15d, eax
0x1800058c0  test    eax, eax
0x1800058c2  jg      loc_1800059BA
0x1800058c8  lea     rcx, [rbp+460h+SubKey]
0x1800058cc  lea     rdx, [rbp+460h+var_250]
0x1800058d3  test    rdi, rdi
0x1800058d6  jz      short loc_1800058F4
0x1800058d8  movzx   eax, word ptr [rcx]
0x1800058db  test    ax, ax
0x1800058de  jz      short loc_1800058F4
0x1800058e0  mov     [rdx], ax
0x1800058e3  add     rcx, 2
0x1800058e7  add     rdx, 2
0x1800058eb  dec     rdi
0x1800058ee  sub     rbx, 1
0x1800058f2  jnz     short loc_1800058D3
0x1800058f4  test    rbx, rbx
0x1800058f7  lea     rcx, [rdx-2]
0x1800058fb  cmovnz  rcx, rdx
0x1800058ff  cmovnz  r14d, r13d
0x180005903  mov     [rcx], r13w
0x180005907  test    r15d, r15d
0x18000590a  js      loc_180005AE8
0x180005910  test    rbx, rbx
0x180005913  jz      loc_180005AE5
0x180005919  mov     r15d, r13d
0x18000591c  mov     rsi, [rsp+560h+arg_10]
0x180005924  mov     r14, [rsp+560h+var_30]
0x18000592c  mov     rdi, [rsp+560h+var_28]
0x180005934  test    r15d, r15d
0x180005937  js      loc_180005A5D
0x18000593d  mov     rcx, [rsp+560h+hkey]; hkey
0x180005942  lea     rax, [rsp+560h+var_518]
0x180005947  mov     [rsp+560h+pcbData], rax; pcbData
0x18000594c  lea     r8, aEnrollmenttype; "EnrollmentType"
0x180005953  mov     [rsp+560h+pvData], r12; pvData
0x180005958  mov     r9d, 10h; dwFlags
0x18000595e  xor     edx, edx; lpSubKey
0x180005960  mov     [rsp+560h+phkResult], r13; pdwType
0x180005965  call    cs:__imp_RegGetValueW
0x18000596b  mov     ebx, eax
0x18000596d  test    eax, eax
0x18000596f  jnz     loc_180005A75
0x180005975  mov     rcx, [rsp+560h+hkey]; hKey
0x18000597a  test    rcx, rcx
0x18000597d  jz      short loc_180005985
0x18000597f  call    cs:__imp_RegCloseKey
0x180005985  mov     eax, r13d
0x180005988  mov     rcx, [rbp+460h+var_40]
0x18000598f  xor     rcx, rsp; StackCookie
0x180005992  call    __security_check_cookie
0x180005997  add     rsp, 540h
0x18000599e  pop     r15
0x1800059a0  pop     r13
0x1800059a2  pop     r12
0x1800059a4  pop     rbx
0x1800059a5  pop     rbp
0x1800059a6  retn
0x1800059a7  mov     r15d, edx
0x1800059aa  jmp     loc_180005924
0x1800059af  mov     r15d, 8000FFFFh
0x1800059b5  jmp     loc_180005924
0x1800059ba  movzx   r15d, ax
0x1800059be  or      r15d, 80070000h
0x1800059c5  jmp     loc_1800058C8
0x1800059ca  lea     eax, [r15+7FF8FFFEh]
0x1800059d1  cmp     eax, 1
0x1800059d4  jbe     loc_180005872
0x1800059da  jmp     loc_1800058C8
0x1800059df  lea     rax, [rsp+560h+hkey]
0x1800059e4  mov     r9d, 20119h; samDesired
0x1800059ea  xor     r8d, r8d; ulOptions
0x1800059ed  mov     [rsp+560h+phkResult], rax; phkResult
0x1800059f2  lea     rdx, [rbp+460h+SubKey]; lpSubKey
0x1800059f6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800059fd  call    cs:__imp_RegOpenKeyExW
0x180005a03  mov     r15d, eax
0x180005a06  test    eax, eax
0x180005a08  jle     short loc_180005A15
0x180005a0a  movzx   r15d, ax
0x180005a0e  or      r15d, 80070000h
0x180005a15  test    r15d, r15d
0x180005a18  jns     short loc_1800059CA
0x180005a1a  mov     r8d, 6; MaxCount
0x180005a20  lea     rdx, aStatus; "Status"
0x180005a27  lea     rcx, [rsp+560h+String1]; String1
0x180005a2c  call    wcsncmp_0
0x180005a31  test    eax, eax
0x180005a33  jz      loc_1800058C8
0x180005a39  mov     r8d, 7; MaxCount
0x180005a3f  lea     rdx, aContext_0; "Context"
0x180005a46  lea     rcx, [rsp+560h+String1]; String1
0x180005a4b  call    wcsncmp_0
0x180005a50  test    eax, eax
0x180005a52  jz      loc_1800058C8
0x180005a58  jmp     loc_1800059CA
0x180005a5d  mov     rcx, [rsp+560h+hkey]; hKey
0x180005a62  test    rcx, rcx
0x180005a65  jz      short loc_180005A6D
0x180005a67  call    cs:__imp_RegCloseKey
0x180005a6d  mov     eax, r15d
0x180005a70  jmp     loc_180005988
0x180005a75  jle     short loc_180005A80
0x180005a77  movzx   ebx, ax
0x180005a7a  or      ebx, 80070000h
0x180005a80  mov     rcx, [rsp+560h+hkey]; hKey
0x180005a85  test    rcx, rcx
0x180005a88  jz      short loc_180005A90
0x180005a8a  call    cs:__imp_RegCloseKey
0x180005a90  mov     eax, ebx
0x180005a92  jmp     loc_180005988
0x180005a97  mov     r15d, 8000FFFFh
0x180005a9d  jmp     short loc_180005A5D
0x180005a9f  call    cs:__imp_RtlIsStateSeparationEnabled
0x180005aa5  test    al, al
0x180005aa7  jz      loc_18000586D
0x180005aad  lea     rax, [rsp+560h+String1]
0x180005ab2  mov     ebx, 104h
0x180005ab7  mov     edx, ebx; unsigned __int64
0x180005ab9  mov     [rsp+560h+phkResult], rax
0x180005abe  lea     r9, aOsdataSoftware_8; "OSData\\Software\\Microsoft\\Enrollment"...
0x180005ac5  lea     r8, aSS_0; "%s\\%s"
0x180005acc  lea     rcx, [rbp+460h+SubKey]; unsigned __int16 *
0x180005ad0  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180005ad5  mov     r15d, eax
0x180005ad8  test    eax, eax
0x180005ada  js      loc_18000591C
0x180005ae0  jmp     loc_1800059DF
0x180005ae5  mov     r15d, r14d
0x180005ae8  mov     rcx, [rsp+560h+hkey]; hKey
0x180005aed  test    rcx, rcx
0x180005af0  jz      loc_18000591C
0x180005af6  call    cs:__imp_RegCloseKey
0x180005afc  mov     [rsp+560h+hkey], r13
0x180005b01  jmp     loc_18000591C
```
