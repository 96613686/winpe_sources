# CWinRtUrlAccessor::~CWinRtUrlAccessor(void)

- ea: `0x18000b54c`
- end: `0x18000b5af`
- name: `??1CWinRtUrlAccessor@@UEAA@XZ`
- size: `99`
- prototype: `void __fastcall(CWinRtUrlAccessor *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000b510`

## callees

- `0x18000b54c`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b566`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b57d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b566`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b57d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CWinRtUrlAccessor::~CWinRtUrlAccessor(CWinRtUrlAccessor *this)
{
  void *v2; // rcx
  void *v3; // rcx
  __int64 v4; // rcx

  v2 = (void *)*((_QWORD *)this + 7);
  *((_QWORD *)this + 7) = 0;
  if ( v2 )
    CoTaskMemFree(v2);
  v3 = (void *)*((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v3 )
    CoTaskMemFree(v3);
  v4 = *((_QWORD *)this + 5);
  if ( v4 )
  {
    *((_QWORD *)this + 5) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
  *((_DWORD *)this + 9) = -1073741823;
}

```

## disassembly

```asm
0x18000b54c  push    rbx
0x18000b54e  sub     rsp, 20h
0x18000b552  mov     rbx, rcx
0x18000b555  mov     rcx, [rcx+38h]; pv
0x18000b559  mov     qword ptr [rbx+38h], 0
0x18000b561  test    rcx, rcx
0x18000b564  jz      short loc_18000B56C
0x18000b566  call    cs:__imp_CoTaskMemFree
0x18000b56c  mov     rcx, [rbx+30h]; pv
0x18000b570  mov     qword ptr [rbx+30h], 0
0x18000b578  test    rcx, rcx
0x18000b57b  jz      short loc_18000B584
0x18000b57d  call    cs:__imp_CoTaskMemFree
0x18000b583  nop
0x18000b584  mov     rcx, [rbx+28h]
0x18000b588  test    rcx, rcx
0x18000b58b  jz      short loc_18000B5A2
0x18000b58d  mov     qword ptr [rbx+28h], 0
0x18000b595  mov     rax, [rcx]
0x18000b598  mov     rax, [rax+10h]
0x18000b59c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5a1  nop
0x18000b5a2  mov     dword ptr [rbx+24h], 0C0000001h
0x18000b5a9  add     rsp, 20h
0x18000b5ad  pop     rbx
0x18000b5ae  retn
```
