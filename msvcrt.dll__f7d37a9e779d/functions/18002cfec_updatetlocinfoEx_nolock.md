# _updatetlocinfoEx_nolock

- ea: `0x18002cfec`
- end: `0x18002d04e`
- name: `_updatetlocinfoEx_nolock`
- size: `98`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18002c214`
- `0x18002d060`

## callees

- `0x18002bd50`
- `0x18002bdf0`
- `0x18002c15c`
- `0x18002cfec`

## pseudocode

```c
struct threadlocaleinfostruct *__fastcall updatetlocinfoEx_nolock(
        struct threadlocaleinfostruct **a1,
        struct threadlocaleinfostruct *a2)
{
  struct threadlocaleinfostruct *v3; // rbx

  if ( !a2 || !a1 )
    return 0;
  v3 = *a1;
  if ( *a1 != a2 )
  {
    *a1 = a2;
    _addlocaleref(a2);
    if ( v3 )
    {
      _removelocaleref((__int64)v3);
      if ( !v3->refcount && v3 != &_initiallocinfo )
        _freetlocinfo(v3);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x18002cfec  mov     [rsp+arg_0], rbx
0x18002cff1  push    rdi
0x18002cff2  sub     rsp, 20h
0x18002cff6  mov     rdi, rdx
0x18002cff9  test    rdx, rdx
0x18002cffc  jz      short loc_18002D041
0x18002cffe  test    rcx, rcx
0x18002d001  jz      short loc_18002D041
0x18002d003  mov     rbx, [rcx]
0x18002d006  cmp     rbx, rdx
0x18002d009  jz      short loc_18002D03C
0x18002d00b  mov     [rcx], rdx
0x18002d00e  mov     rcx, rdx
0x18002d011  call    __addlocaleref
0x18002d016  test    rbx, rbx
0x18002d019  jz      short loc_18002D03C
0x18002d01b  mov     rcx, rbx
0x18002d01e  call    __removelocaleref
0x18002d023  cmp     dword ptr [rbx], 0
0x18002d026  jnz     short loc_18002D03C
0x18002d028  lea     rax, __initiallocinfo
0x18002d02f  cmp     rbx, rax
0x18002d032  jz      short loc_18002D03C
0x18002d034  mov     rcx, rbx
0x18002d037  call    __freetlocinfo
0x18002d03c  mov     rax, rdi
0x18002d03f  jmp     short loc_18002D043
0x18002d041  xor     eax, eax
0x18002d043  mov     rbx, [rsp+28h+arg_0]
0x18002d048  add     rsp, 20h
0x18002d04c  pop     rdi
0x18002d04d  retn
```
