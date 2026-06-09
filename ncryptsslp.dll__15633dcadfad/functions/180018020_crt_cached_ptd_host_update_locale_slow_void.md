# __crt_cached_ptd_host::update_locale_slow(void)

- ea: `0x180018020`
- end: `0x1800180a8`
- name: `?update_locale_slow@__crt_cached_ptd_host@@AEAAXXZ`
- size: `136`
- prototype: `void __fastcall(__crt_cached_ptd_host *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18001b1d8`
- `0x18001c26c`
- `0x18001cc4c`

## callees

- `0x180014afc`
- `0x1800150f8`
- `0x180017684`
- `0x1800176f8`
- `0x180018020`

## pseudocode

```c
void __fastcall __crt_cached_ptd_host::update_locale_slow(__crt_cached_ptd_host *this)
{
  __int64 v2; // r8
  __int64 v3; // rsi
  int v4; // eax

  if ( !*(_QWORD *)this && !__crt_cached_ptd_host::force_synchronize_per_thread_data(this) )
    abort();
  v2 = *((_QWORD *)this + 1);
  v3 = *(_QWORD *)this;
  *((_QWORD *)this + 3) = *(_QWORD *)(*(_QWORD *)this + 144LL);
  *((_QWORD *)this + 4) = *(_QWORD *)(v3 + 136);
  _acrt_update_locale_info_explicit(v3, (char *)this + 24, v2);
  _acrt_update_multibyte_info_explicit(v3, (char *)this + 32, *((_QWORD *)this + 1));
  v4 = *(_DWORD *)(v3 + 936);
  if ( (v4 & 2) == 0 )
  {
    *(_DWORD *)(v3 + 936) = v4 | 2;
    *((_BYTE *)this + 40) = 2;
  }
}

```

## disassembly

```asm
0x180018020  push    rdi
0x180018022  sub     rsp, 20h
0x180018026  cmp     qword ptr [rcx], 0
0x18001802a  mov     rdi, rcx
0x18001802d  jnz     short loc_180018039
0x18001802f  call    ?force_synchronize_per_thread_data@__crt_cached_ptd_host@@AEAAPEAU__acrt_ptd@@XZ; __crt_cached_ptd_host::force_synchronize_per_thread_data(void)
0x180018034  test    rax, rax
0x180018037  jz      short loc_1800180A2
0x180018039  mov     r8, [rdi+8]
0x18001803d  lea     rdx, [rdi+18h]
0x180018041  mov     [rsp+28h+arg_0], rbx
0x180018046  mov     [rsp+28h+arg_8], rsi
0x18001804b  mov     rsi, [rdi]
0x18001804e  mov     rcx, rsi
0x180018051  mov     rax, [rsi+90h]
0x180018058  mov     [rdx], rax
0x18001805b  mov     rax, [rsi+88h]
0x180018062  mov     [rdi+20h], rax
0x180018066  call    __acrt_update_locale_info_explicit
0x18001806b  mov     r8, [rdi+8]
0x18001806f  lea     rdx, [rdi+20h]
0x180018073  mov     rcx, rsi
0x180018076  call    __acrt_update_multibyte_info_explicit
0x18001807b  mov     eax, [rsi+3A8h]
0x180018081  mov     rbx, [rsp+28h+arg_0]
0x180018086  test    al, 2
0x180018088  jnz     short loc_180018097
0x18001808a  or      eax, 2
0x18001808d  mov     [rsi+3A8h], eax
0x180018093  mov     byte ptr [rdi+28h], 2
0x180018097  mov     rsi, [rsp+28h+arg_8]
0x18001809c  add     rsp, 20h
0x1800180a0  pop     rdi
0x1800180a1  retn
0x1800180a2  call    abort
```
