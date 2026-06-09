# Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(Microsoft::Windows::Performance::CCvDDCache::CCvDD const &)

- ea: `0x180010a5c`
- end: `0x180010bc1`
- name: `??0CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@AEBU01234@@Z`
- size: `357`
- prototype: `Microsoft::Windows::Performance::CCvDDCache::CCvDD *__fastcall(Microsoft::Windows::Performance::CCvDDCache::CCvDD *this, const struct Microsoft::Windows::Performance::CCvDDCache::CCvDD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180018014`

## callees

- `0x1800029b5`
- `0x180007cc4`
- `0x18000958c`
- `0x18000977c`
- `0x18000f96c`
- `0x180010988`
- `0x180010a5c`
- `0x180013a4c`

## pseudocode

```c
Microsoft::Windows::Performance::CCvDDCache::CCvDD *__fastcall Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(
        Microsoft::Windows::Performance::CCvDDCache::CCvDD *this,
        const struct Microsoft::Windows::Performance::CCvDDCache::CCvDD *a2)
{
  unsigned int v4; // esi
  __int64 v5; // rax

  std::wstring::wstring(this, a2);
  std::wstring::wstring((char *)this + 32, (char *)a2 + 32);
  *((_DWORD *)this + 16) = *((_DWORD *)a2 + 16);
  v4 = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 14) = 0;
  std::vector<unsigned char>::_Construct_n<unsigned char * const &,unsigned char * const &>(
    (char *)this + 96,
    *((_QWORD *)a2 + 13) - *((_QWORD *)a2 + 12));
  *((_WORD *)this + 60) = *((_WORD *)a2 + 60);
  *((_WORD *)this + 61) = *((_WORD *)a2 + 61);
  *((_BYTE *)this + 124) = *((_BYTE *)a2 + 124);
  *((_DWORD *)this + 32) = *((_DWORD *)a2 + 32);
  *((_DWORD *)this + 33) = *((_DWORD *)a2 + 33);
  *((_DWORD *)this + 34) = *((_DWORD *)a2 + 34);
  if ( *((_DWORD *)this + 16) )
  {
    if ( !(unsigned __int8)ATL::CAutoVectorPtr<_CVDD>::Allocate((char *)this + 72, *((unsigned int *)this + 16))
      || !(unsigned __int8)ATL::CAutoVectorPtr<unsigned long>::Allocate((char *)this + 80, *((unsigned int *)this + 16))
      || !(unsigned __int8)ATL::CAutoVectorPtr<unsigned __int64>::Allocate(
                             (char *)this + 88,
                             *((unsigned int *)this + 16)) )
    {
      ATL::AtlThrowImpl(-2147024882);
    }
    while ( v4 < *((_DWORD *)this + 16) )
    {
      v5 = *((_QWORD *)a2 + 10);
      if ( *(_DWORD *)(v5 + 4LL * v4) > 0x628u )
        ATL::AtlThrowImpl(-2147418113);
      memcpy_0(
        (void *)(*((_QWORD *)this + 9) + 1576LL * v4),
        (const void *)(1576LL * v4 + *((_QWORD *)a2 + 9)),
        *(unsigned int *)(v5 + 4LL * v4));
      *(_QWORD *)(*((_QWORD *)this + 11) + 8LL * v4) = *(_QWORD *)(*((_QWORD *)a2 + 11) + 8LL * v4);
      *(_DWORD *)(*((_QWORD *)this + 10) + 4LL * v4) = *(_DWORD *)(*((_QWORD *)a2 + 10) + 4LL * v4);
      ++v4;
    }
  }
  return this;
}

```

## disassembly

```asm
0x180010a5c  mov     [rsp+arg_8], rbx
0x180010a61  mov     [rsp+arg_10], rbp
0x180010a66  mov     [rsp+arg_0], rcx
0x180010a6b  push    rsi
0x180010a6c  push    rdi
0x180010a6d  push    r12
0x180010a6f  push    r14
0x180010a71  push    r15
0x180010a73  sub     rsp, 20h
0x180010a77  mov     rbp, rdx
0x180010a7a  mov     rbx, rcx
0x180010a7d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180010a82  nop
0x180010a83  lea     rdx, [rbp+20h]
0x180010a87  lea     rcx, [rbx+20h]
0x180010a8b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180010a90  nop
0x180010a91  mov     eax, [rbp+40h]
0x180010a94  mov     [rbx+40h], eax
0x180010a97  lea     r12, [rbx+48h]
0x180010a9b  xor     esi, esi
0x180010a9d  mov     [r12], rsi
0x180010aa1  lea     r14, [rbx+50h]
0x180010aa5  mov     [r14], rsi
0x180010aa8  lea     r15, [rbx+58h]
0x180010aac  mov     [r15], rsi
0x180010aaf  lea     rcx, [rbx+60h]
0x180010ab3  mov     [rcx], rsi
0x180010ab6  mov     [rcx+8], rsi
0x180010aba  mov     [rcx+10h], rsi
0x180010abe  lea     r8, [rbp+60h]
0x180010ac2  lea     r9, [r8+8]
0x180010ac6  mov     rdx, [r9]
0x180010ac9  sub     rdx, [r8]
0x180010acc  call    ??$_Construct_n@AEBQEAEAEBQEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBQEAE1@Z; std::vector<uchar>::_Construct_n<uchar * const &,uchar * const &>(unsigned __int64,uchar * const &,uchar * const &)
0x180010ad1  nop
0x180010ad2  movzx   eax, word ptr [rbp+78h]
0x180010ad6  mov     [rbx+78h], ax
0x180010ada  movzx   eax, word ptr [rbp+7Ah]
0x180010ade  mov     [rbx+7Ah], ax
0x180010ae2  mov     al, [rbp+7Ch]
0x180010ae5  mov     [rbx+7Ch], al
0x180010ae8  mov     eax, [rbp+80h]
0x180010aee  mov     [rbx+80h], eax
0x180010af4  mov     eax, [rbp+84h]
0x180010afa  mov     [rbx+84h], eax
0x180010b00  mov     eax, [rbp+88h]
0x180010b06  mov     [rbx+88h], eax
0x180010b0c  cmp     [rbx+40h], esi
0x180010b0f  jz      loc_180010BA7
0x180010b15  mov     edx, [rbx+40h]
0x180010b18  mov     rcx, r12
0x180010b1b  call    ?Allocate@?$CAutoVectorPtr@T_CVDD@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<_CVDD>::Allocate(unsigned __int64)
0x180010b20  test    al, al
0x180010b22  jz      short loc_180010B9C
0x180010b24  mov     edx, [rbx+40h]
0x180010b27  mov     rcx, r14
0x180010b2a  call    ?Allocate@?$CAutoVectorPtr@K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<ulong>::Allocate(unsigned __int64)
0x180010b2f  test    al, al
0x180010b31  jz      short loc_180010B9C
0x180010b33  mov     edx, [rbx+40h]
0x180010b36  mov     rcx, r15
0x180010b39  call    ?Allocate@?$CAutoVectorPtr@_K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<unsigned __int64>::Allocate(unsigned __int64)
0x180010b3e  test    al, al
0x180010b40  jz      short loc_180010B9C
0x180010b42  cmp     esi, [rbx+40h]
0x180010b45  jnb     short loc_180010BA7
0x180010b47  mov     edi, esi
0x180010b49  mov     rax, [rbp+50h]
0x180010b4d  cmp     dword ptr [rax+rdi*4], 628h
0x180010b54  ja      short loc_180010B91
0x180010b56  imul    rcx, rdi, 628h
0x180010b5d  mov     r8d, [rax+rdi*4]; Size
0x180010b61  mov     rdx, [rbp+48h]
0x180010b65  add     rdx, rcx; Src
0x180010b68  add     rcx, [r12]; void *
0x180010b6c  call    memcpy_0
0x180010b71  mov     rax, [rbp+58h]
0x180010b75  mov     rcx, [r15]
0x180010b78  mov     rax, [rax+rdi*8]
0x180010b7c  mov     [rcx+rdi*8], rax
0x180010b80  mov     rax, [rbp+50h]
0x180010b84  mov     rcx, [r14]
0x180010b87  mov     eax, [rax+rdi*4]
0x180010b8a  mov     [rcx+rdi*4], eax
0x180010b8d  inc     esi
0x180010b8f  jmp     short loc_180010B42
0x180010b91  mov     ecx, 8000FFFFh; int
0x180010b96  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180010b9c  mov     ecx, 8007000Eh; int
0x180010ba1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180010ba7  mov     rax, rbx
0x180010baa  mov     rbx, [rsp+48h+arg_8]
0x180010baf  mov     rbp, [rsp+48h+arg_10]
0x180010bb4  add     rsp, 20h
0x180010bb8  pop     r15
0x180010bba  pop     r14
0x180010bbc  pop     r12
0x180010bbe  pop     rdi
0x180010bbf  pop     rsi
0x180010bc0  retn
```
