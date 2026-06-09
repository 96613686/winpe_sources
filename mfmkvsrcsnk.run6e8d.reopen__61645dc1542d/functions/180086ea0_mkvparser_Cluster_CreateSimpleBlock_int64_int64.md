# mkvparser::Cluster::CreateSimpleBlock(__int64,__int64)

- ea: `0x180086ea0`
- end: `0x1800870c6`
- name: `?CreateSimpleBlock@Cluster@mkvparser@@AEAAJ_J0@Z`
- size: `550`
- prototype: `__int64 __fastcall(mkvparser::Cluster *__hidden this, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180085a08`

## callees

- `0x180002410`
- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180071330`
- `0x180086ea0`
- `0x180092bac`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086f4d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180087012`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180086f4d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180087012`

## string_xrefs

- `0x180086f1d`: `mkvparser::Cluster::CreateSimpleBlock`

## pseudocode

```c
__int64 __fastcall mkvparser::Cluster::CreateSimpleBlock(mkvparser::Cluster *this, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  __int64 v5; // r14
  __int64 v7; // rsi
  _QWORD *v9; // rax
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rdx
  __int64 *v13; // rcx
  CallStackTracing *v14; // rax
  int v15; // ebx
  struct CallStackContext *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  void (__fastcall ***v21)(_QWORD, __int64); // rcx
  __int64 *v22; // rcx
  CallStackTracing *v23; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  char v26; // [rsp+70h] [rbp+8h] BYREF

  v3 = *((int *)this + 15);
  v5 = *((_QWORD *)this + 6);
  v7 = v3;
  v9 = operator new(0x50u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v9 )
  {
    v9[1] = this;
    *v9 = &mkvparser::SimpleBlock::`vftable';
    *((_DWORD *)v9 + 4) = v3;
    v9[5] = -1;
    *((_WORD *)v9 + 24) = -1;
    *((_DWORD *)v9 + 16) = -1;
    v9[3] = a2;
    v9[4] = a3;
    *((_BYTE *)v9 + 50) = 0;
    v9[7] = 0;
    v9[9] = 0;
  }
  *(_QWORD *)(v5 + 8 * v3) = v9;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v26, "mkvparser::Cluster::CreateSimpleBlock", 8065);
  v12 = *(_QWORD *)(v5 + 8 * v3);
  if ( v12 )
  {
    v15 = mkvparser::Block::Parse((mkvparser::Block *)(v12 + 24), *(mkvparser ****)(v12 + 8));
    if ( v15 >= 0 )
    {
      ++*((_DWORD *)this + 15);
      v15 = 0;
      goto LABEL_29;
    }
    v21 = *(void (__fastcall ****)(_QWORD, __int64))(v5 + 8 * v7);
    if ( v21 )
      (**v21)(v21, 1);
    v22 = (__int64 *)CallStackTracing::s_wpInstance;
    *(_QWORD *)(v5 + 8 * v7) = 0;
    if ( !v22 )
    {
      v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v18, v19, v20);
      CallStackTracing::s_wpInstance = v23;
      if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
      {
        v22 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v22 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    if ( *((_BYTE *)v22 + 8) )
    {
      ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v22);
      if ( *((_DWORD *)ThreadRelativeContext + 499) != v15 )
        CallStackContext::TraceFailure(ThreadRelativeContext, "mkvparser::Cluster::CreateSimpleBlock", 8073, v15);
    }
    if ( g_wppLevels )
    {
      v17 = 731;
      goto LABEL_27;
    }
  }
  else
  {
    v13 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v14 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, 0, v10, v11);
      CallStackTracing::s_wpInstance = v14;
      if ( v14 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v14 + 8LL))(v14, 2032) )
      {
        v13 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v13 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
      }
    }
    v15 = -2147024882;
    if ( *((_BYTE *)v13 + 8) )
    {
      v16 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v13);
      if ( *((_DWORD *)v16 + 499) != -2147024882 )
        CallStackContext::TraceFailure(v16, "mkvparser::Cluster::CreateSimpleBlock", 8065, -2147024882);
    }
    if ( g_wppLevels )
    {
      v17 = 730;
LABEL_27:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids, this, v15);
    }
  }
LABEL_29:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v26);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180086ea0  push    rbx
0x180086ea2  push    rbp
0x180086ea3  push    rsi
0x180086ea4  push    rdi
0x180086ea5  push    r14
0x180086ea7  push    r15
0x180086ea9  sub     rsp, 38h
0x180086ead  movsxd  rbx, dword ptr [rcx+3Ch]
0x180086eb1  mov     r15, rdx
0x180086eb4  mov     r14, [rcx+30h]
0x180086eb8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180086ebf  mov     rdi, rcx
0x180086ec2  mov     rsi, rbx
0x180086ec5  mov     ecx, 50h ; 'P'; unsigned __int64
0x180086eca  mov     rbp, r8
0x180086ecd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180086ed2  test    rax, rax
0x180086ed5  jz      short loc_180086F13
0x180086ed7  mov     [rax+8], rdi
0x180086edb  lea     rcx, ??_7SimpleBlock@mkvparser@@6B@; const mkvparser::SimpleBlock::`vftable'
0x180086ee2  mov     [rax], rcx
0x180086ee5  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180086ee9  mov     [rax+10h], ebx
0x180086eec  mov     [rax+28h], rcx
0x180086ef0  mov     [rax+30h], cx
0x180086ef4  mov     [rax+40h], ecx
0x180086ef7  mov     [rax+18h], r15
0x180086efb  mov     [rax+20h], rbp
0x180086eff  mov     byte ptr [rax+32h], 0
0x180086f03  mov     qword ptr [rax+38h], 0
0x180086f0b  mov     qword ptr [rax+48h], 0
0x180086f13  mov     r15d, 1F81h
0x180086f19  mov     [r14+rbx*8], rax
0x180086f1d  lea     rbp, aMkvparserClust_4; "mkvparser::Cluster::CreateSimpleBlock"
0x180086f24  mov     r8d, r15d; int
0x180086f27  mov     rdx, rbp; char *
0x180086f2a  lea     rcx, [rsp+68h+arg_0]; this
0x180086f2f  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180086f34  mov     rdx, [r14+rbx*8]
0x180086f38  test    rdx, rdx
0x180086f3b  jnz     loc_180086FCE
0x180086f41  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180086f48  test    rcx, rcx
0x180086f4b  jnz     short loc_180086F8E
0x180086f4d  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180086f53  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180086f5a  mov     rcx, rax
0x180086f5d  test    rax, rax
0x180086f60  jz      short loc_180086F80
0x180086f62  mov     rax, [rax]
0x180086f65  mov     edx, 7F0h
0x180086f6a  mov     rax, [rax+8]
0x180086f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086f73  test    eax, eax
0x180086f75  jz      short loc_180086F80
0x180086f77  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180086f7e  jmp     short loc_180086F8E
0x180086f80  lea     rcx, qword_1800D6F70; this
0x180086f87  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180086f8e  cmp     byte ptr [rcx+8], 0
0x180086f92  mov     ebx, 8007000Eh
0x180086f97  jz      short loc_180086FB7
0x180086f99  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180086f9e  cmp     [rax+7CCh], ebx
0x180086fa4  jz      short loc_180086FB7
0x180086fa6  mov     r9d, ebx; int
0x180086fa9  mov     r8d, r15d; int
0x180086fac  mov     rdx, rbp; char *
0x180086faf  mov     rcx, rax; this
0x180086fb2  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180086fb7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180086fbe  jb      loc_1800870AD
0x180086fc4  mov     edx, 2DAh
0x180086fc9  jmp     loc_180087088
0x180086fce  lea     rcx, [rdx+18h]; this
0x180086fd2  mov     rdx, [rdx+8]; struct Cluster *
0x180086fd6  call    ?Parse@Block@mkvparser@@QEAAJPEBVCluster@2@@Z; mkvparser::Block::Parse(mkvparser::Cluster const *)
0x180086fdb  mov     ebx, eax
0x180086fdd  test    eax, eax
0x180086fdf  jns     loc_1800870A8
0x180086fe5  mov     rcx, [r14+rsi*8]
0x180086fe9  test    rcx, rcx
0x180086fec  jz      short loc_180086FFE
0x180086fee  mov     rdx, [rcx]
0x180086ff1  mov     rax, [rdx]
0x180086ff4  mov     edx, 1
0x180086ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086ffe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180087005  mov     qword ptr [r14+rsi*8], 0
0x18008700d  test    rcx, rcx
0x180087010  jnz     short loc_180087053
0x180087012  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180087018  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008701f  mov     rcx, rax
0x180087022  test    rax, rax
0x180087025  jz      short loc_180087045
0x180087027  mov     rax, [rax]
0x18008702a  mov     edx, 7F0h
0x18008702f  mov     rax, [rax+8]
0x180087033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087038  test    eax, eax
0x18008703a  jz      short loc_180087045
0x18008703c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180087043  jmp     short loc_180087053
0x180087045  lea     rcx, qword_1800D6F70; this
0x18008704c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180087053  cmp     byte ptr [rcx+8], 0
0x180087057  jz      short loc_18008707A
0x180087059  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008705e  cmp     [rax+7CCh], ebx
0x180087064  jz      short loc_18008707A
0x180087066  mov     r9d, ebx; int
0x180087069  mov     r8d, 1F89h; int
0x18008706f  mov     rdx, rbp; char *
0x180087072  mov     rcx, rax; this
0x180087075  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008707a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180087081  jb      short loc_1800870AD
0x180087083  mov     edx, 2DBh
0x180087088  mov     rcx, cs:WPP_GLOBAL_Control
0x18008708f  lea     r8, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids
0x180087096  mov     r9, rdi
0x180087099  mov     [rsp+68h+var_48], ebx
0x18008709d  mov     rcx, [rcx+10h]
0x1800870a1  call    WPP_SF_qD
0x1800870a6  jmp     short loc_1800870AD
0x1800870a8  inc     dword ptr [rdi+3Ch]
0x1800870ab  xor     ebx, ebx
0x1800870ad  lea     rcx, [rsp+68h+arg_0]; this
0x1800870b2  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800870b7  mov     eax, ebx
0x1800870b9  add     rsp, 38h
0x1800870bd  pop     r15
0x1800870bf  pop     r14
0x1800870c1  pop     rdi
0x1800870c2  pop     rsi
0x1800870c3  pop     rbp
0x1800870c4  pop     rbx
0x1800870c5  retn
```
