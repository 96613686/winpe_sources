# NgscbManageDeviceEncryptionOptOutForVolume(ushort const *,NgscbManageDEVolumeOptOutOption)

- ea: `0x1800106ec`
- end: `0x180010907`
- name: `?NgscbManageDeviceEncryptionOptOutForVolume@@YAJPEBGW4NgscbManageDEVolumeOptOutOption@@@Z`
- size: `539`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting`

## callers

- `0x180007360`

## callees

- `0x180001bb0`
- `0x180002774`
- `0x1800037a0`
- `0x18000e354`
- `0x18000fbc0`
- `0x18000ff64`
- `0x1800103b8`
- `0x1800106ec`
- `0x180010cc4`
- `0x180010e54`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x18001084b`
- `KERNEL32!DeleteFileW` at `0x18001084b`
- `ntdll!RtlFreeUnicodeString` at `0x1800108cd`
- `ntdll!RtlFreeUnicodeString` at `0x1800108cd`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18001075c`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x18001075c`

## pseudocode

```c
__int64 __fastcall NgscbManageDeviceEncryptionOptOutForVolume(const unsigned __int16 *a1)
{
  int v2; // eax
  unsigned int v3; // eax
  unsigned __int64 v4; // r8
  int v5; // ebx
  unsigned int DEOptOutFileName; // eax
  unsigned int v7; // r8d
  unsigned int i; // edi
  unsigned int v9; // eax
  unsigned int KnownLastErrorHR; // eax
  int v12; // [rsp+20h] [rbp-E0h] BYREF
  __int64 v13; // [rsp+28h] [rbp-D8h] BYREF
  char v14; // [rsp+30h] [rbp-D0h]
  int v15; // [rsp+34h] [rbp-CCh]
  _UNICODE_STRING UnicodeString; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR FileName[1024]; // [rsp+50h] [rbp-B0h] BYREF

  memset_0(FileName, 0, sizeof(FileName));
  v13 = 0;
  v14 = 0;
  v15 = 0;
  UnicodeString = 0;
  v2 = RtlDosPathNameToNtPathName_U_WithStatus(a1, &UnicodeString, 0, 0);
  v3 = FromNtStatus(v2);
  v5 = v3;
  if ( !v3 )
    goto LABEL_10;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 326, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v3);
  if ( v5 >= 0 )
  {
LABEL_10:
    DEOptOutFileName = NgscbpGetDEOptOutFileName(a1, FileName, v4);
    v5 = DEOptOutFileName;
    if ( !DEOptOutFileName )
      goto LABEL_11;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        327,
        WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
        DEOptOutFileName);
    if ( v5 >= 0 )
    {
LABEL_11:
      for ( i = 0; i <= 1; ++i )
      {
        if ( i )
        {
          v12 = 18;
          v9 = CNgscbScopedPrivilege::AcquirePrivileges((CNgscbScopedPrivilege *)&v13, &v12, v7);
          v5 = v9;
          if ( v9 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 328, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v9);
            if ( v5 < 0 )
              break;
          }
        }
        if ( DeleteFileW(FileName) )
          break;
        KnownLastErrorHR = NgscbGetKnownLastErrorHR();
        v5 = KnownLastErrorHR;
        if ( KnownLastErrorHR != -2147024891 )
        {
          if ( KnownLastErrorHR + 2147024894 <= 1 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 329, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids);
            v5 = 0;
          }
          else if ( KnownLastErrorHR
                 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              330,
              WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
              KnownLastErrorHR);
          }
          break;
        }
      }
    }
  }
  RtlFreeUnicodeString(&UnicodeString);
  CNgscbScopedPrivilege::ReleasePrivilege((CNgscbScopedPrivilege *)&v13);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800106ec  mov     [rsp-8+arg_8], rbx
0x1800106f1  mov     [rsp-8+arg_10], rdi
0x1800106f6  push    rbp
0x1800106f7  push    r14
0x1800106f9  push    r15
0x1800106fb  lea     rbp, [rsp-760h]
0x180010703  sub     rsp, 860h
0x18001070a  mov     rax, cs:__security_cookie
0x180010711  xor     rax, rsp
0x180010714  mov     [rbp+770h+var_20], rax
0x18001071b  mov     rdi, rcx
0x18001071e  xor     edx, edx; Val
0x180010720  lea     rcx, [rsp+870h+FileName]; void *
0x180010725  mov     r8d, 800h; Size
0x18001072b  call    memset_0
0x180010730  xorps   xmm0, xmm0
0x180010733  mov     [rsp+870h+var_848], 0
0x18001073c  xor     r9d, r9d
0x18001073f  mov     [rsp+870h+var_840], 0
0x180010744  xor     r8d, r8d
0x180010747  mov     [rsp+870h+var_83C], 0
0x18001074f  lea     rdx, [rsp+870h+UnicodeString]
0x180010754  mov     rcx, rdi
0x180010757  movups  xmmword ptr [rsp+870h+UnicodeString.Length], xmm0
0x18001075c  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x180010762  mov     ecx, eax; int
0x180010764  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x180010769  lea     r14, WPP_GLOBAL_Control
0x180010770  mov     ebx, eax
0x180010772  lea     r15, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x180010779  test    eax, eax
0x18001077b  jz      short loc_1800107AB
0x18001077d  mov     rcx, cs:WPP_GLOBAL_Control
0x180010784  cmp     rcx, r14
0x180010787  jz      short loc_1800107A3
0x180010789  test    byte ptr [rcx+1Ch], 40h
0x18001078d  jz      short loc_1800107A3
0x18001078f  mov     rcx, [rcx+10h]
0x180010793  mov     edx, 146h
0x180010798  mov     r9d, eax
0x18001079b  mov     r8, r15
0x18001079e  call    WPP_SF_d
0x1800107a3  test    ebx, ebx
0x1800107a5  js      loc_1800108C8
0x1800107ab  lea     rdx, [rsp+870h+FileName]; unsigned __int16 *
0x1800107b0  mov     rcx, rdi; unsigned __int16 *
0x1800107b3  call    ?NgscbpGetDEOptOutFileName@@YAJPEBGPEAG_K@Z; NgscbpGetDEOptOutFileName(ushort const *,ushort *,unsigned __int64)
0x1800107b8  mov     ebx, eax
0x1800107ba  test    eax, eax
0x1800107bc  jz      short loc_1800107EC
0x1800107be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800107c5  cmp     rcx, r14
0x1800107c8  jz      short loc_1800107E4
0x1800107ca  test    byte ptr [rcx+1Ch], 40h
0x1800107ce  jz      short loc_1800107E4
0x1800107d0  mov     rcx, [rcx+10h]
0x1800107d4  mov     edx, 147h
0x1800107d9  mov     r9d, eax
0x1800107dc  mov     r8, r15
0x1800107df  call    WPP_SF_d
0x1800107e4  test    ebx, ebx
0x1800107e6  js      loc_1800108C8
0x1800107ec  xor     edi, edi
0x1800107ee  cmp     edi, 1
0x1800107f1  ja      loc_1800108C8
0x1800107f7  test    edi, edi
0x1800107f9  jz      short loc_180010846
0x1800107fb  lea     rdx, [rsp+870h+var_850]; int *
0x180010800  mov     [rsp+870h+var_850], 12h
0x180010808  lea     rcx, [rsp+870h+var_848]; this
0x18001080d  call    ?AcquirePrivileges@CNgscbScopedPrivilege@@QEAAJPEAJK@Z; CNgscbScopedPrivilege::AcquirePrivileges(long *,ulong)
0x180010812  mov     ebx, eax
0x180010814  test    eax, eax
0x180010816  jz      short loc_180010846
0x180010818  mov     rcx, cs:WPP_GLOBAL_Control
0x18001081f  cmp     rcx, r14
0x180010822  jz      short loc_18001083E
0x180010824  test    byte ptr [rcx+1Ch], 40h
0x180010828  jz      short loc_18001083E
0x18001082a  mov     rcx, [rcx+10h]
0x18001082e  mov     edx, 148h
0x180010833  mov     r9d, eax
0x180010836  mov     r8, r15
0x180010839  call    WPP_SF_d
0x18001083e  test    ebx, ebx
0x180010840  js      loc_1800108C8
0x180010846  lea     rcx, [rsp+870h+FileName]; lpFileName
0x18001084b  call    cs:__imp_DeleteFileW
0x180010851  test    eax, eax
0x180010853  jnz     short loc_1800108C8
0x180010855  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x18001085a  mov     ebx, eax
0x18001085c  mov     ecx, eax
0x18001085e  cmp     eax, 80070005h
0x180010863  jnz     short loc_180010869
0x180010865  inc     edi
0x180010867  jmp     short loc_1800107EE
0x180010869  add     eax, 7FF8FFFEh
0x18001086e  cmp     eax, 1
0x180010871  jbe     short loc_1800108A3
0x180010873  test    ebx, ebx
0x180010875  js      short loc_18001087B
0x180010877  test    ecx, ecx
0x180010879  jz      short loc_1800108C8
0x18001087b  mov     rcx, cs:WPP_GLOBAL_Control
0x180010882  cmp     rcx, r14
0x180010885  jz      short loc_1800108C8
0x180010887  test    byte ptr [rcx+1Ch], 40h
0x18001088b  jz      short loc_1800108C8
0x18001088d  mov     rcx, [rcx+10h]
0x180010891  mov     edx, 14Ah
0x180010896  mov     r9d, ebx
0x180010899  mov     r8, r15
0x18001089c  call    WPP_SF_d
0x1800108a1  jmp     short loc_1800108C8
0x1800108a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800108aa  cmp     rcx, r14
0x1800108ad  jz      short loc_1800108C6
0x1800108af  test    byte ptr [rcx+1Ch], 8
0x1800108b3  jz      short loc_1800108C6
0x1800108b5  mov     rcx, [rcx+10h]
0x1800108b9  mov     edx, 149h
0x1800108be  mov     r8, r15
0x1800108c1  call    WPP_SF_
0x1800108c6  xor     ebx, ebx
0x1800108c8  lea     rcx, [rsp+870h+UnicodeString]; UnicodeString
0x1800108cd  call    cs:__imp_RtlFreeUnicodeString
0x1800108d3  lea     rcx, [rsp+870h+var_848]; this
0x1800108d8  call    ?ReleasePrivilege@CNgscbScopedPrivilege@@QEAAXXZ; CNgscbScopedPrivilege::ReleasePrivilege(void)
0x1800108dd  mov     eax, ebx
0x1800108df  mov     rcx, [rbp+770h+var_20]
0x1800108e6  xor     rcx, rsp; StackCookie
0x1800108e9  call    __security_check_cookie
0x1800108ee  lea     r11, [rsp+870h+var_10]
0x1800108f6  mov     rbx, [r11+28h]
0x1800108fa  mov     rdi, [r11+30h]
0x1800108fe  mov     rsp, r11
0x180010901  pop     r15
0x180010903  pop     r14
0x180010905  pop     rbp
0x180010906  retn
```
