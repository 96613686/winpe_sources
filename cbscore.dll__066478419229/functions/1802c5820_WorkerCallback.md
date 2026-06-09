# WorkerCallback

- ea: `0x1802c5820`
- end: `0x1802c5b82`
- name: `WorkerCallback`
- size: `866`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x1802c5b90`

## callees

- `0x180048c24`
- `0x180048c80`
- `0x180064c6c`
- `0x1800aa1a4`
- `0x1800eb920`
- `0x1800ef360`
- `0x1802bd42c`
- `0x1802c5820`
- `0x1802c5c40`

## import_xrefs

- `ntdll!NtSetIoCompletion` at `0x1802c58e6`
- `ntdll!NtSetIoCompletion` at `0x1802c5990`
- `ntdll!NtSetIoCompletion` at `0x1802c5af7`
- `ntdll!NtSetIoCompletion` at `0x1802c58e6`
- `ntdll!NtSetIoCompletion` at `0x1802c5990`
- `ntdll!NtSetIoCompletion` at `0x1802c5af7`
- `ntdll!NtRemoveIoCompletion` at `0x1802c59d1`
- `ntdll!NtRemoveIoCompletion` at `0x1802c59d1`

## string_xrefs

- `0x1802c5a8f`: `::NtSetIoCompletion( Context->DispatcherPort, reinterpret_cast<PVOID>(DispatcherCompletionKey::WorkCompleted), Overlapped, ((NTSTATUS)0x00000000L), 0)`
- `0x1802c5a0b`: `::NtRemoveIoCompletion( Context->WorkerPort, reinterpret_cast<PVOID*>(&CompletionKey), reinterpret_cast<PVOID*>(&Overlapped), &IoSb, nullptr)`
- `0x1802c5b29`: `::NtSetIoCompletion( Context->WorkerPort, reinterpret_cast<PVOID>(WorkerCompletionKey::Terminate), nullptr, ((NTSTATUS)0x00000000L), 0)`
- `0x1802c591b`: `::NtSetIoCompletion( Context->DispatcherPort, reinterpret_cast<PVOID>(DispatcherCompletionKey::GetWork), nullptr, ((NTSTATUS)0x00000000L), 0)`

## pseudocode

```c
__int64 __fastcall WorkerCallback(__int64 a1)
{
  HANDLE v2; // rcx
  NTSTATUS v3; // eax
  const char *v4; // rcx
  __int64 Status; // r8
  int v6; // eax
  const char **v7; // rdx
  unsigned int v8; // ebx
  const char *v10; // [rsp+30h] [rbp-D0h] BYREF
  const char *v11; // [rsp+38h] [rbp-C8h]
  __int64 v12; // [rsp+40h] [rbp-C0h]
  const char *v13; // [rsp+48h] [rbp-B8h]
  const char *v14; // [rsp+50h] [rbp-B0h] BYREF
  const char *v15; // [rsp+58h] [rbp-A8h]
  __int64 v16; // [rsp+60h] [rbp-A0h]
  const char *v17; // [rsp+68h] [rbp-98h]
  char v18[8]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE *v19; // [rsp+78h] [rbp-88h]
  _BYTE *v20; // [rsp+80h] [rbp-80h]
  _BYTE *v21; // [rsp+88h] [rbp-78h]
  _QWORD v22[4]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v23[4]; // [rsp+B0h] [rbp-50h] BYREF
  PVOID CompletionContext; // [rsp+D0h] [rbp-30h] BYREF
  int v25; // [rsp+D8h] [rbp-28h] BYREF
  PVOID CompletionKey; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v27[8]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v28; // [rsp+F0h] [rbp-10h]
  __int64 v29; // [rsp+F8h] [rbp-8h]
  __int64 v30; // [rsp+100h] [rbp+0h]
  __int64 v31; // [rsp+108h] [rbp+8h]
  _BYTE v32[8]; // [rsp+110h] [rbp+10h] BYREF
  __int64 v33; // [rsp+118h] [rbp+18h]
  __int64 v34; // [rsp+120h] [rbp+20h]
  __int64 v35; // [rsp+128h] [rbp+28h]
  __int64 v36; // [rsp+130h] [rbp+30h]
  _BYTE v37[8]; // [rsp+138h] [rbp+38h] BYREF
  __int64 v38; // [rsp+140h] [rbp+40h]
  __int64 v39; // [rsp+148h] [rbp+48h]
  __int64 v40; // [rsp+150h] [rbp+50h]
  __int64 v41; // [rsp+158h] [rbp+58h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+160h] [rbp+60h] BYREF

  v27[0] = 0;
  v30 = 0;
  v31 = 0;
  v28 = 0;
  v29 = 0;
  v35 = 0;
  v36 = 0;
  v32[0] = 0;
  v33 = 0;
  v34 = 0;
  v40 = 0;
  v41 = 0;
  v37[0] = 0;
  v38 = 0;
  v25 = 0;
  v39 = 0;
  Windows::Rtl::StopWatch::Start((Windows::Rtl::StopWatch *)v37);
  v2 = *(HANDLE *)a1;
  v19 = v27;
  v18[0] = 1;
  v20 = v32;
  v21 = v37;
  v3 = NtSetIoCompletion(v2, 0, 0, 0, 0);
  if ( v3 >= 0 )
  {
    while ( 1 )
    {
      CompletionContext = 0;
      CompletionKey = 0;
      IoStatusBlock = 0;
      Windows::Rtl::StopWatch::Start((Windows::Rtl::StopWatch *)v27);
      v3 = NtRemoveIoCompletion(*(HANDLE *)(a1 + 8), &CompletionKey, &CompletionContext, &IoStatusBlock, 0);
      if ( v3 < 0 )
      {
        v16 = 4731;
        v14 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
        v7 = &v14;
        v15 = "WorkerCallback";
        v17 = "::NtRemoveIoCompletion( Context->WorkerPort, reinterpret_cast<PVOID*>(&CompletionKey), reinterpret_cast<PV"
              "OID*>(&Overlapped), &IoSb, nullptr)";
        goto LABEL_10;
      }
      Windows::Rtl::StopWatch::Stop((Windows::Rtl::StopWatch *)v27);
      Status = (unsigned int)IoStatusBlock.Status;
      if ( IoStatusBlock.Status < 0 )
      {
        v16 = 4736;
        v14 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
        v17 = "IoSb.Status";
        v15 = "WorkerCallback";
        v7 = &v14;
        goto LABEL_11;
      }
      if ( (_DWORD)CompletionKey )
        break;
      Windows::Rtl::StopWatch::Start((Windows::Rtl::StopWatch *)v32);
      v6 = WorkerExecuteOperation((OperationContext *)CompletionContext);
      if ( v6 < 0 )
        goto LABEL_12;
      Windows::Rtl::StopWatch::Stop((Windows::Rtl::StopWatch *)v32);
      if ( *((int *)CompletionContext + 28) < 0 )
      {
        INTERNAL_ERROR_ACTION(-1073741595);
        JUMPOUT(0x1802C5B81LL);
      }
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 40));
      v3 = NtSetIoCompletion(*(HANDLE *)a1, (PVOID)4, CompletionContext, 0, 0);
      if ( v3 < 0 )
      {
        v12 = 4775;
        v10 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
        v11 = "WorkerCallback";
        v4 = "::NtSetIoCompletion( Context->DispatcherPort, reinterpret_cast<PVOID>(DispatcherCompletionKey::WorkComplete"
             "d), Overlapped, ((NTSTATUS)0x00000000L), 0)";
        goto LABEL_15;
      }
    }
    if ( (_DWORD)CompletionKey != 1 )
    {
      if ( (_DWORD)CompletionKey != 2 )
      {
        v22[2] = 4741;
        v22[0] = "onecore\\base\\wcp\\poq\\poqsil.cpp";
        v7 = (const char **)v22;
        v22[3] = 0;
        v22[1] = "WorkerCallback";
        Status = 3221225485LL;
        goto LABEL_11;
      }
      v3 = NtSetIoCompletion(*(HANDLE *)(a1 + 8), (PVOID)2, 0, 0, 0);
      if ( v3 < 0 )
      {
        v23[2] = 4752;
        v23[0] = "onecore\\base\\wcp\\poq\\poqsil.cpp";
        v7 = (const char **)v23;
        v23[1] = "WorkerCallback";
        v23[3] = "::NtSetIoCompletion( Context->WorkerPort, reinterpret_cast<PVOID>(WorkerCompletionKey::Terminate), null"
                 "ptr, ((NTSTATUS)0x00000000L), 0)";
        goto LABEL_10;
      }
    }
    v8 = 0;
  }
  else
  {
    v12 = 4716;
    v10 = "onecore\\base\\wcp\\poq\\poqsil.cpp";
    v11 = "WorkerCallback";
    v4 = "::NtSetIoCompletion( Context->DispatcherPort, reinterpret_cast<PVOID>(DispatcherCompletionKey::GetWork), nullpt"
         "r, ((NTSTATUS)0x00000000L), 0)";
LABEL_15:
    v13 = v4;
    v7 = &v10;
LABEL_10:
    Status = (unsigned int)v3;
LABEL_11:
    v6 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
           &v25,
           v7,
           Status);
LABEL_12:
    v8 = v6;
  }
  Windows::Detail::OnBlockExitImpl__WorkerCallback_::_5_::_lambda_1___::_OnBlockExitImpl__WorkerCallback_::_5_::_lambda_1___(v18);
  Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v37);
  Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v32);
  Windows::Rtl::StopWatch::~StopWatch((Windows::Rtl::StopWatch *)v27);
  return v8;
}

```

## disassembly

```asm
0x1802c5820  mov     [rsp-8+arg_8], rbx
0x1802c5825  mov     [rsp-8+arg_10], rdi
0x1802c582a  push    rbp
0x1802c582b  lea     rbp, [rsp-80h]
0x1802c5830  sub     rsp, 180h
0x1802c5837  mov     rax, cs:__security_cookie
0x1802c583e  xor     rax, rsp
0x1802c5841  mov     [rbp+80h+var_10], rax
0x1802c5845  xor     edi, edi
0x1802c5847  xor     eax, eax
0x1802c5849  mov     [rbp+80h+var_98], dil
0x1802c584d  mov     rbx, rcx
0x1802c5850  mov     [rbp+80h+var_88], rax
0x1802c5854  lea     rcx, [rbp+80h+var_48]; this
0x1802c5858  mov     [rbp+80h+var_90], rdi
0x1802c585c  mov     [rbp+80h+var_98], dil
0x1802c5860  mov     [rbp+80h+var_80], rax
0x1802c5864  mov     [rbp+80h+var_78], rdi
0x1802c5868  mov     [rbp+80h+var_70], dil
0x1802c586c  mov     [rbp+80h+var_90], rdi
0x1802c5870  mov     [rbp+80h+var_88], rdi
0x1802c5874  mov     [rbp+80h+var_60], rax
0x1802c5878  mov     [rbp+80h+var_68], rdi
0x1802c587c  mov     [rbp+80h+var_58], rax
0x1802c5880  mov     [rbp+80h+var_50], rdi
0x1802c5884  mov     [rbp+80h+var_70], dil
0x1802c5888  mov     [rbp+80h+var_48], dil
0x1802c588c  mov     [rbp+80h+var_68], rdi
0x1802c5890  mov     [rbp+80h+var_60], rdi
0x1802c5894  mov     [rbp+80h+var_38], rax
0x1802c5898  mov     [rbp+80h+var_40], rdi
0x1802c589c  mov     [rbp+80h+var_30], rax
0x1802c58a0  mov     [rbp+80h+var_28], rdi
0x1802c58a4  mov     [rbp+80h+var_48], dil
0x1802c58a8  mov     [rbp+80h+var_40], rdi
0x1802c58ac  mov     [rbp+80h+var_A8], edi
0x1802c58af  mov     [rbp+80h+var_38], rdi
0x1802c58b3  call    ?Start@StopWatch@Rtl@Windows@@QEAAXXZ; Windows::Rtl::StopWatch::Start(void)
0x1802c58b8  mov     rcx, [rbx]; IoCompletionPortHandle
0x1802c58bb  lea     rax, [rbp+80h+var_98]
0x1802c58bf  mov     [rsp+180h+var_108], rax
0x1802c58c4  xor     r9d, r9d; CompletionStatus
0x1802c58c7  lea     rax, [rbp+80h+var_70]
0x1802c58cb  mov     [rsp+180h+var_110], 1
0x1802c58d0  mov     [rbp+80h+var_100], rax
0x1802c58d4  xor     r8d, r8d; CompletionContext
0x1802c58d7  lea     rax, [rbp+80h+var_48]
0x1802c58db  mov     qword ptr [rsp+180h+CompletionInformation], rdi; CompletionInformation
0x1802c58e0  xor     edx, edx; CompletionKey
0x1802c58e2  mov     [rbp+80h+var_F8], rax
0x1802c58e6  call    cs:__imp_NtSetIoCompletion
0x1802c58ed  nop     dword ptr [rax+rax+00h]
0x1802c58f2  test    eax, eax
0x1802c58f4  jns     loc_1802C59A4
0x1802c58fa  lea     rcx, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c5901  mov     [rsp+180h+var_140], 126Ch
0x1802c590a  mov     [rsp+180h+var_150], rcx
0x1802c590f  lea     rcx, aWorkercallback; "WorkerCallback"
0x1802c5916  mov     [rsp+180h+var_148], rcx
0x1802c591b  lea     rcx, aNtsetiocomplet; "::NtSetIoCompletion( Context->Dispatche"...
0x1802c5922  jmp     loc_1802C5A96
0x1802c5927  lea     rcx, [rbp+80h+var_98]; this
0x1802c592b  call    ?Stop@StopWatch@Rtl@Windows@@QEAAAEAV123@XZ; Windows::Rtl::StopWatch::Stop(void)
0x1802c5930  mov     r8d, dword ptr [rbp+80h+IoStatusBlock]
0x1802c5934  test    r8d, r8d
0x1802c5937  js      loc_1802C5B40
0x1802c593d  mov     rcx, [rbp+80h+CompletionKey]
0x1802c5941  test    ecx, ecx
0x1802c5943  jnz     loc_1802C5AA5
0x1802c5949  lea     rcx, [rbp+80h+var_70]; this
0x1802c594d  call    ?Start@StopWatch@Rtl@Windows@@QEAAXXZ; Windows::Rtl::StopWatch::Start(void)
0x1802c5952  mov     rcx, [rbp+80h+CompletionContext]; this
0x1802c5956  call    WorkerExecuteOperation
0x1802c595b  test    eax, eax
0x1802c595d  js      loc_1802C5A23
0x1802c5963  lea     rcx, [rbp+80h+var_70]; this
0x1802c5967  call    ?Stop@StopWatch@Rtl@Windows@@QEAAAEAV123@XZ; Windows::Rtl::StopWatch::Stop(void)
0x1802c596c  mov     rax, [rbp+80h+CompletionContext]
0x1802c5970  cmp     [rax+70h], edi
0x1802c5973  jl      loc_1802C5B77
0x1802c5979  lock inc dword ptr [rbx+28h]
0x1802c597d  mov     r8, [rbp+80h+CompletionContext]; CompletionContext
0x1802c5981  xor     r9d, r9d; CompletionStatus
0x1802c5984  mov     rcx, [rbx]; IoCompletionPortHandle
0x1802c5987  mov     qword ptr [rsp+180h+CompletionInformation], rdi; CompletionInformation
0x1802c598c  lea     edx, [r9+4]; CompletionKey
0x1802c5990  call    cs:__imp_NtSetIoCompletion
0x1802c5997  nop     dword ptr [rax+rax+00h]
0x1802c599c  test    eax, eax
0x1802c599e  js      loc_1802C5A6E
0x1802c59a4  xorps   xmm0, xmm0
0x1802c59a7  mov     [rbp+80h+CompletionContext], rdi
0x1802c59ab  lea     rcx, [rbp+80h+var_98]; this
0x1802c59af  mov     [rbp+80h+CompletionKey], rdi
0x1802c59b3  movups  xmmword ptr [rbp+80h+IoStatusBlock], xmm0
0x1802c59b7  call    ?Start@StopWatch@Rtl@Windows@@QEAAXXZ; Windows::Rtl::StopWatch::Start(void)
0x1802c59bc  mov     rcx, [rbx+8]; IoCompletionHandle
0x1802c59c0  lea     r9, [rbp+80h+IoStatusBlock]; IoStatusBlock
0x1802c59c4  lea     r8, [rbp+80h+CompletionContext]; CompletionContext
0x1802c59c8  mov     qword ptr [rsp+180h+CompletionInformation], rdi; Timeout
0x1802c59cd  lea     rdx, [rbp+80h+CompletionKey]; CompletionKey
0x1802c59d1  call    cs:__imp_NtRemoveIoCompletion
0x1802c59d8  nop     dword ptr [rax+rax+00h]
0x1802c59dd  test    eax, eax
0x1802c59df  jns     loc_1802C5927
0x1802c59e5  lea     rcx, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c59ec  mov     [rsp+180h+var_120], 127Bh
0x1802c59f5  mov     [rsp+180h+var_130], rcx
0x1802c59fa  lea     rdx, [rsp+180h+var_130]
0x1802c59ff  lea     rcx, aWorkercallback; "WorkerCallback"
0x1802c5a06  mov     [rsp+180h+var_128], rcx
0x1802c5a0b  lea     rcx, aNtremoveiocomp_0; "::NtRemoveIoCompletion( Context->Worker"...
0x1802c5a12  mov     [rsp+180h+var_118], rcx
0x1802c5a17  mov     r8d, eax
0x1802c5a1a  lea     rcx, [rbp+80h+var_A8]
0x1802c5a1e  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1802c5a23  mov     ebx, eax
0x1802c5a25  lea     rcx, [rsp+180h+var_110]
0x1802c5a2a  call    Windows__Detail__OnBlockExitImpl__WorkerCallback____5____lambda_1______OnBlockExitImpl__WorkerCallback____5____lambda_1___
0x1802c5a2f  lea     rcx, [rbp+80h+var_48]; this
0x1802c5a33  call    ??1StopWatch@Rtl@Windows@@QEAA@XZ; Windows::Rtl::StopWatch::~StopWatch(void)
0x1802c5a38  lea     rcx, [rbp+80h+var_70]; this
0x1802c5a3c  call    ??1StopWatch@Rtl@Windows@@QEAA@XZ; Windows::Rtl::StopWatch::~StopWatch(void)
0x1802c5a41  lea     rcx, [rbp+80h+var_98]; this
0x1802c5a45  call    ??1StopWatch@Rtl@Windows@@QEAA@XZ; Windows::Rtl::StopWatch::~StopWatch(void)
0x1802c5a4a  mov     eax, ebx
0x1802c5a4c  mov     rcx, [rbp+80h+var_10]
0x1802c5a50  xor     rcx, rsp; StackCookie
0x1802c5a53  call    __security_check_cookie
0x1802c5a58  lea     r11, [rsp+180h+var_s0]
0x1802c5a60  mov     rbx, [r11+18h]
0x1802c5a64  mov     rdi, [r11+20h]
0x1802c5a68  mov     rsp, r11
0x1802c5a6b  pop     rbp
0x1802c5a6c  retn
0x1802c5a6e  lea     rcx, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c5a75  mov     [rsp+180h+var_140], 12A7h
0x1802c5a7e  mov     [rsp+180h+var_150], rcx
0x1802c5a83  lea     rcx, aWorkercallback; "WorkerCallback"
0x1802c5a8a  mov     [rsp+180h+var_148], rcx
0x1802c5a8f  lea     rcx, aNtsetiocomplet_4; "::NtSetIoCompletion( Context->Dispatche"...
0x1802c5a96  mov     [rsp+180h+var_138], rcx
0x1802c5a9b  lea     rdx, [rsp+180h+var_150]
0x1802c5aa0  jmp     loc_1802C5A17
0x1802c5aa5  sub     ecx, 1
0x1802c5aa8  jz      loc_1802C5B39
0x1802c5aae  cmp     ecx, 1
0x1802c5ab1  jz      short loc_1802C5AE4
0x1802c5ab3  lea     rcx, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c5aba  mov     [rbp+80h+var_E0], 1285h
0x1802c5ac2  mov     [rbp+80h+var_F0], rcx
0x1802c5ac6  lea     rdx, [rbp+80h+var_F0]
0x1802c5aca  lea     rcx, aWorkercallback; "WorkerCallback"
0x1802c5ad1  mov     [rbp+80h+var_D8], rdi
0x1802c5ad5  mov     [rbp+80h+var_E8], rcx
0x1802c5ad9  mov     r8d, 0C000000Dh
0x1802c5adf  jmp     loc_1802C5A1A
0x1802c5ae4  mov     rcx, [rbx+8]; IoCompletionPortHandle
0x1802c5ae8  xor     r9d, r9d; CompletionStatus
0x1802c5aeb  xor     r8d, r8d; CompletionContext
0x1802c5aee  mov     qword ptr [rsp+180h+CompletionInformation], rdi; CompletionInformation
0x1802c5af3  lea     edx, [r9+2]; CompletionKey
0x1802c5af7  call    cs:__imp_NtSetIoCompletion
0x1802c5afe  nop     dword ptr [rax+rax+00h]
0x1802c5b03  test    eax, eax
0x1802c5b05  jns     short loc_1802C5B39
0x1802c5b07  lea     rcx, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c5b0e  mov     [rbp+80h+var_C0], 1290h
0x1802c5b16  mov     [rbp+80h+var_D0], rcx
0x1802c5b1a  lea     rdx, [rbp+80h+var_D0]
0x1802c5b1e  lea     rcx, aWorkercallback; "WorkerCallback"
0x1802c5b25  mov     [rbp+80h+var_C8], rcx
0x1802c5b29  lea     rcx, aNtsetiocomplet_3; "::NtSetIoCompletion( Context->WorkerPor"...
0x1802c5b30  mov     [rbp+80h+var_B8], rcx
0x1802c5b34  jmp     loc_1802C5A17
0x1802c5b39  mov     ebx, edi
0x1802c5b3b  jmp     loc_1802C5A25
0x1802c5b40  lea     rcx, aOnecoreBaseWcp_42; "onecore\\base\\wcp\\poq\\poqsil.cpp"
0x1802c5b47  mov     [rsp+180h+var_120], 1280h
0x1802c5b50  mov     [rsp+180h+var_130], rcx
0x1802c5b55  lea     rax, aIosbStatus; "IoSb.Status"
0x1802c5b5c  lea     rcx, aWorkercallback; "WorkerCallback"
0x1802c5b63  mov     [rsp+180h+var_118], rax
0x1802c5b68  mov     [rsp+180h+var_128], rcx
0x1802c5b6d  lea     rdx, [rsp+180h+var_130]
0x1802c5b72  jmp     loc_1802C5A1A
0x1802c5b77  mov     ecx, 0C00000E5h; int
0x1802c5b7c  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
