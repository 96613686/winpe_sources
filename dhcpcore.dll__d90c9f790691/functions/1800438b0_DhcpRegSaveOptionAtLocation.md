# DhcpRegSaveOptionAtLocation

- ea: `0x1800438b0`
- end: `0x180043e26`
- name: `DhcpRegSaveOptionAtLocation`
- size: `1398`
- prototype: `LSTATUS __fastcall(__int64, const wchar_t *, DWORD, __int64, int)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x18000c65c`

## callees

- `0x1800057f0`
- `0x1800062f4`
- `0x180006440`
- `0x18000f78c`
- `0x18000f85c`
- `0x180010b44`
- `0x18001cef0`
- `0x18001d826`
- `0x1800438b0`
- `0x180047e3c`
- `0x18004d1e0`
- `0x18004d200`
- `0x18004d310`
- `0x18004d9e8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180043926`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180043926`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043a50`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043c06`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043dd0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043a50`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043c06`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043dd0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043958`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043958`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800439a8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800439a8`
- `WS2_32!__imp_inet_ntoa` at `0x180043a89`
- `WS2_32!__imp_inet_ntoa` at `0x180043a89`
- `WS2_32!__imp_ntohl` at `0x180043c6e`
- `WS2_32!__imp_ntohl` at `0x180043c6e`

## pseudocode

```c
LSTATUS __fastcall DhcpRegSaveOptionAtLocation(__int64 a1, const wchar_t *a2, DWORD a3, __int64 a4, int a5)
{
  int v7; // r14d
  wchar_t *v8; // rax
  const WCHAR *v9; // r13
  LSTATUS result; // eax
  int v11; // edi
  __int64 v12; // rdx
  LSTATUS v13; // ebx
  int v14; // r15d
  int v15; // ecx
  int v16; // ecx
  int v17; // ecx
  int v18; // ecx
  int v19; // ecx
  int *v20; // rbx
  int v21; // r14d
  int v22; // ecx
  unsigned __int64 v23; // rcx
  __int64 v24; // rax
  bool v25; // zf
  _WORD *v26; // rcx
  unsigned int v27; // edi
  char *v28; // rax
  __int64 v29; // rax
  __int64 v30; // r14
  __int64 v31; // rax
  __int64 v32; // r14
  unsigned int v33; // eax
  __int64 v34; // rax
  unsigned int v35; // edx
  int *v36; // rcx
  __int64 v37; // rax
  _WORD *v38; // rax
  int i; // eax
  int v40; // ecx
  LSTATUS v41; // eax
  DWORD v42; // ebx
  u_long *v43; // r9
  unsigned int v44; // edi
  CHAR *v45; // r15
  __int64 v46; // rcx
  __int64 v47; // rdx
  PHKEY phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int v50; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  u_long v52; // [rsp+40h] [rbp-C0h] BYREF
  LSTATUS v53; // [rsp+48h] [rbp-B8h]
  __int64 v54; // [rsp+50h] [rbp-B0h] BYREF
  _WORD *v55; // [rsp+58h] [rbp-A8h]
  CHAR MultiByteStr[512]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v57[1008]; // [rsp+260h] [rbp+160h] BYREF
  char v58; // [rsp+650h] [rbp+550h] BYREF

  hKey = 0;
  memset_0(v57, 0, 0x3EAu);
  memset_0(MultiByteStr, 0, 0x1F4u);
  v7 = *(_DWORD *)(a1 + 20);
  v52 = 0;
  v8 = wcsrchr(a2, 0x5Cu);
  v9 = v8;
  if ( v8 )
  {
    *v8 = 0;
    v9 = v8 + 1;
  }
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0xFu, &hKey);
  v53 = result;
  v11 = result;
  if ( result )
    return result;
  v12 = *(unsigned int *)(a1 + 56);
  if ( (_DWORD)v12 )
  {
    v14 = 4;
    if ( !v7 )
    {
      v15 = *(_DWORD *)(a1 + 16);
      v50 = 0;
      v54 = 0;
      v16 = v15 - 1;
      if ( v16 && (v17 = v16 - 2) != 0 && (v18 = v17 - 3) != 0 && (v19 = v18 - 38) != 0 )
      {
        if ( v19 == 2 )
        {
          if ( (_DWORD)v12 == 1 )
            v22 = **(unsigned __int8 **)(a1 + 48);
          else
            v22 = 1;
          v50 = v22;
          v20 = (int *)&v50;
          v21 = 4;
        }
        else
        {
          v20 = 0;
          v21 = 0;
        }
      }
      else
      {
        v23 = (unsigned __int64)(34 * v12) >> 2;
        if ( (unsigned int)v23 <= 0x3E8 )
        {
          v20 = (int *)&v58;
        }
        else
        {
          v24 = DhcpAlloc((unsigned int)v23);
          v54 = v24;
          if ( !v24 )
          {
            v13 = 8;
            goto LABEL_23;
          }
          v20 = (int *)v24;
        }
        v25 = (*(_DWORD *)(a1 + 56) & 0xFFFFFFFC) == 0;
        v26 = v20;
        v55 = v20;
        if ( !v25 )
        {
          v27 = 0;
          while ( 1 )
          {
            v28 = inet_ntoa(*(struct in_addr *)(*(_QWORD *)(a1 + 48) + 4LL * v27));
            v29 = DhcpOemToUnicode(v28);
            v30 = v29;
            if ( (BYTE1(xmmword_1800616A0) & 0x20) != 0 )
              WPP_SF_S(1037, 12, WPP_5602bda217e9368988f77cfae69ef51d_Traceguids, v29);
            if ( !v30 )
              break;
            v31 = -1;
            do
              ++v31;
            while ( *(_WORD *)(v30 + 2 * v31) );
            ++v27;
            v32 = v30 + 2 * v31 + 2;
            v33 = *(_DWORD *)(a1 + 56) >> 2;
            v26 = (_WORD *)v32;
            v55 = (_WORD *)v32;
            if ( v27 >= v33 )
              goto LABEL_37;
          }
          v26 = v55;
LABEL_37:
          v11 = v53;
        }
        *v26 = 0;
        v34 = -1;
        do
          ++v34;
        while ( v26[v34] );
        v21 = 2 * (((__int64)v26 + 2 * v34 - (__int64)v20) >> 1) + 2;
      }
      if ( *(_DWORD *)(a1 + 16) == 44 )
      {
        if ( !v21 )
        {
          v20 = &dword_180053FEC;
          v21 = 2;
        }
      }
      else if ( *(_DWORD *)(a1 + 16) == 6 )
      {
        v35 = 1;
        v21 -= 2;
        v50 = *(_DWORD *)(a1 + 56) >> 2;
        v36 = v20;
        if ( v50 > 1 )
        {
          do
          {
            v37 = -1;
            do
              ++v37;
            while ( *((_WORD *)v36 + v37) );
            v38 = (_WORD *)v36 + v37;
            ++v35;
            *v38 = 32;
            v36 = (int *)(v38 + 1);
          }
          while ( v35 < v50 );
        }
        if ( (BYTE1(xmmword_1800616A0) & 0x20) != 0 )
          WPP_SF_S(1037, 13, WPP_5602bda217e9368988f77cfae69ef51d_Traceguids, v20);
      }
      for ( i = 0; ; ++i )
      {
        v40 = qword_180061290[i];
        if ( !v40 )
          break;
        if ( *(_DWORD *)(a1 + 16) == v40 )
        {
          LODWORD(phkResult) = v21;
          v41 = DhcpRegSetOptionRegVal(hKey, v9, HIDWORD(qword_180061290[i]), v20, (size_t)phkResult);
          v13 = v41;
          if ( v41 && (xmmword_1800616A0 & 2) != 0 )
            WPP_SF_SD(1025, 14, (unsigned int)WPP_5602bda217e9368988f77cfae69ef51d_Traceguids, (_DWORD)v9, v41);
          RegCloseKey(hKey);
          if ( v54 )
            DhcpPunycodeFree(&v54);
          return v13;
        }
      }
    }
    v42 = a3;
    if ( a3 != 1 && a3 != 7 )
    {
      if ( a3 == 4 )
      {
        if ( *(_DWORD *)(a1 + 56) != 4 )
        {
          if ( (xmmword_1800616A0 & 2) != 0 )
            WPP_SF_(1025, 17, WPP_5602bda217e9368988f77cfae69ef51d_Traceguids);
          goto LABEL_92;
        }
        v52 = ntohl(**(_DWORD **)(a1 + 48));
        v43 = &v52;
      }
      else
      {
        v43 = *(u_long **)(a1 + 48);
        v14 = *(_DWORD *)(a1 + 56);
      }
      goto LABEL_91;
    }
    v44 = *(_DWORD *)(a1 + 56);
    if ( !v44 )
    {
      v43 = 0;
      v14 = 0;
LABEL_91:
      LODWORD(phkResult) = v14;
      v11 = DhcpRegSetOptionRegVal(hKey, v9, v42, v43, (size_t)phkResult);
LABEL_92:
      RegCloseKey(hKey);
      if ( v11 && (xmmword_1800616A0 & 2) != 0 )
        WPP_SF_SD(1025, 18, (unsigned int)WPP_5602bda217e9368988f77cfae69ef51d_Traceguids, (_DWORD)v9, v11);
      return v11;
    }
    v45 = *(CHAR **)(a1 + 48);
    if ( v44 < 0x1F4 )
    {
      if ( !v45[v44 - 1] )
      {
        if ( !v45 )
        {
          if ( (xmmword_1800616A0 & 2) != 0 )
          {
            v47 = 15;
LABEL_85:
            WPP_SF_(1025, v47, WPP_5602bda217e9368988f77cfae69ef51d_Traceguids);
          }
LABEL_86:
          v11 = 87;
          goto LABEL_92;
        }
LABEL_73:
        if ( *(_DWORD *)(a1 + 16) == 15 && a5 && !(unsigned int)ConvertPunycodeToUnicode(v45, v44) )
        {
          v44 = 501;
          v43 = (u_long *)v57;
          goto LABEL_77;
        }
        v43 = (u_long *)DhcpOemNToUnicodeN(v45);
        if ( v43 )
        {
LABEL_77:
          if ( 2 * (unsigned __int64)(v44 + 1) <= 8 && v42 == 7 )
          {
            v46 = v44++;
            *((_WORD *)v43 + v46) = 0;
          }
          v14 = 2 * v44;
          goto LABEL_91;
        }
        if ( (xmmword_1800616A0 & 2) != 0 )
        {
          v47 = 16;
          goto LABEL_85;
        }
        goto LABEL_86;
      }
    }
    else
    {
      v44 = 499;
      if ( (xmmword_1800616A0 & 2) != 0 )
        WPP_SF_(1025, 10, WPP_5602bda217e9368988f77cfae69ef51d_Traceguids);
    }
    memcpy_0(MultiByteStr, v45, v44);
    v45 = MultiByteStr;
    MultiByteStr[v44++] = 0;
    v42 = a3;
    goto LABEL_73;
  }
  if ( g_fVelocityDhcpv4InformNegativeCacheFix )
  {
    if ( (xmmword_1800616A0 & 0x10) != 0 )
      WPP_SF_d(1028, 11, WPP_5602bda217e9368988f77cfae69ef51d_Traceguids, *(unsigned int *)(a1 + 16));
  }
  v13 = RegDeleteValueW(hKey, v9);
LABEL_23:
  RegCloseKey(hKey);
  return v13;
}

```

## disassembly

```asm
0x1800438b0  mov     [rsp-8+arg_18], rbx
0x1800438b5  push    rbp
0x1800438b6  push    rsi
0x1800438b7  push    rdi
0x1800438b8  push    r12
0x1800438ba  push    r13
0x1800438bc  push    r14
0x1800438be  push    r15
0x1800438c0  lea     rbp, [rsp-950h]
0x1800438c8  sub     rsp, 0A50h
0x1800438cf  mov     rax, cs:__security_cookie
0x1800438d6  xor     rax, rsp
0x1800438d9  mov     [rbp+980h+var_40], rax
0x1800438e0  mov     [rsp+0A80h+dwType], r8d
0x1800438e5  mov     rbx, rdx
0x1800438e8  mov     rsi, rcx
0x1800438eb  xor     edi, edi
0x1800438ed  xor     edx, edx; Val
0x1800438ef  mov     [rsp+0A80h+hKey], rdi
0x1800438f4  mov     r8d, 3EAh; Size
0x1800438fa  lea     rcx, [rbp+980h+var_820]; void *
0x180043901  call    memset_0
0x180043906  xor     edx, edx; Val
0x180043908  lea     rcx, [rsp+0A80h+MultiByteStr]; void *
0x18004390d  mov     r8d, 1F4h; Size
0x180043913  call    memset_0
0x180043918  mov     r14d, [rsi+14h]
0x18004391c  lea     edx, [rdi+5Ch]; Ch
0x18004391f  mov     rcx, rbx; Str
0x180043922  mov     [rsp+0A80h+var_A40], edi
0x180043926  call    cs:__imp_wcsrchr
0x18004392c  mov     r13, rax
0x18004392f  test    rax, rax
0x180043932  jz      short loc_18004393B
0x180043934  mov     [rax], di
0x180043937  add     r13, 2
0x18004393b  lea     rax, [rsp+0A80h+hKey]
0x180043940  mov     r9d, 0Fh; samDesired
0x180043946  xor     r8d, r8d; ulOptions
0x180043949  mov     [rsp+0A80h+phkResult], rax; phkResult
0x18004394e  mov     rdx, rbx; lpSubKey
0x180043951  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180043958  call    cs:__imp_RegOpenKeyExW
0x18004395e  xor     r10d, r10d
0x180043961  mov     [rsp+0A80h+var_A38], eax
0x180043965  mov     edi, eax
0x180043967  test    eax, eax
0x180043969  jnz     loc_180043DFC
0x18004396f  mov     edx, [rsi+38h]
0x180043972  test    edx, edx
0x180043974  jnz     short loc_1800439B5
0x180043976  cmp     cs:g_fVelocityDhcpv4InformNegativeCacheFix, r10d
0x18004397d  jz      short loc_1800439A0
0x18004397f  test    byte ptr cs:xmmword_1800616A0, 10h
0x180043986  jz      short loc_1800439A0
0x180043988  mov     r9d, [rsi+10h]
0x18004398c  lea     edx, [rax+0Bh]
0x18004398f  mov     ecx, 404h
0x180043994  lea     r8, WPP_5602bda217e9368988f77cfae69ef51d_Traceguids
0x18004399b  call    WPP_SF_d
0x1800439a0  mov     rcx, [rsp+0A80h+hKey]; hKey
0x1800439a5  mov     rdx, r13; lpValueName
0x1800439a8  call    cs:__imp_RegDeleteValueW
0x1800439ae  mov     ebx, eax
0x1800439b0  jmp     loc_180043A4B
0x1800439b5  lea     r12, WPP_5602bda217e9368988f77cfae69ef51d_Traceguids
0x1800439bc  mov     r15d, 4
0x1800439c2  test    r14d, r14d
0x1800439c5  jnz     loc_180043C27
0x1800439cb  mov     ecx, [rsi+10h]
0x1800439ce  lea     r8d, [r15+1Ch]
0x1800439d2  mov     [rsp+0A80h+var_A4C], r10d
0x1800439d7  mov     [rsp+0A80h+var_A30], r10
0x1800439dc  sub     ecx, 1
0x1800439df  jz      short loc_180043A24
0x1800439e1  sub     ecx, 2
0x1800439e4  jz      short loc_180043A24
0x1800439e6  sub     ecx, 3
0x1800439e9  jz      short loc_180043A24
0x1800439eb  sub     ecx, 26h ; '&'
0x1800439ee  jz      short loc_180043A24
0x1800439f0  cmp     ecx, 2
0x1800439f3  jz      short loc_180043A00
0x1800439f5  mov     rbx, r10
0x1800439f8  mov     r14d, r10d
0x1800439fb  jmp     loc_180043B24
0x180043a00  cmp     edx, 1
0x180043a03  jnz     short loc_180043A0E
0x180043a05  mov     rax, [rsi+30h]
0x180043a09  movzx   ecx, byte ptr [rax]
0x180043a0c  jmp     short loc_180043A13
0x180043a0e  mov     ecx, 1
0x180043a13  mov     [rsp+0A80h+var_A4C], ecx
0x180043a17  lea     rbx, [rsp+0A80h+var_A4C]
0x180043a1c  mov     r14d, r15d
0x180043a1f  jmp     loc_180043B24
0x180043a24  imul    rcx, rdx, 22h ; '"'
0x180043a28  shr     rcx, 2
0x180043a2c  cmp     ecx, 3E8h
0x180043a32  jbe     short loc_180043A62
0x180043a34  mov     ecx, ecx
0x180043a36  call    DhcpAlloc
0x180043a3b  xor     r10d, r10d
0x180043a3e  mov     [rsp+0A80h+var_A30], rax
0x180043a43  test    rax, rax
0x180043a46  jnz     short loc_180043A5D
0x180043a48  lea     ebx, [rax+8]
0x180043a4b  mov     rcx, [rsp+0A80h+hKey]; hKey
0x180043a50  call    cs:__imp_RegCloseKey
0x180043a56  mov     eax, ebx
0x180043a58  jmp     loc_180043DFC
0x180043a5d  mov     rbx, rax
0x180043a60  jmp     short loc_180043A69
0x180043a62  lea     rbx, [rbp+980h+var_430]
0x180043a69  test    dword ptr [rsi+38h], 0FFFFFFFCh
0x180043a70  mov     r14, rbx
0x180043a73  mov     rcx, rbx
0x180043a76  mov     [rsp+0A80h+var_A28], rbx
0x180043a7b  jbe     short loc_180043AF8
0x180043a7d  mov     edi, r10d
0x180043a80  mov     rax, [rsi+30h]
0x180043a84  mov     ecx, edi
0x180043a86  mov     ecx, [rax+rcx*4]; in
0x180043a89  call    cs:__imp_inet_ntoa
0x180043a8f  mov     rcx, rax; SourceString
0x180043a92  mov     rdx, r14
0x180043a95  call    DhcpOemToUnicode
0x180043a9a  mov     r14, rax
0x180043a9d  test    byte ptr cs:xmmword_1800616A0+1, 20h
0x180043aa4  jz      short loc_180043ABB
0x180043aa6  mov     edx, 0Ch
0x180043aab  mov     ecx, 40Dh
0x180043ab0  mov     r9, rax
0x180043ab3  mov     r8, r12
0x180043ab6  call    WPP_SF_S
0x180043abb  xor     r10d, r10d
0x180043abe  test    r14, r14
0x180043ac1  jz      short loc_180043AEF
0x180043ac3  or      rax, 0FFFFFFFFFFFFFFFFh
0x180043ac7  inc     rax
0x180043aca  cmp     [r14+rax*2], r10w
0x180043acf  jnz     short loc_180043AC7
0x180043ad1  lea     r14, [r14+rax*2]
0x180043ad5  inc     edi
0x180043ad7  mov     eax, [rsi+38h]
0x180043ada  add     r14, 2
0x180043ade  shr     eax, 2
0x180043ae1  mov     rcx, r14
0x180043ae4  mov     [rsp+0A80h+var_A28], rcx
0x180043ae9  cmp     edi, eax
0x180043aeb  jb      short loc_180043A80
0x180043aed  jmp     short loc_180043AF4
0x180043aef  mov     rcx, [rsp+0A80h+var_A28]
0x180043af4  mov     edi, [rsp+0A80h+var_A38]
0x180043af8  mov     [rcx], r10w
0x180043afc  or      rax, 0FFFFFFFFFFFFFFFFh
0x180043b00  inc     rax
0x180043b03  cmp     [rcx+rax*2], r10w
0x180043b08  jnz     short loc_180043B00
0x180043b0a  add     rax, rax
0x180043b0d  mov     r8d, 20h ; ' '
0x180043b13  sub     rax, rbx
0x180043b16  add     rax, rcx
0x180043b19  sar     rax, 1
0x180043b1c  lea     r14d, ds:2[rax*2]
0x180043b24  cmp     dword ptr [rsi+10h], 2Ch ; ','
0x180043b28  jnz     short loc_180043B3E
0x180043b2a  test    r14d, r14d
0x180043b2d  jnz     short loc_180043BA1
0x180043b2f  lea     rbx, dword_180053FEC
0x180043b36  mov     r14d, 2
0x180043b3c  jmp     short loc_180043BA1
0x180043b3e  cmp     dword ptr [rsi+10h], 6
0x180043b42  jnz     short loc_180043BA1
0x180043b44  mov     eax, [rsi+38h]
0x180043b47  mov     edx, 1
0x180043b4c  shr     eax, 2
0x180043b4f  add     r14d, 0FFFFFFFEh
0x180043b53  mov     [rsp+0A80h+var_A4C], eax
0x180043b57  mov     rcx, rbx
0x180043b5a  cmp     eax, edx
0x180043b5c  jbe     short loc_180043B80
0x180043b5e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180043b62  inc     rax
0x180043b65  cmp     [rcx+rax*2], r10w
0x180043b6a  jnz     short loc_180043B62
0x180043b6c  lea     rax, [rcx+rax*2]
0x180043b70  inc     edx
0x180043b72  mov     [rax], r8w
0x180043b76  lea     rcx, [rax+2]
0x180043b7a  cmp     edx, [rsp+0A80h+var_A4C]
0x180043b7e  jb      short loc_180043B5E
0x180043b80  test    byte ptr cs:xmmword_1800616A0+1, r8b
0x180043b87  jz      short loc_180043BA1
0x180043b89  mov     edx, 0Dh
0x180043b8e  mov     ecx, 40Dh
0x180043b93  mov     r9, rbx
0x180043b96  mov     r8, r12
0x180043b99  call    WPP_SF_S
0x180043b9e  xor     r10d, r10d
0x180043ba1  mov     eax, r10d
0x180043ba4  lea     rdx, qword_180061290
0x180043bab  mov     r8d, eax
0x180043bae  mov     ecx, [rdx+r8*8]
0x180043bb2  test    ecx, ecx
0x180043bb4  jz      short loc_180043C27
0x180043bb6  cmp     [rsi+10h], ecx
0x180043bb9  jz      short loc_180043BBF
0x180043bbb  inc     eax
0x180043bbd  jmp     short loc_180043BAB
0x180043bbf  mov     r8d, [rdx+r8*8+4]; dwType
0x180043bc4  mov     r9, rbx; Buf2
0x180043bc7  mov     rcx, [rsp+0A80h+hKey]; hkey
0x180043bcc  mov     rdx, r13; lpValue
0x180043bcf  mov     dword ptr [rsp+0A80h+phkResult], r14d; Size
0x180043bd4  call    DhcpRegSetOptionRegVal
0x180043bd9  mov     ebx, eax
0x180043bdb  test    eax, eax
0x180043bdd  jz      short loc_180043C01
0x180043bdf  test    byte ptr cs:xmmword_1800616A0, 2
0x180043be6  jz      short loc_180043C01
0x180043be8  mov     edx, 0Eh
0x180043bed  mov     dword ptr [rsp+0A80h+phkResult], eax
0x180043bf1  mov     ecx, 401h
0x180043bf6  mov     r9, r13
0x180043bf9  mov     r8, r12
0x180043bfc  call    WPP_SF_SD
0x180043c01  mov     rcx, [rsp+0A80h+hKey]; hKey
0x180043c06  call    cs:__imp_RegCloseKey
0x180043c0c  cmp     [rsp+0A80h+var_A30], 0
0x180043c12  jz      loc_180043A56
0x180043c18  lea     rcx, [rsp+0A80h+var_A30]
0x180043c1d  call    DhcpPunycodeFree
0x180043c22  jmp     loc_180043A56
0x180043c27  mov     ebx, [rsp+0A80h+dwType]
0x180043c2b  mov     r14d, 401h
0x180043c31  cmp     ebx, 1
0x180043c34  jz      short loc_180043C8F
0x180043c36  cmp     ebx, 7
0x180043c39  jz      short loc_180043C8F
0x180043c3b  cmp     ebx, r15d
0x180043c3e  jnz     short loc_180043C82
0x180043c40  cmp     [rsi+38h], r15d
0x180043c44  jz      short loc_180043C68
0x180043c46  test    byte ptr cs:xmmword_1800616A0, 2
0x180043c4d  jz      loc_180043DCB
0x180043c53  mov     edx, 11h
0x180043c58  mov     ecx, r14d
0x180043c5b  mov     r8, r12
0x180043c5e  call    WPP_SF_
0x180043c63  jmp     loc_180043DCB
0x180043c68  mov     rcx, [rsi+30h]
0x180043c6c  mov     ecx, [rcx]; netlong
0x180043c6e  call    cs:__imp_ntohl
0x180043c74  mov     [rsp+0A80h+var_A40], eax
0x180043c78  lea     r9, [rsp+0A80h+var_A40]
0x180043c7d  jmp     loc_180043DB4
0x180043c82  mov     r9, [rsi+30h]
0x180043c86  mov     r15d, [rsi+38h]
0x180043c8a  jmp     loc_180043DB4
0x180043c8f  mov     edi, [rsi+38h]
0x180043c92  test    edi, edi
0x180043c94  jz      loc_180043DAE
0x180043c9a  mov     r15, [rsi+30h]
0x180043c9e  cmp     edi, 1F4h
0x180043ca4  jb      loc_180043D55
0x180043caa  mov     edi, 1F3h
0x180043caf  test    byte ptr cs:xmmword_1800616A0, 2
0x180043cb6  jz      short loc_180043CC8
0x180043cb8  mov     edx, 0Ah
0x180043cbd  mov     ecx, r14d
0x180043cc0  mov     r8, r12
0x180043cc3  call    WPP_SF_
0x180043cc8  mov     r8d, edi; Size
0x180043ccb  lea     rcx, [rsp+0A80h+MultiByteStr]; void *
0x180043cd0  mov     rdx, r15; Src
0x180043cd3  mov     ebx, edi
0x180043cd5  call    memcpy_0
0x180043cda  xor     r10d, r10d
0x180043cdd  lea     r15, [rsp+0A80h+MultiByteStr]
0x180043ce2  mov     [rsp+rbx+0A80h+MultiByteStr], r10b
0x180043ce7  inc     edi
0x180043ce9  mov     ebx, [rsp+0A80h+dwType]
0x180043ced  cmp     dword ptr [rsi+10h], 0Fh
0x180043cf1  jnz     loc_180043D86
0x180043cf7  cmp     [rbp+980h+arg_20], r10d
0x180043cfe  jz      loc_180043D86
0x180043d04  lea     r9, [rsp+0A80h+dwType]
0x180043d09  mov     [rsp+0A80h+dwType], 1F5h
0x180043d11  lea     r8, [rbp+980h+var_820]
0x180043d18  mov     edx, edi; cbMultiByte
0x180043d1a  mov     rcx, r15; lpMultiByteStr
0x180043d1d  call    ConvertPunycodeToUnicode
0x180043d22  test    eax, eax
0x180043d24  jnz     short loc_180043D86
0x180043d26  mov     edi, [rsp+0A80h+dwType]
0x180043d2a  lea     r9, [rbp+980h+var_820]
0x180043d31  lea     edx, [rdi+1]
0x180043d34  mov     eax, edx
0x180043d36  add     rax, rax
  ... truncated ...
```
