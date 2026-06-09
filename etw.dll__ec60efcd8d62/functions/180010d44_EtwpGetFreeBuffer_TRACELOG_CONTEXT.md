# EtwpGetFreeBuffer(_TRACELOG_CONTEXT *)

- ea: `0x180010d44`
- end: `0x180010db2`
- name: `?EtwpGetFreeBuffer@@YAPEAU_WMI_BUFFER_HEADER@@PEAU_TRACELOG_CONTEXT@@@Z`
- size: `110`
- prototype: `struct _WMI_BUFFER_HEADER *__fastcall(struct _TRACELOG_CONTEXT *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180010ed8`
- `0x18001118c`
- `0x180014b10`

## callees

- `0x180001eb2`
- `0x180001ff0`
- `0x180010d44`

## pseudocode

```c
struct _WMI_BUFFER_HEADER *__fastcall EtwpGetFreeBuffer(struct _TRACELOG_CONTEXT *a1)
{
  signed __int64 *v1; // r8
  signed __int64 *v2; // rbx
  unsigned int v3; // edi
  signed __int64 *v4; // rax

  while ( 1 )
  {
    v1 = (signed __int64 *)*((_QWORD *)a1 + 120);
    if ( !v1 )
      break;
    if ( v1 == (signed __int64 *)_InterlockedCompareExchange64(
                                   (volatile signed __int64 *)a1 + 120,
                                   *v1,
                                   (signed __int64)v1) )
    {
      v2 = v1 - 4;
      *v1 = 0;
      return (struct _WMI_BUFFER_HEADER *)v2;
    }
  }
  v3 = *((_DWORD *)a1 + 192);
  v4 = (signed __int64 *)operator new(v3, (const struct std::nothrow_t *)&std::nothrow);
  v2 = v4;
  if ( v4 )
    memset_0(v4, 0, v3);
  return (struct _WMI_BUFFER_HEADER *)v2;
}

```

## disassembly

```asm
0x180010d44  mov     [rsp+arg_0], rbx
0x180010d49  push    rdi
0x180010d4a  sub     rsp, 20h
0x180010d4e  mov     r8, [rcx+3C0h]
0x180010d55  test    r8, r8
0x180010d58  jz      short loc_180010D7B
0x180010d5a  mov     rdx, [r8]
0x180010d5d  mov     rax, r8
0x180010d60  lock cmpxchg [rcx+3C0h], rdx
0x180010d69  cmp     r8, rax
0x180010d6c  jnz     short loc_180010D4E
0x180010d6e  lea     rbx, [r8-20h]
0x180010d72  mov     qword ptr [r8], 0
0x180010d79  jmp     short loc_180010DA4
0x180010d7b  mov     edi, [rcx+300h]
0x180010d81  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180010d88  mov     ecx, edi; unsigned __int64
0x180010d8a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180010d8f  mov     rbx, rax
0x180010d92  test    rax, rax
0x180010d95  jz      short loc_180010DA4
0x180010d97  mov     r8d, edi; Size
0x180010d9a  xor     edx, edx; Val
0x180010d9c  mov     rcx, rax; void *
0x180010d9f  call    memset_0
0x180010da4  mov     rax, rbx
0x180010da7  mov     rbx, [rsp+28h+arg_0]
0x180010dac  add     rsp, 20h
0x180010db0  pop     rdi
0x180010db1  retn
```
