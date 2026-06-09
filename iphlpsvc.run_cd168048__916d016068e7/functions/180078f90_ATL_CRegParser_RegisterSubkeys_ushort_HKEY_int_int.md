# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180078f90`
- end: `0x180079591`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1537`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x180078c3c`
- `0x180078f90`

## callees

- `0x18004b630`
- `0x180077ac0`
- `0x180078114`
- `0x180078188`
- `0x1800781c0`
- `0x180078368`
- `0x18007839c`
- `0x1800785ac`
- `0x180078658`
- `0x1800787e8`
- `0x180078b1c`
- `0x180078f90`
- `0x180079610`
- `0x1800797f8`
- `0x180082000`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800793b7`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800793b7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800791fd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800791fd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800792b6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800792b6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18007900b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180079024`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800790fe`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180079133`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18007900b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180079024`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800790fe`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180079133`

## string_xrefs

- `0x18007901a`: `ForceRemove`
- `0x1800790f4`: `NoRemove`
- `0x180079001`: `Delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
  int v20; // eax
  ATL::CRegParser *v21; // rcx
  __int64 v22; // rax
  int HasSubKeys; // r14d
  LSTATUS v24; // eax
  __int64 dwOptions; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+60h] [rbp-A0h]
  __int64 v30; // [rsp+68h] [rbp-98h]
  HKEY v31[3]; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v34[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ValueName[4096]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v5 = a4;
  v7 = a2;
  v8 = this;
  memset(v31, 0, sizeof(v31));
LABEL_2:
  Token = ATL::CRegParser::NextToken(this, a2);
  while ( 2 )
  {
    v10 = Token;
    if ( Token < 0 )
      goto LABEL_80;
    while ( 1 )
    {
      if ( *v7 == 125 )
        goto LABEL_80;
      v11 = lstrcmpiW(v7, L"Delete");
      if ( !lstrcmpiW(v7, L"ForceRemove") || !v11 )
      {
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_80;
        if ( v5 )
        {
          hKey = 0;
          v29 = 0;
          v30 = 0;
          if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
          {
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_79:
            v10 = -2147352567;
            goto LABEL_80;
          }
          if ( ATL::CRegParser::CanForceRemoveKey(v12, v7) )
          {
            hKey = a3;
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&hKey, v7);
            hKey = 0;
          }
          if ( !v11 )
          {
            v10 = ATL::CRegParser::NextToken(v8, v7);
            if ( v10 < 0 )
              goto LABEL_82;
            v13 = ATL::CRegParser::SkipAssignment(v8, v7);
            v10 = v13;
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
          goto LABEL_80;
      }
      if ( !lstrcmpiW(v7, L"Val") )
        break;
      if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        goto LABEL_79;
      if ( v5 )
      {
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v31, a3, v7, 0x2001Fu)
          && (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v31, a3, v7, 0x20019u) )
        {
          dwDisposition = 0;
          phkResult = 0;
          v16 = RegCreateKeyExW(a3, v7, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
          if ( !v16 )
          {
            v16 = ATL::CRegKey::Close((ATL::CRegKey *)v31);
            v31[0] = phkResult;
          }
          if ( v16 )
            goto LABEL_66;
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_80;
        if ( *v7 == 61 )
        {
          v10 = ATL::CRegParser::AddValue(v8, v31, 0, v7);
          if ( v10 < 0 )
            goto LABEL_80;
        }
LABEL_42:
        if ( *v7 == 123 )
        {
          v17 = -1;
          do
            ++v17;
          while ( v7[v17] );
          if ( v17 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v31[0], v5, 0);
            if ( v10 < 0 )
              goto LABEL_80;
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
          v18 = ATL::CRegKey::Open((ATL::CRegKey *)v31, a3, v7, 0x20019u);
        v19 = 1;
        if ( !v18 )
          v19 = a5;
        v20 = _o_wcsncpy_s(v34, 260, v7, -1, dwOptions);
        ATL::AtlCrtErrorCheck(v20);
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_80;
        v10 = ATL::CRegParser::SkipAssignment(v8, v7);
        v21 = 0;
        if ( v10 < 0 )
          goto LABEL_80;
        if ( *v7 == 123 )
        {
          v22 = -1;
          do
            ++v22;
          while ( v7[v22] );
          if ( v22 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v31[0], 0, v19);
            if ( v10 < 0 && !v19 )
              goto LABEL_80;
            v10 = ATL::CRegParser::NextToken(v8, v7);
            if ( v10 < 0 )
              goto LABEL_80;
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
LABEL_66:
              v10 = ATL::AtlHresultFromWin32(v16);
              goto LABEL_80;
            }
          }
          else if ( a5 && ATL::CRegParser::HasSubKeys(v21, v31[0]) )
          {
            if ( ATL::CRegParser::CanForceRemoveKey(v21, v34) && v14 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v31, v34);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v21, v31[0]);
            v24 = ATL::CRegKey::Close((ATL::CRegKey *)v31);
            if ( v24 )
            {
              v16 = v24;
              goto LABEL_66;
            }
            if ( v14 && !HasSubKeys )
            {
              v29 = 0;
              v30 = 0;
              hKey = a3;
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, v34);
              hKey = 0;
              if ( v15 )
                goto LABEL_81;
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            }
          }
        }
      }
    }
    v10 = ATL::CRegParser::NextToken(v8, ValueName);
    if ( v10 < 0 )
      goto LABEL_80;
    v10 = ATL::CRegParser::NextToken(v8, v7);
    if ( v10 < 0 )
      goto LABEL_80;
    if ( *v7 != 61 )
      goto LABEL_79;
    if ( v5 )
    {
      v29 = 0;
      v30 = 0;
      hKey = a3;
      v13 = ATL::CRegParser::AddValue(v8, &hKey, ValueName, v7);
      v10 = v13;
      hKey = 0;
LABEL_15:
      if ( v13 < 0 )
        goto LABEL_82;
      ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
      goto LABEL_42;
    }
    if ( a5 || !v14 )
      goto LABEL_31;
    hKey = 0;
    v29 = 0;
    v30 = 0;
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
LABEL_81:
  v10 = ATL::AtlHresultFromWin32(v15);
LABEL_82:
  ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_80:
  ATL::CRegKey::Close((ATL::CRegKey *)v31);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180078f90  push    rbp
0x180078f92  push    rbx
0x180078f93  push    rsi
0x180078f94  push    rdi
0x180078f95  push    r12
0x180078f97  push    r13
0x180078f99  push    r14
0x180078f9b  push    r15
0x180078f9d  lea     rbp, [rsp-21C8h]
0x180078fa5  mov     eax, 22C8h
0x180078faa  call    _alloca_probe
0x180078faf  sub     rsp, rax
0x180078fb2  mov     rax, cs:__security_cookie
0x180078fb9  xor     rax, rsp
0x180078fbc  mov     [rbp+2200h+var_50], rax
0x180078fc3  mov     r15d, r9d
0x180078fc6  mov     [rsp+2300h+var_22B0], r9d
0x180078fcb  mov     r13, r8
0x180078fce  mov     rdi, rdx
0x180078fd1  mov     rsi, rcx
0x180078fd4  xor     r14d, r14d
0x180078fd7  mov     [rsp+2300h+var_2290], r14
0x180078fdc  mov     [rsp+2300h+var_2288], r14
0x180078fe1  mov     [rbp+2200h+var_2280], r14
0x180078fe5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180078fea  test    eax, eax
0x180078fec  mov     ebx, eax
0x180078fee  js      loc_180079544
0x180078ff4  xor     r12d, r12d
0x180078ff7  cmp     word ptr [rdi], 7Dh ; '}'
0x180078ffb  jz      loc_180079544
0x180079001  lea     rdx, aDelete; "Delete"
0x180079008  mov     rcx, rdi; lpString1
0x18007900b  call    cs:__imp_lstrcmpiW
0x180079012  nop     dword ptr [rax+rax+00h]
0x180079017  mov     r14d, eax
0x18007901a  lea     rdx, aForceremove; "ForceRemove"
0x180079021  mov     rcx, rdi; lpString1
0x180079024  call    cs:__imp_lstrcmpiW
0x18007902b  nop     dword ptr [rax+rax+00h]
0x180079030  test    eax, eax
0x180079032  jz      short loc_18007903D
0x180079034  test    r14d, r14d
0x180079037  jnz     loc_1800790EE
0x18007903d  mov     rdx, rdi; unsigned __int16 *
0x180079040  mov     rcx, rsi; this
0x180079043  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180079048  mov     ebx, eax
0x18007904a  test    eax, eax
0x18007904c  js      loc_180079544
0x180079052  test    r15d, r15d
0x180079055  jz      loc_1800790EE
0x18007905b  mov     [rsp+2300h+hKey], r12
0x180079060  mov     [rsp+2300h+var_22A0], r12
0x180079065  mov     [rsp+2300h+var_2298], r12
0x18007906a  mov     edx, 5Ch ; '\'; unsigned __int16
0x18007906f  mov     rcx, rdi; lpsz
0x180079072  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180079077  test    rax, rax
0x18007907a  jnz     loc_180079535
0x180079080  mov     rdx, rdi; unsigned __int16 *
0x180079083  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x180079088  test    eax, eax
0x18007908a  jz      short loc_1800790A3
0x18007908c  mov     [rsp+2300h+hKey], r13
0x180079091  mov     rdx, rdi; unsigned __int16 *
0x180079094  lea     rcx, [rsp+2300h+hKey]; this
0x180079099  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18007909e  mov     [rsp+2300h+hKey], r12
0x1800790a3  test    r14d, r14d
0x1800790a6  jnz     short loc_1800790E4
0x1800790a8  mov     rdx, rdi; unsigned __int16 *
0x1800790ab  mov     rcx, rsi; this
0x1800790ae  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800790b3  mov     ebx, eax
0x1800790b5  xor     r14d, r14d
0x1800790b8  test    eax, eax
0x1800790ba  js      loc_18007957D
0x1800790c0  mov     rdx, rdi; unsigned __int16 *
0x1800790c3  mov     rcx, rsi; this
0x1800790c6  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800790cb  mov     ebx, eax
0x1800790cd  test    eax, eax
0x1800790cf  lea     rcx, [rsp+2300h+hKey]; this
0x1800790d4  js      loc_180079582
0x1800790da  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800790df  jmp     loc_18007931D
0x1800790e4  lea     rcx, [rsp+2300h+hKey]; this
0x1800790e9  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800790ee  mov     r12d, 1
0x1800790f4  lea     rdx, aNoremove; "NoRemove"
0x1800790fb  mov     rcx, rdi; lpString1
0x1800790fe  call    cs:__imp_lstrcmpiW
0x180079105  nop     dword ptr [rax+rax+00h]
0x18007910a  xor     r14d, r14d
0x18007910d  test    eax, eax
0x18007910f  jnz     short loc_180079129
0x180079111  mov     r12d, r14d
0x180079114  mov     rdx, rdi; unsigned __int16 *
0x180079117  mov     rcx, rsi; this
0x18007911a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18007911f  mov     ebx, eax
0x180079121  test    eax, eax
0x180079123  js      loc_180079544
0x180079129  lea     rdx, aVal; "Val"
0x180079130  mov     rcx, rdi; lpString1
0x180079133  call    cs:__imp_lstrcmpiW
0x18007913a  nop     dword ptr [rax+rax+00h]
0x18007913f  test    eax, eax
0x180079141  jnz     loc_18007922F
0x180079147  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x18007914e  mov     rcx, rsi; this
0x180079151  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180079156  mov     ebx, eax
0x180079158  test    eax, eax
0x18007915a  js      loc_180079544
0x180079160  mov     rdx, rdi; unsigned __int16 *
0x180079163  mov     rcx, rsi; this
0x180079166  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18007916b  mov     ebx, eax
0x18007916d  test    eax, eax
0x18007916f  js      loc_180079544
0x180079175  cmp     word ptr [rdi], 3Dh ; '='
0x180079179  jnz     loc_18007953F
0x18007917f  test    r15d, r15d
0x180079182  jz      short loc_1800791B6
0x180079184  mov     [rsp+2300h+var_22A0], r14
0x180079189  mov     [rsp+2300h+var_2298], r14
0x18007918e  mov     [rsp+2300h+hKey], r13
0x180079193  mov     r9, rdi; unsigned __int16 *
0x180079196  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x18007919d  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x1800791a2  mov     rcx, rsi; this
0x1800791a5  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1800791aa  mov     ebx, eax
0x1800791ac  mov     [rsp+2300h+hKey], r14
0x1800791b1  jmp     loc_1800790CD
0x1800791b6  cmp     [rbp+2200h+arg_20], r14d
0x1800791bd  jnz     short loc_18007921F
0x1800791bf  test    r12d, r12d
0x1800791c2  jz      short loc_18007921F
0x1800791c4  mov     [rsp+2300h+hKey], r14
0x1800791c9  mov     [rsp+2300h+var_22A0], r14
0x1800791ce  mov     [rsp+2300h+var_2298], r14
0x1800791d3  mov     r9d, 20006h; unsigned int
0x1800791d9  xor     r8d, r8d; lpSubKey
0x1800791dc  mov     rdx, r13; hKey
0x1800791df  lea     rcx, [rsp+2300h+hKey]; this
0x1800791e4  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800791e9  test    eax, eax
0x1800791eb  jnz     loc_180079574
0x1800791f1  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x1800791f8  mov     rcx, [rsp+2300h+hKey]; hKey
0x1800791fd  call    cs:__imp_RegDeleteValueW
0x180079204  nop     dword ptr [rax+rax+00h]
0x180079209  nop
0x18007920a  test    eax, 0FFFFFFFDh
0x18007920f  jnz     loc_180079574
0x180079215  lea     rcx, [rsp+2300h+hKey]; this
0x18007921a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18007921f  mov     rdx, rdi; unsigned __int16 *
0x180079222  mov     rcx, rsi; this
0x180079225  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18007922a  jmp     loc_180078FEA
0x18007922f  mov     edx, 5Ch ; '\'; unsigned __int16
0x180079234  mov     rcx, rdi; lpsz
0x180079237  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18007923c  test    rax, rax
0x18007923f  jnz     loc_18007953F
0x180079245  test    r15d, r15d
0x180079248  jz      loc_18007936C
0x18007924e  mov     ebx, 2001Fh
0x180079253  mov     r9d, ebx; unsigned int
0x180079256  mov     r8, rdi; lpSubKey
0x180079259  mov     rdx, r13; hKey
0x18007925c  lea     rcx, [rsp+2300h+var_2290]; this
0x180079261  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180079266  test    eax, eax
0x180079268  jz      short loc_1800792E5
0x18007926a  lea     r9d, [rbx-6]; unsigned int
0x18007926e  mov     r8, rdi; lpSubKey
0x180079271  mov     rdx, r13; hKey
0x180079274  lea     rcx, [rsp+2300h+var_2290]; this
0x180079279  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18007927e  test    eax, eax
0x180079280  jz      short loc_1800792E5
0x180079282  mov     [rbp+2200h+dwDisposition], r14d
0x180079286  mov     [rbp+2200h+var_2270], r14
0x18007928a  lea     rax, [rbp+2200h+dwDisposition]
0x18007928e  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x180079293  lea     rax, [rbp+2200h+var_2270]
0x180079297  mov     [rsp+2300h+phkResult], rax; phkResult
0x18007929c  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1800792a1  mov     [rsp+2300h+samDesired], ebx; samDesired
0x1800792a5  mov     dword ptr [rsp+2300h+dwOptions], r14d; dwOptions
0x1800792aa  xor     r9d, r9d; lpClass
0x1800792ad  xor     r8d, r8d; Reserved
0x1800792b0  mov     rdx, rdi; lpSubKey
0x1800792b3  mov     rcx, r13; hKey
0x1800792b6  call    cs:__imp_RegCreateKeyExW
0x1800792bd  nop     dword ptr [rax+rax+00h]
0x1800792c2  mov     ecx, eax
0x1800792c4  test    eax, eax
0x1800792c6  jnz     short loc_1800792DD
0x1800792c8  lea     rcx, [rsp+2300h+var_2290]; this
0x1800792cd  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800792d2  mov     ecx, eax
0x1800792d4  mov     rax, [rbp+2200h+var_2270]
0x1800792d8  mov     [rsp+2300h+var_2290], rax
0x1800792dd  test    ecx, ecx
0x1800792df  jnz     loc_180079472
0x1800792e5  mov     rdx, rdi; unsigned __int16 *
0x1800792e8  mov     rcx, rsi; this
0x1800792eb  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800792f0  mov     ebx, eax
0x1800792f2  test    eax, eax
0x1800792f4  js      loc_180079544
0x1800792fa  cmp     word ptr [rdi], 3Dh ; '='
0x1800792fe  jnz     short loc_18007931D
0x180079300  mov     r9, rdi; unsigned __int16 *
0x180079303  xor     r8d, r8d; unsigned __int16 *
0x180079306  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x18007930b  mov     rcx, rsi; this
0x18007930e  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180079313  mov     ebx, eax
0x180079315  test    eax, eax
0x180079317  js      loc_180079544
0x18007931d  cmp     word ptr [rdi], 7Bh ; '{'
0x180079321  jnz     loc_180078FF4
0x180079327  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007932b  inc     rax
0x18007932e  cmp     [rdi+rax*2], r14w
0x180079333  jnz     short loc_18007932B
0x180079335  cmp     rax, 1
0x180079339  jnz     loc_180078FF4
0x18007933f  mov     dword ptr [rsp+2300h+dwOptions], r14d; int
0x180079344  mov     r9d, r15d; int
0x180079347  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18007934c  mov     rdx, rdi; unsigned __int16 *
0x18007934f  mov     rcx, rsi; this
0x180079352  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180079357  mov     ebx, eax
0x180079359  test    eax, eax
0x18007935b  js      loc_180079544
0x180079361  mov     rdx, rdi
0x180079364  mov     rcx, rsi
0x180079367  jmp     loc_180078FE5
0x18007936c  cmp     [rbp+2200h+arg_20], r14d
0x180079373  jnz     short loc_180079390
0x180079375  mov     r9d, 20019h; unsigned int
0x18007937b  mov     r8, rdi; lpSubKey
0x18007937e  mov     rdx, r13; hKey
0x180079381  lea     rcx, [rsp+2300h+var_2290]; this
0x180079386  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18007938b  mov     r14d, eax
0x18007938e  jmp     short loc_180079396
0x180079390  mov     r14d, 2
0x180079396  mov     r15d, 1
0x18007939c  test    r14d, r14d
0x18007939f  cmovz   r15d, [rbp+2200h+arg_20]
0x1800793a7  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800793ab  mov     r8, rdi
0x1800793ae  mov     edx, 104h
0x1800793b3  lea     rcx, [rbp+2200h+var_2260]
0x1800793b7  call    cs:__imp__o_wcsncpy_s
0x1800793be  nop     dword ptr [rax+rax+00h]
0x1800793c3  mov     ecx, eax; int
0x1800793c5  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800793ca  mov     rdx, rdi; unsigned __int16 *
0x1800793cd  mov     rcx, rsi; this
0x1800793d0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800793d5  mov     ebx, eax
0x1800793d7  test    eax, eax
0x1800793d9  js      loc_180079544
0x1800793df  mov     rdx, rdi; unsigned __int16 *
0x1800793e2  mov     rcx, rsi; this
0x1800793e5  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800793ea  mov     ebx, eax
0x1800793ec  xor     ecx, ecx
0x1800793ee  test    eax, eax
0x1800793f0  js      loc_180079544
0x1800793f6  cmp     word ptr [rdi], 7Bh ; '{'
0x1800793fa  jnz     short loc_18007944B
0x1800793fc  or      rax, 0FFFFFFFFFFFFFFFFh
0x180079400  inc     rax
0x180079403  cmp     [rdi+rax*2], cx
0x180079407  jnz     short loc_180079400
0x180079409  cmp     rax, 1
0x18007940d  jnz     short loc_18007944B
0x18007940f  mov     dword ptr [rsp+2300h+dwOptions], r15d; int
0x180079414  xor     r9d, r9d; int
0x180079417  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18007941c  mov     rdx, rdi; unsigned __int16 *
0x18007941f  mov     rcx, rsi; this
0x180079422  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180079427  mov     ebx, eax
0x180079429  test    eax, eax
0x18007942b  jns     short loc_180079436
0x18007942d  test    r15d, r15d
0x180079430  jz      loc_180079544
  ... truncated ...
```
