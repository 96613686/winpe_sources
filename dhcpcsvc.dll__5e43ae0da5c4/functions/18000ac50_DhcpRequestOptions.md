# DhcpRequestOptions

- ea: `0x18000ac50`
- end: `0x18000b172`
- name: `DhcpRequestOptions`
- size: `1314`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `broker_com_uri`

## callees

- `0x180002620`
- `0x180002760`
- `0x180002c50`
- `0x180003080`
- `0x18000ac50`
- `0x18000f4ec`
- `0x180010aac`
- `0x180011324`
- `0x180011374`
- `0x180011e08`
- `0x180011ec4`
- `0x180012850`
- `0x180012a00`
- `0x180012ad0`
- `0x180012d20`

## import_xrefs

- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000ad73`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000adc3`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000aded`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000ad73`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000adc3`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCommandLineW` at `0x18000aded`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000af1c`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000af3a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000af1c`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18000af3a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000b10b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000b119`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000b10b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x18000b119`
- `WS2_32!__imp_ntohl` at `0x18000ae5c`
- `WS2_32!__imp_ntohl` at `0x18000ae69`
- `WS2_32!__imp_ntohl` at `0x18000ae76`
- `WS2_32!__imp_ntohl` at `0x18000ae5c`
- `WS2_32!__imp_ntohl` at `0x18000ae69`
- `WS2_32!__imp_ntohl` at `0x18000ae76`

## pseudocode

```c
__int64 __fastcall DhcpRequestOptions(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        _QWORD *a4,
        _DWORD *a5,
        _QWORD *a6,
        unsigned int *a7)
{
  __int64 v10; // rsi
  _BYTE *v11; // r14
  _BYTE *v12; // r12
  unsigned int v13; // ebx
  int v14; // ecx
  LPWSTR CommandLineW; // rax
  int v16; // ecx
  int v17; // ecx
  int v18; // r8d
  char v19; // al
  LPWSTR v20; // rax
  int v21; // ecx
  unsigned int v22; // ebx
  unsigned int v23; // r13d
  u_long *v24; // r15
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r13
  __int64 v28; // rcx
  __int64 v29; // r8
  SIZE_T v30; // rdx
  unsigned int i; // esi
  size_t v32; // r15
  size_t v33; // r10
  _OWORD *v34; // rcx
  unsigned int uBytes; // [rsp+40h] [rbp-88h]
  SIZE_T uBytesa; // [rsp+40h] [rbp-88h]
  unsigned int v38; // [rsp+48h] [rbp-80h]
  int v39; // [rsp+48h] [rbp-80h]
  __int128 v40; // [rsp+58h] [rbp-70h] BYREF
  _QWORD v41[2]; // [rsp+68h] [rbp-60h] BYREF
  _QWORD v42[10]; // [rsp+78h] [rbp-50h] BYREF
  int v43; // [rsp+D0h] [rbp+8h]

  v43 = a1;
  v10 = a1;
  memset(v42, 0, 32);
  v40 = 0;
  v11 = 0;
  v12 = 0;
  v41[0] = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_Sqdqq(a1, a2, a3, a1, a2, a3, (char)a5, (char)a7);
  if ( (unsigned int)DhcpIsFSEGuestSystem() )
  {
    v13 = 50;
    if ( (xmmword_18001E1E0 & 2) != 0 )
      WPP_SF_d(1025, 68, WPP_e15037783097355a5233924022d92169_Traceguids, 50);
  }
  else
  {
    if ( !v10 || !a2 || !a3 || !a6 || !a7 || !a4 || !a5 )
    {
      v13 = 87;
      goto LABEL_49;
    }
    if ( a3 >= 0xFF )
    {
      v13 = 1450;
      goto LABEL_49;
    }
    *a5 = 0;
    *a7 = 0;
    *a4 = 0;
    *a6 = 0;
    LODWORD(v42[0]) = a3;
    v42[1] = a2;
    v13 = DhcpAdapterNameToIfId(v10, v41);
    if ( !v13 )
    {
      if ( (xmmword_18001E1E0 & 0x10) != 0 )
      {
        CommandLineW = GetCommandLineW();
        WPP_SF_SS(v16, 69, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, v10, (__int64)CommandLineW);
      }
      v13 = RpcCliRequestParams(v14, (unsigned int)v41, 0, 0, (__int64)v42, (__int64)&v40);
      v19 = xmmword_18001E1E0;
      if ( (xmmword_18001E1E0 & 0x10) != 0 )
      {
        v20 = GetCommandLineW();
        WPP_SF_DSS(v21, 70, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, v13, v10, (__int64)v20);
        v19 = xmmword_18001E1E0;
      }
      if ( !v13 )
      {
        if ( (v19 & 0x10) != 0 )
          WPP_SF_LS(v17, 71, v18, 0, v10);
        uBytes = 0;
        v22 = v40;
        v23 = 0;
        v38 = 0;
        v24 = (u_long *)*((_QWORD *)&v40 + 1);
        if ( (unsigned int)v40 > 0xC )
        {
          do
          {
            v22 -= 12;
            v24[2] = ntohl(v24[2]);
            *v24 = ntohl(*v24);
            v24[1] = ntohl(v24[1]);
            v27 = v24[2];
            if ( v22 < (unsigned int)v27 )
              break;
            v22 -= v27;
            if ( (unsigned int)v27 <= 0xFF )
            {
              v28 = (unsigned int)v27 + uBytes + 1;
              uBytes += v27 + 1;
              if ( (xmmword_18001E1E0 & 0x10) != 0 )
                WPP_SF_LL(v28, v25, v26, *v24, v27);
            }
            else
            {
              uBytes += 256;
              if ( (xmmword_18001E1E0 & 2) != 0 )
                WPP_SF_dd(1025, 72, WPP_e15037783097355a5233924022d92169_Traceguids, (unsigned int)v27, *v24);
            }
            ++v38;
            v24 = (u_long *)((char *)v24 + v27 + 12);
          }
          while ( v22 > 0xC );
          v23 = v38;
        }
        if ( v22 )
          goto LABEL_32;
        v12 = LocalAlloc(0x40u, v23);
        if ( v12 && (v11 = LocalAlloc(0x40u, uBytes)) != 0 )
        {
          v29 = 0;
          v13 = v40;
          v30 = *((_QWORD *)&v40 + 1);
          uBytesa = *((_QWORD *)&v40 + 1);
          if ( v23 )
          {
            for ( i = 0; i < v23; ++i )
            {
              if ( v13 <= 0xC )
                break;
              v13 -= 12;
              v32 = *(unsigned int *)(v30 + 8);
              if ( v13 < (unsigned int)v32 )
                break;
              v13 -= v32;
              v12[i] = *(_BYTE *)v30;
              v33 = (unsigned int)v32;
              v39 = v29 + 1;
              v34 = &v11[(unsigned int)(v29 + 1)];
              if ( (unsigned int)v32 <= 0xFF )
              {
                v11[v29] = v32;
                memcpy_0(v34, (const void *)(v30 + 12), v32);
                v29 = (unsigned int)(v32 + v39);
                v30 = uBytesa;
                v33 = v32;
              }
              else
              {
                v11[v29] = -1;
                *v34 = *(_OWORD *)(v30 + 12);
                v34[1] = *(_OWORD *)(v30 + 28);
                v34[2] = *(_OWORD *)(v30 + 44);
                v34[3] = *(_OWORD *)(v30 + 60);
                v34[4] = *(_OWORD *)(v30 + 76);
                v34[5] = *(_OWORD *)(v30 + 92);
                v34[6] = *(_OWORD *)(v30 + 108);
                v34[7] = *(_OWORD *)(v30 + 124);
                v34[8] = *(_OWORD *)(v30 + 140);
                v34[9] = *(_OWORD *)(v30 + 156);
                v34[10] = *(_OWORD *)(v30 + 172);
                v34[11] = *(_OWORD *)(v30 + 188);
                v34[12] = *(_OWORD *)(v30 + 204);
                v34[13] = *(_OWORD *)(v30 + 220);
                v34[14] = *(_OWORD *)(v30 + 236);
                *(_OWORD *)((char *)v34 + 239) = *(_OWORD *)(v30 + 251);
                v29 = (unsigned int)(v29 + 256);
              }
              v30 += v33 + 12;
              uBytesa = v30;
            }
            LODWORD(v10) = v43;
          }
          if ( v13 )
          {
LABEL_32:
            v13 = 1359;
            goto LABEL_49;
          }
          *a7 = v23;
          *a6 = v12;
          v12 = 0;
          *a5 = v29;
          *a4 = v11;
          v11 = 0;
        }
        else
        {
          v13 = 8;
        }
      }
    }
  }
LABEL_49:
  if ( v12 )
    LocalFree(v12);
  if ( v11 )
    LocalFree(v11);
  DhcpMidlUserFree((char *)&v40 + 8);
  LODWORD(v40) = 0;
  if ( (xmmword_18001E1E0 & 0x10) != 0 )
    WPP_SF_SD(1028, 74, (unsigned int)WPP_e15037783097355a5233924022d92169_Traceguids, v10, v13);
  return v13;
}

```

## disassembly

```asm
0x18000ac50  mov     rax, rsp
0x18000ac53  mov     [rax+10h], rbx
0x18000ac57  mov     [rax+20h], r9
0x18000ac5b  mov     [rax+8], rcx
0x18000ac5f  push    rsi
0x18000ac60  push    r12
0x18000ac62  push    r13
0x18000ac64  push    r14
0x18000ac66  push    r15
0x18000ac68  sub     rsp, 0A0h
0x18000ac6f  mov     r13, r9
0x18000ac72  mov     ebx, r8d
0x18000ac75  mov     r15, rdx
0x18000ac78  mov     rsi, rcx
0x18000ac7b  xorps   xmm0, xmm0
0x18000ac7e  movups  xmmword ptr [rax-50h], xmm0
0x18000ac82  movups  xmmword ptr [rax-40h], xmm0
0x18000ac86  movups  xmmword ptr [rax-70h], xmm0
0x18000ac8a  xor     r14d, r14d
0x18000ac8d  mov     [rsp+0C8h+var_80], r14
0x18000ac92  xor     r12d, r12d
0x18000ac95  mov     [rax-60h], r12
0x18000ac99  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000aca0  jz      short loc_18000ACCD
0x18000aca2  mov     rax, [rsp+0C8h+arg_30]
0x18000acaa  mov     [rsp+0C8h+var_90], rax
0x18000acaf  mov     rax, [rsp+0C8h+arg_20]
0x18000acb7  mov     [rsp+0C8h+var_98], rax
0x18000acbc  mov     dword ptr [rsp+0C8h+var_A0], ebx
0x18000acc0  mov     [rsp+0C8h+var_A8], rdx
0x18000acc5  mov     r9, rcx
0x18000acc8  call    WPP_SF_Sqdqq
0x18000accd  call    DhcpIsFSEGuestSystem
0x18000acd2  test    eax, eax
0x18000acd4  jnz     loc_18000B0DE
0x18000acda  test    rsi, rsi
0x18000acdd  jnz     short loc_18000ACE9
0x18000acdf  mov     ebx, 57h ; 'W'
0x18000ace4  jmp     loc_18000B103
0x18000ace9  test    r15, r15
0x18000acec  jz      short loc_18000ACDF
0x18000acee  test    ebx, ebx
0x18000acf0  jz      short loc_18000ACDF
0x18000acf2  mov     rcx, [rsp+0C8h+arg_28]
0x18000acfa  test    rcx, rcx
0x18000acfd  jz      short loc_18000ACDF
0x18000acff  cmp     [rsp+0C8h+arg_30], r12
0x18000ad07  jbe     short loc_18000ACDF
0x18000ad09  test    r13, r13
0x18000ad0c  jz      short loc_18000ACDF
0x18000ad0e  cmp     [rsp+0C8h+arg_20], r12
0x18000ad16  jbe     short loc_18000ACDF
0x18000ad18  cmp     ebx, 0FFh
0x18000ad1e  jb      short loc_18000AD2A
0x18000ad20  mov     ebx, 5AAh
0x18000ad25  jmp     loc_18000B103
0x18000ad2a  mov     rax, [rsp+0C8h+arg_20]
0x18000ad32  mov     [rax], r12d
0x18000ad35  mov     rax, [rsp+0C8h+arg_30]
0x18000ad3d  mov     [rax], r12d
0x18000ad40  mov     [r13+0], r12
0x18000ad44  mov     [rcx], r12
0x18000ad47  mov     [rsp+0C8h+var_50], ebx
0x18000ad4b  mov     [rsp+0C8h+var_48], r15
0x18000ad53  lea     rdx, [rsp+0C8h+var_60]
0x18000ad58  mov     rcx, rsi
0x18000ad5b  call    DhcpAdapterNameToIfId
0x18000ad60  mov     ebx, eax
0x18000ad62  test    eax, eax
0x18000ad64  jnz     loc_18000B103
0x18000ad6a  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000ad71  jz      short loc_18000AD91
0x18000ad73  call    cs:__imp_GetCommandLineW
0x18000ad79  lea     edx, [rbx+45h]
0x18000ad7c  mov     [rsp+0C8h+var_A8], rax
0x18000ad81  mov     r9, rsi
0x18000ad84  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000ad8b  call    WPP_SF_SS
0x18000ad90  nop
0x18000ad91  lea     rax, [rsp+0C8h+var_70]
0x18000ad96  mov     [rsp+0C8h+var_A0], rax
0x18000ad9b  lea     rax, [rsp+0C8h+var_50]
0x18000ada0  mov     [rsp+0C8h+var_A8], rax
0x18000ada5  xor     r9d, r9d
0x18000ada8  xor     r8d, r8d
0x18000adab  lea     rdx, [rsp+0C8h+var_60]
0x18000adb0  call    RpcCliRequestParams
0x18000adb5  mov     ebx, eax
0x18000adb7  mov     [rsp+0C8h+var_78], eax
0x18000adbb  jmp     short loc_18000ADE3
0x18000adbd  mov     ebx, eax
0x18000adbf  mov     [rsp+0C8h+var_78], eax
0x18000adc3  call    cs:__imp_GetCommandLineW
0x18000adc9  mov     rdx, rax
0x18000adcc  mov     ecx, ebx
0x18000adce  call    TraceRpcException
0x18000add3  mov     rsi, [rsp+0C8h+arg_0]
0x18000addb  mov     r14, [rsp+0C8h+var_80]
0x18000ade0  mov     r12, r14
0x18000ade3  mov     al, byte ptr cs:xmmword_18001E1E0
0x18000ade9  test    al, 10h
0x18000adeb  jz      short loc_18000AE17
0x18000aded  call    cs:__imp_GetCommandLineW
0x18000adf3  mov     edx, 46h ; 'F'
0x18000adf8  mov     [rsp+0C8h+var_A0], rax
0x18000adfd  mov     [rsp+0C8h+var_A8], rsi
0x18000ae02  mov     r9d, ebx
0x18000ae05  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000ae0c  call    WPP_SF_DSS
0x18000ae11  mov     al, byte ptr cs:xmmword_18001E1E0
0x18000ae17  test    ebx, ebx
0x18000ae19  jnz     loc_18000B103
0x18000ae1f  test    al, 10h
0x18000ae21  jz      short loc_18000AE33
0x18000ae23  lea     edx, [rbx+47h]
0x18000ae26  mov     [rsp+0C8h+var_A8], rsi
0x18000ae2b  xor     r9d, r9d
0x18000ae2e  call    WPP_SF_LS
0x18000ae33  mov     dword ptr [rsp+0C8h+uBytes], 0
0x18000ae3b  mov     ebx, [rsp+0C8h+var_70]
0x18000ae3f  xor     r13d, r13d
0x18000ae42  mov     dword ptr [rsp+0C8h+var_80], r13d
0x18000ae47  mov     r15, [rsp+0C8h+var_68]
0x18000ae4c  cmp     ebx, 0Ch
0x18000ae4f  jbe     loc_18000AF04
0x18000ae55  add     ebx, 0FFFFFFF4h
0x18000ae58  mov     ecx, [r15+8]; netlong
0x18000ae5c  call    cs:__imp_ntohl
0x18000ae62  mov     [r15+8], eax
0x18000ae66  mov     ecx, [r15]; netlong
0x18000ae69  call    cs:__imp_ntohl
0x18000ae6f  mov     [r15], eax
0x18000ae72  mov     ecx, [r15+4]; netlong
0x18000ae76  call    cs:__imp_ntohl
0x18000ae7c  mov     [r15+4], eax
0x18000ae80  mov     r13d, [r15+8]
0x18000ae84  cmp     ebx, r13d
0x18000ae87  jb      short loc_18000AEFF
0x18000ae89  sub     ebx, r13d
0x18000ae8c  cmp     r13d, 0FFh
0x18000ae93  jbe     short loc_18000AEC8
0x18000ae95  add     dword ptr [rsp+0C8h+uBytes], 100h
0x18000ae9d  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000aea4  jz      short loc_18000AEEB
0x18000aea6  mov     edx, 48h ; 'H'
0x18000aeab  mov     ecx, 401h
0x18000aeb0  mov     eax, [r15]
0x18000aeb3  mov     dword ptr [rsp+0C8h+var_A8], eax
0x18000aeb7  mov     r9d, r13d
0x18000aeba  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000aec1  call    WPP_SF_dd
0x18000aec6  jmp     short loc_18000AEEB
0x18000aec8  mov     ecx, dword ptr [rsp+0C8h+uBytes]
0x18000aecc  inc     ecx
0x18000aece  add     ecx, r13d
0x18000aed1  mov     dword ptr [rsp+0C8h+uBytes], ecx
0x18000aed5  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000aedc  jz      short loc_18000AEEB
0x18000aede  mov     dword ptr [rsp+0C8h+var_A8], r13d
0x18000aee3  mov     r9d, [r15]
0x18000aee6  call    WPP_SF_LL
0x18000aeeb  inc     dword ptr [rsp+0C8h+var_80]
0x18000aeef  add     r15, 0Ch
0x18000aef3  add     r15, r13
0x18000aef6  cmp     ebx, 0Ch
0x18000aef9  ja      loc_18000AE55
0x18000aeff  mov     r13d, dword ptr [rsp+0C8h+var_80]
0x18000af04  test    ebx, ebx
0x18000af06  jz      short loc_18000AF12
0x18000af08  mov     ebx, 54Fh
0x18000af0d  jmp     loc_18000B103
0x18000af12  mov     edx, r13d; uBytes
0x18000af15  mov     ebx, 40h ; '@'
0x18000af1a  mov     ecx, ebx; uFlags
0x18000af1c  call    cs:__imp_LocalAlloc
0x18000af22  mov     r12, rax
0x18000af25  test    rax, rax
0x18000af28  jnz     short loc_18000AF34
0x18000af2a  mov     ebx, 8
0x18000af2f  jmp     loc_18000B103
0x18000af34  mov     edx, dword ptr [rsp+0C8h+uBytes]; uBytes
0x18000af38  mov     ecx, ebx; uFlags
0x18000af3a  call    cs:__imp_LocalAlloc
0x18000af40  mov     r14, rax
0x18000af43  test    rax, rax
0x18000af46  jz      short loc_18000AF2A
0x18000af48  xor     r8d, r8d
0x18000af4b  mov     ebx, [rsp+0C8h+var_70]
0x18000af4f  mov     rdx, [rsp+0C8h+var_68]
0x18000af54  mov     [rsp+0C8h+uBytes], rdx
0x18000af59  test    r13d, r13d
0x18000af5c  jz      loc_18000B0A2
0x18000af62  mov     esi, r8d
0x18000af65  cmp     ebx, 0Ch
0x18000af68  jbe     loc_18000B09A
0x18000af6e  add     ebx, 0FFFFFFF4h
0x18000af71  mov     r15d, [rdx+8]
0x18000af75  cmp     ebx, r15d
0x18000af78  jb      loc_18000B09A
0x18000af7e  sub     ebx, r15d
0x18000af81  mov     ecx, esi
0x18000af83  mov     al, [rdx]
0x18000af85  mov     [rcx+r12], al
0x18000af89  mov     r10d, r15d
0x18000af8c  lea     eax, [r8+1]
0x18000af90  mov     dword ptr [rsp+0C8h+var_80], eax
0x18000af94  mov     ecx, eax
0x18000af96  add     rcx, r14; void *
0x18000af99  cmp     r15d, 0FFh
0x18000afa0  jbe     loc_18000B063
0x18000afa6  mov     byte ptr [r8+r14], 0FFh
0x18000afab  movups  xmm0, xmmword ptr [rdx+0Ch]
0x18000afaf  movups  xmmword ptr [rcx], xmm0
0x18000afb2  movups  xmm1, xmmword ptr [rdx+1Ch]
0x18000afb6  movups  xmmword ptr [rcx+10h], xmm1
0x18000afba  movups  xmm0, xmmword ptr [rdx+2Ch]
0x18000afbe  movups  xmmword ptr [rcx+20h], xmm0
0x18000afc2  movups  xmm1, xmmword ptr [rdx+3Ch]
0x18000afc6  movups  xmmword ptr [rcx+30h], xmm1
0x18000afca  movups  xmm0, xmmword ptr [rdx+4Ch]
0x18000afce  movups  xmmword ptr [rcx+40h], xmm0
0x18000afd2  movups  xmm1, xmmword ptr [rdx+5Ch]
0x18000afd6  movups  xmmword ptr [rcx+50h], xmm1
0x18000afda  movups  xmm0, xmmword ptr [rdx+6Ch]
0x18000afde  movups  xmmword ptr [rcx+60h], xmm0
0x18000afe2  movups  xmm1, xmmword ptr [rdx+7Ch]
0x18000afe6  movups  xmmword ptr [rcx+70h], xmm1
0x18000afea  movups  xmm0, xmmword ptr [rdx+8Ch]
0x18000aff1  movups  xmmword ptr [rcx+80h], xmm0
0x18000aff8  movups  xmm1, xmmword ptr [rdx+9Ch]
0x18000afff  movups  xmmword ptr [rcx+90h], xmm1
0x18000b006  movups  xmm0, xmmword ptr [rdx+0ACh]
0x18000b00d  movups  xmmword ptr [rcx+0A0h], xmm0
0x18000b014  movups  xmm1, xmmword ptr [rdx+0BCh]
0x18000b01b  movups  xmmword ptr [rcx+0B0h], xmm1
0x18000b022  movups  xmm0, xmmword ptr [rdx+0CCh]
0x18000b029  movups  xmmword ptr [rcx+0C0h], xmm0
0x18000b030  movups  xmm1, xmmword ptr [rdx+0DCh]
0x18000b037  movups  xmmword ptr [rcx+0D0h], xmm1
0x18000b03e  movups  xmm0, xmmword ptr [rdx+0ECh]
0x18000b045  movups  xmmword ptr [rcx+0E0h], xmm0
0x18000b04c  movups  xmm1, xmmword ptr [rdx+0FBh]
0x18000b053  movups  xmmword ptr [rcx+0EFh], xmm1
0x18000b05a  add     r8d, 100h
0x18000b061  jmp     short loc_18000B083
0x18000b063  mov     [r8+r14], r15b
0x18000b067  mov     r8, r15; Size
0x18000b06a  add     rdx, 0Ch; Src
0x18000b06e  call    memcpy_0
0x18000b073  mov     r8d, dword ptr [rsp+0C8h+var_80]
0x18000b078  add     r8d, r15d
0x18000b07b  mov     rdx, [rsp+0C8h+uBytes]
0x18000b080  mov     r10, r15
0x18000b083  add     rdx, 0Ch
0x18000b087  add     rdx, r10
0x18000b08a  mov     [rsp+0C8h+uBytes], rdx
0x18000b08f  inc     esi
0x18000b091  cmp     esi, r13d
0x18000b094  jb      loc_18000AF65
0x18000b09a  mov     rsi, [rsp+0C8h+arg_0]
0x18000b0a2  test    ebx, ebx
0x18000b0a4  jnz     loc_18000AF08
0x18000b0aa  mov     rax, [rsp+0C8h+arg_30]
0x18000b0b2  mov     [rax], r13d
0x18000b0b5  mov     rax, [rsp+0C8h+arg_28]
0x18000b0bd  mov     [rax], r12
0x18000b0c0  xor     r12d, r12d
0x18000b0c3  mov     rax, [rsp+0C8h+arg_20]
0x18000b0cb  mov     [rax], r8d
0x18000b0ce  mov     rax, [rsp+0C8h+arg_18]
0x18000b0d6  mov     [rax], r14
0x18000b0d9  xor     r14d, r14d
0x18000b0dc  jmp     short loc_18000B103
0x18000b0de  mov     ebx, 32h ; '2'
0x18000b0e3  test    byte ptr cs:xmmword_18001E1E0, 2
0x18000b0ea  jz      short loc_18000B103
0x18000b0ec  lea     edx, [rbx+12h]
0x18000b0ef  mov     ecx, 401h
0x18000b0f4  mov     r9d, ebx
0x18000b0f7  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000b0fe  call    WPP_SF_d
0x18000b103  test    r12, r12
0x18000b106  jz      short loc_18000B111
0x18000b108  mov     rcx, r12; hMem
0x18000b10b  call    cs:__imp_LocalFree
0x18000b111  test    r14, r14
0x18000b114  jz      short loc_18000B11F
0x18000b116  mov     rcx, r14; hMem
0x18000b119  call    cs:__imp_LocalFree
0x18000b11f  lea     rcx, [rsp+0C8h+var_68]
0x18000b124  call    DhcpMidlUserFree
0x18000b129  mov     [rsp+0C8h+var_70], 0
0x18000b131  test    byte ptr cs:xmmword_18001E1E0, 10h
0x18000b138  jz      short loc_18000B157
0x18000b13a  mov     edx, 4Ah ; 'J'
0x18000b13f  mov     ecx, 404h
0x18000b144  mov     dword ptr [rsp+0C8h+var_A8], ebx
0x18000b148  mov     r9, rsi
0x18000b14b  lea     r8, WPP_e15037783097355a5233924022d92169_Traceguids
0x18000b152  call    WPP_SF_SD
  ... truncated ...
```
