# TMetabase_XMLtable::TLocation::TLocation(ushort const *,ulong)

- ea: `0x18000540c`
- end: `0x1800054b1`
- name: `??0TLocation@TMetabase_XMLtable@@QEAA@PEBGK@Z`
- size: `165`
- prototype: `_QWORD(TMetabase_XMLtable::TLocation *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x180006310`

## callees

- `0x18000540c`
- `0x18002df9b`
- `0x18002e0b2`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180005460`
- `ole32!CoTaskMemAlloc` at `0x180005460`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
TMetabase_XMLtable::TLocation *__fastcall TMetabase_XMLtable::TLocation::TLocation(
        TMetabase_XMLtable::TLocation *this,
        const unsigned __int16 *a2,
        int a3)
{
  __int64 v5; // rax
  void *v6; // rcx
  int pExceptionObject; // [rsp+40h] [rbp+18h] BYREF

  *(_QWORD *)this = 0;
  *((_DWORD *)this + 2) = 1;
  *((_DWORD *)this + 3) = a3;
  if ( a2 )
  {
    v5 = -1;
    do
      ++v5;
    while ( a2[v5] );
    *((_DWORD *)this + 4) = v5;
    v6 = CoTaskMemAlloc(saturated_mul((unsigned int)(v5 + 1), 2u));
    *(_QWORD *)this = v6;
    if ( !v6 )
    {
      pExceptionObject = -2147024882;
      throw (long *)&pExceptionObject;
    }
    memcpy_0(v6, a2, 2LL * (unsigned int)(*((_DWORD *)this + 4) + 1));
  }
  return this;
}

```

## disassembly

```asm
0x18000540c  mov     [rsp+arg_8], rbx
0x180005411  mov     [rsp+arg_18], rsi
0x180005416  mov     [rsp+arg_0], rcx
0x18000541b  push    rdi
0x18000541c  sub     rsp, 20h
0x180005420  mov     rdi, rdx
0x180005423  mov     rbx, rcx
0x180005426  xor     esi, esi
0x180005428  mov     [rcx], rsi
0x18000542b  mov     dword ptr [rcx+8], 1
0x180005432  mov     [rcx+0Ch], r8d
0x180005436  test    rdx, rdx
0x180005439  jz      short loc_18000549E
0x18000543b  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000543f  mov     rax, r8
0x180005442  inc     rax
0x180005445  cmp     [rdx+rax*2], si
0x180005449  jnz     short loc_180005442
0x18000544b  mov     [rcx+10h], eax
0x18000544e  lea     ecx, [rax+1]
0x180005451  mov     eax, 2
0x180005456  mul     rcx
0x180005459  cmovb   rax, r8
0x18000545d  mov     rcx, rax; cb
0x180005460  call    cs:__imp_CoTaskMemAlloc
0x180005466  mov     rcx, rax; void *
0x180005469  mov     [rbx], rax
0x18000546c  test    rax, rax
0x18000546f  jnz     short loc_18000548B
0x180005471  mov     [rsp+28h+pExceptionObject], 8007000Eh
0x180005479  lea     rdx, _TI1J; pThrowInfo
0x180005480  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180005485  call    _CxxThrowException_0
0x18000548b  mov     r8d, [rbx+10h]
0x18000548f  inc     r8d
0x180005492  add     r8, r8; Size
0x180005495  mov     rdx, rdi; Src
0x180005498  call    memcpy_0
0x18000549d  nop
0x18000549e  mov     rax, rbx
0x1800054a1  mov     rbx, [rsp+28h+arg_8]
0x1800054a6  mov     rsi, [rsp+28h+arg_18]
0x1800054ab  add     rsp, 20h
0x1800054af  pop     rdi
0x1800054b0  retn
```
