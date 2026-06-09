# EfsKRpcGenerateDirEfs

- ea: `0x18000bad0`
- end: `0x18000bc1a`
- name: `EfsKRpcGenerateDirEfs`
- size: `330`
- prototype: `void __fastcall(void *, __int64, __int64, __int64, _DWORD *, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180003510`
- `0x180003540`
- `0x18000bad0`
- `0x18000c0ac`
- `0x18000c244`
- `0x18000c386`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x18000bc04`
- `RPCRT4!RpcRaiseException` at `0x18000bc04`
- `EFSCORE!EfsDllDisabled` at `0x18000bb46`
- `EFSCORE!EfsDllDisabled` at `0x18000bb46`
- `EFSCORE!EfsDllFreeHeap` at `0x18000bbab`
- `EFSCORE!EfsDllFreeHeap` at `0x18000bbcb`
- `EFSCORE!EfsDllFreeHeap` at `0x18000bbd9`
- `EFSCORE!EfsDllFreeHeap` at `0x18000bbab`
- `EFSCORE!EfsDllFreeHeap` at `0x18000bbcb`
- `EFSCORE!EfsDllFreeHeap` at `0x18000bbd9`

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
0x18000bad0  mov     rax, rsp
0x18000bad3  push    rbx
0x18000bad4  push    rbp
0x18000bad5  push    rsi
0x18000bad6  push    rdi
0x18000bad7  push    r14
0x18000bad9  push    r15
0x18000badb  sub     rsp, 58h
0x18000badf  mov     r15d, edx
0x18000bae2  mov     qword ptr [rax-48h], 0
0x18000baea  xor     edi, edi
0x18000baec  lea     rdx, [rax-58h]
0x18000baf0  mov     [rax-50h], rdi
0x18000baf4  mov     rbx, r9
0x18000baf7  mov     [rax-58h], edi
0x18000bafa  mov     rbp, r8
0x18000bafd  call    EfspValidateClientCall
0x18000bb02  mov     rsi, [rsp+88h+arg_20]
0x18000bb0a  mov     r14, [rsp+88h+arg_28]
0x18000bb12  test    eax, eax
0x18000bb14  jnz     loc_18000BBBC
0x18000bb1a  cmp     [rsp+88h+var_58], edi
0x18000bb1e  jz      loc_18000BBBC
0x18000bb24  test    r14, r14
0x18000bb27  jnz     short loc_18000BB33
0x18000bb29  mov     ebx, 0C000000Dh
0x18000bb2e  jmp     loc_18000BBE3
0x18000bb33  test    rsi, rsi
0x18000bb36  jz      short loc_18000BB29
0x18000bb38  cmp     cs:EfsServerInitialized, dil
0x18000bb3f  mov     [r14], rdi
0x18000bb42  mov     [rsi], edi
0x18000bb44  jz      short loc_18000BBB5
0x18000bb46  call    cs:__imp_EfsDllDisabled
0x18000bb4c  test    al, al
0x18000bb4e  jnz     short loc_18000BBB5
0x18000bb50  lea     rax, [rsp+88h+Src]
0x18000bb55  mov     r9, rbx
0x18000bb58  mov     [rsp+88h+var_60], rax
0x18000bb5d  xor     r8d, r8d
0x18000bb60  lea     rax, [rsp+88h+var_48]
0x18000bb65  mov     edx, r15d
0x18000bb68  mov     rcx, rbp
0x18000bb6b  mov     [rsp+88h+var_68], rax
0x18000bb70  call    EfspGenerateKey
0x18000bb75  mov     rdi, [rsp+88h+Src]
0x18000bb7a  mov     ebx, eax
0x18000bb7c  test    eax, eax
0x18000bb7e  js      short loc_18000BBC1
0x18000bb80  mov     ebp, [rdi]
0x18000bb82  mov     ecx, ebp; size
0x18000bb84  call    MIDL_user_allocate
0x18000bb89  mov     [r14], rax
0x18000bb8c  test    rax, rax
0x18000bb8f  jnz     short loc_18000BB98
0x18000bb91  mov     ebx, 0C0000017h
0x18000bb96  jmp     short loc_18000BBC1
0x18000bb98  mov     r8, rbp; Size
0x18000bb9b  mov     rdx, rdi; Src
0x18000bb9e  mov     rcx, rax; void *
0x18000bba1  call    memcpy_0
0x18000bba6  mov     rcx, rdi
0x18000bba9  mov     [rsi], ebp
0x18000bbab  call    cs:__imp_EfsDllFreeHeap
0x18000bbb1  xor     edi, edi
0x18000bbb3  jmp     short loc_18000BBC1
0x18000bbb5  mov     ebx, 0C00000BBh
0x18000bbba  jmp     short loc_18000BBE3
0x18000bbbc  mov     ebx, 0C0000022h
0x18000bbc1  mov     rcx, [rsp+88h+var_48]
0x18000bbc6  test    rcx, rcx
0x18000bbc9  jz      short loc_18000BBD1
0x18000bbcb  call    cs:__imp_EfsDllFreeHeap
0x18000bbd1  test    rdi, rdi
0x18000bbd4  jz      short loc_18000BBDF
0x18000bbd6  mov     rcx, rdi
0x18000bbd9  call    cs:__imp_EfsDllFreeHeap
0x18000bbdf  test    ebx, ebx
0x18000bbe1  jns     short loc_18000BC0B
0x18000bbe3  mov     rcx, [r14]; void *
0x18000bbe6  test    rcx, rcx
0x18000bbe9  jz      short loc_18000BBF7
0x18000bbeb  call    MIDL_user_free
0x18000bbf0  mov     qword ptr [r14], 0
0x18000bbf7  test    rsi, rsi
0x18000bbfa  jz      short loc_18000BC02
0x18000bbfc  mov     dword ptr [rsi], 0
0x18000bc02  mov     ecx, ebx; exception
0x18000bc04  call    cs:__imp_RpcRaiseException
0x18000bc0a  int     3; Trap to Debugger
0x18000bc0b  mov     eax, ebx
0x18000bc0d  add     rsp, 58h
0x18000bc11  pop     r15
0x18000bc13  pop     r14
0x18000bc15  pop     rdi
0x18000bc16  pop     rsi
0x18000bc17  pop     rbp
0x18000bc18  pop     rbx
0x18000bc19  retn
```
