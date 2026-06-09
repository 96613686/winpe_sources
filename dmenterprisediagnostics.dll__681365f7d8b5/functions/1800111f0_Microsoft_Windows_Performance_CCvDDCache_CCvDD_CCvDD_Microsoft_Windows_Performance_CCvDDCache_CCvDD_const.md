# Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(Microsoft::Windows::Performance::CCvDDCache::CCvDD const &)

- ea: `0x1800111f0`
- end: `0x180011356`
- name: `??0CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@AEBU01234@@Z`
- size: `358`
- prototype: `__int64 __fastcall(Microsoft::Windows::Performance::CCvDDCache::CCvDD *__hidden this, const struct Microsoft::Windows::Performance::CCvDDCache::CCvDD *)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800102a8`

## callees

- `0x1800029d5`
- `0x180008044`
- `0x180009a4c`
- `0x180009c3c`
- `0x180010058`
- `0x180011118`
- `0x1800111f0`
- `0x180014240`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
0x1800111f0  mov     [rsp+arg_8], rbx
0x1800111f5  mov     [rsp+arg_10], rbp
0x1800111fa  mov     [rsp+arg_0], rcx
0x1800111ff  push    rsi
0x180011200  push    rdi
0x180011201  push    r12
0x180011203  push    r14
0x180011205  push    r15
0x180011207  sub     rsp, 20h
0x18001120b  mov     rbp, rdx
0x18001120e  mov     rbx, rcx
0x180011211  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180011216  nop
0x180011217  lea     rdx, [rbp+20h]
0x18001121b  lea     rcx, [rbx+20h]
0x18001121f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180011224  nop
0x180011225  mov     eax, [rbp+40h]
0x180011228  mov     [rbx+40h], eax
0x18001122b  lea     r12, [rbx+48h]
0x18001122f  xor     esi, esi
0x180011231  mov     [r12], rsi
0x180011235  lea     r14, [rbx+50h]
0x180011239  mov     [r14], rsi
0x18001123c  lea     r15, [rbx+58h]
0x180011240  mov     [r15], rsi
0x180011243  lea     rcx, [rbx+60h]
0x180011247  mov     [rcx], rsi
0x18001124a  mov     [rcx+8], rsi
0x18001124e  mov     [rcx+10h], rsi
0x180011252  lea     r8, [rbp+60h]
0x180011256  lea     r9, [r8+8]
0x18001125a  mov     rdx, [r9]
0x18001125d  sub     rdx, [r8]
0x180011260  call    ??$_Construct_n@AEBQEAEAEBQEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBQEAE1@Z; std::vector<uchar>::_Construct_n<uchar * const &,uchar * const &>(unsigned __int64,uchar * const &,uchar * const &)
0x180011265  nop
0x180011266  movzx   eax, word ptr [rbp+78h]
0x18001126a  mov     [rbx+78h], ax
0x18001126e  movzx   eax, word ptr [rbp+7Ah]
0x180011272  mov     [rbx+7Ah], ax
0x180011276  mov     al, [rbp+7Ch]
0x180011279  mov     [rbx+7Ch], al
0x18001127c  mov     eax, [rbp+80h]
0x180011282  mov     [rbx+80h], eax
0x180011288  mov     eax, [rbp+84h]
0x18001128e  mov     [rbx+84h], eax
0x180011294  mov     eax, [rbp+88h]
0x18001129a  mov     [rbx+88h], eax
0x1800112a0  cmp     [rbx+40h], esi
0x1800112a3  jz      loc_18001133B
0x1800112a9  mov     edx, [rbx+40h]
0x1800112ac  mov     rcx, r12
0x1800112af  call    ?Allocate@?$CAutoVectorPtr@T_CVDD@@@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<_CVDD>::Allocate(unsigned __int64)
0x1800112b4  test    al, al
0x1800112b6  jz      short loc_180011330
0x1800112b8  mov     edx, [rbx+40h]
0x1800112bb  mov     rcx, r14
0x1800112be  call    ?Allocate@?$CAutoVectorPtr@K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<ulong>::Allocate(unsigned __int64)
0x1800112c3  test    al, al
0x1800112c5  jz      short loc_180011330
0x1800112c7  mov     edx, [rbx+40h]
0x1800112ca  mov     rcx, r15
0x1800112cd  call    ?Allocate@?$CAutoVectorPtr@_K@ATL@@QEAA_N_K@Z; ATL::CAutoVectorPtr<unsigned __int64>::Allocate(unsigned __int64)
0x1800112d2  test    al, al
0x1800112d4  jz      short loc_180011330
0x1800112d6  cmp     esi, [rbx+40h]
0x1800112d9  jnb     short loc_18001133B
0x1800112db  mov     edi, esi
0x1800112dd  mov     rax, [rbp+50h]
0x1800112e1  cmp     dword ptr [rax+rdi*4], 628h
0x1800112e8  ja      short loc_180011325
0x1800112ea  imul    rcx, rdi, 628h
0x1800112f1  mov     r8d, [rax+rdi*4]; Size
0x1800112f5  mov     rdx, [rbp+48h]
0x1800112f9  add     rdx, rcx; Src
0x1800112fc  add     rcx, [r12]; void *
0x180011300  call    memcpy_0
0x180011305  mov     rax, [rbp+58h]
0x180011309  mov     rcx, [r15]
0x18001130c  mov     rax, [rax+rdi*8]
0x180011310  mov     [rcx+rdi*8], rax
0x180011314  mov     rax, [rbp+50h]
0x180011318  mov     rcx, [r14]
0x18001131b  mov     eax, [rax+rdi*4]
0x18001131e  mov     [rcx+rdi*4], eax
0x180011321  inc     esi
0x180011323  jmp     short loc_1800112D6
0x180011325  mov     ecx, 8000FFFFh; int
0x18001132a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180011330  mov     ecx, 8007000Eh; int
0x180011335  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18001133b  mov     rax, rbx
0x18001133e  mov     rbx, [rsp+48h+arg_8]
0x180011343  mov     rbp, [rsp+48h+arg_10]
0x180011348  add     rsp, 20h
0x18001134c  pop     r15
0x18001134e  pop     r14
0x180011350  pop     r12
0x180011352  pop     rdi
0x180011353  pop     rsi
0x180011354  retn
```
