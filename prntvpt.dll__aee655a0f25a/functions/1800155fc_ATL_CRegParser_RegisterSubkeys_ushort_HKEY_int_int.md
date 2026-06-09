# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x1800155fc`
- end: `0x180015bf9`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `1533`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callers

- `0x1800152f0`
- `0x1800155fc`

## callees

- `0x18000f970`
- `0x1800119c8`
- `0x180011f78`
- `0x180011fe8`
- `0x180012030`
- `0x180012144`
- `0x180012560`
- `0x18001383c`
- `0x180014370`
- `0x1800146d4`
- `0x1800151dc`
- `0x1800155fc`
- `0x1800163c0`
- `0x180016550`
- `0x180022540`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180015a16`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x180015a16`
- `ADVAPI32!RegDeleteValueW` at `0x180015857`
- `ADVAPI32!RegDeleteValueW` at `0x180015857`
- `ADVAPI32!RegCreateKeyExW` at `0x180015917`
- `ADVAPI32!RegCreateKeyExW` at `0x180015917`
- `KERNEL32!lstrcmpiW` at `0x18001566f`
- `KERNEL32!lstrcmpiW` at `0x180015682`
- `KERNEL32!lstrcmpiW` at `0x180015766`
- `KERNEL32!lstrcmpiW` at `0x180015795`
- `KERNEL32!lstrcmpiW` at `0x18001566f`
- `KERNEL32!lstrcmpiW` at `0x180015682`
- `KERNEL32!lstrcmpiW` at `0x180015766`
- `KERNEL32!lstrcmpiW` at `0x180015795`

## string_xrefs

- `0x180015675`: `ForceRemove`
- `0x180015756`: `NoRemove`
- `0x180015665`: `Delete`

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
0x1800155fc  push    rbp
0x1800155fe  push    rbx
0x1800155ff  push    rsi
0x180015600  push    rdi
0x180015601  push    r12
0x180015603  push    r13
0x180015605  push    r14
0x180015607  push    r15
0x180015609  lea     rbp, [rsp-21C8h]
0x180015611  mov     eax, 22C8h
0x180015616  call    _alloca_probe
0x18001561b  sub     rsp, rax
0x18001561e  mov     rax, cs:__security_cookie
0x180015625  xor     rax, rsp
0x180015628  mov     [rbp+2200h+var_50], rax
0x18001562f  xor     r14d, r14d
0x180015632  mov     [rsp+2300h+var_22B0], r9d
0x180015637  mov     [rsp+2300h+var_2290], r14
0x18001563c  mov     r15d, r9d
0x18001563f  mov     [rsp+2300h+var_2288], r14
0x180015644  mov     r13, r8
0x180015647  mov     [rbp+2200h+var_2280], r14
0x18001564b  mov     rdi, rdx
0x18001564e  mov     rsi, rcx
0x180015651  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180015656  jmp     loc_18001587D
0x18001565b  cmp     word ptr [rdi], 7Dh ; '}'
0x18001565f  jz      loc_180015B93
0x180015665  lea     rdx, aDelete; "Delete"
0x18001566c  mov     rcx, rdi; lpString1
0x18001566f  call    cs:__imp_lstrcmpiW
0x180015675  lea     rdx, aForceremove; "ForceRemove"
0x18001567c  mov     rcx, rdi; lpString1
0x18001567f  mov     r14d, eax
0x180015682  call    cs:__imp_lstrcmpiW
0x180015688  test    eax, eax
0x18001568a  jz      short loc_180015695
0x18001568c  test    r14d, r14d
0x18001568f  jnz     loc_180015756
0x180015695  mov     rdx, rdi; unsigned __int16 *
0x180015698  mov     rcx, rsi; this
0x18001569b  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800156a0  mov     ebx, eax
0x1800156a2  test    eax, eax
0x1800156a4  js      loc_180015B93
0x1800156aa  test    r15d, r15d
0x1800156ad  jz      loc_180015756
0x1800156b3  mov     edx, 5Ch ; '\'; unsigned __int16
0x1800156b8  mov     [rsp+2300h+hKey], 0
0x1800156c1  mov     rcx, rdi; lpsz
0x1800156c4  mov     [rsp+2300h+var_22A0], 0
0x1800156cd  mov     [rsp+2300h+var_2298], 0
0x1800156d6  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x1800156db  test    rax, rax
0x1800156de  jnz     loc_180015B84
0x1800156e4  mov     rdx, rdi; unsigned __int16 *
0x1800156e7  call    ?CanForceRemoveKey@CRegParser@ATL@@IEAAHPEBG@Z; ATL::CRegParser::CanForceRemoveKey(ushort const *)
0x1800156ec  test    eax, eax
0x1800156ee  jz      short loc_18001570B
0x1800156f0  mov     rdx, rdi; unsigned __int16 *
0x1800156f3  mov     [rsp+2300h+hKey], r13
0x1800156f8  lea     rcx, [rsp+2300h+hKey]; this
0x1800156fd  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180015702  mov     [rsp+2300h+hKey], 0
0x18001570b  test    r14d, r14d
0x18001570e  jnz     short loc_18001574C
0x180015710  mov     rdx, rdi; unsigned __int16 *
0x180015713  mov     rcx, rsi; this
0x180015716  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001571b  xor     r14d, r14d
0x18001571e  mov     ebx, eax
0x180015720  test    eax, eax
0x180015722  js      loc_180015BCB
0x180015728  mov     rdx, rdi; unsigned __int16 *
0x18001572b  mov     rcx, rsi; this
0x18001572e  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180015733  lea     rcx, [rsp+2300h+hKey]; this
0x180015738  mov     ebx, eax
0x18001573a  test    eax, eax
0x18001573c  js      loc_180015BD0
0x180015742  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180015747  jmp     loc_18001597C
0x18001574c  lea     rcx, [rsp+2300h+hKey]; this
0x180015751  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180015756  lea     rdx, aNoremove; "NoRemove"
0x18001575d  mov     rcx, rdi; lpString1
0x180015760  mov     r12d, 1
0x180015766  call    cs:__imp_lstrcmpiW
0x18001576c  xor     r14d, r14d
0x18001576f  test    eax, eax
0x180015771  jnz     short loc_18001578B
0x180015773  mov     rdx, rdi; unsigned __int16 *
0x180015776  mov     rcx, rsi; this
0x180015779  mov     r12d, r14d
0x18001577c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180015781  mov     ebx, eax
0x180015783  test    eax, eax
0x180015785  js      loc_180015B93
0x18001578b  lea     rdx, aVal; "Val"
0x180015792  mov     rcx, rdi; lpString1
0x180015795  call    cs:__imp_lstrcmpiW
0x18001579b  test    eax, eax
0x18001579d  jnz     loc_18001588C
0x1800157a3  lea     rdx, [rbp+2200h+ValueName]; unsigned __int16 *
0x1800157aa  mov     rcx, rsi; this
0x1800157ad  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800157b2  mov     ebx, eax
0x1800157b4  test    eax, eax
0x1800157b6  js      loc_180015B93
0x1800157bc  mov     rdx, rdi; unsigned __int16 *
0x1800157bf  mov     rcx, rsi; this
0x1800157c2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800157c7  mov     ebx, eax
0x1800157c9  test    eax, eax
0x1800157cb  js      loc_180015B93
0x1800157d1  cmp     word ptr [rdi], 3Dh ; '='
0x1800157d5  jnz     loc_180015B8E
0x1800157db  test    r15d, r15d
0x1800157de  jz      short loc_180015810
0x1800157e0  mov     r9, rdi; unsigned __int16 *
0x1800157e3  mov     [rsp+2300h+var_22A0], r14
0x1800157e8  lea     r8, [rbp+2200h+ValueName]; unsigned __int16 *
0x1800157ef  mov     [rsp+2300h+var_2298], r14
0x1800157f4  lea     rdx, [rsp+2300h+hKey]; struct ATL::CRegKey *
0x1800157f9  mov     [rsp+2300h+hKey], r13
0x1800157fe  mov     rcx, rsi; this
0x180015801  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180015806  mov     [rsp+2300h+hKey], r14
0x18001580b  jmp     loc_180015733
0x180015810  cmp     [rbp+2200h+arg_20], r14d
0x180015817  jnz     short loc_180015872
0x180015819  test    r12d, r12d
0x18001581c  jz      short loc_180015872
0x18001581e  mov     r9d, 20006h; unsigned int
0x180015824  mov     [rsp+2300h+hKey], r14
0x180015829  xor     r8d, r8d; lpSubKey
0x18001582c  mov     [rsp+2300h+var_22A0], r14
0x180015831  mov     rdx, r13; hKey
0x180015834  mov     [rsp+2300h+var_2298], r14
0x180015839  lea     rcx, [rsp+2300h+hKey]; this
0x18001583e  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x180015843  test    eax, eax
0x180015845  jnz     loc_180015BC2
0x18001584b  mov     rcx, [rsp+2300h+hKey]; hKey
0x180015850  lea     rdx, [rbp+2200h+ValueName]; lpValueName
0x180015857  call    cs:__imp_RegDeleteValueW
0x18001585d  test    eax, 0FFFFFFFDh
0x180015862  jnz     loc_180015BC2
0x180015868  lea     rcx, [rsp+2300h+hKey]; this
0x18001586d  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180015872  mov     rdx, rdi; unsigned __int16 *
0x180015875  mov     rcx, rsi; this
0x180015878  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x18001587d  mov     ebx, eax
0x18001587f  test    eax, eax
0x180015881  jns     loc_18001565B
0x180015887  jmp     loc_180015B93
0x18001588c  mov     edx, 5Ch ; '\'; unsigned __int16
0x180015891  mov     rcx, rdi; lpsz
0x180015894  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x180015899  test    rax, rax
0x18001589c  jnz     loc_180015B8E
0x1800158a2  test    r15d, r15d
0x1800158a5  jz      loc_1800159CB
0x1800158ab  mov     r9d, 2001Fh; unsigned int
0x1800158b1  lea     rcx, [rsp+2300h+var_2290]; this
0x1800158b6  mov     r8, rdi; lpSubKey
0x1800158b9  mov     rdx, r13; hKey
0x1800158bc  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800158c1  test    eax, eax
0x1800158c3  jz      short loc_180015944
0x1800158c5  mov     r9d, 20019h; unsigned int
0x1800158cb  lea     rcx, [rsp+2300h+var_2290]; this
0x1800158d0  mov     r8, rdi; lpSubKey
0x1800158d3  mov     rdx, r13; hKey
0x1800158d6  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800158db  test    eax, eax
0x1800158dd  jz      short loc_180015944
0x1800158df  lea     rax, [rbp+2200h+dwDisposition]
0x1800158e3  mov     [rbp+2200h+dwDisposition], r14d
0x1800158e7  mov     [rsp+2300h+lpdwDisposition], rax; lpdwDisposition
0x1800158ec  xor     r9d, r9d; lpClass
0x1800158ef  lea     rax, [rbp+2200h+var_2270]
0x1800158f3  mov     [rbp+2200h+var_2270], r14
0x1800158f7  mov     [rsp+2300h+phkResult], rax; phkResult
0x1800158fc  xor     r8d, r8d; Reserved
0x1800158ff  mov     [rsp+2300h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180015904  mov     rdx, rdi; lpSubKey
0x180015907  mov     [rsp+2300h+samDesired], 2001Fh; samDesired
0x18001590f  mov     rcx, r13; hKey
0x180015912  mov     dword ptr [rsp+2300h+dwOptions], r14d; dwOptions
0x180015917  call    cs:__imp_RegCreateKeyExW
0x18001591d  mov     ebx, eax
0x18001591f  test    eax, eax
0x180015921  jnz     loc_180015BD7
0x180015927  lea     rcx, [rsp+2300h+var_2290]; this
0x18001592c  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x180015931  mov     ebx, eax
0x180015933  mov     rax, [rbp+2200h+var_2270]
0x180015937  mov     [rsp+2300h+var_2290], rax
0x18001593c  test    ebx, ebx
0x18001593e  jnz     loc_180015BD7
0x180015944  mov     rdx, rdi; unsigned __int16 *
0x180015947  mov     rcx, rsi; this
0x18001594a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001594f  mov     ebx, eax
0x180015951  test    eax, eax
0x180015953  js      loc_180015B93
0x180015959  cmp     word ptr [rdi], 3Dh ; '='
0x18001595d  jnz     short loc_18001597C
0x18001595f  mov     r9, rdi; unsigned __int16 *
0x180015962  lea     rdx, [rsp+2300h+var_2290]; struct ATL::CRegKey *
0x180015967  xor     r8d, r8d; unsigned __int16 *
0x18001596a  mov     rcx, rsi; this
0x18001596d  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x180015972  mov     ebx, eax
0x180015974  test    eax, eax
0x180015976  js      loc_180015B93
0x18001597c  cmp     word ptr [rdi], 7Bh ; '{'
0x180015980  jnz     loc_18001565B
0x180015986  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001598a  inc     rax
0x18001598d  cmp     [rdi+rax*2], r14w
0x180015992  jnz     short loc_18001598A
0x180015994  cmp     rax, 1
0x180015998  jnz     loc_18001565B
0x18001599e  mov     r8, [rsp+2300h+var_2290]; HKEY
0x1800159a3  mov     r9d, r15d; int
0x1800159a6  mov     rdx, rdi; unsigned __int16 *
0x1800159a9  mov     dword ptr [rsp+2300h+dwOptions], r14d; int
0x1800159ae  mov     rcx, rsi; this
0x1800159b1  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x1800159b6  mov     ebx, eax
0x1800159b8  test    eax, eax
0x1800159ba  js      loc_180015B93
0x1800159c0  mov     rdx, rdi
0x1800159c3  mov     rcx, rsi
0x1800159c6  jmp     loc_180015651
0x1800159cb  cmp     [rbp+2200h+arg_20], r14d
0x1800159d2  jnz     short loc_1800159EF
0x1800159d4  mov     r9d, 20019h; unsigned int
0x1800159da  lea     rcx, [rsp+2300h+var_2290]; this
0x1800159df  mov     r8, rdi; lpSubKey
0x1800159e2  mov     rdx, r13; hKey
0x1800159e5  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x1800159ea  mov     r14d, eax
0x1800159ed  jmp     short loc_1800159F5
0x1800159ef  mov     r14d, 2
0x1800159f5  test    r14d, r14d
0x1800159f8  lea     rcx, [rbp+2200h+var_2260]
0x1800159fc  mov     r15d, 1
0x180015a02  mov     r8, rdi
0x180015a05  cmovz   r15d, [rbp+2200h+arg_20]
0x180015a0d  mov     edx, 104h
0x180015a12  or      r9, 0FFFFFFFFFFFFFFFFh
0x180015a16  call    cs:__imp__o_wcsncpy_s
0x180015a1c  mov     ecx, eax; int
0x180015a1e  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x180015a23  mov     rdx, rdi; unsigned __int16 *
0x180015a26  mov     rcx, rsi; this
0x180015a29  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180015a2e  mov     ebx, eax
0x180015a30  test    eax, eax
0x180015a32  js      loc_180015B93
0x180015a38  mov     rdx, rdi; unsigned __int16 *
0x180015a3b  mov     rcx, rsi; this
0x180015a3e  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x180015a43  xor     ecx, ecx
0x180015a45  mov     ebx, eax
0x180015a47  test    eax, eax
0x180015a49  js      loc_180015B93
0x180015a4f  cmp     word ptr [rdi], 7Bh ; '{'
0x180015a53  jnz     short loc_180015AA4
0x180015a55  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015a59  inc     rax
0x180015a5c  cmp     [rdi+rax*2], cx
0x180015a60  jnz     short loc_180015A59
0x180015a62  cmp     rax, 1
0x180015a66  jnz     short loc_180015AA4
0x180015a68  mov     r8, [rsp+2300h+var_2290]; HKEY
0x180015a6d  xor     r9d, r9d; int
0x180015a70  mov     rdx, rdi; unsigned __int16 *
0x180015a73  mov     dword ptr [rsp+2300h+dwOptions], r15d; int
0x180015a78  mov     rcx, rsi; this
0x180015a7b  call    ?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z; ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)
0x180015a80  mov     ebx, eax
0x180015a82  test    eax, eax
0x180015a84  jns     short loc_180015A8F
0x180015a86  test    r15d, r15d
0x180015a89  jz      loc_180015B93
0x180015a8f  mov     rdx, rdi; unsigned __int16 *
0x180015a92  mov     rcx, rsi; this
0x180015a95  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180015a9a  mov     ebx, eax
0x180015a9c  test    eax, eax
0x180015a9e  js      loc_180015B93
0x180015aa4  mov     r15d, [rsp+2300h+var_22B0]
0x180015aa9  cmp     r14d, 2
0x180015aad  jz      loc_18001565B
0x180015ab3  test    r14d, r14d
  ... truncated ...
```
