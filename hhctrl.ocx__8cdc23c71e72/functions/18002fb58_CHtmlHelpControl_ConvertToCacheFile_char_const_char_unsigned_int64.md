# CHtmlHelpControl::ConvertToCacheFile(char const *,char *,unsigned __int64)

- ea: `0x18002fb58`
- end: `0x18002fe89`
- name: `?ConvertToCacheFile@CHtmlHelpControl@@QEAAHPEBDPEAD_K@Z`
- size: `817`
- prototype: `__int64 __fastcall(CHtmlHelpControl *__hidden this, const char *, char *, unsigned __int64)`
- caller_count: `6`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x1800197c8`
- `0x18001a0ac`
- `0x18002e018`
- `0x18003bbc8`
- `0x180043cd8`
- `0x180058b0c`

## callees

- `0x1800029b8`
- `0x180003fc0`
- `0x180004224`
- `0x1800095c8`
- `0x180012934`
- `0x180020100`
- `0x18002018c`
- `0x1800269d0`
- `0x18002f3e8`
- `0x18002fb58`
- `0x18004eea0`
- `0x18004f65c`
- `0x180066a60`
- `0x180069430`
- `0x180075c90`

## import_xrefs

- `USER32!GetClassNameA` at `0x18002fd7f`
- `USER32!GetClassNameA` at `0x18002fd7f`
- `USER32!SendMessageA` at `0x18002fdaf`
- `USER32!SendMessageA` at `0x18002fdaf`
- `USER32!GetParent` at `0x18002fd61`
- `USER32!GetParent` at `0x18002fd61`
- `SHLWAPI!StrChrA` at `0x18002fd4b`
- `SHLWAPI!StrChrA` at `0x18002fd4b`
- `SHLWAPI!StrStrA` at `0x18002fc06`
- `SHLWAPI!StrStrA` at `0x18002fc06`
- `urlmon!URLDownloadToCacheFileA` at `0x18002fc91`
- `urlmon!URLDownloadToCacheFileA` at `0x18002fd37`
- `urlmon!URLDownloadToCacheFileA` at `0x18002fc91`
- `urlmon!URLDownloadToCacheFileA` at `0x18002fd37`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CHtmlHelpControl::ConvertToCacheFile(
        CHtmlHelpControl *this,
        const char *a2,
        char *a3,
        unsigned __int64 a4)
{
  const CHAR *v6; // rdi
  __int64 v8; // rsi
  const CHAR *v9; // rbx
  unsigned int v10; // r14d
  PSTR v11; // rsi
  int v12; // esi
  struct IUnknown *v13; // rbx
  int ThisFile; // ebx
  struct IUnknown *v15; // rbx
  HWND Parent; // rax
  HWND TopLevelWindow; // rbx
  _BYTE *v18; // rax
  const CHAR *v20; // [rsp+30h] [rbp-D0h] BYREF
  char *v21; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[272]; // [rsp+40h] [rbp-C0h] BYREF
  CHAR ClassName[256]; // [rsp+150h] [rbp+50h] BYREF

  v6 = a2;
  v20 = 0;
  v8 = HHStrStrIA(a2, "%SystemRoot%");
  v9 = 0;
  if ( !v8 )
    goto LABEL_4;
  HHGetWindowsDirectory(Data, 0x104u, 0);
  if ( (int)StringCchCatA((char *)Data, 0x104u, (const char *)(v8 + 12)) >= 0 )
  {
    CStr::operator=(&v20);
    v6 = v20;
    v9 = v20;
LABEL_4:
    v10 = 1;
    while ( 1 )
    {
      v11 = StrStrA(v6, "::");
      if ( v11 )
      {
        if ( v6 != v9 )
        {
          CStr::operator=(&v20);
          v12 = (_DWORD)v11 - (_DWORD)v6;
          v6 = v20;
          v11 = (PSTR)&v20[v12];
        }
        *v11 = 0;
        v13 = (struct IUnknown *)*((_QWORD *)this + 1);
        v21 = 0;
        CWStr::operator=(&v21, v6);
        LODWORD(v13) = CHtmlHelpControl::CheckDestUrlSafetyThruMoniker(this, (const unsigned __int16 *)v21, v13);
        CWStr::~CWStr((CWStr *)&v21);
        if ( (_DWORD)v13 )
          break;
        if ( URLDownloadToCacheFileA(*((LPUNKNOWN *)this + 1), v6, a3, a4, 0, 0) >= 0 )
        {
          *v11 = 58;
          if ( (int)StringCchCatA(a3, a4, v11) < 0 )
            break;
LABEL_23:
          CWStr::~CWStr((CWStr *)&v20);
          return v10;
        }
        v21 = 0;
        COleControl::ModalDialog(this, 1);
        ThisFile = FindThisFile(*((HWND *)this + 28), v6, (struct CStr *)&v21, 1);
        COleControl::ModalDialog(this, 0);
        if ( ThisFile )
        {
          if ( StringCchCopyA(a3, a4, v21) < 0 || (*v11 = 58, (int)StringCchCatA(a3, a4, v11) < 0) )
            v10 = 0;
          CWStr::~CWStr((CWStr *)&v21);
          goto LABEL_23;
        }
        CWStr::~CWStr((CWStr *)&v21);
      }
      v15 = (struct IUnknown *)*((_QWORD *)this + 1);
      v21 = 0;
      CWStr::operator=(&v21, v6);
      LODWORD(v15) = CHtmlHelpControl::CheckDestUrlSafetyThruMoniker(this, (const unsigned __int16 *)v21, v15);
      CWStr::~CWStr((CWStr *)&v21);
      if ( (_DWORD)v15 )
        break;
      if ( URLDownloadToCacheFileA(*((LPUNKNOWN *)this + 1), v6, a3, a4, 0, 0) >= 0 )
        goto LABEL_23;
      if ( StrChrA(v6, 0x3Au) )
        break;
      Parent = GetParent(*((HWND *)this + 28));
      TopLevelWindow = FindTopLevelWindow(Parent);
      GetClassNameA(TopLevelWindow, ClassName, 256);
      if ( !(unsigned int)IsSamePrefix(ClassName, "HH Parent", -2) )
        break;
      v18 = (_BYTE *)SendMessageA(TopLevelWindow, 0x614u, 0, 0);
      if ( !v18 || !*v18 )
        break;
      CStr::operator=(&v20);
      CStr::operator+=(&v20, "::");
      CStr::operator+=(&v20, v6);
      v6 = v20;
      v9 = v20;
    }
  }
  CWStr::~CWStr((CWStr *)&v20);
  return 0;
}

```

## disassembly

```asm
0x18002fb58  push    rbp
0x18002fb5a  push    rbx
0x18002fb5b  push    rsi
0x18002fb5c  push    rdi
0x18002fb5d  push    r12
0x18002fb5f  push    r13
0x18002fb61  push    r14
0x18002fb63  push    r15
0x18002fb65  lea     rbp, [rsp-168h]
0x18002fb6d  sub     rsp, 268h
0x18002fb74  mov     rax, cs:__security_cookie
0x18002fb7b  xor     rax, rsp
0x18002fb7e  mov     [rbp+1A0h+var_50], rax
0x18002fb85  mov     r13, r9
0x18002fb88  mov     r12, r8
0x18002fb8b  mov     rdi, rdx
0x18002fb8e  mov     r15, rcx
0x18002fb91  mov     [rsp+2A0h+var_270], 0
0x18002fb9a  lea     rdx, ?txtSysRoot@@3QBDB; "%SystemRoot%"
0x18002fba1  mov     rcx, rdi; pszStart
0x18002fba4  call    HHStrStrIA
0x18002fba9  mov     rsi, rax
0x18002fbac  xor     ebx, ebx
0x18002fbae  test    rax, rax
0x18002fbb1  jz      short loc_18002FBF6
0x18002fbb3  xor     r8d, r8d; unsigned int
0x18002fbb6  mov     ebx, 104h
0x18002fbbb  mov     edx, ebx; unsigned __int64
0x18002fbbd  lea     rcx, [rsp+2A0h+Data]; lpData
0x18002fbc2  call    ?HHGetWindowsDirectory@@YAKPEAD_KI@Z; HHGetWindowsDirectory(char *,unsigned __int64,uint)
0x18002fbc7  lea     r8, [rsi+0Ch]; char *
0x18002fbcb  mov     edx, ebx; unsigned __int64
0x18002fbcd  lea     rcx, [rsp+2A0h+Data]; char *
0x18002fbd2  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x18002fbd7  test    eax, eax
0x18002fbd9  js      loc_18002FE5A
0x18002fbdf  lea     rdx, [rsp+2A0h+Data]
0x18002fbe4  lea     rcx, [rsp+2A0h+var_270]
0x18002fbe9  call    ??4CStr@@QEAAXPEBD@Z; CStr::operator=(char const *)
0x18002fbee  mov     rdi, [rsp+2A0h+var_270]
0x18002fbf3  mov     rbx, rdi
0x18002fbf6  mov     r14d, 1
0x18002fbfc  lea     rdx, ?txtDoubleColonSep@@3QBDB; "::"
0x18002fc03  mov     rcx, rdi; pszFirst
0x18002fc06  call    cs:__imp_StrStrA
0x18002fc0c  mov     rsi, rax
0x18002fc0f  test    rax, rax
0x18002fc12  jz      loc_18002FCE4
0x18002fc18  cmp     rdi, rbx
0x18002fc1b  jz      short loc_18002FC37
0x18002fc1d  mov     rdx, rdi
0x18002fc20  lea     rcx, [rsp+2A0h+var_270]
0x18002fc25  call    ??4CStr@@QEAAXPEBD@Z; CStr::operator=(char const *)
0x18002fc2a  sub     esi, edi
0x18002fc2c  mov     rdi, [rsp+2A0h+var_270]
0x18002fc31  movsxd  rsi, esi
0x18002fc34  add     rsi, rdi
0x18002fc37  mov     byte ptr [rsi], 0
0x18002fc3a  mov     rbx, [r15+8]
0x18002fc3e  mov     [rsp+2A0h+var_268], 0
0x18002fc47  mov     rdx, rdi
0x18002fc4a  lea     rcx, [rsp+2A0h+var_268]
0x18002fc4f  call    ??4CWStr@@QEAAXPEBD@Z; CWStr::operator=(char const *)
0x18002fc54  nop
0x18002fc55  mov     r8, rbx; struct IUnknown *
0x18002fc58  mov     rdx, [rsp+2A0h+var_268]; unsigned __int16 *
0x18002fc5d  mov     rcx, r15; this
0x18002fc60  call    ?CheckDestUrlSafetyThruMoniker@CHtmlHelpControl@@QEAAJPEBGPEAUIUnknown@@@Z; CHtmlHelpControl::CheckDestUrlSafetyThruMoniker(ushort const *,IUnknown *)
0x18002fc65  mov     ebx, eax
0x18002fc67  lea     rcx, [rsp+2A0h+var_268]; this
0x18002fc6c  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x18002fc71  test    ebx, ebx
0x18002fc73  jnz     loc_18002FE5A
0x18002fc79  xor     ebx, ebx
0x18002fc7b  mov     [rsp+2A0h+var_278], rbx; LPBINDSTATUSCALLBACK
0x18002fc80  mov     [rsp+2A0h+var_280], ebx; DWORD
0x18002fc84  mov     r9d, r13d; cchFileName
0x18002fc87  mov     r8, r12; LPSTR
0x18002fc8a  mov     rdx, rdi; LPCSTR
0x18002fc8d  mov     rcx, [r15+8]; LPUNKNOWN
0x18002fc91  call    cs:__imp_URLDownloadToCacheFileA
0x18002fc97  test    eax, eax
0x18002fc99  jns     loc_18002FE45
0x18002fc9f  mov     [rsp+2A0h+var_268], rbx
0x18002fca4  mov     edx, r14d; int
0x18002fca7  mov     rcx, r15; this
0x18002fcaa  call    ?ModalDialog@COleControl@@QEAAXH@Z; COleControl::ModalDialog(int)
0x18002fcaf  mov     r9d, r14d; int
0x18002fcb2  lea     r8, [rsp+2A0h+var_268]; struct CStr *
0x18002fcb7  mov     rdx, rdi; char *
0x18002fcba  mov     rcx, [r15+0E0h]; HWND
0x18002fcc1  call    ?FindThisFile@@YAHPEAUHWND__@@PEBDPEAVCStr@@H@Z; FindThisFile(HWND__ *,char const *,CStr *,int)
0x18002fcc6  mov     ebx, eax
0x18002fcc8  xor     edx, edx; int
0x18002fcca  mov     rcx, r15; this
0x18002fccd  call    ?ModalDialog@COleControl@@QEAAXH@Z; COleControl::ModalDialog(int)
0x18002fcd2  test    ebx, ebx
0x18002fcd4  jnz     loc_18002FDFF
0x18002fcda  lea     rcx, [rsp+2A0h+var_268]; this
0x18002fcdf  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x18002fce4  mov     rbx, [r15+8]
0x18002fce8  xor     esi, esi
0x18002fcea  mov     [rsp+2A0h+var_268], rsi
0x18002fcef  mov     rdx, rdi
0x18002fcf2  lea     rcx, [rsp+2A0h+var_268]
0x18002fcf7  call    ??4CWStr@@QEAAXPEBD@Z; CWStr::operator=(char const *)
0x18002fcfc  nop
0x18002fcfd  mov     r8, rbx; struct IUnknown *
0x18002fd00  mov     rdx, [rsp+2A0h+var_268]; unsigned __int16 *
0x18002fd05  mov     rcx, r15; this
0x18002fd08  call    ?CheckDestUrlSafetyThruMoniker@CHtmlHelpControl@@QEAAJPEBGPEAUIUnknown@@@Z; CHtmlHelpControl::CheckDestUrlSafetyThruMoniker(ushort const *,IUnknown *)
0x18002fd0d  mov     ebx, eax
0x18002fd0f  lea     rcx, [rsp+2A0h+var_268]; this
0x18002fd14  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x18002fd19  test    ebx, ebx
0x18002fd1b  jnz     loc_18002FE5A
0x18002fd21  mov     [rsp+2A0h+var_278], rsi; LPBINDSTATUSCALLBACK
0x18002fd26  mov     [rsp+2A0h+var_280], esi; DWORD
0x18002fd2a  mov     r9d, r13d; cchFileName
0x18002fd2d  mov     r8, r12; LPSTR
0x18002fd30  mov     rdx, rdi; LPCSTR
0x18002fd33  mov     rcx, [r15+8]; LPUNKNOWN
0x18002fd37  call    cs:__imp_URLDownloadToCacheFileA
0x18002fd3d  test    eax, eax
0x18002fd3f  jns     loc_18002FE36
0x18002fd45  lea     edx, [rsi+3Ah]; wMatch
0x18002fd48  mov     rcx, rdi; pszStart
0x18002fd4b  call    cs:__imp_StrChrA
0x18002fd51  test    rax, rax
0x18002fd54  jnz     loc_18002FE5A
0x18002fd5a  mov     rcx, [r15+0E0h]; hWnd
0x18002fd61  call    cs:__imp_GetParent
0x18002fd67  mov     rcx, rax; HWND
0x18002fd6a  call    ?FindTopLevelWindow@@YAPEAUHWND__@@PEAU1@@Z; FindTopLevelWindow(HWND__ *)
0x18002fd6f  mov     rbx, rax
0x18002fd72  mov     r8d, 100h; nMaxCount
0x18002fd78  lea     rdx, [rbp+1A0h+ClassName]; lpClassName
0x18002fd7c  mov     rcx, rax; hWnd
0x18002fd7f  call    cs:__imp_GetClassNameA
0x18002fd85  lea     r8d, [rsi-2]; int
0x18002fd89  lea     rdx, ?txtHtmlHelpWindowClass@@3QBDB; "HH Parent"
0x18002fd90  lea     rcx, [rbp+1A0h+ClassName]; char *
0x18002fd94  call    ?IsSamePrefix@@YAHPEBD0H@Z; IsSamePrefix(char const *,char const *,int)
0x18002fd99  test    eax, eax
0x18002fd9b  jz      loc_18002FE5A
0x18002fda1  xor     r9d, r9d; lParam
0x18002fda4  xor     r8d, r8d; wParam
0x18002fda7  mov     edx, 614h; Msg
0x18002fdac  mov     rcx, rbx; hWnd
0x18002fdaf  call    cs:__imp_SendMessageA
0x18002fdb5  test    rax, rax
0x18002fdb8  jz      loc_18002FE5A
0x18002fdbe  cmp     [rax], sil
0x18002fdc1  jz      loc_18002FE5A
0x18002fdc7  mov     rdx, rax
0x18002fdca  lea     rcx, [rsp+2A0h+var_270]
0x18002fdcf  call    ??4CStr@@QEAAXPEBD@Z; CStr::operator=(char const *)
0x18002fdd4  lea     rdx, ?txtDoubleColonSep@@3QBDB; "::"
0x18002fddb  lea     rcx, [rsp+2A0h+var_270]
0x18002fde0  call    ??YCStr@@QEAAXPEBD@Z; CStr::operator+=(char const *)
0x18002fde5  mov     rdx, rdi
0x18002fde8  lea     rcx, [rsp+2A0h+var_270]
0x18002fded  call    ??YCStr@@QEAAXPEBD@Z; CStr::operator+=(char const *)
0x18002fdf2  mov     rdi, [rsp+2A0h+var_270]
0x18002fdf7  mov     rbx, rdi
0x18002fdfa  jmp     loc_18002FBFC
0x18002fdff  mov     r8, [rsp+2A0h+var_268]; char *
0x18002fe04  mov     rdx, r13; unsigned __int64
0x18002fe07  mov     rcx, r12; char *
0x18002fe0a  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x18002fe0f  test    eax, eax
0x18002fe11  js      short loc_18002FE28
0x18002fe13  mov     byte ptr [rsi], 3Ah ; ':'
0x18002fe16  mov     r8, rsi; char *
0x18002fe19  mov     rdx, r13; unsigned __int64
0x18002fe1c  mov     rcx, r12; char *
0x18002fe1f  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x18002fe24  test    eax, eax
0x18002fe26  jns     short loc_18002FE2B
0x18002fe28  xor     r14d, r14d
0x18002fe2b  lea     rcx, [rsp+2A0h+var_268]; this
0x18002fe30  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x18002fe35  nop
0x18002fe36  lea     rcx, [rsp+2A0h+var_270]; this
0x18002fe3b  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x18002fe40  mov     eax, r14d
0x18002fe43  jmp     short loc_18002FE66
0x18002fe45  mov     byte ptr [rsi], 3Ah ; ':'
0x18002fe48  mov     r8, rsi; char *
0x18002fe4b  mov     rdx, r13; unsigned __int64
0x18002fe4e  mov     rcx, r12; char *
0x18002fe51  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x18002fe56  test    eax, eax
0x18002fe58  jns     short loc_18002FE36
0x18002fe5a  lea     rcx, [rsp+2A0h+var_270]; this
0x18002fe5f  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x18002fe64  xor     eax, eax
0x18002fe66  mov     rcx, [rbp+1A0h+var_50]
0x18002fe6d  xor     rcx, rsp; StackCookie
0x18002fe70  call    __security_check_cookie
0x18002fe75  add     rsp, 268h
0x18002fe7c  pop     r15
0x18002fe7e  pop     r14
0x18002fe80  pop     r13
0x18002fe82  pop     r12
0x18002fe84  pop     rdi
0x18002fe85  pop     rsi
0x18002fe86  pop     rbx
0x18002fe87  pop     rbp
0x18002fe88  retn
```
