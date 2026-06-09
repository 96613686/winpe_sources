# Win32FileOutputProvider::Seek(ulong,__int64,unsigned __int64 *)

- ea: `0x180015af0`
- end: `0x180015b74`
- name: `?Seek@Win32FileOutputProvider@@UEAAJK_JPEA_K@Z`
- size: `132`
- prototype: `int(Win32FileOutputProvider *__hidden this, unsigned int, __int64, unsigned __int64 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180015af0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015b24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015b2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015b38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015b24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015b2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015b38`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180015b17`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180015b17`

## pseudocode

```c
int __fastcall Win32FileOutputProvider::Seek(Win32FileOutputProvider *this, DWORD a2, __int64 a3, unsigned __int64 *a4)
{
  void *v4; // rcx
  DWORD v6; // eax
  __int64 v7; // rdi
  int result; // eax
  LONG DistanceToMoveHigh; // [rsp+30h] [rbp+8h] BYREF

  v4 = (void *)*((_QWORD *)this + 1);
  DistanceToMoveHigh = HIDWORD(a3);
  v6 = SetFilePointer(v4, a3, &DistanceToMoveHigh, a2);
  v7 = v6;
  if ( v6 == -1 && GetLastError() )
  {
    if ( GetLastError() )
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
    else
    {
      return -2147467259;
    }
  }
  else
  {
    if ( a4 )
      *a4 = v7 | ((__int64)DistanceToMoveHigh << 32);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180015af0  mov     [rsp+arg_8], rbx
0x180015af5  push    rdi
0x180015af6  sub     rsp, 20h
0x180015afa  mov     rcx, [rcx+8]; hFile
0x180015afe  mov     rax, r8
0x180015b01  mov     rbx, r9
0x180015b04  sar     rax, 20h
0x180015b08  mov     r9d, edx; dwMoveMethod
0x180015b0b  mov     [rsp+28h+DistanceToMoveHigh], eax
0x180015b0f  mov     edx, r8d; lDistanceToMove
0x180015b12  lea     r8, [rsp+28h+DistanceToMoveHigh]; lpDistanceToMoveHigh
0x180015b17  call    cs:__imp_SetFilePointer
0x180015b1d  mov     edi, eax
0x180015b1f  cmp     eax, 0FFFFFFFFh
0x180015b22  jnz     short loc_180015B53
0x180015b24  call    cs:__imp_GetLastError
0x180015b2a  test    eax, eax
0x180015b2c  jz      short loc_180015B53
0x180015b2e  call    cs:__imp_GetLastError
0x180015b34  test    eax, eax
0x180015b36  jz      short loc_180015B4C
0x180015b38  call    cs:__imp_GetLastError
0x180015b3e  test    eax, eax
0x180015b40  jle     short loc_180015B69
0x180015b42  movzx   eax, ax
0x180015b45  or      eax, 80070000h
0x180015b4a  jmp     short loc_180015B69
0x180015b4c  mov     eax, 80004005h
0x180015b51  jmp     short loc_180015B69
0x180015b53  test    rbx, rbx
0x180015b56  jz      short loc_180015B67
0x180015b58  movsxd  rcx, [rsp+28h+DistanceToMoveHigh]
0x180015b5d  shl     rcx, 20h
0x180015b61  or      rcx, rdi
0x180015b64  mov     [rbx], rcx
0x180015b67  xor     eax, eax
0x180015b69  mov     rbx, [rsp+28h+arg_8]
0x180015b6e  add     rsp, 20h
0x180015b72  pop     rdi
0x180015b73  retn
```
