# GetObjectFromPathWithHandle(CMDBaseObject * &,ulong,CMDHandle *,ulong,char * &,int)

- ea: `0x180003850`
- end: `0x180003d1d`
- name: `?GetObjectFromPathWithHandle@@YAJAEAPEAVCMDBaseObject@@KPEAVCMDHandle@@KAEAPEADH@Z`
- size: `1229`
- prototype: `__int64 __fastcall(struct CMDBaseObject **, unsigned int, struct CMDHandle *, unsigned int, char **, int)`
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x1800166b8`
- `0x180016f80`
- `0x180017104`
- `0x180019d8c`
- `0x18001aeb4`
- `0x18001c580`
- `0x180022ed8`

## callees

- `0x180003850`
- `0x1800056d0`
- `0x18003099a`
- `0x1800309d0`

## import_xrefs

- `USER32!CharNextExA` at `0x180003bd4`
- `USER32!CharNextExA` at `0x180003bd4`
- `KERNEL32!LCMapStringW` at `0x180003a43`
- `KERNEL32!LCMapStringW` at `0x180003a43`
- `KERNEL32!MultiByteToWideChar` at `0x180003c34`
- `KERNEL32!MultiByteToWideChar` at `0x180003c34`
- `KERNEL32!GetLastError` at `0x180003a54`
- `KERNEL32!GetLastError` at `0x180003c40`
- `KERNEL32!GetLastError` at `0x180003a54`
- `KERNEL32!GetLastError` at `0x180003c40`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003a00`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003afa`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003bf8`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003c60`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003a00`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003afa`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003bf8`
- `IisRTL!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003c60`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x180003c0a`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x180003c53`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x180003c84`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x180003c0a`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x180003c53`
- `IisRTL!?QuerySize@BUFFER@@QEBAKXZ` at `0x180003c84`
- `IisRTL!??0BUFFER@@QEAA@PEAEK@Z` at `0x1800039a6`
- `IisRTL!??0BUFFER@@QEAA@PEAEK@Z` at `0x1800039e2`
- `IisRTL!??0BUFFER@@QEAA@PEAEK@Z` at `0x1800039a6`
- `IisRTL!??0BUFFER@@QEAA@PEAEK@Z` at `0x1800039e2`
- `IisRTL!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180003b2f`
- `IisRTL!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180003b2f`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180003a67`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180003a77`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180003b0f`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180003b3f`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180003ce9`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180003a67`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180003a77`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180003b0f`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180003b3f`
- `IisRTL!??1BUFFER@@QEAA@XZ` at `0x180003ce9`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180003a16`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180003adf`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180003c18`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180003c73`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180003a16`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180003adf`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180003c18`
- `IisRTL!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180003c73`

## pseudocode

```c
__int64 __fastcall GetObjectFromPathWithHandle(
        struct CMDBaseObject **a1,
        __int64 a2,
        struct CMDHandle *a3,
        char a4,
        char **a5,
        int a6)
{
  struct CMDBaseObject *v6; // r12
  const CHAR *v7; // r14
  struct CMDBaseObject *v8; // rcx
  unsigned int v9; // ebx
  __int16 v10; // ax
  LPSTR v11; // rdi
  CHAR v12; // al
  int v13; // esi
  const WCHAR *v14; // r15
  unsigned int v15; // ebx
  int cchDest; // ebx
  WCHAR *lpDestStr; // rcx
  int v18; // eax
  int v19; // eax
  int v20; // ebx
  unsigned int v22; // ebx
  struct CMDBaseObject *v23; // rbx
  unsigned int v24; // ebx
  WCHAR *Ptr; // rax
  int v26; // ebx
  unsigned int Size; // eax
  const CHAR *i; // [rsp+30h] [rbp-D0h] BYREF
  struct CMDBaseObject **v29; // [rsp+38h] [rbp-C8h]
  char **v30; // [rsp+40h] [rbp-C0h]
  _BYTE v31[48]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int j; // [rsp+80h] [rbp-80h]
  struct CMDBaseObject *v33; // [rsp+88h] [rbp-78h]
  _BYTE v34[48]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int8 v35[512]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int8 v36[272]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v30 = a5;
  v29 = a1;
  *a1 = 0;
  if ( !a3 )
    return (unsigned int)-2147024809;
  if ( (a4 & 2) != 0 && (*((_BYTE *)a3 + 12) & 2) == 0 || (a4 & 1) != 0 && (*((_BYTE *)a3 + 12) & 1) == 0 )
    return (unsigned int)-2147024891;
  v6 = (struct CMDBaseObject *)*((_QWORD *)a3 + 3);
  if ( !v6 )
    return (unsigned int)-2147467259;
  v7 = *a5;
  if ( !*a5 )
  {
    *a1 = v6;
    return 0;
  }
  v8 = 0;
  if ( a6 )
  {
    if ( *(_WORD *)v7 == 47 || *(_WORD *)v7 == 92 )
      v7 += 2;
  }
  else if ( *v7 == 47 || *v7 == 92 )
  {
    goto LABEL_51;
  }
  while ( v6 )
  {
    if ( a6 )
    {
      if ( !*(_WORD *)v7 )
        goto LABEL_71;
      v10 = *(_WORD *)v7;
      v11 = (LPSTR)v7;
      for ( i = v7; v10 != 92; v11 += 2 )
      {
        if ( v10 == 47 )
          break;
        if ( !v10 )
          break;
        v10 = *((_WORD *)v11 + 1);
      }
    }
    else
    {
      v12 = *v7;
      if ( !*v7 )
      {
LABEL_71:
        v9 = 0;
        *v29 = v6;
        return v9;
      }
      v11 = (LPSTR)v7;
      if ( v12 != 92 )
      {
        do
        {
          if ( v12 == 47 )
            break;
          if ( !v12 )
            break;
          v11 = CharNextExA(0, v11, 0);
          v12 = *v11;
        }
        while ( *v11 != 92 );
      }
    }
    BUFFER::BUFFER((BUFFER *)v31, v36, 0x104u);
    j = 0;
    v33 = v6;
    v13 = (_DWORD)v11 - (_DWORD)v7;
    if ( (_DWORD)v11 == (_DWORD)v7 )
    {
      v9 = -2147024893;
      BUFFER::~BUFFER((BUFFER *)v31);
      return v9;
    }
    v14 = (const WCHAR *)v7;
    memset_0(v35, 0, sizeof(v35));
    BUFFER::BUFFER((BUFFER *)v34, v35, 0x200u);
    if ( !a6 )
    {
      if ( v13 > 0 && !BUFFER::Resize((BUFFER *)v34, 2 * v13 + 50) )
        goto LABEL_31;
      while ( 1 )
      {
        v24 = BUFFER::QuerySize((BUFFER *)v34) >> 1;
        Ptr = (WCHAR *)BUFFER::QueryPtr((BUFFER *)v34);
        v26 = MultiByteToWideChar(0, 1u, v7, v13, Ptr, v24);
        if ( v26 )
          break;
        if ( GetLastError() == 122 )
        {
          Size = BUFFER::QuerySize((BUFFER *)v34);
          if ( BUFFER::Resize((BUFFER *)v34, Size + 50) )
            continue;
        }
        goto LABEL_31;
      }
      v14 = (const WCHAR *)BUFFER::QueryPtr((BUFFER *)v34);
      v13 = 2 * v26;
    }
    if ( v13 > 0 )
    {
      if ( BUFFER::Resize((BUFFER *)v31, v13) )
      {
        v15 = v13;
        j = v13;
        goto LABEL_27;
      }
LABEL_31:
      BUFFER::~BUFFER((BUFFER *)v34);
      v9 = -2147024882;
      BUFFER::~BUFFER((BUFFER *)v31);
      return v9;
    }
    v15 = BUFFER::QuerySize((BUFFER *)v31);
    for ( j = v15; ; v15 = j )
    {
LABEL_27:
      cchDest = v15 >> 1;
      lpDestStr = (WCHAR *)BUFFER::QueryPtr((BUFFER *)v31);
      v18 = v13;
      if ( v13 >= 0 )
        v18 = v13 / 2;
      v19 = LCMapStringW(0x800u, 0x200u, v14, v18, lpDestStr, cchDest);
      v20 = v19;
      if ( v19 )
        break;
      if ( GetLastError() != 122 || !(unsigned int)CMDKeyBuffer::Resize((CMDKeyBuffer *)v31, j + 50) )
        goto LABEL_31;
    }
    if ( !*((_WORD *)BUFFER::QueryPtr((BUFFER *)v31) + v19 - 1) )
      --v20;
    v22 = 2 * v20;
    if ( !BUFFER::Resize((BUFFER *)v31, v22) )
      goto LABEL_31;
    j = v22;
    BUFFER::~BUFFER((BUFFER *)v34);
    i = 0;
    CLKRHashTable::FindKey(g_phtChildren, v31, &i);
    v23 = (struct CMDBaseObject *)i;
    BUFFER::~BUFFER((BUFFER *)v31);
    v8 = v6;
    if ( v23 )
    {
      v7 = v11;
      if ( a6 )
      {
        if ( *(_WORD *)v11 == 47 || *(_WORD *)v11 == 92 )
          v7 = v11 + 2;
        goto LABEL_42;
      }
      if ( *v11 == 47 || *v11 == 92 )
      {
        v6 = v23;
LABEL_51:
        ++v7;
      }
      else
      {
        v6 = v23;
      }
    }
    else
    {
LABEL_42:
      v6 = v23;
    }
  }
  if ( v8 )
  {
    v9 = -2147024893;
    *v29 = v8;
    *v30 = (char *)v7;
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return v9;
}

```

## disassembly

```asm
0x180003850  push    rbp
0x180003852  push    rbx
0x180003853  lea     rbp, [rsp-2F8h]
0x18000385b  sub     rsp, 3F8h
0x180003862  mov     rax, cs:__security_cookie
0x180003869  xor     rax, rsp
0x18000386c  mov     [rbp+300h+var_30], rax
0x180003873  mov     r10, [rbp+300h+arg_20]
0x18000387a  mov     [rsp+400h+var_3C0], r10
0x18000387f  mov     [rsp+400h+var_3C8], rcx
0x180003884  mov     qword ptr [rcx], 0
0x18000388b  test    r8, r8
0x18000388e  jz      loc_180003B78
0x180003894  test    r9b, 2
0x180003898  jnz     loc_180003AC8
0x18000389e  test    r9b, 1
0x1800038a2  jz      short loc_1800038AF
0x1800038a4  test    byte ptr [r8+0Ch], 1
0x1800038a9  jz      loc_180003AD3
0x1800038af  mov     [rsp+400h+arg_18], r12
0x1800038b7  mov     r12, [r8+18h]
0x1800038bb  test    r12, r12
0x1800038be  jz      loc_180003B82
0x1800038c4  mov     [rsp+400h+var_18], r14
0x1800038cc  mov     r14, [r10]
0x1800038cf  test    r14, r14
0x1800038d2  jz      loc_180003B8C
0x1800038d8  mov     [rsp+400h+arg_8], rsi
0x1800038e0  xor     ecx, ecx
0x1800038e2  mov     [rsp+400h+arg_10], rdi
0x1800038ea  mov     [rsp+400h+var_10], r13
0x1800038f2  mov     r13d, [rbp+300h+arg_28]
0x1800038f9  mov     [rsp+400h+var_20], r15
0x180003901  test    r13d, r13d
0x180003904  jz      loc_180003B9F
0x18000390a  movzx   eax, word ptr [r14]
0x18000390e  cmp     ax, 2Fh ; '/'
0x180003912  jz      loc_180003B96
0x180003918  cmp     ax, 5Ch ; '\'
0x18000391c  jz      loc_180003B96
0x180003922  test    r12, r12
0x180003925  jnz     short loc_18000393A
0x180003927  test    rcx, rcx
0x18000392a  jnz     loc_180003D03
0x180003930  mov     ebx, 80004005h
0x180003935  jmp     loc_180003A7D
0x18000393a  test    r13d, r13d
0x18000393d  jz      short loc_18000397B
0x18000393f  cmp     word ptr [r14], 0
0x180003944  jz      loc_180003CF4
0x18000394a  movzx   eax, word ptr [r14]
0x18000394e  mov     rdi, r14
0x180003951  mov     [rsp+400h+var_3D0], r14
0x180003956  cmp     ax, 5Ch ; '\'
0x18000395a  jz      short loc_180003992
0x18000395c  nop     dword ptr [rax+00h]
0x180003960  cmp     ax, 2Fh ; '/'
0x180003964  jz      short loc_180003992
0x180003966  test    ax, ax
0x180003969  jz      short loc_180003992
0x18000396b  movzx   eax, word ptr [rdi+2]
0x18000396f  add     rdi, 2
0x180003973  cmp     ax, 5Ch ; '\'
0x180003977  jnz     short loc_180003960
0x180003979  jmp     short loc_180003992
0x18000397b  movzx   eax, byte ptr [r14]
0x18000397f  test    al, al
0x180003981  jz      loc_180003CF4
0x180003987  mov     rdi, r14
0x18000398a  cmp     al, 5Ch ; '\'
0x18000398c  jnz     loc_180003BBC
0x180003992  mov     r8d, 104h
0x180003998  lea     rdx, [rbp+300h+var_140]
0x18000399f  lea     rcx, [rsp+400h+var_3B0]
0x1800039a4  mov     esi, edi
0x1800039a6  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x1800039ac  mov     [rbp+300h+var_380], 0
0x1800039b3  mov     [rbp+300h+var_378], r12
0x1800039b7  sub     esi, r14d
0x1800039ba  jz      loc_180003CDF
0x1800039c0  xor     edx, edx; Val
0x1800039c2  lea     rcx, [rbp+300h+var_340]; void *
0x1800039c6  mov     r8d, 200h; Size
0x1800039cc  mov     r15, r14
0x1800039cf  call    memset_0
0x1800039d4  mov     r8d, 200h
0x1800039da  lea     rdx, [rbp+300h+var_340]
0x1800039de  lea     rcx, [rbp+300h+var_370]
0x1800039e2  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x1800039e8  test    r13d, r13d
0x1800039eb  jz      loc_180003BE9
0x1800039f1  lea     rcx, [rsp+400h+var_3B0]
0x1800039f6  test    esi, esi
0x1800039f8  jle     loc_180003C84
0x1800039fe  mov     edx, esi
0x180003a00  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180003a06  test    al, al
0x180003a08  jz      short loc_180003A63
0x180003a0a  mov     ebx, esi
0x180003a0c  mov     [rbp+300h+var_380], ebx
0x180003a0f  lea     rcx, [rsp+400h+var_3B0]
0x180003a14  shr     ebx, 1
0x180003a16  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180003a1c  mov     rcx, rax
0x180003a1f  mov     eax, esi
0x180003a21  test    esi, esi
0x180003a23  js      short loc_180003A2A
0x180003a25  cdq
0x180003a26  sub     eax, edx
0x180003a28  sar     eax, 1
0x180003a2a  mov     [rsp+400h+cchDest], ebx; cchDest
0x180003a2e  mov     r9d, eax; cchSrc
0x180003a31  mov     [rsp+400h+lpDestStr], rcx; lpDestStr
0x180003a36  mov     r8, r15; lpSrcStr
0x180003a39  mov     ecx, 800h; Locale
0x180003a3e  mov     edx, 200h; dwMapFlags
0x180003a43  call    cs:__imp_LCMapStringW
0x180003a49  movsxd  rbx, eax
0x180003a4c  test    eax, eax
0x180003a4e  jnz     loc_180003ADA
0x180003a54  call    cs:__imp_GetLastError
0x180003a5a  cmp     eax, 7Ah ; 'z'
0x180003a5d  jz      loc_180003C94
0x180003a63  lea     rcx, [rbp+300h+var_370]
0x180003a67  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180003a6d  lea     rcx, [rsp+400h+var_3B0]
0x180003a72  mov     ebx, 8007000Eh
0x180003a77  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180003a7d  mov     rdi, [rsp+400h+arg_10]
0x180003a85  mov     r13, [rsp+400h+var_10]
0x180003a8d  mov     rsi, [rsp+400h+arg_8]
0x180003a95  mov     r15, [rsp+400h+var_20]
0x180003a9d  mov     r14, [rsp+400h+var_18]
0x180003aa5  mov     r12, [rsp+400h+arg_18]
0x180003aad  mov     eax, ebx
0x180003aaf  mov     rcx, [rbp+300h+var_30]
0x180003ab6  xor     rcx, rsp; StackCookie
0x180003ab9  call    __security_check_cookie
0x180003abe  add     rsp, 3F8h
0x180003ac5  pop     rbx
0x180003ac6  pop     rbp
0x180003ac7  retn
0x180003ac8  test    byte ptr [r8+0Ch], 2
0x180003acd  jnz     loc_18000389E
0x180003ad3  mov     ebx, 80070005h
0x180003ad8  jmp     short loc_180003AAD
0x180003ada  lea     rcx, [rsp+400h+var_3B0]
0x180003adf  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180003ae5  cmp     word ptr [rax+rbx*2-2], 0
0x180003aeb  jz      loc_180003CB4
0x180003af1  add     ebx, ebx
0x180003af3  lea     rcx, [rsp+400h+var_3B0]
0x180003af8  mov     edx, ebx
0x180003afa  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180003b00  test    al, al
0x180003b02  jz      loc_180003A63
0x180003b08  lea     rcx, [rbp+300h+var_370]
0x180003b0c  mov     [rbp+300h+var_380], ebx
0x180003b0f  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180003b15  mov     rcx, cs:?g_phtChildren@@3PEAVCChildNodeHashTable@@EA; CChildNodeHashTable * g_phtChildren
0x180003b1c  lea     r8, [rsp+400h+var_3D0]
0x180003b21  lea     rdx, [rsp+400h+var_3B0]
0x180003b26  mov     [rsp+400h+var_3D0], 0
0x180003b2f  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x180003b35  mov     rbx, [rsp+400h+var_3D0]
0x180003b3a  lea     rcx, [rsp+400h+var_3B0]
0x180003b3f  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180003b45  mov     rcx, r12
0x180003b48  test    rbx, rbx
0x180003b4b  jz      short loc_180003B70
0x180003b4d  mov     r14, rdi
0x180003b50  test    r13d, r13d
0x180003b53  jz      loc_180003CC4
0x180003b59  movzx   eax, word ptr [rdi]
0x180003b5c  cmp     ax, 2Fh ; '/'
0x180003b60  jz      loc_180003CBB
0x180003b66  cmp     ax, 5Ch ; '\'
0x180003b6a  jz      loc_180003CBB
0x180003b70  mov     r12, rbx
0x180003b73  jmp     loc_180003922
0x180003b78  mov     ebx, 80070057h
0x180003b7d  jmp     loc_180003AAD
0x180003b82  mov     ebx, 80004005h
0x180003b87  jmp     loc_180003AA5
0x180003b8c  mov     [rcx], r12
0x180003b8f  xor     ebx, ebx
0x180003b91  jmp     loc_180003A9D
0x180003b96  add     r14, 2
0x180003b9a  jmp     loc_180003922
0x180003b9f  movzx   eax, byte ptr [r14]
0x180003ba3  cmp     al, 2Fh ; '/'
0x180003ba5  jz      short loc_180003BB4
0x180003ba7  cmp     al, 5Ch ; '\'
0x180003ba9  jnz     loc_180003922
0x180003baf  jmp     short loc_180003BB4
0x180003bb1  mov     r12, rbx
0x180003bb4  inc     r14
0x180003bb7  jmp     loc_180003922
0x180003bbc  cmp     al, 2Fh ; '/'
0x180003bbe  jz      loc_180003992
0x180003bc4  test    al, al
0x180003bc6  jz      loc_180003992
0x180003bcc  xor     ecx, ecx; CodePage
0x180003bce  xor     r8d, r8d; dwFlags
0x180003bd1  mov     rdx, rdi; lpCurrentChar
0x180003bd4  call    cs:__imp_CharNextExA
0x180003bda  mov     rdi, rax
0x180003bdd  movzx   eax, byte ptr [rax]
0x180003be0  cmp     al, 5Ch ; '\'
0x180003be2  jnz     short loc_180003BBC
0x180003be4  jmp     loc_180003992
0x180003be9  test    esi, esi
0x180003beb  jle     short loc_180003C06
0x180003bed  lea     edx, ds:32h[rsi*2]
0x180003bf4  lea     rcx, [rbp+300h+var_370]
0x180003bf8  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180003bfe  test    al, al
0x180003c00  jz      loc_180003A63
0x180003c06  lea     rcx, [rbp+300h+var_370]
0x180003c0a  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180003c10  mov     ebx, eax
0x180003c12  lea     rcx, [rbp+300h+var_370]
0x180003c16  shr     ebx, 1
0x180003c18  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180003c1e  mov     r9d, esi; cbMultiByte
0x180003c21  mov     [rsp+400h+cchDest], ebx; cchWideChar
0x180003c25  mov     r8, r14; lpMultiByteStr
0x180003c28  mov     [rsp+400h+lpDestStr], rax; lpWideCharStr
0x180003c2d  mov     edx, 1; dwFlags
0x180003c32  xor     ecx, ecx; CodePage
0x180003c34  call    cs:__imp_MultiByteToWideChar
0x180003c3a  mov     ebx, eax
0x180003c3c  test    eax, eax
0x180003c3e  jnz     short loc_180003C6F
0x180003c40  call    cs:__imp_GetLastError
0x180003c46  cmp     eax, 7Ah ; 'z'
0x180003c49  jnz     loc_180003A63
0x180003c4f  lea     rcx, [rbp+300h+var_370]
0x180003c53  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180003c59  lea     rcx, [rbp+300h+var_370]
0x180003c5d  lea     edx, [rax+32h]
0x180003c60  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180003c66  test    al, al
0x180003c68  jnz     short loc_180003C06
0x180003c6a  jmp     loc_180003A63
0x180003c6f  lea     rcx, [rbp+300h+var_370]
0x180003c73  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180003c79  mov     r15, rax
0x180003c7c  lea     esi, [rbx+rbx]
0x180003c7f  jmp     loc_1800039F1
0x180003c84  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180003c8a  mov     ebx, eax
0x180003c8c  mov     [rbp+300h+var_380], eax
0x180003c8f  jmp     loc_180003A0F
0x180003c94  mov     edx, [rbp+300h+var_380]
0x180003c97  lea     rcx, [rsp+400h+var_3B0]; this
0x180003c9c  add     edx, 32h ; '2'; unsigned int
0x180003c9f  call    ?Resize@CMDKeyBuffer@@QEAAHI@Z; CMDKeyBuffer::Resize(uint)
0x180003ca4  test    eax, eax
0x180003ca6  jz      loc_180003A63
0x180003cac  mov     ebx, [rbp+300h+var_380]
0x180003caf  jmp     loc_180003A0F
0x180003cb4  dec     ebx
0x180003cb6  jmp     loc_180003AF1
0x180003cbb  add     r14, 2
0x180003cbf  jmp     loc_180003B70
0x180003cc4  movzx   eax, byte ptr [rdi]
0x180003cc7  cmp     al, 2Fh ; '/'
0x180003cc9  jz      loc_180003BB1
0x180003ccf  cmp     al, 5Ch ; '\'
0x180003cd1  jz      loc_180003BB1
0x180003cd7  mov     r12, rbx
0x180003cda  jmp     loc_180003922
0x180003cdf  lea     rcx, [rsp+400h+var_3B0]
0x180003ce4  mov     ebx, 80070003h
0x180003ce9  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180003cef  jmp     loc_180003A7D
0x180003cf4  mov     rax, [rsp+400h+var_3C8]
0x180003cf9  xor     ebx, ebx
0x180003cfb  mov     [rax], r12
0x180003cfe  jmp     loc_180003A7D
0x180003d03  mov     rax, [rsp+400h+var_3C8]
0x180003d08  mov     ebx, 80070003h
0x180003d0d  mov     [rax], rcx
0x180003d10  mov     rax, [rsp+400h+var_3C0]
0x180003d15  mov     [rax], r14
0x180003d18  jmp     loc_180003A7D
```
