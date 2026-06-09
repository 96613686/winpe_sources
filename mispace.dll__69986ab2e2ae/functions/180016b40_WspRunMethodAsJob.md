# WspRunMethodAsJob

- ea: `0x180016b40`
- end: `0x180016e1f`
- name: `WspRunMethodAsJob`
- size: `735`
- prototype: `__int64 __usercall@<rax>(struct _MI_Context *@<rcx>, __int64, int, int, __int64, struct _MI_Instance *, __int64)`
- caller_count: `7`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x1801441f0`
- `0x18014abb0`
- `0x18014b300`
- `0x18014e450`
- `0x18014eb60`
- `0x1801528f0`
- `0x180153f90`

## callees

- `0x1800011c4`
- `0x1800015d8`
- `0x180013a24`
- `0x180013b4c`
- `0x180014bd4`
- `0x180014f20`
- `0x180015060`
- `0x180016b40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016d03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016d03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180016cd4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180016cd4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180016cef`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180016cef`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180016c97`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180016c97`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180016dcd`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180016dcd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180016d9c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180016d9c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016d88`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016d88`

## pseudocode

```c
__int64 __fastcall WspRunMethodAsJob(
        struct _MI_Context *a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        int a7,
        __int64 a8,
        struct _MI_Instance *a9,
        _DWORD *a10)
{
  struct _TP_WORK *ThreadpoolWork; // rsi
  __int32 v15; // eax
  unsigned int v16; // edx
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  _QWORD *v20; // rdi
  enum _MI_Result v21; // ebx
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  enum _MI_Result v25; // eax
  int v26; // ecx
  char *v27; // rdx
  HANDLE CurrentThread; // rax
  int v30; // [rsp+40h] [rbp-20h] BYREF
  PVOID pv; // [rsp+48h] [rbp-18h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-10h] BYREF
  const char *v33; // [rsp+58h] [rbp-8h] BYREF

  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    v30 = 1431;
    pv = "WspRunMethodAsJob";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (_DWORD)a1,
      (unsigned int)&byte_1802F5737,
      a3,
      a4,
      (__int64)&pv,
      (__int64)&v30);
  }
  ThreadpoolWork = 0;
  pv = 0;
  TokenHandle = 0;
  v15 = _WspCreateJob(a1, a2, a3, a6, a7, a8, &pv);
  v20 = pv;
  v21 = v15;
  if ( v15 )
  {
    if ( (unsigned int)dword_18039EB68 > 2 )
    {
      v30 = v15;
      LODWORD(pv) = 1452;
      v33 = "WspRunMethodAsJob";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v17,
        (unsigned int)word_1802F5A6A,
        v18,
        v19,
        (__int64)&v33,
        (__int64)&pv,
        (__int64)&v30);
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
      if ( (unsigned int)dword_18039EB68 <= 2 )
        goto LABEL_17;
      LODWORD(pv) = v21;
      v27 = &byte_1802F619F;
      v30 = 1483;
    }
    else
    {
      v25 = GleToMiResult();
      v26 = dword_18039EB68;
      v21 = v25;
      if ( (unsigned int)dword_18039EB68 <= 2 )
        goto LABEL_17;
      LODWORD(pv) = v25;
      v27 = byte_1802F60A5;
      v30 = 1472;
    }
    v33 = "WspRunMethodAsJob";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v26,
      (_DWORD)v27,
      v18,
      v19,
      (__int64)&v33,
      (__int64)&v30,
      (__int64)&pv);
LABEL_17:
    if ( v21 == MI_RESULT_OK )
      goto LABEL_26;
    goto LABEL_18;
  }
  if ( (unsigned int)dword_18039EB68 > 2 )
  {
    LODWORD(pv) = v21;
    v30 = 1462;
    v33 = "WspRunMethodAsJob";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v22,
      (unsigned int)&dword_1802F5BB4,
      v23,
      v24,
      (__int64)&v33,
      (__int64)&v30,
      (__int64)&pv);
  }
LABEL_18:
  _WspDeleteJob((struct _WSP_ASYNC_METHOD_CONTEXT *)v20, 1);
LABEL_19:
  if ( v20 )
    _WSP_ASYNC_METHOD_CONTEXT::`scalar deleting destructor'((_WSP_ASYNC_METHOD_CONTEXT *)v20, v16);
  v26 = (int)TokenHandle;
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( ThreadpoolWork )
    CloseThreadpoolWork(ThreadpoolWork);
LABEL_26:
  if ( (unsigned int)dword_18039EB68 > 5 )
  {
    LODWORD(pv) = 1519;
    v33 = "WspRunMethodAsJob";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v26,
      (unsigned int)word_1802F624A,
      v18,
      v19,
      (__int64)&v33,
      (__int64)&pv);
  }
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x180016b40  push    rbp
0x180016b42  push    rbx
0x180016b43  push    rsi
0x180016b44  push    rdi
0x180016b45  push    r12
0x180016b47  push    r14
0x180016b49  push    r15
0x180016b4b  mov     rbp, rsp
0x180016b4e  sub     rsp, 60h
0x180016b52  mov     eax, cs:dword_18039EB68
0x180016b58  lea     r12, aWsprunmethodas_0; "WspRunMethodAsJob"
0x180016b5f  mov     r15, r9
0x180016b62  mov     ebx, r8d
0x180016b65  mov     rdi, rdx
0x180016b68  mov     r14, rcx
0x180016b6b  cmp     eax, 5
0x180016b6e  jbe     short loc_180016B99
0x180016b70  lea     rax, [rbp+var_20]
0x180016b74  mov     [rbp+var_20], 597h
0x180016b7b  mov     [rsp+60h+var_38], rax
0x180016b80  lea     rdx, byte_1802F5737
0x180016b87  lea     rax, [rbp+pv]
0x180016b8b  mov     [rbp+pv], r12
0x180016b8f  mov     [rsp+60h+var_40], rax
0x180016b94  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180016b99  mov     r9d, [rbp+arg_28]
0x180016b9d  lea     rax, [rbp+pv]
0x180016ba1  mov     [rsp+60h+var_30], rax
0x180016ba6  mov     r8d, ebx
0x180016ba9  mov     rax, [rbp+arg_38]
0x180016bad  mov     rdx, rdi
0x180016bb0  mov     [rsp+60h+var_38], rax
0x180016bb5  mov     rcx, r14
0x180016bb8  mov     eax, [rbp+arg_30]
0x180016bbb  xor     esi, esi
0x180016bbd  mov     dword ptr [rsp+60h+var_40], eax
0x180016bc1  mov     [rbp+pv], 0
0x180016bc9  mov     [rbp+TokenHandle], 0
0x180016bd1  call    ?_WspCreateJob@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEBGW4JOB_TYPE@SM_CONSTANTS@@W4WSP_SUBSYSTEM_TYPE@@W4WSP_OBJECT_TYPE@@1PEAPEAU_WSP_ASYNC_METHOD_CONTEXT@@@Z; _WspCreateJob(_MI_Context *,ushort const *,SM_CONSTANTS::JOB_TYPE,WSP_SUBSYSTEM_TYPE,WSP_OBJECT_TYPE,ushort const *,_WSP_ASYNC_METHOD_CONTEXT * *)
0x180016bd6  mov     rdi, [rbp+pv]
0x180016bda  mov     ebx, eax
0x180016bdc  test    eax, eax
0x180016bde  jz      short loc_180016C29
0x180016be0  mov     eax, cs:dword_18039EB68
0x180016be6  cmp     eax, 2
0x180016be9  jbe     loc_180016D72
0x180016bef  lea     rax, [rbp+var_20]
0x180016bf3  mov     [rbp+var_20], ebx
0x180016bf6  mov     [rsp+60h+var_30], rax
0x180016bfb  lea     rdx, word_1802F5A6A
0x180016c02  lea     rax, [rbp+pv]
0x180016c06  mov     dword ptr [rbp+pv], 5ACh
0x180016c0d  mov     [rsp+60h+var_38], rax
0x180016c12  lea     rax, [rbp+var_8]
0x180016c16  mov     [rsp+60h+var_40], rax
0x180016c1b  mov     [rbp+var_8], r12
0x180016c1f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180016c24  jmp     loc_180016D72
0x180016c29  mov     r8, [rbp+arg_40]; struct _MI_Instance *
0x180016c30  mov     rdx, rdi; struct _WSP_ASYNC_METHOD_CONTEXT *
0x180016c33  mov     rcx, r14; struct _MI_Context *
0x180016c36  call    ?_WspSetCreatedJob@@YA?AW4_MI_Result@@PEAU_MI_Context@@PEAU_WSP_ASYNC_METHOD_CONTEXT@@PEAU_MI_Instance@@@Z; _WspSetCreatedJob(_MI_Context *,_WSP_ASYNC_METHOD_CONTEXT *,_MI_Instance *)
0x180016c3b  mov     ebx, eax
0x180016c3d  test    eax, eax
0x180016c3f  jz      short loc_180016C8A
0x180016c41  mov     eax, cs:dword_18039EB68
0x180016c47  cmp     eax, 2
0x180016c4a  jbe     loc_180016D65
0x180016c50  lea     rax, [rbp+pv]
0x180016c54  mov     dword ptr [rbp+pv], ebx
0x180016c57  mov     [rsp+60h+var_30], rax
0x180016c5c  lea     rdx, dword_1802F5BB4
0x180016c63  lea     rax, [rbp+var_20]
0x180016c67  mov     [rbp+var_20], 5B6h
0x180016c6e  mov     [rsp+60h+var_38], rax
0x180016c73  lea     rax, [rbp+var_8]
0x180016c77  mov     [rsp+60h+var_40], rax
0x180016c7c  mov     [rbp+var_8], r12
0x180016c80  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180016c85  jmp     loc_180016D65
0x180016c8a  xor     r8d, r8d; pcbe
0x180016c8d  lea     rcx, _WspResumeMethodWorker; pfnwk
0x180016c94  mov     rdx, rdi; pv
0x180016c97  call    cs:__imp_CreateThreadpoolWork
0x180016c9e  nop     dword ptr [rax+rax+00h]
0x180016ca3  mov     rsi, rax
0x180016ca6  test    rax, rax
0x180016ca9  jnz     short loc_180016CD4
0x180016cab  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x180016cb0  mov     ecx, cs:dword_18039EB68
0x180016cb6  mov     ebx, eax
0x180016cb8  cmp     ecx, 2
0x180016cbb  jbe     loc_180016D61
0x180016cc1  mov     dword ptr [rbp+pv], eax
0x180016cc4  lea     rdx, byte_1802F60A5
0x180016ccb  mov     [rbp+var_20], 5C0h
0x180016cd2  jmp     short loc_180016D3D
0x180016cd4  call    cs:__imp_GetCurrentThread
0x180016cdb  nop     dword ptr [rax+rax+00h]
0x180016ce0  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180016ce4  xor     r8d, r8d; OpenAsSelf
0x180016ce7  mov     rcx, rax; ThreadHandle
0x180016cea  mov     edx, 2000Ch; DesiredAccess
0x180016cef  call    cs:__imp_OpenThreadToken
0x180016cf6  nop     dword ptr [rax+rax+00h]
0x180016cfb  test    eax, eax
0x180016cfd  jnz     loc_180016DAA
0x180016d03  call    cs:__imp_GetLastError
0x180016d0a  nop     dword ptr [rax+rax+00h]
0x180016d0f  cmp     eax, 3F0h
0x180016d14  jz      loc_180016DAA
0x180016d1a  call    ?GleToMiResult@@YA?AW4_MI_Result@@XZ; GleToMiResult(void)
0x180016d1f  mov     ebx, eax
0x180016d21  mov     eax, cs:dword_18039EB68
0x180016d27  cmp     eax, 2
0x180016d2a  jbe     short loc_180016D61
0x180016d2c  mov     dword ptr [rbp+pv], ebx
0x180016d2f  lea     rdx, byte_1802F619F
0x180016d36  mov     [rbp+var_20], 5CBh
0x180016d3d  lea     rax, [rbp+pv]
0x180016d41  mov     [rbp+var_8], r12
0x180016d45  mov     [rsp+60h+var_30], rax
0x180016d4a  lea     rax, [rbp+var_20]
0x180016d4e  mov     [rsp+60h+var_38], rax
0x180016d53  lea     rax, [rbp+var_8]
0x180016d57  mov     [rsp+60h+var_40], rax
0x180016d5c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180016d61  test    ebx, ebx
0x180016d63  jz      short loc_180016DD9
0x180016d65  mov     edx, 1; int
0x180016d6a  mov     rcx, rdi; struct _WSP_ASYNC_METHOD_CONTEXT *
0x180016d6d  call    ?_WspDeleteJob@@YAXPEAU_WSP_ASYNC_METHOD_CONTEXT@@H@Z; _WspDeleteJob(_WSP_ASYNC_METHOD_CONTEXT *,int)
0x180016d72  test    rdi, rdi
0x180016d75  jz      short loc_180016D7F
0x180016d77  mov     rcx, rdi; this
0x180016d7a  call    ??_G_WSP_ASYNC_METHOD_CONTEXT@@QEAAPEAXI@Z; _WSP_ASYNC_METHOD_CONTEXT::`scalar deleting destructor'(uint)
0x180016d7f  mov     rcx, [rbp+TokenHandle]; hObject
0x180016d83  test    rcx, rcx
0x180016d86  jz      short loc_180016D94
0x180016d88  call    cs:__imp_CloseHandle
0x180016d8f  nop     dword ptr [rax+rax+00h]
0x180016d94  test    rsi, rsi
0x180016d97  jz      short loc_180016DD9
0x180016d99  mov     rcx, rsi; pwk
0x180016d9c  call    cs:__imp_CloseThreadpoolWork
0x180016da3  nop     dword ptr [rax+rax+00h]
0x180016da8  jmp     short loc_180016DD9
0x180016daa  mov     rax, [rbp+arg_48]
0x180016db1  mov     rcx, rsi; pwk
0x180016db4  mov     dword ptr [rax], 1000h
0x180016dba  mov     rax, [rbp+TokenHandle]
0x180016dbe  mov     [rdi], rax
0x180016dc1  mov     rax, [rbp+arg_20]
0x180016dc5  mov     [rdi+8], r15
0x180016dc9  mov     [rdi+10h], rax
0x180016dcd  call    cs:__imp_SubmitThreadpoolWork
0x180016dd4  nop     dword ptr [rax+rax+00h]
0x180016dd9  mov     eax, cs:dword_18039EB68
0x180016ddf  cmp     eax, 5
0x180016de2  jbe     short loc_180016E0D
0x180016de4  lea     rax, [rbp+pv]
0x180016de8  mov     dword ptr [rbp+pv], 5EFh
0x180016def  mov     [rsp+60h+var_38], rax
0x180016df4  lea     rdx, word_1802F624A
0x180016dfb  lea     rax, [rbp+var_8]
0x180016dff  mov     [rbp+var_8], r12
0x180016e03  mov     [rsp+60h+var_40], rax
0x180016e08  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180016e0d  mov     eax, ebx
0x180016e0f  add     rsp, 60h
0x180016e13  pop     r15
0x180016e15  pop     r14
0x180016e17  pop     r12
0x180016e19  pop     rdi
0x180016e1a  pop     rsi
0x180016e1b  pop     rbx
0x180016e1c  pop     rbp
0x180016e1d  retn
```
