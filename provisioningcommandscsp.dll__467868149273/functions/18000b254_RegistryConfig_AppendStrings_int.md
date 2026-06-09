# RegistryConfig::AppendStrings(int,...)

- ea: `0x18000b254`
- end: `0x18000b2b7`
- name: `?AppendStrings@RegistryConfig@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@HZZ`
- size: `99`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000ad90`
- `0x18000b064`
- `0x18000b2c0`
- `0x18000b570`

## callees

- `0x180007d54`
- `0x18000b254`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18000b254  mov     rax, rsp
0x18000b257  mov     [rax+18h], r8d
0x18000b25b  mov     [rax+10h], rdx
0x18000b25f  mov     [rax+20h], r9
0x18000b263  push    rbx
0x18000b264  push    rsi
0x18000b265  push    rdi
0x18000b266  sub     rsp, 30h
0x18000b26a  mov     rbx, rdx
0x18000b26d  xor     ecx, ecx
0x18000b26f  mov     [rax-28h], ecx
0x18000b272  mov     qword ptr [rdx+18h], 7
0x18000b27a  mov     [rdx+10h], rcx
0x18000b27e  mov     [rdx], cx
0x18000b281  mov     dword ptr [rax-28h], 1
0x18000b288  lea     rdi, [rax+20h]
0x18000b28c  mov     esi, ecx
0x18000b28e  cmp     [rax+18h], ecx
0x18000b291  jle     short loc_18000B2AB
0x18000b293  lea     rdi, [rdi+8]
0x18000b297  mov     rdx, [rdi-8]; void *
0x18000b29b  mov     rcx, rbx; Src
0x18000b29e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18000b2a3  inc     esi
0x18000b2a5  cmp     esi, [rsp+48h+arg_10]
0x18000b2a9  jl      short loc_18000B293
0x18000b2ab  mov     rax, rbx
0x18000b2ae  add     rsp, 30h
0x18000b2b2  pop     rdi
0x18000b2b3  pop     rsi
0x18000b2b4  pop     rbx
0x18000b2b5  retn
```
