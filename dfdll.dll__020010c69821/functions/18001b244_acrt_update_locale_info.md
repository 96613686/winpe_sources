# __acrt_update_locale_info

- ea: `0x18001b244`
- end: `0x18001b275`
- name: `__acrt_update_locale_info`
- size: `49`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800184c4`
- `0x18001b4c8`

## callees

- `0x18001b244`
- `0x18001b82c`

## pseudocode

```c
__int64 __fastcall _acrt_update_locale_info(__int64 a1, __int64 *a2)
{
  __int64 result; // rax

  result = _acrt_current_locale_data;
  if ( *a2 != _acrt_current_locale_data )
  {
    result = *(unsigned int *)(a1 + 936);
    if ( ((unsigned int)result & _globallocalestatus) == 0 )
    {
      result = _acrt_update_thread_locale_data();
      *a2 = result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001b244  push    rbx
0x18001b246  sub     rsp, 20h
0x18001b24a  mov     rax, cs:__acrt_current_locale_data
0x18001b251  mov     rbx, rdx
0x18001b254  cmp     [rdx], rax
0x18001b257  jz      short loc_18001B26F
0x18001b259  mov     eax, [rcx+3A8h]
0x18001b25f  test    cs:__globallocalestatus, eax
0x18001b265  jnz     short loc_18001B26F
0x18001b267  call    __acrt_update_thread_locale_data
0x18001b26c  mov     [rbx], rax
0x18001b26f  add     rsp, 20h
0x18001b273  pop     rbx
0x18001b274  retn
```
