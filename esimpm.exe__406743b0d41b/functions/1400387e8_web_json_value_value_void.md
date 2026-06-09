# web::json::value::~value(void)

- ea: `0x1400387e8`
- end: `0x14003880d`
- name: `??1value@json@web@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(web::json::value *__hidden this)`
- caller_count: `13`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14003c110`
- `0x14003c180`
- `0x14003c1c0`
- `0x14003cb2e`
- `0x14003d624`
- `0x14003d670`
- `0x14003d6a6`
- `0x14003d6ca`
- `0x14003d86b`
- `0x14003d88f`
- `0x14003d8f6`
- `0x14003d908`
- `0x14003d920`

## callees

- `0x1400387e8`
- `0x14003e010`

## pseudocode

```c
void __fastcall web::json::value::~value(web::json::value *this)
{
  __int64 v1; // rcx

  v1 = *(_QWORD *)this;
  if ( v1 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v1 + 192LL))(v1, 1);
}

```

## disassembly

```asm
0x1400387e8  sub     rsp, 28h
0x1400387ec  mov     rcx, [rcx]
0x1400387ef  test    rcx, rcx
0x1400387f2  jz      short loc_140038808
0x1400387f4  mov     rax, [rcx]
0x1400387f7  mov     edx, 1
0x1400387fc  mov     rax, [rax+0C0h]
0x140038803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140038808  add     rsp, 28h
0x14003880c  retn
```
