# ORMakeSDRelative

- ea: `0x1400270ec`
- end: `0x1400271cc`
- name: `ORMakeSDRelative`
- size: `224`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pAbsoluteSecurityDescriptor)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140023cb0`
- `0x14002909c`
- `0x140029598`

## callees

- `0x1400029c6`
- `0x1400029d2`
- `0x1400270ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002714d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002719b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002714d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14002719b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x14002711b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x14002711b`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x140027141`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x14002718b`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x140027141`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x14002718b`

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
0x1400270ec  push    rbx
0x1400270ee  push    rsi
0x1400270ef  push    rdi
0x1400270f0  sub     rsp, 20h
0x1400270f4  mov     rsi, rdx
0x1400270f7  mov     [rsp+38h+dwBufferLength], 0
0x1400270ff  xor     eax, eax
0x140027101  mov     [rsp+38h+dwRevision], 0
0x140027109  lea     rdx, [rsp+38h+pControl]; pControl
0x14002710e  mov     [rsp+38h+pControl], ax
0x140027113  lea     r8, [rsp+38h+dwRevision]; lpdwRevision
0x140027118  mov     rdi, rcx
0x14002711b  call    cs:__imp_GetSecurityDescriptorControl
0x140027122  nop     dword ptr [rax+rax+00h]
0x140027127  mov     eax, 8000h
0x14002712c  test    [rsp+38h+pControl], ax
0x140027131  jnz     loc_1400271B9
0x140027137  lea     r8, [rsp+38h+dwBufferLength]; lpdwBufferLength
0x14002713c  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x14002713e  mov     rcx, rdi; pAbsoluteSecurityDescriptor
0x140027141  call    cs:__imp_MakeSelfRelativeSD
0x140027148  nop     dword ptr [rax+rax+00h]
0x14002714d  call    cs:__imp_GetLastError
0x140027154  nop     dword ptr [rax+rax+00h]
0x140027159  cmp     eax, 7Ah ; 'z'
0x14002715c  jz      short loc_140027165
0x14002715e  mov     edi, 54Fh
0x140027163  jmp     short loc_1400271B5
0x140027165  mov     ecx, [rsp+38h+dwBufferLength]; Size
0x140027169  mov     edx, 10h; Alignment
0x14002716e  call    _o__aligned_malloc_0
0x140027173  mov     rbx, rax
0x140027176  test    rax, rax
0x140027179  jnz     short loc_140027180
0x14002717b  lea     edi, [rax+8]
0x14002717e  jmp     short loc_1400271B5
0x140027180  lea     r8, [rsp+38h+dwBufferLength]; lpdwBufferLength
0x140027185  mov     rdx, rbx; pSelfRelativeSecurityDescriptor
0x140027188  mov     rcx, rdi; pAbsoluteSecurityDescriptor
0x14002718b  call    cs:__imp_MakeSelfRelativeSD
0x140027192  nop     dword ptr [rax+rax+00h]
0x140027197  test    eax, eax
0x140027199  jnz     short loc_1400271BC
0x14002719b  call    cs:__imp_GetLastError
0x1400271a2  nop     dword ptr [rax+rax+00h]
0x1400271a7  mov     edi, eax
0x1400271a9  test    eax, eax
0x1400271ab  jz      short loc_1400271BE
0x1400271ad  mov     rcx, rbx; Block
0x1400271b0  call    _aligned_free
0x1400271b5  xor     ebx, ebx
0x1400271b7  jmp     short loc_1400271BE
0x1400271b9  mov     rbx, rdi
0x1400271bc  xor     edi, edi
0x1400271be  mov     [rsi], rbx
0x1400271c1  mov     eax, edi
0x1400271c3  add     rsp, 20h
0x1400271c7  pop     rdi
0x1400271c8  pop     rsi
0x1400271c9  pop     rbx
0x1400271ca  retn
```
