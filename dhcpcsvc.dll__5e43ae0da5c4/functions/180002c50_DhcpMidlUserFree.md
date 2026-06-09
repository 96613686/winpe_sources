# DhcpMidlUserFree

- ea: `0x180002c50`
- end: `0x180002c7a`
- name: `DhcpMidlUserFree`
- size: `42`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x180006e10`
- `0x180007010`
- `0x180007200`
- `0x1800075d0`
- `0x180007aa0`
- `0x180008700`
- `0x18000a950`
- `0x18000ac50`
- `0x18000c540`
- `0x18000c7d0`
- `0x18000c990`
- `0x18000cc10`
- `0x18000cfe0`
- `0x18000d660`

## callees

- `0x180002c50`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180002c6b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180002c6b`

## pseudocode

```c
HLOCAL __fastcall DhcpMidlUserFree(void **a1)
{
  void *v2; // rcx
  HLOCAL result; // rax

  if ( a1 )
  {
    v2 = *a1;
    if ( v2 )
    {
      result = LocalFree(v2);
      *a1 = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002c50  test    rcx, rcx
0x180002c53  jz      short locret_180002C6A
0x180002c55  push    rbx
0x180002c56  sub     rsp, 20h
0x180002c5a  mov     rbx, rcx
0x180002c5d  mov     rcx, [rcx]; hMem
0x180002c60  test    rcx, rcx
0x180002c63  jnz     short loc_180002C6B
0x180002c65  add     rsp, 20h
0x180002c69  pop     rbx
0x180002c6a  retn
0x180002c6b  call    cs:__imp_LocalFree
0x180002c71  mov     qword ptr [rbx], 0
0x180002c78  jmp     short loc_180002C65
```
