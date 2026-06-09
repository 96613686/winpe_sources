# DhcpMidlUserFree

- ea: `0x180002650`
- end: `0x180002678`
- name: `DhcpMidlUserFree`
- size: `40`
- prototype: `HLOCAL __fastcall(void **)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x180001010`
- `0x180004c40`
- `0x180004cc0`
- `0x180004e10`
- `0x180005270`
- `0x180005640`
- `0x180005ec0`
- `0x1800062f0`
- `0x180006820`

## callees

- `0x180002650`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002665`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180002665`

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
0x180002650  test    rcx, rcx
0x180002653  jz      short locret_180002677
0x180002655  push    rbx
0x180002656  sub     rsp, 20h
0x18000265a  mov     rbx, rcx
0x18000265d  mov     rcx, [rcx]; hMem
0x180002660  test    rcx, rcx
0x180002663  jz      short loc_180002672
0x180002665  call    cs:__imp_LocalFree
0x18000266b  mov     qword ptr [rbx], 0
0x180002672  add     rsp, 20h
0x180002676  pop     rbx
0x180002677  retn
```
