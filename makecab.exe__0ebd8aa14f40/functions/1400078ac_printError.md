# printError

- ea: `0x1400078ac`
- end: `0x14000792e`
- name: `printError`
- size: `130`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x140003f68`
- `0x14000463c`
- `0x1400062e0`
- `0x1400064c0`
- `0x140006a6c`
- `0x140007934`

## callees

- `0x1400078ac`

## import_xrefs

- `msvcrt!printf` at `0x1400078ce`
- `msvcrt!printf` at `0x140007901`
- `msvcrt!printf` at `0x14000791a`
- `msvcrt!printf` at `0x1400078ce`
- `msvcrt!printf` at `0x140007901`
- `msvcrt!printf` at `0x14000791a`

## pseudocode

```c
int __fastcall printError(__int64 a1, __int64 a2)
{
  const char *v4; // rdx
  int result; // eax

  if ( a1 )
  {
    if ( *(_DWORD *)(a1 + 108) )
    {
      printf("\n");
      *(_DWORD *)(a1 + 108) = 0;
    }
    v4 = *(const char **)(a2 + 520);
    if ( v4 )
      result = printf("%s(%d): %s: %s\n", v4, *(_DWORD *)(a2 + 528), "ERROR", (const char *)a2);
    else
      result = printf("%s: %s\n", "ERROR", (const char *)a2);
    ++*(_DWORD *)(a1 + 72);
  }
  return result;
}

```

## disassembly

```asm
0x1400078ac  test    rcx, rcx
0x1400078af  jz      short locret_14000792D
0x1400078b1  mov     [rsp+arg_0], rbx
0x1400078b6  push    rdi
0x1400078b7  sub     rsp, 30h
0x1400078bb  cmp     dword ptr [rcx+6Ch], 0
0x1400078bf  mov     rdi, rdx
0x1400078c2  mov     rbx, rcx
0x1400078c5  jz      short loc_1400078DB
0x1400078c7  lea     rcx, asc_140012F58; "\n"
0x1400078ce  call    cs:__imp_printf
0x1400078d4  mov     dword ptr [rbx+6Ch], 0
0x1400078db  mov     rdx, [rdi+208h]
0x1400078e2  test    rdx, rdx
0x1400078e5  jz      short loc_140007909
0x1400078e7  mov     r8d, [rdi+210h]
0x1400078ee  lea     r9, aError; "ERROR"
0x1400078f5  lea     rcx, aSDSS; "%s(%d): %s: %s\n"
0x1400078fc  mov     [rsp+38h+var_18], rdi
0x140007901  call    cs:__imp_printf
0x140007907  jmp     short loc_140007920
0x140007909  mov     r8, rdi
0x14000790c  lea     rdx, aError; "ERROR"
0x140007913  lea     rcx, aSS; "%s: %s\n"
0x14000791a  call    cs:__imp_printf
0x140007920  inc     dword ptr [rbx+48h]
0x140007923  mov     rbx, [rsp+38h+arg_0]
0x140007928  add     rsp, 30h
0x14000792c  pop     rdi
0x14000792d  retn
```
