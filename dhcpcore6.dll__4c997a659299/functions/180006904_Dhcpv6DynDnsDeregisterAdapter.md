# Dhcpv6DynDnsDeregisterAdapter

- ea: `0x180006904`
- end: `0x180006d50`
- name: `Dhcpv6DynDnsDeregisterAdapter`
- size: `1100`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800058ec`
- `0x180010fd4`

## callees

- `0x18000163c`
- `0x180004c3c`
- `0x180006904`
- `0x180007564`
- `0x180019ad0`
- `0x18001a3ee`
- `0x1800337d0`
- `0x1800338c0`
- `0x180033900`
- `0x180033970`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d1b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006bb5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006bb5`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180006995`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x180006995`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006be0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180006be0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180006a72`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180006a72`
- `DNSAPI!DnsDhcpRegisterAddrs` at `0x180006a29`
- `DNSAPI!DnsDhcpRegisterAddrs` at `0x180006a29`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x1800069e4`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x1800069e4`

## pseudocode

```c
__int64 __fastcall Dhcpv6DynDnsDeregisterAdapter(__int64 *a1, int a2, __int64 a3, unsigned int a4)
{
  __int64 v5; // rbx
  __int64 v8; // r14
  char v9; // si
  DWORD v10; // eax
  __int64 v11; // rcx
  DWORD v12; // ebx
  _DWORD *v13; // rax
  __int64 *v15; // rcx
  __int64 v16; // rdx
  __int16 *v17; // rax
  __int16 *v18; // r8
  DWORD v19; // eax
  unsigned int v20; // r8d
  __int64 v21; // rdx
  __int64 v22; // rax
  __int64 v23; // rcx
  __int128 v24; // xmm0
  char *v25; // rax
  __int128 v26; // xmm1
  DWORD LastError; // eax
  _DWORD v28[2]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v29; // [rsp+38h] [rbp-C8h]
  __int64 v30; // [rsp+40h] [rbp-C0h]
  __int64 v31; // [rsp+48h] [rbp-B8h]
  __int64 v32; // [rsp+50h] [rbp-B0h]
  LPVOID lpMem; // [rsp+58h] [rbp-A8h]
  int v34; // [rsp+68h] [rbp-98h]
  int v35; // [rsp+6Ch] [rbp-94h]
  NET_IF_COMPARTMENT_ID CurrentThreadCompartmentId; // [rsp+78h] [rbp-88h]
  _OWORD v37[2]; // [rsp+80h] [rbp-80h] BYREF
  _DWORD v38[40]; // [rsp+A0h] [rbp-60h] BYREF
  __int16 v39; // [rsp+140h] [rbp+40h] BYREF

  v5 = a4;
  memset_0(v38, 0, 0x140u);
  v8 = 80;
  memset_0(v28, 0, 0x50u);
  memset(v37, 0, 28);
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_S(1028, 22, WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids, a1);
  v9 = 0;
  if ( a2 && Dhcpv6GlobalHostStatus )
  {
    ResetEvent(Dhcpv6GlobalHostStatus);
    v9 = 1;
  }
  v28[1] = 1;
  LOWORD(v37[0]) = 23;
  v31 = 0;
  v32 = 0;
  v30 = (unsigned __int64)a1 & -(__int64)(a2 != 0);
  if ( (_DWORD)v5 )
  {
    v13 = (_DWORD *)DhcpAlloc((v5 << 6) + 96);
    lpMem = v13;
    if ( !v13 )
      return 8;
    *v13 = v5;
    v20 = 0;
    *((_DWORD *)lpMem + 1) = v5;
    *((_WORD *)lpMem + 6) = 23;
    v21 = 0;
    do
    {
      v22 = 2 * v21;
      v23 = v21 << 6;
      ++v20;
      ++v21;
      v24 = *(_OWORD *)(a3 + 8 * v22);
      v25 = (char *)lpMem;
      *(_OWORD *)((char *)v37 + 8) = v24;
      v26 = *(_OWORD *)((char *)v37 + 12);
      *(_OWORD *)((char *)lpMem + v23 + 32) = v37[0];
      *(_OWORD *)&v25[v23 + 44] = v26;
      *(_DWORD *)((char *)lpMem + v23 + 64) = 28;
    }
    while ( v20 < (unsigned int)v5 );
  }
  v34 = 0;
  v35 = 544;
  CurrentThreadCompartmentId = GetCurrentThreadCompartmentId();
  v28[0] = 80;
  v29 = (unsigned __int64)&Dhcpv6GlobalHostStatus & -(__int64)(v9 != 0);
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_S(1028, 24, WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids, a1);
  v10 = DnsDhcpRegisterAddrs(v28);
  v12 = v10;
  if ( v10 )
  {
    if ( (xmmword_1800423E0 & 2) != 0 )
      WPP_SF_SD(1025, 25, (unsigned int)WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids, (_DWORD)a1, v10);
    if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 1) != 0 )
      McTemplateU0zq_EtwEventWriteTransfer(v11, ErrorDeregisteringDNS, a1, v12);
    memset_0(v38, 0, sizeof(v38));
    v39 = 0;
    v15 = &qword_180037F50;
    v38[0] = v12;
    if ( a1 )
      v15 = a1;
    v38[3] = 26;
    v16 = 2147483646;
    v17 = &v39;
    do
    {
      if ( !v16 )
        break;
      if ( !*(_WORD *)v15 )
        break;
      *v17 = *(_WORD *)v15;
      v15 = (__int64 *)((char *)v15 + 2);
      ++v17;
      --v16;
      --v8;
    }
    while ( v8 );
    v18 = v17 - 1;
    if ( v8 )
      v18 = v17;
    *v18 = 0;
    TraceLogEx(v38);
  }
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_D(1028, 26, WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids, v12);
  if ( lpMem )
  {
    HeapFree(NtCurrentPeb()->ProcessHeap, 0, lpMem);
    lpMem = 0;
  }
  if ( v12 )
  {
    if ( (BYTE1(xmmword_1800423E0) & 0x20) != 0 )
      WPP_SF_D(1037, 27, WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids, v12);
    if ( v9 )
      return v12;
    goto LABEL_16;
  }
  if ( !v9 )
  {
LABEL_16:
    if ( a2 )
      Sleep(0x3E8u);
    return v12;
  }
  if ( Dhcpv6GlobalHostStatus )
  {
    v19 = WaitForSingleObject(Dhcpv6GlobalHostStatus, 0xFA0u);
    if ( v19 != 128 )
    {
      if ( v19 == 258 )
      {
        if ( (BYTE1(xmmword_1800423E0) & 0x20) != 0 )
          WPP_SF_(1037, 29, WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids);
        return 0;
      }
      if ( v19 != -1 )
        return 0;
    }
    LastError = GetLastError();
    v12 = LastError;
    if ( (BYTE1(xmmword_1800423E0) & 0x20) != 0 )
      WPP_SF_D(1037, 28, WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids, LastError);
  }
  return v12;
}

```

## disassembly

```asm
0x180006904  mov     [rsp-8+arg_8], rbx
0x180006909  push    rbp
0x18000690a  push    rsi
0x18000690b  push    rdi
0x18000690c  push    r12
0x18000690e  push    r13
0x180006910  push    r14
0x180006912  push    r15
0x180006914  lea     rbp, [rsp-0F0h]
0x18000691c  sub     rsp, 1F0h
0x180006923  mov     rax, cs:__security_cookie
0x18000692a  xor     rax, rsp
0x18000692d  mov     [rbp+120h+var_40], rax
0x180006934  mov     r12, r8
0x180006937  mov     ebx, r9d
0x18000693a  mov     r15d, edx
0x18000693d  mov     rdi, rcx
0x180006940  xor     edx, edx; Val
0x180006942  lea     rcx, [rbp+120h+var_180]; void *
0x180006946  mov     r8d, 140h; Size
0x18000694c  call    memset_0
0x180006951  mov     r14d, 50h ; 'P'
0x180006957  lea     rcx, [rsp+220h+var_1F0]; void *
0x18000695c  mov     r8d, r14d; Size
0x18000695f  xor     edx, edx; Val
0x180006961  call    memset_0
0x180006966  xorps   xmm0, xmm0
0x180006969  movups  xmmword ptr [rbp+120h+var_1A0], xmm0
0x18000696d  movups  xmmword ptr [rbp+120h+var_1A0+0Ch], xmm0
0x180006971  test    byte ptr cs:xmmword_1800423E0, 10h
0x180006978  jnz     loc_180006AD7
0x18000697e  xor     r13d, r13d
0x180006981  mov     sil, r13b
0x180006984  test    r15d, r15d
0x180006987  jz      short loc_1800069A4
0x180006989  mov     rcx, cs:Dhcpv6GlobalHostStatus; hEvent
0x180006990  test    rcx, rcx
0x180006993  jz      short loc_1800069A4
0x180006995  call    cs:__imp_ResetEvent
0x18000699c  nop     dword ptr [rax+rax+00h]
0x1800069a1  mov     sil, 1
0x1800069a4  mov     eax, 17h
0x1800069a9  mov     [rsp+220h+var_1EC], 1
0x1800069b1  mov     word ptr [rbp+120h+var_1A0], ax
0x1800069b5  mov     eax, r15d
0x1800069b8  neg     eax
0x1800069ba  mov     [rsp+220h+var_1D8], r13
0x1800069bf  mov     [rsp+220h+var_1D0], r13
0x1800069c4  sbb     rcx, rcx
0x1800069c7  and     rcx, rdi
0x1800069ca  mov     [rsp+220h+var_1E0], rcx
0x1800069cf  test    ebx, ebx
0x1800069d1  jnz     loc_180006A80
0x1800069d7  mov     [rsp+220h+var_1B8], r13d
0x1800069dc  mov     [rsp+220h+var_1B4], 220h
0x1800069e4  call    cs:__imp_GetCurrentThreadCompartmentId
0x1800069eb  nop     dword ptr [rax+rax+00h]
0x1800069f0  mov     [rsp+220h+var_1A8], eax
0x1800069f4  mov     al, sil
0x1800069f7  neg     al
0x1800069f9  mov     [rsp+220h+var_1F0], r14d
0x1800069fe  lea     rax, Dhcpv6GlobalHostStatus
0x180006a05  sbb     rcx, rcx
0x180006a08  and     rcx, rax
0x180006a0b  mov     [rsp+220h+var_1E8], rcx
0x180006a10  test    byte ptr cs:xmmword_1800423E0, 10h
0x180006a17  lea     r12, WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids
0x180006a1e  jnz     loc_180006C81
0x180006a24  lea     rcx, [rsp+220h+var_1F0]
0x180006a29  call    cs:__imp_DnsDhcpRegisterAddrs
0x180006a30  nop     dword ptr [rax+rax+00h]
0x180006a35  mov     ebx, eax
0x180006a37  test    eax, eax
0x180006a39  jnz     loc_180006B0F
0x180006a3f  test    byte ptr cs:xmmword_1800423E0, 10h
0x180006a46  jnz     loc_180006AF5
0x180006a4c  cmp     [rsp+220h+lpMem], r13
0x180006a51  jnz     loc_180006BA1
0x180006a57  test    ebx, ebx
0x180006a59  jnz     loc_180006CD0
0x180006a5f  test    sil, sil
0x180006a62  jnz     loc_180006BCB
0x180006a68  test    r15d, r15d
0x180006a6b  jz      short loc_180006AAA
0x180006a6d  mov     ecx, 3E8h; dwMilliseconds
0x180006a72  call    cs:__imp_Sleep
0x180006a79  nop     dword ptr [rax+rax+00h]
0x180006a7e  jmp     short loc_180006AAA
0x180006a80  mov     rcx, rbx
0x180006a83  shl     rcx, 6
0x180006a87  add     rcx, 60h ; '`'
0x180006a8b  call    DhcpAlloc
0x180006a90  mov     [rsp+220h+lpMem], rax
0x180006a95  test    rax, rax
0x180006a98  jnz     loc_180006C13
0x180006a9e  mov     eax, 8
0x180006aa3  jmp     short loc_180006AAC
0x180006aa5  test    sil, sil
0x180006aa8  jz      short loc_180006A68
0x180006aaa  mov     eax, ebx
0x180006aac  mov     rcx, [rbp+120h+var_40]
0x180006ab3  xor     rcx, rsp; StackCookie
0x180006ab6  call    __security_check_cookie
0x180006abb  mov     rbx, [rsp+220h+arg_8]
0x180006ac3  add     rsp, 1F0h
0x180006aca  pop     r15
0x180006acc  pop     r14
0x180006ace  pop     r13
0x180006ad0  pop     r12
0x180006ad2  pop     rdi
0x180006ad3  pop     rsi
0x180006ad4  pop     rbp
0x180006ad5  retn
0x180006ad7  mov     edx, 16h
0x180006adc  lea     r8, WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids
0x180006ae3  mov     ecx, 404h
0x180006ae8  mov     r9, rdi
0x180006aeb  call    WPP_SF_S
0x180006af0  jmp     loc_18000697E
0x180006af5  mov     edx, 1Ah
0x180006afa  mov     ecx, 404h
0x180006aff  mov     r9d, ebx
0x180006b02  mov     r8, r12
0x180006b05  call    WPP_SF_D
0x180006b0a  jmp     loc_180006A4C
0x180006b0f  test    byte ptr cs:xmmword_1800423E0, 2
0x180006b16  jnz     loc_180006C9B
0x180006b1c  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 1
0x180006b23  jnz     loc_180006CB9
0x180006b29  xor     edx, edx; Val
0x180006b2b  lea     rcx, [rbp+120h+var_180]; void *
0x180006b2f  mov     r8d, 0A0h; Size
0x180006b35  call    memset_0
0x180006b3a  test    rdi, rdi
0x180006b3d  mov     [rbp+120h+var_E0], r13w
0x180006b42  lea     rcx, qword_180037F50
0x180006b49  mov     [rbp+120h+var_180], ebx
0x180006b4c  cmovnz  rcx, rdi
0x180006b50  mov     [rbp+120h+var_174], 1Ah
0x180006b57  mov     edx, 7FFFFFFEh
0x180006b5c  lea     rax, [rbp+120h+var_E0]
0x180006b60  test    rdx, rdx
0x180006b63  jz      short loc_180006B84
0x180006b65  movzx   r8d, word ptr [rcx]
0x180006b69  test    r8w, r8w
0x180006b6d  jz      short loc_180006B84
0x180006b6f  mov     [rax], r8w
0x180006b73  add     rcx, 2
0x180006b77  add     rax, 2
0x180006b7b  dec     rdx
0x180006b7e  sub     r14, 1
0x180006b82  jnz     short loc_180006B60
0x180006b84  test    r14, r14
0x180006b87  lea     r8, [rax-2]
0x180006b8b  lea     rcx, [rbp+120h+var_180]
0x180006b8f  cmovnz  r8, rax
0x180006b93  mov     [r8], r13w
0x180006b97  call    TraceLogEx
0x180006b9c  jmp     loc_180006A3F
0x180006ba1  mov     rcx, gs:60h
0x180006baa  xor     edx, edx; dwFlags
0x180006bac  mov     r8, [rsp+220h+lpMem]; lpMem
0x180006bb1  mov     rcx, [rcx+30h]; hHeap
0x180006bb5  call    cs:__imp_HeapFree
0x180006bbc  nop     dword ptr [rax+rax+00h]
0x180006bc1  mov     [rsp+220h+lpMem], r13
0x180006bc6  jmp     loc_180006A57
0x180006bcb  mov     rcx, cs:Dhcpv6GlobalHostStatus; hHandle
0x180006bd2  test    rcx, rcx
0x180006bd5  jz      loc_180006AAA
0x180006bdb  mov     edx, 0FA0h; dwMilliseconds
0x180006be0  call    cs:__imp_WaitForSingleObject
0x180006be7  nop     dword ptr [rax+rax+00h]
0x180006bec  cmp     eax, 80h
0x180006bf1  jz      loc_180006D1B
0x180006bf7  cmp     eax, 102h
0x180006bfc  jz      loc_180006CF7
0x180006c02  cmp     eax, 0FFFFFFFFh
0x180006c05  jz      loc_180006D1B
0x180006c0b  mov     ebx, r13d
0x180006c0e  jmp     loc_180006AAA
0x180006c13  mov     [rax], ebx
0x180006c15  mov     r8d, r13d
0x180006c18  mov     rax, [rsp+220h+lpMem]
0x180006c1d  mov     [rax+4], ebx
0x180006c20  mov     rax, [rsp+220h+lpMem]
0x180006c25  mov     word ptr [rax+0Ch], 17h
0x180006c2b  test    ebx, ebx
0x180006c2d  jz      loc_1800069D7
0x180006c33  mov     rdx, r13
0x180006c36  mov     rax, rdx
0x180006c39  mov     rcx, rdx
0x180006c3c  add     rax, rax
0x180006c3f  shl     rcx, 6
0x180006c43  inc     r8d
0x180006c46  inc     rdx
0x180006c49  movups  xmm0, xmmword ptr [r12+rax*8]
0x180006c4e  mov     rax, [rsp+220h+lpMem]
0x180006c53  movdqu  xmmword ptr [rbp+120h+var_1A0+8], xmm0
0x180006c58  movups  xmm0, xmmword ptr [rbp+120h+var_1A0]
0x180006c5c  movups  xmm1, xmmword ptr [rbp+120h+var_1A0+0Ch]
0x180006c60  movups  xmmword ptr [rcx+rax+20h], xmm0
0x180006c65  movups  xmmword ptr [rcx+rax+2Ch], xmm1
0x180006c6a  mov     rax, [rsp+220h+lpMem]
0x180006c6f  mov     dword ptr [rcx+rax+40h], 1Ch
0x180006c77  cmp     r8d, ebx
0x180006c7a  jb      short loc_180006C36
0x180006c7c  jmp     loc_1800069D7
0x180006c81  mov     edx, 18h
0x180006c86  mov     ecx, 404h
0x180006c8b  mov     r9, rdi
0x180006c8e  mov     r8, r12
0x180006c91  call    WPP_SF_S
0x180006c96  jmp     loc_180006A24
0x180006c9b  mov     edx, 19h
0x180006ca0  mov     [rsp+220h+var_200], ebx
0x180006ca4  mov     ecx, 401h
0x180006ca9  mov     r9, rdi
0x180006cac  mov     r8, r12
0x180006caf  call    WPP_SF_SD
0x180006cb4  jmp     loc_180006B1C
0x180006cb9  mov     r9d, ebx
0x180006cbc  lea     rdx, ErrorDeregisteringDNS
0x180006cc3  mov     r8, rdi
0x180006cc6  call    McTemplateU0zq_EtwEventWriteTransfer
0x180006ccb  jmp     loc_180006B29
0x180006cd0  test    byte ptr cs:xmmword_1800423E0+1, 20h
0x180006cd7  jz      loc_180006AA5
0x180006cdd  mov     edx, 1Bh
0x180006ce2  mov     ecx, 40Dh
0x180006ce7  mov     r9d, ebx
0x180006cea  mov     r8, r12
0x180006ced  call    WPP_SF_D
0x180006cf2  jmp     loc_180006AA5
0x180006cf7  test    byte ptr cs:xmmword_1800423E0+1, 20h
0x180006cfe  jz      loc_180006C0B
0x180006d04  mov     edx, 1Dh
0x180006d09  mov     ecx, 40Dh
0x180006d0e  mov     r8, r12
0x180006d11  call    WPP_SF_
0x180006d16  jmp     loc_180006C0B
0x180006d1b  call    cs:__imp_GetLastError
0x180006d22  nop     dword ptr [rax+rax+00h]
0x180006d27  mov     ebx, eax
0x180006d29  test    byte ptr cs:xmmword_1800423E0+1, 20h
0x180006d30  jz      loc_180006AAA
0x180006d36  mov     edx, 1Ch
0x180006d3b  mov     ecx, 40Dh
0x180006d40  mov     r9d, eax
0x180006d43  mov     r8, r12
0x180006d46  call    WPP_SF_D
0x180006d4b  jmp     loc_180006AAA
```
