# CHtmlHelpControl::OnCopySample(void)

- ea: `0x1800458c4`
- end: `0x180045cfb`
- name: `?OnCopySample@CHtmlHelpControl@@QEAAHXZ`
- size: `1079`
- prototype: `__int64 __fastcall(CHtmlHelpControl *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800450a0`

## callees

- `0x1800029b8`
- `0x180003fc0`
- `0x180004224`
- `0x1800095c8`
- `0x18000f460`
- `0x180014c80`
- `0x18002018c`
- `0x1800286d4`
- `0x1800301f8`
- `0x1800340b0`
- `0x1800458c4`
- `0x18004ad98`
- `0x18004e6a8`
- `0x180051e98`
- `0x180063bd8`
- `0x180075c90`
- `0x180075d50`

## import_xrefs

- `KERNEL32!DeleteFileA` at `0x180045a9c`
- `KERNEL32!DeleteFileA` at `0x180045a9c`
- `KERNEL32!GetTempPath2A` at `0x180045a4b`
- `KERNEL32!GetTempPath2A` at `0x180045a4b`
- `KERNEL32!GetTempFileNameA` at `0x180045a69`
- `KERNEL32!GetTempFileNameA` at `0x180045a69`
- `urlmon!URLDownloadToFileA` at `0x180045a87`
- `urlmon!URLDownloadToFileA` at `0x180045a87`

## pseudocode

```c
__int64 __fastcall CHtmlHelpControl::OnCopySample(CHtmlHelpControl *this)
{
  __int64 result; // rax
  _BYTE *v3; // rdx
  char *v4; // rbx
  CHAR *v5; // rdi
  CHAR i; // cl
  CHAR *v7; // rax
  char *v8; // rdi
  HWND v9; // rcx
  CExCollection *CurrentCollection; // rax
  CExCollection *v11; // rdi
  struct CExTitle *v12; // rsi
  const char **v13; // rdx
  const char *v14; // rdx
  struct CLocation *Location; // rax
  struct CLocation *v16; // r15
  unsigned int v17; // edi
  int v18; // eax
  char *v19; // [rsp+30h] [rbp-D0h] BYREF
  char *v20; // [rsp+38h] [rbp-C8h] BYREF
  char *v21; // [rsp+40h] [rbp-C0h] BYREF
  char *v22; // [rsp+48h] [rbp-B8h] BYREF
  struct CExTitle *v23; // [rsp+50h] [rbp-B0h] BYREF
  char v24[272]; // [rsp+60h] [rbp-A0h] BYREF
  char v25[256]; // [rsp+170h] [rbp+70h] BYREF
  CHAR TempFileName[272]; // [rsp+270h] [rbp+170h] BYREF
  CHAR PathName[272]; // [rsp+380h] [rbp+280h] BYREF
  char v28[2096]; // [rsp+490h] [rbp+390h] BYREF
  CHAR v29[2096]; // [rsp+CC0h] [rbp+BC0h] BYREF
  char v30[2096]; // [rsp+14F0h] [rbp+13F0h] BYREF

  result = *((_QWORD *)this + 63);
  if ( result )
  {
    v19 = 0;
    v3 = *(_BYTE **)(*(_QWORD *)(result + 16) + 16LL);
    if ( !v3 || !*v3 )
    {
      v17 = 0;
      goto LABEL_34;
    }
    CStr::operator=(&v19);
    StringCchCopyA(v25, 0x100u, v19);
    v25[255] = 0;
    CStr::operator=(&v19);
    CStr::operator+=(&v19, ".SFL");
    v22 = 0;
    CStr::operator=(&v22);
    v21 = 0;
    if ( CHtmlHelpControl::GetCurrentUrl(this, (struct CStr *)&v21) )
    {
      v4 = v19;
      StringCchPrintfA(v30, 0x824u, "/samples/%s/%s", v25, v19);
      StringCchCopyA(v29, 0x824u, v21);
      v5 = v29;
      for ( i = v29[0]; i; i = *v7 )
      {
        v7 = v5 + 1;
        if ( i == 58 && *v7 == 58 )
          break;
        ++v5;
      }
      if ( *v5 )
      {
        v5[2] = 0;
        StringCchCatA(v29, 0x824u, v30);
        GetTempPath2A(260, PathName);
        GetTempFileNameA(PathName, "SFL", 0, TempFileName);
        if ( URLDownloadToFileA(0, v29, TempFileName, 0, 0) >= 0 )
        {
          v5[2] = 0;
          StringCchPrintfA(v28, 0x824u, "%s/samples/%s/", v29, v25);
          v17 = ProcessSample(TempFileName, v28, v22, this, 1);
          goto LABEL_31;
        }
        DeleteFileA(TempFileName);
        v20 = 0;
        v8 = 0;
        if ( CHtmlHelpControl::GetCurrentUrl(this, (struct CStr *)&v20) )
          v8 = v20;
        CurrentCollection = GetCurrentCollection(v9, v8);
        v11 = CurrentCollection;
        if ( CurrentCollection )
        {
          v23 = 0;
          CExCollection::URL2ExTitle(CurrentCollection, v21, &v23);
          v12 = v23;
          if ( v23 )
          {
            if ( (CExTitle::Init(v23), *((_QWORD *)v12 + 1))
              && (v13 = (const char **)*((_QWORD *)v12 + 11)) != 0
              && (v14 = *v13) != 0
              || (v14 = (const char *)*((_QWORD *)v11 + 13)) != 0 )
            {
              Location = CCollection::FindLocation((CExCollection *)((char *)v11 + 64), v14, 0);
              v16 = Location;
              if ( Location )
              {
                StringCchCopyA(v28, 0x104u, *((const char **)Location + 2));
                StringCchCopyA(v24, 0x104u, v28);
                CatPath(v24, "\\SFL\\", 0x104u);
                CatPath(v24, v4, 0x104u);
                if ( v24[0] )
                  StringCchCopyA((char *)v12 + 228, 0x104u, v24);
                v17 = 1;
                v18 = EnsureStorageAvailability(v12, 2u, 1, 1, 0);
                if ( v18 >= 0 )
                {
                  if ( v18 == 262244 )
                  {
                    StringCchCopyA(v28, 0x104u, *((const char **)v16 + 2));
                    StringCchCopyA(v24, 0x104u, v28);
                    CatPath(v24, "\\SFL\\", 0x104u);
                    CatPath(v24, v4, 0x104u);
                  }
                  v17 = ProcessSample(v24, v28, v22, this, 0);
                  goto LABEL_25;
                }
                if ( (unsigned int)(v18 + 2147221404) <= 1 )
                {
LABEL_25:
                  CWStr::~CWStr((CWStr *)&v20);
LABEL_31:
                  CWStr::~CWStr((CWStr *)&v21);
                  CWStr::~CWStr((CWStr *)&v22);
LABEL_34:
                  CWStr::~CWStr((CWStr *)&v19);
                  return v17;
                }
              }
            }
          }
        }
        CWStr::~CWStr((CWStr *)&v20);
      }
    }
    v17 = 0;
    goto LABEL_31;
  }
  return result;
}

```

## disassembly

```asm
0x1800458c4  push    rbp
0x1800458c6  push    rbx
0x1800458c7  push    rsi
0x1800458c8  push    rdi
0x1800458c9  push    r12
0x1800458cb  push    r13
0x1800458cd  push    r14
0x1800458cf  push    r15
0x1800458d1  lea     rbp, [rsp-1C38h]
0x1800458d9  mov     eax, 1D38h
0x1800458de  call    _alloca_probe
0x1800458e3  sub     rsp, rax
0x1800458e6  mov     rax, cs:__security_cookie
0x1800458ed  xor     rax, rsp
0x1800458f0  mov     [rbp+1C70h+var_50], rax
0x1800458f7  mov     r14, rcx
0x1800458fa  mov     rax, [rcx+1F8h]
0x180045901  xor     r12d, r12d
0x180045904  test    rax, rax
0x180045907  jz      loc_180045CD8
0x18004590d  mov     [rsp+1D70h+var_1D40], r12
0x180045912  mov     rax, [rax+10h]
0x180045916  mov     rdx, [rax+10h]
0x18004591a  test    rdx, rdx
0x18004591d  jz      loc_180045CC9
0x180045923  cmp     [rdx], r12b
0x180045926  jz      loc_180045CC9
0x18004592c  lea     rcx, [rsp+1D70h+var_1D40]
0x180045931  call    ??4CStr@@QEAAXPEBD@Z; CStr::operator=(char const *)
0x180045936  mov     r8, [rsp+1D70h+var_1D40]; char *
0x18004593b  mov     edx, 100h; unsigned __int64
0x180045940  lea     rcx, [rbp+1C70h+var_1C00]; char *
0x180045944  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180045949  mov     [rbp+1C70h+var_1B01], r12b
0x180045950  lea     rdx, [rbp+1C70h+var_1C00]
0x180045954  lea     rcx, [rsp+1D70h+var_1D40]
0x180045959  call    ??4CStr@@QEAAXPEBD@Z; CStr::operator=(char const *)
0x18004595e  lea     rdx, aSfl_1; ".SFL"
0x180045965  lea     rcx, [rsp+1D70h+var_1D40]
0x18004596a  call    ??YCStr@@QEAAXPEBD@Z; CStr::operator+=(char const *)
0x18004596f  mov     [rsp+1D70h+var_1D28], r12
0x180045974  mov     rax, [r14+1F8h]
0x18004597b  mov     rcx, [rax+10h]
0x18004597f  mov     rdx, [rcx+8]
0x180045983  test    rdx, rdx
0x180045986  jz      short loc_18004598D
0x180045988  cmp     [rdx], r12b
0x18004598b  jnz     short loc_180045994
0x18004598d  lea     rdx, aSampleApplicat; "Sample Application"
0x180045994  lea     rcx, [rsp+1D70h+var_1D28]
0x180045999  call    ??4CStr@@QEAAXPEBD@Z; CStr::operator=(char const *)
0x18004599e  mov     [rsp+1D70h+var_1D30], r12
0x1800459a3  lea     rdx, [rsp+1D70h+var_1D30]; struct CStr *
0x1800459a8  mov     rcx, r14; this
0x1800459ab  call    ?GetCurrentUrl@CHtmlHelpControl@@QEAA_NAEAVCStr@@@Z; CHtmlHelpControl::GetCurrentUrl(CStr &)
0x1800459b0  test    al, al
0x1800459b2  jz      loc_180045C5E
0x1800459b8  mov     rbx, [rsp+1D70h+var_1D40]
0x1800459bd  mov     [rsp+1D70h+var_1D50], rbx
0x1800459c2  lea     r9, [rbp+1C70h+var_1C00]
0x1800459c6  lea     r8, aSamplesSS; "/samples/%s/%s"
0x1800459cd  mov     esi, 824h
0x1800459d2  mov     edx, esi; unsigned __int64
0x1800459d4  lea     rcx, [rbp+1C70h+var_880]; char *
0x1800459db  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x1800459e0  mov     r8, [rsp+1D70h+var_1D30]; char *
0x1800459e5  mov     edx, esi; unsigned __int64
0x1800459e7  lea     rcx, [rbp+1C70h+var_10B0]; char *
0x1800459ee  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x1800459f3  lea     rdi, [rbp+1C70h+var_10B0]
0x1800459fa  mov     cl, [rbp+1C70h+var_10B0]
0x180045a00  jmp     short loc_180045A14
0x180045a02  lea     rax, [rdi+1]
0x180045a06  cmp     cl, 3Ah ; ':'
0x180045a09  jnz     short loc_180045A0F
0x180045a0b  cmp     [rax], cl
0x180045a0d  jz      short loc_180045A18
0x180045a0f  mov     rdi, rax
0x180045a12  mov     cl, [rax]
0x180045a14  test    cl, cl
0x180045a16  jnz     short loc_180045A02
0x180045a18  cmp     [rdi], r12b
0x180045a1b  jz      loc_180045C5E
0x180045a21  mov     [rdi+2], r12b
0x180045a25  lea     r8, [rbp+1C70h+var_880]; char *
0x180045a2c  mov     rdx, rsi; unsigned __int64
0x180045a2f  lea     rcx, [rbp+1C70h+var_10B0]; char *
0x180045a36  call    ?StringCchCatA@@YAJPEAD_KPEBD@Z; StringCchCatA(char *,unsigned __int64,char const *)
0x180045a3b  lea     rdx, [rbp+1C70h+PathName]
0x180045a42  mov     r13d, 104h
0x180045a48  mov     ecx, r13d
0x180045a4b  call    cs:__imp_GetTempPath2A
0x180045a51  lea     r9, [rbp+1C70h+TempFileName]; lpTempFileName
0x180045a58  xor     r8d, r8d; uUnique
0x180045a5b  lea     rdx, PrefixString; "SFL"
0x180045a62  lea     rcx, [rbp+1C70h+PathName]; lpPathName
0x180045a69  call    cs:__imp_GetTempFileNameA
0x180045a6f  mov     [rsp+1D70h+var_1D50], r12; LPBINDSTATUSCALLBACK
0x180045a74  xor     r9d, r9d; DWORD
0x180045a77  lea     r8, [rbp+1C70h+TempFileName]; LPCSTR
0x180045a7e  lea     rdx, [rbp+1C70h+var_10B0]; LPCSTR
0x180045a85  xor     ecx, ecx; LPUNKNOWN
0x180045a87  call    cs:__imp_URLDownloadToFileA
0x180045a8d  test    eax, eax
0x180045a8f  jns     loc_180045C78
0x180045a95  lea     rcx, [rbp+1C70h+TempFileName]; lpFileName
0x180045a9c  call    cs:__imp_DeleteFileA
0x180045aa2  mov     [rsp+1D70h+var_1D38], r12
0x180045aa7  mov     rdi, r12
0x180045aaa  lea     rdx, [rsp+1D70h+var_1D38]; struct CStr *
0x180045aaf  mov     rcx, r14; this
0x180045ab2  call    ?GetCurrentUrl@CHtmlHelpControl@@QEAA_NAEAVCStr@@@Z; CHtmlHelpControl::GetCurrentUrl(CStr &)
0x180045ab7  test    al, al
0x180045ab9  cmovnz  rdi, [rsp+1D70h+var_1D38]
0x180045abf  mov     rdx, rdi; char *
0x180045ac2  call    ?GetCurrentCollection@@YAPEAVCExCollection@@PEAUHWND__@@PEBD@Z; GetCurrentCollection(HWND__ *,char const *)
0x180045ac7  mov     rdi, rax
0x180045aca  test    rax, rax
0x180045acd  jz      loc_180045C54
0x180045ad3  mov     [rsp+1D70h+var_1D20], r12
0x180045ad8  lea     r8, [rsp+1D70h+var_1D20]; struct CExTitle **
0x180045add  mov     rdx, [rsp+1D70h+var_1D30]; char *
0x180045ae2  mov     rcx, rax; this
0x180045ae5  call    ?URL2ExTitle@CExCollection@@QEAAJPEBDPEAPEAVCExTitle@@@Z; CExCollection::URL2ExTitle(char const *,CExTitle * *)
0x180045aea  mov     rsi, [rsp+1D70h+var_1D20]
0x180045aef  test    rsi, rsi
0x180045af2  jz      loc_180045C54
0x180045af8  mov     rcx, rsi; this
0x180045afb  call    ?Init@CExTitle@@QEAAHXZ; CExTitle::Init(void)
0x180045b00  cmp     [rsi+8], r12
0x180045b04  jz      short loc_180045B17
0x180045b06  mov     rdx, [rsi+58h]
0x180045b0a  test    rdx, rdx
0x180045b0d  jz      short loc_180045B17
0x180045b0f  mov     rdx, [rdx]
0x180045b12  test    rdx, rdx
0x180045b15  jnz     short loc_180045B24
0x180045b17  mov     rdx, [rdi+68h]; char *
0x180045b1b  test    rdx, rdx
0x180045b1e  jz      loc_180045C54
0x180045b24  lea     rcx, [rdi+40h]; this
0x180045b28  xor     r8d, r8d; unsigned int *
0x180045b2b  call    ?FindLocation@CCollection@@QEAAPEAVCLocation@@PEBDPEAI@Z; CCollection::FindLocation(char const *,uint *)
0x180045b30  mov     r15, rax
0x180045b33  test    rax, rax
0x180045b36  jz      loc_180045C54
0x180045b3c  mov     r8, [rax+10h]; char *
0x180045b40  mov     rdx, r13; unsigned __int64
0x180045b43  lea     rcx, [rbp+1C70h+var_18E0]; char *
0x180045b4a  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180045b4f  lea     r8, [rbp+1C70h+var_18E0]; char *
0x180045b56  mov     rdx, r13; unsigned __int64
0x180045b59  lea     rcx, [rsp+1D70h+var_1D10]; char *
0x180045b5e  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180045b63  mov     r8, r13; unsigned __int64
0x180045b66  lea     rdx, aSfl_0; "\\SFL\\"
0x180045b6d  lea     rcx, [rsp+1D70h+var_1D10]; char *
0x180045b72  call    ?CatPath@@YAPEADPEADPEBD_K@Z; CatPath(char *,char const *,unsigned __int64)
0x180045b77  mov     r8, r13; unsigned __int64
0x180045b7a  mov     rdx, rbx; char *
0x180045b7d  lea     rcx, [rsp+1D70h+var_1D10]; char *
0x180045b82  call    ?CatPath@@YAPEADPEADPEBD_K@Z; CatPath(char *,char const *,unsigned __int64)
0x180045b87  cmp     [rsp+1D70h+var_1D10], r12b
0x180045b8c  jz      short loc_180045BA2
0x180045b8e  lea     rcx, [rsi+0E4h]; char *
0x180045b95  lea     r8, [rsp+1D70h+var_1D10]; char *
0x180045b9a  mov     rdx, r13; unsigned __int64
0x180045b9d  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180045ba2  mov     dword ptr [rsp+1D70h+var_1D50], r12d; int
0x180045ba7  mov     edi, 1
0x180045bac  mov     r9d, edi; int
0x180045baf  mov     r8d, edi; int
0x180045bb2  lea     edx, [rdi+1]; unsigned int
0x180045bb5  mov     rcx, rsi; struct CExTitle *
0x180045bb8  call    ?EnsureStorageAvailability@@YAJPEAVCExTitle@@IHHH@Z; EnsureStorageAvailability(CExTitle *,uint,int,int,int)
0x180045bbd  test    eax, eax
0x180045bbf  jns     short loc_180045BDD
0x180045bc1  add     eax, 7FFBFF9Ch
0x180045bc6  cmp     eax, edi
0x180045bc8  ja      loc_180045C54
0x180045bce  lea     rcx, [rsp+1D70h+var_1D38]; this
0x180045bd3  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180045bd8  jmp     loc_180045C61
0x180045bdd  cmp     eax, 40064h
0x180045be2  jnz     short loc_180045C2F
0x180045be4  mov     r8, [r15+10h]; char *
0x180045be8  mov     rdx, r13; unsigned __int64
0x180045beb  lea     rcx, [rbp+1C70h+var_18E0]; char *
0x180045bf2  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180045bf7  lea     r8, [rbp+1C70h+var_18E0]; char *
0x180045bfe  mov     rdx, r13; unsigned __int64
0x180045c01  lea     rcx, [rsp+1D70h+var_1D10]; char *
0x180045c06  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180045c0b  mov     r8, r13; unsigned __int64
0x180045c0e  lea     rdx, aSfl_0; "\\SFL\\"
0x180045c15  lea     rcx, [rsp+1D70h+var_1D10]; char *
0x180045c1a  call    ?CatPath@@YAPEADPEADPEBD_K@Z; CatPath(char *,char const *,unsigned __int64)
0x180045c1f  mov     r8, r13; unsigned __int64
0x180045c22  mov     rdx, rbx; char *
0x180045c25  lea     rcx, [rsp+1D70h+var_1D10]; char *
0x180045c2a  call    ?CatPath@@YAPEADPEADPEBD_K@Z; CatPath(char *,char const *,unsigned __int64)
0x180045c2f  mov     dword ptr [rsp+1D70h+var_1D50], r12d; int
0x180045c34  mov     r9, r14; struct CHtmlHelpControl *
0x180045c37  mov     r8, [rsp+1D70h+var_1D28]; char *
0x180045c3c  lea     rdx, [rbp+1C70h+var_18E0]; char *
0x180045c43  lea     rcx, [rsp+1D70h+var_1D10]; char *
0x180045c48  call    ?ProcessSample@@YAHPEBD00PEAVCHtmlHelpControl@@H@Z; ProcessSample(char const *,char const *,char const *,CHtmlHelpControl *,int)
0x180045c4d  mov     edi, eax
0x180045c4f  jmp     loc_180045BCE
0x180045c54  lea     rcx, [rsp+1D70h+var_1D38]; this
0x180045c59  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180045c5e  mov     edi, r12d
0x180045c61  lea     rcx, [rsp+1D70h+var_1D30]; this
0x180045c66  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180045c6b  nop
0x180045c6c  lea     rcx, [rsp+1D70h+var_1D28]; this
0x180045c71  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180045c76  jmp     short loc_180045CCC
0x180045c78  mov     [rdi+2], r12b
0x180045c7c  lea     rax, [rbp+1C70h+var_1C00]
0x180045c80  mov     [rsp+1D70h+var_1D50], rax
0x180045c85  lea     r9, [rbp+1C70h+var_10B0]
0x180045c8c  lea     r8, aSSamplesS; "%s/samples/%s/"
0x180045c93  mov     rdx, rsi; unsigned __int64
0x180045c96  lea     rcx, [rbp+1C70h+var_18E0]; char *
0x180045c9d  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180045ca2  mov     dword ptr [rsp+1D70h+var_1D50], 1; int
0x180045caa  mov     r9, r14; struct CHtmlHelpControl *
0x180045cad  mov     r8, [rsp+1D70h+var_1D28]; char *
0x180045cb2  lea     rdx, [rbp+1C70h+var_18E0]; char *
0x180045cb9  lea     rcx, [rbp+1C70h+TempFileName]; char *
0x180045cc0  call    ?ProcessSample@@YAHPEBD00PEAVCHtmlHelpControl@@H@Z; ProcessSample(char const *,char const *,char const *,CHtmlHelpControl *,int)
0x180045cc5  mov     edi, eax
0x180045cc7  jmp     short loc_180045C61
0x180045cc9  mov     edi, r12d
0x180045ccc  lea     rcx, [rsp+1D70h+var_1D40]; this
0x180045cd1  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x180045cd6  mov     eax, edi
0x180045cd8  mov     rcx, [rbp+1C70h+var_50]
0x180045cdf  xor     rcx, rsp; StackCookie
0x180045ce2  call    __security_check_cookie
0x180045ce7  add     rsp, 1D38h
0x180045cee  pop     r15
0x180045cf0  pop     r14
0x180045cf2  pop     r13
0x180045cf4  pop     r12
0x180045cf6  pop     rdi
0x180045cf7  pop     rsi
0x180045cf8  pop     rbx
0x180045cf9  pop     rbp
0x180045cfa  retn
```
