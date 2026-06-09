# RleCompressBegin

- ea: `0x18000241c`
- end: `0x180002495`
- name: `RleCompressBegin`
- size: `121`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001cd0`
- `0x180002250`

## callees

- `0x18000241c`
- `0x18000257c`
- `0x180003420`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180002449`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000245b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x180002449`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalHandle` at `0x18000245b`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180002452`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180002452`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180002464`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180002464`

## pseudocode

```c
__int64 __fastcall RleCompressBegin(__int64 a1, __int64 a2)
{
  __int64 result; // rax
  const void **v5; // rcx
  const void *v6; // rcx
  HGLOBAL v7; // rax
  HGLOBAL v8; // rax

  result = RleCompressQuery();
  if ( !(_DWORD)result )
  {
    if ( v5 )
    {
      v6 = *v5;
      if ( v6 )
      {
        v7 = GlobalHandle(v6);
        GlobalUnlock(v7);
        v8 = GlobalHandle(*(LPCVOID *)a1);
        GlobalFree(v8);
        *(_QWORD *)a1 = 0;
      }
      *(_QWORD *)(a1 + 8) = 0;
      *(_DWORD *)(a1 + 44) = 1;
      MakeRgbTable(a2);
      return 0;
    }
    else
    {
      return 4294967288LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000241c  mov     [rsp+arg_0], rbx
0x180002421  push    rdi
0x180002422  sub     rsp, 20h
0x180002426  mov     rdi, rdx
0x180002429  mov     rbx, rcx
0x18000242c  call    RleCompressQuery
0x180002431  test    eax, eax
0x180002433  jnz     short loc_18000248A
0x180002435  test    rcx, rcx
0x180002438  jnz     short loc_180002441
0x18000243a  mov     eax, 0FFFFFFF8h
0x18000243f  jmp     short loc_18000248A
0x180002441  mov     rcx, [rcx]; pMem
0x180002444  test    rcx, rcx
0x180002447  jz      short loc_180002471
0x180002449  call    cs:__imp_GlobalHandle
0x18000244f  mov     rcx, rax; hMem
0x180002452  call    cs:__imp_GlobalUnlock
0x180002458  mov     rcx, [rbx]; pMem
0x18000245b  call    cs:__imp_GlobalHandle
0x180002461  mov     rcx, rax; hMem
0x180002464  call    cs:__imp_GlobalFree
0x18000246a  mov     qword ptr [rbx], 0
0x180002471  mov     rcx, rdi
0x180002474  mov     qword ptr [rbx+8], 0
0x18000247c  mov     dword ptr [rbx+2Ch], 1
0x180002483  call    MakeRgbTable
0x180002488  xor     eax, eax
0x18000248a  mov     rbx, [rsp+28h+arg_0]
0x18000248f  add     rsp, 20h
0x180002493  pop     rdi
0x180002494  retn
```
