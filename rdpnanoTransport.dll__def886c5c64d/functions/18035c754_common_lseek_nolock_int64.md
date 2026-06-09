# common_lseek_nolock___int64_

- ea: `0x18035c754`
- end: `0x18035c803`
- name: `common_lseek_nolock___int64_`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18035c804`

## callees

- `0x18033f210`
- `0x18035c754`
- `0x180364348`

## import_xrefs

- `KERNEL32!SetFilePointerEx` at `0x18035c7a6`
- `KERNEL32!SetFilePointerEx` at `0x18035c7a6`
- `KERNEL32!GetLastError` at `0x18035c7b0`
- `KERNEL32!GetLastError` at `0x18035c7b0`

## pseudocode

```c
union _LARGE_INTEGER __fastcall common_lseek_nolock___int64_(int a1, LARGE_INTEGER a2, DWORD a3, __int64 a4)
{
  __int64 v4; // rdi
  void *osfhandle; // rax
  union _LARGE_INTEGER result; // rax
  DWORD LastError; // eax
  __int64 v11; // r8
  union _LARGE_INTEGER NewFilePointer; // [rsp+20h] [rbp-18h] BYREF

  v4 = a1;
  osfhandle = (void *)get_osfhandle(a1);
  if ( osfhandle == (void *)-1LL )
  {
    *(_BYTE *)(a4 + 48) = 1;
    *(_DWORD *)(a4 + 44) = 9;
    return (union _LARGE_INTEGER)-1LL;
  }
  NewFilePointer.QuadPart = 0;
  if ( !SetFilePointerEx(osfhandle, a2, &NewFilePointer, a3) )
  {
    LastError = GetLastError();
    _acrt_errno_map_os_error_ptd(LastError, a4, v11);
    return (union _LARGE_INTEGER)-1LL;
  }
  result = NewFilePointer;
  if ( NewFilePointer.QuadPart == -1 )
    return (union _LARGE_INTEGER)-1LL;
  *(_BYTE *)(_pioinfo[v4 >> 6] + 72 * (v4 & 0x3F) + 56) &= ~2u;
  return result;
}

```

## disassembly

```asm
0x18035c754  mov     [rsp+arg_0], rbx
0x18035c759  mov     [rsp+arg_8], rbp
0x18035c75e  mov     [rsp+arg_10], rsi
0x18035c763  push    rdi
0x18035c764  sub     rsp, 30h
0x18035c768  movsxd  rdi, ecx
0x18035c76b  mov     rbx, r9
0x18035c76e  mov     ecx, edi; FileHandle
0x18035c770  mov     esi, r8d
0x18035c773  mov     rbp, rdx
0x18035c776  call    _get_osfhandle
0x18035c77b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18035c77f  jnz     short loc_18035C792
0x18035c781  mov     byte ptr [rbx+30h], 1
0x18035c785  mov     dword ptr [rbx+2Ch], 9
0x18035c78c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18035c790  jmp     short loc_18035C7EE
0x18035c792  and     qword ptr [rsp+38h+NewFilePointer], 0
0x18035c798  lea     r8, [rsp+38h+NewFilePointer]; lpNewFilePointer
0x18035c79d  mov     r9d, esi; dwMoveMethod
0x18035c7a0  mov     rdx, rbp; liDistanceToMove
0x18035c7a3  mov     rcx, rax; hFile
0x18035c7a6  call    cs:__imp_SetFilePointerEx
0x18035c7ac  test    eax, eax
0x18035c7ae  jnz     short loc_18035C7C2
0x18035c7b0  call    cs:__imp_GetLastError
0x18035c7b6  mov     ecx, eax
0x18035c7b8  mov     rdx, rbx
0x18035c7bb  call    __acrt_errno_map_os_error_ptd
0x18035c7c0  jmp     short loc_18035C78C
0x18035c7c2  mov     rax, qword ptr [rsp+38h+NewFilePointer]
0x18035c7c7  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18035c7cb  jz      short loc_18035C78C
0x18035c7cd  mov     rdx, rdi
0x18035c7d0  lea     r8, __pioinfo
0x18035c7d7  and     edx, 3Fh
0x18035c7da  mov     rcx, rdi
0x18035c7dd  sar     rcx, 6
0x18035c7e1  lea     rdx, [rdx+rdx*8]
0x18035c7e5  mov     rcx, [r8+rcx*8]
0x18035c7e9  and     byte ptr [rcx+rdx*8+38h], 0FDh
0x18035c7ee  mov     rbx, [rsp+38h+arg_0]
0x18035c7f3  mov     rbp, [rsp+38h+arg_8]
0x18035c7f8  mov     rsi, [rsp+38h+arg_10]
0x18035c7fd  add     rsp, 30h
0x18035c801  pop     rdi
0x18035c802  retn
```
