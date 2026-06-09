# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18013674c`
- end: `0x180136ce9`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1437`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18013640c`
- `0x18013674c`

## callees

- `0x180006350`
- `0x180134038`
- `0x1801345ac`
- `0x1801345c4`
- `0x180134d50`
- `0x180134d84`
- `0x180134fac`
- `0x180135534`
- `0x180135db4`
- `0x180135f58`
- `0x1801362ec`
- `0x18013674c`
- `0x180136f20`
- `0x180136ff8`
- `0x1801fa390`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180136b29`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180136b29`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1801369b3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1801369b3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1801367c0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1801367d9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1801368b0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1801368e5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1801367c0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1801367d9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1801368b0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1801368e5`

## string_xrefs

- `0x1801367cf`: `ForceRemove`
- `0x1801368a6`: `NoRemove`
- `0x1801367b6`: `Delete`

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
  unsigned int v15; // eax
  unsigned __int16 *v16; // r9
  unsigned int v17; // eax
  __int64 v18; // rax
  int v19; // r14d
  int v20; // r15d
  ATL::CRegParser *v21; // rcx
  __int64 v22; // rax
  unsigned int v23; // ecx
  int HasSubKeys; // r14d
  __int64 v26; // [rsp+20h] [rbp-E0h]
  unsigned int v27; // [rsp+28h] [rbp-D8h]
  struct _SECURITY_ATTRIBUTES *v28; // [rsp+30h] [rbp-D0h]
  unsigned int *v29; // [rsp+38h] [rbp-C8h]
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v32; // [rsp+50h] [rbp-B0h]
  __int64 v33; // [rsp+58h] [rbp-A8h]
  HKEY v34[4]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v35[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ValueName[4096]; // [rsp+290h] [rbp+190h] BYREF

  v5 = a4;
  v7 = a2;
  v8 = this;
  memset(v34, 0, 24);
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
        v32 = 0;
        v33 = 0;
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
LABEL_15:
        v10 = v13;
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
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v34[0], v5, 0);
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
        if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v34, a3, v7, 0x2001Fu)
          || !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v34, a3, v7, 0x20019u)
          || (v17 = ATL::CRegKey::Create((ATL::CRegKey *)v34, a3, v7, v16, v26, v27, v28, v29)) == 0 )
        {
          v10 = ATL::CRegParser::NextToken(v8, v7);
          if ( v10 < 0 )
            goto LABEL_80;
          if ( *v7 == 61 )
          {
            v10 = ATL::CRegParser::AddValue(v8, v34, 0, v7);
            if ( v10 < 0 )
              goto LABEL_80;
          }
          goto LABEL_40;
        }
LABEL_83:
        v23 = v17;
LABEL_64:
        v10 = ATL::AtlHresultFromWin32(v23);
        goto LABEL_80;
      }
      if ( a5 )
        v19 = 2;
      else
        v19 = ATL::CRegKey::Open((ATL::CRegKey *)v34, a3, v7, 0x20019u);
      v20 = 1;
      if ( !v19 )
        v20 = a5;
      _o_wcsncpy_s(v35, 260, v7, -1, v26);
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
          v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v34[0], 0, v20);
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
            v23 = v19;
            goto LABEL_64;
          }
        }
        else if ( a5 && ATL::CRegParser::HasSubKeys(v21, v34[0]) )
        {
          if ( ATL::CRegParser::CanForceRemoveKey(v21, v35) && v14 )
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v34, v35);
        }
        else
        {
          HasSubKeys = ATL::CRegParser::HasSubKeys(v21, v34[0]);
          v17 = ATL::CRegKey::Close((ATL::CRegKey *)v34);
          if ( v17 )
            goto LABEL_83;
          if ( v14 && !HasSubKeys )
          {
            v32 = 0;
            v33 = 0;
            hKey = a3;
            v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, v35);
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
      v32 = 0;
      v33 = 0;
      hKey = a3;
      v13 = ATL::CRegParser::AddValue(v8, &hKey, ValueName, v7);
      hKey = 0;
      goto LABEL_15;
    }
    if ( a5 || !v14 )
      goto LABEL_31;
    hKey = 0;
    v32 = 0;
    v33 = 0;
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
  ATL::CRegKey::Close((ATL::CRegKey *)v34);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18013674c  push    rbp
0x18013674e  push    rbx
0x18013674f  push    rsi
0x180136750  push    rdi
0x180136751  push    r12
0x180136753  push    r13
0x180136755  push    r14
0x180136757  push    r15
0x180136759  lea     rbp, [rsp-21A8h]
0x180136761  mov     eax, 22A8h
0x180136766  call    _alloca_probe
0x18013676b  sub     rsp, rax
0x18013676e  mov     rax, cs:__security_cookie
0x180136775  xor     rax, rsp
0x180136778  mov     [rbp+21E0h+var_50], rax
0x18013677f  mov     r15d, r9d
0x180136782  mov     [rsp+22E0h+var_22A0], r9d
0x180136787  mov     r13, r8
0x18013678a  mov     rdi, rdx
0x18013678d  mov     rsi, rcx
0x180136790  xor     r12d, r12d
0x180136793  mov     [rsp+22E0h+var_2280], r12
0x180136798  mov     [rsp+22E0h+var_2278], r12
0x18013679d  mov     [rsp+22E0h+var_2270], r12
0x1801367a2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1801367a7  mov     ebx, eax
0x1801367a9  test    eax, eax
0x1801367ab  js      loc_180136C9C
0x1801367b1  jmp     loc_180136C23
0x1801367b6  lea     rdx, aDelete; "Delete"
0x1801367bd  mov     rcx, rdi; lpString1
0x1801367c0  call    cs:__imp_lstrcmpiW
0x1801367c7  nop     dword ptr [rax+rax+00h]
0x1801367cc  mov     r14d, eax
0x1801367cf  lea     rdx, aForceremove; "ForceRemove"
0x1801367d6  mov     rcx, rdi; lpString1
0x1801367d9  call    cs:__imp_lstrcmpiW
0x1801367e0  nop     dword ptr [rax+rax+00h]
0x1801367e5  test    eax, eax
0x1801367e7  jz      short loc_1801367F2
0x1801367e9  test    r14d, r14d
0x1801367ec  jnz     loc_1801368A0
0x1801367f2  mov     rdx, rdi; unsigned __int16 *
0x1801367f5  mov     rcx, rsi; this
0x1801367f8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1801367fd  mov     ebx, eax
0x1801367ff  test    eax, eax
0x180136801  js      loc_180136C9C
0x180136807  test    r15d, r15d
0x18013680a  jz      loc_1801368A0
0x180136810  mov     [rsp+22E0h+hKey], r12
0x180136815  mov     [rsp+22E0h+var_2290], r12
0x18013681a  mov     [rsp+22E0h+var_2288], r12
0x18013681f  mov     edx, 5Ch ; '\'; unsigned __int16
0x180136824  mov     rcx, rdi; lpsz
0x180136827  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18013682c  test    rax, rax
0x18013682f  jnz     loc_180136C8D
0x180136835  mov     rdx, rdi; unsigned __int16 *
0x180136838  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x18013683d  test    eax, eax
0x18013683f  jz      short loc_180136858
0x180136841  mov     [rsp+22E0h+hKey], r13
0x180136846  mov     rdx, rdi; unsigned __int16 *
0x180136849  lea     rcx, [rsp+22E0h+hKey]; this
0x18013684e  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180136853  mov     [rsp+22E0h+hKey], r12
0x180136858  test    r14d, r14d
0x18013685b  jnz     short loc_180136896
0x18013685d  mov     rdx, rdi; unsigned __int16 *
0x180136860  mov     rcx, rsi; this
0x180136863  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180136868  mov     ebx, eax
0x18013686a  test    eax, eax
0x18013686c  js      loc_180136CD5
0x180136872  mov     rdx, rdi; unsigned __int16 *
0x180136875  mov     rcx, rsi; this
0x180136878  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18013687d  test    eax, eax
0x18013687f  lea     rcx, [rsp+22E0h+hKey]; this
0x180136884  mov     ebx, eax
0x180136886  js      loc_180136CDA
0x18013688c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180136891  jmp     loc_180136A8F
0x180136896  lea     rcx, [rsp+22E0h+hKey]; this
0x18013689b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1801368a0  mov     r12d, 1
0x1801368a6  lea     rdx, aNoremove; "NoRemove"
0x1801368ad  mov     rcx, rdi; lpString1
0x1801368b0  call    cs:__imp_lstrcmpiW
0x1801368b7  nop     dword ptr [rax+rax+00h]
0x1801368bc  xor     r14d, r14d
0x1801368bf  test    eax, eax
0x1801368c1  jnz     short loc_1801368DB
0x1801368c3  mov     r12d, r14d
0x1801368c6  mov     rdx, rdi; unsigned __int16 *
0x1801368c9  mov     rcx, rsi; this
0x1801368cc  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1801368d1  mov     ebx, eax
0x1801368d3  test    eax, eax
0x1801368d5  js      loc_180136C9C
0x1801368db  lea     rdx, aVal; "Val"
0x1801368e2  mov     rcx, rdi; lpString1
0x1801368e5  call    cs:__imp_lstrcmpiW
0x1801368ec  nop     dword ptr [rax+rax+00h]
0x1801368f1  test    eax, eax
0x1801368f3  jnz     loc_1801369E9
0x1801368f9  lea     rdx, [rbp+21E0h+ValueName]; unsigned __int16 *
0x180136900  mov     rcx, rsi; this
0x180136903  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180136908  mov     ebx, eax
0x18013690a  test    eax, eax
0x18013690c  js      loc_180136C9C
0x180136912  mov     rdx, rdi; unsigned __int16 *
0x180136915  mov     rcx, rsi; this
0x180136918  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18013691d  mov     ebx, eax
0x18013691f  test    eax, eax
0x180136921  js      loc_180136C9C
0x180136927  cmp     word ptr [rdi], 3Dh ; '='
0x18013692b  jnz     loc_180136C97
0x180136931  test    r15d, r15d
0x180136934  jz      short loc_180136969
0x180136936  xor     r12d, r12d
0x180136939  mov     [rsp+22E0h+var_2290], r12
0x18013693e  mov     [rsp+22E0h+var_2288], r12
0x180136943  mov     [rsp+22E0h+hKey], r13
0x180136948  mov     r9, rdi; unsigned __int16 *
0x18013694b  lea     r8, [rbp+21E0h+ValueName]; unsigned __int16 *
0x180136952  lea     rdx, [rsp+22E0h+hKey]; struct ATL::CRegKey *
0x180136957  mov     rcx, rsi; this
0x18013695a  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18013695f  mov     [rsp+22E0h+hKey], r12
0x180136964  jmp     loc_18013687D
0x180136969  cmp     [rbp+21E0h+arg_20], r14d
0x180136970  jnz     short loc_1801369D6
0x180136972  test    r12d, r12d
0x180136975  jz      short loc_1801369D6
0x180136977  xor     r12d, r12d
0x18013697a  mov     [rsp+22E0h+hKey], r12
0x18013697f  mov     [rsp+22E0h+var_2290], r12
0x180136984  mov     [rsp+22E0h+var_2288], r12
0x180136989  mov     r9d, 20006h; unsigned int
0x18013698f  xor     r8d, r8d; lpSubKey
0x180136992  mov     rdx, r13; hKey
0x180136995  lea     rcx, [rsp+22E0h+hKey]; this
0x18013699a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18013699f  test    eax, eax
0x1801369a1  jnz     loc_180136CCC
0x1801369a7  lea     rdx, [rbp+21E0h+ValueName]; lpValueName
0x1801369ae  mov     rcx, [rsp+22E0h+hKey]; hKey
0x1801369b3  call    cs:__imp_RegDeleteValueW
0x1801369ba  nop     dword ptr [rax+rax+00h]
0x1801369bf  test    eax, 0FFFFFFFDh
0x1801369c4  jnz     loc_180136CCC
0x1801369ca  lea     rcx, [rsp+22E0h+hKey]; this
0x1801369cf  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1801369d4  jmp     short loc_1801369D9
0x1801369d6  xor     r12d, r12d
0x1801369d9  mov     rdx, rdi; unsigned __int16 *
0x1801369dc  mov     rcx, rsi; this
0x1801369df  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1801369e4  jmp     loc_1801367A7
0x1801369e9  mov     edx, 5Ch ; '\'; unsigned __int16
0x1801369ee  mov     rcx, rdi; lpsz
0x1801369f1  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1801369f6  test    rax, rax
0x1801369f9  jnz     loc_180136C97
0x1801369ff  test    r15d, r15d
0x180136a02  jz      loc_180136ADE
0x180136a08  mov     r9d, 2001Fh; unsigned int
0x180136a0e  mov     r8, rdi; lpSubKey
0x180136a11  mov     rdx, r13; hKey
0x180136a14  lea     rcx, [rsp+22E0h+var_2280]; this
0x180136a19  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180136a1e  xor     r12d, r12d
0x180136a21  test    eax, eax
0x180136a23  jz      short loc_180136A57
0x180136a25  mov     r9d, 20019h; unsigned int
0x180136a2b  mov     r8, rdi; lpSubKey
0x180136a2e  mov     rdx, r13; hKey
0x180136a31  lea     rcx, [rsp+22E0h+var_2280]; this
0x180136a36  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180136a3b  test    eax, eax
0x180136a3d  jz      short loc_180136A57
0x180136a3f  mov     r8, rdi; lpSubKey
0x180136a42  mov     rdx, r13; hKey
0x180136a45  lea     rcx, [rsp+22E0h+var_2280]; this
0x180136a4a  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x180136a4f  test    eax, eax
0x180136a51  jnz     loc_180136CE1
0x180136a57  mov     rdx, rdi; unsigned __int16 *
0x180136a5a  mov     rcx, rsi; this
0x180136a5d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180136a62  mov     ebx, eax
0x180136a64  test    eax, eax
0x180136a66  js      loc_180136C9C
0x180136a6c  cmp     word ptr [rdi], 3Dh ; '='
0x180136a70  jnz     short loc_180136A8F
0x180136a72  mov     r9, rdi; unsigned __int16 *
0x180136a75  xor     r8d, r8d; unsigned __int16 *
0x180136a78  lea     rdx, [rsp+22E0h+var_2280]; struct ATL::CRegKey *
0x180136a7d  mov     rcx, rsi; this
0x180136a80  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180136a85  mov     ebx, eax
0x180136a87  test    eax, eax
0x180136a89  js      loc_180136C9C
0x180136a8f  cmp     word ptr [rdi], 7Bh ; '{'
0x180136a93  jnz     loc_180136C23
0x180136a99  or      rax, 0FFFFFFFFFFFFFFFFh
0x180136a9d  inc     rax
0x180136aa0  cmp     [rdi+rax*2], r12w
0x180136aa5  jnz     short loc_180136A9D
0x180136aa7  cmp     rax, 1
0x180136aab  jnz     loc_180136C23
0x180136ab1  mov     dword ptr [rsp+22E0h+var_22C0], r12d; int
0x180136ab6  mov     r9d, r15d; int
0x180136ab9  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x180136abe  mov     rdx, rdi; unsigned __int16 *
0x180136ac1  mov     rcx, rsi; this
0x180136ac4  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180136ac9  mov     ebx, eax
0x180136acb  test    eax, eax
0x180136acd  js      loc_180136C9C
0x180136ad3  mov     rdx, rdi
0x180136ad6  mov     rcx, rsi
0x180136ad9  jmp     loc_1801367A2
0x180136ade  cmp     [rbp+21E0h+arg_20], r14d
0x180136ae5  jnz     short loc_180136B02
0x180136ae7  mov     r9d, 20019h; unsigned int
0x180136aed  mov     r8, rdi; lpSubKey
0x180136af0  mov     rdx, r13; hKey
0x180136af3  lea     rcx, [rsp+22E0h+var_2280]; this
0x180136af8  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180136afd  mov     r14d, eax
0x180136b00  jmp     short loc_180136B08
0x180136b02  mov     r14d, 2
0x180136b08  mov     r15d, 1
0x180136b0e  test    r14d, r14d
0x180136b11  cmovz   r15d, [rbp+21E0h+arg_20]
0x180136b19  or      r9, 0FFFFFFFFFFFFFFFFh
0x180136b1d  mov     r8, rdi
0x180136b20  mov     edx, 104h
0x180136b25  lea     rcx, [rbp+21E0h+var_2260]
0x180136b29  call    cs:__imp__o_wcsncpy_s
0x180136b30  nop     dword ptr [rax+rax+00h]
0x180136b35  mov     rdx, rdi; unsigned __int16 *
0x180136b38  mov     rcx, rsi; this
0x180136b3b  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180136b40  mov     ebx, eax
0x180136b42  test    eax, eax
0x180136b44  js      loc_180136C9C
0x180136b4a  mov     rdx, rdi; unsigned __int16 *
0x180136b4d  mov     rcx, rsi; this
0x180136b50  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180136b55  mov     ebx, eax
0x180136b57  xor     ecx, ecx; this
0x180136b59  test    eax, eax
0x180136b5b  js      loc_180136C9C
0x180136b61  cmp     word ptr [rdi], 7Bh ; '{'
0x180136b65  jnz     short loc_180136BBB
0x180136b67  or      rax, 0FFFFFFFFFFFFFFFFh
0x180136b6b  inc     rax
0x180136b6e  cmp     [rdi+rax*2], cx
0x180136b72  jnz     short loc_180136B6B
0x180136b74  cmp     rax, 1
0x180136b78  jnz     short loc_180136BBB
0x180136b7a  mov     dword ptr [rsp+22E0h+var_22C0], r15d; int
0x180136b7f  xor     r9d, r9d; int
0x180136b82  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x180136b87  mov     rdx, rdi; unsigned __int16 *
0x180136b8a  mov     rcx, rsi; this
0x180136b8d  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180136b92  mov     ebx, eax
0x180136b94  test    eax, eax
0x180136b96  jns     short loc_180136BA1
0x180136b98  test    r15d, r15d
0x180136b9b  jz      loc_180136C9C
0x180136ba1  mov     rdx, rdi; unsigned __int16 *
0x180136ba4  mov     rcx, rsi; this
0x180136ba7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180136bac  mov     ebx, eax
0x180136bae  xor     r15d, r15d
0x180136bb1  test    eax, eax
0x180136bb3  js      loc_180136C9C
0x180136bb9  jmp     short loc_180136BBE
0x180136bbb  xor     r15d, r15d
0x180136bbe  cmp     r14d, 2
0x180136bc2  jz      short loc_180136C1B
0x180136bc4  test    r14d, r14d
0x180136bc7  jz      short loc_180136BE4
0x180136bc9  xor     r12d, r12d
0x180136bcc  cmp     [rbp+21E0h+arg_20], r12d
0x180136bd3  jnz     short loc_180136C1E
0x180136bd5  mov     ecx, r14d; unsigned int
0x180136bd8  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180136bdd  mov     ebx, eax
0x180136bdf  jmp     loc_180136C9C
0x180136be4  cmp     [rbp+21E0h+arg_20], r15d
0x180136beb  jz      short loc_180136C2F
  ... truncated ...
```
