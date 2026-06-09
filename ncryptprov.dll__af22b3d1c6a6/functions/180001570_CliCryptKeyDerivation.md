# CliCryptKeyDerivation

- ea: `0x180001570`
- end: `0x1800018c5`
- name: `CliCryptKeyDerivation`
- size: `853`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x180001570`
- `0x180002da4`
- `0x180002f8c`
- `0x180003068`
- `0x18000af80`
- `0x18000e9c8`
- `0x180024f60`
- `0x180035b28`
- `0x180038970`
- `0x18003948c`
- `0x180060f5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001618`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001739`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001780`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001618`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001739`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001780`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180001729`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180001729`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000170c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000170c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800015ff`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800015ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001882`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800018a0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180001882`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800018a0`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180001770`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x180001770`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800623ee`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800623ee`

## string_xrefs

- `0x1800015e4`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x18000162c`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x180001822`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`
- `0x18000184c`: `onecore\ds\security\cryptoapi\ncrypt\iso\client\cliapi.c`

## pseudocode

```c
__int64 __fastcall CliCryptKeyDerivation(__int64 *a1, __int64 *a2, __int64 a3, __int64 a4, int a5, __int64 a6, int a7)
{
  __int64 v11; // rsi
  unsigned int v12; // edi
  __int64 v13; // r9
  __int64 v14; // rcx
  DWORD LastError; // ebx
  HANDLE CurrentThread; // rax
  int v18; // eax
  __int64 v19; // r9
  __int64 v20; // r8
  int v21; // eax
  void *TokenHandle; // [rsp+58h] [rbp-F0h] BYREF
  __int64 v23; // [rsp+60h] [rbp-E8h]
  _QWORD pv[2]; // [rsp+70h] [rbp-D8h] BYREF
  __int64 v25; // [rsp+80h] [rbp-C8h]
  __int64 v26; // [rsp+88h] [rbp-C0h]
  __int64 v27; // [rsp+C8h] [rbp-80h]
  int v28; // [rsp+D0h] [rbp-78h]
  HANDLE *p_hObject; // [rsp+D8h] [rbp-70h]
  void *v30; // [rsp+E0h] [rbp-68h]
  __int64 v31; // [rsp+F0h] [rbp-58h]
  __int64 v32; // [rsp+F8h] [rbp-50h]
  int v33; // [rsp+100h] [rbp-48h]
  HANDLE hObject; // [rsp+160h] [rbp+18h] BYREF

  v11 = 0;
  v23 = 0;
  hObject = 0;
  TokenHandle = 0;
  memset_0(pv, 0, 0x98u);
  if ( !a3 || (v11 = MapBufferDescToRPC(a3), (v23 = v11) != 0) )
  {
    hObject = CreateEventW(0, 0, 0, 0);
    if ( !hObject )
    {
      LastError = GetLastError();
      DebugTraceError(LastError, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c", 3076);
      return LastError;
    }
    if ( !(unsigned __int8)IsGetMessageWPresent() || !(unsigned int)IsKeyProtected((int)a1, (__int64)a2) )
    {
      if ( a2 )
        v19 = *a2;
      else
        LODWORD(v19) = 0;
      if ( a1 )
        v20 = *a1;
      else
        LODWORD(v20) = 0;
      v21 = c_SrvRpcCryptKeyDerivation((_DWORD)g_RpcBindingContext, qword_18007A5E0, v20, v19, v11, a4, a5, a6, a7);
      v12 = v21;
      if ( v21 < 0 )
        DebugTraceError(
          (unsigned int)v21,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c",
          3149);
      goto LABEL_33;
    }
    pv[0] = g_RpcBindingContext;
    pv[1] = qword_18007A5E0;
    if ( a1 )
      v25 = *a1;
    else
      v25 = 0;
    if ( a2 )
      v26 = *a2;
    else
      v26 = 0;
    v31 = v11;
    v32 = a4;
    v33 = a5;
    v27 = a6;
    v28 = a7;
    p_hObject = &hObject;
    if ( NtCurrentTeb()->IsImpersonating )
    {
      CurrentThread = GetCurrentThread();
      if ( !OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle) )
      {
        v18 = GetLastError();
        v13 = 3113;
        goto LABEL_18;
      }
      v30 = TokenHandle;
    }
    if ( TrySubmitThreadpoolCallback((PTP_SIMPLE_CALLBACK)CliThreadCryptKeyDerivationCallback, pv, 0) )
    {
      v18 = CliWaitForCallBackCompletion(hObject, (__int64)pv);
      v12 = v18;
      if ( v18 >= 0 )
        goto LABEL_33;
      v13 = 3130;
      goto LABEL_19;
    }
    v18 = GetLastError();
    v13 = 3123;
LABEL_18:
    v12 = v18;
LABEL_19:
    v14 = (unsigned int)v18;
    goto LABEL_4;
  }
  v12 = -1073741801;
  v13 = 3067;
  v14 = 3221225495LL;
LABEL_4:
  DebugTraceError(v14, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\client\\cliapi.c", v13);
LABEL_33:
  if ( v11 )
    FreeRPCBufferDesc(v11);
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return NormalizeNteStatus(v12);
}

```

## disassembly

```asm
0x180001570  mov     rax, rsp
0x180001573  push    rbx
0x180001574  push    rsi
0x180001575  push    rdi
0x180001576  push    r12
0x180001578  push    r14
0x18000157a  push    r15
0x18000157c  sub     rsp, 118h
0x180001583  mov     r12, r9
0x180001586  mov     r15, r8
0x180001589  mov     rdi, rdx
0x18000158c  mov     r14, rcx
0x18000158f  xor     ebx, ebx
0x180001591  mov     esi, ebx
0x180001593  mov     [rsp+148h+var_E8], rbx
0x180001598  mov     [rax+18h], rbx
0x18000159c  mov     [rsp+148h+TokenHandle], rbx
0x1800015a1  xor     edx, edx; Val
0x1800015a3  mov     r8d, 98h; Size
0x1800015a9  lea     rcx, [rsp+148h+pv]; void *
0x1800015ae  call    memset_0
0x1800015b3  test    r15, r15
0x1800015b6  jz      short loc_1800015F5
0x1800015b8  mov     rcx, r15
0x1800015bb  call    _MapBufferDescToRPC
0x1800015c0  mov     rsi, rax
0x1800015c3  mov     [rsp+148h+var_E8], rax
0x1800015c8  test    rax, rax
0x1800015cb  jnz     short loc_1800015F5
0x1800015cd  mov     edi, 0C0000017h
0x1800015d2  mov     r9d, 0BFBh
0x1800015d8  mov     ecx, 0C0000017h
0x1800015dd  lea     rdx, aStatus; "Status"
0x1800015e4  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800015eb  call    DebugTraceError
0x1800015f0  jmp     loc_180001868
0x1800015f5  xor     r9d, r9d; lpName
0x1800015f8  xor     r8d, r8d; bInitialState
0x1800015fb  xor     edx, edx; bManualReset
0x1800015fd  xor     ecx, ecx; lpEventAttributes
0x1800015ff  call    cs:__imp_CreateEventW
0x180001606  nop     dword ptr [rax+rax+00h]
0x18000160b  mov     [rsp+148h+hObject], rax
0x180001613  test    rax, rax
0x180001616  jnz     short loc_180001648
0x180001618  call    cs:__imp_GetLastError
0x18000161f  nop     dword ptr [rax+rax+00h]
0x180001624  mov     ebx, eax
0x180001626  mov     r9d, 0C04h
0x18000162c  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001633  lea     rdx, aStatus; "Status"
0x18000163a  mov     ecx, eax
0x18000163c  call    DebugTraceError
0x180001641  mov     eax, ebx
0x180001643  jmp     loc_1800018B3
0x180001648  call    IsGetMessageWPresent
0x18000164d  test    al, al
0x18000164f  jz      loc_1800017B8
0x180001655  mov     rdx, rdi
0x180001658  mov     rcx, r14
0x18000165b  call    IsKeyProtected
0x180001660  test    eax, eax
0x180001662  jz      loc_1800017B8
0x180001668  mov     rax, cs:g_RpcBindingContext
0x18000166f  mov     [rsp+148h+pv], rax
0x180001674  mov     rax, cs:qword_18007A5E0
0x18000167b  mov     [rsp+148h+var_D0], rax
0x180001680  test    r14, r14
0x180001683  jz      short loc_180001692
0x180001685  mov     rax, [r14]
0x180001688  mov     [rsp+148h+var_C8], rax
0x180001690  jmp     short loc_18000169A
0x180001692  mov     [rsp+148h+var_C8], rbx
0x18000169a  test    rdi, rdi
0x18000169d  jz      short loc_1800016AC
0x18000169f  mov     rax, [rdi]
0x1800016a2  mov     [rsp+148h+var_C0], rax
0x1800016aa  jmp     short loc_1800016B4
0x1800016ac  mov     [rsp+148h+var_C0], rbx
0x1800016b4  mov     [rsp+148h+var_58], rsi
0x1800016bc  mov     [rsp+148h+var_50], r12
0x1800016c4  mov     eax, [rsp+148h+arg_20]
0x1800016cb  mov     [rsp+148h+var_48], eax
0x1800016d2  mov     rax, [rsp+148h+arg_28]
0x1800016da  mov     [rsp+148h+var_80], rax
0x1800016e2  mov     eax, [rsp+148h+arg_30]
0x1800016e9  mov     [rsp+148h+var_78], eax
0x1800016f0  lea     rax, [rsp+148h+hObject]
0x1800016f8  mov     [rsp+148h+var_70], rax
0x180001700  mov     eax, gs:179Ch
0x180001708  test    eax, eax
0x18000170a  jz      short loc_180001761
0x18000170c  call    cs:__imp_GetCurrentThread
0x180001713  nop     dword ptr [rax+rax+00h]
0x180001718  mov     rcx, rax; ThreadHandle
0x18000171b  lea     r9, [rsp+148h+TokenHandle]; TokenHandle
0x180001720  mov     edx, 0Ch; DesiredAccess
0x180001725  lea     r8d, [rdx-0Bh]; OpenAsSelf
0x180001729  call    cs:__imp_OpenThreadToken
0x180001730  nop     dword ptr [rax+rax+00h]
0x180001735  test    eax, eax
0x180001737  jnz     short loc_180001754
0x180001739  call    cs:__imp_GetLastError
0x180001740  nop     dword ptr [rax+rax+00h]
0x180001745  mov     r9d, 0C29h
0x18000174b  mov     edi, eax
0x18000174d  mov     ecx, eax
0x18000174f  jmp     loc_1800015DD
0x180001754  mov     rax, [rsp+148h+TokenHandle]
0x180001759  mov     [rsp+148h+var_68], rax
0x180001761  xor     r8d, r8d; pcbe
0x180001764  lea     rdx, [rsp+148h+pv]; pv
0x180001769  lea     rcx, _CliThreadCryptKeyDerivationCallback; pfns
0x180001770  call    cs:__imp_TrySubmitThreadpoolCallback
0x180001777  nop     dword ptr [rax+rax+00h]
0x18000177c  test    eax, eax
0x18000177e  jnz     short loc_180001794
0x180001780  call    cs:__imp_GetLastError
0x180001787  nop     dword ptr [rax+rax+00h]
0x18000178c  mov     r9d, 0C33h
0x180001792  jmp     short loc_18000174B
0x180001794  lea     rdx, [rsp+148h+pv]
0x180001799  mov     rcx, [rsp+148h+hObject]
0x1800017a1  call    _CliWaitForCallBackCompletion
0x1800017a6  mov     edi, eax
0x1800017a8  test    eax, eax
0x1800017aa  jns     loc_180001868
0x1800017b0  mov     r9d, 0C3Ah
0x1800017b6  jmp     short loc_18000174D
0x1800017b8  test    rdi, rdi
0x1800017bb  jz      short loc_1800017C2
0x1800017bd  mov     r9, [rdi]
0x1800017c0  jmp     short loc_1800017C5
0x1800017c2  mov     r9, rbx
0x1800017c5  test    r14, r14
0x1800017c8  jz      short loc_1800017CF
0x1800017ca  mov     r8, [r14]
0x1800017cd  jmp     short loc_1800017D2
0x1800017cf  mov     r8, rbx
0x1800017d2  mov     eax, [rsp+148h+arg_30]
0x1800017d9  mov     [rsp+148h+var_108], eax
0x1800017dd  mov     rax, [rsp+148h+arg_28]
0x1800017e5  mov     [rsp+148h+var_110], rax
0x1800017ea  mov     eax, [rsp+148h+arg_20]
0x1800017f1  mov     [rsp+148h+var_118], eax
0x1800017f5  mov     [rsp+148h+var_120], r12
0x1800017fa  mov     [rsp+148h+var_128], rsi
0x1800017ff  mov     rdx, cs:qword_18007A5E0
0x180001806  mov     rcx, cs:g_RpcBindingContext
0x18000180d  call    c_SrvRpcCryptKeyDerivation
0x180001812  mov     edi, eax
0x180001814  mov     [rsp+148h+var_F8], eax
0x180001818  test    eax, eax
0x18000181a  jns     short loc_180001837
0x18000181c  mov     r9d, 0C4Dh
0x180001822  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001829  lea     rdx, aStatus; "Status"
0x180001830  mov     ecx, eax
0x180001832  call    DebugTraceError
0x180001837  jmp     short loc_180001868
0x180001839  mov     ecx, eax
0x18000183b  call    HResultFromRpcException
0x180001840  mov     edi, eax
0x180001842  mov     [rsp+148h+var_F8], eax
0x180001846  mov     r9d, 0C51h
0x18000184c  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180001853  lea     rdx, aStatus; "Status"
0x18000185a  mov     ecx, eax
0x18000185c  call    DebugTraceError
0x180001861  xor     ebx, ebx
0x180001863  mov     rsi, [rsp+148h+var_E8]
0x180001868  test    rsi, rsi
0x18000186b  jz      short loc_180001875
0x18000186d  mov     rcx, rsi
0x180001870  call    _FreeRPCBufferDesc
0x180001875  mov     rcx, [rsp+148h+hObject]; hObject
0x18000187d  test    rcx, rcx
0x180001880  jz      short loc_180001896
0x180001882  call    cs:__imp_CloseHandle
0x180001889  nop     dword ptr [rax+rax+00h]
0x18000188e  mov     [rsp+148h+hObject], rbx
0x180001896  mov     rcx, [rsp+148h+TokenHandle]; hObject
0x18000189b  test    rcx, rcx
0x18000189e  jz      short loc_1800018AC
0x1800018a0  call    cs:__imp_CloseHandle
0x1800018a7  nop     dword ptr [rax+rax+00h]
0x1800018ac  mov     ecx, edi
0x1800018ae  call    NormalizeNteStatus
0x1800018b3  add     rsp, 118h
0x1800018ba  pop     r15
0x1800018bc  pop     r14
0x1800018be  pop     r12
0x1800018c0  pop     rdi
0x1800018c1  pop     rsi
0x1800018c2  pop     rbx
0x1800018c3  retn
0x1800623e0  push    rbp
0x1800623e2  sub     rsp, 50h
0x1800623e6  mov     rbp, rdx
0x1800623e9  mov     rcx, [rcx]
0x1800623ec  mov     ecx, [rcx]; ExceptionCode
0x1800623ee  call    cs:__imp_I_RpcExceptionFilter
0x1800623f5  nop     dword ptr [rax+rax+00h]
0x1800623fa  nop
0x1800623fb  add     rsp, 50h
0x1800623ff  pop     rbp
0x180062400  retn
```
