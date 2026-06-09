# PlaiExecuteTask(IDataCollectorSet *,int)

- ea: `0x18009be9c`
- end: `0x18009c8c8`
- name: `?PlaiExecuteTask@@YAJPEAUIDataCollectorSet@@H@Z`
- size: `2604`
- prototype: `__int64 __fastcall(struct IDataCollectorSet *, int)`
- caller_count: `3`
- callee_count: `12`
- tags: `service_task`

## callers

- `0x180075de0`
- `0x180106310`
- `0x180134620`

## callees

- `0x180002bd0`
- `0x180004e98`
- `0x180018420`
- `0x1800198b0`
- `0x18003c808`
- `0x18003ca10`
- `0x180094800`
- `0x180097594`
- `0x18009be9c`
- `0x1800e2ed0`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18009c848`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x18009c848`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18009c19b`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18009c19b`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18009c836`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18009c836`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18009c10c`
- `OLEAUT32!__imp_SafeArrayCreateVector` at `0x18009c10c`

## string_xrefs

- `0x18009bfae`: `PlaiExecuteTask`
- `0x18009c6da`: `PlaiExecuteTask`

## pseudocode

```c
__int64 __fastcall PlaiExecuteTask(struct IDataCollectorSet *a1, int a2)
{
  struct IDataCollectorSetVtbl *lpVtbl; // rax
  SAFEARRAY *v5; // r15
  HRESULT (__stdcall *get_Task)(IDataCollectorSet *, BSTR *); // rax
  int v7; // eax
  __int64 v8; // rdi
  int v9; // ebx
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // rax
  SAFEARRAY *Vector; // rax
  __int64 v16; // rax
  HRESULT v17; // eax
  __int64 v18; // rax
  int v19; // eax
  __int64 v20; // rax
  int v21; // eax
  const char *v22; // rdx
  int v23; // r8d
  __int64 v24; // rax
  unsigned __int16 *v25; // rax
  __int64 v26; // rax
  int RegisteredTask; // eax
  __int64 v28; // rax
  int v29; // eax
  __int64 v30; // rax
  struct IRegisteredTaskVtbl *v31; // rax
  int v32; // eax
  __int64 v33; // rax
  int v34; // eax
  __int64 v35; // rax
  int v36; // eax
  __int64 v37; // rax
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v41; // [rsp+38h] [rbp-C8h]
  __int64 v42; // [rsp+40h] [rbp-C0h]
  __int64 v43; // [rsp+48h] [rbp-B8h]
  __int64 v44; // [rsp+50h] [rbp-B0h]
  int v45; // [rsp+70h] [rbp-90h] BYREF
  __int64 v46; // [rsp+78h] [rbp-88h] BYREF
  __int16 v47; // [rsp+80h] [rbp-80h] BYREF
  void *ppvData; // [rsp+88h] [rbp-78h] BYREF
  struct IRegisteredTask *v49; // [rsp+90h] [rbp-70h] BYREF
  BSTR v50; // [rsp+98h] [rbp-68h] BYREF
  BSTR bstrString; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v52; // [rsp+A8h] [rbp-58h] BYREF
  double v53[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v54; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v55; // [rsp+D0h] [rbp-30h]
  __int128 v56; // [rsp+E0h] [rbp-20h] BYREF
  const unsigned __int16 *v57; // [rsp+F0h] [rbp-10h]
  unsigned __int16 v58[64]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v59[64]; // [rsp+180h] [rbp+80h] BYREF
  unsigned __int16 v60[64]; // [rsp+200h] [rbp+100h] BYREF
  unsigned __int16 v61[64]; // [rsp+280h] [rbp+180h] BYREF
  unsigned __int16 v62[64]; // [rsp+300h] [rbp+200h] BYREF
  unsigned __int16 v63[64]; // [rsp+380h] [rbp+280h] BYREF
  unsigned __int16 v64[64]; // [rsp+400h] [rbp+300h] BYREF
  unsigned __int16 v65[64]; // [rsp+480h] [rbp+380h] BYREF
  unsigned __int16 v66[64]; // [rsp+500h] [rbp+400h] BYREF
  unsigned __int16 v67[64]; // [rsp+580h] [rbp+480h] BYREF
  unsigned __int16 v68[64]; // [rsp+600h] [rbp+500h] BYREF
  unsigned __int16 v69[64]; // [rsp+680h] [rbp+580h] BYREF
  unsigned __int16 v70[64]; // [rsp+700h] [rbp+600h] BYREF

  v57 = L"\\";
  v53[0] = 0.0;
  v46 = 0;
  lpVtbl = a1->lpVtbl;
  v47 = 0;
  v56 = 0;
  v49 = 0;
  v5 = 0;
  get_Task = lpVtbl->get_Task;
  v52 = 0;
  bstrString = 0;
  v50 = 0;
  ppvData = 0;
  v54 = 0;
  v7 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, BSTR *))get_Task)(a1, &v50);
  v8 = -1;
  v9 = v7;
  if ( v7 < 0 )
  {
    v45 = 0;
    LODWORD(v46) = v7;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v58, 0x4000000000000800uLL);
      v10 = -1;
      do
        ++v10;
      while ( v58[v10] );
      EventingWriteEvent(&g_Eventing, PLA_EVENT_ERROR, 5, &v46, 4, qword_180147320, 1, &v45, 4, "PlaiExecuteTask", 16);
    }
    goto LABEL_96;
  }
  if ( !v50 || !*v50 )
    goto LABEL_107;
  v11 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, BSTR *))a1->lpVtbl->get_Name)(a1, &bstrString);
  v9 = v11;
  if ( v11 >= 0 )
  {
    v13 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, __int16 *))a1->lpVtbl->get_TaskRunAsSelf)(a1, &v47);
    v9 = v13;
    if ( v13 >= 0 )
    {
      Vector = SafeArrayCreateVector(8u, 0, 2u);
      v5 = Vector;
      if ( Vector )
      {
        v17 = SafeArrayAccessData(Vector, &ppvData);
        v9 = v17;
        if ( v17 >= 0 )
        {
          v19 = PlaiExpandTaskArguments(a1, (unsigned __int16 **)ppvData);
          v9 = v19;
          if ( v19 >= 0 )
          {
            v21 = ((__int64 (__fastcall *)(struct IDataCollectorSet *, char *))a1->lpVtbl->get_LatestOutputLocation)(
                    a1,
                    (char *)ppvData + 8);
            v9 = v21;
            if ( v21 >= 0 )
            {
              if ( *((_QWORD *)ppvData + 1)
                || (v25 = PlaiAllocStringEx((const unsigned __int16 *)&szPassword, v22, v23),
                    (*((_QWORD *)ppvData + 1) = v25) != 0) )
              {
                RegisteredTask = PlaTaskService::GetRegisteredTask((PlaTaskService *)&v56, v50, &v49);
                v9 = RegisteredTask;
                if ( RegisteredTask >= 0 )
                {
                  *((_QWORD *)&v54 + 1) = v5;
                  LOWORD(v54) = 8200;
                  v29 = ((__int64 (__fastcall *)(struct IRegisteredTask *, double *))v49->lpVtbl->get_LastRunTime)(
                          v49,
                          v53);
                  v9 = v29;
                  if ( v29 >= 0 )
                  {
                    v31 = v49->lpVtbl;
                    v55 = v46;
                    v32 = ((__int64 (__fastcall *)(struct IRegisteredTask *, __int128 *, bool, _QWORD, _QWORD, __int64 *))v31->RunEx)(
                            v49,
                            &v54,
                            v47 == -1,
                            0,
                            0,
                            &v52);
                    v9 = v32;
                    if ( v32 >= 0 )
                    {
                      if ( a2 )
                      {
                        v34 = PlaiWaitForTaskStart(v49, v53);
                        v9 = v34;
                        if ( v34 >= 0 )
                        {
                          v36 = PlaiWaitForTaskStop(v49);
                          v9 = v36;
                          if ( v36 < 0 )
                          {
                            LODWORD(v46) = 0;
                            v45 = v36;
                            if ( (_DWORD)xmmword_180169738 )
                            {
                              if ( (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                                && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                              {
                                PlaiWhoAmI(v70, 0x4000000000000800uLL);
                                v37 = -1;
                                do
                                  ++v37;
                                while ( v70[v37] );
                                goto LABEL_95;
                              }
                            }
                          }
                        }
                        else
                        {
                          LODWORD(v46) = 0;
                          v45 = v34;
                          if ( (_DWORD)xmmword_180169738
                            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                          {
                            PlaiWhoAmI(v69, 0x4000000000000800uLL);
                            v35 = -1;
                            do
                              ++v35;
                            while ( v69[v35] );
                            goto LABEL_95;
                          }
                        }
                      }
                    }
                    else
                    {
                      LODWORD(v46) = 0;
                      v45 = v32;
                      if ( (_DWORD)xmmword_180169738
                        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                      {
                        PlaiWhoAmI(v68, 0x4000000000000800uLL);
                        v33 = -1;
                        do
                          ++v33;
                        while ( v68[v33] );
                        goto LABEL_95;
                      }
                    }
                  }
                  else
                  {
                    LODWORD(v46) = 0;
                    v45 = v29;
                    if ( (_DWORD)xmmword_180169738
                      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                    {
                      PlaiWhoAmI(v67, 0x4000000000000800uLL);
                      v30 = -1;
                      do
                        ++v30;
                      while ( v67[v30] );
                      goto LABEL_95;
                    }
                  }
                }
                else
                {
                  LODWORD(v46) = 0;
                  v45 = RegisteredTask;
                  if ( (_DWORD)xmmword_180169738
                    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                  {
                    PlaiWhoAmI(v66, 0x4000000000000800uLL);
                    v28 = -1;
                    do
                      ++v28;
                    while ( v66[v28] );
                    goto LABEL_95;
                  }
                }
              }
              else
              {
                v9 = -2147024882;
                v45 = -2147024882;
                LODWORD(v46) = 0;
                if ( (_DWORD)xmmword_180169738
                  && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                  && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
                {
                  PlaiWhoAmI(v65, 0x4000000000000800uLL);
                  v26 = -1;
                  do
                    ++v26;
                  while ( v65[v26] );
                  goto LABEL_95;
                }
              }
            }
            else
            {
              LODWORD(v46) = 0;
              v45 = v21;
              if ( (_DWORD)xmmword_180169738
                && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
                && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
              {
                PlaiWhoAmI(v64, 0x4000000000000800uLL);
                v24 = -1;
                do
                  ++v24;
                while ( v64[v24] );
                goto LABEL_95;
              }
            }
          }
          else
          {
            LODWORD(v46) = 0;
            v45 = v19;
            if ( (_DWORD)xmmword_180169738
              && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
              && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
            {
              PlaiWhoAmI(v63, 0x4000000000000800uLL);
              v20 = -1;
              do
                ++v20;
              while ( v63[v20] );
              goto LABEL_95;
            }
          }
        }
        else
        {
          LODWORD(v46) = 0;
          v45 = v17;
          if ( (_DWORD)xmmword_180169738
            && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
            && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
          {
            PlaiWhoAmI(v62, 0x4000000000000800uLL);
            v18 = -1;
            do
              ++v18;
            while ( v62[v18] );
            goto LABEL_95;
          }
        }
      }
      else
      {
        v9 = -2147024882;
        v45 = -2147024882;
        LODWORD(v46) = 0;
        if ( (_DWORD)xmmword_180169738
          && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
          && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
        {
          PlaiWhoAmI(v61, 0x4000000000000800uLL);
          v16 = -1;
          do
            ++v16;
          while ( v61[v16] );
          goto LABEL_95;
        }
      }
    }
    else
    {
      LODWORD(v46) = 0;
      v45 = v13;
      if ( (_DWORD)xmmword_180169738
        && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
        && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
      {
        PlaiWhoAmI(v60, 0x4000000000000800uLL);
        v14 = -1;
        do
          ++v14;
        while ( v60[v14] );
        goto LABEL_95;
      }
    }
  }
  else
  {
    LODWORD(v46) = 0;
    v45 = v11;
    if ( (_DWORD)xmmword_180169738
      && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
      && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
    {
      PlaiWhoAmI(v59, 0x4000000000000800uLL);
      v12 = -1;
      do
        ++v12;
      while ( v59[v12] );
LABEL_95:
      EventingWriteEvent(&g_Eventing, PLA_EVENT_ERROR, 5, &v45, 4, qword_180147320, 1, &v46, 4, "PlaiExecuteTask", 16);
    }
  }
LABEL_96:
  if ( bstrString && v50 )
  {
    LODWORD(v46) = v9;
    if ( v9 < 0 )
    {
      v39 = -1;
      do
        ++v39;
      while ( v50[v39] );
      do
        ++v8;
      while ( bstrString[v8] );
      EventingWriteEvent(
        &g_Eventing,
        PLA_EVENTLOG_TASK_FAILED,
        3,
        bstrString,
        (unsigned int)(2 * v8) + 2LL,
        v50,
        (unsigned int)(2 * v39) + 2LL,
        &v46,
        4,
        v43,
        v44);
    }
    else
    {
      v38 = -1;
      do
        ++v38;
      while ( v50[v38] );
      do
        ++v8;
      while ( bstrString[v8] );
      EventingWriteEvent(
        &g_Eventing,
        PLA_EVENTLOG_TASK,
        2,
        bstrString,
        (unsigned int)(2 * v8) + 2LL,
        v50,
        (unsigned int)(2 * v38) + 2LL,
        v41,
        v42,
        v43,
        v44);
    }
  }
LABEL_107:
  if ( ppvData )
  {
    SafeArrayUnaccessData(v5);
    ppvData = 0;
  }
  if ( v5 )
    SafeArrayDestroy(v5);
  PlaiFreeString(bstrString);
  bstrString = 0;
  PlaiFreeString(v50);
  v50 = 0;
  if ( v49 )
  {
    ((void (__fastcall *)(struct IRegisteredTask *))v49->lpVtbl->Release)(v49);
    v49 = 0;
  }
  if ( v52 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
    v52 = 0;
  }
  PlaTaskService::~PlaTaskService((PlaTaskService *)&v56);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18009be9c  push    rbp
0x18009be9e  push    rbx
0x18009be9f  push    rsi
0x18009bea0  push    rdi
0x18009bea1  push    r12
0x18009bea3  push    r13
0x18009bea5  push    r14
0x18009bea7  push    r15
0x18009bea9  lea     rbp, [rsp-698h]
0x18009beb1  sub     rsp, 798h
0x18009beb8  mov     rax, cs:__security_cookie
0x18009bebf  xor     rax, rsp
0x18009bec2  mov     [rbp+6D0h+var_50], rax
0x18009bec9  xor     r12d, r12d
0x18009becc  lea     rax, asc_180150280; "\\"
0x18009bed3  mov     [rbp+6D0h+var_6E0], rax
0x18009bed7  xorps   xmm0, xmm0
0x18009beda  xor     eax, eax
0x18009bedc  movsd   [rbp+6D0h+var_720], xmm0
0x18009bee1  mov     [rsp+7D0h+var_758], rax
0x18009bee6  mov     r14d, edx
0x18009bee9  mov     rax, [rcx]
0x18009beec  lea     rdx, [rbp+6D0h+var_738]
0x18009bef0  mov     rsi, rcx
0x18009bef3  mov     [rbp+6D0h+var_750], r12w
0x18009bef8  movdqu  [rbp+6D0h+var_6F0], xmm0
0x18009befd  mov     [rbp+6D0h+var_740], r12
0x18009bf01  mov     r15d, r12d
0x18009bf04  mov     rax, [rax+140h]
0x18009bf0b  mov     [rbp+6D0h+var_728], r12
0x18009bf0f  mov     [rbp+6D0h+bstrString], r12
0x18009bf13  mov     [rbp+6D0h+var_738], r12
0x18009bf17  mov     [rbp+6D0h+ppvData], r12
0x18009bf1b  movups  [rbp+6D0h+var_710], xmm0
0x18009bf1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009bf24  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18009bf28  lea     r13d, [r12+2]
0x18009bf2d  mov     ebx, eax
0x18009bf2f  test    eax, eax
0x18009bf31  jns     loc_18009BFCD
0x18009bf37  cmp     dword ptr cs:xmmword_180169738, r12d
0x18009bf3e  mov     [rsp+7D0h+var_760], r12d
0x18009bf43  mov     dword ptr [rsp+7D0h+var_758], eax
0x18009bf47  jz      loc_18009C739
0x18009bf4d  mov     rdx, 4000000000000800h; unsigned __int64
0x18009bf57  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009bf5e  jz      loc_18009C739
0x18009bf64  mov     rax, cs:qword_180169748
0x18009bf6b  and     rax, rdx
0x18009bf6e  cmp     cs:qword_180169748, rax
0x18009bf75  jnz     loc_18009C739
0x18009bf7b  lea     rcx, [rbp+6D0h+var_6D0]; unsigned __int16 *
0x18009bf7f  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009bf84  lea     rcx, [rbp+6D0h+var_6D0]
0x18009bf88  mov     rax, rdi
0x18009bf8b  inc     rax
0x18009bf8e  cmp     [rcx+rax*2], r12w
0x18009bf93  jnz     short loc_18009BF8B
0x18009bf95  lea     ecx, [rax+rax]
0x18009bf98  lea     rax, [rbp+6D0h+var_6D0]
0x18009bf9c  add     rcx, r13
0x18009bf9f  mov     [rsp+7D0h+var_770], rcx
0x18009bfa4  lea     r9, [rsp+7D0h+var_758]
0x18009bfa9  mov     [rsp+7D0h+var_778], rax
0x18009bfae  lea     rax, aPlaiexecutetas; "PlaiExecuteTask"
0x18009bfb5  mov     [rsp+7D0h+var_780], 10h
0x18009bfbe  mov     [rsp+7D0h+var_788], rax
0x18009bfc3  lea     rax, [rsp+7D0h+var_760]
0x18009bfc8  jmp     loc_18009C6F4
0x18009bfcd  mov     rcx, [rbp+6D0h+var_738]
0x18009bfd1  test    rcx, rcx
0x18009bfd4  jz      loc_18009C82D
0x18009bfda  cmp     r12w, [rcx]
0x18009bfde  jz      loc_18009C82D
0x18009bfe4  mov     rax, [rsi]
0x18009bfe7  lea     rdx, [rbp+6D0h+bstrString]
0x18009bfeb  mov     rcx, rsi
0x18009bfee  mov     rax, [rax+0A0h]
0x18009bff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009bffa  mov     ebx, eax
0x18009bffc  test    eax, eax
0x18009bffe  jns     short loc_18009C073
0x18009c000  cmp     dword ptr cs:xmmword_180169738, r12d
0x18009c007  mov     dword ptr [rsp+7D0h+var_758], r12d
0x18009c00c  mov     [rsp+7D0h+var_760], eax
0x18009c010  jz      loc_18009C739
0x18009c016  mov     rdx, 4000000000000800h; unsigned __int64
0x18009c020  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009c027  jz      loc_18009C739
0x18009c02d  mov     rax, cs:qword_180169748
0x18009c034  and     rax, rdx
0x18009c037  cmp     cs:qword_180169748, rax
0x18009c03e  jnz     loc_18009C739
0x18009c044  lea     rcx, [rbp+6D0h+var_650]; unsigned __int16 *
0x18009c04b  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009c050  lea     rcx, [rbp+6D0h+var_650]
0x18009c057  mov     rax, rdi
0x18009c05a  inc     rax
0x18009c05d  cmp     [rcx+rax*2], r12w
0x18009c062  jnz     short loc_18009C05A
0x18009c064  lea     ecx, [rax+rax]
0x18009c067  lea     rax, [rbp+6D0h+var_650]
0x18009c06e  jmp     loc_18009C6C8
0x18009c073  mov     rax, [rsi]
0x18009c076  lea     rdx, [rbp+6D0h+var_750]
0x18009c07a  mov     rcx, rsi
0x18009c07d  mov     rax, [rax+150h]
0x18009c084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c089  mov     ebx, eax
0x18009c08b  test    eax, eax
0x18009c08d  jns     short loc_18009C102
0x18009c08f  cmp     dword ptr cs:xmmword_180169738, r12d
0x18009c096  mov     dword ptr [rsp+7D0h+var_758], r12d
0x18009c09b  mov     [rsp+7D0h+var_760], eax
0x18009c09f  jz      loc_18009C739
0x18009c0a5  mov     rdx, 4000000000000800h; unsigned __int64
0x18009c0af  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009c0b6  jz      loc_18009C739
0x18009c0bc  mov     rax, cs:qword_180169748
0x18009c0c3  and     rax, rdx
0x18009c0c6  cmp     cs:qword_180169748, rax
0x18009c0cd  jnz     loc_18009C739
0x18009c0d3  lea     rcx, [rbp+6D0h+var_5D0]; unsigned __int16 *
0x18009c0da  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009c0df  lea     rcx, [rbp+6D0h+var_5D0]
0x18009c0e6  mov     rax, rdi
0x18009c0e9  inc     rax
0x18009c0ec  cmp     [rcx+rax*2], r12w
0x18009c0f1  jnz     short loc_18009C0E9
0x18009c0f3  lea     ecx, [rax+rax]
0x18009c0f6  lea     rax, [rbp+6D0h+var_5D0]
0x18009c0fd  jmp     loc_18009C6C8
0x18009c102  mov     ecx, 8; vt
0x18009c107  mov     r8d, r13d; cElements
0x18009c10a  xor     edx, edx; lLbound
0x18009c10c  call    cs:__imp_SafeArrayCreateVector
0x18009c112  mov     r15, rax
0x18009c115  test    rax, rax
0x18009c118  jnz     short loc_18009C194
0x18009c11a  cmp     dword ptr cs:xmmword_180169738, r12d
0x18009c121  mov     ecx, 8007000Eh
0x18009c126  mov     ebx, ecx
0x18009c128  mov     [rsp+7D0h+var_760], ecx
0x18009c12c  mov     dword ptr [rsp+7D0h+var_758], r12d
0x18009c131  jz      loc_18009C739
0x18009c137  mov     rdx, 4000000000000800h; unsigned __int64
0x18009c141  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009c148  jz      loc_18009C739
0x18009c14e  mov     rax, cs:qword_180169748
0x18009c155  and     rax, rdx
0x18009c158  cmp     cs:qword_180169748, rax
0x18009c15f  jnz     loc_18009C739
0x18009c165  lea     rcx, [rbp+6D0h+var_550]; unsigned __int16 *
0x18009c16c  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009c171  lea     rcx, [rbp+6D0h+var_550]
0x18009c178  mov     rax, rdi
0x18009c17b  inc     rax
0x18009c17e  cmp     [rcx+rax*2], r12w
0x18009c183  jnz     short loc_18009C17B
0x18009c185  lea     ecx, [rax+rax]
0x18009c188  lea     rax, [rbp+6D0h+var_550]
0x18009c18f  jmp     loc_18009C6C8
0x18009c194  lea     rdx, [rbp+6D0h+ppvData]; ppvData
0x18009c198  mov     rcx, r15; psa
0x18009c19b  call    cs:__imp_SafeArrayAccessData
0x18009c1a1  mov     ebx, eax
0x18009c1a3  test    eax, eax
0x18009c1a5  jns     short loc_18009C21A
0x18009c1a7  cmp     dword ptr cs:xmmword_180169738, r12d
0x18009c1ae  mov     dword ptr [rsp+7D0h+var_758], r12d
0x18009c1b3  mov     [rsp+7D0h+var_760], eax
0x18009c1b7  jz      loc_18009C739
0x18009c1bd  mov     rdx, 4000000000000800h; unsigned __int64
0x18009c1c7  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009c1ce  jz      loc_18009C739
0x18009c1d4  mov     rax, cs:qword_180169748
0x18009c1db  and     rax, rdx
0x18009c1de  cmp     cs:qword_180169748, rax
0x18009c1e5  jnz     loc_18009C739
0x18009c1eb  lea     rcx, [rbp+6D0h+var_4D0]; unsigned __int16 *
0x18009c1f2  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009c1f7  lea     rcx, [rbp+6D0h+var_4D0]
0x18009c1fe  mov     rax, rdi
0x18009c201  inc     rax
0x18009c204  cmp     [rcx+rax*2], r12w
0x18009c209  jnz     short loc_18009C201
0x18009c20b  lea     ecx, [rax+rax]
0x18009c20e  lea     rax, [rbp+6D0h+var_4D0]
0x18009c215  jmp     loc_18009C6C8
0x18009c21a  mov     rdx, [rbp+6D0h+ppvData]; unsigned __int16 **
0x18009c21e  mov     rcx, rsi; struct IDataCollectorSet *
0x18009c221  call    ?PlaiExpandTaskArguments@@YAJPEAUIDataCollectorSet@@PEAPEAG@Z; PlaiExpandTaskArguments(IDataCollectorSet *,ushort * *)
0x18009c226  mov     ebx, eax
0x18009c228  test    eax, eax
0x18009c22a  jns     short loc_18009C29F
0x18009c22c  cmp     dword ptr cs:xmmword_180169738, r12d
0x18009c233  mov     dword ptr [rsp+7D0h+var_758], r12d
0x18009c238  mov     [rsp+7D0h+var_760], eax
0x18009c23c  jz      loc_18009C739
0x18009c242  mov     rdx, 4000000000000800h; unsigned __int64
0x18009c24c  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009c253  jz      loc_18009C739
0x18009c259  mov     rax, cs:qword_180169748
0x18009c260  and     rax, rdx
0x18009c263  cmp     cs:qword_180169748, rax
0x18009c26a  jnz     loc_18009C739
0x18009c270  lea     rcx, [rbp+6D0h+var_450]; unsigned __int16 *
0x18009c277  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009c27c  lea     rcx, [rbp+6D0h+var_450]
0x18009c283  mov     rax, rdi
0x18009c286  inc     rax
0x18009c289  cmp     [rcx+rax*2], r12w
0x18009c28e  jnz     short loc_18009C286
0x18009c290  lea     ecx, [rax+rax]
0x18009c293  lea     rax, [rbp+6D0h+var_450]
0x18009c29a  jmp     loc_18009C6C8
0x18009c29f  mov     rax, [rsi]
0x18009c2a2  mov     rcx, rsi
0x18009c2a5  mov     rdx, [rbp+6D0h+ppvData]
0x18009c2a9  add     rdx, 8
0x18009c2ad  mov     rax, [rax+90h]
0x18009c2b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c2b9  mov     ebx, eax
0x18009c2bb  test    eax, eax
0x18009c2bd  jns     short loc_18009C332
0x18009c2bf  cmp     dword ptr cs:xmmword_180169738, r12d
0x18009c2c6  mov     dword ptr [rsp+7D0h+var_758], r12d
0x18009c2cb  mov     [rsp+7D0h+var_760], eax
0x18009c2cf  jz      loc_18009C739
0x18009c2d5  mov     rdx, 4000000000000800h; unsigned __int64
0x18009c2df  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009c2e6  jz      loc_18009C739
0x18009c2ec  mov     rax, cs:qword_180169748
0x18009c2f3  and     rax, rdx
0x18009c2f6  cmp     cs:qword_180169748, rax
0x18009c2fd  jnz     loc_18009C739
0x18009c303  lea     rcx, [rbp+6D0h+var_3D0]; unsigned __int16 *
0x18009c30a  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009c30f  lea     rcx, [rbp+6D0h+var_3D0]
0x18009c316  mov     rax, rdi
0x18009c319  inc     rax
0x18009c31c  cmp     [rcx+rax*2], r12w
0x18009c321  jnz     short loc_18009C319
0x18009c323  lea     ecx, [rax+rax]
0x18009c326  lea     rax, [rbp+6D0h+var_3D0]
0x18009c32d  jmp     loc_18009C6C8
0x18009c332  mov     rax, [rbp+6D0h+ppvData]
0x18009c336  cmp     [rax+8], r12
0x18009c33a  jnz     loc_18009C3D8
0x18009c340  lea     rcx, szPassword; unsigned __int16 *
0x18009c347  call    ?PlaiAllocStringEx@@YAPEAGPEBGPEBDH@Z; PlaiAllocStringEx(ushort const *,char const *,int)
0x18009c34c  mov     rcx, [rbp+6D0h+ppvData]
0x18009c350  mov     [rcx+8], rax
0x18009c354  mov     rax, [rbp+6D0h+ppvData]
0x18009c358  cmp     [rax+8], r12
0x18009c35c  jnz     short loc_18009C3D8
0x18009c35e  cmp     dword ptr cs:xmmword_180169738, r12d
0x18009c365  mov     ecx, 8007000Eh
0x18009c36a  mov     ebx, ecx
0x18009c36c  mov     [rsp+7D0h+var_760], ecx
0x18009c370  mov     dword ptr [rsp+7D0h+var_758], r12d
0x18009c375  jz      loc_18009C739
0x18009c37b  mov     rdx, 4000000000000800h; unsigned __int64
0x18009c385  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009c38c  jz      loc_18009C739
0x18009c392  mov     rax, cs:qword_180169748
0x18009c399  and     rax, rdx
0x18009c39c  cmp     cs:qword_180169748, rax
0x18009c3a3  jnz     loc_18009C739
0x18009c3a9  lea     rcx, [rbp+6D0h+var_350]; unsigned __int16 *
0x18009c3b0  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009c3b5  lea     rcx, [rbp+6D0h+var_350]
0x18009c3bc  mov     rax, rdi
0x18009c3bf  inc     rax
0x18009c3c2  cmp     [rcx+rax*2], r12w
0x18009c3c7  jnz     short loc_18009C3BF
0x18009c3c9  lea     ecx, [rax+rax]
0x18009c3cc  lea     rax, [rbp+6D0h+var_350]
0x18009c3d3  jmp     loc_18009C6C8
0x18009c3d8  mov     rdx, [rbp+6D0h+var_738]; unsigned __int16 *
0x18009c3dc  lea     r8, [rbp+6D0h+var_740]; struct IRegisteredTask **
0x18009c3e0  lea     rcx, [rbp+6D0h+var_6F0]; this
0x18009c3e4  call    ?GetRegisteredTask@PlaTaskService@@QEAAJPEAGPEAPEAUIRegisteredTask@@@Z; PlaTaskService::GetRegisteredTask(ushort *,IRegisteredTask * *)
0x18009c3e9  mov     ebx, eax
0x18009c3eb  test    eax, eax
0x18009c3ed  jns     short loc_18009C462
0x18009c3ef  cmp     dword ptr cs:xmmword_180169738, r12d
0x18009c3f6  mov     dword ptr [rsp+7D0h+var_758], r12d
0x18009c3fb  mov     [rsp+7D0h+var_760], eax
0x18009c3ff  jz      loc_18009C739
0x18009c405  mov     rdx, 4000000000000800h; unsigned __int64
0x18009c40f  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009c416  jz      loc_18009C739
0x18009c41c  mov     rax, cs:qword_180169748
0x18009c423  and     rax, rdx
0x18009c426  cmp     cs:qword_180169748, rax
0x18009c42d  jnz     loc_18009C739
0x18009c433  lea     rcx, [rbp+6D0h+var_2D0]; unsigned __int16 *
0x18009c43a  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009c43f  lea     rcx, [rbp+6D0h+var_2D0]
  ... truncated ...
```
