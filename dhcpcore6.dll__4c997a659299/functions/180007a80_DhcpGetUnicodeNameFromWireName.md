# DhcpGetUnicodeNameFromWireName

- ea: `0x180007a80`
- end: `0x180007cbf`
- name: `DhcpGetUnicodeNameFromWireName`
- size: `575`
- prototype: `__int64 __fastcall(_BYTE *, unsigned int, _WORD *, __int64, unsigned int *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x1800058ec`
- `0x180028000`

## callees

- `0x180007a80`
- `0x18001907c`
- `0x180019ad0`
- `0x18001a3ee`
- `0x18002c490`
- `0x18003098c`
- `0x1800338c0`
- `0x180033de4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180007bb6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180007bb6`
- `DNSAPI!DnsNameCopy` at `0x180007b78`
- `DNSAPI!DnsNameCopy` at `0x180007b78`

## pseudocode

```c
__int64 __fastcall DhcpGetUnicodeNameFromWireName(_BYTE *a1, unsigned int a2, _WORD *a3, __int64 a4, unsigned int *a5)
{
  unsigned int *v5; // r13
  unsigned int v9; // ebp
  unsigned int v10; // edi
  WCHAR *lpWideCharStr; // r14
  __int64 v12; // r15
  unsigned int v13; // ebx
  int IsEnabledDeviceUsageNoInline; // eax
  const CHAR *v15; // r8
  unsigned int v16; // eax
  __int64 v17; // rcx
  unsigned int LastErrorOrUnknown; // ebx
  unsigned int v19; // eax
  unsigned __int64 v20; // rax
  unsigned int v21; // r8d
  unsigned int v22; // ecx
  WCHAR *v23; // rdx
  unsigned int v25[4]; // [rsp+30h] [rbp-268h] BYREF
  unsigned int *v26; // [rsp+40h] [rbp-258h]
  WCHAR WideCharStr[256]; // [rsp+50h] [rbp-248h] BYREF

  v5 = a5;
  v26 = a5;
  v25[0] = 0;
  v9 = 512;
  memset_0(WideCharStr, 0, sizeof(WideCharStr));
  *a5 = 0;
  *a3 = 0;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_d(1028, 54, WPP_0db776d5b2973b109b50142f7c503650_Traceguids, a2);
  if ( a2 - 1 > 0xFE )
  {
LABEL_29:
    LastErrorOrUnknown = 87;
    goto LABEL_30;
  }
  v10 = 0;
  lpWideCharStr = WideCharStr;
  if ( a2 > 1 )
  {
    while ( 1 )
    {
      v12 = (unsigned __int8)*a1;
      if ( !(_BYTE)v12 )
        break;
      if ( (unsigned __int8)v12 > 0x3Fu || (v13 = a2 - 1, (unsigned int)v12 > v13) )
      {
        LastErrorOrUnknown = 1212;
        goto LABEL_30;
      }
      IsEnabledDeviceUsageNoInline = Feature_5977_1413__private_IsEnabledDeviceUsageNoInline();
      v15 = a1 + 1;
      if ( IsEnabledDeviceUsageNoInline )
      {
        v19 = MultiByteToWideChar(0xFDE9u, 8u, v15, v12, lpWideCharStr, v9 >> 1);
        v17 = v19;
        if ( !v19 )
        {
LABEL_25:
          LastErrorOrUnknown = GetLastErrorOrUnknown(v17);
          goto LABEL_30;
        }
      }
      else
      {
        v25[0] = v9;
        v16 = DnsNameCopy(lpWideCharStr, v25, v15, (unsigned int)v12, 2, 1);
        v17 = v16;
        if ( !v16 )
          goto LABEL_25;
        if ( v25[0] <= 1 )
        {
          LastErrorOrUnknown = 13;
          goto LABEL_30;
        }
      }
      v20 = (unsigned __int64)(unsigned int)v17 >> 1;
      v21 = v10 + v17;
      v10 = v10 + v17 - 2;
      v22 = v9 - v17;
      a1 += v12 + 1;
      v23 = &lpWideCharStr[v20];
      lpWideCharStr = v23 - 1;
      v9 = v22 + 2;
      a2 = v13 - v12;
      if ( a2 && *a1 )
      {
        if ( v22 + 2 < 2 )
          goto LABEL_29;
        *lpWideCharStr = 46;
        v10 = v21;
        lpWideCharStr = v23;
        v9 = v22;
      }
      if ( v9 < 2 )
        goto LABEL_29;
      if ( a2 <= 1 )
      {
        v5 = v26;
        goto LABEL_20;
      }
    }
    v5 = v26;
    goto LABEL_21;
  }
LABEL_20:
  if ( a2 )
  {
LABEL_21:
    if ( !*a1 )
    {
      *lpWideCharStr = 0;
      v10 += 2;
    }
  }
  if ( v10 <= 0xFF )
  {
    LastErrorOrUnknown = 0;
    memcpy_0(a3, WideCharStr, v10);
    *v5 = v10;
  }
  else
  {
    LastErrorOrUnknown = 122;
  }
LABEL_30:
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_D(1028, 55, WPP_0db776d5b2973b109b50142f7c503650_Traceguids, LastErrorOrUnknown);
  return LastErrorOrUnknown;
}

```

## disassembly

```asm
0x180007a80  mov     [rsp+arg_18], rbx
0x180007a85  push    rbp
0x180007a86  push    rsi
0x180007a87  push    rdi
0x180007a88  push    r12
0x180007a8a  push    r13
0x180007a8c  push    r14
0x180007a8e  push    r15
0x180007a90  sub     rsp, 260h
0x180007a97  mov     rax, cs:__security_cookie
0x180007a9e  xor     rax, rsp
0x180007aa1  mov     [rsp+298h+var_48], rax
0x180007aa9  mov     r13, [rsp+298h+arg_20]
0x180007ab1  mov     r12, r8
0x180007ab4  mov     ebx, edx
0x180007ab6  mov     [rsp+298h+var_258], r13
0x180007abb  mov     rsi, rcx
0x180007abe  mov     [rsp+298h+var_268], 0
0x180007ac6  mov     ebp, 200h
0x180007acb  lea     rcx, [rsp+298h+WideCharStr]; void *
0x180007ad0  mov     r8d, ebp; Size
0x180007ad3  xor     edx, edx; Val
0x180007ad5  call    memset_0
0x180007ada  xor     eax, eax
0x180007adc  mov     dword ptr [r13+0], 0
0x180007ae4  mov     [r12], ax
0x180007ae9  test    byte ptr cs:xmmword_1800423E0, 10h
0x180007af0  jz      short loc_180007B09
0x180007af2  lea     edx, [rax+36h]
0x180007af5  mov     ecx, 404h
0x180007afa  mov     r9d, ebx
0x180007afd  lea     r8, WPP_0db776d5b2973b109b50142f7c503650_Traceguids
0x180007b04  call    WPP_SF_d
0x180007b09  lea     eax, [rbx-1]
0x180007b0c  cmp     eax, 0FEh
0x180007b11  ja      loc_180007C6A
0x180007b17  xor     edi, edi
0x180007b19  lea     r14, [rsp+298h+WideCharStr]
0x180007b1e  cmp     ebx, 1
0x180007b21  jbe     loc_180007C1A
0x180007b27  movzx   r15d, byte ptr [rsi]
0x180007b2b  test    r15b, r15b
0x180007b2e  jz      loc_180007C4B
0x180007b34  cmp     r15b, 3Fh ; '?'
0x180007b38  ja      loc_180007C44
0x180007b3e  dec     ebx
0x180007b40  cmp     r15d, ebx
0x180007b43  ja      loc_180007C44
0x180007b49  lea     r13, [rsi+1]
0x180007b4d  call    Feature_5977_1413__private_IsEnabledDeviceUsageNoInline
0x180007b52  mov     r9d, r15d; cbMultiByte
0x180007b55  mov     r8, r13; lpMultiByteStr
0x180007b58  test    eax, eax
0x180007b5a  jnz     short loc_180007B9F
0x180007b5c  mov     [rsp+298h+cchWideChar], 1
0x180007b64  lea     rdx, [rsp+298h+var_268]
0x180007b69  mov     rcx, r14
0x180007b6c  mov     dword ptr [rsp+298h+lpWideCharStr], 2
0x180007b74  mov     [rsp+298h+var_268], ebp
0x180007b78  call    cs:__imp_DnsNameCopy
0x180007b7f  nop     dword ptr [rax+rax+00h]
0x180007b84  mov     ecx, eax
0x180007b86  test    eax, eax
0x180007b88  jz      loc_180007C3B
0x180007b8e  cmp     [rsp+298h+var_268], 1
0x180007b93  ja      short loc_180007BC8
0x180007b95  mov     ebx, 0Dh
0x180007b9a  jmp     loc_180007C6F
0x180007b9f  mov     eax, ebp
0x180007ba1  mov     edx, 8; dwFlags
0x180007ba6  shr     eax, 1
0x180007ba8  mov     ecx, 0FDE9h; CodePage
0x180007bad  mov     [rsp+298h+cchWideChar], eax; cchWideChar
0x180007bb1  mov     [rsp+298h+lpWideCharStr], r14; lpWideCharStr
0x180007bb6  call    cs:__imp_MultiByteToWideChar
0x180007bbd  nop     dword ptr [rax+rax+00h]
0x180007bc2  mov     ecx, eax
0x180007bc4  test    eax, eax
0x180007bc6  jz      short loc_180007C3B
0x180007bc8  sub     ebp, ecx
0x180007bca  mov     eax, ecx
0x180007bcc  shr     rax, 1
0x180007bcf  lea     r8d, [rdi+rcx]
0x180007bd3  lea     edi, [r8-2]
0x180007bd7  mov     ecx, ebp
0x180007bd9  lea     rsi, [r15+r13]
0x180007bdd  lea     rdx, [r14+rax*2]
0x180007be1  lea     eax, [rbp+2]
0x180007be4  lea     r14, [rdx-2]
0x180007be8  mov     ebp, eax
0x180007bea  sub     ebx, r15d
0x180007bed  jz      short loc_180007C07
0x180007bef  cmp     byte ptr [rsi], 0
0x180007bf2  jz      short loc_180007C07
0x180007bf4  cmp     eax, 2
0x180007bf7  jb      short loc_180007C6A
0x180007bf9  mov     word ptr [r14], 2Eh ; '.'
0x180007bff  mov     edi, r8d
0x180007c02  mov     r14, rdx
0x180007c05  mov     ebp, ecx
0x180007c07  cmp     ebp, 2
0x180007c0a  jb      short loc_180007C6A
0x180007c0c  cmp     ebx, 1
0x180007c0f  ja      loc_180007B27
0x180007c15  mov     r13, [rsp+298h+var_258]
0x180007c1a  test    ebx, ebx
0x180007c1c  jz      short loc_180007C2C
0x180007c1e  cmp     byte ptr [rsi], 0
0x180007c21  jnz     short loc_180007C2C
0x180007c23  xor     eax, eax
0x180007c25  mov     [r14], ax
0x180007c29  add     edi, 2
0x180007c2c  cmp     edi, 0FFh
0x180007c32  jbe     short loc_180007C52
0x180007c34  mov     ebx, 7Ah ; 'z'
0x180007c39  jmp     short loc_180007C6F
0x180007c3b  call    GetLastErrorOrUnknown
0x180007c40  mov     ebx, eax
0x180007c42  jmp     short loc_180007C6F
0x180007c44  mov     ebx, 4BCh
0x180007c49  jmp     short loc_180007C6F
0x180007c4b  mov     r13, [rsp+298h+var_258]
0x180007c50  jmp     short loc_180007C1E
0x180007c52  xor     ebx, ebx
0x180007c54  mov     r8d, edi; Size
0x180007c57  lea     rdx, [rsp+298h+WideCharStr]; Src
0x180007c5c  mov     rcx, r12; void *
0x180007c5f  call    memcpy_0
0x180007c64  mov     [r13+0], edi
0x180007c68  jmp     short loc_180007C6F
0x180007c6a  mov     ebx, 57h ; 'W'
0x180007c6f  test    byte ptr cs:xmmword_1800423E0, 10h
0x180007c76  jz      short loc_180007C91
0x180007c78  mov     edx, 37h ; '7'
0x180007c7d  lea     r8, WPP_0db776d5b2973b109b50142f7c503650_Traceguids
0x180007c84  mov     ecx, 404h
0x180007c89  mov     r9d, ebx
0x180007c8c  call    WPP_SF_D
0x180007c91  mov     eax, ebx
0x180007c93  mov     rcx, [rsp+298h+var_48]
0x180007c9b  xor     rcx, rsp; StackCookie
0x180007c9e  call    __security_check_cookie
0x180007ca3  mov     rbx, [rsp+298h+arg_18]
0x180007cab  add     rsp, 260h
0x180007cb2  pop     r15
0x180007cb4  pop     r14
0x180007cb6  pop     r13
0x180007cb8  pop     r12
0x180007cba  pop     rdi
0x180007cbb  pop     rsi
0x180007cbc  pop     rbp
0x180007cbd  retn
```
