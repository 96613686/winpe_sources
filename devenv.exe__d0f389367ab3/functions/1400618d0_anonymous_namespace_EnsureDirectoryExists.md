# _anonymous_namespace_::EnsureDirectoryExists

- ea: `0x1400618d0`
- end: `0x140061988`
- name: `_anonymous_namespace_::EnsureDirectoryExists`
- size: `184`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140024c30`
- `0x1400618d0`

## callees

- `0x140003160`
- `0x140022db0`
- `0x1400618d0`

## import_xrefs

- `KERNEL32!CreateDirectoryW` at `0x14006193a`
- `KERNEL32!CreateDirectoryW` at `0x14006193a`
- `KERNEL32!GetLastError` at `0x140061944`
- `KERNEL32!GetLastError` at `0x140061944`
- `SHLWAPI!PathFileExistsW` at `0x1400618ec`
- `SHLWAPI!PathFileExistsW` at `0x1400618ec`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall anonymous_namespace_::EnsureDirectoryExists(LPCWSTR lpPathName)
{
  unsigned int v3; // ebx
  signed int LastError; // eax
  LPCWSTR v5; // rdx
  LPCWSTR lpPathNamea; // [rsp+30h] [rbp+8h] BYREF

  if ( !lpPathName )
    return 2147942487LL;
  if ( PathFileExistsW(lpPathName) )
    return 0;
  lpPathNamea = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &lpPathNamea,
    lpPathName);
  if ( (unsigned int)ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::RemoveFileSpec(&lpPathNamea) )
  {
    v3 = anonymous_namespace_::EnsureDirectoryExists(lpPathNamea);
    if ( !v3 && !CreateDirectoryW(lpPathName, 0) )
    {
      LastError = GetLastError();
      v3 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v3 = LastError;
    }
  }
  else
  {
    v3 = -2147024882;
  }
  v5 = lpPathNamea - 12;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpPathNamea - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v5 + 8LL))(*(_QWORD *)v5);
  }
  return v3;
}

```

## disassembly

```asm
0x1400618d0  mov     [rsp+arg_8], rbx
0x1400618d5  push    rdi
0x1400618d6  sub     rsp, 20h
0x1400618da  mov     rdi, rcx
0x1400618dd  test    rcx, rcx
0x1400618e0  jnz     short loc_1400618EC
0x1400618e2  mov     eax, 80070057h
0x1400618e7  jmp     loc_14006197D
0x1400618ec  call    cs:__imp_PathFileExistsW
0x1400618f2  test    eax, eax
0x1400618f4  jz      short loc_1400618FD
0x1400618f6  xor     eax, eax
0x1400618f8  jmp     loc_14006197D
0x1400618fd  and     [rsp+28h+lpPathName], 0
0x140061903  mov     rdx, rdi
0x140061906  lea     rcx, [rsp+28h+lpPathName]
0x14006190b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140061910  lea     rcx, [rsp+28h+lpPathName]
0x140061915  call    ?RemoveFileSpec@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAHXZ; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::RemoveFileSpec(void)
0x14006191a  test    eax, eax
0x14006191c  jnz     short loc_140061925
0x14006191e  mov     ebx, 8007000Eh
0x140061923  jmp     short loc_140061958
0x140061925  mov     rcx, [rsp+28h+lpPathName]; lpPathName
0x14006192a  call    _anonymous_namespace___EnsureDirectoryExists
0x14006192f  mov     ebx, eax
0x140061931  test    eax, eax
0x140061933  jnz     short loc_140061958
0x140061935  xor     edx, edx; lpSecurityAttributes
0x140061937  mov     rcx, rdi; lpPathName
0x14006193a  call    cs:__imp_CreateDirectoryW
0x140061940  test    eax, eax
0x140061942  jnz     short loc_140061958
0x140061944  call    cs:__imp_GetLastError
0x14006194a  movzx   ebx, ax
0x14006194d  or      ebx, 80070000h
0x140061953  test    eax, eax
0x140061955  cmovle  ebx, eax
0x140061958  mov     rdx, [rsp+28h+lpPathName]
0x14006195d  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140061961  or      ecx, 0FFFFFFFFh
0x140061964  lock xadd [rdx+10h], ecx
0x140061969  sub     ecx, 1
0x14006196c  jg      short loc_14006197B
0x14006196e  lfence
0x140061971  mov     rcx, [rdx]
0x140061974  mov     r8, [rcx]
0x140061977  call    qword ptr [r8+8]
0x14006197b  mov     eax, ebx
0x14006197d  mov     rbx, [rsp+28h+arg_8]
0x140061982  add     rsp, 20h
0x140061986  pop     rdi
0x140061987  retn
```
