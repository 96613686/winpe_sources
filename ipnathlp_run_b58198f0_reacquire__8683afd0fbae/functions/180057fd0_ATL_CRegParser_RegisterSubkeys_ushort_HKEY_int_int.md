# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180057fd0`
- end: `0x180058576`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1446`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800577e4`
- `0x180057fd0`

## callees

- `0x180051f30`
- `0x1800547c8`
- `0x180054d50`
- `0x180054dc4`
- `0x180054e04`
- `0x180054fb0`
- `0x180054fe4`
- `0x180055354`
- `0x180055a10`
- `0x180056028`
- `0x1800572dc`
- `0x1800576c4`
- `0x180057fd0`
- `0x180058bbc`
- `0x180058c94`
- `0x180095ab0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800583af`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x1800583af`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180058239`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180058239`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180058044`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18005805d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180058134`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180058169`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180058044`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18005805d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180058134`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180058169`

## string_xrefs

- `0x180058053`: `ForceRemove`
- `0x18005812a`: `NoRemove`
- `0x18005803a`: `Delete`

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
  LSTATUS v15; // eax
  unsigned __int16 *v16; // r9
  unsigned int v17; // eax
  __int64 v18; // rax
  int v19; // r14d
  int v20; // r15d
  int v21; // eax
  ATL::CRegParser *v22; // rcx
  __int64 v23; // rax
  unsigned int v24; // ecx
  int HasSubKeys; // r14d
  __int64 v27; // [rsp+20h] [rbp-E0h]
  unsigned int v28; // [rsp+28h] [rbp-D8h]
  struct _SECURITY_ATTRIBUTES *v29; // [rsp+30h] [rbp-D0h]
  unsigned int *v30; // [rsp+38h] [rbp-C8h]
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v33; // [rsp+50h] [rbp-B0h]
  __int64 v34; // [rsp+58h] [rbp-A8h]
  HKEY v35[4]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v36[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ValueName[4096]; // [rsp+290h] [rbp+190h] BYREF

  v5 = a4;
  v7 = a2;
  v8 = this;
  memset(v35, 0, 24);
LABEL_2:
  Token = ATL::CRegParser::NextToken(this, a2);
  while ( 2 )
  {
    v10 = Token;
    if ( Token < 0 )
      goto LABEL_80;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( *v7 == 125 )
          goto LABEL_80;
        v11 = lstrcmpiW(v7, L"Delete");
        if ( lstrcmpiW(v7, L"ForceRemove") )
        {
          if ( v11 )
            break;
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_80;
        if ( !v5 )
          break;
        hKey = 0;
        v33 = 0;
        v34 = 0;
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
        if ( v11 )
        {
          ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
          break;
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_82;
        v13 = ATL::CRegParser::SkipAssignment(v8, v7);
        v10 = v13;
LABEL_15:
        if ( v13 < 0 )
          goto LABEL_82;
        ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_40:
        if ( *v7 == 123 )
        {
          v18 = -1;
          do
            ++v18;
          while ( v7[v18] );
          if ( v18 == 1 )
          {
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v35[0], v5, 0);
            if ( v10 < 0 )
              goto LABEL_80;
            a2 = v7;
            this = v8;
            goto LABEL_2;
          }
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
        if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v35, a3, v7, 0x2001Fu)
          || !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v35, a3, v7, 0x20019u)
          || (v17 = ATL::CRegKey::Create((ATL::CRegKey *)v35, a3, v7, v16, v27, v28, v29, v30)) == 0 )
        {
          v10 = ATL::CRegParser::NextToken(v8, v7);
          if ( v10 < 0 )
            goto LABEL_80;
          if ( *v7 == 61 )
          {
            v10 = ATL::CRegParser::AddValue(v8, v35, 0, v7);
            if ( v10 < 0 )
              goto LABEL_80;
          }
          goto LABEL_40;
        }
LABEL_83:
        v24 = v17;
LABEL_64:
        v10 = ATL::AtlHresultFromWin32(v24);
        goto LABEL_80;
      }
      if ( a5 )
        v19 = 2;
      else
        v19 = ATL::CRegKey::Open((ATL::CRegKey *)v35, a3, v7, 0x20019u);
      v20 = 1;
      if ( !v19 )
        v20 = a5;
      v21 = _o_wcsncpy_s(v36, 260, v7, -1, v27);
      ATL::AtlCrtErrorCheck(v21);
      v10 = ATL::CRegParser::NextToken(v8, v7);
      if ( v10 < 0 )
        goto LABEL_80;
      v10 = ATL::CRegParser::SkipAssignment(v8, v7);
      v22 = 0;
      if ( v10 < 0 )
        goto LABEL_80;
      if ( *v7 == 123 )
      {
        v23 = -1;
        do
          ++v23;
        while ( v7[v23] );
        if ( v23 == 1 )
        {
          v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v35[0], 0, v20);
          if ( v10 < 0 && !v20 )
            goto LABEL_80;
          v10 = ATL::CRegParser::NextToken(v8, v7);
          if ( v10 < 0 )
            goto LABEL_80;
        }
      }
      if ( v19 != 2 )
      {
        if ( v19 )
        {
          if ( !a5 )
          {
            v24 = v19;
            goto LABEL_64;
          }
        }
        else if ( a5 && ATL::CRegParser::HasSubKeys(v22, v35[0]) )
        {
          if ( ATL::CRegParser::CanForceRemoveKey(v22, v36) && v14 )
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v35, v36);
        }
        else
        {
          HasSubKeys = ATL::CRegParser::HasSubKeys(v22, v35[0]);
          v17 = ATL::CRegKey::Close((ATL::CRegKey *)v35);
          if ( v17 )
            goto LABEL_83;
          if ( v14 && !HasSubKeys )
          {
            v33 = 0;
            v34 = 0;
            hKey = a3;
            v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, v36);
            hKey = 0;
            if ( v15 )
              goto LABEL_81;
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
          }
        }
      }
      v5 = a4;
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
      v33 = 0;
      v34 = 0;
      hKey = a3;
      v13 = ATL::CRegParser::AddValue(v8, &hKey, ValueName, v7);
      v10 = v13;
      hKey = 0;
      goto LABEL_15;
    }
    if ( a5 || !v14 )
      goto LABEL_31;
    hKey = 0;
    v33 = 0;
    v34 = 0;
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
  ATL::CRegKey::Close((ATL::CRegKey *)v35);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180057fd0  push    rbp
0x180057fd2  push    rbx
0x180057fd3  push    rsi
0x180057fd4  push    rdi
0x180057fd5  push    r12
0x180057fd7  push    r13
0x180057fd9  push    r14
0x180057fdb  push    r15
0x180057fdd  lea     rbp, [rsp-21A8h]
0x180057fe5  mov     eax, 22A8h
0x180057fea  call    _alloca_probe
0x180057fef  sub     rsp, rax
0x180057ff2  mov     rax, cs:__security_cookie
0x180057ff9  xor     rax, rsp
0x180057ffc  mov     [rbp+21E0h+var_50], rax
0x180058003  mov     r15d, r9d
0x180058006  mov     [rsp+22E0h+var_22A0], r9d
0x18005800b  mov     r13, r8
0x18005800e  mov     rdi, rdx
0x180058011  mov     rsi, rcx
0x180058014  xor     r12d, r12d
0x180058017  mov     [rsp+22E0h+var_2280], r12
0x18005801c  mov     [rsp+22E0h+var_2278], r12
0x180058021  mov     [rsp+22E0h+var_2270], r12
0x180058026  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18005802b  mov     ebx, eax
0x18005802d  test    eax, eax
0x18005802f  js      loc_180058529
0x180058035  jmp     loc_1800584B0
0x18005803a  lea     rdx, aDelete_0; "Delete"
0x180058041  mov     rcx, rdi; lpString1
0x180058044  call    cs:__imp_lstrcmpiW
0x18005804b  nop     dword ptr [rax+rax+00h]
0x180058050  mov     r14d, eax
0x180058053  lea     rdx, aForceremove; "ForceRemove"
0x18005805a  mov     rcx, rdi; lpString1
0x18005805d  call    cs:__imp_lstrcmpiW
0x180058064  nop     dword ptr [rax+rax+00h]
0x180058069  test    eax, eax
0x18005806b  jz      short loc_180058076
0x18005806d  test    r14d, r14d
0x180058070  jnz     loc_180058124
0x180058076  mov     rdx, rdi; unsigned __int16 *
0x180058079  mov     rcx, rsi; this
0x18005807c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180058081  mov     ebx, eax
0x180058083  test    eax, eax
0x180058085  js      loc_180058529
0x18005808b  test    r15d, r15d
0x18005808e  jz      loc_180058124
0x180058094  mov     [rsp+22E0h+hKey], r12
0x180058099  mov     [rsp+22E0h+var_2290], r12
0x18005809e  mov     [rsp+22E0h+var_2288], r12
0x1800580a3  mov     edx, 5Ch ; '\'; unsigned __int16
0x1800580a8  mov     rcx, rdi; lpsz
0x1800580ab  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1800580b0  test    rax, rax
0x1800580b3  jnz     loc_18005851A
0x1800580b9  mov     rdx, rdi; unsigned __int16 *
0x1800580bc  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x1800580c1  test    eax, eax
0x1800580c3  jz      short loc_1800580DC
0x1800580c5  mov     [rsp+22E0h+hKey], r13
0x1800580ca  mov     rdx, rdi; unsigned __int16 *
0x1800580cd  lea     rcx, [rsp+22E0h+hKey]; this
0x1800580d2  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1800580d7  mov     [rsp+22E0h+hKey], r12
0x1800580dc  test    r14d, r14d
0x1800580df  jnz     short loc_18005811A
0x1800580e1  mov     rdx, rdi; unsigned __int16 *
0x1800580e4  mov     rcx, rsi; this
0x1800580e7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800580ec  mov     ebx, eax
0x1800580ee  test    eax, eax
0x1800580f0  js      loc_180058562
0x1800580f6  mov     rdx, rdi; unsigned __int16 *
0x1800580f9  mov     rcx, rsi; this
0x1800580fc  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180058101  mov     ebx, eax
0x180058103  test    eax, eax
0x180058105  lea     rcx, [rsp+22E0h+hKey]; this
0x18005810a  js      loc_180058567
0x180058110  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180058115  jmp     loc_180058315
0x18005811a  lea     rcx, [rsp+22E0h+hKey]; this
0x18005811f  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180058124  mov     r12d, 1
0x18005812a  lea     rdx, aNoremove; "NoRemove"
0x180058131  mov     rcx, rdi; lpString1
0x180058134  call    cs:__imp_lstrcmpiW
0x18005813b  nop     dword ptr [rax+rax+00h]
0x180058140  xor     r14d, r14d
0x180058143  test    eax, eax
0x180058145  jnz     short loc_18005815F
0x180058147  mov     r12d, r14d
0x18005814a  mov     rdx, rdi; unsigned __int16 *
0x18005814d  mov     rcx, rsi; this
0x180058150  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180058155  mov     ebx, eax
0x180058157  test    eax, eax
0x180058159  js      loc_180058529
0x18005815f  lea     rdx, aVal; "Val"
0x180058166  mov     rcx, rdi; lpString1
0x180058169  call    cs:__imp_lstrcmpiW
0x180058170  nop     dword ptr [rax+rax+00h]
0x180058175  test    eax, eax
0x180058177  jnz     loc_18005826F
0x18005817d  lea     rdx, [rbp+21E0h+ValueName]; unsigned __int16 *
0x180058184  mov     rcx, rsi; this
0x180058187  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18005818c  mov     ebx, eax
0x18005818e  test    eax, eax
0x180058190  js      loc_180058529
0x180058196  mov     rdx, rdi; unsigned __int16 *
0x180058199  mov     rcx, rsi; this
0x18005819c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800581a1  mov     ebx, eax
0x1800581a3  test    eax, eax
0x1800581a5  js      loc_180058529
0x1800581ab  cmp     word ptr [rdi], 3Dh ; '='
0x1800581af  jnz     loc_180058524
0x1800581b5  test    r15d, r15d
0x1800581b8  jz      short loc_1800581EF
0x1800581ba  xor     r12d, r12d
0x1800581bd  mov     [rsp+22E0h+var_2290], r12
0x1800581c2  mov     [rsp+22E0h+var_2288], r12
0x1800581c7  mov     [rsp+22E0h+hKey], r13
0x1800581cc  mov     r9, rdi; unsigned __int16 *
0x1800581cf  lea     r8, [rbp+21E0h+ValueName]; unsigned __int16 *
0x1800581d6  lea     rdx, [rsp+22E0h+hKey]; struct ATL::CRegKey *
0x1800581db  mov     rcx, rsi; this
0x1800581de  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1800581e3  mov     ebx, eax
0x1800581e5  mov     [rsp+22E0h+hKey], r12
0x1800581ea  jmp     loc_180058103
0x1800581ef  cmp     [rbp+21E0h+arg_20], r14d
0x1800581f6  jnz     short loc_18005825C
0x1800581f8  test    r12d, r12d
0x1800581fb  jz      short loc_18005825C
0x1800581fd  xor     r12d, r12d
0x180058200  mov     [rsp+22E0h+hKey], r12
0x180058205  mov     [rsp+22E0h+var_2290], r12
0x18005820a  mov     [rsp+22E0h+var_2288], r12
0x18005820f  mov     r9d, 20006h; unsigned int
0x180058215  xor     r8d, r8d; lpSubKey
0x180058218  mov     rdx, r13; hKey
0x18005821b  lea     rcx, [rsp+22E0h+hKey]; this
0x180058220  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180058225  test    eax, eax
0x180058227  jnz     loc_180058559
0x18005822d  lea     rdx, [rbp+21E0h+ValueName]; lpValueName
0x180058234  mov     rcx, [rsp+22E0h+hKey]; hKey
0x180058239  call    cs:__imp_RegDeleteValueW
0x180058240  nop     dword ptr [rax+rax+00h]
0x180058245  test    eax, 0FFFFFFFDh
0x18005824a  jnz     loc_180058559
0x180058250  lea     rcx, [rsp+22E0h+hKey]; this
0x180058255  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18005825a  jmp     short loc_18005825F
0x18005825c  xor     r12d, r12d
0x18005825f  mov     rdx, rdi; unsigned __int16 *
0x180058262  mov     rcx, rsi; this
0x180058265  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18005826a  jmp     loc_18005802B
0x18005826f  mov     edx, 5Ch ; '\'; unsigned __int16
0x180058274  mov     rcx, rdi; lpsz
0x180058277  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18005827c  test    rax, rax
0x18005827f  jnz     loc_180058524
0x180058285  test    r15d, r15d
0x180058288  jz      loc_180058364
0x18005828e  mov     r9d, 2001Fh; unsigned int
0x180058294  mov     r8, rdi; lpSubKey
0x180058297  mov     rdx, r13; hKey
0x18005829a  lea     rcx, [rsp+22E0h+var_2280]; this
0x18005829f  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800582a4  xor     r12d, r12d
0x1800582a7  test    eax, eax
0x1800582a9  jz      short loc_1800582DD
0x1800582ab  mov     r9d, 20019h; unsigned int
0x1800582b1  mov     r8, rdi; lpSubKey
0x1800582b4  mov     rdx, r13; hKey
0x1800582b7  lea     rcx, [rsp+22E0h+var_2280]; this
0x1800582bc  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800582c1  test    eax, eax
0x1800582c3  jz      short loc_1800582DD
0x1800582c5  mov     r8, rdi; lpSubKey
0x1800582c8  mov     rdx, r13; hKey
0x1800582cb  lea     rcx, [rsp+22E0h+var_2280]; this
0x1800582d0  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x1800582d5  test    eax, eax
0x1800582d7  jnz     loc_18005856E
0x1800582dd  mov     rdx, rdi; unsigned __int16 *
0x1800582e0  mov     rcx, rsi; this
0x1800582e3  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800582e8  mov     ebx, eax
0x1800582ea  test    eax, eax
0x1800582ec  js      loc_180058529
0x1800582f2  cmp     word ptr [rdi], 3Dh ; '='
0x1800582f6  jnz     short loc_180058315
0x1800582f8  mov     r9, rdi; unsigned __int16 *
0x1800582fb  xor     r8d, r8d; unsigned __int16 *
0x1800582fe  lea     rdx, [rsp+22E0h+var_2280]; struct ATL::CRegKey *
0x180058303  mov     rcx, rsi; this
0x180058306  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18005830b  mov     ebx, eax
0x18005830d  test    eax, eax
0x18005830f  js      loc_180058529
0x180058315  cmp     word ptr [rdi], 7Bh ; '{'
0x180058319  jnz     loc_1800584B0
0x18005831f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180058323  inc     rax
0x180058326  cmp     [rdi+rax*2], r12w
0x18005832b  jnz     short loc_180058323
0x18005832d  cmp     rax, 1
0x180058331  jnz     loc_1800584B0
0x180058337  mov     dword ptr [rsp+22E0h+var_22C0], r12d; int
0x18005833c  mov     r9d, r15d; int
0x18005833f  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x180058344  mov     rdx, rdi; unsigned __int16 *
0x180058347  mov     rcx, rsi; this
0x18005834a  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18005834f  mov     ebx, eax
0x180058351  test    eax, eax
0x180058353  js      loc_180058529
0x180058359  mov     rdx, rdi
0x18005835c  mov     rcx, rsi
0x18005835f  jmp     loc_180058026
0x180058364  cmp     [rbp+21E0h+arg_20], r14d
0x18005836b  jnz     short loc_180058388
0x18005836d  mov     r9d, 20019h; unsigned int
0x180058373  mov     r8, rdi; lpSubKey
0x180058376  mov     rdx, r13; hKey
0x180058379  lea     rcx, [rsp+22E0h+var_2280]; this
0x18005837e  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180058383  mov     r14d, eax
0x180058386  jmp     short loc_18005838E
0x180058388  mov     r14d, 2
0x18005838e  mov     r15d, 1
0x180058394  test    r14d, r14d
0x180058397  cmovz   r15d, [rbp+21E0h+arg_20]
0x18005839f  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800583a3  mov     r8, rdi
0x1800583a6  mov     edx, 104h
0x1800583ab  lea     rcx, [rbp+21E0h+var_2260]
0x1800583af  call    cs:__imp__o_wcsncpy_s
0x1800583b6  nop     dword ptr [rax+rax+00h]
0x1800583bb  mov     ecx, eax; int
0x1800583bd  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800583c2  mov     rdx, rdi; unsigned __int16 *
0x1800583c5  mov     rcx, rsi; this
0x1800583c8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800583cd  mov     ebx, eax
0x1800583cf  test    eax, eax
0x1800583d1  js      loc_180058529
0x1800583d7  mov     rdx, rdi; unsigned __int16 *
0x1800583da  mov     rcx, rsi; this
0x1800583dd  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800583e2  mov     ebx, eax
0x1800583e4  xor     ecx, ecx; this
0x1800583e6  test    eax, eax
0x1800583e8  js      loc_180058529
0x1800583ee  cmp     word ptr [rdi], 7Bh ; '{'
0x1800583f2  jnz     short loc_180058448
0x1800583f4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800583f8  inc     rax
0x1800583fb  cmp     [rdi+rax*2], cx
0x1800583ff  jnz     short loc_1800583F8
0x180058401  cmp     rax, 1
0x180058405  jnz     short loc_180058448
0x180058407  mov     dword ptr [rsp+22E0h+var_22C0], r15d; int
0x18005840c  xor     r9d, r9d; int
0x18005840f  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x180058414  mov     rdx, rdi; unsigned __int16 *
0x180058417  mov     rcx, rsi; this
0x18005841a  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18005841f  mov     ebx, eax
0x180058421  test    eax, eax
0x180058423  jns     short loc_18005842E
0x180058425  test    r15d, r15d
0x180058428  jz      loc_180058529
0x18005842e  mov     rdx, rdi; unsigned __int16 *
0x180058431  mov     rcx, rsi; this
0x180058434  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180058439  mov     ebx, eax
0x18005843b  xor     r15d, r15d
0x18005843e  test    eax, eax
0x180058440  js      loc_180058529
0x180058446  jmp     short loc_18005844B
0x180058448  xor     r15d, r15d
0x18005844b  cmp     r14d, 2
0x18005844f  jz      short loc_1800584A8
0x180058451  test    r14d, r14d
0x180058454  jz      short loc_180058471
0x180058456  xor     r12d, r12d
0x180058459  cmp     [rbp+21E0h+arg_20], r12d
0x180058460  jnz     short loc_1800584AB
0x180058462  mov     ecx, r14d; unsigned int
0x180058465  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18005846a  mov     ebx, eax
  ... truncated ...
```
