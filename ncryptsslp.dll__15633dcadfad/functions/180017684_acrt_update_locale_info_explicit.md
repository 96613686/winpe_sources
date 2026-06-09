# __acrt_update_locale_info_explicit

- ea: `0x180017684`
- end: `0x1800176b9`
- name: `__acrt_update_locale_info_explicit`
- size: `53`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180018020`

## callees

- `0x180015fd4`
- `0x180017684`

## pseudocode

```c
__int64 __fastcall _acrt_update_locale_info_explicit(__int64 a1, __int64 *a2, __int64 a3)
{
  __int64 result; // rax

  result = _acrt_current_locale_data[a3];
  if ( *a2 != result )
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
0x180017684  push    rbx
0x180017686  sub     rsp, 20h
0x18001768a  lea     rax, __acrt_current_locale_data
0x180017691  mov     rbx, rdx
0x180017694  mov     rax, [rax+r8*8]
0x180017698  cmp     [rdx], rax
0x18001769b  jz      short loc_1800176B3
0x18001769d  mov     eax, [rcx+3A8h]
0x1800176a3  test    cs:__globallocalestatus, eax
0x1800176a9  jnz     short loc_1800176B3
0x1800176ab  call    __acrt_update_thread_locale_data
0x1800176b0  mov     [rbx], rax
0x1800176b3  add     rsp, 20h
0x1800176b7  pop     rbx
0x1800176b8  retn
```
