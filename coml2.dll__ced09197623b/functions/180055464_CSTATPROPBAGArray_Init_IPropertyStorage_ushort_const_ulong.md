# CSTATPROPBAGArray::Init(IPropertyStorage *,ushort const *,ulong)

- ea: `0x180055464`
- end: `0x18005551b`
- name: `?Init@CSTATPROPBAGArray@@QEAAJPEAUIPropertyStorage@@PEBGK@Z`
- size: `183`
- prototype: `int(CSTATPROPBAGArray *__hidden this, struct IPropertyStorage *, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800553c4`

## callees

- `0x180055464`
- `0x18006141c`
- `0x180062010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800554b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800554b9`

## pseudocode

```c
__int64 __fastcall CSTATPROPBAGArray::Init(
        CSTATPROPBAGArray *this,
        struct IPropertyStorage *a2,
        const unsigned __int16 *a3,
        int a4)
{
  __int64 v8; // rax
  SIZE_T v9; // rbx
  void *v10; // rax
  int v11; // ebx

  (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 2) + 24LL))(*((_QWORD *)this + 2), 0xFFFFFFFFLL);
  *((_DWORD *)this + 8) = a4;
  if ( a3 )
  {
    v8 = -1;
    do
      ++v8;
    while ( a3[v8] );
    v9 = (unsigned int)(2 * v8 + 2);
    v10 = CoTaskMemAlloc(v9);
    *((_QWORD *)this + 3) = v10;
    if ( !v10 )
    {
      v11 = -2147024882;
      goto LABEL_11;
    }
    memcpy_0(v10, a3, v9);
  }
  else
  {
    *((_QWORD *)this + 3) = 0;
  }
  if ( !a2
    || (v11 = ((__int64 (__fastcall *)(struct IPropertyStorage *, char *))a2->lpVtbl->Enum)(a2, (char *)this + 8),
        v11 >= 0) )
  {
    v11 = 0;
  }
LABEL_11:
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 32LL))(*((_QWORD *)this + 2));
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180055464  push    rbx
0x180055466  push    rbp
0x180055467  push    rsi
0x180055468  push    rdi
0x180055469  push    r14
0x18005546b  sub     rsp, 20h
0x18005546f  mov     rdi, rcx
0x180055472  mov     rsi, rdx
0x180055475  mov     rcx, [rcx+10h]
0x180055479  or      edx, 0FFFFFFFFh
0x18005547c  mov     ebx, r9d
0x18005547f  mov     rbp, r8
0x180055482  mov     rax, [rcx]
0x180055485  mov     rax, [rax+18h]
0x180055489  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005548e  xor     r14d, r14d
0x180055491  mov     [rdi+20h], ebx
0x180055494  test    rbp, rbp
0x180055497  jnz     short loc_18005549F
0x180055499  mov     [rdi+18h], r14
0x18005549d  jmp     short loc_1800554DD
0x18005549f  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800554a3  inc     rax
0x1800554a6  cmp     [rbp+rax*2+0], r14w
0x1800554ac  jnz     short loc_1800554A3
0x1800554ae  lea     eax, ds:2[rax*2]
0x1800554b5  mov     ecx, eax; cb
0x1800554b7  mov     ebx, eax
0x1800554b9  call    cs:__imp_CoTaskMemAlloc
0x1800554bf  mov     [rdi+18h], rax
0x1800554c3  test    rax, rax
0x1800554c6  jnz     short loc_1800554CF
0x1800554c8  mov     ebx, 8007000Eh
0x1800554cd  jmp     short loc_1800554FE
0x1800554cf  mov     r8, rbx; Size
0x1800554d2  mov     rdx, rbp; Src
0x1800554d5  mov     rcx, rax; void *
0x1800554d8  call    memcpy_0
0x1800554dd  test    rsi, rsi
0x1800554e0  jz      short loc_1800554FB
0x1800554e2  mov     rax, [rsi]
0x1800554e5  lea     rdx, [rdi+8]
0x1800554e9  mov     rcx, rsi
0x1800554ec  mov     rax, [rax+58h]
0x1800554f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800554f5  mov     ebx, eax
0x1800554f7  test    eax, eax
0x1800554f9  js      short loc_1800554FE
0x1800554fb  mov     ebx, r14d
0x1800554fe  mov     rcx, [rdi+10h]
0x180055502  mov     rax, [rcx]
0x180055505  mov     rax, [rax+20h]
0x180055509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005550e  mov     eax, ebx
0x180055510  add     rsp, 20h
0x180055514  pop     r14
0x180055516  pop     rdi
0x180055517  pop     rsi
0x180055518  pop     rbp
0x180055519  pop     rbx
0x18005551a  retn
```
