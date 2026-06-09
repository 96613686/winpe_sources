# FileStream::Write(void const *,ulong,ulong *)

- ea: `0x180013400`
- end: `0x180013456`
- name: `?Write@FileStream@@UEAAJPEBXKPEAK@Z`
- size: `86`
- prototype: `__int64 __fastcall(FileStream *this, const void *, DWORD, unsigned int *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, installer_update`

## callees

- `0x180004a64`
- `0x180013400`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180013423`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180013423`

## pseudocode

```c
__int64 __fastcall FileStream::Write(FileStream *this, const void *a2, DWORD a3, unsigned int *a4)
{
  void *v4; // rcx
  BOOL v6; // eax
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp+8h] BYREF

  v4 = (void *)*((_QWORD *)this + 1);
  NumberOfBytesWritten = 0;
  v6 = WriteFile(v4, a2, a3, &NumberOfBytesWritten, 0);
  if ( a4 )
    *a4 = NumberOfBytesWritten;
  if ( v6 )
    return 0;
  else
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x48,
             (int)"onecore\\base\\ntsetup\\provpackageapi\\inc\\FileStream.h",
             v7);
}

```

## disassembly

```asm
0x180013400  push    rbx
0x180013402  sub     rsp, 30h
0x180013406  mov     rcx, [rcx+8]; hFile
0x18001340a  mov     rbx, r9
0x18001340d  lea     r9, [rsp+38h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180013412  mov     [rsp+38h+NumberOfBytesWritten], 0
0x18001341a  mov     [rsp+38h+lpOverlapped], 0; lpOverlapped
0x180013423  call    cs:__imp_WriteFile
0x180013429  test    rbx, rbx
0x18001342c  jz      short loc_180013434
0x18001342e  mov     ecx, [rsp+38h+NumberOfBytesWritten]
0x180013432  mov     [rbx], ecx
0x180013434  test    eax, eax
0x180013436  jnz     short loc_18001344E
0x180013438  mov     rcx, [rsp+38h]; this
0x18001343d  lea     r8, aOnecoreBaseNts_6; "onecore\\base\\ntsetup\\provpackageapi"...
0x180013444  lea     edx, [rax+48h]; void *
0x180013447  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001344c  jmp     short loc_180013450
0x18001344e  xor     eax, eax
0x180013450  add     rsp, 30h
0x180013454  pop     rbx
0x180013455  retn
```
