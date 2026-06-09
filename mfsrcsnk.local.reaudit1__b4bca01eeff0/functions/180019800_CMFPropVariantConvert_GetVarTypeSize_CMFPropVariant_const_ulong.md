# CMFPropVariantConvert::GetVarTypeSize(CMFPropVariant const *,ulong *)

- ea: `0x180019800`
- end: `0x180019d1c`
- name: `?GetVarTypeSize@CMFPropVariantConvert@@SAJPEBVCMFPropVariant@@PEAK@Z`
- size: `1308`
- prototype: `__int64 __fastcall(const struct CMFPropVariant *, unsigned int *)`
- caller_count: `6`
- callee_count: `8`
- tags: ``

## callers

- `0x180014bf0`
- `0x180016f60`
- `0x180018d60`
- `0x180019264`
- `0x18004452c`
- `0x1800c8690`

## callees

- `0x180005cf4`
- `0x180019800`
- `0x18001c6c0`
- `0x18001cee0`
- `0x180024890`
- `0x180077708`
- `0x180079680`
- `0x18017c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019888`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001990a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019888`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001990a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001985b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800198df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800199b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800199ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001985b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800198df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800199b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800199ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019955`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019955`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001986d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800198f0`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18001986d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800198f0`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019981`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019a68`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019aa3`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019981`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019a68`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x180019aa3`

## pseudocode

```c
__int64 __fastcall CMFPropVariantConvert::GetVarTypeSize(__int64 a1, unsigned __int64 a2)
{
  unsigned __int16 v2; // si
  _DWORD *v3; // r15
  int v4; // ebp
  unsigned int v5; // esi
  wchar_t *v6; // rbx
  wchar_t *v7; // rdi
  DWORD LastError; // r14d
  wchar_t *Value; // rax
  __int64 v10; // rax
  __int64 v11; // rax
  wchar_t *v12; // rdi
  DWORD v13; // esi
  wchar_t *v14; // rax
  int v15; // eax
  int v16; // eax
  CallStackTracing *v18; // rax
  CallStackTracing *v19; // rcx
  __int64 v20; // rax
  CallStackTracing *v21; // rcx
  __int64 v22; // rax
  __int64 v23; // rdx
  wchar_t *v24; // rcx
  CallStackTracing *v25; // rax
  CallStackTracing *v26; // rax
  struct CallStackContext *ThreadRelativeContext; // rax
  struct CallStackContext *v28; // rax
  char v29; // [rsp+60h] [rbp+8h] BYREF

  v2 = *(_WORD *)a1;
  v3 = (_DWORD *)a2;
  v4 = 0;
  if ( (*(_WORD *)a1 & 0xFFF) != 0 )
  {
    a2 = (unsigned __int64)&_ImageBase;
    switch ( *(_WORD *)a1 & 0xFFF )
    {
      case 1:
        goto LABEL_2;
      case 2:
      case 0xB:
      case 0x12:
        v5 = 2;
        break;
      case 3:
      case 4:
      case 0xA:
      case 0x13:
      case 0x16:
      case 0x17:
        v5 = 4;
        break;
      case 5:
      case 6:
      case 7:
      case 8:
      case 9:
      case 0xD:
      case 0x14:
      case 0x15:
      case 0x1E:
      case 0x1F:
      case 0x40:
        v5 = 8;
        break;
      case 0xC:
        v5 = (v2 & 0x1000 | 0x800u) >> 8;
        break;
      case 0x10:
      case 0x11:
        v5 = 1;
        break;
      case 0x41:
        v5 = 16;
        break;
      case 0x48:
        a2 = v2;
        LOWORD(a2) = v2 & 0x1000;
        a1 = 8;
        if ( (v2 & 0x1000) != 0 )
          a1 = 16;
        v5 = a1;
        break;
      default:
        v5 = 0;
        CallStackScopeTrace::CallStackScopeTrace(
          (CallStackScopeTrace *)&v29,
          "CMFPropVariantConvert::GetVarTypeSize",
          2803);
        v24 = (wchar_t *)CallStackTracing::s_wpInstance;
        v4 = -1072875800;
        if ( !CallStackTracing::s_wpInstance )
        {
          v25 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v23);
          CallStackTracing::s_wpInstance = v25;
          if ( v25 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v25 + 8LL))(v25, 2032) )
          {
            v24 = (wchar_t *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v24 = &qword_1801B97E0;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
          }
        }
        if ( *((_BYTE *)v24 + 8) )
        {
          ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v24);
          if ( *((_DWORD *)ThreadRelativeContext + 499) != -1072875800 )
            CallStackContext::TraceFailure(
              ThreadRelativeContext,
              "CMFPropVariantConvert::GetVarTypeSize",
              2803,
              -1072875800);
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            180,
            WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids,
            0,
            -1072875800);
        CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v29);
        break;
    }
  }
  else
  {
LABEL_2:
    v5 = 0;
  }
  v6 = (wchar_t *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(a1, a2);
    CallStackTracing::s_wpInstance = v18;
    a1 = (__int64)v18;
    if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
    {
      v6 = (wchar_t *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v6 = &qword_1801B97E0;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
    }
  }
  if ( *((_BYTE *)v6 + 8) )
  {
    v7 = v6 + 104;
    LastError = GetLastError();
    Value = (wchar_t *)TlsGetValue(*((_DWORD *)v6 + 3));
    if ( Value )
    {
      v7 = Value;
    }
    else if ( !GetLastError() )
    {
      v19 = CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        CallStackTracing::InitInstance();
        v19 = CallStackTracing::s_wpInstance;
      }
      v20 = (**(__int64 (__fastcall ***)(CallStackTracing *))v19)(v19);
      if ( v20 )
        v7 = (wchar_t *)v20;
    }
    SetLastError(LastError);
    v10 = *((unsigned int *)v7 + 497);
    v6 = (wchar_t *)CallStackTracing::s_wpInstance;
    if ( (unsigned int)v10 < *((_DWORD *)v7 + 498) )
    {
      v11 = 2 * v10;
      *(_QWORD *)&v7[4 * v11] = "CMFPropVariantConvert::GetVarTypeSize";
      *(_DWORD *)&v7[4 * v11 + 4] = 2806;
    }
    ++*((_DWORD *)v7 + 497);
  }
  if ( v4 < 0 )
  {
    if ( !v6 )
    {
      v26 = (CallStackTracing *)MFGetCallStackTracingWeakReference(a1, a2);
      CallStackTracing::s_wpInstance = v26;
      if ( v26 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v26 + 8LL))(v26, 2032) )
      {
        v6 = (wchar_t *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v6 = &qword_1801B97E0;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1801B97E0;
      }
    }
    if ( *((_BYTE *)v6 + 8) )
    {
      v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v6);
      if ( *((_DWORD *)v28 + 499) != v4 )
        CallStackContext::TraceFailure(v28, "CMFPropVariantConvert::GetVarTypeSize", 2806, v4);
    }
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 181, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids, 0, v4);
    CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)&v29);
  }
  else
  {
    *v3 = v5;
    if ( *((_BYTE *)v6 + 8) )
    {
      v12 = v6 + 104;
      v13 = GetLastError();
      v14 = (wchar_t *)TlsGetValue(*((_DWORD *)v6 + 3));
      if ( v14 )
      {
        v12 = v14;
      }
      else if ( !GetLastError() )
      {
        v21 = CallStackTracing::s_wpInstance;
        if ( !CallStackTracing::s_wpInstance )
        {
          CallStackTracing::InitInstance();
          v21 = CallStackTracing::s_wpInstance;
        }
        v22 = (**(__int64 (__fastcall ***)(CallStackTracing *))v21)(v21);
        if ( v22 )
          v12 = (wchar_t *)v22;
      }
      SetLastError(v13);
      v15 = *((_DWORD *)v12 + 497);
      if ( v15 )
      {
        v16 = v15 - 1;
        *((_DWORD *)v12 + 497) = v16;
        if ( !v16 )
        {
          *((_DWORD *)v12 + 497) = 0;
          *((_QWORD *)v12 + 252) = 0;
          *((_DWORD *)v12 + 499) = 0;
          *((GUID *)v12 + 125) = GUID_00000000_0000_0000_0000_000000000000;
          *((_DWORD *)v12 + 506) = 0;
          *((_DWORD *)v12 + 496) = GetCurrentThreadId();
        }
      }
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180019800  mov     [rsp+arg_18], rbx
0x180019805  push    rbp
0x180019806  push    rsi
0x180019807  push    r12
0x180019809  push    r13
0x18001980b  push    r15
0x18001980d  sub     rsp, 30h
0x180019811  movzx   esi, word ptr [rcx]
0x180019814  lea     r13, aCmfpropvariant_16; "CMFPropVariantConvert::GetVarTypeSize"
0x18001981b  xor     r12d, r12d
0x18001981e  mov     eax, esi
0x180019820  mov     r15, rdx
0x180019823  mov     ebp, r12d
0x180019826  and     eax, 0FFFh
0x18001982b  jnz     loc_180019B2C
0x180019831  mov     esi, r12d; jumptable 0000000180019B52 case 1
0x180019834  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18001983b  test    rbx, rbx
0x18001983e  jz      loc_180019981
0x180019844  mov     [rsp+58h+arg_8], rdi
0x180019849  cmp     [rbx+8], r12b
0x18001984d  jz      short loc_1800198C3
0x18001984f  lea     rdi, [rbx+0D0h]
0x180019856  mov     [rsp+58h+arg_10], r14
0x18001985b  call    cs:__imp_GetLastError
0x180019862  nop     dword ptr [rax+rax+00h]
0x180019867  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x18001986a  mov     r14d, eax
0x18001986d  call    cs:__imp_TlsGetValue
0x180019874  nop     dword ptr [rax+rax+00h]
0x180019879  test    rax, rax
0x18001987c  jz      loc_1800199B3
0x180019882  mov     rdi, rax
0x180019885  mov     ecx, r14d; dwErrCode
0x180019888  call    cs:__imp_SetLastError
0x18001988f  nop     dword ptr [rax+rax+00h]
0x180019894  mov     eax, [rdi+7C4h]
0x18001989a  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800198a1  mov     r14, [rsp+58h+arg_10]
0x1800198a6  cmp     eax, [rdi+7C8h]
0x1800198ac  jnb     short loc_1800198BD
0x1800198ae  add     rax, rax
0x1800198b1  mov     [rdi+rax*8], r13
0x1800198b5  mov     dword ptr [rdi+rax*8+8], 0AF6h
0x1800198bd  inc     dword ptr [rdi+7C4h]
0x1800198c3  test    ebp, ebp
0x1800198c5  js      loc_180019A9A
0x1800198cb  mov     [r15], esi
0x1800198ce  cmp     [rbx+8], r12b
0x1800198d2  jz      loc_180019967
0x1800198d8  lea     rdi, [rbx+0D0h]
0x1800198df  call    cs:__imp_GetLastError
0x1800198e6  nop     dword ptr [rax+rax+00h]
0x1800198eb  mov     ecx, [rbx+0Ch]; dwTlsIndex
0x1800198ee  mov     esi, eax
0x1800198f0  call    cs:__imp_TlsGetValue
0x1800198f7  nop     dword ptr [rax+rax+00h]
0x1800198fc  test    rax, rax
0x1800198ff  jz      loc_1800199EA
0x180019905  mov     rdi, rax
0x180019908  mov     ecx, esi; dwErrCode
0x18001990a  call    cs:__imp_SetLastError
0x180019911  nop     dword ptr [rax+rax+00h]
0x180019916  mov     eax, [rdi+7C4h]
0x18001991c  test    eax, eax
0x18001991e  jz      short loc_180019967
0x180019920  sub     eax, 1
0x180019923  mov     [rdi+7C4h], eax
0x180019929  jnz     short loc_180019967
0x18001992b  mov     [rdi+7C4h], r12d
0x180019932  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180019939  mov     [rdi+7E0h], r12
0x180019940  mov     [rdi+7CCh], r12d
0x180019947  movups  xmmword ptr [rdi+7D0h], xmm0
0x18001994e  mov     [rdi+7E8h], r12d
0x180019955  call    cs:__imp_GetCurrentThreadId
0x18001995c  nop     dword ptr [rax+rax+00h]
0x180019961  mov     [rdi+7C0h], eax
0x180019967  mov     rdi, [rsp+58h+arg_8]
0x18001996c  mov     eax, ebp
0x18001996e  mov     rbx, [rsp+58h+arg_18]
0x180019973  add     rsp, 30h
0x180019977  pop     r15
0x180019979  pop     r13
0x18001997b  pop     r12
0x18001997d  pop     rsi
0x18001997e  pop     rbp
0x18001997f  retn
0x180019981  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180019988  nop     dword ptr [rax+rax+00h]
0x18001998d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180019994  mov     rcx, rax
0x180019997  test    rax, rax
0x18001999a  jnz     loc_180019C25
0x1800199a0  lea     rbx, qword_1801B97E0
0x1800199a7  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x1800199ae  jmp     loc_180019844
0x1800199b3  call    cs:__imp_GetLastError
0x1800199ba  nop     dword ptr [rax+rax+00h]
0x1800199bf  test    eax, eax
0x1800199c1  jnz     loc_180019885
0x1800199c7  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x1800199ce  test    rcx, rcx
0x1800199d1  jz      short loc_180019A21
0x1800199d3  mov     rax, [rcx]
0x1800199d6  mov     rax, [rax]
0x1800199d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199de  test    rax, rax
0x1800199e1  cmovnz  rdi, rax
0x1800199e5  jmp     loc_180019885
0x1800199ea  call    cs:__imp_GetLastError
0x1800199f1  nop     dword ptr [rax+rax+00h]
0x1800199f6  test    eax, eax
0x1800199f8  jnz     loc_180019908
0x1800199fe  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019a05  test    rcx, rcx
0x180019a08  jz      short loc_180019A2F
0x180019a0a  mov     rax, [rcx]
0x180019a0d  mov     rax, [rax]
0x180019a10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019a15  test    rax, rax
0x180019a18  cmovnz  rdi, rax
0x180019a1c  jmp     loc_180019908
0x180019a21  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180019a26  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019a2d  jmp     short loc_1800199D3
0x180019a2f  call    ?InitInstance@CallStackTracing@@KAXXZ; CallStackTracing::InitInstance(void)
0x180019a34  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019a3b  jmp     short loc_180019A0A
0x180019a3d  mov     r8d, 0AF3h; jumptable 0000000180019B52 default case, cases 14,15,24-29,32-63,66-71
0x180019a43  lea     rcx, [rsp+58h+arg_0]; this
0x180019a48  mov     rdx, r13; char *
0x180019a4b  mov     esi, r12d
0x180019a4e  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x180019a53  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019a5a  mov     ebp, 0C00D36E8h
0x180019a5f  test    rcx, rcx
0x180019a62  jnz     loc_180019BE0
0x180019a68  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180019a6f  nop     dword ptr [rax+rax+00h]
0x180019a74  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180019a7b  mov     rcx, rax
0x180019a7e  test    rax, rax
0x180019a81  jnz     loc_180019BC0
0x180019a87  lea     rcx, qword_1801B97E0
0x180019a8e  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x180019a95  jmp     loc_180019BE0
0x180019a9a  test    rbx, rbx
0x180019a9d  jnz     loc_180019C6A
0x180019aa3  call    cs:__imp_MFGetCallStackTracingWeakReference
0x180019aaa  nop     dword ptr [rax+rax+00h]
0x180019aaf  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x180019ab6  mov     rcx, rax
0x180019ab9  test    rax, rax
0x180019abc  jnz     loc_180019C4A
0x180019ac2  lea     rbx, qword_1801B97E0
0x180019ac9  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rbx; CallStackTracing * CallStackTracing::s_wpInstance
0x180019ad0  jmp     loc_180019C6A
0x180019ad5  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180019ada  cmp     [rax+7CCh], ebp
0x180019ae0  jz      loc_180019BEA
0x180019ae6  mov     r9d, ebp; int
0x180019ae9  mov     r8d, 0AF3h; int
0x180019aef  mov     rdx, r13; char *
0x180019af2  mov     rcx, rax; this
0x180019af5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180019afa  jmp     loc_180019BEA
0x180019aff  mov     rcx, rbx; this
0x180019b02  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x180019b07  cmp     [rax+7CCh], ebp
0x180019b0d  jz      loc_180019C74
0x180019b13  mov     r9d, ebp; int
0x180019b16  mov     r8d, 0AF6h; int
0x180019b1c  mov     rdx, r13; char *
0x180019b1f  mov     rcx, rax; this
0x180019b22  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x180019b27  jmp     loc_180019C74
0x180019b2c  dec     eax; switch 72 cases
0x180019b2e  cmp     eax, 47h
0x180019b31  ja      def_180019B52; jumptable 0000000180019B52 default case, cases 14,15,24-29,32-63,66-71
0x180019b37  lea     rdx, __ImageBase
0x180019b3e  cdqe
0x180019b40  movzx   eax, ds:(byte_180019CD4 - 180000000h)[rdx+rax]
0x180019b48  mov     ecx, ds:(jpt_180019B52 - 180000000h)[rdx+rax*4]
0x180019b4f  add     rcx, rdx
0x180019b52  jmp     rcx; switch jump
0x180019b58  mov     esi, 10h; jumptable 0000000180019B52 case 65
0x180019b5d  jmp     loc_180019834
0x180019b62  mov     esi, 8; jumptable 0000000180019B52 cases 5-9,13,20,21,30,31,64
0x180019b67  jmp     loc_180019834
0x180019b6c  mov     esi, 2; jumptable 0000000180019B52 cases 2,11,18
0x180019b71  jmp     loc_180019834
0x180019b76  mov     esi, 1; jumptable 0000000180019B52 cases 16,17
0x180019b7b  jmp     loc_180019834
0x180019b80  mov     esi, 4; jumptable 0000000180019B52 cases 3,4,10,19,22,23
0x180019b85  jmp     loc_180019834
0x180019b8a  mov     eax, 1000h; jumptable 0000000180019B52 case 12
0x180019b8f  and     esi, eax
0x180019b91  bts     esi, 0Bh
0x180019b95  shr     esi, 8
0x180019b98  jmp     loc_180019834
0x180019b9d  movzx   edx, si; jumptable 0000000180019B52 case 72
0x180019ba0  mov     eax, 1000h
0x180019ba5  mov     esi, 10h
0x180019baa  and     dx, ax
0x180019bad  cmp     r12w, dx
0x180019bb1  mov     ecx, 8
0x180019bb6  cmovnz  ecx, esi
0x180019bb9  mov     esi, ecx
0x180019bbb  jmp     loc_180019834
0x180019bc0  mov     rax, [rax]
0x180019bc3  mov     edx, 7F0h
0x180019bc8  mov     rax, [rax+8]
0x180019bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019bd1  test    eax, eax
0x180019bd3  jz      loc_180019A87
0x180019bd9  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x180019be0  cmp     [rcx+8], sil
0x180019be4  jnz     loc_180019AD5
0x180019bea  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180019bf1  jb      short loc_180019C16
0x180019bf3  mov     rcx, cs:WPP_GLOBAL_Control
0x180019bfa  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x180019c01  mov     edx, 0B4h
0x180019c06  mov     [rsp+58h+var_38], ebp
0x180019c0a  xor     r9d, r9d
0x180019c0d  mov     rcx, [rcx+10h]
0x180019c11  call    WPP_SF_qD
0x180019c16  lea     rcx, [rsp+58h+arg_0]; this
0x180019c1b  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180019c20  jmp     loc_180019834
0x180019c25  mov     rax, [rax]
0x180019c28  mov     edx, 7F0h
0x180019c2d  mov     rax, [rax+8]
0x180019c31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c36  test    eax, eax
0x180019c38  jz      loc_1800199A0
0x180019c3e  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019c45  jmp     loc_180019844
0x180019c4a  mov     rax, [rax]
0x180019c4d  mov     edx, 7F0h
0x180019c52  mov     rax, [rax+8]
0x180019c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019c5b  test    eax, eax
0x180019c5d  jz      loc_180019AC2
0x180019c63  mov     rbx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x180019c6a  cmp     [rbx+8], r12b
0x180019c6e  jnz     loc_180019AFF
0x180019c74  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180019c7b  jb      short loc_180019CA0
0x180019c7d  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c84  lea     r8, WPP_1ec586c66cd5396c94f5f12f97d463a7_Traceguids
0x180019c8b  mov     edx, 0B5h
0x180019c90  mov     [rsp+58h+var_38], ebp
0x180019c94  xor     r9d, r9d
0x180019c97  mov     rcx, [rcx+10h]
0x180019c9b  call    WPP_SF_qD
0x180019ca0  lea     rcx, [rsp+58h+arg_0]; this
0x180019ca5  call    ??1CallStackScopeTrace@@QEAA@XZ; CallStackScopeTrace::~CallStackScopeTrace(void)
0x180019caa  jmp     loc_180019967
```
