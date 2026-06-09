# NlValidateAccountSidKerberosOld(ulong,_SID *,int *)

- ea: `0x180059cfc`
- end: `0x180059e95`
- name: `?NlValidateAccountSidKerberosOld@@YAJKPEAU_SID@@PEAH@Z`
- size: `409`
- prototype: `int(unsigned int, struct _SID *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180059aec`

## callees

- `0x180007278`
- `0x180059cfc`
- `0x1800844d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180059e68`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180059e68`
- `RPCRT4!RpcImpersonateClient` at `0x180059d3e`
- `RPCRT4!RpcImpersonateClient` at `0x180059d3e`
- `RPCRT4!RpcRevertToSelf` at `0x180059e75`
- `RPCRT4!RpcRevertToSelf` at `0x180059e75`
- `RPCRT4!I_RpcMapWin32Status` at `0x180059d46`
- `RPCRT4!I_RpcMapWin32Status` at `0x180059d46`
- `ntdll!NtOpenThreadToken` at `0x180059d6b`
- `ntdll!NtOpenThreadToken` at `0x180059d6b`
- `ntdll!NtQueryInformationToken` at `0x180059daa`
- `ntdll!NtQueryInformationToken` at `0x180059dff`
- `ntdll!NtQueryInformationToken` at `0x180059daa`
- `ntdll!NtQueryInformationToken` at `0x180059dff`
- `ntdll!RtlEqualSid` at `0x180059e4a`
- `ntdll!RtlEqualSid` at `0x180059e4a`
- `ntdll!RtlValidSid` at `0x180059e27`
- `ntdll!RtlValidSid` at `0x180059e27`

## string_xrefs

- `0x180059d77`: `NlValidateAccountSidKerberos: NtOpenThreadToken failed %lx\n`
- `0x180059db9`: `NlValidateAccountSidKerberos: NtQueryInformationToken failed %lx\n`
- `0x180059e0e`: `NlValidateAccountSidKerberos: NtQueryInformationToken failed %lx\n`

## pseudocode

```c
__int64 __fastcall NlValidateAccountSidKerberosOld(int a1, struct _SID *a2, int *a3)
{
  RPC_STATUS v6; // eax
  int v7; // ebx
  int v8; // edi
  NTSTATUS v9; // eax
  unsigned int v10; // eax
  _QWORD *v11; // rsi
  NTSTATUS v12; // eax
  _BYTE *v13; // rbp
  __int64 v14; // rcx
  int v15; // r12d
  void *TokenHandle; // [rsp+30h] [rbp-48h] BYREF
  ULONG TokenInformationLength; // [rsp+90h] [rbp+18h] BYREF
  ULONG ReturnLength; // [rsp+98h] [rbp+20h] BYREF

  TokenHandle = 0;
  TokenInformationLength = 0;
  ReturnLength = 0;
  if ( a3 && a2 )
  {
    v6 = RpcImpersonateClient(0);
    v7 = I_RpcMapWin32Status(v6);
    if ( v7 >= 0 )
    {
      v8 = 1;
      v9 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
      v7 = v9;
      if ( v9 >= 0 )
      {
        v10 = NtQueryInformationToken(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
        v7 = v10;
        if ( v10 == -1073741789 )
        {
          v11 = MIDL_user_allocate(TokenInformationLength);
          if ( v11 )
          {
            v12 = NtQueryInformationToken(TokenHandle, TokenUser, v11, TokenInformationLength, &ReturnLength);
            v7 = v12;
            if ( v12 >= 0 )
            {
              v13 = (_BYTE *)*v11;
              if ( RtlValidSid((PSID)*v11) && (v14 = (unsigned __int8)v13[1], (_BYTE)v14) )
              {
                v15 = *(_DWORD *)&v13[4 * v14 + 4];
                v13[1] = v14 - 1;
                if ( !RtlEqualSid(a2, v13) || v15 != a1 )
                  v8 = 0;
                *a3 = v8;
              }
              else
              {
                v7 = -1073741595;
              }
            }
            else
            {
              NlPrintRoutine(
                0x100u,
                L"NlValidateAccountSidKerberos: NtQueryInformationToken failed %lx\n",
                (unsigned int)v12);
            }
            free(v11);
          }
          else
          {
            v7 = -1073741670;
          }
        }
        else
        {
          NlPrintRoutine(0x100u, L"NlValidateAccountSidKerberos: NtQueryInformationToken failed %lx\n", v10);
        }
      }
      else
      {
        NlPrintRoutine(0x100u, L"NlValidateAccountSidKerberos: NtOpenThreadToken failed %lx\n", (unsigned int)v9);
      }
    }
  }
  else
  {
    v7 = -1073741811;
  }
  RpcRevertToSelf();
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180059cfc  mov     rax, rsp
0x180059cff  mov     [rax+8], rbx
0x180059d03  push    rbp
0x180059d04  push    rsi
0x180059d05  push    rdi
0x180059d06  push    r12
0x180059d08  push    r13
0x180059d0a  push    r14
0x180059d0c  push    r15
0x180059d0e  sub     rsp, 40h
0x180059d12  xor     r12d, r12d
0x180059d15  mov     r14, r8
0x180059d18  mov     [rax-48h], r12
0x180059d1c  mov     r15, rdx
0x180059d1f  mov     [rax+18h], r12d
0x180059d23  mov     r13d, ecx
0x180059d26  mov     [rax+20h], r12d
0x180059d2a  test    r8, r8
0x180059d2d  jz      loc_180059E70
0x180059d33  test    rdx, rdx
0x180059d36  jz      loc_180059E70
0x180059d3c  xor     ecx, ecx; BindingHandle
0x180059d3e  call    cs:__imp_RpcImpersonateClient
0x180059d44  mov     ecx, eax; Status
0x180059d46  call    cs:__imp_I_RpcMapWin32Status
0x180059d4c  mov     ebx, eax
0x180059d4e  test    eax, eax
0x180059d50  js      loc_180059E75
0x180059d56  lea     edi, [r12+1]
0x180059d5b  mov     r8b, dil; OpenAsSelf
0x180059d5e  lea     edx, [rdi+7]; DesiredAccess
0x180059d61  lea     r9, [rsp+78h+TokenHandle]; TokenHandle
0x180059d66  lea     rcx, [r12-2]; ThreadHandle
0x180059d6b  call    cs:__imp_NtOpenThreadToken
0x180059d71  mov     ebx, eax
0x180059d73  test    eax, eax
0x180059d75  jns     short loc_180059D90
0x180059d77  lea     rdx, aNlvalidateacco_1; "NlValidateAccountSidKerberos: NtOpenThr"...
0x180059d7e  mov     r8d, eax
0x180059d81  mov     ecx, 100h; unsigned int
0x180059d86  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180059d8b  jmp     loc_180059E75
0x180059d90  mov     rcx, [rsp+78h+TokenHandle]; TokenHandle
0x180059d95  lea     rax, [rsp+78h+TokenInformationLength]
0x180059d9d  xor     r9d, r9d; TokenInformationLength
0x180059da0  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x180059da5  xor     r8d, r8d; TokenInformation
0x180059da8  mov     edx, edi; TokenInformationClass
0x180059daa  call    cs:__imp_NtQueryInformationToken
0x180059db0  mov     ebx, eax
0x180059db2  cmp     eax, 0C0000023h
0x180059db7  jz      short loc_180059DC2
0x180059db9  lea     rdx, aNlvalidateacco_2; "NlValidateAccountSidKerberos: NtQueryIn"...
0x180059dc0  jmp     short loc_180059D7E
0x180059dc2  mov     ecx, [rsp+78h+TokenInformationLength]; size
0x180059dc9  call    MIDL_user_allocate
0x180059dce  mov     rsi, rax
0x180059dd1  test    rax, rax
0x180059dd4  jnz     short loc_180059DE0
0x180059dd6  mov     ebx, 0C000009Ah
0x180059ddb  jmp     loc_180059E75
0x180059de0  mov     r9d, [rsp+78h+TokenInformationLength]; TokenInformationLength
0x180059de8  lea     rax, [rsp+78h+arg_18]
0x180059df0  mov     rcx, [rsp+78h+TokenHandle]; TokenHandle
0x180059df5  mov     r8, rsi; TokenInformation
0x180059df8  mov     edx, edi; TokenInformationClass
0x180059dfa  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x180059dff  call    cs:__imp_NtQueryInformationToken
0x180059e05  mov     ebx, eax
0x180059e07  test    eax, eax
0x180059e09  jns     short loc_180059E21
0x180059e0b  mov     r8d, eax
0x180059e0e  lea     rdx, aNlvalidateacco_2; "NlValidateAccountSidKerberos: NtQueryIn"...
0x180059e15  mov     ecx, 100h; unsigned int
0x180059e1a  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x180059e1f  jmp     short loc_180059E65
0x180059e21  mov     rbp, [rsi]
0x180059e24  mov     rcx, rbp; Sid
0x180059e27  call    cs:__imp_RtlValidSid
0x180059e2d  test    al, al
0x180059e2f  jz      short loc_180059E60
0x180059e31  movzx   ecx, byte ptr [rbp+1]
0x180059e35  test    cl, cl
0x180059e37  jz      short loc_180059E60
0x180059e39  mov     r12d, [rbp+rcx*4+4]
0x180059e3e  mov     rdx, rbp; Sid2
0x180059e41  sub     cl, dil
0x180059e44  mov     [rbp+1], cl
0x180059e47  mov     rcx, r15; Sid1
0x180059e4a  call    cs:__imp_RtlEqualSid
0x180059e50  test    al, al
0x180059e52  jz      short loc_180059E59
0x180059e54  cmp     r12d, r13d
0x180059e57  jz      short loc_180059E5B
0x180059e59  xor     edi, edi
0x180059e5b  mov     [r14], edi
0x180059e5e  jmp     short loc_180059E65
0x180059e60  mov     ebx, 0C00000E5h
0x180059e65  mov     rcx, rsi; Block
0x180059e68  call    cs:__imp_free
0x180059e6e  jmp     short loc_180059E75
0x180059e70  mov     ebx, 0C000000Dh
0x180059e75  call    cs:__imp_RpcRevertToSelf
0x180059e7b  mov     eax, ebx
0x180059e7d  mov     rbx, [rsp+78h+arg_0]
0x180059e85  add     rsp, 40h
0x180059e89  pop     r15
0x180059e8b  pop     r14
0x180059e8d  pop     r13
0x180059e8f  pop     r12
0x180059e91  pop     rdi
0x180059e92  pop     rsi
0x180059e93  pop     rbp
0x180059e94  retn
```
