# CDisabledList::InitializeFromRegistry(void)

- ea: `0x1800689c0`
- end: `0x180068b6b`
- name: `?InitializeFromRegistry@CDisabledList@@QEAAJXZ`
- size: `427`
- prototype: `__int64 __fastcall(CDisabledList *__hidden this)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001a790`
- `0x180020f90`
- `0x180027250`

## callees

- `0x180038458`
- `0x1800388a0`
- `0x1800689c0`
- `0x180139f68`

## import_xrefs

- `ADVAPI32!RegEnumValueW` at `0x180068a9f`
- `ADVAPI32!RegEnumValueW` at `0x180068a9f`
- `ADVAPI32!RegOpenKeyExW` at `0x180068a20`
- `ADVAPI32!RegOpenKeyExW` at `0x180068a20`
- `ADVAPI32!RegCloseKey` at `0x180068b16`
- `ADVAPI32!RegCloseKey` at `0x180068b16`
- `ole32!CLSIDFromString` at `0x180068ac5`
- `ole32!CLSIDFromString` at `0x180068ac5`

## pseudocode

```c
LSTATUS __fastcall CDisabledList::InitializeFromRegistry(CDisabledList *this)
{
  LSTATUS result; // eax
  DWORD i; // edi
  LSTATUS v4; // eax
  char *v5; // rax
  int v6; // edi
  _QWORD *v7; // rcx
  DWORD cchValueName; // [rsp+40h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-80h] BYREF
  GUID pclsid; // [rsp+50h] [rbp-78h] BYREF
  WCHAR ValueName[40]; // [rsp+60h] [rbp-68h] BYREF

  if ( *((_DWORD *)this + 2) )
    return 0;
  *((_DWORD *)this + 3) = 0;
  hKey = 0;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\DirectShow\\DoNotUse", 0, 1u, &hKey);
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
      pclsid = GUID_NULL;
      cchValueName = 39;
      v4 = RegEnumValueW(hKey, i, ValueName, &cchValueName, 0, 0, 0, 0);
      if ( v4 == 14 )
        break;
      if ( v4 == 259 )
      {
        v6 = 0;
        goto LABEL_18;
      }
      if ( !v4 && CLSIDFromString(ValueName, &pclsid) >= 0 )
      {
        v5 = (char *)operator new(0x18u);
        if ( !v5 )
          break;
        *(_QWORD *)v5 = 0;
        *(GUID *)(v5 + 8) = pclsid;
        *(_QWORD *)v5 = *(_QWORD *)this;
        ++*((_DWORD *)this + 3);
        *(_QWORD *)this = v5;
      }
    }
    v6 = -2147024882;
LABEL_18:
    RegCloseKey(hKey);
    if ( v6 < 0 )
    {
      while ( 1 )
      {
        v7 = *(_QWORD **)this;
        if ( !*(_QWORD *)this )
          break;
        *(_QWORD *)this = *v7;
        operator delete(v7);
      }
    }
    else
    {
      *((_DWORD *)this + 2) = 1;
    }
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x1800689c0  mov     [rsp+arg_8], rbx
0x1800689c5  push    rdi
0x1800689c6  sub     rsp, 0C0h
0x1800689cd  mov     rax, cs:__security_cookie
0x1800689d4  xor     rax, rsp
0x1800689d7  mov     [rsp+0C8h+var_18], rax
0x1800689df  cmp     dword ptr [rcx+8], 0
0x1800689e3  mov     rbx, rcx
0x1800689e6  jz      short loc_1800689EF
0x1800689e8  xor     eax, eax
0x1800689ea  jmp     loc_180068B2F
0x1800689ef  mov     dword ptr [rcx+0Ch], 0
0x1800689f6  lea     rax, [rsp+0C8h+hKey]
0x1800689fb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180068a02  mov     [rsp+0C8h+phkResult], rax; phkResult
0x180068a07  mov     r9d, 1; samDesired
0x180068a0d  mov     [rsp+0C8h+hKey], 0
0x180068a16  xor     r8d, r8d; ulOptions
0x180068a19  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\DirectShow\\DoNotU"...
0x180068a20  call    cs:__imp_RegOpenKeyExW
0x180068a27  nop     dword ptr [rax+rax+00h]
0x180068a2c  test    eax, eax
0x180068a2e  jz      short loc_180068A53
0x180068a30  cmp     eax, 2
0x180068a33  jnz     short loc_180068A3E
0x180068a35  mov     dword ptr [rbx+8], 1
0x180068a3c  jmp     short loc_1800689E8
0x180068a3e  test    eax, eax
0x180068a40  jle     loc_180068B2F
0x180068a46  movzx   eax, ax
0x180068a49  or      eax, 80070000h
0x180068a4e  jmp     loc_180068B2F
0x180068a53  xor     edi, edi
0x180068a55  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180068a5c  mov     rcx, [rsp+0C8h+hKey]; hKey
0x180068a61  lea     r9, [rsp+0C8h+cchValueName]; lpcchValueName
0x180068a66  mov     [rsp+0C8h+lpcbData], 0; lpcbData
0x180068a6f  lea     r8, [rsp+0C8h+ValueName]; lpValueName
0x180068a74  mov     [rsp+0C8h+lpData], 0; lpData
0x180068a7d  mov     edx, edi; dwIndex
0x180068a7f  mov     [rsp+0C8h+lpType], 0; lpType
0x180068a88  movdqu  xmmword ptr [rsp+0C8h+pclsid.Data1], xmm0
0x180068a8e  mov     [rsp+0C8h+cchValueName], 27h ; '''
0x180068a96  mov     [rsp+0C8h+phkResult], 0; lpReserved
0x180068a9f  call    cs:__imp_RegEnumValueW
0x180068aa6  nop     dword ptr [rax+rax+00h]
0x180068aab  cmp     eax, 0Eh
0x180068aae  jz      short loc_180068B0C
0x180068ab0  cmp     eax, 103h
0x180068ab5  jz      short loc_180068B08
0x180068ab7  test    eax, eax
0x180068ab9  jnz     short loc_180068B01
0x180068abb  lea     rdx, [rsp+0C8h+pclsid]; pclsid
0x180068ac0  lea     rcx, [rsp+0C8h+ValueName]; lpsz
0x180068ac5  call    cs:__imp_CLSIDFromString
0x180068acc  nop     dword ptr [rax+rax+00h]
0x180068ad1  test    eax, eax
0x180068ad3  js      short loc_180068B01
0x180068ad5  mov     ecx, 18h; Size
0x180068ada  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180068adf  test    rax, rax
0x180068ae2  jz      short loc_180068B0C
0x180068ae4  mov     qword ptr [rax], 0
0x180068aeb  movups  xmm0, xmmword ptr [rsp+0C8h+pclsid.Data1]
0x180068af0  movdqu  xmmword ptr [rax+8], xmm0
0x180068af5  mov     rcx, [rbx]
0x180068af8  mov     [rax], rcx
0x180068afb  inc     dword ptr [rbx+0Ch]
0x180068afe  mov     [rbx], rax
0x180068b01  inc     edi
0x180068b03  jmp     loc_180068A55
0x180068b08  xor     edi, edi
0x180068b0a  jmp     short loc_180068B11
0x180068b0c  mov     edi, 8007000Eh
0x180068b11  mov     rcx, [rsp+0C8h+hKey]; hKey
0x180068b16  call    cs:__imp_RegCloseKey
0x180068b1d  nop     dword ptr [rax+rax+00h]
0x180068b22  test    edi, edi
0x180068b24  js      short loc_180068B61
0x180068b26  mov     dword ptr [rbx+8], 1
0x180068b2d  mov     eax, edi
0x180068b2f  mov     rcx, [rsp+0C8h+var_18]
0x180068b37  xor     rcx, rsp; StackCookie
0x180068b3a  call    __security_check_cookie
0x180068b3f  mov     rbx, [rsp+0C8h+arg_8]
0x180068b47  add     rsp, 0C0h
0x180068b4e  pop     rdi
0x180068b4f  retn
0x180068b51  mov     rax, [rcx]
0x180068b54  mov     edx, 18h
0x180068b59  mov     [rbx], rax
0x180068b5c  call    ??3@YAXPEAXAEBUthrowing_tag@KsOpmLib@@@Z; operator delete(void *,KsOpmLib::throwing_tag const &)
0x180068b61  mov     rcx, [rbx]; Block
0x180068b64  test    rcx, rcx
0x180068b67  jnz     short loc_180068B51
0x180068b69  jmp     short loc_180068B2D
```
