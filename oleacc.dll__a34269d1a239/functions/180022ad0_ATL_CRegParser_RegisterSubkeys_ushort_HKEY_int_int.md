# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180022ad0`
- end: `0x180023065`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1429`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800227ac`
- `0x180022ad0`

## callees

- `0x18001e0a4`
- `0x18001e4c0`
- `0x180020c50`
- `0x18002132c`
- `0x18002139c`
- `0x180021490`
- `0x1800215f0`
- `0x180021784`
- `0x180021dd8`
- `0x180022200`
- `0x180022360`
- `0x180022698`
- `0x180022ad0`
- `0x180023188`
- `0x180023258`
- `0x180047f80`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180022e92`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180022e92`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180022d26`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180022d26`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180022b4c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180022b5f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180022c33`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180022c62`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180022b4c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180022b5f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180022c33`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180022c62`

## string_xrefs

- `0x180022b55`: `ForceRemove`
- `0x180022c29`: `NoRemove`
- `0x180022b42`: `Delete`

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
  int v21; // eax
  ATL::CRegParser *v22; // rcx
  __int64 v23; // rax
  unsigned int v24; // ecx
  int HasSubKeys; // r14d
  __int64 v27; // [rsp+20h] [rbp-E0h]
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
      goto LABEL_78;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( *v7 == 125 )
          goto LABEL_78;
        v11 = lstrcmpiW(v7, L"Delete");
        if ( lstrcmpiW(v7, L"ForceRemove") )
        {
          if ( v11 )
            break;
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_78;
        if ( !v5 )
          break;
        hKey = 0;
        v32 = 0;
        v33 = 0;
        if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        {
          ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_77:
          v10 = -2147352567;
          goto LABEL_78;
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
          goto LABEL_80;
        v13 = ATL::CRegParser::SkipAssignment(v8, v7);
        v10 = v13;
LABEL_15:
        if ( v13 < 0 )
          goto LABEL_80;
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
              goto LABEL_78;
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
          goto LABEL_78;
      }
      if ( !lstrcmpiW(v7, L"Val") )
        break;
      if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        goto LABEL_77;
      if ( v5 )
      {
        if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v34, a3, v7, 0x2001Fu)
          || !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v34, a3, v7, 0x20019u)
          || (v17 = ATL::CRegKey::Create((ATL::CRegKey *)v34, a3, v7, v16, v27, 0x2001Fu, v28, v29)) == 0 )
        {
          v10 = ATL::CRegParser::NextToken(v8, v7);
          if ( v10 < 0 )
            goto LABEL_78;
          if ( *v7 == 61 )
          {
            v10 = ATL::CRegParser::AddValue(v8, v34, 0, v7);
            if ( v10 < 0 )
              goto LABEL_78;
          }
          goto LABEL_40;
        }
LABEL_81:
        v24 = v17;
LABEL_64:
        v10 = ATL::AtlHresultFromWin32(v24);
        goto LABEL_78;
      }
      if ( a5 )
        v19 = 2;
      else
        v19 = ATL::CRegKey::Open((ATL::CRegKey *)v34, a3, v7, 0x20019u);
      v20 = 1;
      if ( !v19 )
        v20 = a5;
      v21 = _o_wcsncpy_s(v35, 260, v7, -1, v27);
      ATL::AtlCrtErrorCheck(v21);
      v10 = ATL::CRegParser::NextToken(v8, v7);
      if ( v10 < 0 )
        goto LABEL_78;
      v10 = ATL::CRegParser::SkipAssignment(v8, v7);
      v22 = 0;
      if ( v10 < 0 )
        goto LABEL_78;
      if ( *v7 == 123 )
      {
        v23 = -1;
        do
          ++v23;
        while ( v7[v23] );
        if ( v23 == 1 )
        {
          v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v34[0], 0, v20);
          if ( v10 < 0 && !v20 )
            goto LABEL_78;
          v10 = ATL::CRegParser::NextToken(v8, v7);
          if ( v10 < 0 )
            goto LABEL_78;
        }
      }
      v5 = a4;
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
        else if ( a5 && ATL::CRegParser::HasSubKeys(v22, v34[0]) )
        {
          if ( ATL::CRegParser::CanForceRemoveKey(v22, v35) && v14 )
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v34, v35);
        }
        else
        {
          HasSubKeys = ATL::CRegParser::HasSubKeys(v22, v34[0]);
          v17 = ATL::CRegKey::Close((ATL::CRegKey *)v34);
          if ( v17 )
            goto LABEL_81;
          if ( v14 && !HasSubKeys )
          {
            v32 = 0;
            v33 = 0;
            hKey = a3;
            v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, v35);
            hKey = 0;
            if ( v15 )
              goto LABEL_79;
            ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
          }
        }
      }
    }
    v10 = ATL::CRegParser::NextToken(v8, ValueName);
    if ( v10 < 0 )
      goto LABEL_78;
    v10 = ATL::CRegParser::NextToken(v8, v7);
    if ( v10 < 0 )
      goto LABEL_78;
    if ( *v7 != 61 )
      goto LABEL_77;
    if ( v5 )
    {
      v32 = 0;
      v33 = 0;
      hKey = a3;
      v13 = ATL::CRegParser::AddValue(v8, &hKey, ValueName, v7);
      v10 = v13;
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
LABEL_79:
  v10 = ATL::AtlHresultFromWin32(v15);
LABEL_80:
  ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_78:
  ATL::CRegKey::Close((ATL::CRegKey *)v34);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180022ad0  push    rbp
0x180022ad2  push    rbx
0x180022ad3  push    rsi
0x180022ad4  push    rdi
0x180022ad5  push    r12
0x180022ad7  push    r13
0x180022ad9  push    r14
0x180022adb  push    r15
0x180022add  lea     rbp, [rsp-21A8h]
0x180022ae5  mov     eax, 22A8h
0x180022aea  call    _alloca_probe
0x180022aef  sub     rsp, rax
0x180022af2  mov     rax, cs:__security_cookie
0x180022af9  xor     rax, rsp
0x180022afc  mov     [rbp+21E0h+var_50], rax
0x180022b03  mov     r15d, r9d
0x180022b06  mov     [rsp+22E0h+var_22A0], r9d
0x180022b0b  mov     r13, r8
0x180022b0e  mov     rdi, rdx
0x180022b11  mov     rsi, rcx
0x180022b14  xor     r14d, r14d
0x180022b17  mov     [rsp+22E0h+var_2280], r14
0x180022b1c  mov     [rsp+22E0h+var_2278], r14
0x180022b21  mov     [rsp+22E0h+var_2270], r14
0x180022b26  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180022b2b  test    eax, eax
0x180022b2d  mov     ebx, eax
0x180022b2f  js      loc_180023019
0x180022b35  xor     r12d, r12d
0x180022b38  cmp     word ptr [rdi], 7Dh ; '}'
0x180022b3c  jz      loc_180023019
0x180022b42  lea     rdx, aDelete; "Delete"
0x180022b49  mov     rcx, rdi; lpString1
0x180022b4c  call    cs:__imp_lstrcmpiW
0x180022b52  mov     r14d, eax
0x180022b55  lea     rdx, aForceremove; "ForceRemove"
0x180022b5c  mov     rcx, rdi; lpString1
0x180022b5f  call    cs:__imp_lstrcmpiW
0x180022b65  test    eax, eax
0x180022b67  jz      short loc_180022B72
0x180022b69  test    r14d, r14d
0x180022b6c  jnz     loc_180022C23
0x180022b72  mov     rdx, rdi; unsigned __int16 *
0x180022b75  mov     rcx, rsi; this
0x180022b78  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180022b7d  mov     ebx, eax
0x180022b7f  test    eax, eax
0x180022b81  js      loc_180023019
0x180022b87  test    r15d, r15d
0x180022b8a  jz      loc_180022C23
0x180022b90  mov     [rsp+22E0h+hKey], r12
0x180022b95  mov     [rsp+22E0h+var_2290], r12
0x180022b9a  mov     [rsp+22E0h+var_2288], r12
0x180022b9f  mov     edx, 5Ch ; '\'; unsigned __int16
0x180022ba4  mov     rcx, rdi; lpsz
0x180022ba7  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180022bac  test    rax, rax
0x180022baf  jnz     loc_18002300A
0x180022bb5  mov     rdx, rdi; unsigned __int16 *
0x180022bb8  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x180022bbd  test    eax, eax
0x180022bbf  jz      short loc_180022BD8
0x180022bc1  mov     [rsp+22E0h+hKey], r13
0x180022bc6  mov     rdx, rdi; unsigned __int16 *
0x180022bc9  lea     rcx, [rsp+22E0h+hKey]; this
0x180022bce  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180022bd3  mov     [rsp+22E0h+hKey], r12
0x180022bd8  test    r14d, r14d
0x180022bdb  jnz     short loc_180022C19
0x180022bdd  mov     rdx, rdi; unsigned __int16 *
0x180022be0  mov     rcx, rsi; this
0x180022be3  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180022be8  mov     ebx, eax
0x180022bea  xor     r14d, r14d
0x180022bed  test    eax, eax
0x180022bef  js      loc_180023051
0x180022bf5  mov     rdx, rdi; unsigned __int16 *
0x180022bf8  mov     rcx, rsi; this
0x180022bfb  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180022c00  mov     ebx, eax
0x180022c02  test    eax, eax
0x180022c04  lea     rcx, [rsp+22E0h+hKey]; this
0x180022c09  js      loc_180023056
0x180022c0f  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180022c14  jmp     loc_180022DF8
0x180022c19  lea     rcx, [rsp+22E0h+hKey]; this
0x180022c1e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180022c23  mov     r12d, 1
0x180022c29  lea     rdx, aNoremove; "NoRemove"
0x180022c30  mov     rcx, rdi; lpString1
0x180022c33  call    cs:__imp_lstrcmpiW
0x180022c39  xor     r14d, r14d
0x180022c3c  test    eax, eax
0x180022c3e  jnz     short loc_180022C58
0x180022c40  mov     r12d, r14d
0x180022c43  mov     rdx, rdi; unsigned __int16 *
0x180022c46  mov     rcx, rsi; this
0x180022c49  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180022c4e  mov     ebx, eax
0x180022c50  test    eax, eax
0x180022c52  js      loc_180023019
0x180022c58  lea     rdx, aVal; "Val"
0x180022c5f  mov     rcx, rdi; lpString1
0x180022c62  call    cs:__imp_lstrcmpiW
0x180022c68  test    eax, eax
0x180022c6a  jnz     loc_180022D51
0x180022c70  lea     rdx, [rbp+21E0h+ValueName]; unsigned __int16 *
0x180022c77  mov     rcx, rsi; this
0x180022c7a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180022c7f  mov     ebx, eax
0x180022c81  test    eax, eax
0x180022c83  js      loc_180023019
0x180022c89  mov     rdx, rdi; unsigned __int16 *
0x180022c8c  mov     rcx, rsi; this
0x180022c8f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180022c94  mov     ebx, eax
0x180022c96  test    eax, eax
0x180022c98  js      loc_180023019
0x180022c9e  cmp     word ptr [rdi], 3Dh ; '='
0x180022ca2  jnz     loc_180023014
0x180022ca8  test    r15d, r15d
0x180022cab  jz      short loc_180022CDF
0x180022cad  mov     [rsp+22E0h+var_2290], r14
0x180022cb2  mov     [rsp+22E0h+var_2288], r14
0x180022cb7  mov     [rsp+22E0h+hKey], r13
0x180022cbc  mov     r9, rdi; unsigned __int16 *
0x180022cbf  lea     r8, [rbp+21E0h+ValueName]; unsigned __int16 *
0x180022cc6  lea     rdx, [rsp+22E0h+hKey]; struct ATL::CRegKey *
0x180022ccb  mov     rcx, rsi; this
0x180022cce  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180022cd3  mov     ebx, eax
0x180022cd5  mov     [rsp+22E0h+hKey], r14
0x180022cda  jmp     loc_180022C02
0x180022cdf  cmp     [rbp+21E0h+arg_20], r14d
0x180022ce6  jnz     short loc_180022D41
0x180022ce8  test    r12d, r12d
0x180022ceb  jz      short loc_180022D41
0x180022ced  mov     [rsp+22E0h+hKey], r14
0x180022cf2  mov     [rsp+22E0h+var_2290], r14
0x180022cf7  mov     [rsp+22E0h+var_2288], r14
0x180022cfc  mov     r9d, 20006h; unsigned int
0x180022d02  xor     r8d, r8d; lpSubKey
0x180022d05  mov     rdx, r13; hKey
0x180022d08  lea     rcx, [rsp+22E0h+hKey]; this
0x180022d0d  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180022d12  test    eax, eax
0x180022d14  jnz     loc_180023048
0x180022d1a  lea     rdx, [rbp+21E0h+ValueName]; lpValueName
0x180022d21  mov     rcx, [rsp+22E0h+hKey]; hKey
0x180022d26  call    cs:__imp_RegDeleteValueW
0x180022d2c  test    eax, 0FFFFFFFDh
0x180022d31  jnz     loc_180023048
0x180022d37  lea     rcx, [rsp+22E0h+hKey]; this
0x180022d3c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180022d41  mov     rdx, rdi; unsigned __int16 *
0x180022d44  mov     rcx, rsi; this
0x180022d47  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180022d4c  jmp     loc_180022B2B
0x180022d51  mov     edx, 5Ch ; '\'; unsigned __int16
0x180022d56  mov     rcx, rdi; lpsz
0x180022d59  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180022d5e  test    rax, rax
0x180022d61  jnz     loc_180023014
0x180022d67  test    r15d, r15d
0x180022d6a  jz      loc_180022E47
0x180022d70  mov     ebx, 2001Fh
0x180022d75  mov     r9d, ebx; unsigned int
0x180022d78  mov     r8, rdi; lpSubKey
0x180022d7b  mov     rdx, r13; hKey
0x180022d7e  lea     rcx, [rsp+22E0h+var_2280]; this
0x180022d83  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180022d88  test    eax, eax
0x180022d8a  jz      short loc_180022DC0
0x180022d8c  lea     r9d, [rbx-6]; unsigned int
0x180022d90  mov     r8, rdi; lpSubKey
0x180022d93  mov     rdx, r13; hKey
0x180022d96  lea     rcx, [rsp+22E0h+var_2280]; this
0x180022d9b  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180022da0  test    eax, eax
0x180022da2  jz      short loc_180022DC0
0x180022da4  mov     [rsp+22E0h+var_22B8], ebx; unsigned int
0x180022da8  mov     r8, rdi; lpSubKey
0x180022dab  mov     rdx, r13; hKey
0x180022dae  lea     rcx, [rsp+22E0h+var_2280]; this
0x180022db3  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x180022db8  test    eax, eax
0x180022dba  jnz     loc_18002305D
0x180022dc0  mov     rdx, rdi; unsigned __int16 *
0x180022dc3  mov     rcx, rsi; this
0x180022dc6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180022dcb  mov     ebx, eax
0x180022dcd  test    eax, eax
0x180022dcf  js      loc_180023019
0x180022dd5  cmp     word ptr [rdi], 3Dh ; '='
0x180022dd9  jnz     short loc_180022DF8
0x180022ddb  mov     r9, rdi; unsigned __int16 *
0x180022dde  xor     r8d, r8d; unsigned __int16 *
0x180022de1  lea     rdx, [rsp+22E0h+var_2280]; struct ATL::CRegKey *
0x180022de6  mov     rcx, rsi; this
0x180022de9  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180022dee  mov     ebx, eax
0x180022df0  test    eax, eax
0x180022df2  js      loc_180023019
0x180022df8  cmp     word ptr [rdi], 7Bh ; '{'
0x180022dfc  jnz     loc_180022B35
0x180022e02  or      rax, 0FFFFFFFFFFFFFFFFh
0x180022e06  inc     rax
0x180022e09  cmp     [rdi+rax*2], r14w
0x180022e0e  jnz     short loc_180022E06
0x180022e10  cmp     rax, 1
0x180022e14  jnz     loc_180022B35
0x180022e1a  mov     dword ptr [rsp+22E0h+var_22C0], r14d; int
0x180022e1f  mov     r9d, r15d; int
0x180022e22  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x180022e27  mov     rdx, rdi; unsigned __int16 *
0x180022e2a  mov     rcx, rsi; this
0x180022e2d  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180022e32  mov     ebx, eax
0x180022e34  test    eax, eax
0x180022e36  js      loc_180023019
0x180022e3c  mov     rdx, rdi
0x180022e3f  mov     rcx, rsi
0x180022e42  jmp     loc_180022B26
0x180022e47  cmp     [rbp+21E0h+arg_20], r14d
0x180022e4e  jnz     short loc_180022E6B
0x180022e50  mov     r9d, 20019h; unsigned int
0x180022e56  mov     r8, rdi; lpSubKey
0x180022e59  mov     rdx, r13; hKey
0x180022e5c  lea     rcx, [rsp+22E0h+var_2280]; this
0x180022e61  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180022e66  mov     r14d, eax
0x180022e69  jmp     short loc_180022E71
0x180022e6b  mov     r14d, 2
0x180022e71  mov     r15d, 1
0x180022e77  test    r14d, r14d
0x180022e7a  cmovz   r15d, [rbp+21E0h+arg_20]
0x180022e82  or      r9, 0FFFFFFFFFFFFFFFFh
0x180022e86  mov     r8, rdi
0x180022e89  mov     edx, 104h
0x180022e8e  lea     rcx, [rbp+21E0h+var_2260]
0x180022e92  call    cs:__imp__o_wcsncpy_s
0x180022e98  mov     ecx, eax; int
0x180022e9a  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180022e9f  mov     rdx, rdi; unsigned __int16 *
0x180022ea2  mov     rcx, rsi; this
0x180022ea5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180022eaa  mov     ebx, eax
0x180022eac  test    eax, eax
0x180022eae  js      loc_180023019
0x180022eb4  mov     rdx, rdi; unsigned __int16 *
0x180022eb7  mov     rcx, rsi; this
0x180022eba  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180022ebf  mov     ebx, eax
0x180022ec1  xor     ecx, ecx
0x180022ec3  test    eax, eax
0x180022ec5  js      loc_180023019
0x180022ecb  cmp     word ptr [rdi], 7Bh ; '{'
0x180022ecf  jnz     short loc_180022F20
0x180022ed1  or      rax, 0FFFFFFFFFFFFFFFFh
0x180022ed5  inc     rax
0x180022ed8  cmp     [rdi+rax*2], cx
0x180022edc  jnz     short loc_180022ED5
0x180022ede  cmp     rax, 1
0x180022ee2  jnz     short loc_180022F20
0x180022ee4  mov     dword ptr [rsp+22E0h+var_22C0], r15d; int
0x180022ee9  xor     r9d, r9d; int
0x180022eec  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x180022ef1  mov     rdx, rdi; unsigned __int16 *
0x180022ef4  mov     rcx, rsi; this
0x180022ef7  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180022efc  mov     ebx, eax
0x180022efe  test    eax, eax
0x180022f00  jns     short loc_180022F0B
0x180022f02  test    r15d, r15d
0x180022f05  jz      loc_180023019
0x180022f0b  mov     rdx, rdi; unsigned __int16 *
0x180022f0e  mov     rcx, rsi; this
0x180022f11  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180022f16  mov     ebx, eax
0x180022f18  test    eax, eax
0x180022f1a  js      loc_180023019
0x180022f20  cmp     r14d, 2
0x180022f24  mov     r15d, [rsp+22E0h+var_22A0]
0x180022f29  jz      loc_180022B35
0x180022f2f  test    r14d, r14d
0x180022f32  jz      short loc_180022F53
0x180022f34  xor     r12d, r12d
0x180022f37  cmp     [rbp+21E0h+arg_20], r12d
0x180022f3e  jnz     loc_180022B38
0x180022f44  mov     ecx, r14d; unsigned int
0x180022f47  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180022f4c  mov     ebx, eax
0x180022f4e  jmp     loc_180023019
0x180022f53  xor     r14d, r14d
0x180022f56  cmp     [rbp+21E0h+arg_20], r14d
0x180022f5d  jz      short loc_180022F9D
0x180022f5f  mov     rdx, [rsp+22E0h+var_2280]; HKEY
0x180022f64  call    ?HasSubKeys@CRegParser@ATL@@IEAAHPEAUHKEY__@@@Z; ATL::CRegParser::HasSubKeys(HKEY__ *)
0x180022f69  test    eax, eax
0x180022f6b  jz      short loc_180022F9D
  ... truncated ...
```
