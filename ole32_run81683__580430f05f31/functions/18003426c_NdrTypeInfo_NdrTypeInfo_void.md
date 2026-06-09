# NdrTypeInfo::~NdrTypeInfo(void)

- ea: `0x18003426c`
- end: `0x1800342fa`
- name: `??1NdrTypeInfo@@EEAA@XZ`
- size: `142`
- prototype: `void __fastcall(NdrTypeInfo *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180034230`

## callees

- `0x18003426c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003429f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800342b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800342ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800342d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003429f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800342b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800342ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800342d4`
- `RPCRT4!NdrpReleaseTypeFormatString` at `0x1800342e1`
- `RPCRT4!NdrpReleaseTypeFormatString` at `0x1800342e1`

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
0x18003426c  push    rbx
0x18003426e  push    rbp
0x18003426f  push    rsi
0x180034270  push    rdi
0x180034271  sub     rsp, 28h
0x180034275  cmp     qword ptr [this+38h], 0
0x18003427a  lea     rax, ??_7NdrTypeInfo@@6B@; const NdrTypeInfo::`vftable'
0x180034281  mov     [this], rax
0x180034284  mov     rdi, this
0x180034287  jz      short loc_1800342D0
0x180034289  xor     esi, esi
0x18003428b  cmp     [this+138h], esi
0x180034291  jbe     short loc_1800342C6
0x180034293  mov     rbx, [rdi+38h]
0x180034297  lea     rbp, [rsi+rsi*2]
0x18003429b  mov     this, [rbx+rbp*8]; pv
0x18003429f  call    cs:__imp_CoTaskMemFree
0x1800342a5  cmp     qword ptr [rbx+rbp*8+10h], 0
0x1800342ab  jz      short loc_1800342BC
0x1800342ad  mov     this, [rdi+38h]
0x1800342b1  mov     this, [this+rbp*8+10h]; pv
0x1800342b6  call    cs:__imp_CoTaskMemFree
0x1800342bc  inc     esi
0x1800342be  cmp     esi, [rdi+138h]
0x1800342c4  jb      short loc_180034293
0x1800342c6  mov     this, [rdi+38h]; pv
0x1800342ca  call    cs:__imp_CoTaskMemFree
0x1800342d0  mov     this, [rdi+30h]; pv
0x1800342d4  call    cs:__imp_CoTaskMemFree
0x1800342da  mov     this, [rdi+90h]
0x1800342e1  call    cs:__imp_NdrpReleaseTypeFormatString
0x1800342e7  lea     rax, ??_7?$CALLFRAME_CACHE_ENTRY@UINTERFACE_HELPER_CLSID@@@@6B@; const CALLFRAME_CACHE_ENTRY<INTERFACE_HELPER_CLSID>::`vftable'
0x1800342ee  mov     [rdi], rax
0x1800342f1  add     rsp, 28h
0x1800342f5  pop     rdi
0x1800342f6  pop     rsi
0x1800342f7  pop     rbp
0x1800342f8  pop     rbx
0x1800342f9  retn
```
