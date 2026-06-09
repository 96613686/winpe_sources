# ATL::CAtlArray<ATL::CComQIPtr<IUnknown,&_GUID const IID_IUnknown>,ATL::CComQIPtrElementTraits<IUnknown,&_GUID const IID_IUnknown>>::GrowBuffer(unsigned __int64)

- ea: `0x18001b744`
- end: `0x18001b80c`
- name: `?GrowBuffer@?$CAtlArray@V?$CComQIPtr@UIUnknown@@$1?IID_IUnknown@@3U_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIUnknown@@$1?IID_IUnknown@@3U_GUID@@B@2@@ATL@@AEAA_N_K@Z`
- size: `200`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180018e28`
- `0x18001def4`

## callees

- `0x18000be84`
- `0x18001b744`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x18001b7dd`
- `api-ms-win-crt-string-l1-1-0!memmove_s` at `0x18001b7dd`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18001b77f`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18001b7ba`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18001b77f`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x18001b7ba`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001b7ed`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18001b7ed`

## pseudocode

```c
char __fastcall ATL::CAtlArray<ATL::CComQIPtr<IUnknown,&_GUID const IID_IUnknown>,ATL::CComQIPtrElementTraits<IUnknown,&_GUID const IID_IUnknown>>::GrowBuffer(
        __int64 a1,
        size_t a2)
{
  size_t v4; // rdx
  size_t v5; // rcx
  void *v6; // rax
  void *v7; // rax
  void *v8; // rsi
  errno_t v10; // eax

  v4 = *(_QWORD *)(a1 + 16);
  if ( a2 <= v4 )
    return 1;
  v5 = *(int *)(a1 + 24);
  if ( !*(_QWORD *)a1 )
  {
    if ( v5 > a2 )
      a2 = v5;
    v6 = calloc(a2, 8u);
    *(_QWORD *)a1 = v6;
    if ( v6 )
      goto LABEL_15;
    return 0;
  }
  if ( !v5 )
  {
    v5 = v4 >> 1;
    if ( a2 - v4 > v4 >> 1 )
      v5 = a2 - v4;
  }
  if ( a2 < v4 + v5 )
    a2 = v4 + v5;
  v7 = calloc(a2, 8u);
  v8 = v7;
  if ( !v7 )
    return 0;
  v10 = memmove_s(v7, 8LL * *(_QWORD *)(a1 + 8), *(const void *const *)a1, 8LL * *(_QWORD *)(a1 + 8));
  ATL::AtlCrtErrorCheck(v10);
  free(*(void **)a1);
  *(_QWORD *)a1 = v8;
LABEL_15:
  *(_QWORD *)(a1 + 16) = a2;
  return 1;
}

```

## disassembly

```asm
0x18001b744  mov     [rsp+arg_0], rbx
0x18001b749  mov     [rsp+arg_8], rsi
0x18001b74e  push    rdi
0x18001b74f  sub     rsp, 20h
0x18001b753  mov     rdi, rdx
0x18001b756  mov     rbx, rcx
0x18001b759  mov     rdx, [rcx+10h]
0x18001b75d  cmp     rdi, rdx
0x18001b760  jbe     loc_18001B7FA
0x18001b766  cmp     qword ptr [rbx], 0
0x18001b76a  movsxd  rcx, dword ptr [rcx+18h]
0x18001b76e  jnz     short loc_18001B78F
0x18001b770  cmp     rcx, rdi
0x18001b773  mov     edx, 8; Size
0x18001b778  cmova   rdi, rcx
0x18001b77c  mov     rcx, rdi; Count
0x18001b77f  call    cs:__imp_calloc
0x18001b785  mov     [rbx], rax
0x18001b788  test    rax, rax
0x18001b78b  jz      short loc_18001B7C8
0x18001b78d  jmp     short loc_18001B7F6
0x18001b78f  test    rcx, rcx
0x18001b792  jnz     short loc_18001B7A7
0x18001b794  mov     rcx, rdx
0x18001b797  mov     rax, rdi
0x18001b79a  shr     rcx, 1
0x18001b79d  sub     rax, rdx
0x18001b7a0  cmp     rax, rcx
0x18001b7a3  cmova   rcx, rax
0x18001b7a7  lea     rax, [rdx+rcx]
0x18001b7ab  mov     edx, 8; Size
0x18001b7b0  cmp     rdi, rax
0x18001b7b3  cmovb   rdi, rax
0x18001b7b7  mov     rcx, rdi; Count
0x18001b7ba  call    cs:__imp_calloc
0x18001b7c0  mov     rsi, rax
0x18001b7c3  test    rax, rax
0x18001b7c6  jnz     short loc_18001B7CC
0x18001b7c8  xor     al, al
0x18001b7ca  jmp     short loc_18001B7FC
0x18001b7cc  mov     rdx, [rbx+8]
0x18001b7d0  mov     rcx, rsi; Destination
0x18001b7d3  mov     r8, [rbx]; Source
0x18001b7d6  shl     rdx, 3; DestinationSize
0x18001b7da  mov     r9, rdx; SourceSize
0x18001b7dd  call    cs:__imp_memmove_s
0x18001b7e3  mov     ecx, eax; int
0x18001b7e5  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18001b7ea  mov     rcx, [rbx]; Block
0x18001b7ed  call    cs:__imp_free
0x18001b7f3  mov     [rbx], rsi
0x18001b7f6  mov     [rbx+10h], rdi
0x18001b7fa  mov     al, 1
0x18001b7fc  mov     rbx, [rsp+28h+arg_0]
0x18001b801  mov     rsi, [rsp+28h+arg_8]
0x18001b806  add     rsp, 20h
0x18001b80a  pop     rdi
0x18001b80b  retn
```
