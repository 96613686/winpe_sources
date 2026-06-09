# _bstr_t::~_bstr_t(void)

- ea: `0x18000ab84`
- end: `0x18000abf0`
- name: `??1_bstr_t@@QEAA@XZ`
- size: `108`
- prototype: `void __fastcall(_bstr_t *this, const struct std::nothrow_t *)`
- caller_count: `12`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000ac08`
- `0x180012664`
- `0x180012ed4`
- `0x180016ca8`
- `0x180018c6c`
- `0x180019560`
- `0x180019abc`
- `0x180019e58`
- `0x18001a25c`
- `0x18001aa50`
- `0x18001b094`
- `0x18001f513`

## callees

- `0x1800026b0`
- `0x18000ab84`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000abae`
- `OLEAUT32!__imp_SysFreeString` at `0x18000abae`

## pseudocode

```c
void __fastcall _bstr_t::~_bstr_t(_bstr_t *this, const struct std::nothrow_t *a2)
{
  __int64 v2; // rbx
  void *v4; // rcx

  v2 = *(_QWORD *)this;
  if ( *(_QWORD *)this )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v2 + 16), 0xFFFFFFFF) == 1 )
    {
      if ( *(_QWORD *)v2 )
      {
        SysFreeString(*(BSTR *)v2);
        *(_QWORD *)v2 = 0;
      }
      v4 = *(void **)(v2 + 8);
      if ( v4 )
      {
        operator delete(v4, a2);
        *(_QWORD *)(v2 + 8) = 0;
      }
      operator delete((void *)v2, (const struct std::nothrow_t *)0x18);
    }
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x18000ab84  mov     [rsp+arg_8], rbx
0x18000ab89  push    rdi
0x18000ab8a  sub     rsp, 20h
0x18000ab8e  mov     rbx, [rcx]
0x18000ab91  mov     rdi, rcx
0x18000ab94  test    rbx, rbx
0x18000ab97  jz      short loc_18000ABE5
0x18000ab99  or      eax, 0FFFFFFFFh
0x18000ab9c  lock xadd [rbx+10h], eax
0x18000aba1  cmp     eax, 1
0x18000aba4  jnz     short loc_18000ABDE
0x18000aba6  mov     rcx, [rbx]; bstrString
0x18000aba9  test    rcx, rcx
0x18000abac  jz      short loc_18000ABBB
0x18000abae  call    cs:__imp_SysFreeString
0x18000abb4  mov     qword ptr [rbx], 0
0x18000abbb  mov     rcx, [rbx+8]; void *
0x18000abbf  test    rcx, rcx
0x18000abc2  jz      short loc_18000ABD1
0x18000abc4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000abc9  mov     qword ptr [rbx+8], 0
0x18000abd1  mov     edx, 18h; struct std::nothrow_t *
0x18000abd6  mov     rcx, rbx; void *
0x18000abd9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000abde  mov     qword ptr [rdi], 0
0x18000abe5  mov     rbx, [rsp+28h+arg_8]
0x18000abea  add     rsp, 20h
0x18000abee  pop     rdi
0x18000abef  retn
```
