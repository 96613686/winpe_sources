# Microsoft::WRL::ClassFactory<IClassFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::AddRef(void)

- ea: `0x180001f40`
- end: `0x180001f94`
- name: `?AddRef@?$ClassFactory@UIClassFactory@@VNil@Details@WRL@Microsoft@@V2345@$0A@@WRL@Microsoft@@UEAAKXZ`
- size: `84`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001e50`
- `0x180003a80`

## callees

- `0x180001f40`
- `0x180006010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ClassFactory<IClassFactory,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::AddRef(
        __int64 a1)
{
  signed __int32 v1; // eax
  unsigned int v2; // ebx

  v1 = *(_DWORD *)(a1 + 20);
  if ( v1 == 0x7FFFFFFF )
  {
LABEL_4:
    v2 = 0x7FFFFFFF;
  }
  else
  {
    while ( 1 )
    {
      v2 = v1 + 1;
      if ( v1 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 20), v1 + 1, v1) )
        break;
      v1 = *(_DWORD *)(a1 + 20);
      if ( v1 == 0x7FFFFFFF )
        goto LABEL_4;
    }
  }
  if ( (*(_BYTE *)(a1 + 28) & 6) == 0 && v2 == 2 && Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  return v2;
}

```

## disassembly

```asm
0x180001f40  push    rbx
0x180001f42  sub     rsp, 20h
0x180001f46  mov     eax, [rcx+14h]
0x180001f49  cmp     eax, 7FFFFFFFh
0x180001f4e  jz      short loc_180001F64
0x180001f50  lea     ebx, [rax+1]
0x180001f53  lock cmpxchg [rcx+14h], ebx
0x180001f58  jz      short loc_180001F69
0x180001f5a  mov     eax, [rcx+14h]
0x180001f5d  cmp     eax, 7FFFFFFFh
0x180001f62  jnz     short loc_180001F50
0x180001f64  mov     ebx, 7FFFFFFFh
0x180001f69  test    byte ptr [rcx+1Ch], 6
0x180001f6d  jnz     short loc_180001F8C
0x180001f6f  cmp     ebx, 2
0x180001f72  jnz     short loc_180001F8C
0x180001f74  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180001f7b  test    rcx, rcx
0x180001f7e  jz      short loc_180001F8C
0x180001f80  mov     rdx, [rcx]
0x180001f83  mov     rax, [rdx+8]
0x180001f87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180001f8c  mov     eax, ebx
0x180001f8e  add     rsp, 20h
0x180001f92  pop     rbx
0x180001f93  retn
```
