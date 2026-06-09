# EdpInlSetProcessTlsIndex(ulong *)

- ea: `0x1800880bc`
- end: `0x1800881b7`
- name: `?EdpInlSetProcessTlsIndex@@YAJPEAK@Z`
- size: `251`
- prototype: `HRESULT __fastcall(unsigned int *TlsIndex)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task`

## callers

- `0x180088044`

## callees

- `0x180047484`
- `0x180087f74`
- `0x1800880bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088106`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180088106`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180088193`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180088193`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x1800880f3`
- `api-ms-win-core-processthreads-l1-1-0!TlsAlloc` at `0x1800880f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180088137`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180088137`
- `ext-ms-win-feclient-encryptedfile-l1-1-0!EdpSetCredServiceInfo` at `0x180088161`
- `ext-ms-win-feclient-encryptedfile-l1-1-0!EdpSetCredServiceInfo` at `0x180088161`

## pseudocode

```c
__int64 __fastcall EdpInlSetProcessTlsIndex(unsigned int *TlsIndex)
{
  int ProcessTlsIndex; // ebx
  DWORD v3; // edi
  signed int LastError; // eax
  void *v5; // rcx
  _EDP_CRED_SVC_INFO EdpCredSvcInfo; // [rsp+30h] [rbp-98h] BYREF

  memset_0(&EdpCredSvcInfo.ConsumerDplCredentialDelete + 2, 0, 0x78u);
  if ( TlsIndex )
  {
    *TlsIndex = -1;
    v3 = TlsAlloc();
    if ( v3 != -1 )
    {
      EdpCredSvcInfo.cbSize = 136;
      EdpCredSvcInfo.eInfoType = EdpCredSvcInfo_SetProcessTlsIndex;
      EdpCredSvcInfo.DplUserCredentialInfo.DplUserId = __PAIR64__(v3, GetCurrentProcessId());
      ProcessTlsIndex = EdpSetCredServiceInfo(7, 0, 0, 0, &EdpCredSvcInfo);
      if ( ProcessTlsIndex >= 0 )
      {
        ProcessTlsIndex = EdpInlGetProcessTlsIndex(v5, TlsIndex);
        if ( ProcessTlsIndex >= 0 )
        {
          if ( *TlsIndex == -1 )
          {
            ProcessTlsIndex = -2147418113;
          }
          else if ( v3 == *TlsIndex )
          {
            return (unsigned int)ProcessTlsIndex;
          }
        }
      }
      TlsFree(v3);
      return (unsigned int)ProcessTlsIndex;
    }
    LastError = GetLastError();
    ProcessTlsIndex = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    return (unsigned int)-2147467261;
  }
  return (unsigned int)ProcessTlsIndex;
}

```

## disassembly

```asm
0x1800880bc  mov     [rsp+arg_0], rbx
0x1800880c1  mov     [rsp+arg_8], rsi
0x1800880c6  push    rdi
0x1800880c7  sub     rsp, 0C0h
0x1800880ce  xor     edx, edx; Val
0x1800880d0  mov     rsi, TlsIndex
0x1800880d3  lea     TlsIndex, [rsp+0C8h+EdpCredSvcInfo.___u2+8]; void *
0x1800880d8  lea     r8d, [rdx+78h]; Size
0x1800880dc  call    memset_0
0x1800880e1  test    rsi, rsi
0x1800880e4  jnz     short loc_1800880F0
0x1800880e6  mov     ebx, 80004003h
0x1800880eb  jmp     loc_18008819F
0x1800880f0  or      dword ptr [rsi], 0FFFFFFFFh
0x1800880f3  call    cs:__imp_TlsAlloc
0x1800880fa  nop     dword ptr [rax+rax+00h]
0x1800880ff  mov     edi, eax
0x180088101  cmp     eax, 0FFFFFFFFh
0x180088104  jnz     short loc_180088127
0x180088106  call    cs:__imp_GetLastError
0x18008810d  nop     dword ptr [rax+rax+00h]
0x180088112  mov     ebx, eax
0x180088114  test    eax, eax
0x180088116  jle     loc_18008819F
0x18008811c  movzx   ebx, ax
0x18008811f  or      ebx, 80070000h
0x180088125  jmp     short loc_18008819F
0x180088127  mov     [rsp+0C8h+EdpCredSvcInfo.cbSize], 88h
0x18008812f  mov     [rsp+0C8h+EdpCredSvcInfo.eInfoType], 7
0x180088137  call    cs:__imp_GetCurrentProcessId
0x18008813e  nop     dword ptr [rax+rax+00h]
0x180088143  mov     ecx, [rsp+0C8h+EdpCredSvcInfo.eInfoType]
0x180088147  xor     r9d, r9d
0x18008814a  mov     dword ptr [rsp+0C8h+EdpCredSvcInfo.___u2], eax
0x18008814e  xor     r8d, r8d
0x180088151  lea     rax, [rsp+0C8h+EdpCredSvcInfo]
0x180088156  mov     dword ptr [rsp+0C8h+EdpCredSvcInfo.___u2+4], edi
0x18008815a  xor     edx, edx
0x18008815c  mov     [rsp+0C8h+var_A8], rax
0x180088161  call    cs:__imp_EdpSetCredServiceInfo
0x180088168  nop     dword ptr [rax+rax+00h]
0x18008816d  mov     ebx, eax
0x18008816f  test    eax, eax
0x180088171  js      short loc_180088191
0x180088173  mov     rdx, rsi; hProcess
0x180088176  call    ?EdpInlGetProcessTlsIndex@@YAJPEAXPEAK@Z; EdpInlGetProcessTlsIndex(void *,ulong *)
0x18008817b  mov     ebx, eax
0x18008817d  test    eax, eax
0x18008817f  js      short loc_180088191
0x180088181  cmp     dword ptr [rsi], 0FFFFFFFFh
0x180088184  jnz     short loc_18008818D
0x180088186  mov     ebx, 8000FFFFh
0x18008818b  jmp     short loc_180088191
0x18008818d  cmp     edi, [rsi]
0x18008818f  jz      short loc_18008819F
0x180088191  mov     ecx, edi; dwTlsIndex
0x180088193  call    cs:__imp_TlsFree
0x18008819a  nop     dword ptr [rax+rax+00h]
0x18008819f  lea     r11, [rsp+0C8h+var_8]
0x1800881a7  mov     eax, ebx
0x1800881a9  mov     rbx, [r11+10h]
0x1800881ad  mov     rsi, [r11+18h]
0x1800881b1  mov     rsp, r11
0x1800881b4  pop     rdi
0x1800881b5  retn
```
