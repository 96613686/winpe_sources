# sub_18024DAFC

- ea: `0x18024dafc`
- end: `0x18024dfe3`
- name: `sub_18024DAFC`
- size: `1255`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1801be640`

## callees

- `0x18013f000`
- `0x1801655e0`
- `0x1801655f0`
- `0x1801a166c`
- `0x1801a5560`
- `0x1801a569c`
- `0x1801c8638`
- `0x18024d864`
- `0x18024dafc`
- `0x18024e2b8`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x18024de91`
- `ntdll!RtlNtStatusToDosError` at `0x18024dee3`
- `ntdll!RtlNtStatusToDosError` at `0x18024de91`
- `ntdll!RtlNtStatusToDosError` at `0x18024dee3`
- `KERNEL32!CloseHandle` at `0x18024df63`
- `KERNEL32!CloseHandle` at `0x18024df63`
- `KERNEL32!GetCurrentProcess` at `0x18024db5a`
- `KERNEL32!GetCurrentProcess` at `0x18024db5a`
- `KERNEL32!GetLastError` at `0x18024db74`
- `KERNEL32!GetLastError` at `0x18024dc43`
- `KERNEL32!GetLastError` at `0x18024dcf2`
- `KERNEL32!GetLastError` at `0x18024db74`
- `KERNEL32!GetLastError` at `0x18024dc43`
- `KERNEL32!GetLastError` at `0x18024dcf2`
- `ADVAPI32!LsaOpenPolicy` at `0x18024ddee`
- `ADVAPI32!LsaOpenPolicy` at `0x18024ddee`
- `ADVAPI32!LsaAddAccountRights` at `0x18024de44`
- `ADVAPI32!LsaAddAccountRights` at `0x18024de44`
- `ADVAPI32!LsaClose` at `0x18024df73`
- `ADVAPI32!LsaClose` at `0x18024df73`
- `ADVAPI32!GetTokenInformation` at `0x18024dbd0`
- `ADVAPI32!GetTokenInformation` at `0x18024dc39`
- `ADVAPI32!GetTokenInformation` at `0x18024dc8f`
- `ADVAPI32!GetTokenInformation` at `0x18024dce8`
- `ADVAPI32!GetTokenInformation` at `0x18024dbd0`
- `ADVAPI32!GetTokenInformation` at `0x18024dc39`
- `ADVAPI32!GetTokenInformation` at `0x18024dc8f`
- `ADVAPI32!GetTokenInformation` at `0x18024dce8`
- `ADVAPI32!OpenProcessToken` at `0x18024db6a`
- `ADVAPI32!OpenProcessToken` at `0x18024db6a`

## pseudocode

```c
__int64 sub_18024DAFC()
{
  char v0; // r12
  char v1; // si
  char v2; // r14
  _DWORD *v3; // r15
  void **v4; // r13
  HANDLE CurrentProcess; // rax
  DWORD LastError; // eax
  ULONG v7; // ebx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  void **v10; // rax
  _QWORD *v11; // rcx
  __int64 v12; // r9
  __int64 v13; // rdx
  _DWORD *v14; // rax
  _BYTE *v15; // rcx
  __int64 v16; // r12
  __int64 v17; // rsi
  ULONG v18; // eax
  unsigned __int64 v19; // r8
  unsigned __int64 v20; // rdx
  NTSTATUS v21; // eax
  WCHAR *v22; // rcx
  __int64 v23; // rax
  void *v24; // rdx
  NTSTATUS v25; // eax
  char v26; // r14
  char v27; // al
  int v28; // edx
  int v29; // r8d
  char v31; // [rsp+38h] [rbp-39h]
  char v32; // [rsp+39h] [rbp-38h]
  char v33; // [rsp+3Ah] [rbp-37h]
  DWORD TokenInformationLength; // [rsp+3Ch] [rbp-35h] BYREF
  DWORD ReturnLength; // [rsp+40h] [rbp-31h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-29h] BYREF
  PVOID PolicyHandle; // [rsp+50h] [rbp-21h] BYREF
  struct _LSA_UNICODE_STRING UserRights; // [rsp+58h] [rbp-19h] BYREF
  __int64 v39; // [rsp+68h] [rbp-9h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-1h] BYREF

  TokenHandle = (void *)-1LL;
  v0 = 1;
  PolicyHandle = 0;
  v32 = 1;
  v1 = 0;
  v31 = 0;
  v2 = 0;
  v33 = 0;
  v3 = 0;
  ReturnLength = 0;
  v4 = 0;
  TokenInformationLength = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
  {
    LastError = GetLastError();
    v7 = LastError;
    v8 = hDevice;
    if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
    {
      v9 = 11;
LABEL_5:
      sub_1801A166C(v8[2], v9, &stru_180C37738, LastError);
      goto LABEL_58;
    }
    goto LABEL_58;
  }
  GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  v10 = (void **)sub_1801655F0(TokenInformationLength);
  v4 = v10;
  if ( !v10 )
  {
    v11 = hDevice;
    if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 1) == 0 )
      goto LABEL_11;
    v12 = TokenInformationLength;
    v13 = 12;
    goto LABEL_10;
  }
  if ( GetTokenInformation(TokenHandle, TokenUser, v10, TokenInformationLength, &TokenInformationLength) )
  {
    GetTokenInformation(TokenHandle, TokenPrivileges, 0, 0, &ReturnLength);
    v14 = (_DWORD *)sub_1801655F0(ReturnLength);
    v3 = v14;
    if ( v14 )
    {
      if ( GetTokenInformation(TokenHandle, TokenPrivileges, v14, ReturnLength, &ReturnLength) )
      {
        v16 = 0;
        v17 = 0;
        while ( 1 )
        {
          v39 = 0;
          v18 = sub_18024D864(v15, off_180C37710[v17], &v39);
          v7 = v18;
          if ( v18 )
            break;
          v19 = (unsigned int)*v3;
          v20 = 0;
          if ( *v3 )
          {
            v15 = v3 + 3;
            while ( *((_QWORD *)v15 - 1) != v39 || (*v15 & 4) != 0 )
            {
              ++v20;
              v15 += 12;
              if ( v20 >= v19 )
                goto LABEL_31;
            }
          }
          else
          {
LABEL_31:
            if ( v20 == v19 )
            {
              UserRights = 0;
              if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 8) != 0 )
                sub_1801C8638(*((_QWORD *)hDevice + 2), 17, &stru_180C37738, off_180C37710[v17]);
              if ( !v2 )
              {
                memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
                v21 = LsaOpenPolicy(0, &ObjectAttributes, 0xF0FFFu, &PolicyHandle);
                if ( v21 )
                {
                  v7 = RtlNtStatusToDosError(v21);
                  if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
                    sub_1801A5560(*((_QWORD *)hDevice + 2), 18, &stru_180C37738);
                  goto LABEL_57;
                }
                v33 = 1;
              }
              v22 = off_180C37710[v17];
              v23 = -1;
              UserRights.Buffer = v22;
              do
                ++v23;
              while ( v22[v23] );
              v24 = *v4;
              UserRights.Length = 2 * v23;
              UserRights.MaximumLength = 2 * v23 + 2;
              v25 = LsaAddAccountRights(PolicyHandle, v24, &UserRights, 1u);
              v26 = v25;
              if ( v25 )
              {
                v32 = 0;
                v27 = RtlNtStatusToDosError(v25);
                v15 = hDevice;
                if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
                  sub_18024E2B8(*((_QWORD *)hDevice + 2), v28, v29, (unsigned int)off_180C37710[v17], v26, v27);
                v7 = 0;
              }
              else
              {
                v31 = 1;
                v15 = hDevice;
                if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 8) != 0 )
                  sub_1801C8638(*((_QWORD *)hDevice + 2), 19, &stru_180C37738, off_180C37710[v17]);
              }
              v2 = v33;
            }
          }
          ++v16;
          if ( (unsigned __int64)++v17 >= 5 )
            goto LABEL_57;
        }
        if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
          sub_1801A569C(
            *((_QWORD *)hDevice + 2),
            16,
            (unsigned int)&stru_180C37738,
            (unsigned int)off_180C37710[v16],
            v18);
LABEL_57:
        v1 = v31;
        v0 = v32;
      }
      else
      {
        LastError = GetLastError();
        v7 = LastError;
        v8 = hDevice;
        if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
        {
          v9 = 15;
          goto LABEL_5;
        }
      }
      goto LABEL_58;
    }
    v11 = hDevice;
    if ( hDevice == &hDevice || (*((_BYTE *)hDevice + 28) & 1) == 0 )
    {
LABEL_11:
      v7 = 8;
      goto LABEL_58;
    }
    v12 = ReturnLength;
    v13 = 14;
LABEL_10:
    sub_1801A166C(v11[2], v13, &stru_180C37738, v12);
    goto LABEL_11;
  }
  LastError = GetLastError();
  v7 = LastError;
  v8 = hDevice;
  if ( hDevice != &hDevice && (*((_BYTE *)hDevice + 28) & 1) != 0 )
  {
    v9 = 13;
    goto LABEL_5;
  }
LABEL_58:
  if ( TokenHandle != (void *)-1LL )
    CloseHandle(TokenHandle);
  if ( v33 )
    LsaClose(PolicyHandle);
  sub_1801655E0(v3);
  sub_1801655E0(v4);
  if ( v7 == 8 )
    return 32775;
  if ( v7 )
    return 32769;
  if ( v0 )
    return v1 != 0 ? 0x8022 : 0;
  return 32800;
}

```

## disassembly

```asm
0x18024dafc  mov     rax, rsp
0x18024daff  mov     [rax+8], rbx
0x18024db03  mov     [rax+10h], rsi
0x18024db07  mov     [rax+18h], rdi
0x18024db0b  push    rbp
0x18024db0c  push    r12
0x18024db0e  push    r13
0x18024db10  push    r14
0x18024db12  push    r15
0x18024db14  lea     rbp, [rax-5Fh]
0x18024db18  sub     rsp, 0A0h
0x18024db1f  mov     rax, cs:__security_cookie
0x18024db26  xor     rax, rsp
0x18024db29  mov     [rbp+57h+var_28], rax
0x18024db2d  xor     ebx, ebx
0x18024db2f  mov     [rbp+57h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x18024db37  mov     r12b, 1
0x18024db3a  mov     [rbp+57h+PolicyHandle], rbx
0x18024db3e  mov     [rbp+57h+var_8F], r12b
0x18024db42  mov     sil, bl
0x18024db45  mov     [rbp+57h+var_90], bl
0x18024db48  mov     r14b, bl
0x18024db4b  mov     [rbp+57h+var_8E], bl
0x18024db4e  mov     r15d, ebx
0x18024db51  mov     [rbp+57h+var_88], ebx
0x18024db54  mov     r13d, ebx
0x18024db57  mov     [rbp+57h+TokenInformationLength], ebx
0x18024db5a  call    cs:GetCurrentProcess
0x18024db60  mov     rcx, rax; ProcessHandle
0x18024db63  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x18024db67  lea     edx, [rbx+8]; DesiredAccess
0x18024db6a  call    cs:OpenProcessToken
0x18024db70  test    eax, eax
0x18024db72  jnz     short loc_18024DBB9
0x18024db74  call    cs:__imp_GetLastError
0x18024db7a  mov     ebx, eax
0x18024db7c  mov     rcx, cs:hDevice
0x18024db83  lea     rdi, hDevice
0x18024db8a  cmp     rcx, rdi
0x18024db8d  jz      loc_18024DF59
0x18024db93  test    [rcx+1Ch], r12b
0x18024db97  jz      loc_18024DF59
0x18024db9d  lea     edx, [r13+0Bh]
0x18024dba1  mov     rcx, [rcx+10h]
0x18024dba5  lea     r8, stru_180C37738
0x18024dbac  mov     r9d, eax
0x18024dbaf  call    sub_1801A166C
0x18024dbb4  jmp     loc_18024DF59
0x18024dbb9  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18024dbbd  lea     rax, [rbp+57h+TokenInformationLength]
0x18024dbc1  xor     r9d, r9d; TokenInformationLength
0x18024dbc4  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x18024dbc9  xor     r8d, r8d; TokenInformation
0x18024dbcc  lea     edx, [r9+1]; TokenInformationClass
0x18024dbd0  call    cs:GetTokenInformation
0x18024dbd6  mov     ecx, [rbp+57h+TokenInformationLength]
0x18024dbd9  call    sub_1801655F0
0x18024dbde  mov     r13, rax
0x18024dbe1  test    rax, rax
0x18024dbe4  jnz     short loc_18024DC20
0x18024dbe6  mov     rcx, cs:hDevice
0x18024dbed  lea     rdi, hDevice
0x18024dbf4  cmp     rcx, rdi
0x18024dbf7  jz      short loc_18024DC16
0x18024dbf9  test    [rcx+1Ch], r12b
0x18024dbfd  jz      short loc_18024DC16
0x18024dbff  mov     r9d, [rbp+57h+TokenInformationLength]
0x18024dc03  lea     edx, [rax+0Ch]
0x18024dc06  mov     rcx, [rcx+10h]
0x18024dc0a  lea     r8, stru_180C37738
0x18024dc11  call    sub_1801A166C
0x18024dc16  mov     ebx, 8
0x18024dc1b  jmp     loc_18024DF59
0x18024dc20  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x18024dc24  lea     rax, [rbp+57h+TokenInformationLength]
0x18024dc28  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18024dc2c  mov     r8, r13; TokenInformation
0x18024dc2f  mov     edx, 1; TokenInformationClass
0x18024dc34  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x18024dc39  call    cs:GetTokenInformation
0x18024dc3f  test    eax, eax
0x18024dc41  jnz     short loc_18024DC76
0x18024dc43  call    cs:__imp_GetLastError
0x18024dc49  mov     ebx, eax
0x18024dc4b  mov     rcx, cs:hDevice
0x18024dc52  lea     rdi, hDevice
0x18024dc59  cmp     rcx, rdi
0x18024dc5c  jz      loc_18024DF59
0x18024dc62  test    [rcx+1Ch], r12b
0x18024dc66  jz      loc_18024DF59
0x18024dc6c  mov     edx, 0Dh
0x18024dc71  jmp     loc_18024DBA1
0x18024dc76  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18024dc7a  lea     rax, [rbp+57h+var_88]
0x18024dc7e  xor     r9d, r9d; TokenInformationLength
0x18024dc81  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x18024dc86  xor     r8d, r8d; TokenInformation
0x18024dc89  lea     edi, [r9+3]
0x18024dc8d  mov     edx, edi; TokenInformationClass
0x18024dc8f  call    cs:GetTokenInformation
0x18024dc95  mov     ecx, [rbp+57h+var_88]
0x18024dc98  call    sub_1801655F0
0x18024dc9d  mov     r15, rax
0x18024dca0  test    rax, rax
0x18024dca3  jnz     short loc_18024DCD2
0x18024dca5  mov     rcx, cs:hDevice
0x18024dcac  lea     rdi, hDevice
0x18024dcb3  cmp     rcx, rdi
0x18024dcb6  jz      loc_18024DC16
0x18024dcbc  test    [rcx+1Ch], r12b
0x18024dcc0  jz      loc_18024DC16
0x18024dcc6  mov     r9d, [rbp+57h+var_88]
0x18024dcca  lea     edx, [rax+0Eh]
0x18024dccd  jmp     loc_18024DC06
0x18024dcd2  mov     r9d, [rbp+57h+var_88]; TokenInformationLength
0x18024dcd6  lea     rax, [rbp+57h+var_88]
0x18024dcda  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18024dcde  mov     r8, r15; TokenInformation
0x18024dce1  mov     edx, edi; TokenInformationClass
0x18024dce3  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x18024dce8  call    cs:GetTokenInformation
0x18024dcee  test    eax, eax
0x18024dcf0  jnz     short loc_18024DD25
0x18024dcf2  call    cs:__imp_GetLastError
0x18024dcf8  mov     ebx, eax
0x18024dcfa  mov     rcx, cs:hDevice
0x18024dd01  lea     rdi, hDevice
0x18024dd08  cmp     rcx, rdi
0x18024dd0b  jz      loc_18024DF59
0x18024dd11  test    [rcx+1Ch], r12b
0x18024dd15  jz      loc_18024DF59
0x18024dd1b  mov     edx, 0Fh
0x18024dd20  jmp     loc_18024DBA1
0x18024dd25  mov     r12, rbx
0x18024dd28  lea     rdi, hDevice
0x18024dd2f  mov     rsi, rbx
0x18024dd32  lea     rax, off_180C37710; "SeDebugPrivilege"
0x18024dd39  mov     [rbp+57h+var_60], rbx
0x18024dd3d  mov     rdx, [rsi+rax]
0x18024dd41  lea     r8, [rbp+57h+var_60]
0x18024dd45  call    sub_18024D864
0x18024dd4a  xor     r9d, r9d
0x18024dd4d  mov     ebx, eax
0x18024dd4f  test    eax, eax
0x18024dd51  jnz     loc_18024DF1B
0x18024dd57  mov     r8d, [r15]
0x18024dd5a  mov     edx, r9d
0x18024dd5d  test    r8, r8
0x18024dd60  jz      short loc_18024DD85
0x18024dd62  lea     rcx, [r15+0Ch]
0x18024dd66  mov     rax, [rcx-8]
0x18024dd6a  cmp     rax, [rbp+57h+var_60]
0x18024dd6e  jnz     short loc_18024DD79
0x18024dd70  test    byte ptr [rcx], 4
0x18024dd73  jz      loc_18024DECC
0x18024dd79  inc     rdx
0x18024dd7c  add     rcx, 0Ch
0x18024dd80  cmp     rdx, r8
0x18024dd83  jb      short loc_18024DD66
0x18024dd85  cmp     rdx, r8
0x18024dd88  jnz     loc_18024DECC
0x18024dd8e  xorps   xmm0, xmm0
0x18024dd91  movups  xmmword ptr [rbp+57h+UserRights.Length], xmm0
0x18024dd95  mov     rcx, cs:hDevice
0x18024dd9c  cmp     rcx, rdi
0x18024dd9f  jz      short loc_18024DDCA
0x18024dda1  test    byte ptr [rcx+1Ch], 8
0x18024dda5  jz      short loc_18024DDCA
0x18024dda7  mov     rcx, [rcx+10h]
0x18024ddab  lea     r9, off_180C37710; "SeDebugPrivilege"
0x18024ddb2  mov     r9, [rsi+r9]
0x18024ddb6  lea     r8, stru_180C37738
0x18024ddbd  mov     edx, 11h
0x18024ddc2  call    sub_1801C8638
0x18024ddc7  xor     r9d, r9d
0x18024ddca  test    r14b, r14b
0x18024ddcd  jnz     short loc_18024DE06
0x18024ddcf  xorps   xmm0, xmm0
0x18024ddd2  lea     r9, [rbp+57h+PolicyHandle]; PolicyHandle
0x18024ddd6  mov     r8d, 0F0FFFh; DesiredAccess
0x18024dddc  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18024dde0  xor     ecx, ecx; SystemName
0x18024dde2  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18024dde6  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18024ddea  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18024ddee  call    cs:LsaOpenPolicy
0x18024ddf4  xor     r9d, r9d
0x18024ddf7  mov     r14d, eax
0x18024ddfa  test    eax, eax
0x18024ddfc  jnz     loc_18024DEE0
0x18024de02  mov     [rbp+57h+var_8E], 1
0x18024de06  lea     rax, off_180C37710; "SeDebugPrivilege"
0x18024de0d  mov     rcx, [rsi+rax]
0x18024de11  or      rax, 0FFFFFFFFFFFFFFFFh
0x18024de15  mov     [rbp+57h+UserRights.Buffer], rcx
0x18024de19  inc     rax
0x18024de1c  cmp     [rcx+rax*2], r9w
0x18024de21  jnz     short loc_18024DE19
0x18024de23  mov     rdx, [r13+0]; AccountSid
0x18024de27  lea     r8, [rbp+57h+UserRights]; UserRights
0x18024de2b  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x18024de2f  add     ax, ax
0x18024de32  mov     [rbp+57h+UserRights.Length], ax
0x18024de36  mov     r9d, 1; CountOfRights
0x18024de3c  add     ax, 2
0x18024de40  mov     [rbp+57h+UserRights.MaximumLength], ax
0x18024de44  call    cs:LsaAddAccountRights
0x18024de4a  xor     r9d, r9d
0x18024de4d  mov     r14d, eax
0x18024de50  test    eax, eax
0x18024de52  jnz     short loc_18024DE8A
0x18024de54  mov     [rbp+57h+var_90], 1
0x18024de58  mov     rcx, cs:hDevice
0x18024de5f  cmp     rcx, rdi
0x18024de62  jz      short loc_18024DEC8
0x18024de64  test    byte ptr [rcx+1Ch], 8
0x18024de68  jz      short loc_18024DEC8
0x18024de6a  mov     rcx, [rcx+10h]
0x18024de6e  lea     edx, [rax+13h]
0x18024de71  lea     rax, off_180C37710; "SeDebugPrivilege"
0x18024de78  mov     r9, [rsi+rax]
0x18024de7c  lea     r8, stru_180C37738
0x18024de83  call    sub_1801C8638
0x18024de88  jmp     short loc_18024DEC8
0x18024de8a  mov     ecx, r14d; Status
0x18024de8d  mov     [rbp+57h+var_8F], r9b
0x18024de91  call    cs:__imp_RtlNtStatusToDosError
0x18024de97  mov     rcx, cs:hDevice
0x18024de9e  cmp     rcx, rdi
0x18024dea1  jz      short loc_18024DEC6
0x18024dea3  test    byte ptr [rcx+1Ch], 1
0x18024dea7  jz      short loc_18024DEC6
0x18024dea9  mov     rcx, [rcx+10h]
0x18024dead  mov     [rsp+0C0h+var_98], eax
0x18024deb1  lea     rax, off_180C37710; "SeDebugPrivilege"
0x18024deb8  mov     r9, [rsi+rax]
0x18024debc  mov     dword ptr [rsp+0C0h+ReturnLength], r14d
0x18024dec1  call    sub_18024E2B8
0x18024dec6  xor     ebx, ebx
0x18024dec8  mov     r14b, [rbp+57h+var_8E]
0x18024decc  inc     r12
0x18024decf  add     rsi, 8
0x18024ded3  cmp     rsi, 28h ; '('
0x18024ded7  jnb     short loc_18024DF51
0x18024ded9  xor     ebx, ebx
0x18024dedb  jmp     loc_18024DD32
0x18024dee0  mov     ecx, r14d; Status
0x18024dee3  call    cs:__imp_RtlNtStatusToDosError
0x18024dee9  mov     ebx, eax
0x18024deeb  mov     rcx, cs:hDevice
0x18024def2  cmp     rcx, rdi
0x18024def5  jz      short loc_18024DF51
0x18024def7  test    byte ptr [rcx+1Ch], 1
0x18024defb  jz      short loc_18024DF51
0x18024defd  mov     rcx, [rcx+10h]
0x18024df01  lea     r8, stru_180C37738
0x18024df08  mov     edx, 12h
0x18024df0d  mov     dword ptr [rsp+0C0h+ReturnLength], eax
0x18024df11  mov     r9d, r14d
0x18024df14  call    sub_1801A5560
0x18024df19  jmp     short loc_18024DF51
0x18024df1b  mov     rcx, cs:hDevice
0x18024df22  cmp     rcx, rdi
0x18024df25  jz      short loc_18024DF51
0x18024df27  test    byte ptr [rcx+1Ch], 1
0x18024df2b  jz      short loc_18024DF51
0x18024df2d  mov     rcx, [rcx+10h]
0x18024df31  lea     r8, stru_180C37738
0x18024df38  mov     dword ptr [rsp+0C0h+ReturnLength], eax
0x18024df3c  mov     edx, 10h
0x18024df41  lea     rax, off_180C37710; "SeDebugPrivilege"
0x18024df48  mov     r9, [rax+r12*8]
0x18024df4c  call    sub_1801A569C
0x18024df51  mov     sil, [rbp+57h+var_90]
0x18024df55  mov     r12b, [rbp+57h+var_8F]
0x18024df59  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18024df5d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18024df61  jz      short loc_18024DF69
0x18024df63  call    cs:__imp_CloseHandle
0x18024df69  cmp     [rbp+57h+var_8E], 0
0x18024df6d  jz      short loc_18024DF79
0x18024df6f  mov     rcx, [rbp+57h+PolicyHandle]; ObjectHandle
0x18024df73  call    cs:LsaClose
0x18024df79  mov     rcx, r15; lpMem
0x18024df7c  call    sub_1801655E0
0x18024df81  mov     rcx, r13; lpMem
0x18024df84  call    sub_1801655E0
0x18024df89  cmp     ebx, 8
0x18024df8c  jnz     short loc_18024DF95
0x18024df8e  mov     eax, 8007h
0x18024df93  jmp     short loc_18024DFB6
0x18024df95  test    ebx, ebx
0x18024df97  jz      short loc_18024DFA0
0x18024df99  mov     eax, 8001h
0x18024df9e  jmp     short loc_18024DFB6
0x18024dfa0  test    r12b, r12b
0x18024dfa3  jnz     short loc_18024DFAC
0x18024dfa5  mov     eax, 8020h
0x18024dfaa  jmp     short loc_18024DFB6
0x18024dfac  neg     sil
  ... truncated ...
```
