# CComObjectStackRefCount<CURL>::~CComObjectStackRefCount<CURL>(void)

- ea: `0x18000e89c`
- end: `0x18000e8d6`
- name: `??1?$CComObjectStackRefCount@VCURL@@@@QEAA@XZ`
- size: `58`
- prototype: `void __fastcall(CURL *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180022cc8`
- `0x180026aff`

## callees

- `0x180007078`
- `0x18000e7fc`
- `0x18000e89c`

## string_xrefs

- `0x18000e8bb`: `onecoreuap\base\appmodel\Search\common\include\atlext.hxx`

## pseudocode

```c
void __fastcall CComObjectStackRefCount<CURL>::~CComObjectStackRefCount<CURL>(CURL *a1)
{
  int v1; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_QWORD *)a1 = &CComObjectStackRefCount<CURL>::`vftable';
  if ( *((_DWORD *)a1 + 2) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x30B,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\atlext.hxx",
      (const char *)0x8000FFFFLL,
      v1);
  CURL::~CURL(a1);
}

```

## disassembly

```asm
0x18000e89c  sub     rsp, 28h
0x18000e8a0  lea     rax, ??_7?$CComObjectStackRefCount@VCURL@@@@6B@; const CComObjectStackRefCount<CURL>::`vftable'
0x18000e8a7  mov     [rcx], rax
0x18000e8aa  cmp     dword ptr [rcx+8], 0
0x18000e8ae  jz      short loc_18000E8CD
0x18000e8b0  mov     rcx, [rsp+28h]; this
0x18000e8b5  mov     r9d, 8000FFFFh; char *
0x18000e8bb  lea     r8, aOnecoreuapBase_15; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18000e8c2  mov     edx, 30Bh; void *
0x18000e8c7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000e8cd  add     rsp, 28h
0x18000e8d1  jmp     ??1CURL@@QEAA@XZ; CURL::~CURL(void)
```
