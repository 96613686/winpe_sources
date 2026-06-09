# __acrt_update_multibyte_info

- ea: `0x18001b278`
- end: `0x18001b2a9`
- name: `__acrt_update_multibyte_info`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x1800184c4`

## callees

- `0x18001a328`
- `0x18001b278`

## pseudocode

```c
__int64 *__fastcall _acrt_update_multibyte_info(__int64 a1, void **a2)
{
  __int64 *result; // rax

  result = (__int64 *)_acrt_current_multibyte_data;
  if ( *a2 != _acrt_current_multibyte_data )
  {
    result = (__int64 *)*(unsigned int *)(a1 + 936);
    if ( ((unsigned int)result & _globallocalestatus) == 0 )
    {
      result = _acrt_update_thread_multibyte_data();
      *a2 = result;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001b278  push    rbx
0x18001b27a  sub     rsp, 20h
0x18001b27e  mov     rax, cs:__acrt_current_multibyte_data
0x18001b285  mov     rbx, rdx
0x18001b288  cmp     [rdx], rax
0x18001b28b  jz      short loc_18001B2A3
0x18001b28d  mov     eax, [rcx+3A8h]
0x18001b293  test    cs:__globallocalestatus, eax
0x18001b299  jnz     short loc_18001B2A3
0x18001b29b  call    __acrt_update_thread_multibyte_data
0x18001b2a0  mov     [rbx], rax
0x18001b2a3  add     rsp, 20h
0x18001b2a7  pop     rbx
0x18001b2a8  retn
```
