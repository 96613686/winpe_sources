# CCfgArray<TMetabase_XMLtable::TLocation>::AllocNewSize(ulong)

- ea: `0x18000654c`
- end: `0x180006602`
- name: `?AllocNewSize@?$CCfgArray@VTLocation@TMetabase_XMLtable@@@@AEAAJK@Z`
- size: `182`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18000bf74`
- `0x18000e128`

## callees

- `0x180001d04`
- `0x180005ba4`
- `0x180005c48`
- `0x18000654c`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180006578`
- `ole32!CoTaskMemAlloc` at `0x180006578`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CCfgArray<TMetabase_XMLtable::TLocation>::AllocNewSize(__int64 a1, unsigned int a2)
{
  __int64 v2; // rbp
  __int64 v4; // rax
  bool v5; // cf
  SIZE_T v6; // rax
  _QWORD *v7; // rax
  unsigned int v8; // edx
  _QWORD *v9; // rdi
  __int64 i; // rsi

  v2 = a2;
  v4 = 24LL * a2;
  if ( !is_mul_ok(a2, 0x18u) )
    v4 = -1;
  v5 = __CFADD__(v4, 8);
  v6 = v4 + 8;
  if ( v5 )
    v6 = -1;
  v7 = CoTaskMemAlloc(v6);
  if ( v7 )
  {
    *v7 = v2;
    v9 = v7 + 1;
    `eh vector constructor iterator'(
      v7 + 1,
      0x18u,
      (unsigned int)v2,
      (void (*)(void *))TMetabase_XMLtable::TLocation::TLocation,
      (void (*)(void *))TGrowableBuffer::~TGrowableBuffer);
  }
  else
  {
    v9 = 0;
  }
  if ( !v9 )
    return 2147942414LL;
  for ( i = 0; (unsigned int)i < *(_DWORD *)(a1 + 8); i = (unsigned int)(i + 1) )
    TMetabase_XMLtable::TLocation::operator=((__int64)&v9[3 * i], *(_QWORD *)a1 + 24 * i);
  if ( *(_QWORD *)a1 )
    TMetabase_XMLtable::TLocation::`vector deleting destructor'(*(TMetabase_XMLtable::TLocation **)a1, v8);
  *(_QWORD *)a1 = v9;
  *(_DWORD *)(a1 + 8) = v2;
  return 0;
}

```

## disassembly

```asm
0x18000654c  push    rbx
0x18000654e  push    rbp
0x18000654f  push    rsi
0x180006550  push    rdi
0x180006551  sub     rsp, 38h
0x180006555  mov     ebp, edx
0x180006557  mov     rbx, rcx
0x18000655a  mov     eax, 18h
0x18000655f  mul     rbp
0x180006562  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180006569  cmovb   rax, rcx
0x18000656d  add     rax, 8
0x180006571  cmovb   rax, rcx
0x180006575  mov     rcx, rax; cb
0x180006578  call    cs:__imp_CoTaskMemAlloc
0x18000657e  mov     [rsp+58h+arg_10], rax
0x180006583  test    rax, rax
0x180006586  jz      short loc_1800065B4
0x180006588  mov     [rax], rbp
0x18000658b  lea     rdi, [rax+8]
0x18000658f  lea     rax, ??1TGrowableBuffer@@QEAA@XZ; TGrowableBuffer::~TGrowableBuffer(void)
0x180006596  mov     [rsp+58h+var_38], rax; void (*)(void *)
0x18000659b  lea     r9, ??0TLocation@TMetabase_XMLtable@@QEAA@XZ; void (*)(void *)
0x1800065a2  mov     r8d, ebp; unsigned __int64
0x1800065a5  mov     edx, 18h; unsigned __int64
0x1800065aa  mov     rcx, rdi; void *
0x1800065ad  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x1800065b2  jmp     short loc_1800065B6
0x1800065b4  xor     edi, edi
0x1800065b6  test    rdi, rdi
0x1800065b9  jnz     short loc_1800065C2
0x1800065bb  mov     eax, 8007000Eh
0x1800065c0  jmp     short loc_1800065F9
0x1800065c2  xor     esi, esi
0x1800065c4  cmp     [rbx+8], esi
0x1800065c7  jbe     short loc_1800065E4
0x1800065c9  lea     rcx, [rsi+rsi*2]
0x1800065cd  mov     rax, [rbx]
0x1800065d0  lea     rdx, [rax+rcx*8]
0x1800065d4  lea     rcx, [rdi+rcx*8]
0x1800065d8  call    ??4TLocation@TMetabase_XMLtable@@QEAAAEAV01@AEBV01@@Z; TMetabase_XMLtable::TLocation::operator=(TMetabase_XMLtable::TLocation const &)
0x1800065dd  inc     esi
0x1800065df  cmp     esi, [rbx+8]
0x1800065e2  jb      short loc_1800065C9
0x1800065e4  mov     rcx, [rbx]; this
0x1800065e7  test    rcx, rcx
0x1800065ea  jz      short loc_1800065F1
0x1800065ec  call    ??_ETLocation@TMetabase_XMLtable@@QEAAPEAXI@Z; TMetabase_XMLtable::TLocation::`vector deleting destructor'(uint)
0x1800065f1  mov     [rbx], rdi
0x1800065f4  mov     [rbx+8], ebp
0x1800065f7  xor     eax, eax
0x1800065f9  add     rsp, 38h
0x1800065fd  pop     rdi
0x1800065fe  pop     rsi
0x1800065ff  pop     rbp
0x180006600  pop     rbx
0x180006601  retn
```
