# RxpGetLinkedLuid

- ea: `0x14000f500`
- end: `0x14000f5d3`
- name: `RxpGetLinkedLuid`
- size: `211`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14007a510`

## callees

- `0x14000f500`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000f588`
- `ntoskrnl!ObfDereferenceObject` at `0x14000f588`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f5a0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f5a0`
- `ntoskrnl!SeQueryInformationToken` at `0x14000f52b`
- `ntoskrnl!SeQueryInformationToken` at `0x14000f52b`
- `ntoskrnl!SeGetLinkedToken` at `0x14000f556`
- `ntoskrnl!SeGetLinkedToken` at `0x14000f556`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x14000f570`
- `ntoskrnl!SeQueryAuthenticationIdToken` at `0x14000f570`

## pseudocode

```c
__int64 __fastcall RxpGetLinkedLuid(void *a1, struct _LUID *a2)
{
  NTSTATUS LinkedToken; // ebx
  __int64 v5; // rcx
  PACCESS_TOKEN Token; // [rsp+40h] [rbp+18h] BYREF
  PVOID TokenInformation; // [rsp+48h] [rbp+20h] BYREF

  Token = 0;
  TokenInformation = 0;
  LinkedToken = SeQueryInformationToken(a1, TokenElevationType, &TokenInformation);
  if ( LinkedToken >= 0 )
  {
    if ( *(_DWORD *)TokenInformation == 3 )
    {
      v5 = 2;
    }
    else
    {
      LinkedToken = -1073741700;
      if ( *(_DWORD *)TokenInformation != 2 )
        goto LABEL_6;
      v5 = 3;
    }
    LinkedToken = SeGetLinkedToken(v5, a1, &Token);
    if ( LinkedToken >= 0 )
      LinkedToken = SeQueryAuthenticationIdToken(Token, a2);
  }
LABEL_6:
  if ( Token )
    ObfDereferenceObject(Token);
  if ( TokenInformation )
    ExFreePoolWithTag(TokenInformation, 0);
  return (unsigned int)LinkedToken;
}

```

## disassembly

```asm
0x14000f500  mov     [rsp+arg_0], rbx
0x14000f505  mov     [rsp+arg_8], rsi
0x14000f50a  push    rdi
0x14000f50b  sub     rsp, 20h
0x14000f50f  xor     eax, eax
0x14000f511  lea     r8, [rsp+28h+TokenInformation]; TokenInformation
0x14000f516  mov     rsi, rdx
0x14000f519  mov     [rsp+28h+Token], rax
0x14000f51e  mov     edx, 12h; TokenInformationClass
0x14000f523  mov     [rsp+28h+TokenInformation], rax
0x14000f528  mov     rdi, rcx
0x14000f52b  call    cs:__imp_SeQueryInformationToken
0x14000f532  nop     dword ptr [rax+rax+00h]
0x14000f537  mov     ebx, eax
0x14000f539  test    eax, eax
0x14000f53b  js      short loc_14000F57E
0x14000f53d  mov     rax, [rsp+28h+TokenInformation]
0x14000f542  mov     ecx, [rax]
0x14000f544  cmp     ecx, 3
0x14000f547  jnz     short loc_14000F5BF
0x14000f549  mov     ecx, 2
0x14000f54e  lea     r8, [rsp+28h+Token]
0x14000f553  mov     rdx, rdi
0x14000f556  call    cs:__imp_SeGetLinkedToken
0x14000f55d  nop     dword ptr [rax+rax+00h]
0x14000f562  mov     ebx, eax
0x14000f564  test    eax, eax
0x14000f566  js      short loc_14000F57E
0x14000f568  mov     rcx, [rsp+28h+Token]; Token
0x14000f56d  mov     rdx, rsi; AuthenticationId
0x14000f570  call    cs:__imp_SeQueryAuthenticationIdToken
0x14000f577  nop     dword ptr [rax+rax+00h]
0x14000f57c  mov     ebx, eax
0x14000f57e  mov     rcx, [rsp+28h+Token]; Object
0x14000f583  test    rcx, rcx
0x14000f586  jz      short loc_14000F594
0x14000f588  call    cs:__imp_ObfDereferenceObject
0x14000f58f  nop     dword ptr [rax+rax+00h]
0x14000f594  mov     rcx, [rsp+28h+TokenInformation]; P
0x14000f599  test    rcx, rcx
0x14000f59c  jz      short loc_14000F5AC
0x14000f59e  xor     edx, edx; Tag
0x14000f5a0  call    cs:__imp_ExFreePoolWithTag
0x14000f5a7  nop     dword ptr [rax+rax+00h]
0x14000f5ac  mov     rsi, [rsp+28h+arg_8]
0x14000f5b1  mov     eax, ebx
0x14000f5b3  mov     rbx, [rsp+28h+arg_0]
0x14000f5b8  add     rsp, 20h
0x14000f5bc  pop     rdi
0x14000f5bd  retn
0x14000f5bf  mov     ebx, 0C000007Ch
0x14000f5c4  cmp     ecx, 2
0x14000f5c7  jnz     short loc_14000F57E
0x14000f5c9  mov     ecx, 3
0x14000f5ce  jmp     loc_14000F54E
```
