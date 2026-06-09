# common_lseek_nolock___int64_

- ea: `0x180103514`
- end: `0x1801035ad`
- name: `common_lseek_nolock___int64_`
- size: `153`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180103424`
- `0x1801035b8`

## callees

- `0x1800f9a0c`
- `0x1800f9a7c`
- `0x1801031c0`
- `0x180103514`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180103562`
- `KERNEL32!GetLastError` at `0x180103562`
- `KERNEL32!SetFilePointerEx` at `0x180103558`
- `KERNEL32!SetFilePointerEx` at `0x180103558`

## pseudocode

```c
union _LARGE_INTEGER __fastcall common_lseek_nolock___int64_(int a1, LARGE_INTEGER a2, DWORD a3)
{
  __int64 v3; // rbx
  void *osfhandle; // rax
  union _LARGE_INTEGER result; // rax
  DWORD LastError; // eax
  union _LARGE_INTEGER NewFilePointer; // [rsp+48h] [rbp+20h] BYREF

  v3 = a1;
  osfhandle = (void *)get_osfhandle(a1);
  if ( osfhandle == (void *)-1LL )
  {
    *errno() = 9;
    return (union _LARGE_INTEGER)-1LL;
  }
  if ( !SetFilePointerEx(osfhandle, a2, &NewFilePointer, a3) )
  {
    LastError = GetLastError();
    _acrt_errno_map_os_error(LastError);
    return (union _LARGE_INTEGER)-1LL;
  }
  result = NewFilePointer;
  if ( NewFilePointer.QuadPart == -1 )
    return (union _LARGE_INTEGER)-1LL;
  *(_BYTE *)(_pioinfo[v3 >> 6] + ((unsigned __int64)(v3 & 0x3F) << 6) + 56) &= ~2u;
  return result;
}

```

## disassembly

```asm
0x180103514  mov     [rsp+arg_0], rbx
0x180103519  mov     [rsp+arg_8], rsi
0x18010351e  push    rdi
0x18010351f  sub     rsp, 20h
0x180103523  movsxd  rbx, ecx
0x180103526  mov     edi, r8d
0x180103529  mov     ecx, ebx; FileHandle
0x18010352b  mov     rsi, rdx
0x18010352e  call    _get_osfhandle
0x180103533  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180103537  jnz     short loc_18010354A
0x180103539  call    _errno
0x18010353e  mov     dword ptr [rax], 9
0x180103544  or      rax, 0FFFFFFFFFFFFFFFFh
0x180103548  jmp     short loc_18010359D
0x18010354a  mov     r9d, edi; dwMoveMethod
0x18010354d  lea     r8, [rsp+28h+NewFilePointer]; lpNewFilePointer
0x180103552  mov     rdx, rsi; liDistanceToMove
0x180103555  mov     rcx, rax; hFile
0x180103558  call    cs:__imp_SetFilePointerEx
0x18010355e  test    eax, eax
0x180103560  jnz     short loc_180103571
0x180103562  call    cs:__imp_GetLastError
0x180103568  mov     ecx, eax
0x18010356a  call    __acrt_errno_map_os_error
0x18010356f  jmp     short loc_180103544
0x180103571  mov     rax, qword ptr [rsp+28h+NewFilePointer]
0x180103576  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18010357a  jz      short loc_180103544
0x18010357c  mov     rdx, rbx
0x18010357f  lea     r8, __pioinfo
0x180103586  and     edx, 3Fh
0x180103589  mov     rcx, rbx
0x18010358c  sar     rcx, 6
0x180103590  shl     rdx, 6
0x180103594  mov     rcx, [r8+rcx*8]
0x180103598  and     byte ptr [rcx+rdx+38h], 0FDh
0x18010359d  mov     rbx, [rsp+28h+arg_0]
0x1801035a2  mov     rsi, [rsp+28h+arg_8]
0x1801035a7  add     rsp, 20h
0x1801035ab  pop     rdi
0x1801035ac  retn
```
