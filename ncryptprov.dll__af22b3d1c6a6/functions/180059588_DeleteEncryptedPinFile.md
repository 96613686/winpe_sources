# DeleteEncryptedPinFile

- ea: `0x180059588`
- end: `0x18005962a`
- name: `DeleteEncryptedPinFile`
- size: `162`
- prototype: `__int64 __fastcall(__int64, __int64, _WORD *)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003770`
- `0x18002a0c0`
- `0x180059f7c`

## callees

- `0x18000af80`
- `0x18000d3d0`
- `0x180059588`
- `0x180059bd4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800595d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800595d9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800595c9`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800595c9`

## string_xrefs

- `0x1800595ad`: `onecore\ds\security\cryptoapi\ncrypt\storage\encryptedpinfile.c`
- `0x1800595eb`: `onecore\ds\security\cryptoapi\ncrypt\storage\encryptedpinfile.c`

## pseudocode

```c
__int64 __fastcall DeleteEncryptedPinFile(__int64 a1, __int64 a2, _WORD *a3)
{
  int PinFileFullPath; // eax
  DWORD LastError; // ebx
  LPCWSTR lpFileName; // [rsp+48h] [rbp+20h] BYREF

  lpFileName = 0;
  PinFileFullPath = GetPinFileFullPath(a1, a2, a3, &lpFileName);
  LastError = PinFileFullPath;
  if ( PinFileFullPath >= 0 )
  {
    if ( !DeleteFileW(lpFileName) )
    {
      LastError = GetLastError();
      DebugTraceError(
        LastError,
        "dwReturn",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\encryptedpinfile.c",
        340);
      if ( (int)LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
  }
  else
  {
    DebugTraceError(
      (unsigned int)PinFileFullPath,
      "hr",
      "onecore\\ds\\security\\cryptoapi\\ncrypt\\storage\\encryptedpinfile.c",
      333);
  }
  if ( lpFileName )
    MSCryptFree(lpFileName);
  return LastError;
}

```

## disassembly

```asm
0x180059588  push    rbx
0x18005958a  sub     rsp, 20h
0x18005958e  lea     r9, [rsp+28h+lpFileName]
0x180059593  mov     [rsp+28h+lpFileName], 0
0x18005959c  call    GetPinFileFullPath
0x1800595a1  mov     ebx, eax
0x1800595a3  test    eax, eax
0x1800595a5  jns     short loc_1800595C4
0x1800595a7  mov     r9d, 14Dh
0x1800595ad  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800595b4  lea     rdx, aHr; "hr"
0x1800595bb  mov     ecx, eax
0x1800595bd  call    DebugTraceError
0x1800595c2  jmp     short loc_18005960F
0x1800595c4  mov     rcx, [rsp+28h+lpFileName]; lpFileName
0x1800595c9  call    cs:__imp_DeleteFileW
0x1800595d0  nop     dword ptr [rax+rax+00h]
0x1800595d5  test    eax, eax
0x1800595d7  jnz     short loc_18005960F
0x1800595d9  call    cs:__imp_GetLastError
0x1800595e0  nop     dword ptr [rax+rax+00h]
0x1800595e5  mov     r9d, 154h
0x1800595eb  lea     r8, aOnecoreDsSecur_22; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800595f2  mov     ecx, eax
0x1800595f4  lea     rdx, aDwreturn; "dwReturn"
0x1800595fb  mov     ebx, eax
0x1800595fd  call    DebugTraceError
0x180059602  test    ebx, ebx
0x180059604  jle     short loc_18005960F
0x180059606  movzx   ebx, bx
0x180059609  or      ebx, 80070000h
0x18005960f  cmp     [rsp+28h+lpFileName], 0
0x180059615  jz      short loc_180059621
0x180059617  mov     rcx, [rsp+28h+lpFileName]
0x18005961c  call    MSCryptFree
0x180059621  mov     eax, ebx
0x180059623  add     rsp, 20h
0x180059627  pop     rbx
0x180059628  retn
```
