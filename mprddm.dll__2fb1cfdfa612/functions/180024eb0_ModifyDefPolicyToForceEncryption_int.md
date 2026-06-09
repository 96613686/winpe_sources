# ModifyDefPolicyToForceEncryption(int)

- ea: `0x180024eb0`
- end: `0x18002503e`
- name: `?ModifyDefPolicyToForceEncryption@@YAKH@Z`
- size: `398`
- prototype: `unsigned int __fastcall(int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x180017794`

## callees

- `0x180024eb0`
- `0x18007aa4c`
- `0x18007acc4`
- `0x18007ae3c`
- `0x18007c248`
- `0x18008e010`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180025006`
- `ADVAPI32!RegSetValueExW` at `0x180025006`
- `ADVAPI32!RegOpenKeyExW` at `0x180024f98`
- `ADVAPI32!RegOpenKeyExW` at `0x180024f98`
- `ADVAPI32!RegQueryValueExW` at `0x180024fd1`
- `ADVAPI32!RegQueryValueExW` at `0x180024fd1`
- `ADVAPI32!RegCloseKey` at `0x18002502b`
- `ADVAPI32!RegCloseKey` at `0x18002502b`

## string_xrefs

- `0x180024f8a`: `SYSTEM\CurrentControlSet\Services\RemoteAccess\Parameters`
- `0x180024f36`: `SdoOpenDefaultProfile: entered\n`

## pseudocode

```c
__int64 __fastcall ModifyDefPolicyToForceEncryption(__int64 a1, __int64 a2)
{
  int v2; // esi
  unsigned int v3; // eax
  __int64 v4; // rcx
  void *v5; // rdi
  unsigned int v6; // ebx
  unsigned int v7; // esi
  SdoMachine *v8; // rbx
  _QWORD *v9; // r14
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  void *Block; // [rsp+38h] [rbp-8h] BYREF
  int Data; // [rsp+78h] [rbp+38h] BYREF
  DWORD cbData; // [rsp+80h] [rbp+40h] BYREF
  DWORD Type; // [rsp+88h] [rbp+48h] BYREF

  Block = 0;
  v2 = a1;
  Type = 0;
  cbData = 0;
  Data = 0;
  hKey = 0;
  v3 = UserServerConnect(a1, a2, &Block);
  v5 = Block;
  v6 = v3;
  if ( !v3 )
  {
    v7 = v2 != 0 ? 0xFFFFFFFC : 0;
    if ( Block && (v8 = (SdoMachine *)*((_QWORD *)Block + 2)) != 0 )
    {
      v9 = (char *)Block + 24;
      if ( *((_QWORD *)Block + 3) )
        goto LABEL_8;
      if ( (_QWORD)xmmword_1800C9F60 )
        ((void (__fastcall *)(__int64, _QWORD, const wchar_t *))gSdoWrapperTemplateFunc)(
          gSdoWrapperEtwContext,
          xmmword_1800C9F60,
          L"SdoOpenDefaultProfile: entered\n");
      v6 = SdoWrapOpenDefaultProfile(v8);
      if ( !v6 )
LABEL_8:
        v6 = SdoSetProfileData(v4, *v9, v7 + 8);
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
    }
    else
    {
      v6 = 87;
    }
  }
  if ( v5 )
    UserServerDisconnect(v5);
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x180024eb0  push    rbp
0x180024eb2  push    rbx
0x180024eb3  push    rsi
0x180024eb4  push    rdi
0x180024eb5  push    r14
0x180024eb7  mov     rbp, rsp
0x180024eba  sub     rsp, 40h
0x180024ebe  lea     r8, [rbp+Block]
0x180024ec2  mov     [rbp+Block], 0
0x180024eca  mov     esi, ecx
0x180024ecc  mov     [rbp+Type], 0
0x180024ed3  mov     [rbp+cbData], 0
0x180024eda  mov     [rbp+Data], 0
0x180024ee1  mov     [rbp+hKey], 0
0x180024ee9  call    UserServerConnect
0x180024eee  mov     rdi, [rbp+Block]
0x180024ef2  mov     ebx, eax
0x180024ef4  test    eax, eax
0x180024ef6  jnz     loc_180025015
0x180024efc  neg     esi
0x180024efe  sbb     esi, esi
0x180024f00  and     esi, 0FFFFFFFCh
0x180024f03  test    rdi, rdi
0x180024f06  jz      loc_180025010
0x180024f0c  mov     rbx, [rdi+10h]
0x180024f10  test    rbx, rbx
0x180024f13  jz      loc_180025010
0x180024f19  lea     r14, [rdi+18h]
0x180024f1d  cmp     qword ptr [r14], 0
0x180024f21  jnz     short loc_180024F5A
0x180024f23  mov     rdx, qword ptr cs:xmmword_1800C9F60
0x180024f2a  test    rdx, rdx
0x180024f2d  jz      short loc_180024F49
0x180024f2f  mov     rcx, cs:gSdoWrapperEtwContext
0x180024f36  lea     r8, aSdoopendefault; "SdoOpenDefaultProfile: entered\n"
0x180024f3d  mov     rax, cs:gSdoWrapperTemplateFunc
0x180024f44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f49  mov     rdx, r14
0x180024f4c  mov     rcx, rbx; this
0x180024f4f  call    SdoWrapOpenDefaultProfile
0x180024f54  mov     ebx, eax
0x180024f56  test    eax, eax
0x180024f58  jnz     short loc_180024F68
0x180024f5a  mov     rdx, [r14]
0x180024f5d  lea     r8d, [rsi+8]
0x180024f61  call    SdoSetProfileData
0x180024f66  mov     ebx, eax
0x180024f68  cmp     ebx, 80020003h
0x180024f6e  jz      short loc_180024F78
0x180024f70  test    ebx, ebx
0x180024f72  jnz     loc_180025015
0x180024f78  lea     rax, [rbp+hKey]
0x180024f7c  mov     r9d, 2001Fh; samDesired
0x180024f82  xor     r8d, r8d; ulOptions
0x180024f85  mov     [rsp+40h+phkResult], rax; phkResult
0x180024f8a  lea     rdx, aSystemCurrentc_12; "SYSTEM\\CurrentControlSet\\Services\\Re"...
0x180024f91  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180024f98  call    cs:__imp_RegOpenKeyExW
0x180024f9e  mov     ebx, eax
0x180024fa0  test    eax, eax
0x180024fa2  jnz     short loc_180025015
0x180024fa4  mov     rcx, [rbp+hKey]; hKey
0x180024fa8  lea     eax, [rbx+4]
0x180024fab  mov     [rbp+Type], eax
0x180024fae  lea     r9, [rbp+Type]; lpType
0x180024fb2  mov     [rbp+cbData], eax
0x180024fb5  lea     rdx, aServerflags; "ServerFlags"
0x180024fbc  lea     rax, [rbp+cbData]
0x180024fc0  xor     r8d, r8d; lpReserved
0x180024fc3  mov     [rsp+40h+lpcbData], rax; lpcbData
0x180024fc8  lea     rax, [rbp+Data]
0x180024fcc  mov     [rsp+40h+phkResult], rax; lpData
0x180024fd1  call    cs:__imp_RegQueryValueExW
0x180024fd7  mov     ebx, eax
0x180024fd9  test    eax, eax
0x180024fdb  jnz     short loc_180025015
0x180024fdd  mov     eax, [rbp+cbData]
0x180024fe0  lea     rdx, aServerflags; "ServerFlags"
0x180024fe7  and     [rbp+Data], 0FFFFEF7Fh
0x180024fee  xor     r8d, r8d; Reserved
0x180024ff1  mov     r9d, [rbp+Type]; dwType
0x180024ff5  mov     rcx, [rbp+hKey]; hKey
0x180024ff9  mov     dword ptr [rsp+40h+lpcbData], eax; cbData
0x180024ffd  lea     rax, [rbp+Data]
0x180025001  mov     [rsp+40h+phkResult], rax; lpData
0x180025006  call    cs:__imp_RegSetValueExW
0x18002500c  mov     ebx, eax
0x18002500e  jmp     short loc_180025015
0x180025010  mov     ebx, 57h ; 'W'
0x180025015  test    rdi, rdi
0x180025018  jz      short loc_180025022
0x18002501a  mov     rcx, rdi; Block
0x18002501d  call    UserServerDisconnect
0x180025022  mov     rcx, [rbp+hKey]; hKey
0x180025026  test    rcx, rcx
0x180025029  jz      short loc_180025031
0x18002502b  call    cs:__imp_RegCloseKey
0x180025031  mov     eax, ebx
0x180025033  add     rsp, 40h
0x180025037  pop     r14
0x180025039  pop     rdi
0x18002503a  pop     rsi
0x18002503b  pop     rbx
0x18002503c  pop     rbp
0x18002503d  retn
```
