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
        struct MFBUFFER::CBuffer *a3,
        __int64 a4)
{
  unsigned int v6; // r14d
  int v7; // r15d
  CallStackTracing *v8; // rbx
  char *v9; // rdi
  DWORD LastError; // ebp
  char *Value; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  unsigned int v14; // ebx
  __int64 *v15; // rcx
  unsigned int v16; // ebp
  __int64 v17; // rdi
  __int64 v18; // rcx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  unsigned __int64 v23; // r9
  __int64 v24; // r8
  __int64 v25; // rcx
  __int64 v26; // r10
  unsigned __int64 v27; // rax
  unsigned int v28; // r9d
  unsigned __int64 v29; // r10
  unsigned __int64 v30; // rax
  CallStackTracing *v31; // rbx
  GUID *v32; // rdi
  DWORD v33; // esi
  GUID *v34; // rax
  int v35; // eax
  int v36; // eax
  CallStackTracing *v38; // rax
  CallStackTracing *v39; // rcx
  __int64 v40; // rax
  CallStackTracing *v41; // rcx
  __int64 v42; // rax
  CallStackTracing *v43; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  __int64 v45; // rdx
  __int64 v46; // [rsp+70h] [rbp+8h] BYREF
  unsigned int v47; // [rsp+78h] [rbp+10h] BYREF

  v6 = a2;
  v7 = -1072875829;
  if ( !CallStackTracing::s_wpInstance )
  {
    v38 = (CallStackTracing *)MFGetCallStackTracingWeakReference(this, a2, a3, a4);
    CallStackTracing::s_wpInstance = v38;
    if ( !v38 || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v38 + 8LL))(v38, 2032) )
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
  }
  v8 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v9 = (char *)CallStackTracing::s_wpInstance + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v8 + 3));
    if ( Value )
    {
      v9 = Value;
    }
    else if ( !GetLastError() )
    {
      v39 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v39 = CallStackTracing::s_wpInstance;
      }
      v40 = (**(__int64 (__fastcall ***)(CallStackTracing *))v39)(v39);
      if ( v40 )
        v9 = (char *)v40;
    }
    SetLastError(LastError);
    v12 = *((unsigned int *)v9 + 497);
    if ( (unsigned int)v12 < *((_DWORD *)v9 + 498) )
    {
      v13 = 2 * v12;
      *(_QWORD *)&v9[8 * v13] = "CCacheReaderBufferList::GetLockedBufferPointer";
      *(_DWORD *)&v9[8 * v13 + 8] = 814;
    }
    ++*((_DWORD *)v9 + 497);
  }
  if ( v6 >= *((_DWORD *)this + 116) )
  {
    if ( g_wppLevels )
    {
      v45 = 53;
LABEL_50:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v45, &WPP_cf1ca2f8d83a3bfb35334cd6433c5f83_Traceguids, this, v7);
    }
  }
  else
  {
    v14 = 0;
    v15 = this[54];
    v16 = v6 + *((_DWORD *)this + 114);
    while ( v15 )
    {
      v17 = *v15;
      v15 = (__int64 *)v15[1];
      v14 += *(_DWORD *)(v17 + 32);
      if ( v16 < v14 )
      {
        v18 = *(_QWORD *)(v17 + 16);
        v47 = 0;
        v46 = 0;
        v7 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD, unsigned int *))(*(_QWORD *)v18 + 24LL))(
               v18,
               &v46,
               0,
               &v47);
        if ( v7 < 0 )
        {
          if ( !CallStackTracing::s_wpInstance )
          {
            v43 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v20, v19, v21, v22);
            CallStackTracing::s_wpInstance = v43;
            if ( !v43
              || !(*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v43 + 8LL))(v43, 2032) )
            {
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B07E0;
            }
          }
          if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
          {
            ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
            if ( *((_DWORD *)ThreadRelativeContext + 499) != v7 )
              CallStackContext::TraceFailure(
                ThreadRelativeContext,
                "CCacheReaderBufferList::GetLockedBufferPointer",
                843,
                v7);
          }
          if ( g_wppLevels )
          {
            v45 = 54;
            goto LABEL_50;
          }
        }
        else
        {
          v23 = v47;
          v24 = v46;
          v25 = v47;
          *(_QWORD *)a3 = v47;
          v26 = (unsigned int)v23;
          *((_QWORD *)a3 + 1) = v24;
          v27 = v16 - v14 + *(_DWORD *)(v17 + 32);
          if ( v27 <= v23 )
            v25 = (unsigned int)v27;
          v28 = v23 - (v16 - v14 + *(_DWORD *)(v17 + 32));
          v29 = v26 - v25;
          *(_QWORD *)a3 = v29;
          *((_QWORD *)a3 + 1) = v25 + v24;
          v30 = *((_DWORD *)this + 116) - v6;
          if ( (unsigned int)v30 >= v28 )
            v30 = v28;
          if ( v30 <= v29 )
            v29 = v30;
          *(_QWORD *)a3 = v29;
        }
        break;
      }
    }
  }
  v31 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v32 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
    v33 = GetLastError();
    v34 = (GUID *)TlsGetValue(*((_DWORD *)v31 + 3));
    if ( v34 )
    {
      v32 = v34;
    }
    else if ( !GetLastError() )
    {
      v41 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v41 = CallStackTracing::s_wpInstance;
      }
      v42 = (**(__int64 (__fastcall ***)(CallStackTracing *))v41)(v41);
      if ( v42 )
        v32 = (GUID *)v42;
    }
    SetLastError(v33);
    v35 = *(_DWORD *)&v32[124].Data2;
    if ( v35 )
    {
      v36 = v35 - 1;
      *(_DWORD *)&v32[124].Data2 = v36;
      if ( !v36 )
      {
        *(_DWORD *)&v32[124].Data2 = 0;
        *(_QWORD *)&v32[126].Data1 = 0;
        *(_DWORD *)&v32[124].Data4[4] = 0;
        v32[125] = GUID_00000000_0000_0000_0000_000000000000;
        *(_DWORD *)v32[126].Data4 = 0;
        v32[124].Data1 = GetCurrentThreadId();
      }
    }
  }
  return (unsigned int)v7;
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
