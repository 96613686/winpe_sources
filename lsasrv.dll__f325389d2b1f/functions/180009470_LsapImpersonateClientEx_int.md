# LsapImpersonateClientEx(int *)

- ea: `0x180009470`
- end: `0x180009684`
- name: `?LsapImpersonateClientEx@@YAJPEAH@Z`
- size: `532`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `17`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180004c20`
- `0x180008580`
- `0x180013b8c`
- `0x1800168a0`
- `0x18005e058`
- `0x18007b380`
- `0x18007cc54`
- `0x180088ba0`
- `0x180090c2c`
- `0x18009ac50`
- `0x1800a1dc4`
- `0x1800cd01c`
- `0x1800d3a4c`
- `0x1800dd688`
- `0x180107d28`
- `0x18010b518`
- `0x18012fc00`

## callees

- `0x180009470`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009483`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800094d5`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009483`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x1800094d5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180009673`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180009673`
- `ntdll!RtlImpersonateSelfEx` at `0x18000959c`
- `ntdll!RtlImpersonateSelfEx` at `0x18000959c`
- `ntdll!NtSetInformationThread` at `0x1800095e5`
- `ntdll!NtSetInformationThread` at `0x180009608`
- `ntdll!NtSetInformationThread` at `0x1800095e5`
- `ntdll!NtSetInformationThread` at `0x180009608`
- `ntdll!NtOpenThreadToken` at `0x180009549`
- `ntdll!NtOpenThreadToken` at `0x180009549`
- `RPCRT4!RpcRevertToSelf` at `0x180009662`
- `RPCRT4!RpcRevertToSelf` at `0x180009662`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000951b`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000951b`
- `RPCRT4!RpcImpersonateClient` at `0x1800094f9`
- `RPCRT4!RpcImpersonateClient` at `0x1800094f9`
- `lsass!LsaImpersonateKsecCaller` at `0x1800095ad`
- `lsass!LsaImpersonateKsecCaller` at `0x1800095ad`

## pseudocode

```c
__int64 __fastcall LsapImpersonateClientEx(int *a1)
{
  char *Value; // rax
  int v3; // ebp
  void **v4; // rsi
  int v5; // r14d
  _DWORD *v6; // rax
  RPC_STATUS v7; // eax
  int v8; // ebx
  NTSTATUS v9; // eax

  Value = (char *)TlsGetValue(dwCallInfo);
  if ( !Value )
    return (unsigned int)-1071513572;
  v3 = 0;
  v4 = (void **)(Value + 272);
  v5 = 0;
  if ( *((_QWORD *)Value + 34) )
  {
    if ( !Value[60] || *((int *)Value + 14) >= 2 )
    {
      v9 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, Value + 272, 8u);
      goto LABEL_12;
    }
    return (unsigned int)-1073741659;
  }
  if ( !*((_DWORD *)Value + 16) )
  {
    if ( (Value[32] & 0x20) != 0 )
      return (unsigned int)-1073741558;
    v6 = TlsGetValue(dwSession);
    if ( v6 )
    {
      if ( (v6[8] & 0x1000) != 0 )
      {
        v8 = LsaImpersonateKsecCaller(v4);
        if ( v8 >= 0 )
        {
LABEL_13:
          if ( a1 )
            *a1 = v3;
          return (unsigned int)v8;
        }
      }
      v7 = RpcImpersonateClient(0);
      if ( v7 != 5 )
      {
        if ( v7 == 1765 )
          return (unsigned int)-1073741769;
        v8 = I_RpcMapWin32Status(v7);
        if ( v8 < 0 )
          return (unsigned int)v8;
        v5 = 1;
        v3 = 1;
        goto LABEL_11;
      }
      return (unsigned int)-1073741659;
    }
LABEL_17:
    v9 = RtlImpersonateSelfEx(2, 0x2000000, v4);
    goto LABEL_12;
  }
  if ( !*((_QWORD *)Value + 43) )
    goto LABEL_17;
  v8 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, Value + 344, 8u);
  if ( v8 < 0 )
    return (unsigned int)v8;
  v5 = 1;
LABEL_11:
  v9 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x2000000u, 1u, v4);
LABEL_12:
  v8 = v9;
  if ( v9 >= 0 )
    goto LABEL_13;
  if ( v5 )
  {
    if ( v3 )
      RpcRevertToSelf();
    else
      RevertToSelf();
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180009470  mov     [rsp+arg_18], rbx
0x180009475  push    rdi
0x180009476  sub     rsp, 20h
0x18000947a  mov     rdi, rcx
0x18000947d  mov     ecx, cs:?dwCallInfo@@3KA; dwTlsIndex
0x180009483  call    cs:__imp_TlsGetValue
0x18000948a  nop     dword ptr [rax+rax+00h]
0x18000948f  test    rax, rax
0x180009492  jz      loc_18000962D
0x180009498  mov     [rsp+28h+arg_0], rbp
0x18000949d  xor     ebp, ebp
0x18000949f  mov     [rsp+28h+arg_8], rsi
0x1800094a4  lea     rsi, [rax+110h]
0x1800094ab  mov     [rsp+28h+arg_10], r14
0x1800094b0  xor     r14d, r14d
0x1800094b3  cmp     [rsi], rbp
0x1800094b6  jnz     loc_1800095C4
0x1800094bc  cmp     [rax+40h], ebp
0x1800094bf  jnz     loc_180009583
0x1800094c5  test    byte ptr [rax+20h], 20h
0x1800094c9  jnz     loc_180009637
0x1800094cf  mov     ecx, cs:?dwSession@@3KA; dwTlsIndex
0x1800094d5  call    cs:__imp_TlsGetValue
0x1800094dc  nop     dword ptr [rax+rax+00h]
0x1800094e1  test    rax, rax
0x1800094e4  jz      loc_18000958F
0x1800094ea  test    dword ptr [rax+20h], 1000h
0x1800094f1  jnz     loc_1800095AA
0x1800094f7  xor     ecx, ecx; BindingHandle
0x1800094f9  call    cs:__imp_RpcImpersonateClient
0x180009500  nop     dword ptr [rax+rax+00h]
0x180009505  cmp     eax, 5
0x180009508  jz      loc_180009641
0x18000950e  cmp     eax, 6E5h
0x180009513  jz      loc_18000964B
0x180009519  mov     ecx, eax; Status
0x18000951b  call    cs:__imp_I_RpcMapWin32Status
0x180009522  nop     dword ptr [rax+rax+00h]
0x180009527  mov     ebx, eax
0x180009529  test    eax, eax
0x18000952b  js      short loc_180009566
0x18000952d  mov     r14d, 1
0x180009533  mov     ebp, r14d
0x180009536  movzx   r8d, bpl; OpenAsSelf
0x18000953a  mov     r9, rsi; TokenHandle
0x18000953d  mov     edx, 2000000h; DesiredAccess
0x180009542  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180009549  call    cs:__imp_NtOpenThreadToken
0x180009550  nop     dword ptr [rax+rax+00h]
0x180009555  mov     ebx, eax
0x180009557  test    eax, eax
0x180009559  js      loc_180009655
0x18000955f  test    rdi, rdi
0x180009562  jz      short loc_180009566
0x180009564  mov     [rdi], ebp
0x180009566  mov     rsi, [rsp+28h+arg_8]
0x18000956b  mov     rbp, [rsp+28h+arg_0]
0x180009570  mov     r14, [rsp+28h+arg_10]
0x180009575  mov     eax, ebx
0x180009577  mov     rbx, [rsp+28h+arg_18]
0x18000957c  add     rsp, 20h
0x180009580  pop     rdi
0x180009581  retn
0x180009583  lea     r8, [rax+158h]; ThreadInformation
0x18000958a  cmp     [r8], rbp
0x18000958d  jnz     short loc_1800095F6
0x18000958f  mov     r8, rsi
0x180009592  mov     edx, 2000000h
0x180009597  mov     ecx, 2
0x18000959c  call    cs:__imp_RtlImpersonateSelfEx
0x1800095a3  nop     dword ptr [rax+rax+00h]
0x1800095a8  jmp     short loc_180009555
0x1800095aa  mov     rcx, rsi
0x1800095ad  call    cs:__imp_LsaImpersonateKsecCaller
0x1800095b4  nop     dword ptr [rax+rax+00h]
0x1800095b9  mov     ebx, eax
0x1800095bb  test    eax, eax
0x1800095bd  jns     short loc_18000955F
0x1800095bf  jmp     loc_1800094F7
0x1800095c4  cmp     [rax+3Ch], bpl
0x1800095c8  jz      short loc_1800095D0
0x1800095ca  cmp     dword ptr [rax+38h], 2
0x1800095ce  jl      short loc_180009641
0x1800095d0  mov     r9d, 8; ThreadInformationLength
0x1800095d6  mov     r8, rsi; ThreadInformation
0x1800095d9  mov     edx, 5; ThreadInformationClass
0x1800095de  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800095e5  call    cs:__imp_NtSetInformationThread
0x1800095ec  nop     dword ptr [rax+rax+00h]
0x1800095f1  jmp     loc_180009555
0x1800095f6  mov     edx, 5; ThreadInformationClass
0x1800095fb  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180009602  mov     r9d, 8; ThreadInformationLength
0x180009608  call    cs:__imp_NtSetInformationThread
0x18000960f  nop     dword ptr [rax+rax+00h]
0x180009614  mov     ebx, eax
0x180009616  test    eax, eax
0x180009618  js      loc_180009566
0x18000961e  mov     r14d, 1
0x180009624  movzx   r8d, r14b
0x180009628  jmp     loc_18000953A
0x18000962d  mov     ebx, 0C022001Ch
0x180009632  jmp     loc_180009575
0x180009637  mov     ebx, 0C000010Ah
0x18000963c  jmp     loc_180009566
0x180009641  mov     ebx, 0C00000A5h
0x180009646  jmp     loc_180009566
0x18000964b  mov     ebx, 0C0000037h
0x180009650  jmp     loc_180009566
0x180009655  test    r14d, r14d
0x180009658  jz      loc_180009566
0x18000965e  test    ebp, ebp
0x180009660  jz      short loc_180009673
0x180009662  call    cs:__imp_RpcRevertToSelf
0x180009669  nop     dword ptr [rax+rax+00h]
0x18000966e  jmp     loc_180009566
0x180009673  call    cs:__imp_RevertToSelf
0x18000967a  nop     dword ptr [rax+rax+00h]
0x18000967f  jmp     loc_180009566
```
