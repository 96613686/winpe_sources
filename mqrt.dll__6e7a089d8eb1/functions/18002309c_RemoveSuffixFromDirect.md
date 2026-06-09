# RemoveSuffixFromDirect

- ea: `0x18002309c`
- end: `0x1800231e3`
- name: `RemoveSuffixFromDirect`
- size: `327`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800222c0`

## callees

- `0x1800022d6`
- `0x1800087f8`
- `0x1800092c0`
- `0x18000d74c`
- `0x18001ec80`
- `0x180021010`
- `0x18002309c`

## import_xrefs

- `msvcrt!free` at `0x1800231ba`
- `msvcrt!free` at `0x1800231c9`
- `msvcrt!free` at `0x1800231ba`
- `msvcrt!free` at `0x1800231c9`
- `msvcrt!wcschr` at `0x1800230bc`
- `msvcrt!wcschr` at `0x1800230bc`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall RemoveSuffixFromDirect(const wchar_t **a1, void **a2)
{
  wchar_t *v4; // rax
  unsigned __int64 v5; // rbp
  wchar_t *v6; // rbx
  int v7; // eax
  _BYTE pExceptionObject[56]; // [rsp+20h] [rbp-38h] BYREF

  v4 = wcschr(*a1, 0x3Bu);
  if ( !v4 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2));
    bad_document::bad_document((bad_document *)pExceptionObject, &Class);
    throw (bad_format_name *)pExceptionObject;
  }
  v5 = v4 - *a1;
  v6 = (wchar_t *)MmAllocate(saturated_mul(v5 + 1, 2u));
  v7 = StringCchCopyNW(v6, v5 + 1, *a1, v5);
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        21,
        WPP_46d7352ff4ed31571a117a62feb2004e_Traceguids,
        (unsigned int)v7);
    bad_document::bad_document((bad_document *)pExceptionObject, &Class);
    throw (bad_format_name *)pExceptionObject;
  }
  if ( *a2 )
    free(*a2);
  *a2 = v6;
  *a1 = v6;
  free(0);
}

```

## disassembly

```asm
0x18002309c  mov     [rsp+arg_0], rbx
0x1800230a1  mov     [rsp+arg_8], rbp
0x1800230a6  push    rsi
0x1800230a7  push    rdi
0x1800230a8  push    r14
0x1800230aa  sub     rsp, 40h
0x1800230ae  mov     r14, rdx
0x1800230b1  mov     rsi, rcx
0x1800230b4  mov     edx, 3Bh ; ';'; Ch
0x1800230b9  mov     rcx, [rcx]; Str
0x1800230bc  call    cs:__imp_wcschr
0x1800230c2  mov     rbp, rax
0x1800230c5  test    rax, rax
0x1800230c8  jnz     short loc_18002311C
0x1800230ca  lea     rax, WPP_GLOBAL_Control
0x1800230d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800230d8  cmp     rcx, rax
0x1800230db  jz      short loc_1800230F9
0x1800230dd  test    byte ptr [rcx+1Ch], 1
0x1800230e1  jz      short loc_1800230F9
0x1800230e3  lea     edx, [rbp+14h]
0x1800230e6  mov     r9, [rsi]
0x1800230e9  lea     r8, WPP_46d7352ff4ed31571a117a62feb2004e_Traceguids
0x1800230f0  mov     rcx, [rcx+10h]; LoggerHandle
0x1800230f4  call    WPP_SF_S
0x1800230f9  lea     rdx, Class; wchar_t *
0x180023100  lea     rcx, [rsp+58h+pExceptionObject]; this
0x180023105  call    ??0bad_document@@QEAA@PEB_W@Z; bad_document::bad_document(wchar_t const *)
0x18002310a  lea     rdx, _TI2?AVbad_format_name@@; pThrowInfo
0x180023111  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x180023116  call    _CxxThrowException_0
0x18002311c  sub     rbp, [rsi]
0x18002311f  sar     rbp, 1
0x180023122  lea     rdi, [rbp+1]
0x180023126  mov     eax, 2
0x18002312b  mul     rdi
0x18002312e  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180023135  cmovb   rax, rcx
0x180023139  mov     rcx, rax; unsigned __int64
0x18002313c  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x180023141  mov     rbx, rax
0x180023144  mov     [rsp+58h+arg_10], rax
0x180023149  mov     r9, rbp; unsigned __int64
0x18002314c  mov     r8, [rsi]; wchar_t *
0x18002314f  mov     rdx, rdi; unsigned __int64
0x180023152  mov     rcx, rax; wchar_t *
0x180023155  call    ?StringCchCopyNW@@YAJPEA_W_KPEB_W1@Z; StringCchCopyNW(wchar_t *,unsigned __int64,wchar_t const *,unsigned __int64)
0x18002315a  mov     r9d, eax
0x18002315d  test    eax, eax
0x18002315f  jns     short loc_1800231B2
0x180023161  lea     rax, WPP_GLOBAL_Control
0x180023168  mov     rcx, cs:WPP_GLOBAL_Control
0x18002316f  cmp     rcx, rax
0x180023172  jz      short loc_18002318F
0x180023174  test    byte ptr [rcx+1Ch], 1
0x180023178  jz      short loc_18002318F
0x18002317a  mov     edx, 15h
0x18002317f  lea     r8, WPP_46d7352ff4ed31571a117a62feb2004e_Traceguids
0x180023186  mov     rcx, [rcx+10h]
0x18002318a  call    WPP_SF_d
0x18002318f  lea     rdx, Class; wchar_t *
0x180023196  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18002319b  call    ??0bad_document@@QEAA@PEB_W@Z; bad_document::bad_document(wchar_t const *)
0x1800231a0  lea     rdx, _TI2?AVbad_format_name@@; pThrowInfo
0x1800231a7  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800231ac  call    _CxxThrowException_0
0x1800231b2  mov     rcx, [r14]; Block
0x1800231b5  test    rcx, rcx
0x1800231b8  jz      short loc_1800231C1
0x1800231ba  call    cs:__imp_free
0x1800231c0  nop
0x1800231c1  mov     [r14], rbx
0x1800231c4  mov     [rsi], rbx
0x1800231c7  xor     ecx, ecx; Block
0x1800231c9  call    cs:__imp_free
0x1800231cf  nop
0x1800231d0  mov     rbx, [rsp+58h+arg_0]
0x1800231d5  mov     rbp, [rsp+58h+arg_8]
0x1800231da  add     rsp, 40h
0x1800231de  pop     r14
0x1800231e0  pop     rdi
0x1800231e1  pop     rsi
0x1800231e2  retn
```
