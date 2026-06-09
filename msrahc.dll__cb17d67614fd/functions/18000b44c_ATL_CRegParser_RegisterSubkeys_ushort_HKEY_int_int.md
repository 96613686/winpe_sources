# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18000b44c`
- end: `0x18000ba25`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1497`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x18000b05c`
- `0x18000b44c`

## callees

- `0x180008efc`
- `0x1800096a8`
- `0x180009718`
- `0x180009f54`
- `0x18000a064`
- `0x18000a394`
- `0x18000a88c`
- `0x18000aaa0`
- `0x18000ac00`
- `0x18000af48`
- `0x18000b44c`
- `0x18000bbbc`
- `0x18000bc8c`
- `0x18001a5e0`
- `0x18001a6a0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18000b852`
- `msvcrt!wcsncpy_s` at `0x18000b852`
- `ADVAPI32!RegDeleteValueW` at `0x18000b6a1`
- `ADVAPI32!RegDeleteValueW` at `0x18000b6a1`
- `ADVAPI32!RegCreateKeyExW` at `0x18000b753`
- `ADVAPI32!RegCreateKeyExW` at `0x18000b753`
- `KERNEL32!lstrcmpiW` at `0x18000b4c7`
- `KERNEL32!lstrcmpiW` at `0x18000b4da`
- `KERNEL32!lstrcmpiW` at `0x18000b5ae`
- `KERNEL32!lstrcmpiW` at `0x18000b5dd`
- `KERNEL32!lstrcmpiW` at `0x18000b4c7`
- `KERNEL32!lstrcmpiW` at `0x18000b4da`
- `KERNEL32!lstrcmpiW` at `0x18000b5ae`
- `KERNEL32!lstrcmpiW` at `0x18000b5dd`

## string_xrefs

- `0x18000b4d0`: `ForceRemove`
- `0x18000b5a4`: `NoRemove`
- `0x18000b4bd`: `Delete`

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
  ATL::CRegParser *v8; // rsi
  int Token; // eax
  int v10; // ebx
  int v11; // r14d
  ATL::CRegParser *v12; // rcx
  int v13; // eax
  int v14; // r12d
  unsigned int v15; // eax
  LSTATUS v16; // ecx
  __int64 v17; // rax
  int v18; // r14d
  int v19; // r15d
  errno_t v20; // eax
  ATL::CRegParser *v21; // rcx
  __int64 v22; // rax
  int HasSubKeys; // r14d
  LSTATUS v24; // eax
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v28; // [rsp+60h] [rbp-A0h]
  __int64 v29; // [rsp+68h] [rbp-98h]
  HKEY v30[3]; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  wchar_t Destination[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ValueName[4096]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v5 = a4;
  v7 = a2;
  v8 = this;
  memset(v30, 0, sizeof(v30));
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
          v28 = 0;
          v29 = 0;
          if ( ATL::CRegParser::StrChrW(v7, 0x5Cu) )
          {
            ATL::CRegKey::Close(&hKey);
LABEL_78:
            v10 = -2147352567;
            goto LABEL_79;
          }
          if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v12, v7) )
          {
            hKey = a3;
            ATL::CRegKey::RecurseDeleteKey(&hKey, v7);
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
          ATL::CRegKey::Close(&hKey);
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
        if ( (unsigned int)ATL::CRegKey::Open(v30, a3, v7, 0x2001Fu) )
        {
          if ( (unsigned int)ATL::CRegKey::Open(v30, a3, v7, 0x20019u) )
          {
            dwDisposition = 0;
            phkResult = 0;
            v16 = RegCreateKeyExW(a3, v7, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
            if ( v16 )
              goto LABEL_65;
            v16 = ATL::CRegKey::Close(v30);
            v30[0] = phkResult;
            if ( v16 )
              goto LABEL_65;
          }
        }
        v10 = ATL::CRegParser::NextToken(v8, v7);
        if ( v10 < 0 )
          goto LABEL_79;
        if ( *v7 == 61 )
        {
          v10 = ATL::CRegParser::AddValue(v8, v30, 0, v7);
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
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v30[0], v5, 0);
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
          v18 = ATL::CRegKey::Open(v30, a3, v7, 0x20019u);
        v19 = 1;
        if ( !v18 )
          v19 = a5;
        v20 = wcsncpy_s(Destination, 0x104u, v7, 0xFFFFFFFFFFFFFFFFuLL);
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
            v10 = ATL::CRegParser::RegisterSubkeys(v8, v7, v30[0], 0, v19);
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
          else if ( a5 && ATL::CRegParser::HasSubKeys(v21, v30[0]) )
          {
            if ( (unsigned int)ATL::CRegParser::CanForceRemoveKey(v21, Destination) && v14 )
              ATL::CRegKey::RecurseDeleteKey(v30, Destination);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v21, v30[0]);
            v24 = ATL::CRegKey::Close(v30);
            if ( v24 )
            {
              v16 = v24;
              goto LABEL_65;
            }
            if ( v14 && !HasSubKeys )
            {
              v28 = 0;
              v29 = 0;
              hKey = a3;
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, Destination);
              hKey = 0;
              if ( v15 )
                goto LABEL_80;
              ATL::CRegKey::Close(&hKey);
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
      v28 = 0;
      v29 = 0;
      hKey = a3;
      v13 = ATL::CRegParser::AddValue(v8, &hKey, ValueName, v7);
      v10 = v13;
      hKey = 0;
LABEL_15:
      if ( v13 < 0 )
        goto LABEL_81;
      ATL::CRegKey::Close(&hKey);
      goto LABEL_41;
    }
    if ( a5 || !v14 )
      goto LABEL_31;
    hKey = 0;
    v28 = 0;
    v29 = 0;
    v15 = ATL::CRegKey::Open(&hKey, a3, 0, 0x20006u);
    if ( !v15 )
    {
      v15 = RegDeleteValueW(hKey, ValueName);
      if ( (v15 & 0xFFFFFFFD) == 0 )
      {
        ATL::CRegKey::Close(&hKey);
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
  ATL::CRegKey::Close(&hKey);
LABEL_79:
  ATL::CRegKey::Close(v30);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000b44c  push    rbp
0x18000b44e  push    rbx
0x18000b44f  push    rsi
0x18000b450  push    rdi
0x18000b451  push    r12
0x18000b453  push    r13
0x18000b455  push    r14
0x18000b457  push    r15
0x18000b459  lea     rbp, [rsp-21C8h]
0x18000b461  mov     eax, 22C8h
0x18000b466  call    _alloca_probe
0x18000b46b  sub     rsp, rax
0x18000b46e  mov     rax, cs:__security_cookie
0x18000b475  xor     rax, rsp
0x18000b478  mov     [rbp+2200h+var_50], rax
0x18000b47f  mov     r15d, r9d
0x18000b482  mov     [rsp+2300h+var_22B0], r9d
0x18000b487  mov     r13, r8
0x18000b48a  mov     rdi, rdx
0x18000b48d  mov     rsi, rcx
0x18000b490  xor     r14d, r14d
0x18000b493  mov     [rsp+2300h+var_2290], r14
0x18000b498  mov     [rsp+2300h+var_2288], r14
0x18000b49d  mov     [rbp+2200h+var_2280], r14
0x18000b4a1  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000b4a6  test    eax, eax
0x18000b4a8  mov     ebx, eax
0x18000b4aa  js      loc_18000B9D9
0x18000b4b0  xor     r12d, r12d
0x18000b4b3  cmp     word ptr [rdi], 7Dh ; '}'
0x18000b4b7  jz      loc_18000B9D9
0x18000b4bd  lea     rdx, String2; "Delete"
0x18000b4c4  mov     rcx, rdi; lpString1
0x18000b4c7  call    cs:__imp_lstrcmpiW
0x18000b4cd  mov     r14d, eax
0x18000b4d0  lea     rdx, aForceremove; "ForceRemove"
0x18000b4d7  mov     rcx, rdi; lpString1
0x18000b4da  call    cs:__imp_lstrcmpiW
0x18000b4e0  test    eax, eax
0x18000b4e2  jz      short loc_18000B4ED
0x18000b4e4  test    r14d, r14d
0x18000b4e7  jnz     loc_18000B59E
0x18000b4ed  mov     rdx, rdi; unsigned __int16 *
0x18000b4f0  mov     rcx, rsi; this
0x18000b4f3  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000b4f8  mov     ebx, eax
0x18000b4fa  test    eax, eax
0x18000b4fc  js      loc_18000B9D9
0x18000b502  test    r15d, r15d
0x18000b505  jz      loc_18000B59E
0x18000b50b  mov     [rsp+2300h+hKey], r12
0x18000b510  mov     [rsp+2300h+var_22A0], r12
0x18000b515  mov     [rsp+2300h+var_2298], r12
0x18000b51a  mov     edx, 5Ch ; '\'; unsigned __int16
0x18000b51f  mov     rcx, rdi; lpsz
0x18000b522  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18000b527  test    rax, rax
0x18000b52a  jnz     loc_18000B9CA
0x18000b530  mov     rdx, rdi; unsigned __int16 *
0x18000b533  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x18000b538  test    eax, eax
0x18000b53a  jz      short loc_18000B553
0x18000b53c  mov     [rsp+2300h+hKey], r13
0x18000b541  mov     rdx, rdi; unsigned __int16 *
0x18000b544  lea     rcx, [rsp+2300h+hKey]; this
0x18000b549  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000b54e  mov     [rsp+2300h+hKey], r12
0x18000b553  test    r14d, r14d
0x18000b556  jnz     short loc_18000B594
0x18000b558  mov     rdx, rdi; unsigned __int16 *
0x18000b55b  mov     rcx, rsi; this
0x18000b55e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000b563  mov     ebx, eax
0x18000b565  xor     r14d, r14d
0x18000b568  test    eax, eax
0x18000b56a  js      loc_18000BA11
0x18000b570  mov     rdx, rdi; unsigned __int16 *
0x18000b573  mov     rcx, rsi; this
0x18000b576  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000b57b  mov     ebx, eax
0x18000b57d  test    eax, eax
0x18000b57f  lea     rcx, [rsp+2300h+hKey]; this
0x18000b584  js      loc_18000BA16
0x18000b58a  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000b58f  jmp     loc_18000B7B8
0x18000b594  lea     rcx, [rsp+2300h+hKey]; this
0x18000b599  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000b59e  mov     r12d, 1
0x18000b5a4  lea     rdx, aNoremove; "NoRemove"
0x18000b5ab  mov     rcx, rdi; lpString1
0x18000b5ae  call    cs:__imp_lstrcmpiW
0x18000b5b4  xor     r14d, r14d
0x18000b5b7  test    eax, eax
0x18000b5b9  jnz     short loc_18000B5D3
0x18000b5bb  mov     r12d, r14d
0x18000b5be  mov     rdx, rdi; unsigned __int16 *
0x18000b5c1  mov     rcx, rsi; this
0x18000b5c4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000b5c9  mov     ebx, eax
0x18000b5cb  test    eax, eax
0x18000b5cd  js      loc_18000B9D9
0x18000b5d3  lea     rdx, aVal; "Val"
0x18000b5da  mov     rcx, rdi; lpString1
0x18000b5dd  call    cs:__imp_lstrcmpiW
0x18000b5e3  test    eax, eax
0x18000b5e5  jnz     loc_18000B6CC
0x18000b5eb  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x18000b5f2  mov     rcx, rsi; this
0x18000b5f5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000b5fa  mov     ebx, eax
0x18000b5fc  test    eax, eax
0x18000b5fe  js      loc_18000B9D9
0x18000b604  mov     rdx, rdi; unsigned __int16 *
0x18000b607  mov     rcx, rsi; this
0x18000b60a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000b60f  mov     ebx, eax
0x18000b611  test    eax, eax
0x18000b613  js      loc_18000B9D9
0x18000b619  cmp     word ptr [rdi], 3Dh ; '='
0x18000b61d  jnz     loc_18000B9D4
0x18000b623  test    r15d, r15d
0x18000b626  jz      short loc_18000B65A
0x18000b628  mov     [rsp+2300h+var_22A0], r14
0x18000b62d  mov     [rsp+2300h+var_2298], r14
0x18000b632  mov     [rsp+2300h+hKey], r13
0x18000b637  mov     r9, rdi; unsigned __int16 *
0x18000b63a  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x18000b641  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x18000b646  mov     rcx, rsi; this
0x18000b649  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18000b64e  mov     ebx, eax
0x18000b650  mov     [rsp+2300h+hKey], r14
0x18000b655  jmp     loc_18000B57D
0x18000b65a  cmp     [rbp+2200h+arg_20], r14d
0x18000b661  jnz     short loc_18000B6BC
0x18000b663  test    r12d, r12d
0x18000b666  jz      short loc_18000B6BC
0x18000b668  mov     [rsp+2300h+hKey], r14
0x18000b66d  mov     [rsp+2300h+var_22A0], r14
0x18000b672  mov     [rsp+2300h+var_2298], r14
0x18000b677  mov     r9d, 20006h; unsigned int
0x18000b67d  xor     r8d, r8d; lpSubKey
0x18000b680  mov     rdx, r13; hKey
0x18000b683  lea     rcx, [rsp+2300h+hKey]; this
0x18000b688  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000b68d  test    eax, eax
0x18000b68f  jnz     loc_18000BA08
0x18000b695  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x18000b69c  mov     rcx, [rsp+2300h+hKey]; hKey
0x18000b6a1  call    cs:__imp_RegDeleteValueW
0x18000b6a7  test    eax, 0FFFFFFFDh
0x18000b6ac  jnz     loc_18000BA08
0x18000b6b2  lea     rcx, [rsp+2300h+hKey]; this
0x18000b6b7  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000b6bc  mov     rdx, rdi; unsigned __int16 *
0x18000b6bf  mov     rcx, rsi; this
0x18000b6c2  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000b6c7  jmp     loc_18000B4A6
0x18000b6cc  mov     edx, 5Ch ; '\'; unsigned __int16
0x18000b6d1  mov     rcx, rdi; lpsz
0x18000b6d4  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18000b6d9  test    rax, rax
0x18000b6dc  jnz     loc_18000B9D4
0x18000b6e2  test    r15d, r15d
0x18000b6e5  jz      loc_18000B807
0x18000b6eb  mov     ebx, 2001Fh
0x18000b6f0  mov     r9d, ebx; unsigned int
0x18000b6f3  mov     r8, rdi; lpSubKey
0x18000b6f6  mov     rdx, r13; hKey
0x18000b6f9  lea     rcx, [rsp+2300h+var_2290]; this
0x18000b6fe  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000b703  test    eax, eax
0x18000b705  jz      short loc_18000B780
0x18000b707  lea     r9d, [rbx-6]; unsigned int
0x18000b70b  mov     r8, rdi; lpSubKey
0x18000b70e  mov     rdx, r13; hKey
0x18000b711  lea     rcx, [rsp+2300h+var_2290]; this
0x18000b716  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000b71b  test    eax, eax
0x18000b71d  jz      short loc_18000B780
0x18000b71f  mov     [rbp+2200h+dwDisposition], r14d
0x18000b723  mov     [rbp+2200h+var_2270], r14
0x18000b727  lea     rax, [rbp+2200h+dwDisposition]
0x18000b72b  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x18000b730  lea     rax, [rbp+2200h+var_2270]
0x18000b734  mov     [rsp+2300h+phkResult], rax; phkResult
0x18000b739  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18000b73e  mov     [rsp+2300h+samDesired], ebx; samDesired
0x18000b742  mov     [rsp+2300h+dwOptions], r14d; dwOptions
0x18000b747  xor     r9d, r9d; lpClass
0x18000b74a  xor     r8d, r8d; Reserved
0x18000b74d  mov     rdx, rdi; lpSubKey
0x18000b750  mov     rcx, r13; hKey
0x18000b753  call    cs:__imp_RegCreateKeyExW
0x18000b759  mov     ecx, eax
0x18000b75b  test    eax, eax
0x18000b75d  jnz     loc_18000B907
0x18000b763  lea     rcx, [rsp+2300h+var_2290]; this
0x18000b768  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000b76d  mov     ecx, eax
0x18000b76f  mov     rax, [rbp+2200h+var_2270]
0x18000b773  mov     [rsp+2300h+var_2290], rax
0x18000b778  test    ecx, ecx
0x18000b77a  jnz     loc_18000B907
0x18000b780  mov     rdx, rdi; unsigned __int16 *
0x18000b783  mov     rcx, rsi; this
0x18000b786  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000b78b  mov     ebx, eax
0x18000b78d  test    eax, eax
0x18000b78f  js      loc_18000B9D9
0x18000b795  cmp     word ptr [rdi], 3Dh ; '='
0x18000b799  jnz     short loc_18000B7B8
0x18000b79b  mov     r9, rdi; unsigned __int16 *
0x18000b79e  xor     r8d, r8d; unsigned __int16 *
0x18000b7a1  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x18000b7a6  mov     rcx, rsi; this
0x18000b7a9  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18000b7ae  mov     ebx, eax
0x18000b7b0  test    eax, eax
0x18000b7b2  js      loc_18000B9D9
0x18000b7b8  cmp     word ptr [rdi], 7Bh ; '{'
0x18000b7bc  jnz     loc_18000B4B0
0x18000b7c2  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b7c6  inc     rax
0x18000b7c9  cmp     [rdi+rax*2], r14w
0x18000b7ce  jnz     short loc_18000B7C6
0x18000b7d0  cmp     rax, 1
0x18000b7d4  jnz     loc_18000B4B0
0x18000b7da  mov     [rsp+2300h+dwOptions], r14d; int
0x18000b7df  mov     r9d, r15d; int
0x18000b7e2  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18000b7e7  mov     rdx, rdi; unsigned __int16 *
0x18000b7ea  mov     rcx, rsi; this
0x18000b7ed  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000b7f2  mov     ebx, eax
0x18000b7f4  test    eax, eax
0x18000b7f6  js      loc_18000B9D9
0x18000b7fc  mov     rdx, rdi
0x18000b7ff  mov     rcx, rsi
0x18000b802  jmp     loc_18000B4A1
0x18000b807  cmp     [rbp+2200h+arg_20], r14d
0x18000b80e  jnz     short loc_18000B82B
0x18000b810  mov     r9d, 20019h; unsigned int
0x18000b816  mov     r8, rdi; lpSubKey
0x18000b819  mov     rdx, r13; hKey
0x18000b81c  lea     rcx, [rsp+2300h+var_2290]; this
0x18000b821  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000b826  mov     r14d, eax
0x18000b829  jmp     short loc_18000B831
0x18000b82b  mov     r14d, 2
0x18000b831  mov     r15d, 1
0x18000b837  test    r14d, r14d
0x18000b83a  cmovz   r15d, [rbp+2200h+arg_20]
0x18000b842  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18000b846  mov     r8, rdi; Source
0x18000b849  mov     edx, 104h; SizeInWords
0x18000b84e  lea     rcx, [rbp+2200h+Destination]; Destination
0x18000b852  call    cs:__imp_wcsncpy_s
0x18000b858  mov     ecx, eax; int
0x18000b85a  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000b85f  mov     rdx, rdi; unsigned __int16 *
0x18000b862  mov     rcx, rsi; this
0x18000b865  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000b86a  mov     ebx, eax
0x18000b86c  test    eax, eax
0x18000b86e  js      loc_18000B9D9
0x18000b874  mov     rdx, rdi; unsigned __int16 *
0x18000b877  mov     rcx, rsi; this
0x18000b87a  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000b87f  mov     ebx, eax
0x18000b881  xor     ecx, ecx
0x18000b883  test    eax, eax
0x18000b885  js      loc_18000B9D9
0x18000b88b  cmp     word ptr [rdi], 7Bh ; '{'
0x18000b88f  jnz     short loc_18000B8E0
0x18000b891  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b895  inc     rax
0x18000b898  cmp     [rdi+rax*2], cx
0x18000b89c  jnz     short loc_18000B895
0x18000b89e  cmp     rax, 1
0x18000b8a2  jnz     short loc_18000B8E0
0x18000b8a4  mov     [rsp+2300h+dwOptions], r15d; int
0x18000b8a9  xor     r9d, r9d; int
0x18000b8ac  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18000b8b1  mov     rdx, rdi; unsigned __int16 *
0x18000b8b4  mov     rcx, rsi; this
0x18000b8b7  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000b8bc  mov     ebx, eax
0x18000b8be  test    eax, eax
0x18000b8c0  jns     short loc_18000B8CB
0x18000b8c2  test    r15d, r15d
0x18000b8c5  jz      loc_18000B9D9
0x18000b8cb  mov     rdx, rdi; unsigned __int16 *
0x18000b8ce  mov     rcx, rsi; this
0x18000b8d1  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000b8d6  mov     ebx, eax
0x18000b8d8  test    eax, eax
0x18000b8da  js      loc_18000B9D9
0x18000b8e0  cmp     r14d, 2
0x18000b8e4  mov     r15d, [rsp+2300h+var_22B0]
  ... truncated ...
```
