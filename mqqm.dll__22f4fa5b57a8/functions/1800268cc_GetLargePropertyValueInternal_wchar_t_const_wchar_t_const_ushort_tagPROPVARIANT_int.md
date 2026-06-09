# GetLargePropertyValueInternal(wchar_t const *,wchar_t const *,ushort,tagPROPVARIANT *,int *)

- ea: `0x1800268cc`
- end: `0x180026d1c`
- name: `?GetLargePropertyValueInternal@@YAJPEB_W0GPEAUtagPROPVARIANT@@PEAH@Z`
- size: `1104`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpFileName@<rcx>, const wchar_t *@<rdx>, unsigned __int16@<r8w>, struct tagPROPVARIANT *@<r9>, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002683c`

## callees

- `0x18000b9dc`
- `0x18000bab8`
- `0x18000cb80`
- `0x1800261c0`
- `0x1800264a8`
- `0x1800268cc`
- `0x18002c61c`
- `0x18002c6c8`
- `0x18009bd1c`
- `0x1800d6ea0`

## import_xrefs

- `msvcrt!free` at `0x180026a69`
- `msvcrt!free` at `0x180026b07`
- `msvcrt!free` at `0x180026b11`
- `msvcrt!free` at `0x180026b49`
- `msvcrt!free` at `0x180026b53`
- `msvcrt!free` at `0x180026b8e`
- `msvcrt!free` at `0x180026b98`
- `msvcrt!free` at `0x180026be1`
- `msvcrt!free` at `0x180026beb`
- `msvcrt!free` at `0x180026c21`
- `msvcrt!free` at `0x180026c2b`
- `msvcrt!free` at `0x180026c69`
- `msvcrt!free` at `0x180026c73`
- `msvcrt!free` at `0x180026cab`
- `msvcrt!free` at `0x180026cb5`
- `msvcrt!free` at `0x180026cdc`
- `msvcrt!free` at `0x180026ce6`
- `msvcrt!free` at `0x180026a69`
- `msvcrt!free` at `0x180026b07`
- `msvcrt!free` at `0x180026b11`
- `msvcrt!free` at `0x180026b49`
- `msvcrt!free` at `0x180026b53`
- `msvcrt!free` at `0x180026b8e`
- `msvcrt!free` at `0x180026b98`
- `msvcrt!free` at `0x180026be1`
- `msvcrt!free` at `0x180026beb`
- `msvcrt!free` at `0x180026c21`
- `msvcrt!free` at `0x180026c2b`
- `msvcrt!free` at `0x180026c69`
- `msvcrt!free` at `0x180026c73`
- `msvcrt!free` at `0x180026cab`
- `msvcrt!free` at `0x180026cb5`
- `msvcrt!free` at `0x180026cdc`
- `msvcrt!free` at `0x180026ce6`
- `msvcrt!wcsstr` at `0x180026bb6`
- `msvcrt!wcsstr` at `0x180026c3e`
- `msvcrt!wcsstr` at `0x180026bb6`
- `msvcrt!wcsstr` at `0x180026c3e`
- `KERNEL32!GetLastError` at `0x1800269b1`
- `KERNEL32!GetLastError` at `0x180026a28`
- `KERNEL32!GetLastError` at `0x1800269b1`
- `KERNEL32!GetLastError` at `0x180026a28`
- `KERNEL32!CreateFileW` at `0x18002699e`
- `KERNEL32!CreateFileW` at `0x18002699e`
- `KERNEL32!GetFileSize` at `0x1800269d6`
- `KERNEL32!GetFileSize` at `0x1800269d6`
- `KERNEL32!ReadFile` at `0x180026a17`
- `KERNEL32!ReadFile` at `0x180026a17`
- `mqsec!GetFalconKeyValue` at `0x18002695e`
- `mqsec!GetFalconKeyValue` at `0x18002695e`

## string_xrefs

- `0x180026a9a`: `Security`
- `0x180026b1d`: `Security`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall GetLargePropertyValueInternal(
        LPCWSTR lpFileName,
        const wchar_t *a2,
        __int64 a3,
        struct tagPROPVARIANT *a4,
        int *a5)
{
  HANDLE FileW; // rax
  void *v9; // rdi
  DWORD LastError; // eax
  DWORD FileSize; // eax
  __int64 v12; // rsi
  void *v13; // rbx
  DWORD v14; // eax
  unsigned int v15; // esi
  unsigned int v16; // edi
  unsigned __int64 v17; // r12
  wchar_t *v18; // rdi
  int v19; // eax
  int v20; // eax
  int v21; // eax
  __int64 v22; // rsi
  wchar_t *v23; // rax
  wchar_t *v24; // rsi
  wchar_t *v25; // rax
  int v26; // eax
  unsigned int v27; // [rsp+40h] [rbp-30h] BYREF
  DWORD NumberOfBytesRead; // [rsp+44h] [rbp-2Ch] BYREF
  _QWORD v29[3]; // [rsp+48h] [rbp-28h] BYREF
  wchar_t SubStr[4]; // [rsp+60h] [rbp-10h] BYREF

  if ( ((a4->vt - 1) & 0xFFBF) != 0 )
  {
    LogMsgHR(-1072824295, (wchar_t *)L"lqs", 0x10C7u);
    return 3222143001LL;
  }
  if ( !dword_18013C0E0 )
  {
    v27 = 4;
    LODWORD(v29[0]) = 4;
    if ( GetFalconKeyValue(L"FileSizeForProfile", &v27, &dword_18013C0E0, (unsigned int *)v29, 0) || !dword_18013C0E0 )
      dword_18013C0E0 = 0x4000;
  }
  FileW = CreateFileW(lpFileName, 0x80000000, 0, 0, 3u, 0x80u, 0);
  v9 = FileW;
  v29[0] = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError )
      LogMsgNTStatus(LastError, (wchar_t *)L"lqs", 0x1018u);
    goto LABEL_11;
  }
  FileSize = GetFileSize(FileW, 0);
  v12 = FileSize;
  if ( FileSize <= dword_18013C0E0 )
  {
LABEL_11:
    *a5 = 1;
LABEL_31:
    v15 = 0;
    goto LABEL_33;
  }
  v13 = MmAllocate(FileSize + 4);
  v29[1] = v13;
  NumberOfBytesRead = 0;
  if ( !ReadFile(v9, v13, v12, &NumberOfBytesRead, 0) )
  {
    v14 = GetLastError();
    if ( v14 )
      LogMsgNTStatus(v14, (wchar_t *)L"lqs", 0x1054u);
    goto LABEL_16;
  }
  if ( NumberOfBytesRead != (_DWORD)v12 )
  {
LABEL_16:
    *a5 = 1;
    v15 = -2147467259;
    LogMsgHR(-2147467259, (wchar_t *)L"lqs", 0x107Cu);
    free(v13);
    goto LABEL_33;
  }
  *((_BYTE *)v13 + v12) = 0;
  *((_BYTE *)v13 + (unsigned int)(v12 + 1)) = 0;
  *((_BYTE *)v13 + (unsigned int)(v12 + 2)) = 0;
  *((_BYTE *)v13 + (unsigned int)(v12 + 3)) = 0;
  wcscpy(SubStr, L"\r\n");
  v16 = mqwcslen(L"Security");
  v27 = v16 + 2 + mqwcslen(SubStr);
  v17 = v27;
  v18 = (wchar_t *)MmAllocate(saturated_mul(v27, 2u));
  v29[2] = v18;
  v19 = StringCchCopyW(v18, (unsigned int)v17, SubStr);
  v15 = v19;
  if ( v19 >= 0 )
  {
    v20 = StringCchCatW(v18, v17, L"Security");
    v15 = v20;
    if ( v20 >= 0 )
    {
      v21 = StringCchCatW(v18, v17, L"=");
      v15 = v21;
      if ( v21 >= 0 )
      {
        v22 = v27 - 1;
        v18[v22] = 0;
        v23 = wcsstr((const wchar_t *)v13, v18);
        if ( v23 )
        {
          v24 = &v23[v22];
          if ( *v24 )
          {
            v25 = wcsstr(v24, SubStr);
            if ( v25 )
            {
              *v25 = 0;
              v26 = ConvertStringPropertyToVar(v24, v25 - v24, v25 - v24, 0x41u, a4);
              v15 = v26;
              if ( v26 < 0 )
              {
                *a5 = 1;
                LogMsgHR(v26, (wchar_t *)L"lqs", 0x1112u);
                free(v18);
                free(v13);
                goto LABEL_33;
              }
              *a5 = 0;
              free(v18);
              free(v13);
              goto LABEL_31;
            }
            *a5 = 1;
            v15 = -2147467259;
            LogMsgHR(-2147467259, (wchar_t *)L"lqs", 0x10A4u);
            free(v18);
            free(v13);
          }
          else
          {
            *a5 = 1;
            v15 = -2147467259;
            LogMsgHR(-2147467259, (wchar_t *)L"lqs", 0x116Cu);
            free(v18);
            free(v13);
          }
        }
        else
        {
          *a5 = 1;
          v15 = -2147467259;
          LogMsgHR(-2147467259, (wchar_t *)L"lqs", 0x1090u);
          free(v18);
          free(v13);
        }
      }
      else
      {
        LogMsgHR(v21, (wchar_t *)L"lqs", 0x141Eu);
        free(v18);
        free(v13);
      }
    }
    else
    {
      LogMsgHR(v20, (wchar_t *)L"lqs", 0x1414u);
      free(v18);
      free(v13);
    }
  }
  else
  {
    LogMsgHR(v19, (wchar_t *)L"lqs", 0x15FEu);
    free(v18);
    free(v13);
  }
LABEL_33:
  CAutoCloseFileHandle::~CAutoCloseFileHandle((CAutoCloseFileHandle *)v29);
  return v15;
}

```

## disassembly

```asm
0x1800268cc  mov     [rsp-38h+arg_8], rbx
0x1800268d1  push    rbp
0x1800268d2  push    rsi
0x1800268d3  push    rdi
0x1800268d4  push    r12
0x1800268d6  push    r13
0x1800268d8  push    r14
0x1800268da  push    r15
0x1800268dc  mov     rbp, rsp
0x1800268df  sub     rsp, 70h
0x1800268e3  mov     rax, cs:__security_cookie
0x1800268ea  xor     rax, rsp
0x1800268ed  mov     [rbp+var_8], rax
0x1800268f1  mov     r13, r9
0x1800268f4  mov     rbx, rcx
0x1800268f7  mov     r15, [rbp+arg_20]
0x1800268fb  movzx   eax, word ptr [r9]
0x1800268ff  dec     ax
0x180026902  mov     ecx, 0FFBFh
0x180026907  test    cx, ax
0x18002690a  jz      short loc_18002692C
0x18002690c  mov     r8d, 10C7h; unsigned __int16
0x180026912  lea     rdx, aLqs_0; "lqs"
0x180026919  mov     ebx, 0C00E0019h
0x18002691e  mov     ecx, ebx; int
0x180026920  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180026925  mov     eax, ebx
0x180026927  jmp     loc_180026CF8
0x18002692c  xor     r12d, r12d
0x18002692f  cmp     cs:dword_18013C0E0, r12d
0x180026936  jnz     short loc_18002697B
0x180026938  lea     eax, [r12+4]
0x18002693d  mov     [rbp+var_30], eax
0x180026940  mov     dword ptr [rbp+var_28], eax
0x180026943  mov     qword ptr [rsp+70h+dwCreationDisposition], r12
0x180026948  lea     r9, [rbp+var_28]
0x18002694c  lea     r8, dword_18013C0E0
0x180026953  lea     rdx, [rbp+var_30]
0x180026957  lea     rcx, aFilesizeforpro; "FileSizeForProfile"
0x18002695e  call    cs:__imp_?GetFalconKeyValue@@YAJPEB_WPEAKPEAX10@Z; GetFalconKeyValue(wchar_t const *,ulong *,void *,ulong *,wchar_t const *)
0x180026964  test    eax, eax
0x180026966  jnz     short loc_180026971
0x180026968  cmp     cs:dword_18013C0E0, r12d
0x18002696f  jnz     short loc_18002697B
0x180026971  mov     cs:dword_18013C0E0, 4000h
0x18002697b  mov     [rsp+70h+hTemplateFile], r12; hTemplateFile
0x180026980  mov     [rsp+70h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180026988  mov     [rsp+70h+dwCreationDisposition], 3; dwCreationDisposition
0x180026990  xor     r9d, r9d; lpSecurityAttributes
0x180026993  xor     r8d, r8d; dwShareMode
0x180026996  mov     edx, 80000000h; dwDesiredAccess
0x18002699b  mov     rcx, rbx; lpFileName
0x18002699e  call    cs:__imp_CreateFileW
0x1800269a4  mov     rdi, rax
0x1800269a7  mov     [rbp+var_28], rax
0x1800269ab  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800269af  jnz     short loc_1800269D1
0x1800269b1  call    cs:__imp_GetLastError
0x1800269b7  test    eax, eax
0x1800269b9  jz      short loc_1800269E6
0x1800269bb  mov     r8d, 1018h; unsigned __int16
0x1800269c1  lea     rdx, aLqs_0; "lqs"
0x1800269c8  mov     ecx, eax; int
0x1800269ca  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x1800269cf  jmp     short loc_1800269E6
0x1800269d1  xor     edx, edx; lpFileSizeHigh
0x1800269d3  mov     rcx, rdi; hFile
0x1800269d6  call    cs:__imp_GetFileSize
0x1800269dc  mov     esi, eax
0x1800269de  cmp     eax, cs:dword_18013C0E0
0x1800269e4  ja      short loc_1800269F2
0x1800269e6  mov     dword ptr [r15], 1
0x1800269ed  jmp     loc_180026CBC
0x1800269f2  lea     ecx, [rsi+4]; unsigned __int64
0x1800269f5  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800269fa  mov     rbx, rax
0x1800269fd  mov     [rbp+var_20], rax
0x180026a01  mov     [rbp+NumberOfBytesRead], r12d
0x180026a05  mov     qword ptr [rsp+70h+dwCreationDisposition], r12; lpOverlapped
0x180026a0a  lea     r9, [rbp+NumberOfBytesRead]; lpNumberOfBytesRead
0x180026a0e  mov     r8d, esi; nNumberOfBytesToRead
0x180026a11  mov     rdx, rax; lpBuffer
0x180026a14  mov     rcx, rdi; hFile
0x180026a17  call    cs:__imp_ReadFile
0x180026a1d  lea     r14, aLqs_0; "lqs"
0x180026a24  test    eax, eax
0x180026a26  jnz     short loc_180026A44
0x180026a28  call    cs:__imp_GetLastError
0x180026a2e  test    eax, eax
0x180026a30  jz      short loc_180026A49
0x180026a32  mov     r8d, 1054h; unsigned __int16
0x180026a38  mov     rdx, r14; wchar_t *
0x180026a3b  mov     ecx, eax; int
0x180026a3d  call    ?LogMsgNTStatus@@YAXJPEA_WG@Z; LogMsgNTStatus(long,wchar_t *,ushort)
0x180026a42  jmp     short loc_180026A49
0x180026a44  cmp     [rbp+NumberOfBytesRead], esi
0x180026a47  jz      short loc_180026A75
0x180026a49  mov     dword ptr [r15], 1
0x180026a50  mov     r8d, 107Ch; unsigned __int16
0x180026a56  mov     rdx, r14; wchar_t *
0x180026a59  mov     esi, 80004005h
0x180026a5e  mov     ecx, esi; int
0x180026a60  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180026a65  nop
0x180026a66  mov     rcx, rbx; Block
0x180026a69  call    cs:__imp_free
0x180026a6f  nop
0x180026a70  jmp     loc_180026CED
0x180026a75  mov     [rsi+rbx], r12b
0x180026a79  lea     eax, [rsi+1]
0x180026a7c  mov     [rax+rbx], r12b
0x180026a80  lea     eax, [rsi+2]
0x180026a83  mov     [rax+rbx], r12b
0x180026a87  lea     eax, [rsi+3]
0x180026a8a  mov     [rax+rbx], r12b
0x180026a8e  mov     dword ptr [rbp+SubStr], 0A000Dh
0x180026a95  mov     [rbp+var_C], r12w
0x180026a9a  lea     rcx, aSecurity; "Security"
0x180026aa1  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180026aa6  mov     edi, eax
0x180026aa8  lea     rcx, [rbp+SubStr]; wchar_t *
0x180026aac  call    ?mqwcslen@@YAIPEB_W@Z; mqwcslen(wchar_t const *)
0x180026ab1  add     edi, 2
0x180026ab4  add     eax, edi
0x180026ab6  mov     [rbp+var_30], eax
0x180026ab9  mov     r12d, eax
0x180026abc  mov     eax, 2
0x180026ac1  mul     r12
0x180026ac4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180026acb  cmovb   rax, rcx
0x180026acf  mov     rcx, rax; unsigned __int64
0x180026ad2  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180026ad7  mov     rdi, rax
0x180026ada  mov     [rbp+var_18], rax
0x180026ade  lea     r8, [rbp+SubStr]; wchar_t *
0x180026ae2  mov     edx, r12d; unsigned __int64
0x180026ae5  mov     rcx, rax; wchar_t *
0x180026ae8  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180026aed  mov     esi, eax
0x180026aef  test    eax, eax
0x180026af1  jns     short loc_180026B1D
0x180026af3  mov     r8d, 15FEh; unsigned __int16
0x180026af9  mov     rdx, r14; wchar_t *
0x180026afc  mov     ecx, eax; int
0x180026afe  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180026b03  nop
0x180026b04  mov     rcx, rdi; Block
0x180026b07  call    cs:__imp_free
0x180026b0d  nop
0x180026b0e  mov     rcx, rbx; Block
0x180026b11  call    cs:__imp_free
0x180026b17  nop
0x180026b18  jmp     loc_180026CED
0x180026b1d  lea     r8, aSecurity; "Security"
0x180026b24  mov     rdx, r12; unsigned __int64
0x180026b27  mov     rcx, rdi; wchar_t *
0x180026b2a  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180026b2f  mov     esi, eax
0x180026b31  test    eax, eax
0x180026b33  jns     short loc_180026B5F
0x180026b35  mov     r8d, 1414h; unsigned __int16
0x180026b3b  mov     rdx, r14; wchar_t *
0x180026b3e  mov     ecx, eax; int
0x180026b40  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180026b45  nop
0x180026b46  mov     rcx, rdi; Block
0x180026b49  call    cs:__imp_free
0x180026b4f  nop
0x180026b50  mov     rcx, rbx; Block
0x180026b53  call    cs:__imp_free
0x180026b59  nop
0x180026b5a  jmp     loc_180026CED
0x180026b5f  lea     r8, asc_1800FEF50; "="
0x180026b66  mov     rdx, r12; unsigned __int64
0x180026b69  mov     rcx, rdi; wchar_t *
0x180026b6c  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180026b71  mov     esi, eax
0x180026b73  xor     r12d, r12d
0x180026b76  test    eax, eax
0x180026b78  jns     short loc_180026BA4
0x180026b7a  mov     r8d, 141Eh; unsigned __int16
0x180026b80  mov     rdx, r14; wchar_t *
0x180026b83  mov     ecx, eax; int
0x180026b85  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180026b8a  nop
0x180026b8b  mov     rcx, rdi; Block
0x180026b8e  call    cs:__imp_free
0x180026b94  nop
0x180026b95  mov     rcx, rbx; Block
0x180026b98  call    cs:__imp_free
0x180026b9e  nop
0x180026b9f  jmp     loc_180026CED
0x180026ba4  mov     eax, [rbp+var_30]
0x180026ba7  dec     eax
0x180026ba9  mov     esi, eax
0x180026bab  mov     [rdi+rax*2], r12w
0x180026bb0  mov     rdx, rdi; SubStr
0x180026bb3  mov     rcx, rbx; Str
0x180026bb6  call    cs:__imp_wcsstr
0x180026bbc  test    rax, rax
0x180026bbf  jnz     short loc_180026BF7
0x180026bc1  mov     dword ptr [r15], 1
0x180026bc8  mov     r8d, 1090h; unsigned __int16
0x180026bce  mov     rdx, r14; wchar_t *
0x180026bd1  mov     esi, 80004005h
0x180026bd6  mov     ecx, esi; int
0x180026bd8  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180026bdd  nop
0x180026bde  mov     rcx, rdi; Block
0x180026be1  call    cs:__imp_free
0x180026be7  nop
0x180026be8  mov     rcx, rbx; Block
0x180026beb  call    cs:__imp_free
0x180026bf1  nop
0x180026bf2  jmp     loc_180026CED
0x180026bf7  lea     rsi, [rax+rsi*2]
0x180026bfb  cmp     [rsi], r12w
0x180026bff  jnz     short loc_180026C37
0x180026c01  mov     dword ptr [r15], 1
0x180026c08  mov     r8d, 116Ch; unsigned __int16
0x180026c0e  mov     rdx, r14; wchar_t *
0x180026c11  mov     esi, 80004005h
0x180026c16  mov     ecx, esi; int
0x180026c18  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180026c1d  nop
0x180026c1e  mov     rcx, rdi; Block
0x180026c21  call    cs:__imp_free
0x180026c27  nop
0x180026c28  mov     rcx, rbx; Block
0x180026c2b  call    cs:__imp_free
0x180026c31  nop
0x180026c32  jmp     loc_180026CED
0x180026c37  lea     rdx, [rbp+SubStr]; SubStr
0x180026c3b  mov     rcx, rsi; Str
0x180026c3e  call    cs:__imp_wcsstr
0x180026c44  test    rax, rax
0x180026c47  jnz     short loc_180026C7C
0x180026c49  mov     dword ptr [r15], 1
0x180026c50  mov     r8d, 10A4h; unsigned __int16
0x180026c56  mov     rdx, r14; wchar_t *
0x180026c59  mov     esi, 80004005h
0x180026c5e  mov     ecx, esi; int
0x180026c60  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180026c65  nop
0x180026c66  mov     rcx, rdi; Block
0x180026c69  call    cs:__imp_free
0x180026c6f  nop
0x180026c70  mov     rcx, rbx; Block
0x180026c73  call    cs:__imp_free
0x180026c79  nop
0x180026c7a  jmp     short loc_180026CED
0x180026c7c  mov     rdx, rax
0x180026c7f  sub     rdx, rsi
0x180026c82  sar     rdx, 1; BufferCount
0x180026c85  mov     [rax], r12w
0x180026c89  mov     r9d, 41h ; 'A'; unsigned __int16
0x180026c8f  mov     qword ptr [rsp+70h+dwCreationDisposition], r13; struct tagPROPVARIANT *
0x180026c94  mov     r8d, edx; unsigned int
0x180026c97  mov     rcx, rsi; wchar_t *
0x180026c9a  call    ?ConvertStringPropertyToVar@@YAJPEA_WKKGPEAUtagPROPVARIANT@@@Z; ConvertStringPropertyToVar(wchar_t *,ulong,ulong,ushort,tagPROPVARIANT *)
0x180026c9f  mov     esi, eax
0x180026ca1  test    eax, eax
0x180026ca3  js      short loc_180026CC1
0x180026ca5  mov     [r15], r12d
0x180026ca8  mov     rcx, rdi; Block
0x180026cab  call    cs:__imp_free
0x180026cb1  nop
0x180026cb2  mov     rcx, rbx; Block
0x180026cb5  call    cs:__imp_free
0x180026cbb  nop
0x180026cbc  mov     esi, r12d
0x180026cbf  jmp     short loc_180026CED
0x180026cc1  mov     dword ptr [r15], 1
0x180026cc8  mov     r8d, 1112h; unsigned __int16
0x180026cce  mov     rdx, r14; wchar_t *
0x180026cd1  mov     ecx, eax; int
0x180026cd3  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180026cd8  nop
0x180026cd9  mov     rcx, rdi; Block
0x180026cdc  call    cs:__imp_free
0x180026ce2  nop
0x180026ce3  mov     rcx, rbx; Block
0x180026ce6  call    cs:__imp_free
0x180026cec  nop
0x180026ced  lea     rcx, [rbp+var_28]; this
0x180026cf1  call    ??1CAutoCloseFileHandle@@QEAA@XZ; CAutoCloseFileHandle::~CAutoCloseFileHandle(void)
0x180026cf6  mov     eax, esi
0x180026cf8  mov     rcx, [rbp+var_8]
0x180026cfc  xor     rcx, rsp; StackCookie
0x180026cff  call    __security_check_cookie
0x180026d04  mov     rbx, [rsp+70h+arg_8]
0x180026d0c  add     rsp, 70h
0x180026d10  pop     r15
0x180026d12  pop     r14
0x180026d14  pop     r13
0x180026d16  pop     r12
0x180026d18  pop     rdi
0x180026d19  pop     rsi
0x180026d1a  pop     rbp
0x180026d1b  retn
  ... truncated ...
```
