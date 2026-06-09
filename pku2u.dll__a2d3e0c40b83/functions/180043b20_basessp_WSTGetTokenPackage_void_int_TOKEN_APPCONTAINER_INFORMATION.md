# basessp::WSTGetTokenPackage(void *,int *,_TOKEN_APPCONTAINER_INFORMATION * *)

- ea: `0x180043b20`
- end: `0x180043bde`
- name: `?WSTGetTokenPackage@basessp@@YAJPEAXPEAHPEAPEAU_TOKEN_APPCONTAINER_INFORMATION@@@Z`
- size: `190`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, int *, struct _TOKEN_APPCONTAINER_INFORMATION **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800436dc`

## callees

- `0x1800436b0`
- `0x180043b04`
- `0x180043b20`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180043b66`
- `ntdll!NtQueryInformationToken` at `0x180043bb6`
- `ntdll!NtQueryInformationToken` at `0x180043b66`
- `ntdll!NtQueryInformationToken` at `0x180043bb6`

## pseudocode

```c
__int64 __fastcall basessp::WSTGetTokenPackage(
        HANDLE TokenHandle,
        _DWORD *a2,
        int *a3,
        struct _TOKEN_APPCONTAINER_INFORMATION **a4)
{
  unsigned __int64 v7; // rdx
  NTSTATUS v8; // edi
  void *v9; // rbx
  void *v10; // rdx
  ULONG TokenInformationLength; // [rsp+58h] [rbp+10h] BYREF
  int v13; // [rsp+60h] [rbp+18h] BYREF

  *a2 = 0;
  *(_QWORD *)a3 = 0;
  v13 = 0;
  TokenInformationLength = 4;
  v8 = NtQueryInformationToken(TokenHandle, TokenIsAppContainer, &v13, 4u, &TokenInformationLength);
  if ( v8 >= 0 && v13 )
  {
    *a2 = 1;
    TokenInformationLength = 76;
    v9 = basessp::WSTAllocate((basessp *)0x4C, v7);
    if ( v9 )
    {
      v8 = NtQueryInformationToken(
             TokenHandle,
             TokenAppContainerSid,
             v9,
             TokenInformationLength,
             &TokenInformationLength);
      if ( v8 < 0 )
        basessp::WSTFree((basessp *)v9, v10);
      else
        *(_QWORD *)a3 = v9;
    }
    else
    {
      return (unsigned int)-1073741670;
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180043b20  mov     r11, rsp
0x180043b23  mov     [r11+8], rbx
0x180043b27  push    rbp
0x180043b28  push    rsi
0x180043b29  push    rdi
0x180043b2a  sub     rsp, 30h
0x180043b2e  mov     r9d, 4; TokenInformationLength
0x180043b34  mov     dword ptr [rdx], 0
0x180043b3a  mov     rsi, r8
0x180043b3d  mov     qword ptr [r8], 0
0x180043b44  mov     rbx, rdx
0x180043b47  mov     [rsp+48h+arg_10], 0
0x180043b4f  lea     rax, [r11+10h]
0x180043b53  mov     [r11+10h], r9d
0x180043b57  lea     edx, [r9+19h]; TokenInformationClass
0x180043b5b  mov     [r11-28h], rax
0x180043b5f  lea     r8, [r11+18h]; TokenInformation
0x180043b63  mov     rbp, rcx
0x180043b66  call    cs:__imp_NtQueryInformationToken
0x180043b6c  mov     edi, eax
0x180043b6e  test    eax, eax
0x180043b70  js      short loc_180043BCF
0x180043b72  cmp     [rsp+48h+arg_10], 0
0x180043b77  jz      short loc_180043BCF
0x180043b79  mov     ecx, 4Ch ; 'L'; this
0x180043b7e  mov     dword ptr [rbx], 1
0x180043b84  mov     [rsp+48h+TokenInformationLength], ecx
0x180043b88  call    ?WSTAllocate@basessp@@YAPEAX_K@Z; basessp::WSTAllocate(unsigned __int64)
0x180043b8d  mov     rbx, rax
0x180043b90  test    rax, rax
0x180043b93  jnz     short loc_180043B9C
0x180043b95  mov     edi, 0C000009Ah
0x180043b9a  jmp     short loc_180043BCF
0x180043b9c  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x180043ba1  lea     rax, [rsp+48h+TokenInformationLength]
0x180043ba6  mov     r8, rbx; TokenInformation
0x180043ba9  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180043bae  mov     edx, 1Fh; TokenInformationClass
0x180043bb3  mov     rcx, rbp; TokenHandle
0x180043bb6  call    cs:__imp_NtQueryInformationToken
0x180043bbc  mov     edi, eax
0x180043bbe  test    eax, eax
0x180043bc0  js      short loc_180043BC7
0x180043bc2  mov     [rsi], rbx
0x180043bc5  jmp     short loc_180043BCF
0x180043bc7  mov     rcx, rbx; this
0x180043bca  call    ?WSTFree@basessp@@YAXPEAX@Z; basessp::WSTFree(void *)
0x180043bcf  mov     rbx, [rsp+48h+arg_0]
0x180043bd4  mov     eax, edi
0x180043bd6  add     rsp, 30h
0x180043bda  pop     rdi
0x180043bdb  pop     rsi
0x180043bdc  pop     rbp
0x180043bdd  retn
```
