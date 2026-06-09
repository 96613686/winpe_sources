# std::unique_ptr<uus::Session,std::default_delete<uus::Session>>::reset(uus::Session *)

- ea: `0x180003558`
- end: `0x18000357f`
- name: `?reset@?$unique_ptr@USession@uus@@U?$default_delete@USession@uus@@@std@@@std@@QEAAXPEAUSession@uus@@@Z`
- size: `39`
- prototype: `__int64 __fastcall(__int64 (__fastcall ****)(_QWORD, __int64), __int64 (__fastcall ***)(_QWORD, __int64))`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003448`

## callees

- `0x180003558`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall std::unique_ptr<uus::Session>::reset(
        __int64 (__fastcall ****a1)(_QWORD, __int64),
        __int64 (__fastcall ***a2)(_QWORD, __int64))
{
  __int64 (__fastcall ***v2)(_QWORD, __int64); // r8
  __int64 result; // rax

  v2 = *a1;
  *a1 = a2;
  if ( v2 )
    return (**v2)(v2, 1);
  return result;
}

```

## disassembly

```asm
0x180003558  sub     rsp, 28h
0x18000355c  mov     r8, [rcx]
0x18000355f  mov     [rcx], rdx
0x180003562  test    r8, r8
0x180003565  jz      short loc_18000357A
0x180003567  mov     rax, [r8]
0x18000356a  mov     edx, 1
0x18000356f  mov     rcx, r8
0x180003572  mov     rax, [rax]
0x180003575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000357a  add     rsp, 28h
0x18000357e  retn
```
