# CAccServerDocMgr::OnDocumentFocus(IUnknown *)

- ea: `0x18000cff0`
- end: `0x18000d086`
- name: `?OnDocumentFocus@CAccServerDocMgr@@UEAAJPEAUIUnknown@@@Z`
- size: `150`
- prototype: `__int64 __fastcall(CAccServerDocMgr *__hidden this, struct IUnknown *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800026d0`
- `0x18000cff0`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d02a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000d02a`

## string_xrefs

- `0x18000d03a`: `CoCreate(AccStore)`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CAccServerDocMgr::OnDocumentFocus(CAccServerDocMgr *this, struct IUnknown *a2)
{
  LPVOID *v2; // rbx
  LPVOID v4; // rcx
  HRESULT Instance; // eax
  unsigned int v6; // edi
  int ppv; // [rsp+20h] [rbp-28h]

  v2 = (LPVOID *)((char *)this + 32);
  v4 = (LPVOID)*((_QWORD *)this + 4);
  if ( v4 )
    return (*(__int64 (__fastcall **)(LPVOID, struct IUnknown *))(*(_QWORD *)v4 + 64LL))(v4, a2);
  *v2 = 0;
  Instance = CoCreateInstance(&CLSID_AccStore, 0, 4u, &IID_IAccStore, v2);
  v4 = *v2;
  v6 = Instance;
  if ( *v2 )
    return (*(__int64 (__fastcall **)(LPVOID, struct IUnknown *))(*(_QWORD *)v4 + 64LL))(v4, a2);
  InternalTrace(L"windows\\oleacc\\msaatext\\msaaadapter.cpp", 0x106u, ppv, Instance, (__int64)L"CoCreate(AccStore)");
  return v6;
}

```

## disassembly

```asm
0x18000cff0  mov     [rsp+arg_0], rbx
0x18000cff5  mov     [rsp+arg_8], rsi
0x18000cffa  push    rdi
0x18000cffb  sub     rsp, 40h
0x18000cfff  lea     rbx, [rcx+20h]
0x18000d003  mov     rsi, rdx
0x18000d006  mov     rcx, [rbx]
0x18000d009  test    rcx, rcx
0x18000d00c  jnz     short loc_18000D067
0x18000d00e  mov     [rbx], rcx
0x18000d011  lea     r8d, [rcx+4]; dwClsContext
0x18000d015  lea     rcx, CLSID_AccStore; rclsid
0x18000d01c  mov     [rsp+48h+ppv], rbx; int
0x18000d021  lea     r9, IID_IAccStore; riid
0x18000d028  xor     edx, edx; pUnkOuter
0x18000d02a  call    cs:__imp_CoCreateInstance
0x18000d030  mov     rcx, [rbx]
0x18000d033  mov     edi, eax
0x18000d035  test    rcx, rcx
0x18000d038  jnz     short loc_18000D067
0x18000d03a  lea     rax, aCocreateAccsto; "CoCreate(AccStore)"
0x18000d041  mov     edx, 106h; Value
0x18000d046  lea     r9d, [rcx+1]
0x18000d04a  mov     [rsp+48h+var_18], rax; __int64
0x18000d04f  lea     r8d, [rcx+3]
0x18000d053  mov     [rsp+48h+var_20], edi; int
0x18000d057  lea     rcx, aWindowsOleaccM_2; "windows\\oleacc\\msaatext\\msaaadapter."...
0x18000d05e  call    InternalTrace
0x18000d063  mov     eax, edi
0x18000d065  jmp     short loc_18000D076
0x18000d067  mov     rax, [rcx]
0x18000d06a  mov     rdx, rsi
0x18000d06d  mov     rax, [rax+40h]
0x18000d071  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d076  mov     rbx, [rsp+48h+arg_0]
0x18000d07b  mov     rsi, [rsp+48h+arg_8]
0x18000d080  add     rsp, 40h
0x18000d084  pop     rdi
0x18000d085  retn
```
