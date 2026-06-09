# Microsoft::WRL::ClassFactory<IClassFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>::Release(void)

- ea: `0x1800031c0`
- end: `0x180003254`
- name: `?Release@?$ClassFactory@UIClassFactory@@VFtmBase@WRL@Microsoft@@VNil@Details@34@$0A@@WRL@Microsoft@@UEAAKXZ`
- size: `148`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003260`
- `0x180003270`

## callees

- `0x1800031c0`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ClassFactory<IClassFactory,Microsoft::WRL::FtmBase,Microsoft::WRL::Details::Nil,0>::Release(
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
    v3 = *(unsigned int *)(a1 + 52);
    if ( (_DWORD)v3 == 0x7FFFFFFF )
      break;
    a2 = (unsigned int)(v3 - 1);
  }
  while ( (_DWORD)v3 != _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 52), a2, v3) );
  v4 = v3 - 1;
  if ( (_DWORD)v3 == 1 )
  {
    v5 = *(_DWORD *)(a1 + 60) & 5;
    if ( a1 )
      (*(void (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)a1 + 40LL))(a1, 1, v3, 0x7FFFFFFF);
    if ( v5 == 5 && Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *, __int64, __int64, __int64))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 16LL))(
        Microsoft::WRL::Details::ModuleBase::module_,
        a2,
        v3,
        v2);
  }
  else if ( (*(_DWORD *)(a1 + 60) & 6) == 0 && (_DWORD)v3 == 2 && Microsoft::WRL::Details::ModuleBase::module_ )
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
0x1800031c0  mov     [rsp+arg_0], rbx
0x1800031c5  push    rdi
0x1800031c6  sub     rsp, 20h
0x1800031ca  mov     r9d, 7FFFFFFFh
0x1800031d0  jmp     short loc_1800031E0
0x1800031d2  lea     edx, [r8-1]
0x1800031d6  mov     eax, r8d
0x1800031d9  lock cmpxchg [rcx+34h], edx
0x1800031de  jz      short loc_1800031E9
0x1800031e0  mov     r8d, [rcx+34h]
0x1800031e4  cmp     r8d, r9d
0x1800031e7  jnz     short loc_1800031D2
0x1800031e9  mov     ebx, [rcx+3Ch]
0x1800031ec  lea     edi, [r8-1]
0x1800031f0  test    edi, edi
0x1800031f2  jnz     short loc_180003225
0x1800031f4  and     ebx, 5
0x1800031f7  test    rcx, rcx
0x1800031fa  jz      short loc_18000320B
0x1800031fc  mov     rax, [rcx]
0x1800031ff  lea     edx, [rdi+1]
0x180003202  mov     rax, [rax+28h]
0x180003206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000320b  cmp     ebx, 5
0x18000320e  jnz     short loc_180003247
0x180003210  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180003217  test    rcx, rcx
0x18000321a  jz      short loc_180003247
0x18000321c  mov     rax, [rcx]
0x18000321f  mov     rax, [rax+10h]
0x180003223  jmp     short loc_180003242
0x180003225  test    bl, 6
0x180003228  jnz     short loc_180003247
0x18000322a  cmp     edi, 1
0x18000322d  jnz     short loc_180003247
0x18000322f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180003236  test    rcx, rcx
0x180003239  jz      short loc_180003247
0x18000323b  mov     rdx, [rcx]
0x18000323e  mov     rax, [rdx+10h]
0x180003242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003247  mov     rbx, [rsp+28h+arg_0]
0x18000324c  mov     eax, edi
0x18000324e  add     rsp, 20h
0x180003252  pop     rdi
0x180003253  retn
```
