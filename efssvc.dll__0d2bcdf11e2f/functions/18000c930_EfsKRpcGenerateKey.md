# EfsKRpcGenerateKey

- ea: `0x18000c930`
- end: `0x18000cb2f`
- name: `EfsKRpcGenerateKey`
- size: `511`
- prototype: `void __fastcall(void *, __int64, __int64, __int64, __int64, _DWORD *, void **, _DWORD *, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x1800036a0`
- `0x1800036e0`
- `0x18000c930`
- `0x18000ce5c`
- `0x18000d03c`
- `0x18000d186`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x18000cb22`
- `RPCRT4!RpcRaiseException` at `0x18000cb22`
- `EFSCORE!EfsDllDisabled` at `0x18000c9ce`
- `EFSCORE!EfsDllDisabled` at `0x18000c9ce`
- `EFSCORE!EfsDllFreeHeap` at `0x18000ca48`
- `EFSCORE!EfsDllFreeHeap` at `0x18000ca85`
- `EFSCORE!EfsDllFreeHeap` at `0x18000cac7`
- `EFSCORE!EfsDllFreeHeap` at `0x18000cadd`
- `EFSCORE!EfsDllFreeHeap` at `0x18000ca48`
- `EFSCORE!EfsDllFreeHeap` at `0x18000ca85`
- `EFSCORE!EfsDllFreeHeap` at `0x18000cac7`
- `EFSCORE!EfsDllFreeHeap` at `0x18000cadd`

## pseudocode

```c
void __fastcall EfsKRpcGenerateKey(
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
0x18000c930  mov     [rsp-38h+arg_0], rbx
0x18000c935  mov     [rsp-38h+arg_10], r8
0x18000c93a  mov     [rsp-38h+arg_8], edx
0x18000c93e  push    rbp
0x18000c93f  push    rsi
0x18000c940  push    rdi
0x18000c941  push    r12
0x18000c943  push    r13
0x18000c945  push    r14
0x18000c947  push    r15
0x18000c949  mov     rbp, rsp
0x18000c94c  sub     rsp, 50h
0x18000c950  xor     esi, esi
0x18000c952  lea     rdx, [rbp+var_20]
0x18000c956  xor     edi, edi
0x18000c958  mov     [rbp+Src], rsi
0x18000c95c  mov     [rbp+var_18], rdi
0x18000c960  mov     bl, r9b
0x18000c963  mov     [rbp+var_20], esi
0x18000c966  call    EfspValidateClientCall
0x18000c96b  mov     r14, [rbp+arg_38]
0x18000c96f  mov     r12, [rbp+arg_28]
0x18000c973  mov     r13, [rbp+arg_40]
0x18000c97a  mov     r15, [rbp+arg_30]
0x18000c97e  test    eax, eax
0x18000c980  jnz     loc_18000CABA
0x18000c986  cmp     [rbp+var_20], esi
0x18000c989  jz      loc_18000CABA
0x18000c98f  test    r15, r15
0x18000c992  jz      loc_18000CAB3
0x18000c998  test    r13, r13
0x18000c99b  jz      loc_18000CAB3
0x18000c9a1  test    r12, r12
0x18000c9a4  jz      loc_18000CAB3
0x18000c9aa  test    r14, r14
0x18000c9ad  jz      loc_18000CAB3
0x18000c9b3  cmp     cs:EfsServerInitialized, sil
0x18000c9ba  mov     [r15], rsi
0x18000c9bd  mov     [r13+0], rsi
0x18000c9c1  mov     [r12], esi
0x18000c9c5  mov     [r14], esi
0x18000c9c8  jz      loc_18000CAAC
0x18000c9ce  call    cs:__imp_EfsDllDisabled
0x18000c9d5  nop     dword ptr [rax+rax+00h]
0x18000c9da  test    al, al
0x18000c9dc  jnz     loc_18000CAAC
0x18000c9e2  mov     r9, [rbp+arg_20]
0x18000c9e6  lea     rax, [rbp+var_18]
0x18000c9ea  mov     edx, [rbp+arg_8]
0x18000c9ed  mov     r8b, bl
0x18000c9f0  mov     rcx, [rbp+arg_10]
0x18000c9f4  mov     [rsp+50h+var_28], rax
0x18000c9f9  lea     rax, [rbp+Src]
0x18000c9fd  mov     [rsp+50h+var_30], rax
0x18000ca02  call    EfspGenerateKey
0x18000ca07  mov     rsi, [rbp+Src]
0x18000ca0b  mov     ebx, eax
0x18000ca0d  test    eax, eax
0x18000ca0f  js      short loc_18000CA2A
0x18000ca11  mov     edi, [rsi]
0x18000ca13  add     edi, 38h ; '8'
0x18000ca16  mov     ecx, edi; size
0x18000ca18  call    MIDL_user_allocate
0x18000ca1d  mov     [r15], rax
0x18000ca20  test    rax, rax
0x18000ca23  jnz     short loc_18000CA33
0x18000ca25  mov     ebx, 0C0000017h
0x18000ca2a  mov     rdi, [rbp+var_18]
0x18000ca2e  jmp     loc_18000CABF
0x18000ca33  mov     r8d, edi; Size
0x18000ca36  mov     rdx, rsi; Src
0x18000ca39  mov     rcx, rax; void *
0x18000ca3c  call    memcpy_0
0x18000ca41  mov     rcx, rsi
0x18000ca44  mov     [r12], edi
0x18000ca48  call    cs:__imp_EfsDllFreeHeap
0x18000ca4f  nop     dword ptr [rax+rax+00h]
0x18000ca54  mov     rdi, [rbp+var_18]
0x18000ca58  mov     esi, [rdi]
0x18000ca5a  mov     ecx, esi; size
0x18000ca5c  call    MIDL_user_allocate
0x18000ca61  mov     [r13+0], rax
0x18000ca65  test    rax, rax
0x18000ca68  jnz     short loc_18000CA71
0x18000ca6a  mov     ebx, 0C0000017h
0x18000ca6f  jmp     short loc_18000CAD3
0x18000ca71  mov     r8, rsi; Size
0x18000ca74  mov     rdx, rdi; Src
0x18000ca77  mov     rcx, rax; void *
0x18000ca7a  call    memcpy_0
0x18000ca7f  mov     rcx, rdi
0x18000ca82  mov     [r14], esi
0x18000ca85  call    cs:__imp_EfsDllFreeHeap
0x18000ca8c  nop     dword ptr [rax+rax+00h]
0x18000ca91  mov     eax, ebx
0x18000ca93  mov     rbx, [rsp+50h+arg_0]
0x18000ca9b  add     rsp, 50h
0x18000ca9f  pop     r15
0x18000caa1  pop     r14
0x18000caa3  pop     r13
0x18000caa5  pop     r12
0x18000caa7  pop     rdi
0x18000caa8  pop     rsi
0x18000caa9  pop     rbp
0x18000caaa  retn
0x18000caac  mov     ebx, 0C00000BBh
0x18000cab1  jmp     short loc_18000CAED
0x18000cab3  mov     ebx, 0C000000Dh
0x18000cab8  jmp     short loc_18000CAED
0x18000caba  mov     ebx, 0C0000022h
0x18000cabf  test    rsi, rsi
0x18000cac2  jz      short loc_18000CAD3
0x18000cac4  mov     rcx, rsi
0x18000cac7  call    cs:__imp_EfsDllFreeHeap
0x18000cace  nop     dword ptr [rax+rax+00h]
0x18000cad3  xor     esi, esi
0x18000cad5  test    rdi, rdi
0x18000cad8  jz      short loc_18000CAE9
0x18000cada  mov     rcx, rdi
0x18000cadd  call    cs:__imp_EfsDllFreeHeap
0x18000cae4  nop     dword ptr [rax+rax+00h]
0x18000cae9  test    ebx, ebx
0x18000caeb  jns     short loc_18000CA91
0x18000caed  mov     rcx, [r15]; void *
0x18000caf0  test    rcx, rcx
0x18000caf3  jz      short loc_18000CAFD
0x18000caf5  call    MIDL_user_free
0x18000cafa  mov     [r15], rsi
0x18000cafd  test    r12, r12
0x18000cb00  jz      short loc_18000CB06
0x18000cb02  mov     [r12], esi
0x18000cb06  mov     rcx, [r13+0]; void *
0x18000cb0a  test    rcx, rcx
0x18000cb0d  jz      short loc_18000CB18
0x18000cb0f  call    MIDL_user_free
0x18000cb14  mov     [r13+0], rsi
0x18000cb18  test    r14, r14
0x18000cb1b  jz      short loc_18000CB20
0x18000cb1d  mov     [r14], esi
0x18000cb20  mov     ecx, ebx; exception
0x18000cb22  call    cs:__imp_RpcRaiseException
0x18000cb29  nop     dword ptr [rax+rax+00h]
0x18000cb2e  int     3; Trap to Debugger
```
