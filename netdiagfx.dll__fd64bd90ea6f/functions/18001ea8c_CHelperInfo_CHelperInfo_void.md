# CHelperInfo::~CHelperInfo(void)

- ea: `0x18001ea8c`
- end: `0x18001eaee`
- name: `??1CHelperInfo@@QEAA@XZ`
- size: `98`
- prototype: `void __fastcall(CHelperInfo *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001ed70`

## callees

- `0x180006d58`
- `0x18001ea8c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eab4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eac5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eab4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eac5`

## pseudocode

```c
void __fastcall CHelperInfo::~CHelperInfo(CHelperInfo *this)
{
  unsigned int i; // edi

  if ( *((_QWORD *)this + 9) )
  {
    for ( i = 0; i < *((_DWORD *)this + 20); ++i )
      CoTaskMemFree(*(LPVOID *)(*((_QWORD *)this + 9) + 16LL * i));
    CoTaskMemFree(*((LPVOID *)this + 9));
  }
  ATL::CStringData::Release((ATL::CStringData *)(*((_QWORD *)this + 5) - 24LL));
  ATL::CStringData::Release((ATL::CStringData *)(*(_QWORD *)this - 24LL));
}

```

## disassembly

```asm
0x18001ea8c  mov     [rsp+arg_0], rbx
0x18001ea91  push    rdi
0x18001ea92  sub     rsp, 20h
0x18001ea96  cmp     qword ptr [rcx+48h], 0
0x18001ea9b  mov     rbx, rcx
0x18001ea9e  jz      short loc_18001EACB
0x18001eaa0  xor     edi, edi
0x18001eaa2  cmp     [rcx+50h], edi
0x18001eaa5  jbe     short loc_18001EAC1
0x18001eaa7  mov     rcx, [rbx+48h]
0x18001eaab  mov     eax, edi
0x18001eaad  add     rax, rax
0x18001eab0  mov     rcx, [rcx+rax*8]; pv
0x18001eab4  call    cs:__imp_CoTaskMemFree
0x18001eaba  inc     edi
0x18001eabc  cmp     edi, [rbx+50h]
0x18001eabf  jb      short loc_18001EAA7
0x18001eac1  mov     rcx, [rbx+48h]; pv
0x18001eac5  call    cs:__imp_CoTaskMemFree
0x18001eacb  mov     rcx, [rbx+28h]
0x18001eacf  sub     rcx, 18h; this
0x18001ead3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001ead8  mov     rcx, [rbx]
0x18001eadb  sub     rcx, 18h; this
0x18001eadf  mov     rbx, [rsp+28h+arg_0]
0x18001eae4  add     rsp, 20h
0x18001eae8  pop     rdi
0x18001eae9  jmp     ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
```
