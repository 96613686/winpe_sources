# myGetCertificateFromPicker(HINSTANCE__ *,HWND__ *,int,int,ulong,ushort const *,ulong,void * *,ushort const * *,ulong,char const * const *,_CERT_CONTEXT const * *)

- ea: `0x180018310`
- end: `0x1800187e7`
- name: `?myGetCertificateFromPicker@@YAJPEAUHINSTANCE__@@PEAUHWND__@@HHKPEBGKPEAPEAXPEAPEBGKPEBQEBDPEAPEBU_CERT_CONTEXT@@@Z`
- size: `1239`
- prototype: `__int64 __fastcall(HINSTANCE, HWND, unsigned int, unsigned int, unsigned int, unsigned __int16 *, unsigned int, void **Src, const unsigned __int16 **, unsigned int, char **, const struct _CERT_CONTEXT **)`
- caller_count: `0`
- callee_count: `16`
- tags: `loader_planting`

## callees

- `0x18000220c`
- `0x180002306`
- `0x180015a88`
- `0x1800160e4`
- `0x180017a5c`
- `0x180017e6c`
- `0x180017ee0`
- `0x180018310`
- `0x180018d44`
- `0x180019128`
- `0x18001c98c`
- `0x180021438`
- `0x1800217d4`
- `0x1800396f2`
- `0x180039740`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800186eb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800186eb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180018757`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180018757`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800184db`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018504`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800184db`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018504`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001878b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001879a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800187a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800187b2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001878b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001879a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800187a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800187b2`
- `CRYPT32!CertOpenStore` at `0x1800185b2`
- `CRYPT32!CertOpenStore` at `0x1800185b2`
- `CRYPT32!CertCloseStore` at `0x18001877c`
- `CRYPT32!CertCloseStore` at `0x18001877c`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180018416`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180018435`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180018494`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800184be`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800185cf`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180018704`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180018416`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180018435`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180018494`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800184be`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x1800185cf`
- `certca!__imp_?CSPrintErrorLineFile@@YAXKJ@Z` at `0x180018704`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18001861d`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180018745`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x18001861d`
- `certca!__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z` at `0x180018745`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!LoadCursorW` at `0x18001845b`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!LoadCursorW` at `0x18001845b`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!SetCursor` at `0x180018464`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!SetCursor` at `0x18001849e`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!SetCursor` at `0x180018464`
- `ext-ms-win-rtcore-ntuser-cursor-l1-1-0!SetCursor` at `0x18001849e`

## string_xrefs

- `0x1800186b5`: `CryptUI.dll`
- `0x1800186d5`: `CryptUI.dll`

## pseudocode

```c
__int64 __fastcall myGetCertificateFromPicker(
        HINSTANCE a1,
        HWND a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned __int16 *a6,
        unsigned int a7,
        void **Src,
        const unsigned __int16 **a9,
        unsigned int a10,
        char **a11,
        const struct _CERT_CONTEXT **a12)
{
  char *v15; // r15
  int RCString; // eax
  int v17; // eax
  __int64 v18; // rsi
  unsigned int v19; // ebx
  HCURSOR CursorW; // rax
  HCURSOR v21; // rbx
  int v22; // eax
  unsigned int v23; // ebx
  int v24; // edx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  void **v27; // rsi
  unsigned __int16 **v28; // r13
  size_t v29; // rdi
  __int64 v30; // rbx
  char *v31; // rcx
  void *v32; // rdx
  unsigned int v33; // r8d
  unsigned int v34; // eax
  unsigned int v35; // ecx
  unsigned int v36; // edx
  unsigned int v37; // eax
  unsigned int v38; // edx
  const unsigned __int16 *v39; // rcx
  HMODULE v40; // rdi
  const struct _CERT_CONTEXT *v41; // rax
  HMODULE System32Library; // rax
  FARPROC ProcAddress; // rax
  __int64 v44; // rax
  unsigned int v46; // [rsp+30h] [rbp-D0h] BYREF
  void **v47; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 **v48; // [rsp+40h] [rbp-C0h] BYREF
  const struct _CERT_CONTEXT **v49; // [rsp+48h] [rbp-B8h]
  void *v50; // [rsp+50h] [rbp-B0h]
  HWND v51; // [rsp+58h] [rbp-A8h]
  char **v52; // [rsp+60h] [rbp-A0h]
  unsigned int *v53; // [rsp+68h] [rbp-98h]
  int v54; // [rsp+70h] [rbp-90h] BYREF
  HWND v55; // [rsp+78h] [rbp-88h]
  int v56; // [rsp+80h] [rbp-80h]
  HLOCAL hMem; // [rsp+88h] [rbp-78h] BYREF
  HLOCAL v58[4]; // [rsp+98h] [rbp-68h] BYREF
  unsigned int v59; // [rsp+B8h] [rbp-48h]
  HLOCAL v60; // [rsp+C0h] [rbp-40h]
  _DWORD v61[2]; // [rsp+F0h] [rbp-10h] BYREF
  char *v62; // [rsp+F8h] [rbp-8h]
  int v63; // [rsp+100h] [rbp+0h]
  HCERTSTORE hCertStore; // [rsp+108h] [rbp+8h]
  unsigned int v65; // [rsp+110h] [rbp+10h] BYREF
  int v66; // [rsp+114h] [rbp+14h]
  __int64 v67; // [rsp+118h] [rbp+18h]
  _BYTE v68[16]; // [rsp+120h] [rbp+20h] BYREF
  __int64 v69; // [rsp+130h] [rbp+30h]
  __int64 v70; // [rsp+138h] [rbp+38h]

  v51 = a2;
  v46 = a7;
  v50 = a9;
  v52 = a11;
  v49 = a12;
  v15 = 0;
  v47 = 0;
  v48 = 0;
  v53 = &v65;
  v67 = 0;
  `eh vector constructor iterator'(
    v68,
    8u,
    2u,
    (void (*)(void *))CERTFILTERSTRING::CERTFILTERSTRING,
    (void (*)(void *))CERTFILTERSTRING::~CERTFILTERSTRING);
  v69 = 0;
  v70 = 0;
  memset_0(v61, 0, 0xB0u);
  memset_0(&v54, 0, 0x80u);
  if ( a1 )
  {
    RCString = myLoadRCString(a1, a3, (unsigned __int16 **)&hMem);
    if ( RCString )
      CSPrintErrorLineFile(0xCEE019Bu, RCString);
    v17 = myLoadRCString(a1, a4, (unsigned __int16 **)v58);
    if ( v17 )
      CSPrintErrorLineFile(0xCF7019Bu, v17);
  }
  v18 = 0;
  if ( Src )
    v18 = v46;
  v19 = 0;
  v46 = 0;
  if ( (a5 & 0x7001F) != 0 )
  {
    CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
    v21 = SetCursor(CursorW);
    v53 = (unsigned int *)v21;
    v22 = myOpenCertStores(a5, &v46, &v47, (const unsigned __int16 ***)&v48);
    if ( v22 )
      CSPrintErrorLineFile(0xD0B019Bu, v22);
    SetCursor(v21);
    v19 = v46;
  }
  v59 = v18 + v19;
  if ( !((_DWORD)v18 + v19) )
  {
    v23 = -2147024894;
    v24 = -2147024894;
    v25 = 219218331;
LABEL_14:
    CSPrintErrorLineFile(v25, v24);
    v27 = v47;
    v28 = v48;
    goto LABEL_56;
  }
  v60 = LocalAlloc(0, 8LL * ((unsigned int)v18 + v19));
  if ( !v60 )
  {
    v24 = -2147024882;
    v23 = -2147024882;
    v25 = 219742619;
    goto LABEL_14;
  }
  v15 = (char *)LocalAlloc(0x40u, 8LL * v59);
  if ( !v15 )
  {
    v24 = -2147024882;
    v23 = -2147024882;
    v25 = 220266907;
    goto LABEL_14;
  }
  if ( (_DWORD)v18 )
  {
    memcpy_0(v60, Src, 8 * v18);
    if ( v50 )
      memcpy_0(v15, v50, 8 * v18);
  }
  if ( v19 )
  {
    v29 = 8LL * v19;
    v30 = (unsigned int)v18;
    v31 = (char *)v60 + 8 * v18;
    v27 = v47;
    memcpy_0(v31, v47, v29);
    v28 = v48;
    memcpy_0(&v15[8 * v30], v48, v29);
  }
  else
  {
    v27 = v47;
    v28 = v48;
  }
  hCertStore = CertOpenStore((LPCSTR)2, 1u, 0, 0x2000u, 0);
  if ( !hCertStore )
  {
    v34 = myHLastError();
    v23 = v34;
    v35 = 222953883;
LABEL_27:
    v36 = v34;
LABEL_28:
    CSPrintErrorLineFile(v35, v36);
    goto LABEL_56;
  }
  v54 = 128;
  v55 = v51;
  v58[1] = CertificateFilterProc;
  v61[0] = a5;
  if ( a6 )
  {
    v37 = myBuildFilterContent(a6, (bool)v32, (struct _CERTFILTERDATA *)&v65);
    v23 = v37;
    if ( v37 )
    {
      v38 = 224002459;
      v39 = a6;
LABEL_32:
      CSPrintErrorLineFileData(v39, v38, v37);
      goto LABEL_56;
    }
  }
  if ( a10 )
  {
    v34 = cpAddEKUORFilter(a10, (const char *const *)v52, (struct _CERTFILTERDATA *)&v65);
    v23 = v34;
    if ( v34 )
    {
      v35 = 224526747;
      goto LABEL_27;
    }
    v66 |= 8u;
  }
  v65 = a5 & 0xAE070000;
  v61[1] = v59;
  v62 = v15;
  v63 = 1;
  v58[3] = v61;
  if ( (a5 & 0x40000000) != 0 )
  {
    v40 = 0;
    v41 = mySelectCertificate(a5, (struct tagCRYPTUI_SELECTCERTIFICATE_STRUCTW *)&v54);
    v26 = (unsigned int)v49;
    *v49 = v41;
    if ( !v41 )
    {
      v23 = myHLastError();
      if ( !v23 )
        v23 = -2146885628;
      v36 = v23;
      v35 = 226296219;
      goto LABEL_28;
    }
  }
  else
  {
    System32Library = myLoadSystem32LibraryEx(L"CryptUI.dll", v32, v33);
    v40 = System32Library;
    if ( !System32Library )
    {
      v37 = myHLastError();
      v23 = v37;
      v38 = 226886043;
      v39 = L"CryptUI.dll";
      goto LABEL_32;
    }
    ProcAddress = GetProcAddress(System32Library, "CryptUIDlgSelectCertificateW");
    if ( !ProcAddress )
    {
      v23 = myHLastError();
      CSPrintErrorLineFile(0xD90019Bu, v23);
LABEL_55:
      FreeLibrary(v40);
      goto LABEL_56;
    }
    if ( g_fLegacyCertSelectionUI )
      v56 |= 0x1000000u;
    v44 = ((__int64 (__fastcall *)(int *))ProcAddress)(&v54);
    v26 = (unsigned int)v49;
    *v49 = (const struct _CERT_CONTEXT *)v44;
  }
  v23 = 0;
  if ( v63 != 1 )
    v23 = v63;
  if ( v23 )
    CSPrintErrorLineFileData(a6, 0xDA1019Bu, v23);
  else
    v23 = 0;
  if ( v40 )
    goto LABEL_55;
LABEL_56:
  myCloseCertStores(v26, v27, (const unsigned __int16 **)v28);
  myFreeFilterContent((struct _CERTFILTERDATA *)&v65);
  if ( hCertStore )
    CertCloseStore(hCertStore, 0);
  if ( hMem )
    LocalFree(hMem);
  if ( v58[0] )
    LocalFree(v58[0]);
  if ( v60 )
    LocalFree(v60);
  LocalFree(v15);
  _CERTFILTERCALLBACKDATA::~_CERTFILTERCALLBACKDATA((_CERTFILTERCALLBACKDATA *)v61);
  return v23;
}

```

## disassembly

```asm
0x180018310  push    rbp
0x180018312  push    rbx
0x180018313  push    rsi
0x180018314  push    rdi
0x180018315  push    r12
0x180018317  push    r13
0x180018319  push    r14
0x18001831b  push    r15
0x18001831d  lea     rbp, [rsp-0B8h]
0x180018325  sub     rsp, 1B8h
0x18001832c  mov     rax, cs:__security_cookie
0x180018333  xor     rax, rsp
0x180018336  mov     [rbp+0F0h+var_50], rax
0x18001833d  mov     esi, r9d
0x180018340  mov     edi, r8d
0x180018343  mov     [rsp+1F0h+var_198], rdx
0x180018348  mov     rbx, rcx
0x18001834b  mov     eax, [rbp+0F0h+arg_30]
0x180018351  mov     [rsp+1F0h+var_1C0], eax
0x180018355  mov     r14d, [rbp+0F0h+arg_20]
0x18001835c  mov     r12, [rbp+0F0h+arg_28]
0x180018363  mov     r13, [rbp+0F0h+Src]
0x18001836a  mov     rax, [rbp+0F0h+arg_40]
0x180018371  mov     [rsp+1F0h+var_1A0], rax
0x180018376  mov     rax, [rbp+0F0h+arg_50]
0x18001837d  mov     [rsp+1F0h+var_190], rax
0x180018382  mov     rax, [rbp+0F0h+arg_58]
0x180018389  mov     [rsp+1F0h+var_1A8], rax
0x18001838e  xor     r15d, r15d
0x180018391  mov     [rsp+1F0h+var_1B8], r15
0x180018396  mov     [rsp+1F0h+var_1B0], r15
0x18001839b  lea     rax, [rbp+0F0h+var_E0]
0x18001839f  mov     [rsp+1F0h+var_188], rax
0x1800183a4  mov     [rbp+0F0h+var_D8], r15
0x1800183a8  lea     rax, ??1CERTFILTERSTRING@@QEAA@XZ; CERTFILTERSTRING::~CERTFILTERSTRING(void)
0x1800183af  mov     [rsp+1F0h+pvPara], rax; void (*)(void *)
0x1800183b4  lea     r9, ??0CERTFILTERSTRING@@QEAA@XZ; void (*)(void *)
0x1800183bb  lea     edx, [r15+8]; unsigned __int64
0x1800183bf  lea     r8d, [r15+2]; unsigned __int64
0x1800183c3  lea     rcx, [rbp+0F0h+var_D0]; void *
0x1800183c7  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1800183cc  nop
0x1800183cd  mov     [rbp+0F0h+var_C0], r15
0x1800183d1  mov     [rbp+0F0h+var_B8], r15
0x1800183d5  xor     edx, edx; Val
0x1800183d7  mov     r8d, 0B0h; Size
0x1800183dd  lea     rcx, [rbp+0F0h+var_100]; void *
0x1800183e1  call    memset_0
0x1800183e6  xor     edx, edx; Val
0x1800183e8  mov     r8d, 80h; Size
0x1800183ee  lea     rcx, [rsp+1F0h+var_180]; void *
0x1800183f3  call    memset_0
0x1800183f8  test    rbx, rbx
0x1800183fb  jz      short loc_18001843B
0x1800183fd  lea     r8, [rbp+0F0h+hMem]; unsigned __int16 **
0x180018401  mov     edx, edi; unsigned int
0x180018403  mov     rcx, rbx; HINSTANCE
0x180018406  call    ?myLoadRCString@@YAJPEAUHINSTANCE__@@KPEAPEAG@Z; myLoadRCString(HINSTANCE__ *,ulong,ushort * *)
0x18001840b  test    eax, eax
0x18001840d  jz      short loc_18001841C
0x18001840f  mov     edx, eax
0x180018411  mov     ecx, 0CEE019Bh
0x180018416  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001841c  lea     r8, [rbp+0F0h+var_158]; unsigned __int16 **
0x180018420  mov     edx, esi; unsigned int
0x180018422  mov     rcx, rbx; HINSTANCE
0x180018425  call    ?myLoadRCString@@YAJPEAUHINSTANCE__@@KPEAPEAG@Z; myLoadRCString(HINSTANCE__ *,ulong,ushort * *)
0x18001842a  test    eax, eax
0x18001842c  jz      short loc_18001843B
0x18001842e  mov     edx, eax
0x180018430  mov     ecx, 0CF7019Bh
0x180018435  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001843b  xor     esi, esi
0x18001843d  test    r13, r13
0x180018440  cmovnz  esi, [rsp+1F0h+var_1C0]
0x180018445  xor     ebx, ebx
0x180018447  mov     [rsp+1F0h+var_1C0], ebx
0x18001844b  test    r14d, 7001Fh
0x180018452  jz      short loc_1800184A8
0x180018454  mov     edx, 7F02h; lpCursorName
0x180018459  xor     ecx, ecx; hInstance
0x18001845b  call    cs:__imp_LoadCursorW
0x180018461  mov     rcx, rax; hCursor
0x180018464  call    cs:__imp_SetCursor
0x18001846a  mov     rbx, rax
0x18001846d  mov     [rsp+1F0h+var_188], rax
0x180018472  lea     r9, [rsp+1F0h+var_1B0]; unsigned __int16 ***
0x180018477  lea     r8, [rsp+1F0h+var_1B8]; void ***
0x18001847c  lea     rdx, [rsp+1F0h+var_1C0]; unsigned int *
0x180018481  mov     ecx, r14d; unsigned int
0x180018484  call    ?myOpenCertStores@@YAJKPEAKPEAPEAPEAXPEAPEAPEBG@Z; myOpenCertStores(ulong,ulong *,void * * *,ushort const * * *)
0x180018489  test    eax, eax
0x18001848b  jz      short loc_18001849B
0x18001848d  mov     edx, eax
0x18001848f  mov     ecx, 0D0B019Bh
0x180018494  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001849a  nop
0x18001849b  mov     rcx, rbx; hCursor
0x18001849e  call    cs:__imp_SetCursor
0x1800184a4  mov     ebx, [rsp+1F0h+var_1C0]
0x1800184a8  lea     eax, [rsi+rbx]
0x1800184ab  mov     [rbp+0F0h+var_138], eax
0x1800184ae  test    eax, eax
0x1800184b0  jnz     short loc_1800184D3
0x1800184b2  mov     ebx, 80070002h
0x1800184b7  mov     edx, ebx
0x1800184b9  mov     ecx, 0D11019Bh
0x1800184be  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800184c4  mov     rsi, [rsp+1F0h+var_1B8]
0x1800184c9  mov     r13, [rsp+1F0h+var_1B0]
0x1800184ce  jmp     loc_18001875D
0x1800184d3  mov     edx, eax
0x1800184d5  shl     rdx, 3; uBytes
0x1800184d9  xor     ecx, ecx; uFlags
0x1800184db  call    cs:__imp_LocalAlloc
0x1800184e1  mov     [rbp+0F0h+var_130], rax
0x1800184e5  test    rax, rax
0x1800184e8  jnz     short loc_1800184F8
0x1800184ea  mov     edx, 8007000Eh
0x1800184ef  mov     ebx, edx
0x1800184f1  mov     ecx, 0D19019Bh
0x1800184f6  jmp     short loc_1800184BE
0x1800184f8  mov     edx, [rbp+0F0h+var_138]
0x1800184fb  shl     rdx, 3; uBytes
0x1800184ff  mov     ecx, 40h ; '@'; uFlags
0x180018504  call    cs:__imp_LocalAlloc
0x18001850a  mov     r15, rax
0x18001850d  test    rax, rax
0x180018510  jnz     short loc_180018520
0x180018512  mov     edx, 8007000Eh
0x180018517  mov     ebx, edx
0x180018519  mov     ecx, 0D21019Bh
0x18001851e  jmp     short loc_1800184BE
0x180018520  test    esi, esi
0x180018522  jz      short loc_180018553
0x180018524  lea     rdi, ds:0[rsi*8]
0x18001852c  mov     r8, rdi; Size
0x18001852f  mov     rdx, r13; Src
0x180018532  mov     rcx, [rbp+0F0h+var_130]; void *
0x180018536  call    memcpy_0
0x18001853b  mov     rax, [rsp+1F0h+var_1A0]
0x180018540  test    rax, rax
0x180018543  jz      short loc_180018553
0x180018545  mov     r8, rdi; Size
0x180018548  mov     rdx, rax; Src
0x18001854b  mov     rcx, r15; void *
0x18001854e  call    memcpy_0
0x180018553  test    ebx, ebx
0x180018555  jz      short loc_18001858D
0x180018557  mov     edi, ebx
0x180018559  shl     rdi, 3
0x18001855d  mov     ebx, esi
0x18001855f  mov     rax, [rbp+0F0h+var_130]
0x180018563  lea     rcx, [rax+rsi*8]; void *
0x180018567  mov     r8, rdi; Size
0x18001856a  mov     rsi, [rsp+1F0h+var_1B8]
0x18001856f  mov     rdx, rsi; Src
0x180018572  call    memcpy_0
0x180018577  lea     rcx, [r15+rbx*8]; void *
0x18001857b  mov     r8, rdi; Size
0x18001857e  mov     r13, [rsp+1F0h+var_1B0]
0x180018583  mov     rdx, r13; Src
0x180018586  call    memcpy_0
0x18001858b  jmp     short loc_180018597
0x18001858d  mov     rsi, [rsp+1F0h+var_1B8]
0x180018592  mov     r13, [rsp+1F0h+var_1B0]
0x180018597  mov     [rsp+1F0h+pvPara], 0; pvPara
0x1800185a0  mov     r9d, 2000h; dwFlags
0x1800185a6  xor     r8d, r8d; hCryptProv
0x1800185a9  lea     edi, [r8+1]
0x1800185ad  mov     edx, edi; dwEncodingType
0x1800185af  lea     ecx, [rdi+1]; lpszStoreProvider
0x1800185b2  call    cs:__imp_CertOpenStore
0x1800185b8  mov     [rbp+0F0h+hCertStore], rax
0x1800185bc  test    rax, rax
0x1800185bf  jnz     short loc_1800185DA
0x1800185c1  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x1800185c6  mov     ebx, eax
0x1800185c8  mov     ecx, 0D4A019Bh
0x1800185cd  mov     edx, eax
0x1800185cf  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800185d5  jmp     loc_18001875D
0x1800185da  mov     [rsp+1F0h+var_180], 80h
0x1800185e2  mov     rax, [rsp+1F0h+var_198]
0x1800185e7  mov     [rsp+1F0h+var_178], rax
0x1800185ec  lea     rax, ?CertificateFilterProc@@YAHPEBU_CERT_CONTEXT@@PEAHPEAX@Z; CertificateFilterProc(_CERT_CONTEXT const *,int *,void *)
0x1800185f3  mov     [rbp+0F0h+var_150], rax
0x1800185f7  mov     [rbp+0F0h+var_100], r14d
0x1800185fb  test    r12, r12
0x1800185fe  jz      short loc_180018628
0x180018600  lea     r8, [rbp+0F0h+var_E0]; struct _CERTFILTERDATA *
0x180018604  mov     rcx, r12; unsigned __int16 *
0x180018607  call    ?myBuildFilterContent@@YAJPEBG_NPEAU_CERTFILTERDATA@@@Z; myBuildFilterContent(ushort const *,bool,_CERTFILTERDATA *)
0x18001860c  mov     ebx, eax
0x18001860e  test    eax, eax
0x180018610  jz      short loc_180018628
0x180018612  mov     edx, 0D5A019Bh
0x180018617  mov     rcx, r12
0x18001861a  mov     r8d, eax
0x18001861d  call    cs:__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z; CSPrintErrorLineFileData(ushort const *,ulong,long)
0x180018623  jmp     loc_18001875D
0x180018628  mov     ecx, [rbp+0F0h+arg_48]; unsigned int
0x18001862e  test    ecx, ecx
0x180018630  jz      short loc_180018651
0x180018632  lea     r8, [rbp+0F0h+var_E0]; struct _CERTFILTERDATA *
0x180018636  mov     rdx, [rsp+1F0h+var_190]; char **
0x18001863b  call    ?cpAddEKUORFilter@@YAJKPEBQEBDPEAU_CERTFILTERDATA@@@Z; cpAddEKUORFilter(ulong,char const * const *,_CERTFILTERDATA *)
0x180018640  mov     ebx, eax
0x180018642  test    eax, eax
0x180018644  jz      short loc_18001864D
0x180018646  mov     ecx, 0D62019Bh
0x18001864b  jmp     short loc_1800185CD
0x18001864d  or      [rbp+0F0h+var_DC], 8
0x180018651  mov     eax, r14d
0x180018654  and     eax, 0AE070000h
0x180018659  mov     [rbp+0F0h+var_E0], eax
0x18001865c  mov     eax, [rbp+0F0h+var_138]
0x18001865f  mov     [rbp+0F0h+var_FC], eax
0x180018662  mov     [rbp+0F0h+var_F8], r15
0x180018666  mov     [rbp+0F0h+var_F0], edi
0x180018669  lea     rax, [rbp+0F0h+var_100]
0x18001866d  mov     [rbp+0F0h+var_140], rax
0x180018671  bt      r14d, 1Eh
0x180018676  jnb     short loc_1800186B5
0x180018678  xor     edi, edi
0x18001867a  lea     rdx, [rsp+1F0h+var_180]; struct tagCRYPTUI_SELECTCERTIFICATE_STRUCTW *
0x18001867f  mov     ecx, r14d; unsigned int
0x180018682  call    ?mySelectCertificate@@YAPEBU_CERT_CONTEXT@@KPEAUtagCRYPTUI_SELECTCERTIFICATE_STRUCTW@@@Z; mySelectCertificate(ulong,tagCRYPTUI_SELECTCERTIFICATE_STRUCTW *)
0x180018687  mov     rcx, [rsp+1F0h+var_1A8]
0x18001868c  mov     [rcx], rax
0x18001868f  test    rax, rax
0x180018692  jnz     loc_18001872C
0x180018698  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x18001869d  mov     ebx, eax
0x18001869f  mov     eax, 80092004h
0x1800186a4  test    ebx, ebx
0x1800186a6  cmovz   ebx, eax
0x1800186a9  mov     edx, ebx
0x1800186ab  mov     ecx, 0D7D019Bh
0x1800186b0  jmp     loc_1800185CF
0x1800186b5  lea     rcx, aCryptuiDll_0; "CryptUI.dll"
0x1800186bc  call    ?myLoadSystem32LibraryEx@@YAPEAUHINSTANCE__@@PEBGPEAXK@Z; myLoadSystem32LibraryEx(ushort const *,void *,ulong)
0x1800186c1  mov     rdi, rax
0x1800186c4  test    rax, rax
0x1800186c7  jnz     short loc_1800186E1
0x1800186c9  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x1800186ce  mov     ebx, eax
0x1800186d0  mov     edx, 0D86019Bh
0x1800186d5  lea     rcx, aCryptuiDll_0; "CryptUI.dll"
0x1800186dc  jmp     loc_18001861A
0x1800186e1  lea     rdx, aCryptuidlgsele; "CryptUIDlgSelectCertificateW"
0x1800186e8  mov     rcx, rax; hModule
0x1800186eb  call    cs:__imp_GetProcAddress
0x1800186f1  test    rax, rax
0x1800186f4  jnz     short loc_18001870C
0x1800186f6  call    ?myHLastError@@YAJXZ; myHLastError(void)
0x1800186fb  mov     ebx, eax
0x1800186fd  mov     edx, eax
0x1800186ff  mov     ecx, 0D90019Bh
0x180018704  call    cs:__imp_?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x18001870a  jmp     short loc_180018754
0x18001870c  cmp     cs:?g_fLegacyCertSelectionUI@@3_NA, 0; bool g_fLegacyCertSelectionUI
0x180018713  jz      short loc_18001871A
0x180018715  bts     [rbp+0F0h+var_170], 18h
0x18001871a  lea     rcx, [rsp+1F0h+var_180]
0x18001871f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018724  mov     rcx, [rsp+1F0h+var_1A8]
0x180018729  mov     [rcx], rax
0x18001872c  xor     ebx, ebx
0x18001872e  cmp     [rbp+0F0h+var_F0], 1
0x180018732  cmovnz  ebx, [rbp+0F0h+var_F0]
0x180018736  test    ebx, ebx
0x180018738  jz      short loc_18001874D
0x18001873a  mov     r8d, ebx
0x18001873d  mov     edx, 0DA1019Bh
0x180018742  mov     rcx, r12
0x180018745  call    cs:__imp_?CSPrintErrorLineFileData@@YAXPEBGKJ@Z; CSPrintErrorLineFileData(ushort const *,ulong,long)
0x18001874b  jmp     short loc_18001874F
0x18001874d  xor     ebx, ebx
0x18001874f  test    rdi, rdi
0x180018752  jz      short loc_18001875D
0x180018754  mov     rcx, rdi; hLibModule
0x180018757  call    cs:__imp_FreeLibrary
0x18001875d  mov     r8, r13; unsigned __int16 **
0x180018760  mov     rdx, rsi; void **
0x180018763  call    ?myCloseCertStores@@YAXKPEAPEAXPEAPEBG@Z; myCloseCertStores(ulong,void * *,ushort const * *)
0x180018768  lea     rcx, [rbp+0F0h+var_E0]; struct _CERTFILTERDATA *
0x18001876c  call    ?myFreeFilterContent@@YAXPEAU_CERTFILTERDATA@@@Z; myFreeFilterContent(_CERTFILTERDATA *)
0x180018771  mov     rcx, [rbp+0F0h+hCertStore]; hCertStore
0x180018775  test    rcx, rcx
0x180018778  jz      short loc_180018782
0x18001877a  xor     edx, edx; dwFlags
0x18001877c  call    cs:__imp_CertCloseStore
0x180018782  mov     rcx, [rbp+0F0h+hMem]; hMem
0x180018786  test    rcx, rcx
0x180018789  jz      short loc_180018791
0x18001878b  call    cs:__imp_LocalFree
0x180018791  mov     rcx, [rbp+0F0h+var_158]; hMem
0x180018795  test    rcx, rcx
0x180018798  jz      short loc_1800187A0
  ... truncated ...
```
