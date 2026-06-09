# TWriteSchemaBin::~TWriteSchemaBin(void)

- ea: `0x18002324c`
- end: `0x1800232a8`
- name: `??1TWriteSchemaBin@@UEAA@XZ`
- size: `92`
- prototype: `void __fastcall(TWriteSchemaBin *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180015f34`
- `0x1800232b0`
- `0x18002e9ed`

## callees

- `0x18002324c`
- `0x180024a48`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180023268`
- `KERNEL32!LocalFree` at `0x180023295`
- `KERNEL32!LocalFree` at `0x180023268`
- `KERNEL32!LocalFree` at `0x180023295`
- `ADVAPI32!FreeSid` at `0x180023277`
- `ADVAPI32!FreeSid` at `0x180023286`
- `ADVAPI32!FreeSid` at `0x180023277`
- `ADVAPI32!FreeSid` at `0x180023286`

## pseudocode

```c
void __fastcall TWriteSchemaBin::~TWriteSchemaBin(TWriteSchemaBin *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx

  *(_QWORD *)this = &TWriteSchemaBin::`vftable';
  v2 = (void *)*((_QWORD *)this + 6);
  if ( v2 )
    LocalFree(v2);
  v3 = (void *)*((_QWORD *)this + 8);
  if ( v3 )
    FreeSid(v3);
  v4 = (void *)*((_QWORD *)this + 9);
  if ( v4 )
    FreeSid(v4);
  v5 = (void *)*((_QWORD *)this + 7);
  if ( v5 )
    LocalFree(v5);
  TFixedTableHeapBuilder::~TFixedTableHeapBuilder(this);
}

```

## disassembly

```asm
0x18002324c  push    rbx
0x18002324e  sub     rsp, 20h
0x180023252  lea     rax, ??_7TWriteSchemaBin@@6B@; const TWriteSchemaBin::`vftable'
0x180023259  mov     rbx, rcx
0x18002325c  mov     [rcx], rax
0x18002325f  mov     rcx, [rcx+30h]; hMem
0x180023263  test    rcx, rcx
0x180023266  jz      short loc_18002326E
0x180023268  call    cs:__imp_LocalFree
0x18002326e  mov     rcx, [rbx+40h]; pSid
0x180023272  test    rcx, rcx
0x180023275  jz      short loc_18002327D
0x180023277  call    cs:__imp_FreeSid
0x18002327d  mov     rcx, [rbx+48h]; pSid
0x180023281  test    rcx, rcx
0x180023284  jz      short loc_18002328C
0x180023286  call    cs:__imp_FreeSid
0x18002328c  mov     rcx, [rbx+38h]; hMem
0x180023290  test    rcx, rcx
0x180023293  jz      short loc_18002329B
0x180023295  call    cs:__imp_LocalFree
0x18002329b  mov     rcx, rbx; this
0x18002329e  add     rsp, 20h
0x1800232a2  pop     rbx
0x1800232a3  jmp     ??1TFixedTableHeapBuilder@@UEAA@XZ; TFixedTableHeapBuilder::~TFixedTableHeapBuilder(void)
```
