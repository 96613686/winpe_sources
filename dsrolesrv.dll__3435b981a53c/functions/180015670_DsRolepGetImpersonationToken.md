# DsRolepGetImpersonationToken

- ea: `0x180015670`
- end: `0x1800157c3`
- name: `DsRolepGetImpersonationToken`
- size: `339`
- prototype: `__int64 __fastcall(PHANDLE NewTokenHandle)`
- caller_count: `6`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180005400`
- `0x18000e818`
- `0x18000eb40`
- `0x1800150cc`
- `0x1800159a0`
- `0x180015ff0`

## callees

- `0x180015670`
- `0x18002c050`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800156d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800156d9`
- `RPCRT4!RpcRevertToSelf` at `0x180015719`
- `RPCRT4!RpcRevertToSelf` at `0x180015719`
- `RPCRT4!RpcImpersonateClient` at `0x1800156ea`
- `RPCRT4!RpcImpersonateClient` at `0x1800156ea`
- `ntdll!NtOpenThreadToken` at `0x1800156cb`
- `ntdll!NtOpenThreadToken` at `0x18001570c`
- `ntdll!NtOpenThreadToken` at `0x1800156cb`
- `ntdll!NtOpenThreadToken` at `0x18001570c`
- `ntdll!NtDuplicateToken` at `0x18001577d`
- `ntdll!NtDuplicateToken` at `0x18001577d`
- `ntdll!RtlNtStatusToDosError` at `0x180015795`
- `ntdll!RtlNtStatusToDosError` at `0x180015795`
- `ntdll!NtClose` at `0x180015789`
- `ntdll!NtClose` at `0x180015789`

## pseudocode

```c
__int64 __fastcall DsRolepGetImpersonationToken(PHANDLE NewTokenHandle)
{
  unsigned int v1; // ebx
  char v3; // si
  NTSTATUS v4; // eax
  int v5; // edi
  void *TokenHandle; // [rsp+30h] [rbp-50h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-48h] BYREF
  __int64 v9; // [rsp+68h] [rbp-18h] BYREF
  int v10; // [rsp+70h] [rbp-10h]

  v1 = 0;
  v9 = 0;
  v10 = 0;
  TokenHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  v3 = 0;
  v4 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
  if ( v4 < 0 )
  {
    if ( v4 == -1073741700 )
    {
      v1 = RpcImpersonateClient(0);
      v3 = 1;
      if ( v1 )
        return v1;
    }
  }
  else
  {
    CloseHandle(TokenHandle);
  }
  v5 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xAu, 1u, &TokenHandle);
  if ( v3 )
    RpcRevertToSelf();
  if ( v5 < 0 )
    return RtlNtStatusToDosError(v5);
  ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  ObjectAttributes.SecurityDescriptor = 0;
  v9 = 0x20000000CLL;
  LOWORD(v10) = 0;
  ObjectAttributes.SecurityQualityOfService = &v9;
  v5 = NtDuplicateToken(TokenHandle, 0x2Eu, &ObjectAttributes, 0, TokenImpersonation, NewTokenHandle);
  NtClose(TokenHandle);
  if ( v5 < 0 )
    return RtlNtStatusToDosError(v5);
  return v1;
}

```

## disassembly

```asm
0x180015670  mov     [rsp-18h+arg_8], rbx
0x180015675  mov     [rsp-18h+arg_10], rsi
0x18001567a  push    rbp
0x18001567b  push    rdi
0x18001567c  push    r14
0x18001567e  mov     rbp, rsp
0x180015681  sub     rsp, 80h
0x180015688  mov     rax, cs:__security_cookie
0x18001568f  xor     rax, rsp
0x180015692  mov     [rbp+var_8], rax
0x180015696  xorps   xmm0, xmm0
0x180015699  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18001569d  xor     eax, eax
0x18001569f  xor     ebx, ebx
0x1800156a1  mov     r14, rcx
0x1800156a4  mov     [rbp+var_18], rax
0x1800156a8  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800156ac  mov     r8b, 1; OpenAsSelf
0x1800156af  mov     [rbp+var_10], eax
0x1800156b2  lea     rdi, [rbx-2]
0x1800156b6  mov     [rbp+TokenHandle], rax
0x1800156ba  mov     rcx, rdi; ThreadHandle
0x1800156bd  lea     edx, [rbx+8]; DesiredAccess
0x1800156c0  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800156c4  xor     sil, sil
0x1800156c7  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1800156cb  call    cs:__imp_NtOpenThreadToken
0x1800156d1  test    eax, eax
0x1800156d3  js      short loc_1800156E1
0x1800156d5  mov     rcx, [rbp+TokenHandle]; hObject
0x1800156d9  call    cs:__imp_CloseHandle
0x1800156df  jmp     short loc_1800156FD
0x1800156e1  cmp     eax, 0C000007Ch
0x1800156e6  jnz     short loc_1800156FD
0x1800156e8  xor     ecx, ecx; BindingHandle
0x1800156ea  call    cs:__imp_RpcImpersonateClient
0x1800156f0  mov     ebx, eax
0x1800156f2  mov     sil, 1
0x1800156f5  test    eax, eax
0x1800156f7  jnz     loc_18001579D
0x1800156fd  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180015701  mov     r8b, 1; OpenAsSelf
0x180015704  mov     edx, 0Ah; DesiredAccess
0x180015709  mov     rcx, rdi; ThreadHandle
0x18001570c  call    cs:__imp_NtOpenThreadToken
0x180015712  mov     edi, eax
0x180015714  test    sil, sil
0x180015717  jz      short loc_18001571F
0x180015719  call    cs:__imp_RpcRevertToSelf
0x18001571f  test    edi, edi
0x180015721  js      short loc_180015793
0x180015723  mov     ecx, 2
0x180015728  mov     [rsp+80h+NewTokenHandle], r14; NewTokenHandle
0x18001572d  mov     dword ptr [rbp+var_18+4], ecx
0x180015730  lea     rax, [rbp+var_18]
0x180015734  mov     [rsp+80h+TokenType], ecx; TokenType
0x180015738  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18001573c  xor     r9d, r9d; EffectiveOnly
0x18001573f  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180015746  lea     edx, [rcx+2Ch]; DesiredAccess
0x180015749  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180015751  mov     rcx, [rbp+TokenHandle]; ExistingTokenHandle
0x180015755  mov     [rbp+ObjectAttributes.Attributes], 0
0x18001575c  mov     [rbp+ObjectAttributes.ObjectName], 0
0x180015764  mov     [rbp+ObjectAttributes.SecurityDescriptor], 0
0x18001576c  mov     dword ptr [rbp+var_18], 0Ch
0x180015773  mov     word ptr [rbp+var_10], 0
0x180015779  mov     [rbp+ObjectAttributes.SecurityQualityOfService], rax
0x18001577d  call    cs:__imp_NtDuplicateToken
0x180015783  mov     rcx, [rbp+TokenHandle]; Handle
0x180015787  mov     edi, eax
0x180015789  call    cs:__imp_NtClose
0x18001578f  test    edi, edi
0x180015791  jns     short loc_18001579D
0x180015793  mov     ecx, edi; Status
0x180015795  call    cs:__imp_RtlNtStatusToDosError
0x18001579b  mov     ebx, eax
0x18001579d  mov     eax, ebx
0x18001579f  mov     rcx, [rbp+var_8]
0x1800157a3  xor     rcx, rsp; StackCookie
0x1800157a6  call    __security_check_cookie
0x1800157ab  lea     r11, [rsp+80h+var_s0]
0x1800157b3  mov     rbx, [r11+28h]
0x1800157b7  mov     rsi, [r11+30h]
0x1800157bb  mov     rsp, r11
0x1800157be  pop     r14
0x1800157c0  pop     rdi
0x1800157c1  pop     rbp
0x1800157c2  retn
```
