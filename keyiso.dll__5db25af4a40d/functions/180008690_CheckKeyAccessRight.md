# CheckKeyAccessRight

- ea: `0x180008690`
- end: `0x180008756`
- name: `CheckKeyAccessRight`
- size: `198`
- prototype: `__int64 __fastcall(void *, __int64, __int64, unsigned int, unsigned int, __int64, __int64, _QWORD *)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800082b0`
- `0x180008480`
- `0x18000d440`
- `0x18000dae0`
- `0x18000dd40`

## callees

- `0x180008690`
- `0x18000875c`
- `0x180008954`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x1800086bb`
- `RPCRT4!RpcImpersonateClient` at `0x1800086bb`
- `RPCRT4!RpcRevertToSelf` at `0x1800086fd`
- `RPCRT4!RpcRevertToSelf` at `0x1800086fd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800086e8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800086e8`

## pseudocode

```c
__int64 __fastcall CheckKeyAccessRight(
        void *a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        unsigned int a5,
        __int64 a6,
        __int64 a7,
        _QWORD *a8)
{
  HANDLE v8; // rbx
  __int64 v11; // rcx
  RPC_STATUS v12; // esi
  int v13; // edi
  HANDLE hObject[9]; // [rsp+40h] [rbp-48h] BYREF

  v8 = 0;
  hObject[0] = 0;
  if ( a8 )
    *a8 = 0;
  v12 = RpcImpersonateClient(a1);
  if ( !v12 || v12 == 1725 )
  {
    v13 = OpenCallerToken(v11, hObject);
    if ( !v12 )
      RpcRevertToSelf();
    v8 = hObject[0];
  }
  else
  {
    v13 = v12;
  }
  if ( v13 >= 0 )
    v13 = CheckKeyAccessRightInternal(v8, a3, a4, a5, a6, a7, a8);
  if ( v8 )
    CloseHandle(v8);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180008690  push    rbx
0x180008692  push    rbp
0x180008693  push    rsi
0x180008694  push    rdi
0x180008695  push    r14
0x180008697  push    r15
0x180008699  sub     rsp, 58h
0x18000869d  mov     r14, [rsp+88h+arg_38]
0x1800086a5  xor     ebx, ebx
0x1800086a7  mov     [rsp+88h+hObject], rbx
0x1800086ac  mov     ebp, r9d
0x1800086af  mov     r15, r8
0x1800086b2  test    r14, r14
0x1800086b5  jnz     loc_18000873E
0x1800086bb  call    cs:__imp_RpcImpersonateClient
0x1800086c1  mov     esi, eax
0x1800086c3  test    eax, eax
0x1800086c5  jnz     short loc_180008746
0x1800086c7  lea     rdx, [rsp+88h+hObject]
0x1800086cc  call    _OpenCallerToken
0x1800086d1  mov     edi, eax
0x1800086d3  test    esi, esi
0x1800086d5  jz      short loc_1800086FD
0x1800086d7  mov     rbx, [rsp+88h+hObject]
0x1800086dc  test    edi, edi
0x1800086de  jns     short loc_180008705
0x1800086e0  test    rbx, rbx
0x1800086e3  jz      short loc_1800086EE
0x1800086e5  mov     rcx, rbx; hObject
0x1800086e8  call    cs:__imp_CloseHandle
0x1800086ee  mov     eax, edi
0x1800086f0  add     rsp, 58h
0x1800086f4  pop     r15
0x1800086f6  pop     r14
0x1800086f8  pop     rdi
0x1800086f9  pop     rsi
0x1800086fa  pop     rbp
0x1800086fb  pop     rbx
0x1800086fc  retn
0x1800086fd  call    cs:__imp_RpcRevertToSelf
0x180008703  jmp     short loc_1800086D7
0x180008705  mov     rax, [rsp+88h+arg_30]
0x18000870d  mov     r8d, ebp
0x180008710  mov     r9d, [rsp+88h+arg_20]
0x180008718  mov     rdx, r15
0x18000871b  mov     [rsp+88h+var_58], r14
0x180008720  mov     rcx, rbx
0x180008723  mov     [rsp+88h+var_60], rax
0x180008728  mov     rax, [rsp+88h+arg_28]
0x180008730  mov     [rsp+88h+var_68], rax
0x180008735  call    CheckKeyAccessRightInternal
0x18000873a  mov     edi, eax
0x18000873c  jmp     short loc_1800086E0
0x18000873e  mov     [r14], rbx
0x180008741  jmp     loc_1800086BB
0x180008746  cmp     esi, 6BDh
0x18000874c  jz      loc_1800086C7
0x180008752  mov     edi, esi
0x180008754  jmp     short loc_1800086DC
```
