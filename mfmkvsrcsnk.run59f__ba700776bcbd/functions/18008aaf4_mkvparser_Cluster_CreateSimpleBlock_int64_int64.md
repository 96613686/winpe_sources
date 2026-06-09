# mkvparser::Cluster::CreateSimpleBlock(__int64,__int64)

- ea: `0x18008aaf4`
- end: `0x18008ad27`
- name: `?CreateSimpleBlock@Cluster@mkvparser@@AEAAJ_J0@Z`
- size: `563`
- prototype: `__int64 __fastcall(mkvparser::Cluster *__hidden this, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800895cc`

## callees

- `0x180002430`
- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800744d8`
- `0x18008aaf4`
- `0x180096d6c`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008aba1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008ac6c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008aba1`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18008ac6c`

## string_xrefs

- `0x18008ab71`: `mkvparser::Cluster::CreateSimpleBlock`

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
    v15 = mkvparser::Block::Parse((mkvparser::Block *)(v12 + 24), *(const struct Cluster **)(v12 + 8));
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
        v22 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
        v13 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
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
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids, this, v15);
    }
  }
LABEL_29:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v26);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18008aaf4  push    rbx
0x18008aaf6  push    rbp
0x18008aaf7  push    rsi
0x18008aaf8  push    rdi
0x18008aaf9  push    r14
0x18008aafb  push    r15
0x18008aafd  sub     rsp, 38h
0x18008ab01  movsxd  rbx, dword ptr [rcx+3Ch]
0x18008ab05  mov     r15, rdx
0x18008ab08  mov     r14, [rcx+30h]
0x18008ab0c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008ab13  mov     rdi, rcx
0x18008ab16  mov     rsi, rbx
0x18008ab19  mov     ecx, 50h ; 'P'; unsigned __int64
0x18008ab1e  mov     rbp, r8
0x18008ab21  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18008ab26  test    rax, rax
0x18008ab29  jz      short loc_18008AB67
0x18008ab2b  mov     [rax+8], rdi
0x18008ab2f  lea     rcx, ??_7SimpleBlock@mkvparser@@6B@; const mkvparser::SimpleBlock::`vftable'
0x18008ab36  mov     [rax], rcx
0x18008ab39  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18008ab3d  mov     [rax+10h], ebx
0x18008ab40  mov     [rax+28h], rcx
0x18008ab44  mov     [rax+30h], cx
0x18008ab48  mov     [rax+40h], ecx
0x18008ab4b  mov     [rax+18h], r15
0x18008ab4f  mov     [rax+20h], rbp
0x18008ab53  mov     byte ptr [rax+32h], 0
0x18008ab57  mov     qword ptr [rax+38h], 0
0x18008ab5f  mov     qword ptr [rax+48h], 0
0x18008ab67  mov     r15d, 1F81h
0x18008ab6d  mov     [r14+rbx*8], rax
0x18008ab71  lea     rbp, aMkvparserClust_4; "mkvparser::Cluster::CreateSimpleBlock"
0x18008ab78  mov     r8d, r15d; int
0x18008ab7b  mov     rdx, rbp; char *
0x18008ab7e  lea     rcx, [rsp+68h+arg_0]; this
0x18008ab83  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18008ab88  mov     rdx, [r14+rbx*8]
0x18008ab8c  test    rdx, rdx
0x18008ab8f  jnz     loc_18008AC28
0x18008ab95  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008ab9c  test    rcx, rcx
0x18008ab9f  jnz     short loc_18008ABE8
0x18008aba1  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008aba8  nop     dword ptr [rax+rax+00h]
0x18008abad  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008abb4  mov     rcx, rax
0x18008abb7  test    rax, rax
0x18008abba  jz      short loc_18008ABDA
0x18008abbc  mov     rax, [rax]
0x18008abbf  mov     edx, 7F0h
0x18008abc4  mov     rax, [rax+8]
0x18008abc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008abcd  test    eax, eax
0x18008abcf  jz      short loc_18008ABDA
0x18008abd1  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008abd8  jmp     short loc_18008ABE8
0x18008abda  lea     rcx, qword_1800DBF70; this
0x18008abe1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008abe8  cmp     byte ptr [rcx+8], 0
0x18008abec  mov     ebx, 8007000Eh
0x18008abf1  jz      short loc_18008AC11
0x18008abf3  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008abf8  cmp     [rax+7CCh], ebx
0x18008abfe  jz      short loc_18008AC11
0x18008ac00  mov     r9d, ebx; int
0x18008ac03  mov     r8d, r15d; int
0x18008ac06  mov     rdx, rbp; char *
0x18008ac09  mov     rcx, rax; this
0x18008ac0c  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008ac11  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008ac18  jb      loc_18008AD0D
0x18008ac1e  mov     edx, 2DAh
0x18008ac23  jmp     loc_18008ACE8
0x18008ac28  lea     rcx, [rdx+18h]; this
0x18008ac2c  mov     rdx, [rdx+8]; struct Cluster *
0x18008ac30  call    ?Parse@Block@mkvparser@@QEAAJPEBVCluster@2@@Z; mkvparser::Block::Parse(mkvparser::Cluster const *)
0x18008ac35  mov     ebx, eax
0x18008ac37  test    eax, eax
0x18008ac39  jns     loc_18008AD08
0x18008ac3f  mov     rcx, [r14+rsi*8]
0x18008ac43  test    rcx, rcx
0x18008ac46  jz      short loc_18008AC58
0x18008ac48  mov     rdx, [rcx]
0x18008ac4b  mov     rax, [rdx]
0x18008ac4e  mov     edx, 1
0x18008ac53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ac58  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008ac5f  mov     qword ptr [r14+rsi*8], 0
0x18008ac67  test    rcx, rcx
0x18008ac6a  jnz     short loc_18008ACB3
0x18008ac6c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18008ac73  nop     dword ptr [rax+rax+00h]
0x18008ac78  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18008ac7f  mov     rcx, rax
0x18008ac82  test    rax, rax
0x18008ac85  jz      short loc_18008ACA5
0x18008ac87  mov     rax, [rax]
0x18008ac8a  mov     edx, 7F0h
0x18008ac8f  mov     rax, [rax+8]
0x18008ac93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ac98  test    eax, eax
0x18008ac9a  jz      short loc_18008ACA5
0x18008ac9c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18008aca3  jmp     short loc_18008ACB3
0x18008aca5  lea     rcx, qword_1800DBF70; this
0x18008acac  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18008acb3  cmp     byte ptr [rcx+8], 0
0x18008acb7  jz      short loc_18008ACDA
0x18008acb9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18008acbe  cmp     [rax+7CCh], ebx
0x18008acc4  jz      short loc_18008ACDA
0x18008acc6  mov     r9d, ebx; int
0x18008acc9  mov     r8d, 1F89h; int
0x18008accf  mov     rdx, rbp; char *
0x18008acd2  mov     rcx, rax; this
0x18008acd5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18008acda  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18008ace1  jb      short loc_18008AD0D
0x18008ace3  mov     edx, 2DBh
0x18008ace8  mov     rcx, cs:WPP_GLOBAL_Control
0x18008acef  lea     r8, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids
0x18008acf6  mov     r9, rdi
0x18008acf9  mov     [rsp+68h+var_48], ebx
0x18008acfd  mov     rcx, [rcx+10h]
0x18008ad01  call    WPP_SF_qD
0x18008ad06  jmp     short loc_18008AD0D
0x18008ad08  inc     dword ptr [rdi+3Ch]
0x18008ad0b  xor     ebx, ebx
0x18008ad0d  lea     rcx, [rsp+68h+arg_0]; this
0x18008ad12  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18008ad17  mov     eax, ebx
0x18008ad19  add     rsp, 38h
0x18008ad1d  pop     r15
0x18008ad1f  pop     r14
0x18008ad21  pop     rdi
0x18008ad22  pop     rsi
0x18008ad23  pop     rbp
0x18008ad24  pop     rbx
0x18008ad25  retn
```
