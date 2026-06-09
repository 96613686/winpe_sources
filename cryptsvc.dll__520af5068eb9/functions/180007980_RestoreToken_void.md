# RestoreToken(void *)

- ea: `0x180007980`
- end: `0x1800079c8`
- name: `?RestoreToken@@YAXPEAX@Z`
- size: `72`
- prototype: `void __fastcall(HANDLE hObject)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004c90`
- `0x180005700`
- `0x180006aa0`
- `0x180008a10`
- `0x180008df0`
- `0x18000fe44`

## callees

- `0x180004180`
- `0x180007980`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800079b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800079b8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800079c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800079c0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180007992`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180007992`

## pseudocode

```c
void __fastcall RestoreToken(HANDLE hObject)
{
  BOOL v2; // ebx
  DWORD LastError; // eax

  v2 = SetThreadToken(0, hObject);
  if ( hObject )
    I_UrlCacheCloseHandle(hObject);
  if ( !v2 )
  {
    LastError = GetLastError();
    SetLastError(LastError);
  }
}

```

## disassembly

```asm
0x180007980  mov     [rsp+arg_0], rbx
0x180007985  push    rdi
0x180007986  sub     rsp, 20h
0x18000798a  mov     rdi, rcx
0x18000798d  mov     rdx, rcx; Token
0x180007990  xor     ecx, ecx; Thread
0x180007992  call    cs:__imp_SetThreadToken
0x180007998  mov     ebx, eax
0x18000799a  test    rdi, rdi
0x18000799d  jnz     short loc_1800079AE
0x18000799f  test    ebx, ebx
0x1800079a1  jz      short loc_1800079B8
0x1800079a3  mov     rbx, [rsp+28h+arg_0]
0x1800079a8  add     rsp, 20h
0x1800079ac  pop     rdi
0x1800079ad  retn
0x1800079ae  mov     rcx, rdi; hObject
0x1800079b1  call    I_UrlCacheCloseHandle
0x1800079b6  jmp     short loc_18000799F
0x1800079b8  call    cs:__imp_GetLastError
0x1800079be  mov     ecx, eax; dwErrCode
0x1800079c0  call    cs:__imp_SetLastError
0x1800079c6  jmp     short loc_1800079A3
```
