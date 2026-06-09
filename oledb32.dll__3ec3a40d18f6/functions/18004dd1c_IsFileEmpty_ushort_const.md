# IsFileEmpty(ushort const *)

- ea: `0x18004dd1c`
- end: `0x18004ddbf`
- name: `?IsFileEmpty@@YAHPEBG@Z`
- size: `163`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18004de10`

## callees

- `0x18002ec0c`
- `0x18004dd1c`

## import_xrefs

- `KERNEL32!GetFileSize` at `0x18004dd86`
- `KERNEL32!GetFileSize` at `0x18004dd86`
- `KERNEL32!CreateFileW` at `0x18004dd52`
- `KERNEL32!CreateFileW` at `0x18004dd52`
- `KERNEL32!GetLastError` at `0x18004dd66`
- `KERNEL32!GetLastError` at `0x18004dd66`
- `KERNEL32!CloseHandle` at `0x18004dda5`
- `KERNEL32!CloseHandle` at `0x18004dda5`

## pseudocode

```c
_BOOL8 __fastcall IsFileEmpty(const unsigned __int16 *a1)
{
  HANDLE FileW; // rax
  void *v2; // rbx
  _BOOL8 result; // rax
  ulong pExceptionObject; // [rsp+40h] [rbp-18h] BYREF
  BOOL v5; // [rsp+68h] [rbp+10h]
  HANDLE v6; // [rsp+70h] [rbp+18h]

  FileW = CreateFileW(a1, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  try
  {
    v2 = FileW;
    v6 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      pExceptionObject = GetLastError();
      throw &pExceptionObject;
    }
    v5 = GetFileSize(FileW, 0) == 0;
  }
  catch ( ... )
  {
    if ( (bidGblFlags & 2) != 0 && off_1800C8830[0] )
      bidTraceA(off_1800C83D0[0], 321536, off_1800C8830[0], 0);
    v2 = v6;
    if ( v6 != (HANDLE)-1LL )
      goto LABEL_6;
LABEL_7:
    result = v5;
  }
LABEL_6:
  CloseHandle(v2);
  goto LABEL_7;
}

```

## disassembly

```asm
0x18004dd1c  mov     rax, rsp
0x18004dd1f  mov     [rax+8], rbx
0x18004dd23  mov     [rax+20h], rsi
0x18004dd27  push    rdi
0x18004dd28  sub     rsp, 50h
0x18004dd2c  xor     edi, edi
0x18004dd2e  mov     [rsp+58h+arg_8], edi
0x18004dd32  mov     [rax-28h], rdi
0x18004dd36  mov     dword ptr [rax-30h], 80h
0x18004dd3d  mov     dword ptr [rax-38h], 3
0x18004dd44  xor     r9d, r9d; lpSecurityAttributes
0x18004dd47  lea     esi, [rdi+1]
0x18004dd4a  mov     r8d, esi; dwShareMode
0x18004dd4d  mov     edx, 80000000h; dwDesiredAccess
0x18004dd52  call    cs:__imp_CreateFileW
0x18004dd58  mov     rbx, rax
0x18004dd5b  mov     [rsp+58h+arg_10], rax
0x18004dd60  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004dd64  jnz     short loc_18004DD81
0x18004dd66  call    cs:__imp_GetLastError
0x18004dd6c  mov     [rsp+58h+pExceptionObject], eax
0x18004dd70  lea     rdx, _TI1K; pThrowInfo
0x18004dd77  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18004dd7c  call    _CxxThrowException_0
0x18004dd81  xor     edx, edx; lpFileSizeHigh
0x18004dd83  mov     rcx, rax; hFile
0x18004dd86  call    cs:__imp_GetFileSize
0x18004dd8c  test    eax, eax
0x18004dd8e  cmovz   edi, esi
0x18004dd91  mov     [rsp+58h+arg_8], edi
0x18004dd95  jmp     short loc_18004DDA2
0x18004dd97  mov     rbx, [rsp+58h+arg_10]
0x18004dd9c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18004dda0  jz      short loc_18004DDAB
0x18004dda2  mov     rcx, rbx; hObject
0x18004dda5  call    cs:__imp_CloseHandle
0x18004ddab  mov     eax, [rsp+58h+arg_8]
0x18004ddaf  mov     rbx, [rsp+58h+arg_0]
0x18004ddb4  mov     rsi, [rsp+58h+arg_18]
0x18004ddb9  add     rsp, 50h
0x18004ddbd  pop     rdi
0x18004ddbe  retn
```
