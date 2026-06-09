# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180053e48`
- end: `0x1800543c9`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1409`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config`

## callers

- `0x1800536a0`
- `0x180053e48`

## callees

- `0x18004e0c0`
- `0x1800508ac`
- `0x180050e10`
- `0x180050e80`
- `0x180050ec0`
- `0x180051054`
- `0x180051080`
- `0x1800513e0`
- `0x180051a44`
- `0x180052048`
- `0x1800531fc`
- `0x18005358c`
- `0x180053e48`
- `0x1800549e8`
- `0x180054ab8`
- `0x18008e890`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180054209`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180054209`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180054099`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180054099`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180053ebc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180053ecf`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180053fa0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180053fcf`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180053ebc`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180053ecf`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180053fa0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180053fcf`

## string_xrefs

- `0x180053ec5`: `ForceRemove`
- `0x180053f96`: `NoRemove`
- `0x180053eb2`: `Delete`

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
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v30; // [rsp+50h] [rbp-B0h]
  __int64 v31; // [rsp+58h] [rbp-A8h]
  HKEY v32[4]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 v33[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ValueName[4096]; // [rsp+290h] [rbp+190h] BYREF

  v5 = a4;
  v7 = a2;
  v8 = this;
  memset(v32, 0, 24);
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
        v30 = 0;
        v31 = 0;
        if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
        {
          ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
LABEL_79:
          v10 = -2147352567;
          goto LABEL_80;
        }
        if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v12, v7) )
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
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v32[0], v5, 0);
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
        if ( !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v32, a3, v7, 0x2001Fu)
          || !(unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v32, a3, v7, 0x20019u)
          || (v17 = ATL::CRegKey::Create((ATL::CRegKey *)v32, a3, v7, v16, v27)) == 0 )
        {
          v10 = ATL::CRegParser::NextToken(v8, v7);
          if ( v10 < 0 )
            goto LABEL_80;
          if ( *v7 == 61 )
          {
            v10 = ATL::CRegParser::AddValue(v8, v32, 0, v7);
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
        v19 = ATL::CRegKey::Open((ATL::CRegKey *)v32, a3, v7, 0x20019u);
      v20 = 1;
      if ( !v19 )
        v20 = a5;
      v21 = _o_wcsncpy_s(v33, 260, v7, -1, v27);
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
          v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v32[0], 0, v20);
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
        else if ( a5 && ATL::CRegParser::HasSubKeys(v22, v32[0]) )
        {
          if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v22, v33) && v14 )
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v32, v33);
        }
        else
        {
          HasSubKeys = ATL::CRegParser::HasSubKeys(v22, v32[0]);
          v17 = ATL::CRegKey::Close((ATL::CRegKey *)v32);
          if ( v17 )
            goto LABEL_83;
          if ( v14 && !HasSubKeys )
          {
            v30 = 0;
            v31 = 0;
            hKey = a3;
            v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, v33);
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
      v30 = 0;
      v31 = 0;
      hKey = a3;
      v13 = ATL::CRegParser::AddValue(v8, &hKey, ValueName, v7);
      v10 = v13;
      hKey = 0;
      goto LABEL_15;
    }
    if ( a5 || !v14 )
      goto LABEL_31;
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
  ATL::CRegKey::Close((ATL::CRegKey *)v32);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180053e48  push    rbp
0x180053e4a  push    rbx
0x180053e4b  push    rsi
0x180053e4c  push    rdi
0x180053e4d  push    r12
0x180053e4f  push    r13
0x180053e51  push    r14
0x180053e53  push    r15
0x180053e55  lea     rbp, [rsp-21A8h]
0x180053e5d  mov     eax, 22A8h
0x180053e62  call    _alloca_probe
0x180053e67  sub     rsp, rax
0x180053e6a  mov     rax, cs:__security_cookie
0x180053e71  xor     rax, rsp
0x180053e74  mov     [rbp+21E0h+var_50], rax
0x180053e7b  mov     r15d, r9d
0x180053e7e  mov     [rsp+22E0h+var_22A0], r9d
0x180053e83  mov     r13, r8
0x180053e86  mov     rdi, rdx
0x180053e89  mov     rsi, rcx
0x180053e8c  xor     r12d, r12d
0x180053e8f  mov     [rsp+22E0h+var_2280], r12
0x180053e94  mov     [rsp+22E0h+var_2278], r12
0x180053e99  mov     [rsp+22E0h+var_2270], r12
0x180053e9e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180053ea3  mov     ebx, eax
0x180053ea5  test    eax, eax
0x180053ea7  js      loc_18005437D
0x180053ead  jmp     loc_180054304
0x180053eb2  lea     rdx, aDelete_0; "Delete"
0x180053eb9  mov     rcx, rdi; lpString1
0x180053ebc  call    cs:__imp_lstrcmpiW
0x180053ec2  mov     r14d, eax
0x180053ec5  lea     rdx, aForceremove; "ForceRemove"
0x180053ecc  mov     rcx, rdi; lpString1
0x180053ecf  call    cs:__imp_lstrcmpiW
0x180053ed5  test    eax, eax
0x180053ed7  jz      short loc_180053EE2
0x180053ed9  test    r14d, r14d
0x180053edc  jnz     loc_180053F90
0x180053ee2  mov     rdx, rdi; unsigned __int16 *
0x180053ee5  mov     rcx, rsi; this
0x180053ee8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180053eed  mov     ebx, eax
0x180053eef  test    eax, eax
0x180053ef1  js      loc_18005437D
0x180053ef7  test    r15d, r15d
0x180053efa  jz      loc_180053F90
0x180053f00  mov     [rsp+22E0h+hKey], r12
0x180053f05  mov     [rsp+22E0h+var_2290], r12
0x180053f0a  mov     [rsp+22E0h+var_2288], r12
0x180053f0f  mov     edx, 5Ch ; '\'; unsigned __int16
0x180053f14  mov     rcx, rdi; lpsz
0x180053f17  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180053f1c  test    rax, rax
0x180053f1f  jnz     loc_18005436E
0x180053f25  mov     rdx, rdi; unsigned __int16 *
0x180053f28  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x180053f2d  test    eax, eax
0x180053f2f  jz      short loc_180053F48
0x180053f31  mov     [rsp+22E0h+hKey], r13
0x180053f36  mov     rdx, rdi; unsigned __int16 *
0x180053f39  lea     rcx, [rsp+22E0h+hKey]; this
0x180053f3e  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180053f43  mov     [rsp+22E0h+hKey], r12
0x180053f48  test    r14d, r14d
0x180053f4b  jnz     short loc_180053F86
0x180053f4d  mov     rdx, rdi; unsigned __int16 *
0x180053f50  mov     rcx, rsi; this
0x180053f53  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180053f58  mov     ebx, eax
0x180053f5a  test    eax, eax
0x180053f5c  js      loc_1800543B5
0x180053f62  mov     rdx, rdi; unsigned __int16 *
0x180053f65  mov     rcx, rsi; this
0x180053f68  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180053f6d  mov     ebx, eax
0x180053f6f  test    eax, eax
0x180053f71  lea     rcx, [rsp+22E0h+hKey]; this
0x180053f76  js      loc_1800543BA
0x180053f7c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180053f81  jmp     loc_18005416F
0x180053f86  lea     rcx, [rsp+22E0h+hKey]; this
0x180053f8b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180053f90  mov     r12d, 1
0x180053f96  lea     rdx, aNoremove; "NoRemove"
0x180053f9d  mov     rcx, rdi; lpString1
0x180053fa0  call    cs:__imp_lstrcmpiW
0x180053fa6  xor     r14d, r14d
0x180053fa9  test    eax, eax
0x180053fab  jnz     short loc_180053FC5
0x180053fad  mov     r12d, r14d
0x180053fb0  mov     rdx, rdi; unsigned __int16 *
0x180053fb3  mov     rcx, rsi; this
0x180053fb6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180053fbb  mov     ebx, eax
0x180053fbd  test    eax, eax
0x180053fbf  js      loc_18005437D
0x180053fc5  lea     rdx, aVal; "Val"
0x180053fcc  mov     rcx, rdi; lpString1
0x180053fcf  call    cs:__imp_lstrcmpiW
0x180053fd5  test    eax, eax
0x180053fd7  jnz     loc_1800540C9
0x180053fdd  lea     rdx, [rbp+21E0h+ValueName]; unsigned __int16 *
0x180053fe4  mov     rcx, rsi; this
0x180053fe7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180053fec  mov     ebx, eax
0x180053fee  test    eax, eax
0x180053ff0  js      loc_18005437D
0x180053ff6  mov     rdx, rdi; unsigned __int16 *
0x180053ff9  mov     rcx, rsi; this
0x180053ffc  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180054001  mov     ebx, eax
0x180054003  test    eax, eax
0x180054005  js      loc_18005437D
0x18005400b  cmp     word ptr [rdi], 3Dh ; '='
0x18005400f  jnz     loc_180054378
0x180054015  test    r15d, r15d
0x180054018  jz      short loc_18005404F
0x18005401a  xor     r12d, r12d
0x18005401d  mov     [rsp+22E0h+var_2290], r12
0x180054022  mov     [rsp+22E0h+var_2288], r12
0x180054027  mov     [rsp+22E0h+hKey], r13
0x18005402c  mov     r9, rdi; unsigned __int16 *
0x18005402f  lea     r8, [rbp+21E0h+ValueName]; unsigned __int16 *
0x180054036  lea     rdx, [rsp+22E0h+hKey]; struct ATL::CRegKey *
0x18005403b  mov     rcx, rsi; this
0x18005403e  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180054043  mov     ebx, eax
0x180054045  mov     [rsp+22E0h+hKey], r12
0x18005404a  jmp     loc_180053F6F
0x18005404f  cmp     [rbp+21E0h+arg_20], r14d
0x180054056  jnz     short loc_1800540B6
0x180054058  test    r12d, r12d
0x18005405b  jz      short loc_1800540B6
0x18005405d  xor     r12d, r12d
0x180054060  mov     [rsp+22E0h+hKey], r12
0x180054065  mov     [rsp+22E0h+var_2290], r12
0x18005406a  mov     [rsp+22E0h+var_2288], r12
0x18005406f  mov     r9d, 20006h; unsigned int
0x180054075  xor     r8d, r8d; lpSubKey
0x180054078  mov     rdx, r13; hKey
0x18005407b  lea     rcx, [rsp+22E0h+hKey]; this
0x180054080  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180054085  test    eax, eax
0x180054087  jnz     loc_1800543AC
0x18005408d  lea     rdx, [rbp+21E0h+ValueName]; lpValueName
0x180054094  mov     rcx, [rsp+22E0h+hKey]; hKey
0x180054099  call    cs:__imp_RegDeleteValueW
0x18005409f  test    eax, 0FFFFFFFDh
0x1800540a4  jnz     loc_1800543AC
0x1800540aa  lea     rcx, [rsp+22E0h+hKey]; this
0x1800540af  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x1800540b4  jmp     short loc_1800540B9
0x1800540b6  xor     r12d, r12d
0x1800540b9  mov     rdx, rdi; unsigned __int16 *
0x1800540bc  mov     rcx, rsi; this
0x1800540bf  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1800540c4  jmp     loc_180053EA3
0x1800540c9  mov     edx, 5Ch ; '\'; unsigned __int16
0x1800540ce  mov     rcx, rdi; lpsz
0x1800540d1  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1800540d6  test    rax, rax
0x1800540d9  jnz     loc_180054378
0x1800540df  test    r15d, r15d
0x1800540e2  jz      loc_1800541BE
0x1800540e8  mov     r9d, 2001Fh; unsigned int
0x1800540ee  mov     r8, rdi; lpSubKey
0x1800540f1  mov     rdx, r13; hKey
0x1800540f4  lea     rcx, [rsp+22E0h+var_2280]; this
0x1800540f9  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800540fe  xor     r12d, r12d
0x180054101  test    eax, eax
0x180054103  jz      short loc_180054137
0x180054105  mov     r9d, 20019h; unsigned int
0x18005410b  mov     r8, rdi; lpSubKey
0x18005410e  mov     rdx, r13; hKey
0x180054111  lea     rcx, [rsp+22E0h+var_2280]; this
0x180054116  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18005411b  test    eax, eax
0x18005411d  jz      short loc_180054137
0x18005411f  mov     r8, rdi; lpSubKey
0x180054122  mov     rdx, r13; hKey
0x180054125  lea     rcx, [rsp+22E0h+var_2280]; this
0x18005412a  call    ?Create@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGPEAGKKPEAU_SECURITY_ATTRIBUTES@@PEAK@Z; ATL::CRegKey::Create(HKEY__ *,ushort const *,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong *)
0x18005412f  test    eax, eax
0x180054131  jnz     loc_1800543C1
0x180054137  mov     rdx, rdi; unsigned __int16 *
0x18005413a  mov     rcx, rsi; this
0x18005413d  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180054142  mov     ebx, eax
0x180054144  test    eax, eax
0x180054146  js      loc_18005437D
0x18005414c  cmp     word ptr [rdi], 3Dh ; '='
0x180054150  jnz     short loc_18005416F
0x180054152  mov     r9, rdi; unsigned __int16 *
0x180054155  xor     r8d, r8d; unsigned __int16 *
0x180054158  lea     rdx, [rsp+22E0h+var_2280]; struct ATL::CRegKey *
0x18005415d  mov     rcx, rsi; this
0x180054160  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180054165  mov     ebx, eax
0x180054167  test    eax, eax
0x180054169  js      loc_18005437D
0x18005416f  cmp     word ptr [rdi], 7Bh ; '{'
0x180054173  jnz     loc_180054304
0x180054179  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005417d  inc     rax
0x180054180  cmp     [rdi+rax*2], r12w
0x180054185  jnz     short loc_18005417D
0x180054187  cmp     rax, 1
0x18005418b  jnz     loc_180054304
0x180054191  mov     dword ptr [rsp+22E0h+var_22C0], r12d; int
0x180054196  mov     r9d, r15d; int
0x180054199  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x18005419e  mov     rdx, rdi; unsigned __int16 *
0x1800541a1  mov     rcx, rsi; this
0x1800541a4  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800541a9  mov     ebx, eax
0x1800541ab  test    eax, eax
0x1800541ad  js      loc_18005437D
0x1800541b3  mov     rdx, rdi
0x1800541b6  mov     rcx, rsi
0x1800541b9  jmp     loc_180053E9E
0x1800541be  cmp     [rbp+21E0h+arg_20], r14d
0x1800541c5  jnz     short loc_1800541E2
0x1800541c7  mov     r9d, 20019h; unsigned int
0x1800541cd  mov     r8, rdi; lpSubKey
0x1800541d0  mov     rdx, r13; hKey
0x1800541d3  lea     rcx, [rsp+22E0h+var_2280]; this
0x1800541d8  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800541dd  mov     r14d, eax
0x1800541e0  jmp     short loc_1800541E8
0x1800541e2  mov     r14d, 2
0x1800541e8  mov     r15d, 1
0x1800541ee  test    r14d, r14d
0x1800541f1  cmovz   r15d, [rbp+21E0h+arg_20]
0x1800541f9  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800541fd  mov     r8, rdi
0x180054200  mov     edx, 104h
0x180054205  lea     rcx, [rbp+21E0h+var_2260]
0x180054209  call    cs:__imp__o_wcsncpy_s
0x18005420f  mov     ecx, eax; int
0x180054211  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180054216  mov     rdx, rdi; unsigned __int16 *
0x180054219  mov     rcx, rsi; this
0x18005421c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180054221  mov     ebx, eax
0x180054223  test    eax, eax
0x180054225  js      loc_18005437D
0x18005422b  mov     rdx, rdi; unsigned __int16 *
0x18005422e  mov     rcx, rsi; this
0x180054231  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180054236  mov     ebx, eax
0x180054238  xor     ecx, ecx; this
0x18005423a  test    eax, eax
0x18005423c  js      loc_18005437D
0x180054242  cmp     word ptr [rdi], 7Bh ; '{'
0x180054246  jnz     short loc_18005429C
0x180054248  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005424c  inc     rax
0x18005424f  cmp     [rdi+rax*2], cx
0x180054253  jnz     short loc_18005424C
0x180054255  cmp     rax, 1
0x180054259  jnz     short loc_18005429C
0x18005425b  mov     dword ptr [rsp+22E0h+var_22C0], r15d; int
0x180054260  xor     r9d, r9d; int
0x180054263  mov     r8, [rsp+22E0h+var_2280]; HKEY
0x180054268  mov     rdx, rdi; unsigned __int16 *
0x18005426b  mov     rcx, rsi; this
0x18005426e  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180054273  mov     ebx, eax
0x180054275  test    eax, eax
0x180054277  jns     short loc_180054282
0x180054279  test    r15d, r15d
0x18005427c  jz      loc_18005437D
0x180054282  mov     rdx, rdi; unsigned __int16 *
0x180054285  mov     rcx, rsi; this
0x180054288  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18005428d  mov     ebx, eax
0x18005428f  xor     r15d, r15d
0x180054292  test    eax, eax
0x180054294  js      loc_18005437D
0x18005429a  jmp     short loc_18005429F
0x18005429c  xor     r15d, r15d
0x18005429f  cmp     r14d, 2
0x1800542a3  jz      short loc_1800542FC
0x1800542a5  test    r14d, r14d
0x1800542a8  jz      short loc_1800542C5
0x1800542aa  xor     r12d, r12d
0x1800542ad  cmp     [rbp+21E0h+arg_20], r12d
0x1800542b4  jnz     short loc_1800542FF
0x1800542b6  mov     ecx, r14d; unsigned int
0x1800542b9  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800542be  mov     ebx, eax
0x1800542c0  jmp     loc_18005437D
0x1800542c5  cmp     [rbp+21E0h+arg_20], r15d
0x1800542cc  jz      short loc_180054310
0x1800542ce  mov     rdx, [rsp+22E0h+var_2280]; HKEY
0x1800542d3  call    ?HasSubKeys@CRegParser@ATL@@IEAAHPEAUHKEY__@@@Z; ATL::CRegParser::HasSubKeys(HKEY__ *)
0x1800542d8  test    eax, eax
  ... truncated ...
```
