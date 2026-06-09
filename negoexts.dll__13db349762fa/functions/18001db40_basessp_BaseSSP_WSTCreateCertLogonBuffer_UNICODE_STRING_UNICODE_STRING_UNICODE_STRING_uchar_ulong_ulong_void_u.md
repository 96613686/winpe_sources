# basessp::BaseSSP::WSTCreateCertLogonBuffer(_UNICODE_STRING *,_UNICODE_STRING *,_UNICODE_STRING *,uchar *,ulong,ulong,void * *,ulong *)

- ea: `0x18001db40`
- end: `0x18001dc7f`
- name: `?WSTCreateCertLogonBuffer@BaseSSP@basessp@@AEAAJPEAU_UNICODE_STRING@@00PEAEKKPEAPEAXPEAK@Z`
- size: `319`
- prototype: `__int64 __fastcall(basessp::BaseSSP *__hidden this, struct _UNICODE_STRING *, struct _UNICODE_STRING *, struct _UNICODE_STRING *, unsigned __int8 *Src, size_t Size, unsigned int, void **, unsigned int *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180005bc0`

## callees

- `0x1800027e4`
- `0x18001db40`
- `0x18001ece2`

## pseudocode

```c
__int64 __fastcall basessp::BaseSSP::WSTCreateCertLogonBuffer(
        basessp::BaseSSP *this,
        struct _UNICODE_STRING *a2,
        struct _UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4,
        unsigned __int8 *Src,
        size_t Size,
        unsigned int a7,
        void **a8,
        unsigned int *a9)
{
  unsigned int v12; // r13d
  char *v13; // rax
  char *v14; // rdi
  unsigned int v15; // esi
  size_t Length; // r8
  char *v17; // rbx
  PWSTR Buffer; // rdx
  size_t v19; // r8
  char *v20; // rbx
  PWSTR v21; // rdx
  size_t v22; // r8
  char *v23; // rbx
  PWSTR v24; // rdx
  __int64 v25; // rcx
  char *v26; // rcx

  v12 = Size + ((a2->Length + a4->Length + a3->Length + 93) & 0xFFFFFFF8);
  v13 = (char *)basessp::BaseSSP::WSTAllocate(this, v12);
  v14 = v13;
  if ( v13 )
  {
    Length = a2->Length;
    v17 = v13 + 80;
    Buffer = a2->Buffer;
    *(_DWORD *)v13 = 13;
    v15 = 0;
    *((_WORD *)v13 + 20) = Length;
    *((_QWORD *)v13 + 6) = 80;
    *((_WORD *)v13 + 21) = Length + 2;
    memcpy_0(v13 + 80, Buffer, Length);
    v19 = a3->Length;
    v20 = &v17[*((unsigned __int16 *)v14 + 21)];
    v21 = a3->Buffer;
    *((_WORD *)v14 + 4) = v19;
    *((_WORD *)v14 + 5) = v19 + 2;
    *((_QWORD *)v14 + 2) = v20 - v14;
    memcpy_0(v20, v21, v19);
    v22 = a4->Length;
    v23 = &v20[*((unsigned __int16 *)v14 + 5)];
    v24 = a4->Buffer;
    *((_WORD *)v14 + 12) = v22;
    *((_WORD *)v14 + 13) = v22 + 2;
    *((_QWORD *)v14 + 4) = v23 - v14;
    memcpy_0(v23, v24, v22);
    v25 = *((unsigned __int16 *)v14 + 13) + 7LL;
    *((_DWORD *)v14 + 15) = Size;
    v26 = (char *)((unsigned __int64)&v23[v25] & 0xFFFFFFFFFFFFFFF8uLL);
    *((_QWORD *)v14 + 8) = v26 - v14;
    memcpy_0(v26, Src, (unsigned int)Size);
    *((_DWORD *)v14 + 14) = 0;
    *a8 = v14;
    *a9 = v12;
  }
  else
  {
    return (unsigned int)-1073741670;
  }
  return v15;
}

```

## disassembly

```asm
0x18001db40  push    rbx
0x18001db42  push    rbp
0x18001db43  push    rsi
0x18001db44  push    rdi
0x18001db45  push    r12
0x18001db47  push    r13
0x18001db49  push    r14
0x18001db4b  push    r15
0x18001db4d  sub     rsp, 28h
0x18001db51  movzx   eax, word ptr [rdx]
0x18001db54  mov     r15, rdx
0x18001db57  movzx   r10d, word ptr [r9]
0x18001db5b  mov     rbp, r9
0x18001db5e  movzx   r13d, word ptr [r8]
0x18001db62  add     r10d, eax
0x18001db65  mov     r12d, dword ptr [rsp+68h+Size]
0x18001db6d  add     r13d, 5Dh ; ']'
0x18001db71  add     r13d, r10d
0x18001db74  mov     r14, r8
0x18001db77  and     r13d, 0FFFFFFF8h
0x18001db7b  add     r13d, r12d
0x18001db7e  mov     edx, r13d; unsigned __int64
0x18001db81  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x18001db86  mov     rdi, rax
0x18001db89  test    rax, rax
0x18001db8c  jnz     short loc_18001DB98
0x18001db8e  mov     esi, 0C000009Ah
0x18001db93  jmp     loc_18001DC6C
0x18001db98  movzx   r8d, word ptr [r15]; Size
0x18001db9c  lea     rbx, [rax+50h]
0x18001dba0  mov     rdx, [r15+8]; Src
0x18001dba4  mov     rcx, rbx; void *
0x18001dba7  mov     dword ptr [rax], 0Dh
0x18001dbad  xor     esi, esi
0x18001dbaf  mov     [rax+28h], r8w
0x18001dbb4  lea     eax, [r8+2]
0x18001dbb8  mov     qword ptr [rdi+30h], 50h ; 'P'
0x18001dbc0  mov     [rdi+2Ah], ax
0x18001dbc4  call    memcpy_0
0x18001dbc9  movzx   eax, word ptr [rdi+2Ah]
0x18001dbcd  movzx   r8d, word ptr [r14]; Size
0x18001dbd1  add     rbx, rax
0x18001dbd4  mov     rdx, [r14+8]; Src
0x18001dbd8  mov     rcx, rbx; void *
0x18001dbdb  mov     [rdi+8], r8w
0x18001dbe0  lea     eax, [r8+2]
0x18001dbe4  mov     [rdi+0Ah], ax
0x18001dbe8  mov     rax, rbx
0x18001dbeb  sub     rax, rdi
0x18001dbee  mov     [rdi+10h], rax
0x18001dbf2  call    memcpy_0
0x18001dbf7  movzx   eax, word ptr [rdi+0Ah]
0x18001dbfb  movzx   r8d, word ptr [rbp+0]; Size
0x18001dc00  add     rbx, rax
0x18001dc03  mov     rdx, [rbp+8]; Src
0x18001dc07  mov     rcx, rbx; void *
0x18001dc0a  mov     [rdi+18h], r8w
0x18001dc0f  lea     eax, [r8+2]
0x18001dc13  mov     [rdi+1Ah], ax
0x18001dc17  mov     rax, rbx
0x18001dc1a  sub     rax, rdi
0x18001dc1d  mov     [rdi+20h], rax
0x18001dc21  call    memcpy_0
0x18001dc26  movzx   ecx, word ptr [rdi+1Ah]
0x18001dc2a  mov     r8, r12; Size
0x18001dc2d  add     rcx, 7
0x18001dc31  mov     [rdi+3Ch], r12d
0x18001dc35  add     rcx, rbx
0x18001dc38  and     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x18001dc3c  mov     rdx, rcx
0x18001dc3f  sub     rdx, rdi
0x18001dc42  mov     [rdi+40h], rdx
0x18001dc46  mov     rdx, [rsp+68h+Src]; Src
0x18001dc4e  call    memcpy_0
0x18001dc53  mov     rcx, [rsp+68h+arg_38]
0x18001dc5b  mov     [rdi+38h], esi
0x18001dc5e  mov     [rcx], rdi
0x18001dc61  mov     rcx, [rsp+68h+arg_40]
0x18001dc69  mov     [rcx], r13d
0x18001dc6c  mov     eax, esi
0x18001dc6e  add     rsp, 28h
0x18001dc72  pop     r15
0x18001dc74  pop     r14
0x18001dc76  pop     r13
0x18001dc78  pop     r12
0x18001dc7a  pop     rdi
0x18001dc7b  pop     rsi
0x18001dc7c  pop     rbp
0x18001dc7d  pop     rbx
0x18001dc7e  retn
```
