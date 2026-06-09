# OString::StartsWith(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,bool)

- ea: `0x180009e9c`
- end: `0x18000a0ea`
- name: `?StartsWith@OString@@SA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0_N@Z`
- size: `590`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180007a48`
- `0x18000a594`
- `0x1800fca04`

## callees

- `0x180008f14`
- `0x180009e9c`
- `0x18000c0a4`
- `0x18001afdc`
- `0x18003e690`
- `0x1800409e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000a0a4`
- `KERNEL32!GetLastError` at `0x18000a0a4`
- `KERNEL32!CompareStringEx` at `0x180009fba`
- `KERNEL32!CompareStringEx` at `0x18000a096`
- `KERNEL32!CompareStringEx` at `0x180009fba`
- `KERNEL32!CompareStringEx` at `0x18000a096`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool __fastcall OString::StartsWith(__int64 a1, __int64 *a2, unsigned __int8 a3)
{
  int v3; // r12d
  __int64 *lpString2; // rdi
  unsigned __int64 v5; // rbx
  const WCHAR *v6; // r15
  unsigned __int64 v7; // r14
  unsigned __int64 v8; // rsi
  unsigned __int64 v9; // rax
  DWORD v10; // r12d
  int cchCount2; // ebx
  int v12; // eax
  int v13; // eax
  int v14; // eax
  bool v15; // bl
  int v17; // ebx
  int v18; // eax
  int pExceptionObject; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v20; // [rsp+64h] [rbp-9Ch]
  DWORD LastError; // [rsp+264h] [rbp+164h]
  __int16 v22; // [rsp+268h] [rbp+168h]
  __int16 v23; // [rsp+368h] [rbp+268h]
  int v24; // [rsp+3E8h] [rbp+2E8h]
  LPCWCH lpString1[3]; // [rsp+3F0h] [rbp+2F0h] BYREF
  unsigned __int64 v26; // [rsp+408h] [rbp+308h]

  v3 = a3;
  lpString2 = a2;
  v5 = a2[2];
  if ( v5 > *(_QWORD *)(a1 + 16) )
    return 0;
  _mm_lfence();
  std::wstring::substr(a1, lpString1, 0, a2[2]);
  if ( (unsigned __int64)lpString2[3] > 7 )
    lpString2 = (__int64 *)*lpString2;
  v6 = (const WCHAR *)lpString1;
  if ( v26 > 7 )
    v6 = lpString1[0];
  if ( v6 && *v6 )
  {
    if ( lpString2 && *(_WORD *)lpString2 )
    {
      _mm_lfence();
      v7 = v5;
      v8 = v5;
      if ( v5 )
      {
        v8 = -1;
        v9 = -1;
        do
          ++v9;
        while ( v6[v9] );
        do
          ++v8;
        while ( *((_WORD *)lpString2 + v8) );
        v7 = v5;
        if ( v9 <= v5 )
          v7 = v9;
        if ( v8 > v5 )
          v8 = v5;
      }
      v10 = v3 ^ 1;
      cchCount2 = OcfxInt32FromSize_t(v8);
      v12 = OcfxInt32FromSize_t(v7);
      v13 = CompareStringEx(&LocaleName, v10, v6, v12, (LPCWCH)lpString2, cchCount2, 0, 0, 0);
      if ( !v13 )
      {
        _mm_lfence();
        v17 = OcfxInt32FromSize_t(v8);
        v18 = OcfxInt32FromSize_t(v7);
        v13 = CompareStringEx(L"en-US", v10, v6, v18, (LPCWCH)lpString2, v17, 0, 0, 0);
        if ( !v13 )
        {
          pExceptionObject = 15;
          LastError = GetLastError();
          v24 = 808464432;
          v23 = 0;
          v22 = 0;
          v20 = 0;
          throw (OException *)&pExceptionObject;
        }
      }
      v14 = v13 - 2;
    }
    else
    {
      v14 = 1;
    }
  }
  else if ( lpString2 && *(_WORD *)lpString2 )
  {
    v14 = -1;
  }
  else
  {
    v14 = 0;
  }
  v15 = v14 == 0;
  std::wstring::_Tidy_deallocate(lpString1);
  lpString1[0] = (LPCWCH)19937;
  lpString1[2] = 0;
  v26 = 15;
  return v15;
}

```

## disassembly

```asm
0x180009e9c  mov     [rsp-8+arg_10], rbx
0x180009ea1  push    rbp
0x180009ea2  push    rsi
0x180009ea3  push    rdi
0x180009ea4  push    r12
0x180009ea6  push    r13
0x180009ea8  push    r14
0x180009eaa  push    r15
0x180009eac  lea     rbp, [rsp-320h]
0x180009eb4  sub     rsp, 420h
0x180009ebb  mov     rax, cs:__security_cookie
0x180009ec2  xor     rax, rsp
0x180009ec5  mov     [rbp+350h+var_40], rax
0x180009ecc  movzx   r12d, r8b
0x180009ed0  mov     rdi, rdx
0x180009ed3  mov     rbx, [rdx+10h]
0x180009ed7  cmp     rbx, [rcx+10h]
0x180009edb  ja      loc_18000A032
0x180009ee1  lfence
0x180009ee4  mov     r9, rbx
0x180009ee7  xor     r8d, r8d
0x180009eea  lea     rdx, [rbp+350h+lpString1]
0x180009ef1  call    ?substr@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x180009ef6  nop
0x180009ef7  cmp     qword ptr [rdi+18h], 7
0x180009efc  jbe     short loc_180009F01
0x180009efe  mov     rdi, [rdi]
0x180009f01  lea     r15, [rbp+350h+lpString1]
0x180009f08  cmp     [rbp+350h+var_48], 7
0x180009f10  cmova   r15, [rbp+350h+lpString1]
0x180009f18  xor     r13d, r13d
0x180009f1b  test    r15, r15
0x180009f1e  jz      loc_18000A03D
0x180009f24  cmp     r13w, [r15]
0x180009f28  jz      loc_18000A03D
0x180009f2e  test    rdi, rdi
0x180009f31  jz      loc_18000A036
0x180009f37  cmp     r13w, [rdi]
0x180009f3b  jz      loc_18000A036
0x180009f41  lfence
0x180009f44  mov     r14, rbx
0x180009f47  mov     rsi, rbx
0x180009f4a  test    rbx, rbx
0x180009f4d  jz      short loc_180009F7C
0x180009f4f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180009f53  mov     rax, rsi
0x180009f56  inc     rax
0x180009f59  cmp     [r15+rax*2], r13w
0x180009f5e  jnz     short loc_180009F56
0x180009f60  inc     rsi
0x180009f63  cmp     [rdi+rsi*2], r13w
0x180009f68  jnz     short loc_180009F60
0x180009f6a  mov     r14, rbx
0x180009f6d  cmp     rax, rbx
0x180009f70  cmovbe  r14, rax
0x180009f74  cmp     rsi, rbx
0x180009f77  jbe     short loc_180009F7C
0x180009f79  mov     rsi, rbx
0x180009f7c  xor     r12d, 1
0x180009f80  mov     rcx, rsi; unsigned __int64
0x180009f83  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x180009f88  mov     ebx, eax
0x180009f8a  mov     rcx, r14; unsigned __int64
0x180009f8d  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x180009f92  mov     [rsp+450h+lParam], r13; lParam
0x180009f97  mov     [rsp+450h+lpReserved], r13; lpReserved
0x180009f9c  mov     [rsp+450h+lpVersionInformation], r13; lpVersionInformation
0x180009fa1  mov     [rsp+450h+cchCount2], ebx; cchCount2
0x180009fa5  mov     [rsp+450h+lpString2], rdi; lpString2
0x180009faa  mov     r9d, eax; cchCount1
0x180009fad  mov     r8, r15; lpString1
0x180009fb0  mov     edx, r12d; dwCmpFlags
0x180009fb3  lea     rcx, LocaleName; lpLocaleName
0x180009fba  call    cs:__imp_CompareStringEx
0x180009fc0  test    eax, eax
0x180009fc2  jz      loc_18000A059
0x180009fc8  add     eax, 0FFFFFFFEh
0x180009fcb  test    eax, eax
0x180009fcd  setz    bl
0x180009fd0  lea     rcx, [rbp+350h+lpString1]
0x180009fd7  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180009fdc  nop
0x180009fdd  lea     rax, [rbp+350h+lpString1]
0x180009fe4  mov     [rsp+450h+var_400], rax
0x180009fe9  mov     [rbp+350h+lpString1], 4DE1h
0x180009ff4  mov     [rbp+350h+var_50], r13
0x180009ffb  mov     [rbp+350h+var_48], 0Fh
0x18000a006  mov     al, bl
0x18000a008  mov     rcx, [rbp+350h+var_40]
0x18000a00f  xor     rcx, rsp; StackCookie
0x18000a012  call    __security_check_cookie
0x18000a017  mov     rbx, [rsp+450h+arg_10]
0x18000a01f  add     rsp, 420h
0x18000a026  pop     r15
0x18000a028  pop     r14
0x18000a02a  pop     r13
0x18000a02c  pop     r12
0x18000a02e  pop     rdi
0x18000a02f  pop     rsi
0x18000a030  pop     rbp
0x18000a031  retn
0x18000a032  xor     al, al
0x18000a034  jmp     short loc_18000A008
0x18000a036  mov     eax, 1
0x18000a03b  jmp     short loc_180009FCB
0x18000a03d  test    rdi, rdi
0x18000a040  jz      short loc_18000A051
0x18000a042  cmp     r13w, [rdi]
0x18000a046  jz      short loc_18000A051
0x18000a048  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a04c  jmp     loc_180009FCB
0x18000a051  mov     eax, r13d
0x18000a054  jmp     loc_180009FCB
0x18000a059  lfence
0x18000a05c  mov     rcx, rsi; unsigned __int64
0x18000a05f  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x18000a064  mov     ebx, eax
0x18000a066  mov     rcx, r14; unsigned __int64
0x18000a069  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x18000a06e  mov     [rsp+450h+lParam], r13; lParam
0x18000a073  mov     [rsp+450h+lpReserved], r13; lpReserved
0x18000a078  mov     [rsp+450h+lpVersionInformation], r13; lpVersionInformation
0x18000a07d  mov     [rsp+450h+cchCount2], ebx; cchCount2
0x18000a081  mov     [rsp+450h+lpString2], rdi; lpString2
0x18000a086  mov     r9d, eax; cchCount1
0x18000a089  mov     r8, r15; lpString1
0x18000a08c  mov     edx, r12d; dwCmpFlags
0x18000a08f  lea     rcx, aEnUs; "en-US"
0x18000a096  call    cs:__imp_CompareStringEx
0x18000a09c  test    eax, eax
0x18000a09e  jnz     loc_180009FC8
0x18000a0a4  call    cs:__imp_GetLastError
0x18000a0aa  mov     [rsp+450h+pExceptionObject], 0Fh
0x18000a0b2  mov     [rbp+350h+var_1EC], eax
0x18000a0b8  mov     [rbp+350h+var_68], 30303030h
0x18000a0c2  mov     [rbp+350h+var_E8], r13w
0x18000a0ca  mov     [rbp+350h+var_1E8], r13w
0x18000a0d2  mov     [rsp+450h+var_3EC], r13w
0x18000a0d8  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x18000a0df  lea     rcx, [rsp+450h+pExceptionObject]; pExceptionObject
0x18000a0e4  call    _CxxThrowException
```
