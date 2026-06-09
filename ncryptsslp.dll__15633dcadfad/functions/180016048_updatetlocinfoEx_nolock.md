# _updatetlocinfoEx_nolock

- ea: `0x180016048`
- end: `0x1800160ad`
- name: `_updatetlocinfoEx_nolock`
- size: `101`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180015540`
- `0x180015fd4`

## callees

- `0x180015c80`
- `0x180015d18`
- `0x180015f24`
- `0x180016048`

## pseudocode

```c
__int64 __fastcall updatetlocinfoEx_nolock(__int64 *a1, __int64 a2)
{
  __int64 v3; // rbx

  if ( !a2 || !a1 )
    return 0;
  v3 = *a1;
  if ( *a1 != a2 )
  {
    *a1 = a2;
    _acrt_add_locale_ref(a2);
    if ( v3 )
    {
      _acrt_release_locale_ref(v3);
      if ( !*(_DWORD *)(v3 + 16) && (wchar_t **)v3 != &_acrt_initial_locale_data )
        _acrt_free_locale(v3);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x180016048  mov     [rsp+arg_0], rbx
0x18001604d  push    rdi
0x18001604e  sub     rsp, 20h
0x180016052  mov     rdi, rdx
0x180016055  test    rdx, rdx
0x180016058  jz      short loc_1800160A0
0x18001605a  test    rcx, rcx
0x18001605d  jz      short loc_1800160A0
0x18001605f  mov     rbx, [rcx]
0x180016062  cmp     rbx, rdx
0x180016065  jnz     short loc_18001606C
0x180016067  mov     rax, rdi
0x18001606a  jmp     short loc_1800160A2
0x18001606c  mov     [rcx], rdi
0x18001606f  mov     rcx, rdi
0x180016072  call    __acrt_add_locale_ref
0x180016077  test    rbx, rbx
0x18001607a  jz      short loc_180016067
0x18001607c  mov     rcx, rbx
0x18001607f  call    __acrt_release_locale_ref
0x180016084  cmp     dword ptr [rbx+10h], 0
0x180016088  jnz     short loc_180016067
0x18001608a  lea     rax, __acrt_initial_locale_data
0x180016091  cmp     rbx, rax
0x180016094  jz      short loc_180016067
0x180016096  mov     rcx, rbx
0x180016099  call    __acrt_free_locale
0x18001609e  jmp     short loc_180016067
0x1800160a0  xor     eax, eax
0x1800160a2  mov     rbx, [rsp+28h+arg_0]
0x1800160a7  add     rsp, 20h
0x1800160ab  pop     rdi
0x1800160ac  retn
```
