# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDOServiceCallback,IDOServiceCallback2>::Release(void)

- ea: `0x18000a270`
- end: `0x18000a2d1`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIDOServiceCallback@@UIDOServiceCallback2@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `97`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a2e0`

## callees

- `0x18000a270`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IDOServiceCallback,IDOServiceCallback2>::Release(
        volatile signed __int32 *a1)
{
  __int64 v1; // r9
  __int64 v2; // r8
  unsigned int v3; // ebx

  v1 = 0x7FFFFFFF;
  do
    v2 = *((unsigned int *)a1 + 5);
  while ( (_DWORD)v2 != 0x7FFFFFFF && (_DWORD)v2 != _InterlockedCompareExchange(a1 + 5, v2 - 1, v2) );
  v3 = v2 - 1;
  if ( (_DWORD)v2 == 1 )
  {
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, __int64, __int64, __int64))(*(_QWORD *)a1 + 48LL))(
        a1,
        1,
        v2,
        0x7FFFFFFF);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *, _QWORD, __int64, __int64))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 16LL))(
        Microsoft::WRL::Details::ModuleBase::module_,
        *(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_,
        v2,
        v1);
  }
  return v3;
}

```

## disassembly

```asm
0x18000a270  push    rbx
0x18000a272  sub     rsp, 20h
0x18000a276  mov     r9d, 7FFFFFFFh
0x18000a27c  jmp     short loc_18000A28C
0x18000a27e  lea     edx, [r8-1]
0x18000a282  mov     eax, r8d
0x18000a285  lock cmpxchg [rcx+14h], edx
0x18000a28a  jz      short loc_18000A295
0x18000a28c  mov     r8d, [rcx+14h]
0x18000a290  cmp     r8d, r9d
0x18000a293  jnz     short loc_18000A27E
0x18000a295  lea     ebx, [r8-1]
0x18000a299  test    ebx, ebx
0x18000a29b  jnz     short loc_18000A2C9
0x18000a29d  test    rcx, rcx
0x18000a2a0  jz      short loc_18000A2B1
0x18000a2a2  mov     rax, [rcx]
0x18000a2a5  lea     edx, [rbx+1]
0x18000a2a8  mov     rax, [rax+30h]
0x18000a2ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2b1  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000a2b8  test    rcx, rcx
0x18000a2bb  jz      short loc_18000A2C9
0x18000a2bd  mov     rdx, [rcx]
0x18000a2c0  mov     rax, [rdx+10h]
0x18000a2c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2c9  mov     eax, ebx
0x18000a2cb  add     rsp, 20h
0x18000a2cf  pop     rbx
0x18000a2d0  retn
```
