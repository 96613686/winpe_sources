# CredrBackupCredentials

- ea: `0x1800f4070`
- end: `0x1800f424e`
- name: `CredrBackupCredentials`
- size: `478`
- prototype: `__int64 __fastcall(__int64, void *, unsigned int, unsigned __int16 *, unsigned __int8 *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000c300`
- `0x180044860`
- `0x1800c13cc`
- `0x1800f3bb4`
- `0x1800f3d60`
- `0x1800f3f3c`
- `0x1800f4070`

## import_xrefs

- `ntdll!NtClose` at `0x1800f411a`
- `ntdll!NtClose` at `0x1800f411a`
- `ntdll!NtSetInformationThread` at `0x1800f41aa`
- `ntdll!NtSetInformationThread` at `0x1800f423d`
- `ntdll!NtSetInformationThread` at `0x1800f41aa`
- `ntdll!NtSetInformationThread` at `0x1800f423d`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x1800f40da`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x1800f40da`
- `RPCRT4!RpcRevertToSelf` at `0x1800f4105`
- `RPCRT4!RpcRevertToSelf` at `0x1800f418e`
- `RPCRT4!RpcRevertToSelf` at `0x1800f4105`
- `RPCRT4!RpcRevertToSelf` at `0x1800f418e`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800f40c2`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800f40e8`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800f40c2`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800f40e8`
- `RPCRT4!RpcImpersonateClient` at `0x1800f40b4`
- `RPCRT4!RpcImpersonateClient` at `0x1800f40b4`

## pseudocode

```c
__int64 __fastcall CredrBackupCredentials(
        __int64 a1,
        void *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        unsigned __int8 *a5,
        unsigned int a6,
        unsigned int a7)
{
  RPC_STATUS v11; // eax
  int LogonId; // ebx
  RPC_STATUS IsClientLocal; // eax
  int v15; // edi
  int v16; // eax
  unsigned __int8 *v17; // rsi
  char *v18; // rdx
  unsigned __int8 *v19; // rax
  int v20; // edi
  unsigned int v21; // [rsp+30h] [rbp-28h] BYREF
  unsigned int ClientLocalFlag; // [rsp+34h] [rbp-24h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-20h] BYREF
  unsigned __int8 *ThreadInformation; // [rsp+40h] [rbp-18h] BYREF
  struct _LUID v25; // [rsp+48h] [rbp-10h] BYREF

  v25 = 0;
  Handle = 0;
  ClientLocalFlag = 0;
  ThreadInformation = 0;
  v21 = 0;
  v11 = RpcImpersonateClient(0);
  LogonId = I_RpcMapWin32Status(v11);
  if ( LogonId < 0 )
    goto LABEL_6;
  IsClientLocal = I_RpcBindingIsClientLocal(0, &ClientLocalFlag);
  LogonId = I_RpcMapWin32Status(IsClientLocal);
  if ( LogonId < 0 )
  {
LABEL_5:
    RpcRevertToSelf();
    goto LABEL_6;
  }
  if ( !ClientLocalFlag || !(unsigned int)CredpIsRpcClientTrusted() )
  {
    LogonId = -1073741790;
    goto LABEL_5;
  }
  LogonId = CredpDuplicateImpersonationTokenFromCallersHandle(a3, a2, &Handle);
  if ( LogonId < 0 )
    goto LABEL_5;
  if ( a1 )
  {
    LogonId = -1073741534;
    goto LABEL_5;
  }
  v15 = 1;
  v16 = CredpDecodeSecret(0, a5, a6, &ThreadInformation, &v21);
  v17 = ThreadInformation;
  LogonId = v16;
  if ( v16 >= 0 )
  {
    RpcRevertToSelf();
    v15 = 0;
    LogonId = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &Handle, 8u);
    if ( LogonId >= 0 )
    {
      v15 = 2;
      LogonId = CrediGetLogonId(1, &v25);
      if ( LogonId >= 0 )
        LogonId = CrediBackupCredentials(&v25, a4, v17, v21, a7);
    }
  }
  if ( v17 )
  {
    v18 = (char *)v21;
    v19 = v17;
    if ( v21 )
    {
      do
      {
        *v19++ = 0;
        --v18;
      }
      while ( v18 );
    }
    LsapSubProv_FreeRoutine((struct _RTL_BALANCED_NODE *)v17, v18);
  }
  v20 = v15 - 1;
  if ( !v20 )
    goto LABEL_5;
  if ( v20 == 1 )
  {
    ThreadInformation = 0;
    NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
  }
LABEL_6:
  if ( Handle )
    NtClose(Handle);
  return (unsigned int)LogonId;
}

```

## disassembly

```asm
0x1800f4070  push    rbp
0x1800f4072  push    rbx
0x1800f4073  push    rsi
0x1800f4074  push    rdi
0x1800f4075  push    r14
0x1800f4077  push    r15
0x1800f4079  mov     rbp, rsp
0x1800f407c  sub     rsp, 58h
0x1800f4080  mov     rdi, rcx
0x1800f4083  mov     qword ptr [rbp+var_10.LowPart], 0
0x1800f408b  xor     ecx, ecx; BindingHandle
0x1800f408d  mov     [rbp+Handle], 0
0x1800f4095  mov     r15, r9
0x1800f4098  mov     [rbp+ClientLocalFlag], 0
0x1800f409f  mov     esi, r8d
0x1800f40a2  mov     [rbp+ThreadInformation], 0
0x1800f40aa  mov     r14, rdx
0x1800f40ad  mov     [rbp+var_28], 0
0x1800f40b4  call    cs:__imp_RpcImpersonateClient
0x1800f40bb  nop     dword ptr [rax+rax+00h]
0x1800f40c0  mov     ecx, eax; Status
0x1800f40c2  call    cs:__imp_I_RpcMapWin32Status
0x1800f40c9  nop     dword ptr [rax+rax+00h]
0x1800f40ce  mov     ebx, eax
0x1800f40d0  test    eax, eax
0x1800f40d2  js      short loc_1800F4111
0x1800f40d4  lea     rdx, [rbp+ClientLocalFlag]; ClientLocalFlag
0x1800f40d8  xor     ecx, ecx; BindingHandle
0x1800f40da  call    cs:__imp_I_RpcBindingIsClientLocal
0x1800f40e1  nop     dword ptr [rax+rax+00h]
0x1800f40e6  mov     ecx, eax; Status
0x1800f40e8  call    cs:__imp_I_RpcMapWin32Status
0x1800f40ef  nop     dword ptr [rax+rax+00h]
0x1800f40f4  mov     ebx, eax
0x1800f40f6  test    eax, eax
0x1800f40f8  js      short loc_1800F4105
0x1800f40fa  cmp     [rbp+ClientLocalFlag], 0
0x1800f40fe  jnz     short loc_1800F4136
0x1800f4100  mov     ebx, 0C0000022h
0x1800f4105  call    cs:__imp_RpcRevertToSelf
0x1800f410c  nop     dword ptr [rax+rax+00h]
0x1800f4111  mov     rcx, [rbp+Handle]; Handle
0x1800f4115  test    rcx, rcx
0x1800f4118  jz      short loc_1800F4126
0x1800f411a  call    cs:__imp_NtClose
0x1800f4121  nop     dword ptr [rax+rax+00h]
0x1800f4126  mov     eax, ebx
0x1800f4128  add     rsp, 58h
0x1800f412c  pop     r15
0x1800f412e  pop     r14
0x1800f4130  pop     rdi
0x1800f4131  pop     rsi
0x1800f4132  pop     rbx
0x1800f4133  pop     rbp
0x1800f4134  retn
0x1800f4136  call    ?CredpIsRpcClientTrusted@@YAHXZ; CredpIsRpcClientTrusted(void)
0x1800f413b  test    eax, eax
0x1800f413d  jz      short loc_1800F4100
0x1800f413f  lea     r8, [rbp+Handle]; void **
0x1800f4143  mov     rdx, r14; void *
0x1800f4146  mov     ecx, esi; unsigned int
0x1800f4148  call    ?CredpDuplicateImpersonationTokenFromCallersHandle@@YAJKPEAXPEAPEAX@Z; CredpDuplicateImpersonationTokenFromCallersHandle(ulong,void *,void * *)
0x1800f414d  mov     ebx, eax
0x1800f414f  test    eax, eax
0x1800f4151  js      short loc_1800F4105
0x1800f4153  test    rdi, rdi
0x1800f4156  jz      short loc_1800F415F
0x1800f4158  mov     ebx, 0C0000122h
0x1800f415d  jmp     short loc_1800F4105
0x1800f415f  mov     r8d, [rbp+arg_28]; unsigned int
0x1800f4163  lea     rax, [rbp+var_28]
0x1800f4167  mov     rdx, [rbp+arg_20]; unsigned __int8 *
0x1800f416b  lea     r9, [rbp+ThreadInformation]; unsigned __int8 **
0x1800f416f  xor     ecx, ecx; int
0x1800f4171  mov     [rsp+58h+var_38], rax; unsigned int *
0x1800f4176  mov     edi, 1
0x1800f417b  call    ?CredpDecodeSecret@@YAJHPEAEKPEAPEAEPEAK@Z; CredpDecodeSecret(int,uchar *,ulong,uchar * *,ulong *)
0x1800f4180  mov     rsi, [rbp+ThreadInformation]
0x1800f4184  mov     ebx, eax
0x1800f4186  lea     r14d, [rdi+7]
0x1800f418a  test    eax, eax
0x1800f418c  js      short loc_1800F41EE
0x1800f418e  call    cs:__imp_RpcRevertToSelf
0x1800f4195  nop     dword ptr [rax+rax+00h]
0x1800f419a  xor     edi, edi
0x1800f419c  lea     r8, [rbp+Handle]; ThreadInformation
0x1800f41a0  mov     r9d, r14d; ThreadInformationLength
0x1800f41a3  lea     edx, [rdi+5]; ThreadInformationClass
0x1800f41a6  lea     rcx, [rdi-2]; ThreadHandle
0x1800f41aa  call    cs:__imp_NtSetInformationThread
0x1800f41b1  nop     dword ptr [rax+rax+00h]
0x1800f41b6  mov     ebx, eax
0x1800f41b8  test    eax, eax
0x1800f41ba  js      short loc_1800F41EE
0x1800f41bc  lea     edi, [r14-6]
0x1800f41c0  lea     ecx, [rdi-1]; int
0x1800f41c3  lea     rdx, [rbp+var_10]; struct _LUID *
0x1800f41c7  call    ?CrediGetLogonId@@YAJHPEAU_LUID@@@Z; CrediGetLogonId(int,_LUID *)
0x1800f41cc  mov     ebx, eax
0x1800f41ce  test    eax, eax
0x1800f41d0  js      short loc_1800F41EE
0x1800f41d2  mov     eax, [rbp+arg_30]
0x1800f41d5  lea     rcx, [rbp+var_10]; struct _LUID *
0x1800f41d9  mov     r9d, [rbp+var_28]; unsigned int
0x1800f41dd  mov     r8, rsi; unsigned __int8 *
0x1800f41e0  mov     rdx, r15; unsigned __int16 *
0x1800f41e3  mov     dword ptr [rsp+58h+var_38], eax; unsigned int
0x1800f41e7  call    ?CrediBackupCredentials@@YAJPEAU_LUID@@PEAGPEAEKK@Z; CrediBackupCredentials(_LUID *,ushort *,uchar *,ulong,ulong)
0x1800f41ec  mov     ebx, eax
0x1800f41ee  test    rsi, rsi
0x1800f41f1  jz      short loc_1800F4212
0x1800f41f3  mov     edx, [rbp+var_28]
0x1800f41f6  mov     rax, rsi
0x1800f41f9  test    rdx, rdx
0x1800f41fc  jz      short loc_1800F420A
0x1800f41fe  mov     byte ptr [rax], 0
0x1800f4201  inc     rax
0x1800f4204  sub     rdx, 1; void *
0x1800f4208  jnz     short loc_1800F41FE
0x1800f420a  mov     rcx, rsi; struct _RTL_BALANCED_NODE *
0x1800f420d  call    ?LsapSubProv_FreeRoutine@@YAXPEAU_RTL_BALANCED_NODE@@PEAX@Z; LsapSubProv_FreeRoutine(_RTL_BALANCED_NODE *,void *)
0x1800f4212  sub     edi, 1
0x1800f4215  jz      loc_1800F4105
0x1800f421b  cmp     edi, 1
0x1800f421e  jnz     loc_1800F4111
0x1800f4224  mov     r9d, r14d; ThreadInformationLength
0x1800f4227  mov     [rbp+ThreadInformation], 0
0x1800f422f  lea     r8, [rbp+ThreadInformation]; ThreadInformation
0x1800f4233  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800f423a  lea     edx, [rdi+4]; ThreadInformationClass
0x1800f423d  call    cs:__imp_NtSetInformationThread
0x1800f4244  nop     dword ptr [rax+rax+00h]
0x1800f4249  jmp     loc_1800F4111
```
