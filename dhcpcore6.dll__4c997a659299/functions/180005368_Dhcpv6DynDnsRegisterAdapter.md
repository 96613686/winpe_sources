# Dhcpv6DynDnsRegisterAdapter

- ea: `0x180005368`
- end: `0x1800058e5`
- name: `Dhcpv6DynDnsRegisterAdapter`
- size: `1405`
- prototype: `__int64 __usercall@<rax>(STRSAFE_LPCWSTR pszSrc@<rcx>, __int64, __int64, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180004d78`

## callees

- `0x18000163c`
- `0x180004a8c`
- `0x180004c3c`
- `0x180004d00`
- `0x180005368`
- `0x180007564`
- `0x180019ad0`
- `0x18001a3ee`
- `0x1800337d0`
- `0x1800338c0`
- `0x180033900`
- `0x180033970`
- `0x180033de4`
- `0x180033f08`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005834`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005834`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005601`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005773`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005601`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005773`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180005410`
- `api-ms-win-core-sysinfo-l1-1-0!GetComputerNameExW` at `0x180005410`
- `DNSAPI!DnsDhcpRegisterAddrs` at `0x1800055ab`
- `DNSAPI!DnsDhcpRegisterAddrs` at `0x1800055ab`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18000547c`
- `IPHLPAPI!GetCurrentThreadCompartmentId` at `0x18000547c`

## pseudocode

```c
DWORD __fastcall Dhcpv6DynDnsRegisterAdapter(
        STRSAFE_LPCWSTR pszSrc,
        __int64 a2,
        unsigned int a3,
        int a4,
        const wchar_t *a5,
        __int64 a6,
        unsigned int a7)
{
  const wchar_t *v7; // r14
  __int64 v9; // rdi
  char v12; // al
  unsigned int v13; // ebx
  char v14; // al
  int *v16; // r10
  int *v17; // r8
  int *v18; // rdx
  int *v19; // rcx
  int *v20; // rax
  unsigned int *v21; // rax
  unsigned int v22; // edx
  __int64 v23; // rcx
  __int64 v24; // rax
  __int128 v25; // xmm0
  char *v26; // rax
  __int128 v27; // xmm1
  _DWORD *v28; // rax
  unsigned int v29; // r8d
  __int64 v30; // rdx
  __int128 v31; // xmm0
  char *v32; // rax
  __int64 v33; // rcx
  __int128 v34; // xmm1
  size_t v35; // rdx
  STRSAFE_LPWSTR *v36; // r9
  __int64 v37; // rcx
  size_t *pcchRemaining; // [rsp+20h] [rbp-428h]
  DWORD v39; // [rsp+28h] [rbp-420h]
  DWORD nSize[4]; // [rsp+50h] [rbp-3F8h] BYREF
  _DWORD v41[2]; // [rsp+60h] [rbp-3E8h] BYREF
  __int64 v42; // [rsp+68h] [rbp-3E0h]
  STRSAFE_LPCWSTR v43; // [rsp+70h] [rbp-3D8h]
  WCHAR *v44; // [rsp+78h] [rbp-3D0h]
  __int64 v45; // [rsp+80h] [rbp-3C8h]
  LPVOID v46; // [rsp+88h] [rbp-3C0h]
  LPVOID lpMem; // [rsp+90h] [rbp-3B8h]
  int v48; // [rsp+98h] [rbp-3B0h]
  int v49; // [rsp+9Ch] [rbp-3ACh]
  NET_IF_COMPARTMENT_ID CurrentThreadCompartmentId; // [rsp+A8h] [rbp-3A0h]
  _OWORD v51[2]; // [rsp+B0h] [rbp-398h] BYREF
  _DWORD v52[40]; // [rsp+D0h] [rbp-378h] BYREF
  wchar_t pszDest[80]; // [rsp+170h] [rbp-2D8h] BYREF
  WCHAR Buffer[256]; // [rsp+210h] [rbp-238h] BYREF

  v7 = a5;
  v9 = a3;
  memset_0(v41, 0, 0x50u);
  memset(v51, 0, 28);
  memset_0(v52, 0, 0x140u);
  memset_0(Buffer, 0, sizeof(Buffer));
  nSize[0] = 256;
  if ( !GetComputerNameExW(ComputerNameDnsHostname, Buffer, nSize) )
    return GetLastError();
  v41[1] = 1;
  LOWORD(v51[0]) = 23;
  v44 = Buffer;
  v43 = pszSrc;
  v45 = (__int64)a5;
  if ( (_DWORD)v9 )
  {
    v28 = (_DWORD *)DhcpAlloc((v9 << 6) + 96);
    v46 = v28;
    if ( !v28 )
      return 8;
    *v28 = v9;
    v29 = 0;
    *((_DWORD *)v46 + 1) = v9;
    *((_WORD *)v46 + 6) = 23;
    v30 = 0;
    do
    {
      v31 = *(_OWORD *)(a2 + 24 * v30);
      v32 = (char *)v46;
      ++v29;
      v33 = v30++ << 6;
      *(_OWORD *)((char *)v51 + 8) = v31;
      v34 = *(_OWORD *)((char *)v51 + 12);
      *(_OWORD *)((char *)v46 + v33 + 32) = v51[0];
      *(_OWORD *)&v32[v33 + 44] = v34;
      *(_DWORD *)((char *)v46 + v33 + 64) = 28;
    }
    while ( v29 < (unsigned int)v9 );
  }
  if ( a7 )
  {
    v21 = (unsigned int *)DhcpAlloc(((unsigned __int64)a7 << 6) + 96);
    lpMem = v21;
    if ( v21 )
    {
      v22 = 0;
      *v21 = a7;
      *((_DWORD *)lpMem + 1) = a7;
      *((_WORD *)lpMem + 6) = 23;
      do
      {
        v23 = v22;
        v24 = 16 * v22++;
        v23 <<= 6;
        v25 = *(_OWORD *)(v24 + a6);
        v26 = (char *)lpMem;
        *(_OWORD *)((char *)v51 + 8) = v25;
        v27 = *(_OWORD *)((char *)v51 + 12);
        *(_OWORD *)((char *)lpMem + v23 + 32) = v51[0];
        *(_OWORD *)&v26[v23 + 44] = v27;
        *(_DWORD *)((char *)lpMem + v23 + 64) = 28;
      }
      while ( v22 < a7 );
      goto LABEL_4;
    }
    return 8;
  }
LABEL_4:
  v48 = 0;
  v49 = a4 | 0x200;
  CurrentThreadCompartmentId = GetCurrentThreadCompartmentId();
  v41[0] = 80;
  v42 = 0;
  v12 = xmmword_1800423E0;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
  {
    WPP_SF_(1028, 13, WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids);
    v12 = xmmword_1800423E0;
    if ( (xmmword_1800423E0 & 0x10) != 0 )
    {
      WPP_SF_S(1028, 14, WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids, pszSrc);
      v12 = xmmword_1800423E0;
      if ( (xmmword_1800423E0 & 0x10) != 0 )
      {
        WPP_SF_S(1028, 15, WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids, Buffer);
        v12 = xmmword_1800423E0;
        if ( (xmmword_1800423E0 & 0x10) != 0 )
        {
          if ( !a5 )
            v7 = L"[PrimaryOnly]";
          WPP_SF_S(1028, 16, WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids, v7);
          v12 = xmmword_1800423E0;
        }
      }
    }
  }
  if ( (v12 & 0x10) != 0 )
  {
    WPP_SF_d(1028, 17, WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids, (unsigned int)v9);
    if ( (xmmword_1800423E0 & 0x10) != 0 )
    {
      WPP_SF_d(1028, 18, WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids, a7);
      if ( (xmmword_1800423E0 & 0x10) != 0 )
      {
        v16 = (int *)"REG_UNKNOWN  ";
        if ( (a4 & 0x80u) == 0 )
          v16 = &dword_18003803C;
        v17 = (int *)"NO_REG  ";
        v18 = (int *)"REG_RAS ";
        if ( (a4 & 0x40) == 0 )
          v17 = &dword_18003803C;
        v19 = (int *)"REG_PTR ";
        v20 = (int *)"REG_DOMAIN ";
        if ( (a4 & 0x10) == 0 )
          v18 = &dword_18003803C;
        if ( (a4 & 8) == 0 )
          v19 = &dword_18003803C;
        if ( (a4 & 2) == 0 )
          v20 = &dword_18003803C;
        WPP_SF_ssssss(
          (_DWORD)v19,
          (_DWORD)v18,
          (_DWORD)v17,
          (unsigned int)&dword_18003803C,
          (__int64)v20,
          (__int64)v19,
          (__int64)v18,
          (__int64)v17,
          (__int64)v16);
      }
    }
  }
  v13 = DnsDhcpRegisterAddrs(v41);
  v14 = xmmword_1800423E0;
  if ( (xmmword_1800423E0 & 0x10) != 0 )
  {
    WPP_SF_D(1028, 20, WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids, v13);
    v14 = xmmword_1800423E0;
  }
  if ( v13 )
  {
    if ( (v14 & 2) != 0 )
      WPP_SF_SD(1025, 21, (unsigned int)WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids, (_DWORD)pszSrc, v13);
    InitializeTraceElementFromContext(v52, 0, v13, 45);
    StringCchCopyExW(pszDest, v35, pszSrc, v36, pcchRemaining, v39);
    TraceLogEx(v52);
    if ( (Microsoft_Windows_DHCPv6_ClientEnableBits & 1) != 0 )
      McTemplateU0zq_EtwEventWriteTransfer(v37, ErrorRegisteringDNS, pszSrc, v13);
  }
  if ( v46 )
  {
    HeapFree(NtCurrentPeb()->ProcessHeap, 0, v46);
    v46 = 0;
  }
  if ( lpMem )
    HeapFree(NtCurrentPeb()->ProcessHeap, 0, lpMem);
  return v13;
}

```

## disassembly

```asm
0x180005368  mov     [rsp+arg_8], rbx
0x18000536d  push    rsi
0x18000536e  push    rdi
0x18000536f  push    r12
0x180005371  push    r14
0x180005373  push    r15
0x180005375  sub     rsp, 420h
0x18000537c  mov     rax, cs:__security_cookie
0x180005383  xor     rax, rsp
0x180005386  mov     [rsp+448h+var_38], rax
0x18000538e  mov     r14, [rsp+448h+arg_20]
0x180005396  mov     r12, rdx
0x180005399  mov     ebx, [rsp+448h+arg_30]
0x1800053a0  xor     edx, edx; Val
0x1800053a2  mov     edi, r8d
0x1800053a5  mov     rsi, rcx
0x1800053a8  lea     rcx, [rsp+448h+var_3E8]; void *
0x1800053ad  mov     r15d, r9d
0x1800053b0  lea     r8d, [rdx+50h]; Size
0x1800053b4  call    memset_0
0x1800053b9  xorps   xmm0, xmm0
0x1800053bc  lea     rcx, [rsp+448h+var_378]; void *
0x1800053c4  movups  xmmword ptr [rsp+448h+var_398], xmm0
0x1800053cc  xor     edx, edx; Val
0x1800053ce  mov     r8d, 140h; Size
0x1800053d4  movups  xmmword ptr [rsp+448h+var_398+0Ch], xmm0
0x1800053dc  call    memset_0
0x1800053e1  xor     edx, edx; Val
0x1800053e3  lea     rcx, [rsp+448h+Buffer]; void *
0x1800053eb  mov     r8d, 200h; Size
0x1800053f1  call    memset_0
0x1800053f6  lea     r8, [rsp+448h+nSize]; nSize
0x1800053fb  mov     [rsp+448h+nSize], 100h
0x180005403  lea     rdx, [rsp+448h+Buffer]; lpBuffer
0x18000540b  mov     ecx, 1; NameType
0x180005410  call    cs:__imp_GetComputerNameExW
0x180005417  nop     dword ptr [rax+rax+00h]
0x18000541c  test    eax, eax
0x18000541e  jz      loc_180005834
0x180005424  mov     [rsp+448h+var_3E4], 1
0x18000542c  mov     eax, 17h
0x180005431  mov     word ptr [rsp+448h+var_398], ax
0x180005439  lea     rax, [rsp+448h+Buffer]
0x180005441  mov     [rsp+448h+var_3D0], rax
0x180005446  mov     [rsp+448h+var_3D8], rsi
0x18000544b  mov     [rsp+448h+var_3C8], r14
0x180005453  test    edi, edi
0x180005455  jnz     loc_180005790
0x18000545b  test    ebx, ebx
0x18000545d  jnz     loc_1800056B8
0x180005463  mov     eax, r15d
0x180005466  mov     [rsp+448h+var_3B0], 0
0x180005471  bts     eax, 9
0x180005475  mov     [rsp+448h+var_3AC], eax
0x18000547c  call    cs:__imp_GetCurrentThreadCompartmentId
0x180005483  nop     dword ptr [rax+rax+00h]
0x180005488  mov     [rsp+448h+var_3A0], eax
0x18000548f  mov     [rsp+448h+var_3E8], 50h ; 'P'
0x180005497  mov     [rsp+448h+var_3E0], 0
0x1800054a0  mov     al, byte ptr cs:xmmword_1800423E0
0x1800054a6  mov     r12d, 10h
0x1800054ac  test    r12b, al
0x1800054af  jz      loc_180005638
0x1800054b5  lea     edx, [r12-3]
0x1800054ba  mov     ecx, 404h
0x1800054bf  lea     r8, WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids
0x1800054c6  call    WPP_SF_
0x1800054cb  mov     al, byte ptr cs:xmmword_1800423E0
0x1800054d1  test    r12b, al
0x1800054d4  jz      loc_180005638
0x1800054da  lea     edx, [r12-2]
0x1800054df  mov     ecx, 404h
0x1800054e4  mov     r9, rsi
0x1800054e7  lea     r8, WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids
0x1800054ee  call    WPP_SF_S
0x1800054f3  mov     al, byte ptr cs:xmmword_1800423E0
0x1800054f9  test    r12b, al
0x1800054fc  jz      loc_180005638
0x180005502  lea     edx, [r12-1]
0x180005507  mov     ecx, 404h
0x18000550c  lea     r9, [rsp+448h+Buffer]
0x180005514  lea     r8, WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids
0x18000551b  call    WPP_SF_S
0x180005520  mov     al, byte ptr cs:xmmword_1800423E0
0x180005526  test    r12b, al
0x180005529  jz      loc_180005638
0x18000552f  test    r14, r14
0x180005532  lea     rax, aPrimaryonly; "[PrimaryOnly]"
0x180005539  mov     edx, r12d
0x18000553c  mov     ecx, 404h
0x180005541  cmovz   r14, rax
0x180005545  mov     r9, r14
0x180005548  lea     r14, WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids
0x18000554f  mov     r8, r14
0x180005552  call    WPP_SF_S
0x180005557  mov     al, byte ptr cs:xmmword_1800423E0
0x18000555d  test    r12b, al
0x180005560  jz      short loc_1800055A6
0x180005562  mov     edx, 11h
0x180005567  mov     ecx, 404h
0x18000556c  mov     r9d, edi
0x18000556f  mov     r8, r14
0x180005572  call    WPP_SF_d
0x180005577  mov     al, byte ptr cs:xmmword_1800423E0
0x18000557d  test    r12b, al
0x180005580  jz      short loc_1800055A6
0x180005582  mov     edx, 12h
0x180005587  mov     ecx, 404h
0x18000558c  mov     r9d, ebx
0x18000558f  mov     r8, r14
0x180005592  call    WPP_SF_d
0x180005597  mov     al, byte ptr cs:xmmword_1800423E0
0x18000559d  test    r12b, al
0x1800055a0  jnz     loc_180005644
0x1800055a6  lea     rcx, [rsp+448h+var_3E8]
0x1800055ab  call    cs:__imp_DnsDhcpRegisterAddrs
0x1800055b2  nop     dword ptr [rax+rax+00h]
0x1800055b7  mov     ebx, eax
0x1800055b9  mov     al, byte ptr cs:xmmword_1800423E0
0x1800055bf  test    r12b, al
0x1800055c2  jnz     loc_18000584F
0x1800055c8  test    ebx, ebx
0x1800055ca  jnz     loc_18000586F
0x1800055d0  cmp     [rsp+448h+var_3C0], 0
0x1800055d9  jnz     loc_18000575C
0x1800055df  cmp     [rsp+448h+lpMem], 0
0x1800055e8  jz      short loc_18000560D
0x1800055ea  mov     rcx, gs:60h
0x1800055f3  xor     edx, edx; dwFlags
0x1800055f5  mov     r8, [rsp+448h+lpMem]; lpMem
0x1800055fd  mov     rcx, [rcx+30h]; hHeap
0x180005601  call    cs:__imp_HeapFree
0x180005608  nop     dword ptr [rax+rax+00h]
0x18000560d  mov     eax, ebx
0x18000560f  mov     rcx, [rsp+448h+var_38]
0x180005617  xor     rcx, rsp; StackCookie
0x18000561a  call    __security_check_cookie
0x18000561f  mov     rbx, [rsp+448h+arg_8]
0x180005627  add     rsp, 420h
0x18000562e  pop     r15
0x180005630  pop     r14
0x180005632  pop     r12
0x180005634  pop     rdi
0x180005635  pop     rsi
0x180005636  retn
0x180005638  lea     r14, WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids
0x18000563f  jmp     loc_18000555D
0x180005644  test    r15b, 80h
0x180005648  lea     r9, dword_18003803C
0x18000564f  lea     r10, aRegUnknown; "REG_UNKNOWN  "
0x180005656  cmovz   r10, r9
0x18000565a  lea     r8, aNoReg; "NO_REG  "
0x180005661  test    r15b, 40h
0x180005665  mov     [rsp+448h+var_408], r10
0x18000566a  lea     rdx, aRegRas; "REG_RAS "
0x180005671  cmovz   r8, r9
0x180005675  lea     rcx, aRegPtr; "REG_PTR "
0x18000567c  test    r12b, r15b
0x18000567f  mov     [rsp+448h+var_410], r8
0x180005684  lea     rax, aRegDomain; "REG_DOMAIN "
0x18000568b  cmovz   rdx, r9
0x18000568f  test    r15b, 8
0x180005693  mov     [rsp+448h+var_418], rdx
0x180005698  cmovz   rcx, r9
0x18000569c  test    r15b, 2
0x1800056a0  mov     [rsp+448h+var_420], rcx
0x1800056a5  cmovz   rax, r9
0x1800056a9  mov     [rsp+448h+pcchRemaining], rax
0x1800056ae  call    WPP_SF_ssssss
0x1800056b3  jmp     loc_1800055A6
0x1800056b8  mov     rcx, rbx
0x1800056bb  shl     rcx, 6
0x1800056bf  add     rcx, 60h ; '`'
0x1800056c3  call    DhcpAlloc
0x1800056c8  mov     [rsp+448h+lpMem], rax
0x1800056d0  test    rax, rax
0x1800056d3  jz      loc_180005845
0x1800056d9  mov     r8, [rsp+448h+arg_28]
0x1800056e1  xor     edx, edx
0x1800056e3  mov     [rax], ebx
0x1800056e5  mov     rax, [rsp+448h+lpMem]
0x1800056ed  mov     [rax+4], ebx
0x1800056f0  mov     rax, [rsp+448h+lpMem]
0x1800056f8  mov     word ptr [rax+0Ch], 17h
0x1800056fe  test    ebx, ebx
0x180005700  jz      loc_180005463
0x180005706  mov     eax, edx
0x180005708  mov     ecx, edx
0x18000570a  shl     eax, 4
0x18000570d  inc     edx
0x18000570f  shl     rcx, 6
0x180005713  movups  xmm0, xmmword ptr [rax+r8]
0x180005718  mov     rax, [rsp+448h+lpMem]
0x180005720  movdqu  xmmword ptr [rsp+448h+var_398+8], xmm0
0x180005729  movups  xmm0, xmmword ptr [rsp+448h+var_398]
0x180005731  movups  xmm1, xmmword ptr [rsp+448h+var_398+0Ch]
0x180005739  movups  xmmword ptr [rcx+rax+20h], xmm0
0x18000573e  movups  xmmword ptr [rcx+rax+2Ch], xmm1
0x180005743  mov     rax, [rsp+448h+lpMem]
0x18000574b  mov     dword ptr [rcx+rax+40h], 1Ch
0x180005753  cmp     edx, ebx
0x180005755  jb      short loc_180005706
0x180005757  jmp     loc_180005463
0x18000575c  mov     rcx, gs:60h
0x180005765  xor     edx, edx; dwFlags
0x180005767  mov     r8, [rsp+448h+var_3C0]; lpMem
0x18000576f  mov     rcx, [rcx+30h]; hHeap
0x180005773  call    cs:__imp_HeapFree
0x18000577a  nop     dword ptr [rax+rax+00h]
0x18000577f  mov     [rsp+448h+var_3C0], 0
0x18000578b  jmp     loc_1800055DF
0x180005790  mov     rcx, rdi
0x180005793  shl     rcx, 6
0x180005797  add     rcx, 60h ; '`'
0x18000579b  call    DhcpAlloc
0x1800057a0  mov     [rsp+448h+var_3C0], rax
0x1800057a8  test    rax, rax
0x1800057ab  jz      loc_180005845
0x1800057b1  mov     [rax], edi
0x1800057b3  xor     r8d, r8d
0x1800057b6  mov     rax, [rsp+448h+var_3C0]
0x1800057be  mov     [rax+4], edi
0x1800057c1  mov     rax, [rsp+448h+var_3C0]
0x1800057c9  mov     word ptr [rax+0Ch], 17h
0x1800057cf  test    edi, edi
0x1800057d1  jz      loc_18000545B
0x1800057d7  xor     edx, edx
0x1800057d9  lea     rax, [rdx+rdx*2]
0x1800057dd  mov     rcx, rdx
0x1800057e0  movups  xmm0, xmmword ptr [r12+rax*8]
0x1800057e5  mov     rax, [rsp+448h+var_3C0]
0x1800057ed  inc     r8d
0x1800057f0  shl     rcx, 6
0x1800057f4  inc     rdx
0x1800057f7  movdqu  xmmword ptr [rsp+448h+var_398+8], xmm0
0x180005800  movups  xmm0, xmmword ptr [rsp+448h+var_398]
0x180005808  movups  xmm1, xmmword ptr [rsp+448h+var_398+0Ch]
0x180005810  movups  xmmword ptr [rcx+rax+20h], xmm0
0x180005815  movups  xmmword ptr [rcx+rax+2Ch], xmm1
0x18000581a  mov     rax, [rsp+448h+var_3C0]
0x180005822  mov     dword ptr [rcx+rax+40h], 1Ch
0x18000582a  cmp     r8d, edi
0x18000582d  jb      short loc_1800057D9
0x18000582f  jmp     loc_18000545B
0x180005834  call    cs:__imp_GetLastError
0x18000583b  nop     dword ptr [rax+rax+00h]
0x180005840  jmp     loc_18000560F
0x180005845  mov     eax, 8
0x18000584a  jmp     loc_18000560F
0x18000584f  mov     edx, 14h
0x180005854  mov     ecx, 404h
0x180005859  mov     r9d, ebx
0x18000585c  mov     r8, r14
0x18000585f  call    WPP_SF_D
0x180005864  mov     al, byte ptr cs:xmmword_1800423E0
0x18000586a  jmp     loc_1800055C8
0x18000586f  test    al, 2
0x180005871  jz      short loc_18000588C
0x180005873  mov     edx, 15h
0x180005878  mov     dword ptr [rsp+448h+pcchRemaining], ebx; pcchRemaining
0x18000587c  mov     ecx, 401h
0x180005881  mov     r9, rsi
0x180005884  mov     r8, r14
0x180005887  call    WPP_SF_SD
0x18000588c  mov     r9d, 2Dh ; '-'
0x180005892  lea     rcx, [rsp+448h+var_378]
0x18000589a  mov     r8d, ebx
0x18000589d  xor     edx, edx
0x18000589f  call    InitializeTraceElementFromContext
0x1800058a4  mov     r8, rsi; pszSrc
0x1800058a7  lea     rcx, [rsp+448h+pszDest]; pszDest
0x1800058af  call    StringCchCopyExW
0x1800058b4  lea     rcx, [rsp+448h+var_378]
0x1800058bc  call    TraceLogEx
0x1800058c1  test    byte ptr cs:Microsoft_Windows_DHCPv6_ClientEnableBits, 1
0x1800058c8  jz      loc_1800055D0
0x1800058ce  mov     r9d, ebx
0x1800058d1  lea     rdx, ErrorRegisteringDNS
0x1800058d8  mov     r8, rsi
0x1800058db  call    McTemplateU0zq_EtwEventWriteTransfer
0x1800058e0  jmp     loc_1800055D0
```
