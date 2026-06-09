# ModifyDefPolicyToForceEncryption(int)

- ea: `0x180027044`
- end: `0x1800271e7`
- name: `?ModifyDefPolicyToForceEncryption@@YAKH@Z`
- size: `419`
- prototype: `unsigned int __fastcall(int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180017fc8`

## callees

- `0x180027044`
- `0x18007f904`
- `0x18007fba4`
- `0x18007fd2c`
- `0x1800811f4`
- `0x180095010`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x1800271a2`
- `ADVAPI32!RegSetValueExW` at `0x1800271a2`
- `ADVAPI32!RegOpenKeyExW` at `0x180027128`
- `ADVAPI32!RegOpenKeyExW` at `0x180027128`
- `ADVAPI32!RegQueryValueExW` at `0x180027167`
- `ADVAPI32!RegQueryValueExW` at `0x180027167`
- `ADVAPI32!RegCloseKey` at `0x1800271cd`
- `ADVAPI32!RegCloseKey` at `0x1800271cd`

## string_xrefs

- `0x18002711a`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Parameters`
- `0x1800270bb`: `SdoOpenDefaultProfile: entered\n`

## pseudocode

```c
__int64 __fastcall ModifyDefPolicyToForceEncryption(__int64 a1, __int64 a2)
{
  int v2; // edi
  unsigned int v3; // eax
  __int64 v4; // rcx
  void *v5; // rsi
  unsigned int v6; // ebx
  unsigned int v7; // edi
  SdoMachine *v8; // rbx
  _QWORD *v9; // r14
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  void *Block; // [rsp+38h] [rbp-8h] BYREF
  int Data; // [rsp+78h] [rbp+38h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+40h] BYREF
  DWORD Type; // [rsp+88h] [rbp+48h] BYREF

  Block = 0;
  Type = 0;
  v2 = a1;
  cbData = 0;
  Data = 0;
  hKey = 0;
  v3 = UserServerConnect(a1, a2, &Block);
  v5 = Block;
  v6 = v3;
  if ( v3 )
    goto LABEL_17;
  v7 = v2 != 0 ? 0xFFFFFFFC : 0;
  if ( !Block || (v8 = (SdoMachine *)*((_QWORD *)Block + 2)) == 0 )
  {
    v6 = 87;
    goto LABEL_17;
  }
  v9 = (char *)Block + 24;
  if ( *((_QWORD *)Block + 3) )
    goto LABEL_10;
  if ( (_QWORD)xmmword_1800D0F60 )
    ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gSdoWrapperTemplateFunc)(
      gSdoWrapperEtwContext,
      xmmword_1800D0F60,
      L"SdoOpenDefaultProfile: entered\n");
  if ( v5 == (void *)-24LL )
  {
    v6 = 87;
    goto LABEL_11;
  }
  v6 = SdoWrapOpenDefaultProfile(v8);
  if ( !v6 )
LABEL_10:
    v6 = SdoSetProfileData(v4, *v9, v7 + 8);
LABEL_11:
  if ( v6 == -2147352573 || !v6 )
  {
    v6 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"SYSTEM\\CurrentControlSet\\Services\\RemoteAccess\\Parameters",
           0,
           0x2001Fu,
           &hKey);
    if ( !v6 )
    {
      Type = 4;
      cbData = 4;
      v6 = RegQueryValueExW(hKey, L"ServerFlags", 0, &Type, (LPBYTE)&Data, &cbData);
      if ( !v6 )
      {
        Data &= 0xFFFFEF7F;
        v6 = RegSetValueExW(hKey, L"ServerFlags", 0, Type, (const BYTE *)&Data, cbData);
      }
    }
  }
LABEL_17:
  if ( v5 )
    UserServerDisconnect(v5);
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x180027044  push    rbp
0x180027046  push    rbx
0x180027047  push    rsi
0x180027048  push    rdi
0x180027049  push    r14
0x18002704b  mov     rbp, rsp
0x18002704e  sub     rsp, 40h
0x180027052  and     [rbp+Block], 0
0x180027057  lea     r8, [rbp+Block]
0x18002705b  and     [rbp+Type], 0
0x18002705f  mov     edi, ecx
0x180027061  and     [rbp+cbData], 0
0x180027065  and     [rbp+Data], 0
0x180027069  and     [rbp+hKey], 0
0x18002706e  call    UserServerConnect
0x180027073  mov     rsi, [rbp+Block]
0x180027077  mov     ebx, eax
0x180027079  test    eax, eax
0x18002707b  jnz     loc_1800271B7
0x180027081  neg     edi
0x180027083  sbb     edi, edi
0x180027085  and     edi, 0FFFFFFFCh
0x180027088  test    rsi, rsi
0x18002708b  jz      loc_1800271B2
0x180027091  mov     rbx, [rsi+10h]
0x180027095  test    rbx, rbx
0x180027098  jz      loc_1800271B2
0x18002709e  lea     r14, [rsi+18h]
0x1800270a2  cmp     qword ptr [r14], 0
0x1800270a6  jnz     short loc_1800270EA
0x1800270a8  mov     rdx, qword ptr cs:xmmword_1800D0F60
0x1800270af  test    rdx, rdx
0x1800270b2  jz      short loc_1800270CE
0x1800270b4  mov     rcx, cs:gSdoWrapperEtwContext
0x1800270bb  lea     r8, aSdoopendefault; "SdoOpenDefaultProfile: entered\n"
0x1800270c2  mov     rax, cs:gSdoWrapperTemplateFunc
0x1800270c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800270ce  test    r14, r14
0x1800270d1  jnz     short loc_1800270D9
0x1800270d3  lea     ebx, [r14+57h]
0x1800270d7  jmp     short loc_1800270F8
0x1800270d9  mov     rdx, r14
0x1800270dc  mov     rcx, rbx; this
0x1800270df  call    SdoWrapOpenDefaultProfile
0x1800270e4  mov     ebx, eax
0x1800270e6  test    eax, eax
0x1800270e8  jnz     short loc_1800270F8
0x1800270ea  mov     rdx, [r14]
0x1800270ed  lea     r8d, [rdi+8]
0x1800270f1  call    SdoSetProfileData
0x1800270f6  mov     ebx, eax
0x1800270f8  cmp     ebx, 80020003h
0x1800270fe  jz      short loc_180027108
0x180027100  test    ebx, ebx
0x180027102  jnz     loc_1800271B7
0x180027108  lea     rax, [rbp+hKey]
0x18002710c  mov     r9d, 2001Fh; samDesired
0x180027112  xor     r8d, r8d; ulOptions
0x180027115  mov     [rsp+40h+phkResult], rax; phkResult
0x18002711a  lea     rdx, aSystemCurrentc_12; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x180027121  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180027128  call    cs:__imp_RegOpenKeyExW
0x18002712f  nop     dword ptr [rax+rax+00h]
0x180027134  mov     ebx, eax
0x180027136  test    eax, eax
0x180027138  jnz     short loc_1800271B7
0x18002713a  mov     rcx, [rbp+hKey]; hKey
0x18002713e  lea     eax, [rbx+4]
0x180027141  mov     [rbp+Type], eax
0x180027144  lea     r9, [rbp+Type]; lpType
0x180027148  mov     [rbp+cbData], eax
0x18002714b  lea     rdx, aServerflags; "ServerFlags"
0x180027152  lea     rax, [rbp+cbData]
0x180027156  xor     r8d, r8d; lpReserved
0x180027159  mov     [rsp+40h+lpcbData], rax; lpcbData
0x18002715e  lea     rax, [rbp+Data]
0x180027162  mov     [rsp+40h+phkResult], rax; lpData
0x180027167  call    cs:__imp_RegQueryValueExW
0x18002716e  nop     dword ptr [rax+rax+00h]
0x180027173  mov     ebx, eax
0x180027175  test    eax, eax
0x180027177  jnz     short loc_1800271B7
0x180027179  mov     eax, [rbp+cbData]
0x18002717c  lea     rdx, aServerflags; "ServerFlags"
0x180027183  and     [rbp+Data], 0FFFFEF7Fh
0x18002718a  xor     r8d, r8d; Reserved
0x18002718d  mov     r9d, [rbp+Type]; dwType
0x180027191  mov     rcx, [rbp+hKey]; hKey
0x180027195  mov     dword ptr [rsp+40h+lpcbData], eax; cbData
0x180027199  lea     rax, [rbp+Data]
0x18002719d  mov     [rsp+40h+phkResult], rax; lpData
0x1800271a2  call    cs:__imp_RegSetValueExW
0x1800271a9  nop     dword ptr [rax+rax+00h]
0x1800271ae  mov     ebx, eax
0x1800271b0  jmp     short loc_1800271B7
0x1800271b2  mov     ebx, 57h ; 'W'
0x1800271b7  test    rsi, rsi
0x1800271ba  jz      short loc_1800271C4
0x1800271bc  mov     rcx, rsi; Block
0x1800271bf  call    UserServerDisconnect
0x1800271c4  mov     rcx, [rbp+hKey]; hKey
0x1800271c8  test    rcx, rcx
0x1800271cb  jz      short loc_1800271D9
0x1800271cd  call    cs:__imp_RegCloseKey
0x1800271d4  nop     dword ptr [rax+rax+00h]
0x1800271d9  mov     eax, ebx
0x1800271db  add     rsp, 40h
0x1800271df  pop     r14
0x1800271e1  pop     rdi
0x1800271e2  pop     rsi
0x1800271e3  pop     rbx
0x1800271e4  pop     rbp
0x1800271e5  retn
```
