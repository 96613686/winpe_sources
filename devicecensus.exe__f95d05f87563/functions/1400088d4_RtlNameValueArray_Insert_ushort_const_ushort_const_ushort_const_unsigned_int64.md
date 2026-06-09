# RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)

- ea: `0x1400088d4`
- end: `0x140008993`
- name: `?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z`
- size: `191`
- prototype: `__int64 __fastcall(PVOID *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140008b9c`
- `0x140008c40`

## callees

- `0x14000233f`
- `0x1400086ac`
- `0x1400088d4`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x140008950`
- `msvcrt!wcscpy_s` at `0x140008960`
- `msvcrt!wcscpy_s` at `0x140008950`
- `msvcrt!wcscpy_s` at `0x140008960`
- `ntdll!RtlAllocateHeap` at `0x140008927`
- `ntdll!RtlAllocateHeap` at `0x140008927`

## pseudocode

```c
__int64 __fastcall RtlNameValueArray::Insert(
        PVOID *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int64 a5)
{
  __int64 v5; // rax
  __int64 v7; // rdx
  rsize_t v10; // rsi
  rsize_t v11; // r15
  SIZE_T v12; // rbx
  unsigned __int16 *Heap; // rax
  wchar_t *v14; // rdi
  const unsigned __int16 *v16; // [rsp+78h] [rbp+10h] BYREF

  v16 = a2;
  v5 = -1;
  v7 = -1;
  do
    ++v7;
  while ( a3[v7] );
  v10 = v7 + 1;
  do
    ++v5;
  while ( a4[v5] );
  v11 = v5 + 1;
  v12 = 2 * (v5 + 1 + v10);
  Heap = (unsigned __int16 *)RtlAllocateHeap(*this, 0, v12);
  v16 = Heap;
  v14 = Heap;
  if ( !Heap )
    return 3221225495LL;
  memset_0(Heap, 0, v12);
  wcscpy_s(v14, v10, a3);
  wcscpy_s(&v14[v10], v11, a4);
  return RtlArray<unsigned short *>::Insert(this, &v16, a5);
}

```

## disassembly

```asm
0x1400088d4  mov     [rsp+arg_8], rdx
0x1400088d9  push    rbx
0x1400088da  push    rbp
0x1400088db  push    rsi
0x1400088dc  push    rdi
0x1400088dd  push    r12
0x1400088df  push    r13
0x1400088e1  push    r14
0x1400088e3  push    r15
0x1400088e5  sub     rsp, 28h
0x1400088e9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400088ed  mov     rbp, r9
0x1400088f0  mov     rdx, rax
0x1400088f3  xor     r13d, r13d
0x1400088f6  mov     r14, r8
0x1400088f9  mov     r12, rcx
0x1400088fc  inc     rdx
0x1400088ff  cmp     [r8+rdx*2], r13w
0x140008904  jnz     short loc_1400088FC
0x140008906  lea     rsi, [rdx+1]
0x14000890a  inc     rax
0x14000890d  cmp     [r9+rax*2], r13w
0x140008912  jnz     short loc_14000890A
0x140008914  mov     rcx, [rcx]; HeapHandle
0x140008917  lea     r15, [rax+1]
0x14000891b  lea     rbx, [r15+rsi]
0x14000891f  xor     edx, edx; Flags
0x140008921  add     rbx, rbx
0x140008924  mov     r8, rbx; Size
0x140008927  call    cs:__imp_RtlAllocateHeap
0x14000892d  mov     [rsp+68h+arg_8], rax
0x140008932  mov     rdi, rax
0x140008935  test    rax, rax
0x140008938  jz      short loc_14000897D
0x14000893a  mov     r8, rbx; Size
0x14000893d  xor     edx, edx; Val
0x14000893f  mov     rcx, rax; void *
0x140008942  call    memset_0
0x140008947  mov     r8, r14; Source
0x14000894a  mov     rdx, rsi; SizeInWords
0x14000894d  mov     rcx, rdi; Destination
0x140008950  call    cs:__imp_wcscpy_s
0x140008956  lea     rcx, [rdi+rsi*2]; Destination
0x14000895a  mov     r8, rbp; Source
0x14000895d  mov     rdx, r15; SizeInWords
0x140008960  call    cs:__imp_wcscpy_s
0x140008966  mov     r8, [rsp+68h+arg_20]
0x14000896e  lea     rdx, [rsp+68h+arg_8]
0x140008973  mov     rcx, r12
0x140008976  call    ?Insert@?$RtlArray@PEAG@@QEAAJAEBQEAG_K@Z; RtlArray<ushort *>::Insert(ushort * const &,unsigned __int64)
0x14000897b  jmp     short loc_140008982
0x14000897d  mov     eax, 0C0000017h
0x140008982  add     rsp, 28h
0x140008986  pop     r15
0x140008988  pop     r14
0x14000898a  pop     r13
0x14000898c  pop     r12
0x14000898e  pop     rdi
0x14000898f  pop     rsi
0x140008990  pop     rbp
0x140008991  pop     rbx
0x140008992  retn
```
