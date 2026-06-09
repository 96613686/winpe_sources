# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x1800493b8`
- end: `0x180049988`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1488`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, registry_config`

## callers

- `0x180048e9c`
- `0x1800493b8`

## callees

- `0x1800476dc`
- `0x180047d44`
- `0x180048074`
- `0x180048214`
- `0x1800483ac`
- `0x180048728`
- `0x180048910`
- `0x180048a7c`
- `0x180048d88`
- `0x1800493b8`
- `0x180049b74`
- `0x180049c44`
- `0x180067b30`
- `0x180067bf0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x1800497bc`
- `msvcrt!wcsncpy_s` at `0x1800497bc`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004960b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004960b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800496bd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800496bd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180049433`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180049446`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18004951a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180049549`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180049433`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180049446`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18004951a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180049549`

## string_xrefs

- `0x18004943c`: `ForceRemove`
- `0x180049510`: `NoRemove`
- `0x180049429`: `Delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        HKEY a3,
        int a4,
        int a5)
{
  int v5; // r15d
  unsigned __int16 *v7; // rdi
  ATL::CRegParser *v8; // rsi
  int Token; // eax
  int v10; // ebx
  int v11; // r14d
  ATL::CRegParser *v12; // rcx
  int v13; // eax
  int v14; // r12d
  LSTATUS v15; // eax
  LSTATUS v16; // ecx
  __int64 v17; // rax
  int v18; // r14d
  int v19; // r15d
  ATL::CRegParser *v20; // rcx
  __int64 v21; // rax
  int HasSubKeys; // r14d
  LSTATUS v23; // eax
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v27; // [rsp+60h] [rbp-A0h]
  __int64 v28; // [rsp+68h] [rbp-98h]
  HKEY v29[3]; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  wchar_t Destination[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ValueName[4096]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v5 = a4;
  v7 = a2;
  v8 = this;
  memset(v29, 0, sizeof(v29));
LABEL_2:
  Token = ATL::CRegParser::NextToken(this, a2);
  while ( 2 )
  {
    v10 = Token;
    if ( Token < 0 )
      goto LABEL_79;
    while ( 1 )
    {
      if ( *v7 == 125 )
        goto LABEL_79;
      v11 = lstrcmpiW(v7, L"Delete");
      if ( !lstrcmpiW(v7, L"ForceRemove") || !v11 )
      {
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        if ( v5 )
        {
          hKey = 0;
          v27 = 0;
          v28 = 0;
          if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
          {
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_78:
            v10 = -2147352567;
            goto LABEL_79;
          }
          if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v12, v7) )
          {
            hKey = a3;
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&hKey, v7);
            hKey = 0;
          }
          if ( !v11 )
          {
            v10 = ATL::CRegParser::NextToken(v8, v7);
            if ( v10 < 0 )
              goto LABEL_81;
            v13 = ATL::CRegParser::SkipAssignment(v8, v7);
            goto LABEL_15;
          }
          ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
        }
      }
      v14 = 1;
      if ( !lstrcmpiW(v7, L"NoRemove") )
      {
        v14 = 0;
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
      }
      if ( !lstrcmpiW(v7, L"Val") )
        break;
      if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        goto LABEL_78;
      if ( v5 )
      {
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v29, a3, v7, 0x2001Fu) )
        {
          if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v29, a3, v7, 0x20019u) )
          {
            dwDisposition = 0;
            phkResult = 0;
            v16 = RegCreateKeyExW(a3, v7, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
            if ( v16 )
              goto LABEL_65;
            v16 = ATL::CRegKey::Close((ATL::CRegKey *)v29);
            v29[0] = phkResult;
            if ( v16 )
              goto LABEL_65;
          }
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        if ( *v7 == 61 )
        {
          v10 = ATL::CRegParser::AddValue(v8, v29, 0, v7);
          if ( v10 < 0 )
            goto LABEL_79;
        }
LABEL_41:
        if ( *v7 == 123 )
        {
          v17 = -1;
          do
            ++v17;
          while ( v7[v17] );
          if ( v17 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v29[0], v5, 0);
            if ( v10 < 0 )
              goto LABEL_79;
            a2 = v7;
            this = v8;
            goto LABEL_2;
          }
        }
      }
      else
      {
        if ( a5 )
          v18 = 2;
        else
          v18 = ATL::CRegKey::Open((ATL::CRegKey *)v29, a3, v7, 0x20019u);
        v19 = 1;
        if ( !v18 )
          v19 = a5;
        wcsncpy_s(Destination, 0x104u, v7, 0xFFFFFFFFFFFFFFFFuLL);
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        v10 = ATL::CRegParser::SkipAssignment(v8, v7);
        v20 = 0;
        if ( v10 < 0 )
          goto LABEL_79;
        if ( *v7 == 123 )
        {
          v21 = -1;
          do
            ++v21;
          while ( v7[v21] );
          if ( v21 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v29[0], 0, v19);
            if ( v10 < 0 && !v19 )
              goto LABEL_79;
            v10 = ATL::CRegParser::NextToken(v8, v7);
            if ( v10 < 0 )
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
              v16 = v18;
LABEL_65:
              v10 = ATL::AtlHresultFromWin32(v16);
              goto LABEL_79;
            }
          }
          else if ( a5 && ATL::CRegParser::HasSubKeys(v20, v29[0]) )
          {
            if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v20, Destination) && v14 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v29, Destination);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v20, v29[0]);
            v23 = ATL::CRegKey::Close((ATL::CRegKey *)v29);
            if ( v23 )
            {
              v16 = v23;
              goto LABEL_65;
            }
            if ( v14 && !HasSubKeys )
            {
              v27 = 0;
              v28 = 0;
              hKey = a3;
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, Destination);
              hKey = 0;
              if ( v15 )
                goto LABEL_80;
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            }
          }
        }
      }
    }
    v10 = ATL::CRegParser::NextToken(v8, ValueName);
    if ( v10 < 0 )
      goto LABEL_79;
    v10 = ATL::CRegParser::NextToken(v8, v7);
    if ( v10 < 0 )
      goto LABEL_79;
    if ( *v7 != 61 )
      goto LABEL_78;
    if ( v5 )
    {
      v27 = 0;
      v28 = 0;
      hKey = a3;
      v13 = ATL::CRegParser::AddValue(v8, &hKey, ValueName, v7);
      hKey = 0;
LABEL_15:
      v10 = v13;
      if ( v13 < 0 )
        goto LABEL_81;
      ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
      goto LABEL_41;
    }
    if ( a5 || !v14 )
      goto LABEL_31;
    hKey = 0;
    v27 = 0;
    v28 = 0;
    v15 = ATL::CRegKey::Open((ATL::CRegKey *)&hKey, a3, 0, 0x20006u);
    if ( !v15 )
    {
      v15 = RegDeleteValueW(hKey, ValueName);
      if ( (v15 & 0xFFFFFFFD) == 0 )
      {
        ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_31:
        Token = ATL::CRegParser::SkipAssignment(v8, v7);
        continue;
      }
    }
    break;
  }
LABEL_80:
  v10 = ATL::AtlHresultFromWin32(v15);
LABEL_81:
  ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_79:
  ATL::CRegKey::Close((ATL::CRegKey *)v29);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800493b8  push    rbp
0x1800493ba  push    rbx
0x1800493bb  push    rsi
0x1800493bc  push    rdi
0x1800493bd  push    r12
0x1800493bf  push    r13
0x1800493c1  push    r14
0x1800493c3  push    r15
0x1800493c5  lea     rbp, [rsp-21C8h]
0x1800493cd  mov     eax, 22C8h
0x1800493d2  call    _alloca_probe
0x1800493d7  sub     rsp, rax
0x1800493da  mov     rax, cs:__security_cookie
0x1800493e1  xor     rax, rsp
0x1800493e4  mov     [rbp+2200h+var_50], rax
0x1800493eb  mov     r15d, r9d
0x1800493ee  mov     [rsp+2300h+var_22B0], r9d
0x1800493f3  mov     r13, r8
0x1800493f6  mov     rdi, rdx
0x1800493f9  mov     rsi, rcx
0x1800493fc  xor     r14d, r14d
0x1800493ff  mov     [rsp+2300h+var_2290], r14
0x180049404  mov     [rsp+2300h+var_2288], r14
0x180049409  mov     [rbp+2200h+var_2280], r14
0x18004940d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180049412  test    eax, eax
0x180049414  mov     ebx, eax
0x180049416  js      loc_18004993C
0x18004941c  xor     r12d, r12d
0x18004941f  cmp     word ptr [rdi], 7Dh ; '}'
0x180049423  jz      loc_18004993C
0x180049429  lea     rdx, aDelete; "Delete"
0x180049430  mov     rcx, rdi; lpString1
0x180049433  call    cs:__imp_lstrcmpiW
0x180049439  mov     r14d, eax
0x18004943c  lea     rdx, aForceremove; "ForceRemove"
0x180049443  mov     rcx, rdi; lpString1
0x180049446  call    cs:__imp_lstrcmpiW
0x18004944c  test    eax, eax
0x18004944e  jz      short loc_180049459
0x180049450  test    r14d, r14d
0x180049453  jnz     loc_18004950A
0x180049459  mov     rdx, rdi; unsigned __int16 *
0x18004945c  mov     rcx, rsi; this
0x18004945f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180049464  mov     ebx, eax
0x180049466  test    eax, eax
0x180049468  js      loc_18004993C
0x18004946e  test    r15d, r15d
0x180049471  jz      loc_18004950A
0x180049477  mov     [rsp+2300h+hKey], r12
0x18004947c  mov     [rsp+2300h+var_22A0], r12
0x180049481  mov     [rsp+2300h+var_2298], r12
0x180049486  mov     edx, 5Ch ; '\'; unsigned __int16
0x18004948b  mov     rcx, rdi; lpsz
0x18004948e  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180049493  test    rax, rax
0x180049496  jnz     loc_18004992D
0x18004949c  mov     rdx, rdi; unsigned __int16 *
0x18004949f  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x1800494a4  test    eax, eax
0x1800494a6  jz      short loc_1800494BF
0x1800494a8  mov     [rsp+2300h+hKey], r13
0x1800494ad  mov     rdx, rdi; unsigned __int16 *
0x1800494b0  lea     rcx, [rsp+2300h+hKey]; this
0x1800494b5  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1800494ba  mov     [rsp+2300h+hKey], r12
0x1800494bf  test    r14d, r14d
0x1800494c2  jnz     short loc_180049500
0x1800494c4  mov     rdx, rdi; unsigned __int16 *
0x1800494c7  mov     rcx, rsi; this
0x1800494ca  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800494cf  mov     ebx, eax
0x1800494d1  xor     r14d, r14d
0x1800494d4  test    eax, eax
0x1800494d6  js      loc_180049974
0x1800494dc  mov     rdx, rdi; unsigned __int16 *
0x1800494df  mov     rcx, rsi; this
0x1800494e2  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800494e7  test    eax, eax
0x1800494e9  lea     rcx, [rsp+2300h+hKey]; this
0x1800494ee  mov     ebx, eax
0x1800494f0  js      loc_180049979
0x1800494f6  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800494fb  jmp     loc_180049722
0x180049500  lea     rcx, [rsp+2300h+hKey]; this
0x180049505  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18004950a  mov     r12d, 1
0x180049510  lea     rdx, aNoremove; "NoRemove"
0x180049517  mov     rcx, rdi; lpString1
0x18004951a  call    cs:__imp_lstrcmpiW
0x180049520  xor     r14d, r14d
0x180049523  test    eax, eax
0x180049525  jnz     short loc_18004953F
0x180049527  mov     r12d, r14d
0x18004952a  mov     rdx, rdi; unsigned __int16 *
0x18004952d  mov     rcx, rsi; this
0x180049530  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180049535  mov     ebx, eax
0x180049537  test    eax, eax
0x180049539  js      loc_18004993C
0x18004953f  lea     rdx, aVal; "Val"
0x180049546  mov     rcx, rdi; lpString1
0x180049549  call    cs:__imp_lstrcmpiW
0x18004954f  test    eax, eax
0x180049551  jnz     loc_180049636
0x180049557  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x18004955e  mov     rcx, rsi; this
0x180049561  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180049566  mov     ebx, eax
0x180049568  test    eax, eax
0x18004956a  js      loc_18004993C
0x180049570  mov     rdx, rdi; unsigned __int16 *
0x180049573  mov     rcx, rsi; this
0x180049576  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18004957b  mov     ebx, eax
0x18004957d  test    eax, eax
0x18004957f  js      loc_18004993C
0x180049585  cmp     word ptr [rdi], 3Dh ; '='
0x180049589  jnz     loc_180049937
0x18004958f  test    r15d, r15d
0x180049592  jz      short loc_1800495C4
0x180049594  mov     [rsp+2300h+var_22A0], r14
0x180049599  mov     [rsp+2300h+var_2298], r14
0x18004959e  mov     [rsp+2300h+hKey], r13
0x1800495a3  mov     r9, rdi; unsigned __int16 *
0x1800495a6  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x1800495ad  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x1800495b2  mov     rcx, rsi; this
0x1800495b5  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1800495ba  mov     [rsp+2300h+hKey], r14
0x1800495bf  jmp     loc_1800494E7
0x1800495c4  cmp     [rbp+2200h+arg_20], r14d
0x1800495cb  jnz     short loc_180049626
0x1800495cd  test    r12d, r12d
0x1800495d0  jz      short loc_180049626
0x1800495d2  mov     [rsp+2300h+hKey], r14
0x1800495d7  mov     [rsp+2300h+var_22A0], r14
0x1800495dc  mov     [rsp+2300h+var_2298], r14
0x1800495e1  mov     r9d, 20006h; unsigned int
0x1800495e7  xor     r8d, r8d; lpSubKey
0x1800495ea  mov     rdx, r13; hKey
0x1800495ed  lea     rcx, [rsp+2300h+hKey]; this
0x1800495f2  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800495f7  test    eax, eax
0x1800495f9  jnz     loc_18004996B
0x1800495ff  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x180049606  mov     rcx, [rsp+2300h+hKey]; hKey
0x18004960b  call    cs:__imp_RegDeleteValueW
0x180049611  test    eax, 0FFFFFFFDh
0x180049616  jnz     loc_18004996B
0x18004961c  lea     rcx, [rsp+2300h+hKey]; this
0x180049621  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180049626  mov     rdx, rdi; unsigned __int16 *
0x180049629  mov     rcx, rsi; this
0x18004962c  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180049631  jmp     loc_180049412
0x180049636  mov     edx, 5Ch ; '\'; unsigned __int16
0x18004963b  mov     rcx, rdi; lpsz
0x18004963e  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180049643  test    rax, rax
0x180049646  jnz     loc_180049937
0x18004964c  test    r15d, r15d
0x18004964f  jz      loc_180049771
0x180049655  mov     ebx, 2001Fh
0x18004965a  mov     r9d, ebx; unsigned int
0x18004965d  mov     r8, rdi; lpSubKey
0x180049660  mov     rdx, r13; hKey
0x180049663  lea     rcx, [rsp+2300h+var_2290]; this
0x180049668  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18004966d  test    eax, eax
0x18004966f  jz      short loc_1800496EA
0x180049671  lea     r9d, [rbx-6]; unsigned int
0x180049675  mov     r8, rdi; lpSubKey
0x180049678  mov     rdx, r13; hKey
0x18004967b  lea     rcx, [rsp+2300h+var_2290]; this
0x180049680  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180049685  test    eax, eax
0x180049687  jz      short loc_1800496EA
0x180049689  mov     [rbp+2200h+dwDisposition], r14d
0x18004968d  mov     [rbp+2200h+var_2270], r14
0x180049691  lea     rax, [rbp+2200h+dwDisposition]
0x180049695  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x18004969a  lea     rax, [rbp+2200h+var_2270]
0x18004969e  mov     [rsp+2300h+phkResult], rax; phkResult
0x1800496a3  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1800496a8  mov     [rsp+2300h+samDesired], ebx; samDesired
0x1800496ac  mov     [rsp+2300h+dwOptions], r14d; dwOptions
0x1800496b1  xor     r9d, r9d; lpClass
0x1800496b4  xor     r8d, r8d; Reserved
0x1800496b7  mov     rdx, rdi; lpSubKey
0x1800496ba  mov     rcx, r13; hKey
0x1800496bd  call    cs:__imp_RegCreateKeyExW
0x1800496c3  mov     ecx, eax
0x1800496c5  test    eax, eax
0x1800496c7  jnz     loc_18004986A
0x1800496cd  lea     rcx, [rsp+2300h+var_2290]; this
0x1800496d2  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800496d7  mov     ecx, eax
0x1800496d9  mov     rax, [rbp+2200h+var_2270]
0x1800496dd  mov     [rsp+2300h+var_2290], rax
0x1800496e2  test    ecx, ecx
0x1800496e4  jnz     loc_18004986A
0x1800496ea  mov     rdx, rdi; unsigned __int16 *
0x1800496ed  mov     rcx, rsi; this
0x1800496f0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800496f5  mov     ebx, eax
0x1800496f7  test    eax, eax
0x1800496f9  js      loc_18004993C
0x1800496ff  cmp     word ptr [rdi], 3Dh ; '='
0x180049703  jnz     short loc_180049722
0x180049705  mov     r9, rdi; unsigned __int16 *
0x180049708  xor     r8d, r8d; unsigned __int16 *
0x18004970b  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x180049710  mov     rcx, rsi; this
0x180049713  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180049718  mov     ebx, eax
0x18004971a  test    eax, eax
0x18004971c  js      loc_18004993C
0x180049722  cmp     word ptr [rdi], 7Bh ; '{'
0x180049726  jnz     loc_18004941C
0x18004972c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180049730  inc     rax
0x180049733  cmp     [rdi+rax*2], r14w
0x180049738  jnz     short loc_180049730
0x18004973a  cmp     rax, 1
0x18004973e  jnz     loc_18004941C
0x180049744  mov     [rsp+2300h+dwOptions], r14d; int
0x180049749  mov     r9d, r15d; int
0x18004974c  mov     r8, [rsp+2300h+var_2290]; HKEY
0x180049751  mov     rdx, rdi; unsigned __int16 *
0x180049754  mov     rcx, rsi; this
0x180049757  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18004975c  mov     ebx, eax
0x18004975e  test    eax, eax
0x180049760  js      loc_18004993C
0x180049766  mov     rdx, rdi
0x180049769  mov     rcx, rsi
0x18004976c  jmp     loc_18004940D
0x180049771  cmp     [rbp+2200h+arg_20], r14d
0x180049778  jnz     short loc_180049795
0x18004977a  mov     r9d, 20019h; unsigned int
0x180049780  mov     r8, rdi; lpSubKey
0x180049783  mov     rdx, r13; hKey
0x180049786  lea     rcx, [rsp+2300h+var_2290]; this
0x18004978b  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180049790  mov     r14d, eax
0x180049793  jmp     short loc_18004979B
0x180049795  mov     r14d, 2
0x18004979b  mov     r15d, 1
0x1800497a1  test    r14d, r14d
0x1800497a4  cmovz   r15d, [rbp+2200h+arg_20]
0x1800497ac  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800497b0  mov     r8, rdi; Source
0x1800497b3  mov     edx, 104h; SizeInWords
0x1800497b8  lea     rcx, [rbp+2200h+Destination]; Destination
0x1800497bc  call    cs:__imp_wcsncpy_s
0x1800497c2  mov     rdx, rdi; unsigned __int16 *
0x1800497c5  mov     rcx, rsi; this
0x1800497c8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800497cd  mov     ebx, eax
0x1800497cf  test    eax, eax
0x1800497d1  js      loc_18004993C
0x1800497d7  mov     rdx, rdi; unsigned __int16 *
0x1800497da  mov     rcx, rsi; this
0x1800497dd  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800497e2  mov     ebx, eax
0x1800497e4  xor     ecx, ecx
0x1800497e6  test    eax, eax
0x1800497e8  js      loc_18004993C
0x1800497ee  cmp     word ptr [rdi], 7Bh ; '{'
0x1800497f2  jnz     short loc_180049843
0x1800497f4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800497f8  inc     rax
0x1800497fb  cmp     [rdi+rax*2], cx
0x1800497ff  jnz     short loc_1800497F8
0x180049801  cmp     rax, 1
0x180049805  jnz     short loc_180049843
0x180049807  mov     [rsp+2300h+dwOptions], r15d; int
0x18004980c  xor     r9d, r9d; int
0x18004980f  mov     r8, [rsp+2300h+var_2290]; HKEY
0x180049814  mov     rdx, rdi; unsigned __int16 *
0x180049817  mov     rcx, rsi; this
0x18004981a  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18004981f  mov     ebx, eax
0x180049821  test    eax, eax
0x180049823  jns     short loc_18004982E
0x180049825  test    r15d, r15d
0x180049828  jz      loc_18004993C
0x18004982e  mov     rdx, rdi; unsigned __int16 *
0x180049831  mov     rcx, rsi; this
0x180049834  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180049839  mov     ebx, eax
0x18004983b  test    eax, eax
0x18004983d  js      loc_18004993C
0x180049843  cmp     r14d, 2
0x180049847  mov     r15d, [rsp+2300h+var_22B0]
0x18004984c  jz      loc_18004941C
0x180049852  test    r14d, r14d
0x180049855  jz      short loc_180049876
  ... truncated ...
```
