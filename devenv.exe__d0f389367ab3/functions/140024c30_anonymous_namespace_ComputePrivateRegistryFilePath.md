# _anonymous_namespace_::ComputePrivateRegistryFilePath

- ea: `0x140024c30`
- end: `0x140024e41`
- name: `_anonymous_namespace_::ComputePrivateRegistryFilePath`
- size: `529`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1400249e0`

## callees

- `0x140003160`
- `0x140004950`
- `0x140008120`
- `0x140009fb0`
- `0x140022db0`
- `0x140024c30`
- `0x140024e44`
- `0x1400618d0`

## import_xrefs

- `KERNEL32!CreateDirectoryW` at `0x140024d30`
- `KERNEL32!CreateDirectoryW` at `0x140024d30`
- `KERNEL32!GetLastError` at `0x140024d3a`
- `KERNEL32!GetLastError` at `0x140024d3a`
- `SHLWAPI!PathFileExistsW` at `0x140024cc2`
- `SHLWAPI!PathFileExistsW` at `0x140024dca`
- `SHLWAPI!PathFileExistsW` at `0x140024cc2`
- `SHLWAPI!PathFileExistsW` at `0x140024dca`

## string_xrefs

- `0x140024d9f`: `privateregistry.bin`
- `0x140024e29`: `privateregistry.user.bin`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall anonymous_namespace_::ComputePrivateRegistryFilePath(LPCWSTR lpPathName, LPCWSTR *a2, char a3)
{
  LPCWSTR v6; // rdx
  unsigned int v7; // ebx
  LPCWSTR v9; // rdx
  signed int LastError; // eax
  LPCWSTR v11; // rdx
  unsigned int v12; // ecx
  LPCWSTR v13; // rdx
  LPCWSTR lpPathNamea; // [rsp+40h] [rbp+20h] BYREF

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &lpPathNamea,
    &WindowName);
  ATL::CSimpleStringT<unsigned short,0>::operator=(a2, &lpPathNamea);
  v6 = lpPathNamea - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)lpPathNamea - 2) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v6 + 8LL))(*(_QWORD *)v6);
  }
  if ( !lpPathName )
  {
    v7 = -2147024809;
LABEL_5:
    _mm_lfence();
    return v7;
  }
  if ( PathFileExistsW(lpPathName) )
  {
    v7 = 0;
    goto LABEL_22;
  }
  lpPathNamea = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &lpPathNamea,
    lpPathName);
  if ( !(unsigned int)ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::RemoveFileSpec(&lpPathNamea) )
  {
    v9 = lpPathNamea - 12;
    if ( _InterlockedDecrement((volatile signed __int32 *)lpPathNamea - 2) <= 0 )
    {
      _mm_lfence();
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v9 + 8LL))(*(_QWORD *)v9);
    }
    v7 = -2147024882;
    goto LABEL_5;
  }
  v7 = anonymous_namespace_::EnsureDirectoryExists(lpPathNamea);
  if ( v7 || CreateDirectoryW(lpPathName, 0) )
  {
    v11 = lpPathNamea - 12;
    if ( _InterlockedDecrement((volatile signed __int32 *)lpPathNamea - 2) > 0 )
      goto LABEL_21;
    goto LABEL_20;
  }
  LastError = GetLastError();
  v7 = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    v7 = LastError;
  v11 = lpPathNamea - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)lpPathNamea - 2) <= 0 )
  {
LABEL_20:
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v11 + 8LL))(*(_QWORD *)v11);
  }
LABEL_21:
  if ( (v7 & 0x80000000) != 0 )
    goto LABEL_5;
LABEL_22:
  ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::Combine(
    a2,
    lpPathName,
    L"privateregistry.bin");
  if ( !a3 || IsWindows8OrGreater() || PathFileExistsW(*a2) || (unsigned int)IsUserInGroupRID(v12) )
    goto LABEL_5;
  _mm_lfence();
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &lpPathNamea,
    &WindowName);
  ATL::CSimpleStringT<unsigned short,0>::operator=(a2, &lpPathNamea);
  v13 = lpPathNamea - 12;
  if ( _InterlockedDecrement((volatile signed __int32 *)lpPathNamea - 2) <= 0 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v13 + 8LL))(*(_QWORD *)v13);
  }
  ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::Combine(
    a2,
    lpPathName,
    L"privateregistry.user.bin");
  return v7;
}

```

## disassembly

```asm
0x140024c30  mov     [rsp-18h+arg_8], rbx
0x140024c35  mov     [rsp-18h+arg_10], rsi
0x140024c3a  mov     [rsp-18h+arg_18], rdi
0x140024c3f  push    rbp
0x140024c40  push    r14
0x140024c42  push    r15
0x140024c44  mov     rbp, rsp
0x140024c47  sub     rsp, 20h
0x140024c4b  mov     r14b, r8b
0x140024c4e  mov     rsi, rdx
0x140024c51  mov     rdi, rcx
0x140024c54  lea     rdx, WindowName
0x140024c5b  lea     rcx, [rbp+lpPathName]
0x140024c5f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140024c64  lea     rdx, [rbp+lpPathName]
0x140024c68  mov     rcx, rsi
0x140024c6b  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140024c70  mov     rdx, [rbp+lpPathName]
0x140024c74  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140024c78  or      r15d, 0FFFFFFFFh
0x140024c7c  mov     eax, r15d
0x140024c7f  lock xadd [rdx+10h], eax
0x140024c84  add     eax, r15d
0x140024c87  test    eax, eax
0x140024c89  jg      short loc_140024C97
0x140024c8b  lfence
0x140024c8e  mov     rcx, [rdx]
0x140024c91  mov     rax, [rcx]
0x140024c94  call    qword ptr [rax+8]
0x140024c97  test    rdi, rdi
0x140024c9a  jnz     short loc_140024CBF
0x140024c9c  mov     ebx, 80070057h
0x140024ca1  lfence
0x140024ca4  mov     eax, ebx
0x140024ca6  mov     rbx, [rsp+20h+arg_8]
0x140024cab  mov     rsi, [rsp+20h+arg_10]
0x140024cb0  mov     rdi, [rsp+20h+arg_18]
0x140024cb5  add     rsp, 20h
0x140024cb9  pop     r15
0x140024cbb  pop     r14
0x140024cbd  pop     rbp
0x140024cbe  retn
0x140024cbf  mov     rcx, rdi; pszPath
0x140024cc2  call    cs:__imp_PathFileExistsW
0x140024cc8  test    eax, eax
0x140024cca  jz      short loc_140024CD3
0x140024ccc  xor     ebx, ebx
0x140024cce  jmp     loc_140024D9F
0x140024cd3  and     [rbp+lpPathName], 0
0x140024cd8  mov     rdx, rdi
0x140024cdb  lea     rcx, [rbp+lpPathName]
0x140024cdf  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140024ce4  nop
0x140024ce5  lea     rcx, [rbp+lpPathName]
0x140024ce9  call    ?RemoveFileSpec@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAHXZ; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::RemoveFileSpec(void)
0x140024cee  test    eax, eax
0x140024cf0  jnz     short loc_140024D1C
0x140024cf2  mov     rdx, [rbp+lpPathName]
0x140024cf6  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140024cfa  mov     eax, r15d
0x140024cfd  lock xadd [rdx+10h], eax
0x140024d02  add     eax, r15d
0x140024d05  test    eax, eax
0x140024d07  jg      short loc_140024D15
0x140024d09  lfence
0x140024d0c  mov     rcx, [rdx]
0x140024d0f  mov     rax, [rcx]
0x140024d12  call    qword ptr [rax+8]
0x140024d15  mov     ebx, 8007000Eh
0x140024d1a  jmp     short loc_140024CA1
0x140024d1c  mov     rcx, [rbp+lpPathName]; lpPathName
0x140024d20  call    _anonymous_namespace___EnsureDirectoryExists
0x140024d25  mov     ebx, eax
0x140024d27  test    eax, eax
0x140024d29  jnz     short loc_140024D73
0x140024d2b  xor     edx, edx; lpSecurityAttributes
0x140024d2d  mov     rcx, rdi; lpPathName
0x140024d30  call    cs:__imp_CreateDirectoryW
0x140024d36  test    eax, eax
0x140024d38  jnz     short loc_140024D73
0x140024d3a  call    cs:__imp_GetLastError
0x140024d40  movzx   ebx, ax
0x140024d43  or      ebx, 80070000h
0x140024d49  test    eax, eax
0x140024d4b  cmovle  ebx, eax
0x140024d4e  mov     rdx, [rbp+lpPathName]
0x140024d52  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140024d56  mov     eax, r15d
0x140024d59  lock xadd [rdx+10h], eax
0x140024d5e  add     eax, r15d
0x140024d61  test    eax, eax
0x140024d63  jg      short loc_140024D97
0x140024d65  lfence
0x140024d68  mov     rcx, [rdx]
0x140024d6b  mov     rax, [rcx]
0x140024d6e  call    qword ptr [rax+8]
0x140024d71  jmp     short loc_140024D97
0x140024d73  mov     rdx, [rbp+lpPathName]
0x140024d77  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140024d7b  mov     eax, r15d
0x140024d7e  lock xadd [rdx+10h], eax
0x140024d83  add     eax, r15d
0x140024d86  test    eax, eax
0x140024d88  jg      short loc_140024D97
0x140024d8a  lfence
0x140024d8d  mov     rcx, [rdx]
0x140024d90  mov     r8, [rcx]
0x140024d93  call    qword ptr [r8+8]
0x140024d97  test    ebx, ebx
0x140024d99  js      loc_140024CA1
0x140024d9f  lea     r8, aPrivateregistr_1; "privateregistry.bin"
0x140024da6  mov     rdx, rdi
0x140024da9  mov     rcx, rsi
0x140024dac  call    ?Combine@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAXPEBG0@Z; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::Combine(ushort const *,ushort const *)
0x140024db1  test    r14b, r14b
0x140024db4  jz      loc_140024CA1
0x140024dba  call    ?IsWindows8OrGreater@@YA_NXZ; IsWindows8OrGreater(void)
0x140024dbf  test    al, al
0x140024dc1  jnz     loc_140024CA1
0x140024dc7  mov     rcx, [rsi]; pszPath
0x140024dca  call    cs:__imp_PathFileExistsW
0x140024dd0  test    eax, eax
0x140024dd2  jnz     loc_140024CA1
0x140024dd8  call    ?IsUserInGroupRID@@YAHK@Z; IsUserInGroupRID(ulong)
0x140024ddd  test    eax, eax
0x140024ddf  jnz     loc_140024CA1
0x140024de5  lfence
0x140024de8  lea     rdx, WindowName
0x140024def  lea     rcx, [rbp+lpPathName]
0x140024df3  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140024df8  nop
0x140024df9  lea     rdx, [rbp+lpPathName]
0x140024dfd  mov     rcx, rsi
0x140024e00  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x140024e05  nop
0x140024e06  mov     rdx, [rbp+lpPathName]
0x140024e0a  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140024e0e  mov     eax, r15d
0x140024e11  lock xadd [rdx+10h], eax
0x140024e16  add     eax, r15d
0x140024e19  test    eax, eax
0x140024e1b  jg      short loc_140024E29
0x140024e1d  lfence
0x140024e20  mov     rcx, [rdx]
0x140024e23  mov     rax, [rcx]
0x140024e26  call    qword ptr [rax+8]
0x140024e29  lea     r8, aPrivateregistr; "privateregistry.user.bin"
0x140024e30  mov     rdx, rdi
0x140024e33  mov     rcx, rsi
0x140024e36  call    ?Combine@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAXPEBG0@Z; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::Combine(ushort const *,ushort const *)
0x140024e3b  jmp     loc_140024CA4
```
