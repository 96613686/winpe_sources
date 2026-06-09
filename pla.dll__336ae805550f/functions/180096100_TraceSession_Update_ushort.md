# TraceSession::Update(ushort *)

- ea: `0x180096100`
- end: `0x1800968c1`
- name: `?Update@TraceSession@@UEAAJPEAG@Z`
- size: `1985`
- prototype: `int(TraceSession *__hidden this, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `13`
- tags: `installer_update`

## callees

- `0x180002bd0`
- `0x180002c8c`
- `0x180002ebc`
- `0x180004e98`
- `0x1800106d0`
- `0x1800109f4`
- `0x1800198b0`
- `0x18002b3a0`
- `0x18004a5ec`
- `0x18005136c`
- `0x180096100`
- `0x18013aee0`
- `0x18013c010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18009651e`
- `msvcrt!_wcsicmp` at `0x18009651e`
- `api-ms-win-eventing-legacy-l1-1-0!QueryTraceW` at `0x180096503`
- `api-ms-win-eventing-legacy-l1-1-0!QueryTraceW` at `0x180096503`
- `api-ms-win-eventing-legacy-l1-1-0!UpdateTraceW` at `0x180096669`
- `api-ms-win-eventing-legacy-l1-1-0!UpdateTraceW` at `0x180096669`

## string_xrefs

- `0x18009628d`: `TraceSession::Update`
- `0x180096822`: `TraceSession::Update`

## pseudocode

```c
__int64 __fastcall TraceSession::Update(TraceSession *this, unsigned __int16 *a2)
{
  __int64 v2; // rax
  __int64 (__fastcall *v5)(TraceSession *, struct ITraceDataCollector **); // rax
  PEVENT_TRACE_PROPERTIES v6; // rsi
  int v7; // eax
  BOOL v8; // r14d
  unsigned int v9; // edi
  __int64 v10; // rbx
  int *v11; // r9
  int *v12; // rcx
  int inited; // eax
  __int64 v14; // rbx
  int v15; // eax
  __int64 v16; // rbx
  __int64 v17; // rbx
  int v18; // eax
  int v19; // eax
  TraceSession *v20; // rcx
  int v21; // eax
  ULONG TraceW; // eax
  int v23; // eax
  int v24; // eax
  ULONG updated; // eax
  int v26; // eax
  int v27; // eax
  TraceSession *v28; // rcx
  int v29; // eax
  int v31; // [rsp+70h] [rbp-90h] BYREF
  int v32; // [rsp+78h] [rbp-88h] BYREF
  __int16 v33; // [rsp+80h] [rbp-80h] BYREF
  PEVENT_TRACE_PROPERTIES Properties; // [rsp+88h] [rbp-78h] BYREF
  struct ITraceDataCollector *v35; // [rsp+90h] [rbp-70h] BYREF
  TRACEHANDLE TraceHandle; // [rsp+98h] [rbp-68h] BYREF
  wchar_t *String1; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v38[64]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v39[64]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v40[64]; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int16 v41[64]; // [rsp+230h] [rbp+130h] BYREF
  unsigned __int16 v42[64]; // [rsp+2B0h] [rbp+1B0h] BYREF
  unsigned __int16 v43[64]; // [rsp+330h] [rbp+230h] BYREF
  unsigned __int16 v44[64]; // [rsp+3B0h] [rbp+2B0h] BYREF
  unsigned __int16 v45[64]; // [rsp+430h] [rbp+330h] BYREF
  unsigned __int16 v46[64]; // [rsp+4B0h] [rbp+3B0h] BYREF
  unsigned __int16 v47[64]; // [rsp+530h] [rbp+430h] BYREF
  unsigned __int16 v48[64]; // [rsp+5B0h] [rbp+4B0h] BYREF

  v2 = *(_QWORD *)this;
  TraceHandle = 0;
  Properties = 0;
  v35 = 0;
  v5 = *(__int64 (__fastcall **)(TraceSession *, struct ITraceDataCollector **))(v2 + 656);
  v6 = 0;
  String1 = 0;
  v33 = 0;
  v7 = v5(this, &v35);
  v8 = 1;
  v9 = v7;
  if ( v7 >= 0 )
  {
    inited = PlaiInitTraceProperties(&Properties);
    v9 = inited;
    if ( inited < 0 )
    {
      v32 = 0;
      v31 = inited;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_15;
      }
      PlaiWhoAmI(v39, 0x4000000000000800uLL);
      v14 = -1;
      do
        ++v14;
      while ( v39[v14] );
LABEL_14:
      EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, &v31, 4, byte_180147320, 1, &v32, 4);
LABEL_15:
      v6 = Properties;
      goto LABEL_89;
    }
    v15 = ((__int64 (__fastcall *)(struct ITraceDataCollector *, __int16 *))v35->lpVtbl->get_ProcessMode)(v35, &v33);
    v9 = v15;
    if ( v15 < 0 )
    {
      v32 = 0;
      v31 = v15;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_15;
      }
      PlaiWhoAmI(v40, 0x4000000000000800uLL);
      v16 = -1;
      do
        ++v16;
      while ( v40[v16] );
      goto LABEL_14;
    }
    v6 = Properties;
    v17 = -1;
    if ( v33 == -1
      && (Properties->LogFileMode |= 0x800u, v18 = PlaiSetPrivateTraceProperties(v35, v6), v9 = v18, v18 < 0) )
    {
      v32 = 0;
      v31 = v18;
      if ( !(_DWORD)xmmword_180169738
        || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
        || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
      {
        goto LABEL_89;
      }
      PlaiWhoAmI(v41, 0x4000000000000800uLL);
      do
        ++v17;
      while ( v41[v17] );
    }
    else
    {
      v19 = ((__int64 (__fastcall *)(struct ITraceDataCollector *, TRACEHANDLE *))v35->lpVtbl->get_SessionId)(
              v35,
              &TraceHandle);
      v9 = v19;
      if ( v19 >= 0 )
      {
        v21 = TraceSession::GetOrCreateLatestOutputLocation(v20, v35, &String1);
        v9 = v21;
        if ( v21 >= 0 )
        {
          TraceW = QueryTraceW(TraceHandle, a2, v6);
          if ( (int)PlaiHResultFromWin32(TraceW) >= 0 )
            v8 = _wcsicmp(String1, (const wchar_t *)((char *)v6 + v6->LogFileNameOffset)) != 0;
          if ( v6 )
          {
            PlaiFree(v6, 1);
            Properties = 0;
          }
          v23 = PlaiInitTraceProperties(&Properties);
          v9 = v23;
          if ( v23 < 0 )
          {
            v32 = 0;
            v31 = v23;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              v6 = Properties;
              goto LABEL_89;
            }
            PlaiWhoAmI(v44, 0x4000000000000800uLL);
            do
              ++v17;
            while ( v44[v17] );
            goto LABEL_14;
          }
          v6 = Properties;
          v24 = (*(__int64 (__fastcall **)(TraceSession *, PEVENT_TRACE_PROPERTIES, wchar_t *))(*(_QWORD *)this + 632LL))(
                  this,
                  Properties,
                  String1);
          v9 = v24;
          if ( v24 >= 0 )
          {
            if ( !v8 )
              *(_WORD *)((char *)&v6->Wnode.BufferSize + v6->LogFileNameOffset) = 0;
            updated = UpdateTraceW(TraceHandle, a2, v6);
            v26 = TraceSession::ConvertError(updated);
            v9 = v26;
            if ( v26 >= 0 )
            {
              v27 = (*(__int64 (__fastcall **)(TraceSession *, __int64, TRACEHANDLE))(*(_QWORD *)this + 672LL))(
                      this,
                      1,
                      TraceHandle);
              v9 = v27;
              if ( v27 >= 0 )
              {
                v29 = TraceSession::DisableProviders(v28, TraceHandle, v35);
                v9 = v29;
                if ( v29 >= 0 )
                  goto LABEL_89;
                v32 = 0;
                v31 = v29;
                if ( !(_DWORD)xmmword_180169738
                  || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                  || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                {
                  goto LABEL_89;
                }
                PlaiWhoAmI(v48, 0x4000000000000800uLL);
                do
                  ++v17;
                while ( v48[v17] );
              }
              else
              {
                v32 = 0;
                v31 = v27;
                if ( !(_DWORD)xmmword_180169738
                  || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                  || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
                {
                  goto LABEL_89;
                }
                PlaiWhoAmI(v47, 0x4000000000000800uLL);
                do
                  ++v17;
                while ( v47[v17] );
              }
            }
            else
            {
              v32 = 0;
              v31 = v26;
              if ( !(_DWORD)xmmword_180169738
                || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
                || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
              {
                goto LABEL_89;
              }
              PlaiWhoAmI(v46, 0x4000000000000800uLL);
              do
                ++v17;
              while ( v46[v17] );
            }
          }
          else
          {
            v32 = 0;
            v31 = v24;
            if ( !(_DWORD)xmmword_180169738
              || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
              || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
            {
              goto LABEL_89;
            }
            PlaiWhoAmI(v45, 0x4000000000000800uLL);
            do
              ++v17;
            while ( v45[v17] );
          }
        }
        else
        {
          v32 = 0;
          v31 = v21;
          if ( !(_DWORD)xmmword_180169738
            || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
            || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
          {
            goto LABEL_89;
          }
          PlaiWhoAmI(v43, 0x4000000000000800uLL);
          do
            ++v17;
          while ( v43[v17] );
        }
      }
      else
      {
        v32 = 0;
        v31 = v19;
        if ( !(_DWORD)xmmword_180169738
          || (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) == 0
          || qword_180169748 != (qword_180169748 & 0x4000000000000800LL) )
        {
          goto LABEL_89;
        }
        PlaiWhoAmI(v42, 0x4000000000000800uLL);
        do
          ++v17;
        while ( v42[v17] );
      }
    }
    v11 = &v31;
    v12 = &v32;
LABEL_88:
    EventingWriteEvent(&g_Eventing, &PLA_EVENT_ERROR, 5, v11, 4, byte_180147320, 1, v12, 4);
    goto LABEL_89;
  }
  v31 = 0;
  v32 = v7;
  if ( (_DWORD)xmmword_180169738
    && (*(&xmmword_180169738 + 1) & 0x4000000000000800LL) != 0
    && qword_180169748 == (qword_180169748 & 0x4000000000000800LL) )
  {
    PlaiWhoAmI(v38, 0x4000000000000800uLL);
    v10 = -1;
    do
      ++v10;
    while ( v38[v10] );
    v11 = &v32;
    v12 = &v31;
    goto LABEL_88;
  }
LABEL_89:
  PlaiFreeString(String1);
  String1 = 0;
  if ( v6 )
    PlaiFree(v6, 1);
  if ( v35 )
    ((void (__fastcall *)(struct ITraceDataCollector *))v35->lpVtbl->Release)(v35);
  return v9;
}

```

## disassembly

```asm
0x180096100  mov     [rsp-8+arg_10], rbx
0x180096105  push    rbp
0x180096106  push    rsi
0x180096107  push    rdi
0x180096108  push    r12
0x18009610a  push    r13
0x18009610c  push    r14
0x18009610e  push    r15
0x180096110  lea     rbp, [rsp-540h]
0x180096118  sub     rsp, 640h
0x18009611f  mov     rax, cs:__security_cookie
0x180096126  xor     rax, rsp
0x180096129  mov     [rbp+570h+var_40], rax
0x180096130  mov     rax, [rcx]
0x180096133  xor     r13d, r13d
0x180096136  mov     r12, rdx
0x180096139  mov     [rbp+570h+TraceHandle], r13
0x18009613d  lea     rdx, [rbp+570h+var_5E0]
0x180096141  mov     [rbp+570h+Properties], r13
0x180096145  mov     r15, rcx
0x180096148  mov     [rbp+570h+var_5E0], r13
0x18009614c  mov     rax, [rax+290h]
0x180096153  mov     esi, r13d
0x180096156  mov     [rbp+570h+String1], r13
0x18009615a  mov     [rbp+570h+var_5F0], r13w
0x18009615f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096164  lea     r14d, [r13+1]
0x180096168  mov     edi, eax
0x18009616a  test    eax, eax
0x18009616c  jns     short loc_1800961EC
0x18009616e  cmp     dword ptr cs:xmmword_180169738, r13d
0x180096175  mov     [rsp+670h+var_600], r13d
0x18009617a  mov     [rsp+670h+var_5F8], eax
0x18009617e  jz      loc_180096863
0x180096184  mov     rdx, 4000000000000800h; unsigned __int64
0x18009618e  test    qword ptr cs:xmmword_180169738+8, rdx
0x180096195  jz      loc_180096863
0x18009619b  mov     rax, cs:qword_180169748
0x1800961a2  and     rax, rdx
0x1800961a5  cmp     cs:qword_180169748, rax
0x1800961ac  jnz     loc_180096863
0x1800961b2  lea     rcx, [rbp+570h+var_5C0]; unsigned __int16 *
0x1800961b6  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800961bb  lea     rax, [rbp+570h+var_5C0]
0x1800961bf  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800961c3  inc     rbx
0x1800961c6  cmp     [rax+rbx*2], r13w
0x1800961cb  jnz     short loc_1800961C3
0x1800961cd  lea     ecx, [rbx+rbx]
0x1800961d0  add     rcx, 2
0x1800961d4  lea     rax, [rbp+570h+var_5C0]
0x1800961d8  mov     [rsp+670h+var_610], rcx
0x1800961dd  lea     r9, [rsp+670h+var_5F8]
0x1800961e2  lea     rcx, [rsp+670h+var_600]
0x1800961e7  jmp     loc_18009680D
0x1800961ec  lea     rcx, [rbp+570h+Properties]; struct _EVENT_TRACE_PROPERTIES **
0x1800961f0  call    ?PlaiInitTraceProperties@@YAJPEAPEAU_EVENT_TRACE_PROPERTIES@@@Z; PlaiInitTraceProperties(_EVENT_TRACE_PROPERTIES * *)
0x1800961f5  mov     edi, eax
0x1800961f7  test    eax, eax
0x1800961f9  jns     loc_1800962D7
0x1800961ff  cmp     dword ptr cs:xmmword_180169738, r13d
0x180096206  mov     [rsp+670h+var_5F8], r13d
0x18009620b  mov     [rsp+670h+var_600], eax
0x18009620f  jz      loc_1800962CE
0x180096215  mov     rdx, 4000000000000800h; unsigned __int64
0x18009621f  test    qword ptr cs:xmmword_180169738+8, rdx
0x180096226  jz      loc_1800962CE
0x18009622c  mov     rax, cs:qword_180169748
0x180096233  and     rax, rdx
0x180096236  cmp     cs:qword_180169748, rax
0x18009623d  jnz     loc_1800962CE
0x180096243  lea     rcx, [rbp+570h+var_540]; unsigned __int16 *
0x180096247  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009624c  lea     rax, [rbp+570h+var_540]
0x180096250  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180096254  inc     rbx
0x180096257  cmp     [rax+rbx*2], r13w
0x18009625c  jnz     short loc_180096254
0x18009625e  lea     rax, [rbp+570h+var_540]
0x180096262  lea     ecx, [rbx+rbx]
0x180096265  add     rcx, 2
0x180096269  lea     r9, [rsp+670h+var_600]
0x18009626e  mov     [rsp+670h+var_610], rcx
0x180096273  lea     rdx, PLA_EVENT_ERROR
0x18009627a  mov     [rsp+670h+var_618], rax
0x18009627f  lea     rcx, [rsp+670h+var_5F8]
0x180096284  mov     [rsp+670h+var_620], 15h
0x18009628d  lea     rax, aTracesessionUp; "TraceSession::Update"
0x180096294  mov     [rsp+670h+var_628], rax
0x180096299  mov     eax, 4
0x18009629e  mov     [rsp+670h+var_630], rax
0x1800962a3  mov     [rsp+670h+var_638], rcx
0x1800962a8  lea     rcx, byte_180147320
0x1800962af  mov     [rsp+670h+var_640], r14
0x1800962b4  mov     [rsp+670h+var_648], rcx
0x1800962b9  lea     r8d, [rax+1]
0x1800962bd  lea     rcx, ?g_Eventing@@3UEVENTING_OBJECT@@A; EVENTING_OBJECT g_Eventing
0x1800962c4  mov     [rsp+670h+var_650], rax
0x1800962c9  call    EventingWriteEvent
0x1800962ce  mov     rsi, [rbp+570h+Properties]
0x1800962d2  jmp     loc_180096863
0x1800962d7  mov     rcx, [rbp+570h+var_5E0]
0x1800962db  lea     rdx, [rbp+570h+var_5F0]
0x1800962df  mov     rax, [rcx]
0x1800962e2  mov     rax, [rax+1D8h]
0x1800962e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800962ee  mov     edi, eax
0x1800962f0  test    eax, eax
0x1800962f2  jns     short loc_180096359
0x1800962f4  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800962fb  mov     [rsp+670h+var_5F8], r13d
0x180096300  mov     [rsp+670h+var_600], eax
0x180096304  jz      short loc_1800962CE
0x180096306  mov     rdx, 4000000000000800h; unsigned __int64
0x180096310  test    qword ptr cs:xmmword_180169738+8, rdx
0x180096317  jz      short loc_1800962CE
0x180096319  mov     rax, cs:qword_180169748
0x180096320  and     rax, rdx
0x180096323  cmp     cs:qword_180169748, rax
0x18009632a  jnz     short loc_1800962CE
0x18009632c  lea     rcx, [rbp+570h+var_4C0]; unsigned __int16 *
0x180096333  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180096338  lea     rax, [rbp+570h+var_4C0]
0x18009633f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180096343  inc     rbx
0x180096346  cmp     [rax+rbx*2], r13w
0x18009634b  jnz     short loc_180096343
0x18009634d  lea     rax, [rbp+570h+var_4C0]
0x180096354  jmp     loc_180096262
0x180096359  mov     rsi, [rbp+570h+Properties]
0x18009635d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180096361  cmp     [rbp+570h+var_5F0], bx
0x180096365  jnz     loc_1800963EF
0x18009636b  bts     dword ptr [rsi+40h], 0Bh
0x180096370  mov     rdx, rsi; struct _EVENT_TRACE_PROPERTIES *
0x180096373  mov     rcx, [rbp+570h+var_5E0]; struct ITraceDataCollector *
0x180096377  call    ?PlaiSetPrivateTraceProperties@@YAJPEAUITraceDataCollector@@PEAU_EVENT_TRACE_PROPERTIES@@@Z; PlaiSetPrivateTraceProperties(ITraceDataCollector *,_EVENT_TRACE_PROPERTIES *)
0x18009637c  mov     edi, eax
0x18009637e  test    eax, eax
0x180096380  jns     short loc_1800963EF
0x180096382  cmp     dword ptr cs:xmmword_180169738, r13d
0x180096389  mov     [rsp+670h+var_5F8], r13d
0x18009638e  mov     [rsp+670h+var_600], eax
0x180096392  jz      loc_180096863
0x180096398  mov     rdx, 4000000000000800h; unsigned __int64
0x1800963a2  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800963a9  jz      loc_180096863
0x1800963af  mov     rax, cs:qword_180169748
0x1800963b6  and     rax, rdx
0x1800963b9  cmp     cs:qword_180169748, rax
0x1800963c0  jnz     loc_180096863
0x1800963c6  lea     rcx, [rbp+570h+var_440]; unsigned __int16 *
0x1800963cd  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800963d2  lea     rax, [rbp+570h+var_440]
0x1800963d9  inc     rbx
0x1800963dc  cmp     [rax+rbx*2], r13w
0x1800963e1  jnz     short loc_1800963D9
0x1800963e3  lea     rax, [rbp+570h+var_440]
0x1800963ea  jmp     loc_1800967F7
0x1800963ef  mov     rcx, [rbp+570h+var_5E0]
0x1800963f3  lea     rdx, [rbp+570h+TraceHandle]
0x1800963f7  mov     rax, [rcx]
0x1800963fa  mov     rax, [rax+1F8h]
0x180096401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096406  mov     edi, eax
0x180096408  test    eax, eax
0x18009640a  jns     short loc_180096479
0x18009640c  cmp     dword ptr cs:xmmword_180169738, r13d
0x180096413  mov     [rsp+670h+var_5F8], r13d
0x180096418  mov     [rsp+670h+var_600], eax
0x18009641c  jz      loc_180096863
0x180096422  mov     rdx, 4000000000000800h; unsigned __int64
0x18009642c  test    qword ptr cs:xmmword_180169738+8, rdx
0x180096433  jz      loc_180096863
0x180096439  mov     rax, cs:qword_180169748
0x180096440  and     rax, rdx
0x180096443  cmp     cs:qword_180169748, rax
0x18009644a  jnz     loc_180096863
0x180096450  lea     rcx, [rbp+570h+var_3C0]; unsigned __int16 *
0x180096457  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009645c  lea     rax, [rbp+570h+var_3C0]
0x180096463  inc     rbx
0x180096466  cmp     [rax+rbx*2], r13w
0x18009646b  jnz     short loc_180096463
0x18009646d  lea     rax, [rbp+570h+var_3C0]
0x180096474  jmp     loc_1800967F7
0x180096479  mov     rdx, [rbp+570h+var_5E0]; struct ITraceDataCollector *
0x18009647d  lea     r8, [rbp+570h+String1]; unsigned __int16 **
0x180096481  call    ?GetOrCreateLatestOutputLocation@TraceSession@@AEAAJPEAUITraceDataCollector@@PEAPEAG@Z; TraceSession::GetOrCreateLatestOutputLocation(ITraceDataCollector *,ushort * *)
0x180096486  mov     edi, eax
0x180096488  test    eax, eax
0x18009648a  jns     short loc_1800964F9
0x18009648c  cmp     dword ptr cs:xmmword_180169738, r13d
0x180096493  mov     [rsp+670h+var_5F8], r13d
0x180096498  mov     [rsp+670h+var_600], eax
0x18009649c  jz      loc_180096863
0x1800964a2  mov     rdx, 4000000000000800h; unsigned __int64
0x1800964ac  test    qword ptr cs:xmmword_180169738+8, rdx
0x1800964b3  jz      loc_180096863
0x1800964b9  mov     rax, cs:qword_180169748
0x1800964c0  and     rax, rdx
0x1800964c3  cmp     cs:qword_180169748, rax
0x1800964ca  jnz     loc_180096863
0x1800964d0  lea     rcx, [rbp+570h+var_340]; unsigned __int16 *
0x1800964d7  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x1800964dc  lea     rax, [rbp+570h+var_340]
0x1800964e3  inc     rbx
0x1800964e6  cmp     [rax+rbx*2], r13w
0x1800964eb  jnz     short loc_1800964E3
0x1800964ed  lea     rax, [rbp+570h+var_340]
0x1800964f4  jmp     loc_1800967F7
0x1800964f9  mov     rcx, [rbp+570h+TraceHandle]; TraceHandle
0x1800964fd  mov     r8, rsi; Properties
0x180096500  mov     rdx, r12; InstanceName
0x180096503  call    cs:__imp_QueryTraceW
0x180096509  mov     ecx, eax; unsigned int
0x18009650b  call    ?PlaiHResultFromWin32@@YAJK@Z; PlaiHResultFromWin32(ulong)
0x180096510  test    eax, eax
0x180096512  js      short loc_18009652D
0x180096514  mov     edx, [rsi+70h]
0x180096517  mov     rcx, [rbp+570h+String1]; String1
0x18009651b  add     rdx, rsi; String2
0x18009651e  call    cs:__imp__wcsicmp
0x180096524  test    eax, eax
0x180096526  mov     r14d, r13d
0x180096529  setnz   r14b
0x18009652d  test    rsi, rsi
0x180096530  jz      short loc_180096543
0x180096532  mov     edx, 1; int
0x180096537  mov     rcx, rsi; lpMem
0x18009653a  call    ?PlaiFree@@YAXPEAXH@Z; PlaiFree(void *,int)
0x18009653f  mov     [rbp+570h+Properties], r13
0x180096543  lea     rcx, [rbp+570h+Properties]; struct _EVENT_TRACE_PROPERTIES **
0x180096547  call    ?PlaiInitTraceProperties@@YAJPEAPEAU_EVENT_TRACE_PROPERTIES@@@Z; PlaiInitTraceProperties(_EVENT_TRACE_PROPERTIES * *)
0x18009654c  mov     edi, eax
0x18009654e  test    eax, eax
0x180096550  jns     short loc_1800965C8
0x180096552  cmp     dword ptr cs:xmmword_180169738, r13d
0x180096559  mov     [rsp+670h+var_5F8], r13d
0x18009655e  mov     [rsp+670h+var_600], eax
0x180096562  jz      short loc_1800965B9
0x180096564  mov     rdx, 4000000000000800h; unsigned __int64
0x18009656e  test    qword ptr cs:xmmword_180169738+8, rdx
0x180096575  jz      short loc_1800965B9
0x180096577  mov     rax, cs:qword_180169748
0x18009657e  and     rax, rdx
0x180096581  cmp     cs:qword_180169748, rax
0x180096588  jnz     short loc_1800965B9
0x18009658a  lea     rcx, [rbp+570h+var_2C0]; unsigned __int16 *
0x180096591  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x180096596  lea     rax, [rbp+570h+var_2C0]
0x18009659d  inc     rbx
0x1800965a0  cmp     [rax+rbx*2], r13w
0x1800965a5  jnz     short loc_18009659D
0x1800965a7  lea     rax, [rbp+570h+var_2C0]
0x1800965ae  mov     r14d, 1
0x1800965b4  jmp     loc_180096262
0x1800965b9  mov     rsi, [rbp+570h+Properties]
0x1800965bd  mov     r14d, 1
0x1800965c3  jmp     loc_180096863
0x1800965c8  mov     rax, [r15]
0x1800965cb  mov     rcx, r15
0x1800965ce  mov     rsi, [rbp+570h+Properties]
0x1800965d2  mov     r8, [rbp+570h+String1]
0x1800965d6  mov     rdx, rsi
0x1800965d9  mov     rax, [rax+278h]
0x1800965e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800965e5  mov     edi, eax
0x1800965e7  test    eax, eax
0x1800965e9  jns     short loc_180096652
0x1800965eb  cmp     dword ptr cs:xmmword_180169738, r13d
0x1800965f2  mov     [rsp+670h+var_5F8], r13d
0x1800965f7  mov     [rsp+670h+var_600], eax
0x1800965fb  jz      short loc_1800965BD
0x1800965fd  mov     rdx, 4000000000000800h; unsigned __int64
0x180096607  test    qword ptr cs:xmmword_180169738+8, rdx
0x18009660e  jz      short loc_1800965BD
0x180096610  mov     rax, cs:qword_180169748
0x180096617  and     rax, rdx
0x18009661a  cmp     cs:qword_180169748, rax
0x180096621  jnz     short loc_1800965BD
0x180096623  lea     rcx, [rbp+570h+var_240]; unsigned __int16 *
0x18009662a  call    ?PlaiWhoAmI@@YAJPEAG_K@Z; PlaiWhoAmI(ushort *,unsigned __int64)
0x18009662f  lea     rax, [rbp+570h+var_240]
0x180096636  inc     rbx
0x180096639  cmp     [rax+rbx*2], r13w
0x18009663e  jnz     short loc_180096636
0x180096640  lea     rax, [rbp+570h+var_240]
0x180096647  mov     r14d, 1
0x18009664d  jmp     loc_1800967F7
0x180096652  test    r14d, r14d
0x180096655  jnz     short loc_18009665F
0x180096657  mov     ecx, [rsi+70h]
0x18009665a  mov     [rcx+rsi], r13w
0x18009665f  mov     rcx, [rbp+570h+TraceHandle]; TraceHandle
0x180096663  mov     r8, rsi; Properties
0x180096666  mov     rdx, r12; InstanceName
0x180096669  call    cs:__imp_UpdateTraceW
0x18009666f  mov     ecx, eax; unsigned int
0x180096671  call    ?ConvertError@TraceSession@@SAJK@Z; TraceSession::ConvertError(ulong)
  ... truncated ...
```
