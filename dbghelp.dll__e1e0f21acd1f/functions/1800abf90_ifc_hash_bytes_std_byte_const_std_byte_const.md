# ifc::hash_bytes(std::byte const *,std::byte const *)

- ea: `0x1800abf90`
- end: `0x1800ac326`
- name: `?hash_bytes@ifc@@YA?AUSHA256Hash@1@PEBW4byte@std@@0@Z`
- size: `918`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x1800a8d00`

## callees

- `0x180027440`
- `0x1800abd80`
- `0x1800abf90`
- `0x1801d6350`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac2ca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ac2ca`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800abff1`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800abff1`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800ac011`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800ac035`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800ac059`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800ac07d`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800ac0a1`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800ac0c5`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800ac0e9`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800ac011`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800ac035`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800ac059`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800ac07d`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800ac0a1`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800ac0c5`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800ac0e9`

## string_xrefs

- `0x1800abfea`: `bcrypt.dll`
- `0x1800ac007`: `BCryptOpenAlgorithmProvider`
- `0x1800ac04b`: `BCryptCreateHash`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_OWORD *__fastcall ifc::hash_bytes(_OWORD *a1, __int64 a2, __int64 a3)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rcx
  __int64 (__fastcall *v8)(__int64, const wchar_t *, _QWORD *, __int64, int *, _DWORD); // rbx
  int v9; // eax
  int v10; // eax
  int v11; // eax
  _OWORD *v12; // rax
  int v14; // [rsp+30h] [rbp-1F8h] BYREF
  DWORD pExceptionObject; // [rsp+34h] [rbp-1F4h] BYREF
  int v16; // [rsp+38h] [rbp-1F0h] BYREF
  int v17; // [rsp+3Ch] [rbp-1ECh] BYREF
  int v18; // [rsp+40h] [rbp-1E8h] BYREF
  _QWORD v19[2]; // [rsp+50h] [rbp-1D8h] BYREF
  __int128 v20; // [rsp+60h] [rbp-1C8h]
  __int128 v21; // [rsp+70h] [rbp-1B8h]
  void (__fastcall *v22)(_QWORD, _QWORD); // [rsp+80h] [rbp-1A8h]
  __int64 v23; // [rsp+88h] [rbp-1A0h]
  __int64 v24; // [rsp+90h] [rbp-198h] BYREF
  _QWORD v25[2]; // [rsp+98h] [rbp-190h] BYREF
  const `anonymous namespace'::FailedLibraryBinding *v26; // [rsp+A8h] [rbp-180h] BYREF
  const `anonymous namespace'::OpenAlgorithmError *v27; // [rsp+B0h] [rbp-178h] BYREF
  const `anonymous namespace'::HashLengthPropertyError *v28; // [rsp+B8h] [rbp-170h] BYREF
  const `anonymous namespace'::ObjectLengthPropertyError *v29; // [rsp+C0h] [rbp-168h] BYREF
  const `anonymous namespace'::CreateHashError *v30; // [rsp+C8h] [rbp-160h] BYREF
  const `anonymous namespace'::HashDataError *v31; // [rsp+D0h] [rbp-158h] BYREF
  const `anonymous namespace'::FinishHashError *v32; // [rsp+D8h] [rbp-150h] BYREF
  _BYTE v33[16]; // [rsp+E0h] [rbp-148h] BYREF
  __int128 v34; // [rsp+F0h] [rbp-138h]
  __int128 v35; // [rsp+100h] [rbp-128h]
  __int64 v36; // [rsp+118h] [rbp-110h]
  _BYTE v37[32]; // [rsp+120h] [rbp-108h] BYREF
  _BYTE v38[32]; // [rsp+140h] [rbp-E8h] BYREF
  _BYTE v39[32]; // [rsp+160h] [rbp-C8h] BYREF
  _BYTE v40[32]; // [rsp+180h] [rbp-A8h] BYREF
  _BYTE v41[32]; // [rsp+1A0h] [rbp-88h] BYREF
  _BYTE v42[32]; // [rsp+1C0h] [rbp-68h] BYREF
  _BYTE v43[32]; // [rsp+1E0h] [rbp-48h] BYREF

  v25[1] = -2;
  try
  {
    if ( dword_1802B5AB8 != 1 )
    {
      if ( dword_1802B5AB8 != 2 )
      {
        Library = LoadLibraryExW(L"bcrypt.dll", 0, 0);
        hModule = Library;
        if ( Library )
        {
          qword_1802B5A80 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))GetProcAddress(
                                                                                      Library,
                                                                                      "BCryptOpenAlgorithmProvider");
          if ( qword_1802B5A80 )
          {
            qword_1802B5A88 = (__int64)GetProcAddress(hModule, "BCryptGetProperty");
            if ( qword_1802B5A88 )
            {
              *(_QWORD *)&xmmword_1802B5A90 = GetProcAddress(hModule, "BCryptCreateHash");
              if ( (_QWORD)xmmword_1802B5A90 )
              {
                *((_QWORD *)&xmmword_1802B5A90 + 1) = GetProcAddress(hModule, "BCryptHashData");
                if ( *((_QWORD *)&xmmword_1802B5A90 + 1) )
                {
                  *(_QWORD *)&xmmword_1802B5AA0 = GetProcAddress(hModule, "BCryptDestroyHash");
                  if ( (_QWORD)xmmword_1802B5AA0 )
                  {
                    *((_QWORD *)&xmmword_1802B5AA0 + 1) = GetProcAddress(hModule, "BCryptFinishHash");
                    if ( *((_QWORD *)&xmmword_1802B5AA0 + 1) )
                    {
                      ProcAddress = GetProcAddress(hModule, "BCryptCloseAlgorithmProvider");
                      qword_1802B5AB0 = (__int64)ProcAddress;
                      if ( ProcAddress )
                      {
                        dword_1802B5AB8 = 1;
LABEL_14:
                        v8 = (__int64 (__fastcall *)(__int64, const wchar_t *, _QWORD *, __int64, int *, _DWORD))qword_1802B5A88;
                        v34 = xmmword_1802B5A90;
                        v35 = xmmword_1802B5AA0;
                        LODWORD(v36) = 1;
                        HIDWORD(v36) = dword_1802B5ABC;
                        v19[0] = qword_1802B5A80;
                        v19[1] = qword_1802B5A88;
                        v20 = xmmword_1802B5A90;
                        v21 = xmmword_1802B5AA0;
                        v22 = (void (__fastcall *)(_QWORD, _QWORD))ProcAddress;
                        v23 = v36;
                        v24 = 0;
                        v25[0] = 0;
                        v9 = qword_1802B5A80(&v24, L"SHA256", 0, 0);
                        if ( v9 < 0 )
                        {
                          v16 = v9;
                          throw (`anonymous namespace'::OpenAlgorithmError *)&v16;
                        }
                        v14 = 0;
                        v10 = v8(v24, L"HashDigestLength", v25, 4, &v14, 0);
                        if ( v10 < 0 )
                        {
                          v17 = v10;
                          throw (`anonymous namespace'::HashLengthPropertyError *)&v17;
                        }
                        v11 = v8(v24, L"ObjectLength", (_QWORD *)((char *)v25 + 4), 4, &v14, 0);
                        if ( v11 < 0 )
                        {
                          v18 = v11;
                          throw (`anonymous namespace'::ObjectLengthPropertyError *)&v18;
                        }
                        v12 = (_OWORD *)anonymous_namespace_::SHA256Helper::hash(v19, v33, a2, a3);
                        *a1 = *v12;
                        a1[1] = v12[1];
                        if ( v24 )
                          v22(v24, 0);
                        return a1;
                      }
                    }
                  }
                }
              }
            }
          }
        }
        dword_1802B5AB8 = 2;
      }
      pExceptionObject = GetLastError();
      throw (`anonymous namespace'::FailedLibraryBinding *)&pExceptionObject;
    }
    ProcAddress = (FARPROC)qword_1802B5AB0;
    goto LABEL_14;
  }
  catch ( const `anonymous namespace'::FailedLibraryBinding *v26 )
  {
    anonymous_namespace_::format__anonymous_namespace_::FailedLibraryBinding_(v37, "library binding error: ", v26);
    throw (ifc::HashFailed *)v37;
  }
  catch ( const `anonymous namespace'::OpenAlgorithmError *v27 )
  {
    anonymous_namespace_::format__anonymous_namespace_::OpenAlgorithmError_(v38, "open algorithm failed: ", v27);
    throw (ifc::HashFailed *)v38;
  }
  catch ( const `anonymous namespace'::HashLengthPropertyError *v28 )
  {
    anonymous_namespace_::format__anonymous_namespace_::HashLengthPropertyError_(v39, "hash length failed: ", v28);
    throw (ifc::HashFailed *)v39;
  }
  catch ( const `anonymous namespace'::ObjectLengthPropertyError *v29 )
  {
    anonymous_namespace_::format__anonymous_namespace_::ObjectLengthPropertyError_(v40, "object length failed: ", v29);
    throw (ifc::HashFailed *)v40;
  }
  catch ( const `anonymous namespace'::CreateHashError *v30 )
  {
    anonymous_namespace_::format__anonymous_namespace_::CreateHashError_(v41, "create hash failed: ", v30);
    throw (ifc::HashFailed *)v41;
  }
  catch ( const `anonymous namespace'::HashDataError *v31 )
  {
    anonymous_namespace_::format__anonymous_namespace_::HashDataError_(v42, "hash data failed: ", v31);
    throw (ifc::HashFailed *)v42;
  }
  catch ( const `anonymous namespace'::FinishHashError *v32 )
  {
    anonymous_namespace_::format__anonymous_namespace_::HashDataError_(v43, "finish hash failed: ", v32);
    throw (ifc::HashFailed *)v43;
  }
  catch ( ... )
  {
    throw;
  }
  return a1;
}

```

## disassembly

```asm
0x1800abf90  mov     rax, rsp
0x1800abf93  push    rdi
0x1800abf94  push    r14
0x1800abf96  push    r15
0x1800abf98  sub     rsp, 210h
0x1800abf9f  mov     qword ptr [rax-188h], 0FFFFFFFFFFFFFFFEh
0x1800abfaa  mov     [rax+8], rbx
0x1800abfae  mov     [rax+20h], rsi
0x1800abfb2  mov     rax, cs:__security_cookie
0x1800abfb9  xor     rax, rsp
0x1800abfbc  mov     [rsp+228h+var_28], rax
0x1800abfc4  mov     r14, r8
0x1800abfc7  mov     rsi, rdx
0x1800abfca  mov     rdi, rcx
0x1800abfcd  mov     edx, cs:dword_1802B5AB8
0x1800abfd3  sub     edx, 1
0x1800abfd6  jz      loc_1800AC10E
0x1800abfdc  cmp     edx, 1
0x1800abfdf  jz      loc_1800AC2CA
0x1800abfe5  xor     r8d, r8d; dwFlags
0x1800abfe8  xor     edx, edx; hFile
0x1800abfea  lea     rcx, aBcryptDll; "bcrypt.dll"
0x1800abff1  call    cs:__imp_LoadLibraryExW
0x1800abff7  mov     cs:hModule, rax
0x1800abffe  test    rax, rax
0x1800ac001  jz      loc_1800AC2C0
0x1800ac007  lea     rdx, aBcryptopenalgo; "BCryptOpenAlgorithmProvider"
0x1800ac00e  mov     rcx, rax; hModule
0x1800ac011  call    cs:__imp_GetProcAddress
0x1800ac017  mov     cs:qword_1802B5A80, rax
0x1800ac01e  test    rax, rax
0x1800ac021  jz      loc_1800AC2C0
0x1800ac027  lea     rdx, aBcryptgetprope; "BCryptGetProperty"
0x1800ac02e  mov     rcx, cs:hModule; hModule
0x1800ac035  call    cs:__imp_GetProcAddress
0x1800ac03b  mov     cs:qword_1802B5A88, rax
0x1800ac042  test    rax, rax
0x1800ac045  jz      loc_1800AC2C0
0x1800ac04b  lea     rdx, aBcryptcreateha; "BCryptCreateHash"
0x1800ac052  mov     rcx, cs:hModule; hModule
0x1800ac059  call    cs:__imp_GetProcAddress
0x1800ac05f  mov     qword ptr cs:xmmword_1802B5A90, rax
0x1800ac066  test    rax, rax
0x1800ac069  jz      loc_1800AC2C0
0x1800ac06f  lea     rdx, aBcrypthashdata; "BCryptHashData"
0x1800ac076  mov     rcx, cs:hModule; hModule
0x1800ac07d  call    cs:__imp_GetProcAddress
0x1800ac083  mov     qword ptr cs:xmmword_1802B5A90+8, rax
0x1800ac08a  test    rax, rax
0x1800ac08d  jz      loc_1800AC2C0
0x1800ac093  lea     rdx, aBcryptdestroyh; "BCryptDestroyHash"
0x1800ac09a  mov     rcx, cs:hModule; hModule
0x1800ac0a1  call    cs:__imp_GetProcAddress
0x1800ac0a7  mov     qword ptr cs:xmmword_1802B5AA0, rax
0x1800ac0ae  test    rax, rax
0x1800ac0b1  jz      loc_1800AC2C0
0x1800ac0b7  lea     rdx, aBcryptfinishha; "BCryptFinishHash"
0x1800ac0be  mov     rcx, cs:hModule; hModule
0x1800ac0c5  call    cs:__imp_GetProcAddress
0x1800ac0cb  mov     qword ptr cs:xmmword_1802B5AA0+8, rax
0x1800ac0d2  test    rax, rax
0x1800ac0d5  jz      loc_1800AC2C0
0x1800ac0db  lea     rdx, aBcryptclosealg; "BCryptCloseAlgorithmProvider"
0x1800ac0e2  mov     rcx, cs:hModule; hModule
0x1800ac0e9  call    cs:__imp_GetProcAddress
0x1800ac0ef  mov     rcx, rax
0x1800ac0f2  mov     cs:qword_1802B5AB0, rax
0x1800ac0f9  test    rax, rax
0x1800ac0fc  jz      loc_1800AC2C0
0x1800ac102  mov     cs:dword_1802B5AB8, 1
0x1800ac10c  jmp     short loc_1800AC115
0x1800ac10e  mov     rcx, cs:qword_1802B5AB0
0x1800ac115  mov     r10, cs:qword_1802B5A80
0x1800ac11c  mov     rbx, cs:qword_1802B5A88
0x1800ac123  mov     rax, qword ptr cs:xmmword_1802B5A90
0x1800ac12a  mov     qword ptr [rsp+228h+var_138], rax
0x1800ac132  mov     rax, qword ptr cs:xmmword_1802B5A90+8
0x1800ac139  mov     qword ptr [rsp+228h+var_138+8], rax
0x1800ac141  mov     rax, qword ptr cs:xmmword_1802B5AA0
0x1800ac148  mov     qword ptr [rsp+228h+var_128], rax
0x1800ac150  mov     rax, qword ptr cs:xmmword_1802B5AA0+8
0x1800ac157  mov     qword ptr [rsp+228h+var_128+8], rax
0x1800ac15f  mov     dword ptr [rsp+228h+var_110], 1
0x1800ac16a  mov     eax, cs:dword_1802B5ABC
0x1800ac170  mov     dword ptr [rsp+228h+var_110+4], eax
0x1800ac177  mov     [rsp+228h+var_1D8], r10
0x1800ac17c  mov     [rsp+228h+var_1D0], rbx
0x1800ac181  movaps  xmm0, [rsp+228h+var_138]
0x1800ac189  movaps  [rsp+228h+var_1C8], xmm0
0x1800ac18e  movaps  xmm1, [rsp+228h+var_128]
0x1800ac196  movaps  [rsp+228h+var_1B8], xmm1
0x1800ac19b  mov     [rsp+228h+var_1A8], rcx
0x1800ac1a3  mov     rax, [rsp+228h+var_110]
0x1800ac1ab  mov     [rsp+228h+var_1A0], rax
0x1800ac1b3  xor     r15d, r15d
0x1800ac1b6  mov     [rsp+228h+var_198], r15
0x1800ac1be  mov     [rsp+228h+var_190], r15
0x1800ac1c6  xor     r9d, r9d
0x1800ac1c9  xor     r8d, r8d
0x1800ac1cc  lea     rdx, aSha256; "SHA256"
0x1800ac1d3  lea     rcx, [rsp+228h+var_198]
0x1800ac1db  call    r10 ; qword_1802B5A80
0x1800ac1de  test    eax, eax
0x1800ac1e0  js      loc_1800AC2E5
0x1800ac1e6  mov     [rsp+228h+var_1F8], r15d
0x1800ac1eb  mov     [rsp+228h+var_200], r15d
0x1800ac1f0  lea     rax, [rsp+228h+var_1F8]
0x1800ac1f5  mov     [rsp+228h+var_208], rax
0x1800ac1fa  mov     r9d, 4
0x1800ac200  lea     r8, [rsp+228h+var_190]
0x1800ac208  lea     rdx, aHashdigestleng; "HashDigestLength"
0x1800ac20f  mov     rcx, [rsp+228h+var_198]
0x1800ac217  call    rbx ; qword_1802B5A88
0x1800ac219  test    eax, eax
0x1800ac21b  js      loc_1800AC2FA
0x1800ac221  mov     [rsp+228h+var_200], r15d
0x1800ac226  lea     rax, [rsp+228h+var_1F8]
0x1800ac22b  mov     [rsp+228h+var_208], rax
0x1800ac230  mov     r9d, 4
0x1800ac236  lea     r8, [rsp+228h+var_190+4]
0x1800ac23e  lea     rdx, aObjectlength; "ObjectLength"
0x1800ac245  mov     rcx, [rsp+228h+var_198]
0x1800ac24d  call    rbx ; qword_1802B5A88
0x1800ac24f  test    eax, eax
0x1800ac251  js      loc_1800AC30F
0x1800ac257  mov     r9, r14
0x1800ac25a  mov     r8, rsi
0x1800ac25d  lea     rdx, [rsp+228h+var_148]
0x1800ac265  lea     rcx, [rsp+228h+var_1D8]
0x1800ac26a  call    _anonymous_namespace___SHA256Helper__hash
0x1800ac26f  movups  xmm0, xmmword ptr [rax]
0x1800ac272  movups  xmmword ptr [rdi], xmm0
0x1800ac275  movups  xmm1, xmmword ptr [rax+10h]
0x1800ac279  movups  xmmword ptr [rdi+10h], xmm1
0x1800ac27d  mov     rcx, [rsp+228h+var_198]
0x1800ac285  test    rcx, rcx
0x1800ac288  jz      short loc_1800AC294
0x1800ac28a  xor     edx, edx
0x1800ac28c  call    [rsp+228h+var_1A8]
0x1800ac293  nop
0x1800ac294  mov     rax, rdi
0x1800ac297  mov     rcx, [rsp+228h+var_28]
0x1800ac29f  xor     rcx, rsp; StackCookie
0x1800ac2a2  call    __security_check_cookie
0x1800ac2a7  lea     r11, [rsp+228h+var_18]
0x1800ac2af  mov     rbx, [r11+20h]
0x1800ac2b3  mov     rsi, [r11+38h]
0x1800ac2b7  mov     rsp, r11
0x1800ac2ba  pop     r15
0x1800ac2bc  pop     r14
0x1800ac2be  pop     rdi
0x1800ac2bf  retn
0x1800ac2c0  mov     cs:dword_1802B5AB8, 2
0x1800ac2ca  call    cs:__imp_GetLastError
0x1800ac2d0  mov     [rsp+228h+pExceptionObject], eax
0x1800ac2d4  lea     rdx, __TI1?AUFailedLibraryBinding@?A0x8ad9c2b9@@; pThrowInfo
0x1800ac2db  lea     rcx, [rsp+228h+pExceptionObject]; pExceptionObject
0x1800ac2e0  call    _CxxThrowException_0
0x1800ac2e5  mov     [rsp+228h+var_1F0], eax
0x1800ac2e9  lea     rdx, __TI1?AUOpenAlgorithmError@?A0x8ad9c2b9@@; pThrowInfo
0x1800ac2f0  lea     rcx, [rsp+228h+var_1F0]; pExceptionObject
0x1800ac2f5  call    _CxxThrowException_0
0x1800ac2fa  mov     [rsp+228h+var_1EC], eax
0x1800ac2fe  lea     rdx, __TI1?AUHashLengthPropertyError@?A0x8ad9c2b9@@; pThrowInfo
0x1800ac305  lea     rcx, [rsp+228h+var_1EC]; pExceptionObject
0x1800ac30a  call    _CxxThrowException_0
0x1800ac30f  mov     [rsp+228h+var_1E8], eax
0x1800ac313  lea     rdx, __TI1?AUObjectLengthPropertyError@?A0x8ad9c2b9@@; pThrowInfo
0x1800ac31a  lea     rcx, [rsp+228h+var_1E8]; pExceptionObject
0x1800ac31f  call    _CxxThrowException_0
```
