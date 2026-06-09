# Dhcpv6DynDnsGetDynDNSOption

- ea: `0x180003100`
- end: `0x1800032fd`
- name: `Dhcpv6DynDnsGetDynDNSOption`
- size: `509`
- prototype: `__int64 __fastcall(_BYTE *, _WORD *, __int64, __int64)`
- caller_count: `4`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180002328`
- `0x1800027e0`
- `0x18001f77c`
- `0x1800200d8`

## callees

- `0x180003100`
- `0x180003304`
- `0x180016910`
- `0x18001907c`
- `0x180019ad0`
- `0x180019b10`
- `0x18001a3ee`
- `0x1800338c0`
- `0x180033900`
- `0x1800347c8`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800031ee`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x1800031ee`
- `DNSAPI!DnsQueryConfigDword` at `0x180003180`
- `DNSAPI!DnsQueryConfigDword` at `0x180003180`

## pseudocode

```c
__int64 __fastcall Dhcpv6DynDnsGetDynDNSOption(_BYTE *a1, _WORD *a2, __int64 a3, __int64 a4)
{
  int v7; // ecx
  unsigned int LastErrorOrUnknown; // ebx
  int v9; // ebx
  int v10; // ebx
  WCHAR *v11; // r14
  __int64 v12; // rdx
  DWORD v13; // eax
  DWORD nSize; // [rsp+30h] [rbp-D0h] BYREF
  DWORD v16; // [rsp+34h] [rbp-CCh]
  int v17; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Buffer[256]; // [rsp+40h] [rbp-C0h] BYREF

  nSize = 0;
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_Sl(v7, 33, (unsigned int)WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids, a4, 1);
  if ( !(unsigned int)DnsQueryConfigDword(65552, a4) )
  {
    LastErrorOrUnknown = 1003;
    goto LABEL_21;
  }
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_(1028, 34, WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids);
  v9 = (unsigned __int16)*a2;
  if ( !*a2 )
  {
    LastErrorOrUnknown = 122;
    goto LABEL_21;
  }
  *a1 = 0;
  v10 = v9 - 1;
  *a2 = 1;
  v17 = v10;
  nSize = 256;
  if ( !GetComputerNameExW(ComputerNameDnsHostname, Buffer, &nSize) )
  {
    LastErrorOrUnknown = GetLastErrorOrUnknown();
    goto LABEL_21;
  }
  if ( nSize > 0x3F )
    goto LABEL_12;
  v11 = &Buffer[nSize + 1];
  v16 = 254 - nSize;
  if ( (unsigned int)Dhcpv6DynDnsGetDynDNSOptionDomain(v11) || (v12 = v16) == 0 )
  {
    if ( 2 * (unsigned __int64)nSize >= 0x200 )
      _report_rangecheckfailure();
    Buffer[nSize] = 0;
  }
  else
  {
    v13 = nSize + 1;
    Buffer[nSize] = 46;
    if ( (unsigned int)v12 + v13 > 0xFF )
    {
LABEL_12:
      LastErrorOrUnknown = 1212;
      goto LABEL_21;
    }
    v11[v12] = 0;
  }
  LastErrorOrUnknown = DhcpGetWireFormatNameFromUnicode(a1 + 1, &a1[v10 + 1], Buffer, &v17);
  if ( !LastErrorOrUnknown )
    *a2 += v17;
LABEL_21:
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_D(1028, 35, WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids, LastErrorOrUnknown);
  return LastErrorOrUnknown;
}

```

## disassembly

```asm
0x180003100  push    rbp
0x180003102  push    rbx
0x180003103  push    rsi
0x180003104  push    rdi
0x180003105  push    r12
0x180003107  push    r14
0x180003109  push    r15
0x18000310b  lea     rbp, [rsp-150h]
0x180003113  sub     rsp, 250h
0x18000311a  mov     rax, cs:__security_cookie
0x180003121  xor     rax, rsp
0x180003124  mov     [rbp+180h+var_40], rax
0x18000312b  mov     r12, r8
0x18000312e  mov     [rsp+280h+nSize], 0
0x180003136  mov     rdi, rdx
0x180003139  mov     r15, rcx
0x18000313c  xor     edx, edx; Val
0x18000313e  lea     rcx, [rsp+280h+Buffer]; void *
0x180003143  mov     r8d, 200h; Size
0x180003149  mov     rsi, r9
0x18000314c  call    memset_0
0x180003151  test    byte ptr cs:xmmword_1800423E0, 10h
0x180003158  mov     r14d, 1
0x18000315e  jz      short loc_180003178
0x180003160  lea     edx, [r14+20h]
0x180003164  mov     [rsp+280h+var_260], r14d
0x180003169  mov     r9, rsi
0x18000316c  lea     r8, WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids
0x180003173  call    WPP_SF_Sl
0x180003178  mov     rdx, rsi
0x18000317b  mov     ecx, 10010h
0x180003180  call    cs:__imp_DnsQueryConfigDword
0x180003187  nop     dword ptr [rax+rax+00h]
0x18000318c  test    eax, eax
0x18000318e  jnz     short loc_18000319A
0x180003190  mov     ebx, 3EBh
0x180003195  jmp     loc_1800032B1
0x18000319a  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800031a1  jz      short loc_1800031B9
0x1800031a3  mov     edx, 22h ; '"'
0x1800031a8  lea     r8, WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids
0x1800031af  mov     ecx, 404h
0x1800031b4  call    WPP_SF_
0x1800031b9  movzx   ebx, word ptr [rdi]
0x1800031bc  cmp     ebx, r14d
0x1800031bf  jnb     short loc_1800031CB
0x1800031c1  mov     ebx, 7Ah ; 'z'
0x1800031c6  jmp     loc_1800032B1
0x1800031cb  mov     byte ptr [r15], 0
0x1800031cf  lea     r8, [rsp+280h+nSize]; nSize
0x1800031d4  dec     ebx
0x1800031d6  mov     [rdi], r14w
0x1800031da  lea     rdx, [rsp+280h+Buffer]; lpBuffer
0x1800031df  mov     [rsp+280h+var_248], ebx
0x1800031e3  mov     ecx, r14d; NameType
0x1800031e6  mov     [rsp+280h+nSize], 100h
0x1800031ee  call    cs:__imp_GetComputerNameExW
0x1800031f5  nop     dword ptr [rax+rax+00h]
0x1800031fa  test    eax, eax
0x1800031fc  jnz     short loc_18000320A
0x1800031fe  call    GetLastErrorOrUnknown
0x180003203  mov     ebx, eax
0x180003205  jmp     loc_1800032B1
0x18000320a  mov     ecx, [rsp+280h+nSize]
0x18000320e  cmp     ecx, 3Fh ; '?'
0x180003211  jbe     short loc_18000321D
0x180003213  mov     ebx, 4BCh
0x180003218  jmp     loc_1800032B1
0x18000321d  mov     eax, 0FEh
0x180003222  lea     r14, [rsp+280h+var_23E]
0x180003227  sub     eax, ecx
0x180003229  lea     r14, [r14+rcx*2]
0x18000322d  mov     rcx, r14; void *
0x180003230  mov     [rsp+280h+var_24C], eax
0x180003234  mov     r9, rsi
0x180003237  lea     rdx, [rsp+280h+var_24C]
0x18000323c  mov     r8, r12
0x18000323f  call    Dhcpv6DynDnsGetDynDNSOptionDomain
0x180003244  test    eax, eax
0x180003246  jnz     short loc_180003273
0x180003248  mov     edx, [rsp+280h+var_24C]
0x18000324c  test    edx, edx
0x18000324e  jz      short loc_180003273
0x180003250  mov     ecx, [rsp+280h+nSize]
0x180003254  lea     r8d, [rax+2Eh]
0x180003258  lea     eax, [rcx+1]
0x18000325b  mov     [rsp+rcx*2+280h+Buffer], r8w
0x180003261  add     eax, edx
0x180003263  cmp     eax, 0FFh
0x180003268  ja      short loc_180003213
0x18000326a  xor     eax, eax
0x18000326c  mov     [r14+rdx*2], ax
0x180003271  jmp     short loc_18000328B
0x180003273  mov     eax, [rsp+280h+nSize]
0x180003277  lea     rcx, [rax+rax]
0x18000327b  cmp     rcx, 200h
0x180003282  jnb     short loc_1800032F7
0x180003284  xor     eax, eax
0x180003286  mov     [rsp+rcx+280h+Buffer], ax
0x18000328b  lea     rcx, [r15+1]
0x18000328f  mov     edx, ebx
0x180003291  add     rdx, rcx
0x180003294  lea     r9, [rsp+280h+var_248]
0x180003299  lea     r8, [rsp+280h+Buffer]
0x18000329e  call    DhcpGetWireFormatNameFromUnicode
0x1800032a3  mov     ebx, eax
0x1800032a5  test    eax, eax
0x1800032a7  jnz     short loc_1800032B1
0x1800032a9  movzx   eax, word ptr [rsp+280h+var_248]
0x1800032ae  add     [rdi], ax
0x1800032b1  test    byte ptr cs:xmmword_1800423E0, 10h
0x1800032b8  jz      short loc_1800032D3
0x1800032ba  mov     edx, 23h ; '#'
0x1800032bf  lea     r8, WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids
0x1800032c6  mov     ecx, 404h
0x1800032cb  mov     r9d, ebx
0x1800032ce  call    WPP_SF_D
0x1800032d3  mov     eax, ebx
0x1800032d5  mov     rcx, [rbp+180h+var_40]
0x1800032dc  xor     rcx, rsp; StackCookie
0x1800032df  call    __security_check_cookie
0x1800032e4  add     rsp, 250h
0x1800032eb  pop     r15
0x1800032ed  pop     r14
0x1800032ef  pop     r12
0x1800032f1  pop     rdi
0x1800032f2  pop     rsi
0x1800032f3  pop     rbx
0x1800032f4  pop     rbp
0x1800032f5  retn
0x1800032f7  call    __report_rangecheckfailure
```
