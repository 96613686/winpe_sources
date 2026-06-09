# NfsXmlIsNameSpaceValid(IXMLDOMDocument * *)

- ea: `0x180027adc`
- end: `0x180027b76`
- name: `?NfsXmlIsNameSpaceValid@@YA_NPEAPEAUIXMLDOMDocument@@@Z`
- size: `154`
- prototype: `bool __fastcall(struct IXMLDOMDocument **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180028ac4`

## callees

- `0x180027adc`
- `0x180037010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180027b3a`
- `msvcrt!_wcsicmp` at `0x180027b3a`
- `OLEAUT32!__imp_SysFreeString` at `0x180027b52`
- `OLEAUT32!__imp_SysFreeString` at `0x180027b52`

## string_xrefs

- `0x180027b33`: `http://schemas.microsoft.com/nfs/2011/03/share`

## pseudocode

```c
bool __fastcall NfsXmlIsNameSpaceValid(struct IXMLDOMDocument **a1)
{
  __int64 v1; // rcx
  bool v2; // bl
  wchar_t *String1; // [rsp+30h] [rbp+8h] BYREF
  __int64 v5; // [rsp+38h] [rbp+10h] BYREF

  v1 = (__int64)*a1;
  v5 = 0;
  v2 = 0;
  String1 = 0;
  if ( (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v1 + 360LL))(v1, &v5) >= 0
    && (*(int (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v5 + 312LL))(v5, &String1) >= 0 )
  {
    v2 = _wcsicmp(String1, L"http://schemas.microsoft.com/nfs/2011/03/share") == 0;
  }
  SysFreeString(String1);
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  return v2;
}

```

## disassembly

```asm
0x180027adc  push    rbx
0x180027ade  sub     rsp, 20h
0x180027ae2  mov     rcx, [rcx]
0x180027ae5  lea     rdx, [rsp+28h+arg_8]
0x180027aea  mov     [rsp+28h+arg_8], 0
0x180027af3  xor     bl, bl
0x180027af5  mov     [rsp+28h+String1], 0
0x180027afe  mov     rax, [rcx]
0x180027b01  mov     rax, [rax+168h]
0x180027b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b0d  test    eax, eax
0x180027b0f  js      short loc_180027B4D
0x180027b11  mov     rcx, [rsp+28h+arg_8]
0x180027b16  lea     rdx, [rsp+28h+String1]
0x180027b1b  mov     rax, [rcx]
0x180027b1e  mov     rax, [rax+138h]
0x180027b25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b2a  test    eax, eax
0x180027b2c  js      short loc_180027B4D
0x180027b2e  mov     rcx, [rsp+28h+String1]; String1
0x180027b33  lea     rdx, aHttpSchemasMic; "http://schemas.microsoft.com/nfs/2011/0"...
0x180027b3a  call    cs:__imp__wcsicmp
0x180027b40  movzx   ebx, bl
0x180027b43  mov     ecx, 1
0x180027b48  test    eax, eax
0x180027b4a  cmovz   ebx, ecx
0x180027b4d  mov     rcx, [rsp+28h+String1]; bstrString
0x180027b52  call    cs:__imp_SysFreeString
0x180027b58  mov     rcx, [rsp+28h+arg_8]
0x180027b5d  test    rcx, rcx
0x180027b60  jz      short loc_180027B6E
0x180027b62  mov     rdx, [rcx]
0x180027b65  mov     rax, [rdx+10h]
0x180027b69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027b6e  mov     al, bl
0x180027b70  add     rsp, 20h
0x180027b74  pop     rbx
0x180027b75  retn
```
