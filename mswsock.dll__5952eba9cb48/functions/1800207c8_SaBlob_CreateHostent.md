# SaBlob_CreateHostent

- ea: `0x1800207c8`
- end: `0x180020c37`
- name: `SaBlob_CreateHostent`
- size: `1135`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18001f4e0`
- `0x18002aa78`

## callees

- `0x180018f3c`
- `0x18001c024`
- `0x18001c120`
- `0x18001cb98`
- `0x1800207c8`
- `0x180022bd2`
- `0x180029a14`
- `0x180037195`
- `0x180038118`
- `0x18003a04c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180020ab5`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180020b68`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180020ab5`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180020b68`
- `DNSAPI!DnsNameCopy` at `0x180020ae0`
- `DNSAPI!DnsNameCopy` at `0x180020b93`
- `DNSAPI!DnsNameCopy` at `0x180020ae0`
- `DNSAPI!DnsNameCopy` at `0x180020b93`
- `DNSAPI!DnsApiAlloc` at `0x180020980`
- `DNSAPI!DnsApiAlloc` at `0x180020980`

## pseudocode

```c
unsigned __int64 __fastcall SaBlob_CreateHostent(char **a1, char **a2, char **a3, const WCHAR **a4, int a5, int a6)
{
  unsigned __int64 v6; // rsi
  unsigned int v7; // r15d
  const WCHAR *v8; // rcx
  __int64 v9; // rbx
  int v10; // r13d
  unsigned int v11; // eax
  __int64 v12; // r14
  unsigned __int64 v13; // rdi
  int v14; // r12d
  const WCHAR *v15; // rcx
  unsigned int i; // edi
  int BufferLengthForString; // eax
  __int64 v18; // rdx
  unsigned int v19; // eax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rbx
  size_t v23; // r8
  char *v24; // rdi
  unsigned int v25; // r13d
  char *v26; // r12
  char *v27; // rbx
  unsigned int v28; // edi
  size_t v29; // r15
  const WCHAR *v30; // r14
  unsigned __int64 v31; // rdi
  int IsEnabledDeviceUsageNoInline; // eax
  const WCHAR *v33; // r8
  unsigned int v34; // eax
  unsigned int v35; // r13d
  unsigned __int64 *v36; // r14
  __int64 v37; // r15
  int v38; // esi
  unsigned __int64 v39; // rdi
  int v40; // ecx
  const WCHAR *v41; // r8
  unsigned int v42; // eax
  char **v43; // rcx
  char *v44; // rax
  int v46; // [rsp+58h] [rbp-59h] BYREF
  unsigned int v47; // [rsp+5Ch] [rbp-55h]
  unsigned int v48; // [rsp+60h] [rbp-51h]
  int v49; // [rsp+64h] [rbp-4Dh]
  unsigned int Size; // [rsp+68h] [rbp-49h]
  unsigned int Size_4; // [rsp+6Ch] [rbp-45h]
  __int64 v52; // [rsp+70h] [rbp-41h]
  unsigned __int64 v53; // [rsp+80h] [rbp-31h]
  _DWORD v54[6]; // [rsp+88h] [rbp-29h]
  unsigned __int64 v55; // [rsp+A0h] [rbp-11h]
  const WCHAR *v56; // [rsp+A8h] [rbp-9h]
  size_t v57; // [rsp+B0h] [rbp-1h]
  const WCHAR **v61; // [rsp+120h] [rbp+6Fh]

  v61 = a4;
  v6 = 0;
  v53 = 0;
  v7 = 0;
  v46 = 0;
  if ( (xmmword_180063D60 & 8) != 0 )
  {
    WPP_SF_q(1027, 24, WPP_2f101c91d5a73f6393099490a21b8b8b_Traceguids, a4);
    a4 = v61;
  }
  v8 = a4[1];
  LODWORD(v9) = 32;
  v56 = v8;
  if ( v8 )
  {
    v10 = v8[16];
    v11 = *((_DWORD *)v8 + 1);
    Size_4 = v11;
    v49 = v10;
    switch ( v10 )
    {
      case 2:
        v7 = 4;
LABEL_6:
        v12 = 18;
        goto LABEL_13;
      case 23:
        v7 = 16;
        v12 = 20;
        goto LABEL_13;
      case 22:
        v7 = 28;
        goto LABEL_6;
    }
  }
  else
  {
    LOWORD(v10) = 0;
    v11 = 0;
    v49 = 0;
    Size_4 = 0;
  }
  v12 = 16;
LABEL_13:
  v13 = v7 * (unsigned __int64)v11;
  v57 = v7;
  v55 = v13;
  if ( v13 <= 0xFFFFFFFF )
  {
    v48 = *((_DWORD *)a4 + 6);
    v14 = 0;
    v47 = 0;
    LODWORD(v52) = 8 * v11 + 8;
    Size = 8 * v48 + 8;
    v15 = *a4;
    if ( *a4 )
      v14 = (DnsGetBufferLengthForString(v15) + 1) & 0xFFFFFFFE;
    if ( v48 )
    {
      for ( i = 0; i < v48; ++i )
      {
        BufferLengthForString = DnsGetBufferLengthForString(v61[i + 4]);
        LODWORD(v6) = (BufferLengthForString + v6 + 1) & 0xFFFFFFFE;
      }
      LODWORD(v13) = v55;
      LODWORD(v9) = 32;
      LOWORD(v10) = v49;
      v47 = v6;
      v6 = v53;
    }
    LODWORD(v18) = 1;
    v54[1] = Size;
    v54[2] = v52;
    v54[5] = v47;
    v54[0] = 32;
    v54[3] = v13;
    v54[4] = v14;
    while ( 1 )
    {
      v19 = v9 + v54[(unsigned int)v18];
      if ( v19 < (unsigned int)v9 )
        break;
      v18 = (unsigned int)(v18 + 1);
      v9 = v19;
      if ( (unsigned int)v18 >= 6 )
      {
        if ( (xmmword_180063D60 & 8) != 0 )
          WPP_SF_dddddd(v15, v18, v47, v19, Size, v52, v13, v14, v47);
        if ( a6 )
          v20 = DnsApiAlloc((unsigned int)v9);
        else
          v20 = FlatBuf_Ptr_Reserve(a1, a2, (unsigned int)v9, 8);
        if ( v20 )
        {
          v6 = (v20 + 3) & 0xFFFFFFFFFFFFFFFCuLL;
          v21 = v20 + v9;
          v22 = Size;
          v23 = Size;
          v52 = v21;
          v53 = v6;
          *(_QWORD *)v6 = 0;
          v24 = (char *)((v6 + 35) & 0xFFFFFFFFFFFFFFFCuLL);
          *(_WORD *)(v6 + 18) = v7;
          *(_WORD *)(v6 + 16) = v10;
          *(_QWORD *)(v6 + 8) = v24;
          memset_0(v24, 0, v23);
          v25 = Size_4;
          v26 = &v24[v22];
          *(_QWORD *)&v24[v22] = 0;
          *(_QWORD *)(v6 + 24) = &v24[v22];
          v27 = &v24[8 * v25 + 8 + v22];
          if ( v56 )
          {
            if ( v7 )
            {
              v28 = 0;
              if ( v25 )
              {
                v29 = v57;
                v30 = &v56[v12];
                do
                {
                  *(_QWORD *)v26 = v27;
                  v26 += 8;
                  memcpy_0(v27, &v30[32 * (unsigned __int64)v28], v29);
                  v27 += v29;
                  ++v28;
                }
                while ( v28 < v25 );
              }
            }
          }
          *(_QWORD *)v26 = 0;
          if ( *v61 )
          {
            v31 = (unsigned __int64)(v27 + 1) & 0xFFFFFFFFFFFFFFFEuLL;
            *(_QWORD *)v6 = v31;
            if ( (Feature_5977_1413__private_featureState & 0x10) != 0 )
              IsEnabledDeviceUsageNoInline = Feature_5977_1413__private_featureState & 1;
            else
              IsEnabledDeviceUsageNoInline = Feature_5977_1413__private_IsEnabledDeviceUsageNoInline();
            v33 = *v61;
            if ( IsEnabledDeviceUsageNoInline )
            {
              v34 = WideCharToMultiByte(
                      0,
                      0,
                      v33,
                      -1,
                      (LPSTR)((unsigned __int64)(v27 + 1) & 0xFFFFFFFFFFFFFFFEuLL),
                      v52 - v31,
                      0,
                      0);
            }
            else
            {
              v46 = v52 - v31;
              v34 = DnsNameCopy((unsigned __int64)(v27 + 1) & 0xFFFFFFFFFFFFFFFEuLL, &v46, v33, 0, 1, 3);
            }
            v27 = (char *)(v31 + v34);
          }
          v35 = v48;
          v36 = *(unsigned __int64 **)(v6 + 8);
          if ( v48 )
          {
            v37 = 0;
            v38 = v52;
            do
            {
              v39 = (unsigned __int64)(v27 + 1) & 0xFFFFFFFFFFFFFFFEuLL;
              *v36++ = v39;
              if ( (Feature_5977_1413__private_featureState & 0x10) != 0 )
                v40 = Feature_5977_1413__private_featureState & 1;
              else
                v40 = Feature_5977_1413__private_IsEnabledDeviceUsageNoInline();
              v41 = v61[v37 + 4];
              if ( v40 )
              {
                v42 = WideCharToMultiByte(
                        0,
                        0,
                        v41,
                        -1,
                        (LPSTR)((unsigned __int64)(v27 + 1) & 0xFFFFFFFFFFFFFFFEuLL),
                        v38 - v39,
                        0,
                        0);
              }
              else
              {
                v46 = v38 - v39;
                v42 = DnsNameCopy((unsigned __int64)(v27 + 1) & 0xFFFFFFFFFFFFFFFEuLL, &v46, v41, 0, 1, 3);
              }
              v37 = (unsigned int)(v37 + 1);
              v27 = (char *)(v39 + v42);
            }
            while ( (unsigned int)v37 < v35 );
            v6 = v53;
          }
          v43 = a3;
          *v36 = 0;
          if ( a3 )
            *(_DWORD *)a3 = (_DWORD)v27 - v6;
          if ( !a6 )
          {
            v43 = a1;
            v44 = *a1;
            if ( *a1 < v27 )
            {
              *a1 = v27;
              v43 = a2;
              *(_DWORD *)a2 += (_DWORD)v44 - (_DWORD)v27;
            }
          }
          Print_Hostent(v43, v6);
          if ( a5 )
            Hostent_ConvertToOffsets(v6);
        }
        break;
      }
    }
  }
  if ( (xmmword_180063D60 & 2) != 0 )
    WPP_SF_q(1025, 26, WPP_2f101c91d5a73f6393099490a21b8b8b_Traceguids, v6);
  return v6;
}

```

## disassembly

```asm
0x1800207c8  mov     rax, rsp
0x1800207cb  mov     [rax+20h], r9
0x1800207cf  mov     [rax+18h], r8
0x1800207d3  mov     [rax+10h], rdx
0x1800207d7  mov     [rax+8], rcx
0x1800207db  push    rbp
0x1800207dc  push    rbx
0x1800207dd  push    rsi
0x1800207de  push    rdi
0x1800207df  push    r12
0x1800207e1  push    r13
0x1800207e3  push    r14
0x1800207e5  push    r15
0x1800207e7  lea     rbp, [rax-4Fh]
0x1800207eb  sub     rsp, 0B8h
0x1800207f2  xor     esi, esi
0x1800207f4  mov     [rbp+47h+var_78], rsi
0x1800207f8  xor     r15d, r15d
0x1800207fb  mov     [rbp+47h+var_A0], esi
0x1800207fe  test    byte ptr cs:xmmword_180063D60, 8
0x180020805  jz      short loc_18002081F
0x180020807  lea     edx, [rsi+18h]
0x18002080a  mov     ecx, 403h
0x18002080f  lea     r8, WPP_2f101c91d5a73f6393099490a21b8b8b_Traceguids
0x180020816  call    WPP_SF_q
0x18002081b  mov     r9, [rbp+47h+arg_18]
0x18002081f  mov     rcx, [r9+8]
0x180020823  mov     ebx, 20h ; ' '
0x180020828  mov     [rbp+47h+var_50], rcx
0x18002082c  test    rcx, rcx
0x18002082f  jz      short loc_18002086E
0x180020831  movzx   r13d, word ptr [rcx+20h]
0x180020836  mov     eax, [rcx+4]
0x180020839  mov     dword ptr [rbp+47h+Size+4], eax
0x18002083c  mov     [rbp+47h+var_94], r13d
0x180020840  cmp     r13d, 2
0x180020844  jnz     short loc_180020852
0x180020846  lea     r15d, [rbx-1Ch]
0x18002084a  mov     r14d, 24h ; '$'
0x180020850  jmp     short loc_18002087D
0x180020852  cmp     r13d, 17h
0x180020856  jnz     short loc_180020862
0x180020858  lea     r15d, [r13-7]
0x18002085c  lea     r14d, [r13+11h]
0x180020860  jmp     short loc_18002087D
0x180020862  cmp     r13d, 16h
0x180020866  jnz     short loc_18002087A
0x180020868  lea     r15d, [r13+6]
0x18002086c  jmp     short loc_18002084A
0x18002086e  xor     r13d, r13d
0x180020871  xor     eax, eax
0x180020873  mov     [rbp+47h+var_94], r13d
0x180020877  mov     dword ptr [rbp+47h+Size+4], eax
0x18002087a  mov     r14, rbx
0x18002087d  mov     ecx, r15d
0x180020880  mov     edi, eax
0x180020882  imul    rdi, rcx
0x180020886  mov     [rbp+47h+var_48], rcx
0x18002088a  mov     ecx, 0FFFFFFFFh
0x18002088f  mov     [rbp+47h+var_58], rdi
0x180020893  cmp     rdi, rcx
0x180020896  ja      loc_180020BFD
0x18002089c  mov     ecx, [r9+18h]
0x1800208a0  lea     eax, ds:8[rax*8]
0x1800208a7  mov     [rbp+47h+var_98], ecx
0x1800208aa  xor     r12d, r12d
0x1800208ad  mov     [rbp+47h+var_9C], esi
0x1800208b0  mov     dword ptr [rbp+47h+var_88], eax
0x1800208b3  lea     ecx, ds:8[rcx*8]
0x1800208ba  mov     dword ptr [rbp+47h+Size], ecx
0x1800208bd  mov     rcx, [r9]; lpWideCharStr
0x1800208c0  test    rcx, rcx
0x1800208c3  jz      short loc_1800208D2
0x1800208c5  call    DnsGetBufferLengthForString
0x1800208ca  lea     r12d, [rax+1]
0x1800208ce  and     r12d, 0FFFFFFFEh
0x1800208d2  cmp     [rbp+47h+var_98], esi
0x1800208d5  jbe     short loc_18002090F
0x1800208d7  mov     rbx, [rbp+47h+arg_18]
0x1800208db  mov     edi, esi
0x1800208dd  mov     r13d, [rbp+47h+var_98]
0x1800208e1  mov     ecx, edi
0x1800208e3  mov     rcx, [rbx+rcx*8+20h]; lpWideCharStr
0x1800208e8  call    DnsGetBufferLengthForString
0x1800208ed  inc     esi
0x1800208ef  inc     edi
0x1800208f1  add     esi, eax
0x1800208f3  and     esi, 0FFFFFFFEh
0x1800208f6  cmp     edi, r13d
0x1800208f9  jb      short loc_1800208E1
0x1800208fb  mov     rdi, [rbp+47h+var_58]
0x1800208ff  mov     ebx, 20h ; ' '
0x180020904  mov     r13d, [rbp+47h+var_94]
0x180020908  mov     [rbp+47h+var_9C], esi
0x18002090b  mov     rsi, [rbp+47h+var_78]
0x18002090f  mov     r10d, dword ptr [rbp+47h+Size]
0x180020913  mov     edx, 1
0x180020918  mov     r9d, dword ptr [rbp+47h+var_88]
0x18002091c  mov     r8d, [rbp+47h+var_9C]
0x180020920  mov     [rbp+47h+var_6C], r10d
0x180020924  mov     [rbp+47h+var_68], r9d
0x180020928  mov     [rbp+47h+var_5C], r8d
0x18002092c  mov     [rbp+47h+var_70], ebx
0x18002092f  mov     [rbp+47h+var_64], edi
0x180020932  mov     [rbp+47h+var_60], r12d
0x180020936  mov     eax, edx
0x180020938  mov     eax, [rbp+rax*4+47h+var_70]
0x18002093c  add     eax, ebx
0x18002093e  cmp     eax, ebx
0x180020940  jb      loc_180020BFD
0x180020946  inc     edx
0x180020948  mov     ebx, eax
0x18002094a  cmp     edx, 6
0x18002094d  jb      short loc_180020936
0x18002094f  test    byte ptr cs:xmmword_180063D60, 8
0x180020956  jz      short loc_180020978
0x180020958  mov     [rsp+40h], r8d
0x18002095d  mov     dword ptr [rsp+0F0h+lpUsedDefaultChar], r12d
0x180020962  mov     dword ptr [rsp+0F0h+lpDefaultChar], edi
0x180020966  mov     [rsp+0F0h+cbMultiByte], r9d
0x18002096b  mov     r9d, ebx
0x18002096e  mov     dword ptr [rsp+0F0h+lpMultiByteStr], r10d
0x180020973  call    WPP_SF_dddddd
0x180020978  cmp     [rbp+47h+arg_28], 0
0x18002097c  jz      short loc_18002098E
0x18002097e  mov     ecx, ebx
0x180020980  call    cs:__imp_DnsApiAlloc
0x180020987  nop     dword ptr [rax+rax+00h]
0x18002098c  jmp     short loc_1800209A4
0x18002098e  mov     rdx, [rbp+47h+arg_8]
0x180020992  mov     r9d, 8
0x180020998  mov     rcx, [rbp+47h+arg_0]
0x18002099c  mov     r8d, ebx
0x18002099f  call    FlatBuf_Ptr_Reserve
0x1800209a4  mov     rcx, rax
0x1800209a7  test    rax, rax
0x1800209aa  jz      loc_180020BFD
0x1800209b0  lea     rsi, [rcx+3]
0x1800209b4  xor     edx, edx; Val
0x1800209b6  and     rsi, 0FFFFFFFFFFFFFFFCh
0x1800209ba  lea     rax, [rax+rbx]
0x1800209be  mov     ebx, dword ptr [rbp+47h+Size]
0x1800209c1  mov     r8d, ebx; Size
0x1800209c4  mov     [rbp+47h+var_88], rax
0x1800209c8  mov     [rbp+47h+var_78], rsi
0x1800209cc  lea     rdi, [rsi+23h]
0x1800209d0  mov     qword ptr [rsi], 0
0x1800209d7  and     rdi, 0FFFFFFFFFFFFFFFCh
0x1800209db  mov     [rsi+12h], r15w
0x1800209e0  mov     rcx, rdi; void *
0x1800209e3  mov     [rsi+10h], r13w
0x1800209e8  mov     [rsi+8], rdi
0x1800209ec  call    memset_0
0x1800209f1  mov     r13d, dword ptr [rbp+47h+Size+4]
0x1800209f5  lea     r12, [rdi+rbx]
0x1800209f9  mov     qword ptr [r12], 0
0x180020a01  mov     [rsi+18h], r12
0x180020a05  lea     eax, [r13+1]
0x180020a09  lea     rbx, [r12+rax*8]
0x180020a0d  mov     rax, [rbp+47h+var_50]
0x180020a11  test    rax, rax
0x180020a14  jz      short loc_180020A4F
0x180020a16  test    r15d, r15d
0x180020a19  jz      short loc_180020A4F
0x180020a1b  xor     edi, edi
0x180020a1d  test    r13d, r13d
0x180020a20  jz      short loc_180020A4F
0x180020a22  mov     r15, [rbp+47h+var_48]
0x180020a26  add     r14, rax
0x180020a29  mov     [r12], rbx
0x180020a2d  mov     r8, r15; Size
0x180020a30  mov     edx, edi
0x180020a32  mov     rcx, rbx; void *
0x180020a35  shl     rdx, 6
0x180020a39  add     r12, 8
0x180020a3d  add     rdx, r14; Src
0x180020a40  call    memcpy_0
0x180020a45  add     rbx, r15
0x180020a48  inc     edi
0x180020a4a  cmp     edi, r13d
0x180020a4d  jb      short loc_180020A29
0x180020a4f  mov     qword ptr [r12], 0
0x180020a57  mov     r12, [rbp+47h+arg_18]
0x180020a5b  cmp     qword ptr [r12], 0
0x180020a60  jz      loc_180020AF1
0x180020a66  lea     rdi, [rbx+1]
0x180020a6a  and     rdi, 0FFFFFFFFFFFFFFFEh
0x180020a6e  mov     [rsi], rdi
0x180020a71  mov     eax, cs:Feature_5977_1413__private_featureState
0x180020a77  test    al, 10h
0x180020a79  jz      short loc_180020A80
0x180020a7b  and     eax, 1
0x180020a7e  jmp     short loc_180020A85
0x180020a80  call    Feature_5977_1413__private_IsEnabledDeviceUsageNoInline
0x180020a85  mov     ecx, dword ptr [rbp+47h+var_88]
0x180020a88  mov     r8, [r12]; lpWideCharStr
0x180020a8c  sub     ecx, edi
0x180020a8e  test    eax, eax
0x180020a90  jz      short loc_180020AC3
0x180020a92  mov     [rsp+0F0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180020a9b  or      r9d, 0FFFFFFFFh; cchWideChar
0x180020a9f  mov     [rsp+0F0h+lpDefaultChar], 0; lpDefaultChar
0x180020aa8  xor     edx, edx; dwFlags
0x180020aaa  mov     [rsp+0F0h+cbMultiByte], ecx; cbMultiByte
0x180020aae  xor     ecx, ecx; CodePage
0x180020ab0  mov     [rsp+0F0h+lpMultiByteStr], rdi; lpMultiByteStr
0x180020ab5  call    cs:__imp_WideCharToMultiByte
0x180020abc  nop     dword ptr [rax+rax+00h]
0x180020ac1  jmp     short loc_180020AEC
0x180020ac3  mov     [rbp+47h+var_A0], ecx
0x180020ac6  lea     rdx, [rbp+47h+var_A0]
0x180020aca  mov     rcx, rdi
0x180020acd  mov     [rsp+0F0h+cbMultiByte], 3
0x180020ad5  xor     r9d, r9d
0x180020ad8  mov     dword ptr [rsp+0F0h+lpMultiByteStr], 1
0x180020ae0  call    cs:__imp_DnsNameCopy
0x180020ae7  nop     dword ptr [rax+rax+00h]
0x180020aec  mov     ebx, eax
0x180020aee  add     rbx, rdi
0x180020af1  mov     r13d, [rbp+47h+var_98]
0x180020af5  mov     r14, [rsi+8]
0x180020af9  test    r13d, r13d
0x180020afc  jz      loc_180020BB4
0x180020b02  xor     r15d, r15d
0x180020b05  test    r13d, r13d
0x180020b08  jz      loc_180020BB4
0x180020b0e  mov     rsi, [rbp+47h+var_88]
0x180020b12  lea     rdi, [rbx+1]
0x180020b16  and     rdi, 0FFFFFFFFFFFFFFFEh
0x180020b1a  mov     [r14], rdi
0x180020b1d  add     r14, 8
0x180020b21  mov     ecx, cs:Feature_5977_1413__private_featureState
0x180020b27  test    cl, 10h
0x180020b2a  jz      short loc_180020B31
0x180020b2c  and     ecx, 1
0x180020b2f  jmp     short loc_180020B38
0x180020b31  call    Feature_5977_1413__private_IsEnabledDeviceUsageNoInline
0x180020b36  mov     ecx, eax
0x180020b38  mov     r8, [r12+r15*8+20h]; lpWideCharStr
0x180020b3d  mov     edx, esi
0x180020b3f  sub     edx, edi
0x180020b41  test    ecx, ecx
0x180020b43  jz      short loc_180020B76
0x180020b45  mov     [rsp+0F0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180020b4e  or      r9d, 0FFFFFFFFh; cchWideChar
0x180020b52  mov     [rsp+0F0h+lpDefaultChar], 0; lpDefaultChar
0x180020b5b  xor     ecx, ecx; CodePage
0x180020b5d  mov     [rsp+0F0h+cbMultiByte], edx; cbMultiByte
0x180020b61  xor     edx, edx; dwFlags
0x180020b63  mov     [rsp+0F0h+lpMultiByteStr], rdi; lpMultiByteStr
0x180020b68  call    cs:__imp_WideCharToMultiByte
0x180020b6f  nop     dword ptr [rax+rax+00h]
0x180020b74  jmp     short loc_180020B9F
0x180020b76  mov     [rbp+47h+var_A0], edx
0x180020b79  xor     r9d, r9d
0x180020b7c  lea     rdx, [rbp+47h+var_A0]
0x180020b80  mov     [rsp+0F0h+cbMultiByte], 3
0x180020b88  mov     rcx, rdi
0x180020b8b  mov     dword ptr [rsp+0F0h+lpMultiByteStr], 1
0x180020b93  call    cs:__imp_DnsNameCopy
0x180020b9a  nop     dword ptr [rax+rax+00h]
0x180020b9f  mov     ebx, eax
0x180020ba1  inc     r15d
0x180020ba4  add     rbx, rdi
0x180020ba7  cmp     r15d, r13d
0x180020baa  jb      loc_180020B12
0x180020bb0  mov     rsi, [rbp+47h+var_78]
0x180020bb4  mov     rcx, [rbp+47h+arg_10]
0x180020bb8  mov     qword ptr [r14], 0
0x180020bbf  test    rcx, rcx
0x180020bc2  jz      short loc_180020BCA
0x180020bc4  mov     eax, ebx
0x180020bc6  sub     eax, esi
0x180020bc8  mov     [rcx], eax
0x180020bca  cmp     [rbp+47h+arg_28], 0
0x180020bce  jnz     short loc_180020BE7
0x180020bd0  mov     rcx, [rbp+47h+arg_0]
0x180020bd4  mov     rax, [rcx]
0x180020bd7  cmp     rax, rbx
0x180020bda  jnb     short loc_180020BE7
0x180020bdc  mov     [rcx], rbx
0x180020bdf  sub     eax, ebx
0x180020be1  mov     rcx, [rbp+47h+arg_8]
0x180020be5  add     [rcx], eax
0x180020be7  mov     rdx, rsi
0x180020bea  call    Print_Hostent
0x180020bef  cmp     [rbp+47h+arg_20], 0
0x180020bf3  jz      short loc_180020BFD
0x180020bf5  mov     rcx, rsi
0x180020bf8  call    Hostent_ConvertToOffsets
0x180020bfd  test    byte ptr cs:xmmword_180063D60, 2
0x180020c04  jz      short loc_180020C1F
0x180020c06  mov     edx, 1Ah
0x180020c0b  lea     r8, WPP_2f101c91d5a73f6393099490a21b8b8b_Traceguids
0x180020c12  mov     ecx, 401h
0x180020c17  mov     r9, rsi
0x180020c1a  call    WPP_SF_q
0x180020c1f  mov     rax, rsi
0x180020c22  add     rsp, 0B8h
0x180020c29  pop     r15
  ... truncated ...
```
