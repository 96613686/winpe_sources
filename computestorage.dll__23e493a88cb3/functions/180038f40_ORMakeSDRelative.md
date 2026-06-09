# ORMakeSDRelative

- ea: `0x180038f40`
- end: `0x180039020`
- name: `ORMakeSDRelative`
- size: `224`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pAbsoluteSecurityDescriptor)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180039320`
- `0x18003c864`
- `0x18003cd60`

## callees

- `0x180003166`
- `0x180003172`
- `0x180038f40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038fa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038fef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038fa1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038fef`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180038f6f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180038f6f`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180038f95`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180038fdf`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180038f95`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x180038fdf`

## pseudocode

```c
__int64 __fastcall ORMakeSDRelative(PSECURITY_DESCRIPTOR pAbsoluteSecurityDescriptor, _QWORD *a2)
{
  DWORD LastError; // edi
  void *v5; // rax
  PSECURITY_DESCRIPTOR v6; // rbx
  WORD pControl; // [rsp+48h] [rbp+10h] BYREF
  DWORD dwBufferLength; // [rsp+50h] [rbp+18h] BYREF
  DWORD dwRevision; // [rsp+58h] [rbp+20h] BYREF

  dwBufferLength = 0;
  dwRevision = 0;
  pControl = 0;
  GetSecurityDescriptorControl(pAbsoluteSecurityDescriptor, &pControl, &dwRevision);
  if ( (pControl & 0x8000u) != 0 )
  {
    v6 = pAbsoluteSecurityDescriptor;
    goto LABEL_11;
  }
  MakeSelfRelativeSD(pAbsoluteSecurityDescriptor, 0, &dwBufferLength);
  if ( GetLastError() != 122 )
  {
    LastError = 1359;
LABEL_9:
    v6 = 0;
    goto LABEL_12;
  }
  v5 = o__aligned_malloc_0(dwBufferLength, 0x10u);
  v6 = v5;
  if ( !v5 )
  {
    LastError = 8;
    goto LABEL_9;
  }
  if ( MakeSelfRelativeSD(pAbsoluteSecurityDescriptor, v5, &dwBufferLength) )
  {
LABEL_11:
    LastError = 0;
    goto LABEL_12;
  }
  LastError = GetLastError();
  if ( LastError )
  {
    aligned_free(v6);
    goto LABEL_9;
  }
LABEL_12:
  *a2 = v6;
  return LastError;
}

```

## disassembly

```asm
0x180038f40  push    rbx
0x180038f42  push    rsi
0x180038f43  push    rdi
0x180038f44  sub     rsp, 20h
0x180038f48  mov     rsi, rdx
0x180038f4b  mov     [rsp+38h+dwBufferLength], 0
0x180038f53  xor     eax, eax
0x180038f55  mov     [rsp+38h+dwRevision], 0
0x180038f5d  lea     rdx, [rsp+38h+pControl]; pControl
0x180038f62  mov     [rsp+38h+pControl], ax
0x180038f67  lea     r8, [rsp+38h+dwRevision]; lpdwRevision
0x180038f6c  mov     rdi, rcx
0x180038f6f  call    cs:__imp_GetSecurityDescriptorControl
0x180038f76  nop     dword ptr [rax+rax+00h]
0x180038f7b  mov     eax, 8000h
0x180038f80  test    [rsp+38h+pControl], ax
0x180038f85  jnz     loc_18003900D
0x180038f8b  lea     r8, [rsp+38h+dwBufferLength]; lpdwBufferLength
0x180038f90  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x180038f92  mov     rcx, rdi; pAbsoluteSecurityDescriptor
0x180038f95  call    cs:__imp_MakeSelfRelativeSD
0x180038f9c  nop     dword ptr [rax+rax+00h]
0x180038fa1  call    cs:__imp_GetLastError
0x180038fa8  nop     dword ptr [rax+rax+00h]
0x180038fad  cmp     eax, 7Ah ; 'z'
0x180038fb0  jz      short loc_180038FB9
0x180038fb2  mov     edi, 54Fh
0x180038fb7  jmp     short loc_180039009
0x180038fb9  mov     ecx, [rsp+38h+dwBufferLength]; Size
0x180038fbd  mov     edx, 10h; Alignment
0x180038fc2  call    _o__aligned_malloc_0
0x180038fc7  mov     rbx, rax
0x180038fca  test    rax, rax
0x180038fcd  jnz     short loc_180038FD4
0x180038fcf  lea     edi, [rax+8]
0x180038fd2  jmp     short loc_180039009
0x180038fd4  lea     r8, [rsp+38h+dwBufferLength]; lpdwBufferLength
0x180038fd9  mov     rdx, rbx; pSelfRelativeSecurityDescriptor
0x180038fdc  mov     rcx, rdi; pAbsoluteSecurityDescriptor
0x180038fdf  call    cs:__imp_MakeSelfRelativeSD
0x180038fe6  nop     dword ptr [rax+rax+00h]
0x180038feb  test    eax, eax
0x180038fed  jnz     short loc_180039010
0x180038fef  call    cs:__imp_GetLastError
0x180038ff6  nop     dword ptr [rax+rax+00h]
0x180038ffb  mov     edi, eax
0x180038ffd  test    eax, eax
0x180038fff  jz      short loc_180039012
0x180039001  mov     rcx, rbx; Block
0x180039004  call    _aligned_free
0x180039009  xor     ebx, ebx
0x18003900b  jmp     short loc_180039012
0x18003900d  mov     rbx, rdi
0x180039010  xor     edi, edi
0x180039012  mov     [rsi], rbx
0x180039015  mov     eax, edi
0x180039017  add     rsp, 20h
0x18003901b  pop     rdi
0x18003901c  pop     rsi
0x18003901d  pop     rbx
0x18003901e  retn
```
