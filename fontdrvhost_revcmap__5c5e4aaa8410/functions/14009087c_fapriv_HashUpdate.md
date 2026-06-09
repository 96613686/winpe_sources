# fapriv_HashUpdate

- ea: `0x14009087c`
- end: `0x140090894`
- name: `fapriv_HashUpdate`
- size: `24`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140090440`
- `0x14009049c`

## callees

- `0x1400910ec`

## pseudocode

```c
__int64 __fastcall fapriv_HashUpdate(_DWORD *a1, char *a2, unsigned int a3)
{
  return (unsigned int)sha1_update(a1, a2, a3) != 0 ? 0xFFFFFFFB : 0;
}

```

## disassembly

```asm
0x14009087c  sub     rsp, 28h
0x140090880  mov     r8d, r8d
0x140090883  call    sha1_update
0x140090888  neg     eax
0x14009088a  sbb     eax, eax
0x14009088c  and     eax, 0FFFFFFFBh
0x14009088f  add     rsp, 28h
0x140090893  retn
```
