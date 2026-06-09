# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180118418`
- end: `0x180118a44`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1580`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x1801180dc`
- `0x180118418`

## callees

- `0x180110ed0`
- `0x1801141a8`
- `0x180114858`
- `0x1801148cc`
- `0x18011490c`
- `0x180114ac0`
- `0x1801166ac`
- `0x180117224`
- `0x180117414`
- `0x1801175a4`
- `0x180117fbc`
- `0x180118418`
- `0x180119654`
- `0x18011972c`
- `0x18017b6b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18011885a`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18011885a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180118755`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180118755`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18011868b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18011868b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18011848b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1801184a4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18011858e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1801185c3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18011848b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1801184a4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18011858e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1801185c3`

## string_xrefs

- `0x180118497`: `ForceRemove`
- `0x18011857e`: `NoRemove`
- `0x180118481`: `Delete`

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
  int v20; // eax
  int v21; // eax
  ATL::CRegParser *v22; // rcx
  __int64 v23; // rax
  int HasSubKeys; // r15d
  unsigned int v25; // r14d
  unsigned int v27; // ecx
  __int64 dwOptions; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v31; // [rsp+60h] [rbp-A0h]
  __int64 v32; // [rsp+68h] [rbp-98h]
  HKEY v33[3]; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v36[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ValueName[4096]; // [rsp+2B0h] [rbp+1B0h] BYREF

  memset(v33, 0, sizeof(v33));
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
            v31 = 0;
            v32 = 0;
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
            v31 = 0;
            v32 = 0;
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
          v31 = 0;
          v32 = 0;
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
          v18 = ATL::CRegKey::Open((ATL::CRegKey *)v33, a3, v7, 0x20019u);
        v19 = 1;
        if ( !v18 )
          v19 = a5;
        v20 = _o_wcsncpy_s(v36, 260, v7, -1, dwOptions);
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
            v11 = ATL::CRegParser::RegisterSubkeys(i, v7, v33[0], 0, v19);
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
          else if ( a5 && ATL::CRegParser::HasSubKeys(v22, v33[0]) )
          {
            if ( ATL::CRegParser::CanForceRemoveKey(v22, v36) && v14 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v33, v36);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v22, v33[0]);
            v25 = ATL::CRegKey::Close((ATL::CRegKey *)v33);
            if ( v25 )
            {
              ATL::CRegKey::Close((ATL::CRegKey *)v33);
              v27 = v25;
              return ATL::AtlHresultFromWin32(v27);
            }
            if ( v14 && !HasSubKeys )
            {
              v31 = 0;
              v32 = 0;
              hKey = a3;
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, v36);
              hKey = 0;
              if ( v15 )
                goto LABEL_80;
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            }
            v5 = a4;
          }
        }
      }
      if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v33, a3, v7, 0x2001Fu) )
      {
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v33, a3, v7, 0x20019u) )
        {
          dwDisposition = 0;
          phkResult = 0;
          v16 = RegCreateKeyExW(a3, v7, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
          if ( v16 || (v16 = ATL::CRegKey::Close((ATL::CRegKey *)v33), v33[0] = phkResult, v16) )
          {
            ATL::CRegKey::Close((ATL::CRegKey *)v33);
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
        v11 = ATL::CRegParser::AddValue(i, v33, 0, v7);
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
    v11 = ATL::CRegParser::RegisterSubkeys(i, v7, v33[0], v5, 0);
    if ( v11 < 0 )
      break;
    a2 = v7;
  }
LABEL_79:
  ATL::CRegKey::Close((ATL::CRegKey *)v33);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180118418  push    rbp
0x18011841a  push    rbx
0x18011841b  push    rsi
0x18011841c  push    rdi
0x18011841d  push    r12
0x18011841f  push    r13
0x180118421  push    r14
0x180118423  push    r15
0x180118425  lea     rbp, [rsp-21C8h]
0x18011842d  mov     eax, 22C8h
0x180118432  call    _alloca_probe
0x180118437  sub     rsp, rax
0x18011843a  mov     rax, cs:__security_cookie
0x180118441  xor     rax, rsp
0x180118444  mov     [rbp+2200h+var_50], rax
0x18011844b  xor     r14d, r14d
0x18011844e  mov     [rsp+2300h+var_22B0], r9d
0x180118453  mov     [rsp+2300h+var_2290], r14
0x180118458  mov     r15d, r9d
0x18011845b  mov     [rsp+2300h+var_2288], r14
0x180118460  mov     r13, r8
0x180118463  mov     [rbp+2200h+var_2280], r14
0x180118467  mov     rdi, rdx
0x18011846a  mov     rsi, rcx
0x18011846d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180118472  jmp     loc_1801186B7
0x180118477  cmp     word ptr [rdi], 7Dh ; '}'
0x18011847b  jz      loc_1801189DD
0x180118481  lea     rdx, aDelete; "Delete"
0x180118488  mov     rcx, rdi; lpString1
0x18011848b  call    cs:__imp_lstrcmpiW
0x180118492  nop     dword ptr [rax+rax+00h]
0x180118497  lea     rdx, aForceremove; "ForceRemove"
0x18011849e  mov     rcx, rdi; lpString1
0x1801184a1  mov     r14d, eax
0x1801184a4  call    cs:__imp_lstrcmpiW
0x1801184ab  nop     dword ptr [rax+rax+00h]
0x1801184b0  test    eax, eax
0x1801184b2  jz      short loc_1801184BD
0x1801184b4  test    r14d, r14d
0x1801184b7  jnz     loc_18011857E
0x1801184bd  mov     rdx, rdi; unsigned __int16 *
0x1801184c0  mov     rcx, rsi; this
0x1801184c3  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1801184c8  mov     ebx, eax
0x1801184ca  test    eax, eax
0x1801184cc  js      loc_1801189DD
0x1801184d2  test    r15d, r15d
0x1801184d5  jz      loc_18011857E
0x1801184db  mov     edx, 5Ch ; '\'; unsigned __int16
0x1801184e0  mov     [rsp+2300h+hKey], 0
0x1801184e9  mov     rcx, rdi; lpsz
0x1801184ec  mov     [rsp+2300h+var_22A0], 0
0x1801184f5  mov     [rsp+2300h+var_2298], 0
0x1801184fe  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180118503  test    rax, rax
0x180118506  jnz     loc_1801189CE
0x18011850c  mov     rdx, rdi; unsigned __int16 *
0x18011850f  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x180118514  test    eax, eax
0x180118516  jz      short loc_180118533
0x180118518  mov     rdx, rdi; unsigned __int16 *
0x18011851b  mov     [rsp+2300h+hKey], r13
0x180118520  lea     rcx, [rsp+2300h+hKey]; this
0x180118525  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18011852a  mov     [rsp+2300h+hKey], 0
0x180118533  test    r14d, r14d
0x180118536  jnz     short loc_180118574
0x180118538  mov     rdx, rdi; unsigned __int16 *
0x18011853b  mov     rcx, rsi; this
0x18011853e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180118543  xor     r14d, r14d
0x180118546  mov     ebx, eax
0x180118548  test    eax, eax
0x18011854a  js      loc_180118A16
0x180118550  mov     rdx, rdi; unsigned __int16 *
0x180118553  mov     rcx, rsi; this
0x180118556  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18011855b  lea     rcx, [rsp+2300h+hKey]; this
0x180118560  mov     ebx, eax
0x180118562  test    eax, eax
0x180118564  js      loc_180118A1B
0x18011856a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18011856f  jmp     loc_1801187C0
0x180118574  lea     rcx, [rsp+2300h+hKey]; this
0x180118579  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18011857e  lea     rdx, aNoremove; "NoRemove"
0x180118585  mov     rcx, rdi; lpString1
0x180118588  mov     r12d, 1
0x18011858e  call    cs:__imp_lstrcmpiW
0x180118595  nop     dword ptr [rax+rax+00h]
0x18011859a  xor     r14d, r14d
0x18011859d  test    eax, eax
0x18011859f  jnz     short loc_1801185B9
0x1801185a1  mov     rdx, rdi; unsigned __int16 *
0x1801185a4  mov     rcx, rsi; this
0x1801185a7  mov     r12d, r14d
0x1801185aa  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1801185af  mov     ebx, eax
0x1801185b1  test    eax, eax
0x1801185b3  js      loc_1801189DD
0x1801185b9  lea     rdx, aVal; "Val"
0x1801185c0  mov     rcx, rdi; lpString1
0x1801185c3  call    cs:__imp_lstrcmpiW
0x1801185ca  nop     dword ptr [rax+rax+00h]
0x1801185cf  test    eax, eax
0x1801185d1  jnz     loc_1801186C6
0x1801185d7  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x1801185de  mov     rcx, rsi; this
0x1801185e1  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1801185e6  mov     ebx, eax
0x1801185e8  test    eax, eax
0x1801185ea  js      loc_1801189DD
0x1801185f0  mov     rdx, rdi; unsigned __int16 *
0x1801185f3  mov     rcx, rsi; this
0x1801185f6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1801185fb  mov     ebx, eax
0x1801185fd  test    eax, eax
0x1801185ff  js      loc_1801189DD
0x180118605  cmp     word ptr [rdi], 3Dh ; '='
0x180118609  jnz     loc_1801189D8
0x18011860f  test    r15d, r15d
0x180118612  jz      short loc_180118644
0x180118614  mov     r9, rdi; unsigned __int16 *
0x180118617  mov     [rsp+2300h+var_22A0], r14
0x18011861c  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x180118623  mov     [rsp+2300h+var_2298], r14
0x180118628  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x18011862d  mov     [rsp+2300h+hKey], r13
0x180118632  mov     rcx, rsi; this
0x180118635  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18011863a  mov     [rsp+2300h+hKey], r14
0x18011863f  jmp     loc_18011855B
0x180118644  cmp     [rbp+2200h+arg_20], r14d
0x18011864b  jnz     short loc_1801186AC
0x18011864d  test    r12d, r12d
0x180118650  jz      short loc_1801186AC
0x180118652  mov     r9d, 20006h; unsigned int
0x180118658  mov     [rsp+2300h+hKey], r14
0x18011865d  xor     r8d, r8d; lpSubKey
0x180118660  mov     [rsp+2300h+var_22A0], r14
0x180118665  mov     rdx, r13; hKey
0x180118668  mov     [rsp+2300h+var_2298], r14
0x18011866d  lea     rcx, [rsp+2300h+hKey]; this
0x180118672  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180118677  test    eax, eax
0x180118679  jnz     loc_180118A0D
0x18011867f  mov     rcx, [rsp+2300h+hKey]; hKey
0x180118684  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x18011868b  call    cs:__imp_RegDeleteValueW
0x180118692  nop     dword ptr [rax+rax+00h]
0x180118697  test    eax, 0FFFFFFFDh
0x18011869c  jnz     loc_180118A0D
0x1801186a2  lea     rcx, [rsp+2300h+hKey]; this
0x1801186a7  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1801186ac  mov     rdx, rdi; unsigned __int16 *
0x1801186af  mov     rcx, rsi; this
0x1801186b2  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1801186b7  mov     ebx, eax
0x1801186b9  test    eax, eax
0x1801186bb  jns     loc_180118477
0x1801186c1  jmp     loc_1801189DD
0x1801186c6  mov     edx, 5Ch ; '\'; unsigned __int16
0x1801186cb  mov     rcx, rdi; lpsz
0x1801186ce  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1801186d3  test    rax, rax
0x1801186d6  jnz     loc_1801189D8
0x1801186dc  test    r15d, r15d
0x1801186df  jz      loc_18011880F
0x1801186e5  mov     r9d, 2001Fh; unsigned int
0x1801186eb  lea     rcx, [rsp+2300h+var_2290]; this
0x1801186f0  mov     r8, rdi; lpSubKey
0x1801186f3  mov     rdx, r13; hKey
0x1801186f6  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1801186fb  test    eax, eax
0x1801186fd  jz      loc_180118788
0x180118703  mov     r9d, 20019h; unsigned int
0x180118709  lea     rcx, [rsp+2300h+var_2290]; this
0x18011870e  mov     r8, rdi; lpSubKey
0x180118711  mov     rdx, r13; hKey
0x180118714  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180118719  test    eax, eax
0x18011871b  jz      short loc_180118788
0x18011871d  lea     rax, [rbp+2200h+dwDisposition]
0x180118721  mov     [rbp+2200h+dwDisposition], r14d
0x180118725  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x18011872a  xor     r9d, r9d; lpClass
0x18011872d  lea     rax, [rbp+2200h+var_2270]
0x180118731  mov     [rbp+2200h+var_2270], r14
0x180118735  mov     [rsp+2300h+phkResult], rax; phkResult
0x18011873a  xor     r8d, r8d; Reserved
0x18011873d  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180118742  mov     rdx, rdi; lpSubKey
0x180118745  mov     [rsp+2300h+samDesired], 2001Fh; samDesired
0x18011874d  mov     rcx, r13; hKey
0x180118750  mov     dword ptr [rsp+2300h+dwOptions], r14d; dwOptions
0x180118755  call    cs:__imp_RegCreateKeyExW
0x18011875c  nop     dword ptr [rax+rax+00h]
0x180118761  mov     ebx, eax
0x180118763  test    eax, eax
0x180118765  jnz     loc_180118A22
0x18011876b  lea     rcx, [rsp+2300h+var_2290]; this
0x180118770  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180118775  mov     ebx, eax
0x180118777  mov     rax, [rbp+2200h+var_2270]
0x18011877b  mov     [rsp+2300h+var_2290], rax
0x180118780  test    ebx, ebx
0x180118782  jnz     loc_180118A22
0x180118788  mov     rdx, rdi; unsigned __int16 *
0x18011878b  mov     rcx, rsi; this
0x18011878e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180118793  mov     ebx, eax
0x180118795  test    eax, eax
0x180118797  js      loc_1801189DD
0x18011879d  cmp     word ptr [rdi], 3Dh ; '='
0x1801187a1  jnz     short loc_1801187C0
0x1801187a3  mov     r9, rdi; unsigned __int16 *
0x1801187a6  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x1801187ab  xor     r8d, r8d; unsigned __int16 *
0x1801187ae  mov     rcx, rsi; this
0x1801187b1  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x1801187b6  mov     ebx, eax
0x1801187b8  test    eax, eax
0x1801187ba  js      loc_1801189DD
0x1801187c0  cmp     word ptr [rdi], 7Bh ; '{'
0x1801187c4  jnz     loc_180118477
0x1801187ca  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801187ce  inc     rax
0x1801187d1  cmp     [rdi+rax*2], r14w
0x1801187d6  jnz     short loc_1801187CE
0x1801187d8  cmp     rax, 1
0x1801187dc  jnz     loc_180118477
0x1801187e2  mov     r8, [rsp+2300h+var_2290]; HKEY
0x1801187e7  mov     r9d, r15d; int
0x1801187ea  mov     rdx, rdi; unsigned __int16 *
0x1801187ed  mov     dword ptr [rsp+2300h+dwOptions], r14d; int
0x1801187f2  mov     rcx, rsi; this
0x1801187f5  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1801187fa  mov     ebx, eax
0x1801187fc  test    eax, eax
0x1801187fe  js      loc_1801189DD
0x180118804  mov     rdx, rdi
0x180118807  mov     rcx, rsi
0x18011880a  jmp     loc_18011846D
0x18011880f  cmp     [rbp+2200h+arg_20], r14d
0x180118816  jnz     short loc_180118833
0x180118818  mov     r9d, 20019h; unsigned int
0x18011881e  lea     rcx, [rsp+2300h+var_2290]; this
0x180118823  mov     r8, rdi; lpSubKey
0x180118826  mov     rdx, r13; hKey
0x180118829  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18011882e  mov     r14d, eax
0x180118831  jmp     short loc_180118839
0x180118833  mov     r14d, 2
0x180118839  test    r14d, r14d
0x18011883c  lea     rcx, [rbp+2200h+var_2260]
0x180118840  mov     r15d, 1
0x180118846  mov     r8, rdi
0x180118849  cmovz   r15d, [rbp+2200h+arg_20]
0x180118851  mov     edx, 104h
0x180118856  or      r9, 0FFFFFFFFFFFFFFFFh
0x18011885a  call    cs:__imp__o_wcsncpy_s
0x180118861  nop     dword ptr [rax+rax+00h]
0x180118866  mov     ecx, eax; int
0x180118868  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18011886d  mov     rdx, rdi; unsigned __int16 *
0x180118870  mov     rcx, rsi; this
0x180118873  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180118878  mov     ebx, eax
0x18011887a  test    eax, eax
0x18011887c  js      loc_1801189DD
0x180118882  mov     rdx, rdi; unsigned __int16 *
0x180118885  mov     rcx, rsi; this
0x180118888  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18011888d  xor     ecx, ecx
0x18011888f  mov     ebx, eax
0x180118891  test    eax, eax
0x180118893  js      loc_1801189DD
0x180118899  cmp     word ptr [rdi], 7Bh ; '{'
0x18011889d  jnz     short loc_1801188EE
0x18011889f  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801188a3  inc     rax
0x1801188a6  cmp     [rdi+rax*2], cx
0x1801188aa  jnz     short loc_1801188A3
0x1801188ac  cmp     rax, 1
0x1801188b0  jnz     short loc_1801188EE
0x1801188b2  mov     r8, [rsp+2300h+var_2290]; HKEY
0x1801188b7  xor     r9d, r9d; int
0x1801188ba  mov     rdx, rdi; unsigned __int16 *
0x1801188bd  mov     dword ptr [rsp+2300h+dwOptions], r15d; int
0x1801188c2  mov     rcx, rsi; this
0x1801188c5  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1801188ca  mov     ebx, eax
0x1801188cc  test    eax, eax
0x1801188ce  jns     short loc_1801188D9
0x1801188d0  test    r15d, r15d
0x1801188d3  jz      loc_1801189DD
0x1801188d9  mov     rdx, rdi; unsigned __int16 *
0x1801188dc  mov     rcx, rsi; this
0x1801188df  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
  ... truncated ...
```
