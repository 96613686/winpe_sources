# Marshal::Details::ReadObjectXml(Marshal::XmlReader &,int,void *,Marshal::UnmarshalContext const &,Marshal::ClassData const &,Marshal::Details::ArrayView<Marshal::Details::BaseTypeData const *>,Marshal::Details::ArrayView<Marshal::Details::XmlTypeData const *>)

- ea: `0x18001ff3c`
- end: `0x180020467`
- name: `?ReadObjectXml@Details@Marshal@@YA_NAEAUXmlReader@2@HPEAXAEBVUnmarshalContext@2@AEBUClassData@2@V?$ArrayView@PEBUBaseTypeData@Details@Marshal@@@12@V?$ArrayView@PEBUXmlTypeData@Details@Marshal@@@12@@Z`
- size: `1323`
- prototype: `__int64 __usercall@<rax>(Marshal::Details *this@<rcx>, __int64, __int64, __int64)`
- caller_count: `30`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x1800130d8`
- `0x180013854`
- `0x1800138bc`
- `0x180013924`
- `0x18001398c`
- `0x1800139f4`
- `0x180013a5c`
- `0x180013ac4`
- `0x180013b2c`
- `0x180013b94`
- `0x180013bfc`
- `0x180013c64`
- `0x180013ccc`
- `0x180013d34`
- `0x180013d9c`
- `0x180013e04`
- `0x180013e6c`
- `0x180014ac0`
- `0x180014ba0`
- `0x180014cc0`
- `0x180014e20`
- `0x180014e90`
- `0x180014f00`
- `0x180015020`
- `0x180015110`
- `0x180015200`
- `0x1800152f0`
- `0x1800153e0`
- `0x1800154c0`
- `0x180015740`

## callees

- `0x180002af4`
- `0x180003608`
- `0x18000362c`
- `0x18000bdc8`
- `0x18000be08`
- `0x18001e5ac`
- `0x18001e748`
- `0x18001f75c`
- `0x18001ff3c`
- `0x180020470`
- `0x1800208b8`
- `0x1800215cc`
- `0x180034010`

## string_xrefs

- `0x1800203fe`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180020416`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x18002042b`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180020440`: `onecore\internal\vm\inc\MarshalXml.h`
- `0x180020455`: `onecore\internal\vm\inc\MarshalXml.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall Marshal::Details::ReadObjectXml(
        Marshal::Details *this,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        _QWORD *a6,
        __int64 *a7)
{
  Marshal::XmlReader *v7; // r12
  __int64 v8; // r13
  __int64 v9; // r15
  unsigned int v10; // r14d
  unsigned __int64 v11; // rsi
  unsigned __int64 v12; // rbx
  _QWORD *v13; // rdi
  void *v14; // rax
  char *v15; // r14
  unsigned __int64 v16; // r13
  unsigned int *v17; // r8
  int v18; // r15d
  unsigned int v19; // r15d
  char v20; // si
  __int64 *v21; // rbx
  __int64 v22; // rdi
  __int64 v23; // r13
  __int64 v24; // r12
  void (__fastcall *v25)(__int64, __int64, unsigned int *, __int64); // rax
  char v26; // al
  int v27; // eax
  char v28; // si
  int v29; // ebx
  __int64 v30; // r14
  int v31; // eax
  int v32; // eax
  __int64 v33; // rbx
  unsigned int v34; // r14d
  __int64 *v35; // rbx
  __int64 v36; // rdi
  _QWORD *v37; // r15
  int v38; // eax
  __int64 v39; // rdx
  __int64 v40; // rcx
  int v41; // eax
  int v43; // [rsp+28h] [rbp-71h]
  __int128 Buf1; // [rsp+38h] [rbp-61h] BYREF
  __int128 v45; // [rsp+48h] [rbp-51h] BYREF
  char *v46; // [rsp+58h] [rbp-41h]
  __int64 v47; // [rsp+60h] [rbp-39h]
  _QWORD v48[14]; // [rsp+68h] [rbp-31h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E0h] [rbp+47h]
  int Buf2; // [rsp+F0h] [rbp+57h] BYREF
  __int64 v52; // [rsp+F8h] [rbp+5Fh]
  __int64 v53; // [rsp+100h] [rbp+67h]

  v53 = a4;
  v52 = a3;
  Buf2 = a2;
  v7 = this;
  v8 = a5;
  v9 = *(unsigned int *)(a5 + 16);
  v10 = 0;
  LODWORD(Buf1) = 0;
  v11 = (unsigned __int64)(v9 + 31) >> 5;
  v45 = 0;
  v46 = 0;
  v12 = 4 * v11;
  if ( v11 )
  {
    if ( v12 )
    {
      if ( v12 < 0x1000 )
      {
        v13 = operator new(4 * v11);
      }
      else
      {
        if ( v12 + 39 < v12 )
          __scrt_throw_std_bad_array_new_length();
        v14 = operator new(v12 + 39);
        if ( !v14 )
          __fastfail(5u);
        v13 = (_QWORD *)(((unsigned __int64)v14 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v13 - 1) = v14;
      }
    }
    else
    {
      v13 = 0;
    }
    *(_QWORD *)&v45 = v13;
    v15 = (char *)v13 + v12;
    v46 = (char *)v13 + v12;
    Buf2 = 0;
    if ( !memcmp_0(&Buf1, &Buf2, 4u) )
    {
      memset_0(v13, 0, 4 * v11);
    }
    else
    {
      v16 = (unsigned __int64)(v9 + 31) >> 5;
      v15 = (char *)v13;
      memset_0(v13, 0, 4 * v11);
      do
      {
        v15 += 4;
        --v16;
      }
      while ( v16 );
      v8 = a5;
    }
    *((_QWORD *)&v45 + 1) = v15;
    v10 = 0;
    *(_QWORD *)&Buf1 = 0;
    std::_Tidy_guard<std::vector<unsigned int>>::~_Tidy_guard<std::vector<unsigned int>>(&Buf1);
  }
  v17 = (unsigned int *)(v8 + 16);
  v47 = 0;
  if ( v11 < (__int64)(*((_QWORD *)&v45 + 1) - v45) >> 2 && v12 + (_QWORD)v45 != *((_QWORD *)&v45 + 1) )
    *((_QWORD *)&v45 + 1) = v12 + v45;
  v47 = v9;
  v18 = v9 & 0x1F;
  if ( v18 )
  {
    a2 = (unsigned int)((1 << v18) - 1);
    *(_DWORD *)(v12 + v45 - 4) &= a2;
  }
  v19 = -1;
  v20 = 0;
  v21 = *(__int64 **)v8;
  v22 = *(_QWORD *)v8 + 32LL * *v17;
  if ( *(_QWORD *)v8 != v22 )
  {
    v23 = *a7;
    v24 = v52;
    do
    {
      v25 = *(void (__fastcall **)(__int64, __int64, unsigned int *, __int64))(*(_QWORD *)(v23 + 8LL * v10) + 16LL);
      if ( v25 )
        v25(v24 + *((unsigned int *)v21 + 2), a2, v17, 1);
      if ( (*((_BYTE *)v21 + 12) & 8) != 0 )
      {
        v19 = v10;
      }
      else if ( (*((_BYTE *)v21 + 12) & 4) == 0 )
      {
        v20 = 1;
      }
      ++v10;
      v21 += 4;
    }
    while ( v21 != (__int64 *)v22 );
    v7 = this;
    v8 = a5;
  }
  if ( v19 >= *(_DWORD *)(v8 + 16) || (v26 = 0, !v20) )
    v26 = 1;
  if ( !v26 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x690,
      (unsigned int)"onecore\\internal\\vm\\inc\\MarshalXml.h",
      (const char *)1);
  v27 = (*(__int64 (__fastcall **)(_QWORD, __int64, unsigned int *, __int64))(**(_QWORD **)v7 + 64LL))(
          *(_QWORD *)v7,
          a2,
          v17,
          1);
  if ( v27 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x693,
      (unsigned int)"onecore\\internal\\vm\\inc\\MarshalXml.h",
      (const char *)(unsigned int)v27,
      v43);
  v28 = 1;
  v29 = 0;
  v30 = v53;
  if ( !v27 )
  {
    do
    {
      if ( v29 != -1 )
      {
        Marshal::XmlReader::CaptureNodeName(v7, 1);
        Buf1 = *(_OWORD *)a7;
        v28 = (unsigned __int8)Marshal::Details::ReadXmlElement(v7, v8, (__int64)&Buf1) != 0 ? v28 : 0;
      }
      v31 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v7 + 72LL))(*(_QWORD *)v7);
      if ( v31 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x69F,
          (unsigned int)"onecore\\internal\\vm\\inc\\MarshalXml.h",
          (const char *)(unsigned int)v31,
          v43);
      ++v29;
    }
    while ( !v31 );
  }
  v32 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)v7 + 88LL))(*(_QWORD *)v7);
  if ( v32 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x6A2,
      (unsigned int)"onecore\\internal\\vm\\inc\\MarshalXml.h",
      (const char *)(unsigned int)v32,
      v43);
  if ( v19 >= *(_DWORD *)(v8 + 16) )
  {
    if ( !(*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)v7 + 160LL))(*(_QWORD *)v7) )
    {
      while ( 1 )
      {
        Buf2 = 0;
        v41 = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)v7 + 48LL))(*(_QWORD *)v7, &Buf2);
        if ( v41 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x6B3,
            (unsigned int)"onecore\\internal\\vm\\inc\\MarshalXml.h",
            (const char *)(unsigned int)v41,
            v43);
        if ( !Buf2 )
          break;
        if ( Buf2 == 1 )
        {
          Marshal::XmlReader::CaptureNodeName(v7, 0);
          Buf1 = *(_OWORD *)a7;
          if ( !(unsigned __int8)Marshal::Details::ReadXmlElement(v7, v8, (__int64)&Buf1) )
            v28 = 0;
        }
        else if ( Buf2 != 8 && Buf2 != 13 )
        {
          if ( Buf2 == 15 )
            break;
          if ( Buf2 != 17 )
          {
            Marshal::UnmarshalContext::ReportError(v30, 15);
            std::vector<unsigned int>::~vector<unsigned int>(&v45);
            return 0;
          }
        }
      }
    }
  }
  else
  {
    _mm_lfence();
    *(_DWORD *)(v45 + 4 * ((unsigned __int64)v19 >> 5)) |= 1 << (v19 & 0x1F);
    v33 = v52 + *(unsigned int *)(32LL * v19 + *(_QWORD *)v8 + 8);
    Marshal::XmlReader::CaptureNodeName(v7, 0);
    if ( !(*(unsigned __int8 (__fastcall **)(Marshal::XmlReader *, __int64, __int64))(*(_QWORD *)(*a7 + 8LL * v19) + 8LL))(
            v7,
            v33,
            v30) )
      v28 = 0;
  }
  v34 = 0;
  v35 = *(__int64 **)v8;
  v36 = *(_QWORD *)v8 + 32LL * *(unsigned int *)(v8 + 16);
  if ( *(_QWORD *)v8 != v36 )
  {
    v37 = a6;
    do
    {
      v38 = *(_DWORD *)(v45 + 4 * ((unsigned __int64)v34 >> 5));
      if ( !_bittest(&v38, v34 & 0x1F) )
      {
        if ( (*((_BYTE *)v35 + 12) & 2) != 0 )
        {
          v39 = *v35;
          v40 = -1;
          v28 = 0;
          do
            ++v40;
          while ( *(_WORD *)(v39 + 2 * v40) );
          v48[1] = *(_QWORD *)(v53 + 8);
          v48[2] = v53;
          v48[0] = &Marshal::Details::UnmarshalFieldContext::`vftable';
          v48[3] = v39;
          v48[4] = v40;
          Marshal::UnmarshalContext::ReportError(v48, 11);
        }
        else
        {
          (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)(*v37 + 8LL * v34) + 8LL))(
            v52 + *((unsigned int *)v35 + 2),
            v35[2]);
        }
      }
      ++v34;
      v35 += 4;
    }
    while ( v35 != (__int64 *)v36 );
  }
  std::vector<unsigned int>::~vector<unsigned int>(&v45);
  return v28;
}

```

## disassembly

```asm
0x18001ff3c  mov     rax, rsp
0x18001ff3f  mov     [rax+20h], r9
0x18001ff43  mov     [rax+18h], r8
0x18001ff47  mov     [rax+10h], edx
0x18001ff4a  mov     [rax+8], rcx
0x18001ff4e  push    rbp
0x18001ff4f  push    rbx
0x18001ff50  push    rsi
0x18001ff51  push    rdi
0x18001ff52  push    r12
0x18001ff54  push    r13
0x18001ff56  push    r14
0x18001ff58  push    r15
0x18001ff5a  lea     rbp, [rax-47h]
0x18001ff5e  sub     rsp, 98h
0x18001ff65  mov     r12, rcx
0x18001ff68  mov     r13, [rbp+3Fh+arg_20]
0x18001ff6c  mov     r15d, [r13+10h]
0x18001ff70  xor     r14d, r14d
0x18001ff73  mov     dword ptr [rbp+3Fh+Buf1], r14d
0x18001ff77  lea     rsi, [r15+1Fh]
0x18001ff7b  shr     rsi, 5
0x18001ff7f  xorps   xmm0, xmm0
0x18001ff82  movdqu  [rbp+3Fh+var_90], xmm0
0x18001ff87  mov     [rbp+3Fh+var_80], r14
0x18001ff8b  lea     r9d, [r14+1]
0x18001ff8f  lea     rbx, ds:0[rsi*4]
0x18001ff97  test    rsi, rsi
0x18001ff9a  jz      loc_180020056
0x18001ffa0  test    rbx, rbx
0x18001ffa3  jnz     short loc_18001FFAA
0x18001ffa5  mov     edi, r14d
0x18001ffa8  jmp     short loc_18001FFE8
0x18001ffaa  cmp     rbx, 1000h
0x18001ffb1  jb      short loc_18001FFDD
0x18001ffb3  lea     rcx, [rbx+27h]; Size
0x18001ffb7  cmp     rcx, rbx
0x18001ffba  jbe     loc_180020410
0x18001ffc0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ffc5  test    rax, rax
0x18001ffc8  jnz     short loc_18001FFCF
0x18001ffca  lea     ecx, [rax+5]
0x18001ffcd  int     29h; Win8: RtlFailFast(ecx)
0x18001ffcf  lea     rdi, [rax+27h]
0x18001ffd3  and     rdi, 0FFFFFFFFFFFFFFE0h
0x18001ffd7  mov     [rdi-8], rax
0x18001ffdb  jmp     short loc_18001FFE8
0x18001ffdd  mov     rcx, rbx; Size
0x18001ffe0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ffe5  mov     rdi, rax
0x18001ffe8  mov     qword ptr [rbp+3Fh+var_90], rdi
0x18001ffec  lea     r14, [rdi+rbx]
0x18001fff0  mov     [rbp+3Fh+var_80], r14
0x18001fff4  mov     [rbp+3Fh+Buf2], 0
0x18001fffb  mov     r8d, 4; Size
0x180020001  lea     rdx, [rbp+3Fh+Buf2]; Buf2
0x180020005  lea     rcx, [rbp+3Fh+Buf1]; Buf1
0x180020009  call    memcmp_0
0x18002000e  mov     r8, rbx; Size
0x180020011  xor     edx, edx; Val
0x180020013  mov     rcx, rdi; void *
0x180020016  test    eax, eax
0x180020018  jnz     short loc_180020021
0x18002001a  call    memset_0
0x18002001f  jmp     short loc_18002003E
0x180020021  mov     r13, rsi
0x180020024  mov     r14, rdi
0x180020027  and     r8, 0FFFFFFFFFFFFFFFCh; Size
0x18002002b  call    memset_0
0x180020030  add     r14, 4
0x180020034  sub     r13, 1
0x180020038  jnz     short loc_180020030
0x18002003a  mov     r13, [rbp+3Fh+arg_20]
0x18002003e  mov     qword ptr [rbp+3Fh+var_90+8], r14
0x180020042  xor     r14d, r14d
0x180020045  mov     qword ptr [rbp+3Fh+Buf1], r14
0x180020049  lea     rcx, [rbp+3Fh+Buf1]
0x18002004d  call    ??1?$_Tidy_guard@V?$vector@IV?$allocator@I@std@@@std@@@std@@QEAA@XZ; std::_Tidy_guard<std::vector<uint>>::~_Tidy_guard<std::vector<uint>>(void)
0x180020052  lea     r9d, [r14+1]
0x180020056  lea     r8, [r13+10h]
0x18002005a  mov     [rbp+3Fh+var_78], r14
0x18002005e  mov     rcx, qword ptr [rbp+3Fh+var_90+8]
0x180020062  mov     rax, qword ptr [rbp+3Fh+var_90]
0x180020066  sub     rcx, rax
0x180020069  sar     rcx, 2
0x18002006d  cmp     rsi, rcx
0x180020070  jnb     short loc_180020080
0x180020072  lea     rcx, [rbx+rax]
0x180020076  cmp     rcx, qword ptr [rbp+3Fh+var_90+8]
0x18002007a  jz      short loc_180020080
0x18002007c  mov     qword ptr [rbp+3Fh+var_90+8], rcx
0x180020080  mov     [rbp+3Fh+var_78], r15
0x180020084  and     r15d, 1Fh
0x180020088  jbe     short loc_180020099
0x18002008a  mov     ecx, r15d
0x18002008d  mov     edx, r9d
0x180020090  shl     edx, cl
0x180020092  sub     edx, r9d
0x180020095  and     [rbx+rax-4], edx
0x180020099  or      r15d, 0FFFFFFFFh
0x18002009d  mov     sil, r14b
0x1800200a0  mov     rbx, [r13+0]
0x1800200a4  mov     edi, [r8]
0x1800200a7  shl     rdi, 5
0x1800200ab  add     rdi, rbx
0x1800200ae  cmp     rbx, rdi
0x1800200b1  jz      short loc_18002010E
0x1800200b3  mov     rax, [rbp+3Fh+arg_30]
0x1800200b7  mov     r13, [rax]
0x1800200ba  mov     r12, [rbp+3Fh+arg_10]
0x1800200be  mov     eax, r14d
0x1800200c1  mov     rcx, [r13+rax*8+0]
0x1800200c6  mov     rax, [rcx+10h]
0x1800200ca  test    rax, rax
0x1800200cd  jz      short loc_1800200DA
0x1800200cf  mov     ecx, [rbx+8]
0x1800200d2  add     rcx, r12
0x1800200d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800200da  mov     r9d, 1; char *
0x1800200e0  test    byte ptr [rbx+0Ch], 8
0x1800200e4  jz      short loc_1800200EB
0x1800200e6  mov     r15d, r14d
0x1800200e9  jmp     short loc_1800200F7
0x1800200eb  test    byte ptr [rbx+0Ch], 4
0x1800200ef  movzx   esi, sil
0x1800200f3  cmovz   esi, r9d
0x1800200f7  add     r14d, r9d
0x1800200fa  add     rbx, 20h ; ' '
0x1800200fe  cmp     rbx, rdi
0x180020101  jnz     short loc_1800200BE
0x180020103  mov     r12, [rbp+3Fh+arg_0]
0x180020107  mov     r13, [rbp+3Fh+arg_20]
0x18002010b  xor     r14d, r14d
0x18002010e  cmp     r15d, [r13+10h]
0x180020112  jnb     short loc_18002011C
0x180020114  test    sil, sil
0x180020117  mov     al, r14b
0x18002011a  jnz     short loc_18002011F
0x18002011c  mov     al, r9b
0x18002011f  mov     rcx, [rbp+47h]; this
0x180020123  test    al, al
0x180020125  jz      loc_180020416
0x18002012b  mov     rcx, [r12]
0x18002012f  mov     rax, [rcx]
0x180020132  mov     rax, [rax+40h]
0x180020136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002013b  mov     rcx, [rbp+47h]; this
0x18002013f  test    eax, eax
0x180020141  js      loc_180020428
0x180020147  mov     ecx, 1
0x18002014c  mov     sil, cl
0x18002014f  mov     ebx, r14d
0x180020152  mov     r14, [rbp+3Fh+arg_18]
0x180020156  test    eax, eax
0x180020158  jnz     short loc_1800201C7
0x18002015a  mov     rdi, [rbp+3Fh+arg_10]
0x18002015e  cmp     ebx, 0FFFFFFFFh
0x180020161  jz      short loc_1800201A0
0x180020163  mov     dl, cl; bool
0x180020165  mov     rcx, r12; this
0x180020168  call    ?CaptureNodeName@XmlReader@Marshal@@QEAAX_N@Z; Marshal::XmlReader::CaptureNodeName(bool)
0x18002016d  mov     rax, [rbp+3Fh+arg_30]
0x180020171  movaps  xmm0, xmmword ptr [rax]
0x180020174  movdqa  [rbp+3Fh+Buf1], xmm0
0x180020179  lea     rax, [rbp+3Fh+Buf1]
0x18002017d  mov     qword ptr [rsp+0D0h+var_B0+8], rax; __int64
0x180020182  mov     qword ptr [rsp+0D0h+var_B0], r13; int
0x180020187  mov     r9, r14
0x18002018a  lea     r8, [rbp+3Fh+var_90]
0x18002018e  mov     rdx, rdi
0x180020191  mov     rcx, r12; this
0x180020194  call    ?ReadXmlElement@Details@Marshal@@YA_NAEAUXmlReader@2@PEAXAEAV?$vector@_NV?$allocator@_N@std@@@std@@AEBVUnmarshalContext@2@AEBUClassData@2@V?$ArrayView@PEBUXmlTypeData@Details@Marshal@@@12@@Z; Marshal::Details::ReadXmlElement(Marshal::XmlReader &,void *,std::vector<bool> &,Marshal::UnmarshalContext const &,Marshal::ClassData const &,Marshal::Details::ArrayView<Marshal::Details::XmlTypeData const *>)
0x180020199  neg     al
0x18002019b  sbb     cl, cl
0x18002019d  and     sil, cl
0x1800201a0  mov     rcx, [r12]
0x1800201a4  mov     rax, [rcx]
0x1800201a7  mov     rax, [rax+48h]
0x1800201ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201b0  mov     rcx, [rbp+47h]; this
0x1800201b4  test    eax, eax
0x1800201b6  js      loc_180020452
0x1800201bc  mov     ecx, 1
0x1800201c1  add     ebx, ecx
0x1800201c3  test    eax, eax
0x1800201c5  jz      short loc_18002015E
0x1800201c7  mov     rcx, [r12]
0x1800201cb  mov     rax, [rcx]
0x1800201ce  mov     rax, [rax+58h]
0x1800201d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201d7  mov     rcx, [rbp+47h]; this
0x1800201db  xor     ebx, ebx
0x1800201dd  test    eax, eax
0x1800201df  js      loc_18002043D
0x1800201e5  cmp     r15d, [r13+10h]
0x1800201e9  jnb     loc_1800202E7
0x1800201ef  lfence
0x1800201f2  mov     r8, qword ptr [rbp+3Fh+var_90]
0x1800201f6  mov     edi, r15d
0x1800201f9  mov     edx, r15d
0x1800201fc  shr     rdx, 5
0x180020200  mov     ecx, r15d
0x180020203  and     ecx, 1Fh
0x180020206  mov     eax, [r8+rdx*4]
0x18002020a  bts     eax, ecx
0x18002020d  mov     [r8+rdx*4], eax
0x180020211  mov     ecx, r15d
0x180020214  shl     rcx, 5
0x180020218  mov     rax, [r13+0]
0x18002021c  mov     ebx, [rcx+rax+8]
0x180020220  add     rbx, [rbp+3Fh+arg_10]
0x180020224  xor     edx, edx; bool
0x180020226  mov     rcx, r12; this
0x180020229  call    ?CaptureNodeName@XmlReader@Marshal@@QEAAX_N@Z; Marshal::XmlReader::CaptureNodeName(bool)
0x18002022e  mov     rcx, [rbp+3Fh+arg_30]
0x180020232  mov     rax, [rcx]
0x180020235  mov     rcx, [rax+rdi*8]
0x180020239  mov     rax, [rcx+8]
0x18002023d  mov     r8, r14
0x180020240  mov     rdx, rbx
0x180020243  mov     rcx, r12
0x180020246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002024b  xor     ebx, ebx
0x18002024d  test    al, al
0x18002024f  jnz     short loc_180020254
0x180020251  mov     sil, bl
0x180020254  mov     r14d, ebx
0x180020257  mov     rbx, [r13+0]
0x18002025b  mov     edi, [r13+10h]
0x18002025f  shl     rdi, 5
0x180020263  add     rdi, rbx
0x180020266  cmp     rbx, rdi
0x180020269  jz      loc_1800203DA
0x18002026f  mov     r15, [rbp+3Fh+arg_28]
0x180020273  mov     rdx, qword ptr [rbp+3Fh+var_90]
0x180020277  mov     r8d, r14d
0x18002027a  mov     al, r14b
0x18002027d  and     al, 1Fh
0x18002027f  movzx   ecx, al
0x180020282  mov     eax, r14d
0x180020285  shr     rax, 5
0x180020289  mov     eax, [rdx+rax*4]
0x18002028c  bt      eax, ecx
0x18002028f  jb      loc_1800203CA
0x180020295  test    byte ptr [rbx+0Ch], 2
0x180020299  jz      loc_1800203AF
0x18002029f  mov     rdx, [rbx]
0x1800202a2  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800202a6  xor     esi, esi
0x1800202a8  inc     rcx
0x1800202ab  cmp     [rdx+rcx*2], si
0x1800202af  jnz     short loc_1800202A8
0x1800202b1  mov     r8, [rbp+3Fh+arg_18]
0x1800202b5  mov     rax, [r8+8]
0x1800202b9  mov     [rbp+3Fh+var_68], rax
0x1800202bd  mov     [rbp+3Fh+var_60], r8
0x1800202c1  lea     rax, ??_7UnmarshalFieldContext@Details@Marshal@@6B@; const Marshal::Details::UnmarshalFieldContext::`vftable'
0x1800202c8  mov     [rbp+3Fh+var_70], rax
0x1800202cc  mov     [rbp+3Fh+var_58], rdx
0x1800202d0  mov     [rbp+3Fh+var_50], rcx
0x1800202d4  mov     edx, 0Bh
0x1800202d9  lea     rcx, [rbp+3Fh+var_70]
0x1800202dd  call    ?ReportError@UnmarshalContext@Marshal@@QEBAXW4UnmarshalError@2@@Z; Marshal::UnmarshalContext::ReportError(Marshal::UnmarshalError)
0x1800202e2  jmp     loc_1800203CA
0x1800202e7  mov     rcx, [r12]
0x1800202eb  mov     rax, [rcx]
0x1800202ee  mov     rax, [rax+0A0h]
0x1800202f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800202fa  test    eax, eax
0x1800202fc  jnz     loc_180020254
0x180020302  mov     [rbp+3Fh+Buf2], ebx
0x180020305  mov     rcx, [r12]
0x180020309  mov     rax, [rcx]
0x18002030c  lea     rdx, [rbp+3Fh+Buf2]
0x180020310  mov     rax, [rax+30h]
0x180020314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020319  mov     rcx, [rbp+47h]; this
0x18002031d  test    eax, eax
0x18002031f  js      loc_1800203FB
0x180020325  mov     ecx, [rbp+3Fh+Buf2]
0x180020328  test    ecx, ecx
0x18002032a  jz      loc_180020254
0x180020330  sub     ecx, 1
0x180020333  jz      short loc_180020368
0x180020335  sub     ecx, 7
0x180020338  jz      short loc_180020302
0x18002033a  sub     ecx, 5
0x18002033d  jz      short loc_180020302
0x18002033f  sub     ecx, 2
0x180020342  jz      loc_180020254
0x180020348  cmp     ecx, 2
0x18002034b  jz      short loc_180020302
0x18002034d  mov     edx, 0Fh
0x180020352  mov     rcx, r14
0x180020355  call    ?ReportError@UnmarshalContext@Marshal@@QEBAXW4UnmarshalError@2@@Z; Marshal::UnmarshalContext::ReportError(Marshal::UnmarshalError)
0x18002035a  nop
0x18002035b  lea     rcx, [rbp+3Fh+var_90]
0x18002035f  call    ??1?$vector@IV?$allocator@I@std@@@std@@QEAA@XZ; std::vector<uint>::~vector<uint>(void)
0x180020364  xor     al, al
0x180020366  jmp     short loc_1800203E6
  ... truncated ...
```
