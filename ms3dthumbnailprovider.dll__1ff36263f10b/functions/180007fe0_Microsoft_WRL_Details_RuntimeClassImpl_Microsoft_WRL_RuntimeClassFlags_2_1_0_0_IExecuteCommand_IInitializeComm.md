# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExecuteCommand,IInitializeCommand,IObjectWithSelection>::Release(void)

- ea: `0x180007fe0`
- end: `0x180008041`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIExecuteCommand@@UIInitializeCommand@@UIObjectWithSelection@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `97`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008050`
- `0x180008060`

## callees

- `0x180007fe0`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IExecuteCommand,IInitializeCommand,IObjectWithSelection>::Release(
        volatile signed __int32 *a1)
{
  __int64 v1; // r9
  __int64 v2; // r8
  unsigned int v3; // ebx

  v1 = 0x7FFFFFFF;
  do
    v2 = *((unsigned int *)a1 + 7);
  while ( (_DWORD)v2 != 0x7FFFFFFF && (_DWORD)v2 != _InterlockedCompareExchange(a1 + 7, v2 - 1, v2) );
  v3 = v2 - 1;
  if ( (_DWORD)v2 == 1 )
  {
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, __int64, __int64, __int64))(*(_QWORD *)a1 + 80LL))(
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
0x180007fe0  push    rbx
0x180007fe2  sub     rsp, 20h
0x180007fe6  mov     r9d, 7FFFFFFFh
0x180007fec  jmp     short loc_180007FFC
0x180007fee  lea     edx, [r8-1]
0x180007ff2  mov     eax, r8d
0x180007ff5  lock cmpxchg [rcx+1Ch], edx
0x180007ffa  jz      short loc_180008005
0x180007ffc  mov     r8d, [rcx+1Ch]
0x180008000  cmp     r8d, r9d
0x180008003  jnz     short loc_180007FEE
0x180008005  lea     ebx, [r8-1]
0x180008009  test    ebx, ebx
0x18000800b  jnz     short loc_180008039
0x18000800d  test    rcx, rcx
0x180008010  jz      short loc_180008021
0x180008012  mov     rax, [rcx]
0x180008015  lea     edx, [rbx+1]
0x180008018  mov     rax, [rax+50h]
0x18000801c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008021  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180008028  test    rcx, rcx
0x18000802b  jz      short loc_180008039
0x18000802d  mov     rdx, [rcx]
0x180008030  mov     rax, [rdx+10h]
0x180008034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008039  mov     eax, ebx
0x18000803b  add     rsp, 20h
0x18000803f  pop     rbx
0x180008040  retn
```
