# I_CryptRecursiveCreateLowIntegrityDirectory

- ea: `0x180009030`
- end: `0x1800090a0`
- name: `I_CryptRecursiveCreateLowIntegrityDirectory`
- size: `112`
- prototype: `_BOOL8 __fastcall(LPCWSTR lpFileName, __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180004498`
- `0x180004c90`
- `0x180007af0`

## callees

- `0x180008330`
- `0x180009030`
- `0x1800090b0`
- `0x18000961c`
- `0x1800114c4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180009045`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180009045`

## pseudocode

```c
_BOOL8 __fastcall I_CryptRecursiveCreateLowIntegrityDirectory(LPCWSTR lpFileName, __int64 a2)
{
  DWORD FileAttributesW; // eax
  int v5; // [rsp+38h] [rbp+10h] BYREF
  int v6; // [rsp+3Ch] [rbp+14h]

  v6 = HIDWORD(a2);
  v5 = 0;
  FileAttributesW = GetFileAttributesW(lpFileName);
  return (FileAttributesW != -1 && (FileAttributesW & 0x10) != 0 || (unsigned int)I_RecursiveCreateDirectory(lpFileName))
      && ((unsigned int)I_CryptIsAppContainerToken(0)
       || (unsigned int)CheckLowIntegrityDir(lpFileName, &v5) && (v5 || (unsigned int)SetLowIntegrityFile(lpFileName)));
}

```

## disassembly

```asm
0x180009030  mov     [rsp+arg_8], rdx
0x180009035  push    rbx
0x180009036  sub     rsp, 20h
0x18000903a  mov     rbx, rcx
0x18000903d  mov     dword ptr [rsp+28h+arg_8], 0
0x180009045  call    cs:__imp_GetFileAttributesW
0x18000904b  cmp     eax, 0FFFFFFFFh
0x18000904e  jz      short loc_18000907E
0x180009050  test    al, 10h
0x180009052  jz      short loc_18000907E
0x180009054  xor     ecx, ecx
0x180009056  call    I_CryptIsAppContainerToken
0x18000905b  test    eax, eax
0x18000905d  jnz     short loc_180009077
0x18000905f  lea     rdx, [rsp+28h+arg_8]
0x180009064  mov     rcx, rbx; lpFileName
0x180009067  call    _CheckLowIntegrityDir
0x18000906c  test    eax, eax
0x18000906e  jz      short loc_18000908A
0x180009070  cmp     dword ptr [rsp+28h+arg_8], 0
0x180009075  jz      short loc_180009092
0x180009077  mov     eax, 1
0x18000907c  jmp     short loc_18000908C
0x18000907e  mov     rcx, rbx; lpFileName
0x180009081  call    I_RecursiveCreateDirectory
0x180009086  test    eax, eax
0x180009088  jnz     short loc_180009054
0x18000908a  xor     eax, eax
0x18000908c  add     rsp, 20h
0x180009090  pop     rbx
0x180009091  retn
0x180009092  mov     rcx, rbx; lpFileName
0x180009095  call    _SetLowIntegrityFile
0x18000909a  test    eax, eax
0x18000909c  jz      short loc_18000908A
0x18000909e  jmp     short loc_180009077
```
