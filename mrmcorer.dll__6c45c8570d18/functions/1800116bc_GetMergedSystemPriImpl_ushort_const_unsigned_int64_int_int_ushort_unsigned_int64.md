# GetMergedSystemPriImpl(ushort const *,unsigned __int64,int,int,ushort *,unsigned __int64 *)

- ea: `0x1800116bc`
- end: `0x180011a76`
- name: `?GetMergedSystemPriImpl@@YAJPEBG_KHHPEAGPEA_K@Z`
- size: `954`
- prototype: `int(const unsigned __int16 *, unsigned __int64, int, int, unsigned __int16 *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `19`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180010110`
- `0x18008f770`

## callees

- `0x1800116bc`
- `0x180011af4`
- `0x180012c78`
- `0x1800130e0`
- `0x1800157e8`
- `0x180016b00`
- `0x180017960`
- `0x18001d734`
- `0x18001f1b4`
- `0x18002c8d0`
- `0x18002cfd0`
- `0x180032980`
- `0x180034650`
- `0x180035110`
- `0x180035e8c`
- `0x180040c44`
- `0x180066c48`
- `0x18007e4a0`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800117ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800117ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800117fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800117fa`

## string_xrefs

- `0x180011921`: `onecoreuap\base\mrt\runtime\com\dllsrv\mrtwin32apis.cpp`
- `0x1800119be`: `onecoreuap\base\mrt\runtime\com\dllsrv\mrtwin32apis.cpp`
- `0x1800119f8`: `onecoreuap\base\mrt\runtime\com\dllsrv\mrtwin32apis.cpp`
- `0x180011a17`: `onecoreuap\base\mrt\runtime\com\dllsrv\mrtwin32apis.cpp`
- `0x1800c0af6`: `onecoreuap\base\mrt\runtime\com\dllsrv\mrtwin32apis.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall GetMergedSystemPriImpl(
        const unsigned __int16 *a1,
        unsigned __int64 a2,
        __int64 a3,
        int a4,
        unsigned __int16 *a5,
        unsigned __int64 *a6)
{
  int v9; // eax
  int AutoMergedFile; // ebx
  int v11; // eax
  int v12; // eax
  unsigned __int8 v13; // dl
  struct Microsoft::Resources::UnifiedResourceView *v14; // r14
  void *v15; // rbx
  HANDLE ProcessHeap; // rax
  const unsigned __int16 *v18; // rcx
  int v19; // edi
  const unsigned __int16 *v20; // r8
  int v21; // eax
  int v22; // edi
  void *v23; // rcx
  void *v24; // rcx
  unsigned __int64 v25; // r9
  __int64 v26; // rdx
  unsigned int v27; // ebx
  unsigned int v28; // edi
  unsigned int v29; // edx
  _DWORD *v30; // r9
  unsigned int v31; // edx
  _DWORD *v32; // r9
  LPVOID lpMem; // [rsp+38h] [rbp-71h] BYREF
  __int64 v34; // [rsp+40h] [rbp-69h]
  Microsoft::Resources::UnifiedResourceView::PriFileInfo *v35; // [rsp+48h] [rbp-61h] BYREF
  const int *v36; // [rsp+50h] [rbp-59h] BYREF
  struct Microsoft::Resources::UnifiedResourceView *v37; // [rsp+58h] [rbp-51h] BYREF
  __int64 *v38; // [rsp+60h] [rbp-49h] BYREF
  __int64 v39; // [rsp+68h] [rbp-41h] BYREF
  __int64 v40; // [rsp+70h] [rbp-39h]
  const unsigned __int16 *v41; // [rsp+78h] [rbp-31h]
  void **v42; // [rsp+80h] [rbp-29h] BYREF
  struct Microsoft::Resources::CoreProfile *v43; // [rsp+88h] [rbp-21h]
  _BYTE *v44; // [rsp+90h] [rbp-19h] BYREF
  _BYTE v45[88]; // [rsp+98h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+4Fh]

  v42 = &Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::MrmProfile>::`vftable';
  v43 = 0;
  v9 = Microsoft::Resources::MrmProfile::ChooseDefaultProfile(1, a2, 0, a1);
  AutoMergedFile = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x80,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\dllsrv\\mrtwin32apis.cpp",
      (const char *)(unsigned int)v9,
      0);
    goto LABEL_38;
  }
  v36 = &Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::UnifiedResourceView>::`vftable';
  v37 = 0;
  v11 = Microsoft::Resources::UnifiedResourceView::CreateInstance(v43, &v37);
  AutoMergedFile = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x83,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\dllsrv\\mrtwin32apis.cpp",
      (const char *)(unsigned int)v11,
      0);
    if ( v37 )
      (**(void (__fastcall ***)(struct Microsoft::Resources::UnifiedResourceView *, __int64))v37)(v37, 1);
    return (unsigned int)AutoMergedFile;
  }
  DefStringResult_InitBuf(&v39);
  v38 = &v39;
  if ( !v39 && (_DWORD)v40 || !(_DWORD)v40 && v39 )
  {
    v22 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x86,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\dllsrv\\mrtwin32apis.cpp",
      (const char *)0x80070057LL,
      0);
LABEL_37:
    Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v38);
    Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::UnifiedResourceView>::~AutoDeletePtr<Microsoft::Resources::UnifiedResourceView>(&v36);
    AutoMergedFile = v22;
LABEL_38:
    v42 = &Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::MrmProfile>::`vftable';
    Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Build::AutoMergeBehavior>::Release(&v42);
    return (unsigned int)AutoMergedFile;
  }
  v41 = a1;
  lpMem = 0;
  v34 = 0;
  v12 = Microsoft::Resources::DynamicArray<Microsoft::Resources::StringResult *>::Extend(&lpMem, 1, 0);
  AutoMergedFile = v12;
  if ( v12 < 0 )
  {
    v25 = (unsigned int)v12;
    v26 = 137;
    goto LABEL_57;
  }
  *((_QWORD *)lpMem + HIDWORD(v34)) = &v38;
  ++HIDWORD(v34);
  v13 = a4 != 0;
  v14 = v37;
  AutoMergedFile = Microsoft::Resources::UnifiedResourceView::LoadPriFiles(v37, v13, 0, &lpMem);
  if ( AutoMergedFile >= 0 )
  {
    DefStringResult_InitBuf(v45);
    v44 = v45;
    if ( MEMORY[0xC] )
    {
      AutoMergedFile = 0;
      if ( *MEMORY[0] )
      {
        AutoMergedFile = Microsoft::Resources::UnifiedResourceView::PriFileInfo::GetAutoMergedFile(
                           (Microsoft::Resources::UnifiedResourceView::PriFileInfo *)*MEMORY[0],
                           (struct Microsoft::Resources::StringResult *)&v44);
        if ( AutoMergedFile >= 0 )
        {
          if ( v44 && (*(_QWORD *)v44 || !*((_DWORD *)v44 + 2)) && (*((_DWORD *)v44 + 2) || !*(_QWORD *)v44) )
          {
            v18 = (const unsigned __int16 *)*((_QWORD *)v44 + 2);
            v19 = 0;
          }
          else
          {
            v18 = 0;
            v19 = -2147024809;
          }
          v20 = 0;
          if ( v19 >= 0 )
            v20 = v18;
          v21 = StringCchCopyW(a5, a2, v20);
          v22 = v21;
          if ( v21 >= 0 )
          {
            if ( a6 )
              AutoMergedFile = DefStringResult_GetLength(v44, a6);
            goto LABEL_27;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xA6,
            (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\dllsrv\\mrtwin32apis.cpp",
            (const char *)(unsigned int)v21,
            0);
          Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v44);
          v24 = 0;
          if ( MEMORY[0xC] )
          {
            v27 = 0;
            do
            {
              v35 = 0;
              Microsoft::Resources::DynamicArray<Microsoft::Resources::ManagedSchema *>::Get(v24, v27, &v35);
              if ( v35 )
              {
                Microsoft::Resources::UnifiedResourceView::PriFileInfo::`scalar deleting destructor'(v35, v29);
                v30 = 0;
              }
              ++v27;
              v24 = v30;
            }
            while ( v27 < v30[3] );
          }
          if ( v24 )
            Microsoft::Resources::DynamicArray<Microsoft::Resources::ManagedSchema *>::`scalar deleting destructor'(v24);
          Microsoft::Resources::DynamicArray<Microsoft::Resources::UnifiedResourceView::PriFileInfo *>::~DynamicArray<Microsoft::Resources::UnifiedResourceView::PriFileInfo *>(&lpMem);
          goto LABEL_37;
        }
      }
    }
    else
    {
      AutoMergedFile = -2147024809;
    }
LABEL_27:
    Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v44);
    v23 = 0;
    if ( MEMORY[0xC] )
    {
      v28 = 0;
      do
      {
        v35 = 0;
        Microsoft::Resources::DynamicArray<Microsoft::Resources::ManagedSchema *>::Get(v23, v28, &v35);
        if ( v35 )
        {
          Microsoft::Resources::UnifiedResourceView::PriFileInfo::`scalar deleting destructor'(v35, v31);
          v32 = 0;
        }
        ++v28;
        v23 = v32;
      }
      while ( v28 < v32[3] );
    }
    if ( v23 )
      Microsoft::Resources::DynamicArray<Microsoft::Resources::ManagedSchema *>::`scalar deleting destructor'(v23);
  }
  if ( AutoMergedFile < 0 )
  {
    if ( (unsigned int)(AutoMergedFile + 2147024894) <= 1 )
    {
LABEL_58:
      Microsoft::Resources::DynamicArray<Microsoft::Resources::UnifiedResourceView::PriFileInfo *>::~DynamicArray<Microsoft::Resources::UnifiedResourceView::PriFileInfo *>(&lpMem);
      Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)&v38);
      Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::UnifiedResourceView>::~AutoDeletePtr<Microsoft::Resources::UnifiedResourceView>(&v36);
      goto LABEL_38;
    }
    v25 = (unsigned int)AutoMergedFile;
    v26 = 182;
LABEL_57:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"onecoreuap\\base\\mrt\\runtime\\com\\dllsrv\\mrtwin32apis.cpp",
      (const char *)v25,
      0);
    goto LABEL_58;
  }
  v15 = lpMem;
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, v15);
  DefStringResult_Clear(&v39, 1);
  if ( v14 )
    (**(void (__fastcall ***)(struct Microsoft::Resources::UnifiedResourceView *, __int64))v14)(v14, 1);
  return 0;
}

```

## disassembly

```asm
0x1800116bc  push    rbp
0x1800116be  push    rbx
0x1800116bf  push    rsi
0x1800116c0  push    rdi
0x1800116c1  push    r12
0x1800116c3  push    r13
0x1800116c5  push    r14
0x1800116c7  push    r15
0x1800116c9  lea     rbp, [rsp-0Fh]
0x1800116ce  sub     rsp, 0B8h
0x1800116d5  mov     r14d, r9d
0x1800116d8  mov     r15, rdx
0x1800116db  mov     rdi, rcx
0x1800116de  lea     rax, ??_7?$AutoDeletePtr@VMrmProfile@Resources@Microsoft@@@Resources@Microsoft@@6B@; const Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::MrmProfile>::`vftable'
0x1800116e5  mov     [rbp+47h+var_70], rax
0x1800116e9  xor     r12d, r12d
0x1800116ec  mov     [rbp+47h+var_68], r12
0x1800116f0  lea     rax, [rbp+47h+var_68]
0x1800116f4  mov     [rsp+0F0h+var_C8], rax
0x1800116f9  mov     qword ptr [rsp+0F0h+var_D0], r12; int
0x1800116fe  mov     r9, rcx
0x180011701  xor     r8d, r8d
0x180011704  lea     r13d, [r12+1]
0x180011709  mov     ecx, r13d
0x18001170c  call    ?ChooseDefaultProfile@MrmProfile@Resources@Microsoft@@SAJW4ProfileType@123@W4_MrmPlatformVersionInternal@23@PEBG22PEAPEAV123@@Z; Microsoft::Resources::MrmProfile::ChooseDefaultProfile(Microsoft::Resources::MrmProfile::ProfileType,Microsoft::Resources::_MrmPlatformVersionInternal,ushort const *,ushort const *,ushort const *,Microsoft::Resources::MrmProfile * *)
0x180011711  mov     ebx, eax
0x180011713  test    eax, eax
0x180011715  js      loc_1800119F1
0x18001171b  lea     rax, ??_7?$AutoDeletePtr@VUnifiedResourceView@Resources@Microsoft@@@Resources@Microsoft@@6B@; const Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::UnifiedResourceView>::`vftable'
0x180011722  mov     [rbp+47h+var_A0], rax
0x180011726  mov     [rbp+47h+var_98], r12
0x18001172a  mov     rsi, [rbp+47h+var_68]
0x18001172e  lea     rdx, [rbp+47h+var_98]; struct Microsoft::Resources::UnifiedResourceView **
0x180011732  mov     rcx, rsi; struct Microsoft::Resources::CoreProfile *
0x180011735  call    ?CreateInstance@UnifiedResourceView@Resources@Microsoft@@SAJPEAVCoreProfile@23@PEAPEAV123@@Z; Microsoft::Resources::UnifiedResourceView::CreateInstance(Microsoft::Resources::CoreProfile *,Microsoft::Resources::UnifiedResourceView * *)
0x18001173a  mov     ebx, eax
0x18001173c  test    eax, eax
0x18001173e  js      loc_18001191A
0x180011744  lea     rcx, [rbp+47h+var_88]
0x180011748  call    DefStringResult_InitBuf
0x18001174d  lea     rcx, [rbp+47h+var_88]
0x180011751  mov     [rbp+47h+var_90], rcx
0x180011755  mov     rcx, [rbp+47h+var_88]
0x180011759  mov     rax, [rbp+47h+var_80]
0x18001175d  test    rcx, rcx
0x180011760  jnz     short loc_18001176A
0x180011762  test    eax, eax
0x180011764  jnz     loc_180011A0B
0x18001176a  test    eax, eax
0x18001176c  jnz     short loc_180011777
0x18001176e  test    rcx, rcx
0x180011771  jnz     loc_180011A0B
0x180011777  mov     [rbp+47h+var_78], rdi
0x18001177b  mov     [rbp+47h+lpMem], r12
0x18001177f  mov     [rbp+47h+var_B0], r12
0x180011783  xor     r8d, r8d
0x180011786  mov     edx, r13d
0x180011789  lea     rcx, [rbp+47h+lpMem]
0x18001178d  call    ?Extend@?$DynamicArray@PEAVStringResult@Resources@Microsoft@@@Resources@Microsoft@@IEAAJI_N@Z; Microsoft::Resources::DynamicArray<Microsoft::Resources::StringResult *>::Extend(uint,bool)
0x180011792  mov     ebx, eax
0x180011794  test    eax, eax
0x180011796  js      loc_180011A2D
0x18001179c  mov     ecx, dword ptr [rbp+47h+var_B0+4]
0x18001179f  lea     rdx, [rbp+47h+var_90]
0x1800117a3  mov     rax, [rbp+47h+lpMem]
0x1800117a7  mov     [rax+rcx*8], rdx
0x1800117ab  add     dword ptr [rbp+47h+var_B0+4], r13d
0x1800117af  mov     [rbp+47h+var_C0], r12
0x1800117b3  test    r14d, r14d
0x1800117b6  setnz   dl
0x1800117b9  lea     rax, [rbp+47h+var_C0]
0x1800117bd  mov     [rsp+0F0h+var_C8], rax
0x1800117c2  mov     [rsp+0F0h+var_D0], r12d; int
0x1800117c7  lea     r9, [rbp+47h+lpMem]
0x1800117cb  xor     r8d, r8d
0x1800117ce  mov     r14, [rbp+47h+var_98]
0x1800117d2  mov     rcx, r14
0x1800117d5  call    ?LoadPriFiles@UnifiedResourceView@Resources@Microsoft@@QEAAJ_NW4_MRMPROFILE_PHASE@23@PEAV?$DynamicArray@PEAVStringResult@Resources@Microsoft@@@23@W4LoadPriFlags@23@PEAPEAV?$DynamicArray@PEAVPriFileInfo@UnifiedResourceView@Resources@Microsoft@@@23@@Z; Microsoft::Resources::UnifiedResourceView::LoadPriFiles(bool,Microsoft::Resources::_MRMPROFILE_PHASE,Microsoft::Resources::DynamicArray<Microsoft::Resources::StringResult *> *,Microsoft::Resources::LoadPriFlags,Microsoft::Resources::DynamicArray<Microsoft::Resources::UnifiedResourceView::PriFileInfo *> * *)
0x1800117da  mov     ebx, eax
0x1800117dc  test    eax, eax
0x1800117de  jns     short loc_180011851
0x1800117e0  test    ebx, ebx
0x1800117e2  js      loc_180011A5A
0x1800117e8  mov     rbx, [rbp+47h+lpMem]
0x1800117ec  call    cs:__imp_GetProcessHeap
0x1800117f2  mov     r8, rbx; lpMem
0x1800117f5  xor     edx, edx; dwFlags
0x1800117f7  mov     rcx, rax; hHeap
0x1800117fa  call    cs:__imp_HeapFree
0x180011800  nop
0x180011801  mov     edx, r13d
0x180011804  lea     rcx, [rbp+47h+var_88]
0x180011808  call    DefStringResult_Clear
0x18001180d  nop
0x18001180e  test    r14, r14
0x180011811  jz      short loc_180011825
0x180011813  mov     rax, [r14]
0x180011816  mov     edx, r13d
0x180011819  mov     rcx, r14
0x18001181c  mov     rax, [rax]
0x18001181f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011824  nop
0x180011825  test    rsi, rsi
0x180011828  jz      short loc_18001183B
0x18001182a  mov     rax, [rsi]
0x18001182d  mov     edx, r13d
0x180011830  mov     rcx, rsi
0x180011833  mov     rax, [rax]
0x180011836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001183b  xor     eax, eax
0x18001183d  add     rsp, 0B8h
0x180011844  pop     r15
0x180011846  pop     r14
0x180011848  pop     r13
0x18001184a  pop     r12
0x18001184c  pop     rdi
0x18001184d  pop     rsi
0x18001184e  pop     rbx
0x18001184f  pop     rbp
0x180011850  retn
0x180011851  lea     rcx, [rbp+47h+var_58]
0x180011855  call    DefStringResult_InitBuf
0x18001185a  lea     rcx, [rbp+47h+var_58]
0x18001185e  mov     [rbp+47h+var_60], rcx
0x180011862  mov     rax, [rbp+47h+var_C0]
0x180011866  cmp     [rax+0Ch], r12d
0x18001186a  jbe     loc_180011913
0x180011870  mov     rax, [rax]
0x180011873  mov     rcx, [rax]; this
0x180011876  mov     ebx, r12d
0x180011879  test    rcx, rcx
0x18001187c  jz      short loc_1800118EB
0x18001187e  lea     rdx, [rbp+47h+var_60]; struct Microsoft::Resources::StringResult *
0x180011882  call    ?GetAutoMergedFile@PriFileInfo@UnifiedResourceView@Resources@Microsoft@@QEBAJPEAVStringResult@34@@Z; Microsoft::Resources::UnifiedResourceView::PriFileInfo::GetAutoMergedFile(Microsoft::Resources::StringResult *)
0x180011887  mov     ebx, eax
0x180011889  test    eax, eax
0x18001188b  js      short loc_1800118EB
0x18001188d  mov     rax, [rbp+47h+var_60]
0x180011891  test    rax, rax
0x180011894  jz      loc_18001196A
0x18001189a  cmp     [rax], r12
0x18001189d  jnz     short loc_1800118A9
0x18001189f  cmp     [rax+8], r12d
0x1800118a3  ja      loc_18001196A
0x1800118a9  cmp     [rax+8], r12d
0x1800118ad  jnz     short loc_1800118B8
0x1800118af  cmp     [rax], r12
0x1800118b2  jnz     loc_18001196A
0x1800118b8  mov     rcx, [rax+10h]
0x1800118bc  mov     edi, r12d
0x1800118bf  mov     r8, r12
0x1800118c2  test    edi, edi
0x1800118c4  cmovns  r8, rcx; unsigned __int16 *
0x1800118c8  mov     rdx, r15; unsigned __int64
0x1800118cb  mov     rcx, [rbp+47h+arg_20]; unsigned __int16 *
0x1800118cf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800118d4  mov     edi, eax
0x1800118d6  test    eax, eax
0x1800118d8  js      loc_1800119B7
0x1800118de  mov     rdx, [rbp+47h+arg_28]
0x1800118e2  test    rdx, rdx
0x1800118e5  jnz     loc_180011A42
0x1800118eb  lea     rcx, [rbp+47h+var_60]; this
0x1800118ef  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x1800118f4  mov     r9, [rbp+47h+var_C0]
0x1800118f8  mov     rcx, r9; lpMem
0x1800118fb  cmp     [r9+0Ch], r12d
0x1800118ff  ja      loc_180011A52
0x180011905  test    rcx, rcx
0x180011908  jnz     short loc_180011977
0x18001190a  mov     [rbp+47h+var_C0], r12
0x18001190e  jmp     loc_1800117E0
0x180011913  mov     ebx, 80070057h
0x180011918  jmp     short loc_1800118EB
0x18001191a  mov     rcx, [rbp+4Fh]; this
0x18001191e  mov     r9d, ebx; char *
0x180011921  lea     r8, aOnecoreuapBase_28; "onecoreuap\\base\\mrt\\runtime\\com\\dl"...
0x180011928  mov     edx, 83h; void *
0x18001192d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011932  nop
0x180011933  mov     rcx, [rbp+47h+var_98]
0x180011937  test    rcx, rcx
0x18001193a  jz      short loc_18001194B
0x18001193c  mov     rax, [rcx]
0x18001193f  mov     edx, r13d
0x180011942  mov     rax, [rax]
0x180011945  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001194a  nop
0x18001194b  test    rsi, rsi
0x18001194e  jnz     short loc_180011957
0x180011950  mov     eax, ebx
0x180011952  jmp     loc_18001183D
0x180011957  mov     rax, [rsi]
0x18001195a  mov     edx, r13d
0x18001195d  mov     rcx, rsi
0x180011960  mov     rax, [rax]
0x180011963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011968  jmp     short loc_180011950
0x18001196a  mov     rcx, r12
0x18001196d  mov     edi, 80070057h
0x180011972  jmp     loc_1800118BF
0x180011977  call    ??_G?$DynamicArray@PEAVManagedSchema@Resources@Microsoft@@@Resources@Microsoft@@QEAAPEAXI@Z; Microsoft::Resources::DynamicArray<Microsoft::Resources::ManagedSchema *>::`scalar deleting destructor'(uint)
0x18001197c  jmp     short loc_18001190A
0x18001197e  mov     [rbp+47h+var_C0], r12
0x180011982  lea     rcx, [rbp+47h+lpMem]
0x180011986  call    ??1?$DynamicArray@PEAVPriFileInfo@UnifiedResourceView@Resources@Microsoft@@@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::DynamicArray<Microsoft::Resources::UnifiedResourceView::PriFileInfo *>::~DynamicArray<Microsoft::Resources::UnifiedResourceView::PriFileInfo *>(void)
0x18001198b  nop
0x18001198c  lea     rcx, [rbp+47h+var_90]; this
0x180011990  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x180011995  nop
0x180011996  lea     rcx, [rbp+47h+var_A0]
0x18001199a  call    ??1?$AutoDeletePtr@VUnifiedResourceView@Resources@Microsoft@@@Resources@Microsoft@@UEAA@XZ; Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::UnifiedResourceView>::~AutoDeletePtr<Microsoft::Resources::UnifiedResourceView>(void)
0x18001199f  mov     ebx, edi
0x1800119a1  lea     rax, ??_7?$AutoDeletePtr@VMrmProfile@Resources@Microsoft@@@Resources@Microsoft@@6B@; const Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::MrmProfile>::`vftable'
0x1800119a8  mov     [rbp+47h+var_70], rax
0x1800119ac  lea     rcx, [rbp+47h+var_70]
0x1800119b0  call    ?Release@?$AutoDeletePtr@VAutoMergeBehavior@Build@Resources@Microsoft@@@Resources@Microsoft@@QEAAXXZ; Microsoft::Resources::AutoDeletePtr<Microsoft::Resources::Build::AutoMergeBehavior>::Release(void)
0x1800119b5  jmp     short loc_180011950
0x1800119b7  mov     rcx, [rbp+4Fh]; this
0x1800119bb  mov     r9d, edi; char *
0x1800119be  lea     r8, aOnecoreuapBase_28; "onecoreuap\\base\\mrt\\runtime\\com\\dl"...
0x1800119c5  mov     edx, 0A6h; void *
0x1800119ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800119cf  lea     rcx, [rbp+47h+var_60]; this
0x1800119d3  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x1800119d8  mov     r9, [rbp+47h+var_C0]
0x1800119dc  mov     rcx, r9; lpMem
0x1800119df  cmp     [r9+0Ch], r12d
0x1800119e3  ja      short loc_180011A3A
0x1800119e5  test    rcx, rcx
0x1800119e8  jz      short loc_18001197E
0x1800119ea  call    ??_G?$DynamicArray@PEAVManagedSchema@Resources@Microsoft@@@Resources@Microsoft@@QEAAPEAXI@Z; Microsoft::Resources::DynamicArray<Microsoft::Resources::ManagedSchema *>::`scalar deleting destructor'(uint)
0x1800119ef  jmp     short loc_18001197E
0x1800119f1  mov     rcx, [rbp+4Fh]; this
0x1800119f5  mov     r9d, eax; char *
0x1800119f8  lea     r8, aOnecoreuapBase_28; "onecoreuap\\base\\mrt\\runtime\\com\\dl"...
0x1800119ff  mov     edx, 80h; void *
0x180011a04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011a09  jmp     short loc_1800119A1
0x180011a0b  mov     rcx, [rbp+4Fh]; this
0x180011a0f  mov     edi, 80070057h
0x180011a14  mov     r9d, edi; char *
0x180011a17  lea     r8, aOnecoreuapBase_28; "onecoreuap\\base\\mrt\\runtime\\com\\dl"...
0x180011a1e  mov     edx, 86h; void *
0x180011a23  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011a28  jmp     loc_18001198C
0x180011a2d  mov     r9d, eax; char *
0x180011a30  mov     edx, 89h; void *
0x180011a35  jmp     loc_1800C0AF6
0x180011a3a  mov     ebx, r12d
0x180011a3d  jmp     loc_1800C0A92
0x180011a42  mov     rcx, [rbp+47h+var_60]
0x180011a46  call    DefStringResult_GetLength
0x180011a4b  mov     ebx, eax
0x180011a4d  jmp     loc_1800118EB
0x180011a52  mov     edi, r12d
0x180011a55  jmp     loc_1800C0AC4
0x180011a5a  lea     eax, [rbx+7FF8FFFEh]
0x180011a60  cmp     eax, r13d
0x180011a63  jbe     loc_1800C0B07
0x180011a69  mov     r9d, ebx
0x180011a6c  mov     edx, 0B6h
0x180011a71  jmp     loc_1800C0AF6
0x1800c0a92  mov     [rbp+47h+var_A8], r12
0x1800c0a96  lea     r8, [rbp+47h+var_A8]
0x1800c0a9a  mov     edx, ebx
0x1800c0a9c  call    ?Get@?$DynamicArray@PEAVManagedSchema@Resources@Microsoft@@@Resources@Microsoft@@QEBAJIPEAPEAVManagedSchema@23@@Z; Microsoft::Resources::DynamicArray<Microsoft::Resources::ManagedSchema *>::Get(uint,Microsoft::Resources::ManagedSchema * *)
0x1800c0aa1  mov     rcx, [rbp+47h+var_A8]; this
0x1800c0aa5  test    rcx, rcx
0x1800c0aa8  jz      short loc_1800C0AB3
0x1800c0aaa  call    ??_GPriFileInfo@UnifiedResourceView@Resources@Microsoft@@QEAAPEAXI@Z; Microsoft::Resources::UnifiedResourceView::PriFileInfo::`scalar deleting destructor'(uint)
0x1800c0aaf  mov     r9, [rbp+47h+var_C0]
0x1800c0ab3  add     ebx, r13d
0x1800c0ab6  mov     rcx, r9
0x1800c0ab9  cmp     ebx, [r9+0Ch]
0x1800c0abd  jb      short loc_1800C0A92
0x1800c0abf  jmp     loc_1800119E5
0x1800c0ac4  mov     [rbp+47h+var_A8], r12
0x1800c0ac8  lea     r8, [rbp+47h+var_A8]
0x1800c0acc  mov     edx, edi
0x1800c0ace  call    ?Get@?$DynamicArray@PEAVManagedSchema@Resources@Microsoft@@@Resources@Microsoft@@QEBAJIPEAPEAVManagedSchema@23@@Z; Microsoft::Resources::DynamicArray<Microsoft::Resources::ManagedSchema *>::Get(uint,Microsoft::Resources::ManagedSchema * *)
0x1800c0ad3  mov     rcx, [rbp+47h+var_A8]; this
0x1800c0ad7  test    rcx, rcx
0x1800c0ada  jz      short loc_1800C0AE5
0x1800c0adc  call    ??_GPriFileInfo@UnifiedResourceView@Resources@Microsoft@@QEAAPEAXI@Z; Microsoft::Resources::UnifiedResourceView::PriFileInfo::`scalar deleting destructor'(uint)
0x1800c0ae1  mov     r9, [rbp+47h+var_C0]
0x1800c0ae5  add     edi, r13d
0x1800c0ae8  mov     rcx, r9
0x1800c0aeb  cmp     edi, [r9+0Ch]
0x1800c0aef  jb      short loc_1800C0AC4
0x1800c0af1  jmp     loc_180011905
0x1800c0af6  lea     r8, aOnecoreuapBase_28; "onecoreuap\\base\\mrt\\runtime\\com\\dl"...
0x1800c0afd  mov     rcx, [rbp+4Fh]; this
0x1800c0b01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c0b06  nop
0x1800c0b07  lea     rcx, [rbp+47h+lpMem]
0x1800c0b0b  call    ??1?$DynamicArray@PEAVPriFileInfo@UnifiedResourceView@Resources@Microsoft@@@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::DynamicArray<Microsoft::Resources::UnifiedResourceView::PriFileInfo *>::~DynamicArray<Microsoft::Resources::UnifiedResourceView::PriFileInfo *>(void)
0x1800c0b10  nop
0x1800c0b11  lea     rcx, [rbp+47h+var_90]; this
0x1800c0b15  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
  ... truncated ...
```
