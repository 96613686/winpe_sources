# CDocWrapBase<DocTraitsACP>::QueryService(_GUID const &,_GUID const &,void * *)

- ea: `0x18000a330`
- end: `0x18000a3d3`
- name: `?QueryService@?$CDocWrapBase@VDocTraitsACP@@@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `163`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x18000a300`
- `0x18000a330`
- `0x180014010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CDocWrapBase<DocTraitsACP>::QueryService(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  unsigned int v7; // ebx
  __int64 v9; // [rsp+40h] [rbp+8h] BYREF

  *a4 = 0;
  v9 = 0;
  if ( (unsigned int)SEHWrap_IUnknown<ITextStoreACP>::QueryInterface(a1 + 88, &IID_IServiceProvider, &v9) || !v9 )
  {
    if ( v9 )
      (*(void (**)(void))(*(_QWORD *)v9 + 16LL))();
    return 2147500037LL;
  }
  else
  {
    v7 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD *))(*(_QWORD *)v9 + 24LL))(v9, a2, a3, a4);
    if ( v9 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    return v7;
  }
}

```

## disassembly

```asm
0x18000a330  mov     rax, rsp
0x18000a333  mov     [rax+10h], rbx
0x18000a337  mov     [rax+18h], rsi
0x18000a33b  push    rdi
0x18000a33c  sub     rsp, 30h
0x18000a340  mov     rbx, r9
0x18000a343  mov     rdi, r8
0x18000a346  mov     rsi, rdx
0x18000a349  mov     qword ptr [r9], 0
0x18000a350  mov     qword ptr [rax+8], 0
0x18000a358  add     rcx, 58h ; 'X'
0x18000a35c  lea     r8, [rax+8]
0x18000a360  lea     rdx, IID_IServiceProvider
0x18000a367  call    ?QueryInterface@?$SEHWrap_IUnknown@UITextStoreACP@@@@QEAAJAEBU_GUID@@PEAPEAX@Z; SEHWrap_IUnknown<ITextStoreACP>::QueryInterface(_GUID const &,void * *)
0x18000a36c  mov     rcx, [rsp+38h+arg_0]
0x18000a371  test    eax, eax
0x18000a373  jnz     short loc_18000A3AC
0x18000a375  test    rcx, rcx
0x18000a378  jz      short loc_18000A3AC
0x18000a37a  mov     rax, [rcx]
0x18000a37d  mov     r9, rbx
0x18000a380  mov     r8, rdi
0x18000a383  mov     rdx, rsi
0x18000a386  mov     rax, [rax+18h]
0x18000a38a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a38f  mov     ebx, eax
0x18000a391  mov     rcx, [rsp+38h+arg_0]
0x18000a396  test    rcx, rcx
0x18000a399  jz      short loc_18000A3A8
0x18000a39b  mov     rdx, [rcx]
0x18000a39e  mov     rax, [rdx+10h]
0x18000a3a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3a7  nop
0x18000a3a8  mov     eax, ebx
0x18000a3aa  jmp     short loc_18000A3C3
0x18000a3ac  test    rcx, rcx
0x18000a3af  jz      short loc_18000A3BE
0x18000a3b1  mov     rax, [rcx]
0x18000a3b4  mov     rax, [rax+10h]
0x18000a3b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3bd  nop
0x18000a3be  mov     eax, 80004005h
0x18000a3c3  mov     rbx, [rsp+38h+arg_8]
0x18000a3c8  mov     rsi, [rsp+38h+arg_10]
0x18000a3cd  add     rsp, 30h
0x18000a3d1  pop     rdi
0x18000a3d2  retn
```
