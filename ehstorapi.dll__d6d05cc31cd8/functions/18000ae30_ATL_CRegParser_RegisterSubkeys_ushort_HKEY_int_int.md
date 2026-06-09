# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x18000ae30`
- end: `0x18000b409`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1497`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x18000ab0c`
- `0x18000ae30`

## callees

- `0x180002210`
- `0x18000919c`
- `0x18000996c`
- `0x180009984`
- `0x180009a94`
- `0x18000a0ec`
- `0x18000a3f8`
- `0x18000a570`
- `0x18000a6d0`
- `0x18000a9f8`
- `0x18000ae30`
- `0x18000b524`
- `0x18000b5f4`
- `0x18000c4f0`
- `0x18000c5b0`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18000b236`
- `msvcrt!wcsncpy_s` at `0x18000b236`
- `ADVAPI32!RegDeleteValueW` at `0x18000b085`
- `ADVAPI32!RegDeleteValueW` at `0x18000b085`
- `ADVAPI32!RegCreateKeyExW` at `0x18000b137`
- `ADVAPI32!RegCreateKeyExW` at `0x18000b137`
- `KERNEL32!lstrcmpiW` at `0x18000aeab`
- `KERNEL32!lstrcmpiW` at `0x18000aebe`
- `KERNEL32!lstrcmpiW` at `0x18000af92`
- `KERNEL32!lstrcmpiW` at `0x18000afc1`
- `KERNEL32!lstrcmpiW` at `0x18000aeab`
- `KERNEL32!lstrcmpiW` at `0x18000aebe`
- `KERNEL32!lstrcmpiW` at `0x18000af92`
- `KERNEL32!lstrcmpiW` at `0x18000afc1`

## string_xrefs

- `0x18000aeb4`: `ForceRemove`
- `0x18000af88`: `NoRemove`
- `0x18000aea1`: `Delete`

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
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x2001Fu) )
        {
          if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x20019u) )
          {
            dwDisposition = 0;
            phkResult = 0;
            v16 = RegCreateKeyExW(a3, v7, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
            if ( v16 )
              goto LABEL_65;
            v16 = ATL::CRegKey::Close((ATL::CRegKey *)v30);
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
          v18 = ATL::CRegKey::Open((ATL::CRegKey *)v30, a3, v7, 0x20019u);
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
            if ( ATL::CRegParser::CanForceRemoveKey(v21, Destination) && v14 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v30, Destination);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v21, v30[0]);
            v24 = ATL::CRegKey::Close((ATL::CRegKey *)v30);
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
      v28 = 0;
      v29 = 0;
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
    v28 = 0;
    v29 = 0;
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
  ATL::CRegKey::Close((ATL::CRegKey *)v30);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000ae30  push    rbp
0x18000ae32  push    rbx
0x18000ae33  push    rsi
0x18000ae34  push    rdi
0x18000ae35  push    r12
0x18000ae37  push    r13
0x18000ae39  push    r14
0x18000ae3b  push    r15
0x18000ae3d  lea     rbp, [rsp-21C8h]
0x18000ae45  mov     eax, 22C8h
0x18000ae4a  call    _alloca_probe
0x18000ae4f  sub     rsp, rax
0x18000ae52  mov     rax, cs:__security_cookie
0x18000ae59  xor     rax, rsp
0x18000ae5c  mov     [rbp+2200h+var_50], rax
0x18000ae63  mov     r15d, r9d
0x18000ae66  mov     [rsp+2300h+var_22B0], r9d
0x18000ae6b  mov     r13, r8
0x18000ae6e  mov     rdi, rdx
0x18000ae71  mov     rsi, rcx
0x18000ae74  xor     r14d, r14d
0x18000ae77  mov     [rsp+2300h+var_2290], r14
0x18000ae7c  mov     [rsp+2300h+var_2288], r14
0x18000ae81  mov     [rbp+2200h+var_2280], r14
0x18000ae85  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000ae8a  test    eax, eax
0x18000ae8c  mov     ebx, eax
0x18000ae8e  js      loc_18000B3BD
0x18000ae94  xor     r12d, r12d
0x18000ae97  cmp     word ptr [rdi], 7Dh ; '}'
0x18000ae9b  jz      loc_18000B3BD
0x18000aea1  lea     rdx, aDelete; "Delete"
0x18000aea8  mov     rcx, rdi; lpString1
0x18000aeab  call    cs:__imp_lstrcmpiW
0x18000aeb1  mov     r14d, eax
0x18000aeb4  lea     rdx, aForceremove; "ForceRemove"
0x18000aebb  mov     rcx, rdi; lpString1
0x18000aebe  call    cs:__imp_lstrcmpiW
0x18000aec4  test    eax, eax
0x18000aec6  jz      short loc_18000AED1
0x18000aec8  test    r14d, r14d
0x18000aecb  jnz     loc_18000AF82
0x18000aed1  mov     rdx, rdi; unsigned __int16 *
0x18000aed4  mov     rcx, rsi; this
0x18000aed7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000aedc  mov     ebx, eax
0x18000aede  test    eax, eax
0x18000aee0  js      loc_18000B3BD
0x18000aee6  test    r15d, r15d
0x18000aee9  jz      loc_18000AF82
0x18000aeef  mov     [rsp+2300h+hKey], r12
0x18000aef4  mov     [rsp+2300h+var_22A0], r12
0x18000aef9  mov     [rsp+2300h+var_2298], r12
0x18000aefe  mov     edx, 5Ch ; '\'; unsigned __int16
0x18000af03  mov     rcx, rdi; lpsz
0x18000af06  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18000af0b  test    rax, rax
0x18000af0e  jnz     loc_18000B3AE
0x18000af14  mov     rdx, rdi; unsigned __int16 *
0x18000af17  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x18000af1c  test    eax, eax
0x18000af1e  jz      short loc_18000AF37
0x18000af20  mov     [rsp+2300h+hKey], r13
0x18000af25  mov     rdx, rdi; unsigned __int16 *
0x18000af28  lea     rcx, [rsp+2300h+hKey]; this
0x18000af2d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x18000af32  mov     [rsp+2300h+hKey], r12
0x18000af37  test    r14d, r14d
0x18000af3a  jnz     short loc_18000AF78
0x18000af3c  mov     rdx, rdi; unsigned __int16 *
0x18000af3f  mov     rcx, rsi; this
0x18000af42  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000af47  mov     ebx, eax
0x18000af49  xor     r14d, r14d
0x18000af4c  test    eax, eax
0x18000af4e  js      loc_18000B3F5
0x18000af54  mov     rdx, rdi; unsigned __int16 *
0x18000af57  mov     rcx, rsi; this
0x18000af5a  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000af5f  mov     ebx, eax
0x18000af61  test    eax, eax
0x18000af63  lea     rcx, [rsp+2300h+hKey]; this
0x18000af68  js      loc_18000B3FA
0x18000af6e  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000af73  jmp     loc_18000B19C
0x18000af78  lea     rcx, [rsp+2300h+hKey]; this
0x18000af7d  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000af82  mov     r12d, 1
0x18000af88  lea     rdx, aNoremove; "NoRemove"
0x18000af8f  mov     rcx, rdi; lpString1
0x18000af92  call    cs:__imp_lstrcmpiW
0x18000af98  xor     r14d, r14d
0x18000af9b  test    eax, eax
0x18000af9d  jnz     short loc_18000AFB7
0x18000af9f  mov     r12d, r14d
0x18000afa2  mov     rdx, rdi; unsigned __int16 *
0x18000afa5  mov     rcx, rsi; this
0x18000afa8  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000afad  mov     ebx, eax
0x18000afaf  test    eax, eax
0x18000afb1  js      loc_18000B3BD
0x18000afb7  lea     rdx, aVal; "Val"
0x18000afbe  mov     rcx, rdi; lpString1
0x18000afc1  call    cs:__imp_lstrcmpiW
0x18000afc7  test    eax, eax
0x18000afc9  jnz     loc_18000B0B0
0x18000afcf  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x18000afd6  mov     rcx, rsi; this
0x18000afd9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000afde  mov     ebx, eax
0x18000afe0  test    eax, eax
0x18000afe2  js      loc_18000B3BD
0x18000afe8  mov     rdx, rdi; unsigned __int16 *
0x18000afeb  mov     rcx, rsi; this
0x18000afee  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000aff3  mov     ebx, eax
0x18000aff5  test    eax, eax
0x18000aff7  js      loc_18000B3BD
0x18000affd  cmp     word ptr [rdi], 3Dh ; '='
0x18000b001  jnz     loc_18000B3B8
0x18000b007  test    r15d, r15d
0x18000b00a  jz      short loc_18000B03E
0x18000b00c  mov     [rsp+2300h+var_22A0], r14
0x18000b011  mov     [rsp+2300h+var_2298], r14
0x18000b016  mov     [rsp+2300h+hKey], r13
0x18000b01b  mov     r9, rdi; unsigned __int16 *
0x18000b01e  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x18000b025  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x18000b02a  mov     rcx, rsi; this
0x18000b02d  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18000b032  mov     ebx, eax
0x18000b034  mov     [rsp+2300h+hKey], r14
0x18000b039  jmp     loc_18000AF61
0x18000b03e  cmp     [rbp+2200h+arg_20], r14d
0x18000b045  jnz     short loc_18000B0A0
0x18000b047  test    r12d, r12d
0x18000b04a  jz      short loc_18000B0A0
0x18000b04c  mov     [rsp+2300h+hKey], r14
0x18000b051  mov     [rsp+2300h+var_22A0], r14
0x18000b056  mov     [rsp+2300h+var_2298], r14
0x18000b05b  mov     r9d, 20006h; unsigned int
0x18000b061  xor     r8d, r8d; lpSubKey
0x18000b064  mov     rdx, r13; hKey
0x18000b067  lea     rcx, [rsp+2300h+hKey]; this
0x18000b06c  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000b071  test    eax, eax
0x18000b073  jnz     loc_18000B3EC
0x18000b079  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x18000b080  mov     rcx, [rsp+2300h+hKey]; hKey
0x18000b085  call    cs:__imp_RegDeleteValueW
0x18000b08b  test    eax, 0FFFFFFFDh
0x18000b090  jnz     loc_18000B3EC
0x18000b096  lea     rcx, [rsp+2300h+hKey]; this
0x18000b09b  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000b0a0  mov     rdx, rdi; unsigned __int16 *
0x18000b0a3  mov     rcx, rsi; this
0x18000b0a6  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000b0ab  jmp     loc_18000AE8A
0x18000b0b0  mov     edx, 5Ch ; '\'; unsigned __int16
0x18000b0b5  mov     rcx, rdi; lpsz
0x18000b0b8  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18000b0bd  test    rax, rax
0x18000b0c0  jnz     loc_18000B3B8
0x18000b0c6  test    r15d, r15d
0x18000b0c9  jz      loc_18000B1EB
0x18000b0cf  mov     ebx, 2001Fh
0x18000b0d4  mov     r9d, ebx; unsigned int
0x18000b0d7  mov     r8, rdi; lpSubKey
0x18000b0da  mov     rdx, r13; hKey
0x18000b0dd  lea     rcx, [rsp+2300h+var_2290]; this
0x18000b0e2  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000b0e7  test    eax, eax
0x18000b0e9  jz      short loc_18000B164
0x18000b0eb  lea     r9d, [rbx-6]; unsigned int
0x18000b0ef  mov     r8, rdi; lpSubKey
0x18000b0f2  mov     rdx, r13; hKey
0x18000b0f5  lea     rcx, [rsp+2300h+var_2290]; this
0x18000b0fa  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000b0ff  test    eax, eax
0x18000b101  jz      short loc_18000B164
0x18000b103  mov     [rbp+2200h+dwDisposition], r14d
0x18000b107  mov     [rbp+2200h+var_2270], r14
0x18000b10b  lea     rax, [rbp+2200h+dwDisposition]
0x18000b10f  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x18000b114  lea     rax, [rbp+2200h+var_2270]
0x18000b118  mov     [rsp+2300h+phkResult], rax; phkResult
0x18000b11d  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18000b122  mov     [rsp+2300h+samDesired], ebx; samDesired
0x18000b126  mov     [rsp+2300h+dwOptions], r14d; dwOptions
0x18000b12b  xor     r9d, r9d; lpClass
0x18000b12e  xor     r8d, r8d; Reserved
0x18000b131  mov     rdx, rdi; lpSubKey
0x18000b134  mov     rcx, r13; hKey
0x18000b137  call    cs:__imp_RegCreateKeyExW
0x18000b13d  mov     ecx, eax
0x18000b13f  test    eax, eax
0x18000b141  jnz     loc_18000B2EB
0x18000b147  lea     rcx, [rsp+2300h+var_2290]; this
0x18000b14c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18000b151  mov     ecx, eax
0x18000b153  mov     rax, [rbp+2200h+var_2270]
0x18000b157  mov     [rsp+2300h+var_2290], rax
0x18000b15c  test    ecx, ecx
0x18000b15e  jnz     loc_18000B2EB
0x18000b164  mov     rdx, rdi; unsigned __int16 *
0x18000b167  mov     rcx, rsi; this
0x18000b16a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000b16f  mov     ebx, eax
0x18000b171  test    eax, eax
0x18000b173  js      loc_18000B3BD
0x18000b179  cmp     word ptr [rdi], 3Dh ; '='
0x18000b17d  jnz     short loc_18000B19C
0x18000b17f  mov     r9, rdi; unsigned __int16 *
0x18000b182  xor     r8d, r8d; unsigned __int16 *
0x18000b185  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x18000b18a  mov     rcx, rsi; this
0x18000b18d  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x18000b192  mov     ebx, eax
0x18000b194  test    eax, eax
0x18000b196  js      loc_18000B3BD
0x18000b19c  cmp     word ptr [rdi], 7Bh ; '{'
0x18000b1a0  jnz     loc_18000AE94
0x18000b1a6  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b1aa  inc     rax
0x18000b1ad  cmp     [rdi+rax*2], r14w
0x18000b1b2  jnz     short loc_18000B1AA
0x18000b1b4  cmp     rax, 1
0x18000b1b8  jnz     loc_18000AE94
0x18000b1be  mov     [rsp+2300h+dwOptions], r14d; int
0x18000b1c3  mov     r9d, r15d; int
0x18000b1c6  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18000b1cb  mov     rdx, rdi; unsigned __int16 *
0x18000b1ce  mov     rcx, rsi; this
0x18000b1d1  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000b1d6  mov     ebx, eax
0x18000b1d8  test    eax, eax
0x18000b1da  js      loc_18000B3BD
0x18000b1e0  mov     rdx, rdi
0x18000b1e3  mov     rcx, rsi
0x18000b1e6  jmp     loc_18000AE85
0x18000b1eb  cmp     [rbp+2200h+arg_20], r14d
0x18000b1f2  jnz     short loc_18000B20F
0x18000b1f4  mov     r9d, 20019h; unsigned int
0x18000b1fa  mov     r8, rdi; lpSubKey
0x18000b1fd  mov     rdx, r13; hKey
0x18000b200  lea     rcx, [rsp+2300h+var_2290]; this
0x18000b205  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18000b20a  mov     r14d, eax
0x18000b20d  jmp     short loc_18000B215
0x18000b20f  mov     r14d, 2
0x18000b215  mov     r15d, 1
0x18000b21b  test    r14d, r14d
0x18000b21e  cmovz   r15d, [rbp+2200h+arg_20]
0x18000b226  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18000b22a  mov     r8, rdi; Source
0x18000b22d  mov     edx, 104h; SizeInWords
0x18000b232  lea     rcx, [rbp+2200h+Destination]; Destination
0x18000b236  call    cs:__imp_wcsncpy_s
0x18000b23c  mov     ecx, eax; int
0x18000b23e  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000b243  mov     rdx, rdi; unsigned __int16 *
0x18000b246  mov     rcx, rsi; this
0x18000b249  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000b24e  mov     ebx, eax
0x18000b250  test    eax, eax
0x18000b252  js      loc_18000B3BD
0x18000b258  mov     rdx, rdi; unsigned __int16 *
0x18000b25b  mov     rcx, rsi; this
0x18000b25e  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18000b263  mov     ebx, eax
0x18000b265  xor     ecx, ecx
0x18000b267  test    eax, eax
0x18000b269  js      loc_18000B3BD
0x18000b26f  cmp     word ptr [rdi], 7Bh ; '{'
0x18000b273  jnz     short loc_18000B2C4
0x18000b275  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b279  inc     rax
0x18000b27c  cmp     [rdi+rax*2], cx
0x18000b280  jnz     short loc_18000B279
0x18000b282  cmp     rax, 1
0x18000b286  jnz     short loc_18000B2C4
0x18000b288  mov     [rsp+2300h+dwOptions], r15d; int
0x18000b28d  xor     r9d, r9d; int
0x18000b290  mov     r8, [rsp+2300h+var_2290]; HKEY
0x18000b295  mov     rdx, rdi; unsigned __int16 *
0x18000b298  mov     rcx, rsi; this
0x18000b29b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x18000b2a0  mov     ebx, eax
0x18000b2a2  test    eax, eax
0x18000b2a4  jns     short loc_18000B2AF
0x18000b2a6  test    r15d, r15d
0x18000b2a9  jz      loc_18000B3BD
0x18000b2af  mov     rdx, rdi; unsigned __int16 *
0x18000b2b2  mov     rcx, rsi; this
0x18000b2b5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000b2ba  mov     ebx, eax
0x18000b2bc  test    eax, eax
0x18000b2be  js      loc_18000B3BD
0x18000b2c4  cmp     r14d, 2
0x18000b2c8  mov     r15d, [rsp+2300h+var_22B0]
  ... truncated ...
```
