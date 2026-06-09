# CPreferredList::InitializeFromRegistry(void)

- ea: `0x180068b74`
- end: `0x180068d89`
- name: `?InitializeFromRegistry@CPreferredList@@QEAAJXZ`
- size: `533`
- prototype: `__int64 __fastcall(CPreferredList *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001a790`
- `0x180020f90`
- `0x180027250`

## callees

- `0x180038458`
- `0x1800388a0`
- `0x180038e40`
- `0x180068b74`
- `0x180139f68`

## import_xrefs

- `ADVAPI32!RegEnumValueW` at `0x180068c6d`
- `ADVAPI32!RegEnumValueW` at `0x180068c6d`
- `ADVAPI32!RegOpenKeyExW` at `0x180068bda`
- `ADVAPI32!RegOpenKeyExW` at `0x180068bda`
- `ADVAPI32!RegCloseKey` at `0x180068d34`
- `ADVAPI32!RegCloseKey` at `0x180068d34`
- `ole32!CLSIDFromString` at `0x180068ca5`
- `ole32!CLSIDFromString` at `0x180068cd3`
- `ole32!CLSIDFromString` at `0x180068ca5`
- `ole32!CLSIDFromString` at `0x180068cd3`

## pseudocode

```c
LSTATUS __fastcall CPreferredList::InitializeFromRegistry(CPreferredList *this)
{
  LSTATUS result; // eax
  DWORD i; // edi
  LSTATUS v4; // eax
  unsigned __int64 v5; // rcx
  char *v6; // rax
  int v7; // edi
  _QWORD *v8; // rcx
  DWORD Type; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchValueName; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  GUID pclsid; // [rsp+58h] [rbp-A8h] BYREF
  GUID v14; // [rsp+68h] [rbp-98h] BYREF
  BYTE Data[2]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ValueName[40]; // [rsp+D0h] [rbp-30h] BYREF

  if ( *((_DWORD *)this + 2) )
    return 0;
  *((_DWORD *)this + 3) = 0;
  hKey = 0;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\DirectShow\\Preferred", 0, 1u, &hKey);
  if ( result )
  {
    if ( result == 2 )
    {
      *((_DWORD *)this + 2) = 1;
      return 0;
    }
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  else
  {
    for ( i = 0; ; ++i )
    {
      cchValueName = 39;
      Type = 3;
      cbData = 78;
      pclsid = 0;
      v14 = 0;
      v4 = RegEnumValueW(hKey, i, ValueName, &cchValueName, 0, &Type, Data, &cbData);
      if ( v4 == 14 )
        break;
      if ( v4 == 259 )
      {
        v7 = 0;
        goto LABEL_22;
      }
      if ( !v4 && Type == 1 && CLSIDFromString(ValueName, &pclsid) >= 0 )
      {
        v5 = cbData & 0xFFFFFFFE;
        if ( v5 >= 0x50 )
          _report_rangecheckfailure();
        *(_WORD *)&Data[v5] = 0;
        if ( CLSIDFromString((LPCOLESTR)Data, &v14) >= 0 )
        {
          v6 = (char *)operator new(0x28u);
          if ( !v6 )
            break;
          *(_QWORD *)v6 = 0;
          *(GUID *)(v6 + 8) = pclsid;
          *(GUID *)(v6 + 24) = v14;
          *(_QWORD *)v6 = *(_QWORD *)this;
          ++*((_DWORD *)this + 3);
          *(_QWORD *)this = v6;
        }
      }
    }
    v7 = -2147024882;
LABEL_22:
    RegCloseKey(hKey);
    if ( v7 < 0 )
    {
      while ( 1 )
      {
        v8 = *(_QWORD **)this;
        if ( !*(_QWORD *)this )
          break;
        *(_QWORD *)this = *v8;
        operator delete(v8);
      }
    }
    else
    {
      *((_DWORD *)this + 2) = 1;
    }
    return v7;
  }
  return result;
}

```

## disassembly

```asm
0x180068b74  mov     [rsp-8+arg_8], rbx
0x180068b79  mov     [rsp-8+arg_10], rdi
0x180068b7e  push    rbp
0x180068b7f  lea     rbp, [rsp-30h]
0x180068b84  sub     rsp, 130h
0x180068b8b  mov     rax, cs:__security_cookie
0x180068b92  xor     rax, rsp
0x180068b95  mov     [rbp+30h+var_10], rax
0x180068b99  cmp     dword ptr [rcx+8], 0
0x180068b9d  mov     rbx, rcx
0x180068ba0  jz      short loc_180068BA9
0x180068ba2  xor     eax, eax
0x180068ba4  jmp     loc_180068D4D
0x180068ba9  mov     dword ptr [rcx+0Ch], 0
0x180068bb0  lea     rax, [rsp+130h+hKey]
0x180068bb5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180068bbc  mov     [rsp+130h+phkResult], rax; phkResult
0x180068bc1  mov     r9d, 1; samDesired
0x180068bc7  mov     [rsp+130h+hKey], 0
0x180068bd0  xor     r8d, r8d; ulOptions
0x180068bd3  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\DirectShow\\Prefer"...
0x180068bda  call    cs:__imp_RegOpenKeyExW
0x180068be1  nop     dword ptr [rax+rax+00h]
0x180068be6  test    eax, eax
0x180068be8  jz      short loc_180068C0D
0x180068bea  cmp     eax, 2
0x180068bed  jnz     short loc_180068BF8
0x180068bef  mov     dword ptr [rbx+8], 1
0x180068bf6  jmp     short loc_180068BA2
0x180068bf8  test    eax, eax
0x180068bfa  jle     loc_180068D4D
0x180068c00  movzx   eax, ax
0x180068c03  or      eax, 80070000h
0x180068c08  jmp     loc_180068D4D
0x180068c0d  xor     edi, edi
0x180068c0f  mov     rcx, [rsp+130h+hKey]; hKey
0x180068c14  lea     rax, [rsp+130h+cbData]
0x180068c19  mov     [rsp+130h+lpcbData], rax; lpcbData
0x180068c1e  lea     r9, [rsp+130h+cchValueName]; lpcchValueName
0x180068c23  lea     rax, [rbp+30h+Data]
0x180068c27  mov     [rsp+130h+cchValueName], 27h ; '''
0x180068c2f  mov     [rsp+130h+lpData], rax; lpData
0x180068c34  lea     r8, [rbp+30h+ValueName]; lpValueName
0x180068c38  lea     rax, [rsp+130h+Type]
0x180068c3d  mov     [rsp+130h+Type], 3
0x180068c45  xorps   xmm0, xmm0
0x180068c48  mov     [rsp+130h+lpType], rax; lpType
0x180068c4d  xorps   xmm1, xmm1
0x180068c50  mov     [rsp+130h+phkResult], 0; lpReserved
0x180068c59  mov     edx, edi; dwIndex
0x180068c5b  mov     [rsp+130h+cbData], 4Eh ; 'N'
0x180068c63  movups  xmmword ptr [rsp+130h+pclsid.Data1], xmm0
0x180068c68  movups  xmmword ptr [rsp+130h+var_C8.Data1], xmm1
0x180068c6d  call    cs:__imp_RegEnumValueW
0x180068c74  nop     dword ptr [rax+rax+00h]
0x180068c79  cmp     eax, 0Eh
0x180068c7c  jz      loc_180068D2A
0x180068c82  cmp     eax, 103h
0x180068c87  jz      loc_180068D26
0x180068c8d  test    eax, eax
0x180068c8f  jnz     loc_180068D19
0x180068c95  cmp     [rsp+130h+Type], 1
0x180068c9a  jnz     short loc_180068D19
0x180068c9c  lea     rdx, [rsp+130h+pclsid]; pclsid
0x180068ca1  lea     rcx, [rbp+30h+ValueName]; lpsz
0x180068ca5  call    cs:__imp_CLSIDFromString
0x180068cac  nop     dword ptr [rax+rax+00h]
0x180068cb1  test    eax, eax
0x180068cb3  js      short loc_180068D19
0x180068cb5  mov     ecx, [rsp+130h+cbData]
0x180068cb9  and     rcx, 0FFFFFFFFFFFFFFFEh
0x180068cbd  cmp     rcx, 50h ; 'P'
0x180068cc1  jnb     short loc_180068D20
0x180068cc3  xor     eax, eax
0x180068cc5  lea     rdx, [rsp+130h+var_C8]; pclsid
0x180068cca  mov     word ptr [rbp+rcx+30h+Data], ax
0x180068ccf  lea     rcx, [rbp+30h+Data]; lpsz
0x180068cd3  call    cs:__imp_CLSIDFromString
0x180068cda  nop     dword ptr [rax+rax+00h]
0x180068cdf  test    eax, eax
0x180068ce1  js      short loc_180068D19
0x180068ce3  mov     ecx, 28h ; '('; Size
0x180068ce8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180068ced  test    rax, rax
0x180068cf0  jz      short loc_180068D2A
0x180068cf2  mov     qword ptr [rax], 0
0x180068cf9  movups  xmm0, xmmword ptr [rsp+130h+pclsid.Data1]
0x180068cfe  movdqu  xmmword ptr [rax+8], xmm0
0x180068d03  movups  xmm1, xmmword ptr [rsp+130h+var_C8.Data1]
0x180068d08  movdqu  xmmword ptr [rax+18h], xmm1
0x180068d0d  mov     rcx, [rbx]
0x180068d10  mov     [rax], rcx
0x180068d13  inc     dword ptr [rbx+0Ch]
0x180068d16  mov     [rbx], rax
0x180068d19  inc     edi
0x180068d1b  jmp     loc_180068C0F
0x180068d20  call    __report_rangecheckfailure
0x180068d26  xor     edi, edi
0x180068d28  jmp     short loc_180068D2F
0x180068d2a  mov     edi, 8007000Eh
0x180068d2f  mov     rcx, [rsp+130h+hKey]; hKey
0x180068d34  call    cs:__imp_RegCloseKey
0x180068d3b  nop     dword ptr [rax+rax+00h]
0x180068d40  test    edi, edi
0x180068d42  js      short loc_180068D7F
0x180068d44  mov     dword ptr [rbx+8], 1
0x180068d4b  mov     eax, edi
0x180068d4d  mov     rcx, [rbp+30h+var_10]
0x180068d51  xor     rcx, rsp; StackCookie
0x180068d54  call    __security_check_cookie
0x180068d59  lea     r11, [rsp+130h+var_s0]
0x180068d61  mov     rbx, [r11+18h]
0x180068d65  mov     rdi, [r11+20h]
0x180068d69  mov     rsp, r11
0x180068d6c  pop     rbp
0x180068d6d  retn
0x180068d6f  mov     rax, [rcx]
0x180068d72  mov     edx, 28h ; '('
0x180068d77  mov     [rbx], rax
0x180068d7a  call    ??3@YAXPEAXAEBUthrowing_tag@KsOpmLib@@@Z; operator delete(void *,KsOpmLib::throwing_tag const &)
0x180068d7f  mov     rcx, [rbx]; Block
0x180068d82  test    rcx, rcx
0x180068d85  jnz     short loc_180068D6F
0x180068d87  jmp     short loc_180068D4B
```
