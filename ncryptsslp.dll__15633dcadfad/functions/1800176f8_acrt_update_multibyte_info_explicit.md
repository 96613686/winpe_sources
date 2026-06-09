# __acrt_update_multibyte_info_explicit

- ea: `0x1800176f8`
- end: `0x18001772d`
- name: `__acrt_update_multibyte_info_explicit`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180018020`

## callees

- `0x180016dcc`
- `0x1800176f8`

## pseudocode

```c
__int64 *__fastcall _acrt_update_multibyte_info_explicit(__int64 a1, __int64 **a2, __int64 a3)
{
  __int64 *result; // rax

  result = (__int64 *)_acrt_current_multibyte_data[a3];
  if ( *a2 != result )
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
0x1800176f8  push    rbx
0x1800176fa  sub     rsp, 20h
0x1800176fe  lea     rax, __acrt_current_multibyte_data
0x180017705  mov     rbx, rdx
0x180017708  mov     rax, [rax+r8*8]
0x18001770c  cmp     [rdx], rax
0x18001770f  jz      short loc_180017727
0x180017711  mov     eax, [rcx+3A8h]
0x180017717  test    cs:__globallocalestatus, eax
0x18001771d  jnz     short loc_180017727
0x18001771f  call    __acrt_update_thread_multibyte_data
0x180017724  mov     [rbx], rax
0x180017727  add     rsp, 20h
0x18001772b  pop     rbx
0x18001772c  retn
```
