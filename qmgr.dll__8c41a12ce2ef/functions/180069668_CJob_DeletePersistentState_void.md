# CJob::DeletePersistentState(void)

- ea: `0x180069668`
- end: `0x180069b8a`
- name: `?DeletePersistentState@CJob@@IEAAJXZ`
- size: `1314`
- prototype: `__int64 __fastcall(CJob *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18009c50c`
- `0x1800d59dc`

## callees

- `0x18000b4d0`
- `0x1800292a0`
- `0x180034760`
- `0x180069668`
- `0x180069b90`
- `0x1800a3de8`
- `0x1800ab7fc`
- `0x1800b6d34`
- `0x1800f9948`
- `0x18010f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800696d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800696d1`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180069739`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180069a08`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180069739`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180069a08`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180069a73`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180069a73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800698f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800698f9`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CJob::DeletePersistentState(CJob *this)
{
  TaskScheduler *v2; // r15
  int v3; // r14d
  int v4; // eax
  int v5; // ecx
  int v6; // edx
  int v7; // ebx
  __int64 v8; // r12
  int v9; // eax
  __int64 v10; // r13
  int v11; // eax
  CFile **i; // rbx
  CFile *v13; // rax
  int v14; // eax
  void *v15; // rax
  size_t v16; // rax
  int v17; // eax
  int v18; // eax
  ULONGLONG v19; // rax
  EVENT_LOG *v20; // rcx
  ULONGLONG v21; // rbx
  __int64 result; // rax
  int v23; // eax
  const ComError *v24; // rbx
  PROPVARIANT pvar[2]; // [rsp+30h] [rbp-328h] BYREF
  __int64 v26; // [rsp+40h] [rbp-318h]
  const ComError *v27[2]; // [rsp+48h] [rbp-310h] BYREF
  int v28; // [rsp+58h] [rbp-300h]
  __int64 v29; // [rsp+60h] [rbp-2F8h]
  bool v30; // [rsp+68h] [rbp-2F0h]
  __int64 v31; // [rsp+70h] [rbp-2E8h]
  char v32; // [rsp+78h] [rbp-2E0h]
  void **pExceptionObject; // [rsp+80h] [rbp-2D8h] BYREF
  __int128 v34; // [rsp+88h] [rbp-2D0h]
  int v35; // [rsp+98h] [rbp-2C0h]
  int v36; // [rsp+9Ch] [rbp-2BCh]
  int v37; // [rsp+A0h] [rbp-2B8h]
  void **v38; // [rsp+E0h] [rbp-278h] BYREF
  __int128 v39; // [rsp+E8h] [rbp-270h]
  int v40; // [rsp+F8h] [rbp-260h]
  int v41; // [rsp+FCh] [rbp-25Ch]
  int v42; // [rsp+100h] [rbp-258h]
  void **v43; // [rsp+140h] [rbp-218h] BYREF
  __int128 v44; // [rsp+148h] [rbp-210h]
  int v45; // [rsp+158h] [rbp-200h]
  int v46; // [rsp+15Ch] [rbp-1FCh]
  int v47; // [rsp+160h] [rbp-1F8h]
  void **v48; // [rsp+1A0h] [rbp-1B8h] BYREF
  __int128 v49; // [rsp+1A8h] [rbp-1B0h]
  int v50; // [rsp+1B8h] [rbp-1A0h]
  int v51; // [rsp+1BCh] [rbp-19Ch]
  int v52; // [rsp+1C0h] [rbp-198h]
  void **v53; // [rsp+200h] [rbp-158h] BYREF
  __int128 v54; // [rsp+208h] [rbp-150h]
  int v55; // [rsp+218h] [rbp-140h]
  int v56; // [rsp+21Ch] [rbp-13Ch]
  int v57; // [rsp+220h] [rbp-138h]
  void **v58; // [rsp+260h] [rbp-F8h] BYREF
  __int128 v59; // [rsp+268h] [rbp-F0h]
  int v60; // [rsp+278h] [rbp-E0h]
  int v61; // [rsp+27Ch] [rbp-DCh]
  int v62; // [rsp+280h] [rbp-D8h]
  void **v63; // [rsp+2C0h] [rbp-98h] BYREF
  __int128 v64; // [rsp+2C8h] [rbp-90h]
  int v65; // [rsp+2D8h] [rbp-80h]
  int v66; // [rsp+2DCh] [rbp-7Ch]
  int v67; // [rsp+2E0h] [rbp-78h]
  __int64 v68; // [rsp+360h] [rbp+8h] BYREF
  BOOL v69; // [rsp+368h] [rbp+10h]
  ULONGLONG TickCount64; // [rsp+370h] [rbp+18h]

  if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids, this);
  v2 = (CJobManager *)((char *)g_Manager + 520);
  v27[1] = (CJobManager *)((char *)g_Manager + 520);
  v3 = 0;
  v28 = 0;
  if ( *((_DWORD *)v2 + 14) == GetCurrentThreadId() )
  {
    v4 = 0;
    v5 = 0;
    v6 = 0;
    v7 = 0;
  }
  else
  {
    v3 = 1;
    v28 = 1;
    TaskScheduler::LockWriter(v2, 0);
    v4 = 1;
    v5 = 1;
    v6 = 1;
    v7 = 1;
  }
  try
  {
    if ( *((_BYTE *)this + 936) )
    {
      v7 = v6;
      v5 = v4;
    }
    else
    {
      v68 = *((_QWORD *)this + 122);
      if ( v68 )
      {
        TickCount64 = GetTickCount64();
        v8 = *((_QWORD *)g_Manager + 83);
        v29 = v8;
        LOBYTE(v68) = 0;
        v9 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v8 + 24LL))(v8, &v68);
        if ( v9 < 0 )
        {
          v34 = 0;
          pExceptionObject = &ComError::`vftable';
          v35 = v9;
          v36 = 16;
          v37 = 1;
          throw (ComError *)&pExceptionObject;
        }
        v69 = (_BYTE)v68 == 0;
        v30 = (_BYTE)v68 == 0;
        v10 = *((_QWORD *)g_Manager + 83);
        v31 = v10;
        v32 = 0;
        v11 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 40LL))(v10);
        if ( v11 < 0 )
        {
          v39 = 0;
          v38 = &ComError::`vftable';
          v40 = v11;
          v41 = 15;
          v42 = 1;
          throw (ComError *)&v38;
        }
        for ( i = (CFile **)*((_QWORD *)this + 106); i != *((CFile ***)this + 107); ++i )
        {
          v23 = CFile::DeletePersistentState(*i);
          if ( v23 < 0 )
          {
            v64 = 0;
            v63 = &ComError::`vftable';
            v65 = v23;
            v66 = 1193;
            v67 = 1;
            throw (ComError *)&v63;
          }
        }
        if ( (unsigned int)(*((_DWORD *)this + 166) - 1) <= 1 )
        {
          v13 = (CFile *)(*(__int64 (__fastcall **)(CJob *, __int64))(*(_QWORD *)this + 384LL))(this, 0xFFFFFFFFLL);
          if ( v13 )
          {
            v14 = CFile::DeletePersistentState(v13);
            if ( v14 < 0 )
            {
              v44 = 0;
              v43 = &ComError::`vftable';
              v45 = v14;
              v46 = 1201;
              v47 = 1;
              throw (ComError *)&v43;
            }
          }
        }
        pvar[0] = 0;
        v26 = 0;
        v15 = CoTaskMemAlloc(0x10u);
        pvar[1] = v15;
        if ( !v15 )
        {
          v59 = 0;
          v58 = &ComError::`vftable';
          v60 = -2147024882;
          v61 = 1206;
          v62 = 1;
          throw (ComError *)&v58;
        }
        v16 = CTCoAllocPolicy::_CoTaskMemSize(v15);
        memset_0(pvar[1], 0, v16);
        LOWORD(pvar[0]) = 72;
        *(_OWORD *)pvar[1] = *(_OWORD *)((char *)this + 676);
        v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, PROPVARIANT *))(**((_QWORD **)g_Manager + 83) + 80LL))(
                *((_QWORD *)g_Manager + 83),
                0,
                pvar);
        if ( v17 < 0 )
        {
          v49 = 0;
          v48 = &ComError::`vftable';
          v50 = v17;
          v51 = 1209;
          v52 = 1;
          throw (ComError *)&v48;
        }
        v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 48LL))(v10);
        if ( v18 < 0 )
        {
          v54 = 0;
          v53 = &ComError::`vftable';
          v55 = v18;
          v56 = 20;
          v57 = 1;
          throw (ComError *)&v53;
        }
        v19 = GetTickCount64();
        v21 = v19 - TickCount64;
        if ( v19 - TickCount64 > 0x3A98 )
          EVENT_LOG::ReportSerialize(v20, v19 - TickCount64);
        v68 = 0;
        *((_QWORD *)this + 122) = 0;
        if ( WPP_GLOBAL_Control != (EVENT_LOG *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids, v21);
        PropVariantClear(pvar);
        if ( v69 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 32LL))(v8);
        for ( ; v3; --v3 )
          TaskScheduler::UnlockWriter(v2);
        return 0;
      }
    }
    if ( v5 )
    {
      do
      {
        TaskScheduler::UnlockWriter(v2);
        --v7;
      }
      while ( v7 );
    }
    result = 0;
  }
  catch ( const ComError *v27 )
  {
    if ( WPP_GLOBAL_Control == (EVENT_LOG *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      v24 = v27[0];
    }
    else
    {
      v24 = v27[0];
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        61,
        &WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids,
        *((unsigned int *)v27[0] + 6),
        *((_DWORD *)v27[0] + 7));
    }
    LODWORD(v68) = *((_DWORD *)v24 + 6);
    return (unsigned int)v68;
  }
  return result;
}

```

## disassembly

```asm
0x180069668  push    rbx
0x18006966a  push    rsi
0x18006966b  push    rdi
0x18006966c  push    r12
0x18006966e  push    r13
0x180069670  push    r14
0x180069672  push    r15
0x180069674  sub     rsp, 320h
0x18006967b  mov     rsi, rcx
0x18006967e  lea     rax, WPP_GLOBAL_Control
0x180069685  mov     rcx, cs:WPP_GLOBAL_Control
0x18006968c  mov     edi, 1
0x180069691  cmp     rcx, rax
0x180069694  jz      short loc_1800696B3
0x180069696  test    [rcx+1Ch], dil
0x18006969a  jz      short loc_1800696B3
0x18006969c  lea     edx, [rdi+3Ah]
0x18006969f  mov     r9, rsi
0x1800696a2  lea     r8, WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids
0x1800696a9  mov     rcx, [rcx+10h]
0x1800696ad  call    WPP_SF_q
0x1800696b2  nop
0x1800696b3  mov     r15, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x1800696ba  add     r15, 208h
0x1800696c1  mov     [rsp+358h+var_308], r15
0x1800696c6  xor     r13d, r13d
0x1800696c9  mov     r14d, r13d
0x1800696cc  mov     [rsp+358h+var_300], r13d
0x1800696d1  call    cs:__imp_GetCurrentThreadId
0x1800696d7  cmp     [r15+38h], eax
0x1800696db  jnz     short loc_1800696EB
0x1800696dd  mov     eax, r13d
0x1800696e0  mov     ecx, r13d
0x1800696e3  mov     edx, r13d
0x1800696e6  mov     ebx, r13d
0x1800696e9  jmp     short loc_180069704
0x1800696eb  mov     r14d, edi
0x1800696ee  mov     [rsp+358h+var_300], edi
0x1800696f2  xor     edx, edx; void *
0x1800696f4  mov     rcx, r15; this
0x1800696f7  call    ?LockWriter@TaskScheduler@@QEAA_NPEAX@Z; TaskScheduler::LockWriter(void *)
0x1800696fc  mov     eax, edi
0x1800696fe  mov     ecx, edi
0x180069700  mov     edx, edi
0x180069702  mov     ebx, edi
0x180069704  cmp     [rsi+3A8h], r13b
0x18006970b  jnz     loc_180069B56
0x180069711  mov     eax, [rsi+3D4h]
0x180069717  mov     dword ptr [rsp+358h+arg_0+4], eax
0x18006971e  mov     eax, [rsi+3D0h]
0x180069724  mov     dword ptr [rsp+358h+arg_0], eax
0x18006972b  cmp     [rsp+358h+arg_0], r13
0x180069733  jz      loc_180069B5A
0x180069739  call    cs:__imp_GetTickCount64
0x18006973f  mov     [rsp+358h+arg_10], rax
0x180069747  mov     rcx, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x18006974e  mov     r12, [rcx+298h]
0x180069755  mov     [rsp+358h+var_2F8], r12
0x18006975a  movzx   ebx, r13b
0x18006975e  mov     byte ptr [rsp+358h+arg_0], r13b
0x180069766  mov     rcx, [r12]
0x18006976a  mov     rax, [rcx+18h]
0x18006976e  lea     rdx, [rsp+358h+arg_0]
0x180069776  mov     rcx, r12
0x180069779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006977e  test    eax, eax
0x180069780  jns     short loc_1800697C9
0x180069782  xorps   xmm0, xmm0
0x180069785  movups  [rsp+358h+var_2D0], xmm0
0x18006978d  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180069794  mov     [rsp+358h+pExceptionObject], rcx
0x18006979c  mov     [rsp+358h+var_2C0], eax
0x1800697a3  mov     [rsp+358h+var_2BC], 10h
0x1800697ae  mov     [rsp+358h+var_2B8], edi
0x1800697b5  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800697bc  lea     rcx, [rsp+358h+pExceptionObject]; pExceptionObject
0x1800697c4  call    _CxxThrowException_0
0x1800697c9  mov     eax, ebx
0x1800697cb  cmp     byte ptr [rsp+358h+arg_0], r13b
0x1800697d3  cmovz   eax, edi
0x1800697d6  mov     [rsp+358h+arg_8], eax
0x1800697dd  mov     [rsp+358h+var_2F0], al
0x1800697e1  mov     rax, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x1800697e8  mov     r13, [rax+298h]
0x1800697ef  mov     [rsp+358h+var_2E8], r13
0x1800697f4  mov     [rsp+358h+var_2E0], 0
0x1800697f9  mov     rax, [r13+0]
0x1800697fd  mov     rcx, r13
0x180069800  mov     rax, [rax+28h]
0x180069804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069809  test    eax, eax
0x18006980b  jns     short loc_180069855
0x18006980d  xorps   xmm0, xmm0
0x180069810  movups  [rsp+358h+var_270], xmm0
0x180069818  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x18006981f  mov     [rsp+358h+var_278], rcx
0x180069827  mov     [rsp+358h+var_260], eax
0x18006982e  mov     [rsp+358h+var_25C], 0Fh
0x180069839  mov     [rsp+358h+var_258], edi
0x180069840  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180069847  lea     rcx, [rsp+358h+var_278]; pExceptionObject
0x18006984f  call    _CxxThrowException_0
0x180069855  mov     rbx, [rsi+350h]
0x18006985c  cmp     rbx, [rsi+358h]
0x180069863  jnz     loc_180069AFA
0x180069869  mov     eax, [rsi+298h]
0x18006986f  sub     eax, edi
0x180069871  cmp     eax, edi
0x180069873  ja      short loc_1800698E2
0x180069875  mov     rax, [rsi]
0x180069878  or      edx, 0FFFFFFFFh
0x18006987b  mov     rcx, rsi
0x18006987e  mov     rax, [rax+180h]
0x180069885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006988a  test    rax, rax
0x18006988d  jz      short loc_1800698E2
0x18006988f  mov     rcx, rax; this
0x180069892  call    ?DeletePersistentState@CFile@@QEAAJXZ; CFile::DeletePersistentState(void)
0x180069897  test    eax, eax
0x180069899  jns     short loc_1800698E2
0x18006989b  xorps   xmm0, xmm0
0x18006989e  movups  [rsp+358h+var_210], xmm0
0x1800698a6  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800698ad  mov     [rsp+358h+var_218], rcx
0x1800698b5  mov     [rsp+358h+var_200], eax
0x1800698bc  mov     [rsp+358h+var_1FC], 4B1h
0x1800698c7  mov     [rsp+358h+var_1F8], edi
0x1800698ce  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800698d5  lea     rcx, [rsp+358h+var_218]; pExceptionObject
0x1800698dd  call    _CxxThrowException_0
0x1800698e2  xorps   xmm0, xmm0
0x1800698e5  xor     eax, eax
0x1800698e7  movups  xmmword ptr [rsp+358h+pvar], xmm0
0x1800698ec  mov     [rsp+358h+var_318], rax
0x1800698f1  mov     word ptr [rsp+358h+pvar], ax
0x1800698f6  lea     ecx, [rax+10h]; cb
0x1800698f9  call    cs:__imp_CoTaskMemAlloc
0x1800698ff  mov     [rsp+358h+pvar+8], rax
0x180069904  test    rax, rax
0x180069907  jz      loc_180069AAE
0x18006990d  mov     rcx, rax; void *
0x180069910  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x180069915  mov     r8, rax; Size
0x180069918  xor     edx, edx; Val
0x18006991a  mov     rcx, [rsp+358h+pvar+8]; void *
0x18006991f  call    memset_0
0x180069924  mov     eax, 48h ; 'H'
0x180069929  mov     word ptr [rsp+358h+pvar], ax
0x18006992e  movups  xmm0, xmmword ptr [rsi+2A4h]
0x180069935  mov     rax, [rsp+358h+pvar+8]
0x18006993a  movdqu  xmmword ptr [rax], xmm0
0x18006993e  mov     rax, cs:?g_Manager@@3PEAVCJobManager@@EA; CJobManager * g_Manager
0x180069945  mov     rcx, [rax+298h]
0x18006994c  mov     rax, [rcx]
0x18006994f  lea     r8, [rsp+358h+pvar]
0x180069954  xor     edx, edx
0x180069956  mov     rax, [rax+50h]
0x18006995a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006995f  test    eax, eax
0x180069961  jns     short loc_1800699AA
0x180069963  xorps   xmm0, xmm0
0x180069966  movups  [rsp+358h+var_1B0], xmm0
0x18006996e  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180069975  mov     [rsp+358h+var_1B8], rcx
0x18006997d  mov     [rsp+358h+var_1A0], eax
0x180069984  mov     [rsp+358h+var_19C], 4B9h
0x18006998f  mov     [rsp+358h+var_198], edi
0x180069996  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x18006999d  lea     rcx, [rsp+358h+var_1B8]; pExceptionObject
0x1800699a5  call    _CxxThrowException_0
0x1800699aa  mov     rax, [r13+0]
0x1800699ae  mov     rcx, r13
0x1800699b1  mov     rax, [rax+30h]
0x1800699b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800699ba  xor     r13d, r13d
0x1800699bd  test    eax, eax
0x1800699bf  jns     short loc_180069A08
0x1800699c1  xorps   xmm0, xmm0
0x1800699c4  movups  [rsp+358h+var_150], xmm0
0x1800699cc  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x1800699d3  mov     [rsp+358h+var_158], rcx
0x1800699db  mov     [rsp+358h+var_140], eax
0x1800699e2  mov     [rsp+358h+var_13C], 14h
0x1800699ed  mov     [rsp+358h+var_138], edi
0x1800699f4  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x1800699fb  lea     rcx, [rsp+358h+var_158]; pExceptionObject
0x180069a03  call    _CxxThrowException_0
0x180069a08  call    cs:__imp_GetTickCount64
0x180069a0e  mov     rbx, rax
0x180069a11  sub     rbx, [rsp+358h+arg_10]
0x180069a19  cmp     rbx, 3A98h
0x180069a20  jbe     short loc_180069A2A
0x180069a22  mov     rdx, rbx; unsigned __int64
0x180069a25  call    ?ReportSerialize@EVENT_LOG@@QEAAJ_K@Z; EVENT_LOG::ReportSerialize(unsigned __int64)
0x180069a2a  mov     [rsp+358h+arg_0], r13
0x180069a32  mov     rcx, r13
0x180069a35  mov     [rsi+3D0h], rcx
0x180069a3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180069a43  lea     rax, WPP_GLOBAL_Control
0x180069a4a  cmp     rcx, rax
0x180069a4d  jz      short loc_180069A6E
0x180069a4f  test    byte ptr [rcx+1Ch], 20h
0x180069a53  jz      short loc_180069A6E
0x180069a55  mov     edx, 3Ch ; '<'
0x180069a5a  mov     r9, rbx
0x180069a5d  lea     r8, WPP_fc1a8969500934a5540c0841eee52ba4_Traceguids
0x180069a64  mov     rcx, [rcx+10h]
0x180069a68  call    WPP_SF_q
0x180069a6d  nop
0x180069a6e  lea     rcx, [rsp+358h+pvar]; pvar
0x180069a73  call    cs:__imp_PropVariantClear
0x180069a79  nop
0x180069a7a  cmp     byte ptr [rsp+358h+arg_8], r13b
0x180069a82  jz      short loc_180069A95
0x180069a84  mov     rax, [r12]
0x180069a88  mov     rcx, r12
0x180069a8b  mov     rax, [rax+20h]
0x180069a8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069a94  nop
0x180069a95  test    r14d, r14d
0x180069a98  jz      short loc_180069AA7
0x180069a9a  mov     rcx, r15; this
0x180069a9d  call    ?UnlockWriter@TaskScheduler@@QEAAXXZ; TaskScheduler::UnlockWriter(void)
0x180069aa2  sub     r14d, edi
0x180069aa5  jnz     short loc_180069A9A
0x180069aa7  xor     eax, eax
0x180069aa9  jmp     loc_180069B76
0x180069aae  xorps   xmm0, xmm0
0x180069ab1  movups  [rsp+358h+var_F0], xmm0
0x180069ab9  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180069ac0  mov     [rsp+358h+var_F8], rcx
0x180069ac8  mov     [rsp+358h+var_E0], 8007000Eh
0x180069ad3  mov     [rsp+358h+var_DC], 4B6h
0x180069ade  mov     [rsp+358h+var_D8], edi
0x180069ae5  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180069aec  lea     rcx, [rsp+358h+var_F8]; pExceptionObject
0x180069af4  call    _CxxThrowException_0
0x180069afa  mov     rcx, [rbx]; this
0x180069afd  call    ?DeletePersistentState@CFile@@QEAAJXZ; CFile::DeletePersistentState(void)
0x180069b02  test    eax, eax
0x180069b04  jns     short loc_180069B4D
0x180069b06  xorps   xmm0, xmm0
0x180069b09  movups  [rsp+358h+var_90], xmm0
0x180069b11  lea     rcx, ??_7ComError@@6B@; const ComError::`vftable'
0x180069b18  mov     [rsp+358h+var_98], rcx
0x180069b20  mov     [rsp+358h+var_80], eax
0x180069b27  mov     [rsp+358h+var_7C], 4A9h
0x180069b32  mov     [rsp+358h+var_78], edi
0x180069b39  lea     rdx, _TI2?AVComError@@; pThrowInfo
0x180069b40  lea     rcx, [rsp+358h+var_98]; pExceptionObject
0x180069b48  call    _CxxThrowException_0
0x180069b4d  add     rbx, 8
0x180069b51  jmp     loc_18006985C
0x180069b56  mov     ebx, edx
0x180069b58  mov     ecx, eax
0x180069b5a  test    ecx, ecx
0x180069b5c  jz      short loc_180069B6B
0x180069b5e  mov     rcx, r15; this
0x180069b61  call    ?UnlockWriter@TaskScheduler@@QEAAXXZ; TaskScheduler::UnlockWriter(void)
0x180069b66  sub     ebx, 1
0x180069b69  jnz     short loc_180069B5E
0x180069b6b  xor     eax, eax
0x180069b6d  jmp     short loc_180069B76
0x180069b6f  mov     eax, dword ptr [rsp+358h+arg_0]
0x180069b76  add     rsp, 320h
0x180069b7d  pop     r15
0x180069b7f  pop     r14
0x180069b81  pop     r13
0x180069b83  pop     r12
0x180069b85  pop     rdi
0x180069b86  pop     rsi
0x180069b87  pop     rbx
0x180069b88  retn
```
