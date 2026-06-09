# fciOpenInfo

- ea: `0x140005ae0`
- end: `0x140005b0a`
- name: `fciOpenInfo`
- size: `42`
- prototype: `INT_PTR __cdecl(LPSTR pszName, USHORT *pdate, USHORT *ptime, USHORT *pattribs, int *err, void *pv)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140005b10`

## pseudocode

```c
INT_PTR __fastcall fciOpenInfo(
        const CHAR *pszName,
        USHORT *pdate,
        USHORT *ptime,
        USHORT *pattribs,
        int *err,
        __int64 *pv)
{
  return fciOpenInfoEx(pszName, pdate, ptime, pattribs, err, pv, 0);
}

```

## disassembly

```asm
0x140005ae0  sub     rsp, 48h
0x140005ae4  mov     rax, [rsp+48h+pv]
0x140005ae9  mov     [rsp+48h+var_18], 0; int
0x140005af1  mov     [rsp+48h+var_20], rax; void *
0x140005af6  mov     rax, [rsp+48h+err]
0x140005afb  mov     [rsp+48h+var_28], rax; err
0x140005b00  call    fciOpenInfoEx
0x140005b05  add     rsp, 48h
0x140005b09  retn
```
