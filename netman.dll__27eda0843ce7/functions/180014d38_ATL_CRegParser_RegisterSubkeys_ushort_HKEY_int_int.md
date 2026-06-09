# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180014d38`
- end: `0x1800152d5`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1437`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800148d4`
- `0x180014d38`

## callees

- `0x180001710`
- `0x18000a190`
- `0x18000a938`
- `0x18000a9a8`
- `0x18000aabc`
- `0x18000aeb8`
- `0x18000af44`
- `0x18000f0fc`
- `0x1800115f8`
- `0x180012408`
- `0x1800128a4`
- `0x180014780`
- `0x180014d38`
- `0x180017360`
- `0x180017510`
- `0x180034d90`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180015106`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180015106`
- `ADVAPI32!RegDeleteValueW` at `0x180014f9e`
- `ADVAPI32!RegDeleteValueW` at `0x180014f9e`
- `KERNEL32!lstrcmpiW` at `0x180014dbc`
- `KERNEL32!lstrcmpiW` at `0x180014dcf`
- `KERNEL32!lstrcmpiW` at `0x180014ea3`
- `KERNEL32!lstrcmpiW` at `0x180014ed2`
- `KERNEL32!lstrcmpiW` at `0x180014dbc`
- `KERNEL32!lstrcmpiW` at `0x180014dcf`
- `KERNEL32!lstrcmpiW` at `0x180014ea3`
- `KERNEL32!lstrcmpiW` at `0x180014ed2`

## string_xrefs

- `0x180014dc5`: `ForceRemove`
- `0x180014e99`: `NoRemove`
- `0x180014db2`: `Delete`

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
  unsigned int v28; // [rsp+28h] [rbp-D8h]
  struct _SECURITY_ATTRIBUTES *v29; // [rsp+30h] [rbp-D0h]
  unsigned int *v30; // [rsp+38h] [rbp-C8h]
  HKEY hKey[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v33; // [rsp+58h] [rbp-A8h]
  HKEY v34[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v35; // [rsp+70h] [rbp-90h]
  unsigned __int16 v36[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ValueName[4096]; // [rsp+290h] [rbp+190h] BYREF

  v5 = a4;
  v7 = a2;
  v8 = this;
  v34[0] = 0;
  v34[1] = 0;
  v35 = 0;
LABEL_2:
  Token = ATL::CRegParser::NextToken(this, a2);
  while ( 2 )
  {
    v10 = Token;
    if ( Token < 0 )
      goto LABEL_77;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( *v7 == 125 )
          goto LABEL_77;
        v11 = lstrcmpiW(v7, L"Delete");
        if ( lstrcmpiW(v7, L"ForceRemove") )
        {
          if ( v11 )
            break;
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_77;
        if ( !v5 )
          break;
        hKey[0] = 0;
        hKey[1] = 0;
        v33 = 0;
        if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        {
          ATL::CRegKey::Close((ATL::CRegKey *)hKey);
LABEL_76:
          v10 = -2147352567;
          goto LABEL_77;
        }
        if ( ATL::CRegParser::CanForceRemoveKey(v12, v7) )
        {
          hKey[0] = a3;
          ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, v7);
          hKey[0] = 0;
        }
        if ( v11 )
        {
          ATL::CRegKey::Close((ATL::CRegKey *)hKey);
          break;
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        v13 = ATL::CRegParser::SkipAssignment(v8, v7);
        v10 = v13;
LABEL_15:
        if ( v13 < 0 )
          goto LABEL_79;
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
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
              goto LABEL_77;
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
          goto LABEL_77;
      }
      if ( !lstrcmpiW(v7, L"Val") )
        break;
      if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        goto LABEL_76;
      if ( v5 )
      {
        if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v34, a3, v7, 0x2001Fu)
          || !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v34, a3, v7, 0x20019u)
          || (v17 = ATL::CRegKey::Create((ATL::CRegKey *)v34, a3, v7, v16, v27, v28, v29, v30)) == 0 )
        {
          v10 = ATL::CRegParser::NextToken(v8, v7);
          if ( v10 < 0 )
            goto LABEL_77;
          if ( *v7 == 61 )
          {
            v10 = ATL::CRegParser::AddValue(v8, v34, 0, v7);
            if ( v10 < 0 )
              goto LABEL_77;
          }
          goto LABEL_40;
        }
LABEL_80:
        v24 = v17;
LABEL_64:
        v10 = ATL::AtlHresultFromWin32(v24);
        goto LABEL_77;
      }
      if ( a5 )
        v19 = 2;
      else
        v19 = ATL::CRegKey::Open((ATL::CRegKey *)v34, a3, v7, 0x20019u);
      v20 = 1;
      if ( !v19 )
        v20 = a5;
      v21 = _o_wcsncpy_s(v36, 260, v7, -1, v27);
      ATL::AtlCrtErrorCheck(v21);
      v10 = ATL::CRegParser::NextToken(v8, v7);
      if ( v10 < 0 )
        goto LABEL_77;
      v10 = ATL::CRegParser::SkipAssignment(v8, v7);
      v22 = 0;
      if ( v10 < 0 )
        goto LABEL_77;
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
            goto LABEL_77;
          v10 = ATL::CRegParser::NextToken(v8, v7);
          if ( v10 < 0 )
            goto LABEL_77;
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
          if ( ATL::CRegParser::CanForceRemoveKey(v22, v36) && v14 )
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v34, v36);
        }
        else
        {
          HasSubKeys = ATL::CRegParser::HasSubKeys(v22, v34[0]);
          v17 = ATL::CRegKey::Close((ATL::CRegKey *)v34);
          if ( v17 )
            goto LABEL_80;
          if ( v14 && !HasSubKeys )
          {
            hKey[1] = 0;
            v33 = 0;
            hKey[0] = a3;
            v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)hKey, v36);
            hKey[0] = 0;
            if ( v15 )
              goto LABEL_78;
            ATL::CRegKey::Close((ATL::CRegKey *)hKey);
          }
        }
      }
    }
    v10 = ATL::CRegParser::NextToken(v8, ValueName);
    if ( v10 < 0 )
      goto LABEL_77;
    v10 = ATL::CRegParser::NextToken(v8, v7);
    if ( v10 < 0 )
      goto LABEL_77;
    if ( *v7 != 61 )
      goto LABEL_76;
    if ( v5 )
    {
      hKey[1] = 0;
      v33 = 0;
      hKey[0] = a3;
      v13 = ATL::CRegParser::AddValue(v8, hKey, ValueName, v7);
      v10 = v13;
      hKey[0] = 0;
      goto LABEL_15;
    }
    if ( a5 || !v14 )
      goto LABEL_31;
    hKey[0] = 0;
    hKey[1] = 0;
    v33 = 0;
    v15 = ATL::CRegKey::Open((ATL::CRegKey *)hKey, a3, 0, 0x20006u);
    if ( !v15 )
    {
      v15 = RegDeleteValueW(hKey[0], ValueName);
      if ( (v15 & 0xFFFFFFFD) == 0 )
      {
        ATL::CRegKey::Close((ATL::CRegKey *)hKey);
LABEL_31:
        Token = ATL::CRegParser::SkipAssignment(v8, v7);
        continue;
      }
    }
    break;
  }
LABEL_78:
  v10 = ATL::AtlHresultFromWin32(v15);
LABEL_79:
  ATL::CRegKey::Close((ATL::CRegKey *)hKey);
LABEL_77:
  ATL::CRegKey::Close((ATL::CRegKey *)v34);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180014d38  push    rbp
0x180014d3a  push    rbx
0x180014d3b  push    rsi
0x180014d3c  push    rdi
0x180014d3d  push    r12
0x180014d3f  push    r13
0x180014d41  push    r14
0x180014d43  push    r15
0x180014d45  lea     rbp, [rsp-21A8h]
0x180014d4d  mov     eax, 22A8h
0x180014d52  call    _alloca_probe
0x180014d57  sub     rsp, rax
0x180014d5a  mov     rax, cs:__security_cookie
0x180014d61  xor     rax, rsp
0x180014d64  mov     [rbp+21E0h+var_50], rax
0x180014d6b  mov     r15d, r9d
0x180014d6e  mov     [rsp+22E0h+var_22A0], r9d
0x180014d73  mov     r13, r8
0x180014d76  mov     rdi, rdx
0x180014d79  mov     rsi, rcx
0x180014d7c  xorps   xmm0, xmm0
0x180014d7f  movups  xmmword ptr [rsp+22E0h+var_2280], xmm0
0x180014d84  xor     r14d, r14d
0x180014d87  mov     [rsp+22E0h+var_2280], r14
0x180014d8c  mov     [rsp+22E0h+var_2280+8], r14
0x180014d91  mov     [rsp+22E0h+var_2270], r14
0x180014d96  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180014d9b  test    eax, eax
0x180014d9d  mov     ebx, eax
0x180014d9f  js      loc_180015289
0x180014da5  xor     r12d, r12d
0x180014da8  cmp     word ptr [rdi], 7Dh ; '}'
0x180014dac  jz      loc_180015289
0x180014db2  lea     rdx, String2; "Delete"
0x180014db9  mov     rcx, rdi; lpString1
0x180014dbc  call    cs:__imp_lstrcmpiW
0x180014dc2  mov     r14d, eax
0x180014dc5  lea     rdx, aForceremove; "ForceRemove"
0x180014dcc  mov     rcx, rdi; lpString1
0x180014dcf  call    cs:__imp_lstrcmpiW
0x180014dd5  test    eax, eax
0x180014dd7  jz      short loc_180014DE2
0x180014dd9  test    r14d, r14d
0x180014ddc  jnz     loc_180014E93
0x180014de2  mov     rdx, rdi; unsigned __int16 *
0x180014de5  mov     rcx, rsi; this
0x180014de8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180014ded  mov     ebx, eax
0x180014def  test    eax, eax
0x180014df1  js      loc_180015289
0x180014df7  test    r15d, r15d
0x180014dfa  jz      loc_180014E93
0x180014e00  mov     [rsp+22E0h+hKey], r12
0x180014e05  mov     [rsp+22E0h+hKey+8], r12
0x180014e0a  mov     [rsp+22E0h+var_2288], r12
0x180014e0f  mov     edx, 5Ch ; '\'; unsigned __int16
0x180014e14  mov     rcx, rdi; lpsz
0x180014e17  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180014e1c  test    rax, rax
0x180014e1f  jnz     loc_18001527A
0x180014e25  mov     rdx, rdi; unsigned __int16 *
0x180014e28  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x180014e2d  test    eax, eax
0x180014e2f  jz      short loc_180014E48
0x180014e31  mov     [rsp+22E0h+hKey], r13
0x180014e36  mov     rdx, rdi; unsigned __int16 *
0x180014e39  lea     rcx, [rsp+22E0h+hKey]; this
0x180014e3e  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180014e43  mov     [rsp+22E0h+hKey], r12
0x180014e48  test    r14d, r14d
0x180014e4b  jnz     short loc_180014E89
0x180014e4d  mov     rdx, rdi; unsigned __int16 *
0x180014e50  mov     rcx, rsi; this
0x180014e53  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180014e58  mov     ebx, eax
0x180014e5a  xor     r14d, r14d
0x180014e5d  test    eax, eax
0x180014e5f  js      loc_1800152C1
0x180014e65  mov     rdx, rdi; unsigned __int16 *
0x180014e68  mov     rcx, rsi; this
0x180014e6b  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180014e70  mov     ebx, eax
0x180014e72  test    eax, eax
0x180014e74  lea     rcx, [rsp+22E0h+hKey]; this
0x180014e79  js      loc_1800152C6
0x180014e7f  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180014e84  jmp     loc_18001506C
0x180014e89  lea     rcx, [rsp+22E0h+hKey]; this
0x180014e8e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180014e93  mov     r12d, 1
0x180014e99  lea     rdx, aNoremove; "NoRemove"
0x180014ea0  mov     rcx, rdi; lpString1
0x180014ea3  call    cs:__imp_lstrcmpiW
0x180014ea9  xor     r14d, r14d
0x180014eac  test    eax, eax
0x180014eae  jnz     short loc_180014EC8
0x180014eb0  mov     r12d, r14d
0x180014eb3  mov     rdx, rdi; unsigned __int16 *
0x180014eb6  mov     rcx, rsi; this
0x180014eb9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180014ebe  mov     ebx, eax
0x180014ec0  test    eax, eax
0x180014ec2  js      loc_180015289
0x180014ec8  lea     rdx, aVal; "Val"
0x180014ecf  mov     rcx, rdi; lpString1
0x180014ed2  call    cs:__imp_lstrcmpiW
0x180014ed8  test    eax, eax
0x180014eda  jnz     loc_180014FC9
0x180014ee0  lea     rdx, [rbp+21E0h+ValueName]; unsigned __int16 *
0x180014ee7  mov     rcx, rsi; this
0x180014eea  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180014eef  mov     ebx, eax
0x180014ef1  test    eax, eax
0x180014ef3  js      loc_180015289
0x180014ef9  mov     rdx, rdi; unsigned __int16 *
0x180014efc  mov     rcx, rsi; this
0x180014eff  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180014f04  mov     ebx, eax
0x180014f06  test    eax, eax
0x180014f08  js      loc_180015289
0x180014f0e  cmp     word ptr [rdi], 3Dh ; '='
0x180014f12  jnz     loc_180015284
0x180014f18  test    r15d, r15d
0x180014f1b  jz      short loc_180014F57
0x180014f1d  xorps   xmm0, xmm0
0x180014f20  movups  xmmword ptr [rsp+22E0h+hKey], xmm0
0x180014f25  mov     [rsp+22E0h+hKey+8], r14
0x180014f2a  mov     [rsp+22E0h+var_2288], r14
0x180014f2f  mov     [rsp+22E0h+hKey], r13
0x180014f34  mov     r9, rdi; unsigned __int16 *
0x180014f37  lea     r8, [rbp+21E0h+ValueName]; unsigned __int16 *
0x180014f3e  lea     rdx, [rsp+22E0h+hKey]; struct ATL::CRegKey *
0x180014f43  mov     rcx, rsi; this
0x180014f46  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180014f4b  mov     ebx, eax
0x180014f4d  mov     [rsp+22E0h+hKey], r14
0x180014f52  jmp     loc_180014E72
0x180014f57  cmp     [rbp+21E0h+arg_20], r14d
0x180014f5e  jnz     short loc_180014FB9
0x180014f60  test    r12d, r12d
0x180014f63  jz      short loc_180014FB9
0x180014f65  mov     [rsp+22E0h+hKey], r14
0x180014f6a  mov     [rsp+22E0h+hKey+8], r14
0x180014f6f  mov     [rsp+22E0h+var_2288], r14
0x180014f74  mov     r9d, 20006h; unsigned int
0x180014f7a  xor     r8d, r8d; lpSubKey
0x180014f7d  mov     rdx, r13; hKey
0x180014f80  lea     rcx, [rsp+22E0h+hKey]; this
0x180014f85  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180014f8a  test    eax, eax
0x180014f8c  jnz     loc_1800152B8
0x180014f92  lea     rdx, [rbp+21E0h+ValueName]; lpValueName
0x180014f99  mov     rcx, [rsp+22E0h+hKey]; hKey
0x180014f9e  call    cs:__imp_RegDeleteValueW
0x180014fa4  test    eax, 0FFFFFFFDh
0x180014fa9  jnz     loc_1800152B8
0x180014faf  lea     rcx, [rsp+22E0h+hKey]; this
0x180014fb4  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180014fb9  mov     rdx, rdi; unsigned __int16 *
0x180014fbc  mov     rcx, rsi; this
0x180014fbf  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180014fc4  jmp     loc_180014D9B
0x180014fc9  mov     edx, 5Ch ; '\'; unsigned __int16
0x180014fce  mov     rcx, rdi; lpsz
0x180014fd1  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180014fd6  test    rax, rax
0x180014fd9  jnz     loc_180015284
0x180014fdf  test    r15d, r15d
0x180014fe2  jz      loc_1800150BB
0x180014fe8  mov     r9d, 2001Fh; unsigned int
0x180014fee  mov     r8, rdi; lpSubKey
0x180014ff1  mov     rdx, r13; hKey
0x180014ff4  lea     rcx, [rsp+22E0h+var_2280]; this
0x180014ff9  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180014ffe  test    eax, eax
0x180015000  jz      short loc_180015034
0x180015002  mov     r9d, 20019h; unsigned int
0x180015008  mov     r8, rdi; lpSubKey
0x18001500b  mov     rdx, r13; hKey
0x18001500e  lea     rcx, [rsp+22E0h+var_2280]; this
0x180015013  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180015018  test    eax, eax
0x18001501a  jz      short loc_180015034
0x18001501c  mov     r8, rdi; lpSubKey
0x18001501f  mov     rdx, r13; hKey
0x180015022  lea     rcx, [rsp+22E0h+var_2280]; this
0x180015027  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x18001502c  test    eax, eax
0x18001502e  jnz     loc_1800152CD
0x180015034  mov     rdx, rdi; unsigned __int16 *
0x180015037  mov     rcx, rsi; this
0x18001503a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001503f  mov     ebx, eax
0x180015041  test    eax, eax
0x180015043  js      loc_180015289
0x180015049  cmp     word ptr [rdi], 3Dh ; '='
0x18001504d  jnz     short loc_18001506C
0x18001504f  mov     r9, rdi; unsigned __int16 *
0x180015052  xor     r8d, r8d; unsigned __int16 *
0x180015055  lea     rdx, [rsp+22E0h+var_2280]; struct ATL::CRegKey *
0x18001505a  mov     rcx, rsi; this
0x18001505d  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180015062  mov     ebx, eax
0x180015064  test    eax, eax
0x180015066  js      loc_180015289
0x18001506c  cmp     word ptr [rdi], 7Bh ; '{'
0x180015070  jnz     loc_180014DA5
0x180015076  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001507a  inc     rax
0x18001507d  cmp     [rdi+rax*2], r14w
0x180015082  jnz     short loc_18001507A
0x180015084  cmp     rax, 1
0x180015088  jnz     loc_180014DA5
0x18001508e  mov     dword ptr [rsp+22E0h+var_22C0], r14d; int
0x180015093  mov     r9d, r15d; int
0x180015096  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x18001509b  mov     rdx, rdi; unsigned __int16 *
0x18001509e  mov     rcx, rsi; this
0x1800150a1  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800150a6  mov     ebx, eax
0x1800150a8  test    eax, eax
0x1800150aa  js      loc_180015289
0x1800150b0  mov     rdx, rdi
0x1800150b3  mov     rcx, rsi
0x1800150b6  jmp     loc_180014D96
0x1800150bb  cmp     [rbp+21E0h+arg_20], r14d
0x1800150c2  jnz     short loc_1800150DF
0x1800150c4  mov     r9d, 20019h; unsigned int
0x1800150ca  mov     r8, rdi; lpSubKey
0x1800150cd  mov     rdx, r13; hKey
0x1800150d0  lea     rcx, [rsp+22E0h+var_2280]; this
0x1800150d5  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800150da  mov     r14d, eax
0x1800150dd  jmp     short loc_1800150E5
0x1800150df  mov     r14d, 2
0x1800150e5  mov     r15d, 1
0x1800150eb  test    r14d, r14d
0x1800150ee  cmovz   r15d, [rbp+21E0h+arg_20]
0x1800150f6  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800150fa  mov     r8, rdi
0x1800150fd  mov     edx, 104h
0x180015102  lea     rcx, [rbp+21E0h+var_2260]
0x180015106  call    cs:__imp__o_wcsncpy_s
0x18001510c  mov     ecx, eax; int
0x18001510e  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180015113  mov     rdx, rdi; unsigned __int16 *
0x180015116  mov     rcx, rsi; this
0x180015119  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001511e  mov     ebx, eax
0x180015120  test    eax, eax
0x180015122  js      loc_180015289
0x180015128  mov     rdx, rdi; unsigned __int16 *
0x18001512b  mov     rcx, rsi; this
0x18001512e  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180015133  mov     ebx, eax
0x180015135  xor     ecx, ecx
0x180015137  test    eax, eax
0x180015139  js      loc_180015289
0x18001513f  cmp     word ptr [rdi], 7Bh ; '{'
0x180015143  jnz     short loc_180015194
0x180015145  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015149  inc     rax
0x18001514c  cmp     [rdi+rax*2], cx
0x180015150  jnz     short loc_180015149
0x180015152  cmp     rax, 1
0x180015156  jnz     short loc_180015194
0x180015158  mov     dword ptr [rsp+22E0h+var_22C0], r15d; int
0x18001515d  xor     r9d, r9d; int
0x180015160  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x180015165  mov     rdx, rdi; unsigned __int16 *
0x180015168  mov     rcx, rsi; this
0x18001516b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180015170  mov     ebx, eax
0x180015172  test    eax, eax
0x180015174  jns     short loc_18001517F
0x180015176  test    r15d, r15d
0x180015179  jz      loc_180015289
0x18001517f  mov     rdx, rdi; unsigned __int16 *
0x180015182  mov     rcx, rsi; this
0x180015185  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001518a  mov     ebx, eax
0x18001518c  test    eax, eax
0x18001518e  js      loc_180015289
0x180015194  cmp     r14d, 2
0x180015198  mov     r15d, [rsp+22E0h+var_22A0]
0x18001519d  jz      loc_180014DA5
0x1800151a3  test    r14d, r14d
0x1800151a6  jz      short loc_1800151C7
0x1800151a8  xor     r12d, r12d
0x1800151ab  cmp     [rbp+21E0h+arg_20], r12d
0x1800151b2  jnz     loc_180014DA8
0x1800151b8  mov     ecx, r14d; unsigned int
0x1800151bb  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800151c0  mov     ebx, eax
0x1800151c2  jmp     loc_180015289
0x1800151c7  xor     r14d, r14d
0x1800151ca  cmp     [rbp+21E0h+arg_20], r14d
0x1800151d1  jz      short loc_180015211
0x1800151d3  mov     rdx, [rsp+22E0h+var_2280]; HKEY
0x1800151d8  call    ?HasSubKeys@CRegParser@ATL@@IEAAHPEAUHKEY__@@@Z; ATL::CRegParser::HasSubKeys(HKEY__ *)
  ... truncated ...
```
