# VARY_BY_CACHE::CacheFlushByFileChange(void *,void *)

- ea: `0x180007660`
- end: `0x180007697`
- name: `?CacheFlushByFileChange@VARY_BY_CACHE@@SAHPEAX0@Z`
- size: `55`
- prototype: `static int(void *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180007660`
- `0x180008bca`

## pseudocode

```c
_BOOL8 __fastcall VARY_BY_CACHE::CacheFlushByFileChange(const wchar_t **a1, const wchar_t *a2)
{
  size_t v2; // r8

  v2 = -1;
  do
    ++v2;
  while ( a2[v2] );
  return wcsncmp_0(a2, a1[46], v2) == 0;
}

```

## disassembly

```asm
0x180007660  push    rbx
0x180007662  sub     rsp, 20h
0x180007666  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000766a  mov     rax, rdx
0x18000766d  xor     ebx, ebx
0x18000766f  inc     r8; MaxCount
0x180007672  cmp     [rdx+r8*2], bx
0x180007677  jnz     short loc_18000766F
0x180007679  mov     rdx, [rcx+170h]; String2
0x180007680  mov     rcx, rax; String1
0x180007683  call    wcsncmp_0
0x180007688  test    eax, eax
0x18000768a  mov     ecx, ebx
0x18000768c  setz    cl
0x18000768f  mov     eax, ecx
0x180007691  add     rsp, 20h
0x180007695  pop     rbx
0x180007696  retn
```
