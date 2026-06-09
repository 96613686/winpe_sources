# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x1800290b0`
- end: `0x180029689`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1497`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x180028d8c`
- `0x1800290b0`

## callees

- `0x18001e1e0`
- `0x18002504c`
- `0x18002579c`
- `0x18002580c`
- `0x180025844`
- `0x1800259e4`
- `0x1800279cc`
- `0x180027e78`
- `0x180027fc8`
- `0x180028128`
- `0x180028c78`
- `0x1800290b0`
- `0x180029e3c`
- `0x180029f0c`
- `0x1800620a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800294b6`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800294b6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002912b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002913e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180029212`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180029241`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002912b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002913e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180029212`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180029241`
- `ADVAPI32!RegDeleteValueW` at `0x180029305`
- `ADVAPI32!RegDeleteValueW` at `0x180029305`
- `ADVAPI32!RegCreateKeyExW` at `0x1800293b7`
- `ADVAPI32!RegCreateKeyExW` at `0x1800293b7`

## string_xrefs

- `0x180029134`: `ForceRemove`
- `0x180029208`: `NoRemove`
- `0x180029121`: `Delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
          v29 = 0;
          v30 = 0;
          if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
          {
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_78:
            v10 = -2147352567;
            goto LABEL_79;
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
              goto LABEL_81;
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
          goto LABEL_79;
      }
      if ( !lstrcmpiW(v7, L"Val") )
        break;
      if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        goto LABEL_78;
      if ( v5 )
      {
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v31, a3, v7, 0x2001Fu) )
        {
          if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v31, a3, v7, 0x20019u) )
          {
            dwDisposition = 0;
            phkResult = 0;
            v16 = RegCreateKeyExW(a3, v7, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
            if ( v16 )
              goto LABEL_65;
            v16 = ATL::CRegKey::Close((ATL::CRegKey *)v31);
            v31[0] = phkResult;
            if ( v16 )
              goto LABEL_65;
          }
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        if ( *v7 == 61 )
        {
          v10 = ATL::CRegParser::AddValue(v8, v31, 0, v7);
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
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v31[0], v5, 0);
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
          v18 = ATL::CRegKey::Open((ATL::CRegKey *)v31, a3, v7, 0x20019u);
        v19 = 1;
        if ( !v18 )
          v19 = a5;
        v20 = _o_wcsncpy_s(v34, 260, v7, -1, dwOptions);
        ATL::AtlCrtErrorCheck(v20);
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        v10 = ATL::CRegParser::SkipAssignment(v8, v7);
        v21 = 0;
        if ( v10 < 0 )
          goto LABEL_79;
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
              goto LABEL_65;
            }
            if ( v14 && !HasSubKeys )
            {
              v29 = 0;
              v30 = 0;
              hKey = a3;
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, v34);
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
      v29 = 0;
      v30 = 0;
      hKey = a3;
      v13 = ATL::CRegParser::AddValue(v8, &hKey, ValueName, v7);
      v10 = v13;
      hKey = 0;
LABEL_15:
      if ( v13 < 0 )
        goto LABEL_81;
      ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
      goto LABEL_41;
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
LABEL_80:
  v10 = ATL::AtlHresultFromWin32(v15);
LABEL_81:
  ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_79:
  ATL::CRegKey::Close((ATL::CRegKey *)v31);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800290b0  push    rbp
0x1800290b2  push    rbx
0x1800290b3  push    rsi
0x1800290b4  push    rdi
0x1800290b5  push    r12
0x1800290b7  push    r13
0x1800290b9  push    r14
0x1800290bb  push    r15
0x1800290bd  lea     rbp, [rsp-21C8h]
0x1800290c5  mov     eax, 22C8h
0x1800290ca  call    _alloca_probe
0x1800290cf  sub     rsp, rax
0x1800290d2  mov     rax, cs:__security_cookie
0x1800290d9  xor     rax, rsp
0x1800290dc  mov     [rbp+2200h+var_50], rax
0x1800290e3  mov     r15d, r9d
0x1800290e6  mov     [rsp+2300h+var_22B0], r9d
0x1800290eb  mov     r13, r8
0x1800290ee  mov     rdi, rdx
0x1800290f1  mov     rsi, rcx
0x1800290f4  xor     r14d, r14d
0x1800290f7  mov     [rsp+2300h+var_2290], r14
0x1800290fc  mov     [rsp+2300h+var_2288], r14
0x180029101  mov     [rbp+2200h+var_2280], r14
0x180029105  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002910a  test    eax, eax
0x18002910c  mov     ebx, eax
0x18002910e  js      loc_18002963D
0x180029114  xor     r12d, r12d
0x180029117  cmp     word ptr [rdi], 7Dh ; '}'
0x18002911b  jz      loc_18002963D
0x180029121  lea     rdx, aDelete; "Delete"
0x180029128  mov     rcx, rdi; lpString1
0x18002912b  call    cs:__imp_lstrcmpiW
0x180029131  mov     r14d, eax
0x180029134  lea     rdx, aForceremove; "ForceRemove"
0x18002913b  mov     rcx, rdi; lpString1
0x18002913e  call    cs:__imp_lstrcmpiW
0x180029144  test    eax, eax
0x180029146  jz      short loc_180029151
0x180029148  test    r14d, r14d
0x18002914b  jnz     loc_180029202
0x180029151  mov     rdx, rdi; unsigned __int16 *
0x180029154  mov     rcx, rsi; this
0x180029157  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002915c  mov     ebx, eax
0x18002915e  test    eax, eax
0x180029160  js      loc_18002963D
0x180029166  test    r15d, r15d
0x180029169  jz      loc_180029202
0x18002916f  mov     [rsp+2300h+hKey], r12
0x180029174  mov     [rsp+2300h+var_22A0], r12
0x180029179  mov     [rsp+2300h+var_2298], r12
0x18002917e  mov     edx, 5Ch ; '\'; unsigned __int16
0x180029183  mov     rcx, rdi; lpsz
0x180029186  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18002918b  test    rax, rax
0x18002918e  jnz     loc_18002962E
0x180029194  mov     rdx, rdi; unsigned __int16 *
0x180029197  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x18002919c  test    eax, eax
0x18002919e  jz      short loc_1800291B7
0x1800291a0  mov     [rsp+2300h+hKey], r13
0x1800291a5  mov     rdx, rdi; unsigned __int16 *
0x1800291a8  lea     rcx, [rsp+2300h+hKey]; this
0x1800291ad  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1800291b2  mov     [rsp+2300h+hKey], r12
0x1800291b7  test    r14d, r14d
0x1800291ba  jnz     short loc_1800291F8
0x1800291bc  mov     rdx, rdi; unsigned __int16 *
0x1800291bf  mov     rcx, rsi; this
0x1800291c2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800291c7  mov     ebx, eax
0x1800291c9  xor     r14d, r14d
0x1800291cc  test    eax, eax
0x1800291ce  js      loc_180029675
0x1800291d4  mov     rdx, rdi; unsigned __int16 *
0x1800291d7  mov     rcx, rsi; this
0x1800291da  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800291df  mov     ebx, eax
0x1800291e1  test    eax, eax
0x1800291e3  lea     rcx, [rsp+2300h+hKey]; this
0x1800291e8  js      loc_18002967A
0x1800291ee  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800291f3  jmp     loc_18002941C
0x1800291f8  lea     rcx, [rsp+2300h+hKey]; this
0x1800291fd  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180029202  mov     r12d, 1
0x180029208  lea     rdx, aNoremove; "NoRemove"
0x18002920f  mov     rcx, rdi; lpString1
0x180029212  call    cs:__imp_lstrcmpiW
0x180029218  xor     r14d, r14d
0x18002921b  test    eax, eax
0x18002921d  jnz     short loc_180029237
0x18002921f  mov     r12d, r14d
0x180029222  mov     rdx, rdi; unsigned __int16 *
0x180029225  mov     rcx, rsi; this
0x180029228  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002922d  mov     ebx, eax
0x18002922f  test    eax, eax
0x180029231  js      loc_18002963D
0x180029237  lea     rdx, aVal; "Val"
0x18002923e  mov     rcx, rdi; lpString1
0x180029241  call    cs:__imp_lstrcmpiW
0x180029247  test    eax, eax
0x180029249  jnz     loc_180029330
0x18002924f  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x180029256  mov     rcx, rsi; this
0x180029259  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002925e  mov     ebx, eax
0x180029260  test    eax, eax
0x180029262  js      loc_18002963D
0x180029268  mov     rdx, rdi; unsigned __int16 *
0x18002926b  mov     rcx, rsi; this
0x18002926e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180029273  mov     ebx, eax
0x180029275  test    eax, eax
0x180029277  js      loc_18002963D
0x18002927d  cmp     word ptr [rdi], 3Dh ; '='
0x180029281  jnz     loc_180029638
0x180029287  test    r15d, r15d
0x18002928a  jz      short loc_1800292BE
0x18002928c  mov     [rsp+2300h+var_22A0], r14
0x180029291  mov     [rsp+2300h+var_2298], r14
0x180029296  mov     [rsp+2300h+hKey], r13
0x18002929b  mov     r9, rdi; unsigned __int16 *
0x18002929e  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x1800292a5  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x1800292aa  mov     rcx, rsi; this
0x1800292ad  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1800292b2  mov     ebx, eax
0x1800292b4  mov     [rsp+2300h+hKey], r14
0x1800292b9  jmp     loc_1800291E1
0x1800292be  cmp     [rbp+2200h+arg_20], r14d
0x1800292c5  jnz     short loc_180029320
0x1800292c7  test    r12d, r12d
0x1800292ca  jz      short loc_180029320
0x1800292cc  mov     [rsp+2300h+hKey], r14
0x1800292d1  mov     [rsp+2300h+var_22A0], r14
0x1800292d6  mov     [rsp+2300h+var_2298], r14
0x1800292db  mov     r9d, 20006h; unsigned int
0x1800292e1  xor     r8d, r8d; lpSubKey
0x1800292e4  mov     rdx, r13; hKey
0x1800292e7  lea     rcx, [rsp+2300h+hKey]; this
0x1800292ec  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800292f1  test    eax, eax
0x1800292f3  jnz     loc_18002966C
0x1800292f9  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x180029300  mov     rcx, [rsp+2300h+hKey]; hKey
0x180029305  call    cs:__imp_RegDeleteValueW
0x18002930b  test    eax, 0FFFFFFFDh
0x180029310  jnz     loc_18002966C
0x180029316  lea     rcx, [rsp+2300h+hKey]; this
0x18002931b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180029320  mov     rdx, rdi; unsigned __int16 *
0x180029323  mov     rcx, rsi; this
0x180029326  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18002932b  jmp     loc_18002910A
0x180029330  mov     edx, 5Ch ; '\'; unsigned __int16
0x180029335  mov     rcx, rdi; lpsz
0x180029338  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18002933d  test    rax, rax
0x180029340  jnz     loc_180029638
0x180029346  test    r15d, r15d
0x180029349  jz      loc_18002946B
0x18002934f  mov     ebx, 2001Fh
0x180029354  mov     r9d, ebx; unsigned int
0x180029357  mov     r8, rdi; lpSubKey
0x18002935a  mov     rdx, r13; hKey
0x18002935d  lea     rcx, [rsp+2300h+var_2290]; this
0x180029362  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180029367  test    eax, eax
0x180029369  jz      short loc_1800293E4
0x18002936b  lea     r9d, [rbx-6]; unsigned int
0x18002936f  mov     r8, rdi; lpSubKey
0x180029372  mov     rdx, r13; hKey
0x180029375  lea     rcx, [rsp+2300h+var_2290]; this
0x18002937a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18002937f  test    eax, eax
0x180029381  jz      short loc_1800293E4
0x180029383  mov     [rbp+2200h+dwDisposition], r14d
0x180029387  mov     [rbp+2200h+var_2270], r14
0x18002938b  lea     rax, [rbp+2200h+dwDisposition]
0x18002938f  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x180029394  lea     rax, [rbp+2200h+var_2270]
0x180029398  mov     [rsp+2300h+phkResult], rax; phkResult
0x18002939d  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1800293a2  mov     [rsp+2300h+samDesired], ebx; samDesired
0x1800293a6  mov     dword ptr [rsp+2300h+dwOptions], r14d; dwOptions
0x1800293ab  xor     r9d, r9d; lpClass
0x1800293ae  xor     r8d, r8d; Reserved
0x1800293b1  mov     rdx, rdi; lpSubKey
0x1800293b4  mov     rcx, r13; hKey
0x1800293b7  call    cs:__imp_RegCreateKeyExW
0x1800293bd  mov     ecx, eax
0x1800293bf  test    eax, eax
0x1800293c1  jnz     loc_18002956B
0x1800293c7  lea     rcx, [rsp+2300h+var_2290]; this
0x1800293cc  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800293d1  mov     ecx, eax
0x1800293d3  mov     rax, [rbp+2200h+var_2270]
0x1800293d7  mov     [rsp+2300h+var_2290], rax
0x1800293dc  test    ecx, ecx
0x1800293de  jnz     loc_18002956B
0x1800293e4  mov     rdx, rdi; unsigned __int16 *
0x1800293e7  mov     rcx, rsi; this
0x1800293ea  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800293ef  mov     ebx, eax
0x1800293f1  test    eax, eax
0x1800293f3  js      loc_18002963D
0x1800293f9  cmp     word ptr [rdi], 3Dh ; '='
0x1800293fd  jnz     short loc_18002941C
0x1800293ff  mov     r9, rdi; unsigned __int16 *
0x180029402  xor     r8d, r8d; unsigned __int16 *
0x180029405  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x18002940a  mov     rcx, rsi; this
0x18002940d  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180029412  mov     ebx, eax
0x180029414  test    eax, eax
0x180029416  js      loc_18002963D
0x18002941c  cmp     word ptr [rdi], 7Bh ; '{'
0x180029420  jnz     loc_180029114
0x180029426  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002942a  inc     rax
0x18002942d  cmp     [rdi+rax*2], r14w
0x180029432  jnz     short loc_18002942A
0x180029434  cmp     rax, 1
0x180029438  jnz     loc_180029114
0x18002943e  mov     dword ptr [rsp+2300h+dwOptions], r14d; int
0x180029443  mov     r9d, r15d; int
0x180029446  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18002944b  mov     rdx, rdi; unsigned __int16 *
0x18002944e  mov     rcx, rsi; this
0x180029451  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180029456  mov     ebx, eax
0x180029458  test    eax, eax
0x18002945a  js      loc_18002963D
0x180029460  mov     rdx, rdi
0x180029463  mov     rcx, rsi
0x180029466  jmp     loc_180029105
0x18002946b  cmp     [rbp+2200h+arg_20], r14d
0x180029472  jnz     short loc_18002948F
0x180029474  mov     r9d, 20019h; unsigned int
0x18002947a  mov     r8, rdi; lpSubKey
0x18002947d  mov     rdx, r13; hKey
0x180029480  lea     rcx, [rsp+2300h+var_2290]; this
0x180029485  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18002948a  mov     r14d, eax
0x18002948d  jmp     short loc_180029495
0x18002948f  mov     r14d, 2
0x180029495  mov     r15d, 1
0x18002949b  test    r14d, r14d
0x18002949e  cmovz   r15d, [rbp+2200h+arg_20]
0x1800294a6  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800294aa  mov     r8, rdi
0x1800294ad  mov     edx, 104h
0x1800294b2  lea     rcx, [rbp+2200h+var_2260]
0x1800294b6  call    cs:__imp__o_wcsncpy_s
0x1800294bc  mov     ecx, eax; int
0x1800294be  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800294c3  mov     rdx, rdi; unsigned __int16 *
0x1800294c6  mov     rcx, rsi; this
0x1800294c9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800294ce  mov     ebx, eax
0x1800294d0  test    eax, eax
0x1800294d2  js      loc_18002963D
0x1800294d8  mov     rdx, rdi; unsigned __int16 *
0x1800294db  mov     rcx, rsi; this
0x1800294de  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800294e3  mov     ebx, eax
0x1800294e5  xor     ecx, ecx
0x1800294e7  test    eax, eax
0x1800294e9  js      loc_18002963D
0x1800294ef  cmp     word ptr [rdi], 7Bh ; '{'
0x1800294f3  jnz     short loc_180029544
0x1800294f5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800294f9  inc     rax
0x1800294fc  cmp     [rdi+rax*2], cx
0x180029500  jnz     short loc_1800294F9
0x180029502  cmp     rax, 1
0x180029506  jnz     short loc_180029544
0x180029508  mov     dword ptr [rsp+2300h+dwOptions], r15d; int
0x18002950d  xor     r9d, r9d; int
0x180029510  mov     r8, [rsp+2300h+var_2290]; HKEY
0x180029515  mov     rdx, rdi; unsigned __int16 *
0x180029518  mov     rcx, rsi; this
0x18002951b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180029520  mov     ebx, eax
0x180029522  test    eax, eax
0x180029524  jns     short loc_18002952F
0x180029526  test    r15d, r15d
0x180029529  jz      loc_18002963D
0x18002952f  mov     rdx, rdi; unsigned __int16 *
0x180029532  mov     rcx, rsi; this
0x180029535  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002953a  mov     ebx, eax
0x18002953c  test    eax, eax
0x18002953e  js      loc_18002963D
0x180029544  cmp     r14d, 2
0x180029548  mov     r15d, [rsp+2300h+var_22B0]
  ... truncated ...
```
