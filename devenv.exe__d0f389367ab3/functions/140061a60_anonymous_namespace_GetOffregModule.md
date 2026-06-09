# _anonymous_namespace_::GetOffregModule

- ea: `0x140061a60`
- end: `0x140061b92`
- name: `_anonymous_namespace_::GetOffregModule`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x140061b94`

## callees

- `0x140001020`
- `0x140003160`
- `0x140009b10`
- `0x140022db0`
- `0x140061a60`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x140061a90`
- `KERNEL32!LoadLibraryW` at `0x140061b30`
- `KERNEL32!LoadLibraryW` at `0x140061a90`
- `KERNEL32!LoadLibraryW` at `0x140061b30`
- `KERNEL32!GetModuleHandleExW` at `0x140061aba`
- `KERNEL32!GetModuleHandleExW` at `0x140061aba`
- `KERNEL32!GetModuleFileNameW` at `0x140061ade`
- `KERNEL32!GetModuleFileNameW` at `0x140061ade`
- `KERNEL32!GetLastError` at `0x140061ae8`
- `KERNEL32!GetLastError` at `0x140061ae8`

## string_xrefs

- `0x140061a89`: `offreg.dll`
- `0x140061b16`: `offreg.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
DWORD anonymous_namespace_::GetOffregModule()
{
  int v1; // ebx
  LPCWSTR v2; // rdx
  LPCWSTR lpLibFileName; // [rsp+20h] [rbp-238h] BYREF
  HMODULE phModule; // [rsp+28h] [rbp-230h] BYREF
  WCHAR Filename[264]; // [rsp+30h] [rbp-228h] BYREF

  if ( qword_14009F1F0 )
    return 0;
  qword_14009F1F0 = LoadLibraryW(L"offreg.dll");
  if ( qword_14009F1F0 )
    return 0;
  phModule = 0;
  if ( !GetModuleHandleExW(6u, (LPCWSTR)anonymous_namespace_::GetOffregModule, &phModule) )
    return 126;
  if ( !GetModuleFileNameW(phModule, Filename, 0x104u) )
    return GetLastError();
  lpLibFileName = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &lpLibFileName,
    Filename);
  if ( (unsigned int)ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::RemoveFileSpec(&lpLibFileName)
    && (unsigned int)ATL::CPathT<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::Append(
                       &lpLibFileName,
                       L"offreg.dll") )
  {
    qword_14009F1F0 = LoadLibraryW(lpLibFileName);
    if ( qword_14009F1F0 )
      v1 = 0;
    else
      v1 = 126;
  }
  else
  {
    v1 = 14;
  }
  v2 = lpLibFileName - 12;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpLibFileName - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v2 + 8LL))(*(_QWORD *)v2);
  }
  return v1;
}

```

## disassembly

```asm
0x140061a60  push    rbx
0x140061a62  sub     rsp, 250h
0x140061a69  mov     rax, cs:__security_cookie
0x140061a70  xor     rax, rsp
0x140061a73  mov     [rsp+258h+var_18], rax
0x140061a7b  cmp     cs:qword_14009F1F0, 0
0x140061a83  jnz     loc_140061B77
0x140061a89  lea     rcx, aOffregDll; "offreg.dll"
0x140061a90  call    cs:__imp_LoadLibraryW
0x140061a96  mov     cs:qword_14009F1F0, rax
0x140061a9d  test    rax, rax
0x140061aa0  jnz     loc_140061B77
0x140061aa6  and     [rsp+258h+phModule], rax
0x140061aab  lea     r8, [rsp+258h+phModule]; phModule
0x140061ab0  lea     rdx, _anonymous_namespace___GetOffregModule; lpModuleName
0x140061ab7  lea     ecx, [rax+6]; dwFlags
0x140061aba  call    cs:__imp_GetModuleHandleExW
0x140061ac0  test    eax, eax
0x140061ac2  jnz     short loc_140061ACE
0x140061ac4  mov     eax, 7Eh ; '~'
0x140061ac9  jmp     loc_140061B79
0x140061ace  mov     r8d, 104h; nSize
0x140061ad4  lea     rdx, [rsp+258h+Filename]; lpFilename
0x140061ad9  mov     rcx, [rsp+258h+phModule]; hModule
0x140061ade  call    cs:__imp_GetModuleFileNameW
0x140061ae4  test    eax, eax
0x140061ae6  jnz     short loc_140061AF3
0x140061ae8  call    cs:__imp_GetLastError
0x140061aee  jmp     loc_140061B79
0x140061af3  and     [rsp+258h+lpLibFileName], 0
0x140061af9  lea     rdx, [rsp+258h+Filename]
0x140061afe  lea     rcx, [rsp+258h+lpLibFileName]
0x140061b03  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x140061b08  lea     rcx, [rsp+258h+lpLibFileName]
0x140061b0d  call    ?RemoveFileSpec@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAHXZ; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::RemoveFileSpec(void)
0x140061b12  test    eax, eax
0x140061b14  jz      short loc_140061B4B
0x140061b16  lea     rdx, aOffregDll; "offreg.dll"
0x140061b1d  lea     rcx, [rsp+258h+lpLibFileName]
0x140061b22  call    ?Append@?$CPathT@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CPathT<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::Append(ushort const *)
0x140061b27  test    eax, eax
0x140061b29  jz      short loc_140061B4B
0x140061b2b  mov     rcx, [rsp+258h+lpLibFileName]; lpLibFileName
0x140061b30  call    cs:__imp_LoadLibraryW
0x140061b36  mov     cs:qword_14009F1F0, rax
0x140061b3d  test    rax, rax
0x140061b40  jnz     short loc_140061B47
0x140061b42  lea     ebx, [rax+7Eh]
0x140061b45  jmp     short loc_140061B50
0x140061b47  xor     ebx, ebx
0x140061b49  jmp     short loc_140061B50
0x140061b4b  mov     ebx, 0Eh
0x140061b50  mov     rdx, [rsp+258h+lpLibFileName]
0x140061b55  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140061b59  or      ecx, 0FFFFFFFFh
0x140061b5c  lock xadd [rdx+10h], ecx
0x140061b61  sub     ecx, 1
0x140061b64  jg      short loc_140061B73
0x140061b66  lfence
0x140061b69  mov     rcx, [rdx]
0x140061b6c  mov     r8, [rcx]
0x140061b6f  call    qword ptr [r8+8]
0x140061b73  mov     eax, ebx
0x140061b75  jmp     short loc_140061B79
0x140061b77  xor     eax, eax
0x140061b79  mov     rcx, [rsp+258h+var_18]
0x140061b81  xor     rcx, rsp; StackCookie
0x140061b84  call    __security_check_cookie
0x140061b89  add     rsp, 250h
0x140061b90  pop     rbx
0x140061b91  retn
```
