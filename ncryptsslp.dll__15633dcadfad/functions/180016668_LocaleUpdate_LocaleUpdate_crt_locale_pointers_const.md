# _LocaleUpdate::_LocaleUpdate(__crt_locale_pointers * const)

- ea: `0x180016668`
- end: `0x180016703`
- name: `??0_LocaleUpdate@@QEAA@QEAU__crt_locale_pointers@@@Z`
- size: `155`
- prototype: `_LocaleUpdate *__fastcall(_LocaleUpdate *__hidden this, struct __crt_locale_pointers *const)`
- caller_count: `4`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18001670c`
- `0x1800173e4`
- `0x180017f64`
- `0x1800187c8`

## callees

- `0x1800153dc`
- `0x180016668`
- `0x18001764c`
- `0x1800176c0`

## pseudocode

```c
_LocaleUpdate *__fastcall _LocaleUpdate::_LocaleUpdate(_LocaleUpdate *this, struct __crt_locale_pointers *const a2)
{
  _OWORD *v3; // rsi
  __int128 v4; // xmm0
  __int64 v5; // rax
  int v6; // eax

  *((_BYTE *)this + 24) = 0;
  v3 = (_OWORD *)((char *)this + 8);
  if ( a2 )
  {
    v4 = (__int128)*a2;
LABEL_5:
    *v3 = v4;
    return this;
  }
  if ( !_acrt_locale_changed_data )
  {
    v4 = *(_OWORD *)&_acrt_initial_locale_pointers;
    goto LABEL_5;
  }
  v5 = _acrt_getptd();
  *(_QWORD *)this = v5;
  *(_QWORD *)v3 = *(_QWORD *)(v5 + 144);
  *((_QWORD *)this + 2) = *(_QWORD *)(v5 + 136);
  _acrt_update_locale_info(v5, v3);
  _acrt_update_multibyte_info(*(_QWORD *)this, (char *)this + 16);
  v6 = *(_DWORD *)(*(_QWORD *)this + 936LL);
  if ( (v6 & 2) == 0 )
  {
    *(_DWORD *)(*(_QWORD *)this + 936LL) = v6 | 2;
    *((_BYTE *)this + 24) = 1;
  }
  return this;
}

```

## disassembly

```asm
0x180016668  mov     [rsp+arg_0], rbx
0x18001666d  mov     [rsp+arg_8], rsi
0x180016672  push    rdi
0x180016673  sub     rsp, 20h
0x180016677  mov     byte ptr [rcx+18h], 0
0x18001667b  mov     rdi, rcx
0x18001667e  lea     rsi, [rcx+8]
0x180016682  test    rdx, rdx
0x180016685  jz      short loc_18001668C
0x180016687  movups  xmm0, xmmword ptr [rdx]
0x18001668a  jmp     short loc_18001669C
0x18001668c  cmp     cs:__acrt_locale_changed_data, 0
0x180016693  jnz     short loc_1800166A2
0x180016695  movups  xmm0, xmmword ptr cs:__acrt_initial_locale_pointers
0x18001669c  movdqu  xmmword ptr [rsi], xmm0
0x1800166a0  jmp     short loc_1800166F0
0x1800166a2  call    __acrt_getptd
0x1800166a7  mov     [rdi], rax
0x1800166aa  mov     rdx, rsi
0x1800166ad  mov     rcx, [rax+90h]
0x1800166b4  mov     [rsi], rcx
0x1800166b7  mov     rcx, [rax+88h]
0x1800166be  mov     [rdi+10h], rcx
0x1800166c2  mov     rcx, rax
0x1800166c5  call    __acrt_update_locale_info
0x1800166ca  mov     rcx, [rdi]
0x1800166cd  lea     rdx, [rdi+10h]
0x1800166d1  call    __acrt_update_multibyte_info
0x1800166d6  mov     rcx, [rdi]
0x1800166d9  mov     eax, [rcx+3A8h]
0x1800166df  test    al, 2
0x1800166e1  jnz     short loc_1800166F0
0x1800166e3  or      eax, 2
0x1800166e6  mov     [rcx+3A8h], eax
0x1800166ec  mov     byte ptr [rdi+18h], 1
0x1800166f0  mov     rbx, [rsp+28h+arg_0]
0x1800166f5  mov     rax, rdi
0x1800166f8  mov     rsi, [rsp+28h+arg_8]
0x1800166fd  add     rsp, 20h
0x180016701  pop     rdi
0x180016702  retn
```
