# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEmptyVolumeCache>::Release(void)

- ea: `0x18000ba60`
- end: `0x18000bac1`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIEmptyVolumeCache@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `97`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000ba60`
- `0x18000e010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEmptyVolumeCache>::Release(
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
      (*(void (__fastcall **)(volatile signed __int32 *, __int64, __int64, __int64))(*(_QWORD *)a1 + 64LL))(
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
0x18000ba60  push    rbx
0x18000ba62  sub     rsp, 20h
0x18000ba66  mov     r9d, 7FFFFFFFh
0x18000ba6c  jmp     short loc_18000BA7C
0x18000ba6e  lea     edx, [r8-1]
0x18000ba72  mov     eax, r8d
0x18000ba75  lock cmpxchg [rcx+0Ch], edx
0x18000ba7a  jz      short loc_18000BA85
0x18000ba7c  mov     r8d, [rcx+0Ch]
0x18000ba80  cmp     r8d, r9d
0x18000ba83  jnz     short loc_18000BA6E
0x18000ba85  lea     ebx, [r8-1]
0x18000ba89  test    ebx, ebx
0x18000ba8b  jnz     short loc_18000BAB9
0x18000ba8d  test    rcx, rcx
0x18000ba90  jz      short loc_18000BAA1
0x18000ba92  mov     rax, [rcx]
0x18000ba95  lea     edx, [rbx+1]
0x18000ba98  mov     rax, [rax+40h]
0x18000ba9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000baa1  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000baa8  test    rcx, rcx
0x18000baab  jz      short loc_18000BAB9
0x18000baad  mov     rdx, [rcx]
0x18000bab0  mov     rax, [rdx+10h]
0x18000bab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bab9  mov     eax, ebx
0x18000babb  add     rsp, 20h
0x18000babf  pop     rbx
0x18000bac0  retn
```
