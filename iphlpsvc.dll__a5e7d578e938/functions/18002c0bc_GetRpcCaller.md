# GetRpcCaller

- ea: `0x18002c0bc`
- end: `0x18002c26f`
- name: `GetRpcCaller`
- size: `435`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18002bd80`

## callees

- `0x1800190f0`
- `0x18002c0bc`
- `0x18002c4c4`
- `0x18002c730`
- `0x180041518`
- `0x1800421e0`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18002c225`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x18002c225`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c1ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002c1ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c23e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002c23e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c253`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002c253`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002c19a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002c1be`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002c19a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002c1be`

## string_xrefs

- `0x18002c0f9`: `Failed to get RPC caller token 0x%x`
- `0x18002c1ec`: `Failed to get SID 0x%x`

## pseudocode

```c
__int64 __fastcall GetRpcCaller(void *a1, int a2, wchar_t *a3, DWORD *a4)
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
        GetCallerName(a1, ppszDestEnd, pcchRemaining);
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
0x18002c0bc  push    rbp
0x18002c0be  push    rbx
0x18002c0bf  push    rsi
0x18002c0c0  push    rdi
0x18002c0c1  push    r14
0x18002c0c3  push    r15
0x18002c0c5  mov     rbp, rsp
0x18002c0c8  sub     rsp, 68h
0x18002c0cc  mov     edi, edx
0x18002c0ce  mov     [rbp+hObject], 0
0x18002c0d6  lea     rdx, [rbp+hObject]; TokenHandle
0x18002c0da  mov     [rbp+Sid], 0
0x18002c0e2  mov     rsi, r9
0x18002c0e5  mov     r14, r8
0x18002c0e8  mov     r15, rcx
0x18002c0eb  call    GetRpcCallerToken
0x18002c0f0  mov     ebx, eax
0x18002c0f2  test    eax, eax
0x18002c0f4  jns     short loc_18002C10F
0x18002c0f6  mov     r8d, eax
0x18002c0f9  lea     rdx, aFailedToGetRpc; "Failed to get RPC caller token 0x%x"
0x18002c100  mov     ecx, 100000h
0x18002c105  call    EventWriteError0
0x18002c10a  jmp     loc_18002C235
0x18002c10f  sub     edi, 1
0x18002c112  jz      loc_18002C1B3
0x18002c118  sub     edi, 1
0x18002c11b  jz      short loc_18002C18F
0x18002c11d  cmp     edi, 1
0x18002c120  jz      short loc_18002C135
0x18002c122  mov     r8d, [rsi]
0x18002c125  mov     rdx, r14
0x18002c128  mov     rcx, r15
0x18002c12b  call    GetCallerName
0x18002c130  jmp     loc_18002C21A
0x18002c135  mov     edx, [rsi]; cchDest
0x18002c137  lea     rax, aMsra; "MSRA"
0x18002c13e  mov     [rsp+68h+var_38], rax
0x18002c143  lea     r9, [rbp+pcchRemaining]; pcchRemaining
0x18002c147  lea     rax, aWs; "%ws: "
0x18002c14e  mov     [rbp+ppszDestEnd], 0
0x18002c156  mov     [rsp+68h+pszFormat], rax; pszFormat
0x18002c15b  lea     r8, [rbp+ppszDestEnd]; ppszDestEnd
0x18002c15f  mov     rcx, r14; pszDest
0x18002c162  mov     qword ptr [rsp+68h+dwFlags], 0; dwFlags
0x18002c16b  mov     [rbp+pcchRemaining], 0
0x18002c173  call    StringCchPrintfExW
0x18002c178  mov     r8d, dword ptr [rbp+pcchRemaining]
0x18002c17c  mov     rcx, r15
0x18002c17f  mov     rdx, [rbp+ppszDestEnd]
0x18002c183  mov     ebx, eax
0x18002c185  call    GetCallerName
0x18002c18a  jmp     loc_18002C21C
0x18002c18f  lea     rdx, [rbp+Sid]; Sid
0x18002c193  lea     rcx, StringSid; "S-1-5-80-3055155277-3816794035-39940655"...
0x18002c19a  call    cs:__imp_ConvertStringSidToSidW
0x18002c1a1  nop     dword ptr [rax+rax+00h]
0x18002c1a6  test    eax, eax
0x18002c1a8  jz      short loc_18002C1CE
0x18002c1aa  lea     r9, aDosvc; "DoSvc"
0x18002c1b1  jmp     short loc_18002C1FF
0x18002c1b3  lea     rdx, [rbp+Sid]; Sid
0x18002c1b7  lea     rcx, aS1580135271583; "S-1-5-80-1352715831-1104254428-97934242"...
0x18002c1be  call    cs:__imp_ConvertStringSidToSidW
0x18002c1c5  nop     dword ptr [rax+rax+00h]
0x18002c1ca  test    eax, eax
0x18002c1cc  jnz     short loc_18002C1F8
0x18002c1ce  call    cs:__imp_GetLastError
0x18002c1d5  nop     dword ptr [rax+rax+00h]
0x18002c1da  mov     ebx, eax
0x18002c1dc  test    eax, eax
0x18002c1de  jle     short loc_18002C1E9
0x18002c1e0  movzx   ebx, ax
0x18002c1e3  or      ebx, 80070000h
0x18002c1e9  mov     r8d, ebx
0x18002c1ec  lea     rdx, aFailedToGetSid_0; "Failed to get SID 0x%x"
0x18002c1f3  jmp     loc_18002C100
0x18002c1f8  lea     r9, aXboxnetapisvc; "XboxNetApiSvc"
0x18002c1ff  mov     eax, [rsi]
0x18002c201  mov     rcx, r15
0x18002c204  mov     r8, [rbp+Sid]
0x18002c208  mov     rdx, [rbp+hObject]
0x18002c20c  mov     dword ptr [rsp+68h+pszFormat], eax
0x18002c210  mov     qword ptr [rsp+68h+dwFlags], r14
0x18002c215  call    GetStringForService
0x18002c21a  mov     ebx, eax
0x18002c21c  test    ebx, ebx
0x18002c21e  js      short loc_18002C235
0x18002c220  mov     edx, [rsi]; MaxCount
0x18002c222  mov     rcx, r14; Source
0x18002c225  call    cs:__imp_wcsnlen
0x18002c22c  nop     dword ptr [rax+rax+00h]
0x18002c231  inc     eax
0x18002c233  mov     [rsi], eax
0x18002c235  mov     rcx, [rbp+hObject]; hObject
0x18002c239  test    rcx, rcx
0x18002c23c  jz      short loc_18002C24A
0x18002c23e  call    cs:__imp_CloseHandle
0x18002c245  nop     dword ptr [rax+rax+00h]
0x18002c24a  mov     rcx, [rbp+Sid]; hMem
0x18002c24e  test    rcx, rcx
0x18002c251  jz      short loc_18002C25F
0x18002c253  call    cs:__imp_LocalFree
0x18002c25a  nop     dword ptr [rax+rax+00h]
0x18002c25f  mov     eax, ebx
0x18002c261  add     rsp, 68h
0x18002c265  pop     r15
0x18002c267  pop     r14
0x18002c269  pop     rdi
0x18002c26a  pop     rsi
0x18002c26b  pop     rbx
0x18002c26c  pop     rbp
0x18002c26d  retn
```
