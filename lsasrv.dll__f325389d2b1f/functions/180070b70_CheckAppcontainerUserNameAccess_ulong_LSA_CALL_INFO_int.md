# CheckAppcontainerUserNameAccess(ulong,_LSA_CALL_INFO *,int *)

- ea: `0x180070b70`
- end: `0x180070eeb`
- name: `?CheckAppcontainerUserNameAccess@@YAJKPEAU_LSA_CALL_INFO@@PEAH@Z`
- size: `891`
- prototype: `__int64 __fastcall(unsigned __int16, struct _LSA_CALL_INFO *, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180005d40`

## callees

- `0x180009330`
- `0x180014954`
- `0x180070b70`
- `0x1800b86d0`
- `0x18014a6b0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180070c66`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180070e79`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180070ec6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180070c66`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180070e79`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180070ec6`
- `ntdll!RtlFreeUnicodeString` at `0x180070e28`
- `ntdll!RtlFreeUnicodeString` at `0x180070e28`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180070df0`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180070df0`
- `ntdll!NtQueryInformationToken` at `0x180070cf2`
- `ntdll!NtQueryInformationToken` at `0x180070dcf`
- `ntdll!NtQueryInformationToken` at `0x180070cf2`
- `ntdll!NtQueryInformationToken` at `0x180070dcf`

## string_xrefs

- `0x180070c36`: `AllowUserInfoAccess`
- `0x180070e49`: `AppsReadAccess`
- `0x180070e96`: `AppsReadAccess`

## pseudocode

```c
__int64 __fastcall CheckAppcontainerUserNameAccess(unsigned __int16 a1, struct _LSA_CALL_INFO *a2, int *a3)
{
  bool v4; // zf
  NTSTATUS v7; // ebx
  int v8; // ecx
  int v10; // esi
  ULONG *p_pvData; // r15
  NTSTATUS v12; // eax
  unsigned __int64 v13; // rbx
  __int64 v14; // rcx
  unsigned __int64 v15; // rcx
  void *v16; // rsp
  void *v17; // rsp
  ULONG *v18; // rax
  __int64 v19; // [rsp+0h] [rbp-40h] BYREF
  int pvData; // [rsp+40h] [rbp+0h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp+4h] BYREF
  ULONG ReturnLength; // [rsp+48h] [rbp+8h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+50h] [rbp+10h] BYREF
  _BYTE TokenInformation[88]; // [rsp+68h] [rbp+28h] BYREF
  WCHAR SubKey[520]; // [rsp+C0h] [rbp+80h] BYREF

  *a3 = 0;
  v4 = *((_DWORD *)a2 + 16) == 1;
  ReturnLength = 0;
  v7 = 0;
  UnicodeString = 0;
  if ( v4 )
    goto LABEL_3;
  v8 = *((_DWORD *)a2 + 18);
  if ( (v8 & 1) == 0 || a1 == 2 || a1 == 12 )
    goto LABEL_3;
  if ( a1 == 3 || (unsigned int)a1 - 13 <= 1 )
    goto LABEL_11;
  if ( (v8 & 2) == 0 )
    return (unsigned int)v7;
  if ( (v8 & 8) != 0 )
  {
LABEL_3:
    *a3 = 1;
  }
  else
  {
LABEL_11:
    pvData = 0;
    pcbData = 4;
    if ( !RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Policies\\Microsoft\\Windows\\System",
            L"AllowUserInfoAccess",
            0x10u,
            0,
            &pvData,
            &pcbData) )
    {
      if ( pvData == 1 )
      {
        v10 = 1;
        goto LABEL_20;
      }
      if ( pvData == 2 )
      {
        v10 = 0;
LABEL_20:
        *a3 = v10;
        return (unsigned int)v7;
      }
    }
    p_pvData = (ULONG *)TokenInformation;
    v12 = NtQueryInformationToken(*((HANDLE *)a2 + 34), TokenUser, TokenInformation, 0x54u, &ReturnLength);
    v7 = v12;
    if ( v12 >= 0 )
      goto LABEL_37;
    if ( v12 != -1073741789 )
      return (unsigned int)v7;
    v13 = ReturnLength;
    p_pvData = 0;
    if ( !ReturnLength
      || ReturnLength > (unsigned __int64)g_ulMaxStackAllocSize
      || (unsigned __int64)ReturnLength + g_ulAdditionalProbeSize + 8 < ReturnLength
      || !(unsigned int)VerifyStackAvailable() )
    {
      goto LABEL_44;
    }
    v14 = v13 + 23;
    if ( v13 + 23 <= v13 + 8 )
      v14 = 0xFFFFFFFFFFFFFF0LL;
    v15 = v14 & 0xFFFFFFFFFFFFFFF0uLL;
    v16 = alloca(v15);
    v17 = alloca(v15);
    p_pvData = (ULONG *)&pvData;
    if ( &v19 == (__int64 *)-64LL || (pvData = 1801679955, (p_pvData = &ReturnLength) == 0) )
    {
LABEL_44:
      if ( v13 + 8 >= v13 )
      {
        v18 = (ULONG *)((__int64 (*)(void))g_pfnAllocate)();
        p_pvData = v18;
        if ( v18 )
        {
          *v18 = 1885431112;
          p_pvData = v18 + 2;
        }
      }
    }
    if ( !p_pvData )
      return (unsigned int)-1073741670;
    v7 = NtQueryInformationToken(*((HANDLE *)a2 + 34), TokenUser, p_pvData, ReturnLength, &ReturnLength);
    if ( v7 >= 0 )
    {
LABEL_37:
      v7 = RtlConvertSidToUnicodeString(&UnicodeString, *(PSID *)p_pvData, 1u);
      if ( v7 >= 0 )
      {
        v7 = RtlStringCchPrintfW(
               SubKey,
               0x208u,
               L"%s\\Software\\Microsoft\\Windows\\CurrentVersion\\AccountPicture",
               UnicodeString.Buffer);
        RtlFreeUnicodeString(&UnicodeString);
        if ( v7 >= 0 )
        {
          pvData = 0;
          pcbData = 4;
          if ( !RegGetValueW(HKEY_USERS, SubKey, L"AppsReadAccess", 0x10u, 0, &pvData, &pcbData)
            || (pvData = 0,
                pcbData = 4,
                !RegGetValueW(
                   HKEY_LOCAL_MACHINE,
                   L"Software\\Microsoft\\Windows\\CurrentVersion\\AccountPicture",
                   L"AppsReadAccess",
                   0x10u,
                   0,
                   &pvData,
                   &pcbData)) )
          {
            *a3 = pvData != 0;
          }
        }
      }
    }
    if ( p_pvData && p_pvData != (ULONG *)TokenInformation && *(p_pvData - 2) == 1885431112 )
      ((void (__fastcall *)(ULONG *))g_pfnFree)(p_pvData - 2);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180070b70  push    rbp
0x180070b72  push    rdi
0x180070b73  push    r12
0x180070b75  push    r14
0x180070b77  push    r15
0x180070b79  sub     rsp, 4E0h
0x180070b80  lea     rbp, [rsp+40h]
0x180070b85  mov     [rbp+4C0h+arg_0], rbx
0x180070b8c  mov     [rbp+4C0h+arg_18], rsi
0x180070b93  mov     rax, cs:__security_cookie
0x180070b9a  xor     rax, rbp
0x180070b9d  mov     [rbp+4C0h+var_30], rax
0x180070ba4  xor     r12d, r12d
0x180070ba7  xorps   xmm0, xmm0
0x180070baa  mov     [r8], r12d
0x180070bad  mov     rdi, r8
0x180070bb0  cmp     dword ptr [rdx+40h], 1
0x180070bb4  mov     r14, rdx
0x180070bb7  mov     eax, ecx
0x180070bb9  mov     [rbp+4C0h+ReturnLength], r12d
0x180070bbd  mov     ebx, r12d
0x180070bc0  movups  xmmword ptr [rbp+4C0h+UnicodeString.Length], xmm0
0x180070bc4  jz      short loc_180070BCE
0x180070bc6  mov     ecx, [rdx+48h]
0x180070bc9  test    cl, 1
0x180070bcc  jnz     short loc_180070C05
0x180070bce  mov     dword ptr [r8], 1
0x180070bd5  mov     eax, ebx
0x180070bd7  mov     rcx, [rbp+4C0h+var_30]
0x180070bde  xor     rcx, rbp; StackCookie
0x180070be1  call    __security_check_cookie
0x180070be6  mov     rbx, [rbp+4C0h+arg_0]
0x180070bed  mov     rsi, [rbp+4C0h+arg_18]
0x180070bf4  lea     rsp, [rbp+4A0h]
0x180070bfb  pop     r15
0x180070bfd  pop     r14
0x180070bff  pop     r12
0x180070c01  pop     rdi
0x180070c02  pop     rbp
0x180070c03  retn
0x180070c05  movzx   eax, ax
0x180070c08  cmp     eax, 2
0x180070c0b  jz      short loc_180070BCE
0x180070c0d  cmp     eax, 0Ch
0x180070c10  jz      short loc_180070BCE
0x180070c12  cmp     eax, 3
0x180070c15  jz      short loc_180070C29
0x180070c17  add     eax, 0FFFFFFF3h
0x180070c1a  cmp     eax, 1
0x180070c1d  jbe     short loc_180070C29
0x180070c1f  test    cl, 2
0x180070c22  jz      short loc_180070BD5
0x180070c24  test    cl, 8
0x180070c27  jnz     short loc_180070BCE
0x180070c29  lea     rax, [rbp+4C0h+var_4BC]
0x180070c2d  mov     [rbp+4C0h+var_4C0], r12d
0x180070c31  mov     [rsp+500h+pcbData], rax; pcbData
0x180070c36  lea     r8, aAllowuserinfoa; "AllowUserInfoAccess"
0x180070c3d  lea     rax, [rbp+4C0h+var_4C0]
0x180070c41  mov     [rbp+4C0h+var_4BC], 4
0x180070c48  mov     [rsp+500h+pvData], rax; pvData
0x180070c4d  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180070c54  mov     r9d, 10h; dwFlags
0x180070c5a  mov     [rsp+500h+pdwType], r12; pdwType
0x180070c5f  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180070c66  call    cs:__imp_RegGetValueW
0x180070c6d  nop     dword ptr [rax+rax+00h]
0x180070c72  test    eax, eax
0x180070c74  jnz     short loc_180070CCD
0x180070c76  mov     eax, [rbp+4C0h+var_4C0]
0x180070c79  cmp     eax, 1
0x180070c7c  jz      short loc_180070CC1
0x180070c7e  cmp     eax, 2
0x180070c81  jnz     short loc_180070CCD
0x180070c83  mov     esi, r12d
0x180070c86  jmp     short loc_180070CC6
0x180070c88  test    r15, r15
0x180070c8b  jz      loc_180070BD5
0x180070c91  lea     rax, [rbp+4C0h+TokenInformation]
0x180070c95  cmp     r15, rax
0x180070c98  jz      loc_180070BD5
0x180070c9e  cmp     dword ptr [r15-8], 70616548h
0x180070ca6  lea     rcx, [r15-8]
0x180070caa  jnz     loc_180070BD5
0x180070cb0  mov     rax, cs:g_pfnFree
0x180070cb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070cbc  jmp     loc_180070BD5
0x180070cc1  mov     esi, 1
0x180070cc6  mov     [rdi], esi
0x180070cc8  jmp     loc_180070BD5
0x180070ccd  mov     rcx, [r14+110h]; TokenHandle
0x180070cd4  lea     rax, [rbp+4C0h+ReturnLength]
0x180070cd8  mov     esi, 1
0x180070cdd  mov     [rsp+500h+pdwType], rax; ReturnLength
0x180070ce2  mov     edx, esi; TokenInformationClass
0x180070ce4  lea     r8, [rbp+4C0h+TokenInformation]; TokenInformation
0x180070ce8  mov     r9d, 54h ; 'T'; TokenInformationLength
0x180070cee  lea     r15, [rbp+4C0h+TokenInformation]
0x180070cf2  call    cs:__imp_NtQueryInformationToken
0x180070cf9  nop     dword ptr [rax+rax+00h]
0x180070cfe  mov     ebx, eax
0x180070d00  test    eax, eax
0x180070d02  jns     loc_180070DE5
0x180070d08  cmp     eax, 0C0000023h
0x180070d0d  jnz     loc_180070BD5
0x180070d13  mov     ebx, [rbp+4C0h+ReturnLength]
0x180070d16  mov     r15, r12
0x180070d19  test    rbx, rbx
0x180070d1c  jz      short loc_180070D80
0x180070d1e  cmp     rbx, cs:g_ulMaxStackAllocSize
0x180070d25  ja      short loc_180070D80
0x180070d27  mov     rcx, cs:g_ulAdditionalProbeSize
0x180070d2e  add     rcx, 8
0x180070d32  add     rcx, rbx
0x180070d35  cmp     rcx, rbx
0x180070d38  jb      short loc_180070D80
0x180070d3a  call    VerifyStackAvailable
0x180070d3f  test    eax, eax
0x180070d41  jz      short loc_180070D80
0x180070d43  lea     rax, [rbx+8]
0x180070d47  lea     rcx, [rax+0Fh]
0x180070d4b  cmp     rcx, rax
0x180070d4e  ja      short loc_180070D5A
0x180070d50  mov     rcx, 0FFFFFFFFFFFFFF0h
0x180070d5a  and     rcx, 0FFFFFFFFFFFFFFF0h
0x180070d5e  mov     rax, rcx
0x180070d61  call    _alloca_probe
0x180070d66  sub     rsp, rcx
0x180070d69  lea     r15, [rsp+500h+var_4C0]
0x180070d6e  test    r15, r15
0x180070d71  jz      short loc_180070D80
0x180070d73  mov     dword ptr [r15], 6B637453h
0x180070d7a  add     r15, 8
0x180070d7e  jnz     short loc_180070DA7
0x180070d80  lea     rcx, [rbx+8]
0x180070d84  cmp     rcx, rbx
0x180070d87  jb      short loc_180070DA7
0x180070d89  mov     rax, cs:g_pfnAllocate
0x180070d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070d95  mov     r15, rax
0x180070d98  test    rax, rax
0x180070d9b  jz      short loc_180070DA7
0x180070d9d  mov     dword ptr [rax], 70616548h
0x180070da3  add     r15, 8
0x180070da7  test    r15, r15
0x180070daa  jnz     short loc_180070DB6
0x180070dac  mov     ebx, 0C000009Ah
0x180070db1  jmp     loc_180070BD5
0x180070db6  mov     r9d, [rbp+4C0h+ReturnLength]; TokenInformationLength
0x180070dba  lea     rax, [rbp+4C0h+ReturnLength]
0x180070dbe  mov     rcx, [r14+110h]; TokenHandle
0x180070dc5  mov     r8, r15; TokenInformation
0x180070dc8  mov     edx, esi; TokenInformationClass
0x180070dca  mov     [rsp+500h+pdwType], rax; ReturnLength
0x180070dcf  call    cs:__imp_NtQueryInformationToken
0x180070dd6  nop     dword ptr [rax+rax+00h]
0x180070ddb  mov     ebx, eax
0x180070ddd  test    eax, eax
0x180070ddf  js      loc_180070C88
0x180070de5  mov     rdx, [r15]; Sid
0x180070de8  lea     rcx, [rbp+4C0h+UnicodeString]; UnicodeString
0x180070dec  movzx   r8d, sil; AllocateDestinationString
0x180070df0  call    cs:__imp_RtlConvertSidToUnicodeString
0x180070df7  nop     dword ptr [rax+rax+00h]
0x180070dfc  mov     ebx, eax
0x180070dfe  test    eax, eax
0x180070e00  js      loc_180070C88
0x180070e06  mov     r9, [rbp+4C0h+UnicodeString.Buffer]
0x180070e0a  lea     r8, aSSoftwareMicro; "%s\\Software\\Microsoft\\Windows\\Curre"...
0x180070e11  mov     edx, 208h; unsigned __int64
0x180070e16  lea     rcx, [rbp+4C0h+SubKey]; unsigned __int16 *
0x180070e1d  call    ?RtlStringCchPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180070e22  lea     rcx, [rbp+4C0h+UnicodeString]; UnicodeString
0x180070e26  mov     ebx, eax
0x180070e28  call    cs:__imp_RtlFreeUnicodeString
0x180070e2f  nop     dword ptr [rax+rax+00h]
0x180070e34  test    ebx, ebx
0x180070e36  js      loc_180070C88
0x180070e3c  lea     rax, [rbp+4C0h+var_4BC]
0x180070e40  mov     [rbp+4C0h+var_4C0], r12d
0x180070e44  mov     [rsp+500h+pcbData], rax; pcbData
0x180070e49  lea     r8, aAppsreadaccess; "AppsReadAccess"
0x180070e50  lea     rax, [rbp+4C0h+var_4C0]
0x180070e54  mov     [rbp+4C0h+var_4BC], 4
0x180070e5b  mov     [rsp+500h+pvData], rax; pvData
0x180070e60  lea     rdx, [rbp+4C0h+SubKey]; lpSubKey
0x180070e67  mov     r9d, 10h; dwFlags
0x180070e6d  mov     [rsp+500h+pdwType], r12; pdwType
0x180070e72  mov     rcx, 0FFFFFFFF80000003h; hkey
0x180070e79  call    cs:__imp_RegGetValueW
0x180070e80  nop     dword ptr [rax+rax+00h]
0x180070e85  test    eax, eax
0x180070e87  jz      short loc_180070EDA
0x180070e89  lea     rax, [rbp+4C0h+var_4BC]
0x180070e8d  mov     [rbp+4C0h+var_4C0], r12d
0x180070e91  mov     [rsp+500h+pcbData], rax; pcbData
0x180070e96  lea     r8, aAppsreadaccess; "AppsReadAccess"
0x180070e9d  lea     rax, [rbp+4C0h+var_4C0]
0x180070ea1  mov     [rbp+4C0h+var_4BC], 4
0x180070ea8  mov     [rsp+500h+pvData], rax; pvData
0x180070ead  lea     rdx, aSoftwareMicros_12; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180070eb4  mov     r9d, 10h; dwFlags
0x180070eba  mov     [rsp+500h+pdwType], r12; pdwType
0x180070ebf  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180070ec6  call    cs:__imp_RegGetValueW
0x180070ecd  nop     dword ptr [rax+rax+00h]
0x180070ed2  test    eax, eax
0x180070ed4  jnz     loc_180070C88
0x180070eda  cmp     [rbp+4C0h+var_4C0], r12d
0x180070ede  mov     eax, r12d
0x180070ee1  setnz   al
0x180070ee4  mov     [rdi], eax
0x180070ee6  jmp     loc_180070C88
```
