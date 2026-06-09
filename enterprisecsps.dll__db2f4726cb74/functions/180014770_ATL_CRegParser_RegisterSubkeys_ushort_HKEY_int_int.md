# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180014770`
- end: `0x180014d74`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1540`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x18001441c`
- `0x180014770`

## callees

- `0x180008de0`
- `0x1800103a8`
- `0x180010aa0`
- `0x180010b14`
- `0x180010c2c`
- `0x180010de0`
- `0x180012f8c`
- `0x1800132bc`
- `0x180013480`
- `0x180013610`
- `0x1800142fc`
- `0x180014770`
- `0x18001505c`
- `0x180015134`
- `0x180100500`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180014b9a`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180014b9a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800149dd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800149dd`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180014a95`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180014a95`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800147eb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180014804`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800148de`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180014913`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800147eb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180014804`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800148de`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180014913`

## string_xrefs

- `0x1800147fa`: `ForceRemove`
- `0x1800148d4`: `NoRemove`
- `0x1800147e1`: `Delete`

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
0x180014770  push    rbp
0x180014772  push    rbx
0x180014773  push    rsi
0x180014774  push    rdi
0x180014775  push    r12
0x180014777  push    r13
0x180014779  push    r14
0x18001477b  push    r15
0x18001477d  lea     rbp, [rsp-21C8h]
0x180014785  mov     eax, 22C8h
0x18001478a  call    _alloca_probe
0x18001478f  sub     rsp, rax
0x180014792  mov     rax, cs:__security_cookie
0x180014799  xor     rax, rsp
0x18001479c  mov     [rbp+2200h+var_50], rax
0x1800147a3  mov     r15d, r9d
0x1800147a6  mov     [rsp+2300h+var_22B0], r9d
0x1800147ab  mov     r13, r8
0x1800147ae  mov     rdi, rdx
0x1800147b1  mov     rsi, rcx
0x1800147b4  xor     r14d, r14d
0x1800147b7  mov     [rsp+2300h+var_2290], r14
0x1800147bc  mov     [rsp+2300h+var_2288], r14
0x1800147c1  mov     [rbp+2200h+var_2280], r14
0x1800147c5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800147ca  test    eax, eax
0x1800147cc  mov     ebx, eax
0x1800147ce  js      loc_180014D27
0x1800147d4  xor     r12d, r12d
0x1800147d7  cmp     word ptr [rdi], 7Dh ; '}'
0x1800147db  jz      loc_180014D27
0x1800147e1  lea     rdx, String2; "Delete"
0x1800147e8  mov     rcx, rdi; lpString1
0x1800147eb  call    cs:__imp_lstrcmpiW
0x1800147f2  nop     dword ptr [rax+rax+00h]
0x1800147f7  mov     r14d, eax
0x1800147fa  lea     rdx, aForceremove; "ForceRemove"
0x180014801  mov     rcx, rdi; lpString1
0x180014804  call    cs:__imp_lstrcmpiW
0x18001480b  nop     dword ptr [rax+rax+00h]
0x180014810  test    eax, eax
0x180014812  jz      short loc_18001481D
0x180014814  test    r14d, r14d
0x180014817  jnz     loc_1800148CE
0x18001481d  mov     rdx, rdi; unsigned __int16 *
0x180014820  mov     rcx, rsi; this
0x180014823  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180014828  mov     ebx, eax
0x18001482a  test    eax, eax
0x18001482c  js      loc_180014D27
0x180014832  test    r15d, r15d
0x180014835  jz      loc_1800148CE
0x18001483b  mov     [rsp+2300h+hKey], r12
0x180014840  mov     [rsp+2300h+var_22A0], r12
0x180014845  mov     [rsp+2300h+var_2298], r12
0x18001484a  mov     edx, 5Ch ; '\'; unsigned __int16
0x18001484f  mov     rcx, rdi; lpsz
0x180014852  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180014857  test    rax, rax
0x18001485a  jnz     loc_180014D18
0x180014860  mov     rdx, rdi; unsigned __int16 *
0x180014863  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x180014868  test    eax, eax
0x18001486a  jz      short loc_180014883
0x18001486c  mov     [rsp+2300h+hKey], r13
0x180014871  mov     rdx, rdi; unsigned __int16 *
0x180014874  lea     rcx, [rsp+2300h+hKey]; this
0x180014879  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18001487e  mov     [rsp+2300h+hKey], r12
0x180014883  test    r14d, r14d
0x180014886  jnz     short loc_1800148C4
0x180014888  mov     rdx, rdi; unsigned __int16 *
0x18001488b  mov     rcx, rsi; this
0x18001488e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180014893  mov     ebx, eax
0x180014895  xor     r14d, r14d
0x180014898  test    eax, eax
0x18001489a  js      loc_180014D60
0x1800148a0  mov     rdx, rdi; unsigned __int16 *
0x1800148a3  mov     rcx, rsi; this
0x1800148a6  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800148ab  mov     ebx, eax
0x1800148ad  test    eax, eax
0x1800148af  lea     rcx, [rsp+2300h+hKey]; this
0x1800148b4  js      loc_180014D65
0x1800148ba  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800148bf  jmp     loc_180014B00
0x1800148c4  lea     rcx, [rsp+2300h+hKey]; this
0x1800148c9  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800148ce  mov     r12d, 1
0x1800148d4  lea     rdx, aNoremove; "NoRemove"
0x1800148db  mov     rcx, rdi; lpString1
0x1800148de  call    cs:__imp_lstrcmpiW
0x1800148e5  nop     dword ptr [rax+rax+00h]
0x1800148ea  xor     r14d, r14d
0x1800148ed  test    eax, eax
0x1800148ef  jnz     short loc_180014909
0x1800148f1  mov     r12d, r14d
0x1800148f4  mov     rdx, rdi; unsigned __int16 *
0x1800148f7  mov     rcx, rsi; this
0x1800148fa  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800148ff  mov     ebx, eax
0x180014901  test    eax, eax
0x180014903  js      loc_180014D27
0x180014909  lea     rdx, aVal; "Val"
0x180014910  mov     rcx, rdi; lpString1
0x180014913  call    cs:__imp_lstrcmpiW
0x18001491a  nop     dword ptr [rax+rax+00h]
0x18001491f  test    eax, eax
0x180014921  jnz     loc_180014A0E
0x180014927  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x18001492e  mov     rcx, rsi; this
0x180014931  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180014936  mov     ebx, eax
0x180014938  test    eax, eax
0x18001493a  js      loc_180014D27
0x180014940  mov     rdx, rdi; unsigned __int16 *
0x180014943  mov     rcx, rsi; this
0x180014946  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001494b  mov     ebx, eax
0x18001494d  test    eax, eax
0x18001494f  js      loc_180014D27
0x180014955  cmp     word ptr [rdi], 3Dh ; '='
0x180014959  jnz     loc_180014D22
0x18001495f  test    r15d, r15d
0x180014962  jz      short loc_180014996
0x180014964  mov     [rsp+2300h+var_22A0], r14
0x180014969  mov     [rsp+2300h+var_2298], r14
0x18001496e  mov     [rsp+2300h+hKey], r13
0x180014973  mov     r9, rdi; unsigned __int16 *
0x180014976  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x18001497d  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x180014982  mov     rcx, rsi; this
0x180014985  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18001498a  mov     ebx, eax
0x18001498c  mov     [rsp+2300h+hKey], r14
0x180014991  jmp     loc_1800148AD
0x180014996  cmp     [rbp+2200h+arg_20], r14d
0x18001499d  jnz     short loc_1800149FE
0x18001499f  test    r12d, r12d
0x1800149a2  jz      short loc_1800149FE
0x1800149a4  mov     [rsp+2300h+hKey], r14
0x1800149a9  mov     [rsp+2300h+var_22A0], r14
0x1800149ae  mov     [rsp+2300h+var_2298], r14
0x1800149b3  mov     r9d, 20006h; unsigned int
0x1800149b9  xor     r8d, r8d; lpSubKey
0x1800149bc  mov     rdx, r13; hKey
0x1800149bf  lea     rcx, [rsp+2300h+hKey]; this
0x1800149c4  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800149c9  test    eax, eax
0x1800149cb  jnz     loc_180014D57
0x1800149d1  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x1800149d8  mov     rcx, [rsp+2300h+hKey]; hKey
0x1800149dd  call    cs:__imp_RegDeleteValueW
0x1800149e4  nop     dword ptr [rax+rax+00h]
0x1800149e9  test    eax, 0FFFFFFFDh
0x1800149ee  jnz     loc_180014D57
0x1800149f4  lea     rcx, [rsp+2300h+hKey]; this
0x1800149f9  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800149fe  mov     rdx, rdi; unsigned __int16 *
0x180014a01  mov     rcx, rsi; this
0x180014a04  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180014a09  jmp     loc_1800147CA
0x180014a0e  mov     edx, 5Ch ; '\'; unsigned __int16
0x180014a13  mov     rcx, rdi; lpsz
0x180014a16  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180014a1b  test    rax, rax
0x180014a1e  jnz     loc_180014D22
0x180014a24  test    r15d, r15d
0x180014a27  jz      loc_180014B4F
0x180014a2d  mov     ebx, 2001Fh
0x180014a32  mov     r9d, ebx; unsigned int
0x180014a35  mov     r8, rdi; lpSubKey
0x180014a38  mov     rdx, r13; hKey
0x180014a3b  lea     rcx, [rsp+2300h+var_2290]; this
0x180014a40  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180014a45  test    eax, eax
0x180014a47  jz      short loc_180014AC8
0x180014a49  lea     r9d, [rbx-6]; unsigned int
0x180014a4d  mov     r8, rdi; lpSubKey
0x180014a50  mov     rdx, r13; hKey
0x180014a53  lea     rcx, [rsp+2300h+var_2290]; this
0x180014a58  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180014a5d  test    eax, eax
0x180014a5f  jz      short loc_180014AC8
0x180014a61  mov     [rbp+2200h+dwDisposition], r14d
0x180014a65  mov     [rbp+2200h+var_2270], r14
0x180014a69  lea     rax, [rbp+2200h+dwDisposition]
0x180014a6d  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x180014a72  lea     rax, [rbp+2200h+var_2270]
0x180014a76  mov     [rsp+2300h+phkResult], rax; phkResult
0x180014a7b  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180014a80  mov     [rsp+2300h+samDesired], ebx; samDesired
0x180014a84  mov     dword ptr [rsp+2300h+dwOptions], r14d; dwOptions
0x180014a89  xor     r9d, r9d; lpClass
0x180014a8c  xor     r8d, r8d; Reserved
0x180014a8f  mov     rdx, rdi; lpSubKey
0x180014a92  mov     rcx, r13; hKey
0x180014a95  call    cs:__imp_RegCreateKeyExW
0x180014a9c  nop     dword ptr [rax+rax+00h]
0x180014aa1  mov     ecx, eax
0x180014aa3  test    eax, eax
0x180014aa5  jnz     loc_180014C55
0x180014aab  lea     rcx, [rsp+2300h+var_2290]; this
0x180014ab0  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180014ab5  mov     ecx, eax
0x180014ab7  mov     rax, [rbp+2200h+var_2270]
0x180014abb  mov     [rsp+2300h+var_2290], rax
0x180014ac0  test    ecx, ecx
0x180014ac2  jnz     loc_180014C55
0x180014ac8  mov     rdx, rdi; unsigned __int16 *
0x180014acb  mov     rcx, rsi; this
0x180014ace  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180014ad3  mov     ebx, eax
0x180014ad5  test    eax, eax
0x180014ad7  js      loc_180014D27
0x180014add  cmp     word ptr [rdi], 3Dh ; '='
0x180014ae1  jnz     short loc_180014B00
0x180014ae3  mov     r9, rdi; unsigned __int16 *
0x180014ae6  xor     r8d, r8d; unsigned __int16 *
0x180014ae9  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x180014aee  mov     rcx, rsi; this
0x180014af1  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180014af6  mov     ebx, eax
0x180014af8  test    eax, eax
0x180014afa  js      loc_180014D27
0x180014b00  cmp     word ptr [rdi], 7Bh ; '{'
0x180014b04  jnz     loc_1800147D4
0x180014b0a  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014b0e  inc     rax
0x180014b11  cmp     [rdi+rax*2], r14w
0x180014b16  jnz     short loc_180014B0E
0x180014b18  cmp     rax, 1
0x180014b1c  jnz     loc_1800147D4
0x180014b22  mov     dword ptr [rsp+2300h+dwOptions], r14d; int
0x180014b27  mov     r9d, r15d; int
0x180014b2a  mov     r8, [rsp+2300h+var_2290]; HKEY
0x180014b2f  mov     rdx, rdi; unsigned __int16 *
0x180014b32  mov     rcx, rsi; this
0x180014b35  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180014b3a  mov     ebx, eax
0x180014b3c  test    eax, eax
0x180014b3e  js      loc_180014D27
0x180014b44  mov     rdx, rdi
0x180014b47  mov     rcx, rsi
0x180014b4a  jmp     loc_1800147C5
0x180014b4f  cmp     [rbp+2200h+arg_20], r14d
0x180014b56  jnz     short loc_180014B73
0x180014b58  mov     r9d, 20019h; unsigned int
0x180014b5e  mov     r8, rdi; lpSubKey
0x180014b61  mov     rdx, r13; hKey
0x180014b64  lea     rcx, [rsp+2300h+var_2290]; this
0x180014b69  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180014b6e  mov     r14d, eax
0x180014b71  jmp     short loc_180014B79
0x180014b73  mov     r14d, 2
0x180014b79  mov     r15d, 1
0x180014b7f  test    r14d, r14d
0x180014b82  cmovz   r15d, [rbp+2200h+arg_20]
0x180014b8a  or      r9, 0FFFFFFFFFFFFFFFFh
0x180014b8e  mov     r8, rdi
0x180014b91  mov     edx, 104h
0x180014b96  lea     rcx, [rbp+2200h+var_2260]
0x180014b9a  call    cs:__imp__o_wcsncpy_s
0x180014ba1  nop     dword ptr [rax+rax+00h]
0x180014ba6  mov     ecx, eax; int
0x180014ba8  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180014bad  mov     rdx, rdi; unsigned __int16 *
0x180014bb0  mov     rcx, rsi; this
0x180014bb3  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180014bb8  mov     ebx, eax
0x180014bba  test    eax, eax
0x180014bbc  js      loc_180014D27
0x180014bc2  mov     rdx, rdi; unsigned __int16 *
0x180014bc5  mov     rcx, rsi; this
0x180014bc8  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180014bcd  mov     ebx, eax
0x180014bcf  xor     ecx, ecx
0x180014bd1  test    eax, eax
0x180014bd3  js      loc_180014D27
0x180014bd9  cmp     word ptr [rdi], 7Bh ; '{'
0x180014bdd  jnz     short loc_180014C2E
0x180014bdf  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014be3  inc     rax
0x180014be6  cmp     [rdi+rax*2], cx
0x180014bea  jnz     short loc_180014BE3
0x180014bec  cmp     rax, 1
0x180014bf0  jnz     short loc_180014C2E
0x180014bf2  mov     dword ptr [rsp+2300h+dwOptions], r15d; int
0x180014bf7  xor     r9d, r9d; int
0x180014bfa  mov     r8, [rsp+2300h+var_2290]; HKEY
0x180014bff  mov     rdx, rdi; unsigned __int16 *
0x180014c02  mov     rcx, rsi; this
0x180014c05  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180014c0a  mov     ebx, eax
0x180014c0c  test    eax, eax
0x180014c0e  jns     short loc_180014C19
0x180014c10  test    r15d, r15d
0x180014c13  jz      loc_180014D27
0x180014c19  mov     rdx, rdi; unsigned __int16 *
  ... truncated ...
```
