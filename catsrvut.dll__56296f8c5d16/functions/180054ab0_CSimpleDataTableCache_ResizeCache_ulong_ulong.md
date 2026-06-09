# CSimpleDataTableCache::ResizeCache(ulong,ulong)

- ea: `0x180054ab0`
- end: `0x180054b8c`
- name: `?ResizeCache@CSimpleDataTableCache@@IEAAJKK@Z`
- size: `220`
- prototype: `__int64 __fastcall(CSimpleDataTableCache *this, int, unsigned int)`
- caller_count: `4`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800530c8`
- `0x180053154`
- `0x18005329c`
- `0x180054138`

## callees

- `0x180054ab0`
- `0x18005582e`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180054b3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180054b3e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180054b6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x180054b6a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSimpleDataTableCache::ResizeCache(CSimpleDataTableCache *this, int a2, unsigned int a3)
{
  LPVOID *v6; // rdi
  unsigned int v7; // ebp
  int v8; // ebp
  void *v9; // rax
  void *v10; // r14
  LPVOID v11; // rax

  if ( a2 == 0x20000 )
  {
    v6 = (LPVOID *)((char *)this + 88);
    if ( *((_QWORD *)this + 7) == *((_QWORD *)this + 11) )
      *((_QWORD *)this + 7) = 0;
    v8 = *((_DWORD *)this + 20) * (*((_DWORD *)this + 3) + *((_DWORD *)this + 4) + *((_DWORD *)this + 2) + 1);
    goto LABEL_12;
  }
  if ( a2 == 0x40000 )
  {
    v6 = (LPVOID *)((char *)this + 120);
    v8 = 3 * *((_DWORD *)this + 28);
LABEL_12:
    v7 = 4 * v8;
    goto LABEL_13;
  }
  if ( a2 != 0x200000 )
    return 2147549183LL;
  v6 = (LPVOID *)((char *)this + 104);
  if ( *((_QWORD *)this + 9) == *((_QWORD *)this + 13) )
    *((_QWORD *)this + 9) = 0;
  v7 = *((_DWORD *)this + 24);
LABEL_13:
  if ( (*(_DWORD *)this & 0x40000) != 0 || (a2 & *((_DWORD *)this + 10)) == 0 )
  {
    v11 = CoTaskMemRealloc(*v6, a3);
    if ( v11 )
    {
      *v6 = v11;
      return 0;
    }
    return 2147942414LL;
  }
  v9 = CoTaskMemAlloc(a3);
  v10 = v9;
  if ( !v9 )
    return 2147942414LL;
  memcpy_0(v9, *v6, v7);
  *v6 = v10;
  *((_DWORD *)this + 10) &= ~a2;
  return 0;
}

```

## disassembly

```asm
0x180054ab0  push    rbx
0x180054ab2  push    rbp
0x180054ab3  push    rsi
0x180054ab4  push    rdi
0x180054ab5  push    r14
0x180054ab7  sub     rsp, 20h
0x180054abb  mov     esi, edx
0x180054abd  mov     rbx, rcx
0x180054ac0  mov     edx, 40000h
0x180054ac5  cmp     esi, 20000h
0x180054acb  jz      short loc_180054B09
0x180054acd  cmp     esi, edx
0x180054acf  jz      short loc_180054AFD
0x180054ad1  cmp     esi, 200000h
0x180054ad7  jz      short loc_180054AE3
0x180054ad9  mov     eax, 8000FFFFh
0x180054ade  jmp     loc_180054B81
0x180054ae3  lea     rdi, [rcx+68h]
0x180054ae7  mov     rax, [rdi]
0x180054aea  cmp     [rcx+48h], rax
0x180054aee  jnz     short loc_180054AF8
0x180054af0  mov     qword ptr [rcx+48h], 0
0x180054af8  mov     ebp, [rcx+60h]
0x180054afb  jmp     short loc_180054B32
0x180054afd  mov     eax, [rcx+70h]
0x180054b00  lea     rdi, [rcx+78h]
0x180054b04  lea     ebp, [rax+rax*2]
0x180054b07  jmp     short loc_180054B2F
0x180054b09  lea     rdi, [rcx+58h]
0x180054b0d  mov     rax, [rdi]
0x180054b10  cmp     [rcx+38h], rax
0x180054b14  jnz     short loc_180054B1E
0x180054b16  mov     qword ptr [rcx+38h], 0
0x180054b1e  mov     ecx, [rcx+10h]
0x180054b21  add     ecx, [rbx+0Ch]
0x180054b24  mov     ebp, [rbx+8]
0x180054b27  inc     ebp
0x180054b29  add     ebp, ecx
0x180054b2b  imul    ebp, [rbx+50h]
0x180054b2f  shl     ebp, 2
0x180054b32  test    [rbx], edx
0x180054b34  jnz     short loc_180054B64
0x180054b36  test    [rbx+28h], esi
0x180054b39  jz      short loc_180054B64
0x180054b3b  mov     ecx, r8d; cb
0x180054b3e  call    cs:__imp_CoTaskMemAlloc
0x180054b44  mov     r14, rax
0x180054b47  test    rax, rax
0x180054b4a  jz      short loc_180054B75
0x180054b4c  mov     rdx, [rdi]; Src
0x180054b4f  mov     rcx, rax; void *
0x180054b52  mov     r8d, ebp; Size
0x180054b55  call    memcpy_0
0x180054b5a  not     esi
0x180054b5c  mov     [rdi], r14
0x180054b5f  and     [rbx+28h], esi
0x180054b62  jmp     short loc_180054B7F
0x180054b64  mov     rcx, [rdi]; pv
0x180054b67  mov     edx, r8d; cb
0x180054b6a  call    cs:__imp_CoTaskMemRealloc
0x180054b70  test    rax, rax
0x180054b73  jnz     short loc_180054B7C
0x180054b75  mov     eax, 8007000Eh
0x180054b7a  jmp     short loc_180054B81
0x180054b7c  mov     [rdi], rax
0x180054b7f  xor     eax, eax
0x180054b81  add     rsp, 20h
0x180054b85  pop     r14
0x180054b87  pop     rdi
0x180054b88  pop     rsi
0x180054b89  pop     rbp
0x180054b8a  pop     rbx
0x180054b8b  retn
```
