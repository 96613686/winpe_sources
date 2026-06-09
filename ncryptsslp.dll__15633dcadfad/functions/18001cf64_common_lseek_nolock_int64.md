# common_lseek_nolock___int64_

- ea: `0x18001cf64`
- end: `0x18001cffe`
- name: `common_lseek_nolock___int64_`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001d004`

## callees

- `0x180015080`
- `0x18001bef4`
- `0x18001cf64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cfb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cfb8`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18001cfae`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x18001cfae`

## pseudocode

```c
_LARGE_INTEGER __fastcall common_lseek_nolock___int64_(int a1, LARGE_INTEGER a2, DWORD a3, __int64 a4)
{
  __int64 v4; // rdi
  void *osfhandle; // rax
  _LARGE_INTEGER result; // rax
  DWORD LastError; // eax
  __int64 v11; // r8
  _LARGE_INTEGER NewFilePointer; // [rsp+20h] [rbp-38h] BYREF

  v4 = a1;
  osfhandle = (void *)get_osfhandle(a1);
  if ( osfhandle == (void *)-1LL )
  {
    *(_BYTE *)(a4 + 48) = 1;
    *(_DWORD *)(a4 + 44) = 9;
    return (_LARGE_INTEGER)-1LL;
  }
  NewFilePointer.QuadPart = 0;
  if ( !SetFilePointerEx(osfhandle, a2, &NewFilePointer, a3) )
  {
    LastError = GetLastError();
    _acrt_errno_map_os_error_ptd(LastError, a4, v11);
    return (_LARGE_INTEGER)-1LL;
  }
  result = NewFilePointer;
  if ( NewFilePointer.QuadPart == -1 )
    return (_LARGE_INTEGER)-1LL;
  *(_BYTE *)(_pioinfo[v4 >> 6] + 72 * (v4 & 0x3F) + 56) &= ~2u;
  return result;
}

```

## disassembly

```asm
0x18001cf64  push    rbx
0x18001cf66  push    rbp
0x18001cf67  push    rsi
0x18001cf68  push    rdi
0x18001cf69  sub     rsp, 38h
0x18001cf6d  movsxd  rdi, ecx
0x18001cf70  mov     rbx, r9
0x18001cf73  mov     ecx, edi; FileHandle
0x18001cf75  mov     esi, r8d
0x18001cf78  mov     rbp, rdx
0x18001cf7b  call    _get_osfhandle
0x18001cf80  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001cf84  jnz     short loc_18001CF97
0x18001cf86  mov     byte ptr [rbx+30h], 1
0x18001cf8a  mov     dword ptr [rbx+2Ch], 9
0x18001cf91  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001cf95  jmp     short loc_18001CFF5
0x18001cf97  mov     r9d, esi; dwMoveMethod
0x18001cf9a  mov     qword ptr [rsp+58h+NewFilePointer], 0
0x18001cfa3  lea     r8, [rsp+58h+NewFilePointer]; lpNewFilePointer
0x18001cfa8  mov     rdx, rbp; liDistanceToMove
0x18001cfab  mov     rcx, rax; hFile
0x18001cfae  call    cs:__imp_SetFilePointerEx
0x18001cfb4  test    eax, eax
0x18001cfb6  jnz     short loc_18001CFCA
0x18001cfb8  call    cs:__imp_GetLastError
0x18001cfbe  mov     ecx, eax
0x18001cfc0  mov     rdx, rbx
0x18001cfc3  call    __acrt_errno_map_os_error_ptd
0x18001cfc8  jmp     short loc_18001CF91
0x18001cfca  mov     rax, qword ptr [rsp+58h+NewFilePointer]
0x18001cfcf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001cfd3  jz      short loc_18001CF91
0x18001cfd5  mov     ecx, edi
0x18001cfd7  lea     r9, __pioinfo
0x18001cfde  and     ecx, 3Fh
0x18001cfe1  mov     r8, rdi
0x18001cfe4  sar     r8, 6
0x18001cfe8  lea     rdx, [rcx+rcx*8]
0x18001cfec  mov     rcx, [r9+r8*8]
0x18001cff0  and     byte ptr [rcx+rdx*8+38h], 0FDh
0x18001cff5  add     rsp, 38h
0x18001cff9  pop     rdi
0x18001cffa  pop     rsi
0x18001cffb  pop     rbp
0x18001cffc  pop     rbx
0x18001cffd  retn
```
