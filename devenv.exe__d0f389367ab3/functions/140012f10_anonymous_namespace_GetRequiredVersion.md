# _anonymous_namespace_::GetRequiredVersion

- ea: `0x140012f10`
- end: `0x140013043`
- name: `_anonymous_namespace_::GetRequiredVersion`
- size: `307`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000ccfc`
- `0x140021988`

## callees

- `0x140001020`
- `0x140002f00`
- `0x140012f10`
- `0x140027c20`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140013014`
- `ADVAPI32!RegCloseKey` at `0x140013014`
- `ADVAPI32!RegOpenKeyExW` at `0x140012f8c`
- `ADVAPI32!RegOpenKeyExW` at `0x140012f8c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall anonymous_namespace_::GetRequiredVersion(__int64 a1, __int64 a2)
{
  HKEY v3; // rbx
  LSTATUS v4; // eax
  signed int v5; // edi
  int v6; // eax
  __int64 v7; // r8
  unsigned int v9; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v10; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v11; // [rsp+48h] [rbp-B8h]
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v13[264]; // [rsp+60h] [rbp-A0h] BYREF

  v3 = 0;
  v10 = 0u;
  v11 = 0;
  v9 = 260;
  phkResult = 0;
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\VisualStudio\\17.0", 0, 0x20019u, &phkResult);
  if ( !v4 )
  {
    v4 = 0;
    v3 = phkResult;
    *(_QWORD *)&v10 = phkResult;
    DWORD2(v10) = 0;
  }
  v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v4 <= 0 )
    v5 = v4;
  if ( v5 >= 0 )
  {
    v6 = ATL::CRegKey::QueryStringValue((ATL::CRegKey *)&v10, L"RequiredNDPVersion", v13, &v9);
    v5 = (unsigned __int16)v6 | 0x80070000;
    if ( v6 <= 0 )
      v5 = v6;
    if ( v5 >= 0 )
    {
      v7 = -1;
      do
        ++v7;
      while ( v13[v7] );
      ATL::CSimpleStringT<unsigned short,0>::SetString(a2, v13);
    }
    v3 = (HKEY)v10;
  }
  if ( v3 )
    RegCloseKey(v3);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x140012f10  mov     [rsp-8+arg_0], rbx
0x140012f15  mov     [rsp-8+arg_10], rsi
0x140012f1a  push    rbp
0x140012f1b  push    rdi
0x140012f1c  push    r14
0x140012f1e  lea     rbp, [rsp-180h]
0x140012f26  sub     rsp, 280h
0x140012f2d  mov     rax, cs:__security_cookie
0x140012f34  xor     rax, rsp
0x140012f37  mov     [rbp+190h+var_20], rax
0x140012f3e  mov     rsi, rdx
0x140012f41  xorps   xmm0, xmm0
0x140012f44  movups  [rsp+290h+var_258], xmm0
0x140012f49  xor     r14d, r14d
0x140012f4c  mov     ebx, r14d
0x140012f4f  mov     qword ptr [rsp+290h+var_258], rbx
0x140012f54  mov     dword ptr [rsp+290h+var_258+8], r14d
0x140012f59  mov     [rsp+290h+var_248], r14
0x140012f5e  mov     [rsp+290h+var_260], 104h
0x140012f66  mov     [rsp+290h+var_240], r14
0x140012f6b  lea     rax, [rsp+290h+var_240]
0x140012f70  mov     [rsp+290h+phkResult], rax; phkResult
0x140012f75  mov     r9d, 20019h; samDesired
0x140012f7b  xor     r8d, r8d; ulOptions
0x140012f7e  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\VisualStudio\\17.0"
0x140012f85  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140012f8c  call    cs:__imp_RegOpenKeyExW
0x140012f92  test    eax, eax
0x140012f94  jnz     short loc_140012FA8
0x140012f96  mov     eax, r14d
0x140012f99  mov     rbx, [rsp+290h+var_240]
0x140012f9e  mov     qword ptr [rsp+290h+var_258], rbx
0x140012fa3  mov     dword ptr [rsp+290h+var_258+8], r14d
0x140012fa8  movzx   edi, ax
0x140012fab  or      edi, 80070000h
0x140012fb1  test    eax, eax
0x140012fb3  cmovle  edi, eax
0x140012fb6  test    edi, edi
0x140012fb8  js      short loc_14001300C
0x140012fba  lea     r9, [rsp+290h+var_260]; unsigned int *
0x140012fbf  lea     r8, [rsp+290h+var_230]; unsigned __int16 *
0x140012fc4  lea     rdx, aRequiredndpver; "RequiredNDPVersion"
0x140012fcb  lea     rcx, [rsp+290h+var_258]; this
0x140012fd0  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEBGPEAGPEAK@Z; ATL::CRegKey::QueryStringValue(ushort const *,ushort *,ulong *)
0x140012fd5  movzx   edi, ax
0x140012fd8  or      edi, 80070000h
0x140012fde  test    eax, eax
0x140012fe0  cmovle  edi, eax
0x140012fe3  test    edi, edi
0x140012fe5  js      short loc_140013007
0x140012fe7  lea     rax, [rsp+290h+var_230]
0x140012fec  or      r8, 0FFFFFFFFFFFFFFFFh
0x140012ff0  inc     r8
0x140012ff3  cmp     [rax+r8*2], r14w
0x140012ff8  jnz     short loc_140012FF0
0x140012ffa  lea     rdx, [rsp+290h+var_230]
0x140012fff  mov     rcx, rsi
0x140013002  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x140013007  mov     rbx, qword ptr [rsp+290h+var_258]
0x14001300c  test    rbx, rbx
0x14001300f  jz      short loc_14001301A
0x140013011  mov     rcx, rbx; hKey
0x140013014  call    cs:__imp_RegCloseKey
0x14001301a  mov     eax, edi
0x14001301c  mov     rcx, [rbp+190h+var_20]
0x140013023  xor     rcx, rsp; StackCookie
0x140013026  call    __security_check_cookie
0x14001302b  lea     r11, [rsp+290h+var_10]
0x140013033  mov     rbx, [r11+20h]
0x140013037  mov     rsi, [r11+30h]
0x14001303b  mov     rsp, r11
0x14001303e  pop     r14
0x140013040  pop     rdi
0x140013041  pop     rbp
0x140013042  retn
```
