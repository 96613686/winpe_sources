# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IPopupCommand>::Release(void)

- ea: `0x180002570`
- end: `0x1800025d1`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIPopupCommand@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `97`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002570`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IPopupCommand>::Release(
        volatile signed __int32 *a1)
{
  __int64 v1; // r9
  __int64 v2; // r8
  unsigned int v3; // ebx

  v1 = 0x7FFFFFFF;
  do
    v2 = *((unsigned int *)a1 + 3);
  while ( (_DWORD)v2 != 0x7FFFFFFF && (_DWORD)v2 != _InterlockedCompareExchange(a1 + 3, v2 - 1, v2) );
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
0x180002570  push    rbx
0x180002572  sub     rsp, 20h
0x180002576  mov     r9d, 7FFFFFFFh
0x18000257c  jmp     short loc_18000258C
0x18000257e  lea     edx, [r8-1]
0x180002582  mov     eax, r8d
0x180002585  lock cmpxchg [rcx+0Ch], edx
0x18000258a  jz      short loc_180002595
0x18000258c  mov     r8d, [rcx+0Ch]
0x180002590  cmp     r8d, r9d
0x180002593  jnz     short loc_18000257E
0x180002595  lea     ebx, [r8-1]
0x180002599  test    ebx, ebx
0x18000259b  jnz     short loc_1800025C9
0x18000259d  test    rcx, rcx
0x1800025a0  jz      short loc_1800025B1
0x1800025a2  mov     rax, [rcx]
0x1800025a5  lea     edx, [rbx+1]
0x1800025a8  mov     rax, [rax+30h]
0x1800025ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025b1  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800025b8  test    rcx, rcx
0x1800025bb  jz      short loc_1800025C9
0x1800025bd  mov     rdx, [rcx]
0x1800025c0  mov     rax, [rdx+10h]
0x1800025c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025c9  mov     eax, ebx
0x1800025cb  add     rsp, 20h
0x1800025cf  pop     rbx
0x1800025d0  retn
```
