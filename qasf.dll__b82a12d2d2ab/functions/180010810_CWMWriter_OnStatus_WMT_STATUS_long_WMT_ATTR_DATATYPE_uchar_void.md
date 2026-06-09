# CWMWriter::OnStatus(WMT_STATUS,long,WMT_ATTR_DATATYPE,uchar *,void *)

- ea: `0x180010810`
- end: `0x180010880`
- name: `?OnStatus@CWMWriter@@UEAAJW4WMT_STATUS@@JW4WMT_ATTR_DATATYPE@@PEAEPEAX@Z`
- size: `112`
- prototype: `__int64 __fastcall(CWMWriter *__hidden this, enum WMT_STATUS, int, enum WMT_ATTR_DATATYPE, unsigned __int8 *, void *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x180010810`
- `0x18001f010`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x180010832`
- `ole32!CoTaskMemAlloc` at `0x180010832`

## pseudocode

```c
__int64 __fastcall CWMWriter::OnStatus(CWMWriter *this, enum WMT_STATUS a2, int a3, enum WMT_ATTR_DATATYPE a4)
{
  __int64 v4; // rsi
  _QWORD *v7; // rax
  __int64 v8; // rcx

  v4 = a2;
  if ( a3 < 0 )
  {
    v7 = CoTaskMemAlloc(0x10u);
    if ( v7 )
    {
      *(_DWORD *)v7 = a3;
      v7[1] = 0;
    }
    v8 = *((_QWORD *)this - 12);
    if ( v8 )
      (*(void (__fastcall **)(__int64, __int64, __int64, _QWORD *))(*(_QWORD *)v8 + 24LL))(v8, 594, v4, v7);
    *((_DWORD *)this + 25) = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180010810  mov     [rsp+arg_0], rbx
0x180010815  mov     [rsp+arg_8], rsi
0x18001081a  push    rdi
0x18001081b  sub     rsp, 30h
0x18001081f  movsxd  rsi, edx
0x180010822  mov     edi, r8d
0x180010825  mov     rbx, rcx
0x180010828  test    r8d, r8d
0x18001082b  jns     short loc_18001086E
0x18001082d  mov     ecx, 10h; cb
0x180010832  call    cs:__imp_CoTaskMemAlloc
0x180010838  mov     r9, rax
0x18001083b  test    rax, rax
0x18001083e  jz      short loc_18001084A
0x180010840  mov     [rax], edi
0x180010842  mov     qword ptr [rax+8], 0
0x18001084a  mov     rcx, [rbx-60h]
0x18001084e  test    rcx, rcx
0x180010851  jz      short loc_180010867
0x180010853  mov     rdx, [rcx]
0x180010856  mov     r8, rsi
0x180010859  mov     rax, [rdx+18h]
0x18001085d  mov     edx, 252h
0x180010862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010867  mov     dword ptr [rbx+64h], 1
0x18001086e  mov     rbx, [rsp+38h+arg_0]
0x180010873  xor     eax, eax
0x180010875  mov     rsi, [rsp+38h+arg_8]
0x18001087a  add     rsp, 30h
0x18001087e  pop     rdi
0x18001087f  retn
```
