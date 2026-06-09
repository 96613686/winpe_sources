# AuthorizeTeredoCtrlCaller

- ea: `0x18002c268`
- end: `0x18002c4ad`
- name: `AuthorizeTeredoCtrlCaller`
- size: `581`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002bd70`

## callees

- `0x180004c54`
- `0x180012dbc`
- `0x1800190e0`
- `0x18002c268`
- `0x18002c4b4`
- `0x18002c7cc`
- `0x18002dd20`
- `0x180042220`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002c424`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18002c424`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c31d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c3a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c31d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c3a1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c48a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c48a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002c391`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18002c391`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c2f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c475`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c2f2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c475`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002c30d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002c30d`

## string_xrefs

- `0x18002c2c4`: `Failed to get RPC caller token 0x%x`
- `0x18002c3bf`: `Failed to get system path 0x%x`
- `0x18002c32c`: `Failed to get SID for %ws 0x%x`
- `0x18002c43c`: `Failed to alloc executable and system path strings.`
- `0x18002c3f2`: `Failed to concat system path 0x%x`

## pseudocode

```c
__int64 __fastcall AuthorizeTeredoCtrlCaller(void *a1)
{
  int RpcCallerToken; // eax
  unsigned int v3; // ebx
  unsigned int i; // ebx
  const WCHAR *v5; // rsi
  DWORD LastError; // eax
  __int64 v7; // r14
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
  v7 = MALLOC(0x208u);
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
        CallerName = GetCallerName(a1, v7, 260);
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
0x18002c268  mov     [rsp-18h+arg_0], rbx
0x18002c26d  mov     [rsp-18h+arg_18], rsi
0x18002c272  push    rbp
0x18002c273  push    r14
0x18002c275  push    r15
0x18002c277  mov     rbp, rsp
0x18002c27a  sub     rsp, 40h
0x18002c27e  lea     rax, aS1580135271583; "S-1-5-80-1352715831-1104254428-97934242"...
0x18002c285  mov     [rbp+hObject], 0
0x18002c28d  mov     [rbp+StringSid], rax
0x18002c291  lea     rdx, [rbp+hObject]; TokenHandle
0x18002c295  lea     rax, StringSid; "S-1-5-80-3055155277-3816794035-39940655"...
0x18002c29c  mov     [rbp+hMem], 0
0x18002c2a4  mov     [rbp+var_18], rax
0x18002c2a8  mov     r15, rcx
0x18002c2ab  lea     rax, aS1532544; "S-1-5-32-544"
0x18002c2b2  mov     [rbp+var_10], rax
0x18002c2b6  call    GetRpcCallerToken
0x18002c2bb  mov     ebx, eax
0x18002c2bd  test    eax, eax
0x18002c2bf  jns     short loc_18002C2DA
0x18002c2c1  mov     r8d, eax
0x18002c2c4  lea     rdx, aFailedToGetRpc; "Failed to get RPC caller token 0x%x"
0x18002c2cb  mov     ecx, 100000h
0x18002c2d0  call    EventWriteError0
0x18002c2d5  jmp     loc_18002C46C
0x18002c2da  xor     ebx, ebx
0x18002c2dc  cmp     ebx, 3
0x18002c2df  jnb     short loc_18002C35E
0x18002c2e1  mov     rcx, [rbp+hMem]; hMem
0x18002c2e5  movsxd  rax, ebx
0x18002c2e8  mov     rsi, [rbp+rax*8+StringSid]
0x18002c2ed  test    rcx, rcx
0x18002c2f0  jz      short loc_18002C306
0x18002c2f2  call    cs:__imp_LocalFree
0x18002c2f9  nop     dword ptr [rax+rax+00h]
0x18002c2fe  mov     [rbp+hMem], 0
0x18002c306  lea     rdx, [rbp+hMem]; Sid
0x18002c30a  mov     rcx, rsi; StringSid
0x18002c30d  call    cs:__imp_ConvertStringSidToSidW
0x18002c314  nop     dword ptr [rax+rax+00h]
0x18002c319  test    eax, eax
0x18002c31b  jnz     short loc_18002C342
0x18002c31d  call    cs:__imp_GetLastError
0x18002c324  nop     dword ptr [rax+rax+00h]
0x18002c329  mov     r8, rsi
0x18002c32c  lea     rdx, aFailedToGetSid; "Failed to get SID for %ws 0x%x"
0x18002c333  mov     r9d, eax
0x18002c336  mov     ecx, 100000h
0x18002c33b  call    EventWriteError0
0x18002c340  jmp     short loc_18002C353
0x18002c342  mov     rdx, [rbp+hMem]
0x18002c346  mov     rcx, [rbp+hObject]
0x18002c34a  call    IsSidOnToken
0x18002c34f  test    eax, eax
0x18002c351  jnz     short loc_18002C357
0x18002c353  inc     ebx
0x18002c355  jmp     short loc_18002C2DC
0x18002c357  xor     ebx, ebx
0x18002c359  jmp     loc_18002C46C
0x18002c35e  mov     ebx, 208h
0x18002c363  mov     ecx, ebx; dwBytes
0x18002c365  call    MALLOC
0x18002c36a  mov     ecx, ebx; dwBytes
0x18002c36c  mov     r14, rax
0x18002c36f  call    MALLOC
0x18002c374  mov     rsi, rax
0x18002c377  test    r14, r14
0x18002c37a  jz      loc_18002C43C
0x18002c380  test    rax, rax
0x18002c383  jz      loc_18002C43C
0x18002c389  mov     edx, 104h; uSize
0x18002c38e  mov     rcx, rax; lpBuffer
0x18002c391  call    cs:__imp_GetSystemDirectoryW
0x18002c398  nop     dword ptr [rax+rax+00h]
0x18002c39d  test    eax, eax
0x18002c39f  jnz     short loc_18002C3D5
0x18002c3a1  call    cs:__imp_GetLastError
0x18002c3a8  nop     dword ptr [rax+rax+00h]
0x18002c3ad  mov     ebx, eax
0x18002c3af  test    eax, eax
0x18002c3b1  jle     short loc_18002C3BC
0x18002c3b3  movzx   ebx, ax
0x18002c3b6  or      ebx, 80070000h
0x18002c3bc  mov     r8d, ebx
0x18002c3bf  lea     rdx, aFailedToGetSys; "Failed to get system path 0x%x"
0x18002c3c6  mov     ecx, 100000h
0x18002c3cb  call    EventWriteError0
0x18002c3d0  jmp     loc_18002C457
0x18002c3d5  lea     r8, aMsraExe; "\\msra.exe"
0x18002c3dc  mov     edx, 104h; cchDest
0x18002c3e1  mov     rcx, rsi; pszDest
0x18002c3e4  call    StringCchCatW
0x18002c3e9  mov     ebx, eax
0x18002c3eb  test    eax, eax
0x18002c3ed  jns     short loc_18002C3FB
0x18002c3ef  mov     r8d, eax
0x18002c3f2  lea     rdx, aFailedToConcat; "Failed to concat system path 0x%x"
0x18002c3f9  jmp     short loc_18002C3C6
0x18002c3fb  mov     r8d, 104h
0x18002c401  mov     rdx, r14
0x18002c404  mov     rcx, r15
0x18002c407  call    GetCallerName
0x18002c40c  mov     ebx, eax
0x18002c40e  test    eax, eax
0x18002c410  jns     short loc_18002C41E
0x18002c412  mov     r8d, eax
0x18002c415  lea     rdx, aFailedToGetCal; "Failed to get caller name 0x%x"
0x18002c41c  jmp     short loc_18002C3C6
0x18002c41e  mov     rdx, rsi
0x18002c421  mov     rcx, r14
0x18002c424  call    cs:__imp__o__wcsicmp
0x18002c42b  nop     dword ptr [rax+rax+00h]
0x18002c430  neg     eax
0x18002c432  sbb     ebx, ebx
0x18002c434  and     ebx, 80070005h
0x18002c43a  jmp     short loc_18002C457
0x18002c43c  lea     rdx, aFailedToAllocE; "Failed to alloc executable and system p"...
0x18002c443  mov     ecx, 100000h
0x18002c448  call    EventWriteError0
0x18002c44d  mov     ebx, 8007000Eh
0x18002c452  test    r14, r14
0x18002c455  jz      short loc_18002C45F
0x18002c457  mov     rcx, r14
0x18002c45a  call    FREE
0x18002c45f  test    rsi, rsi
0x18002c462  jz      short loc_18002C46C
0x18002c464  mov     rcx, rsi
0x18002c467  call    FREE
0x18002c46c  mov     rcx, [rbp+hMem]; hMem
0x18002c470  test    rcx, rcx
0x18002c473  jz      short loc_18002C481
0x18002c475  call    cs:__imp_LocalFree
0x18002c47c  nop     dword ptr [rax+rax+00h]
0x18002c481  mov     rcx, [rbp+hObject]; hObject
0x18002c485  test    rcx, rcx
0x18002c488  jz      short loc_18002C496
0x18002c48a  call    cs:__imp_CloseHandle
0x18002c491  nop     dword ptr [rax+rax+00h]
0x18002c496  mov     rsi, [rsp+40h+arg_18]
0x18002c49b  mov     eax, ebx
0x18002c49d  mov     rbx, [rsp+40h+arg_0]
0x18002c4a2  add     rsp, 40h
0x18002c4a6  pop     r15
0x18002c4a8  pop     r14
0x18002c4aa  pop     rbp
0x18002c4ab  retn
```
