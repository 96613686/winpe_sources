# EEDBManager::GetEnrollmentType(_GUID,EnrollmentEnrollType *)

- ea: `0x180006950`
- end: `0x180006d85`
- name: `?GetEnrollmentType@EEDBManager@@SAJU_GUID@@PEAW4EnrollmentEnrollType@@@Z`
- size: `1077`
- prototype: `static int(struct _GUID *__struct_ptr, enum EnrollmentEnrollType *)`
- caller_count: `16`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800141d0`
- `0x18001796c`
- `0x180036c60`
- `0x180036d80`
- `0x180038a30`
- `0x180038ae0`
- `0x180040078`
- `0x180041e80`
- `0x1800426e0`
- `0x180066f10`
- `0x180067c90`
- `0x18006b980`
- `0x18006d5c0`
- `0x18006da50`
- `0x18006e7c0`
- `0x180077540`

## callees

- `0x1800067a0`
- `0x180006950`
- `0x18002e1a0`
- `0x180078040`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180006d1e`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180006d1e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006b37`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006c7c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006b37`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180006c7c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180006be5`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180006be5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006bff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006ce6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006d09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006d75`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006bff`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006ce6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006d09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180006d75`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800069bf`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800069bf`

## pseudocode

```c
__int64 __fastcall EEDBManager::GetEnrollmentType(struct _GUID *a1, enum EnrollmentEnrollType *a2)
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
  *(_DWORD *)a2 = 63;
  v4 = 39;
  pcbData = 4;
  hkey = 0;
  rguid = v2;
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
0x180006950  push    rbp
0x180006952  push    rbx
0x180006953  push    r12
0x180006955  push    r13
0x180006957  push    r15
0x180006959  lea     rbp, [rsp-440h]
0x180006961  sub     rsp, 540h
0x180006968  mov     rax, cs:__security_cookie
0x18000696f  xor     rax, rsp
0x180006972  mov     [rbp+460h+var_40], rax
0x180006979  movaps  xmm0, xmmword ptr [rcx]
0x18000697c  xor     r13d, r13d
0x18000697f  mov     r12, rdx
0x180006982  mov     dword ptr [rdx], 3Fh ; '?'
0x180006988  mov     ebx, 27h ; '''
0x18000698d  mov     [rsp+560h+var_518], 4
0x180006995  mov     r8d, ebx; cchMax
0x180006998  mov     [rsp+560h+hkey], r13
0x18000699d  lea     rdx, [rbp+460h+sz]; lpsz
0x1800069a1  movdqa  xmmword ptr [rsp+560h+rguid.Data1], xmm0
0x1800069a7  lea     rcx, [rsp+560h+rguid]; rguid
0x1800069ac  mov     [rbp+460h+var_250], r13w
0x1800069b4  mov     [rsp+560h+String1], r13w
0x1800069ba  mov     [rbp+460h+sz], r13w
0x1800069bf  call    cs:__imp_StringFromGUID2
0x1800069c5  cmp     eax, ebx
0x1800069c7  jnz     loc_180006D16
0x1800069cd  mov     ecx, ebx
0x1800069cf  lea     rax, [rbp+460h+sz]
0x1800069d3  cmp     [rax], r13w
0x1800069d7  jz      short loc_1800069E3
0x1800069d9  add     rax, 2
0x1800069dd  sub     rcx, 1
0x1800069e1  jnz     short loc_1800069D3
0x1800069e3  mov     r15d, 80070057h
0x1800069e9  mov     [rsp+560h+var_28], rdi
0x1800069f1  test    rcx, rcx
0x1800069f4  mov     [rsp+560h+var_30], r14
0x1800069fc  mov     edx, r15d
0x1800069ff  cmovnz  edx, r13d
0x180006a03  jz      loc_180006C26
0x180006a09  mov     r10d, 25h ; '%'
0x180006a0f  mov     eax, r10d
0x180006a12  sub     rax, rcx
0x180006a15  cmp     rax, 24h ; '$'
0x180006a19  ja      loc_180006C2E
0x180006a1f  mov     edi, 7FFFFFFEh
0x180006a24  lea     rdx, [rbp+460h+var_4AE]
0x180006a28  mov     ecx, edi
0x180006a2a  lea     r9, [rsp+560h+String1]
0x180006a2f  mov     r8, rbx
0x180006a32  test    rcx, rcx
0x180006a35  jz      short loc_180006A54
0x180006a37  movzx   eax, word ptr [rdx]
0x180006a3a  test    ax, ax
0x180006a3d  jz      short loc_180006A54
0x180006a3f  mov     [r9], ax
0x180006a43  add     rdx, 2
0x180006a47  add     r9, 2
0x180006a4b  dec     rcx
0x180006a4e  sub     r8, 1
0x180006a52  jnz     short loc_180006A32
0x180006a54  test    r8, r8
0x180006a57  lea     rcx, [r9-2]
0x180006a5b  mov     r14d, 8007007Ah
0x180006a61  cmovnz  rcx, r9
0x180006a65  mov     edx, r14d
0x180006a68  cmovnz  edx, r13d
0x180006a6c  mov     [rcx], r13w
0x180006a70  jz      loc_180006C26
0x180006a76  lea     rax, [rsp+560h+String1]
0x180006a7b  nop     dword ptr [rax+rax+00h]
0x180006a80  cmp     [rax], r13w
0x180006a84  jz      short loc_180006A90
0x180006a86  add     rax, 2
0x180006a8a  sub     rbx, 1
0x180006a8e  jnz     short loc_180006A80
0x180006a90  test    rbx, rbx
0x180006a93  cmovnz  r15d, r13d
0x180006a97  jz      loc_180006BA4
0x180006a9d  sub     r10, rbx
0x180006aa0  cmp     r10, 24h ; '$'
0x180006aa4  ja      loc_180006C2E
0x180006aaa  mov     [rsp+560h+arg_10], rsi
0x180006ab2  lea     rax, [rbx+rbx]
0x180006ab6  mov     rsi, r13
0x180006ab9  lea     rcx, [rbp+460h+var_4B4]
0x180006abd  sub     rcx, rax
0x180006ac0  mov     eax, 2000h
0x180006ac5  cmp     cs:word_1800AFC84, ax
0x180006acc  setnz   sil
0x180006ad0  add     rsi, 0FFFFFFFF80000001h
0x180006ad7  mov     [rcx], r13w
0x180006adb  mov     [rsp+560h+hkey], r13
0x180006ae0  cmp     rsi, 0FFFFFFFF80000002h
0x180006ae7  jz      loc_180006D1E
0x180006aed  mov     ebx, 104h
0x180006af2  lea     rax, [rsp+560h+String1]
0x180006af7  mov     rdx, rbx; unsigned __int64
0x180006afa  lea     r9, SubKey; "Software\\Microsoft\\Enrollments"
0x180006b01  mov     [rsp+560h+phkResult], rax
0x180006b06  lea     r8, aSS_0; "%s\\%s"
0x180006b0d  lea     rcx, [rbp+460h+SubKey]; unsigned __int16 *
0x180006b11  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006b16  mov     r15d, eax
0x180006b19  test    eax, eax
0x180006b1b  js      short loc_180006B9C
0x180006b1d  lea     rax, [rsp+560h+hkey]
0x180006b22  mov     r9d, 20119h; samDesired
0x180006b28  xor     r8d, r8d; ulOptions
0x180006b2b  mov     [rsp+560h+phkResult], rax; phkResult
0x180006b30  lea     rdx, [rbp+460h+SubKey]; lpSubKey
0x180006b34  mov     rcx, rsi; hKey
0x180006b37  call    cs:__imp_RegOpenKeyExW
0x180006b3d  mov     r15d, eax
0x180006b40  test    eax, eax
0x180006b42  jg      loc_180006C39
0x180006b48  lea     rcx, [rbp+460h+SubKey]
0x180006b4c  lea     rdx, [rbp+460h+var_250]
0x180006b53  test    rdi, rdi
0x180006b56  jz      short loc_180006B74
0x180006b58  movzx   eax, word ptr [rcx]
0x180006b5b  test    ax, ax
0x180006b5e  jz      short loc_180006B74
0x180006b60  mov     [rdx], ax
0x180006b63  add     rcx, 2
0x180006b67  add     rdx, 2
0x180006b6b  dec     rdi
0x180006b6e  sub     rbx, 1
0x180006b72  jnz     short loc_180006B53
0x180006b74  test    rbx, rbx
0x180006b77  lea     rcx, [rdx-2]
0x180006b7b  cmovnz  rcx, rdx
0x180006b7f  cmovnz  r14d, r13d
0x180006b83  mov     [rcx], r13w
0x180006b87  test    r15d, r15d
0x180006b8a  js      loc_180006D67
0x180006b90  test    rbx, rbx
0x180006b93  jz      loc_180006D64
0x180006b99  mov     r15d, r13d
0x180006b9c  mov     rsi, [rsp+560h+arg_10]
0x180006ba4  mov     r14, [rsp+560h+var_30]
0x180006bac  mov     rdi, [rsp+560h+var_28]
0x180006bb4  test    r15d, r15d
0x180006bb7  js      loc_180006CDC
0x180006bbd  mov     rcx, [rsp+560h+hkey]; hkey
0x180006bc2  lea     rax, [rsp+560h+var_518]
0x180006bc7  mov     [rsp+560h+pcbData], rax; pcbData
0x180006bcc  lea     r8, aEnrollmenttype; "EnrollmentType"
0x180006bd3  mov     [rsp+560h+pvData], r12; pvData
0x180006bd8  mov     r9d, 10h; dwFlags
0x180006bde  xor     edx, edx; lpSubKey
0x180006be0  mov     [rsp+560h+phkResult], r13; pdwType
0x180006be5  call    cs:__imp_RegGetValueW
0x180006beb  mov     ebx, eax
0x180006bed  test    eax, eax
0x180006bef  jnz     loc_180006CF4
0x180006bf5  mov     rcx, [rsp+560h+hkey]; hKey
0x180006bfa  test    rcx, rcx
0x180006bfd  jz      short loc_180006C05
0x180006bff  call    cs:__imp_RegCloseKey
0x180006c05  xor     eax, eax
0x180006c07  mov     rcx, [rbp+460h+var_40]
0x180006c0e  xor     rcx, rsp; StackCookie
0x180006c11  call    __security_check_cookie
0x180006c16  add     rsp, 540h
0x180006c1d  pop     r15
0x180006c1f  pop     r13
0x180006c21  pop     r12
0x180006c23  pop     rbx
0x180006c24  pop     rbp
0x180006c25  retn
0x180006c26  mov     r15d, edx
0x180006c29  jmp     loc_180006BA4
0x180006c2e  mov     r15d, 8000FFFFh
0x180006c34  jmp     loc_180006BA4
0x180006c39  movzx   r15d, ax
0x180006c3d  or      r15d, 80070000h
0x180006c44  jmp     loc_180006B48
0x180006c49  lea     eax, [r15+7FF8FFFEh]
0x180006c50  cmp     eax, 1
0x180006c53  jbe     loc_180006AF2
0x180006c59  jmp     loc_180006B48
0x180006c5e  lea     rax, [rsp+560h+hkey]
0x180006c63  mov     r9d, 20119h; samDesired
0x180006c69  xor     r8d, r8d; ulOptions
0x180006c6c  mov     [rsp+560h+phkResult], rax; phkResult
0x180006c71  lea     rdx, [rbp+460h+SubKey]; lpSubKey
0x180006c75  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180006c7c  call    cs:__imp_RegOpenKeyExW
0x180006c82  mov     r15d, eax
0x180006c85  test    eax, eax
0x180006c87  jle     short loc_180006C94
0x180006c89  movzx   r15d, ax
0x180006c8d  or      r15d, 80070000h
0x180006c94  test    r15d, r15d
0x180006c97  jns     short loc_180006C49
0x180006c99  mov     r8d, 6; MaxCount
0x180006c9f  lea     rdx, aStatus; "Status"
0x180006ca6  lea     rcx, [rsp+560h+String1]; String1
0x180006cab  call    wcsncmp_0
0x180006cb0  test    eax, eax
0x180006cb2  jz      loc_180006B48
0x180006cb8  mov     r8d, 7; MaxCount
0x180006cbe  lea     rdx, aContext_0; "Context"
0x180006cc5  lea     rcx, [rsp+560h+String1]; String1
0x180006cca  call    wcsncmp_0
0x180006ccf  test    eax, eax
0x180006cd1  jz      loc_180006B48
0x180006cd7  jmp     loc_180006C49
0x180006cdc  mov     rcx, [rsp+560h+hkey]; hKey
0x180006ce1  test    rcx, rcx
0x180006ce4  jz      short loc_180006CEC
0x180006ce6  call    cs:__imp_RegCloseKey
0x180006cec  mov     eax, r15d
0x180006cef  jmp     loc_180006C07
0x180006cf4  jle     short loc_180006CFF
0x180006cf6  movzx   ebx, ax
0x180006cf9  or      ebx, 80070000h
0x180006cff  mov     rcx, [rsp+560h+hkey]; hKey
0x180006d04  test    rcx, rcx
0x180006d07  jz      short loc_180006D0F
0x180006d09  call    cs:__imp_RegCloseKey
0x180006d0f  mov     eax, ebx
0x180006d11  jmp     loc_180006C07
0x180006d16  mov     r15d, 8000FFFFh
0x180006d1c  jmp     short loc_180006CDC
0x180006d1e  call    cs:__imp_RtlIsStateSeparationEnabled
0x180006d24  test    al, al
0x180006d26  jz      loc_180006AED
0x180006d2c  lea     rax, [rsp+560h+String1]
0x180006d31  mov     ebx, 104h
0x180006d36  mov     edx, ebx; unsigned __int64
0x180006d38  mov     [rsp+560h+phkResult], rax
0x180006d3d  lea     r9, aOsdataSoftware_8; "OSData\\Software\\Microsoft\\Enrollment"...
0x180006d44  lea     r8, aSS_0; "%s\\%s"
0x180006d4b  lea     rcx, [rbp+460h+SubKey]; unsigned __int16 *
0x180006d4f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006d54  mov     r15d, eax
0x180006d57  test    eax, eax
0x180006d59  js      loc_180006B9C
0x180006d5f  jmp     loc_180006C5E
0x180006d64  mov     r15d, r14d
0x180006d67  mov     rcx, [rsp+560h+hkey]; hKey
0x180006d6c  test    rcx, rcx
0x180006d6f  jz      loc_180006B9C
0x180006d75  call    cs:__imp_RegCloseKey
0x180006d7b  mov     [rsp+560h+hkey], r13
0x180006d80  jmp     loc_180006B9C
```
