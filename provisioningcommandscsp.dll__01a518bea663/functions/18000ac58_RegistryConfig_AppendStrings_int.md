# RegistryConfig::AppendStrings(int,...)

- ea: `0x18000ac58`
- end: `0x18000acbb`
- name: `?AppendStrings@RegistryConfig@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HZZ`
- size: `99`
- prototype: `_QWORD *(__int64, _QWORD *, int, ...)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000a7f8`
- `0x18000aa94`
- `0x18000acc4`
- `0x18000af48`

## callees

- `0x1800079c0`
- `0x18000ac58`

## pseudocode

```c
_QWORD *RegistryConfig::AppendStrings(__int64 a1, _QWORD *a2, int a3, ...)
{
  va_list v4; // rdi
  int i; // esi
  va_list va; // [rsp+68h] [rbp+20h] BYREF

  va_start(va, a3);
  a2[3] = 7;
  a2[2] = 0;
  *(_WORD *)a2 = 0;
  va_copy(v4, va);
  for ( i = 0; i < a3; ++i )
  {
    v4 += 8;
    std::wstring::append(a2, *((void **)v4 - 1));
  }
  return a2;
}

```

## disassembly

```asm
0x18000ac58  mov     rax, rsp
0x18000ac5b  mov     [rax+18h], r8d
0x18000ac5f  mov     [rax+10h], rdx
0x18000ac63  mov     [rax+20h], r9
0x18000ac67  push    rbx
0x18000ac68  push    rsi
0x18000ac69  push    rdi
0x18000ac6a  sub     rsp, 30h
0x18000ac6e  mov     rbx, rdx
0x18000ac71  xor     ecx, ecx
0x18000ac73  mov     [rax-28h], ecx
0x18000ac76  mov     qword ptr [rdx+18h], 7
0x18000ac7e  mov     [rdx+10h], rcx
0x18000ac82  mov     [rdx], cx
0x18000ac85  mov     dword ptr [rax-28h], 1
0x18000ac8c  lea     rdi, [rax+20h]
0x18000ac90  mov     esi, ecx
0x18000ac92  cmp     [rax+18h], ecx
0x18000ac95  jle     short loc_18000ACAF
0x18000ac97  lea     rdi, [rdi+8]
0x18000ac9b  mov     rdx, [rdi-8]; void *
0x18000ac9f  mov     rcx, rbx; Src
0x18000aca2  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18000aca7  inc     esi
0x18000aca9  cmp     esi, [rsp+48h+arg_10]
0x18000acad  jl      short loc_18000AC97
0x18000acaf  mov     rax, rbx
0x18000acb2  add     rsp, 30h
0x18000acb6  pop     rdi
0x18000acb7  pop     rsi
0x18000acb8  pop     rbx
0x18000acb9  retn
```
