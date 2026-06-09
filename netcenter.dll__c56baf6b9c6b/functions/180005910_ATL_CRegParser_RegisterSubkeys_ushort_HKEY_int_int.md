# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x180005910`
- end: `0x180005ee9`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1497`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x1800055ec`
- `0x180005910`

## callees

- `0x180002270`
- `0x18000441c`
- `0x180004aa0`
- `0x180004b10`
- `0x180004b48`
- `0x180004c64`
- `0x180004d4c`
- `0x180004f38`
- `0x180005030`
- `0x180005190`
- `0x1800054d8`
- `0x180005910`
- `0x180005f70`
- `0x180006040`
- `0x180022330`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180005d16`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180005d16`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180005c17`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180005c17`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180005b65`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x180005b65`
- `KERNEL32!lstrcmpiW` at `0x18000598b`
- `KERNEL32!lstrcmpiW` at `0x18000599e`
- `KERNEL32!lstrcmpiW` at `0x180005a72`
- `KERNEL32!lstrcmpiW` at `0x180005aa1`
- `KERNEL32!lstrcmpiW` at `0x18000598b`
- `KERNEL32!lstrcmpiW` at `0x18000599e`
- `KERNEL32!lstrcmpiW` at `0x180005a72`
- `KERNEL32!lstrcmpiW` at `0x180005aa1`

## string_xrefs

- `0x180005994`: `ForceRemove`
- `0x180005a68`: `NoRemove`
- `0x180005981`: `Delete`

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
  int v20; // eax
  ATL::CRegParser *v21; // rcx
  __int64 v22; // rax
  int HasSubKeys; // r14d
  LSTATUS v24; // eax
  __int64 dwOptions; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+60h] [rbp-A0h]
  __int64 v30; // [rsp+68h] [rbp-98h]
  HKEY v31[3]; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v34[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ValueName[4096]; // [rsp+2B0h] [rbp+1B0h] BYREF

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
          v29 = 0;
          v30 = 0;
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
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v31, a3, v7, 0x2001Fu) )
        {
          if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v31, a3, v7, 0x20019u) )
          {
            dwDisposition = 0;
            phkResult = 0;
            v16 = RegCreateKeyExW(a3, v7, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
            if ( v16 )
              goto LABEL_65;
            v16 = ATL::CRegKey::Close((ATL::CRegKey *)v31);
            v31[0] = phkResult;
            if ( v16 )
              goto LABEL_65;
          }
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        if ( *v7 == 61 )
        {
          v10 = ATL::CRegParser::AddValue(v8, v31, 0, v7);
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
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v31[0], v5, 0);
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
          v18 = ATL::CRegKey::Open((ATL::CRegKey *)v31, a3, v7, 0x20019u);
        v19 = 1;
        if ( !v18 )
          v19 = a5;
        v20 = _o_wcsncpy_s(v34, 260, v7, -1, dwOptions);
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
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v31[0], 0, v19);
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
          else if ( a5 && ATL::CRegParser::HasSubKeys(v21, v31[0]) )
          {
            if ( ATL::CRegParser::CanForceRemoveKey(v21, v34) && v14 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v31, v34);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v21, v31[0]);
            v24 = ATL::CRegKey::Close((ATL::CRegKey *)v31);
            if ( v24 )
            {
              v16 = v24;
              goto LABEL_65;
            }
            if ( v14 && !HasSubKeys )
            {
              v29 = 0;
              v30 = 0;
              hKey = a3;
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, v34);
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
      v29 = 0;
      v30 = 0;
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
    v29 = 0;
    v30 = 0;
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
  ATL::CRegKey::Close((ATL::CRegKey *)v31);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180005910  push    rbp
0x180005912  push    rbx
0x180005913  push    rsi
0x180005914  push    rdi
0x180005915  push    r12
0x180005917  push    r13
0x180005919  push    r14
0x18000591b  push    r15
0x18000591d  lea     rbp, [rsp-21C8h]
0x180005925  mov     eax, 22C8h
0x18000592a  call    _alloca_probe
0x18000592f  sub     rsp, rax
0x180005932  mov     rax, cs:__security_cookie
0x180005939  xor     rax, rsp
0x18000593c  mov     [rbp+2200h+var_50], rax
0x180005943  mov     r15d, r9d
0x180005946  mov     [rsp+2300h+var_22B0], r9d
0x18000594b  mov     r13, r8
0x18000594e  mov     rdi, rdx
0x180005951  mov     rsi, rcx
0x180005954  xor     r14d, r14d
0x180005957  mov     [rsp+2300h+var_2290], r14
0x18000595c  mov     [rsp+2300h+var_2288], r14
0x180005961  mov     [rbp+2200h+var_2280], r14
0x180005965  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000596a  test    eax, eax
0x18000596c  mov     ebx, eax
0x18000596e  js      loc_180005E9D
0x180005974  xor     r12d, r12d
0x180005977  cmp     word ptr [rdi], 7Dh ; '}'
0x18000597b  jz      loc_180005E9D
0x180005981  lea     rdx, String2; "Delete"
0x180005988  mov     rcx, rdi; lpString1
0x18000598b  call    cs:__imp_lstrcmpiW
0x180005991  mov     r14d, eax
0x180005994  lea     rdx, aForceremove; "ForceRemove"
0x18000599b  mov     rcx, rdi; lpString1
0x18000599e  call    cs:__imp_lstrcmpiW
0x1800059a4  test    eax, eax
0x1800059a6  jz      short loc_1800059B1
0x1800059a8  test    r14d, r14d
0x1800059ab  jnz     loc_180005A62
0x1800059b1  mov     rdx, rdi; unsigned __int16 *
0x1800059b4  mov     rcx, rsi; this
0x1800059b7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800059bc  mov     ebx, eax
0x1800059be  test    eax, eax
0x1800059c0  js      loc_180005E9D
0x1800059c6  test    r15d, r15d
0x1800059c9  jz      loc_180005A62
0x1800059cf  mov     [rsp+2300h+hKey], r12
0x1800059d4  mov     [rsp+2300h+var_22A0], r12
0x1800059d9  mov     [rsp+2300h+var_2298], r12
0x1800059de  mov     edx, 5Ch ; '\'; unsigned __int16
0x1800059e3  mov     rcx, rdi; lpsz
0x1800059e6  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1800059eb  test    rax, rax
0x1800059ee  jnz     loc_180005E8E
0x1800059f4  mov     rdx, rdi; unsigned __int16 *
0x1800059f7  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x1800059fc  test    eax, eax
0x1800059fe  jz      short loc_180005A17
0x180005a00  mov     [rsp+2300h+hKey], r13
0x180005a05  mov     rdx, rdi; unsigned __int16 *
0x180005a08  lea     rcx, [rsp+2300h+hKey]; this
0x180005a0d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180005a12  mov     [rsp+2300h+hKey], r12
0x180005a17  test    r14d, r14d
0x180005a1a  jnz     short loc_180005A58
0x180005a1c  mov     rdx, rdi; unsigned __int16 *
0x180005a1f  mov     rcx, rsi; this
0x180005a22  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005a27  mov     ebx, eax
0x180005a29  xor     r14d, r14d
0x180005a2c  test    eax, eax
0x180005a2e  js      loc_180005ED5
0x180005a34  mov     rdx, rdi; unsigned __int16 *
0x180005a37  mov     rcx, rsi; this
0x180005a3a  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180005a3f  mov     ebx, eax
0x180005a41  test    eax, eax
0x180005a43  lea     rcx, [rsp+2300h+hKey]; this
0x180005a48  js      loc_180005EDA
0x180005a4e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180005a53  jmp     loc_180005C7C
0x180005a58  lea     rcx, [rsp+2300h+hKey]; this
0x180005a5d  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180005a62  mov     r12d, 1
0x180005a68  lea     rdx, aNoremove; "NoRemove"
0x180005a6f  mov     rcx, rdi; lpString1
0x180005a72  call    cs:__imp_lstrcmpiW
0x180005a78  xor     r14d, r14d
0x180005a7b  test    eax, eax
0x180005a7d  jnz     short loc_180005A97
0x180005a7f  mov     r12d, r14d
0x180005a82  mov     rdx, rdi; unsigned __int16 *
0x180005a85  mov     rcx, rsi; this
0x180005a88  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005a8d  mov     ebx, eax
0x180005a8f  test    eax, eax
0x180005a91  js      loc_180005E9D
0x180005a97  lea     rdx, aVal; "Val"
0x180005a9e  mov     rcx, rdi; lpString1
0x180005aa1  call    cs:__imp_lstrcmpiW
0x180005aa7  test    eax, eax
0x180005aa9  jnz     loc_180005B90
0x180005aaf  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x180005ab6  mov     rcx, rsi; this
0x180005ab9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005abe  mov     ebx, eax
0x180005ac0  test    eax, eax
0x180005ac2  js      loc_180005E9D
0x180005ac8  mov     rdx, rdi; unsigned __int16 *
0x180005acb  mov     rcx, rsi; this
0x180005ace  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005ad3  mov     ebx, eax
0x180005ad5  test    eax, eax
0x180005ad7  js      loc_180005E9D
0x180005add  cmp     word ptr [rdi], 3Dh ; '='
0x180005ae1  jnz     loc_180005E98
0x180005ae7  test    r15d, r15d
0x180005aea  jz      short loc_180005B1E
0x180005aec  mov     [rsp+2300h+var_22A0], r14
0x180005af1  mov     [rsp+2300h+var_2298], r14
0x180005af6  mov     [rsp+2300h+hKey], r13
0x180005afb  mov     r9, rdi; unsigned __int16 *
0x180005afe  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x180005b05  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x180005b0a  mov     rcx, rsi; this
0x180005b0d  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180005b12  mov     ebx, eax
0x180005b14  mov     [rsp+2300h+hKey], r14
0x180005b19  jmp     loc_180005A41
0x180005b1e  cmp     [rbp+2200h+arg_20], r14d
0x180005b25  jnz     short loc_180005B80
0x180005b27  test    r12d, r12d
0x180005b2a  jz      short loc_180005B80
0x180005b2c  mov     [rsp+2300h+hKey], r14
0x180005b31  mov     [rsp+2300h+var_22A0], r14
0x180005b36  mov     [rsp+2300h+var_2298], r14
0x180005b3b  mov     r9d, 20006h; unsigned int
0x180005b41  xor     r8d, r8d; lpSubKey
0x180005b44  mov     rdx, r13; hKey
0x180005b47  lea     rcx, [rsp+2300h+hKey]; this
0x180005b4c  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180005b51  test    eax, eax
0x180005b53  jnz     loc_180005ECC
0x180005b59  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x180005b60  mov     rcx, [rsp+2300h+hKey]; hKey
0x180005b65  call    cs:__imp_RegDeleteValueW
0x180005b6b  test    eax, 0FFFFFFFDh
0x180005b70  jnz     loc_180005ECC
0x180005b76  lea     rcx, [rsp+2300h+hKey]; this
0x180005b7b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180005b80  mov     rdx, rdi; unsigned __int16 *
0x180005b83  mov     rcx, rsi; this
0x180005b86  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180005b8b  jmp     loc_18000596A
0x180005b90  mov     edx, 5Ch ; '\'; unsigned __int16
0x180005b95  mov     rcx, rdi; lpsz
0x180005b98  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180005b9d  test    rax, rax
0x180005ba0  jnz     loc_180005E98
0x180005ba6  test    r15d, r15d
0x180005ba9  jz      loc_180005CCB
0x180005baf  mov     ebx, 2001Fh
0x180005bb4  mov     r9d, ebx; unsigned int
0x180005bb7  mov     r8, rdi; lpSubKey
0x180005bba  mov     rdx, r13; hKey
0x180005bbd  lea     rcx, [rsp+2300h+var_2290]; this
0x180005bc2  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180005bc7  test    eax, eax
0x180005bc9  jz      short loc_180005C44
0x180005bcb  lea     r9d, [rbx-6]; unsigned int
0x180005bcf  mov     r8, rdi; lpSubKey
0x180005bd2  mov     rdx, r13; hKey
0x180005bd5  lea     rcx, [rsp+2300h+var_2290]; this
0x180005bda  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180005bdf  test    eax, eax
0x180005be1  jz      short loc_180005C44
0x180005be3  mov     [rbp+2200h+dwDisposition], r14d
0x180005be7  mov     [rbp+2200h+var_2270], r14
0x180005beb  lea     rax, [rbp+2200h+dwDisposition]
0x180005bef  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x180005bf4  lea     rax, [rbp+2200h+var_2270]
0x180005bf8  mov     [rsp+2300h+phkResult], rax; phkResult
0x180005bfd  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180005c02  mov     [rsp+2300h+samDesired], ebx; samDesired
0x180005c06  mov     dword ptr [rsp+2300h+dwOptions], r14d; dwOptions
0x180005c0b  xor     r9d, r9d; lpClass
0x180005c0e  xor     r8d, r8d; Reserved
0x180005c11  mov     rdx, rdi; lpSubKey
0x180005c14  mov     rcx, r13; hKey
0x180005c17  call    cs:__imp_RegCreateKeyExW
0x180005c1d  mov     ecx, eax
0x180005c1f  test    eax, eax
0x180005c21  jnz     loc_180005DCB
0x180005c27  lea     rcx, [rsp+2300h+var_2290]; this
0x180005c2c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180005c31  mov     ecx, eax
0x180005c33  mov     rax, [rbp+2200h+var_2270]
0x180005c37  mov     [rsp+2300h+var_2290], rax
0x180005c3c  test    ecx, ecx
0x180005c3e  jnz     loc_180005DCB
0x180005c44  mov     rdx, rdi; unsigned __int16 *
0x180005c47  mov     rcx, rsi; this
0x180005c4a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005c4f  mov     ebx, eax
0x180005c51  test    eax, eax
0x180005c53  js      loc_180005E9D
0x180005c59  cmp     word ptr [rdi], 3Dh ; '='
0x180005c5d  jnz     short loc_180005C7C
0x180005c5f  mov     r9, rdi; unsigned __int16 *
0x180005c62  xor     r8d, r8d; unsigned __int16 *
0x180005c65  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x180005c6a  mov     rcx, rsi; this
0x180005c6d  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180005c72  mov     ebx, eax
0x180005c74  test    eax, eax
0x180005c76  js      loc_180005E9D
0x180005c7c  cmp     word ptr [rdi], 7Bh ; '{'
0x180005c80  jnz     loc_180005974
0x180005c86  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005c8a  inc     rax
0x180005c8d  cmp     [rdi+rax*2], r14w
0x180005c92  jnz     short loc_180005C8A
0x180005c94  cmp     rax, 1
0x180005c98  jnz     loc_180005974
0x180005c9e  mov     dword ptr [rsp+2300h+dwOptions], r14d; int
0x180005ca3  mov     r9d, r15d; int
0x180005ca6  mov     r8, [rsp+2300h+var_2290]; HKEY
0x180005cab  mov     rdx, rdi; unsigned __int16 *
0x180005cae  mov     rcx, rsi; this
0x180005cb1  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180005cb6  mov     ebx, eax
0x180005cb8  test    eax, eax
0x180005cba  js      loc_180005E9D
0x180005cc0  mov     rdx, rdi
0x180005cc3  mov     rcx, rsi
0x180005cc6  jmp     loc_180005965
0x180005ccb  cmp     [rbp+2200h+arg_20], r14d
0x180005cd2  jnz     short loc_180005CEF
0x180005cd4  mov     r9d, 20019h; unsigned int
0x180005cda  mov     r8, rdi; lpSubKey
0x180005cdd  mov     rdx, r13; hKey
0x180005ce0  lea     rcx, [rsp+2300h+var_2290]; this
0x180005ce5  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180005cea  mov     r14d, eax
0x180005ced  jmp     short loc_180005CF5
0x180005cef  mov     r14d, 2
0x180005cf5  mov     r15d, 1
0x180005cfb  test    r14d, r14d
0x180005cfe  cmovz   r15d, [rbp+2200h+arg_20]
0x180005d06  or      r9, 0FFFFFFFFFFFFFFFFh
0x180005d0a  mov     r8, rdi
0x180005d0d  mov     edx, 104h
0x180005d12  lea     rcx, [rbp+2200h+var_2260]
0x180005d16  call    cs:__imp__o_wcsncpy_s
0x180005d1c  mov     ecx, eax; int
0x180005d1e  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180005d23  mov     rdx, rdi; unsigned __int16 *
0x180005d26  mov     rcx, rsi; this
0x180005d29  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005d2e  mov     ebx, eax
0x180005d30  test    eax, eax
0x180005d32  js      loc_180005E9D
0x180005d38  mov     rdx, rdi; unsigned __int16 *
0x180005d3b  mov     rcx, rsi; this
0x180005d3e  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180005d43  mov     ebx, eax
0x180005d45  xor     ecx, ecx
0x180005d47  test    eax, eax
0x180005d49  js      loc_180005E9D
0x180005d4f  cmp     word ptr [rdi], 7Bh ; '{'
0x180005d53  jnz     short loc_180005DA4
0x180005d55  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005d59  inc     rax
0x180005d5c  cmp     [rdi+rax*2], cx
0x180005d60  jnz     short loc_180005D59
0x180005d62  cmp     rax, 1
0x180005d66  jnz     short loc_180005DA4
0x180005d68  mov     dword ptr [rsp+2300h+dwOptions], r15d; int
0x180005d6d  xor     r9d, r9d; int
0x180005d70  mov     r8, [rsp+2300h+var_2290]; HKEY
0x180005d75  mov     rdx, rdi; unsigned __int16 *
0x180005d78  mov     rcx, rsi; this
0x180005d7b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180005d80  mov     ebx, eax
0x180005d82  test    eax, eax
0x180005d84  jns     short loc_180005D8F
0x180005d86  test    r15d, r15d
0x180005d89  jz      loc_180005E9D
0x180005d8f  mov     rdx, rdi; unsigned __int16 *
0x180005d92  mov     rcx, rsi; this
0x180005d95  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005d9a  mov     ebx, eax
0x180005d9c  test    eax, eax
0x180005d9e  js      loc_180005E9D
0x180005da4  cmp     r14d, 2
0x180005da8  mov     r15d, [rsp+2300h+var_22B0]
  ... truncated ...
```
