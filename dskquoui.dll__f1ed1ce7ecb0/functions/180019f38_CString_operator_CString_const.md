# CString::operator=(CString const &)

- ea: `0x180019f38`
- end: `0x180019fa7`
- name: `??4CString@@QEAAAEAV0@AEBV0@@Z`
- size: `111`
- prototype: ``
- caller_count: `20`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180009b34`
- `0x18000a07c`
- `0x18000b090`
- `0x18000c224`
- `0x18000e4fc`
- `0x18000fc54`
- `0x18001003c`
- `0x1800113c0`
- `0x1800121a4`
- `0x18001270c`
- `0x180012b10`
- `0x18001387c`
- `0x180013d44`
- `0x180014220`
- `0x180014980`
- `0x180014e68`
- `0x180015694`
- `0x180016470`
- `0x18001bfc8`
- `0x18001c054`

## callees

- `0x180001534`
- `0x180019f38`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019f75`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180019f75`

## pseudocode

```c
__int64 __fastcall CString::operator=(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  HLOCAL *v5; // rdi
  __int64 v6; // rax

  v4 = *(_QWORD *)(a1 + 8);
  if ( v4 != *(_QWORD *)(a2 + 8) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v4 + 12), 0xFFFFFFFF) == 1 )
    {
      v5 = *(HLOCAL **)(a1 + 8);
      if ( v5 )
      {
        if ( *v5 )
          LocalFree(*v5);
        operator delete(v5);
      }
    }
    v6 = *(_QWORD *)(a2 + 8);
    *(_QWORD *)(a1 + 8) = v6;
    _InterlockedIncrement((volatile signed __int32 *)(v6 + 12));
  }
  return a1;
}

```

## disassembly

```asm
0x180019f38  mov     [rsp+arg_0], rbx
0x180019f3d  mov     [rsp+arg_8], rsi
0x180019f42  push    rdi
0x180019f43  sub     rsp, 20h
0x180019f47  mov     rbx, rcx
0x180019f4a  mov     rsi, rdx
0x180019f4d  mov     rcx, [rcx+8]
0x180019f51  cmp     rcx, [rdx+8]
0x180019f55  jz      short loc_180019F94
0x180019f57  or      eax, 0FFFFFFFFh
0x180019f5a  lock xadd [rcx+0Ch], eax
0x180019f5f  cmp     eax, 1
0x180019f62  jnz     short loc_180019F88
0x180019f64  mov     rdi, [rbx+8]
0x180019f68  test    rdi, rdi
0x180019f6b  jz      short loc_180019F88
0x180019f6d  mov     rcx, [rdi]; hMem
0x180019f70  test    rcx, rcx
0x180019f73  jz      short loc_180019F7B
0x180019f75  call    cs:__imp_LocalFree
0x180019f7b  mov     edx, 18h; unsigned __int64
0x180019f80  mov     rcx, rdi; void *
0x180019f83  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180019f88  mov     rax, [rsi+8]
0x180019f8c  mov     [rbx+8], rax
0x180019f90  lock inc dword ptr [rax+0Ch]
0x180019f94  mov     rsi, [rsp+28h+arg_8]
0x180019f99  mov     rax, rbx
0x180019f9c  mov     rbx, [rsp+28h+arg_0]
0x180019fa1  add     rsp, 20h
0x180019fa5  pop     rdi
0x180019fa6  retn
```
