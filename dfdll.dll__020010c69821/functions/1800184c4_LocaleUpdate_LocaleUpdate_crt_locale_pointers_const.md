# _LocaleUpdate::_LocaleUpdate(__crt_locale_pointers * const)

- ea: `0x1800184c4`
- end: `0x180018554`
- name: `??0_LocaleUpdate@@QEAA@QEAU__crt_locale_pointers@@@Z`
- size: `144`
- prototype: `_LocaleUpdate *__fastcall(_LocaleUpdate *__hidden this, struct __crt_locale_pointers *const)`
- caller_count: `7`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180019e4c`
- `0x18001a690`
- `0x18001b0f4`
- `0x18001bf90`
- `0x18001c028`
- `0x18001c538`
- `0x18001cbd8`

## callees

- `0x1800184c4`
- `0x1800189e4`
- `0x18001b244`
- `0x18001b278`

## pseudocode

```c
_LocaleUpdate *__fastcall _LocaleUpdate::_LocaleUpdate(_LocaleUpdate *this, struct __crt_locale_pointers *const a2)
{
  __int128 v3; // xmm0
  __int64 v4; // rax
  int v5; // eax

  *((_BYTE *)this + 24) = 0;
  if ( a2 )
  {
    v3 = (__int128)*a2;
LABEL_5:
    *(_OWORD *)((char *)this + 8) = v3;
    return this;
  }
  if ( !_acrt_locale_changed_data )
  {
    v3 = *(_OWORD *)&_acrt_initial_locale_pointers;
    goto LABEL_5;
  }
  v4 = _acrt_getptd();
  *(_QWORD *)this = v4;
  *((_QWORD *)this + 1) = *(_QWORD *)(v4 + 144);
  *((_QWORD *)this + 2) = *(_QWORD *)(v4 + 136);
  _acrt_update_locale_info(v4);
  _acrt_update_multibyte_info(*(_QWORD *)this, (char *)this + 16);
  v5 = *(_DWORD *)(*(_QWORD *)this + 936LL);
  if ( (v5 & 2) == 0 )
  {
    *(_DWORD *)(*(_QWORD *)this + 936LL) = v5 | 2;
    *((_BYTE *)this + 24) = 1;
  }
  return this;
}

```

## disassembly

```asm
0x1800184c4  mov     [rsp+arg_0], rbx
0x1800184c9  push    rdi
0x1800184ca  sub     rsp, 20h
0x1800184ce  mov     byte ptr [rcx+18h], 0
0x1800184d2  mov     rdi, rcx
0x1800184d5  test    rdx, rdx
0x1800184d8  jz      short loc_1800184DF
0x1800184da  movups  xmm0, xmmword ptr [rdx]
0x1800184dd  jmp     short loc_1800184F0
0x1800184df  mov     eax, cs:__acrt_locale_changed_data
0x1800184e5  test    eax, eax
0x1800184e7  jnz     short loc_1800184F7
0x1800184e9  movups  xmm0, xmmword ptr cs:__acrt_initial_locale_pointers
0x1800184f0  movdqu  xmmword ptr [rcx+8], xmm0
0x1800184f5  jmp     short loc_180018546
0x1800184f7  call    __acrt_getptd
0x1800184fc  mov     [rdi], rax
0x1800184ff  lea     rdx, [rdi+8]
0x180018503  mov     rcx, [rax+90h]
0x18001850a  mov     [rdx], rcx
0x18001850d  mov     rcx, [rax+88h]
0x180018514  mov     [rdi+10h], rcx
0x180018518  mov     rcx, rax
0x18001851b  call    __acrt_update_locale_info
0x180018520  mov     rcx, [rdi]
0x180018523  lea     rdx, [rdi+10h]
0x180018527  call    __acrt_update_multibyte_info
0x18001852c  mov     rcx, [rdi]
0x18001852f  mov     eax, [rcx+3A8h]
0x180018535  test    al, 2
0x180018537  jnz     short loc_180018546
0x180018539  or      eax, 2
0x18001853c  mov     [rcx+3A8h], eax
0x180018542  mov     byte ptr [rdi+18h], 1
0x180018546  mov     rax, rdi
0x180018549  mov     rbx, [rsp+28h+arg_0]
0x18001854e  add     rsp, 20h
0x180018552  pop     rdi
0x180018553  retn
```
