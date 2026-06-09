# ConfigDSNW

- ea: `0x10053ffb0`
- end: `0x100540502`
- name: `ConfigDSNW`
- size: `1362`
- prototype: `BOOL __stdcall(HWND hwndParent, WORD fRequest, LPCWSTR lpszDriver, LPCWSTR lpszAttributes)`
- caller_count: `0`
- callee_count: `23`
- tags: `registry_config, installer_update`

## callees

- `0x1004070bc`
- `0x10046d020`
- `0x10046d140`
- `0x10048b9c4`
- `0x1004e71f4`
- `0x1004e7330`
- `0x1004e7ee8`
- `0x1004e9708`
- `0x1004ea8d8`
- `0x1004eaf58`
- `0x1004eb0b4`
- `0x1004eb81c`
- `0x1004ebd04`
- `0x10051aa9c`
- `0x10053f624`
- `0x10053ffb0`
- `0x100545d74`
- `0x100546f80`
- `0x100547060`
- `0x1005470b0`
- `0x100548140`
- `0x100548210`
- `0x1005495d0`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x100540061`
- `KERNEL32!FormatMessageW` at `0x100540061`
- `USER32!MessageBoxW` at `0x10054036c`
- `USER32!MessageBoxW` at `0x10054036c`
- `USER32!LoadStringW` at `0x100540351`
- `USER32!LoadStringW` at `0x100540351`

## pseudocode

```c
BOOL __stdcall ConfigDSNW(HWND hwndParent, WORD fRequest, LPCWSTR lpszDriver, LPCWSTR lpszAttributes)
{
  int Wizard; // esi
  int v7; // eax
  struct tagDBC *v8; // rdx
  WCHAR *v9; // rdx
  DWORD v10; // ecx
  __int64 v11; // rax
  __int64 v12; // rbx
  unsigned __int64 v13; // r12
  __int64 v14; // rdi
  _WORD *v15; // r15
  int v16; // eax
  struct tagENV **v17; // rdx
  int v18; // eax
  DWORD v19; // ecx
  struct tagDBC **v20; // r8
  __int64 v21; // r12
  __int64 v22; // r13
  _WORD *v23; // rdx
  __int64 v24; // rcx
  _WORD *v25; // rax
  WORD v26; // si
  __int16 v27; // cx
  __int16 v28; // cx
  DWORD v29; // ecx
  const WCHAR *v30; // rsi
  DWORD v31; // eax
  __int64 v32; // rax
  ExportImp *v34; // [rsp+40h] [rbp-C0h] BYREF
  WORD v35; // [rsp+48h] [rbp-B8h]
  _WORD *v36; // [rsp+50h] [rbp-B0h]
  LPCWSTR v37; // [rsp+58h] [rbp-A8h]
  WCHAR szRetBuffer[264]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Buffer[264]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR Text[264]; // [rsp+480h] [rbp+380h] BYREF

  v37 = lpszDriver;
  v35 = fRequest;
  Wizard = 0;
  memset_0(szRetBuffer, 0, 0x20Au);
  memset_0(Buffer, 0, 0x208u);
  v34 = 0;
  v7 = DvrInit();
  if ( v7 )
  {
    if ( v7 != 6 )
      goto LABEL_53;
    FormatMessageW(0xA00u, g_hinstance, 0xC0000001, 0, Buffer, 0x104u, 0);
    v9 = Buffer;
    v10 = 6;
    goto LABEL_4;
  }
  if ( (unsigned int)IsEmbeddedSNAC() )
  {
    v9 = 0;
    v10 = 9;
LABEL_4:
    SQLPostInstallerErrorW(v10, v9);
    goto LABEL_53;
  }
  v11 = ((__int64 (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Release)(g_pMO, 1824);
  v12 = v11;
  if ( !v11 )
  {
    v12 = 0;
    v14 = 136;
LABEL_47:
    SQLPostInstallerErrorW(0x15u, 0);
    Wizard = 0;
    if ( !v12 )
      goto LABEL_53;
    goto LABEL_48;
  }
  v13 = -1;
  *(_DWORD *)(v11 + 96) = 0;
  *(_DWORD *)(v11 + 160) = -1;
  *(_DWORD *)(v11 + 168) = -1;
  *(_WORD *)(v11 + 136) = 0;
  *(_QWORD *)(v11 + 144) = 0;
  *(_QWORD *)(v11 + 152) = 0;
  *(_DWORD *)(v11 + 164) = 0;
  *(_DWORD *)(v11 + 172) = 0;
  memset_0((void *)v11, 0, 0x88u);
  v14 = v12 + 136;
  *(_WORD *)(v12 + 258) = 0;
  v15 = (_WORD *)(v12 + 192);
  *(_WORD *)(v12 + 1540) = 0;
  *(_WORD *)(v12 + 192) = 0;
  v16 = CDlgATTRs::FInit(
          (CDlgATTRs *)(v12 + 136),
          0x3Au,
          (const struct tagATTRSTOSECURE *)&g_AttrsToSecure,
          0x3E8u,
          0x200u);
  v17 = 0;
  if ( !v16 )
    goto LABEL_47;
  *(_DWORD *)(v12 + 4) = 7;
  *(_WORD *)(v12 + 120) |= 0x40u;
  v36 = (_WORD *)(v12 + 120);
  if ( !lpszAttributes )
    goto LABEL_58;
  do
    ++v13;
  while ( lpszAttributes[v13] );
  v18 = ParseAttrStr(0, lpszAttributes, v13, 0, (struct CDlgATTRs *)(v12 + 136), 0x1BFEFFFFFFFF92CuLL);
  lpszAttributes = 0;
  if ( !v18 )
  {
LABEL_58:
    if ( ExportImp::SQLAllocEnv((ExportImp *)&v34, v17)
      || (*((_QWORD *)v34 + 13) = 3, ExportImp::SQLAllocConnect(v34, (struct tagENV *)(v12 + 64), v20)) )
    {
      v19 = 21;
      goto LABEL_13;
    }
    v34 = (ExportImp *)lpszAttributes;
    if ( (int)FillAttrStructFromDSN(*(struct tagDBC **)(v12 + 64), (struct tagDLGSTRUCT *)v12, hwndParent) >= 0 )
    {
      _mm_lfence();
      v21 = v12 + 144;
      v22 = v12 + 152;
      if ( (*(_BYTE *)(*(_QWORD *)(v12 + 144) + 48LL) & 1) != 0 )
      {
        _mm_lfence();
        v23 = (_WORD *)(*(_QWORD *)(*(_QWORD *)v21 + 56LL) + *(_QWORD *)(*(_QWORD *)v22 + 32LL));
        v24 = 33;
        do
        {
          if ( v24 == -2147483613 )
            break;
          if ( !*v23 )
            break;
          *v15++ = *v23++;
          --v24;
        }
        while ( v24 );
        v25 = v15 - 1;
        if ( v24 )
          v25 = v15;
        *v25 = 0;
        if ( !v24 )
        {
          v19 = 8;
          goto LABEL_13;
        }
      }
      else
      {
        *v15 = 0;
      }
      v26 = v35;
      v27 = 0;
      if ( v35 == 1 )
        v27 = 32;
      v28 = *v36 & 0xFFDF | v27;
      *v36 = v28;
      if ( (v28 & 0x20) != 0
        || (_mm_lfence(),
            SQLGetPrivateProfileStringW(
              (LPCWSTR)(*(_QWORD *)(*(_QWORD *)v21 + 56LL) + *(_QWORD *)(*(_QWORD *)v22 + 32LL)),
              0,
              &szDefault,
              szRetBuffer,
              261,
              L"ODBC.INI")) )
      {
        if ( v26 == 3 )
        {
          _mm_lfence();
          v30 = (const WCHAR *)(*(_QWORD *)(*(_QWORD *)v21 + 56LL) + *(_QWORD *)(*(_QWORD *)v22 + 32LL));
          SQLGetPrivateProfileStringW(v30, L"Server", v30, szRetBuffer, 261, L"ODBC.INI");
          if ( CDlgATTRs::SetATTRValue((CDlgATTRs *)(v12 + 136), 5, szRetBuffer) < 0 )
            SQLPostInstallerErrorW(0x15u, 0);
          SQLRemoveDSNFromIniW(v30);
          Wizard = 1;
          goto LABEL_48;
        }
        *(_QWORD *)(v12 + 104) = v37;
        *(_QWORD *)(v12 + 56) = hwndParent;
        if ( hwndParent )
        {
          _mm_lfence();
          Wizard = CreateWizard(hwndParent, (struct tagDLGSTRUCT *)v12);
          if ( !Wizard )
          {
            v19 = 16;
            goto LABEL_13;
          }
        }
        else
        {
          Wizard = 1;
        }
        _mm_lfence();
        v31 = SaveDSNAttributes(0, (struct tagDLGSTRUCT *)v12, 0);
        if ( !v31 )
          goto LABEL_48;
        _mm_lfence();
        v29 = v31;
      }
      else
      {
        if ( hwndParent )
        {
          _mm_lfence();
          LoadFormattedMessage(
            g_hinstance_language,
            0x9C4Fu,
            Text,
            0x105u,
            *(_QWORD *)(*(_QWORD *)v21 + 56LL) + *(_QWORD *)(*(_QWORD *)v22 + 32LL));
          LoadStringW(g_hinstance_language, 0x9C4Cu, szRetBuffer, 261);
          MessageBoxW(hwndParent, Text, szRetBuffer, 0x30u);
        }
        v29 = 9;
      }
      SQLPostInstallerErrorW(v29, 0);
      Wizard = 0;
      goto LABEL_48;
    }
  }
  v19 = 8;
LABEL_13:
  SQLPostInstallerErrorW(v19, 0);
LABEL_48:
  v32 = *(_QWORD *)(v12 + 64);
  if ( v32 )
  {
    v34 = *(ExportImp **)(v32 + 88);
    if ( *(_QWORD *)(*(_QWORD *)(v12 + 64) + 64LL) )
      ExportImp::SQLDisconnect(*(ExportImp **)(v12 + 64), v8);
    ExportImp::SQLFreeConnect(*(ExportImp **)(v12 + 64), v8);
    *(_QWORD *)(v12 + 64) = 0;
  }
  CDlgATTRs::Uninitialize((CDlgATTRs *)v14);
  ((void (__fastcall *)(struct IMalloc *, __int64))g_pMO->lpVtbl[1].Realloc)(g_pMO, v12);
LABEL_53:
  if ( v34 )
    ExportImp::SQLFreeEnv(v34, v8);
  DrvTerm();
  return Wizard;
}

```

## disassembly

```asm
0x10053ffb0  mov     [rsp-8+arg_8], rbx
0x10053ffb5  push    rbp
0x10053ffb6  push    rsi
0x10053ffb7  push    rdi
0x10053ffb8  push    r12
0x10053ffba  push    r13
0x10053ffbc  push    r14
0x10053ffbe  push    r15
0x10053ffc0  lea     rbp, [rsp-5A0h]
0x10053ffc8  sub     rsp, 6A0h
0x10053ffcf  mov     rax, cs:__security_cookie
0x10053ffd6  xor     rax, rsp
0x10053ffd9  mov     [rbp+5D0h+var_40], rax
0x10053ffe0  mov     [rsp+6D0h+var_678], r8
0x10053ffe5  mov     r14, rcx
0x10053ffe8  mov     [rsp+6D0h+var_688], dx
0x10053ffed  lea     rcx, [rsp+6D0h+szRetBuffer]; void *
0x10053fff2  xor     r15d, r15d
0x10053fff5  xor     edx, edx; Val
0x10053fff7  mov     r8d, 20Ah; Size
0x10053fffd  mov     esi, r15d
0x100540000  mov     r13, r9
0x100540003  call    memset_0
0x100540008  xor     edx, edx; Val
0x10054000a  lea     rcx, [rbp+5D0h+Buffer]; void *
0x100540011  mov     r8d, 208h; Size
0x100540017  call    memset_0
0x10054001c  mov     [rsp+6D0h+var_690], r15
0x100540021  call    ?DvrInit@@YAKXZ; DvrInit(void)
0x100540026  test    eax, eax
0x100540028  jz      short loc_10054007C
0x10054002a  cmp     eax, 6
0x10054002d  jnz     loc_1005404C2
0x100540033  mov     rdx, cs:?g_hinstance@@3PEAUHINSTANCE__@@EA; lpSource
0x10054003a  lea     rax, [rbp+5D0h+Buffer]
0x100540041  mov     [rsp+6D0h+Arguments], r15; Arguments
0x100540046  xor     r9d, r9d; dwLanguageId
0x100540049  mov     [rsp+6D0h+nSize], 104h; nSize
0x100540051  mov     r8d, 0C0000001h; dwMessageId
0x100540057  mov     ecx, 0A00h; dwFlags
0x10054005c  mov     [rsp+6D0h+lpBuffer], rax; lpBuffer
0x100540061  call    cs:__imp_FormatMessageW
0x100540067  lea     rdx, [rbp+5D0h+Buffer]; lpszErrorMsg
0x10054006e  lea     ecx, [r15+6]; dwErrorCode
0x100540072  call    SQLPostInstallerErrorW
0x100540077  jmp     loc_1005404C2
0x10054007c  call    ?IsEmbeddedSNAC@@YAHXZ; IsEmbeddedSNAC(void)
0x100540081  test    eax, eax
0x100540083  jz      short loc_10054008C
0x100540085  xor     edx, edx
0x100540087  lea     ecx, [rdx+9]
0x10054008a  jmp     short loc_100540072
0x10054008c  mov     rcx, cs:?g_pMO@@3PEAUISOSHost_MemObj@@EA; ISOSHost_MemObj * g_pMO
0x100540093  mov     edx, 720h
0x100540098  mov     rax, [rcx]
0x10054009b  mov     rax, [rax+58h]
0x10054009f  call    cs:__guard_dispatch_icall_fptr
0x1005400a5  mov     rbx, rax
0x1005400a8  test    rax, rax
0x1005400ab  jz      loc_10054044F
0x1005400b1  or      r12, 0FFFFFFFFFFFFFFFFh
0x1005400b5  mov     [rax+60h], r15d
0x1005400b9  xor     edx, edx; Val
0x1005400bb  mov     [rax+0A0h], r12d
0x1005400c2  mov     r8d, 88h; Size
0x1005400c8  mov     [rax+0A8h], r12d
0x1005400cf  mov     rcx, rax; void *
0x1005400d2  mov     [rax+88h], r15w
0x1005400da  mov     [rax+90h], r15
0x1005400e1  mov     [rax+98h], r15
0x1005400e8  mov     [rax+0A4h], r15d
0x1005400ef  mov     [rax+0ACh], r15d
0x1005400f6  call    memset_0
0x1005400fb  xor     eax, eax
0x1005400fd  mov     [rsp+6D0h+lpBuffer], 200h; unsigned __int64
0x100540106  lea     rdi, [rbx+88h]
0x10054010d  mov     [rbx+102h], ax
0x100540114  lea     r15, [rbx+0C0h]
0x10054011b  mov     [rbx+604h], ax
0x100540122  mov     r9d, 3E8h; unsigned __int64
0x100540128  mov     [r15], ax
0x10054012c  lea     edx, [rax+3Ah]; unsigned __int16
0x10054012f  mov     rcx, rdi; this
0x100540132  lea     r8, ?g_AttrsToSecure@@3UtagATTRSTOSECURE@@B; struct tagATTRSTOSECURE *
0x100540139  call    ?FInit@CDlgATTRs@@QEAAHGAEBUtagATTRSTOSECURE@@_K1@Z; CDlgATTRs::FInit(ushort,tagATTRSTOSECURE const &,unsigned __int64,unsigned __int64)
0x10054013e  xor     edx, edx; struct tagENV **
0x100540140  test    eax, eax
0x100540142  jz      loc_100540459
0x100540148  lea     rcx, [rbx+78h]
0x10054014c  mov     dword ptr [rbx+4], 7
0x100540153  or      word ptr [rcx], 40h
0x100540157  mov     [rsp+6D0h+var_680], rcx
0x10054015c  test    r13, r13
0x10054015f  jz      short loc_1005401AC
0x100540161  inc     r12
0x100540164  cmp     [r13+r12*2+0], dx
0x10054016a  jnz     short loc_100540161
0x10054016c  mov     rax, 1BFEFFFFFFFF92Ch
0x100540176  movzx   r9d, dx; unsigned __int16
0x10054017a  mov     qword ptr [rsp+6D0h+nSize], rax; unsigned __int64
0x10054017f  mov     r8, r12; unsigned __int64
0x100540182  mov     rdx, r13; unsigned __int16 *
0x100540185  mov     [rsp+6D0h+lpBuffer], rdi; struct CDlgATTRs *
0x10054018a  xor     ecx, ecx; struct tagOBJBASE *
0x10054018c  call    ?ParseAttrStr@@YAJPEAUtagOBJBASE@@PEBG_KGAEAVCDlgATTRs@@2@Z; ParseAttrStr(tagOBJBASE *,ushort const *,unsigned __int64,ushort,CDlgATTRs &,unsigned __int64)
0x100540191  xor     r13d, r13d
0x100540194  test    eax, eax
0x100540196  jz      short loc_1005401AC
0x100540198  mov     ecx, 8; dwErrorCode
0x10054019d  xor     edx, edx; lpszErrorMsg
0x10054019f  call    SQLPostInstallerErrorW
0x1005401a4  xor     r15d, r15d
0x1005401a7  jmp     loc_10054046E
0x1005401ac  lea     rcx, [rsp+6D0h+var_690]; this
0x1005401b1  call    ?SQLAllocEnv@ExportImp@@YAFPEAPEAUtagENV@@@Z; ExportImp::SQLAllocEnv(tagENV * *)
0x1005401b6  test    ax, ax
0x1005401b9  jz      short loc_1005401C2
0x1005401bb  mov     ecx, 15h
0x1005401c0  jmp     short loc_10054019D
0x1005401c2  mov     rax, [rsp+6D0h+var_690]
0x1005401c7  lea     rdx, [rbx+40h]; struct tagENV *
0x1005401cb  mov     ecx, 3
0x1005401d0  mov     [rax+68h], rcx
0x1005401d4  mov     rcx, [rsp+6D0h+var_690]; this
0x1005401d9  call    ?SQLAllocConnect@ExportImp@@YAFPEAUtagENV@@PEAPEAUtagDBC@@@Z; ExportImp::SQLAllocConnect(tagENV *,tagDBC * *)
0x1005401de  test    ax, ax
0x1005401e1  jnz     short loc_1005401BB
0x1005401e3  mov     [rsp+6D0h+var_690], r13
0x1005401e8  mov     r8, r14; HWND
0x1005401eb  mov     rcx, [rbx+40h]; struct tagDBC *
0x1005401ef  mov     rdx, rbx; struct tagDLGSTRUCT *
0x1005401f2  call    ?FillAttrStructFromDSN@@YAJPEAUtagDBC@@PEAUtagDLGSTRUCT@@PEAUHWND__@@@Z; FillAttrStructFromDSN(tagDBC *,tagDLGSTRUCT *,HWND__ *)
0x1005401f7  xor     r8d, r8d
0x1005401fa  test    eax, eax
0x1005401fc  js      short loc_100540198
0x1005401fe  lfence
0x100540201  lea     r12, [rbx+90h]
0x100540208  mov     rax, [r12]
0x10054020c  lea     r10d, [r8+1]
0x100540210  lea     r13, [rbx+98h]
0x100540217  test    [rax+30h], r10b
0x10054021b  jz      short loc_100540280
0x10054021d  lfence
0x100540220  mov     rcx, [r12]
0x100540224  mov     rax, [r13+0]
0x100540228  mov     rdx, [rax+20h]
0x10054022c  add     rdx, [rcx+38h]
0x100540230  lea     ecx, [r8+21h]
0x100540234  lea     rax, [rcx+7FFFFFDDh]
0x10054023b  test    rax, rax
0x10054023e  jz      short loc_100540259
0x100540240  movzx   eax, word ptr [rdx]
0x100540243  test    ax, ax
0x100540246  jz      short loc_100540259
0x100540248  mov     [r15], ax
0x10054024c  add     rdx, 2
0x100540250  add     r15, 2
0x100540254  sub     rcx, r10
0x100540257  jnz     short loc_100540234
0x100540259  test    rcx, rcx
0x10054025c  lea     rax, [r15-2]
0x100540260  cmovnz  rax, r15
0x100540264  xor     r15d, r15d
0x100540267  mov     [rax], r15w
0x10054026b  test    rcx, rcx
0x10054026e  jnz     short loc_100540287
0x100540270  lea     ecx, [r15+8]; dwErrorCode
0x100540274  xor     edx, edx; lpszErrorMsg
0x100540276  call    SQLPostInstallerErrorW
0x10054027b  jmp     loc_10054046E
0x100540280  mov     [r15], r8w
0x100540284  xor     r15d, r15d
0x100540287  mov     rdx, [rsp+6D0h+var_680]
0x10054028c  mov     r9d, 20h ; ' '
0x100540292  movzx   esi, [rsp+6D0h+var_688]
0x100540297  mov     ecx, r15d
0x10054029a  cmp     si, r10w
0x10054029e  mov     r8d, 0FFDFh
0x1005402a4  movzx   eax, word ptr [rdx]
0x1005402a7  cmovz   cx, r9w
0x1005402ac  and     ax, r8w
0x1005402b0  or      cx, ax
0x1005402b3  mov     [rdx], cx
0x1005402b6  lea     rdx, szFilename; "ODBC.INI"
0x1005402bd  test    r9b, cl
0x1005402c0  jnz     loc_100540389
0x1005402c6  lfence
0x1005402c9  mov     rcx, [r12]
0x1005402cd  lea     r9, [rsp+6D0h+szRetBuffer]; lpszRetBuffer
0x1005402d2  mov     rax, [r13+0]
0x1005402d6  lea     r8, szDefault; lpszDefault
0x1005402dd  mov     qword ptr [rsp+6D0h+nSize], rdx; lpszFilename
0x1005402e2  xor     edx, edx; lpszEntry
0x1005402e4  mov     dword ptr [rsp+6D0h+lpBuffer], 105h; cchRetBuffer
0x1005402ec  mov     r10, [rax+20h]
0x1005402f0  add     r10, [rcx+38h]
0x1005402f4  mov     rcx, r10; lpszSection
0x1005402f7  call    SQLGetPrivateProfileStringW
0x1005402fc  test    eax, eax
0x1005402fe  jnz     short loc_10054037C
0x100540300  test    r14, r14
0x100540303  jz      short loc_100540372
0x100540305  lfence
0x100540308  mov     rcx, [r12]
0x10054030c  lea     r8, [rbp+5D0h+Text]; unsigned __int16 *
0x100540313  mov     rax, [r13+0]
0x100540317  mov     esi, 105h
0x10054031c  mov     r9d, esi; unsigned int
0x10054031f  mov     rdx, [rax+20h]
0x100540323  add     rdx, [rcx+38h]
0x100540327  mov     rcx, cs:?g_hinstance_language@@3PEAUHINSTANCE__@@EA; HINSTANCE
0x10054032e  mov     [rsp+6D0h+lpBuffer], rdx
0x100540333  mov     edx, 9C4Fh; unsigned int
0x100540338  call    ?LoadFormattedMessage@@YAKPEAUHINSTANCE__@@KPEAGKZZ; LoadFormattedMessage(HINSTANCE__ *,ulong,ushort *,ulong,...)
0x10054033d  mov     rcx, cs:?g_hinstance_language@@3PEAUHINSTANCE__@@EA; hInstance
0x100540344  lea     r8, [rsp+6D0h+szRetBuffer]; lpBuffer
0x100540349  mov     r9d, esi; cchBufferMax
0x10054034c  mov     edx, 9C4Ch; uID
0x100540351  call    cs:__imp_LoadStringW
0x100540357  mov     r9d, 30h ; '0'; uType
0x10054035d  lea     r8, [rsp+6D0h+szRetBuffer]; lpCaption
0x100540362  lea     rdx, [rbp+5D0h+Text]; lpText
0x100540369  mov     rcx, r14; hWnd
0x10054036c  call    cs:__imp_MessageBoxW
0x100540372  mov     ecx, 9
0x100540377  jmp     loc_100540443
0x10054037c  mov     r10d, 1
0x100540382  lea     rdx, szFilename; "ODBC.INI"
0x100540389  mov     eax, 3
0x10054038e  cmp     si, ax
0x100540391  jnz     short loc_1005403F9
0x100540393  lfence
0x100540396  mov     rcx, [r12]
0x10054039a  lea     r9, [rsp+6D0h+szRetBuffer]; lpszRetBuffer
0x10054039f  mov     rax, [r13+0]
0x1005403a3  mov     qword ptr [rsp+6D0h+nSize], rdx; lpszFilename
0x1005403a8  lea     rdx, szEntry; "Server"
0x1005403af  mov     dword ptr [rsp+6D0h+lpBuffer], 105h; cchRetBuffer
0x1005403b7  mov     rsi, [rax+20h]
0x1005403bb  add     rsi, [rcx+38h]
0x1005403bf  mov     r8, rsi; lpszDefault
0x1005403c2  mov     rcx, rsi; lpszSection
0x1005403c5  call    SQLGetPrivateProfileStringW
0x1005403ca  lea     r8, [rsp+6D0h+szRetBuffer]; unsigned __int16 *
0x1005403cf  mov     edx, 5; int
0x1005403d4  mov     rcx, rdi; this
0x1005403d7  call    ?SetATTRValue@CDlgATTRs@@QEAAJHPEBG@Z; CDlgATTRs::SetATTRValue(int,ushort const *)
0x1005403dc  test    eax, eax
0x1005403de  jns     short loc_1005403EA
0x1005403e0  xor     edx, edx; lpszErrorMsg
0x1005403e2  lea     ecx, [rdx+15h]; dwErrorCode
0x1005403e5  call    SQLPostInstallerErrorW
0x1005403ea  mov     rcx, rsi; lpszDSN
0x1005403ed  call    SQLRemoveDSNFromIniW
0x1005403f2  mov     esi, 1
0x1005403f7  jmp     short loc_10054046E
0x1005403f9  mov     rax, [rsp+6D0h+var_678]
0x1005403fe  mov     [rbx+68h], rax
0x100540402  mov     [rbx+38h], r14
0x100540406  test    r14, r14
0x100540409  jz      short loc_100540427
0x10054040b  lfence
0x10054040e  mov     rdx, rbx; struct tagDLGSTRUCT *
0x100540411  mov     rcx, r14; HWND
0x100540414  call    ?CreateWizard@@YAHPEAUHWND__@@PEAUtagDLGSTRUCT@@@Z; CreateWizard(HWND__ *,tagDLGSTRUCT *)
0x100540419  mov     esi, eax
0x10054041b  test    eax, eax
0x10054041d  jnz     short loc_10054042A
0x10054041f  lea     ecx, [rax+10h]
0x100540422  jmp     loc_100540274
0x100540427  mov     esi, r10d
0x10054042a  lfence
0x10054042d  xor     r8d, r8d; int
0x100540430  mov     rdx, rbx; struct tagDLGSTRUCT *
0x100540433  xor     ecx, ecx; hWnd
0x100540435  call    ?SaveDSNAttributes@@YAKPEAUHWND__@@PEAUtagDLGSTRUCT@@H@Z; SaveDSNAttributes(HWND__ *,tagDLGSTRUCT *,int)
0x10054043a  test    eax, eax
0x10054043c  jz      short loc_10054046E
0x10054043e  lfence
0x100540441  mov     ecx, eax; dwErrorCode
0x100540443  xor     edx, edx; lpszErrorMsg
0x100540445  call    SQLPostInstallerErrorW
0x10054044a  mov     esi, r15d
0x10054044d  jmp     short loc_10054046E
0x10054044f  mov     rbx, r15
0x100540452  mov     edi, 88h
0x100540457  jmp     short loc_10054045C
0x100540459  xor     r15d, r15d
0x10054045c  xor     edx, edx; lpszErrorMsg
0x10054045e  lea     ecx, [rdx+15h]; dwErrorCode
0x100540461  call    SQLPostInstallerErrorW
0x100540466  mov     esi, r15d
0x100540469  test    rbx, rbx
0x10054046c  jz      short loc_1005404C2
0x10054046e  mov     rax, [rbx+40h]
0x100540472  test    rax, rax
0x100540475  jz      short loc_1005404A3
0x100540477  mov     rax, [rax+58h]
0x10054047b  mov     [rsp+6D0h+var_690], rax
0x100540480  mov     rax, [rbx+40h]
  ... truncated ...
```
