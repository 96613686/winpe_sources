# Microsoft::WRL::ClassFactory<IClassFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)

- ea: `0x180002090`
- end: `0x180002104`
- name: `?Release@?$ClassFactory@UIClassFactory@@VNil@Details@WRL@Microsoft@@V2345@$0A@@WRL@Microsoft@@UEAAKXZ`
- size: `116`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001e50`
- `0x1800040a0`

## callees

- `0x180002090`
- `0x180002550`
- `0x180006010`

## pseudocode

```c
__int64 Microsoft::WRL::ClassFactory<IClassFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release()
{
  __int64 result; // rax
  _DWORD *v1; // rcx
  unsigned int v2; // ebx
  int v3; // edi
  struct Microsoft::WRL::Details::ModuleBase *v4; // rcx

  result = Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<6>,0,0,0,IClassFactory,IClassFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::InternalRelease();
  v2 = result;
  if ( !(_DWORD)result )
  {
    v3 = v1[7] & 5;
    if ( v1 )
      (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)v1 + 40LL))(v1, 1);
    if ( v3 != 5 )
      return v2;
    v4 = Microsoft::WRL::Details::ModuleBase::module_;
    if ( !Microsoft::WRL::Details::ModuleBase::module_ )
      return v2;
    goto LABEL_10;
  }
  if ( (v1[7] & 6) == 0 && (_DWORD)result == 1 )
  {
    v4 = Microsoft::WRL::Details::ModuleBase::module_;
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
    {
LABEL_10:
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v4 + 16LL))(v4);
      return v2;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002090  mov     [rsp+arg_0], rbx
0x180002095  push    rdi
0x180002096  sub     rsp, 20h
0x18000209a  call    ?InternalRelease@?$RuntimeClassImpl@U?$RuntimeClassFlags@$05@WRL@Microsoft@@$0A@$0A@$0A@UIClassFactory@@U4@VNil@Details@23@V5623@V5623@@Details@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<6>,0,0,0,IClassFactory,IClassFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::InternalRelease(void)
0x18000209f  mov     edi, [rcx+1Ch]
0x1800020a2  mov     ebx, eax
0x1800020a4  test    eax, eax
0x1800020a6  jnz     short loc_1800020D4
0x1800020a8  and     edi, 5
0x1800020ab  test    rcx, rcx
0x1800020ae  jz      short loc_1800020C1
0x1800020b0  mov     rax, [rcx]
0x1800020b3  mov     edx, 1
0x1800020b8  mov     rax, [rax+28h]
0x1800020bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020c1  cmp     edi, 5
0x1800020c4  jnz     short loc_1800020F7
0x1800020c6  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800020cd  test    rcx, rcx
0x1800020d0  jnz     short loc_1800020EB
0x1800020d2  jmp     short loc_1800020F7
0x1800020d4  test    dil, 6
0x1800020d8  jnz     short loc_1800020F9
0x1800020da  cmp     ebx, 1
0x1800020dd  jnz     short loc_1800020F9
0x1800020df  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800020e6  test    rcx, rcx
0x1800020e9  jz      short loc_1800020F9
0x1800020eb  mov     rax, [rcx]
0x1800020ee  mov     rax, [rax+10h]
0x1800020f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020f7  mov     eax, ebx
0x1800020f9  mov     rbx, [rsp+28h+arg_0]
0x1800020fe  add     rsp, 20h
0x180002102  pop     rdi
0x180002103  retn
```
