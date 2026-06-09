# CPidlMgr::SetProperty(_tagpropertykey const &,tagPROPVARIANT &)

- ea: `0x180004120`
- end: `0x180004193`
- name: `?SetProperty@CPidlMgr@@QEAAJAEBU_tagpropertykey@@AEAUtagPROPVARIANT@@@Z`
- size: `115`
- prototype: `HRESULT __fastcall(LPVOID *this, const struct _tagpropertykey *, struct tagPROPVARIANT *)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002030`
- `0x180020b00`
- `0x180020f80`

## callees

- `0x180004120`
- `0x18003d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000415f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000415f`

## pseudocode

```c
HRESULT __fastcall CPidlMgr::SetProperty(LPVOID *this, const struct _tagpropertykey *a2, struct tagPROPVARIANT *a3)
{
  _QWORD *v3; // rbx
  HRESULT result; // eax

  v3 = this + 1;
  if ( this[1] )
  {
    result = 0;
  }
  else
  {
    result = CoCreateInstance(&CLSID_InMemoryPropertyStore, 0, 1u, &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, this + 1);
    if ( result < 0 )
      return result;
  }
  if ( *v3 )
    return (*(__int64 (__fastcall **)(_QWORD, const struct _tagpropertykey *, struct tagPROPVARIANT *))(*(_QWORD *)*v3 + 48LL))(
             *v3,
             a2,
             a3);
  return result;
}

```

## disassembly

```asm
0x180004120  mov     [rsp+arg_0], rbx
0x180004125  mov     [rsp+arg_8], rsi
0x18000412a  push    rdi
0x18000412b  sub     rsp, 30h
0x18000412f  cmp     qword ptr [rcx+8], 0
0x180004134  lea     rbx, [rcx+8]
0x180004138  mov     rdi, r8
0x18000413b  mov     rsi, rdx
0x18000413e  jz      short loc_180004144
0x180004140  xor     eax, eax
0x180004142  jmp     short loc_180004169
0x180004144  lea     r9, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x18000414b  mov     [rsp+38h+ppv], rbx; ppv
0x180004150  xor     edx, edx; pUnkOuter
0x180004152  lea     rcx, CLSID_InMemoryPropertyStore; rclsid
0x180004159  mov     r8d, 1; dwClsContext
0x18000415f  call    cs:__imp_CoCreateInstance
0x180004165  test    eax, eax
0x180004167  js      short loc_180004183
0x180004169  mov     rcx, [rbx]
0x18000416c  test    rcx, rcx
0x18000416f  jz      short loc_180004183
0x180004171  mov     rax, [rcx]
0x180004174  mov     r8, rdi
0x180004177  mov     rdx, rsi
0x18000417a  mov     rax, [rax+30h]
0x18000417e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004183  mov     rbx, [rsp+38h+arg_0]
0x180004188  mov     rsi, [rsp+38h+arg_8]
0x18000418d  add     rsp, 30h
0x180004191  pop     rdi
0x180004192  retn
```
