# FindDarwinURL(char const *,char const *,CStr *)

- ea: `0x1800258c0`
- end: `0x180025a6f`
- name: `?FindDarwinURL@@YAHPEBD0PEAVCStr@@@Z`
- size: `431`
- prototype: `__int64 __fastcall(const char *, const char *, struct CStr *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800269d0`

## callees

- `0x180002a64`
- `0x180003fc0`
- `0x180004224`
- `0x18000f810`
- `0x1800115b0`
- `0x18002018c`
- `0x1800258c0`
- `0x180075c90`
- `0x180078010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180025926`
- `KERNEL32!GetProcAddress` at `0x180025926`
- `SHLWAPI!StrChrA` at `0x18002597b`
- `SHLWAPI!StrChrA` at `0x18002597b`

## string_xrefs

- `0x180025900`: `Msi.dll`
- `0x18002591c`: `MsiProvideQualifiedComponentA`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall FindDarwinURL(const char *a1, const char *a2, struct CStr *a3)
{
  HMODULE LibraryA; // rax
  int v7; // eax
  PCSTR v8; // rdi
  PSTR v9; // rax
  _BYTE *v10; // rbx
  __int64 v12; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v13; // [rsp+38h] [rbp-C8h] BYREF
  PCSTR pszStart; // [rsp+40h] [rbp-C0h] BYREF
  int v15; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v16[272]; // [rsp+50h] [rbp-B0h] BYREF

  if ( !pMsiProvideQualifiedComponent )
  {
    LibraryA = g_hmodMSI;
    if ( !g_hmodMSI )
    {
      LibraryA = IsolationAwareLoadLibraryA("Msi.dll");
      g_hmodMSI = LibraryA;
      if ( !LibraryA )
        return 0;
    }
    pMsiProvideQualifiedComponent = (unsigned int (*)(const char *, const char *, unsigned int, char *, unsigned int *))GetProcAddress(LibraryA, "MsiProvideQualifiedComponentA");
    if ( !pMsiProvideQualifiedComponent )
      return 0;
  }
  v15 = 260;
  CStr::CStr((CStr *)&pszStart, a1);
  v13 = 0;
  v7 = CStr::strlen((CStr *)&pszStart);
  v8 = pszStart;
  if ( pszStart[v7 - 1] == 125 )
  {
LABEL_10:
    CWStr::~CWStr((CWStr *)&v13);
    CWStr::~CWStr((CWStr *)&pszStart);
    return 0;
  }
  v9 = StrChrA(pszStart, 0x7Du);
  if ( v9 )
  {
    v10 = v9 + 1;
    CStr::operator=(&v13);
    *v10 = 0;
  }
  v12 = 0;
  CStr::operator=(&v12);
  CStr::operator+=(&v12, "\\");
  CStr::operator+=(&v12, a2);
  if ( (unsigned int)((__int64 (__fastcall *)(PCSTR, __int64, __int64, _BYTE *, int *))pMsiProvideQualifiedComponent)(
                       v8,
                       v12,
                       0xFFFFFFFFLL,
                       v16,
                       &v15) )
  {
    CWStr::~CWStr((CWStr *)&v12);
    goto LABEL_10;
  }
  CStr::operator=(a3);
  CWStr::~CWStr((CWStr *)&v12);
  CWStr::~CWStr((CWStr *)&v13);
  CWStr::~CWStr((CWStr *)&pszStart);
  return 1;
}

```

## disassembly

```asm
0x1800258c0  push    rbp
0x1800258c2  push    rbx
0x1800258c3  push    rsi
0x1800258c4  push    rdi
0x1800258c5  push    r14
0x1800258c7  lea     rbp, [rsp-70h]
0x1800258cc  sub     rsp, 170h
0x1800258d3  mov     rax, cs:__security_cookie
0x1800258da  xor     rax, rsp
0x1800258dd  mov     [rbp+90h+var_30], rax
0x1800258e1  mov     rsi, r8
0x1800258e4  mov     r14, rdx
0x1800258e7  mov     rbx, rcx
0x1800258ea  cmp     cs:?pMsiProvideQualifiedComponent@@3P6AIPEBD0KPEADPEAK@ZEA, 0; uint (*pMsiProvideQualifiedComponent)(char const *,char const *,ulong,char *,ulong *)
0x1800258f2  jnz     short loc_18002593C
0x1800258f4  mov     rax, cs:?g_hmodMSI@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hmodMSI
0x1800258fb  test    rax, rax
0x1800258fe  jnz     short loc_18002591C
0x180025900  lea     rcx, aMsiDll; "Msi.dll"
0x180025907  call    IsolationAwareLoadLibraryA
0x18002590c  mov     cs:?g_hmodMSI@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hmodMSI
0x180025913  test    rax, rax
0x180025916  jz      loc_180025A1E
0x18002591c  lea     rdx, aMsiprovidequal; "MsiProvideQualifiedComponentA"
0x180025923  mov     rcx, rax; hModule
0x180025926  call    cs:__imp_GetProcAddress
0x18002592c  mov     cs:?pMsiProvideQualifiedComponent@@3P6AIPEBD0KPEADPEAK@ZEA, rax; uint (*pMsiProvideQualifiedComponent)(char const *,char const *,ulong,char *,ulong *)
0x180025933  test    rax, rax
0x180025936  jz      loc_180025A1E
0x18002593c  mov     [rsp+190h+var_148], 104h
0x180025944  mov     rdx, rbx; char *
0x180025947  lea     rcx, [rsp+190h+pszStart]; this
0x18002594c  call    ??0CStr@@QEAA@PEBD@Z; CStr::CStr(char const *)
0x180025951  nop
0x180025952  xor     ebx, ebx
0x180025954  mov     [rsp+190h+var_158], rbx
0x180025959  lea     rcx, [rsp+190h+pszStart]; this
0x18002595e  call    ?strlen@CStr@@QEAAHXZ; CStr::strlen(void)
0x180025963  movsxd  rcx, eax
0x180025966  lea     edx, [rbx+7Dh]; wMatch
0x180025969  mov     rdi, [rsp+190h+pszStart]
0x18002596e  cmp     [rcx+rdi-1], dl
0x180025972  jz      loc_180025A09
0x180025978  mov     rcx, rdi; pszStart
0x18002597b  call    cs:__imp_StrChrA
0x180025981  test    rax, rax
0x180025984  jz      short loc_18002599F
0x180025986  lea     rbx, [rax+1]
0x18002598a  mov     rdx, rbx
0x18002598d  lea     rcx, [rsp+190h+var_158]
0x180025992  call    ??4CStr@@QEAAXPEBD@Z; CStr::operator=(char const *)
0x180025997  mov     byte ptr [rbx], 0
0x18002599a  mov     rbx, [rsp+190h+var_158]
0x18002599f  mov     [rsp+190h+var_160], 0
0x1800259a8  mov     rdx, rbx
0x1800259ab  lea     rcx, [rsp+190h+var_160]
0x1800259b0  call    ??4CStr@@QEAAXPEBD@Z; CStr::operator=(char const *)
0x1800259b5  lea     rdx, asc_18007E4A8; "\\"
0x1800259bc  lea     rcx, [rsp+190h+var_160]
0x1800259c1  call    ??YCStr@@QEAAXPEBD@Z; CStr::operator+=(char const *)
0x1800259c6  mov     rdx, r14
0x1800259c9  lea     rcx, [rsp+190h+var_160]
0x1800259ce  call    ??YCStr@@QEAAXPEBD@Z; CStr::operator+=(char const *)
0x1800259d3  lea     rax, [rsp+190h+var_148]
0x1800259d8  mov     [rsp+190h+var_170], rax
0x1800259dd  lea     r9, [rsp+190h+var_140]
0x1800259e2  or      r8d, 0FFFFFFFFh
0x1800259e6  mov     rdx, [rsp+190h+var_160]
0x1800259eb  mov     rcx, rdi
0x1800259ee  mov     rax, cs:?pMsiProvideQualifiedComponent@@3P6AIPEBD0KPEADPEAK@ZEA; uint (*pMsiProvideQualifiedComponent)(char const *,char const *,ulong,char *,ulong *)
0x1800259f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800259fa  test    eax, eax
0x1800259fc  jz      short loc_180025A3A
0x1800259fe  lea     rcx, [rsp+190h+var_160]; this
0x180025a03  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180025a08  nop
0x180025a09  lea     rcx, [rsp+190h+var_158]; this
0x180025a0e  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180025a13  nop
0x180025a14  lea     rcx, [rsp+190h+pszStart]; this
0x180025a19  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180025a1e  xor     eax, eax
0x180025a20  mov     rcx, [rbp+90h+var_30]
0x180025a24  xor     rcx, rsp; StackCookie
0x180025a27  call    __security_check_cookie
0x180025a2c  add     rsp, 170h
0x180025a33  pop     r14
0x180025a35  pop     rdi
0x180025a36  pop     rsi
0x180025a37  pop     rbx
0x180025a38  pop     rbp
0x180025a39  retn
0x180025a3a  lea     rdx, [rsp+190h+var_140]
0x180025a3f  mov     rcx, rsi
0x180025a42  call    ??4CStr@@QEAAXPEBD@Z; CStr::operator=(char const *)
0x180025a47  nop
0x180025a48  lea     rcx, [rsp+190h+var_160]; this
0x180025a4d  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180025a52  nop
0x180025a53  lea     rcx, [rsp+190h+var_158]; this
0x180025a58  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180025a5d  nop
0x180025a5e  lea     rcx, [rsp+190h+pszStart]; this
0x180025a63  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180025a68  mov     eax, 1
0x180025a6d  jmp     short loc_180025A20
```
