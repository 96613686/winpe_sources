# DhcpDynDnsGetDynDNSOptionDomain

- ea: `0x180041a24`
- end: `0x180041c7c`
- name: `DhcpDynDnsGetDynDNSOptionDomain`
- size: `600`
- prototype: `__int64 __fastcall(void *, unsigned int *, HKEY, __int64, CHAR *lpMultiByteStr, int cbMultiByte, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800416ec`

## callees

- `0x180004124`
- `0x180005670`
- `0x180010b44`
- `0x180018fbc`
- `0x18001cef0`
- `0x18001d826`
- `0x180041a24`
- `0x180047e3c`
- `0x18004d1a0`

## import_xrefs

- `ntdll!RtlOemStringToUnicodeString` at `0x180041c15`
- `ntdll!RtlOemStringToUnicodeString` at `0x180041c15`
- `ntdll!RtlNtStatusToDosError` at `0x180041c21`
- `ntdll!RtlNtStatusToDosError` at `0x180041c21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041b54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180041b54`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180041b4a`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180041b4a`

## pseudocode

```c
__int64 __fastcall DhcpDynDnsGetDynDNSOptionDomain(
        void *a1,
        unsigned int *a2,
        HKEY a3,
        __int64 a4,
        CHAR *lpMultiByteStr,
        int cbMultiByte,
        int a7)
{
  DWORD v10; // esi
  WCHAR *v11; // r14
  int PerAdapterRegConfig; // eax
  unsigned int v13; // eax
  ULONG LastError; // ebx
  unsigned int v15; // eax
  unsigned int v16; // esi
  int v17; // eax
  DWORD nSize; // [rsp+30h] [rbp-D0h] BYREF
  DWORD v20; // [rsp+34h] [rbp-CCh] BYREF
  int v21; // [rsp+38h] [rbp-C8h]
  STRING SourceString; // [rsp+40h] [rbp-C0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[256]; // [rsp+60h] [rbp-A0h] BYREF

  memset_0(Buffer, 0, sizeof(Buffer));
  v21 = 0;
  v10 = 0;
  v20 = 0;
  nSize = 512;
  v11 = 0;
  PerAdapterRegConfig = GetPerAdapterRegConfig(a3, &nSize);
  if ( v21 )
  {
    if ( !PerAdapterRegConfig )
    {
      v13 = WxStringCchLengthDWordW(Buffer, 0x7FFFFFFF, &v20);
      LastError = WX_WIN32_FROM_HR(v13);
      if ( LastError )
        goto LABEL_19;
      LastError = 0;
      goto LABEL_14;
    }
    if ( lpMultiByteStr && *lpMultiByteStr )
    {
      if ( !a7 )
      {
        SourceString.Length = cbMultiByte;
        SourceString.MaximumLength = cbMultiByte;
        *(_QWORD *)&DestinationString.Length = 0x2000000;
        *(_DWORD *)(&SourceString.MaximumLength + 1) = 0;
        DestinationString.Buffer = Buffer;
        SourceString.Buffer = lpMultiByteStr;
        v17 = RtlOemStringToUnicodeString(&DestinationString, &SourceString, 0);
        if ( v17 < 0 )
        {
          LastError = RtlNtStatusToDosError(v17);
          if ( LastError )
            goto LABEL_19;
        }
        LastError = 0;
        v10 = DestinationString.Length >> 1;
        goto LABEL_15;
      }
      nSize = 256;
      if ( !(unsigned int)ConvertPunycodeToUnicode(lpMultiByteStr, cbMultiByte) )
      {
        v10 = nSize;
        v11 = Buffer;
        v20 = nSize;
      }
    }
  }
  LastError = 0;
  if ( !v11 )
  {
    nSize = 256;
    if ( !GetComputerNameExW(ComputerNameDnsDomain, Buffer, &nSize) )
    {
      LastError = GetLastError();
      if ( LastError )
        goto LABEL_19;
    }
    v15 = WxStringCchLengthDWordW(Buffer, 0x7FFFFFFF, &v20);
    LastError = WX_WIN32_FROM_HR(v15);
    if ( LastError )
      goto LABEL_19;
LABEL_14:
    v10 = v20;
LABEL_15:
    v11 = Buffer;
  }
  if ( !*v11 )
  {
    *a2 = 0;
    return LastError;
  }
  v16 = 2 * v10;
  if ( v16 <= *a2 )
  {
    *a2 = v16;
    memcpy_0(a1, v11, v16);
    return LastError;
  }
  LastError = 122;
LABEL_19:
  if ( (xmmword_1800616A0 & 2) != 0 )
    WPP_SF_D(1025, 10, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x180041a24  push    rbp
0x180041a26  push    rbx
0x180041a27  push    rsi
0x180041a28  push    rdi
0x180041a29  push    r12
0x180041a2b  push    r13
0x180041a2d  push    r14
0x180041a2f  push    r15
0x180041a31  lea     rbp, [rsp-178h]
0x180041a39  sub     rsp, 278h
0x180041a40  mov     rax, cs:__security_cookie
0x180041a47  xor     rax, rsp
0x180041a4a  mov     [rbp+1B0h+var_50], rax
0x180041a51  mov     r15, [rbp+1B0h+lpMultiByteStr]
0x180041a58  mov     rbx, r8
0x180041a5b  mov     r12, rdx
0x180041a5e  mov     r13, rcx
0x180041a61  xor     edx, edx; Val
0x180041a63  lea     rcx, [rsp+2B0h+Buffer]; void *
0x180041a68  mov     r8d, 200h; Size
0x180041a6e  mov     rdi, r9
0x180041a71  call    memset_0
0x180041a76  lea     rax, [rsp+2B0h+nSize]
0x180041a7b  mov     [rsp+2B0h+var_278], 0
0x180041a83  xor     esi, esi
0x180041a85  mov     [rsp+2B0h+var_290], rax; LPDWORD
0x180041a8a  lea     r9, [rsp+2B0h+Buffer]
0x180041a8f  mov     [rsp+2B0h+var_27C], esi
0x180041a93  lea     r8, [rsp+2B0h+var_278]
0x180041a98  mov     [rsp+2B0h+nSize], 200h
0x180041aa0  mov     rdx, rdi
0x180041aa3  mov     rcx, rbx; hKey
0x180041aa6  xor     r14d, r14d
0x180041aa9  call    GetPerAdapterRegConfig
0x180041aae  xor     edi, edi
0x180041ab0  cmp     [rsp+2B0h+var_278], edi
0x180041ab4  jz      short loc_180041B2D
0x180041ab6  test    eax, eax
0x180041ab8  jnz     short loc_180041AE6
0x180041aba  lea     r8, [rsp+2B0h+var_27C]
0x180041abf  mov     edx, 7FFFFFFFh
0x180041ac4  lea     rcx, [rsp+2B0h+Buffer]
0x180041ac9  call    WxStringCchLengthDWordW
0x180041ace  mov     ecx, eax
0x180041ad0  call    WX_WIN32_FROM_HR
0x180041ad5  mov     ebx, eax
0x180041ad7  test    eax, eax
0x180041ad9  jnz     loc_180041BA7
0x180041adf  mov     ebx, edi
0x180041ae1  jmp     loc_180041B81
0x180041ae6  test    r15, r15
0x180041ae9  jz      short loc_180041B2D
0x180041aeb  cmp     [r15], dil
0x180041aee  jz      short loc_180041B2D
0x180041af0  cmp     [rbp+1B0h+arg_30], edi
0x180041af6  jz      loc_180041BD2
0x180041afc  mov     edx, [rbp+1B0h+cbMultiByte]; cbMultiByte
0x180041b02  lea     r9, [rsp+2B0h+nSize]
0x180041b07  lea     r8, [rsp+2B0h+Buffer]
0x180041b0c  mov     [rsp+2B0h+nSize], 100h
0x180041b14  mov     rcx, r15; lpMultiByteStr
0x180041b17  call    ConvertPunycodeToUnicode
0x180041b1c  test    eax, eax
0x180041b1e  jnz     short loc_180041B2D
0x180041b20  mov     esi, [rsp+2B0h+nSize]
0x180041b24  lea     r14, [rsp+2B0h+Buffer]
0x180041b29  mov     [rsp+2B0h+var_27C], esi
0x180041b2d  mov     ebx, edi
0x180041b2f  test    r14, r14
0x180041b32  jnz     short loc_180041B8A
0x180041b34  lea     r8, [rsp+2B0h+nSize]; nSize
0x180041b39  mov     [rsp+2B0h+nSize], 100h
0x180041b41  lea     rdx, [rsp+2B0h+Buffer]; lpBuffer
0x180041b46  lea     ecx, [r14+2]; NameType
0x180041b4a  call    cs:__imp_GetComputerNameExW
0x180041b50  test    eax, eax
0x180041b52  jnz     short loc_180041B60
0x180041b54  call    cs:__imp_GetLastError
0x180041b5a  mov     ebx, eax
0x180041b5c  test    eax, eax
0x180041b5e  jnz     short loc_180041BA7
0x180041b60  lea     r8, [rsp+2B0h+var_27C]
0x180041b65  mov     edx, 7FFFFFFFh
0x180041b6a  lea     rcx, [rsp+2B0h+Buffer]
0x180041b6f  call    WxStringCchLengthDWordW
0x180041b74  mov     ecx, eax
0x180041b76  call    WX_WIN32_FROM_HR
0x180041b7b  mov     ebx, eax
0x180041b7d  test    eax, eax
0x180041b7f  jnz     short loc_180041BA7
0x180041b81  mov     esi, [rsp+2B0h+var_27C]
0x180041b85  lea     r14, [rsp+2B0h+Buffer]
0x180041b8a  cmp     [r14], di
0x180041b8e  jz      loc_180041C53
0x180041b94  add     esi, esi
0x180041b96  mov     eax, esi
0x180041b98  cmp     esi, [r12]
0x180041b9c  jbe     loc_180041C3F
0x180041ba2  mov     ebx, 7Ah ; 'z'
0x180041ba7  test    byte ptr cs:xmmword_1800616A0, 2
0x180041bae  jz      loc_180041C57
0x180041bb4  mov     edx, 0Ah
0x180041bb9  lea     r8, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids
0x180041bc0  mov     ecx, 401h
0x180041bc5  mov     r9d, ebx
0x180041bc8  call    WPP_SF_D
0x180041bcd  jmp     loc_180041C57
0x180041bd2  movzx   eax, word ptr [rbp+1B0h+cbMultiByte]
0x180041bd9  lea     rdx, [rsp+2B0h+SourceString]; SourceString
0x180041bde  mov     [rsp+2B0h+SourceString.Length], ax
0x180041be3  lea     rcx, [rsp+2B0h+DestinationString]; DestinationString
0x180041be8  mov     [rsp+2B0h+SourceString.MaximumLength], ax
0x180041bed  xorps   xmm0, xmm0
0x180041bf0  movups  xmmword ptr [rsp+2B0h+DestinationString.Length], xmm0
0x180041bf5  lea     rax, [rsp+2B0h+Buffer]
0x180041bfa  mov     dword ptr [rsp+2B0h+SourceString+4], edi
0x180041bfe  mov     [rsp+2B0h+DestinationString.Buffer], rax
0x180041c03  xor     r8d, r8d; AllocateDestinationString
0x180041c06  mov     eax, 200h
0x180041c0b  mov     [rsp+2B0h+SourceString.Buffer], r15
0x180041c10  mov     [rsp+2B0h+DestinationString.MaximumLength], ax
0x180041c15  call    cs:__imp_RtlOemStringToUnicodeString
0x180041c1b  test    eax, eax
0x180041c1d  jns     short loc_180041C31
0x180041c1f  mov     ecx, eax; Status
0x180041c21  call    cs:__imp_RtlNtStatusToDosError
0x180041c27  mov     ebx, eax
0x180041c29  test    eax, eax
0x180041c2b  jnz     loc_180041BA7
0x180041c31  movzx   esi, [rsp+2B0h+DestinationString.Length]
0x180041c36  mov     ebx, edi
0x180041c38  shr     esi, 1
0x180041c3a  jmp     loc_180041B85
0x180041c3f  mov     r8, rax; Size
0x180041c42  mov     [r12], esi
0x180041c46  mov     rdx, r14; Src
0x180041c49  mov     rcx, r13; void *
0x180041c4c  call    memcpy_0
0x180041c51  jmp     short loc_180041C57
0x180041c53  mov     [r12], edi
0x180041c57  mov     eax, ebx
0x180041c59  mov     rcx, [rbp+1B0h+var_50]
0x180041c60  xor     rcx, rsp; StackCookie
0x180041c63  call    __security_check_cookie
0x180041c68  add     rsp, 278h
0x180041c6f  pop     r15
0x180041c71  pop     r14
0x180041c73  pop     r13
0x180041c75  pop     r12
0x180041c77  pop     rdi
0x180041c78  pop     rsi
0x180041c79  pop     rbx
0x180041c7a  pop     rbp
0x180041c7b  retn
```
