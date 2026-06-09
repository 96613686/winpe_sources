# OnexQueryUserToken

- ea: `0x18001abb4`
- end: `0x18001ac06`
- name: `OnexQueryUserToken`
- size: `82`
- prototype: `__int64 __fastcall(ULONG SessionId, PHANDLE phToken)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180029668`
- `0x18002da24`

## callees

- `0x18001abb4`
- `0x180020ce0`
- `0x180020de4`
- `0x180028ef0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001abf3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001abf3`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18001abd1`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x18001abd1`

## pseudocode

```c
int __fastcall OnexQueryUserToken(ULONG SessionId, PHANDLE phToken)
{
  if ( (unsigned __int8)IsWTSQueryUserTokenPresent() )
    return WTSQueryUserToken(SessionId, phToken);
  if ( (unsigned __int8)IsQueryUserTokenPresent() )
    return QueryLoggedOnUserForSingleSessionDevice(SessionId, (__int64)phToken);
  SetLastError(0x32u);
  return 0;
}

```

## disassembly

```asm
0x18001abb4  mov     [rsp+arg_0], rbx
0x18001abb9  push    rdi
0x18001abba  sub     rsp, 20h
0x18001abbe  mov     rbx, rdx
0x18001abc1  mov     edi, ecx
0x18001abc3  call    IsWTSQueryUserTokenPresent
0x18001abc8  test    al, al
0x18001abca  jz      short loc_18001ABD9
0x18001abcc  mov     rdx, rbx; phToken
0x18001abcf  mov     ecx, edi; SessionId
0x18001abd1  call    cs:__imp_WTSQueryUserToken
0x18001abd7  jmp     short loc_18001ABFB
0x18001abd9  call    IsQueryUserTokenPresent
0x18001abde  test    al, al
0x18001abe0  jz      short loc_18001ABEE
0x18001abe2  mov     rdx, rbx
0x18001abe5  mov     ecx, edi
0x18001abe7  call    QueryLoggedOnUserForSingleSessionDevice
0x18001abec  jmp     short loc_18001ABFB
0x18001abee  mov     ecx, 32h ; '2'; dwErrCode
0x18001abf3  call    cs:__imp_SetLastError
0x18001abf9  xor     eax, eax
0x18001abfb  mov     rbx, [rsp+28h+arg_0]
0x18001ac00  add     rsp, 20h
0x18001ac04  pop     rdi
0x18001ac05  retn
```
