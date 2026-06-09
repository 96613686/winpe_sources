# OleCheckClipboardCallerIntegrityLevel(void)

- ea: `0x18001e150`
- end: `0x18001e21d`
- name: `?OleCheckClipboardCallerIntegrityLevel@@YAJXZ`
- size: `205`
- prototype: `HRESULT __fastcall()`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001dbc0`
- `0x18001df10`
- `0x18001dfb0`
- `0x18001f560`
- `0x18008b530`

## callees

- `0x18001c778`
- `0x18001e150`
- `0x18001e25c`
- `0x180034f78`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001e193`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001e193`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001e178`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001e178`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e1b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001e1b9`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001e15a`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18001e15a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001e1d1`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18001e1d1`

## pseudocode

```c
__int64 __fastcall OleCheckClipboardCallerIntegrityLevel()
{
  int ThreadIntegrityLevel; // ebx
  unsigned int v1; // edi
  HANDLE CurrentThread; // rax
  _TOKEN_INFORMATION_CLASS v3; // edx
  unsigned int dwLevel; // [rsp+30h] [rbp+8h] BYREF
  void *hToken; // [rsp+38h] [rbp+10h] BYREF

  ThreadIntegrityLevel = CoImpersonateClient();
  if ( ThreadIntegrityLevel >= 0 )
  {
    hToken = 0;
    v1 = 0;
    dwLevel = 0;
    CurrentThread = GetCurrentThread();
    if ( OpenThreadToken(CurrentThread, 0x18u, 1, &hToken) )
    {
      ThreadIntegrityLevel = IsTokenBoolPresent(hToken, v3, (int *)&dwLevel);
      CloseHandle(hToken);
      if ( ThreadIntegrityLevel < 0 )
        goto LABEL_8;
      v1 = dwLevel;
    }
    if ( v1 )
    {
LABEL_6:
      CoRevertToSelf();
      return (unsigned int)ThreadIntegrityLevel;
    }
LABEL_8:
    dwLevel = 0;
    ThreadIntegrityLevel = GetThreadIntegrityLevel(&dwLevel);
    if ( ThreadIntegrityLevel >= 0 && dwLevel < 0x2000 )
    {
      ThreadIntegrityLevel = -2147024891;
      OleInternalOriginateError(-2147024891, 0x134u);
    }
    goto LABEL_6;
  }
  return (unsigned int)ThreadIntegrityLevel;
}

```

## disassembly

```asm
0x18001e150  mov     [rsp+arg_10], rbx
0x18001e155  push    rdi
0x18001e156  sub     rsp, 20h
0x18001e15a  call    cs:__imp_CoImpersonateClient
0x18001e161  nop     dword ptr [rax+rax+00h]
0x18001e166  mov     ebx, eax
0x18001e168  test    eax, eax
0x18001e16a  js      short loc_18001E1DD
0x18001e16c  and     [rsp+28h+hToken], 0
0x18001e172  xor     edi, edi
0x18001e174  mov     [rsp+28h+dwLevel], edi
0x18001e178  call    cs:__imp_GetCurrentThread
0x18001e17f  nop     dword ptr [rax+rax+00h]
0x18001e184  mov     rcx, rax; ThreadHandle
0x18001e187  lea     r9, [rsp+28h+hToken]; TokenHandle
0x18001e18c  lea     edx, [rdi+18h]; DesiredAccess
0x18001e18f  lea     r8d, [rdi+1]; OpenAsSelf
0x18001e193  call    cs:__imp_OpenThreadToken
0x18001e19a  nop     dword ptr [rax+rax+00h]
0x18001e19f  test    eax, eax
0x18001e1a1  jz      short loc_18001E1CD
0x18001e1a3  mov     rcx, [rsp+28h+hToken]; hToken
0x18001e1a8  lea     r8, [rsp+28h+dwLevel]; hToken
0x18001e1ad  call    ?IsTokenBoolPresent@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAH@Z; IsTokenBoolPresent(void *,_TOKEN_INFORMATION_CLASS,int *)
0x18001e1b2  mov     rcx, [rsp+28h+hToken]; hObject
0x18001e1b7  mov     ebx, eax
0x18001e1b9  call    cs:__imp_CloseHandle
0x18001e1c0  nop     dword ptr [rax+rax+00h]
0x18001e1c5  test    ebx, ebx
0x18001e1c7  js      short loc_18001E1EB
0x18001e1c9  mov     edi, [rsp+28h+dwLevel]
0x18001e1cd  test    edi, edi
0x18001e1cf  jz      short loc_18001E1EB
0x18001e1d1  call    cs:__imp_CoRevertToSelf
0x18001e1d8  nop     dword ptr [rax+rax+00h]
0x18001e1dd  mov     eax, ebx
0x18001e1df  mov     rbx, [rsp+28h+arg_10]
0x18001e1e4  add     rsp, 20h
0x18001e1e8  pop     rdi
0x18001e1e9  retn
0x18001e1eb  and     [rsp+28h+dwLevel], 0
0x18001e1f0  lea     rcx, [rsp+28h+dwLevel]; pdwIntegrityLevel
0x18001e1f5  call    ?GetThreadIntegrityLevel@@YAJPEAK@Z; GetThreadIntegrityLevel(ulong *)
0x18001e1fa  mov     ebx, eax
0x18001e1fc  test    eax, eax
0x18001e1fe  js      short loc_18001E1D1
0x18001e200  cmp     [rsp+28h+dwLevel], 2000h
0x18001e208  jnb     short loc_18001E1D1
0x18001e20a  mov     ebx, 80070005h
0x18001e20f  mov     edx, 134h; messageID
0x18001e214  mov     ecx, ebx; hr
0x18001e216  call    ?OleInternalOriginateError@@YAXJG@Z; OleInternalOriginateError(long,ushort)
0x18001e21b  jmp     short loc_18001E1D1
```
