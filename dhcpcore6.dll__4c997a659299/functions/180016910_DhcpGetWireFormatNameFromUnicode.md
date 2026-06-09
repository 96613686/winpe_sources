# DhcpGetWireFormatNameFromUnicode

- ea: `0x180016910`
- end: `0x180016ad4`
- name: `DhcpGetWireFormatNameFromUnicode`
- size: `452`
- prototype: `__int64 __fastcall(CHAR *, unsigned __int64, const WCHAR *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180003100`

## callees

- `0x180016910`
- `0x18001907c`
- `0x180019ad0`
- `0x18001a3ee`
- `0x18002c490`
- `0x18003431c`
- `0x18003483c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180016a16`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180016a16`
- `DNSAPI!DnsNameCopy` at `0x1800169b0`
- `DNSAPI!DnsNameCopy` at `0x1800169b0`

## pseudocode

```c
__int64 __fastcall DhcpGetWireFormatNameFromUnicode(CHAR *a1, unsigned __int64 a2, const WCHAR *a3, unsigned int *a4)
{
  unsigned int v7; // edi
  int v9; // ecx
  __int64 v10; // rcx
  CHAR *v11; // r9
  CHAR *v12; // rdx
  CHAR *v13; // rbx
  char v14; // r8
  unsigned int LastErrorOrUnknown; // ebx
  int v17[4]; // [rsp+40h] [rbp-148h] BYREF
  CHAR MultiByteStr[256]; // [rsp+50h] [rbp-138h] BYREF

  v7 = 0;
  memset_0(MultiByteStr, 0, sizeof(MultiByteStr));
  v17[0] = 255;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_Sqq(v9, 52, (unsigned int)WPP_0db776d5b2973b109b50142f7c503650_Traceguids, (_DWORD)a3, (char)a1, a2);
  *a1 = 0;
  if ( a4 )
    *a4 = 0;
  if ( (unsigned int)Feature_5977_1413__private_IsEnabledDeviceUsageNoInline() )
  {
    if ( WideCharToMultiByte(0xFDE9u, 0, a3, -1, MultiByteStr, 256, 0, 0) > 0 )
      goto LABEL_7;
LABEL_12:
    LastErrorOrUnknown = GetLastErrorOrUnknown(v10);
    goto LABEL_26;
  }
  if ( !(unsigned int)DnsNameCopy(MultiByteStr, v17, a3, 0, 1, 2) )
    goto LABEL_12;
LABEL_7:
  v11 = a1;
  v12 = MultiByteStr;
  v13 = a1 + 1;
  LOBYTE(v10) = 0;
  v14 = 0;
  if ( MultiByteStr[0] )
  {
    do
    {
      if ( (unsigned __int64)v13 >= a2 )
      {
        LastErrorOrUnknown = 122;
        goto LABEL_26;
      }
      if ( *v12 == 46 )
      {
        if ( (unsigned __int8)(v10 - 1) > 0x3Eu )
          goto LABEL_22;
        *v11 = v10;
        LOBYTE(v10) = 0;
        ++v14;
        v11 = v13;
      }
      else
      {
        *v13 = *v12;
        LOBYTE(v10) = v10 + 1;
      }
      ++v12;
      ++v7;
      ++v13;
    }
    while ( *v12 );
    if ( (unsigned __int8)v10 > 0x3Fu
      || (_BYTE)v10 && (++v7, *v11 = v10, v7 > 0xFF)
      || v14 && (unsigned __int64)v13 <= a2 && (++v7, *v13 = 0, v7 > 0xFF) )
    {
LABEL_22:
      LastErrorOrUnknown = 1212;
      goto LABEL_26;
    }
  }
  LastErrorOrUnknown = 0;
  if ( a4 )
    *a4 = v7;
LABEL_26:
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_Dd(v10, 53, WPP_0db776d5b2973b109b50142f7c503650_Traceguids, LastErrorOrUnknown, v7);
  return LastErrorOrUnknown;
}

```

## disassembly

```asm
0x180016910  push    rbx
0x180016912  push    rbp
0x180016913  push    rsi
0x180016914  push    rdi
0x180016915  push    r14
0x180016917  sub     rsp, 160h
0x18001691e  mov     rax, cs:__security_cookie
0x180016925  xor     rax, rsp
0x180016928  mov     [rsp+188h+var_38], rax
0x180016930  mov     rbp, r8
0x180016933  mov     r14, rdx
0x180016936  mov     rbx, rcx
0x180016939  xor     edx, edx; Val
0x18001693b  mov     r8d, 100h; Size
0x180016941  lea     rcx, [rsp+188h+MultiByteStr]; void *
0x180016946  xor     edi, edi
0x180016948  mov     rsi, r9
0x18001694b  call    memset_0
0x180016950  mov     [rsp+188h+var_148], 0FFh
0x180016958  test    byte ptr cs:xmmword_1800423E0, 10h
0x18001695f  jz      short loc_18001697D
0x180016961  lea     edx, [rdi+34h]
0x180016964  mov     qword ptr [rsp+188h+cbMultiByte], r14
0x180016969  mov     r9, rbp
0x18001696c  mov     [rsp+188h+lpMultiByteStr], rbx
0x180016971  lea     r8, WPP_0db776d5b2973b109b50142f7c503650_Traceguids
0x180016978  call    WPP_SF_Sqq
0x18001697d  mov     [rbx], dil
0x180016980  test    rsi, rsi
0x180016983  jz      short loc_180016987
0x180016985  mov     [rsi], edi
0x180016987  call    Feature_5977_1413__private_IsEnabledDeviceUsageNoInline
0x18001698c  mov     r8, rbp; lpWideCharStr
0x18001698f  test    eax, eax
0x180016991  jnz     short loc_1800169EF
0x180016993  mov     [rsp+188h+cbMultiByte], 2
0x18001699b  lea     rdx, [rsp+188h+var_148]
0x1800169a0  xor     r9d, r9d
0x1800169a3  mov     dword ptr [rsp+188h+lpMultiByteStr], 1
0x1800169ab  lea     rcx, [rsp+188h+MultiByteStr]
0x1800169b0  call    cs:__imp_DnsNameCopy
0x1800169b7  nop     dword ptr [rax+rax+00h]
0x1800169bc  test    eax, eax
0x1800169be  jz      short loc_180016A26
0x1800169c0  mov     r9, rbx
0x1800169c3  lea     rdx, [rsp+188h+MultiByteStr]
0x1800169c8  inc     rbx
0x1800169cb  xor     cl, cl
0x1800169cd  xor     r8b, r8b
0x1800169d0  cmp     [rsp+188h+MultiByteStr], cl
0x1800169d4  jz      loc_180016A89
0x1800169da  cmp     rbx, r14
0x1800169dd  jnb     loc_180016A82
0x1800169e3  mov     al, [rdx]
0x1800169e5  cmp     al, 2Eh ; '.'
0x1800169e7  jz      short loc_180016A2F
0x1800169e9  mov     [rbx], al
0x1800169eb  inc     cl
0x1800169ed  jmp     short loc_180016A41
0x1800169ef  mov     [rsp+188h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x1800169f4  lea     rax, [rsp+188h+MultiByteStr]
0x1800169f9  mov     [rsp+188h+lpDefaultChar], rdi; lpDefaultChar
0x1800169fe  or      r9d, 0FFFFFFFFh; cchWideChar
0x180016a02  mov     [rsp+188h+cbMultiByte], 100h; cbMultiByte
0x180016a0a  xor     edx, edx; dwFlags
0x180016a0c  mov     ecx, 0FDE9h; CodePage
0x180016a11  mov     [rsp+188h+lpMultiByteStr], rax; lpMultiByteStr
0x180016a16  call    cs:__imp_WideCharToMultiByte
0x180016a1d  nop     dword ptr [rax+rax+00h]
0x180016a22  test    eax, eax
0x180016a24  jg      short loc_1800169C0
0x180016a26  call    GetLastErrorOrUnknown
0x180016a2b  mov     ebx, eax
0x180016a2d  jmp     short loc_180016A92
0x180016a2f  lea     eax, [rcx-1]
0x180016a32  cmp     al, 3Eh ; '>'
0x180016a34  ja      short loc_180016A7B
0x180016a36  mov     [r9], cl
0x180016a39  xor     cl, cl
0x180016a3b  inc     r8b
0x180016a3e  mov     r9, rbx
0x180016a41  inc     rdx
0x180016a44  inc     edi
0x180016a46  inc     rbx
0x180016a49  cmp     byte ptr [rdx], 0
0x180016a4c  jnz     short loc_1800169DA
0x180016a4e  cmp     cl, 3Fh ; '?'
0x180016a51  ja      short loc_180016A7B
0x180016a53  test    cl, cl
0x180016a55  jz      short loc_180016A64
0x180016a57  inc     edi
0x180016a59  mov     [r9], cl
0x180016a5c  cmp     edi, 0FFh
0x180016a62  ja      short loc_180016A7B
0x180016a64  test    r8b, r8b
0x180016a67  jz      short loc_180016A89
0x180016a69  cmp     rbx, r14
0x180016a6c  ja      short loc_180016A89
0x180016a6e  inc     edi
0x180016a70  mov     byte ptr [rbx], 0
0x180016a73  cmp     edi, 0FFh
0x180016a79  jbe     short loc_180016A89
0x180016a7b  mov     ebx, 4BCh
0x180016a80  jmp     short loc_180016A92
0x180016a82  mov     ebx, 7Ah ; 'z'
0x180016a87  jmp     short loc_180016A92
0x180016a89  xor     ebx, ebx
0x180016a8b  test    rsi, rsi
0x180016a8e  jz      short loc_180016A92
0x180016a90  mov     [rsi], edi
0x180016a92  test    byte ptr cs:xmmword_1800423E0, 10h
0x180016a99  jz      short loc_180016AB3
0x180016a9b  mov     edx, 35h ; '5'
0x180016aa0  mov     dword ptr [rsp+188h+lpMultiByteStr], edi
0x180016aa4  mov     r9d, ebx
0x180016aa7  lea     r8, WPP_0db776d5b2973b109b50142f7c503650_Traceguids
0x180016aae  call    WPP_SF_Dd
0x180016ab3  mov     eax, ebx
0x180016ab5  mov     rcx, [rsp+188h+var_38]
0x180016abd  xor     rcx, rsp; StackCookie
0x180016ac0  call    __security_check_cookie
0x180016ac5  add     rsp, 160h
0x180016acc  pop     r14
0x180016ace  pop     rdi
0x180016acf  pop     rsi
0x180016ad0  pop     rbp
0x180016ad1  pop     rbx
0x180016ad2  retn
```
