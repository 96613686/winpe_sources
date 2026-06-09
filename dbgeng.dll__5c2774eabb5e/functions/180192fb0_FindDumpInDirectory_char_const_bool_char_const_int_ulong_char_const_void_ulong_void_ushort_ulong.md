# FindDumpInDirectory(char const *,bool,char const *,int (*)(ulong,char const *,void *,ulong,void *),ushort *,ulong)

- ea: `0x180192fb0`
- end: `0x1801937d6`
- name: `?FindDumpInDirectory@@YAJPEBD_N0P6AHK0PEAXK2@ZPEAGK@Z`
- size: `2086`
- prototype: `__int64 __usercall@<rax>(const char *@<rcx>, bool@<dl>, const char *@<r8>, int (*)(unsigned int, const char *, void *, unsigned int, void *)@<r9>, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops`

## callers

- `0x1801a46ac`

## callees

- `0x180073230`
- `0x18009a070`
- `0x1800aa0e0`
- `0x1800cffa8`
- `0x1800f0f40`
- `0x18018f42c`
- `0x18018fdb8`
- `0x180190470`
- `0x180190944`
- `0x180192fb0`
- `0x180193848`
- `0x1801939e8`
- `0x180194208`
- `0x180194588`
- `0x18019475c`
- `0x180416398`
- `0x180416438`
- `0x18041649c`
- `0x1804da397`
- `0x1804da4c0`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!calloc` at `0x180193058`
- `api-ms-win-crt-heap-l1-1-0!calloc` at `0x18019309e`
- `api-ms-win-crt-heap-l1-1-0!calloc` at `0x1801930bf`
- `api-ms-win-crt-heap-l1-1-0!calloc` at `0x180193058`
- `api-ms-win-crt-heap-l1-1-0!calloc` at `0x18019309e`
- `api-ms-win-crt-heap-l1-1-0!calloc` at `0x1801930bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801935db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180193619`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019368a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801935db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180193619`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019368a`
- `api-ms-win-core-file-l1-1-0!FindNextFileA` at `0x1801934b0`
- `api-ms-win-core-file-l1-1-0!FindNextFileA` at `0x1801934b0`
- `api-ms-win-core-file-l1-1-0!FindFirstFileA` at `0x18019331e`
- `api-ms-win-core-file-l1-1-0!FindFirstFileA` at `0x18019331e`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801934c7`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801934c7`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180193571`
- `api-ms-win-core-file-l1-1-0!CreateFileA` at `0x180193571`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall FindDumpInDirectory(
        const char *a1,
        char a2,
        const char *a3,
        int (*a4)(unsigned int, const char *, void *, unsigned int, void *),
        unsigned __int16 *Buffer)
{
  __int64 v9; // rax
  CHAR *v10; // rax
  wchar_t *v11; // rax
  int MatchInDirectory; // ebx
  int v13; // ebx
  const char *v14; // rdx
  int v15; // esi
  const char *FileName; // rax
  __int64 v17; // rax
  int v18; // esi
  __int64 v19; // rax
  HANDLE FirstFileA; // rsi
  __int64 v21; // rax
  int v22; // ebx
  __int64 v23; // rax
  char *v24; // rbx
  __int64 v25; // r8
  const CHAR *v26; // rax
  __int64 v27; // rdx
  unsigned int dwCreationDisposition; // [rsp+28h] [rbp-E0h]
  bool v30[8]; // [rsp+48h] [rbp-C0h] BYREF
  const char *Str; // [rsp+50h] [rbp-B8h] BYREF
  char *Str_8[2]; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v33; // [rsp+68h] [rbp-A0h]
  __int64 v34; // [rsp+70h] [rbp-98h]
  HANDLE hObject; // [rsp+78h] [rbp-90h] BYREF
  wchar_t *v36; // [rsp+80h] [rbp-88h] BYREF
  LPCSTR lpFileName; // [rsp+88h] [rbp-80h] BYREF
  _QWORD v38[5]; // [rsp+90h] [rbp-78h] BYREF
  char v39[8]; // [rsp+B8h] [rbp-50h] BYREF
  _BYTE v40[24]; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v41; // [rsp+D8h] [rbp-30h]
  __int16 v42; // [rsp+E0h] [rbp-28h]
  int v43; // [rsp+E8h] [rbp-20h]
  HANDLE *p_hObject; // [rsp+F0h] [rbp-18h] BYREF
  char v45; // [rsp+F8h] [rbp-10h]
  struct _WIN32_FIND_DATAA FindFileData; // [rsp+118h] [rbp+10h] BYREF

  v38[3] = -2;
  if ( !a1 || !Buffer )
    return 2147500037LL;
  lpFileName = 0;
  Str = 0;
  v36 = 0;
  v38[0] = &lpFileName;
  v38[1] = &Str;
  v38[2] = &v36;
  v38[4] = v38;
  v9 = -1;
  do
    ++v9;
  while ( a1[v9] );
  v10 = (CHAR *)calloc((unsigned int)(v9 + 3), 1u);
  lpFileName = v10;
  if ( v10 )
  {
    CopyNString(v10);
    CatNString((void *)lpFileName);
    Str = (const char *)calloc(0x208u, 1u);
    if ( Str )
    {
      v11 = (wchar_t *)calloc(0x208u, 2u);
      v36 = v11;
      if ( v11 )
      {
        if ( a3 )
        {
          v30[0] = 0;
          MatchInDirectory = FindMatchInDirectory(a1, a3, 0, Buffer, dwCreationDisposition, v30);
          if ( MatchInDirectory >= 0 && !v30[0] )
            MatchInDirectory = -2147483637;
          goto LABEL_63;
        }
        *(_OWORD *)Str_8 = 0;
        v33 = 0;
        LOBYTE(v34) = 0;
        v13 = 0;
        while ( 1 )
        {
          v14 = (const char *)(&g_ExpandDumpExt)[v13];
          v30[0] = 0;
          v15 = FindMatchInDirectory(a1, v14, *v14 == 46, v11, dwCreationDisposition, v30);
          if ( v15 < 0 )
          {
            if ( Str_8[0] )
            {
              std::_Destroy_range<std::allocator<std::tuple<long,unsigned short,std::string,bool>>>(Str_8[0], Str_8[1]);
              std::_Deallocate<16>(Str_8[0], 8 * ((signed __int64)(v33 - (unsigned __int64)Str_8[0]) >> 3));
              *(_OWORD *)Str_8 = 0;
              v33 = 0;
            }
            MatchInDirectory = v15;
            goto LABEL_63;
          }
          if ( v30[0] && (unsigned int)PrintString(Str, 520, "%ls", v36) )
          {
            FileName = GetFileName(Str);
            if ( IsDummyTargetFileA(FileName) )
            {
              v17 = std::string::string(&p_hObject, Str);
              v39[0] = 0;
              *(_OWORD *)v40 = 0;
              *(_QWORD *)v40 = *(_QWORD *)v17;
              *(_OWORD *)&v40[8] = *(_OWORD *)(v17 + 8);
              v41 = *(_QWORD *)(v17 + 24);
              *(_QWORD *)(v17 + 16) = 0;
              *(_QWORD *)(v17 + 24) = 15;
              *(_BYTE *)v17 = 0;
              v42 = *((_WORD *)&g_ExpandDumpExtPriorities + v13);
              v43 = 0;
              std::priority_queue<std::tuple<long,unsigned short,std::string,bool>>::push(Str_8, v39);
              std::string::_Tidy_deallocate(v40);
              std::string::_Tidy_deallocate(&p_hObject);
            }
            else
            {
              if ( !a2 || (v18 = 3, strcmp_0((const char *)(&g_ExpandDumpExt)[v13], ".run")) )
                v18 = 2;
              v19 = std::string::string(&p_hObject, Str);
              v39[0] = 0;
              *(_OWORD *)v40 = 0;
              *(_QWORD *)v40 = *(_QWORD *)v19;
              *(_OWORD *)&v40[8] = *(_OWORD *)(v19 + 8);
              v41 = *(_QWORD *)(v19 + 24);
              *(_QWORD *)(v19 + 16) = 0;
              *(_QWORD *)(v19 + 24) = 15;
              *(_BYTE *)v19 = 0;
              v42 = *((_WORD *)&g_ExpandDumpExtPriorities + v13);
              v43 = v18;
              std::priority_queue<std::tuple<long,unsigned short,std::string,bool>>::push(Str_8, v39);
              std::string::_Tidy_deallocate(v40);
              std::string::_Tidy_deallocate(&p_hObject);
            }
          }
          if ( (unsigned int)++v13 >= 0xE )
            break;
          v11 = v36;
        }
        if ( a4 )
        {
          memset(&FindFileData, 0, sizeof(FindFileData));
          FirstFileA = FindFirstFileA(lpFileName, &FindFileData);
          if ( FirstFileA != (HANDLE)-1LL )
          {
            while ( 1 )
            {
              *(_WORD *)v30 = 0;
              if ( ((unsigned int (__fastcall *)(__int64, CHAR *, _QWORD))a4)(2, FindFileData.cFileName, 0) )
              {
                if ( IsDummyTargetFileA(FindFileData.cFileName) )
                {
                  if ( (unsigned int)PrintString(Str, 520, "%hs\\%hs", a1, FindFileData.cFileName) )
                  {
                    v21 = std::string::string(&p_hObject, Str);
                    v39[0] = 1;
                    *(_OWORD *)v40 = 0;
                    *(_QWORD *)v40 = *(_QWORD *)v21;
                    *(_OWORD *)&v40[8] = *(_OWORD *)(v21 + 8);
                    v41 = *(_QWORD *)(v21 + 24);
                    *(_QWORD *)(v21 + 16) = 0;
                    *(_QWORD *)(v21 + 24) = 15;
                    *(_BYTE *)v21 = 0;
                    v42 = *(_WORD *)v30;
                    v43 = 0;
                    std::priority_queue<std::tuple<long,unsigned short,std::string,bool>>::push(Str_8, v39);
                    std::string::_Tidy_deallocate(v40);
LABEL_32:
                    std::string::_Tidy_deallocate(&p_hObject);
                  }
                }
                else if ( (unsigned int)PrintString(Str, 520, "%hs\\%hs", a1, FindFileData.cFileName) )
                {
                  v22 = (((unsigned int (__fastcall *)(_QWORD, CHAR *, _QWORD, _QWORD, _QWORD))a4)(
                           0,
                           FindFileData.cFileName,
                           0,
                           0,
                           0) != 0)
                      + 1;
                  v23 = std::string::string(&p_hObject, Str);
                  v39[0] = 1;
                  *(_OWORD *)v40 = 0;
                  *(_QWORD *)v40 = *(_QWORD *)v23;
                  *(_OWORD *)&v40[8] = *(_OWORD *)(v23 + 8);
                  v41 = *(_QWORD *)(v23 + 24);
                  *(_QWORD *)(v23 + 16) = 0;
                  *(_QWORD *)(v23 + 24) = 15;
                  *(_BYTE *)v23 = 0;
                  v42 = *(_WORD *)v30;
                  v43 = v22;
                  std::priority_queue<std::tuple<long,unsigned short,std::string,bool>>::push(Str_8, v39);
                  std::string::_Tidy_deallocate(v40);
                  goto LABEL_32;
                }
              }
              if ( !FindNextFileA(FirstFileA, &FindFileData) )
              {
                FindClose(FirstFileA);
                break;
              }
            }
          }
        }
        while ( 1 )
        {
          v24 = Str_8[0];
          if ( Str_8[0] == Str_8[1] )
            break;
          v39[0] = *Str_8[0];
          std::string::string(v40, Str_8[0] + 8);
          v42 = *((_WORD *)v24 + 20);
          v43 = *((_DWORD *)v24 + 12);
          LOBYTE(v25) = v34;
          std::_Pop_heap_unchecked<std::tuple<long,unsigned short,std::string,bool> *,std::less<std::tuple<long,unsigned short,std::string,bool>>>(
            Str_8[0],
            Str_8[1],
            v25);
          std::string::_Tidy_deallocate(Str_8[1] - 48);
          Str_8[1] -= 56;
          hObject = (HANDLE)-1LL;
          p_hObject = &hObject;
          v45 = 1;
          v26 = (const CHAR *)std::_String_val<std::_Simple_types<char>>::_Myptr(v40);
          hObject = CreateFileA(v26, 0x80000000, 1u, 0, 3u, 0x80u, 0);
          if ( hObject == (HANDLE)-1LL )
          {
            v45 = 0;
          }
          else
          {
            if ( !v39[0]
              || !a4
              || (v27 = std::_String_val<std::_Simple_types<char>>::_Myptr(v40),
                  ((unsigned int (__fastcall *)(__int64, __int64))a4)(1, v27)) )
            {
              std::_String_val<std::_Simple_types<char>>::_Myptr(v40);
              if ( (unsigned int)PrintStringW(Buffer, 0x208u, (wchar_t *)L"%hs") )
              {
                if ( hObject != (HANDLE)-1LL )
                  CloseHandle(hObject);
                std::string::_Tidy_deallocate(v40);
                if ( Str_8[0] )
                {
                  std::_Destroy_range<std::allocator<std::tuple<long,unsigned short,std::string,bool>>>(
                    Str_8[0],
                    Str_8[1]);
                  std::_Deallocate<16>(Str_8[0], 8 * ((signed __int64)(v33 - (unsigned __int64)Str_8[0]) >> 3));
                  *(_OWORD *)Str_8 = 0;
                  v33 = 0;
                }
                MatchInDirectory = 0;
              }
              else
              {
                if ( hObject != (HANDLE)-1LL )
                  CloseHandle(hObject);
                std::string::_Tidy_deallocate(v40);
                if ( Str_8[0] )
                {
                  std::_Destroy_range<std::allocator<std::tuple<long,unsigned short,std::string,bool>>>(
                    Str_8[0],
                    Str_8[1]);
                  std::_Deallocate<16>(Str_8[0], 8 * ((signed __int64)(v33 - (unsigned __int64)Str_8[0]) >> 3));
                  *(_OWORD *)Str_8 = 0;
                  v33 = 0;
                }
                MatchInDirectory = -2147467259;
              }
              goto LABEL_63;
            }
            v45 = 0;
            if ( hObject != (HANDLE)-1LL )
              CloseHandle(hObject);
          }
          std::string::_Tidy_deallocate(v40);
        }
        if ( Str_8[0] )
        {
          std::_Destroy_range<std::allocator<std::tuple<long,unsigned short,std::string,bool>>>(Str_8[0], Str_8[1]);
          std::_Deallocate<16>(Str_8[0], 8 * ((signed __int64)(v33 - (unsigned __int64)Str_8[0]) >> 3));
          *(_OWORD *)Str_8 = 0;
          v33 = 0;
        }
        lambda_bda4da4880bc99110f64a199c4fd6a98_::operator()(v38);
        return 2147500037LL;
      }
    }
  }
  MatchInDirectory = -2147024882;
LABEL_63:
  lambda_bda4da4880bc99110f64a199c4fd6a98_::operator()(v38);
  return (unsigned int)MatchInDirectory;
}

```

## disassembly

```asm
0x180192fb0  mov     rax, rsp
0x180192fb3  push    rbp
0x180192fb4  push    rsi
0x180192fb5  push    rdi
0x180192fb6  push    r12
0x180192fb8  push    r13
0x180192fba  push    r14
0x180192fbc  push    r15
0x180192fbe  lea     rbp, [rax-198h]
0x180192fc5  sub     rsp, 260h
0x180192fcc  mov     [rbp+190h+var_1F0], 0FFFFFFFFFFFFFFFEh
0x180192fd4  mov     [rax+10h], rbx
0x180192fd8  mov     rax, cs:__security_cookie
0x180192fdf  xor     rax, rsp
0x180192fe2  mov     [rbp+190h+var_40], rax
0x180192fe9  mov     r15, r9
0x180192fec  mov     rsi, r8
0x180192fef  mov     r13b, dl
0x180192ff2  mov     rdi, rcx
0x180192ff5  mov     r12, [rbp+190h+Buffer]
0x180192ffc  xor     r14d, r14d
0x180192fff  test    rcx, rcx
0x180193002  jz      loc_18019373F
0x180193008  test    r12, r12
0x18019300b  jz      loc_18019373F
0x180193011  mov     [rbp+190h+lpFileName], r14
0x180193015  mov     [rsp+290h+Str], r14
0x18019301a  mov     [rsp+290h+var_218], r14
0x18019301f  lea     rax, [rbp+190h+lpFileName]
0x180193023  mov     [rbp+190h+var_208], rax
0x180193027  lea     rax, [rsp+290h+Str]
0x18019302c  mov     [rbp+190h+var_200], rax
0x180193030  lea     rax, [rsp+290h+var_218]
0x180193035  mov     [rbp+190h+var_1F8], rax
0x180193039  lea     rax, [rbp+190h+var_208]
0x18019303d  mov     [rbp+190h+var_1E8], rax
0x180193041  or      rax, 0FFFFFFFFFFFFFFFFh
0x180193045  inc     rax
0x180193048  cmp     [rcx+rax], r14b
0x18019304c  jnz     short loc_180193045
0x18019304e  lea     ebx, [rax+3]
0x180193051  mov     ecx, ebx; Count
0x180193053  mov     edx, 1; Size
0x180193058  call    cs:__imp_calloc
0x18019305f  nop     dword ptr [rax+rax+00h]
0x180193064  mov     [rbp+190h+lpFileName], rax
0x180193068  test    rax, rax
0x18019306b  jz      loc_1801937C1
0x180193071  mov     r9d, ebx
0x180193074  mov     rdx, rdi
0x180193077  mov     rcx, rax; void *
0x18019307a  call    CopyNString
0x18019307f  mov     r9d, ebx
0x180193082  lea     rdx, asc_1805E9E10; "\\*"
0x180193089  mov     rcx, [rbp+190h+lpFileName]; void *
0x18019308d  call    CatNString
0x180193092  mov     edx, 1; Size
0x180193097  mov     ebx, 208h
0x18019309c  mov     ecx, ebx; Count
0x18019309e  call    cs:__imp_calloc
0x1801930a5  nop     dword ptr [rax+rax+00h]
0x1801930aa  mov     [rsp+290h+Str], rax
0x1801930af  test    rax, rax
0x1801930b2  jz      loc_1801937C1
0x1801930b8  mov     edx, 2; Size
0x1801930bd  mov     ecx, ebx; Count
0x1801930bf  call    cs:__imp_calloc
0x1801930c6  nop     dword ptr [rax+rax+00h]
0x1801930cb  mov     [rsp+290h+var_218], rax
0x1801930d0  test    rax, rax
0x1801930d3  jz      loc_1801937C1
0x1801930d9  test    rsi, rsi
0x1801930dc  jz      short loc_18019311D
0x1801930de  mov     [rsp+290h+var_250], r14b
0x1801930e3  lea     rax, [rsp+290h+var_250]
0x1801930e8  mov     qword ptr [rsp+290h+dwFlagsAndAttributes], rax; bool *
0x1801930ed  mov     r9, r12; unsigned __int16 *
0x1801930f0  xor     r8d, r8d; bool
0x1801930f3  mov     rdx, rsi; char *
0x1801930f6  mov     rcx, rdi; char *
0x1801930f9  call    ?FindMatchInDirectory@@YAJPEBD0_NPEAGKPEA_N@Z; FindMatchInDirectory(char const *,char const *,bool,ushort *,ulong,bool *)
0x1801930fe  mov     ebx, eax
0x180193100  test    eax, eax
0x180193102  js      loc_1801937C6
0x180193108  cmp     [rsp+290h+var_250], r14b
0x18019310d  jnz     loc_1801937C6
0x180193113  mov     ebx, 8000000Bh
0x180193118  jmp     loc_1801937C6
0x18019311d  xorps   xmm0, xmm0
0x180193120  movdqu  xmmword ptr [rsp+290h+Str+8], xmm0
0x180193126  mov     [rsp+290h+var_230], r14
0x18019312b  xor     ecx, ecx
0x18019312d  mov     byte ptr [rsp+290h+var_228], cl
0x180193131  mov     ebx, r14d
0x180193134  lea     rcx, __ImageBase
0x18019313b  movsxd  r14, ebx
0x18019313e  mov     rdx, ds:rva ?g_ExpandDumpExt@@3PAPEADA[rcx+r14*8]; char *
0x180193146  mov     [rsp+290h+var_250], 0
0x18019314b  cmp     byte ptr [rdx], 2Eh ; '.'
0x18019314e  setz    r8b; bool
0x180193152  lea     rcx, [rsp+290h+var_250]
0x180193157  mov     qword ptr [rsp+290h+dwFlagsAndAttributes], rcx; bool *
0x18019315c  mov     r9, rax; unsigned __int16 *
0x18019315f  mov     rcx, rdi; char *
0x180193162  call    ?FindMatchInDirectory@@YAJPEBD0_NPEAGKPEA_N@Z; FindMatchInDirectory(char const *,char const *,bool,ushort *,ulong,bool *)
0x180193167  mov     esi, eax
0x180193169  test    eax, eax
0x18019316b  js      loc_18019376F
0x180193171  xor     esi, esi
0x180193173  cmp     [rsp+290h+var_250], sil
0x180193178  jz      loc_1801932E8
0x18019317e  mov     r9, [rsp+290h+var_218]
0x180193183  lea     r8, aLs; "%ls"
0x18019318a  mov     edx, 208h
0x18019318f  mov     rcx, [rsp+290h+Str]
0x180193194  call    PrintString
0x180193199  test    eax, eax
0x18019319b  jz      loc_1801932E8
0x1801931a1  mov     rcx, [rsp+290h+Str]; Str
0x1801931a6  call    ?GetFileName@@YAPEBDPEBD@Z; GetFileName(char const *)
0x1801931ab  mov     rcx, rax; char *
0x1801931ae  call    ?IsDummyTargetFileA@@YA_NPEBD@Z; IsDummyTargetFileA(char const *)
0x1801931b3  test    al, al
0x1801931b5  jz      loc_18019323F
0x1801931bb  mov     rdx, [rsp+290h+Str]
0x1801931c0  lea     rcx, [rbp+190h+var_1A8]
0x1801931c4  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801931c9  nop
0x1801931ca  mov     [rbp+190h+var_1E0], sil
0x1801931ce  xorps   xmm0, xmm0
0x1801931d1  movups  xmmword ptr [rbp+190h+var_1D8], xmm0
0x1801931d5  mov     rcx, [rax]
0x1801931d8  mov     qword ptr [rbp+190h+var_1D8], rcx
0x1801931dc  movups  xmm0, xmmword ptr [rax+8]
0x1801931e0  movups  xmmword ptr [rbp+190h+var_1D8+8], xmm0
0x1801931e4  movsd   xmm1, qword ptr [rax+18h]
0x1801931e9  movsd   [rbp+190h+var_1C0], xmm1
0x1801931ee  mov     [rax+10h], rsi
0x1801931f2  mov     qword ptr [rax+18h], 0Fh
0x1801931fa  mov     [rax], sil
0x1801931fd  lea     rcx, __ImageBase
0x180193204  movzx   eax, rva ?g_ExpandDumpExtPriorities@@3PAGA[rcx+r14*2]; ushort near * g_ExpandDumpExtPriorities ...
0x18019320d  mov     [rbp+190h+var_1B8], ax
0x180193211  xor     r14d, r14d
0x180193214  mov     [rbp+190h+var_1B0], r14d
0x180193218  lea     rdx, [rbp+190h+var_1E0]
0x18019321c  lea     rcx, [rsp+290h+Str+8]
0x180193221  call    ?push@?$priority_queue@V?$tuple@JGV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@std@@V?$vector@V?$tuple@JGV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@std@@V?$allocator@V?$tuple@JGV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@std@@@2@@2@U?$less@V?$tuple@JGV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@std@@@2@@std@@QEAAX$$QEAV?$tuple@JGV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@2@@Z; std::priority_queue<std::tuple<long,ushort,std::string,bool>>::push(std::tuple<long,ushort,std::string,bool> &&)
0x180193226  nop
0x180193227  lea     rcx, [rbp+190h+var_1D8]
0x18019322b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180193230  nop
0x180193231  lea     rcx, [rbp+190h+var_1A8]
0x180193235  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18019323a  jmp     loc_1801932EB
0x18019323f  test    r13b, r13b
0x180193242  jz      short loc_180193268
0x180193244  lea     rdx, Str2; ".run"
0x18019324b  lea     rcx, __ImageBase
0x180193252  mov     rcx, ds:rva ?g_ExpandDumpExt@@3PAPEADA[rcx+r14*8]; Str1
0x18019325a  call    strcmp_0
0x18019325f  test    eax, eax
0x180193261  mov     esi, 3
0x180193266  jz      short loc_18019326D
0x180193268  mov     esi, 2
0x18019326d  mov     rdx, [rsp+290h+Str]
0x180193272  lea     rcx, [rbp+190h+var_1A8]
0x180193276  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18019327b  nop
0x18019327c  xor     edx, edx
0x18019327e  mov     [rbp+190h+var_1E0], dl
0x180193281  xorps   xmm0, xmm0
0x180193284  movups  xmmword ptr [rbp+190h+var_1D8], xmm0
0x180193288  mov     rcx, [rax]
0x18019328b  mov     qword ptr [rbp+190h+var_1D8], rcx
0x18019328f  movups  xmm0, xmmword ptr [rax+8]
0x180193293  movups  xmmword ptr [rbp+190h+var_1D8+8], xmm0
0x180193297  movsd   xmm1, qword ptr [rax+18h]
0x18019329c  movsd   [rbp+190h+var_1C0], xmm1
0x1801932a1  mov     [rax+10h], rdx
0x1801932a5  mov     qword ptr [rax+18h], 0Fh
0x1801932ad  mov     [rax], dl
0x1801932af  lea     rax, __ImageBase
0x1801932b6  movzx   eax, rva ?g_ExpandDumpExtPriorities@@3PAGA[rax+r14*2]; ushort near * g_ExpandDumpExtPriorities ...
0x1801932bf  mov     [rbp+190h+var_1B8], ax
0x1801932c3  mov     [rbp+190h+var_1B0], esi
0x1801932c6  lea     rdx, [rbp+190h+var_1E0]
0x1801932ca  lea     rcx, [rsp+290h+Str+8]
0x1801932cf  call    ?push@?$priority_queue@V?$tuple@JGV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@std@@V?$vector@V?$tuple@JGV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@std@@V?$allocator@V?$tuple@JGV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@std@@@2@@2@U?$less@V?$tuple@JGV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@std@@@2@@std@@QEAAX$$QEAV?$tuple@JGV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@2@@Z; std::priority_queue<std::tuple<long,ushort,std::string,bool>>::push(std::tuple<long,ushort,std::string,bool> &&)
0x1801932d4  nop
0x1801932d5  lea     rcx, [rbp+190h+var_1D8]
0x1801932d9  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801932de  nop
0x1801932df  lea     rcx, [rbp+190h+var_1A8]
0x1801932e3  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1801932e8  xor     r14d, r14d
0x1801932eb  inc     ebx
0x1801932ed  cmp     ebx, 0Eh
0x1801932f0  jnb     short loc_1801932FC
0x1801932f2  mov     rax, [rsp+290h+var_218]
0x1801932f7  jmp     loc_180193134
0x1801932fc  test    r15, r15
0x1801932ff  jz      loc_1801934D3
0x180193305  xor     edx, edx; Val
0x180193307  mov     r8d, 140h; Size
0x18019330d  lea     rcx, [rbp+190h+FindFileData]; void *
0x180193311  call    memset
0x180193316  lea     rdx, [rbp+190h+FindFileData]; lpFindFileData
0x18019331a  mov     rcx, [rbp+190h+lpFileName]; lpFileName
0x18019331e  call    cs:__imp_FindFirstFileA
0x180193325  nop     dword ptr [rax+rax+00h]
0x18019332a  mov     rsi, rax
0x18019332d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180193331  jz      loc_1801934D3
0x180193337  mov     word ptr [rsp+290h+var_250], r14w
0x18019333d  lea     rax, [rsp+290h+var_250]
0x180193342  mov     qword ptr [rsp+290h+dwCreationDisposition], rax
0x180193347  mov     r9d, 2
0x18019334d  xor     r8d, r8d
0x180193350  lea     rdx, [rbp+190h+FindFileData.cFileName]
0x180193354  mov     ecx, r9d
0x180193357  mov     rax, r15
0x18019335a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18019335f  test    eax, eax
0x180193361  jz      loc_1801934A9
0x180193367  lea     rcx, [rbp+190h+FindFileData.cFileName]; char *
0x18019336b  call    ?IsDummyTargetFileA@@YA_NPEBD@Z; IsDummyTargetFileA(char const *)
0x180193370  mov     r9, rdi
0x180193373  lea     r8, aHsHs; "%hs\\%hs"
0x18019337a  mov     edx, 208h
0x18019337f  mov     rcx, [rsp+290h+Str]
0x180193384  test    al, al
0x180193386  lea     rax, [rbp+190h+FindFileData.cFileName]
0x18019338a  mov     qword ptr [rsp+290h+dwCreationDisposition], rax
0x18019338f  jz      short loc_18019340B
0x180193391  call    PrintString
0x180193396  test    eax, eax
0x180193398  jz      loc_1801934A9
0x18019339e  mov     rdx, [rsp+290h+Str]
0x1801933a3  lea     rcx, [rbp+190h+var_1A8]
0x1801933a7  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801933ac  nop
0x1801933ad  mov     [rbp+190h+var_1E0], 1
0x1801933b1  xorps   xmm0, xmm0
0x1801933b4  movups  xmmword ptr [rbp+190h+var_1D8], xmm0
0x1801933b8  mov     rcx, [rax]
0x1801933bb  mov     qword ptr [rbp+190h+var_1D8], rcx
0x1801933bf  movups  xmm0, xmmword ptr [rax+8]
0x1801933c3  movups  xmmword ptr [rbp+190h+var_1D8+8], xmm0
0x1801933c7  movsd   xmm1, qword ptr [rax+18h]
0x1801933cc  movsd   [rbp+190h+var_1C0], xmm1
0x1801933d1  mov     [rax+10h], r14
0x1801933d5  mov     qword ptr [rax+18h], 0Fh
0x1801933dd  mov     [rax], r14b
0x1801933e0  movzx   eax, word ptr [rsp+290h+var_250]
0x1801933e5  mov     [rbp+190h+var_1B8], ax
0x1801933e9  mov     [rbp+190h+var_1B0], r14d
0x1801933ed  lea     rdx, [rbp+190h+var_1E0]
0x1801933f1  lea     rcx, [rsp+290h+Str+8]
0x1801933f6  call    ?push@?$priority_queue@V?$tuple@JGV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@std@@V?$vector@V?$tuple@JGV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@std@@V?$allocator@V?$tuple@JGV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@std@@@2@@2@U?$less@V?$tuple@JGV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@std@@@2@@std@@QEAAX$$QEAV?$tuple@JGV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@2@@Z; std::priority_queue<std::tuple<long,ushort,std::string,bool>>::push(std::tuple<long,ushort,std::string,bool> &&)
0x1801933fb  nop
0x1801933fc  lea     rcx, [rbp+190h+var_1D8]
0x180193400  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180193405  nop
0x180193406  jmp     loc_1801934A0
0x18019340b  call    PrintString
0x180193410  test    eax, eax
0x180193412  jz      loc_1801934A9
0x180193418  mov     qword ptr [rsp+290h+dwCreationDisposition], r14
0x18019341d  xor     r9d, r9d
0x180193420  xor     r8d, r8d
0x180193423  lea     rdx, [rbp+190h+FindFileData.cFileName]
0x180193427  xor     ecx, ecx
0x180193429  mov     rax, r15
0x18019342c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180193431  neg     eax
0x180193433  sbb     ebx, ebx
0x180193435  neg     ebx
0x180193437  inc     ebx
0x180193439  mov     rdx, [rsp+290h+Str]
0x18019343e  lea     rcx, [rbp+190h+var_1A8]
0x180193442  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180193447  nop
0x180193448  mov     [rbp+190h+var_1E0], 1
0x18019344c  xorps   xmm0, xmm0
0x18019344f  movups  xmmword ptr [rbp+190h+var_1D8], xmm0
0x180193453  mov     rcx, [rax]
0x180193456  mov     qword ptr [rbp+190h+var_1D8], rcx
0x18019345a  movups  xmm0, xmmword ptr [rax+8]
0x18019345e  movups  xmmword ptr [rbp+190h+var_1D8+8], xmm0
0x180193462  movsd   xmm1, qword ptr [rax+18h]
0x180193467  movsd   [rbp+190h+var_1C0], xmm1
0x18019346c  mov     [rax+10h], r14
0x180193470  mov     qword ptr [rax+18h], 0Fh
0x180193478  mov     [rax], r14b
0x18019347b  movzx   eax, word ptr [rsp+290h+var_250]
0x180193480  mov     [rbp+190h+var_1B8], ax
0x180193484  mov     [rbp+190h+var_1B0], ebx
0x180193487  lea     rdx, [rbp+190h+var_1E0]
0x18019348b  lea     rcx, [rsp+290h+Str+8]
  ... truncated ...
```
