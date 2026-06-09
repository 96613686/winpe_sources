# XList<CQueueBase,16>::remove(CQueueBase *)

- ea: `0x14001a7d0`
- end: `0x14001a805`
- name: `?remove@?$XList@VCQueueBase@@$0BA@@@QEAAXPEAVCQueueBase@@@Z`
- size: `53`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x14001a09c`
- `0x14001a670`
- `0x14001a6c0`

## callees

- `0x14001a7d0`

## pseudocode

```c
_QWORD *__fastcall XList<CQueueBase,16>::remove(__int64 a1, __int64 a2)
{
  _QWORD *v2; // rdx
  __int64 v3; // rcx
  _QWORD *result; // rax

  v2 = (_QWORD *)(a2 + 16);
  v3 = *v2;
  if ( *(_QWORD **)(*v2 + 8LL) != v2 || (result = (_QWORD *)v2[1], (_QWORD *)*result != v2) )
    __fastfail(3u);
  *result = v3;
  *(_QWORD *)(v3 + 8) = result;
  *v2 = 0;
  v2[1] = 0;
  return result;
}

```

## disassembly

```asm
0x14001a7d0  add     rdx, 10h
0x14001a7d4  mov     rcx, [rdx]
0x14001a7d7  cmp     [rcx+8], rdx
0x14001a7db  jnz     short loc_14001A7FE
0x14001a7dd  mov     rax, [rdx+8]
0x14001a7e1  cmp     [rax], rdx
0x14001a7e4  jnz     short loc_14001A7FE
0x14001a7e6  mov     [rax], rcx
0x14001a7e9  mov     [rcx+8], rax
0x14001a7ed  mov     qword ptr [rdx], 0
0x14001a7f4  mov     qword ptr [rdx+8], 0
0x14001a7fc  retn
0x14001a7fe  mov     ecx, 3
0x14001a803  int     29h; Win8: RtlFailFast(ecx)
```
