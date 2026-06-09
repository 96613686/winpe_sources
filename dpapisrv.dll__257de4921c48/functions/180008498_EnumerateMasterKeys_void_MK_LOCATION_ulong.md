# EnumerateMasterKeys(void *,_MK_LOCATION * *,ulong *)

- ea: `0x180008498`
- end: `0x180008a3e`
- name: `?EnumerateMasterKeys@@YAKPEAXPEAPEAU_MK_LOCATION@@PEAK@Z`
- size: `1446`
- prototype: `__int64 __fastcall(_DWORD *, struct _MK_LOCATION **, unsigned int *)`
- caller_count: `2`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008c3c`
- `0x180039d90`

## callees

- `0x1800063c0`
- `0x180006510`
- `0x180006c60`
- `0x180007f10`
- `0x180008498`
- `0x1800090e8`
- `0x1800095d0`
- `0x1800136f8`
- `0x180013f2c`
- `0x18001c0a4`
- `0x18001d810`
- `0x18001d850`
- `0x18001e1b4`
- `0x18003c62c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008663`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008882`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800088ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800089c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800089d9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008663`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180008882`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800088ca`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800089c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800089d9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800084f3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008736`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000875a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800084f3`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180008736`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000875a`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18000897e`
- `api-ms-win-core-heap-l2-1-0!LocalReAlloc` at `0x18000897e`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800086cb`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800086cb`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180008642`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180008642`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800086de`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800086de`

## string_xrefs

- `0x180008905`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysync.cpp`
- `0x1800089f8`: `onecore\ds\security\cryptoapi\secstor\dpapisvc\keysync.cpp`

## pseudocode

```c
__int64 __fastcall EnumerateMasterKeys(_DWORD *a1, struct _MK_LOCATION **a2, unsigned int *a3)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  int v6; // r12d
  unsigned int i; // edi
  void *v8; // rdx
  unsigned int v9; // eax
  void *v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r13
  size_t v13; // r15
  unsigned int v14; // eax
  HANDLE FirstFileW; // rsi
  void *v16; // rcx
  __int64 v17; // rbx
  char *v18; // rax
  unsigned int v19; // eax
  _DWORD *v20; // r8
  _DWORD *v22; // rax
  __int64 v23; // r9
  unsigned int v24; // [rsp+30h] [rbp-D0h] BYREF
  HLOCAL v25; // [rsp+38h] [rbp-C8h] BYREF
  void *Src; // [rsp+40h] [rbp-C0h] BYREF
  HLOCAL v27; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v28; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v29; // [rsp+54h] [rbp-ACh]
  void **p_Src; // [rsp+58h] [rbp-A8h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-A0h] BYREF
  char *v32; // [rsp+68h] [rbp-98h] BYREF
  HLOCAL *p_hMem; // [rsp+70h] [rbp-90h] BYREF
  HLOCAL *v34; // [rsp+78h] [rbp-88h] BYREF
  HLOCAL *v35; // [rsp+80h] [rbp-80h] BYREF
  struct _MK_LOCATION **v36; // [rsp+88h] [rbp-78h]
  unsigned int *v37; // [rsp+90h] [rbp-70h]
  _QWORD v38[3]; // [rsp+98h] [rbp-68h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR FileName[264]; // [rsp+300h] [rbp+200h] BYREF

  v37 = a3;
  v36 = a2;
  v28 = 0;
  hMem = 0;
  p_hMem = &hMem;
  v24 = 0;
  v25 = LocalAlloc(0, 0xF0u);
  v38[0] = &v25;
  v38[1] = &v24;
  if ( !v25 )
  {
    v5 = 14;
LABEL_55:
    ScopedSSFreeMK_LOCATION_Array::~ScopedSSFreeMK_LOCATION_Array((ScopedSSFreeMK_LOCATION_Array *)v38);
    ScopedSSFree::~ScopedSSFree((ScopedSSFree *)&p_hMem);
    return v5;
  }
  v4 = CPSGetSidHistory(a1, (void ***)&hMem, &v28);
  v5 = v4;
  if ( v4 )
  {
    DebugTraceError(v4, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysync.cpp", 678);
    goto LABEL_55;
  }
  v6 = 0;
  v29 = 10;
  for ( i = 0; i < v28; ++i )
  {
    Src = 0;
    p_Src = &Src;
    v6 = 0;
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    if ( i )
      v8 = (void *)*((_QWORD *)hMem + i);
    else
      v8 = 0;
    v9 = CPSGetUserStorageArea(a1, v8, 0, 0, (unsigned __int16 **)&Src);
    v5 = v9;
    if ( (v9 & 0xFFFFFFFC) != 0 || v9 == 1 )
    {
LABEL_31:
      v5 = 0;
      ScopedSSFree::~ScopedSSFree((ScopedSSFree *)&p_Src);
    }
    else
    {
      v10 = Src;
      if ( Src )
      {
        v11 = -1;
        do
          ++v11;
        while ( *((_WORD *)Src + v11) );
      }
      else
      {
        LODWORD(v11) = 0;
      }
      v12 = (unsigned int)(v11 + 1);
      if ( (unsigned __int64)(v12 + 2) > 0x104 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
        {
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            30,
            WPP_c230f57ad4ef3aae53613952fd7c9bd0_Traceguids,
            (unsigned int)(v11 + 3));
          v10 = Src;
        }
        if ( v10 )
        {
          v16 = v10;
LABEL_17:
          LocalFree(v16);
          continue;
        }
      }
      else
      {
        v13 = 2LL * (unsigned int)v11;
        memcpy_0(FileName, Src, v13);
        *(_DWORD *)&FileName[v13 / 2] = 42;
        if ( v13 + 2 >= 0x208 )
          _report_rangecheckfailure();
        FileName[v13 / 2 + 1] = 0;
        v14 = CPSImpersonateClient(a1);
        v5 = v14;
        if ( v14 )
        {
          v23 = 736;
LABEL_64:
          DebugTraceError(v14, "dwLastError", "onecore\\ds\\security\\cryptoapi\\secstor\\dpapisvc\\keysync.cpp", v23);
          ScopedSSFree::~ScopedSSFree((ScopedSSFree *)&p_Src);
          break;
        }
        v6 = 1;
        FirstFileW = FindFirstFileW(FileName, &FindFileData);
        if ( FirstFileW != (HANDLE)-1LL )
        {
          do
          {
            if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
            {
              v17 = -1;
              do
                ++v17;
              while ( FindFileData.cFileName[v17] );
              if ( (_DWORD)v17 == 36
                && FindFileData.cFileName[23] == 45
                && FindFileData.cFileName[8] == 45
                && FindFileData.cFileName[13] == 45
                && FindFileData.cFileName[18] == 45 )
              {
                v27 = LocalAlloc(0, 0x4Au);
                v35 = &v27;
                v18 = (char *)LocalAlloc(0, 2 * v12);
                v32 = v18;
                v34 = (HLOCAL *)&v32;
                if ( !v18 )
                  goto LABEL_47;
                if ( !v27 )
                {
                  LocalFree(v18);
LABEL_47:
                  v5 = 14;
                  if ( v27 )
                    LocalFree(v27);
                  if ( Src )
                    LocalFree(Src);
                  goto LABEL_51;
                }
                memcpy_0(v18, Src, v13);
                *(_WORD *)&v32[v13] = 0;
                memcpy_0(v27, FindFileData.cFileName, 0x48u);
                *((_WORD *)v27 + 36) = 0;
                v19 = v24 + 1;
                v24 = v19;
                if ( v19 > v29 )
                {
                  v29 += v29 >> 1;
                  v22 = LocalReAlloc(v25, 24LL * v29, 2u);
                  v20 = v22;
                  if ( !v22 )
                  {
                    v5 = 14;
                    ScopedSSFree::~ScopedSSFree((ScopedSSFree *)&v34);
                    ScopedSSFree::~ScopedSSFree((ScopedSSFree *)&v35);
                    ScopedSSFree::~ScopedSSFree((ScopedSSFree *)&p_Src);
                    goto LABEL_51;
                  }
                  v25 = v22;
                  v19 = v24;
                }
                else
                {
                  v20 = v25;
                }
                v20[6 * v19 - 2] = FindFileData.nFileSizeLow;
                *((_QWORD *)v25 + 3 * v24 - 2) = v27;
                *((_QWORD *)v25 + 3 * v24 - 3) = v32;
              }
            }
          }
          while ( FindNextFileW(FirstFileW, &FindFileData) );
          FindClose(FirstFileW);
          v14 = CPSRevertToSelf(a1);
          v5 = v14;
          if ( !v14 )
          {
            v6 = 0;
            goto LABEL_31;
          }
          v23 = 841;
          goto LABEL_64;
        }
        v16 = Src;
        if ( Src )
          goto LABEL_17;
      }
    }
  }
  std::_Sort_unchecked<_MK_LOCATION *,bool (*)(_MK_LOCATION,_MK_LOCATION)>(
    v25,
    (char *)v25 + 24 * v24,
    0xAAAAAAAAAAAAAAABuLL * ((24LL * v24) >> 3),
    &lessMK_LOCATION);
  if ( !v5 )
  {
    *v36 = (struct _MK_LOCATION *)v25;
    *v37 = v24;
    v25 = 0;
  }
  if ( v6 == 1 )
LABEL_51:
    CPSRevertToSelf(a1);
  ScopedSSFreeMK_LOCATION_Array::~ScopedSSFreeMK_LOCATION_Array((ScopedSSFreeMK_LOCATION_Array *)v38);
  if ( hMem )
    LocalFree(hMem);
  return v5;
}

```

## disassembly

```asm
0x180008498  mov     [rsp-8+arg_18], rbx
0x18000849d  push    rbp
0x18000849e  push    rsi
0x18000849f  push    rdi
0x1800084a0  push    r12
0x1800084a2  push    r13
0x1800084a4  push    r14
0x1800084a6  push    r15
0x1800084a8  lea     rbp, [rsp-420h]
0x1800084b0  sub     rsp, 520h
0x1800084b7  mov     rax, cs:__security_cookie
0x1800084be  xor     rax, rsp
0x1800084c1  mov     [rbp+450h+var_40], rax
0x1800084c8  mov     [rbp+450h+var_4C0], r8
0x1800084cc  mov     [rbp+450h+var_4C8], rdx
0x1800084d0  mov     r14, rcx
0x1800084d3  xor     esi, esi
0x1800084d5  mov     [rsp+550h+var_500], esi
0x1800084d9  mov     [rsp+550h+hMem], rsi
0x1800084de  lea     rax, [rsp+550h+hMem]
0x1800084e3  mov     [rsp+550h+var_4E0], rax
0x1800084e8  mov     [rsp+550h+var_520], esi
0x1800084ec  mov     edx, 0F0h; uBytes
0x1800084f1  xor     ecx, ecx; uFlags
0x1800084f3  call    cs:__imp_LocalAlloc
0x1800084fa  nop     dword ptr [rax+rax+00h]
0x1800084ff  mov     [rsp+550h+var_518], rax
0x180008504  lea     rcx, [rsp+550h+var_518]
0x180008509  mov     [rbp+450h+var_4B8], rcx
0x18000850d  lea     rcx, [rsp+550h+var_520]
0x180008512  mov     [rbp+450h+var_4B0], rcx
0x180008516  test    rax, rax
0x180008519  jz      loc_1800088F8
0x18000851f  lea     r8, [rsp+550h+var_500]; unsigned int *
0x180008524  lea     rdx, [rsp+550h+hMem]; void ***
0x180008529  mov     rcx, r14; void *
0x18000852c  call    ?CPSGetSidHistory@@YAKPEAXPEAPEAPEAXPEAK@Z; CPSGetSidHistory(void *,void * * *,ulong *)
0x180008531  mov     ebx, eax
0x180008533  test    eax, eax
0x180008535  jnz     loc_1800088FF
0x18000853b  mov     r12d, esi
0x18000853e  mov     [rsp+550h+var_4FC], 0Ah
0x180008546  mov     edi, esi
0x180008548  cmp     edi, [rsp+550h+var_500]
0x18000854c  jnb     loc_180008828
0x180008552  mov     [rsp+550h+Src], rsi
0x180008557  lea     rax, [rsp+550h+Src]
0x18000855c  mov     [rsp+550h+var_4F8], rax
0x180008561  mov     r12d, esi
0x180008564  xor     edx, edx; Val
0x180008566  mov     r8d, 250h; Size
0x18000856c  lea     rcx, [rbp+450h+FindFileData]; void *
0x180008570  call    memset_0
0x180008575  test    edi, edi
0x180008577  jz      loc_180008697
0x18000857d  mov     ecx, edi
0x18000857f  mov     rax, [rsp+550h+hMem]
0x180008584  mov     rdx, [rax+rcx*8]; void *
0x180008588  lea     rax, [rsp+550h+Src]
0x18000858d  mov     [rsp+550h+var_530], rax; unsigned __int16 **
0x180008592  xor     r9d, r9d; int
0x180008595  xor     r8d, r8d; int
0x180008598  mov     rcx, r14; void *
0x18000859b  call    ?CPSGetUserStorageArea@@YAKPEAX0HHPEAPEAG@Z; CPSGetUserStorageArea(void *,void *,int,int,ushort * *)
0x1800085a0  mov     ebx, eax
0x1800085a2  test    eax, 0FFFFFFFCh
0x1800085a7  jnz     loc_180008701
0x1800085ad  cmp     eax, 1
0x1800085b0  jz      loc_180008701
0x1800085b6  mov     rdx, [rsp+550h+Src]; Src
0x1800085bb  test    rdx, rdx
0x1800085be  jz      loc_18000869F
0x1800085c4  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800085c8  inc     rcx
0x1800085cb  cmp     [rdx+rcx*2], si
0x1800085cf  jnz     short loc_1800085C8
0x1800085d1  lea     eax, [rcx+1]
0x1800085d4  mov     r13d, eax
0x1800085d7  add     rax, 2
0x1800085db  cmp     rax, 104h
0x1800085e1  ja      loc_180008676
0x1800085e7  mov     eax, ecx
0x1800085e9  lea     r15, [rax+rax]
0x1800085ed  mov     r8, r15; Size
0x1800085f0  lea     rcx, [rbp+450h+FileName]; void *
0x1800085f7  call    memcpy_0
0x1800085fc  mov     dword ptr [rbp+r15+450h+FileName], 2Ah ; '*'
0x180008608  lea     rcx, [r15+2]
0x18000860c  cmp     rcx, 208h
0x180008613  jnb     loc_1800088F2
0x180008619  mov     [rbp+rcx+450h+FileName], si
0x180008621  mov     rcx, r14; void *
0x180008624  call    ?CPSImpersonateClient@@YAKPEAX@Z; CPSImpersonateClient(void *)
0x180008629  mov     ebx, eax
0x18000862b  test    eax, eax
0x18000862d  jnz     loc_1800089F2
0x180008633  lea     r12d, [rax+1]
0x180008637  lea     rdx, [rbp+450h+FindFileData]; lpFindFileData
0x18000863b  lea     rcx, [rbp+450h+FileName]; lpFileName
0x180008642  call    cs:__imp_FindFirstFileW
0x180008649  nop     dword ptr [rax+rax+00h]
0x18000864e  mov     rsi, rax
0x180008651  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008655  jnz     short loc_1800086A6
0x180008657  mov     rcx, [rsp+550h+Src]; hMem
0x18000865c  xor     esi, esi
0x18000865e  test    rcx, rcx
0x180008661  jz      short loc_18000866F
0x180008663  call    cs:__imp_LocalFree
0x18000866a  nop     dword ptr [rax+rax+00h]
0x18000866f  inc     edi
0x180008671  jmp     loc_180008548
0x180008676  lea     r8, WPP_GLOBAL_Control
0x18000867d  mov     rax, cs:WPP_GLOBAL_Control
0x180008684  cmp     rax, r8
0x180008687  jnz     loc_180008934
0x18000868d  test    rdx, rdx
0x180008690  jz      short loc_18000866F
0x180008692  mov     rcx, rdx
0x180008695  jmp     short loc_180008663
0x180008697  mov     rdx, rsi
0x18000869a  jmp     loc_180008588
0x18000869f  mov     ecx, esi
0x1800086a1  jmp     loc_1800085D1
0x1800086a6  test    byte ptr [rbp+450h+FindFileData.dwFileAttributes], 10h
0x1800086aa  jnz     short loc_1800086C4
0x1800086ac  lea     rcx, [rbp+450h+FindFileData.cFileName]
0x1800086b0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800086b4  xor     eax, eax
0x1800086b6  inc     rbx
0x1800086b9  cmp     [rcx+rbx*2], ax
0x1800086bd  jnz     short loc_1800086B6
0x1800086bf  cmp     ebx, 24h ; '$'
0x1800086c2  jz      short loc_180008712
0x1800086c4  lea     rdx, [rbp+450h+FindFileData]; lpFindFileData
0x1800086c8  mov     rcx, rsi; hFindFile
0x1800086cb  call    cs:__imp_FindNextFileW
0x1800086d2  nop     dword ptr [rax+rax+00h]
0x1800086d7  test    eax, eax
0x1800086d9  jnz     short loc_1800086A6
0x1800086db  mov     rcx, rsi; hFindFile
0x1800086de  call    cs:__imp_FindClose
0x1800086e5  nop     dword ptr [rax+rax+00h]
0x1800086ea  mov     rcx, r14; void *
0x1800086ed  call    ?CPSRevertToSelf@@YAKPEAX@Z; CPSRevertToSelf(void *)
0x1800086f2  mov     ebx, eax
0x1800086f4  xor     esi, esi
0x1800086f6  test    eax, eax
0x1800086f8  jnz     loc_1800089EA
0x1800086fe  mov     r12d, esi
0x180008701  mov     ebx, esi
0x180008703  lea     rcx, [rsp+550h+var_4F8]; this
0x180008708  call    ??1ScopedSSFree@@QEAA@XZ; ScopedSSFree::~ScopedSSFree(void)
0x18000870d  jmp     loc_18000866F
0x180008712  mov     ax, 2Dh ; '-'
0x180008716  cmp     [rbp+450h+FindFileData.cFileName+2Eh], ax
0x18000871a  jnz     short loc_1800086C4
0x18000871c  cmp     [rbp+450h+FindFileData.cFileName+10h], ax
0x180008720  jnz     short loc_1800086C4
0x180008722  cmp     [rbp+450h+FindFileData.cFileName+1Ah], ax
0x180008726  jnz     short loc_1800086C4
0x180008728  cmp     [rbp+450h+FindFileData.cFileName+24h], ax
0x18000872c  jnz     short loc_1800086C4
0x18000872e  lea     edx, [rbx+1]
0x180008731  add     rdx, rdx; uBytes
0x180008734  xor     ecx, ecx; uFlags
0x180008736  call    cs:__imp_LocalAlloc
0x18000873d  nop     dword ptr [rax+rax+00h]
0x180008742  mov     [rsp+550h+var_508], rax
0x180008747  lea     rax, [rsp+550h+var_508]
0x18000874c  mov     [rbp+450h+var_4D0], rax
0x180008750  lea     rdx, ds:0[r13*2]; uBytes
0x180008758  xor     ecx, ecx; uFlags
0x18000875a  call    cs:__imp_LocalAlloc
0x180008761  nop     dword ptr [rax+rax+00h]
0x180008766  mov     [rsp+550h+var_4E8], rax
0x18000876b  lea     rcx, [rsp+550h+var_4E8]
0x180008770  mov     [rsp+550h+var_4D8], rcx
0x180008775  xor     ecx, ecx
0x180008777  test    rax, rax
0x18000877a  jz      loc_1800088BB
0x180008780  cmp     [rsp+550h+var_508], rcx
0x180008785  mov     rcx, rax; void *
0x180008788  jz      loc_1800089C8
0x18000878e  mov     r8, r15; Size
0x180008791  mov     rdx, [rsp+550h+Src]; Src
0x180008796  call    memcpy_0
0x18000879b  xor     ecx, ecx
0x18000879d  mov     rax, [rsp+550h+var_4E8]
0x1800087a2  mov     [r15+rax], cx
0x1800087a7  mov     eax, ebx
0x1800087a9  lea     rbx, [rax+rax]
0x1800087ad  mov     r8, rbx; Size
0x1800087b0  lea     rdx, [rbp+450h+FindFileData.cFileName]; Src
0x1800087b4  mov     rcx, [rsp+550h+var_508]; void *
0x1800087b9  call    memcpy_0
0x1800087be  xor     ecx, ecx
0x1800087c0  mov     rax, [rsp+550h+var_508]
0x1800087c5  mov     [rbx+rax], cx
0x1800087c9  mov     eax, [rsp+550h+var_520]
0x1800087cd  inc     eax
0x1800087cf  mov     [rsp+550h+var_520], eax
0x1800087d3  mov     ecx, [rsp+550h+var_4FC]
0x1800087d7  cmp     eax, ecx
0x1800087d9  ja      loc_180008961
0x1800087df  mov     r8, [rsp+550h+var_518]
0x1800087e4  dec     eax
0x1800087e6  lea     rdx, [rax+rax*2]
0x1800087ea  mov     eax, [rbp+450h+FindFileData.nFileSizeLow]
0x1800087ed  mov     [r8+rdx*8+10h], eax
0x1800087f2  mov     eax, [rsp+550h+var_520]
0x1800087f6  dec     eax
0x1800087f8  lea     rdx, [rax+rax*2]
0x1800087fc  mov     rcx, [rsp+550h+var_518]
0x180008801  mov     rax, [rsp+550h+var_508]
0x180008806  mov     [rcx+rdx*8+8], rax
0x18000880b  mov     eax, [rsp+550h+var_520]
0x18000880f  dec     eax
0x180008811  lea     rdx, [rax+rax*2]
0x180008815  mov     rcx, [rsp+550h+var_518]
0x18000881a  mov     rax, [rsp+550h+var_4E8]
0x18000881f  mov     [rcx+rdx*8], rax
0x180008823  jmp     loc_1800086C4
0x180008828  mov     eax, [rsp+550h+var_520]
0x18000882c  lea     rcx, [rax+rax*2]
0x180008830  mov     rax, [rsp+550h+var_518]
0x180008835  lea     rdx, [rax+rcx*8]
0x180008839  mov     r8, rdx
0x18000883c  sub     r8, rax
0x18000883f  sar     r8, 3
0x180008843  mov     rcx, 0AAAAAAAAAAAAAAABh
0x18000884d  imul    r8, rcx
0x180008851  lea     r9, ?lessMK_LOCATION@@YA_NU_MK_LOCATION@@0@Z; lessMK_LOCATION(_MK_LOCATION,_MK_LOCATION)
0x180008858  mov     rcx, rax
0x18000885b  call    ??$_Sort_unchecked@PEAU_MK_LOCATION@@P6A_NU1@0@Z@std@@YAXPEAU_MK_LOCATION@@0_JP6A_NU1@2@Z@Z; std::_Sort_unchecked<_MK_LOCATION *,bool (*)(_MK_LOCATION,_MK_LOCATION)>(_MK_LOCATION *,_MK_LOCATION *,__int64,bool (*)(_MK_LOCATION,_MK_LOCATION))
0x180008860  test    ebx, ebx
0x180008862  jz      loc_180008A1D
0x180008868  cmp     r12d, 1
0x18000886c  jz      short loc_1800088E5
0x18000886e  lea     rcx, [rbp+450h+var_4B8]; this
0x180008872  call    ??1ScopedSSFreeMK_LOCATION_Array@@QEAA@XZ; ScopedSSFreeMK_LOCATION_Array::~ScopedSSFreeMK_LOCATION_Array(void)
0x180008877  nop
0x180008878  mov     rcx, [rsp+550h+hMem]; hMem
0x18000887d  test    rcx, rcx
0x180008880  jz      short loc_18000888E
0x180008882  call    cs:__imp_LocalFree
0x180008889  nop     dword ptr [rax+rax+00h]
0x18000888e  mov     eax, ebx
0x180008890  mov     rcx, [rbp+450h+var_40]
0x180008897  xor     rcx, rsp; StackCookie
0x18000889a  call    __security_check_cookie
0x18000889f  mov     rbx, [rsp+550h+arg_18]
0x1800088a7  add     rsp, 520h
0x1800088ae  pop     r15
0x1800088b0  pop     r14
0x1800088b2  pop     r13
0x1800088b4  pop     r12
0x1800088b6  pop     rdi
0x1800088b7  pop     rsi
0x1800088b8  pop     rbp
0x1800088b9  retn
0x1800088bb  mov     ebx, 0Eh
0x1800088c0  mov     rcx, [rsp+550h+var_508]; hMem
0x1800088c5  test    rcx, rcx
0x1800088c8  jz      short loc_1800088D7
0x1800088ca  call    cs:__imp_LocalFree
0x1800088d1  nop     dword ptr [rax+rax+00h]
0x1800088d6  nop
0x1800088d7  mov     rcx, [rsp+550h+Src]; hMem
0x1800088dc  test    rcx, rcx
0x1800088df  jnz     loc_1800089D9
0x1800088e5  mov     rcx, r14; void *
0x1800088e8  call    ?CPSRevertToSelf@@YAKPEAX@Z; CPSRevertToSelf(void *)
0x1800088ed  jmp     loc_18000886E
0x1800088f2  call    __report_rangecheckfailure
0x1800088f8  mov     ebx, 0Eh
0x1800088fd  jmp     short loc_18000891B
0x1800088ff  mov     r9d, 2A6h
0x180008905  lea     r8, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\secst"...
0x18000890c  lea     rdx, aDwlasterror; "dwLastError"
0x180008913  mov     ecx, eax
0x180008915  call    DebugTraceError
0x18000891a  nop
0x18000891b  lea     rcx, [rbp+450h+var_4B8]; this
0x18000891f  call    ??1ScopedSSFreeMK_LOCATION_Array@@QEAA@XZ; ScopedSSFreeMK_LOCATION_Array::~ScopedSSFreeMK_LOCATION_Array(void)
0x180008924  nop
0x180008925  lea     rcx, [rsp+550h+var_4E0]; this
0x18000892a  call    ??1ScopedSSFree@@QEAA@XZ; ScopedSSFree::~ScopedSSFree(void)
0x18000892f  jmp     loc_18000888E
0x180008934  test    byte ptr [rax+1Ch], 2
0x180008938  jz      loc_18000868D
0x18000893e  lea     r9d, [rcx+3]
0x180008942  mov     edx, 1Eh
0x180008947  lea     r8, WPP_c230f57ad4ef3aae53613952fd7c9bd0_Traceguids
0x18000894e  mov     rcx, [rax+10h]
0x180008952  call    WPP_SF_d
0x180008957  mov     rdx, [rsp+550h+Src]
0x18000895c  jmp     loc_18000868D
0x180008961  mov     eax, ecx
0x180008963  shr     eax, 1
  ... truncated ...
```
