# REQUEST_LIST_BLOB::AddString(ushort const *,ulong)

- ea: `0x180001bbc`
- end: `0x180001c2e`
- name: `?AddString@REQUEST_LIST_BLOB@@QEAAJPEBGK@Z`
- size: `114`
- prototype: `__int64 __fastcall(REQUEST_LIST_BLOB *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180001cb4`

## callees

- `0x180001bbc`
- `0x180002ac4`
- `0x180002d86`

## pseudocode

```c
__int64 __fastcall REQUEST_LIST_BLOB::AddString(REQUEST_LIST_BLOB *this, const unsigned __int16 *a2, int a3)
{
  __int64 v3; // rdi
  __int64 result; // rax

  v3 = (unsigned int)(2 * a3 + 2);
  result = REQUEST_LIST_BLOB::ResizeIfNeeded(this, 2 * a3 + 2);
  if ( (int)result >= 0 )
  {
    if ( (unsigned int)(*(_DWORD *)this - *((_DWORD *)this + 1)) < (unsigned __int64)(v3 + 4) )
    {
      return 2147942487LL;
    }
    else
    {
      *(_DWORD *)(*((unsigned int *)this + 1) + *((_QWORD *)this + 1)) = v3;
      *((_DWORD *)this + 1) += 4;
      memcpy_0((void *)(*((_QWORD *)this + 1) + *((unsigned int *)this + 1)), a2, (unsigned int)v3);
      *((_DWORD *)this + 1) += v3;
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180001bbc  mov     [rsp+arg_0], rbx
0x180001bc1  mov     [rsp+arg_8], rsi
0x180001bc6  push    rdi
0x180001bc7  sub     rsp, 20h
0x180001bcb  lea     edi, ds:2[r8*2]
0x180001bd3  mov     rsi, rdx
0x180001bd6  mov     edx, edi; unsigned int
0x180001bd8  mov     rbx, rcx
0x180001bdb  call    ?ResizeIfNeeded@REQUEST_LIST_BLOB@@AEAAJK@Z; REQUEST_LIST_BLOB::ResizeIfNeeded(ulong)
0x180001be0  test    eax, eax
0x180001be2  js      short loc_180001C1E
0x180001be4  mov     ecx, [rbx]
0x180001be6  lea     rax, [rdi+4]
0x180001bea  sub     ecx, [rbx+4]
0x180001bed  mov     r8d, edi; Size
0x180001bf0  cmp     rcx, rax
0x180001bf3  jb      short loc_180001C19
0x180001bf5  mov     ecx, [rbx+4]
0x180001bf8  mov     rdx, rsi; Src
0x180001bfb  mov     rax, [rbx+8]
0x180001bff  mov     [rcx+rax], edi
0x180001c02  add     dword ptr [rbx+4], 4
0x180001c06  mov     ecx, [rbx+4]
0x180001c09  add     rcx, [rbx+8]; void *
0x180001c0d  call    memcpy_0
0x180001c12  add     [rbx+4], edi
0x180001c15  xor     eax, eax
0x180001c17  jmp     short loc_180001C1E
0x180001c19  mov     eax, 80070057h
0x180001c1e  mov     rbx, [rsp+28h+arg_0]
0x180001c23  mov     rsi, [rsp+28h+arg_8]
0x180001c28  add     rsp, 20h
0x180001c2c  pop     rdi
0x180001c2d  retn
```
