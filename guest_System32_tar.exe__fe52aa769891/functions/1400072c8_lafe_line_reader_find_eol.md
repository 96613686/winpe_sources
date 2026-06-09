# lafe_line_reader_find_eol

- ea: `0x1400072c8`
- end: `0x14000730e`
- name: `lafe_line_reader_find_eol`
- size: `70`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140007314`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x1400072f2`
- `api-ms-win-crt-string-l1-1-0!strcspn` at `0x1400072f2`

## pseudocode

```c
size_t __fastcall lafe_line_reader_find_eol(__int64 a1)
{
  __int64 v1; // rbx
  const char *v2; // rdx
  size_t result; // rax

  v1 = *(_QWORD *)(a1 + 32);
  v2 = (const char *)&unk_14000A36F;
  if ( !*(_DWORD *)(a1 + 56) )
    v2 = "\r\n";
  result = strcspn(*(const char **)(a1 + 32), v2);
  *(_QWORD *)(a1 + 32) = result + v1;
  *(_BYTE *)(result + v1) = 0;
  return result;
}

```

## disassembly

```asm
0x1400072c8  mov     [rsp+arg_0], rbx
0x1400072cd  push    rdi
0x1400072ce  sub     rsp, 20h
0x1400072d2  cmp     dword ptr [rcx+38h], 0
0x1400072d6  lea     rax, Control; "\r\n"
0x1400072dd  mov     rbx, [rcx+20h]
0x1400072e1  lea     rdx, unk_14000A36F
0x1400072e8  mov     rdi, rcx
0x1400072eb  cmovz   rdx, rax; Control
0x1400072ef  mov     rcx, rbx; Str
0x1400072f2  call    cs:__imp_strcspn
0x1400072f8  lea     rdx, [rax+rbx]
0x1400072fc  mov     rbx, [rsp+28h+arg_0]
0x140007301  mov     [rdi+20h], rdx
0x140007305  mov     byte ptr [rdx], 0
0x140007308  add     rsp, 20h
0x14000730c  pop     rdi
0x14000730d  retn
```
