# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180013134`
- end: `0x180013731`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1533`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x180012e28`
- `0x180013134`

## callees

- `0x180011508`
- `0x180011ac4`
- `0x180011b34`
- `0x180011b7c`
- `0x180011c94`
- `0x180011e84`
- `0x180012078`
- `0x180012760`
- `0x1800128c0`
- `0x180012d14`
- `0x180013134`
- `0x1800138ec`
- `0x180013a3c`
- `0x180049880`
- `0x180049940`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18001354e`
- `msvcrt!wcsncpy_s` at `0x18001354e`
- `ADVAPI32!RegDeleteValueW` at `0x18001338f`
- `ADVAPI32!RegDeleteValueW` at `0x18001338f`
- `ADVAPI32!RegCreateKeyExW` at `0x18001344f`
- `ADVAPI32!RegCreateKeyExW` at `0x18001344f`
- `KERNEL32!lstrcmpiW` at `0x1800131a7`
- `KERNEL32!lstrcmpiW` at `0x1800131ba`
- `KERNEL32!lstrcmpiW` at `0x18001329e`
- `KERNEL32!lstrcmpiW` at `0x1800132cd`
- `KERNEL32!lstrcmpiW` at `0x1800131a7`
- `KERNEL32!lstrcmpiW` at `0x1800131ba`
- `KERNEL32!lstrcmpiW` at `0x18001329e`
- `KERNEL32!lstrcmpiW` at `0x1800132cd`

## string_xrefs

- `0x1800131ad`: `ForceRemove`
- `0x18001328e`: `NoRemove`
- `0x18001319d`: `Delete`

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
  ATL::CRegParser *i; // rsi
  int Token; // eax
  int v10; // r14d
  int v11; // ebx
  ATL::CRegParser *v12; // rcx
  int v13; // eax
  int v14; // r12d
  LSTATUS v15; // eax
  LSTATUS v16; // ebx
  __int64 v17; // rax
  unsigned int v18; // r14d
  int v19; // r15d
  errno_t v20; // eax
  int v21; // eax
  ATL::CRegParser *v22; // rcx
  __int64 v23; // rax
  int HasSubKeys; // r15d
  unsigned int v25; // r14d
  unsigned int v27; // ecx
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v30; // [rsp+60h] [rbp-A0h]
  __int64 v31; // [rsp+68h] [rbp-98h]
  HKEY v32[3]; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  wchar_t Destination[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ValueName[4096]; // [rsp+2B0h] [rbp+1B0h] BYREF

  memset(v32, 0, sizeof(v32));
  v5 = a4;
  v7 = a2;
  for ( i = this; ; this = i )
  {
    Token = ATL::CRegParser::NextToken(this, a2);
LABEL_31:
    v11 = Token;
    if ( Token < 0 )
      break;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( *v7 == 125 )
          goto LABEL_79;
        v10 = lstrcmpiW(v7, L"Delete");
        if ( !lstrcmpiW(v7, L"ForceRemove") || !v10 )
        {
          v11 = ATL::CRegParser::NextToken(i, v7);
          if ( v11 < 0 )
            goto LABEL_79;
          if ( v5 )
          {
            hKey = 0;
            v30 = 0;
            v31 = 0;
            if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
            {
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_78:
              v11 = -2147352567;
              goto LABEL_79;
            }
            if ( ATL::CRegParser::CanForceRemoveKey(v12, v7) )
            {
              hKey = a3;
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&hKey, v7);
              hKey = 0;
            }
            if ( !v10 )
            {
              v11 = ATL::CRegParser::NextToken(i, v7);
              if ( v11 < 0 )
                goto LABEL_81;
              v13 = ATL::CRegParser::SkipAssignment(i, v7);
LABEL_14:
              v11 = v13;
              if ( v13 < 0 )
                goto LABEL_81;
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
              goto LABEL_42;
            }
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
          }
        }
        v14 = 1;
        if ( !lstrcmpiW(v7, L"NoRemove") )
        {
          v14 = 0;
          v11 = ATL::CRegParser::NextToken(i, v7);
          if ( v11 < 0 )
            goto LABEL_79;
        }
        if ( !lstrcmpiW(v7, L"Val") )
        {
          v11 = ATL::CRegParser::NextToken(i, ValueName);
          if ( v11 < 0 )
            goto LABEL_79;
          v11 = ATL::CRegParser::NextToken(i, v7);
          if ( v11 < 0 )
            goto LABEL_79;
          if ( *v7 != 61 )
            goto LABEL_78;
          if ( !v5 )
          {
            if ( a5 || !v14 )
              goto LABEL_30;
            hKey = 0;
            v30 = 0;
            v31 = 0;
            v15 = ATL::CRegKey::Open((ATL::CRegKey *)&hKey, a3, 0, 0x20006u);
            if ( !v15 )
            {
              v15 = RegDeleteValueW(hKey, ValueName);
              if ( (v15 & 0xFFFFFFFD) == 0 )
              {
                ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_30:
                Token = ATL::CRegParser::SkipAssignment(i, v7);
                goto LABEL_31;
              }
            }
LABEL_80:
            v11 = ATL::AtlHresultFromWin32(v15);
LABEL_81:
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            goto LABEL_79;
          }
          v30 = 0;
          v31 = 0;
          hKey = a3;
          v13 = ATL::CRegParser::AddValue(i, &hKey, ValueName, v7);
          hKey = 0;
          goto LABEL_14;
        }
        if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
          goto LABEL_78;
        if ( v5 )
          break;
        if ( a5 )
          v18 = 2;
        else
          v18 = ATL::CRegKey::Open((ATL::CRegKey *)v32, a3, v7, 0x20019u);
        v19 = 1;
        if ( !v18 )
          v19 = a5;
        v20 = wcsncpy_s(Destination, 0x104u, v7, 0xFFFFFFFFFFFFFFFFuLL);
        ATL::AtlCrtErrorCheck(v20);
        v11 = ATL::CRegParser::NextToken(i, v7);
        if ( v11 < 0 )
          goto LABEL_79;
        v21 = ATL::CRegParser::SkipAssignment(i, v7);
        v22 = 0;
        v11 = v21;
        if ( v21 < 0 )
          goto LABEL_79;
        if ( *v7 == 123 )
        {
          v23 = -1;
          do
            ++v23;
          while ( v7[v23] );
          if ( v23 == 1 )
          {
            v11 = ATL::CRegParser::RegisterSubkeys(i, v7, v32[0], 0, v19);
            if ( v11 < 0 && !v19 )
              goto LABEL_79;
            v11 = ATL::CRegParser::NextToken(i, v7);
            if ( v11 < 0 )
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
              v11 = ATL::AtlHresultFromWin32(v18);
              goto LABEL_79;
            }
          }
          else if ( a5 && ATL::CRegParser::HasSubKeys(v22, v32[0]) )
          {
            if ( ATL::CRegParser::CanForceRemoveKey(v22, Destination) && v14 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v32, Destination);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v22, v32[0]);
            v25 = ATL::CRegKey::Close((ATL::CRegKey *)v32);
            if ( v25 )
            {
              ATL::CRegKey::Close((ATL::CRegKey *)v32);
              v27 = v25;
              return ATL::AtlHresultFromWin32(v27);
            }
            if ( v14 && !HasSubKeys )
            {
              v30 = 0;
              v31 = 0;
              hKey = a3;
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, Destination);
              hKey = 0;
              if ( v15 )
                goto LABEL_80;
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            }
            v5 = a4;
          }
        }
      }
      if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v32, a3, v7, 0x2001Fu) )
      {
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v32, a3, v7, 0x20019u) )
        {
          dwDisposition = 0;
          phkResult = 0;
          v16 = RegCreateKeyExW(a3, v7, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
          if ( v16 || (v16 = ATL::CRegKey::Close((ATL::CRegKey *)v32), v32[0] = phkResult, v16) )
          {
            ATL::CRegKey::Close((ATL::CRegKey *)v32);
            v27 = v16;
            return ATL::AtlHresultFromWin32(v27);
          }
        }
      }
      v11 = ATL::CRegParser::NextToken(i, v7);
      if ( v11 < 0 )
        goto LABEL_79;
      if ( *v7 == 61 )
      {
        v11 = ATL::CRegParser::AddValue(i, v32, 0, v7);
        if ( v11 < 0 )
          goto LABEL_79;
      }
LABEL_42:
      if ( *v7 == 123 )
      {
        v17 = -1;
        do
          ++v17;
        while ( v7[v17] );
        if ( v17 == 1 )
          break;
      }
    }
    v11 = ATL::CRegParser::RegisterSubkeys(i, v7, v32[0], v5, 0);
    if ( v11 < 0 )
      break;
    a2 = v7;
  }
LABEL_79:
  ATL::CRegKey::Close((ATL::CRegKey *)v32);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180013134  push    rbp
0x180013136  push    rbx
0x180013137  push    rsi
0x180013138  push    rdi
0x180013139  push    r12
0x18001313b  push    r13
0x18001313d  push    r14
0x18001313f  push    r15
0x180013141  lea     rbp, [rsp-21C8h]
0x180013149  mov     eax, 22C8h
0x18001314e  call    _alloca_probe
0x180013153  sub     rsp, rax
0x180013156  mov     rax, cs:__security_cookie
0x18001315d  xor     rax, rsp
0x180013160  mov     [rbp+2200h+var_50], rax
0x180013167  xor     r14d, r14d
0x18001316a  mov     [rsp+2300h+var_22B0], r9d
0x18001316f  mov     [rsp+2300h+var_2290], r14
0x180013174  mov     r15d, r9d
0x180013177  mov     [rsp+2300h+var_2288], r14
0x18001317c  mov     r13, r8
0x18001317f  mov     [rbp+2200h+var_2280], r14
0x180013183  mov     rdi, rdx
0x180013186  mov     rsi, rcx
0x180013189  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001318e  jmp     loc_1800133B5
0x180013193  cmp     word ptr [rdi], 7Dh ; '}'
0x180013197  jz      loc_1800136CB
0x18001319d  lea     rdx, String2; "Delete"
0x1800131a4  mov     rcx, rdi; lpString1
0x1800131a7  call    cs:__imp_lstrcmpiW
0x1800131ad  lea     rdx, aForceremove; "ForceRemove"
0x1800131b4  mov     rcx, rdi; lpString1
0x1800131b7  mov     r14d, eax
0x1800131ba  call    cs:__imp_lstrcmpiW
0x1800131c0  test    eax, eax
0x1800131c2  jz      short loc_1800131CD
0x1800131c4  test    r14d, r14d
0x1800131c7  jnz     loc_18001328E
0x1800131cd  mov     rdx, rdi; unsigned __int16 *
0x1800131d0  mov     rcx, rsi; this
0x1800131d3  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800131d8  mov     ebx, eax
0x1800131da  test    eax, eax
0x1800131dc  js      loc_1800136CB
0x1800131e2  test    r15d, r15d
0x1800131e5  jz      loc_18001328E
0x1800131eb  mov     edx, 5Ch ; '\'; unsigned __int16
0x1800131f0  mov     [rsp+2300h+hKey], 0
0x1800131f9  mov     rcx, rdi; lpsz
0x1800131fc  mov     [rsp+2300h+var_22A0], 0
0x180013205  mov     [rsp+2300h+var_2298], 0
0x18001320e  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180013213  test    rax, rax
0x180013216  jnz     loc_1800136BC
0x18001321c  mov     rdx, rdi; unsigned __int16 *
0x18001321f  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x180013224  test    eax, eax
0x180013226  jz      short loc_180013243
0x180013228  mov     rdx, rdi; unsigned __int16 *
0x18001322b  mov     [rsp+2300h+hKey], r13
0x180013230  lea     rcx, [rsp+2300h+hKey]; this
0x180013235  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18001323a  mov     [rsp+2300h+hKey], 0
0x180013243  test    r14d, r14d
0x180013246  jnz     short loc_180013284
0x180013248  mov     rdx, rdi; unsigned __int16 *
0x18001324b  mov     rcx, rsi; this
0x18001324e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180013253  xor     r14d, r14d
0x180013256  mov     ebx, eax
0x180013258  test    eax, eax
0x18001325a  js      loc_180013703
0x180013260  mov     rdx, rdi; unsigned __int16 *
0x180013263  mov     rcx, rsi; this
0x180013266  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18001326b  lea     rcx, [rsp+2300h+hKey]; this
0x180013270  mov     ebx, eax
0x180013272  test    eax, eax
0x180013274  js      loc_180013708
0x18001327a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001327f  jmp     loc_1800134B4
0x180013284  lea     rcx, [rsp+2300h+hKey]; this
0x180013289  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001328e  lea     rdx, aNoremove; "NoRemove"
0x180013295  mov     rcx, rdi; lpString1
0x180013298  mov     r12d, 1
0x18001329e  call    cs:__imp_lstrcmpiW
0x1800132a4  xor     r14d, r14d
0x1800132a7  test    eax, eax
0x1800132a9  jnz     short loc_1800132C3
0x1800132ab  mov     rdx, rdi; unsigned __int16 *
0x1800132ae  mov     rcx, rsi; this
0x1800132b1  mov     r12d, r14d
0x1800132b4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800132b9  mov     ebx, eax
0x1800132bb  test    eax, eax
0x1800132bd  js      loc_1800136CB
0x1800132c3  lea     rdx, aVal; "Val"
0x1800132ca  mov     rcx, rdi; lpString1
0x1800132cd  call    cs:__imp_lstrcmpiW
0x1800132d3  test    eax, eax
0x1800132d5  jnz     loc_1800133C4
0x1800132db  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x1800132e2  mov     rcx, rsi; this
0x1800132e5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800132ea  mov     ebx, eax
0x1800132ec  test    eax, eax
0x1800132ee  js      loc_1800136CB
0x1800132f4  mov     rdx, rdi; unsigned __int16 *
0x1800132f7  mov     rcx, rsi; this
0x1800132fa  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800132ff  mov     ebx, eax
0x180013301  test    eax, eax
0x180013303  js      loc_1800136CB
0x180013309  cmp     word ptr [rdi], 3Dh ; '='
0x18001330d  jnz     loc_1800136C6
0x180013313  test    r15d, r15d
0x180013316  jz      short loc_180013348
0x180013318  mov     r9, rdi; unsigned __int16 *
0x18001331b  mov     [rsp+2300h+var_22A0], r14
0x180013320  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x180013327  mov     [rsp+2300h+var_2298], r14
0x18001332c  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x180013331  mov     [rsp+2300h+hKey], r13
0x180013336  mov     rcx, rsi; this
0x180013339  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18001333e  mov     [rsp+2300h+hKey], r14
0x180013343  jmp     loc_18001326B
0x180013348  cmp     [rbp+2200h+arg_20], r14d
0x18001334f  jnz     short loc_1800133AA
0x180013351  test    r12d, r12d
0x180013354  jz      short loc_1800133AA
0x180013356  mov     r9d, 20006h; unsigned int
0x18001335c  mov     [rsp+2300h+hKey], r14
0x180013361  xor     r8d, r8d; lpSubKey
0x180013364  mov     [rsp+2300h+var_22A0], r14
0x180013369  mov     rdx, r13; hKey
0x18001336c  mov     [rsp+2300h+var_2298], r14
0x180013371  lea     rcx, [rsp+2300h+hKey]; this
0x180013376  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001337b  test    eax, eax
0x18001337d  jnz     loc_1800136FA
0x180013383  mov     rcx, [rsp+2300h+hKey]; hKey
0x180013388  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x18001338f  call    cs:__imp_RegDeleteValueW
0x180013395  test    eax, 0FFFFFFFDh
0x18001339a  jnz     loc_1800136FA
0x1800133a0  lea     rcx, [rsp+2300h+hKey]; this
0x1800133a5  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800133aa  mov     rdx, rdi; unsigned __int16 *
0x1800133ad  mov     rcx, rsi; this
0x1800133b0  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800133b5  mov     ebx, eax
0x1800133b7  test    eax, eax
0x1800133b9  jns     loc_180013193
0x1800133bf  jmp     loc_1800136CB
0x1800133c4  mov     edx, 5Ch ; '\'; unsigned __int16
0x1800133c9  mov     rcx, rdi; lpsz
0x1800133cc  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1800133d1  test    rax, rax
0x1800133d4  jnz     loc_1800136C6
0x1800133da  test    r15d, r15d
0x1800133dd  jz      loc_180013503
0x1800133e3  mov     r9d, 2001Fh; unsigned int
0x1800133e9  lea     rcx, [rsp+2300h+var_2290]; this
0x1800133ee  mov     r8, rdi; lpSubKey
0x1800133f1  mov     rdx, r13; hKey
0x1800133f4  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800133f9  test    eax, eax
0x1800133fb  jz      short loc_18001347C
0x1800133fd  mov     r9d, 20019h; unsigned int
0x180013403  lea     rcx, [rsp+2300h+var_2290]; this
0x180013408  mov     r8, rdi; lpSubKey
0x18001340b  mov     rdx, r13; hKey
0x18001340e  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180013413  test    eax, eax
0x180013415  jz      short loc_18001347C
0x180013417  lea     rax, [rbp+2200h+dwDisposition]
0x18001341b  mov     [rbp+2200h+dwDisposition], r14d
0x18001341f  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x180013424  xor     r9d, r9d; lpClass
0x180013427  lea     rax, [rbp+2200h+var_2270]
0x18001342b  mov     [rbp+2200h+var_2270], r14
0x18001342f  mov     [rsp+2300h+phkResult], rax; phkResult
0x180013434  xor     r8d, r8d; Reserved
0x180013437  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18001343c  mov     rdx, rdi; lpSubKey
0x18001343f  mov     [rsp+2300h+samDesired], 2001Fh; samDesired
0x180013447  mov     rcx, r13; hKey
0x18001344a  mov     [rsp+2300h+dwOptions], r14d; dwOptions
0x18001344f  call    cs:__imp_RegCreateKeyExW
0x180013455  mov     ebx, eax
0x180013457  test    eax, eax
0x180013459  jnz     loc_18001370F
0x18001345f  lea     rcx, [rsp+2300h+var_2290]; this
0x180013464  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180013469  mov     ebx, eax
0x18001346b  mov     rax, [rbp+2200h+var_2270]
0x18001346f  mov     [rsp+2300h+var_2290], rax
0x180013474  test    ebx, ebx
0x180013476  jnz     loc_18001370F
0x18001347c  mov     rdx, rdi; unsigned __int16 *
0x18001347f  mov     rcx, rsi; this
0x180013482  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180013487  mov     ebx, eax
0x180013489  test    eax, eax
0x18001348b  js      loc_1800136CB
0x180013491  cmp     word ptr [rdi], 3Dh ; '='
0x180013495  jnz     short loc_1800134B4
0x180013497  mov     r9, rdi; unsigned __int16 *
0x18001349a  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x18001349f  xor     r8d, r8d; unsigned __int16 *
0x1800134a2  mov     rcx, rsi; this
0x1800134a5  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1800134aa  mov     ebx, eax
0x1800134ac  test    eax, eax
0x1800134ae  js      loc_1800136CB
0x1800134b4  cmp     word ptr [rdi], 7Bh ; '{'
0x1800134b8  jnz     loc_180013193
0x1800134be  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800134c2  inc     rax
0x1800134c5  cmp     [rdi+rax*2], r14w
0x1800134ca  jnz     short loc_1800134C2
0x1800134cc  cmp     rax, 1
0x1800134d0  jnz     loc_180013193
0x1800134d6  mov     r8, [rsp+2300h+var_2290]; HKEY
0x1800134db  mov     r9d, r15d; int
0x1800134de  mov     rdx, rdi; unsigned __int16 *
0x1800134e1  mov     [rsp+2300h+dwOptions], r14d; int
0x1800134e6  mov     rcx, rsi; this
0x1800134e9  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800134ee  mov     ebx, eax
0x1800134f0  test    eax, eax
0x1800134f2  js      loc_1800136CB
0x1800134f8  mov     rdx, rdi
0x1800134fb  mov     rcx, rsi
0x1800134fe  jmp     loc_180013189
0x180013503  cmp     [rbp+2200h+arg_20], r14d
0x18001350a  jnz     short loc_180013527
0x18001350c  mov     r9d, 20019h; unsigned int
0x180013512  lea     rcx, [rsp+2300h+var_2290]; this
0x180013517  mov     r8, rdi; lpSubKey
0x18001351a  mov     rdx, r13; hKey
0x18001351d  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180013522  mov     r14d, eax
0x180013525  jmp     short loc_18001352D
0x180013527  mov     r14d, 2
0x18001352d  test    r14d, r14d
0x180013530  lea     rcx, [rbp+2200h+Destination]; Destination
0x180013534  mov     r15d, 1
0x18001353a  mov     r8, rdi; Source
0x18001353d  cmovz   r15d, [rbp+2200h+arg_20]
0x180013545  mov     edx, 104h; SizeInWords
0x18001354a  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18001354e  call    cs:__imp_wcsncpy_s
0x180013554  mov     ecx, eax; int
0x180013556  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001355b  mov     rdx, rdi; unsigned __int16 *
0x18001355e  mov     rcx, rsi; this
0x180013561  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180013566  mov     ebx, eax
0x180013568  test    eax, eax
0x18001356a  js      loc_1800136CB
0x180013570  mov     rdx, rdi; unsigned __int16 *
0x180013573  mov     rcx, rsi; this
0x180013576  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18001357b  xor     ecx, ecx
0x18001357d  mov     ebx, eax
0x18001357f  test    eax, eax
0x180013581  js      loc_1800136CB
0x180013587  cmp     word ptr [rdi], 7Bh ; '{'
0x18001358b  jnz     short loc_1800135DC
0x18001358d  or      rax, 0FFFFFFFFFFFFFFFFh
0x180013591  inc     rax
0x180013594  cmp     [rdi+rax*2], cx
0x180013598  jnz     short loc_180013591
0x18001359a  cmp     rax, 1
0x18001359e  jnz     short loc_1800135DC
0x1800135a0  mov     r8, [rsp+2300h+var_2290]; HKEY
0x1800135a5  xor     r9d, r9d; int
0x1800135a8  mov     rdx, rdi; unsigned __int16 *
0x1800135ab  mov     [rsp+2300h+dwOptions], r15d; int
0x1800135b0  mov     rcx, rsi; this
0x1800135b3  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800135b8  mov     ebx, eax
0x1800135ba  test    eax, eax
0x1800135bc  jns     short loc_1800135C7
0x1800135be  test    r15d, r15d
0x1800135c1  jz      loc_1800136CB
0x1800135c7  mov     rdx, rdi; unsigned __int16 *
0x1800135ca  mov     rcx, rsi; this
0x1800135cd  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800135d2  mov     ebx, eax
0x1800135d4  test    eax, eax
0x1800135d6  js      loc_1800136CB
0x1800135dc  mov     r15d, [rsp+2300h+var_22B0]
0x1800135e1  cmp     r14d, 2
0x1800135e5  jz      loc_180013193
0x1800135eb  test    r14d, r14d
  ... truncated ...
```
