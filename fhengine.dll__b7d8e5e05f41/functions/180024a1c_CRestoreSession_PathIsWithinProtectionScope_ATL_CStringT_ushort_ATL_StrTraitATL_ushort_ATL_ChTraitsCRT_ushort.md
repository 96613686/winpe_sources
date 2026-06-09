# CRestoreSession::PathIsWithinProtectionScope(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)

- ea: `0x180024a1c`
- end: `0x180024b09`
- name: `?PathIsWithinProtectionScope@CRestoreSession@@AEAAHV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `237`
- prototype: `__int64 __fastcall(__int64, const wchar_t **)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800236d0`

## callees

- `0x1800062d0`
- `0x180009404`
- `0x1800236a4`
- `0x1800240d8`
- `0x180024a1c`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180024a7f`
- `msvcrt!_wcsnicmp` at `0x180024ad7`
- `msvcrt!_wcsnicmp` at `0x180024a7f`
- `msvcrt!_wcsnicmp` at `0x180024ad7`

## pseudocode

```c
__int64 __fastcall CRestoreSession::PathIsWithinProtectionScope(__int64 a1, const wchar_t **a2)
{
  __int64 v4; // rbp
  __int64 v5; // rax
  __int64 v6; // rcx
  __int64 StringInSortedList; // rax
  __int64 v8; // r14
  size_t v9; // rbx
  const wchar_t **v10; // rax
  __int64 v11; // rsi
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rbp
  size_t v16; // rbx
  const wchar_t **v17; // rax
  unsigned int v18; // ebx
  char v20; // [rsp+40h] [rbp+8h] BYREF

  v4 = a1 + 280;
  v5 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
         &v20,
         a2);
  StringInSortedList = CRestoreSession::FindStringInSortedList(v6, v4, v5);
  v8 = StringInSortedList;
  if ( StringInSortedList != -1 )
  {
    v9 = *(int *)(*(_QWORD *)ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::operator[](
                               v4,
                               StringInSortedList)
                - 16LL);
    v10 = (const wchar_t **)ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::operator[](
                              v4,
                              v8);
    if ( !_wcsnicmp(*a2, *v10, v9) )
      goto LABEL_6;
  }
  v11 = a1 + 248;
  v12 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          &v20,
          a2);
  v14 = CRestoreSession::FindStringInSortedList(v13, v11, v12);
  v15 = v14;
  if ( v14 == -1
    || (v16 = *(int *)(*(_QWORD *)ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::operator[](
                                    v11,
                                    v14)
                     - 16LL),
        v17 = (const wchar_t **)ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::operator[](
                                  v11,
                                  v15),
        _wcsnicmp(*a2, *v17, v16)) )
  {
LABEL_6:
    v18 = 0;
  }
  else
  {
    v18 = 1;
  }
  ATL::CStringData::Release((ATL::CStringData *)(*a2 - 12));
  return v18;
}

```

## disassembly

```asm
0x180024a1c  mov     [rsp+arg_8], rbx
0x180024a21  mov     [rsp+arg_10], rbp
0x180024a26  push    rsi
0x180024a27  push    rdi
0x180024a28  push    r14
0x180024a2a  sub     rsp, 20h
0x180024a2e  mov     rdi, rdx
0x180024a31  mov     rsi, rcx
0x180024a34  lea     rbp, [rcx+118h]
0x180024a3b  lea     rcx, [rsp+38h+arg_0]
0x180024a40  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180024a45  mov     r8, rax
0x180024a48  mov     rdx, rbp
0x180024a4b  call    ?FindStringInSortedList@CRestoreSession@@AEAA_KAEAV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z; CRestoreSession::FindStringInSortedList(ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)
0x180024a50  mov     r14, rax
0x180024a53  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180024a57  jz      short loc_180024A89
0x180024a59  mov     rdx, rax
0x180024a5c  mov     rcx, rbp
0x180024a5f  call    ??A?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@1@_K@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::operator[](unsigned __int64)
0x180024a64  mov     rdx, [rax]
0x180024a67  movsxd  rbx, dword ptr [rdx-10h]
0x180024a6b  mov     rdx, r14
0x180024a6e  mov     rcx, rbp
0x180024a71  call    ??A?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@1@_K@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::operator[](unsigned __int64)
0x180024a76  mov     r8, rbx; MaxCount
0x180024a79  mov     rdx, [rax]; String2
0x180024a7c  mov     rcx, [rdi]; String1
0x180024a7f  call    cs:__imp__wcsnicmp
0x180024a85  test    eax, eax
0x180024a87  jz      short loc_180024AE6
0x180024a89  add     rsi, 0F8h
0x180024a90  mov     rdx, rdi
0x180024a93  lea     rcx, [rsp+38h+arg_0]
0x180024a98  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180024a9d  mov     r8, rax
0x180024aa0  mov     rdx, rsi
0x180024aa3  call    ?FindStringInSortedList@CRestoreSession@@AEAA_KAEAV?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z; CRestoreSession::FindStringInSortedList(ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>)
0x180024aa8  mov     rbp, rax
0x180024aab  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180024aaf  jz      short loc_180024AE6
0x180024ab1  mov     rdx, rax
0x180024ab4  mov     rcx, rsi
0x180024ab7  call    ??A?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@1@_K@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::operator[](unsigned __int64)
0x180024abc  mov     rdx, [rax]
0x180024abf  movsxd  rbx, dword ptr [rdx-10h]
0x180024ac3  mov     rdx, rbp
0x180024ac6  mov     rcx, rsi
0x180024ac9  call    ??A?$CAtlArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@1@_K@Z; ATL::CAtlArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::operator[](unsigned __int64)
0x180024ace  mov     r8, rbx; MaxCount
0x180024ad1  mov     rdx, [rax]; String2
0x180024ad4  mov     rcx, [rdi]; String1
0x180024ad7  call    cs:__imp__wcsnicmp
0x180024add  test    eax, eax
0x180024adf  jnz     short loc_180024AE6
0x180024ae1  lea     ebx, [rax+1]
0x180024ae4  jmp     short loc_180024AE8
0x180024ae6  xor     ebx, ebx
0x180024ae8  mov     rcx, [rdi]
0x180024aeb  sub     rcx, 18h; this
0x180024aef  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180024af4  mov     eax, ebx
0x180024af6  mov     rbx, [rsp+38h+arg_8]
0x180024afb  mov     rbp, [rsp+38h+arg_10]
0x180024b00  add     rsp, 20h
0x180024b04  pop     r14
0x180024b06  pop     rdi
0x180024b07  pop     rsi
0x180024b08  retn
```
