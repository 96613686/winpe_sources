# mkvparser::ReadUInt(mkvparser::IMkvReader *,__int64,__int64 &,long &)

- ea: `0x1800a96cc`
- end: `0x1800a9acc`
- name: `?ReadUInt@mkvparser@@YAJPEAUIMkvReader@1@_JAEA_JAEAJ@Z`
- size: `1024`
- prototype: `__int64 __fastcall(mkvparser *__hidden this, struct mkvparser::IMkvReader *, __int64, __int64 *, int *)`
- caller_count: `25`
- callee_count: `7`
- tags: ``

## callers

- `0x180085edc`
- `0x1800867f0`
- `0x1800870cc`
- `0x180088614`
- `0x18008b0dc`
- `0x18008c718`
- `0x18008d628`
- `0x18008dbd4`
- `0x18008dfe0`
- `0x18008ef54`
- `0x18008fb48`
- `0x180090ff8`
- `0x180091950`
- `0x180092bac`
- `0x1800953f4`
- `0x180097920`
- `0x18009b3e4`
- `0x18009ba68`
- `0x18009dd9c`
- `0x1800a0978`
- `0x1800a1710`
- `0x1800a3018`
- `0x1800a43f4`
- `0x1800a4d84`
- `0x1800a5eb4`

## callees

- `0x1800097f0`
- `0x18000cfb4`
- `0x18000d7cc`
- `0x180020d84`
- `0x180071330`
- `0x1800a96cc`
- `0x1800af010`

## import_xrefs

- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a971f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a97b5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9878`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a992e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9a2a`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a971f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a97b5`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9878`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a992e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800a9a2a`

## string_xrefs

- `0x1800a96e5`: `mkvparser::ReadUInt`

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
              v38 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
              v27 = &qword_1800D6F70;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
            v23 = &qword_1800D6F70;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
          v16 = &qword_1800D6F70;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
        v11 = &qword_1800D6F70;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800D6F70;
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
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids, 0, v13);
    }
  }
LABEL_65:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v42);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800a96cc  mov     [rsp+arg_8], rbx
0x1800a96d1  mov     [rsp+arg_10], rbp
0x1800a96d6  push    rsi
0x1800a96d7  push    rdi
0x1800a96d8  push    r13
0x1800a96da  push    r14
0x1800a96dc  push    r15
0x1800a96de  sub     rsp, 40h
0x1800a96e2  mov     r15, r8
0x1800a96e5  lea     r13, aMkvparserReadu; "mkvparser::ReadUInt"
0x1800a96ec  mov     rdi, rdx
0x1800a96ef  mov     rbp, rcx
0x1800a96f2  mov     esi, 0E7h
0x1800a96f7  lea     rcx, [rsp+68h+var_38]; this
0x1800a96fc  mov     r8d, esi; int
0x1800a96ff  mov     rdx, r13; char *
0x1800a9702  mov     r14, r9
0x1800a9705  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800a970a  test    rbp, rbp
0x1800a970d  jnz     loc_1800A97A0
0x1800a9713  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a971a  test    rcx, rcx
0x1800a971d  jnz     short loc_1800A9760
0x1800a971f  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a9725  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a972c  mov     rcx, rax
0x1800a972f  test    rax, rax
0x1800a9732  jz      short loc_1800A9752
0x1800a9734  mov     rax, [rax]
0x1800a9737  mov     edx, 7F0h
0x1800a973c  mov     rax, [rax+8]
0x1800a9740  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9745  test    eax, eax
0x1800a9747  jz      short loc_1800A9752
0x1800a9749  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9750  jmp     short loc_1800A9760
0x1800a9752  lea     rcx, qword_1800D6F70; this
0x1800a9759  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9760  cmp     byte ptr [rcx+8], 0
0x1800a9764  mov     ebx, 80070057h
0x1800a9769  jz      short loc_1800A9789
0x1800a976b  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a9770  cmp     [rax+7CCh], ebx
0x1800a9776  jz      short loc_1800A9789
0x1800a9778  mov     r9d, ebx; int
0x1800a977b  mov     r8d, esi; int
0x1800a977e  mov     rdx, r13; char *
0x1800a9781  mov     rcx, rax; this
0x1800a9784  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a9789  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a9790  jb      loc_1800A9AA7
0x1800a9796  mov     edx, 0Ah
0x1800a979b  jmp     loc_1800A98F2
0x1800a97a0  test    rdi, rdi
0x1800a97a3  jns     loc_1800A9839
0x1800a97a9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a97b0  test    rcx, rcx
0x1800a97b3  jnz     short loc_1800A97F6
0x1800a97b5  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a97bb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a97c2  mov     rcx, rax
0x1800a97c5  test    rax, rax
0x1800a97c8  jz      short loc_1800A97E8
0x1800a97ca  mov     rax, [rax]
0x1800a97cd  mov     edx, 7F0h
0x1800a97d2  mov     rax, [rax+8]
0x1800a97d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a97db  test    eax, eax
0x1800a97dd  jz      short loc_1800A97E8
0x1800a97df  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a97e6  jmp     short loc_1800A97F6
0x1800a97e8  lea     rcx, qword_1800D6F70; this
0x1800a97ef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a97f6  cmp     byte ptr [rcx+8], 0
0x1800a97fa  mov     ebx, 80070057h
0x1800a97ff  jz      short loc_1800A9822
0x1800a9801  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a9806  cmp     [rax+7CCh], ebx
0x1800a980c  jz      short loc_1800A9822
0x1800a980e  mov     r9d, ebx; int
0x1800a9811  mov     r8d, 0EBh; int
0x1800a9817  mov     rdx, r13; char *
0x1800a981a  mov     rcx, rax; this
0x1800a981d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a9822  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a9829  jb      loc_1800A9AA7
0x1800a982f  mov     edx, 0Bh
0x1800a9834  jmp     loc_1800A98F2
0x1800a9839  mov     dword ptr [r14], 1
0x1800a9840  lea     r9, [rsp+68h+arg_0]
0x1800a9845  mov     rax, [rbp+0]
0x1800a9849  mov     r8d, 1
0x1800a984f  mov     rdx, rdi
0x1800a9852  mov     [rsp+68h+arg_0], 0
0x1800a9857  mov     rcx, rbp
0x1800a985a  mov     rax, [rax]
0x1800a985d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9862  mov     ebx, eax
0x1800a9864  test    eax, eax
0x1800a9866  jns     loc_1800A9915
0x1800a986c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9873  test    rcx, rcx
0x1800a9876  jnz     short loc_1800A98B9
0x1800a9878  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a987e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9885  mov     rcx, rax
0x1800a9888  test    rax, rax
0x1800a988b  jz      short loc_1800A98AB
0x1800a988d  mov     rax, [rax]
0x1800a9890  mov     edx, 7F0h
0x1800a9895  mov     rax, [rax+8]
0x1800a9899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a989e  test    eax, eax
0x1800a98a0  jz      short loc_1800A98AB
0x1800a98a2  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a98a9  jmp     short loc_1800A98B9
0x1800a98ab  lea     rcx, qword_1800D6F70; this
0x1800a98b2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a98b9  cmp     byte ptr [rcx+8], 0
0x1800a98bd  jz      short loc_1800A98E0
0x1800a98bf  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a98c4  cmp     [rax+7CCh], ebx
0x1800a98ca  jz      short loc_1800A98E0
0x1800a98cc  mov     r9d, ebx; int
0x1800a98cf  mov     r8d, 0F1h; int
0x1800a98d5  mov     rdx, r13; char *
0x1800a98d8  mov     rcx, rax; this
0x1800a98db  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a98e0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a98e7  jb      loc_1800A9AA7
0x1800a98ed  mov     edx, 0Ch
0x1800a98f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800a98f9  lea     r8, WPP_889f6835d2b438fa4c33a79df9f08ee3_Traceguids
0x1800a9900  xor     r9d, r9d
0x1800a9903  mov     [rsp+68h+var_48], ebx
0x1800a9907  mov     rcx, [rcx+10h]
0x1800a990b  call    WPP_SF_qD
0x1800a9910  jmp     loc_1800A9AA7
0x1800a9915  movzx   edx, [rsp+68h+arg_0]
0x1800a991a  test    dl, dl
0x1800a991c  jnz     loc_1800A99B2
0x1800a9922  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9929  test    rcx, rcx
0x1800a992c  jnz     short loc_1800A996F
0x1800a992e  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a9934  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a993b  mov     rcx, rax
0x1800a993e  test    rax, rax
0x1800a9941  jz      short loc_1800A9961
0x1800a9943  mov     rax, [rax]
0x1800a9946  mov     edx, 7F0h
0x1800a994b  mov     rax, [rax+8]
0x1800a994f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9954  test    eax, eax
0x1800a9956  jz      short loc_1800A9961
0x1800a9958  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a995f  jmp     short loc_1800A996F
0x1800a9961  lea     rcx, qword_1800D6F70; this
0x1800a9968  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a996f  cmp     byte ptr [rcx+8], 0
0x1800a9973  mov     ebx, 0C00D36BEh
0x1800a9978  jz      short loc_1800A999B
0x1800a997a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a997f  cmp     [rax+7CCh], ebx
0x1800a9985  jz      short loc_1800A999B
0x1800a9987  mov     r9d, ebx; int
0x1800a998a  mov     r8d, 0F5h; int
0x1800a9990  mov     rdx, r13; char *
0x1800a9993  mov     rcx, rax; this
0x1800a9996  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a999b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a99a2  jb      loc_1800A9AA7
0x1800a99a8  mov     edx, 0Dh
0x1800a99ad  jmp     loc_1800A98F2
0x1800a99b2  mov     al, 80h
0x1800a99b4  test    al, dl
0x1800a99b6  jnz     short loc_1800A99C6
0x1800a99b8  mov     ecx, [r14]
0x1800a99bb  shr     al, 1
0x1800a99bd  inc     ecx
0x1800a99bf  test    dl, al
0x1800a99c1  jz      short loc_1800A99BB
0x1800a99c3  mov     [r14], ecx
0x1800a99c6  movzx   eax, al
0x1800a99c9  mov     esi, 1
0x1800a99ce  not     eax
0x1800a99d0  movsxd  rcx, eax
0x1800a99d3  and     rcx, rdx
0x1800a99d6  inc     rdi
0x1800a99d9  mov     [r15], rcx
0x1800a99dc  cmp     esi, [r14]
0x1800a99df  jge     loc_1800A9AA5
0x1800a99e5  mov     rax, [rbp+0]
0x1800a99e9  lea     r9, [rsp+68h+arg_0]
0x1800a99ee  mov     r8d, 1
0x1800a99f4  mov     rdx, rdi
0x1800a99f7  mov     rcx, rbp
0x1800a99fa  mov     rax, [rax]
0x1800a99fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9a02  mov     ebx, eax
0x1800a9a04  test    eax, eax
0x1800a9a06  js      short loc_1800A9A1E
0x1800a9a08  mov     rcx, [r15]
0x1800a9a0b  inc     rdi
0x1800a9a0e  movzx   eax, [rsp+68h+arg_0]
0x1800a9a13  shl     rcx, 8
0x1800a9a17  or      rcx, rax
0x1800a9a1a  inc     esi
0x1800a9a1c  jmp     short loc_1800A99D9
0x1800a9a1e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9a25  test    rcx, rcx
0x1800a9a28  jnz     short loc_1800A9A6B
0x1800a9a2a  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800a9a30  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9a37  mov     rcx, rax
0x1800a9a3a  test    rax, rax
0x1800a9a3d  jz      short loc_1800A9A5D
0x1800a9a3f  mov     rax, [rax]
0x1800a9a42  mov     edx, 7F0h
0x1800a9a47  mov     rax, [rax+8]
0x1800a9a4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a9a50  test    eax, eax
0x1800a9a52  jz      short loc_1800A9A5D
0x1800a9a54  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9a5b  jmp     short loc_1800A9A6B
0x1800a9a5d  lea     rcx, qword_1800D6F70; this
0x1800a9a64  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800a9a6b  cmp     byte ptr [rcx+8], 0
0x1800a9a6f  jz      short loc_1800A9A92
0x1800a9a71  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x1800a9a76  cmp     [rax+7CCh], ebx
0x1800a9a7c  jz      short loc_1800A9A92
0x1800a9a7e  mov     r9d, ebx; int
0x1800a9a81  mov     r8d, 103h; int
0x1800a9a87  mov     rdx, r13; char *
0x1800a9a8a  mov     rcx, rax; this
0x1800a9a8d  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x1800a9a92  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800a9a99  jb      short loc_1800A9AA7
0x1800a9a9b  mov     edx, 0Eh
0x1800a9aa0  jmp     loc_1800A98F2
0x1800a9aa5  xor     ebx, ebx
0x1800a9aa7  lea     rcx, [rsp+68h+var_38]; this
0x1800a9aac  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x1800a9ab1  lea     r11, [rsp+68h+var_28]
0x1800a9ab6  mov     eax, ebx
0x1800a9ab8  mov     rbx, [r11+38h]
0x1800a9abc  mov     rbp, [r11+40h]
0x1800a9ac0  mov     rsp, r11
0x1800a9ac3  pop     r15
0x1800a9ac5  pop     r14
0x1800a9ac7  pop     r13
0x1800a9ac9  pop     rdi
0x1800a9aca  pop     rsi
0x1800a9acb  retn
```
