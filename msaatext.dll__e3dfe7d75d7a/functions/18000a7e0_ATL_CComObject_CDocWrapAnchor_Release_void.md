# ATL::CComObject<CDocWrapAnchor>::Release(void)

- ea: `0x18000a7e0`
- end: `0x18000a835`
- name: `?Release@?$CComObject@VCDocWrapAnchor@@@ATL@@UEAAKXZ`
- size: `85`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000a840`
- `0x18000a850`
- `0x18000a860`
- `0x18000a870`
- `0x18000a880`
- `0x18000a890`

## callees

- `0x1800054d4`
- `0x18000a7e0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000a81b`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000a81b`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CDocWrapAnchor>::Release(_DWORD *a1)
{
  int v1; // edi
  unsigned int v3; // edi

  v1 = a1[20];
  if ( v1 == 0x7FFFFFFF )
  {
    return 2147483646;
  }
  else
  {
    v3 = v1 - 1;
    a1[20] = v3;
    if ( !v3 )
    {
      _InterlockedIncrement(&dword_180024B28);
      if ( a1 )
      {
        ATL::CComObject<CDocWrapAnchor>::~CComObject<CDocWrapAnchor>();
        operator delete(a1);
      }
      _InterlockedDecrement(&dword_180024B28);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000a7e0  mov     [rsp+arg_0], rbx
0x18000a7e5  push    rdi
0x18000a7e6  sub     rsp, 20h
0x18000a7ea  mov     edi, [rcx+50h]
0x18000a7ed  mov     rbx, rcx
0x18000a7f0  cmp     edi, 7FFFFFFFh
0x18000a7f6  jnz     short loc_18000A7FF
0x18000a7f8  mov     edi, 7FFFFFFEh
0x18000a7fd  jmp     short loc_18000A828
0x18000a7ff  sub     edi, 1
0x18000a802  mov     [rcx+50h], edi
0x18000a805  jnz     short loc_18000A828
0x18000a807  lock inc cs:dword_180024B28
0x18000a80e  test    rbx, rbx
0x18000a811  jz      short loc_18000A821
0x18000a813  call    ??1?$CComObject@VCDocWrapAnchor@@@ATL@@QEAA@XZ; ATL::CComObject<CDocWrapAnchor>::~CComObject<CDocWrapAnchor>(void)
0x18000a818  mov     rcx, rbx
0x18000a81b  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000a821  lock dec cs:dword_180024B28
0x18000a828  mov     rbx, [rsp+28h+arg_0]
0x18000a82d  mov     eax, edi
0x18000a82f  add     rsp, 20h
0x18000a833  pop     rdi
0x18000a834  retn
```
