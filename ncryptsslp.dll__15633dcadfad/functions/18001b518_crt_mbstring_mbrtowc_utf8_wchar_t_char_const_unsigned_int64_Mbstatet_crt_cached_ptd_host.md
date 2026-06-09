# __crt_mbstring::__mbrtowc_utf8(wchar_t *,char const *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)

- ea: `0x18001b518`
- end: `0x18001b562`
- name: `?__mbrtowc_utf8@__crt_mbstring@@YA_KPEA_WPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z`
- size: `74`
- prototype: `unsigned __int64 __fastcall(__crt_mbstring *__hidden this, wchar_t *, const char *, unsigned __int64, struct _Mbstatet *, struct __crt_cached_ptd_host *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18001b1d8`

## callees

- `0x18001b378`
- `0x18001b518`

## pseudocode

```c
unsigned __int64 __fastcall __crt_mbstring::__mbrtowc_utf8(
        __crt_mbstring *this,
        char32_t *a2,
        struct __crt_cached_ptd_host *a3,
        __int64 *a4,
        struct _Mbstatet *a5)
{
  unsigned __int64 result; // rax
  __int16 v7; // cx
  unsigned int v8[6]; // [rsp+30h] [rbp-18h] BYREF

  v8[0] = 0;
  result = __crt_mbstring::__mbrtoc32_utf8((unsigned __int64)v8, a2, a3, a4, a5);
  if ( result <= 4 )
  {
    v7 = v8[0];
    if ( v8[0] > 0xFFFF )
      v7 = -3;
    if ( this )
      *(_WORD *)this = v7;
  }
  return result;
}

```

## disassembly

```asm
0x18001b518  push    rbx
0x18001b51a  sub     rsp, 40h
0x18001b51e  mov     rax, [rsp+48h+arg_20]
0x18001b523  mov     rbx, rcx
0x18001b526  lea     rcx, [rsp+48h+var_18]; this
0x18001b52b  mov     [rsp+48h+var_28], rax; struct _Mbstatet *
0x18001b530  mov     [rsp+48h+var_18], 0
0x18001b538  call    ?__mbrtoc32_utf8@__crt_mbstring@@YA_KPEA_UPEBD_KPEAU_Mbstatet@@AEAV__crt_cached_ptd_host@@@Z; __crt_mbstring::__mbrtoc32_utf8(char32_t *,char const *,unsigned __int64,_Mbstatet *,__crt_cached_ptd_host &)
0x18001b53d  cmp     rax, 4
0x18001b541  ja      short loc_18001B55C
0x18001b543  mov     ecx, [rsp+48h+var_18]
0x18001b547  cmp     ecx, 0FFFFh
0x18001b54d  jbe     short loc_18001B554
0x18001b54f  mov     ecx, 0FFFDh
0x18001b554  test    rbx, rbx
0x18001b557  jz      short loc_18001B55C
0x18001b559  mov     [rbx], cx
0x18001b55c  add     rsp, 40h
0x18001b560  pop     rbx
0x18001b561  retn
```
