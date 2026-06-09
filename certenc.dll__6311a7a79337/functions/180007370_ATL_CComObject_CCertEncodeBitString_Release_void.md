# ATL::CComObject<CCertEncodeBitString>::Release(void)

- ea: `0x180007370`
- end: `0x1800073f6`
- name: `?Release@?$CComObject@VCCertEncodeBitString@@@ATL@@UEAAKXZ`
- size: `134`
- prototype: `__int64 __fastcall(CCertEncodeBitString *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180007400`

## callees

- `0x180001008`
- `0x180004bc8`
- `0x180007370`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCertEncodeBitString>::Release(CCertEncodeBitString *this)
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
      *(_QWORD *)this = &ATL::CComObject<CCertEncodeBitString>::`vftable'{for `ATL::IDispatchImpl<ICertEncodeBitString2,&_GUID const IID_ICertEncodeBitString2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'};
      *((_QWORD *)this + 1) = &ATL::CComObject<CCertEncodeBitString>::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeBitString2>'};
      _InterlockedDecrement(&dword_18000F8D8);
      CCertEncodeBitString::~CCertEncodeBitString(this);
      operator delete(this);
    }
    _InterlockedDecrement(&dword_18000F8D8);
  }
  return v3;
}

```

## disassembly

```asm
0x180007370  mov     [rsp+arg_0], rbx
0x180007375  push    rdi
0x180007376  sub     rsp, 20h
0x18000737a  mov     rbx, rcx
0x18000737d  mov     r8d, 7FFFFFFFh
0x180007383  mov     ecx, [rcx+10h]
0x180007386  jmp     short loc_180007397
0x180007388  lea     edx, [rcx-1]
0x18000738b  mov     eax, ecx
0x18000738d  lock cmpxchg [rbx+10h], edx
0x180007392  jz      short loc_18000739C
0x180007394  mov     ecx, [rbx+10h]
0x180007397  cmp     ecx, r8d
0x18000739a  jnz     short loc_180007388
0x18000739c  lea     edi, [rcx-1]
0x18000739f  test    edi, edi
0x1800073a1  jnz     short loc_1800073E9
0x1800073a3  lock inc cs:dword_18000F8D8
0x1800073aa  test    rbx, rbx
0x1800073ad  jz      short loc_1800073E2
0x1800073af  lea     rax, ??_7?$CComObject@VCCertEncodeBitString@@@ATL@@6B?$IDispatchImpl@UICertEncodeBitString2@@$1?IID_ICertEncodeBitString2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CCertEncodeBitString>::`vftable'{for `ATL::IDispatchImpl<ICertEncodeBitString2,&_GUID const IID_ICertEncodeBitString2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'}
0x1800073b6  mov     dword ptr [rbx+10h], 1
0x1800073bd  mov     [rbx], rax
0x1800073c0  mov     rcx, rbx; this
0x1800073c3  lea     rax, ??_7?$CComObject@VCCertEncodeBitString@@@ATL@@6B?$ISupportErrorInfoImpl@$1?IID_ICertEncodeBitString2@@3U_GUID@@B@1@@; const ATL::CComObject<CCertEncodeBitString>::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeBitString2>'}
0x1800073ca  mov     [rbx+8], rax
0x1800073ce  lock dec cs:dword_18000F8D8
0x1800073d5  call    ??1CCertEncodeBitString@@QEAA@XZ; CCertEncodeBitString::~CCertEncodeBitString(void)
0x1800073da  mov     rcx, rbx; Block
0x1800073dd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800073e2  lock dec cs:dword_18000F8D8
0x1800073e9  mov     rbx, [rsp+28h+arg_0]
0x1800073ee  mov     eax, edi
0x1800073f0  add     rsp, 20h
0x1800073f4  pop     rdi
0x1800073f5  retn
```
