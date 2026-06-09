# replace_current_thread_locale_nolock

- ea: `0x18001536c`
- end: `0x1800153d3`
- name: `replace_current_thread_locale_nolock`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18001519c`

## callees

- `0x18001536c`
- `0x180015c80`
- `0x180015d18`
- `0x180015f24`

## pseudocode

```c
wchar_t **__fastcall replace_current_thread_locale_nolock(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  wchar_t **result; // rax
  __int64 v6; // rcx

  v4 = *(_QWORD *)(a1 + 144);
  if ( v4 )
  {
    result = (wchar_t **)_acrt_release_locale_ref(v4);
    v6 = *(_QWORD *)(a1 + 144);
    if ( v6 != _acrt_current_locale_data )
    {
      result = &_acrt_initial_locale_data;
      if ( (wchar_t **)v6 != &_acrt_initial_locale_data && !*(_DWORD *)(v6 + 16) )
        result = (wchar_t **)_acrt_free_locale(v6);
    }
  }
  *(_QWORD *)(a1 + 144) = a2;
  if ( a2 )
    return (wchar_t **)_acrt_add_locale_ref(a2);
  return result;
}

```

## disassembly

```asm
0x18001536c  mov     [rsp+arg_0], rbx
0x180015371  push    rdi
0x180015372  sub     rsp, 20h
0x180015376  mov     rdi, rcx
0x180015379  mov     rbx, rdx
0x18001537c  mov     rcx, [rcx+90h]
0x180015383  test    rcx, rcx
0x180015386  jz      short loc_1800153B4
0x180015388  call    __acrt_release_locale_ref
0x18001538d  mov     rcx, [rdi+90h]
0x180015394  cmp     rcx, cs:__acrt_current_locale_data
0x18001539b  jz      short loc_1800153B4
0x18001539d  lea     rax, __acrt_initial_locale_data
0x1800153a4  cmp     rcx, rax
0x1800153a7  jz      short loc_1800153B4
0x1800153a9  cmp     dword ptr [rcx+10h], 0
0x1800153ad  jnz     short loc_1800153B4
0x1800153af  call    __acrt_free_locale
0x1800153b4  mov     [rdi+90h], rbx
0x1800153bb  test    rbx, rbx
0x1800153be  jz      short loc_1800153C8
0x1800153c0  mov     rcx, rbx
0x1800153c3  call    __acrt_add_locale_ref
0x1800153c8  mov     rbx, [rsp+28h+arg_0]
0x1800153cd  add     rsp, 20h
0x1800153d1  pop     rdi
0x1800153d2  retn
```
