# DoesThisAppMatch(ApplicationIdentity *,HKEY__ *)

- ea: `0x1800325d4`
- end: `0x180032a6d`
- name: `?DoesThisAppMatch@@YAJPEAVApplicationIdentity@@PEAUHKEY__@@@Z`
- size: `1177`
- prototype: `__int64 __fastcall(struct ApplicationIdentity *this, HKEY hKey)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18000ac2c`
- `0x180032a80`

## callees

- `0x180003070`
- `0x180003740`
- `0x18000b1f0`
- `0x1800325d4`
- `0x18003310c`
- `0x180033174`
- `0x180033444`
- `0x1800334a0`
- `0x180033560`
- `0x18003378c`
- `0x1800337bc`
- `0x180041a38`
- `0x180041ac0`

## import_xrefs

- `ADVAPI32!RegQueryInfoKeyW` at `0x18003265d`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18003265d`
- `ADVAPI32!RegEnumValueW` at `0x1800326e8`
- `ADVAPI32!RegEnumValueW` at `0x1800326e8`

## string_xrefs

- `0x18003272d`: `CompanyName`
- `0x1800326f6`: `Company`
- `0x18003270d`: `Company`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DoesThisAppMatch(unsigned __int16 **this, HKEY hKey)
{
  LSTATUS v4; // eax
  unsigned int v5; // ebx
  unsigned __int128 v6; // rax
  BYTE *v7; // rsi
  DWORD v8; // r15d
  int v9; // r14d
  int IsAString; // eax
  _QWORD *v11; // rbx
  BYTE *v12; // rax
  int v13; // edx
  int v14; // r8d
  bool v15; // zf
  _QWORD *v16; // rbx
  BYTE *v17; // rax
  int v18; // edx
  _QWORD *v19; // rbx
  BYTE *v20; // rax
  int v21; // edx
  struct ApplicationVersion *v22; // rdx
  ApplicationVersion *v23; // rcx
  int v24; // ebx
  int v25; // ebx
  int v26; // ebx
  DWORD Type; // [rsp+60h] [rbp-69h] BYREF
  DWORD cbMaxValueLen; // [rsp+64h] [rbp-65h] BYREF
  DWORD cbData; // [rsp+68h] [rbp-61h] BYREF
  DWORD cchValueName; // [rsp+6Ch] [rbp-5Dh] BYREF
  BYTE *v32; // [rsp+70h] [rbp-59h] BYREF
  int v33; // [rsp+78h] [rbp-51h]
  _QWORD v34[3]; // [rsp+80h] [rbp-49h] BYREF
  int v35; // [rsp+98h] [rbp-31h]
  WCHAR ValueName[32]; // [rsp+A0h] [rbp-29h] BYREF

  cchValueName = 30;
  v32 = 0;
  v33 = 0;
  cbMaxValueLen = 0;
  cbData = 0;
  Type = 1;
  v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, 0, 0, &cbMaxValueLen, 0, 0);
  v5 = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      v5 = (unsigned __int16)v4 | 0x80070000;
LABEL_71:
    Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&v32);
    return v5;
  }
  v6 = ((unsigned __int64)cbMaxValueLen >> 1) * (unsigned __int128)2uLL;
  if ( !is_mul_ok((unsigned __int64)cbMaxValueLen >> 1, 2u) )
    *(_QWORD *)&v6 = -1;
  v7 = (BYTE *)operator new(v6, *((const struct NoThrow **)&v6 + 1));
  v32 = v7;
  if ( !v7 )
  {
    Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&v32);
    return 2147942414LL;
  }
  v33 = 1;
  v8 = 0;
  v9 = 0;
  cbData = cbMaxValueLen;
  while ( !RegEnumValueW(hKey, v8, ValueName, &cchValueName, 0, &Type, v7, &cbData) )
  {
    if ( !wcscmp(ValueName, L"Company") )
    {
      IsAString = VerifyThisIsAString(L"Company", Type);
      if ( IsAString < 0 )
        goto LABEL_67;
      v11 = this + 3;
      if ( !this[3] )
        ApplicationIdentity::FetchResourceString((ApplicationIdentity *)this, L"CompanyName", this + 3);
      if ( !*v11 )
        goto LABEL_68;
      v12 = v7;
      do
      {
        v13 = *(unsigned __int16 *)&v12[*v11 - (_QWORD)v7];
        v14 = *(unsigned __int16 *)v12 - v13;
        if ( v14 )
          break;
        v12 += 2;
      }
      while ( v13 );
LABEL_17:
      v15 = v14 == 0;
      goto LABEL_65;
    }
    if ( !wcscmp(ValueName, L"Product Name") )
    {
      IsAString = VerifyThisIsAString(L"Product Name", Type);
      if ( IsAString < 0 )
        goto LABEL_67;
      v16 = this + 4;
      if ( !this[4] )
        ApplicationIdentity::FetchResourceString((ApplicationIdentity *)this, L"ProductName", this + 4);
      if ( !*v16 )
        goto LABEL_68;
      v17 = v7;
      do
      {
        v18 = *(unsigned __int16 *)&v17[*v16 - (_QWORD)v7];
        v14 = *(unsigned __int16 *)v17 - v18;
        if ( v14 )
          break;
        v17 += 2;
      }
      while ( v18 );
      goto LABEL_17;
    }
    if ( !wcscmp(ValueName, L"Internal Name") )
    {
      IsAString = VerifyThisIsAString(L"Internal Name", Type);
      if ( IsAString < 0 )
        goto LABEL_67;
      v19 = this + 5;
      if ( !this[5] )
        ApplicationIdentity::FetchResourceString((ApplicationIdentity *)this, L"InternalName", this + 5);
      if ( !*v19 )
        goto LABEL_68;
      v20 = v7;
      do
      {
        v21 = *(unsigned __int16 *)&v20[*v19 - (_QWORD)v7];
        v14 = *(unsigned __int16 *)v20 - v21;
        if ( v14 )
          break;
        v20 += 2;
      }
      while ( v21 );
      goto LABEL_17;
    }
    if ( !wcscmp(ValueName, L"Maximum File Version") )
    {
      IsAString = VerifyThisIsAString(L"Maximum File Version", Type);
      if ( IsAString < 0 )
        goto LABEL_67;
      if ( !this[10] && (int)ApplicationIdentity::FetchFileVersion((ApplicationIdentity *)this) < 0 )
        goto LABEL_68;
      v35 = 0;
      v34[0] = v7;
      if ( (int)ApplicationVersion::ParseVersionString((ApplicationVersion *)v34) < 0 )
        goto LABEL_68;
      v22 = (struct ApplicationVersion *)(this + 10);
      v23 = (ApplicationVersion *)v34;
LABEL_48:
      if ( ApplicationVersion::IsThisVersionGreaterThanMe(v23, v22) )
        goto LABEL_68;
      ++v9;
      goto LABEL_66;
    }
    if ( !wcscmp(ValueName, L"Minimum File Version") )
    {
      IsAString = VerifyThisIsAString(L"Minimum File Version", Type);
      if ( IsAString < 0 )
        goto LABEL_67;
      if ( !this[10] && (int)ApplicationIdentity::FetchFileVersion((ApplicationIdentity *)this) < 0
        || (v35 = 0, v34[0] = v7, (int)ApplicationVersion::ParseVersionString((ApplicationVersion *)v34) < 0) )
      {
LABEL_68:
        v5 = 1;
        goto LABEL_71;
      }
      v22 = (struct ApplicationVersion *)v34;
      v23 = (ApplicationVersion *)(this + 10);
      goto LABEL_48;
    }
    if ( !wcscmp(ValueName, L"File Size") )
    {
      IsAString = VerifyThisIsADWORD(L"File Size", Type);
      if ( IsAString < 0 )
        goto LABEL_67;
      v24 = *(_DWORD *)v7;
      if ( !*((_DWORD *)this + 18) )
        ApplicationIdentity::SetSizeAndModifiedData((ApplicationIdentity *)this);
      v15 = v24 == *((_DWORD *)this + 18);
    }
    else if ( !wcscmp(ValueName, L"Date Modified High") )
    {
      IsAString = VerifyThisIsADWORD(L"Date Modified High", Type);
      if ( IsAString < 0 )
        goto LABEL_67;
      v25 = *(_DWORD *)v7;
      if ( !*((_DWORD *)this + 16) )
        ApplicationIdentity::SetSizeAndModifiedData((ApplicationIdentity *)this);
      v15 = *((_DWORD *)this + 16) == v25;
    }
    else
    {
      if ( wcscmp(ValueName, L"Date Modified Low") )
        goto LABEL_66;
      IsAString = VerifyThisIsADWORD(L"Date Modified Low", Type);
      if ( IsAString < 0 )
      {
LABEL_67:
        v5 = IsAString;
        goto LABEL_71;
      }
      v26 = *(_DWORD *)v7;
      if ( !*((_DWORD *)this + 17) )
        ApplicationIdentity::SetSizeAndModifiedData((ApplicationIdentity *)this);
      v15 = *((_DWORD *)this + 17) == v26;
    }
LABEL_65:
    if ( !v15 )
      goto LABEL_68;
LABEL_66:
    cchValueName = 30;
    cbData = cbMaxValueLen;
    ++v8;
  }
  if ( v9 == 1 )
  {
    ReportAppCompatError((wchar_t *)L"%s had a match, but didn't list both the min and max version numbers", this[1]);
    v5 = -2147467259;
    goto LABEL_71;
  }
  Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&v32);
  return 0;
}

```

## disassembly

```asm
0x1800325d4  mov     [rsp-8+arg_10], rbx
0x1800325d9  push    rbp
0x1800325da  push    rsi
0x1800325db  push    rdi
0x1800325dc  push    r12
0x1800325de  push    r13
0x1800325e0  push    r14
0x1800325e2  push    r15
0x1800325e4  lea     rbp, [rsp-27h]
0x1800325e9  sub     rsp, 0F0h
0x1800325f0  mov     rax, cs:__security_cookie
0x1800325f7  xor     rax, rsp
0x1800325fa  mov     [rbp+57h+var_40], rax
0x1800325fe  mov     r12, rdx
0x180032601  mov     rdi, rcx
0x180032604  mov     [rbp+57h+cchValueName], 1Eh
0x18003260b  xor     r13d, r13d
0x18003260e  mov     [rbp+57h+var_B0], r13
0x180032612  mov     [rbp+57h+var_A8], r13d
0x180032616  mov     [rbp+57h+cbMaxValueLen], r13d
0x18003261a  mov     [rbp+57h+cbData], r13d
0x18003261e  lea     r14d, [r13+1]
0x180032622  mov     [rbp+57h+Type], r14d
0x180032626  mov     [rsp+120h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18003262b  mov     [rsp+120h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x180032630  lea     rax, [rbp+57h+cbMaxValueLen]
0x180032634  mov     [rsp+120h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x180032639  mov     [rsp+120h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x18003263e  mov     [rsp+120h+lpcValues], r13; lpcValues
0x180032643  mov     [rsp+120h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x180032648  mov     [rsp+120h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x18003264d  mov     [rsp+120h+lpcSubKeys], r13; lpcSubKeys
0x180032652  xor     r9d, r9d; lpReserved
0x180032655  xor     r8d, r8d; lpcchClass
0x180032658  xor     edx, edx; lpClass
0x18003265a  mov     rcx, r12; hKey
0x18003265d  call    cs:__imp_RegQueryInfoKeyW
0x180032663  mov     ebx, eax
0x180032665  test    eax, eax
0x180032667  jz      short loc_18003267D
0x180032669  jle     loc_180032A1E
0x18003266f  movzx   ebx, ax
0x180032672  or      ebx, 80070000h
0x180032678  jmp     loc_180032A1E
0x18003267d  mov     ecx, [rbp+57h+cbMaxValueLen]
0x180032680  shr     rcx, 1
0x180032683  mov     eax, 2
0x180032688  mul     rcx
0x18003268b  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180032692  cmovb   rax, rcx
0x180032696  mov     rcx, rax; unsigned __int64
0x180032699  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x18003269e  mov     rsi, rax
0x1800326a1  mov     [rbp+57h+var_B0], rax
0x1800326a5  test    rax, rax
0x1800326a8  jz      loc_180032A38
0x1800326ae  mov     [rbp+57h+var_A8], r14d
0x1800326b2  mov     r15d, r13d
0x1800326b5  mov     r14d, r13d
0x1800326b8  mov     ecx, [rbp+57h+cbMaxValueLen]
0x1800326bb  mov     [rbp+57h+cbData], ecx
0x1800326be  lea     rax, [rbp+57h+cbData]
0x1800326c2  mov     [rsp+120h+lpcValues], rax; lpcbData
0x1800326c7  mov     [rsp+120h+lpcbMaxClassLen], rsi; lpData
0x1800326cc  lea     rax, [rbp+57h+Type]
0x1800326d0  mov     [rsp+120h+lpcbMaxSubKeyLen], rax; lpType
0x1800326d5  mov     [rsp+120h+lpcSubKeys], r13; lpReserved
0x1800326da  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x1800326de  lea     r8, [rbp+57h+ValueName]; lpValueName
0x1800326e2  mov     edx, r15d; dwIndex
0x1800326e5  mov     rcx, r12; hKey
0x1800326e8  call    cs:__imp_RegEnumValueW
0x1800326ee  test    eax, eax
0x1800326f0  jnz     loc_180032A03
0x1800326f6  lea     rdx, aCompany; "Company"
0x1800326fd  lea     rcx, [rbp+57h+ValueName]; String1
0x180032701  call    wcscmp
0x180032706  test    eax, eax
0x180032708  jnz     short loc_18003276B
0x18003270a  mov     edx, [rbp+57h+Type]; unsigned int
0x18003270d  lea     rcx, aCompany; "Company"
0x180032714  call    ?VerifyThisIsAString@@YAJPEBGK@Z; VerifyThisIsAString(ushort const *,ulong)
0x180032719  test    eax, eax
0x18003271b  js      loc_1800329F8
0x180032721  lea     rbx, [rdi+18h]
0x180032725  cmp     [rbx], r13
0x180032728  jnz     short loc_18003273C
0x18003272a  mov     r8, rbx; unsigned __int16 **
0x18003272d  lea     rdx, aCompanyname; "CompanyName"
0x180032734  mov     rcx, rdi; this
0x180032737  call    ?FetchResourceString@ApplicationIdentity@@AEAAJPEAGPEAPEAG@Z; ApplicationIdentity::FetchResourceString(ushort *,ushort * *)
0x18003273c  mov     rcx, [rbx]
0x18003273f  test    rcx, rcx
0x180032742  jz      loc_1800329FC
0x180032748  mov     rax, rsi
0x18003274b  sub     rcx, rsi
0x18003274e  movzx   r8d, word ptr [rax]
0x180032752  movzx   edx, word ptr [rax+rcx]
0x180032756  sub     r8d, edx
0x180032759  jnz     short loc_180032763
0x18003275b  add     rax, 2
0x18003275f  test    edx, edx
0x180032761  jnz     short loc_18003274E
0x180032763  test    r8d, r8d
0x180032766  jmp     loc_1800329E1
0x18003276b  lea     rdx, aProductName; "Product Name"
0x180032772  lea     rcx, [rbp+57h+ValueName]; String1
0x180032776  call    wcscmp
0x18003277b  test    eax, eax
0x18003277d  jnz     short loc_1800327DA
0x18003277f  mov     edx, [rbp+57h+Type]; unsigned int
0x180032782  lea     rcx, aProductName; "Product Name"
0x180032789  call    ?VerifyThisIsAString@@YAJPEBGK@Z; VerifyThisIsAString(ushort const *,ulong)
0x18003278e  test    eax, eax
0x180032790  js      loc_1800329F8
0x180032796  lea     rbx, [rdi+20h]
0x18003279a  cmp     [rbx], r13
0x18003279d  jnz     short loc_1800327B1
0x18003279f  mov     r8, rbx; unsigned __int16 **
0x1800327a2  lea     rdx, aProductname; "ProductName"
0x1800327a9  mov     rcx, rdi; this
0x1800327ac  call    ?FetchResourceString@ApplicationIdentity@@AEAAJPEAGPEAPEAG@Z; ApplicationIdentity::FetchResourceString(ushort *,ushort * *)
0x1800327b1  mov     rcx, [rbx]
0x1800327b4  test    rcx, rcx
0x1800327b7  jz      loc_1800329FC
0x1800327bd  mov     rax, rsi
0x1800327c0  sub     rcx, rsi
0x1800327c3  movzx   r8d, word ptr [rax]
0x1800327c7  movzx   edx, word ptr [rax+rcx]
0x1800327cb  sub     r8d, edx
0x1800327ce  jnz     short loc_180032763
0x1800327d0  add     rax, 2
0x1800327d4  test    edx, edx
0x1800327d6  jnz     short loc_1800327C3
0x1800327d8  jmp     short loc_180032763
0x1800327da  lea     rdx, aInternalName; "Internal Name"
0x1800327e1  lea     rcx, [rbp+57h+ValueName]; String1
0x1800327e5  call    wcscmp
0x1800327ea  test    eax, eax
0x1800327ec  jnz     short loc_180032850
0x1800327ee  mov     edx, [rbp+57h+Type]; unsigned int
0x1800327f1  lea     rcx, aInternalName; "Internal Name"
0x1800327f8  call    ?VerifyThisIsAString@@YAJPEBGK@Z; VerifyThisIsAString(ushort const *,ulong)
0x1800327fd  test    eax, eax
0x1800327ff  js      loc_1800329F8
0x180032805  lea     rbx, [rdi+28h]
0x180032809  cmp     [rbx], r13
0x18003280c  jnz     short loc_180032820
0x18003280e  mov     r8, rbx; unsigned __int16 **
0x180032811  lea     rdx, aInternalname; "InternalName"
0x180032818  mov     rcx, rdi; this
0x18003281b  call    ?FetchResourceString@ApplicationIdentity@@AEAAJPEAGPEAPEAG@Z; ApplicationIdentity::FetchResourceString(ushort *,ushort * *)
0x180032820  mov     rcx, [rbx]
0x180032823  test    rcx, rcx
0x180032826  jz      loc_1800329FC
0x18003282c  mov     rax, rsi
0x18003282f  sub     rcx, rsi
0x180032832  movzx   r8d, word ptr [rax]
0x180032836  movzx   edx, word ptr [rax+rcx]
0x18003283a  sub     r8d, edx
0x18003283d  jnz     loc_180032763
0x180032843  add     rax, 2
0x180032847  test    edx, edx
0x180032849  jnz     short loc_180032832
0x18003284b  jmp     loc_180032763
0x180032850  lea     rdx, aMaximumFileVer; "Maximum File Version"
0x180032857  lea     rcx, [rbp+57h+ValueName]; String1
0x18003285b  call    wcscmp
0x180032860  test    eax, eax
0x180032862  jnz     short loc_1800328B4
0x180032864  mov     edx, [rbp+57h+Type]; unsigned int
0x180032867  lea     rcx, aMaximumFileVer; "Maximum File Version"
0x18003286e  call    ?VerifyThisIsAString@@YAJPEBGK@Z; VerifyThisIsAString(ushort const *,ulong)
0x180032873  test    eax, eax
0x180032875  js      loc_1800329F8
0x18003287b  cmp     [rdi+50h], r13
0x18003287f  jnz     short loc_180032891
0x180032881  mov     rcx, rdi; this
0x180032884  call    ?FetchFileVersion@ApplicationIdentity@@AEAAJXZ; ApplicationIdentity::FetchFileVersion(void)
0x180032889  test    eax, eax
0x18003288b  js      loc_1800329FC
0x180032891  mov     [rbp+57h+var_88], r13d
0x180032895  mov     [rbp+57h+var_A0], rsi
0x180032899  lea     rcx, [rbp+57h+var_A0]; this
0x18003289d  call    ?ParseVersionString@ApplicationVersion@@QEAAJXZ; ApplicationVersion::ParseVersionString(void)
0x1800328a2  test    eax, eax
0x1800328a4  js      loc_1800329FC
0x1800328aa  lea     rdx, [rdi+50h]
0x1800328ae  lea     rcx, [rbp+57h+var_A0]
0x1800328b2  jmp     short loc_180032916
0x1800328b4  lea     rdx, aMinimumFileVer; "Minimum File Version"
0x1800328bb  lea     rcx, [rbp+57h+ValueName]; String1
0x1800328bf  call    wcscmp
0x1800328c4  test    eax, eax
0x1800328c6  jnz     short loc_18003292B
0x1800328c8  mov     edx, [rbp+57h+Type]; unsigned int
0x1800328cb  lea     rcx, aMinimumFileVer; "Minimum File Version"
0x1800328d2  call    ?VerifyThisIsAString@@YAJPEBGK@Z; VerifyThisIsAString(ushort const *,ulong)
0x1800328d7  test    eax, eax
0x1800328d9  js      loc_1800329F8
0x1800328df  cmp     [rdi+50h], r13
0x1800328e3  jnz     short loc_1800328F5
0x1800328e5  mov     rcx, rdi; this
0x1800328e8  call    ?FetchFileVersion@ApplicationIdentity@@AEAAJXZ; ApplicationIdentity::FetchFileVersion(void)
0x1800328ed  test    eax, eax
0x1800328ef  js      loc_1800329FC
0x1800328f5  mov     [rbp+57h+var_88], r13d
0x1800328f9  mov     [rbp+57h+var_A0], rsi
0x1800328fd  lea     rcx, [rbp+57h+var_A0]; this
0x180032901  call    ?ParseVersionString@ApplicationVersion@@QEAAJXZ; ApplicationVersion::ParseVersionString(void)
0x180032906  test    eax, eax
0x180032908  js      loc_1800329FC
0x18003290e  lea     rdx, [rbp+57h+var_A0]; struct ApplicationVersion *
0x180032912  lea     rcx, [rdi+50h]; this
0x180032916  call    ?IsThisVersionGreaterThanMe@ApplicationVersion@@QEAAHPEAV1@@Z; ApplicationVersion::IsThisVersionGreaterThanMe(ApplicationVersion *)
0x18003291b  test    eax, eax
0x18003291d  jnz     loc_1800329FC
0x180032923  inc     r14d
0x180032926  jmp     loc_1800329E3
0x18003292b  lea     rdx, aFileSize; "File Size"
0x180032932  lea     rcx, [rbp+57h+ValueName]; String1
0x180032936  call    wcscmp
0x18003293b  test    eax, eax
0x18003293d  jnz     short loc_18003296B
0x18003293f  mov     edx, [rbp+57h+Type]; unsigned int
0x180032942  lea     rcx, aFileSize; "File Size"
0x180032949  call    ?VerifyThisIsADWORD@@YAJPEBGK@Z; VerifyThisIsADWORD(ushort const *,ulong)
0x18003294e  test    eax, eax
0x180032950  js      loc_1800329F8
0x180032956  mov     ebx, [rsi]
0x180032958  cmp     [rdi+48h], r13d
0x18003295c  jnz     short loc_180032966
0x18003295e  mov     rcx, rdi; this
0x180032961  call    ?SetSizeAndModifiedData@ApplicationIdentity@@AEAAJXZ; ApplicationIdentity::SetSizeAndModifiedData(void)
0x180032966  cmp     ebx, [rdi+48h]
0x180032969  jmp     short loc_1800329E1
0x18003296b  lea     rdx, aDateModifiedHi; "Date Modified High"
0x180032972  lea     rcx, [rbp+57h+ValueName]; String1
0x180032976  call    wcscmp
0x18003297b  test    eax, eax
0x18003297d  jnz     short loc_1800329A7
0x18003297f  mov     edx, [rbp+57h+Type]; unsigned int
0x180032982  lea     rcx, aDateModifiedHi; "Date Modified High"
0x180032989  call    ?VerifyThisIsADWORD@@YAJPEBGK@Z; VerifyThisIsADWORD(ushort const *,ulong)
0x18003298e  test    eax, eax
0x180032990  js      short loc_1800329F8
0x180032992  mov     ebx, [rsi]
0x180032994  cmp     [rdi+40h], r13d
0x180032998  jnz     short loc_1800329A2
0x18003299a  mov     rcx, rdi; this
0x18003299d  call    ?SetSizeAndModifiedData@ApplicationIdentity@@AEAAJXZ; ApplicationIdentity::SetSizeAndModifiedData(void)
0x1800329a2  cmp     [rdi+40h], ebx
0x1800329a5  jmp     short loc_1800329E1
0x1800329a7  lea     rdx, aDateModifiedLo; "Date Modified Low"
0x1800329ae  lea     rcx, [rbp+57h+ValueName]; String1
0x1800329b2  call    wcscmp
0x1800329b7  test    eax, eax
0x1800329b9  jnz     short loc_1800329E3
0x1800329bb  mov     edx, [rbp+57h+Type]; unsigned int
0x1800329be  lea     rcx, aDateModifiedLo; "Date Modified Low"
0x1800329c5  call    ?VerifyThisIsADWORD@@YAJPEBGK@Z; VerifyThisIsADWORD(ushort const *,ulong)
0x1800329ca  test    eax, eax
0x1800329cc  js      short loc_1800329F8
0x1800329ce  mov     ebx, [rsi]
0x1800329d0  cmp     [rdi+44h], r13d
0x1800329d4  jnz     short loc_1800329DE
0x1800329d6  mov     rcx, rdi; this
0x1800329d9  call    ?SetSizeAndModifiedData@ApplicationIdentity@@AEAAJXZ; ApplicationIdentity::SetSizeAndModifiedData(void)
0x1800329de  cmp     [rdi+44h], ebx
0x1800329e1  jnz     short loc_1800329FC
0x1800329e3  mov     [rbp+57h+cchValueName], 1Eh
0x1800329ea  mov     eax, [rbp+57h+cbMaxValueLen]
0x1800329ed  mov     [rbp+57h+cbData], eax
0x1800329f0  inc     r15d
0x1800329f3  jmp     loc_1800326BE
0x1800329f8  mov     ebx, eax
0x1800329fa  jmp     short loc_180032A1E
0x1800329fc  mov     ebx, 1
0x180032a01  jmp     short loc_180032A1E
0x180032a03  cmp     r14d, 1
0x180032a07  jnz     short loc_180032A2B
0x180032a09  mov     rdx, [rdi+8]
0x180032a0d  lea     rcx, aSHadAMatchButD; "%s had a match, but didn't list both th"...
0x180032a14  call    ?ReportAppCompatError@@YAXPEAGZZ; ReportAppCompatError(ushort *,...)
0x180032a19  mov     ebx, 80004005h
0x180032a1e  lea     rcx, [rbp+57h+var_B0]
0x180032a22  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x180032a27  mov     eax, ebx
0x180032a29  jmp     short loc_180032A46
0x180032a2b  lea     rcx, [rbp+57h+var_B0]
0x180032a2f  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x180032a34  xor     eax, eax
0x180032a36  jmp     short loc_180032A46
0x180032a38  lea     rcx, [rbp+57h+var_B0]
0x180032a3c  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x180032a41  mov     eax, 8007000Eh
0x180032a46  mov     rcx, [rbp+57h+var_40]
0x180032a4a  xor     rcx, rsp; StackCookie
0x180032a4d  call    __security_check_cookie
0x180032a52  mov     rbx, [rsp+120h+arg_10]
  ... truncated ...
```
