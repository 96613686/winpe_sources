# MkvMfSourceLib::MkvMfSource::GetNextBlockForStream(MkvMfSourceLib::MkvMfStream *)

- ea: `0x180012f90`
- end: `0x180013324`
- name: `?GetNextBlockForStream@MkvMfSource@MkvMfSourceLib@@AEAAJPEAVMkvMfStream@2@@Z`
- size: `916`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfSource *__hidden this, struct MkvMfSourceLib::MkvMfStream *)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x180015dcc`

## callees

- `0x1800023e0`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180010fd0`
- `0x180012f90`
- `0x18001ac70`
- `0x180020d84`
- `0x180020ea0`
- `0x180020ef4`
- `0x180042db4`
- `0x180071330`
- `0x1800953f4`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800131be`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800131be`

## string_xrefs

- `0x1800130fe`: `OnRequestSample AsyncReadInit 1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MkvMfSourceLib::MkvMfSource::GetNextBlockForStream(
        MkvMfSourceLib::MkvMfSource *this,
        struct MkvMfSourceLib::MkvMfStream *a2)
{
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v5; // ebx
  int v6; // eax
  int v7; // eax
  __int64 v8; // r8
  int Init; // eax
  unsigned int v10; // ebx
  __int64 v11; // rdx
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 *v15; // rcx
  CallStackTracing *v16; // rax
  struct CallStackContext *v17; // rax
  _BYTE v19[4]; // [rsp+40h] [rbp-30h] BYREF
  int v20; // [rsp+44h] [rbp-2Ch] BYREF
  int v21; // [rsp+48h] [rbp-28h] BYREF
  __int64 v22; // [rsp+50h] [rbp-20h] BYREF
  MkvMfSourceLib::MkvMfSource *v23; // [rsp+58h] [rbp-18h] BYREF
  int *v24; // [rsp+60h] [rbp-10h]

  v20 = 0;
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v19,
    "MkvMfSourceLib::MkvMfSource::GetNextBlockForStream",
    1705);
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *((_QWORD *)this + 86) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v5 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 86) + 296LL))(*((_QWORD *)this + 86));
    *((_OWORD *)ThreadRelativeContext + 125) = *(_OWORD *)(*(__int64 (__fastcall **)(_QWORD, MkvMfSourceLib::MkvMfSource **))(**((_QWORD **)this + 86) + 280LL))(
                                                            *((_QWORD *)this + 86),
                                                            &v23);
    *((_DWORD *)ThreadRelativeContext + 504) = v5;
  }
  v23 = this;
  v24 = &v20;
  *((_QWORD *)this + 68) = *((_QWORD *)a2 + 41);
LABEL_5:
  v6 = (*(__int64 (__fastcall **)(struct MkvMfSourceLib::MkvMfStream *, _QWORD))(*(_QWORD *)a2 + 168LL))(a2, 0);
  if ( v6 )
  {
    if ( v6 <= 0 )
    {
      while ( 1 )
      {
        v22 = 0;
        v21 = 0;
        v7 = mkvparser::Cluster::Parse(*((mkvparser::Cluster **)this + 68), &v22, &v21);
        if ( v7 >= 0 )
          goto LABEL_5;
        if ( v7 != -1072863856 )
          break;
        Init = MkvReader::AsyncReadInit(
                 (MkvMfSourceLib::MkvMfSource *)((char *)this + 184),
                 v22,
                 v21,
                 (struct IMFAsyncCallback *)this + 61);
        v10 = Init;
        if ( Init < 0 )
        {
          MkvMfSourceLib::MkvMfSource::Error(this, L"OnRequestSample AsyncReadInit 1", Init);
LABEL_32:
          CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v19);
          return v10;
        }
        if ( Init == 1 )
        {
          *((_QWORD *)this + 66) = &MkvMfSourceLib::MkvMfSource::StateAsyncRequestSample;
          *((_DWORD *)this + 134) = 0;
          *((_DWORD *)this + 135) = HIDWORD(v24);
          goto LABEL_34;
        }
      }
      v11 = (unsigned int)++*((_DWORD *)a2 + 108);
      if ( (unsigned __int8)byte_1800D78D3 >= 4u )
        WPP_SF_qqdiD(
          *((_QWORD *)WPP_GLOBAL_Control + 17),
          v11,
          v8,
          this,
          a2,
          v11,
          *(_QWORD *)(*((_QWORD *)this + 68) + 24LL),
          v7);
      if ( *((_DWORD *)a2 + 108) <= 5u
        || (*(unsigned __int8 (__fastcall **)(struct MkvMfSourceLib::MkvMfStream *, __int64))(*(_QWORD *)a2 + 120LL))(
             a2,
             v11) )
      {
        *((_DWORD *)this + 120) = 0;
        *((_QWORD *)this + 66) = &MkvMfSourceLib::MkvMfSource::StateAsyncGetNextBlockCluster;
        *((_DWORD *)this + 134) = 0;
        *((_DWORD *)this + 135) = HIDWORD(v24);
        MkvMfSourceLib::MkvMfSource::QueueOperation(this, (struct IMFAsyncCallback *)this + 62);
        v10 = 1;
      }
      else
      {
        if ( (unsigned __int8)byte_1800D78D3 >= 4u )
          WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 17), 177, v13, this, a2);
        v20 = -1072875829;
        v15 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v16 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v12, v13, v14);
          CallStackTracing::s_wpInstance = v16;
          if ( v16 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v16 + 8LL))(v16, 2032) )
          {
            v15 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v15 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
          }
        }
        if ( *((_BYTE *)v15 + 8) )
        {
          v17 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v15);
          if ( v20 < 0 && *((_DWORD *)v17 + 499) != v20 )
            CallStackContext::TraceFailure(v17, "MkvMfSourceLib::MkvMfSource::GetNextBlockForStream", 1767, v20);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            178,
            &WPP_767377f0d4d83278867700df36ce02a8_Traceguids,
            this,
            v20);
        v10 = v20;
      }
      goto LABEL_32;
    }
    *((_DWORD *)this + 120) = 0;
    *((_QWORD *)this + 66) = &MkvMfSourceLib::MkvMfSource::StateAsyncGetNextBlockCluster;
    *((_DWORD *)this + 134) = 0;
    *((_DWORD *)this + 135) = HIDWORD(v24);
    MkvMfSourceLib::MkvMfSource::QueueOperation(this, (struct IMFAsyncCallback *)this + 62);
LABEL_34:
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v19);
    return 1;
  }
  else
  {
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v19);
    return 0;
  }
}

```

## disassembly

```asm
0x180012f90  mov     [rsp-18h+arg_10], rbx
0x180012f95  mov     [rsp-18h+arg_18], rsi
0x180012f9a  push    rbp
0x180012f9b  push    rdi
0x180012f9c  push    r14
0x180012f9e  mov     rbp, rsp
0x180012fa1  sub     rsp, 70h
0x180012fa5  mov     rax, cs:__security_cookie
0x180012fac  xor     rax, rsp
0x180012faf  mov     [rbp+var_8], rax
0x180012fb3  mov     r14, rdx
0x180012fb6  mov     rsi, rcx
0x180012fb9  mov     [rbp+var_2C], 0
0x180012fc0  mov     r8d, 6A9h; int
0x180012fc6  lea     rdx, aMkvmfsourcelib_87; "MkvMfSourceLib::MkvMfSource::GetNextBlo"...
0x180012fcd  lea     rcx, [rbp+var_30]; this
0x180012fd1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180012fd6  nop
0x180012fd7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180012fde  cmp     byte ptr [rcx+8], 0
0x180012fe2  jz      short loc_18001303F
0x180012fe4  cmp     qword ptr [rsi+2B0h], 0
0x180012fec  jz      short loc_18001303F
0x180012fee  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180012ff3  mov     rdi, rax
0x180012ff6  mov     rdx, [rsi+2B0h]
0x180012ffd  mov     rcx, [rdx]
0x180013000  mov     rax, [rcx+128h]
0x180013007  mov     rcx, rdx
0x18001300a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001300f  mov     ebx, eax
0x180013011  mov     r8, [rsi+2B0h]
0x180013018  mov     rcx, [r8]
0x18001301b  mov     rax, [rcx+118h]
0x180013022  lea     rdx, [rbp+var_18]
0x180013026  mov     rcx, r8
0x180013029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001302e  movups  xmm0, xmmword ptr [rax]
0x180013031  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x180013039  mov     [rdi+7E0h], ebx
0x18001303f  mov     [rbp+var_18], rsi
0x180013043  lea     rax, [rbp+var_2C]
0x180013047  mov     [rbp+var_10], rax
0x18001304b  mov     rax, [r14+148h]
0x180013052  mov     [rsi+220h], rax
0x180013059  mov     edi, 1
0x18001305e  mov     rax, [r14]
0x180013061  xor     edx, edx
0x180013063  mov     rcx, r14
0x180013066  mov     rax, [rax+0A8h]
0x18001306d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013072  test    eax, eax
0x180013074  jz      loc_1800132F8
0x18001307a  jg      loc_1800132B0
0x180013080  mov     [rbp+var_20], 0
0x180013088  mov     [rbp+var_28], 0
0x18001308f  lea     r8, [rbp+var_28]; int *
0x180013093  lea     rdx, [rbp+var_20]; __int64 *
0x180013097  mov     rcx, [rsi+220h]; this
0x18001309e  call    ?Parse@Cluster@mkvparser@@QEBAJAEA_JAEAJ@Z; mkvparser::Cluster::Parse(__int64 &,long &)
0x1800130a3  mov     ecx, eax
0x1800130a5  test    eax, eax
0x1800130a7  jns     short loc_18001305E
0x1800130a9  cmp     eax, 0C00D6590h
0x1800130ae  jnz     short loc_180013113
0x1800130b0  lea     r9, [rsi+1E8h]; struct IMFAsyncCallback *
0x1800130b7  lea     rcx, [rsi+0B8h]; this
0x1800130be  mov     r8d, [rbp+var_28]; int
0x1800130c2  mov     rdx, [rbp+var_20]; __int64
0x1800130c6  call    ?AsyncReadInit@MkvReader@@QEAAJ_JJPEAUIMFAsyncCallback@@@Z; MkvReader::AsyncReadInit(__int64,long,IMFAsyncCallback *)
0x1800130cb  mov     ebx, eax
0x1800130cd  test    eax, eax
0x1800130cf  js      short loc_1800130FB
0x1800130d1  cmp     eax, edi
0x1800130d3  jnz     short loc_180013080
0x1800130d5  lea     rcx, ?StateAsyncRequestSample@MkvMfSource@MkvMfSourceLib@@AEAA?AW4OperationState@12@XZ; MkvMfSourceLib::MkvMfSource::StateAsyncRequestSample(void)
0x1800130dc  mov     [rsi+210h], rcx
0x1800130e3  mov     dword ptr [rsi+218h], 0
0x1800130ed  mov     ecx, dword ptr [rbp+var_10+4]
0x1800130f0  mov     [rsi+21Ch], ecx
0x1800130f6  jmp     loc_1800132EB
0x1800130fb  mov     r8d, eax; int
0x1800130fe  lea     rdx, aOnrequestsampl; "OnRequestSample AsyncReadInit 1"
0x180013105  mov     rcx, rsi; this
0x180013108  call    ?Error@MkvMfSource@MkvMfSourceLib@@AEAAJPEBGJ@Z; MkvMfSourceLib::MkvMfSource::Error(ushort const *,long)
0x18001310d  nop
0x18001310e  jmp     loc_1800132A3
0x180013113  add     [r14+1B0h], edi
0x18001311a  mov     edx, [r14+1B0h]
0x180013121  cmp     cs:byte_1800D78D3, 4
0x180013128  jb      short loc_18001315D
0x18001312a  mov     rax, [rsi+220h]
0x180013131  mov     [rsp+70h+var_38], ecx
0x180013135  mov     rax, [rax+18h]
0x180013139  mov     [rsp+70h+var_40], rax
0x18001313e  mov     [rsp+70h+var_48], edx
0x180013142  mov     [rsp+70h+var_50], r14
0x180013147  mov     r9, rsi
0x18001314a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013151  mov     rcx, [rcx+88h]
0x180013158  call    WPP_SF_qqdiD
0x18001315d  cmp     dword ptr [r14+1B0h], 5
0x180013165  jbe     loc_180013266
0x18001316b  mov     rax, [r14]
0x18001316e  mov     rcx, r14
0x180013171  mov     rax, [rax+78h]
0x180013175  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001317a  test    al, al
0x18001317c  jnz     loc_180013266
0x180013182  cmp     cs:byte_1800D78D3, 4
0x180013189  jb      short loc_1800131AB
0x18001318b  mov     edx, 0B1h
0x180013190  mov     [rsp+70h+var_50], r14
0x180013195  mov     r9, rsi
0x180013198  mov     rcx, cs:WPP_GLOBAL_Control
0x18001319f  mov     rcx, [rcx+88h]
0x1800131a6  call    WPP_SF_qq
0x1800131ab  mov     [rbp+var_2C], 0C00D36CBh
0x1800131b2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800131b9  test    rcx, rcx
0x1800131bc  jnz     short loc_1800131FF
0x1800131be  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800131c4  mov     rcx, rax
0x1800131c7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800131ce  test    rax, rax
0x1800131d1  jz      short loc_1800131F1
0x1800131d3  mov     rax, [rax]
0x1800131d6  mov     edx, 7F0h
0x1800131db  mov     rax, [rax+8]
0x1800131df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131e4  test    eax, eax
0x1800131e6  jz      short loc_1800131F1
0x1800131e8  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800131ef  jmp     short loc_1800131FF
0x1800131f1  lea     rcx, qword_1800D6F70; this
0x1800131f8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800131ff  cmp     byte ptr [rcx+8], 0
0x180013203  jz      short loc_180013231
0x180013205  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18001320a  mov     r9d, [rbp+var_2C]; int
0x18001320e  test    r9d, r9d
0x180013211  jns     short loc_180013231
0x180013213  cmp     [rax+7CCh], r9d
0x18001321a  jz      short loc_180013231
0x18001321c  mov     r8d, 6E7h; int
0x180013222  lea     rdx, aMkvmfsourcelib_87; "MkvMfSourceLib::MkvMfSource::GetNextBlo"...
0x180013229  mov     rcx, rax; this
0x18001322c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180013231  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180013238  jb      short loc_180013261
0x18001323a  mov     edx, 0B2h
0x18001323f  mov     eax, [rbp+var_2C]
0x180013242  mov     dword ptr [rsp+70h+var_50], eax
0x180013246  mov     r9, rsi
0x180013249  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180013250  mov     rcx, cs:WPP_GLOBAL_Control
0x180013257  mov     rcx, [rcx+10h]
0x18001325b  call    WPP_SF_qD
0x180013260  nop
0x180013261  mov     ebx, [rbp+var_2C]
0x180013264  jmp     short loc_1800132A3
0x180013266  mov     dword ptr [rsi+1E0h], 0
0x180013270  lea     rax, ?StateAsyncGetNextBlockCluster@MkvMfSource@MkvMfSourceLib@@AEAA?AW4OperationState@12@XZ; MkvMfSourceLib::MkvMfSource::StateAsyncGetNextBlockCluster(void)
0x180013277  mov     [rsi+210h], rax
0x18001327e  mov     dword ptr [rsi+218h], 0
0x180013288  mov     eax, dword ptr [rbp+var_10+4]
0x18001328b  mov     [rsi+21Ch], eax
0x180013291  lea     rdx, [rsi+1F0h]; struct IMFAsyncCallback *
0x180013298  mov     rcx, rsi; this
0x18001329b  call    ?QueueOperation@MkvMfSource@MkvMfSourceLib@@AEAAJPEAUIMFAsyncCallback@@@Z; MkvMfSourceLib::MkvMfSource::QueueOperation(IMFAsyncCallback *)
0x1800132a0  nop
0x1800132a1  mov     ebx, edi
0x1800132a3  lea     rcx, [rbp+var_30]; this
0x1800132a7  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800132ac  mov     eax, ebx
0x1800132ae  jmp     short loc_180013303
0x1800132b0  mov     dword ptr [rsi+1E0h], 0
0x1800132ba  lea     rax, ?StateAsyncGetNextBlockCluster@MkvMfSource@MkvMfSourceLib@@AEAA?AW4OperationState@12@XZ; MkvMfSourceLib::MkvMfSource::StateAsyncGetNextBlockCluster(void)
0x1800132c1  mov     [rsi+210h], rax
0x1800132c8  mov     dword ptr [rsi+218h], 0
0x1800132d2  mov     eax, dword ptr [rbp+var_10+4]
0x1800132d5  mov     [rsi+21Ch], eax
0x1800132db  lea     rdx, [rsi+1F0h]; struct IMFAsyncCallback *
0x1800132e2  mov     rcx, rsi; this
0x1800132e5  call    ?QueueOperation@MkvMfSource@MkvMfSourceLib@@AEAAJPEAUIMFAsyncCallback@@@Z; MkvMfSourceLib::MkvMfSource::QueueOperation(IMFAsyncCallback *)
0x1800132ea  nop
0x1800132eb  lea     rcx, [rbp+var_30]; this
0x1800132ef  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800132f4  mov     eax, edi
0x1800132f6  jmp     short loc_180013303
0x1800132f8  lea     rcx, [rbp+var_30]; this
0x1800132fc  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180013301  xor     eax, eax
0x180013303  mov     rcx, [rbp+var_8]
0x180013307  xor     rcx, rsp; StackCookie
0x18001330a  call    __security_check_cookie
0x18001330f  lea     r11, [rsp+70h+var_s0]
0x180013314  mov     rbx, [r11+30h]
0x180013318  mov     rsi, [r11+38h]
0x18001331c  mov     rsp, r11
0x18001331f  pop     r14
0x180013321  pop     rdi
0x180013322  pop     rbp
0x180013323  retn
```
