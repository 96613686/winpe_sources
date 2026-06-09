# MvGetContextSubKeyPath(IMVHandler *,ulong const *,ushort const *,ushort const *,ushort *,ulong,_MVProvisionData *)

- ea: `0x1800376bc`
- end: `0x180037743`
- name: `?MvGetContextSubKeyPath@@YAJPEAUIMVHandler@@PEBKPEBG2PEAGKPEAU_MVProvisionData@@@Z`
- size: `135`
- prototype: `__int64 __fastcall(struct IMVHandler *, const unsigned int *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180031100`
- `0x18003774c`

## callees

- `0x180007f48`
- `0x1800376bc`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003772b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003772b`

## pseudocode

```c
__int64 __fastcall MvGetContextSubKeyPath(
        struct IMVHandler *a1,
        const unsigned int *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5)
{
  LPCWSTR v5; // rsi
  unsigned __int16 *v6; // rdi
  int v7; // ebx
  LPVOID pv; // [rsp+58h] [rbp+20h] BYREF

  v5 = gc_wszRegMultivariant;
  v6 = a5;
  *a5 = 0;
  pv = 0;
  v7 = (*(__int64 (__fastcall **)(struct IMVHandler *, LPVOID *, _QWORD))(*(_QWORD *)a1 + 88LL))(a1, &pv, 0);
  if ( v7 >= 0 )
    v7 = StringCchPrintfW(v6, 0x104u, L"%s\\%s", v5, pv);
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800376bc  mov     r11, rsp
0x1800376bf  mov     [r11+8], rbx
0x1800376c3  mov     [r11+10h], rsi
0x1800376c7  mov     [r11+20h], r9
0x1800376cb  push    rdi
0x1800376cc  sub     rsp, 30h
0x1800376d0  mov     rsi, cs:?gc_wszRegMultivariant@@3PEBGEB; ushort const * const gc_wszRegMultivariant
0x1800376d7  xor     eax, eax
0x1800376d9  mov     rdi, [rsp+38h+arg_20]
0x1800376de  mov     [rdi], ax
0x1800376e1  mov     [r11+20h], rax
0x1800376e5  mov     rax, [rcx]
0x1800376e8  xor     r8d, r8d
0x1800376eb  lea     rdx, [r11+20h]
0x1800376ef  mov     rax, [rax+58h]
0x1800376f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800376f8  mov     ebx, eax
0x1800376fa  test    eax, eax
0x1800376fc  js      short loc_180037721
0x1800376fe  mov     rax, [rsp+38h+pv]
0x180037703  mov     [rsp+38h+var_18], rax
0x180037708  mov     r9, rsi
0x18003770b  lea     r8, ?gc_szConcatTwoPathsFormat@@3QBGB; "%s\\%s"
0x180037712  mov     edx, 104h; unsigned __int64
0x180037717  mov     rcx, rdi; unsigned __int16 *
0x18003771a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003771f  mov     ebx, eax
0x180037721  mov     rcx, [rsp+38h+pv]; pv
0x180037726  test    rcx, rcx
0x180037729  jz      short loc_180037731
0x18003772b  call    cs:__imp_CoTaskMemFree
0x180037731  mov     eax, ebx
0x180037733  mov     rbx, [rsp+38h+arg_0]
0x180037738  mov     rsi, [rsp+38h+arg_8]
0x18003773d  add     rsp, 30h
0x180037741  pop     rdi
0x180037742  retn
```
