# ReleaseCachedFrame(_MCIGRAPHIC *)

- ea: `0x1800041fc`
- end: `0x180004234`
- name: `?ReleaseCachedFrame@@YAJPEAU_MCIGRAPHIC@@@Z`
- size: `56`
- prototype: `__int64 __fastcall(struct _MCIGRAPHIC *)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180001f60`
- `0x180003a04`
- `0x18000443c`

## callees

- `0x180001008`
- `0x1800041fc`

## pseudocode

```c
__int64 __fastcall ReleaseCachedFrame(struct _MCIGRAPHIC *a1)
{
  void *v2; // rcx
  __int64 result; // rax

  v2 = (void *)*((_QWORD *)a1 + 75);
  if ( v2 )
    operator delete[](v2);
  *((_QWORD *)a1 + 75) = 0;
  result = 0;
  *((_QWORD *)a1 + 76) = 0;
  return result;
}

```

## disassembly

```asm
0x1800041fc  push    rbx
0x1800041fe  sub     rsp, 20h
0x180004202  mov     rbx, rcx
0x180004205  mov     rcx, [rcx+258h]; void *
0x18000420c  test    rcx, rcx
0x18000420f  jz      short loc_180004216
0x180004211  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x180004216  mov     qword ptr [rbx+258h], 0
0x180004221  xor     eax, eax
0x180004223  mov     qword ptr [rbx+260h], 0
0x18000422e  add     rsp, 20h
0x180004232  pop     rbx
0x180004233  retn
```
