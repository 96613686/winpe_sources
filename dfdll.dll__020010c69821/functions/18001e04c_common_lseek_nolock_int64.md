# common_lseek_nolock___int64_

- ea: `0x18001e04c`
- end: `0x18001e0e5`
- name: `common_lseek_nolock___int64_`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001e0e8`

## callees

- `0x180019500`
- `0x180019570`
- `0x18001c94c`
- `0x18001e04c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001e09a`
- `KERNEL32!GetLastError` at `0x18001e09a`
- `KERNEL32!SetFilePointerEx` at `0x18001e090`
- `KERNEL32!SetFilePointerEx` at `0x18001e090`

## pseudocode

```c
LARGE_INTEGER __fastcall common_lseek_nolock___int64_(int a1, LARGE_INTEGER a2, DWORD a3)
{
  __int64 v3; // rbx
  void *osfhandle; // rax
  LARGE_INTEGER result; // rax
  DWORD LastError; // eax
  LARGE_INTEGER NewFilePointer; // [rsp+48h] [rbp+20h] BYREF

  v3 = a1;
  osfhandle = (void *)get_osfhandle(a1);
  if ( osfhandle == (void *)-1LL )
  {
    *errno() = 9;
    return (LARGE_INTEGER)-1LL;
  }
  if ( !SetFilePointerEx(osfhandle, a2, &NewFilePointer, a3) )
  {
    LastError = GetLastError();
    _acrt_errno_map_os_error(LastError);
    return (LARGE_INTEGER)-1LL;
  }
  result = NewFilePointer;
  if ( NewFilePointer.QuadPart == -1 )
    return (LARGE_INTEGER)-1LL;
  *(_BYTE *)(_pioinfo[v3 >> 6] + ((unsigned __int64)(v3 & 0x3F) << 6) + 56) &= ~2u;
  return result;
}

```

## disassembly

```asm
0x18001e04c  mov     [rsp+arg_0], rbx
0x18001e051  mov     [rsp+arg_8], rsi
0x18001e056  push    rdi
0x18001e057  sub     rsp, 20h
0x18001e05b  movsxd  rbx, ecx
0x18001e05e  mov     edi, r8d
0x18001e061  mov     ecx, ebx; FileHandle
0x18001e063  mov     rsi, rdx
0x18001e066  call    _get_osfhandle
0x18001e06b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001e06f  jnz     short loc_18001E082
0x18001e071  call    _errno
0x18001e076  mov     dword ptr [rax], 9
0x18001e07c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001e080  jmp     short loc_18001E0D5
0x18001e082  mov     r9d, edi; dwMoveMethod
0x18001e085  lea     r8, [rsp+28h+NewFilePointer]; lpNewFilePointer
0x18001e08a  mov     rdx, rsi; liDistanceToMove
0x18001e08d  mov     rcx, rax; hFile
0x18001e090  call    cs:__imp_SetFilePointerEx
0x18001e096  test    eax, eax
0x18001e098  jnz     short loc_18001E0A9
0x18001e09a  call    cs:__imp_GetLastError
0x18001e0a0  mov     ecx, eax
0x18001e0a2  call    __acrt_errno_map_os_error
0x18001e0a7  jmp     short loc_18001E07C
0x18001e0a9  mov     rax, qword ptr [rsp+28h+NewFilePointer]
0x18001e0ae  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001e0b2  jz      short loc_18001E07C
0x18001e0b4  mov     rdx, rbx
0x18001e0b7  lea     r8, __pioinfo
0x18001e0be  and     edx, 3Fh
0x18001e0c1  mov     rcx, rbx
0x18001e0c4  sar     rcx, 6
0x18001e0c8  shl     rdx, 6
0x18001e0cc  mov     rcx, [r8+rcx*8]
0x18001e0d0  and     byte ptr [rcx+rdx+38h], 0FDh
0x18001e0d5  mov     rbx, [rsp+28h+arg_0]
0x18001e0da  mov     rsi, [rsp+28h+arg_8]
0x18001e0df  add     rsp, 20h
0x18001e0e3  pop     rdi
0x18001e0e4  retn
```
