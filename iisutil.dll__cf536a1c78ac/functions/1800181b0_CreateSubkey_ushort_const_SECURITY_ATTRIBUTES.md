# CreateSubkey(ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x1800181b0`
- end: `0x180018379`
- name: `?CreateSubkey@@YAKPEBGPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `457`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800181b0`
- `0x180018ec0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001828f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001828f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180018209`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180018209`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018358`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180018358`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18001827f`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x18001827f`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1800182f8`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1800182f8`

## string_xrefs

- `0x180018331`: `CreateSubkey`
- `0x18001833f`: `servercommon\inetsrv\iis\iisrearc\core\common\util\helpfunc.cxx`
- `0x180018234`: `Creating/opening registry key failed\n`
- `0x1800182b6`: `Getting DACL to apply to registry key failed\n`
- `0x18001831f`: `Setting DACL on registry key failed\n`

## pseudocode

```c
__int64 __fastcall CreateSubkey(LPCWSTR lpSubKey, struct _SECURITY_ATTRIBUTES *a2)
{
  signed int LastError; // eax
  unsigned int v4; // ebx
  char *v5; // rcx
  unsigned int v6; // r8d
  void *lpSecurityDescriptor; // rcx
  char pSacl; // [rsp+30h] [rbp-40h]
  WINBOOL bDaclDefaulted; // [rsp+50h] [rbp-20h] BYREF
  HANDLE handle; // [rsp+58h] [rbp-18h] BYREF
  PACL pDacl; // [rsp+60h] [rbp-10h] BYREF
  DWORD v13; // [rsp+90h] [rbp+20h] BYREF
  WINBOOL bDaclPresent; // [rsp+98h] [rbp+28h] BYREF

  handle = 0;
  v13 = 0;
  LastError = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 1u, 0xF003Fu, a2, (PHKEY)&handle, &v13);
  v4 = LastError;
  if ( LastError )
  {
    if ( (g_dwDebugFlagsIISUtil & 0xF) == 0 )
      goto LABEL_20;
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    v5 = "Creating/opening registry key failed\n";
    v6 = 609;
    goto LABEL_19;
  }
  if ( a2 && v13 == 2 )
  {
    lpSecurityDescriptor = a2->lpSecurityDescriptor;
    bDaclPresent = 0;
    pDacl = 0;
    bDaclDefaulted = 0;
    if ( !GetSecurityDescriptorDacl(lpSecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( (g_dwDebugFlagsIISUtil & 0xF) == 0 )
        goto LABEL_20;
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v5 = "Getting DACL to apply to registry key failed\n";
      v6 = 636;
      goto LABEL_19;
    }
    if ( bDaclPresent )
    {
      LastError = SetSecurityInfo(handle, SE_REGISTRY_KEY, 4u, 0, 0, pDacl, 0);
      v4 = LastError;
      if ( LastError )
      {
        if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
        {
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          v5 = "Setting DACL on registry key failed\n";
          v6 = 658;
LABEL_19:
          PuDbgPrintError(
            (struct _DEBUG_PRINTS *)g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\helpfunc.cxx",
            v6,
            "CreateSubkey",
            LastError,
            v5,
            pSacl);
        }
      }
    }
  }
LABEL_20:
  if ( handle )
    RegCloseKey((HKEY)handle);
  return v4;
}

```

## disassembly

```asm
0x1800181b0  mov     r11, rsp
0x1800181b3  mov     [r11+8], rbx
0x1800181b7  mov     [r11+10h], rdi
0x1800181bb  push    rbp
0x1800181bc  mov     rbp, rsp
0x1800181bf  sub     rsp, 70h
0x1800181c3  lea     rax, [rbp+arg_10]
0x1800181c7  mov     [rbp+handle], 0
0x1800181cf  mov     [r11-38h], rax
0x1800181d3  mov     rdi, rdx
0x1800181d6  lea     rax, [rbp+handle]
0x1800181da  mov     [rbp+arg_10], 0
0x1800181e1  mov     [r11-40h], rax
0x1800181e5  xor     r9d, r9d; lpClass
0x1800181e8  mov     [r11-48h], rdx
0x1800181ec  xor     r8d, r8d; Reserved
0x1800181ef  mov     rdx, rcx; lpSubKey
0x1800181f2  mov     [rsp+70h+samDesired], 0F003Fh; samDesired
0x1800181fa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180018201  mov     [rsp+70h+dwOptions], 1; dwOptions
0x180018209  call    cs:__imp_RegCreateKeyExW
0x180018210  nop     dword ptr [rax+rax+00h]
0x180018215  mov     ebx, eax
0x180018217  test    eax, eax
0x180018219  jz      short loc_180018246
0x18001821b  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180018222  jz      loc_18001834F
0x180018228  test    eax, eax
0x18001822a  jle     short loc_180018234
0x18001822c  movzx   eax, ax
0x18001822f  or      eax, 80070000h
0x180018234  lea     rcx, aCreatingOpenin; "Creating/opening registry key failed\n"
0x18001823b  mov     r8d, 261h
0x180018241  jmp     loc_18001832C
0x180018246  test    rdi, rdi
0x180018249  jz      loc_18001834F
0x18001824f  cmp     [rbp+arg_10], 2
0x180018253  jnz     loc_18001834F
0x180018259  mov     rcx, [rdi+8]; pSecurityDescriptor
0x18001825d  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x180018261  lea     r8, [rbp+pDacl]; pDacl
0x180018265  mov     [rbp+bDaclPresent], 0
0x18001826c  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x180018270  mov     [rbp+pDacl], 0
0x180018278  mov     [rbp+bDaclDefaulted], 0
0x18001827f  call    cs:__imp_GetSecurityDescriptorDacl
0x180018286  nop     dword ptr [rax+rax+00h]
0x18001828b  test    eax, eax
0x18001828d  jnz     short loc_1800182C5
0x18001828f  call    cs:__imp_GetLastError
0x180018296  nop     dword ptr [rax+rax+00h]
0x18001829b  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x1800182a2  mov     ebx, eax
0x1800182a4  jz      loc_18001834F
0x1800182aa  test    eax, eax
0x1800182ac  jle     short loc_1800182B6
0x1800182ae  movzx   eax, ax
0x1800182b1  or      eax, 80070000h
0x1800182b6  lea     rcx, aGettingDaclToA; "Getting DACL to apply to registry key f"...
0x1800182bd  mov     r8d, 27Ch
0x1800182c3  jmp     short loc_18001832C
0x1800182c5  cmp     [rbp+bDaclPresent], 0
0x1800182c9  jz      loc_18001834F
0x1800182cf  mov     rax, [rbp+pDacl]
0x1800182d3  xor     r9d, r9d; psidOwner
0x1800182d6  mov     rcx, [rbp+handle]; handle
0x1800182da  mov     qword ptr [rsp+70h+pSacl], 0; char
0x1800182e3  mov     qword ptr [rsp+70h+samDesired], rax; pDacl
0x1800182e8  lea     edx, [r9+4]; ObjectType
0x1800182ec  mov     qword ptr [rsp+70h+dwOptions], 0; psidGroup
0x1800182f5  mov     r8d, edx; SecurityInfo
0x1800182f8  call    cs:__imp_SetSecurityInfo
0x1800182ff  nop     dword ptr [rax+rax+00h]
0x180018304  mov     ebx, eax
0x180018306  test    eax, eax
0x180018308  jz      short loc_18001834F
0x18001830a  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180018311  jz      short loc_18001834F
0x180018313  test    eax, eax
0x180018315  jle     short loc_18001831F
0x180018317  movzx   eax, ax
0x18001831a  or      eax, 80070000h
0x18001831f  lea     rcx, aSettingDaclOnR; "Setting DACL on registry key failed\n"
0x180018326  mov     r8d, 292h; unsigned int
0x18001832c  mov     qword ptr [rsp+70h+samDesired], rcx; char *
0x180018331  lea     r9, aCreatesubkey_0; "CreateSubkey"
0x180018338  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18001833f  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180018346  mov     [rsp+70h+dwOptions], eax; dwMessageId
0x18001834a  call    PuDbgPrintError
0x18001834f  mov     rcx, [rbp+handle]; hKey
0x180018353  test    rcx, rcx
0x180018356  jz      short loc_180018364
0x180018358  call    cs:__imp_RegCloseKey
0x18001835f  nop     dword ptr [rax+rax+00h]
0x180018364  lea     r11, [rsp+70h+var_s0]
0x180018369  mov     eax, ebx
0x18001836b  mov     rbx, [r11+10h]
0x18001836f  mov     rdi, [r11+18h]
0x180018373  mov     rsp, r11
0x180018376  pop     rbp
0x180018377  retn
```
