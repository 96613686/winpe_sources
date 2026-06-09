# CFvePolicyReader::UsePolicyFromVolume(ushort const *)

- ea: `0x180057790`
- end: `0x180057aa4`
- name: `?UsePolicyFromVolume@CFvePolicyReader@@UEAAJPEBG@Z`
- size: `788`
- prototype: `__int64 __fastcall(CFvePolicyReader *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, registry_config`

## callees

- `0x1800050c0`
- `0x18003a230`
- `0x18003e314`
- `0x18003e418`
- `0x18003e470`
- `0x180057790`
- `0x18011efce`
- `0x18011f010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x18005798d`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x1800579c4`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x18005798d`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x1800579c4`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x180057842`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x180057858`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x180057842`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x180057858`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005786e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057884`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005786e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180057884`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180057a01`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180057a3e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180057a01`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180057a3e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18005790b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18005796d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18005790b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18005796d`

## string_xrefs

- `0x1800578e9`: `\Windows\System32\Config\SOFTWARE`
- `0x180057946`: `\Windows\System32\Config\SYSTEM`

## pseudocode

```c
__int64 __fastcall CFvePolicyReader::UsePolicyFromVolume(CFvePolicyReader *this, const unsigned __int16 *a2)
{
  signed int v4; // ebx
  LSTATUS KeyW; // eax
  LSTATUS v7; // eax
  LSTATUS v8; // eax
  LSTATUS v9; // eax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR FileName[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR File[264]; // [rsp+250h] [rbp+150h] BYREF

  memset_0(FileName, 0, 0x208u);
  hKey = 0;
  memset_0(File, 0, 0x208u);
  phkResult = 0;
  if ( a2 )
  {
    CFvePolicyReader::CloseRootPolicyKeys(this);
    CFvePolicyReader::UnloadVolumePolicy(this);
    v4 = StringCchCopyW(FileName, 0x104u, a2);
    if ( v4 < 0 )
      goto LABEL_4;
    v4 = StringCchCatW(FileName, 0x104u, L"\\Windows\\System32\\Config\\SOFTWARE");
    if ( v4 < 0 )
      goto LABEL_4;
    if ( GetFileAttributesW(FileName) == -1 )
      goto LABEL_13;
    v4 = StringCchCopyW(File, 0x104u, a2);
    if ( v4 < 0 )
      goto LABEL_4;
    v4 = StringCchCatW(File, 0x104u, L"\\Windows\\System32\\Config\\SYSTEM");
    if ( v4 < 0 )
      goto LABEL_4;
    if ( GetFileAttributesW(File) == -1 )
    {
LABEL_13:
      v4 = -2147024894;
LABEL_4:
      RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"BitLockerSoftwareRoot");
      RegUnLoadKeyW(HKEY_LOCAL_MACHINE, L"BitLockerSystemRoot");
      goto LABEL_5;
    }
    KeyW = RegLoadKeyW(HKEY_LOCAL_MACHINE, L"BitLockerSoftwareRoot", FileName);
    v4 = KeyW;
    if ( KeyW > 0 )
      v4 = (unsigned __int16)KeyW | 0x80070000;
    if ( v4 < 0 )
      goto LABEL_4;
    v7 = RegLoadKeyW(HKEY_LOCAL_MACHINE, L"BitLockerSystemRoot", File);
    v4 = v7;
    if ( v7 > 0 )
      v4 = (unsigned __int16)v7 | 0x80070000;
    if ( v4 < 0 )
      goto LABEL_4;
    v8 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"BitLockerSoftwareRoot", 0, 0x20019u, &hKey);
    v4 = v8;
    if ( v8 > 0 )
      v4 = (unsigned __int16)v8 | 0x80070000;
    if ( v4 < 0 )
      goto LABEL_4;
    v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"BitLockerSystemRoot", 0, 0x20019u, &phkResult);
    v4 = v9;
    if ( v9 > 0 )
      v4 = (unsigned __int16)v9 | 0x80070000;
    if ( v4 < 0 )
      goto LABEL_4;
    *((_QWORD *)this + 2) = hKey;
    *((_QWORD *)this + 3) = phkResult;
    hKey = 0;
    phkResult = 0;
    v4 = StringCchCopyW((unsigned __int16 *)this + 17, 0x104u, a2);
    if ( v4 < 0 )
      goto LABEL_4;
    *((_BYTE *)this + 32) = 1;
  }
  else
  {
    v4 = CFvePolicyReader::ResetRootPolicyKeys(this);
    if ( v4 < 0 )
      goto LABEL_4;
    v4 = StringCchCopyW((unsigned __int16 *)this + 17, 0x104u, (const unsigned __int16 *)&cchOriginalDestLength);
    if ( v4 < 0 )
      goto LABEL_4;
  }
LABEL_5:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180057790  mov     [rsp-8+arg_10], rbx
0x180057795  mov     [rsp-8+arg_18], rsi
0x18005779a  push    rbp
0x18005779b  push    rdi
0x18005779c  push    r12
0x18005779e  push    r13
0x1800577a0  push    r14
0x1800577a2  lea     rbp, [rsp-370h]
0x1800577aa  sub     rsp, 470h
0x1800577b1  mov     rax, cs:__security_cookie
0x1800577b8  xor     rax, rsp
0x1800577bb  mov     [rbp+390h+var_30], rax
0x1800577c2  mov     r14, rdx
0x1800577c5  mov     rdi, rcx
0x1800577c8  mov     ebx, 208h
0x1800577cd  lea     rcx, [rsp+490h+FileName]; void *
0x1800577d2  mov     r8d, ebx; Size
0x1800577d5  xor     edx, edx; Val
0x1800577d7  call    memset_0
0x1800577dc  mov     r8d, ebx; Size
0x1800577df  mov     [rsp+490h+hKey], 0
0x1800577e8  xor     edx, edx; Val
0x1800577ea  lea     rcx, [rbp+390h+File]; void *
0x1800577f1  call    memset_0
0x1800577f6  mov     [rsp+490h+var_458], 0
0x1800577ff  mov     r13, 0FFFFFFFF80000002h
0x180057806  mov     rcx, rdi; this
0x180057809  test    r14, r14
0x18005780c  jnz     loc_1800578BE
0x180057812  call    ?ResetRootPolicyKeys@CFvePolicyReader@@AEAAJXZ; CFvePolicyReader::ResetRootPolicyKeys(void)
0x180057817  mov     ebx, eax
0x180057819  test    eax, eax
0x18005781b  js      short loc_180057838
0x18005781d  lea     rcx, [rdi+22h]; unsigned __int16 *
0x180057821  mov     edx, 104h; unsigned __int64
0x180057826  lea     r8, cchOriginalDestLength; unsigned __int16 *
0x18005782d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180057832  mov     ebx, eax
0x180057834  test    eax, eax
0x180057836  jns     short loc_180057864
0x180057838  lea     rdx, aBitlockersoftw; "BitLockerSoftwareRoot"
0x18005783f  mov     rcx, r13; hKey
0x180057842  call    cs:__imp_RegUnLoadKeyW
0x180057849  nop     dword ptr [rax+rax+00h]
0x18005784e  lea     rdx, aBitlockersyste_0; "BitLockerSystemRoot"
0x180057855  mov     rcx, r13; hKey
0x180057858  call    cs:__imp_RegUnLoadKeyW
0x18005785f  nop     dword ptr [rax+rax+00h]
0x180057864  mov     rcx, [rsp+490h+hKey]; hKey
0x180057869  test    rcx, rcx
0x18005786c  jz      short loc_18005787A
0x18005786e  call    cs:__imp_RegCloseKey
0x180057875  nop     dword ptr [rax+rax+00h]
0x18005787a  mov     rcx, [rsp+490h+var_458]; hKey
0x18005787f  test    rcx, rcx
0x180057882  jz      short loc_180057890
0x180057884  call    cs:__imp_RegCloseKey
0x18005788b  nop     dword ptr [rax+rax+00h]
0x180057890  mov     eax, ebx
0x180057892  mov     rcx, [rbp+390h+var_30]
0x180057899  xor     rcx, rsp; StackCookie
0x18005789c  call    __security_check_cookie
0x1800578a1  lea     r11, [rsp+490h+var_20]
0x1800578a9  mov     rbx, [r11+40h]
0x1800578ad  mov     rsi, [r11+48h]
0x1800578b1  mov     rsp, r11
0x1800578b4  pop     r14
0x1800578b6  pop     r13
0x1800578b8  pop     r12
0x1800578ba  pop     rdi
0x1800578bb  pop     rbp
0x1800578bc  retn
0x1800578be  call    ?CloseRootPolicyKeys@CFvePolicyReader@@AEAAXXZ; CFvePolicyReader::CloseRootPolicyKeys(void)
0x1800578c3  mov     rcx, rdi; this
0x1800578c6  call    ?UnloadVolumePolicy@CFvePolicyReader@@AEAAXXZ; CFvePolicyReader::UnloadVolumePolicy(void)
0x1800578cb  mov     esi, 104h
0x1800578d0  lea     rcx, [rsp+490h+FileName]; unsigned __int16 *
0x1800578d5  mov     edx, esi; unsigned __int64
0x1800578d7  mov     r8, r14; unsigned __int16 *
0x1800578da  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800578df  mov     ebx, eax
0x1800578e1  test    eax, eax
0x1800578e3  js      loc_180057838
0x1800578e9  lea     r8, aWindowsSystem3; "\\Windows\\System32\\Config\\SOFTWARE"
0x1800578f0  mov     edx, esi; unsigned __int64
0x1800578f2  lea     rcx, [rsp+490h+FileName]; unsigned __int16 *
0x1800578f7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800578fc  mov     ebx, eax
0x1800578fe  test    eax, eax
0x180057900  js      loc_180057838
0x180057906  lea     rcx, [rsp+490h+FileName]; lpFileName
0x18005790b  call    cs:__imp_GetFileAttributesW
0x180057912  nop     dword ptr [rax+rax+00h]
0x180057917  or      r12d, 0FFFFFFFFh
0x18005791b  cmp     eax, r12d
0x18005791e  jnz     short loc_18005792A
0x180057920  mov     ebx, 80070002h
0x180057925  jmp     loc_180057838
0x18005792a  mov     r8, r14; unsigned __int16 *
0x18005792d  lea     rcx, [rbp+390h+File]; unsigned __int16 *
0x180057934  mov     rdx, rsi; unsigned __int64
0x180057937  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18005793c  mov     ebx, eax
0x18005793e  test    eax, eax
0x180057940  js      loc_180057838
0x180057946  lea     r8, aWindowsSystem3_1; "\\Windows\\System32\\Config\\SYSTEM"
0x18005794d  mov     rdx, rsi; unsigned __int64
0x180057950  lea     rcx, [rbp+390h+File]; unsigned __int16 *
0x180057957  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18005795c  mov     ebx, eax
0x18005795e  test    eax, eax
0x180057960  js      loc_180057838
0x180057966  lea     rcx, [rbp+390h+File]; lpFileName
0x18005796d  call    cs:__imp_GetFileAttributesW
0x180057974  nop     dword ptr [rax+rax+00h]
0x180057979  cmp     eax, r12d
0x18005797c  jz      short loc_180057920
0x18005797e  lea     r8, [rsp+490h+FileName]; lpFile
0x180057983  mov     rcx, r13; hKey
0x180057986  lea     rdx, aBitlockersoftw; "BitLockerSoftwareRoot"
0x18005798d  call    cs:__imp_RegLoadKeyW
0x180057994  nop     dword ptr [rax+rax+00h]
0x180057999  mov     ebx, eax
0x18005799b  mov     r12d, 80070000h
0x1800579a1  test    eax, eax
0x1800579a3  jle     short loc_1800579AB
0x1800579a5  movzx   ebx, ax
0x1800579a8  or      ebx, r12d
0x1800579ab  test    ebx, ebx
0x1800579ad  js      loc_180057838
0x1800579b3  lea     r8, [rbp+390h+File]; lpFile
0x1800579ba  mov     rcx, r13; hKey
0x1800579bd  lea     rdx, aBitlockersyste_0; "BitLockerSystemRoot"
0x1800579c4  call    cs:__imp_RegLoadKeyW
0x1800579cb  nop     dword ptr [rax+rax+00h]
0x1800579d0  mov     ebx, eax
0x1800579d2  test    eax, eax
0x1800579d4  jle     short loc_1800579DC
0x1800579d6  movzx   ebx, ax
0x1800579d9  or      ebx, r12d
0x1800579dc  test    ebx, ebx
0x1800579de  js      loc_180057838
0x1800579e4  lea     rax, [rsp+490h+hKey]
0x1800579e9  mov     r9d, 20019h; samDesired
0x1800579ef  xor     r8d, r8d; ulOptions
0x1800579f2  mov     [rsp+490h+phkResult], rax; phkResult
0x1800579f7  lea     rdx, aBitlockersoftw; "BitLockerSoftwareRoot"
0x1800579fe  mov     rcx, r13; hKey
0x180057a01  call    cs:__imp_RegOpenKeyExW
0x180057a08  nop     dword ptr [rax+rax+00h]
0x180057a0d  mov     ebx, eax
0x180057a0f  test    eax, eax
0x180057a11  jle     short loc_180057A19
0x180057a13  movzx   ebx, ax
0x180057a16  or      ebx, r12d
0x180057a19  test    ebx, ebx
0x180057a1b  js      loc_180057838
0x180057a21  lea     rax, [rsp+490h+var_458]
0x180057a26  mov     r9d, 20019h; samDesired
0x180057a2c  xor     r8d, r8d; ulOptions
0x180057a2f  mov     [rsp+490h+phkResult], rax; phkResult
0x180057a34  lea     rdx, aBitlockersyste_0; "BitLockerSystemRoot"
0x180057a3b  mov     rcx, r13; hKey
0x180057a3e  call    cs:__imp_RegOpenKeyExW
0x180057a45  nop     dword ptr [rax+rax+00h]
0x180057a4a  mov     ebx, eax
0x180057a4c  test    eax, eax
0x180057a4e  jle     short loc_180057A56
0x180057a50  movzx   ebx, ax
0x180057a53  or      ebx, r12d
0x180057a56  test    ebx, ebx
0x180057a58  js      loc_180057838
0x180057a5e  mov     rax, [rsp+490h+hKey]
0x180057a63  lea     rcx, [rdi+22h]; unsigned __int16 *
0x180057a67  mov     [rdi+10h], rax
0x180057a6b  mov     r8, r14; unsigned __int16 *
0x180057a6e  mov     rax, [rsp+490h+var_458]
0x180057a73  mov     rdx, rsi; unsigned __int64
0x180057a76  mov     [rdi+18h], rax
0x180057a7a  mov     [rsp+490h+hKey], 0
0x180057a83  mov     [rsp+490h+var_458], 0
0x180057a8c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180057a91  mov     ebx, eax
0x180057a93  test    eax, eax
0x180057a95  js      loc_180057838
0x180057a9b  mov     byte ptr [rdi+20h], 1
0x180057a9f  jmp     loc_180057864
```
