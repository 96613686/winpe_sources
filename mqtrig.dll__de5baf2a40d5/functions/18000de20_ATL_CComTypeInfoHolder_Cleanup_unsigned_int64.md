# ATL::CComTypeInfoHolder::Cleanup(unsigned __int64)

- ea: `0x18000de20`
- end: `0x18000de66`
- name: `?Cleanup@CComTypeInfoHolder@ATL@@SAX_K@Z`
- size: `70`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002d84`
- `0x18000de20`
- `0x180022010`

## pseudocode

```c
void __fastcall ATL::CComTypeInfoHolder::Cleanup(__int64 a1)
{
  __int64 v2; // rcx
  ATL::CComTypeInfoHolder::stringdispid *v3; // rcx

  if ( a1 )
  {
    v2 = *(_QWORD *)(a1 + 24);
    if ( v2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    v3 = *(ATL::CComTypeInfoHolder::stringdispid **)(a1 + 40);
    *(_QWORD *)(a1 + 24) = 0;
    if ( v3 )
      ATL::CComTypeInfoHolder::stringdispid::`vector deleting destructor'(v3);
    *(_QWORD *)(a1 + 40) = 0;
  }
}

```

## disassembly

```asm
0x18000de20  test    rcx, rcx
0x18000de23  jz      short locret_18000DE65
0x18000de25  push    rbx
0x18000de26  sub     rsp, 20h
0x18000de2a  mov     rbx, rcx
0x18000de2d  mov     rcx, [rcx+18h]
0x18000de31  test    rcx, rcx
0x18000de34  jz      short loc_18000DE42
0x18000de36  mov     rax, [rcx]
0x18000de39  mov     rax, [rax+10h]
0x18000de3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de42  mov     rcx, [rbx+28h]; this
0x18000de46  mov     qword ptr [rbx+18h], 0
0x18000de4e  test    rcx, rcx
0x18000de51  jz      short loc_18000DE58
0x18000de53  call    ??_Estringdispid@CComTypeInfoHolder@ATL@@QEAAPEAXI@Z; ATL::CComTypeInfoHolder::stringdispid::`vector deleting destructor'(uint)
0x18000de58  mov     qword ptr [rbx+28h], 0
0x18000de60  add     rsp, 20h
0x18000de64  pop     rbx
0x18000de65  retn
```
