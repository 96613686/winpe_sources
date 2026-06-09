# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18000893c`
- end: `0x180008eeb`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1455`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config`

## callers

- `0x1800082ac`
- `0x18000893c`

## callees

- `0x18000586c`
- `0x180005fbc`
- `0x18000602c`
- `0x180006240`
- `0x1800063c4`
- `0x1800063f0`
- `0x180006b9c`
- `0x1800073e8`
- `0x180007c40`
- `0x180007da0`
- `0x180008198`
- `0x18000893c`
- `0x180009350`
- `0x180009420`
- `0x180039740`
- `0x180039800`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180008d00`
- `msvcrt!wcsncpy_s` at `0x180008d00`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180008b95`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180008b95`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800089b8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800089cb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008a9f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008ace`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800089b8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800089cb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008a9f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180008ace`

## string_xrefs

- `0x1800089c1`: `ForceRemove`
- `0x180008a95`: `NoRemove`
- `0x1800089ae`: `Delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
  HKEY *v14; // rcx
  int v15; // r12d
  LSTATUS v16; // eax
  unsigned __int16 *v17; // r9
  unsigned int v18; // eax
  __int64 v19; // rax
  int v20; // r14d
  int v21; // r15d
  errno_t v22; // eax
  ATL::CRegParser *v23; // rcx
  __int64 v24; // rax
  unsigned int v25; // ecx
  int HasSubKeys; // r14d
  DWORD v27; // eax
  unsigned int v29; // [rsp+20h] [rbp-E0h]
  HKEY v31[3]; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v32[3]; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v33[3]; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey[3]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v35[3]; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t Destination[264]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR ValueName[4096]; // [rsp+2D0h] [rbp+1D0h] BYREF

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
      while ( 1 )
      {
        if ( *v7 == 125 )
          goto LABEL_79;
        v11 = lstrcmpiW(v7, L"Delete");
        if ( lstrcmpiW(v7, L"ForceRemove") )
        {
          if ( v11 )
            break;
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        if ( !v5 )
          break;
        memset(v32, 0, sizeof(v32));
        if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        {
          ATL::CRegKey::Close((ATL::CRegKey *)v32);
LABEL_78:
          v10 = -2147352567;
          goto LABEL_79;
        }
        if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v12, v7) )
        {
          v32[0] = a3;
          ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v32, v7);
          v32[0] = 0;
        }
        if ( v11 )
        {
          ATL::CRegKey::Close((ATL::CRegKey *)v32);
          break;
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
        {
          v14 = (HKEY *)v32;
          goto LABEL_81;
        }
        v13 = ATL::CRegParser::SkipAssignment(v8, v7);
        v10 = v13;
        v14 = (HKEY *)v32;
LABEL_15:
        if ( v13 < 0 )
          goto LABEL_81;
        ATL::CRegKey::Close((ATL::CRegKey *)v14);
LABEL_40:
        if ( *v7 == 123 )
        {
          v19 = -1;
          do
            ++v19;
          while ( v7[v19] );
          if ( v19 == 1 )
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
      v15 = 1;
      if ( !lstrcmpiW(v7, L"NoRemove") )
      {
        v15 = 0;
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
        if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v31, a3, v7, 0x2001Fu)
          || !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v31, a3, v7, 0x20019u)
          || (v18 = ATL::CRegKey::Create((ATL::CRegKey *)v31, a3, v7, v17, v29, 0x2001Fu)) == 0 )
        {
          v10 = ATL::CRegParser::NextToken(v8, v7);
          if ( v10 < 0 )
            goto LABEL_79;
          if ( *v7 == 61 )
          {
            v10 = ATL::CRegParser::AddValue(v8, (struct ATL::CRegKey *)v31, 0, v7);
            if ( v10 < 0 )
              goto LABEL_79;
          }
          goto LABEL_40;
        }
LABEL_82:
        v25 = v18;
LABEL_64:
        v10 = ATL::AtlHresultFromWin32(v25);
        goto LABEL_79;
      }
      if ( a5 )
        v20 = 2;
      else
        v20 = ATL::CRegKey::Open((ATL::CRegKey *)v31, a3, v7, 0x20019u);
      v21 = 1;
      if ( !v20 )
        v21 = a5;
      v22 = wcsncpy_s(Destination, 0x104u, v7, 0xFFFFFFFFFFFFFFFFuLL);
      ATL::AtlCrtErrorCheck(v22);
      v10 = ATL::CRegParser::NextToken(v8, v7);
      if ( v10 < 0 )
        goto LABEL_79;
      v10 = ATL::CRegParser::SkipAssignment(v8, v7);
      v23 = 0;
      if ( v10 < 0 )
        goto LABEL_79;
      if ( *v7 == 123 )
      {
        v24 = -1;
        do
          ++v24;
        while ( v7[v24] );
        if ( v24 == 1 )
        {
          v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v31[0], 0, v21);
          if ( v10 < 0 && !v21 )
            goto LABEL_79;
          v10 = ATL::CRegParser::NextToken(v8, v7);
          if ( v10 < 0 )
            goto LABEL_79;
        }
      }
      v5 = a4;
      if ( v20 != 2 )
      {
        if ( v20 )
        {
          if ( !a5 )
          {
            v25 = v20;
            goto LABEL_64;
          }
        }
        else if ( a5 && ATL::CRegParser::HasSubKeys(v23, v31[0]) )
        {
          if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v23, Destination) && v15 )
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v31, Destination);
        }
        else
        {
          HasSubKeys = ATL::CRegParser::HasSubKeys(v23, v31[0]);
          v18 = ATL::CRegKey::Close((ATL::CRegKey *)v31);
          if ( v18 )
            goto LABEL_82;
          if ( v15 && !HasSubKeys )
          {
            v35[1] = 0;
            v35[2] = 0;
            v35[0] = a3;
            v27 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)v35, Destination);
            v35[0] = 0;
            if ( v27 )
            {
              v10 = ATL::AtlHresultFromWin32(v27);
              v14 = (HKEY *)v35;
              goto LABEL_81;
            }
            ATL::CRegKey::Close((ATL::CRegKey *)v35);
            v5 = a4;
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
      v33[1] = 0;
      v33[2] = 0;
      v33[0] = a3;
      v13 = ATL::CRegParser::AddValue(v8, (struct ATL::CRegKey *)v33, ValueName, v7);
      v10 = v13;
      v33[0] = 0;
      v14 = (HKEY *)v33;
      goto LABEL_15;
    }
    if ( a5 || !v15 )
      goto LABEL_31;
    memset(hKey, 0, sizeof(hKey));
    v16 = ATL::CRegKey::Open((ATL::CRegKey *)hKey, a3, 0, 0x20006u);
    if ( !v16 )
    {
      v16 = RegDeleteValueW(hKey[0], ValueName);
      if ( (v16 & 0xFFFFFFFD) == 0 )
      {
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
LABEL_31:
        Token = ATL::CRegParser::SkipAssignment(v8, v7);
        continue;
      }
    }
    break;
  }
  v10 = ATL::AtlHresultFromWin32(v16);
  v14 = hKey;
LABEL_81:
  ATL::CRegKey::Close((ATL::CRegKey *)v14);
LABEL_79:
  ATL::CRegKey::Close((ATL::CRegKey *)v31);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000893c  push    rbp
0x18000893e  push    rbx
0x18000893f  push    rsi
0x180008940  push    rdi
0x180008941  push    r12
0x180008943  push    r13
0x180008945  push    r14
0x180008947  push    r15
0x180008949  lea     rbp, [rsp-21E8h]
0x180008951  mov     eax, 22E8h
0x180008956  call    _alloca_probe
0x18000895b  sub     rsp, rax
0x18000895e  mov     rax, cs:__security_cookie
0x180008965  xor     rax, rsp
0x180008968  mov     [rbp+2220h+var_50], rax
0x18000896f  mov     r15d, r9d
0x180008972  mov     [rsp+2320h+var_22E0], r9d
0x180008977  mov     r13, r8
0x18000897a  mov     rdi, rdx
0x18000897d  mov     rsi, rcx
0x180008980  xor     r14d, r14d
0x180008983  mov     [rsp+2320h+var_22D8], r14
0x180008988  mov     [rsp+2320h+var_22D0], r14
0x18000898d  mov     [rsp+2320h+var_22C8], r14
0x180008992  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008997  test    eax, eax
0x180008999  mov     ebx, eax
0x18000899b  js      loc_180008E91
0x1800089a1  xor     r12d, r12d
0x1800089a4  cmp     word ptr [rdi], 7Dh ; '}'
0x1800089a8  jz      loc_180008E91
0x1800089ae  lea     rdx, String2; "Delete"
0x1800089b5  mov     rcx, rdi; lpString1
0x1800089b8  call    cs:__imp_lstrcmpiW
0x1800089be  mov     r14d, eax
0x1800089c1  lea     rdx, aForceremove; "ForceRemove"
0x1800089c8  mov     rcx, rdi; lpString1
0x1800089cb  call    cs:__imp_lstrcmpiW
0x1800089d1  test    eax, eax
0x1800089d3  jz      short loc_1800089DE
0x1800089d5  test    r14d, r14d
0x1800089d8  jnz     loc_180008A8F
0x1800089de  mov     rdx, rdi; unsigned __int16 *
0x1800089e1  mov     rcx, rsi; this
0x1800089e4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800089e9  mov     ebx, eax
0x1800089eb  test    eax, eax
0x1800089ed  js      loc_180008E91
0x1800089f3  test    r15d, r15d
0x1800089f6  jz      loc_180008A8F
0x1800089fc  mov     [rsp+2320h+var_22C0], r12
0x180008a01  mov     [rsp+2320h+var_22B8], r12
0x180008a06  mov     [rsp+2320h+var_22B0], r12
0x180008a0b  mov     edx, 5Ch ; '\'; unsigned __int16
0x180008a10  mov     rcx, rdi; lpsz
0x180008a13  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180008a18  test    rax, rax
0x180008a1b  jnz     loc_180008E82
0x180008a21  mov     rdx, rdi; unsigned __int16 *
0x180008a24  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x180008a29  test    eax, eax
0x180008a2b  jz      short loc_180008A44
0x180008a2d  mov     [rsp+2320h+var_22C0], r13
0x180008a32  mov     rdx, rdi; unsigned __int16 *
0x180008a35  lea     rcx, [rsp+2320h+var_22C0]; this
0x180008a3a  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180008a3f  mov     [rsp+2320h+var_22C0], r12
0x180008a44  test    r14d, r14d
0x180008a47  jnz     short loc_180008A85
0x180008a49  mov     rdx, rdi; unsigned __int16 *
0x180008a4c  mov     rcx, rsi; this
0x180008a4f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008a54  mov     ebx, eax
0x180008a56  xor     r14d, r14d
0x180008a59  test    eax, eax
0x180008a5b  js      loc_180008E7B
0x180008a61  mov     rdx, rdi; unsigned __int16 *
0x180008a64  mov     rcx, rsi; this
0x180008a67  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180008a6c  mov     ebx, eax
0x180008a6e  lea     rcx, [rsp+2320h+var_22C0]; this
0x180008a73  test    eax, eax
0x180008a75  js      loc_180008ECD
0x180008a7b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180008a80  jmp     loc_180008C66
0x180008a85  lea     rcx, [rsp+2320h+var_22C0]; this
0x180008a8a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180008a8f  mov     r12d, 1
0x180008a95  lea     rdx, aNoremove; "NoRemove"
0x180008a9c  mov     rcx, rdi; lpString1
0x180008a9f  call    cs:__imp_lstrcmpiW
0x180008aa5  xor     r14d, r14d
0x180008aa8  test    eax, eax
0x180008aaa  jnz     short loc_180008AC4
0x180008aac  mov     r12d, r14d
0x180008aaf  mov     rdx, rdi; unsigned __int16 *
0x180008ab2  mov     rcx, rsi; this
0x180008ab5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008aba  mov     ebx, eax
0x180008abc  test    eax, eax
0x180008abe  js      loc_180008E91
0x180008ac4  lea     rdx, aVal; "Val"
0x180008acb  mov     rcx, rdi; lpString1
0x180008ace  call    cs:__imp_lstrcmpiW
0x180008ad4  test    eax, eax
0x180008ad6  jnz     loc_180008BBF
0x180008adc  lea     rdx, [rbp+2220h+ValueName]; unsigned __int16 *
0x180008ae3  mov     rcx, rsi; this
0x180008ae6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008aeb  mov     ebx, eax
0x180008aed  test    eax, eax
0x180008aef  js      loc_180008E91
0x180008af5  mov     rdx, rdi; unsigned __int16 *
0x180008af8  mov     rcx, rsi; this
0x180008afb  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008b00  mov     ebx, eax
0x180008b02  test    eax, eax
0x180008b04  js      loc_180008E91
0x180008b0a  cmp     word ptr [rdi], 3Dh ; '='
0x180008b0e  jnz     loc_180008E8C
0x180008b14  test    r15d, r15d
0x180008b17  jz      short loc_180008B53
0x180008b19  mov     [rsp+2320h+var_22A8], r14
0x180008b1e  mov     [rbp+2220h+var_22A0], r14
0x180008b22  mov     [rbp+2220h+var_2298], r14
0x180008b26  mov     [rsp+2320h+var_22A8], r13
0x180008b2b  mov     r9, rdi; unsigned __int16 *
0x180008b2e  lea     r8, [rbp+2220h+ValueName]; unsigned __int16 *
0x180008b35  lea     rdx, [rsp+2320h+var_22A8]; struct ATL::CRegKey *
0x180008b3a  mov     rcx, rsi; this
0x180008b3d  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180008b42  mov     ebx, eax
0x180008b44  mov     [rsp+2320h+var_22A8], r14
0x180008b49  lea     rcx, [rsp+2320h+var_22A8]
0x180008b4e  jmp     loc_180008A73
0x180008b53  cmp     [rbp+2220h+arg_20], r14d
0x180008b5a  jnz     short loc_180008BAF
0x180008b5c  test    r12d, r12d
0x180008b5f  jz      short loc_180008BAF
0x180008b61  mov     [rbp+2220h+hKey], r14
0x180008b65  mov     [rbp+2220h+var_2288], r14
0x180008b69  mov     [rbp+2220h+var_2280], r14
0x180008b6d  mov     r9d, 20006h; unsigned int
0x180008b73  xor     r8d, r8d; lpSubKey
0x180008b76  mov     rdx, r13; hKey
0x180008b79  lea     rcx, [rbp+2220h+hKey]; this
0x180008b7d  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180008b82  test    eax, eax
0x180008b84  jnz     loc_180008EC0
0x180008b8a  lea     rdx, [rbp+2220h+ValueName]; lpValueName
0x180008b91  mov     rcx, [rbp+2220h+hKey]; hKey
0x180008b95  call    cs:__imp_RegDeleteValueW
0x180008b9b  test    eax, 0FFFFFFFDh
0x180008ba0  jnz     loc_180008EC0
0x180008ba6  lea     rcx, [rbp+2220h+hKey]; this
0x180008baa  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180008baf  mov     rdx, rdi; unsigned __int16 *
0x180008bb2  mov     rcx, rsi; this
0x180008bb5  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180008bba  jmp     loc_180008997
0x180008bbf  mov     edx, 5Ch ; '\'; unsigned __int16
0x180008bc4  mov     rcx, rdi; lpsz
0x180008bc7  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180008bcc  test    rax, rax
0x180008bcf  jnz     loc_180008E8C
0x180008bd5  test    r15d, r15d
0x180008bd8  jz      loc_180008CB5
0x180008bde  mov     ebx, 2001Fh
0x180008be3  mov     r9d, ebx; unsigned int
0x180008be6  mov     r8, rdi; lpSubKey
0x180008be9  mov     rdx, r13; hKey
0x180008bec  lea     rcx, [rsp+2320h+var_22D8]; this
0x180008bf1  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180008bf6  test    eax, eax
0x180008bf8  jz      short loc_180008C2E
0x180008bfa  lea     r9d, [rbx-6]; unsigned int
0x180008bfe  mov     r8, rdi; lpSubKey
0x180008c01  mov     rdx, r13; hKey
0x180008c04  lea     rcx, [rsp+2320h+var_22D8]; this
0x180008c09  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180008c0e  test    eax, eax
0x180008c10  jz      short loc_180008C2E
0x180008c12  mov     [rsp+2320h+var_22F8], ebx; unsigned int
0x180008c16  mov     r8, rdi; lpSubKey
0x180008c19  mov     rdx, r13; hKey
0x180008c1c  lea     rcx, [rsp+2320h+var_22D8]; this
0x180008c21  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x180008c26  test    eax, eax
0x180008c28  jnz     loc_180008ED4
0x180008c2e  mov     rdx, rdi; unsigned __int16 *
0x180008c31  mov     rcx, rsi; this
0x180008c34  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008c39  mov     ebx, eax
0x180008c3b  test    eax, eax
0x180008c3d  js      loc_180008E91
0x180008c43  cmp     word ptr [rdi], 3Dh ; '='
0x180008c47  jnz     short loc_180008C66
0x180008c49  mov     r9, rdi; unsigned __int16 *
0x180008c4c  xor     r8d, r8d; unsigned __int16 *
0x180008c4f  lea     rdx, [rsp+2320h+var_22D8]; struct ATL::CRegKey *
0x180008c54  mov     rcx, rsi; this
0x180008c57  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180008c5c  mov     ebx, eax
0x180008c5e  test    eax, eax
0x180008c60  js      loc_180008E91
0x180008c66  cmp     word ptr [rdi], 7Bh ; '{'
0x180008c6a  jnz     loc_1800089A1
0x180008c70  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008c74  inc     rax
0x180008c77  cmp     [rdi+rax*2], r14w
0x180008c7c  jnz     short loc_180008C74
0x180008c7e  cmp     rax, 1
0x180008c82  jnz     loc_1800089A1
0x180008c88  mov     [rsp+2320h+var_2300], r14d; int
0x180008c8d  mov     r9d, r15d; int
0x180008c90  mov     r8, [rsp+2320h+var_22D8]; HKEY
0x180008c95  mov     rdx, rdi; unsigned __int16 *
0x180008c98  mov     rcx, rsi; this
0x180008c9b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180008ca0  mov     ebx, eax
0x180008ca2  test    eax, eax
0x180008ca4  js      loc_180008E91
0x180008caa  mov     rdx, rdi
0x180008cad  mov     rcx, rsi
0x180008cb0  jmp     loc_180008992
0x180008cb5  cmp     [rbp+2220h+arg_20], r14d
0x180008cbc  jnz     short loc_180008CD9
0x180008cbe  mov     r9d, 20019h; unsigned int
0x180008cc4  mov     r8, rdi; lpSubKey
0x180008cc7  mov     rdx, r13; hKey
0x180008cca  lea     rcx, [rsp+2320h+var_22D8]; this
0x180008ccf  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180008cd4  mov     r14d, eax
0x180008cd7  jmp     short loc_180008CDF
0x180008cd9  mov     r14d, 2
0x180008cdf  mov     r15d, 1
0x180008ce5  test    r14d, r14d
0x180008ce8  cmovz   r15d, [rbp+2220h+arg_20]
0x180008cf0  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180008cf4  mov     r8, rdi; Source
0x180008cf7  mov     edx, 104h; SizeInWords
0x180008cfc  lea     rcx, [rbp+2220h+Destination]; Destination
0x180008d00  call    cs:__imp_wcsncpy_s
0x180008d06  mov     ecx, eax; int
0x180008d08  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180008d0d  mov     rdx, rdi; unsigned __int16 *
0x180008d10  mov     rcx, rsi; this
0x180008d13  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008d18  mov     ebx, eax
0x180008d1a  test    eax, eax
0x180008d1c  js      loc_180008E91
0x180008d22  mov     rdx, rdi; unsigned __int16 *
0x180008d25  mov     rcx, rsi; this
0x180008d28  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180008d2d  mov     ebx, eax
0x180008d2f  xor     ecx, ecx
0x180008d31  test    eax, eax
0x180008d33  js      loc_180008E91
0x180008d39  cmp     word ptr [rdi], 7Bh ; '{'
0x180008d3d  jnz     short loc_180008D8E
0x180008d3f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008d43  inc     rax
0x180008d46  cmp     [rdi+rax*2], cx
0x180008d4a  jnz     short loc_180008D43
0x180008d4c  cmp     rax, 1
0x180008d50  jnz     short loc_180008D8E
0x180008d52  mov     [rsp+2320h+var_2300], r15d; int
0x180008d57  xor     r9d, r9d; int
0x180008d5a  mov     r8, [rsp+2320h+var_22D8]; HKEY
0x180008d5f  mov     rdx, rdi; unsigned __int16 *
0x180008d62  mov     rcx, rsi; this
0x180008d65  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180008d6a  mov     ebx, eax
0x180008d6c  test    eax, eax
0x180008d6e  jns     short loc_180008D79
0x180008d70  test    r15d, r15d
0x180008d73  jz      loc_180008E91
0x180008d79  mov     rdx, rdi; unsigned __int16 *
0x180008d7c  mov     rcx, rsi; this
0x180008d7f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008d84  mov     ebx, eax
0x180008d86  test    eax, eax
0x180008d88  js      loc_180008E91
0x180008d8e  cmp     r14d, 2
0x180008d92  mov     r15d, [rsp+2320h+var_22E0]
0x180008d97  jz      loc_1800089A1
0x180008d9d  test    r14d, r14d
0x180008da0  jz      short loc_180008DC1
0x180008da2  xor     r12d, r12d
0x180008da5  cmp     [rbp+2220h+arg_20], r12d
0x180008dac  jnz     loc_1800089A4
0x180008db2  mov     ecx, r14d; unsigned int
0x180008db5  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180008dba  mov     ebx, eax
0x180008dbc  jmp     loc_180008E91
0x180008dc1  xor     r14d, r14d
0x180008dc4  cmp     [rbp+2220h+arg_20], r14d
0x180008dcb  jz      short loc_180008E0B
0x180008dcd  mov     rdx, [rsp+2320h+var_22D8]; HKEY
0x180008dd2  call    ?HasSubKeys@CRegParser@ATL@@IEAAHPEAUHKEY__@@@Z; ATL::CRegParser::HasSubKeys(HKEY__ *)
  ... truncated ...
```
