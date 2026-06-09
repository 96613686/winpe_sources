# _bstr_t::~_bstr_t(void)

- ea: `0x1800076dc`
- end: `0x180007745`
- name: `??1_bstr_t@@QEAA@XZ`
- size: `105`
- prototype: `void __fastcall(_bstr_t *__hidden this)`
- caller_count: `40`
- callee_count: `1`
- tags: ``

## callers

- `0x1800079fc`
- `0x180007fb4`
- `0x1800081b8`
- `0x1800086c8`
- `0x1800093cc`
- `0x180009af8`
- `0x18000a4a0`
- `0x18000b210`
- `0x18000bf74`
- `0x18000c000`
- `0x18000e6ba`
- `0x18000e79a`
- `0x18000e7ac`
- `0x18000e7be`
- `0x18000e7d0`
- `0x18000e7e2`
- `0x18000e7f4`
- `0x18000e806`
- `0x18000e818`
- `0x18000e82a`
- `0x18000e83c`
- `0x18000e86e`
- `0x18000e8a0`
- `0x18000e8d2`
- `0x18000e904`
- `0x18000e939`
- `0x18000ea07`
- `0x18000ea19`
- `0x18000ea3d`
- `0x18000ea4f`
- `0x18000ea61`
- `0x18000ea73`
- `0x18000eab7`
- `0x18000eae9`
- `0x18000eb1b`
- `0x18000eb4d`
- `0x18000eb82`
- `0x18000ec98`
- `0x18000ed43`
- `0x18000eda6`

## callees

- `0x1800076dc`

## import_xrefs

- `msvcrt!free` at `0x18000771c`
- `msvcrt!free` at `0x18000772d`
- `msvcrt!free` at `0x18000771c`
- `msvcrt!free` at `0x18000772d`
- `OLEAUT32!__imp_SysFreeString` at `0x180007706`
- `OLEAUT32!__imp_SysFreeString` at `0x180007706`

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
        free(v3);
        *(_QWORD *)(v1 + 8) = 0;
      }
      free((void *)v1);
    }
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x1800076dc  mov     [rsp+arg_8], rbx
0x1800076e1  push    rdi
0x1800076e2  sub     rsp, 20h
0x1800076e6  mov     rbx, [rcx]
0x1800076e9  mov     rdi, rcx
0x1800076ec  test    rbx, rbx
0x1800076ef  jz      short loc_18000773A
0x1800076f1  or      eax, 0FFFFFFFFh
0x1800076f4  lock xadd [rbx+10h], eax
0x1800076f9  cmp     eax, 1
0x1800076fc  jnz     short loc_180007733
0x1800076fe  mov     rcx, [rbx]; bstrString
0x180007701  test    rcx, rcx
0x180007704  jz      short loc_180007713
0x180007706  call    cs:__imp_SysFreeString
0x18000770c  mov     qword ptr [rbx], 0
0x180007713  mov     rcx, [rbx+8]; Block
0x180007717  test    rcx, rcx
0x18000771a  jz      short loc_18000772A
0x18000771c  call    cs:__imp_free
0x180007722  mov     qword ptr [rbx+8], 0
0x18000772a  mov     rcx, rbx; Block
0x18000772d  call    cs:__imp_free
0x180007733  mov     qword ptr [rdi], 0
0x18000773a  mov     rbx, [rsp+28h+arg_8]
0x18000773f  add     rsp, 20h
0x180007743  pop     rdi
0x180007744  retn
```
