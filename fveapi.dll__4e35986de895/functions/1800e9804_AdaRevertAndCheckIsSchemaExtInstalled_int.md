# AdaRevertAndCheckIsSchemaExtInstalled(int *)

- ea: `0x1800e9804`
- end: `0x1800e9b44`
- name: `?AdaRevertAndCheckIsSchemaExtInstalled@@YAJPEAH@Z`
- size: `832`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800b1450`
- `0x1800cbe60`

## callees

- `0x180008d70`
- `0x1800090c0`
- `0x180019128`
- `0x1800e88d4`
- `0x1800e9804`
- `0x1800ea0bc`
- `0x1800ea100`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e9922`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e9984`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e9922`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e9984`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e98f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800e98f7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e9912`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800e9912`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800e9abb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800e9abb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e9adb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e9adb`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800e9974`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800e9974`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800e9afe`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1800e9afe`
- `RPCRT4!RpcImpersonateClient` at `0x1800e9a7e`
- `RPCRT4!RpcImpersonateClient` at `0x1800e9a7e`
- `RPCRT4!RpcRevertToSelf` at `0x1800e99c0`
- `RPCRT4!RpcRevertToSelf` at `0x1800e99c0`

## pseudocode

```c
__int64 __fastcall AdaRevertAndCheckIsSchemaExtInstalled(int *a1)
{
  unsigned int v2; // eax
  signed int v3; // ebx
  PVOID *v4; // rcx
  bool v5; // si
  char v6; // di
  BOOL IsComImpersonating; // eax
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  __int64 v10; // rdx
  signed int v11; // eax
  RPC_STATUS v12; // eax
  unsigned int IsSchemaExtInstalled; // eax
  unsigned int v14; // eax
  bool v16; // [rsp+58h] [rbp+10h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp+18h] BYREF

  v16 = 0;
  TokenHandle = (void *)-1LL;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids);
  v2 = AdapInitializeCOM(&v16);
  v3 = v2;
  if ( v2 )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids, v2);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v3 < 0 )
      goto LABEL_54;
  }
  v5 = 0;
  v6 = 0;
  if ( !NtCurrentTeb()->IsImpersonating )
  {
LABEL_36:
    IsSchemaExtInstalled = AdaIsSchemaExtInstalled(a1);
    v3 = IsSchemaExtInstalled;
    if ( IsSchemaExtInstalled )
    {
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          36,
          WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids,
          IsSchemaExtInstalled);
        v4 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v3 < 0 )
        goto LABEL_46;
    }
    else
    {
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 8) != 0 )
    {
      WPP_SF_d(v4[2], 37, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids, (unsigned int)*a1);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
LABEL_46:
    if ( !v6 )
      goto LABEL_54;
    if ( !v5 )
    {
      v14 = RpcImpersonateClient(0);
      if ( v14 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids, v14);
      }
    }
    SetThreadToken(0, TokenHandle);
    goto LABEL_53;
  }
  IsComImpersonating = AdapIsComImpersonating();
  v3 = IsComImpersonating;
  if ( IsComImpersonating )
  {
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids,
        IsComImpersonating);
      v4 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v3 < 0 )
      goto LABEL_54;
  }
  v5 = v3 == 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 4u, 0, &TokenHandle) )
  {
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    v4 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    {
      v10 = 33;
LABEL_21:
      WPP_SF_d(v4[2], v10, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids, (unsigned int)v3);
LABEL_53:
      v4 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_54;
    }
    goto LABEL_54;
  }
  if ( v3 )
  {
    v12 = RpcRevertToSelf();
    v3 = v12;
    if ( v12 )
    {
      if ( v12 > 0 )
        v3 = (unsigned __int16)v12 | 0x80070000;
      v4 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      {
        v10 = 35;
        goto LABEL_21;
      }
      goto LABEL_54;
    }
    goto LABEL_35;
  }
  if ( RevertToSelf() )
  {
LABEL_35:
    v6 = 1;
    goto LABEL_36;
  }
  v11 = GetLastError();
  v3 = v11;
  if ( v11 > 0 )
    v3 = (unsigned __int16)v11 | 0x80070000;
  v4 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
  {
    v10 = 34;
    goto LABEL_21;
  }
LABEL_54:
  if ( TokenHandle != (void *)-1LL )
  {
    CloseHandle(TokenHandle);
    v4 = (PVOID *)WPP_GLOBAL_Control;
    TokenHandle = (void *)-1LL;
  }
  if ( v16 )
  {
    CoUninitialize();
    v4 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v4 != &WPP_GLOBAL_Control && (*((_BYTE *)v4 + 28) & 0x20) != 0 )
    WPP_SF_d(v4[2], 39, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids, (unsigned int)v3);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800e9804  mov     [rsp+arg_0], rbx
0x1800e9809  push    rbp
0x1800e980a  push    rsi
0x1800e980b  push    rdi
0x1800e980c  push    r12
0x1800e980e  push    r14
0x1800e9810  sub     rsp, 20h
0x1800e9814  mov     r14, rcx
0x1800e9817  mov     [rsp+48h+arg_8], 0
0x1800e981c  mov     [rsp+48h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x1800e9825  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e982c  lea     rbp, WPP_GLOBAL_Control
0x1800e9833  lea     r12, WPP_70dbe177a73a3b62ce3dc20ba8f7c92c_Traceguids
0x1800e983a  cmp     rcx, rbp
0x1800e983d  jz      short loc_1800E9856
0x1800e983f  test    byte ptr [rcx+1Ch], 20h
0x1800e9843  jz      short loc_1800E9856
0x1800e9845  mov     rcx, [rcx+10h]
0x1800e9849  mov     edx, 1Eh
0x1800e984e  mov     r8, r12
0x1800e9851  call    WPP_SF_
0x1800e9856  lea     rcx, [rsp+48h+arg_8]; bool *
0x1800e985b  call    ?AdapInitializeCOM@@YAJPEA_N@Z; AdapInitializeCOM(bool *)
0x1800e9860  mov     ebx, eax
0x1800e9862  test    eax, eax
0x1800e9864  jz      short loc_1800E989B
0x1800e9866  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e986d  cmp     rcx, rbp
0x1800e9870  jz      short loc_1800E9893
0x1800e9872  test    byte ptr [rcx+1Ch], 40h
0x1800e9876  jz      short loc_1800E9893
0x1800e9878  mov     rcx, [rcx+10h]
0x1800e987c  mov     edx, 1Fh
0x1800e9881  mov     r9d, eax
0x1800e9884  mov     r8, r12
0x1800e9887  call    WPP_SF_d
0x1800e988c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9893  test    ebx, ebx
0x1800e9895  js      loc_1800E9ACE
0x1800e989b  mov     eax, gs:179Ch
0x1800e98a3  xor     sil, sil
0x1800e98a6  xor     dil, dil
0x1800e98a9  test    eax, eax
0x1800e98ab  jz      loc_1800E9A04
0x1800e98b1  call    ?AdapIsComImpersonating@@YAJXZ; AdapIsComImpersonating(void)
0x1800e98b6  mov     ebx, eax
0x1800e98b8  test    eax, eax
0x1800e98ba  jz      short loc_1800E98F1
0x1800e98bc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e98c3  cmp     rcx, rbp
0x1800e98c6  jz      short loc_1800E98E9
0x1800e98c8  test    byte ptr [rcx+1Ch], 40h
0x1800e98cc  jz      short loc_1800E98E9
0x1800e98ce  mov     rcx, [rcx+10h]
0x1800e98d2  mov     edx, 20h ; ' '
0x1800e98d7  mov     r9d, eax
0x1800e98da  mov     r8, r12
0x1800e98dd  call    WPP_SF_d
0x1800e98e2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e98e9  test    ebx, ebx
0x1800e98eb  js      loc_1800E9ACE
0x1800e98f1  test    ebx, ebx
0x1800e98f3  setz    sil
0x1800e98f7  call    cs:__imp_GetCurrentThread
0x1800e98fe  nop     dword ptr [rax+rax+00h]
0x1800e9903  xor     r8d, r8d; OpenAsSelf
0x1800e9906  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x1800e990b  mov     rcx, rax; ThreadHandle
0x1800e990e  lea     edx, [r8+4]; DesiredAccess
0x1800e9912  call    cs:__imp_OpenThreadToken
0x1800e9919  nop     dword ptr [rax+rax+00h]
0x1800e991e  test    eax, eax
0x1800e9920  jnz     short loc_1800E9970
0x1800e9922  call    cs:__imp_GetLastError
0x1800e9929  nop     dword ptr [rax+rax+00h]
0x1800e992e  mov     ebx, eax
0x1800e9930  test    eax, eax
0x1800e9932  jle     short loc_1800E993D
0x1800e9934  movzx   ebx, ax
0x1800e9937  or      ebx, 80070000h
0x1800e993d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9944  cmp     rcx, rbp
0x1800e9947  jz      loc_1800E9ACE
0x1800e994d  test    byte ptr [rcx+1Ch], 40h
0x1800e9951  jz      loc_1800E9ACE
0x1800e9957  mov     edx, 21h ; '!'
0x1800e995c  mov     rcx, [rcx+10h]
0x1800e9960  mov     r9d, ebx
0x1800e9963  mov     r8, r12
0x1800e9966  call    WPP_SF_d
0x1800e996b  jmp     loc_1800E9AC7
0x1800e9970  test    ebx, ebx
0x1800e9972  jnz     short loc_1800E99C0
0x1800e9974  call    cs:__imp_RevertToSelf
0x1800e997b  nop     dword ptr [rax+rax+00h]
0x1800e9980  test    eax, eax
0x1800e9982  jnz     short loc_1800E9A01
0x1800e9984  call    cs:__imp_GetLastError
0x1800e998b  nop     dword ptr [rax+rax+00h]
0x1800e9990  mov     ebx, eax
0x1800e9992  test    eax, eax
0x1800e9994  jle     short loc_1800E999F
0x1800e9996  movzx   ebx, ax
0x1800e9999  or      ebx, 80070000h
0x1800e999f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e99a6  cmp     rcx, rbp
0x1800e99a9  jz      loc_1800E9ACE
0x1800e99af  test    byte ptr [rcx+1Ch], 40h
0x1800e99b3  jz      loc_1800E9ACE
0x1800e99b9  mov     edx, 22h ; '"'
0x1800e99be  jmp     short loc_1800E995C
0x1800e99c0  call    cs:__imp_RpcRevertToSelf
0x1800e99c7  nop     dword ptr [rax+rax+00h]
0x1800e99cc  mov     ebx, eax
0x1800e99ce  test    eax, eax
0x1800e99d0  jz      short loc_1800E9A01
0x1800e99d2  jle     short loc_1800E99DD
0x1800e99d4  movzx   ebx, ax
0x1800e99d7  or      ebx, 80070000h
0x1800e99dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e99e4  cmp     rcx, rbp
0x1800e99e7  jz      loc_1800E9ACE
0x1800e99ed  test    byte ptr [rcx+1Ch], 40h
0x1800e99f1  jz      loc_1800E9ACE
0x1800e99f7  mov     edx, 23h ; '#'
0x1800e99fc  jmp     loc_1800E995C
0x1800e9a01  mov     dil, 1
0x1800e9a04  mov     rcx, r14; int *
0x1800e9a07  call    ?AdaIsSchemaExtInstalled@@YAJPEAH@Z; AdaIsSchemaExtInstalled(int *)
0x1800e9a0c  mov     ebx, eax
0x1800e9a0e  test    eax, eax
0x1800e9a10  jz      short loc_1800E9A45
0x1800e9a12  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9a19  cmp     rcx, rbp
0x1800e9a1c  jz      short loc_1800E9A3F
0x1800e9a1e  test    byte ptr [rcx+1Ch], 40h
0x1800e9a22  jz      short loc_1800E9A3F
0x1800e9a24  mov     rcx, [rcx+10h]
0x1800e9a28  mov     edx, 24h ; '$'
0x1800e9a2d  mov     r9d, eax
0x1800e9a30  mov     r8, r12
0x1800e9a33  call    WPP_SF_d
0x1800e9a38  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9a3f  test    ebx, ebx
0x1800e9a41  js      short loc_1800E9A72
0x1800e9a43  jmp     short loc_1800E9A4C
0x1800e9a45  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9a4c  cmp     rcx, rbp
0x1800e9a4f  jz      short loc_1800E9A72
0x1800e9a51  test    byte ptr [rcx+1Ch], 8
0x1800e9a55  jz      short loc_1800E9A72
0x1800e9a57  mov     r9d, [r14]
0x1800e9a5a  mov     edx, 25h ; '%'
0x1800e9a5f  mov     rcx, [rcx+10h]
0x1800e9a63  mov     r8, r12
0x1800e9a66  call    WPP_SF_d
0x1800e9a6b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9a72  test    dil, dil
0x1800e9a75  jz      short loc_1800E9ACE
0x1800e9a77  test    sil, sil
0x1800e9a7a  jnz     short loc_1800E9AB4
0x1800e9a7c  xor     ecx, ecx; BindingHandle
0x1800e9a7e  call    cs:__imp_RpcImpersonateClient
0x1800e9a85  nop     dword ptr [rax+rax+00h]
0x1800e9a8a  test    eax, eax
0x1800e9a8c  jz      short loc_1800E9AB4
0x1800e9a8e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9a95  cmp     rcx, rbp
0x1800e9a98  jz      short loc_1800E9AB4
0x1800e9a9a  test    byte ptr [rcx+1Ch], 2
0x1800e9a9e  jz      short loc_1800E9AB4
0x1800e9aa0  mov     rcx, [rcx+10h]
0x1800e9aa4  mov     edx, 26h ; '&'
0x1800e9aa9  mov     r9d, eax
0x1800e9aac  mov     r8, r12
0x1800e9aaf  call    WPP_SF_D
0x1800e9ab4  mov     rdx, [rsp+48h+TokenHandle]; Token
0x1800e9ab9  xor     ecx, ecx; Thread
0x1800e9abb  call    cs:__imp_SetThreadToken
0x1800e9ac2  nop     dword ptr [rax+rax+00h]
0x1800e9ac7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9ace  cmp     [rsp+48h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x1800e9ad4  jz      short loc_1800E9AF7
0x1800e9ad6  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x1800e9adb  call    cs:__imp_CloseHandle
0x1800e9ae2  nop     dword ptr [rax+rax+00h]
0x1800e9ae7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9aee  mov     [rsp+48h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x1800e9af7  cmp     [rsp+48h+arg_8], 0
0x1800e9afc  jz      short loc_1800E9B11
0x1800e9afe  call    cs:__imp_CoUninitialize
0x1800e9b05  nop     dword ptr [rax+rax+00h]
0x1800e9b0a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9b11  cmp     rcx, rbp
0x1800e9b14  jz      short loc_1800E9B30
0x1800e9b16  test    byte ptr [rcx+1Ch], 20h
0x1800e9b1a  jz      short loc_1800E9B30
0x1800e9b1c  mov     rcx, [rcx+10h]
0x1800e9b20  mov     edx, 27h ; '''
0x1800e9b25  mov     r9d, ebx
0x1800e9b28  mov     r8, r12
0x1800e9b2b  call    WPP_SF_d
0x1800e9b30  mov     eax, ebx
0x1800e9b32  mov     rbx, [rsp+48h+arg_0]
0x1800e9b37  add     rsp, 20h
0x1800e9b3b  pop     r14
0x1800e9b3d  pop     r12
0x1800e9b3f  pop     rdi
0x1800e9b40  pop     rsi
0x1800e9b41  pop     rbp
0x1800e9b42  retn
```
