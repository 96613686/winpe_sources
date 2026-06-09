# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180008e68`
- end: `0x180009441`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1497`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x180008aac`
- `0x180008e68`

## callees

- `0x180006dfc`
- `0x180007594`
- `0x180007604`
- `0x180007a5c`
- `0x180007b74`
- `0x180007f70`
- `0x180008278`
- `0x180008410`
- `0x180008570`
- `0x180008998`
- `0x180008e68`
- `0x1800096cc`
- `0x18000979c`
- `0x18002d200`
- `0x18002d2c0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18000926e`
- `msvcrt!wcsncpy_s` at `0x18000926e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000916f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000916f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800090bd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800090bd`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008ee3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008ef6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008fca`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008ff9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008ee3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008ef6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008fca`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008ff9`

## string_xrefs

- `0x180008eec`: `ForceRemove`
- `0x180008fc0`: `NoRemove`
- `0x180008ed9`: `Delete`

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
  LSTATUS v16; // ecx
  __int64 v17; // rax
  int v18; // r14d
  int v19; // r15d
  errno_t v20; // eax
  ATL::CRegParser *v21; // rcx
  __int64 v22; // rax
  int HasSubKeys; // r14d
  LSTATUS v24; // eax
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+60h] [rbp-A0h]
  __int64 v29; // [rsp+68h] [rbp-98h]
  HKEY v30[3]; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  wchar_t Destination[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ValueName[4096]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v5 = a4;
  v7 = a2;
  v8 = this;
  memset(v30, 0, sizeof(v30));
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
          v28 = 0;
          v29 = 0;
          if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
          {
            ATL::CRegKey::Close(&hKey);
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
            v10 = v13;
            goto LABEL_15;
          }
          ATL::CRegKey::Close(&hKey);
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
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x2001Fu) )
        {
          if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x20019u) )
          {
            dwDisposition = 0;
            phkResult = 0;
            v16 = RegCreateKeyExW(a3, v7, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
            if ( v16 )
              goto LABEL_65;
            v16 = ATL::CRegKey::Close(v30);
            v30[0] = phkResult;
            if ( v16 )
              goto LABEL_65;
          }
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        if ( *v7 == 61 )
        {
          v10 = ATL::CRegParser::AddValue(v8, v30, 0, v7);
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
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v30[0], v5, 0);
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
          v18 = ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x20019u);
        v19 = 1;
        if ( !v18 )
          v19 = a5;
        v20 = wcsncpy_s(Destination, 0x104u, v7, 0xFFFFFFFFFFFFFFFFuLL);
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
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v30[0], 0, v19);
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
          else if ( a5 && ATL::CRegParser::HasSubKeys(v21, v30[0]) )
          {
            if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v21, Destination) && v14 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v30, Destination);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v21, v30[0]);
            v24 = ATL::CRegKey::Close(v30);
            if ( v24 )
            {
              v16 = v24;
              goto LABEL_65;
            }
            if ( v14 && !HasSubKeys )
            {
              v28 = 0;
              v29 = 0;
              hKey = a3;
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, Destination);
              hKey = 0;
              if ( v15 )
                goto LABEL_80;
              ATL::CRegKey::Close(&hKey);
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
      v28 = 0;
      v29 = 0;
      hKey = a3;
      v13 = ATL::CRegParser::AddValue(v8, &hKey, ValueName, v7);
      v10 = v13;
      hKey = 0;
LABEL_15:
      if ( v13 < 0 )
        goto LABEL_81;
      ATL::CRegKey::Close(&hKey);
      goto LABEL_41;
    }
    if ( a5 || !v14 )
      goto LABEL_31;
    hKey = 0;
    v28 = 0;
    v29 = 0;
    v15 = ATL::CRegKey::Open((ATL::CRegKey *)&hKey, a3, 0, 0x20006u);
    if ( !v15 )
    {
      v15 = RegDeleteValueW(hKey, ValueName);
      if ( (v15 & 0xFFFFFFFD) == 0 )
      {
        ATL::CRegKey::Close(&hKey);
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
  ATL::CRegKey::Close(&hKey);
LABEL_79:
  ATL::CRegKey::Close(v30);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180008e68  push    rbp
0x180008e6a  push    rbx
0x180008e6b  push    rsi
0x180008e6c  push    rdi
0x180008e6d  push    r12
0x180008e6f  push    r13
0x180008e71  push    r14
0x180008e73  push    r15
0x180008e75  lea     rbp, [rsp-21C8h]
0x180008e7d  mov     eax, 22C8h
0x180008e82  call    _alloca_probe
0x180008e87  sub     rsp, rax
0x180008e8a  mov     rax, cs:__security_cookie
0x180008e91  xor     rax, rsp
0x180008e94  mov     [rbp+2200h+var_50], rax
0x180008e9b  mov     r15d, r9d
0x180008e9e  mov     [rsp+2300h+var_22B0], r9d
0x180008ea3  mov     r13, r8
0x180008ea6  mov     rdi, rdx
0x180008ea9  mov     rsi, rcx
0x180008eac  xor     r14d, r14d
0x180008eaf  mov     [rsp+2300h+var_2290], r14
0x180008eb4  mov     [rsp+2300h+var_2288], r14
0x180008eb9  mov     [rbp+2200h+var_2280], r14
0x180008ebd  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008ec2  test    eax, eax
0x180008ec4  mov     ebx, eax
0x180008ec6  js      loc_1800093F5
0x180008ecc  xor     r12d, r12d
0x180008ecf  cmp     word ptr [rdi], 7Dh ; '}'
0x180008ed3  jz      loc_1800093F5
0x180008ed9  lea     rdx, String2; "Delete"
0x180008ee0  mov     rcx, rdi; lpString1
0x180008ee3  call    cs:__imp_lstrcmpiW
0x180008ee9  mov     r14d, eax
0x180008eec  lea     rdx, aForceremove; "ForceRemove"
0x180008ef3  mov     rcx, rdi; lpString1
0x180008ef6  call    cs:__imp_lstrcmpiW
0x180008efc  test    eax, eax
0x180008efe  jz      short loc_180008F09
0x180008f00  test    r14d, r14d
0x180008f03  jnz     loc_180008FBA
0x180008f09  mov     rdx, rdi; unsigned __int16 *
0x180008f0c  mov     rcx, rsi; this
0x180008f0f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008f14  mov     ebx, eax
0x180008f16  test    eax, eax
0x180008f18  js      loc_1800093F5
0x180008f1e  test    r15d, r15d
0x180008f21  jz      loc_180008FBA
0x180008f27  mov     [rsp+2300h+hKey], r12
0x180008f2c  mov     [rsp+2300h+var_22A0], r12
0x180008f31  mov     [rsp+2300h+var_2298], r12
0x180008f36  mov     edx, 5Ch ; '\'; unsigned __int16
0x180008f3b  mov     rcx, rdi; lpsz
0x180008f3e  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180008f43  test    rax, rax
0x180008f46  jnz     loc_1800093E6
0x180008f4c  mov     rdx, rdi; unsigned __int16 *
0x180008f4f  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x180008f54  test    eax, eax
0x180008f56  jz      short loc_180008F6F
0x180008f58  mov     [rsp+2300h+hKey], r13
0x180008f5d  mov     rdx, rdi; unsigned __int16 *
0x180008f60  lea     rcx, [rsp+2300h+hKey]; this
0x180008f65  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180008f6a  mov     [rsp+2300h+hKey], r12
0x180008f6f  test    r14d, r14d
0x180008f72  jnz     short loc_180008FB0
0x180008f74  mov     rdx, rdi; unsigned __int16 *
0x180008f77  mov     rcx, rsi; this
0x180008f7a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008f7f  mov     ebx, eax
0x180008f81  xor     r14d, r14d
0x180008f84  test    eax, eax
0x180008f86  js      loc_18000942D
0x180008f8c  mov     rdx, rdi; unsigned __int16 *
0x180008f8f  mov     rcx, rsi; this
0x180008f92  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180008f97  mov     ebx, eax
0x180008f99  test    eax, eax
0x180008f9b  lea     rcx, [rsp+2300h+hKey]; this
0x180008fa0  js      loc_180009432
0x180008fa6  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180008fab  jmp     loc_1800091D4
0x180008fb0  lea     rcx, [rsp+2300h+hKey]; this
0x180008fb5  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180008fba  mov     r12d, 1
0x180008fc0  lea     rdx, aNoremove; "NoRemove"
0x180008fc7  mov     rcx, rdi; lpString1
0x180008fca  call    cs:__imp_lstrcmpiW
0x180008fd0  xor     r14d, r14d
0x180008fd3  test    eax, eax
0x180008fd5  jnz     short loc_180008FEF
0x180008fd7  mov     r12d, r14d
0x180008fda  mov     rdx, rdi; unsigned __int16 *
0x180008fdd  mov     rcx, rsi; this
0x180008fe0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008fe5  mov     ebx, eax
0x180008fe7  test    eax, eax
0x180008fe9  js      loc_1800093F5
0x180008fef  lea     rdx, aVal; "Val"
0x180008ff6  mov     rcx, rdi; lpString1
0x180008ff9  call    cs:__imp_lstrcmpiW
0x180008fff  test    eax, eax
0x180009001  jnz     loc_1800090E8
0x180009007  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x18000900e  mov     rcx, rsi; this
0x180009011  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180009016  mov     ebx, eax
0x180009018  test    eax, eax
0x18000901a  js      loc_1800093F5
0x180009020  mov     rdx, rdi; unsigned __int16 *
0x180009023  mov     rcx, rsi; this
0x180009026  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000902b  mov     ebx, eax
0x18000902d  test    eax, eax
0x18000902f  js      loc_1800093F5
0x180009035  cmp     word ptr [rdi], 3Dh ; '='
0x180009039  jnz     loc_1800093F0
0x18000903f  test    r15d, r15d
0x180009042  jz      short loc_180009076
0x180009044  mov     [rsp+2300h+var_22A0], r14
0x180009049  mov     [rsp+2300h+var_2298], r14
0x18000904e  mov     [rsp+2300h+hKey], r13
0x180009053  mov     r9, rdi; unsigned __int16 *
0x180009056  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x18000905d  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x180009062  mov     rcx, rsi; this
0x180009065  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18000906a  mov     ebx, eax
0x18000906c  mov     [rsp+2300h+hKey], r14
0x180009071  jmp     loc_180008F99
0x180009076  cmp     [rbp+2200h+arg_20], r14d
0x18000907d  jnz     short loc_1800090D8
0x18000907f  test    r12d, r12d
0x180009082  jz      short loc_1800090D8
0x180009084  mov     [rsp+2300h+hKey], r14
0x180009089  mov     [rsp+2300h+var_22A0], r14
0x18000908e  mov     [rsp+2300h+var_2298], r14
0x180009093  mov     r9d, 20006h; unsigned int
0x180009099  xor     r8d, r8d; lpSubKey
0x18000909c  mov     rdx, r13; hKey
0x18000909f  lea     rcx, [rsp+2300h+hKey]; this
0x1800090a4  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800090a9  test    eax, eax
0x1800090ab  jnz     loc_180009424
0x1800090b1  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x1800090b8  mov     rcx, [rsp+2300h+hKey]; hKey
0x1800090bd  call    cs:__imp_RegDeleteValueW
0x1800090c3  test    eax, 0FFFFFFFDh
0x1800090c8  jnz     loc_180009424
0x1800090ce  lea     rcx, [rsp+2300h+hKey]; this
0x1800090d3  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800090d8  mov     rdx, rdi; unsigned __int16 *
0x1800090db  mov     rcx, rsi; this
0x1800090de  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800090e3  jmp     loc_180008EC2
0x1800090e8  mov     edx, 5Ch ; '\'; unsigned __int16
0x1800090ed  mov     rcx, rdi; lpsz
0x1800090f0  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1800090f5  test    rax, rax
0x1800090f8  jnz     loc_1800093F0
0x1800090fe  test    r15d, r15d
0x180009101  jz      loc_180009223
0x180009107  mov     ebx, 2001Fh
0x18000910c  mov     r9d, ebx; unsigned int
0x18000910f  mov     r8, rdi; lpSubKey
0x180009112  mov     rdx, r13; hKey
0x180009115  lea     rcx, [rsp+2300h+var_2290]; this
0x18000911a  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000911f  test    eax, eax
0x180009121  jz      short loc_18000919C
0x180009123  lea     r9d, [rbx-6]; unsigned int
0x180009127  mov     r8, rdi; lpSubKey
0x18000912a  mov     rdx, r13; hKey
0x18000912d  lea     rcx, [rsp+2300h+var_2290]; this
0x180009132  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180009137  test    eax, eax
0x180009139  jz      short loc_18000919C
0x18000913b  mov     [rbp+2200h+dwDisposition], r14d
0x18000913f  mov     [rbp+2200h+var_2270], r14
0x180009143  lea     rax, [rbp+2200h+dwDisposition]
0x180009147  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x18000914c  lea     rax, [rbp+2200h+var_2270]
0x180009150  mov     [rsp+2300h+phkResult], rax; phkResult
0x180009155  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18000915a  mov     [rsp+2300h+samDesired], ebx; samDesired
0x18000915e  mov     [rsp+2300h+dwOptions], r14d; dwOptions
0x180009163  xor     r9d, r9d; lpClass
0x180009166  xor     r8d, r8d; Reserved
0x180009169  mov     rdx, rdi; lpSubKey
0x18000916c  mov     rcx, r13; hKey
0x18000916f  call    cs:__imp_RegCreateKeyExW
0x180009175  mov     ecx, eax
0x180009177  test    eax, eax
0x180009179  jnz     loc_180009323
0x18000917f  lea     rcx, [rsp+2300h+var_2290]; this
0x180009184  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180009189  mov     ecx, eax
0x18000918b  mov     rax, [rbp+2200h+var_2270]
0x18000918f  mov     [rsp+2300h+var_2290], rax
0x180009194  test    ecx, ecx
0x180009196  jnz     loc_180009323
0x18000919c  mov     rdx, rdi; unsigned __int16 *
0x18000919f  mov     rcx, rsi; this
0x1800091a2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800091a7  mov     ebx, eax
0x1800091a9  test    eax, eax
0x1800091ab  js      loc_1800093F5
0x1800091b1  cmp     word ptr [rdi], 3Dh ; '='
0x1800091b5  jnz     short loc_1800091D4
0x1800091b7  mov     r9, rdi; unsigned __int16 *
0x1800091ba  xor     r8d, r8d; unsigned __int16 *
0x1800091bd  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x1800091c2  mov     rcx, rsi; this
0x1800091c5  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1800091ca  mov     ebx, eax
0x1800091cc  test    eax, eax
0x1800091ce  js      loc_1800093F5
0x1800091d4  cmp     word ptr [rdi], 7Bh ; '{'
0x1800091d8  jnz     loc_180008ECC
0x1800091de  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800091e2  inc     rax
0x1800091e5  cmp     [rdi+rax*2], r14w
0x1800091ea  jnz     short loc_1800091E2
0x1800091ec  cmp     rax, 1
0x1800091f0  jnz     loc_180008ECC
0x1800091f6  mov     [rsp+2300h+dwOptions], r14d; int
0x1800091fb  mov     r9d, r15d; int
0x1800091fe  mov     r8, [rsp+2300h+var_2290]; HKEY
0x180009203  mov     rdx, rdi; unsigned __int16 *
0x180009206  mov     rcx, rsi; this
0x180009209  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000920e  mov     ebx, eax
0x180009210  test    eax, eax
0x180009212  js      loc_1800093F5
0x180009218  mov     rdx, rdi
0x18000921b  mov     rcx, rsi
0x18000921e  jmp     loc_180008EBD
0x180009223  cmp     [rbp+2200h+arg_20], r14d
0x18000922a  jnz     short loc_180009247
0x18000922c  mov     r9d, 20019h; unsigned int
0x180009232  mov     r8, rdi; lpSubKey
0x180009235  mov     rdx, r13; hKey
0x180009238  lea     rcx, [rsp+2300h+var_2290]; this
0x18000923d  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180009242  mov     r14d, eax
0x180009245  jmp     short loc_18000924D
0x180009247  mov     r14d, 2
0x18000924d  mov     r15d, 1
0x180009253  test    r14d, r14d
0x180009256  cmovz   r15d, [rbp+2200h+arg_20]
0x18000925e  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180009262  mov     r8, rdi; Source
0x180009265  mov     edx, 104h; SizeInWords
0x18000926a  lea     rcx, [rbp+2200h+Destination]; Destination
0x18000926e  call    cs:__imp_wcsncpy_s
0x180009274  mov     ecx, eax; int
0x180009276  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000927b  mov     rdx, rdi; unsigned __int16 *
0x18000927e  mov     rcx, rsi; this
0x180009281  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180009286  mov     ebx, eax
0x180009288  test    eax, eax
0x18000928a  js      loc_1800093F5
0x180009290  mov     rdx, rdi; unsigned __int16 *
0x180009293  mov     rcx, rsi; this
0x180009296  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000929b  mov     ebx, eax
0x18000929d  xor     ecx, ecx
0x18000929f  test    eax, eax
0x1800092a1  js      loc_1800093F5
0x1800092a7  cmp     word ptr [rdi], 7Bh ; '{'
0x1800092ab  jnz     short loc_1800092FC
0x1800092ad  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800092b1  inc     rax
0x1800092b4  cmp     [rdi+rax*2], cx
0x1800092b8  jnz     short loc_1800092B1
0x1800092ba  cmp     rax, 1
0x1800092be  jnz     short loc_1800092FC
0x1800092c0  mov     [rsp+2300h+dwOptions], r15d; int
0x1800092c5  xor     r9d, r9d; int
0x1800092c8  mov     r8, [rsp+2300h+var_2290]; HKEY
0x1800092cd  mov     rdx, rdi; unsigned __int16 *
0x1800092d0  mov     rcx, rsi; this
0x1800092d3  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800092d8  mov     ebx, eax
0x1800092da  test    eax, eax
0x1800092dc  jns     short loc_1800092E7
0x1800092de  test    r15d, r15d
0x1800092e1  jz      loc_1800093F5
0x1800092e7  mov     rdx, rdi; unsigned __int16 *
0x1800092ea  mov     rcx, rsi; this
0x1800092ed  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800092f2  mov     ebx, eax
0x1800092f4  test    eax, eax
0x1800092f6  js      loc_1800093F5
0x1800092fc  cmp     r14d, 2
0x180009300  mov     r15d, [rsp+2300h+var_22B0]
  ... truncated ...
```
