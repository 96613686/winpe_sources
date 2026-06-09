# RestrictDriverInstallationToAdministrators(void)

- ea: `0x18002faa8`
- end: `0x18002fb37`
- name: `?RestrictDriverInstallationToAdministrators@@YAHXZ`
- size: `143`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002f770`

## callees

- `0x18000d57c`
- `0x18002faa8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002faf3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002faf3`

## string_xrefs

- `0x18002fb1c`: `Failed to query RegValue for RestrictDriverInstallationToAdministrators: hr: 0x%x`
- `0x18002fac0`: `RestrictDriverInstallationToAdministrators`
- `0x18002fb23`: `RestrictDriverInstallationToAdministrators`

## pseudocode

```c
__int64 RestrictDriverInstallationToAdministrators(void)
{
  int ValueW; // eax
  unsigned int v1; // ebx
  int v3; // [rsp+50h] [rbp+8h] BYREF
  DWORD v4; // [rsp+58h] [rbp+10h] BYREF

  v3 = 0;
  v4 = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Policies\\Microsoft\\Windows NT\\Printers\\PointAndPrint",
             L"RestrictDriverInstallationToAdministrators",
             0x10u,
             0,
             &v3,
             &v4);
  if ( ValueW )
  {
    v1 = 1;
    if ( ValueW > 0 )
      ValueW = (unsigned __int16)ValueW | 0x80070000;
    ClassInstallerTelemetry::WriteDbgTraceError(
      "RestrictDriverInstallationToAdministrators",
      L"Failed to query RegValue for RestrictDriverInstallationToAdministrators: hr: 0x%x",
      (unsigned int)ValueW);
  }
  else
  {
    return v3 != 0;
  }
  return v1;
}

```

## disassembly

```asm
0x18002faa8  mov     r11, rsp
0x18002faab  push    rbx
0x18002faac  sub     rsp, 40h
0x18002fab0  lea     rax, [r11+10h]
0x18002fab4  mov     [rsp+48h+arg_0], 0
0x18002fabc  mov     [r11-18h], rax
0x18002fac0  lea     r8, aRestrictdriver_0; "RestrictDriverInstallationToAdministrat"...
0x18002fac7  lea     rax, [r11+8]
0x18002facb  mov     [rsp+48h+arg_8], 4
0x18002fad3  mov     [r11-20h], rax
0x18002fad7  lea     rdx, aSoftwarePolici_6; "Software\\Policies\\Microsoft\\Windows "...
0x18002fade  mov     r9d, 10h; dwFlags
0x18002fae4  mov     qword ptr [r11-28h], 0
0x18002faec  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002faf3  call    cs:__imp_RegGetValueW
0x18002faf9  test    eax, eax
0x18002fafb  jnz     short loc_18002FB08
0x18002fafd  xor     ebx, ebx
0x18002faff  cmp     [rsp+48h+arg_0], ebx
0x18002fb03  setnz   bl
0x18002fb06  jmp     short loc_18002FB2F
0x18002fb08  mov     ebx, 1
0x18002fb0d  test    eax, eax
0x18002fb0f  jle     short loc_18002FB19
0x18002fb11  movzx   eax, ax
0x18002fb14  or      eax, 80070000h
0x18002fb19  mov     r8d, eax
0x18002fb1c  lea     rdx, aFailedToQueryR; "Failed to query RegValue for RestrictDr"...
0x18002fb23  lea     rcx, aRestrictdriver; "RestrictDriverInstallationToAdministrat"...
0x18002fb2a  call    ?WriteDbgTraceError@ClassInstallerTelemetry@@SAXPEADPEAGZZ; ClassInstallerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18002fb2f  mov     eax, ebx
0x18002fb31  add     rsp, 40h
0x18002fb35  pop     rbx
0x18002fb36  retn
```
