# InternalGetColorDirectory(ushort const *,ushort *,ulong *)

- ea: `0x180008cc0`
- end: `0x180009133`
- name: `?InternalGetColorDirectory@@YAHPEBGPEAGPEAK@Z`
- size: `1139`
- prototype: `_BOOL8 __fastcall(LPWSTR pName, unsigned __int16 *, LPDWORD pcbNeeded)`
- caller_count: `13`
- callee_count: `12`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000815c`
- `0x180008374`
- `0x180008a64`
- `0x180009810`
- `0x18001d6f4`
- `0x1800212e0`
- `0x180023a78`
- `0x1800412a4`
- `0x1800446f0`
- `0x180044ab0`
- `0x180044d90`
- `0x180044ed0`
- `0x180045200`

## callees

- `0x180008bf0`
- `0x180008cc0`
- `0x1800098b0`
- `0x180009a14`
- `0x18000b828`
- `0x18000be44`
- `0x180029f14`
- `0x18002e5f0`
- `0x18002f2f4`
- `0x18002fc90`
- `0x18003d8c8`
- `0x18004180c`

## import_xrefs

- `ntdll!RtlGetPersistedStateLocation` at `0x180009108`
- `ntdll!RtlGetPersistedStateLocation` at `0x180009108`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008dc9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008f47`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008dc9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180008f47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008edf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fb2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008e9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008edf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008f18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008fb2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180009120`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180009120`
- `ext-ms-win-printer-winspool-l1-1-1!GetPrinterDriverDirectoryW` at `0x180008fa8`
- `ext-ms-win-printer-winspool-l1-1-1!GetPrinterDriverDirectoryW` at `0x180008fe1`
- `ext-ms-win-printer-winspool-l1-1-1!GetPrinterDriverDirectoryW` at `0x180008fa8`
- `ext-ms-win-printer-winspool-l1-1-1!GetPrinterDriverDirectoryW` at `0x180008fe1`

## string_xrefs

- `0x1800090e8`: `InstalledColorProfiles`

## pseudocode

```c
_BOOL8 __fastcall InternalGetColorDirectory(LPWSTR pName, unsigned __int16 *a2, LPDWORD pcbNeeded)
{
  unsigned __int64 v6; // r14
  const unsigned __int16 *v7; // r8
  __int64 v8; // r11
  WCHAR *v9; // rbp
  bool v10; // zf
  int v11; // ebx
  const wchar_t *v13; // r8
  __int64 v14; // rdx
  wchar_t *v15; // rcx
  size_t v16; // r13
  wchar_t *v17; // rax
  __int64 v18; // r11
  DWORD v19; // r11d
  unsigned __int64 v20; // rax
  signed int v21; // eax
  signed int LastError; // eax
  DWORD cbBuf; // ebx
  const WCHAR *FilenameFromPath; // rax
  __int64 v25; // r11
  __int64 v26; // rcx
  unsigned __int64 v27; // r13
  int v28; // r11d
  int v29; // r11d
  size_t v30; // rdx
  int v31; // eax
  size_t pcchLength; // [rsp+40h] [rbp-468h] BYREF
  unsigned __int64 v33; // [rsp+48h] [rbp-460h]
  wchar_t psz[520]; // [rsp+50h] [rbp-458h] BYREF

  if ( pcbNeeded )
  {
    v6 = *pcbNeeded;
    if ( !pName )
    {
      v7 = gszLocalColorDirectory;
      if ( gszLocalColorDirectory )
      {
        v8 = -1;
        v9 = 0;
        do
          v10 = gszLocalColorDirectory[++v8] == 0;
        while ( !v10 );
        *pcbNeeded = 2 * v8 + 2;
        goto LABEL_7;
      }
    }
    *pcbNeeded = 520;
    v9 = (WCHAR *)MemAlloc(520);
    if ( !v9 )
    {
      v11 = -2147024882;
      goto LABEL_44;
    }
    cbBuf = *pcbNeeded;
    LODWORD(v33) = *pcbNeeded >> 1;
    if ( pName || (LODWORD(pcchLength) = 0, IsClusterServiceInstalled((int *)&pcchLength)) || (_DWORD)pcchLength )
    {
      if ( (unsigned __int8)IsDeletePrinterDataExWPresent() )
      {
        if ( GetPrinterDriverDirectoryW(pName, 0, 1u, (LPBYTE)v9, *pcbNeeded, pcbNeeded)
          || GetLastError() == 1805
          && (*pcbNeeded = cbBuf,
              GetPrinterDriverDirectoryW(pName, (LPWSTR)L"Windows NT x86", 1u, (LPBYTE)v9, cbBuf, pcbNeeded)) )
        {
LABEL_52:
          FilenameFromPath = GetFilenameFromPath(v9);
          if ( FilenameFromPath )
          {
            v25 = -1;
            pcchLength = 0;
            v26 = -1;
            do
              ++v26;
            while ( FilenameFromPath[v26] );
            *pcbNeeded += -2 * v26;
            do
              ++v25;
            while ( gszColorDir[v25] );
            v27 = (unsigned int)v33;
            *FilenameFromPath = 0;
            v11 = StringCchLengthW(v9, (unsigned int)v27, &pcchLength);
            if ( v11 < 0 )
              goto LABEL_32;
            if ( pcchLength )
            {
              v29 = 2 * v28;
              v30 = pcchLength;
              v31 = v29 + 2;
              if ( v9[pcchLength - 1] == 92 )
                v31 = v29;
              *pcbNeeded += v31;
              if ( *pcbNeeded <= 2 * v27 )
              {
                if ( v9[v30 - 1] != 92 )
                {
                  v11 = StringCchCatW(v9, (unsigned int)v27, gszBackslash);
                  if ( v11 < 0 )
                    goto LABEL_32;
                }
                v11 = StringCchCatW(v9, v27, gszColorDir);
LABEL_35:
                if ( v11 < 0 )
                  goto LABEL_32;
                goto LABEL_36;
              }
LABEL_65:
              v11 = -2147024774;
              goto LABEL_32;
            }
LABEL_36:
            v7 = v9;
            if ( !pName
              && !_InterlockedCompareExchange64(
                    (volatile signed __int64 *)&gszLocalColorDirectory,
                    (signed __int64)v9,
                    0) )
            {
              v9 = 0;
            }
LABEL_7:
            if ( a2 && *pcbNeeded <= (unsigned int)v6 )
              v11 = StringCchCopyW(a2, v6 >> 1, v7);
            else
              v11 = -2147024774;
            if ( !v9 )
            {
LABEL_10:
              if ( v11 >= 0 )
                return v11 >= 0;
LABEL_44:
              SetLastError((unsigned __int16)v11);
              return v11 >= 0;
            }
LABEL_32:
            MemFree(v9);
            goto LABEL_10;
          }
          LastError = GetLastError();
          v11 = LastError;
          if ( LastError <= 0 )
            goto LABEL_35;
LABEL_34:
          v11 = (unsigned __int16)LastError | 0x80070000;
          goto LABEL_35;
        }
        v21 = GetLastError();
        v11 = v21;
        if ( v21 > 0 )
          v11 = (unsigned __int16)v21 | 0x80070000;
        if ( v11 == -2147023112 )
          goto LABEL_65;
        if ( v11 != -2147023174 )
        {
          if ( v11 < 0 )
            goto LABEL_32;
          goto LABEL_52;
        }
      }
    }
    memset_0(psz, 0, sizeof(psz));
    if ( (int)RtlGetPersistedStateLocation(L"InstalledColorProfiles", 0, 0, 1, v9, *pcbNeeded, 0) >= 0 )
      goto LABEL_36;
    if ( GetSystemDirectoryW(psz, 0x104u) )
    {
      pcchLength = 0;
      v11 = StringLengthWorkerW(psz, 0x208u, &pcchLength);
      if ( v11 < 0 )
        goto LABEL_35;
      v13 = L"\\spool\\drivers\\color";
      v14 = 2147483646;
      v15 = &psz[pcchLength];
      v16 = 520 - pcchLength;
      if ( 520 != pcchLength )
      {
        do
        {
          if ( !v14 )
            break;
          if ( !*v13 )
            break;
          *v15++ = *v13++;
          --v14;
          --v16;
        }
        while ( v16 );
      }
      v17 = v15 - 1;
      v11 = -2147024774;
      if ( v16 )
      {
        v17 = v15;
        v11 = 0;
      }
      *v17 = 0;
      if ( !v16 )
        goto LABEL_35;
      v18 = -1;
      do
        v10 = psz[++v18] == 0;
      while ( !v10 );
      v19 = 2 * v18 + 2;
      v20 = 2LL * (unsigned int)v33;
      *pcbNeeded = v19;
      if ( v19 <= v20 )
      {
        v11 = StringCchCopyW(v9, (unsigned __int64)v19 >> 1, psz);
        goto LABEL_35;
      }
      goto LABEL_65;
    }
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError <= 0 )
      goto LABEL_35;
    goto LABEL_34;
  }
  SetLastError(0x57u);
  return 0;
}

```

## disassembly

```asm
0x180008cc0  mov     r11, rsp
0x180008cc3  push    rsi
0x180008cc4  push    rdi
0x180008cc5  push    r15
0x180008cc7  sub     rsp, 490h
0x180008cce  mov     rax, cs:__security_cookie
0x180008cd5  xor     rax, rsp
0x180008cd8  mov     [rsp+4A8h+var_48], rax
0x180008ce0  mov     rdi, r8
0x180008ce3  mov     r15, rdx
0x180008ce6  mov     rsi, rcx
0x180008ce9  test    r8, r8
0x180008cec  jz      loc_180008DC4
0x180008cf2  mov     [r11+20h], rbx
0x180008cf6  mov     [r11-20h], rbp
0x180008cfa  mov     [r11-28h], r12
0x180008cfe  mov     [r11-30h], r13
0x180008d02  mov     [r11-38h], r14
0x180008d06  mov     r14d, [r8]
0x180008d09  test    rcx, rcx
0x180008d0c  jnz     loc_180008F26
0x180008d12  mov     r8, cs:gszLocalColorDirectory; unsigned __int16 *
0x180008d19  test    r8, r8
0x180008d1c  jz      loc_180008F26
0x180008d22  xor     r12d, r12d
0x180008d25  mov     r11, 0FFFFFFFFFFFFFFFFh
0x180008d2c  mov     ebp, r12d
0x180008d2f  nop
0x180008d30  cmp     [r8+r11*2+2], bp
0x180008d36  lea     r11, [r11+1]
0x180008d3a  jnz     short loc_180008D30
0x180008d3c  lea     r11d, ds:2[r11*2]
0x180008d44  mov     [rdi], r11d
0x180008d47  test    r15, r15
0x180008d4a  jnz     short loc_180008DAD
0x180008d4c  mov     ebx, 8007007Ah
0x180008d51  test    rbp, rbp
0x180008d54  jnz     loc_180008ED2
0x180008d5a  test    ebx, ebx
0x180008d5c  js      loc_180008F44
0x180008d62  mov     r14, [rsp+4A8h+var_38]
0x180008d6a  not     ebx
0x180008d6c  mov     r13, [rsp+4A8h+var_30]
0x180008d74  mov     r12, [rsp+4A8h+var_28]
0x180008d7c  mov     rbp, [rsp+4A8h+var_20]
0x180008d84  shr     ebx, 1Fh
0x180008d87  mov     eax, ebx
0x180008d89  mov     rbx, [rsp+4A8h+arg_18]
0x180008d91  mov     rcx, [rsp+4A8h+var_48]
0x180008d99  xor     rcx, rsp; StackCookie
0x180008d9c  call    __security_check_cookie
0x180008da1  add     rsp, 490h
0x180008da8  pop     r15
0x180008daa  pop     rdi
0x180008dab  pop     rsi
0x180008dac  retn
0x180008dad  cmp     [rdi], r14d
0x180008db0  ja      short loc_180008D4C
0x180008db2  mov     rdx, r14
0x180008db5  mov     rcx, r15; unsigned __int16 *
0x180008db8  shr     rdx, 1; unsigned __int64
0x180008dbb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008dc0  mov     ebx, eax
0x180008dc2  jmp     short loc_180008D51
0x180008dc4  mov     ecx, 57h ; 'W'; dwErrCode
0x180008dc9  call    cs:__imp_SetLastError
0x180008dcf  xor     eax, eax
0x180008dd1  jmp     short loc_180008D91
0x180008dd3  lea     r8, [rsp+4A8h+pcchLength]; pcchLength
0x180008dd8  mov     [rsp+4A8h+pcchLength], r12
0x180008ddd  mov     rdx, r13; cchMax
0x180008de0  lea     rcx, [rsp+4A8h+psz]; psz
0x180008de5  call    StringLengthWorkerW
0x180008dea  mov     ebx, eax
0x180008dec  test    eax, eax
0x180008dee  js      loc_180008EF4
0x180008df4  mov     rax, [rsp+4A8h+pcchLength]
0x180008df9  lea     rcx, [rsp+4A8h+psz]
0x180008dfe  lea     r8, aSpoolDriversCo; "\\spool\\drivers\\color"
0x180008e05  mov     edx, 7FFFFFFEh
0x180008e0a  lea     rcx, [rcx+rax*2]
0x180008e0e  sub     r13, rax
0x180008e11  jz      short loc_180008E35
0x180008e13  test    rdx, rdx
0x180008e16  jz      short loc_180008E35
0x180008e18  movzx   eax, word ptr [r8]
0x180008e1c  test    ax, ax
0x180008e1f  jz      short loc_180008E35
0x180008e21  mov     [rcx], ax
0x180008e24  add     r8, 2
0x180008e28  add     rcx, 2
0x180008e2c  dec     rdx
0x180008e2f  sub     r13, 1
0x180008e33  jnz     short loc_180008E13
0x180008e35  test    r13, r13
0x180008e38  lea     rax, [rcx-2]
0x180008e3c  mov     ebx, 8007007Ah
0x180008e41  cmovnz  rax, rcx
0x180008e45  cmovnz  ebx, r12d
0x180008e49  mov     [rax], r12w
0x180008e4d  jz      loc_180008EF4
0x180008e53  lea     rax, [rsp+4A8h+psz]
0x180008e58  mov     r11, 0FFFFFFFFFFFFFFFFh
0x180008e5f  cmp     [rax+r11*2+2], r12w
0x180008e65  lea     r11, [r11+1]
0x180008e69  jnz     short loc_180008E5F
0x180008e6b  mov     eax, dword ptr [rsp+4A8h+var_460]
0x180008e6f  lea     r11d, ds:2[r11*2]
0x180008e77  mov     edx, r11d
0x180008e7a  add     rax, rax
0x180008e7d  mov     [rdi], r11d
0x180008e80  cmp     rdx, rax
0x180008e83  ja      loc_1800090CA
0x180008e89  shr     rdx, 1; unsigned __int64
0x180008e8c  lea     r8, [rsp+4A8h+psz]; unsigned __int16 *
0x180008e91  mov     rcx, rbp; unsigned __int16 *
0x180008e94  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008e99  mov     ebx, eax
0x180008e9b  jmp     short loc_180008EF4
0x180008e9d  call    cs:__imp_GetLastError
0x180008ea3  mov     ebx, eax
0x180008ea5  test    eax, eax
0x180008ea7  jle     short loc_180008EB2
0x180008ea9  movzx   ebx, ax
0x180008eac  or      ebx, 80070000h
0x180008eb2  cmp     ebx, 800706F8h
0x180008eb8  jz      loc_1800090CA
0x180008ebe  cmp     ebx, 800706BAh
0x180008ec4  jz      loc_1800090D4
0x180008eca  test    ebx, ebx
0x180008ecc  jns     loc_180008FEF
0x180008ed2  mov     rcx, rbp; lpMem
0x180008ed5  call    MemFree
0x180008eda  jmp     loc_180008D5A
0x180008edf  call    cs:__imp_GetLastError
0x180008ee5  mov     ebx, eax
0x180008ee7  test    eax, eax
0x180008ee9  jle     short loc_180008EF4
0x180008eeb  movzx   ebx, ax
0x180008eee  or      ebx, 80070000h
0x180008ef4  test    ebx, ebx
0x180008ef6  js      short loc_180008ED2
0x180008ef8  mov     r8, rbp
0x180008efb  test    rsi, rsi
0x180008efe  jnz     loc_180008D47
0x180008f04  xor     eax, eax
0x180008f06  lock cmpxchg cs:gszLocalColorDirectory, rbp
0x180008f0f  cmovz   rbp, r12
0x180008f13  jmp     loc_180008D47
0x180008f18  call    cs:__imp_GetLastError
0x180008f1e  mov     ebx, eax
0x180008f20  test    eax, eax
0x180008f22  jg      short loc_180008EEB
0x180008f24  jmp     short loc_180008EF4
0x180008f26  mov     r13d, 208h
0x180008f2c  mov     ecx, r13d
0x180008f2f  mov     [rdi], r13d
0x180008f32  call    MemAlloc
0x180008f37  mov     rbp, rax
0x180008f3a  test    rax, rax
0x180008f3d  jnz     short loc_180008F52
0x180008f3f  mov     ebx, 8007000Eh
0x180008f44  movzx   ecx, bx; dwErrCode
0x180008f47  call    cs:__imp_SetLastError
0x180008f4d  jmp     loc_180008D62
0x180008f52  mov     ebx, [rdi]
0x180008f54  xor     r12d, r12d
0x180008f57  mov     eax, ebx
0x180008f59  shr     eax, 1
0x180008f5b  mov     dword ptr [rsp+4A8h+var_460], eax
0x180008f5f  test    rsi, rsi
0x180008f62  jnz     short loc_180008F82
0x180008f64  lea     rcx, [rsp+4A8h+pcchLength]; int *
0x180008f69  mov     dword ptr [rsp+4A8h+pcchLength], r12d
0x180008f6e  call    ?IsClusterServiceInstalled@@YAKPEAH@Z; IsClusterServiceInstalled(int *)
0x180008f73  test    eax, eax
0x180008f75  jnz     short loc_180008F82
0x180008f77  cmp     dword ptr [rsp+4A8h+pcchLength], r12d
0x180008f7c  jz      loc_1800090D4
0x180008f82  call    IsDeletePrinterDataExWPresent
0x180008f87  test    al, al
0x180008f89  jz      loc_1800090D4
0x180008f8f  mov     eax, [rdi]
0x180008f91  mov     r9, rbp; pDriverDirectory
0x180008f94  mov     [rsp+4A8h+pcbNeeded], rdi; pcbNeeded
0x180008f99  xor     edx, edx; pEnvironment
0x180008f9b  mov     r8d, 1; Level
0x180008fa1  mov     [rsp+4A8h+cbBuf], eax; cbBuf
0x180008fa5  mov     rcx, rsi; pName
0x180008fa8  call    cs:__imp_GetPrinterDriverDirectoryW
0x180008fae  test    eax, eax
0x180008fb0  jnz     short loc_180008FEF
0x180008fb2  call    cs:__imp_GetLastError
0x180008fb8  cmp     eax, 70Dh
0x180008fbd  jnz     loc_180008E9D
0x180008fc3  mov     [rsp+4A8h+pcbNeeded], rdi; pcbNeeded
0x180008fc8  lea     rdx, pEnvironment; "Windows NT x86"
0x180008fcf  mov     r9, rbp; pDriverDirectory
0x180008fd2  mov     [rsp+4A8h+cbBuf], ebx; cbBuf
0x180008fd6  mov     r8d, 1; Level
0x180008fdc  mov     [rdi], ebx
0x180008fde  mov     rcx, rsi; pName
0x180008fe1  call    cs:__imp_GetPrinterDriverDirectoryW
0x180008fe7  test    eax, eax
0x180008fe9  jz      loc_180008E9D
0x180008fef  mov     rcx, rbp; lpStringSource
0x180008ff2  call    GetFilenameFromPath
0x180008ff7  mov     rdx, rax
0x180008ffa  test    rax, rax
0x180008ffd  jz      loc_180008EDF
0x180009003  mov     r11, 0FFFFFFFFFFFFFFFFh
0x18000900a  mov     [rsp+4A8h+pcchLength], r12
0x18000900f  mov     rcx, r11
0x180009012  inc     rcx
0x180009015  cmp     [rax+rcx*2], r12w
0x18000901a  jnz     short loc_180009012
0x18000901c  imul    eax, ecx, -2
0x18000901f  add     [rdi], eax
0x180009021  lea     rax, gszColorDir; "COLOR"
0x180009028  inc     r11
0x18000902b  cmp     [rax+r11*2], r12w
0x180009030  jnz     short loc_180009028
0x180009032  mov     r13d, dword ptr [rsp+4A8h+var_460]
0x180009037  lea     r8, [rsp+4A8h+pcchLength]; unsigned __int64 *
0x18000903c  mov     [rdx], r12w
0x180009040  mov     rcx, rbp; unsigned __int16 *
0x180009043  mov     edx, r13d; unsigned __int64
0x180009046  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18000904b  mov     ebx, eax
0x18000904d  test    eax, eax
0x18000904f  js      loc_180008ED2
0x180009055  mov     rax, [rsp+4A8h+pcchLength]
0x18000905a  test    rax, rax
0x18000905d  jz      loc_180008EF8
0x180009063  add     r11d, r11d
0x180009066  lea     rdx, ds:0[rax*2]
0x18000906e  cmp     word ptr [rdx+rbp-2], 5Ch ; '\'
0x180009074  lea     eax, [r11+2]
0x180009078  cmovz   eax, r11d
0x18000907c  add     [rdi], eax
0x18000907e  lea     rax, ds:0[r13*2]
0x180009086  mov     ecx, [rdi]
0x180009088  cmp     rcx, rax
0x18000908b  ja      short loc_1800090CA
0x18000908d  cmp     word ptr [rdx+rbp-2], 5Ch ; '\'
0x180009093  jz      short loc_1800090B1
0x180009095  lea     r8, gszBackslash; "\\"
0x18000909c  mov     edx, r13d; unsigned __int64
0x18000909f  mov     rcx, rbp; unsigned __int16 *
0x1800090a2  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800090a7  mov     ebx, eax
0x1800090a9  test    eax, eax
0x1800090ab  js      loc_180008ED2
0x1800090b1  lea     r8, gszColorDir; "COLOR"
0x1800090b8  mov     rdx, r13; unsigned __int64
0x1800090bb  mov     rcx, rbp; unsigned __int16 *
0x1800090be  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800090c3  mov     ebx, eax
0x1800090c5  jmp     loc_180008EF4
0x1800090ca  mov     ebx, 8007007Ah
0x1800090cf  jmp     loc_180008ED2
0x1800090d4  xor     edx, edx; Val
0x1800090d6  lea     rcx, [rsp+4A8h+psz]; void *
0x1800090db  mov     r8d, 410h; Size
0x1800090e1  call    memset_0
0x1800090e6  mov     eax, [rdi]
0x1800090e8  lea     rcx, aInstalledcolor; "InstalledColorProfiles"
0x1800090ef  mov     [rsp+4A8h+var_478], r12
0x1800090f4  mov     r9d, 1
0x1800090fa  mov     dword ptr [rsp+4A8h+pcbNeeded], eax
0x1800090fe  xor     r8d, r8d
0x180009101  xor     edx, edx
0x180009103  mov     qword ptr [rsp+4A8h+cbBuf], rbp
0x180009108  call    cs:__imp_RtlGetPersistedStateLocation
0x18000910e  test    eax, eax
0x180009110  jns     loc_180008EF8
0x180009116  mov     edx, 104h; uSize
0x18000911b  lea     rcx, [rsp+4A8h+psz]; lpBuffer
0x180009120  call    cs:__imp_GetSystemDirectoryW
0x180009126  test    eax, eax
0x180009128  jz      loc_180008F18
0x18000912e  jmp     loc_180008DD3
```
