# std::vector<web::json::value,std::allocator<web::json::value>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x1400066e0`
- end: `0x140006794`
- name: `??1_Reallocation_guard@?$vector@Vvalue@json@web@@V?$allocator@Vvalue@json@web@@@std@@@std@@QEAA@XZ`
- size: `180`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x1400088d0`
- `0x14003be40`

## callees

- `0x140003244`
- `0x1400066e0`
- `0x14003e010`

## pseudocode

```c
void __fastcall std::vector<web::json::value>::_Reallocation_guard::~_Reallocation_guard(_QWORD *a1)
{
  _QWORD *v2; // rbx
  _QWORD *i; // rsi
  void *v4; // rcx
  _BYTE *v5; // rax

  if ( a1[1] )
  {
    v2 = (_QWORD *)a1[3];
    for ( i = (_QWORD *)a1[4]; v2 != i; ++v2 )
    {
      if ( *v2 )
        (*(void (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v2 + 192LL))(*v2, 1);
    }
    v4 = (void *)a1[1];
    if ( (unsigned __int64)(8LL * a1[2]) < 0x1000 )
    {
      operator delete(v4);
    }
    else
    {
      v5 = (_BYTE *)*((_QWORD *)v4 - 1);
      if ( (unsigned __int64)((_BYTE *)v4 - v5 - 8) > 0x1F )
        __fastfail(5u);
      operator delete(v5);
    }
  }
}

```

## disassembly

```asm
0x1400066e0  push    rdi
0x1400066e2  sub     rsp, 20h
0x1400066e6  cmp     qword ptr [rcx+8], 0
0x1400066eb  mov     rdi, rcx
0x1400066ee  jz      loc_14000678E
0x1400066f4  mov     [rsp+28h+arg_0], rbx
0x1400066f9  mov     rbx, [rcx+18h]
0x1400066fd  mov     [rsp+28h+arg_8], rsi
0x140006702  mov     rsi, [rcx+20h]
0x140006706  cmp     rbx, rsi
0x140006709  jz      short loc_140006735
0x14000670b  nop     dword ptr [rax+rax+00h]
0x140006710  mov     rcx, [rbx]
0x140006713  test    rcx, rcx
0x140006716  jz      short loc_14000672C
0x140006718  mov     rax, [rcx]
0x14000671b  mov     edx, 1
0x140006720  mov     rax, [rax+0C0h]
0x140006727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000672c  add     rbx, 8
0x140006730  cmp     rbx, rsi
0x140006733  jnz     short loc_140006710
0x140006735  mov     rax, [rdi+10h]
0x140006739  mov     rcx, [rdi+8]; Block
0x14000673d  mov     rsi, [rsp+28h+arg_8]
0x140006742  mov     rbx, [rsp+28h+arg_0]
0x140006747  lea     rdx, ds:0[rax*8]
0x14000674f  cmp     rdx, 1000h
0x140006756  jb      short loc_140006781
0x140006758  mov     rax, [rcx-8]
0x14000675c  sub     rcx, rax
0x14000675f  sub     rcx, 8
0x140006763  cmp     rcx, 1Fh
0x140006767  ja      short loc_14000677A
0x140006769  add     rdx, 27h ; '''
0x14000676d  mov     rcx, rax; Block
0x140006770  add     rsp, 20h
0x140006774  pop     rdi
0x140006775  jmp     ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000677a  mov     ecx, 5
0x14000677f  int     29h; Win8: RtlFailFast(ecx)
0x140006781  mov     rax, rcx
0x140006784  add     rsp, 20h
0x140006788  pop     rdi
0x140006789  jmp     ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14000678e  add     rsp, 20h
0x140006792  pop     rdi
0x140006793  retn
```
