# parseSetCommand

- ea: `0x1400038b8`
- end: `0x14000392c`
- name: `parseSetCommand`
- size: `116`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140002c80`

## callees

- `0x1400021cc`
- `0x1400038b8`
- `0x14000ce88`

## import_xrefs

- `msvcrt!printf` at `0x140003916`
- `msvcrt!printf` at `0x140003916`

## pseudocode

```c
__int64 __fastcall parseSetCommand(__int64 a1, __int64 a2, const char *a3, __int64 a4)
{
  __int64 result; // rax

  result = DFPParseVarAssignment(a1, a2, a3, a4);
  if ( (_DWORD)result )
  {
    if ( *(int *)(a2 + 80) >= 3 )
    {
      MsgSet(a2 + 484, 2048, "==> Setting variable %1 to '%2'", "%s%s", (const char *)(a1 + 8), (const char *)(a1 + 40));
      printf("%s\n", (const char *)(a2 + 484));
    }
    return 1;
  }
  return result;
}

```

## disassembly

```asm
0x1400038b8  mov     [rsp+arg_0], rbx
0x1400038bd  push    rdi
0x1400038be  sub     rsp, 30h
0x1400038c2  mov     rbx, rdx
0x1400038c5  mov     rdi, rcx
0x1400038c8  call    DFPParseVarAssignment
0x1400038cd  test    eax, eax
0x1400038cf  jz      short loc_140003921
0x1400038d1  cmp     dword ptr [rbx+50h], 3
0x1400038d5  jl      short loc_14000391C
0x1400038d7  lea     rax, [rdi+28h]
0x1400038db  mov     edx, 800h
0x1400038e0  lea     rcx, [rdi+8]
0x1400038e4  mov     [rsp+38h+var_10], rax
0x1400038e9  mov     [rsp+38h+var_18], rcx
0x1400038ee  lea     r9, aSS_1; "%s%s"
0x1400038f5  lea     rcx, [rbx+1E4h]
0x1400038fc  lea     r8, aSettingVariabl; "==> Setting variable %1 to '%2'"
0x140003903  call    MsgSet
0x140003908  lea     rdx, [rbx+1E4h]
0x14000390f  lea     rcx, aS_2; "%s\n"
0x140003916  call    cs:__imp_printf
0x14000391c  mov     eax, 1
0x140003921  mov     rbx, [rsp+38h+arg_0]
0x140003926  add     rsp, 30h
0x14000392a  pop     rdi
0x14000392b  retn
```
