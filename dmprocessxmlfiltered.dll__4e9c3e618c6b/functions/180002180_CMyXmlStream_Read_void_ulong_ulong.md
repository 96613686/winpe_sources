# CMyXmlStream::Read(void *,ulong,ulong *)

- ea: `0x180002180`
- end: `0x1800021d8`
- name: `?Read@CMyXmlStream@@UEAAJPEAXKPEAK@Z`
- size: `88`
- prototype: `int(CMyXmlStream *__hidden this, void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180002180`
- `0x180006bd0`

## pseudocode

```c
_BOOL8 __fastcall CMyXmlStream::Read(CMyXmlStream *this, void *a2, unsigned int a3, unsigned int *a4)
{
  int v4; // ebx
  unsigned int v9; // ebx

  v4 = *((_DWORD *)this + 4);
  if ( v4 == *((_DWORD *)this + 5) )
  {
    *a4 = 0;
    return 1;
  }
  else
  {
    v9 = v4 - *((_DWORD *)this + 5);
    if ( a3 < v9 )
      v9 = a3;
    memcpy_0(a2, (const void *)(*((_QWORD *)this + 1) + *((unsigned int *)this + 5)), v9);
    *((_DWORD *)this + 5) += v9;
    *a4 = v9;
    return v9 != a3;
  }
}

```

## disassembly

```asm
0x180002180  push    rbx
0x180002182  push    rbp
0x180002183  push    rsi
0x180002184  push    rdi
0x180002185  sub     rsp, 28h
0x180002189  mov     ebx, [rcx+10h]
0x18000218c  mov     rsi, r9
0x18000218f  mov     ebp, r8d
0x180002192  mov     rax, rdx
0x180002195  mov     rdi, rcx
0x180002198  cmp     ebx, [rcx+14h]
0x18000219b  jnz     short loc_1800021A9
0x18000219d  xor     eax, eax
0x18000219f  mov     [r9], eax
0x1800021a2  mov     eax, 1
0x1800021a7  jmp     short loc_1800021CF
0x1800021a9  sub     ebx, [rcx+14h]
0x1800021ac  mov     edx, [rcx+14h]
0x1800021af  cmp     ebp, ebx
0x1800021b1  cmovb   ebx, ebp
0x1800021b4  add     rdx, [rcx+8]; Src
0x1800021b8  mov     r8d, ebx; Size
0x1800021bb  mov     rcx, rax; void *
0x1800021be  call    memcpy_0
0x1800021c3  add     [rdi+14h], ebx
0x1800021c6  xor     eax, eax
0x1800021c8  cmp     ebx, ebp
0x1800021ca  mov     [rsi], ebx
0x1800021cc  setnz   al
0x1800021cf  add     rsp, 28h
0x1800021d3  pop     rdi
0x1800021d4  pop     rsi
0x1800021d5  pop     rbp
0x1800021d6  pop     rbx
0x1800021d7  retn
```
