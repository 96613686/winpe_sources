# CPPTPDiagHelper::~CPPTPDiagHelper(void)

- ea: `0x180009a6c`
- end: `0x180009ac8`
- name: `??1CPPTPDiagHelper@@QEAA@XZ`
- size: `92`
- prototype: `void __fastcall(CPPTPDiagHelper *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180009ad0`

## callees

- `0x180006030`
- `0x180009a6c`
- `0x18000f010`

## import_xrefs

- `WS2_32!__imp_WSACleanup` at `0x180009a98`
- `WS2_32!__imp_WSACleanup` at `0x180009a98`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009a81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009a81`

## pseudocode

```c
void __fastcall CPPTPDiagHelper::~CPPTPDiagHelper(CPPTPDiagHelper *this)
{
  void *v2; // rcx
  __int64 v3; // rcx

  v2 = (void *)*((_QWORD *)this + 178);
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *((_QWORD *)this + 178) = 0;
  }
  WSACleanup();
  v3 = *((_QWORD *)this + 14);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  CNetDiagHelper::~CNetDiagHelper(this);
}

```

## disassembly

```asm
0x180009a6c  push    rbx
0x180009a6e  sub     rsp, 20h
0x180009a72  mov     rbx, rcx
0x180009a75  mov     rcx, [rcx+590h]; pv
0x180009a7c  test    rcx, rcx
0x180009a7f  jz      short loc_180009A98
0x180009a81  call    cs:__imp_CoTaskMemFree
0x180009a88  nop     dword ptr [rax+rax+00h]
0x180009a8d  mov     qword ptr [rbx+590h], 0
0x180009a98  call    cs:__imp_WSACleanup
0x180009a9f  nop     dword ptr [rax+rax+00h]
0x180009aa4  nop
0x180009aa5  mov     rcx, [rbx+70h]
0x180009aa9  test    rcx, rcx
0x180009aac  jz      short loc_180009ABB
0x180009aae  mov     rax, [rcx]
0x180009ab1  mov     rax, [rax+10h]
0x180009ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009aba  nop
0x180009abb  mov     rcx, rbx; this
0x180009abe  add     rsp, 20h
0x180009ac2  pop     rbx
0x180009ac3  jmp     ??1CNetDiagHelper@@QEAA@XZ; CNetDiagHelper::~CNetDiagHelper(void)
```
