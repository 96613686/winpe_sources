# __acrt_update_multibyte_info

- ea: `0x1800176c0`
- end: `0x1800176f1`
- name: `__acrt_update_multibyte_info`
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

- `0x180016dcc`
- `0x1800176c0`

## pseudocode

```c
__int64 __fastcall _acrt_update_multibyte_info(__int64 a1, __int64 *a2)
{
  __int64 result; // rax

  result = _acrt_current_multibyte_data;
  if ( *a2 != _acrt_current_multibyte_data )
  {
    result = *(unsigned int *)(a1 + 936);
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
0x1800176c0  push    rbx
0x1800176c2  sub     rsp, 20h
0x1800176c6  mov     rax, cs:__acrt_current_multibyte_data
0x1800176cd  mov     rbx, rdx
0x1800176d0  cmp     [rdx], rax
0x1800176d3  jz      short loc_1800176EB
0x1800176d5  mov     eax, [rcx+3A8h]
0x1800176db  test    cs:__globallocalestatus, eax
0x1800176e1  jnz     short loc_1800176EB
0x1800176e3  call    __acrt_update_thread_multibyte_data
0x1800176e8  mov     [rbx], rax
0x1800176eb  add     rsp, 20h
0x1800176ef  pop     rbx
0x1800176f0  retn
```
