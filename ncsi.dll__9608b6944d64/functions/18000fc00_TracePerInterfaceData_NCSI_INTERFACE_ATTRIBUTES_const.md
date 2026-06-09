# TracePerInterfaceData(NCSI_INTERFACE_ATTRIBUTES const &)

- ea: `0x18000fc00`
- end: `0x18001004d`
- name: `?TracePerInterfaceData@@YAXAEBVNCSI_INTERFACE_ATTRIBUTES@@@Z`
- size: `1101`
- prototype: `void __fastcall(const struct NCSI_INTERFACE_ATTRIBUTES *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18000ef10`

## callees

- `0x18000fc00`
- `0x180010200`
- `0x180010d30`
- `0x1800296b8`
- `0x180047240`
- `0x180060c98`

## import_xrefs

- `ntdll!RtlIpv4AddressToStringA` at `0x18000fed3`
- `ntdll!RtlIpv4AddressToStringA` at `0x18000ff11`
- `ntdll!RtlIpv4AddressToStringA` at `0x18000fed3`
- `ntdll!RtlIpv4AddressToStringA` at `0x18000ff11`
- `ntdll!RtlIpv6AddressToStringA` at `0x18000ff35`
- `ntdll!RtlIpv6AddressToStringA` at `0x18000ff59`
- `ntdll!RtlIpv6AddressToStringA` at `0x18000ff35`
- `ntdll!RtlIpv6AddressToStringA` at `0x18000ff59`

## string_xrefs

- `0x18000fff5`: `ssrBadPath`
- `0x180010041`: `ssrBadPath`
- `0x18000ffe9`: `ssrBadPathToProxy`
- `0x180010035`: `ssrBadPathToProxy`

## pseudocode

```c
void __fastcall TracePerInterfaceData(const struct NCSI_INTERFACE_ATTRIBUTES *a1)
{
  __int64 v1; // rbp
  const char *v3; // rdi
  __int64 v4; // rbx
  __int64 v5; // rsi
  __int64 v6; // rcx
  CHAR *v7; // r8
  const char *v8; // rdx
  __int64 v9; // r9
  CHAR *v10; // rax
  CHAR *v11; // rax
  CHAR *v12; // rcx
  int v13; // ecx
  const char *v14; // rdx
  int v15; // r10d
  const char *v16; // r11
  const char *v17; // r8
  const char *v18; // r9
  const char *v19; // rcx
  unsigned __int16 *DefaultGatewayAddress; // rax
  int v21; // r9d
  unsigned __int16 *v22; // rax
  int v23; // r9d
  int v24; // ecx
  int v25; // ecx
  int v26; // ecx
  int v27; // r10d
  int v28; // r10d
  int v29; // r10d
  CHAR v30[32]; // [rsp+80h] [rbp-E8h] BYREF
  CHAR v31[16]; // [rsp+A0h] [rbp-C8h] BYREF
  __int128 v32; // [rsp+B0h] [rbp-B8h]
  __int128 v33; // [rsp+C0h] [rbp-A8h]
  __int128 v34; // [rsp+D0h] [rbp-98h]
  __int16 v35; // [rsp+E0h] [rbp-88h]
  CHAR S[16]; // [rsp+F0h] [rbp-78h] BYREF
  __int128 v37; // [rsp+100h] [rbp-68h]
  __int128 v38; // [rsp+110h] [rbp-58h]
  __int128 v39; // [rsp+120h] [rbp-48h]
  __int16 v40; // [rsp+130h] [rbp-38h]

  v1 = WPP_GLOBAL_Control;
  if ( *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 5u )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x40) != 0 )
    {
      WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 25, WPP_908899ae445231599b715923bce5511e_Traceguids);
      v1 = WPP_GLOBAL_Control;
    }
    v3 = "<none>";
    v4 = 2147483646;
    v40 = 0;
    v5 = 66;
    v35 = 0;
    *(_OWORD *)S = 0;
    v37 = 0;
    v38 = 0;
    v39 = 0;
    *(_OWORD *)v31 = 0;
    v32 = 0;
    v33 = 0;
    v34 = 0;
    if ( *((_WORD *)a1 + 2180) )
    {
      DefaultGatewayAddress = (unsigned __int16 *)NCSI_INTERFACE_ATTRIBUTES::GetDefaultGatewayAddress(a1, v30, 0);
      v21 = *DefaultGatewayAddress;
      if ( v21 == 2 )
      {
        RtlIpv4AddressToStringA((const struct in_addr *)DefaultGatewayAddress + 1, S);
        v1 = WPP_GLOBAL_Control;
      }
      else
      {
        if ( v21 == 23 )
          RtlIpv6AddressToStringA((const struct in6_addr *)(DefaultGatewayAddress + 4), S);
        else
          StringCchPrintfA(S, 0x41u, "Unknown family %d.", v21);
        v1 = WPP_GLOBAL_Control;
      }
    }
    else
    {
      v6 = 2147483646;
      v7 = S;
      v8 = "<none>";
      v9 = 66;
      do
      {
        if ( !v6 )
          break;
        if ( !*v8 )
          break;
        *v7++ = *v8++;
        --v6;
        --v9;
      }
      while ( v9 );
      v10 = v7 - 1;
      if ( v9 )
        v10 = v7;
      *v10 = 0;
    }
    if ( *((_WORD *)a1 + 4152) )
    {
      v22 = (unsigned __int16 *)NCSI_INTERFACE_ATTRIBUTES::GetDefaultGatewayAddress(a1, v30, 1);
      v23 = *v22;
      if ( v23 == 2 )
      {
        RtlIpv4AddressToStringA((const struct in_addr *)v22 + 1, v31);
        v1 = WPP_GLOBAL_Control;
      }
      else
      {
        if ( v23 == 23 )
          RtlIpv6AddressToStringA((const struct in6_addr *)(v22 + 4), v31);
        else
          StringCchPrintfA(v31, 0x41u, "Unknown family %d.", v23);
        v1 = WPP_GLOBAL_Control;
      }
    }
    else
    {
      v11 = v31;
      do
      {
        if ( !v4 )
          break;
        if ( !*v3 )
          break;
        *v11++ = *v3++;
        --v4;
        --v5;
      }
      while ( v5 );
      v12 = v11 - 1;
      if ( v5 )
        v12 = v11;
      *v12 = 0;
    }
    if ( (_UNKNOWN *)v1 != &WPP_GLOBAL_Control && (*(_BYTE *)(v1 + 28) & 0x40) != 0 && *(_BYTE *)(v1 + 25) >= 5u )
    {
      v13 = *((_DWORD *)a1 + 2108);
      v14 = "UNKNOWN";
      v15 = *((_DWORD *)a1 + 1122);
      if ( v13 )
      {
        v24 = v13 - 1;
        if ( v24 )
        {
          v25 = v24 - 1;
          if ( v25 )
          {
            v26 = v25 - 1;
            if ( v26 )
            {
              if ( v26 == 1 )
                v16 = "ssrDnsAllServerTimeout";
              else
                v16 = "UNKNOWN";
            }
            else
            {
              v16 = "ssrTeredoDown";
            }
          }
          else
          {
            v16 = "ssrBadPathToProxy";
          }
        }
        else
        {
          v16 = "ssrBadPath";
        }
      }
      else
      {
        v16 = "no";
      }
      v17 = " ";
      v18 = " ";
      if ( !*((_BYTE *)a1 + 8297) )
        v18 = " <NO IP> ";
      if ( v15 )
      {
        v27 = v15 - 1;
        if ( v27 )
        {
          v28 = v27 - 1;
          if ( v28 )
          {
            v29 = v28 - 1;
            if ( v29 )
            {
              if ( v29 == 1 )
                v14 = "ssrDnsAllServerTimeout";
            }
            else
            {
              v14 = "ssrTeredoDown";
            }
          }
          else
          {
            v14 = "ssrBadPathToProxy";
          }
        }
        else
        {
          v14 = "ssrBadPath";
        }
      }
      else
      {
        v14 = "no";
      }
      if ( !*((_BYTE *)a1 + 4353) )
        v17 = " <NO IP> ";
      v19 = " DISCONNECTED ";
      if ( !*((_DWORD *)a1 + 6) )
        v19 = " CONNECTED";
      WPP_SF_issdssdsdssd(
        *(_QWORD *)(v1 + 16),
        (_DWORD)v14,
        (_DWORD)v17,
        *(_QWORD *)a1,
        (__int64)v19,
        (__int64)v17,
        *((_DWORD *)a1 + 1106),
        (__int64)S,
        (__int64)v14,
        *((_DWORD *)a1 + 1107),
        (__int64)v18,
        *((_DWORD *)a1 + 2092),
        (__int64)v31,
        (__int64)v16,
        *((_DWORD *)a1 + 2093));
    }
  }
}

```

## disassembly

```asm
0x18000fc00  mov     r11, rsp
0x18000fc03  push    rbp
0x18000fc04  push    r14
0x18000fc06  sub     rsp, 158h
0x18000fc0d  mov     rax, cs:__security_cookie
0x18000fc14  xor     rax, rsp
0x18000fc17  mov     [rsp+168h+var_28], rax
0x18000fc1f  mov     rbp, cs:WPP_GLOBAL_Control
0x18000fc26  mov     r14, rcx
0x18000fc29  cmp     byte ptr [rbp+19h], 5
0x18000fc2d  jb      loc_18000FD74
0x18000fc33  mov     [r11+10h], rbx
0x18000fc37  mov     [r11+18h], rsi
0x18000fc3b  mov     [r11+20h], rdi
0x18000fc3f  mov     [r11-18h], r15
0x18000fc43  lea     r15, WPP_GLOBAL_Control
0x18000fc4a  cmp     rbp, r15
0x18000fc4d  jnz     loc_18000FE7F
0x18000fc53  xorps   xmm0, xmm0
0x18000fc56  lea     rdi, aNone; "<none>"
0x18000fc5d  xorps   xmm1, xmm1
0x18000fc60  xor     eax, eax
0x18000fc62  mov     ebx, 7FFFFFFEh
0x18000fc67  mov     [rsp+168h+var_38], ax
0x18000fc6f  mov     esi, 42h ; 'B'
0x18000fc74  mov     [rsp+168h+var_88], ax
0x18000fc7c  movups  xmmword ptr [rsp+168h+S], xmm0
0x18000fc84  movups  [rsp+168h+var_68], xmm0
0x18000fc8c  movups  [rsp+168h+var_58], xmm0
0x18000fc94  movups  [rsp+168h+var_48], xmm0
0x18000fc9c  movups  xmmword ptr [rsp+168h+var_C8], xmm1
0x18000fca4  movups  [rsp+168h+var_B8], xmm1
0x18000fcac  movups  [rsp+168h+var_A8], xmm1
0x18000fcb4  movups  [rsp+168h+var_98], xmm1
0x18000fcbc  cmp     ax, [r14+1108h]
0x18000fcc4  jnz     loc_18000FEAA
0x18000fcca  mov     ecx, ebx
0x18000fccc  lea     r8, [rsp+168h+S]
0x18000fcd4  mov     rdx, rdi
0x18000fcd7  mov     r9d, esi
0x18000fcda  nop     word ptr [rax+rax+00h]
0x18000fce0  test    rcx, rcx
0x18000fce3  jz      short loc_18000FCFE
0x18000fce5  movzx   eax, byte ptr [rdx]
0x18000fce8  test    al, al
0x18000fcea  jz      short loc_18000FCFE
0x18000fcec  mov     [r8], al
0x18000fcef  inc     rdx
0x18000fcf2  inc     r8
0x18000fcf5  dec     rcx
0x18000fcf8  sub     r9, 1
0x18000fcfc  jnz     short loc_18000FCE0
0x18000fcfe  test    r9, r9
0x18000fd01  lea     rax, [r8-1]
0x18000fd05  cmovnz  rax, r8
0x18000fd09  mov     byte ptr [rax], 0
0x18000fd0c  xor     eax, eax
0x18000fd0e  cmp     ax, [r14+2070h]
0x18000fd16  jnz     loc_18000FEE5
0x18000fd1c  lea     rax, [rsp+168h+var_C8]
0x18000fd24  test    rbx, rbx
0x18000fd27  jz      short loc_18000FD41
0x18000fd29  movzx   ecx, byte ptr [rdi]
0x18000fd2c  test    cl, cl
0x18000fd2e  jz      short loc_18000FD41
0x18000fd30  mov     [rax], cl
0x18000fd32  inc     rdi
0x18000fd35  inc     rax
0x18000fd38  dec     rbx
0x18000fd3b  sub     rsi, 1
0x18000fd3f  jnz     short loc_18000FD24
0x18000fd41  test    rsi, rsi
0x18000fd44  lea     rcx, [rax-1]
0x18000fd48  cmovnz  rcx, rax
0x18000fd4c  mov     byte ptr [rcx], 0
0x18000fd4f  cmp     rbp, r15
0x18000fd52  mov     r15, [rsp+168h+var_18]
0x18000fd5a  jnz     short loc_18000FD8F
0x18000fd5c  mov     rsi, [rsp+168h+arg_10]
0x18000fd64  mov     rbx, [rsp+168h+arg_8]
0x18000fd6c  mov     rdi, [rsp+168h+arg_18]
0x18000fd74  mov     rcx, [rsp+168h+var_28]
0x18000fd7c  xor     rcx, rsp; StackCookie
0x18000fd7f  call    __security_check_cookie
0x18000fd84  add     rsp, 158h
0x18000fd8b  pop     r14
0x18000fd8d  pop     rbp
0x18000fd8e  retn
0x18000fd8f  test    byte ptr [rbp+1Ch], 40h
0x18000fd93  jz      short loc_18000FD5C
0x18000fd95  cmp     byte ptr [rbp+19h], 5
0x18000fd99  jb      short loc_18000FD5C
0x18000fd9b  mov     ecx, [r14+20F0h]
0x18000fda2  lea     rdx, aUnknown; "UNKNOWN"
0x18000fda9  mov     r10d, [r14+1188h]
0x18000fdb0  mov     ebx, [r14+20B4h]
0x18000fdb7  test    ecx, ecx
0x18000fdb9  jnz     loc_18000FFB5
0x18000fdbf  lea     r11, aNo; "no"
0x18000fdc6  cmp     byte ptr [r14+2069h], 0
0x18000fdce  lea     r8, asc_18007F250; " "
0x18000fdd5  mov     edi, [r14+20B0h]
0x18000fddc  lea     rcx, aNoIp; " <NO IP> "
0x18000fde3  mov     esi, [r14+114Ch]
0x18000fdea  mov     r9, r8
0x18000fded  cmovz   r9, rcx
0x18000fdf1  test    r10d, r10d
0x18000fdf4  jnz     loc_180010001
0x18000fdfa  lea     rdx, aNo; "no"
0x18000fe01  cmp     byte ptr [r14+1101h], 0
0x18000fe09  lea     rax, aConnected; " CONNECTED"
0x18000fe10  mov     [rsp+168h+var_F8], ebx
0x18000fe14  mov     [rsp+168h+var_100], r11
0x18000fe19  cmovz   r8, rcx
0x18000fe1d  cmp     dword ptr [r14+18h], 0
0x18000fe22  lea     rcx, aDisconnected; " DISCONNECTED "
0x18000fe29  cmovz   rcx, rax
0x18000fe2d  lea     rax, [rsp+168h+var_C8]
0x18000fe35  mov     [rsp+168h+var_108], rax
0x18000fe3a  lea     rax, [rsp+168h+S]
0x18000fe42  mov     [rsp+168h+var_110], edi
0x18000fe46  mov     [rsp+168h+var_118], r9
0x18000fe4b  mov     r9, [r14]
0x18000fe4e  mov     [rsp+168h+var_120], esi
0x18000fe52  mov     [rsp+168h+var_128], rdx
0x18000fe57  mov     [rsp+168h+var_130], rax
0x18000fe5c  mov     eax, [r14+1148h]
0x18000fe63  mov     [rsp+168h+var_138], eax
0x18000fe67  mov     [rsp+168h+var_140], r8
0x18000fe6c  mov     [rsp+168h+var_148], rcx
0x18000fe71  mov     rcx, [rbp+10h]
0x18000fe75  call    WPP_SF_issdssdsdssd
0x18000fe7a  jmp     loc_18000FD5C
0x18000fe7f  test    byte ptr [rbp+1Ch], 40h
0x18000fe83  jz      loc_18000FC53
0x18000fe89  mov     rcx, [rbp+10h]
0x18000fe8d  lea     r8, WPP_908899ae445231599b715923bce5511e_Traceguids
0x18000fe94  mov     edx, 19h
0x18000fe99  call    WPP_SF_
0x18000fe9e  mov     rbp, cs:WPP_GLOBAL_Control
0x18000fea5  jmp     loc_18000FC53
0x18000feaa  xor     r8d, r8d
0x18000fead  lea     rdx, [rsp+168h+var_E8]
0x18000feb5  mov     rcx, r14
0x18000feb8  call    ?GetDefaultGatewayAddress@NCSI_INTERFACE_ATTRIBUTES@@QEBA?AT_SOCKADDR_INET@@W4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::GetDefaultGatewayAddress(_NLA_CONNECTIVITY_FAMILY)
0x18000febd  movzx   r9d, word ptr [rax]
0x18000fec1  cmp     r9d, 2
0x18000fec5  jnz     short loc_18000FF23
0x18000fec7  lea     rcx, [rax+4]; Addr
0x18000fecb  lea     rdx, [rsp+168h+S]; S
0x18000fed3  call    cs:__imp_RtlIpv4AddressToStringA
0x18000fed9  mov     rbp, cs:WPP_GLOBAL_Control
0x18000fee0  jmp     loc_18000FD0C
0x18000fee5  mov     r8d, 1
0x18000feeb  lea     rdx, [rsp+168h+var_E8]
0x18000fef3  mov     rcx, r14
0x18000fef6  call    ?GetDefaultGatewayAddress@NCSI_INTERFACE_ATTRIBUTES@@QEBA?AT_SOCKADDR_INET@@W4_NLA_CONNECTIVITY_FAMILY@@@Z; NCSI_INTERFACE_ATTRIBUTES::GetDefaultGatewayAddress(_NLA_CONNECTIVITY_FAMILY)
0x18000fefb  movzx   r9d, word ptr [rax]
0x18000feff  cmp     r9d, 2
0x18000ff03  jnz     short loc_18000FF47
0x18000ff05  lea     rcx, [rax+4]; Addr
0x18000ff09  lea     rdx, [rsp+168h+var_C8]; S
0x18000ff11  call    cs:__imp_RtlIpv4AddressToStringA
0x18000ff17  mov     rbp, cs:WPP_GLOBAL_Control
0x18000ff1e  jmp     loc_18000FD4F
0x18000ff23  cmp     r9d, 17h
0x18000ff27  jnz     short loc_18000FF6B
0x18000ff29  lea     rcx, [rax+8]; Addr
0x18000ff2d  lea     rdx, [rsp+168h+S]; S
0x18000ff35  call    cs:__imp_RtlIpv6AddressToStringA
0x18000ff3b  mov     rbp, cs:WPP_GLOBAL_Control
0x18000ff42  jmp     loc_18000FD0C
0x18000ff47  cmp     r9d, 17h
0x18000ff4b  jnz     short loc_18000FF90
0x18000ff4d  lea     rcx, [rax+8]; Addr
0x18000ff51  lea     rdx, [rsp+168h+var_C8]; S
0x18000ff59  call    cs:__imp_RtlIpv6AddressToStringA
0x18000ff5f  mov     rbp, cs:WPP_GLOBAL_Control
0x18000ff66  jmp     loc_18000FD4F
0x18000ff6b  lea     r8, aUnknownFamilyD; "Unknown family %d."
0x18000ff72  mov     edx, 41h ; 'A'; unsigned __int64
0x18000ff77  lea     rcx, [rsp+168h+S]; char *
0x18000ff7f  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000ff84  mov     rbp, cs:WPP_GLOBAL_Control
0x18000ff8b  jmp     loc_18000FD0C
0x18000ff90  lea     r8, aUnknownFamilyD; "Unknown family %d."
0x18000ff97  mov     edx, 41h ; 'A'; unsigned __int64
0x18000ff9c  lea     rcx, [rsp+168h+var_C8]; char *
0x18000ffa4  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x18000ffa9  mov     rbp, cs:WPP_GLOBAL_Control
0x18000ffb0  jmp     loc_18000FD4F
0x18000ffb5  sub     ecx, 1
0x18000ffb8  jz      short loc_18000FFF5
0x18000ffba  sub     ecx, 1
0x18000ffbd  jz      short loc_18000FFE9
0x18000ffbf  sub     ecx, 1
0x18000ffc2  jz      short loc_18000FFDD
0x18000ffc4  cmp     ecx, 1
0x18000ffc7  jz      short loc_18000FFD1
0x18000ffc9  mov     r11, rdx
0x18000ffcc  jmp     loc_18000FDC6
0x18000ffd1  lea     r11, aSsrdnsallserve; "ssrDnsAllServerTimeout"
0x18000ffd8  jmp     loc_18000FDC6
0x18000ffdd  lea     r11, aSsrteredodown; "ssrTeredoDown"
0x18000ffe4  jmp     loc_18000FDC6
0x18000ffe9  lea     r11, aSsrbadpathtopr; "ssrBadPathToProxy"
0x18000fff0  jmp     loc_18000FDC6
0x18000fff5  lea     r11, aSsrbadpath; "ssrBadPath"
0x18000fffc  jmp     loc_18000FDC6
0x180010001  sub     r10d, 1
0x180010005  jz      short loc_180010041
0x180010007  sub     r10d, 1
0x18001000b  jz      short loc_180010035
0x18001000d  sub     r10d, 1
0x180010011  jz      short loc_180010029
0x180010013  cmp     r10d, 1
0x180010017  jnz     loc_18000FE01
0x18001001d  lea     rdx, aSsrdnsallserve; "ssrDnsAllServerTimeout"
0x180010024  jmp     loc_18000FE01
0x180010029  lea     rdx, aSsrteredodown; "ssrTeredoDown"
0x180010030  jmp     loc_18000FE01
0x180010035  lea     rdx, aSsrbadpathtopr; "ssrBadPathToProxy"
0x18001003c  jmp     loc_18000FE01
0x180010041  lea     rdx, aSsrbadpath; "ssrBadPath"
0x180010048  jmp     loc_18000FE01
```
