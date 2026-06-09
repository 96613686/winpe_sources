# OString::Compare(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,bool)

- ea: `0x1800384bc`
- end: `0x18003865d`
- name: `?Compare@OString@@SAHAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@0_N@Z`
- size: `417`
- prototype: `__int64 __fastcall(LPCWCH lpString1, LPCWCH lpString2)`
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18013a878`
- `0x18013a920`

## callees

- `0x180008f14`
- `0x1800384bc`
- `0x1800409e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800385cc`
- `KERNEL32!GetLastError` at `0x1800385cc`
- `KERNEL32!CompareStringEx` at `0x18003857a`
- `KERNEL32!CompareStringEx` at `0x1800385c2`
- `KERNEL32!CompareStringEx` at `0x18003857a`
- `KERNEL32!CompareStringEx` at `0x1800385c2`

## pseudocode

```c
__int64 __fastcall OString::Compare(const WCHAR *lpString1, const WCHAR *lpString2)
{
  const WCHAR *v2; // rdi
  const WCHAR *v3; // rsi
  unsigned __int64 v4; // rbp
  unsigned __int64 v5; // r15
  int cchCount2; // ebx
  int v7; // eax
  int v8; // eax
  int v9; // ebx
  int v10; // eax
  int pExceptionObject; // [rsp+50h] [rbp-3A8h] BYREF
  __int16 v14; // [rsp+54h] [rbp-3A4h]
  DWORD LastError; // [rsp+254h] [rbp-1A4h]
  __int16 v16; // [rsp+258h] [rbp-1A0h]
  __int16 v17; // [rsp+358h] [rbp-A0h]
  int v18; // [rsp+3D8h] [rbp-20h]

  v2 = lpString2;
  v3 = lpString1;
  if ( *((_QWORD *)lpString2 + 3) > 7u )
    v2 = *(const WCHAR **)lpString2;
  if ( *((_QWORD *)lpString1 + 3) > 7u )
    v3 = *(const WCHAR **)lpString1;
  if ( v3 && *v3 )
  {
    if ( v2 && *v2 )
    {
      v4 = -1;
      v5 = -1;
      do
        ++v5;
      while ( v3[v5] );
      do
        ++v4;
      while ( v2[v4] );
      cchCount2 = OcfxInt32FromSize_t(v4);
      v7 = OcfxInt32FromSize_t(v5);
      v8 = CompareStringEx(&LocaleName, 1u, v3, v7, v2, cchCount2, 0, 0, 0);
      if ( !v8 )
      {
        v9 = OcfxInt32FromSize_t(v4);
        v10 = OcfxInt32FromSize_t(v5);
        v8 = CompareStringEx(L"en-US", 1u, v3, v10, v2, v9, 0, 0, 0);
        if ( !v8 )
        {
          pExceptionObject = 15;
          LastError = GetLastError();
          v18 = 808464432;
          v17 = 0;
          v16 = 0;
          v14 = 0;
          throw (OException *)&pExceptionObject;
        }
      }
      return (unsigned int)(v8 - 2);
    }
    else
    {
      return 1;
    }
  }
  else if ( v2 && *v2 )
  {
    return (unsigned int)-1;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x1800384bc  mov     rax, rsp
0x1800384bf  mov     [rax+8], rbx
0x1800384c3  mov     [rax+10h], rbp
0x1800384c7  mov     [rax+18h], rsi
0x1800384cb  mov     [rax+20h], rdi
0x1800384cf  push    r12
0x1800384d1  push    r14
0x1800384d3  push    r15
0x1800384d5  sub     rsp, 3E0h
0x1800384dc  cmp     qword ptr [rdx+18h], 7
0x1800384e1  mov     rdi, rdx
0x1800384e4  mov     rsi, rcx
0x1800384e7  jbe     short loc_1800384EC
0x1800384e9  mov     rdi, [rdx]
0x1800384ec  cmp     qword ptr [rcx+18h], 7
0x1800384f1  jbe     short loc_1800384F6
0x1800384f3  mov     rsi, [rcx]
0x1800384f6  xor     r12d, r12d
0x1800384f9  test    rsi, rsi
0x1800384fc  jz      loc_180038624
0x180038502  cmp     r12w, [rsi]
0x180038506  jz      loc_180038624
0x18003850c  test    rdi, rdi
0x18003850f  jz      loc_18003861C
0x180038515  cmp     r12w, [rdi]
0x180038519  jz      loc_18003861C
0x18003851f  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180038523  mov     r15, rbp
0x180038526  inc     r15
0x180038529  cmp     [rsi+r15*2], r12w
0x18003852e  jnz     short loc_180038526
0x180038530  inc     rbp
0x180038533  cmp     [rdi+rbp*2], r12w
0x180038538  jnz     short loc_180038530
0x18003853a  mov     rcx, rbp; unsigned __int64
0x18003853d  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x180038542  mov     rcx, r15; unsigned __int64
0x180038545  mov     ebx, eax
0x180038547  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x18003854c  mov     [rsp+3F8h+lParam], r12; lParam
0x180038551  lea     rcx, LocaleName; lpLocaleName
0x180038558  mov     [rsp+3F8h+lpReserved], r12; lpReserved
0x18003855d  mov     r14d, 1
0x180038563  mov     [rsp+3F8h+lpVersionInformation], r12; lpVersionInformation
0x180038568  mov     r9d, eax; cchCount1
0x18003856b  mov     [rsp+3F8h+cchCount2], ebx; cchCount2
0x18003856f  mov     r8, rsi; lpString1
0x180038572  mov     edx, r14d; dwCmpFlags
0x180038575  mov     [rsp+3F8h+lpString2], rdi; lpString2
0x18003857a  call    cs:__imp_CompareStringEx
0x180038580  test    eax, eax
0x180038582  jnz     loc_180038616
0x180038588  mov     rcx, rbp; unsigned __int64
0x18003858b  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x180038590  mov     rcx, r15; unsigned __int64
0x180038593  mov     ebx, eax
0x180038595  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x18003859a  mov     [rsp+3F8h+lParam], r12; lParam
0x18003859f  lea     rcx, aEnUs; "en-US"
0x1800385a6  mov     [rsp+3F8h+lpReserved], r12; lpReserved
0x1800385ab  mov     r9d, eax; cchCount1
0x1800385ae  mov     [rsp+3F8h+lpVersionInformation], r12; lpVersionInformation
0x1800385b3  mov     r8, rsi; lpString1
0x1800385b6  mov     [rsp+3F8h+cchCount2], ebx; cchCount2
0x1800385ba  mov     edx, r14d; dwCmpFlags
0x1800385bd  mov     [rsp+3F8h+lpString2], rdi; lpString2
0x1800385c2  call    cs:__imp_CompareStringEx
0x1800385c8  test    eax, eax
0x1800385ca  jnz     short loc_180038616
0x1800385cc  call    cs:__imp_GetLastError
0x1800385d2  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x1800385d9  mov     [rsp+3F8h+pExceptionObject], 0Fh
0x1800385e1  lea     rcx, [rsp+3F8h+pExceptionObject]; pExceptionObject
0x1800385e6  mov     [rsp+3F8h+var_1A4], eax
0x1800385ed  mov     [rsp+3F8h+var_20], 30303030h
0x1800385f8  mov     [rsp+3F8h+var_A0], r12w
0x180038601  mov     [rsp+3F8h+var_1A0], r12w
0x18003860a  mov     [rsp+3F8h+var_3A4], r12w
0x180038610  call    _CxxThrowException
0x180038616  lea     r14d, [rax-2]
0x18003861a  jmp     short loc_180038638
0x18003861c  mov     r14d, 1
0x180038622  jmp     short loc_180038638
0x180038624  test    rdi, rdi
0x180038627  jz      short loc_180038635
0x180038629  cmp     r12w, [rdi]
0x18003862d  jz      short loc_180038635
0x18003862f  or      r14, 0FFFFFFFFFFFFFFFFh
0x180038633  jmp     short loc_180038638
0x180038635  mov     r14d, r12d
0x180038638  lea     r11, [rsp+3F8h+var_18]
0x180038640  mov     eax, r14d
0x180038643  mov     rbx, [r11+20h]
0x180038647  mov     rbp, [r11+28h]
0x18003864b  mov     rsi, [r11+30h]
0x18003864f  mov     rdi, [r11+38h]
0x180038653  mov     rsp, r11
0x180038656  pop     r15
0x180038658  pop     r14
0x18003865a  pop     r12
0x18003865c  retn
```
