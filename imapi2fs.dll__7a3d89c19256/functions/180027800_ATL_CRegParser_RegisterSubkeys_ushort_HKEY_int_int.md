# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180027800`
- end: `0x180027dd9`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1497`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x18002744c`
- `0x180027800`

## callees

- `0x180005cec`
- `0x18001901c`
- `0x180025d40`
- `0x180026bb4`
- `0x180026c90`
- `0x180026cbc`
- `0x180026e58`
- `0x180026f14`
- `0x180027074`
- `0x180027338`
- `0x180027800`
- `0x180027e40`
- `0x180027f10`
- `0x180081750`
- `0x180081810`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180027c06`
- `msvcrt!wcsncpy_s` at `0x180027c06`
- `ADVAPI32!RegCreateKeyExW` at `0x180027b07`
- `ADVAPI32!RegCreateKeyExW` at `0x180027b07`
- `ADVAPI32!RegDeleteValueW` at `0x180027a55`
- `ADVAPI32!RegDeleteValueW` at `0x180027a55`
- `KERNEL32!lstrcmpiW` at `0x18002787b`
- `KERNEL32!lstrcmpiW` at `0x18002788e`
- `KERNEL32!lstrcmpiW` at `0x180027962`
- `KERNEL32!lstrcmpiW` at `0x180027991`
- `KERNEL32!lstrcmpiW` at `0x18002787b`
- `KERNEL32!lstrcmpiW` at `0x18002788e`
- `KERNEL32!lstrcmpiW` at `0x180027962`
- `KERNEL32!lstrcmpiW` at `0x180027991`

## string_xrefs

- `0x180027884`: `ForceRemove`
- `0x180027958`: `NoRemove`
- `0x180027871`: `Delete`

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
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x2001Fu) )
        {
          if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x20019u) )
          {
            dwDisposition = 0;
            phkResult = 0;
            v16 = RegCreateKeyExW(a3, v7, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
            if ( v16 )
              goto LABEL_65;
            v16 = ATL::CRegKey::Close((ATL::CRegKey *)v30);
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
            if ( ATL::CRegParser::CanForceRemoveKey(v21, Destination) && v14 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v30, Destination);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v21, v30[0]);
            v24 = ATL::CRegKey::Close((ATL::CRegKey *)v30);
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
      v28 = 0;
      v29 = 0;
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
    v28 = 0;
    v29 = 0;
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
  ATL::CRegKey::Close((ATL::CRegKey *)v30);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180027800  push    rbp
0x180027802  push    rbx
0x180027803  push    rsi
0x180027804  push    rdi
0x180027805  push    r12
0x180027807  push    r13
0x180027809  push    r14
0x18002780b  push    r15
0x18002780d  lea     rbp, [rsp-21C8h]
0x180027815  mov     eax, 22C8h
0x18002781a  call    _alloca_probe
0x18002781f  sub     rsp, rax
0x180027822  mov     rax, cs:__security_cookie
0x180027829  xor     rax, rsp
0x18002782c  mov     [rbp+2200h+var_50], rax
0x180027833  mov     r15d, r9d
0x180027836  mov     [rsp+2300h+var_22B0], r9d
0x18002783b  mov     r13, r8
0x18002783e  mov     rdi, rdx
0x180027841  mov     rsi, rcx
0x180027844  xor     r14d, r14d
0x180027847  mov     [rsp+2300h+var_2290], r14
0x18002784c  mov     [rsp+2300h+var_2288], r14
0x180027851  mov     [rbp+2200h+var_2280], r14
0x180027855  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002785a  test    eax, eax
0x18002785c  mov     ebx, eax
0x18002785e  js      loc_180027D8D
0x180027864  xor     r12d, r12d
0x180027867  cmp     word ptr [rdi], 7Dh ; '}'
0x18002786b  jz      loc_180027D8D
0x180027871  lea     rdx, String2; "Delete"
0x180027878  mov     rcx, rdi; lpString1
0x18002787b  call    cs:__imp_lstrcmpiW
0x180027881  mov     r14d, eax
0x180027884  lea     rdx, aForceremove; "ForceRemove"
0x18002788b  mov     rcx, rdi; lpString1
0x18002788e  call    cs:__imp_lstrcmpiW
0x180027894  test    eax, eax
0x180027896  jz      short loc_1800278A1
0x180027898  test    r14d, r14d
0x18002789b  jnz     loc_180027952
0x1800278a1  mov     rdx, rdi; unsigned __int16 *
0x1800278a4  mov     rcx, rsi; this
0x1800278a7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800278ac  mov     ebx, eax
0x1800278ae  test    eax, eax
0x1800278b0  js      loc_180027D8D
0x1800278b6  test    r15d, r15d
0x1800278b9  jz      loc_180027952
0x1800278bf  mov     [rsp+2300h+hKey], r12
0x1800278c4  mov     [rsp+2300h+var_22A0], r12
0x1800278c9  mov     [rsp+2300h+var_2298], r12
0x1800278ce  mov     edx, 5Ch ; '\'; unsigned __int16
0x1800278d3  mov     rcx, rdi; lpsz
0x1800278d6  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1800278db  test    rax, rax
0x1800278de  jnz     loc_180027D7E
0x1800278e4  mov     rdx, rdi; unsigned __int16 *
0x1800278e7  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x1800278ec  test    eax, eax
0x1800278ee  jz      short loc_180027907
0x1800278f0  mov     [rsp+2300h+hKey], r13
0x1800278f5  mov     rdx, rdi; unsigned __int16 *
0x1800278f8  lea     rcx, [rsp+2300h+hKey]; this
0x1800278fd  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180027902  mov     [rsp+2300h+hKey], r12
0x180027907  test    r14d, r14d
0x18002790a  jnz     short loc_180027948
0x18002790c  mov     rdx, rdi; unsigned __int16 *
0x18002790f  mov     rcx, rsi; this
0x180027912  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180027917  mov     ebx, eax
0x180027919  xor     r14d, r14d
0x18002791c  test    eax, eax
0x18002791e  js      loc_180027DC5
0x180027924  mov     rdx, rdi; unsigned __int16 *
0x180027927  mov     rcx, rsi; this
0x18002792a  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18002792f  mov     ebx, eax
0x180027931  test    eax, eax
0x180027933  lea     rcx, [rsp+2300h+hKey]; this
0x180027938  js      loc_180027DCA
0x18002793e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180027943  jmp     loc_180027B6C
0x180027948  lea     rcx, [rsp+2300h+hKey]; this
0x18002794d  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180027952  mov     r12d, 1
0x180027958  lea     rdx, aNoremove; "NoRemove"
0x18002795f  mov     rcx, rdi; lpString1
0x180027962  call    cs:__imp_lstrcmpiW
0x180027968  xor     r14d, r14d
0x18002796b  test    eax, eax
0x18002796d  jnz     short loc_180027987
0x18002796f  mov     r12d, r14d
0x180027972  mov     rdx, rdi; unsigned __int16 *
0x180027975  mov     rcx, rsi; this
0x180027978  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002797d  mov     ebx, eax
0x18002797f  test    eax, eax
0x180027981  js      loc_180027D8D
0x180027987  lea     rdx, aVal; "Val"
0x18002798e  mov     rcx, rdi; lpString1
0x180027991  call    cs:__imp_lstrcmpiW
0x180027997  test    eax, eax
0x180027999  jnz     loc_180027A80
0x18002799f  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x1800279a6  mov     rcx, rsi; this
0x1800279a9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800279ae  mov     ebx, eax
0x1800279b0  test    eax, eax
0x1800279b2  js      loc_180027D8D
0x1800279b8  mov     rdx, rdi; unsigned __int16 *
0x1800279bb  mov     rcx, rsi; this
0x1800279be  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800279c3  mov     ebx, eax
0x1800279c5  test    eax, eax
0x1800279c7  js      loc_180027D8D
0x1800279cd  cmp     word ptr [rdi], 3Dh ; '='
0x1800279d1  jnz     loc_180027D88
0x1800279d7  test    r15d, r15d
0x1800279da  jz      short loc_180027A0E
0x1800279dc  mov     [rsp+2300h+var_22A0], r14
0x1800279e1  mov     [rsp+2300h+var_2298], r14
0x1800279e6  mov     [rsp+2300h+hKey], r13
0x1800279eb  mov     r9, rdi; unsigned __int16 *
0x1800279ee  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x1800279f5  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x1800279fa  mov     rcx, rsi; this
0x1800279fd  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180027a02  mov     ebx, eax
0x180027a04  mov     [rsp+2300h+hKey], r14
0x180027a09  jmp     loc_180027931
0x180027a0e  cmp     [rbp+2200h+arg_20], r14d
0x180027a15  jnz     short loc_180027A70
0x180027a17  test    r12d, r12d
0x180027a1a  jz      short loc_180027A70
0x180027a1c  mov     [rsp+2300h+hKey], r14
0x180027a21  mov     [rsp+2300h+var_22A0], r14
0x180027a26  mov     [rsp+2300h+var_2298], r14
0x180027a2b  mov     r9d, 20006h; unsigned int
0x180027a31  xor     r8d, r8d; lpSubKey
0x180027a34  mov     rdx, r13; hKey
0x180027a37  lea     rcx, [rsp+2300h+hKey]; this
0x180027a3c  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180027a41  test    eax, eax
0x180027a43  jnz     loc_180027DBC
0x180027a49  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x180027a50  mov     rcx, [rsp+2300h+hKey]; hKey
0x180027a55  call    cs:__imp_RegDeleteValueW
0x180027a5b  test    eax, 0FFFFFFFDh
0x180027a60  jnz     loc_180027DBC
0x180027a66  lea     rcx, [rsp+2300h+hKey]; this
0x180027a6b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180027a70  mov     rdx, rdi; unsigned __int16 *
0x180027a73  mov     rcx, rsi; this
0x180027a76  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180027a7b  jmp     loc_18002785A
0x180027a80  mov     edx, 5Ch ; '\'; unsigned __int16
0x180027a85  mov     rcx, rdi; lpsz
0x180027a88  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180027a8d  test    rax, rax
0x180027a90  jnz     loc_180027D88
0x180027a96  test    r15d, r15d
0x180027a99  jz      loc_180027BBB
0x180027a9f  mov     ebx, 2001Fh
0x180027aa4  mov     r9d, ebx; unsigned int
0x180027aa7  mov     r8, rdi; lpSubKey
0x180027aaa  mov     rdx, r13; hKey
0x180027aad  lea     rcx, [rsp+2300h+var_2290]; this
0x180027ab2  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180027ab7  test    eax, eax
0x180027ab9  jz      short loc_180027B34
0x180027abb  lea     r9d, [rbx-6]; unsigned int
0x180027abf  mov     r8, rdi; lpSubKey
0x180027ac2  mov     rdx, r13; hKey
0x180027ac5  lea     rcx, [rsp+2300h+var_2290]; this
0x180027aca  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180027acf  test    eax, eax
0x180027ad1  jz      short loc_180027B34
0x180027ad3  mov     [rbp+2200h+dwDisposition], r14d
0x180027ad7  mov     [rbp+2200h+var_2270], r14
0x180027adb  lea     rax, [rbp+2200h+dwDisposition]
0x180027adf  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x180027ae4  lea     rax, [rbp+2200h+var_2270]
0x180027ae8  mov     [rsp+2300h+phkResult], rax; phkResult
0x180027aed  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180027af2  mov     [rsp+2300h+samDesired], ebx; samDesired
0x180027af6  mov     [rsp+2300h+dwOptions], r14d; dwOptions
0x180027afb  xor     r9d, r9d; lpClass
0x180027afe  xor     r8d, r8d; Reserved
0x180027b01  mov     rdx, rdi; lpSubKey
0x180027b04  mov     rcx, r13; hKey
0x180027b07  call    cs:__imp_RegCreateKeyExW
0x180027b0d  mov     ecx, eax
0x180027b0f  test    eax, eax
0x180027b11  jnz     loc_180027CBB
0x180027b17  lea     rcx, [rsp+2300h+var_2290]; this
0x180027b1c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180027b21  mov     ecx, eax
0x180027b23  mov     rax, [rbp+2200h+var_2270]
0x180027b27  mov     [rsp+2300h+var_2290], rax
0x180027b2c  test    ecx, ecx
0x180027b2e  jnz     loc_180027CBB
0x180027b34  mov     rdx, rdi; unsigned __int16 *
0x180027b37  mov     rcx, rsi; this
0x180027b3a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180027b3f  mov     ebx, eax
0x180027b41  test    eax, eax
0x180027b43  js      loc_180027D8D
0x180027b49  cmp     word ptr [rdi], 3Dh ; '='
0x180027b4d  jnz     short loc_180027B6C
0x180027b4f  mov     r9, rdi; unsigned __int16 *
0x180027b52  xor     r8d, r8d; unsigned __int16 *
0x180027b55  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x180027b5a  mov     rcx, rsi; this
0x180027b5d  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180027b62  mov     ebx, eax
0x180027b64  test    eax, eax
0x180027b66  js      loc_180027D8D
0x180027b6c  cmp     word ptr [rdi], 7Bh ; '{'
0x180027b70  jnz     loc_180027864
0x180027b76  or      rax, 0FFFFFFFFFFFFFFFFh
0x180027b7a  inc     rax
0x180027b7d  cmp     [rdi+rax*2], r14w
0x180027b82  jnz     short loc_180027B7A
0x180027b84  cmp     rax, 1
0x180027b88  jnz     loc_180027864
0x180027b8e  mov     [rsp+2300h+dwOptions], r14d; int
0x180027b93  mov     r9d, r15d; int
0x180027b96  mov     r8, [rsp+2300h+var_2290]; HKEY
0x180027b9b  mov     rdx, rdi; unsigned __int16 *
0x180027b9e  mov     rcx, rsi; this
0x180027ba1  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180027ba6  mov     ebx, eax
0x180027ba8  test    eax, eax
0x180027baa  js      loc_180027D8D
0x180027bb0  mov     rdx, rdi
0x180027bb3  mov     rcx, rsi
0x180027bb6  jmp     loc_180027855
0x180027bbb  cmp     [rbp+2200h+arg_20], r14d
0x180027bc2  jnz     short loc_180027BDF
0x180027bc4  mov     r9d, 20019h; unsigned int
0x180027bca  mov     r8, rdi; lpSubKey
0x180027bcd  mov     rdx, r13; hKey
0x180027bd0  lea     rcx, [rsp+2300h+var_2290]; this
0x180027bd5  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180027bda  mov     r14d, eax
0x180027bdd  jmp     short loc_180027BE5
0x180027bdf  mov     r14d, 2
0x180027be5  mov     r15d, 1
0x180027beb  test    r14d, r14d
0x180027bee  cmovz   r15d, [rbp+2200h+arg_20]
0x180027bf6  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180027bfa  mov     r8, rdi; Source
0x180027bfd  mov     edx, 104h; SizeInWords
0x180027c02  lea     rcx, [rbp+2200h+Destination]; Destination
0x180027c06  call    cs:__imp_wcsncpy_s
0x180027c0c  mov     ecx, eax; int
0x180027c0e  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180027c13  mov     rdx, rdi; unsigned __int16 *
0x180027c16  mov     rcx, rsi; this
0x180027c19  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180027c1e  mov     ebx, eax
0x180027c20  test    eax, eax
0x180027c22  js      loc_180027D8D
0x180027c28  mov     rdx, rdi; unsigned __int16 *
0x180027c2b  mov     rcx, rsi; this
0x180027c2e  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180027c33  mov     ebx, eax
0x180027c35  xor     ecx, ecx
0x180027c37  test    eax, eax
0x180027c39  js      loc_180027D8D
0x180027c3f  cmp     word ptr [rdi], 7Bh ; '{'
0x180027c43  jnz     short loc_180027C94
0x180027c45  or      rax, 0FFFFFFFFFFFFFFFFh
0x180027c49  inc     rax
0x180027c4c  cmp     [rdi+rax*2], cx
0x180027c50  jnz     short loc_180027C49
0x180027c52  cmp     rax, 1
0x180027c56  jnz     short loc_180027C94
0x180027c58  mov     [rsp+2300h+dwOptions], r15d; int
0x180027c5d  xor     r9d, r9d; int
0x180027c60  mov     r8, [rsp+2300h+var_2290]; HKEY
0x180027c65  mov     rdx, rdi; unsigned __int16 *
0x180027c68  mov     rcx, rsi; this
0x180027c6b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180027c70  mov     ebx, eax
0x180027c72  test    eax, eax
0x180027c74  jns     short loc_180027C7F
0x180027c76  test    r15d, r15d
0x180027c79  jz      loc_180027D8D
0x180027c7f  mov     rdx, rdi; unsigned __int16 *
0x180027c82  mov     rcx, rsi; this
0x180027c85  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180027c8a  mov     ebx, eax
0x180027c8c  test    eax, eax
0x180027c8e  js      loc_180027D8D
0x180027c94  cmp     r14d, 2
0x180027c98  mov     r15d, [rsp+2300h+var_22B0]
  ... truncated ...
```
