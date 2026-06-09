# IsCompiledHtmlFile(char const *,CStr *)

- ea: `0x180068790`
- end: `0x180068a27`
- name: `?IsCompiledHtmlFile@@YAHPEBDPEAVCStr@@@Z`
- size: `663`
- prototype: `__int64 __fastcall(PCSTR pszStart, struct CStr *this)`
- caller_count: `14`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180013c00`
- `0x18001a0ac`
- `0x18001dd04`
- `0x18002d2dc`
- `0x180030704`
- `0x180037e70`
- `0x180038028`
- `0x180038640`
- `0x180038d40`
- `0x18003bbc8`
- `0x180045e94`
- `0x1800470d8`
- `0x180053084`
- `0x18006a610`

## callees

- `0x1800029b8`
- `0x180004224`
- `0x18000f810`
- `0x18002018c`
- `0x1800269d0`
- `0x180042da8`
- `0x18004f65c`
- `0x180068790`
- `0x180068a30`
- `0x18006a7ac`
- `0x180075c90`

## import_xrefs

- `msvcrt!realloc` at `0x18006899a`
- `msvcrt!realloc` at `0x18006899a`
- `msvcrt!free` at `0x1800689ad`
- `msvcrt!free` at `0x1800689f4`
- `msvcrt!free` at `0x1800689ad`
- `msvcrt!free` at `0x1800689f4`
- `KERNEL32!lstrlenA` at `0x180068841`
- `KERNEL32!lstrlenA` at `0x180068863`
- `KERNEL32!lstrlenA` at `0x180068841`
- `KERNEL32!lstrlenA` at `0x180068863`
- `USER32!CharNextA` at `0x180068888`
- `USER32!CharNextA` at `0x180068888`
- `SHLWAPI!StrChrIA` at `0x180068852`
- `SHLWAPI!StrChrIA` at `0x180068852`
- `SHLWAPI!StrCmpNIA` at `0x18006887b`
- `SHLWAPI!StrCmpNIA` at `0x18006887b`

## string_xrefs

- `0x18006894a`: `mk:@MSITStore:`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall IsCompiledHtmlFile(PCSTR pszStart, struct CStr *this)
{
  PCSTR v4; // rsi
  __int64 v5; // rbp
  __int64 v6; // rax
  __int64 v7; // rax
  const CHAR *v8; // rsi
  unsigned int v9; // r14d
  const CHAR *v10; // rax
  const CHAR *v11; // rsi
  char *v13; // rax
  char *v14; // rcx
  __int64 v15; // rax
  char *v16; // r8
  __int64 v17; // rdx
  char *v18; // rcx
  char v19; // r9
  char *v20; // rax
  size_t v21; // rbx
  char *v22; // rax
  void *v23; // rcx
  void *Block; // [rsp+20h] [rbp-148h] BYREF
  char v25[272]; // [rsp+30h] [rbp-138h] BYREF

  if ( (unsigned int)IsCompiledURL(pszStart) )
  {
    if ( this )
      CStr::operator=(this);
    return 1;
  }
  v4 = (PCSTR)HHStrStrIA(pszStart, "::");
  v5 = -1;
  if ( !v4 )
  {
    v6 = -1;
    do
      ++v6;
    while ( pszStart[v6] );
    if ( !HHStrStrIA(&pszStart[v6 - 4], ".chm") )
    {
      v7 = -1;
      do
        ++v7;
      while ( pszStart[v7] );
      v8 = &pszStart[v7 - 4];
      if ( !v8 )
        return 0;
      v9 = lstrlenA(".its");
      while ( 1 )
      {
        v10 = StrChrIA(v8, 0x692Eu);
        v11 = v10;
        if ( !v10 )
          break;
        if ( lstrlenA(v10) < v9 )
        {
          v11 = 0;
          break;
        }
        if ( !StrCmpNIA(v11, ".its", v9) )
          break;
        v8 = CharNextA(v11);
      }
      if ( !v11 )
        return 0;
    }
    v4 = pszStart;
  }
  if ( this )
  {
    if ( pszStart )
    {
      v13 = lcStrDup(pszStart);
      Block = v13;
      if ( !v13 )
        OOM();
      v14 = v13;
    }
    else
    {
      v13 = 0;
      Block = 0;
      v14 = 0;
    }
    if ( v4 > pszStart )
    {
      v4[v14 - pszStart] = 0;
      v13 = (char *)Block;
    }
    if ( (unsigned int)FindThisFile(0, v13, (struct CStr *)&Block, 0) )
    {
      v15 = 2147483646;
      v16 = (char *)v4;
      v17 = 260;
      v18 = v25;
      do
      {
        if ( !v15 )
          break;
        v19 = *v16;
        if ( !*v16 )
          break;
        ++v16;
        *v18++ = v19;
        --v15;
        --v17;
      }
      while ( v17 );
      v20 = v18 - 1;
      if ( v17 )
        v20 = v18;
      *v20 = 0;
      CStr::operator=(this);
      CStr::operator+=(this, Block);
      if ( v4 > pszStart )
      {
        do
          ++v5;
        while ( v25[v5] );
        v21 = (int)(v5 + CStr::strlen(this) + 1);
        v22 = (char *)realloc(*(void **)this, v21);
        if ( *(_QWORD *)this && !v22 )
        {
          free(*(void **)this);
          OOM();
        }
        *(_QWORD *)this = v22;
        if ( v22 )
          StringCchCatA(v22, v21, v25);
      }
      v23 = Block;
      if ( !Block )
        return 1;
      goto LABEL_45;
    }
    CStr::operator=(this);
    v23 = Block;
    if ( Block )
LABEL_45:
      free(v23);
  }
  return 1;
}

```

## disassembly

```asm
0x180068790  mov     [rsp+arg_10], rbx
0x180068795  mov     [rsp+arg_18], rbp
0x18006879a  push    rsi
0x18006879b  push    rdi
0x18006879c  push    r14
0x18006879e  sub     rsp, 150h
0x1800687a5  mov     rax, cs:__security_cookie
0x1800687ac  xor     rax, rsp
0x1800687af  mov     [rsp+168h+var_28], rax
0x1800687b7  mov     rdi, rdx
0x1800687ba  mov     rbx, rcx
0x1800687bd  call    ?IsCompiledURL@@YAHPEBD@Z; IsCompiledURL(char const *)
0x1800687c2  test    eax, eax
0x1800687c4  jz      short loc_1800687DF
0x1800687c6  test    rdi, rdi
0x1800687c9  jz      loc_1800689FA
0x1800687cf  mov     rdx, rbx
0x1800687d2  mov     rcx, rdi
0x1800687d5  call    ??4CStr@@QEAAXPEBD@Z; CStr::operator=(char const *)
0x1800687da  jmp     loc_1800689FA
0x1800687df  lea     rdx, ?txtDoubleColonSep@@3QBDB; "::"
0x1800687e6  mov     rcx, rbx; pszStart
0x1800687e9  call    HHStrStrIA
0x1800687ee  mov     rsi, rax
0x1800687f1  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x1800687f8  test    rax, rax
0x1800687fb  jnz     loc_1800688A4
0x180068801  mov     rax, rbp
0x180068804  inc     rax
0x180068807  cmp     byte ptr [rbx+rax], 0
0x18006880b  jnz     short loc_180068804
0x18006880d  lea     rcx, [rbx-4]
0x180068811  add     rcx, rax; pszStart
0x180068814  lea     rdx, ?txtDefExtension@@3QBDB; ".chm"
0x18006881b  call    HHStrStrIA
0x180068820  test    rax, rax
0x180068823  jnz     short loc_1800688A1
0x180068825  mov     rax, rbp
0x180068828  inc     rax
0x18006882b  cmp     byte ptr [rbx+rax], 0
0x18006882f  jnz     short loc_180068828
0x180068831  lea     rsi, [rbx-4]
0x180068835  add     rsi, rax
0x180068838  jz      short loc_18006889A
0x18006883a  lea     rcx, aIts_1; ".its"
0x180068841  call    cs:__imp_lstrlenA
0x180068847  mov     r14d, eax
0x18006884a  mov     edx, 692Eh; wMatch
0x18006884f  mov     rcx, rsi; pszStart
0x180068852  call    cs:__imp_StrChrIA
0x180068858  mov     rsi, rax
0x18006885b  test    rax, rax
0x18006885e  jz      short loc_180068895
0x180068860  mov     rcx, rax; lpString
0x180068863  call    cs:__imp_lstrlenA
0x180068869  cmp     eax, r14d
0x18006886c  jb      short loc_180068893
0x18006886e  mov     r8d, r14d; nChar
0x180068871  lea     rdx, aIts_1; ".its"
0x180068878  mov     rcx, rsi; psz1
0x18006887b  call    cs:__imp_StrCmpNIA
0x180068881  test    eax, eax
0x180068883  jz      short loc_180068895
0x180068885  mov     rcx, rsi; lpsz
0x180068888  call    cs:__imp_CharNextA
0x18006888e  mov     rsi, rax
0x180068891  jmp     short loc_18006884A
0x180068893  xor     esi, esi
0x180068895  test    rsi, rsi
0x180068898  jnz     short loc_1800688A1
0x18006889a  xor     eax, eax
0x18006889c  jmp     loc_1800689FF
0x1800688a1  mov     rsi, rbx
0x1800688a4  test    rdi, rdi
0x1800688a7  jz      loc_1800689FA
0x1800688ad  test    rbx, rbx
0x1800688b0  jz      short loc_1800688CF
0x1800688b2  mov     rcx, rbx; char *
0x1800688b5  call    ?lcStrDup@@YAPEADPEBD@Z; lcStrDup(char const *)
0x1800688ba  mov     [rsp+168h+Block], rax
0x1800688bf  test    rax, rax
0x1800688c2  jnz     short loc_1800688CA
0x1800688c4  call    ?OOM@@YAXXZ; OOM(void)
0x1800688ca  mov     rcx, rax
0x1800688cd  jmp     short loc_1800688D8
0x1800688cf  xor     eax, eax
0x1800688d1  mov     [rsp+168h+Block], rax
0x1800688d6  xor     ecx, ecx
0x1800688d8  cmp     rsi, rbx
0x1800688db  jbe     short loc_1800688E9
0x1800688dd  sub     rcx, rbx
0x1800688e0  mov     byte ptr [rcx+rsi], 0
0x1800688e4  mov     rax, [rsp+168h+Block]
0x1800688e9  xor     r9d, r9d; int
0x1800688ec  lea     r8, [rsp+168h+Block]; struct CStr *
0x1800688f1  mov     rdx, rax; char *
0x1800688f4  xor     ecx, ecx; HWND
0x1800688f6  call    ?FindThisFile@@YAHPEAUHWND__@@PEBDPEAVCStr@@H@Z; FindThisFile(HWND__ *,char const *,CStr *,int)
0x1800688fb  test    eax, eax
0x1800688fd  jz      loc_1800689DE
0x180068903  mov     eax, 7FFFFFFEh
0x180068908  mov     r8, rsi
0x18006890b  mov     edx, 104h
0x180068910  lea     rcx, [rsp+168h+var_138]
0x180068915  test    rax, rax
0x180068918  jz      short loc_180068935
0x18006891a  movzx   r9d, byte ptr [r8]
0x18006891e  test    r9b, r9b
0x180068921  jz      short loc_180068935
0x180068923  inc     r8
0x180068926  mov     [rcx], r9b
0x180068929  inc     rcx
0x18006892c  dec     rax
0x18006892f  sub     rdx, 1
0x180068933  jnz     short loc_180068915
0x180068935  lea     rax, [rcx-1]
0x180068939  test    rdx, rdx
0x18006893c  cmovnz  rax, rcx
0x180068940  mov     byte ptr [rax], 0
0x180068943  lea     rdx, ?txtMsItsMoniker@@3QBDB; "ms-its:"
0x18006894a  lea     rax, ?txtMkStore@@3QBDB; "mk:@MSITStore:"
0x180068951  cmp     cs:?g_bMsItsMonikerSupport@@3HA, 0; int g_bMsItsMonikerSupport
0x180068958  cmovz   rdx, rax
0x18006895c  mov     rcx, rdi
0x18006895f  call    ??4CStr@@QEAAXPEBD@Z; CStr::operator=(char const *)
0x180068964  mov     rdx, [rsp+168h+Block]
0x180068969  mov     rcx, rdi
0x18006896c  call    ??YCStr@@QEAAXPEBD@Z; CStr::operator+=(char const *)
0x180068971  cmp     rsi, rbx
0x180068974  jbe     short loc_1800689D2
0x180068976  lea     rax, [rsp+168h+var_138]
0x18006897b  inc     rbp
0x18006897e  cmp     byte ptr [rax+rbp], 0
0x180068982  jnz     short loc_18006897B
0x180068984  mov     rcx, rdi; this
0x180068987  call    ?strlen@CStr@@QEAAHXZ; CStr::strlen(void)
0x18006898c  lea     ecx, [rax+1]
0x18006898f  add     ecx, ebp
0x180068991  movsxd  rbx, ecx
0x180068994  mov     rdx, rbx; Size
0x180068997  mov     rcx, [rdi]; Block
0x18006899a  call    cs:__imp_realloc
0x1800689a0  mov     rcx, [rdi]; Block
0x1800689a3  test    rcx, rcx
0x1800689a6  jz      short loc_1800689B9
0x1800689a8  test    rax, rax
0x1800689ab  jnz     short loc_1800689B9
0x1800689ad  call    cs:__imp_free
0x1800689b3  call    ?OOM@@YAXXZ; OOM(void)
0x1800689b9  mov     [rdi], rax
0x1800689bc  test    rax, rax
0x1800689bf  jz      short loc_1800689D2
0x1800689c1  lea     r8, [rsp+168h+var_138]; char *
0x1800689c6  mov     rdx, rbx; unsigned __int64
0x1800689c9  mov     rcx, rax; char *
0x1800689cc  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x1800689d1  nop
0x1800689d2  mov     rcx, [rsp+168h+Block]
0x1800689d7  test    rcx, rcx
0x1800689da  jz      short loc_1800689FA
0x1800689dc  jmp     short loc_1800689F4
0x1800689de  mov     rdx, rbx
0x1800689e1  mov     rcx, rdi
0x1800689e4  call    ??4CStr@@QEAAXPEBD@Z; CStr::operator=(char const *)
0x1800689e9  nop
0x1800689ea  mov     rcx, [rsp+168h+Block]; Block
0x1800689ef  test    rcx, rcx
0x1800689f2  jz      short loc_1800689FA
0x1800689f4  call    cs:__imp_free
0x1800689fa  mov     eax, 1
0x1800689ff  mov     rcx, [rsp+168h+var_28]
0x180068a07  xor     rcx, rsp; StackCookie
0x180068a0a  call    __security_check_cookie
0x180068a0f  lea     r11, [rsp+168h+var_18]
0x180068a17  mov     rbx, [r11+30h]
0x180068a1b  mov     rbp, [r11+38h]
0x180068a1f  mov     rsp, r11
0x180068a22  pop     r14
0x180068a24  pop     rdi
0x180068a25  pop     rsi
0x180068a26  retn
```
