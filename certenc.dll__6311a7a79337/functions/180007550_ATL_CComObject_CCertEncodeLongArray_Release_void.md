# ATL::CComObject<CCertEncodeLongArray>::Release(void)

- ea: `0x180007550`
- end: `0x1800075d6`
- name: `?Release@?$CComObject@VCCertEncodeLongArray@@@ATL@@UEAAKXZ`
- size: `134`
- prototype: `__int64 __fastcall(CCertEncodeLongArray *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800075e0`

## callees

- `0x180001008`
- `0x1800022ac`
- `0x180007550`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCertEncodeLongArray>::Release(CCertEncodeLongArray *this)
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
      *(_QWORD *)this = &ATL::CComObject<CCertEncodeLongArray>::`vftable'{for `ATL::IDispatchImpl<ICertEncodeLongArray2,&_GUID const IID_ICertEncodeLongArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'};
      *((_QWORD *)this + 1) = &ATL::CComObject<CCertEncodeLongArray>::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeLongArray2>'};
      _InterlockedDecrement(&dword_18000F8D8);
      CCertEncodeLongArray::~CCertEncodeLongArray(this);
      operator delete(this);
    }
    _InterlockedDecrement(&dword_18000F8D8);
  }
  return v3;
}

```

## disassembly

```asm
0x180007550  mov     [rsp+arg_0], rbx
0x180007555  push    rdi
0x180007556  sub     rsp, 20h
0x18000755a  mov     rbx, rcx
0x18000755d  mov     r8d, 7FFFFFFFh
0x180007563  mov     ecx, [rcx+10h]
0x180007566  jmp     short loc_180007577
0x180007568  lea     edx, [rcx-1]
0x18000756b  mov     eax, ecx
0x18000756d  lock cmpxchg [rbx+10h], edx
0x180007572  jz      short loc_18000757C
0x180007574  mov     ecx, [rbx+10h]
0x180007577  cmp     ecx, r8d
0x18000757a  jnz     short loc_180007568
0x18000757c  lea     edi, [rcx-1]
0x18000757f  test    edi, edi
0x180007581  jnz     short loc_1800075C9
0x180007583  lock inc cs:dword_18000F8D8
0x18000758a  test    rbx, rbx
0x18000758d  jz      short loc_1800075C2
0x18000758f  lea     rax, ??_7?$CComObject@VCCertEncodeLongArray@@@ATL@@6B?$IDispatchImpl@UICertEncodeLongArray2@@$1?IID_ICertEncodeLongArray2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CCertEncodeLongArray>::`vftable'{for `ATL::IDispatchImpl<ICertEncodeLongArray2,&_GUID const IID_ICertEncodeLongArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'}
0x180007596  mov     dword ptr [rbx+10h], 1
0x18000759d  mov     [rbx], rax
0x1800075a0  mov     rcx, rbx; this
0x1800075a3  lea     rax, ??_7?$CComObject@VCCertEncodeLongArray@@@ATL@@6B?$ISupportErrorInfoImpl@$1?IID_ICertEncodeLongArray2@@3U_GUID@@B@1@@; const ATL::CComObject<CCertEncodeLongArray>::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeLongArray2>'}
0x1800075aa  mov     [rbx+8], rax
0x1800075ae  lock dec cs:dword_18000F8D8
0x1800075b5  call    ??1CCertEncodeLongArray@@QEAA@XZ; CCertEncodeLongArray::~CCertEncodeLongArray(void)
0x1800075ba  mov     rcx, rbx; Block
0x1800075bd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800075c2  lock dec cs:dword_18000F8D8
0x1800075c9  mov     rbx, [rsp+28h+arg_0]
0x1800075ce  mov     eax, edi
0x1800075d0  add     rsp, 20h
0x1800075d4  pop     rdi
0x1800075d5  retn
```
