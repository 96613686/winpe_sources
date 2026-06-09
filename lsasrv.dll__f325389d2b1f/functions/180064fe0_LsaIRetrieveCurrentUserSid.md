# LsaIRetrieveCurrentUserSid

- ea: `0x180064fe0`
- end: `0x180065280`
- name: `LsaIRetrieveCurrentUserSid`
- size: `672`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800fab50`

## callees

- `0x180064fe0`
- `0x1800b86d0`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800650ed`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800650ed`
- `ntdll!RtlCopySid` at `0x180065112`
- `ntdll!RtlCopySid` at `0x180065112`
- `ntdll!NtClose` at `0x18006507f`
- `ntdll!NtClose` at `0x18006507f`
- `ntdll!RtlLengthSid` at `0x1800650d7`
- `ntdll!RtlLengthSid` at `0x1800650d7`
- `ntdll!NtQueryInformationToken` at `0x18006521c`
- `ntdll!NtQueryInformationToken` at `0x18006521c`
- `ntdll!NtOpenThreadToken` at `0x1800651ce`
- `ntdll!NtOpenThreadToken` at `0x1800651ce`
- `RPCRT4!RpcRevertToSelf` at `0x1800651dc`
- `RPCRT4!RpcRevertToSelf` at `0x1800651dc`
- `RPCRT4!I_RpcMapWin32Status` at `0x180065046`
- `RPCRT4!I_RpcMapWin32Status` at `0x180065188`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800651ea`
- `RPCRT4!I_RpcMapWin32Status` at `0x180065046`
- `RPCRT4!I_RpcMapWin32Status` at `0x180065188`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800651ea`
- `RPCRT4!RpcImpersonateClient` at `0x18006517a`
- `RPCRT4!RpcImpersonateClient` at `0x18006517a`
- `RPCRT4!I_RpcBindingInqClientTokenAttributes` at `0x180065038`
- `RPCRT4!I_RpcBindingInqClientTokenAttributes` at `0x180065038`

## pseudocode

```c
__int64 __fastcall LsaIRetrieveCurrentUserSid(_QWORD *a1)
{
  RPC_STATUS v2; // eax
  int v3; // edi
  LUID v4; // rbx
  DWORD LowPart; // esi
  unsigned __int64 v6; // rax
  unsigned __int64 v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rbx
  void *v10; // rcx
  SIZE_T v11; // r14
  HLOCAL v12; // rax
  HLOCAL v13; // rsi
  RPC_STATUS v15; // eax
  int v16; // eax
  RPC_STATUS v17; // eax
  int v18; // eax
  LUID AuthenticationId; // [rsp+30h] [rbp-59h] BYREF
  ULONG ReturnLength; // [rsp+38h] [rbp-51h] BYREF
  HANDLE Handle; // [rsp+40h] [rbp-49h] BYREF
  _QWORD v22[2]; // [rsp+48h] [rbp-41h] BYREF
  _QWORD v23[2]; // [rsp+58h] [rbp-31h] BYREF
  _OWORD TokenInformation[3]; // [rsp+68h] [rbp-21h] BYREF
  __int64 v25; // [rsp+98h] [rbp+Fh]

  *a1 = 0;
  Handle = 0;
  ReturnLength = 0;
  v25 = 0;
  AuthenticationId = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  v2 = I_RpcBindingInqClientTokenAttributes(0, 0, &AuthenticationId, 0);
  v3 = I_RpcMapWin32Status(v2);
  if ( v3 >= 0 )
    goto LABEL_2;
  v15 = RpcImpersonateClient(0);
  v16 = I_RpcMapWin32Status(v15);
  v3 = v16;
  switch ( v16 )
  {
    case -1073610687:
      AuthenticationId = (LUID)998LL;
      v3 = 0;
LABEL_2:
      v4 = AuthenticationId;
LABEL_3:
      v22[0] = v4;
      LowPart = v4.LowPart;
      v6 = HIDWORD(*(unsigned __int64 *)&v4);
      v7 = HIDWORD(*(unsigned __int64 *)&v4);
      goto LABEL_4;
    case -1073610726:
    case -1073610686:
      v4 = LsapGlobalProcessTokenLuid;
      v3 = 0;
      AuthenticationId = LsapGlobalProcessTokenLuid;
      goto LABEL_3;
    case 0:
      v3 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xAu, 1u, &Handle);
      v17 = RpcRevertToSelf();
      v18 = I_RpcMapWin32Status(v17);
      if ( v3 < 0 )
        goto LABEL_24;
      v3 = v18;
      break;
  }
  if ( v3 >= 0 )
  {
    v3 = NtQueryInformationToken(Handle, TokenStatistics, TokenInformation, 0x38u, &ReturnLength);
    if ( v3 >= 0 )
    {
      v4 = (LUID)*((_QWORD *)&TokenInformation[0] + 1);
      AuthenticationId = (LUID)*((_QWORD *)&TokenInformation[0] + 1);
      goto LABEL_3;
    }
  }
LABEL_24:
  LowPart = 0;
  LODWORD(v6) = 0;
  LODWORD(v7) = 0;
LABEL_4:
  if ( Handle )
    NtClose(Handle);
  else
    LODWORD(v7) = v6;
  if ( v3 < 0 )
    return (unsigned int)v3;
  v22[0] = (int)v7;
  v22[1] = LowPart;
  v8 = (*((__int64 (__fastcall **)(void *, _QWORD *))LogonSessionPackage + 9))(LogonSessionTable, v22);
  v9 = v8;
  if ( v8 )
  {
    v10 = *(void **)(v8 + 224);
    if ( v10 )
    {
      v11 = RtlLengthSid(v10);
      v12 = LocalAlloc(0x40u, v11);
      v13 = v12;
      if ( v12 )
      {
        RtlCopySid(v11, v12, *(PSID *)(v9 + 224));
        *a1 = v13;
      }
      else
      {
        v3 = -1073741801;
      }
    }
    else
    {
      v3 = -1073741564;
    }
    v23[0] = *(int *)(v9 + 116);
    v23[1] = *(unsigned int *)(v9 + 112);
    (*((void (__fastcall **)(void *, _QWORD *))LogonSessionPackage + 10))(LogonSessionTable, v23);
    return (unsigned int)v3;
  }
  return 3221225567LL;
}

```

## disassembly

```asm
0x180064fe0  push    rbp
0x180064fe2  push    rbx
0x180064fe3  push    rsi
0x180064fe4  push    rdi
0x180064fe5  push    r14
0x180064fe7  push    r15
0x180064fe9  lea     rbp, [rsp-2Fh]
0x180064fee  sub     rsp, 0B8h
0x180064ff5  mov     rax, cs:__security_cookie
0x180064ffc  xor     rax, rsp
0x180064fff  mov     [rbp+57h+var_40], rax
0x180065003  xor     r14d, r14d
0x180065006  lea     r8, [rbp+57h+AuthenticationId]; AuthenticationId
0x18006500a  xorps   xmm0, xmm0
0x18006500d  mov     [rcx], r14
0x180065010  mov     r15, rcx
0x180065013  mov     [rbp+57h+Handle], r14
0x180065017  xor     eax, eax
0x180065019  mov     [rbp+57h+var_A8], r14d
0x18006501d  xor     ecx, ecx; Binding
0x18006501f  mov     [rbp+57h+var_48], rax
0x180065023  xor     r9d, r9d; ModifiedId
0x180065026  mov     qword ptr [rbp+57h+AuthenticationId.LowPart], r14
0x18006502a  xor     edx, edx; TokenId
0x18006502c  movups  [rbp+57h+TokenInformation], xmm0
0x180065030  movups  [rbp+57h+var_68], xmm0
0x180065034  movups  [rbp+57h+var_58], xmm0
0x180065038  call    cs:__imp_I_RpcBindingInqClientTokenAttributes
0x18006503f  nop     dword ptr [rax+rax+00h]
0x180065044  mov     ecx, eax; Status
0x180065046  call    cs:__imp_I_RpcMapWin32Status
0x18006504d  nop     dword ptr [rax+rax+00h]
0x180065052  mov     edi, eax
0x180065054  test    eax, eax
0x180065056  js      loc_180065178
0x18006505c  mov     rbx, qword ptr [rbp+57h+AuthenticationId.LowPart]
0x180065060  mov     rax, rbx
0x180065063  mov     [rbp+57h+var_98], rbx
0x180065067  mov     esi, dword ptr [rbp+57h+var_98]
0x18006506a  shr     rax, 20h
0x18006506e  shr     rbx, 20h
0x180065072  mov     rcx, [rbp+57h+Handle]; Handle
0x180065076  test    rcx, rcx
0x180065079  jz      loc_18006516A
0x18006507f  call    cs:__imp_NtClose
0x180065086  nop     dword ptr [rax+rax+00h]
0x18006508b  test    edi, edi
0x18006508d  js      loc_18006514B
0x180065093  mov     rcx, cs:?LogonSessionTable@@3PEAXEA; void * LogonSessionTable
0x18006509a  lea     rdx, [rbp+57h+var_98]
0x18006509e  movsxd  rax, ebx
0x1800650a1  mov     [rbp+57h+var_98], rax
0x1800650a5  mov     eax, esi
0x1800650a7  mov     [rbp+57h+var_90], rax
0x1800650ab  mov     rax, cs:?LogonSessionPackage@@3PEAU_HANDLE_PACKAGE@@EA; _HANDLE_PACKAGE * LogonSessionPackage
0x1800650b2  mov     rax, [rax+48h]
0x1800650b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800650bb  mov     rbx, rax
0x1800650be  test    rax, rax
0x1800650c1  jz      loc_18006526C
0x1800650c7  mov     rcx, [rax+0E0h]; Sid
0x1800650ce  test    rcx, rcx
0x1800650d1  jz      loc_180065171
0x1800650d7  call    cs:__imp_RtlLengthSid
0x1800650de  nop     dword ptr [rax+rax+00h]
0x1800650e3  mov     edx, eax; uBytes
0x1800650e5  mov     ecx, 40h ; '@'; uFlags
0x1800650ea  mov     r14d, eax
0x1800650ed  call    cs:__imp_LocalAlloc
0x1800650f4  nop     dword ptr [rax+rax+00h]
0x1800650f9  mov     rsi, rax
0x1800650fc  test    rax, rax
0x1800650ff  jz      loc_180065276
0x180065105  mov     r8, [rbx+0E0h]; SourceSid
0x18006510c  mov     rdx, rax; DestinationSid
0x18006510f  mov     ecx, r14d; DestinationSidLength
0x180065112  call    cs:__imp_RtlCopySid
0x180065119  nop     dword ptr [rax+rax+00h]
0x18006511e  mov     [r15], rsi
0x180065121  movsxd  rcx, dword ptr [rbx+74h]
0x180065125  lea     rdx, [rbp+57h+var_88]
0x180065129  mov     [rbp+57h+var_88], rcx
0x18006512d  mov     ecx, [rbx+70h]
0x180065130  mov     [rbp+57h+var_80], rcx
0x180065134  mov     rcx, cs:?LogonSessionPackage@@3PEAU_HANDLE_PACKAGE@@EA; _HANDLE_PACKAGE * LogonSessionPackage
0x18006513b  mov     rax, [rcx+50h]
0x18006513f  mov     rcx, cs:?LogonSessionTable@@3PEAXEA; void * LogonSessionTable
0x180065146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006514b  mov     eax, edi
0x18006514d  mov     rcx, [rbp+57h+var_40]
0x180065151  xor     rcx, rsp; StackCookie
0x180065154  call    __security_check_cookie
0x180065159  add     rsp, 0B8h
0x180065160  pop     r15
0x180065162  pop     r14
0x180065164  pop     rdi
0x180065165  pop     rsi
0x180065166  pop     rbx
0x180065167  pop     rbp
0x180065168  retn
0x18006516a  mov     ebx, eax
0x18006516c  jmp     loc_18006508B
0x180065171  mov     edi, 0C0000104h
0x180065176  jmp     short loc_180065121
0x180065178  xor     ecx, ecx; BindingHandle
0x18006517a  call    cs:__imp_RpcImpersonateClient
0x180065181  nop     dword ptr [rax+rax+00h]
0x180065186  mov     ecx, eax; Status
0x180065188  call    cs:__imp_I_RpcMapWin32Status
0x18006518f  nop     dword ptr [rax+rax+00h]
0x180065194  mov     edi, eax
0x180065196  cmp     eax, 0C0020041h
0x18006519b  jz      loc_18006525C
0x1800651a1  cmp     eax, 0C002001Ah
0x1800651a6  jz      loc_180065249
0x1800651ac  cmp     eax, 0C0020042h
0x1800651b1  jz      loc_180065249
0x1800651b7  test    eax, eax
0x1800651b9  jnz     short loc_1800651FC
0x1800651bb  lea     r9, [rbp+57h+Handle]; TokenHandle
0x1800651bf  mov     r8b, 1; OpenAsSelf
0x1800651c2  mov     edx, 0Ah; DesiredAccess
0x1800651c7  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800651ce  call    cs:__imp_NtOpenThreadToken
0x1800651d5  nop     dword ptr [rax+rax+00h]
0x1800651da  mov     edi, eax
0x1800651dc  call    cs:__imp_RpcRevertToSelf
0x1800651e3  nop     dword ptr [rax+rax+00h]
0x1800651e8  mov     ecx, eax; Status
0x1800651ea  call    cs:__imp_I_RpcMapWin32Status
0x1800651f1  nop     dword ptr [rax+rax+00h]
0x1800651f6  test    edi, edi
0x1800651f8  js      short loc_18006523B
0x1800651fa  mov     edi, eax
0x1800651fc  test    edi, edi
0x1800651fe  js      short loc_18006523B
0x180065200  mov     rcx, [rbp+57h+Handle]; TokenHandle
0x180065204  lea     rax, [rbp+57h+var_A8]
0x180065208  mov     r9d, 38h ; '8'; TokenInformationLength
0x18006520e  mov     [rsp+0E0h+ReturnLength], rax; ReturnLength
0x180065213  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180065217  mov     edx, 0Ah; TokenInformationClass
0x18006521c  call    cs:__imp_NtQueryInformationToken
0x180065223  nop     dword ptr [rax+rax+00h]
0x180065228  mov     edi, eax
0x18006522a  test    eax, eax
0x18006522c  js      short loc_18006523B
0x18006522e  mov     rbx, qword ptr [rbp+57h+TokenInformation+8]
0x180065232  mov     qword ptr [rbp+57h+AuthenticationId.LowPart], rbx
0x180065236  jmp     loc_180065060
0x18006523b  mov     esi, r14d
0x18006523e  mov     eax, r14d
0x180065241  mov     ebx, r14d
0x180065244  jmp     loc_180065072
0x180065249  mov     rbx, cs:?LsapGlobalProcessTokenLuid@@3U_LUID@@A; _LUID LsapGlobalProcessTokenLuid
0x180065250  mov     edi, r14d
0x180065253  mov     qword ptr [rbp+57h+AuthenticationId.LowPart], rbx
0x180065257  jmp     loc_180065060
0x18006525c  mov     qword ptr [rbp+57h+AuthenticationId.LowPart], 3E6h
0x180065264  mov     edi, r14d
0x180065267  jmp     loc_18006505C
0x18006526c  mov     eax, 0C000005Fh
0x180065271  jmp     loc_18006514D
0x180065276  mov     edi, 0C0000017h
0x18006527b  jmp     loc_180065121
```
