# CreateSubkey(ushort const *,_SECURITY_ATTRIBUTES *)

- ea: `0x180017490`
- end: `0x180017636`
- name: `?CreateSubkey@@YAKPEBGPEAU_SECURITY_ATTRIBUTES@@@Z`
- size: `422`
- prototype: `unsigned int __fastcall(LPCWSTR lpSubKey, struct _SECURITY_ATTRIBUTES *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180017490`
- `0x1800180c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017563`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017563`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800174e9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800174e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001761c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001761c`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180017559`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180017559`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1800175c2`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1800175c2`

## string_xrefs

- `0x1800175f5`: `CreateSubkey`
- `0x180017603`: `servercommon\inetsrv\iis\iisrearc\core\common\util\helpfunc.cxx`
- `0x18001750e`: `Creating/opening registry key failed\n`
- `0x180017584`: `Getting DACL to apply to registry key failed\n`
- `0x1800175e3`: `Setting DACL on registry key failed\n`

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
0x180017490  mov     r11, rsp
0x180017493  mov     [r11+8], rbx
0x180017497  mov     [r11+10h], rdi
0x18001749b  push    rbp
0x18001749c  mov     rbp, rsp
0x18001749f  sub     rsp, 70h
0x1800174a3  lea     rax, [rbp+arg_10]
0x1800174a7  mov     [rbp+handle], 0
0x1800174af  mov     [r11-38h], rax
0x1800174b3  mov     rdi, rdx
0x1800174b6  lea     rax, [rbp+handle]
0x1800174ba  mov     [rbp+arg_10], 0
0x1800174c1  mov     [r11-40h], rax
0x1800174c5  xor     r9d, r9d; lpClass
0x1800174c8  mov     [r11-48h], rdx
0x1800174cc  xor     r8d, r8d; Reserved
0x1800174cf  mov     rdx, rcx; lpSubKey
0x1800174d2  mov     [rsp+70h+samDesired], 0F003Fh; samDesired
0x1800174da  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800174e1  mov     [rsp+70h+dwOptions], 1; dwOptions
0x1800174e9  call    cs:__imp_RegCreateKeyExW
0x1800174ef  mov     ebx, eax
0x1800174f1  test    eax, eax
0x1800174f3  jz      short loc_180017520
0x1800174f5  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x1800174fc  jz      loc_180017613
0x180017502  test    eax, eax
0x180017504  jle     short loc_18001750E
0x180017506  movzx   eax, ax
0x180017509  or      eax, 80070000h
0x18001750e  lea     rcx, aCreatingOpenin; "Creating/opening registry key failed\n"
0x180017515  mov     r8d, 261h
0x18001751b  jmp     loc_1800175F0
0x180017520  test    rdi, rdi
0x180017523  jz      loc_180017613
0x180017529  cmp     [rbp+arg_10], 2
0x18001752d  jnz     loc_180017613
0x180017533  mov     rcx, [rdi+8]; pSecurityDescriptor
0x180017537  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x18001753b  lea     r8, [rbp+pDacl]; pDacl
0x18001753f  mov     [rbp+bDaclPresent], 0
0x180017546  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x18001754a  mov     [rbp+pDacl], 0
0x180017552  mov     [rbp+bDaclDefaulted], 0
0x180017559  call    cs:__imp_GetSecurityDescriptorDacl
0x18001755f  test    eax, eax
0x180017561  jnz     short loc_180017593
0x180017563  call    cs:__imp_GetLastError
0x180017569  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180017570  mov     ebx, eax
0x180017572  jz      loc_180017613
0x180017578  test    eax, eax
0x18001757a  jle     short loc_180017584
0x18001757c  movzx   eax, ax
0x18001757f  or      eax, 80070000h
0x180017584  lea     rcx, aGettingDaclToA; "Getting DACL to apply to registry key f"...
0x18001758b  mov     r8d, 27Ch
0x180017591  jmp     short loc_1800175F0
0x180017593  cmp     [rbp+bDaclPresent], 0
0x180017597  jz      short loc_180017613
0x180017599  mov     rax, [rbp+pDacl]
0x18001759d  xor     r9d, r9d; psidOwner
0x1800175a0  mov     rcx, [rbp+handle]; handle
0x1800175a4  mov     qword ptr [rsp+70h+pSacl], 0; char
0x1800175ad  mov     qword ptr [rsp+70h+samDesired], rax; pDacl
0x1800175b2  lea     edx, [r9+4]; ObjectType
0x1800175b6  mov     qword ptr [rsp+70h+dwOptions], 0; psidGroup
0x1800175bf  mov     r8d, edx; SecurityInfo
0x1800175c2  call    cs:__imp_SetSecurityInfo
0x1800175c8  mov     ebx, eax
0x1800175ca  test    eax, eax
0x1800175cc  jz      short loc_180017613
0x1800175ce  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x1800175d5  jz      short loc_180017613
0x1800175d7  test    eax, eax
0x1800175d9  jle     short loc_1800175E3
0x1800175db  movzx   eax, ax
0x1800175de  or      eax, 80070000h
0x1800175e3  lea     rcx, aSettingDaclOnR; "Setting DACL on registry key failed\n"
0x1800175ea  mov     r8d, 292h; unsigned int
0x1800175f0  mov     qword ptr [rsp+70h+samDesired], rcx; char *
0x1800175f5  lea     r9, aCreatesubkey_0; "CreateSubkey"
0x1800175fc  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180017603  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001760a  mov     [rsp+70h+dwOptions], eax; dwMessageId
0x18001760e  call    PuDbgPrintError
0x180017613  mov     rcx, [rbp+handle]; hKey
0x180017617  test    rcx, rcx
0x18001761a  jz      short loc_180017622
0x18001761c  call    cs:__imp_RegCloseKey
0x180017622  lea     r11, [rsp+70h+var_s0]
0x180017627  mov     eax, ebx
0x180017629  mov     rbx, [r11+10h]
0x18001762d  mov     rdi, [r11+18h]
0x180017631  mov     rsp, r11
0x180017634  pop     rbp
0x180017635  retn
```
