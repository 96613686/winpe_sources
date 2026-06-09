# CDevEnvAppId::InitJITHelper(void)

- ea: `0x140011b9c`
- end: `0x140011d60`
- name: `?InitJITHelper@CDevEnvAppId@@QEAAJXZ`
- size: `452`
- prototype: `__int64 __fastcall(CDevEnvAppId *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000ccfc`

## callees

- `0x14000b1b4`
- `0x14000b9e8`
- `0x14000bfa8`
- `0x140011b9c`
- `0x14002fa90`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140011c53`
- `ADVAPI32!RegCloseKey` at `0x140011c53`
- `ADVAPI32!RegOpenKeyExW` at `0x140011c20`
- `ADVAPI32!RegOpenKeyExW` at `0x140011c20`
- `api-ms-win-crt-convert-l1-1-0!_wcstoui64` at `0x140011cf0`
- `api-ms-win-crt-convert-l1-1-0!_wcstoui64` at `0x140011cf0`
- `OLEAUT32!__imp_SysFreeString` at `0x140011d05`
- `OLEAUT32!__imp_SysFreeString` at `0x140011d4d`
- `OLEAUT32!__imp_SysFreeString` at `0x140011d05`
- `OLEAUT32!__imp_SysFreeString` at `0x140011d4d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CDevEnvAppId::InitJITHelper(const WCHAR *this)
{
  CDevEnvAppId *v1; // rdi
  int v2; // ebx
  __int64 v3; // rsi
  __int64 v4; // r8
  LSTATUS v5; // eax
  HKEY v6; // r8
  int v7; // edx
  unsigned int v8; // eax
  bool v9; // si
  LPCWSTR v10; // rdx
  _QWORD *v11; // rdx
  LPCWSTR lpSubKey; // [rsp+60h] [rbp+30h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+38h] BYREF
  __int64 v15; // [rsp+70h] [rbp+40h] BYREF

  lpSubKey = this;
  v1 = CDevEnvAppId::ms_pTheAppId;
  v2 = 0;
  v3 = *(_QWORD *)CAppIdExtImpl::GetIsolationInstallationId(&v15);
  lpSubKey = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    &lpSubKey,
    "Software\\Microsoft\\VisualStudio\\Debugger\\JIT\\{3B476D35-A401-11D2-AAD4-00C04F990171}\\");
  if ( v3 )
  {
    v4 = -1;
    do
      ++v4;
    while ( *(_WORD *)(v3 + 2 * v4) );
  }
  else
  {
    v4 = 0;
  }
  ATL::CSimpleStringT<unsigned short,0>::Append(&lpSubKey, v3, v4);
  hKey = 0;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20219u, &hKey);
  v6 = 0;
  if ( !v5 )
    v6 = hKey;
  v7 = v5 != 0 ? v5 : 0;
  v8 = (unsigned __int16)(v5 != 0 ? v5 : 0) | 0x80070000;
  if ( v7 <= 0 )
    v8 = v7;
  v9 = v8 == 0;
  if ( v6 )
    RegCloseKey(v6);
  v10 = lpSubKey - 12;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)lpSubKey - 2, 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v10 + 8LL))(*(_QWORD *)v10);
  }
  *((_BYTE *)v1 + 1792) = v9;
  v11 = (_QWORD *)(v15 - 24);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v15 - 24 + 16), 0xFFFFFFFF) <= 1 )
  {
    _mm_lfence();
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v11 + 8LL))(*v11);
  }
  if ( *((_BYTE *)v1 + 1792) )
  {
    LODWORD(lpSubKey) = 0;
    hKey = 0;
    v2 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, LPCWSTR *, HKEY *))(*((_QWORD *)v1 + 190) + 24LL))(
           (__int64)v1 + 1520,
           L"JITDebugParam",
           &lpSubKey,
           &hKey);
    if ( v2 >= 0 )
    {
      _mm_lfence();
      if ( (_DWORD)lpSubKey )
        *((_QWORD *)v1 + 220) = _wcstoui64((const wchar_t *)hKey, 0, 16);
      LODWORD(lpSubKey) = 0;
      SysFreeString((BSTR)hKey);
      hKey = 0;
      v2 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, LPCWSTR *, HKEY *))(*((_QWORD *)v1 + 190) + 24LL))(
             (__int64)v1 + 1520,
             L"JITDebug",
             &lpSubKey,
             &hKey);
      if ( v2 >= 0 && (_DWORD)lpSubKey )
      {
        _mm_lfence();
        v2 = CJITHelper::RegisterRuntimeJITServer((CDevEnvAppId *)((char *)v1 + 1744), 1);
      }
    }
    SysFreeString((BSTR)hKey);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x140011b9c  mov     [rsp-28h+lpSubKey], rcx
0x140011ba1  push    rbp
0x140011ba2  push    rbx
0x140011ba3  push    rsi
0x140011ba4  push    rdi
0x140011ba5  push    r14
0x140011ba7  mov     rbp, rsp
0x140011baa  sub     rsp, 30h
0x140011bae  mov     rdi, cs:?ms_pTheAppId@CDevEnvAppId@@1PEAV?$CComFreeThreadedObject@VCDevEnvAppId@@@@EA; CComFreeThreadedObject<CDevEnvAppId> * CDevEnvAppId::ms_pTheAppId
0x140011bb5  xor     r14d, r14d
0x140011bb8  mov     ebx, r14d
0x140011bbb  lea     rcx, [rbp+arg_10]
0x140011bbf  call    ?GetIsolationInstallationId@CAppIdExtImpl@@KA?AV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@XZ; CAppIdExtImpl::GetIsolationInstallationId(void)
0x140011bc4  mov     rsi, [rax]
0x140011bc7  mov     [rbp+lpSubKey], r14
0x140011bcb  lea     rdx, aSoftwareMicros_9; "Software\\Microsoft\\VisualStudio\\Debu"...
0x140011bd2  lea     rcx, [rbp+lpSubKey]
0x140011bd6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(char const *)
0x140011bdb  test    rsi, rsi
0x140011bde  jnz     short loc_140011BE5
0x140011be0  mov     r8d, r14d
0x140011be3  jmp     short loc_140011BF3
0x140011be5  or      r8, 0FFFFFFFFFFFFFFFFh
0x140011be9  inc     r8
0x140011bec  cmp     [rsi+r8*2], r14w
0x140011bf1  jnz     short loc_140011BE9
0x140011bf3  mov     rdx, rsi
0x140011bf6  lea     rcx, [rbp+lpSubKey]
0x140011bfa  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x140011bff  mov     [rbp+hKey], r14
0x140011c03  lea     rax, [rbp+hKey]
0x140011c07  mov     [rsp+30h+phkResult], rax; phkResult
0x140011c0c  mov     r9d, 20219h; samDesired
0x140011c12  xor     r8d, r8d; ulOptions
0x140011c15  mov     rdx, [rbp+lpSubKey]; lpSubKey
0x140011c19  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140011c20  call    cs:__imp_RegOpenKeyExW
0x140011c26  mov     ecx, eax
0x140011c28  mov     r8, r14
0x140011c2b  test    eax, eax
0x140011c2d  cmovz   r8, [rbp+hKey]
0x140011c32  neg     eax
0x140011c34  sbb     edx, edx
0x140011c36  and     edx, ecx
0x140011c38  movzx   eax, dx
0x140011c3b  or      eax, 80070000h
0x140011c40  test    edx, edx
0x140011c42  cmovle  eax, edx
0x140011c45  test    eax, eax
0x140011c47  setz    sil
0x140011c4b  test    r8, r8
0x140011c4e  jz      short loc_140011C5A
0x140011c50  mov     rcx, r8; hKey
0x140011c53  call    cs:__imp_RegCloseKey
0x140011c59  nop
0x140011c5a  mov     rdx, [rbp+lpSubKey]
0x140011c5e  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140011c62  or      eax, 0FFFFFFFFh
0x140011c65  lock xadd [rdx+10h], eax
0x140011c6a  sub     eax, 1
0x140011c6d  jg      short loc_140011C7B
0x140011c6f  lfence
0x140011c72  mov     rcx, [rdx]
0x140011c75  mov     rax, [rcx]
0x140011c78  call    qword ptr [rax+8]
0x140011c7b  mov     [rdi+700h], sil
0x140011c82  mov     rdx, [rbp+arg_10]
0x140011c86  add     rdx, 0FFFFFFFFFFFFFFE8h
0x140011c8a  or      eax, 0FFFFFFFFh
0x140011c8d  lock xadd [rdx+10h], eax
0x140011c92  sub     eax, 1
0x140011c95  jg      short loc_140011CA3
0x140011c97  lfence
0x140011c9a  mov     rcx, [rdx]
0x140011c9d  mov     rax, [rcx]
0x140011ca0  call    qword ptr [rax+8]
0x140011ca3  cmp     [rdi+700h], r14b
0x140011caa  jz      loc_140011D53
0x140011cb0  mov     dword ptr [rbp+lpSubKey], r14d
0x140011cb4  mov     [rbp+hKey], r14
0x140011cb8  lea     rsi, [rdi+5F0h]
0x140011cbf  mov     rax, [rsi]
0x140011cc2  lea     r9, [rbp+hKey]
0x140011cc6  lea     r8, [rbp+lpSubKey]
0x140011cca  lea     rdx, aJitdebugparam; "JITDebugParam"
0x140011cd1  mov     rcx, rsi
0x140011cd4  call    qword ptr [rax+18h]
0x140011cd7  mov     ebx, eax
0x140011cd9  test    eax, eax
0x140011cdb  js      short loc_140011D49
0x140011cdd  lfence
0x140011ce0  cmp     dword ptr [rbp+lpSubKey], r14d
0x140011ce4  jz      short loc_140011CFD
0x140011ce6  xor     edx, edx; EndPtr
0x140011ce8  lea     r8d, [rdx+10h]; Radix
0x140011cec  mov     rcx, [rbp+hKey]; String
0x140011cf0  call    cs:__imp__wcstoui64
0x140011cf6  mov     [rdi+6E0h], rax
0x140011cfd  mov     dword ptr [rbp+lpSubKey], r14d
0x140011d01  mov     rcx, [rbp+hKey]; bstrString
0x140011d05  call    cs:__imp_SysFreeString
0x140011d0b  mov     [rbp+hKey], r14
0x140011d0f  mov     rax, [rsi]
0x140011d12  lea     r9, [rbp+hKey]
0x140011d16  lea     r8, [rbp+lpSubKey]
0x140011d1a  lea     rdx, aJitdebug; "JITDebug"
0x140011d21  mov     rcx, rsi
0x140011d24  call    qword ptr [rax+18h]
0x140011d27  mov     ebx, eax
0x140011d29  test    eax, eax
0x140011d2b  js      short loc_140011D49
0x140011d2d  cmp     dword ptr [rbp+lpSubKey], r14d
0x140011d31  jz      short loc_140011D49
0x140011d33  lfence
0x140011d36  lea     rcx, [rdi+6D0h]; this
0x140011d3d  mov     edx, 1; int
0x140011d42  call    ?RegisterRuntimeJITServer@CJITHelper@@QEAAJH@Z; CJITHelper::RegisterRuntimeJITServer(int)
0x140011d47  mov     ebx, eax
0x140011d49  mov     rcx, [rbp+hKey]; bstrString
0x140011d4d  call    cs:__imp_SysFreeString
0x140011d53  mov     eax, ebx
0x140011d55  add     rsp, 30h
0x140011d59  pop     r14
0x140011d5b  pop     rdi
0x140011d5c  pop     rsi
0x140011d5d  pop     rbx
0x140011d5e  pop     rbp
0x140011d5f  retn
```
