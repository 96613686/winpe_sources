# ATL::CComObject<CCertEncodeStringArray>::Release(void)

- ea: `0x1800075f0`
- end: `0x180007676`
- name: `?Release@?$CComObject@VCCertEncodeStringArray@@@ATL@@UEAAKXZ`
- size: `134`
- prototype: `__int64 __fastcall(CCertEncodeStringArray *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180007680`

## callees

- `0x180001008`
- `0x18000374c`
- `0x1800075f0`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CCertEncodeStringArray>::Release(CCertEncodeStringArray *this)
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
      *(_QWORD *)this = &ATL::CComObject<CCertEncodeStringArray>::`vftable'{for `ATL::IDispatchImpl<ICertEncodeStringArray2,&_GUID const IID_ICertEncodeStringArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'};
      *((_QWORD *)this + 1) = &ATL::CComObject<CCertEncodeStringArray>::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeStringArray2>'};
      _InterlockedDecrement(&dword_18000F8D8);
      CCertEncodeStringArray::~CCertEncodeStringArray(this);
      operator delete(this);
    }
    _InterlockedDecrement(&dword_18000F8D8);
  }
  return v3;
}

```

## disassembly

```asm
0x1800075f0  mov     [rsp+arg_0], rbx
0x1800075f5  push    rdi
0x1800075f6  sub     rsp, 20h
0x1800075fa  mov     rbx, rcx
0x1800075fd  mov     r8d, 7FFFFFFFh
0x180007603  mov     ecx, [rcx+10h]
0x180007606  jmp     short loc_180007617
0x180007608  lea     edx, [rcx-1]
0x18000760b  mov     eax, ecx
0x18000760d  lock cmpxchg [rbx+10h], edx
0x180007612  jz      short loc_18000761C
0x180007614  mov     ecx, [rbx+10h]
0x180007617  cmp     ecx, r8d
0x18000761a  jnz     short loc_180007608
0x18000761c  lea     edi, [rcx-1]
0x18000761f  test    edi, edi
0x180007621  jnz     short loc_180007669
0x180007623  lock inc cs:dword_18000F8D8
0x18000762a  test    rbx, rbx
0x18000762d  jz      short loc_180007662
0x18000762f  lea     rax, ??_7?$CComObject@VCCertEncodeStringArray@@@ATL@@6B?$IDispatchImpl@UICertEncodeStringArray2@@$1?IID_ICertEncodeStringArray2@@3U_GUID@@B$1?LIBID_CERTENCODELib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@1@@; const ATL::CComObject<CCertEncodeStringArray>::`vftable'{for `ATL::IDispatchImpl<ICertEncodeStringArray2,&_GUID const IID_ICertEncodeStringArray2,&_GUID const LIBID_CERTENCODELib,1,0,ATL::CComTypeInfoHolder>'}
0x180007636  mov     dword ptr [rbx+10h], 1
0x18000763d  mov     [rbx], rax
0x180007640  mov     rcx, rbx; this
0x180007643  lea     rax, ??_7?$CComObject@VCCertEncodeStringArray@@@ATL@@6B?$ISupportErrorInfoImpl@$1?IID_ICertEncodeStringArray2@@3U_GUID@@B@1@@; const ATL::CComObject<CCertEncodeStringArray>::`vftable'{for `ATL::ISupportErrorInfoImpl<&_GUID const IID_ICertEncodeStringArray2>'}
0x18000764a  mov     [rbx+8], rax
0x18000764e  lock dec cs:dword_18000F8D8
0x180007655  call    ??1CCertEncodeStringArray@@QEAA@XZ; CCertEncodeStringArray::~CCertEncodeStringArray(void)
0x18000765a  mov     rcx, rbx; Block
0x18000765d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180007662  lock dec cs:dword_18000F8D8
0x180007669  mov     rbx, [rsp+28h+arg_0]
0x18000766e  mov     eax, edi
0x180007670  add     rsp, 20h
0x180007674  pop     rdi
0x180007675  retn
```
