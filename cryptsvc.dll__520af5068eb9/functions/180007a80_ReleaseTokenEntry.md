# ReleaseTokenEntry

- ea: `0x180007a80`
- end: `0x180007ae8`
- name: `ReleaseTokenEntry`
- size: `104`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180002478`
- `0x1800026cc`
- `0x180006aa0`
- `0x1800089a0`
- `0x180008dc0`

## callees

- `0x180007a80`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ab8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007ab8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007acb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007acb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007ab2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007ab2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007ac3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007ac3`

## pseudocode

```c
void __fastcall ReleaseTokenEntry(__int64 *a1)
{
  __int64 v1; // rbx
  DWORD LastError; // edi

  v1 = *a1;
  if ( *a1 )
  {
    if ( *(_QWORD *)v1 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 8), 0xFFFFFFFF) != 1 )
      {
LABEL_6:
        *a1 = 0;
        return;
      }
      CloseHandle(*(HANDLE *)v1);
    }
    LastError = GetLastError();
    LocalFree((HLOCAL)v1);
    SetLastError(LastError);
    goto LABEL_6;
  }
}

```

## disassembly

```asm
0x180007a80  mov     [rsp+arg_8], rbx
0x180007a85  push    rsi
0x180007a86  sub     rsp, 20h
0x180007a8a  mov     rbx, [rcx]
0x180007a8d  mov     rsi, rcx
0x180007a90  test    rbx, rbx
0x180007a93  jz      short loc_180007ADD
0x180007a95  cmp     qword ptr [rbx], 0
0x180007a99  mov     [rsp+28h+arg_0], rdi
0x180007a9e  jz      short loc_180007AB8
0x180007aa0  mov     eax, 0FFFFFFFFh
0x180007aa5  lock xadd [rbx+8], eax
0x180007aaa  cmp     eax, 1
0x180007aad  jnz     short loc_180007AD1
0x180007aaf  mov     rcx, [rbx]; hObject
0x180007ab2  call    cs:__imp_CloseHandle
0x180007ab8  call    cs:__imp_GetLastError
0x180007abe  mov     rcx, rbx; hMem
0x180007ac1  mov     edi, eax
0x180007ac3  call    cs:__imp_LocalFree
0x180007ac9  mov     ecx, edi; dwErrCode
0x180007acb  call    cs:__imp_SetLastError
0x180007ad1  mov     rdi, [rsp+28h+arg_0]
0x180007ad6  mov     qword ptr [rsi], 0
0x180007add  mov     rbx, [rsp+28h+arg_8]
0x180007ae2  add     rsp, 20h
0x180007ae6  pop     rsi
0x180007ae7  retn
```
