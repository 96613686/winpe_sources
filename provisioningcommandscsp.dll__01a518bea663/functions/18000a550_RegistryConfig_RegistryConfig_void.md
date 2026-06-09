# RegistryConfig::~RegistryConfig(void)

- ea: `0x18000a550`
- end: `0x18000a582`
- name: `??1RegistryConfig@@QEAA@XZ`
- size: `50`
- prototype: `void __fastcall(void **this)`
- caller_count: `13`
- callee_count: `1`
- tags: `file_ops, registry_config`

## callers

- `0x180006b10`
- `0x1800071d8`
- `0x180007360`
- `0x180008670`
- `0x180008cc0`
- `0x180009290`
- `0x18000ced4`
- `0x18000cef8`
- `0x18000cf40`
- `0x18000cfa3`
- `0x18000d180`
- `0x18000d234`
- `0x18000d2c4`

## callees

- `0x18000a550`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000a564`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a564`

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
0x18000a550  push    rbx
0x18000a552  sub     rsp, 20h
0x18000a556  cmp     qword ptr [rcx+20h], 8
0x18000a55b  mov     rbx, rcx
0x18000a55e  jb      short loc_18000A56A
0x18000a560  mov     rcx, [rcx+8]
0x18000a564  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a56a  xor     eax, eax
0x18000a56c  mov     qword ptr [rbx+20h], 7
0x18000a574  mov     [rbx+18h], rax
0x18000a578  mov     [rbx+8], ax
0x18000a57c  add     rsp, 20h
0x18000a580  pop     rbx
0x18000a581  retn
```
