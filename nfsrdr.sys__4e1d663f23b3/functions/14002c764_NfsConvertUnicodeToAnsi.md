# NfsConvertUnicodeToAnsi

- ea: `0x14002c764`
- end: `0x14002c84e`
- name: `NfsConvertUnicodeToAnsi`
- size: `234`
- prototype: `NTSTATUS __fastcall(int, struct _STRING *, const UNICODE_STRING *, __int64, int)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x140003510`
- `0x140004530`
- `0x14000e940`
- `0x14000f274`
- `0x14000fbc0`
- `0x1400124ec`
- `0x1400196a8`

## callees

- `0x14002c764`
- `0x14002c854`

## import_xrefs

- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x14002c83c`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x14002c83c`

## pseudocode

```c
NTSTATUS __fastcall NfsConvertUnicodeToAnsi(int a1, struct _STRING *a2, const UNICODE_STRING *a3, __int64 a4, int a5)
{
  if ( (a5 & 0x14000) != 0 )
    return NfsConvertUnicodeToDbcs(a1, (int)a2, (int)a3, (int)a3, &KscTableInfo, (__int64)&KscTableBase, 949);
  if ( (a5 & 0x8040) != 0 )
    return NfsConvertUnicodeToDbcs(a1, (int)a2, (int)a3, (int)a3, &ShiftJisTableInfo, (__int64)&ShiftJisTableBase, 932);
  if ( (a5 & 0x20000) != 0 )
    return NfsConvertUnicodeToDbcs(a1, (int)a2, (int)a3, (int)a3, &Big5TableInfo, (__int64)&Big5TableBase, 950);
  if ( (a5 & 0x2000) != 0 )
    return NfsConvertUnicodeToDbcs(a1, (int)a2, (int)a3, (int)a3, &CnsTableInfo, (__int64)&CnsTableBase, 20000);
  if ( (a5 & 0x40000) != 0 )
    return NfsConvertUnicodeToDbcs(a1, (int)a2, (int)a3, (int)a3, &GBTableInfo, (__int64)&GBTableBase, 936);
  return RtlUnicodeStringToAnsiString(a2, a3, 0);
}

```

## disassembly

```asm
0x14002c764  sub     rsp, 48h
0x14002c768  mov     eax, [rsp+48h+arg_20]
0x14002c76c  mov     r9, r8; int
0x14002c76f  mov     r10, rdx
0x14002c772  test    eax, 14000h
0x14002c777  jz      short loc_14002C7A3
0x14002c779  lea     rax, KscTableBase
0x14002c780  mov     [rsp+48h+var_18], 3B5h; int
0x14002c788  mov     [rsp+48h+var_20], rax; __int64
0x14002c78d  lea     rax, KscTableInfo
0x14002c794  mov     [rsp+48h+CustomCP], rax; CustomCP
0x14002c799  call    NfsConvertUnicodeToDbcs
0x14002c79e  jmp     loc_14002C848
0x14002c7a3  test    eax, 8040h
0x14002c7a8  jz      short loc_14002C7C7
0x14002c7aa  lea     rax, ShiftJisTableBase
0x14002c7b1  mov     [rsp+48h+var_18], 3A4h
0x14002c7b9  mov     [rsp+48h+var_20], rax
0x14002c7be  lea     rax, ShiftJisTableInfo
0x14002c7c5  jmp     short loc_14002C794
0x14002c7c7  bt      eax, 11h
0x14002c7cb  jnb     short loc_14002C7EA
0x14002c7cd  lea     rax, Big5TableBase
0x14002c7d4  mov     [rsp+48h+var_18], 3B6h
0x14002c7dc  mov     [rsp+48h+var_20], rax
0x14002c7e1  lea     rax, Big5TableInfo
0x14002c7e8  jmp     short loc_14002C794
0x14002c7ea  bt      eax, 0Dh
0x14002c7ee  jnb     short loc_14002C80D
0x14002c7f0  lea     rax, CnsTableBase
0x14002c7f7  mov     [rsp+48h+var_18], 4E20h
0x14002c7ff  mov     [rsp+48h+var_20], rax
0x14002c804  lea     rax, CnsTableInfo
0x14002c80b  jmp     short loc_14002C794
0x14002c80d  bt      eax, 12h
0x14002c811  jnb     short loc_14002C833
0x14002c813  lea     rax, GBTableBase
0x14002c81a  mov     [rsp+48h+var_18], 3A8h
0x14002c822  mov     [rsp+48h+var_20], rax
0x14002c827  lea     rax, GBTableInfo
0x14002c82e  jmp     loc_14002C794
0x14002c833  xor     r8d, r8d; AllocateDestinationString
0x14002c836  mov     rdx, r9; SourceString
0x14002c839  mov     rcx, r10; DestinationString
0x14002c83c  call    cs:__imp_RtlUnicodeStringToAnsiString
0x14002c843  nop     dword ptr [rax+rax+00h]
0x14002c848  add     rsp, 48h
0x14002c84c  retn
```
