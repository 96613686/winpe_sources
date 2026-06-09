# CCabFolder::QueryInterface(_GUID const &,void * *)

- ea: `0x18000f0d0`
- end: `0x18000f11e`
- name: `?QueryInterface@CCabFolder@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `78`
- prototype: `__int64 __fastcall(CCabFolder *__hidden this, const struct _GUID *, void **)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f130`
- `0x18000f140`
- `0x18000f150`
- `0x18000f160`

## callees

- `0x18000f0d0`
- `0x180013010`

## import_xrefs

- `SHLWAPI!__imp_QISearch` at `0x18000f117`

## pseudocode

```c
HRESULT __fastcall CCabFolder::QueryInterface(CCabFolder *this, const struct _GUID *a2, void **a3)
{
  __int64 v3; // rax

  v3 = *(_QWORD *)&CLSID_CabFolder.Data1 - *(_QWORD *)&a2->Data1;
  if ( *(_QWORD *)&CLSID_CabFolder.Data1 == *(_QWORD *)&a2->Data1 )
    v3 = *(_QWORD *)CLSID_CabFolder.Data4 - *(_QWORD *)a2->Data4;
  if ( v3 )
    return QISearch(this, (LPCQITAB)&off_180014600, a2, a3);
  *a3 = this;
  (*(void (__fastcall **)(CCabFolder *))(*(_QWORD *)this + 8LL))(this);
  return 0;
}

```

## disassembly

```asm
0x18000f0d0  sub     rsp, 28h
0x18000f0d4  mov     rax, qword ptr cs:CLSID_CabFolder.Data1
0x18000f0db  sub     rax, [rdx]
0x18000f0de  jnz     short loc_18000F0EB
0x18000f0e0  mov     rax, qword ptr cs:CLSID_CabFolder.Data4
0x18000f0e7  sub     rax, [rdx+8]
0x18000f0eb  test    rax, rax
0x18000f0ee  jnz     short loc_18000F106
0x18000f0f0  mov     [r8], rcx
0x18000f0f3  mov     rax, [rcx]
0x18000f0f6  mov     rax, [rax+8]
0x18000f0fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0ff  xor     eax, eax
0x18000f101  add     rsp, 28h
0x18000f105  retn
0x18000f106  mov     r9, r8
0x18000f109  mov     r8, rdx
0x18000f10c  lea     rdx, off_180014600
0x18000f113  add     rsp, 28h
0x18000f117  jmp     cs:__imp_QISearch
```
