# ClfsEnableThreadPrivilege(ulong,void * *)

- ea: `0x140036dd0`
- end: `0x14003719c`
- name: `?ClfsEnableThreadPrivilege@@YAJKPEAPEAX@Z`
- size: `972`
- prototype: `__int64 __fastcall(unsigned int, void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14004b314`
- `0x14004b3e0`

## callees

- `0x140017e40`
- `0x140036dd0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x140037127`
- `ntoskrnl!ZwClose` at `0x140037156`
- `ntoskrnl!ZwClose` at `0x14003716c`
- `ntoskrnl!ZwClose` at `0x14007d16c`
- `ntoskrnl!ZwClose` at `0x14007d19d`
- `ntoskrnl!ZwClose` at `0x14007d1b3`
- `ntoskrnl!ZwClose` at `0x140037127`
- `ntoskrnl!ZwClose` at `0x140037156`
- `ntoskrnl!ZwClose` at `0x14003716c`
- `ntoskrnl!ZwClose` at `0x14007d16c`
- `ntoskrnl!ZwClose` at `0x14007d19d`
- `ntoskrnl!ZwClose` at `0x14007d1b3`
- `ntoskrnl!ZwOpenThreadTokenEx` at `0x140036e69`
- `ntoskrnl!ZwOpenThreadTokenEx` at `0x140036e69`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x140036ea4`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x140036ea4`
- `ntoskrnl!ZwQuerySecurityObject` at `0x140036eda`
- `ntoskrnl!ZwQuerySecurityObject` at `0x140036f4b`
- `ntoskrnl!ZwQuerySecurityObject` at `0x140036eda`
- `ntoskrnl!ZwQuerySecurityObject` at `0x140036f4b`
- `ntoskrnl!ZwDuplicateToken` at `0x140036fe5`
- `ntoskrnl!ZwDuplicateToken` at `0x140036fe5`
- `ntoskrnl!ZwSetInformationThread` at `0x140037015`
- `ntoskrnl!ZwSetInformationThread` at `0x1400370e0`
- `ntoskrnl!ZwSetInformationThread` at `0x140037111`
- `ntoskrnl!ZwSetInformationThread` at `0x14007d156`
- `ntoskrnl!ZwSetInformationThread` at `0x140037015`
- `ntoskrnl!ZwSetInformationThread` at `0x1400370e0`
- `ntoskrnl!ZwSetInformationThread` at `0x140037111`
- `ntoskrnl!ZwSetInformationThread` at `0x14007d156`
- `ntoskrnl!ZwAdjustPrivilegesToken` at `0x1400370a2`
- `ntoskrnl!ZwAdjustPrivilegesToken` at `0x1400370a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037140`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007d187`
- `ntoskrnl!ExFreePoolWithTag` at `0x140037140`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007d187`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140036f0a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140036f0a`

## pseudocode

```c
__int64 __fastcall ClfsEnableThreadPrivilege(__int64 a1, void **a2)
{
  HANDLE v3; // rsi
  PVOID PoolWithTag; // rdi
  char v5; // r15
  NTSTATUS v6; // eax
  NTSTATUS v7; // ebx
  ULONG LengthNeeded; // [rsp+38h] [rbp-E0h] BYREF
  HANDLE Handle; // [rsp+40h] [rbp-D8h] BYREF
  void *ThreadInformation; // [rsp+48h] [rbp-D0h] BYREF
  HANDLE v12[2]; // [rsp+50h] [rbp-C8h] BYREF
  PVOID v13; // [rsp+60h] [rbp-B8h]
  __int64 v14; // [rsp+68h] [rbp-B0h]
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-A8h] BYREF
  __int64 v16; // [rsp+A0h] [rbp-78h] BYREF
  int v17; // [rsp+A8h] [rbp-70h]
  struct _TOKEN_PRIVILEGES NewState[2]; // [rsp+B0h] [rbp-68h] BYREF

  Handle = 0;
  v12[0] = 0;
  v3 = 0;
  ThreadInformation = 0;
  PoolWithTag = 0;
  v13 = 0;
  v16 = 0;
  v17 = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  LengthNeeded = 0;
  v5 = 0;
  *a2 = 0;
  v6 = ZwOpenThreadTokenEx((HANDLE)0xFFFFFFFFFFFFFFFELL, 0x20002u, 0, 0x200u, &Handle);
  v7 = v6;
  if ( v6 < 0 )
  {
    if ( v6 == -1073741700 )
    {
      v7 = ZwOpenProcessTokenEx((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x20002u, 0x200u, v12);
      v3 = v12[0];
    }
  }
  else
  {
    v3 = Handle;
    *a2 = Handle;
  }
  if ( v7 >= 0 )
  {
    v7 = ZwQuerySecurityObject(v3, 4u, 0, 0, &LengthNeeded);
    if ( v7 == -1073741789 )
    {
      PoolWithTag = ExAllocatePoolWithTag(PagedPool, LengthNeeded, 0x58666C43u);
      v13 = PoolWithTag;
      if ( PoolWithTag )
      {
        v7 = ZwQuerySecurityObject(v3, 4u, PoolWithTag, LengthNeeded, &LengthNeeded);
        if ( v7 >= 0 )
        {
          ObjectAttributes.Length = 48;
          ObjectAttributes.RootDirectory = 0;
          ObjectAttributes.Attributes = 512;
          ObjectAttributes.ObjectName = 0;
          ObjectAttributes.SecurityDescriptor = PoolWithTag;
          v16 = 0x20000000CLL;
          LOWORD(v17) = 1;
          ObjectAttributes.SecurityQualityOfService = &v16;
          v7 = ZwDuplicateToken(v3, 0x2Cu, &ObjectAttributes, 0, TokenImpersonation, &ThreadInformation);
          if ( v7 >= 0 )
          {
            v7 = ZwSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
            if ( v7 >= 0 )
            {
              v5 = 1;
              *(_OWORD *)&NewState[0].Privileges[0].Attributes = 0;
              NewState[0].PrivilegeCount = 1;
              v14 = 8;
              v12[1] = (HANDLE)8;
              NewState[0].Privileges[0].Luid = (LUID)8LL;
              NewState[0].Privileges[0].Attributes = 2;
              v7 = ZwAdjustPrivilegesToken(ThreadInformation, 0, NewState, 0, 0, 0);
              if ( v7 == 262 )
                v7 = -1073741727;
              if ( v7 >= 0 )
                v7 = ZwSetInformationThread(
                       (HANDLE)0xFFFFFFFFFFFFFFFELL,
                       ThreadImpersonationToken,
                       &ThreadInformation,
                       8u);
            }
          }
        }
      }
      else
      {
        v7 = -1073741670;
      }
    }
  }
  if ( v7 < 0 )
  {
    if ( v5 )
      ZwSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &Handle, 8u);
    if ( Handle )
      ZwClose(Handle);
  }
  if ( PoolWithTag )
    ExFreePoolWithTag(PoolWithTag, 0x58666C43u);
  if ( ThreadInformation )
    ZwClose(ThreadInformation);
  if ( v12[0] )
    ZwClose(v12[0]);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140036dd0  mov     r11, rsp
0x140036dd3  push    rbx
0x140036dd4  push    rsi
0x140036dd5  push    rdi
0x140036dd6  push    r12
0x140036dd8  push    r14
0x140036dda  push    r15
0x140036ddc  sub     rsp, 0E8h
0x140036de3  mov     rax, cs:__security_cookie
0x140036dea  xor     rax, rsp
0x140036ded  mov     [rsp+118h+var_48], rax
0x140036df5  mov     r14, rdx
0x140036df8  xor     r12d, r12d
0x140036dfb  mov     [rsp+118h+Handle], r12
0x140036e00  mov     [rsp+118h+var_C8], r12
0x140036e05  mov     esi, r12d
0x140036e08  mov     [rsp+118h+ThreadInformation], r12
0x140036e0d  mov     edi, r12d
0x140036e10  mov     [rsp+118h+var_B8], r12
0x140036e15  xor     eax, eax
0x140036e17  mov     [r11-78h], rax
0x140036e1b  mov     [r11-70h], eax
0x140036e1f  xorps   xmm0, xmm0
0x140036e22  movups  xmmword ptr [rsp+118h+ObjectAttributes.Length], xmm0
0x140036e27  movups  xmmword ptr [rsp+118h+ObjectAttributes.ObjectName], xmm0
0x140036e2f  movups  xmmword ptr [rsp+118h+ObjectAttributes.SecurityDescriptor], xmm0
0x140036e37  mov     [rsp+118h+LengthNeeded], r12d
0x140036e3c  mov     [rsp+118h+var_E4], r12d
0x140036e41  mov     r15b, r12b
0x140036e44  mov     [rsp+118h+var_E8], r12b
0x140036e49  mov     [rdx], r12
0x140036e4c  lea     rax, [rsp+118h+Handle]
0x140036e51  mov     [rsp+118h+TokenHandle], rax; TokenHandle
0x140036e56  mov     r9d, 200h; HandleAttributes
0x140036e5c  xor     r8d, r8d; OpenAsSelf
0x140036e5f  mov     edx, 20002h; DesiredAccess
0x140036e64  lea     rcx, [r12-2]; ThreadHandle
0x140036e69  call    cs:__imp_ZwOpenThreadTokenEx
0x140036e70  nop     dword ptr [rax+rax+00h]
0x140036e75  mov     ebx, eax
0x140036e77  mov     [rsp+118h+var_E4], eax
0x140036e7b  test    eax, eax
0x140036e7d  js      short loc_140036E89
0x140036e7f  mov     rsi, [rsp+118h+Handle]
0x140036e84  mov     [r14], rsi
0x140036e87  jmp     short loc_140036EBB
0x140036e89  cmp     eax, 0C000007Ch
0x140036e8e  jnz     short loc_140036EBB
0x140036e90  lea     r9, [rsp+118h+var_C8]; TokenHandle
0x140036e95  mov     edx, 20002h; DesiredAccess
0x140036e9a  mov     r8d, 200h; HandleAttributes
0x140036ea0  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x140036ea4  call    cs:__imp_ZwOpenProcessTokenEx
0x140036eab  nop     dword ptr [rax+rax+00h]
0x140036eb0  mov     ebx, eax
0x140036eb2  mov     [rsp+118h+var_E4], eax
0x140036eb6  mov     rsi, [rsp+118h+var_C8]
0x140036ebb  test    ebx, ebx
0x140036ebd  js      loc_1400370F2
0x140036ec3  lea     rax, [rsp+118h+LengthNeeded]
0x140036ec8  mov     [rsp+118h+TokenHandle], rax; LengthNeeded
0x140036ecd  xor     r9d, r9d; Length
0x140036ed0  xor     r8d, r8d; SecurityDescriptor
0x140036ed3  lea     edx, [r9+4]; SecurityInformation
0x140036ed7  mov     rcx, rsi; Handle
0x140036eda  call    cs:__imp_ZwQuerySecurityObject
0x140036ee1  nop     dword ptr [rax+rax+00h]
0x140036ee6  mov     ebx, eax
0x140036ee8  mov     [rsp+118h+var_E4], eax
0x140036eec  cmp     eax, 0C0000023h
0x140036ef1  jnz     loc_1400370F2
0x140036ef7  mov     edx, [rsp+118h+LengthNeeded]; NumberOfBytes
0x140036efb  mov     r8d, 58666C43h; Tag
0x140036f01  mov     r14d, 1
0x140036f07  mov     ecx, r14d; PoolType
0x140036f0a  call    cs:__imp_ExAllocatePoolWithTag
0x140036f11  nop     dword ptr [rax+rax+00h]
0x140036f16  mov     rdi, rax
0x140036f19  mov     [rsp+118h+var_B8], rax
0x140036f1e  test    rax, rax
0x140036f21  jnz     short loc_140036F31
0x140036f23  mov     ebx, 0C000009Ah
0x140036f28  mov     [rsp+118h+var_E4], ebx
0x140036f2c  jmp     loc_1400370F2
0x140036f31  lea     rax, [rsp+118h+LengthNeeded]
0x140036f36  mov     [rsp+118h+TokenHandle], rax; LengthNeeded
0x140036f3b  mov     r9d, [rsp+118h+LengthNeeded]; Length
0x140036f40  mov     r8, rdi; SecurityDescriptor
0x140036f43  mov     edx, 4; SecurityInformation
0x140036f48  mov     rcx, rsi; Handle
0x140036f4b  call    cs:__imp_ZwQuerySecurityObject
0x140036f52  nop     dword ptr [rax+rax+00h]
0x140036f57  mov     ebx, eax
0x140036f59  mov     [rsp+118h+var_E4], eax
0x140036f5d  test    eax, eax
0x140036f5f  js      loc_1400370F2
0x140036f65  mov     [rsp+118h+ObjectAttributes.Length], 30h ; '0'
0x140036f6d  mov     [rsp+118h+ObjectAttributes.RootDirectory], r12
0x140036f72  mov     [rsp+118h+ObjectAttributes.Attributes], 200h
0x140036f7d  mov     [rsp+118h+ObjectAttributes.ObjectName], r12
0x140036f85  mov     [rsp+118h+ObjectAttributes.SecurityDescriptor], rdi
0x140036f8d  mov     [rsp+118h+ObjectAttributes.SecurityQualityOfService], r12
0x140036f95  mov     [rsp+118h+var_78], 0Ch
0x140036fa0  mov     [rsp+118h+var_74], 2
0x140036fab  mov     word ptr [rsp+118h+var_70], r14w
0x140036fb4  lea     rax, [rsp+118h+var_78]
0x140036fbc  mov     [rsp+118h+ObjectAttributes.SecurityQualityOfService], rax
0x140036fc4  lea     rax, [rsp+118h+ThreadInformation]
0x140036fc9  mov     [rsp+118h+NewTokenHandle], rax; NewTokenHandle
0x140036fce  mov     dword ptr [rsp+118h+TokenHandle], 2; TokenType
0x140036fd6  xor     r9d, r9d; EffectiveOnly
0x140036fd9  lea     r8, [rsp+118h+ObjectAttributes]; ObjectAttributes
0x140036fde  lea     edx, [r9+2Ch]; DesiredAccess
0x140036fe2  mov     rcx, rsi; ExistingTokenHandle
0x140036fe5  call    cs:__imp_ZwDuplicateToken
0x140036fec  nop     dword ptr [rax+rax+00h]
0x140036ff1  mov     ebx, eax
0x140036ff3  mov     [rsp+118h+var_E4], eax
0x140036ff7  test    eax, eax
0x140036ff9  js      loc_1400370F2
0x140036fff  mov     r9d, 8; ThreadInformationLength
0x140037005  lea     r8, [rsp+118h+ThreadInformation]; ThreadInformation
0x14003700a  lea     edx, [r9-3]; ThreadInformationClass
0x14003700e  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x140037015  call    cs:__imp_ZwSetInformationThread
0x14003701c  nop     dword ptr [rax+rax+00h]
0x140037021  mov     ebx, eax
0x140037023  mov     [rsp+118h+var_E4], eax
0x140037027  test    eax, eax
0x140037029  js      loc_1400370F2
0x14003702f  mov     r15b, r14b
0x140037032  mov     [rsp+118h+var_E8], r14b
0x140037037  xorps   xmm0, xmm0
0x14003703a  movups  xmmword ptr [rsp+118h+NewState], xmm0
0x140037042  movups  xmmword ptr [rsp+118h+NewState+0Ch], xmm0
0x14003704a  mov     dword ptr [rsp+118h+NewState], r14d
0x140037052  mov     [rsp+118h+var_C0], r12
0x140037057  mov     [rsp+118h+var_B0], r12
0x14003705c  mov     [rsp+118h+var_B0], 8
0x140037065  mov     [rsp+118h+var_C0], 8
0x14003706e  mov     rax, [rsp+118h+var_C0]
0x140037073  mov     qword ptr [rsp+118h+NewState+4], rax
0x14003707b  mov     dword ptr [rsp+118h+NewState+0Ch], 2
0x140037086  mov     [rsp+118h+NewTokenHandle], r12; ReturnLength
0x14003708b  mov     [rsp+118h+TokenHandle], r12; PreviousState
0x140037090  xor     r9d, r9d; BufferLength
0x140037093  lea     r8, [rsp+118h+NewState]; NewState
0x14003709b  xor     edx, edx; DisableAllPrivileges
0x14003709d  mov     rcx, [rsp+118h+ThreadInformation]; TokenHandle
0x1400370a2  call    cs:__imp_ZwAdjustPrivilegesToken
0x1400370a9  nop     dword ptr [rax+rax+00h]
0x1400370ae  mov     ebx, eax
0x1400370b0  mov     [rsp+118h+var_E4], eax
0x1400370b4  mov     eax, 0C0000061h
0x1400370b9  cmp     ebx, 106h
0x1400370bf  cmovz   ebx, eax
0x1400370c2  mov     [rsp+118h+var_E4], ebx
0x1400370c6  test    ebx, ebx
0x1400370c8  js      short loc_1400370F2
0x1400370ca  mov     r9d, 8; ThreadInformationLength
0x1400370d0  lea     r8, [rsp+118h+ThreadInformation]; ThreadInformation
0x1400370d5  lea     edx, [r9-3]; ThreadInformationClass
0x1400370d9  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1400370e0  call    cs:__imp_ZwSetInformationThread
0x1400370e7  nop     dword ptr [rax+rax+00h]
0x1400370ec  mov     ebx, eax
0x1400370ee  mov     [rsp+118h+var_E4], eax
0x1400370f2  test    ebx, ebx
0x1400370f4  jns     short loc_140037133
0x1400370f6  test    r15b, r15b
0x1400370f9  jz      short loc_14003711D
0x1400370fb  mov     r9d, 8; ThreadInformationLength
0x140037101  lea     r8, [rsp+118h+Handle]; ThreadInformation
0x140037106  lea     edx, [r9-3]; ThreadInformationClass
0x14003710a  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x140037111  call    cs:__imp_ZwSetInformationThread
0x140037118  nop     dword ptr [rax+rax+00h]
0x14003711d  mov     rcx, [rsp+118h+Handle]; Handle
0x140037122  test    rcx, rcx
0x140037125  jz      short loc_140037133
0x140037127  call    cs:__imp_ZwClose
0x14003712e  nop     dword ptr [rax+rax+00h]
0x140037133  test    rdi, rdi
0x140037136  jz      short loc_14003714C
0x140037138  mov     edx, 58666C43h; Tag
0x14003713d  mov     rcx, rdi; P
0x140037140  call    cs:__imp_ExFreePoolWithTag
0x140037147  nop     dword ptr [rax+rax+00h]
0x14003714c  mov     rcx, [rsp+118h+ThreadInformation]; Handle
0x140037151  test    rcx, rcx
0x140037154  jz      short loc_140037162
0x140037156  call    cs:__imp_ZwClose
0x14003715d  nop     dword ptr [rax+rax+00h]
0x140037162  mov     rcx, [rsp+118h+var_C8]; Handle
0x140037167  test    rcx, rcx
0x14003716a  jz      short loc_140037178
0x14003716c  call    cs:__imp_ZwClose
0x140037173  nop     dword ptr [rax+rax+00h]
0x140037178  mov     eax, ebx
0x14003717a  mov     rcx, [rsp+118h+var_48]
0x140037182  xor     rcx, rsp; StackCookie
0x140037185  call    __security_check_cookie
0x14003718a  add     rsp, 0E8h
0x140037191  pop     r15
0x140037193  pop     r14
0x140037195  pop     r12
0x140037197  pop     rdi
0x140037198  pop     rsi
0x140037199  pop     rbx
0x14003719a  retn
0x14007d12c  push    rbp
0x14007d12e  sub     rsp, 30h
0x14007d132  mov     rbp, rdx
0x14007d135  cmp     dword ptr [rbp+34h], 0
0x14007d139  jge     short loc_14007D179
0x14007d13b  cmp     byte ptr [rbp+30h], 0
0x14007d13f  jz      short loc_14007D163
0x14007d141  mov     r9d, 8; ThreadInformationLength
0x14007d147  lea     r8, [rbp+40h]; ThreadInformation
0x14007d14b  lea     edx, [r9-3]; ThreadInformationClass
0x14007d14f  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x14007d156  call    cs:__imp_ZwSetInformationThread
0x14007d15d  nop     dword ptr [rax+rax+00h]
0x14007d162  nop
0x14007d163  mov     rcx, [rbp+40h]; Handle
0x14007d167  test    rcx, rcx
0x14007d16a  jz      short loc_14007D179
0x14007d16c  call    cs:__imp_ZwClose
0x14007d173  nop     dword ptr [rax+rax+00h]
0x14007d178  nop
0x14007d179  mov     rcx, [rbp+60h]; P
0x14007d17d  test    rcx, rcx
0x14007d180  jz      short loc_14007D194
0x14007d182  mov     edx, 58666C43h; Tag
0x14007d187  call    cs:__imp_ExFreePoolWithTag
0x14007d18e  nop     dword ptr [rax+rax+00h]
0x14007d193  nop
0x14007d194  mov     rcx, [rbp+48h]; Handle
0x14007d198  test    rcx, rcx
0x14007d19b  jz      short loc_14007D1AA
0x14007d19d  call    cs:__imp_ZwClose
0x14007d1a4  nop     dword ptr [rax+rax+00h]
0x14007d1a9  nop
0x14007d1aa  mov     rcx, [rbp+50h]; Handle
0x14007d1ae  test    rcx, rcx
0x14007d1b1  jz      short loc_14007D1C0
0x14007d1b3  call    cs:__imp_ZwClose
0x14007d1ba  nop     dword ptr [rax+rax+00h]
0x14007d1bf  nop
0x14007d1c0  add     rsp, 30h
0x14007d1c4  pop     rbp
0x14007d1c5  retn
```
