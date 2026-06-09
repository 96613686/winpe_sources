# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IDOServiceCallback,IDOServiceCallback2>::`scalar deleting destructor'(uint)

- ea: `0x180009510`
- end: `0x180009538`
- name: `??_G?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIDOServiceCallback@@UIDOServiceCallback2@@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `40`
- prototype: `_DWORD *__fastcall(_DWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x180001f70`
- `0x180009510`

## pseudocode

```c
_DWORD *__fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IDOServiceCallback,IDOServiceCallback2>::`scalar deleting destructor'(
        _DWORD *a1,
        char a2)
{
  a1[5] = -1073741823;
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180009510  push    rbx
0x180009512  sub     rsp, 20h
0x180009516  mov     dword ptr [rcx+14h], 0C0000001h
0x18000951d  mov     rbx, rcx
0x180009520  test    dl, 1
0x180009523  jz      short loc_18000952F
0x180009525  mov     edx, 18h; unsigned __int64
0x18000952a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000952f  mov     rax, rbx
0x180009532  add     rsp, 20h
0x180009536  pop     rbx
0x180009537  retn
```
