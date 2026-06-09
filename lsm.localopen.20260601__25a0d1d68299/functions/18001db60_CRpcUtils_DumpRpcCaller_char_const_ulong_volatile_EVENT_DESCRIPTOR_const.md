# CRpcUtils::DumpRpcCaller(char const *,ulong volatile &,_EVENT_DESCRIPTOR const &)

- ea: `0x18001db60`
- end: `0x18001e1b6`
- name: `?DumpRpcCaller@CRpcUtils@@SAXPEBDAECKAEBU_EVENT_DESCRIPTOR@@@Z`
- size: `1622`
- prototype: `void __fastcall(const char *, volatile unsigned int *, const struct _EVENT_DESCRIPTOR *)`
- caller_count: `5`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x18001d1c0`
- `0x180022290`
- `0x18005e678`
- `0x18005f690`
- `0x180062120`

## callees

- `0x18001db60`
- `0x18004e850`
- `0x18004eca4`
- `0x18004f174`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x18001dc53`
- `ntdll!NtQueryInformationProcess` at `0x18001dc9a`
- `ntdll!NtQueryInformationProcess` at `0x18001dc53`
- `ntdll!NtQueryInformationProcess` at `0x18001dc9a`
- `ntdll!EtwEventWriteFull` at `0x18001dea9`
- `ntdll!EtwEventWriteFull` at `0x18001e088`
- `ntdll!EtwEventWriteFull` at `0x18001dea9`
- `ntdll!EtwEventWriteFull` at `0x18001e088`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18001dbd7`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18001dbd7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001deca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001deca`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18001db87`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18001db87`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001dbed`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001dbed`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001ddf1`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001dfe1`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001e171`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001ddf1`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001dfe1`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18001e171`

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
  int *v12; // rcx
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
    if ( (unsigned int)dword_1800DF020 > 5 )
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
        a1 = (DWORD *)&word_1800A93F6;
        v25 = 1;
      }
      v39 = a1;
      v37 = (DWORD *)"Dump RPC Caller";
      *(_DWORD *)&EventDescriptor.Level = 5125;
      UserData.Ptr = (ULONGLONG)off_1800DF028;
      v40 = v25;
      v38 = 16;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = *(unsigned __int16 *)off_1800DF028;
      v35 = (__int16 *)&dword_1800CDD9C;
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
    v8 = &word_1800A93F6;
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
        if ( (unsigned int)dword_1800DF020 > 5 )
        {
          v12 = (int *)*((_QWORD *)Block + 1);
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
            v12 = &dword_1800A8ADC;
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
            v16 = &word_1800A93F6;
            v18 = 1;
          }
          v40 = v18;
          v39 = (DWORD *)v16;
          v37 = (DWORD *)"Dump RPC Caller";
          *(_DWORD *)&EventDescriptor.Level = 5125;
          UserData.Ptr = (ULONGLONG)off_1800DF028;
          v38 = 16;
          *(_DWORD *)&EventDescriptor.Id = 184549376;
          EventDescriptor.Keyword = 0;
          UserData.Size = *(unsigned __int16 *)off_1800DF028;
          v35 = (__int16 *)byte_1800CDD49;
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
        if ( byte_1800E26C8 )
        {
          EventDescriptor = 0;
          EtwEventWriteFull(qword_1800E26C0, ";", 0, 0, 0, 4, &UserData);
        }
        v10 = 1;
      }
      operator delete(Block);
    }
    CloseHandle(ProcessHandle);
    if ( !v10 )
    {
LABEL_29:
      if ( (unsigned int)dword_1800DF020 > 5 )
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
        UserData.Ptr = (ULONGLONG)off_1800DF028;
        v37 = (DWORD *)"Dump RPC Caller";
        v39 = (DWORD *)v8;
        v38 = 16;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 0;
        UserData.Size = *(unsigned __int16 *)off_1800DF028;
        v35 = &word_1800CDDC6;
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
      if ( byte_1800E26C8 )
      {
        EventDescriptor = 0;
        EtwEventWriteFull(qword_1800E26C0, ";", 0, 0, 0, 4, &UserData);
      }
    }
  }
}

```

## disassembly

```asm
0x18001db60  push    rbp
0x18001db62  push    rdi
0x18001db63  push    r15
0x18001db65  lea     rbp, [rsp-20h]
0x18001db6a  sub     rsp, 120h
0x18001db71  mov     rax, cs:__security_cookie
0x18001db78  xor     rax, rsp
0x18001db7b  mov     [rbp+30h+var_30], rax
0x18001db7f  mov     rdi, rcx
0x18001db82  mov     r15, rdx
0x18001db85  xor     ecx, ecx; Binding
0x18001db87  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18001db8e  nop     dword ptr [rax+rax+00h]
0x18001db93  test    eax, eax
0x18001db95  jle     short loc_18001DB9F
0x18001db97  movzx   eax, ax
0x18001db9a  or      eax, 80070000h
0x18001db9f  mov     [rsp+130h+arg_0], rbx
0x18001dba7  mov     [rsp+130h+arg_10], rsi
0x18001dbaf  mov     [rsp+130h+arg_18], r12
0x18001dbb7  mov     [rsp+130h+var_18], r13
0x18001dbbf  test    eax, eax
0x18001dbc1  js      loc_18001E099
0x18001dbc7  mov     ecx, [r15]; dwProcessId
0x18001dbca  lea     rdx, [rsp+130h+pSessionId]; pSessionId
0x18001dbcf  mov     [rsp+130h+pSessionId], 0FFFFFFFFh
0x18001dbd7  call    cs:__imp_ProcessIdToSessionId
0x18001dbde  nop     dword ptr [rax+rax+00h]
0x18001dbe3  mov     r8d, [r15]; dwProcessId
0x18001dbe6  xor     edx, edx; bInheritHandle
0x18001dbe8  mov     ecx, 400h; dwDesiredAccess
0x18001dbed  call    cs:__imp_OpenProcess
0x18001dbf4  nop     dword ptr [rax+rax+00h]
0x18001dbf9  xor     esi, esi
0x18001dbfb  mov     [rsp+130h+ProcessHandle], rax
0x18001dc00  lea     r12, word_1800A93F6
0x18001dc07  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18001dc0e  lea     rdx, aDumpRpcCaller; "Dump RPC Caller"
0x18001dc15  lea     r13, _TraceLoggingMetadataEnd
0x18001dc1c  lea     r8, _TraceLoggingMetadata
0x18001dc23  test    rax, rax
0x18001dc26  jz      loc_18001DEF5
0x18001dc2c  lea     rcx, [rsp+130h+ProcessInformationLength]
0x18001dc31  mov     [rsp+130h+var_20], r14
0x18001dc39  mov     [rsp+130h+ReturnLength], rcx; ReturnLength
0x18001dc3e  xor     r9d, r9d; ProcessInformationLength
0x18001dc41  mov     rcx, rax; ProcessHandle
0x18001dc44  mov     [rsp+130h+ProcessInformationLength], esi
0x18001dc48  xor     r8d, r8d; ProcessInformation
0x18001dc4b  mov     edx, 3Ch ; '<'; ProcessInformationClass
0x18001dc50  mov     r14d, esi
0x18001dc53  call    cs:__imp_NtQueryInformationProcess
0x18001dc5a  nop     dword ptr [rax+rax+00h]
0x18001dc5f  cmp     eax, 0C0000004h
0x18001dc64  jnz     loc_18001DEC5
0x18001dc6a  mov     eax, [rsp+130h+ProcessInformationLength]
0x18001dc6e  cmp     eax, 10h
0x18001dc71  jbe     loc_18001DEC5
0x18001dc77  mov     ecx, eax; Size
0x18001dc79  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001dc7e  mov     r9d, [rsp+130h+ProcessInformationLength]; ProcessInformationLength
0x18001dc83  mov     r8, rax; ProcessInformation
0x18001dc86  mov     rcx, [rsp+130h+ProcessHandle]; ProcessHandle
0x18001dc8b  mov     edx, 3Ch ; '<'; ProcessInformationClass
0x18001dc90  mov     [rsp+130h+Block], rax
0x18001dc95  mov     [rsp+130h+ReturnLength], rsi; ReturnLength
0x18001dc9a  call    cs:__imp_NtQueryInformationProcess
0x18001dca1  nop     dword ptr [rax+rax+00h]
0x18001dca6  or      eax, 10000000h
0x18001dcab  jl      loc_18001DEBB
0x18001dcb1  mov     ecx, cs:dword_1800DF020
0x18001dcb7  mov     r14, [rsp+130h+Block]
0x18001dcbc  cmp     ecx, 5
0x18001dcbf  jbe     loc_18001DDFD
0x18001dcc5  mov     eax, [r15]
0x18001dcc8  mov     rcx, [r14+8]
0x18001dccc  mov     [rsp+130h+var_E0], rax
0x18001dcd1  mov     eax, [rsp+130h+pSessionId]
0x18001dcd5  mov     [rsp+130h+var_C8], rax
0x18001dcda  lea     rax, [rsp+130h+var_E0]
0x18001dcdf  mov     [rbp+30h+var_40], rax
0x18001dce3  lea     rax, [rsp+130h+var_C8]
0x18001dce8  mov     [rbp+30h+var_50], rax
0x18001dcec  mov     [rbp+30h+var_38], 8
0x18001dcf4  mov     [rbp+30h+var_48], 8
0x18001dcfc  test    rcx, rcx
0x18001dcff  jz      short loc_18001DD18
0x18001dd01  mov     rax, rbx
0x18001dd04  cmp     [rcx+rax*2+2], si
0x18001dd09  lea     rax, [rax+1]
0x18001dd0d  jnz     short loc_18001DD04
0x18001dd0f  lea     eax, ds:2[rax*2]
0x18001dd16  jmp     short loc_18001DD24
0x18001dd18  lea     rcx, dword_1800A8ADC
0x18001dd1f  mov     eax, 2
0x18001dd24  mov     [rbp+30h+var_60], rcx
0x18001dd28  mov     dword ptr [rbp+30h+var_58], eax
0x18001dd2b  mov     dword ptr [rbp+30h+var_58+4], esi
0x18001dd2e  test    rdi, rdi
0x18001dd31  jz      short loc_18001DD4D
0x18001dd33  mov     rcx, rdi
0x18001dd36  mov     rax, rbx
0x18001dd39  nop     dword ptr [rax+00000000h]
0x18001dd40  inc     rax
0x18001dd43  cmp     [rdi+rax], sil
0x18001dd47  jnz     short loc_18001DD40
0x18001dd49  inc     eax
0x18001dd4b  jmp     short loc_18001DD55
0x18001dd4d  mov     rcx, r12
0x18001dd50  mov     eax, 1
0x18001dd55  mov     dword ptr [rbp+30h+var_68], eax
0x18001dd58  lea     rdx, [rsp+130h+EventDescriptor]; EventDescriptor
0x18001dd5d  mov     [rbp+30h+var_70], rcx
0x18001dd61  lea     rax, aDumpRpcCaller; "Dump RPC Caller"
0x18001dd68  mov     [rbp+30h+var_80], rax
0x18001dd6c  lea     rcx, _TraceLoggingMetadata
0x18001dd73  movzx   eax, cs:word_1800CDD3F
0x18001dd7a  xor     r9d, r9d; RelatedActivityId
0x18001dd7d  mov     dword ptr [rsp+130h+EventDescriptor.Level], eax
0x18001dd81  xor     r8d, r8d; ActivityId
0x18001dd84  mov     rax, cs:off_1800DF028
0x18001dd8b  mov     [rbp+30h+var_A0.Ptr], rax
0x18001dd8f  mov     dword ptr [rbp+30h+var_68+4], esi
0x18001dd92  mov     [rbp+30h+var_78], 10h
0x18001dd9a  mov     dword ptr [rsp+130h+EventDescriptor.Id], 0B000000h
0x18001dda2  mov     [rbp+30h+EventDescriptor.Keyword], rsi
0x18001dda6  movzx   eax, word ptr [rax]
0x18001dda9  mov     [rbp+30h+var_A0.Size], eax
0x18001ddac  lea     rax, byte_1800CDD49
0x18001ddb3  mov     [rbp+30h+var_90], rax
0x18001ddb7  mov     rax, r13
0x18001ddba  sub     eax, ecx
0x18001ddbc  mov     dword ptr [rbp+30h+var_A0.0Ch], 2
0x18001ddc3  mov     dword ptr [rbp+30h+var_88], 47h ; 'G'
0x18001ddca  mov     dword ptr [rbp+30h+var_88+4], 1
0x18001ddd1  mov     [rsp+130h+var_E8], eax
0x18001ddd5  mov     eax, [rsp+130h+var_E8]
0x18001ddd9  mov     rcx, cs:RegHandle; RegHandle
0x18001dde0  lea     rax, [rbp+30h+var_A0]
0x18001dde4  mov     [rsp+130h+UserData], rax; UserData
0x18001dde9  mov     dword ptr [rsp+130h+ReturnLength], 7; UserDataCount
0x18001ddf1  call    cs:__imp_EventWriteTransfer
0x18001ddf8  nop     dword ptr [rax+rax+00h]
0x18001ddfd  mov     eax, [r15]
0x18001de00  mov     rcx, [r14+8]
0x18001de04  mov     dword ptr [rsp+130h+var_E0], eax
0x18001de08  mov     eax, [rsp+130h+pSessionId]
0x18001de0c  mov     [rsp+130h+var_E8], eax
0x18001de10  mov     rax, rbx
0x18001de13  inc     rax
0x18001de16  cmp     [rdi+rax], sil
0x18001de1a  jnz     short loc_18001DE13
0x18001de1c  inc     eax
0x18001de1e  mov     [rbp+30h+var_A0.Ptr], rdi
0x18001de22  mov     [rbp+30h+var_A0.Size], eax
0x18001de25  mov     rax, rbx
0x18001de28  mov     dword ptr [rbp+30h+var_A0.0Ch], esi
0x18001de2b  nop     dword ptr [rax+rax+00h]
0x18001de30  cmp     [rcx+rax*2+2], si
0x18001de35  lea     rax, [rax+1]
0x18001de39  jnz     short loc_18001DE30
0x18001de3b  cmp     cs:byte_1800E26C8, sil
0x18001de42  lea     eax, ds:2[rax*2]
0x18001de49  mov     dword ptr [rbp+30h+var_88], eax
0x18001de4c  lea     rax, [rsp+130h+var_E8]
0x18001de51  mov     [rbp+30h+var_80], rax
0x18001de55  lea     rax, [rsp+130h+var_E0]
0x18001de5a  mov     [rbp+30h+var_70], rax
0x18001de5e  mov     [rbp+30h+var_90], rcx
0x18001de62  mov     dword ptr [rbp+30h+var_88+4], esi
0x18001de65  mov     [rbp+30h+var_78], 4
0x18001de6d  mov     [rbp+30h+var_68], 4
0x18001de75  jz      short loc_18001DEB5
0x18001de77  mov     rcx, cs:qword_1800E26C0
0x18001de7e  lea     rax, [rbp+30h+var_A0]
0x18001de82  mov     [rsp+130h+var_100], rax
0x18001de87  lea     rdx, EVENT_RPC_CALLER_INFO; ";"
0x18001de8e  xorps   xmm0, xmm0
0x18001de91  mov     dword ptr [rsp+130h+UserData], 4
0x18001de99  xor     r8d, r8d
0x18001de9c  mov     [rsp+130h+ReturnLength], rsi
0x18001dea1  xor     r9d, r9d
0x18001dea4  movups  xmmword ptr [rsp+130h+EventDescriptor.Id], xmm0
0x18001dea9  call    cs:__imp_EtwEventWriteFull
0x18001deb0  nop     dword ptr [rax+rax+00h]
0x18001deb5  mov     r14d, 1
0x18001debb  mov     rcx, [rsp+130h+Block]; Block
0x18001dec0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001dec5  mov     rcx, [rsp+130h+ProcessHandle]; hObject
0x18001deca  call    cs:__imp_CloseHandle
0x18001ded1  nop     dword ptr [rax+rax+00h]
0x18001ded6  test    r14d, r14d
0x18001ded9  mov     r14, [rsp+130h+var_20]
0x18001dee1  jnz     loc_18001E17D
0x18001dee7  lea     rdx, aDumpRpcCaller; "Dump RPC Caller"
0x18001deee  lea     r8, _TraceLoggingMetadata
0x18001def5  mov     eax, cs:dword_1800DF020
0x18001defb  cmp     eax, 5
0x18001defe  jbe     loc_18001DFED
0x18001df04  mov     eax, [r15]
0x18001df07  mov     [rsp+130h+var_C8], rax
0x18001df0c  mov     eax, [rsp+130h+pSessionId]
0x18001df10  mov     [rsp+130h+ProcessHandle], rax
0x18001df15  lea     rax, [rsp+130h+var_C8]
0x18001df1a  mov     [rbp+30h+var_50], rax
0x18001df1e  lea     rax, [rsp+130h+ProcessHandle]
0x18001df23  mov     [rbp+30h+var_60], rax
0x18001df27  mov     [rbp+30h+var_48], 8
0x18001df2f  mov     [rbp+30h+var_58], 8
0x18001df37  test    rdi, rdi
0x18001df3a  jz      short loc_18001DF4F
0x18001df3c  mov     r12, rdi
0x18001df3f  mov     rax, rbx
0x18001df42  inc     rax
0x18001df45  cmp     [rdi+rax], sil
0x18001df49  jnz     short loc_18001DF42
0x18001df4b  inc     eax
0x18001df4d  jmp     short loc_18001DF54
0x18001df4f  mov     eax, 1
0x18001df54  mov     dword ptr [rbp+30h+var_68], eax
0x18001df57  sub     r13d, r8d
0x18001df5a  movzx   eax, cs:word_1800CDDBC
0x18001df61  xor     r9d, r9d; RelatedActivityId
0x18001df64  mov     dword ptr [rsp+130h+EventDescriptor.Level], eax
0x18001df68  xor     r8d, r8d; ActivityId
0x18001df6b  mov     rax, cs:off_1800DF028
0x18001df72  mov     [rbp+30h+var_A0.Ptr], rax
0x18001df76  mov     [rbp+30h+var_80], rdx
0x18001df7a  lea     rdx, [rsp+130h+EventDescriptor]; EventDescriptor
0x18001df7f  mov     [rbp+30h+var_70], r12
0x18001df83  mov     dword ptr [rbp+30h+var_68+4], esi
0x18001df86  mov     [rbp+30h+var_78], 10h
0x18001df8e  mov     dword ptr [rsp+130h+EventDescriptor.Id], 0B000000h
0x18001df96  mov     [rbp+30h+EventDescriptor.Keyword], rsi
0x18001df9a  movzx   eax, word ptr [rax]
0x18001df9d  mov     [rbp+30h+var_A0.Size], eax
0x18001dfa0  lea     rax, word_1800CDDC6
0x18001dfa7  mov     [rbp+30h+var_90], rax
0x18001dfab  mov     dword ptr [rbp+30h+var_A0.0Ch], 2
0x18001dfb2  mov     dword ptr [rbp+30h+var_88], 3Ah ; ':'
0x18001dfb9  mov     dword ptr [rbp+30h+var_88+4], 1
0x18001dfc0  mov     dword ptr [rsp+130h+var_E0], r13d
0x18001dfc5  mov     eax, dword ptr [rsp+130h+var_E0]
0x18001dfc9  mov     rcx, cs:RegHandle; RegHandle
0x18001dfd0  lea     rax, [rbp+30h+var_A0]
0x18001dfd4  mov     [rsp+130h+UserData], rax; UserData
0x18001dfd9  mov     dword ptr [rsp+130h+ReturnLength], 6; UserDataCount
0x18001dfe1  call    cs:__imp_EventWriteTransfer
0x18001dfe8  nop     dword ptr [rax+rax+00h]
0x18001dfed  mov     eax, [r15]
0x18001dff0  mov     [rsp+130h+var_E8], eax
0x18001dff4  mov     eax, [rsp+130h+pSessionId]
0x18001dff8  mov     dword ptr [rsp+130h+var_E0], eax
0x18001dffc  mov     [rbp+30h+var_A0.Ptr], rdi
0x18001e000  cmp     [rdi+rbx+1], sil
0x18001e005  lea     rbx, [rbx+1]
0x18001e009  jnz     short loc_18001E000
0x18001e00b  cmp     cs:byte_1800E26C8, sil
0x18001e012  lea     eax, [rbx+1]
0x18001e015  mov     [rbp+30h+var_A0.Size], eax
0x18001e018  lea     rax, asc_1800BF6B8; " "
0x18001e01f  mov     [rbp+30h+var_90], rax
0x18001e023  lea     rax, [rsp+130h+var_E0]
0x18001e028  mov     [rbp+30h+var_80], rax
0x18001e02c  lea     rax, [rsp+130h+var_E8]
0x18001e031  mov     [rbp+30h+var_70], rax
0x18001e035  mov     dword ptr [rbp+30h+var_A0.0Ch], esi
0x18001e038  mov     [rbp+30h+var_88], 4
0x18001e040  mov     [rbp+30h+var_78], 4
0x18001e048  mov     [rbp+30h+var_68], 4
0x18001e050  jz      loc_18001E17D
0x18001e056  mov     rcx, cs:qword_1800E26C0
0x18001e05d  lea     rax, [rbp+30h+var_A0]
0x18001e061  mov     [rsp+130h+var_100], rax
0x18001e066  lea     rdx, EVENT_RPC_CALLER_INFO; ";"
0x18001e06d  xorps   xmm0, xmm0
0x18001e070  mov     dword ptr [rsp+130h+UserData], 4
0x18001e078  xor     r8d, r8d
0x18001e07b  mov     [rsp+130h+ReturnLength], rsi
0x18001e080  xor     r9d, r9d
0x18001e083  movups  xmmword ptr [rsp+130h+EventDescriptor.Id], xmm0
0x18001e088  call    cs:__imp_EtwEventWriteFull
0x18001e08f  nop     dword ptr [rax+rax+00h]
0x18001e094  jmp     loc_18001E17D
0x18001e099  mov     eax, cs:dword_1800DF020
0x18001e09f  cmp     eax, 5
0x18001e0a2  jbe     loc_18001E17D
0x18001e0a8  test    rdi, rdi
0x18001e0ab  jz      short loc_18001E0C1
0x18001e0ad  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18001e0b4  inc     rbx
0x18001e0b7  cmp     byte ptr [rdi+rbx], 0
0x18001e0bb  jnz     short loc_18001E0B4
0x18001e0bd  inc     ebx
0x18001e0bf  jmp     short loc_18001E0CD
0x18001e0c1  lea     rdi, word_1800A93F6
0x18001e0c8  mov     ebx, 1
0x18001e0cd  lea     rax, aDumpRpcCaller; "Dump RPC Caller"
0x18001e0d4  mov     [rbp+30h+var_70], rdi
0x18001e0d8  mov     [rbp+30h+var_80], rax
  ... truncated ...
```
