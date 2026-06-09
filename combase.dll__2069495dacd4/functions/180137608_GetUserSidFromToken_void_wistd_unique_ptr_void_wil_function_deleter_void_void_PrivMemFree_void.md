# GetUserSidFromToken(void *,wistd::unique_ptr<void,wil::function_deleter<void (*)(void *),&PrivMemFree(void *)>> *)

- ea: `0x180137608`
- end: `0x1801378a7`
- name: `?GetUserSidFromToken@@YAJPEAXPEAV?$unique_ptr@XU?$function_deleter@P6AXPEAX@Z$1?PrivMemFree@@YAX0@Z@wil@@@wistd@@@Z`
- size: `671`
- prototype: `HRESULT __fastcall(void *token, wistd::unique_ptr<void,wil::function_deleter<void (__cdecl*)(void *),&PrivMemFree> > *ppSid)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800d11ec`
- `0x1801374dc`

## callees

- `0x18003a8bc`
- `0x18003cf8c`
- `0x180086038`
- `0x18008ce08`
- `0x180137608`
- `0x18018ab84`
- `0x1801999b0`
- `0x18019a080`
- `0x180255010`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180137657`
- `ntdll!NtQueryInformationToken` at `0x180137790`
- `ntdll!NtQueryInformationToken` at `0x180137657`
- `ntdll!NtQueryInformationToken` at `0x180137790`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801377b1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801377b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801377ed`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1801377ed`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1801377cf`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1801377cf`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18013779d`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18013779d`

## string_xrefs

- `0x1801376d2`: `onecore\com\combase\processtoken\processtoken.cxx`
- `0x1801376f3`: `onecore\com\combase\processtoken\processtoken.cxx`
- `0x180137816`: `onecore\com\combase\processtoken\processtoken.cxx`
- `0x180137832`: `onecore\com\combase\processtoken\processtoken.cxx`
- `0x180137872`: `onecore\com\combase\processtoken\processtoken.cxx`

## pseudocode

```c
__int64 __fastcall GetUserSidFromToken(
        void *token,
        wistd::unique_ptr<void,wil::function_deleter<void (__cdecl*)(void *),&PrivMemFree> > *ppSid)
{
  unsigned __int64 v4; // rbx
  PSID *p_cbNeeded; // rdi
  unsigned __int64 v6; // rcx
  _DWORD *v7; // rax
  unsigned int LastError; // ebx
  __int64 v10; // rcx
  unsigned __int64 v11; // rcx
  void *v12; // rsp
  void *v13; // rsp
  NTSTATUS v14; // eax
  SIZE_T LengthSid; // rsi
  void *v16; // rax
  void *v17; // rbx
  void *value; // r8
  __int64 v19; // [rsp+0h] [rbp-30h] BYREF
  unsigned int cbNeeded; // [rsp+30h] [rbp+0h] BYREF
  wistd::unique_ptr<void,wil::function_deleter<void (__cdecl*)(void *),&PrivMemFree> > sidBuffer; // [rsp+38h] [rbp+8h] BYREF
  unsigned __int8 bDummyBuffer[16]; // [rsp+40h] [rbp+10h] BYREF
  void *retaddr; // [rsp+88h] [rbp+58h]

  cbNeeded = 0;
  *(_OWORD *)bDummyBuffer = 0;
  if ( NtQueryInformationToken(token, TokenUser, bDummyBuffer, 0, &cbNeeded) != -1073741789 )
  {
    LastError = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x2C1u,
      "onecore\\com\\combase\\processtoken\\processtoken.cxx",
      -2147418113);
    return LastError;
  }
  v4 = cbNeeded;
  p_cbNeeded = 0;
  if ( !cbNeeded )
    goto LABEL_34;
  if ( cbNeeded > g_ulMaxStackAllocSize )
    goto LABEL_34;
  v6 = cbNeeded + g_ulAdditionalProbeSize + 8;
  if ( v6 < cbNeeded || !VerifyStackAvailable(v6) )
    goto LABEL_34;
  v10 = v4 + 23;
  if ( v4 + 23 <= v4 + 8 )
    v10 = 0xFFFFFFFFFFFFFF0LL;
  v11 = v10 & 0xFFFFFFFFFFFFFFF0uLL;
  v12 = alloca(v11);
  v13 = alloca(v11);
  p_cbNeeded = (PSID *)&cbNeeded;
  if ( &v19 == (__int64 *)-48LL || (cbNeeded = 1801679955, (p_cbNeeded = (PSID *)&sidBuffer) == 0) )
  {
LABEL_34:
    if ( v4 + 8 >= v4 )
    {
      v7 = (_DWORD *)((__int64 (*)(void))g_pfnAllocate)();
      p_cbNeeded = (PSID *)v7;
      if ( v7 )
      {
        *v7 = 1885431112;
        p_cbNeeded = (PSID *)(v7 + 2);
      }
    }
  }
  if ( !p_cbNeeded )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x2C5u,
      "onecore\\com\\combase\\processtoken\\processtoken.cxx",
      -2147024882);
    return 2147942414LL;
  }
  v14 = NtQueryInformationToken(token, TokenUser, p_cbNeeded, cbNeeded, &cbNeeded);
  if ( v14 < 0 )
  {
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  0x2CBu,
                  "onecore\\com\\combase\\processtoken\\processtoken.cxx",
                  (const char *)(unsigned int)v14);
    goto LABEL_27;
  }
  LengthSid = GetLengthSid(*p_cbNeeded);
  v16 = HeapAlloc(g_hHeap, 0, LengthSid);
  sidBuffer.__ptr_.__value_ = v16;
  v17 = v16;
  if ( !v16 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      0x2D0u,
      "onecore\\com\\combase\\processtoken\\processtoken.cxx",
      -2147024882);
    if ( *((_DWORD *)p_cbNeeded - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
    return 2147942414LL;
  }
  if ( !CopySid(LengthSid, v16, *p_cbNeeded) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  0x2D2u,
                  "onecore\\com\\combase\\processtoken\\processtoken.cxx");
    std::unique_ptr<unsigned char [0],DeleteMarshaledTargetInfo>::reset<unsigned char *,0>(
      (wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> *)&sidBuffer,
      0);
LABEL_27:
    if ( *((_DWORD *)p_cbNeeded - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
    return LastError;
  }
  value = ppSid->__ptr_.__value_;
  ppSid->__ptr_.__value_ = v17;
  if ( value )
    HeapFree(g_hHeap, 0, value);
  if ( *((_DWORD *)p_cbNeeded - 2) == 1885431112 )
    ((void (*)(void))g_pfnFree)();
  return 0;
}

```

## disassembly

```asm
0x180137608  push    rbp
0x18013760a  push    rsi
0x18013760b  push    rdi
0x18013760c  push    r14
0x18013760e  push    r15
0x180137610  sub     rsp, 60h
0x180137614  lea     rbp, [rsp+30h]
0x180137619  mov     [rbp+50h+arg_10], rbx
0x18013761d  mov     rax, cs:__security_cookie
0x180137624  xor     rax, rbp
0x180137627  mov     [rbp+50h+var_30], rax
0x18013762b  xor     r9d, r9d; TokenInformationLength
0x18013762e  mov     [rbp+50h+cbNeeded], 0
0x180137635  mov     r14, ppSid
0x180137638  lea     rax, [rbp+50h+cbNeeded]
0x18013763c  xorps   xmm0, xmm0
0x18013763f  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x180137644  lea     r8, [rbp+50h+bDummyBuffer+7]
0x180137648  mov     rsi, token
0x18013764b  lea     edx, [r9+1]; TokenInformationClass
0x18013764f  and     r8, 0FFFFFFFFFFFFFFF8h; TokenInformation
0x180137653  movups  xmmword ptr [rbp+50h+bDummyBuffer], xmm0
0x180137657  call    cs:__imp_NtQueryInformationToken
0x18013765d  cmp     eax, 0C0000023h
0x180137662  jnz     short loc_1801376CE
0x180137664  mov     ebx, [rbp+50h+cbNeeded]
0x180137667  xor     edi, edi
0x180137669  mov     r15d, 70616548h
0x18013766f  test    rbx, rbx
0x180137672  jz      short loc_18013769D
0x180137674  cmp     rbx, cs:g_ulMaxStackAllocSize
0x18013767b  ja      short loc_18013769D
0x18013767d  mov     token, cs:g_ulAdditionalProbeSize
0x180137684  add     token, 8
0x180137688  add     token, rbx; Size
0x18013768b  cmp     token, rbx
0x18013768e  jb      short loc_18013769D
0x180137690  call    VerifyStackAvailable
0x180137695  test    eax, eax
0x180137697  jnz     loc_18013772B
0x18013769d  lea     token, [rbx+8]
0x1801376a1  cmp     token, rbx
0x1801376a4  jb      loc_18013776F
0x1801376aa  mov     rax, cs:g_pfnAllocate
0x1801376b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801376b6  mov     rdi, rax
0x1801376b9  test    rax, rax
0x1801376bc  jz      loc_18013776F
0x1801376c2  mov     [rax], r15d
0x1801376c5  add     rdi, 8
0x1801376c9  jmp     loc_18013776F
0x1801376ce  mov     token, [rbp+58h]; callerReturnAddress
0x1801376d2  lea     r8, aOnecoreComComb_166; "onecore\\com\\combase\\processtoken\\pr"...
0x1801376d9  mov     ebx, 8000FFFFh
0x1801376de  mov     edx, 2C1h; lineNumber
0x1801376e3  mov     r9d, ebx; hr
0x1801376e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801376eb  mov     eax, ebx
0x1801376ed  jmp     short loc_18013770F
0x1801376ef  mov     token, [rbp+58h]; callerReturnAddress
0x1801376f3  lea     r8, aOnecoreComComb_166; "onecore\\com\\combase\\processtoken\\pr"...
0x1801376fa  mov     r9d, 8007000Eh; hr
0x180137700  mov     edx, 2C5h; lineNumber
0x180137705  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013770a  mov     eax, 8007000Eh
0x18013770f  mov     token, [rbp+50h+var_30]
0x180137713  xor     token, rbp; StackCookie
0x180137716  call    __security_check_cookie
0x18013771b  mov     rbx, [rbp+50h+arg_10]
0x18013771f  lea     rsp, [rbp+30h]
0x180137723  pop     r15
0x180137725  pop     r14
0x180137727  pop     rdi
0x180137728  pop     rsi
0x180137729  pop     rbp
0x18013772a  retn
0x18013772b  lea     rax, [rbx+8]
0x18013772f  lea     token, [rax+0Fh]
0x180137733  cmp     token, rax
0x180137736  ja      short loc_180137742
0x180137738  mov     token, 0FFFFFFFFFFFFFF0h
0x180137742  and     token, 0FFFFFFFFFFFFFFF0h
0x180137746  mov     rax, token
0x180137749  call    _alloca_probe
0x18013774e  sub     rsp, token
0x180137751  lea     rdi, [rsp+80h+cbNeeded]
0x180137756  test    rdi, rdi
0x180137759  jz      loc_18013769D
0x18013775f  mov     dword ptr [rdi], 6B637453h
0x180137765  add     rdi, 8
0x180137769  jz      loc_18013769D
0x18013776f  test    rdi, rdi
0x180137772  jz      loc_1801376EF
0x180137778  mov     r9d, [rbp+50h+cbNeeded]; TokenInformationLength
0x18013777c  lea     rax, [rbp+50h+cbNeeded]
0x180137780  mov     r8, rdi; TokenInformation
0x180137783  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x180137788  mov     edx, 1; TokenInformationClass
0x18013778d  mov     token, rsi; TokenHandle
0x180137790  call    cs:__imp_NtQueryInformationToken
0x180137796  test    eax, eax
0x180137798  js      short loc_180137812
0x18013779a  mov     token, [rdi]; pSid
0x18013779d  call    cs:__imp_GetLengthSid
0x1801377a3  mov     token, cs:?g_hHeap@@3QEAXEA; hHeap
0x1801377aa  xor     edx, edx; dwFlags
0x1801377ac  mov     r8d, eax; dwBytes
0x1801377af  mov     esi, eax
0x1801377b1  call    cs:__imp_HeapAlloc
0x1801377b7  mov     [rbp+50h+sidBuffer.__ptr_.__value_], rax
0x1801377bb  mov     rbx, rax
0x1801377be  test    rax, rax
0x1801377c1  jz      loc_18013786E
0x1801377c7  mov     r8, [rdi]; pSourceSid
0x1801377ca  mov     ppSid, rax; pDestinationSid
0x1801377cd  mov     ecx, esi; nDestinationSidLength
0x1801377cf  call    cs:__imp_CopySid
0x1801377d5  test    eax, eax
0x1801377d7  jz      short loc_18013782E
0x1801377d9  mov     r8, [r14]; lpMem
0x1801377dc  mov     [r14], rbx
0x1801377df  test    r8, r8
0x1801377e2  jz      short loc_1801377F3
0x1801377e4  mov     token, cs:?g_hHeap@@3QEAXEA; hHeap
0x1801377eb  xor     edx, edx; dwFlags
0x1801377ed  call    cs:__imp_HeapFree
0x1801377f3  lea     token, [rdi-8]
0x1801377f7  cmp     [token], r15d
0x1801377fa  jnz     loc_18024E1D6
0x180137800  mov     rax, cs:g_pfnFree
0x180137807  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013780c  nop
0x18013780d  jmp     loc_18024E1D6
0x180137812  mov     token, [rbp+58h]; callerReturnAddress
0x180137816  lea     r8, aOnecoreComComb_166; "onecore\\com\\combase\\processtoken\\pr"...
0x18013781d  mov     r9d, eax; status
0x180137820  mov     edx, 2CBh; lineNumber
0x180137825  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18013782a  mov     ebx, eax
0x18013782c  jmp     short loc_180137850
0x18013782e  mov     token, [rbp+58h]; callerReturnAddress
0x180137832  lea     r8, aOnecoreComComb_166; "onecore\\com\\combase\\processtoken\\pr"...
0x180137839  mov     edx, 2D2h; lineNumber
0x18013783e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180137843  xor     edx, edx; __p
0x180137845  lea     token, [rbp+50h+sidBuffer]; this
0x180137849  mov     ebx, eax
0x18013784b  call    ??$reset@PEAE$0A@@?$unique_ptr@$$BY0A@EUDeleteMarshaledTargetInfo@@@std@@QEAAXPEAE@Z; std::unique_ptr<uchar [0],DeleteMarshaledTargetInfo>::reset<uchar *,0>(uchar *)
0x180137850  lea     token, [rdi-8]
0x180137854  cmp     [token], r15d
0x180137857  jnz     loc_1801376EB
0x18013785d  mov     rax, cs:g_pfnFree
0x180137864  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137869  jmp     loc_1801376EB
0x18013786e  mov     token, [rbp+58h]; callerReturnAddress
0x180137872  lea     r8, aOnecoreComComb_166; "onecore\\com\\combase\\processtoken\\pr"...
0x180137879  mov     r9d, 8007000Eh; hr
0x18013787f  mov     edx, 2D0h; lineNumber
0x180137884  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180137889  lea     token, [rdi-8]
0x18013788d  cmp     [token], r15d
0x180137890  jnz     loc_18013770A
0x180137896  mov     rax, cs:g_pfnFree
0x18013789d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801378a2  jmp     loc_18013770A
0x18024e1d6  xor     eax, eax
0x18024e1d8  jmp     loc_18013770F
```
