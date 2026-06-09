# EfspGenerateKey

- ea: `0x18000c0ac`
- end: `0x18000c23b`
- name: `EfspGenerateKey`
- size: `399`
- prototype: `__int64 __fastcall(__int64, unsigned int, char, __int64, _QWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000bad0`
- `0x18000bc20`

## callees

- `0x18000c0ac`
- `0x18000c392`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c153`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c153`
- `RPCRT4!RpcRevertToSelf` at `0x18000c21d`
- `RPCRT4!RpcRevertToSelf` at `0x18000c21d`
- `RPCRT4!RpcImpersonateClient` at `0x18000c129`
- `RPCRT4!RpcImpersonateClient` at `0x18000c129`
- `EFSCORE!EfsDllConstructEFS` at `0x18000c1aa`
- `EFSCORE!EfsDllConstructEFS` at `0x18000c1aa`
- `EFSCORE!EfsDllValidateEfsStream` at `0x18000c10b`
- `EFSCORE!EfsDllValidateEfsStream` at `0x18000c10b`
- `EFSCORE!EfsDllErrorToNtStatus` at `0x18000c160`
- `EFSCORE!EfsDllErrorToNtStatus` at `0x18000c160`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x18000c204`
- `EFSCORE!EfsDllUnloadUserProfile` at `0x18000c204`
- `EFSCORE!EfsDllFreeUserInfo` at `0x18000c213`
- `EFSCORE!EfsDllFreeUserInfo` at `0x18000c213`
- `EFSCORE!EfsDllGetUserInfo` at `0x18000c149`
- `EFSCORE!EfsDllGetUserInfo` at `0x18000c149`
- `EFSCORE!EfsDllLoadUserProfile` at `0x18000c17d`
- `EFSCORE!EfsDllLoadUserProfile` at `0x18000c17d`
- `EFSCORE!EfsDllFreeHeap` at `0x18000c1e6`
- `EFSCORE!EfsDllFreeHeap` at `0x18000c1f5`
- `EFSCORE!EfsDllFreeHeap` at `0x18000c1e6`
- `EFSCORE!EfsDllFreeHeap` at `0x18000c1f5`

## pseudocode

```c
__int64 __fastcall EfspGenerateKey(__int64 a1, unsigned int a2, char a3, __int64 a4, _QWORD *a5, _QWORD *a6)
{
  int v9; // ebx
  int v11; // r14d
  int v12; // r15d
  DWORD LastError; // eax
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 v16; // rax
  unsigned int v18; // [rsp+30h] [rbp-89h] BYREF
  __int64 v19; // [rsp+38h] [rbp-81h] BYREF
  __int64 v20; // [rsp+40h] [rbp-79h] BYREF
  _BYTE v21[176]; // [rsp+50h] [rbp-69h] BYREF
  char v22; // [rsp+110h] [rbp+57h] BYREF

  v18 = 0;
  v9 = 0;
  v11 = 0;
  v12 = 0;
  memset_0(v21, 0, 0x70u);
  v19 = 0;
  v20 = 0;
  v22 = 0;
  if ( a1 && ((unsigned int)EfsDllValidateEfsStream(a1, a2, &v22) || !v22) )
  {
    v18 = -1073741811;
  }
  else if ( RpcImpersonateClient(0) )
  {
    v18 = -1073741790;
  }
  else
  {
    v9 = 1;
    if ( (unsigned __int8)EfsDllGetUserInfo(v21)
      && (v11 = 1, (unsigned int)EfsDllLoadUserProfile(v21, 0))
      && (LOBYTE(v14) = a3, v12 = 1, (unsigned __int8)EfsDllConstructEFS(v21, a1, v14, a4, &v19, &v20)) )
    {
      v15 = v20;
      v20 = 0;
      *a6 = v15;
      v16 = v19;
      v19 = 0;
      *a5 = v16;
    }
    else
    {
      LastError = GetLastError();
      if ( !(unsigned int)EfsDllErrorToNtStatus(LastError, &v18) )
        v18 = -1073741823;
    }
  }
  if ( v19 )
    EfsDllFreeHeap(v19);
  if ( v20 )
    EfsDllFreeHeap(v20);
  if ( v12 )
    EfsDllUnloadUserProfile(v21);
  if ( v11 )
    EfsDllFreeUserInfo(v21);
  if ( v9 )
    RpcRevertToSelf();
  return v18;
}

```

## disassembly

```asm
0x18000c0ac  push    rbp
0x18000c0ae  push    rbx
0x18000c0af  push    rsi
0x18000c0b0  push    rdi
0x18000c0b1  push    r12
0x18000c0b3  push    r13
0x18000c0b5  push    r14
0x18000c0b7  push    r15
0x18000c0b9  lea     rbp, [rsp-0Fh]
0x18000c0be  sub     rsp, 0C8h
0x18000c0c5  mov     r13b, r8b
0x18000c0c8  mov     [rsp+100h+var_D0], 0
0x18000c0d0  mov     esi, edx
0x18000c0d2  mov     rdi, rcx
0x18000c0d5  xor     ebx, ebx
0x18000c0d7  lea     rcx, [rbp+47h+var_B0]; void *
0x18000c0db  xor     edx, edx; Val
0x18000c0dd  mov     r12, r9
0x18000c0e0  xor     r14d, r14d
0x18000c0e3  xor     r15d, r15d
0x18000c0e6  lea     r8d, [rbx+70h]; Size
0x18000c0ea  call    memset_0
0x18000c0ef  xor     eax, eax
0x18000c0f1  mov     [rsp+100h+var_C8], rax
0x18000c0f6  mov     [rbp+47h+var_C0], rax
0x18000c0fa  mov     [rbp+47h+arg_0], al
0x18000c0fd  test    rdi, rdi
0x18000c100  jz      short loc_18000C127
0x18000c102  lea     r8, [rbp+47h+arg_0]
0x18000c106  mov     edx, esi
0x18000c108  mov     rcx, rdi
0x18000c10b  call    cs:__imp_EfsDllValidateEfsStream
0x18000c111  test    eax, eax
0x18000c113  jnz     short loc_18000C11A
0x18000c115  cmp     [rbp+47h+arg_0], bl
0x18000c118  jnz     short loc_18000C127
0x18000c11a  mov     [rsp+100h+var_D0], 0C000000Dh
0x18000c122  jmp     loc_18000C1DC
0x18000c127  xor     ecx, ecx; BindingHandle
0x18000c129  call    cs:__imp_RpcImpersonateClient
0x18000c12f  test    eax, eax
0x18000c131  jz      short loc_18000C140
0x18000c133  mov     [rsp+100h+var_D0], 0C0000022h
0x18000c13b  jmp     loc_18000C1DC
0x18000c140  lea     rcx, [rbp+47h+var_B0]
0x18000c144  mov     ebx, 1
0x18000c149  call    cs:__imp_EfsDllGetUserInfo
0x18000c14f  test    al, al
0x18000c151  jnz     short loc_18000C174
0x18000c153  call    cs:__imp_GetLastError
0x18000c159  mov     ecx, eax
0x18000c15b  lea     rdx, [rsp+100h+var_D0]
0x18000c160  call    cs:__imp_EfsDllErrorToNtStatus
0x18000c166  test    eax, eax
0x18000c168  jnz     short loc_18000C1DC
0x18000c16a  mov     [rsp+100h+var_D0], 0C0000001h
0x18000c172  jmp     short loc_18000C1DC
0x18000c174  xor     edx, edx
0x18000c176  lea     rcx, [rbp+47h+var_B0]
0x18000c17a  mov     r14d, ebx
0x18000c17d  call    cs:__imp_EfsDllLoadUserProfile
0x18000c183  test    eax, eax
0x18000c185  jz      short loc_18000C153
0x18000c187  lea     rax, [rbp+47h+var_C0]
0x18000c18b  mov     r9, r12
0x18000c18e  mov     [rsp+100h+var_D8], rax
0x18000c193  lea     rcx, [rbp+47h+var_B0]
0x18000c197  lea     rax, [rsp+100h+var_C8]
0x18000c19c  mov     r8b, r13b
0x18000c19f  mov     rdx, rdi
0x18000c1a2  mov     [rsp+100h+var_E0], rax
0x18000c1a7  mov     r15d, ebx
0x18000c1aa  call    cs:__imp_EfsDllConstructEFS
0x18000c1b0  test    al, al
0x18000c1b2  jz      short loc_18000C153
0x18000c1b4  mov     rax, [rbp+47h+var_C0]
0x18000c1b8  mov     rcx, [rbp+47h+arg_28]
0x18000c1bc  mov     [rbp+47h+var_C0], 0
0x18000c1c4  mov     [rcx], rax
0x18000c1c7  mov     rax, [rsp+100h+var_C8]
0x18000c1cc  mov     rcx, [rbp+47h+arg_20]
0x18000c1d0  mov     [rsp+100h+var_C8], 0
0x18000c1d9  mov     [rcx], rax
0x18000c1dc  mov     rcx, [rsp+100h+var_C8]
0x18000c1e1  test    rcx, rcx
0x18000c1e4  jz      short loc_18000C1EC
0x18000c1e6  call    cs:__imp_EfsDllFreeHeap
0x18000c1ec  mov     rcx, [rbp+47h+var_C0]
0x18000c1f0  test    rcx, rcx
0x18000c1f3  jz      short loc_18000C1FB
0x18000c1f5  call    cs:__imp_EfsDllFreeHeap
0x18000c1fb  test    r15d, r15d
0x18000c1fe  jz      short loc_18000C20A
0x18000c200  lea     rcx, [rbp+47h+var_B0]
0x18000c204  call    cs:__imp_EfsDllUnloadUserProfile
0x18000c20a  test    r14d, r14d
0x18000c20d  jz      short loc_18000C219
0x18000c20f  lea     rcx, [rbp+47h+var_B0]
0x18000c213  call    cs:__imp_EfsDllFreeUserInfo
0x18000c219  test    ebx, ebx
0x18000c21b  jz      short loc_18000C223
0x18000c21d  call    cs:__imp_RpcRevertToSelf
0x18000c223  mov     eax, [rsp+100h+var_D0]
0x18000c227  add     rsp, 0C8h
0x18000c22e  pop     r15
0x18000c230  pop     r14
0x18000c232  pop     r13
0x18000c234  pop     r12
0x18000c236  pop     rdi
0x18000c237  pop     rsi
0x18000c238  pop     rbx
0x18000c239  pop     rbp
0x18000c23a  retn
```
