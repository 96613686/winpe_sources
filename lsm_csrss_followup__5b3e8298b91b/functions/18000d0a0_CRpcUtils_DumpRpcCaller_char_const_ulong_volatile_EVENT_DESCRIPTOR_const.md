# CRpcUtils::DumpRpcCaller(char const *,ulong volatile &,_EVENT_DESCRIPTOR const &)

- ea: `0x18000d0a0`
- end: `0x18000d6bb`
- name: `?DumpRpcCaller@CRpcUtils@@SAXPEBDAECKAEBU_EVENT_DESCRIPTOR@@@Z`
- size: `1563`
- prototype: `void __fastcall(const char *, volatile unsigned int *, const struct _EVENT_DESCRIPTOR *)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x18000c7a0`
- `0x18001fef0`
- `0x18005ac9c`
- `0x18005bc50`
- `0x18005e640`

## callees

- `0x18000d0a0`
- `0x18004b460`
- `0x18004b8b4`
- `0x18004bd84`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x18000d181`
- `ntdll!NtQueryInformationProcess` at `0x18000d1c2`
- `ntdll!NtQueryInformationProcess` at `0x18000d181`
- `ntdll!NtQueryInformationProcess` at `0x18000d1c2`
- `ntdll!EtwEventWriteFull` at `0x18000d3c9`
- `ntdll!EtwEventWriteFull` at `0x18000d598`
- `ntdll!EtwEventWriteFull` at `0x18000d3c9`
- `ntdll!EtwEventWriteFull` at `0x18000d598`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000d111`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18000d111`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d3e4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000d3e4`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000d0c7`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18000d0c7`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000d121`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18000d121`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000d316`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000d4f5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000d67d`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000d316`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000d4f5`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18000d67d`

## pseudocode

```c
void __fastcall CRpcUtils::DumpRpcCaller(DWORD *a1, volatile unsigned int *a2, const struct _EVENT_DESCRIPTOR *a3)
{
  int v5; // eax
  DWORD v6; // ecx
  HANDLE v7; // rax
  const unsigned __int16 *v8; // r12
  __int64 v9; // rbx
  int v10; // r14d
  _QWORD *v11; // r14
  __int64 *v12; // rcx
  __int64 v13; // rax
  bool v14; // zf
  unsigned int v15; // eax
  const unsigned __int16 *v16; // rcx
  __int64 v17; // rax
  unsigned int v18; // eax
  __int16 *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  unsigned int v23; // eax
  __int64 v24; // rbx
  unsigned int v25; // ebx
  DWORD pSessionId; // [rsp+40h] [rbp-C0h] BYREF
  DWORD v27; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v28; // [rsp+50h] [rbp-B0h] BYREF
  ULONG ProcessInformationLength; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE ProcessHandle; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v31; // [rsp+68h] [rbp-98h] BYREF
  void *Block; // [rsp+70h] [rbp-90h]
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+78h] [rbp-88h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+90h] [rbp-70h] BYREF
  __int16 *v35; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  DWORD *v37; // [rsp+B0h] [rbp-50h]
  __int64 v38; // [rsp+B8h] [rbp-48h]
  DWORD *v39; // [rsp+C0h] [rbp-40h]
  __int64 v40; // [rsp+C8h] [rbp-38h]
  HANDLE *p_ProcessHandle; // [rsp+D0h] [rbp-30h]
  __int64 v42; // [rsp+D8h] [rbp-28h]
  __int64 *v43; // [rsp+E0h] [rbp-20h]
  __int64 v44; // [rsp+E8h] [rbp-18h]
  __int64 *v45; // [rsp+F0h] [rbp-10h]
  __int64 v46; // [rsp+F8h] [rbp-8h]

  v5 = I_RpcBindingInqLocalClientPID(0, (unsigned int *)a2);
  if ( v5 > 0 )
    v5 = (unsigned __int16)v5 | 0x80070000;
  if ( v5 < 0 )
  {
    if ( (unsigned int)dword_1800DA020 > 5 )
    {
      if ( a1 )
      {
        v24 = -1;
        do
          ++v24;
        while ( *((_BYTE *)a1 + v24) );
        v25 = v24 + 1;
      }
      else
      {
        a1 = (DWORD *)&word_1800A4196;
        v25 = 1;
      }
      v39 = a1;
      v37 = (DWORD *)"Dump RPC Caller";
      *(_DWORD *)&EventDescriptor.Level = 5125;
      UserData.Ptr = (ULONGLONG)off_1800DA028;
      v40 = v25;
      v38 = 16;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = *(unsigned __int16 *)off_1800DA028;
      v35 = (__int16 *)&dword_1800C8C14;
      UserData.Reserved = 2;
      v36 = 0x10000001ELL;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 4u, &UserData);
    }
  }
  else
  {
    v6 = *a2;
    pSessionId = -1;
    ProcessIdToSessionId(v6, &pSessionId);
    v7 = OpenProcess(0x400u, 0, *a2);
    ProcessHandle = v7;
    v8 = &word_1800A4196;
    v9 = -1;
    if ( !v7 )
      goto LABEL_29;
    ProcessInformationLength = 0;
    v10 = 0;
    if ( NtQueryInformationProcess(v7, ProcessImageFileMapping|ProcessUserModeIOPL, 0, 0, &ProcessInformationLength) == -1073741820
      && ProcessInformationLength > 0x10 )
    {
      Block = operator new(ProcessInformationLength);
      if ( NtQueryInformationProcess(
             ProcessHandle,
             ProcessImageFileMapping|ProcessUserModeIOPL,
             Block,
             ProcessInformationLength,
             0) >= 0 )
      {
        v11 = Block;
        if ( (unsigned int)dword_1800DA020 > 5 )
        {
          v12 = (__int64 *)*((_QWORD *)Block + 1);
          v28 = *(unsigned int *)a2;
          v31 = pSessionId;
          v45 = &v28;
          v43 = &v31;
          v46 = 8;
          v44 = 8;
          if ( v12 )
          {
            v13 = -1;
            do
              v14 = *((_WORD *)v12 + ++v13) == 0;
            while ( !v14 );
            v15 = 2 * v13 + 2;
          }
          else
          {
            v12 = &qword_1800A3968;
            v15 = 2;
          }
          p_ProcessHandle = (HANDLE *)v12;
          v42 = v15;
          if ( a1 )
          {
            v16 = (const unsigned __int16 *)a1;
            v17 = -1;
            do
              ++v17;
            while ( *((_BYTE *)a1 + v17) );
            v18 = v17 + 1;
          }
          else
          {
            v16 = &word_1800A4196;
            v18 = 1;
          }
          v40 = v18;
          v39 = (DWORD *)v16;
          v37 = (DWORD *)"Dump RPC Caller";
          *(_DWORD *)&EventDescriptor.Level = 5125;
          UserData.Ptr = (ULONGLONG)off_1800DA028;
          v38 = 16;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          EventDescriptor.Keyword = 0;
          UserData.Size = *(unsigned __int16 *)off_1800DA028;
          v35 = (__int16 *)byte_1800C8BC1;
          UserData.Reserved = 2;
          v36 = 0x100000047LL;
          v27 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 7u, &UserData);
        }
        v19 = (__int16 *)v11[1];
        LODWORD(v28) = *a2;
        v27 = pSessionId;
        v20 = -1;
        do
          ++v20;
        while ( *((_BYTE *)a1 + v20) );
        UserData.Ptr = (ULONGLONG)a1;
        UserData.Size = v20 + 1;
        v21 = -1;
        UserData.Reserved = 0;
        do
          v14 = v19[++v21] == 0;
        while ( !v14 );
        v36 = (unsigned int)(2 * v21 + 2);
        v37 = &v27;
        v39 = (DWORD *)&v28;
        v35 = v19;
        v38 = 4;
        v40 = 4;
        if ( byte_1800DD6B8 )
        {
          EventDescriptor = 0;
          EtwEventWriteFull(qword_1800DD6B0, ";", 0, 0, 0, 4, &UserData);
        }
        v10 = 1;
      }
      operator delete(Block);
    }
    CloseHandle(ProcessHandle);
    if ( !v10 )
    {
LABEL_29:
      if ( (unsigned int)dword_1800DA020 > 5 )
      {
        v31 = *(unsigned int *)a2;
        ProcessHandle = (HANDLE)pSessionId;
        v43 = &v31;
        p_ProcessHandle = &ProcessHandle;
        v44 = 8;
        v42 = 8;
        if ( a1 )
        {
          v8 = (const unsigned __int16 *)a1;
          v22 = -1;
          do
            ++v22;
          while ( *((_BYTE *)a1 + v22) );
          v23 = v22 + 1;
        }
        else
        {
          v23 = 1;
        }
        v40 = v23;
        *(_DWORD *)&EventDescriptor.Level = 5125;
        UserData.Ptr = (ULONGLONG)off_1800DA028;
        v37 = (DWORD *)"Dump RPC Caller";
        v39 = (DWORD *)v8;
        v38 = 16;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 0;
        UserData.Size = *(unsigned __int16 *)off_1800DA028;
        v35 = &word_1800C8C3E;
        UserData.Reserved = 2;
        v36 = 0x10000003ALL;
        LODWORD(v28) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 6u, &UserData);
      }
      v27 = *a2;
      LODWORD(v28) = pSessionId;
      UserData.Ptr = (ULONGLONG)a1;
      do
        v14 = *((_BYTE *)a1 + ++v9) == 0;
      while ( !v14 );
      UserData.Size = v9 + 1;
      v35 = L" ";
      v37 = (DWORD *)&v28;
      v39 = &v27;
      UserData.Reserved = 0;
      v36 = 4;
      v38 = 4;
      v40 = 4;
      if ( byte_1800DD6B8 )
      {
        EventDescriptor = 0;
        EtwEventWriteFull(qword_1800DD6B0, ";", 0, 0, 0, 4, &UserData);
      }
    }
  }
}

```

## disassembly

```asm
0x18000d0a0  push    rbp
0x18000d0a2  push    rdi
0x18000d0a3  push    r15
0x18000d0a5  lea     rbp, [rsp-20h]
0x18000d0aa  sub     rsp, 120h
0x18000d0b1  mov     rax, cs:__security_cookie
0x18000d0b8  xor     rax, rsp
0x18000d0bb  mov     [rbp+30h+var_30], rax
0x18000d0bf  mov     rdi, rcx
0x18000d0c2  mov     r15, rdx
0x18000d0c5  xor     ecx, ecx; Binding
0x18000d0c7  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18000d0cd  test    eax, eax
0x18000d0cf  jle     short loc_18000D0D9
0x18000d0d1  movzx   eax, ax
0x18000d0d4  or      eax, 80070000h
0x18000d0d9  mov     [rsp+130h+arg_0], rbx
0x18000d0e1  mov     [rsp+130h+arg_10], rsi
0x18000d0e9  mov     [rsp+130h+arg_18], r12
0x18000d0f1  mov     [rsp+130h+var_18], r13
0x18000d0f9  test    eax, eax
0x18000d0fb  js      loc_18000D5A3
0x18000d101  mov     ecx, [r15]; dwProcessId
0x18000d104  lea     rdx, [rsp+130h+pSessionId]; pSessionId
0x18000d109  mov     [rsp+130h+pSessionId], 0FFFFFFFFh
0x18000d111  call    cs:__imp_ProcessIdToSessionId
0x18000d117  mov     r8d, [r15]; dwProcessId
0x18000d11a  xor     edx, edx; bInheritHandle
0x18000d11c  mov     ecx, 400h; dwDesiredAccess
0x18000d121  call    cs:__imp_OpenProcess
0x18000d127  xor     esi, esi
0x18000d129  mov     [rsp+130h+ProcessHandle], rax
0x18000d12e  lea     r12, word_1800A4196
0x18000d135  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000d13c  lea     rdx, aDumpRpcCaller; "Dump RPC Caller"
0x18000d143  lea     r13, _TraceLoggingMetadataEnd
0x18000d14a  lea     r8, _TraceLoggingMetadata
0x18000d151  test    rax, rax
0x18000d154  jz      loc_18000D409
0x18000d15a  lea     rcx, [rsp+130h+ProcessInformationLength]
0x18000d15f  mov     [rsp+130h+var_20], r14
0x18000d167  mov     [rsp+130h+ReturnLength], rcx; ReturnLength
0x18000d16c  xor     r9d, r9d; ProcessInformationLength
0x18000d16f  mov     rcx, rax; ProcessHandle
0x18000d172  mov     [rsp+130h+ProcessInformationLength], esi
0x18000d176  xor     r8d, r8d; ProcessInformation
0x18000d179  mov     edx, 3Ch ; '<'; ProcessInformationClass
0x18000d17e  mov     r14d, esi
0x18000d181  call    cs:__imp_NtQueryInformationProcess
0x18000d187  cmp     eax, 0C0000004h
0x18000d18c  jnz     loc_18000D3DF
0x18000d192  mov     eax, [rsp+130h+ProcessInformationLength]
0x18000d196  cmp     eax, 10h
0x18000d199  jbe     loc_18000D3DF
0x18000d19f  mov     ecx, eax; Size
0x18000d1a1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000d1a6  mov     r9d, [rsp+130h+ProcessInformationLength]; ProcessInformationLength
0x18000d1ab  mov     r8, rax; ProcessInformation
0x18000d1ae  mov     rcx, [rsp+130h+ProcessHandle]; ProcessHandle
0x18000d1b3  mov     edx, 3Ch ; '<'; ProcessInformationClass
0x18000d1b8  mov     [rsp+130h+Block], rax
0x18000d1bd  mov     [rsp+130h+ReturnLength], rsi; ReturnLength
0x18000d1c2  call    cs:__imp_NtQueryInformationProcess
0x18000d1c8  or      eax, 10000000h
0x18000d1cd  jl      loc_18000D3D5
0x18000d1d3  mov     ecx, cs:dword_1800DA020
0x18000d1d9  mov     r14, [rsp+130h+Block]
0x18000d1de  cmp     ecx, 5
0x18000d1e1  jbe     loc_18000D31C
0x18000d1e7  mov     eax, [r15]
0x18000d1ea  mov     rcx, [r14+8]
0x18000d1ee  mov     [rsp+130h+var_E0], rax
0x18000d1f3  mov     eax, [rsp+130h+pSessionId]
0x18000d1f7  mov     [rsp+130h+var_C8], rax
0x18000d1fc  lea     rax, [rsp+130h+var_E0]
0x18000d201  mov     [rbp+30h+var_40], rax
0x18000d205  lea     rax, [rsp+130h+var_C8]
0x18000d20a  mov     [rbp+30h+var_50], rax
0x18000d20e  mov     [rbp+30h+var_38], 8
0x18000d216  mov     [rbp+30h+var_48], 8
0x18000d21e  test    rcx, rcx
0x18000d221  jz      short loc_18000D244
0x18000d223  mov     rax, rbx
0x18000d226  nop     word ptr [rax+rax+00000000h]
0x18000d230  cmp     [rcx+rax*2+2], si
0x18000d235  lea     rax, [rax+1]
0x18000d239  jnz     short loc_18000D230
0x18000d23b  lea     eax, ds:2[rax*2]
0x18000d242  jmp     short loc_18000D250
0x18000d244  lea     rcx, qword_1800A3968
0x18000d24b  mov     eax, 2
0x18000d250  mov     [rbp+30h+var_60], rcx
0x18000d254  mov     dword ptr [rbp+30h+var_58], eax
0x18000d257  mov     dword ptr [rbp+30h+var_58+4], esi
0x18000d25a  test    rdi, rdi
0x18000d25d  jz      short loc_18000D272
0x18000d25f  mov     rcx, rdi
0x18000d262  mov     rax, rbx
0x18000d265  inc     rax
0x18000d268  cmp     [rdi+rax], sil
0x18000d26c  jnz     short loc_18000D265
0x18000d26e  inc     eax
0x18000d270  jmp     short loc_18000D27A
0x18000d272  mov     rcx, r12
0x18000d275  mov     eax, 1
0x18000d27a  mov     dword ptr [rbp+30h+var_68], eax
0x18000d27d  lea     rdx, [rsp+130h+EventDescriptor]; EventDescriptor
0x18000d282  mov     [rbp+30h+var_70], rcx
0x18000d286  lea     rax, aDumpRpcCaller; "Dump RPC Caller"
0x18000d28d  mov     [rbp+30h+var_80], rax
0x18000d291  lea     rcx, _TraceLoggingMetadata
0x18000d298  movzx   eax, cs:word_1800C8BB7
0x18000d29f  xor     r9d, r9d; RelatedActivityId
0x18000d2a2  mov     dword ptr [rsp+130h+EventDescriptor.Level], eax
0x18000d2a6  xor     r8d, r8d; ActivityId
0x18000d2a9  mov     rax, cs:off_1800DA028
0x18000d2b0  mov     [rbp+30h+var_A0.Ptr], rax
0x18000d2b4  mov     dword ptr [rbp+30h+var_68+4], esi
0x18000d2b7  mov     [rbp+30h+var_78], 10h
0x18000d2bf  mov     dword ptr [rsp+130h+EventDescriptor.Id], 0B000000h
0x18000d2c7  mov     [rbp+30h+EventDescriptor.Keyword], rsi
0x18000d2cb  movzx   eax, word ptr [rax]
0x18000d2ce  mov     [rbp+30h+var_A0.Size], eax
0x18000d2d1  lea     rax, byte_1800C8BC1
0x18000d2d8  mov     [rbp+30h+var_90], rax
0x18000d2dc  mov     rax, r13
0x18000d2df  sub     eax, ecx
0x18000d2e1  mov     dword ptr [rbp+30h+var_A0.0Ch], 2
0x18000d2e8  mov     dword ptr [rbp+30h+var_88], 47h ; 'G'
0x18000d2ef  mov     dword ptr [rbp+30h+var_88+4], 1
0x18000d2f6  mov     [rsp+130h+var_E8], eax
0x18000d2fa  mov     eax, [rsp+130h+var_E8]
0x18000d2fe  mov     rcx, cs:RegHandle; RegHandle
0x18000d305  lea     rax, [rbp+30h+var_A0]
0x18000d309  mov     [rsp+130h+UserData], rax; UserData
0x18000d30e  mov     dword ptr [rsp+130h+ReturnLength], 7; UserDataCount
0x18000d316  call    cs:__imp_EventWriteTransfer
0x18000d31c  mov     eax, [r15]
0x18000d31f  mov     rcx, [r14+8]
0x18000d323  mov     dword ptr [rsp+130h+var_E0], eax
0x18000d327  mov     eax, [rsp+130h+pSessionId]
0x18000d32b  mov     [rsp+130h+var_E8], eax
0x18000d32f  mov     rax, rbx
0x18000d332  inc     rax
0x18000d335  cmp     [rdi+rax], sil
0x18000d339  jnz     short loc_18000D332
0x18000d33b  inc     eax
0x18000d33d  mov     [rbp+30h+var_A0.Ptr], rdi
0x18000d341  mov     [rbp+30h+var_A0.Size], eax
0x18000d344  mov     rax, rbx
0x18000d347  mov     dword ptr [rbp+30h+var_A0.0Ch], esi
0x18000d34a  nop     word ptr [rax+rax+00h]
0x18000d350  cmp     [rcx+rax*2+2], si
0x18000d355  lea     rax, [rax+1]
0x18000d359  jnz     short loc_18000D350
0x18000d35b  cmp     cs:byte_1800DD6B8, sil
0x18000d362  lea     eax, ds:2[rax*2]
0x18000d369  mov     dword ptr [rbp+30h+var_88], eax
0x18000d36c  lea     rax, [rsp+130h+var_E8]
0x18000d371  mov     [rbp+30h+var_80], rax
0x18000d375  lea     rax, [rsp+130h+var_E0]
0x18000d37a  mov     [rbp+30h+var_70], rax
0x18000d37e  mov     [rbp+30h+var_90], rcx
0x18000d382  mov     dword ptr [rbp+30h+var_88+4], esi
0x18000d385  mov     [rbp+30h+var_78], 4
0x18000d38d  mov     [rbp+30h+var_68], 4
0x18000d395  jz      short loc_18000D3CF
0x18000d397  mov     rcx, cs:qword_1800DD6B0
0x18000d39e  lea     rax, [rbp+30h+var_A0]
0x18000d3a2  mov     [rsp+130h+var_100], rax
0x18000d3a7  lea     rdx, EVENT_RPC_CALLER_INFO; ";"
0x18000d3ae  xorps   xmm0, xmm0
0x18000d3b1  mov     dword ptr [rsp+130h+UserData], 4
0x18000d3b9  xor     r8d, r8d
0x18000d3bc  mov     [rsp+130h+ReturnLength], rsi
0x18000d3c1  xor     r9d, r9d
0x18000d3c4  movups  xmmword ptr [rsp+130h+EventDescriptor.Id], xmm0
0x18000d3c9  call    cs:__imp_EtwEventWriteFull
0x18000d3cf  mov     r14d, 1
0x18000d3d5  mov     rcx, [rsp+130h+Block]; Block
0x18000d3da  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000d3df  mov     rcx, [rsp+130h+ProcessHandle]; hObject
0x18000d3e4  call    cs:__imp_CloseHandle
0x18000d3ea  test    r14d, r14d
0x18000d3ed  mov     r14, [rsp+130h+var_20]
0x18000d3f5  jnz     loc_18000D683
0x18000d3fb  lea     rdx, aDumpRpcCaller; "Dump RPC Caller"
0x18000d402  lea     r8, _TraceLoggingMetadata
0x18000d409  mov     eax, cs:dword_1800DA020
0x18000d40f  cmp     eax, 5
0x18000d412  jbe     loc_18000D4FB
0x18000d418  mov     eax, [r15]
0x18000d41b  mov     [rsp+130h+var_C8], rax
0x18000d420  mov     eax, [rsp+130h+pSessionId]
0x18000d424  mov     [rsp+130h+ProcessHandle], rax
0x18000d429  lea     rax, [rsp+130h+var_C8]
0x18000d42e  mov     [rbp+30h+var_50], rax
0x18000d432  lea     rax, [rsp+130h+ProcessHandle]
0x18000d437  mov     [rbp+30h+var_60], rax
0x18000d43b  mov     [rbp+30h+var_48], 8
0x18000d443  mov     [rbp+30h+var_58], 8
0x18000d44b  test    rdi, rdi
0x18000d44e  jz      short loc_18000D463
0x18000d450  mov     r12, rdi
0x18000d453  mov     rax, rbx
0x18000d456  inc     rax
0x18000d459  cmp     [rdi+rax], sil
0x18000d45d  jnz     short loc_18000D456
0x18000d45f  inc     eax
0x18000d461  jmp     short loc_18000D468
0x18000d463  mov     eax, 1
0x18000d468  mov     dword ptr [rbp+30h+var_68], eax
0x18000d46b  sub     r13d, r8d
0x18000d46e  movzx   eax, cs:word_1800C8C34
0x18000d475  xor     r9d, r9d; RelatedActivityId
0x18000d478  mov     dword ptr [rsp+130h+EventDescriptor.Level], eax
0x18000d47c  xor     r8d, r8d; ActivityId
0x18000d47f  mov     rax, cs:off_1800DA028
0x18000d486  mov     [rbp+30h+var_A0.Ptr], rax
0x18000d48a  mov     [rbp+30h+var_80], rdx
0x18000d48e  lea     rdx, [rsp+130h+EventDescriptor]; EventDescriptor
0x18000d493  mov     [rbp+30h+var_70], r12
0x18000d497  mov     dword ptr [rbp+30h+var_68+4], esi
0x18000d49a  mov     [rbp+30h+var_78], 10h
0x18000d4a2  mov     dword ptr [rsp+130h+EventDescriptor.Id], 0B000000h
0x18000d4aa  mov     [rbp+30h+EventDescriptor.Keyword], rsi
0x18000d4ae  movzx   eax, word ptr [rax]
0x18000d4b1  mov     [rbp+30h+var_A0.Size], eax
0x18000d4b4  lea     rax, word_1800C8C3E
0x18000d4bb  mov     [rbp+30h+var_90], rax
0x18000d4bf  mov     dword ptr [rbp+30h+var_A0.0Ch], 2
0x18000d4c6  mov     dword ptr [rbp+30h+var_88], 3Ah ; ':'
0x18000d4cd  mov     dword ptr [rbp+30h+var_88+4], 1
0x18000d4d4  mov     dword ptr [rsp+130h+var_E0], r13d
0x18000d4d9  mov     eax, dword ptr [rsp+130h+var_E0]
0x18000d4dd  mov     rcx, cs:RegHandle; RegHandle
0x18000d4e4  lea     rax, [rbp+30h+var_A0]
0x18000d4e8  mov     [rsp+130h+UserData], rax; UserData
0x18000d4ed  mov     dword ptr [rsp+130h+ReturnLength], 6; UserDataCount
0x18000d4f5  call    cs:__imp_EventWriteTransfer
0x18000d4fb  mov     eax, [r15]
0x18000d4fe  mov     [rsp+130h+var_E8], eax
0x18000d502  mov     eax, [rsp+130h+pSessionId]
0x18000d506  mov     dword ptr [rsp+130h+var_E0], eax
0x18000d50a  mov     [rbp+30h+var_A0.Ptr], rdi
0x18000d50e  xchg    ax, ax
0x18000d510  cmp     [rdi+rbx+1], sil
0x18000d515  lea     rbx, [rbx+1]
0x18000d519  jnz     short loc_18000D510
0x18000d51b  cmp     cs:byte_1800DD6B8, sil
0x18000d522  lea     eax, [rbx+1]
0x18000d525  mov     [rbp+30h+var_A0.Size], eax
0x18000d528  lea     rax, asc_1800BA598; " "
0x18000d52f  mov     [rbp+30h+var_90], rax
0x18000d533  lea     rax, [rsp+130h+var_E0]
0x18000d538  mov     [rbp+30h+var_80], rax
0x18000d53c  lea     rax, [rsp+130h+var_E8]
0x18000d541  mov     [rbp+30h+var_70], rax
0x18000d545  mov     dword ptr [rbp+30h+var_A0.0Ch], esi
0x18000d548  mov     [rbp+30h+var_88], 4
0x18000d550  mov     [rbp+30h+var_78], 4
0x18000d558  mov     [rbp+30h+var_68], 4
0x18000d560  jz      loc_18000D683
0x18000d566  mov     rcx, cs:qword_1800DD6B0
0x18000d56d  lea     rax, [rbp+30h+var_A0]
0x18000d571  mov     [rsp+130h+var_100], rax
0x18000d576  lea     rdx, EVENT_RPC_CALLER_INFO; ";"
0x18000d57d  xorps   xmm0, xmm0
0x18000d580  mov     dword ptr [rsp+130h+UserData], 4
0x18000d588  xor     r8d, r8d
0x18000d58b  mov     [rsp+130h+ReturnLength], rsi
0x18000d590  xor     r9d, r9d
0x18000d593  movups  xmmword ptr [rsp+130h+EventDescriptor.Id], xmm0
0x18000d598  call    cs:__imp_EtwEventWriteFull
0x18000d59e  jmp     loc_18000D683
0x18000d5a3  mov     eax, cs:dword_1800DA020
0x18000d5a9  cmp     eax, 5
0x18000d5ac  jbe     loc_18000D683
0x18000d5b2  test    rdi, rdi
0x18000d5b5  jz      short loc_18000D5CD
0x18000d5b7  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18000d5be  xchg    ax, ax
0x18000d5c0  inc     rbx
0x18000d5c3  cmp     byte ptr [rdi+rbx], 0
0x18000d5c7  jnz     short loc_18000D5C0
0x18000d5c9  inc     ebx
0x18000d5cb  jmp     short loc_18000D5D9
0x18000d5cd  lea     rdi, word_1800A4196
0x18000d5d4  mov     ebx, 1
0x18000d5d9  lea     rax, aDumpRpcCaller; "Dump RPC Caller"
0x18000d5e0  mov     [rbp+30h+var_70], rdi
0x18000d5e4  mov     [rbp+30h+var_80], rax
0x18000d5e8  lea     r13, _TraceLoggingMetadataEnd
0x18000d5ef  movzx   eax, cs:word_1800C8C0A
0x18000d5f6  lea     rdx, [rsp+130h+EventDescriptor]; EventDescriptor
0x18000d5fb  mov     dword ptr [rsp+130h+EventDescriptor.Level], eax
0x18000d5ff  xor     esi, esi
0x18000d601  mov     rax, cs:off_1800DA028
0x18000d608  xor     r9d, r9d; RelatedActivityId
0x18000d60b  mov     [rbp+30h+var_A0.Ptr], rax
  ... truncated ...
```
