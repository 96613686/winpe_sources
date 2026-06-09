# CComBase::NDRelease(void)

- ea: `0x180008ec0`
- end: `0x180008ef1`
- name: `?NDRelease@CComBase@@UEAAKXZ`
- size: `49`
- prototype: `unsigned int __fastcall(CComBase *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180008ec0`
- `0x18002b010`

## pseudocode

```c
__int64 __fastcall CComBase::NDRelease(CComBase *this)
{
  __int64 result; // rax

  result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)this + 4);
  if ( !(_DWORD)result )
  {
    ++*((_DWORD *)this + 4);
    (*(void (__fastcall **)(CComBase *))(*(_QWORD *)this + 24LL))(this);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180008ec0  sub     rsp, 28h
0x180008ec4  or      eax, 0FFFFFFFFh
0x180008ec7  lock xadd [rcx+10h], eax
0x180008ecc  sub     eax, 1
0x180008ecf  jnz     short loc_180008EEC
0x180008ed1  mov     eax, [rcx+10h]
0x180008ed4  mov     edx, 1
0x180008ed9  add     eax, edx
0x180008edb  mov     [rcx+10h], eax
0x180008ede  mov     rax, [rcx]
0x180008ee1  mov     rax, [rax+18h]
0x180008ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008eea  xor     eax, eax
0x180008eec  add     rsp, 28h
0x180008ef0  retn
```
