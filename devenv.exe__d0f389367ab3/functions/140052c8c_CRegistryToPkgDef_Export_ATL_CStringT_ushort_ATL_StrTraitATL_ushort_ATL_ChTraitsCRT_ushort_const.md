# CRegistryToPkgDef::Export(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x140052c8c`
- end: `0x140052e59`
- name: `?Export@CRegistryToPkgDef@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `461`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14004c05c`
- `0x140052c8c`

## callees

- `0x140001020`
- `0x14001c380`
- `0x140052c8c`
- `0x140052e5c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140052e2b`
- `ADVAPI32!RegCloseKey` at `0x140052e2b`
- `ADVAPI32!RegOpenKeyExW` at `0x140052ce4`
- `ADVAPI32!RegOpenKeyExW` at `0x140052ce4`
- `ADVAPI32!RegEnumKeyExW` at `0x140052d64`
- `ADVAPI32!RegEnumKeyExW` at `0x140052d64`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CRegistryToPkgDef::Export(__int64 a1, LPCWSTR *a2)
{
  LSTATUS v4; // eax
  signed int v5; // ebx
  DWORD i; // edi
  __int64 v7; // rax
  _QWORD *v8; // rdx
  _QWORD *v9; // rdx
  __int64 v11; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  DWORD v13; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v14; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cchName[4]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[256]; // [rsp+70h] [rbp-90h] BYREF

  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v4 = RegOpenKeyExW(*(HKEY *)(a1 + 152), *a2, 0, 0x20019u, &hKey);
  v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v4 <= 0 )
    v5 = v4;
  if ( v5 >= 0 )
  {
    v13 = 0;
    v5 = CRegistryToPkgDef::ShallowExport(a1, hKey, a2, &v13);
    if ( v5 >= 0 )
    {
      _mm_lfence();
      for ( i = 0; i < v13; ++i )
      {
        cchName[0] = 255;
        if ( !RegEnumKeyExW(hKey, i, Name, cchName, 0, 0, 0, 0) )
        {
          v14 = 0;
          v7 = ATL::operator+(&v11, a2, L"\\");
          ATL::operator+(&v14, v7, Name);
          v8 = (_QWORD *)(v11 - 24);
          if ( _InterlockedDecrement((volatile signed __int32 *)(v11 - 24 + 16)) <= 0 )
          {
            _mm_lfence();
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 8LL))(*v8);
          }
          v5 = CRegistryToPkgDef::Export(a1, &v14);
          v9 = (_QWORD *)(v14 - 24);
          if ( v5 < 0 )
          {
            if ( _InterlockedDecrement((volatile signed __int32 *)(v14 - 24 + 16)) <= 0 )
            {
              _mm_lfence();
              (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v9 + 8LL))(*v9);
            }
            break;
          }
          if ( _InterlockedDecrement((volatile signed __int32 *)(v14 - 24 + 16)) <= 0 )
          {
            _mm_lfence();
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v9 + 8LL))(*v9);
          }
        }
      }
    }
  }
  if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    RegCloseKey(hKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140052c8c  mov     [rsp-8+arg_10], rbx
0x140052c91  push    rbp
0x140052c92  push    rsi
0x140052c93  push    rdi
0x140052c94  push    r12
0x140052c96  push    r14
0x140052c98  lea     rbp, [rsp-180h]
0x140052ca0  sub     rsp, 280h
0x140052ca7  mov     rax, cs:__security_cookie
0x140052cae  xor     rax, rsp
0x140052cb1  mov     [rbp+1A0h+var_30], rax
0x140052cb8  mov     r14, rdx
0x140052cbb  mov     rsi, rcx
0x140052cbe  or      r12, 0FFFFFFFFFFFFFFFFh
0x140052cc2  mov     [rsp+2A0h+hKey], r12
0x140052cc7  lea     rax, [rsp+2A0h+hKey]
0x140052ccc  mov     [rsp+2A0h+phkResult], rax; lpReserved
0x140052cd1  mov     r9d, 20019h; samDesired
0x140052cd7  xor     r8d, r8d; ulOptions
0x140052cda  mov     rdx, [rdx]; lpSubKey
0x140052cdd  mov     rcx, [rcx+98h]; hKey
0x140052ce4  call    cs:__imp_RegOpenKeyExW
0x140052cea  movzx   ebx, ax
0x140052ced  or      ebx, 80070000h
0x140052cf3  test    eax, eax
0x140052cf5  cmovle  ebx, eax
0x140052cf8  test    ebx, ebx
0x140052cfa  js      loc_140052E21
0x140052d00  and     [rsp+2A0h+var_250], 0
0x140052d05  lea     r9, [rsp+2A0h+var_250]
0x140052d0a  mov     r8, r14
0x140052d0d  mov     rdx, [rsp+2A0h+hKey]
0x140052d12  mov     rcx, rsi
0x140052d15  call    ?ShallowExport@CRegistryToPkgDef@@AEAAJPEAUHKEY__@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAK@Z; CRegistryToPkgDef::ShallowExport(HKEY__ *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ulong &)
0x140052d1a  mov     ebx, eax
0x140052d1c  test    eax, eax
0x140052d1e  js      loc_140052E21
0x140052d24  lfence
0x140052d27  xor     edi, edi
0x140052d29  cmp     [rsp+2A0h+var_250], edi
0x140052d2d  jbe     loc_140052E21
0x140052d33  mov     [rsp+2A0h+cchName], 0FFh
0x140052d3b  and     [rsp+2A0h+var_268], 0
0x140052d41  and     [rsp+2A0h+var_270], 0
0x140052d47  and     [rsp+2A0h+var_278], 0
0x140052d4d  and     [rsp+2A0h+phkResult], 0
0x140052d53  lea     r9, [rsp+2A0h+cchName]; lpcchName
0x140052d58  lea     r8, [rsp+2A0h+Name]; lpName
0x140052d5d  mov     edx, edi; dwIndex
0x140052d5f  mov     rcx, [rsp+2A0h+hKey]; hKey
0x140052d64  call    cs:__imp_RegEnumKeyExW
0x140052d6a  test    eax, eax
0x140052d6c  jnz     loc_140052DFB
0x140052d72  and     [rsp+2A0h+var_248], 0
0x140052d78  lea     r8, SubBlock; "\\"
0x140052d7f  mov     rdx, r14
0x140052d82  lea     rcx, [rsp+2A0h+var_260]
0x140052d87  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x140052d8c  nop
0x140052d8d  lea     r8, [rsp+2A0h+Name]
0x140052d92  mov     rdx, rax
0x140052d95  lea     rcx, [rsp+2A0h+var_248]
0x140052d9a  call    ??HATL@@YA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@0@AEBV10@PEBG@Z; ATL::operator+(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *)
0x140052d9f  nop
0x140052da0  mov     rdx, [rsp+2A0h+var_260]
0x140052da5  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140052da9  mov     eax, r12d
0x140052dac  lock xadd [rdx+10h], eax
0x140052db1  add     eax, r12d
0x140052db4  test    eax, eax
0x140052db6  jg      short loc_140052DC4
0x140052db8  lfence
0x140052dbb  mov     rcx, [rdx]
0x140052dbe  mov     rax, [rcx]
0x140052dc1  call    qword ptr [rax+8]
0x140052dc4  lea     rdx, [rsp+2A0h+var_248]
0x140052dc9  mov     rcx, rsi
0x140052dcc  call    ?Export@CRegistryToPkgDef@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; CRegistryToPkgDef::Export(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140052dd1  mov     ebx, eax
0x140052dd3  mov     rdx, [rsp+2A0h+var_248]
0x140052dd8  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140052ddc  test    eax, eax
0x140052dde  mov     eax, r12d
0x140052de1  js      short loc_140052E09
0x140052de3  lock xadd [rdx+10h], eax
0x140052de8  add     eax, r12d
0x140052deb  test    eax, eax
0x140052ded  jg      short loc_140052DFB
0x140052def  lfence
0x140052df2  mov     rcx, [rdx]
0x140052df5  mov     rax, [rcx]
0x140052df8  call    qword ptr [rax+8]
0x140052dfb  inc     edi
0x140052dfd  cmp     edi, [rsp+2A0h+var_250]
0x140052e01  jb      loc_140052D33
0x140052e07  jmp     short loc_140052E21
0x140052e09  lock xadd [rdx+10h], eax
0x140052e0e  add     eax, r12d
0x140052e11  test    eax, eax
0x140052e13  jg      short loc_140052E21
0x140052e15  lfence
0x140052e18  mov     rcx, [rdx]
0x140052e1b  mov     rax, [rcx]
0x140052e1e  call    qword ptr [rax+8]
0x140052e21  mov     rcx, [rsp+2A0h+hKey]; hKey
0x140052e26  cmp     rcx, r12
0x140052e29  jz      short loc_140052E31
0x140052e2b  call    cs:__imp_RegCloseKey
0x140052e31  mov     eax, ebx
0x140052e33  mov     rcx, [rbp+1A0h+var_30]
0x140052e3a  xor     rcx, rsp; StackCookie
0x140052e3d  call    __security_check_cookie
0x140052e42  mov     rbx, [rsp+2A0h+arg_10]
0x140052e4a  add     rsp, 280h
0x140052e51  pop     r14
0x140052e53  pop     r12
0x140052e55  pop     rdi
0x140052e56  pop     rsi
0x140052e57  pop     rbp
0x140052e58  retn
```
