# basessp::BaseSSP::WSTGetTokenUser(void *,_TOKEN_USER * *)

- ea: `0x180043be4`
- end: `0x180043c8c`
- name: `?WSTGetTokenUser@BaseSSP@basessp@@QEAAJPEAXPEAPEAU_TOKEN_USER@@@Z`
- size: `168`
- prototype: `__int64 __fastcall(basessp::BaseSSP *__hidden this, HANDLE TokenHandle, struct _TOKEN_USER **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800436dc`

## callees

- `0x180012820`
- `0x180018870`
- `0x180043be4`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180043c16`
- `ntdll!NtQueryInformationToken` at `0x180043c64`
- `ntdll!NtQueryInformationToken` at `0x180043c16`
- `ntdll!NtQueryInformationToken` at `0x180043c64`

## pseudocode

```c
NTSTATUS __fastcall basessp::BaseSSP::WSTGetTokenUser(
        basessp::BaseSSP *this,
        HANDLE TokenHandle,
        struct _TOKEN_USER **a3)
{
  NTSTATUS result; // eax
  struct _TOKEN_USER *v7; // rbx
  NTSTATUS v8; // edi
  ULONG TokenInformationLength; // [rsp+78h] [rbp+20h] BYREF

  TokenInformationLength = 0;
  result = NtQueryInformationToken(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  if ( result == -1073741789 )
  {
    v7 = (struct _TOKEN_USER *)basessp::BaseSSP::WSTAllocate(this, TokenInformationLength);
    if ( v7 )
    {
      v8 = NtQueryInformationToken(TokenHandle, TokenUser, v7, TokenInformationLength, &TokenInformationLength);
      if ( v8 < 0 )
        basessp::BaseSSP::WSTFree(this, v7);
      else
        *a3 = v7;
      return v8;
    }
    else
    {
      return -1073741670;
    }
  }
  else if ( result >= 0 )
  {
    return -1073741823;
  }
  return result;
}

```

## disassembly

```asm
0x180043be4  push    rbx
0x180043be6  push    rsi
0x180043be7  push    rdi
0x180043be8  push    r14
0x180043bea  sub     rsp, 38h
0x180043bee  mov     rdi, rdx
0x180043bf1  mov     [rsp+58h+TokenInformationLength], 0
0x180043bf9  xor     r9d, r9d; TokenInformationLength
0x180043bfc  lea     rax, [rsp+58h+TokenInformationLength]
0x180043c01  mov     r14, r8
0x180043c04  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180043c09  mov     rsi, rcx
0x180043c0c  xor     r8d, r8d; TokenInformation
0x180043c0f  mov     rcx, rdi; TokenHandle
0x180043c12  lea     edx, [r9+1]; TokenInformationClass
0x180043c16  call    cs:__imp_NtQueryInformationToken
0x180043c1c  cmp     eax, 0C0000023h
0x180043c21  jz      short loc_180043C2F
0x180043c23  test    eax, eax
0x180043c25  mov     ecx, 0C0000001h
0x180043c2a  cmovns  eax, ecx
0x180043c2d  jmp     short loc_180043C82
0x180043c2f  mov     edx, [rsp+58h+TokenInformationLength]; unsigned __int64
0x180043c33  mov     rcx, rsi; this
0x180043c36  call    ?WSTAllocate@BaseSSP@basessp@@QEAAPEAX_K@Z; basessp::BaseSSP::WSTAllocate(unsigned __int64)
0x180043c3b  mov     rbx, rax
0x180043c3e  test    rax, rax
0x180043c41  jnz     short loc_180043C4A
0x180043c43  mov     eax, 0C000009Ah
0x180043c48  jmp     short loc_180043C82
0x180043c4a  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x180043c4f  lea     rax, [rsp+58h+TokenInformationLength]
0x180043c54  mov     r8, rbx; TokenInformation
0x180043c57  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180043c5c  mov     edx, 1; TokenInformationClass
0x180043c61  mov     rcx, rdi; TokenHandle
0x180043c64  call    cs:__imp_NtQueryInformationToken
0x180043c6a  mov     edi, eax
0x180043c6c  test    eax, eax
0x180043c6e  js      short loc_180043C75
0x180043c70  mov     [r14], rbx
0x180043c73  jmp     short loc_180043C80
0x180043c75  mov     rdx, rbx; void *
0x180043c78  mov     rcx, rsi; this
0x180043c7b  call    ?WSTFree@BaseSSP@basessp@@QEAAXPEAX@Z; basessp::BaseSSP::WSTFree(void *)
0x180043c80  mov     eax, edi
0x180043c82  add     rsp, 38h
0x180043c86  pop     r14
0x180043c88  pop     rdi
0x180043c89  pop     rsi
0x180043c8a  pop     rbx
0x180043c8b  retn
```
