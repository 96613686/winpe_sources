# CLangTagStack::Push(HtmlTokenType,int,ulong)

- ea: `0x180006834`
- end: `0x18000690c`
- name: `?Push@CLangTagStack@@QEAAXW4HtmlTokenType@@HK@Z`
- size: `216`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180006a10`
- `0x180008690`

## callees

- `0x180006834`
- `0x180014154`
- `0x180014544`
- `0x18001457c`
- `0x180023388`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CLangTagStack::Push(__int64 a1, int a2, int a3, int a4)
{
  _DWORD *v8; // r14
  int v9; // eax
  unsigned int v10; // edi
  void *v11; // rbx

  v8 = operator new(0x10u);
  *v8 = a2;
  v8[1] = 0;
  v8[2] = a3;
  v8[3] = a4;
  v9 = *(_DWORD *)(a1 + 20);
  if ( *(_DWORD *)(a1 + 16) == v9 )
  {
    v10 = 16;
    if ( v9 )
      v10 = 2 * v9;
    v11 = operator new[](saturated_mul(v10, 8u));
    memcpy_0(v11, *(const void **)(a1 + 8), 8LL * *(unsigned int *)(a1 + 20));
    operator delete(*(void **)(a1 + 8));
    *(_QWORD *)(a1 + 8) = v11;
    *(_DWORD *)(a1 + 20) = v10;
  }
  *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8LL * (unsigned int)(*(_DWORD *)(a1 + 16))++) = v8;
  if ( a3 )
    *(_DWORD *)a1 = *(_DWORD *)(a1 + 16) - 1;
  operator delete(0);
}

```

## disassembly

```asm
0x180006834  mov     [rsp+arg_8], rbx
0x180006839  mov     [rsp+arg_10], rbp
0x18000683e  push    rsi
0x18000683f  push    rdi
0x180006840  push    r14
0x180006842  sub     rsp, 20h
0x180006846  mov     edi, r9d
0x180006849  mov     ebp, r8d
0x18000684c  mov     ebx, edx
0x18000684e  mov     rsi, rcx
0x180006851  mov     ecx, 10h; Size
0x180006856  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000685b  mov     r14, rax
0x18000685e  mov     [rax], ebx
0x180006860  mov     dword ptr [rax+4], 0
0x180006867  mov     [rax+8], ebp
0x18000686a  mov     [rax+0Ch], edi
0x18000686d  mov     [rsp+38h+arg_0], rax
0x180006872  mov     eax, [rsi+14h]
0x180006875  cmp     [rsi+10h], eax
0x180006878  jz      short loc_1800068B1
0x18000687a  mov     ecx, [rsi+10h]
0x18000687d  mov     rax, [rsi+8]
0x180006881  mov     [rax+rcx*8], r14
0x180006885  inc     dword ptr [rsi+10h]
0x180006888  test    ebp, ebp
0x18000688a  jz      short loc_180006893
0x18000688c  mov     eax, [rsi+10h]
0x18000688f  dec     eax
0x180006891  mov     [rsi], eax
0x180006893  mov     edx, 10h
0x180006898  xor     ecx, ecx; Block
0x18000689a  mov     rbx, [rsp+38h+arg_8]
0x18000689f  mov     rbp, [rsp+38h+arg_10]
0x1800068a4  add     rsp, 20h
0x1800068a8  pop     r14
0x1800068aa  pop     rdi
0x1800068ab  pop     rsi
0x1800068ac  jmp     ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800068b1  test    eax, eax
0x1800068b3  mov     edi, 10h
0x1800068b8  jz      short loc_1800068BD
0x1800068ba  lea     edi, [rax+rax]
0x1800068bd  mov     ecx, edi
0x1800068bf  mov     eax, 8
0x1800068c4  mul     rcx
0x1800068c7  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800068ce  cmovb   rax, rcx
0x1800068d2  mov     rcx, rax; unsigned __int64
0x1800068d5  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800068da  mov     rbx, rax
0x1800068dd  mov     r8d, [rsi+14h]
0x1800068e1  shl     r8, 3; Size
0x1800068e5  mov     rdx, [rsi+8]; Src
0x1800068e9  mov     rcx, rax; void *
0x1800068ec  call    memcpy_0
0x1800068f1  mov     edx, 8
0x1800068f6  mov     rcx, [rsi+8]; Block
0x1800068fa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800068ff  mov     [rsi+8], rbx
0x180006903  mov     [rsi+14h], edi
0x180006906  jmp     loc_18000687A
```
