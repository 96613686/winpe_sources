# Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong,_CVDD const *,ulong const *,CODEVIEW_INFORMATION_1 const *,ulong,ulong,ulong,EMBEDDED_PDB_INFORMATION const *,bool)

- ea: `0x18001135c`
- end: `0x180011557`
- name: `??0CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0KPEBT_CVDD@@PEBKPEBUCODEVIEW_INFORMATION_1@@KKKPEBUEMBEDDED_PDB_INFORMATION@@_N@Z`
- size: `507`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800123fc`
- `0x18001266c`

## callees

- `0x1800023e0`
- `0x1800029d5`
- `0x180007e18`
- `0x180008044`
- `0x180009a4c`
- `0x180009c3c`
- `0x180010b1c`
- `0x180011118`
- `0x18001135c`
- `0x180014240`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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

  ((void (*)(void))std::wstring::wstring)();
  std::wstring::wstring(a1 + 32, a3);
  *(_DWORD *)(a1 + 64) = a4;
  v15 = 0;
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  v16 = (_QWORD *)(a1 + 88);
  *(_QWORD *)(a1 + 88) = 0;
  v17 = (void **)(a1 + 96);
  std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>(a1 + 96);
  *(_BYTE *)(a1 + 124) = a12;
  *(_DWORD *)(a1 + 128) = a8;
  *(_DWORD *)(a1 + 132) = a9;
  *(_DWORD *)(a1 + 136) = a10;
  if ( *(_DWORD *)(a1 + 64) )
  {
    if ( !(unsigned __int8)ATL::CAutoVectorPtr<_CVDD>::Allocate(a1 + 72, *(unsigned int *)(a1 + 64))
      || !(unsigned __int8)ATL::CAutoVectorPtr<unsigned long>::Allocate(a1 + 80, *(unsigned int *)(a1 + 64))
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
    try
    {
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
    catch ( std::bad_alloc )
    {
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
0x18001135c  mov     [rsp+arg_8], rbx
0x180011361  mov     [rsp+arg_10], rsi
0x180011366  mov     [rsp+arg_0], rcx
0x18001136b  push    rdi
0x18001136c  push    r12
0x18001136e  push    r13
0x180011370  push    r14
0x180011372  push    r15
0x180011374  sub     rsp, 20h
0x180011378  mov     edi, r9d
0x18001137b  mov     rbx, r8
0x18001137e  mov     rsi, rcx
0x180011381  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180011386  nop
0x180011387  lea     rcx, [rsi+20h]
0x18001138b  mov     rdx, rbx
0x18001138e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180011393  nop
0x180011394  mov     [rsi+40h], edi
0x180011397  xor     edi, edi
0x180011399  mov     [rsi+48h], rdi
0x18001139d  mov     [rsi+50h], rdi
0x1800113a1  lea     r15, [rsi+58h]
0x1800113a5  mov     [r15], rdi
0x1800113a8  lea     r14, [rsi+60h]
0x1800113ac  mov     rcx, r14
0x1800113af  call    ??0?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>(void)
0x1800113b4  nop
0x1800113b5  mov     al, [rsp+48h+arg_58]
0x1800113bc  mov     [rsi+7Ch], al
0x1800113bf  mov     eax, [rsp+48h+arg_38]
0x1800113c6  mov     [rsi+80h], eax
0x1800113cc  mov     eax, [rsp+48h+arg_40]
0x1800113d3  mov     [rsi+84h], eax
0x1800113d9  mov     eax, [rsp+48h+arg_48]
0x1800113e0  mov     [rsi+88h], eax
0x1800113e6  cmp     [rsi+40h], edi
0x1800113e9  jz      loc_18001149F
0x1800113ef  mov     edx, [rsi+40h]
0x1800113f2  lea     rcx, [rsi+48h]
0x1800113f6  call    ?Allocate@?$CAutoVectorPtr@T_CVDD@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<_CVDD>::Allocate(unsigned __int64)
0x1800113fb  test    al, al
0x1800113fd  jz      loc_180011492
0x180011403  mov     edx, [rsi+40h]
0x180011406  lea     rcx, [rsi+50h]
0x18001140a  call    ?Allocate@?$CAutoVectorPtr@K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<ulong>::Allocate(unsigned __int64)
0x18001140f  test    al, al
0x180011411  jz      short loc_180011492
0x180011413  mov     edx, [rsi+40h]
0x180011416  mov     rcx, r15
0x180011419  call    ?Allocate@?$CAutoVectorPtr@_K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<unsigned __int64>::Allocate(unsigned __int64)
0x18001141e  test    al, al
0x180011420  jz      short loc_180011492
0x180011422  mov     r13, [rsp+48h+arg_30]
0x18001142a  mov     r12, [rsp+48h+arg_28]
0x18001142f  cmp     edi, [rsi+40h]
0x180011432  jnb     short loc_18001149D
0x180011434  mov     ebx, edi
0x180011436  cmp     dword ptr [r12+rbx*4], 628h
0x18001143e  ja      short loc_180011487
0x180011440  imul    rcx, rbx, 628h
0x180011447  mov     r8d, [r12+rbx*4]; Size
0x18001144b  mov     rdx, [rsp+48h+arg_20]
0x180011450  add     rdx, rcx; Src
0x180011453  add     rcx, [rsi+48h]; void *
0x180011457  call    memcpy_0
0x18001145c  test    r13, r13
0x18001145f  jz      short loc_18001146F
0x180011461  mov     rcx, [r15]
0x180011464  mov     rax, [r13+rbx*8+0]
0x180011469  mov     [rcx+rbx*8], rax
0x18001146d  jmp     short loc_180011478
0x18001146f  mov     rax, [r15]
0x180011472  xor     ecx, ecx
0x180011474  mov     [rax+rbx*8], rcx
0x180011478  mov     rcx, [rsi+50h]
0x18001147c  mov     eax, [r12+rbx*4]
0x180011480  mov     [rcx+rbx*4], eax
0x180011483  inc     edi
0x180011485  jmp     short loc_18001142F
0x180011487  mov     ecx, 8000FFFFh; int
0x18001148c  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180011492  mov     ecx, 8007000Eh; int
0x180011497  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001149d  xor     edi, edi
0x18001149f  mov     rbx, [rsp+48h+arg_50]
0x1800114a7  test    rbx, rbx
0x1800114aa  jz      loc_18001153B
0x1800114b0  cmp     [rbx], edi
0x1800114b2  jz      loc_18001153B
0x1800114b8  cmp     [rbx+8], rdi
0x1800114bc  jz      short loc_18001153B
0x1800114be  mov     [rsp+48h+arg_58], dil
0x1800114c6  mov     rdx, [r14]
0x1800114c9  mov     r15, [r14+8]
0x1800114cd  mov     rcx, r15
0x1800114d0  sub     rcx, rdx
0x1800114d3  mov     edi, [rbx]
0x1800114d5  cmp     rdi, rcx
0x1800114d8  jnb     short loc_1800114E0
0x1800114da  lea     rax, [rdi+rdx]
0x1800114de  jmp     short loc_180011517
0x1800114e0  jbe     short loc_18001151B
0x1800114e2  mov     rax, [r14+10h]
0x1800114e6  sub     rax, rdx
0x1800114e9  cmp     rdi, rax
0x1800114ec  jbe     short loc_180011503
0x1800114ee  lea     r8, [rsp+48h+arg_58]
0x1800114f6  mov     rdx, rdi
0x1800114f9  mov     rcx, r14
0x1800114fc  call    ??$_Resize_reallocate@E@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBE@Z; std::vector<uchar>::_Resize_reallocate<uchar>(unsigned __int64,uchar const &)
0x180011501  jmp     short loc_18001151B
0x180011503  sub     rdi, rcx
0x180011506  mov     r8, rdi; Size
0x180011509  xor     edx, edx; Val
0x18001150b  mov     rcx, r15; void *
0x18001150e  call    memset_0
0x180011513  lea     rax, [rdi+r15]
0x180011517  mov     [r14+8], rax
0x18001151b  mov     r8d, [rbx]; Size
0x18001151e  mov     rdx, [rbx+8]; Src
0x180011522  mov     rcx, [r14]; void *
0x180011525  call    memcpy_0
0x18001152a  nop
0x18001152b  movzx   eax, word ptr [rbx+10h]
0x18001152f  mov     [rsi+7Ah], ax
0x180011533  movzx   eax, word ptr [rbx+12h]
0x180011537  mov     [rsi+78h], ax
0x18001153b  mov     rax, rsi
0x18001153e  mov     rbx, [rsp+48h+arg_8]
0x180011543  mov     rsi, [rsp+48h+arg_10]
0x180011548  add     rsp, 20h
0x18001154c  pop     r15
0x18001154e  pop     r14
0x180011550  pop     r13
0x180011552  pop     r12
0x180011554  pop     rdi
0x180011555  retn
```
