# PpfTransformStore::DeleteTransform(ushort const *)

- ea: `0x180038a4c`
- end: `0x180038c76`
- name: `?DeleteTransform@PpfTransformStore@@QEAAJPEBG@Z`
- size: `554`
- prototype: `__int64 __fastcall(PpfTransformStore *this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x1800107e8`
- `0x180013ef4`

## callees

- `0x180003270`
- `0x18000b5c8`
- `0x18000c6d0`
- `0x18000dfe0`
- `0x18001c48c`
- `0x18002a92c`
- `0x18002d5ec`
- `0x180038a4c`
- `0x18003bad0`
- `0x18003bd9c`

## string_xrefs

- `0x180038a77`: `PpfTransformStore::DeleteTransform`
- `0x180038b1b`: `%ws transform does not exist to delete.`

## pseudocode

```c
__int64 __fastcall PpfTransformStore::DeleteTransform(PpfTransformStore *this, const unsigned __int16 *a2)
{
  const char *v4; // r9
  __int64 v5; // rdi
  _QWORD *v6; // rbx
  __int64 v7; // rsi
  const wchar_t *v8; // rcx
  __int64 v9; // rax
  size_t v10; // r8
  unsigned int v11; // ebx
  __int64 v13; // r8
  __int128 v14; // [rsp+30h] [rbp-58h] BYREF
  __int128 v15; // [rsp+40h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  PpfTraceLogFormat(
    "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
    0x84u,
    "PpfTraceFunctionEntryExit::PpfTraceFunctionEntryExit",
    "Entering %hs",
    "PpfTransformStore::DeleteTransform");
  if ( dword_180072BF8 != 1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1C2,
      (int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
      v4);
  v5 = qword_180072C00;
  v6 = *(_QWORD **)qword_180072C00;
  v7 = -1;
  while ( v6 != (_QWORD *)v5 )
  {
    v8 = (const wchar_t *)(v6 + 2);
    v9 = -1;
    do
      ++v9;
    while ( a2[v9] );
    v10 = v6[4];
    if ( v6[5] > 7u )
      v8 = *(const wchar_t **)v8;
    if ( v10 == v9 && (!v10 || !wmemcmp(v8, a2, v10)) )
      break;
    v6 = (_QWORD *)*v6;
  }
  if ( v6 == (_QWORD *)qword_180072C00 )
  {
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
      0x1C7u,
      "PpfTransformStore::DeleteTransform",
      "%ws transform does not exist to delete.");
    v11 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x1C8,
            (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\txstore.cpp",
            (const char *)2,
            (unsigned int)a2);
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfTransformStore::DeleteTransform");
    return v11;
  }
  else
  {
    v14 = 0;
    v15 = 0;
    v13 = -1;
    do
      ++v13;
    while ( a2[v13] );
    std::wstring::_Construct<1,unsigned short const *>(&v14, a2);
    std::list<std::wstring>::remove(&qword_180072C00, &v14);
    std::wstring::~wstring((char **)&v14);
    v14 = 0;
    v15 = 0;
    do
      ++v7;
    while ( a2[v7] );
    std::wstring::_Construct<1,unsigned short const *>(&v14, a2);
    std::_Tree<std::_Tmap_traits<std::wstring,PpfTransformInfo,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PpfTransformInfo>>,0>>::erase(
      &qword_180072C10,
      &v14);
    std::wstring::~wstring((char **)&v14);
    *((_BYTE *)this + 96) = 1;
    PpfTraceLogFormat(
      "onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.h",
      0x89u,
      "PpfTraceFunctionEntryExit::~PpfTraceFunctionEntryExit",
      "Leaving %hs",
      "PpfTransformStore::DeleteTransform");
    return 0;
  }
}

```

## disassembly

```asm
0x180038a4c  mov     [rsp+arg_10], rbx
0x180038a51  mov     [rsp+arg_18], rbp
0x180038a56  push    rsi
0x180038a57  push    rdi
0x180038a58  push    r12
0x180038a5a  push    r14
0x180038a5c  push    r15
0x180038a5e  sub     rsp, 60h
0x180038a62  mov     rax, cs:__security_cookie
0x180038a69  xor     rax, rsp
0x180038a6c  mov     [rsp+88h+var_38], rax
0x180038a71  mov     rbp, rdx
0x180038a74  mov     r14, rcx
0x180038a77  lea     r12, aPpftransformst_4; "PpfTransformStore::DeleteTransform"
0x180038a7e  mov     qword ptr [rsp+88h+var_68], r12
0x180038a83  lea     r9, aEnteringHs; "Entering %hs"
0x180038a8a  lea     r8, aPpftracefuncti; "PpfTraceFunctionEntryExit::PpfTraceFunc"...
0x180038a91  mov     edx, 84h; unsigned int
0x180038a96  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180038a9d  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180038aa2  cmp     cs:dword_180072BF8, 1
0x180038aa9  setnz   al
0x180038aac  mov     rcx, [rsp+88h]; this
0x180038ab4  xor     r15d, r15d
0x180038ab7  test    al, al
0x180038ab9  jnz     loc_180038C64
0x180038abf  mov     rdi, cs:qword_180072C00
0x180038ac6  mov     rbx, [rdi]
0x180038ac9  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180038acd  cmp     rbx, rdi
0x180038ad0  jz      short loc_180038B0D
0x180038ad2  lea     rcx, [rbx+10h]
0x180038ad6  mov     rax, rsi
0x180038ad9  inc     rax
0x180038adc  cmp     [rbp+rax*2+0], r15w
0x180038ae2  jnz     short loc_180038AD9
0x180038ae4  mov     r8, [rbx+20h]; N
0x180038ae8  cmp     qword ptr [rcx+18h], 7
0x180038aed  jbe     short loc_180038AF2
0x180038aef  mov     rcx, [rcx]; S1
0x180038af2  cmp     r8, rax
0x180038af5  jnz     short loc_180038B08
0x180038af7  test    r8, r8
0x180038afa  jz      short loc_180038B0D
0x180038afc  mov     rdx, rbp; S2
0x180038aff  call    wmemcmp
0x180038b04  test    eax, eax
0x180038b06  jz      short loc_180038B0D
0x180038b08  mov     rbx, [rbx]
0x180038b0b  jmp     short loc_180038ACD
0x180038b0d  cmp     rbx, cs:qword_180072C00
0x180038b14  jnz     short loc_180038B83
0x180038b16  mov     qword ptr [rsp+88h+var_68], rbp; unsigned int
0x180038b1b  lea     r9, aWsTransformDoe; "%ws transform does not exist to delete."
0x180038b22  mov     r8, r12; char *
0x180038b25  mov     edx, 1C7h; unsigned int
0x180038b2a  lea     rcx, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180038b31  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180038b36  mov     rcx, [rsp+88h]; this
0x180038b3e  mov     r9d, 2; char *
0x180038b44  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180038b4b  mov     edx, 1C8h; void *
0x180038b50  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180038b55  mov     ebx, eax
0x180038b57  mov     qword ptr [rsp+88h+var_68], r12
0x180038b5c  lea     r9, aLeavingHs; "Leaving %hs"
0x180038b63  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x180038b6a  mov     edx, 89h; unsigned int
0x180038b6f  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180038b76  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180038b7b  nop
0x180038b7c  mov     eax, ebx
0x180038b7e  jmp     loc_180038C3D
0x180038b83  xorps   xmm0, xmm0
0x180038b86  movups  [rsp+88h+var_58], xmm0
0x180038b8b  xorps   xmm1, xmm1
0x180038b8e  movdqu  [rsp+88h+var_48], xmm1
0x180038b94  mov     r8, rsi
0x180038b97  inc     r8
0x180038b9a  cmp     [rbp+r8*2+0], r15w
0x180038ba0  jnz     short loc_180038B97
0x180038ba2  mov     rdx, rbp
0x180038ba5  lea     rcx, [rsp+88h+var_58]
0x180038baa  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180038baf  lea     rdx, [rsp+88h+var_58]
0x180038bb4  lea     rcx, qword_180072C00
0x180038bbb  call    ?remove@?$list@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::list<std::wstring>::remove(std::wstring const &)
0x180038bc0  lea     rcx, [rsp+88h+var_58]
0x180038bc5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180038bca  xorps   xmm0, xmm0
0x180038bcd  movups  [rsp+88h+var_58], xmm0
0x180038bd2  xorps   xmm1, xmm1
0x180038bd5  movdqu  [rsp+88h+var_48], xmm1
0x180038bdb  inc     rsi
0x180038bde  cmp     [rbp+rsi*2+0], r15w
0x180038be4  jnz     short loc_180038BDB
0x180038be6  mov     r8, rsi
0x180038be9  mov     rdx, rbp
0x180038bec  lea     rcx, [rsp+88h+var_58]
0x180038bf1  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180038bf6  lea     rdx, [rsp+88h+var_58]
0x180038bfb  lea     rcx, qword_180072C10
0x180038c02  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VPpfTransformInfo@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VPpfTransformInfo@@@std@@@2@$0A@@std@@@std@@QEAA_KAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,PpfTransformInfo,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,PpfTransformInfo>>,0>>::erase(std::wstring const &)
0x180038c07  lea     rcx, [rsp+88h+var_58]
0x180038c0c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180038c11  mov     byte ptr [r14+60h], 1
0x180038c16  mov     qword ptr [rsp+88h+var_68], r12
0x180038c1b  lea     r9, aLeavingHs; "Leaving %hs"
0x180038c22  lea     r8, aPpftracefuncti_0; "PpfTraceFunctionEntryExit::~PpfTraceFun"...
0x180038c29  mov     edx, 89h; unsigned int
0x180038c2e  lea     rcx, aOnecoreBaseNgs_11; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180038c35  call    ?PpfTraceLogFormat@@YAXPEBDI00ZZ; PpfTraceLogFormat(char const *,uint,char const *,char const *,...)
0x180038c3a  nop
0x180038c3b  xor     eax, eax
0x180038c3d  mov     rcx, [rsp+88h+var_38]
0x180038c42  xor     rcx, rsp; StackCookie
0x180038c45  call    __security_check_cookie
0x180038c4a  lea     r11, [rsp+88h+var_28]
0x180038c4f  mov     rbx, [r11+40h]
0x180038c53  mov     rbp, [r11+48h]
0x180038c57  mov     rsp, r11
0x180038c5a  pop     r15
0x180038c5c  pop     r14
0x180038c5e  pop     r12
0x180038c60  pop     rdi
0x180038c61  pop     rsi
0x180038c62  retn
0x180038c64  lea     r8, aOnecoreBaseNgs_9; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x180038c6b  mov     edx, 1C2h; void *
0x180038c70  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
