# CDSLPageHolder::~CDSLPageHolder(void)

- ea: `0x180059b10`
- end: `0x180059bb0`
- name: `??1CDSLPageHolder@@UEAA@XZ`
- size: `160`
- prototype: `void __fastcall(CDSLPageHolder *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180055520`

## callees

- `0x180059b10`
- `0x180087010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180059b81`
- `ole32!CoTaskMemFree` at `0x180059b99`
- `ole32!CoTaskMemFree` at `0x180059b81`
- `ole32!CoTaskMemFree` at `0x180059b99`

## pseudocode

```c
void __fastcall CDSLPageHolder::~CDSLPageHolder(CDSLPageHolder *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  *(_QWORD *)this = &CDSLPageHolder::`vftable'{for `IPropertyPageSite'};
  *((_QWORD *)this + 1) = &CDSLPageHolder::`vftable'{for `IPropertyBag'};
  v2 = *((_QWORD *)this + 5);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *((_QWORD *)this + 5) = 0;
  }
  v3 = *((_QWORD *)this + 4);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 24LL))(v3, 0);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 4) + 16LL))(*((_QWORD *)this + 4));
    *((_QWORD *)this + 4) = 0;
  }
  CoTaskMemFree(*((LPVOID *)this + 19));
  *((_QWORD *)this + 19) = 0;
  CoTaskMemFree(*((LPVOID *)this + 29));
  *((_QWORD *)this + 29) = 0;
}

```

## disassembly

```asm
0x180059b10  push    rbx
0x180059b12  sub     rsp, 20h
0x180059b16  mov     rbx, rcx
0x180059b19  lea     rax, ??_7CDSLPageHolder@@6BIPropertyPageSite@@@; const CDSLPageHolder::`vftable'{for `IPropertyPageSite'}
0x180059b20  mov     [rcx], rax
0x180059b23  lea     rax, ??_7CDSLPageHolder@@6BIPropertyBag@@@; const CDSLPageHolder::`vftable'{for `IPropertyBag'}
0x180059b2a  mov     [rcx+8], rax
0x180059b2e  mov     rcx, [rcx+28h]
0x180059b32  test    rcx, rcx
0x180059b35  jz      short loc_180059B4B
0x180059b37  mov     rax, [rcx]
0x180059b3a  mov     rax, [rax+10h]
0x180059b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059b43  mov     qword ptr [rbx+28h], 0
0x180059b4b  mov     rcx, [rbx+20h]
0x180059b4f  test    rcx, rcx
0x180059b52  jz      short loc_180059B7A
0x180059b54  mov     rax, [rcx]
0x180059b57  xor     edx, edx
0x180059b59  mov     rax, [rax+18h]
0x180059b5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059b62  mov     rcx, [rbx+20h]
0x180059b66  mov     rax, [rcx]
0x180059b69  mov     rax, [rax+10h]
0x180059b6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059b72  mov     qword ptr [rbx+20h], 0
0x180059b7a  mov     rcx, [rbx+98h]; pv
0x180059b81  call    cs:__imp_CoTaskMemFree
0x180059b87  mov     qword ptr [rbx+98h], 0
0x180059b92  mov     rcx, [rbx+0E8h]; pv
0x180059b99  call    cs:__imp_CoTaskMemFree
0x180059b9f  mov     qword ptr [rbx+0E8h], 0
0x180059baa  add     rsp, 20h
0x180059bae  pop     rbx
0x180059baf  retn
```
