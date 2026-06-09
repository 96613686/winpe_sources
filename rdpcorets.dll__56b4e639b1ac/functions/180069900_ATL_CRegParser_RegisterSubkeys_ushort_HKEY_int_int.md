# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180069900`
- end: `0x180069efd`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1533`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x18006954c`
- `0x180069900`

## callees

- `0x180033da0`
- `0x1800674a8`
- `0x180067be4`
- `0x180067c54`
- `0x1800683c4`
- `0x1800684d4`
- `0x18006877c`
- `0x180068a78`
- `0x180068b70`
- `0x180068cd0`
- `0x180069438`
- `0x180069900`
- `0x18006a084`
- `0x18006a154`
- `0x18014c2b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180069d1a`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180069d1a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180069c1b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180069c1b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180069b5b`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180069b5b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180069973`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180069986`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180069a6a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180069a99`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180069973`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180069986`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180069a6a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180069a99`

## string_xrefs

- `0x180069979`: `ForceRemove`
- `0x180069a5a`: `NoRemove`
- `0x180069969`: `Delete`

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
0x180069900  push    rbp
0x180069902  push    rbx
0x180069903  push    rsi
0x180069904  push    rdi
0x180069905  push    r12
0x180069907  push    r13
0x180069909  push    r14
0x18006990b  push    r15
0x18006990d  lea     rbp, [rsp-21C8h]
0x180069915  mov     eax, 22C8h
0x18006991a  call    _alloca_probe
0x18006991f  sub     rsp, rax
0x180069922  mov     rax, cs:__security_cookie
0x180069929  xor     rax, rsp
0x18006992c  mov     [rbp+2200h+var_50], rax
0x180069933  xor     r14d, r14d
0x180069936  mov     [rsp+2300h+var_22B0], r9d
0x18006993b  mov     [rsp+2300h+var_2290], r14
0x180069940  mov     r15d, r9d
0x180069943  mov     [rsp+2300h+var_2288], r14
0x180069948  mov     r13, r8
0x18006994b  mov     [rbp+2200h+var_2280], r14
0x18006994f  mov     rdi, rdx
0x180069952  mov     rsi, rcx
0x180069955  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18006995a  jmp     loc_180069B81
0x18006995f  cmp     word ptr [rdi], 7Dh ; '}'
0x180069963  jz      loc_180069E97
0x180069969  lea     rdx, aDelete; "Delete"
0x180069970  mov     rcx, rdi; lpString1
0x180069973  call    cs:__imp_lstrcmpiW
0x180069979  lea     rdx, aForceremove; "ForceRemove"
0x180069980  mov     rcx, rdi; lpString1
0x180069983  mov     r14d, eax
0x180069986  call    cs:__imp_lstrcmpiW
0x18006998c  test    eax, eax
0x18006998e  jz      short loc_180069999
0x180069990  test    r14d, r14d
0x180069993  jnz     loc_180069A5A
0x180069999  mov     rdx, rdi; unsigned __int16 *
0x18006999c  mov     rcx, rsi; this
0x18006999f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800699a4  mov     ebx, eax
0x1800699a6  test    eax, eax
0x1800699a8  js      loc_180069E97
0x1800699ae  test    r15d, r15d
0x1800699b1  jz      loc_180069A5A
0x1800699b7  mov     edx, 5Ch ; '\'; unsigned __int16
0x1800699bc  mov     [rsp+2300h+hKey], 0
0x1800699c5  mov     rcx, rdi; lpsz
0x1800699c8  mov     [rsp+2300h+var_22A0], 0
0x1800699d1  mov     [rsp+2300h+var_2298], 0
0x1800699da  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1800699df  test    rax, rax
0x1800699e2  jnz     loc_180069E88
0x1800699e8  mov     rdx, rdi; unsigned __int16 *
0x1800699eb  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x1800699f0  test    eax, eax
0x1800699f2  jz      short loc_180069A0F
0x1800699f4  mov     rdx, rdi; unsigned __int16 *
0x1800699f7  mov     [rsp+2300h+hKey], r13
0x1800699fc  lea     rcx, [rsp+2300h+hKey]; this
0x180069a01  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180069a06  mov     [rsp+2300h+hKey], 0
0x180069a0f  test    r14d, r14d
0x180069a12  jnz     short loc_180069A50
0x180069a14  mov     rdx, rdi; unsigned __int16 *
0x180069a17  mov     rcx, rsi; this
0x180069a1a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180069a1f  xor     r14d, r14d
0x180069a22  mov     ebx, eax
0x180069a24  test    eax, eax
0x180069a26  js      loc_180069ECF
0x180069a2c  mov     rdx, rdi; unsigned __int16 *
0x180069a2f  mov     rcx, rsi; this
0x180069a32  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180069a37  lea     rcx, [rsp+2300h+hKey]; this
0x180069a3c  mov     ebx, eax
0x180069a3e  test    eax, eax
0x180069a40  js      loc_180069ED4
0x180069a46  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180069a4b  jmp     loc_180069C80
0x180069a50  lea     rcx, [rsp+2300h+hKey]; this
0x180069a55  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180069a5a  lea     rdx, aNoremove; "NoRemove"
0x180069a61  mov     rcx, rdi; lpString1
0x180069a64  mov     r12d, 1
0x180069a6a  call    cs:__imp_lstrcmpiW
0x180069a70  xor     r14d, r14d
0x180069a73  test    eax, eax
0x180069a75  jnz     short loc_180069A8F
0x180069a77  mov     rdx, rdi; unsigned __int16 *
0x180069a7a  mov     rcx, rsi; this
0x180069a7d  mov     r12d, r14d
0x180069a80  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180069a85  mov     ebx, eax
0x180069a87  test    eax, eax
0x180069a89  js      loc_180069E97
0x180069a8f  lea     rdx, aVal; "Val"
0x180069a96  mov     rcx, rdi; lpString1
0x180069a99  call    cs:__imp_lstrcmpiW
0x180069a9f  test    eax, eax
0x180069aa1  jnz     loc_180069B90
0x180069aa7  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x180069aae  mov     rcx, rsi; this
0x180069ab1  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180069ab6  mov     ebx, eax
0x180069ab8  test    eax, eax
0x180069aba  js      loc_180069E97
0x180069ac0  mov     rdx, rdi; unsigned __int16 *
0x180069ac3  mov     rcx, rsi; this
0x180069ac6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180069acb  mov     ebx, eax
0x180069acd  test    eax, eax
0x180069acf  js      loc_180069E97
0x180069ad5  cmp     word ptr [rdi], 3Dh ; '='
0x180069ad9  jnz     loc_180069E92
0x180069adf  test    r15d, r15d
0x180069ae2  jz      short loc_180069B14
0x180069ae4  mov     r9, rdi; unsigned __int16 *
0x180069ae7  mov     [rsp+2300h+var_22A0], r14
0x180069aec  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x180069af3  mov     [rsp+2300h+var_2298], r14
0x180069af8  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x180069afd  mov     [rsp+2300h+hKey], r13
0x180069b02  mov     rcx, rsi; this
0x180069b05  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180069b0a  mov     [rsp+2300h+hKey], r14
0x180069b0f  jmp     loc_180069A37
0x180069b14  cmp     [rbp+2200h+arg_20], r14d
0x180069b1b  jnz     short loc_180069B76
0x180069b1d  test    r12d, r12d
0x180069b20  jz      short loc_180069B76
0x180069b22  mov     r9d, 20006h; unsigned int
0x180069b28  mov     [rsp+2300h+hKey], r14
0x180069b2d  xor     r8d, r8d; lpSubKey
0x180069b30  mov     [rsp+2300h+var_22A0], r14
0x180069b35  mov     rdx, r13; hKey
0x180069b38  mov     [rsp+2300h+var_2298], r14
0x180069b3d  lea     rcx, [rsp+2300h+hKey]; this
0x180069b42  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180069b47  test    eax, eax
0x180069b49  jnz     loc_180069EC6
0x180069b4f  mov     rcx, [rsp+2300h+hKey]; hKey
0x180069b54  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x180069b5b  call    cs:__imp_RegDeleteValueW
0x180069b61  test    eax, 0FFFFFFFDh
0x180069b66  jnz     loc_180069EC6
0x180069b6c  lea     rcx, [rsp+2300h+hKey]; this
0x180069b71  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180069b76  mov     rdx, rdi; unsigned __int16 *
0x180069b79  mov     rcx, rsi; this
0x180069b7c  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180069b81  mov     ebx, eax
0x180069b83  test    eax, eax
0x180069b85  jns     loc_18006995F
0x180069b8b  jmp     loc_180069E97
0x180069b90  mov     edx, 5Ch ; '\'; unsigned __int16
0x180069b95  mov     rcx, rdi; lpsz
0x180069b98  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180069b9d  test    rax, rax
0x180069ba0  jnz     loc_180069E92
0x180069ba6  test    r15d, r15d
0x180069ba9  jz      loc_180069CCF
0x180069baf  mov     r9d, 2001Fh; unsigned int
0x180069bb5  lea     rcx, [rsp+2300h+var_2290]; this
0x180069bba  mov     r8, rdi; lpSubKey
0x180069bbd  mov     rdx, r13; hKey
0x180069bc0  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180069bc5  test    eax, eax
0x180069bc7  jz      short loc_180069C48
0x180069bc9  mov     r9d, 20019h; unsigned int
0x180069bcf  lea     rcx, [rsp+2300h+var_2290]; this
0x180069bd4  mov     r8, rdi; lpSubKey
0x180069bd7  mov     rdx, r13; hKey
0x180069bda  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180069bdf  test    eax, eax
0x180069be1  jz      short loc_180069C48
0x180069be3  lea     rax, [rbp+2200h+dwDisposition]
0x180069be7  mov     [rbp+2200h+dwDisposition], r14d
0x180069beb  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x180069bf0  xor     r9d, r9d; lpClass
0x180069bf3  lea     rax, [rbp+2200h+var_2270]
0x180069bf7  mov     [rbp+2200h+var_2270], r14
0x180069bfb  mov     [rsp+2300h+phkResult], rax; phkResult
0x180069c00  xor     r8d, r8d; Reserved
0x180069c03  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180069c08  mov     rdx, rdi; lpSubKey
0x180069c0b  mov     [rsp+2300h+samDesired], 2001Fh; samDesired
0x180069c13  mov     rcx, r13; hKey
0x180069c16  mov     dword ptr [rsp+2300h+dwOptions], r14d; dwOptions
0x180069c1b  call    cs:__imp_RegCreateKeyExW
0x180069c21  mov     ebx, eax
0x180069c23  test    eax, eax
0x180069c25  jnz     loc_180069EDB
0x180069c2b  lea     rcx, [rsp+2300h+var_2290]; this
0x180069c30  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180069c35  mov     ebx, eax
0x180069c37  mov     rax, [rbp+2200h+var_2270]
0x180069c3b  mov     [rsp+2300h+var_2290], rax
0x180069c40  test    ebx, ebx
0x180069c42  jnz     loc_180069EDB
0x180069c48  mov     rdx, rdi; unsigned __int16 *
0x180069c4b  mov     rcx, rsi; this
0x180069c4e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180069c53  mov     ebx, eax
0x180069c55  test    eax, eax
0x180069c57  js      loc_180069E97
0x180069c5d  cmp     word ptr [rdi], 3Dh ; '='
0x180069c61  jnz     short loc_180069C80
0x180069c63  mov     r9, rdi; unsigned __int16 *
0x180069c66  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x180069c6b  xor     r8d, r8d; unsigned __int16 *
0x180069c6e  mov     rcx, rsi; this
0x180069c71  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180069c76  mov     ebx, eax
0x180069c78  test    eax, eax
0x180069c7a  js      loc_180069E97
0x180069c80  cmp     word ptr [rdi], 7Bh ; '{'
0x180069c84  jnz     loc_18006995F
0x180069c8a  or      rax, 0FFFFFFFFFFFFFFFFh
0x180069c8e  inc     rax
0x180069c91  cmp     [rdi+rax*2], r14w
0x180069c96  jnz     short loc_180069C8E
0x180069c98  cmp     rax, 1
0x180069c9c  jnz     loc_18006995F
0x180069ca2  mov     r8, [rsp+2300h+var_2290]; HKEY
0x180069ca7  mov     r9d, r15d; int
0x180069caa  mov     rdx, rdi; unsigned __int16 *
0x180069cad  mov     dword ptr [rsp+2300h+dwOptions], r14d; int
0x180069cb2  mov     rcx, rsi; this
0x180069cb5  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180069cba  mov     ebx, eax
0x180069cbc  test    eax, eax
0x180069cbe  js      loc_180069E97
0x180069cc4  mov     rdx, rdi
0x180069cc7  mov     rcx, rsi
0x180069cca  jmp     loc_180069955
0x180069ccf  cmp     [rbp+2200h+arg_20], r14d
0x180069cd6  jnz     short loc_180069CF3
0x180069cd8  mov     r9d, 20019h; unsigned int
0x180069cde  lea     rcx, [rsp+2300h+var_2290]; this
0x180069ce3  mov     r8, rdi; lpSubKey
0x180069ce6  mov     rdx, r13; hKey
0x180069ce9  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180069cee  mov     r14d, eax
0x180069cf1  jmp     short loc_180069CF9
0x180069cf3  mov     r14d, 2
0x180069cf9  test    r14d, r14d
0x180069cfc  lea     rcx, [rbp+2200h+var_2260]
0x180069d00  mov     r15d, 1
0x180069d06  mov     r8, rdi
0x180069d09  cmovz   r15d, [rbp+2200h+arg_20]
0x180069d11  mov     edx, 104h
0x180069d16  or      r9, 0FFFFFFFFFFFFFFFFh
0x180069d1a  call    cs:__imp__o_wcsncpy_s
0x180069d20  mov     ecx, eax; int
0x180069d22  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180069d27  mov     rdx, rdi; unsigned __int16 *
0x180069d2a  mov     rcx, rsi; this
0x180069d2d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180069d32  mov     ebx, eax
0x180069d34  test    eax, eax
0x180069d36  js      loc_180069E97
0x180069d3c  mov     rdx, rdi; unsigned __int16 *
0x180069d3f  mov     rcx, rsi; this
0x180069d42  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180069d47  xor     ecx, ecx
0x180069d49  mov     ebx, eax
0x180069d4b  test    eax, eax
0x180069d4d  js      loc_180069E97
0x180069d53  cmp     word ptr [rdi], 7Bh ; '{'
0x180069d57  jnz     short loc_180069DA8
0x180069d59  or      rax, 0FFFFFFFFFFFFFFFFh
0x180069d5d  inc     rax
0x180069d60  cmp     [rdi+rax*2], cx
0x180069d64  jnz     short loc_180069D5D
0x180069d66  cmp     rax, 1
0x180069d6a  jnz     short loc_180069DA8
0x180069d6c  mov     r8, [rsp+2300h+var_2290]; HKEY
0x180069d71  xor     r9d, r9d; int
0x180069d74  mov     rdx, rdi; unsigned __int16 *
0x180069d77  mov     dword ptr [rsp+2300h+dwOptions], r15d; int
0x180069d7c  mov     rcx, rsi; this
0x180069d7f  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180069d84  mov     ebx, eax
0x180069d86  test    eax, eax
0x180069d88  jns     short loc_180069D93
0x180069d8a  test    r15d, r15d
0x180069d8d  jz      loc_180069E97
0x180069d93  mov     rdx, rdi; unsigned __int16 *
0x180069d96  mov     rcx, rsi; this
0x180069d99  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180069d9e  mov     ebx, eax
0x180069da0  test    eax, eax
0x180069da2  js      loc_180069E97
0x180069da8  mov     r15d, [rsp+2300h+var_22B0]
0x180069dad  cmp     r14d, 2
0x180069db1  jz      loc_18006995F
0x180069db7  test    r14d, r14d
  ... truncated ...
```
