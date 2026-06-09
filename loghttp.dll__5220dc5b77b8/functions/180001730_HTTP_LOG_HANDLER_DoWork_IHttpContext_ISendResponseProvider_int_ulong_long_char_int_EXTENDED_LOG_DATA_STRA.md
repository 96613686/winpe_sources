# HTTP_LOG_HANDLER::DoWork(IHttpContext *,ISendResponseProvider *,int,ulong,long,char *,int,EXTENDED_LOG_DATA *,STRA *)

- ea: `0x180001730`
- end: `0x180001ca5`
- name: `?DoWork@HTTP_LOG_HANDLER@@QEAA?AW4REQUEST_NOTIFICATION_STATUS@@PEAVIHttpContext@@PEAVISendResponseProvider@@HKJPEADHPEAVEXTENDED_LOG_DATA@@PEAVSTRA@@@Z`
- size: `1397`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64, int, int, __int64, __int64, int, void *, STRA *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001080`

## callees

- `0x180001730`
- `0x1800047f8`
- `0x1800048ec`
- `0x1800056e6`
- `0x180006010`

## import_xrefs

- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180001bb0`
- `iisutil!?QueryStr@STRA@@QEAAPEADXZ` at `0x180001bb0`
- `iisutil!?IsEmpty@STRA@@QEBA_NXZ` at `0x180001b82`
- `iisutil!?IsEmpty@STRA@@QEBA_NXZ` at `0x180001b82`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180001b96`
- `iisutil!?QueryCCH@STRA@@QEBAKXZ` at `0x180001b96`
- `iisutil!?QueryStr@STRA@@QEBAPEBDXZ` at `0x180001c39`
- `iisutil!?QueryStr@STRA@@QEBAPEBDXZ` at `0x180001c39`
- `iisutil!PuDbgPrint` at `0x180001978`
- `iisutil!PuDbgPrint` at `0x180001978`
- `WS2_32!__imp_ntohs` at `0x1800018cb`
- `WS2_32!__imp_ntohs` at `0x1800018cb`

## string_xrefs

- `0x180001971`: `servercommon\inetsrv\iis\iisrearc\iis70\httplog\httplog.cxx`

## pseudocode

```c
__int64 __fastcall HTTP_LOG_HANDLER::DoWork(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        int a4,
        int a5,
        __int64 a6,
        __int64 a7,
        int a8,
        void *a9,
        STRA *a10)
{
  __int64 v13; // rax
  __int64 v14; // rdi
  __int64 v15; // rsi
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // rbp
  __int64 v19; // r13
  __int64 v20; // r12
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rcx
  _WORD *v24; // rax
  u_short v25; // cx
  __int64 v26; // rax
  __int64 v27; // rcx
  bool v28; // zf
  int v29; // eax
  _WORD *v30; // rax
  _WORD *v32; // rdx
  __int64 v33; // rax
  int v34; // ecx
  __int64 v35; // rax
  STRA *v36; // rdi
  W3LOGSVC_APP_CONTEXT *v37; // r15
  unsigned __int8 CCH; // bp
  BOOL v39; // esi
  const char *v40; // rdi
  __int64 (__fastcall ***v41)(_QWORD); // rax
  unsigned int v42; // eax
  __int16 v43; // ax
  unsigned __int64 v44; // rdi
  BOOL v45; // esi
  __int64 (__fastcall ***v46)(_QWORD); // rax
  unsigned int v47; // ebx
  const char *Str; // rax
  __int64 v49; // rax
  __int64 v50; // [rsp+A0h] [rbp+8h] BYREF
  _WORD *v51; // [rsp+A8h] [rbp+10h]
  int v52; // [rsp+B8h] [rbp+20h] BYREF

  v52 = a4;
  v13 = (*(__int64 (__fastcall **)(__int64 *))(*a2 + 240))(a2);
  v14 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 24LL))(v13);
  v15 = (*(__int64 (__fastcall **)(__int64 *))(*a2 + 32))(a2);
  v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
  v17 = *a2;
  v18 = v16;
  a5 = 0;
  v50 = 0;
  v52 = 0;
  if ( (*(int (__fastcall **)(__int64 *, const char *, __int64 *, int *))(v17 + 120))(a2, "REMOTE_HOST", &v50, &v52) < 0 )
    return 2;
  v19 = a1 + 8;
  *(_QWORD *)(a1 + 56) = v50;
  *(_WORD *)(a1 + 16) = v52;
  v20 = -1;
  if ( (*(__int64 (__fastcall **)(__int64 *))(*a2 + 48))(a2) )
  {
    v21 = (*(__int64 (__fastcall **)(__int64 *))(*a2 + 48))(a2);
    v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v21 + 8LL))(v21);
    *(_QWORD *)(a1 + 40) = v22;
    if ( v22 )
    {
      v23 = -1;
      do
        ++v23;
      while ( *(_WORD *)(v22 + 2 * v23) );
      *(_WORD *)(a1 + 12) = 2 * v23;
    }
  }
  else
  {
    *(_QWORD *)(a1 + 40) = &dword_180007E94;
    *(_WORD *)(a1 + 12) = 0;
  }
  if ( (*(int (__fastcall **)(__int64 *, const char *, __int64 *, int *))(*a2 + 120))(a2, "LOCAL_ADDR", &v50, &v52) < 0 )
    return 2;
  *(_QWORD *)(a1 + 80) = v50;
  *(_WORD *)(a1 + 22) = v52;
  v24 = *(_WORD **)(v18 + 112);
  if ( *v24 == 2 || (v25 = 0, *v24 == 23) )
    v25 = v24[1];
  *(_WORD *)(a1 + 136) = ntohs(v25);
  v26 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v14 + 64LL))(v14);
  *(_QWORD *)(a1 + 88) = v26;
  v27 = -1;
  do
    ++v27;
  while ( *(_BYTE *)(v26 + v27) );
  v28 = a8 == 0;
  *(_WORD *)(a1 + 24) = v27;
  *(_DWORD *)(a1 + 144) = *(_DWORD *)(v18 + 36);
  if ( v28 )
  {
    *(_QWORD *)(a1 + 48) = *(_QWORD *)(v18 + 88);
    *(_WORD *)(a1 + 14) = *(_WORD *)(v18 + 68);
  }
  else
  {
    v29 = *(unsigned __int16 *)(v18 + 68);
    *(_WORD *)(a1 + 14) = v29;
    v30 = (_WORD *)(*(__int64 (__fastcall **)(__int64 *, _QWORD))(*a2 + 144))(a2, (unsigned int)(v29 + 2));
    v51 = v30;
    if ( !v30 )
    {
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\httplog\\httplog.cxx",
          740,
          "HTTP_LOG_HANDLER::DoWork",
          "Failed to request memory. hr = %x\n",
          -2147024888);
      return 2;
    }
    memcpy_0(v30, *(const void **)(v18 + 88), *(unsigned __int16 *)(a1 + 14));
    v32 = v51;
    v51[(unsigned __int64)*(unsigned __int16 *)(a1 + 14) >> 1] = 0;
    *(_QWORD *)(a1 + 48) = v32;
  }
  if ( (*(unsigned int (__fastcall **)(__int64 *, const char *, __int64 *, int *))(*a2 + 120))(
         a2,
         "LOG_QUERY_STRING",
         &v50,
         &v52) == -2147023483 )
  {
    v33 = (*(__int64 (__fastcall **)(__int64 *))(*a2 + 240))(a2);
    if ( (*(int (__fastcall **)(__int64, const char *, __int64 *, int *))(*(_QWORD *)v33 + 120LL))(
           v33,
           "QUERY_STRING",
           &v50,
           &v52) < 0 )
      return 2;
  }
  *(_QWORD *)(a1 + 96) = v50;
  *(_WORD *)(a1 + 26) = v52;
  (*(void (__fastcall **)(__int64, __int64, __int64, _QWORD, _QWORD, int *, _QWORD, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v15 + 184LL))(
    v15,
    a1 + 138,
    a1 + 148,
    0,
    0,
    &a5,
    0,
    0,
    0,
    0);
  v34 = a5;
  if ( (a5 & 0x1FFF0000) == 0x70000 && a5 < 0 )
    v34 = (unsigned __int16)a5;
  *(_DWORD *)(a1 + 140) = v34;
  *(_QWORD *)(a1 + 64) = HTTP_LOG_HANDLER::sm_achComputerName;
  *(_WORD *)(a1 + 18) = HTTP_LOG_HANDLER::sm_cchComputerName;
  *(_QWORD *)(a1 + 104) = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v14 + 16LL))(
                            v14,
                            28,
                            a1 + 28);
  *(_QWORD *)(a1 + 112) = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v14 + 16LL))(
                            v14,
                            40,
                            a1 + 30);
  *(_QWORD *)(a1 + 120) = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v14 + 16LL))(
                            v14,
                            25,
                            a1 + 32);
  v35 = (*(__int64 (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v14 + 16LL))(v14, 36, a1 + 34);
  v28 = a8 == 0;
  *(_QWORD *)(a1 + 128) = v35;
  if ( v28 )
  {
    v49 = a7;
    *(_QWORD *)(a1 + 72) = a7;
    do
      ++v20;
    while ( *(_BYTE *)(v49 + v20) );
    *(_WORD *)(a1 + 20) = v20;
  }
  else
  {
    v36 = a10;
    if ( STRA::IsEmpty(a10) )
    {
      v44 = *(_QWORD *)(v18 + 16);
      v37 = (W3LOGSVC_APP_CONTEXT *)(a1 + 152);
      v45 = dword_18000B050 == 1;
      v46 = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(__int64 *))*a2)(a2);
      v47 = (**v46)(v46);
      Str = STRA::QueryStr((STRA *)qword_18000B018);
      W3LOGSVC_APP_CONTEXT::SetContext(v37, Str, v47, v44, a9, v45);
      v43 = 97;
    }
    else
    {
      v37 = (W3LOGSVC_APP_CONTEXT *)(a1 + 250);
      CCH = STRA::QueryCCH(v36);
      v39 = dword_18000B050 == 1;
      v40 = STRA::QueryStr(v36);
      v41 = (__int64 (__fastcall ***)(_QWORD))(*(__int64 (__fastcall **)(__int64 *))*a2)(a2);
      v42 = (**v41)(v41);
      W3LOGSVC_FAST_APP_CONTEXT::SetContext(v37, v42, v40, CCH, v39);
      v43 = CCH + 11;
    }
    *(_QWORD *)(v19 + 64) = v37;
    *(_WORD *)(v19 + 12) = v43;
  }
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)a3 + 40LL))(a3, v19);
  return 0;
}

```

## disassembly

```asm
0x180001730  mov     [rsp+arg_10], rbx
0x180001735  mov     [rsp+arg_18], r9d
0x18000173a  push    rbp
0x18000173b  push    rsi
0x18000173c  push    rdi
0x18000173d  push    r12
0x18000173f  push    r13
0x180001741  push    r14
0x180001743  push    r15
0x180001745  sub     rsp, 60h
0x180001749  mov     rax, [rdx]
0x18000174c  mov     r15, rcx
0x18000174f  mov     rcx, rdx
0x180001752  mov     r14, r8
0x180001755  mov     rbx, rdx
0x180001758  mov     rax, [rax+0F0h]
0x18000175f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001764  mov     rcx, rax
0x180001767  mov     rdx, [rax]
0x18000176a  mov     rax, [rdx+18h]
0x18000176e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001773  mov     rcx, [rbx]
0x180001776  mov     rdi, rax
0x180001779  mov     rax, [rcx+20h]
0x18000177d  mov     rcx, rbx
0x180001780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001785  mov     rcx, [rdi]
0x180001788  mov     rsi, rax
0x18000178b  mov     rax, [rcx+8]
0x18000178f  mov     rcx, rdi
0x180001792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001797  mov     rcx, [rbx]
0x18000179a  lea     r9, [rsp+98h+arg_18]
0x1800017a2  mov     rbp, rax
0x1800017a5  lea     r8, [rsp+98h+arg_0]
0x1800017ad  xor     eax, eax
0x1800017af  lea     rdx, aRemoteHost; "REMOTE_HOST"
0x1800017b6  mov     [rsp+98h+arg_20], eax
0x1800017bd  mov     [rsp+98h+arg_0], rax
0x1800017c5  mov     [rsp+98h+arg_18], eax
0x1800017cc  mov     rax, [rcx+78h]
0x1800017d0  mov     rcx, rbx
0x1800017d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800017d8  test    eax, eax
0x1800017da  js      loc_18000197E
0x1800017e0  mov     rax, [rsp+98h+arg_0]
0x1800017e8  lea     r13, [r15+8]
0x1800017ec  mov     [r13+30h], rax
0x1800017f0  mov     rcx, rbx
0x1800017f3  movzx   eax, word ptr [rsp+98h+arg_18]
0x1800017fb  mov     [r13+8], ax
0x180001800  mov     rax, [rbx]
0x180001803  mov     rax, [rax+30h]
0x180001807  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000180c  mov     r12, 0FFFFFFFFFFFFFFFFh
0x180001813  test    rax, rax
0x180001816  jnz     short loc_18000182C
0x180001818  lea     rax, dword_180007E94
0x18000181f  mov     [r13+20h], rax
0x180001823  xor     eax, eax
0x180001825  mov     [r13+4], ax
0x18000182a  jmp     short loc_18000186B
0x18000182c  mov     rax, [rbx]
0x18000182f  mov     rcx, rbx
0x180001832  mov     rax, [rax+30h]
0x180001836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000183b  mov     rdx, rax
0x18000183e  mov     rcx, [rax]
0x180001841  mov     rax, [rcx+8]
0x180001845  mov     rcx, rdx
0x180001848  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000184d  mov     [r13+20h], rax
0x180001851  test    rax, rax
0x180001854  jz      short loc_18000186B
0x180001856  mov     rcx, r12
0x180001859  inc     rcx
0x18000185c  cmp     word ptr [rax+rcx*2], 0
0x180001861  jnz     short loc_180001859
0x180001863  add     cx, cx
0x180001866  mov     [r13+4], cx
0x18000186b  mov     rax, [rbx]
0x18000186e  lea     r9, [rsp+98h+arg_18]
0x180001876  lea     r8, [rsp+98h+arg_0]
0x18000187e  mov     rcx, rbx
0x180001881  lea     rdx, aLocalAddr; "LOCAL_ADDR"
0x180001888  mov     rax, [rax+78h]
0x18000188c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001891  test    eax, eax
0x180001893  js      loc_18000197E
0x180001899  mov     rax, [rsp+98h+arg_0]
0x1800018a1  mov     [r13+48h], rax
0x1800018a5  movzx   eax, word ptr [rsp+98h+arg_18]
0x1800018ad  mov     [r13+0Eh], ax
0x1800018b2  mov     rax, [rbp+70h]
0x1800018b6  movzx   edx, word ptr [rax]
0x1800018b9  cmp     dx, 2
0x1800018bd  jz      short loc_1800018C7
0x1800018bf  xor     ecx, ecx
0x1800018c1  cmp     dx, 17h
0x1800018c5  jnz     short loc_1800018CB
0x1800018c7  movzx   ecx, word ptr [rax+2]; netshort
0x1800018cb  call    cs:__imp_ntohs
0x1800018d1  mov     [r13+80h], ax
0x1800018d9  mov     rcx, rdi
0x1800018dc  mov     rax, [rdi]
0x1800018df  mov     rax, [rax+40h]
0x1800018e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018e8  mov     [r13+50h], rax
0x1800018ec  mov     rcx, r12
0x1800018ef  inc     rcx
0x1800018f2  cmp     byte ptr [rax+rcx], 0
0x1800018f6  jnz     short loc_1800018EF
0x1800018f8  cmp     [rsp+98h+arg_38], 0
0x180001900  mov     [r13+10h], cx
0x180001905  mov     eax, [rbp+24h]
0x180001908  mov     [r13+88h], eax
0x18000190f  jz      loc_1800019C8
0x180001915  movzx   eax, word ptr [rbp+44h]
0x180001919  mov     [r13+6], ax
0x18000191e  mov     rcx, [rbx]
0x180001921  lea     edx, [rax+2]
0x180001924  mov     rax, [rcx+90h]
0x18000192b  mov     rcx, rbx
0x18000192e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001933  mov     [rsp+98h+arg_8], rax
0x18000193b  test    rax, rax
0x18000193e  jnz     short loc_18000199B
0x180001940  test    byte ptr cs:g_dwDebugFlags, 3
0x180001947  jz      short loc_18000197E
0x180001949  mov     rcx, cs:g_pDebug
0x180001950  lea     rax, aFailedToReques; "Failed to request memory. hr = %x\n"
0x180001957  mov     [rsp+98h+var_70], 80070008h
0x18000195f  lea     r9, aHttpLogHandler_1; "HTTP_LOG_HANDLER::DoWork"
0x180001966  mov     r8d, 2E4h
0x18000196c  mov     [rsp+98h+var_78], rax
0x180001971  lea     rdx, aServercommonIn_0; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180001978  call    cs:__imp_PuDbgPrint
0x18000197e  mov     eax, 2
0x180001983  mov     rbx, [rsp+98h+arg_10]
0x18000198b  add     rsp, 60h
0x18000198f  pop     r15
0x180001991  pop     r14
0x180001993  pop     r13
0x180001995  pop     r12
0x180001997  pop     rdi
0x180001998  pop     rsi
0x180001999  pop     rbp
0x18000199a  retn
0x18000199b  movzx   r8d, word ptr [r13+6]; Size
0x1800019a0  mov     rcx, rax; void *
0x1800019a3  mov     rdx, [rbp+58h]; Src
0x1800019a7  call    memcpy_0
0x1800019ac  movzx   ecx, word ptr [r13+6]
0x1800019b1  mov     rdx, [rsp+98h+arg_8]
0x1800019b9  shr     rcx, 1
0x1800019bc  xor     eax, eax
0x1800019be  mov     [rdx+rcx*2], ax
0x1800019c2  mov     [r13+28h], rdx
0x1800019c6  jmp     short loc_1800019D9
0x1800019c8  mov     rax, [rbp+58h]
0x1800019cc  mov     [r13+28h], rax
0x1800019d0  movzx   eax, word ptr [rbp+44h]
0x1800019d4  mov     [r13+6], ax
0x1800019d9  mov     rax, [rbx]
0x1800019dc  lea     r9, [rsp+98h+arg_18]
0x1800019e4  lea     r8, [rsp+98h+arg_0]
0x1800019ec  mov     rcx, rbx
0x1800019ef  lea     rdx, aLogQueryString; "LOG_QUERY_STRING"
0x1800019f6  mov     rax, [rax+78h]
0x1800019fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800019ff  cmp     eax, 80070585h
0x180001a04  jnz     short loc_180001A49
0x180001a06  mov     rax, [rbx]
0x180001a09  mov     rcx, rbx
0x180001a0c  mov     rax, [rax+0F0h]
0x180001a13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a18  mov     r10, rax
0x180001a1b  lea     r9, [rsp+98h+arg_18]
0x180001a23  lea     r8, [rsp+98h+arg_0]
0x180001a2b  lea     rdx, aQueryString; "QUERY_STRING"
0x180001a32  mov     rcx, [rax]
0x180001a35  mov     rax, [rcx+78h]
0x180001a39  mov     rcx, r10
0x180001a3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001a41  test    eax, eax
0x180001a43  js      loc_18000197E
0x180001a49  mov     rax, [rsp+98h+arg_0]
0x180001a51  lea     rcx, [rsp+98h+arg_20]
0x180001a59  mov     [rsp+98h+var_50], 0
0x180001a62  lea     r8, [r13+8Ch]
0x180001a69  mov     [r13+58h], rax
0x180001a6d  lea     rdx, [r13+82h]
0x180001a74  movzx   eax, word ptr [rsp+98h+arg_18]
0x180001a7c  xor     r9d, r9d
0x180001a7f  mov     [rsp+98h+var_58], 0
0x180001a88  mov     [r13+12h], ax
0x180001a8d  mov     rax, [rsi]
0x180001a90  mov     [rsp+98h+var_60], 0
0x180001a99  mov     [rsp+98h+var_68], 0
0x180001aa2  mov     qword ptr [rsp+98h+var_70], rcx
0x180001aa7  mov     rcx, rsi
0x180001aaa  mov     rax, [rax+0B8h]
0x180001ab1  mov     [rsp+98h+var_78], 0
0x180001aba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001abf  mov     ecx, [rsp+98h+arg_20]
0x180001ac6  mov     eax, ecx
0x180001ac8  and     eax, 1FFF0000h
0x180001acd  cmp     eax, 70000h
0x180001ad2  jnz     short loc_180001ADB
0x180001ad4  test    ecx, ecx
0x180001ad6  jns     short loc_180001ADB
0x180001ad8  movzx   ecx, cx
0x180001adb  lea     rax, ?sm_achComputerName@HTTP_LOG_HANDLER@@0PADA; char near * HTTP_LOG_HANDLER::sm_achComputerName
0x180001ae2  mov     [r13+84h], ecx
0x180001ae9  mov     [r13+38h], rax
0x180001aed  lea     r8, [r13+14h]
0x180001af1  movzx   eax, word ptr cs:?sm_cchComputerName@HTTP_LOG_HANDLER@@0KA; ulong HTTP_LOG_HANDLER::sm_cchComputerName
0x180001af8  mov     edx, 1Ch
0x180001afd  mov     [r13+0Ah], ax
0x180001b02  mov     rcx, rdi
0x180001b05  mov     rax, [rdi]
0x180001b08  mov     rax, [rax+10h]
0x180001b0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b11  mov     [r13+60h], rax
0x180001b15  lea     r8, [r13+16h]
0x180001b19  mov     rax, [rdi]
0x180001b1c  mov     edx, 28h ; '('
0x180001b21  mov     rcx, rdi
0x180001b24  mov     rax, [rax+10h]
0x180001b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b2d  mov     [r13+68h], rax
0x180001b31  lea     r8, [r13+18h]
0x180001b35  mov     rax, [rdi]
0x180001b38  mov     edx, 19h
0x180001b3d  mov     rcx, rdi
0x180001b40  mov     rax, [rax+10h]
0x180001b44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b49  mov     [r13+70h], rax
0x180001b4d  lea     r8, [r13+1Ah]
0x180001b51  mov     rax, [rdi]
0x180001b54  mov     edx, 24h ; '$'
0x180001b59  mov     rcx, rdi
0x180001b5c  mov     rax, [rax+10h]
0x180001b60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001b65  cmp     [rsp+98h+arg_38], 0
0x180001b6d  mov     [r13+78h], rax
0x180001b71  jz      loc_180001C71
0x180001b77  mov     rdi, [rsp+98h+arg_48]
0x180001b7f  mov     rcx, rdi
0x180001b82  call    cs:__imp_?IsEmpty@STRA@@QEBA_NXZ; STRA::IsEmpty(void)
0x180001b88  test    al, al
0x180001b8a  jnz     short loc_180001BF7
0x180001b8c  mov     rcx, rdi
0x180001b8f  add     r15, 0FAh
0x180001b96  call    cs:__imp_?QueryCCH@STRA@@QEBAKXZ; STRA::QueryCCH(void)
0x180001b9c  mov     edx, cs:dword_18000B050
0x180001ba2  xor     esi, esi
0x180001ba4  cmp     edx, 1
0x180001ba7  mov     rcx, rdi
0x180001baa  mov     ebp, eax
0x180001bac  setz    sil
0x180001bb0  call    cs:__imp_?QueryStr@STRA@@QEAAPEADXZ; STRA::QueryStr(void)
0x180001bb6  mov     rcx, [rbx]
0x180001bb9  mov     rdi, rax
0x180001bbc  mov     rax, [rcx]
0x180001bbf  mov     rcx, rbx
0x180001bc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bc7  mov     rdx, rax
0x180001bca  mov     rcx, [rax]
0x180001bcd  mov     rax, [rcx]
0x180001bd0  mov     rcx, rdx
0x180001bd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001bd8  movzx   r9d, bpl; unsigned __int8
0x180001bdc  mov     dword ptr [rsp+98h+var_78], esi; int
0x180001be0  mov     r8, rdi; char *
0x180001be3  mov     edx, eax; unsigned int
0x180001be5  mov     rcx, r15; this
0x180001be8  call    ?SetContext@W3LOGSVC_FAST_APP_CONTEXT@@QEAAXKPEBDEH@Z; W3LOGSVC_FAST_APP_CONTEXT::SetContext(ulong,char const *,uchar,int)
0x180001bed  movzx   eax, bpl
0x180001bf1  add     ax, 0Bh
0x180001bf5  jmp     short loc_180001C66
0x180001bf7  mov     eax, cs:dword_18000B050
0x180001bfd  xor     esi, esi
0x180001bff  mov     rdi, [rbp+10h]
0x180001c03  add     r15, 98h
0x180001c0a  cmp     eax, 1
0x180001c0d  mov     rcx, rbx
0x180001c10  mov     rax, [rbx]
0x180001c13  setz    sil
0x180001c17  mov     rax, [rax]
0x180001c1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c1f  mov     rdx, rax
0x180001c22  mov     rcx, [rax]
0x180001c25  mov     rax, [rcx]
0x180001c28  mov     rcx, rdx
0x180001c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001c30  lea     rcx, qword_18000B018
0x180001c37  mov     ebx, eax
0x180001c39  call    cs:__imp_?QueryStr@STRA@@QEBAPEBDXZ; STRA::QueryStr(void)
0x180001c3f  mov     rcx, [rsp+98h+arg_40]
  ... truncated ...
```
