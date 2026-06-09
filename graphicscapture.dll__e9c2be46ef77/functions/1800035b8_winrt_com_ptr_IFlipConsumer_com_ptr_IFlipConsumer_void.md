# winrt::com_ptr<IFlipConsumer>::~com_ptr<IFlipConsumer>(void)

- ea: `0x1800035b8`
- end: `0x1800035cc`
- name: `??1?$com_ptr@UIFlipConsumer@@@winrt@@QEAA@XZ`
- size: `20`
- prototype: ``
- caller_count: `30`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180025e18`
- `0x180025e2a`
- `0x180025ecc`
- `0x180025f06`
- `0x180025f1c`
- `0x180025f32`
- `0x180025f48`
- `0x180025f5e`
- `0x180025fd2`
- `0x1800260c9`
- `0x1800260ed`
- `0x1800260ff`
- `0x180026135`
- `0x180026159`
- `0x18002623b`
- `0x18002624d`
- `0x18002625f`
- `0x180026271`
- `0x180026295`
- `0x1800262a7`
- `0x180026587`
- `0x18002692b`
- `0x1800269a3`
- `0x180026cd6`
- `0x180026d72`
- `0x1800271d3`
- `0x1800272aa`
- `0x180027598`
- `0x1800275ce`
- `0x1800275e4`

## callees

- `0x1800035b8`
- `0x180006610`

## pseudocode

```c
__int64 __fastcall winrt::com_ptr<IFlipConsumer>::~com_ptr<IFlipConsumer>(_QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(a1);
  return result;
}

```

## disassembly

```asm
0x1800035b8  sub     rsp, 28h
0x1800035bc  cmp     qword ptr [rcx], 0
0x1800035c0  jz      short loc_1800035C7
0x1800035c2  call    ?unconditional_release_ref@?$com_ptr@UID3D11DeviceContext@@@winrt@@AEAAXXZ; winrt::com_ptr<ID3D11DeviceContext>::unconditional_release_ref(void)
0x1800035c7  add     rsp, 28h
0x1800035cb  retn
```
