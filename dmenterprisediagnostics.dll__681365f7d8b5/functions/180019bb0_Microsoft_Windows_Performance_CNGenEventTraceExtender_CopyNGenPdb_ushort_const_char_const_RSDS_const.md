# Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(ushort const *,char const *,_RSDS const &)

- ea: `0x180019bb0`
- end: `0x180019d46`
- name: `?CopyNGenPdb@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAJPEBGPEBDAEBU_RSDS@@@Z`
- size: `406`
- prototype: `int(Microsoft::Windows::Performance::CNGenEventTraceExtender *__hidden this, const unsigned __int16 *, const char *, const struct _RSDS *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001a090`

## callees

- `0x180009d08`
- `0x180009e70`
- `0x180009e98`
- `0x18000c6e4`
- `0x1800110b4`
- `0x180014380`
- `0x1800194c8`
- `0x180019bb0`
- `0x18001a2c4`
- `0x18001b12c`
- `0x18001b2ac`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180019be2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180019c29`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180019c71`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180019be2`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180019c29`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180019c71`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180019cdd`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180019cdd`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::Windows::Performance::CNGenEventTraceExtender::CopyNGenPdb(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *this,
        const unsigned __int16 *a2,
        const char *a3,
        const struct _RSDS *a4)
{
  _QWORD *v7; // r14
  const WCHAR *v8; // rbx
  unsigned int v9; // edi
  int v10; // ecx
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rcx
  unsigned int Error; // eax
  __int64 v15; // rcx
  LPCWSTR lpPathName; // [rsp+70h] [rbp+8h] BYREF

  v7 = (_QWORD *)((char *)this + 56);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &lpPathName,
    (char *)this + 56);
  v8 = lpPathName;
  if ( CreateDirectoryW(lpPathName, 0)
    || (v9 = ATL::AtlHresultFromLastError(), v9 == (unsigned int)ATL::AtlHresultFromWin32(0xB7u)) )
  {
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::AppendFormat(
      &lpPathName,
      L"\\%hs",
      a3);
    v8 = lpPathName;
    if ( CreateDirectoryW(lpPathName, 0)
      || (v9 = ATL::AtlHresultFromLastError(), v9 == (unsigned int)ATL::AtlHresultFromWin32(0xB7u)) )
    {
      Microsoft::Windows::Performance::CNGenEventTraceExtender::CreatePathToPdbFromStoreRoot(
        v10,
        (unsigned int)&lpPathName,
        *v7,
        (_DWORD)a3,
        (__int64)a4);
      v8 = lpPathName;
      if ( CreateDirectoryW(lpPathName, 0)
        || (v9 = ATL::AtlHresultFromLastError(), v9 == (unsigned int)ATL::AtlHresultFromWin32(0xB7u)) )
      {
        ATL::CSimpleStringT<unsigned short,0>::Append(&lpPathName, L"\\");
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator+=(
          &lpPathName,
          a3);
        v8 = lpPathName;
        if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
          McTemplateU0zz_EventWriteTransfer(v12, v11, a2, lpPathName);
        if ( CopyFileW(a2, v8, 0) )
        {
          if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
            McTemplateU0q_EventWriteTransfer(v13, TraceMerge_NGEN_CopyingPDB_Stop, 0);
          v9 = 0;
        }
        else
        {
          if ( (Microsoft_Windows_XPerfCoreEnableBits & 1) != 0 )
          {
            Error = ATL::AtlHresultFromLastError();
            McTemplateU0q_EventWriteTransfer(v15, TraceMerge_NGEN_CopyingPDB_Stop, Error);
          }
          v9 = ATL::AtlHresultFromLastError();
        }
      }
    }
  }
  ATL::CStringData::Release((ATL::CStringData *)(v8 - 12));
  return v9;
}

```

## disassembly

```asm
0x180019bb0  push    rbx
0x180019bb2  push    rbp
0x180019bb3  push    rsi
0x180019bb4  push    rdi
0x180019bb5  push    r14
0x180019bb7  push    r15
0x180019bb9  sub     rsp, 38h
0x180019bbd  mov     r15, r9
0x180019bc0  mov     rsi, r8
0x180019bc3  mov     rbp, rdx
0x180019bc6  lea     r14, [rcx+38h]
0x180019bca  mov     rdx, r14
0x180019bcd  lea     rcx, [rsp+68h+lpPathName]
0x180019bd2  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180019bd7  nop
0x180019bd8  xor     edx, edx; lpSecurityAttributes
0x180019bda  mov     rbx, [rsp+68h+lpPathName]
0x180019bdf  mov     rcx, rbx; lpPathName
0x180019be2  call    cs:__imp_CreateDirectoryW
0x180019be9  nop     dword ptr [rax+rax+00h]
0x180019bee  test    eax, eax
0x180019bf0  jnz     short loc_180019C0B
0x180019bf2  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180019bf7  mov     edi, eax
0x180019bf9  mov     ecx, 0B7h; unsigned int
0x180019bfe  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180019c03  cmp     edi, eax
0x180019c05  jnz     loc_180019D2D
0x180019c0b  mov     r8, rsi
0x180019c0e  lea     rdx, aHs_0; "\\%hs"
0x180019c15  lea     rcx, [rsp+68h+lpPathName]
0x180019c1a  call    ?AppendFormat@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAXPEBGZZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::AppendFormat(ushort const *,...)
0x180019c1f  xor     edx, edx; lpSecurityAttributes
0x180019c21  mov     rbx, [rsp+68h+lpPathName]
0x180019c26  mov     rcx, rbx; lpPathName
0x180019c29  call    cs:__imp_CreateDirectoryW
0x180019c30  nop     dword ptr [rax+rax+00h]
0x180019c35  test    eax, eax
0x180019c37  jnz     short loc_180019C52
0x180019c39  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180019c3e  mov     edi, eax
0x180019c40  mov     ecx, 0B7h; unsigned int
0x180019c45  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180019c4a  cmp     edi, eax
0x180019c4c  jnz     loc_180019D2D
0x180019c52  mov     [rsp+68h+var_48], r15
0x180019c57  mov     r9, rsi
0x180019c5a  mov     r8, [r14]
0x180019c5d  lea     rdx, [rsp+68h+lpPathName]
0x180019c62  call    ?CreatePathToPdbFromStoreRoot@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBAXAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEBDAEBU_RSDS@@@Z; Microsoft::Windows::Performance::CNGenEventTraceExtender::CreatePathToPdbFromStoreRoot(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,char const *,_RSDS const &)
0x180019c67  xor     edx, edx; lpSecurityAttributes
0x180019c69  mov     rbx, [rsp+68h+lpPathName]
0x180019c6e  mov     rcx, rbx; lpPathName
0x180019c71  call    cs:__imp_CreateDirectoryW
0x180019c78  nop     dword ptr [rax+rax+00h]
0x180019c7d  test    eax, eax
0x180019c7f  jnz     short loc_180019C9A
0x180019c81  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180019c86  mov     edi, eax
0x180019c88  mov     ecx, 0B7h; unsigned int
0x180019c8d  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180019c92  cmp     edi, eax
0x180019c94  jnz     loc_180019D2D
0x180019c9a  lea     rdx, asc_18002A930; "\\"
0x180019ca1  lea     rcx, [rsp+68h+lpPathName]
0x180019ca6  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x180019cab  mov     rdx, rsi
0x180019cae  lea     rcx, [rsp+68h+lpPathName]
0x180019cb3  call    ??Y?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator+=(char const *)
0x180019cb8  mov     rbx, [rsp+68h+lpPathName]
0x180019cbd  mov     dil, 1
0x180019cc0  test    cs:Microsoft_Windows_XPerfCoreEnableBits, dil
0x180019cc7  jz      short loc_180019CD4
0x180019cc9  mov     r9, rbx
0x180019ccc  mov     r8, rbp
0x180019ccf  call    McTemplateU0zz_EventWriteTransfer
0x180019cd4  xor     r8d, r8d; bFailIfExists
0x180019cd7  mov     rdx, rbx; lpNewFileName
0x180019cda  mov     rcx, rbp; lpExistingFileName
0x180019cdd  call    cs:__imp_CopyFileW
0x180019ce4  nop     dword ptr [rax+rax+00h]
0x180019ce9  test    eax, eax
0x180019ceb  jnz     short loc_180019D13
0x180019ced  test    cs:Microsoft_Windows_XPerfCoreEnableBits, dil
0x180019cf4  jz      short loc_180019D0A
0x180019cf6  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180019cfb  mov     r8d, eax
0x180019cfe  lea     rdx, TraceMerge_NGEN_CopyingPDB_Stop
0x180019d05  call    McTemplateU0q_EventWriteTransfer
0x180019d0a  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180019d0f  mov     edi, eax
0x180019d11  jmp     short loc_180019D2D
0x180019d13  test    cs:Microsoft_Windows_XPerfCoreEnableBits, dil
0x180019d1a  jz      short loc_180019D2B
0x180019d1c  xor     r8d, r8d
0x180019d1f  lea     rdx, TraceMerge_NGEN_CopyingPDB_Stop
0x180019d26  call    McTemplateU0q_EventWriteTransfer
0x180019d2b  xor     edi, edi
0x180019d2d  lea     rcx, [rbx-18h]; this
0x180019d31  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180019d36  mov     eax, edi
0x180019d38  add     rsp, 38h
0x180019d3c  pop     r15
0x180019d3e  pop     r14
0x180019d40  pop     rdi
0x180019d41  pop     rsi
0x180019d42  pop     rbp
0x180019d43  pop     rbx
0x180019d44  retn
```
