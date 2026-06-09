# TSmartPointerArray<TXmlParsedFile>::~TSmartPointerArray<TXmlParsedFile>(void)

- ea: `0x18002a0ec`
- end: `0x18002a12e`
- name: `??1?$TSmartPointerArray@VTXmlParsedFile@@@@QEAA@XZ`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18002f090`

## callees

- `0x18002a0ec`
- `0x180030010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18002a11b`
- `ole32!CoTaskMemFree` at `0x18002a11b`

## pseudocode

```c
void __fastcall TSmartPointerArray<TXmlParsedFile>::~TSmartPointerArray<TXmlParsedFile>(__int64 *a1)
{
  __int64 v2; // rcx

  v2 = *a1;
  if ( v2 )
  {
    if ( *(_QWORD *)(v2 - 8) )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v2 + 64LL))(v2, 3);
    else
      CoTaskMemFree((LPVOID)(v2 - 8));
  }
  *a1 = 0;
}

```

## disassembly

```asm
0x18002a0ec  push    rbx
0x18002a0ee  sub     rsp, 20h
0x18002a0f2  mov     rbx, rcx
0x18002a0f5  mov     rcx, [rcx]
0x18002a0f8  test    rcx, rcx
0x18002a0fb  jz      short loc_18002A121
0x18002a0fd  cmp     qword ptr [rcx-8], 0
0x18002a102  jz      short loc_18002A117
0x18002a104  mov     rax, [rcx]
0x18002a107  mov     edx, 3
0x18002a10c  mov     rax, [rax+40h]
0x18002a110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a115  jmp     short loc_18002A121
0x18002a117  add     rcx, 0FFFFFFFFFFFFFFF8h; pv
0x18002a11b  call    cs:__imp_CoTaskMemFree
0x18002a121  mov     qword ptr [rbx], 0
0x18002a128  add     rsp, 20h
0x18002a12c  pop     rbx
0x18002a12d  retn
```
