# CSchedule::Delete(ushort const *)

- ea: `0x18000f700`
- end: `0x18000f769`
- name: `?Delete@CSchedule@@UEAAJPEBG@Z`
- size: `105`
- prototype: `__int64 __fastcall(CSchedule *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180006120`
- `0x180009f38`
- `0x18000f700`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f73a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f73a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000f730`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000f730`

## pseudocode

```c
__int64 __fastcall CSchedule::Delete(CSchedule *this, const unsigned __int16 *a2)
{
  signed int v2; // ebx
  signed int LastError; // eax
  LPCWSTR lpFileName; // [rsp+38h] [rbp+10h] BYREF

  lpFileName = 0;
  if ( a2 )
  {
    v2 = CSchedule::CheckJobName(this, a2, (unsigned __int16 **)&lpFileName);
    if ( v2 >= 0 && !DeleteFileW(lpFileName) )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( lpFileName )
      operator delete((void *)lpFileName);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x18000f700  push    rbx
0x18000f702  sub     rsp, 20h
0x18000f706  mov     [rsp+28h+lpFileName], 0
0x18000f70f  test    rdx, rdx
0x18000f712  jnz     short loc_18000F71B
0x18000f714  mov     ebx, 80070057h
0x18000f719  jmp     short loc_18000F761
0x18000f71b  lea     r8, [rsp+28h+lpFileName]; unsigned __int16 **
0x18000f720  call    ?CheckJobName@CSchedule@@AEAAJPEBGPEAPEAG@Z; CSchedule::CheckJobName(ushort const *,ushort * *)
0x18000f725  mov     ebx, eax
0x18000f727  test    eax, eax
0x18000f729  js      short loc_18000F74F
0x18000f72b  mov     rcx, [rsp+28h+lpFileName]; lpFileName
0x18000f730  call    cs:__imp_DeleteFileW
0x18000f736  test    eax, eax
0x18000f738  jnz     short loc_18000F74F
0x18000f73a  call    cs:__imp_GetLastError
0x18000f740  mov     ebx, eax
0x18000f742  test    eax, eax
0x18000f744  jle     short loc_18000F74F
0x18000f746  movzx   ebx, ax
0x18000f749  or      ebx, 80070000h
0x18000f74f  cmp     [rsp+28h+lpFileName], 0
0x18000f755  jz      short loc_18000F761
0x18000f757  mov     rcx, [rsp+28h+lpFileName]; Block
0x18000f75c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f761  mov     eax, ebx
0x18000f763  add     rsp, 20h
0x18000f767  pop     rbx
0x18000f768  retn
```
