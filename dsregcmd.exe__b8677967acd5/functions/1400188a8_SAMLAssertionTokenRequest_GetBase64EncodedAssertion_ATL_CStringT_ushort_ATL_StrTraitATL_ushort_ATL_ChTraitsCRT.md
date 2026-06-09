# SAMLAssertionTokenRequest::GetBase64EncodedAssertion(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x1400188a8`
- end: `0x1400189e9`
- name: `?GetBase64EncodedAssertion@SAMLAssertionTokenRequest@@CA?AVCSecureStringA@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `321`
- prototype: `char **__fastcall(char **, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1400180b8`

## callees

- `0x140005c58`
- `0x14000caac`
- `0x14000e6a0`
- `0x140012448`
- `0x1400127bc`
- `0x140012de4`
- `0x140013604`
- `0x1400188a8`
- `0x14002c3e8`
- `0x140030010`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
char **__fastcall SAMLAssertionTokenRequest::GetBase64EncodedAssertion(char **a1, __int64 a2)
{
  unsigned int v4; // edx
  int RequiredLength; // eax
  __int64 v6; // rdi
  char *v7; // r8
  char *v8; // rax
  __int64 v9; // rcx
  unsigned int v11; // [rsp+20h] [rbp-40h]
  _BYTE pExceptionObject[16]; // [rsp+38h] [rbp-28h] BYREF
  unsigned __int8 *v13[2]; // [rsp+48h] [rbp-18h] BYREF
  __int64 v14; // [rsp+58h] [rbp-8h]
  int v15; // [rsp+90h] [rbp+30h] BYREF

  *a1 = (char *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  *(_OWORD *)v13 = 0;
  v14 = 0;
  StringUtility::EncodeString(a2, v13);
  RequiredLength = ATL::Base64EncodeGetRequiredLength(LODWORD(v13[1]) - LODWORD(v13[0]), v4);
  v6 = RequiredLength;
  v15 = RequiredLength;
  if ( ((*((_DWORD *)*a1 - 3) - RequiredLength) | (1 - *((_DWORD *)*a1 - 2))) < 0 )
    ATL::CSimpleStringT<char,0>::PrepareWrite2(a1, (unsigned int)RequiredLength);
  if ( (int)v6 < 0 )
    goto LABEL_14;
  v7 = *a1;
  if ( (int)v6 > *((_DWORD *)*a1 - 3) )
    goto LABEL_14;
  *((_DWORD *)v7 - 4) = v6;
  (*a1)[v6] = 0;
  if ( !ATL::Base64Encode(v13[0], LODWORD(v13[1]) - LODWORD(v13[0]), v7, &v15, v11) )
  {
    Exception::Exception((Exception *)pExceptionObject, -894828542);
    throw (Exception *)pExceptionObject;
  }
  LODWORD(v8) = v15;
  v9 = -1;
  if ( v15 == -1 )
  {
    v8 = *a1;
    if ( *a1 )
    {
      do
        ++v9;
      while ( v8[v9] );
      LODWORD(v8) = v9;
    }
  }
  if ( (int)v8 < 0 || (int)v8 > *((_DWORD *)*a1 - 3) )
LABEL_14:
    ATL::AtlThrowImpl(0x80070057);
  *((_DWORD *)*a1 - 4) = (_DWORD)v8;
  (*a1)[(int)v8] = 0;
  std::vector<unsigned char>::~vector<unsigned char>((char **)v13);
  return a1;
}

```

## disassembly

```asm
0x1400188a8  mov     [rsp-18h+arg_8], rbx
0x1400188ad  mov     [rsp-18h+arg_0], rcx
0x1400188b2  push    rbp
0x1400188b3  push    rsi
0x1400188b4  push    rdi
0x1400188b5  mov     rbp, rsp
0x1400188b8  sub     rsp, 60h
0x1400188bc  mov     rdi, rdx
0x1400188bf  mov     rsi, rcx
0x1400188c2  mov     [rbp+var_30], 0
0x1400188c9  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400188d0  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x1400188d7  mov     rax, [rax+18h]
0x1400188db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400188e0  add     rax, 18h
0x1400188e4  mov     [rsi], rax
0x1400188e7  mov     ebx, 1
0x1400188ec  mov     [rbp+var_30], ebx
0x1400188ef  xorps   xmm0, xmm0
0x1400188f2  movdqu  xmmword ptr [rbp+var_18], xmm0
0x1400188f7  mov     [rbp+var_8], 0
0x1400188ff  lea     rdx, [rbp+var_18]
0x140018903  mov     rcx, rdi
0x140018906  call    ?EncodeString@StringUtility@@SAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV?$vector@EV?$allocator@E@std@@@std@@I@Z; StringUtility::EncodeString(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,std::vector<uchar> &,uint)
0x14001890b  mov     ecx, dword ptr [rbp+var_18+8]
0x14001890e  sub     ecx, dword ptr [rbp+var_18]; int
0x140018911  call    ?Base64EncodeGetRequiredLength@ATL@@YAHHK@Z; ATL::Base64EncodeGetRequiredLength(int,ulong)
0x140018916  movsxd  rdi, eax
0x140018919  mov     [rbp+arg_10], edi
0x14001891c  mov     rcx, [rsi]
0x14001891f  sub     ebx, [rcx-8]
0x140018922  mov     edx, [rcx-0Ch]
0x140018925  sub     edx, edi
0x140018927  or      ebx, edx
0x140018929  jge     short loc_140018935
0x14001892b  mov     edx, edi
0x14001892d  mov     rcx, rsi
0x140018930  call    ?PrepareWrite2@?$CSimpleStringT@D$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<char,0>::PrepareWrite2(int)
0x140018935  test    edi, edi
0x140018937  js      loc_1400189DE
0x14001893d  mov     r8, [rsi]; char *
0x140018940  cmp     edi, [r8-0Ch]
0x140018944  jg      loc_1400189DE
0x14001894a  mov     [r8-10h], edi
0x14001894e  mov     rax, [rsi]
0x140018951  mov     byte ptr [rdi+rax], 0
0x140018955  mov     rcx, [rbp+var_18]; unsigned __int8 *
0x140018959  mov     edx, dword ptr [rbp+var_18+8]
0x14001895c  sub     edx, ecx; int
0x14001895e  lea     r9, [rbp+arg_10]; int *
0x140018962  call    ?Base64Encode@ATL@@YAHPEBEHPEADPEAHK@Z; ATL::Base64Encode(uchar const *,int,char *,int *,ulong)
0x140018967  test    eax, eax
0x140018969  jz      short loc_1400189BF
0x14001896b  mov     eax, [rbp+arg_10]
0x14001896e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140018972  cmp     eax, ecx
0x140018974  jnz     short loc_14001898A
0x140018976  mov     rax, [rsi]
0x140018979  test    rax, rax
0x14001897c  jz      short loc_14001898A
0x14001897e  inc     rcx
0x140018981  cmp     byte ptr [rax+rcx], 0
0x140018985  jnz     short loc_14001897E
0x140018987  mov     rax, rcx
0x14001898a  test    eax, eax
0x14001898c  js      short loc_1400189DE
0x14001898e  mov     rcx, [rsi]
0x140018991  cmp     eax, [rcx-0Ch]
0x140018994  jg      short loc_1400189DE
0x140018996  mov     [rcx-10h], eax
0x140018999  movsxd  rcx, eax
0x14001899c  mov     rax, [rsi]
0x14001899f  mov     byte ptr [rcx+rax], 0
0x1400189a3  lea     rcx, [rbp+var_18]
0x1400189a7  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x1400189ac  mov     rax, rsi
0x1400189af  mov     rbx, [rsp+60h+arg_8]
0x1400189b7  add     rsp, 60h
0x1400189bb  pop     rdi
0x1400189bc  pop     rsi
0x1400189bd  pop     rbp
0x1400189be  retn
0x1400189bf  mov     edx, 0CAAA0002h; unsigned int
0x1400189c4  lea     rcx, [rbp+pExceptionObject]; this
0x1400189c8  call    ??0Exception@@QEAA@K@Z; Exception::Exception(ulong)
0x1400189cd  lea     rdx, _TI1?AVException@@; pThrowInfo
0x1400189d4  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x1400189d8  call    _CxxThrowException_0
0x1400189de  mov     ecx, 80070057h; unsigned int
0x1400189e3  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
