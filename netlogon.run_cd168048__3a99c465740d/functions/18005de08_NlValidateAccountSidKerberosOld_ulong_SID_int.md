# NlValidateAccountSidKerberosOld(ulong,_SID *,int *)

- ea: `0x18005de08`
- end: `0x18005dfd8`
- name: `?NlValidateAccountSidKerberosOld@@YAJKPEAU_SID@@PEAH@Z`
- size: `464`
- prototype: `int(unsigned int, struct _SID *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18005db8c`

## callees

- `0x180007518`
- `0x18005de08`
- `0x18008a5c0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005df9e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18005df9e`
- `RPCRT4!RpcImpersonateClient` at `0x18005de4a`
- `RPCRT4!RpcImpersonateClient` at `0x18005de4a`
- `RPCRT4!RpcRevertToSelf` at `0x18005dfb1`
- `RPCRT4!RpcRevertToSelf` at `0x18005dfb1`
- `RPCRT4!I_RpcMapWin32Status` at `0x18005de58`
- `RPCRT4!I_RpcMapWin32Status` at `0x18005de58`
- `ntdll!NtOpenThreadToken` at `0x18005de83`
- `ntdll!NtOpenThreadToken` at `0x18005de83`
- `ntdll!NtQueryInformationToken` at `0x18005dec8`
- `ntdll!NtQueryInformationToken` at `0x18005df23`
- `ntdll!NtQueryInformationToken` at `0x18005dec8`
- `ntdll!NtQueryInformationToken` at `0x18005df23`
- `ntdll!RtlEqualSid` at `0x18005df7a`
- `ntdll!RtlEqualSid` at `0x18005df7a`
- `ntdll!RtlValidSid` at `0x18005df51`
- `ntdll!RtlValidSid` at `0x18005df51`

## string_xrefs

- `0x18005de95`: `NlValidateAccountSidKerberos: NtOpenThreadToken failed %lx\n`
- `0x18005dedd`: `NlValidateAccountSidKerberos: NtQueryInformationToken failed %lx\n`
- `0x18005df38`: `NlValidateAccountSidKerberos: NtQueryInformationToken failed %lx\n`

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
0x18005de08  mov     rax, rsp
0x18005de0b  mov     [rax+8], rbx
0x18005de0f  push    rbp
0x18005de10  push    rsi
0x18005de11  push    rdi
0x18005de12  push    r12
0x18005de14  push    r13
0x18005de16  push    r14
0x18005de18  push    r15
0x18005de1a  sub     rsp, 40h
0x18005de1e  xor     r12d, r12d
0x18005de21  mov     r14, r8
0x18005de24  mov     [rax-48h], r12
0x18005de28  mov     r15, rdx
0x18005de2b  mov     [rax+18h], r12d
0x18005de2f  mov     r13d, ecx
0x18005de32  mov     [rax+20h], r12d
0x18005de36  test    r8, r8
0x18005de39  jz      loc_18005DFAC
0x18005de3f  test    rdx, rdx
0x18005de42  jz      loc_18005DFAC
0x18005de48  xor     ecx, ecx; BindingHandle
0x18005de4a  call    cs:__imp_RpcImpersonateClient
0x18005de51  nop     dword ptr [rax+rax+00h]
0x18005de56  mov     ecx, eax; Status
0x18005de58  call    cs:__imp_I_RpcMapWin32Status
0x18005de5f  nop     dword ptr [rax+rax+00h]
0x18005de64  mov     ebx, eax
0x18005de66  test    eax, eax
0x18005de68  js      loc_18005DFB1
0x18005de6e  lea     edi, [r12+1]
0x18005de73  mov     r8b, dil; OpenAsSelf
0x18005de76  lea     edx, [rdi+7]; DesiredAccess
0x18005de79  lea     r9, [rsp+78h+TokenHandle]; TokenHandle
0x18005de7e  lea     rcx, [r12-2]; ThreadHandle
0x18005de83  call    cs:__imp_NtOpenThreadToken
0x18005de8a  nop     dword ptr [rax+rax+00h]
0x18005de8f  mov     ebx, eax
0x18005de91  test    eax, eax
0x18005de93  jns     short loc_18005DEAE
0x18005de95  lea     rdx, aNlvalidateacco_1; "NlValidateAccountSidKerberos: NtOpenThr"...
0x18005de9c  mov     r8d, eax
0x18005de9f  mov     ecx, 100h; unsigned int
0x18005dea4  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005dea9  jmp     loc_18005DFB1
0x18005deae  mov     rcx, [rsp+78h+TokenHandle]; TokenHandle
0x18005deb3  lea     rax, [rsp+78h+TokenInformationLength]
0x18005debb  xor     r9d, r9d; TokenInformationLength
0x18005debe  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x18005dec3  xor     r8d, r8d; TokenInformation
0x18005dec6  mov     edx, edi; TokenInformationClass
0x18005dec8  call    cs:__imp_NtQueryInformationToken
0x18005decf  nop     dword ptr [rax+rax+00h]
0x18005ded4  mov     ebx, eax
0x18005ded6  cmp     eax, 0C0000023h
0x18005dedb  jz      short loc_18005DEE6
0x18005dedd  lea     rdx, aNlvalidateacco_2; "NlValidateAccountSidKerberos: NtQueryIn"...
0x18005dee4  jmp     short loc_18005DE9C
0x18005dee6  mov     ecx, [rsp+78h+TokenInformationLength]; size
0x18005deed  call    MIDL_user_allocate
0x18005def2  mov     rsi, rax
0x18005def5  test    rax, rax
0x18005def8  jnz     short loc_18005DF04
0x18005defa  mov     ebx, 0C000009Ah
0x18005deff  jmp     loc_18005DFB1
0x18005df04  mov     r9d, [rsp+78h+TokenInformationLength]; TokenInformationLength
0x18005df0c  lea     rax, [rsp+78h+arg_18]
0x18005df14  mov     rcx, [rsp+78h+TokenHandle]; TokenHandle
0x18005df19  mov     r8, rsi; TokenInformation
0x18005df1c  mov     edx, edi; TokenInformationClass
0x18005df1e  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x18005df23  call    cs:__imp_NtQueryInformationToken
0x18005df2a  nop     dword ptr [rax+rax+00h]
0x18005df2f  mov     ebx, eax
0x18005df31  test    eax, eax
0x18005df33  jns     short loc_18005DF4B
0x18005df35  mov     r8d, eax
0x18005df38  lea     rdx, aNlvalidateacco_2; "NlValidateAccountSidKerberos: NtQueryIn"...
0x18005df3f  mov     ecx, 100h; unsigned int
0x18005df44  call    ?NlPrintRoutine@@YAXKPEAGZZ; NlPrintRoutine(ulong,ushort *,...)
0x18005df49  jmp     short loc_18005DF9B
0x18005df4b  mov     rbp, [rsi]
0x18005df4e  mov     rcx, rbp; Sid
0x18005df51  call    cs:__imp_RtlValidSid
0x18005df58  nop     dword ptr [rax+rax+00h]
0x18005df5d  test    al, al
0x18005df5f  jz      short loc_18005DF96
0x18005df61  movzx   ecx, byte ptr [rbp+1]
0x18005df65  test    cl, cl
0x18005df67  jz      short loc_18005DF96
0x18005df69  mov     r12d, [rbp+rcx*4+4]
0x18005df6e  mov     rdx, rbp; Sid2
0x18005df71  sub     cl, dil
0x18005df74  mov     [rbp+1], cl
0x18005df77  mov     rcx, r15; Sid1
0x18005df7a  call    cs:__imp_RtlEqualSid
0x18005df81  nop     dword ptr [rax+rax+00h]
0x18005df86  test    al, al
0x18005df88  jz      short loc_18005DF8F
0x18005df8a  cmp     r12d, r13d
0x18005df8d  jz      short loc_18005DF91
0x18005df8f  xor     edi, edi
0x18005df91  mov     [r14], edi
0x18005df94  jmp     short loc_18005DF9B
0x18005df96  mov     ebx, 0C00000E5h
0x18005df9b  mov     rcx, rsi; Block
0x18005df9e  call    cs:__imp_free
0x18005dfa5  nop     dword ptr [rax+rax+00h]
0x18005dfaa  jmp     short loc_18005DFB1
0x18005dfac  mov     ebx, 0C000000Dh
0x18005dfb1  call    cs:__imp_RpcRevertToSelf
0x18005dfb8  nop     dword ptr [rax+rax+00h]
0x18005dfbd  mov     eax, ebx
0x18005dfbf  mov     rbx, [rsp+78h+arg_0]
0x18005dfc7  add     rsp, 40h
0x18005dfcb  pop     r15
0x18005dfcd  pop     r14
0x18005dfcf  pop     r13
0x18005dfd1  pop     r12
0x18005dfd3  pop     rdi
0x18005dfd4  pop     rsi
0x18005dfd5  pop     rbp
0x18005dfd6  retn
```
