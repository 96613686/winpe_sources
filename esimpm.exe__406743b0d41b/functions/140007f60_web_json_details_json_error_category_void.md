# web::json::details::json_error_category(void)

- ea: `0x140007f60`
- end: `0x140007fc2`
- name: `?json_error_category@details@json@web@@YAAEBVjson_error_category_impl@123@XZ`
- size: `98`
- prototype: `const struct web::json::details::json_error_category_impl *__fastcall(web::json::details *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400098a0`
- `0x140009db0`
- `0x140009f80`
- `0x14000a3c0`

## callees

- `0x140003218`
- `0x140007f60`
- `0x14000cfd0`
- `0x14000d038`

## pseudocode

```c
void ***__fastcall web::json::details::json_error_category(web::json::details *this)
{
  if ( dword_140075994 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 4LL) )
  {
    Init_thread_header(&dword_140075994);
    if ( dword_140075994 == -1 )
    {
      atexit(web::json::details::json_error_category_::_2_::_dynamic_atexit_destructor_for__instance__);
      Init_thread_footer(&dword_140075994);
    }
  }
  return &off_140075000;
}

```

## disassembly

```asm
0x140007f60  sub     rsp, 28h
0x140007f64  mov     ecx, cs:_tls_index
0x140007f6a  mov     rax, gs:58h
0x140007f73  mov     edx, 4
0x140007f78  mov     rax, [rax+rcx*8]
0x140007f7c  mov     eax, [rdx+rax]
0x140007f7f  cmp     cs:dword_140075994, eax
0x140007f85  jg      short loc_140007F93
0x140007f87  lea     rax, off_140075000
0x140007f8e  add     rsp, 28h
0x140007f92  retn
0x140007f93  lea     rcx, dword_140075994
0x140007f9a  call    _Init_thread_header
0x140007f9f  cmp     cs:dword_140075994, 0FFFFFFFFh
0x140007fa6  jnz     short loc_140007F87
0x140007fa8  lea     rcx, _web__json__details__json_error_category____2____dynamic_atexit_destructor_for__instance__; void (__cdecl *)()
0x140007faf  call    atexit
0x140007fb4  lea     rcx, dword_140075994
0x140007fbb  call    _Init_thread_footer
0x140007fc0  jmp     short loc_140007F87
```
