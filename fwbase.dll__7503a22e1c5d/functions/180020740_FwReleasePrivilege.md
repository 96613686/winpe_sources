# FwReleasePrivilege

- ea: `0x180020740`
- end: `0x1800207ea`
- name: `FwReleasePrivilege`
- size: `170`
- prototype: `__int64 __fastcall(HANDLE hObject)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x180020740`
- `0x1800214c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002077f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800207c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002077f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800207c1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002075c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18002075c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800207a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800207a5`

## pseudocode

```c
void __fastcall FwReleasePrivilege(HANDLE hObject)
{
  DWORD LastError; // eax
  __int64 v3; // r8
  DWORD v4; // eax
  __int64 v5; // r8

  if ( hObject != (HANDLE)-1LL )
  {
    if ( !SetThreadToken(0, hObject)
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_l(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, v3, LastError);
    }
    if ( hObject
      && !CloseHandle(hObject)
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v4 = GetLastError();
      WPP_SF_l(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, v5, v4);
    }
  }
}

```

## disassembly

```asm
0x180020740  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180020744  jz      locret_1800207E9
0x18002074a  mov     [rsp+arg_0], rbx
0x18002074f  push    rdi
0x180020750  sub     rsp, 20h
0x180020754  mov     rbx, rcx
0x180020757  mov     rdx, rcx; Token
0x18002075a  xor     ecx, ecx; Thread
0x18002075c  call    cs:__imp_SetThreadToken
0x180020762  lea     rdi, WPP_GLOBAL_Control
0x180020769  test    eax, eax
0x18002076b  jnz     short loc_18002079D
0x18002076d  mov     rax, cs:WPP_GLOBAL_Control
0x180020774  cmp     rax, rdi
0x180020777  jz      short loc_18002079D
0x180020779  test    byte ptr [rax+1Ch], 1
0x18002077d  jz      short loc_18002079D
0x18002077f  call    cs:__imp_GetLastError
0x180020785  mov     rcx, cs:WPP_GLOBAL_Control
0x18002078c  mov     edx, 1Eh
0x180020791  mov     r9d, eax
0x180020794  mov     rcx, [rcx+10h]
0x180020798  call    WPP_SF_l
0x18002079d  test    rbx, rbx
0x1800207a0  jz      short loc_1800207DF
0x1800207a2  mov     rcx, rbx; hObject
0x1800207a5  call    cs:__imp_CloseHandle
0x1800207ab  test    eax, eax
0x1800207ad  jnz     short loc_1800207DF
0x1800207af  mov     rax, cs:WPP_GLOBAL_Control
0x1800207b6  cmp     rax, rdi
0x1800207b9  jz      short loc_1800207DF
0x1800207bb  test    byte ptr [rax+1Ch], 1
0x1800207bf  jz      short loc_1800207DF
0x1800207c1  call    cs:__imp_GetLastError
0x1800207c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800207ce  mov     edx, 1Fh
0x1800207d3  mov     r9d, eax
0x1800207d6  mov     rcx, [rcx+10h]
0x1800207da  call    WPP_SF_l
0x1800207df  mov     rbx, [rsp+28h+arg_0]
0x1800207e4  add     rsp, 20h
0x1800207e8  pop     rdi
0x1800207e9  retn
```
