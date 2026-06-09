# SignatureGenerator

- ea: `0x1401246e0`
- end: `0x140124f65`
- name: `SignatureGenerator`
- size: `2181`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140120538`
- `0x140125138`

## callees

- `0x1400036a0`
- `0x1400036d0`
- `0x140003714`
- `0x1400046cc`
- `0x14000bacc`
- `0x14000c910`
- `0x14000cc64`
- `0x14009d5e0`
- `0x14011ed84`
- `0x14011f740`
- `0x140123284`
- `0x1401246e0`
- `0x1401b9494`
- `0x1402066a8`
- `0x140206a40`
- `0x140206b08`
- `0x140208190`
- `0x140209f78`
- `0x140223010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140124818`
- `KERNEL32!GetCurrentThreadId` at `0x14012497c`
- `KERNEL32!GetCurrentThreadId` at `0x140124a1c`
- `KERNEL32!GetCurrentThreadId` at `0x140124add`
- `KERNEL32!GetCurrentThreadId` at `0x140124b66`
- `KERNEL32!GetCurrentThreadId` at `0x140124be5`
- `KERNEL32!GetCurrentThreadId` at `0x140124d2a`
- `KERNEL32!GetCurrentThreadId` at `0x140124d73`
- `KERNEL32!GetCurrentThreadId` at `0x140124dcf`
- `KERNEL32!GetCurrentThreadId` at `0x140124e0a`
- `KERNEL32!GetCurrentThreadId` at `0x140124e5d`
- `KERNEL32!GetCurrentThreadId` at `0x140124ed7`
- `KERNEL32!GetCurrentThreadId` at `0x140124818`
- `KERNEL32!GetCurrentThreadId` at `0x14012497c`
- `KERNEL32!GetCurrentThreadId` at `0x140124a1c`
- `KERNEL32!GetCurrentThreadId` at `0x140124add`
- `KERNEL32!GetCurrentThreadId` at `0x140124b66`
- `KERNEL32!GetCurrentThreadId` at `0x140124be5`
- `KERNEL32!GetCurrentThreadId` at `0x140124d2a`
- `KERNEL32!GetCurrentThreadId` at `0x140124d73`
- `KERNEL32!GetCurrentThreadId` at `0x140124dcf`
- `KERNEL32!GetCurrentThreadId` at `0x140124e0a`
- `KERNEL32!GetCurrentThreadId` at `0x140124e5d`
- `KERNEL32!GetCurrentThreadId` at `0x140124ed7`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SignatureGenerator(
        __int64 a1,
        SignatureIndexFile *a2,
        int a3,
        unsigned int a4,
        struct RDCLibFree::FilterMaxParameters *a5,
        _OWORD *a6,
        _DWORD *a7)
{
  __int64 v8; // rdi
  int v9; // r14d
  unsigned int *v10; // rsi
  unsigned __int64 v11; // r9
  DWORD v12; // eax
  __int64 v13; // rcx
  unsigned int i; // r14d
  unsigned int v15; // r8d
  __int64 v16; // r15
  BCRYPT_HASH_HANDLE *v17; // rbx
  int v18; // edx
  SignatureBufferTee *v19; // rbx
  __int64 v20; // rdx
  __int64 v21; // rcx
  DWORD CurrentThreadId; // eax
  __int64 v23; // rcx
  struct Win32SignatureGeneration *GeneratorFilterMax2; // rax
  struct Win32SignatureGeneration *v25; // rcx
  DWORD v26; // eax
  __int64 v27; // rcx
  _DWORD *v28; // r12
  struct Win32SignatureGeneration *v29; // rbx
  int v30; // eax
  int v31; // eax
  int v32; // eax
  int v33; // eax
  __int64 v34; // rcx
  __int64 v35; // r9
  __int64 v36; // rdx
  unsigned int v37; // ebx
  DWORD v38; // eax
  __int64 v39; // rcx
  DWORD v40; // eax
  __int64 v41; // rcx
  __int64 v42; // rax
  char v43; // al
  _QWORD *v44; // r14
  unsigned __int64 v45; // r15
  __int64 v46; // r12
  bool v47; // zf
  _QWORD *v48; // rax
  __int64 v49; // rcx
  DWORD v50; // eax
  __int64 v51; // rcx
  unsigned int *v52; // rsi
  __int64 v53; // rcx
  __int64 v54; // rax
  __int64 v55; // rcx
  DWORD v56; // eax
  __int64 v57; // rcx
  unsigned __int64 v58; // rcx
  _BYTE *v59; // rdx
  __int64 v60; // rcx
  int v62; // [rsp+30h] [rbp-D0h]
  DWORD v63; // [rsp+38h] [rbp-C8h]
  DWORD v64; // [rsp+38h] [rbp-C8h]
  DWORD v65; // [rsp+38h] [rbp-C8h]
  DWORD v66; // [rsp+38h] [rbp-C8h]
  unsigned int v67; // [rsp+50h] [rbp-B0h] BYREF
  int v68; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v69; // [rsp+60h] [rbp-A0h] BYREF
  int v70; // [rsp+68h] [rbp-98h]
  unsigned int v71; // [rsp+6Ch] [rbp-94h] BYREF
  struct Win32SignatureGeneration *v72; // [rsp+70h] [rbp-90h] BYREF
  __int64 v73; // [rsp+78h] [rbp-88h] BYREF
  _QWORD *v74; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v75; // [rsp+88h] [rbp-78h] BYREF
  _OWORD *v76; // [rsp+90h] [rbp-70h]
  char v77[8]; // [rsp+98h] [rbp-68h] BYREF
  __int64 v78; // [rsp+A0h] [rbp-60h]
  char v79; // [rsp+A8h] [rbp-58h]
  struct SignatureBufferTee *v80[8]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v81[8]; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v82[23]; // [rsp+108h] [rbp+8h]
  __int128 v83; // [rsp+1C0h] [rbp+C0h] BYREF
  const wchar_t *v84; // [rsp+1D0h] [rbp+D0h]

  v73 = a1;
  v68 = a3;
  v69 = a4;
  v76 = a6;
  v8 = 0;
  if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
  {
    *(_QWORD *)&v83 = L"SignatureGenerator";
    *((_QWORD *)&v83 + 1) = 0x5000000ACLL;
    v84 = L"RDCX";
    dbgobj::DbgPrint<unsigned short,unsigned int,unsigned int>(&v83, L"Level=%?, Depth = %?", &v68, &v69);
    a4 = v69;
  }
  if ( a4 >= 8 )
    v69 = 8;
  v9 = 0;
  v70 = 0;
  v67 = 0;
  v10 = 0;
  v72 = 0;
  RDCApp::AutoBufferArray::AutoBufferArray((RDCApp::AutoBufferArray *)v77, 8u, 0x400u);
  `eh vector constructor iterator'(
    v81,
    0x18u,
    8u,
    (void (*)(void *))SignatureBufferTee::SignatureBufferTee,
    (void (*)(void *))SignatureBufferTee::~SignatureBufferTee);
  memset_0(v80, 0, sizeof(v80));
  if ( v79
    || (v12 = GetCurrentThreadId(),
        (v10 = (unsigned int *)FrsStatusList::PushNewError(
                                 v13,
                                 14,
                                 0,
                                 1,
                                 "base\\fs\\remotefs\\frs\\src\\sync\\rdc.cpp",
                                 "SignatureGenerator",
                                 197,
                                 v12,
                                 0)) == 0) )
  {
    for ( i = 0; ; ++i )
    {
      v15 = v69;
      if ( i >= v69 )
        break;
      if ( i + v68 )
      {
        v16 = i;
      }
      else
      {
        if ( g_DebugLog && LODWORD(g_DebugLog[1].LockSemaphore) && SLODWORD(g_DebugLog[1].OwningThread) >= 5 )
        {
          *(_QWORD *)&v83 = L"SignatureGenerator";
          *((_QWORD *)&v83 + 1) = 0x5000000CCLL;
          v84 = L"RDCX";
          dbgobj::DbgPrint<unsigned short>(&v83, L"Similarity enabled");
        }
        v16 = i;
        v17 = (BCRYPT_HASH_HANDLE *)operator new(0x130u);
        v75 = (unsigned __int64)v17;
        CngRsa32Compat_MD4Init(v17 + 32);
        LOBYTE(v18) = -1;
        memset_0(v17, v18, 0x100u);
        v82[3 * i] = v17;
      }
      v19 = (SignatureBufferTee *)&v81[24 * v16];
      *(_QWORD *)v19 = *(_QWORD *)(v78 + 8 * v16);
      SignatureBufferTee::InsertSignatureStreamHeader(v19);
      if ( a2 )
      {
        v20 = i + v68;
        v21 = 3 * v20;
        *((_WORD *)a2 + 4 * v21 + 15) = *((_WORD *)a5 + 2 * v16 + 1);
        *((_WORD *)a2 + 4 * v21 + 14) = *((_WORD *)a5 + 2 * v16);
        if ( !SignatureIndexFile::WriteHeader(a2, v20 + 1, 0, &v67) )
        {
          CurrentThreadId = GetCurrentThreadId();
          v10 = (unsigned int *)FrsStatusList::PushNewError(
                                  v23,
                                  v67,
                                  0,
                                  1,
                                  "base\\fs\\remotefs\\frs\\src\\sync\\rdc.cpp",
                                  "SignatureGenerator",
                                  212,
                                  CurrentThreadId,
                                  0);
          if ( v10 )
            goto LABEL_27;
          v15 = v69;
          break;
        }
      }
      v80[v16] = v19;
    }
    GeneratorFilterMax2 = Win32SignatureGeneration::CreateGeneratorFilterMax2(v80, v68 + 1, v15, v11, a5);
    v25 = 0;
    if ( GeneratorFilterMax2 )
      v25 = GeneratorFilterMax2;
    v72 = v25;
    if ( !(*(unsigned __int8 (__fastcall **)(struct Win32SignatureGeneration *, unsigned int *))(*(_QWORD *)v25 + 8LL))(
            v25,
            &v67) )
    {
      v26 = GetCurrentThreadId();
      v10 = (unsigned int *)FrsStatusList::PushNewError(
                              v27,
                              v67,
                              0,
                              1,
                              "base\\fs\\remotefs\\frs\\src\\sync\\rdc.cpp",
                              "SignatureGenerator",
                              229,
                              v26,
                              0);
    }
LABEL_27:
    v9 = v70;
  }
  v28 = a7;
  while ( 1 )
  {
LABEL_29:
    if ( v10 )
      goto LABEL_73;
    if ( v9 )
      goto LABEL_71;
    if ( *v28 )
      break;
    v29 = v72;
    v30 = (*(__int64 (__fastcall **)(struct Win32SignatureGeneration *))(*(_QWORD *)v72 + 16LL))(v72) - 2;
    if ( v30 )
    {
      v31 = v30 - 1;
      if ( v31 )
      {
        v32 = v31 - 1;
        if ( v32 )
        {
          v33 = v32 - 1;
          if ( !v33 )
          {
            v9 = 1;
            v70 = 1;
            goto LABEL_40;
          }
          if ( v33 == 1 )
          {
            (*(void (__fastcall **)(struct Win32SignatureGeneration *, __int64 *))(*(_QWORD *)v29 + 48LL))(v29, &v73);
            if ( (_DWORD)v73 == 10 )
            {
              v63 = GetCurrentThreadId();
              v62 = 326;
              v35 = 1;
              v36 = HIDWORD(v73);
            }
            else
            {
              v63 = GetCurrentThreadId();
              v62 = 329;
              v35 = 3;
              v36 = 9035;
            }
            v52 = (unsigned int *)FrsStatusList::PushNewError(
                                    v34,
                                    v36,
                                    0,
                                    v35,
                                    "base\\fs\\remotefs\\frs\\src\\sync\\rdc.cpp",
                                    "SignatureGenerator",
                                    v62,
                                    v63,
                                    0);
            (*(void (__fastcall **)(struct Win32SignatureGeneration *))(*(_QWORD *)v29 + 40LL))(v29);
            if ( v52 )
            {
              v64 = GetCurrentThreadId();
              v54 = FrsStatusList::PushNewError(
                      v53,
                      v52[1],
                      v52[2],
                      *v52,
                      "base\\fs\\remotefs\\frs\\src\\sync\\rdc.cpp",
                      "SignatureGenerator",
                      333,
                      v64,
                      v52);
LABEL_79:
              v8 = v54;
              goto LABEL_80;
            }
            goto LABEL_80;
          }
        }
        else
        {
LABEL_40:
          v37 = 0;
          do
          {
            if ( v37 >= v69 )
              break;
            if ( a2 )
            {
              v75 = 0;
              if ( !SignatureIndexFile::WriteSignatures(
                      a2,
                      v37 + v68 + 1,
                      **(const unsigned __int8 ***)(v78 + 8LL * v37),
                      *(_QWORD *)(*(_QWORD *)(v78 + 8LL * v37) + 16LL) - **(_QWORD **)(v78 + 8LL * v37),
                      &v75,
                      &v67) )
              {
                v38 = GetCurrentThreadId();
                v10 = (unsigned int *)FrsStatusList::PushNewError(
                                        v39,
                                        v67,
                                        0,
                                        1,
                                        "base\\fs\\remotefs\\frs\\src\\sync\\rdc.cpp",
                                        "SignatureGenerator",
                                        308,
                                        v38,
                                        0);
              }
            }
            *(_QWORD *)(*(_QWORD *)(v78 + 8LL * v37) + 16LL) = **(_QWORD **)(v78 + 8LL * v37);
            if ( !v10 && v9 && a2 && !SignatureIndexFile::WriteHeader(a2, v37 + v68 + 1, 1, &v67) )
            {
              v40 = GetCurrentThreadId();
              v10 = (unsigned int *)FrsStatusList::PushNewError(
                                      v41,
                                      v67,
                                      0,
                                      1,
                                      "base\\fs\\remotefs\\frs\\src\\sync\\rdc.cpp",
                                      "SignatureGenerator",
                                      315,
                                      v40,
                                      0);
            }
            ++v37;
          }
          while ( !v10 );
        }
      }
      else
      {
        v74 = 0;
        while ( 1 )
        {
          v42 = (*(__int64 (__fastcall **)(struct Win32SignatureGeneration *))(*(_QWORD *)v29 + 24LL))(v29);
          v43 = RDCLibFree::TwoQueue<RDCLibFree::ChunkSignature<RDCLibFree::MD4Wrapper::Digest> *>::PopOldest(v42, &v74);
          v9 = v70;
          if ( !v43 )
            break;
          v44 = v74;
          v45 = *v74;
          v46 = v73;
          do
          {
            if ( v45 >= v44[1] )
              break;
            v71 = 0;
            v10 = (unsigned int *)(*(__int64 (__fastcall **)(__int64, unsigned __int64, _QWORD, unsigned int *))(*(_QWORD *)v46 + 8LL))(
                                    v46,
                                    v45,
                                    (unsigned int)(*((_DWORD *)v44 + 2) - v45),
                                    &v71);
            if ( !v71 )
              break;
            v45 += v71;
          }
          while ( !v10 );
          v28 = a7;
          if ( v10 )
          {
            (*(void (__fastcall **)(struct Win32SignatureGeneration *))(*(_QWORD *)v29 + 40LL))(v29);
            v65 = GetCurrentThreadId();
            v54 = FrsStatusList::PushNewError(
                    v55,
                    v10[1],
                    v10[2],
                    *v10,
                    "base\\fs\\remotefs\\frs\\src\\sync\\rdc.cpp",
                    "SignatureGenerator",
                    270,
                    v65,
                    v10);
            goto LABEL_79;
          }
          v47 = v45 == *v44;
          v44[2] = v45;
          if ( !v47 )
          {
            v48 = (_QWORD *)(*(__int64 (__fastcall **)(struct Win32SignatureGeneration *))(*(_QWORD *)v29 + 24LL))(v29);
            *(_QWORD *)(v48[4] + 8LL * v48[3]) = v44;
            v49 = 0;
            if ( v48[3] + 1LL != *v48 )
              v49 = v48[3] + 1LL;
            v48[3] = v49;
          }
          if ( v44[1] != v44[2] )
          {
            (*(void (__fastcall **)(struct Win32SignatureGeneration *))(*(_QWORD *)v29 + 32LL))(v29);
            v9 = v70;
            goto LABEL_29;
          }
        }
      }
    }
    else
    {
      v50 = GetCurrentThreadId();
      v10 = (unsigned int *)FrsStatusList::PushNewError(
                              v51,
                              9035,
                              0,
                              3,
                              "base\\fs\\remotefs\\frs\\src\\sync\\rdc.cpp",
                              "SignatureGenerator",
                              291,
                              v50,
                              0);
    }
  }
  (*(void (__fastcall **)(struct Win32SignatureGeneration *))(*(_QWORD *)v72 + 40LL))(v72);
LABEL_71:
  if ( *v28 )
  {
    v56 = GetCurrentThreadId();
    v10 = (unsigned int *)FrsStatusList::PushNewError(
                            v57,
                            9033,
                            0,
                            3,
                            "base\\fs\\remotefs\\frs\\src\\sync\\rdc.cpp",
                            "SignatureGenerator",
                            341,
                            v56,
                            0);
  }
LABEL_73:
  if ( !v68 )
  {
    v58 = 0;
    v59 = (_BYTE *)(v82[0] + 7LL);
    do
    {
      *((_BYTE *)&v83 + v58++) = *v59 & 0x3F;
      v59 += 16;
    }
    while ( v58 < 0x10 );
    *v76 = v83;
  }
  if ( v10 )
  {
    v66 = GetCurrentThreadId();
    v54 = FrsStatusList::PushNewError(
            v60,
            v10[1],
            v10[2],
            *v10,
            "base\\fs\\remotefs\\frs\\src\\sync\\rdc.cpp",
            "SignatureGenerator",
            350,
            v66,
            v10);
    goto LABEL_79;
  }
LABEL_80:
  `eh vector destructor iterator'(v81, 0x18u, 8u, (void (*)(void *))SignatureBufferTee::~SignatureBufferTee);
  RDCApp::AutoBufferArray::~AutoBufferArray((RDCApp::AutoBufferArray *)v77);
  scoped_any<Rdc::RDCIndexReader *,close_delete,null_t,0>::~scoped_any<Rdc::RDCIndexReader *,close_delete,null_t,0>(&v72);
  return v8;
}

```

## disassembly

```asm
0x1401246e0  push    rbp
0x1401246e2  push    rbx
0x1401246e3  push    rsi
0x1401246e4  push    rdi
0x1401246e5  push    r12
0x1401246e7  push    r13
0x1401246e9  push    r14
0x1401246eb  push    r15
0x1401246ed  lea     rbp, [rsp-0E8h]
0x1401246f5  sub     rsp, 1E8h
0x1401246fc  mov     rax, cs:__security_cookie
0x140124703  xor     rax, rsp
0x140124706  mov     [rbp+120h+var_48], rax
0x14012470d  mov     r13, rdx
0x140124710  mov     [rsp+220h+var_1A8], rcx
0x140124715  mov     [rsp+220h+var_1C8], r8d
0x14012471a  mov     [rsp+220h+var_1C0], r9d
0x14012471f  mov     r12, [rbp+120h+arg_20]
0x140124726  mov     rax, [rbp+120h+arg_28]
0x14012472d  mov     [rbp+120h+var_190], rax
0x140124731  lea     rcx, aSignaturegener; "SignatureGenerator"
0x140124738  lea     rdx, aRdcx; "RDCX"
0x14012473f  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140124746  xor     edi, edi
0x140124748  test    rax, rax
0x14012474b  jz      short loc_14012479C
0x14012474d  cmp     [rax+40h], edi
0x140124750  jz      short loc_14012479C
0x140124752  cmp     dword ptr [rax+38h], 5
0x140124756  jl      short loc_14012479C
0x140124758  mov     qword ptr [rbp+120h+var_60], rcx
0x14012475f  mov     dword ptr [rbp+120h+var_60+8], 0ACh
0x140124769  mov     dword ptr [rbp+120h+var_60+0Ch], 5
0x140124773  mov     [rbp+120h+var_50], rdx
0x14012477a  lea     r9, [rsp+220h+var_1C0]
0x14012477f  lea     r8, [rsp+220h+var_1C8]
0x140124784  lea     rdx, aLevelDepth; "Level=%?, Depth = %?"
0x14012478b  lea     rcx, [rbp+120h+var_60]
0x140124792  call    ??$DbgPrint@GII@dbgobj@@QEAA_KPEBGAEBI1@Z; dbgobj::DbgPrint<ushort,uint,uint>(ushort const *,uint const &,uint const &)
0x140124797  mov     r9d, [rsp+220h+var_1C0]
0x14012479c  mov     ebx, 8
0x1401247a1  cmp     r9d, ebx
0x1401247a4  jb      short loc_1401247AA
0x1401247a6  mov     [rsp+220h+var_1C0], ebx
0x1401247aa  mov     r14d, edi
0x1401247ad  mov     [rsp+220h+var_1B8], edi
0x1401247b1  mov     [rsp+220h+var_1D0], edi
0x1401247b5  mov     rsi, rdi
0x1401247b8  mov     [rsp+220h+var_1B0], rdi
0x1401247bd  mov     r8d, 400h; unsigned __int64
0x1401247c3  mov     rdx, rbx; unsigned __int64
0x1401247c6  lea     rcx, [rbp+120h+var_188]; this
0x1401247ca  call    ??0AutoBufferArray@RDCApp@@QEAA@_K0@Z; RDCApp::AutoBufferArray::AutoBufferArray(unsigned __int64,unsigned __int64)
0x1401247cf  nop
0x1401247d0  lea     rax, ??1SignatureBufferTee@@QEAA@XZ; SignatureBufferTee::~SignatureBufferTee(void)
0x1401247d7  mov     [rsp+220h+var_200], rax; void (*)(void *)
0x1401247dc  lea     r9, ??0SignatureBufferTee@@QEAA@XZ; void (*)(void *)
0x1401247e3  mov     r8, rbx; unsigned __int64
0x1401247e6  mov     edx, 18h; unsigned __int64
0x1401247eb  lea     rcx, [rbp+120h+var_120]; void *
0x1401247ef  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1401247f4  nop
0x1401247f5  xor     edx, edx; Val
0x1401247f7  lea     r8d, [rdx+40h]; Size
0x1401247fb  lea     rcx, [rbp+120h+var_160]; void *
0x1401247ff  call    memset_0
0x140124804  lea     r15, aSignaturegener_0; "SignatureGenerator"
0x14012480b  lea     rbx, aBaseFsRemotefs_49; "base\\fs\\remotefs\\frs\\src\\sync\\rdc"...
0x140124812  cmp     [rbp+120h+var_178], dil
0x140124816  jnz     short loc_14012485D
0x140124818  call    cs:__imp_GetCurrentThreadId
0x14012481f  nop     dword ptr [rax+rax+00h]
0x140124824  mov     [rsp+220h+var_1E0], rdi
0x140124829  mov     [rsp+220h+var_1E8], eax
0x14012482d  mov     [rsp+220h+var_1F0], 0C5h
0x140124835  mov     [rsp+220h+var_1F8], r15
0x14012483a  mov     [rsp+220h+var_200], rbx
0x14012483f  mov     r9d, 1
0x140124845  xor     r8d, r8d
0x140124848  lea     edx, [r9+0Dh]
0x14012484c  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140124851  mov     rsi, rax
0x140124854  test    rax, rax
0x140124857  jnz     loc_140124A5D
0x14012485d  mov     r14d, edi
0x140124860  mov     r8d, [rsp+220h+var_1C0]; unsigned int
0x140124865  cmp     r14d, r8d
0x140124868  jnb     loc_1401249D6
0x14012486e  mov     ecx, [rsp+220h+var_1C8]
0x140124872  add     ecx, r14d
0x140124875  jnz     loc_140124910
0x14012487b  mov     rax, cs:?g_DebugLog@@3PEAVFrsLogger@@EA; FrsLogger * g_DebugLog
0x140124882  test    rax, rax
0x140124885  jz      short loc_1401248D5
0x140124887  cmp     [rax+40h], edi
0x14012488a  jz      short loc_1401248D5
0x14012488c  cmp     dword ptr [rax+38h], 5
0x140124890  jl      short loc_1401248D5
0x140124892  lea     rax, aSignaturegener; "SignatureGenerator"
0x140124899  mov     qword ptr [rbp+120h+var_60], rax
0x1401248a0  mov     dword ptr [rbp+120h+var_60+8], 0CCh
0x1401248aa  mov     dword ptr [rbp+120h+var_60+0Ch], 5
0x1401248b4  lea     rax, aRdcx; "RDCX"
0x1401248bb  mov     [rbp+120h+var_50], rax
0x1401248c2  lea     rdx, aSimilarityEnab; "Similarity enabled"
0x1401248c9  lea     rcx, [rbp+120h+var_60]
0x1401248d0  call    ??$DbgPrint@G@dbgobj@@QEAA_KPEBG@Z; dbgobj::DbgPrint<ushort>(ushort const *)
0x1401248d5  mov     r15d, r14d
0x1401248d8  mov     ecx, 130h; Size
0x1401248dd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1401248e2  mov     rbx, rax
0x1401248e5  mov     [rbp+120h+var_198], rax
0x1401248e9  lea     rcx, [rax+100h]; phHash
0x1401248f0  call    CngRsa32Compat_MD4Init
0x1401248f5  mov     r8d, 100h; Size
0x1401248fb  mov     dl, 0FFh; Val
0x1401248fd  mov     rcx, rbx; void *
0x140124900  call    memset_0
0x140124905  lea     rcx, [r15+r15*2]
0x140124909  mov     [rbp+rcx*8+120h+var_118], rbx
0x14012490e  jmp     short loc_140124913
0x140124910  mov     r15d, r14d
0x140124913  lea     rax, [r15+r15*2]
0x140124917  lea     rbx, [rbp+120h+var_120]
0x14012491b  lea     rbx, [rbx+rax*8]
0x14012491f  mov     rax, [rbp+120h+var_180]
0x140124923  mov     rcx, [rax+r15*8]
0x140124927  mov     [rbx], rcx
0x14012492a  mov     rcx, rbx; this
0x14012492d  call    ?InsertSignatureStreamHeader@SignatureBufferTee@@QEAAXXZ; SignatureBufferTee::InsertSignatureStreamHeader(void)
0x140124932  test    r13, r13
0x140124935  jz      short loc_14012496F
0x140124937  mov     edx, [rsp+220h+var_1C8]
0x14012493b  add     edx, r14d
0x14012493e  lea     rcx, [rdx+rdx*2]
0x140124942  movzx   eax, word ptr [r12+r15*4+2]
0x140124948  mov     [r13+rcx*8+1Eh], ax
0x14012494e  movzx   eax, word ptr [r12+r15*4]
0x140124953  mov     [r13+rcx*8+1Ch], ax
0x140124959  inc     edx; unsigned int
0x14012495b  lea     r9, [rsp+220h+var_1D0]; unsigned int *
0x140124960  xor     r8d, r8d; bool
0x140124963  mov     rcx, r13; this
0x140124966  call    ?WriteHeader@SignatureIndexFile@@QEAA_NI_NAEAK@Z; SignatureIndexFile::WriteHeader(uint,bool,ulong &)
0x14012496b  test    al, al
0x14012496d  jz      short loc_14012497C
0x14012496f  mov     [rbp+r15*8+120h+var_160], rbx
0x140124974  inc     r14d
0x140124977  jmp     loc_140124860
0x14012497c  call    cs:__imp_GetCurrentThreadId
0x140124983  nop     dword ptr [rax+rax+00h]
0x140124988  mov     [rsp+220h+var_1E0], rdi
0x14012498d  mov     [rsp+220h+var_1E8], eax
0x140124991  mov     [rsp+220h+var_1F0], 0D4h
0x140124999  lea     r15, aSignaturegener_0; "SignatureGenerator"
0x1401249a0  mov     [rsp+220h+var_1F8], r15
0x1401249a5  lea     rbx, aBaseFsRemotefs_49; "base\\fs\\remotefs\\frs\\src\\sync\\rdc"...
0x1401249ac  mov     [rsp+220h+var_200], rbx
0x1401249b1  mov     r9d, 1
0x1401249b7  xor     r8d, r8d
0x1401249ba  mov     edx, [rsp+220h+var_1D0]
0x1401249be  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x1401249c3  mov     rsi, rax
0x1401249c6  test    rax, rax
0x1401249c9  jnz     loc_140124A58
0x1401249cf  mov     r8d, [rsp+220h+var_1C0]
0x1401249d4  jmp     short loc_1401249E4
0x1401249d6  lea     r15, aSignaturegener_0; "SignatureGenerator"
0x1401249dd  lea     rbx, aBaseFsRemotefs_49; "base\\fs\\remotefs\\frs\\src\\sync\\rdc"...
0x1401249e4  mov     edx, [rsp+220h+var_1C8]
0x1401249e8  inc     edx; unsigned int
0x1401249ea  mov     [rsp+220h+var_200], r12; struct RDCLibFree::FilterMaxParameters *
0x1401249ef  lea     rcx, [rbp+120h+var_160]; struct SignatureBufferTee **
0x1401249f3  call    ?CreateGeneratorFilterMax2@Win32SignatureGeneration@@SAPEAV1@QEAPEAVSignatureBufferTee@@II_KPEBUFilterMaxParameters@RDCLibFree@@@Z; Win32SignatureGeneration::CreateGeneratorFilterMax2(SignatureBufferTee * * const,uint,uint,unsigned __int64,RDCLibFree::FilterMaxParameters const *)
0x1401249f8  mov     rcx, rdi
0x1401249fb  test    rax, rax
0x1401249fe  cmovnz  rcx, rax
0x140124a02  mov     [rsp+220h+var_1B0], rcx
0x140124a07  mov     rax, [rcx]
0x140124a0a  lea     rdx, [rsp+220h+var_1D0]
0x140124a0f  mov     rax, [rax+8]
0x140124a13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140124a18  test    al, al
0x140124a1a  jnz     short loc_140124A58
0x140124a1c  call    cs:__imp_GetCurrentThreadId
0x140124a23  nop     dword ptr [rax+rax+00h]
0x140124a28  mov     [rsp+220h+var_1E0], rdi
0x140124a2d  mov     [rsp+220h+var_1E8], eax
0x140124a31  mov     [rsp+220h+var_1F0], 0E5h
0x140124a39  mov     [rsp+220h+var_1F8], r15
0x140124a3e  mov     [rsp+220h+var_200], rbx
0x140124a43  mov     r9d, 1
0x140124a49  xor     r8d, r8d
0x140124a4c  mov     edx, [rsp+220h+var_1D0]
0x140124a50  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140124a55  mov     rsi, rax
0x140124a58  mov     r14d, [rsp+220h+var_1B8]
0x140124a5d  mov     r12, [rbp+120h+arg_30]
0x140124a64  lea     rbx, aBaseFsRemotefs_49; "base\\fs\\remotefs\\frs\\src\\sync\\rdc"...
0x140124a6b  test    rsi, rsi
0x140124a6e  jnz     loc_140124E9A
0x140124a74  test    r14d, r14d
0x140124a77  jnz     loc_140124E55
0x140124a7d  mov     eax, [r12]
0x140124a81  test    eax, eax
0x140124a83  jnz     loc_140124E44
0x140124a89  mov     rbx, [rsp+220h+var_1B0]
0x140124a8e  mov     rax, [rbx]
0x140124a91  mov     rcx, rbx
0x140124a94  mov     rax, [rax+10h]
0x140124a98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140124a9d  sub     eax, 2
0x140124aa0  jz      loc_140124D2A
0x140124aa6  sub     eax, 1
0x140124aa9  jz      loc_140124C36
0x140124aaf  sub     eax, 1
0x140124ab2  jz      short loc_140124B12
0x140124ab4  sub     eax, 1
0x140124ab7  jz      short loc_140124B07
0x140124ab9  cmp     eax, 1
0x140124abc  jnz     short loc_140124A64
0x140124abe  mov     rax, [rbx]
0x140124ac1  lea     rdx, [rsp+220h+var_1A8]
0x140124ac6  mov     rcx, rbx
0x140124ac9  mov     rax, [rax+30h]
0x140124acd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140124ad2  cmp     dword ptr [rsp+220h+var_1A8], 0Ah
0x140124ad7  jnz     loc_140124D73
0x140124add  call    cs:__imp_GetCurrentThreadId
0x140124ae4  nop     dword ptr [rax+rax+00h]
0x140124ae9  mov     [rsp+220h+var_1E0], rdi
0x140124aee  mov     [rsp+220h+var_1E8], eax
0x140124af2  mov     [rsp+220h+var_1F0], 146h
0x140124afa  lea     r9d, [rsi+1]
0x140124afe  mov     edx, dword ptr [rsp+220h+var_1A8+4]
0x140124b02  jmp     loc_140124D9B
0x140124b07  mov     r14d, 1
0x140124b0d  mov     [rsp+220h+var_1B8], r14d
0x140124b12  mov     ebx, edi
0x140124b14  cmp     ebx, [rsp+220h+var_1C0]
0x140124b18  jnb     loc_140124A64
0x140124b1e  test    r13, r13
0x140124b21  jz      loc_140124BA9
0x140124b27  mov     [rbp+120h+var_198], rdi
0x140124b2b  mov     ecx, ebx
0x140124b2d  mov     rax, [rbp+120h+var_180]
0x140124b31  mov     rdx, [rax+rcx*8]
0x140124b35  mov     r8, [rdx]; unsigned __int8 *
0x140124b38  mov     r9, [rdx+10h]
0x140124b3c  sub     r9, r8; unsigned __int64
0x140124b3f  mov     edx, [rsp+220h+var_1C8]
0x140124b43  inc     edx
0x140124b45  add     edx, ebx; unsigned int
0x140124b47  lea     rax, [rsp+220h+var_1D0]
0x140124b4c  mov     [rsp+220h+var_1F8], rax; unsigned int *
0x140124b51  lea     rax, [rbp+120h+var_198]
0x140124b55  mov     [rsp+220h+var_200], rax; unsigned __int64 *
0x140124b5a  mov     rcx, r13; this
0x140124b5d  call    ?WriteSignatures@SignatureIndexFile@@QEAA_NIPEBE_KAEA_KAEAK@Z; SignatureIndexFile::WriteSignatures(uint,uchar const *,unsigned __int64,unsigned __int64 &,ulong &)
0x140124b62  test    al, al
0x140124b64  jnz     short loc_140124BA9
0x140124b66  call    cs:__imp_GetCurrentThreadId
0x140124b6d  nop     dword ptr [rax+rax+00h]
0x140124b72  mov     [rsp+220h+var_1E0], rdi
0x140124b77  mov     [rsp+220h+var_1E8], eax
0x140124b7b  mov     [rsp+220h+var_1F0], 134h
0x140124b83  mov     [rsp+220h+var_1F8], r15
0x140124b88  lea     rax, aBaseFsRemotefs_49; "base\\fs\\remotefs\\frs\\src\\sync\\rdc"...
0x140124b8f  mov     [rsp+220h+var_200], rax
0x140124b94  mov     r9d, 1
0x140124b9a  xor     r8d, r8d
0x140124b9d  mov     edx, [rsp+220h+var_1D0]
0x140124ba1  call    ?PushNewError@FrsStatusList@@QEAAPEAVFrsStatus@@KHW4_FRS_ERRORTYPE@@QEAD1KKPEAV2@@Z; FrsStatusList::PushNewError(ulong,int,_FRS_ERRORTYPE,char * const,char * const,ulong,ulong,FrsStatus *)
0x140124ba6  mov     rsi, rax
0x140124ba9  mov     ecx, ebx
0x140124bab  mov     rax, [rbp+120h+var_180]
0x140124baf  mov     rdx, [rax+rcx*8]
0x140124bb3  mov     rax, [rdx]
0x140124bb6  mov     [rdx+10h], rax
0x140124bba  test    rsi, rsi
0x140124bbd  jnz     short loc_140124C26
0x140124bbf  test    r14d, r14d
0x140124bc2  jz      short loc_140124C26
0x140124bc4  test    r13, r13
0x140124bc7  jz      short loc_140124C26
0x140124bc9  mov     edx, [rsp+220h+var_1C8]
0x140124bcd  inc     edx
0x140124bcf  add     edx, ebx; unsigned int
0x140124bd1  lea     r9, [rsp+220h+var_1D0]; unsigned int *
0x140124bd6  mov     r8b, 1; bool
0x140124bd9  mov     rcx, r13; this
0x140124bdc  call    ?WriteHeader@SignatureIndexFile@@QEAA_NI_NAEAK@Z; SignatureIndexFile::WriteHeader(uint,bool,ulong &)
0x140124be1  test    al, al
0x140124be3  jnz     short loc_140124C26
0x140124be5  call    cs:__imp_GetCurrentThreadId
0x140124bec  nop     dword ptr [rax+rax+00h]
0x140124bf1  mov     [rsp+220h+var_1E0], rdi
0x140124bf6  mov     [rsp+220h+var_1E8], eax
0x140124bfa  mov     [rsp+220h+var_1F0], 13Bh
0x140124c02  mov     [rsp+220h+var_1F8], r15
  ... truncated ...
```
