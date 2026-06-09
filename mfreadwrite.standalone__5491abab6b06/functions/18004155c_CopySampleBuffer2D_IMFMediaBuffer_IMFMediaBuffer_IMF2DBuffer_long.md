# CopySampleBuffer2D(IMFMediaBuffer *,IMFMediaBuffer *,IMF2DBuffer *,long)

- ea: `0x18004155c`
- end: `0x180041af5`
- name: `?CopySampleBuffer2D@@YAJPEAUIMFMediaBuffer@@0PEAUIMF2DBuffer@@J@Z`
- size: `1433`
- prototype: `__int64 __fastcall(struct IMFMediaBuffer *, struct IMFMediaBuffer *, struct IMF2DBuffer *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18003fa50`

## callees

- `0x180006bd4`
- `0x18000e590`
- `0x180012640`
- `0x180014a14`
- `0x1800252a0`
- `0x18004155c`
- `0x1800f3010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800416ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041810`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041961`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041aa7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800416ec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041810`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041961`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180041aa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004167f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041696`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800417aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800417c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800418fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041912`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041a41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041a58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004167f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041696`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800417aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800417c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800418fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041912`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041a41`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041a58`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004168b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800417b6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180041907`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180041a4d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18004168b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800417b6`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180041907`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180041a4d`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800416ac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041749`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800417d7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041871`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041928`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800419c2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041a6e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800416ac`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041749`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800417d7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041871`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041928`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1800419c2`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180041a6e`

## string_xrefs

- `0x180041594`: `CopySampleBuffer2D`
- `0x180041701`: `CopySampleBuffer2D`
- `0x180041826`: `CopySampleBuffer2D`
- `0x180041977`: `CopySampleBuffer2D`
- `0x180041abd`: `CopySampleBuffer2D`

## pseudocode

```c
__int64 __fastcall CopySampleBuffer2D(struct IMFMediaBuffer *a1, struct IMFMediaBuffer *a2, struct IMF2DBuffer *a3)
{
  int v6; // ebx
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  CallStackTracing *v14; // rdi
  __int64 v15; // rdx
  CallStackContext *v16; // rsi
  DWORD v17; // r14d
  CallStackContext *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  CallStackTracing *v21; // rdi
  CallStackTracing *v22; // rax
  __int64 v23; // rax
  CallStackTracing *v24; // rsi
  CallStackTracing *v25; // rax
  __int64 v26; // rdx
  CallStackContext *v27; // r14
  DWORD LastError; // r12d
  CallStackContext *Value; // rax
  __int64 v30; // rdx
  CallStackTracing *v31; // rcx
  CallStackTracing *v32; // rax
  __int64 v33; // rax
  CallStackTracing *v34; // rsi
  CallStackTracing *v35; // rax
  CallStackContext *v36; // r14
  DWORD v37; // r12d
  CallStackContext *v38; // rax
  __int64 v39; // rdx
  CallStackTracing *v40; // rcx
  CallStackTracing *v41; // rax
  __int64 v42; // rax
  CallStackTracing *v43; // rsi
  CallStackTracing *v44; // rax
  CallStackContext *v45; // r14
  DWORD v46; // r15d
  CallStackContext *v47; // rax
  __int64 v48; // rdx
  CallStackTracing *v49; // rcx
  CallStackTracing *v50; // rax
  __int64 v51; // rax
  int v52; // [rsp+30h] [rbp-38h] BYREF
  __int64 v53[6]; // [rsp+38h] [rbp-30h] BYREF
  unsigned int v54; // [rsp+70h] [rbp+8h] BYREF
  char v55; // [rsp+88h] [rbp+20h] BYREF

  v53[0] = 0;
  v52 = 0;
  v54 = 0;
  CallStackScopeTrace::CallStackScopeTrace((CallStackScopeTrace *)&v55, "CopySampleBuffer2D", 238);
  v6 = ((__int64 (__fastcall *)(struct IMFMediaBuffer *, __int64 *, int *, unsigned int *))a1->lpVtbl->Lock)(
         a1,
         v53,
         &v52,
         &v54);
  if ( v6 >= 0 )
  {
    v6 = ((__int64 (__fastcall *)(struct IMF2DBuffer *, __int64, _QWORD))a3->lpVtbl->ContiguousCopyFrom)(
           a3,
           v53[0],
           v54);
    if ( v6 < 0 )
    {
      v24 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v8, v7);
        CallStackTracing::s_wpInstance = v25;
        if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
        {
          v24 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v24 = (CallStackTracing *)&qword_18010C230;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
        }
      }
      if ( *((_BYTE *)v24 + 8) )
      {
        v27 = (CallStackTracing *)((char *)v24 + 208);
        LastError = GetLastError();
        Value = (CallStackContext *)TlsGetValue(*((_DWORD *)v24 + 3));
        if ( Value )
        {
          v27 = Value;
        }
        else if ( !GetLastError() )
        {
          v31 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v32 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v30);
            CallStackTracing::s_wpInstance = v32;
            if ( v32 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v32 + 8LL))(v32, 2032) )
            {
              v31 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v31 = (CallStackTracing *)&qword_18010C230;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
            }
          }
          v33 = (**(__int64 (__fastcall ***)(CallStackTracing *))v31)(v31);
          if ( v33 )
            v27 = (CallStackContext *)v33;
        }
        SetLastError(LastError);
        if ( *((_DWORD *)v27 + 499) != v6 )
          CallStackContext::TraceFailure(v27, "CopySampleBuffer2D", 253, v6);
      }
      if ( !g_wppLevels )
        goto LABEL_53;
      v26 = 34;
    }
    else
    {
      v6 = ((__int64 (__fastcall *)(struct IMFMediaBuffer *))a1->lpVtbl->Unlock)(a1);
      if ( v6 >= 0 )
      {
        v6 = ((__int64 (__fastcall *)(struct IMFMediaBuffer *, _QWORD))a2->lpVtbl->SetCurrentLength)(a2, v54);
        if ( v6 < 0 )
        {
          v43 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v12, v11);
            CallStackTracing::s_wpInstance = v44;
            if ( v44 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
            {
              v43 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v43 = (CallStackTracing *)&qword_18010C230;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
            }
          }
          if ( *((_BYTE *)v43 + 8) )
          {
            v45 = (CallStackTracing *)((char *)v43 + 208);
            v46 = GetLastError();
            v47 = (CallStackContext *)TlsGetValue(*((_DWORD *)v43 + 3));
            if ( v47 )
            {
              v45 = v47;
            }
            else if ( !GetLastError() )
            {
              v49 = CallStackTracing::s_wpInstance;
              if ( !CallStackTracing::s_wpInstance )
              {
                v50 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v48);
                CallStackTracing::s_wpInstance = v50;
                if ( v50
                  && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v50 + 8LL))(v50, 2032) )
                {
                  v49 = CallStackTracing::s_wpInstance;
                }
                else
                {
                  v49 = (CallStackTracing *)&qword_18010C230;
                  CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
                }
              }
              v51 = (**(__int64 (__fastcall ***)(CallStackTracing *))v49)(v49);
              if ( v51 )
                v45 = (CallStackContext *)v51;
            }
            SetLastError(v46);
            if ( *((_DWORD *)v45 + 499) != v6 )
              CallStackContext::TraceFailure(v45, "CopySampleBuffer2D", 263, v6);
          }
          if ( g_wppLevels )
          {
            v15 = 36;
            goto LABEL_75;
          }
        }
        goto LABEL_5;
      }
      v34 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v35 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v10, v9);
        CallStackTracing::s_wpInstance = v35;
        if ( v35 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v35 + 8LL))(v35, 2032) )
        {
          v34 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v34 = (CallStackTracing *)&qword_18010C230;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
        }
      }
      if ( *((_BYTE *)v34 + 8) )
      {
        v36 = (CallStackTracing *)((char *)v34 + 208);
        v37 = GetLastError();
        v38 = (CallStackContext *)TlsGetValue(*((_DWORD *)v34 + 3));
        if ( v38 )
        {
          v36 = v38;
        }
        else if ( !GetLastError() )
        {
          v40 = CallStackTracing::s_wpInstance;
          if ( !CallStackTracing::s_wpInstance )
          {
            v41 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v39);
            CallStackTracing::s_wpInstance = v41;
            if ( v41 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v41 + 8LL))(v41, 2032) )
            {
              v40 = CallStackTracing::s_wpInstance;
            }
            else
            {
              v40 = (CallStackTracing *)&qword_18010C230;
              CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
            }
          }
          v42 = (**(__int64 (__fastcall ***)(CallStackTracing *))v40)(v40);
          if ( v42 )
            v36 = (CallStackContext *)v42;
        }
        SetLastError(v37);
        if ( *((_DWORD *)v36 + 499) != v6 )
          CallStackContext::TraceFailure(v36, "CopySampleBuffer2D", 260, v6);
      }
      if ( !g_wppLevels )
      {
LABEL_53:
        ((void (__fastcall *)(struct IMFMediaBuffer *))a1->lpVtbl->Unlock)(a1);
        goto LABEL_5;
      }
      v26 = 35;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v26, WPP_78ad5779643337f2c47fabc78d39cf1a_Traceguids, 0, v6);
    goto LABEL_53;
  }
  v14 = CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    CallStackTracing::InitInstance();
    v14 = CallStackTracing::s_wpInstance;
  }
  if ( *((_BYTE *)v14 + 8) )
  {
    v16 = (CallStackTracing *)((char *)v14 + 208);
    v17 = GetLastError();
    v18 = (CallStackContext *)TlsGetValue(*((_DWORD *)v14 + 3));
    if ( v18 )
    {
      v16 = v18;
    }
    else if ( !GetLastError() )
    {
      v21 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v22 = (CallStackTracing *)MFGetCallStackTracingWeakReference(v20, v19);
        CallStackTracing::s_wpInstance = v22;
        if ( v22 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v22 + 8LL))(v22, 2032) )
        {
          v21 = CallStackTracing::s_wpInstance;
        }
        else
        {
          v21 = (CallStackTracing *)&qword_18010C230;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_18010C230;
        }
      }
      v23 = (**(__int64 (__fastcall ***)(CallStackTracing *))v21)(v21);
      if ( v23 )
        v16 = (CallStackContext *)v23;
    }
    SetLastError(v17);
    if ( *((_DWORD *)v16 + 499) != v6 )
      CallStackContext::TraceFailure(v16, "CopySampleBuffer2D", 238, v6);
  }
  if ( g_wppLevels )
  {
    v15 = 32;
LABEL_75:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, WPP_78ad5779643337f2c47fabc78d39cf1a_Traceguids, 0, v6);
  }
LABEL_5:
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v55);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18004155c  mov     rax, rsp
0x18004155f  mov     [rax+10h], rbx
0x180041563  push    rsi
0x180041564  push    rdi
0x180041565  push    r12
0x180041567  push    r14
0x180041569  push    r15
0x18004156b  sub     rsp, 40h
0x18004156f  mov     rsi, r8
0x180041572  mov     qword ptr [rax-30h], 0
0x18004157a  mov     rdi, rdx
0x18004157d  mov     dword ptr [rax-38h], 0
0x180041584  mov     r15, rcx
0x180041587  mov     dword ptr [rax+8], 0
0x18004158e  mov     r12d, 0EEh
0x180041594  lea     rdx, aCopysamplebuff; "CopySampleBuffer2D"
0x18004159b  mov     r8d, r12d; int
0x18004159e  lea     rcx, [rax+20h]; this
0x1800415a2  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x1800415a7  mov     rax, [r15]
0x1800415aa  lea     r9, [rsp+68h+arg_0]
0x1800415af  lea     r8, [rsp+68h+var_38]
0x1800415b4  mov     rcx, r15
0x1800415b7  lea     rdx, [rsp+68h+var_30]
0x1800415bc  mov     rax, [rax+18h]
0x1800415c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800415c5  mov     ebx, eax
0x1800415c7  test    eax, eax
0x1800415c9  js      short loc_180041645
0x1800415cb  mov     rax, [rsi]
0x1800415ce  mov     rcx, rsi
0x1800415d1  mov     r8d, [rsp+68h+arg_0]
0x1800415d6  mov     rdx, [rsp+68h+var_30]
0x1800415db  mov     rax, [rax+48h]
0x1800415df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800415e4  mov     ebx, eax
0x1800415e6  test    eax, eax
0x1800415e8  js      loc_180041736
0x1800415ee  mov     rax, [r15]
0x1800415f1  mov     rcx, r15
0x1800415f4  mov     rax, [rax+20h]
0x1800415f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800415fd  mov     ebx, eax
0x1800415ff  test    eax, eax
0x180041601  js      loc_18004185E
0x180041607  mov     rax, [rdi]
0x18004160a  mov     rcx, rdi
0x18004160d  mov     edx, [rsp+68h+arg_0]
0x180041611  mov     rax, [rax+30h]
0x180041615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004161a  mov     ebx, eax
0x18004161c  test    eax, eax
0x18004161e  js      loc_1800419AF
0x180041624  lea     rcx, [rsp+68h+arg_18]; this
0x18004162c  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180041631  mov     eax, ebx
0x180041633  mov     rbx, [rsp+68h+arg_8]
0x180041638  add     rsp, 40h
0x18004163c  pop     r15
0x18004163e  pop     r14
0x180041640  pop     r12
0x180041642  pop     rdi
0x180041643  pop     rsi
0x180041644  retn
0x180041645  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004164c  test    rdi, rdi
0x18004164f  jz      short loc_18004166A
0x180041651  cmp     byte ptr [rdi+8], 0
0x180041655  jnz     short loc_180041678
0x180041657  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004165e  jb      short loc_180041624
0x180041660  mov     edx, 20h ; ' '
0x180041665  jmp     loc_180041A0B
0x18004166a  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x18004166f  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180041676  jmp     short loc_180041651
0x180041678  lea     rsi, [rdi+0D0h]
0x18004167f  call    cs:__imp_GetLastError
0x180041685  mov     ecx, [rdi+0Ch]; dwTlsIndex
0x180041688  mov     r14d, eax
0x18004168b  call    cs:__imp_TlsGetValue
0x180041691  test    rax, rax
0x180041694  jnz     short loc_1800416E6
0x180041696  call    cs:__imp_GetLastError
0x18004169c  test    eax, eax
0x18004169e  jnz     short loc_1800416E9
0x1800416a0  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800416a7  test    rdi, rdi
0x1800416aa  jnz     short loc_1800416CF
0x1800416ac  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800416b2  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800416b9  mov     rcx, rax
0x1800416bc  test    rax, rax
0x1800416bf  jnz     short loc_180041718
0x1800416c1  lea     rdi, qword_18010C230
0x1800416c8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800416cf  mov     rax, [rdi]
0x1800416d2  mov     rcx, rdi
0x1800416d5  mov     rax, [rax]
0x1800416d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800416dd  test    rax, rax
0x1800416e0  cmovnz  rsi, rax
0x1800416e4  jmp     short loc_1800416E9
0x1800416e6  mov     rsi, rax
0x1800416e9  mov     ecx, r14d; dwErrCode
0x1800416ec  call    cs:__imp_SetLastError
0x1800416f2  cmp     [rsi+7CCh], ebx
0x1800416f8  jz      loc_180041657
0x1800416fe  mov     r9d, ebx; int
0x180041701  lea     rdx, aCopysamplebuff; "CopySampleBuffer2D"
0x180041708  mov     r8d, r12d; int
0x18004170b  mov     rcx, rsi; this
0x18004170e  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180041713  jmp     loc_180041657
0x180041718  mov     rax, [rax]
0x18004171b  mov     edx, 7F0h
0x180041720  mov     rax, [rax+8]
0x180041724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041729  test    eax, eax
0x18004172b  jz      short loc_1800416C1
0x18004172d  mov     rdi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180041734  jmp     short loc_1800416CF
0x180041736  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004173d  lea     rdi, qword_18010C230
0x180041744  test    rsi, rsi
0x180041747  jnz     short loc_18004177A
0x180041749  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004174f  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180041756  mov     rcx, rax
0x180041759  test    rax, rax
0x18004175c  jz      short loc_180041797
0x18004175e  mov     rax, [rax]
0x180041761  mov     edx, 7F0h
0x180041766  mov     rax, [rax+8]
0x18004176a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004176f  test    eax, eax
0x180041771  jz      short loc_180041797
0x180041773  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004177a  cmp     byte ptr [rsi+8], 0
0x18004177e  jnz     short loc_1800417A3
0x180041780  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180041787  jb      loc_1800418D4
0x18004178d  mov     edx, 22h ; '"'
0x180041792  jmp     loc_1800418B6
0x180041797  mov     rsi, rdi
0x18004179a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800417a1  jmp     short loc_18004177A
0x1800417a3  lea     r14, [rsi+0D0h]
0x1800417aa  call    cs:__imp_GetLastError
0x1800417b0  mov     ecx, [rsi+0Ch]; dwTlsIndex
0x1800417b3  mov     r12d, eax
0x1800417b6  call    cs:__imp_TlsGetValue
0x1800417bc  test    rax, rax
0x1800417bf  jnz     short loc_18004180A
0x1800417c1  call    cs:__imp_GetLastError
0x1800417c7  test    eax, eax
0x1800417c9  jnz     short loc_18004180D
0x1800417cb  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800417d2  test    rcx, rcx
0x1800417d5  jnz     short loc_1800417F6
0x1800417d7  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800417dd  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800417e4  mov     rcx, rax
0x1800417e7  test    rax, rax
0x1800417ea  jnz     short loc_180041840
0x1800417ec  mov     rcx, rdi
0x1800417ef  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800417f6  mov     rax, [rcx]
0x1800417f9  mov     rax, [rax]
0x1800417fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041801  test    rax, rax
0x180041804  cmovnz  r14, rax
0x180041808  jmp     short loc_18004180D
0x18004180a  mov     r14, rax
0x18004180d  mov     ecx, r12d; dwErrCode
0x180041810  call    cs:__imp_SetLastError
0x180041816  cmp     [r14+7CCh], ebx
0x18004181d  jz      loc_180041780
0x180041823  mov     r9d, ebx; int
0x180041826  lea     rdx, aCopysamplebuff; "CopySampleBuffer2D"
0x18004182d  mov     r8d, 0FDh; int
0x180041833  mov     rcx, r14; this
0x180041836  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004183b  jmp     loc_180041780
0x180041840  mov     rax, [rax]
0x180041843  mov     edx, 7F0h
0x180041848  mov     rax, [rax+8]
0x18004184c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041851  test    eax, eax
0x180041853  jz      short loc_1800417EC
0x180041855  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18004185c  jmp     short loc_1800417F6
0x18004185e  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180041865  lea     rdi, qword_18010C230
0x18004186c  test    rsi, rsi
0x18004186f  jnz     short loc_1800418A2
0x180041871  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180041877  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18004187e  mov     rcx, rax
0x180041881  test    rax, rax
0x180041884  jz      short loc_1800418E8
0x180041886  mov     rax, [rax]
0x180041889  mov     edx, 7F0h
0x18004188e  mov     rax, [rax+8]
0x180041892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041897  test    eax, eax
0x180041899  jz      short loc_1800418E8
0x18004189b  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800418a2  cmp     byte ptr [rsi+8], 0
0x1800418a6  jnz     short loc_1800418F4
0x1800418a8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800418af  jb      short loc_1800418D4
0x1800418b1  mov     edx, 23h ; '#'
0x1800418b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800418bd  lea     r8, WPP_78ad5779643337f2c47fabc78d39cf1a_Traceguids
0x1800418c4  xor     r9d, r9d
0x1800418c7  mov     [rsp+68h+var_48], ebx
0x1800418cb  mov     rcx, [rcx+10h]
0x1800418cf  call    WPP_SF_qD
0x1800418d4  mov     rax, [r15]
0x1800418d7  mov     rcx, r15
0x1800418da  mov     rax, [rax+20h]
0x1800418de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800418e3  jmp     loc_180041624
0x1800418e8  mov     rsi, rdi
0x1800418eb  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rdi; CallStackTracing * CallStackTracing::s_wpInstance
0x1800418f2  jmp     short loc_1800418A2
0x1800418f4  lea     r14, [rsi+0D0h]
0x1800418fb  call    cs:__imp_GetLastError
0x180041901  mov     ecx, [rsi+0Ch]; dwTlsIndex
0x180041904  mov     r12d, eax
0x180041907  call    cs:__imp_TlsGetValue
0x18004190d  test    rax, rax
0x180041910  jnz     short loc_18004195B
0x180041912  call    cs:__imp_GetLastError
0x180041918  test    eax, eax
0x18004191a  jnz     short loc_18004195E
0x18004191c  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180041923  test    rcx, rcx
0x180041926  jnz     short loc_180041947
0x180041928  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18004192e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180041935  mov     rcx, rax
0x180041938  test    rax, rax
0x18004193b  jnz     short loc_180041991
0x18004193d  mov     rcx, rdi
0x180041940  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180041947  mov     rax, [rcx]
0x18004194a  mov     rax, [rax]
0x18004194d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041952  test    rax, rax
0x180041955  cmovnz  r14, rax
0x180041959  jmp     short loc_18004195E
0x18004195b  mov     r14, rax
0x18004195e  mov     ecx, r12d; dwErrCode
0x180041961  call    cs:__imp_SetLastError
0x180041967  cmp     [r14+7CCh], ebx
0x18004196e  jz      loc_1800418A8
0x180041974  mov     r9d, ebx; int
0x180041977  lea     rdx, aCopysamplebuff; "CopySampleBuffer2D"
0x18004197e  mov     r8d, 104h; int
0x180041984  mov     rcx, r14; this
0x180041987  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18004198c  jmp     loc_1800418A8
0x180041991  mov     rax, [rax]
0x180041994  mov     edx, 7F0h
0x180041999  mov     rax, [rax+8]
0x18004199d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800419a2  test    eax, eax
0x1800419a4  jz      short loc_18004193D
0x1800419a6  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800419ad  jmp     short loc_180041947
0x1800419af  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800419b6  lea     rdi, qword_18010C230
0x1800419bd  test    rsi, rsi
0x1800419c0  jnz     short loc_1800419F3
0x1800419c2  call    cs:__imp_MFGetCallStackTracingWeakReference
0x1800419c8  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x1800419cf  mov     rcx, rax
0x1800419d2  test    rax, rax
0x1800419d5  jz      short loc_180041A2E
0x1800419d7  mov     rax, [rax]
0x1800419da  mov     edx, 7F0h
0x1800419df  mov     rax, [rax+8]
0x1800419e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800419e8  test    eax, eax
0x1800419ea  jz      short loc_180041A2E
0x1800419ec  mov     rsi, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800419f3  cmp     byte ptr [rsi+8], 0
0x1800419f7  jnz     short loc_180041A3A
0x1800419f9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180041a00  jb      loc_180041624
0x180041a06  mov     edx, 24h ; '$'
0x180041a0b  mov     rcx, cs:WPP_GLOBAL_Control
0x180041a12  lea     r8, WPP_78ad5779643337f2c47fabc78d39cf1a_Traceguids
0x180041a19  xor     r9d, r9d
0x180041a1c  mov     [rsp+68h+var_48], ebx
0x180041a20  mov     rcx, [rcx+10h]
0x180041a24  call    WPP_SF_qD
0x180041a29  jmp     loc_180041624
  ... truncated ...
```
