# AMGetWideString

- ea: `0x1800077a8`
- end: `0x180007844`
- name: `AMGetWideString`
- size: `156`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180005890`
- `0x18000c2a0`
- `0x18001ce60`

## callees

- `0x1800077a8`
- `0x18001e5c5`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x18000780e`
- `ole32!CoTaskMemAlloc` at `0x18000780e`

## pseudocode

```c
__int64 __fastcall AMGetWideString(_WORD *Src, _QWORD *a2)
{
  __int64 result; // rax
  _WORD *v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rsi
  void *v8; // rax

  if ( !a2 )
    return 2147500035LL;
  *a2 = 0;
  if ( !Src )
    return 2147942487LL;
  v5 = Src;
  v6 = 50000;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v6;
  }
  while ( v6 );
  result = v6 == 0 ? 0x80070057 : 0;
  if ( v6 )
  {
    v7 = -(__int64)(v6 != 0) & (2 * (50000 - v6));
    v8 = CoTaskMemAlloc(v7 + 2);
    *a2 = v8;
    if ( v8 )
    {
      memcpy_0(v8, Src, v7 + 2);
      return 0;
    }
    else
    {
      return 2147942414LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800077a8  push    rbx
0x1800077aa  push    rbp
0x1800077ab  push    rsi
0x1800077ac  push    rdi
0x1800077ad  sub     rsp, 28h
0x1800077b1  xor     ebp, ebp
0x1800077b3  mov     rdi, rdx
0x1800077b6  mov     rbx, rcx
0x1800077b9  test    rdx, rdx
0x1800077bc  jnz     short loc_1800077C5
0x1800077be  mov     eax, 80004003h
0x1800077c3  jmp     short loc_18000783B
0x1800077c5  mov     [rdx], rbp
0x1800077c8  test    rbx, rbx
0x1800077cb  jz      short loc_180007836
0x1800077cd  mov     edx, 0C350h
0x1800077d2  mov     rax, rbx
0x1800077d5  mov     ecx, edx
0x1800077d7  cmp     [rax], bp
0x1800077da  jz      short loc_1800077E6
0x1800077dc  add     rax, 2
0x1800077e0  sub     rcx, 1
0x1800077e4  jnz     short loc_1800077D7
0x1800077e6  mov     rax, rcx
0x1800077e9  neg     rax
0x1800077ec  sbb     eax, eax
0x1800077ee  not     eax
0x1800077f0  and     eax, 80070057h
0x1800077f5  test    rcx, rcx
0x1800077f8  jz      short loc_18000783B
0x1800077fa  sub     rdx, rcx
0x1800077fd  neg     rcx
0x180007800  sbb     rax, rax
0x180007803  lea     rsi, [rdx+rdx]
0x180007807  and     rsi, rax
0x18000780a  lea     rcx, [rsi+2]; cb
0x18000780e  call    cs:__imp_CoTaskMemAlloc
0x180007814  mov     [rdi], rax
0x180007817  test    rax, rax
0x18000781a  jnz     short loc_180007823
0x18000781c  mov     eax, 8007000Eh
0x180007821  jmp     short loc_18000783B
0x180007823  lea     r8, [rsi+2]; Size
0x180007827  mov     rdx, rbx; Src
0x18000782a  mov     rcx, rax; void *
0x18000782d  call    memcpy_0
0x180007832  xor     eax, eax
0x180007834  jmp     short loc_18000783B
0x180007836  mov     eax, 80070057h
0x18000783b  add     rsp, 28h
0x18000783f  pop     rdi
0x180007840  pop     rsi
0x180007841  pop     rbp
0x180007842  pop     rbx
0x180007843  retn
```
