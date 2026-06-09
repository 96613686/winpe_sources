# __acrt_update_thread_locale_data

- ea: `0x18001b82c`
- end: `0x18001b89c`
- name: `__acrt_update_thread_locale_data`
- size: `112`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18001b244`

## callees

- `0x1800183f4`
- `0x1800189e4`
- `0x180018bd8`
- `0x180018c38`
- `0x18001b82c`
- `0x18001b89c`

## pseudocode

```c
__int64 _acrt_update_thread_locale_data()
{
  __int64 v0; // rax
  __int64 v1; // rdi
  __int64 v2; // rbx

  v0 = _acrt_getptd();
  v1 = v0;
  if ( (_globallocalestatus & *(_DWORD *)(v0 + 936)) == 0 || (v2 = *(_QWORD *)(v0 + 144)) == 0 )
  {
    _acrt_lock(4);
    v2 = updatetlocinfoEx_nolock(v1 + 144, _acrt_current_locale_data);
    _acrt_unlock(4);
    if ( !v2 )
      abort();
  }
  return v2;
}

```

## disassembly

```asm
0x18001b82c  mov     [rsp+arg_0], rbx
0x18001b831  push    rdi
0x18001b832  sub     rsp, 20h
0x18001b836  call    __acrt_getptd
0x18001b83b  mov     rdi, rax
0x18001b83e  mov     ecx, cs:__globallocalestatus
0x18001b844  test    [rax+3A8h], ecx
0x18001b84a  jz      short loc_18001B858
0x18001b84c  mov     rbx, [rax+90h]
0x18001b853  test    rbx, rbx
0x18001b856  jnz     short loc_18001B88E
0x18001b858  mov     ecx, 4
0x18001b85d  call    __acrt_lock
0x18001b862  nop
0x18001b863  lea     rcx, [rdi+90h]
0x18001b86a  mov     rdx, cs:__acrt_current_locale_data
0x18001b871  call    _updatetlocinfoEx_nolock
0x18001b876  mov     rbx, rax
0x18001b879  mov     ecx, 4
0x18001b87e  call    __acrt_unlock
0x18001b883  test    rbx, rbx
0x18001b886  jnz     short loc_18001B88E
0x18001b888  call    abort
0x18001b88e  mov     rax, rbx
0x18001b891  mov     rbx, [rsp+28h+arg_0]
0x18001b896  add     rsp, 20h
0x18001b89a  pop     rdi
0x18001b89b  retn
0x18001f7e1  push    rbp
0x18001f7e3  sub     rsp, 20h
0x18001f7e7  mov     rbp, rdx
0x18001f7ea  mov     ecx, 4
0x18001f7ef  add     rsp, 20h
0x18001f7f3  pop     rbp
0x18001f7f4  jmp     __acrt_unlock
```
