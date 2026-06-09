# mkvparser::ReadUInt(mkvparser::IMkvReader *,__int64,__int64 &,long &)

- ea: `0x1800ae378`
- end: `0x1800ae797`
- name: `?ReadUInt@mkvparser@@YAJPEAUIMkvReader@1@_JAEA_JAEAJ@Z`
- size: `1055`
- prototype: `__int64 __fastcall(mkvparser *__hidden this, struct mkvparser::IMkvReader *, __int64, __int64 *, int *)`
- caller_count: `25`
- callee_count: `7`
- tags: ``

## callers

- `0x180089abc`
- `0x18008a410`
- `0x18008ad30`
- `0x18008c320`
- `0x18008eef8`
- `0x1800905dc`
- `0x180091564`
- `0x180091b3c`
- `0x180091f68`
- `0x180092f5c`
- `0x180093bb4`
- `0x1800950f0`
- `0x180095a94`
- `0x180096d6c`
- `0x18009970c`
- `0x18009bd54`
- `0x18009f9d4`
- `0x1800a0088`
- `0x1800a24c8`
- `0x1800a51ec`
- `0x1800a5fec`
- `0x1800a79c4`
- `0x1800a8e30`
- `0x1800a9808`
- `0x1800aa9c0`

## callees

- `0x180009b04`
- `0x18000d554`
- `0x18000ddc0`
- `0x180021b9c`
- `0x1800744d8`
- `0x1800ae378`
- `0x1800b4010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ae3cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ae467`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ae530`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ae5ec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ae6ee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ae3cb`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ae467`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ae530`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ae5ec`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800ae6ee`

## string_xrefs

- `0x1800ae391`: `mkvparser::ReadUInt`

## pseudocode

```c
__int64 __fastcall mkvparser::ReadUInt(
        __int64 (__fastcall ***this)(mkvparser *, struct mkvparser::IMkvReader *, __int64, unsigned __int8 *),
        struct mkvparser::IMkvReader *a2,
        __int64 *a3,
        __int64 *a4)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r9
  __int64 *v11; // rcx
  CallStackTracing *v12; // rax
  int v13; // ebx
  struct CallStackContext *v14; // rax
  __int64 v15; // rdx
  __int64 *v16; // rcx
  CallStackTracing *v17; // rax
  struct CallStackContext *v18; // rax
  __int64 (__fastcall **v19)(mkvparser *, struct mkvparser::IMkvReader *, __int64, unsigned __int8 *); // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 *v23; // rcx
  CallStackTracing *v24; // rax
  struct CallStackContext *v25; // rax
  __int64 v26; // rdx
  __int64 *v27; // rcx
  CallStackTracing *v28; // rax
  struct CallStackContext *v29; // rax
  unsigned __int8 v30; // al
  int v31; // ecx
  int v32; // esi
  __int64 v33; // rcx
  char *i; // rdi
  __int64 v35; // rdx
  __int64 v36; // r8
  __int64 v37; // r9
  __int64 *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  _BYTE v42[16]; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int8 v43; // [rsp+70h] [rbp+8h] BYREF

  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)v42, "mkvparser::ReadUInt", 231);
  if ( this )
  {
    if ( (__int64)a2 >= 0 )
    {
      *(_DWORD *)a4 = 1;
      v19 = *this;
      v43 = 0;
      v13 = (*v19)((mkvparser *)this, a2, 1, &v43);
      if ( v13 >= 0 )
      {
        v26 = v43;
        if ( v43 )
        {
          v30 = 0x80;
          if ( (v43 & 0x80u) == 0 )
          {
            v31 = *(_DWORD *)a4;
            do
            {
              v30 >>= 1;
              ++v31;
            }
            while ( (v30 & v43) == 0 );
            *(_DWORD *)a4 = v31;
          }
          v32 = 1;
          v33 = v26 & ~v30;
          for ( i = (char *)a2 + 1; ; ++i )
          {
            *a3 = v33;
            if ( v32 >= *(_DWORD *)a4 )
            {
              v13 = 0;
              goto LABEL_65;
            }
            v13 = (**this)((mkvparser *)this, (struct mkvparser::IMkvReader *)i, 1, &v43);
            if ( v13 < 0 )
              break;
            v33 = v43 | (unsigned __int64)(*a3 << 8);
            ++v32;
          }
          v38 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v35, v36, v37);
            CallStackTracing::s_wpInstance = v39;
            if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
            {
              v38 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v38 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          if ( *((_BYTE *)v38 + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != v13 )
              CallStackContext::TraceFailure(ThreadRelativeContext, "mkvparser::ReadUInt", 259, v13);
          }
          if ( g_wppLevels )
          {
            v15 = 14;
            goto LABEL_34;
          }
        }
        else
        {
          v27 = (__int64 *)CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v28 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v43, v21, v22);
            CallStackTracing::s_wpInstance = v28;
            if ( v28 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v28 + 8LL))(v28, 2032) )
            {
              v27 = (__int64 *)CallStackTracing::s_wpInstance;
            }
            else
            {
              v27 = &qword_1800DBF70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
            }
          }
          v13 = -1072875842;
          if ( *((_BYTE *)v27 + 8) )
          {
            v29 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v27);
            if ( *((_DWORD *)v29 + 499) != -1072875842 )
              CallStackContext::TraceFailure(v29, "mkvparser::ReadUInt", 245, -1072875842);
          }
          if ( g_wppLevels )
          {
            v15 = 13;
            goto LABEL_34;
          }
        }
      }
      else
      {
        v23 = (__int64 *)CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v24 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v20, v21, v22);
          CallStackTracing::s_wpInstance = v24;
          if ( v24 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v24 + 8LL))(v24, 2032) )
          {
            v23 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v23 = &qword_1800DBF70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
          }
        }
        if ( *((_BYTE *)v23 + 8) )
        {
          v25 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v23);
          if ( *((_DWORD *)v25 + 499) != v13 )
            CallStackContext::TraceFailure(v25, "mkvparser::ReadUInt", 241, v13);
        }
        if ( g_wppLevels )
        {
          v15 = 12;
          goto LABEL_34;
        }
      }
    }
    else
    {
      v16 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v17 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v9, v10);
        CallStackTracing::s_wpInstance = v17;
        if ( v17 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v17 + 8LL))(v17, 2032) )
        {
          v16 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v16 = &qword_1800DBF70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
        }
      }
      v13 = -2147024809;
      if ( *((_BYTE *)v16 + 8) )
      {
        v18 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v16);
        if ( *((_DWORD *)v18 + 499) != -2147024809 )
          CallStackContext::TraceFailure(v18, "mkvparser::ReadUInt", 235, -2147024809);
      }
      if ( g_wppLevels )
      {
        v15 = 11;
        goto LABEL_34;
      }
    }
  }
  else
  {
    v11 = (__int64 *)CallStackTracing::s_wpInstance;
    if ( !CallStackTracing::s_wpInstance )
    {
      v12 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v8, v9, v10);
      CallStackTracing::s_wpInstance = v12;
      if ( v12 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v12 + 8LL))(v12, 2032) )
      {
        v11 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_1800DBF70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800DBF70;
      }
    }
    v13 = -2147024809;
    if ( *((_BYTE *)v11 + 8) )
    {
      v14 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)v14 + 499) != -2147024809 )
        CallStackContext::TraceFailure(v14, "mkvparser::ReadUInt", 231, -2147024809);
    }
    if ( g_wppLevels )
    {
      v15 = 10;
LABEL_34:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids, 0, v13);
    }
  }
LABEL_65:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v42);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800ae378  mov     [rsp+arg_8], rbx
0x1800ae37d  mov     [rsp+arg_10], rbp
0x1800ae382  push    rsi
0x1800ae383  push    rdi
0x1800ae384  push    r13
0x1800ae386  push    r14
0x1800ae388  push    r15
0x1800ae38a  sub     rsp, 40h
0x1800ae38e  mov     r15, r8
0x1800ae391  lea     r13, aMkvparserReadu; "mkvparser::ReadUInt"
0x1800ae398  mov     rdi, rdx
0x1800ae39b  mov     rbp, rcx
0x1800ae39e  mov     esi, 0E7h
0x1800ae3a3  lea     rcx, [rsp+68h+var_38]; this
0x1800ae3a8  mov     r8d, esi; int
0x1800ae3ab  mov     rdx, r13; char *
0x1800ae3ae  mov     r14, r9
0x1800ae3b1  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800ae3b6  test    rbp, rbp
0x1800ae3b9  jnz     loc_1800AE452
0x1800ae3bf  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae3c6  test    rcx, rcx
0x1800ae3c9  jnz     short loc_1800AE412
0x1800ae3cb  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ae3d2  nop     dword ptr [rax+rax+00h]
0x1800ae3d7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae3de  mov     rcx, rax
0x1800ae3e1  test    rax, rax
0x1800ae3e4  jz      short loc_1800AE404
0x1800ae3e6  mov     rax, [rax]
0x1800ae3e9  mov     edx, 7F0h
0x1800ae3ee  mov     rax, [rax+8]
0x1800ae3f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae3f7  test    eax, eax
0x1800ae3f9  jz      short loc_1800AE404
0x1800ae3fb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae402  jmp     short loc_1800AE412
0x1800ae404  lea     rcx, qword_1800DBF70; this
0x1800ae40b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae412  cmp     byte ptr [rcx+8], 0
0x1800ae416  mov     ebx, 80070057h
0x1800ae41b  jz      short loc_1800AE43B
0x1800ae41d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ae422  cmp     [rax+7CCh], ebx
0x1800ae428  jz      short loc_1800AE43B
0x1800ae42a  mov     r9d, ebx; int
0x1800ae42d  mov     r8d, esi; int
0x1800ae430  mov     rdx, r13; char *
0x1800ae433  mov     rcx, rax; this
0x1800ae436  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ae43b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ae442  jb      loc_1800AE771
0x1800ae448  mov     edx, 0Ah
0x1800ae44d  jmp     loc_1800AE5B0
0x1800ae452  test    rdi, rdi
0x1800ae455  jns     loc_1800AE4F1
0x1800ae45b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae462  test    rcx, rcx
0x1800ae465  jnz     short loc_1800AE4AE
0x1800ae467  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ae46e  nop     dword ptr [rax+rax+00h]
0x1800ae473  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae47a  mov     rcx, rax
0x1800ae47d  test    rax, rax
0x1800ae480  jz      short loc_1800AE4A0
0x1800ae482  mov     rax, [rax]
0x1800ae485  mov     edx, 7F0h
0x1800ae48a  mov     rax, [rax+8]
0x1800ae48e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae493  test    eax, eax
0x1800ae495  jz      short loc_1800AE4A0
0x1800ae497  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae49e  jmp     short loc_1800AE4AE
0x1800ae4a0  lea     rcx, qword_1800DBF70; this
0x1800ae4a7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae4ae  cmp     byte ptr [rcx+8], 0
0x1800ae4b2  mov     ebx, 80070057h
0x1800ae4b7  jz      short loc_1800AE4DA
0x1800ae4b9  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ae4be  cmp     [rax+7CCh], ebx
0x1800ae4c4  jz      short loc_1800AE4DA
0x1800ae4c6  mov     r9d, ebx; int
0x1800ae4c9  mov     r8d, 0EBh; int
0x1800ae4cf  mov     rdx, r13; char *
0x1800ae4d2  mov     rcx, rax; this
0x1800ae4d5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ae4da  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ae4e1  jb      loc_1800AE771
0x1800ae4e7  mov     edx, 0Bh
0x1800ae4ec  jmp     loc_1800AE5B0
0x1800ae4f1  mov     dword ptr [r14], 1
0x1800ae4f8  lea     r9, [rsp+68h+arg_0]
0x1800ae4fd  mov     rax, [rbp+0]
0x1800ae501  mov     r8d, 1
0x1800ae507  mov     rdx, rdi
0x1800ae50a  mov     [rsp+68h+arg_0], 0
0x1800ae50f  mov     rcx, rbp
0x1800ae512  mov     rax, [rax]
0x1800ae515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae51a  mov     ebx, eax
0x1800ae51c  test    eax, eax
0x1800ae51e  jns     loc_1800AE5D3
0x1800ae524  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae52b  test    rcx, rcx
0x1800ae52e  jnz     short loc_1800AE577
0x1800ae530  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ae537  nop     dword ptr [rax+rax+00h]
0x1800ae53c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae543  mov     rcx, rax
0x1800ae546  test    rax, rax
0x1800ae549  jz      short loc_1800AE569
0x1800ae54b  mov     rax, [rax]
0x1800ae54e  mov     edx, 7F0h
0x1800ae553  mov     rax, [rax+8]
0x1800ae557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae55c  test    eax, eax
0x1800ae55e  jz      short loc_1800AE569
0x1800ae560  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae567  jmp     short loc_1800AE577
0x1800ae569  lea     rcx, qword_1800DBF70; this
0x1800ae570  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae577  cmp     byte ptr [rcx+8], 0
0x1800ae57b  jz      short loc_1800AE59E
0x1800ae57d  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ae582  cmp     [rax+7CCh], ebx
0x1800ae588  jz      short loc_1800AE59E
0x1800ae58a  mov     r9d, ebx; int
0x1800ae58d  mov     r8d, 0F1h; int
0x1800ae593  mov     rdx, r13; char *
0x1800ae596  mov     rcx, rax; this
0x1800ae599  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ae59e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ae5a5  jb      loc_1800AE771
0x1800ae5ab  mov     edx, 0Ch
0x1800ae5b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae5b7  lea     r8, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids
0x1800ae5be  xor     r9d, r9d
0x1800ae5c1  mov     [rsp+68h+var_48], ebx
0x1800ae5c5  mov     rcx, [rcx+10h]
0x1800ae5c9  call    WPP_SF_qD
0x1800ae5ce  jmp     loc_1800AE771
0x1800ae5d3  movzx   edx, [rsp+68h+arg_0]
0x1800ae5d8  test    dl, dl
0x1800ae5da  jnz     loc_1800AE676
0x1800ae5e0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae5e7  test    rcx, rcx
0x1800ae5ea  jnz     short loc_1800AE633
0x1800ae5ec  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ae5f3  nop     dword ptr [rax+rax+00h]
0x1800ae5f8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae5ff  mov     rcx, rax
0x1800ae602  test    rax, rax
0x1800ae605  jz      short loc_1800AE625
0x1800ae607  mov     rax, [rax]
0x1800ae60a  mov     edx, 7F0h
0x1800ae60f  mov     rax, [rax+8]
0x1800ae613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae618  test    eax, eax
0x1800ae61a  jz      short loc_1800AE625
0x1800ae61c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae623  jmp     short loc_1800AE633
0x1800ae625  lea     rcx, qword_1800DBF70; this
0x1800ae62c  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae633  cmp     byte ptr [rcx+8], 0
0x1800ae637  mov     ebx, 0C00D36BEh
0x1800ae63c  jz      short loc_1800AE65F
0x1800ae63e  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ae643  cmp     [rax+7CCh], ebx
0x1800ae649  jz      short loc_1800AE65F
0x1800ae64b  mov     r9d, ebx; int
0x1800ae64e  mov     r8d, 0F5h; int
0x1800ae654  mov     rdx, r13; char *
0x1800ae657  mov     rcx, rax; this
0x1800ae65a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ae65f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ae666  jb      loc_1800AE771
0x1800ae66c  mov     edx, 0Dh
0x1800ae671  jmp     loc_1800AE5B0
0x1800ae676  mov     al, 80h
0x1800ae678  test    al, dl
0x1800ae67a  jnz     short loc_1800AE68A
0x1800ae67c  mov     ecx, [r14]
0x1800ae67f  shr     al, 1
0x1800ae681  inc     ecx
0x1800ae683  test    dl, al
0x1800ae685  jz      short loc_1800AE67F
0x1800ae687  mov     [r14], ecx
0x1800ae68a  movzx   eax, al
0x1800ae68d  mov     esi, 1
0x1800ae692  not     eax
0x1800ae694  movsxd  rcx, eax
0x1800ae697  and     rcx, rdx
0x1800ae69a  inc     rdi
0x1800ae69d  mov     [r15], rcx
0x1800ae6a0  cmp     esi, [r14]
0x1800ae6a3  jge     loc_1800AE76F
0x1800ae6a9  mov     rax, [rbp+0]
0x1800ae6ad  lea     r9, [rsp+68h+arg_0]
0x1800ae6b2  mov     r8d, 1
0x1800ae6b8  mov     rdx, rdi
0x1800ae6bb  mov     rcx, rbp
0x1800ae6be  mov     rax, [rax]
0x1800ae6c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae6c6  mov     ebx, eax
0x1800ae6c8  test    eax, eax
0x1800ae6ca  js      short loc_1800AE6E2
0x1800ae6cc  mov     rcx, [r15]
0x1800ae6cf  inc     rdi
0x1800ae6d2  movzx   eax, [rsp+68h+arg_0]
0x1800ae6d7  shl     rcx, 8
0x1800ae6db  or      rcx, rax
0x1800ae6de  inc     esi
0x1800ae6e0  jmp     short loc_1800AE69D
0x1800ae6e2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae6e9  test    rcx, rcx
0x1800ae6ec  jnz     short loc_1800AE735
0x1800ae6ee  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800ae6f5  nop     dword ptr [rax+rax+00h]
0x1800ae6fa  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae701  mov     rcx, rax
0x1800ae704  test    rax, rax
0x1800ae707  jz      short loc_1800AE727
0x1800ae709  mov     rax, [rax]
0x1800ae70c  mov     edx, 7F0h
0x1800ae711  mov     rax, [rax+8]
0x1800ae715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae71a  test    eax, eax
0x1800ae71c  jz      short loc_1800AE727
0x1800ae71e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae725  jmp     short loc_1800AE735
0x1800ae727  lea     rcx, qword_1800DBF70; this
0x1800ae72e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800ae735  cmp     byte ptr [rcx+8], 0
0x1800ae739  jz      short loc_1800AE75C
0x1800ae73b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800ae740  cmp     [rax+7CCh], ebx
0x1800ae746  jz      short loc_1800AE75C
0x1800ae748  mov     r9d, ebx; int
0x1800ae74b  mov     r8d, 103h; int
0x1800ae751  mov     rdx, r13; char *
0x1800ae754  mov     rcx, rax; this
0x1800ae757  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800ae75c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800ae763  jb      short loc_1800AE771
0x1800ae765  mov     edx, 0Eh
0x1800ae76a  jmp     loc_1800AE5B0
0x1800ae76f  xor     ebx, ebx
0x1800ae771  lea     rcx, [rsp+68h+var_38]; this
0x1800ae776  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800ae77b  lea     r11, [rsp+68h+var_28]
0x1800ae780  mov     eax, ebx
0x1800ae782  mov     rbx, [r11+38h]
0x1800ae786  mov     rbp, [r11+40h]
0x1800ae78a  mov     rsp, r11
0x1800ae78d  pop     r15
0x1800ae78f  pop     r14
0x1800ae791  pop     r13
0x1800ae793  pop     rdi
0x1800ae794  pop     rsi
0x1800ae795  retn
```
