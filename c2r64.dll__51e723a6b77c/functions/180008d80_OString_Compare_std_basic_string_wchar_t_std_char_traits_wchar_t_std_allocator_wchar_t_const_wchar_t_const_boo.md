# OString::Compare(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,wchar_t const *,bool)

- ea: `0x180008d80`
- end: `0x180008f14`
- name: `?Compare@OString@@SAHAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W_N@Z`
- size: `404`
- prototype: `__int64 __fastcall(LPCWCH lpString1, LPCWCH lpString2)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180008c14`
- `0x18004fc00`
- `0x18004fd20`

## callees

- `0x180008d80`
- `0x180008f14`
- `0x1800409e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180008eca`
- `KERNEL32!GetLastError` at `0x180008eca`
- `KERNEL32!CompareStringEx` at `0x180008e36`
- `KERNEL32!CompareStringEx` at `0x180008ebc`
- `KERNEL32!CompareStringEx` at `0x180008e36`
- `KERNEL32!CompareStringEx` at `0x180008ebc`

## pseudocode

```c
__int64 __fastcall OString::Compare(const WCHAR *lpString1, LPCWCH lpString2, unsigned __int8 a3)
{
  const WCHAR *v4; // rdi
  unsigned __int64 v5; // rsi
  unsigned __int64 v6; // r14
  DWORD v7; // r15d
  int cchCount2; // ebx
  int v9; // eax
  int v10; // eax
  int v12; // ebx
  int v13; // eax
  int pExceptionObject; // [rsp+50h] [rbp-3A8h] BYREF
  __int16 v15; // [rsp+54h] [rbp-3A4h]
  DWORD LastError; // [rsp+254h] [rbp-1A4h]
  __int16 v17; // [rsp+258h] [rbp-1A0h]
  __int16 v18; // [rsp+358h] [rbp-A0h]
  int v19; // [rsp+3D8h] [rbp-20h]

  v4 = lpString1;
  if ( *((_QWORD *)lpString1 + 3) > 7u )
    v4 = *(const WCHAR **)lpString1;
  if ( v4 && *v4 )
  {
    if ( lpString2 && *lpString2 )
    {
      v5 = -1;
      v6 = -1;
      do
        ++v6;
      while ( v4[v6] );
      do
        ++v5;
      while ( lpString2[v5] );
      v7 = a3 ^ 1;
      cchCount2 = OcfxInt32FromSize_t(v5);
      v9 = OcfxInt32FromSize_t(v6);
      v10 = CompareStringEx(&LocaleName, v7, v4, v9, lpString2, cchCount2, 0, 0, 0);
      if ( !v10 )
      {
        v12 = OcfxInt32FromSize_t(v5);
        v13 = OcfxInt32FromSize_t(v6);
        v10 = CompareStringEx(L"en-US", v7, v4, v13, lpString2, v12, 0, 0, 0);
        if ( !v10 )
        {
          pExceptionObject = 15;
          LastError = GetLastError();
          v19 = 808464432;
          v18 = 0;
          v17 = 0;
          v15 = 0;
          throw (OException *)&pExceptionObject;
        }
      }
      return (unsigned int)(v10 - 2);
    }
    else
    {
      return 1;
    }
  }
  else if ( lpString2 && *lpString2 )
  {
    return -1;
  }
  else
  {
    return 0;
  }
}

```

## disassembly

```asm
0x180008d80  mov     rax, rsp
0x180008d83  mov     [rax+8], rbx
0x180008d87  mov     [rax+10h], rbp
0x180008d8b  mov     [rax+18h], rsi
0x180008d8f  mov     [rax+20h], rdi
0x180008d93  push    r12
0x180008d95  push    r14
0x180008d97  push    r15
0x180008d99  sub     rsp, 3E0h
0x180008da0  cmp     qword ptr [rcx+18h], 7
0x180008da5  mov     rbp, rdx
0x180008da8  mov     rdi, rcx
0x180008dab  jbe     short loc_180008DB0
0x180008dad  mov     rdi, [rcx]
0x180008db0  xor     r12d, r12d
0x180008db3  test    rdi, rdi
0x180008db6  jz      loc_180008E6C
0x180008dbc  cmp     r12w, [rdi]
0x180008dc0  jz      loc_180008E6C
0x180008dc6  test    rbp, rbp
0x180008dc9  jz      loc_180008E65
0x180008dcf  cmp     r12w, [rdx]
0x180008dd3  jz      loc_180008E65
0x180008dd9  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180008ddd  mov     r14, rsi
0x180008de0  inc     r14
0x180008de3  cmp     [rdi+r14*2], r12w
0x180008de8  jnz     short loc_180008DE0
0x180008dea  inc     rsi
0x180008ded  cmp     [rdx+rsi*2], r12w
0x180008df2  jnz     short loc_180008DEA
0x180008df4  movzx   r15d, r8b
0x180008df8  mov     rcx, rsi; unsigned __int64
0x180008dfb  xor     r15d, 1
0x180008dff  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x180008e04  mov     rcx, r14; unsigned __int64
0x180008e07  mov     ebx, eax
0x180008e09  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x180008e0e  mov     [rsp+3F8h+lParam], r12; lParam
0x180008e13  lea     rcx, LocaleName; lpLocaleName
0x180008e1a  mov     [rsp+3F8h+lpReserved], r12; lpReserved
0x180008e1f  mov     r9d, eax; cchCount1
0x180008e22  mov     [rsp+3F8h+lpVersionInformation], r12; lpVersionInformation
0x180008e27  mov     r8, rdi; lpString1
0x180008e2a  mov     [rsp+3F8h+cchCount2], ebx; cchCount2
0x180008e2e  mov     edx, r15d; dwCmpFlags
0x180008e31  mov     [rsp+3F8h+lpString2], rbp; lpString2
0x180008e36  call    cs:__imp_CompareStringEx
0x180008e3c  test    eax, eax
0x180008e3e  jz      short loc_180008E82
0x180008e40  add     eax, 0FFFFFFFEh
0x180008e43  lea     r11, [rsp+3F8h+var_18]
0x180008e4b  mov     rbx, [r11+20h]
0x180008e4f  mov     rbp, [r11+28h]
0x180008e53  mov     rsi, [r11+30h]
0x180008e57  mov     rdi, [r11+38h]
0x180008e5b  mov     rsp, r11
0x180008e5e  pop     r15
0x180008e60  pop     r14
0x180008e62  pop     r12
0x180008e64  retn
0x180008e65  mov     eax, 1
0x180008e6a  jmp     short loc_180008E43
0x180008e6c  test    rbp, rbp
0x180008e6f  jz      short loc_180008E7D
0x180008e71  cmp     r12w, [rdx]
0x180008e75  jz      short loc_180008E7D
0x180008e77  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008e7b  jmp     short loc_180008E43
0x180008e7d  mov     eax, r12d
0x180008e80  jmp     short loc_180008E43
0x180008e82  mov     rcx, rsi; unsigned __int64
0x180008e85  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x180008e8a  mov     rcx, r14; unsigned __int64
0x180008e8d  mov     ebx, eax
0x180008e8f  call    ?OcfxInt32FromSize_t@@YAH_K@Z; OcfxInt32FromSize_t(unsigned __int64)
0x180008e94  mov     [rsp+3F8h+lParam], r12; lParam
0x180008e99  lea     rcx, aEnUs; "en-US"
0x180008ea0  mov     [rsp+3F8h+lpReserved], r12; lpReserved
0x180008ea5  mov     r9d, eax; cchCount1
0x180008ea8  mov     [rsp+3F8h+lpVersionInformation], r12; lpVersionInformation
0x180008ead  mov     r8, rdi; lpString1
0x180008eb0  mov     [rsp+3F8h+cchCount2], ebx; cchCount2
0x180008eb4  mov     edx, r15d; dwCmpFlags
0x180008eb7  mov     [rsp+3F8h+lpString2], rbp; lpString2
0x180008ebc  call    cs:__imp_CompareStringEx
0x180008ec2  test    eax, eax
0x180008ec4  jnz     loc_180008E40
0x180008eca  call    cs:__imp_GetLastError
0x180008ed0  lea     rdx, _TI2?AVOException@@; pThrowInfo
0x180008ed7  mov     [rsp+3F8h+pExceptionObject], 0Fh
0x180008edf  lea     rcx, [rsp+3F8h+pExceptionObject]; pExceptionObject
0x180008ee4  mov     [rsp+3F8h+var_1A4], eax
0x180008eeb  mov     [rsp+3F8h+var_20], 30303030h
0x180008ef6  mov     [rsp+3F8h+var_A0], r12w
0x180008eff  mov     [rsp+3F8h+var_1A0], r12w
0x180008f08  mov     [rsp+3F8h+var_3A4], r12w
0x180008f0e  call    _CxxThrowException
```
