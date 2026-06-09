# std::vector<Microsoft::WRL::ComPtr<IMVKey>,std::allocator<Microsoft::WRL::ComPtr<IMVKey>>>::~vector<Microsoft::WRL::ComPtr<IMVKey>,std::allocator<Microsoft::WRL::ComPtr<IMVKey>>>(void)

- ea: `0x180015fa0`
- end: `0x180016015`
- name: `??1?$vector@V?$ComPtr@UIMVKey@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIMVKey@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ`
- size: `117`
- prototype: `void __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180017d04`
- `0x18003cba5`

## callees

- `0x180015fa0`
- `0x18003f010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180015fe8`
- `msvcrt!??3@YAXPEAX@Z` at `0x180015fe8`

## pseudocode

```c
void __fastcall std::vector<Microsoft::WRL::ComPtr<IMVKey>>::~vector<Microsoft::WRL::ComPtr<IMVKey>>(__int64 a1)
{
  __int64 *v2; // rbx
  __int64 *v3; // rsi
  __int64 v4; // rcx

  v2 = *(__int64 **)a1;
  if ( *(_QWORD *)a1 )
  {
    v3 = *(__int64 **)(a1 + 8);
    while ( v2 != v3 )
    {
      v4 = *v2;
      if ( *v2 )
      {
        *v2 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
      }
      ++v2;
    }
    operator delete(*(void **)a1);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x180015fa0  mov     [rsp+arg_0], rbx
0x180015fa5  mov     [rsp+arg_8], rsi
0x180015faa  push    rdi
0x180015fab  sub     rsp, 20h
0x180015faf  mov     rdi, rcx
0x180015fb2  mov     rbx, [rcx]
0x180015fb5  test    rbx, rbx
0x180015fb8  jz      short loc_180016005
0x180015fba  mov     rsi, [rcx+8]
0x180015fbe  jmp     short loc_180015FE0
0x180015fc0  mov     rcx, [rbx]
0x180015fc3  test    rcx, rcx
0x180015fc6  jz      short loc_180015FDC
0x180015fc8  mov     qword ptr [rbx], 0
0x180015fcf  mov     rax, [rcx]
0x180015fd2  mov     rax, [rax+10h]
0x180015fd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fdb  nop
0x180015fdc  add     rbx, 8
0x180015fe0  cmp     rbx, rsi
0x180015fe3  jnz     short loc_180015FC0
0x180015fe5  mov     rcx, [rdi]
0x180015fe8  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180015fee  mov     qword ptr [rdi], 0
0x180015ff5  mov     qword ptr [rdi+8], 0
0x180015ffd  mov     qword ptr [rdi+10h], 0
0x180016005  mov     rbx, [rsp+28h+arg_0]
0x18001600a  mov     rsi, [rsp+28h+arg_8]
0x18001600f  add     rsp, 20h
0x180016013  pop     rdi
0x180016014  retn
```
