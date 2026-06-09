# ChooseInformationTypes(CInfoType *,CSiteMap *,HWND__ *,CHtmlHelpControl *)

- ea: `0x18002f6d8`
- end: `0x18002fb23`
- name: `?ChooseInformationTypes@@YAHPEAVCInfoType@@PEAVCSiteMap@@PEAUHWND__@@PEAVCHtmlHelpControl@@@Z`
- size: `1099`
- prototype: `__int64 __fastcall(struct CInfoType *, struct CSiteMap *, HWND, struct CHtmlHelpControl *)`
- caller_count: `3`
- callee_count: `20`
- tags: `installer_update`

## callers

- `0x18001a608`
- `0x18001b530`
- `0x180070230`

## callees

- `0x180001728`
- `0x180003fc0`
- `0x180011e94`
- `0x180012934`
- `0x180013670`
- `0x1800136f8`
- `0x18001393c`
- `0x18001f84c`
- `0x18001f8e4`
- `0x18001f96c`
- `0x18001fc7c`
- `0x18002ead8`
- `0x18002f6d8`
- `0x18002ff70`
- `0x1800305b4`
- `0x18003065c`
- `0x180042d00`
- `0x180075c42`
- `0x180075c5a`
- `0x180075d50`

## import_xrefs

- `msvcrt!_msize` at `0x18002f73b`
- `msvcrt!_msize` at `0x18002f756`
- `msvcrt!_msize` at `0x18002f773`
- `msvcrt!_msize` at `0x18002f78d`
- `msvcrt!_msize` at `0x18002facb`
- `msvcrt!_msize` at `0x18002f73b`
- `msvcrt!_msize` at `0x18002f756`
- `msvcrt!_msize` at `0x18002f773`
- `msvcrt!_msize` at `0x18002f78d`
- `msvcrt!_msize` at `0x18002facb`
- `msvcrt!realloc` at `0x18002f919`
- `msvcrt!realloc` at `0x18002f919`
- `msvcrt!malloc` at `0x18002f722`
- `msvcrt!malloc` at `0x18002f722`
- `msvcrt!free` at `0x18002f99b`
- `msvcrt!free` at `0x18002fafd`
- `msvcrt!free` at `0x18002f99b`
- `msvcrt!free` at `0x18002fafd`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ChooseInformationTypes(
        struct CInfoType *a1,
        struct CSiteMap *a2,
        HWND a3,
        struct CHtmlHelpControl *a4)
{
  __int64 v8; // rax
  _QWORD *v9; // rsi
  int v10; // r14d
  int v11; // eax
  void *v12; // rbx
  size_t v13; // rax
  const void *v14; // rdx
  void *v15; // rbx
  int v16; // eax
  size_t v17; // rax
  const char *v18; // rdx
  unsigned int v19; // r8d
  __int64 v20; // rax
  int v21; // edx
  unsigned int v22; // r8d
  __int64 v23; // rax
  int v24; // r15d
  int v25; // ebx
  int v26; // r13d
  __int64 v27; // rax
  int FirstCategoryType; // r10d
  int v29; // r10d
  _QWORD *v30; // rax
  CInfoTypePageContents *v31; // rax
  struct CHtmlHelpControl *v32; // rdx
  CInfoTypePageContents *v33; // rcx
  __int64 v34; // rdx
  __int64 v36; // rax
  CInfoTypePageContents *v37; // rax
  struct CHtmlHelpControl *v38; // rdx
  CInfoTypePageContents *v39; // rax
  __int64 i; // rbx
  int v41; // ebx
  void *v42; // rbx
  size_t v43; // rax
  void *v44[2]; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v45[2]; // [rsp+30h] [rbp-D0h] BYREF
  void *Src; // [rsp+40h] [rbp-C0h]
  __int64 v47; // [rsp+48h] [rbp-B8h]
  __m128i si128; // [rsp+50h] [rbp-B0h]
  int v49; // [rsp+60h] [rbp-A0h]
  _BYTE v50[12]; // [rsp+64h] [rbp-9Ch] BYREF
  int v51; // [rsp+70h] [rbp-90h]
  __int64 v52; // [rsp+74h] [rbp-8Ch]
  int v53; // [rsp+7Ch] [rbp-84h]
  CInfoTypePageContents *v54; // [rsp+80h] [rbp-80h]
  _BYTE v55[56]; // [rsp+90h] [rbp-70h] BYREF
  void *Block; // [rsp+C8h] [rbp-38h]
  _QWORD v57[290]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v58[298]; // [rsp+A10h] [rbp+910h] BYREF
  void *v59; // [rsp+1370h] [rbp+1270h] BYREF

  v8 = *((_QWORD *)a1 + 1);
  if ( !v8 )
    return 0;
  if ( *(_DWORD *)(v8 + 32) == 1 )
    return 0;
  v9 = malloc(0x58u);
  if ( !v9 )
    return 0;
  v10 = 0;
  v11 = _msize(*((void **)a1 + 10));
  CMem::CMem((CMem *)v44, v11);
  v12 = (void *)*((_QWORD *)a1 + 10);
  v13 = _msize(v12);
  v14 = v12;
  v15 = v44[0];
  memcpy_0(v44[0], v14, v13);
  v16 = _msize(*((void **)a1 + 10));
  CMem::CMem((CMem *)&v59, v16);
  v17 = _msize(*((void **)a1 + 10));
  memset_0(v59, 0, v17);
  memset(v50, 0, sizeof(v50));
  v53 = 0;
  v20 = *((_QWORD *)a1 + 11);
  if ( !v20 )
    v20 = *((_QWORD *)a1 + 10);
  v47 = v20;
  Src = v15;
  v45[1] = a2;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v49 = -1;
  v51 = 0;
  v52 = 1;
  v45[0] = a1;
  CPropSheet::CPropSheet((CPropSheet *)v55, v18, v19, a3);
  CPropPage::CPropPage((CPropPage *)v58, 116);
  v58[0] = &CWizardIntro::`vftable';
  v58[287] = v45;
  CPropPage::CPropPage((CPropPage *)v57, 117);
  v57[0] = &CInfoWizFinish::`vftable';
  v57[287] = v45;
  v23 = *((_QWORD *)a1 + 3);
  v24 = 1;
  if ( v23 && *(_DWORD *)(v23 + 32) - 1 > 0 )
  {
    v25 = 0;
    v26 = 11;
    while ( 1 )
    {
      v27 = *((_QWORD *)a1 + 3);
      if ( v27 )
        LODWORD(v27) = *(_DWORD *)(v27 + 32) - 1;
      if ( v25 >= (int)v27 )
        break;
      v49 = v25;
      *(_QWORD *)&v50[4] = *(_QWORD *)(*((_QWORD *)a1 + 9) + 16LL * v25 + 8);
      FirstCategoryType = CInfoType::GetFirstCategoryType(a1, v25);
      if ( FirstCategoryType != -1 )
      {
        while ( FirstCategoryType != -1 )
        {
          v24 = (unsigned int)CInfoType::IsHidden(a1, FirstCategoryType) != 0 ? v24 : 0;
          if ( (unsigned int)CInfoType::IsExclusive(a1, v29) )
          {
            si128.m128i_i64[0] = 0x100000077LL;
            break;
          }
          FirstCategoryType = CInfoType::GetNextITinCategory(a1);
        }
        if ( !v24 )
        {
          if ( v10 >= v26 )
          {
            v26 += 10;
            v30 = realloc(v9, 8LL * v26);
            if ( !v30 )
              goto LABEL_28;
            v9 = v30;
          }
          v31 = (CInfoTypePageContents *)operator new(0x950u);
          v54 = v31;
          if ( v31 )
            v33 = CInfoTypePageContents::CInfoTypePageContents(v31, v32, (struct INFO_PARAM *)v45);
          else
            v33 = 0;
          v9[v10] = v33;
          if ( !v33 )
          {
LABEL_28:
            v34 = (unsigned int)v10;
            goto LABEL_29;
          }
          ++v10;
        }
        si128.m128i_i64[0] = 118;
      }
      v24 = 1;
      ++v25;
    }
  }
  else
  {
    v36 = *((_QWORD *)a1 + 1);
    if ( v36 && *(_DWORD *)(v36 + 32) - 1 > 0 )
    {
      v49 = -1;
      si128.m128i_i32[2] = 117;
      if ( (unsigned int)CInfoType::GetFirstExclusive(a1, v21, v22) == -1 )
      {
        *(_QWORD *)&v50[4] = 0;
      }
      else
      {
        si128.m128i_i64[0] = 0x100000077LL;
        *(_QWORD *)&v50[4] = *((_QWORD *)a1 + 6);
      }
      v37 = (CInfoTypePageContents *)operator new(0x950u);
      v54 = v37;
      if ( v37 )
        v39 = CInfoTypePageContents::CInfoTypePageContents(v37, v38, (struct INFO_PARAM *)v45);
      else
        v39 = 0;
      *v9 = v39;
      if ( !v39 )
      {
        v34 = 0;
LABEL_29:
        FreeWizardPages(v9, v34);
        goto LABEL_30;
      }
      v10 = 1;
    }
  }
  CPropSheet::AddPage((CPropSheet *)v55, (struct CPropPage *)v58);
  for ( i = 0; (int)i < v10; i = (unsigned int)(i + 1) )
    CPropSheet::AddPage((CPropSheet *)v55, (struct CPropPage *)v9[i]);
  CPropSheet::AddPage((CPropSheet *)v55, (struct CPropPage *)v57);
  if ( a4 )
    COleControl::ModalDialog(a4, 1);
  v41 = CPropSheet::DoModal((CPropSheet *)v55);
  if ( a4 )
    COleControl::ModalDialog(a4, 0);
  FreeWizardPages(v9, (unsigned int)v10);
  if ( v41 <= 0 )
  {
LABEL_30:
    CDlg::~CDlg((CDlg *)v57);
    CDlg::~CDlg((CDlg *)v58);
    free(Block);
    CWStr::~CWStr((CWStr *)&v59);
    CWStr::~CWStr((CWStr *)v44);
    return 0;
  }
  v42 = (void *)*((_QWORD *)a1 + 10);
  v43 = _msize(v42);
  memcpy_0(v42, Src, v43);
  CDlg::~CDlg((CDlg *)v57);
  CDlg::~CDlg((CDlg *)v58);
  free(Block);
  CWStr::~CWStr((CWStr *)&v59);
  CWStr::~CWStr((CWStr *)v44);
  return 1;
}

```

## disassembly

```asm
0x18002f6d8  push    rbp
0x18002f6da  push    rbx
0x18002f6db  push    rsi
0x18002f6dc  push    rdi
0x18002f6dd  push    r12
0x18002f6df  push    r13
0x18002f6e1  push    r14
0x18002f6e3  push    r15
0x18002f6e5  lea     rbp, [rsp-1228h]
0x18002f6ed  mov     eax, 1328h
0x18002f6f2  call    _alloca_probe
0x18002f6f7  sub     rsp, rax
0x18002f6fa  mov     r12, r9
0x18002f6fd  mov     r15, r8
0x18002f700  mov     r13, rdx
0x18002f703  mov     rdi, rcx
0x18002f706  mov     rax, [rcx+8]
0x18002f70a  test    rax, rax
0x18002f70d  jz      loc_18002F9B9
0x18002f713  cmp     dword ptr [rax+20h], 1
0x18002f717  jz      loc_18002F9B9
0x18002f71d  mov     ecx, 58h ; 'X'; Size
0x18002f722  call    cs:__imp_malloc
0x18002f728  mov     rsi, rax
0x18002f72b  test    rax, rax
0x18002f72e  jz      loc_18002F9B9
0x18002f734  xor     r14d, r14d
0x18002f737  mov     rcx, [rdi+50h]; Block
0x18002f73b  call    cs:__imp__msize
0x18002f741  mov     rdx, rax; int
0x18002f744  lea     rcx, [rsp+1360h+var_1340]; this
0x18002f749  call    ??0CMem@@QEAA@H@Z; CMem::CMem(int)
0x18002f74e  nop
0x18002f74f  mov     rbx, [rdi+50h]
0x18002f753  mov     rcx, rbx; Block
0x18002f756  call    cs:__imp__msize
0x18002f75c  mov     r8, rax; Size
0x18002f75f  mov     rdx, rbx; Src
0x18002f762  mov     rbx, [rsp+1360h+var_1340]
0x18002f767  mov     rcx, rbx; void *
0x18002f76a  call    memcpy_0
0x18002f76f  mov     rcx, [rdi+50h]; Block
0x18002f773  call    cs:__imp__msize
0x18002f779  mov     rdx, rax; int
0x18002f77c  lea     rcx, [rbp+1260h+arg_0]; this
0x18002f783  call    ??0CMem@@QEAA@H@Z; CMem::CMem(int)
0x18002f788  nop
0x18002f789  mov     rcx, [rdi+50h]; Block
0x18002f78d  call    cs:__imp__msize
0x18002f793  mov     r8, rax; Size
0x18002f796  xor     edx, edx; Val
0x18002f798  mov     rcx, [rbp+1260h+arg_0]; void *
0x18002f79f  call    memset_0
0x18002f7a4  xor     ecx, ecx
0x18002f7a6  mov     [rsp+1360h+var_12FC], rcx
0x18002f7ab  mov     [rsp+1360h+var_12F4], ecx
0x18002f7af  mov     [rsp+1360h+var_12E4], ecx
0x18002f7b3  mov     rax, [rdi+58h]
0x18002f7b7  test    rax, rax
0x18002f7ba  jnz     short loc_18002F7C0
0x18002f7bc  mov     rax, [rdi+50h]
0x18002f7c0  mov     [rsp+1360h+var_1318], rax
0x18002f7c5  mov     [rsp+1360h+Src], rbx
0x18002f7ca  mov     [rsp+1360h+var_1328], r13
0x18002f7cf  movdqa  xmm0, cs:__xmm@00000000000000000000000000000076
0x18002f7d7  movdqa  [rsp+1360h+var_1310], xmm0
0x18002f7dd  or      ebx, 0FFFFFFFFh
0x18002f7e0  mov     [rsp+1360h+var_1300], ebx
0x18002f7e4  mov     [rsp+1360h+var_12F0], ecx
0x18002f7e8  mov     [rsp+1360h+var_12EC], 1
0x18002f7f1  mov     [rsp+1360h+var_1330], rdi
0x18002f7f6  mov     r9, r15; HWND
0x18002f7f9  lea     rcx, [rbp+1260h+var_12D0]; this
0x18002f7fd  call    ??0CPropSheet@@QEAA@PEBDKPEAUHWND__@@@Z; CPropSheet::CPropSheet(char const *,ulong,HWND__ *)
0x18002f802  nop
0x18002f803  lea     edx, [rbx+75h]; int
0x18002f806  lea     rcx, [rbp+1260h+var_950]; this
0x18002f80d  call    ??0CPropPage@@QEAA@H@Z; CPropPage::CPropPage(int)
0x18002f812  lea     rax, ??_7CWizardIntro@@6B@; const CWizardIntro::`vftable'
0x18002f819  mov     [rbp+1260h+var_950], rax
0x18002f820  lea     rax, [rsp+1360h+var_1330]
0x18002f825  mov     [rbp+1260h+var_58], rax
0x18002f82c  lea     r13d, [rbx+76h]
0x18002f830  mov     edx, r13d; int
0x18002f833  lea     rcx, [rbp+1260h+var_1260]; this
0x18002f837  call    ??0CPropPage@@QEAA@H@Z; CPropPage::CPropPage(int)
0x18002f83c  lea     rax, ??_7CInfoWizFinish@@6B@; const CInfoWizFinish::`vftable'
0x18002f843  mov     [rbp+1260h+var_1260], rax
0x18002f847  lea     rax, [rsp+1360h+var_1330]
0x18002f84c  mov     [rbp+1260h+var_968], rax
0x18002f853  mov     rax, [rdi+18h]
0x18002f857  lea     r15d, [rbx+2]
0x18002f85b  test    rax, rax
0x18002f85e  jz      loc_18002F9CF
0x18002f864  mov     eax, [rax+20h]
0x18002f867  sub     eax, r15d
0x18002f86a  test    eax, eax
0x18002f86c  jle     loc_18002F9CF
0x18002f872  xor     ebx, ebx
0x18002f874  lea     r13d, [r15+0Ah]
0x18002f878  mov     rax, [rdi+18h]
0x18002f87c  test    rax, rax
0x18002f87f  jz      short loc_18002F887
0x18002f881  mov     eax, [rax+20h]
0x18002f884  sub     eax, r15d
0x18002f887  cmp     ebx, eax
0x18002f889  jge     loc_18002FA4E
0x18002f88f  mov     [rsp+1360h+var_1300], ebx
0x18002f893  movsxd  rcx, ebx
0x18002f896  add     rcx, rcx
0x18002f899  mov     rax, [rdi+48h]
0x18002f89d  mov     rcx, [rax+rcx*8+8]
0x18002f8a2  mov     [rsp+1360h+var_12FC+4], rcx
0x18002f8a7  mov     edx, ebx; int
0x18002f8a9  mov     rcx, rdi; this
0x18002f8ac  call    ?GetFirstCategoryType@CInfoType@@QEBAHH@Z; CInfoType::GetFirstCategoryType(int)
0x18002f8b1  mov     r10d, eax
0x18002f8b4  cmp     eax, 0FFFFFFFFh
0x18002f8b7  jz      loc_18002F966
0x18002f8bd  cmp     r10d, 0FFFFFFFFh
0x18002f8c1  jz      short loc_18002F901
0x18002f8c3  mov     edx, r10d; int
0x18002f8c6  mov     rcx, rdi; this
0x18002f8c9  call    ?IsHidden@CInfoType@@QEBAHH@Z; CInfoType::IsHidden(int)
0x18002f8ce  neg     eax
0x18002f8d0  sbb     ecx, ecx
0x18002f8d2  and     r15d, ecx
0x18002f8d5  mov     edx, r10d; int
0x18002f8d8  mov     rcx, rdi; this
0x18002f8db  call    ?IsExclusive@CInfoType@@QEBAHH@Z; CInfoType::IsExclusive(int)
0x18002f8e0  test    eax, eax
0x18002f8e2  jnz     short loc_18002F8F1
0x18002f8e4  mov     rcx, rdi; this
0x18002f8e7  call    ?GetNextITinCategory@CInfoType@@QEBAHXZ; CInfoType::GetNextITinCategory(void)
0x18002f8ec  mov     r10d, eax
0x18002f8ef  jmp     short loc_18002F8BD
0x18002f8f1  mov     dword ptr [rsp+1360h+var_1310], 77h ; 'w'
0x18002f8f9  mov     dword ptr [rsp+1360h+var_1310+4], 1
0x18002f901  test    r15d, r15d
0x18002f904  jnz     short loc_18002F95D
0x18002f906  cmp     r14d, r13d
0x18002f909  jl      short loc_18002F927
0x18002f90b  add     r13d, 0Ah
0x18002f90f  movsxd  rdx, r13d
0x18002f912  shl     rdx, 3; Size
0x18002f916  mov     rcx, rsi; Block
0x18002f919  call    cs:__imp_realloc
0x18002f91f  test    rax, rax
0x18002f922  jz      short loc_18002F974
0x18002f924  mov     rsi, rax
0x18002f927  mov     ecx, 950h; Size
0x18002f92c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f931  mov     [rbp+1260h+var_12E0], rax
0x18002f935  test    rax, rax
0x18002f938  jz      short loc_18002F94C
0x18002f93a  lea     r8, [rsp+1360h+var_1330]; struct INFO_PARAM *
0x18002f93f  mov     rcx, rax; this
0x18002f942  call    ??0CInfoTypePageContents@@QEAA@PEAVCHtmlHelpControl@@PEAUINFO_PARAM@@@Z; CInfoTypePageContents::CInfoTypePageContents(CHtmlHelpControl *,INFO_PARAM *)
0x18002f947  mov     rcx, rax
0x18002f94a  jmp     short loc_18002F94E
0x18002f94c  xor     ecx, ecx
0x18002f94e  movsxd  rax, r14d
0x18002f951  mov     [rsi+rax*8], rcx
0x18002f955  test    rcx, rcx
0x18002f958  jz      short loc_18002F974
0x18002f95a  inc     r14d
0x18002f95d  mov     qword ptr [rsp+1360h+var_1310], 76h ; 'v'
0x18002f966  mov     r15d, 1
0x18002f96c  add     ebx, r15d
0x18002f96f  jmp     loc_18002F878
0x18002f974  mov     edx, r14d
0x18002f977  mov     rcx, rsi
0x18002f97a  call    FreeWizardPages
0x18002f97f  nop
0x18002f980  lea     rcx, [rbp+1260h+var_1260]; this
0x18002f984  call    ??1CDlg@@QEAA@XZ; CDlg::~CDlg(void)
0x18002f989  nop
0x18002f98a  lea     rcx, [rbp+1260h+var_950]; this
0x18002f991  call    ??1CDlg@@QEAA@XZ; CDlg::~CDlg(void)
0x18002f996  nop
0x18002f997  mov     rcx, [rbp+1260h+Block]; Block
0x18002f99b  call    cs:__imp_free
0x18002f9a1  nop
0x18002f9a2  lea     rcx, [rbp+1260h+arg_0]; this
0x18002f9a9  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x18002f9ae  nop
0x18002f9af  lea     rcx, [rsp+1360h+var_1340]; this
0x18002f9b4  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x18002f9b9  xor     eax, eax
0x18002f9bb  add     rsp, 1328h
0x18002f9c2  pop     r15
0x18002f9c4  pop     r14
0x18002f9c6  pop     r13
0x18002f9c8  pop     r12
0x18002f9ca  pop     rdi
0x18002f9cb  pop     rsi
0x18002f9cc  pop     rbx
0x18002f9cd  pop     rbp
0x18002f9ce  retn
0x18002f9cf  mov     rax, [rdi+8]
0x18002f9d3  test    rax, rax
0x18002f9d6  jz      short loc_18002FA4E
0x18002f9d8  mov     eax, [rax+20h]
0x18002f9db  sub     eax, r15d
0x18002f9de  test    eax, eax
0x18002f9e0  jle     short loc_18002FA4E
0x18002f9e2  mov     [rsp+1360h+var_1300], ebx
0x18002f9e6  mov     dword ptr [rsp+1360h+var_1310+8], r13d
0x18002f9eb  mov     rcx, rdi; this
0x18002f9ee  call    ?GetFirstExclusive@CInfoType@@QEBAHHI@Z; CInfoType::GetFirstExclusive(int,uint)
0x18002f9f3  mov     ecx, 950h; Size
0x18002f9f8  cmp     eax, ebx
0x18002f9fa  jz      short loc_18002FA14
0x18002f9fc  mov     dword ptr [rsp+1360h+var_1310], 77h ; 'w'
0x18002fa04  mov     dword ptr [rsp+1360h+var_1310+4], r15d
0x18002fa09  mov     rax, [rdi+30h]
0x18002fa0d  mov     [rsp+1360h+var_12FC+4], rax
0x18002fa12  jmp     short loc_18002FA1D
0x18002fa14  mov     [rsp+1360h+var_12FC+4], 0
0x18002fa1d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002fa22  test    rax, rax
0x18002fa25  mov     [rbp+1260h+var_12E0], rax
0x18002fa29  jz      short loc_18002FA3A
0x18002fa2b  lea     r8, [rsp+1360h+var_1330]; struct INFO_PARAM *
0x18002fa30  mov     rcx, rax; this
0x18002fa33  call    ??0CInfoTypePageContents@@QEAA@PEAVCHtmlHelpControl@@PEAUINFO_PARAM@@@Z; CInfoTypePageContents::CInfoTypePageContents(CHtmlHelpControl *,INFO_PARAM *)
0x18002fa38  jmp     short loc_18002FA3C
0x18002fa3a  xor     eax, eax
0x18002fa3c  mov     [rsi], rax
0x18002fa3f  test    rax, rax
0x18002fa42  jnz     short loc_18002FA4B
0x18002fa44  xor     edx, edx
0x18002fa46  jmp     loc_18002F977
0x18002fa4b  mov     r14d, r15d
0x18002fa4e  lea     rdx, [rbp+1260h+var_950]; struct CPropPage *
0x18002fa55  lea     rcx, [rbp+1260h+var_12D0]; this
0x18002fa59  call    ?AddPage@CPropSheet@@QEAAXPEAVCPropPage@@@Z; CPropSheet::AddPage(CPropPage *)
0x18002fa5e  xor     ebx, ebx
0x18002fa60  test    r14d, r14d
0x18002fa63  jle     short loc_18002FA7A
0x18002fa65  mov     rdx, [rsi+rbx*8]; struct CPropPage *
0x18002fa69  lea     rcx, [rbp+1260h+var_12D0]; this
0x18002fa6d  call    ?AddPage@CPropSheet@@QEAAXPEAVCPropPage@@@Z; CPropSheet::AddPage(CPropPage *)
0x18002fa72  add     ebx, r15d
0x18002fa75  cmp     ebx, r14d
0x18002fa78  jl      short loc_18002FA65
0x18002fa7a  lea     rdx, [rbp+1260h+var_1260]; struct CPropPage *
0x18002fa7e  lea     rcx, [rbp+1260h+var_12D0]; this
0x18002fa82  call    ?AddPage@CPropSheet@@QEAAXPEAVCPropPage@@@Z; CPropSheet::AddPage(CPropPage *)
0x18002fa87  test    r12, r12
0x18002fa8a  jz      short loc_18002FA97
0x18002fa8c  mov     edx, r15d; int
0x18002fa8f  mov     rcx, r12; this
0x18002fa92  call    ?ModalDialog@COleControl@@QEAAXH@Z; COleControl::ModalDialog(int)
0x18002fa97  lea     rcx, [rbp+1260h+var_12D0]; this
0x18002fa9b  call    ?DoModal@CPropSheet@@QEAAHXZ; CPropSheet::DoModal(void)
0x18002faa0  mov     ebx, eax
0x18002faa2  test    r12, r12
0x18002faa5  jz      short loc_18002FAB1
0x18002faa7  xor     edx, edx; int
0x18002faa9  mov     rcx, r12; this
0x18002faac  call    ?ModalDialog@COleControl@@QEAAXH@Z; COleControl::ModalDialog(int)
0x18002fab1  mov     edx, r14d
0x18002fab4  mov     rcx, rsi
0x18002fab7  call    FreeWizardPages
0x18002fabc  test    ebx, ebx
0x18002fabe  jle     loc_18002F980
0x18002fac4  mov     rbx, [rdi+50h]
0x18002fac8  mov     rcx, rbx; Block
0x18002facb  call    cs:__imp__msize
0x18002fad1  mov     r8, rax; Size
0x18002fad4  mov     rdx, [rsp+1360h+Src]; Src
0x18002fad9  mov     rcx, rbx; void *
0x18002fadc  call    memcpy_0
0x18002fae1  nop
0x18002fae2  lea     rcx, [rbp+1260h+var_1260]; this
0x18002fae6  call    ??1CDlg@@QEAA@XZ; CDlg::~CDlg(void)
0x18002faeb  nop
0x18002faec  lea     rcx, [rbp+1260h+var_950]; this
0x18002faf3  call    ??1CDlg@@QEAA@XZ; CDlg::~CDlg(void)
0x18002faf8  nop
0x18002faf9  mov     rcx, [rbp+1260h+Block]; Block
0x18002fafd  call    cs:__imp_free
0x18002fb03  nop
0x18002fb04  lea     rcx, [rbp+1260h+arg_0]; this
0x18002fb0b  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x18002fb10  nop
0x18002fb11  lea     rcx, [rsp+1360h+var_1340]; this
0x18002fb16  call    ??1CWStr@@QEAA@XZ; CWStr::~CWStr(void)
0x18002fb1b  mov     eax, r15d
0x18002fb1e  jmp     loc_18002F9BB
```
