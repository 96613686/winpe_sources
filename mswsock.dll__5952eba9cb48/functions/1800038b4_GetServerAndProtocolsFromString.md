# GetServerAndProtocolsFromString

- ea: `0x1800038b4`
- end: `0x180003b0a`
- name: `GetServerAndProtocolsFromString`
- size: `598`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180002d00`
- `0x18001f4e0`

## callees

- `0x1800018b0`
- `0x180001998`
- `0x180001f84`
- `0x1800038b4`
- `0x180037195`
- `0x180038104`
- `0x18003847c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180003a32`
- `api-ms-win-crt-private-l1-1-0!_o__stricmp` at `0x180003a32`
- `api-ms-win-crt-private-l1-1-0!_o_atoi` at `0x180003af6`
- `api-ms-win-crt-private-l1-1-0!_o_atoi` at `0x180003af6`
- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x1800039cb`
- `api-ms-win-crt-private-l1-1-0!_o_isdigit` at `0x1800039cb`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000393f`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180003ad5`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x18000393f`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x180003ad5`
- `DNSAPI!DnsApiFree` at `0x1800039aa`
- `DNSAPI!DnsApiFree` at `0x180003a16`
- `DNSAPI!DnsApiFree` at `0x180003a61`
- `DNSAPI!DnsApiFree` at `0x1800039aa`
- `DNSAPI!DnsApiFree` at `0x180003a16`
- `DNSAPI!DnsApiFree` at `0x180003a61`
- `DNSAPI!DnsApiAlloc` at `0x18000396b`
- `DNSAPI!DnsApiAlloc` at `0x18000396b`

## pseudocode

```c
__int64 __fastcall GetServerAndProtocolsFromString(const wchar_t *Src, _QWORD *a2, __int64 *a3)
{
  __int64 v4; // r14
  __int64 v8; // rax
  wchar_t *v9; // rdi
  __int64 v10; // rbx
  __int64 v11; // rcx
  char *v12; // r15
  size_t v13; // rbx
  const char *AnsiNameRnR; // rsi
  char v15; // al
  const char *v16; // rbx
  __int64 v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rax

  v4 = 0;
  if ( (xmmword_180063D60 & 2) != 0 )
  {
    WPP_SF_(1025, 17, WPP_32eac39b2eb031c68cbf204d083572e1_Traceguids);
    if ( (xmmword_180063D60 & 2) != 0 )
      WPP_SF_S(1025, 18, WPP_32eac39b2eb031c68cbf204d083572e1_Traceguids, Src);
  }
  if ( Src && a2 )
  {
    v8 = *a2 - HostnameGuid;
    if ( *a2 == HostnameGuid )
      v8 = a2[1] - qword_180063A90;
    if ( !v8 )
      goto LABEL_11;
    v19 = *a2 - InetHostName;
    if ( *a2 == InetHostName )
      v19 = a2[1] - qword_180063A70;
    if ( !v19 )
    {
LABEL_11:
      v9 = wcschr(Src, 0x2Fu);
      if ( !v9 )
        v9 = wcschr(Src, 0);
      v10 = v9 - Src;
      v11 = (unsigned int)(2 * v10 + 2);
      if ( (unsigned int)v11 > (unsigned int)v10 )
      {
        v12 = (char *)DnsApiAlloc(v11);
        if ( v12 )
        {
          v13 = 2LL * (unsigned int)v10;
          memcpy_0(v12, Src, v13);
          *(_WORD *)&v12[v13] = 0;
          AnsiNameRnR = (const char *)GetAnsiNameRnR((LPCWCH)v12);
          DnsApiFree(v12);
          if ( AnsiNameRnR )
          {
            v15 = *AnsiNameRnR;
            v16 = AnsiNameRnR;
            while ( v15 && (unsigned int)_o_isdigit((unsigned int)v15) )
              v15 = *++v16;
            if ( !*v16 )
              LODWORD(v4) = atoi(AnsiNameRnR);
            if ( *v9 && v9[1] )
              v17 = GetAnsiNameRnR(v9 + 1);
            else
              v17 = 0;
            if ( (_DWORD)v4 )
              v18 = pgetservebyport((unsigned int)v4, v17);
            else
              v18 = pgetservebyname(AnsiNameRnR, v17);
            v4 = v18;
            if ( v17 )
              DnsApiFree(v17);
            DnsApiFree(AnsiNameRnR);
          }
        }
      }
    }
  }
  if ( a3 )
    *a3 = v4;
  if ( v4 )
    return 2 - (unsigned int)((unsigned int)_o__stricmp("udp", *(_QWORD *)(v4 + 16)) != 0);
  else
    return 3;
}

```

## disassembly

```asm
0x1800038b4  push    rbx
0x1800038b6  push    rsi
0x1800038b7  push    rdi
0x1800038b8  push    r12
0x1800038ba  push    r13
0x1800038bc  push    r14
0x1800038be  push    r15
0x1800038c0  sub     rsp, 20h
0x1800038c4  xor     r13d, r13d
0x1800038c7  mov     r12, r8
0x1800038ca  mov     r14d, r13d
0x1800038cd  mov     rbx, rdx
0x1800038d0  mov     rsi, rcx
0x1800038d3  mov     al, byte ptr cs:xmmword_180063D60
0x1800038d9  mov     edi, 401h
0x1800038de  test    al, 2
0x1800038e0  jnz     loc_180003A6F
0x1800038e6  test    rsi, rsi
0x1800038e9  jnz     short loc_180003912
0x1800038eb  test    r12, r12
0x1800038ee  jz      short loc_1800038F4
0x1800038f0  mov     [r12], r14
0x1800038f4  test    r14, r14
0x1800038f7  jnz     loc_180003A27
0x1800038fd  lea     eax, [r14+3]
0x180003901  add     rsp, 20h
0x180003905  pop     r15
0x180003907  pop     r14
0x180003909  pop     r13
0x18000390b  pop     r12
0x18000390d  pop     rdi
0x18000390e  pop     rsi
0x18000390f  pop     rbx
0x180003910  retn
0x180003912  test    rbx, rbx
0x180003915  jz      short loc_1800038EB
0x180003917  mov     rax, [rbx]
0x18000391a  sub     rax, cs:HostnameGuid
0x180003921  jnz     short loc_18000392E
0x180003923  mov     rax, [rbx+8]
0x180003927  sub     rax, cs:qword_180063A90
0x18000392e  test    rax, rax
0x180003931  jnz     loc_180003AAB
0x180003937  mov     edx, 2Fh ; '/'; Ch
0x18000393c  mov     rcx, rsi; Str
0x18000393f  call    cs:__imp_wcschr
0x180003946  nop     dword ptr [rax+rax+00h]
0x18000394b  mov     rdi, rax
0x18000394e  test    rax, rax
0x180003951  jz      loc_180003AD0
0x180003957  mov     rbx, rdi
0x18000395a  sub     rbx, rsi
0x18000395d  sar     rbx, 1
0x180003960  lea     ecx, ds:2[rbx*2]
0x180003967  cmp     ecx, ebx
0x180003969  jbe     short loc_1800038EB
0x18000396b  call    cs:__imp_DnsApiAlloc
0x180003972  nop     dword ptr [rax+rax+00h]
0x180003977  mov     r15, rax
0x18000397a  test    rax, rax
0x18000397d  jz      loc_1800038EB
0x180003983  mov     eax, ebx
0x180003985  mov     rdx, rsi; Src
0x180003988  mov     rcx, r15; void *
0x18000398b  lea     rbx, [rax+rax]
0x18000398f  mov     r8, rbx; Size
0x180003992  call    memcpy_0
0x180003997  mov     rcx, r15; lpWideCharStr
0x18000399a  mov     [rbx+r15], r13w
0x18000399f  call    GetAnsiNameRnR
0x1800039a4  mov     rcx, r15
0x1800039a7  mov     rsi, rax
0x1800039aa  call    cs:__imp_DnsApiFree
0x1800039b1  nop     dword ptr [rax+rax+00h]
0x1800039b6  test    rsi, rsi
0x1800039b9  jz      loc_1800038EB
0x1800039bf  mov     al, [rsi]
0x1800039c1  mov     rbx, rsi
0x1800039c4  test    al, al
0x1800039c6  jz      short loc_1800039DF
0x1800039c8  movsx   ecx, al
0x1800039cb  call    cs:__imp__o_isdigit
0x1800039d2  nop     dword ptr [rax+rax+00h]
0x1800039d7  test    eax, eax
0x1800039d9  jnz     loc_180003AE9
0x1800039df  cmp     [rbx], r13b
0x1800039e2  jz      loc_180003AF3
0x1800039e8  cmp     [rdi], r13w
0x1800039ec  jz      short loc_1800039F8
0x1800039ee  lea     rcx, [rdi+2]; lpWideCharStr
0x1800039f2  cmp     [rcx], r13w
0x1800039f6  jnz     short loc_180003A54
0x1800039f8  mov     rbx, r13
0x1800039fb  mov     rdx, rbx
0x1800039fe  test    r14d, r14d
0x180003a01  jz      short loc_180003A4A
0x180003a03  mov     ecx, r14d
0x180003a06  call    _pgetservebyport
0x180003a0b  mov     r14, rax
0x180003a0e  test    rbx, rbx
0x180003a11  jnz     short loc_180003A5E
0x180003a13  mov     rcx, rsi
0x180003a16  call    cs:__imp_DnsApiFree
0x180003a1d  nop     dword ptr [rax+rax+00h]
0x180003a22  jmp     loc_1800038EB
0x180003a27  mov     rdx, [r14+10h]
0x180003a2b  lea     rcx, proto; "udp"
0x180003a32  call    cs:__imp__o__stricmp
0x180003a39  nop     dword ptr [rax+rax+00h]
0x180003a3e  neg     eax
0x180003a40  sbb     eax, eax
0x180003a42  add     eax, 2
0x180003a45  jmp     loc_180003901
0x180003a4a  mov     rcx, rsi
0x180003a4d  call    _pgetservebyname
0x180003a52  jmp     short loc_180003A0B
0x180003a54  call    GetAnsiNameRnR
0x180003a59  mov     rbx, rax
0x180003a5c  jmp     short loc_1800039FB
0x180003a5e  mov     rcx, rbx
0x180003a61  call    cs:__imp_DnsApiFree
0x180003a68  nop     dword ptr [rax+rax+00h]
0x180003a6d  jmp     short loc_180003A13
0x180003a6f  mov     edx, 11h
0x180003a74  lea     r8, WPP_32eac39b2eb031c68cbf204d083572e1_Traceguids
0x180003a7b  mov     ecx, edi
0x180003a7d  call    WPP_SF_
0x180003a82  mov     al, byte ptr cs:xmmword_180063D60
0x180003a88  test    al, 2
0x180003a8a  jz      loc_1800038E6
0x180003a90  mov     edx, 12h
0x180003a95  lea     r8, WPP_32eac39b2eb031c68cbf204d083572e1_Traceguids
0x180003a9c  mov     ecx, edi
0x180003a9e  mov     r9, rsi
0x180003aa1  call    WPP_SF_S
0x180003aa6  jmp     loc_1800038E6
0x180003aab  mov     rax, [rbx]
0x180003aae  sub     rax, cs:InetHostName
0x180003ab5  jnz     short loc_180003AC2
0x180003ab7  mov     rax, [rbx+8]
0x180003abb  sub     rax, cs:qword_180063A70
0x180003ac2  test    rax, rax
0x180003ac5  jnz     loc_1800038EB
0x180003acb  jmp     loc_180003937
0x180003ad0  xor     edx, edx; Ch
0x180003ad2  mov     rcx, rsi; Str
0x180003ad5  call    cs:__imp_wcschr
0x180003adc  nop     dword ptr [rax+rax+00h]
0x180003ae1  mov     rdi, rax
0x180003ae4  jmp     loc_180003957
0x180003ae9  inc     rbx
0x180003aec  mov     al, [rbx]
0x180003aee  jmp     loc_1800039C4
0x180003af3  mov     rcx, rsi; String
0x180003af6  call    cs:__imp_atoi
0x180003afd  nop     dword ptr [rax+rax+00h]
0x180003b02  mov     r14d, eax
0x180003b05  jmp     loc_1800039E8
```
