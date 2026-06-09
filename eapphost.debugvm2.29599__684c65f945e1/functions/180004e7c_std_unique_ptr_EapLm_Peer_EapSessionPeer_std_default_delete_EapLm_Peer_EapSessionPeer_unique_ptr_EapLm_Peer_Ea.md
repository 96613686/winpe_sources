# std::unique_ptr<EapLm::Peer::EapSessionPeer,std::default_delete<EapLm::Peer::EapSessionPeer>>::~unique_ptr<EapLm::Peer::EapSessionPeer,std::default_delete<EapLm::Peer::EapSessionPeer>>(void)

- ea: `0x180004e7c`
- end: `0x180004e9d`
- name: `??1?$unique_ptr@VEapSessionPeer@Peer@EapLm@@U?$default_delete@VEapSessionPeer@Peer@EapLm@@@std@@@std@@QEAA@XZ`
- size: `33`
- prototype: ``
- caller_count: `19`
- callee_count: `2`
- tags: ``

## callers

- `0x180006310`
- `0x180012900`
- `0x180015140`
- `0x18001d9bc`
- `0x180022d70`
- `0x180022d9c`
- `0x180022e40`
- `0x180026df4`
- `0x180026e60`
- `0x180028f64`
- `0x1800343a7`
- `0x18003507e`
- `0x1800352e1`
- `0x180035576`
- `0x180036acc`
- `0x180036b0a`
- `0x180036b39`
- `0x180036b68`
- `0x180036bd2`

## callees

- `0x180004e7c`
- `0x180038010`

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
0x180004e7c  sub     rsp, 28h
0x180004e80  mov     rcx, [rcx]
0x180004e83  test    rcx, rcx
0x180004e86  jz      short loc_180004E98
0x180004e88  mov     rax, [rcx]
0x180004e8b  mov     edx, 1
0x180004e90  mov     rax, [rax]
0x180004e93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e98  add     rsp, 28h
0x180004e9c  retn
```
