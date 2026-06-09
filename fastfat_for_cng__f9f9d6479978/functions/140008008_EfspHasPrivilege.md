# EfspHasPrivilege

- ea: `0x140008008`
- end: `0x140008087`
- name: `EfspHasPrivilege`
- size: `127`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14004ed40`
- `0x14005202c`

## callees

- `0x140008008`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140008072`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008072`
- `ntoskrnl!SeQueryInformationToken` at `0x140008023`
- `ntoskrnl!SeQueryInformationToken` at `0x140008023`

## pseudocode

```c
bool __fastcall EfspHasPrivilege(void *a1)
{
  bool v1; // bl
  __int64 i; // rdx
  PVOID TokenInformation; // [rsp+48h] [rbp+20h] BYREF

  TokenInformation = 0;
  v1 = 0;
  if ( SeQueryInformationToken(a1, TokenPrivileges, &TokenInformation) >= 0 )
  {
    for ( i = 0; (unsigned int)i < *(_DWORD *)TokenInformation; i = (unsigned int)(i + 1) )
    {
      if ( *((_DWORD *)TokenInformation + 3 * i + 1) == 18 && !*((_DWORD *)TokenInformation + 3 * i + 2) )
      {
        v1 = (*((_BYTE *)TokenInformation + 12 * i + 12) & 2) != 0;
        break;
      }
    }
  }
  if ( TokenInformation )
    ExFreePoolWithTag(TokenInformation, 0);
  return v1;
}

```

## disassembly

```asm
0x140008008  push    rbx
0x14000800a  sub     rsp, 20h
0x14000800e  lea     r8, [rsp+28h+TokenInformation]; TokenInformation
0x140008013  mov     [rsp+28h+TokenInformation], 0
0x14000801c  mov     edx, 3; TokenInformationClass
0x140008021  xor     bl, bl
0x140008023  call    cs:__imp_SeQueryInformationToken
0x14000802a  nop     dword ptr [rax+rax+00h]
0x14000802f  mov     rcx, [rsp+28h+TokenInformation]; P
0x140008034  test    eax, eax
0x140008036  js      short loc_14000806B
0x140008038  mov     r8d, [rcx]
0x14000803b  xor     edx, edx
0x14000803d  lea     r9d, [rdx+1]
0x140008041  cmp     edx, r8d
0x140008044  jnb     short loc_14000806B
0x140008046  lea     rax, [rdx+rdx*2]
0x14000804a  cmp     dword ptr [rcx+rax*4+4], 12h
0x14000804f  jnz     short loc_140008058
0x140008051  cmp     dword ptr [rcx+rax*4+8], 0
0x140008056  jz      short loc_14000805D
0x140008058  add     edx, r9d
0x14000805b  jmp     short loc_140008041
0x14000805d  xor     dl, dl
0x14000805f  test    byte ptr [rcx+rax*4+0Ch], 2
0x140008064  movzx   ebx, dl
0x140008067  cmovnz  ebx, r9d
0x14000806b  test    rcx, rcx
0x14000806e  jz      short loc_14000807E
0x140008070  xor     edx, edx; Tag
0x140008072  call    cs:__imp_ExFreePoolWithTag
0x140008079  nop     dword ptr [rax+rax+00h]
0x14000807e  mov     al, bl
0x140008080  add     rsp, 20h
0x140008084  pop     rbx
0x140008085  retn
```
