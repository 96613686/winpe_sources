# Microsoft::WRL::ComPtr<CProvisioningNode>::~ComPtr<CProvisioningNode>(void)

- ea: `0x1800081ec`
- end: `0x180008215`
- name: `??1?$ComPtr@VCProvisioningNode@@@WRL@Microsoft@@QEAA@XZ`
- size: `41`
- prototype: ``
- caller_count: `16`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800360eb`
- `0x1800360fd`
- `0x180036121`
- `0x18003625d`
- `0x180036319`
- `0x18003632b`
- `0x1800363ea`
- `0x1800368da`
- `0x1800368ec`
- `0x1800368fe`
- `0x1800369a0`
- `0x180036b49`
- `0x180036b5b`
- `0x180037773`
- `0x180037785`
- `0x18003789f`

## callees

- `0x1800081ec`
- `0x180038010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::ComPtr<CProvisioningNode>::~ComPtr<CProvisioningNode>(_QWORD *a1)
{
  _QWORD *result; // rax
  __int64 v2; // rcx

  result = a1;
  v2 = *a1;
  if ( v2 )
  {
    *result = 0;
    return (_QWORD *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  return result;
}

```

## disassembly

```asm
0x1800081ec  sub     rsp, 28h
0x1800081f0  mov     rax, rcx
0x1800081f3  mov     rcx, [rcx]
0x1800081f6  test    rcx, rcx
0x1800081f9  jz      short loc_18000820F
0x1800081fb  mov     qword ptr [rax], 0
0x180008202  mov     rax, [rcx]
0x180008205  mov     rax, [rax+10h]
0x180008209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000820e  nop
0x18000820f  add     rsp, 28h
0x180008213  retn
```
