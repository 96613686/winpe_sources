# LogPPPPacket

- ea: `0x180012a20`
- end: `0x180012d4c`
- name: `LogPPPPacket`
- size: `812`
- prototype: `char __fastcall(int, __int64, unsigned __int8 *, unsigned int)`
- caller_count: `12`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800023c0`
- `0x18000442c`
- `0x18000c3e8`
- `0x18000d5e4`
- `0x18000d6b4`
- `0x18000d8b4`
- `0x18000dd20`
- `0x18000deb0`
- `0x18000dfac`
- `0x18000e1e0`
- `0x18000e298`
- `0x18000e358`

## callees

- `0x180001460`
- `0x180001d3e`
- `0x180003170`
- `0x180012a20`
- `0x1800133e0`
- `0x18002b0dc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180012a91`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x180012a91`

## string_xrefs

- `0x180012b32`: `Protocol specific`
- `0x180012b53`: `Protocol specific`
- `0x180012b6a`: `Protocol specific`
- `0x180012c96`: `%hsProtocol = %hs, Type = %hs, Length = 0x%x, Id = 0x%x, Port = %d`

## pseudocode

```c
char __fastcall LogPPPPacket(int a1, __int64 a2, unsigned __int8 *a3, unsigned int a4)
{
  unsigned int v6; // ebx
  const char *v7; // r14
  const char *v8; // rsi
  unsigned __int8 v9; // dl
  int v10; // eax
  char result; // al
  const char *v12; // r13
  const char *v13; // r9
  const char *v14; // r8
  __int64 v15; // [rsp+28h] [rbp-E8h]
  __int64 v16; // [rsp+30h] [rbp-E0h]
  unsigned __int8 v17; // [rsp+90h] [rbp-80h]
  unsigned int v19; // [rsp+98h] [rbp-78h]
  int v20; // [rsp+9Ch] [rbp-74h]
  _SYSTEMTIME SystemTime; // [rsp+B0h] [rbp-60h] BYREF
  int v23; // [rsp+C0h] [rbp-50h] BYREF
  char v24[2044]; // [rsp+C4h] [rbp-4Ch] BYREF

  v19 = a4;
  v20 = 1;
  v23 = 0;
  SystemTime = 0;
  memset_0(v24, 0, sizeof(v24));
  v6 = dword_18004DA18;
  GetSystemTime(&SystemTime);
  v7 = "UNKNOWN";
  if ( a4 <= 4 )
  {
    v9 = 0;
    v8 = "UNKNOWN";
    if ( a4 <= 2 )
    {
      v17 = 0;
      goto LABEL_27;
    }
  }
  else
  {
    if ( (unsigned __int8)(a3[2] - 1) > 0xCu )
      v8 = "UNKNOWN";
    else
      v8 = (const char *)FsmCodes[a3[2]];
    v9 = a3[3];
  }
  v10 = a3[1];
  v17 = v9;
  switch ( v10 + (*a3 << 8) )
  {
    case 32801:
      v7 = "IPCP";
      goto LABEL_27;
    case 32855:
      v7 = "IPv6CP";
      goto LABEL_27;
    case 33021:
      v7 = "CCP";
      goto LABEL_27;
    case 49185:
      v7 = "LCP";
      goto LABEL_27;
    case 49187:
      v7 = "PAP";
      v20 = 0;
      v8 = "Protocol specific";
      goto LABEL_27;
    case 49193:
      v7 = "CBCP";
      goto LABEL_20;
    case 49699:
      v7 = "CHAP";
LABEL_20:
      v8 = "Protocol specific";
      goto LABEL_27;
    case 49703:
      v7 = "EAP";
      v8 = "Protocol specific";
      break;
  }
  if ( a4 > v6 )
    v19 = v6;
LABEL_27:
  result = byte_18004DF34;
  v12 = ">";
  if ( (byte_18004DF34 & 1) != 0 )
  {
    v13 = "received";
    if ( !a1 )
      v13 = "sent";
    LOWORD(v23) = 0;
    v14 = ">";
    if ( !a1 )
      v14 = "<";
    FormatRRASErrorString(
      (wchar_t *)&v23,
      L"%hsPPP packet %hs at %0*d/%0*d/%0*d %0*d:%0*d:%0*d:%0*d",
      v14,
      v13,
      2,
      SystemTime.wMonth,
      2,
      SystemTime.wDay,
      2,
      SystemTime.wYear,
      2,
      SystemTime.wHour,
      2,
      SystemTime.wMinute,
      2,
      SystemTime.wSecond,
      3,
      SystemTime.wMilliseconds);
    result = byte_18004DF34;
    if ( (byte_18004DF34 & 1) != 0 )
    {
      McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v23);
      result = byte_18004DF34;
    }
    if ( (result & 1) != 0 )
    {
      LOWORD(v23) = 0;
      if ( !a1 )
        v12 = "<";
      LODWORD(v16) = v17;
      LODWORD(v15) = a4;
      FormatRRASErrorString(
        (wchar_t *)&v23,
        L"%hsProtocol = %hs, Type = %hs, Length = 0x%x, Id = 0x%x, Port = %d",
        v12,
        v7,
        v8,
        v15,
        v16,
        *(_QWORD *)(a2 + 16));
      result = byte_18004DF34;
      if ( (byte_18004DF34 & 1) != 0 )
      {
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasPppTraceInfo, &v23);
        result = byte_18004DF34;
      }
    }
  }
  if ( v20 )
  {
    if ( (result & 1) != 0 )
      return McTemplateU0zqbr1_EventWriteTransfer(
               (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
               (unsigned int)RasPppTraceByteBuffer,
               (unsigned int)L"PPP Packet buffer",
               v19,
               (__int64)a3);
  }
  return result;
}

```

## disassembly

```asm
0x180012a20  mov     [rsp-8+arg_0], rbx
0x180012a25  push    rbp
0x180012a26  push    rsi
0x180012a27  push    rdi
0x180012a28  push    r12
0x180012a2a  push    r13
0x180012a2c  push    r14
0x180012a2e  push    r15
0x180012a30  lea     rbp, [rsp-7C0h]
0x180012a38  sub     rsp, 8D0h
0x180012a3f  mov     rax, cs:__security_cookie
0x180012a46  xor     rax, rsp
0x180012a49  mov     [rbp+7F0h+var_40], rax
0x180012a50  mov     r15, r8
0x180012a53  mov     [rbp+7F0h+var_858], rdx
0x180012a57  mov     edi, ecx
0x180012a59  mov     [rbp+7F0h+var_86C], ecx
0x180012a5c  xorps   xmm0, xmm0
0x180012a5f  mov     [rbp+7F0h+var_868], r9d
0x180012a63  xor     eax, eax
0x180012a65  mov     [rbp+7F0h+var_864], 1
0x180012a6c  xor     edx, edx; Val
0x180012a6e  mov     [rbp+7F0h+var_840], eax
0x180012a71  mov     r8d, 7FCh; Size
0x180012a77  lea     rcx, [rbp+7F0h+var_83C]; void *
0x180012a7b  movups  xmmword ptr [rbp+7F0h+SystemTime.wYear], xmm0
0x180012a7f  mov     r12d, r9d
0x180012a82  call    memset_0
0x180012a87  mov     ebx, cs:dword_18004DA18
0x180012a8d  lea     rcx, [rbp+7F0h+SystemTime]; lpSystemTime
0x180012a91  call    cs:__imp_GetSystemTime
0x180012a98  nop     dword ptr [rax+rax+00h]
0x180012a9d  lea     r14, aUnknown; "UNKNOWN"
0x180012aa4  cmp     r12d, 4
0x180012aa8  jbe     short loc_180012ACF
0x180012aaa  mov     al, [r15+2]
0x180012aae  dec     al
0x180012ab0  cmp     al, 0Ch
0x180012ab2  ja      short loc_180012AC6
0x180012ab4  movzx   eax, byte ptr [r15+2]
0x180012ab9  lea     rsi, FsmCodes
0x180012ac0  mov     rsi, [rsi+rax*8]
0x180012ac4  jmp     short loc_180012AC9
0x180012ac6  mov     rsi, r14
0x180012ac9  mov     dl, [r15+3]
0x180012acd  jmp     short loc_180012ADE
0x180012acf  xor     dl, dl
0x180012ad1  mov     rsi, r14
0x180012ad4  cmp     r12d, 2
0x180012ad8  jbe     loc_180012B97
0x180012ade  movzx   ecx, byte ptr [r15]
0x180012ae2  movzx   eax, byte ptr [r15+1]
0x180012ae7  shl     ecx, 8
0x180012aea  add     ecx, eax
0x180012aec  mov     [rbp+7F0h+var_870], dl
0x180012aef  sub     ecx, 8021h
0x180012af5  jz      loc_180012B8E
0x180012afb  sub     ecx, 36h ; '6'
0x180012afe  jz      loc_180012B85
0x180012b04  sub     ecx, 0A6h
0x180012b0a  jz      short loc_180012B7C
0x180012b0c  sub     ecx, 3F24h
0x180012b12  jz      short loc_180012B73
0x180012b14  sub     ecx, 2
0x180012b17  jz      short loc_180012B5C
0x180012b19  sub     ecx, 6
0x180012b1c  jz      short loc_180012B4C
0x180012b1e  sub     ecx, 1FAh
0x180012b24  jz      short loc_180012B43
0x180012b26  cmp     ecx, 4
0x180012b29  jnz     short loc_180012B39
0x180012b2b  lea     r14, aEap; "EAP"
0x180012b32  lea     rsi, aProtocolSpecif; "Protocol specific"
0x180012b39  cmp     r12d, ebx
0x180012b3c  jbe     short loc_180012B9A
0x180012b3e  mov     [rbp+7F0h+var_868], ebx
0x180012b41  jmp     short loc_180012B9A
0x180012b43  lea     r14, aChap; "CHAP"
0x180012b4a  jmp     short loc_180012B53
0x180012b4c  lea     r14, aCbcp; "CBCP"
0x180012b53  lea     rsi, aProtocolSpecif; "Protocol specific"
0x180012b5a  jmp     short loc_180012B9A
0x180012b5c  lea     r14, aPap; "PAP"
0x180012b63  mov     [rbp+7F0h+var_864], 0
0x180012b6a  lea     rsi, aProtocolSpecif; "Protocol specific"
0x180012b71  jmp     short loc_180012B9A
0x180012b73  lea     r14, aLcp; "LCP"
0x180012b7a  jmp     short loc_180012B9A
0x180012b7c  lea     r14, aCcp; "CCP"
0x180012b83  jmp     short loc_180012B9A
0x180012b85  lea     r14, aIpv6cp; "IPv6CP"
0x180012b8c  jmp     short loc_180012B9A
0x180012b8e  lea     r14, aIpcp; "IPCP"
0x180012b95  jmp     short loc_180012B9A
0x180012b97  mov     [rbp+7F0h+var_870], dl
0x180012b9a  mov     al, cs:byte_18004DF34
0x180012ba0  lea     r8, asc_18003B660; "<"
0x180012ba7  mov     [rbp+7F0h+var_860], r8
0x180012bab  lea     r13, asc_18003B65C; ">"
0x180012bb2  test    al, 1
0x180012bb4  jz      loc_180012CF4
0x180012bba  movzx   ecx, [rbp+7F0h+SystemTime.wSecond]
0x180012bbe  lea     r8, aSent; "sent"
0x180012bc5  movzx   edx, [rbp+7F0h+SystemTime.wMinute]
0x180012bc9  lea     r9, aReceived; "received"
0x180012bd0  movzx   r10d, [rbp+7F0h+SystemTime.wHour]
0x180012bd5  xor     eax, eax
0x180012bd7  movzx   r11d, [rbp+7F0h+SystemTime.wYear]
0x180012bdc  cmp     [rbp+7F0h+var_86C], 0
0x180012be0  movzx   ebx, [rbp+7F0h+SystemTime.wDay]
0x180012be4  movzx   edi, [rbp+7F0h+SystemTime.wMonth]
0x180012be8  cmovz   r9, r8
0x180012bec  mov     word ptr [rbp+7F0h+var_840], ax
0x180012bf0  mov     r8, r13
0x180012bf3  movzx   eax, [rbp+7F0h+SystemTime.wMilliseconds]
0x180012bf7  cmovz   r8, [rbp+7F0h+var_860]
0x180012bfc  mov     [rsp+900h+var_878], eax
0x180012c03  mov     eax, 2
0x180012c08  mov     [rsp+900h+var_880], 3
0x180012c13  mov     [rsp+900h+var_888], ecx
0x180012c17  lea     rcx, [rbp+7F0h+var_840]
0x180012c1b  mov     [rsp+900h+var_890], eax
0x180012c1f  mov     [rsp+900h+var_898], edx
0x180012c23  lea     rdx, aHspppPacketHsA; "%hsPPP packet %hs at %0*d/%0*d/%0*d %0*"...
0x180012c2a  mov     [rsp+900h+var_8A0], eax
0x180012c2e  mov     [rsp+900h+var_8A8], r10d
0x180012c33  mov     [rsp+900h+var_8B0], eax
0x180012c37  mov     [rsp+900h+var_8B8], r11d
0x180012c3c  mov     [rsp+900h+var_8C0], eax
0x180012c40  mov     dword ptr [rsp+900h+var_8C8], ebx
0x180012c44  mov     dword ptr [rsp+900h+var_8D0], eax
0x180012c48  mov     dword ptr [rsp+900h+var_8D8], edi
0x180012c4c  mov     dword ptr [rsp+900h+var_8E0], eax
0x180012c50  call    FormatRRASErrorString
0x180012c55  mov     al, cs:byte_18004DF34
0x180012c5b  test    al, 1
0x180012c5d  jz      short loc_180012C7C
0x180012c5f  lea     r8, [rbp+7F0h+var_840]
0x180012c63  lea     rdx, RasPppTraceInfo
0x180012c6a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180012c71  call    McTemplateU0z_EventWriteTransfer
0x180012c76  mov     al, cs:byte_18004DF34
0x180012c7c  mov     edi, [rbp+7F0h+var_86C]
0x180012c7f  lea     r8, asc_18003B660; "<"
0x180012c86  mov     dl, [rbp+7F0h+var_870]
0x180012c89  test    al, 1
0x180012c8b  jz      short loc_180012CF4
0x180012c8d  xor     eax, eax
0x180012c8f  movzx   ecx, dl
0x180012c92  mov     word ptr [rbp+7F0h+var_840], ax
0x180012c96  lea     rdx, aHsprotocolHsTy; "%hsProtocol = %hs, Type = %hs, Length ="...
0x180012c9d  mov     rax, [rbp+7F0h+var_858]
0x180012ca1  test    edi, edi
0x180012ca3  mov     r9, r14
0x180012ca6  cmovz   r13, r8
0x180012caa  mov     r8, r13
0x180012cad  mov     rax, [rax+10h]
0x180012cb1  mov     [rsp+900h+var_8C8], rax
0x180012cb6  mov     dword ptr [rsp+900h+var_8D0], ecx
0x180012cba  lea     rcx, [rbp+7F0h+var_840]
0x180012cbe  mov     dword ptr [rsp+900h+var_8D8], r12d
0x180012cc3  mov     [rsp+900h+var_8E0], rsi
0x180012cc8  call    FormatRRASErrorString
0x180012ccd  mov     al, cs:byte_18004DF34
0x180012cd3  test    al, 1
0x180012cd5  jz      short loc_180012CF4
0x180012cd7  lea     r8, [rbp+7F0h+var_840]
0x180012cdb  lea     rdx, RasPppTraceInfo
0x180012ce2  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180012ce9  call    McTemplateU0z_EventWriteTransfer
0x180012cee  mov     al, cs:byte_18004DF34
0x180012cf4  cmp     [rbp+7F0h+var_864], 0
0x180012cf8  jz      short loc_180012D21
0x180012cfa  test    al, 1
0x180012cfc  jz      short loc_180012D21
0x180012cfe  mov     r9d, [rbp+7F0h+var_868]
0x180012d02  lea     r8, aPppPacketBuffe; "PPP Packet buffer"
0x180012d09  lea     rdx, RasPppTraceByteBuffer
0x180012d10  mov     [rsp+900h+var_8E0], r15
0x180012d15  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180012d1c  call    McTemplateU0zqbr1_EventWriteTransfer
0x180012d21  mov     rcx, [rbp+7F0h+var_40]
0x180012d28  xor     rcx, rsp; StackCookie
0x180012d2b  call    __security_check_cookie
0x180012d30  mov     rbx, [rsp+900h+arg_0]
0x180012d38  add     rsp, 8D0h
0x180012d3f  pop     r15
0x180012d41  pop     r14
0x180012d43  pop     r13
0x180012d45  pop     r12
0x180012d47  pop     rdi
0x180012d48  pop     rsi
0x180012d49  pop     rbp
0x180012d4a  retn
```
