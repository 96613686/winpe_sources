# std::vector<web::json::value,std::allocator<web::json::value>>::_Tidy(void)

- ea: `0x140006f70`
- end: `0x140007021`
- name: `?_Tidy@?$vector@Vvalue@json@web@@V?$allocator@Vvalue@json@web@@@std@@@std@@AEAAXXZ`
- size: `177`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x1400065a0`
- `0x140006ad0`

## callees

- `0x140003244`
- `0x140006f70`
- `0x14003e010`

## pseudocode

```c
void __fastcall std::vector<web::json::value>::_Tidy(__int64 a1)
{
  char *v1; // rbx
  char *i; // rsi
  char *v4; // rcx
  char *v5; // rax

  v1 = *(char **)a1;
  if ( *(_QWORD *)a1 )
  {
    for ( i = *(char **)(a1 + 8); v1 != i; v1 += 8 )
    {
      if ( *(_QWORD *)v1 )
        (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v1 + 192LL))(*(_QWORD *)v1, 1);
    }
    v4 = *(char **)a1;
    if ( (unsigned __int64)(8 * ((__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) >> 3)) < 0x1000 )
    {
      v5 = *(char **)a1;
    }
    else
    {
      v5 = (char *)*((_QWORD *)v4 - 1);
      if ( (unsigned __int64)(v4 - v5 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v5);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x140006f70  mov     [rsp+arg_8], rbx
0x140006f75  push    rdi
0x140006f76  sub     rsp, 20h
0x140006f7a  mov     rbx, [rcx]
0x140006f7d  mov     rdi, rcx
0x140006f80  test    rbx, rbx
0x140006f83  jz      loc_140007016
0x140006f89  mov     [rsp+28h+arg_0], rsi
0x140006f8e  mov     rsi, [rcx+8]
0x140006f92  cmp     rbx, rsi
0x140006f95  jz      short loc_140006FBC
0x140006f97  mov     rcx, [rbx]
0x140006f9a  test    rcx, rcx
0x140006f9d  jz      short loc_140006FB3
0x140006f9f  mov     rax, [rcx]
0x140006fa2  mov     edx, 1
0x140006fa7  mov     rax, [rax+0C0h]
0x140006fae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006fb3  add     rbx, 8
0x140006fb7  cmp     rbx, rsi
0x140006fba  jnz     short loc_140006F97
0x140006fbc  mov     rcx, [rdi]
0x140006fbf  mov     rax, [rdi+10h]
0x140006fc3  mov     rsi, [rsp+28h+arg_0]
0x140006fc8  sub     rax, rcx
0x140006fcb  sar     rax, 3
0x140006fcf  lea     rdx, ds:0[rax*8]
0x140006fd7  cmp     rdx, 1000h
0x140006fde  jb      short loc_140006FFE
0x140006fe0  mov     rax, [rcx-8]
0x140006fe4  sub     rcx, rax
0x140006fe7  sub     rcx, 8
0x140006feb  cmp     rcx, 1Fh
0x140006fef  ja      short loc_140006FF7
0x140006ff1  add     rdx, 27h ; '''
0x140006ff5  jmp     short loc_140007001
0x140006ff7  mov     ecx, 5
0x140006ffc  int     29h; Win8: RtlFailFast(ecx)
0x140006ffe  mov     rax, rcx
0x140007001  mov     rcx, rax; Block
0x140007004  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140007009  xor     eax, eax
0x14000700b  mov     [rdi], rax
0x14000700e  mov     [rdi+8], rax
0x140007012  mov     [rdi+10h], rax
0x140007016  mov     rbx, [rsp+28h+arg_8]
0x14000701b  add     rsp, 20h
0x14000701f  pop     rdi
0x140007020  retn
```
