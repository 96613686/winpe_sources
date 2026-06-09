# CPropertyTag::ReadProperty(void)

- ea: `0x18000eac8`
- end: `0x18000ed72`
- name: `?ReadProperty@CPropertyTag@@IEAAJXZ`
- size: `682`
- prototype: `__int64 __fastcall(CPropertyTag *__hidden this)`
- caller_count: `4`
- callee_count: `9`
- tags: ``

## callers

- `0x18000e9f0`
- `0x18000fb70`
- `0x18000ff50`
- `0x180010010`

## callees

- `0x180008210`
- `0x180009fa0`
- `0x18000aef4`
- `0x18000eac8`
- `0x18000f614`
- `0x18000fab0`
- `0x180010dfc`
- `0x180014130`
- `0x180023388`

## string_xrefs

- `0x18000ed1a`: `[HTML] CPropertyTag::ReadProperty, unknown value of _eState: %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPropertyTag::ReadProperty(CPropertyTag *this)
{
  const wchar_t *v2; // r9
  __int64 v3; // r14
  int v4; // ebx
  int v5; // ecx
  int v6; // edx
  __int64 v7; // rbx
  __int64 v8; // rbx
  __int64 result; // rax
  __int64 v10; // rbx
  _OWORD *v11; // rdx
  wchar_t *v12; // rax
  __int64 v13; // rcx
  unsigned int v14[4]; // [rsp+30h] [rbp-D0h] BYREF
  int v15; // [rsp+40h] [rbp-C0h] BYREF
  int v16; // [rsp+44h] [rbp-BCh]
  __int64 v17; // [rsp+48h] [rbp-B8h]
  _QWORD v18[3]; // [rsp+50h] [rbp-B0h] BYREF
  __int16 v19; // [rsp+68h] [rbp-98h] BYREF
  wchar_t Src[256]; // [rsp+B0h] [rbp-50h] BYREF

  v2 = (const wchar_t *)*((unsigned int *)this + 62);
  if ( (_DWORD)v2 )
  {
    if ( (_DWORD)v2 == 1 )
    {
      return 2147751682LL;
    }
    else
    {
      SearchIndexerDebug::Error(
        (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\filters\\html\\nlhtml\\proptag.cxx",
        (const wchar_t *)0x118,
        (unsigned int)L"[HTML] CPropertyTag::ReadProperty, unknown value of _eState: %d\n",
        v2);
      return 2147500037LL;
    }
  }
  else
  {
    v3 = 0;
    while ( !*((_DWORD *)this + 62) )
    {
      v14[0] = 0;
      v4 = 256 - v3;
      v15 = 1;
      v16 = 1;
      v17 = 0;
      v18[1] = &v19;
      v18[2] = 33;
      v19 = 0;
      v18[0] = &TLMString<32,32,1024>::`vftable';
      CHtmlScanner::GetBlockOfChars(
        *((CHtmlScanner **)this + 3),
        256 - v3,
        &Src[v3],
        (const wchar_t *)v14,
        (struct CToken *)&v15);
      v3 = v14[0] + (unsigned int)v3;
      if ( v14[0] == v4 )
      {
        if ( v14[0] )
        {
          v10 = *((unsigned int *)this + 196);
          XGrowable<wchar_t,256>::SetSize((unsigned int *)this + 64, v10 + 256);
          v11 = (_OWORD *)(*((_QWORD *)this + 33) + 2 * v10);
          v12 = Src;
          v13 = 4;
          do
          {
            *v11 = *(_OWORD *)v12;
            v11[1] = *((_OWORD *)v12 + 1);
            v11[2] = *((_OWORD *)v12 + 2);
            v11[3] = *((_OWORD *)v12 + 3);
            v11[4] = *((_OWORD *)v12 + 4);
            v11[5] = *((_OWORD *)v12 + 5);
            v11[6] = *((_OWORD *)v12 + 6);
            v11[7] = *((_OWORD *)v12 + 7);
            v11 += 8;
            v12 += 64;
            --v13;
          }
          while ( v13 );
          *((_DWORD *)this + 196) += 256;
          v3 = 0;
        }
      }
      else
      {
        v5 = v15;
        if ( v15 == 2 )
          goto LABEL_12;
        v6 = v16;
        if ( v15 == *((_DWORD *)this + 34) && !v16 )
          goto LABEL_12;
        if ( (unsigned int)(v15 - 11) <= 6 || v15 == 19 )
        {
          *((_DWORD *)this + 197) = 1;
          *((_DWORD *)this + 198) = v5;
          *((_DWORD *)this + 199) = v6;
          *((_QWORD *)this + 100) = v17;
          TLMString<32,32,1024>::operator=((char *)this + 808, v18);
LABEL_12:
          *((_DWORD *)this + 62) = 1;
          TLMString<32,32,1024>::~TLMString<32,32,1024>(v18);
          break;
        }
        CHtmlScanner::ReadTag(*((CHtmlScanner **)this + 3), 0);
      }
      TLMString<32,32,1024>::~TLMString<32,32,1024>(v18);
    }
    *((_DWORD *)this + 62) = 1;
    if ( (_DWORD)v3 )
    {
      v7 = *((unsigned int *)this + 196);
      XGrowable<wchar_t,256>::SetSize((unsigned int *)this + 64, v7 + v3);
      memcpy_0((void *)(*((_QWORD *)this + 33) + 2 * v7), Src, 2LL * (unsigned int)v3);
      *((_DWORD *)this + 196) += v3;
    }
    v8 = *((unsigned int *)this + 196);
    XGrowable<wchar_t,256>::SetSize((unsigned int *)this + 64, v8 + 1);
    result = 0;
    *(_WORD *)(*((_QWORD *)this + 33) + 2 * v8) = 0;
    ++*((_DWORD *)this + 196);
  }
  return result;
}

```

## disassembly

```asm
0x18000eac8  push    rbp
0x18000eaca  push    rbx
0x18000eacb  push    rsi
0x18000eacc  push    rdi
0x18000eacd  push    r12
0x18000eacf  push    r14
0x18000ead1  lea     rbp, [rsp-1C8h]
0x18000ead9  sub     rsp, 2C8h
0x18000eae0  mov     rax, cs:__security_cookie
0x18000eae7  xor     rax, rsp
0x18000eaea  mov     [rbp+1F0h+var_40], rax
0x18000eaf1  mov     rsi, rcx
0x18000eaf4  mov     r9d, [rcx+0F8h]; wchar_t *
0x18000eafb  test    r9d, r9d
0x18000eafe  jnz     loc_18000ED0A
0x18000eb04  xor     r14d, r14d
0x18000eb07  lea     r12d, [r9+1]
0x18000eb0b  cmp     dword ptr [rsi+0F8h], 0
0x18000eb12  jnz     loc_18000EBEC
0x18000eb18  mov     [rsp+2F0h+var_2C0], 0
0x18000eb20  mov     ebx, 100h
0x18000eb25  sub     ebx, r14d
0x18000eb28  mov     [rsp+2F0h+var_2B0], r12d
0x18000eb2d  mov     [rsp+2F0h+var_2AC], r12d
0x18000eb32  mov     [rsp+2F0h+var_2A8], 0
0x18000eb3b  lea     rax, [rsp+2F0h+var_288]
0x18000eb40  mov     [rsp+2F0h+var_298], rax
0x18000eb45  mov     [rsp+2F0h+var_290], 21h ; '!'
0x18000eb4e  xor     eax, eax
0x18000eb50  mov     [rsp+2F0h+var_288], ax
0x18000eb55  lea     rax, ??_7?$TLMString@$0CA@$0CA@$0EAA@@@6B@; const TLMString<32,32,1024>::`vftable'
0x18000eb5c  mov     [rsp+2F0h+var_2A0], rax
0x18000eb61  lea     r8, [rbp+1F0h+Src]
0x18000eb65  lea     r8, [r8+r14*2]; wchar_t *
0x18000eb69  lea     rax, [rsp+2F0h+var_2B0]
0x18000eb6e  mov     [rsp+2F0h+var_2D0], rax; struct CToken *
0x18000eb73  lea     r9, [rsp+2F0h+var_2C0]; unsigned int *
0x18000eb78  mov     edx, ebx; unsigned int
0x18000eb7a  mov     rcx, [rsi+18h]; this
0x18000eb7e  call    ?GetBlockOfChars@CHtmlScanner@@QEAAXKPEA_WAEAKAEAVCToken@@@Z; CHtmlScanner::GetBlockOfChars(ulong,wchar_t *,ulong &,CToken &)
0x18000eb83  mov     eax, [rsp+2F0h+var_2C0]
0x18000eb87  add     r14d, eax
0x18000eb8a  cmp     eax, ebx
0x18000eb8c  jz      loc_18000EC77
0x18000eb92  mov     ecx, [rsp+2F0h+var_2B0]
0x18000eb96  cmp     ecx, 2
0x18000eb99  jz      short loc_18000EBDB
0x18000eb9b  mov     edx, [rsp+2F0h+var_2AC]
0x18000eb9f  cmp     ecx, [rsi+88h]
0x18000eba5  jz      short loc_18000EBD7
0x18000eba7  lea     eax, [rcx-0Bh]
0x18000ebaa  cmp     eax, 6
0x18000ebad  jbe     loc_18000ED3C
0x18000ebb3  cmp     ecx, 13h
0x18000ebb6  jz      loc_18000ED3C
0x18000ebbc  xor     edx, edx; int
0x18000ebbe  mov     rcx, [rsi+18h]; this
0x18000ebc2  call    ?ReadTag@CHtmlScanner@@AEAAXH@Z; CHtmlScanner::ReadTag(int)
0x18000ebc7  nop
0x18000ebc8  lea     rcx, [rsp+2F0h+var_2A0]
0x18000ebcd  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x18000ebd2  jmp     loc_18000EB0B
0x18000ebd7  test    edx, edx
0x18000ebd9  jnz     short loc_18000EBA7
0x18000ebdb  mov     [rsi+0F8h], r12d
0x18000ebe2  lea     rcx, [rsp+2F0h+var_2A0]
0x18000ebe7  call    ??1?$TLMString@$0CA@$0CA@$0EAA@@@UEAA@XZ; TLMString<32,32,1024>::~TLMString<32,32,1024>(void)
0x18000ebec  mov     [rsi+0F8h], r12d
0x18000ebf3  test    r14d, r14d
0x18000ebf6  jz      short loc_18000EC2F
0x18000ebf8  lea     rdi, [rsi+100h]
0x18000ebff  mov     ebx, [rsi+310h]
0x18000ec05  lea     edx, [rbx+r14]
0x18000ec09  mov     rcx, rdi
0x18000ec0c  call    ?SetSize@?$XGrowable@_W$0BAA@@@QEAAPEA_WI@Z; XGrowable<wchar_t,256>::SetSize(uint)
0x18000ec11  mov     r8d, r14d
0x18000ec14  add     r8, r8; Size
0x18000ec17  mov     rax, [rdi+8]
0x18000ec1b  lea     rcx, [rax+rbx*2]; void *
0x18000ec1f  lea     rdx, [rbp+1F0h+Src]; Src
0x18000ec23  call    memcpy_0
0x18000ec28  add     [rsi+310h], r14d
0x18000ec2f  lea     rdi, [rsi+100h]
0x18000ec36  mov     ebx, [rsi+310h]
0x18000ec3c  lea     edx, [rbx+1]
0x18000ec3f  mov     rcx, rdi
0x18000ec42  call    ?SetSize@?$XGrowable@_W$0BAA@@@QEAAPEA_WI@Z; XGrowable<wchar_t,256>::SetSize(uint)
0x18000ec47  mov     rcx, [rdi+8]
0x18000ec4b  xor     eax, eax
0x18000ec4d  mov     [rcx+rbx*2], ax
0x18000ec51  add     [rsi+310h], r12d
0x18000ec58  mov     rcx, [rbp+1F0h+var_40]
0x18000ec5f  xor     rcx, rsp; StackCookie
0x18000ec62  call    __security_check_cookie
0x18000ec67  add     rsp, 2C8h
0x18000ec6e  pop     r14
0x18000ec70  pop     r12
0x18000ec72  pop     rdi
0x18000ec73  pop     rsi
0x18000ec74  pop     rbx
0x18000ec75  pop     rbp
0x18000ec76  retn
0x18000ec77  test    eax, eax
0x18000ec79  jz      loc_18000EBC8
0x18000ec7f  lea     rdi, [rsi+100h]
0x18000ec86  mov     ebx, [rsi+310h]
0x18000ec8c  lea     edx, [rbx+100h]
0x18000ec92  mov     rcx, rdi
0x18000ec95  call    ?SetSize@?$XGrowable@_W$0BAA@@@QEAAPEA_WI@Z; XGrowable<wchar_t,256>::SetSize(uint)
0x18000ec9a  mov     rax, [rdi+8]
0x18000ec9e  lea     rdx, [rax+rbx*2]
0x18000eca2  lea     rax, [rbp+1F0h+Src]
0x18000eca6  mov     ecx, 4
0x18000ecab  lea     ebx, [rcx+7Ch]
0x18000ecae  movups  xmm0, xmmword ptr [rax]
0x18000ecb1  movups  xmmword ptr [rdx], xmm0
0x18000ecb4  movups  xmm1, xmmword ptr [rax+10h]
0x18000ecb8  movups  xmmword ptr [rdx+10h], xmm1
0x18000ecbc  movups  xmm0, xmmword ptr [rax+20h]
0x18000ecc0  movups  xmmword ptr [rdx+20h], xmm0
0x18000ecc4  movups  xmm1, xmmword ptr [rax+30h]
0x18000ecc8  movups  xmmword ptr [rdx+30h], xmm1
0x18000eccc  movups  xmm0, xmmword ptr [rax+40h]
0x18000ecd0  movups  xmmword ptr [rdx+40h], xmm0
0x18000ecd4  movups  xmm1, xmmword ptr [rax+50h]
0x18000ecd8  movups  xmmword ptr [rdx+50h], xmm1
0x18000ecdc  movups  xmm0, xmmword ptr [rax+60h]
0x18000ece0  movups  xmmword ptr [rdx+60h], xmm0
0x18000ece4  movups  xmm1, xmmword ptr [rax+70h]
0x18000ece8  movups  xmmword ptr [rdx+70h], xmm1
0x18000ecec  add     rdx, rbx
0x18000ecef  add     rax, rbx
0x18000ecf2  sub     rcx, 1
0x18000ecf6  jnz     short loc_18000ECAE
0x18000ecf8  add     dword ptr [rsi+310h], 100h
0x18000ed02  xor     r14d, r14d
0x18000ed05  jmp     loc_18000EBC8
0x18000ed0a  cmp     r9d, 1
0x18000ed0e  jnz     short loc_18000ED1A
0x18000ed10  mov     eax, 80041702h
0x18000ed15  jmp     loc_18000EC58
0x18000ed1a  lea     r8, aHtmlCpropertyt; "[HTML] CPropertyTag::ReadProperty, unkn"...
0x18000ed21  mov     edx, 118h; wchar_t *
0x18000ed26  lea     rcx, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\search\\fil"...
0x18000ed2d  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x18000ed32  mov     eax, 80004005h
0x18000ed37  jmp     loc_18000EC58
0x18000ed3c  mov     [rsi+314h], r12d
0x18000ed43  mov     [rsi+318h], ecx
0x18000ed49  mov     [rsi+31Ch], edx
0x18000ed4f  mov     rax, [rsp+2F0h+var_2A8]
0x18000ed54  mov     [rsi+320h], rax
0x18000ed5b  lea     rcx, [rsi+328h]
0x18000ed62  lea     rdx, [rsp+2F0h+var_2A0]
0x18000ed67  call    ??4?$TLMString@$0CA@$0CA@$0EAA@@@QEAAXAEBV0@@Z; TLMString<32,32,1024>::operator=(TLMString<32,32,1024> const &)
0x18000ed6c  jmp     loc_18000EBDB
```
