# GetServerConfig(_NFS_SERVER_NETGROUP_CONFIG *)

- ea: `0x180015980`
- end: `0x180015b27`
- name: `?GetServerConfig@@YA?AW4_MI_Result@@PEAU_NFS_SERVER_NETGROUP_CONFIG@@@Z`
- size: `423`
- prototype: `enum _MI_Result __fastcall(struct _NFS_SERVER_NETGROUP_CONFIG *)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800147ac`
- `0x180014a3c`
- `0x180014c58`
- `0x1800156bc`
- `0x18001603c`

## callees

- `0x180015890`
- `0x180015980`
- `0x180037010`

## import_xrefs

- `mi!MI_Application_InitializeV1` at `0x1800159cc`
- `mi!MI_Application_InitializeV1` at `0x1800159cc`

## pseudocode

```c
__int64 __fastcall GetServerConfig(struct _NFS_SERVER_NETGROUP_CONFIG *a1)
{
  int v3; // [rsp+28h] [rbp-31h]
  _BYTE v4[24]; // [rsp+50h] [rbp-9h] BYREF
  _BYTE v5[24]; // [rsp+68h] [rbp+Fh] BYREF
  MI_Application application; // [rsp+80h] [rbp+27h] BYREF
  char v7; // [rsp+C8h] [rbp+6Fh] BYREF
  MI_Result LdapNetGroupConfiguration; // [rsp+D0h] [rbp+77h] BYREF
  __int64 v9; // [rsp+D8h] [rbp+7Fh] BYREF

  LdapNetGroupConfiguration = MI_RESULT_OK;
  v7 = 0;
  v9 = 0;
  memset(&application, 0, sizeof(application));
  memset(v5, 0, sizeof(v5));
  memset(v4, 0, sizeof(v4));
  LdapNetGroupConfiguration = MI_Application_InitializeV1(0, 0, 0, &application);
  if ( LdapNetGroupConfiguration == MI_RESULT_OK )
  {
    if ( application.ft )
    {
      LdapNetGroupConfiguration = ((unsigned int (__fastcall *)(MI_Application *, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _BYTE *))application.ft->NewSession)(
                                    &application,
                                    0,
                                    0,
                                    0,
                                    0,
                                    0,
                                    v5);
      if ( LdapNetGroupConfiguration == MI_RESULT_OK )
      {
        if ( *(_QWORD *)&v5[16] )
        {
          LOBYTE(v3) = 0;
          (*(void (__fastcall **)(_BYTE *, _QWORD, _QWORD, const wchar_t *, const wchar_t *, int, _QWORD, _BYTE *))(*(_QWORD *)&v5[16] + 56LL))(
            v5,
            0,
            0,
            L"root/microsoft/windows/nfs",
            L"MSFT_NfsNetgroupStore",
            v3,
            0,
            v4);
        }
        else
        {
          memset(v4, 0, sizeof(v4));
        }
        if ( *(_QWORD *)&v4[16] )
        {
          (*(void (__fastcall **)(_BYTE *, __int64 *, char *, MI_Result *, _QWORD, _QWORD))(*(_QWORD *)&v4[16] + 24LL))(
            v4,
            &v9,
            &v7,
            &LdapNetGroupConfiguration,
            0,
            0);
        }
        else
        {
          LdapNetGroupConfiguration = MI_RESULT_INVALID_PARAMETER;
          v7 = 0;
        }
        if ( LdapNetGroupConfiguration == MI_RESULT_OK && v9 )
          LdapNetGroupConfiguration = (unsigned int)GetLdapNetGroupConfiguration(v9, a1);
        if ( *(_QWORD *)&v4[16] )
          (**(void (__fastcall ***)(_BYTE *))&v4[16])(v4);
        if ( *(_QWORD *)&v5[16] )
          (**(void (__fastcall ***)(_BYTE *, _QWORD, _QWORD))&v5[16])(v5, 0, 0);
      }
    }
    else
    {
      LdapNetGroupConfiguration = MI_RESULT_INVALID_PARAMETER;
      memset(v5, 0, sizeof(v5));
    }
    if ( application.ft )
      ((void (__fastcall *)(MI_Application *))application.ft->Close)(&application);
  }
  return (unsigned int)LdapNetGroupConfiguration;
}

```

## disassembly

```asm
0x180015980  push    rbp
0x180015982  push    rbx
0x180015983  push    rdi
0x180015984  lea     rbp, [rsp-47h]
0x180015989  sub     rsp, 0A0h
0x180015990  xor     edi, edi
0x180015992  lea     r9, [rbp+57h+application]; application
0x180015996  xorps   xmm0, xmm0
0x180015999  mov     [rbp+57h+arg_10], edi
0x18001599c  mov     rbx, rcx
0x18001599f  mov     [rbp+57h+arg_8], dil
0x1800159a3  xorps   xmm1, xmm1
0x1800159a6  mov     [rbp+57h+arg_18], rdi
0x1800159aa  xor     ecx, ecx; flags
0x1800159ac  mov     [rbp+57h+application.reserved1], rdi
0x1800159b0  xor     r8d, r8d; extendedError
0x1800159b3  mov     qword ptr [rbp+57h+var_48], rdi
0x1800159b7  xor     edx, edx; applicationID
0x1800159b9  mov     qword ptr [rbp+57h+var_60], rdi
0x1800159bd  movdqu  xmmword ptr [rbp+57h+application.reserved2], xmm0
0x1800159c2  movdqu  [rbp+57h+var_48+8], xmm1
0x1800159c7  movdqu  [rbp+57h+var_60+8], xmm0
0x1800159cc  call    cs:__imp_MI_Application_InitializeV1
0x1800159d2  mov     [rbp+57h+arg_10], eax
0x1800159d5  test    eax, eax
0x1800159d7  jnz     loc_180015B19
0x1800159dd  mov     rax, [rbp+57h+application.ft]
0x1800159e1  test    rax, rax
0x1800159e4  jz      loc_180015AF0
0x1800159ea  mov     rax, [rax+8]
0x1800159ee  lea     rcx, [rbp+57h+var_48]
0x1800159f2  mov     [rsp+0B0h+var_80], rcx
0x1800159f7  xor     r9d, r9d
0x1800159fa  mov     [rsp+0B0h+var_88], rdi
0x1800159ff  lea     rcx, [rbp+57h+application]
0x180015a03  xor     r8d, r8d
0x180015a06  mov     [rsp+0B0h+var_90], rdi
0x180015a0b  xor     edx, edx
0x180015a0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a12  mov     [rbp+57h+arg_10], eax
0x180015a15  test    eax, eax
0x180015a17  jnz     loc_180015B04
0x180015a1d  mov     rax, [rbp+57h+var_38]
0x180015a21  test    rax, rax
0x180015a24  jz      short loc_180015A60
0x180015a26  mov     rax, [rax+38h]
0x180015a2a  lea     rcx, [rbp+57h+var_60]
0x180015a2e  mov     [rsp+0B0h+var_78], rcx
0x180015a33  lea     r9, aRootMicrosoftW; "root/microsoft/windows/nfs"
0x180015a3a  mov     [rsp+0B0h+var_80], rdi
0x180015a3f  lea     rcx, aMsftNfsnetgrou; "MSFT_NfsNetgroupStore"
0x180015a46  mov     byte ptr [rsp+0B0h+var_88], dil
0x180015a4b  xor     r8d, r8d
0x180015a4e  mov     [rsp+0B0h+var_90], rcx
0x180015a53  xor     edx, edx
0x180015a55  lea     rcx, [rbp+57h+var_48]
0x180015a59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a5e  jmp     short loc_180015A6D
0x180015a60  xorps   xmm0, xmm0
0x180015a63  xor     eax, eax
0x180015a65  movups  [rbp+57h+var_60], xmm0
0x180015a69  mov     [rbp+57h+var_50], rax
0x180015a6d  mov     rax, [rbp+57h+var_50]
0x180015a71  test    rax, rax
0x180015a74  jz      short loc_180015A9B
0x180015a76  mov     rax, [rax+18h]
0x180015a7a  lea     r9, [rbp+57h+arg_10]
0x180015a7e  mov     [rsp+0B0h+var_88], rdi
0x180015a83  lea     r8, [rbp+57h+arg_8]
0x180015a87  lea     rdx, [rbp+57h+arg_18]
0x180015a8b  mov     [rsp+0B0h+var_90], rdi
0x180015a90  lea     rcx, [rbp+57h+var_60]
0x180015a94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015a99  jmp     short loc_180015AA6
0x180015a9b  mov     [rbp+57h+arg_10], 4
0x180015aa2  mov     [rbp+57h+arg_8], dil
0x180015aa6  cmp     [rbp+57h+arg_10], edi
0x180015aa9  jnz     short loc_180015ABF
0x180015aab  mov     rcx, [rbp+57h+arg_18]
0x180015aaf  test    rcx, rcx
0x180015ab2  jz      short loc_180015ABF
0x180015ab4  mov     rdx, rbx
0x180015ab7  call    GetLdapNetGroupConfiguration
0x180015abc  mov     [rbp+57h+arg_10], eax
0x180015abf  mov     rax, [rbp+57h+var_50]
0x180015ac3  test    rax, rax
0x180015ac6  jz      short loc_180015AD4
0x180015ac8  mov     rax, [rax]
0x180015acb  lea     rcx, [rbp+57h+var_60]
0x180015acf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ad4  mov     rax, [rbp+57h+var_38]
0x180015ad8  test    rax, rax
0x180015adb  jz      short loc_180015B04
0x180015add  mov     rax, [rax]
0x180015ae0  lea     rcx, [rbp+57h+var_48]
0x180015ae4  xor     r8d, r8d
0x180015ae7  xor     edx, edx
0x180015ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015aee  jmp     short loc_180015B04
0x180015af0  xorps   xmm0, xmm0
0x180015af3  mov     [rbp+57h+arg_10], 4
0x180015afa  xor     eax, eax
0x180015afc  movups  [rbp+57h+var_48], xmm0
0x180015b00  mov     [rbp+57h+var_38], rax
0x180015b04  mov     rax, [rbp+57h+application.ft]
0x180015b08  test    rax, rax
0x180015b0b  jz      short loc_180015B19
0x180015b0d  mov     rax, [rax]
0x180015b10  lea     rcx, [rbp+57h+application]
0x180015b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b19  mov     eax, [rbp+57h+arg_10]
0x180015b1c  add     rsp, 0A0h
0x180015b23  pop     rdi
0x180015b24  pop     rbx
0x180015b25  pop     rbp
0x180015b26  retn
```
