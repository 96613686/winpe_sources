# EfsKRpcDecryptFek

- ea: `0x18000b880`
- end: `0x18000ba91`
- name: `EfsKRpcDecryptFek`
- size: `529`
- prototype: `void __fastcall(void *, __int64, __int64, __int64, __int64, _DWORD *, void **, _DWORD *, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180003510`
- `0x180003540`
- `0x18000b880`
- `0x18000bf94`
- `0x18000c244`
- `0x18000c386`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x18000ba77`
- `RPCRT4!RpcRaiseException` at `0x18000ba77`
- `EFSCORE!EfsDllValidateEfsStream` at `0x18000b941`
- `EFSCORE!EfsDllValidateEfsStream` at `0x18000b941`
- `EFSCORE!EfsDllDisabled` at `0x18000b929`
- `EFSCORE!EfsDllDisabled` at `0x18000b929`
- `EFSCORE!EfsDllFreeHeap` at `0x18000b9b7`
- `EFSCORE!EfsDllFreeHeap` at `0x18000b9f7`
- `EFSCORE!EfsDllFreeHeap` at `0x18000ba1c`
- `EFSCORE!EfsDllFreeHeap` at `0x18000ba2b`
- `EFSCORE!EfsDllFreeHeap` at `0x18000b9b7`
- `EFSCORE!EfsDllFreeHeap` at `0x18000b9f7`
- `EFSCORE!EfsDllFreeHeap` at `0x18000ba1c`
- `EFSCORE!EfsDllFreeHeap` at `0x18000ba2b`

## pseudocode

```c
void __fastcall EfsKRpcDecryptFek(
        void *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _DWORD *a6,
        void **a7,
        _DWORD *a8,
        void **a9)
{
  EfspValidateClientCall(a1);
  if ( *a7 )
  {
    MIDL_user_free(*a7);
    *a7 = 0;
  }
  if ( a6 )
    *a6 = 0;
  if ( *a9 )
  {
    MIDL_user_free(*a9);
    *a9 = 0;
  }
  if ( a8 )
    *a8 = 0;
  RpcRaiseException(-1073741790);
}

```

## disassembly

```asm
0x18000b880  mov     [rsp-40h+arg_18], r9
0x18000b885  push    rbp
0x18000b886  push    rbx
0x18000b887  push    rsi
0x18000b888  push    rdi
0x18000b889  push    r12
0x18000b88b  push    r13
0x18000b88d  push    r14
0x18000b88f  push    r15
0x18000b891  mov     rbp, rsp
0x18000b894  sub     rsp, 58h
0x18000b898  mov     r13d, edx
0x18000b89b  mov     [rbp+var_28], 0
0x18000b89f  lea     rdx, [rbp+var_24]
0x18000b8a3  mov     [rbp+Src], 0
0x18000b8ab  mov     r15, r8
0x18000b8ae  mov     [rbp+var_18], 0
0x18000b8b6  mov     [rbp+var_24], 0
0x18000b8bd  call    EfspValidateClientCall
0x18000b8c2  mov     r14, [rbp+arg_40]
0x18000b8c9  xor     ecx, ecx
0x18000b8cb  mov     rdi, [rbp+arg_38]
0x18000b8d2  mov     r12, [rbp+arg_30]
0x18000b8d6  mov     rsi, [rbp+arg_28]
0x18000b8da  test    eax, eax
0x18000b8dc  jnz     loc_18000BA0E
0x18000b8e2  cmp     [rbp+var_24], ecx
0x18000b8e5  jz      loc_18000BA0E
0x18000b8eb  mov     rbx, [rbp+arg_20]
0x18000b8ef  test    rbx, rbx
0x18000b8f2  jnz     short loc_18000B8FE
0x18000b8f4  mov     ebx, 0C000000Dh
0x18000b8f9  jmp     loc_18000BA13
0x18000b8fe  test    r12, r12
0x18000b901  jz      short loc_18000B8F4
0x18000b903  test    r14, r14
0x18000b906  jz      short loc_18000B8F4
0x18000b908  test    rsi, rsi
0x18000b90b  jz      short loc_18000B8F4
0x18000b90d  test    rdi, rdi
0x18000b910  jz      short loc_18000B8F4
0x18000b912  cmp     cs:EfsServerInitialized, cl
0x18000b918  mov     [r12], rcx
0x18000b91c  mov     [r14], rcx
0x18000b91f  mov     [rsi], ecx
0x18000b921  mov     [rdi], ecx
0x18000b923  jz      loc_18000BA07
0x18000b929  call    cs:__imp_EfsDllDisabled
0x18000b92f  test    al, al
0x18000b931  jnz     loc_18000BA07
0x18000b937  lea     r8, [rbp+var_28]
0x18000b93b  mov     edx, r13d
0x18000b93e  mov     rcx, r15
0x18000b941  call    cs:__imp_EfsDllValidateEfsStream
0x18000b947  test    eax, eax
0x18000b949  jnz     short loc_18000B8F4
0x18000b94b  cmp     [rbp+var_28], al
0x18000b94e  jz      short loc_18000B8F4
0x18000b950  mov     rdx, [rbp+arg_18]
0x18000b954  lea     rax, [rbp+var_18]
0x18000b958  lea     r9, [rbp+Src]
0x18000b95c  mov     [rsp+58h+var_38], rax
0x18000b961  mov     r8, rbx
0x18000b964  mov     rcx, r15
0x18000b967  call    EfspDecryptFek
0x18000b96c  mov     ebx, eax
0x18000b96e  test    eax, eax
0x18000b970  js      loc_18000BA13
0x18000b976  mov     rcx, [rbp+Src]
0x18000b97a  test    rcx, rcx
0x18000b97d  jz      short loc_18000B9C5
0x18000b97f  mov     r15d, [rcx]
0x18000b982  add     r15d, 38h ; '8'
0x18000b986  mov     ecx, r15d; size
0x18000b989  mov     r13d, r15d
0x18000b98c  call    MIDL_user_allocate
0x18000b991  mov     [r12], rax
0x18000b995  test    rax, rax
0x18000b998  jnz     short loc_18000B9A1
0x18000b99a  mov     ebx, 0C0000017h
0x18000b99f  jmp     short loc_18000BA13
0x18000b9a1  mov     rdx, [rbp+Src]; Src
0x18000b9a5  mov     r8, r13; Size
0x18000b9a8  mov     rcx, rax; void *
0x18000b9ab  call    memcpy_0
0x18000b9b0  mov     rcx, [rbp+Src]
0x18000b9b4  mov     [rsi], r15d
0x18000b9b7  call    cs:__imp_EfsDllFreeHeap
0x18000b9bd  mov     [rbp+Src], 0
0x18000b9c5  mov     rcx, [rbp+var_18]
0x18000b9c9  test    rcx, rcx
0x18000b9cc  jz      short loc_18000BA13
0x18000b9ce  mov     r15d, [rcx]
0x18000b9d1  mov     ecx, r15d; size
0x18000b9d4  call    MIDL_user_allocate
0x18000b9d9  mov     [r14], rax
0x18000b9dc  test    rax, rax
0x18000b9df  jz      short loc_18000B99A
0x18000b9e1  mov     rdx, [rbp+var_18]; Src
0x18000b9e5  mov     r8d, r15d; Size
0x18000b9e8  mov     rcx, rax; void *
0x18000b9eb  call    memcpy_0
0x18000b9f0  mov     rcx, [rbp+var_18]
0x18000b9f4  mov     [rdi], r15d
0x18000b9f7  call    cs:__imp_EfsDllFreeHeap
0x18000b9fd  mov     [rbp+var_18], 0
0x18000ba05  jmp     short loc_18000BA13
0x18000ba07  mov     ebx, 0C00000BBh
0x18000ba0c  jmp     short loc_18000BA13
0x18000ba0e  mov     ebx, 0C0000022h
0x18000ba13  mov     rcx, [rbp+Src]
0x18000ba17  test    rcx, rcx
0x18000ba1a  jz      short loc_18000BA22
0x18000ba1c  call    cs:__imp_EfsDllFreeHeap
0x18000ba22  mov     rcx, [rbp+var_18]
0x18000ba26  test    rcx, rcx
0x18000ba29  jz      short loc_18000BA31
0x18000ba2b  call    cs:__imp_EfsDllFreeHeap
0x18000ba31  test    ebx, ebx
0x18000ba33  jns     short loc_18000BA7E
0x18000ba35  mov     rcx, [r12]; void *
0x18000ba39  test    rcx, rcx
0x18000ba3c  jz      short loc_18000BA4B
0x18000ba3e  call    MIDL_user_free
0x18000ba43  mov     qword ptr [r12], 0
0x18000ba4b  test    rsi, rsi
0x18000ba4e  jz      short loc_18000BA56
0x18000ba50  mov     dword ptr [rsi], 0
0x18000ba56  mov     rcx, [r14]; void *
0x18000ba59  test    rcx, rcx
0x18000ba5c  jz      short loc_18000BA6A
0x18000ba5e  call    MIDL_user_free
0x18000ba63  mov     qword ptr [r14], 0
0x18000ba6a  test    rdi, rdi
0x18000ba6d  jz      short loc_18000BA75
0x18000ba6f  mov     dword ptr [rdi], 0
0x18000ba75  mov     ecx, ebx; exception
0x18000ba77  call    cs:__imp_RpcRaiseException
0x18000ba7d  int     3; Trap to Debugger
0x18000ba7e  mov     eax, ebx
0x18000ba80  add     rsp, 58h
0x18000ba84  pop     r15
0x18000ba86  pop     r14
0x18000ba88  pop     r13
0x18000ba8a  pop     r12
0x18000ba8c  pop     rdi
0x18000ba8d  pop     rsi
0x18000ba8e  pop     rbx
0x18000ba8f  pop     rbp
0x18000ba90  retn
```
