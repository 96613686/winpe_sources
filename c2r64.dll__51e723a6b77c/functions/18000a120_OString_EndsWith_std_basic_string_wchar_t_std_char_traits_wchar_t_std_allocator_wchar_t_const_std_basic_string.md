# OString::EndsWith(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,bool)

- ea: `0x18000a120`
- end: `0x18000a377`
- name: `?EndsWith@OString@@SA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0_N@Z`
- size: `599`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000ae28`
- `0x1800fca04`
- `0x18013b4d8`
- `0x18013b56c`
- `0x18013b600`
- `0x18013b6ac`

## callees

- `0x180008f14`
- `0x18000a120`
- `0x18000c0a4`
- `0x18001afdc`
- `0x18003e690`
- `0x1800409e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000a331`
- `KERNEL32!GetLastError` at `0x18000a331`
- `KERNEL32!CompareStringEx` at `0x18000a24b`
- `KERNEL32!CompareStringEx` at `0x18000a323`
- `KERNEL32!CompareStringEx` at `0x18000a24b`
- `KERNEL32!CompareStringEx` at `0x18000a323`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
bool __fastcall OString::EndsWith(__int64 a1, __int64 *a2, unsigned __int8 a3)
{
  int v3; // r13d
  __int64 *lpString2; // rdi
  unsigned __int64 v5; // rsi
  unsigned __int64 v6; // r8
  int v7; // ebx
  const WCHAR *v8; // r12
  unsigned __int64 v9; // r15
  unsigned __int64 v10; // r14
  unsigned __int64 v11; // rax
  int cchCount2; // ebx
  int v13; // eax
  int v14; // eax
  int v16; // ebx
  int v17; // eax
  int pExceptionObject; // [rsp+60h] [rbp-A0h] BYREF
  __int16 v19; // [rsp+64h] [rbp-9Ch]
  DWORD LastError; // [rsp+264h] [rbp+164h]
  __int16 v21; // [rsp+268h] [rbp+168h]
  __int16 v22; // [rsp+368h] [rbp+268h]
  int v23; // [rsp+3E8h] [rbp+2E8h]
  LPCWCH lpString1[3]; // [rsp+3F0h] [rbp+2F0h] BYREF
  unsigned __int64 v25; // [rsp+408h] [rbp+308h]

  v3 = a3;
  lpString2 = a2;
  v5 = a2[2];
  v6 = *(_QWORD *)(a1 + 16);
  if ( v5 > v6 )
    return 0;
  _mm_lfence();
  v7 = -1;
  std::wstring::substr(a1, lpString1, v6 - v5, -1);
  if ( (unsigned __int64)lpString2[3] > 7 )
    lpString2 = (__int64 *)*lpString2;
  v8 = (const WCHAR *)lpString1;
  if ( v25 > 7 )
    v8 = lpString1[0];
  if ( v8 && *v8 )
  {
    if ( lpString2 && *(_WORD *)lpString2 )
    {
      _mm_lfence();
      v9 = v5;
      v10 = v5;
      if ( v5 )
      {
        v11 = -1;
        do
          ++v11;
        while ( v8[v11] );
        v10 = -1;
        do
          ++v10;
        while ( *((_WORD *)lpString2 + v10) );
        v9 = v5;
        if ( v11 <= v5 )
          v9 = v11;
        if ( v10 > v5 )
          v10 = v5;
      }
      cchCount2 = OcfxInt32FromSize_t(v10);
      v13 = OcfxInt32FromSize_t(v9);
      v14 = CompareStringEx(&LocaleName, v3 ^ 1, v8, v13, (LPCWCH)lpString2, cchCount2, 0, 0, 0);
      if ( !v14 )
      {
        _mm_lfence();
        v16 = OcfxInt32FromSize_t(v10);
        v17 = OcfxInt32FromSize_t(v9);
        v14 = CompareStringEx(L"en-US", v3 ^ 1, v8, v17, (LPCWCH)lpString2, v16, 0, 0, 0);
        if ( !v14 )
        {
          pExceptionObject = 15;
          LastError = GetLastError();
          v23 = 808464432;
          v22 = 0;
          v21 = 0;
          v19 = 0;
          throw (OException *)&pExceptionObject;
        }
      }
      v7 = v14 - 2;
    }
    else
    {
      v7 = 1;
    }
  }
  else if ( !lpString2 || !*(_WORD *)lpString2 )
  {
    v7 = 0;
  }
  std::wstring::_Tidy_deallocate(lpString1);
  lpString1[0] = (LPCWCH)19937;
  lpString1[2] = 0;
  v25 = 15;
  return v7 == 0;
}

```

## disassembly

```asm
0x18000a120  mov     [rsp-8+arg_10], rbx
0x18000a125  push    rbp
0x18000a126  push    rsi
0x18000a127  push    rdi
0x18000a128  push    r12
0x18000a12a  push    r13
0x18000a12c  push    r14
0x18000a12e  push    r15
0x18000a130  lea     rbp, [rsp-320h]
0x18000a138  sub     rsp, 420h
0x18000a13f  mov     rax, cs:__security_cookie
0x18000a146  xor     rax, rsp
0x18000a149  mov     [rbp+350h+var_40], rax
0x18000a150  movzx   r13d, r8b
0x18000a154  mov     rdi, rdx
0x18000a157  mov     rsi, [rdx+10h]
0x18000a15b  mov     r8, [rcx+10h]
0x18000a15f  cmp     rsi, r8
0x18000a162  ja      loc_18000A2C6
0x18000a168  lfence
0x18000a16b  sub     r8, rsi
0x18000a16e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000a172  mov     r9, rbx
0x18000a175  lea     rdx, [rbp+350h+lpString1]
0x18000a17c  call    ?substr@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBA?AV12@_K0@Z; std::wstring::substr(unsigned __int64,unsigned __int64)
0x18000a181  nop
0x18000a182  cmp     qword ptr [rdi+18h], 7
0x18000a187  jbe     short loc_18000A18C
0x18000a189  mov     rdi, [rdi]
0x18000a18c  lea     r12, [rbp+350h+lpString1]
0x18000a193  cmp     [rbp+350h+var_48], 7
0x18000a19b  cmova   r12, [rbp+350h+lpString1]
0x18000a1a3  xor     r14d, r14d
0x18000a1a6  test    r12, r12
0x18000a1a9  jz      loc_18000A2D1
0x18000a1af  cmp     r14w, [r12]
0x18000a1b4  jz      loc_18000A2D1
0x18000a1ba  test    rdi, rdi
0x18000a1bd  jz      loc_18000A2CA
0x18000a1c3  cmp     r14w, [rdi]
0x18000a1c7  jz      loc_18000A2CA
0x18000a1cd  lfence
0x18000a1d0  mov     r15, rsi
0x18000a1d3  mov     r14, rsi
0x18000a1d6  xor     ecx, ecx
0x18000a1d8  test    rsi, rsi
0x18000a1db  jz      short loc_18000A209
0x18000a1dd  mov     rax, rbx
0x18000a1e0  inc     rax
0x18000a1e3  cmp     [r12+rax*2], cx
0x18000a1e8  jnz     short loc_18000A1E0
0x18000a1ea  mov     r14, rbx
0x18000a1ed  inc     r14
0x18000a1f0  cmp     [rdi+r14*2], cx
0x18000a1f5  jnz     short loc_18000A1ED
0x18000a1f7  mov     r15, rsi
0x18000a1fa  cmp     rax, rsi
0x18000a1fd  cmovbe  r15, rax
0x18000a201  cmp     r14, rsi
0x18000a204  jbe     short loc_18000A209
0x18000a206  mov     r14, rsi
0x18000a209  mov     esi, r13d
0x18000a20c  xor     esi, 1
0x18000a20f  mov     rcx, r14; unsigned __int64
0x18000a212  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x18000a217  mov     ebx, eax
0x18000a219  mov     rcx, r15; unsigned __int64
0x18000a21c  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x18000a221  xor     r13d, r13d
0x18000a224  mov     [rsp+450h+lParam], r13; lParam
0x18000a229  mov     [rsp+450h+lpReserved], r13; lpReserved
0x18000a22e  mov     [rsp+450h+lpVersionInformation], r13; lpVersionInformation
0x18000a233  mov     [rsp+450h+cchCount2], ebx; cchCount2
0x18000a237  mov     [rsp+450h+lpString2], rdi; lpString2
0x18000a23c  mov     r9d, eax; cchCount1
0x18000a23f  mov     r8, r12; lpString1
0x18000a242  mov     edx, esi; dwCmpFlags
0x18000a244  lea     rcx, LocaleName; lpLocaleName
0x18000a24b  call    cs:__imp_CompareStringEx
0x18000a251  test    eax, eax
0x18000a253  jz      loc_18000A2E4
0x18000a259  xor     r14d, r14d
0x18000a25c  lea     ebx, [rax-2]
0x18000a25f  test    ebx, ebx
0x18000a261  setz    bl
0x18000a264  lea     rcx, [rbp+350h+lpString1]
0x18000a26b  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000a270  nop
0x18000a271  lea     rax, [rbp+350h+lpString1]
0x18000a278  mov     [rsp+450h+var_400], rax
0x18000a27d  mov     [rbp+350h+lpString1], 4DE1h
0x18000a288  mov     [rbp+350h+var_50], r14
0x18000a28f  mov     [rbp+350h+var_48], 0Fh
0x18000a29a  mov     al, bl
0x18000a29c  mov     rcx, [rbp+350h+var_40]
0x18000a2a3  xor     rcx, rsp; StackCookie
0x18000a2a6  call    __security_check_cookie
0x18000a2ab  mov     rbx, [rsp+450h+arg_10]
0x18000a2b3  add     rsp, 420h
0x18000a2ba  pop     r15
0x18000a2bc  pop     r14
0x18000a2be  pop     r13
0x18000a2c0  pop     r12
0x18000a2c2  pop     rdi
0x18000a2c3  pop     rsi
0x18000a2c4  pop     rbp
0x18000a2c5  retn
0x18000a2c6  xor     al, al
0x18000a2c8  jmp     short loc_18000A29C
0x18000a2ca  mov     ebx, 1
0x18000a2cf  jmp     short loc_18000A25F
0x18000a2d1  test    rdi, rdi
0x18000a2d4  jz      short loc_18000A2DC
0x18000a2d6  cmp     r14w, [rdi]
0x18000a2da  jnz     short loc_18000A25F
0x18000a2dc  mov     ebx, r14d
0x18000a2df  jmp     loc_18000A25F
0x18000a2e4  lfence
0x18000a2e7  mov     rcx, r14; unsigned __int64
0x18000a2ea  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x18000a2ef  mov     ebx, eax
0x18000a2f1  mov     rcx, r15; unsigned __int64
0x18000a2f4  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x18000a2f9  xor     r14d, r14d
0x18000a2fc  mov     [rsp+450h+lParam], r14; lParam
0x18000a301  mov     [rsp+450h+lpReserved], r14; lpReserved
0x18000a306  mov     [rsp+450h+lpVersionInformation], r14; lpVersionInformation
0x18000a30b  mov     [rsp+450h+cchCount2], ebx; cchCount2
0x18000a30f  mov     [rsp+450h+lpString2], rdi; lpString2
0x18000a314  mov     r9d, eax; cchCount1
0x18000a317  mov     r8, r12; lpString1
0x18000a31a  mov     edx, esi; dwCmpFlags
0x18000a31c  lea     rcx, aEnUs; "en-US"
0x18000a323  call    cs:__imp_CompareStringEx
0x18000a329  test    eax, eax
0x18000a32b  jnz     loc_18000A25C
0x18000a331  call    cs:__imp_GetLastError
0x18000a337  mov     [rsp+450h+pExceptionObject], 0Fh
0x18000a33f  mov     [rbp+350h+var_1EC], eax
0x18000a345  mov     [rbp+350h+var_68], 30303030h
0x18000a34f  mov     [rbp+350h+var_E8], r14w
0x18000a357  mov     [rbp+350h+var_1E8], r14w
0x18000a35f  mov     [rsp+450h+var_3EC], r14w
0x18000a365  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x18000a36c  lea     rcx, [rsp+450h+pExceptionObject]; pExceptionObject
0x18000a371  call    _CxxThrowException
```
