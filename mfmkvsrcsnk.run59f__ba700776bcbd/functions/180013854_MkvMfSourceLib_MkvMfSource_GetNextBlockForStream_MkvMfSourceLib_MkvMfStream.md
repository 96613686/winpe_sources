# MkvMfSourceLib::MkvMfSource::GetNextBlockForStream(MkvMfSourceLib::MkvMfStream *)

- ea: `0x180013854`
- end: `0x180013bef`
- name: `?GetNextBlockForStream@MkvMfSource@MkvMfSourceLib@@AEAAJPEAVMkvMfStream@2@@Z`
- size: `923`
- prototype: `__int64 __fastcall(MkvMfSourceLib::MkvMfSource *__hidden this, struct MkvMfSourceLib::MkvMfStream *)`
- caller_count: `1`
- callee_count: `14`
- tags: ``

## callers

- `0x180016840`

## callees

- `0x180002400`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180011720`
- `0x180013854`
- `0x18001b8b0`
- `0x180021b9c`
- `0x180021ccc`
- `0x180021d28`
- `0x180044b74`
- `0x1800744d8`
- `0x18009970c`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013a82`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180013a82`

## string_xrefs

- `0x1800139c2`: `OnRequestSample AsyncReadInit 1`

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
      if ( (unsigned __int8)byte_1800DC8D3 >= 4u )
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
        if ( (unsigned __int8)byte_1800DC8D3 >= 4u )
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
            v15 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
0x180013854  mov     [rsp-18h+arg_10], rbx
0x180013859  mov     [rsp-18h+arg_18], rsi
0x18001385e  push    rbp
0x18001385f  push    rdi
0x180013860  push    r14
0x180013862  mov     rbp, rsp
0x180013865  sub     rsp, 70h
0x180013869  mov     rax, cs:__security_cookie
0x180013870  xor     rax, rsp
0x180013873  mov     [rbp+var_8], rax
0x180013877  mov     r14, rdx
0x18001387a  mov     rsi, rcx
0x18001387d  mov     [rbp+var_2C], 0
0x180013884  mov     r8d, 6A9h; int
0x18001388a  lea     rdx, aMkvmfsourcelib_87; "MkvMfSourceLib::MkvMfSource::GetNextBlo"...
0x180013891  lea     rcx, [rbp+var_30]; this
0x180013895  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18001389a  nop
0x18001389b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x1800138a2  cmp     byte ptr [rcx+8], 0
0x1800138a6  jz      short loc_180013903
0x1800138a8  cmp     qword ptr [rsi+2B0h], 0
0x1800138b0  jz      short loc_180013903
0x1800138b2  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800138b7  mov     rdi, rax
0x1800138ba  mov     rdx, [rsi+2B0h]
0x1800138c1  mov     rcx, [rdx]
0x1800138c4  mov     rax, [rcx+128h]
0x1800138cb  mov     rcx, rdx
0x1800138ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138d3  mov     ebx, eax
0x1800138d5  mov     r8, [rsi+2B0h]
0x1800138dc  mov     rcx, [r8]
0x1800138df  mov     rax, [rcx+118h]
0x1800138e6  lea     rdx, [rbp+var_18]
0x1800138ea  mov     rcx, r8
0x1800138ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138f2  movups  xmm0, xmmword ptr [rax]
0x1800138f5  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x1800138fd  mov     [rdi+7E0h], ebx
0x180013903  mov     [rbp+var_18], rsi
0x180013907  lea     rax, [rbp+var_2C]
0x18001390b  mov     [rbp+var_10], rax
0x18001390f  mov     rax, [r14+148h]
0x180013916  mov     [rsi+220h], rax
0x18001391d  mov     edi, 1
0x180013922  mov     rax, [r14]
0x180013925  xor     edx, edx
0x180013927  mov     rcx, r14
0x18001392a  mov     rax, [rax+0A8h]
0x180013931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013936  test    eax, eax
0x180013938  jz      loc_180013BC2
0x18001393e  jg      loc_180013B7A
0x180013944  mov     [rbp+var_20], 0
0x18001394c  mov     [rbp+var_28], 0
0x180013953  lea     r8, [rbp+var_28]; int *
0x180013957  lea     rdx, [rbp+var_20]; __int64 *
0x18001395b  mov     rcx, [rsi+220h]; this
0x180013962  call    ?Parse@Cluster@mkvparser@@QEBAJAEA_JAEAJ@Z; mkvparser::Cluster::Parse(__int64 &,long &)
0x180013967  mov     ecx, eax
0x180013969  test    eax, eax
0x18001396b  jns     short loc_180013922
0x18001396d  cmp     eax, 0C00D6590h
0x180013972  jnz     short loc_1800139D7
0x180013974  lea     r9, [rsi+1E8h]; struct IMFAsyncCallback *
0x18001397b  lea     rcx, [rsi+0B8h]; this
0x180013982  mov     r8d, [rbp+var_28]; int
0x180013986  mov     rdx, [rbp+var_20]; __int64
0x18001398a  call    ?AsyncReadInit@MkvReader@@QEAAJ_JJPEAUIMFAsyncCallback@@@Z; MkvReader::AsyncReadInit(__int64,long,IMFAsyncCallback *)
0x18001398f  mov     ebx, eax
0x180013991  test    eax, eax
0x180013993  js      short loc_1800139BF
0x180013995  cmp     eax, edi
0x180013997  jnz     short loc_180013944
0x180013999  lea     rcx, ?StateAsyncRequestSample@MkvMfSource@MkvMfSourceLib@@AEAA?AW4OperationState@12@XZ; MkvMfSourceLib::MkvMfSource::StateAsyncRequestSample(void)
0x1800139a0  mov     [rsi+210h], rcx
0x1800139a7  mov     dword ptr [rsi+218h], 0
0x1800139b1  mov     ecx, dword ptr [rbp+var_10+4]
0x1800139b4  mov     [rsi+21Ch], ecx
0x1800139ba  jmp     loc_180013BB5
0x1800139bf  mov     r8d, eax; int
0x1800139c2  lea     rdx, aOnrequestsampl; "OnRequestSample AsyncReadInit 1"
0x1800139c9  mov     rcx, rsi; this
0x1800139cc  call    ?Error@MkvMfSource@MkvMfSourceLib@@AEAAJPEBGJ@Z; MkvMfSourceLib::MkvMfSource::Error(ushort const *,long)
0x1800139d1  nop
0x1800139d2  jmp     loc_180013B6D
0x1800139d7  add     [r14+1B0h], edi
0x1800139de  mov     edx, [r14+1B0h]
0x1800139e5  cmp     cs:byte_1800DC8D3, 4
0x1800139ec  jb      short loc_180013A21
0x1800139ee  mov     rax, [rsi+220h]
0x1800139f5  mov     [rsp+70h+var_38], ecx
0x1800139f9  mov     rax, [rax+18h]
0x1800139fd  mov     [rsp+70h+var_40], rax
0x180013a02  mov     [rsp+70h+var_48], edx
0x180013a06  mov     [rsp+70h+var_50], r14
0x180013a0b  mov     r9, rsi
0x180013a0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180013a15  mov     rcx, [rcx+88h]
0x180013a1c  call    WPP_SF_qqdiD
0x180013a21  cmp     dword ptr [r14+1B0h], 5
0x180013a29  jbe     loc_180013B30
0x180013a2f  mov     rax, [r14]
0x180013a32  mov     rcx, r14
0x180013a35  mov     rax, [rax+78h]
0x180013a39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a3e  test    al, al
0x180013a40  jnz     loc_180013B30
0x180013a46  cmp     cs:byte_1800DC8D3, 4
0x180013a4d  jb      short loc_180013A6F
0x180013a4f  mov     edx, 0B1h
0x180013a54  mov     [rsp+70h+var_50], r14
0x180013a59  mov     r9, rsi
0x180013a5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180013a63  mov     rcx, [rcx+88h]
0x180013a6a  call    WPP_SF_qq
0x180013a6f  mov     [rbp+var_2C], 0C00D36CBh
0x180013a76  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180013a7d  test    rcx, rcx
0x180013a80  jnz     short loc_180013AC9
0x180013a82  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180013a89  nop     dword ptr [rax+rax+00h]
0x180013a8e  mov     rcx, rax
0x180013a91  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180013a98  test    rax, rax
0x180013a9b  jz      short loc_180013ABB
0x180013a9d  mov     rax, [rax]
0x180013aa0  mov     edx, 7F0h
0x180013aa5  mov     rax, [rax+8]
0x180013aa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013aae  test    eax, eax
0x180013ab0  jz      short loc_180013ABB
0x180013ab2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180013ab9  jmp     short loc_180013AC9
0x180013abb  lea     rcx, qword_1800DBF70; this
0x180013ac2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180013ac9  cmp     byte ptr [rcx+8], 0
0x180013acd  jz      short loc_180013AFB
0x180013acf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180013ad4  mov     r9d, [rbp+var_2C]; int
0x180013ad8  test    r9d, r9d
0x180013adb  jns     short loc_180013AFB
0x180013add  cmp     [rax+7CCh], r9d
0x180013ae4  jz      short loc_180013AFB
0x180013ae6  mov     r8d, 6E7h; int
0x180013aec  lea     rdx, aMkvmfsourcelib_87; "MkvMfSourceLib::MkvMfSource::GetNextBlo"...
0x180013af3  mov     rcx, rax; this
0x180013af6  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180013afb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, dil; MFWppLevels g_wppLevels
0x180013b02  jb      short loc_180013B2B
0x180013b04  mov     edx, 0B2h
0x180013b09  mov     eax, [rbp+var_2C]
0x180013b0c  mov     dword ptr [rsp+70h+var_50], eax
0x180013b10  mov     r9, rsi
0x180013b13  lea     r8, WPP_767377f0d4d83278867700df36ce02a8_Traceguids
0x180013b1a  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b21  mov     rcx, [rcx+10h]
0x180013b25  call    WPP_SF_qD
0x180013b2a  nop
0x180013b2b  mov     ebx, [rbp+var_2C]
0x180013b2e  jmp     short loc_180013B6D
0x180013b30  mov     dword ptr [rsi+1E0h], 0
0x180013b3a  lea     rax, ?StateAsyncGetNextBlockCluster@MkvMfSource@MkvMfSourceLib@@AEAA?AW4OperationState@12@XZ; MkvMfSourceLib::MkvMfSource::StateAsyncGetNextBlockCluster(void)
0x180013b41  mov     [rsi+210h], rax
0x180013b48  mov     dword ptr [rsi+218h], 0
0x180013b52  mov     eax, dword ptr [rbp+var_10+4]
0x180013b55  mov     [rsi+21Ch], eax
0x180013b5b  lea     rdx, [rsi+1F0h]; struct IMFAsyncCallback *
0x180013b62  mov     rcx, rsi; this
0x180013b65  call    ?QueueOperation@MkvMfSource@MkvMfSourceLib@@AEAAJPEAUIMFAsyncCallback@@@Z; MkvMfSourceLib::MkvMfSource::QueueOperation(IMFAsyncCallback *)
0x180013b6a  nop
0x180013b6b  mov     ebx, edi
0x180013b6d  lea     rcx, [rbp+var_30]; this
0x180013b71  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180013b76  mov     eax, ebx
0x180013b78  jmp     short loc_180013BCD
0x180013b7a  mov     dword ptr [rsi+1E0h], 0
0x180013b84  lea     rax, ?StateAsyncGetNextBlockCluster@MkvMfSource@MkvMfSourceLib@@AEAA?AW4OperationState@12@XZ; MkvMfSourceLib::MkvMfSource::StateAsyncGetNextBlockCluster(void)
0x180013b8b  mov     [rsi+210h], rax
0x180013b92  mov     dword ptr [rsi+218h], 0
0x180013b9c  mov     eax, dword ptr [rbp+var_10+4]
0x180013b9f  mov     [rsi+21Ch], eax
0x180013ba5  lea     rdx, [rsi+1F0h]; struct IMFAsyncCallback *
0x180013bac  mov     rcx, rsi; this
0x180013baf  call    ?QueueOperation@MkvMfSource@MkvMfSourceLib@@AEAAJPEAUIMFAsyncCallback@@@Z; MkvMfSourceLib::MkvMfSource::QueueOperation(IMFAsyncCallback *)
0x180013bb4  nop
0x180013bb5  lea     rcx, [rbp+var_30]; this
0x180013bb9  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180013bbe  mov     eax, edi
0x180013bc0  jmp     short loc_180013BCD
0x180013bc2  lea     rcx, [rbp+var_30]; this
0x180013bc6  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180013bcb  xor     eax, eax
0x180013bcd  mov     rcx, [rbp+var_8]
0x180013bd1  xor     rcx, rsp; StackCookie
0x180013bd4  call    __security_check_cookie
0x180013bd9  lea     r11, [rsp+70h+var_s0]
0x180013bde  mov     rbx, [r11+30h]
0x180013be2  mov     rsi, [r11+38h]
0x180013be6  mov     rsp, r11
0x180013be9  pop     r14
0x180013beb  pop     rdi
0x180013bec  pop     rbp
0x180013bed  retn
```
