# EfsKRpcGenerateDirEfs

- ea: `0x18000c7c0`
- end: `0x18000c929`
- name: `EfsKRpcGenerateDirEfs`
- size: `361`
- prototype: `void __fastcall(void *, __int64, __int64, __int64, _DWORD *, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x1800036a0`
- `0x1800036e0`
- `0x18000c7c0`
- `0x18000ce5c`
- `0x18000d03c`
- `0x18000d186`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x18000c90c`
- `RPCRT4!RpcRaiseException` at `0x18000c90c`
- `EFSCORE!EfsDllDisabled` at `0x18000c836`
- `EFSCORE!EfsDllDisabled` at `0x18000c836`
- `EFSCORE!EfsDllFreeHeap` at `0x18000c8a1`
- `EFSCORE!EfsDllFreeHeap` at `0x18000c8c7`
- `EFSCORE!EfsDllFreeHeap` at `0x18000c8db`
- `EFSCORE!EfsDllFreeHeap` at `0x18000c8a1`
- `EFSCORE!EfsDllFreeHeap` at `0x18000c8c7`
- `EFSCORE!EfsDllFreeHeap` at `0x18000c8db`

## pseudocode

```c
void __fastcall EfsKRpcGenerateDirEfs(void *a1, __int64 a2, __int64 a3, __int64 a4, _DWORD *a5, void **a6)
{
  EfspValidateClientCall(a1);
  if ( *a6 )
  {
    MIDL_user_free(*a6);
    *a6 = 0;
  }
  if ( a5 )
    *a5 = 0;
  RpcRaiseException(-1073741790);
}

```

## disassembly

```asm
0x18000c7c0  mov     rax, rsp
0x18000c7c3  push    rbx
0x18000c7c4  push    rbp
0x18000c7c5  push    rsi
0x18000c7c6  push    rdi
0x18000c7c7  push    r14
0x18000c7c9  push    r15
0x18000c7cb  sub     rsp, 58h
0x18000c7cf  mov     r15d, edx
0x18000c7d2  mov     qword ptr [rax-48h], 0
0x18000c7da  xor     edi, edi
0x18000c7dc  lea     rdx, [rax-58h]
0x18000c7e0  mov     [rax-50h], rdi
0x18000c7e4  mov     rbx, r9
0x18000c7e7  mov     [rax-58h], edi
0x18000c7ea  mov     rbp, r8
0x18000c7ed  call    EfspValidateClientCall
0x18000c7f2  mov     rsi, [rsp+88h+arg_20]
0x18000c7fa  mov     r14, [rsp+88h+arg_28]
0x18000c802  test    eax, eax
0x18000c804  jnz     loc_18000C8B8
0x18000c80a  cmp     [rsp+88h+var_58], edi
0x18000c80e  jz      loc_18000C8B8
0x18000c814  test    r14, r14
0x18000c817  jnz     short loc_18000C823
0x18000c819  mov     ebx, 0C000000Dh
0x18000c81e  jmp     loc_18000C8EB
0x18000c823  test    rsi, rsi
0x18000c826  jz      short loc_18000C819
0x18000c828  cmp     cs:EfsServerInitialized, dil
0x18000c82f  mov     [r14], rdi
0x18000c832  mov     [rsi], edi
0x18000c834  jz      short loc_18000C8B1
0x18000c836  call    cs:__imp_EfsDllDisabled
0x18000c83d  nop     dword ptr [rax+rax+00h]
0x18000c842  test    al, al
0x18000c844  jnz     short loc_18000C8B1
0x18000c846  lea     rax, [rsp+88h+Src]
0x18000c84b  mov     r9, rbx
0x18000c84e  mov     [rsp+88h+var_60], rax
0x18000c853  xor     r8d, r8d
0x18000c856  lea     rax, [rsp+88h+var_48]
0x18000c85b  mov     edx, r15d
0x18000c85e  mov     rcx, rbp
0x18000c861  mov     [rsp+88h+var_68], rax
0x18000c866  call    EfspGenerateKey
0x18000c86b  mov     rdi, [rsp+88h+Src]
0x18000c870  mov     ebx, eax
0x18000c872  test    eax, eax
0x18000c874  js      short loc_18000C8BD
0x18000c876  mov     ebp, [rdi]
0x18000c878  mov     ecx, ebp; size
0x18000c87a  call    MIDL_user_allocate
0x18000c87f  mov     [r14], rax
0x18000c882  test    rax, rax
0x18000c885  jnz     short loc_18000C88E
0x18000c887  mov     ebx, 0C0000017h
0x18000c88c  jmp     short loc_18000C8BD
0x18000c88e  mov     r8, rbp; Size
0x18000c891  mov     rdx, rdi; Src
0x18000c894  mov     rcx, rax; void *
0x18000c897  call    memcpy_0
0x18000c89c  mov     rcx, rdi
0x18000c89f  mov     [rsi], ebp
0x18000c8a1  call    cs:__imp_EfsDllFreeHeap
0x18000c8a8  nop     dword ptr [rax+rax+00h]
0x18000c8ad  xor     edi, edi
0x18000c8af  jmp     short loc_18000C8BD
0x18000c8b1  mov     ebx, 0C00000BBh
0x18000c8b6  jmp     short loc_18000C8EB
0x18000c8b8  mov     ebx, 0C0000022h
0x18000c8bd  mov     rcx, [rsp+88h+var_48]
0x18000c8c2  test    rcx, rcx
0x18000c8c5  jz      short loc_18000C8D3
0x18000c8c7  call    cs:__imp_EfsDllFreeHeap
0x18000c8ce  nop     dword ptr [rax+rax+00h]
0x18000c8d3  test    rdi, rdi
0x18000c8d6  jz      short loc_18000C8E7
0x18000c8d8  mov     rcx, rdi
0x18000c8db  call    cs:__imp_EfsDllFreeHeap
0x18000c8e2  nop     dword ptr [rax+rax+00h]
0x18000c8e7  test    ebx, ebx
0x18000c8e9  jns     short loc_18000C919
0x18000c8eb  mov     rcx, [r14]; void *
0x18000c8ee  test    rcx, rcx
0x18000c8f1  jz      short loc_18000C8FF
0x18000c8f3  call    MIDL_user_free
0x18000c8f8  mov     qword ptr [r14], 0
0x18000c8ff  test    rsi, rsi
0x18000c902  jz      short loc_18000C90A
0x18000c904  mov     dword ptr [rsi], 0
0x18000c90a  mov     ecx, ebx; exception
0x18000c90c  call    cs:__imp_RpcRaiseException
0x18000c913  nop     dword ptr [rax+rax+00h]
0x18000c918  int     3; Trap to Debugger
0x18000c919  mov     eax, ebx
0x18000c91b  add     rsp, 58h
0x18000c91f  pop     r15
0x18000c921  pop     r14
0x18000c923  pop     rdi
0x18000c924  pop     rsi
0x18000c925  pop     rbp
0x18000c926  pop     rbx
0x18000c927  retn
```
