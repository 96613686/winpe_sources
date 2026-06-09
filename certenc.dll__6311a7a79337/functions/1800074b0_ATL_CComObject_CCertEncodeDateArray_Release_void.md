# ATL::CComObject<CCertEncodeDateArray>::Release(void)

- ea: `0x1800074b0`
- end: `0x180007536`
- name: `?Release@?$CComObject@VCCertEncodeDateArray@@@ATL@@UEAAKXZ`
- size: `134`
- prototype: `__int64 __fastcall(CCertEncodeDateArray *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180007540`

## callees

- `0x180001008`
- `0x180001a2c`
- `0x1800074b0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCertEncodeDateArray>::Release(CCertEncodeDateArray *this)
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
      *(_QWORD *)this = &ATL::CComObject<CCertEncodeDateArray>::`vftable'{for `ATL::IDispatchImpl<ICertEncodeDateArray2,&_GUID const IID_ICertEncodeDateArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'};
      *((_QWORD *)this + 1) = &ATL::CComObject<CCertEncodeDateArray>::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeDateArray2>'};
      _InterlockedDecrement(&dword_18000F8D8);
      CCertEncodeDateArray::~CCertEncodeDateArray(this);
      operator delete(this);
    }
    _InterlockedDecrement(&dword_18000F8D8);
  }
  return v3;
}

```

## disassembly

```asm
0x1800074b0  mov     [rsp+arg_0], rbx
0x1800074b5  push    rdi
0x1800074b6  sub     rsp, 20h
0x1800074ba  mov     rbx, rcx
0x1800074bd  mov     r8d, 7FFFFFFFh
0x1800074c3  mov     ecx, [rcx+10h]
0x1800074c6  jmp     short loc_1800074D7
0x1800074c8  lea     edx, [rcx-1]
0x1800074cb  mov     eax, ecx
0x1800074cd  lock cmpxchg [rbx+10h], edx
0x1800074d2  jz      short loc_1800074DC
0x1800074d4  mov     ecx, [rbx+10h]
0x1800074d7  cmp     ecx, r8d
0x1800074da  jnz     short loc_1800074C8
0x1800074dc  lea     edi, [rcx-1]
0x1800074df  test    edi, edi
0x1800074e1  jnz     short loc_180007529
0x1800074e3  lock inc cs:dword_18000F8D8
0x1800074ea  test    rbx, rbx
0x1800074ed  jz      short loc_180007522
0x1800074ef  lea     rax, ??_7?$CComObject@VCCertEncodeDateArray@@@ATL@@6B?$IDispatchImpl@UICertEncodeDateArray2@@$1?IID_ICertEncodeDateArray2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CCertEncodeDateArray>::`vftable'{for `ATL::IDispatchImpl<ICertEncodeDateArray2,&_GUID const IID_ICertEncodeDateArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'}
0x1800074f6  mov     dword ptr [rbx+10h], 1
0x1800074fd  mov     [rbx], rax
0x180007500  mov     rcx, rbx; this
0x180007503  lea     rax, ??_7?$CComObject@VCCertEncodeDateArray@@@ATL@@6B?$ISupportErrorInfoImpl@$1?IID_ICertEncodeDateArray2@@3U_GUID@@B@1@@; const ATL::CComObject<CCertEncodeDateArray>::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeDateArray2>'}
0x18000750a  mov     [rbx+8], rax
0x18000750e  lock dec cs:dword_18000F8D8
0x180007515  call    ??1CCertEncodeDateArray@@QEAA@XZ; CCertEncodeDateArray::~CCertEncodeDateArray(void)
0x18000751a  mov     rcx, rbx; Block
0x18000751d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007522  lock dec cs:dword_18000F8D8
0x180007529  mov     rbx, [rsp+28h+arg_0]
0x18000752e  mov     eax, edi
0x180007530  add     rsp, 20h
0x180007534  pop     rdi
0x180007535  retn
```
