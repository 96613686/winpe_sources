# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x1800110f4`
- end: `0x180011675`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1409`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180010ccc`
- `0x1800110f4`

## callees

- `0x18000ea4c`
- `0x18000f0c0`
- `0x18000f19c`
- `0x18000f8d4`
- `0x18000fa64`
- `0x18000fa90`
- `0x18000fffc`
- `0x180010394`
- `0x1800106a0`
- `0x180010818`
- `0x180010bb8`
- `0x1800110f4`
- `0x180011990`
- `0x180011a60`
- `0x18002e230`
- `0x18002e2f0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x1800114b5`
- `msvcrt!wcsncpy_s` at `0x1800114b5`
- `KERNEL32!lstrcmpiW` at `0x180011168`
- `KERNEL32!lstrcmpiW` at `0x18001117b`
- `KERNEL32!lstrcmpiW` at `0x18001124c`
- `KERNEL32!lstrcmpiW` at `0x18001127b`
- `KERNEL32!lstrcmpiW` at `0x180011168`
- `KERNEL32!lstrcmpiW` at `0x18001117b`
- `KERNEL32!lstrcmpiW` at `0x18001124c`
- `KERNEL32!lstrcmpiW` at `0x18001127b`
- `ADVAPI32!RegDeleteValueW` at `0x180011345`
- `ADVAPI32!RegDeleteValueW` at `0x180011345`

## string_xrefs

- `0x180011171`: `ForceRemove`
- `0x180011242`: `NoRemove`
- `0x18001115e`: `Delete`

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
0x1800110f4  push    rbp
0x1800110f6  push    rbx
0x1800110f7  push    rsi
0x1800110f8  push    rdi
0x1800110f9  push    r12
0x1800110fb  push    r13
0x1800110fd  push    r14
0x1800110ff  push    r15
0x180011101  lea     rbp, [rsp-21A8h]
0x180011109  mov     eax, 22A8h
0x18001110e  call    _alloca_probe
0x180011113  sub     rsp, rax
0x180011116  mov     rax, cs:__security_cookie
0x18001111d  xor     rax, rsp
0x180011120  mov     [rbp+21E0h+var_50], rax
0x180011127  mov     r15d, r9d
0x18001112a  mov     [rsp+22E0h+var_22A0], r9d
0x18001112f  mov     r13, r8
0x180011132  mov     rdi, rdx
0x180011135  mov     rsi, rcx
0x180011138  xor     r12d, r12d
0x18001113b  mov     [rsp+22E0h+var_2280], r12
0x180011140  mov     [rsp+22E0h+var_2278], r12
0x180011145  mov     [rsp+22E0h+var_2270], r12
0x18001114a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001114f  mov     ebx, eax
0x180011151  test    eax, eax
0x180011153  js      loc_180011629
0x180011159  jmp     loc_1800115B0
0x18001115e  lea     rdx, String2; "Delete"
0x180011165  mov     rcx, rdi; lpString1
0x180011168  call    cs:__imp_lstrcmpiW
0x18001116e  mov     r14d, eax
0x180011171  lea     rdx, aForceremove; "ForceRemove"
0x180011178  mov     rcx, rdi; lpString1
0x18001117b  call    cs:__imp_lstrcmpiW
0x180011181  test    eax, eax
0x180011183  jz      short loc_18001118E
0x180011185  test    r14d, r14d
0x180011188  jnz     loc_18001123C
0x18001118e  mov     rdx, rdi; unsigned __int16 *
0x180011191  mov     rcx, rsi; this
0x180011194  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180011199  mov     ebx, eax
0x18001119b  test    eax, eax
0x18001119d  js      loc_180011629
0x1800111a3  test    r15d, r15d
0x1800111a6  jz      loc_18001123C
0x1800111ac  mov     [rsp+22E0h+hKey], r12
0x1800111b1  mov     [rsp+22E0h+var_2290], r12
0x1800111b6  mov     [rsp+22E0h+var_2288], r12
0x1800111bb  mov     edx, 5Ch ; '\'; unsigned __int16
0x1800111c0  mov     rcx, rdi; lpsz
0x1800111c3  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1800111c8  test    rax, rax
0x1800111cb  jnz     loc_18001161A
0x1800111d1  mov     rdx, rdi; unsigned __int16 *
0x1800111d4  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x1800111d9  test    eax, eax
0x1800111db  jz      short loc_1800111F4
0x1800111dd  mov     [rsp+22E0h+hKey], r13
0x1800111e2  mov     rdx, rdi; unsigned __int16 *
0x1800111e5  lea     rcx, [rsp+22E0h+hKey]; this
0x1800111ea  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x1800111ef  mov     [rsp+22E0h+hKey], r12
0x1800111f4  test    r14d, r14d
0x1800111f7  jnz     short loc_180011232
0x1800111f9  mov     rdx, rdi; unsigned __int16 *
0x1800111fc  mov     rcx, rsi; this
0x1800111ff  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180011204  mov     ebx, eax
0x180011206  test    eax, eax
0x180011208  js      loc_180011661
0x18001120e  mov     rdx, rdi; unsigned __int16 *
0x180011211  mov     rcx, rsi; this
0x180011214  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180011219  mov     ebx, eax
0x18001121b  test    eax, eax
0x18001121d  lea     rcx, [rsp+22E0h+hKey]; this
0x180011222  js      loc_180011666
0x180011228  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001122d  jmp     loc_18001141B
0x180011232  lea     rcx, [rsp+22E0h+hKey]; this
0x180011237  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001123c  mov     r12d, 1
0x180011242  lea     rdx, aNoremove; "NoRemove"
0x180011249  mov     rcx, rdi; lpString1
0x18001124c  call    cs:__imp_lstrcmpiW
0x180011252  xor     r14d, r14d
0x180011255  test    eax, eax
0x180011257  jnz     short loc_180011271
0x180011259  mov     r12d, r14d
0x18001125c  mov     rdx, rdi; unsigned __int16 *
0x18001125f  mov     rcx, rsi; this
0x180011262  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180011267  mov     ebx, eax
0x180011269  test    eax, eax
0x18001126b  js      loc_180011629
0x180011271  lea     rdx, aVal; "Val"
0x180011278  mov     rcx, rdi; lpString1
0x18001127b  call    cs:__imp_lstrcmpiW
0x180011281  test    eax, eax
0x180011283  jnz     loc_180011375
0x180011289  lea     rdx, [rbp+21E0h+ValueName]; unsigned __int16 *
0x180011290  mov     rcx, rsi; this
0x180011293  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180011298  mov     ebx, eax
0x18001129a  test    eax, eax
0x18001129c  js      loc_180011629
0x1800112a2  mov     rdx, rdi; unsigned __int16 *
0x1800112a5  mov     rcx, rsi; this
0x1800112a8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800112ad  mov     ebx, eax
0x1800112af  test    eax, eax
0x1800112b1  js      loc_180011629
0x1800112b7  cmp     word ptr [rdi], 3Dh ; '='
0x1800112bb  jnz     loc_180011624
0x1800112c1  test    r15d, r15d
0x1800112c4  jz      short loc_1800112FB
0x1800112c6  xor     r12d, r12d
0x1800112c9  mov     [rsp+22E0h+var_2290], r12
0x1800112ce  mov     [rsp+22E0h+var_2288], r12
0x1800112d3  mov     [rsp+22E0h+hKey], r13
0x1800112d8  mov     r9, rdi; unsigned __int16 *
0x1800112db  lea     r8, [rbp+21E0h+ValueName]; unsigned __int16 *
0x1800112e2  lea     rdx, [rsp+22E0h+hKey]; struct ATL::CRegKey *
0x1800112e7  mov     rcx, rsi; this
0x1800112ea  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1800112ef  mov     ebx, eax
0x1800112f1  mov     [rsp+22E0h+hKey], r12
0x1800112f6  jmp     loc_18001121B
0x1800112fb  cmp     [rbp+21E0h+arg_20], r14d
0x180011302  jnz     short loc_180011362
0x180011304  test    r12d, r12d
0x180011307  jz      short loc_180011362
0x180011309  xor     r12d, r12d
0x18001130c  mov     [rsp+22E0h+hKey], r12
0x180011311  mov     [rsp+22E0h+var_2290], r12
0x180011316  mov     [rsp+22E0h+var_2288], r12
0x18001131b  mov     r9d, 20006h; unsigned int
0x180011321  xor     r8d, r8d; lpSubKey
0x180011324  mov     rdx, r13; hKey
0x180011327  lea     rcx, [rsp+22E0h+hKey]; this
0x18001132c  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180011331  test    eax, eax
0x180011333  jnz     loc_180011658
0x180011339  lea     rdx, [rbp+21E0h+ValueName]; lpValueName
0x180011340  mov     rcx, [rsp+22E0h+hKey]; hKey
0x180011345  call    cs:__imp_RegDeleteValueW
0x18001134b  test    eax, 0FFFFFFFDh
0x180011350  jnz     loc_180011658
0x180011356  lea     rcx, [rsp+22E0h+hKey]; this
0x18001135b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180011360  jmp     short loc_180011365
0x180011362  xor     r12d, r12d
0x180011365  mov     rdx, rdi; unsigned __int16 *
0x180011368  mov     rcx, rsi; this
0x18001136b  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180011370  jmp     loc_18001114F
0x180011375  mov     edx, 5Ch ; '\'; unsigned __int16
0x18001137a  mov     rcx, rdi; lpsz
0x18001137d  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180011382  test    rax, rax
0x180011385  jnz     loc_180011624
0x18001138b  test    r15d, r15d
0x18001138e  jz      loc_18001146A
0x180011394  mov     r9d, 2001Fh; unsigned int
0x18001139a  mov     r8, rdi; lpSubKey
0x18001139d  mov     rdx, r13; hKey
0x1800113a0  lea     rcx, [rsp+22E0h+var_2280]; this
0x1800113a5  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800113aa  xor     r12d, r12d
0x1800113ad  test    eax, eax
0x1800113af  jz      short loc_1800113E3
0x1800113b1  mov     r9d, 20019h; unsigned int
0x1800113b7  mov     r8, rdi; lpSubKey
0x1800113ba  mov     rdx, r13; hKey
0x1800113bd  lea     rcx, [rsp+22E0h+var_2280]; this
0x1800113c2  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800113c7  test    eax, eax
0x1800113c9  jz      short loc_1800113E3
0x1800113cb  mov     r8, rdi; lpSubKey
0x1800113ce  mov     rdx, r13; hKey
0x1800113d1  lea     rcx, [rsp+22E0h+var_2280]; this
0x1800113d6  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x1800113db  test    eax, eax
0x1800113dd  jnz     loc_18001166D
0x1800113e3  mov     rdx, rdi; unsigned __int16 *
0x1800113e6  mov     rcx, rsi; this
0x1800113e9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800113ee  mov     ebx, eax
0x1800113f0  test    eax, eax
0x1800113f2  js      loc_180011629
0x1800113f8  cmp     word ptr [rdi], 3Dh ; '='
0x1800113fc  jnz     short loc_18001141B
0x1800113fe  mov     r9, rdi; unsigned __int16 *
0x180011401  xor     r8d, r8d; unsigned __int16 *
0x180011404  lea     rdx, [rsp+22E0h+var_2280]; struct ATL::CRegKey *
0x180011409  mov     rcx, rsi; this
0x18001140c  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180011411  mov     ebx, eax
0x180011413  test    eax, eax
0x180011415  js      loc_180011629
0x18001141b  cmp     word ptr [rdi], 7Bh ; '{'
0x18001141f  jnz     loc_1800115B0
0x180011425  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011429  inc     rax
0x18001142c  cmp     [rdi+rax*2], r12w
0x180011431  jnz     short loc_180011429
0x180011433  cmp     rax, 1
0x180011437  jnz     loc_1800115B0
0x18001143d  mov     [rsp+22E0h+var_22C0], r12d; int
0x180011442  mov     r9d, r15d; int
0x180011445  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x18001144a  mov     rdx, rdi; unsigned __int16 *
0x18001144d  mov     rcx, rsi; this
0x180011450  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180011455  mov     ebx, eax
0x180011457  test    eax, eax
0x180011459  js      loc_180011629
0x18001145f  mov     rdx, rdi
0x180011462  mov     rcx, rsi
0x180011465  jmp     loc_18001114A
0x18001146a  cmp     [rbp+21E0h+arg_20], r14d
0x180011471  jnz     short loc_18001148E
0x180011473  mov     r9d, 20019h; unsigned int
0x180011479  mov     r8, rdi; lpSubKey
0x18001147c  mov     rdx, r13; hKey
0x18001147f  lea     rcx, [rsp+22E0h+var_2280]; this
0x180011484  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180011489  mov     r14d, eax
0x18001148c  jmp     short loc_180011494
0x18001148e  mov     r14d, 2
0x180011494  mov     r15d, 1
0x18001149a  test    r14d, r14d
0x18001149d  cmovz   r15d, [rbp+21E0h+arg_20]
0x1800114a5  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x1800114a9  mov     r8, rdi; Source
0x1800114ac  mov     edx, 104h; SizeInWords
0x1800114b1  lea     rcx, [rbp+21E0h+Destination]; Destination
0x1800114b5  call    cs:__imp_wcsncpy_s
0x1800114bb  mov     ecx, eax; int
0x1800114bd  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x1800114c2  mov     rdx, rdi; unsigned __int16 *
0x1800114c5  mov     rcx, rsi; this
0x1800114c8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800114cd  mov     ebx, eax
0x1800114cf  test    eax, eax
0x1800114d1  js      loc_180011629
0x1800114d7  mov     rdx, rdi; unsigned __int16 *
0x1800114da  mov     rcx, rsi; this
0x1800114dd  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800114e2  mov     ebx, eax
0x1800114e4  xor     ecx, ecx; this
0x1800114e6  test    eax, eax
0x1800114e8  js      loc_180011629
0x1800114ee  cmp     word ptr [rdi], 7Bh ; '{'
0x1800114f2  jnz     short loc_180011548
0x1800114f4  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800114f8  inc     rax
0x1800114fb  cmp     [rdi+rax*2], cx
0x1800114ff  jnz     short loc_1800114F8
0x180011501  cmp     rax, 1
0x180011505  jnz     short loc_180011548
0x180011507  mov     [rsp+22E0h+var_22C0], r15d; int
0x18001150c  xor     r9d, r9d; int
0x18001150f  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x180011514  mov     rdx, rdi; unsigned __int16 *
0x180011517  mov     rcx, rsi; this
0x18001151a  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18001151f  mov     ebx, eax
0x180011521  test    eax, eax
0x180011523  jns     short loc_18001152E
0x180011525  test    r15d, r15d
0x180011528  jz      loc_180011629
0x18001152e  mov     rdx, rdi; unsigned __int16 *
0x180011531  mov     rcx, rsi; this
0x180011534  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180011539  mov     ebx, eax
0x18001153b  xor     r15d, r15d
0x18001153e  test    eax, eax
0x180011540  js      loc_180011629
0x180011546  jmp     short loc_18001154B
0x180011548  xor     r15d, r15d
0x18001154b  cmp     r14d, 2
0x18001154f  jz      short loc_1800115A8
0x180011551  test    r14d, r14d
0x180011554  jz      short loc_180011571
0x180011556  xor     r12d, r12d
0x180011559  cmp     [rbp+21E0h+arg_20], r12d
0x180011560  jnz     short loc_1800115AB
0x180011562  mov     ecx, r14d; unsigned int
0x180011565  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18001156a  mov     ebx, eax
0x18001156c  jmp     loc_180011629
0x180011571  cmp     [rbp+21E0h+arg_20], r15d
0x180011578  jz      short loc_1800115BC
0x18001157a  mov     rdx, [rsp+22E0h+var_2280]; HKEY
0x18001157f  call    ?HasSubKeys@CRegParser@ATL@@IEAAHPEAUHKEY__@@@Z; ATL::CRegParser::HasSubKeys(HKEY__ *)
0x180011584  test    eax, eax
  ... truncated ...
```
