# Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong,_CVDD const *,ulong const *,CODEVIEW_INFORMATION_1 const *,ulong,ulong,ulong,EMBEDDED_PDB_INFORMATION const *,bool)

- ea: `0x180010bc8`
- end: `0x180010dc2`
- name: `??0CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0KPEBT_CVDD@@PEBKPEBUCODEVIEW_INFORMATION_1@@KKKPEBUEMBEDDED_PDB_INFORMATION@@_N@Z`
- size: `506`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, int, __int64, __int64, __int64, int, int, int, const void **, char)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180011bfc`
- `0x180011e80`

## callees

- `0x1800023c0`
- `0x1800029b5`
- `0x180007ab0`
- `0x180007cc4`
- `0x18000958c`
- `0x18000977c`
- `0x18001038c`
- `0x180010988`
- `0x180010bc8`
- `0x180013a4c`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        int a8,
        int a9,
        int a10,
        const void **a11,
        char a12)
{
  unsigned int v15; // edi
  _QWORD *v16; // r15
  void **v17; // r14
  char *v18; // rdx
  __int64 v19; // r15
  unsigned __int64 v20; // rcx
  unsigned __int64 v21; // rdi
  char *v22; // rax
  size_t v23; // rdi

  std::wstring::wstring(a1, a2);
  std::wstring::wstring(a1 + 32, a3);
  *(_DWORD *)(a1 + 64) = a4;
  v15 = 0;
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  v16 = (_QWORD *)(a1 + 88);
  *(_QWORD *)(a1 + 88) = 0;
  v17 = (void **)(a1 + 96);
  std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>((_QWORD *)(a1 + 96));
  *(_BYTE *)(a1 + 124) = a12;
  *(_DWORD *)(a1 + 128) = a8;
  *(_DWORD *)(a1 + 132) = a9;
  *(_DWORD *)(a1 + 136) = a10;
  if ( *(_DWORD *)(a1 + 64) )
  {
    if ( !(unsigned __int8)ATL::CAutoVectorPtr<_CVDD>::Allocate(a1 + 72, *(unsigned int *)(a1 + 64))
      || !ATL::CAutoVectorPtr<unsigned long>::Allocate((void **)(a1 + 80), *(unsigned int *)(a1 + 64))
      || !(unsigned __int8)ATL::CAutoVectorPtr<unsigned __int64>::Allocate(a1 + 88, *(unsigned int *)(a1 + 64)) )
    {
      ATL::AtlThrowImpl(-2147024882);
    }
    while ( v15 < *(_DWORD *)(a1 + 64) )
    {
      if ( *(_DWORD *)(a6 + 4LL * v15) > 0x628u )
        ATL::AtlThrowImpl(-2147418113);
      memcpy_0(
        (void *)(*(_QWORD *)(a1 + 72) + 1576LL * v15),
        (const void *)(1576LL * v15 + a5),
        *(unsigned int *)(a6 + 4LL * v15));
      if ( a7 )
        *(_QWORD *)(*v16 + 8LL * v15) = *(_QWORD *)(a7 + 8LL * v15);
      else
        *(_QWORD *)(*v16 + 8LL * v15) = 0;
      *(_DWORD *)(*(_QWORD *)(a1 + 80) + 4LL * v15) = *(_DWORD *)(a6 + 4LL * v15);
      ++v15;
    }
  }
  if ( a11 && *(_DWORD *)a11 && a11[1] )
  {
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      a12 = 0;
      v18 = (char *)*v17;
      v19 = *(_QWORD *)(a1 + 104);
      v20 = v19 - *(_QWORD *)(a1 + 96);
      v21 = *(unsigned int *)a11;
      if ( v21 < v20 )
      {
        v22 = &v18[v21];
LABEL_23:
        *(_QWORD *)(a1 + 104) = v22;
        goto LABEL_24;
      }
      if ( v21 > v20 )
      {
        if ( v21 <= *(_QWORD *)(a1 + 112) - (_QWORD)v18 )
        {
          v23 = v21 - v20;
          memset_0(*(void **)(a1 + 104), 0, v23);
          v22 = (char *)(v23 + v19);
          goto LABEL_23;
        }
        std::vector<unsigned char>::_Resize_reallocate<unsigned char>(a1 + 96, *(unsigned int *)a11, &a12);
      }
LABEL_24:
      memcpy_0(*v17, a11[1], *(unsigned int *)a11);
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
        ATL::AtlThrowImpl(-2147024882);
    }
    *(_WORD *)(a1 + 122) = *((_WORD *)a11 + 8);
    *(_WORD *)(a1 + 120) = *((_WORD *)a11 + 9);
  }
  return a1;
}

```

## disassembly

```asm
0x180010bc8  mov     [rsp+arg_8], rbx
0x180010bcd  mov     [rsp+arg_10], rsi
0x180010bd2  mov     [rsp+arg_0], rcx
0x180010bd7  push    rdi
0x180010bd8  push    r12
0x180010bda  push    r13
0x180010bdc  push    r14
0x180010bde  push    r15
0x180010be0  sub     rsp, 20h
0x180010be4  mov     edi, r9d
0x180010be7  mov     rbx, r8
0x180010bea  mov     rsi, rcx
0x180010bed  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180010bf2  nop
0x180010bf3  lea     rcx, [rsi+20h]
0x180010bf7  mov     rdx, rbx
0x180010bfa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180010bff  nop
0x180010c00  mov     [rsi+40h], edi
0x180010c03  xor     edi, edi
0x180010c05  mov     [rsi+48h], rdi
0x180010c09  mov     [rsi+50h], rdi
0x180010c0d  lea     r15, [rsi+58h]
0x180010c11  mov     [r15], rdi
0x180010c14  lea     r14, [rsi+60h]
0x180010c18  mov     rcx, r14
0x180010c1b  call    ??0?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>(void)
0x180010c20  nop
0x180010c21  mov     al, [rsp+48h+arg_58]
0x180010c28  mov     [rsi+7Ch], al
0x180010c2b  mov     eax, [rsp+48h+arg_38]
0x180010c32  mov     [rsi+80h], eax
0x180010c38  mov     eax, [rsp+48h+arg_40]
0x180010c3f  mov     [rsi+84h], eax
0x180010c45  mov     eax, [rsp+48h+arg_48]
0x180010c4c  mov     [rsi+88h], eax
0x180010c52  cmp     [rsi+40h], edi
0x180010c55  jz      loc_180010D0B
0x180010c5b  mov     edx, [rsi+40h]
0x180010c5e  lea     rcx, [rsi+48h]
0x180010c62  call    ?Allocate@?$CAutoVectorPtr@T_CVDD@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<_CVDD>::Allocate(unsigned __int64)
0x180010c67  test    al, al
0x180010c69  jz      loc_180010CFE
0x180010c6f  mov     edx, [rsi+40h]
0x180010c72  lea     rcx, [rsi+50h]
0x180010c76  call    ?Allocate@?$CAutoVectorPtr@K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<ulong>::Allocate(unsigned __int64)
0x180010c7b  test    al, al
0x180010c7d  jz      short loc_180010CFE
0x180010c7f  mov     edx, [rsi+40h]
0x180010c82  mov     rcx, r15
0x180010c85  call    ?Allocate@?$CAutoVectorPtr@_K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<unsigned __int64>::Allocate(unsigned __int64)
0x180010c8a  test    al, al
0x180010c8c  jz      short loc_180010CFE
0x180010c8e  mov     r13, [rsp+48h+arg_30]
0x180010c96  mov     r12, [rsp+48h+arg_28]
0x180010c9b  cmp     edi, [rsi+40h]
0x180010c9e  jnb     short loc_180010D09
0x180010ca0  mov     ebx, edi
0x180010ca2  cmp     dword ptr [r12+rbx*4], 628h
0x180010caa  ja      short loc_180010CF3
0x180010cac  imul    rcx, rbx, 628h
0x180010cb3  mov     r8d, [r12+rbx*4]; Size
0x180010cb7  mov     rdx, [rsp+48h+arg_20]
0x180010cbc  add     rdx, rcx; Src
0x180010cbf  add     rcx, [rsi+48h]; void *
0x180010cc3  call    memcpy_0
0x180010cc8  test    r13, r13
0x180010ccb  jz      short loc_180010CDB
0x180010ccd  mov     rcx, [r15]
0x180010cd0  mov     rax, [r13+rbx*8+0]
0x180010cd5  mov     [rcx+rbx*8], rax
0x180010cd9  jmp     short loc_180010CE4
0x180010cdb  mov     rax, [r15]
0x180010cde  xor     ecx, ecx
0x180010ce0  mov     [rax+rbx*8], rcx
0x180010ce4  mov     rcx, [rsi+50h]
0x180010ce8  mov     eax, [r12+rbx*4]
0x180010cec  mov     [rcx+rbx*4], eax
0x180010cef  inc     edi
0x180010cf1  jmp     short loc_180010C9B
0x180010cf3  mov     ecx, 8000FFFFh; int
0x180010cf8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180010cfe  mov     ecx, 8007000Eh; int
0x180010d03  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180010d09  xor     edi, edi
0x180010d0b  mov     rbx, [rsp+48h+arg_50]
0x180010d13  test    rbx, rbx
0x180010d16  jz      loc_180010DA7
0x180010d1c  cmp     [rbx], edi
0x180010d1e  jz      loc_180010DA7
0x180010d24  cmp     [rbx+8], rdi
0x180010d28  jz      short loc_180010DA7
0x180010d2a  mov     [rsp+48h+arg_58], dil
0x180010d32  mov     rdx, [r14]
0x180010d35  mov     r15, [r14+8]
0x180010d39  mov     rcx, r15
0x180010d3c  sub     rcx, rdx
0x180010d3f  mov     edi, [rbx]
0x180010d41  cmp     rdi, rcx
0x180010d44  jnb     short loc_180010D4C
0x180010d46  lea     rax, [rdi+rdx]
0x180010d4a  jmp     short loc_180010D83
0x180010d4c  jbe     short loc_180010D87
0x180010d4e  mov     rax, [r14+10h]
0x180010d52  sub     rax, rdx
0x180010d55  cmp     rdi, rax
0x180010d58  jbe     short loc_180010D6F
0x180010d5a  lea     r8, [rsp+48h+arg_58]
0x180010d62  mov     rdx, rdi
0x180010d65  mov     rcx, r14
0x180010d68  call    ??$_Resize_reallocate@E@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBE@Z; std::vector<uchar>::_Resize_reallocate<uchar>(unsigned __int64,uchar const &)
0x180010d6d  jmp     short loc_180010D87
0x180010d6f  sub     rdi, rcx
0x180010d72  mov     r8, rdi; Size
0x180010d75  xor     edx, edx; Val
0x180010d77  mov     rcx, r15; void *
0x180010d7a  call    memset_0
0x180010d7f  lea     rax, [rdi+r15]
0x180010d83  mov     [r14+8], rax
0x180010d87  mov     r8d, [rbx]; Size
0x180010d8a  mov     rdx, [rbx+8]; Src
0x180010d8e  mov     rcx, [r14]; void *
0x180010d91  call    memcpy_0
0x180010d96  nop
0x180010d97  movzx   eax, word ptr [rbx+10h]
0x180010d9b  mov     [rsi+7Ah], ax
0x180010d9f  movzx   eax, word ptr [rbx+12h]
0x180010da3  mov     [rsi+78h], ax
0x180010da7  mov     rax, rsi
0x180010daa  mov     rbx, [rsp+48h+arg_8]
0x180010daf  mov     rsi, [rsp+48h+arg_10]
0x180010db4  add     rsp, 20h
0x180010db8  pop     r15
0x180010dba  pop     r14
0x180010dbc  pop     r13
0x180010dbe  pop     r12
0x180010dc0  pop     rdi
0x180010dc1  retn
```
