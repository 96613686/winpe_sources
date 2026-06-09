# DfscImpersonateLinkedToken

- ea: `0x1400170a8`
- end: `0x14001728b`
- name: `DfscImpersonateLinkedToken`
- size: `483`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140014520`
- `0x140014810`

## callees

- `0x140005f70`
- `0x1400170a8`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140017246`
- `ntoskrnl!ZwClose` at `0x14001725b`
- `ntoskrnl!ZwClose` at `0x140017246`
- `ntoskrnl!ZwClose` at `0x14001725b`
- `ntoskrnl!ZwQueryInformationToken` at `0x140017128`
- `ntoskrnl!ZwQueryInformationToken` at `0x140017158`
- `ntoskrnl!ZwQueryInformationToken` at `0x140017198`
- `ntoskrnl!ZwQueryInformationToken` at `0x140017128`
- `ntoskrnl!ZwQueryInformationToken` at `0x140017158`
- `ntoskrnl!ZwQueryInformationToken` at `0x140017198`
- `ntoskrnl!ZwDuplicateToken` at `0x140017208`
- `ntoskrnl!ZwDuplicateToken` at `0x140017208`
- `ntoskrnl!ZwSetInformationThread` at `0x14001722f`
- `ntoskrnl!ZwSetInformationThread` at `0x14001722f`

## pseudocode

```c
__int64 __fastcall DfscImpersonateLinkedToken(void **a1)
{
  void *v1; // rdi
  NTSTATUS v2; // ebx
  ULONG ReturnLength; // [rsp+30h] [rbp-49h] BYREF
  int v5; // [rsp+34h] [rbp-45h] BYREF
  void *ThreadInformation; // [rsp+38h] [rbp-41h] BYREF
  HANDLE ExistingTokenHandle; // [rsp+40h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-31h] BYREF
  __int64 v9; // [rsp+78h] [rbp-1h] BYREF
  int v10; // [rsp+80h] [rbp+7h]
  _OWORD TokenInformation[3]; // [rsp+88h] [rbp+Fh] BYREF
  __int64 v12; // [rsp+B8h] [rbp+3Fh]

  v1 = *a1;
  ThreadInformation = 0;
  v12 = 0;
  ReturnLength = 0;
  v9 = 0;
  v10 = 0;
  ExistingTokenHandle = 0;
  v5 = 0;
  memset(TokenInformation, 0, sizeof(TokenInformation));
  memset(&ObjectAttributes, 0, 44);
  v2 = ZwQueryInformationToken(v1, TokenStatistics, TokenInformation, 0x38u, &ReturnLength);
  if ( v2 >= 0 )
  {
    v2 = ZwQueryInformationToken(v1, TokenElevationType, &v5, 4u, &ReturnLength);
    if ( v2 >= 0 )
    {
      if ( v5 == 1 )
      {
        v2 = -1073741788;
      }
      else
      {
        v2 = ZwQueryInformationToken(v1, TokenLinkedToken, &ExistingTokenHandle, 8u, &ReturnLength);
        if ( v2 >= 0 )
        {
          LOWORD(v10) = 1;
          v9 = 0x20000000CLL;
          ObjectAttributes.SecurityQualityOfService = &v9;
          ObjectAttributes.Length = 48;
          ObjectAttributes.RootDirectory = 0;
          ObjectAttributes.Attributes = 512;
          ObjectAttributes.ObjectName = 0;
          ObjectAttributes.SecurityDescriptor = 0;
          v2 = ZwDuplicateToken(ExistingTokenHandle, 0xCu, &ObjectAttributes, 0, TokenImpersonation, &ThreadInformation);
          if ( v2 >= 0 )
            v2 = ZwSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
        }
      }
    }
  }
  if ( ThreadInformation )
    ZwClose(ThreadInformation);
  if ( ExistingTokenHandle )
    ZwClose(ExistingTokenHandle);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1400170a8  mov     [rsp-8+arg_8], rbx
0x1400170ad  mov     [rsp-8+arg_10], rdi
0x1400170b2  push    rbp
0x1400170b3  lea     rbp, [rsp-57h]
0x1400170b8  sub     rsp, 0D0h
0x1400170bf  mov     rax, cs:__security_cookie
0x1400170c6  xor     rax, rsp
0x1400170c9  mov     [rbp+57h+var_10], rax
0x1400170cd  mov     rdi, [rcx]
0x1400170d0  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1400170d4  xor     eax, eax
0x1400170d6  mov     [rbp+57h+ThreadInformation], 0
0x1400170de  xorps   xmm0, xmm0
0x1400170e1  mov     [rbp+57h+var_18], rax
0x1400170e5  mov     r9d, 38h ; '8'; TokenInformationLength
0x1400170eb  mov     [rbp+57h+var_A0], eax
0x1400170ee  mov     [rbp+57h+var_58], rax
0x1400170f2  mov     rcx, rdi; TokenHandle
0x1400170f5  mov     [rbp+57h+var_50], eax
0x1400170f8  mov     [rbp+57h+ExistingTokenHandle], rax
0x1400170fc  lea     rax, [rbp+57h+var_A0]
0x140017100  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140017104  lea     edx, [r9-2Eh]; TokenInformationClass
0x140017108  mov     [rbp+57h+var_9C], 0
0x14001710f  movups  [rbp+57h+TokenInformation], xmm0
0x140017113  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x140017118  movups  [rbp+57h+var_38], xmm0
0x14001711c  movups  [rbp+57h+var_28], xmm0
0x140017120  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140017124  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x140017128  call    cs:__imp_ZwQueryInformationToken
0x14001712f  nop     dword ptr [rax+rax+00h]
0x140017134  mov     ebx, eax
0x140017136  test    eax, eax
0x140017138  js      loc_14001723D
0x14001713e  mov     r9d, 4; TokenInformationLength
0x140017144  lea     rax, [rbp+57h+var_A0]
0x140017148  lea     r8, [rbp+57h+var_9C]; TokenInformation
0x14001714c  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x140017151  mov     rcx, rdi; TokenHandle
0x140017154  lea     edx, [r9+0Eh]; TokenInformationClass
0x140017158  call    cs:__imp_ZwQueryInformationToken
0x14001715f  nop     dword ptr [rax+rax+00h]
0x140017164  mov     ebx, eax
0x140017166  test    eax, eax
0x140017168  js      loc_14001723D
0x14001716e  cmp     [rbp+57h+var_9C], 1
0x140017172  jnz     short loc_14001717E
0x140017174  mov     ebx, 0C0000024h
0x140017179  jmp     loc_14001723D
0x14001717e  mov     r9d, 8; TokenInformationLength
0x140017184  lea     rax, [rbp+57h+var_A0]
0x140017188  lea     r8, [rbp+57h+ExistingTokenHandle]; TokenInformation
0x14001718c  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x140017191  mov     rcx, rdi; TokenHandle
0x140017194  lea     edx, [r9+0Bh]; TokenInformationClass
0x140017198  call    cs:__imp_ZwQueryInformationToken
0x14001719f  nop     dword ptr [rax+rax+00h]
0x1400171a4  mov     ebx, eax
0x1400171a6  test    eax, eax
0x1400171a8  js      loc_14001723D
0x1400171ae  mov     edx, 0Ch; DesiredAccess
0x1400171b3  mov     word ptr [rbp+57h+var_50], 1
0x1400171b9  lea     rax, [rbp+57h+var_58]
0x1400171bd  mov     dword ptr [rbp+57h+var_58], edx
0x1400171c0  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], rax
0x1400171c4  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400171c8  lea     rax, [rbp+57h+ThreadInformation]
0x1400171cc  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400171d3  lea     ecx, [rdx-0Ah]
0x1400171d6  mov     [rsp+0D0h+NewTokenHandle], rax; NewTokenHandle
0x1400171db  mov     dword ptr [rbp+57h+var_58+4], ecx
0x1400171de  xor     r9d, r9d; EffectiveOnly
0x1400171e1  mov     dword ptr [rsp+0D0h+ReturnLength], ecx; TokenType
0x1400171e5  mov     rcx, [rbp+57h+ExistingTokenHandle]; ExistingTokenHandle
0x1400171e9  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1400171f1  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x1400171f8  mov     [rbp+57h+ObjectAttributes.ObjectName], 0
0x140017200  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], 0
0x140017208  call    cs:__imp_ZwDuplicateToken
0x14001720f  nop     dword ptr [rax+rax+00h]
0x140017214  mov     ebx, eax
0x140017216  test    eax, eax
0x140017218  js      short loc_14001723D
0x14001721a  mov     r9d, 8; ThreadInformationLength
0x140017220  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x140017224  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x14001722b  lea     edx, [r9-3]; ThreadInformationClass
0x14001722f  call    cs:__imp_ZwSetInformationThread
0x140017236  nop     dword ptr [rax+rax+00h]
0x14001723b  mov     ebx, eax
0x14001723d  mov     rcx, [rbp+57h+ThreadInformation]; Handle
0x140017241  test    rcx, rcx
0x140017244  jz      short loc_140017252
0x140017246  call    cs:__imp_ZwClose
0x14001724d  nop     dword ptr [rax+rax+00h]
0x140017252  mov     rcx, [rbp+57h+ExistingTokenHandle]; Handle
0x140017256  test    rcx, rcx
0x140017259  jz      short loc_140017267
0x14001725b  call    cs:__imp_ZwClose
0x140017262  nop     dword ptr [rax+rax+00h]
0x140017267  mov     eax, ebx
0x140017269  mov     rcx, [rbp+57h+var_10]
0x14001726d  xor     rcx, rsp; StackCookie
0x140017270  call    __security_check_cookie
0x140017275  lea     r11, [rsp+0D0h+var_s0]
0x14001727d  mov     rbx, [r11+18h]
0x140017281  mov     rdi, [r11+20h]
0x140017285  mov     rsp, r11
0x140017288  pop     rbp
0x140017289  retn
```
