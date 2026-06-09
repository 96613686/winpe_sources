# Pku2uImpersonateToken2(void *,void * *,int *)

- ea: `0x180014ba0`
- end: `0x180014c56`
- name: `?Pku2uImpersonateToken2@@YAJPEAXPEAPEAXPEAH@Z`
- size: `182`
- prototype: `__int64 __fastcall(void *, void **, int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180020238`
- `0x1800286bc`

## callees

- `0x180014ba0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014c4e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014c4e`
- `ntdll!NtSetInformationThread` at `0x180014c0c`
- `ntdll!NtSetInformationThread` at `0x180014c0c`
- `ntdll!NtOpenThreadToken` at `0x180014bdb`
- `ntdll!NtOpenThreadToken` at `0x180014bdb`

## pseudocode

```c
NTSTATUS __fastcall Pku2uImpersonateToken2(void *a1, void **a2, int *a3)
{
  NTSTATUS v5; // esi
  NTSTATUS result; // eax
  void *ThreadInformation; // [rsp+30h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF

  ThreadInformation = a1;
  *a3 = 0;
  *a2 = 0;
  TokenHandle = 0;
  v5 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &TokenHandle);
  if ( (int)(v5 + 0x80000000) < 0 || v5 == -1073741700 )
  {
    *a3 = 1;
    result = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
    *a2 = TokenHandle;
  }
  else
  {
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x180014ba0  mov     [rsp+arg_10], rbx
0x180014ba5  mov     [rsp+arg_18], rsi
0x180014baa  mov     [rsp+ThreadInformation], rcx
0x180014baf  push    rdi
0x180014bb0  sub     rsp, 20h
0x180014bb4  xor     eax, eax
0x180014bb6  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x180014bbb  mov     [r8], eax
0x180014bbe  mov     rdi, r8
0x180014bc1  mov     [rdx], rax
0x180014bc4  mov     rbx, rdx
0x180014bc7  mov     r8b, 1; OpenAsSelf
0x180014bca  mov     [rsp+28h+TokenHandle], rax
0x180014bcf  mov     edx, 0Ch; DesiredAccess
0x180014bd4  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180014bdb  call    cs:__imp_NtOpenThreadToken
0x180014be1  mov     esi, eax
0x180014be3  mov     eax, 80000000h
0x180014be8  lea     ecx, [rsi+rax]
0x180014beb  test    eax, ecx
0x180014bed  jz      short loc_180014C2A
0x180014bef  mov     r9d, 8; ThreadInformationLength
0x180014bf5  mov     dword ptr [rdi], 1
0x180014bfb  lea     r8, [rsp+28h+ThreadInformation]; ThreadInformation
0x180014c00  mov     edx, 5; ThreadInformationClass
0x180014c05  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180014c0c  call    cs:__imp_NtSetInformationThread
0x180014c12  mov     rcx, [rsp+28h+TokenHandle]
0x180014c17  mov     [rbx], rcx
0x180014c1a  mov     rbx, [rsp+28h+arg_10]
0x180014c1f  mov     rsi, [rsp+28h+arg_18]
0x180014c24  add     rsp, 20h
0x180014c28  pop     rdi
0x180014c29  retn
0x180014c2a  cmp     esi, 0C000007Ch
0x180014c30  jz      short loc_180014BEF
0x180014c32  mov     rcx, [rsp+28h+TokenHandle]; hObject
0x180014c37  test    rcx, rcx
0x180014c3a  jnz     short loc_180014C4E
0x180014c3c  mov     rbx, [rsp+28h+arg_10]
0x180014c41  mov     eax, esi
0x180014c43  mov     rsi, [rsp+28h+arg_18]
0x180014c48  add     rsp, 20h
0x180014c4c  pop     rdi
0x180014c4d  retn
0x180014c4e  call    cs:__imp_CloseHandle
0x180014c54  jmp     short loc_180014C3C
```
