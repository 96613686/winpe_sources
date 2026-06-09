# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180007e04`
- end: `0x180008385`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1409`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800079dc`
- `0x180007e04`

## callees

- `0x180003dbc`
- `0x180004430`
- `0x18000450c`
- `0x180004d2c`
- `0x180004f44`
- `0x180004f70`
- `0x1800063fc`
- `0x180006bac`
- `0x1800072f0`
- `0x18000747c`
- `0x1800078c8`
- `0x180007e04`
- `0x180008730`
- `0x180008800`
- `0x18002b4a0`
- `0x18002b560`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x1800081c5`
- `msvcrt!wcsncpy_s` at `0x1800081c5`
- `KERNEL32!lstrcmpiW` at `0x180007e78`
- `KERNEL32!lstrcmpiW` at `0x180007e8b`
- `KERNEL32!lstrcmpiW` at `0x180007f5c`
- `KERNEL32!lstrcmpiW` at `0x180007f8b`
- `KERNEL32!lstrcmpiW` at `0x180007e78`
- `KERNEL32!lstrcmpiW` at `0x180007e8b`
- `KERNEL32!lstrcmpiW` at `0x180007f5c`
- `KERNEL32!lstrcmpiW` at `0x180007f8b`
- `ADVAPI32!RegDeleteValueW` at `0x180008055`
- `ADVAPI32!RegDeleteValueW` at `0x180008055`

## string_xrefs

- `0x180007e81`: `ForceRemove`
- `0x180007f52`: `NoRemove`
- `0x180007e6e`: `Delete`

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
0x180007e04  push    rbp
0x180007e06  push    rbx
0x180007e07  push    rsi
0x180007e08  push    rdi
0x180007e09  push    r12
0x180007e0b  push    r13
0x180007e0d  push    r14
0x180007e0f  push    r15
0x180007e11  lea     rbp, [rsp-21A8h]
0x180007e19  mov     eax, 22A8h
0x180007e1e  call    _alloca_probe
0x180007e23  sub     rsp, rax
0x180007e26  mov     rax, cs:__security_cookie
0x180007e2d  xor     rax, rsp
0x180007e30  mov     [rbp+21E0h+var_50], rax
0x180007e37  mov     r15d, r9d
0x180007e3a  mov     [rsp+22E0h+var_22A0], r9d
0x180007e3f  mov     r13, r8
0x180007e42  mov     rdi, rdx
0x180007e45  mov     rsi, rcx
0x180007e48  xor     r12d, r12d
0x180007e4b  mov     [rsp+22E0h+var_2280], r12
0x180007e50  mov     [rsp+22E0h+var_2278], r12
0x180007e55  mov     [rsp+22E0h+var_2270], r12
0x180007e5a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007e5f  mov     ebx, eax
0x180007e61  test    eax, eax
0x180007e63  js      loc_180008339
0x180007e69  jmp     loc_1800082C0
0x180007e6e  lea     rdx, String2; "Delete"
0x180007e75  mov     rcx, rdi; lpString1
0x180007e78  call    cs:__imp_lstrcmpiW
0x180007e7e  mov     r14d, eax
0x180007e81  lea     rdx, aForceremove; "ForceRemove"
0x180007e88  mov     rcx, rdi; lpString1
0x180007e8b  call    cs:__imp_lstrcmpiW
0x180007e91  test    eax, eax
0x180007e93  jz      short loc_180007E9E
0x180007e95  test    r14d, r14d
0x180007e98  jnz     loc_180007F4C
0x180007e9e  mov     rdx, rdi; unsigned __int16 *
0x180007ea1  mov     rcx, rsi; this
0x180007ea4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007ea9  mov     ebx, eax
0x180007eab  test    eax, eax
0x180007ead  js      loc_180008339
0x180007eb3  test    r15d, r15d
0x180007eb6  jz      loc_180007F4C
0x180007ebc  mov     [rsp+22E0h+hKey], r12
0x180007ec1  mov     [rsp+22E0h+var_2290], r12
0x180007ec6  mov     [rsp+22E0h+var_2288], r12
0x180007ecb  mov     edx, 5Ch ; '\'; unsigned __int16
0x180007ed0  mov     rcx, rdi; lpsz
0x180007ed3  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180007ed8  test    rax, rax
0x180007edb  jnz     loc_18000832A
0x180007ee1  mov     rdx, rdi; unsigned __int16 *
0x180007ee4  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x180007ee9  test    eax, eax
0x180007eeb  jz      short loc_180007F04
0x180007eed  mov     [rsp+22E0h+hKey], r13
0x180007ef2  mov     rdx, rdi; unsigned __int16 *
0x180007ef5  lea     rcx, [rsp+22E0h+hKey]; this
0x180007efa  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180007eff  mov     [rsp+22E0h+hKey], r12
0x180007f04  test    r14d, r14d
0x180007f07  jnz     short loc_180007F42
0x180007f09  mov     rdx, rdi; unsigned __int16 *
0x180007f0c  mov     rcx, rsi; this
0x180007f0f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007f14  mov     ebx, eax
0x180007f16  test    eax, eax
0x180007f18  js      loc_180008371
0x180007f1e  mov     rdx, rdi; unsigned __int16 *
0x180007f21  mov     rcx, rsi; this
0x180007f24  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180007f29  mov     ebx, eax
0x180007f2b  test    eax, eax
0x180007f2d  lea     rcx, [rsp+22E0h+hKey]; this
0x180007f32  js      loc_180008376
0x180007f38  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180007f3d  jmp     loc_18000812B
0x180007f42  lea     rcx, [rsp+22E0h+hKey]; this
0x180007f47  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180007f4c  mov     r12d, 1
0x180007f52  lea     rdx, aNoremove; "NoRemove"
0x180007f59  mov     rcx, rdi; lpString1
0x180007f5c  call    cs:__imp_lstrcmpiW
0x180007f62  xor     r14d, r14d
0x180007f65  test    eax, eax
0x180007f67  jnz     short loc_180007F81
0x180007f69  mov     r12d, r14d
0x180007f6c  mov     rdx, rdi; unsigned __int16 *
0x180007f6f  mov     rcx, rsi; this
0x180007f72  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007f77  mov     ebx, eax
0x180007f79  test    eax, eax
0x180007f7b  js      loc_180008339
0x180007f81  lea     rdx, aVal; "Val"
0x180007f88  mov     rcx, rdi; lpString1
0x180007f8b  call    cs:__imp_lstrcmpiW
0x180007f91  test    eax, eax
0x180007f93  jnz     loc_180008085
0x180007f99  lea     rdx, [rbp+21E0h+ValueName]; unsigned __int16 *
0x180007fa0  mov     rcx, rsi; this
0x180007fa3  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007fa8  mov     ebx, eax
0x180007faa  test    eax, eax
0x180007fac  js      loc_180008339
0x180007fb2  mov     rdx, rdi; unsigned __int16 *
0x180007fb5  mov     rcx, rsi; this
0x180007fb8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180007fbd  mov     ebx, eax
0x180007fbf  test    eax, eax
0x180007fc1  js      loc_180008339
0x180007fc7  cmp     word ptr [rdi], 3Dh ; '='
0x180007fcb  jnz     loc_180008334
0x180007fd1  test    r15d, r15d
0x180007fd4  jz      short loc_18000800B
0x180007fd6  xor     r12d, r12d
0x180007fd9  mov     [rsp+22E0h+var_2290], r12
0x180007fde  mov     [rsp+22E0h+var_2288], r12
0x180007fe3  mov     [rsp+22E0h+hKey], r13
0x180007fe8  mov     r9, rdi; unsigned __int16 *
0x180007feb  lea     r8, [rbp+21E0h+ValueName]; unsigned __int16 *
0x180007ff2  lea     rdx, [rsp+22E0h+hKey]; struct ATL::CRegKey *
0x180007ff7  mov     rcx, rsi; this
0x180007ffa  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180007fff  mov     ebx, eax
0x180008001  mov     [rsp+22E0h+hKey], r12
0x180008006  jmp     loc_180007F2B
0x18000800b  cmp     [rbp+21E0h+arg_20], r14d
0x180008012  jnz     short loc_180008072
0x180008014  test    r12d, r12d
0x180008017  jz      short loc_180008072
0x180008019  xor     r12d, r12d
0x18000801c  mov     [rsp+22E0h+hKey], r12
0x180008021  mov     [rsp+22E0h+var_2290], r12
0x180008026  mov     [rsp+22E0h+var_2288], r12
0x18000802b  mov     r9d, 20006h; unsigned int
0x180008031  xor     r8d, r8d; lpSubKey
0x180008034  mov     rdx, r13; hKey
0x180008037  lea     rcx, [rsp+22E0h+hKey]; this
0x18000803c  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180008041  test    eax, eax
0x180008043  jnz     loc_180008368
0x180008049  lea     rdx, [rbp+21E0h+ValueName]; lpValueName
0x180008050  mov     rcx, [rsp+22E0h+hKey]; hKey
0x180008055  call    cs:__imp_RegDeleteValueW
0x18000805b  test    eax, 0FFFFFFFDh
0x180008060  jnz     loc_180008368
0x180008066  lea     rcx, [rsp+22E0h+hKey]; this
0x18000806b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180008070  jmp     short loc_180008075
0x180008072  xor     r12d, r12d
0x180008075  mov     rdx, rdi; unsigned __int16 *
0x180008078  mov     rcx, rsi; this
0x18000807b  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180008080  jmp     loc_180007E5F
0x180008085  mov     edx, 5Ch ; '\'; unsigned __int16
0x18000808a  mov     rcx, rdi; lpsz
0x18000808d  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180008092  test    rax, rax
0x180008095  jnz     loc_180008334
0x18000809b  test    r15d, r15d
0x18000809e  jz      loc_18000817A
0x1800080a4  mov     r9d, 2001Fh; unsigned int
0x1800080aa  mov     r8, rdi; lpSubKey
0x1800080ad  mov     rdx, r13; hKey
0x1800080b0  lea     rcx, [rsp+22E0h+var_2280]; this
0x1800080b5  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800080ba  xor     r12d, r12d
0x1800080bd  test    eax, eax
0x1800080bf  jz      short loc_1800080F3
0x1800080c1  mov     r9d, 20019h; unsigned int
0x1800080c7  mov     r8, rdi; lpSubKey
0x1800080ca  mov     rdx, r13; hKey
0x1800080cd  lea     rcx, [rsp+22E0h+var_2280]; this
0x1800080d2  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800080d7  test    eax, eax
0x1800080d9  jz      short loc_1800080F3
0x1800080db  mov     r8, rdi; lpSubKey
0x1800080de  mov     rdx, r13; hKey
0x1800080e1  lea     rcx, [rsp+22E0h+var_2280]; this
0x1800080e6  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x1800080eb  test    eax, eax
0x1800080ed  jnz     loc_18000837D
0x1800080f3  mov     rdx, rdi; unsigned __int16 *
0x1800080f6  mov     rcx, rsi; this
0x1800080f9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800080fe  mov     ebx, eax
0x180008100  test    eax, eax
0x180008102  js      loc_180008339
0x180008108  cmp     word ptr [rdi], 3Dh ; '='
0x18000810c  jnz     short loc_18000812B
0x18000810e  mov     r9, rdi; unsigned __int16 *
0x180008111  xor     r8d, r8d; unsigned __int16 *
0x180008114  lea     rdx, [rsp+22E0h+var_2280]; struct ATL::CRegKey *
0x180008119  mov     rcx, rsi; this
0x18000811c  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180008121  mov     ebx, eax
0x180008123  test    eax, eax
0x180008125  js      loc_180008339
0x18000812b  cmp     word ptr [rdi], 7Bh ; '{'
0x18000812f  jnz     loc_1800082C0
0x180008135  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008139  inc     rax
0x18000813c  cmp     [rdi+rax*2], r12w
0x180008141  jnz     short loc_180008139
0x180008143  cmp     rax, 1
0x180008147  jnz     loc_1800082C0
0x18000814d  mov     [rsp+22E0h+var_22C0], r12d; int
0x180008152  mov     r9d, r15d; int
0x180008155  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x18000815a  mov     rdx, rdi; unsigned __int16 *
0x18000815d  mov     rcx, rsi; this
0x180008160  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180008165  mov     ebx, eax
0x180008167  test    eax, eax
0x180008169  js      loc_180008339
0x18000816f  mov     rdx, rdi
0x180008172  mov     rcx, rsi
0x180008175  jmp     loc_180007E5A
0x18000817a  cmp     [rbp+21E0h+arg_20], r14d
0x180008181  jnz     short loc_18000819E
0x180008183  mov     r9d, 20019h; unsigned int
0x180008189  mov     r8, rdi; lpSubKey
0x18000818c  mov     rdx, r13; hKey
0x18000818f  lea     rcx, [rsp+22E0h+var_2280]; this
0x180008194  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180008199  mov     r14d, eax
0x18000819c  jmp     short loc_1800081A4
0x18000819e  mov     r14d, 2
0x1800081a4  mov     r15d, 1
0x1800081aa  test    r14d, r14d
0x1800081ad  cmovz   r15d, [rbp+21E0h+arg_20]
0x1800081b5  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800081b9  mov     r8, rdi; Source
0x1800081bc  mov     edx, 104h; SizeInWords
0x1800081c1  lea     rcx, [rbp+21E0h+Destination]; Destination
0x1800081c5  call    cs:__imp_wcsncpy_s
0x1800081cb  mov     ecx, eax; int
0x1800081cd  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800081d2  mov     rdx, rdi; unsigned __int16 *
0x1800081d5  mov     rcx, rsi; this
0x1800081d8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800081dd  mov     ebx, eax
0x1800081df  test    eax, eax
0x1800081e1  js      loc_180008339
0x1800081e7  mov     rdx, rdi; unsigned __int16 *
0x1800081ea  mov     rcx, rsi; this
0x1800081ed  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800081f2  mov     ebx, eax
0x1800081f4  xor     ecx, ecx; this
0x1800081f6  test    eax, eax
0x1800081f8  js      loc_180008339
0x1800081fe  cmp     word ptr [rdi], 7Bh ; '{'
0x180008202  jnz     short loc_180008258
0x180008204  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008208  inc     rax
0x18000820b  cmp     [rdi+rax*2], cx
0x18000820f  jnz     short loc_180008208
0x180008211  cmp     rax, 1
0x180008215  jnz     short loc_180008258
0x180008217  mov     [rsp+22E0h+var_22C0], r15d; int
0x18000821c  xor     r9d, r9d; int
0x18000821f  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x180008224  mov     rdx, rdi; unsigned __int16 *
0x180008227  mov     rcx, rsi; this
0x18000822a  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000822f  mov     ebx, eax
0x180008231  test    eax, eax
0x180008233  jns     short loc_18000823E
0x180008235  test    r15d, r15d
0x180008238  jz      loc_180008339
0x18000823e  mov     rdx, rdi; unsigned __int16 *
0x180008241  mov     rcx, rsi; this
0x180008244  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008249  mov     ebx, eax
0x18000824b  xor     r15d, r15d
0x18000824e  test    eax, eax
0x180008250  js      loc_180008339
0x180008256  jmp     short loc_18000825B
0x180008258  xor     r15d, r15d
0x18000825b  cmp     r14d, 2
0x18000825f  jz      short loc_1800082B8
0x180008261  test    r14d, r14d
0x180008264  jz      short loc_180008281
0x180008266  xor     r12d, r12d
0x180008269  cmp     [rbp+21E0h+arg_20], r12d
0x180008270  jnz     short loc_1800082BB
0x180008272  mov     ecx, r14d; unsigned int
0x180008275  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18000827a  mov     ebx, eax
0x18000827c  jmp     loc_180008339
0x180008281  cmp     [rbp+21E0h+arg_20], r15d
0x180008288  jz      short loc_1800082CC
0x18000828a  mov     rdx, [rsp+22E0h+var_2280]; HKEY
0x18000828f  call    ?HasSubKeys@CRegParser@ATL@@IEAAHPEAUHKEY__@@@Z; ATL::CRegParser::HasSubKeys(HKEY__ *)
0x180008294  test    eax, eax
  ... truncated ...
```
