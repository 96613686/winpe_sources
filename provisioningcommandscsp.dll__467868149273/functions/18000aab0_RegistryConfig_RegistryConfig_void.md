# RegistryConfig::~RegistryConfig(void)

- ea: `0x18000aab0`
- end: `0x18000aae9`
- name: `??1RegistryConfig@@QEAA@XZ`
- size: `57`
- prototype: `void __fastcall(RegistryConfig *__hidden this)`
- caller_count: `13`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callers

- `0x180006e40`
- `0x18000751c`
- `0x1800076ac`
- `0x180008a70`
- `0x1800090e0`
- `0x1800096c0`
- `0x18000d59a`
- `0x18000d5be`
- `0x18000d606`
- `0x18000d669`
- `0x18000d84c`
- `0x18000d900`
- `0x18000d990`

## callees

- `0x18000aab0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000aac4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000aac4`

## pseudocode

```c
void __fastcall RegistryConfig::~RegistryConfig(void **this)
{
  if ( (unsigned __int64)this[4] >= 8 )
    operator delete(this[1]);
  this[4] = (void *)7;
  this[3] = 0;
  *((_WORD *)this + 4) = 0;
}

```

## disassembly

```asm
0x18000aab0  push    rbx
0x18000aab2  sub     rsp, 20h
0x18000aab6  cmp     qword ptr [rcx+20h], 8
0x18000aabb  mov     rbx, rcx
0x18000aabe  jb      short loc_18000AAD0
0x18000aac0  mov     rcx, [rcx+8]
0x18000aac4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000aacb  nop     dword ptr [rax+rax+00h]
0x18000aad0  xor     eax, eax
0x18000aad2  mov     qword ptr [rbx+20h], 7
0x18000aada  mov     [rbx+18h], rax
0x18000aade  mov     [rbx+8], ax
0x18000aae2  add     rsp, 20h
0x18000aae6  pop     rbx
0x18000aae7  retn
```
