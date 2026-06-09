# CLogMgr::_Flush(ulong,ulong,int)

- ea: `0x1800073b4`
- end: `0x180007b35`
- name: `?_Flush@CLogMgr@@QEAAXKKH@Z`
- size: `1921`
- prototype: `void __fastcall(CLogMgr *__hidden this, unsigned int, unsigned int, int)`
- caller_count: `3`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800064e8`
- `0x180006f8c`
- `0x180007b40`

## callees

- `0x1800012c0`
- `0x180001300`
- `0x18000651c`
- `0x1800073b4`
- `0x18000c6b8`
- `0x18000d998`
- `0x18000e6fc`
- `0x18001266c`
- `0x1800127f2`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!FlushViewOfFile` at `0x18000765e`
- `api-ms-win-core-memory-l1-1-0!FlushViewOfFile` at `0x18000765e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ae2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ae2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800076b7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800076b7`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800075aa`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800075aa`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000756f`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000756f`
- `KERNEL32!QueueUserWorkItem` at `0x180007a0a`
- `KERNEL32!QueueUserWorkItem` at `0x180007a0a`

## string_xrefs

- `0x180007af0`: `com\complus\dtc\dtc\log\logmgr\src\logstor.cpp`

## pseudocode

```c
void __fastcall CLogMgr::_Flush(CLogMgr *this, unsigned int a2, unsigned int a3, int a4)
{
  int v4; // r14d
  unsigned int v5; // esi
  int v8; // r13d
  BOOL v9; // r12d
  char *v10; // rbx
  HANDLE *v11; // r14
  char *v12; // rsi
  __int64 v13; // rcx
  _QWORD *v14; // rcx
  __int64 v15; // rax
  __int64 v16; // r8
  __int64 v17; // rdx
  __int64 v18; // r14
  __int64 v19; // r14
  void *v20; // r13
  unsigned __int16 *v21; // rdx
  DWORD v22; // eax
  unsigned __int16 *v23; // rdx
  __int64 v24; // rsi
  int v25; // r15d
  __int64 v26; // rcx
  __int64 v27; // rcx
  int v28; // esi
  unsigned __int16 *v29; // rdx
  __int64 v30; // r14
  unsigned int i; // r15d
  __int64 v32; // rsi
  __int64 v33; // rbx
  int v34; // ebx
  __int64 v35; // r14
  unsigned int v36; // r15d
  __int64 v37; // r9
  unsigned int *v38; // r12
  int v39; // eax
  __int64 v40; // rbx
  int v41; // r13d
  __int64 v42; // r12
  __int64 v43; // rdx
  __int64 v44; // rax
  unsigned int v45; // r14d
  __int64 v46; // rdx
  _DWORD *v47; // r14
  DWORD LastError; // ebx
  ulong v49; // eax
  int v50; // [rsp+50h] [rbp-B8h]
  unsigned int v51; // [rsp+50h] [rbp-B8h]
  int v52; // [rsp+54h] [rbp-B4h]
  ulong v53; // [rsp+54h] [rbp-B4h]
  ulong v54; // [rsp+58h] [rbp-B0h] BYREF
  ulong v55; // [rsp+5Ch] [rbp-ACh] BYREF
  int v56; // [rsp+60h] [rbp-A8h] BYREF
  ulong v57; // [rsp+64h] [rbp-A4h] BYREF
  ulong v58; // [rsp+68h] [rbp-A0h] BYREF
  ulong pExceptionObject; // [rsp+6Ch] [rbp-9Ch] BYREF
  ulong v60; // [rsp+70h] [rbp-98h] BYREF
  ulong v61; // [rsp+74h] [rbp-94h] BYREF
  __int64 v62; // [rsp+78h] [rbp-90h]
  __int64 v63; // [rsp+80h] [rbp-88h]
  char *v64; // [rsp+88h] [rbp-80h]
  ulong v65; // [rsp+90h] [rbp-78h] BYREF
  ulong v66; // [rsp+94h] [rbp-74h] BYREF
  _DWORD v67[4]; // [rsp+98h] [rbp-70h] BYREF
  __int64 v68; // [rsp+A8h] [rbp-60h]
  int v69; // [rsp+B0h] [rbp-58h]
  __int64 v70; // [rsp+B8h] [rbp-50h]
  int v71; // [rsp+C0h] [rbp-48h]
  __int64 v72; // [rsp+C8h] [rbp-40h]
  unsigned int v74; // [rsp+110h] [rbp+8h]

  v4 = a4;
  v5 = a3;
  v8 = 0;
  v9 = 0;
  v50 = 0;
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    while ( 1 )
    {
      LODWORD(v63) = 1;
      v10 = (char *)this + 408;
      v64 = (char *)this + 408;
      (**((void (__fastcall ***)(char *))this + 51))((char *)this + 408);
      if ( *((_DWORD *)this + 3) && !v4 )
      {
LABEL_26:
        (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 8LL))((char *)this + 408);
        goto LABEL_98;
      }
      if ( *((_DWORD *)this + 2) )
      {
        v8 = 1;
        v11 = (HANDLE *)((char *)this + 464);
        v12 = (char *)this + 392;
      }
      else
      {
        if ( a2 && __PAIR64__(a2, v5) < *((_QWORD *)this + 59) )
          goto LABEL_26;
        v13 = *((_QWORD *)this + 50);
        if ( __PAIR64__(a2, v5) > *(_QWORD *)(v13 + 24) )
        {
          pExceptionObject = -2147024809;
          throw &pExceptionObject;
        }
        v50 = *(_DWORD *)(v13 + 24);
        v9 = !a2 || *(_DWORD *)(v13 + 108) && v5 > *(_DWORD *)(v13 + 108);
        v12 = (char *)this + 392;
        v14 = (_QWORD *)*((_QWORD *)this + 49);
        v15 = v14[10];
        if ( v15 )
        {
          v14[8] = v15;
          v14[9] = v14[11];
          v14[11] = 0;
          v14[10] = 0;
        }
        else if ( !v9 )
        {
          goto LABEL_26;
        }
        *((_DWORD *)this + 2) = 1;
        if ( v9 )
        {
          v16 = *(_QWORD *)v12;
          v17 = *(_QWORD *)((*(_DWORD *)(*(_QWORD *)v12 + 120LL) != 0 ? 8 : 0) + *(_QWORD *)v12 + 128LL);
          *(_DWORD *)(v16 + 120) = *(_DWORD *)(*((_QWORD *)this + 49) + 120LL) == 0;
          v18 = *(_QWORD *)(v16 + 96);
          if ( v18 )
          {
            v19 = *(_QWORD *)(v18 + 24);
            v20 = *(void **)(v17 + 24);
            *(_DWORD *)(v19 + 4) = lpCalcCRC(
                                     *(_DWORD *)(v16 + 40) - 8,
                                     (unsigned __int8 *)(v19 + 8),
                                     (unsigned int *)pulCRCTable);
            memcpy_0(v20, (const void *)v19, 0x2000u);
            v8 = 0;
          }
        }
        v11 = (HANDLE *)((char *)this + 464);
        if ( !ResetEvent(*((HANDLE *)this + 58)) )
          UtsemWin32Error(L"ResetEvent fails in CEventSem::Reset()", v21, 0x7F);
      }
      (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 8LL))((char *)this + 408);
      if ( !v8 )
        break;
      v22 = WaitForSingleObjectEx(*v11, 0xFFFFFFFF, 0);
      v5 = a3;
      v4 = a4;
      v8 = 0;
      if ( v22 == -1 )
        UtsemWin32Error(L"WaitForSingleObjectEx fails in CEventSem::Wait()", v23, 0x74);
    }
    v24 = *(_QWORD *)v12;
    v25 = 0;
    while ( 1 )
    {
      v26 = *(_QWORD *)(v24 + 64);
      if ( !v26 )
        break;
      *(_QWORD *)(v24 + 64) = *(_QWORD *)(v26 + 48);
      v25 = *(_DWORD *)v26 + *(_DWORD *)(v26 + 4);
      CLogStorage::_UnmapBuffer((CLogStorage *)v24, (LPCVOID *)v26, 1);
    }
    *(_QWORD *)(v24 + 72) = 0;
    if ( v9 )
    {
      v27 = v24 + 128;
      if ( !*(_DWORD *)(v24 + 120) )
        v27 = v24 + 136;
      if ( !FlushViewOfFile(*(LPCVOID *)(*(_QWORD *)v27 + 24LL), *(unsigned int *)(*(_QWORD *)v27 + 4LL)) )
      {
        LastError = GetLastError();
        TraceFile(LastError, "FlushViewOfFile", "com\\complus\\dtc\\dtc\\log\\logmgr\\src\\logstor.cpp", 0x264);
        v55 = LastError;
        throw &v55;
      }
      v28 = v50;
    }
    else
    {
      v28 = v25;
    }
    LODWORD(v63) = 1;
    v64 = (char *)this + 408;
    (**(void (__fastcall ***)(char *))v10)((char *)this + 408);
    *((_DWORD *)this + 2) = 0;
    *((_DWORD *)this + 119) = *(_DWORD *)(*((_QWORD *)this + 50) + 28LL);
    *((_DWORD *)this + 118) = v28;
    if ( !SetEvent(*v11) )
      UtsemWin32Error(L"SetEvent fails in CEventSem::Set()", v29, 0x7A);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v10 + 8LL))((char *)this + 408);
    v4 = a4;
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &long `RTTI Type Descriptor', (long *)v67) )
    {
      v49 = v67[0];
      v53 = v67[0];
      if ( *((_QWORD *)this + 3) )
      {
        (*(void (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)this + 3) + 24LL))(
          *((_QWORD *)this + 3),
          4097,
          4);
        v49 = v53;
      }
      v60 = v49;
      throw &v60;
    }
    if ( __eh34_catch_type(0, &unsigned long `RTTI Type Descriptor', &v54) )
    {
      if ( *((_QWORD *)this + 3) )
        (*(void (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)this + 3) + 24LL))(
          *((_QWORD *)this + 3),
          4097,
          4);
      v61 = v54;
      throw &v61;
    }
  }
LABEL_98:
  if ( !v4 && *(_WORD *)(*((_QWORD *)this + 50) + 88LL) )
  {
    v30 = *((_QWORD *)this + 37);
    for ( i = 0; ; ++i )
    {
      v51 = i;
      v62 = v30;
      if ( i >= *(unsigned __int16 *)(*((_QWORD *)this + 50) + 88LL) )
        break;
      v32 = *(_QWORD *)(v30 + 20);
      if ( v32 )
      {
        v67[2] = 1;
        v33 = v32 + 232;
        v63 = v32 + 232;
        v68 = v32 + 232;
        (**(void (__fastcall ***)(__int64))(v32 + 232))(v32 + 232);
        if ( *(_DWORD *)(v32 + 288) && !*(_DWORD *)(v32 + 312) )
        {
          if ( !*(_QWORD *)(v32 + 296) )
          {
            v56 = -2147418113;
            throw (long *)&v56;
          }
          v34 = 0;
          v69 = 1;
          v35 = v32 + 176;
          v70 = v32 + 176;
          (**(void (__fastcall ***)(__int64))(v32 + 176))(v32 + 176);
          v36 = *(_DWORD *)(v32 + 308);
          while ( 1 )
          {
            v37 = *(_QWORD *)(v32 + 296);
            if ( *(_DWORD *)(v37 + 24LL * v36 + 16) != 1
              && *(_QWORD *)(v37 + 24LL * v36)
              && (*(unsigned int (__fastcall **)(char *, _QWORD, _QWORD))(*((_QWORD *)this + 18) + 24LL))(
                   (char *)this + 144,
                   *(_QWORD *)(v37 + 24LL * v36),
                   *((_QWORD *)this + 59)) == 1 )
            {
              break;
            }
            v38 = (unsigned int *)(v32 + 304);
            if ( v36 == *(_DWORD *)(v32 + 304) )
              goto LABEL_56;
            if ( v36 )
              --v36;
            else
              v36 = *(_DWORD *)(v32 + 288) - 1;
          }
          v34 = 1;
          *(_DWORD *)(v32 + 292) = 0;
          v38 = (unsigned int *)(v32 + 304);
LABEL_56:
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 8LL))(v32 + 176);
          if ( v34 )
          {
            v74 = *v38;
            v39 = 1;
            v52 = 1;
            v40 = 0;
            v41 = -1;
            while ( v39 )
            {
              v71 = 1;
              v72 = v35;
              (**(void (__fastcall ***)(__int64))v35)(v35);
              v42 = 0;
              v43 = *(_QWORD *)(v32 + 296);
              if ( *(_DWORD *)(v43 + 24LL * v74 + 16)
                || (*(unsigned int (__fastcall **)(char *, _QWORD, _QWORD))(*((_QWORD *)this + 18) + 24LL))(
                     (char *)this + 144,
                     *(_QWORD *)(v43 + 24LL * v74),
                     *((_QWORD *)this + 59)) != 1 )
              {
                v45 = v74;
                if ( v41 == -1 )
                  v41 = v74;
              }
              else
              {
                v44 = *(_QWORD *)(v32 + 296);
                if ( *(_QWORD *)(v44 + 24LL * v74 + 8) )
                {
                  v42 = *(_QWORD *)(v44 + 24LL * v74 + 8);
                  v40 = *(_QWORD *)(v44 + 24LL * v74);
                  *(_QWORD *)(v44 + 24LL * v74 + 8) = 0;
                  *(_QWORD *)(*(_QWORD *)(v32 + 296) + 24LL * v74) = 0;
                  *(_DWORD *)(*(_QWORD *)(v32 + 296) + 24LL * v74 + 16) = 0;
                }
                v45 = v74;
              }
              if ( v41 < 0 )
                v46 = (v45 + 1) % *(_DWORD *)(v32 + 288);
              else
                v46 = (unsigned int)v41;
              *(_DWORD *)(v32 + 304) = v46;
              if ( v45 == v36 )
              {
                v52 = 0;
                if ( v36 == *(_DWORD *)(v32 + 308) && v41 == -1 )
                {
                  *(_DWORD *)(v32 + 312) = 1;
                  *(_DWORD *)(v32 + 308) = 0;
                  *(_DWORD *)(v32 + 304) = 0;
                }
              }
              (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)(v32 + 176) + 8LL))(v32 + 176, v46, 0);
              if ( v42 )
              {
                if ( __eh34_try(-1, 2) )
                {
                  __eh34_scope_strut(2);
                  if ( g_fNoParallelLogFlushNotification == 1 )
                  {
                    (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v42 + 8LL))(v42, 0, v40);
                  }
                  else
                  {
                    v47 = operator new(0x18u);
                    if ( v47 )
                    {
                      *(_QWORD *)v47 = v42;
                      v47[2] = 0;
                      *((_QWORD *)v47 + 2) = v40;
                      if ( !QueueUserWorkItem((LPTHREAD_START_ROUTINE)AppendCallbackThreadRoutine, v47, 0x10u) )
                      {
                        operator delete(v47);
                        (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v42 + 8LL))(v42, 0, v40);
                      }
                    }
                    else
                    {
                      (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v42 + 8LL))(v42, 0, v40);
                    }
                    v45 = v74;
                  }
                }
                if ( __eh34_catch(2) )
                {
                  if ( __eh34_catch_type(2, &long `RTTI Type Descriptor', (long *)&v65) )
                  {
                    v57 = v65;
                    throw &v57;
                  }
                  if ( __eh34_catch_type(2, &unsigned long `RTTI Type Descriptor', &v66) )
                  {
                    v58 = v66;
                    throw &v58;
                  }
                }
              }
              v74 = (v45 + 1) % *(_DWORD *)(v32 + 288);
              v35 = v32 + 176;
              v39 = v52;
            }
          }
          i = v51;
          v30 = v62;
          v33 = v63;
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 8LL))(v33);
      }
      v30 += 44;
    }
  }
  *((_QWORD *)this + 76) = CLogMgr::Get64BitTickCount() + *((unsigned int *)this + 126);
}

```

## disassembly

```asm
0x1800073b4  mov     [rsp+arg_18], r9d
0x1800073b9  mov     [rsp+arg_10], r8d
0x1800073be  mov     [rsp+arg_0], rcx
0x1800073c3  push    rbx
0x1800073c4  push    rsi
0x1800073c5  push    rdi
0x1800073c6  push    r12
0x1800073c8  push    r13
0x1800073ca  push    r14
0x1800073cc  push    r15
0x1800073ce  sub     rsp, 0D0h
0x1800073d5  mov     r14d, r9d
0x1800073d8  mov     esi, r8d
0x1800073db  mov     r15d, edx
0x1800073de  mov     rdi, rcx
0x1800073e1  xor     r13d, r13d
0x1800073e4  mov     r12d, r13d
0x1800073e7  mov     [rsp+108h+var_B8], r13d
0x1800073ec  mov     dword ptr [rsp+108h+var_88], 1
0x1800073f7  lea     rbx, [rdi+198h]
0x1800073fe  mov     [rsp+108h+var_80], rbx
0x180007406  mov     rax, [rbx]
0x180007409  mov     rcx, rbx
0x18000740c  mov     rax, [rax]
0x18000740f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007414  nop
0x180007415  cmp     [rdi+0Ch], r13d
0x180007419  jz      short loc_18000743B
0x18000741b  test    r14d, r14d
0x18000741e  jnz     short loc_18000743B
0x180007420  mov     rax, [rbx]
0x180007423  mov     rcx, rbx
0x180007426  mov     rax, [rax+8]
0x18000742a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000742f  nop
0x180007430  mov     r12d, 1
0x180007436  jmp     loc_1800076EB
0x18000743b  cmp     [rdi+8], r13d
0x18000743f  jz      short loc_18000745A
0x180007441  mov     r13d, 1
0x180007447  lea     r14, [rdi+1D0h]
0x18000744e  lea     rsi, [rdi+188h]
0x180007455  jmp     loc_18000758A
0x18000745a  test    r15d, r15d
0x18000745d  jz      short loc_180007484
0x18000745f  cmp     r15d, [rdi+1DCh]
0x180007466  ja      short loc_180007484
0x180007468  jnz     short loc_180007472
0x18000746a  cmp     esi, [rdi+1D8h]
0x180007470  jnb     short loc_180007484
0x180007472  mov     rax, [rbx]
0x180007475  mov     rcx, rbx
0x180007478  mov     rax, [rax+8]
0x18000747c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007481  nop
0x180007482  jmp     short loc_180007430
0x180007484  mov     rcx, [rdi+190h]
0x18000748b  cmp     r15d, [rcx+1Ch]
0x18000748f  ja      loc_180007AC8
0x180007495  jnz     short loc_1800074A0
0x180007497  cmp     esi, [rcx+18h]
0x18000749a  ja      loc_180007AC8
0x1800074a0  mov     eax, [rcx+18h]
0x1800074a3  mov     [rsp+108h+var_B8], eax
0x1800074a7  test    r15d, r15d
0x1800074aa  jz      short loc_1800074BC
0x1800074ac  cmp     [rcx+6Ch], r13d
0x1800074b0  jbe     short loc_1800074B7
0x1800074b2  cmp     esi, [rcx+6Ch]
0x1800074b5  ja      short loc_1800074BC
0x1800074b7  mov     r12d, r13d
0x1800074ba  jmp     short loc_1800074C2
0x1800074bc  mov     r12d, 1
0x1800074c2  lea     rsi, [rdi+188h]
0x1800074c9  mov     rcx, [rsi]
0x1800074cc  mov     rax, [rcx+50h]
0x1800074d0  test    rax, rax
0x1800074d3  jz      loc_1800075E2
0x1800074d9  mov     [rcx+40h], rax
0x1800074dd  mov     rax, [rcx+58h]
0x1800074e1  mov     [rcx+48h], rax
0x1800074e5  mov     [rcx+58h], r13
0x1800074e9  mov     [rcx+50h], r13
0x1800074ed  mov     dword ptr [rdi+8], 1
0x1800074f4  test    r12d, r12d
0x1800074f7  jz      short loc_180007565
0x1800074f9  mov     r8, [rsi]
0x1800074fc  mov     eax, [r8+78h]
0x180007500  neg     eax
0x180007502  sbb     rcx, rcx
0x180007505  and     ecx, 8
0x180007508  mov     rdx, [rcx+r8+80h]
0x180007510  mov     eax, r13d
0x180007513  cmp     [r8+78h], r13d
0x180007517  setz    al
0x18000751a  mov     [r8+78h], eax
0x18000751e  mov     r14, [r8+60h]
0x180007522  test    r14, r14
0x180007525  jz      short loc_180007565
0x180007527  mov     r14, [r14+18h]
0x18000752b  mov     r13, [rdx+18h]
0x18000752f  lea     rdx, [r14+8]
0x180007533  mov     ecx, [r8+28h]
0x180007537  sub     ecx, 8
0x18000753a  mov     r8, cs:?pulCRCTable@@3PEAKEA; ulong * pulCRCTable
0x180007541  mov     rax, cs:?lpCalcCRC@@3P6AKIPEAEPEAK@ZEA; ulong (*lpCalcCRC)(uint,uchar *,ulong *)
0x180007548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000754d  mov     [r14+4], eax
0x180007551  mov     r8d, 2000h; Size
0x180007557  mov     rdx, r14; Src
0x18000755a  mov     rcx, r13; void *
0x18000755d  call    memcpy_0
0x180007562  xor     r13d, r13d
0x180007565  lea     r14, [rdi+1D0h]
0x18000756c  mov     rcx, [r14]; hEvent
0x18000756f  call    cs:__imp_ResetEvent
0x180007575  test    eax, eax
0x180007577  jnz     short loc_18000758A
0x180007579  lea     r8d, [rax+7Fh]; unsigned int
0x18000757d  lea     rcx, aReseteventFail; "ResetEvent fails in CEventSem::Reset()"
0x180007584  call    ?UtsemWin32Error@@YAXPEAG0K@Z; UtsemWin32Error(ushort *,ushort *,ulong)
0x180007589  nop
0x18000758a  mov     rax, [rbx]
0x18000758d  mov     rcx, rbx
0x180007590  mov     rax, [rax+8]
0x180007594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007599  nop
0x18000759a  test    r13d, r13d
0x18000759d  jz      short loc_180007600
0x18000759f  xor     r8d, r8d; bAlertable
0x1800075a2  or      ebx, 0FFFFFFFFh
0x1800075a5  mov     edx, ebx; dwMilliseconds
0x1800075a7  mov     rcx, [r14]; hHandle
0x1800075aa  call    cs:__imp_WaitForSingleObjectEx
0x1800075b0  cmp     eax, ebx
0x1800075b2  mov     esi, [rsp+108h+arg_10]
0x1800075b9  mov     r14d, [rsp+108h+arg_18]
0x1800075c1  mov     r13d, 0
0x1800075c7  jnz     loc_1800073EC
0x1800075cd  lea     r8d, [r13+74h]; unsigned int
0x1800075d1  lea     rcx, aWaitforsingleo; "WaitForSingleObjectEx fails in CEventSe"...
0x1800075d8  call    ?UtsemWin32Error@@YAXPEAG0K@Z; UtsemWin32Error(ushort *,ushort *,ulong)
0x1800075dd  jmp     loc_1800073EC
0x1800075e2  test    r12d, r12d
0x1800075e5  jnz     loc_1800074ED
0x1800075eb  mov     rax, [rbx]
0x1800075ee  mov     rcx, rbx
0x1800075f1  mov     rax, [rax+8]
0x1800075f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075fa  nop
0x1800075fb  jmp     loc_180007430
0x180007600  mov     rsi, [rsi]
0x180007603  xor     r13d, r13d
0x180007606  mov     r15d, r13d
0x180007609  mov     rcx, [rsi+40h]
0x18000760d  mov     rax, rcx
0x180007610  test    rcx, rcx
0x180007613  jz      short loc_180007637
0x180007615  mov     rax, [rcx+30h]
0x180007619  mov     [rsi+40h], rax
0x18000761d  mov     r15d, [rcx+4]
0x180007621  add     r15d, [rcx]
0x180007624  mov     r8d, 1; int
0x18000762a  mov     rdx, rcx; struct CBuffer *
0x18000762d  mov     rcx, rsi; this
0x180007630  call    ?_UnmapBuffer@CLogStorage@@AEAAXPEAVCBuffer@@H@Z; CLogStorage::_UnmapBuffer(CBuffer *,int)
0x180007635  jmp     short loc_180007609
0x180007637  mov     [rsi+48h], r13
0x18000763b  test    r12d, r12d
0x18000763e  jz      short loc_180007672
0x180007640  cmp     [rsi+78h], r13d
0x180007644  lea     rcx, [rsi+80h]
0x18000764b  jnz     short loc_180007654
0x18000764d  lea     rcx, [rsi+88h]
0x180007654  mov     rcx, [rcx]
0x180007657  mov     edx, [rcx+4]; dwNumberOfBytesToFlush
0x18000765a  mov     rcx, [rcx+18h]; lpBaseAddress
0x18000765e  call    cs:__imp_FlushViewOfFile
0x180007664  test    eax, eax
0x180007666  jz      loc_180007AE2
0x18000766c  mov     esi, [rsp+108h+var_B8]
0x180007670  jmp     short loc_180007675
0x180007672  mov     esi, r15d
0x180007675  mov     r12d, 1
0x18000767b  mov     dword ptr [rsp+108h+var_88], r12d
0x180007683  mov     [rsp+108h+var_80], rbx
0x18000768b  mov     rax, [rbx]
0x18000768e  mov     rcx, rbx
0x180007691  mov     rax, [rax]
0x180007694  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007699  nop
0x18000769a  mov     [rdi+8], r13d
0x18000769e  mov     rax, [rdi+190h]
0x1800076a5  mov     ecx, [rax+1Ch]
0x1800076a8  mov     [rdi+1DCh], ecx
0x1800076ae  mov     [rdi+1D8h], esi
0x1800076b4  mov     rcx, [r14]; hEvent
0x1800076b7  call    cs:__imp_SetEvent
0x1800076bd  test    eax, eax
0x1800076bf  jnz     short loc_1800076D3
0x1800076c1  lea     r8d, [r12+79h]; unsigned int
0x1800076c6  lea     rcx, aSeteventFailsI; "SetEvent fails in CEventSem::Set()"
0x1800076cd  call    ?UtsemWin32Error@@YAXPEAG0K@Z; UtsemWin32Error(ushort *,ushort *,ulong)
0x1800076d2  nop
0x1800076d3  mov     rax, [rbx]
0x1800076d6  mov     rcx, rbx
0x1800076d9  mov     rax, [rax+8]
0x1800076dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076e2  nop
0x1800076e3  mov     r14d, [rsp+108h+arg_18]
0x1800076eb  test    r14d, r14d
0x1800076ee  jnz     loc_180007AA0
0x1800076f4  mov     rax, [rdi+190h]
0x1800076fb  cmp     [rax+58h], r13w
0x180007700  jbe     loc_180007AA0
0x180007706  mov     r14, [rdi+128h]
0x18000770d  mov     r15d, r13d
0x180007710  mov     [rsp+108h+var_B8], r15d
0x180007715  mov     [rsp+108h+var_90], r14
0x18000771a  mov     rax, [rdi+190h]
0x180007721  movzx   ecx, word ptr [rax+58h]
0x180007725  cmp     r15d, ecx
0x180007728  jnb     loc_180007AA0
0x18000772e  mov     rsi, [r14+14h]
0x180007732  test    rsi, rsi
0x180007735  jz      loc_180007A94
0x18000773b  mov     [rsp+108h+var_68], r12d
0x180007743  lea     rbx, [rsi+0E8h]
0x18000774a  mov     [rsp+108h+var_88], rbx
0x180007752  mov     [rsp+108h+var_60], rbx
0x18000775a  mov     rax, [rbx]
0x18000775d  mov     rcx, rbx
0x180007760  mov     rax, [rax]
0x180007763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007768  nop
0x180007769  cmp     [rsi+120h], r13d
0x180007770  jbe     loc_180007A7F
0x180007776  cmp     [rsi+138h], r13d
0x18000777d  jnz     loc_180007A7F
0x180007783  cmp     [rsi+128h], r13
0x18000778a  jz      loc_180007B1B
0x180007790  mov     ebx, r13d
0x180007793  mov     [rsp+108h+var_58], r12d
0x18000779b  lea     r14, [rsi+0B0h]
0x1800077a2  mov     [rsp+108h+var_50], r14
0x1800077aa  mov     rax, [r14]
0x1800077ad  mov     rcx, r14
0x1800077b0  mov     rax, [rax]
0x1800077b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077b8  nop
0x1800077b9  mov     r15d, [rsi+134h]
0x1800077c0  mov     eax, r15d
0x1800077c3  lea     rdx, [rax+rax*2]
0x1800077c7  mov     r9, [rsi+128h]
0x1800077ce  cmp     [r9+rdx*8+10h], r12d
0x1800077d3  jz      short loc_1800077FE
0x1800077d5  cmp     [r9+rdx*8], r13
0x1800077d9  jz      short loc_1800077FE
0x1800077db  lea     rcx, [rdi+90h]
0x1800077e2  mov     rax, [rcx]
0x1800077e5  mov     r8, [rdi+1D8h]
0x1800077ec  mov     rdx, [r9+rdx*8]
0x1800077f0  mov     rax, [rax+18h]
0x1800077f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077f9  cmp     eax, r12d
0x1800077fc  jz      short loc_180007827
0x1800077fe  lea     r12, [rsi+130h]
0x180007805  cmp     r15d, [r12]
0x180007809  jz      short loc_180007838
0x18000780b  mov     r12d, 1
0x180007811  test    r15d, r15d
0x180007814  jnz     short loc_180007822
0x180007816  mov     r15d, [rsi+120h]
0x18000781d  sub     r15d, r12d
0x180007820  jmp     short loc_1800077C0
0x180007822  dec     r15d
0x180007825  jmp     short loc_1800077C0
0x180007827  mov     ebx, r12d
0x18000782a  mov     [rsi+124h], r13d
0x180007831  lea     r12, [rsi+130h]
0x180007838  mov     rax, [r14]
0x18000783b  mov     rcx, r14
0x18000783e  mov     rax, [rax+8]
0x180007842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007847  nop
0x180007848  test    ebx, ebx
0x18000784a  jz      loc_180007A62
0x180007850  mov     eax, [r12]
0x180007854  mov     dword ptr [rsp+108h+arg_0], eax
0x18000785b  mov     r12d, 1
0x180007861  mov     eax, r12d
0x180007864  mov     [rsp+108h+var_B4], eax
0x180007868  mov     rbx, r13
0x18000786b  or      r13d, 0FFFFFFFFh
0x18000786f  test    eax, eax
0x180007871  jz      loc_180007A6A
0x180007877  mov     [rsp+108h+var_48], r12d
0x18000787f  mov     [rsp+108h+var_40], r14
0x180007887  mov     rax, [r14]
0x18000788a  mov     rcx, r14
  ... truncated ...
```
