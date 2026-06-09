# NgscbManageDeviceEncryptionOptOutForVolume(ushort const *,NgscbManageDEVolumeOptOutOption)

- ea: `0x1800d67e8`
- end: `0x1800d6a19`
- name: `?NgscbManageDeviceEncryptionOptOutForVolume@@YAJPEBGW4NgscbManageDEVolumeOptOutOption@@@Z`
- size: `561`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting`

## callers

- `0x180066f10`

## callees

- `0x180008d70`
- `0x1800090c0`
- `0x1800166ac`
- `0x180018b10`
- `0x180044d54`
- `0x18004fddc`
- `0x1800d67e8`
- `0x1800d6a20`
- `0x18011efce`
- `0x18011f010`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800d6858`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800d6858`
- `ntdll!RtlFreeUnicodeString` at `0x1800d69d8`
- `ntdll!RtlFreeUnicodeString` at `0x1800d69d8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800d694d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800d694d`

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
  struct _UNICODE_STRING UnicodeString; // [rsp+38h] [rbp-C8h] BYREF
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 326, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v3);
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
        &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
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
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 328, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids, v9);
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
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 329, &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids);
            v5 = 0;
          }
          else if ( KnownLastErrorHR
                 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              330,
              &WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids,
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
0x1800d67e8  mov     [rsp-8+arg_8], rbx
0x1800d67ed  mov     [rsp-8+arg_10], rdi
0x1800d67f2  push    rbp
0x1800d67f3  push    r14
0x1800d67f5  push    r15
0x1800d67f7  lea     rbp, [rsp-760h]
0x1800d67ff  sub     rsp, 860h
0x1800d6806  mov     rax, cs:__security_cookie
0x1800d680d  xor     rax, rsp
0x1800d6810  mov     [rbp+770h+var_20], rax
0x1800d6817  mov     rdi, rcx
0x1800d681a  xor     edx, edx; Val
0x1800d681c  lea     rcx, [rsp+870h+FileName]; void *
0x1800d6821  mov     r8d, 800h; Size
0x1800d6827  call    memset_0
0x1800d682c  xorps   xmm0, xmm0
0x1800d682f  mov     [rsp+870h+var_848], 0
0x1800d6838  xor     r9d, r9d
0x1800d683b  mov     [rsp+870h+var_840], 0
0x1800d6840  xor     r8d, r8d
0x1800d6843  mov     [rsp+870h+var_83C], 0
0x1800d684b  lea     rdx, [rsp+870h+UnicodeString]
0x1800d6850  mov     rcx, rdi
0x1800d6853  movups  xmmword ptr [rsp+870h+UnicodeString.Length], xmm0
0x1800d6858  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x1800d685f  nop     dword ptr [rax+rax+00h]
0x1800d6864  mov     ecx, eax; int
0x1800d6866  call    ?FromNtStatus@@YAJJ@Z; FromNtStatus(long)
0x1800d686b  lea     r14, WPP_GLOBAL_Control
0x1800d6872  mov     ebx, eax
0x1800d6874  lea     r15, WPP_675b2fa976c6352e0be0677ce868dc4e_Traceguids
0x1800d687b  test    eax, eax
0x1800d687d  jz      short loc_1800D68AD
0x1800d687f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d6886  cmp     rcx, r14
0x1800d6889  jz      short loc_1800D68A5
0x1800d688b  test    byte ptr [rcx+1Ch], 40h
0x1800d688f  jz      short loc_1800D68A5
0x1800d6891  mov     rcx, [rcx+10h]
0x1800d6895  mov     edx, 146h
0x1800d689a  mov     r9d, eax
0x1800d689d  mov     r8, r15
0x1800d68a0  call    WPP_SF_d
0x1800d68a5  test    ebx, ebx
0x1800d68a7  js      loc_1800D69D3
0x1800d68ad  lea     rdx, [rsp+870h+FileName]; unsigned __int16 *
0x1800d68b2  mov     rcx, rdi; unsigned __int16 *
0x1800d68b5  call    ?NgscbpGetDEOptOutFileName@@YAJPEBGPEAG_K@Z; NgscbpGetDEOptOutFileName(ushort const *,ushort *,unsigned __int64)
0x1800d68ba  mov     ebx, eax
0x1800d68bc  test    eax, eax
0x1800d68be  jz      short loc_1800D68EE
0x1800d68c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d68c7  cmp     rcx, r14
0x1800d68ca  jz      short loc_1800D68E6
0x1800d68cc  test    byte ptr [rcx+1Ch], 40h
0x1800d68d0  jz      short loc_1800D68E6
0x1800d68d2  mov     rcx, [rcx+10h]
0x1800d68d6  mov     edx, 147h
0x1800d68db  mov     r9d, eax
0x1800d68de  mov     r8, r15
0x1800d68e1  call    WPP_SF_d
0x1800d68e6  test    ebx, ebx
0x1800d68e8  js      loc_1800D69D3
0x1800d68ee  xor     edi, edi
0x1800d68f0  cmp     edi, 1
0x1800d68f3  ja      loc_1800D69D3
0x1800d68f9  test    edi, edi
0x1800d68fb  jz      short loc_1800D6948
0x1800d68fd  lea     rdx, [rsp+870h+var_850]; int *
0x1800d6902  mov     [rsp+870h+var_850], 12h
0x1800d690a  lea     rcx, [rsp+870h+var_848]; this
0x1800d690f  call    ?AcquirePrivileges@CNgscbScopedPrivilege@@QEAAJPEAJK@Z; CNgscbScopedPrivilege::AcquirePrivileges(long *,ulong)
0x1800d6914  mov     ebx, eax
0x1800d6916  test    eax, eax
0x1800d6918  jz      short loc_1800D6948
0x1800d691a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d6921  cmp     rcx, r14
0x1800d6924  jz      short loc_1800D6940
0x1800d6926  test    byte ptr [rcx+1Ch], 40h
0x1800d692a  jz      short loc_1800D6940
0x1800d692c  mov     rcx, [rcx+10h]
0x1800d6930  mov     edx, 148h
0x1800d6935  mov     r9d, eax
0x1800d6938  mov     r8, r15
0x1800d693b  call    WPP_SF_d
0x1800d6940  test    ebx, ebx
0x1800d6942  js      loc_1800D69D3
0x1800d6948  lea     rcx, [rsp+870h+FileName]; lpFileName
0x1800d694d  call    cs:__imp_DeleteFileW
0x1800d6954  nop     dword ptr [rax+rax+00h]
0x1800d6959  test    eax, eax
0x1800d695b  jnz     short loc_1800D69D3
0x1800d695d  call    ?NgscbGetKnownLastErrorHR@@YAJXZ; NgscbGetKnownLastErrorHR(void)
0x1800d6962  mov     ebx, eax
0x1800d6964  mov     ecx, eax
0x1800d6966  cmp     eax, 80070005h
0x1800d696b  jnz     short loc_1800D6974
0x1800d696d  inc     edi
0x1800d696f  jmp     loc_1800D68F0
0x1800d6974  add     eax, 7FF8FFFEh
0x1800d6979  cmp     eax, 1
0x1800d697c  jbe     short loc_1800D69AE
0x1800d697e  test    ebx, ebx
0x1800d6980  js      short loc_1800D6986
0x1800d6982  test    ecx, ecx
0x1800d6984  jz      short loc_1800D69D3
0x1800d6986  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d698d  cmp     rcx, r14
0x1800d6990  jz      short loc_1800D69D3
0x1800d6992  test    byte ptr [rcx+1Ch], 40h
0x1800d6996  jz      short loc_1800D69D3
0x1800d6998  mov     rcx, [rcx+10h]
0x1800d699c  mov     edx, 14Ah
0x1800d69a1  mov     r9d, ebx
0x1800d69a4  mov     r8, r15
0x1800d69a7  call    WPP_SF_d
0x1800d69ac  jmp     short loc_1800D69D3
0x1800d69ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800d69b5  cmp     rcx, r14
0x1800d69b8  jz      short loc_1800D69D1
0x1800d69ba  test    byte ptr [rcx+1Ch], 8
0x1800d69be  jz      short loc_1800D69D1
0x1800d69c0  mov     rcx, [rcx+10h]
0x1800d69c4  mov     edx, 149h
0x1800d69c9  mov     r8, r15
0x1800d69cc  call    WPP_SF_
0x1800d69d1  xor     ebx, ebx
0x1800d69d3  lea     rcx, [rsp+870h+UnicodeString]; UnicodeString
0x1800d69d8  call    cs:__imp_RtlFreeUnicodeString
0x1800d69df  nop     dword ptr [rax+rax+00h]
0x1800d69e4  lea     rcx, [rsp+870h+var_848]; this
0x1800d69e9  call    ?ReleasePrivilege@CNgscbScopedPrivilege@@QEAAXXZ; CNgscbScopedPrivilege::ReleasePrivilege(void)
0x1800d69ee  mov     eax, ebx
0x1800d69f0  mov     rcx, [rbp+770h+var_20]
0x1800d69f7  xor     rcx, rsp; StackCookie
0x1800d69fa  call    __security_check_cookie
0x1800d69ff  lea     r11, [rsp+870h+var_10]
0x1800d6a07  mov     rbx, [r11+28h]
0x1800d6a0b  mov     rdi, [r11+30h]
0x1800d6a0f  mov     rsp, r11
0x1800d6a12  pop     r15
0x1800d6a14  pop     r14
0x1800d6a16  pop     rbp
0x1800d6a17  retn
```
