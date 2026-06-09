# CCertTypeInfo::_LoadFromRegBase(ushort const *,HKEY__ *)

- ea: `0x18000b800`
- end: `0x18000c14e`
- name: `?_LoadFromRegBase@CCertTypeInfo@@IEAAJPEBGPEAUHKEY__@@@Z`
- size: `2382`
- prototype: `__int64 __fastcall(CCertTypeInfo *this, const unsigned __int16 *, HKEY)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800327c4`

## callees

- `0x18000b800`
- `0x18000ce90`
- `0x18000cfc0`
- `0x18000fac0`
- `0x180011ebc`
- `0x180014fac`
- `0x180038286`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000bb4b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000be59`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000bb4b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000be59`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c0ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c0ed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c135`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c135`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bb16`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bb7e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bbe3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bc41`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bc7c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bcff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bd80`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bddb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000be2b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000be95`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000befb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bfec`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bb16`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bb7e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bbe3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bc41`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bc7c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bcff`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bd80`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bddb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000be2b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000be95`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000befb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000bfec`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b842`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b842`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18000beac`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18000beac`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18000bebe`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18000bebe`

## string_xrefs

- `0x18000bef0`: `msPKI-Template-Schema-Version`
- `0x18000c0b1`: `msPKI-Template-Schema-Version`
- `0x18000c009`: `msPKI-Template-Minor-Revision`
- `0x18000ba73`: `pKICriticalExtensions`
- `0x18000bcf4`: `PathLen`
- `0x18000be20`: `Security`
- `0x18000be8a`: `Security`
- `0x18000baa6`: `CriticalExtensions`

## pseudocode

```c
__int64 __fastcall CCertTypeInfo::_LoadFromRegBase(CCertTypeInfo *this, const unsigned __int16 *a2, HKEY a3)
{
  LSTATUS v4; // eax
  int v5; // ebx
  bool v6; // cc
  struct CCAProperty *v7; // rax
  struct CCAProperty *v8; // rdi
  struct CCAProperty **v9; // r14
  struct CCAProperty *v10; // rax
  struct CCAProperty *v11; // rax
  struct CCAProperty *v12; // rax
  struct CCAProperty *v13; // rax
  struct CCAProperty *v14; // rax
  struct CCAProperty *v15; // rax
  struct CCAProperty *v16; // rax
  LSTATUS v17; // eax
  BYTE *v18; // rax
  LSTATUS v19; // eax
  LSTATUS v20; // eax
  LSTATUS v21; // eax
  LSTATUS v22; // eax
  LSTATUS v23; // eax
  int v24; // ecx
  BOOL v25; // edx
  LSTATUS v26; // eax
  LSTATUS v27; // eax
  BYTE *v28; // rax
  DWORD SecurityDescriptorLength; // eax
  unsigned int i; // r12d
  const unsigned __int16 **v31; // r15
  struct CCAProperty *v32; // rax
  const unsigned __int16 *v33; // rcx
  const wchar_t *v34; // rbx
  DWORD Type; // [rsp+30h] [rbp-28h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-24h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-20h] BYREF
  struct CCAProperty *v39[3]; // [rsp+40h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+B8h] [rbp+60h] BYREF

  Type = 0;
  cbData = 0;
  *(_DWORD *)Data = 0;
  hKey = 0;
  v4 = RegOpenKeyExW(a3, a2, 0, 0x20019u, &hKey);
  v5 = v4;
  v6 = v4 <= 0;
  if ( v4 )
  {
LABEL_2:
    if ( !v6 )
      v5 = (unsigned __int16)v4 | 0x80070000;
    goto LABEL_146;
  }
  v7 = (struct CCAProperty *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  v39[0] = v7;
  if ( v7 )
  {
    *(_QWORD *)v7 = 0;
    *((_QWORD *)v7 + 2) = 0;
    *((_QWORD *)v7 + 1) = CertAllocString(L"displayName");
  }
  else
  {
    v8 = 0;
  }
  v39[0] = v8;
  if ( !v8 )
  {
LABEL_8:
    v5 = -2147024882;
    goto LABEL_142;
  }
  if ( !*((_QWORD *)v8 + 1) )
    goto LABEL_144;
  v5 = CCAProperty::LoadFromRegValue(v8, hKey, L"DisplayName");
  if ( v5 )
    goto LABEL_142;
  v9 = (struct CCAProperty **)((char *)this + 96);
  if ( this == (CCertTypeInfo *)-96LL )
  {
    v5 = -2147467261;
    goto LABEL_142;
  }
  v10 = *v9;
  if ( *v9 )
  {
    for ( ; *((_QWORD *)v10 + 2); v10 = (struct CCAProperty *)*((_QWORD *)v10 + 2) )
      ;
    *((_QWORD *)v10 + 2) = v8;
  }
  else
  {
    *v9 = v8;
  }
  v11 = (struct CCAProperty *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v11;
  v39[0] = v11;
  if ( v11 )
  {
    *(_QWORD *)v11 = 0;
    *((_QWORD *)v11 + 2) = 0;
    *((_QWORD *)v11 + 1) = CertAllocString(L"pKIDefaultCSPs");
  }
  else
  {
    v8 = 0;
  }
  v39[0] = v8;
  if ( !v8 )
  {
    v5 = -2147024882;
    goto LABEL_142;
  }
  if ( !*((_QWORD *)v8 + 1) )
    goto LABEL_144;
  v5 = CCAProperty::LoadFromRegValue(v8, hKey, L"SupportedCSPs");
  if ( v5 )
    goto LABEL_142;
  v12 = *v9;
  if ( *v9 )
  {
    for ( ; *((_QWORD *)v12 + 2); v12 = (struct CCAProperty *)*((_QWORD *)v12 + 2) )
      ;
    *((_QWORD *)v12 + 2) = v8;
  }
  else
  {
    *v9 = v8;
  }
  v13 = (struct CCAProperty *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v13;
  v39[0] = v13;
  if ( v13 )
  {
    *(_QWORD *)v13 = 0;
    *((_QWORD *)v13 + 2) = 0;
    *((_QWORD *)v13 + 1) = CertAllocString(L"pKIExtendedKeyUsage");
  }
  else
  {
    v8 = 0;
  }
  v39[0] = v8;
  if ( !v8 )
  {
    v5 = -2147024882;
    goto LABEL_142;
  }
  if ( !*((_QWORD *)v8 + 1) )
    goto LABEL_144;
  v5 = CCAProperty::LoadFromRegValue(v8, hKey, L"ExtKeyUsageSyntax");
  if ( v5 )
    goto LABEL_142;
  v14 = *v9;
  if ( *v9 )
  {
    for ( ; *((_QWORD *)v14 + 2); v14 = (struct CCAProperty *)*((_QWORD *)v14 + 2) )
      ;
    *((_QWORD *)v14 + 2) = v8;
  }
  else
  {
    *v9 = v8;
  }
  v15 = (struct CCAProperty *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v15;
  v39[0] = v15;
  if ( v15 )
  {
    *(_QWORD *)v15 = 0;
    *((_QWORD *)v15 + 2) = 0;
    *((_QWORD *)v15 + 1) = CertAllocString(L"pKICriticalExtensions");
  }
  else
  {
    v8 = 0;
  }
  v39[0] = v8;
  if ( !v8 )
  {
    v5 = -2147024882;
    goto LABEL_142;
  }
  if ( !*((_QWORD *)v8 + 1) )
  {
LABEL_144:
    CCAProperty::DeleteChain(v39);
    goto LABEL_145;
  }
  v5 = CCAProperty::LoadFromRegValue(v8, hKey, L"CriticalExtensions");
  if ( v5 )
    goto LABEL_142;
  v16 = *v9;
  if ( *v9 )
  {
    for ( ; *((_QWORD *)v16 + 2); v16 = (struct CCAProperty *)*((_QWORD *)v16 + 2) )
      ;
    *((_QWORD *)v16 + 2) = v8;
  }
  else
  {
    *v9 = v8;
  }
  v8 = 0;
  v39[0] = 0;
  v17 = RegQueryValueExW(hKey, L"KeyUsage", 0, &Type, 0, &cbData);
  v5 = v17;
  if ( v17 )
  {
    if ( v17 > 0 )
      v5 = (unsigned __int16)v17 | 0x80070000;
    goto LABEL_146;
  }
  if ( Type != 3 )
  {
LABEL_57:
    v5 = -2147024883;
    goto LABEL_146;
  }
  v18 = (BYTE *)LocalAlloc(0, cbData);
  *((_QWORD *)this + 5) = v18;
  if ( !v18 )
  {
LABEL_145:
    v5 = -2147024882;
    goto LABEL_146;
  }
  v19 = RegQueryValueExW(hKey, L"KeyUsage", 0, &Type, v18, &cbData);
  v5 = v19;
  if ( v19 )
  {
    if ( v19 > 0 )
      v5 = (unsigned __int16)v19 | 0x80070000;
    goto LABEL_146;
  }
  if ( Type != 3 )
  {
    v5 = -2147024883;
    goto LABEL_146;
  }
  *((_DWORD *)this + 8) = cbData;
  *((_DWORD *)this + 12) = 0;
  cbData = 4;
  v20 = RegQueryValueExW(hKey, L"Flags", 0, &Type, (LPBYTE)this + 56, &cbData);
  v5 = v20;
  if ( v20 )
  {
    if ( v20 > 0 )
      v5 = (unsigned __int16)v20 | 0x80070000;
    goto LABEL_146;
  }
  if ( Type != 4 )
  {
    v5 = -2147024883;
    goto LABEL_146;
  }
  cbData = 4;
  v21 = RegQueryValueExW(hKey, L"Revision", 0, &Type, (LPBYTE)this + 144, &cbData);
  v5 = v21;
  if ( v21 == 2 )
  {
    *((_DWORD *)this + 36) = 0;
    goto LABEL_71;
  }
  if ( !v21 )
  {
    if ( Type != 4 )
    {
      v5 = -2147024883;
      goto LABEL_146;
    }
LABEL_71:
    cbData = 4;
    v22 = RegQueryValueExW(hKey, L"KeySpec", 0, &Type, (LPBYTE)this + 60, &cbData);
    v5 = v22;
    if ( v22 )
    {
      if ( v22 > 0 )
        v5 = (unsigned __int16)v22 | 0x80070000;
      goto LABEL_146;
    }
    if ( Type != 4 )
    {
      v5 = -2147024883;
      goto LABEL_146;
    }
    cbData = 4;
    v23 = RegQueryValueExW(hKey, L"PathLen", 0, &Type, (LPBYTE)this + 24, &cbData);
    v5 = v23;
    if ( v23 )
    {
      if ( v23 > 0 )
        v5 = (unsigned __int16)v23 | 0x80070000;
      goto LABEL_146;
    }
    v24 = 1;
    v25 = (*((_DWORD *)this + 14) & 0x880) != 0;
    *((_DWORD *)this + 4) = v25;
    if ( *((_DWORD *)this + 6) == -1 || !v25 )
      v24 = 0;
    *((_DWORD *)this + 5) = v24;
    if ( Type != 4 )
      goto LABEL_88;
    cbData = 8;
    v26 = RegQueryValueExW(hKey, L"ValidityPeriod", 0, &Type, (LPBYTE)this + 104, &cbData);
    v5 = v26;
    if ( v26 )
    {
      if ( v26 > 0 )
        v5 = (unsigned __int16)v26 | 0x80070000;
      goto LABEL_142;
    }
    if ( Type == 3 )
    {
      cbData = 8;
      v27 = RegQueryValueExW(hKey, L"RenewalOverlap", 0, &Type, (LPBYTE)this + 112, &cbData);
      v5 = v27;
      if ( v27 )
      {
        if ( v27 > 0 )
          v5 = (unsigned __int16)v27 | 0x80070000;
        goto LABEL_142;
      }
      if ( Type == 3 )
      {
        if ( !RegQueryValueExW(hKey, L"Security", 0, &Type, 0, &cbData) && cbData )
        {
          if ( Type == 3 )
          {
            v28 = (BYTE *)LocalAlloc(0, cbData);
            *((_QWORD *)this + 17) = v28;
            if ( v28 )
            {
              v5 = RegQueryValueExW(hKey, L"Security", 0, &Type, v28, &cbData);
              if ( v5
                || (SecurityDescriptorLength = GetSecurityDescriptorLength(*((PSECURITY_DESCRIPTOR *)this + 17)),
                    !RtlValidRelativeSecurityDescriptor(
                       *((PSECURITY_DESCRIPTOR *)this + 17),
                       SecurityDescriptorLength,
                       0)) )
              {
                LocalFree(*((HLOCAL *)this + 17));
                *((_QWORD *)this + 17) = 0;
                if ( v5 > 0 )
                  v5 = (unsigned __int16)v5 | 0x80070000;
              }
              else
              {
                *((_DWORD *)this + 30) = 0;
                cbData = 4;
                if ( !RegQueryValueExW(hKey, L"msPKI-Template-Schema-Version", 0, &Type, Data, &cbData) )
                {
                  Type = 0;
                  cbData = 0;
                  *(_DWORD *)Data = 0;
                  for ( i = 0; i < 0xD; ++i )
                  {
                    v31 = (const unsigned __int16 **)(&g_CTV2Properties + 2 * i);
                    if ( *((_DWORD *)v31 + 2) )
                    {
                      v32 = (struct CCAProperty *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
                      v8 = v32;
                      v39[1] = v32;
                      if ( v32 )
                      {
                        v33 = *v31;
                        *(_QWORD *)v32 = 0;
                        *((_QWORD *)v32 + 2) = 0;
                        *((_QWORD *)v32 + 1) = CertAllocString(v33);
                      }
                      else
                      {
                        v8 = 0;
                      }
                      v39[0] = v8;
                      if ( !v8 )
                        goto LABEL_8;
                      if ( !*((_QWORD *)v8 + 1) )
                        goto LABEL_144;
                      v5 = CCAProperty::LoadFromRegValue(v8, hKey, *v31);
                      if ( v5 )
                        goto LABEL_142;
                      v5 = CCAProperty::Append((struct CCAProperty **)this + 12, v8);
                      if ( v5 )
                        goto LABEL_142;
                      v8 = 0;
                      v39[0] = 0;
                    }
                    else
                    {
                      cbData = 4;
                      v4 = RegQueryValueExW(hKey, *v31, 0, &Type, Data, &cbData);
                      v5 = v4;
                      v6 = v4 <= 0;
                      if ( v4 )
                        goto LABEL_2;
                      if ( Type != 4 )
                        goto LABEL_57;
                      v34 = *v31;
                      if ( !wcscmp_0(*v31, L"msPKI-Template-Minor-Revision") )
                      {
                        *((_DWORD *)this + 16) = *(_DWORD *)Data;
                      }
                      else if ( !wcscmp_0(v34, L"msPKI-RA-Signature") )
                      {
                        *((_DWORD *)this + 21) = *(_DWORD *)Data;
                      }
                      else if ( !wcscmp_0(v34, L"msPKI-Enrollment-Flag") )
                      {
                        *((_DWORD *)this + 17) = *(_DWORD *)Data;
                      }
                      else if ( !wcscmp_0(v34, L"msPKI-Private-Key-Flag") )
                      {
                        *((_DWORD *)this + 18) = *(_DWORD *)Data;
                      }
                      else if ( !wcscmp_0(v34, L"msPKI-Certificate-Name-Flag") )
                      {
                        *((_DWORD *)this + 19) = *(_DWORD *)Data;
                      }
                      else if ( !wcscmp_0(v34, L"msPKI-Minimal-Key-Size") )
                      {
                        *((_DWORD *)this + 20) = *(_DWORD *)Data;
                      }
                      else
                      {
                        if ( wcscmp_0(v34, L"msPKI-Template-Schema-Version") )
                        {
                          v5 = -2147418113;
                          goto LABEL_146;
                        }
                        *((_DWORD *)this + 22) = *(_DWORD *)Data;
                      }
                      Type = 0;
                      *(_DWORD *)Data = 0;
                    }
                  }
                }
                v5 = 0;
              }
            }
            else
            {
              v5 = -2147024882;
            }
          }
          else
          {
            v5 = -2147024883;
          }
          goto LABEL_142;
        }
LABEL_88:
        v5 = -2147024883;
        goto LABEL_142;
      }
      v5 = -2147024883;
    }
    else
    {
      v5 = -2147024883;
    }
LABEL_142:
    if ( v8 )
      CCAProperty::DeleteChain(v39);
    goto LABEL_146;
  }
  if ( v21 > 0 )
    v5 = (unsigned __int16)v21 | 0x80070000;
LABEL_146:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000b800  push    rbp
0x18000b802  push    rbx
0x18000b803  push    rsi
0x18000b804  push    rdi
0x18000b805  push    r12
0x18000b807  push    r13
0x18000b809  push    r14
0x18000b80b  push    r15
0x18000b80d  mov     rbp, rsp
0x18000b810  sub     rsp, 58h
0x18000b814  mov     rax, r8
0x18000b817  mov     rsi, rcx
0x18000b81a  xor     r13d, r13d
0x18000b81d  mov     [rbp+Type], r13d
0x18000b821  mov     [rbp+cbData], r13d
0x18000b825  mov     dword ptr [rbp+Data], r13d
0x18000b829  mov     [rbp+hKey], r13
0x18000b82d  lea     rcx, [rbp+hKey]
0x18000b831  mov     [rsp+58h+phkResult], rcx; phkResult
0x18000b836  mov     r9d, 20019h; samDesired
0x18000b83c  xor     r8d, r8d; ulOptions
0x18000b83f  mov     rcx, rax; hKey
0x18000b842  call    cs:__imp_RegOpenKeyExW
0x18000b848  mov     ebx, eax
0x18000b84a  test    eax, eax
0x18000b84c  jz      short loc_18000B862
0x18000b84e  jle     loc_18000C12C
0x18000b854  movzx   ebx, ax
0x18000b857  or      ebx, 80070000h
0x18000b85d  jmp     loc_18000C12C
0x18000b862  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b869  mov     ecx, 18h; unsigned __int64
0x18000b86e  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b873  mov     rdi, rax
0x18000b876  mov     [rbp+var_18], rax
0x18000b87a  test    rax, rax
0x18000b87d  jz      short loc_18000B898
0x18000b87f  mov     [rax], r13
0x18000b882  mov     [rax+10h], r13
0x18000b886  lea     rcx, aDisplayname_0; "displayName"
0x18000b88d  call    ?CertAllocString@@YAPEAGPEBG@Z; CertAllocString(ushort const *)
0x18000b892  mov     [rdi+8], rax
0x18000b896  jmp     short loc_18000B89B
0x18000b898  mov     rdi, r13
0x18000b89b  mov     [rbp+var_18], rdi
0x18000b89f  test    rdi, rdi
0x18000b8a2  jnz     short loc_18000B8AE
0x18000b8a4  mov     ebx, 8007000Eh
0x18000b8a9  jmp     loc_18000C10E
0x18000b8ae  cmp     qword ptr [rdi+8], 0
0x18000b8b3  jz      loc_18000C11E
0x18000b8b9  lea     r8, ValueName; "DisplayName"
0x18000b8c0  mov     rdx, [rbp+hKey]; HKEY
0x18000b8c4  mov     rcx, rdi; this
0x18000b8c7  call    ?LoadFromRegValue@CCAProperty@@QEAAJPEAUHKEY__@@PEBG@Z; CCAProperty::LoadFromRegValue(HKEY__ *,ushort const *)
0x18000b8cc  mov     ebx, eax
0x18000b8ce  test    eax, eax
0x18000b8d0  jnz     loc_18000C10E
0x18000b8d6  lea     r14, [rsi+60h]
0x18000b8da  test    r14, r14
0x18000b8dd  jz      loc_18000C109
0x18000b8e3  mov     rax, [r14]
0x18000b8e6  test    rax, rax
0x18000b8e9  jnz     short loc_18000B8F0
0x18000b8eb  mov     [r14], rdi
0x18000b8ee  jmp     short loc_18000B90F
0x18000b8f0  cmp     qword ptr [rax+10h], 0
0x18000b8f5  jz      short loc_18000B90B
0x18000b8f7  nop     word ptr [rax+rax+00000000h]
0x18000b900  mov     rax, [rax+10h]
0x18000b904  cmp     qword ptr [rax+10h], 0
0x18000b909  jnz     short loc_18000B900
0x18000b90b  mov     [rax+10h], rdi
0x18000b90f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b916  mov     ecx, 18h; unsigned __int64
0x18000b91b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b920  mov     rdi, rax
0x18000b923  mov     [rbp+var_18], rax
0x18000b927  test    rax, rax
0x18000b92a  jz      short loc_18000B945
0x18000b92c  mov     [rax], r13
0x18000b92f  mov     [rax+10h], r13
0x18000b933  lea     rcx, aPkidefaultcsps; "pKIDefaultCSPs"
0x18000b93a  call    ?CertAllocString@@YAPEAGPEBG@Z; CertAllocString(ushort const *)
0x18000b93f  mov     [rdi+8], rax
0x18000b943  jmp     short loc_18000B948
0x18000b945  mov     rdi, r13
0x18000b948  mov     [rbp+var_18], rdi
0x18000b94c  test    rdi, rdi
0x18000b94f  jnz     short loc_18000B95B
0x18000b951  mov     ebx, 8007000Eh
0x18000b956  jmp     loc_18000C10E
0x18000b95b  cmp     qword ptr [rdi+8], 0
0x18000b960  jz      loc_18000C11E
0x18000b966  lea     r8, aSupportedcsps; "SupportedCSPs"
0x18000b96d  mov     rdx, [rbp+hKey]; HKEY
0x18000b971  mov     rcx, rdi; this
0x18000b974  call    ?LoadFromRegValue@CCAProperty@@QEAAJPEAUHKEY__@@PEBG@Z; CCAProperty::LoadFromRegValue(HKEY__ *,ushort const *)
0x18000b979  mov     ebx, eax
0x18000b97b  test    eax, eax
0x18000b97d  jnz     loc_18000C10E
0x18000b983  mov     rax, [r14]
0x18000b986  test    rax, rax
0x18000b989  jnz     short loc_18000B990
0x18000b98b  mov     [r14], rdi
0x18000b98e  jmp     short loc_18000B9AF
0x18000b990  cmp     qword ptr [rax+10h], 0
0x18000b995  jz      short loc_18000B9AB
0x18000b997  nop     word ptr [rax+rax+00000000h]
0x18000b9a0  mov     rax, [rax+10h]
0x18000b9a4  cmp     qword ptr [rax+10h], 0
0x18000b9a9  jnz     short loc_18000B9A0
0x18000b9ab  mov     [rax+10h], rdi
0x18000b9af  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000b9b6  mov     ecx, 18h; unsigned __int64
0x18000b9bb  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b9c0  mov     rdi, rax
0x18000b9c3  mov     [rbp+var_18], rax
0x18000b9c7  test    rax, rax
0x18000b9ca  jz      short loc_18000B9E5
0x18000b9cc  mov     [rax], r13
0x18000b9cf  mov     [rax+10h], r13
0x18000b9d3  lea     rcx, aPkiextendedkey; "pKIExtendedKeyUsage"
0x18000b9da  call    ?CertAllocString@@YAPEAGPEBG@Z; CertAllocString(ushort const *)
0x18000b9df  mov     [rdi+8], rax
0x18000b9e3  jmp     short loc_18000B9E8
0x18000b9e5  mov     rdi, r13
0x18000b9e8  mov     [rbp+var_18], rdi
0x18000b9ec  test    rdi, rdi
0x18000b9ef  jnz     short loc_18000B9FB
0x18000b9f1  mov     ebx, 8007000Eh
0x18000b9f6  jmp     loc_18000C10E
0x18000b9fb  cmp     qword ptr [rdi+8], 0
0x18000ba00  jz      loc_18000C11E
0x18000ba06  lea     r8, aExtkeyusagesyn; "ExtKeyUsageSyntax"
0x18000ba0d  mov     rdx, [rbp+hKey]; HKEY
0x18000ba11  mov     rcx, rdi; this
0x18000ba14  call    ?LoadFromRegValue@CCAProperty@@QEAAJPEAUHKEY__@@PEBG@Z; CCAProperty::LoadFromRegValue(HKEY__ *,ushort const *)
0x18000ba19  mov     ebx, eax
0x18000ba1b  test    eax, eax
0x18000ba1d  jnz     loc_18000C10E
0x18000ba23  mov     rax, [r14]
0x18000ba26  test    rax, rax
0x18000ba29  jnz     short loc_18000BA30
0x18000ba2b  mov     [r14], rdi
0x18000ba2e  jmp     short loc_18000BA4F
0x18000ba30  cmp     qword ptr [rax+10h], 0
0x18000ba35  jz      short loc_18000BA4B
0x18000ba37  nop     word ptr [rax+rax+00000000h]
0x18000ba40  mov     rax, [rax+10h]
0x18000ba44  cmp     qword ptr [rax+10h], 0
0x18000ba49  jnz     short loc_18000BA40
0x18000ba4b  mov     [rax+10h], rdi
0x18000ba4f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000ba56  mov     ecx, 18h; unsigned __int64
0x18000ba5b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ba60  mov     rdi, rax
0x18000ba63  mov     [rbp+var_18], rax
0x18000ba67  test    rax, rax
0x18000ba6a  jz      short loc_18000BA85
0x18000ba6c  mov     [rax], r13
0x18000ba6f  mov     [rax+10h], r13
0x18000ba73  lea     rcx, aPkicriticalext; "pKICriticalExtensions"
0x18000ba7a  call    ?CertAllocString@@YAPEAGPEBG@Z; CertAllocString(ushort const *)
0x18000ba7f  mov     [rdi+8], rax
0x18000ba83  jmp     short loc_18000BA88
0x18000ba85  mov     rdi, r13
0x18000ba88  mov     [rbp+var_18], rdi
0x18000ba8c  test    rdi, rdi
0x18000ba8f  jnz     short loc_18000BA9B
0x18000ba91  mov     ebx, 8007000Eh
0x18000ba96  jmp     loc_18000C10E
0x18000ba9b  cmp     qword ptr [rdi+8], 0
0x18000baa0  jz      loc_18000C11E
0x18000baa6  lea     r8, aCriticalextens; "CriticalExtensions"
0x18000baad  mov     rdx, [rbp+hKey]; HKEY
0x18000bab1  mov     rcx, rdi; this
0x18000bab4  call    ?LoadFromRegValue@CCAProperty@@QEAAJPEAUHKEY__@@PEBG@Z; CCAProperty::LoadFromRegValue(HKEY__ *,ushort const *)
0x18000bab9  mov     ebx, eax
0x18000babb  test    eax, eax
0x18000babd  jnz     loc_18000C10E
0x18000bac3  mov     rax, [r14]
0x18000bac6  test    rax, rax
0x18000bac9  jnz     short loc_18000BAD0
0x18000bacb  mov     [r14], rdi
0x18000bace  jmp     short loc_18000BAEF
0x18000bad0  cmp     qword ptr [rax+10h], 0
0x18000bad5  jz      short loc_18000BAEB
0x18000bad7  nop     word ptr [rax+rax+00000000h]
0x18000bae0  mov     rax, [rax+10h]
0x18000bae4  cmp     qword ptr [rax+10h], 0
0x18000bae9  jnz     short loc_18000BAE0
0x18000baeb  mov     [rax+10h], rdi
0x18000baef  mov     rdi, r13
0x18000baf2  mov     [rbp+var_18], r13
0x18000baf6  lea     rax, [rbp+cbData]
0x18000bafa  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18000baff  mov     [rsp+58h+phkResult], r13; lpData
0x18000bb04  lea     r9, [rbp+Type]; lpType
0x18000bb08  xor     r8d, r8d; lpReserved
0x18000bb0b  lea     rdx, aKeyusage; "KeyUsage"
0x18000bb12  mov     rcx, [rbp+hKey]; hKey
0x18000bb16  call    cs:__imp_RegQueryValueExW
0x18000bb1c  mov     ebx, eax
0x18000bb1e  test    eax, eax
0x18000bb20  jz      short loc_18000BB36
0x18000bb22  jle     loc_18000C12C
0x18000bb28  movzx   ebx, ax
0x18000bb2b  or      ebx, 80070000h
0x18000bb31  jmp     loc_18000C12C
0x18000bb36  cmp     [rbp+Type], 3
0x18000bb3a  jz      short loc_18000BB46
0x18000bb3c  mov     ebx, 8007000Dh
0x18000bb41  jmp     loc_18000C12C
0x18000bb46  mov     edx, [rbp+cbData]; uBytes
0x18000bb49  xor     ecx, ecx; uFlags
0x18000bb4b  call    cs:__imp_LocalAlloc
0x18000bb51  mov     [rsi+28h], rax
0x18000bb55  test    rax, rax
0x18000bb58  jz      loc_18000C127
0x18000bb5e  lea     rcx, [rbp+cbData]
0x18000bb62  mov     [rsp+58h+lpcbData], rcx; lpcbData
0x18000bb67  mov     [rsp+58h+phkResult], rax; lpData
0x18000bb6c  lea     r9, [rbp+Type]; lpType
0x18000bb70  xor     r8d, r8d; lpReserved
0x18000bb73  lea     rdx, aKeyusage; "KeyUsage"
0x18000bb7a  mov     rcx, [rbp+hKey]; hKey
0x18000bb7e  call    cs:__imp_RegQueryValueExW
0x18000bb84  mov     ebx, eax
0x18000bb86  test    eax, eax
0x18000bb88  jz      short loc_18000BB9E
0x18000bb8a  jle     loc_18000C12C
0x18000bb90  movzx   ebx, ax
0x18000bb93  or      ebx, 80070000h
0x18000bb99  jmp     loc_18000C12C
0x18000bb9e  cmp     [rbp+Type], 3
0x18000bba2  jz      short loc_18000BBAE
0x18000bba4  mov     ebx, 8007000Dh
0x18000bba9  jmp     loc_18000C12C
0x18000bbae  mov     eax, [rbp+cbData]
0x18000bbb1  mov     [rsi+20h], eax
0x18000bbb4  mov     [rsi+30h], r13d
0x18000bbb8  mov     [rbp+cbData], 4
0x18000bbbf  lea     r12, [rsi+38h]
0x18000bbc3  lea     rax, [rbp+cbData]
0x18000bbc7  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18000bbcc  mov     [rsp+58h+phkResult], r12; lpData
0x18000bbd1  lea     r9, [rbp+Type]; lpType
0x18000bbd5  xor     r8d, r8d; lpReserved
0x18000bbd8  lea     rdx, aFlags; "Flags"
0x18000bbdf  mov     rcx, [rbp+hKey]; hKey
0x18000bbe3  call    cs:__imp_RegQueryValueExW
0x18000bbe9  mov     ebx, eax
0x18000bbeb  test    eax, eax
0x18000bbed  jz      short loc_18000BC03
0x18000bbef  jle     loc_18000C12C
0x18000bbf5  movzx   ebx, ax
0x18000bbf8  or      ebx, 80070000h
0x18000bbfe  jmp     loc_18000C12C
0x18000bc03  cmp     [rbp+Type], 4
0x18000bc07  jz      short loc_18000BC13
0x18000bc09  mov     ebx, 8007000Dh
0x18000bc0e  jmp     loc_18000C12C
0x18000bc13  mov     [rbp+cbData], 4
0x18000bc1a  lea     r15, [rsi+90h]
0x18000bc21  lea     rax, [rbp+cbData]
0x18000bc25  mov     [rsp+58h+lpcbData], rax; lpcbData
0x18000bc2a  mov     [rsp+58h+phkResult], r15; lpData
0x18000bc2f  lea     r9, [rbp+Type]; lpType
0x18000bc33  xor     r8d, r8d; lpReserved
0x18000bc36  lea     rdx, aRevision; "Revision"
0x18000bc3d  mov     rcx, [rbp+hKey]; hKey
0x18000bc41  call    cs:__imp_RegQueryValueExW
0x18000bc47  mov     ebx, eax
0x18000bc49  cmp     eax, 2
0x18000bc4c  jnz     short loc_18000BC9C
0x18000bc4e  mov     [r15], r13d
0x18000bc51  mov     [rbp+cbData], 4
0x18000bc58  lea     rax, [rsi+3Ch]
0x18000bc5c  lea     rcx, [rbp+cbData]
0x18000bc60  mov     [rsp+58h+lpcbData], rcx; lpcbData
0x18000bc65  mov     [rsp+58h+phkResult], rax; lpData
0x18000bc6a  lea     r9, [rbp+Type]; lpType
0x18000bc6e  xor     r8d, r8d; lpReserved
0x18000bc71  lea     rdx, aKeyspec; "KeySpec"
0x18000bc78  mov     rcx, [rbp+hKey]; hKey
0x18000bc7c  call    cs:__imp_RegQueryValueExW
0x18000bc82  mov     ebx, eax
0x18000bc84  test    eax, eax
0x18000bc86  jz      short loc_18000BCC4
0x18000bc88  jle     loc_18000C12C
0x18000bc8e  movzx   ebx, ax
0x18000bc91  or      ebx, 80070000h
0x18000bc97  jmp     loc_18000C12C
0x18000bc9c  test    eax, eax
0x18000bc9e  jz      short loc_18000BCB4
0x18000bca0  jle     loc_18000C12C
0x18000bca6  movzx   ebx, ax
0x18000bca9  or      ebx, 80070000h
0x18000bcaf  jmp     loc_18000C12C
  ... truncated ...
```
