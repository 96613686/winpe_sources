# EfsKRpcDecryptFek

- ea: `0x18000c530`
- end: `0x18000c76c`
- name: `EfsKRpcDecryptFek`
- size: `572`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x1800036a0`
- `0x1800036e0`
- `0x18000c530`
- `0x18000ccf8`
- `0x18000d03c`
- `0x18000d186`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x18000c74b`
- `RPCRT4!RpcRaiseException` at `0x18000c74b`
- `EFSCORE!EfsDllValidateEfsStream` at `0x18000c5f7`
- `EFSCORE!EfsDllValidateEfsStream` at `0x18000c5f7`
- `EFSCORE!EfsDllDisabled` at `0x18000c5d9`
- `EFSCORE!EfsDllDisabled` at `0x18000c5d9`
- `EFSCORE!EfsDllFreeHeap` at `0x18000c673`
- `EFSCORE!EfsDllFreeHeap` at `0x18000c6b9`
- `EFSCORE!EfsDllFreeHeap` at `0x18000c6e4`
- `EFSCORE!EfsDllFreeHeap` at `0x18000c6f9`
- `EFSCORE!EfsDllFreeHeap` at `0x18000c673`
- `EFSCORE!EfsDllFreeHeap` at `0x18000c6b9`
- `EFSCORE!EfsDllFreeHeap` at `0x18000c6e4`
- `EFSCORE!EfsDllFreeHeap` at `0x18000c6f9`

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
0x18000c530  mov     [rsp-40h+arg_18], r9
0x18000c535  push    rbp
0x18000c536  push    rbx
0x18000c537  push    rsi
0x18000c538  push    rdi
0x18000c539  push    r12
0x18000c53b  push    r13
0x18000c53d  push    r14
0x18000c53f  push    r15
0x18000c541  mov     rbp, rsp
0x18000c544  sub     rsp, 58h
0x18000c548  mov     r13d, edx
0x18000c54b  mov     [rbp+var_28], 0
0x18000c54f  lea     rdx, [rbp+var_24]
0x18000c553  mov     [rbp+Src], 0
0x18000c55b  mov     r15, r8
0x18000c55e  mov     [rbp+var_18], 0
0x18000c566  mov     [rbp+var_24], 0
0x18000c56d  call    EfspValidateClientCall
0x18000c572  mov     r14, [rbp+arg_40]
0x18000c579  xor     ecx, ecx
0x18000c57b  mov     rdi, [rbp+arg_38]
0x18000c582  mov     r12, [rbp+arg_30]
0x18000c586  mov     rsi, [rbp+arg_28]
0x18000c58a  test    eax, eax
0x18000c58c  jnz     loc_18000C6D6
0x18000c592  cmp     [rbp+var_24], ecx
0x18000c595  jz      loc_18000C6D6
0x18000c59b  mov     rbx, [rbp+arg_20]
0x18000c59f  test    rbx, rbx
0x18000c5a2  jnz     short loc_18000C5AE
0x18000c5a4  mov     ebx, 0C000000Dh
0x18000c5a9  jmp     loc_18000C6DB
0x18000c5ae  test    r12, r12
0x18000c5b1  jz      short loc_18000C5A4
0x18000c5b3  test    r14, r14
0x18000c5b6  jz      short loc_18000C5A4
0x18000c5b8  test    rsi, rsi
0x18000c5bb  jz      short loc_18000C5A4
0x18000c5bd  test    rdi, rdi
0x18000c5c0  jz      short loc_18000C5A4
0x18000c5c2  cmp     cs:EfsServerInitialized, cl
0x18000c5c8  mov     [r12], rcx
0x18000c5cc  mov     [r14], rcx
0x18000c5cf  mov     [rsi], ecx
0x18000c5d1  mov     [rdi], ecx
0x18000c5d3  jz      loc_18000C6CF
0x18000c5d9  call    cs:__imp_EfsDllDisabled
0x18000c5e0  nop     dword ptr [rax+rax+00h]
0x18000c5e5  test    al, al
0x18000c5e7  jnz     loc_18000C6CF
0x18000c5ed  lea     r8, [rbp+var_28]
0x18000c5f1  mov     edx, r13d
0x18000c5f4  mov     rcx, r15
0x18000c5f7  call    cs:__imp_EfsDllValidateEfsStream
0x18000c5fe  nop     dword ptr [rax+rax+00h]
0x18000c603  test    eax, eax
0x18000c605  jnz     short loc_18000C5A4
0x18000c607  cmp     [rbp+var_28], al
0x18000c60a  jz      short loc_18000C5A4
0x18000c60c  mov     rdx, [rbp+arg_18]
0x18000c610  lea     rax, [rbp+var_18]
0x18000c614  lea     r9, [rbp+Src]
0x18000c618  mov     [rsp+58h+var_38], rax
0x18000c61d  mov     r8, rbx
0x18000c620  mov     rcx, r15
0x18000c623  call    EfspDecryptFek
0x18000c628  mov     ebx, eax
0x18000c62a  test    eax, eax
0x18000c62c  js      loc_18000C6DB
0x18000c632  mov     rcx, [rbp+Src]
0x18000c636  test    rcx, rcx
0x18000c639  jz      short loc_18000C687
0x18000c63b  mov     r15d, [rcx]
0x18000c63e  add     r15d, 38h ; '8'
0x18000c642  mov     ecx, r15d; size
0x18000c645  mov     r13d, r15d
0x18000c648  call    MIDL_user_allocate
0x18000c64d  mov     [r12], rax
0x18000c651  test    rax, rax
0x18000c654  jnz     short loc_18000C65D
0x18000c656  mov     ebx, 0C0000017h
0x18000c65b  jmp     short loc_18000C6DB
0x18000c65d  mov     rdx, [rbp+Src]; Src
0x18000c661  mov     r8, r13; Size
0x18000c664  mov     rcx, rax; void *
0x18000c667  call    memcpy_0
0x18000c66c  mov     rcx, [rbp+Src]
0x18000c670  mov     [rsi], r15d
0x18000c673  call    cs:__imp_EfsDllFreeHeap
0x18000c67a  nop     dword ptr [rax+rax+00h]
0x18000c67f  mov     [rbp+Src], 0
0x18000c687  mov     rcx, [rbp+var_18]
0x18000c68b  test    rcx, rcx
0x18000c68e  jz      short loc_18000C6DB
0x18000c690  mov     r15d, [rcx]
0x18000c693  mov     ecx, r15d; size
0x18000c696  call    MIDL_user_allocate
0x18000c69b  mov     [r14], rax
0x18000c69e  test    rax, rax
0x18000c6a1  jz      short loc_18000C656
0x18000c6a3  mov     rdx, [rbp+var_18]; Src
0x18000c6a7  mov     r8d, r15d; Size
0x18000c6aa  mov     rcx, rax; void *
0x18000c6ad  call    memcpy_0
0x18000c6b2  mov     rcx, [rbp+var_18]
0x18000c6b6  mov     [rdi], r15d
0x18000c6b9  call    cs:__imp_EfsDllFreeHeap
0x18000c6c0  nop     dword ptr [rax+rax+00h]
0x18000c6c5  mov     [rbp+var_18], 0
0x18000c6cd  jmp     short loc_18000C6DB
0x18000c6cf  mov     ebx, 0C00000BBh
0x18000c6d4  jmp     short loc_18000C6DB
0x18000c6d6  mov     ebx, 0C0000022h
0x18000c6db  mov     rcx, [rbp+Src]
0x18000c6df  test    rcx, rcx
0x18000c6e2  jz      short loc_18000C6F0
0x18000c6e4  call    cs:__imp_EfsDllFreeHeap
0x18000c6eb  nop     dword ptr [rax+rax+00h]
0x18000c6f0  mov     rcx, [rbp+var_18]
0x18000c6f4  test    rcx, rcx
0x18000c6f7  jz      short loc_18000C705
0x18000c6f9  call    cs:__imp_EfsDllFreeHeap
0x18000c700  nop     dword ptr [rax+rax+00h]
0x18000c705  test    ebx, ebx
0x18000c707  jns     short loc_18000C758
0x18000c709  mov     rcx, [r12]; void *
0x18000c70d  test    rcx, rcx
0x18000c710  jz      short loc_18000C71F
0x18000c712  call    MIDL_user_free
0x18000c717  mov     qword ptr [r12], 0
0x18000c71f  test    rsi, rsi
0x18000c722  jz      short loc_18000C72A
0x18000c724  mov     dword ptr [rsi], 0
0x18000c72a  mov     rcx, [r14]; void *
0x18000c72d  test    rcx, rcx
0x18000c730  jz      short loc_18000C73E
0x18000c732  call    MIDL_user_free
0x18000c737  mov     qword ptr [r14], 0
0x18000c73e  test    rdi, rdi
0x18000c741  jz      short loc_18000C749
0x18000c743  mov     dword ptr [rdi], 0
0x18000c749  mov     ecx, ebx; exception
0x18000c74b  call    cs:__imp_RpcRaiseException
0x18000c752  nop     dword ptr [rax+rax+00h]
0x18000c757  int     3; Trap to Debugger
0x18000c758  mov     eax, ebx
0x18000c75a  add     rsp, 58h
0x18000c75e  pop     r15
0x18000c760  pop     r14
0x18000c762  pop     r13
0x18000c764  pop     r12
0x18000c766  pop     rdi
0x18000c767  pop     rsi
0x18000c768  pop     rbx
0x18000c769  pop     rbp
0x18000c76a  retn
```
