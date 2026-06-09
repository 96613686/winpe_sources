# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18000d764`
- end: `0x18000dd61`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1533`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x18000d45c`
- `0x18000d764`

## callees

- `0x18000c0c8`
- `0x18000c78c`
- `0x18000c7fc`
- `0x18000c844`
- `0x18000c954`
- `0x18000c980`
- `0x18000ce28`
- `0x18000cf14`
- `0x18000d074`
- `0x18000d348`
- `0x18000d764`
- `0x18000ddbc`
- `0x18000de8c`
- `0x180018a80`
- `0x180018b10`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18000db7e`
- `msvcrt!wcsncpy_s` at `0x18000db7e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000da7f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000da7f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000d9bf`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18000d9bf`
- `KERNEL32!lstrcmpiW` at `0x18000d7d7`
- `KERNEL32!lstrcmpiW` at `0x18000d7ea`
- `KERNEL32!lstrcmpiW` at `0x18000d8ce`
- `KERNEL32!lstrcmpiW` at `0x18000d8fd`
- `KERNEL32!lstrcmpiW` at `0x18000d7d7`
- `KERNEL32!lstrcmpiW` at `0x18000d7ea`
- `KERNEL32!lstrcmpiW` at `0x18000d8ce`
- `KERNEL32!lstrcmpiW` at `0x18000d8fd`

## string_xrefs

- `0x18000d7dd`: `ForceRemove`
- `0x18000d8be`: `NoRemove`
- `0x18000d7cd`: `Delete`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        HKEY a3,
        int a4,
        int a5)
{
  int v5; // r15d
  unsigned __int16 *v7; // rdi
  ATL::CRegParser *i; // rsi
  int Token; // eax
  int v10; // r14d
  int v11; // ebx
  ATL::CRegParser *v12; // rcx
  int v13; // eax
  int v14; // r12d
  LSTATUS v15; // eax
  LSTATUS v16; // ebx
  __int64 v17; // rax
  unsigned int v18; // r14d
  int v19; // r15d
  errno_t v20; // eax
  int v21; // eax
  ATL::CRegParser *v22; // rcx
  __int64 v23; // rax
  int HasSubKeys; // r15d
  unsigned int v25; // r14d
  unsigned int v27; // ecx
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v30; // [rsp+60h] [rbp-A0h]
  __int64 v31; // [rsp+68h] [rbp-98h]
  HKEY v32[3]; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  wchar_t Destination[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ValueName[4096]; // [rsp+2B0h] [rbp+1B0h] BYREF

  memset(v32, 0, sizeof(v32));
  v5 = a4;
  v7 = a2;
  for ( i = this; ; this = i )
  {
    Token = ATL::CRegParser::NextToken(this, a2);
LABEL_31:
    v11 = Token;
    if ( Token < 0 )
      break;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( *v7 == 125 )
          goto LABEL_79;
        v10 = lstrcmpiW(v7, L"Delete");
        if ( !lstrcmpiW(v7, L"ForceRemove") || !v10 )
        {
          v11 = ATL::CRegParser::NextToken(i, v7);
          if ( v11 < 0 )
            goto LABEL_79;
          if ( v5 )
          {
            hKey = 0;
            v30 = 0;
            v31 = 0;
            if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
            {
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_78:
              v11 = -2147352567;
              goto LABEL_79;
            }
            if ( ATL::CRegParser::CanForceRemoveKey(v12, v7) )
            {
              hKey = a3;
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&hKey, v7);
              hKey = 0;
            }
            if ( !v10 )
            {
              v11 = ATL::CRegParser::NextToken(i, v7);
              if ( v11 < 0 )
                goto LABEL_81;
              v13 = ATL::CRegParser::SkipAssignment(i, v7);
LABEL_14:
              v11 = v13;
              if ( v13 < 0 )
                goto LABEL_81;
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
              goto LABEL_42;
            }
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
          }
        }
        v14 = 1;
        if ( !lstrcmpiW(v7, L"NoRemove") )
        {
          v14 = 0;
          v11 = ATL::CRegParser::NextToken(i, v7);
          if ( v11 < 0 )
            goto LABEL_79;
        }
        if ( !lstrcmpiW(v7, L"Val") )
        {
          v11 = ATL::CRegParser::NextToken(i, ValueName);
          if ( v11 < 0 )
            goto LABEL_79;
          v11 = ATL::CRegParser::NextToken(i, v7);
          if ( v11 < 0 )
            goto LABEL_79;
          if ( *v7 != 61 )
            goto LABEL_78;
          if ( !v5 )
          {
            if ( a5 || !v14 )
              goto LABEL_30;
            hKey = 0;
            v30 = 0;
            v31 = 0;
            v15 = ATL::CRegKey::Open((ATL::CRegKey *)&hKey, a3, 0, 0x20006u);
            if ( !v15 )
            {
              v15 = RegDeleteValueW(hKey, ValueName);
              if ( (v15 & 0xFFFFFFFD) == 0 )
              {
                ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_30:
                Token = ATL::CRegParser::SkipAssignment(i, v7);
                goto LABEL_31;
              }
            }
LABEL_80:
            v11 = ATL::AtlHresultFromWin32(v15);
LABEL_81:
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            goto LABEL_79;
          }
          v30 = 0;
          v31 = 0;
          hKey = a3;
          v13 = ATL::CRegParser::AddValue(i, &hKey, ValueName, v7);
          hKey = 0;
          goto LABEL_14;
        }
        if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
          goto LABEL_78;
        if ( v5 )
          break;
        if ( a5 )
          v18 = 2;
        else
          v18 = ATL::CRegKey::Open((ATL::CRegKey *)v32, a3, v7, 0x20019u);
        v19 = 1;
        if ( !v18 )
          v19 = a5;
        v20 = wcsncpy_s(Destination, 0x104u, v7, 0xFFFFFFFFFFFFFFFFuLL);
        ATL::AtlCrtErrorCheck(v20);
        v11 = ATL::CRegParser::NextToken(i, v7);
        if ( v11 < 0 )
          goto LABEL_79;
        v21 = ATL::CRegParser::SkipAssignment(i, v7);
        v22 = 0;
        v11 = v21;
        if ( v21 < 0 )
          goto LABEL_79;
        if ( *v7 == 123 )
        {
          v23 = -1;
          do
            ++v23;
          while ( v7[v23] );
          if ( v23 == 1 )
          {
            v11 = ATL::CRegParser::RegisterSubkeys(i, v7, v32[0], 0, v19);
            if ( v11 < 0 && !v19 )
              goto LABEL_79;
            v11 = ATL::CRegParser::NextToken(i, v7);
            if ( v11 < 0 )
              goto LABEL_79;
          }
        }
        v5 = a4;
        if ( v18 != 2 )
        {
          if ( v18 )
          {
            if ( !a5 )
            {
              v11 = ATL::AtlHresultFromWin32(v18);
              goto LABEL_79;
            }
          }
          else if ( a5 && ATL::CRegParser::HasSubKeys(v22, v32[0]) )
          {
            if ( ATL::CRegParser::CanForceRemoveKey(v22, Destination) && v14 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v32, Destination);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v22, v32[0]);
            v25 = ATL::CRegKey::Close((ATL::CRegKey *)v32);
            if ( v25 )
            {
              ATL::CRegKey::Close((ATL::CRegKey *)v32);
              v27 = v25;
              return ATL::AtlHresultFromWin32(v27);
            }
            if ( v14 && !HasSubKeys )
            {
              v30 = 0;
              v31 = 0;
              hKey = a3;
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, Destination);
              hKey = 0;
              if ( v15 )
                goto LABEL_80;
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            }
            v5 = a4;
          }
        }
      }
      if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v32, a3, v7, 0x2001Fu) )
      {
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v32, a3, v7, 0x20019u) )
        {
          dwDisposition = 0;
          phkResult = 0;
          v16 = RegCreateKeyExW(a3, v7, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
          if ( v16 || (v16 = ATL::CRegKey::Close((ATL::CRegKey *)v32), v32[0] = phkResult, v16) )
          {
            ATL::CRegKey::Close((ATL::CRegKey *)v32);
            v27 = v16;
            return ATL::AtlHresultFromWin32(v27);
          }
        }
      }
      v11 = ATL::CRegParser::NextToken(i, v7);
      if ( v11 < 0 )
        goto LABEL_79;
      if ( *v7 == 61 )
      {
        v11 = ATL::CRegParser::AddValue(i, v32, 0, v7);
        if ( v11 < 0 )
          goto LABEL_79;
      }
LABEL_42:
      if ( *v7 == 123 )
      {
        v17 = -1;
        do
          ++v17;
        while ( v7[v17] );
        if ( v17 == 1 )
          break;
      }
    }
    v11 = ATL::CRegParser::RegisterSubkeys(i, v7, v32[0], v5, 0);
    if ( v11 < 0 )
      break;
    a2 = v7;
  }
LABEL_79:
  ATL::CRegKey::Close((ATL::CRegKey *)v32);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000d764  push    rbp
0x18000d766  push    rbx
0x18000d767  push    rsi
0x18000d768  push    rdi
0x18000d769  push    r12
0x18000d76b  push    r13
0x18000d76d  push    r14
0x18000d76f  push    r15
0x18000d771  lea     rbp, [rsp-21C8h]
0x18000d779  mov     eax, 22C8h
0x18000d77e  call    _alloca_probe
0x18000d783  sub     rsp, rax
0x18000d786  mov     rax, cs:__security_cookie
0x18000d78d  xor     rax, rsp
0x18000d790  mov     [rbp+2200h+var_50], rax
0x18000d797  xor     r14d, r14d
0x18000d79a  mov     [rsp+2300h+var_22B0], r9d
0x18000d79f  mov     [rsp+2300h+var_2290], r14
0x18000d7a4  mov     r15d, r9d
0x18000d7a7  mov     [rsp+2300h+var_2288], r14
0x18000d7ac  mov     r13, r8
0x18000d7af  mov     [rbp+2200h+var_2280], r14
0x18000d7b3  mov     rdi, rdx
0x18000d7b6  mov     rsi, rcx
0x18000d7b9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000d7be  jmp     loc_18000D9E5
0x18000d7c3  cmp     word ptr [rdi], 7Dh ; '}'
0x18000d7c7  jz      loc_18000DCFB
0x18000d7cd  lea     rdx, aDelete; "Delete"
0x18000d7d4  mov     rcx, rdi; lpString1
0x18000d7d7  call    cs:__imp_lstrcmpiW
0x18000d7dd  lea     rdx, aForceremove; "ForceRemove"
0x18000d7e4  mov     rcx, rdi; lpString1
0x18000d7e7  mov     r14d, eax
0x18000d7ea  call    cs:__imp_lstrcmpiW
0x18000d7f0  test    eax, eax
0x18000d7f2  jz      short loc_18000D7FD
0x18000d7f4  test    r14d, r14d
0x18000d7f7  jnz     loc_18000D8BE
0x18000d7fd  mov     rdx, rdi; unsigned __int16 *
0x18000d800  mov     rcx, rsi; this
0x18000d803  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000d808  mov     ebx, eax
0x18000d80a  test    eax, eax
0x18000d80c  js      loc_18000DCFB
0x18000d812  test    r15d, r15d
0x18000d815  jz      loc_18000D8BE
0x18000d81b  mov     edx, 5Ch ; '\'; unsigned __int16
0x18000d820  mov     [rsp+2300h+hKey], 0
0x18000d829  mov     rcx, rdi; lpsz
0x18000d82c  mov     [rsp+2300h+var_22A0], 0
0x18000d835  mov     [rsp+2300h+var_2298], 0
0x18000d83e  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18000d843  test    rax, rax
0x18000d846  jnz     loc_18000DCEC
0x18000d84c  mov     rdx, rdi; unsigned __int16 *
0x18000d84f  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x18000d854  test    eax, eax
0x18000d856  jz      short loc_18000D873
0x18000d858  mov     rdx, rdi; unsigned __int16 *
0x18000d85b  mov     [rsp+2300h+hKey], r13
0x18000d860  lea     rcx, [rsp+2300h+hKey]; this
0x18000d865  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000d86a  mov     [rsp+2300h+hKey], 0
0x18000d873  test    r14d, r14d
0x18000d876  jnz     short loc_18000D8B4
0x18000d878  mov     rdx, rdi; unsigned __int16 *
0x18000d87b  mov     rcx, rsi; this
0x18000d87e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000d883  xor     r14d, r14d
0x18000d886  mov     ebx, eax
0x18000d888  test    eax, eax
0x18000d88a  js      loc_18000DD33
0x18000d890  mov     rdx, rdi; unsigned __int16 *
0x18000d893  mov     rcx, rsi; this
0x18000d896  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000d89b  lea     rcx, [rsp+2300h+hKey]; this
0x18000d8a0  mov     ebx, eax
0x18000d8a2  test    eax, eax
0x18000d8a4  js      loc_18000DD38
0x18000d8aa  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000d8af  jmp     loc_18000DAE4
0x18000d8b4  lea     rcx, [rsp+2300h+hKey]; this
0x18000d8b9  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000d8be  lea     rdx, aNoremove; "NoRemove"
0x18000d8c5  mov     rcx, rdi; lpString1
0x18000d8c8  mov     r12d, 1
0x18000d8ce  call    cs:__imp_lstrcmpiW
0x18000d8d4  xor     r14d, r14d
0x18000d8d7  test    eax, eax
0x18000d8d9  jnz     short loc_18000D8F3
0x18000d8db  mov     rdx, rdi; unsigned __int16 *
0x18000d8de  mov     rcx, rsi; this
0x18000d8e1  mov     r12d, r14d
0x18000d8e4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000d8e9  mov     ebx, eax
0x18000d8eb  test    eax, eax
0x18000d8ed  js      loc_18000DCFB
0x18000d8f3  lea     rdx, aVal; "Val"
0x18000d8fa  mov     rcx, rdi; lpString1
0x18000d8fd  call    cs:__imp_lstrcmpiW
0x18000d903  test    eax, eax
0x18000d905  jnz     loc_18000D9F4
0x18000d90b  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x18000d912  mov     rcx, rsi; this
0x18000d915  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000d91a  mov     ebx, eax
0x18000d91c  test    eax, eax
0x18000d91e  js      loc_18000DCFB
0x18000d924  mov     rdx, rdi; unsigned __int16 *
0x18000d927  mov     rcx, rsi; this
0x18000d92a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000d92f  mov     ebx, eax
0x18000d931  test    eax, eax
0x18000d933  js      loc_18000DCFB
0x18000d939  cmp     word ptr [rdi], 3Dh ; '='
0x18000d93d  jnz     loc_18000DCF6
0x18000d943  test    r15d, r15d
0x18000d946  jz      short loc_18000D978
0x18000d948  mov     r9, rdi; unsigned __int16 *
0x18000d94b  mov     [rsp+2300h+var_22A0], r14
0x18000d950  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x18000d957  mov     [rsp+2300h+var_2298], r14
0x18000d95c  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x18000d961  mov     [rsp+2300h+hKey], r13
0x18000d966  mov     rcx, rsi; this
0x18000d969  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18000d96e  mov     [rsp+2300h+hKey], r14
0x18000d973  jmp     loc_18000D89B
0x18000d978  cmp     [rbp+2200h+arg_20], r14d
0x18000d97f  jnz     short loc_18000D9DA
0x18000d981  test    r12d, r12d
0x18000d984  jz      short loc_18000D9DA
0x18000d986  mov     r9d, 20006h; unsigned int
0x18000d98c  mov     [rsp+2300h+hKey], r14
0x18000d991  xor     r8d, r8d; lpSubKey
0x18000d994  mov     [rsp+2300h+var_22A0], r14
0x18000d999  mov     rdx, r13; hKey
0x18000d99c  mov     [rsp+2300h+var_2298], r14
0x18000d9a1  lea     rcx, [rsp+2300h+hKey]; this
0x18000d9a6  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000d9ab  test    eax, eax
0x18000d9ad  jnz     loc_18000DD2A
0x18000d9b3  mov     rcx, [rsp+2300h+hKey]; hKey
0x18000d9b8  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x18000d9bf  call    cs:__imp_RegDeleteValueW
0x18000d9c5  test    eax, 0FFFFFFFDh
0x18000d9ca  jnz     loc_18000DD2A
0x18000d9d0  lea     rcx, [rsp+2300h+hKey]; this
0x18000d9d5  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000d9da  mov     rdx, rdi; unsigned __int16 *
0x18000d9dd  mov     rcx, rsi; this
0x18000d9e0  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000d9e5  mov     ebx, eax
0x18000d9e7  test    eax, eax
0x18000d9e9  jns     loc_18000D7C3
0x18000d9ef  jmp     loc_18000DCFB
0x18000d9f4  mov     edx, 5Ch ; '\'; unsigned __int16
0x18000d9f9  mov     rcx, rdi; lpsz
0x18000d9fc  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18000da01  test    rax, rax
0x18000da04  jnz     loc_18000DCF6
0x18000da0a  test    r15d, r15d
0x18000da0d  jz      loc_18000DB33
0x18000da13  mov     r9d, 2001Fh; unsigned int
0x18000da19  lea     rcx, [rsp+2300h+var_2290]; this
0x18000da1e  mov     r8, rdi; lpSubKey
0x18000da21  mov     rdx, r13; hKey
0x18000da24  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000da29  test    eax, eax
0x18000da2b  jz      short loc_18000DAAC
0x18000da2d  mov     r9d, 20019h; unsigned int
0x18000da33  lea     rcx, [rsp+2300h+var_2290]; this
0x18000da38  mov     r8, rdi; lpSubKey
0x18000da3b  mov     rdx, r13; hKey
0x18000da3e  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000da43  test    eax, eax
0x18000da45  jz      short loc_18000DAAC
0x18000da47  lea     rax, [rbp+2200h+dwDisposition]
0x18000da4b  mov     [rbp+2200h+dwDisposition], r14d
0x18000da4f  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x18000da54  xor     r9d, r9d; lpClass
0x18000da57  lea     rax, [rbp+2200h+var_2270]
0x18000da5b  mov     [rbp+2200h+var_2270], r14
0x18000da5f  mov     [rsp+2300h+phkResult], rax; phkResult
0x18000da64  xor     r8d, r8d; Reserved
0x18000da67  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18000da6c  mov     rdx, rdi; lpSubKey
0x18000da6f  mov     [rsp+2300h+samDesired], 2001Fh; samDesired
0x18000da77  mov     rcx, r13; hKey
0x18000da7a  mov     [rsp+2300h+dwOptions], r14d; dwOptions
0x18000da7f  call    cs:__imp_RegCreateKeyExW
0x18000da85  mov     ebx, eax
0x18000da87  test    eax, eax
0x18000da89  jnz     loc_18000DD3F
0x18000da8f  lea     rcx, [rsp+2300h+var_2290]; this
0x18000da94  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000da99  mov     ebx, eax
0x18000da9b  mov     rax, [rbp+2200h+var_2270]
0x18000da9f  mov     [rsp+2300h+var_2290], rax
0x18000daa4  test    ebx, ebx
0x18000daa6  jnz     loc_18000DD3F
0x18000daac  mov     rdx, rdi; unsigned __int16 *
0x18000daaf  mov     rcx, rsi; this
0x18000dab2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000dab7  mov     ebx, eax
0x18000dab9  test    eax, eax
0x18000dabb  js      loc_18000DCFB
0x18000dac1  cmp     word ptr [rdi], 3Dh ; '='
0x18000dac5  jnz     short loc_18000DAE4
0x18000dac7  mov     r9, rdi; unsigned __int16 *
0x18000daca  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x18000dacf  xor     r8d, r8d; unsigned __int16 *
0x18000dad2  mov     rcx, rsi; this
0x18000dad5  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18000dada  mov     ebx, eax
0x18000dadc  test    eax, eax
0x18000dade  js      loc_18000DCFB
0x18000dae4  cmp     word ptr [rdi], 7Bh ; '{'
0x18000dae8  jnz     loc_18000D7C3
0x18000daee  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000daf2  inc     rax
0x18000daf5  cmp     [rdi+rax*2], r14w
0x18000dafa  jnz     short loc_18000DAF2
0x18000dafc  cmp     rax, 1
0x18000db00  jnz     loc_18000D7C3
0x18000db06  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18000db0b  mov     r9d, r15d; int
0x18000db0e  mov     rdx, rdi; unsigned __int16 *
0x18000db11  mov     [rsp+2300h+dwOptions], r14d; int
0x18000db16  mov     rcx, rsi; this
0x18000db19  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000db1e  mov     ebx, eax
0x18000db20  test    eax, eax
0x18000db22  js      loc_18000DCFB
0x18000db28  mov     rdx, rdi
0x18000db2b  mov     rcx, rsi
0x18000db2e  jmp     loc_18000D7B9
0x18000db33  cmp     [rbp+2200h+arg_20], r14d
0x18000db3a  jnz     short loc_18000DB57
0x18000db3c  mov     r9d, 20019h; unsigned int
0x18000db42  lea     rcx, [rsp+2300h+var_2290]; this
0x18000db47  mov     r8, rdi; lpSubKey
0x18000db4a  mov     rdx, r13; hKey
0x18000db4d  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000db52  mov     r14d, eax
0x18000db55  jmp     short loc_18000DB5D
0x18000db57  mov     r14d, 2
0x18000db5d  test    r14d, r14d
0x18000db60  lea     rcx, [rbp+2200h+Destination]; Destination
0x18000db64  mov     r15d, 1
0x18000db6a  mov     r8, rdi; Source
0x18000db6d  cmovz   r15d, [rbp+2200h+arg_20]
0x18000db75  mov     edx, 104h; SizeInWords
0x18000db7a  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18000db7e  call    cs:__imp_wcsncpy_s
0x18000db84  mov     ecx, eax; int
0x18000db86  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000db8b  mov     rdx, rdi; unsigned __int16 *
0x18000db8e  mov     rcx, rsi; this
0x18000db91  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000db96  mov     ebx, eax
0x18000db98  test    eax, eax
0x18000db9a  js      loc_18000DCFB
0x18000dba0  mov     rdx, rdi; unsigned __int16 *
0x18000dba3  mov     rcx, rsi; this
0x18000dba6  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000dbab  xor     ecx, ecx
0x18000dbad  mov     ebx, eax
0x18000dbaf  test    eax, eax
0x18000dbb1  js      loc_18000DCFB
0x18000dbb7  cmp     word ptr [rdi], 7Bh ; '{'
0x18000dbbb  jnz     short loc_18000DC0C
0x18000dbbd  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000dbc1  inc     rax
0x18000dbc4  cmp     [rdi+rax*2], cx
0x18000dbc8  jnz     short loc_18000DBC1
0x18000dbca  cmp     rax, 1
0x18000dbce  jnz     short loc_18000DC0C
0x18000dbd0  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18000dbd5  xor     r9d, r9d; int
0x18000dbd8  mov     rdx, rdi; unsigned __int16 *
0x18000dbdb  mov     [rsp+2300h+dwOptions], r15d; int
0x18000dbe0  mov     rcx, rsi; this
0x18000dbe3  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000dbe8  mov     ebx, eax
0x18000dbea  test    eax, eax
0x18000dbec  jns     short loc_18000DBF7
0x18000dbee  test    r15d, r15d
0x18000dbf1  jz      loc_18000DCFB
0x18000dbf7  mov     rdx, rdi; unsigned __int16 *
0x18000dbfa  mov     rcx, rsi; this
0x18000dbfd  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000dc02  mov     ebx, eax
0x18000dc04  test    eax, eax
0x18000dc06  js      loc_18000DCFB
0x18000dc0c  mov     r15d, [rsp+2300h+var_22B0]
0x18000dc11  cmp     r14d, 2
0x18000dc15  jz      loc_18000D7C3
0x18000dc1b  test    r14d, r14d
  ... truncated ...
```
