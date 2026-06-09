# CConfigServiceProvider2Impl::GetConfigSession(IConfigSession2 * *)

- ea: `0x180008110`
- end: `0x18000814d`
- name: `?GetConfigSession@CConfigServiceProvider2Impl@@UEAAJPEAPEAUIConfigSession2@@@Z`
- size: `61`
- prototype: `__int64 __fastcall(CConfigServiceProvider2Impl *__hidden this, struct IConfigSession2 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task`

## callees

- `0x180008110`
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
0x180008110  sub     rsp, 28h
0x180008114  test    rdx, rdx
0x180008117  jz      short loc_180008143
0x180008119  mov     qword ptr [rdx], 0
0x180008120  mov     rcx, [rcx+10h]
0x180008124  test    rcx, rcx
0x180008127  jz      short loc_18000813C
0x180008129  mov     [rdx], rcx
0x18000812c  mov     rax, [rcx]
0x18000812f  mov     rax, [rax+8]
0x180008133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008138  xor     eax, eax
0x18000813a  jmp     short loc_180008148
0x18000813c  mov     eax, 80070002h
0x180008141  jmp     short loc_180008148
0x180008143  mov     eax, 80070057h
0x180008148  add     rsp, 28h
0x18000814c  retn
```
