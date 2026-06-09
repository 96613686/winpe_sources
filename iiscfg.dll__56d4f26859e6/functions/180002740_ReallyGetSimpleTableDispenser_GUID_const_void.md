# ReallyGetSimpleTableDispenser(_GUID const &,void * *)

- ea: `0x180002740`
- end: `0x180002877`
- name: `?ReallyGetSimpleTableDispenser@@YAJAEBU_GUID@@PEAPEAX@Z`
- size: `311`
- prototype: `__int64 __fastcall(const struct _GUID *, void **)`
- caller_count: `3`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180002950`
- `0x180002970`
- `0x180002af0`

## callees

- `0x180002740`
- `0x180003ed0`
- `0x1800117b4`
- `0x1800117f8`
- `0x1800154b4`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1800027ab`
- `ole32!CoTaskMemAlloc` at `0x1800027ab`

## pseudocode

```c
__int64 __fastcall ReallyGetSimpleTableDispenser(const struct _GUID *a1, void **a2)
{
  CSimpleTableDispenser *v4; // rcx
  int v5; // eax
  unsigned int v6; // ebx
  _QWORD *v7; // rax
  CSimpleTableDispenser *v8; // rbx
  unsigned int v9; // eax
  int v11; // [rsp+20h] [rbp-18h] BYREF
  _RTL_CRITICAL_SECTION *v12; // [rsp+28h] [rbp-10h]

  v4 = g_pSimpleTableDispenser;
  if ( !g_pSimpleTableDispenser )
  {
    v11 = 0;
    v12 = &g_csSADispenser;
    v5 = CSafeLock::Lock((CSafeLock *)&v11);
    v6 = v5;
    if ( v5 )
    {
      if ( v5 > 0 )
        v6 = (unsigned __int16)v5 | 0x80070000;
      goto LABEL_10;
    }
    if ( !g_pSimpleTableDispenser )
    {
      v7 = CoTaskMemAlloc(0xA48u);
      v8 = (CSimpleTableDispenser *)v7;
      if ( !v7 )
      {
        g_pSimpleTableDispenser = 0;
        v6 = -2147024882;
        goto LABEL_10;
      }
      *v7 = &CSimpleTableDispenser::`vftable'{for `IAdvancedTableDispenser'};
      v7[1] = &CSimpleTableDispenser::`vftable'{for `IMetabaseSchemaCompiler'};
      v7[2] = &CSimpleTableDispenser::`vftable'{for `ICatalogErrorLogger'};
      v7[3] = 0;
      v7[4] = 0;
      TMBSchemaCompilation::TMBSchemaCompilation((TMBSchemaCompilation *)(v7 + 5));
      *((_QWORD *)v8 + 328) = 0;
      g_pSimpleTableDispenser = v8;
      (*(void (__fastcall **)(CSimpleTableDispenser *))(*(_QWORD *)v8 + 8LL))(v8);
      v9 = CSimpleTableDispenser::Init(g_pSimpleTableDispenser);
      if ( v9 )
      {
        v6 = v9;
LABEL_10:
        CSafeLock::~CSafeLock((CSafeLock *)&v11);
        return v6;
      }
    }
    CSafeLock::~CSafeLock((CSafeLock *)&v11);
    v4 = g_pSimpleTableDispenser;
  }
  return (**(__int64 (__fastcall ***)(CSimpleTableDispenser *, const struct _GUID *, void **))v4)(v4, a1, a2);
}

```

## disassembly

```asm
0x180002740  mov     r11, rsp
0x180002743  mov     [r11+8], rbx
0x180002747  mov     [r11+10h], rsi
0x18000274b  push    rdi
0x18000274c  sub     rsp, 30h
0x180002750  mov     rsi, rcx
0x180002753  mov     rdi, rdx
0x180002756  mov     rcx, cs:?g_pSimpleTableDispenser@@3V?$TSmartPointer@VCSimpleTableDispenser@@@@A; TSmartPointer<CSimpleTableDispenser> g_pSimpleTableDispenser
0x18000275d  test    rcx, rcx
0x180002760  jnz     loc_180002856
0x180002766  mov     [rsp+38h+var_18], ecx
0x18000276a  lea     rax, ?g_csSADispenser@@3VCSafeAutoCriticalSection@@A; CSafeAutoCriticalSection g_csSADispenser
0x180002771  lea     rcx, [r11-18h]; this
0x180002775  mov     [r11-10h], rax
0x180002779  call    ?Lock@CSafeLock@@QEAAKXZ; CSafeLock::Lock(void)
0x18000277e  mov     ebx, eax
0x180002780  test    eax, eax
0x180002782  jz      short loc_180002798
0x180002784  jle     loc_180002837
0x18000278a  movzx   ebx, ax
0x18000278d  or      ebx, 80070000h
0x180002793  jmp     loc_180002837
0x180002798  cmp     cs:?g_pSimpleTableDispenser@@3V?$TSmartPointer@VCSimpleTableDispenser@@@@A, 0; TSmartPointer<CSimpleTableDispenser> g_pSimpleTableDispenser
0x1800027a0  jnz     loc_180002845
0x1800027a6  mov     ecx, 0A48h; cb
0x1800027ab  call    cs:__imp_CoTaskMemAlloc
0x1800027b1  mov     rbx, rax
0x1800027b4  test    rax, rax
0x1800027b7  jz      short loc_180002827
0x1800027b9  lea     rax, ??_7CSimpleTableDispenser@@6BIAdvancedTableDispenser@@@; const CSimpleTableDispenser::`vftable'{for `IAdvancedTableDispenser'}
0x1800027c0  mov     [rbx], rax
0x1800027c3  lea     rcx, [rbx+28h]; this
0x1800027c7  lea     rax, ??_7CSimpleTableDispenser@@6BIMetabaseSchemaCompiler@@@; const CSimpleTableDispenser::`vftable'{for `IMetabaseSchemaCompiler'}
0x1800027ce  mov     [rbx+8], rax
0x1800027d2  lea     rax, ??_7CSimpleTableDispenser@@6BICatalogErrorLogger@@@; const CSimpleTableDispenser::`vftable'{for `ICatalogErrorLogger'}
0x1800027d9  mov     [rbx+10h], rax
0x1800027dd  mov     qword ptr [rbx+18h], 0
0x1800027e5  mov     qword ptr [rbx+20h], 0
0x1800027ed  call    ??0TMBSchemaCompilation@@QEAA@XZ; TMBSchemaCompilation::TMBSchemaCompilation(void)
0x1800027f2  mov     qword ptr [rbx+0A40h], 0
0x1800027fd  mov     rcx, rbx
0x180002800  mov     cs:?g_pSimpleTableDispenser@@3V?$TSmartPointer@VCSimpleTableDispenser@@@@A, rbx; TSmartPointer<CSimpleTableDispenser> g_pSimpleTableDispenser
0x180002807  mov     rax, [rbx]
0x18000280a  mov     rax, [rax+8]
0x18000280e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002813  mov     rcx, cs:?g_pSimpleTableDispenser@@3V?$TSmartPointer@VCSimpleTableDispenser@@@@A; this
0x18000281a  call    ?Init@CSimpleTableDispenser@@QEAAJXZ; CSimpleTableDispenser::Init(void)
0x18000281f  test    eax, eax
0x180002821  jz      short loc_180002845
0x180002823  mov     ebx, eax
0x180002825  jmp     short loc_180002837
0x180002827  mov     cs:?g_pSimpleTableDispenser@@3V?$TSmartPointer@VCSimpleTableDispenser@@@@A, 0; TSmartPointer<CSimpleTableDispenser> g_pSimpleTableDispenser
0x180002832  mov     ebx, 8007000Eh
0x180002837  lea     rcx, [rsp+38h+var_18]; this
0x18000283c  call    ??1CSafeLock@@QEAA@XZ; CSafeLock::~CSafeLock(void)
0x180002841  mov     eax, ebx
0x180002843  jmp     short loc_180002867
0x180002845  lea     rcx, [rsp+38h+var_18]; this
0x18000284a  call    ??1CSafeLock@@QEAA@XZ; CSafeLock::~CSafeLock(void)
0x18000284f  mov     rcx, cs:?g_pSimpleTableDispenser@@3V?$TSmartPointer@VCSimpleTableDispenser@@@@A; TSmartPointer<CSimpleTableDispenser> g_pSimpleTableDispenser
0x180002856  mov     rax, [rcx]
0x180002859  mov     r8, rdi
0x18000285c  mov     rdx, rsi
0x18000285f  mov     rax, [rax]
0x180002862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002867  mov     rbx, [rsp+38h+arg_0]
0x18000286c  mov     rsi, [rsp+38h+arg_8]
0x180002871  add     rsp, 30h
0x180002875  pop     rdi
0x180002876  retn
```
