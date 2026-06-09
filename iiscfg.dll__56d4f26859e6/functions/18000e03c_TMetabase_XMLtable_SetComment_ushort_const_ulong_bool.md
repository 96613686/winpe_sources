# TMetabase_XMLtable::SetComment(ushort const *,ulong,bool)

- ea: `0x18000e03c`
- end: `0x18000e122`
- name: `?SetComment@TMetabase_XMLtable@@AEAAJPEBGK_N@Z`
- size: `230`
- prototype: `int(TMetabase_XMLtable *__hidden this, const unsigned __int16 *, unsigned int, bool)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180006750`

## callees

- `0x18000e03c`
- `0x18002e0b2`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18000e08c`
- `ole32!CoTaskMemAlloc` at `0x18000e08c`
- `ole32!CoTaskMemRealloc` at `0x18000e0d5`
- `ole32!CoTaskMemRealloc` at `0x18000e0d5`

## pseudocode

```c
__int64 __fastcall TMetabase_XMLtable::SetComment(
        TMetabase_XMLtable *this,
        const unsigned __int16 *a2,
        unsigned int a3)
{
  _QWORD *v3; // rbx
  __int64 v4; // r15
  __int64 v5; // rdi
  unsigned int *v6; // rsi
  _WORD *v9; // rax
  _QWORD *v10; // rbp
  _WORD *v11; // rcx
  __int64 v12; // r14
  __int64 v13; // rdx
  _WORD *v14; // rax
  __int64 result; // rax

  v3 = (_QWORD *)((char *)this + 1760);
  v4 = a3;
  v5 = -1;
  v6 = (unsigned int *)((char *)this + 1628);
  if ( *((_QWORD *)this + 220) )
  {
    v10 = (_QWORD *)((char *)this + 1760);
  }
  else
  {
    *v6 = (a3 + 1024) & 0xFFFFFC00;
    v9 = CoTaskMemAlloc(saturated_mul((a3 + 1024) & 0xFFFFFC00, 2u));
    *v3 = v9;
    if ( !v9 )
      return 2147942414LL;
    *v9 = 0;
    v10 = (_QWORD *)((char *)this + 1760);
  }
  v11 = (_WORD *)*v3;
  do
    ++v5;
  while ( v11[v5] );
  v12 = (unsigned int)(v5 + v4);
  if ( (int)v12 + 1 <= *v6 )
  {
    v10 = v3;
  }
  else
  {
    v13 = ((_DWORD)v12 + 1024) & 0xFFFFFC00;
    *v6 = v13;
    v14 = CoTaskMemRealloc(v11, 2 * v13);
    v11 = v14;
    if ( !v14 )
      return 2147942414LL;
    *v3 = v14;
  }
  memcpy_0(&v11[(unsigned int)v5], a2, 2 * v4);
  result = 0;
  *(_WORD *)(*v10 + 2 * v12) = 0;
  return result;
}

```

## disassembly

```asm
0x18000e03c  push    rbx
0x18000e03e  push    rbp
0x18000e03f  push    rsi
0x18000e040  push    rdi
0x18000e041  push    r12
0x18000e043  push    r13
0x18000e045  push    r14
0x18000e047  push    r15
0x18000e049  sub     rsp, 28h
0x18000e04d  lea     rbx, [rcx+6E0h]
0x18000e054  mov     r15d, r8d
0x18000e057  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000e05b  lea     rsi, [rcx+65Ch]
0x18000e062  xor     r13d, r13d
0x18000e065  mov     r12, rdx
0x18000e068  mov     rbp, rcx
0x18000e06b  cmp     [rbx], r13
0x18000e06e  jnz     short loc_18000E0A7
0x18000e070  lea     edx, [r15+400h]
0x18000e077  and     edx, 0FFFFFC00h
0x18000e07d  lea     eax, [rdi+3]
0x18000e080  mov     [rsi], edx
0x18000e082  mul     rdx
0x18000e085  cmovb   rax, rdi
0x18000e089  mov     rcx, rax; cb
0x18000e08c  call    cs:__imp_CoTaskMemAlloc
0x18000e092  mov     [rbx], rax
0x18000e095  test    rax, rax
0x18000e098  jz      short loc_18000E0E3
0x18000e09a  mov     [rax], r13w
0x18000e09e  add     rbp, 6E0h
0x18000e0a5  jmp     short loc_18000E0AA
0x18000e0a7  mov     rbp, rbx
0x18000e0aa  mov     rcx, [rbx]; pv
0x18000e0ad  inc     rdi
0x18000e0b0  cmp     [rcx+rdi*2], r13w
0x18000e0b5  jnz     short loc_18000E0AD
0x18000e0b7  lea     r14d, [rdi+r15]
0x18000e0bb  lea     eax, [r14+1]
0x18000e0bf  cmp     eax, [rsi]
0x18000e0c1  jbe     short loc_18000E0EF
0x18000e0c3  lea     edx, [r14+400h]
0x18000e0ca  and     edx, 0FFFFFC00h
0x18000e0d0  mov     [rsi], edx
0x18000e0d2  add     rdx, rdx; cb
0x18000e0d5  call    cs:__imp_CoTaskMemRealloc
0x18000e0db  mov     rcx, rax
0x18000e0de  test    rax, rax
0x18000e0e1  jnz     short loc_18000E0EA
0x18000e0e3  mov     eax, 8007000Eh
0x18000e0e8  jmp     short loc_18000E111
0x18000e0ea  mov     [rbx], rax
0x18000e0ed  jmp     short loc_18000E0F2
0x18000e0ef  mov     rbp, rbx
0x18000e0f2  mov     eax, edi
0x18000e0f4  mov     r8, r15
0x18000e0f7  add     r8, r8; Size
0x18000e0fa  mov     rdx, r12; Src
0x18000e0fd  lea     rcx, [rcx+rax*2]; void *
0x18000e101  call    memcpy_0
0x18000e106  mov     rcx, [rbp+0]
0x18000e10a  xor     eax, eax
0x18000e10c  mov     [rcx+r14*2], r13w
0x18000e111  add     rsp, 28h
0x18000e115  pop     r15
0x18000e117  pop     r14
0x18000e119  pop     r13
0x18000e11b  pop     r12
0x18000e11d  pop     rdi
0x18000e11e  pop     rsi
0x18000e11f  pop     rbp
0x18000e120  pop     rbx
0x18000e121  retn
```
