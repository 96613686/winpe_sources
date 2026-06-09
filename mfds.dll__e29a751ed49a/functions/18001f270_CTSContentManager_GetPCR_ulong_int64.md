# CTSContentManager::GetPCR(ulong,__int64 *)

- ea: `0x18001f270`
- end: `0x18001f747`
- name: `?GetPCR@CTSContentManager@@UEAAXKPEA_J@Z`
- size: `1239`
- prototype: `void __fastcall(CTSContentManager *__hidden this, unsigned int, __int64 *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180002820`
- `0x18001f270`
- `0x1800214e0`
- `0x18007c8e8`
- `0x1800a4118`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f3e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f479`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f4ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f5ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f3e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f479`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f4ba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f5ab`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f3a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f442`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f4a7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f3a6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f442`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f4a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f2de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f51a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f2de`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f51a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f2b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f4ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f5bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f5f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f2b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f4ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f5bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f5f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f569`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f569`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001f2c4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001f500`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001f2c4`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001f500`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001f638`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001f6f8`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001f638`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18001f6f8`

## pseudocode

```c
void __fastcall CTSContentManager::GetPCR(CTSContentManager *this, unsigned int a2, __int64 *a3)
{
  CallStackTracing *v6; // rdi
  char *v7; // rbx
  DWORD LastError; // esi
  char *Value; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  unsigned int v12; // esi
  __int64 v13; // rbp
  char *v14; // rdi
  __int64 v15; // rbx
  _QWORD **v16; // rcx
  _QWORD *i; // rax
  __int64 v18; // rbx
  _QWORD **v19; // rcx
  _QWORD *j; // rax
  __int64 v21; // rbx
  __int64 v22; // rbx
  struct _RTL_CRITICAL_SECTION *v23; // rdi
  __int64 v24; // rbx
  CallStackTracing *v25; // rdi
  GUID *v26; // rbx
  DWORD v27; // esi
  GUID *v28; // rax
  int v29; // eax
  int v30; // eax
  CallStackTracing *v31; // rcx
  __int64 v32; // rax
  CallStackTracing *v33; // rcx
  __int64 v34; // rax
  CallStackTracing *v35; // rax
  CallStackTracing *v36; // rax
  __int64 v37; // [rsp+30h] [rbp-38h]
  __int64 v38; // [rsp+70h] [rbp+8h] BYREF
  char v39; // [rsp+78h] [rbp+10h] BYREF

  if ( !CallStackTracing::s_wpInstance )
    CallStackTracing::InitInstance();
  v6 = CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
  {
    v7 = (char *)CallStackTracing::s_wpInstance + 208;
    LastError = GetLastError();
    Value = (char *)TlsGetValue(*((_DWORD *)v6 + 3));
    if ( Value )
    {
      v7 = Value;
    }
    else if ( !GetLastError() )
    {
      v31 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
        CallStackTracing::s_wpInstance = v35;
        if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
        {
          v31 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v31 = (CallStackTracing *)&qword_1800EB130;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
        }
      }
      v32 = (**(__int64 (__fastcall ***)(CallStackTracing *))v31)(v31);
      if ( v32 )
        v7 = (char *)v32;
    }
    SetLastError(LastError);
    v10 = *((unsigned int *)v7 + 497);
    if ( (unsigned int)v10 < *((_DWORD *)v7 + 498) )
    {
      v11 = 2 * v10;
      *(_QWORD *)&v7[8 * v11] = "CTSContentManager::GetPCR";
      *(_DWORD *)&v7[8 * v11 + 8] = 1412;
    }
    ++*((_DWORD *)v7 + 497);
  }
  if ( (unsigned __int8)byte_1800EACCB >= 0x20u )
    WPP_SF_qDq(
      *((_QWORD *)WPP_GLOBAL_Control + 17),
      44,
      &WPP_2f3388c9edf036fc9dd113cf4a92beb4_Traceguids,
      this,
      a2,
      a3,
      v37);
  v12 = *((_DWORD *)this + 395);
  v38 = 0;
  v13 = 0;
  *a3 = -1;
  if ( !a2 )
    a2 = *((_DWORD *)this + 394);
  if ( *((CTSContentManager **)this + 26) == (CTSContentManager *)((char *)this + 208) || a2 == -1 )
  {
LABEL_54:
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v39);
  }
  else
  {
    if ( v12 == -1 )
    {
      v14 = (char *)this + 1072;
      v15 = (*(unsigned int (__fastcall **)(char *, _QWORD))(*((_QWORD *)this + 134) + 8LL))((char *)this + 1072, a2)
          % 0x13;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 1456));
      v16 = (_QWORD **)((char *)this + 16 * v15 + 1136);
      for ( i = *v16; i != v16; i = (_QWORD *)*i )
      {
        if ( *((_DWORD *)i - 10) == a2 )
        {
          v38 = *(i - 4);
          v13 = v38;
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 1456));
          if ( !v13 )
            goto LABEL_29;
          v12 = *(_DWORD *)(v13 + 24);
          if ( v12 == -1 )
            goto LABEL_29;
          goto LABEL_21;
        }
      }
    }
    else
    {
LABEL_21:
      v14 = (char *)this + 224;
      v18 = (*(unsigned int (__fastcall **)(char *, _QWORD))(*((_QWORD *)this + 28) + 8LL))((char *)this + 224, v12)
          % 0x13;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 608));
      v19 = (_QWORD **)((char *)this + 16 * v18 + 288);
      for ( j = *v19; j != v19; j = (_QWORD *)*j )
      {
        if ( *((_DWORD *)j - 10) == v12 )
        {
          v21 = *(j - 4);
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 608));
          if ( !v13 && (int)TGenericMap<unsigned __int64,unsigned long,0,5,19>::Find(v21 + 104, a2, &v38) < 0 )
            goto LABEL_54;
          v22 = *(_QWORD *)(v21 + 56);
          if ( v22 )
          {
            if ( *(_DWORD *)(v22 + 104) == *((_DWORD *)this + 27) )
            {
              v23 = (struct _RTL_CRITICAL_SECTION *)(v22 + 48);
              EnterCriticalSection((LPCRITICAL_SECTION)(v22 + 48));
              v24 = *(_QWORD *)(v22 + 88);
              LeaveCriticalSection(v23);
              *a3 = v24;
              if ( !*((_DWORD *)this + 394) )
                *((_DWORD *)this + 394) = a2;
            }
          }
          goto LABEL_29;
        }
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(v14 + 384));
LABEL_29:
    v25 = CallStackTracing::s_wpInstance;
    if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) )
    {
      v26 = (GUID *)((char *)CallStackTracing::s_wpInstance + 208);
      v27 = GetLastError();
      v28 = (GUID *)TlsGetValue(*((_DWORD *)v25 + 3));
      if ( v28 )
      {
        v26 = v28;
      }
      else if ( !GetLastError() )
      {
        v33 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          v36 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0);
          CallStackTracing::s_wpInstance = v36;
          if ( v36 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
          {
            v33 = CallStackTracing::s_wpInstance;
          }
          else
          {
            v33 = (CallStackTracing *)&qword_1800EB130;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1800EB130;
          }
        }
        v34 = (**(__int64 (__fastcall ***)(CallStackTracing *))v33)(v33);
        if ( v34 )
          v26 = (GUID *)v34;
      }
      SetLastError(v27);
      v29 = *(_DWORD *)&v26[124].Data2;
      if ( v29 )
      {
        v30 = v29 - 1;
        *(_DWORD *)&v26[124].Data2 = v30;
        if ( !v30 )
        {
          *(_DWORD *)&v26[124].Data2 = 0;
          *(_QWORD *)&v26[126].Data1 = 0;
          *(_DWORD *)&v26[124].Data4[4] = 0;
          v26[125] = GUID_00000000_0000_0000_0000_000000000000;
          *(_DWORD *)v26[126].Data4 = 0;
          v26[124].Data1 = GetCurrentThreadId();
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18001f270  push    rbp
0x18001f272  push    rsi
0x18001f273  push    rdi
0x18001f274  push    r12
0x18001f276  push    r13
0x18001f278  push    r14
0x18001f27a  push    r15
0x18001f27c  sub     rsp, 30h
0x18001f280  cmp     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, 0; CallStackTracing * CallStackTracing::s_wpInstance
0x18001f288  mov     r12, r8
0x18001f28b  mov     r14d, edx
0x18001f28e  mov     r15, rcx
0x18001f291  jz      loc_18001F62E
0x18001f297  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001f29e  mov     [rsp+68h+arg_10], rbx
0x18001f2a6  cmp     byte ptr [rdi+8], 0
0x18001f2aa  jz      short loc_18001F314
0x18001f2ac  lea     rbx, [rdi+0D0h]
0x18001f2b3  call    cs:__imp_GetLastError
0x18001f2ba  nop     dword ptr [rax+rax+00h]
0x18001f2bf  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18001f2c2  mov     esi, eax
0x18001f2c4  call    cs:__imp_TlsGetValue
0x18001f2cb  nop     dword ptr [rax+rax+00h]
0x18001f2d0  test    rax, rax
0x18001f2d3  jz      loc_18001F5BC
0x18001f2d9  mov     rbx, rax
0x18001f2dc  mov     ecx, esi; dwErrCode
0x18001f2de  call    cs:__imp_SetLastError
0x18001f2e5  nop     dword ptr [rax+rax+00h]
0x18001f2ea  mov     eax, [rbx+7C4h]
0x18001f2f0  cmp     eax, [rbx+7C8h]
0x18001f2f6  jnb     short loc_18001F30E
0x18001f2f8  add     rax, rax
0x18001f2fb  lea     rcx, aCtscontentmana_4; "CTSContentManager::GetPCR"
0x18001f302  mov     [rbx+rax*8], rcx
0x18001f306  mov     dword ptr [rbx+rax*8+8], 584h
0x18001f30e  inc     dword ptr [rbx+7C4h]
0x18001f314  cmp     cs:byte_1800EACCB, 20h ; ' '
0x18001f31b  jnb     loc_18001F687
0x18001f321  mov     esi, [r15+62Ch]
0x18001f328  xor     r13d, r13d
0x18001f32b  mov     [rsp+68h+arg_0], r13
0x18001f330  mov     ebp, r13d
0x18001f333  mov     qword ptr [r12], 0FFFFFFFFFFFFFFFFh
0x18001f33b  test    r14d, r14d
0x18001f33e  jz      loc_18001F6B8
0x18001f344  lea     rax, [r15+0D0h]
0x18001f34b  cmp     [rax], rax
0x18001f34e  jz      loc_18001F6DD
0x18001f354  cmp     r14d, 0FFFFFFFFh
0x18001f358  jz      loc_18001F6DD
0x18001f35e  mov     rbx, 0D79435E50D79435Fh
0x18001f368  cmp     esi, 0FFFFFFFFh
0x18001f36b  jnz     loc_18001F40E
0x18001f371  lea     rdi, [r15+430h]
0x18001f378  mov     edx, r14d
0x18001f37b  mov     rax, [rdi]
0x18001f37e  mov     rcx, rdi
0x18001f381  mov     rax, [rax+8]
0x18001f385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f38a  mov     ecx, eax
0x18001f38c  mov     rax, rbx
0x18001f38f  mul     rcx
0x18001f392  shr     rdx, 4
0x18001f396  imul    rax, rdx, 13h
0x18001f39a  sub     rcx, rax
0x18001f39d  mov     ebx, ecx
0x18001f39f  lea     rcx, [rdi+180h]; lpCriticalSection
0x18001f3a6  call    cs:__imp_EnterCriticalSection
0x18001f3ad  nop     dword ptr [rax+rax+00h]
0x18001f3b2  lea     rcx, [rbx+4]
0x18001f3b6  shl     rcx, 4
0x18001f3ba  add     rcx, rdi
0x18001f3bd  mov     rax, [rcx]
0x18001f3c0  cmp     rax, rcx
0x18001f3c3  jz      loc_18001F5A4
0x18001f3c9  cmp     [rax-28h], r14d
0x18001f3cd  jnz     loc_18001F59C
0x18001f3d3  mov     rbp, [rax-20h]
0x18001f3d7  lea     rcx, [rdi+180h]; lpCriticalSection
0x18001f3de  mov     [rsp+68h+arg_0], rbp
0x18001f3e3  call    cs:__imp_LeaveCriticalSection
0x18001f3ea  nop     dword ptr [rax+rax+00h]
0x18001f3ef  test    rbp, rbp
0x18001f3f2  jz      loc_18001F4D7
0x18001f3f8  mov     esi, [rbp+18h]
0x18001f3fb  mov     rbx, 0D79435E50D79435Fh
0x18001f405  cmp     esi, 0FFFFFFFFh
0x18001f408  jz      loc_18001F4D7
0x18001f40e  lea     rdi, [r15+0E0h]
0x18001f415  mov     edx, esi
0x18001f417  mov     rcx, [rdi]
0x18001f41a  mov     rax, [rcx+8]
0x18001f41e  mov     rcx, rdi
0x18001f421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f426  mov     ecx, eax
0x18001f428  mov     rax, rbx
0x18001f42b  mul     rcx
0x18001f42e  shr     rdx, 4
0x18001f432  imul    rax, rdx, 13h
0x18001f436  sub     rcx, rax
0x18001f439  mov     ebx, ecx
0x18001f43b  lea     rcx, [rdi+180h]; lpCriticalSection
0x18001f442  call    cs:__imp_EnterCriticalSection
0x18001f449  nop     dword ptr [rax+rax+00h]
0x18001f44e  lea     rcx, [rbx+4]
0x18001f452  shl     rcx, 4
0x18001f456  add     rcx, rdi
0x18001f459  mov     rax, [rcx]
0x18001f45c  cmp     rax, rcx
0x18001f45f  jz      loc_18001F5A4
0x18001f465  cmp     [rax-28h], esi
0x18001f468  jnz     loc_18001F594
0x18001f46e  mov     rbx, [rax-20h]
0x18001f472  lea     rcx, [rdi+180h]; lpCriticalSection
0x18001f479  call    cs:__imp_LeaveCriticalSection
0x18001f480  nop     dword ptr [rax+rax+00h]
0x18001f485  test    rbp, rbp
0x18001f488  jz      loc_18001F6C4
0x18001f48e  mov     rbx, [rbx+38h]
0x18001f492  test    rbx, rbx
0x18001f495  jz      short loc_18001F4D7
0x18001f497  mov     eax, [r15+6Ch]
0x18001f49b  cmp     [rbx+68h], eax
0x18001f49e  jnz     short loc_18001F4D7
0x18001f4a0  lea     rdi, [rbx+30h]
0x18001f4a4  mov     rcx, rdi; lpCriticalSection
0x18001f4a7  call    cs:__imp_EnterCriticalSection
0x18001f4ae  nop     dword ptr [rax+rax+00h]
0x18001f4b3  mov     rbx, [rbx+58h]
0x18001f4b7  mov     rcx, rdi; lpCriticalSection
0x18001f4ba  call    cs:__imp_LeaveCriticalSection
0x18001f4c1  nop     dword ptr [rax+rax+00h]
0x18001f4c6  mov     [r12], rbx
0x18001f4ca  cmp     [r15+628h], r13d
0x18001f4d1  jz      loc_18001F6EC
0x18001f4d7  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001f4de  cmp     byte ptr [rdi+8], 0
0x18001f4e2  jz      loc_18001F57B
0x18001f4e8  lea     rbx, [rdi+0D0h]
0x18001f4ef  call    cs:__imp_GetLastError
0x18001f4f6  nop     dword ptr [rax+rax+00h]
0x18001f4fb  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x18001f4fe  mov     esi, eax
0x18001f500  call    cs:__imp_TlsGetValue
0x18001f507  nop     dword ptr [rax+rax+00h]
0x18001f50c  test    rax, rax
0x18001f50f  jz      loc_18001F5F3
0x18001f515  mov     rbx, rax
0x18001f518  mov     ecx, esi; dwErrCode
0x18001f51a  call    cs:__imp_SetLastError
0x18001f521  nop     dword ptr [rax+rax+00h]
0x18001f526  mov     eax, [rbx+7C4h]
0x18001f52c  test    eax, eax
0x18001f52e  jz      short loc_18001F57B
0x18001f530  sub     eax, 1
0x18001f533  mov     [rbx+7C4h], eax
0x18001f539  jnz     short loc_18001F57B
0x18001f53b  mov     [rbx+7C4h], r13d
0x18001f542  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18001f549  mov     qword ptr [rbx+7E0h], 0
0x18001f554  mov     [rbx+7CCh], r13d
0x18001f55b  movups  xmmword ptr [rbx+7D0h], xmm0
0x18001f562  mov     [rbx+7E8h], r13d
0x18001f569  call    cs:__imp_GetCurrentThreadId
0x18001f570  nop     dword ptr [rax+rax+00h]
0x18001f575  mov     [rbx+7C0h], eax
0x18001f57b  mov     rbx, [rsp+68h+arg_10]
0x18001f583  add     rsp, 30h
0x18001f587  pop     r15
0x18001f589  pop     r14
0x18001f58b  pop     r13
0x18001f58d  pop     r12
0x18001f58f  pop     rdi
0x18001f590  pop     rsi
0x18001f591  pop     rbp
0x18001f592  retn
0x18001f594  mov     rax, [rax]
0x18001f597  jmp     loc_18001F45C
0x18001f59c  mov     rax, [rax]
0x18001f59f  jmp     loc_18001F3C0
0x18001f5a4  lea     rcx, [rdi+180h]; lpCriticalSection
0x18001f5ab  call    cs:__imp_LeaveCriticalSection
0x18001f5b2  nop     dword ptr [rax+rax+00h]
0x18001f5b7  jmp     loc_18001F4D7
0x18001f5bc  call    cs:__imp_GetLastError
0x18001f5c3  nop     dword ptr [rax+rax+00h]
0x18001f5c8  test    eax, eax
0x18001f5ca  jnz     loc_18001F2DC
0x18001f5d0  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001f5d7  test    rcx, rcx
0x18001f5da  jz      short loc_18001F638
0x18001f5dc  mov     rax, [rcx]
0x18001f5df  mov     rax, [rax]
0x18001f5e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f5e7  test    rax, rax
0x18001f5ea  cmovnz  rbx, rax
0x18001f5ee  jmp     loc_18001F2DC
0x18001f5f3  call    cs:__imp_GetLastError
0x18001f5fa  nop     dword ptr [rax+rax+00h]
0x18001f5ff  test    eax, eax
0x18001f601  jnz     loc_18001F518
0x18001f607  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001f60e  test    rcx, rcx
0x18001f611  jz      loc_18001F6F8
0x18001f617  mov     rax, [rcx]
0x18001f61a  mov     rax, [rax]
0x18001f61d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f622  test    rax, rax
0x18001f625  cmovnz  rbx, rax
0x18001f629  jmp     loc_18001F518
0x18001f62e  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18001f633  jmp     loc_18001F297
0x18001f638  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001f63f  nop     dword ptr [rax+rax+00h]
0x18001f644  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001f64b  mov     rcx, rax
0x18001f64e  test    rax, rax
0x18001f651  jz      short loc_18001F674
0x18001f653  mov     rax, [rax]
0x18001f656  mov     edx, 7F0h
0x18001f65b  mov     rax, [rax+8]
0x18001f65f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f664  test    eax, eax
0x18001f666  jz      short loc_18001F674
0x18001f668  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001f66f  jmp     loc_18001F5DC
0x18001f674  lea     rcx, qword_1800EB130
0x18001f67b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001f682  jmp     loc_18001F5DC
0x18001f687  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f68e  lea     r8, WPP_2f3388c9edf036fc9dd113cf4a92beb4_Traceguids
0x18001f695  mov     edx, 2Ch ; ','
0x18001f69a  mov     [rsp+68h+var_40], r12
0x18001f69f  mov     r9, r15
0x18001f6a2  mov     [rsp+68h+var_48], r14d
0x18001f6a7  mov     rcx, [rcx+88h]
0x18001f6ae  call    WPP_SF_qDq
0x18001f6b3  jmp     loc_18001F321
0x18001f6b8  mov     r14d, [r15+628h]
0x18001f6bf  jmp     loc_18001F344
0x18001f6c4  lea     rcx, [rbx+68h]
0x18001f6c8  mov     edx, r14d
0x18001f6cb  lea     r8, [rsp+68h+arg_0]
0x18001f6d0  call    ?Find@?$TGenericMap@_KK$0A@$04$0BD@@@QEAAJKPEA_K@Z; TGenericMap<unsigned __int64,ulong,0,5,19>::Find(ulong,unsigned __int64 *)
0x18001f6d5  test    eax, eax
0x18001f6d7  jns     loc_18001F48E
0x18001f6dd  lea     rcx, [rsp+68h+arg_8]; this
0x18001f6e2  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x18001f6e7  jmp     loc_18001F57B
0x18001f6ec  mov     [r15+628h], r14d
0x18001f6f3  jmp     loc_18001F4D7
0x18001f6f8  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18001f6ff  nop     dword ptr [rax+rax+00h]
0x18001f704  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18001f70b  mov     rcx, rax
0x18001f70e  test    rax, rax
0x18001f711  jz      short loc_18001F734
0x18001f713  mov     rax, [rax]
0x18001f716  mov     edx, 7F0h
0x18001f71b  mov     rax, [rax+8]
0x18001f71f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f724  test    eax, eax
0x18001f726  jz      short loc_18001F734
0x18001f728  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001f72f  jmp     loc_18001F617
0x18001f734  lea     rcx, qword_1800EB130
0x18001f73b  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18001f742  jmp     loc_18001F617
```
