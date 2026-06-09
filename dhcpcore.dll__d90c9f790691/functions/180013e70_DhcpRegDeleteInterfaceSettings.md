# DhcpRegDeleteInterfaceSettings

- ea: `0x180013e70`
- end: `0x1800140dc`
- name: `DhcpRegDeleteInterfaceSettings`
- size: `620`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180013b60`

## callees

- `0x1800057f0`
- `0x180006440`
- `0x180013e70`
- `0x18003611c`
- `0x18004b4bc`
- `0x18004d1a0`
- `0x18004d1e0`
- `0x18004d310`
- `0x18004e160`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001402a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18001402a`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180013fba`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180013fba`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180013ee8`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180013ee8`

## pseudocode

```c
__int64 __fastcall DhcpRegDeleteInterfaceSettings(HKEY hKey)
{
  DWORD v1; // ebx
  unsigned int v3; // eax
  unsigned int v4; // edi
  WCHAR *v5; // r13
  unsigned __int64 v6; // r15
  WCHAR *v7; // r15
  LSTATUS v8; // eax
  WCHAR *i; // rbx
  LSTATUS v10; // eax
  WCHAR *v12; // [rsp+68h] [rbp-8h] BYREF
  DWORD cbMaxValueNameLen; // [rsp+B8h] [rbp+48h] BYREF
  DWORD cValues; // [rsp+C0h] [rbp+50h] BYREF
  DWORD cchValueName; // [rsp+C8h] [rbp+58h] BYREF

  v1 = 0;
  cValues = 0;
  cbMaxValueNameLen = 0;
  cchValueName = 0;
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_(1028, 61, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids);
  v3 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, &cbMaxValueNameLen, 0, 0, 0);
  v4 = v3;
  if ( v3 )
  {
    if ( (xmmword_1800616A0 & 2) != 0 )
      WPP_SF_D(1025, 62, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, v3);
  }
  else if ( cValues )
  {
    ++cbMaxValueNameLen;
    v12 = (WCHAR *)DhcpAlloc(2 * cValues * cbMaxValueNameLen);
    if ( v12 )
    {
      v4 = 0;
      v5 = &v12[cValues * cbMaxValueNameLen];
      v6 = (unsigned __int64)(v5 - 1);
      if ( cValues )
      {
        v7 = v12;
        do
        {
          cchValueName = cbMaxValueNameLen;
          v8 = RegEnumValueW(hKey, v1, v7, &cchValueName, 0, 0, 0, 0);
          if ( v8 && (xmmword_1800616A0 & 2) != 0 )
            WPP_SF_ddD(1025, 64, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, v1, cValues, v8);
          ++v1;
          v7 += cbMaxValueNameLen;
        }
        while ( v1 < cValues );
        v6 = (unsigned __int64)(v5 - 1);
      }
      for ( i = v12; (unsigned __int64)i <= v6; i += cbMaxValueNameLen )
      {
        if ( *i )
        {
          if ( !(unsigned int)DhcpIgnoreInterfaceRegSetting((char *)i) )
          {
            v10 = RegDeleteValueW(hKey, i);
            if ( v10 )
            {
              if ( (xmmword_1800616A0 & 2) != 0 )
                WPP_SF_SD(1025, 65, (unsigned int)WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, (_DWORD)i, v10);
            }
          }
        }
      }
      if ( i != v5 )
      {
        if ( (xmmword_1800616A0 & 2) != 0 )
          WPP_SF_qq(1025, 66, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, v5, i);
        v4 = 487;
      }
    }
    else
    {
      v4 = 8;
    }
    if ( v12 )
      DhcpPunycodeFree((LPVOID *)&v12);
  }
  else
  {
    if ( (xmmword_1800616A0 & 0x10) == 0 )
      return v4;
    WPP_SF_(1028, 63, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids);
  }
  if ( (xmmword_1800616A0 & 0x10) != 0 )
    WPP_SF_D(1028, 67, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x180013e70  push    rbp
0x180013e72  push    rbx
0x180013e73  push    rsi
0x180013e74  push    rdi
0x180013e75  push    r12
0x180013e77  push    r13
0x180013e79  push    r15
0x180013e7b  mov     rbp, rsp
0x180013e7e  sub     rsp, 70h
0x180013e82  xor     ebx, ebx
0x180013e84  mov     r12, rcx
0x180013e87  mov     [rbp+cValues], ebx
0x180013e8a  mov     [rbp+cbMaxValueNameLen], ebx
0x180013e8d  mov     [rbp+cchValueName], ebx
0x180013e90  test    byte ptr cs:xmmword_1800616A0, 10h
0x180013e97  jz      short loc_180013EAD
0x180013e99  lea     edx, [rbx+3Dh]
0x180013e9c  mov     ecx, 404h
0x180013ea1  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x180013ea8  call    WPP_SF_
0x180013ead  mov     [rsp+70h+lpftLastWriteTime], rbx; lpftLastWriteTime
0x180013eb2  lea     rax, [rbp+cbMaxValueNameLen]
0x180013eb6  mov     [rsp+70h+lpcbSecurityDescriptor], rbx; lpcbSecurityDescriptor
0x180013ebb  xor     r9d, r9d; lpReserved
0x180013ebe  mov     [rsp+70h+lpcbMaxValueLen], rbx; lpcbMaxValueLen
0x180013ec3  xor     r8d, r8d; lpcchClass
0x180013ec6  mov     [rsp+70h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180013ecb  xor     edx, edx; lpClass
0x180013ecd  lea     rax, [rbp+cValues]
0x180013ed1  mov     rcx, r12; hKey
0x180013ed4  mov     [rsp+70h+lpcValues], rax; lpcValues
0x180013ed9  mov     [rsp+70h+lpcbMaxClassLen], rbx; lpcbMaxClassLen
0x180013ede  mov     [rsp+70h+lpcbMaxSubKeyLen], rbx; lpcbMaxSubKeyLen
0x180013ee3  mov     [rsp+70h+lpcSubKeys], rbx; lpcSubKeys
0x180013ee8  call    cs:__imp_RegQueryInfoKeyW
0x180013eee  mov     edi, eax
0x180013ef0  test    eax, eax
0x180013ef2  jz      short loc_180013F1F
0x180013ef4  test    byte ptr cs:xmmword_1800616A0, 2
0x180013efb  jz      loc_1800140A9
0x180013f01  mov     edx, 3Eh ; '>'
0x180013f06  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x180013f0d  mov     ecx, 401h
0x180013f12  mov     r9d, eax
0x180013f15  call    WPP_SF_D
0x180013f1a  jmp     loc_1800140A9
0x180013f1f  mov     ecx, [rbp+cValues]
0x180013f22  test    ecx, ecx
0x180013f24  jnz     short loc_180013F4C
0x180013f26  test    byte ptr cs:xmmword_1800616A0, 10h
0x180013f2d  jz      loc_1800140CB
0x180013f33  lea     edx, [rcx+3Fh]
0x180013f36  mov     ecx, 404h
0x180013f3b  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x180013f42  call    WPP_SF_
0x180013f47  jmp     loc_1800140A9
0x180013f4c  mov     eax, [rbp+cbMaxValueNameLen]
0x180013f4f  inc     eax
0x180013f51  mov     [rbp+cbMaxValueNameLen], eax
0x180013f54  imul    eax, ecx
0x180013f57  lea     ecx, [rax+rax]
0x180013f5a  call    DhcpAlloc
0x180013f5f  mov     [rbp+var_8], rax
0x180013f63  mov     rsi, rax
0x180013f66  test    rax, rax
0x180013f69  jnz     short loc_180013F73
0x180013f6b  lea     edi, [rax+8]
0x180013f6e  jmp     loc_18001409B
0x180013f73  mov     eax, [rbp+cbMaxValueNameLen]
0x180013f76  mov     edi, ebx
0x180013f78  mov     ecx, [rbp+cValues]
0x180013f7b  imul    eax, ecx
0x180013f7e  lea     r13, [rsi+rax*2]
0x180013f82  mov     [rbp+var_10], r13
0x180013f86  lea     r15, [r13-2]
0x180013f8a  test    ecx, ecx
0x180013f8c  jz      short loc_180014007
0x180013f8e  mov     r15, rsi
0x180013f91  xor     r13d, r13d
0x180013f94  mov     eax, [rbp+cbMaxValueNameLen]
0x180013f97  lea     r9, [rbp+cchValueName]; lpcchValueName
0x180013f9b  mov     [rsp+70h+lpcValues], r13; lpcbData
0x180013fa0  mov     r8, r15; lpValueName
0x180013fa3  mov     [rsp+70h+lpcbMaxClassLen], r13; lpData
0x180013fa8  mov     edx, ebx; dwIndex
0x180013faa  mov     [rsp+70h+lpcbMaxSubKeyLen], r13; lpType
0x180013faf  mov     rcx, r12; hKey
0x180013fb2  mov     [rsp+70h+lpcSubKeys], r13; lpReserved
0x180013fb7  mov     [rbp+cchValueName], eax
0x180013fba  call    cs:__imp_RegEnumValueW
0x180013fc0  test    eax, eax
0x180013fc2  jz      short loc_180013FF1
0x180013fc4  test    byte ptr cs:xmmword_1800616A0, 2
0x180013fcb  jz      short loc_180013FF1
0x180013fcd  mov     dword ptr [rsp+70h+lpcbMaxSubKeyLen], eax
0x180013fd1  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x180013fd8  mov     eax, [rbp+cValues]
0x180013fdb  mov     edx, 40h ; '@'
0x180013fe0  mov     ecx, 401h
0x180013fe5  mov     dword ptr [rsp+70h+lpcSubKeys], eax
0x180013fe9  mov     r9d, ebx
0x180013fec  call    WPP_SF_ddD
0x180013ff1  mov     eax, [rbp+cbMaxValueNameLen]
0x180013ff4  inc     ebx
0x180013ff6  lea     r15, [r15+rax*2]
0x180013ffa  cmp     ebx, [rbp+cValues]
0x180013ffd  jb      short loc_180013F94
0x180013fff  mov     r13, [rbp+var_10]
0x180014003  lea     r15, [r13-2]
0x180014007  mov     rbx, rsi
0x18001400a  cmp     rsi, r15
0x18001400d  ja      short loc_18001406A
0x18001400f  xor     r13d, r13d
0x180014012  cmp     [rbx], r13w
0x180014016  jz      short loc_18001405A
0x180014018  mov     rcx, rbx
0x18001401b  call    DhcpIgnoreInterfaceRegSetting
0x180014020  test    eax, eax
0x180014022  jnz     short loc_18001405A
0x180014024  mov     rdx, rbx; lpValueName
0x180014027  mov     rcx, r12; hKey
0x18001402a  call    cs:__imp_RegDeleteValueW
0x180014030  test    eax, eax
0x180014032  jz      short loc_18001405A
0x180014034  test    byte ptr cs:xmmword_1800616A0, 2
0x18001403b  jz      short loc_18001405A
0x18001403d  mov     edx, 41h ; 'A'
0x180014042  mov     dword ptr [rsp+70h+lpcSubKeys], eax
0x180014046  mov     ecx, 401h
0x18001404b  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x180014052  mov     r9, rbx
0x180014055  call    WPP_SF_SD
0x18001405a  mov     eax, [rbp+cbMaxValueNameLen]
0x18001405d  lea     rbx, [rbx+rax*2]
0x180014061  cmp     rbx, r15
0x180014064  jbe     short loc_180014012
0x180014066  mov     r13, [rbp+var_10]
0x18001406a  cmp     rbx, r13
0x18001406d  jz      short loc_18001409B
0x18001406f  test    byte ptr cs:xmmword_1800616A0, 2
0x180014076  jz      short loc_180014096
0x180014078  mov     edx, 42h ; 'B'
0x18001407d  mov     [rsp+70h+lpcSubKeys], rbx
0x180014082  mov     ecx, 401h
0x180014087  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x18001408e  mov     r9, r13
0x180014091  call    WPP_SF_qq
0x180014096  mov     edi, 1E7h
0x18001409b  test    rsi, rsi
0x18001409e  jz      short loc_1800140A9
0x1800140a0  lea     rcx, [rbp+var_8]
0x1800140a4  call    DhcpPunycodeFree
0x1800140a9  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800140b0  jz      short loc_1800140CB
0x1800140b2  mov     edx, 43h ; 'C'
0x1800140b7  lea     r8, WPP_a1eae5ef76d23d59fbadaa0980bd692f_Traceguids
0x1800140be  mov     ecx, 404h
0x1800140c3  mov     r9d, edi
0x1800140c6  call    WPP_SF_D
0x1800140cb  mov     eax, edi
0x1800140cd  add     rsp, 70h
0x1800140d1  pop     r15
0x1800140d3  pop     r13
0x1800140d5  pop     r12
0x1800140d7  pop     rdi
0x1800140d8  pop     rsi
0x1800140d9  pop     rbx
0x1800140da  pop     rbp
0x1800140db  retn
```
