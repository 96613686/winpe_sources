# WcpFilterLoadWithPrivilege

- ea: `0x1800ac2fc`
- end: `0x1800ac473`
- name: `WcpFilterLoadWithPrivilege`
- size: `375`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800abf80`

## callees

- `0x1800ab9b8`
- `0x1800ac2fc`
- `0x1800acb84`
- `0x1800acdc0`

## import_xrefs

- `ntdll!NtSetInformationThread` at `0x1800ac446`
- `ntdll!NtSetInformationThread` at `0x1800ac446`
- `ntdll!RtlImpersonateSelf` at `0x1800ac385`
- `ntdll!RtlImpersonateSelf` at `0x1800ac385`
- `ntdll!NtClose` at `0x1800ac41e`
- `ntdll!NtClose` at `0x1800ac41e`
- `ntdll!NtOpenThreadToken` at `0x1800ac359`
- `ntdll!NtOpenThreadToken` at `0x1800ac3a6`
- `ntdll!NtOpenThreadToken` at `0x1800ac359`
- `ntdll!NtOpenThreadToken` at `0x1800ac3a6`

## pseudocode

```c
__int64 __fastcall WcpFilterLoadWithPrivilege(void *Src)
{
  int v1; // edi
  int v3; // esi
  int v4; // eax
  unsigned int v5; // ebx
  NTSTATUS v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int v9; // eax
  __int64 ThreadInformation; // [rsp+48h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF

  TokenHandle = (void *)-1LL;
  v1 = 0;
  LODWORD(ThreadInformation) = 0;
  v3 = 0;
  v4 = NtFilterLoad(Src);
  v5 = v4;
  if ( v4 < 0 && (v4 == -2147023582 || v4 == (unsigned int)FilterHResultFromNtStatus(3221225569LL)) )
  {
    v6 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x28u, 0, &TokenHandle);
    if ( !v6 )
    {
LABEL_10:
      v8 = WcpSetPrivilege(TokenHandle, 10, 1, &ThreadInformation);
      if ( v8 )
        v9 = FilterHResultFromNtStatus(v8);
      else
        v9 = NtFilterLoad(Src);
      v5 = v9;
      if ( v3 )
        goto LABEL_17;
      v1 = ThreadInformation;
      goto LABEL_15;
    }
    if ( v6 == -1073741700 )
    {
      v6 = RtlImpersonateSelf(SecurityImpersonation);
      if ( v6 >= 0 )
      {
        v3 = 1;
        v7 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x28u, 0, &TokenHandle);
        if ( v7 )
        {
          v5 = FilterHResultFromNtStatus(v7);
          goto LABEL_17;
        }
        goto LABEL_10;
      }
    }
    v5 = FilterHResultFromNtStatus((unsigned int)v6);
  }
LABEL_15:
  if ( v1 && (unsigned int)WcpSetPrivilege(TokenHandle, 10, 0, 0) )
    goto LABEL_21;
LABEL_17:
  if ( TokenHandle != (void *)-1LL )
    NtClose(TokenHandle);
  if ( v3 )
  {
    ThreadInformation = 0;
    if ( NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u) )
LABEL_21:
      __fastfail(7u);
  }
  return v5;
}

```

## disassembly

```asm
0x1800ac2fc  mov     rax, rsp
0x1800ac2ff  mov     [rax+8], rbx
0x1800ac303  mov     [rax+20h], rbp
0x1800ac307  push    rsi
0x1800ac308  push    rdi
0x1800ac309  push    r15
0x1800ac30b  sub     rsp, 20h
0x1800ac30f  or      qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x1800ac314  xor     edi, edi
0x1800ac316  mov     [rax+10h], edi
0x1800ac319  mov     rbp, rcx
0x1800ac31c  xor     esi, esi
0x1800ac31e  call    NtFilterLoad
0x1800ac323  lea     r15, [rsi-2]
0x1800ac327  mov     ebx, eax
0x1800ac329  test    eax, eax
0x1800ac32b  jns     loc_1800AC3F7
0x1800ac331  cmp     eax, 80070522h
0x1800ac336  jz      short loc_1800AC34A
0x1800ac338  mov     ecx, 0C0000061h
0x1800ac33d  call    FilterHResultFromNtStatus
0x1800ac342  cmp     ebx, eax
0x1800ac344  jnz     loc_1800AC3F7
0x1800ac34a  xor     r8d, r8d; OpenAsSelf
0x1800ac34d  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x1800ac352  mov     rcx, r15; ThreadHandle
0x1800ac355  lea     edx, [r8+28h]; DesiredAccess
0x1800ac359  call    cs:__imp_NtOpenThreadToken
0x1800ac360  nop     dword ptr [rax+rax+00h]
0x1800ac365  mov     ebx, 1
0x1800ac36a  test    eax, eax
0x1800ac36c  jz      short loc_1800AC3C1
0x1800ac36e  cmp     eax, 0C000007Ch
0x1800ac373  jz      short loc_1800AC380
0x1800ac375  mov     ecx, eax
0x1800ac377  call    FilterHResultFromNtStatus
0x1800ac37c  mov     ebx, eax
0x1800ac37e  jmp     short loc_1800AC3F7
0x1800ac380  mov     ecx, 2; ImpersonationLevel
0x1800ac385  call    cs:__imp_RtlImpersonateSelf
0x1800ac38c  nop     dword ptr [rax+rax+00h]
0x1800ac391  test    eax, eax
0x1800ac393  js      short loc_1800AC375
0x1800ac395  xor     r8d, r8d; OpenAsSelf
0x1800ac398  lea     r9, [rsp+38h+TokenHandle]; TokenHandle
0x1800ac39d  mov     rcx, r15; ThreadHandle
0x1800ac3a0  mov     esi, ebx
0x1800ac3a2  lea     edx, [r8+28h]; DesiredAccess
0x1800ac3a6  call    cs:__imp_NtOpenThreadToken
0x1800ac3ad  nop     dword ptr [rax+rax+00h]
0x1800ac3b2  test    eax, eax
0x1800ac3b4  jz      short loc_1800AC3C1
0x1800ac3b6  mov     ecx, eax
0x1800ac3b8  call    FilterHResultFromNtStatus
0x1800ac3bd  mov     ebx, eax
0x1800ac3bf  jmp     short loc_1800AC413
0x1800ac3c1  mov     rcx, [rsp+38h+TokenHandle]
0x1800ac3c6  lea     r9, [rsp+38h+ThreadInformation]
0x1800ac3cb  mov     r8d, ebx
0x1800ac3ce  mov     edx, 0Ah
0x1800ac3d3  call    WcpSetPrivilege
0x1800ac3d8  test    eax, eax
0x1800ac3da  jz      short loc_1800AC3E5
0x1800ac3dc  mov     ecx, eax
0x1800ac3de  call    FilterHResultFromNtStatus
0x1800ac3e3  jmp     short loc_1800AC3ED
0x1800ac3e5  mov     rcx, rbp; Src
0x1800ac3e8  call    NtFilterLoad
0x1800ac3ed  mov     ebx, eax
0x1800ac3ef  test    esi, esi
0x1800ac3f1  jnz     short loc_1800AC413
0x1800ac3f3  mov     edi, dword ptr [rsp+38h+ThreadInformation]
0x1800ac3f7  test    edi, edi
0x1800ac3f9  jz      short loc_1800AC413
0x1800ac3fb  mov     rcx, [rsp+38h+TokenHandle]
0x1800ac400  xor     r9d, r9d
0x1800ac403  xor     r8d, r8d
0x1800ac406  lea     edx, [r9+0Ah]
0x1800ac40a  call    WcpSetPrivilege
0x1800ac40f  test    eax, eax
0x1800ac411  jnz     short loc_1800AC456
0x1800ac413  mov     rcx, [rsp+38h+TokenHandle]; Handle
0x1800ac418  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800ac41c  jz      short loc_1800AC42A
0x1800ac41e  call    cs:__imp_NtClose
0x1800ac425  nop     dword ptr [rax+rax+00h]
0x1800ac42a  test    esi, esi
0x1800ac42c  jz      short loc_1800AC45D
0x1800ac42e  and     [rsp+38h+ThreadInformation], 0
0x1800ac434  lea     r8, [rsp+38h+ThreadInformation]; ThreadInformation
0x1800ac439  mov     r9d, 8; ThreadInformationLength
0x1800ac43f  mov     rcx, r15; ThreadHandle
0x1800ac442  lea     edx, [r9-3]; ThreadInformationClass
0x1800ac446  call    cs:__imp_NtSetInformationThread
0x1800ac44d  nop     dword ptr [rax+rax+00h]
0x1800ac452  test    eax, eax
0x1800ac454  jz      short loc_1800AC45D
0x1800ac456  mov     ecx, 7
0x1800ac45b  int     29h; Win8: RtlFailFast(ecx)
0x1800ac45d  mov     rbp, [rsp+38h+arg_18]
0x1800ac462  mov     eax, ebx
0x1800ac464  mov     rbx, [rsp+38h+arg_0]
0x1800ac469  add     rsp, 20h
0x1800ac46d  pop     r15
0x1800ac46f  pop     rdi
0x1800ac470  pop     rsi
0x1800ac471  retn
```
