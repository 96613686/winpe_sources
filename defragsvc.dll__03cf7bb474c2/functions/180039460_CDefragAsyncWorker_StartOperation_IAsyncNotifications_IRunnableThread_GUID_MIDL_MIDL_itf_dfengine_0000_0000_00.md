# CDefragAsyncWorker::StartOperation(IAsyncNotifications *,IRunnableThread *,_GUID *,__MIDL___MIDL_itf_dfengine_0000_0000_0001,ulong,ulong,_GUID)

- ea: `0x180039460`
- end: `0x180039783`
- name: `?StartOperation@CDefragAsyncWorker@@UEAAJPEAUIAsyncNotifications@@PEAUIRunnableThread@@PEAU_GUID@@W4__MIDL___MIDL_itf_dfengine_0000_0000_0001@@KKU4@@Z`
- size: `803`
- prototype: `int __high(struct IAsyncNotifications *, struct IRunnableThread *, struct _GUID *, enum __MIDL___MIDL_itf_dfengine_0000_0000_0001, unsigned int, unsigned int, struct _GUID)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180006400`
- `0x18000ad50`
- `0x180012c6c`
- `0x18001a630`
- `0x180038f58`
- `0x180039460`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003975b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003975b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039574`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180039574`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180039699`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180039699`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800396b3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800396b3`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDefragAsyncWorker::StartOperation(
        __int64 a1,
        struct IUnknown *a2,
        __int64 a3,
        _OWORD *a4,
        int a5,
        unsigned int a6,
        unsigned int a7,
        _OWORD *a8)
{
  int v12; // r15d
  int v13; // r14d
  __int64 v14; // r12
  __int16 v15; // ax
  __int64 (__fastcall ***v16)(_QWORD, GUID *, LPVOID *); // rax
  __int16 v17; // ax
  __int16 v18; // ax
  __int64 v19; // rcx
  _OWORD *v20; // rax
  int v21; // eax
  __int64 v22; // rcx
  HANDLE v23; // rsi
  __int64 v24; // r8
  __int64 v25; // r9
  char *v26; // rcx
  char *v27; // rdx
  _BYTE *v28; // rax
  unsigned int v29; // ebx
  DWORD ThreadId; // [rsp+30h] [rbp-51h] BYREF
  LPVOID lpParameter; // [rsp+38h] [rbp-49h] BYREF
  int LastFailureAsHRESULT; // [rsp+40h] [rbp-41h] BYREF
  __int16 v34; // [rsp+44h] [rbp-3Dh]
  __int16 v35; // [rsp+46h] [rbp-3Bh]

  CSxFunctionTracer::CSxFunctionTracer(
    (CSxFunctionTracer *)&LastFailureAsHRESULT,
    "CDefragAsyncWorker::StartOperation",
    288,
    1);
  v12 = 0;
  v13 = 0;
  ThreadId = 0;
  lpParameter = 0;
  v14 = 16;
  v15 = 295;
  if ( !a2 || (v34 = 295, v15 = 296, !a3) )
  {
    LastFailureAsHRESULT = -2147024809;
    v35 = v15;
    goto LABEL_31;
  }
  v34 = 296;
  if ( a6 > a7 )
  {
    LastFailureAsHRESULT = -2147024809;
    v35 = 297;
    v12 = 0;
    goto LABEL_31;
  }
  LastFailureAsHRESULT = 0;
  v34 = 297;
  v16 = (__int64 (__fastcall ***)(_QWORD, GUID *, LPVOID *))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 256LL))(a1);
  LastFailureAsHRESULT = (**v16)(v16, &IID_IDefragAsyncWorker, &lpParameter);
  v17 = 302;
  if ( LastFailureAsHRESULT < 0 )
    goto LABEL_7;
  v34 = 302;
  v17 = 303;
  if ( !lpParameter )
  {
    LastFailureAsHRESULT = -2147024809;
LABEL_7:
    v35 = v17;
    v12 = v13;
    goto LABEL_31;
  }
  LastFailureAsHRESULT = 0;
  v34 = 303;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
  v18 = 313;
  if ( *(_DWORD *)(a1 + 84) == 3 )
  {
    LastFailureAsHRESULT = -1996488701;
LABEL_12:
    v35 = v18;
    goto LABEL_30;
  }
  v34 = 313;
  v18 = 316;
  if ( *(_DWORD *)(a1 + 84) )
  {
    LastFailureAsHRESULT = -1996488704;
    goto LABEL_12;
  }
  LastFailureAsHRESULT = 0;
  v34 = 316;
  *(_OWORD *)(a1 + 144) = *a8;
  *(_DWORD *)(a1 + 84) = 1;
  *(_DWORD *)(a1 + 88) = a5;
  *(_DWORD *)(a1 + 100) = a6;
  *(_DWORD *)(a1 + 92) = a6;
  *(_DWORD *)(a1 + 96) = a7;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a3 + 8LL))(a3);
  v19 = *(_QWORD *)(a1 + 136);
  if ( v19 )
  {
    *(_QWORD *)(a1 + 136) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
  *(_QWORD *)(a1 + 136) = a3;
  *(_DWORD *)(a1 + 112) = 0;
  *(_DWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 168) = 0;
  v20 = (_OWORD *)(a1 + 176);
  if ( a4 )
  {
    *v20 = *a4;
    v21 = 1;
  }
  else
  {
    if ( a1 != -176 )
    {
      v22 = 16;
      do
      {
        *(_BYTE *)v20 = 0;
        v20 = (_OWORD *)((char *)v20 + 1);
        --v22;
      }
      while ( v22 );
    }
    v21 = 0;
  }
  *(_DWORD *)(a1 + 192) = v21;
  if ( *(struct IUnknown **)(a1 + 120) != a2 )
    ATL::AtlComPtrAssign((struct IUnknown **)(a1 + 120), a2);
  v23 = CreateThread(0, 0x8000u, (LPTHREAD_START_ROUTINE)CDefragAsyncWorker::_ThreadFunction, lpParameter, 0, &ThreadId);
  v26 = *(char **)(a1 + 160);
  v27 = v26 - 1;
  if ( (unsigned __int64)(v26 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v26);
  *(_QWORD *)(a1 + 160) = v23;
  if ( (((unsigned __int64)v23 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    v13 = 1;
    LastFailureAsHRESULT = GetLastFailureAsHRESULT(v26, v27, v24, v25);
    v17 = 349;
    goto LABEL_7;
  }
  LastFailureAsHRESULT = 0;
  v34 = 349;
  lpParameter = 0;
LABEL_30:
  v12 = 1;
LABEL_31:
  ((void (__fastcall *)(struct IUnknown *))a2->lpVtbl->Release)(a2);
  if ( v13 )
  {
    *(_DWORD *)(a1 + 84) = 0;
    ATL::CComPtrBase<IContextCallback>::Release(a1 + 120);
    v28 = (_BYTE *)(a1 + 176);
    if ( a1 != -176 )
    {
      do
      {
        *v28++ = 0;
        --v14;
      }
      while ( v14 );
    }
    *(_DWORD *)(a1 + 192) = 0;
  }
  if ( lpParameter )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)lpParameter + 16LL))(lpParameter);
  if ( v12 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 40));
  v29 = LastFailureAsHRESULT;
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&LastFailureAsHRESULT);
  return v29;
}

```

## disassembly

```asm
0x180039460  push    rbp
0x180039462  push    rbx
0x180039463  push    rsi
0x180039464  push    rdi
0x180039465  push    r12
0x180039467  push    r13
0x180039469  push    r14
0x18003946b  push    r15
0x18003946d  lea     rbp, [rsp-7]
0x180039472  sub     rsp, 88h
0x180039479  mov     r13, r9
0x18003947c  mov     rsi, r8
0x18003947f  mov     rdi, rdx
0x180039482  mov     rbx, rcx
0x180039485  mov     r9d, 1; unsigned __int16
0x18003948b  mov     r8d, 120h; unsigned __int16
0x180039491  lea     rdx, aCdefragasyncwo_1; "CDefragAsyncWorker::StartOperation"
0x180039498  lea     rcx, [rbp+3Fh+var_80]; this
0x18003949c  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x1800394a1  nop
0x1800394a2  xor     ecx, ecx
0x1800394a4  mov     r15d, ecx
0x1800394a7  mov     r14d, ecx
0x1800394aa  mov     [rbp+3Fh+ThreadId], ecx
0x1800394ad  mov     [rbp+3Fh+lpParameter], rcx
0x1800394b1  lea     r12d, [rcx+10h]
0x1800394b5  mov     eax, 127h
0x1800394ba  test    rdi, rdi
0x1800394bd  jnz     short loc_1800394CF
0x1800394bf  mov     [rbp+3Fh+var_80], 80070057h
0x1800394c6  mov     [rbp+3Fh+var_7A], ax
0x1800394ca  jmp     loc_1800396FD
0x1800394cf  mov     [rbp+3Fh+var_7C], ax
0x1800394d3  mov     eax, 128h
0x1800394d8  test    rsi, rsi
0x1800394db  jz      short loc_1800394BF
0x1800394dd  mov     [rbp+3Fh+var_7C], ax
0x1800394e1  mov     r15d, [rbp+3Fh+arg_28]
0x1800394e5  mov     eax, 129h
0x1800394ea  cmp     r15d, [rbp+3Fh+arg_30]
0x1800394ee  jbe     short loc_180039503
0x1800394f0  mov     [rbp+3Fh+var_80], 80070057h
0x1800394f7  mov     [rbp+3Fh+var_7A], ax
0x1800394fb  mov     r15d, ecx
0x1800394fe  jmp     loc_1800396FD
0x180039503  mov     [rbp+3Fh+var_80], ecx
0x180039506  mov     [rbp+3Fh+var_7C], ax
0x18003950a  mov     rax, [rbx]
0x18003950d  mov     rcx, rbx
0x180039510  mov     rax, [rax+100h]
0x180039517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003951c  mov     r9, rax
0x18003951f  mov     rcx, [rax]
0x180039522  mov     rax, [rcx]
0x180039525  lea     r8, [rbp+3Fh+lpParameter]
0x180039529  lea     rdx, IID_IDefragAsyncWorker
0x180039530  mov     rcx, r9
0x180039533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039538  mov     [rbp+3Fh+var_80], eax
0x18003953b  test    eax, eax
0x18003953d  mov     eax, 12Eh
0x180039542  jns     short loc_180039550
0x180039544  mov     [rbp+3Fh+var_7A], ax
0x180039548  mov     r15d, r14d
0x18003954b  jmp     loc_1800396FD
0x180039550  mov     [rbp+3Fh+var_7C], ax
0x180039554  mov     eax, 12Fh
0x180039559  cmp     [rbp+3Fh+lpParameter], r14
0x18003955d  jnz     short loc_180039568
0x18003955f  mov     [rbp+3Fh+var_80], 80070057h
0x180039566  jmp     short loc_180039544
0x180039568  mov     [rbp+3Fh+var_80], r14d
0x18003956c  mov     [rbp+3Fh+var_7C], ax
0x180039570  lea     rcx, [rbx+28h]; lpCriticalSection
0x180039574  call    cs:__imp_EnterCriticalSection
0x18003957a  mov     [rbp+3Fh+arg_8], 1
0x180039581  mov     eax, 139h
0x180039586  cmp     dword ptr [rbx+54h], 3
0x18003958a  jnz     short loc_18003959C
0x18003958c  mov     [rbp+3Fh+var_80], 89000003h
0x180039593  mov     [rbp+3Fh+var_7A], ax
0x180039597  jmp     loc_1800396F9
0x18003959c  mov     [rbp+3Fh+var_7C], ax
0x1800395a0  mov     eax, 13Ch
0x1800395a5  cmp     [rbx+54h], r14d
0x1800395a9  jz      short loc_1800395B4
0x1800395ab  mov     [rbp+3Fh+var_80], 89000000h
0x1800395b2  jmp     short loc_180039593
0x1800395b4  mov     [rbp+3Fh+var_80], r14d
0x1800395b8  mov     [rbp+3Fh+var_7C], ax
0x1800395bc  mov     rax, [rbp+3Fh+arg_38]
0x1800395c3  movups  xmm0, xmmword ptr [rax]
0x1800395c6  movdqu  xmmword ptr [rbx+90h], xmm0
0x1800395ce  mov     dword ptr [rbx+54h], 1
0x1800395d5  mov     eax, [rbp+3Fh+arg_20]
0x1800395d8  mov     [rbx+58h], eax
0x1800395db  mov     [rbx+64h], r15d
0x1800395df  mov     [rbx+5Ch], r15d
0x1800395e3  mov     eax, [rbp+3Fh+arg_30]
0x1800395e6  mov     [rbx+60h], eax
0x1800395e9  mov     rax, [rsi]
0x1800395ec  mov     rcx, rsi
0x1800395ef  mov     rax, [rax+8]
0x1800395f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800395f8  nop
0x1800395f9  mov     rcx, [rbx+88h]
0x180039600  test    rcx, rcx
0x180039603  jz      short loc_180039619
0x180039605  mov     [rbx+88h], r14
0x18003960c  mov     rax, [rcx]
0x18003960f  mov     rax, [rax+10h]
0x180039613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039618  nop
0x180039619  mov     [rbx+88h], rsi
0x180039620  mov     [rbx+70h], r14d
0x180039624  mov     [rbx+68h], r14d
0x180039628  mov     [rbx+0A8h], r14
0x18003962f  lea     rax, [rbx+0B0h]
0x180039636  test    r13, r13
0x180039639  jz      short loc_18003964B
0x18003963b  movups  xmm0, xmmword ptr [r13+0]
0x180039640  movdqu  xmmword ptr [rax], xmm0
0x180039644  mov     eax, 1
0x180039649  jmp     short loc_180039662
0x18003964b  test    rax, rax
0x18003964e  jz      short loc_18003965F
0x180039650  mov     rcx, r12
0x180039653  mov     [rax], r14b
0x180039656  inc     rax
0x180039659  sub     rcx, 1
0x18003965d  jnz     short loc_180039653
0x18003965f  mov     eax, r14d
0x180039662  mov     [rbx+0C0h], eax
0x180039668  lea     rcx, [rbx+78h]; struct IUnknown **
0x18003966c  cmp     [rcx], rdi
0x18003966f  jz      short loc_180039679
0x180039671  mov     rdx, rdi; struct IUnknown *
0x180039674  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x180039679  lea     rax, [rbp+3Fh+ThreadId]
0x18003967d  mov     [rsp+0C0h+lpThreadId], rax; lpThreadId
0x180039682  mov     [rsp+0C0h+dwCreationFlags], r14d; dwCreationFlags
0x180039687  mov     r9, [rbp+3Fh+lpParameter]; lpParameter
0x18003968b  lea     r8, ?_ThreadFunction@CDefragAsyncWorker@@CAKPEAX@Z; lpStartAddress
0x180039692  mov     edx, 8000h; dwStackSize
0x180039697  xor     ecx, ecx; lpThreadAttributes
0x180039699  call    cs:__imp_CreateThread
0x18003969f  mov     rsi, rax
0x1800396a2  mov     rcx, [rbx+0A0h]; hObject
0x1800396a9  lea     rdx, [rcx-1]
0x1800396ad  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800396b1  ja      short loc_1800396B9
0x1800396b3  call    cs:__imp_CloseHandle
0x1800396b9  mov     [rbx+0A0h], rsi
0x1800396c0  lea     rax, [rsi+1]
0x1800396c4  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800396ca  jnz     short loc_1800396E4
0x1800396cc  mov     r14d, 1
0x1800396d2  call    GetLastFailureAsHRESULT
0x1800396d7  mov     [rbp+3Fh+var_80], eax
0x1800396da  mov     eax, 15Dh
0x1800396df  jmp     loc_180039544
0x1800396e4  mov     [rbp+3Fh+var_80], r14d
0x1800396e8  mov     eax, 15Dh
0x1800396ed  mov     [rbp+3Fh+var_7C], ax
0x1800396f1  mov     [rbp+3Fh+lpParameter], 0
0x1800396f9  mov     r15d, [rbp+3Fh+arg_8]
0x1800396fd  mov     rax, [rdi]
0x180039700  mov     rcx, rdi
0x180039703  mov     rax, [rax+10h]
0x180039707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003970c  xor     edi, edi
0x18003970e  test    r14d, r14d
0x180039711  jz      short loc_18003973D
0x180039713  mov     [rbx+54h], edi
0x180039716  lea     rcx, [rbx+78h]
0x18003971a  call    ?Release@?$CComPtrBase@UIContextCallback@@@ATL@@QEAAXXZ; ATL::CComPtrBase<IContextCallback>::Release(void)
0x18003971f  lea     rax, [rbx+0B0h]
0x180039726  test    rax, rax
0x180039729  jz      short loc_180039737
0x18003972b  mov     [rax], dil
0x18003972e  inc     rax
0x180039731  sub     r12, 1
0x180039735  jnz     short loc_18003972B
0x180039737  mov     [rbx+0C0h], edi
0x18003973d  mov     rcx, [rbp+3Fh+lpParameter]
0x180039741  test    rcx, rcx
0x180039744  jz      short loc_180039752
0x180039746  mov     rax, [rcx]
0x180039749  mov     rax, [rax+10h]
0x18003974d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039752  test    r15d, r15d
0x180039755  jz      short loc_180039761
0x180039757  lea     rcx, [rbx+28h]; lpCriticalSection
0x18003975b  call    cs:__imp_LeaveCriticalSection
0x180039761  mov     ebx, [rbp+3Fh+var_80]
0x180039764  lea     rcx, [rbp+3Fh+var_80]; this
0x180039768  call    ??1CSxFunctionTracer@@QEAA@XZ; CSxFunctionTracer::~CSxFunctionTracer(void)
0x18003976d  mov     eax, ebx
0x18003976f  add     rsp, 88h
0x180039776  pop     r15
0x180039778  pop     r14
0x18003977a  pop     r13
0x18003977c  pop     r12
0x18003977e  pop     rdi
0x18003977f  pop     rsi
0x180039780  pop     rbx
0x180039781  pop     rbp
0x180039782  retn
```
