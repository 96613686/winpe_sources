# NdrTypeInfo::~NdrTypeInfo(void)

- ea: `0x180037c5c`
- end: `0x180037d20`
- name: `??1NdrTypeInfo@@EEAA@XZ`
- size: `196`
- prototype: `void __fastcall(NdrTypeInfo *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180037c20`

## callees

- `0x180037c5c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037c9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037cb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037cd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037ce1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037c9a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037cb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037cd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180037ce1`
- `RPCRT4!NdrpReleaseTypeFormatString` at `0x180037cf4`
- `RPCRT4!NdrpReleaseTypeFormatString` at `0x180037cf4`

## pseudocode

```c
void __fastcall NdrTypeInfo::~NdrTypeInfo(NdrTypeInfo *this)
{
  bool v1; // zf
  __int64 i; // rsi
  METHOD_DESCRIPTOR *m_rgMethodDescs; // rbx

  v1 = this->m_rgMethodDescs == 0;
  this->__vftable = (NdrTypeInfo_vtbl *)NdrTypeInfo::`vftable';
  if ( !v1 )
  {
    for ( i = 0; (unsigned int)i < this->m_stubHeader.DispatchTableCount; i = (unsigned int)(i + 1) )
    {
      m_rgMethodDescs = this->m_rgMethodDescs;
      CoTaskMemFree(m_rgMethodDescs[i].m_szMethodName);
      if ( m_rgMethodDescs[i].m_paramVTs )
        CoTaskMemFree(this->m_rgMethodDescs[i].m_paramVTs);
    }
    CoTaskMemFree(this->m_rgMethodDescs);
  }
  CoTaskMemFree(this->m_szInterfaceName);
  NdrpReleaseTypeFormatString(this->m_stubDesc.pFormatTypes);
  this->__vftable = (NdrTypeInfo_vtbl *)CALLFRAME_CACHE_ENTRY<INTERFACE_HELPER_CLSID>::`vftable';
}

```

## disassembly

```asm
0x180037c5c  mov     [rsp+arg_0], rbx
0x180037c61  mov     [rsp+arg_8], rbp
0x180037c66  mov     [rsp+arg_10], rsi
0x180037c6b  push    rdi
0x180037c6c  sub     rsp, 20h
0x180037c70  cmp     qword ptr [this+38h], 0
0x180037c75  lea     rax, ??_7NdrTypeInfo@@6B@; const NdrTypeInfo::`vftable'
0x180037c7c  mov     [this], rax
0x180037c7f  mov     rdi, this
0x180037c82  jz      short loc_180037CDD
0x180037c84  xor     esi, esi
0x180037c86  cmp     [this+138h], esi
0x180037c8c  jbe     short loc_180037CCD
0x180037c8e  mov     rbx, [rdi+38h]
0x180037c92  lea     rbp, [rsi+rsi*2]
0x180037c96  mov     this, [rbx+rbp*8]; pv
0x180037c9a  call    cs:__imp_CoTaskMemFree
0x180037ca1  nop     dword ptr [rax+rax+00h]
0x180037ca6  cmp     qword ptr [rbx+rbp*8+10h], 0
0x180037cac  jz      short loc_180037CC3
0x180037cae  mov     this, [rdi+38h]
0x180037cb2  mov     this, [this+rbp*8+10h]; pv
0x180037cb7  call    cs:__imp_CoTaskMemFree
0x180037cbe  nop     dword ptr [rax+rax+00h]
0x180037cc3  inc     esi
0x180037cc5  cmp     esi, [rdi+138h]
0x180037ccb  jb      short loc_180037C8E
0x180037ccd  mov     this, [rdi+38h]; pv
0x180037cd1  call    cs:__imp_CoTaskMemFree
0x180037cd8  nop     dword ptr [rax+rax+00h]
0x180037cdd  mov     this, [rdi+30h]; pv
0x180037ce1  call    cs:__imp_CoTaskMemFree
0x180037ce8  nop     dword ptr [rax+rax+00h]
0x180037ced  mov     this, [rdi+90h]
0x180037cf4  call    cs:__imp_NdrpReleaseTypeFormatString
0x180037cfb  nop     dword ptr [rax+rax+00h]
0x180037d00  mov     rbx, [rsp+28h+arg_0]
0x180037d05  lea     rax, ??_7?$CALLFRAME_CACHE_ENTRY@UINTERFACE_HELPER_CLSID@@@@6B@; const CALLFRAME_CACHE_ENTRY<INTERFACE_HELPER_CLSID>::`vftable'
0x180037d0c  mov     rbp, [rsp+28h+arg_8]
0x180037d11  mov     rsi, [rsp+28h+arg_10]
0x180037d16  mov     [rdi], rax
0x180037d19  add     rsp, 20h
0x180037d1d  pop     rdi
0x180037d1e  retn
```
