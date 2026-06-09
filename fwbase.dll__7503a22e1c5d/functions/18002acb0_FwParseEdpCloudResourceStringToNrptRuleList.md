# FwParseEdpCloudResourceStringToNrptRuleList

- ea: `0x18002acb0`
- end: `0x18002b113`
- name: `FwParseEdpCloudResourceStringToNrptRuleList`
- size: `1123`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180002c10`
- `0x1800045f0`
- `0x180004840`
- `0x180004870`
- `0x18000ccd4`
- `0x1800113d0`
- `0x18001e1d0`
- `0x18001eb54`
- `0x18002acb0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18002ad8e`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18002addd`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18002adf3`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18002ad8e`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18002addd`
- `api-ms-win-crt-private-l1-1-0!_o_wcstok_s` at `0x18002adf3`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002aead`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002aead`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002aed0`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x18002aed0`

## pseudocode

```c
__int64 __fastcall FwParseEdpCloudResourceStringToNrptRuleList(void *Src, wchar_t *a2, _QWORD *a3, _DWORD *a4)
{
  _QWORD *v4; // r12
  unsigned int v8; // eax
  unsigned int v9; // eax
  unsigned int v10; // edi
  _QWORD *v11; // rsi
  int i; // r13d
  wchar_t *v13; // rbx
  int v14; // eax
  wchar_t *v15; // r15
  wchar_t *v16; // rax
  __int64 v17; // rdx
  wchar_t *v18; // r14
  __int64 v19; // rax
  __int64 v20; // rbx
  unsigned int v21; // eax
  unsigned int v22; // eax
  wchar_t *v23; // rcx
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  __int64 v27; // rax
  __int64 v28; // rcx
  __int64 v29; // rax
  _QWORD *v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // r9
  _QWORD *v33; // rbx
  wchar_t *Context; // [rsp+48h] [rbp-71h] BYREF
  wchar_t *v39; // [rsp+50h] [rbp-69h] BYREF
  GUID pguid; // [rsp+58h] [rbp-61h] BYREF
  OLECHAR sz[40]; // [rsp+70h] [rbp-49h] BYREF

  v4 = 0;
  Context = 0;
  v39 = 0;
  pguid = 0;
  memset_0(sz, 0, 0x4Eu);
  *a3 = 0;
  *a4 = 0;
  v8 = FwStringCopy(Src);
  v9 = FwHResultToWindowsError(v8);
  v10 = v9;
  if ( v9 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_7f5bde6595ff3eb51821de83b63f4275_Traceguids, v9);
    goto LABEL_59;
  }
  v11 = 0;
  for ( i = 0; ; ++i )
  {
    do
    {
      while ( 1 )
      {
        v13 = wcstok_s(0, Delimiter, &Context);
        if ( !v13 )
        {
          *a3 = v11;
          *a4 = i;
          goto LABEL_59;
        }
        FwFree(0);
        v14 = FwStringCopy(v13);
        if ( v14 < 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              23,
              WPP_7f5bde6595ff3eb51821de83b63f4275_Traceguids,
              (unsigned int)v14);
          goto LABEL_55;
        }
        v15 = wcstok_s(0, L",", &v39);
        v16 = wcstok_s(0, L",", &v39);
        v18 = v16;
        if ( !v15 )
        {
          v10 = 87;
          v30 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
            goto LABEL_55;
          v31 = 24;
          v32 = 87;
          goto LABEL_51;
        }
        if ( v16 )
          break;
        if ( a2 )
          goto LABEL_13;
      }
    }
    while ( a2 );
LABEL_13:
    v19 = FwAlloc(64, v17);
    v20 = v19;
    if ( !v19 )
    {
      v32 = 8;
      v10 = 8;
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_55;
      v31 = 25;
      goto LABEL_51;
    }
    if ( v11 )
      *v4 = v19;
    else
      v11 = (_QWORD *)v19;
    *(_OWORD *)(v19 + 8) = 0;
    *(_OWORD *)(v19 + 24) = 0;
    v4 = (_QWORD *)v19;
    *(_OWORD *)(v19 + 40) = 0;
    *(_QWORD *)(v19 + 56) = 0;
    *(_DWORD *)(v19 + 8) = 2;
    v21 = FwStringCopy(v15);
    v22 = FwHResultToWindowsError(v21);
    v10 = v22;
    if ( v22 )
    {
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_55;
      v31 = 26;
LABEL_44:
      v32 = v22;
      goto LABEL_51;
    }
    v23 = a2;
    if ( v18 )
      v23 = v18;
    v24 = FwStringCopy(v23);
    v22 = FwHResultToWindowsError(v24);
    v10 = v22;
    if ( v22 )
      break;
    v25 = CoCreateGuid(&pguid);
    v22 = FwHResultToWindowsError(v25);
    v10 = v22;
    if ( v22 )
    {
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v31 = 28;
        goto LABEL_44;
      }
      goto LABEL_55;
    }
    if ( !StringFromGUID2(&pguid, sz, 39) )
    {
      v32 = 8;
      v10 = 8;
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_55;
      v31 = 29;
LABEL_51:
      WPP_SF_d(v30[2], v31, WPP_7f5bde6595ff3eb51821de83b63f4275_Traceguids, v32);
      goto LABEL_55;
    }
    v26 = FwStringBuild(v20 + 48, L"EDP_", sz, 0);
    v22 = FwHResultToWindowsError(v26);
    v10 = v22;
    if ( v22 )
    {
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v31 = 30;
        goto LABEL_44;
      }
      goto LABEL_55;
    }
    v27 = -1;
    do
      ++v27;
    while ( *(_WORD *)(*(_QWORD *)(v20 + 40) + 2 * v27) );
    v28 = *(_QWORD *)(v20 + 56);
    *(_DWORD *)(v20 + 16) = v27 + 1;
    v29 = -1;
    do
      ++v29;
    while ( *(_WORD *)(v28 + 2 * v29) );
    *(_DWORD *)(v20 + 20) = v29 + 1;
  }
  v30 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v31 = 27;
    goto LABEL_44;
  }
LABEL_55:
  if ( v11 )
  {
    do
    {
      FwFree(v11[5]);
      FwFree(v11[7]);
      v33 = (_QWORD *)*v11;
      FwFree(v11);
      v11 = v33;
    }
    while ( v33 );
  }
LABEL_59:
  FwFree(0);
  FwFree(0);
  return v10;
}

```

## disassembly

```asm
0x18002acb0  push    rbp
0x18002acb2  push    rbx
0x18002acb3  push    rsi
0x18002acb4  push    rdi
0x18002acb5  push    r12
0x18002acb7  push    r13
0x18002acb9  push    r14
0x18002acbb  push    r15
0x18002acbd  lea     rbp, [rsp-1Fh]
0x18002acc2  sub     rsp, 0D8h
0x18002acc9  mov     rax, cs:__security_cookie
0x18002acd0  xor     rax, rsp
0x18002acd3  mov     [rbp+57h+var_50], rax
0x18002acd7  xor     r12d, r12d
0x18002acda  mov     [rsp+110h+var_D8], r8
0x18002acdf  mov     r14, r8
0x18002ace2  mov     [rsp+110h+var_E8], rdx
0x18002ace7  mov     rbx, rcx
0x18002acea  mov     [rbp+57h+var_D0], r9
0x18002acee  xorps   xmm0, xmm0
0x18002acf1  mov     [rsp+110h+String], r12
0x18002acf6  lea     r8d, [r12+4Eh]; Size
0x18002acfb  mov     [rsp+110h+var_F0], r12
0x18002ad00  xor     edx, edx; Val
0x18002ad02  mov     [rbp+57h+Context], r12
0x18002ad06  lea     rcx, [rbp+57h+sz]; void *
0x18002ad0a  mov     [rbp+57h+var_C0], r12
0x18002ad0e  mov     r15, r9
0x18002ad11  movups  xmmword ptr [rbp+57h+pguid.Data1], xmm0
0x18002ad15  call    memset_0
0x18002ad1a  mov     [r14], r12
0x18002ad1d  lea     rdx, [rsp+110h+String]
0x18002ad22  mov     rcx, rbx; Src
0x18002ad25  mov     [r15], r12d
0x18002ad28  call    FwStringCopy
0x18002ad2d  mov     ecx, eax
0x18002ad2f  call    FwHResultToWindowsError
0x18002ad34  mov     edi, eax
0x18002ad36  test    eax, eax
0x18002ad38  jz      short loc_18002AD78
0x18002ad3a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002ad41  lea     rdx, WPP_GLOBAL_Control
0x18002ad48  cmp     rcx, rdx
0x18002ad4b  jz      loc_18002B0DD
0x18002ad51  test    byte ptr [rcx+1Ch], 1
0x18002ad55  jz      loc_18002B0DD
0x18002ad5b  mov     rcx, [rcx+10h]
0x18002ad5f  lea     edx, [r12+16h]
0x18002ad64  mov     r9d, eax
0x18002ad67  lea     r8, WPP_7f5bde6595ff3eb51821de83b63f4275_Traceguids
0x18002ad6e  call    WPP_SF_d
0x18002ad73  jmp     loc_18002B0DD
0x18002ad78  mov     rcx, [rsp+110h+String]; String
0x18002ad7d  mov     rsi, r12
0x18002ad80  mov     r13d, r12d
0x18002ad83  lea     rdx, Delimiter; Delimiter
0x18002ad8a  lea     r8, [rbp+57h+Context]; Context
0x18002ad8e  call    cs:__imp_wcstok_s
0x18002ad94  mov     rbx, rax
0x18002ad97  test    rax, rax
0x18002ad9a  jz      loc_18002B0CE
0x18002ada0  mov     rcx, [rsp+110h+var_F0]
0x18002ada5  call    FwFree
0x18002adaa  lea     rdx, [rsp+110h+var_F0]
0x18002adaf  mov     [rsp+110h+var_F0], 0
0x18002adb8  mov     rcx, rbx; Src
0x18002adbb  call    FwStringCopy
0x18002adc0  mov     rcx, [rsp+110h+var_F0]; String
0x18002adc5  mov     [rsp+110h+var_F0], rcx
0x18002adca  test    eax, eax
0x18002adcc  js      loc_18002B071
0x18002add2  lea     r8, [rbp+57h+var_C0]; Context
0x18002add6  lea     rdx, asc_1800347D4; ","
0x18002addd  call    cs:__imp_wcstok_s
0x18002ade3  lea     r8, [rbp+57h+var_C0]; Context
0x18002ade7  xor     ecx, ecx; String
0x18002ade9  lea     rdx, asc_1800347D4; ","
0x18002adf0  mov     r15, rax
0x18002adf3  call    cs:__imp_wcstok_s
0x18002adf9  xor     ecx, ecx
0x18002adfb  mov     r14, rax
0x18002adfe  test    r15, r15
0x18002ae01  jz      loc_18002B03B
0x18002ae07  test    rax, rax
0x18002ae0a  jnz     short loc_18002AE18
0x18002ae0c  cmp     [rsp+110h+var_E8], rcx
0x18002ae11  jnz     short loc_18002AE23
0x18002ae13  jmp     loc_18002AD83
0x18002ae18  cmp     [rsp+110h+var_E8], rcx
0x18002ae1d  jnz     loc_18002AD83
0x18002ae23  mov     ecx, 40h ; '@'
0x18002ae28  call    FwAlloc
0x18002ae2d  mov     rbx, rax
0x18002ae30  test    rax, rax
0x18002ae33  jz      loc_18002B013
0x18002ae39  test    rsi, rsi
0x18002ae3c  jnz     short loc_18002AE43
0x18002ae3e  mov     rsi, rax
0x18002ae41  jmp     short loc_18002AE47
0x18002ae43  mov     [r12], rbx
0x18002ae47  xorps   xmm0, xmm0
0x18002ae4a  lea     rdx, [rbx+28h]
0x18002ae4e  movups  xmmword ptr [rbx+8], xmm0
0x18002ae52  xor     eax, eax
0x18002ae54  mov     rcx, r15; Src
0x18002ae57  movups  xmmword ptr [rbx+18h], xmm0
0x18002ae5b  mov     r12, rbx
0x18002ae5e  movups  xmmword ptr [rbx+28h], xmm0
0x18002ae62  mov     [rbx+38h], rax
0x18002ae66  mov     dword ptr [rbx+8], 2
0x18002ae6d  call    FwStringCopy
0x18002ae72  mov     ecx, eax
0x18002ae74  call    FwHResultToWindowsError
0x18002ae79  mov     edi, eax
0x18002ae7b  test    eax, eax
0x18002ae7d  jnz     loc_18002AFE8
0x18002ae83  mov     rcx, [rsp+110h+var_E8]
0x18002ae88  lea     rdx, [rbx+38h]
0x18002ae8c  test    r14, r14
0x18002ae8f  cmovnz  rcx, r14; Src
0x18002ae93  call    FwStringCopy
0x18002ae98  mov     ecx, eax
0x18002ae9a  call    FwHResultToWindowsError
0x18002ae9f  mov     edi, eax
0x18002aea1  test    eax, eax
0x18002aea3  jnz     loc_18002AFC0
0x18002aea9  lea     rcx, [rbp+57h+pguid]; pguid
0x18002aead  call    cs:__imp_CoCreateGuid
0x18002aeb3  mov     ecx, eax
0x18002aeb5  call    FwHResultToWindowsError
0x18002aeba  mov     edi, eax
0x18002aebc  test    eax, eax
0x18002aebe  jnz     loc_18002AF98
0x18002aec4  lea     r8d, [rax+27h]; cchMax
0x18002aec8  lea     rdx, [rbp+57h+sz]; lpsz
0x18002aecc  lea     rcx, [rbp+57h+pguid]; rguid
0x18002aed0  call    cs:__imp_StringFromGUID2
0x18002aed6  test    eax, eax
0x18002aed8  jz      loc_18002AF65
0x18002aede  lea     rcx, [rbx+30h]
0x18002aee2  xor     r9d, r9d
0x18002aee5  lea     r8, [rbp+57h+sz]
0x18002aee9  lea     rdx, aEdp; "EDP_"
0x18002aef0  call    FwStringBuild
0x18002aef5  mov     ecx, eax
0x18002aef7  call    FwHResultToWindowsError
0x18002aefc  xor     edx, edx
0x18002aefe  mov     edi, eax
0x18002af00  test    eax, eax
0x18002af02  jnz     short loc_18002AF3A
0x18002af04  mov     rcx, [rbx+28h]
0x18002af08  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002af0c  inc     rax
0x18002af0f  cmp     [rcx+rax*2], dx
0x18002af13  jnz     short loc_18002AF0C
0x18002af15  mov     rcx, [rbx+38h]
0x18002af19  inc     eax
0x18002af1b  mov     [rbx+10h], eax
0x18002af1e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002af22  inc     rax
0x18002af25  cmp     [rcx+rax*2], dx
0x18002af29  jnz     short loc_18002AF22
0x18002af2b  inc     eax
0x18002af2d  inc     r13d
0x18002af30  mov     [rbx+14h], eax
0x18002af33  xor     ecx, ecx
0x18002af35  jmp     loc_18002AD83
0x18002af3a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002af41  lea     rdx, WPP_GLOBAL_Control
0x18002af48  cmp     rcx, rdx
0x18002af4b  jz      loc_18002B0A2
0x18002af51  test    byte ptr [rcx+1Ch], 1
0x18002af55  jz      loc_18002B0A2
0x18002af5b  mov     edx, 1Eh
0x18002af60  jmp     loc_18002B00E
0x18002af65  mov     r9d, 8
0x18002af6b  mov     edi, r9d
0x18002af6e  mov     rcx, cs:WPP_GLOBAL_Control
0x18002af75  lea     rdx, WPP_GLOBAL_Control
0x18002af7c  cmp     rcx, rdx
0x18002af7f  jz      loc_18002B0A2
0x18002af85  test    byte ptr [rcx+1Ch], 1
0x18002af89  jz      loc_18002B0A2
0x18002af8f  lea     edx, [r9+15h]
0x18002af93  jmp     loc_18002B05F
0x18002af98  mov     rcx, cs:WPP_GLOBAL_Control
0x18002af9f  lea     rdx, WPP_GLOBAL_Control
0x18002afa6  cmp     rcx, rdx
0x18002afa9  jz      loc_18002B0A2
0x18002afaf  test    byte ptr [rcx+1Ch], 1
0x18002afb3  jz      loc_18002B0A2
0x18002afb9  mov     edx, 1Ch
0x18002afbe  jmp     short loc_18002B00E
0x18002afc0  mov     rcx, cs:WPP_GLOBAL_Control
0x18002afc7  lea     rdx, WPP_GLOBAL_Control
0x18002afce  cmp     rcx, rdx
0x18002afd1  jz      loc_18002B0A2
0x18002afd7  test    byte ptr [rcx+1Ch], 1
0x18002afdb  jz      loc_18002B0A2
0x18002afe1  mov     edx, 1Bh
0x18002afe6  jmp     short loc_18002B00E
0x18002afe8  mov     rcx, cs:WPP_GLOBAL_Control
0x18002afef  lea     rdx, WPP_GLOBAL_Control
0x18002aff6  cmp     rcx, rdx
0x18002aff9  jz      loc_18002B0A2
0x18002afff  test    byte ptr [rcx+1Ch], 1
0x18002b003  jz      loc_18002B0A2
0x18002b009  mov     edx, 1Ah
0x18002b00e  mov     r9d, eax
0x18002b011  jmp     short loc_18002B05F
0x18002b013  mov     r9d, 8
0x18002b019  mov     edi, r9d
0x18002b01c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b023  lea     rdx, WPP_GLOBAL_Control
0x18002b02a  cmp     rcx, rdx
0x18002b02d  jz      short loc_18002B0A2
0x18002b02f  test    byte ptr [rcx+1Ch], 1
0x18002b033  jz      short loc_18002B0A2
0x18002b035  lea     edx, [r9+11h]
0x18002b039  jmp     short loc_18002B05F
0x18002b03b  mov     edi, 57h ; 'W'
0x18002b040  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b047  lea     rdx, WPP_GLOBAL_Control
0x18002b04e  cmp     rcx, rdx
0x18002b051  jz      short loc_18002B0A2
0x18002b053  test    byte ptr [rcx+1Ch], 1
0x18002b057  jz      short loc_18002B0A2
0x18002b059  lea     edx, [rdi-3Fh]
0x18002b05c  mov     r9d, edi
0x18002b05f  mov     rcx, [rcx+10h]
0x18002b063  lea     r8, WPP_7f5bde6595ff3eb51821de83b63f4275_Traceguids
0x18002b06a  call    WPP_SF_d
0x18002b06f  jmp     short loc_18002B0A2
0x18002b071  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b078  lea     rdx, WPP_GLOBAL_Control
0x18002b07f  cmp     rcx, rdx
0x18002b082  jz      short loc_18002B0A2
0x18002b084  test    byte ptr [rcx+1Ch], 1
0x18002b088  jz      short loc_18002B0A2
0x18002b08a  mov     rcx, [rcx+10h]
0x18002b08e  lea     r8, WPP_7f5bde6595ff3eb51821de83b63f4275_Traceguids
0x18002b095  mov     edx, 17h
0x18002b09a  mov     r9d, eax
0x18002b09d  call    WPP_SF_d
0x18002b0a2  test    rsi, rsi
0x18002b0a5  jz      short loc_18002B0DD
0x18002b0a7  mov     rcx, [rsi+28h]
0x18002b0ab  call    FwFree
0x18002b0b0  mov     rcx, [rsi+38h]
0x18002b0b4  call    FwFree
0x18002b0b9  mov     rbx, [rsi]
0x18002b0bc  mov     rcx, rsi
0x18002b0bf  call    FwFree
0x18002b0c4  mov     rsi, rbx
0x18002b0c7  test    rbx, rbx
0x18002b0ca  jnz     short loc_18002B0A7
0x18002b0cc  jmp     short loc_18002B0DD
0x18002b0ce  mov     rax, [rsp+110h+var_D8]
0x18002b0d3  mov     [rax], rsi
0x18002b0d6  mov     rax, [rbp+57h+var_D0]
0x18002b0da  mov     [rax], r13d
0x18002b0dd  mov     rcx, [rsp+110h+var_F0]
0x18002b0e2  call    FwFree
0x18002b0e7  mov     rcx, [rsp+110h+String]
0x18002b0ec  call    FwFree
0x18002b0f1  mov     eax, edi
0x18002b0f3  mov     rcx, [rbp+57h+var_50]
0x18002b0f7  xor     rcx, rsp; StackCookie
0x18002b0fa  call    __security_check_cookie
0x18002b0ff  add     rsp, 0D8h
0x18002b106  pop     r15
0x18002b108  pop     r14
0x18002b10a  pop     r13
0x18002b10c  pop     r12
0x18002b10e  pop     rdi
0x18002b10f  pop     rsi
0x18002b110  pop     rbx
0x18002b111  pop     rbp
0x18002b112  retn
```
