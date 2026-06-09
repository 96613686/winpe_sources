# TSmartPointerArray<TSmartPointerArray<ushort>>::~TSmartPointerArray<TSmartPointerArray<ushort>>(void)

- ea: `0x180010ec4`
- end: `0x180010f0c`
- name: `??1?$TSmartPointerArray@V?$TSmartPointerArray@G@@@@QEAA@XZ`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180010fc0`

## callees

- `0x180001f2c`
- `0x180010ec4`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180010ef4`
- `ole32!CoTaskMemFree` at `0x180010ef4`

## pseudocode

```c
void __fastcall TSmartPointerArray<TSmartPointerArray<unsigned short>>::~TSmartPointerArray<TSmartPointerArray<unsigned short>>(
        void **a1)
{
  char *v2; // rcx
  char *v3; // rbx

  v2 = (char *)*a1;
  if ( v2 )
  {
    v3 = v2 - 8;
    `vector destructor iterator'(
      v2,
      8u,
      *((_QWORD *)v2 - 1),
      (void (*)(void *))TSmartPointerArray<bool>::~TSmartPointerArray<bool>);
    CoTaskMemFree(v3);
  }
  *a1 = 0;
}

```

## disassembly

```asm
0x180010ec4  mov     [rsp+arg_0], rbx
0x180010ec9  push    rdi
0x180010eca  sub     rsp, 20h
0x180010ece  mov     rdi, rcx
0x180010ed1  mov     rcx, [rcx]; void *
0x180010ed4  test    rcx, rcx
0x180010ed7  jz      short loc_180010EFA
0x180010ed9  lea     rbx, [rcx-8]
0x180010edd  mov     edx, 8; unsigned __int64
0x180010ee2  mov     r8, [rbx]; unsigned __int64
0x180010ee5  lea     r9, ??1?$TSmartPointerArray@_N@@QEAA@XZ; void (*)(void *)
0x180010eec  call    ??_I@YAXPEAX_K1P6AX0@Z@Z; `vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180010ef1  mov     rcx, rbx; pv
0x180010ef4  call    cs:__imp_CoTaskMemFree
0x180010efa  mov     rbx, [rsp+28h+arg_0]
0x180010eff  mov     qword ptr [rdi], 0
0x180010f06  add     rsp, 20h
0x180010f0a  pop     rdi
0x180010f0b  retn
```
