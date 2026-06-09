# _bstr_t::~_bstr_t(void)

- ea: `0x180005344`
- end: `0x1800053ad`
- name: `??1_bstr_t@@QEAA@XZ`
- size: `105`
- prototype: `void __fastcall(_bstr_t *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180005500`
- `0x180009eb4`
- `0x180009ec6`

## callees

- `0x180005344`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180005395`
- `msvcrt!??3@YAXPEAX@Z` at `0x180005395`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180005384`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180005384`
- `OLEAUT32!__imp_SysFreeString` at `0x18000536e`
- `OLEAUT32!__imp_SysFreeString` at `0x18000536e`

## pseudocode

```c
void __fastcall _bstr_t::~_bstr_t(_bstr_t *this)
{
  __int64 v1; // rbx
  void *v3; // rcx

  v1 = *(_QWORD *)this;
  if ( *(_QWORD *)this )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 16), 0xFFFFFFFF) == 1 )
    {
      if ( *(_QWORD *)v1 )
      {
        SysFreeString(*(BSTR *)v1);
        *(_QWORD *)v1 = 0;
      }
      v3 = *(void **)(v1 + 8);
      if ( v3 )
      {
        operator delete[](v3);
        *(_QWORD *)(v1 + 8) = 0;
      }
      operator delete((void *)v1);
    }
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x180005344  mov     [rsp+arg_8], rbx
0x180005349  push    rdi
0x18000534a  sub     rsp, 20h
0x18000534e  mov     rbx, [rcx]
0x180005351  mov     rdi, rcx
0x180005354  test    rbx, rbx
0x180005357  jz      short loc_1800053A2
0x180005359  or      eax, 0FFFFFFFFh
0x18000535c  lock xadd [rbx+10h], eax
0x180005361  cmp     eax, 1
0x180005364  jnz     short loc_18000539B
0x180005366  mov     rcx, [rbx]; bstrString
0x180005369  test    rcx, rcx
0x18000536c  jz      short loc_18000537B
0x18000536e  call    cs:__imp_SysFreeString
0x180005374  mov     qword ptr [rbx], 0
0x18000537b  mov     rcx, [rbx+8]
0x18000537f  test    rcx, rcx
0x180005382  jz      short loc_180005392
0x180005384  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18000538a  mov     qword ptr [rbx+8], 0
0x180005392  mov     rcx, rbx
0x180005395  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000539b  mov     qword ptr [rdi], 0
0x1800053a2  mov     rbx, [rsp+28h+arg_8]
0x1800053a7  add     rsp, 20h
0x1800053ab  pop     rdi
0x1800053ac  retn
```
