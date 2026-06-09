# TlsCloseRegKey

- ea: `0x180012d6c`
- end: `0x180012d90`
- name: `TlsCloseRegKey`
- size: `36`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001d8e8`
- `0x180023e34`
- `0x180024190`
- `0x180024650`
- `0x180024a3c`

## callees

- `0x180012d6c`

## import_xrefs

- `ntdll!NtClose` at `0x180012d7d`
- `ntdll!NtClose` at `0x180012d7d`

## pseudocode

```c
NTSTATUS __fastcall TlsCloseRegKey(void **a1)
{
  void *v2; // rcx
  NTSTATUS result; // eax

  v2 = *a1;
  if ( v2 )
  {
    result = NtClose(v2);
    *a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180012d6c  push    rbx
0x180012d6e  sub     rsp, 20h
0x180012d72  mov     rbx, rcx
0x180012d75  mov     rcx, [rcx]; Handle
0x180012d78  test    rcx, rcx
0x180012d7b  jz      short loc_180012D8A
0x180012d7d  call    cs:__imp_NtClose
0x180012d83  mov     qword ptr [rbx], 0
0x180012d8a  add     rsp, 20h
0x180012d8e  pop     rbx
0x180012d8f  retn
```
