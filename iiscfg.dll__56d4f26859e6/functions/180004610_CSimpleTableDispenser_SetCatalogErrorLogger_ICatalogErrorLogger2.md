# CSimpleTableDispenser::SetCatalogErrorLogger(ICatalogErrorLogger2 *)

- ea: `0x180004610`
- end: `0x180004652`
- name: `?SetCatalogErrorLogger@CSimpleTableDispenser@@UEAAJPEAUICatalogErrorLogger2@@@Z`
- size: `66`
- prototype: `__int64 __fastcall(CSimpleTableDispenser *__hidden this, struct ICatalogErrorLogger2 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180004610`
- `0x1800117b4`

## import_xrefs

- `ATL!__imp_AtlComPtrAssign` at `0x18000463b`
- `ATL!__imp_AtlComPtrAssign` at `0x18000463b`

## pseudocode

```c
__int64 __fastcall CSimpleTableDispenser::SetCatalogErrorLogger(
        CSimpleTableDispenser *this,
        struct ICatalogErrorLogger2 *a2)
{
  int v3; // [rsp+20h] [rbp-18h] BYREF
  _RTL_CRITICAL_SECTION *v4; // [rsp+28h] [rbp-10h]

  if ( !a2 )
    return 2147942487LL;
  v3 = 0;
  v4 = &g_csSADispenser;
  AtlComPtrAssign((char *)this + 2624, a2);
  CSafeLock::~CSafeLock((CSafeLock *)&v3);
  return 0;
}

```

## disassembly

```asm
0x180004610  sub     rsp, 38h
0x180004614  test    rdx, rdx
0x180004617  jnz     short loc_180004620
0x180004619  mov     eax, 80070057h
0x18000461e  jmp     short loc_18000464D
0x180004620  lea     rax, ?g_csSADispenser@@3VCSafeAutoCriticalSection@@A; CSafeAutoCriticalSection g_csSADispenser
0x180004627  mov     [rsp+38h+var_18], 0
0x18000462f  add     rcx, 0A40h
0x180004636  mov     [rsp+38h+var_10], rax
0x18000463b  call    cs:__imp_AtlComPtrAssign
0x180004641  lea     rcx, [rsp+38h+var_18]; this
0x180004646  call    ??1CSafeLock@@QEAA@XZ; CSafeLock::~CSafeLock(void)
0x18000464b  xor     eax, eax
0x18000464d  add     rsp, 38h
0x180004651  retn
```
