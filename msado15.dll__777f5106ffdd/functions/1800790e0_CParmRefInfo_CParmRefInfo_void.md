# CParmRefInfo::~CParmRefInfo(void)

- ea: `0x1800790e0`
- end: `0x18007916b`
- name: `??1CParmRefInfo@@QEAA@XZ`
- size: `139`
- prototype: `void __fastcall(CParmRefInfo *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800792d8`

## callees

- `0x1800790e0`
- `0x1800d0010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180079111`
- `ole32!CoTaskMemFree` at `0x180079152`
- `ole32!CoTaskMemFree` at `0x180079111`
- `ole32!CoTaskMemFree` at `0x180079152`

## pseudocode

```c
void __fastcall CParmRefInfo::~CParmRefInfo(CParmRefInfo *this)
{
  __int64 v2; // rcx
  void *v3; // rcx
  __int64 i; // rdi
  __int64 v5; // rcx

  v2 = *((_QWORD *)this + 4);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  if ( *(_QWORD *)this )
  {
    v3 = (void *)*((_QWORD *)this + 2);
    if ( v3 )
      CoTaskMemFree(v3);
    for ( i = 0; (unsigned __int64)(unsigned int)i < *((_QWORD *)this + 1); i = (unsigned int)(i + 1) )
    {
      v5 = *(_QWORD *)(*(_QWORD *)this + 48 * i + 24);
      if ( v5 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    CoTaskMemFree(*(LPVOID *)this);
  }
}

```

## disassembly

```asm
0x1800790e0  mov     [rsp+arg_0], rbx
0x1800790e5  push    rdi
0x1800790e6  sub     rsp, 20h
0x1800790ea  mov     rbx, rcx
0x1800790ed  mov     rcx, [rcx+20h]
0x1800790f1  test    rcx, rcx
0x1800790f4  jz      short loc_180079102
0x1800790f6  mov     rax, [rcx]
0x1800790f9  mov     rax, [rax+10h]
0x1800790fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079102  cmp     qword ptr [rbx], 0
0x180079106  jz      short loc_18007915F
0x180079108  mov     rcx, [rbx+10h]; pv
0x18007910c  test    rcx, rcx
0x18007910f  jz      short loc_18007911D
0x180079111  call    cs:__imp_CoTaskMemFree
0x180079118  nop     dword ptr [rax+rax+00h]
0x18007911d  xor     edi, edi
0x18007911f  cmp     [rbx+8], rdi
0x180079123  jbe     short loc_18007914F
0x180079125  lea     rcx, [rdi+rdi*2]
0x180079129  add     rcx, rcx
0x18007912c  mov     rax, [rbx]
0x18007912f  mov     rcx, [rax+rcx*8+18h]
0x180079134  test    rcx, rcx
0x180079137  jz      short loc_180079145
0x180079139  mov     rax, [rcx]
0x18007913c  mov     rax, [rax+10h]
0x180079140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180079145  inc     edi
0x180079147  mov     eax, edi
0x180079149  cmp     rax, [rbx+8]
0x18007914d  jb      short loc_180079125
0x18007914f  mov     rcx, [rbx]; pv
0x180079152  call    cs:__imp_CoTaskMemFree
0x180079159  nop     dword ptr [rax+rax+00h]
0x18007915e  nop
0x18007915f  mov     rbx, [rsp+28h+arg_0]
0x180079164  add     rsp, 20h
0x180079168  pop     rdi
0x180079169  retn
```
