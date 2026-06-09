# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180078fb0`
- end: `0x1800795b1`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1537`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x180078c5c`
- `0x180078fb0`

## callees

- `0x18004b5f0`
- `0x180077ae0`
- `0x180078134`
- `0x1800781a8`
- `0x1800781e0`
- `0x180078388`
- `0x1800783bc`
- `0x1800785cc`
- `0x180078678`
- `0x180078808`
- `0x180078b3c`
- `0x180078fb0`
- `0x180079630`
- `0x180079818`
- `0x1800821f0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800793d7`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800793d7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18007921d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18007921d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800792d6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800792d6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18007902b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180079044`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18007911e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180079153`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18007902b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180079044`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18007911e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180079153`

## string_xrefs

- `0x18007903a`: `ForceRemove`
- `0x180079114`: `NoRemove`
- `0x180079021`: `Delete`

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
  ATL::CRegParser *v8; // rsi
  int Token; // eax
  int v10; // ebx
  int v11; // r14d
  ATL::CRegParser *v12; // rcx
  int v13; // eax
  int v14; // r12d
  unsigned int v15; // eax
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
          if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v12, v7) )
          {
            hKey = a3;
            ATL::CRegKey::RecurseDeleteKey(&hKey, v7);
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
            if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v21, v34) && v14 )
              ATL::CRegKey::RecurseDeleteKey(v31, v34);
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
0x180078fb0  push    rbp
0x180078fb2  push    rbx
0x180078fb3  push    rsi
0x180078fb4  push    rdi
0x180078fb5  push    r12
0x180078fb7  push    r13
0x180078fb9  push    r14
0x180078fbb  push    r15
0x180078fbd  lea     rbp, [rsp-21C8h]
0x180078fc5  mov     eax, 22C8h
0x180078fca  call    _alloca_probe
0x180078fcf  sub     rsp, rax
0x180078fd2  mov     rax, cs:__security_cookie
0x180078fd9  xor     rax, rsp
0x180078fdc  mov     [rbp+2200h+var_50], rax
0x180078fe3  mov     r15d, r9d
0x180078fe6  mov     [rsp+2300h+var_22B0], r9d
0x180078feb  mov     r13, r8
0x180078fee  mov     rdi, rdx
0x180078ff1  mov     rsi, rcx
0x180078ff4  xor     r14d, r14d
0x180078ff7  mov     [rsp+2300h+var_2290], r14
0x180078ffc  mov     [rsp+2300h+var_2288], r14
0x180079001  mov     [rbp+2200h+var_2280], r14
0x180079005  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18007900a  test    eax, eax
0x18007900c  mov     ebx, eax
0x18007900e  js      loc_180079564
0x180079014  xor     r12d, r12d
0x180079017  cmp     word ptr [rdi], 7Dh ; '}'
0x18007901b  jz      loc_180079564
0x180079021  lea     rdx, aDelete; "Delete"
0x180079028  mov     rcx, rdi; lpString1
0x18007902b  call    cs:__imp_lstrcmpiW
0x180079032  nop     dword ptr [rax+rax+00h]
0x180079037  mov     r14d, eax
0x18007903a  lea     rdx, aForceremove; "ForceRemove"
0x180079041  mov     rcx, rdi; lpString1
0x180079044  call    cs:__imp_lstrcmpiW
0x18007904b  nop     dword ptr [rax+rax+00h]
0x180079050  test    eax, eax
0x180079052  jz      short loc_18007905D
0x180079054  test    r14d, r14d
0x180079057  jnz     loc_18007910E
0x18007905d  mov     rdx, rdi; unsigned __int16 *
0x180079060  mov     rcx, rsi; this
0x180079063  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180079068  mov     ebx, eax
0x18007906a  test    eax, eax
0x18007906c  js      loc_180079564
0x180079072  test    r15d, r15d
0x180079075  jz      loc_18007910E
0x18007907b  mov     [rsp+2300h+hKey], r12
0x180079080  mov     [rsp+2300h+var_22A0], r12
0x180079085  mov     [rsp+2300h+var_2298], r12
0x18007908a  mov     edx, 5Ch ; '\'; unsigned __int16
0x18007908f  mov     rcx, rdi; lpsz
0x180079092  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180079097  test    rax, rax
0x18007909a  jnz     loc_180079555
0x1800790a0  mov     rdx, rdi; unsigned __int16 *
0x1800790a3  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x1800790a8  test    eax, eax
0x1800790aa  jz      short loc_1800790C3
0x1800790ac  mov     [rsp+2300h+hKey], r13
0x1800790b1  mov     rdx, rdi; unsigned __int16 *
0x1800790b4  lea     rcx, [rsp+2300h+hKey]; this
0x1800790b9  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1800790be  mov     [rsp+2300h+hKey], r12
0x1800790c3  test    r14d, r14d
0x1800790c6  jnz     short loc_180079104
0x1800790c8  mov     rdx, rdi; unsigned __int16 *
0x1800790cb  mov     rcx, rsi; this
0x1800790ce  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800790d3  mov     ebx, eax
0x1800790d5  xor     r14d, r14d
0x1800790d8  test    eax, eax
0x1800790da  js      loc_18007959D
0x1800790e0  mov     rdx, rdi; unsigned __int16 *
0x1800790e3  mov     rcx, rsi; this
0x1800790e6  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800790eb  mov     ebx, eax
0x1800790ed  test    eax, eax
0x1800790ef  lea     rcx, [rsp+2300h+hKey]; this
0x1800790f4  js      loc_1800795A2
0x1800790fa  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800790ff  jmp     loc_18007933D
0x180079104  lea     rcx, [rsp+2300h+hKey]; this
0x180079109  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18007910e  mov     r12d, 1
0x180079114  lea     rdx, aNoremove; "NoRemove"
0x18007911b  mov     rcx, rdi; lpString1
0x18007911e  call    cs:__imp_lstrcmpiW
0x180079125  nop     dword ptr [rax+rax+00h]
0x18007912a  xor     r14d, r14d
0x18007912d  test    eax, eax
0x18007912f  jnz     short loc_180079149
0x180079131  mov     r12d, r14d
0x180079134  mov     rdx, rdi; unsigned __int16 *
0x180079137  mov     rcx, rsi; this
0x18007913a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18007913f  mov     ebx, eax
0x180079141  test    eax, eax
0x180079143  js      loc_180079564
0x180079149  lea     rdx, aVal; "Val"
0x180079150  mov     rcx, rdi; lpString1
0x180079153  call    cs:__imp_lstrcmpiW
0x18007915a  nop     dword ptr [rax+rax+00h]
0x18007915f  test    eax, eax
0x180079161  jnz     loc_18007924F
0x180079167  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x18007916e  mov     rcx, rsi; this
0x180079171  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180079176  mov     ebx, eax
0x180079178  test    eax, eax
0x18007917a  js      loc_180079564
0x180079180  mov     rdx, rdi; unsigned __int16 *
0x180079183  mov     rcx, rsi; this
0x180079186  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18007918b  mov     ebx, eax
0x18007918d  test    eax, eax
0x18007918f  js      loc_180079564
0x180079195  cmp     word ptr [rdi], 3Dh ; '='
0x180079199  jnz     loc_18007955F
0x18007919f  test    r15d, r15d
0x1800791a2  jz      short loc_1800791D6
0x1800791a4  mov     [rsp+2300h+var_22A0], r14
0x1800791a9  mov     [rsp+2300h+var_2298], r14
0x1800791ae  mov     [rsp+2300h+hKey], r13
0x1800791b3  mov     r9, rdi; unsigned __int16 *
0x1800791b6  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x1800791bd  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x1800791c2  mov     rcx, rsi; this
0x1800791c5  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1800791ca  mov     ebx, eax
0x1800791cc  mov     [rsp+2300h+hKey], r14
0x1800791d1  jmp     loc_1800790ED
0x1800791d6  cmp     [rbp+2200h+arg_20], r14d
0x1800791dd  jnz     short loc_18007923F
0x1800791df  test    r12d, r12d
0x1800791e2  jz      short loc_18007923F
0x1800791e4  mov     [rsp+2300h+hKey], r14
0x1800791e9  mov     [rsp+2300h+var_22A0], r14
0x1800791ee  mov     [rsp+2300h+var_2298], r14
0x1800791f3  mov     r9d, 20006h; unsigned int
0x1800791f9  xor     r8d, r8d; lpSubKey
0x1800791fc  mov     rdx, r13; hKey
0x1800791ff  lea     rcx, [rsp+2300h+hKey]; this
0x180079204  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180079209  test    eax, eax
0x18007920b  jnz     loc_180079594
0x180079211  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x180079218  mov     rcx, [rsp+2300h+hKey]; hKey
0x18007921d  call    cs:__imp_RegDeleteValueW
0x180079224  nop     dword ptr [rax+rax+00h]
0x180079229  nop
0x18007922a  test    eax, 0FFFFFFFDh
0x18007922f  jnz     loc_180079594
0x180079235  lea     rcx, [rsp+2300h+hKey]; this
0x18007923a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18007923f  mov     rdx, rdi; unsigned __int16 *
0x180079242  mov     rcx, rsi; this
0x180079245  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18007924a  jmp     loc_18007900A
0x18007924f  mov     edx, 5Ch ; '\'; unsigned __int16
0x180079254  mov     rcx, rdi; lpsz
0x180079257  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18007925c  test    rax, rax
0x18007925f  jnz     loc_18007955F
0x180079265  test    r15d, r15d
0x180079268  jz      loc_18007938C
0x18007926e  mov     ebx, 2001Fh
0x180079273  mov     r9d, ebx; unsigned int
0x180079276  mov     r8, rdi; lpSubKey
0x180079279  mov     rdx, r13; hKey
0x18007927c  lea     rcx, [rsp+2300h+var_2290]; this
0x180079281  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180079286  test    eax, eax
0x180079288  jz      short loc_180079305
0x18007928a  lea     r9d, [rbx-6]; unsigned int
0x18007928e  mov     r8, rdi; lpSubKey
0x180079291  mov     rdx, r13; hKey
0x180079294  lea     rcx, [rsp+2300h+var_2290]; this
0x180079299  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18007929e  test    eax, eax
0x1800792a0  jz      short loc_180079305
0x1800792a2  mov     [rbp+2200h+dwDisposition], r14d
0x1800792a6  mov     [rbp+2200h+var_2270], r14
0x1800792aa  lea     rax, [rbp+2200h+dwDisposition]
0x1800792ae  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x1800792b3  lea     rax, [rbp+2200h+var_2270]
0x1800792b7  mov     [rsp+2300h+phkResult], rax; phkResult
0x1800792bc  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1800792c1  mov     [rsp+2300h+samDesired], ebx; samDesired
0x1800792c5  mov     dword ptr [rsp+2300h+dwOptions], r14d; dwOptions
0x1800792ca  xor     r9d, r9d; lpClass
0x1800792cd  xor     r8d, r8d; Reserved
0x1800792d0  mov     rdx, rdi; lpSubKey
0x1800792d3  mov     rcx, r13; hKey
0x1800792d6  call    cs:__imp_RegCreateKeyExW
0x1800792dd  nop     dword ptr [rax+rax+00h]
0x1800792e2  mov     ecx, eax
0x1800792e4  test    eax, eax
0x1800792e6  jnz     short loc_1800792FD
0x1800792e8  lea     rcx, [rsp+2300h+var_2290]; this
0x1800792ed  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800792f2  mov     ecx, eax
0x1800792f4  mov     rax, [rbp+2200h+var_2270]
0x1800792f8  mov     [rsp+2300h+var_2290], rax
0x1800792fd  test    ecx, ecx
0x1800792ff  jnz     loc_180079492
0x180079305  mov     rdx, rdi; unsigned __int16 *
0x180079308  mov     rcx, rsi; this
0x18007930b  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180079310  mov     ebx, eax
0x180079312  test    eax, eax
0x180079314  js      loc_180079564
0x18007931a  cmp     word ptr [rdi], 3Dh ; '='
0x18007931e  jnz     short loc_18007933D
0x180079320  mov     r9, rdi; unsigned __int16 *
0x180079323  xor     r8d, r8d; unsigned __int16 *
0x180079326  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x18007932b  mov     rcx, rsi; this
0x18007932e  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180079333  mov     ebx, eax
0x180079335  test    eax, eax
0x180079337  js      loc_180079564
0x18007933d  cmp     word ptr [rdi], 7Bh ; '{'
0x180079341  jnz     loc_180079014
0x180079347  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007934b  inc     rax
0x18007934e  cmp     [rdi+rax*2], r14w
0x180079353  jnz     short loc_18007934B
0x180079355  cmp     rax, 1
0x180079359  jnz     loc_180079014
0x18007935f  mov     dword ptr [rsp+2300h+dwOptions], r14d; int
0x180079364  mov     r9d, r15d; int
0x180079367  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18007936c  mov     rdx, rdi; unsigned __int16 *
0x18007936f  mov     rcx, rsi; this
0x180079372  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180079377  mov     ebx, eax
0x180079379  test    eax, eax
0x18007937b  js      loc_180079564
0x180079381  mov     rdx, rdi
0x180079384  mov     rcx, rsi
0x180079387  jmp     loc_180079005
0x18007938c  cmp     [rbp+2200h+arg_20], r14d
0x180079393  jnz     short loc_1800793B0
0x180079395  mov     r9d, 20019h; unsigned int
0x18007939b  mov     r8, rdi; lpSubKey
0x18007939e  mov     rdx, r13; hKey
0x1800793a1  lea     rcx, [rsp+2300h+var_2290]; this
0x1800793a6  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800793ab  mov     r14d, eax
0x1800793ae  jmp     short loc_1800793B6
0x1800793b0  mov     r14d, 2
0x1800793b6  mov     r15d, 1
0x1800793bc  test    r14d, r14d
0x1800793bf  cmovz   r15d, [rbp+2200h+arg_20]
0x1800793c7  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800793cb  mov     r8, rdi
0x1800793ce  mov     edx, 104h
0x1800793d3  lea     rcx, [rbp+2200h+var_2260]
0x1800793d7  call    cs:__imp__o_wcsncpy_s
0x1800793de  nop     dword ptr [rax+rax+00h]
0x1800793e3  mov     ecx, eax; int
0x1800793e5  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800793ea  mov     rdx, rdi; unsigned __int16 *
0x1800793ed  mov     rcx, rsi; this
0x1800793f0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800793f5  mov     ebx, eax
0x1800793f7  test    eax, eax
0x1800793f9  js      loc_180079564
0x1800793ff  mov     rdx, rdi; unsigned __int16 *
0x180079402  mov     rcx, rsi; this
0x180079405  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18007940a  mov     ebx, eax
0x18007940c  xor     ecx, ecx
0x18007940e  test    eax, eax
0x180079410  js      loc_180079564
0x180079416  cmp     word ptr [rdi], 7Bh ; '{'
0x18007941a  jnz     short loc_18007946B
0x18007941c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180079420  inc     rax
0x180079423  cmp     [rdi+rax*2], cx
0x180079427  jnz     short loc_180079420
0x180079429  cmp     rax, 1
0x18007942d  jnz     short loc_18007946B
0x18007942f  mov     dword ptr [rsp+2300h+dwOptions], r15d; int
0x180079434  xor     r9d, r9d; int
0x180079437  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18007943c  mov     rdx, rdi; unsigned __int16 *
0x18007943f  mov     rcx, rsi; this
0x180079442  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180079447  mov     ebx, eax
0x180079449  test    eax, eax
0x18007944b  jns     short loc_180079456
0x18007944d  test    r15d, r15d
0x180079450  jz      loc_180079564
  ... truncated ...
```
