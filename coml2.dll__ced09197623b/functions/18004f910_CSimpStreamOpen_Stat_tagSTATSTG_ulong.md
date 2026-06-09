# CSimpStreamOpen::Stat(tagSTATSTG *,ulong)

- ea: `0x18004f910`
- end: `0x18004f9cd`
- name: `?Stat@CSimpStreamOpen@@UEAAJPEAUtagSTATSTG@@K@Z`
- size: `189`
- prototype: `int(CSimpStreamOpen *__hidden this, struct tagSTATSTG *, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x180023e70`
- `0x180043100`
- `0x18004f910`
- `0x18006141c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004f96a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18004f96a`

## pseudocode

```c
__int64 __fastcall CSimpStreamOpen::Stat(CSimpStreamOpen *this, struct tagSTATSTG *a2, int a3)
{
  size_t v6; // rdx
  void *v7; // rcx
  __int64 result; // rax
  unsigned int v9; // esi
  void *v10; // rax

  if ( !(unsigned int)IsValidReadPtrIn(a2, 0x50u) )
    return 2147680265LL;
  if ( (a3 & 0xFFFFFFFE) != 0 )
    return 2147680511LL;
  v9 = 0;
  memset_0(v7, 0, v6);
  if ( (a3 & 1) == 0 )
  {
    v10 = CoTaskMemAlloc(*(unsigned __int16 *)(*((_QWORD *)this + 6) + 64LL) + 2LL);
    *(_QWORD *)a2 = v10;
    if ( v10 )
    {
      memcpy_0(v10, *((const void **)this + 6), *(unsigned __int16 *)(*((_QWORD *)this + 6) + 64LL));
      *(_WORD *)(*(_QWORD *)a2 + 2 * ((unsigned __int64)*(unsigned __int16 *)(*((_QWORD *)this + 6) + 64LL) >> 1)) = 0;
    }
    else
    {
      v9 = -2147287032;
    }
  }
  result = v9;
  *((_QWORD *)a2 + 2) = *(unsigned int *)(*((_QWORD *)this + 6) + 72LL);
  *((_DWORD *)a2 + 2) = 2;
  *((_DWORD *)a2 + 12) = *((_DWORD *)this + 14);
  return result;
}

```

## disassembly

```asm
0x18004f910  push    rbx
0x18004f912  push    rbp
0x18004f913  push    rsi
0x18004f914  push    rdi
0x18004f915  sub     rsp, 28h
0x18004f919  mov     rbx, rdx
0x18004f91c  mov     rdi, rcx
0x18004f91f  mov     rcx, rbx; void *
0x18004f922  mov     edx, 50h ; 'P'; unsigned __int64
0x18004f927  mov     ebp, r8d
0x18004f92a  call    ?IsValidReadPtrIn@@YAHPEBX_K@Z; IsValidReadPtrIn(void const *,unsigned __int64)
0x18004f92f  test    eax, eax
0x18004f931  jnz     short loc_18004F93D
0x18004f933  mov     eax, 80030009h
0x18004f938  jmp     loc_18004F9C4
0x18004f93d  test    ebp, 0FFFFFFFEh
0x18004f943  jz      short loc_18004F94C
0x18004f945  mov     eax, 800300FFh
0x18004f94a  jmp     short loc_18004F9C4
0x18004f94c  mov     r8, rdx; Size
0x18004f94f  xor     esi, esi
0x18004f951  xor     edx, edx; Val
0x18004f953  call    memset_0
0x18004f958  test    bpl, 1
0x18004f95c  jnz     short loc_18004F9A4
0x18004f95e  mov     rax, [rdi+30h]
0x18004f962  movzx   ecx, word ptr [rax+40h]
0x18004f966  add     rcx, 2; cb
0x18004f96a  call    cs:__imp_CoTaskMemAlloc
0x18004f970  mov     [rbx], rax
0x18004f973  test    rax, rax
0x18004f976  jz      short loc_18004F99F
0x18004f978  mov     rdx, [rdi+30h]; Src
0x18004f97c  mov     rcx, rax; void *
0x18004f97f  movzx   r8d, word ptr [rdx+40h]; Size
0x18004f984  call    memcpy_0
0x18004f989  mov     rax, [rdi+30h]
0x18004f98d  mov     rcx, [rbx]
0x18004f990  movzx   edx, word ptr [rax+40h]
0x18004f994  shr     rdx, 1
0x18004f997  xor     eax, eax
0x18004f999  mov     [rcx+rdx*2], ax
0x18004f99d  jmp     short loc_18004F9A4
0x18004f99f  mov     esi, 80030008h
0x18004f9a4  mov     rcx, [rdi+30h]
0x18004f9a8  mov     eax, esi
0x18004f9aa  mov     edx, [rcx+48h]
0x18004f9ad  mov     [rbx+10h], edx
0x18004f9b0  mov     dword ptr [rbx+14h], 0
0x18004f9b7  mov     dword ptr [rbx+8], 2
0x18004f9be  mov     ecx, [rdi+38h]
0x18004f9c1  mov     [rbx+30h], ecx
0x18004f9c4  add     rsp, 28h
0x18004f9c8  pop     rdi
0x18004f9c9  pop     rsi
0x18004f9ca  pop     rbp
0x18004f9cb  pop     rbx
0x18004f9cc  retn
```
