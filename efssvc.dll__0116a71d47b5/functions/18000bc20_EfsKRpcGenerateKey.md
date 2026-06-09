# EfsKRpcGenerateKey

- ea: `0x18000bc20`
- end: `0x18000bdf7`
- name: `EfsKRpcGenerateKey`
- size: `471`
- prototype: `void __fastcall(void *, __int64, __int64, __int64, __int64, _DWORD *, void **, _DWORD *, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x180003510`
- `0x180003540`
- `0x18000bc20`
- `0x18000c0ac`
- `0x18000c244`
- `0x18000c386`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x18000bdf0`
- `RPCRT4!RpcRaiseException` at `0x18000bdf0`
- `EFSCORE!EfsDllDisabled` at `0x18000bcbe`
- `EFSCORE!EfsDllDisabled` at `0x18000bcbe`
- `EFSCORE!EfsDllFreeHeap` at `0x18000bd2f`
- `EFSCORE!EfsDllFreeHeap` at `0x18000bd66`
- `EFSCORE!EfsDllFreeHeap` at `0x18000bda1`
- `EFSCORE!EfsDllFreeHeap` at `0x18000bdb1`
- `EFSCORE!EfsDllFreeHeap` at `0x18000bd2f`
- `EFSCORE!EfsDllFreeHeap` at `0x18000bd66`
- `EFSCORE!EfsDllFreeHeap` at `0x18000bda1`
- `EFSCORE!EfsDllFreeHeap` at `0x18000bdb1`

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
0x18000bc20  mov     [rsp-38h+arg_0], rbx
0x18000bc25  mov     [rsp-38h+arg_10], r8
0x18000bc2a  mov     [rsp-38h+arg_8], edx
0x18000bc2e  push    rbp
0x18000bc2f  push    rsi
0x18000bc30  push    rdi
0x18000bc31  push    r12
0x18000bc33  push    r13
0x18000bc35  push    r14
0x18000bc37  push    r15
0x18000bc39  mov     rbp, rsp
0x18000bc3c  sub     rsp, 50h
0x18000bc40  xor     esi, esi
0x18000bc42  lea     rdx, [rbp+var_20]
0x18000bc46  xor     edi, edi
0x18000bc48  mov     [rbp+Src], rsi
0x18000bc4c  mov     [rbp+var_18], rdi
0x18000bc50  mov     bl, r9b
0x18000bc53  mov     [rbp+var_20], esi
0x18000bc56  call    EfspValidateClientCall
0x18000bc5b  mov     r14, [rbp+arg_38]
0x18000bc5f  mov     r12, [rbp+arg_28]
0x18000bc63  mov     r13, [rbp+arg_40]
0x18000bc6a  mov     r15, [rbp+arg_30]
0x18000bc6e  test    eax, eax
0x18000bc70  jnz     loc_18000BD94
0x18000bc76  cmp     [rbp+var_20], esi
0x18000bc79  jz      loc_18000BD94
0x18000bc7f  test    r15, r15
0x18000bc82  jz      loc_18000BD8D
0x18000bc88  test    r13, r13
0x18000bc8b  jz      loc_18000BD8D
0x18000bc91  test    r12, r12
0x18000bc94  jz      loc_18000BD8D
0x18000bc9a  test    r14, r14
0x18000bc9d  jz      loc_18000BD8D
0x18000bca3  cmp     cs:EfsServerInitialized, sil
0x18000bcaa  mov     [r15], rsi
0x18000bcad  mov     [r13+0], rsi
0x18000bcb1  mov     [r12], esi
0x18000bcb5  mov     [r14], esi
0x18000bcb8  jz      loc_18000BD86
0x18000bcbe  call    cs:__imp_EfsDllDisabled
0x18000bcc4  test    al, al
0x18000bcc6  jnz     loc_18000BD86
0x18000bccc  mov     r9, [rbp+arg_20]
0x18000bcd0  lea     rax, [rbp+var_18]
0x18000bcd4  mov     edx, [rbp+arg_8]
0x18000bcd7  mov     r8b, bl
0x18000bcda  mov     rcx, [rbp+arg_10]
0x18000bcde  mov     [rsp+50h+var_28], rax
0x18000bce3  lea     rax, [rbp+Src]
0x18000bce7  mov     [rsp+50h+var_30], rax
0x18000bcec  call    EfspGenerateKey
0x18000bcf1  mov     rsi, [rbp+Src]
0x18000bcf5  mov     ebx, eax
0x18000bcf7  test    eax, eax
0x18000bcf9  js      short loc_18000BD14
0x18000bcfb  mov     edi, [rsi]
0x18000bcfd  add     edi, 38h ; '8'
0x18000bd00  mov     ecx, edi; size
0x18000bd02  call    MIDL_user_allocate
0x18000bd07  mov     [r15], rax
0x18000bd0a  test    rax, rax
0x18000bd0d  jnz     short loc_18000BD1A
0x18000bd0f  mov     ebx, 0C0000017h
0x18000bd14  mov     rdi, [rbp+var_18]
0x18000bd18  jmp     short loc_18000BD99
0x18000bd1a  mov     r8d, edi; Size
0x18000bd1d  mov     rdx, rsi; Src
0x18000bd20  mov     rcx, rax; void *
0x18000bd23  call    memcpy_0
0x18000bd28  mov     rcx, rsi
0x18000bd2b  mov     [r12], edi
0x18000bd2f  call    cs:__imp_EfsDllFreeHeap
0x18000bd35  mov     rdi, [rbp+var_18]
0x18000bd39  mov     esi, [rdi]
0x18000bd3b  mov     ecx, esi; size
0x18000bd3d  call    MIDL_user_allocate
0x18000bd42  mov     [r13+0], rax
0x18000bd46  test    rax, rax
0x18000bd49  jnz     short loc_18000BD52
0x18000bd4b  mov     ebx, 0C0000017h
0x18000bd50  jmp     short loc_18000BDA7
0x18000bd52  mov     r8, rsi; Size
0x18000bd55  mov     rdx, rdi; Src
0x18000bd58  mov     rcx, rax; void *
0x18000bd5b  call    memcpy_0
0x18000bd60  mov     rcx, rdi
0x18000bd63  mov     [r14], esi
0x18000bd66  call    cs:__imp_EfsDllFreeHeap
0x18000bd6c  mov     eax, ebx
0x18000bd6e  mov     rbx, [rsp+50h+arg_0]
0x18000bd76  add     rsp, 50h
0x18000bd7a  pop     r15
0x18000bd7c  pop     r14
0x18000bd7e  pop     r13
0x18000bd80  pop     r12
0x18000bd82  pop     rdi
0x18000bd83  pop     rsi
0x18000bd84  pop     rbp
0x18000bd85  retn
0x18000bd86  mov     ebx, 0C00000BBh
0x18000bd8b  jmp     short loc_18000BDBB
0x18000bd8d  mov     ebx, 0C000000Dh
0x18000bd92  jmp     short loc_18000BDBB
0x18000bd94  mov     ebx, 0C0000022h
0x18000bd99  test    rsi, rsi
0x18000bd9c  jz      short loc_18000BDA7
0x18000bd9e  mov     rcx, rsi
0x18000bda1  call    cs:__imp_EfsDllFreeHeap
0x18000bda7  xor     esi, esi
0x18000bda9  test    rdi, rdi
0x18000bdac  jz      short loc_18000BDB7
0x18000bdae  mov     rcx, rdi
0x18000bdb1  call    cs:__imp_EfsDllFreeHeap
0x18000bdb7  test    ebx, ebx
0x18000bdb9  jns     short loc_18000BD6C
0x18000bdbb  mov     rcx, [r15]; void *
0x18000bdbe  test    rcx, rcx
0x18000bdc1  jz      short loc_18000BDCB
0x18000bdc3  call    MIDL_user_free
0x18000bdc8  mov     [r15], rsi
0x18000bdcb  test    r12, r12
0x18000bdce  jz      short loc_18000BDD4
0x18000bdd0  mov     [r12], esi
0x18000bdd4  mov     rcx, [r13+0]; void *
0x18000bdd8  test    rcx, rcx
0x18000bddb  jz      short loc_18000BDE6
0x18000bddd  call    MIDL_user_free
0x18000bde2  mov     [r13+0], rsi
0x18000bde6  test    r14, r14
0x18000bde9  jz      short loc_18000BDEE
0x18000bdeb  mov     [r14], esi
0x18000bdee  mov     ecx, ebx; exception
0x18000bdf0  call    cs:__imp_RpcRaiseException
```
