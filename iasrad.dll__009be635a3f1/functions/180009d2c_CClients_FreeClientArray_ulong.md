# CClients::FreeClientArray(ulong)

- ea: `0x180009d2c`
- end: `0x180009d80`
- name: `?FreeClientArray@CClients@@AEAAXK@Z`
- size: `84`
- prototype: `void __fastcall(CClients *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009e44`
- `0x180009f58`

## callees

- `0x180009d2c`
- `0x180030010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009d63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009d63`

## pseudocode

```c
void __fastcall CClients::FreeClientArray(CClients *this, unsigned int a2)
{
  __int64 v2; // rdi
  LPVOID *i; // rbx

  v2 = 0;
  for ( i = (LPVOID *)((char *)this + 48); (unsigned int)v2 < a2; v2 = (unsigned int)(v2 + 1) )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)*i + v2) + 16LL))(*((_QWORD *)*i + v2));
  CoTaskMemFree(*i);
  *i = 0;
}

```

## disassembly

```asm
0x180009d2c  mov     [rsp+arg_0], rbx
0x180009d31  mov     [rsp+arg_8], rsi
0x180009d36  push    rdi
0x180009d37  sub     rsp, 20h
0x180009d3b  xor     edi, edi
0x180009d3d  lea     rbx, [rcx+30h]
0x180009d41  mov     esi, edx
0x180009d43  test    edx, edx
0x180009d45  jz      short loc_180009D60
0x180009d47  mov     rax, [rbx]
0x180009d4a  mov     rcx, [rax+rdi*8]
0x180009d4e  mov     rax, [rcx]
0x180009d51  mov     rax, [rax+10h]
0x180009d55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d5a  inc     edi
0x180009d5c  cmp     edi, esi
0x180009d5e  jb      short loc_180009D47
0x180009d60  mov     rcx, [rbx]; pv
0x180009d63  call    cs:__imp_CoTaskMemFree
0x180009d69  mov     rsi, [rsp+28h+arg_8]
0x180009d6e  mov     qword ptr [rbx], 0
0x180009d75  mov     rbx, [rsp+28h+arg_0]
0x180009d7a  add     rsp, 20h
0x180009d7e  pop     rdi
0x180009d7f  retn
```
