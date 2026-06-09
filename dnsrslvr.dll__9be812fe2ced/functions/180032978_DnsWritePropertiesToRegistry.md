# DnsWritePropertiesToRegistry

- ea: `0x180032978`
- end: `0x180032c89`
- name: `DnsWritePropertiesToRegistry`
- size: `785`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, HKEY@<rdx>, void *Src@<r8>, __int64, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180032dd4`

## callees

- `0x18000b130`
- `0x1800226e0`
- `0x180032978`
- `0x180032c90`
- `0x18004e508`
- `0x18004e674`
- `0x18007e550`
- `0x180086b1c`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x180032b29`
- `api-ms-win-crt-string-l1-1-0!wcscspn` at `0x180032b29`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032c04`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032c12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032c04`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180032c12`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180032c2e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180032c41`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180032c2e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180032c41`

## pseudocode

```c
__int64 __fastcall DnsWritePropertiesToRegistry(HKEY hKey, HKEY a2, void *Src, unsigned int a4, __int64 a5, int a6)
{
  const WCHAR *v9; // rdi
  unsigned int PropertyKey; // eax
  unsigned int v11; // ebx
  const WCHAR *v12; // r15
  unsigned int v13; // eax
  unsigned int v14; // r14d
  __int16 *StringCopy_W; // rax
  __int16 v16; // cx
  const wchar_t *v17; // r12
  _WORD *v18; // rdx
  unsigned int v19; // eax
  __int16 v21; // [rsp+50h] [rbp-68h]
  int v22; // [rsp+58h] [rbp-60h]
  HKEY hKeya; // [rsp+60h] [rbp-58h]
  const WCHAR *lpSubKey; // [rsp+68h] [rbp-50h]
  const WCHAR *v25; // [rsp+70h] [rbp-48h]
  __int16 *v26; // [rsp+78h] [rbp-40h]

  lpSubKey = L"Doh";
  v26 = 0;
  v25 = L"Dot";
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_qqSdql(0, (_DWORD)a2, (_DWORD)Src, (_DWORD)hKey, (__int64)a2, (__int64)Src, a4, a5, a6);
  if ( hKey )
  {
    v9 = L"Doh6";
    if ( !a6 )
      v9 = L"Doh";
    lpSubKey = v9;
    PropertyKey = DnsCreatePropertyKey(hKey, v9);
    v11 = PropertyKey;
    if ( PropertyKey )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_d(1035, 170, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, PropertyKey);
      goto LABEL_34;
    }
    lpSubKey = v9;
  }
  if ( a2 )
  {
    v12 = L"Dot6";
    if ( !a6 )
      v12 = L"Dot";
    v25 = v12;
    v13 = DnsCreatePropertyKey(a2, v12);
    v14 = 0;
    v11 = v13;
    if ( v13 )
    {
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_d(1035, 171, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v13);
      goto LABEL_34;
    }
    v25 = v12;
  }
  else
  {
    v14 = 0;
  }
  StringCopy_W = (__int16 *)Dns_CreateStringCopy_W(Src);
  v26 = StringCopy_W;
  if ( StringCopy_W )
  {
    v16 = *StringCopy_W;
    v11 = 0;
    v22 = 0;
    v17 = (const wchar_t *)StringCopy_W;
LABEL_23:
    if ( v16 )
    {
      v18 = &v17[wcscspn(v17, L" ,;")];
      v21 = *v18;
      hKeya = (HKEY)v18;
      *v18 = 0;
      while ( 1 )
      {
        if ( v14 >= a4 )
        {
          v16 = v21;
          ++v22;
          *(_WORD *)hKeya = v21;
          v17 = (const wchar_t *)hKeya + 1;
          v14 = 0;
          goto LABEL_23;
        }
        if ( *(_DWORD *)(a5 + 24LL * v14 + 4) == v22 && *(_DWORD *)(a5 + 24LL * v14 + 8) == 2 )
        {
          if ( a2 )
          {
            v19 = DnsWriteDotProperty(0, v17, *(_QWORD *)(a5 + 24LL * v14 + 16));
            v11 = v19;
            if ( v19 )
              break;
          }
        }
        ++v14;
      }
      if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
        WPP_SF_d(1035, 173, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v19);
    }
  }
  else
  {
    v11 = 14;
  }
LABEL_34:
  if ( v11 )
  {
    if ( hKey )
      RegDeleteTreeW(hKey, lpSubKey);
    if ( a2 )
      RegDeleteTreeW(a2, v25);
  }
  MIDL_user_free(v26);
  if ( (BYTE1(xmmword_1800AB5A0) & 8) != 0 )
    WPP_SF_d(1035, 174, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x180032978  mov     r11, rsp
0x18003297b  mov     [r11+10h], rbx
0x18003297f  mov     [r11+20h], r9d
0x180032983  mov     [r11+8], rcx
0x180032987  push    rbp
0x180032988  push    rsi
0x180032989  push    rdi
0x18003298a  push    r12
0x18003298c  push    r13
0x18003298e  push    r14
0x180032990  push    r15
0x180032992  sub     rsp, 80h
0x180032999  mov     rsi, rcx
0x18003299c  lea     rax, aDoh; "Doh"
0x1800329a3  xor     ecx, ecx
0x1800329a5  mov     [rsp+0B8h+lpSubKey], rax
0x1800329aa  lea     rbx, aDot; "Dot"
0x1800329b1  mov     [rsp+0B8h+var_40], rcx
0x1800329b6  mov     ebp, ecx
0x1800329b8  mov     [r11-60h], rcx
0x1800329bc  mov     r15d, ecx
0x1800329bf  mov     [r11-58h], rcx
0x1800329c3  mov     r12, r8
0x1800329c6  mov     [rsp+0B8h+var_48], rbx
0x1800329cb  mov     r13, rdx
0x1800329ce  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x1800329d5  mov     r14d, [rsp+0B8h+arg_28]
0x1800329dd  jz      short loc_180032A0D
0x1800329df  mov     rax, [rsp+0B8h+arg_20]
0x1800329e7  mov     [r11-78h], r14d
0x1800329eb  mov     [r11-80h], rax
0x1800329ef  mov     [rsp+0B8h+var_88], r9d
0x1800329f4  mov     r9, rsi
0x1800329f7  mov     [rsp+0B8h+var_90], r8
0x1800329fc  mov     [rsp+0B8h+var_98], rdx
0x180032a01  call    WPP_SF_qqSdql
0x180032a06  lea     rax, aDoh; "Doh"
0x180032a0d  test    rsi, rsi
0x180032a10  jz      short loc_180032A7D
0x180032a12  test    r14d, r14d
0x180032a15  lea     rdi, aDoh6; "Doh6"
0x180032a1c  lea     r8, [rsp+0B8h+var_60]
0x180032a21  mov     rcx, rsi; hKey
0x180032a24  cmovz   rdi, rax
0x180032a28  mov     rdx, rdi; lpSubKey
0x180032a2b  mov     [rsp+0B8h+lpSubKey], rdi
0x180032a30  call    DnsCreatePropertyKey
0x180032a35  mov     ebx, eax
0x180032a37  test    eax, eax
0x180032a39  jz      short loc_180032A6C
0x180032a3b  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180032a42  lea     rsi, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x180032a49  mov     edi, 40Bh
0x180032a4e  jz      short loc_180032A62
0x180032a50  mov     edx, 0AAh
0x180032a55  mov     ecx, edi
0x180032a57  mov     r9d, eax
0x180032a5a  mov     r8, rsi
0x180032a5d  call    WPP_SF_d
0x180032a62  mov     rbp, [rsp+0B8h+var_60]
0x180032a67  jmp     loc_180032C0A
0x180032a6c  mov     rbp, [rsp+0B8h+var_60]
0x180032a71  lea     rbx, aDot; "Dot"
0x180032a78  mov     [rsp+0B8h+lpSubKey], rdi
0x180032a7d  lea     rsi, WPP_c0db0faf0710345e3f24c62deaaeab26_Traceguids
0x180032a84  mov     edi, 40Bh
0x180032a89  test    r13, r13
0x180032a8c  jz      short loc_180032AEB
0x180032a8e  test    r14d, r14d
0x180032a91  lea     r15, aDot6; "Dot6"
0x180032a98  lea     r8, [rsp+0B8h+hKey]
0x180032a9d  mov     rcx, r13; hKey
0x180032aa0  cmovz   r15, rbx
0x180032aa4  mov     rdx, r15; lpSubKey
0x180032aa7  mov     [rsp+0B8h+var_48], r15
0x180032aac  call    DnsCreatePropertyKey
0x180032ab1  xor     r14d, r14d
0x180032ab4  mov     ebx, eax
0x180032ab6  test    eax, eax
0x180032ab8  jz      short loc_180032ADF
0x180032aba  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180032ac1  jz      short loc_180032AD5
0x180032ac3  mov     edx, 0ABh
0x180032ac8  mov     ecx, edi
0x180032aca  mov     r9d, eax
0x180032acd  mov     r8, rsi
0x180032ad0  call    WPP_SF_d
0x180032ad5  mov     r15, [rsp+0B8h+hKey]
0x180032ada  jmp     loc_180032BFC
0x180032adf  mov     [rsp+0B8h+var_48], r15
0x180032ae4  mov     r15, [rsp+0B8h+hKey]
0x180032ae9  jmp     short loc_180032AEE
0x180032aeb  xor     r14d, r14d
0x180032aee  mov     rcx, r12; Src
0x180032af1  call    Dns_CreateStringCopy_W
0x180032af6  mov     [rsp+0B8h+var_40], rax
0x180032afb  test    rax, rax
0x180032afe  jnz     short loc_180032B08
0x180032b00  lea     ebx, [rax+0Eh]
0x180032b03  jmp     loc_180032BFC
0x180032b08  movzx   ecx, word ptr [rax]
0x180032b0b  mov     ebx, r14d
0x180032b0e  mov     dword ptr [rsp+0B8h+var_60], r14d
0x180032b13  mov     r12, rax
0x180032b16  test    cx, cx
0x180032b19  jz      loc_180032BFC
0x180032b1f  lea     rdx, Control; " ,;"
0x180032b26  mov     rcx, r12; String
0x180032b29  call    cs:__imp_wcscspn
0x180032b2f  lea     rdx, [r12+rax*2]
0x180032b33  movzx   eax, word ptr [rdx]
0x180032b36  mov     [rsp+0B8h+var_68], ax
0x180032b3b  mov     [rsp+0B8h+hKey], rdx
0x180032b40  mov     [rdx], r14w
0x180032b44  cmp     r14d, [rsp+0B8h+arg_18]
0x180032b4c  jnb     short loc_180032BC2
0x180032b4e  mov     rdx, [rsp+0B8h+arg_20]
0x180032b56  mov     eax, r14d
0x180032b59  lea     r8, [rax+rax*2]
0x180032b5d  mov     eax, dword ptr [rsp+0B8h+var_60]
0x180032b61  cmp     [rdx+r8*8+4], eax
0x180032b66  jnz     short loc_180032BBD
0x180032b68  mov     ecx, [rdx+r8*8+8]
0x180032b6d  sub     ecx, 1
0x180032b70  jz      short loc_180032BA2
0x180032b72  cmp     ecx, 1
0x180032b75  jnz     short loc_180032BBD
0x180032b77  test    r13, r13
0x180032b7a  jz      short loc_180032BBD
0x180032b7c  mov     r8, [rdx+r8*8+10h]
0x180032b81  mov     rcx, r15; hKey
0x180032b84  mov     rdx, r12; lpSubKey
0x180032b87  call    DnsWriteDotProperty
0x180032b8c  mov     ebx, eax
0x180032b8e  test    eax, eax
0x180032b90  jz      short loc_180032BBD
0x180032b92  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180032b99  jz      short loc_180032BFC
0x180032b9b  mov     edx, 0ADh
0x180032ba0  jmp     short loc_180032BEF
0x180032ba2  test    rbp, rbp
0x180032ba5  jz      short loc_180032BBD
0x180032ba7  mov     r8, [rdx+r8*8+10h]
0x180032bac  mov     rcx, rbp; hKey
0x180032baf  mov     rdx, r12; lpSubKey
0x180032bb2  call    DnsWriteDohProperty
0x180032bb7  mov     ebx, eax
0x180032bb9  test    eax, eax
0x180032bbb  jnz     short loc_180032BE1
0x180032bbd  inc     r14d
0x180032bc0  jmp     short loc_180032B44
0x180032bc2  mov     r12, [rsp+0B8h+hKey]
0x180032bc7  movzx   ecx, [rsp+0B8h+var_68]
0x180032bcc  inc     dword ptr [rsp+0B8h+var_60]
0x180032bd0  mov     [r12], cx
0x180032bd5  add     r12, 2
0x180032bd9  xor     r14d, r14d
0x180032bdc  jmp     loc_180032B16
0x180032be1  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180032be8  jz      short loc_180032BFC
0x180032bea  mov     edx, 0ACh
0x180032bef  mov     r9d, eax
0x180032bf2  mov     r8, rsi
0x180032bf5  mov     ecx, edi
0x180032bf7  call    WPP_SF_d
0x180032bfc  test    r15, r15
0x180032bff  jz      short loc_180032C0A
0x180032c01  mov     rcx, r15; hKey
0x180032c04  call    cs:__imp_RegCloseKey
0x180032c0a  test    rbp, rbp
0x180032c0d  jz      short loc_180032C18
0x180032c0f  mov     rcx, rbp; hKey
0x180032c12  call    cs:__imp_RegCloseKey
0x180032c18  test    ebx, ebx
0x180032c1a  jz      short loc_180032C47
0x180032c1c  mov     rcx, [rsp+0B8h+arg_0]; hKey
0x180032c24  test    rcx, rcx
0x180032c27  jz      short loc_180032C34
0x180032c29  mov     rdx, [rsp+0B8h+lpSubKey]; lpSubKey
0x180032c2e  call    cs:__imp_RegDeleteTreeW
0x180032c34  test    r13, r13
0x180032c37  jz      short loc_180032C47
0x180032c39  mov     rdx, [rsp+0B8h+var_48]; lpSubKey
0x180032c3e  mov     rcx, r13; hKey
0x180032c41  call    cs:__imp_RegDeleteTreeW
0x180032c47  mov     rcx, [rsp+0B8h+var_40]; void *
0x180032c4c  call    MIDL_user_free
0x180032c51  test    byte ptr cs:xmmword_1800AB5A0+1, 8
0x180032c58  jz      short loc_180032C6C
0x180032c5a  mov     edx, 0AEh
0x180032c5f  mov     ecx, edi
0x180032c61  mov     r9d, ebx
0x180032c64  mov     r8, rsi
0x180032c67  call    WPP_SF_d
0x180032c6c  mov     eax, ebx
0x180032c6e  mov     rbx, [rsp+0B8h+arg_8]
0x180032c76  add     rsp, 80h
0x180032c7d  pop     r15
0x180032c7f  pop     r14
0x180032c81  pop     r13
0x180032c83  pop     r12
0x180032c85  pop     rdi
0x180032c86  pop     rsi
0x180032c87  pop     rbp
0x180032c88  retn
```
