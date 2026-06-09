# GetRpcClientInfo(void *,ulong *,ushort *,ulong *,void * *,void * *,ulong *,ushort * *,ushort * *)

- ea: `0x18001bf50`
- end: `0x18001c4df`
- name: `?GetRpcClientInfo@@YAJPEAXPEAKPEAG1PEAPEAX31PEAPEAG4@Z`
- size: `1423`
- prototype: `int(void *, unsigned int *, unsigned __int16 *, unsigned int *, void **, void **, unsigned int *, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001bbfc`
- `0x180026e30`
- `0x18002eee0`
- `0x180030960`

## callees

- `0x180007500`
- `0x18001b804`
- `0x18001bf50`
- `0x18002394c`
- `0x18005e4a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c435`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c44e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c435`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001c44e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c443`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c45c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c443`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001c45c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c05b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c11d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c1c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c221`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c3ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c40b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c4b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c05b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c11d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c1c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c221`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c3ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c40b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c4b5`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001c113`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001c113`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001c0ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001c0ff`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001c1b6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001c1b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c3b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c3f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c49a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c3b7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c3f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001c49a`
- `RPCRT4!RpcRevertToSelf` at `0x18001c132`
- `RPCRT4!RpcRevertToSelf` at `0x18001c18e`
- `RPCRT4!RpcRevertToSelf` at `0x18001c132`
- `RPCRT4!RpcRevertToSelf` at `0x18001c18e`
- `RPCRT4!RpcImpersonateClient` at `0x18001c0e6`
- `RPCRT4!RpcImpersonateClient` at `0x18001c0e6`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18001bf99`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18001bf99`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001c217`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001c217`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001c04c`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001c04c`

## pseudocode

```c
__int64 __fastcall GetRpcClientInfo(
        void *a1,
        unsigned int *a2,
        unsigned __int16 *a3,
        unsigned int *a4,
        void **a5,
        void **a6,
        unsigned int *a7,
        unsigned __int16 **a8,
        unsigned __int16 **a9)
{
  unsigned __int16 *v11; // r14
  unsigned __int16 *v12; // r13
  RPC_STATUS v13; // eax
  int v14; // edx
  int v15; // r8d
  signed int AumId; // ebx
  DWORD v17; // r8d
  signed int LastError; // eax
  int v19; // edx
  int v20; // r8d
  RPC_STATUS v21; // eax
  int v22; // edx
  int v23; // r8d
  HANDLE CurrentThread; // rax
  signed int v25; // eax
  int v26; // r9d
  signed int v27; // eax
  signed int v28; // eax
  int v29; // edx
  int v30; // r8d
  int v31; // edx
  int v32; // r8d
  char v33; // al
  int v34; // edx
  int v35; // r8d
  char v36; // al
  int v37; // edx
  int v38; // r8d
  HANDLE ProcessHeap; // rax
  HANDLE v40; // rax
  char v42; // al
  int v43; // edx
  int v44; // r8d
  int TokenInformation; // [rsp+48h] [rbp-39h] BYREF
  unsigned int Pid; // [rsp+4Ch] [rbp-35h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-31h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp-29h] BYREF
  unsigned __int16 *v49; // [rsp+60h] [rbp-21h]
  unsigned __int16 *v50; // [rsp+68h] [rbp-19h] BYREF
  DWORD ReturnLength; // [rsp+70h] [rbp-11h] BYREF
  HANDLE ProcessHandle; // [rsp+78h] [rbp-9h]

  Pid = 0;
  hObject = 0;
  TokenHandle = 0;
  TokenInformation = 0;
  v11 = 0;
  v49 = 0;
  v12 = 0;
  v50 = 0;
  v13 = I_RpcBindingInqLocalClientPID(a1, &Pid);
  AumId = v13;
  if ( v13 >= 1 )
    AumId = (unsigned __int16)v13 | 0x80010000;
  if ( AumId < 0 )
  {
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      if ( !a3 )
        a3 = L"-none passed-";
      WPP_RECORDER_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v14,
        v15,
        15,
        &WPP_86914d2e09da351300e95fc82fbf9ce2_Traceguids,
        (__int64)a3,
        AumId);
    }
    goto LABEL_82;
  }
  v17 = Pid;
  if ( a4 )
    *a4 = Pid;
  if ( !a5 && !a6 && !a7 && !a8 && !a9 )
    goto LABEL_81;
  ProcessHandle = OpenProcess(0x1040u, 0, v17);
  if ( ProcessHandle )
  {
    AumId = 0;
  }
  else
  {
    LastError = GetLastError();
    AumId = LastError;
    if ( LastError > 0 )
      AumId = (unsigned __int16)LastError | 0x80070000;
    if ( AumId < 0 )
    {
      if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
      {
        if ( !a3 )
          a3 = L"-none passed-";
        WPP_RECORDER_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 5),
          v19,
          v20,
          16,
          &WPP_86914d2e09da351300e95fc82fbf9ce2_Traceguids,
          (__int64)a3,
          AumId);
      }
      goto LABEL_81;
    }
  }
  if ( !a6 && !a7 && !a8 && !a9 )
  {
LABEL_79:
    if ( !a5 )
      goto LABEL_95;
    *a5 = ProcessHandle;
LABEL_81:
    v11 = 0;
    goto LABEL_82;
  }
  TokenHandle = 0;
  v21 = RpcImpersonateClient(0);
  AumId = v21;
  if ( v21 )
  {
    if ( v21 > 0 )
      AumId = (unsigned __int16)v21 | 0x80070000;
  }
  else
  {
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0xEu, 0, &TokenHandle) )
    {
      RpcRevertToSelf();
      AumId = 0;
      goto LABEL_42;
    }
    v25 = GetLastError();
    AumId = v25;
    if ( v25 > 0 )
      AumId = (unsigned __int16)v25 | 0x80070000;
    RpcRevertToSelf();
  }
  if ( AumId < 0 )
  {
    if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      v26 = 17;
LABEL_38:
      if ( !a3 )
        a3 = L"-none passed-";
      WPP_RECORDER_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        v22,
        v23,
        v26,
        &WPP_86914d2e09da351300e95fc82fbf9ce2_Traceguids,
        (__int64)a3,
        AumId);
      goto LABEL_95;
    }
    goto LABEL_95;
  }
LABEL_42:
  if ( !a7 && !a8 && !a9 )
  {
LABEL_77:
    if ( a6 )
    {
      *a6 = TokenHandle;
      TokenHandle = 0;
    }
    goto LABEL_79;
  }
  if ( OpenProcessToken(ProcessHandle, 0xEu, &hObject) )
    goto LABEL_51;
  v27 = GetLastError();
  AumId = v27;
  if ( v27 > 0 )
    AumId = (unsigned __int16)v27 | 0x80070000;
  if ( AumId >= 0 )
  {
LABEL_51:
    ReturnLength = 0;
    if ( GetTokenInformation(hObject, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength) )
    {
      AumId = 0;
    }
    else
    {
      v28 = GetLastError();
      AumId = v28;
      if ( v28 > 0 )
        AumId = (unsigned __int16)v28 | 0x80070000;
      if ( AumId < 0 )
      {
        if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          v26 = 19;
          goto LABEL_38;
        }
        goto LABEL_95;
      }
    }
    if ( a8 && TokenInformation )
    {
      AumId = GetAumId(hObject);
      if ( AumId < 0 )
      {
        if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          if ( !a3 )
            a3 = L"-none passed-";
          WPP_RECORDER_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 5),
            v29,
            v30,
            20,
            &WPP_86914d2e09da351300e95fc82fbf9ce2_Traceguids,
            (__int64)a3,
            AumId);
        }
        v11 = v49;
        goto LABEL_96;
      }
      *a8 = v49;
    }
    if ( a9 )
    {
      AumId = GetPerUserSidString(TokenInformation, Pid, hObject, TokenHandle, a2, a3, &v50);
      if ( AumId < 0 )
      {
        if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
        {
          if ( !a3 )
            a3 = L"-none passed-";
          WPP_RECORDER_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 5),
            v31,
            v32,
            21,
            &WPP_86914d2e09da351300e95fc82fbf9ce2_Traceguids,
            (__int64)a3,
            AumId);
        }
        v12 = v50;
        goto LABEL_95;
      }
      *a9 = v50;
    }
    if ( a7 )
      *a7 = TokenInformation;
    goto LABEL_77;
  }
  if ( *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v26 = 18;
    goto LABEL_38;
  }
LABEL_95:
  v11 = 0;
LABEL_96:
  if ( ProcessHandle && !CloseHandle(ProcessHandle) && *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v42 = GetLastError();
    WPP_RECORDER_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v43,
      v44,
      22,
      &WPP_86914d2e09da351300e95fc82fbf9ce2_Traceguids,
      v42);
  }
LABEL_82:
  if ( hObject && !CloseHandle(hObject) && *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v33 = GetLastError();
    WPP_RECORDER_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v34,
      v35,
      23,
      &WPP_86914d2e09da351300e95fc82fbf9ce2_Traceguids,
      v33);
  }
  if ( TokenHandle && !CloseHandle(TokenHandle) && *(int **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    v36 = GetLastError();
    WPP_RECORDER_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v37,
      v38,
      24,
      &WPP_86914d2e09da351300e95fc82fbf9ce2_Traceguids,
      v36);
  }
  if ( v11 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v11);
  }
  if ( v12 )
  {
    v40 = GetProcessHeap();
    HeapFree(v40, 0, v12);
  }
  return (unsigned int)AumId;
}

```

## disassembly

```asm
0x18001bf50  mov     [rsp-8+arg_8], rdx
0x18001bf55  push    rbp
0x18001bf56  push    rbx
0x18001bf57  push    rsi
0x18001bf58  push    rdi
0x18001bf59  push    r12
0x18001bf5b  push    r13
0x18001bf5d  push    r14
0x18001bf5f  push    r15
0x18001bf61  lea     rbp, [rsp-7]
0x18001bf66  sub     rsp, 88h
0x18001bf6d  mov     rsi, r9
0x18001bf70  mov     rdi, r8
0x18001bf73  xor     eax, eax
0x18001bf75  mov     [rbp+3Fh+Pid], eax
0x18001bf78  mov     [rbp+3Fh+hObject], rax
0x18001bf7c  mov     [rbp+3Fh+TokenHandle], rax
0x18001bf80  mov     [rbp+3Fh+TokenInformation], eax
0x18001bf83  mov     r14d, eax
0x18001bf86  mov     [rbp+3Fh+var_80], rax
0x18001bf8a  mov     [rbp+3Fh+var_60], rax
0x18001bf8e  mov     r13d, eax
0x18001bf91  mov     [rbp+3Fh+var_58], rax
0x18001bf95  lea     rdx, [rbp+3Fh+Pid]; Pid
0x18001bf99  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18001bf9f  mov     ebx, eax
0x18001bfa1  cmp     eax, 1
0x18001bfa4  jl      short loc_18001BFAF
0x18001bfa6  movzx   ebx, ax
0x18001bfa9  or      ebx, 80010000h
0x18001bfaf  lea     r12, WPP_86914d2e09da351300e95fc82fbf9ce2_Traceguids
0x18001bfb6  lea     r15, WPP_RECORDER_INITIALIZED
0x18001bfbd  test    ebx, ebx
0x18001bfbf  jns     short loc_18001C005
0x18001bfc1  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001bfc8  jz      loc_18001C3AE
0x18001bfce  lea     rax, aNonePassed; "-none passed-"
0x18001bfd5  test    rdi, rdi
0x18001bfd8  cmovz   rdi, rax
0x18001bfdc  mov     r9d, 0Fh; int
0x18001bfe2  mov     dword ptr [rsp+0C0h+var_90], ebx; char
0x18001bfe6  mov     [rsp+0C0h+var_98], rdi; __int64
0x18001bfeb  mov     [rsp+0C0h+ReturnLength], r12; MessageGuid
0x18001bff0  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bff7  mov     rcx, [rcx+28h]; int
0x18001bffb  call    WPP_RECORDER_SF_Sd
0x18001c000  jmp     loc_18001C3AE
0x18001c005  mov     r8d, [rbp+3Fh+Pid]; dwProcessId
0x18001c009  test    rsi, rsi
0x18001c00c  jz      short loc_18001C011
0x18001c00e  mov     [rsi], r8d
0x18001c011  mov     r15, [rbp+3Fh+arg_40]
0x18001c018  mov     rsi, [rbp+3Fh+arg_38]
0x18001c01f  mov     r14, [rbp+3Fh+arg_30]
0x18001c023  mov     r12, [rbp+3Fh+arg_28]
0x18001c027  cmp     [rbp+3Fh+arg_20], r13
0x18001c02b  jnz     short loc_18001C045
0x18001c02d  test    r12, r12
0x18001c030  jnz     short loc_18001C045
0x18001c032  test    r14, r14
0x18001c035  jnz     short loc_18001C045
0x18001c037  test    rsi, rsi
0x18001c03a  jnz     short loc_18001C045
0x18001c03c  test    r15, r15
0x18001c03f  jz      loc_18001C39C
0x18001c045  xor     edx, edx; bInheritHandle
0x18001c047  mov     ecx, 1040h; dwDesiredAccess
0x18001c04c  call    cs:__imp_OpenProcess
0x18001c052  mov     [rbp+3Fh+ProcessHandle], rax
0x18001c056  test    rax, rax
0x18001c059  jnz     short loc_18001C0C6
0x18001c05b  call    cs:__imp_GetLastError
0x18001c061  mov     ebx, eax
0x18001c063  test    eax, eax
0x18001c065  jle     short loc_18001C070
0x18001c067  movzx   ebx, ax
0x18001c06a  or      ebx, 80070000h
0x18001c070  test    ebx, ebx
0x18001c072  jns     short loc_18001C0C8
0x18001c074  lea     r15, WPP_RECORDER_INITIALIZED
0x18001c07b  lea     r12, WPP_86914d2e09da351300e95fc82fbf9ce2_Traceguids
0x18001c082  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001c089  jz      loc_18001C3AA
0x18001c08f  lea     rax, aNonePassed; "-none passed-"
0x18001c096  test    rdi, rdi
0x18001c099  cmovz   rdi, rax
0x18001c09d  mov     r9d, 10h; int
0x18001c0a3  mov     dword ptr [rsp+0C0h+var_90], ebx; char
0x18001c0a7  mov     [rsp+0C0h+var_98], rdi; __int64
0x18001c0ac  mov     [rsp+0C0h+ReturnLength], r12; MessageGuid
0x18001c0b1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c0b8  mov     rcx, [rcx+28h]; int
0x18001c0bc  call    WPP_RECORDER_SF_Sd
0x18001c0c1  jmp     loc_18001C3AA
0x18001c0c6  xor     ebx, ebx
0x18001c0c8  test    r12, r12
0x18001c0cb  jnz     short loc_18001C0E0
0x18001c0cd  test    r14, r14
0x18001c0d0  jnz     short loc_18001C0E0
0x18001c0d2  test    rsi, rsi
0x18001c0d5  jnz     short loc_18001C0E0
0x18001c0d7  test    r15, r15
0x18001c0da  jz      loc_18001C388
0x18001c0e0  mov     [rbp+3Fh+TokenHandle], r13
0x18001c0e4  xor     ecx, ecx; BindingHandle
0x18001c0e6  call    cs:__imp_RpcImpersonateClient
0x18001c0ec  mov     ebx, eax
0x18001c0ee  test    eax, eax
0x18001c0f0  jz      short loc_18001C0FF
0x18001c0f2  jle     short loc_18001C138
0x18001c0f4  movzx   ebx, ax
0x18001c0f7  or      ebx, 80070000h
0x18001c0fd  jmp     short loc_18001C138
0x18001c0ff  call    cs:__imp_GetCurrentThread
0x18001c105  mov     rcx, rax; ThreadHandle
0x18001c108  lea     r9, [rbp+3Fh+TokenHandle]; TokenHandle
0x18001c10c  xor     r8d, r8d; OpenAsSelf
0x18001c10f  lea     edx, [r8+0Eh]; DesiredAccess
0x18001c113  call    cs:__imp_OpenThreadToken
0x18001c119  test    eax, eax
0x18001c11b  jnz     short loc_18001C18E
0x18001c11d  call    cs:__imp_GetLastError
0x18001c123  mov     ebx, eax
0x18001c125  test    eax, eax
0x18001c127  jle     short loc_18001C132
0x18001c129  movzx   ebx, ax
0x18001c12c  or      ebx, 80070000h
0x18001c132  call    cs:__imp_RpcRevertToSelf
0x18001c138  test    ebx, ebx
0x18001c13a  jns     short loc_18001C196
0x18001c13c  lea     rax, WPP_RECORDER_INITIALIZED
0x18001c143  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001c14a  jz      loc_18001C478
0x18001c150  mov     r9d, 11h; int
0x18001c156  test    rdi, rdi
0x18001c159  lea     rax, aNonePassed; "-none passed-"
0x18001c160  cmovz   rdi, rax
0x18001c164  mov     dword ptr [rsp+0C0h+var_90], ebx; char
0x18001c168  mov     [rsp+0C0h+var_98], rdi; __int64
0x18001c16d  lea     r12, WPP_86914d2e09da351300e95fc82fbf9ce2_Traceguids
0x18001c174  mov     [rsp+0C0h+ReturnLength], r12; MessageGuid
0x18001c179  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c180  mov     rcx, [rcx+28h]; int
0x18001c184  call    WPP_RECORDER_SF_Sd
0x18001c189  jmp     loc_18001C47F
0x18001c18e  call    cs:__imp_RpcRevertToSelf
0x18001c194  xor     ebx, ebx
0x18001c196  test    r14, r14
0x18001c199  jnz     short loc_18001C1A9
0x18001c19b  test    rsi, rsi
0x18001c19e  jnz     short loc_18001C1A9
0x18001c1a0  test    r15, r15
0x18001c1a3  jz      loc_18001C373
0x18001c1a9  lea     r8, [rbp+3Fh+hObject]; TokenHandle
0x18001c1ad  mov     edx, 0Eh; DesiredAccess
0x18001c1b2  mov     rcx, [rbp+3Fh+ProcessHandle]; ProcessHandle
0x18001c1b6  call    cs:__imp_OpenProcessToken
0x18001c1bc  test    eax, eax
0x18001c1be  jnz     short loc_18001C1F8
0x18001c1c0  call    cs:__imp_GetLastError
0x18001c1c6  mov     ebx, eax
0x18001c1c8  test    eax, eax
0x18001c1ca  jle     short loc_18001C1D5
0x18001c1cc  movzx   ebx, ax
0x18001c1cf  or      ebx, 80070000h
0x18001c1d5  test    ebx, ebx
0x18001c1d7  jns     short loc_18001C1F8
0x18001c1d9  lea     rax, WPP_RECORDER_INITIALIZED
0x18001c1e0  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001c1e7  jz      loc_18001C478
0x18001c1ed  mov     r9d, 12h
0x18001c1f3  jmp     loc_18001C156
0x18001c1f8  mov     [rbp+3Fh+var_50], r13d
0x18001c1fc  lea     rax, [rbp+3Fh+var_50]
0x18001c200  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x18001c205  mov     r9d, 4; TokenInformationLength
0x18001c20b  lea     r8, [rbp+3Fh+TokenInformation]; TokenInformation
0x18001c20f  lea     edx, [r9+19h]; TokenInformationClass
0x18001c213  mov     rcx, [rbp+3Fh+hObject]; TokenHandle
0x18001c217  call    cs:__imp_GetTokenInformation
0x18001c21d  test    eax, eax
0x18001c21f  jnz     short loc_18001C259
0x18001c221  call    cs:__imp_GetLastError
0x18001c227  mov     ebx, eax
0x18001c229  test    eax, eax
0x18001c22b  jle     short loc_18001C236
0x18001c22d  movzx   ebx, ax
0x18001c230  or      ebx, 80070000h
0x18001c236  test    ebx, ebx
0x18001c238  jns     short loc_18001C25B
0x18001c23a  lea     rax, WPP_RECORDER_INITIALIZED
0x18001c241  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18001c248  jz      loc_18001C478
0x18001c24e  mov     r9d, 13h
0x18001c254  jmp     loc_18001C156
0x18001c259  xor     ebx, ebx
0x18001c25b  test    rsi, rsi
0x18001c25e  jz      short loc_18001C2D6
0x18001c260  cmp     [rbp+3Fh+TokenInformation], r13d
0x18001c264  jz      short loc_18001C2D6
0x18001c266  lea     rdx, [rbp+3Fh+var_60]
0x18001c26a  mov     rcx, [rbp+3Fh+hObject]; token
0x18001c26e  call    GetAumId
0x18001c273  mov     ebx, eax
0x18001c275  test    eax, eax
0x18001c277  jns     short loc_18001C2CB
0x18001c279  lea     r15, WPP_RECORDER_INITIALIZED
0x18001c280  lea     r12, WPP_86914d2e09da351300e95fc82fbf9ce2_Traceguids
0x18001c287  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001c28e  jz      short loc_18001C2C2
0x18001c290  lea     rax, aNonePassed; "-none passed-"
0x18001c297  test    rdi, rdi
0x18001c29a  cmovz   rdi, rax
0x18001c29e  mov     r9d, 14h; int
0x18001c2a4  mov     dword ptr [rsp+0C0h+var_90], ebx; char
0x18001c2a8  mov     [rsp+0C0h+var_98], rdi; __int64
0x18001c2ad  mov     [rsp+0C0h+ReturnLength], r12; MessageGuid
0x18001c2b2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c2b9  mov     rcx, [rcx+28h]; int
0x18001c2bd  call    WPP_RECORDER_SF_Sd
0x18001c2c2  mov     r14, [rbp+3Fh+var_60]
0x18001c2c6  jmp     loc_18001C48A
0x18001c2cb  mov     rax, [rbp+3Fh+var_60]
0x18001c2cf  mov     [rsi], rax
0x18001c2d2  mov     [rbp+3Fh+var_80], r13
0x18001c2d6  test    r15, r15
0x18001c2d9  jz      loc_18001C368
0x18001c2df  lea     rax, [rbp+3Fh+var_58]
0x18001c2e3  mov     [rsp+0C0h+var_90], rax; unsigned __int16 **
0x18001c2e8  mov     [rsp+0C0h+var_98], rdi; unsigned __int16 *
0x18001c2ed  mov     rax, [rbp+3Fh+arg_8]
0x18001c2f1  mov     [rsp+0C0h+ReturnLength], rax; unsigned int *
0x18001c2f6  mov     r9, [rbp+3Fh+TokenHandle]; void *
0x18001c2fa  mov     r8, [rbp+3Fh+hObject]; void *
0x18001c2fe  mov     edx, [rbp+3Fh+Pid]; unsigned int
0x18001c301  mov     ecx, [rbp+3Fh+TokenInformation]; int
0x18001c304  call    ?GetPerUserSidString@@YAJHKPEAX0PEAKPEAGPEAPEAG@Z; GetPerUserSidString(int,ulong,void *,void *,ulong *,ushort *,ushort * *)
0x18001c309  mov     ebx, eax
0x18001c30b  test    eax, eax
0x18001c30d  jns     short loc_18001C361
0x18001c30f  lea     r15, WPP_RECORDER_INITIALIZED
0x18001c316  lea     r12, WPP_86914d2e09da351300e95fc82fbf9ce2_Traceguids
0x18001c31d  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001c324  jz      short loc_18001C358
0x18001c326  lea     rax, aNonePassed; "-none passed-"
0x18001c32d  test    rdi, rdi
0x18001c330  cmovz   rdi, rax
0x18001c334  mov     r9d, 15h; int
0x18001c33a  mov     dword ptr [rsp+0C0h+var_90], ebx; char
0x18001c33e  mov     [rsp+0C0h+var_98], rdi; __int64
0x18001c343  mov     [rsp+0C0h+ReturnLength], r12; MessageGuid
0x18001c348  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c34f  mov     rcx, [rcx+28h]; int
0x18001c353  call    WPP_RECORDER_SF_Sd
0x18001c358  mov     r13, [rbp+3Fh+var_58]
0x18001c35c  jmp     loc_18001C486
0x18001c361  mov     rax, [rbp+3Fh+var_58]
0x18001c365  mov     [r15], rax
0x18001c368  test    r14, r14
0x18001c36b  jz      short loc_18001C373
0x18001c36d  mov     eax, [rbp+3Fh+TokenInformation]
0x18001c370  mov     [r14], eax
0x18001c373  test    r12, r12
0x18001c376  jz      short loc_18001C388
0x18001c378  mov     rax, [rbp+3Fh+TokenHandle]
0x18001c37c  mov     [r12], rax
0x18001c380  mov     [rbp+3Fh+TokenHandle], 0
0x18001c388  mov     rcx, [rbp+3Fh+arg_20]
0x18001c38c  test    rcx, rcx
0x18001c38f  jz      loc_18001C478
0x18001c395  mov     rax, [rbp+3Fh+ProcessHandle]
0x18001c399  mov     [rcx], rax
0x18001c39c  lea     r12, WPP_86914d2e09da351300e95fc82fbf9ce2_Traceguids
0x18001c3a3  lea     r15, WPP_RECORDER_INITIALIZED
0x18001c3aa  mov     r14, [rbp+3Fh+var_80]
0x18001c3ae  mov     rcx, [rbp+3Fh+hObject]; hObject
0x18001c3b2  test    rcx, rcx
0x18001c3b5  jz      short loc_18001C3EF
0x18001c3b7  call    cs:__imp_CloseHandle
0x18001c3bd  test    eax, eax
0x18001c3bf  jnz     short loc_18001C3EF
0x18001c3c1  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001c3c8  jz      short loc_18001C3EF
0x18001c3ca  call    cs:__imp_GetLastError
0x18001c3d0  mov     r9d, 17h; int
0x18001c3d6  mov     dword ptr [rsp+0C0h+var_98], eax; char
0x18001c3da  mov     [rsp+0C0h+ReturnLength], r12; MessageGuid
0x18001c3df  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c3e6  mov     rcx, [rcx+28h]; int
0x18001c3ea  call    WPP_RECORDER_SF_D
0x18001c3ef  mov     rcx, [rbp+3Fh+TokenHandle]; hObject
0x18001c3f3  test    rcx, rcx
0x18001c3f6  jz      short loc_18001C430
0x18001c3f8  call    cs:__imp_CloseHandle
0x18001c3fe  test    eax, eax
0x18001c400  jnz     short loc_18001C430
0x18001c402  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18001c409  jz      short loc_18001C430
0x18001c40b  call    cs:__imp_GetLastError
0x18001c411  mov     r9d, 18h; int
  ... truncated ...
```
