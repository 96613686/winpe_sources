# CMSMQQueueInfo::UpdateFormatName(void)

- ea: `0x18001e10c`
- end: `0x18001e196`
- name: `?UpdateFormatName@CMSMQQueueInfo@@IEAAJXZ`
- size: `138`
- prototype: `__int64 __fastcall(CMSMQQueueInfo *__hidden this)`
- caller_count: `6`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18001d0a0`
- `0x18001d410`
- `0x18001da30`
- `0x18001dc10`
- `0x18001e020`
- `0x18001e350`

## callees

- `0x18001e10c`
- `0x1800220b4`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18001e14f`
- `OLEAUT32!__imp_SysStringLen` at `0x18001e14f`

## pseudocode

```c
__int64 __fastcall CMSMQQueueInfo::UpdateFormatName(CMSMQQueueInfo *this)
{
  wchar_t **v1; // rsi
  int FormatNameFromPathName; // ebx
  const WCHAR *v5; // rcx

  v1 = (wchar_t **)((char *)this + 160);
  if ( !*((_QWORD *)this + 22) && !*v1 )
    return 2147942487LL;
  if ( !*((_DWORD *)this + 42) || !*v1 || (FormatNameFromPathName = 0, !SysStringLen(*v1)) )
  {
    v5 = (const WCHAR *)*((_QWORD *)this + 22);
    if ( v5 )
    {
      FormatNameFromPathName = GetFormatNameFromPathName(v5, v1);
      if ( FormatNameFromPathName >= 0 )
        *((_DWORD *)this + 42) = 1;
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  return (unsigned int)FormatNameFromPathName;
}

```

## disassembly

```asm
0x18001e10c  mov     [rsp+arg_0], rbx
0x18001e111  mov     [rsp+arg_8], rsi
0x18001e116  push    rdi
0x18001e117  sub     rsp, 20h
0x18001e11b  cmp     qword ptr [rcx+0B0h], 0
0x18001e123  lea     rsi, [rcx+0A0h]
0x18001e12a  mov     rdi, rcx
0x18001e12d  jnz     short loc_18001E13C
0x18001e12f  cmp     qword ptr [rsi], 0
0x18001e133  jnz     short loc_18001E13C
0x18001e135  mov     eax, 80070057h
0x18001e13a  jmp     short loc_18001E186
0x18001e13c  cmp     dword ptr [rcx+0A8h], 0
0x18001e143  jz      short loc_18001E159
0x18001e145  mov     rcx, [rsi]; pbstr
0x18001e148  test    rcx, rcx
0x18001e14b  jz      short loc_18001E159
0x18001e14d  xor     ebx, ebx
0x18001e14f  call    cs:__imp_SysStringLen
0x18001e155  test    eax, eax
0x18001e157  jnz     short loc_18001E184
0x18001e159  mov     rcx, [rdi+0B0h]; lpwcsPathName
0x18001e160  test    rcx, rcx
0x18001e163  jnz     short loc_18001E16C
0x18001e165  mov     ebx, 80070057h
0x18001e16a  jmp     short loc_18001E184
0x18001e16c  mov     rdx, rsi; wchar_t **
0x18001e16f  call    ?GetFormatNameFromPathName@@YAJPEB_WPEAPEA_W@Z; GetFormatNameFromPathName(wchar_t const *,wchar_t * *)
0x18001e174  mov     ebx, eax
0x18001e176  test    eax, eax
0x18001e178  js      short loc_18001E184
0x18001e17a  mov     dword ptr [rdi+0A8h], 1
0x18001e184  mov     eax, ebx
0x18001e186  mov     rbx, [rsp+28h+arg_0]
0x18001e18b  mov     rsi, [rsp+28h+arg_8]
0x18001e190  add     rsp, 20h
0x18001e194  pop     rdi
0x18001e195  retn
```
