# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x14000bf0c`
- end: `0x14000c509`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1533`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x14000b980`
- `0x14000bf0c`

## callees

- `0x1400099b0`
- `0x140009f74`
- `0x140009fe4`
- `0x14000a754`
- `0x14000a830`
- `0x14000aa34`
- `0x14000ac98`
- `0x14000add4`
- `0x14000b04c`
- `0x14000b86c`
- `0x14000bf0c`
- `0x14000c828`
- `0x14000c8f8`
- `0x140113390`
- `0x140113450`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x14000c326`
- `msvcrt!wcsncpy_s` at `0x14000c326`
- `KERNEL32!lstrcmpiW` at `0x14000bf7f`
- `KERNEL32!lstrcmpiW` at `0x14000bf92`
- `KERNEL32!lstrcmpiW` at `0x14000c076`
- `KERNEL32!lstrcmpiW` at `0x14000c0a5`
- `KERNEL32!lstrcmpiW` at `0x14000bf7f`
- `KERNEL32!lstrcmpiW` at `0x14000bf92`
- `KERNEL32!lstrcmpiW` at `0x14000c076`
- `KERNEL32!lstrcmpiW` at `0x14000c0a5`
- `ADVAPI32!RegDeleteValueW` at `0x14000c167`
- `ADVAPI32!RegDeleteValueW` at `0x14000c167`
- `ADVAPI32!RegCreateKeyExW` at `0x14000c227`
- `ADVAPI32!RegCreateKeyExW` at `0x14000c227`

## string_xrefs

- `0x14000bf85`: `ForceRemove`
- `0x14000c066`: `NoRemove`
- `0x14000bf75`: `Delete`

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
  errno_t v20; // eax
  int v21; // eax
  ATL::CRegParser *v22; // rcx
  __int64 v23; // rax
  int HasSubKeys; // r15d
  unsigned int v25; // r14d
  unsigned int v27; // ecx
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v30; // [rsp+60h] [rbp-A0h]
  __int64 v31; // [rsp+68h] [rbp-98h]
  HKEY v32[3]; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwDisposition; // [rsp+88h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  wchar_t Destination[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR ValueName[4096]; // [rsp+2B0h] [rbp+1B0h] BYREF

  memset(v32, 0, sizeof(v32));
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
            v30 = 0;
            v31 = 0;
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
            v30 = 0;
            v31 = 0;
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
          v30 = 0;
          v31 = 0;
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
          v18 = ATL::CRegKey::Open((ATL::CRegKey *)v32, a3, v7, 0x20019u);
        v19 = 1;
        if ( !v18 )
          v19 = a5;
        v20 = wcsncpy_s(Destination, 0x104u, v7, 0xFFFFFFFFFFFFFFFFuLL);
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
            v11 = ATL::CRegParser::RegisterSubkeys(i, v7, v32[0], 0, v19);
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
          else if ( a5 && ATL::CRegParser::HasSubKeys(v22, v32[0]) )
          {
            if ( ATL::CRegParser::CanForceRemoveKey(v22, Destination) && v14 )
              ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)v32, Destination);
          }
          else
          {
            HasSubKeys = ATL::CRegParser::HasSubKeys(v22, v32[0]);
            v25 = ATL::CRegKey::Close((ATL::CRegKey *)v32);
            if ( v25 )
            {
              ATL::CRegKey::Close((ATL::CRegKey *)v32);
              v27 = v25;
              return ATL::AtlHresultFromWin32(v27);
            }
            if ( v14 && !HasSubKeys )
            {
              v30 = 0;
              v31 = 0;
              hKey = a3;
              v15 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)&hKey, Destination);
              hKey = 0;
              if ( v15 )
                goto LABEL_80;
              ATL::CRegKey::Close((ATL::CRegKey *)&hKey);
            }
            v5 = a4;
          }
        }
      }
      if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v32, a3, v7, 0x2001Fu) )
      {
        if ( (unsigned int)ATL::CRegKey::Open((ATL::CRegKey *)v32, a3, v7, 0x20019u) )
        {
          dwDisposition = 0;
          phkResult = 0;
          v16 = RegCreateKeyExW(a3, v7, 0, 0, 0, 0x2001Fu, 0, &phkResult, &dwDisposition);
          if ( v16 || (v16 = ATL::CRegKey::Close((ATL::CRegKey *)v32), v32[0] = phkResult, v16) )
          {
            ATL::CRegKey::Close((ATL::CRegKey *)v32);
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
        v11 = ATL::CRegParser::AddValue(i, v32, 0, v7);
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
    v11 = ATL::CRegParser::RegisterSubkeys(i, v7, v32[0], v5, 0);
    if ( v11 < 0 )
      break;
    a2 = v7;
  }
LABEL_79:
  ATL::CRegKey::Close((ATL::CRegKey *)v32);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14000bf0c  push    rbp
0x14000bf0e  push    rbx
0x14000bf0f  push    rsi
0x14000bf10  push    rdi
0x14000bf11  push    r12
0x14000bf13  push    r13
0x14000bf15  push    r14
0x14000bf17  push    r15
0x14000bf19  lea     rbp, [rsp-21C8h]
0x14000bf21  mov     eax, 22C8h
0x14000bf26  call    _alloca_probe
0x14000bf2b  sub     rsp, rax
0x14000bf2e  mov     rax, cs:__security_cookie
0x14000bf35  xor     rax, rsp
0x14000bf38  mov     [rbp+2200h+var_50], rax
0x14000bf3f  xor     r14d, r14d
0x14000bf42  mov     [rsp+2300h+var_22B0], r9d
0x14000bf47  mov     [rsp+2300h+var_2290], r14
0x14000bf4c  mov     r15d, r9d
0x14000bf4f  mov     [rsp+2300h+var_2288], r14
0x14000bf54  mov     r13, r8
0x14000bf57  mov     [rbp+2200h+var_2280], r14
0x14000bf5b  mov     rdi, rdx
0x14000bf5e  mov     rsi, rcx
0x14000bf61  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000bf66  jmp     loc_14000C18D
0x14000bf6b  cmp     word ptr [rdi], 7Dh ; '}'
0x14000bf6f  jz      loc_14000C4A3
0x14000bf75  lea     rdx, String2; "Delete"
0x14000bf7c  mov     rcx, rdi; lpString1
0x14000bf7f  call    cs:__imp_lstrcmpiW
0x14000bf85  lea     rdx, aForceremove; "ForceRemove"
0x14000bf8c  mov     rcx, rdi; lpString1
0x14000bf8f  mov     r14d, eax
0x14000bf92  call    cs:__imp_lstrcmpiW
0x14000bf98  test    eax, eax
0x14000bf9a  jz      short loc_14000BFA5
0x14000bf9c  test    r14d, r14d
0x14000bf9f  jnz     loc_14000C066
0x14000bfa5  mov     rdx, rdi; unsigned __int16 *
0x14000bfa8  mov     rcx, rsi; this
0x14000bfab  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000bfb0  mov     ebx, eax
0x14000bfb2  test    eax, eax
0x14000bfb4  js      loc_14000C4A3
0x14000bfba  test    r15d, r15d
0x14000bfbd  jz      loc_14000C066
0x14000bfc3  mov     edx, 5Ch ; '\'; unsigned __int16
0x14000bfc8  mov     [rsp+2300h+hKey], 0
0x14000bfd1  mov     rcx, rdi; lpsz
0x14000bfd4  mov     [rsp+2300h+var_22A0], 0
0x14000bfdd  mov     [rsp+2300h+var_2298], 0
0x14000bfe6  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x14000bfeb  test    rax, rax
0x14000bfee  jnz     loc_14000C494
0x14000bff4  mov     rdx, rdi; unsigned __int16 *
0x14000bff7  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x14000bffc  test    eax, eax
0x14000bffe  jz      short loc_14000C01B
0x14000c000  mov     rdx, rdi; unsigned __int16 *
0x14000c003  mov     [rsp+2300h+hKey], r13
0x14000c008  lea     rcx, [rsp+2300h+hKey]; this
0x14000c00d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x14000c012  mov     [rsp+2300h+hKey], 0
0x14000c01b  test    r14d, r14d
0x14000c01e  jnz     short loc_14000C05C
0x14000c020  mov     rdx, rdi; unsigned __int16 *
0x14000c023  mov     rcx, rsi; this
0x14000c026  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000c02b  xor     r14d, r14d
0x14000c02e  mov     ebx, eax
0x14000c030  test    eax, eax
0x14000c032  js      loc_14000C4DB
0x14000c038  mov     rdx, rdi; unsigned __int16 *
0x14000c03b  mov     rcx, rsi; this
0x14000c03e  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x14000c043  lea     rcx, [rsp+2300h+hKey]; this
0x14000c048  mov     ebx, eax
0x14000c04a  test    eax, eax
0x14000c04c  js      loc_14000C4E0
0x14000c052  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14000c057  jmp     loc_14000C28C
0x14000c05c  lea     rcx, [rsp+2300h+hKey]; this
0x14000c061  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14000c066  lea     rdx, aNoremove; "NoRemove"
0x14000c06d  mov     rcx, rdi; lpString1
0x14000c070  mov     r12d, 1
0x14000c076  call    cs:__imp_lstrcmpiW
0x14000c07c  xor     r14d, r14d
0x14000c07f  test    eax, eax
0x14000c081  jnz     short loc_14000C09B
0x14000c083  mov     rdx, rdi; unsigned __int16 *
0x14000c086  mov     rcx, rsi; this
0x14000c089  mov     r12d, r14d
0x14000c08c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000c091  mov     ebx, eax
0x14000c093  test    eax, eax
0x14000c095  js      loc_14000C4A3
0x14000c09b  lea     rdx, aVal; "Val"
0x14000c0a2  mov     rcx, rdi; lpString1
0x14000c0a5  call    cs:__imp_lstrcmpiW
0x14000c0ab  test    eax, eax
0x14000c0ad  jnz     loc_14000C19C
0x14000c0b3  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x14000c0ba  mov     rcx, rsi; this
0x14000c0bd  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000c0c2  mov     ebx, eax
0x14000c0c4  test    eax, eax
0x14000c0c6  js      loc_14000C4A3
0x14000c0cc  mov     rdx, rdi; unsigned __int16 *
0x14000c0cf  mov     rcx, rsi; this
0x14000c0d2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000c0d7  mov     ebx, eax
0x14000c0d9  test    eax, eax
0x14000c0db  js      loc_14000C4A3
0x14000c0e1  cmp     word ptr [rdi], 3Dh ; '='
0x14000c0e5  jnz     loc_14000C49E
0x14000c0eb  test    r15d, r15d
0x14000c0ee  jz      short loc_14000C120
0x14000c0f0  mov     r9, rdi; unsigned __int16 *
0x14000c0f3  mov     [rsp+2300h+var_22A0], r14
0x14000c0f8  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x14000c0ff  mov     [rsp+2300h+var_2298], r14
0x14000c104  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x14000c109  mov     [rsp+2300h+hKey], r13
0x14000c10e  mov     rcx, rsi; this
0x14000c111  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x14000c116  mov     [rsp+2300h+hKey], r14
0x14000c11b  jmp     loc_14000C043
0x14000c120  cmp     [rbp+2200h+arg_20], r14d
0x14000c127  jnz     short loc_14000C182
0x14000c129  test    r12d, r12d
0x14000c12c  jz      short loc_14000C182
0x14000c12e  mov     r9d, 20006h; unsigned int
0x14000c134  mov     [rsp+2300h+hKey], r14
0x14000c139  xor     r8d, r8d; lpSubKey
0x14000c13c  mov     [rsp+2300h+var_22A0], r14
0x14000c141  mov     rdx, r13; hKey
0x14000c144  mov     [rsp+2300h+var_2298], r14
0x14000c149  lea     rcx, [rsp+2300h+hKey]; this
0x14000c14e  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14000c153  test    eax, eax
0x14000c155  jnz     loc_14000C4D2
0x14000c15b  mov     rcx, [rsp+2300h+hKey]; hKey
0x14000c160  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x14000c167  call    cs:__imp_RegDeleteValueW
0x14000c16d  test    eax, 0FFFFFFFDh
0x14000c172  jnz     loc_14000C4D2
0x14000c178  lea     rcx, [rsp+2300h+hKey]; this
0x14000c17d  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14000c182  mov     rdx, rdi; unsigned __int16 *
0x14000c185  mov     rcx, rsi; this
0x14000c188  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x14000c18d  mov     ebx, eax
0x14000c18f  test    eax, eax
0x14000c191  jns     loc_14000BF6B
0x14000c197  jmp     loc_14000C4A3
0x14000c19c  mov     edx, 5Ch ; '\'; unsigned __int16
0x14000c1a1  mov     rcx, rdi; lpsz
0x14000c1a4  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x14000c1a9  test    rax, rax
0x14000c1ac  jnz     loc_14000C49E
0x14000c1b2  test    r15d, r15d
0x14000c1b5  jz      loc_14000C2DB
0x14000c1bb  mov     r9d, 2001Fh; unsigned int
0x14000c1c1  lea     rcx, [rsp+2300h+var_2290]; this
0x14000c1c6  mov     r8, rdi; lpSubKey
0x14000c1c9  mov     rdx, r13; hKey
0x14000c1cc  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14000c1d1  test    eax, eax
0x14000c1d3  jz      short loc_14000C254
0x14000c1d5  mov     r9d, 20019h; unsigned int
0x14000c1db  lea     rcx, [rsp+2300h+var_2290]; this
0x14000c1e0  mov     r8, rdi; lpSubKey
0x14000c1e3  mov     rdx, r13; hKey
0x14000c1e6  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14000c1eb  test    eax, eax
0x14000c1ed  jz      short loc_14000C254
0x14000c1ef  lea     rax, [rbp+2200h+dwDisposition]
0x14000c1f3  mov     [rbp+2200h+dwDisposition], r14d
0x14000c1f7  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x14000c1fc  xor     r9d, r9d; lpClass
0x14000c1ff  lea     rax, [rbp+2200h+var_2270]
0x14000c203  mov     [rbp+2200h+var_2270], r14
0x14000c207  mov     [rsp+2300h+phkResult], rax; phkResult
0x14000c20c  xor     r8d, r8d; Reserved
0x14000c20f  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x14000c214  mov     rdx, rdi; lpSubKey
0x14000c217  mov     [rsp+2300h+samDesired], 2001Fh; samDesired
0x14000c21f  mov     rcx, r13; hKey
0x14000c222  mov     [rsp+2300h+dwOptions], r14d; dwOptions
0x14000c227  call    cs:__imp_RegCreateKeyExW
0x14000c22d  mov     ebx, eax
0x14000c22f  test    eax, eax
0x14000c231  jnz     loc_14000C4E7
0x14000c237  lea     rcx, [rsp+2300h+var_2290]; this
0x14000c23c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x14000c241  mov     ebx, eax
0x14000c243  mov     rax, [rbp+2200h+var_2270]
0x14000c247  mov     [rsp+2300h+var_2290], rax
0x14000c24c  test    ebx, ebx
0x14000c24e  jnz     loc_14000C4E7
0x14000c254  mov     rdx, rdi; unsigned __int16 *
0x14000c257  mov     rcx, rsi; this
0x14000c25a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000c25f  mov     ebx, eax
0x14000c261  test    eax, eax
0x14000c263  js      loc_14000C4A3
0x14000c269  cmp     word ptr [rdi], 3Dh ; '='
0x14000c26d  jnz     short loc_14000C28C
0x14000c26f  mov     r9, rdi; unsigned __int16 *
0x14000c272  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x14000c277  xor     r8d, r8d; unsigned __int16 *
0x14000c27a  mov     rcx, rsi; this
0x14000c27d  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x14000c282  mov     ebx, eax
0x14000c284  test    eax, eax
0x14000c286  js      loc_14000C4A3
0x14000c28c  cmp     word ptr [rdi], 7Bh ; '{'
0x14000c290  jnz     loc_14000BF6B
0x14000c296  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000c29a  inc     rax
0x14000c29d  cmp     [rdi+rax*2], r14w
0x14000c2a2  jnz     short loc_14000C29A
0x14000c2a4  cmp     rax, 1
0x14000c2a8  jnz     loc_14000BF6B
0x14000c2ae  mov     r8, [rsp+2300h+var_2290]; HKEY
0x14000c2b3  mov     r9d, r15d; int
0x14000c2b6  mov     rdx, rdi; unsigned __int16 *
0x14000c2b9  mov     [rsp+2300h+dwOptions], r14d; int
0x14000c2be  mov     rcx, rsi; this
0x14000c2c1  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x14000c2c6  mov     ebx, eax
0x14000c2c8  test    eax, eax
0x14000c2ca  js      loc_14000C4A3
0x14000c2d0  mov     rdx, rdi
0x14000c2d3  mov     rcx, rsi
0x14000c2d6  jmp     loc_14000BF61
0x14000c2db  cmp     [rbp+2200h+arg_20], r14d
0x14000c2e2  jnz     short loc_14000C2FF
0x14000c2e4  mov     r9d, 20019h; unsigned int
0x14000c2ea  lea     rcx, [rsp+2300h+var_2290]; this
0x14000c2ef  mov     r8, rdi; lpSubKey
0x14000c2f2  mov     rdx, r13; hKey
0x14000c2f5  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x14000c2fa  mov     r14d, eax
0x14000c2fd  jmp     short loc_14000C305
0x14000c2ff  mov     r14d, 2
0x14000c305  test    r14d, r14d
0x14000c308  lea     rcx, [rbp+2200h+Destination]; Destination
0x14000c30c  mov     r15d, 1
0x14000c312  mov     r8, rdi; Source
0x14000c315  cmovz   r15d, [rbp+2200h+arg_20]
0x14000c31d  mov     edx, 104h; SizeInWords
0x14000c322  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x14000c326  call    cs:__imp_wcsncpy_s
0x14000c32c  mov     ecx, eax; int
0x14000c32e  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x14000c333  mov     rdx, rdi; unsigned __int16 *
0x14000c336  mov     rcx, rsi; this
0x14000c339  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000c33e  mov     ebx, eax
0x14000c340  test    eax, eax
0x14000c342  js      loc_14000C4A3
0x14000c348  mov     rdx, rdi; unsigned __int16 *
0x14000c34b  mov     rcx, rsi; this
0x14000c34e  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x14000c353  xor     ecx, ecx
0x14000c355  mov     ebx, eax
0x14000c357  test    eax, eax
0x14000c359  js      loc_14000C4A3
0x14000c35f  cmp     word ptr [rdi], 7Bh ; '{'
0x14000c363  jnz     short loc_14000C3B4
0x14000c365  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000c369  inc     rax
0x14000c36c  cmp     [rdi+rax*2], cx
0x14000c370  jnz     short loc_14000C369
0x14000c372  cmp     rax, 1
0x14000c376  jnz     short loc_14000C3B4
0x14000c378  mov     r8, [rsp+2300h+var_2290]; HKEY
0x14000c37d  xor     r9d, r9d; int
0x14000c380  mov     rdx, rdi; unsigned __int16 *
0x14000c383  mov     [rsp+2300h+dwOptions], r15d; int
0x14000c388  mov     rcx, rsi; this
0x14000c38b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x14000c390  mov     ebx, eax
0x14000c392  test    eax, eax
0x14000c394  jns     short loc_14000C39F
0x14000c396  test    r15d, r15d
0x14000c399  jz      loc_14000C4A3
0x14000c39f  mov     rdx, rdi; unsigned __int16 *
0x14000c3a2  mov     rcx, rsi; this
0x14000c3a5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000c3aa  mov     ebx, eax
0x14000c3ac  test    eax, eax
0x14000c3ae  js      loc_14000C4A3
0x14000c3b4  mov     r15d, [rsp+2300h+var_22B0]
0x14000c3b9  cmp     r14d, 2
0x14000c3bd  jz      loc_14000BF6B
0x14000c3c3  test    r14d, r14d
  ... truncated ...
```
