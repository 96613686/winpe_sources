# RepoMan::CreateDeltaFile(IStream *,IStream *,IStream *)

- ea: `0x1801927e4`
- end: `0x180192ef5`
- name: `?CreateDeltaFile@RepoMan@@YA_NPEAUIStream@@00@Z`
- size: `1809`
- prototype: `bool __fastcall(RepoMan *__hidden this, struct IStream *, struct IStream *, struct IStream *)`
- caller_count: `1`
- callee_count: `13`
- tags: ``

## callers

- `0x1800cd170`

## callees

- `0x1800028e8`
- `0x180003710`
- `0x1800038ac`
- `0x180013b14`
- `0x18001c48c`
- `0x18002e5bc`
- `0x18002e6b8`
- `0x180038ac8`
- `0x18018aed8`
- `0x1801927e4`
- `0x18019a840`
- `0x18019f7a0`
- `0x18019fea0`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!free` at `0x18019298b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180192a2d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180192d78`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180192db9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180192dfa`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180192e4f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180192e90`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18019298b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180192a2d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180192d78`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180192db9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180192dfa`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180192e4f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180192e90`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180192981`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180192c7c`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180192d71`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180192daf`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180192df0`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180192e45`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180192e86`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180192981`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180192c7c`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180192d71`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180192daf`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180192df0`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180192e45`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180192e86`
- `msdelta!DeltaFree` at `0x180192c42`
- `msdelta!DeltaFree` at `0x180192c42`
- `msdelta!CreateDeltaB` at `0x180192bf2`
- `msdelta!CreateDeltaB` at `0x180192bf2`

## string_xrefs

- `0x180192829`: `Win32.CreateDelta`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
bool __fastcall RepoMan::CreateDeltaFile(RepoMan *this, struct IStream *a2, struct IStream *a3, struct IStream *a4)
{
  __int64 v6; // rax
  size_t v7; // rbx
  __int64 v8; // rsi
  _BYTE *v9; // rdi
  char *v10; // r13
  __int64 v11; // rax
  size_t v12; // r15
  __int64 v13; // r14
  char *v14; // r8
  char *v15; // rbx
  __int64 v16; // r15
  char *v17; // rax
  __int64 v18; // r13
  void *v19; // r15
  int uSize; // r15d
  const char *v21; // r9
  unsigned int v22; // r13d
  void *v23; // rcx
  void *v24; // rcx
  char *v25; // rax
  _BYTE *v26; // rax
  bool result; // al
  char *v28; // rax
  _BYTE *v29; // rax
  char *v30; // [rsp+60h] [rbp-1B8h] BYREF
  void *v31; // [rsp+68h] [rbp-1B0h] BYREF
  void *Block[2]; // [rsp+70h] [rbp-1A8h] BYREF
  __int64 v33; // [rsp+80h] [rbp-198h]
  void *v34[2]; // [rsp+88h] [rbp-190h] BYREF
  __int64 v35; // [rsp+98h] [rbp-180h]
  DELTA_INPUT Source; // [rsp+A0h] [rbp-178h] BYREF
  DELTA_INPUT Target; // [rsp+C0h] [rbp-158h] BYREF
  DELTA_OUTPUT Delta; // [rsp+E0h] [rbp-138h] BYREF
  struct IStream *v39; // [rsp+F0h] [rbp-128h]
  RepoMan *v40; // [rsp+F8h] [rbp-120h]
  struct IStream *v41; // [rsp+100h] [rbp-118h]
  __int128 v42; // [rsp+108h] [rbp-110h]
  __int64 v43; // [rsp+118h] [rbp-100h]
  DELTA_INPUT SourceOptions; // [rsp+120h] [rbp-F8h] BYREF
  DELTA_INPUT GlobalOptions; // [rsp+140h] [rbp-D8h] BYREF
  DELTA_INPUT TargetOptions; // [rsp+160h] [rbp-B8h] BYREF
  void *v47[2]; // [rsp+180h] [rbp-98h] BYREF
  __m128i si128; // [rsp+190h] [rbp-88h]
  _BYTE v49[40]; // [rsp+1A0h] [rbp-78h] BYREF
  __int64 v50; // [rsp+1C8h] [rbp-50h]

  v39 = a3;
  v41 = a2;
  v40 = this;
  RepoMan::Tracer::Tracer(v49, 1, "Win32.CreateDelta");
  try
  {
    v6 = RepoMan::StreamBase<>::Size(this);
    v7 = v6;
    *(_OWORD *)v34 = 0;
    v8 = 0;
    v35 = 0;
    if ( v6 )
    {
      std::vector<unsigned char>::_Buy_nonzero(v34, v6);
      v9 = v34[0];
      memset(v34[0], 0, v7);
      v10 = &v9[v7];
      v34[1] = &v9[v7];
      v8 = v35;
    }
    else
    {
      v10 = (char *)v34[1];
      v9 = v34[0];
    }
    v31 = v10;
    v11 = RepoMan::StreamBase<>::Size(a3);
    v12 = v11;
    *(_OWORD *)Block = 0;
    v13 = 0;
    v33 = 0;
    v14 = 0;
    if ( v11 )
    {
      std::vector<unsigned char>::_Buy_nonzero(Block, v11);
      v15 = (char *)Block[0];
      memset(Block[0], 0, v12);
      v14 = &v15[v12];
      v30 = &v15[v12];
      Block[1] = &v15[v12];
      v13 = v33;
    }
    else
    {
      v30 = (char *)Block[1];
      v15 = (char *)Block[0];
    }
    v16 = RepoMan::StreamBase<>::Read(&Target, v39, v14 - v15);
    if ( Block != (void **)v16 )
    {
      if ( v15 )
      {
        v17 = v15;
        if ( (unsigned __int64)(v13 - (_QWORD)v15) >= 0x1000 )
        {
          v15 = (char *)*((_QWORD *)v15 - 1);
          if ( (unsigned __int64)(v17 - v15 - 8) > 0x1F )
            _invoke_watson(0, 0, 0, 0, 0);
        }
        free(v15);
      }
      v15 = *(char **)v16;
      Block[0] = *(void **)v16;
      v30 = *(char **)(v16 + 8);
      Block[1] = v30;
      v13 = *(_QWORD *)(v16 + 16);
      v33 = v13;
      *(_QWORD *)v16 = 0;
      *(_QWORD *)(v16 + 8) = 0;
      *(_QWORD *)(v16 + 16) = 0;
    }
    std::vector<unsigned char>::_Tidy(&Target);
    v18 = RepoMan::StreamBase<>::Read(&Target, v40, v10 - v9);
    v19 = v9;
    if ( v34 != (void **)v18 )
    {
      if ( v9 )
      {
        if ( (unsigned __int64)(v8 - (_QWORD)v9) >= 0x1000 )
        {
          if ( (unsigned __int64)&v9[-*((_QWORD *)v9 - 1) - 8] > 0x1F )
            _invoke_watson(0, 0, 0, 0, 0);
          v19 = (void *)*((_QWORD *)v9 - 1);
        }
        free(v19);
      }
      v34[0] = *(void **)v18;
      v9 = v34[0];
      v31 = *(void **)(v18 + 8);
      v34[1] = v31;
      v8 = *(_QWORD *)(v18 + 16);
      v35 = v8;
      *(_QWORD *)v18 = 0;
      *(_QWORD *)(v18 + 8) = 0;
      *(_QWORD *)(v18 + 16) = 0;
      LODWORD(v19) = (_DWORD)v9;
    }
    std::vector<unsigned char>::_Tidy(&Target);
    v43 = 1;
    Source.lpcStart = v15;
    Source.uSize = (unsigned int)((_DWORD)v30 - (_DWORD)v15);
    *(_QWORD *)&v42 = v9;
    *((_QWORD *)&v42 + 1) = (unsigned int)((_DWORD)v31 - (_DWORD)v19);
    si128.m128i_i64[0] = 0;
    Delta = 0;
    memset(&GlobalOptions, 0, sizeof(GlobalOptions));
    memset(&TargetOptions, 0, sizeof(TargetOptions));
    memset(&SourceOptions, 0, sizeof(SourceOptions));
    *(_OWORD *)&Target.lpcStart = *(_OWORD *)&Source.lpcStart;
    *(_QWORD *)&Target.Editable = 1;
    *(_OWORD *)&Source.lpcStart = v42;
    *(_QWORD *)&Source.Editable = 1;
    if ( CreateDeltaB(
           15,
           393216,
           0,
           &Source,
           &Target,
           &SourceOptions,
           &TargetOptions,
           &GlobalOptions,
           0,
           0x8004u,
           &Delta) )
    {
      LODWORD(v30) = 0;
      uSize = Delta.uSize;
      v22 = ((__int64 (__fastcall *)(struct IStream *, LPVOID, _QWORD, char **))v41->lpVtbl->Write)(
              v41,
              Delta.lpStart,
              LODWORD(Delta.uSize),
              &v30);
      if ( Delta.lpStart )
        DeltaFree(Delta.lpStart);
      RepoMan::RaiseExceptionIfFailed(
        (RepoMan *)v22,
        172,
        (int)"src\\repoman\\src\\reposhared\\pal\\delta\\win32\\deltaapi.cpp",
        v21);
      if ( (_DWORD)v30 != uSize )
        RepoMan::RaiseException<RepoMan::Exception,enum RepoMan::Error>(
          173,
          (unsigned int)"src\\repoman\\src\\reposhared\\pal\\delta\\win32\\deltaapi.cpp",
          (unsigned int)"Not all data written.",
          -1941503468,
          8);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      qmemcpy(v47, "bytes_writte", 12);
      HIDWORD(v47[1]) = (unsigned __int8)aBytesWritten[12];
      RepoMan::Logger::CreateValue((unsigned int)&v31, 3, 11, (unsigned int)v47, (unsigned int)v30);
      (*(void (__fastcall **)(__int64, void **))(*(_QWORD *)v50 + 48LL))(v50, &v31);
      v23 = v31;
      if ( v31 )
      {
        v31 = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v23 + 8LL))(v23);
      }
      if ( si128.m128i_i64[1] > 0xFuLL )
      {
        v24 = v47[0];
        if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
        {
          v24 = (void *)*((_QWORD *)v47[0] - 1);
          if ( (unsigned __int64)((char *)v47[0] - (char *)v24 - 8) > 0x1F )
            _invoke_watson(0, 0, 0, 0, 0);
        }
        free(v24);
      }
      if ( v15 )
      {
        v25 = v15;
        if ( (unsigned __int64)(v13 - (_QWORD)v15) >= 0x1000 )
        {
          v15 = (char *)*((_QWORD *)v15 - 1);
          if ( (unsigned __int64)(v25 - v15 - 8) > 0x1F )
            _invoke_watson(0, 0, 0, 0, 0);
        }
        free(v15);
      }
      if ( v9 )
      {
        v26 = v9;
        if ( (unsigned __int64)(v8 - (_QWORD)v9) >= 0x1000 )
        {
          v9 = (_BYTE *)*((_QWORD *)v9 - 1);
          if ( (unsigned __int64)(v26 - v9 - 8) > 0x1F )
            _invoke_watson(0, 0, 0, 0, 0);
        }
        free(v9);
      }
      RepoMan::Tracer::~Tracer((RepoMan::Tracer *)v49);
      result = 1;
    }
    else
    {
      if ( v15 )
      {
        v28 = v15;
        if ( (unsigned __int64)(v13 - (_QWORD)v15) >= 0x1000 )
        {
          v15 = (char *)*((_QWORD *)v15 - 1);
          if ( (unsigned __int64)(v28 - v15 - 8) > 0x1F )
            _invoke_watson(0, 0, 0, 0, 0);
        }
        free(v15);
      }
      if ( v9 )
      {
        v29 = v9;
        if ( (unsigned __int64)(v8 - (_QWORD)v9) >= 0x1000 )
        {
          v9 = (_BYTE *)*((_QWORD *)v9 - 1);
          if ( (unsigned __int64)(v29 - v9 - 8) > 0x1F )
            _invoke_watson(0, 0, 0, 0, 0);
        }
        free(v9);
      }
      RepoMan::Tracer::~Tracer((RepoMan::Tracer *)v49);
      result = 0;
    }
  }
  catch ( ... )
  {
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1801927e4  mov     r11, rsp
0x1801927e7  push    rbx
0x1801927e8  push    rsi
0x1801927e9  push    rdi
0x1801927ea  push    r12
0x1801927ec  push    r13
0x1801927ee  push    r14
0x1801927f0  push    r15
0x1801927f2  sub     rsp, 1E0h
0x1801927f9  mov     rax, cs:__security_cookie
0x180192800  xor     rax, rsp
0x180192803  mov     [rsp+218h+var_48], rax
0x18019280b  mov     r14, r8
0x18019280e  mov     [rsp+218h+var_128], r8
0x180192816  mov     [rsp+218h+var_118], rdx
0x18019281e  mov     rbx, rcx
0x180192821  mov     [rsp+218h+var_120], rcx
0x180192829  lea     r8, aWin32Createdel; "Win32.CreateDelta"
0x180192830  mov     edx, 1
0x180192835  lea     rcx, [r11-78h]
0x180192839  call    ??0Tracer@RepoMan@@QEAA@W4Verbosity@ILogger@1@QEBD@Z; RepoMan::Tracer::Tracer(RepoMan::ILogger::Verbosity,char const * const)
0x18019283e  nop
0x18019283f  mov     rcx, rbx
0x180192842  call    ?Size@?$StreamBase@$$V@RepoMan@@SA_KPEAUIStream@@@Z; RepoMan::StreamBase<>::Size(IStream *)
0x180192847  mov     rbx, rax
0x18019284a  xorps   xmm0, xmm0
0x18019284d  movdqu  xmmword ptr [rsp+218h+var_190], xmm0
0x180192856  xor     esi, esi
0x180192858  mov     [rsp+218h+var_180], rsi
0x180192860  test    rax, rax
0x180192863  jz      short loc_1801928A0
0x180192865  mov     rdx, rax
0x180192868  lea     rcx, [rsp+218h+var_190]
0x180192870  call    ?_Buy_nonzero@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Buy_nonzero(unsigned __int64)
0x180192875  mov     r8, rbx; Size
0x180192878  xor     edx, edx; Val
0x18019287a  mov     rdi, [rsp+218h+var_190]
0x180192882  mov     rcx, rdi; void *
0x180192885  call    memset
0x18019288a  lea     r13, [rdi+rbx]
0x18019288e  mov     [rsp+218h+var_190+8], r13
0x180192896  mov     rsi, [rsp+218h+var_180]
0x18019289e  jmp     short loc_1801928B0
0x1801928a0  mov     r13, [rsp+218h+var_190+8]
0x1801928a8  mov     rdi, [rsp+218h+var_190]
0x1801928b0  mov     [rsp+218h+var_1B0], r13
0x1801928b5  mov     rcx, r14
0x1801928b8  call    ?Size@?$StreamBase@$$V@RepoMan@@SA_KPEAUIStream@@@Z; RepoMan::StreamBase<>::Size(IStream *)
0x1801928bd  mov     r15, rax
0x1801928c0  xorps   xmm0, xmm0
0x1801928c3  movdqu  xmmword ptr [rsp+218h+Block], xmm0
0x1801928c9  xor     r14d, r14d
0x1801928cc  mov     [rsp+218h+var_198], r14
0x1801928d4  xor     r8d, r8d
0x1801928d7  test    rax, rax
0x1801928da  jz      short loc_180192913
0x1801928dc  mov     rdx, rax
0x1801928df  lea     rcx, [rsp+218h+Block]
0x1801928e4  call    ?_Buy_nonzero@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Buy_nonzero(unsigned __int64)
0x1801928e9  mov     r8, r15; Size
0x1801928ec  xor     edx, edx; Val
0x1801928ee  mov     rbx, [rsp+218h+Block]
0x1801928f3  mov     rcx, rbx; void *
0x1801928f6  call    memset
0x1801928fb  lea     r8, [r15+rbx]
0x1801928ff  mov     [rsp+218h+var_1B8], r8
0x180192904  mov     [rsp+218h+Block+8], r8
0x180192909  mov     r14, [rsp+218h+var_198]
0x180192911  jmp     short loc_180192922
0x180192913  mov     rax, [rsp+218h+Block+8]
0x180192918  mov     [rsp+218h+var_1B8], rax
0x18019291d  mov     rbx, [rsp+218h+Block]
0x180192922  sub     r8, rbx
0x180192925  mov     rdx, [rsp+218h+var_128]
0x18019292d  lea     rcx, [rsp+218h+Target]
0x180192935  call    ?Read@?$StreamBase@$$V@RepoMan@@SA?AV?$vector@EV?$allocator@E@std@@@std@@PEAUIStream@@_K@Z; RepoMan::StreamBase<>::Read(IStream *,unsigned __int64)
0x18019293a  mov     r15, rax
0x18019293d  lea     rax, [rsp+218h+Block]
0x180192942  mov     r12d, 1000h
0x180192948  cmp     rax, r15
0x18019294b  jz      short loc_1801929CA
0x18019294d  test    rbx, rbx
0x180192950  jz      short loc_180192991
0x180192952  mov     rax, rbx
0x180192955  sub     r14, rbx
0x180192958  cmp     r14, r12
0x18019295b  jb      short loc_180192988
0x18019295d  mov     rbx, [rbx-8]
0x180192961  sub     rax, rbx
0x180192964  add     rax, 0FFFFFFFFFFFFFFF8h
0x180192968  cmp     rax, 1Fh
0x18019296c  jbe     short loc_180192988
0x18019296e  mov     [rsp+218h+Reserved], 0; Reserved
0x180192977  xor     r9d, r9d; LineNo
0x18019297a  xor     r8d, r8d; FileName
0x18019297d  xor     edx, edx; FunctionName
0x18019297f  xor     ecx, ecx; Expression
0x180192981  call    cs:__imp__invoke_watson
0x180192988  mov     rcx, rbx; Block
0x18019298b  call    cs:__imp_free
0x180192991  mov     rbx, [r15]
0x180192994  mov     [rsp+218h+Block], rbx
0x180192999  mov     rax, [r15+8]
0x18019299d  mov     [rsp+218h+var_1B8], rax
0x1801929a2  mov     [rsp+218h+Block+8], rax
0x1801929a7  mov     r14, [r15+10h]
0x1801929ab  mov     [rsp+218h+var_198], r14
0x1801929b3  mov     qword ptr [r15], 0
0x1801929ba  mov     qword ptr [r15+8], 0
0x1801929c2  mov     qword ptr [r15+10h], 0
0x1801929ca  lea     rcx, [rsp+218h+Target]
0x1801929d2  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1801929d7  mov     r8, r13
0x1801929da  sub     r8, rdi
0x1801929dd  mov     rdx, [rsp+218h+var_120]
0x1801929e5  lea     rcx, [rsp+218h+Target]
0x1801929ed  call    ?Read@?$StreamBase@$$V@RepoMan@@SA?AV?$vector@EV?$allocator@E@std@@@std@@PEAUIStream@@_K@Z; RepoMan::StreamBase<>::Read(IStream *,unsigned __int64)
0x1801929f2  mov     r13, rax
0x1801929f5  mov     r15, rdi
0x1801929f8  lea     rax, [rsp+218h+var_190]
0x180192a00  cmp     rax, r13
0x180192a03  jz      short loc_180192A77
0x180192a05  test    rdi, rdi
0x180192a08  jz      short loc_180192A33
0x180192a0a  sub     rsi, rdi
0x180192a0d  cmp     rsi, r12
0x180192a10  jb      short loc_180192A2A
0x180192a12  mov     rcx, [rdi-8]
0x180192a16  sub     r15, rcx
0x180192a19  lea     rax, [r15-8]
0x180192a1d  cmp     rax, 1Fh
0x180192a21  ja      loc_180192C69
0x180192a27  mov     r15, rcx
0x180192a2a  mov     rcx, r15; Block
0x180192a2d  call    cs:__imp_free
0x180192a33  mov     rdi, [r13+0]
0x180192a37  mov     [rsp+218h+var_190], rdi
0x180192a3f  mov     rax, [r13+8]
0x180192a43  mov     [rsp+218h+var_1B0], rax
0x180192a48  mov     [rsp+218h+var_190+8], rax
0x180192a50  mov     rsi, [r13+10h]
0x180192a54  mov     [rsp+218h+var_180], rsi
0x180192a5c  mov     qword ptr [r13+0], 0
0x180192a64  mov     qword ptr [r13+8], 0
0x180192a6c  mov     qword ptr [r13+10h], 0
0x180192a74  mov     r15, rdi
0x180192a77  lea     rcx, [rsp+218h+Target]
0x180192a7f  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180192a84  xor     r13d, r13d
0x180192a87  mov     [rsp+218h+var_100], 1
0x180192a93  mov     qword ptr [rsp+218h+Source.Editable], 1
0x180192a9f  mov     qword ptr [rsp+218h+Source], rbx
0x180192aa7  mov     rax, [rsp+218h+var_1B8]
0x180192aac  sub     eax, ebx
0x180192aae  mov     [rsp+218h+Source.uSize], rax
0x180192ab6  mov     qword ptr [rsp+218h+var_110], rdi
0x180192abe  mov     rax, [rsp+218h+var_1B0]
0x180192ac3  sub     rax, r15
0x180192ac6  mov     eax, eax
0x180192ac8  mov     qword ptr [rsp+218h+var_110+8], rax
0x180192ad0  xorps   xmm2, xmm2
0x180192ad3  xor     eax, eax
0x180192ad5  mov     qword ptr [rsp+218h+Target.Editable], rax
0x180192add  xorps   xmm3, xmm3
0x180192ae0  mov     qword ptr [rsp+218h+var_88], rax
0x180192ae8  xorps   xmm1, xmm1
0x180192aeb  mov     qword ptr [rsp+218h+var_F8.Editable], rax
0x180192af3  xorps   xmm0, xmm0
0x180192af6  movups  xmmword ptr [rsp+218h+Delta.lpStart], xmm0
0x180192afe  movaps  xmmword ptr [rsp+218h+var_D8], xmm2
0x180192b06  movsd   xmm0, qword ptr [rsp+218h+Target.Editable]
0x180192b0f  movsd   qword ptr [rsp+218h+var_D8.Editable], xmm0
0x180192b18  movaps  xmmword ptr [rsp+218h+var_B8], xmm1
0x180192b20  movsd   xmm0, qword ptr [rsp+218h+var_F8.Editable]
0x180192b29  movsd   qword ptr [rsp+218h+var_B8.Editable], xmm0
0x180192b32  movaps  xmmword ptr [rsp+218h+var_F8], xmm3
0x180192b3a  movsd   xmm0, qword ptr [rsp+218h+var_88]
0x180192b43  movsd   qword ptr [rsp+218h+var_F8.Editable], xmm0
0x180192b4c  movups  xmm1, xmmword ptr [rsp+218h+Source]
0x180192b54  movaps  xmmword ptr [rsp+218h+Target], xmm1
0x180192b5c  movsd   xmm0, qword ptr [rsp+218h+Source.Editable]
0x180192b65  movsd   qword ptr [rsp+218h+Target.Editable], xmm0
0x180192b6e  movups  xmm1, [rsp+218h+var_110]
0x180192b76  movaps  xmmword ptr [rsp+218h+Source], xmm1
0x180192b7e  movsd   xmm0, [rsp+218h+var_100]
0x180192b87  movsd   qword ptr [rsp+218h+Source.Editable], xmm0
0x180192b90  lea     rax, [rsp+218h+Delta]
0x180192b98  mov     [rsp+218h+lpDelta], rax; lpDelta
0x180192b9d  mov     [rsp+218h+HashAlgId], 8004h; HashAlgId
0x180192ba5  mov     [rsp+218h+lpTargetFileTime], r13; lpTargetFileTime
0x180192baa  lea     rax, [rsp+218h+var_D8]
0x180192bb2  mov     [rsp+218h+GlobalOptions], rax; GlobalOptions
0x180192bb7  lea     rax, [rsp+218h+var_B8]
0x180192bbf  mov     [rsp+218h+TargetOptions], rax; TargetOptions
0x180192bc4  lea     rax, [rsp+218h+var_F8]
0x180192bcc  mov     [rsp+218h+SourceOptions], rax; SourceOptions
0x180192bd1  lea     rax, [rsp+218h+Target]
0x180192bd9  mov     [rsp+218h+Reserved], rax; Target
0x180192bde  lea     r9, [rsp+218h+Source]; Source
0x180192be6  xor     r8d, r8d; ResetFlags
0x180192be9  mov     edx, 60000h; SetFlags
0x180192bee  lea     ecx, [r13+0Fh]; FileTypeSet
0x180192bf2  call    cs:__imp_CreateDeltaB
0x180192bf8  test    eax, eax
0x180192bfa  jz      loc_180192E15
0x180192c00  mov     dword ptr [rsp+218h+var_1B8], r13d
0x180192c05  mov     r15d, dword ptr [rsp+218h+Delta.uSize]
0x180192c0d  mov     rcx, [rsp+218h+var_118]
0x180192c15  mov     rax, [rcx]
0x180192c18  lea     r9, [rsp+218h+var_1B8]
0x180192c1d  mov     r8d, r15d
0x180192c20  mov     rdx, [rsp+218h+Delta.lpStart]
0x180192c28  mov     rax, [rax+20h]
0x180192c2c  call    cs:__guard_dispatch_icall_fptr
0x180192c32  mov     r13d, eax
0x180192c35  mov     rcx, [rsp+218h+Delta.lpStart]; lpMemory
0x180192c3d  test    rcx, rcx
0x180192c40  jz      short loc_180192C48
0x180192c42  call    cs:__imp_DeltaFree
0x180192c48  lea     r8, aSrcRepomanSrcR_11; "src\\repoman\\src\\reposhared\\pal\\del"...
0x180192c4f  mov     edx, 0ACh; int
0x180192c54  mov     ecx, r13d; this
0x180192c57  call    ?RaiseExceptionIfFailed@RepoMan@@YAXJHQEBD@Z; RepoMan::RaiseExceptionIfFailed(long,int,char const * const)
0x180192c5c  cmp     dword ptr [rsp+218h+var_1B8], r15d
0x180192c61  jnz     loc_180192ECD
0x180192c67  jmp     short loc_180192C83
0x180192c69  mov     [rsp+218h+Reserved], 0; Reserved
0x180192c72  xor     r9d, r9d; LineNo
0x180192c75  xor     r8d, r8d; FileName
0x180192c78  xor     edx, edx; FunctionName
0x180192c7a  xor     ecx, ecx; Expression
0x180192c7c  call    cs:__imp__invoke_watson
0x180192c83  xorps   xmm0, xmm0
0x180192c86  movups  xmmword ptr [rsp+218h+var_98], xmm0
0x180192c8e  movdqa  xmm0, cs:__xmm@000000000000000f000000000000000d
0x180192c96  movdqu  [rsp+218h+var_88], xmm0
0x180192c9f  movsd   xmm0, qword ptr cs:aBytesWritten; "bytes_written"
0x180192ca7  movsd   [rsp+218h+var_98], xmm0
0x180192cb0  mov     eax, dword ptr cs:aBytesWritten+8; "itten"
0x180192cb6  mov     dword ptr [rsp+218h+var_98+8], eax
0x180192cbd  mov     al, byte ptr cs:aBytesWritten+0Ch; "n"
0x180192cc3  mov     byte ptr [rsp+218h+var_98+0Ch], al
0x180192cca  xor     r15d, r15d
0x180192ccd  mov     byte ptr [rsp+218h+var_98+0Dh], r15b
0x180192cd5  mov     eax, dword ptr [rsp+218h+var_1B8]
0x180192cd9  mov     [rsp+218h+Reserved], rax
0x180192cde  lea     r9, [rsp+218h+var_98]
0x180192ce6  lea     edx, [r15+3]
0x180192cea  lea     r8d, [r15+0Bh]
0x180192cee  lea     rcx, [rsp+218h+var_1B0]
0x180192cf3  call    ?CreateValue@Logger@RepoMan@@SA?AV?$Ptr@VIValue@ILogger@RepoMan@@@ILogger@2@W4ValueType@42@W4Id@42@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_K@Z; RepoMan::Logger::CreateValue(RepoMan::ILogger::ValueType,RepoMan::ILogger::Id,std::string const &,unsigned __int64)
0x180192cf8  mov     rcx, [rsp+218h+var_50]
0x180192d00  mov     rax, [rcx]
0x180192d03  lea     rdx, [rsp+218h+var_1B0]
0x180192d08  mov     rax, [rax+30h]
0x180192d0c  call    cs:__guard_dispatch_icall_fptr
0x180192d12  nop
0x180192d13  mov     rcx, [rsp+218h+var_1B0]
0x180192d18  test    rcx, rcx
0x180192d1b  jz      short loc_180192D30
0x180192d1d  mov     [rsp+218h+var_1B0], r15
0x180192d22  mov     rax, [rcx]
0x180192d25  mov     rax, [rax+8]
0x180192d29  call    cs:__guard_dispatch_icall_fptr
0x180192d2f  nop
0x180192d30  mov     rax, qword ptr [rsp+218h+var_88+8]
0x180192d38  cmp     rax, 0Fh
0x180192d3c  jbe     short loc_180192D7F
0x180192d3e  mov     rcx, [rsp+218h+var_98]; Block
0x180192d46  mov     rdx, rcx
0x180192d49  inc     rax
0x180192d4c  cmp     rax, r12
0x180192d4f  jb      short loc_180192D78
0x180192d51  mov     rcx, [rcx-8]
0x180192d55  sub     rdx, rcx
0x180192d58  lea     rax, [rdx-8]
0x180192d5c  cmp     rax, 1Fh
0x180192d60  jbe     short loc_180192D78
0x180192d62  mov     [rsp+218h+Reserved], r15; Reserved
0x180192d67  xor     r9d, r9d; LineNo
0x180192d6a  xor     r8d, r8d; FileName
0x180192d6d  xor     edx, edx; FunctionName
0x180192d6f  xor     ecx, ecx; Expression
0x180192d71  call    cs:__imp__invoke_watson
0x180192d78  call    cs:__imp_free
0x180192d7e  nop
0x180192d7f  test    rbx, rbx
0x180192d82  jz      short loc_180192DC0
0x180192d84  mov     rax, rbx
0x180192d87  sub     r14, rbx
0x180192d8a  cmp     r14, r12
0x180192d8d  jb      short loc_180192DB6
0x180192d8f  mov     rbx, [rbx-8]
0x180192d93  sub     rax, rbx
0x180192d96  add     rax, 0FFFFFFFFFFFFFFF8h
0x180192d9a  cmp     rax, 1Fh
0x180192d9e  jbe     short loc_180192DB6
0x180192da0  mov     [rsp+218h+Reserved], r15; Reserved
0x180192da5  xor     r9d, r9d; LineNo
0x180192da8  xor     r8d, r8d; FileName
  ... truncated ...
```
