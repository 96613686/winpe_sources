# ORMakeSDRelative

- ea: `0x18002fb20`
- end: `0x18002fc00`
- name: `ORMakeSDRelative`
- size: `224`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pAbsoluteSecurityDescriptor)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002cdfc`
- `0x18002ff60`
- `0x18003045c`

## callees

- `0x180003542`
- `0x18000354e`
- `0x18002fb20`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fbcf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fbcf`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18002fb4f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18002fb4f`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18002fb75`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18002fbbf`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18002fb75`
- `api-ms-win-security-base-l1-1-0!MakeSelfRelativeSD` at `0x18002fbbf`

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
0x18002fb20  push    rbx
0x18002fb22  push    rsi
0x18002fb23  push    rdi
0x18002fb24  sub     rsp, 20h
0x18002fb28  mov     rsi, rdx
0x18002fb2b  mov     [rsp+38h+dwBufferLength], 0
0x18002fb33  xor     eax, eax
0x18002fb35  mov     [rsp+38h+dwRevision], 0
0x18002fb3d  lea     rdx, [rsp+38h+pControl]; pControl
0x18002fb42  mov     [rsp+38h+pControl], ax
0x18002fb47  lea     r8, [rsp+38h+dwRevision]; lpdwRevision
0x18002fb4c  mov     rdi, rcx
0x18002fb4f  call    cs:__imp_GetSecurityDescriptorControl
0x18002fb56  nop     dword ptr [rax+rax+00h]
0x18002fb5b  mov     eax, 8000h
0x18002fb60  test    [rsp+38h+pControl], ax
0x18002fb65  jnz     loc_18002FBED
0x18002fb6b  lea     r8, [rsp+38h+dwBufferLength]; lpdwBufferLength
0x18002fb70  xor     edx, edx; pSelfRelativeSecurityDescriptor
0x18002fb72  mov     rcx, rdi; pAbsoluteSecurityDescriptor
0x18002fb75  call    cs:__imp_MakeSelfRelativeSD
0x18002fb7c  nop     dword ptr [rax+rax+00h]
0x18002fb81  call    cs:__imp_GetLastError
0x18002fb88  nop     dword ptr [rax+rax+00h]
0x18002fb8d  cmp     eax, 7Ah ; 'z'
0x18002fb90  jz      short loc_18002FB99
0x18002fb92  mov     edi, 54Fh
0x18002fb97  jmp     short loc_18002FBE9
0x18002fb99  mov     ecx, [rsp+38h+dwBufferLength]; Size
0x18002fb9d  mov     edx, 10h; Alignment
0x18002fba2  call    _o__aligned_malloc_0
0x18002fba7  mov     rbx, rax
0x18002fbaa  test    rax, rax
0x18002fbad  jnz     short loc_18002FBB4
0x18002fbaf  lea     edi, [rax+8]
0x18002fbb2  jmp     short loc_18002FBE9
0x18002fbb4  lea     r8, [rsp+38h+dwBufferLength]; lpdwBufferLength
0x18002fbb9  mov     rdx, rbx; pSelfRelativeSecurityDescriptor
0x18002fbbc  mov     rcx, rdi; pAbsoluteSecurityDescriptor
0x18002fbbf  call    cs:__imp_MakeSelfRelativeSD
0x18002fbc6  nop     dword ptr [rax+rax+00h]
0x18002fbcb  test    eax, eax
0x18002fbcd  jnz     short loc_18002FBF0
0x18002fbcf  call    cs:__imp_GetLastError
0x18002fbd6  nop     dword ptr [rax+rax+00h]
0x18002fbdb  mov     edi, eax
0x18002fbdd  test    eax, eax
0x18002fbdf  jz      short loc_18002FBF2
0x18002fbe1  mov     rcx, rbx; Block
0x18002fbe4  call    _aligned_free
0x18002fbe9  xor     ebx, ebx
0x18002fbeb  jmp     short loc_18002FBF2
0x18002fbed  mov     rbx, rdi
0x18002fbf0  xor     edi, edi
0x18002fbf2  mov     [rsi], rbx
0x18002fbf5  mov     eax, edi
0x18002fbf7  add     rsp, 20h
0x18002fbfb  pop     rdi
0x18002fbfc  pop     rsi
0x18002fbfd  pop     rbx
0x18002fbfe  retn
```
