# EfspHasTCBPrivilege

- ea: `0x140051788`
- end: `0x14005189f`
- name: `EfspHasTCBPrivilege`
- size: `279`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x14004eff0`

## callees

- `0x140051788`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14005186e`
- `ntoskrnl!ZwClose` at `0x14005186e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051884`
- `ntoskrnl!ExFreePoolWithTag` at `0x140051884`
- `ntoskrnl!ExAllocatePool2` at `0x140051801`
- `ntoskrnl!ExAllocatePool2` at `0x140051801`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x1400517b5`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x1400517b5`
- `ntoskrnl!ZwQueryInformationToken` at `0x1400517e1`
- `ntoskrnl!ZwQueryInformationToken` at `0x140051831`
- `ntoskrnl!ZwQueryInformationToken` at `0x1400517e1`
- `ntoskrnl!ZwQueryInformationToken` at `0x140051831`

## pseudocode

```c
char EfspHasTCBPrivilege()
{
  _DWORD *Pool2; // rbx
  char v1; // di
  __int64 i; // rcx
  ULONG TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF
  HANDLE TokenHandle; // [rsp+48h] [rbp+10h] BYREF

  Pool2 = 0;
  TokenHandle = 0;
  TokenInformationLength = 0;
  v1 = 0;
  if ( ZwOpenProcessTokenEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, 0x200u, &TokenHandle) >= 0
    && ZwQueryInformationToken(TokenHandle, TokenPrivileges, 0, 0, &TokenInformationLength) == -1073741789 )
  {
    Pool2 = (_DWORD *)ExAllocatePool2(64, TokenInformationLength, 1265854021);
    if ( Pool2 )
    {
      if ( ZwQueryInformationToken(TokenHandle, TokenPrivileges, Pool2, TokenInformationLength, &TokenInformationLength) >= 0 )
      {
        for ( i = 0; (unsigned int)i < *Pool2; i = (unsigned int)(i + 1) )
        {
          if ( Pool2[3 * i + 1] == 7 && !Pool2[3 * i + 2] )
          {
            v1 = 1;
            break;
          }
        }
      }
    }
  }
  if ( TokenHandle )
    ZwClose(TokenHandle);
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0);
  return v1;
}

```

## disassembly

```asm
0x140051788  mov     rax, rsp
0x14005178b  mov     [rax+18h], rbx
0x14005178f  push    rdi
0x140051790  sub     rsp, 30h
0x140051794  xor     ebx, ebx
0x140051796  mov     qword ptr [rax+10h], 0
0x14005179e  lea     r9, [rax+10h]; TokenHandle
0x1400517a2  mov     [rax+8], ebx
0x1400517a5  mov     r8d, 200h; HandleAttributes
0x1400517ab  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1400517af  xor     dil, dil
0x1400517b2  lea     edx, [rbx+8]; DesiredAccess
0x1400517b5  call    cs:__imp_ZwOpenProcessTokenEx
0x1400517bc  nop     dword ptr [rax+rax+00h]
0x1400517c1  test    eax, eax
0x1400517c3  js      loc_140051864
0x1400517c9  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x1400517ce  lea     rax, [rsp+38h+TokenInformationLength]
0x1400517d3  xor     r9d, r9d; TokenInformationLength
0x1400517d6  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1400517db  xor     r8d, r8d; TokenInformation
0x1400517de  lea     edx, [rbx+3]; TokenInformationClass
0x1400517e1  call    cs:__imp_ZwQueryInformationToken
0x1400517e8  nop     dword ptr [rax+rax+00h]
0x1400517ed  cmp     eax, 0C0000023h
0x1400517f2  jnz     short loc_140051864
0x1400517f4  mov     edx, [rsp+38h+TokenInformationLength]
0x1400517f8  lea     ecx, [rbx+40h]
0x1400517fb  mov     r8d, 4B736645h
0x140051801  call    cs:__imp_ExAllocatePool2
0x140051808  nop     dword ptr [rax+rax+00h]
0x14005180d  mov     rbx, rax
0x140051810  test    rax, rax
0x140051813  jz      short loc_140051864
0x140051815  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x14005181a  lea     rax, [rsp+38h+TokenInformationLength]
0x14005181f  mov     rcx, [rsp+38h+TokenHandle]; TokenHandle
0x140051824  mov     r8, rbx; TokenInformation
0x140051827  mov     edx, 3; TokenInformationClass
0x14005182c  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x140051831  call    cs:__imp_ZwQueryInformationToken
0x140051838  nop     dword ptr [rax+rax+00h]
0x14005183d  test    eax, eax
0x14005183f  js      short loc_140051864
0x140051841  mov     r8d, [rbx]
0x140051844  xor     ecx, ecx
0x140051846  cmp     ecx, r8d
0x140051849  jnb     short loc_140051864
0x14005184b  lea     rdx, [rcx+rcx*2]
0x14005184f  cmp     dword ptr [rbx+rdx*4+4], 7
0x140051854  jnz     short loc_14005185D
0x140051856  cmp     dword ptr [rbx+rdx*4+8], 0
0x14005185b  jz      short loc_140051861
0x14005185d  inc     ecx
0x14005185f  jmp     short loc_140051846
0x140051861  mov     dil, 1
0x140051864  mov     rcx, [rsp+38h+TokenHandle]; Handle
0x140051869  test    rcx, rcx
0x14005186c  jz      short loc_14005187A
0x14005186e  call    cs:__imp_ZwClose
0x140051875  nop     dword ptr [rax+rax+00h]
0x14005187a  test    rbx, rbx
0x14005187d  jz      short loc_140051890
0x14005187f  xor     edx, edx; Tag
0x140051881  mov     rcx, rbx; P
0x140051884  call    cs:__imp_ExFreePoolWithTag
0x14005188b  nop     dword ptr [rax+rax+00h]
0x140051890  mov     rbx, [rsp+38h+arg_10]
0x140051895  mov     al, dil
0x140051898  add     rsp, 30h
0x14005189c  pop     rdi
0x14005189d  retn
```
