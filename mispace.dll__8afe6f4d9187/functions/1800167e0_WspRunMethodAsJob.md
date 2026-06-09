# WspRunMethodAsJob

- ea: `0x1800167e0`
- end: `0x180016a94`
- name: `WspRunMethodAsJob`
- size: `692`
- prototype: `__int64 __usercall@<rax>(struct _MI_Context *@<rcx>, __int64, int, int, __int64, struct _MI_Instance *, __int64)`
- caller_count: `7`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x18013fd50`
- `0x180146680`
- `0x180146e00`
- `0x18014a060`
- `0x18014a7a0`
- `0x18014e5f0`
- `0x18014fd10`

## callees

- `0x1800011b0`
- `0x1800015b8`
- `0x180013774`
- `0x180013898`
- `0x18001489c`
- `0x180014be8`
- `0x180014d18`
- `0x1800167e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016991`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016991`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001696e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001696e`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180016983`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180016983`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180016937`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180016937`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180016a49`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180016a49`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180016a1e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180016a1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016a10`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016a10`

## pseudocode

```c
__int64 __fastcall WspRunMethodAsJob(
        struct _MI_Context *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        int a7,
        __int64 a8,
        struct _MI_Instance *a9,
        _DWORD *a10)
{
  unsigned int v11; // ebx
  struct _TP_WORK *ThreadpoolWork; // rsi
  enum _MI_Result v15; // eax
  unsigned int v16; // edx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  _QWORD *v20; // rdi
  enum _MI_Result v21; // ebx
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  enum _MI_Result v25; // eax
  __int64 v26; // rcx
  char *v27; // rdx
  HANDLE CurrentThread; // rax
  PVOID pv; // [rsp+48h] [rbp-18h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-10h] BYREF
  const char *v32; // [rsp+58h] [rbp-8h] BYREF

  v11 = a3;
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    pv = "WspRunMethodAsJob";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (__int64)a1,
      (__int64)&byte_1802EE7AF,
      a3,
      a4,
      &pv);
  }
  ThreadpoolWork = 0;
  pv = 0;
  TokenHandle = 0;
  v15 = (unsigned int)_WspCreateJob(a1, a2, v11, a6, a7, a8, &pv);
  v20 = pv;
  v21 = v15;
  if ( v15 )
  {
    if ( (unsigned int)dword_180397B68 > 2 )
    {
      LODWORD(pv) = 1452;
      v32 = "WspRunMethodAsJob";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v17,
        (__int64)word_1802EEAE2,
        v18,
        v19,
        &v32);
    }
    goto LABEL_19;
  }
  v21 = _WspSetCreatedJob(a1, (struct _WSP_ASYNC_METHOD_CONTEXT *)pv, a9);
  if ( v21 == MI_RESULT_OK )
  {
    ThreadpoolWork = CreateThreadpoolWork(WspResumeMethodWorker, v20, 0);
    if ( ThreadpoolWork )
    {
      CurrentThread = GetCurrentThread();
      if ( OpenThreadToken(CurrentThread, 0x2000Cu, 0, &TokenHandle) || GetLastError() == 1008 )
      {
        *a10 = 4096;
        *v20 = TokenHandle;
        v20[1] = a4;
        v20[2] = a5;
        SubmitThreadpoolWork(ThreadpoolWork);
        goto LABEL_26;
      }
      v21 = GleToMiResult();
      if ( (unsigned int)dword_180397B68 <= 2 )
        goto LABEL_17;
      LODWORD(pv) = v21;
      v27 = &byte_1802EF217;
    }
    else
    {
      v25 = GleToMiResult();
      v26 = (unsigned int)dword_180397B68;
      v21 = v25;
      if ( (unsigned int)dword_180397B68 <= 2 )
        goto LABEL_17;
      LODWORD(pv) = v25;
      v27 = byte_1802EF11D;
    }
    v32 = "WspRunMethodAsJob";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v26,
      (__int64)v27,
      v18,
      v19,
      &v32);
LABEL_17:
    if ( v21 == MI_RESULT_OK )
      goto LABEL_26;
    goto LABEL_18;
  }
  if ( (unsigned int)dword_180397B68 > 2 )
  {
    LODWORD(pv) = v21;
    v32 = "WspRunMethodAsJob";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v22,
      (__int64)&dword_1802EEC2C,
      v23,
      v24,
      &v32);
  }
LABEL_18:
  _WspDeleteJob((struct _WSP_ASYNC_METHOD_CONTEXT *)v20, 1);
LABEL_19:
  if ( v20 )
    _WSP_ASYNC_METHOD_CONTEXT::`scalar deleting destructor'((_WSP_ASYNC_METHOD_CONTEXT *)v20, v16);
  v26 = (__int64)TokenHandle;
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( ThreadpoolWork )
    CloseThreadpoolWork(ThreadpoolWork);
LABEL_26:
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    LODWORD(pv) = 1519;
    v32 = "WspRunMethodAsJob";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v26,
      (__int64)word_1802EF2C2,
      v18,
      v19,
      &v32);
  }
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x1800167e0  push    rbp
0x1800167e2  push    rbx
0x1800167e3  push    rsi
0x1800167e4  push    rdi
0x1800167e5  push    r12
0x1800167e7  push    r14
0x1800167e9  push    r15
0x1800167eb  mov     rbp, rsp
0x1800167ee  sub     rsp, 60h
0x1800167f2  mov     eax, cs:dword_180397B68
0x1800167f8  lea     r12, aWsprunmethodas_0; "WspRunMethodAsJob"
0x1800167ff  mov     r15, r9
0x180016802  mov     ebx, r8d
0x180016805  mov     rdi, rdx
0x180016808  mov     r14, rcx
0x18001680b  cmp     eax, 5
0x18001680e  jbe     short loc_180016839
0x180016810  lea     rax, [rbp+var_20]
0x180016814  mov     [rbp+var_20], 597h
0x18001681b  mov     [rsp+60h+var_38], rax
0x180016820  lea     rdx, byte_1802EE7AF
0x180016827  lea     rax, [rbp+pv]
0x18001682b  mov     [rbp+pv], r12
0x18001682f  mov     [rsp+60h+var_40], rax
0x180016834  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180016839  mov     r9d, [rbp+arg_28]
0x18001683d  lea     rax, [rbp+pv]
0x180016841  mov     [rsp+60h+var_30], rax
0x180016846  mov     r8d, ebx
0x180016849  mov     rax, [rbp+arg_38]
0x18001684d  mov     rdx, rdi
0x180016850  mov     [rsp+60h+var_38], rax
0x180016855  mov     rcx, r14
0x180016858  mov     eax, [rbp+arg_30]
0x18001685b  xor     esi, esi
0x18001685d  mov     dword ptr [rsp+60h+var_40], eax
0x180016861  mov     [rbp+pv], 0
0x180016869  mov     [rbp+TokenHandle], 0
0x180016871  call    ?_WspCreateJob@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBGW4JOB_TYPE@SM_CONSTANTS@@W4WSP_SUBSYSTEM_TYPE@@W4WSP_OBJECT_TYPE@@1PEAPEAU_WSP_ASYNC_METHOD_CONTEXT@@@Z; _WspCreateJob(_MI_Context *,ushort const *,SM_CONSTANTS::JOB_TYPE,WSP_SUBSYSTEM_TYPE,WSP_OBJECT_TYPE,ushort const *,_WSP_ASYNC_METHOD_CONTEXT * *)
0x180016876  mov     rdi, [rbp+pv]
0x18001687a  mov     ebx, eax
0x18001687c  test    eax, eax
0x18001687e  jz      short loc_1800168C9
0x180016880  mov     eax, cs:dword_180397B68
0x180016886  cmp     eax, 2
0x180016889  jbe     loc_1800169FA
0x18001688f  lea     rax, [rbp+var_20]
0x180016893  mov     [rbp+var_20], ebx
0x180016896  mov     [rsp+60h+var_30], rax
0x18001689b  lea     rdx, word_1802EEAE2
0x1800168a2  lea     rax, [rbp+pv]
0x1800168a6  mov     dword ptr [rbp+pv], 5ACh
0x1800168ad  mov     [rsp+60h+var_38], rax
0x1800168b2  lea     rax, [rbp+var_8]
0x1800168b6  mov     [rsp+60h+var_40], rax
0x1800168bb  mov     [rbp+var_8], r12
0x1800168bf  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800168c4  jmp     loc_1800169FA
0x1800168c9  mov     r8, [rbp+arg_40]; struct _MI_Instance *
0x1800168d0  mov     rdx, rdi; struct _WSP_ASYNC_METHOD_CONTEXT *
0x1800168d3  mov     rcx, r14; struct _MI_Context *
0x1800168d6  call    ?_WspSetCreatedJob@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_WSP_ASYNC_METHOD_CONTEXT@@PEAU_MI_Instance@@@Z; _WspSetCreatedJob(_MI_Context *,_WSP_ASYNC_METHOD_CONTEXT *,_MI_Instance *)
0x1800168db  mov     ebx, eax
0x1800168dd  test    eax, eax
0x1800168df  jz      short loc_18001692A
0x1800168e1  mov     eax, cs:dword_180397B68
0x1800168e7  cmp     eax, 2
0x1800168ea  jbe     loc_1800169ED
0x1800168f0  lea     rax, [rbp+pv]
0x1800168f4  mov     dword ptr [rbp+pv], ebx
0x1800168f7  mov     [rsp+60h+var_30], rax
0x1800168fc  lea     rdx, dword_1802EEC2C
0x180016903  lea     rax, [rbp+var_20]
0x180016907  mov     [rbp+var_20], 5B6h
0x18001690e  mov     [rsp+60h+var_38], rax
0x180016913  lea     rax, [rbp+var_8]
0x180016917  mov     [rsp+60h+var_40], rax
0x18001691c  mov     [rbp+var_8], r12
0x180016920  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180016925  jmp     loc_1800169ED
0x18001692a  xor     r8d, r8d; pcbe
0x18001692d  lea     rcx, _WspResumeMethodWorker; pfnwk
0x180016934  mov     rdx, rdi; pv
0x180016937  call    cs:__imp_CreateThreadpoolWork
0x18001693d  mov     rsi, rax
0x180016940  test    rax, rax
0x180016943  jnz     short loc_18001696E
0x180016945  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x18001694a  mov     ecx, cs:dword_180397B68
0x180016950  mov     ebx, eax
0x180016952  cmp     ecx, 2
0x180016955  jbe     loc_1800169E9
0x18001695b  mov     dword ptr [rbp+pv], eax
0x18001695e  lea     rdx, byte_1802EF11D
0x180016965  mov     [rbp+var_20], 5C0h
0x18001696c  jmp     short loc_1800169C5
0x18001696e  call    cs:__imp_GetCurrentThread
0x180016974  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180016978  xor     r8d, r8d; OpenAsSelf
0x18001697b  mov     rcx, rax; ThreadHandle
0x18001697e  mov     edx, 2000Ch; DesiredAccess
0x180016983  call    cs:__imp_OpenThreadToken
0x180016989  test    eax, eax
0x18001698b  jnz     loc_180016A26
0x180016991  call    cs:__imp_GetLastError
0x180016997  cmp     eax, 3F0h
0x18001699c  jz      loc_180016A26
0x1800169a2  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x1800169a7  mov     ebx, eax
0x1800169a9  mov     eax, cs:dword_180397B68
0x1800169af  cmp     eax, 2
0x1800169b2  jbe     short loc_1800169E9
0x1800169b4  mov     dword ptr [rbp+pv], ebx
0x1800169b7  lea     rdx, byte_1802EF217
0x1800169be  mov     [rbp+var_20], 5CBh
0x1800169c5  lea     rax, [rbp+pv]
0x1800169c9  mov     [rbp+var_8], r12
0x1800169cd  mov     [rsp+60h+var_30], rax
0x1800169d2  lea     rax, [rbp+var_20]
0x1800169d6  mov     [rsp+60h+var_38], rax
0x1800169db  lea     rax, [rbp+var_8]
0x1800169df  mov     [rsp+60h+var_40], rax
0x1800169e4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800169e9  test    ebx, ebx
0x1800169eb  jz      short loc_180016A4F
0x1800169ed  mov     edx, 1; int
0x1800169f2  mov     rcx, rdi; struct _WSP_ASYNC_METHOD_CONTEXT *
0x1800169f5  call    ?_WspDeleteJob@@YAXPEAU_WSP_ASYNC_METHOD_CONTEXT@@H@Z; _WspDeleteJob(_WSP_ASYNC_METHOD_CONTEXT *,int)
0x1800169fa  test    rdi, rdi
0x1800169fd  jz      short loc_180016A07
0x1800169ff  mov     rcx, rdi; this
0x180016a02  call    ??_G_WSP_ASYNC_METHOD_CONTEXT@@QEAAPEAXI@Z; _WSP_ASYNC_METHOD_CONTEXT::`scalar deleting destructor'(uint)
0x180016a07  mov     rcx, [rbp+TokenHandle]; hObject
0x180016a0b  test    rcx, rcx
0x180016a0e  jz      short loc_180016A16
0x180016a10  call    cs:__imp_CloseHandle
0x180016a16  test    rsi, rsi
0x180016a19  jz      short loc_180016A4F
0x180016a1b  mov     rcx, rsi; pwk
0x180016a1e  call    cs:__imp_CloseThreadpoolWork
0x180016a24  jmp     short loc_180016A4F
0x180016a26  mov     rax, [rbp+arg_48]
0x180016a2d  mov     rcx, rsi; pwk
0x180016a30  mov     dword ptr [rax], 1000h
0x180016a36  mov     rax, [rbp+TokenHandle]
0x180016a3a  mov     [rdi], rax
0x180016a3d  mov     rax, [rbp+arg_20]
0x180016a41  mov     [rdi+8], r15
0x180016a45  mov     [rdi+10h], rax
0x180016a49  call    cs:__imp_SubmitThreadpoolWork
0x180016a4f  mov     eax, cs:dword_180397B68
0x180016a55  cmp     eax, 5
0x180016a58  jbe     short loc_180016A83
0x180016a5a  lea     rax, [rbp+pv]
0x180016a5e  mov     dword ptr [rbp+pv], 5EFh
0x180016a65  mov     [rsp+60h+var_38], rax
0x180016a6a  lea     rdx, word_1802EF2C2
0x180016a71  lea     rax, [rbp+var_8]
0x180016a75  mov     [rbp+var_8], r12
0x180016a79  mov     [rsp+60h+var_40], rax
0x180016a7e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180016a83  mov     eax, ebx
0x180016a85  add     rsp, 60h
0x180016a89  pop     r15
0x180016a8b  pop     r14
0x180016a8d  pop     r12
0x180016a8f  pop     rdi
0x180016a90  pop     rsi
0x180016a91  pop     rbx
0x180016a92  pop     rbp
0x180016a93  retn
```
