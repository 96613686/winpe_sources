# wil::details::RevertImpersonateToken(void *)

- ea: `0x1800b8154`
- end: `0x1800b8186`
- name: `?RevertImpersonateToken@details@wil@@YAXPEAX@Z`
- size: `50`
- prototype: `void __fastcall(HANDLE hObject, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800a7fbc`
- `0x1800c3440`

## callees

- `0x18005d994`
- `0x1800b8154`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800b8162`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800b8162`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b817a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800b817a`

## pseudocode

```c
void __fastcall wil::details::RevertImpersonateToken(HANDLE hObject, void *a2)
{
  wil::details::in1diag3 *v3; // rcx

  if ( !SetThreadToken(0, hObject) )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v3);
  if ( hObject )
    CloseHandle(hObject);
}

```

## disassembly

```asm
0x1800b8154  push    rbx
0x1800b8156  sub     rsp, 20h
0x1800b815a  mov     rbx, rcx
0x1800b815d  mov     rdx, rcx; Token
0x1800b8160  xor     ecx, ecx; Thread
0x1800b8162  call    cs:__imp_SetThreadToken
0x1800b8168  test    eax, eax
0x1800b816a  jnz     short loc_1800B8172
0x1800b816c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800b8172  test    rbx, rbx
0x1800b8175  jz      short loc_1800B8180
0x1800b8177  mov     rcx, rbx; hObject
0x1800b817a  call    cs:__imp_CloseHandle
0x1800b8180  add     rsp, 20h
0x1800b8184  pop     rbx
0x1800b8185  retn
```
