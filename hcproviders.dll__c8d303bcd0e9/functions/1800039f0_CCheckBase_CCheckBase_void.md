# CCheckBase::~CCheckBase(void)

- ea: `0x1800039f0`
- end: `0x180003aaa`
- name: `??1CCheckBase@@MEAA@XZ`
- size: `186`
- prototype: `void __fastcall(CCheckBase *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180003990`
- `0x1800065a8`
- `0x180008ff0`

## callees

- `0x1800039f0`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003a6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003a7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003a90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003a6a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003a7d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180003a90`

## pseudocode

```c
void __fastcall CCheckBase::~CCheckBase(CCheckBase *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx

  *(_QWORD *)this = &CCheckBase::`vftable';
  v2 = *((_QWORD *)this + 23);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  v3 = *((_QWORD *)this + 22);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = *((_QWORD *)this + 24);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = *((_QWORD *)this + 25);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  CoTaskMemFree(*((LPVOID *)this + 20));
  CoTaskMemFree(*((LPVOID *)this + 18));
  CoTaskMemFree(*((LPVOID *)this + 19));
  _InterlockedDecrement(&g_cLocks);
}

```

## disassembly

```asm
0x1800039f0  push    rbx
0x1800039f2  sub     rsp, 20h
0x1800039f6  lea     rax, ??_7CCheckBase@@6B@; const CCheckBase::`vftable'
0x1800039fd  mov     rbx, rcx
0x180003a00  mov     [rcx], rax
0x180003a03  mov     rcx, [rcx+0B8h]
0x180003a0a  test    rcx, rcx
0x180003a0d  jz      short loc_180003A1B
0x180003a0f  mov     rax, [rcx]
0x180003a12  mov     rax, [rax+10h]
0x180003a16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a1b  mov     rcx, [rbx+0B0h]
0x180003a22  test    rcx, rcx
0x180003a25  jz      short loc_180003A33
0x180003a27  mov     rax, [rcx]
0x180003a2a  mov     rax, [rax+10h]
0x180003a2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a33  mov     rcx, [rbx+0C0h]
0x180003a3a  test    rcx, rcx
0x180003a3d  jz      short loc_180003A4B
0x180003a3f  mov     rax, [rcx]
0x180003a42  mov     rax, [rax+10h]
0x180003a46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a4b  mov     rcx, [rbx+0C8h]
0x180003a52  test    rcx, rcx
0x180003a55  jz      short loc_180003A63
0x180003a57  mov     rax, [rcx]
0x180003a5a  mov     rax, [rax+10h]
0x180003a5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a63  mov     rcx, [rbx+0A0h]; pv
0x180003a6a  call    cs:__imp_CoTaskMemFree
0x180003a71  nop     dword ptr [rax+rax+00h]
0x180003a76  mov     rcx, [rbx+90h]; pv
0x180003a7d  call    cs:__imp_CoTaskMemFree
0x180003a84  nop     dword ptr [rax+rax+00h]
0x180003a89  mov     rcx, [rbx+98h]; pv
0x180003a90  call    cs:__imp_CoTaskMemFree
0x180003a97  nop     dword ptr [rax+rax+00h]
0x180003a9c  lock dec cs:?g_cLocks@@3JA; long g_cLocks
0x180003aa3  add     rsp, 20h
0x180003aa7  pop     rbx
0x180003aa8  retn
```
