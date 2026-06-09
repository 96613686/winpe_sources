# CSinkWrapBase<DocTraitsAnchor>::QueryService(_GUID const &,_GUID const &,void * *)

- ea: `0x18000a4d0`
- end: `0x18000a5ac`
- name: `?QueryService@?$CSinkWrapBase@VDocTraitsAnchor@@@@UEAAJAEBU_GUID@@0PEAPEAX@Z`
- size: `220`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18000a4d0`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall CSinkWrapBase<DocTraitsAnchor>::QueryService(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
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
      if ( !(**v8)(v8, &GUID_aa80e9fe_2021_11d2_93e0_0060b067b86e, v11) )
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
0x18000a4d0  push    rbx
0x18000a4d2  push    rbp
0x18000a4d3  push    rsi
0x18000a4d4  push    rdi
0x18000a4d5  sub     rsp, 48h
0x18000a4d9  mov     rdi, r9
0x18000a4dc  mov     rsi, r8
0x18000a4df  mov     rbp, rdx
0x18000a4e2  mov     [rsp+68h+var_38], 0
0x18000a4eb  mov     rbx, [rcx+10h]
0x18000a4ef  mov     rbx, [rbx+38h]
0x18000a4f3  test    rbx, rbx
0x18000a4f6  jz      short loc_18000A522
0x18000a4f8  mov     rcx, [rbx+18h]
0x18000a4fc  test    rcx, rcx
0x18000a4ff  jz      short loc_18000A51C
0x18000a501  mov     rax, [rcx]
0x18000a504  lea     r8, [rsp+68h+var_38]
0x18000a509  lea     rdx, _GUID_aa80e9fe_2021_11d2_93e0_0060b067b86e
0x18000a510  mov     rax, [rax]
0x18000a513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a518  test    eax, eax
0x18000a51a  jz      short loc_18000A522
0x18000a51c  mov     rbx, [rbx+8]
0x18000a520  jmp     short loc_18000A4F3
0x18000a522  mov     rcx, [rsp+68h+var_38]
0x18000a527  test    rcx, rcx
0x18000a52a  jz      short loc_18000A59E
0x18000a52c  mov     [rsp+68h+arg_0], 0
0x18000a535  mov     rax, [rcx]
0x18000a538  lea     r8, [rsp+68h+arg_0]
0x18000a53d  lea     rdx, IID_IServiceProvider
0x18000a544  mov     rax, [rax]
0x18000a547  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a54c  mov     rcx, [rsp+68h+arg_0]
0x18000a551  test    eax, eax
0x18000a553  jnz     short loc_18000A58C
0x18000a555  test    rcx, rcx
0x18000a558  jz      short loc_18000A58C
0x18000a55a  mov     rax, [rcx]
0x18000a55d  mov     r9, rdi
0x18000a560  mov     r8, rsi
0x18000a563  mov     rdx, rbp
0x18000a566  mov     rax, [rax+18h]
0x18000a56a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a56f  mov     ebx, eax
0x18000a571  mov     rcx, [rsp+68h+arg_0]
0x18000a576  test    rcx, rcx
0x18000a579  jz      short loc_18000A588
0x18000a57b  mov     rdx, [rcx]
0x18000a57e  mov     rax, [rdx+10h]
0x18000a582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a587  nop
0x18000a588  mov     eax, ebx
0x18000a58a  jmp     short loc_18000A5A3
0x18000a58c  test    rcx, rcx
0x18000a58f  jz      short loc_18000A59E
0x18000a591  mov     rax, [rcx]
0x18000a594  mov     rax, [rax+10h]
0x18000a598  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a59d  nop
0x18000a59e  mov     eax, 80004005h
0x18000a5a3  add     rsp, 48h
0x18000a5a7  pop     rdi
0x18000a5a8  pop     rsi
0x18000a5a9  pop     rbp
0x18000a5aa  pop     rbx
0x18000a5ab  retn
```
