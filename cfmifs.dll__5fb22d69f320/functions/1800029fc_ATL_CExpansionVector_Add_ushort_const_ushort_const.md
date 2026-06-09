# ATL::CExpansionVector::Add(ushort const *,ushort const *)

- ea: `0x1800029fc`
- end: `0x180002c12`
- name: `?Add@CExpansionVector@ATL@@QEAAHPEBG0@Z`
- size: `534`
- prototype: `int(ATL::CExpansionVector *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180002ce0`
- `0x18000547c`
- `0x18000579c`

## callees

- `0x180001900`
- `0x1800029fc`
- `0x18000397c`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180002ac5`
- `msvcrt!memcpy_s` at `0x180002aff`
- `msvcrt!memcpy_s` at `0x180002ac5`
- `msvcrt!memcpy_s` at `0x180002aff`
- `ntdll!RtlFreeHeap` at `0x180002bb7`
- `ntdll!RtlFreeHeap` at `0x180002bd4`
- `ntdll!RtlFreeHeap` at `0x180002bb7`
- `ntdll!RtlFreeHeap` at `0x180002bd4`
- `ntdll!RtlAllocateHeap` at `0x180002a62`
- `ntdll!RtlAllocateHeap` at `0x180002a9e`
- `ntdll!RtlAllocateHeap` at `0x180002a62`
- `ntdll!RtlAllocateHeap` at `0x180002a9e`

## pseudocode

```c
__int64 __fastcall ATL::CExpansionVector::Add(void **this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  __int64 v6; // rax
  __int64 v7; // r12
  SIZE_T v8; // rax
  PVOID ProcessHeap; // rcx
  PVOID Heap; // rdi
  __int64 v11; // rcx
  __int64 v12; // r15
  SIZE_T v13; // rax
  PVOID v14; // rcx
  PVOID v15; // rax
  void *v16; // rbx
  errno_t v17; // eax
  errno_t v18; // eax
  unsigned int v19; // ebp
  void *v20; // rax
  void *v21; // rcx
  void *v22; // rax
  __int64 v23; // rdx
  _QWORD *v24; // rcx
  _QWORD *v25; // rcx

  if ( a2 && a3 )
  {
    v6 = -1;
    do
      ++v6;
    while ( a2[v6] );
    v7 = 2 * v6 + 2;
    v8 = 2 * v7;
    ProcessHeap = NtCurrentPeb()->ProcessHeap;
    if ( !is_mul_ok(v7, 2u) )
      v8 = -1;
    Heap = RtlAllocateHeap(ProcessHeap, 0, v8);
    v11 = -1;
    do
      ++v11;
    while ( a3[v11] );
    v12 = 2LL * ((int)v11 + 1);
    v13 = 4LL * ((int)v11 + 1);
    v14 = NtCurrentPeb()->ProcessHeap;
    if ( !is_mul_ok(v12, 2u) )
      v13 = -1;
    v15 = RtlAllocateHeap(v14, 0, v13);
    v16 = v15;
    if ( !Heap || !v15 )
    {
      v19 = 0;
      if ( !v15 )
        goto LABEL_33;
      goto LABEL_32;
    }
    v17 = memcpy_s(Heap, v7, a2, v7);
    if ( v17 )
    {
      if ( v17 == 12 )
        goto LABEL_37;
      if ( v17 == 22 || v17 == 34 )
        goto LABEL_39;
      if ( v17 != 80 )
        goto LABEL_38;
    }
    v18 = memcpy_s(v16, v12, a3, v12);
    if ( !v18 )
      goto LABEL_23;
    if ( v18 != 12 )
    {
      if ( v18 != 22 && v18 != 34 )
      {
        if ( v18 == 80 )
        {
LABEL_23:
          v19 = 1;
          v20 = _recalloc(*this, *((_DWORD *)this + 4) + 1, 8u);
          if ( v20 )
          {
            v21 = this[1];
            *this = v20;
            v22 = _recalloc(v21, *((_DWORD *)this + 4) + 1, 8u);
            if ( v22 )
            {
              v23 = *((int *)this + 4);
              this[1] = v22;
              v24 = (char *)*this + 8 * v23;
              if ( v24 )
                *v24 = Heap;
              v25 = (char *)this[1] + 8 * v23;
              if ( v25 )
                *v25 = v16;
              ++*((_DWORD *)this + 4);
              return v19;
            }
          }
          v19 = 0;
LABEL_32:
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v16);
LABEL_33:
          if ( Heap )
            RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
          return v19;
        }
LABEL_38:
        ATL::AtlThrowImpl(-2147467259);
      }
LABEL_39:
      ATL::AtlThrowImpl(-2147024809);
    }
LABEL_37:
    ATL::AtlThrowImpl(-2147024882);
  }
  return 0;
}

```

## disassembly

```asm
0x1800029fc  push    rbx
0x1800029fe  push    rbp
0x1800029ff  push    rsi
0x180002a00  push    rdi
0x180002a01  push    r12
0x180002a03  push    r13
0x180002a05  push    r14
0x180002a07  push    r15
0x180002a09  sub     rsp, 28h
0x180002a0d  xor     r13d, r13d
0x180002a10  mov     r14, r8
0x180002a13  mov     rbp, rdx
0x180002a16  mov     rsi, rcx
0x180002a19  test    rdx, rdx
0x180002a1c  jz      loc_180002BDE
0x180002a22  test    r8, r8
0x180002a25  jz      loc_180002BDE
0x180002a2b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180002a2f  mov     rax, rbx
0x180002a32  inc     rax
0x180002a35  cmp     [rdx+rax*2], r13w
0x180002a3a  jnz     short loc_180002A32
0x180002a3c  mov     rcx, gs:60h
0x180002a45  lea     r12, ds:2[rax*2]
0x180002a4d  mov     eax, 2
0x180002a52  mul     r12
0x180002a55  mov     rcx, [rcx+30h]; HeapHandle
0x180002a59  cmovb   rax, rbx
0x180002a5d  xor     edx, edx; Flags
0x180002a5f  mov     r8, rax; Size
0x180002a62  call    cs:__imp_RtlAllocateHeap
0x180002a68  mov     rdi, rax
0x180002a6b  mov     rcx, rbx
0x180002a6e  inc     rcx
0x180002a71  cmp     [r14+rcx*2], r13w
0x180002a76  jnz     short loc_180002A6E
0x180002a78  inc     ecx
0x180002a7a  mov     eax, 2
0x180002a7f  movsxd  r15, ecx
0x180002a82  mov     rcx, gs:60h
0x180002a8b  add     r15, r15
0x180002a8e  mul     r15
0x180002a91  mov     rcx, [rcx+30h]; HeapHandle
0x180002a95  cmovb   rax, rbx
0x180002a99  xor     edx, edx; Flags
0x180002a9b  mov     r8, rax; Size
0x180002a9e  call    cs:__imp_RtlAllocateHeap
0x180002aa4  mov     rbx, rax
0x180002aa7  test    rdi, rdi
0x180002aaa  jz      loc_180002B9D
0x180002ab0  test    rax, rax
0x180002ab3  jz      loc_180002B9D
0x180002ab9  mov     r9, r12; SourceSize
0x180002abc  mov     r8, rbp; Source
0x180002abf  mov     rdx, r12; DestinationSize
0x180002ac2  mov     rcx, rdi; Destination
0x180002ac5  call    cs:__imp_memcpy_s
0x180002acb  test    eax, eax
0x180002acd  jz      short loc_180002AF3
0x180002acf  cmp     eax, 0Ch
0x180002ad2  jz      loc_180002BF1
0x180002ad8  cmp     eax, 16h
0x180002adb  jz      loc_180002C07
0x180002ae1  cmp     eax, 22h ; '"'
0x180002ae4  jz      loc_180002C07
0x180002aea  cmp     eax, 50h ; 'P'
0x180002aed  jnz     loc_180002BFC
0x180002af3  mov     r9, r15; SourceSize
0x180002af6  mov     r8, r14; Source
0x180002af9  mov     rdx, r15; DestinationSize
0x180002afc  mov     rcx, rbx; Destination
0x180002aff  call    cs:__imp_memcpy_s
0x180002b05  test    eax, eax
0x180002b07  jz      short loc_180002B2D
0x180002b09  cmp     eax, 0Ch
0x180002b0c  jz      loc_180002BF1
0x180002b12  cmp     eax, 16h
0x180002b15  jz      loc_180002C07
0x180002b1b  cmp     eax, 22h ; '"'
0x180002b1e  jz      loc_180002C07
0x180002b24  cmp     eax, 50h ; 'P'
0x180002b27  jnz     loc_180002BFC
0x180002b2d  mov     eax, [rsi+10h]
0x180002b30  mov     ebp, 1
0x180002b35  mov     rcx, [rsi]; Block
0x180002b38  add     eax, ebp
0x180002b3a  movsxd  rdx, eax; Count
0x180002b3d  lea     r14d, [rbp+7]
0x180002b41  mov     r8d, r14d; Size
0x180002b44  call    cs:__imp__recalloc
0x180002b4a  test    rax, rax
0x180002b4d  jz      short loc_180002B98
0x180002b4f  mov     rcx, [rsi+8]; Block
0x180002b53  mov     r8d, r14d; Size
0x180002b56  mov     [rsi], rax
0x180002b59  mov     eax, [rsi+10h]
0x180002b5c  add     eax, ebp
0x180002b5e  movsxd  rdx, eax; Count
0x180002b61  call    cs:__imp__recalloc
0x180002b67  test    rax, rax
0x180002b6a  jz      short loc_180002B98
0x180002b6c  movsxd  rdx, dword ptr [rsi+10h]
0x180002b70  mov     [rsi+8], rax
0x180002b74  mov     rax, [rsi]
0x180002b77  lea     rcx, [rax+rdx*8]
0x180002b7b  test    rcx, rcx
0x180002b7e  jz      short loc_180002B83
0x180002b80  mov     [rcx], rdi
0x180002b83  mov     rax, [rsi+8]
0x180002b87  lea     rcx, [rax+rdx*8]
0x180002b8b  test    rcx, rcx
0x180002b8e  jz      short loc_180002B93
0x180002b90  mov     [rcx], rbx
0x180002b93  add     [rsi+10h], ebp
0x180002b96  jmp     short loc_180002BDA
0x180002b98  mov     ebp, r13d
0x180002b9b  jmp     short loc_180002BA5
0x180002b9d  mov     ebp, r13d
0x180002ba0  test    rbx, rbx
0x180002ba3  jz      short loc_180002BBD
0x180002ba5  mov     rcx, gs:60h
0x180002bae  mov     r8, rbx; P
0x180002bb1  xor     edx, edx; Flags
0x180002bb3  mov     rcx, [rcx+30h]; HeapHandle
0x180002bb7  call    cs:__imp_RtlFreeHeap
0x180002bbd  test    rdi, rdi
0x180002bc0  jz      short loc_180002BDA
0x180002bc2  mov     rcx, gs:60h
0x180002bcb  mov     r8, rdi; P
0x180002bce  xor     edx, edx; Flags
0x180002bd0  mov     rcx, [rcx+30h]; HeapHandle
0x180002bd4  call    cs:__imp_RtlFreeHeap
0x180002bda  mov     eax, ebp
0x180002bdc  jmp     short loc_180002BE0
0x180002bde  xor     eax, eax
0x180002be0  add     rsp, 28h
0x180002be4  pop     r15
0x180002be6  pop     r14
0x180002be8  pop     r13
0x180002bea  pop     r12
0x180002bec  pop     rdi
0x180002bed  pop     rsi
0x180002bee  pop     rbp
0x180002bef  pop     rbx
0x180002bf0  retn
0x180002bf1  mov     ecx, 8007000Eh; int
0x180002bf6  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180002bfc  mov     ecx, 80004005h; int
0x180002c01  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180002c07  mov     ecx, 80070057h; int
0x180002c0c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
