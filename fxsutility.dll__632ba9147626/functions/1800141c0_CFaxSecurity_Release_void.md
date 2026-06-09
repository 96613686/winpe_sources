# CFaxSecurity::Release(void)

- ea: `0x1800141c0`
- end: `0x1800141f9`
- name: `?Release@CFaxSecurity@@UEAAKXZ`
- size: `57`
- prototype: `unsigned int __fastcall(CFaxSecurity *__hidden this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800141c0`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall CFaxSecurity::Release(CFaxSecurity *this)
{
  __int64 result; // rax

  result = (unsigned int)_InterlockedDecrement((volatile signed __int32 *)this + 6);
  if ( !(_DWORD)result )
  {
    if ( this )
      (*(void (__fastcall **)(CFaxSecurity *, __int64))(*(_QWORD *)this + 80LL))(this, 1);
    g_pFaxSecurity = 0;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800141c0  sub     rsp, 28h
0x1800141c4  or      eax, 0FFFFFFFFh
0x1800141c7  lock xadd [rcx+18h], eax
0x1800141cc  sub     eax, 1
0x1800141cf  jnz     short loc_1800141F4
0x1800141d1  test    rcx, rcx
0x1800141d4  jz      short loc_1800141E7
0x1800141d6  mov     rax, [rcx]
0x1800141d9  mov     edx, 1
0x1800141de  mov     rax, [rax+50h]
0x1800141e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141e7  mov     cs:?g_pFaxSecurity@@3PEAVCFaxSecurity@@EA, 0; CFaxSecurity * g_pFaxSecurity
0x1800141f2  xor     eax, eax
0x1800141f4  add     rsp, 28h
0x1800141f8  retn
```
