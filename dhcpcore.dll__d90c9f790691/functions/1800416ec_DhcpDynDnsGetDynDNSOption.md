# DhcpDynDnsGetDynDNSOption

- ea: `0x1800416ec`
- end: `0x180041a1e`
- name: `DhcpDynDnsGetDynDNSOption`
- size: `818`
- prototype: `DWORD __fastcall(__int64, unsigned int *, __int64, __int64, const CHAR *, int cbMultiByte)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180034bcc`
- `0x18003f420`

## callees

- `0x180005670`
- `0x180018fbc`
- `0x180019620`
- `0x18001cef0`
- `0x18001d826`
- `0x1800416ec`
- `0x180041a24`
- `0x1800466c8`
- `0x18004c33c`

## import_xrefs

- `ntdll!RtlUnicodeStringToOemString` at `0x1800419d8`
- `ntdll!RtlUnicodeStringToOemString` at `0x1800419d8`
- `ntdll!RtlInitUnicodeString` at `0x180041969`
- `ntdll!RtlInitUnicodeString` at `0x180041969`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800419a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800419a9`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18004199f`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x18004199f`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180041812`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180041812`
- `DNSAPI!DnsQueryConfigDword` at `0x1800417c1`
- `DNSAPI!DnsQueryConfigDword` at `0x1800417c1`

## pseudocode

```c
DWORD __fastcall DhcpDynDnsGetDynDNSOption(
        __int64 a1,
        unsigned int *a2,
        __int64 a3,
        __int64 a4,
        const CHAR *a5,
        int cbMultiByte)
{
  unsigned int v6; // r12d
  DWORD result; // eax
  int v10; // r9d
  int v11; // ecx
  int v12; // edx
  __int64 v13; // r13
  bool v14; // al
  NTSTATUS v15; // ebx
  DWORD v16; // r14d
  unsigned int v17; // eax
  unsigned int v18; // r12d
  CHAR *v19; // rsi
  WCHAR *v20; // r15
  DWORD v21; // eax
  DWORD v22; // ebx
  int Length; // eax
  DWORD nSize; // [rsp+40h] [rbp-C0h] BYREF
  int v25; // [rsp+44h] [rbp-BCh] BYREF
  int v26; // [rsp+48h] [rbp-B8h] BYREF
  int v27; // [rsp+4Ch] [rbp-B4h] BYREF
  struct _STRING v28; // [rsp+50h] [rbp-B0h] BYREF
  int v29; // [rsp+60h] [rbp-A0h]
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-98h] BYREF
  LPCCH lpMultiByteStr; // [rsp+78h] [rbp-88h]
  WCHAR Buffer[264]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v33[912]; // [rsp+290h] [rbp+190h] BYREF

  v6 = *a2;
  lpMultiByteStr = a5;
  nSize = 0;
  v27 = 0;
  v26 = 0;
  DestinationString = 0;
  if ( v6 < 4 )
    return 122;
  v10 = *(_DWORD *)(a3 + 148);
  v11 = DhcpGlobalUseMHAsyncDns;
  v12 = *(_DWORD *)(a3 + 152);
  v13 = *(_QWORD *)(a3 + 56);
  *(_QWORD *)&v28.Length = *(_QWORD *)(a3 + 728);
  v14 = DhcpGlobalUseMHAsyncDns == 0;
  *(_BYTE *)a1 = DhcpGlobalUseMHAsyncDns == 0;
  v29 = v10;
  v25 = v12;
  if ( v10 || v12 )
    *(_BYTE *)a1 = v14 | 4;
  if ( *(_DWORD *)(a3 + 816) )
    *(_BYTE *)a1 |= 8u;
  *(_WORD *)(a1 + 1) = 0;
  *a2 = 3;
  if ( !(unsigned int)DnsQueryConfigDword(65552, v13 & -(__int64)(v11 != 0)) )
  {
    v15 = 1003;
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_DS(1028, 11, (unsigned int)WPP_f2ae1866e2793df1a38d81436db84831_Traceguids, 1003, v13);
    return v15;
  }
  nSize = 257;
  result = GetComputerNameExW(ComputerNameDnsHostname, Buffer, &nSize);
  if ( !result )
    return result;
  v16 = nSize;
  v17 = WxStringCchLengthDWordW(Buffer, 0x7FFFFFFF, &v26);
  v15 = WX_WIN32_FROM_HR(v17);
  if ( !v15 )
  {
    v18 = v6 - 3;
    v19 = (CHAR *)(a1 + 3);
    v20 = &Buffer[v26 + 1];
    nSize = 255 - v26;
    if ( (unsigned int)DhcpDynDnsGetDynDNSOptionDomain(v20, lpMultiByteStr, cbMultiByte, v25) || (v21 = nSize) == 0 )
    {
      v22 = 0;
      *(v20 - 1) = 0;
    }
    else
    {
      *(v20 - 1) = 46;
      v22 = v21 >> 1;
      v20[(unsigned __int64)v21 >> 1] = 0;
    }
    if ( v25 )
    {
      memset_0(v33, 0, 0x384u);
      v25 = 900;
      *(_QWORD *)&v28.Length = v33;
      if ( v22 )
        v16 += v22 + 1;
      v15 = ConvertUnicodeToPunycode(Buffer, v16, &v28, &v25);
      if ( v15 )
        return v15;
      if ( DhcpGetWireFormatNameFromPunycode(v19, &v19[v18], v33, &v27) )
      {
        Length = v27;
LABEL_31:
        *a2 += Length;
        return v15;
      }
      return 1359;
    }
    else
    {
      Buffer[256] = 0;
      RtlInitUnicodeString(&DestinationString, Buffer);
      if ( v29 )
      {
        Length = WideCharToMultiByte(
                   0xFDE9u,
                   0,
                   DestinationString.Buffer,
                   DestinationString.Length >> 1,
                   v19,
                   v18,
                   0,
                   0);
        if ( Length )
        {
          v15 = 0;
          goto LABEL_31;
        }
        return GetLastError();
      }
      else
      {
        *(_QWORD *)&v28.Length = 0;
        v28.Buffer = v19;
        v28.MaximumLength = v18;
        v15 = RtlUnicodeStringToOemString(&v28, &DestinationString, 0);
        if ( v15 >= 0 )
        {
          Length = v28.Length;
          goto LABEL_31;
        }
        return 13;
      }
    }
  }
  return v15;
}

```

## disassembly

```asm
0x1800416ec  mov     [rsp-8+arg_18], rbx
0x1800416f1  push    rbp
0x1800416f2  push    rsi
0x1800416f3  push    rdi
0x1800416f4  push    r12
0x1800416f6  push    r13
0x1800416f8  push    r14
0x1800416fa  push    r15
0x1800416fc  lea     rbp, [rsp-530h]
0x180041704  sub     rsp, 630h
0x18004170b  mov     rax, cs:__security_cookie
0x180041712  xor     rax, rsp
0x180041715  mov     [rbp+560h+var_40], rax
0x18004171c  mov     rax, [rbp+560h+arg_20]
0x180041723  xor     r15d, r15d
0x180041726  mov     r12d, [rdx]
0x180041729  xorps   xmm0, xmm0
0x18004172c  mov     [rsp+660h+var_5E8], rax
0x180041731  mov     rdi, rdx
0x180041734  mov     [rsp+660h+nSize], r15d
0x180041739  mov     rsi, rcx
0x18004173c  mov     [rsp+660h+var_614], r15d
0x180041741  mov     [rsp+660h+var_618], r15d
0x180041746  movups  xmmword ptr [rsp+660h+DestinationString.Length], xmm0
0x18004174b  cmp     r12d, 4
0x18004174f  jnb     short loc_18004175A
0x180041751  lea     eax, [r15+7Ah]
0x180041755  jmp     loc_1800419F4
0x18004175a  mov     rax, [r8+2D8h]
0x180041761  mov     r9d, [r8+94h]
0x180041768  mov     ecx, cs:DhcpGlobalUseMHAsyncDns
0x18004176e  test    ecx, ecx
0x180041770  mov     edx, [r8+98h]
0x180041777  mov     r13, [r8+38h]
0x18004177b  mov     qword ptr [rsp+660h+var_610.Length], rax
0x180041780  setz    al
0x180041783  mov     [rsi], al
0x180041785  mov     [rsp+660h+var_600], r9d
0x18004178a  mov     [rsp+660h+var_61C], edx
0x18004178e  test    r9d, r9d
0x180041791  jnz     short loc_180041797
0x180041793  test    edx, edx
0x180041795  jz      short loc_18004179B
0x180041797  or      al, 4
0x180041799  mov     [rsi], al
0x18004179b  mov     eax, [r8+330h]
0x1800417a2  test    eax, eax
0x1800417a4  jz      short loc_1800417A9
0x1800417a6  or      byte ptr [rsi], 8
0x1800417a9  neg     ecx
0x1800417ab  mov     [rsi+1], r15w
0x1800417b0  mov     ecx, 10010h
0x1800417b5  mov     dword ptr [rdi], 3
0x1800417bb  sbb     rdx, rdx
0x1800417be  and     rdx, r13
0x1800417c1  call    cs:__imp_DnsQueryConfigDword
0x1800417c7  test    eax, eax
0x1800417c9  jnz     short loc_1800417FC
0x1800417cb  test    byte ptr cs:xmmword_1800616A0, 10h
0x1800417d2  mov     ebx, 3EBh
0x1800417d7  jz      loc_1800419F2
0x1800417dd  lea     edx, [rax+0Bh]
0x1800417e0  mov     [rsp+660h+lpMultiByteStr], r13
0x1800417e5  lea     ecx, [rbx+19h]
0x1800417e8  mov     r9d, ebx
0x1800417eb  lea     r8, WPP_f2ae1866e2793df1a38d81436db84831_Traceguids
0x1800417f2  call    WPP_SF_DS
0x1800417f7  jmp     loc_1800419F2
0x1800417fc  lea     r8, [rsp+660h+nSize]; nSize
0x180041801  mov     [rsp+660h+nSize], 101h
0x180041809  lea     rdx, [rbp+560h+Buffer]; lpBuffer
0x18004180d  mov     ecx, 1; NameType
0x180041812  call    cs:__imp_GetComputerNameExW
0x180041818  test    eax, eax
0x18004181a  jz      loc_1800419F4
0x180041820  mov     r14d, [rsp+660h+nSize]
0x180041825  lea     r8, [rsp+660h+var_618]
0x18004182a  mov     edx, 7FFFFFFFh
0x18004182f  lea     rcx, [rbp+560h+Buffer]
0x180041833  call    WxStringCchLengthDWordW
0x180041838  mov     ecx, eax
0x18004183a  call    WX_WIN32_FROM_HR
0x18004183f  mov     ebx, eax
0x180041841  test    eax, eax
0x180041843  jnz     loc_1800419F2
0x180041849  mov     eax, [rsp+660h+var_618]
0x18004184d  lea     r15, [rbp+560h+var_5DE]
0x180041851  mov     r8, qword ptr [rsp+660h+var_610.Length]
0x180041856  lea     rdx, [rsp+660h+nSize]
0x18004185b  mov     r9, r13
0x18004185e  add     r12d, 0FFFFFFFDh
0x180041862  add     rsi, 3
0x180041866  lea     r15, [r15+rax*2]
0x18004186a  mov     eax, 0FFh
0x18004186f  sub     eax, [rsp+660h+var_618]
0x180041873  mov     rcx, r15; void *
0x180041876  mov     [rsp+660h+nSize], eax
0x18004187a  mov     eax, [rsp+660h+var_61C]
0x18004187e  mov     dword ptr [rsp+660h+lpDefaultChar], eax; int
0x180041882  mov     eax, [rbp+560h+arg_28]
0x180041888  mov     [rsp+660h+cbMultiByte], eax; cbMultiByte
0x18004188c  mov     rax, [rsp+660h+var_5E8]
0x180041891  mov     [rsp+660h+lpMultiByteStr], rax; lpMultiByteStr
0x180041896  call    DhcpDynDnsGetDynDNSOptionDomain
0x18004189b  xor     r13d, r13d
0x18004189e  test    eax, eax
0x1800418a0  jnz     short loc_1800418C1
0x1800418a2  mov     eax, [rsp+660h+nSize]
0x1800418a6  test    eax, eax
0x1800418a8  jz      short loc_1800418C1
0x1800418aa  mov     ebx, eax
0x1800418ac  mov     word ptr [r15-2], 2Eh ; '.'
0x1800418b3  shr     ebx, 1
0x1800418b5  mov     ecx, eax
0x1800418b7  shr     rcx, 1
0x1800418ba  mov     [r15+rcx*2], r13w
0x1800418bf  jmp     short loc_1800418C9
0x1800418c1  mov     ebx, r13d
0x1800418c4  mov     [r15-2], r13w
0x1800418c9  cmp     [rsp+660h+var_61C], r13d
0x1800418ce  jz      loc_180041958
0x1800418d4  mov     r15d, 384h
0x1800418da  lea     rcx, [rbp+560h+var_3D0]; void *
0x1800418e1  mov     r8d, r15d; Size
0x1800418e4  xor     edx, edx; Val
0x1800418e6  call    memset_0
0x1800418eb  mov     [rsp+660h+var_61C], r15d
0x1800418f0  lea     rax, [rbp+560h+var_3D0]
0x1800418f7  mov     qword ptr [rsp+660h+var_610.Length], rax
0x1800418fc  test    ebx, ebx
0x1800418fe  jz      short loc_180041906
0x180041900  inc     r14d
0x180041903  add     r14d, ebx
0x180041906  lea     r9, [rsp+660h+var_61C]
0x18004190b  mov     edx, r14d
0x18004190e  lea     r8, [rsp+660h+var_610]
0x180041913  lea     rcx, [rbp+560h+Buffer]
0x180041917  call    ConvertUnicodeToPunycode
0x18004191c  mov     ebx, eax
0x18004191e  test    eax, eax
0x180041920  jnz     loc_1800419F2
0x180041926  mov     edx, r12d
0x180041929  lea     r9, [rsp+660h+var_614]
0x18004192e  add     rdx, rsi
0x180041931  lea     r8, [rbp+560h+var_3D0]
0x180041938  mov     rcx, rsi
0x18004193b  call    DhcpGetWireFormatNameFromPunycode
0x180041940  test    rax, rax
0x180041943  jz      short loc_18004194E
0x180041945  mov     eax, [rsp+660h+var_614]
0x180041949  jmp     loc_1800419F0
0x18004194e  mov     ebx, 54Fh
0x180041953  jmp     loc_1800419F2
0x180041958  lea     rdx, [rbp+560h+Buffer]; SourceString
0x18004195c  mov     [rbp+560h+var_3E0], r13w
0x180041964  lea     rcx, [rsp+660h+DestinationString]; DestinationString
0x180041969  call    cs:__imp_RtlInitUnicodeString
0x18004196f  cmp     [rsp+660h+var_600], r13d
0x180041974  jz      short loc_1800419B8
0x180041976  movzx   r9d, [rsp+660h+DestinationString.Length]
0x18004197c  xor     edx, edx; dwFlags
0x18004197e  mov     r8, [rsp+660h+DestinationString.Buffer]; lpWideCharStr
0x180041983  mov     ecx, 0FDE9h; CodePage
0x180041988  mov     [rsp+660h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x18004198d  mov     [rsp+660h+lpDefaultChar], r13; lpDefaultChar
0x180041992  shr     r9d, 1; cchWideChar
0x180041995  mov     [rsp+660h+cbMultiByte], r12d; cbMultiByte
0x18004199a  mov     [rsp+660h+lpMultiByteStr], rsi; lpMultiByteStr
0x18004199f  call    cs:__imp_WideCharToMultiByte
0x1800419a5  test    eax, eax
0x1800419a7  jnz     short loc_1800419B3
0x1800419a9  call    cs:__imp_GetLastError
0x1800419af  mov     ebx, eax
0x1800419b1  jmp     short loc_1800419F2
0x1800419b3  mov     ebx, r13d
0x1800419b6  jmp     short loc_1800419F0
0x1800419b8  xorps   xmm0, xmm0
0x1800419bb  lea     rdx, [rsp+660h+DestinationString]; SourceString
0x1800419c0  movups  xmmword ptr [rsp+660h+var_610.Length], xmm0
0x1800419c5  xor     r8d, r8d; AllocateDestinationString
0x1800419c8  mov     [rsp+660h+var_610.Buffer], rsi
0x1800419cd  lea     rcx, [rsp+660h+var_610]; DestinationString
0x1800419d2  mov     [rsp+660h+var_610.MaximumLength], r12w
0x1800419d8  call    cs:__imp_RtlUnicodeStringToOemString
0x1800419de  mov     ebx, eax
0x1800419e0  test    eax, eax
0x1800419e2  jns     short loc_1800419EB
0x1800419e4  mov     ebx, 0Dh
0x1800419e9  jmp     short loc_1800419F2
0x1800419eb  movzx   eax, [rsp+660h+var_610.Length]
0x1800419f0  add     [rdi], eax
0x1800419f2  mov     eax, ebx
0x1800419f4  mov     rcx, [rbp+560h+var_40]
0x1800419fb  xor     rcx, rsp; StackCookie
0x1800419fe  call    __security_check_cookie
0x180041a03  mov     rbx, [rsp+660h+arg_18]
0x180041a0b  add     rsp, 630h
0x180041a12  pop     r15
0x180041a14  pop     r14
0x180041a16  pop     r13
0x180041a18  pop     r12
0x180041a1a  pop     rdi
0x180041a1b  pop     rsi
0x180041a1c  pop     rbp
0x180041a1d  retn
```
