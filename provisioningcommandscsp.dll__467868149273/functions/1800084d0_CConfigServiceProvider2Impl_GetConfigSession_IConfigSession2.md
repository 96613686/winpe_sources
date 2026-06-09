# CConfigServiceProvider2Impl::GetConfigSession(IConfigSession2 * *)

- ea: `0x1800084d0`
- end: `0x18000850e`
- name: `?GetConfigSession@CConfigServiceProvider2Impl@@UEAAJPEAPEAUIConfigSession2@@@Z`
- size: `62`
- prototype: `__int64 __fastcall(CConfigServiceProvider2Impl *__hidden this, struct IConfigSession2 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task`

## callees

- `0x1800084d0`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall CConfigServiceProvider2Impl::GetConfigSession(
        CConfigServiceProvider2Impl *this,
        struct IConfigSession2 **a2)
{
  struct IConfigSession2 *v2; // rcx

  if ( !a2 )
    return 2147942487LL;
  *a2 = 0;
  v2 = (struct IConfigSession2 *)*((_QWORD *)this + 2);
  if ( !v2 )
    return 2147942402LL;
  *a2 = v2;
  (*(void (__fastcall **)(struct IConfigSession2 *))(*(_QWORD *)v2 + 8LL))(v2);
  return 0;
}

```

## disassembly

```asm
0x1800084d0  sub     rsp, 28h
0x1800084d4  test    rdx, rdx
0x1800084d7  jz      short loc_180008503
0x1800084d9  mov     qword ptr [rdx], 0
0x1800084e0  mov     rcx, [rcx+10h]
0x1800084e4  test    rcx, rcx
0x1800084e7  jz      short loc_1800084FC
0x1800084e9  mov     [rdx], rcx
0x1800084ec  mov     rax, [rcx]
0x1800084ef  mov     rax, [rax+8]
0x1800084f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084f8  xor     eax, eax
0x1800084fa  jmp     short loc_180008508
0x1800084fc  mov     eax, 80070002h
0x180008501  jmp     short loc_180008508
0x180008503  mov     eax, 80070057h
0x180008508  add     rsp, 28h
0x18000850c  retn
```
