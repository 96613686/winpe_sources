# APIReq::UnwrapNoException(HADALREQUEST__ *)

- ea: `0x14000a0ec`
- end: `0x14000a175`
- name: `?UnwrapNoException@APIReq@@SAPEAVTokenRequest@@PEAUHADALREQUEST__@@@Z`
- size: `137`
- prototype: `struct TokenRequest *__fastcall(struct HADALREQUEST__ *)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x14002c9d9`
- `0x14002ca21`
- `0x14002ca6d`
- `0x14002cab5`
- `0x14002cc17`
- `0x14002cc5f`

## callees

- `0x14000a0ec`
- `0x14000a17c`
- `0x140030010`

## pseudocode

```c
struct TokenRequest *__fastcall APIReq::UnwrapNoException(struct HADALREQUEST__ *a1)
{
  __int64 v2; // rax
  __int64 v3; // rdi
  volatile signed __int32 *v4; // rbx
  __int64 v5; // rdi

  if ( !a1 || !(unsigned __int8)APIHandle<APIReq,HADALREQUEST__ *,-1440046422>::Validate() )
  {
    v4 = 0;
LABEL_8:
    v5 = 0;
    goto LABEL_9;
  }
  v2 = *((_QWORD *)a1 + 2);
  if ( v2 )
    _InterlockedIncrement((volatile signed __int32 *)(v2 + 8));
  v3 = *((_QWORD *)a1 + 1);
  v4 = (volatile signed __int32 *)*((_QWORD *)a1 + 2);
  if ( !v3 )
    goto LABEL_8;
  v5 = *(_QWORD *)(v3 + 16);
LABEL_9:
  if ( v4 )
  {
    if ( _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
      if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
    }
  }
  return (struct TokenRequest *)v5;
}

```

## disassembly

```asm
0x14000a0ec  mov     [rsp+arg_0], rbx
0x14000a0f1  push    rdi
0x14000a0f2  sub     rsp, 20h
0x14000a0f6  mov     rbx, rcx
0x14000a0f9  test    rcx, rcx
0x14000a0fc  jz      short loc_14000A127
0x14000a0fe  call    ?Validate@?$APIHandle@VAPIReq@@PEAUHADALREQUEST__@@$0?FFNFFNFG@@@CA_NPEBV1@@Z; APIHandle<APIReq,HADALREQUEST__ *,-1440046422>::Validate(APIHandle<APIReq,HADALREQUEST__ *,-1440046422> const *)
0x14000a103  test    al, al
0x14000a105  jz      short loc_14000A127
0x14000a107  mov     rax, [rbx+10h]
0x14000a10b  test    rax, rax
0x14000a10e  jz      short loc_14000A114
0x14000a110  lock inc dword ptr [rax+8]
0x14000a114  mov     rdi, [rbx+8]
0x14000a118  mov     rbx, [rbx+10h]
0x14000a11c  test    rdi, rdi
0x14000a11f  jz      short loc_14000A129
0x14000a121  mov     rdi, [rdi+10h]
0x14000a125  jmp     short loc_14000A12B
0x14000a127  xor     ebx, ebx
0x14000a129  xor     edi, edi
0x14000a12b  test    rbx, rbx
0x14000a12e  jz      short loc_14000A167
0x14000a130  or      eax, 0FFFFFFFFh
0x14000a133  lock xadd [rbx+8], eax
0x14000a138  cmp     eax, 1
0x14000a13b  jnz     short loc_14000A167
0x14000a13d  mov     rax, [rbx]
0x14000a140  mov     rcx, rbx
0x14000a143  mov     rax, [rax]
0x14000a146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a14b  or      edx, 0FFFFFFFFh
0x14000a14e  lock xadd [rbx+0Ch], edx
0x14000a153  cmp     edx, 1
0x14000a156  jnz     short loc_14000A167
0x14000a158  mov     rdx, [rbx]
0x14000a15b  mov     rcx, rbx
0x14000a15e  mov     rax, [rdx+8]
0x14000a162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a167  mov     rbx, [rsp+28h+arg_0]
0x14000a16c  mov     rax, rdi
0x14000a16f  add     rsp, 20h
0x14000a173  pop     rdi
0x14000a174  retn
```
