# PushClient::AttachClient(void *,ushort * *)

- ea: `0x180017cec`
- end: `0x180018059`
- name: `?AttachClient@PushClient@@QEAAJPEAXPEAPEAG@Z`
- size: `877`
- prototype: `__int64 __fastcall(PushClient *__hidden this, void *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001478c`

## callees

- `0x1800039f0`
- `0x1800043a8`
- `0x18000c5c8`
- `0x18000c63c`
- `0x180017cec`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180017ff5`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180017ff5`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180017f77`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180017f77`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180017e0f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180017e0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180017df8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180017df8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ea8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ef5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017e19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ea8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017ef5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017f08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017f20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017fb4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017ffe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018007`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018017`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017f08`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017f20`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017fb4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180017ffe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018007`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018017`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017fde`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017fde`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017fcb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017fcb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180017fec`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180017fec`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180017e9a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180017e9a`
- `ntdll!RtlNtStatusToDosError` at `0x180017e66`
- `ntdll!RtlNtStatusToDosError` at `0x180017e66`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180017eea`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180017eea`
- `RPCRT4!RpcRevertToSelfEx` at `0x180017e21`
- `RPCRT4!RpcRevertToSelfEx` at `0x180017e42`
- `RPCRT4!RpcRevertToSelfEx` at `0x180017e21`
- `RPCRT4!RpcRevertToSelfEx` at `0x180017e42`
- `RPCRT4!RpcImpersonateClient` at `0x180017dd8`
- `RPCRT4!RpcImpersonateClient` at `0x180017dd8`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180017ec5`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180017ec5`
- `api-ms-win-security-accesshlpr-l1-1-0!BuildSecurityDescriptorForSharingAccess` at `0x180017e5a`
- `api-ms-win-security-accesshlpr-l1-1-0!BuildSecurityDescriptorForSharingAccess` at `0x180017e5a`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180018027`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180018027`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall PushClient::AttachClient(PushClient *this, void *a2, unsigned __int16 **a3)
{
  HANDLE v6; // r12
  void *v7; // r13
  unsigned __int16 *v8; // r15
  signed int v9; // esi
  signed int LastError; // eax
  bool v11; // cc
  HANDLE CurrentThread; // rax
  RPC_STATUS v13; // eax
  NTSTATUS v14; // eax
  struct _SECURITY_ATTRIBUTES *v15; // rcx
  signed int v16; // eax
  bool v17; // cc
  HANDLE v18; // rax
  void *v19; // rcx
  __int64 v20; // rcx
  WCHAR *p_Name; // rax
  __int64 v22; // r8
  unsigned __int64 v23; // rbx
  unsigned __int16 *v24; // rax
  int v25; // ebx
  unsigned int Pid; // [rsp+20h] [rbp-E0h] BYREF
  void *TokenHandle; // [rsp+28h] [rbp-D8h] BYREF
  __int128 v29; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v30; // [rsp+40h] [rbp-C0h]
  unsigned __int16 **v31; // [rsp+48h] [rbp-B8h]
  unsigned __int16 v32[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v33; // [rsp+60h] [rbp-A0h]
  _OWORD v34[2]; // [rsp+70h] [rbp-90h]
  WCHAR Name; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v36[526]; // [rsp+92h] [rbp-6Eh] BYREF

  v31 = a3;
  Name = 0;
  v6 = 0;
  v7 = 0;
  v8 = 0;
  memset_0(v36, 0, 0x206u);
  TokenHandle = 0;
  v30 = 0;
  v29 = 0;
  v33 = *(_OWORD *)L"erMsgAvailableEvent%d";
  *(_OWORD *)v32 = *(_OWORD *)L"PushRouterMsgAvailableEvent%d";
  v34[0] = *(_OWORD *)L"ilableEvent%d";
  *(_OWORD *)((char *)v34 + 12) = *(_OWORD *)L"Event%d";
  if ( !a3 )
  {
    v9 = -2147467261;
    goto LABEL_41;
  }
  ++g_cPROpenUniqueEvent;
  v9 = StringCchPrintfW(&Name, 0x104u, v32);
  if ( v9 >= 0 )
  {
    if ( a2 )
    {
      LastError = RpcImpersonateClient(0);
      v9 = LastError;
      v11 = LastError <= 0;
      if ( LastError )
        goto LABEL_6;
      CurrentThread = GetCurrentThread();
      if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
      {
        GetLastError();
        v13 = RpcRevertToSelfEx(0);
        v9 = v13;
        if ( v13 >= 1 )
          v9 = (unsigned __int16)v13 | 0x80010000;
        goto LABEL_41;
      }
      RpcRevertToSelfEx(0);
      v14 = BuildSecurityDescriptorForSharingAccess(TokenHandle, 0, 0x10000000, (char *)&v29 + 8);
      if ( v14 < 0 )
      {
        LastError = RtlNtStatusToDosError(v14);
LABEL_13:
        v9 = LastError;
        v11 = LastError <= 0;
LABEL_6:
        if ( !v11 )
          v9 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_41;
      }
      LODWORD(v29) = 24;
      LODWORD(v30) = 1;
    }
    v15 = (struct _SECURITY_ATTRIBUTES *)&v29;
    if ( !a2 )
      v15 = 0;
    v6 = CreateEventW(v15, 0, 0, &Name);
    if ( !v6 )
    {
      LastError = GetLastError();
      goto LABEL_13;
    }
    Pid = 0;
    if ( !a2 )
    {
      v9 = 1;
      goto LABEL_27;
    }
    v16 = I_RpcBindingInqLocalClientPID(0, &Pid);
    v9 = v16;
    v17 = v16 <= 0;
    if ( !v16 )
    {
      v18 = OpenProcess(0x410u, 0, Pid);
      if ( v18 )
      {
        v9 = 0;
        v7 = v18;
LABEL_27:
        CloseHandle(0);
        if ( v9 >= 0 )
        {
          v19 = (void *)*((_QWORD *)this + 4);
          if ( v19 != (void *)-1LL )
            CloseHandle(v19);
          *((_QWORD *)this + 4) = v6;
          v20 = 0x7FFFFFFF;
          p_Name = &Name;
          v6 = 0;
          do
          {
            if ( !*p_Name )
              break;
            ++p_Name;
            --v20;
          }
          while ( v20 );
          v9 = v20 == 0 ? 0x80070057 : 0;
          v22 = (0x7FFFFFFF - v20) & -(__int64)(v20 != 0);
          if ( v20 )
          {
            v23 = v22 + 1;
            v24 = (unsigned __int16 *)malloc(2 * (v22 + 1));
            v8 = v24;
            if ( v24 )
            {
              v9 = StringCchCopyW(v24, v23, &Name);
              if ( v9 >= 0 )
              {
                *v31 = v8;
                if ( a2 )
                {
                  CloseHandle(*((HANDLE *)this + 13));
                  *((_QWORD *)this + 13) = v7;
                  v7 = 0;
                }
                EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
                v8 = 0;
                v25 = *((_DWORD *)this + 42);
                LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
                if ( v25 )
                  SetEvent(*((HANDLE *)this + 4));
              }
            }
            else
            {
              v9 = -2147024882;
            }
          }
        }
        goto LABEL_41;
      }
      v16 = GetLastError();
      v9 = v16;
      v17 = v16 <= 0;
    }
    if ( !v17 )
      v9 = (unsigned __int16)v16 | 0x80070000;
    goto LABEL_27;
  }
LABEL_41:
  free(v8);
  CloseHandle(v6);
  CloseHandle(v7);
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  if ( *((_QWORD *)&v29 + 1) )
    FreeTransientObjectSecurityDescriptor();
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180017cec  mov     [rsp-8+arg_8], rbx
0x180017cf1  push    rbp
0x180017cf2  push    rsi
0x180017cf3  push    rdi
0x180017cf4  push    r12
0x180017cf6  push    r13
0x180017cf8  push    r14
0x180017cfa  push    r15
0x180017cfc  lea     rbp, [rsp-1B0h]
0x180017d04  sub     rsp, 2B0h
0x180017d0b  mov     rax, cs:__security_cookie
0x180017d12  xor     rax, rsp
0x180017d15  mov     [rbp+1E0h+var_40], rax
0x180017d1c  xor     esi, esi
0x180017d1e  mov     rbx, r8
0x180017d21  mov     rdi, rdx
0x180017d24  mov     [rsp+2E0h+var_298], rbx
0x180017d29  mov     r14, rcx
0x180017d2c  mov     [rbp+1E0h+Name], si
0x180017d30  xor     edx, edx; Val
0x180017d32  lea     rcx, [rbp+1E0h+var_24E]; void *
0x180017d36  mov     r8d, 206h; Size
0x180017d3c  mov     r12d, esi
0x180017d3f  mov     r13d, esi
0x180017d42  mov     r15d, esi
0x180017d45  call    memset_0
0x180017d4a  movups  xmm1, xmmword ptr cs:aPushroutermsga+10h; "erMsgAvailableEvent%d"
0x180017d51  mov     [rsp+2E0h+TokenHandle], rsi
0x180017d56  xor     eax, eax
0x180017d58  xorps   xmm0, xmm0
0x180017d5b  mov     [rsp+2E0h+var_2A0], rax
0x180017d60  movups  [rsp+2E0h+var_2B0], xmm0
0x180017d65  movups  xmm0, xmmword ptr cs:aPushroutermsga; "PushRouterMsgAvailableEvent%d"
0x180017d6c  movups  [rsp+2E0h+var_280], xmm1
0x180017d71  movups  xmm1, xmmword ptr cs:aPushroutermsga+2Ch; "Event%d"
0x180017d78  movups  xmmword ptr [rsp+2E0h+var_290], xmm0
0x180017d7d  movups  xmm0, xmmword ptr cs:aPushroutermsga+20h; "ilableEvent%d"
0x180017d84  movups  xmmword ptr [rsp+2E0h+var_270], xmm0
0x180017d89  movups  xmmword ptr [rsp+2E0h+var_270+0Ch], xmm1
0x180017d8e  test    rbx, rbx
0x180017d91  jnz     short loc_180017D9D
0x180017d93  mov     esi, 80004003h
0x180017d98  jmp     loc_180017FF2
0x180017d9d  mov     r9d, cs:?g_cPROpenUniqueEvent@@3KA; ulong g_cPROpenUniqueEvent
0x180017da4  lea     r8, [rsp+2E0h+var_290]; unsigned __int16 *
0x180017da9  mov     edx, 104h; unsigned __int64
0x180017dae  lea     rcx, [rbp+1E0h+Name]; unsigned __int16 *
0x180017db2  lea     eax, [r9+1]
0x180017db6  mov     cs:?g_cPROpenUniqueEvent@@3KA, eax; ulong g_cPROpenUniqueEvent
0x180017dbc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180017dc1  xor     ebx, ebx
0x180017dc3  mov     esi, eax
0x180017dc5  test    eax, eax
0x180017dc7  js      loc_180017FF2
0x180017dcd  test    rdi, rdi
0x180017dd0  jz      loc_180017E85
0x180017dd6  xor     ecx, ecx; BindingHandle
0x180017dd8  call    cs:__imp_RpcImpersonateClient
0x180017dde  mov     esi, eax
0x180017de0  test    eax, eax
0x180017de2  jz      short loc_180017DF8
0x180017de4  jle     loc_180017FF2
0x180017dea  movzx   esi, ax
0x180017ded  or      esi, 80070000h
0x180017df3  jmp     loc_180017FF2
0x180017df8  call    cs:__imp_GetCurrentThread
0x180017dfe  mov     edx, 8; DesiredAccess
0x180017e03  lea     r9, [rsp+2E0h+TokenHandle]; TokenHandle
0x180017e08  mov     rcx, rax; ThreadHandle
0x180017e0b  lea     r8d, [rdx-7]; OpenAsSelf
0x180017e0f  call    cs:__imp_OpenThreadToken
0x180017e15  test    eax, eax
0x180017e17  jnz     short loc_180017E40
0x180017e19  call    cs:__imp_GetLastError
0x180017e1f  xor     ecx, ecx; BindingHandle
0x180017e21  call    cs:__imp_RpcRevertToSelfEx
0x180017e27  mov     esi, eax
0x180017e29  cmp     eax, 1
0x180017e2c  jl      loc_180017FF2
0x180017e32  movzx   esi, ax
0x180017e35  or      esi, 80010000h
0x180017e3b  jmp     loc_180017FF2
0x180017e40  xor     ecx, ecx; BindingHandle
0x180017e42  call    cs:__imp_RpcRevertToSelfEx
0x180017e48  mov     rcx, [rsp+2E0h+TokenHandle]
0x180017e4d  lea     r9, [rsp+2E0h+var_2B0+8]
0x180017e52  xor     edx, edx
0x180017e54  mov     r8d, 10000000h
0x180017e5a  call    cs:__imp_BuildSecurityDescriptorForSharingAccess
0x180017e60  test    eax, eax
0x180017e62  jns     short loc_180017E75
0x180017e64  mov     ecx, eax; Status
0x180017e66  call    cs:__imp_RtlNtStatusToDosError
0x180017e6c  mov     esi, eax
0x180017e6e  test    eax, eax
0x180017e70  jmp     loc_180017DE4
0x180017e75  mov     dword ptr [rsp+2E0h+var_2B0], 18h
0x180017e7d  mov     dword ptr [rsp+2E0h+var_2A0], 1
0x180017e85  test    rdi, rdi
0x180017e88  lea     rcx, [rsp+2E0h+var_2B0]
0x180017e8d  lea     r9, [rbp+1E0h+Name]; lpName
0x180017e91  cmovz   rcx, rbx; lpEventAttributes
0x180017e95  xor     r8d, r8d; bInitialState
0x180017e98  xor     edx, edx; bManualReset
0x180017e9a  call    cs:__imp_CreateEventW
0x180017ea0  mov     r12, rax
0x180017ea3  test    rax, rax
0x180017ea6  jnz     short loc_180017EB0
0x180017ea8  call    cs:__imp_GetLastError
0x180017eae  jmp     short loc_180017E6C
0x180017eb0  mov     [rsp+2E0h+Pid], ebx
0x180017eb4  test    rdi, rdi
0x180017eb7  jnz     short loc_180017EBE
0x180017eb9  lea     esi, [rdi+1]
0x180017ebc  jmp     short loc_180017F06
0x180017ebe  lea     rdx, [rsp+2E0h+Pid]; Pid
0x180017ec3  xor     ecx, ecx; Binding
0x180017ec5  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180017ecb  mov     esi, eax
0x180017ecd  test    eax, eax
0x180017ecf  jz      short loc_180017EDE
0x180017ed1  jle     short loc_180017F06
0x180017ed3  movzx   esi, ax
0x180017ed6  or      esi, 80070000h
0x180017edc  jmp     short loc_180017F06
0x180017ede  mov     r8d, [rsp+2E0h+Pid]; dwProcessId
0x180017ee3  xor     edx, edx; bInheritHandle
0x180017ee5  mov     ecx, 410h; dwDesiredAccess
0x180017eea  call    cs:__imp_OpenProcess
0x180017ef0  test    rax, rax
0x180017ef3  jnz     short loc_180017F01
0x180017ef5  call    cs:__imp_GetLastError
0x180017efb  mov     esi, eax
0x180017efd  test    eax, eax
0x180017eff  jmp     short loc_180017ED1
0x180017f01  mov     esi, ebx
0x180017f03  mov     r13, rax
0x180017f06  xor     ecx, ecx; hObject
0x180017f08  call    cs:__imp_CloseHandle
0x180017f0e  test    esi, esi
0x180017f10  js      loc_180017FF2
0x180017f16  mov     rcx, [r14+20h]; hObject
0x180017f1a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180017f1e  jz      short loc_180017F26
0x180017f20  call    cs:__imp_CloseHandle
0x180017f26  mov     edx, 7FFFFFFFh
0x180017f2b  mov     [r14+20h], r12
0x180017f2f  mov     ecx, edx
0x180017f31  lea     rax, [rbp+1E0h+Name]
0x180017f35  mov     r12, rbx
0x180017f38  cmp     [rax], bx
0x180017f3b  jz      short loc_180017F47
0x180017f3d  add     rax, 2
0x180017f41  sub     rcx, 1
0x180017f45  jnz     short loc_180017F38
0x180017f47  mov     rax, rcx
0x180017f4a  neg     rax
0x180017f4d  mov     rax, rcx
0x180017f50  sbb     esi, esi
0x180017f52  sub     rdx, rcx
0x180017f55  not     esi
0x180017f57  and     esi, 80070057h
0x180017f5d  neg     rax
0x180017f60  sbb     r8, r8
0x180017f63  and     r8, rdx
0x180017f66  test    rcx, rcx
0x180017f69  jz      loc_180017FF2
0x180017f6f  lea     rbx, [r8+1]
0x180017f73  lea     rcx, [rbx+rbx]; Size
0x180017f77  call    cs:__imp_malloc
0x180017f7d  mov     r15, rax
0x180017f80  test    rax, rax
0x180017f83  jnz     short loc_180017F8C
0x180017f85  mov     esi, 8007000Eh
0x180017f8a  jmp     short loc_180017FF2
0x180017f8c  lea     r8, [rbp+1E0h+Name]; unsigned __int16 *
0x180017f90  mov     rdx, rbx; unsigned __int64
0x180017f93  mov     rcx, r15; unsigned __int16 *
0x180017f96  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180017f9b  xor     ebx, ebx
0x180017f9d  mov     esi, eax
0x180017f9f  test    eax, eax
0x180017fa1  js      short loc_180017FF2
0x180017fa3  mov     rax, [rsp+2E0h+var_298]
0x180017fa8  mov     [rax], r15
0x180017fab  test    rdi, rdi
0x180017fae  jz      short loc_180017FC1
0x180017fb0  mov     rcx, [r14+68h]; hObject
0x180017fb4  call    cs:__imp_CloseHandle
0x180017fba  mov     [r14+68h], r13
0x180017fbe  mov     r13d, ebx
0x180017fc1  lea     rdi, [r14+0C0h]
0x180017fc8  mov     rcx, rdi; lpCriticalSection
0x180017fcb  call    cs:__imp_EnterCriticalSection
0x180017fd1  mov     rcx, rdi; lpCriticalSection
0x180017fd4  mov     r15, rbx
0x180017fd7  mov     ebx, [r14+0A8h]
0x180017fde  call    cs:__imp_LeaveCriticalSection
0x180017fe4  test    ebx, ebx
0x180017fe6  jz      short loc_180017FF2
0x180017fe8  mov     rcx, [r14+20h]; hEvent
0x180017fec  call    cs:__imp_SetEvent
0x180017ff2  mov     rcx, r15; Block
0x180017ff5  call    cs:__imp_free
0x180017ffb  mov     rcx, r12; hObject
0x180017ffe  call    cs:__imp_CloseHandle
0x180018004  mov     rcx, r13; hObject
0x180018007  call    cs:__imp_CloseHandle
0x18001800d  mov     rcx, [rsp+2E0h+TokenHandle]; hObject
0x180018012  test    rcx, rcx
0x180018015  jz      short loc_18001801D
0x180018017  call    cs:__imp_CloseHandle
0x18001801d  mov     rcx, qword ptr [rsp+2E0h+var_2B0+8]
0x180018022  test    rcx, rcx
0x180018025  jz      short loc_18001802D
0x180018027  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18001802d  mov     eax, esi
0x18001802f  mov     rcx, [rbp+1E0h+var_40]
0x180018036  xor     rcx, rsp; StackCookie
0x180018039  call    __security_check_cookie
0x18001803e  mov     rbx, [rsp+2E0h+arg_8]
0x180018046  add     rsp, 2B0h
0x18001804d  pop     r15
0x18001804f  pop     r14
0x180018051  pop     r13
0x180018053  pop     r12
0x180018055  pop     rdi
0x180018056  pop     rsi
0x180018057  pop     rbp
0x180018058  retn
```
