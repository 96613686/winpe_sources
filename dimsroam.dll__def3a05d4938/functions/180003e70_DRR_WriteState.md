# DRR_WriteState

- ea: `0x180003e70`
- end: `0x180003f06`
- name: `DRR_WriteState`
- size: `150`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180005c00`
- `0x180006230`

## callees

- `0x180003ad0`
- `0x180003e70`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180003eb0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180003eb0`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180003e89`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180003eee`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180003e89`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180003eee`

## pseudocode

```c
__int64 DRR_WriteState()
{
  unsigned int v0; // edi
  __int64 v1; // rbx

  DeleteFileW(lpFileName);
  v0 = drr_WriteStateFile((LPCWSTR)Src);
  if ( v0 )
  {
    v1 = 0;
    while ( 1 )
    {
      Sleep(*((_DWORD *)qword_18000FC50 + v1));
      v0 = drr_WriteStateFile((LPCWSTR)Src);
      if ( !v0 )
        break;
      v1 = (unsigned int)(v1 + 1);
      if ( (unsigned int)v1 >= 6 )
        return v0;
    }
  }
  if ( (unsigned int)drr_WriteStateFile(lpFileName) )
    DeleteFileW(lpFileName);
  return v0;
}

```

## disassembly

```asm
0x180003e70  mov     [rsp+arg_0], rbx
0x180003e75  mov     [rsp+arg_8], rsi
0x180003e7a  push    rdi
0x180003e7b  sub     rsp, 20h
0x180003e7f  mov     rsi, rcx
0x180003e82  mov     rcx, cs:lpFileName; lpFileName
0x180003e89  call    cs:__imp_DeleteFileW
0x180003e8f  mov     rcx, cs:Src; lpFileName
0x180003e96  mov     r8, rsi
0x180003e99  call    _drr_WriteStateFile
0x180003e9e  mov     edi, eax
0x180003ea0  test    eax, eax
0x180003ea2  jz      short loc_180003ED4
0x180003ea4  xor     ebx, ebx
0x180003ea6  lea     rax, qword_18000FC50
0x180003ead  mov     ecx, [rax+rbx*4]; dwMilliseconds
0x180003eb0  call    cs:__imp_Sleep
0x180003eb6  mov     rcx, cs:Src; lpFileName
0x180003ebd  mov     r8, rsi
0x180003ec0  call    _drr_WriteStateFile
0x180003ec5  mov     edi, eax
0x180003ec7  test    eax, eax
0x180003ec9  jz      short loc_180003ED4
0x180003ecb  inc     ebx
0x180003ecd  cmp     ebx, 6
0x180003ed0  jb      short loc_180003EA6
0x180003ed2  jmp     short loc_180003EF4
0x180003ed4  mov     rcx, cs:lpFileName; lpFileName
0x180003edb  mov     r8, rsi
0x180003ede  call    _drr_WriteStateFile
0x180003ee3  test    eax, eax
0x180003ee5  jz      short loc_180003EF4
0x180003ee7  mov     rcx, cs:lpFileName; lpFileName
0x180003eee  call    cs:__imp_DeleteFileW
0x180003ef4  mov     rbx, [rsp+28h+arg_0]
0x180003ef9  mov     eax, edi
0x180003efb  mov     rsi, [rsp+28h+arg_8]
0x180003f00  add     rsp, 20h
0x180003f04  pop     rdi
0x180003f05  retn
```
