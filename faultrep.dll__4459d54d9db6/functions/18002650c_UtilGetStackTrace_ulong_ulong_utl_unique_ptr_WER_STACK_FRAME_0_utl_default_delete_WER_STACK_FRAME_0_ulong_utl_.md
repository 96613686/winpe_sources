# UtilGetStackTrace(ulong,ulong,utl::unique_ptr<_WER_STACK_FRAME [0],utl::default_delete<_WER_STACK_FRAME [0]>> *,ulong *,utl::unique_ptr<wchar_t [0],utl::default_delete<wchar_t [0]>> *,void * *,void * *)

- ea: `0x18002650c`
- end: `0x180026b2f`
- name: `?UtilGetStackTrace@@YAJKKPEAV?$unique_ptr@$$BY0A@U_WER_STACK_FRAME@@U?$default_delete@$$BY0A@U_WER_STACK_FRAME@@@utl@@@utl@@PEAKPEAV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@2@PEAPEAX3@Z`
- size: `1571`
- prototype: `__int64 __fastcall(DWORD dwProcessId, DWORD dwThreadId, void **, unsigned int *, void **, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x180026210`

## callees

- `0x180002890`
- `0x1800028b4`
- `0x180003474`
- `0x1800047cc`
- `0x180024bc4`
- `0x180025f80`
- `0x18002650c`
- `0x180049304`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1800265c9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1800265c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026699`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026ae9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026699`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026ae9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800266b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800266cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800266b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800266cb`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x18002668c`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x18002668c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800267a6`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800267a6`
- `dbghelp!StackWalk64` at `0x18002685d`
- `dbghelp!StackWalk64` at `0x18002685d`
- `dbghelp!SymGetModuleBase64` at `0x180026815`
- `dbghelp!SymCleanup` at `0x180026ac0`
- `dbghelp!SymCleanup` at `0x180026ac0`
- `dbghelp!SymSetExtendedOption` at `0x1800267c4`
- `dbghelp!SymSetExtendedOption` at `0x1800267c4`
- `dbghelp!SymInitialize` at `0x1800267da`
- `dbghelp!SymInitialize` at `0x1800267da`
- `dbghelp!SymFunctionTableAccess64` at `0x180026837`

## pseudocode

```c
__int64 __fastcall UtilGetStackTrace(
        DWORD dwProcessId,
        DWORD dwThreadId,
        void **a3,
        unsigned int *a4,
        void **a5,
        _QWORD *a6,
        _QWORD *a7)
{
  void **v7; // r13
  void **v8; // r15
  const struct std::nothrow_t *v12; // rdx
  unsigned int v13; // r12d
  void *v14; // rcx
  char *v15; // r14
  __int64 v16; // rdx
  CONTEXT *p_Context; // rax
  _OWORD *v18; // rcx
  __int128 v19; // xmm1
  __int128 v20; // xmm0
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  __int128 v25; // xmm1
  __int128 v26; // xmm1
  __int128 v27; // xmm0
  __int128 v28; // xmm1
  __int128 v29; // xmm0
  char *v30; // rbx
  signed int LastError; // eax
  unsigned int v32; // r15d
  _tagSTACKFRAME64 *p_StackFrame; // rcx
  __int64 v34; // rdx
  ADDRESS64 *v35; // rax
  ADDRESS64 v36; // xmm1
  ADDRESS64 v37; // xmm0
  ADDRESS64 v38; // xmm1
  ADDRESS64 v39; // xmm0
  ADDRESS64 v40; // xmm1
  ADDRESS64 v41; // xmm0
  ADDRESS64 v42; // xmm1
  _QWORD *v43; // rax
  _QWORD *v44; // rdi
  ADDRESS64 *v45; // rcx
  __int64 v46; // rdx
  _tagSTACKFRAME64 *v47; // rax
  ADDRESS64 AddrReturn; // xmm1
  ADDRESS64 AddrFrame; // xmm0
  ADDRESS64 AddrStack; // xmm1
  ADDRESS64 AddrBStore; // xmm0
  ADDRESS64 v52; // xmm1
  ADDRESS64 v53; // xmm0
  ADDRESS64 v54; // xmm1
  __int64 v55; // rcx
  _OWORD *v56; // rax
  _OWORD *v57; // r8
  __int128 v58; // xmm1
  __int128 v59; // xmm0
  __int128 v60; // xmm1
  __int128 v61; // xmm0
  __int128 v62; // xmm1
  __int128 v63; // xmm0
  __int128 v64; // xmm1
  unsigned __int64 v65; // rax
  const struct std::nothrow_t *v66; // rdx
  char *v67; // rsi
  struct _WER_STACK_FRAME *v68; // r9
  __int64 v69; // r13
  unsigned int i; // r14d
  __int64 v71; // r15
  const struct std::nothrow_t **unique_for; // rax
  void *v73; // rcx
  size_t v74; // r15
  void *v75; // rcx
  const struct std::nothrow_t *v76; // rdx
  signed int v77; // eax
  char *Src; // [rsp+50h] [rbp-B0h]
  void *v80; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD *v81; // [rsp+68h] [rbp-98h]
  char *v82; // [rsp+70h] [rbp-90h]
  void **v83; // [rsp+78h] [rbp-88h]
  _QWORD *v84; // [rsp+80h] [rbp-80h]
  unsigned int *v85; // [rsp+88h] [rbp-78h]
  _BYTE v86[1232]; // [rsp+90h] [rbp-70h] BYREF
  _tagSTACKFRAME64 StackFrame; // [rsp+560h] [rbp+460h] BYREF
  CONTEXT Context; // [rsp+670h] [rbp+570h] BYREF

  v7 = a3;
  v8 = a5;
  v81 = a6;
  v83 = a3;
  v84 = a7;
  v85 = a4;
  memset_0(&StackFrame, 0, sizeof(StackFrame));
  memset_0(&Context, 0, sizeof(Context));
  v13 = 0;
  if ( a5 )
  {
    v14 = *a5;
    *a5 = 0;
    if ( v14 )
      operator delete(v14, v12);
  }
  if ( !v7 || !a4 )
    return (unsigned int)-2147024809;
  v15 = (char *)OpenThread(0x48u, 0, dwThreadId);
  v82 = v15;
  if ( v15 != (char *)-1LL && v15 + 1 != (char *)1 )
  {
    memset_0(v86, 0, sizeof(v86));
    v16 = 9;
    p_Context = &Context;
    v18 = v86;
    do
    {
      v19 = v18[1];
      *(_OWORD *)&p_Context->P1Home = *v18;
      v20 = v18[2];
      *(_OWORD *)&p_Context->P3Home = v19;
      v21 = v18[3];
      *(_OWORD *)&p_Context->P5Home = v20;
      v22 = v18[4];
      *(_OWORD *)&p_Context->ContextFlags = v21;
      v23 = v18[5];
      *(_OWORD *)&p_Context->SegGs = v22;
      v24 = v18[6];
      *(_OWORD *)&p_Context->Dr1 = v23;
      v25 = v18[7];
      v18 += 8;
      *(_OWORD *)&p_Context->Dr3 = v24;
      *(_OWORD *)&p_Context->Dr7 = v25;
      p_Context = (CONTEXT *)((char *)p_Context + 128);
      --v16;
    }
    while ( v16 );
    v26 = v18[1];
    *(_OWORD *)&p_Context->P1Home = *v18;
    v27 = v18[2];
    *(_OWORD *)&p_Context->P3Home = v26;
    v28 = v18[3];
    *(_OWORD *)&p_Context->P5Home = v27;
    v29 = v18[4];
    *(_OWORD *)&p_Context->ContextFlags = v28;
    *(_OWORD *)&p_Context->SegGs = v29;
    Context.ContextFlags = 1048607;
    if ( !GetThreadContext(v15, &Context) )
    {
      v30 = 0;
      goto LABEL_11;
    }
    memset_0(v86, 0, 0x108u);
    p_StackFrame = &StackFrame;
    v34 = 2;
    v35 = (ADDRESS64 *)v86;
    do
    {
      v36 = v35[1];
      p_StackFrame->AddrPC = *v35;
      v37 = v35[2];
      p_StackFrame->AddrReturn = v36;
      v38 = v35[3];
      p_StackFrame->AddrFrame = v37;
      v39 = v35[4];
      p_StackFrame->AddrStack = v38;
      v40 = v35[5];
      p_StackFrame->AddrBStore = v39;
      v41 = v35[6];
      *(ADDRESS64 *)&p_StackFrame->FuncTableEntry = v40;
      v42 = v35[7];
      v35 += 8;
      *(ADDRESS64 *)&p_StackFrame->Params[1] = v41;
      *(ADDRESS64 *)&p_StackFrame->Params[3] = v42;
      p_StackFrame = (_tagSTACKFRAME64 *)((char *)p_StackFrame + 128);
      --v34;
    }
    while ( v34 );
    p_StackFrame->AddrPC.Offset = v35->Offset;
    StackFrame.AddrPC.Mode = AddrModeFlat;
    StackFrame.AddrStack.Mode = AddrModeFlat;
    StackFrame.AddrFrame.Mode = AddrModeFlat;
    StackFrame.AddrPC.Offset = Context.Rip;
    StackFrame.AddrStack.Offset = Context.Rsp;
    StackFrame.AddrFrame.Offset = Context.Rbp;
    StackFrame.AddrPC.Segment = 0;
    StackFrame.AddrStack.Segment = 0;
    StackFrame.AddrFrame.Segment = 0;
    v30 = (char *)OpenProcess(0x410u, 0, dwProcessId);
    if ( v30 == (char *)-1LL
      || v30 + 1 == (char *)1
      || (SymSetExtendedOption((IMAGEHLP_EXTENDED_OPTIONS)3, 1), !SymInitialize(v30, UserSearchPath, 1)) )
    {
LABEL_11:
      LastError = GetLastError();
      v32 = LastError;
      if ( LastError > 0 )
        v32 = (unsigned __int16)LastError | 0x80070000;
LABEL_13:
      CloseHandle(v15);
      if ( (unsigned __int64)(v30 + 1) > 1 )
        CloseHandle(v30);
      return v32;
    }
    v43 = operator new[](0x8400u, (const struct std::nothrow_t *)&std::nothrow);
    v44 = v43;
    if ( v43 )
    {
      memset_0(v43, 0, 0x8400u);
      do
      {
        if ( !StackWalk64(0x8664u, v30, v15, &StackFrame, &Context, 0, SymFunctionTableAccess64, SymGetModuleBase64, 0) )
          break;
        v45 = (ADDRESS64 *)v86;
        v46 = 2;
        v47 = &StackFrame;
        do
        {
          AddrReturn = v47->AddrReturn;
          *v45 = v47->AddrPC;
          AddrFrame = v47->AddrFrame;
          v45[1] = AddrReturn;
          AddrStack = v47->AddrStack;
          v45[2] = AddrFrame;
          AddrBStore = v47->AddrBStore;
          v45[3] = AddrStack;
          v52 = *(ADDRESS64 *)&v47->FuncTableEntry;
          v45[4] = AddrBStore;
          v53 = *(ADDRESS64 *)&v47->Params[1];
          v45[5] = v52;
          v54 = *(ADDRESS64 *)&v47->Params[3];
          v47 = (_tagSTACKFRAME64 *)((char *)v47 + 128);
          v45[6] = v53;
          v45[7] = v54;
          v45 += 8;
          --v46;
        }
        while ( v46 );
        v45->Offset = v47->AddrPC.Offset;
        v55 = 2;
        v56 = v86;
        v57 = &v44[33 * v13];
        do
        {
          v58 = v56[1];
          *v57 = *v56;
          v59 = v56[2];
          v57[1] = v58;
          v60 = v56[3];
          v57[2] = v59;
          v61 = v56[4];
          v57[3] = v60;
          v62 = v56[5];
          v57[4] = v61;
          v63 = v56[6];
          v57[5] = v62;
          v64 = v56[7];
          v56 += 8;
          v57[6] = v63;
          v57[7] = v64;
          v57 += 8;
          --v55;
        }
        while ( v55 );
        ++v13;
        *(_QWORD *)v57 = *(_QWORD *)v56;
      }
      while ( v13 < 0x80 );
      v65 = 1048LL * v13;
      if ( !is_mul_ok(v13, 0x418u) )
        v65 = -1;
      v67 = (char *)operator new[](v65, (const struct std::nothrow_t *)&std::nothrow);
      if ( v67 )
      {
        if ( v13 )
        {
          v69 = 0;
          for ( i = 0; i < v13; ++i )
          {
            Src = &v67[1048 * v69];
            _werDetail::UtilConvertDbgFrameToWerFrame((_werDetail *)v30, &v44[33 * v69], Src, v68);
            if ( v8 && !*v8 )
            {
              v71 = -1;
              do
                ++v71;
              while ( *(_WORD *)&Src[2 * v71] );
              unique_for = (const struct std::nothrow_t **)utl::make_unique_for_overwrite<wchar_t [0],0>(&v80, v71 + 1);
              v66 = *unique_for;
              *unique_for = 0;
              v73 = *a5;
              *a5 = v66;
              if ( v73 )
                operator delete(v73, v66);
              if ( v80 )
                operator delete(v80, v66);
              if ( *a5 )
              {
                v74 = 2 * v71;
                memcpy_0(*a5, Src, v74);
                *(_WORD *)((char *)*a5 + v74) = 0;
              }
              v8 = a5;
              if ( v81 )
                *v81 = *((_QWORD *)Src + 130);
            }
            ++v69;
          }
          v15 = v82;
          v7 = v83;
        }
        if ( v84 )
          *v84 = *v44;
        v75 = *v7;
        *v7 = v67;
        if ( v75 )
          operator delete(v75, v66);
        *v85 = v13;
        v32 = 0;
        goto LABEL_53;
      }
    }
    else
    {
      v44 = 0;
    }
    v32 = -2147024882;
LABEL_53:
    SymCleanup(v30);
    if ( v44 )
      operator delete(v44, v76);
    goto LABEL_13;
  }
  v77 = GetLastError();
  v32 = v77;
  if ( v77 > 0 )
    return (unsigned __int16)v77 | 0x80070000;
  return v32;
}

```

## disassembly

```asm
0x18002650c  push    rbp
0x18002650e  push    rbx
0x18002650f  push    rsi
0x180026510  push    rdi
0x180026511  push    r12
0x180026513  push    r13
0x180026515  push    r14
0x180026517  push    r15
0x180026519  lea     rbp, [rsp-0A58h]
0x180026521  sub     rsp, 0B58h
0x180026528  mov     rax, cs:__security_cookie
0x18002652f  xor     rax, rsp
0x180026532  mov     [rbp+0A90h+var_50], rax
0x180026539  mov     rax, [rbp+0A90h+arg_28]
0x180026540  mov     r13, r8
0x180026543  mov     r15, [rbp+0A90h+arg_20]
0x18002654a  mov     ebx, edx
0x18002654c  mov     [rsp+0B90h+var_B28], rax
0x180026551  mov     edi, ecx
0x180026553  mov     rax, [rbp+0A90h+arg_30]
0x18002655a  lea     rcx, [rbp+0A90h+StackFrame]; void *
0x180026561  mov     [rsp+0B90h+var_B18], r8
0x180026566  xor     edx, edx; Val
0x180026568  mov     r8d, 108h; Size
0x18002656e  mov     [rbp+0A90h+var_B10], rax
0x180026572  mov     rsi, r9
0x180026575  mov     [rbp+0A90h+var_B08], r9
0x180026579  mov     [rsp+0B90h+var_B38], r15
0x18002657e  call    memset_0
0x180026583  xor     edx, edx; Val
0x180026585  lea     rcx, [rbp+0A90h+Context]; void *
0x18002658c  mov     r8d, 4D0h; Size
0x180026592  call    memset_0
0x180026597  xor     r12d, r12d
0x18002659a  test    r15, r15
0x18002659d  jz      short loc_1800265AF
0x18002659f  mov     rcx, [r15]; void *
0x1800265a2  mov     [r15], r12
0x1800265a5  test    rcx, rcx
0x1800265a8  jz      short loc_1800265AF
0x1800265aa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800265af  test    r13, r13
0x1800265b2  jz      loc_180026B03
0x1800265b8  test    rsi, rsi
0x1800265bb  jz      loc_180026B03
0x1800265c1  xor     edx, edx; bInheritHandle
0x1800265c3  mov     r8d, ebx; dwThreadId
0x1800265c6  lea     ecx, [rdx+48h]; dwDesiredAccess
0x1800265c9  call    cs:__imp_OpenThread
0x1800265cf  mov     r14, rax
0x1800265d2  mov     [rsp+0B90h+var_B20], rax
0x1800265d7  inc     rax
0x1800265da  cmp     rax, 1
0x1800265de  jbe     loc_180026AE9
0x1800265e4  xor     edx, edx; Val
0x1800265e6  lea     rcx, [rbp+0A90h+var_B00]; void *
0x1800265ea  mov     r8d, 4D0h; Size
0x1800265f0  call    memset_0
0x1800265f5  mov     edx, 9
0x1800265fa  lea     rax, [rbp+0A90h+Context]
0x180026601  lea     rcx, [rbp+0A90h+var_B00]
0x180026605  lea     esi, [rdx+77h]
0x180026608  movups  xmm0, xmmword ptr [rcx]
0x18002660b  movups  xmm1, xmmword ptr [rcx+10h]
0x18002660f  movups  xmmword ptr [rax], xmm0
0x180026612  movups  xmm0, xmmword ptr [rcx+20h]
0x180026616  movups  xmmword ptr [rax+10h], xmm1
0x18002661a  movups  xmm1, xmmword ptr [rcx+30h]
0x18002661e  movups  xmmword ptr [rax+20h], xmm0
0x180026622  movups  xmm0, xmmword ptr [rcx+40h]
0x180026626  movups  xmmword ptr [rax+30h], xmm1
0x18002662a  movups  xmm1, xmmword ptr [rcx+50h]
0x18002662e  movups  xmmword ptr [rax+40h], xmm0
0x180026632  movups  xmm0, xmmword ptr [rcx+60h]
0x180026636  movups  xmmword ptr [rax+50h], xmm1
0x18002663a  movups  xmm1, xmmword ptr [rcx+70h]
0x18002663e  add     rcx, rsi
0x180026641  movups  xmmword ptr [rax+60h], xmm0
0x180026645  movups  xmmword ptr [rax+70h], xmm1
0x180026649  add     rax, rsi
0x18002664c  sub     rdx, 1
0x180026650  jnz     short loc_180026608
0x180026652  movups  xmm0, xmmword ptr [rcx]
0x180026655  lea     rdx, [rbp+0A90h+Context]; lpContext
0x18002665c  movups  xmm1, xmmword ptr [rcx+10h]
0x180026660  movups  xmmword ptr [rax], xmm0
0x180026663  movups  xmm0, xmmword ptr [rcx+20h]
0x180026667  movups  xmmword ptr [rax+10h], xmm1
0x18002666b  movups  xmm1, xmmword ptr [rcx+30h]
0x18002666f  movups  xmmword ptr [rax+20h], xmm0
0x180026673  movups  xmm0, xmmword ptr [rcx+40h]
0x180026677  mov     rcx, r14; hThread
0x18002667a  movups  xmmword ptr [rax+30h], xmm1
0x18002667e  movups  xmmword ptr [rax+40h], xmm0
0x180026682  mov     [rbp+0A90h+Context.ContextFlags], 10001Fh
0x18002668c  call    cs:__imp_GetThreadContext
0x180026692  test    eax, eax
0x180026694  jnz     short loc_1800266D6
0x180026696  mov     rbx, r12
0x180026699  call    cs:__imp_GetLastError
0x18002669f  mov     r15d, eax
0x1800266a2  test    eax, eax
0x1800266a4  jle     short loc_1800266B1
0x1800266a6  movzx   r15d, ax
0x1800266aa  or      r15d, 80070000h
0x1800266b1  mov     rcx, r14; hObject
0x1800266b4  call    cs:__imp_CloseHandle
0x1800266ba  lea     rax, [rbx+1]
0x1800266be  cmp     rax, 1
0x1800266c2  jbe     loc_180026B09
0x1800266c8  mov     rcx, rbx; hObject
0x1800266cb  call    cs:__imp_CloseHandle
0x1800266d1  jmp     loc_180026B09
0x1800266d6  xor     edx, edx; Val
0x1800266d8  lea     rcx, [rbp+0A90h+var_B00]; void *
0x1800266dc  mov     r8d, 108h; Size
0x1800266e2  call    memset_0
0x1800266e7  lea     rcx, [rbp+0A90h+StackFrame]
0x1800266ee  mov     edx, 2
0x1800266f3  lea     rax, [rbp+0A90h+var_B00]
0x1800266f7  movups  xmm0, xmmword ptr [rax]
0x1800266fa  movups  xmm1, xmmword ptr [rax+10h]
0x1800266fe  movups  xmmword ptr [rcx], xmm0
0x180026701  movups  xmm0, xmmword ptr [rax+20h]
0x180026705  movups  xmmword ptr [rcx+10h], xmm1
0x180026709  movups  xmm1, xmmword ptr [rax+30h]
0x18002670d  movups  xmmword ptr [rcx+20h], xmm0
0x180026711  movups  xmm0, xmmword ptr [rax+40h]
0x180026715  movups  xmmword ptr [rcx+30h], xmm1
0x180026719  movups  xmm1, xmmword ptr [rax+50h]
0x18002671d  movups  xmmword ptr [rcx+40h], xmm0
0x180026721  movups  xmm0, xmmword ptr [rax+60h]
0x180026725  movups  xmmword ptr [rcx+50h], xmm1
0x180026729  movups  xmm1, xmmword ptr [rax+70h]
0x18002672d  add     rax, rsi
0x180026730  movups  xmmword ptr [rcx+60h], xmm0
0x180026734  movups  xmmword ptr [rcx+70h], xmm1
0x180026738  add     rcx, rsi
0x18002673b  sub     rdx, 1; bInheritHandle
0x18002673f  jnz     short loc_1800266F7
0x180026741  mov     rax, [rax]
0x180026744  mov     r8d, edi; dwProcessId
0x180026747  mov     [rcx], rax
0x18002674a  lea     eax, [rdx+3]
0x18002674d  mov     [rbp+0A90h+StackFrame.AddrPC.Mode], eax
0x180026753  mov     ecx, 410h; dwDesiredAccess
0x180026758  mov     [rbp+0A90h+StackFrame.AddrStack.Mode], eax
0x18002675e  mov     [rbp+0A90h+StackFrame.AddrFrame.Mode], eax
0x180026764  mov     rax, [rbp+0A90h+Context.Rip]
0x18002676b  mov     [rbp+0A90h+StackFrame.AddrPC.Offset], rax
0x180026772  mov     rax, [rbp+0A90h+Context.Rsp]
0x180026779  mov     [rbp+0A90h+StackFrame.AddrStack.Offset], rax
0x180026780  mov     rax, [rbp+0A90h+Context.Rbp]
0x180026787  mov     [rbp+0A90h+StackFrame.AddrFrame.Offset], rax
0x18002678e  mov     [rbp+0A90h+StackFrame.AddrPC.Segment], r12w
0x180026796  mov     [rbp+0A90h+StackFrame.AddrStack.Segment], r12w
0x18002679e  mov     [rbp+0A90h+StackFrame.AddrFrame.Segment], r12w
0x1800267a6  call    cs:__imp_OpenProcess
0x1800267ac  mov     rbx, rax
0x1800267af  inc     rax
0x1800267b2  cmp     rax, 1
0x1800267b6  jbe     loc_180026699
0x1800267bc  mov     edx, 1; value
0x1800267c1  lea     ecx, [rdx+2]; option
0x1800267c4  call    cs:__imp_SymSetExtendedOption
0x1800267ca  mov     r8d, 1; fInvadeProcess
0x1800267d0  lea     rdx, UserSearchPath; UserSearchPath
0x1800267d7  mov     rcx, rbx; hProcess
0x1800267da  call    cs:__imp_SymInitialize
0x1800267e0  test    eax, eax
0x1800267e2  jz      loc_180026699
0x1800267e8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800267ef  mov     ecx, 8400h; unsigned __int64
0x1800267f4  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800267f9  mov     rdi, rax
0x1800267fc  test    rax, rax
0x1800267ff  jz      loc_180026AB1
0x180026805  xor     edx, edx; Val
0x180026807  mov     r8d, 8400h; Size
0x18002680d  mov     rcx, rax; void *
0x180026810  call    memset_0
0x180026815  mov     rax, cs:__imp_SymGetModuleBase64
0x18002681c  lea     r9, [rbp+0A90h+StackFrame]; StackFrame
0x180026823  mov     [rsp+0B90h+TranslateAddress], 0; TranslateAddress
0x18002682c  mov     r8, r14; hThread
0x18002682f  mov     [rsp+0B90h+GetModuleBaseRoutine], rax; GetModuleBaseRoutine
0x180026834  mov     rdx, rbx; hProcess
0x180026837  mov     rax, cs:__imp_SymFunctionTableAccess64
0x18002683e  mov     ecx, 8664h; MachineType
0x180026843  mov     [rsp+0B90h+FunctionTableAccessRoutine], rax; FunctionTableAccessRoutine
0x180026848  lea     rax, [rbp+0A90h+Context]
0x18002684f  mov     [rsp+0B90h+ReadMemoryRoutine], 0; ReadMemoryRoutine
0x180026858  mov     [rsp+0B90h+ContextRecord], rax; ContextRecord
0x18002685d  call    cs:__imp_StackWalk64
0x180026863  test    eax, eax
0x180026865  jz      loc_180026947
0x18002686b  mov     r9d, 2
0x180026871  lea     rcx, [rbp+0A90h+var_B00]
0x180026875  mov     edx, r9d
0x180026878  lea     rax, [rbp+0A90h+StackFrame]
0x18002687f  movups  xmm0, xmmword ptr [rax]
0x180026882  movups  xmm1, xmmword ptr [rax+10h]
0x180026886  movups  xmmword ptr [rcx], xmm0
0x180026889  movups  xmm0, xmmword ptr [rax+20h]
0x18002688d  movups  xmmword ptr [rcx+10h], xmm1
0x180026891  movups  xmm1, xmmword ptr [rax+30h]
0x180026895  movups  xmmword ptr [rcx+20h], xmm0
0x180026899  movups  xmm0, xmmword ptr [rax+40h]
0x18002689d  movups  xmmword ptr [rcx+30h], xmm1
0x1800268a1  movups  xmm1, xmmword ptr [rax+50h]
0x1800268a5  movups  xmmword ptr [rcx+40h], xmm0
0x1800268a9  movups  xmm0, xmmword ptr [rax+60h]
0x1800268ad  movups  xmmword ptr [rcx+50h], xmm1
0x1800268b1  movups  xmm1, xmmword ptr [rax+70h]
0x1800268b5  add     rax, rsi
0x1800268b8  movups  xmmword ptr [rcx+60h], xmm0
0x1800268bc  movups  xmmword ptr [rcx+70h], xmm1
0x1800268c0  add     rcx, rsi
0x1800268c3  sub     rdx, 1
0x1800268c7  jnz     short loc_18002687F
0x1800268c9  mov     rax, [rax]
0x1800268cc  mov     [rcx], rax
0x1800268cf  mov     rcx, r9
0x1800268d2  mov     eax, r12d
0x1800268d5  imul    r8, rax, 108h
0x1800268dc  lea     rax, [rbp+0A90h+var_B00]
0x1800268e0  add     r8, rdi
0x1800268e3  movups  xmm0, xmmword ptr [rax]
0x1800268e6  movups  xmm1, xmmword ptr [rax+10h]
0x1800268ea  movups  xmmword ptr [r8], xmm0
0x1800268ee  movups  xmm0, xmmword ptr [rax+20h]
0x1800268f2  movups  xmmword ptr [r8+10h], xmm1
0x1800268f7  movups  xmm1, xmmword ptr [rax+30h]
0x1800268fb  movups  xmmword ptr [r8+20h], xmm0
0x180026900  movups  xmm0, xmmword ptr [rax+40h]
0x180026904  movups  xmmword ptr [r8+30h], xmm1
0x180026909  movups  xmm1, xmmword ptr [rax+50h]
0x18002690d  movups  xmmword ptr [r8+40h], xmm0
0x180026912  movups  xmm0, xmmword ptr [rax+60h]
0x180026916  movups  xmmword ptr [r8+50h], xmm1
0x18002691b  movups  xmm1, xmmword ptr [rax+70h]
0x18002691f  add     rax, rsi
0x180026922  movups  xmmword ptr [r8+60h], xmm0
0x180026927  movups  xmmword ptr [r8+70h], xmm1
0x18002692c  add     r8, rsi
0x18002692f  sub     rcx, 1
0x180026933  jnz     short loc_1800268E3
0x180026935  mov     rax, [rax]
0x180026938  inc     r12d
0x18002693b  mov     [r8], rax
0x18002693e  cmp     r12d, esi
0x180026941  jb      loc_180026815
0x180026947  mov     ecx, r12d
0x18002694a  mov     eax, 418h
0x18002694f  mul     rcx
0x180026952  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180026959  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180026960  cmovb   rax, rcx
0x180026964  mov     rcx, rax; unsigned __int64
0x180026967  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18002696c  xor     r8d, r8d
0x18002696f  mov     rsi, rax
0x180026972  test    rax, rax
0x180026975  jz      loc_180026AB7
0x18002697b  test    r12d, r12d
0x18002697e  jz      loc_180026A7B
0x180026984  mov     r13d, r8d
0x180026987  mov     r14d, r8d
0x18002698a  imul    rax, r13, 418h
0x180026991  imul    rdx, r13, 108h
0x180026998  add     rax, rsi
0x18002699b  mov     rcx, rbx; this
0x18002699e  mov     r8, rax; void *
0x1800269a1  mov     [rsp+0B90h+Src], rax
0x1800269a6  add     rdx, rdi; void *
0x1800269a9  call    ?UtilConvertDbgFrameToWerFrame@_werDetail@@YAJPEAX0PEAU_WER_STACK_FRAME@@@Z; _werDetail::UtilConvertDbgFrameToWerFrame(void *,void *,_WER_STACK_FRAME *)
0x1800269ae  xor     r8d, r8d
0x1800269b1  test    r15, r15
0x1800269b4  jz      loc_180026A62
0x1800269ba  cmp     [r15], r8
0x1800269bd  jnz     loc_180026A62
0x1800269c3  mov     rax, [rsp+0B90h+Src]
0x1800269c8  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800269cc  inc     r15
0x1800269cf  cmp     [rax+r15*2], r8w
0x1800269d4  jnz     short loc_1800269CC
0x1800269d6  lea     rdx, [r15+1]
0x1800269da  lea     rcx, [rsp+0B90h+var_B30]
0x1800269df  call    ??$make_unique_for_overwrite@$$BY0A@_W$0A@@utl@@YA?AV?$unique_ptr@$$BY0A@_WU?$default_delete@$$BY0A@_W@utl@@@0@_K@Z; utl::make_unique_for_overwrite<wchar_t [0],0>(unsigned __int64)
0x1800269e4  xor     r8d, r8d
0x1800269e7  mov     rdx, [rax]; struct std::nothrow_t *
0x1800269ea  mov     [rax], r8
0x1800269ed  mov     rax, [rsp+0B90h+var_B38]
0x1800269f2  mov     rcx, [rax]; void *
0x1800269f5  mov     [rax], rdx
0x1800269f8  test    rcx, rcx
0x1800269fb  jz      short loc_180026A05
0x1800269fd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180026a02  xor     r8d, r8d
0x180026a05  mov     rcx, [rsp+0B90h+var_B30]; void *
  ... truncated ...
```
