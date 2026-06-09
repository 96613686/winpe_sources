# CfpIsDirectory

- ea: `0x1800048bc`
- end: `0x180004932`
- name: `CfpIsDirectory`
- size: `118`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000dfe0`
- `0x18000f100`

## callees

- `0x1800048bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004903`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004903`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800048ef`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x1800048ef`

## pseudocode

```c
signed int __fastcall CfpIsDirectory(unsigned __int64 a1, bool *a2)
{
  signed int result; // eax
  bool v4; // sf
  __int64 FileInformation; // [rsp+30h] [rbp+8h] BYREF

  FileInformation = 0;
  if ( a1 != -1 && (a1 & 1) != 0 )
    a1 = *(_QWORD *)(a1 & 0xFFFFFFFFFFFFFFFEuLL);
  if ( GetFileInformationByHandleEx((HANDLE)a1, FileAttributeTagInfo, &FileInformation, 8u) )
  {
    result = 0;
  }
  else
  {
    result = GetLastError();
    v4 = result < 0;
    if ( result <= 0 )
      goto LABEL_9;
    result = (unsigned __int16)result | 0x80070000;
  }
  v4 = result < 0;
LABEL_9:
  if ( !v4 )
    *a2 = (FileInformation & 0x10) != 0;
  return result;
}

```

## disassembly

```asm
0x1800048bc  push    rbx
0x1800048be  sub     rsp, 20h
0x1800048c2  mov     [rsp+28h+FileInformation], 0
0x1800048cb  mov     rbx, rdx
0x1800048ce  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800048d2  jz      short loc_1800048E0
0x1800048d4  test    cl, 1
0x1800048d7  jz      short loc_1800048E0
0x1800048d9  and     rcx, 0FFFFFFFFFFFFFFFEh
0x1800048dd  mov     rcx, [rcx]; hFile
0x1800048e0  mov     r9d, 8; dwBufferSize
0x1800048e6  lea     r8, [rsp+28h+FileInformation]; lpFileInformation
0x1800048eb  lea     edx, [r9+1]; FileInformationClass
0x1800048ef  call    cs:__imp_GetFileInformationByHandleEx
0x1800048f6  nop     dword ptr [rax+rax+00h]
0x1800048fb  test    eax, eax
0x1800048fd  jz      short loc_180004903
0x1800048ff  xor     eax, eax
0x180004901  jmp     short loc_18000491B
0x180004903  call    cs:__imp_GetLastError
0x18000490a  nop     dword ptr [rax+rax+00h]
0x18000490f  test    eax, eax
0x180004911  jle     short loc_18000491D
0x180004913  movzx   eax, ax
0x180004916  or      eax, 80070000h
0x18000491b  test    eax, eax
0x18000491d  js      short loc_18000492B
0x18000491f  mov     ecx, dword ptr [rsp+28h+FileInformation]
0x180004923  shr     ecx, 4
0x180004926  and     cl, 1
0x180004929  mov     [rbx], cl
0x18000492b  add     rsp, 20h
0x18000492f  pop     rbx
0x180004930  retn
```
