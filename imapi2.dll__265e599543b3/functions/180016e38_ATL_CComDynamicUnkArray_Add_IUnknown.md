# ATL::CComDynamicUnkArray::Add(IUnknown *)

- ea: `0x180016e38`
- end: `0x180016f03`
- name: `?Add@CComDynamicUnkArray@ATL@@QEAAKPEAUIUnknown@@@Z`
- size: `203`
- prototype: `unsigned int __fastcall(ATL::CComDynamicUnkArray *__hidden this, struct IUnknown *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180016f80`
- `0x180025080`
- `0x1800280c0`

## callees

- `0x180010330`
- `0x180016e38`
- `0x18004984a`

## import_xrefs

- `msvcrt!calloc` at `0x180016e5e`
- `msvcrt!calloc` at `0x180016e5e`

## pseudocode

```c
__int64 __fastcall ATL::CComDynamicUnkArray::Add(ATL::CComDynamicUnkArray *this, struct IUnknown *a2)
{
  int v2; // edi
  _OWORD *v5; // rax
  unsigned int v6; // edx
  _QWORD *i; // rcx
  __int64 result; // rax
  int v9; // edi
  char *v10; // rcx
  __int64 v11; // rax

  v2 = *((_DWORD *)this + 2);
  if ( !v2 )
  {
    v2 = 4;
    v5 = calloc(8u, 4u);
    if ( !v5 )
      return 0;
    *(_QWORD *)this = v5;
    *v5 = 0;
    *((_DWORD *)this + 2) = 4;
    v5[1] = 0;
  }
  v6 = 1;
  for ( i = *(_QWORD **)this; (unsigned __int64)i < *(_QWORD *)this + 8LL * v2; ++i )
  {
    if ( !*i )
    {
      *i = a2;
      return v6;
    }
    ++v6;
  }
  v9 = 2 * *((_DWORD *)this + 2);
  v10 = (char *)_recalloc(*(void **)this, 8u, v9);
  if ( !v10 )
    return 0;
  v11 = *((int *)this + 2);
  *(_QWORD *)this = v10;
  memset_0(&v10[8 * v11], 0, 8 * v11);
  *(_QWORD *)(*(_QWORD *)this + 8LL * *((int *)this + 2)) = a2;
  result = (unsigned int)(*((_DWORD *)this + 2) + 1);
  *((_DWORD *)this + 2) = v9;
  return result;
}

```

## disassembly

```asm
0x180016e38  mov     [rsp+arg_0], rbx
0x180016e3d  mov     [rsp+arg_8], rsi
0x180016e42  push    rdi
0x180016e43  sub     rsp, 20h
0x180016e47  mov     edi, [rcx+8]
0x180016e4a  mov     rsi, rdx
0x180016e4d  mov     rbx, rcx
0x180016e50  test    edi, edi
0x180016e52  jnz     short loc_180016E79
0x180016e54  mov     edi, 4
0x180016e59  mov     edx, edi; Size
0x180016e5b  lea     ecx, [rdi+4]; Count
0x180016e5e  call    cs:__imp_calloc
0x180016e64  test    rax, rax
0x180016e67  jz      short loc_180016EC3
0x180016e69  xorps   xmm0, xmm0
0x180016e6c  mov     [rbx], rax
0x180016e6f  movups  xmmword ptr [rax], xmm0
0x180016e72  mov     [rbx+8], edi
0x180016e75  movups  xmmword ptr [rax+10h], xmm0
0x180016e79  mov     r9, [rbx]
0x180016e7c  mov     edx, 1
0x180016e81  movsxd  rax, edi
0x180016e84  mov     rcx, r9
0x180016e87  lea     r8, [r9+rax*8]
0x180016e8b  cmp     rcx, r8
0x180016e8e  jnb     short loc_180016EA5
0x180016e90  cmp     qword ptr [rcx], 0
0x180016e94  jz      short loc_180016E9E
0x180016e96  inc     edx
0x180016e98  add     rcx, 8
0x180016e9c  jmp     short loc_180016E8B
0x180016e9e  mov     [rcx], rsi
0x180016ea1  mov     eax, edx
0x180016ea3  jmp     short loc_180016EF3
0x180016ea5  mov     edi, [rbx+8]
0x180016ea8  mov     edx, 8; Count
0x180016ead  add     edi, edi
0x180016eaf  mov     rcx, r9; Block
0x180016eb2  movsxd  r8, edi; Size
0x180016eb5  call    cs:__imp__recalloc
0x180016ebb  mov     rcx, rax
0x180016ebe  test    rax, rax
0x180016ec1  jnz     short loc_180016EC7
0x180016ec3  xor     eax, eax
0x180016ec5  jmp     short loc_180016EF3
0x180016ec7  movsxd  rax, dword ptr [rbx+8]
0x180016ecb  xor     edx, edx; Val
0x180016ecd  mov     [rbx], rcx
0x180016ed0  lea     r8, ds:0[rax*8]; Size
0x180016ed8  add     rcx, r8; void *
0x180016edb  call    memset_0
0x180016ee0  movsxd  rcx, dword ptr [rbx+8]
0x180016ee4  mov     rax, [rbx]
0x180016ee7  mov     [rax+rcx*8], rsi
0x180016eeb  mov     eax, [rbx+8]
0x180016eee  inc     eax
0x180016ef0  mov     [rbx+8], edi
0x180016ef3  mov     rbx, [rsp+28h+arg_0]
0x180016ef8  mov     rsi, [rsp+28h+arg_8]
0x180016efd  add     rsp, 20h
0x180016f01  pop     rdi
0x180016f02  retn
```
