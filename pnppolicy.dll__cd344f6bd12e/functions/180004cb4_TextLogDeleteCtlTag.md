# TextLogDeleteCtlTag

- ea: `0x180004cb4`
- end: `0x180004d2d`
- name: `TextLogDeleteCtlTag`
- size: `121`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x1800054d4`
- `0x1800063bc`
- `0x180006590`

## callees

- `0x180004cb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004d0e`
- `KERNEL32!SetFilePointer` at `0x180004d03`
- `KERNEL32!SetFilePointer` at `0x180004d03`

## pseudocode

```c
__int64 __fastcall TextLogDeleteCtlTag(__int64 a1, int a2)
{
  __int64 v2; // r9
  unsigned int v3; // r8d
  __int64 i; // rdx
  unsigned int v5; // ebx

  v2 = *(_QWORD *)(a1 + 24) - 20LL * (unsigned int)(a2 + 1);
  v3 = *(_QWORD *)(a1 + 24) - (v2 + 20);
  for ( i = 0; (unsigned int)i < v3; i = (unsigned int)(i + 1) )
    *(_BYTE *)(i + v2) = *(_BYTE *)(i + v2 + 20);
  v5 = 0;
  *(_QWORD *)(a1 + 24) -= 20LL;
  if ( SetFilePointer(*(HANDLE *)a1, *(_DWORD *)(a1 + 24) - *(_DWORD *)(a1 + 16), 0, 0) == -1 )
    return GetLastError();
  return v5;
}

```

## disassembly

```asm
0x180004cb4  push    rbx
0x180004cb6  sub     rsp, 30h
0x180004cba  mov     r8, [rcx+18h]
0x180004cbe  lea     eax, [rdx+1]
0x180004cc1  lea     rax, [rax+rax*4]
0x180004cc5  shl     rax, 2
0x180004cc9  mov     r9, r8
0x180004ccc  sub     r9, rax
0x180004ccf  lea     r11, [r9+14h]
0x180004cd3  sub     r8d, r11d
0x180004cd6  xor     edx, edx
0x180004cd8  mov     [rsp+38h+var_18], edx
0x180004cdc  cmp     edx, r8d
0x180004cdf  jnb     short loc_180004CED
0x180004ce1  mov     al, [rdx+r11]
0x180004ce5  mov     [rdx+r9], al
0x180004ce9  inc     edx
0x180004ceb  jmp     short loc_180004CD8
0x180004ced  xor     ebx, ebx
0x180004cef  add     qword ptr [rcx+18h], 0FFFFFFFFFFFFFFECh
0x180004cf4  mov     edx, [rcx+18h]
0x180004cf7  sub     edx, [rcx+10h]; lDistanceToMove
0x180004cfa  xor     r9d, r9d; dwMoveMethod
0x180004cfd  xor     r8d, r8d; lpDistanceToMoveHigh
0x180004d00  mov     rcx, [rcx]; hFile
0x180004d03  call    cs:__imp_SetFilePointer
0x180004d09  cmp     eax, 0FFFFFFFFh
0x180004d0c  jnz     short loc_180004D16
0x180004d0e  call    cs:__imp_GetLastError
0x180004d14  mov     ebx, eax
0x180004d16  mov     [rsp+38h+var_14], ebx
0x180004d1a  jmp     short loc_180004D25
0x180004d1c  mov     ebx, 0Dh
0x180004d21  mov     [rsp+38h+var_14], ebx
0x180004d25  mov     eax, ebx
0x180004d27  add     rsp, 30h
0x180004d2b  pop     rbx
0x180004d2c  retn
```
