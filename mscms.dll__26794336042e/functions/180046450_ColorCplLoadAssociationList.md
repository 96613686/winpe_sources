# ColorCplLoadAssociationList

- ea: `0x180046450`
- end: `0x180046909`
- name: `ColorCplLoadAssociationList`
- size: `1209`
- prototype: `__int64 __fastcall(enum WCS_PROFILE_MANAGEMENT_SCOPE, unsigned __int16 *, unsigned int, LPCWSTR lpFileName, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops`

## callees

- `0x180023a78`
- `0x18002e5f0`
- `0x18002e614`
- `0x18002ea60`
- `0x180040d94`
- `0x180041bf0`
- `0x180046450`
- `0x1800471b0`
- `0x18004aa0c`
- `0x18004b680`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18004666f`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800466f4`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18004666f`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x1800466f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046556`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046610`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046556`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046610`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180046543`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180046543`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180046606`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180046606`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180046581`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180046581`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800468be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800468be`

## pseudocode

```c
__int64 __fastcall ColorCplLoadAssociationList(
        enum WCS_PROFILE_MANAGEMENT_SCOPE a1,
        unsigned __int16 *a2,
        unsigned int a3,
        LPCWSTR lpFileName,
        int a5)
{
  unsigned int v5; // edi
  __int64 v9; // rax
  __int64 v10; // rax
  void *v11; // r15
  HANDLE FileW; // rax
  void *v13; // r13
  signed int LastError; // eax
  signed int DefaultDeviceProfileInDefaultScope; // ebx
  DWORD LowPart; // ebx
  __int64 v17; // rsi
  unsigned int v18; // eax
  unsigned __int64 v19; // rax
  unsigned __int64 v20; // kr00_8
  signed int v21; // eax
  unsigned int v22; // ebx
  wchar_t *v23; // rcx
  unsigned int v24; // esi
  wchar_t *v25; // rax
  unsigned __int64 v26; // rcx
  unsigned __int64 v27; // rax
  void *v28; // rax
  unsigned int v29; // edx
  unsigned int v30; // r9d
  wchar_t *v31; // rcx
  _QWORD *v32; // r15
  wchar_t *v33; // rax
  __int64 v34; // rcx
  unsigned int v35; // edx
  unsigned int v36; // r9d
  unsigned int v37; // r12d
  enum WCS_PROFILE_MANAGEMENT_SCOPE v38; // r13d
  int v39; // ebx
  const unsigned __int16 **v40; // rdi
  unsigned __int16 *v41; // rax
  int v42; // r8d
  int v43; // ecx
  unsigned __int16 *v44; // rax
  int v45; // r9d
  int v46; // edx
  void *v47; // [rsp+40h] [rbp-C0h]
  int v48; // [rsp+48h] [rbp-B8h]
  DWORD NumberOfBytesRead; // [rsp+4Ch] [rbp-B4h] BYREF
  void *v50; // [rsp+50h] [rbp-B0h]
  enum WCS_PROFILE_MANAGEMENT_SCOPE v51; // [rsp+58h] [rbp-A8h]
  int v52; // [rsp+5Ch] [rbp-A4h]
  unsigned int v53; // [rsp+60h] [rbp-A0h]
  union _LARGE_INTEGER FileSize; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *Context; // [rsp+70h] [rbp-90h] BYREF
  HANDLE v56; // [rsp+78h] [rbp-88h]
  wchar_t Delimiter[8]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR FileName[264]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v59[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  unsigned __int16 v60[264]; // [rsp+4B0h] [rbp+3B0h] BYREF
  unsigned __int16 v61[264]; // [rsp+6C0h] [rbp+5C0h] BYREF

  v53 = a3;
  v5 = a3;
  v51 = a1;
  if ( !dword_18009F478 )
    return 2147745801LL;
  if ( a2 )
  {
    v9 = -1;
    do
      ++v9;
    while ( a2[v9] );
    if ( v9
      && (a3 == 1835955314 || a3 == 1886549106 || a3 == 1935896178)
      && (unsigned int)a1 <= WCS_PROFILE_MANAGEMENT_SCOPE_CURRENT_USER )
    {
      if ( lpFileName )
      {
        v10 = -1;
        do
          ++v10;
        while ( lpFileName[v10] );
        if ( v10 )
        {
          v50 = 0;
          v11 = 0;
          v48 = 0;
          FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x8000080u, 0);
          v56 = FileW;
          v13 = FileW;
          if ( FileW == (HANDLE)-1LL || (FileSize.QuadPart = 0, !GetFileSizeEx(FileW, &FileSize)) )
          {
            LastError = GetLastError();
            DefaultDeviceProfileInDefaultScope = LastError;
            if ( LastError > 0 )
              DefaultDeviceProfileInDefaultScope = (unsigned __int16)LastError | 0x80070000;
LABEL_30:
            if ( DefaultDeviceProfileInDefaultScope < 0 )
              goto LABEL_74;
            goto LABEL_72;
          }
          if ( FileSize.HighPart
            || (LowPart = FileSize.LowPart, (FileSize.LowPart & 1) != 0)
            || (v17 = FileSize.LowPart >> 1, v18 = v17 + 1, (unsigned int)(v17 + 1) > 0x7FFFFFFF) )
          {
            DefaultDeviceProfileInDefaultScope = -2147221499;
            goto LABEL_77;
          }
          v20 = v18;
          v19 = 2LL * v18;
          if ( !is_mul_ok(v20, 2u) )
            v19 = -1;
          v11 = operator new[](v19, (const struct std::nothrow_t *)&std::nothrow);
          v47 = v11;
          if ( !v11 )
          {
LABEL_26:
            DefaultDeviceProfileInDefaultScope = -2147024882;
            goto LABEL_77;
          }
          NumberOfBytesRead = 0;
          if ( !ReadFile(v13, v11, LowPart, &NumberOfBytesRead, 0) )
          {
            v21 = GetLastError();
            DefaultDeviceProfileInDefaultScope = v21;
            if ( v21 > 0 )
              DefaultDeviceProfileInDefaultScope = (unsigned __int16)v21 | 0x80070000;
            goto LABEL_30;
          }
          if ( NumberOfBytesRead != LowPart )
          {
            DefaultDeviceProfileInDefaultScope = -2147221500;
            goto LABEL_77;
          }
          v22 = 0;
          v23 = (wchar_t *)v11;
          *((_WORD *)v11 + v17) = 0;
          v24 = 0;
          wcscpy(Delimiter, L"\n\r");
          Context = 0;
          while ( 1 )
          {
            v25 = wcstok_s(v23, Delimiter, &Context);
            if ( !v25 )
              break;
            v26 = -1;
            do
              ++v26;
            while ( v25[v26] );
            if ( v26 > 0x104 )
            {
              DefaultDeviceProfileInDefaultScope = -2147221499;
              goto LABEL_77;
            }
            ++v24;
            v25[v26] = 10;
            v23 = 0;
          }
          v27 = 8LL * v24;
          if ( !is_mul_ok(v24, 8u) )
            v27 = -1;
          v28 = operator new[](v27, (const struct std::nothrow_t *)&std::nothrow);
          v50 = v28;
          if ( !v28 )
            goto LABEL_26;
          Context = 0;
          v31 = (wchar_t *)v11;
          if ( v24 )
          {
            v32 = v28;
            do
            {
              v33 = wcstok_s(v31, Delimiter, &Context);
              v34 = v22++;
              v32[v34] = v33;
              v31 = 0;
            }
            while ( v22 < v24 );
          }
          if ( v5 != 1835955314
            || (DefaultDeviceProfileInDefaultScope = GetDefaultDeviceProfileInDefaultScope(a2, v29, v59, v30, v60),
                DefaultDeviceProfileInDefaultScope >= 0) )
          {
            v52 = ColorCplSupportUtil::SetProfileData(
                    a1,
                    a2,
                    v5,
                    a5 != 0 ? 5 : 1,
                    (unsigned __int8 *)&word_1800884E0,
                    2u);
            DefaultDeviceProfileInDefaultScope = v52;
            if ( v52 >= 0 )
            {
              v37 = 0;
              if ( v24 )
              {
                v38 = v51;
                v39 = 0;
                v40 = (const unsigned __int16 **)v50;
                do
                {
                  if ( !InternalAssociateColorProfileWithDevice(v38, v40[v24 - v37 - 1], a2, 0, 0, a5) )
                    v39 = 1;
                  ++v37;
                }
                while ( v37 < v24 );
                v5 = v53;
                v13 = v56;
                v48 = v39;
                DefaultDeviceProfileInDefaultScope = v52;
              }
              if ( v5 != 1835955314 && v5 != 1936744803 || !v59[0] )
                goto LABEL_71;
              DefaultDeviceProfileInDefaultScope = GetDefaultDeviceProfileInDefaultScope(a2, v35, v61, v36, FileName);
              if ( DefaultDeviceProfileInDefaultScope >= 0 )
              {
                if ( a5 )
                {
                  v41 = v60;
                  do
                  {
                    v42 = *(v41 - 528);
                    v43 = *v41 - v42;
                    if ( v43 )
                      break;
                    ++v41;
                  }
                  while ( v42 );
                  if ( v43 && (int)SetMHC2DataToDisplay(a2, FileName) >= 0 )
                    goto LABEL_70;
                }
                v44 = v59;
                do
                {
                  v45 = v44[528];
                  v46 = *v44 - v45;
                  if ( v46 )
                    break;
                  ++v44;
                }
                while ( v45 );
                if ( v46 )
                {
LABEL_70:
                  InternalRefreshCalibration(a2, 0);
                  NotifyOfPossibleColorProfileChange();
                }
LABEL_71:
                v11 = v47;
LABEL_72:
                if ( v48 )
                  DefaultDeviceProfileInDefaultScope = -2147221498;
LABEL_74:
                if ( v13 == (void *)-1LL )
                {
LABEL_78:
                  operator delete(v11);
                  operator delete(v50);
                  return (unsigned int)DefaultDeviceProfileInDefaultScope;
                }
LABEL_77:
                CloseHandle(v13);
                goto LABEL_78;
              }
            }
          }
          v11 = v47;
          goto LABEL_77;
        }
      }
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180046450  mov     [rsp-8+arg_10], rbx
0x180046455  push    rbp
0x180046456  push    rsi
0x180046457  push    rdi
0x180046458  push    r12
0x18004645a  push    r13
0x18004645c  push    r14
0x18004645e  push    r15
0x180046460  lea     rbp, [rsp-7E0h]
0x180046468  sub     rsp, 8E0h
0x18004646f  mov     rax, cs:__security_cookie
0x180046476  xor     rax, rsp
0x180046479  mov     [rbp+810h+var_40], rax
0x180046480  xor     esi, esi
0x180046482  mov     [rsp+910h+var_8B0], r8d
0x180046487  cmp     cs:dword_18009F478, esi
0x18004648d  mov     r10, r9
0x180046490  mov     edi, r8d
0x180046493  mov     [rsp+910h+var_8B8], ecx
0x180046497  mov     r14, rdx
0x18004649a  mov     r12d, ecx
0x18004649d  jnz     short loc_1800464A9
0x18004649f  mov     eax, 80040009h
0x1800464a4  jmp     loc_1800468DF
0x1800464a9  test    r14, r14
0x1800464ac  jz      loc_1800468DA
0x1800464b2  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800464b6  mov     rax, rbx
0x1800464b9  inc     rax
0x1800464bc  cmp     [rdx+rax*2], si
0x1800464c0  jnz     short loc_1800464B9
0x1800464c2  test    rax, rax
0x1800464c5  jz      loc_1800468DA
0x1800464cb  cmp     edi, 6D6E7472h
0x1800464d1  jz      short loc_1800464E7
0x1800464d3  cmp     edi, 70727472h
0x1800464d9  jz      short loc_1800464E7
0x1800464db  cmp     edi, 73636E72h
0x1800464e1  jnz     loc_1800468DA
0x1800464e7  mov     ecx, 1
0x1800464ec  cmp     r12d, ecx
0x1800464ef  ja      loc_1800468DA
0x1800464f5  test    r10, r10
0x1800464f8  jz      loc_1800468DA
0x1800464fe  mov     rax, rbx
0x180046501  inc     rax
0x180046504  cmp     [r9+rax*2], si
0x180046509  jnz     short loc_180046501
0x18004650b  test    rax, rax
0x18004650e  jz      loc_1800468DA
0x180046514  mov     [rsp+910h+hTemplateFile], rsi; hTemplateFile
0x180046519  mov     r8d, ecx; dwShareMode
0x18004651c  mov     [rsp+910h+dwFlagsAndAttributes], 8000080h; dwFlagsAndAttributes
0x180046524  mov     rcx, r10; lpFileName
0x180046527  xor     r9d, r9d; lpSecurityAttributes
0x18004652a  mov     [rsp+910h+dwCreationDisposition], 3; dwCreationDisposition
0x180046532  mov     edx, 80000000h; dwDesiredAccess
0x180046537  mov     [rsp+910h+var_8C0], rsi
0x18004653c  mov     r15, rsi
0x18004653f  mov     [rsp+910h+var_8C8], esi
0x180046543  call    cs:__imp_CreateFileW
0x180046549  mov     [rsp+910h+var_898], rax
0x18004654e  mov     r13, rax
0x180046551  cmp     rax, rbx
0x180046554  jnz     short loc_180046574
0x180046556  call    cs:__imp_GetLastError
0x18004655c  mov     ebx, eax
0x18004655e  test    eax, eax
0x180046560  jle     loc_180046627
0x180046566  movzx   ebx, ax
0x180046569  or      ebx, 80070000h
0x18004656f  jmp     loc_180046627
0x180046574  lea     rdx, [rsp+910h+FileSize]; lpFileSize
0x180046579  mov     qword ptr [rsp+910h+FileSize], rsi
0x18004657e  mov     rcx, r13; hFile
0x180046581  call    cs:__imp_GetFileSizeEx
0x180046587  test    eax, eax
0x180046589  jz      short loc_180046556
0x18004658b  cmp     dword ptr [rsp+910h+FileSize+4], esi
0x18004658f  jz      short loc_18004659B
0x180046591  mov     ebx, 80040005h
0x180046596  jmp     loc_1800468BB
0x18004659b  mov     ebx, dword ptr [rsp+910h+FileSize]
0x18004659f  test    bl, 1
0x1800465a2  jnz     short loc_180046591
0x1800465a4  mov     esi, ebx
0x1800465a6  shr     esi, 1
0x1800465a8  lea     eax, [rsi+1]
0x1800465ab  cmp     eax, 7FFFFFFFh
0x1800465b0  ja      short loc_180046591
0x1800465b2  mov     ecx, eax
0x1800465b4  mov     eax, 2
0x1800465b9  mul     rcx
0x1800465bc  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800465c3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800465ca  cmovb   rax, rcx
0x1800465ce  mov     rcx, rax; unsigned __int64
0x1800465d1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800465d6  mov     r15, rax
0x1800465d9  mov     [rsp+910h+var_8D0], rax
0x1800465de  xor     eax, eax
0x1800465e0  test    r15, r15
0x1800465e3  jnz     short loc_1800465EF
0x1800465e5  mov     ebx, 8007000Eh
0x1800465ea  jmp     loc_1800468BB
0x1800465ef  lea     r9, [rsp+910h+NumberOfBytesRead]; lpNumberOfBytesRead
0x1800465f4  mov     [rsp+910h+NumberOfBytesRead], eax
0x1800465f8  mov     r8d, ebx; nNumberOfBytesToRead
0x1800465fb  mov     qword ptr [rsp+910h+dwCreationDisposition], rax; lpOverlapped
0x180046600  mov     rdx, r15; lpBuffer
0x180046603  mov     rcx, r13; hFile
0x180046606  call    cs:__imp_ReadFile
0x18004660c  test    eax, eax
0x18004660e  jnz     short loc_180046634
0x180046610  call    cs:__imp_GetLastError
0x180046616  xor     esi, esi
0x180046618  mov     ebx, eax
0x18004661a  test    eax, eax
0x18004661c  jle     short loc_180046627
0x18004661e  movzx   ebx, ax
0x180046621  or      ebx, 80070000h
0x180046627  test    ebx, ebx
0x180046629  js      loc_1800468AE
0x18004662f  jmp     loc_1800468A2
0x180046634  cmp     [rsp+910h+NumberOfBytesRead], ebx
0x180046638  jz      short loc_180046641
0x18004663a  mov     ebx, 80040004h
0x18004663f  jmp     short loc_1800465EA
0x180046641  xor     ebx, ebx
0x180046643  mov     rcx, r15; String
0x180046646  mov     [r15+rsi*2], bx
0x18004664b  mov     esi, ebx
0x18004664d  mov     eax, dword ptr cs:asc_18008C330; "\n\r"
0x180046653  mov     dword ptr [rbp+810h+Delimiter], eax
0x180046656  movzx   eax, word ptr cs:asc_18008C330+4; ""
0x18004665d  mov     [rbp+810h+var_88C], ax
0x180046661  mov     [rsp+910h+Context], rbx
0x180046666  lea     r8, [rsp+910h+Context]; Context
0x18004666b  lea     rdx, [rbp+810h+Delimiter]; Delimiter
0x18004666f  call    cs:__imp_wcstok_s
0x180046675  test    rax, rax
0x180046678  jz      short loc_1800466AA
0x18004667a  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004667e  inc     rcx
0x180046681  cmp     [rax+rcx*2], bx
0x180046685  jnz     short loc_18004667E
0x180046687  cmp     rcx, 104h
0x18004668e  ja      short loc_1800466A0
0x180046690  mov     edx, 0Ah
0x180046695  inc     esi
0x180046697  mov     [rax+rcx*2], dx
0x18004669b  mov     rcx, rbx
0x18004669e  jmp     short loc_180046666
0x1800466a0  mov     ebx, 80040005h
0x1800466a5  jmp     loc_1800465EA
0x1800466aa  mov     ecx, esi
0x1800466ac  mov     eax, 8
0x1800466b1  mul     rcx
0x1800466b4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800466bb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800466c2  cmovb   rax, rcx
0x1800466c6  mov     rcx, rax; unsigned __int64
0x1800466c9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800466ce  mov     [rsp+910h+var_8C0], rax
0x1800466d3  test    rax, rax
0x1800466d6  jz      loc_1800465E5
0x1800466dc  mov     [rsp+910h+Context], rbx
0x1800466e1  mov     rcx, r15; String
0x1800466e4  test    esi, esi
0x1800466e6  jz      short loc_180046708
0x1800466e8  mov     r15, rax
0x1800466eb  lea     r8, [rsp+910h+Context]; Context
0x1800466f0  lea     rdx, [rbp+810h+Delimiter]; Delimiter
0x1800466f4  call    cs:__imp_wcstok_s
0x1800466fa  mov     ecx, ebx
0x1800466fc  inc     ebx
0x1800466fe  mov     [r15+rcx*8], rax
0x180046702  xor     ecx, ecx
0x180046704  cmp     ebx, esi
0x180046706  jb      short loc_1800466EB
0x180046708  cmp     edi, 6D6E7472h
0x18004670e  jz      short loc_180046718
0x180046710  cmp     edi, 73706163h
0x180046716  jnz     short loc_18004673D
0x180046718  lea     rax, [rbp+810h+var_460]
0x18004671f  mov     rcx, r14; pDeviceName
0x180046722  lea     r8, [rbp+810h+var_670]; unsigned __int16 *
0x180046729  mov     qword ptr [rsp+910h+dwCreationDisposition], rax; unsigned __int16 *
0x18004672e  call    ?GetDefaultDeviceProfileInDefaultScope@@YAJPEBGIPEAGI1@Z; GetDefaultDeviceProfileInDefaultScope(ushort const *,uint,ushort *,uint,ushort *)
0x180046733  mov     ebx, eax
0x180046735  test    eax, eax
0x180046737  js      loc_1800468B6
0x18004673d  mov     r15d, [rbp+810h+arg_20]
0x180046744  mov     r8d, edi; unsigned int
0x180046747  mov     eax, r15d
0x18004674a  mov     [rsp+910h+dwFlagsAndAttributes], 2; unsigned int
0x180046752  neg     eax
0x180046754  mov     rdx, r14; unsigned __int16 *
0x180046757  lea     rax, word_1800884E0
0x18004675e  mov     ecx, r12d; enum WCS_PROFILE_MANAGEMENT_SCOPE
0x180046761  sbb     r9d, r9d
0x180046764  mov     qword ptr [rsp+910h+dwCreationDisposition], rax; unsigned __int8 *
0x180046769  and     r9d, 4
0x18004676d  inc     r9d; unsigned int
0x180046770  call    ?SetProfileData@ColorCplSupportUtil@@CAJW4WCS_PROFILE_MANAGEMENT_SCOPE@@PEBGKKPEAEK@Z; ColorCplSupportUtil::SetProfileData(WCS_PROFILE_MANAGEMENT_SCOPE,ushort const *,ulong,ulong,uchar *,ulong)
0x180046775  xor     ecx, ecx
0x180046777  mov     [rsp+910h+var_8B4], eax
0x18004677b  mov     ebx, eax
0x18004677d  test    eax, eax
0x18004677f  js      loc_1800468B6
0x180046785  mov     r12d, ecx
0x180046788  test    esi, esi
0x18004678a  jz      short loc_1800467DD
0x18004678c  mov     r13d, [rsp+910h+var_8B8]
0x180046791  mov     ebx, ecx
0x180046793  mov     rdi, [rsp+910h+var_8C0]
0x180046798  mov     eax, esi
0x18004679a  mov     [rsp+910h+dwFlagsAndAttributes], r15d; int
0x18004679f  sub     eax, r12d
0x1800467a2  mov     [rsp+910h+dwCreationDisposition], ecx; int
0x1800467a6  dec     eax
0x1800467a8  xor     r9d, r9d; int
0x1800467ab  mov     r8, r14; unsigned __int16 *
0x1800467ae  mov     ecx, r13d; enum WCS_PROFILE_MANAGEMENT_SCOPE
0x1800467b1  mov     rdx, [rdi+rax*8]; unsigned __int16 *
0x1800467b5  call    ?InternalAssociateColorProfileWithDevice@@YAHW4WCS_PROFILE_MANAGEMENT_SCOPE@@PEBG1HHH@Z; InternalAssociateColorProfileWithDevice(WCS_PROFILE_MANAGEMENT_SCOPE,ushort const *,ushort const *,int,int,int)
0x1800467ba  xor     ecx, ecx
0x1800467bc  test    eax, eax
0x1800467be  lea     eax, [rcx+1]
0x1800467c1  cmovz   ebx, eax
0x1800467c4  add     r12d, eax
0x1800467c7  cmp     r12d, esi
0x1800467ca  jb      short loc_180046798
0x1800467cc  mov     edi, [rsp+910h+var_8B0]
0x1800467d0  mov     r13, [rsp+910h+var_898]
0x1800467d5  mov     [rsp+910h+var_8C8], ebx
0x1800467d9  mov     ebx, [rsp+910h+var_8B4]
0x1800467dd  cmp     edi, 6D6E7472h
0x1800467e3  jz      short loc_1800467F1
0x1800467e5  cmp     edi, 73706163h
0x1800467eb  jnz     loc_18004689B
0x1800467f1  xor     esi, esi
0x1800467f3  cmp     [rbp+810h+var_670], si
0x1800467fa  jz      loc_18004689D
0x180046800  lea     rax, [rbp+810h+FileName]
0x180046804  mov     rcx, r14; pDeviceName
0x180046807  lea     r8, [rbp+810h+var_250]; unsigned __int16 *
0x18004680e  mov     qword ptr [rsp+910h+dwCreationDisposition], rax; unsigned __int16 *
0x180046813  call    ?GetDefaultDeviceProfileInDefaultScope@@YAJPEBGIPEAGI1@Z; GetDefaultDeviceProfileInDefaultScope(ushort const *,uint,ushort *,uint,ushort *)
0x180046818  mov     ebx, eax
0x18004681a  test    eax, eax
0x18004681c  js      loc_1800468B6
0x180046822  test    r15d, r15d
0x180046825  jz      short loc_18004685F
0x180046827  lea     rax, [rbp+810h+var_460]
0x18004682e  lea     rdx, [rbp+810h+FileName]
0x180046832  sub     rdx, rax
0x180046835  movzx   ecx, word ptr [rax]
0x180046838  movzx   r8d, word ptr [rax+rdx]
0x18004683d  sub     ecx, r8d
0x180046840  jnz     short loc_18004684B
0x180046842  add     rax, 2
0x180046846  test    r8d, r8d
0x180046849  jnz     short loc_180046835
0x18004684b  test    ecx, ecx
0x18004684d  jz      short loc_18004685F
0x18004684f  lea     rdx, [rbp+810h+FileName]; lpFileName
0x180046853  mov     rcx, r14; unsigned __int16 *
0x180046856  call    ?SetMHC2DataToDisplay@@YAJPEBG0@Z; SetMHC2DataToDisplay(ushort const *,ushort const *)
0x18004685b  test    eax, eax
0x18004685d  jns     short loc_18004688A
0x18004685f  lea     rax, [rbp+810h+var_670]
0x180046866  lea     r8, [rbp+810h+var_250]
0x18004686d  sub     r8, rax
0x180046870  movzx   edx, word ptr [rax]
0x180046873  movzx   r9d, word ptr [rax+r8]
0x180046878  sub     edx, r9d
0x18004687b  jnz     short loc_180046886
0x18004687d  add     rax, 2
0x180046881  test    r9d, r9d
0x180046884  jnz     short loc_180046870
0x180046886  test    edx, edx
0x180046888  jz      short loc_18004689D
0x18004688a  xor     edx, edx
0x18004688c  mov     rcx, r14; lpString1
0x18004688f  call    InternalRefreshCalibration
0x180046894  call    ?NotifyOfPossibleColorProfileChange@@YAXXZ; NotifyOfPossibleColorProfileChange(void)
0x180046899  jmp     short loc_18004689D
0x18004689b  xor     esi, esi
0x18004689d  mov     r15, [rsp+910h+var_8D0]
0x1800468a2  cmp     [rsp+910h+var_8C8], esi
0x1800468a6  mov     eax, 80040006h
0x1800468ab  cmovnz  ebx, eax
0x1800468ae  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x1800468b2  jz      short loc_1800468C4
0x1800468b4  jmp     short loc_1800468BB
0x1800468b6  mov     r15, [rsp+910h+var_8D0]
0x1800468bb  mov     rcx, r13; hObject
0x1800468be  call    cs:__imp_CloseHandle
0x1800468c4  mov     rcx, r15; void *
  ... truncated ...
```
