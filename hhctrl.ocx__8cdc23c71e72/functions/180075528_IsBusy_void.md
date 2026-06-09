# IsBusy(void)

- ea: `0x180075528`
- end: `0x1800755a5`
- name: `?IsBusy@@YAHXZ`
- size: `125`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800216d0`
- `0x1800756e0`

## callees

- `0x180075528`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180075592`
- `KERNEL32!CloseHandle` at `0x180075592`
- `KERNEL32!CreateFileMappingA` at `0x180075573`
- `KERNEL32!CreateFileMappingA` at `0x180075573`
- `KERNEL32!GetLastError` at `0x180075581`
- `KERNEL32!GetLastError` at `0x180075581`
- `KERNEL32!SetLastError` at `0x180075536`
- `KERNEL32!SetLastError` at `0x180075536`

## pseudocode

```c
__int64 IsBusy(void)
{
  unsigned int v0; // ebx
  HANDLE v1; // rdi
  struct _SECURITY_ATTRIBUTES FileMappingAttributes; // [rsp+30h] [rbp-28h] BYREF

  v0 = 0;
  SetLastError(0);
  *(_QWORD *)&FileMappingAttributes.nLength = 24;
  *(_QWORD *)&FileMappingAttributes.bInheritHandle = 0;
  FileMappingAttributes.lpSecurityDescriptor = 0;
  v1 = CreateFileMappingA(
         (HANDLE)0xFFFFFFFFFFFFFFFFLL,
         &FileMappingAttributes,
         2u,
         0,
         0x20u,
         "HTMLHelpKeywordMergingBusy");
  if ( v1 )
  {
    LOBYTE(v0) = GetLastError() == 183;
    CloseHandle(v1);
  }
  return v0;
}

```

## disassembly

```asm
0x180075528  mov     [rsp+arg_0], rbx
0x18007552d  push    rdi
0x18007552e  sub     rsp, 50h
0x180075532  xor     ecx, ecx; dwErrCode
0x180075534  xor     ebx, ebx
0x180075536  call    cs:__imp_SetLastError
0x18007553c  lea     rax, aHtmlhelpkeywor; "HTMLHelpKeywordMergingBusy"
0x180075543  mov     qword ptr [rsp+58h+FileMappingAttributes.nLength], 18h
0x18007554c  mov     [rsp+58h+lpName], rax; lpName
0x180075551  lea     r8d, [rbx+2]; flProtect
0x180075555  xor     r9d, r9d; dwMaximumSizeHigh
0x180075558  mov     [rsp+58h+dwMaximumSizeLow], 20h ; ' '; dwMaximumSizeLow
0x180075560  lea     rdx, [rsp+58h+FileMappingAttributes]; lpFileMappingAttributes
0x180075565  mov     qword ptr [rsp+58h+FileMappingAttributes.bInheritHandle], rbx
0x18007556a  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x18007556e  mov     [rsp+58h+FileMappingAttributes.lpSecurityDescriptor], rbx
0x180075573  call    cs:__imp_CreateFileMappingA
0x180075579  mov     rdi, rax
0x18007557c  test    rax, rax
0x18007557f  jz      short loc_180075598
0x180075581  call    cs:__imp_GetLastError
0x180075587  cmp     eax, 0B7h
0x18007558c  mov     rcx, rdi; hObject
0x18007558f  setz    bl
0x180075592  call    cs:__imp_CloseHandle
0x180075598  mov     eax, ebx
0x18007559a  mov     rbx, [rsp+58h+arg_0]
0x18007559f  add     rsp, 50h
0x1800755a3  pop     rdi
0x1800755a4  retn
```
