# COledbEnum::Next(RowBinding *)

- ea: `0x180016cf0`
- end: `0x18001721a`
- name: `?Next@COledbEnum@@QEAAJPEAURowBinding@@@Z`
- size: `1322`
- prototype: `int(COledbEnum *__hidden this, struct RowBinding *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800168e4`
- `0x18003ca20`

## callees

- `0x180016cf0`
- `0x180019780`
- `0x18002ec26`
- `0x18007e6d6`
- `0x18007e700`

## import_xrefs

- `ADVAPI32!RegEnumKeyExW` at `0x180016d74`
- `ADVAPI32!RegEnumKeyExW` at `0x180016df6`
- `ADVAPI32!RegEnumKeyExW` at `0x180016e8a`
- `ADVAPI32!RegEnumKeyExW` at `0x180016d74`
- `ADVAPI32!RegEnumKeyExW` at `0x180016df6`
- `ADVAPI32!RegEnumKeyExW` at `0x180016e8a`
- `ADVAPI32!RegQueryValueExW` at `0x180016fb2`
- `ADVAPI32!RegQueryValueExW` at `0x1800170c1`
- `ADVAPI32!RegQueryValueExW` at `0x180017141`
- `ADVAPI32!RegQueryValueExW` at `0x1800171be`
- `ADVAPI32!RegQueryValueExW` at `0x180016fb2`
- `ADVAPI32!RegQueryValueExW` at `0x1800170c1`
- `ADVAPI32!RegQueryValueExW` at `0x180017141`
- `ADVAPI32!RegQueryValueExW` at `0x1800171be`
- `ADVAPI32!RegOpenKeyExW` at `0x180016db8`
- `ADVAPI32!RegOpenKeyExW` at `0x180016eed`
- `ADVAPI32!RegOpenKeyExW` at `0x180016f28`
- `ADVAPI32!RegOpenKeyExW` at `0x180016f63`
- `ADVAPI32!RegOpenKeyExW` at `0x180016db8`
- `ADVAPI32!RegOpenKeyExW` at `0x180016eed`
- `ADVAPI32!RegOpenKeyExW` at `0x180016f28`
- `ADVAPI32!RegOpenKeyExW` at `0x180016f63`
- `ADVAPI32!RegCloseKey` at `0x180016d9a`
- `ADVAPI32!RegCloseKey` at `0x180016d9a`

## pseudocode

```c
__int64 __fastcall COledbEnum::Next(COledbEnum *this, struct RowBinding *a2)
{
  DWORD v4; // edx
  HKEY v5; // rcx
  LSTATUS v6; // eax
  HKEY v7; // rcx
  HKEY *v8; // rdi
  HKEY v9; // rcx
  DWORD v10; // ebx
  int v11; // esi
  HKEY v12; // rcx
  HKEY *v14; // rax
  HKEY *v15; // rax
  HKEY *v16; // rax
  HKEY v17; // rcx
  unsigned __int64 v18; // rdi
  unsigned __int64 v19; // rax
  __int64 v20; // rbx
  unsigned __int64 v21; // rax
  __int64 v22; // rbx
  unsigned __int64 v23; // rax
  __int64 v24; // rbx
  int v25; // eax
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  BYTE Data[2]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Name[256]; // [rsp+250h] [rbp+150h] BYREF

  if ( !*(_QWORD *)this )
    return 1;
  cchName = 0;
  while ( 1 )
  {
    while ( !*((_DWORD *)this + 10) )
    {
      v4 = *((_DWORD *)this + 12);
      v5 = *(HKEY *)this;
      *((_DWORD *)this + 11) = 64;
      v6 = RegEnumKeyExW(v5, v4, (LPWSTR)this + 26, (LPDWORD)this + 11, 0, 0, 0, 0);
      ++*((_DWORD *)this + 12);
      if ( v6 != 234 )
      {
        if ( v6 )
          return 1;
        v7 = (HKEY)*((_QWORD *)this + 1);
        v8 = (HKEY *)((char *)this + 8);
        if ( v7 )
        {
          RegCloseKey(v7);
          *v8 = 0;
        }
        if ( !RegOpenKeyExW(*(HKEY *)this, (LPCWSTR)this + 26, 0, 0x20019u, (PHKEY)this + 1) )
        {
          v9 = *v8;
          v10 = 0;
          v11 = 0;
          cchName = 255;
          if ( !RegEnumKeyExW(v9, 0, Name, &cchName, 0, 0, 0, 0) )
          {
            do
            {
              if ( v11 >= 3 )
                break;
              if ( !wcscmp_0(Name, L"OLE DB Provider") )
              {
                v14 = (HKEY *)HKAuto::operator&((char *)this + 16);
                if ( !RegOpenKeyExW(*v8, L"OLE DB Provider", 0, 0x20019u, v14) )
                {
                  *((_DWORD *)this + 10) |= 1u;
                  ++v11;
                }
              }
              if ( !wcscmp_0(Name, L"OLE DB Enumerator") )
              {
                v15 = (HKEY *)HKAuto::operator&((char *)this + 24);
                if ( !RegOpenKeyExW(*v8, L"OLE DB Enumerator", 0, 0x20019u, v15) )
                {
                  *((_DWORD *)this + 10) |= 2u;
                  ++v11;
                }
              }
              if ( !wcscmp_0(Name, L"OLE DB MD Provider") )
              {
                v16 = (HKEY *)HKAuto::operator&((char *)this + 32);
                if ( !RegOpenKeyExW(*v8, L"OLE DB MD Provider", 0, 0x20019u, v16) )
                {
                  *((_DWORD *)this + 10) |= 4u;
                  ++v11;
                }
              }
              v12 = *v8;
              ++v10;
              cchName = 255;
            }
            while ( !RegEnumKeyExW(v12, v10, Name, &cchName, 0, 0, 0, 0) );
          }
        }
      }
    }
    v17 = (HKEY)*((_QWORD *)this + 1);
    Type = 0;
    cbData = 512;
    *(_WORD *)Data = 0;
    if ( !RegQueryValueExW(v17, 0, 0, &Type, Data, &cbData) )
      break;
    *((_DWORD *)this + 10) = 0;
  }
  v18 = -1;
  v19 = -1;
  do
    ++v19;
  while ( *(_WORD *)&Data[2 * v19] );
  if ( v19 > 0xFF )
    v19 = 255;
  v20 = 2 * v19;
  memcpy_0(a2, Data, 2 * v19);
  *(_WORD *)((char *)a2 + v20) = 0;
  v21 = -1;
  *((_QWORD *)a2 + 64) = v20;
  do
    ++v21;
  while ( *((_WORD *)this + v21 + 26) );
  if ( v21 > 0xFF )
    v21 = 255;
  v22 = 2 * v21;
  memcpy_0((char *)a2 + 520, (char *)this + 52, 2 * v21);
  *(_WORD *)((char *)a2 + v22 + 520) = 0;
  v23 = -1;
  *((_QWORD *)a2 + 129) = v22;
  *((_WORD *)a2 + 781) = 0;
  do
    ++v23;
  while ( *((_WORD *)this + v23 + 26) );
  if ( v23 > 0xFF )
    v23 = 255;
  v24 = 2 * v23;
  memcpy_0((char *)a2 + 1564, (char *)this + 52, 2 * v23);
  *(_WORD *)((char *)a2 + v24 + 1564) = 0;
  *((_QWORD *)a2 + 260) = v24;
  v25 = *((_DWORD *)this + 10);
  cbData = 512;
  *(_WORD *)Data = 0;
  if ( (v25 & 1) != 0 )
  {
    RegQueryValueExW(*((HKEY *)this + 2), 0, 0, &Type, Data, &cbData);
    do
      ++v18;
    while ( *(_WORD *)&Data[2 * v18] );
    if ( v18 > 0xFF )
      v18 = 255;
    memcpy_0((char *)a2 + 1040, Data, 2 * v18);
    *((_WORD *)a2 + v18 + 520) = 0;
    *((_QWORD *)a2 + 194) = 2 * v18;
    *((_WORD *)a2 + 780) = 1;
    *((_DWORD *)this + 10) &= ~1u;
  }
  else if ( (v25 & 2) != 0 )
  {
    RegQueryValueExW(*((HKEY *)this + 3), 0, 0, &Type, Data, &cbData);
    do
      ++v18;
    while ( *(_WORD *)&Data[2 * v18] );
    if ( v18 > 0xFF )
      v18 = 255;
    memcpy_0((char *)a2 + 1040, Data, 2 * v18);
    *((_WORD *)a2 + v18 + 520) = 0;
    *((_QWORD *)a2 + 194) = 2 * v18;
    *((_WORD *)a2 + 780) = 2;
    *((_DWORD *)this + 10) &= ~2u;
  }
  else if ( (v25 & 4) != 0 )
  {
    RegQueryValueExW(*((HKEY *)this + 4), 0, 0, &Type, Data, &cbData);
    do
      ++v18;
    while ( *(_WORD *)&Data[2 * v18] );
    if ( v18 > 0xFF )
      v18 = 255;
    memcpy_0((char *)a2 + 1040, Data, 2 * v18);
    *((_WORD *)a2 + v18 + 520) = 0;
    *((_QWORD *)a2 + 194) = 2 * v18;
    *((_WORD *)a2 + 780) = 3;
    *((_DWORD *)this + 10) &= ~4u;
  }
  return 0;
}

```

## disassembly

```asm
0x180016cf0  mov     [rsp-8+arg_10], rbx
0x180016cf5  push    rbp
0x180016cf6  push    rsi
0x180016cf7  push    rdi
0x180016cf8  push    r12
0x180016cfa  push    r13
0x180016cfc  push    r14
0x180016cfe  push    r15
0x180016d00  lea     rbp, [rsp-360h]
0x180016d08  sub     rsp, 460h
0x180016d0f  mov     rax, cs:__security_cookie
0x180016d16  xor     rax, rsp
0x180016d19  mov     [rbp+390h+var_40], rax
0x180016d20  cmp     qword ptr [rcx], 0
0x180016d24  mov     r13, rdx
0x180016d27  mov     r14, rcx
0x180016d2a  jz      loc_180016E9D
0x180016d30  xor     r12d, r12d
0x180016d33  mov     r15d, 0FFh
0x180016d39  mov     [rsp+490h+cchName], r12d
0x180016d3e  xchg    ax, ax
0x180016d40  cmp     [r14+28h], r12d
0x180016d44  jnz     loc_180016F7D
0x180016d4a  mov     edx, [r14+30h]; dwIndex
0x180016d4e  lea     r9, [r14+2Ch]; lpcchName
0x180016d52  mov     rcx, [r14]; hKey
0x180016d55  lea     r8, [r14+34h]; lpName
0x180016d59  mov     [rsp+490h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180016d5e  mov     [rsp+490h+lpcchClass], r12; lpcchClass
0x180016d63  mov     [rsp+490h+lpClass], r12; lpClass
0x180016d68  mov     [rsp+490h+lpReserved], r12; lpReserved
0x180016d6d  mov     dword ptr [r9], 40h ; '@'
0x180016d74  call    cs:__imp_RegEnumKeyExW
0x180016d7a  inc     dword ptr [r14+30h]
0x180016d7e  cmp     eax, 0EAh
0x180016d83  jz      short loc_180016D40
0x180016d85  test    eax, eax
0x180016d87  jnz     loc_180016E9D
0x180016d8d  mov     rcx, [r14+8]; hKey
0x180016d91  lea     rdi, [r14+8]
0x180016d95  test    rcx, rcx
0x180016d98  jz      short loc_180016DA3
0x180016d9a  call    cs:__imp_RegCloseKey
0x180016da0  mov     [rdi], r12
0x180016da3  mov     rcx, [r14]; hKey
0x180016da6  lea     rdx, [r14+34h]; lpSubKey
0x180016daa  mov     r9d, 20019h; samDesired
0x180016db0  mov     [rsp+490h+lpReserved], rdi; phkResult
0x180016db5  xor     r8d, r8d; ulOptions
0x180016db8  call    cs:__imp_RegOpenKeyExW
0x180016dbe  test    eax, eax
0x180016dc0  jnz     loc_180016D40
0x180016dc6  mov     rcx, [rdi]; hKey
0x180016dc9  lea     r9, [rsp+490h+cchName]; lpcchName
0x180016dce  mov     [rsp+490h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180016dd3  lea     r8, [rbp+390h+Name]; lpName
0x180016dda  mov     [rsp+490h+lpcchClass], r12; lpcchClass
0x180016ddf  xor     edx, edx; dwIndex
0x180016de1  mov     [rsp+490h+lpClass], r12; lpClass
0x180016de6  mov     ebx, r12d
0x180016de9  mov     [rsp+490h+lpReserved], r12; lpReserved
0x180016dee  mov     esi, r12d
0x180016df1  mov     [rsp+490h+cchName], r15d
0x180016df6  call    cs:__imp_RegEnumKeyExW
0x180016dfc  test    eax, eax
0x180016dfe  jnz     loc_180016D40
0x180016e04  cmp     esi, 3
0x180016e07  jge     loc_180016D40
0x180016e0d  lea     rdx, aOleDbProvider; "OLE DB Provider"
0x180016e14  lea     rcx, [rbp+390h+Name]; String1
0x180016e1b  call    wcscmp_0
0x180016e20  test    eax, eax
0x180016e22  jz      loc_180016ECC
0x180016e28  lea     rdx, aOleDbEnumerato; "OLE DB Enumerator"
0x180016e2f  lea     rcx, [rbp+390h+Name]; String1
0x180016e36  call    wcscmp_0
0x180016e3b  test    eax, eax
0x180016e3d  jz      loc_180016F07
0x180016e43  lea     rdx, aOleDbMdProvide; "OLE DB MD Provider"
0x180016e4a  lea     rcx, [rbp+390h+Name]; String1
0x180016e51  call    wcscmp_0
0x180016e56  test    eax, eax
0x180016e58  jz      loc_180016F42
0x180016e5e  mov     rcx, [rdi]; hKey
0x180016e61  lea     r9, [rsp+490h+cchName]; lpcchName
0x180016e66  mov     [rsp+490h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180016e6b  lea     r8, [rbp+390h+Name]; lpName
0x180016e72  mov     [rsp+490h+lpcchClass], r12; lpcchClass
0x180016e77  inc     ebx
0x180016e79  mov     [rsp+490h+lpClass], r12; lpClass
0x180016e7e  mov     edx, ebx; dwIndex
0x180016e80  mov     [rsp+490h+lpReserved], r12; lpReserved
0x180016e85  mov     [rsp+490h+cchName], r15d
0x180016e8a  call    cs:__imp_RegEnumKeyExW
0x180016e90  test    eax, eax
0x180016e92  jz      loc_180016E04
0x180016e98  jmp     loc_180016D40
0x180016e9d  mov     eax, 1
0x180016ea2  mov     rcx, [rbp+390h+var_40]
0x180016ea9  xor     rcx, rsp; StackCookie
0x180016eac  call    __security_check_cookie
0x180016eb1  mov     rbx, [rsp+490h+arg_10]
0x180016eb9  add     rsp, 460h
0x180016ec0  pop     r15
0x180016ec2  pop     r14
0x180016ec4  pop     r13
0x180016ec6  pop     r12
0x180016ec8  pop     rdi
0x180016ec9  pop     rsi
0x180016eca  pop     rbp
0x180016ecb  retn
0x180016ecc  lea     rcx, [r14+10h]
0x180016ed0  call    ??IHKAuto@@QEAAPEAPEAUHKEY__@@XZ; HKAuto::operator&(void)
0x180016ed5  mov     rcx, [rdi]; hKey
0x180016ed8  lea     rdx, aOleDbProvider; "OLE DB Provider"
0x180016edf  mov     r9d, 20019h; samDesired
0x180016ee5  mov     [rsp+490h+lpReserved], rax; phkResult
0x180016eea  xor     r8d, r8d; ulOptions
0x180016eed  call    cs:__imp_RegOpenKeyExW
0x180016ef3  test    eax, eax
0x180016ef5  jnz     loc_180016E28
0x180016efb  or      dword ptr [r14+28h], 1
0x180016f00  inc     esi
0x180016f02  jmp     loc_180016E28
0x180016f07  lea     rcx, [r14+18h]
0x180016f0b  call    ??IHKAuto@@QEAAPEAPEAUHKEY__@@XZ; HKAuto::operator&(void)
0x180016f10  mov     rcx, [rdi]; hKey
0x180016f13  lea     rdx, aOleDbEnumerato; "OLE DB Enumerator"
0x180016f1a  mov     r9d, 20019h; samDesired
0x180016f20  mov     [rsp+490h+lpReserved], rax; phkResult
0x180016f25  xor     r8d, r8d; ulOptions
0x180016f28  call    cs:__imp_RegOpenKeyExW
0x180016f2e  test    eax, eax
0x180016f30  jnz     loc_180016E43
0x180016f36  or      dword ptr [r14+28h], 2
0x180016f3b  inc     esi
0x180016f3d  jmp     loc_180016E43
0x180016f42  lea     rcx, [r14+20h]
0x180016f46  call    ??IHKAuto@@QEAAPEAPEAUHKEY__@@XZ; HKAuto::operator&(void)
0x180016f4b  mov     rcx, [rdi]; hKey
0x180016f4e  lea     rdx, aOleDbMdProvide; "OLE DB MD Provider"
0x180016f55  mov     r9d, 20019h; samDesired
0x180016f5b  mov     [rsp+490h+lpReserved], rax; phkResult
0x180016f60  xor     r8d, r8d; ulOptions
0x180016f63  call    cs:__imp_RegOpenKeyExW
0x180016f69  test    eax, eax
0x180016f6b  jnz     loc_180016E5E
0x180016f71  or      dword ptr [r14+28h], 4
0x180016f76  inc     esi
0x180016f78  jmp     loc_180016E5E
0x180016f7d  mov     rcx, [r14+8]; hKey
0x180016f81  lea     rax, [rsp+490h+cbData]
0x180016f86  mov     [rsp+490h+lpClass], rax; lpcbData
0x180016f8b  lea     r9, [rsp+490h+Type]; lpType
0x180016f90  lea     rax, [rsp+490h+Data]
0x180016f95  mov     [rsp+490h+Type], r12d
0x180016f9a  xor     r8d, r8d; lpReserved
0x180016f9d  mov     [rsp+490h+lpReserved], rax; lpData
0x180016fa2  xor     edx, edx; lpValueName
0x180016fa4  mov     [rsp+490h+cbData], 200h
0x180016fac  mov     word ptr [rsp+490h+Data], r12w
0x180016fb2  call    cs:__imp_RegQueryValueExW
0x180016fb8  test    eax, eax
0x180016fba  jz      short loc_180016FC5
0x180016fbc  mov     [r14+28h], r12d
0x180016fc0  jmp     loc_180016D40
0x180016fc5  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x180016fcc  lea     rcx, [rsp+490h+Data]
0x180016fd1  mov     rax, rdi
0x180016fd4  inc     rax
0x180016fd7  cmp     [rcx+rax*2], r12w
0x180016fdc  jnz     short loc_180016FD4
0x180016fde  cmp     rax, r15
0x180016fe1  lea     rdx, [rsp+490h+Data]; Src
0x180016fe6  mov     rcx, r13; void *
0x180016fe9  cmova   eax, r15d
0x180016fed  lea     rbx, [rax+rax]
0x180016ff1  mov     r8, rbx; Size
0x180016ff4  call    memcpy_0
0x180016ff9  mov     [rbx+r13], r12w
0x180016ffe  mov     rax, rdi
0x180017001  mov     [r13+200h], rbx
0x180017008  inc     rax
0x18001700b  cmp     [r14+rax*2+34h], r12w
0x180017011  jnz     short loc_180017008
0x180017013  mov     rcx, r15
0x180017016  lea     rdx, [r14+34h]; Src
0x18001701a  cmp     rax, rcx
0x18001701d  cmova   eax, ecx
0x180017020  lea     rcx, [r13+208h]; void *
0x180017027  lea     rbx, [rax+rax]
0x18001702b  mov     r8, rbx; Size
0x18001702e  call    memcpy_0
0x180017033  mov     [rbx+r13+208h], r12w
0x18001703c  mov     rax, rdi
0x18001703f  mov     [r13+408h], rbx
0x180017046  mov     [r13+61Ah], r12w
0x18001704e  inc     rax
0x180017051  cmp     [r14+rax*2+34h], r12w
0x180017057  jnz     short loc_18001704E
0x180017059  mov     rcx, r15
0x18001705c  lea     rdx, [r14+34h]; Src
0x180017060  cmp     rax, rcx
0x180017063  cmova   eax, ecx
0x180017066  lea     rcx, [r13+61Ch]; void *
0x18001706d  lea     rbx, [rax+rax]
0x180017071  mov     r8, rbx; Size
0x180017074  call    memcpy_0
0x180017079  mov     [rbx+r13+61Ch], r12w
0x180017082  mov     [r13+820h], rbx
0x180017089  mov     eax, [r14+28h]
0x18001708d  mov     [rsp+490h+cbData], 200h
0x180017095  mov     word ptr [rsp+490h+Data], r12w
0x18001709b  test    al, 1
0x18001709d  jz      short loc_18001711B
0x18001709f  mov     rcx, [r14+10h]; hKey
0x1800170a3  lea     rax, [rsp+490h+cbData]
0x1800170a8  mov     [rsp+490h+lpClass], rax; lpcbData
0x1800170ad  lea     r9, [rsp+490h+Type]; lpType
0x1800170b2  lea     rax, [rsp+490h+Data]
0x1800170b7  xor     r8d, r8d; lpReserved
0x1800170ba  xor     edx, edx; lpValueName
0x1800170bc  mov     [rsp+490h+lpReserved], rax; lpData
0x1800170c1  call    cs:__imp_RegQueryValueExW
0x1800170c7  lea     rax, [rsp+490h+Data]
0x1800170cc  inc     rdi
0x1800170cf  cmp     [rax+rdi*2], r12w
0x1800170d4  jnz     short loc_1800170CC
0x1800170d6  mov     rax, r15
0x1800170d9  lea     rdx, [rsp+490h+Data]; Src
0x1800170de  cmp     rdi, rax
0x1800170e1  lea     rcx, [r13+410h]; void *
0x1800170e8  cmova   edi, eax
0x1800170eb  lea     rbx, [rdi+rdi]
0x1800170ef  mov     r8, rbx; Size
0x1800170f2  call    memcpy_0
0x1800170f7  mov     [rbx+r13+410h], r12w
0x180017100  mov     [r13+610h], rbx
0x180017107  mov     word ptr [r13+618h], 1
0x180017111  and     dword ptr [r14+28h], 0FFFFFFFEh
0x180017116  jmp     loc_180017213
0x18001711b  test    al, 2
0x18001711d  jz      short loc_180017198
0x18001711f  mov     rcx, [r14+18h]; hKey
0x180017123  lea     rax, [rsp+490h+cbData]
0x180017128  mov     [rsp+490h+lpClass], rax; lpcbData
0x18001712d  lea     r9, [rsp+490h+Type]; lpType
0x180017132  lea     rax, [rsp+490h+Data]
0x180017137  xor     r8d, r8d; lpReserved
0x18001713a  xor     edx, edx; lpValueName
0x18001713c  mov     [rsp+490h+lpReserved], rax; lpData
0x180017141  call    cs:__imp_RegQueryValueExW
0x180017147  lea     rax, [rsp+490h+Data]
0x18001714c  inc     rdi
0x18001714f  cmp     [rax+rdi*2], r12w
0x180017154  jnz     short loc_18001714C
0x180017156  mov     rax, r15
0x180017159  lea     rdx, [rsp+490h+Data]; Src
0x18001715e  cmp     rdi, rax
0x180017161  lea     rcx, [r13+410h]; void *
0x180017168  cmova   edi, eax
0x18001716b  lea     rbx, [rdi+rdi]
0x18001716f  mov     r8, rbx; Size
0x180017172  call    memcpy_0
0x180017177  mov     [rbx+r13+410h], r12w
0x180017180  mov     [r13+610h], rbx
0x180017187  mov     word ptr [r13+618h], 2
0x180017191  and     dword ptr [r14+28h], 0FFFFFFFDh
0x180017196  jmp     short loc_180017213
0x180017198  test    al, 4
0x18001719a  jz      short loc_180017213
0x18001719c  mov     rcx, [r14+20h]; hKey
0x1800171a0  lea     rax, [rsp+490h+cbData]
0x1800171a5  mov     [rsp+490h+lpClass], rax; lpcbData
0x1800171aa  lea     r9, [rsp+490h+Type]; lpType
0x1800171af  lea     rax, [rsp+490h+Data]
0x1800171b4  xor     r8d, r8d; lpReserved
0x1800171b7  xor     edx, edx; lpValueName
0x1800171b9  mov     [rsp+490h+lpReserved], rax; lpData
0x1800171be  call    cs:__imp_RegQueryValueExW
0x1800171c4  lea     rax, [rsp+490h+Data]
0x1800171c9  inc     rdi
0x1800171cc  cmp     [rax+rdi*2], r12w
0x1800171d1  jnz     short loc_1800171C9
0x1800171d3  mov     rax, r15
0x1800171d6  lea     rdx, [rsp+490h+Data]; Src
0x1800171db  cmp     rdi, rax
0x1800171de  lea     rcx, [r13+410h]; void *
0x1800171e5  cmova   edi, eax
0x1800171e8  lea     rbx, [rdi+rdi]
0x1800171ec  mov     r8, rbx; Size
0x1800171ef  call    memcpy_0
0x1800171f4  mov     [rbx+r13+410h], r12w
0x1800171fd  mov     [r13+610h], rbx
0x180017204  mov     word ptr [r13+618h], 3
0x18001720e  and     dword ptr [r14+28h], 0FFFFFFFBh
0x180017213  xor     eax, eax
0x180017215  jmp     loc_180016EA2
```
