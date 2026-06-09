# _dynamic_atexit_destructor_for__g_szCommandLine__

- ea: `0x140009a60`
- end: `0x140009a9a`
- name: `_dynamic_atexit_destructor_for__g_szCommandLine__`
- size: `58`
- prototype: `__int64 *()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140009a60`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x140009a77`
- `KERNEL32!GlobalFree` at `0x140009a77`

## pseudocode

```c
__int64 *dynamic_atexit_destructor_for__g_szCommandLine__()
{
  __int64 *result; // rax

  if ( dword_14000F0C8 > 1024 )
    GlobalFree((HGLOBAL)g_szCommandLine);
  result = qword_14000F0D0;
  dword_14000F0C8 = 1024;
  g_szCommandLine = (LPCWSTR)qword_14000F0D0;
  return result;
}

```

## disassembly

```asm
0x140009a60  sub     rsp, 28h
0x140009a64  cmp     cs:dword_14000F0C8, 400h
0x140009a6e  jle     short loc_140009A7D
0x140009a70  mov     rcx, cs:?g_szCommandLine@@3V?$CAPITempBuffer@G$0EAA@@@A; hMem
0x140009a77  call    cs:__imp_GlobalFree
0x140009a7d  lea     rax, qword_14000F0D0
0x140009a84  mov     cs:dword_14000F0C8, 400h
0x140009a8e  mov     cs:?g_szCommandLine@@3V?$CAPITempBuffer@G$0EAA@@@A, rax; CAPITempBuffer<ushort,1024> g_szCommandLine
0x140009a95  add     rsp, 28h
0x140009a99  retn
```
