# CRenderGraphLogger::WriteGuidAttribute(ushort const *,_GUID const &)

- ea: `0x180206c04`
- end: `0x180206c84`
- name: `?WriteGuidAttribute@CRenderGraphLogger@@AEAAJPEBGAEBU_GUID@@@Z`
- size: `128`
- prototype: `int(CRenderGraphLogger *__hidden this, const unsigned __int16 *, const struct _GUID *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180206324`
- `0x180206890`

## callees

- `0x18001fd58`
- `0x180206c04`
- `0x180307010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180206c29`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180206c29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180206c68`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180206c68`

## pseudocode

```c
__int64 __fastcall CRenderGraphLogger::WriteGuidAttribute(
        CRenderGraphLogger *this,
        const unsigned __int16 *a2,
        const struct _GUID *a3)
{
  HRESULT v5; // ebx
  LPVOID pv; // [rsp+58h] [rbp+20h] BYREF

  pv = 0;
  v5 = StringFromCLSID(a3, (LPOLESTR *)&pv);
  if ( v5 >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const unsigned __int16 *, _QWORD, LPVOID))(**(_QWORD **)this + 56LL))(
           *(_QWORD *)this,
           0,
           a2,
           0,
           pv);
    CoTaskMemFree(pv);
    if ( v5 >= 0 )
      return 0;
  }
  DoStackCapture(v5);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180206c04  mov     rax, rsp
0x180206c07  mov     [rax+8], rbx
0x180206c0b  mov     [rax+10h], rsi
0x180206c0f  push    rdi
0x180206c10  sub     rsp, 30h
0x180206c14  mov     rdi, rdx
0x180206c17  mov     qword ptr [rax+20h], 0
0x180206c1f  mov     rsi, rcx
0x180206c22  lea     rdx, [rax+20h]; lplpsz
0x180206c26  mov     rcx, r8; rclsid
0x180206c29  call    cs:__imp_StringFromCLSID
0x180206c2f  mov     ebx, eax
0x180206c31  test    eax, eax
0x180206c33  jns     short loc_180206C40
0x180206c35  mov     ecx, ebx; int
0x180206c37  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180206c3c  mov     eax, ebx
0x180206c3e  jmp     short loc_180206C74
0x180206c40  mov     rdx, [rsp+38h+pv]
0x180206c45  xor     r9d, r9d
0x180206c48  mov     rcx, [rsi]
0x180206c4b  mov     r8, rdi
0x180206c4e  mov     [rsp+38h+var_18], rdx
0x180206c53  xor     edx, edx
0x180206c55  mov     rax, [rcx]
0x180206c58  mov     rax, [rax+38h]
0x180206c5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180206c61  mov     rcx, [rsp+38h+pv]; pv
0x180206c66  mov     ebx, eax
0x180206c68  call    cs:__imp_CoTaskMemFree
0x180206c6e  test    ebx, ebx
0x180206c70  js      short loc_180206C35
0x180206c72  xor     eax, eax
0x180206c74  mov     rbx, [rsp+38h+arg_0]
0x180206c79  mov     rsi, [rsp+38h+arg_8]
0x180206c7e  add     rsp, 30h
0x180206c82  pop     rdi
0x180206c83  retn
```
