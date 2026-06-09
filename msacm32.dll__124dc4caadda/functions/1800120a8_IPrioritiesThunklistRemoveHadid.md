# IPrioritiesThunklistRemoveHadid

- ea: `0x1800120a8`
- end: `0x1800120e3`
- name: `IPrioritiesThunklistRemoveHadid`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001570`

## callees

- `0x1800120a8`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800120d8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800120d8`

## pseudocode

```c
char *__fastcall IPrioritiesThunklistRemoveHadid(char *a1, __int64 a2)
{
  char *result; // rax
  __int64 v3; // rdx

  for ( result = *(char **)(a1 + 12); result && a2 != *(_QWORD *)(result + 4); result = *(char **)(result + 12) )
    a1 = result;
  v3 = *(_QWORD *)(a1 + 12);
  if ( v3 )
  {
    *(_QWORD *)(a1 + 12) = *(_QWORD *)(v3 + 12);
    return (char *)LocalFree((HLOCAL)v3);
  }
  return result;
}

```

## disassembly

```asm
0x1800120a8  sub     rsp, 28h
0x1800120ac  mov     rax, [rcx+0Ch]
0x1800120b0  jmp     short loc_1800120BF
0x1800120b2  cmp     rdx, [rax+4]
0x1800120b6  jz      short loc_1800120C4
0x1800120b8  mov     rcx, rax
0x1800120bb  mov     rax, [rax+0Ch]
0x1800120bf  test    rax, rax
0x1800120c2  jnz     short loc_1800120B2
0x1800120c4  mov     rdx, [rcx+0Ch]
0x1800120c8  test    rdx, rdx
0x1800120cb  jz      short loc_1800120DE
0x1800120cd  mov     rax, [rdx+0Ch]
0x1800120d1  mov     [rcx+0Ch], rax
0x1800120d5  mov     rcx, rdx; hMem
0x1800120d8  call    cs:__imp_LocalFree
0x1800120de  add     rsp, 28h
0x1800120e2  retn
```
