# Microsoft::WRL::ClassFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)

- ea: `0x180002450`
- end: `0x1800024e4`
- name: `?Release@?$ClassFactory@VNil@Details@WRL@Microsoft@@V1234@V1234@$0A@@WRL@Microsoft@@UEAAKXZ`
- size: `148`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002450`
- `0x180004010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ClassFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // r9
  __int64 v3; // r8
  unsigned int v4; // edi
  int v5; // ebx

  v2 = 0x7FFFFFFF;
  do
  {
    v3 = *(unsigned int *)(a1 + 12);
    if ( (_DWORD)v3 == 0x7FFFFFFF )
      break;
    a2 = (unsigned int)(v3 - 1);
  }
  while ( (_DWORD)v3 != _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 12), a2, v3) );
  v4 = v3 - 1;
  if ( (_DWORD)v3 == 1 )
  {
    v5 = *(_DWORD *)(a1 + 20) & 5;
    if ( a1 )
      (*(void (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)a1 + 40LL))(a1, 1, v3, 0x7FFFFFFF);
    if ( v5 == 5 && Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *, __int64, __int64, __int64))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 16LL))(
        Microsoft::WRL::Details::ModuleBase::module_,
        a2,
        v3,
        v2);
  }
  else if ( (*(_DWORD *)(a1 + 20) & 6) == 0 && (_DWORD)v3 == 2 && Microsoft::WRL::Details::ModuleBase::module_ )
  {
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *, _QWORD, __int64, __int64))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 16LL))(
      Microsoft::WRL::Details::ModuleBase::module_,
      *(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_,
      v3,
      0x7FFFFFFF);
  }
  return v4;
}

```

## disassembly

```asm
0x180002450  mov     [rsp+arg_0], rbx
0x180002455  push    rdi
0x180002456  sub     rsp, 20h
0x18000245a  mov     r9d, 7FFFFFFFh
0x180002460  jmp     short loc_180002470
0x180002462  lea     edx, [r8-1]
0x180002466  mov     eax, r8d
0x180002469  lock cmpxchg [rcx+0Ch], edx
0x18000246e  jz      short loc_180002479
0x180002470  mov     r8d, [rcx+0Ch]
0x180002474  cmp     r8d, r9d
0x180002477  jnz     short loc_180002462
0x180002479  mov     ebx, [rcx+14h]
0x18000247c  lea     edi, [r8-1]
0x180002480  test    edi, edi
0x180002482  jnz     short loc_1800024B5
0x180002484  and     ebx, 5
0x180002487  test    rcx, rcx
0x18000248a  jz      short loc_18000249B
0x18000248c  mov     rax, [rcx]
0x18000248f  lea     edx, [rdi+1]
0x180002492  mov     rax, [rax+28h]
0x180002496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000249b  cmp     ebx, 5
0x18000249e  jnz     short loc_1800024D7
0x1800024a0  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800024a7  test    rcx, rcx
0x1800024aa  jz      short loc_1800024D7
0x1800024ac  mov     rax, [rcx]
0x1800024af  mov     rax, [rax+10h]
0x1800024b3  jmp     short loc_1800024D2
0x1800024b5  test    bl, 6
0x1800024b8  jnz     short loc_1800024D7
0x1800024ba  cmp     edi, 1
0x1800024bd  jnz     short loc_1800024D7
0x1800024bf  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800024c6  test    rcx, rcx
0x1800024c9  jz      short loc_1800024D7
0x1800024cb  mov     rdx, [rcx]
0x1800024ce  mov     rax, [rdx+10h]
0x1800024d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800024d7  mov     rbx, [rsp+28h+arg_0]
0x1800024dc  mov     eax, edi
0x1800024de  add     rsp, 20h
0x1800024e2  pop     rdi
0x1800024e3  retn
```
