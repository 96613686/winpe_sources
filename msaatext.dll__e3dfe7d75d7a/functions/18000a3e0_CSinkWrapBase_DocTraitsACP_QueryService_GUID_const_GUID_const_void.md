# CSinkWrapBase<DocTraitsACP>::QueryService(_GUID const &,_GUID const &,void * *)

- ea: `0x18000a3e0`
- end: `0x18000a4bc`
- name: `?QueryService@?$CSinkWrapBase@VDocTraitsACP@@@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `220`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18000a3e0`
- `0x180014010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSinkWrapBase<DocTraitsACP>::QueryService(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 i; // rbx
  unsigned int (__fastcall ***v8)(_QWORD, GUID *, _QWORD *); // rcx
  unsigned int v9; // ebx
  _QWORD v11[7]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v12; // [rsp+70h] [rbp+8h] BYREF

  v11[0] = 0;
  for ( i = *(_QWORD *)(*(_QWORD *)(a1 + 16) + 56LL); i; i = *(_QWORD *)(i + 8) )
  {
    v8 = *(unsigned int (__fastcall ****)(_QWORD, GUID *, _QWORD *))(i + 24);
    if ( v8 )
    {
      if ( !(**v8)(v8, &GUID_aa80e901_2021_11d2_93e0_0060b067b86e, v11) )
        break;
    }
  }
  if ( !v11[0] )
    return 2147500037LL;
  v12 = 0;
  if ( (**(unsigned int (__fastcall ***)(_QWORD, GUID *, __int64 *))v11[0])(v11[0], &IID_IServiceProvider, &v12) || !v12 )
  {
    if ( v12 )
      (*(void (**)(void))(*(_QWORD *)v12 + 16LL))();
    return 2147500037LL;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)v12 + 24LL))(v12, a2, a3, a4);
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  return v9;
}

```

## disassembly

```asm
0x18000a3e0  push    rbx
0x18000a3e2  push    rbp
0x18000a3e3  push    rsi
0x18000a3e4  push    rdi
0x18000a3e5  sub     rsp, 48h
0x18000a3e9  mov     rdi, r9
0x18000a3ec  mov     rsi, r8
0x18000a3ef  mov     rbp, rdx
0x18000a3f2  mov     [rsp+68h+var_38], 0
0x18000a3fb  mov     rbx, [rcx+10h]
0x18000a3ff  mov     rbx, [rbx+38h]
0x18000a403  test    rbx, rbx
0x18000a406  jz      short loc_18000A432
0x18000a408  mov     rcx, [rbx+18h]
0x18000a40c  test    rcx, rcx
0x18000a40f  jz      short loc_18000A42C
0x18000a411  mov     rax, [rcx]
0x18000a414  lea     r8, [rsp+68h+var_38]
0x18000a419  lea     rdx, _GUID_aa80e901_2021_11d2_93e0_0060b067b86e
0x18000a420  mov     rax, [rax]
0x18000a423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a428  test    eax, eax
0x18000a42a  jz      short loc_18000A432
0x18000a42c  mov     rbx, [rbx+8]
0x18000a430  jmp     short loc_18000A403
0x18000a432  mov     rcx, [rsp+68h+var_38]
0x18000a437  test    rcx, rcx
0x18000a43a  jz      short loc_18000A4AE
0x18000a43c  mov     [rsp+68h+arg_0], 0
0x18000a445  mov     rax, [rcx]
0x18000a448  lea     r8, [rsp+68h+arg_0]
0x18000a44d  lea     rdx, IID_IServiceProvider
0x18000a454  mov     rax, [rax]
0x18000a457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a45c  mov     rcx, [rsp+68h+arg_0]
0x18000a461  test    eax, eax
0x18000a463  jnz     short loc_18000A49C
0x18000a465  test    rcx, rcx
0x18000a468  jz      short loc_18000A49C
0x18000a46a  mov     rax, [rcx]
0x18000a46d  mov     r9, rdi
0x18000a470  mov     r8, rsi
0x18000a473  mov     rdx, rbp
0x18000a476  mov     rax, [rax+18h]
0x18000a47a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a47f  mov     ebx, eax
0x18000a481  mov     rcx, [rsp+68h+arg_0]
0x18000a486  test    rcx, rcx
0x18000a489  jz      short loc_18000A498
0x18000a48b  mov     rdx, [rcx]
0x18000a48e  mov     rax, [rdx+10h]
0x18000a492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a497  nop
0x18000a498  mov     eax, ebx
0x18000a49a  jmp     short loc_18000A4B3
0x18000a49c  test    rcx, rcx
0x18000a49f  jz      short loc_18000A4AE
0x18000a4a1  mov     rax, [rcx]
0x18000a4a4  mov     rax, [rax+10h]
0x18000a4a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4ad  nop
0x18000a4ae  mov     eax, 80004005h
0x18000a4b3  add     rsp, 48h
0x18000a4b7  pop     rdi
0x18000a4b8  pop     rsi
0x18000a4b9  pop     rbp
0x18000a4ba  pop     rbx
0x18000a4bb  retn
```
