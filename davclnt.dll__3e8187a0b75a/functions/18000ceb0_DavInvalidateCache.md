# DavInvalidateCache

- ea: `0x18000ceb0`
- end: `0x18000d0e5`
- name: `DavInvalidateCache`
- size: `565`
- prototype: `DWORD __stdcall(LPCWSTR URLName)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800028f0`
- `0x18000ceb0`
- `0x18000d510`
- `0x180010a3c`
- `0x180010be8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cf6d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cf6d`
- `KERNEL32!LocalAlloc` at `0x18000cf5a`
- `KERNEL32!LocalAlloc` at `0x18000cf5a`
- `KERNEL32!LocalFree` at `0x18000d0c6`
- `KERNEL32!LocalFree` at `0x18000d0d6`
- `KERNEL32!LocalFree` at `0x18000d0c6`
- `KERNEL32!LocalFree` at `0x18000d0d6`
- `RPCRT4!NdrClientCall3` at `0x18000d021`
- `RPCRT4!NdrClientCall3` at `0x18000d021`
- `RPCRT4!RpcBindingFree` at `0x18000d0b8`
- `RPCRT4!RpcBindingFree` at `0x18000d0b8`
- `DAVHLPR!DavGetHTTPFromUNCPath` at `0x18000cf44`
- `DAVHLPR!DavGetHTTPFromUNCPath` at `0x18000cf87`
- `DAVHLPR!DavGetHTTPFromUNCPath` at `0x18000cf44`
- `DAVHLPR!DavGetHTTPFromUNCPath` at `0x18000cf87`
- `DAVHLPR!DavCheckAndConvertHttpUrlToUncName` at `0x18000cef1`
- `DAVHLPR!DavCheckAndConvertHttpUrlToUncName` at `0x18000cef1`

## pseudocode

```c
DWORD __stdcall DavInvalidateCache(LPCWSTR URLName)
{
  WCHAR *v1; // rsi
  DWORD HTTPFromUNCPath; // ebx
  __int64 v3; // r8
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  __int64 v6; // rdx
  WCHAR *v7; // rax
  unsigned int v8; // eax
  __int64 v9; // r8
  unsigned int Pointer; // eax
  DWORD Size; // [rsp+60h] [rbp+8h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+68h] [rbp+10h] BYREF
  LPCWSTR UncPath; // [rsp+70h] [rbp+18h] BYREF
  WCHAR *v15; // [rsp+78h] [rbp+20h]

  Size = 0;
  UncPath = 0;
  v1 = 0;
  v15 = 0;
  Binding = 0;
  if ( !URLName )
  {
    HTTPFromUNCPath = 87;
    goto LABEL_24;
  }
  HTTPFromUNCPath = DavCheckAndConvertHttpUrlToUncName(URLName, &UncPath, 0, 0, 0);
  if ( HTTPFromUNCPath )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 249;
LABEL_7:
      WPP_SF_D(v4[2], v5, v3, HTTPFromUNCPath);
    }
  }
  else
  {
    Size = 0;
    HTTPFromUNCPath = DavGetHTTPFromUNCPath(UncPath, 0, &Size);
    if ( HTTPFromUNCPath == 122 )
    {
      v7 = (WCHAR *)LocalAlloc(0, 2LL * Size);
      v1 = v7;
      v15 = v7;
      if ( !v7 )
      {
        HTTPFromUNCPath = GetLastError();
        goto LABEL_24;
      }
      HTTPFromUNCPath = DavGetHTTPFromUNCPath(UncPath, v7, &Size);
    }
    if ( HTTPFromUNCPath )
    {
      v4 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v5 = 250;
        goto LABEL_7;
      }
    }
    else
    {
      v8 = DavBindTheRpcHandle(&Binding, v6, v3);
      if ( v8 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 251, v9, v8);
        HTTPFromUNCPath = 1222;
      }
      else
      {
        Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x10u, 0, Binding, v1).Pointer;
        HTTPFromUNCPath = Pointer;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 252, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids, Pointer);
      }
    }
  }
LABEL_24:
  if ( Binding )
    RpcBindingFree(&Binding);
  if ( v1 )
    LocalFree(v1);
  if ( UncPath )
    LocalFree((HLOCAL)UncPath);
  return HTTPFromUNCPath;
}

```

## disassembly

```asm
0x18000ceb0  push    rbx
0x18000ceb2  push    rsi
0x18000ceb3  sub     rsp, 48h
0x18000ceb7  mov     [rsp+58h+Size], 0
0x18000cebf  mov     [rsp+58h+UncPath], 0
0x18000cec8  xor     esi, esi
0x18000ceca  mov     [rsp+58h+arg_18], rsi
0x18000cecf  mov     [rsp+58h+Binding], rsi
0x18000ced4  test    rcx, rcx
0x18000ced7  jnz     short loc_18000CEE1
0x18000ced9  lea     ebx, [rsi+57h]
0x18000cedc  jmp     loc_18000D0AB
0x18000cee1  mov     [rsp+58h+var_38], rsi
0x18000cee6  xor     r9d, r9d
0x18000cee9  xor     r8d, r8d
0x18000ceec  lea     rdx, [rsp+58h+UncPath]
0x18000cef1  call    cs:__imp_DavCheckAndConvertHttpUrlToUncName
0x18000cef7  mov     ebx, eax
0x18000cef9  test    eax, eax
0x18000cefb  jz      short loc_18000CF34
0x18000cefd  lea     rax, WPP_GLOBAL_Control
0x18000cf04  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cf0b  cmp     rcx, rax
0x18000cf0e  jz      loc_18000D0AB
0x18000cf14  test    byte ptr [rcx+1Ch], 1
0x18000cf18  jz      loc_18000D0AB
0x18000cf1e  mov     edx, 0F9h
0x18000cf23  mov     r9d, ebx
0x18000cf26  mov     rcx, [rcx+10h]
0x18000cf2a  call    WPP_SF_D
0x18000cf2f  jmp     loc_18000D0AB
0x18000cf34  mov     [rsp+58h+Size], esi
0x18000cf38  lea     r8, [rsp+58h+Size]; lpSize
0x18000cf3d  xor     edx, edx; Url
0x18000cf3f  mov     rcx, [rsp+58h+UncPath]; UncPath
0x18000cf44  call    cs:__imp_DavGetHTTPFromUNCPath
0x18000cf4a  mov     ebx, eax
0x18000cf4c  cmp     eax, 7Ah ; 'z'
0x18000cf4f  jnz     short loc_18000CF8F
0x18000cf51  mov     edx, [rsp+58h+Size]
0x18000cf55  add     rdx, rdx; uBytes
0x18000cf58  xor     ecx, ecx; uFlags
0x18000cf5a  call    cs:__imp_LocalAlloc
0x18000cf60  mov     rsi, rax
0x18000cf63  mov     [rsp+58h+arg_18], rax
0x18000cf68  test    rax, rax
0x18000cf6b  jnz     short loc_18000CF7A
0x18000cf6d  call    cs:__imp_GetLastError
0x18000cf73  mov     ebx, eax
0x18000cf75  jmp     loc_18000D0AB
0x18000cf7a  lea     r8, [rsp+58h+Size]; lpSize
0x18000cf7f  mov     rdx, rax; Url
0x18000cf82  mov     rcx, [rsp+58h+UncPath]; UncPath
0x18000cf87  call    cs:__imp_DavGetHTTPFromUNCPath
0x18000cf8d  mov     ebx, eax
0x18000cf8f  test    ebx, ebx
0x18000cf91  jz      short loc_18000CFBE
0x18000cf93  lea     rax, WPP_GLOBAL_Control
0x18000cf9a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cfa1  cmp     rcx, rax
0x18000cfa4  jz      loc_18000D0AB
0x18000cfaa  test    byte ptr [rcx+1Ch], 1
0x18000cfae  jz      loc_18000D0AB
0x18000cfb4  mov     edx, 0FAh
0x18000cfb9  jmp     loc_18000CF23
0x18000cfbe  lea     rcx, [rsp+58h+Binding]
0x18000cfc3  call    DavBindTheRpcHandle
0x18000cfc8  mov     r9d, eax
0x18000cfcb  test    eax, eax
0x18000cfcd  jz      short loc_18000D000
0x18000cfcf  lea     rax, WPP_GLOBAL_Control
0x18000cfd6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000cfdd  cmp     rcx, rax
0x18000cfe0  jz      short loc_18000CFF6
0x18000cfe2  test    byte ptr [rcx+1Ch], 1
0x18000cfe6  jz      short loc_18000CFF6
0x18000cfe8  mov     edx, 0FBh
0x18000cfed  mov     rcx, [rcx+10h]
0x18000cff1  call    WPP_SF_D
0x18000cff6  mov     ebx, 4C6h
0x18000cffb  jmp     loc_18000D0AB
0x18000d000  mov     [rsp+58h+var_20], 0
0x18000d009  mov     [rsp+58h+var_38], rsi
0x18000d00e  mov     r9, [rsp+58h+Binding]
0x18000d013  xor     r8d, r8d; pReturnValue
0x18000d016  lea     edx, [r8+10h]; nProcNum
0x18000d01a  lea     rcx, pProxyInfo; pProxyInfo
0x18000d021  call    cs:__imp_NdrClientCall3
0x18000d027  mov     rbx, rax
0x18000d02a  mov     [rsp+58h+var_20], rax
0x18000d02f  mov     [rsp+58h+var_28], ebx
0x18000d033  lea     rax, WPP_GLOBAL_Control
0x18000d03a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d041  cmp     rcx, rax
0x18000d044  jz      short loc_18000D064
0x18000d046  test    byte ptr [rcx+1Ch], 2
0x18000d04a  jz      short loc_18000D064
0x18000d04c  mov     edx, 0FCh
0x18000d051  mov     r9d, ebx
0x18000d054  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000d05b  mov     rcx, [rcx+10h]
0x18000d05f  call    WPP_SF_d
0x18000d064  jmp     short loc_18000D0AB
0x18000d066  mov     ebx, eax
0x18000d068  lea     rax, WPP_GLOBAL_Control
0x18000d06f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d076  cmp     rcx, rax
0x18000d079  jz      short loc_18000D099
0x18000d07b  test    byte ptr [rcx+1Ch], 1
0x18000d07f  jz      short loc_18000D099
0x18000d081  mov     edx, 0FDh
0x18000d086  mov     r9d, ebx
0x18000d089  lea     r8, WPP_834d339bfac63cfe53ce606fa1b4fc9f_Traceguids
0x18000d090  mov     rcx, [rcx+10h]
0x18000d094  call    WPP_SF_d
0x18000d099  mov     ecx, ebx
0x18000d09b  call    DavMapRpcErrorToProviderError
0x18000d0a0  mov     ebx, eax
0x18000d0a2  mov     [rsp+58h+var_28], eax
0x18000d0a6  mov     rsi, [rsp+58h+arg_18]
0x18000d0ab  cmp     [rsp+58h+Binding], 0
0x18000d0b1  jz      short loc_18000D0BE
0x18000d0b3  lea     rcx, [rsp+58h+Binding]; Binding
0x18000d0b8  call    cs:__imp_RpcBindingFree
0x18000d0be  test    rsi, rsi
0x18000d0c1  jz      short loc_18000D0CC
0x18000d0c3  mov     rcx, rsi; hMem
0x18000d0c6  call    cs:__imp_LocalFree
0x18000d0cc  mov     rcx, [rsp+58h+UncPath]; hMem
0x18000d0d1  test    rcx, rcx
0x18000d0d4  jz      short loc_18000D0DC
0x18000d0d6  call    cs:__imp_LocalFree
0x18000d0dc  mov     eax, ebx
0x18000d0de  add     rsp, 48h
0x18000d0e2  pop     rsi
0x18000d0e3  pop     rbx
0x18000d0e4  retn
0x1800123b6  push    rbp
0x1800123b8  sub     rsp, 30h
0x1800123bc  mov     rbp, rdx
0x1800123bf  mov     rcx, [rcx]
0x1800123c2  mov     ecx, [rcx]; ExceptionCode
0x1800123c4  call    cs:__imp_I_RpcExceptionFilter
0x1800123ca  nop
0x1800123cb  add     rsp, 30h
0x1800123cf  pop     rbp
0x1800123d0  retn
```
