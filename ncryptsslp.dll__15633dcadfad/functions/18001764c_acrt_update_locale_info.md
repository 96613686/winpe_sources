# __acrt_update_locale_info

- ea: `0x18001764c`
- end: `0x18001767d`
- name: `__acrt_update_locale_info`
- size: `49`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180016668`
- `0x180018170`
- `0x180018400`

## callees

- `0x180015fd4`
- `0x18001764c`

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
0x18001764c  push    rbx
0x18001764e  sub     rsp, 20h
0x180017652  mov     rax, cs:__acrt_current_locale_data
0x180017659  mov     rbx, rdx
0x18001765c  cmp     [rdx], rax
0x18001765f  jz      short loc_180017677
0x180017661  mov     eax, [rcx+3A8h]
0x180017667  test    cs:__globallocalestatus, eax
0x18001766d  jnz     short loc_180017677
0x18001766f  call    __acrt_update_thread_locale_data
0x180017674  mov     [rbx], rax
0x180017677  add     rsp, 20h
0x18001767b  pop     rbx
0x18001767c  retn
```
