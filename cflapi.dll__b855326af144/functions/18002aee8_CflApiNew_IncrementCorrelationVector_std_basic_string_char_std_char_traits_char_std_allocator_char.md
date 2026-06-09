# CflApiNew::IncrementCorrelationVector(std::basic_string<char,std::char_traits<char>,std::allocator<char>> *)

- ea: `0x18002aee8`
- end: `0x18002b25e`
- name: `?IncrementCorrelationVector@CflApiNew@@YAJPEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `886`
- prototype: `__int64 __fastcall(CflApiNew *this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180011030`

## callees

- `0x180002490`
- `0x180002860`
- `0x180002ef8`
- `0x1800067c4`
- `0x180008594`
- `0x180008a68`
- `0x180008ad0`
- `0x180010700`
- `0x180015794`
- `0x180028124`
- `0x18002a498`
- `0x18002aee8`
- `0x18002b7d8`
- `0x18002c11c`
- `0x18002c204`
- `0x18002cc60`
- `0x18002e008`
- `0x180030010`

## string_xrefs

- `0x18002af37`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`
- `0x18002b0cc`: `onecore\ds\security\cfl\api\lib\cflapiimplnew.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CflApiNew::IncrementCorrelationVector(CflApiNew *this)
{
  int CorrelationVectorInternal; // eax
  __int64 v3; // rdx
  unsigned int v4; // ebx
  HLOCAL v6; // rbx
  _QWORD *v7; // rax
  _QWORD *v8; // r8
  __int64 v9; // rdx
  __int64 v10; // r8
  bool v11; // dl
  const char *v12; // rcx
  struct TraceLoggingCorrelationVector *v13; // rdi
  signed __int64 v14; // r8
  unsigned __int64 v15; // r9
  unsigned __int64 v16; // rdx
  unsigned __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // r8
  void (__fastcall ***v21)(_QWORD, __int64); // rax
  size_t v22; // rsi
  CflApiNew *v23; // r15
  const char *v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // r8
  void (__fastcall ***v27)(_QWORD, __int64); // rax
  HLOCAL hMem[3]; // [rsp+20h] [rbp-E0h] BYREF
  char *Str[5]; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v30[3]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v31; // [rsp+78h] [rbp-88h]
  _BYTE v32[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v33[64]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v34[32]; // [rsp+E0h] [rbp-20h] BYREF
  char Src[144]; // [rsp+100h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  hMem[0] = 0;
  CorrelationVectorInternal = CflApiNew::GetCorrelationVectorInternal(hMem);
  v4 = CorrelationVectorInternal;
  if ( CorrelationVectorInternal >= 0 )
  {
    std::wstring_convert<std::codecvt<unsigned short,char,_Mbstatet>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::wstring_convert<std::codecvt<unsigned short,char,_Mbstatet>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>(
      v30,
      v3);
    v6 = hMem[0];
    v7 = (_QWORD *)std::wstring::wstring(v34, hMem[0]);
    if ( v7[3] <= 7u )
      v8 = v7;
    else
      v8 = (_QWORD *)*v7;
    std::wstring_convert<std::codecvt<unsigned short,char,_Mbstatet>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::to_bytes(
      v30,
      Str,
      v8,
      (char *)v8 + 2 * v7[2]);
    std::wstring::~wstring(v34, v9, v10);
    v12 = (const char *)Str;
    if ( Str[3] > (char *)0xF )
      v12 = Str[0];
    v13 = TraceLoggingCorrelationVector::Set(v12, v11);
    hMem[2] = v13;
    memset_0(Src, 0, 0x81u);
    while ( 1 )
    {
      v14 = _InterlockedExchangeAdd64((volatile signed __int64 *)v13 + 17, 0);
      if ( (unsigned int)v14 == 0x7FFFFFFF || v14 < 0 )
        break;
      v15 = HIDWORD(v14) & 0x7FFFFFFF;
      if ( (unsigned int)v14 == 9
        || (unsigned int)v14 == 99
        || (unsigned int)v14 == 999
        || (unsigned int)v14 == 9999
        || (unsigned int)v14 == 99999
        || (unsigned int)v14 == 999999
        || (unsigned int)v14 == 9999999
        || (unsigned int)v14 == 99999999
        || (unsigned int)v14 == 999999999 )
      {
        ++v15;
      }
      v16 = v15 << 32;
      if ( v15 < *((unsigned __int8 *)v13 + 130) )
        v17 = (((unsigned int)v14 + 1LL) | v16) & 0x7FFFFFFFFFFFFFFFLL;
      else
        v17 = (unsigned int)v14 | v16 | 0x8000000000000000uLL;
      if ( v14 == _InterlockedCompareExchange64((volatile signed __int64 *)v13 + 17, v17, v14) )
        goto LABEL_29;
    }
    v17 = v14;
LABEL_29:
    if ( TraceLoggingCorrelationVector::ToStringImpl(v13, v17, Src) )
    {
      v22 = -1;
      do
        ++v22;
      while ( Src[v22] );
      if ( v22 > *((_QWORD *)this + 3) )
      {
        std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(this, v22, v18, Src);
      }
      else
      {
        if ( *((_QWORD *)this + 3) <= 0xFu )
          v23 = this;
        else
          v23 = *(CflApiNew **)this;
        *((_QWORD *)this + 2) = v22;
        memmove_0(v23, Src, v22);
        *((_BYTE *)v23 + v22) = 0;
      }
      if ( *((_QWORD *)this + 3) > 0xFu )
        this = *(CflApiNew **)this;
      CflApiNew::UpdateCorrelationVectorString(this, v24);
      if ( v13 )
        operator delete(v13, 0x90u);
      std::string::~string(Str);
      v30[0] = &std::wstring_convert<std::codecvt<unsigned short,char,_Mbstatet>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::`vftable';
      std::wstring::~wstring(v33, v25, v26);
      std::string::~string(v32);
      if ( v31 )
      {
        v27 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        if ( v27 )
          (**v27)(v27, 1);
      }
      if ( v6 )
        CflFreeBuffer(v6);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C4,
        (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
        (const char *)0x8007000ELL,
        (int)hMem[0]);
      if ( v13 )
        operator delete(v13, 0x90u);
      std::string::~string(Str);
      v30[0] = &std::wstring_convert<std::codecvt<unsigned short,char,_Mbstatet>,unsigned short,std::allocator<unsigned short>,std::allocator<char>>::`vftable';
      std::wstring::~wstring(v33, v19, v20);
      std::string::~string(v32);
      if ( v31 )
      {
        v21 = (void (__fastcall ***)(_QWORD, __int64))(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
        if ( v21 )
          (**v21)(v21, 1);
      }
      if ( v6 )
        CflFreeBuffer(v6);
      return 2147942414LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BB,
      (unsigned int)"onecore\\ds\\security\\cfl\\api\\lib\\cflapiimplnew.cpp",
      (const char *)(unsigned int)CorrelationVectorInternal,
      (int)hMem[0]);
    if ( hMem[0] )
      CflFreeBuffer(hMem[0]);
    return v4;
  }
}

```

## disassembly

```asm
0x18002aee8  push    rbp
0x18002aeea  push    rbx
0x18002aeeb  push    rsi
0x18002aeec  push    rdi
0x18002aeed  push    r14
0x18002aeef  push    r15
0x18002aef1  lea     rbp, [rsp-0A8h]
0x18002aef9  sub     rsp, 1A8h
0x18002af00  mov     rax, cs:__security_cookie
0x18002af07  xor     rax, rsp
0x18002af0a  mov     [rbp+0D0h+var_40], rax
0x18002af11  mov     r14, rcx
0x18002af14  mov     [rsp+1D0h+hMem], 0; int
0x18002af1d  lea     rcx, [rsp+1D0h+hMem]
0x18002af22  call    CflApiNew__GetCorrelationVectorInternal
0x18002af27  mov     ebx, eax
0x18002af29  test    eax, eax
0x18002af2b  jns     short loc_18002AF5F
0x18002af2d  mov     rcx, [rbp+0D8h]; this
0x18002af34  mov     r9d, eax; char *
0x18002af37  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002af3e  mov     edx, 1BBh; void *
0x18002af43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002af48  nop
0x18002af49  mov     rcx, [rsp+1D0h+hMem]; hMem
0x18002af4e  test    rcx, rcx
0x18002af51  jz      short loc_18002AF58
0x18002af53  call    CflFreeBuffer
0x18002af58  mov     eax, ebx
0x18002af5a  jmp     loc_18002B23F
0x18002af5f  lea     rcx, [rsp+1D0h+var_170]
0x18002af64  call    ??0?$wstring_convert@V?$codecvt@GDU_Mbstatet@@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA@XZ; std::wstring_convert<std::codecvt<ushort,char,_Mbstatet>,ushort,std::allocator<ushort>,std::allocator<char>>::wstring_convert<std::codecvt<ushort,char,_Mbstatet>,ushort,std::allocator<ushort>,std::allocator<char>>(void)
0x18002af69  nop
0x18002af6a  mov     rbx, [rsp+1D0h+hMem]
0x18002af6f  mov     rdx, rbx
0x18002af72  lea     rcx, [rbp+0D0h+var_F0]
0x18002af76  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002af7b  nop
0x18002af7c  cmp     qword ptr [rax+18h], 7
0x18002af81  jbe     short loc_18002AF88
0x18002af83  mov     r8, [rax]
0x18002af86  jmp     short loc_18002AF8B
0x18002af88  mov     r8, rax
0x18002af8b  mov     rax, [rax+10h]
0x18002af8f  lea     r9, [r8+rax*2]
0x18002af93  lea     rdx, [rsp+1D0h+Str]
0x18002af98  lea     rcx, [rsp+1D0h+var_170]
0x18002af9d  call    ?to_bytes@?$wstring_convert@V?$codecvt@GDU_Mbstatet@@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@PEBG0@Z; std::wstring_convert<std::codecvt<ushort,char,_Mbstatet>,ushort,std::allocator<ushort>,std::allocator<char>>::to_bytes(ushort const *,ushort const *)
0x18002afa2  nop
0x18002afa3  lea     rcx, [rbp+0D0h+var_F0]
0x18002afa7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002afac  nop
0x18002afad  lea     rcx, [rsp+1D0h+Str]
0x18002afb2  cmp     [rsp+1D0h+var_180], 0Fh
0x18002afb8  cmova   rcx, [rsp+1D0h+Str]; Str
0x18002afbe  call    ?Set@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z; TraceLoggingCorrelationVector::Set(char const *,bool)
0x18002afc3  mov     rdi, rax
0x18002afc6  mov     [rsp+1D0h+var_1A0], rax
0x18002afcb  xor     edx, edx; Val
0x18002afcd  mov     r8d, 81h; Size
0x18002afd3  lea     rcx, [rbp+0D0h+Src]; void *
0x18002afd7  call    memset_0
0x18002afdc  mov     r11d, 7FFFFFFFh
0x18002afe2  xor     r8d, r8d
0x18002afe5  lock xadd [rdi+88h], r8
0x18002afee  mov     r10d, r8d
0x18002aff1  test    r8, r8
0x18002aff4  sets    al
0x18002aff7  cmp     r10, r11
0x18002affa  jz      loc_18002B0A6
0x18002b000  test    al, al
0x18002b002  jnz     loc_18002B0A6
0x18002b008  mov     r9, r8
0x18002b00b  shr     r9, 20h
0x18002b00f  and     r9, r11
0x18002b012  lea     rax, [r10+1]
0x18002b016  cmp     rax, 0Ah
0x18002b01a  jz      short loc_18002B05A
0x18002b01c  cmp     rax, 64h ; 'd'
0x18002b020  jz      short loc_18002B05A
0x18002b022  cmp     rax, 3E8h
0x18002b028  jz      short loc_18002B05A
0x18002b02a  cmp     rax, 2710h
0x18002b030  jz      short loc_18002B05A
0x18002b032  cmp     rax, 186A0h
0x18002b038  jz      short loc_18002B05A
0x18002b03a  cmp     rax, 0F4240h
0x18002b040  jz      short loc_18002B05A
0x18002b042  cmp     rax, 989680h
0x18002b048  jz      short loc_18002B05A
0x18002b04a  cmp     rax, 5F5E100h
0x18002b050  jz      short loc_18002B05A
0x18002b052  cmp     rax, 3B9ACA00h
0x18002b058  jnz     short loc_18002B05D
0x18002b05a  inc     r9
0x18002b05d  mov     rdx, r9
0x18002b060  shl     rdx, 20h
0x18002b064  movzx   ecx, byte ptr [rdi+82h]
0x18002b06b  cmp     r9, rcx
0x18002b06e  jb      short loc_18002B082
0x18002b070  or      rdx, r10
0x18002b073  mov     rax, 8000000000000000h
0x18002b07d  or      rdx, rax
0x18002b080  jmp     short loc_18002B092
0x18002b082  or      rdx, rax
0x18002b085  mov     rax, 7FFFFFFFFFFFFFFFh
0x18002b08f  and     rdx, rax
0x18002b092  mov     rax, r8
0x18002b095  lock cmpxchg [rdi+88h], rdx
0x18002b09e  jnz     loc_18002AFE2
0x18002b0a4  jmp     short loc_18002B0A9
0x18002b0a6  mov     rdx, r8; unsigned __int64
0x18002b0a9  lea     r8, [rbp+0D0h+Src]; char *
0x18002b0ad  mov     rcx, rdi; this
0x18002b0b0  call    ?ToStringImpl@TraceLoggingCorrelationVector@@AEAA_N_KPEAD@Z; TraceLoggingCorrelationVector::ToStringImpl(unsigned __int64,char *)
0x18002b0b5  test    al, al
0x18002b0b7  jnz     loc_18002B160
0x18002b0bd  mov     rcx, [rbp+0D8h]; this
0x18002b0c4  mov     esi, 8007000Eh
0x18002b0c9  mov     r9d, esi; char *
0x18002b0cc  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\cfl\\api\\lib\\c"...
0x18002b0d3  mov     edx, 1C4h; void *
0x18002b0d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b0dd  nop
0x18002b0de  test    rdi, rdi
0x18002b0e1  jz      short loc_18002B0F1
0x18002b0e3  mov     edx, 90h; unsigned __int64
0x18002b0e8  mov     rcx, rdi; void *
0x18002b0eb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002b0f0  nop
0x18002b0f1  lea     rcx, [rsp+1D0h+Str]
0x18002b0f6  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002b0fb  nop
0x18002b0fc  lea     rax, ??_7?$wstring_convert@V?$codecvt@GDU_Mbstatet@@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@6B@; const std::wstring_convert<std::codecvt<ushort,char,_Mbstatet>,ushort,std::allocator<ushort>,std::allocator<char>>::`vftable'
0x18002b103  mov     [rsp+1D0h+var_170], rax
0x18002b108  lea     rcx, [rbp+0D0h+var_130]
0x18002b10c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002b111  lea     rcx, [rbp+0D0h+var_150]
0x18002b115  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002b11a  mov     rcx, [rsp+1D0h+var_158]
0x18002b11f  test    rcx, rcx
0x18002b122  jz      short loc_18002B14C
0x18002b124  mov     rax, [rcx]
0x18002b127  mov     rax, [rax+10h]
0x18002b12b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b130  mov     r8, rax
0x18002b133  test    rax, rax
0x18002b136  jz      short loc_18002B14C
0x18002b138  mov     rcx, [rax]
0x18002b13b  mov     rax, [rcx]
0x18002b13e  mov     edx, 1
0x18002b143  mov     rcx, r8
0x18002b146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b14b  nop
0x18002b14c  test    rbx, rbx
0x18002b14f  jz      short loc_18002B159
0x18002b151  mov     rcx, rbx; hMem
0x18002b154  call    CflFreeBuffer
0x18002b159  mov     eax, esi
0x18002b15b  jmp     loc_18002B23F
0x18002b160  lea     rax, [rbp+0D0h+Src]
0x18002b164  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002b168  inc     rsi
0x18002b16b  cmp     byte ptr [rax+rsi], 0
0x18002b16f  jnz     short loc_18002B168
0x18002b171  cmp     rsi, [r14+18h]
0x18002b175  ja      short loc_18002B1A0
0x18002b177  cmp     qword ptr [r14+18h], 0Fh
0x18002b17c  jbe     short loc_18002B183
0x18002b17e  mov     r15, [r14]
0x18002b181  jmp     short loc_18002B186
0x18002b183  mov     r15, r14
0x18002b186  mov     [r14+10h], rsi
0x18002b18a  mov     r8, rsi; Size
0x18002b18d  lea     rdx, [rbp+0D0h+Src]; Src
0x18002b191  mov     rcx, r15; void *
0x18002b194  call    memmove_0
0x18002b199  mov     byte ptr [rsi+r15], 0
0x18002b19e  jmp     short loc_18002B1AF
0x18002b1a0  lea     r9, [rbp+0D0h+Src]
0x18002b1a4  mov     rdx, rsi
0x18002b1a7  mov     rcx, r14
0x18002b1aa  call    ??$_Reallocate_for@V_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAAEAV01@_KV_lambda_a132b9f505f015b07a26cb4edca31da2_@@PEBD@Z; std::string::_Reallocate_for<_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *>(unsigned __int64,_lambda_a132b9f505f015b07a26cb4edca31da2_,char const *)
0x18002b1af  cmp     qword ptr [r14+18h], 0Fh
0x18002b1b4  jbe     short loc_18002B1B9
0x18002b1b6  mov     r14, [r14]
0x18002b1b9  mov     rcx, r14; this
0x18002b1bc  call    ?UpdateCorrelationVectorString@CflApiNew@@YAJPEBD@Z; CflApiNew::UpdateCorrelationVectorString(char const *)
0x18002b1c1  nop
0x18002b1c2  test    rdi, rdi
0x18002b1c5  jz      short loc_18002B1D5
0x18002b1c7  mov     edx, 90h; unsigned __int64
0x18002b1cc  mov     rcx, rdi; void *
0x18002b1cf  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002b1d4  nop
0x18002b1d5  lea     rcx, [rsp+1D0h+Str]
0x18002b1da  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002b1df  nop
0x18002b1e0  lea     rax, ??_7?$wstring_convert@V?$codecvt@GDU_Mbstatet@@@std@@GV?$allocator@G@2@V?$allocator@D@2@@std@@6B@; const std::wstring_convert<std::codecvt<ushort,char,_Mbstatet>,ushort,std::allocator<ushort>,std::allocator<char>>::`vftable'
0x18002b1e7  mov     [rsp+1D0h+var_170], rax
0x18002b1ec  lea     rcx, [rbp+0D0h+var_130]
0x18002b1f0  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18002b1f5  lea     rcx, [rbp+0D0h+var_150]
0x18002b1f9  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18002b1fe  mov     rcx, [rsp+1D0h+var_158]
0x18002b203  test    rcx, rcx
0x18002b206  jz      short loc_18002B230
0x18002b208  mov     rax, [rcx]
0x18002b20b  mov     rax, [rax+10h]
0x18002b20f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b214  mov     r8, rax
0x18002b217  test    rax, rax
0x18002b21a  jz      short loc_18002B230
0x18002b21c  mov     rcx, [rax]
0x18002b21f  mov     rax, [rcx]
0x18002b222  mov     edx, 1
0x18002b227  mov     rcx, r8
0x18002b22a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b22f  nop
0x18002b230  test    rbx, rbx
0x18002b233  jz      short loc_18002B23D
0x18002b235  mov     rcx, rbx; hMem
0x18002b238  call    CflFreeBuffer
0x18002b23d  xor     eax, eax
0x18002b23f  mov     rcx, [rbp+0D0h+var_40]
0x18002b246  xor     rcx, rsp; StackCookie
0x18002b249  call    __security_check_cookie
0x18002b24e  add     rsp, 1A8h
0x18002b255  pop     r15
0x18002b257  pop     r14
0x18002b259  pop     rdi
0x18002b25a  pop     rsi
0x18002b25b  pop     rbx
0x18002b25c  pop     rbp
0x18002b25d  retn
```
