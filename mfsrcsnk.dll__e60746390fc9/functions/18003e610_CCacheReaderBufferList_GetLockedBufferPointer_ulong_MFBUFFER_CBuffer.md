# CCacheReaderBufferList::GetLockedBufferPointer(ulong,MFBUFFER::CBuffer &)

- ea: `0x18003e610`
- end: `0x18003e9cd`
- name: `?GetLockedBufferPointer@CCacheReaderBufferList@@QEAAJKAEAVCBuffer@MFBUFFER@@@Z`
- size: `957`
- prototype: `__int64 __fastcall(CCacheReaderBufferList *__hidden this, unsigned int, struct MFBUFFER::CBuffer *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180009ab4`
- `0x18003eb70`

## callees

- `0x180010190`
- `0x18001303c`
- `0x18003e610`
- `0x180071a44`
- `0x180073b14`
- `0x180173010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e690`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e7c7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e690`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003e7c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e671`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e7a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e850`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e881`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e671`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e7a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e850`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003e881`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003e80c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003e80c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003e67c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003e7b3`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003e67c`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18003e7b3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003e82b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003e8db`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003e82b`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18003e8db`

## string_xrefs

- `0x18003e650`: `CCacheReaderBufferList::GetLockedBufferPointer`
- `0x18003e69c`: `CCacheReaderBufferList::GetLockedBufferPointer`
- `0x18003e91f`: `CCacheReaderBufferList::GetLockedBufferPointer`

## pseudocode

```c
__int64 __fastcall CCacheReaderBufferList::GetLockedBufferPointer(
        __int64 **this,
        __int64 a2,
        struct MFBUFFER::CBuffer *a3)
{
  unsigned int v5; // r14d
  int v6; // r15d
  CallStackTracing *v7; // rbx
  char *v8; // rdi
  DWORD LastError; // ebp
  char *Value; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  unsigned int v13; // ebx
  __int64 *v14; // rcx
  unsigned int v15; // ebp
  __int64 v16; // rdi
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  unsigned __int64 v20; // r9
  __int64 v21; // r8
  __int64 v22; // rcx
  __int64 v23; // r10
  unsigned __int64 v24; // rax
  unsigned int v25; // r9d
  unsigned __int64 v26; // r10
  unsigned __int64 v27; // rax
  CallStackTracing *v28; // rbx
  GUID *v29; // rdi
  DWORD v30; // esi
  GUID *v31; // rax
  int v32; // eax
  int v33; // eax
  CallStackTracing *v35; // rax
  CallStackTracing *v36; // rcx
  __int64 v37; // rax
  CallStackTracing *v38; // rcx
  __int64 v39; // rax
  CallStackTracing *v40; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v42; // rdx
  __int64 v43; // [rsp+70h] [rbp+8h] BYREF
  unsigned int v44; // [rsp+78h] [rbp+10h] BYREF

  v5 = a2;
  v6 = -1072875829;
  if ( !CallStackTracing::s_wpInstance )
  {
    v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(this, a2);
    CallStackTracing::s_wpInstance = v35;
    if ( !v35 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
  }
  v7 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v8 = (char *)CallStackTracing::s_wpInstance + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v7 + 3));
    if ( Value )
    {
      v8 = Value;
    }
    else if ( !GetLastError() )
    {
      v36 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v36 = CallStackTracing::s_wpInstance;
      }
      v37 = (**(__int64 (__fastcall ***)(CallStackTracing *))v36)(v36);
      if ( v37 )
        v8 = (char *)v37;
    }
    SetLastError(LastError);
    v11 = *((unsigned int *)v8 + 497);
    if ( (unsigned int)v11 < *((_DWORD *)v8 + 498) )
    {
      v12 = 2 * v11;
      *(_QWORD *)&v8[8 * v12] = "CCacheReaderBufferList::GetLockedBufferPointer";
      *(_DWORD *)&v8[8 * v12 + 8] = 814;
    }
    ++*((_DWORD *)v8 + 497);
  }
  if ( v5 >= *((_DWORD *)this + 116) )
  {
    if ( g_wppLevels )
    {
      v42 = 53;
LABEL_50:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v42, WPP_cf1ca2f8d83a3bfb35334cd6433c5f83_Traceguids, this, v6);
    }
  }
  else
  {
    v13 = 0;
    v14 = this[54];
    v15 = v5 + *((_DWORD *)this + 114);
    while ( v14 )
    {
      v16 = *v14;
      v14 = (__int64 *)v14[1];
      v13 += *(_DWORD *)(v16 + 32);
      if ( v15 < v13 )
      {
        v17 = *(_QWORD *)(v16 + 16);
        v44 = 0;
        v43 = 0;
        v6 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD, unsigned int *))(*(_QWORD *)v17 + 24LL))(
               v17,
               &v43,
               0,
               &v44);
        if ( v6 < 0 )
        {
          if ( !CallStackTracing::s_wpInstance )
          {
            v40 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v19, v18);
            CallStackTracing::s_wpInstance = v40;
            if ( !v40
              || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v40 + 8LL))(v40, 2032) )
            {
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != v6 )
              CallStackContext::TraceFailure(
                ThreadRelativeContext,
                "CCacheReaderBufferList::GetLockedBufferPointer",
                843,
                v6);
          }
          if ( g_wppLevels )
          {
            v42 = 54;
            goto LABEL_50;
          }
        }
        else
        {
          v20 = v44;
          v21 = v43;
          v22 = v44;
          *(_QWORD *)a3 = v44;
          v23 = (unsigned int)v20;
          *((_QWORD *)a3 + 1) = v21;
          v24 = v15 - v13 + *(_DWORD *)(v16 + 32);
          if ( v24 <= v20 )
            v22 = (unsigned int)v24;
          v25 = v20 - (v15 - v13 + *(_DWORD *)(v16 + 32));
          v26 = v23 - v22;
          *(_QWORD *)a3 = v26;
          *((_QWORD *)a3 + 1) = v22 + v21;
          v27 = *((_DWORD *)this + 116) - v5;
          if ( (unsigned int)v27 >= v25 )
            v27 = v25;
          if ( v27 <= v26 )
            v26 = v27;
          *(_QWORD *)a3 = v26;
        }
        break;
      }
    }
  }
  v28 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v29 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
    v30 = GetLastError();
    v31 = (GUID *)TlsGetValue(*((_DWORD *)v28 + 3));
    if ( v31 )
    {
      v29 = v31;
    }
    else if ( !GetLastError() )
    {
      v38 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v38 = CallStackTracing::s_wpInstance;
      }
      v39 = (**(__int64 (__fastcall ***)(CallStackTracing *))v38)(v38);
      if ( v39 )
        v29 = (GUID *)v39;
    }
    SetLastError(v30);
    v32 = *(_DWORD *)&v29[124].Data2;
    if ( v32 )
    {
      v33 = v32 - 1;
      *(_DWORD *)&v29[124].Data2 = v33;
      if ( !v33 )
      {
        *(_DWORD *)&v29[124].Data2 = 0;
        *(_QWORD *)&v29[126].Data1 = 0;
        *(_DWORD *)&v29[124].Data4[4] = 0;
        v29[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v29[126].Data4 = 0;
        v29[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18003e610  push    rbx
0x18003e612  push    rsi
0x18003e613  push    r13
0x18003e615  push    r15
0x18003e617  sub     rsp, 48h
0x18003e61b  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e623  lea     rbx, qword_1801B07E0
0x18003e62a  mov     [rsp+68h+var_30], r12
0x18003e62f  mov     rsi, rcx
0x18003e632  mov     [rsp+68h+var_38], r14
0x18003e637  mov     r12, r8
0x18003e63a  mov     r14d, edx
0x18003e63d  mov     r15d, 0C00D36CBh
0x18003e643  jz      loc_18003E82B
0x18003e649  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e650  lea     rcx, aCcachereaderbu; "CCacheReaderBufferList::GetLockedBuffer"...
0x18003e657  mov     [rsp+68h+arg_10], rbp
0x18003e65f  mov     [rsp+68h+var_28], rdi
0x18003e664  cmp     byte ptr [rbx+8], 0
0x18003e668  jz      short loc_18003E6C0
0x18003e66a  lea     rdi, [rbx+0D0h]
0x18003e671  call    cs:__imp_GetLastError
0x18003e677  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18003e67a  mov     ebp, eax
0x18003e67c  call    cs:__imp_TlsGetValue
0x18003e682  test    rax, rax
0x18003e685  jz      loc_18003E850
0x18003e68b  mov     rdi, rax
0x18003e68e  mov     ecx, ebp; dwErrCode
0x18003e690  call    cs:__imp_SetLastError
0x18003e696  mov     eax, [rdi+7C4h]
0x18003e69c  lea     rcx, aCcachereaderbu; "CCacheReaderBufferList::GetLockedBuffer"...
0x18003e6a3  cmp     eax, [rdi+7C8h]
0x18003e6a9  jnb     short loc_18003E6BA
0x18003e6ab  add     rax, rax
0x18003e6ae  mov     [rdi+rax*8], rcx
0x18003e6b2  mov     dword ptr [rdi+rax*8+8], 32Eh
0x18003e6ba  inc     dword ptr [rdi+7C4h]
0x18003e6c0  xor     r13d, r13d
0x18003e6c3  cmp     r14d, [rsi+1D0h]
0x18003e6ca  jnb     loc_18003E957
0x18003e6d0  mov     ebp, [rsi+1C8h]
0x18003e6d6  mov     ebx, r13d
0x18003e6d9  mov     rcx, [rsi+1B0h]
0x18003e6e0  add     ebp, r14d
0x18003e6e3  test    rcx, rcx
0x18003e6e6  jz      loc_18003E782
0x18003e6ec  mov     rdi, [rcx]
0x18003e6ef  mov     rcx, [rcx+8]
0x18003e6f3  add     ebx, [rdi+20h]
0x18003e6f6  cmp     ebp, ebx
0x18003e6f8  jnb     short loc_18003E6E3
0x18003e6fa  mov     rcx, [rdi+10h]
0x18003e6fe  lea     r9, [rsp+68h+arg_8]
0x18003e703  mov     [rsp+68h+arg_8], r13d
0x18003e708  lea     rdx, [rsp+68h+arg_0]
0x18003e70d  mov     [rsp+68h+arg_0], r13
0x18003e712  xor     r8d, r8d
0x18003e715  mov     rax, [rcx]
0x18003e718  mov     rax, [rax+18h]
0x18003e71c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e721  mov     r15d, eax
0x18003e724  test    eax, eax
0x18003e726  js      loc_18003E8CE
0x18003e72c  mov     r9d, [rsp+68h+arg_8]
0x18003e731  sub     ebp, ebx
0x18003e733  mov     r8, [rsp+68h+arg_0]
0x18003e738  mov     ecx, r9d
0x18003e73b  mov     [r12], r9
0x18003e73f  mov     r10d, r9d
0x18003e742  mov     [r12+8], r8
0x18003e747  mov     edx, [rdi+20h]
0x18003e74a  add     edx, ebp
0x18003e74c  mov     eax, edx
0x18003e74e  cmp     rax, r9
0x18003e751  cmovbe  ecx, eax
0x18003e754  sub     r9d, edx
0x18003e757  sub     r10, rcx
0x18003e75a  mov     [r12], r10
0x18003e75e  lea     rax, [rcx+r8]
0x18003e762  mov     [r12+8], rax
0x18003e767  mov     eax, [rsi+1D0h]
0x18003e76d  sub     eax, r14d
0x18003e770  cmp     eax, r9d
0x18003e773  cmovnb  eax, r9d
0x18003e777  cmp     rax, r10
0x18003e77a  cmovbe  r10, rax
0x18003e77e  mov     [r12], r10
0x18003e782  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e789  mov     r14, [rsp+68h+var_38]
0x18003e78e  mov     r12, [rsp+68h+var_30]
0x18003e793  mov     rbp, [rsp+68h+arg_10]
0x18003e79b  cmp     [rbx+8], r13b
0x18003e79f  jz      short loc_18003E818
0x18003e7a1  lea     rdi, [rbx+0D0h]
0x18003e7a8  call    cs:__imp_GetLastError
0x18003e7ae  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18003e7b1  mov     esi, eax
0x18003e7b3  call    cs:__imp_TlsGetValue
0x18003e7b9  test    rax, rax
0x18003e7bc  jz      loc_18003E881
0x18003e7c2  mov     rdi, rax
0x18003e7c5  mov     ecx, esi; dwErrCode
0x18003e7c7  call    cs:__imp_SetLastError
0x18003e7cd  mov     eax, [rdi+7C4h]
0x18003e7d3  test    eax, eax
0x18003e7d5  jz      short loc_18003E818
0x18003e7d7  sub     eax, 1
0x18003e7da  mov     [rdi+7C4h], eax
0x18003e7e0  jnz     short loc_18003E818
0x18003e7e2  mov     [rdi+7C4h], r13d
0x18003e7e9  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18003e7f0  mov     [rdi+7E0h], r13
0x18003e7f7  mov     [rdi+7CCh], r13d
0x18003e7fe  movups  xmmword ptr [rdi+7D0h], xmm0
0x18003e805  mov     [rdi+7E8h], r13d
0x18003e80c  call    cs:__imp_GetCurrentThreadId
0x18003e812  mov     [rdi+7C0h], eax
0x18003e818  mov     rdi, [rsp+68h+var_28]
0x18003e81d  mov     eax, r15d
0x18003e820  add     rsp, 48h
0x18003e824  pop     r15
0x18003e826  pop     r13
0x18003e828  pop     rsi
0x18003e829  pop     rbx
0x18003e82a  retn
0x18003e82b  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003e831  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e838  mov     rcx, rax
0x18003e83b  test    rax, rax
0x18003e83e  jnz     loc_18003E939
0x18003e844  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e84b  jmp     loc_18003E649
0x18003e850  call    cs:__imp_GetLastError
0x18003e856  test    eax, eax
0x18003e858  jnz     loc_18003E68E
0x18003e85e  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e865  test    rcx, rcx
0x18003e868  jz      short loc_18003E8B2
0x18003e86a  mov     rax, [rcx]
0x18003e86d  mov     rax, [rax]
0x18003e870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e875  test    rax, rax
0x18003e878  cmovnz  rdi, rax
0x18003e87c  jmp     loc_18003E68E
0x18003e881  call    cs:__imp_GetLastError
0x18003e887  test    eax, eax
0x18003e889  jnz     loc_18003E7C5
0x18003e88f  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e896  test    rcx, rcx
0x18003e899  jz      short loc_18003E8C0
0x18003e89b  mov     rax, [rcx]
0x18003e89e  mov     rax, [rax]
0x18003e8a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e8a6  test    rax, rax
0x18003e8a9  cmovnz  rdi, rax
0x18003e8ad  jmp     loc_18003E7C5
0x18003e8b2  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18003e8b7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e8be  jmp     short loc_18003E86A
0x18003e8c0  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18003e8c5  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e8cc  jmp     short loc_18003E89B
0x18003e8ce  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, r13; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e8d5  jnz     loc_18003E9AD
0x18003e8db  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18003e8e1  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e8e8  mov     rcx, rax
0x18003e8eb  test    rax, rax
0x18003e8ee  jnz     loc_18003E994
0x18003e8f4  lea     rax, qword_1801B07E0
0x18003e8fb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e902  jmp     loc_18003E9AD
0x18003e907  mov     rcx, rbx; this
0x18003e90a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18003e90f  cmp     [rax+7CCh], r15d
0x18003e916  jz      loc_18003E9BE
0x18003e91c  mov     r9d, r15d; int
0x18003e91f  lea     rdx, aCcachereaderbu; "CCacheReaderBufferList::GetLockedBuffer"...
0x18003e926  mov     r8d, 34Bh; int
0x18003e92c  mov     rcx, rax; this
0x18003e92f  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18003e934  jmp     loc_18003E9BE
0x18003e939  mov     rax, [rax]
0x18003e93c  mov     edx, 7F0h
0x18003e941  mov     rax, [rax+8]
0x18003e945  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e94a  test    eax, eax
0x18003e94c  jnz     loc_18003E649
0x18003e952  jmp     loc_18003E844
0x18003e957  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003e95e  jb      loc_18003E782
0x18003e964  mov     edx, 35h ; '5'
0x18003e969  jmp     short loc_18003E970
0x18003e96b  mov     edx, 36h ; '6'
0x18003e970  mov     rcx, cs:WPP_GLOBAL_Control
0x18003e977  lea     r8, WPP_cf1ca2f8d83a3bfb35334cd6433c5f83_Traceguids
0x18003e97e  mov     r9, rsi
0x18003e981  mov     [rsp+68h+var_48], r15d
0x18003e986  mov     rcx, [rcx+10h]
0x18003e98a  call    WPP_SF_qD
0x18003e98f  jmp     loc_18003E782
0x18003e994  mov     rax, [rax]
0x18003e997  mov     edx, 7F0h
0x18003e99c  mov     rax, [rax+8]
0x18003e9a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e9a5  test    eax, eax
0x18003e9a7  jz      loc_18003E8F4
0x18003e9ad  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18003e9b4  cmp     [rbx+8], r13b
0x18003e9b8  jnz     loc_18003E907
0x18003e9be  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003e9c5  jb      loc_18003E782
0x18003e9cb  jmp     short loc_18003E96B
```
