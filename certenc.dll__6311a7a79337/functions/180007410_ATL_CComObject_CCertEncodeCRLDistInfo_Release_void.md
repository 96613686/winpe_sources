# ATL::CComObject<CCertEncodeCRLDistInfo>::Release(void)

- ea: `0x180007410`
- end: `0x180007496`
- name: `?Release@?$CComObject@VCCertEncodeCRLDistInfo@@@ATL@@UEAAKXZ`
- size: `134`
- prototype: `__int64 __fastcall(CCertEncodeCRLDistInfo *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800074a0`

## callees

- `0x180001008`
- `0x180007410`
- `0x180007a20`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCertEncodeCRLDistInfo>::Release(CCertEncodeCRLDistInfo *this)
{
  signed __int32 i; // ecx
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)this + 4);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange((volatile signed __int32 *)this + 4, i - 1, i);
        i = *((_DWORD *)this + 4) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    _InterlockedIncrement(&dword_18000F8D8);
    if ( this )
    {
      *((_DWORD *)this + 4) = 1;
      *(_QWORD *)this = &ATL::CComObject<CCertEncodeCRLDistInfo>::`vftable'{for `ATL::IDispatchImpl<ICertEncodeCRLDistInfo2,&_GUID const IID_ICertEncodeCRLDistInfo2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'};
      *((_QWORD *)this + 1) = &ATL::CComObject<CCertEncodeCRLDistInfo>::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeCRLDistInfo2>'};
      _InterlockedDecrement(&dword_18000F8D8);
      CCertEncodeCRLDistInfo::~CCertEncodeCRLDistInfo(this);
      operator delete(this);
    }
    _InterlockedDecrement(&dword_18000F8D8);
  }
  return v3;
}

```

## disassembly

```asm
0x180007410  mov     [rsp+arg_0], rbx
0x180007415  push    rdi
0x180007416  sub     rsp, 20h
0x18000741a  mov     rbx, rcx
0x18000741d  mov     r8d, 7FFFFFFFh
0x180007423  mov     ecx, [rcx+10h]
0x180007426  jmp     short loc_180007437
0x180007428  lea     edx, [rcx-1]
0x18000742b  mov     eax, ecx
0x18000742d  lock cmpxchg [rbx+10h], edx
0x180007432  jz      short loc_18000743C
0x180007434  mov     ecx, [rbx+10h]
0x180007437  cmp     ecx, r8d
0x18000743a  jnz     short loc_180007428
0x18000743c  lea     edi, [rcx-1]
0x18000743f  test    edi, edi
0x180007441  jnz     short loc_180007489
0x180007443  lock inc cs:dword_18000F8D8
0x18000744a  test    rbx, rbx
0x18000744d  jz      short loc_180007482
0x18000744f  lea     rax, ??_7?$CComObject@VCCertEncodeCRLDistInfo@@@ATL@@6B?$IDispatchImpl@UICertEncodeCRLDistInfo2@@$1?IID_ICertEncodeCRLDistInfo2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CCertEncodeCRLDistInfo>::`vftable'{for `ATL::IDispatchImpl<ICertEncodeCRLDistInfo2,&_GUID const IID_ICertEncodeCRLDistInfo2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'}
0x180007456  mov     dword ptr [rbx+10h], 1
0x18000745d  mov     [rbx], rax
0x180007460  mov     rcx, rbx; this
0x180007463  lea     rax, ??_7?$CComObject@VCCertEncodeCRLDistInfo@@@ATL@@6B?$ISupportErrorInfoImpl@$1?IID_ICertEncodeCRLDistInfo2@@3U_GUID@@B@1@@; const ATL::CComObject<CCertEncodeCRLDistInfo>::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeCRLDistInfo2>'}
0x18000746a  mov     [rbx+8], rax
0x18000746e  lock dec cs:dword_18000F8D8
0x180007475  call    ??1CCertEncodeCRLDistInfo@@QEAA@XZ; CCertEncodeCRLDistInfo::~CCertEncodeCRLDistInfo(void)
0x18000747a  mov     rcx, rbx; Block
0x18000747d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007482  lock dec cs:dword_18000F8D8
0x180007489  mov     rbx, [rsp+28h+arg_0]
0x18000748e  mov     eax, edi
0x180007490  add     rsp, 20h
0x180007494  pop     rdi
0x180007495  retn
```
