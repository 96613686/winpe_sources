# LsaDbpGetCurrentOwnerAndPrimaryGroup(_TOKEN_OWNER * *,_TOKEN_PRIMARY_GROUP * *)

- ea: `0x1800361ec`
- end: `0x180036328`
- name: `?LsaDbpGetCurrentOwnerAndPrimaryGroup@@YAJPEAPEAU_TOKEN_OWNER@@PEAPEAU_TOKEN_PRIMARY_GROUP@@@Z`
- size: `316`
- prototype: `__int64 __fastcall(struct _TOKEN_OWNER **, struct _TOKEN_PRIMARY_GROUP **)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800115a8`
- `0x180035fdc`
- `0x1800360f8`
- `0x180036a7c`

## callees

- `0x1800361ec`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180036224`
- `RPCRT4!RpcImpersonateClient` at `0x180036224`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003622c`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003630d`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003622c`
- `RPCRT4!I_RpcMapWin32Status` at `0x18003630d`
- `RPCRT4!RpcRevertToSelf` at `0x180036305`
- `RPCRT4!RpcRevertToSelf` at `0x180036305`
- `LSASRV!LsapAllocateLsaHeap` at `0x18003624d`
- `LSASRV!LsapAllocateLsaHeap` at `0x180036299`
- `LSASRV!LsapAllocateLsaHeap` at `0x18003624d`
- `LSASRV!LsapAllocateLsaHeap` at `0x180036299`
- `LSASRV!LsapFreeLsaHeap` at `0x1800362d9`
- `LSASRV!LsapFreeLsaHeap` at `0x1800362f3`
- `LSASRV!LsapFreeLsaHeap` at `0x1800362d9`
- `LSASRV!LsapFreeLsaHeap` at `0x1800362f3`
- `ntdll!NtQueryInformationToken` at `0x180036280`
- `ntdll!NtQueryInformationToken` at `0x1800362c5`
- `ntdll!NtQueryInformationToken` at `0x180036280`
- `ntdll!NtQueryInformationToken` at `0x1800362c5`

## pseudocode

```c
__int64 __fastcall LsaDbpGetCurrentOwnerAndPrimaryGroup(struct _TOKEN_OWNER **a1, struct _TOKEN_PRIMARY_GROUP **a2)
{
  char v2; // bp
  RPC_STATUS v5; // eax
  __int64 v6; // rdx
  int v7; // ebx
  __int64 v8; // r8
  struct _TOKEN_OWNER *LsaHeap; // rax
  struct _TOKEN_PRIMARY_GROUP *v10; // rax
  RPC_STATUS v11; // eax
  ULONG TokenInformationLength; // [rsp+50h] [rbp+8h] BYREF

  v2 = 0;
  TokenInformationLength = 0;
  *a1 = 0;
  if ( a2 )
    *a2 = 0;
  v5 = RpcImpersonateClient(0);
  v7 = I_RpcMapWin32Status(v5);
  if ( v7 >= 0 )
  {
    v2 = 1;
    TokenInformationLength = 76;
    LsaHeap = (struct _TOKEN_OWNER *)LsapAllocateLsaHeap(76);
    *a1 = LsaHeap;
    if ( !LsaHeap )
    {
LABEL_5:
      v7 = -1073741670;
      goto LABEL_10;
    }
    v7 = NtQueryInformationToken(
           (HANDLE)0xFFFFFFFFFFFFFFFBLL,
           TokenOwner,
           LsaHeap,
           TokenInformationLength,
           &TokenInformationLength);
    if ( v7 >= 0 )
    {
      if ( !a2 )
        goto LABEL_16;
      TokenInformationLength = 76;
      v10 = (struct _TOKEN_PRIMARY_GROUP *)LsapAllocateLsaHeap(76);
      *a2 = v10;
      if ( !v10 )
        goto LABEL_5;
      v7 = NtQueryInformationToken(
             (HANDLE)0xFFFFFFFFFFFFFFFBLL,
             TokenPrimaryGroup,
             v10,
             TokenInformationLength,
             &TokenInformationLength);
      if ( v7 >= 0 )
      {
LABEL_16:
        v11 = RpcRevertToSelf();
        I_RpcMapWin32Status(v11);
        return (unsigned int)v7;
      }
    }
  }
LABEL_10:
  if ( *a1 )
  {
    LsapFreeLsaHeap(*a1, v6, v8);
    *a1 = 0;
  }
  if ( a2 && *a2 )
  {
    LsapFreeLsaHeap(*a2, v6, v8);
    *a2 = 0;
  }
  if ( v2 )
    goto LABEL_16;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800361ec  mov     [rsp+arg_8], rbx
0x1800361f1  mov     [rsp+arg_10], rbp
0x1800361f6  push    rsi
0x1800361f7  push    rdi
0x1800361f8  push    r15
0x1800361fa  sub     rsp, 30h
0x1800361fe  xor     bpl, bpl
0x180036201  mov     [rsp+48h+TokenInformationLength], 0
0x180036209  mov     qword ptr [rcx], 0
0x180036210  mov     rdi, rdx
0x180036213  mov     rsi, rcx
0x180036216  test    rdx, rdx
0x180036219  jz      short loc_180036222
0x18003621b  mov     qword ptr [rdx], 0
0x180036222  xor     ecx, ecx; BindingHandle
0x180036224  call    cs:__imp_RpcImpersonateClient
0x18003622a  mov     ecx, eax; Status
0x18003622c  call    cs:__imp_I_RpcMapWin32Status
0x180036232  mov     ebx, eax
0x180036234  test    eax, eax
0x180036236  js      loc_1800362D1
0x18003623c  mov     r15d, 4Ch ; 'L'
0x180036242  mov     bpl, 1
0x180036245  mov     ecx, r15d
0x180036248  mov     [rsp+48h+TokenInformationLength], r15d
0x18003624d  call    cs:__imp_LsapAllocateLsaHeap
0x180036253  mov     [rsi], rax
0x180036256  test    rax, rax
0x180036259  jnz     short loc_180036262
0x18003625b  mov     ebx, 0C000009Ah
0x180036260  jmp     short loc_1800362D1
0x180036262  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x180036267  lea     rcx, [rsp+48h+TokenInformationLength]
0x18003626c  mov     [rsp+48h+ReturnLength], rcx; ReturnLength
0x180036271  mov     r8, rax; TokenInformation
0x180036274  mov     rcx, 0FFFFFFFFFFFFFFFBh; TokenHandle
0x18003627b  mov     edx, 4; TokenInformationClass
0x180036280  call    cs:__imp_NtQueryInformationToken
0x180036286  mov     ebx, eax
0x180036288  test    eax, eax
0x18003628a  js      short loc_1800362D1
0x18003628c  test    rdi, rdi
0x18003628f  jz      short loc_180036305
0x180036291  mov     rcx, r15
0x180036294  mov     [rsp+48h+TokenInformationLength], r15d
0x180036299  call    cs:__imp_LsapAllocateLsaHeap
0x18003629f  mov     [rdi], rax
0x1800362a2  test    rax, rax
0x1800362a5  jz      short loc_18003625B
0x1800362a7  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x1800362ac  lea     rdx, [rsp+48h+TokenInformationLength]
0x1800362b1  mov     [rsp+48h+ReturnLength], rdx; ReturnLength
0x1800362b6  mov     r8, rax; TokenInformation
0x1800362b9  mov     edx, 5; TokenInformationClass
0x1800362be  mov     rcx, 0FFFFFFFFFFFFFFFBh; TokenHandle
0x1800362c5  call    cs:__imp_NtQueryInformationToken
0x1800362cb  mov     ebx, eax
0x1800362cd  test    eax, eax
0x1800362cf  jns     short loc_180036305
0x1800362d1  mov     rcx, [rsi]
0x1800362d4  test    rcx, rcx
0x1800362d7  jz      short loc_1800362E6
0x1800362d9  call    cs:__imp_LsapFreeLsaHeap
0x1800362df  mov     qword ptr [rsi], 0
0x1800362e6  test    rdi, rdi
0x1800362e9  jz      short loc_180036300
0x1800362eb  mov     rcx, [rdi]
0x1800362ee  test    rcx, rcx
0x1800362f1  jz      short loc_180036300
0x1800362f3  call    cs:__imp_LsapFreeLsaHeap
0x1800362f9  mov     qword ptr [rdi], 0
0x180036300  test    bpl, bpl
0x180036303  jz      short loc_180036313
0x180036305  call    cs:__imp_RpcRevertToSelf
0x18003630b  mov     ecx, eax; Status
0x18003630d  call    cs:__imp_I_RpcMapWin32Status
0x180036313  mov     rbp, [rsp+48h+arg_10]
0x180036318  mov     eax, ebx
0x18003631a  mov     rbx, [rsp+48h+arg_8]
0x18003631f  add     rsp, 30h
0x180036323  pop     r15
0x180036325  pop     rdi
0x180036326  pop     rsi
0x180036327  retn
```
