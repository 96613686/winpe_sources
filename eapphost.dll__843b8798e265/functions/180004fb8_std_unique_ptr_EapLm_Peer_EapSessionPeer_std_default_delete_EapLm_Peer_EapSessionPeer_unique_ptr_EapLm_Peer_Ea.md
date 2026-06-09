# std::unique_ptr<EapLm::Peer::EapSessionPeer,std::default_delete<EapLm::Peer::EapSessionPeer>>::~unique_ptr<EapLm::Peer::EapSessionPeer,std::default_delete<EapLm::Peer::EapSessionPeer>>(void)

- ea: `0x180004fb8`
- end: `0x180004fda`
- name: `??1?$unique_ptr@VEapSessionPeer@Peer@EapLm@@U?$default_delete@VEapSessionPeer@Peer@EapLm@@@std@@@std@@QEAA@XZ`
- size: `34`
- prototype: ``
- caller_count: `19`
- callee_count: `2`
- tags: ``

## callers

- `0x180006580`
- `0x180013090`
- `0x180015980`
- `0x18001e4ac`
- `0x1800239b4`
- `0x1800239e0`
- `0x180023a90`
- `0x180027b60`
- `0x180027bcc`
- `0x180029d84`
- `0x180035767`
- `0x18003641f`
- `0x180036698`
- `0x180036930`
- `0x180037e9a`
- `0x180037ed9`
- `0x180037f09`
- `0x180037f39`
- `0x180037fa4`

## callees

- `0x180004fb8`
- `0x180039010`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<EapLm::Peer::EapSessionPeer>::~unique_ptr<EapLm::Peer::EapSessionPeer>(
        __int64 (__fastcall ****a1)(_QWORD, __int64))
{
  __int64 (__fastcall ***v1)(_QWORD, __int64); // rcx
  __int64 result; // rax

  v1 = *a1;
  if ( v1 )
    return (**v1)(v1, 1);
  return result;
}

```

## disassembly

```asm
0x180004fb8  sub     rsp, 28h
0x180004fbc  mov     rcx, [rcx]
0x180004fbf  test    rcx, rcx
0x180004fc2  jz      short loc_180004FD4
0x180004fc4  mov     rax, [rcx]
0x180004fc7  mov     edx, 1
0x180004fcc  mov     rax, [rax]
0x180004fcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fd4  add     rsp, 28h
0x180004fd8  retn
```
