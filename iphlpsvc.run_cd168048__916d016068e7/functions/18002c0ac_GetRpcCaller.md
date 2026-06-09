# GetRpcCaller

- ea: `0x18002c0ac`
- end: `0x18002c25f`
- name: `GetRpcCaller`
- size: `435`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002bd70`

## callees

- `0x1800190e0`
- `0x18002c0ac`
- `0x18002c4b4`
- `0x18002c720`
- `0x180041558`
- `0x180042220`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18002c215`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18002c215`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c1be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c1be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c22e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c22e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c243`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c243`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002c18a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002c1ae`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002c18a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002c1ae`

## string_xrefs

- `0x18002c0e9`: `Failed to get RPC caller token 0x%x`
- `0x18002c1dc`: `Failed to get SID 0x%x`

## pseudocode

```c
__int64 __fastcall GetRpcCaller(void *a1, int a2, wchar_t *a3, unsigned int *a4)
{
  int RpcCallerToken; // eax
  int v9; // ebx
  int v10; // edi
  int v11; // edi
  int CallerName; // eax
  size_t v13; // rdx
  const wchar_t *v14; // r9
  signed int LastError; // eax
  PSID Sid; // [rsp+40h] [rbp-28h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-20h] BYREF
  size_t pcchRemaining; // [rsp+50h] [rbp-18h] BYREF
  STRSAFE_LPWSTR ppszDestEnd; // [rsp+58h] [rbp-10h] BYREF

  hObject = 0;
  Sid = 0;
  RpcCallerToken = GetRpcCallerToken(a1, &hObject);
  v9 = RpcCallerToken;
  if ( RpcCallerToken < 0 )
  {
    EventWriteError0(0x100000, L"Failed to get RPC caller token 0x%x", (unsigned int)RpcCallerToken);
    goto LABEL_20;
  }
  v10 = a2 - 1;
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( v11 )
    {
      if ( v11 == 1 )
      {
        v13 = *a4;
        ppszDestEnd = 0;
        pcchRemaining = 0;
        v9 = StringCchPrintfExW(a3, v13, &ppszDestEnd, &pcchRemaining, 0, L"%ws: ", L"MSRA");
        GetCallerName(a1, ppszDestEnd, (unsigned int)pcchRemaining);
        goto LABEL_18;
      }
      CallerName = GetCallerName(a1, a3, *a4);
LABEL_17:
      v9 = CallerName;
LABEL_18:
      if ( v9 >= 0 )
        *a4 = wcsnlen(a3, *a4) + 1;
      goto LABEL_20;
    }
    if ( ConvertStringSidToSidW(L"S-1-5-80-3055155277-3816794035-3994065555-2874236192-2193176987", &Sid) )
    {
      v14 = L"DoSvc";
LABEL_16:
      CallerName = GetStringForService(a1, hObject, Sid, v14, a3, *a4);
      goto LABEL_17;
    }
  }
  else if ( ConvertStringSidToSidW(L"S-1-5-80-1352715831-1104254428-97934242-2131353953-1898040052", &Sid) )
  {
    v14 = L"XboxNetApiSvc";
    goto LABEL_16;
  }
  LastError = GetLastError();
  v9 = LastError;
  if ( LastError > 0 )
    v9 = (unsigned __int16)LastError | 0x80070000;
  EventWriteError0(0x100000, L"Failed to get SID 0x%x", (unsigned int)v9);
LABEL_20:
  if ( hObject )
    CloseHandle(hObject);
  if ( Sid )
    LocalFree(Sid);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18002c0ac  push    rbp
0x18002c0ae  push    rbx
0x18002c0af  push    rsi
0x18002c0b0  push    rdi
0x18002c0b1  push    r14
0x18002c0b3  push    r15
0x18002c0b5  mov     rbp, rsp
0x18002c0b8  sub     rsp, 68h
0x18002c0bc  mov     edi, edx
0x18002c0be  mov     [rbp+hObject], 0
0x18002c0c6  lea     rdx, [rbp+hObject]; TokenHandle
0x18002c0ca  mov     [rbp+Sid], 0
0x18002c0d2  mov     rsi, r9
0x18002c0d5  mov     r14, r8
0x18002c0d8  mov     r15, rcx
0x18002c0db  call    GetRpcCallerToken
0x18002c0e0  mov     ebx, eax
0x18002c0e2  test    eax, eax
0x18002c0e4  jns     short loc_18002C0FF
0x18002c0e6  mov     r8d, eax
0x18002c0e9  lea     rdx, aFailedToGetRpc; "Failed to get RPC caller token 0x%x"
0x18002c0f0  mov     ecx, 100000h
0x18002c0f5  call    EventWriteError0
0x18002c0fa  jmp     loc_18002C225
0x18002c0ff  sub     edi, 1
0x18002c102  jz      loc_18002C1A3
0x18002c108  sub     edi, 1
0x18002c10b  jz      short loc_18002C17F
0x18002c10d  cmp     edi, 1
0x18002c110  jz      short loc_18002C125
0x18002c112  mov     r8d, [rsi]
0x18002c115  mov     rdx, r14
0x18002c118  mov     rcx, r15
0x18002c11b  call    GetCallerName
0x18002c120  jmp     loc_18002C20A
0x18002c125  mov     edx, [rsi]; cchDest
0x18002c127  lea     rax, aMsra; "MSRA"
0x18002c12e  mov     [rsp+68h+var_38], rax
0x18002c133  lea     r9, [rbp+pcchRemaining]; pcchRemaining
0x18002c137  lea     rax, aWs; "%ws: "
0x18002c13e  mov     [rbp+ppszDestEnd], 0
0x18002c146  mov     [rsp+68h+pszFormat], rax; pszFormat
0x18002c14b  lea     r8, [rbp+ppszDestEnd]; ppszDestEnd
0x18002c14f  mov     rcx, r14; pszDest
0x18002c152  mov     qword ptr [rsp+68h+dwFlags], 0; dwFlags
0x18002c15b  mov     [rbp+pcchRemaining], 0
0x18002c163  call    StringCchPrintfExW
0x18002c168  mov     r8d, dword ptr [rbp+pcchRemaining]
0x18002c16c  mov     rcx, r15
0x18002c16f  mov     rdx, [rbp+ppszDestEnd]
0x18002c173  mov     ebx, eax
0x18002c175  call    GetCallerName
0x18002c17a  jmp     loc_18002C20C
0x18002c17f  lea     rdx, [rbp+Sid]; Sid
0x18002c183  lea     rcx, StringSid; "S-1-5-80-3055155277-3816794035-39940655"...
0x18002c18a  call    cs:__imp_ConvertStringSidToSidW
0x18002c191  nop     dword ptr [rax+rax+00h]
0x18002c196  test    eax, eax
0x18002c198  jz      short loc_18002C1BE
0x18002c19a  lea     r9, aDosvc; "DoSvc"
0x18002c1a1  jmp     short loc_18002C1EF
0x18002c1a3  lea     rdx, [rbp+Sid]; Sid
0x18002c1a7  lea     rcx, aS1580135271583; "S-1-5-80-1352715831-1104254428-97934242"...
0x18002c1ae  call    cs:__imp_ConvertStringSidToSidW
0x18002c1b5  nop     dword ptr [rax+rax+00h]
0x18002c1ba  test    eax, eax
0x18002c1bc  jnz     short loc_18002C1E8
0x18002c1be  call    cs:__imp_GetLastError
0x18002c1c5  nop     dword ptr [rax+rax+00h]
0x18002c1ca  mov     ebx, eax
0x18002c1cc  test    eax, eax
0x18002c1ce  jle     short loc_18002C1D9
0x18002c1d0  movzx   ebx, ax
0x18002c1d3  or      ebx, 80070000h
0x18002c1d9  mov     r8d, ebx
0x18002c1dc  lea     rdx, aFailedToGetSid_0; "Failed to get SID 0x%x"
0x18002c1e3  jmp     loc_18002C0F0
0x18002c1e8  lea     r9, aXboxnetapisvc; "XboxNetApiSvc"
0x18002c1ef  mov     eax, [rsi]
0x18002c1f1  mov     rcx, r15
0x18002c1f4  mov     r8, [rbp+Sid]
0x18002c1f8  mov     rdx, [rbp+hObject]
0x18002c1fc  mov     dword ptr [rsp+68h+pszFormat], eax
0x18002c200  mov     qword ptr [rsp+68h+dwFlags], r14
0x18002c205  call    GetStringForService
0x18002c20a  mov     ebx, eax
0x18002c20c  test    ebx, ebx
0x18002c20e  js      short loc_18002C225
0x18002c210  mov     edx, [rsi]; MaxCount
0x18002c212  mov     rcx, r14; Source
0x18002c215  call    cs:__imp_wcsnlen
0x18002c21c  nop     dword ptr [rax+rax+00h]
0x18002c221  inc     eax
0x18002c223  mov     [rsi], eax
0x18002c225  mov     rcx, [rbp+hObject]; hObject
0x18002c229  test    rcx, rcx
0x18002c22c  jz      short loc_18002C23A
0x18002c22e  call    cs:__imp_CloseHandle
0x18002c235  nop     dword ptr [rax+rax+00h]
0x18002c23a  mov     rcx, [rbp+Sid]; hMem
0x18002c23e  test    rcx, rcx
0x18002c241  jz      short loc_18002C24F
0x18002c243  call    cs:__imp_LocalFree
0x18002c24a  nop     dword ptr [rax+rax+00h]
0x18002c24f  mov     eax, ebx
0x18002c251  add     rsp, 68h
0x18002c255  pop     r15
0x18002c257  pop     r14
0x18002c259  pop     rdi
0x18002c25a  pop     rsi
0x18002c25b  pop     rbx
0x18002c25c  pop     rbp
0x18002c25d  retn
```
