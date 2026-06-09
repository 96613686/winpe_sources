# RtlNameValueArray::Append(ushort const *,ushort const *)

- ea: `0x180002c04`
- end: `0x180002cbd`
- name: `?Append@RtlNameValueArray@@QEAAKPEBG0@Z`
- size: `185`
- prototype: `unsigned int(RtlNameValueArray *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800039c8`
- `0x180004ef4`
- `0x180006664`

## callees

- `0x180002c04`
- `0x1800046f8`
- `0x1800191a2`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180002c7f`
- `msvcrt!wcscpy_s` at `0x180002c8f`
- `msvcrt!wcscpy_s` at `0x180002c7f`
- `msvcrt!wcscpy_s` at `0x180002c8f`
- `KERNEL32!HeapAlloc` at `0x180002c56`
- `KERNEL32!HeapAlloc` at `0x180002c56`

## pseudocode

```c
__int64 __fastcall RtlNameValueArray::Append(
        RtlNameValueArray *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 v3; // r13
  __int64 v4; // rax
  __int64 v6; // r9
  rsize_t v9; // rbp
  rsize_t v10; // r12
  SIZE_T v11; // rbx
  wchar_t *v12; // rax
  wchar_t *v13; // rdi
  wchar_t *v15; // [rsp+70h] [rbp+8h] BYREF

  v3 = *((_QWORD *)this + 2);
  v4 = -1;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v9 = v6 + 1;
  do
    ++v4;
  while ( a3[v4] );
  v10 = v4 + 1;
  v11 = 2 * (v4 + 1 + v9);
  v12 = (wchar_t *)HeapAlloc(*(HANDLE *)this, 0, v11);
  v15 = v12;
  v13 = v12;
  if ( !v12 )
    return 14;
  memset_0(v12, 0, v11);
  wcscpy_s(v13, v9, a2);
  wcscpy_s(&v13[v9], v10, a3);
  return RtlArray<unsigned short *>::Insert(this, &v15, v3);
}

```

## disassembly

```asm
0x180002c04  push    rbx
0x180002c06  push    rbp
0x180002c07  push    rsi
0x180002c08  push    rdi
0x180002c09  push    r12
0x180002c0b  push    r13
0x180002c0d  push    r14
0x180002c0f  push    r15
0x180002c11  sub     rsp, 28h
0x180002c15  mov     r13, [rcx+10h]
0x180002c19  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002c1d  mov     rsi, rcx
0x180002c20  mov     r9, rax
0x180002c23  xor     ecx, ecx
0x180002c25  mov     r14, r8
0x180002c28  mov     r15, rdx
0x180002c2b  inc     r9
0x180002c2e  cmp     [rdx+r9*2], cx
0x180002c33  jnz     short loc_180002C2B
0x180002c35  lea     rbp, [r9+1]
0x180002c39  inc     rax
0x180002c3c  cmp     [r8+rax*2], cx
0x180002c41  jnz     short loc_180002C39
0x180002c43  mov     rcx, [rsi]; hHeap
0x180002c46  lea     r12, [rax+1]
0x180002c4a  lea     rbx, [r12+rbp]
0x180002c4e  xor     edx, edx; dwFlags
0x180002c50  add     rbx, rbx
0x180002c53  mov     r8, rbx; dwBytes
0x180002c56  call    cs:__imp_HeapAlloc
0x180002c5c  mov     [rsp+68h+arg_0], rax
0x180002c61  mov     rdi, rax
0x180002c64  test    rax, rax
0x180002c67  jz      short loc_180002CA7
0x180002c69  mov     r8, rbx; Size
0x180002c6c  xor     edx, edx; Val
0x180002c6e  mov     rcx, rax; void *
0x180002c71  call    memset_0
0x180002c76  mov     r8, r15; Source
0x180002c79  mov     rdx, rbp; SizeInWords
0x180002c7c  mov     rcx, rdi; Destination
0x180002c7f  call    cs:__imp_wcscpy_s
0x180002c85  lea     rcx, [rdi+rbp*2]; Destination
0x180002c89  mov     r8, r14; Source
0x180002c8c  mov     rdx, r12; SizeInWords
0x180002c8f  call    cs:__imp_wcscpy_s
0x180002c95  mov     r8, r13
0x180002c98  lea     rdx, [rsp+68h+arg_0]
0x180002c9d  mov     rcx, rsi
0x180002ca0  call    ?Insert@?$RtlArray@PEAG@@QEAAJAEBQEAG_K@Z; RtlArray<ushort *>::Insert(ushort * const &,unsigned __int64)
0x180002ca5  jmp     short loc_180002CAC
0x180002ca7  mov     eax, 0Eh
0x180002cac  add     rsp, 28h
0x180002cb0  pop     r15
0x180002cb2  pop     r14
0x180002cb4  pop     r13
0x180002cb6  pop     r12
0x180002cb8  pop     rdi
0x180002cb9  pop     rsi
0x180002cba  pop     rbp
0x180002cbb  pop     rbx
0x180002cbc  retn
```
