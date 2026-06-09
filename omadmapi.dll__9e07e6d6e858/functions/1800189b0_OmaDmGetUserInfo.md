# OmaDmGetUserInfo

- ea: `0x1800189b0`
- end: `0x180018bb7`
- name: `OmaDmGetUserInfo`
- size: `519`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001b750`

## callees

- `0x1800075f0`
- `0x180007930`
- `0x180008290`
- `0x180009bf4`
- `0x18000c814`
- `0x18000dfc0`
- `0x1800189b0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018b58`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180018b58`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018b48`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018b83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018b98`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018b48`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018b83`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018b98`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018a78`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018abc`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018a78`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180018abc`

## pseudocode

```c
__int64 __fastcall OmaDmGetUserInfo(__int64 a1, __int64 a2, const WCHAR *a3, __int64 a4)
{
  unsigned int v6; // esi
  signed int AccountKey; // ebx
  HKEY *phkResult; // rax
  LSTATUS v10; // eax
  bool v11; // cc
  HKEY *v12; // rax
  HLOCAL v13; // xmm1_8
  HKEY hKey; // [rsp+50h] [rbp-19h] BYREF
  HKEY v16; // [rsp+58h] [rbp-11h] BYREF
  HKEY v17; // [rsp+60h] [rbp-9h] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-1h] BYREF
  __int64 v19[2]; // [rsp+70h] [rbp+7h] BYREF
  HLOCAL hMem; // [rsp+80h] [rbp+17h]
  __int64 v21; // [rsp+E8h] [rbp+7Fh] BYREF

  hObject = 0;
  hKey = 0;
  LODWORD(v21) = 0;
  v17 = 0;
  v16 = 0;
  v6 = a2;
  hMem = 0;
  *(_OWORD *)v19 = 0;
  if ( a4 && (unsigned int)IsValidAccountID(a1, a2) )
  {
    AccountKey = AcquireOmaDmMutex(&hObject);
    if ( AccountKey >= 0 )
    {
      AccountKey = GetAccountKey(a1, v6, 131353, &hKey, 0);
      if ( AccountKey >= 0 )
      {
        phkResult = (HKEY *)ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v17);
        v10 = RegOpenKeyExW(hKey, L"UserInfo", 0, 0x20119u, phkResult);
        AccountKey = v10;
        v11 = v10 <= 0;
        if ( v10
          || (v12 = (HKEY *)ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v16),
              v10 = RegOpenKeyExW(v17, a3, 0, 0x20119u, v12),
              AccountKey = v10,
              v11 = v10 <= 0,
              v10) )
        {
          if ( !v11 )
            AccountKey = (unsigned __int16)v10 | 0x80070000;
        }
        else
        {
          AccountKey = GetStructFromRegistry(
                         v16,
                         2,
                         (__int64)v19,
                         24,
                         (__int64)&v21,
                         (unsigned __int8 *)&qword_18002A538,
                         0x10u);
          if ( AccountKey >= 0 )
          {
            v13 = hMem;
            LODWORD(v19[0]) = v21;
            hMem = 0;
            *(_OWORD *)a4 = *(_OWORD *)v19;
            *(_QWORD *)(a4 + 16) = v13;
            *(_OWORD *)v19 = 0;
          }
        }
      }
    }
  }
  else
  {
    AccountKey = -2147024809;
  }
  RegCloseKey(hKey);
  LocalFree(hMem);
  *(_OWORD *)v19 = 0;
  hMem = 0;
  ReleaseOmaDmMutex(hObject);
  if ( v16 )
    RegCloseKey(v16);
  if ( v17 )
    RegCloseKey(v17);
  return (unsigned int)AccountKey;
}

```

## disassembly

```asm
0x1800189b0  push    rbp
0x1800189b2  push    rbx
0x1800189b3  push    rsi
0x1800189b4  push    rdi
0x1800189b5  push    r14
0x1800189b7  push    r15
0x1800189b9  lea     rbp, [rsp-2Fh]
0x1800189be  sub     rsp, 98h
0x1800189c5  xor     eax, eax
0x1800189c7  mov     [rbp+57h+hObject], 0
0x1800189cf  mov     [rbp+57h+hKey], 0
0x1800189d7  xorps   xmm0, xmm0
0x1800189da  mov     dword ptr [rbp+57h+arg_18], 0
0x1800189e1  mov     rdi, r9
0x1800189e4  mov     [rbp+57h+var_60], 0
0x1800189ec  mov     r15, r8
0x1800189ef  mov     [rbp+57h+var_68], 0
0x1800189f7  mov     esi, edx
0x1800189f9  mov     [rbp+57h+hMem], rax
0x1800189fd  mov     r14, rcx
0x180018a00  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x180018a04  test    r9, r9
0x180018a07  jnz     short loc_180018A13
0x180018a09  mov     ebx, 80070057h
0x180018a0e  jmp     loc_180018B44
0x180018a13  call    IsValidAccountID
0x180018a18  test    eax, eax
0x180018a1a  jz      short loc_180018A09
0x180018a1c  lea     rcx, [rbp+57h+hObject]; void **
0x180018a20  call    ?AcquireOmaDmMutex@@YAJPEAPEAX@Z; AcquireOmaDmMutex(void * *)
0x180018a25  mov     ebx, eax
0x180018a27  test    eax, eax
0x180018a29  js      loc_180018B44
0x180018a2f  lea     r9, [rbp+57h+hKey]
0x180018a33  mov     [rsp+0C0h+phkResult], 0
0x180018a3c  mov     r8d, 20119h
0x180018a42  mov     edx, esi
0x180018a44  mov     rcx, r14
0x180018a47  call    GetAccountKey
0x180018a4c  mov     ebx, eax
0x180018a4e  test    eax, eax
0x180018a50  js      loc_180018B44
0x180018a56  lea     rcx, [rbp+57h+var_60]
0x180018a5a  call    ??$replace@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@ipx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@0@@Z; ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(ipx::unique_any<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180018a5f  mov     rcx, [rbp+57h+hKey]; hKey
0x180018a63  lea     rdx, aUserinfo; "UserInfo"
0x180018a6a  mov     r9d, 20119h; samDesired
0x180018a70  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180018a75  xor     r8d, r8d; ulOptions
0x180018a78  call    cs:__imp_RegOpenKeyExW
0x180018a7f  nop     dword ptr [rax+rax+00h]
0x180018a84  mov     ebx, eax
0x180018a86  test    eax, eax
0x180018a88  jz      short loc_180018A9E
0x180018a8a  jle     loc_180018B44
0x180018a90  movzx   ebx, ax
0x180018a93  or      ebx, 80070000h
0x180018a99  jmp     loc_180018B44
0x180018a9e  lea     rcx, [rbp+57h+var_68]
0x180018aa2  call    ??$replace@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@ipx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$_HandleTraits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@detail@ipx@@@0@@Z; ipx::replace<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(ipx::unique_any<ipx::detail::_HandleTraits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180018aa7  mov     rcx, [rbp+57h+var_60]; hKey
0x180018aab  mov     r9d, 20119h; samDesired
0x180018ab1  xor     r8d, r8d; ulOptions
0x180018ab4  mov     [rsp+0C0h+phkResult], rax; phkResult
0x180018ab9  mov     rdx, r15; lpSubKey
0x180018abc  call    cs:__imp_RegOpenKeyExW
0x180018ac3  nop     dword ptr [rax+rax+00h]
0x180018ac8  mov     ebx, eax
0x180018aca  test    eax, eax
0x180018acc  jnz     short loc_180018A8A
0x180018ace  mov     r8d, [rdi]
0x180018ad1  lea     rax, qword_18002A538
0x180018ad8  mov     rcx, [rbp+57h+var_68]; hKey
0x180018adc  lea     r9, off_180025C60; "AADTokenNeedsUserInteraction"
0x180018ae3  mov     [rsp+0C0h+var_78], 10h; unsigned int
0x180018aeb  lea     edx, [rbx+1]
0x180018aee  mov     [rsp+0C0h+var_80], rax; unsigned __int8 *
0x180018af3  lea     rax, [rbp+57h+arg_18]
0x180018af7  mov     [rsp+0C0h+var_88], rax; __int64
0x180018afc  lea     rax, [rbp+57h+var_50]
0x180018b00  mov     [rsp+0C0h+var_90], 18h; int
0x180018b08  mov     [rsp+0C0h+var_98], rax; __int64
0x180018b0d  mov     dword ptr [rsp+0C0h+phkResult], 2; int
0x180018b15  call    GetStructFromRegistry
0x180018b1a  mov     ebx, eax
0x180018b1c  test    eax, eax
0x180018b1e  js      short loc_180018B44
0x180018b20  mov     eax, dword ptr [rbp+57h+arg_18]
0x180018b23  movsd   xmm1, [rbp+57h+hMem]
0x180018b28  mov     dword ptr [rbp+57h+var_50], eax
0x180018b2b  xor     eax, eax
0x180018b2d  movups  xmm0, xmmword ptr [rbp+57h+var_50]
0x180018b31  mov     [rbp+57h+hMem], rax
0x180018b35  movups  xmmword ptr [rdi], xmm0
0x180018b38  xorps   xmm0, xmm0
0x180018b3b  movsd   qword ptr [rdi+10h], xmm1
0x180018b40  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x180018b44  mov     rcx, [rbp+57h+hKey]; hKey
0x180018b48  call    cs:__imp_RegCloseKey
0x180018b4f  nop     dword ptr [rax+rax+00h]
0x180018b54  mov     rcx, [rbp+57h+hMem]; hMem
0x180018b58  call    cs:__imp_LocalFree
0x180018b5f  nop     dword ptr [rax+rax+00h]
0x180018b64  mov     rcx, [rbp+57h+hObject]; hObject
0x180018b68  xorps   xmm0, xmm0
0x180018b6b  xor     eax, eax
0x180018b6d  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x180018b71  mov     [rbp+57h+hMem], rax
0x180018b75  call    ?ReleaseOmaDmMutex@@YAXPEAX@Z; ReleaseOmaDmMutex(void *)
0x180018b7a  mov     rcx, [rbp+57h+var_68]; hKey
0x180018b7e  test    rcx, rcx
0x180018b81  jz      short loc_180018B8F
0x180018b83  call    cs:__imp_RegCloseKey
0x180018b8a  nop     dword ptr [rax+rax+00h]
0x180018b8f  mov     rcx, [rbp+57h+var_60]; hKey
0x180018b93  test    rcx, rcx
0x180018b96  jz      short loc_180018BA4
0x180018b98  call    cs:__imp_RegCloseKey
0x180018b9f  nop     dword ptr [rax+rax+00h]
0x180018ba4  mov     eax, ebx
0x180018ba6  add     rsp, 98h
0x180018bad  pop     r15
0x180018baf  pop     r14
0x180018bb1  pop     rdi
0x180018bb2  pop     rsi
0x180018bb3  pop     rbx
0x180018bb4  pop     rbp
0x180018bb5  retn
```
