# DhcpRegisterParamChange

- ea: `0x180008aa0`
- end: `0x180008c49`
- name: `DhcpRegisterParamChange`
- size: `425`
- prototype: `DWORD __stdcall(DWORD Flags, LPVOID Reserved, LPWSTR AdapterName, LPDHCPCAPI_CLASSID ClassId, DHCPCAPI_PARAMS_ARRAY *__struct_ptr Params, LPVOID Handle)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800048c0`
- `0x180008aa0`
- `0x180008c50`
- `0x180012850`
- `0x180012ad0`

## import_xrefs

- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180008ae7`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x180008ae7`

## pseudocode

```c
DWORD __stdcall DhcpRegisterParamChange(
        DWORD Flags,
        LPVOID Reserved,
        LPWSTR AdapterName,
        LPDHCPCAPI_CLASSID ClassId,
        DHCPCAPI_PARAMS_ARRAY *Params,
        LPVOID Handle)
{
  LPWSTR CommandLineW; // rax
  int v11; // ecx
  DWORD v12; // ebx
  unsigned int v13; // r8d
  unsigned int v14; // edx
  ULONG i; // r9d
  LPDHCPCAPI_PARAMS v16; // rax
  __int64 v17; // rcx
  char OptionId; // r10
  __int64 v19; // rax
  __int64 v20; // rax
  char *v21; // r9
  int v22; // ecx
  _BOOL8 v23; // rax
  LPBYTE Data; // rdx
  ULONG nBytesData; // r8d
  char v27; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v28; // [rsp+44h] [rbp-BCh]
  _BYTE *v29; // [rsp+50h] [rbp-B0h]
  unsigned int v30; // [rsp+58h] [rbp-A8h]
  char v31; // [rsp+60h] [rbp-A0h] BYREF
  int v32; // [rsp+64h] [rbp-9Ch]
  int v33; // [rsp+68h] [rbp-98h]
  _BYTE *v34; // [rsp+70h] [rbp-90h]
  unsigned int v35; // [rsp+78h] [rbp-88h]
  _BYTE v36[256]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v37[256]; // [rsp+180h] [rbp+80h] BYREF

  if ( (xmmword_18001E1E0 & 0x10) != 0 )
  {
    CommandLineW = GetCommandLineW();
    WPP_SF_SS(
      v11,
      122,
      (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids,
      (_DWORD)AdapterName,
      (__int64)CommandLineW);
  }
  if ( Flags == 1 && !Reserved && AdapterName && Params->nParams && Handle )
  {
    v13 = 0;
    v14 = 0;
    for ( i = 0; i < Params->nParams; ++i )
    {
      if ( v13 >= 0x100 || v14 >= 0x100 )
        goto LABEL_4;
      v16 = Params->Params;
      v17 = i;
      OptionId = v16[v17].OptionId;
      if ( v16[v17].IsVendor )
      {
        v19 = v13++;
        v37[v19] = OptionId;
      }
      else
      {
        v20 = v14++;
        v36[v20] = OptionId;
      }
    }
    v28 = 55;
    v30 = v14;
    v29 = v36;
    v21 = &v27;
    v32 = 0;
    v34 = v37;
    v22 = 0;
    v33 = 1;
    if ( !v14 )
      v21 = &v31;
    v35 = v13;
    v23 = v14 != 0;
    LOBYTE(v22) = v13 != 0;
    if ( ClassId )
    {
      Data = ClassId->Data;
      nBytesData = ClassId->nBytesData;
    }
    else
    {
      LODWORD(Data) = 0;
      nBytesData = 0;
    }
    v12 = DhcpRegisterParameterChangeNotification(
            (_DWORD)AdapterName,
            (_DWORD)Data,
            nBytesData,
            (_DWORD)v21,
            v22 + (int)v23);
  }
  else
  {
LABEL_4:
    v12 = 87;
  }
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_SD(1028, 123, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, (_DWORD)AdapterName, v12);
  return v12;
}

```

## disassembly

```asm
0x180008aa0  mov     [rsp-8+arg_0], rbx
0x180008aa5  push    rbp
0x180008aa6  push    rsi
0x180008aa7  push    rdi
0x180008aa8  push    r14
0x180008aaa  push    r15
0x180008aac  lea     rbp, [rsp-190h]
0x180008ab4  sub     rsp, 290h
0x180008abb  mov     rax, cs:__security_cookie
0x180008ac2  xor     rax, rsp
0x180008ac5  mov     [rbp+1B0h+var_30], rax
0x180008acc  mov     r15, [rbp+1B0h+Handle]
0x180008ad3  mov     r14, r9
0x180008ad6  mov     rdi, r8
0x180008ad9  mov     rsi, rdx
0x180008adc  mov     ebx, ecx
0x180008ade  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180008ae5  jz      short loc_180008B06
0x180008ae7  call    cs:__imp_GetCommandLineW
0x180008aed  mov     edx, 7Ah ; 'z'
0x180008af2  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180008af9  mov     r9, rdi
0x180008afc  mov     [rsp+2B0h+var_290], rax
0x180008b01  call    WPP_SF_SS
0x180008b06  cmp     ebx, 1
0x180008b09  jz      short loc_180008B15
0x180008b0b  mov     ebx, 57h ; 'W'
0x180008b10  jmp     loc_180008BFB
0x180008b15  xor     ebx, ebx
0x180008b17  test    rsi, rsi
0x180008b1a  jnz     short loc_180008B0B
0x180008b1c  test    rdi, rdi
0x180008b1f  jz      short loc_180008B0B
0x180008b21  mov     r11, [rbp+1B0h+Params]
0x180008b28  cmp     [r11], ebx
0x180008b2b  jbe     short loc_180008B0B
0x180008b2d  test    r15, r15
0x180008b30  jz      short loc_180008B0B
0x180008b32  mov     r8d, ebx
0x180008b35  mov     edx, ebx
0x180008b37  mov     r9d, ebx
0x180008b3a  mov     esi, 100h
0x180008b3f  cmp     r9d, [r11]
0x180008b42  jnb     short loc_180008B81
0x180008b44  cmp     r8d, esi
0x180008b47  jnb     short loc_180008B0B
0x180008b49  cmp     edx, esi
0x180008b4b  jnb     short loc_180008B0B
0x180008b4d  mov     rax, [r11+8]
0x180008b51  mov     ecx, r9d
0x180008b54  shl     rcx, 5
0x180008b58  mov     r10b, [rcx+rax+4]
0x180008b5d  cmp     [rcx+rax+8], ebx
0x180008b61  jz      short loc_180008B73
0x180008b63  mov     eax, r8d
0x180008b66  inc     r8d
0x180008b69  mov     [rbp+rax+1B0h+var_130], r10b
0x180008b71  jmp     short loc_180008B7C
0x180008b73  mov     eax, edx
0x180008b75  inc     edx
0x180008b77  mov     [rbp+rax+1B0h+var_230], r10b
0x180008b7c  inc     r9d
0x180008b7f  jmp     short loc_180008B3F
0x180008b81  test    edx, edx
0x180008b83  mov     [rsp+2B0h+var_26C], 37h ; '7'
0x180008b8c  lea     rax, [rbp+1B0h+var_230]
0x180008b90  mov     [rsp+2B0h+var_258], edx
0x180008b94  mov     [rsp+2B0h+var_260], rax
0x180008b99  lea     r9, [rsp+2B0h+var_270]
0x180008b9e  lea     rax, [rbp+1B0h+var_130]
0x180008ba5  mov     [rsp+2B0h+var_24C], ebx
0x180008ba9  mov     [rsp+2B0h+var_240], rax
0x180008bae  mov     ecx, ebx
0x180008bb0  lea     rax, [rsp+2B0h+var_250]
0x180008bb5  mov     [rsp+2B0h+var_248], 1
0x180008bbd  cmovz   r9, rax
0x180008bc1  mov     [rsp+2B0h+var_238], r8d
0x180008bc6  mov     eax, ebx
0x180008bc8  setnz   al
0x180008bcb  test    r8d, r8d
0x180008bce  setnz   cl
0x180008bd1  test    r14, r14
0x180008bd4  jz      short loc_180008BE0
0x180008bd6  mov     rdx, [r14+8]
0x180008bda  mov     r8d, [r14+10h]
0x180008bde  jmp     short loc_180008BE6
0x180008be0  mov     rdx, rbx
0x180008be3  mov     r8d, ebx
0x180008be6  add     eax, ecx
0x180008be8  mov     [rsp+2B0h+var_280], r15
0x180008bed  mov     rcx, rdi
0x180008bf0  mov     dword ptr [rsp+2B0h+var_290], eax
0x180008bf4  call    DhcpRegisterParameterChangeNotification
0x180008bf9  mov     ebx, eax
0x180008bfb  test    byte ptr cs:xmmword_18001E1E0, 10h
0x180008c02  jz      short loc_180008C21
0x180008c04  mov     edx, 7Bh ; '{'
0x180008c09  mov     dword ptr [rsp+2B0h+var_290], ebx
0x180008c0d  mov     ecx, 404h
0x180008c12  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x180008c19  mov     r9, rdi
0x180008c1c  call    WPP_SF_SD
0x180008c21  mov     eax, ebx
0x180008c23  mov     rcx, [rbp+1B0h+var_30]
0x180008c2a  xor     rcx, rsp; StackCookie
0x180008c2d  call    __security_check_cookie
0x180008c32  mov     rbx, [rsp+2B0h+arg_0]
0x180008c3a  add     rsp, 290h
0x180008c41  pop     r15
0x180008c43  pop     r14
0x180008c45  pop     rdi
0x180008c46  pop     rsi
0x180008c47  pop     rbp
0x180008c48  retn
```
