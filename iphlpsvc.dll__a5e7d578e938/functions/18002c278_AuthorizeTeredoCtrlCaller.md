# AuthorizeTeredoCtrlCaller

- ea: `0x18002c278`
- end: `0x18002c4bd`
- name: `AuthorizeTeredoCtrlCaller`
- size: `581`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002bd80`

## callees

- `0x180004c64`
- `0x180012dcc`
- `0x1800190f0`
- `0x18002c278`
- `0x18002c4c4`
- `0x18002c7dc`
- `0x18002dd30`
- `0x1800421e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002c434`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002c434`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c32d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c3b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c32d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c3b1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c49a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c49a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002c3a1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002c3a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c302`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c485`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c302`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c485`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002c31d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002c31d`

## string_xrefs

- `0x18002c2d4`: `Failed to get RPC caller token 0x%x`
- `0x18002c3cf`: `Failed to get system path 0x%x`
- `0x18002c33c`: `Failed to get SID for %ws 0x%x`
- `0x18002c44c`: `Failed to alloc executable and system path strings.`
- `0x18002c402`: `Failed to concat system path 0x%x`

## pseudocode

```c
__int64 __fastcall AuthorizeTeredoCtrlCaller(void *a1)
{
  int RpcCallerToken; // eax
  unsigned int v3; // ebx
  unsigned int i; // ebx
  const WCHAR *v5; // rsi
  DWORD LastError; // eax
  WCHAR *v7; // r14
  WCHAR *v8; // rax
  wchar_t *v9; // rsi
  signed int v10; // eax
  HRESULT v11; // eax
  int CallerName; // eax
  LPCWSTR StringSid; // [rsp+20h] [rbp-20h]
  const WCHAR *v15; // [rsp+28h] [rbp-18h]
  const wchar_t *v16; // [rsp+30h] [rbp-10h]
  HLOCAL hMem; // [rsp+68h] [rbp+28h] BYREF
  HANDLE hObject; // [rsp+70h] [rbp+30h] BYREF

  hObject = 0;
  StringSid = L"S-1-5-80-1352715831-1104254428-97934242-2131353953-1898040052";
  hMem = 0;
  v15 = L"S-1-5-80-3055155277-3816794035-3994065555-2874236192-2193176987";
  v16 = L"S-1-5-32-544";
  RpcCallerToken = GetRpcCallerToken(a1, &hObject);
  v3 = RpcCallerToken;
  if ( RpcCallerToken < 0 )
  {
    EventWriteError0(0x100000, L"Failed to get RPC caller token 0x%x", (unsigned int)RpcCallerToken);
    goto LABEL_28;
  }
  for ( i = 0; i < 3; ++i )
  {
    v5 = (&StringSid)[i];
    if ( hMem )
    {
      LocalFree(hMem);
      hMem = 0;
    }
    if ( ConvertStringSidToSidW(v5, &hMem) )
    {
      if ( (unsigned int)IsSidOnToken(hObject, hMem) )
      {
        v3 = 0;
        goto LABEL_28;
      }
    }
    else
    {
      LastError = GetLastError();
      EventWriteError0(0x100000, L"Failed to get SID for %ws 0x%x", v5, LastError, StringSid, v15, v16);
    }
  }
  v7 = (WCHAR *)MALLOC(0x208u);
  v8 = (WCHAR *)MALLOC(0x208u);
  v9 = v8;
  if ( v7 && v8 )
  {
    if ( GetSystemDirectoryW(v8, 0x104u) )
    {
      v11 = StringCchCatW(v9, 0x104u, L"\\msra.exe");
      v3 = v11;
      if ( v11 >= 0 )
      {
        CallerName = GetCallerName(a1, v7, 0x104u);
        v3 = CallerName;
        if ( CallerName >= 0 )
          v3 = (unsigned int)_o__wcsicmp(v7, v9) != 0 ? 0x80070005 : 0;
        else
          EventWriteError0(0x100000, L"Failed to get caller name 0x%x", (unsigned int)CallerName);
      }
      else
      {
        EventWriteError0(0x100000, L"Failed to concat system path 0x%x", (unsigned int)v11);
      }
    }
    else
    {
      v10 = GetLastError();
      v3 = v10;
      if ( v10 > 0 )
        v3 = (unsigned __int16)v10 | 0x80070000;
      EventWriteError0(0x100000, L"Failed to get system path 0x%x", v3);
    }
  }
  else
  {
    EventWriteError0(0x100000, L"Failed to alloc executable and system path strings.");
    v3 = -2147024882;
    if ( !v7 )
      goto LABEL_26;
  }
  FREE(v7);
LABEL_26:
  if ( v9 )
    FREE(v9);
LABEL_28:
  if ( hMem )
    LocalFree(hMem);
  if ( hObject )
    CloseHandle(hObject);
  return v3;
}

```

## disassembly

```asm
0x18002c278  mov     [rsp-18h+arg_0], rbx
0x18002c27d  mov     [rsp-18h+arg_18], rsi
0x18002c282  push    rbp
0x18002c283  push    r14
0x18002c285  push    r15
0x18002c287  mov     rbp, rsp
0x18002c28a  sub     rsp, 40h
0x18002c28e  lea     rax, aS1580135271583; "S-1-5-80-1352715831-1104254428-97934242"...
0x18002c295  mov     [rbp+hObject], 0
0x18002c29d  mov     [rbp+StringSid], rax
0x18002c2a1  lea     rdx, [rbp+hObject]; TokenHandle
0x18002c2a5  lea     rax, StringSid; "S-1-5-80-3055155277-3816794035-39940655"...
0x18002c2ac  mov     [rbp+hMem], 0
0x18002c2b4  mov     [rbp+var_18], rax
0x18002c2b8  mov     r15, rcx
0x18002c2bb  lea     rax, aS1532544; "S-1-5-32-544"
0x18002c2c2  mov     [rbp+var_10], rax
0x18002c2c6  call    GetRpcCallerToken
0x18002c2cb  mov     ebx, eax
0x18002c2cd  test    eax, eax
0x18002c2cf  jns     short loc_18002C2EA
0x18002c2d1  mov     r8d, eax
0x18002c2d4  lea     rdx, aFailedToGetRpc; "Failed to get RPC caller token 0x%x"
0x18002c2db  mov     ecx, 100000h
0x18002c2e0  call    EventWriteError0
0x18002c2e5  jmp     loc_18002C47C
0x18002c2ea  xor     ebx, ebx
0x18002c2ec  cmp     ebx, 3
0x18002c2ef  jnb     short loc_18002C36E
0x18002c2f1  mov     rcx, [rbp+hMem]; hMem
0x18002c2f5  movsxd  rax, ebx
0x18002c2f8  mov     rsi, [rbp+rax*8+StringSid]
0x18002c2fd  test    rcx, rcx
0x18002c300  jz      short loc_18002C316
0x18002c302  call    cs:__imp_LocalFree
0x18002c309  nop     dword ptr [rax+rax+00h]
0x18002c30e  mov     [rbp+hMem], 0
0x18002c316  lea     rdx, [rbp+hMem]; Sid
0x18002c31a  mov     rcx, rsi; StringSid
0x18002c31d  call    cs:__imp_ConvertStringSidToSidW
0x18002c324  nop     dword ptr [rax+rax+00h]
0x18002c329  test    eax, eax
0x18002c32b  jnz     short loc_18002C352
0x18002c32d  call    cs:__imp_GetLastError
0x18002c334  nop     dword ptr [rax+rax+00h]
0x18002c339  mov     r8, rsi
0x18002c33c  lea     rdx, aFailedToGetSid; "Failed to get SID for %ws 0x%x"
0x18002c343  mov     r9d, eax
0x18002c346  mov     ecx, 100000h
0x18002c34b  call    EventWriteError0
0x18002c350  jmp     short loc_18002C363
0x18002c352  mov     rdx, [rbp+hMem]
0x18002c356  mov     rcx, [rbp+hObject]
0x18002c35a  call    IsSidOnToken
0x18002c35f  test    eax, eax
0x18002c361  jnz     short loc_18002C367
0x18002c363  inc     ebx
0x18002c365  jmp     short loc_18002C2EC
0x18002c367  xor     ebx, ebx
0x18002c369  jmp     loc_18002C47C
0x18002c36e  mov     ebx, 208h
0x18002c373  mov     ecx, ebx; dwBytes
0x18002c375  call    MALLOC
0x18002c37a  mov     ecx, ebx; dwBytes
0x18002c37c  mov     r14, rax
0x18002c37f  call    MALLOC
0x18002c384  mov     rsi, rax
0x18002c387  test    r14, r14
0x18002c38a  jz      loc_18002C44C
0x18002c390  test    rax, rax
0x18002c393  jz      loc_18002C44C
0x18002c399  mov     edx, 104h; uSize
0x18002c39e  mov     rcx, rax; lpBuffer
0x18002c3a1  call    cs:__imp_GetSystemDirectoryW
0x18002c3a8  nop     dword ptr [rax+rax+00h]
0x18002c3ad  test    eax, eax
0x18002c3af  jnz     short loc_18002C3E5
0x18002c3b1  call    cs:__imp_GetLastError
0x18002c3b8  nop     dword ptr [rax+rax+00h]
0x18002c3bd  mov     ebx, eax
0x18002c3bf  test    eax, eax
0x18002c3c1  jle     short loc_18002C3CC
0x18002c3c3  movzx   ebx, ax
0x18002c3c6  or      ebx, 80070000h
0x18002c3cc  mov     r8d, ebx
0x18002c3cf  lea     rdx, aFailedToGetSys; "Failed to get system path 0x%x"
0x18002c3d6  mov     ecx, 100000h
0x18002c3db  call    EventWriteError0
0x18002c3e0  jmp     loc_18002C467
0x18002c3e5  lea     r8, aMsraExe; "\\msra.exe"
0x18002c3ec  mov     edx, 104h; cchDest
0x18002c3f1  mov     rcx, rsi; pszDest
0x18002c3f4  call    StringCchCatW
0x18002c3f9  mov     ebx, eax
0x18002c3fb  test    eax, eax
0x18002c3fd  jns     short loc_18002C40B
0x18002c3ff  mov     r8d, eax
0x18002c402  lea     rdx, aFailedToConcat; "Failed to concat system path 0x%x"
0x18002c409  jmp     short loc_18002C3D6
0x18002c40b  mov     r8d, 104h
0x18002c411  mov     rdx, r14
0x18002c414  mov     rcx, r15
0x18002c417  call    GetCallerName
0x18002c41c  mov     ebx, eax
0x18002c41e  test    eax, eax
0x18002c420  jns     short loc_18002C42E
0x18002c422  mov     r8d, eax
0x18002c425  lea     rdx, aFailedToGetCal; "Failed to get caller name 0x%x"
0x18002c42c  jmp     short loc_18002C3D6
0x18002c42e  mov     rdx, rsi
0x18002c431  mov     rcx, r14
0x18002c434  call    cs:__imp__o__wcsicmp
0x18002c43b  nop     dword ptr [rax+rax+00h]
0x18002c440  neg     eax
0x18002c442  sbb     ebx, ebx
0x18002c444  and     ebx, 80070005h
0x18002c44a  jmp     short loc_18002C467
0x18002c44c  lea     rdx, aFailedToAllocE; "Failed to alloc executable and system p"...
0x18002c453  mov     ecx, 100000h
0x18002c458  call    EventWriteError0
0x18002c45d  mov     ebx, 8007000Eh
0x18002c462  test    r14, r14
0x18002c465  jz      short loc_18002C46F
0x18002c467  mov     rcx, r14
0x18002c46a  call    FREE
0x18002c46f  test    rsi, rsi
0x18002c472  jz      short loc_18002C47C
0x18002c474  mov     rcx, rsi
0x18002c477  call    FREE
0x18002c47c  mov     rcx, [rbp+hMem]; hMem
0x18002c480  test    rcx, rcx
0x18002c483  jz      short loc_18002C491
0x18002c485  call    cs:__imp_LocalFree
0x18002c48c  nop     dword ptr [rax+rax+00h]
0x18002c491  mov     rcx, [rbp+hObject]; hObject
0x18002c495  test    rcx, rcx
0x18002c498  jz      short loc_18002C4A6
0x18002c49a  call    cs:__imp_CloseHandle
0x18002c4a1  nop     dword ptr [rax+rax+00h]
0x18002c4a6  mov     rsi, [rsp+40h+arg_18]
0x18002c4ab  mov     eax, ebx
0x18002c4ad  mov     rbx, [rsp+40h+arg_0]
0x18002c4b2  add     rsp, 40h
0x18002c4b6  pop     r15
0x18002c4b8  pop     r14
0x18002c4ba  pop     rbp
0x18002c4bb  retn
```
