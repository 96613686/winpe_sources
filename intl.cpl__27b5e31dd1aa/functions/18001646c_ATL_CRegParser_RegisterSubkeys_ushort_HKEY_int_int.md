# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18001646c`
- end: `0x1800169ed`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1409`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001614c`
- `0x18001646c`

## callees

- `0x18001399c`
- `0x180014010`
- `0x180014080`
- `0x18001423c`
- `0x1800143d4`
- `0x180014400`
- `0x180014aac`
- `0x18001548c`
- `0x180015890`
- `0x180015d5c`
- `0x180016038`
- `0x18001646c`
- `0x180016c70`
- `0x18001710c`
- `0x18002a150`
- `0x18002a210`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18001682d`
- `msvcrt!wcsncpy_s` at `0x18001682d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800166bd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800166bd`
- `KERNEL32!lstrcmpiW` at `0x1800164e0`
- `KERNEL32!lstrcmpiW` at `0x1800164f3`
- `KERNEL32!lstrcmpiW` at `0x1800165c4`
- `KERNEL32!lstrcmpiW` at `0x1800165f3`
- `KERNEL32!lstrcmpiW` at `0x1800164e0`
- `KERNEL32!lstrcmpiW` at `0x1800164f3`
- `KERNEL32!lstrcmpiW` at `0x1800165c4`
- `KERNEL32!lstrcmpiW` at `0x1800165f3`

## string_xrefs

- `0x1800164e9`: `ForceRemove`
- `0x1800165ba`: `NoRemove`
- `0x1800164d6`: `Delete`

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
  unsigned int v15; // eax
  unsigned __int16 *v16; // r9
  unsigned int v17; // eax
  __int64 v18; // rax
  int v19; // r14d
  int v20; // r15d
  errno_t v21; // eax
  ATL::CRegParser *v22; // rcx
  __int64 v23; // rax
  unsigned int v24; // ecx
  int HasSubKeys; // r14d
  unsigned int v27; // [rsp+20h] [rbp-E0h]
  unsigned int v28; // [rsp+28h] [rbp-D8h]
  struct _SECURITY_ATTRIBUTES *v29; // [rsp+30h] [rbp-D0h]
  unsigned int *v30; // [rsp+38h] [rbp-C8h]
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v33; // [rsp+50h] [rbp-B0h]
  __int64 v34; // [rsp+58h] [rbp-A8h]
  HKEY v35[4]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t Destination[264]; // [rsp+80h] [rbp-80h] BYREF
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
      v21 = wcsncpy_s(Destination, 0x104u, v7, 0xFFFFFFFFFFFFFFFFuLL);
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
          if ( ATL::CRegParser::CanForceRemoveKey(v22, Destination) && v14 )
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v35, Destination);
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
            v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, Destination);
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
0x18001646c  push    rbp
0x18001646e  push    rbx
0x18001646f  push    rsi
0x180016470  push    rdi
0x180016471  push    r12
0x180016473  push    r13
0x180016475  push    r14
0x180016477  push    r15
0x180016479  lea     rbp, [rsp-21A8h]
0x180016481  mov     eax, 22A8h
0x180016486  call    _alloca_probe
0x18001648b  sub     rsp, rax
0x18001648e  mov     rax, cs:__security_cookie
0x180016495  xor     rax, rsp
0x180016498  mov     [rbp+21E0h+var_50], rax
0x18001649f  mov     r15d, r9d
0x1800164a2  mov     [rsp+22E0h+var_22A0], r9d
0x1800164a7  mov     r13, r8
0x1800164aa  mov     rdi, rdx
0x1800164ad  mov     rsi, rcx
0x1800164b0  xor     r12d, r12d
0x1800164b3  mov     [rsp+22E0h+var_2280], r12
0x1800164b8  mov     [rsp+22E0h+var_2278], r12
0x1800164bd  mov     [rsp+22E0h+var_2270], r12
0x1800164c2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800164c7  mov     ebx, eax
0x1800164c9  test    eax, eax
0x1800164cb  js      loc_1800169A1
0x1800164d1  jmp     loc_180016928
0x1800164d6  lea     rdx, aDelete; "Delete"
0x1800164dd  mov     rcx, rdi; lpString1
0x1800164e0  call    cs:__imp_lstrcmpiW
0x1800164e6  mov     r14d, eax
0x1800164e9  lea     rdx, aForceremove; "ForceRemove"
0x1800164f0  mov     rcx, rdi; lpString1
0x1800164f3  call    cs:__imp_lstrcmpiW
0x1800164f9  test    eax, eax
0x1800164fb  jz      short loc_180016506
0x1800164fd  test    r14d, r14d
0x180016500  jnz     loc_1800165B4
0x180016506  mov     rdx, rdi; unsigned __int16 *
0x180016509  mov     rcx, rsi; this
0x18001650c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180016511  mov     ebx, eax
0x180016513  test    eax, eax
0x180016515  js      loc_1800169A1
0x18001651b  test    r15d, r15d
0x18001651e  jz      loc_1800165B4
0x180016524  mov     [rsp+22E0h+hKey], r12
0x180016529  mov     [rsp+22E0h+var_2290], r12
0x18001652e  mov     [rsp+22E0h+var_2288], r12
0x180016533  mov     edx, 5Ch ; '\'; unsigned __int16
0x180016538  mov     rcx, rdi; lpsz
0x18001653b  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180016540  test    rax, rax
0x180016543  jnz     loc_180016992
0x180016549  mov     rdx, rdi; unsigned __int16 *
0x18001654c  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x180016551  test    eax, eax
0x180016553  jz      short loc_18001656C
0x180016555  mov     [rsp+22E0h+hKey], r13
0x18001655a  mov     rdx, rdi; unsigned __int16 *
0x18001655d  lea     rcx, [rsp+22E0h+hKey]; this
0x180016562  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180016567  mov     [rsp+22E0h+hKey], r12
0x18001656c  test    r14d, r14d
0x18001656f  jnz     short loc_1800165AA
0x180016571  mov     rdx, rdi; unsigned __int16 *
0x180016574  mov     rcx, rsi; this
0x180016577  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001657c  mov     ebx, eax
0x18001657e  test    eax, eax
0x180016580  js      loc_1800169D9
0x180016586  mov     rdx, rdi; unsigned __int16 *
0x180016589  mov     rcx, rsi; this
0x18001658c  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180016591  mov     ebx, eax
0x180016593  test    eax, eax
0x180016595  lea     rcx, [rsp+22E0h+hKey]; this
0x18001659a  js      loc_1800169DE
0x1800165a0  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800165a5  jmp     loc_180016793
0x1800165aa  lea     rcx, [rsp+22E0h+hKey]; this
0x1800165af  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800165b4  mov     r12d, 1
0x1800165ba  lea     rdx, aNoremove; "NoRemove"
0x1800165c1  mov     rcx, rdi; lpString1
0x1800165c4  call    cs:__imp_lstrcmpiW
0x1800165ca  xor     r14d, r14d
0x1800165cd  test    eax, eax
0x1800165cf  jnz     short loc_1800165E9
0x1800165d1  mov     r12d, r14d
0x1800165d4  mov     rdx, rdi; unsigned __int16 *
0x1800165d7  mov     rcx, rsi; this
0x1800165da  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800165df  mov     ebx, eax
0x1800165e1  test    eax, eax
0x1800165e3  js      loc_1800169A1
0x1800165e9  lea     rdx, aVal; "Val"
0x1800165f0  mov     rcx, rdi; lpString1
0x1800165f3  call    cs:__imp_lstrcmpiW
0x1800165f9  test    eax, eax
0x1800165fb  jnz     loc_1800166ED
0x180016601  lea     rdx, [rbp+21E0h+ValueName]; unsigned __int16 *
0x180016608  mov     rcx, rsi; this
0x18001660b  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180016610  mov     ebx, eax
0x180016612  test    eax, eax
0x180016614  js      loc_1800169A1
0x18001661a  mov     rdx, rdi; unsigned __int16 *
0x18001661d  mov     rcx, rsi; this
0x180016620  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180016625  mov     ebx, eax
0x180016627  test    eax, eax
0x180016629  js      loc_1800169A1
0x18001662f  cmp     word ptr [rdi], 3Dh ; '='
0x180016633  jnz     loc_18001699C
0x180016639  test    r15d, r15d
0x18001663c  jz      short loc_180016673
0x18001663e  xor     r12d, r12d
0x180016641  mov     [rsp+22E0h+var_2290], r12
0x180016646  mov     [rsp+22E0h+var_2288], r12
0x18001664b  mov     [rsp+22E0h+hKey], r13
0x180016650  mov     r9, rdi; unsigned __int16 *
0x180016653  lea     r8, [rbp+21E0h+ValueName]; unsigned __int16 *
0x18001665a  lea     rdx, [rsp+22E0h+hKey]; struct ATL::CRegKey *
0x18001665f  mov     rcx, rsi; this
0x180016662  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180016667  mov     ebx, eax
0x180016669  mov     [rsp+22E0h+hKey], r12
0x18001666e  jmp     loc_180016593
0x180016673  cmp     [rbp+21E0h+arg_20], r14d
0x18001667a  jnz     short loc_1800166DA
0x18001667c  test    r12d, r12d
0x18001667f  jz      short loc_1800166DA
0x180016681  xor     r12d, r12d
0x180016684  mov     [rsp+22E0h+hKey], r12
0x180016689  mov     [rsp+22E0h+var_2290], r12
0x18001668e  mov     [rsp+22E0h+var_2288], r12
0x180016693  mov     r9d, 20006h; unsigned int
0x180016699  xor     r8d, r8d; lpSubKey
0x18001669c  mov     rdx, r13; hKey
0x18001669f  lea     rcx, [rsp+22E0h+hKey]; this
0x1800166a4  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800166a9  test    eax, eax
0x1800166ab  jnz     loc_1800169D0
0x1800166b1  lea     rdx, [rbp+21E0h+ValueName]; lpValueName
0x1800166b8  mov     rcx, [rsp+22E0h+hKey]; hKey
0x1800166bd  call    cs:__imp_RegDeleteValueW
0x1800166c3  test    eax, 0FFFFFFFDh
0x1800166c8  jnz     loc_1800169D0
0x1800166ce  lea     rcx, [rsp+22E0h+hKey]; this
0x1800166d3  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800166d8  jmp     short loc_1800166DD
0x1800166da  xor     r12d, r12d
0x1800166dd  mov     rdx, rdi; unsigned __int16 *
0x1800166e0  mov     rcx, rsi; this
0x1800166e3  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800166e8  jmp     loc_1800164C7
0x1800166ed  mov     edx, 5Ch ; '\'; unsigned __int16
0x1800166f2  mov     rcx, rdi; lpsz
0x1800166f5  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1800166fa  test    rax, rax
0x1800166fd  jnz     loc_18001699C
0x180016703  test    r15d, r15d
0x180016706  jz      loc_1800167E2
0x18001670c  mov     r9d, 2001Fh; unsigned int
0x180016712  mov     r8, rdi; lpSubKey
0x180016715  mov     rdx, r13; hKey
0x180016718  lea     rcx, [rsp+22E0h+var_2280]; this
0x18001671d  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180016722  xor     r12d, r12d
0x180016725  test    eax, eax
0x180016727  jz      short loc_18001675B
0x180016729  mov     r9d, 20019h; unsigned int
0x18001672f  mov     r8, rdi; lpSubKey
0x180016732  mov     rdx, r13; hKey
0x180016735  lea     rcx, [rsp+22E0h+var_2280]; this
0x18001673a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001673f  test    eax, eax
0x180016741  jz      short loc_18001675B
0x180016743  mov     r8, rdi; lpSubKey
0x180016746  mov     rdx, r13; hKey
0x180016749  lea     rcx, [rsp+22E0h+var_2280]; this
0x18001674e  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x180016753  test    eax, eax
0x180016755  jnz     loc_1800169E5
0x18001675b  mov     rdx, rdi; unsigned __int16 *
0x18001675e  mov     rcx, rsi; this
0x180016761  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180016766  mov     ebx, eax
0x180016768  test    eax, eax
0x18001676a  js      loc_1800169A1
0x180016770  cmp     word ptr [rdi], 3Dh ; '='
0x180016774  jnz     short loc_180016793
0x180016776  mov     r9, rdi; unsigned __int16 *
0x180016779  xor     r8d, r8d; unsigned __int16 *
0x18001677c  lea     rdx, [rsp+22E0h+var_2280]; struct ATL::CRegKey *
0x180016781  mov     rcx, rsi; this
0x180016784  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180016789  mov     ebx, eax
0x18001678b  test    eax, eax
0x18001678d  js      loc_1800169A1
0x180016793  cmp     word ptr [rdi], 7Bh ; '{'
0x180016797  jnz     loc_180016928
0x18001679d  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800167a1  inc     rax
0x1800167a4  cmp     [rdi+rax*2], r12w
0x1800167a9  jnz     short loc_1800167A1
0x1800167ab  cmp     rax, 1
0x1800167af  jnz     loc_180016928
0x1800167b5  mov     [rsp+22E0h+var_22C0], r12d; int
0x1800167ba  mov     r9d, r15d; int
0x1800167bd  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x1800167c2  mov     rdx, rdi; unsigned __int16 *
0x1800167c5  mov     rcx, rsi; this
0x1800167c8  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800167cd  mov     ebx, eax
0x1800167cf  test    eax, eax
0x1800167d1  js      loc_1800169A1
0x1800167d7  mov     rdx, rdi
0x1800167da  mov     rcx, rsi
0x1800167dd  jmp     loc_1800164C2
0x1800167e2  cmp     [rbp+21E0h+arg_20], r14d
0x1800167e9  jnz     short loc_180016806
0x1800167eb  mov     r9d, 20019h; unsigned int
0x1800167f1  mov     r8, rdi; lpSubKey
0x1800167f4  mov     rdx, r13; hKey
0x1800167f7  lea     rcx, [rsp+22E0h+var_2280]; this
0x1800167fc  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180016801  mov     r14d, eax
0x180016804  jmp     short loc_18001680C
0x180016806  mov     r14d, 2
0x18001680c  mov     r15d, 1
0x180016812  test    r14d, r14d
0x180016815  cmovz   r15d, [rbp+21E0h+arg_20]
0x18001681d  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180016821  mov     r8, rdi; Source
0x180016824  mov     edx, 104h; SizeInWords
0x180016829  lea     rcx, [rbp+21E0h+Destination]; Destination
0x18001682d  call    cs:__imp_wcsncpy_s
0x180016833  mov     ecx, eax; int
0x180016835  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001683a  mov     rdx, rdi; unsigned __int16 *
0x18001683d  mov     rcx, rsi; this
0x180016840  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180016845  mov     ebx, eax
0x180016847  test    eax, eax
0x180016849  js      loc_1800169A1
0x18001684f  mov     rdx, rdi; unsigned __int16 *
0x180016852  mov     rcx, rsi; this
0x180016855  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18001685a  mov     ebx, eax
0x18001685c  xor     ecx, ecx; this
0x18001685e  test    eax, eax
0x180016860  js      loc_1800169A1
0x180016866  cmp     word ptr [rdi], 7Bh ; '{'
0x18001686a  jnz     short loc_1800168C0
0x18001686c  or      rax, 0FFFFFFFFFFFFFFFFh
0x180016870  inc     rax
0x180016873  cmp     [rdi+rax*2], cx
0x180016877  jnz     short loc_180016870
0x180016879  cmp     rax, 1
0x18001687d  jnz     short loc_1800168C0
0x18001687f  mov     [rsp+22E0h+var_22C0], r15d; int
0x180016884  xor     r9d, r9d; int
0x180016887  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x18001688c  mov     rdx, rdi; unsigned __int16 *
0x18001688f  mov     rcx, rsi; this
0x180016892  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180016897  mov     ebx, eax
0x180016899  test    eax, eax
0x18001689b  jns     short loc_1800168A6
0x18001689d  test    r15d, r15d
0x1800168a0  jz      loc_1800169A1
0x1800168a6  mov     rdx, rdi; unsigned __int16 *
0x1800168a9  mov     rcx, rsi; this
0x1800168ac  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800168b1  mov     ebx, eax
0x1800168b3  xor     r15d, r15d
0x1800168b6  test    eax, eax
0x1800168b8  js      loc_1800169A1
0x1800168be  jmp     short loc_1800168C3
0x1800168c0  xor     r15d, r15d
0x1800168c3  cmp     r14d, 2
0x1800168c7  jz      short loc_180016920
0x1800168c9  test    r14d, r14d
0x1800168cc  jz      short loc_1800168E9
0x1800168ce  xor     r12d, r12d
0x1800168d1  cmp     [rbp+21E0h+arg_20], r12d
0x1800168d8  jnz     short loc_180016923
0x1800168da  mov     ecx, r14d; unsigned int
0x1800168dd  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800168e2  mov     ebx, eax
0x1800168e4  jmp     loc_1800169A1
0x1800168e9  cmp     [rbp+21E0h+arg_20], r15d
0x1800168f0  jz      short loc_180016934
0x1800168f2  mov     rdx, [rsp+22E0h+var_2280]; HKEY
0x1800168f7  call    ?HasSubKeys@CRegParser@ATL@@IEAAHPEAUHKEY__@@@Z; ATL::CRegParser::HasSubKeys(HKEY__ *)
0x1800168fc  test    eax, eax
  ... truncated ...
```
