# CADMCOMW::OpenKey(ulong,ushort const *,ulong,ulong,ulong *)

- ea: `0x180007ee0`
- end: `0x180007f37`
- name: `?OpenKey@CADMCOMW@@UEAAJKPEBGKKPEAK@Z`
- size: `87`
- prototype: `__int64 __fastcall(CADMCOMW *__hidden this, unsigned int, wchar_t *Str, unsigned int, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006c0c`
- `0x180007ee0`
- `0x180007f40`

## pseudocode

```c
__int64 __fastcall CADMCOMW::OpenKey(
        CADMCOMW *this,
        unsigned int a2,
        wchar_t *Str,
        unsigned int a4,
        unsigned int a5,
        unsigned int *a6)
{
  __int64 result; // rax

  if ( *((_DWORD *)this + 42) )
    return CADMCOMW::OpenKeyHelper(this, a2, Str, a4, a5, a6);
  result = CADMCOMW::InitializeCallerWatch((char *)this);
  if ( (int)result >= 0 )
    return CADMCOMW::OpenKeyHelper(this, a2, Str, a4, a5, a6);
  return result;
}

```

## disassembly

```asm
0x180007ee0  push    rbx
0x180007ee2  push    rbp
0x180007ee3  push    rsi
0x180007ee4  push    rdi
0x180007ee5  sub     rsp, 38h
0x180007ee9  cmp     dword ptr [rcx+0A8h], 0
0x180007ef0  mov     edi, r9d
0x180007ef3  mov     rsi, r8
0x180007ef6  mov     ebp, edx
0x180007ef8  mov     rbx, rcx
0x180007efb  jnz     short loc_180007F06
0x180007efd  call    ?InitializeCallerWatch@CADMCOMW@@AEAAJXZ; CADMCOMW::InitializeCallerWatch(void)
0x180007f02  test    eax, eax
0x180007f04  js      short loc_180007F2E
0x180007f06  mov     rax, [rsp+58h+arg_28]
0x180007f0e  mov     r9d, edi; unsigned int
0x180007f11  mov     [rsp+58h+var_30], rax; unsigned int *
0x180007f16  mov     r8, rsi; Str
0x180007f19  mov     eax, [rsp+58h+arg_20]
0x180007f20  mov     edx, ebp; unsigned int
0x180007f22  mov     rcx, rbx; this
0x180007f25  mov     [rsp+58h+var_38], eax; unsigned int
0x180007f29  call    ?OpenKeyHelper@CADMCOMW@@QEAAJKPEBGKKPEAK@Z; CADMCOMW::OpenKeyHelper(ulong,ushort const *,ulong,ulong,ulong *)
0x180007f2e  add     rsp, 38h
0x180007f32  pop     rdi
0x180007f33  pop     rsi
0x180007f34  pop     rbp
0x180007f35  pop     rbx
0x180007f36  retn
```
