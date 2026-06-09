# __acrt_update_thread_locale_data

- ea: `0x180015fd4`
- end: `0x180016042`
- name: `__acrt_update_thread_locale_data`
- size: `110`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x18001764c`
- `0x180017684`

## callees

- `0x1800150f8`
- `0x1800153dc`
- `0x180015fd4`
- `0x180016048`
- `0x1800160b4`
- `0x1800160d4`

## pseudocode

```c
__int64 _acrt_update_thread_locale_data()
{
  __int64 v0; // rax
  __int64 *v1; // rdi
  __int64 v2; // rbx

  v0 = _acrt_getptd();
  v1 = (__int64 *)(v0 + 144);
  if ( (*(_DWORD *)(v0 + 936) & _globallocalestatus) == 0 || (v2 = *v1) == 0 )
  {
    _acrt_lock(4);
    v2 = updatetlocinfoEx_nolock(v1, _acrt_current_locale_data);
    _acrt_unlock(4);
    if ( !v2 )
      abort();
  }
  return v2;
}

```

## disassembly

```asm
0x180015fd4  mov     [rsp+arg_0], rbx
0x180015fd9  push    rdi
0x180015fda  sub     rsp, 20h
0x180015fde  call    __acrt_getptd
0x180015fe3  lea     rdi, [rax+90h]
0x180015fea  mov     ecx, [rax+3A8h]
0x180015ff0  mov     eax, cs:__globallocalestatus
0x180015ff6  test    eax, ecx
0x180015ff8  jz      short loc_180016002
0x180015ffa  mov     rbx, [rdi]
0x180015ffd  test    rbx, rbx
0x180016000  jnz     short loc_18001602E
0x180016002  mov     ecx, 4
0x180016007  call    __acrt_lock
0x18001600c  nop
0x18001600d  mov     rdx, cs:__acrt_current_locale_data
0x180016014  mov     rcx, rdi
0x180016017  call    _updatetlocinfoEx_nolock
0x18001601c  mov     rbx, rax
0x18001601f  mov     ecx, 4
0x180016024  call    __acrt_unlock
0x180016029  test    rbx, rbx
0x18001602c  jz      short loc_18001603C
0x18001602e  mov     rax, rbx
0x180016031  mov     rbx, [rsp+28h+arg_0]
0x180016036  add     rsp, 20h
0x18001603a  pop     rdi
0x18001603b  retn
0x18001603c  call    abort
0x180025c3d  push    rbp
0x180025c3f  sub     rsp, 20h
0x180025c43  mov     rbp, rdx
0x180025c46  mov     ecx, 4
0x180025c4b  add     rsp, 20h
0x180025c4f  pop     rbp
0x180025c50  jmp     __acrt_unlock
```
