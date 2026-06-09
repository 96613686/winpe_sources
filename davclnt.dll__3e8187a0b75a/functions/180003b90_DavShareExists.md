# DavShareExists

- ea: `0x180003b90`
- end: `0x1800042eb`
- name: `DavShareExists`
- size: `1883`
- prototype: `__int64 __fastcall(LPCWSTR UncPath, _DWORD *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180004340`

## callees

- `0x180001010`
- `0x180003540`
- `0x180003b90`
- `0x180004300`
- `0x18000d510`
- `0x180010a14`
- `0x180010a3c`
- `0x180010be8`
- `0x180010c28`
- `0x180010d00`
- `0x180011340`
- `0x180011e76`
- `0x180011e82`
- `0x180011eb0`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180003d6b`
- `msvcrt!_wcsnicmp` at `0x180003d6b`
- `msvcrt!wcschr` at `0x180003c4a`
- `msvcrt!wcschr` at `0x180003c4a`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180003f4e`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x180003f4e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800041ba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800041ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003cc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003cc9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e17`
- `KERNEL32!LocalAlloc` at `0x180003cb3`
- `KERNEL32!LocalAlloc` at `0x180003e01`
- `KERNEL32!LocalAlloc` at `0x180003cb3`
- `KERNEL32!LocalAlloc` at `0x180003e01`
- `KERNEL32!LocalFree` at `0x180004295`
- `KERNEL32!LocalFree` at `0x1800042a3`
- `KERNEL32!LocalFree` at `0x180004295`
- `KERNEL32!LocalFree` at `0x1800042a3`
- `RPCRT4!NdrClientCall3` at `0x180004037`
- `RPCRT4!NdrClientCall3` at `0x180004037`
- `RPCRT4!I_RpcExceptionFilter` at `0x18001202e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18001202e`
- `RPCRT4!RpcBindingFree` at `0x1800042b6`
- `RPCRT4!RpcBindingFree` at `0x1800042b6`
- `DAVHLPR!DavGetHTTPFromUNCPath` at `0x180003e79`
- `DAVHLPR!DavGetHTTPFromUNCPath` at `0x180003e79`

## pseudocode

```c
__int64 __fastcall DavShareExists(LPCWSTR UncPath, _DWORD *a2)
{
  _DWORD *v2; // r14
  char *v4; // r12
  DWORD Pointer; // ebx
  _WORD *v6; // rdi
  wchar_t *v7; // r15
  unsigned __int64 v8; // rax
  _QWORD *v9; // rcx
  SIZE_T v10; // r14
  char *v11; // rax
  DWORD LastError; // eax
  __int64 v13; // rdx
  const wchar_t *v14; // rsi
  char v15; // r14
  HRESULT v16; // eax
  size_t v17; // r15
  _WORD *v18; // rax
  __int64 v19; // rdx
  void *v20; // rcx
  __int64 v21; // r8
  __int64 v22; // rax
  NTSTATUS v23; // eax
  ULONG v24; // eax
  ULONG v25; // ebx
  char v26; // r13
  char v27; // si
  __int64 v28; // r14
  CLIENT_CALL_RETURN v29; // rax
  CLIENT_CALL_RETURN v30; // r8
  int v31; // eax
  int v32; // eax
  int v33; // eax
  int v34; // eax
  size_t v35; // rax
  __int64 v36; // rcx
  const char *v37; // r9
  __int64 v39; // [rsp+38h] [rbp-2C0h]
  _BYTE v40[8]; // [rsp+50h] [rbp-2A8h] BYREF
  _DWORD *v41; // [rsp+58h] [rbp-2A0h]
  size_t pcchLength; // [rsp+60h] [rbp-298h] BYREF
  int v43; // [rsp+68h] [rbp-290h]
  __int64 v44; // [rsp+70h] [rbp-288h] BYREF
  void *Simple; // [rsp+78h] [rbp-280h] BYREF
  DWORD Size; // [rsp+80h] [rbp-278h] BYREF
  size_t v47; // [rsp+88h] [rbp-270h]
  RPC_BINDING_HANDLE Binding[4]; // [rsp+90h] [rbp-268h] BYREF
  WCHAR Url[264]; // [rsp+B0h] [rbp-248h] BYREF

  v2 = a2;
  v41 = a2;
  Binding[1] = a2;
  v4 = 0;
  Pointer = 0;
  Binding[0] = 0;
  v6 = 0;
  pcchLength = 0;
  memset_0(Url, 0, 0x208u);
  Size = 260;
  v44 = 0;
  *v2 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 220, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, UncPath);
  v7 = wcschr(UncPath + 2, 0x5Cu);
  v8 = v7 - (UncPath + 2);
  if ( v8 > 0x104 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 221, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids);
      v9 = WPP_GLOBAL_Control;
    }
    goto LABEL_94;
  }
  v10 = 2 * v8 + 2;
  v11 = (char *)LocalAlloc(0x40u, v10);
  v4 = v11;
  Binding[2] = v11;
  if ( !v11 )
  {
    LastError = GetLastError();
    Pointer = LastError;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_93;
    v13 = 222;
    goto LABEL_12;
  }
  memcpy_0(v11, UncPath + 2, v10 - 2);
  *(_WORD *)&v4[v10 - 2] = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 223, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, v4);
  v14 = v7 + 1;
  if ( _wcsnicmp(v7 + 1, L"DavWWWRoot", 0xAu) )
  {
    v15 = 0;
  }
  else
  {
    v14 = v7 + 11;
    v15 = 1;
    if ( v7[11] == 92 )
      v14 = v7 + 12;
  }
  if ( v14 )
  {
    v16 = StringLengthWorkerW(v14, 0x104u, &pcchLength);
    if ( v16 >= 0 )
    {
      v17 = pcchLength;
      goto LABEL_25;
    }
  }
  else
  {
    v16 = -2147024809;
  }
  v17 = 0;
LABEL_25:
  if ( v16 < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_93;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 224, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids);
    goto LABEL_92;
  }
  v18 = LocalAlloc(0x40u, 2 * v17 + 2);
  v6 = v18;
  Binding[3] = v18;
  if ( !v18 )
  {
    LastError = GetLastError();
    Pointer = LastError;
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_93;
    v13 = 225;
LABEL_12:
    WPP_SF_d(v9[2], v13, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, LastError);
LABEL_92:
    v9 = WPP_GLOBAL_Control;
LABEL_93:
    v2 = v41;
LABEL_94:
    v26 = 0;
    goto LABEL_95;
  }
  LODWORD(pcchLength) = 0;
  memcpy_0(v18, v14, 2 * v17);
  v6[v17] = 0;
  if ( !DavGetHTTPFromUNCPath(UncPath, Url, &Size) )
  {
    DavClntQueryWinInetCookies((__int64)Url, &v44);
    v21 = v44;
    if ( v44 )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      {
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          226,
          (unsigned int)WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids,
          v44,
          (__int64)Url);
        v21 = v44;
      }
      v22 = -1;
      do
        ++v22;
      while ( *(_WORD *)(v21 + 2 * v22) );
      LODWORD(pcchLength) = v22 + 1;
    }
    else
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 227, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, Url);
    }
  }
  Simple = 0;
  v23 = RpcpBindRpc(v20, v19, v21, &Simple);
  v24 = RtlNtStatusToDosErrorNoTeb(v23);
  v25 = v24;
  if ( !v24 )
  {
    Binding[0] = Simple;
    goto LABEL_49;
  }
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 202, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, v24);
LABEL_49:
    v9 = WPP_GLOBAL_Control;
  }
  if ( v25 )
  {
    if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 1) != 0 )
    {
      WPP_SF_d(v9[2], 228, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, v25);
      v9 = WPP_GLOBAL_Control;
    }
    Pointer = 1222;
    goto LABEL_93;
  }
  v26 = 1;
  v40[1] = 1;
  v27 = 1;
  v40[0] = v15;
  v28 = v44;
LABEL_56:
  Simple = 0;
  LODWORD(v39) = pcchLength;
  v29.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 4u, 0, Binding[0], v4, v6, v28, v39, v40).Pointer;
  Pointer = (DWORD)v29.Pointer;
  Simple = (void *)v29.Simple;
  v43 = (int)v29.Pointer;
  if ( LODWORD(v29.Pointer) )
  {
    if ( LODWORD(v29.Pointer) != 224 )
    {
      v31 = LODWORD(v29.Pointer) - 5;
      if ( v31 )
      {
        v32 = v31 - 81;
        if ( v32 )
        {
          v33 = v32 - 1240;
          if ( v33 )
          {
            v34 = v33 - 71;
            if ( v34 )
            {
              if ( v34 != 393 && v27 )
              {
                v35 = v17;
                v27 = 0;
                while ( 1 )
                {
                  v47 = v35;
                  if ( !v35 )
                    goto LABEL_71;
                  if ( v6[v35] )
                    break;
                  --v35;
                }
                while ( v35 && v6[v35] == 92 )
                  v47 = --v35;
LABEL_71:
                while ( 1 )
                {
                  v36 = v35;
                  if ( !v35 )
                    break;
                  if ( v6[v36] == 92 )
                  {
                    v6[v36] = 0;
                    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
                    {
                      ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_D)(
                        *((_QWORD *)WPP_GLOBAL_Control + 2),
                        229,
                        (CLIENT_CALL_RETURN)v30.Simple,
                        Pointer);
                    }
                    goto LABEL_56;
                  }
                  v47 = --v35;
                }
              }
            }
          }
        }
      }
    }
  }
  v2 = v41;
  if ( v40[0] )
    *v41 = 1;
  if ( Pointer )
  {
    if ( Pointer == 12175 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 231, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids);
      Pointer = 1790;
      v43 = 1790;
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 230, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, Pointer);
    }
    SetLastError(Pointer);
  }
  v9 = WPP_GLOBAL_Control;
LABEL_95:
  if ( v9 != &WPP_GLOBAL_Control && (*((_BYTE *)v9 + 28) & 2) != 0 )
  {
    v37 = "TRUE";
    if ( !*v2 )
      v37 = "FALSE";
    WPP_SF_s(v9[2], 233, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, v37);
  }
  if ( v4 )
    LocalFree(v4);
  if ( v6 )
    LocalFree(v6);
  if ( v26 )
    RpcBindingFree(Binding);
  return Pointer;
}

```

## disassembly

```asm
0x180003b90  mov     [rsp+arg_10], rbx
0x180003b95  mov     [rsp+arg_18], rsi
0x180003b9a  push    rdi
0x180003b9b  push    r12
0x180003b9d  push    r13
0x180003b9f  push    r14
0x180003ba1  push    r15
0x180003ba3  sub     rsp, 2D0h
0x180003baa  mov     rax, cs:__security_cookie
0x180003bb1  xor     rax, rsp
0x180003bb4  mov     [rsp+2F8h+var_38], rax
0x180003bbc  mov     r14, rdx
0x180003bbf  mov     [rsp+2F8h+var_2A0], rdx
0x180003bc4  mov     r13, rcx
0x180003bc7  mov     [rsp+2F8h+var_260], rdx
0x180003bcf  xor     r12d, r12d
0x180003bd2  mov     ebx, r12d
0x180003bd5  mov     [rsp+2F8h+Binding], r12
0x180003bdd  mov     edi, r12d
0x180003be0  mov     [rsp+2F8h+pcchLength], r12
0x180003be5  xor     edx, edx; Val
0x180003be7  mov     r8d, 208h; Size
0x180003bed  lea     rcx, [rsp+2F8h+Url]; void *
0x180003bf5  call    memset_0
0x180003bfa  mov     [rsp+2F8h+Size], 104h
0x180003c05  mov     [rsp+2F8h+var_288], r12
0x180003c0a  mov     [r14], r12d
0x180003c0d  lea     rax, WPP_GLOBAL_Control
0x180003c14  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c1b  cmp     rcx, rax
0x180003c1e  jz      short loc_180003C3E
0x180003c20  test    byte ptr [rcx+1Ch], 20h
0x180003c24  jz      short loc_180003C3E
0x180003c26  mov     edx, 0DCh
0x180003c2b  mov     r9, r13
0x180003c2e  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x180003c35  mov     rcx, [rcx+10h]
0x180003c39  call    WPP_SF_S
0x180003c3e  lea     rsi, [r13+4]
0x180003c42  mov     edx, 5Ch ; '\'; Ch
0x180003c47  mov     rcx, rsi; Str
0x180003c4a  call    cs:__imp_wcschr
0x180003c50  mov     r15, rax
0x180003c53  sub     rax, rsi
0x180003c56  sar     rax, 1
0x180003c59  cmp     rax, 104h
0x180003c5f  jbe     short loc_180003CA3
0x180003c61  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c68  lea     rsi, WPP_GLOBAL_Control
0x180003c6f  cmp     rcx, rsi
0x180003c72  jz      loc_180004254
0x180003c78  test    byte ptr [rcx+1Ch], 1
0x180003c7c  jz      loc_180004254
0x180003c82  mov     edx, 0DDh
0x180003c87  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x180003c8e  mov     rcx, [rcx+10h]
0x180003c92  call    WPP_SF_
0x180003c97  mov     rcx, cs:WPP_GLOBAL_Control
0x180003c9e  jmp     loc_180004254
0x180003ca3  lea     r14, ds:2[rax*2]
0x180003cab  mov     rdx, r14; uBytes
0x180003cae  mov     ecx, 40h ; '@'; uFlags
0x180003cb3  call    cs:__imp_LocalAlloc
0x180003cb9  mov     r12, rax
0x180003cbc  mov     [rsp+2F8h+var_258], rax
0x180003cc4  test    rax, rax
0x180003cc7  jnz     short loc_180003D0F
0x180003cc9  call    cs:__imp_GetLastError
0x180003ccf  mov     ebx, eax
0x180003cd1  mov     rcx, cs:WPP_GLOBAL_Control
0x180003cd8  lea     rsi, WPP_GLOBAL_Control
0x180003cdf  cmp     rcx, rsi
0x180003ce2  jz      loc_18000424F
0x180003ce8  test    byte ptr [rcx+1Ch], 1
0x180003cec  jz      loc_18000424F
0x180003cf2  mov     edx, 0DEh
0x180003cf7  mov     r9d, eax
0x180003cfa  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x180003d01  mov     rcx, [rcx+10h]
0x180003d05  call    WPP_SF_d
0x180003d0a  jmp     loc_180004248
0x180003d0f  lea     r8, [r14-2]; Size
0x180003d13  mov     rdx, rsi; Src
0x180003d16  mov     rcx, r12; void *
0x180003d19  call    memcpy_0
0x180003d1e  xor     eax, eax
0x180003d20  mov     [r14+r12-2], ax
0x180003d26  mov     rcx, cs:WPP_GLOBAL_Control
0x180003d2d  lea     rax, WPP_GLOBAL_Control
0x180003d34  cmp     rcx, rax
0x180003d37  jz      short loc_180003D57
0x180003d39  test    byte ptr [rcx+1Ch], 2
0x180003d3d  jz      short loc_180003D57
0x180003d3f  mov     edx, 0DFh
0x180003d44  mov     r9, r12
0x180003d47  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x180003d4e  mov     rcx, [rcx+10h]
0x180003d52  call    WPP_SF_S
0x180003d57  lea     rsi, [r15+2]
0x180003d5b  mov     r8d, 0Ah; MaxCount
0x180003d61  lea     rdx, aDavwwwroot; "DavWWWRoot"
0x180003d68  mov     rcx, rsi; String1
0x180003d6b  call    cs:__imp__wcsnicmp
0x180003d71  test    eax, eax
0x180003d73  jnz     short loc_180003D88
0x180003d75  add     rsi, 14h
0x180003d79  mov     r14b, 1
0x180003d7c  cmp     word ptr [rsi], 5Ch ; '\'
0x180003d80  jnz     short loc_180003D8B
0x180003d82  add     rsi, 2
0x180003d86  jmp     short loc_180003D8B
0x180003d88  xor     r14b, r14b
0x180003d8b  test    rsi, rsi
0x180003d8e  jz      short loc_180003DAD
0x180003d90  lea     r8, [rsp+2F8h+pcchLength]; pcchLength
0x180003d95  mov     edx, 104h; cchMax
0x180003d9a  mov     rcx, rsi; psz
0x180003d9d  call    StringLengthWorkerW
0x180003da2  test    eax, eax
0x180003da4  js      short loc_180003DB2
0x180003da6  mov     r15, [rsp+2F8h+pcchLength]
0x180003dab  jmp     short loc_180003DB5
0x180003dad  mov     eax, 80070057h
0x180003db2  xor     r15d, r15d
0x180003db5  test    eax, eax
0x180003db7  jns     short loc_180003DF4
0x180003db9  mov     rcx, cs:WPP_GLOBAL_Control
0x180003dc0  lea     rsi, WPP_GLOBAL_Control
0x180003dc7  cmp     rcx, rsi
0x180003dca  jz      loc_18000424F
0x180003dd0  test    byte ptr [rcx+1Ch], 1
0x180003dd4  jz      loc_18000424F
0x180003dda  mov     edx, 0E0h
0x180003ddf  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x180003de6  mov     rcx, [rcx+10h]
0x180003dea  call    WPP_SF_
0x180003def  jmp     loc_180004248
0x180003df4  lea     rbx, [r15+r15]
0x180003df8  lea     rdx, [rbx+2]; uBytes
0x180003dfc  mov     ecx, 40h ; '@'; uFlags
0x180003e01  call    cs:__imp_LocalAlloc
0x180003e07  mov     rdi, rax
0x180003e0a  mov     [rsp+2F8h+var_250], rax
0x180003e12  test    rax, rax
0x180003e15  jnz     short loc_180003E4A
0x180003e17  call    cs:__imp_GetLastError
0x180003e1d  mov     ebx, eax
0x180003e1f  mov     rcx, cs:WPP_GLOBAL_Control
0x180003e26  lea     rsi, WPP_GLOBAL_Control
0x180003e2d  cmp     rcx, rsi
0x180003e30  jz      loc_18000424F
0x180003e36  test    byte ptr [rcx+1Ch], 1
0x180003e3a  jz      loc_18000424F
0x180003e40  mov     edx, 0E1h
0x180003e45  jmp     loc_180003CF7
0x180003e4a  mov     dword ptr [rsp+2F8h+pcchLength], 0
0x180003e52  mov     r8, rbx; Size
0x180003e55  mov     rdx, rsi; Src
0x180003e58  mov     rcx, rdi; void *
0x180003e5b  call    memcpy_0
0x180003e60  xor     eax, eax
0x180003e62  mov     [rbx+rdi], ax
0x180003e66  lea     r8, [rsp+2F8h+Size]; lpSize
0x180003e6e  lea     rdx, [rsp+2F8h+Url]; Url
0x180003e76  mov     rcx, r13; UncPath
0x180003e79  call    cs:__imp_DavGetHTTPFromUNCPath
0x180003e7f  test    eax, eax
0x180003e81  jnz     loc_180003F39
0x180003e87  lea     rdx, [rsp+2F8h+var_288]
0x180003e8c  lea     rcx, [rsp+2F8h+Url]
0x180003e94  call    DavClntQueryWinInetCookies
0x180003e99  mov     r8, [rsp+2F8h+var_288]
0x180003e9e  test    r8, r8
0x180003ea1  jz      short loc_180003F03
0x180003ea3  mov     rcx, cs:WPP_GLOBAL_Control
0x180003eaa  lea     rax, WPP_GLOBAL_Control
0x180003eb1  cmp     rcx, rax
0x180003eb4  jz      short loc_180003EE6
0x180003eb6  test    byte ptr [rcx+1Ch], 2
0x180003eba  jz      short loc_180003EE6
0x180003ebc  mov     edx, 0E2h
0x180003ec1  lea     rax, [rsp+2F8h+Url]
0x180003ec9  mov     [rsp+2F8h+var_2D8], rax
0x180003ece  mov     r9, r8
0x180003ed1  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x180003ed8  mov     rcx, [rcx+10h]
0x180003edc  call    WPP_SF_SS
0x180003ee1  mov     r8, [rsp+2F8h+var_288]
0x180003ee6  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180003eed  nop     dword ptr [rax]
0x180003ef0  inc     rax
0x180003ef3  cmp     word ptr [r8+rax*2], 0
0x180003ef9  jnz     short loc_180003EF0
0x180003efb  inc     eax
0x180003efd  mov     dword ptr [rsp+2F8h+pcchLength], eax
0x180003f01  jmp     short loc_180003F39
0x180003f03  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f0a  lea     rax, WPP_GLOBAL_Control
0x180003f11  cmp     rcx, rax
0x180003f14  jz      short loc_180003F39
0x180003f16  test    byte ptr [rcx+1Ch], 2
0x180003f1a  jz      short loc_180003F39
0x180003f1c  mov     edx, 0E3h
0x180003f21  lea     r9, [rsp+2F8h+Url]
0x180003f29  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x180003f30  mov     rcx, [rcx+10h]
0x180003f34  call    WPP_SF_S
0x180003f39  mov     [rsp+2F8h+var_280], 0
0x180003f42  lea     r9, [rsp+2F8h+var_280]
0x180003f47  call    RpcpBindRpc
0x180003f4c  mov     ecx, eax; Status
0x180003f4e  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180003f54  mov     ebx, eax
0x180003f56  test    eax, eax
0x180003f58  jz      short loc_180003F8D
0x180003f5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180003f61  lea     rsi, WPP_GLOBAL_Control
0x180003f68  cmp     rcx, rsi
0x180003f6b  jz      short loc_180003FA8
0x180003f6d  test    byte ptr [rcx+1Ch], 1
0x180003f71  jz      short loc_180003FA8
0x180003f73  mov     edx, 0CAh
0x180003f78  mov     r9d, eax
0x180003f7b  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x180003f82  mov     rcx, [rcx+10h]
0x180003f86  call    WPP_SF_d
0x180003f8b  jmp     short loc_180003FA1
0x180003f8d  mov     rax, [rsp+2F8h+var_280]
0x180003f92  mov     [rsp+2F8h+Binding], rax
0x180003f9a  lea     rsi, WPP_GLOBAL_Control
0x180003fa1  mov     rcx, cs:WPP_GLOBAL_Control
0x180003fa8  test    ebx, ebx
0x180003faa  jz      short loc_180003FE0
0x180003fac  cmp     rcx, rsi
0x180003faf  jz      short loc_180003FD6
0x180003fb1  test    byte ptr [rcx+1Ch], 1
0x180003fb5  jz      short loc_180003FD6
0x180003fb7  mov     edx, 0E4h
0x180003fbc  mov     r9d, ebx
0x180003fbf  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x180003fc6  mov     rcx, [rcx+10h]
0x180003fca  call    WPP_SF_d
0x180003fcf  mov     rcx, cs:WPP_GLOBAL_Control
0x180003fd6  mov     ebx, 4C6h
0x180003fdb  jmp     loc_18000424F
0x180003fe0  mov     r13b, 1
0x180003fe3  mov     [rsp+2F8h+var_2A7], r13b
0x180003fe8  movzx   esi, r13b
0x180003fec  mov     [rsp+2F8h+var_2A8], r14b
0x180003ff1  mov     r14, [rsp+2F8h+var_288]
0x180003ff6  mov     [rsp+2F8h+var_280], 0
0x180003fff  lea     rax, [rsp+2F8h+var_2A8]
0x180004004  mov     [rsp+2F8h+var_2B8], rax
0x180004009  mov     eax, dword ptr [rsp+2F8h+pcchLength]
0x18000400d  mov     dword ptr [rsp+2F8h+var_2C0], eax
0x180004011  mov     [rsp+2F8h+var_2C8], r14
0x180004016  mov     [rsp+2F8h+var_2D0], rdi
0x18000401b  mov     [rsp+2F8h+var_2D8], r12
0x180004020  mov     r9, [rsp+2F8h+Binding]
0x180004028  xor     r8d, r8d; pReturnValue
0x18000402b  mov     edx, 4; nProcNum
0x180004030  lea     rcx, pProxyInfo; pProxyInfo
0x180004037  call    cs:__imp_NdrClientCall3
0x18000403d  mov     rbx, rax
0x180004040  mov     [rsp+2F8h+var_280], rax
0x180004045  mov     [rsp+2F8h+var_290], ebx
0x180004049  test    eax, eax
0x18000404b  jz      loc_180004127
0x180004051  cmp     ebx, 0E0h
0x180004057  jz      loc_180004127
0x18000405d  sub     eax, 5
0x180004060  jz      loc_180004127
0x180004066  sub     eax, 51h ; 'Q'
0x180004069  jz      loc_180004127
0x18000406f  sub     eax, 4D8h
0x180004074  jz      loc_180004127
0x18000407a  sub     eax, 47h ; 'G'
0x18000407d  jz      loc_180004127
0x180004083  cmp     eax, 189h
0x180004088  jz      loc_180004127
0x18000408e  test    sil, sil
0x180004091  jz      loc_180004127
0x180004097  mov     rax, r15
0x18000409a  xor     sil, sil
0x18000409d  mov     [rsp+2F8h+var_270], rax
0x1800040a5  test    rax, rax
0x1800040a8  jz      short loc_1800040D0
0x1800040aa  cmp     word ptr [rdi+rax*2], 0
0x1800040af  jnz     short loc_1800040B6
0x1800040b1  dec     rax
0x1800040b4  jmp     short loc_18000409D
0x1800040b6  test    rax, rax
0x1800040b9  jz      short loc_1800040D0
0x1800040bb  cmp     word ptr [rdi+rax*2], 5Ch ; '\'
0x1800040c0  jnz     short loc_1800040D0
0x1800040c2  dec     rax
0x1800040c5  mov     [rsp+2F8h+var_270], rax
0x1800040cd  jmp     short loc_1800040B6
0x1800040d0  lea     rcx, [rax+rax]
0x1800040d4  test    rax, rax
  ... truncated ...
```
