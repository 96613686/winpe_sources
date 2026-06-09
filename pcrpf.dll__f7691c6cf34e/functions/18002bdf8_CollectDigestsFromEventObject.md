# CollectDigestsFromEventObject

- ea: `0x18002bdf8`
- end: `0x18002c3b3`
- name: `CollectDigestsFromEventObject`
- size: `1467`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18002da6c`

## callees

- `0x180003270`
- `0x180003cc0`
- `0x1800290f4`
- `0x18002919c`
- `0x18002aa70`
- `0x18002b204`
- `0x18002bdf8`
- `0x180030534`
- `0x180034724`
- `0x180034780`
- `0x180034f7c`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c171`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c221`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c171`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002c221`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c185`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c235`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c185`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002c235`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002bfbe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002c130`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002bfbe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002c130`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c24b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c261`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c24b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002c261`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002be47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002bf74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002c0dd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002be47`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002bf74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18002c0dd`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
unsigned int __fastcall CollectDigestsFromEventObject(__int64 *a1, __int64 a2)
{
  __int64 v4; // rdi
  HRESULT v5; // eax
  int v6; // edx
  unsigned int v7; // r8d
  unsigned int result; // eax
  int v9; // eax
  wil::details::in1diag3 *v10; // rcx
  int v11; // eax
  __int64 v12; // rcx
  unsigned int i; // r12d
  int v14; // eax
  int v15; // eax
  PCWSTR *v16; // rdi
  PCWSTR v17; // rsi
  HRESULT v18; // eax
  int v19; // edx
  unsigned int v20; // r8d
  int v21; // eax
  unsigned __int16 v22; // r15
  unsigned __int16 v23; // r14
  PCWSTR StringRawBuffer; // rsi
  unsigned __int16 v25; // di
  int Size; // eax
  int v27; // edx
  wil::details::in1diag3 *v28; // rcx
  PCWSTR *v29; // rdi
  HRESULT v30; // eax
  int v31; // edx
  unsigned int v32; // r8d
  int v33; // eax
  const unsigned __int16 *v34; // rax
  int v35; // eax
  void *v36; // rdi
  HANDLE ProcessHeap; // rax
  __int64 v38; // rax
  void *v39; // rdi
  HANDLE v40; // rax
  PCWSTR *v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rcx
  __int64 (__fastcall ***v44)(_QWORD, GUID *, _QWORD *); // rcx
  int Format; // [rsp+20h] [rbp-79h]
  char *v46; // [rsp+30h] [rbp-69h]
  __int64 v47; // [rsp+38h] [rbp-61h]
  __int64 v48; // [rsp+40h] [rbp-59h] BYREF
  __int64 (__fastcall ***v49)(_QWORD, GUID *, __int64 *); // [rsp+48h] [rbp-51h] BYREF
  unsigned int v50[2]; // [rsp+50h] [rbp-49h] BYREF
  unsigned int v51; // [rsp+58h] [rbp-41h] BYREF
  __int64 v52; // [rsp+60h] [rbp-39h] BYREF
  PCWSTR *v53; // [rsp+68h] [rbp-31h] BYREF
  LPVOID lpMem; // [rsp+70h] [rbp-29h] BYREF
  __int64 v55; // [rsp+78h] [rbp-21h] BYREF
  HSTRING v56; // [rsp+80h] [rbp-19h] BYREF
  HSTRING v57; // [rsp+88h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+90h] [rbp-9h] BYREF
  HSTRING string; // [rsp+A8h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  v49 = 0;
  v4 = *a1;
  string = 0;
  v5 = WindowsCreateStringReference(L"Digests", 7u, &hstringHeader, &string);
  if ( v5 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v5, v6, v7);
    goto LABEL_53;
  }
  result = (*(__int64 (__fastcall **)(__int64 *, HSTRING, _QWORD))(v4 + 72))(a1, string, &v49);
  if ( result == -2089484279 )
    goto LABEL_47;
  v52 = 0;
  v9 = (**v49)(v49, &GUID_d44662bc_dce3_59a8_9272_4b210f33908b, &v52);
  v10 = retaddr;
  if ( v9 < 0 )
LABEL_53:
    wil::details::in1diag3::_Throw_Hr(
      v10,
      (void *)0x589,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
      (const char *)(unsigned int)v9,
      Format);
  v51 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v52 + 56LL))(v52, &v51);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x58B,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
      (const char *)(unsigned int)v11,
      Format);
  result = v51;
  if ( !v51 )
  {
    v12 = v52;
    if ( v52 )
    {
      v52 = 0;
      result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    goto LABEL_47;
  }
  for ( i = 0; i < v51; ++i )
  {
    v55 = 0;
    v14 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v52 + 48LL))(v52, i, &v55);
    if ( v14 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x598,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
        (const char *)(unsigned int)v14,
        Format);
    v53 = 0;
    v15 = (*(__int64 (__fastcall **)(__int64, PCWSTR **))(*(_QWORD *)v55 + 96LL))(v55, &v53);
    if ( v15 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x59A,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
        (const char *)(unsigned int)v15,
        Format);
    v57 = 0;
    v16 = v53;
    v17 = *v53;
    string = 0;
    v18 = WindowsCreateStringReference(L"Alg", 3u, &hstringHeader, &string);
    if ( v18 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v18, v19, v20);
      JUMPOUT(0x18002C3B2LL);
    }
    v21 = (*((__int64 (__fastcall **)(PCWSTR *, HSTRING, HSTRING *))v17 + 10))(v16, string, &v57);
    if ( v21 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x59F,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
        (const char *)(unsigned int)v21,
        Format);
    v22 = 0;
    WORD2(v48) = 0;
    v23 = 0;
    LOWORD(v48) = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(v57, 0);
    LOWORD(v50[0]) = 0;
    if ( StringRawBuffer )
    {
      v25 = 0;
      while ( wcsicmp(StringRawBuffer, (const wchar_t *)c_PpfAlgorithmIdToNameTable[v25]) )
      {
        if ( ++v25 >= 0x2Au )
        {
          PpfEvtLogTraceHelper(
            (int)"minkernel\\ngscb\\ppfevtlog\\ppfevtlog.c",
            265,
            (int)"PpfEvtLogGetDigestIDAndSizeFromName",
            1,
            "No known algorithm by this name: %ws",
            (char)StringRawBuffer);
          LODWORD(StringRawBuffer) = -1073741811;
          PpfEvtLogTraceHelper(
            (int)"minkernel\\ngscb\\ppfevtlog\\ppfevtlog.c",
            266,
            (int)"PpfEvtLogGetDigestIDAndSizeFromName",
            1,
            "Error: 0x%x",
            13);
          goto LABEL_24;
        }
      }
      Size = PpfEvtLogValidateDigestAlgIDAndGetSize(v25, v50);
      LODWORD(StringRawBuffer) = Size;
      if ( Size >= 0 )
      {
        v22 = v25;
        WORD2(v48) = v25;
        v23 = v50[0];
        LOWORD(v48) = v50[0];
        goto LABEL_24;
      }
      v27 = 256;
    }
    else
    {
      LOBYTE(Size) = 13;
      LODWORD(StringRawBuffer) = -1073741811;
      v27 = 244;
    }
    PpfEvtLogTraceHelper(
      (int)"minkernel\\ngscb\\ppfevtlog\\ppfevtlog.c",
      v27,
      (int)"PpfEvtLogGetDigestIDAndSizeFromName",
      1,
      "Error: 0x%x",
      Size);
LABEL_24:
    v28 = retaddr;
    if ( (int)StringRawBuffer < 0 )
      goto LABEL_58;
    v56 = 0;
    v29 = v53;
    StringRawBuffer = *v53;
    string = 0;
    v30 = WindowsCreateStringReference(L"EventDigest", 0xBu, &hstringHeader, &string);
    if ( v30 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v30, v31, v32);
LABEL_58:
      wil::details::in1diag3::_Throw_Hr(
        v28,
        (void *)0x5A6,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
        (const char *)(unsigned int)StringRawBuffer,
        Format);
    }
    v33 = (*((__int64 (__fastcall **)(PCWSTR *, HSTRING, HSTRING *))StringRawBuffer + 10))(v29, string, &v56);
    if ( v33 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x5AB,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
        (const char *)(unsigned int)v33,
        Format);
    lpMem = 0;
    v50[0] = 0;
    hstringHeader.Reserved.Reserved1 = &lpMem;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
    hstringHeader.Reserved.Reserved2[16] = 1;
    v34 = WindowsGetStringRawBuffer(v56, 0);
    v35 = PpfhConvertHexStringToBytes(v34, (unsigned __int8 **)&hstringHeader.Reserved.Reserved2[8], v50);
    if ( v35 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x5B3,
        (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
        (const char *)(unsigned int)v35,
        Format);
    if ( hstringHeader.Reserved.Reserved2[16] )
    {
      v36 = *(void **)hstringHeader.Reserved.Reserved1;
      *(_QWORD *)hstringHeader.Reserved.Reserved1 = *(_QWORD *)&hstringHeader.Reserved.Reserved2[8];
      if ( v36 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v36);
      }
    }
    LODWORD(v47) = v50[0];
    LODWORD(v46) = v23;
    LOBYTE(Format) = v50[0] != v23;
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0x5B5,
      (unsigned int)"onecore\\base\\ngscb\\pcrpf\\helperlib\\ppfhelpers.cpp",
      (const char *)0x80070057LL,
      Format,
      (bool)"Unexpected digest size, expected: 0x%x based on alg ID, digest string size: 0x%x",
      v46,
      v47,
      v48);
    *(_QWORD *)v50 = lpMem;
    v38 = *(_QWORD *)(a2 + 8);
    if ( v38 == *(_QWORD *)(a2 + 16) )
    {
      result = std::vector<PpfhEventLogDigest>::_Emplace_reallocate<unsigned short &,unsigned char * &,unsigned short &>(
                 a2,
                 v38,
                 (unsigned int)&v48 + 4,
                 (unsigned int)v50,
                 (__int64)&v48);
    }
    else
    {
      result = (unsigned int)PpfhEventLogDigest::PpfhEventLogDigest(
                               *(PpfhEventLogDigest **)(a2 + 8),
                               v22,
                               (unsigned __int8 *)lpMem,
                               v23);
      *(_QWORD *)(a2 + 8) += 24LL;
    }
    v39 = lpMem;
    lpMem = 0;
    if ( v39 )
    {
      v40 = GetProcessHeap();
      result = HeapFree(v40, 0, v39);
    }
    if ( v56 )
      result = WindowsDeleteString(v56);
    if ( v57 )
      result = WindowsDeleteString(v57);
    v41 = v53;
    if ( v53 )
    {
      v53 = 0;
      result = (*((__int64 (__fastcall **)(PCWSTR *))*v41 + 2))(v41);
    }
    v42 = v55;
    if ( v55 )
    {
      v55 = 0;
      result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
    }
  }
  v43 = v52;
  if ( v52 )
  {
    v52 = 0;
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  }
LABEL_47:
  v44 = v49;
  if ( v49 )
  {
    v49 = 0;
    return ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, _QWORD *)))(*v44)[2])(v44);
  }
  return result;
}

```

## disassembly

```asm
0x18002bdf8  mov     [rsp-8+arg_10], rbx
0x18002bdfd  push    rbp
0x18002bdfe  push    rsi
0x18002bdff  push    rdi
0x18002be00  push    r12
0x18002be02  push    r13
0x18002be04  push    r14
0x18002be06  push    r15
0x18002be08  lea     rbp, [rsp-27h]
0x18002be0d  sub     rsp, 0C0h
0x18002be14  mov     rax, cs:__security_cookie
0x18002be1b  xor     rax, rsp
0x18002be1e  mov     [rbp+57h+var_40], rax
0x18002be22  mov     r13, rdx
0x18002be25  mov     rbx, rcx
0x18002be28  xor     esi, esi
0x18002be2a  mov     [rbp+57h+var_A8], rsi
0x18002be2e  mov     rdi, [rcx]
0x18002be31  mov     [rbp+57h+string], rsi
0x18002be35  lea     r9, [rbp+57h+string]; string
0x18002be39  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18002be3d  lea     edx, [rsi+7]; length
0x18002be40  lea     rcx, sourceString; "Digests"
0x18002be47  call    cs:__imp_WindowsCreateStringReference
0x18002be4e  nop     dword ptr [rax+rax+00h]
0x18002be53  test    eax, eax
0x18002be55  js      loc_18002C32D
0x18002be5b  lea     r8, [rbp+57h+var_A8]
0x18002be5f  mov     rdx, [rbp+57h+string]
0x18002be63  mov     rcx, rbx
0x18002be66  mov     rax, [rdi+48h]
0x18002be6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be6f  nop
0x18002be70  cmp     eax, 83750009h
0x18002be75  jnz     short loc_18002BE7C
0x18002be77  jmp     loc_18002C2C9
0x18002be7c  mov     [rbp+57h+var_90], rsi
0x18002be80  mov     rcx, [rbp+57h+var_A8]
0x18002be84  mov     rax, [rcx]
0x18002be87  lea     r8, [rbp+57h+var_90]
0x18002be8b  lea     rdx, _GUID_d44662bc_dce3_59a8_9272_4b210f33908b
0x18002be92  mov     rax, [rax]
0x18002be95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be9a  nop
0x18002be9b  mov     rcx, [rbp+5Fh]
0x18002be9f  test    eax, eax
0x18002bea1  js      loc_18002C335
0x18002bea7  mov     [rbp+57h+var_98], esi
0x18002beaa  mov     rcx, [rbp+57h+var_90]
0x18002beae  mov     rax, [rcx]
0x18002beb1  lea     rdx, [rbp+57h+var_98]
0x18002beb5  mov     rax, [rax+38h]
0x18002beb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bebe  mov     rcx, [rbp+5Fh]; this
0x18002bec2  test    eax, eax
0x18002bec4  js      loc_18002C34A
0x18002beca  mov     eax, [rbp+57h+var_98]
0x18002becd  test    eax, eax
0x18002becf  jnz     short loc_18002BEF0
0x18002bed1  mov     rcx, [rbp+57h+var_90]
0x18002bed5  test    rcx, rcx
0x18002bed8  jz      short loc_18002BEEB
0x18002beda  mov     [rbp+57h+var_90], rsi
0x18002bede  mov     rax, [rcx]
0x18002bee1  mov     rax, [rax+10h]
0x18002bee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002beea  nop
0x18002beeb  jmp     loc_18002C2C9
0x18002bef0  mov     r12d, esi
0x18002bef3  test    eax, eax
0x18002bef5  jz      loc_18002C2AF
0x18002befb  lea     rbx, aOnecoreBaseNgs_1; "onecore\\base\\ngscb\\pcrpf\\helperlib"...
0x18002bf02  mov     [rbp+57h+var_78], rsi
0x18002bf06  mov     rcx, [rbp+57h+var_90]
0x18002bf0a  mov     rax, [rcx]
0x18002bf0d  lea     r8, [rbp+57h+var_78]
0x18002bf11  mov     edx, r12d
0x18002bf14  mov     rax, [rax+30h]
0x18002bf18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf1d  mov     rcx, [rbp+5Fh]; this
0x18002bf21  test    eax, eax
0x18002bf23  js      loc_18002C31C
0x18002bf29  mov     [rbp+57h+var_88], rsi
0x18002bf2d  mov     rcx, [rbp+57h+var_78]
0x18002bf31  mov     rax, [rcx]
0x18002bf34  lea     rdx, [rbp+57h+var_88]
0x18002bf38  mov     rax, [rax+60h]
0x18002bf3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf41  mov     rcx, [rbp+5Fh]; this
0x18002bf45  test    eax, eax
0x18002bf47  js      loc_18002C30B
0x18002bf4d  mov     [rbp+57h+var_68], rsi
0x18002bf51  mov     rdi, [rbp+57h+var_88]
0x18002bf55  mov     rsi, [rdi]
0x18002bf58  mov     [rbp+57h+string], 0
0x18002bf60  lea     r9, [rbp+57h+string]; string
0x18002bf64  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18002bf68  mov     edx, 3; length
0x18002bf6d  lea     rcx, aAlg_0; "Alg"
0x18002bf74  call    cs:__imp_WindowsCreateStringReference
0x18002bf7b  nop     dword ptr [rax+rax+00h]
0x18002bf80  test    eax, eax
0x18002bf82  js      loc_18002C3AB
0x18002bf88  lea     r8, [rbp+57h+var_68]
0x18002bf8c  mov     rdx, [rbp+57h+string]
0x18002bf90  mov     rcx, rdi
0x18002bf93  mov     rax, [rsi+50h]
0x18002bf97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bf9c  mov     rcx, [rbp+5Fh]; this
0x18002bfa0  test    eax, eax
0x18002bfa2  js      loc_18002C39A
0x18002bfa8  xor     r15d, r15d
0x18002bfab  mov     [rbp+57h+var_AC], r15w
0x18002bfb0  xor     r14d, r14d
0x18002bfb3  mov     [rbp+57h+var_B0], r14w
0x18002bfb8  xor     edx, edx; length
0x18002bfba  mov     rcx, [rbp+57h+var_68]; string
0x18002bfbe  call    cs:__imp_WindowsGetStringRawBuffer
0x18002bfc5  nop     dword ptr [rax+rax+00h]
0x18002bfca  mov     rsi, rax
0x18002bfcd  xor     ecx, ecx
0x18002bfcf  mov     word ptr [rbp+57h+var_A0], cx
0x18002bfd3  test    rax, rax
0x18002bfd6  jz      loc_18002C071
0x18002bfdc  xor     edi, edi
0x18002bfde  movzx   edx, di
0x18002bfe1  lea     rax, c_PpfAlgorithmIdToNameTable
0x18002bfe8  mov     rdx, [rax+rdx*8]; String2
0x18002bfec  mov     rcx, rsi; String1
0x18002bfef  call    _wcsicmp
0x18002bff4  test    eax, eax
0x18002bff6  jz      short loc_18002C044
0x18002bff8  mov     ecx, 1
0x18002bffd  add     di, cx
0x18002c000  cmp     di, 2Ah ; '*'
0x18002c004  jb      short loc_18002BFDE
0x18002c006  mov     qword ptr [rsp+0F0h+var_C8], rsi; char
0x18002c00b  lea     rax, aNoKnownAlgorit; "No known algorithm by this name: %ws"
0x18002c012  mov     [rsp+0F0h+Format], rax; Format
0x18002c017  mov     r9d, ecx; int
0x18002c01a  lea     r8, aPpfevtloggetdi; "PpfEvtLogGetDigestIDAndSizeFromName"
0x18002c021  mov     edx, 109h; int
0x18002c026  lea     rcx, aMinkernelNgscb_1; "minkernel\\ngscb\\ppfevtlog\\ppfevtlog."...
0x18002c02d  call    PpfEvtLogTraceHelper
0x18002c032  mov     edi, 0C000000Dh
0x18002c037  mov     esi, edi
0x18002c039  mov     dword ptr [rsp+0F0h+var_C8], edi
0x18002c03d  mov     edx, 10Ah
0x18002c042  jmp     short loc_18002C081
0x18002c044  lea     rdx, [rbp+57h+var_A0]
0x18002c048  movzx   ecx, di
0x18002c04b  call    PpfEvtLogValidateDigestAlgIDAndGetSize
0x18002c050  mov     esi, eax
0x18002c052  test    eax, eax
0x18002c054  jns     short loc_18002C05D
0x18002c056  mov     edx, 100h
0x18002c05b  jmp     short loc_18002C07D
0x18002c05d  movzx   r15d, di
0x18002c061  mov     [rbp+57h+var_AC], di
0x18002c065  movzx   r14d, word ptr [rbp+57h+var_A0]
0x18002c06a  mov     [rbp+57h+var_B0], r14w
0x18002c06f  jmp     short loc_18002C0A6
0x18002c071  mov     eax, 0C000000Dh
0x18002c076  mov     esi, eax
0x18002c078  mov     edx, 0F4h; int
0x18002c07d  mov     dword ptr [rsp+0F0h+var_C8], eax; char
0x18002c081  lea     rax, aError0xX; "Error: 0x%x"
0x18002c088  mov     [rsp+0F0h+Format], rax; int
0x18002c08d  mov     r9d, 1; int
0x18002c093  lea     r8, aPpfevtloggetdi; "PpfEvtLogGetDigestIDAndSizeFromName"
0x18002c09a  lea     rcx, aMinkernelNgscb_1; "minkernel\\ngscb\\ppfevtlog\\ppfevtlog."...
0x18002c0a1  call    PpfEvtLogTraceHelper
0x18002c0a6  mov     rcx, [rbp+5Fh]
0x18002c0aa  test    esi, esi
0x18002c0ac  js      loc_18002C389
0x18002c0b2  mov     [rbp+57h+var_70], 0
0x18002c0ba  mov     rdi, [rbp+57h+var_88]
0x18002c0be  mov     rsi, [rdi]
0x18002c0c1  mov     [rbp+57h+string], 0
0x18002c0c9  lea     r9, [rbp+57h+string]; string
0x18002c0cd  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18002c0d1  mov     edx, 0Bh; length
0x18002c0d6  lea     rcx, aEventdigest_0; "EventDigest"
0x18002c0dd  call    cs:__imp_WindowsCreateStringReference
0x18002c0e4  nop     dword ptr [rax+rax+00h]
0x18002c0e9  test    eax, eax
0x18002c0eb  js      loc_18002C381
0x18002c0f1  lea     r8, [rbp+57h+var_70]
0x18002c0f5  mov     rdx, [rbp+57h+string]
0x18002c0f9  mov     rcx, rdi
0x18002c0fc  mov     rax, [rsi+50h]
0x18002c100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c105  mov     rcx, [rbp+5Fh]; this
0x18002c109  xor     esi, esi
0x18002c10b  test    eax, eax
0x18002c10d  js      loc_18002C370
0x18002c113  mov     [rbp+57h+lpMem], rsi
0x18002c117  mov     [rbp+57h+var_A0], esi
0x18002c11a  lea     rax, [rbp+57h+lpMem]
0x18002c11e  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x18002c122  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], rsi
0x18002c126  mov     byte ptr [rbp+57h+hstringHeader.Reserved+10h], 1
0x18002c12a  xor     edx, edx; length
0x18002c12c  mov     rcx, [rbp+57h+var_70]; string
0x18002c130  call    cs:__imp_WindowsGetStringRawBuffer
0x18002c137  nop     dword ptr [rax+rax+00h]
0x18002c13c  lea     r8, [rbp+57h+var_A0]; unsigned int *
0x18002c140  lea     rdx, [rbp+57h+hstringHeader.Reserved+8]; unsigned __int8 **
0x18002c144  mov     rcx, rax; unsigned __int16 *
0x18002c147  call    ?PpfhConvertHexStringToBytes@@YAJPEBGPEAPEAEPEAI@Z; PpfhConvertHexStringToBytes(ushort const *,uchar * *,uint *)
0x18002c14c  mov     rcx, [rbp+5Fh]; this
0x18002c150  test    eax, eax
0x18002c152  js      loc_18002C35F
0x18002c158  cmp     byte ptr [rbp+57h+hstringHeader.Reserved+10h], sil
0x18002c15c  jz      short loc_18002C191
0x18002c15e  mov     rcx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x18002c162  mov     rdi, [rcx]
0x18002c165  mov     rax, qword ptr [rbp+57h+hstringHeader.Reserved+8]
0x18002c169  mov     [rcx], rax
0x18002c16c  test    rdi, rdi
0x18002c16f  jz      short loc_18002C191
0x18002c171  call    cs:__imp_GetProcessHeap
0x18002c178  nop     dword ptr [rax+rax+00h]
0x18002c17d  mov     rcx, rax; hHeap
0x18002c180  mov     r8, rdi; lpMem
0x18002c183  xor     edx, edx; dwFlags
0x18002c185  call    cs:__imp_HeapFree
0x18002c18c  nop     dword ptr [rax+rax+00h]
0x18002c191  mov     eax, [rbp+57h+var_A0]
0x18002c194  movzx   edx, r14w
0x18002c198  cmp     eax, edx
0x18002c19a  setnz   r8b
0x18002c19e  mov     rcx, [rbp+5Fh]; this
0x18002c1a2  mov     dword ptr [rsp+0F0h+var_B8], eax
0x18002c1a6  mov     dword ptr [rsp+0F0h+var_C0], edx; char *
0x18002c1aa  lea     rax, aUnexpectedDige; "Unexpected digest size, expected: 0x%x "...
0x18002c1b1  mov     qword ptr [rsp+0F0h+var_C8], rax; bool
0x18002c1b6  mov     byte ptr [rsp+0F0h+Format], r8b; int
0x18002c1bb  mov     r9d, 80070057h; char *
0x18002c1c1  mov     r8, rbx; unsigned int
0x18002c1c4  mov     edx, 5B5h; void *
0x18002c1c9  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18002c1ce  mov     r8, [rbp+57h+lpMem]; unsigned __int8 *
0x18002c1d2  mov     qword ptr [rbp+57h+var_A0], r8
0x18002c1d6  mov     rax, [r13+8]
0x18002c1da  cmp     rax, [r13+10h]
0x18002c1de  jz      short loc_18002C1F7
0x18002c1e0  movzx   r9d, r14w; unsigned __int16
0x18002c1e4  movzx   edx, r15w; unsigned __int16
0x18002c1e8  mov     rcx, rax; this
0x18002c1eb  call    ??0PpfhEventLogDigest@@QEAA@GPEAEG@Z; PpfhEventLogDigest::PpfhEventLogDigest(ushort,uchar *,ushort)
0x18002c1f0  add     qword ptr [r13+8], 18h
0x18002c1f5  jmp     short loc_18002C214
0x18002c1f7  lea     rcx, [rbp+57h+var_B0]
0x18002c1fb  mov     [rsp+0F0h+Format], rcx
0x18002c200  lea     r9, [rbp+57h+var_A0]
0x18002c204  lea     r8, [rbp+57h+var_AC]
0x18002c208  mov     rdx, rax
0x18002c20b  mov     rcx, r13
0x18002c20e  call    ??$_Emplace_reallocate@AEAGAEAPEAEAEAG@?$vector@VPpfhEventLogDigest@@V?$allocator@VPpfhEventLogDigest@@@std@@@std@@AEAAPEAVPpfhEventLogDigest@@QEAV2@AEAGAEAPEAE1@Z; std::vector<PpfhEventLogDigest>::_Emplace_reallocate<ushort &,uchar * &,ushort &>(PpfhEventLogDigest * const,ushort &,uchar * &,ushort &)
0x18002c213  nop
0x18002c214  mov     rdi, [rbp+57h+lpMem]
0x18002c218  mov     [rbp+57h+lpMem], rsi
0x18002c21c  test    rdi, rdi
0x18002c21f  jz      short loc_18002C242
0x18002c221  call    cs:__imp_GetProcessHeap
0x18002c228  nop     dword ptr [rax+rax+00h]
0x18002c22d  mov     rcx, rax; hHeap
0x18002c230  mov     r8, rdi; lpMem
0x18002c233  xor     edx, edx; dwFlags
0x18002c235  call    cs:__imp_HeapFree
0x18002c23c  nop     dword ptr [rax+rax+00h]
0x18002c241  nop
0x18002c242  mov     rcx, [rbp+57h+var_70]; string
0x18002c246  test    rcx, rcx
0x18002c249  jz      short loc_18002C258
0x18002c24b  call    cs:__imp_WindowsDeleteString
0x18002c252  nop     dword ptr [rax+rax+00h]
0x18002c257  nop
0x18002c258  mov     rcx, [rbp+57h+var_68]; string
0x18002c25c  test    rcx, rcx
0x18002c25f  jz      short loc_18002C26E
0x18002c261  call    cs:__imp_WindowsDeleteString
0x18002c268  nop     dword ptr [rax+rax+00h]
0x18002c26d  nop
0x18002c26e  mov     rcx, [rbp+57h+var_88]
0x18002c272  test    rcx, rcx
0x18002c275  jz      short loc_18002C288
0x18002c277  mov     [rbp+57h+var_88], rsi
0x18002c27b  mov     rax, [rcx]
0x18002c27e  mov     rax, [rax+10h]
0x18002c282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002c287  nop
0x18002c288  mov     rcx, [rbp+57h+var_78]
0x18002c28c  test    rcx, rcx
0x18002c28f  jz      short loc_18002C2A2
0x18002c291  mov     [rbp+57h+var_78], rsi
0x18002c295  mov     rax, [rcx]
0x18002c298  mov     rax, [rax+10h]
0x18002c29c  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
