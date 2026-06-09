# _updatetlocinfoEx_nolock

- ea: `0x18001b89c`
- end: `0x18001b904`
- name: `_updatetlocinfoEx_nolock`
- size: `104`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18001b480`
- `0x18001b82c`

## callees

- `0x18001b4f8`
- `0x18001b584`
- `0x18001b784`
- `0x18001b89c`

## pseudocode

```c
__int64 __fastcall updatetlocinfoEx_nolock(__int64 *a1, __int64 a2)
{
  __int64 v3; // rbx

  if ( !a2 || !a1 )
    return 0;
  v3 = *a1;
  if ( *a1 == a2 )
    return a2;
  *a1 = a2;
  _acrt_add_locale_ref(a2);
  if ( v3 )
  {
    _acrt_release_locale_ref(v3);
    if ( !*(_DWORD *)(v3 + 16) && (wchar_t **)v3 != &_acrt_initial_locale_data )
      _acrt_free_locale(v3);
  }
  return a2;
}

```

## disassembly

```asm
0x18001b89c  mov     [rsp+arg_0], rbx
0x18001b8a1  push    rdi
0x18001b8a2  sub     rsp, 20h
0x18001b8a6  mov     rdi, rdx
0x18001b8a9  test    rdx, rdx
0x18001b8ac  jz      short loc_18001B8F7
0x18001b8ae  test    rcx, rcx
0x18001b8b1  jz      short loc_18001B8F7
0x18001b8b3  mov     rbx, [rcx]
0x18001b8b6  cmp     rbx, rdx
0x18001b8b9  jnz     short loc_18001B8C0
0x18001b8bb  mov     rax, rdx
0x18001b8be  jmp     short loc_18001B8F9
0x18001b8c0  mov     [rcx], rdx
0x18001b8c3  mov     rcx, rdx
0x18001b8c6  call    __acrt_add_locale_ref
0x18001b8cb  test    rbx, rbx
0x18001b8ce  jz      short loc_18001B8F2
0x18001b8d0  mov     rcx, rbx
0x18001b8d3  call    __acrt_release_locale_ref
0x18001b8d8  cmp     dword ptr [rbx+10h], 0
0x18001b8dc  jnz     short loc_18001B8F2
0x18001b8de  lea     rax, __acrt_initial_locale_data
0x18001b8e5  cmp     rbx, rax
0x18001b8e8  jz      short loc_18001B8F2
0x18001b8ea  mov     rcx, rbx
0x18001b8ed  call    __acrt_free_locale
0x18001b8f2  mov     rax, rdi
0x18001b8f5  jmp     short loc_18001B8F9
0x18001b8f7  xor     eax, eax
0x18001b8f9  mov     rbx, [rsp+28h+arg_0]
0x18001b8fe  add     rsp, 20h
0x18001b902  pop     rdi
0x18001b903  retn
```
