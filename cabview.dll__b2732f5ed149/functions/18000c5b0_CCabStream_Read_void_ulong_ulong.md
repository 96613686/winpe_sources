# CCabStream::Read(void *,ulong,ulong *)

- ea: `0x18000c5b0`
- end: `0x18000c60c`
- name: `?Read@CCabStream@@UEAAJPEAXKPEAK@Z`
- size: `92`
- prototype: `int(CCabStream *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x18000c5b0`
- `0x180012a80`

## pseudocode

```c
__int64 __fastcall CCabStream::Read(CCabStream *this, void *a2, unsigned int a3, unsigned int *a4)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  unsigned int v8; // eax

  v4 = *((_DWORD *)this + 6);
  v5 = 0;
  if ( *((_DWORD *)this + 7) < v4 )
  {
    v8 = v4 - *((_DWORD *)this + 7);
    v5 = a3;
    if ( a3 > v8 )
      v5 = v8;
    memcpy_0(a2, (const void *)(*((_QWORD *)this + 2) + *((unsigned int *)this + 7)), v5);
    *((_DWORD *)this + 7) += v5;
  }
  if ( a4 )
    *a4 = v5;
  return 0;
}

```

## disassembly

```asm
0x18000c5b0  mov     [rsp+arg_0], rbx
0x18000c5b5  mov     [rsp+arg_8], rsi
0x18000c5ba  push    rdi
0x18000c5bb  sub     rsp, 20h
0x18000c5bf  mov     eax, [rcx+18h]
0x18000c5c2  xor     ebx, ebx
0x18000c5c4  mov     rdi, r9
0x18000c5c7  mov     r9, rdx
0x18000c5ca  mov     rsi, rcx
0x18000c5cd  cmp     [rcx+1Ch], eax
0x18000c5d0  jnb     short loc_18000C5F3
0x18000c5d2  sub     eax, [rcx+1Ch]
0x18000c5d5  mov     ebx, r8d
0x18000c5d8  mov     edx, [rcx+1Ch]
0x18000c5db  cmp     r8d, eax
0x18000c5de  cmova   ebx, eax
0x18000c5e1  add     rdx, [rcx+10h]; Src
0x18000c5e5  mov     r8d, ebx; Size
0x18000c5e8  mov     rcx, r9; void *
0x18000c5eb  call    memcpy_0
0x18000c5f0  add     [rsi+1Ch], ebx
0x18000c5f3  test    rdi, rdi
0x18000c5f6  jz      short loc_18000C5FA
0x18000c5f8  mov     [rdi], ebx
0x18000c5fa  mov     rbx, [rsp+28h+arg_0]
0x18000c5ff  xor     eax, eax
0x18000c601  mov     rsi, [rsp+28h+arg_8]
0x18000c606  add     rsp, 20h
0x18000c60a  pop     rdi
0x18000c60b  retn
```
