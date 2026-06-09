# _PreFetchTimerCallback

- ea: `0x18001f480`
- end: `0x18001f4f3`
- name: `_PreFetchTimerCallback`
- size: `115`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, HANDLE *Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task`

## callees

- `0x180005900`
- `0x18001e834`
- `0x18001f054`
- `0x18001f480`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f4e2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f4e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f4da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f4da`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001f4c1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001f4c1`

## pseudocode

```c
void __fastcall PreFetchTimerCallback(PTP_CALLBACK_INSTANCE Instance, HANDLE *Context, PTP_TIMER Timer)
{
  int v4; // ebx
  CTVOAgent *v5; // rcx
  DWORD LastError; // eax

  if ( Context )
  {
    v4 = ImpersonateToken(Context[1]);
    CTVOAgent::PreFetchCrl(v5, (struct _CRL_PRE_FETCH_ENTRY *)Context);
    if ( v4 )
    {
      if ( !SetThreadToken(0, 0) )
      {
        LastError = GetLastError();
        SetLastError(LastError);
      }
    }
  }
}

```

## disassembly

```asm
0x18001f480  mov     [rsp+arg_0], rbx
0x18001f485  push    rdi
0x18001f486  sub     rsp, 20h
0x18001f48a  mov     [rsp+28h+Token], 0
0x18001f493  mov     rdi, rdx
0x18001f496  test    rdx, rdx
0x18001f499  jz      short loc_18001F4E8
0x18001f49b  mov     rcx, [rdi+8]; Token
0x18001f49f  lea     rdx, [rsp+28h+Token]
0x18001f4a4  call    _ImpersonateToken
0x18001f4a9  mov     rdx, rdi; struct _CRL_PRE_FETCH_ENTRY *
0x18001f4ac  mov     ebx, eax
0x18001f4ae  call    ?PreFetchCrl@CTVOAgent@@QEAAXPEAU_CRL_PRE_FETCH_ENTRY@@@Z; CTVOAgent::PreFetchCrl(_CRL_PRE_FETCH_ENTRY *)
0x18001f4b3  test    ebx, ebx
0x18001f4b5  jz      short loc_18001F4E8
0x18001f4b7  mov     rbx, [rsp+28h+Token]
0x18001f4bc  xor     ecx, ecx; Thread
0x18001f4be  mov     rdx, rbx; Token
0x18001f4c1  call    cs:__imp_SetThreadToken
0x18001f4c7  mov     edi, eax
0x18001f4c9  test    rbx, rbx
0x18001f4cc  jz      short loc_18001F4D6
0x18001f4ce  mov     rcx, rbx; hObject
0x18001f4d1  call    I_UrlCacheCloseHandle
0x18001f4d6  test    edi, edi
0x18001f4d8  jnz     short loc_18001F4E8
0x18001f4da  call    cs:__imp_GetLastError
0x18001f4e0  mov     ecx, eax; dwErrCode
0x18001f4e2  call    cs:__imp_SetLastError
0x18001f4e8  mov     rbx, [rsp+28h+arg_0]
0x18001f4ed  add     rsp, 20h
0x18001f4f1  pop     rdi
0x18001f4f2  retn
```
