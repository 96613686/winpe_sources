# CMachineSettings::OnAccessLoadBalancingCLSID(RSTableMetaEntry *,int,void *,void * *)

- ea: `0x1800359c0`
- end: `0x180035a29`
- name: `?OnAccessLoadBalancingCLSID@CMachineSettings@@QEAAJPEAURSTableMetaEntry@@HPEAXPEAPEAX@Z`
- size: `105`
- prototype: `int(CMachineSettings *__hidden this, struct RSTableMetaEntry *, int, void *, void **)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800359c0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800359fc`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180035a10`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800359fc`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180035a10`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800359d8`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800359d8`

## pseudocode

```c
__int64 __fastcall CMachineSettings::OnAccessLoadBalancingCLSID(
        LPOLESTR *this,
        struct RSTableMetaEntry *a2,
        int a3,
        const OLECHAR *a4,
        void **a5)
{
  LPOLESTR v5; // rbx
  LPOLESTR *v6; // rbx

  if ( a3 )
  {
    v5 = (LPOLESTR)this + 122;
    if ( CLSIDFromString(a4, (LPCLSID)((char *)this + 244)) < 0 )
      *(GUID *)v5 = GUID_NULL;
  }
  else
  {
    v6 = this + 33;
    if ( StringFromCLSID((const IID *const)a4, this + 33) < 0 )
      StringFromCLSID(&GUID_NULL, v6);
    v5 = *v6;
  }
  *a5 = v5;
  return 0;
}

```

## disassembly

```asm
0x1800359c0  push    rbx
0x1800359c2  sub     rsp, 20h
0x1800359c6  test    r8d, r8d
0x1800359c9  jz      short loc_1800359EF
0x1800359cb  lea     rbx, [rcx+0F4h]
0x1800359d2  mov     rcx, r9; lpsz
0x1800359d5  mov     rdx, rbx; pclsid
0x1800359d8  call    cs:__imp_CLSIDFromString
0x1800359de  test    eax, eax
0x1800359e0  jns     short loc_180035A19
0x1800359e2  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800359e9  movdqu  xmmword ptr [rbx], xmm0
0x1800359ed  jmp     short loc_180035A19
0x1800359ef  lea     rbx, [rcx+108h]
0x1800359f6  mov     rcx, r9; rclsid
0x1800359f9  mov     rdx, rbx; lplpsz
0x1800359fc  call    cs:__imp_StringFromCLSID
0x180035a02  test    eax, eax
0x180035a04  jns     short loc_180035A16
0x180035a06  mov     rdx, rbx; lplpsz
0x180035a09  lea     rcx, GUID_NULL; rclsid
0x180035a10  call    cs:__imp_StringFromCLSID
0x180035a16  mov     rbx, [rbx]
0x180035a19  mov     rax, [rsp+28h+arg_20]
0x180035a1e  mov     [rax], rbx
0x180035a21  xor     eax, eax
0x180035a23  add     rsp, 20h
0x180035a27  pop     rbx
0x180035a28  retn
```
