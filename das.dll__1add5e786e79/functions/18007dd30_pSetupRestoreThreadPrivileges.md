# pSetupRestoreThreadPrivileges

- ea: `0x18007dd30`
- end: `0x18007dd6e`
- name: `pSetupRestoreThreadPrivileges`
- size: `62`
- prototype: `__int64 __fastcall(HANDLE hObject)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, installer_update`

## callers

- `0x180022624`

## callees

- `0x18007dd10`
- `0x18007dd30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007dd40`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18007dd40`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18007dd4b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18007dd4b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007dd62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007dd62`

## pseudocode

```c
void __fastcall pSetupRestoreThreadPrivileges(HANDLE hObject)
{
  if ( hObject != (HANDLE)-1LL )
  {
    SetLastError(0);
    if ( !SetThreadToken(0, hObject) )
      pSpUtilsGetLastError();
    if ( hObject )
      CloseHandle(hObject);
  }
}

```

## disassembly

```asm
0x18007dd30  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18007dd34  jz      short locret_18007DD6D
0x18007dd36  push    rbx
0x18007dd37  sub     rsp, 20h
0x18007dd3b  mov     rbx, rcx
0x18007dd3e  xor     ecx, ecx; dwErrCode
0x18007dd40  call    cs:__imp_SetLastError
0x18007dd46  mov     rdx, rbx; Token
0x18007dd49  xor     ecx, ecx; Thread
0x18007dd4b  call    cs:__imp_SetThreadToken
0x18007dd51  test    eax, eax
0x18007dd53  jnz     short loc_18007DD5A
0x18007dd55  call    _pSpUtilsGetLastError
0x18007dd5a  test    rbx, rbx
0x18007dd5d  jz      short loc_18007DD68
0x18007dd5f  mov     rcx, rbx; hObject
0x18007dd62  call    cs:__imp_CloseHandle
0x18007dd68  add     rsp, 20h
0x18007dd6c  pop     rbx
0x18007dd6d  retn
```
