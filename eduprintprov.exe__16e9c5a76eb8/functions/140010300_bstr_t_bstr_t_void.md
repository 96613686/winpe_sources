# _bstr_t::~_bstr_t(void)

- ea: `0x140010300`
- end: `0x14001036c`
- name: `??1_bstr_t@@QEAA@XZ`
- size: `108`
- prototype: `void __fastcall(_bstr_t *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x14000fa88`
- `0x140010384`
- `0x1400136a3`
- `0x140013744`

## callees

- `0x140002624`
- `0x140010300`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x14001032a`
- `OLEAUT32!__imp_SysFreeString` at `0x14001032a`

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
        operator delete(v3);
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
0x140010300  mov     [rsp+arg_8], rbx
0x140010305  push    rdi
0x140010306  sub     rsp, 20h
0x14001030a  mov     rbx, [rcx]
0x14001030d  mov     rdi, rcx
0x140010310  test    rbx, rbx
0x140010313  jz      short loc_140010361
0x140010315  or      eax, 0FFFFFFFFh
0x140010318  lock xadd [rbx+10h], eax
0x14001031d  cmp     eax, 1
0x140010320  jnz     short loc_14001035A
0x140010322  mov     rcx, [rbx]; bstrString
0x140010325  test    rcx, rcx
0x140010328  jz      short loc_140010337
0x14001032a  call    cs:__imp_SysFreeString
0x140010330  mov     qword ptr [rbx], 0
0x140010337  mov     rcx, [rbx+8]; void *
0x14001033b  test    rcx, rcx
0x14001033e  jz      short loc_14001034D
0x140010340  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140010345  mov     qword ptr [rbx+8], 0
0x14001034d  mov     edx, 18h; unsigned __int64
0x140010352  mov     rcx, rbx; void *
0x140010355  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14001035a  mov     qword ptr [rdi], 0
0x140010361  mov     rbx, [rsp+28h+arg_8]
0x140010366  add     rsp, 20h
0x14001036a  pop     rdi
0x14001036b  retn
```
