# CIISGlobalModule::Terminate(void)

- ea: `0x180002470`
- end: `0x1800024c8`
- name: `?Terminate@CIISGlobalModule@@UEAAXXZ`
- size: `88`
- prototype: `void __fastcall(CIISGlobalModule *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180001530`
- `0x1800015f0`
- `0x180002470`

## import_xrefs

- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x18000249d`
- `iisutil!??1CLKRHashTable@@QEAA@XZ` at `0x18000249d`

## pseudocode

```c
void __fastcall CIISGlobalModule::Terminate(CIISGlobalModule *this)
{
  PVOID v2; // rbx

  if ( g_pTokenCache )
  {
    TOKEN_CACHE::Terminate((TOKEN_CACHE *)g_pTokenCache);
    v2 = g_pTokenCache;
    if ( g_pTokenCache )
    {
      CLKRHashTable::~CLKRHashTable((CLKRHashTable *)g_pTokenCache);
      operator delete(v2);
    }
    g_pTokenCache = 0;
  }
  operator delete(this);
}

```

## disassembly

```asm
0x180002470  mov     [rsp+arg_0], rbx
0x180002475  push    rdi
0x180002476  sub     rsp, 20h
0x18000247a  mov     rdi, rcx
0x18000247d  mov     rcx, cs:?g_pTokenCache@@3PEAVTOKEN_CACHE@@EA; this
0x180002484  test    rcx, rcx
0x180002487  jz      short loc_1800024B6
0x180002489  call    ?Terminate@TOKEN_CACHE@@QEAAXXZ; TOKEN_CACHE::Terminate(void)
0x18000248e  mov     rbx, cs:?g_pTokenCache@@3PEAVTOKEN_CACHE@@EA; TOKEN_CACHE * g_pTokenCache
0x180002495  test    rbx, rbx
0x180002498  jz      short loc_1800024AB
0x18000249a  mov     rcx, rbx
0x18000249d  call    cs:__imp_??1CLKRHashTable@@QEAA@XZ; CLKRHashTable::~CLKRHashTable(void)
0x1800024a3  mov     rcx, rbx; Block
0x1800024a6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800024ab  mov     cs:?g_pTokenCache@@3PEAVTOKEN_CACHE@@EA, 0; TOKEN_CACHE * g_pTokenCache
0x1800024b6  mov     rcx, rdi; Block
0x1800024b9  mov     rbx, [rsp+28h+arg_0]
0x1800024be  add     rsp, 20h
0x1800024c2  pop     rdi
0x1800024c3  jmp     ??3@YAXPEAX@Z; operator delete(void *)
```
