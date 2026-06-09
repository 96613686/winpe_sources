# std::vector<Microsoft::WRL::ComPtr<IMVHandler>,std::allocator<Microsoft::WRL::ComPtr<IMVHandler>>>::~vector<Microsoft::WRL::ComPtr<IMVHandler>,std::allocator<Microsoft::WRL::ComPtr<IMVHandler>>>(void)

- ea: `0x180010a5c`
- end: `0x180010ad1`
- name: `??1?$vector@V?$ComPtr@UIMVHandler@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIMVHandler@@@WRL@Microsoft@@@std@@@std@@QEAA@XZ`
- size: `117`
- prototype: `void __fastcall(__int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180010d34`
- `0x180015740`
- `0x18004443e`
- `0x180044b11`

## callees

- `0x180010a5c`
- `0x180047010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180010aa4`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010aa4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::vector<Microsoft::WRL::ComPtr<IMVHandler>>::~vector<Microsoft::WRL::ComPtr<IMVHandler>>(
        __int64 a1)
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
0x180010a5c  mov     [rsp+arg_0], rbx
0x180010a61  mov     [rsp+arg_8], rsi
0x180010a66  push    rdi
0x180010a67  sub     rsp, 20h
0x180010a6b  mov     rdi, rcx
0x180010a6e  mov     rbx, [rcx]
0x180010a71  test    rbx, rbx
0x180010a74  jz      short loc_180010AC1
0x180010a76  mov     rsi, [rcx+8]
0x180010a7a  jmp     short loc_180010A9C
0x180010a7c  mov     rcx, [rbx]
0x180010a7f  test    rcx, rcx
0x180010a82  jz      short loc_180010A98
0x180010a84  mov     qword ptr [rbx], 0
0x180010a8b  mov     rax, [rcx]
0x180010a8e  mov     rax, [rax+10h]
0x180010a92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a97  nop
0x180010a98  add     rbx, 8
0x180010a9c  cmp     rbx, rsi
0x180010a9f  jnz     short loc_180010A7C
0x180010aa1  mov     rcx, [rdi]
0x180010aa4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180010aaa  mov     qword ptr [rdi], 0
0x180010ab1  mov     qword ptr [rdi+8], 0
0x180010ab9  mov     qword ptr [rdi+10h], 0
0x180010ac1  mov     rbx, [rsp+28h+arg_0]
0x180010ac6  mov     rsi, [rsp+28h+arg_8]
0x180010acb  add     rsp, 20h
0x180010acf  pop     rdi
0x180010ad0  retn
```
