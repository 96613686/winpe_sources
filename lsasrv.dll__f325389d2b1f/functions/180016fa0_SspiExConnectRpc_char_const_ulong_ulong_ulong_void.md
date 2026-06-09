# SspiExConnectRpc(char const *,ulong,ulong *,ulong *,void * *)

- ea: `0x180016fa0`
- end: `0x180017289`
- name: `?SspiExConnectRpc@@YAJPEBDKPEAK1PEAPEAX@Z`
- size: `745`
- prototype: `int(const char *, unsigned int, unsigned int *, unsigned int *, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, installer_update`

## callees

- `0x180016fa0`
- `0x180017290`
- `0x180017304`
- `0x1800177bc`
- `0x1800b86d0`
- `0x1800b9304`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x180017252`
- `api-ms-win-crt-private-l1-1-0!_o_mbstowcs` at `0x180017252`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800170bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800170bf`
- `ntdll!NtClose` at `0x1800171e4`
- `ntdll!NtClose` at `0x1800171fa`
- `ntdll!NtClose` at `0x1800171e4`
- `ntdll!NtClose` at `0x1800171fa`
- `ntdll!RtlTestProtectedAccess` at `0x1800171b4`
- `ntdll!RtlTestProtectedAccess` at `0x1800171b4`
- `ntdll!NtQueryInformationProcess` at `0x18001707a`
- `ntdll!NtQueryInformationProcess` at `0x1800170a9`
- `ntdll!NtQueryInformationProcess` at `0x1800170e2`
- `ntdll!NtQueryInformationProcess` at `0x18001707a`
- `ntdll!NtQueryInformationProcess` at `0x1800170a9`
- `ntdll!NtQueryInformationProcess` at `0x1800170e2`
- `ntdll!NtOpenThreadToken` at `0x180017120`
- `ntdll!NtOpenThreadToken` at `0x180017120`
- `RPCRT4!RpcRevertToSelf` at `0x18001712e`
- `RPCRT4!RpcRevertToSelf` at `0x18001712e`
- `RPCRT4!I_RpcMapWin32Status` at `0x180017276`
- `RPCRT4!I_RpcMapWin32Status` at `0x180017276`
- `RPCRT4!RpcImpersonateClient` at `0x1800170fa`
- `RPCRT4!RpcImpersonateClient` at `0x1800170fa`
- `RPCRT4!I_RpcOpenClientProcess` at `0x180017051`
- `RPCRT4!I_RpcOpenClientProcess` at `0x180017051`

## pseudocode

```c
__int64 __fastcall SspiExConnectRpc(const char *a1, char a2, unsigned int *a3, unsigned int *a4, void **a5)
{
  RPC_STATUS v9; // eax
  int InformationProcess; // ebx
  HANDLE CurrentProcess; // rax
  __int64 v12; // r9
  __int64 v13; // rdx
  struct _Session *v14; // rax
  __int64 v15; // rcx
  unsigned __int64 v17; // rax
  char v18; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v19[3]; // [rsp+31h] [rbp-CFh] BYREF
  unsigned int v20; // [rsp+34h] [rbp-CCh] BYREF
  void *ClientProcess; // [rsp+38h] [rbp-C8h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-C0h] BYREF
  struct _Session *v23; // [rsp+48h] [rbp-B8h] BYREF
  struct _CLIENT_ID v24; // [rsp+50h] [rbp-B0h] BYREF
  _OWORD ProcessInformation[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v26; // [rsp+80h] [rbp-80h]
  unsigned __int16 v27[128]; // [rsp+90h] [rbp-70h] BYREF

  v23 = 0;
  v20 = 0;
  memset_0(v27, 0, sizeof(v27));
  ClientProcess = 0;
  TokenHandle = 0;
  v18 = 0;
  v19[0] = 0;
  memset(ProcessInformation, 0, sizeof(ProcessInformation));
  v26 = 0;
  if ( a3 && a4 && a5 )
  {
    if ( a1 )
    {
      v17 = -1;
      do
        ++v17;
      while ( a1[v17] );
      if ( v17 > 0x7F )
        return (unsigned int)-1073741562;
      _o_mbstowcs(v27, a1, 128);
    }
    v9 = I_RpcOpenClientProcess(0, 0x1000u, &ClientProcess);
    if ( !v9 )
    {
      InformationProcess = NtQueryInformationProcess(
                             ClientProcess,
                             ProcessBasicInformation,
                             ProcessInformation,
                             0x30u,
                             0);
      if ( InformationProcess < 0 )
        goto LABEL_17;
      InformationProcess = NtQueryInformationProcess(
                             ClientProcess,
                             ProcessAffinityUpdateMode|ProcessUserModeIOPL,
                             &v18,
                             1u,
                             0);
      if ( InformationProcess < 0 )
        goto LABEL_17;
      CurrentProcess = GetCurrentProcess();
      InformationProcess = NtQueryInformationProcess(
                             CurrentProcess,
                             ProcessAffinityUpdateMode|ProcessUserModeIOPL,
                             v19,
                             1u,
                             0);
      if ( InformationProcess < 0 )
        goto LABEL_17;
      v9 = RpcImpersonateClient(0);
      if ( !v9 )
      {
        InformationProcess = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
        RpcRevertToSelf();
        if ( InformationProcess >= 0 )
        {
          InformationProcess = SspipValidedLogonProcess(v27, a2, TokenHandle, v12, &v20);
          if ( InformationProcess >= 0 )
          {
            v24.UniqueProcess = (HANDLE)v26;
            v24.UniqueThread = 0;
            InformationProcess = CreateSession(&v24, 1, v27, v20, &v23);
            if ( InformationProcess >= 0 )
            {
              v14 = pDefaultSession;
              *a3 = 0;
              v15 = *((unsigned int *)v14 + 4);
              if ( (_QWORD)v26 == v15 )
              {
                *a3 = 0x10000;
              }
              else
              {
                LOBYTE(v13) = v18;
                LOBYTE(v15) = v19[0];
                if ( !(unsigned __int8)RtlTestProtectedAccess(v15, v13) )
                  *a3 |= 0x20000u;
              }
              *a4 = SpmpCurrentPackageCount();
              InformationProcess = 0;
              *a5 = v23;
            }
          }
        }
        goto LABEL_17;
      }
    }
    InformationProcess = I_RpcMapWin32Status(v9);
  }
  else
  {
    InformationProcess = -1073741811;
  }
LABEL_17:
  if ( ClientProcess )
    NtClose(ClientProcess);
  if ( TokenHandle )
    NtClose(TokenHandle);
  return (unsigned int)InformationProcess;
}

```

## disassembly

```asm
0x180016fa0  push    rbp
0x180016fa2  push    rbx
0x180016fa3  push    rsi
0x180016fa4  push    rdi
0x180016fa5  push    r12
0x180016fa7  push    r14
0x180016fa9  push    r15
0x180016fab  lea     rbp, [rsp-0A0h]
0x180016fb3  sub     rsp, 1A0h
0x180016fba  mov     rax, cs:__security_cookie
0x180016fc1  xor     rax, rsp
0x180016fc4  mov     [rbp+0D0h+var_40], rax
0x180016fcb  mov     r14, [rbp+0D0h+arg_20]
0x180016fd2  mov     rdi, r8
0x180016fd5  mov     r15d, edx
0x180016fd8  mov     rbx, rcx
0x180016fdb  xor     r12d, r12d
0x180016fde  lea     rcx, [rbp+0D0h+var_140]; void *
0x180016fe2  xor     edx, edx; Val
0x180016fe4  mov     [rsp+1D0h+var_188], r12
0x180016fe9  mov     r8d, 100h; Size
0x180016fef  mov     [rsp+1D0h+var_19C], r12d
0x180016ff4  mov     rsi, r9
0x180016ff7  call    memset_0
0x180016ffc  mov     [rsp+1D0h+ClientProcess], r12
0x180017001  xorps   xmm0, xmm0
0x180017004  mov     [rsp+1D0h+TokenHandle], r12
0x180017009  mov     [rsp+1D0h+var_1A0], r12b
0x18001700e  mov     [rsp+1D0h+var_19F], r12b
0x180017013  movups  [rsp+1D0h+ProcessInformation], xmm0
0x180017018  movups  [rsp+1D0h+var_160], xmm0
0x18001701d  movups  [rbp+0D0h+var_150], xmm0
0x180017021  test    rdi, rdi
0x180017024  jz      loc_180017263
0x18001702a  test    rsi, rsi
0x18001702d  jz      loc_180017263
0x180017033  test    r14, r14
0x180017036  jz      loc_180017263
0x18001703c  test    rbx, rbx
0x18001703f  jnz     loc_180017232
0x180017045  lea     r8, [rsp+1D0h+ClientProcess]; ClientProcess
0x18001704a  mov     edx, 1000h; DesiredAccess
0x18001704f  xor     ecx, ecx; Binding
0x180017051  call    cs:__imp_I_RpcOpenClientProcess
0x180017058  nop     dword ptr [rax+rax+00h]
0x18001705d  test    eax, eax
0x18001705f  jnz     loc_180017274
0x180017065  mov     rcx, [rsp+1D0h+ClientProcess]; ProcessHandle
0x18001706a  lea     r9d, [rax+30h]; ProcessInformationLength
0x18001706e  lea     r8, [rsp+1D0h+ProcessInformation]; ProcessInformation
0x180017073  mov     [rsp+1D0h+ReturnLength], r12; ReturnLength
0x180017078  xor     edx, edx; ProcessInformationClass
0x18001707a  call    cs:__imp_NtQueryInformationProcess
0x180017081  nop     dword ptr [rax+rax+00h]
0x180017086  mov     ebx, eax
0x180017088  test    eax, eax
0x18001708a  js      loc_1800171DA
0x180017090  mov     rcx, [rsp+1D0h+ClientProcess]; ProcessHandle
0x180017095  lea     r8, [rsp+1D0h+var_1A0]; ProcessInformation
0x18001709a  mov     r9d, 1; ProcessInformationLength
0x1800170a0  mov     [rsp+1D0h+ReturnLength], r12; ReturnLength
0x1800170a5  lea     edx, [r9+3Ch]; ProcessInformationClass
0x1800170a9  call    cs:__imp_NtQueryInformationProcess
0x1800170b0  nop     dword ptr [rax+rax+00h]
0x1800170b5  mov     ebx, eax
0x1800170b7  test    eax, eax
0x1800170b9  js      loc_1800171DA
0x1800170bf  call    cs:__imp_GetCurrentProcess
0x1800170c6  nop     dword ptr [rax+rax+00h]
0x1800170cb  mov     r9d, 1; ProcessInformationLength
0x1800170d1  mov     [rsp+1D0h+ReturnLength], r12; ReturnLength
0x1800170d6  mov     rcx, rax; ProcessHandle
0x1800170d9  lea     r8, [rsp+1D0h+var_19F]; ProcessInformation
0x1800170de  lea     edx, [r9+3Ch]; ProcessInformationClass
0x1800170e2  call    cs:__imp_NtQueryInformationProcess
0x1800170e9  nop     dword ptr [rax+rax+00h]
0x1800170ee  mov     ebx, eax
0x1800170f0  test    eax, eax
0x1800170f2  js      loc_1800171DA
0x1800170f8  xor     ecx, ecx; BindingHandle
0x1800170fa  call    cs:__imp_RpcImpersonateClient
0x180017101  nop     dword ptr [rax+rax+00h]
0x180017106  test    eax, eax
0x180017108  jnz     loc_180017274
0x18001710e  lea     r9, [rsp+1D0h+TokenHandle]; TokenHandle
0x180017113  mov     r8b, 1; OpenAsSelf
0x180017116  lea     edx, [rax+8]; DesiredAccess
0x180017119  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180017120  call    cs:__imp_NtOpenThreadToken
0x180017127  nop     dword ptr [rax+rax+00h]
0x18001712c  mov     ebx, eax
0x18001712e  call    cs:__imp_RpcRevertToSelf
0x180017135  nop     dword ptr [rax+rax+00h]
0x18001713a  test    ebx, ebx
0x18001713c  js      loc_1800171DA
0x180017142  mov     r8, [rsp+1D0h+TokenHandle]; void *
0x180017147  lea     rax, [rsp+1D0h+var_19C]
0x18001714c  mov     edx, r15d; unsigned int
0x18001714f  mov     [rsp+1D0h+ReturnLength], rax; unsigned int *
0x180017154  lea     rcx, [rbp+0D0h+var_140]; unsigned __int16 *
0x180017158  call    ?SspipValidedLogonProcess@@YAJPEAGKPEAXHPEAK@Z; SspipValidedLogonProcess(ushort *,ulong,void *,int,ulong *)
0x18001715d  mov     ebx, eax
0x18001715f  test    eax, eax
0x180017161  js      short loc_1800171DA
0x180017163  mov     rax, qword ptr [rbp+0D0h+var_150]
0x180017167  lea     r8, [rbp+0D0h+var_140]; unsigned __int16 *
0x18001716b  mov     r9d, [rsp+1D0h+var_19C]; unsigned int
0x180017170  lea     rcx, [rsp+1D0h+var_180]; struct _CLIENT_ID *
0x180017175  mov     [rsp+1D0h+var_180.UniqueProcess], rax
0x18001717a  mov     edx, 1; unsigned int
0x18001717f  lea     rax, [rsp+1D0h+var_188]
0x180017184  mov     [rsp+1D0h+var_180.UniqueThread], r12
0x180017189  mov     [rsp+1D0h+ReturnLength], rax; struct _Session **
0x18001718e  call    ?CreateSession@@YAJPEAU_CLIENT_ID@@KPEBGKPEAPEAU_Session@@@Z; CreateSession(_CLIENT_ID *,ulong,ushort const *,ulong,_Session * *)
0x180017193  mov     ebx, eax
0x180017195  test    eax, eax
0x180017197  js      short loc_1800171DA
0x180017199  mov     rax, cs:?pDefaultSession@@3PEAU_Session@@EA; _Session * pDefaultSession
0x1800171a0  mov     [rdi], r12d
0x1800171a3  mov     ecx, [rax+10h]
0x1800171a6  cmp     qword ptr [rbp+0D0h+var_150], rcx
0x1800171aa  jz      short loc_18001722A
0x1800171ac  mov     dl, [rsp+1D0h+var_1A0]
0x1800171b0  mov     cl, [rsp+1D0h+var_19F]
0x1800171b4  call    cs:__imp_RtlTestProtectedAccess
0x1800171bb  nop     dword ptr [rax+rax+00h]
0x1800171c0  test    al, al
0x1800171c2  jnz     short loc_1800171C8
0x1800171c4  bts     dword ptr [rdi], 11h
0x1800171c8  call    ?SpmpCurrentPackageCount@@YAKXZ; SpmpCurrentPackageCount(void)
0x1800171cd  mov     [rsi], eax
0x1800171cf  mov     ebx, r12d
0x1800171d2  mov     rax, [rsp+1D0h+var_188]
0x1800171d7  mov     [r14], rax
0x1800171da  mov     rcx, [rsp+1D0h+ClientProcess]; Handle
0x1800171df  test    rcx, rcx
0x1800171e2  jz      short loc_1800171F0
0x1800171e4  call    cs:__imp_NtClose
0x1800171eb  nop     dword ptr [rax+rax+00h]
0x1800171f0  mov     rcx, [rsp+1D0h+TokenHandle]; Handle
0x1800171f5  test    rcx, rcx
0x1800171f8  jz      short loc_180017206
0x1800171fa  call    cs:__imp_NtClose
0x180017201  nop     dword ptr [rax+rax+00h]
0x180017206  mov     eax, ebx
0x180017208  mov     rcx, [rbp+0D0h+var_40]
0x18001720f  xor     rcx, rsp; StackCookie
0x180017212  call    __security_check_cookie
0x180017217  add     rsp, 1A0h
0x18001721e  pop     r15
0x180017220  pop     r14
0x180017222  pop     r12
0x180017224  pop     rdi
0x180017225  pop     rsi
0x180017226  pop     rbx
0x180017227  pop     rbp
0x180017228  retn
0x18001722a  mov     dword ptr [rdi], 10000h
0x180017230  jmp     short loc_1800171C8
0x180017232  or      rax, 0FFFFFFFFFFFFFFFFh
0x180017236  inc     rax
0x180017239  cmp     [rbx+rax], r12b
0x18001723d  jnz     short loc_180017236
0x18001723f  cmp     rax, 7Fh
0x180017243  ja      short loc_18001726D
0x180017245  mov     r8d, 80h
0x18001724b  lea     rcx, [rbp+0D0h+var_140]
0x18001724f  mov     rdx, rbx
0x180017252  call    cs:__imp__o_mbstowcs
0x180017259  nop     dword ptr [rax+rax+00h]
0x18001725e  jmp     loc_180017045
0x180017263  mov     ebx, 0C000000Dh
0x180017268  jmp     loc_1800171DA
0x18001726d  mov     ebx, 0C0000106h
0x180017272  jmp     short loc_180017206
0x180017274  mov     ecx, eax; Status
0x180017276  call    cs:__imp_I_RpcMapWin32Status
0x18001727d  nop     dword ptr [rax+rax+00h]
0x180017282  mov     ebx, eax
0x180017284  jmp     loc_1800171DA
```
